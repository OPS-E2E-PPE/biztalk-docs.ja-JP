---
title: モニタのしきい値を表示する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88d88b15-0691-49d9-b116-1a2ae95bead9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be3818512f76e95655e0441f039176fe6f855344
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297706"
---
# <a name="how-to-display-monitor-thresholds"></a><span data-ttu-id="d4904-102">モニタのしきい値を表示する方法</span><span class="sxs-lookup"><span data-stu-id="d4904-102">How to Display Monitor Thresholds</span></span>
<span data-ttu-id="d4904-103">モニタのしきい値を表示するには、このセクションで説明されているスクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4904-103">To display monitor thresholds, use the script described in this section.</span></span> <span data-ttu-id="d4904-104">このスクリプトは、ほとんどのモニタに対して機能します。</span><span class="sxs-lookup"><span data-stu-id="d4904-104">This script works for the majority of monitors.</span></span> <span data-ttu-id="d4904-105">次の表で説明する列を含む .csv ファイルを作成し、Office Excel を使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="d4904-105">It creates a .csv file that includes the columns described in the following table, and can be viewed using Office Excel.</span></span>  
  
|<span data-ttu-id="d4904-106">列</span><span class="sxs-lookup"><span data-stu-id="d4904-106">Column</span></span>|<span data-ttu-id="d4904-107">Description</span><span class="sxs-lookup"><span data-stu-id="d4904-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d4904-108">型</span><span class="sxs-lookup"><span data-stu-id="d4904-108">Type</span></span>|<span data-ttu-id="d4904-109">モニターが対象となるオブジェクトの型。</span><span class="sxs-lookup"><span data-stu-id="d4904-109">The type of objects the monitor is targeted.</span></span>|  
|<span data-ttu-id="d4904-110">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d4904-110">DisplayName</span></span>|<span data-ttu-id="d4904-111">モニターの表示名。</span><span class="sxs-lookup"><span data-stu-id="d4904-111">The display name of the monitor.</span></span>|  
|<span data-ttu-id="d4904-112">しきい値</span><span class="sxs-lookup"><span data-stu-id="d4904-112">Threshold</span></span>|<span data-ttu-id="d4904-113">モニターによって使用されるしきい値。</span><span class="sxs-lookup"><span data-stu-id="d4904-113">The threshold used by the monitor.</span></span>|  
|<span data-ttu-id="d4904-114">AlertOnState</span><span class="sxs-lookup"><span data-stu-id="d4904-114">AlertOnState</span></span>|<span data-ttu-id="d4904-115">状態が変更されたときに、モニターがアラートを生成するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="d4904-115">Determines whether the monitor generates an alert when the state changes.</span></span>|  
|<span data-ttu-id="d4904-116">AutoResolveAlert</span><span class="sxs-lookup"><span data-stu-id="d4904-116">AutoResolveAlert</span></span>|<span data-ttu-id="d4904-117">かどうか、生成されたアラートを自動的に解決するモニターの状態が緑色に戻ったときに決定します。</span><span class="sxs-lookup"><span data-stu-id="d4904-117">Determines whether the generated alert will be automatically resolved when the monitor state goes back to green.</span></span>|  
|<span data-ttu-id="d4904-118">AlertSeverity</span><span class="sxs-lookup"><span data-stu-id="d4904-118">AlertSeverity</span></span>|<span data-ttu-id="d4904-119">生成されたアラートの重大度。</span><span class="sxs-lookup"><span data-stu-id="d4904-119">The severity of the generated alert.</span></span>|  
  
#### <a name="to-display-monitor-thresholds"></a><span data-ttu-id="d4904-120">モニターのしきい値を表示するには</span><span class="sxs-lookup"><span data-stu-id="d4904-120">To display monitor thresholds</span></span>  
 <span data-ttu-id="d4904-121">モニタのしきい値を表示する .csv ファイルを作成する次のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="d4904-121">Run the following script to create the .csv file that displays the monitor thresholds:</span></span>  
  
```  
function GetThreshold ([String] $configuration)   
{   
  $config = [xml] ("<config>" + $configuration + "</config>")   
  $threshold = $config.Config.Threshold   
  if($threshold -eq $null)   
  {   
    $threshold = $config.Config.MemoryThreshold   
  }   
  if($threshold -eq $null)   
  {   
    $threshold = $config.Config.CPUPercentageThreshold   
  }   
  if($threshold -eq $null)   
  {   
    if($config.Config.Threshold1 -ne $null -and $config.Config.Threshold2 -ne $null)   
    {   
      $threshold = "first threshold is: " + $config.Config.Threshold1 + " second threshold is: " + $config.Config.Threshold2   
    }   
  }   
  if($threshold -eq $null)   
  {   
    if($config.Config.ThresholdWarnSec -ne $null -and $config.Config.ThresholdErrorSec -ne $null)   
    {   
      $threshold = "warning threshold is: " + $config.Config.ThresholdWarnSec + " error threshold is: " + $config.Config.ThresholdErrorSec   
    }   
  }   
  if($threshold -eq $null)   
  {   
    if($config.Config.LearningAndBaseliningSettings -ne $null)   
    {   
      $threshold = "no threshold (baseline monitor)"   
    }   
  }   
  return $threshold   
}   
#$perfMonitors = get-monitor -Criteria:"IsUnitMonitor=1 and Category='PerformanceHealth'"   
$perfMonitors = Get-ScommanagementPack -DisplayName "BizTalk Server Monitoring" | get-scommonitor | where-object{$_.XmlTag -eq "UnitMonitor" -and $_.Category -eq "PerformanceHealth"}  
  
$perfMonitors | select-object @{name="Target";expression={foreach-object {(Get-SCOMClass -Id:$_.Target.Id).DisplayName}}},DisplayName, @{name="Threshold";expression={foreach-object {GetThreshold $_.Configuration}}}, @{name="AlertOnState";expression={foreach-object {$_.AlertSettings.AlertOnState}}}, @{name="AutoResolveAlert";expression={foreach-object {$_.AlertSettings.AutoResolve}}}, @{name="AlertSeverity";expression={foreach-object {$_.AlertSettings.AlertSeverity}}} | sort Target, DisplayName | export-csv "c:\monitor_thresholds.csv"  
  
```