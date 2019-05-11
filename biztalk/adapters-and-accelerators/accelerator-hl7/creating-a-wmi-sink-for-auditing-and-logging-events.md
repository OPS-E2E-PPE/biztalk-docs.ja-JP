---
title: 監査およびイベントをログ出力シンク、WMI の作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WMI sink
- auditing, WMI sink
- WMI sink, auditing
- logging, WMI sink
- WMI sink, logging
ms.assetid: 5feb1e98-32ed-4505-878e-274028d50c3c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 375a16a338c991f80e6a1ffb079ea15fedc0389c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255679"
---
# <a name="creating-a-wmi-sink-for-auditing-and-logging-events"></a><span data-ttu-id="74080-102">監査とイベントをログ記録用の WMI シンクの作成</span><span class="sxs-lookup"><span data-stu-id="74080-102">Creating a WMI Sink for Auditing and Logging Events</span></span>
<span data-ttu-id="74080-103">次のサンプル コードを使用して作成することができます、 [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Management Instrumentation (WMI) のシンクを監査およびログ イベントを監視します。</span><span class="sxs-lookup"><span data-stu-id="74080-103">You can use the following sample code to create a [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Management Instrumentation (WMI) sink to monitor auditing and logging events:</span></span>  
  
 `//Create the WMI query and Event watcher and subscribe to events`  
  
 `ManagementEventWatcher watcher = new ManagementEventWatcher ("root/Default", "select * from  PackageEvent");`  
  
 `ManagementBaseObject evtObj = watcher.WaitForNextEvent();`  
  
 `//Do what you want with the event`  
  
## <a name="see-also"></a><span data-ttu-id="74080-104">参照</span><span class="sxs-lookup"><span data-stu-id="74080-104">See Also</span></span>  
 [<span data-ttu-id="74080-105">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="74080-105">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)