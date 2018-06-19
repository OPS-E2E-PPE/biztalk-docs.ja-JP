---
title: パフォーマンス収集ルールを表示する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: cd7b7d1d2e368572740a3c7a54799bc56b2330e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298186"
---
# <a name="how-to-display-performance-collection-rules"></a>パフォーマンス収集ルールを表示する方法
パフォーマンス収集ルールを表示するには、このセクションのスクリプトを使用します。 このスクリプトは、規則の大部分に対して機能します。 次の表で示されている列を含む .csv ファイルを作成し、Office Excel を使用して表示できます。  
  
|列|Description|  
|------------|-----------------|  
|WriteToDB または CollectionPerformanceData|Operations Manager データベースに書き込みます。|  
|WriteToDW または CollectPerfDataWarehouse|データ ウェアハウスに書き込みます。|  
|WC|パフォーマンス カウンタのベースライン データをオペレーション データベースに格納します。|  
  
#### <a name="to-display-performance-collection-rules"></a>パフォーマンス収集ルールを表示するには  
 管理グループでのパフォーマンス収集ルールを表示するには、次のスクリプトを実行します。  
  
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