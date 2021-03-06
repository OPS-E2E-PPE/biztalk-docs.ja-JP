---
title: パフォーマンス収集ルールを表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 546aa853-c372-4e26-a1ed-19294c658583
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ddb8f0482864945a6dd89cc953523d0fb6642cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253377"
---
# <a name="how-to-display-performance-collection-rules"></a>パフォーマンス収集ルールを表示する方法
パフォーマンス収集ルールを表示するには、このセクションでは、スクリプトを使用します。 このスクリプトは、ほとんどの規則は機能します。 次の表に示されている列を含む .csv ファイルを作成し、Office Excel を使用して表示できます。  
  
|[列]|説明|  
|------------|-----------------|  
|WriteToDB または CollectionPerformanceData|Operations Manager データベースに書き込みます。|  
|WriteToDW または CollectPerfDataWarehouse|データ ウェアハウスに書き込みます。|  
|WC|パフォーマンス カウンタのベースライン データをオペレーション データベースに格納します。|  
  
#### <a name="to-display-performance-collection-rules"></a>パフォーマンス収集ルールを表示するには  
 管理グループのパフォーマンス収集ルールを表示するには、次のスクリプトを実行します。  
  
```  
function GetPerfCounterName ([String] $configuration)   
{   
$config = [xml] ("<config>" + $configuration + "</config>")   
return ($config.Config.ObjectName + "\" + $config.Config.CounterName)   
}   
function GetFrequency ([String] $configuration)   
{   
$config = [xml] ("<config>" + $configuration + "</config>")   
$frequency = $config.Config.Frequency;   
if($frequency -eq $null)   
{   
$frequency = $config.Config.IntervalSeconds;   
}   
return ($frequency)   
}   
function GetDisplayName($performanceRule)   
{   
if($performanceRule.DisplayName -eq $null)   
{   
return ($performanceRule.Name);   
}   
else   
{   
return ($performanceRule.DisplayName);   
}   
}   
function GetWriteActionNames($performanceRule)   
{   
$writeActions = "";   
foreach($writeAction in $performanceRule.WriteActionCollection)   
{   
$writeActions += " " + $writeAction.Name;   
}   
return ($writeActions);   
}   
$perf_collection_rules = Get-SCOMManagementPack -DisplayName "BizTalk Server Monitoring" | Get-SCOMRule | where-object{$_.Category -eq "PerformanceCollection"}  
  
$perf_collection_rules | select-object @{name="Type";expression={foreach-object {(Get-SCOMClass -id:$_.Target.Id).DisplayName}}},@{name="RuleDisplayName";expression={foreach-object {GetDisplayName $_}}} ,@{name="CounterName";expression={foreach-object {GetPerfCounterName $_.DataSourceCollection[0].Configuration}}},@{name="Frequency";expression={foreach-object {GetFrequency $_.DataSourceCollection[0].Configuration}}},@{name="WriteActions";expression={foreach-object {GetWriteActionNames $_}}} | sort Type,RuleDisplayName,CounterName | export-csv "c:\perf_collection_rules.csv"  
  
```