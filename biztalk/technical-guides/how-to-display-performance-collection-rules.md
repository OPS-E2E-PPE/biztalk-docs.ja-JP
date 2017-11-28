---
title: "パフォーマンス収集ルールを表示する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 546aa853-c372-4e26-a1ed-19294c658583
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd7b7d1d2e368572740a3c7a54799bc56b2330e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-display-performance-collection-rules"></a><span data-ttu-id="6f5c0-102">パフォーマンス収集ルールを表示する方法</span><span class="sxs-lookup"><span data-stu-id="6f5c0-102">How to Display Performance Collection Rules</span></span>
<span data-ttu-id="6f5c0-103">パフォーマンス収集ルールを表示するには、このセクションのスクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="6f5c0-103">To display performance collection rules, use the script in this section.</span></span> <span data-ttu-id="6f5c0-104">このスクリプトは、規則の大部分に対して機能します。</span><span class="sxs-lookup"><span data-stu-id="6f5c0-104">This script works for the majority of rules.</span></span> <span data-ttu-id="6f5c0-105">次の表で示されている列を含む .csv ファイルを作成し、Office Excel を使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="6f5c0-105">It creates a .csv file that includes the columns listed in the following table, and can be viewed using Office Excel.</span></span>  
  
|<span data-ttu-id="6f5c0-106">列</span><span class="sxs-lookup"><span data-stu-id="6f5c0-106">Column</span></span>|<span data-ttu-id="6f5c0-107">Description</span><span class="sxs-lookup"><span data-stu-id="6f5c0-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="6f5c0-108">WriteToDB または CollectionPerformanceData</span><span class="sxs-lookup"><span data-stu-id="6f5c0-108">WriteToDB or CollectionPerformanceData</span></span>|<span data-ttu-id="6f5c0-109">Operations Manager データベースに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="6f5c0-109">Writes to the Operations Manager database.</span></span>|  
|<span data-ttu-id="6f5c0-110">WriteToDW または CollectPerfDataWarehouse</span><span class="sxs-lookup"><span data-stu-id="6f5c0-110">WriteToDW or CollectPerfDataWarehouse</span></span>|<span data-ttu-id="6f5c0-111">データ ウェアハウスに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="6f5c0-111">Writes to the data warehouse.</span></span>|  
|<span data-ttu-id="6f5c0-112">WC</span><span class="sxs-lookup"><span data-stu-id="6f5c0-112">WC</span></span>|<span data-ttu-id="6f5c0-113">パフォーマンス カウンタのベースライン データをオペレーション データベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="6f5c0-113">Stores baseline data for a performance counter into the operational database.</span></span>|  
  
#### <a name="to-display-performance-collection-rules"></a><span data-ttu-id="6f5c0-114">パフォーマンス収集ルールを表示するには</span><span class="sxs-lookup"><span data-stu-id="6f5c0-114">To display performance collection rules</span></span>  
 <span data-ttu-id="6f5c0-115">管理グループでのパフォーマンス収集ルールを表示するには、次のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="6f5c0-115">To display the performance collection rules in the management group, run the following script:</span></span>  
  
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