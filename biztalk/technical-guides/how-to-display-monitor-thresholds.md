---
title: モニターのしきい値を表示する方法 |Microsoft Docs
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
ms.openlocfilehash: 92db77c3e13bd479d71f845bd0854d721d2d6938
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253310"
---
# <a name="how-to-display-monitor-thresholds"></a><span data-ttu-id="b79e1-102">モニターのしきい値を表示する方法</span><span class="sxs-lookup"><span data-stu-id="b79e1-102">How to Display Monitor Thresholds</span></span>
<span data-ttu-id="b79e1-103">モニタのしきい値を表示するには、このセクションで説明するスクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="b79e1-103">To display monitor thresholds, use the script described in this section.</span></span> <span data-ttu-id="b79e1-104">このスクリプトは、ほとんどのモニタによって適しています。</span><span class="sxs-lookup"><span data-stu-id="b79e1-104">This script works for the majority of monitors.</span></span> <span data-ttu-id="b79e1-105">次の表で説明する列を含む .csv ファイルを作成し、Office Excel を使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="b79e1-105">It creates a .csv file that includes the columns described in the following table, and can be viewed using Office Excel.</span></span>  
  
|<span data-ttu-id="b79e1-106">[列]</span><span class="sxs-lookup"><span data-stu-id="b79e1-106">Column</span></span>|<span data-ttu-id="b79e1-107">説明</span><span class="sxs-lookup"><span data-stu-id="b79e1-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b79e1-108">型</span><span class="sxs-lookup"><span data-stu-id="b79e1-108">Type</span></span>|<span data-ttu-id="b79e1-109">モニターが対象となるオブジェクトの型。</span><span class="sxs-lookup"><span data-stu-id="b79e1-109">The type of objects the monitor is targeted.</span></span>|  
|<span data-ttu-id="b79e1-110">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b79e1-110">DisplayName</span></span>|<span data-ttu-id="b79e1-111">モニターの表示名。</span><span class="sxs-lookup"><span data-stu-id="b79e1-111">The display name of the monitor.</span></span>|  
|<span data-ttu-id="b79e1-112">しきい値</span><span class="sxs-lookup"><span data-stu-id="b79e1-112">Threshold</span></span>|<span data-ttu-id="b79e1-113">モニターで使用されるしきい値。</span><span class="sxs-lookup"><span data-stu-id="b79e1-113">The threshold used by the monitor.</span></span>|  
|<span data-ttu-id="b79e1-114">AlertOnState</span><span class="sxs-lookup"><span data-stu-id="b79e1-114">AlertOnState</span></span>|<span data-ttu-id="b79e1-115">状態が変更されたときに、モニターがアラートを生成するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="b79e1-115">Determines whether the monitor generates an alert when the state changes.</span></span>|  
|<span data-ttu-id="b79e1-116">AutoResolveAlert</span><span class="sxs-lookup"><span data-stu-id="b79e1-116">AutoResolveAlert</span></span>|<span data-ttu-id="b79e1-117">モニターの状態が緑色に戻ったとき生成されたアラートに自動的に解決するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="b79e1-117">Determines whether the generated alert will be automatically resolved when the monitor state goes back to green.</span></span>|  
|<span data-ttu-id="b79e1-118">AlertSeverity</span><span class="sxs-lookup"><span data-stu-id="b79e1-118">AlertSeverity</span></span>|<span data-ttu-id="b79e1-119">生成されたアラートの重大度。</span><span class="sxs-lookup"><span data-stu-id="b79e1-119">The severity of the generated alert.</span></span>|  
  
#### <a name="to-display-monitor-thresholds"></a><span data-ttu-id="b79e1-120">モニターのしきい値を表示するには</span><span class="sxs-lookup"><span data-stu-id="b79e1-120">To display monitor thresholds</span></span>  
 <span data-ttu-id="b79e1-121">モニタのしきい値を表示する .csv ファイルを作成する次のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="b79e1-121">Run the following script to create the .csv file that displays the monitor thresholds:</span></span>  
  
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