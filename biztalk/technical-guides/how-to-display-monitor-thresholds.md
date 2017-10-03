---
title: "モニタのしきい値を表示する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88d88b15-0691-49d9-b116-1a2ae95bead9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be3818512f76e95655e0441f039176fe6f855344
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-display-monitor-thresholds"></a>モニタのしきい値を表示する方法
モニタのしきい値を表示するには、このセクションで説明されているスクリプトを使用します。 このスクリプトは、ほとんどのモニタに対して機能します。 次の表で説明する列を含む .csv ファイルを作成し、Office Excel を使用して表示できます。  
  
|列|Description|  
|------------|-----------------|  
|型|モニターが対象となるオブジェクトの型。|  
|DisplayName|モニターの表示名。|  
|しきい値|モニターによって使用されるしきい値。|  
|AlertOnState|状態が変更されたときに、モニターがアラートを生成するかどうかを判断します。|  
|AutoResolveAlert|かどうか、生成されたアラートを自動的に解決するモニターの状態が緑色に戻ったときに決定します。|  
|AlertSeverity|生成されたアラートの重大度。|  
  
#### <a name="to-display-monitor-thresholds"></a>モニターのしきい値を表示するには  
 モニタのしきい値を表示する .csv ファイルを作成する次のスクリプトを実行します。  
  
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