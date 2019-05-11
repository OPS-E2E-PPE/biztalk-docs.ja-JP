---
title: BAM の追跡を無効にする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, disabling BAM tracking
- BAM tracking
ms.assetid: ea5fef0e-7a96-46f5-81d8-9b1d8a5d24d2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c70760db419ac11386e0cfa83b85b89fdd0bc63f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378053"
---
# <a name="disabling-bam-tracking"></a><span data-ttu-id="3288c-102">BAM 追跡を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3288c-102">Disabling BAM Tracking</span></span>
<span data-ttu-id="3288c-103">既定では、FIN Response Reconciliation の BAM の追跡が有効にします。</span><span class="sxs-lookup"><span data-stu-id="3288c-103">By default, BAM tracking is enabled for FIN Response Reconciliation.</span></span> <span data-ttu-id="3288c-104">次のように無効することができます。</span><span class="sxs-lookup"><span data-stu-id="3288c-104">You can disable it as follows.</span></span>  
  
### <a name="to-disable-bam-tracking-for-frr"></a><span data-ttu-id="3288c-105">BAM FRR の追跡を無効にするには</span><span class="sxs-lookup"><span data-stu-id="3288c-105">To disable BAM tracking for FRR</span></span>  
  
1.  <span data-ttu-id="3288c-106">をクリックして**開始**、 をクリックして**実行**、型**regedit**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="3288c-106">Click **Start**, click **Run**, type **regedit**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="3288c-107">レジストリ エディターの左側のウィンドウでは、SWIFT/FRR のマイ コンピューター/HKEY_LOCAL_MACHINE/ソフトウェア/Microsoft/BizTalk アクセラレータに移動します。</span><span class="sxs-lookup"><span data-stu-id="3288c-107">In the left pane of the Registry Editor, move to My Computer/HKEY_LOCAL_MACHINE/SOFTWARE/Microsoft/BizTalk Accelerator for SWIFT/FRR.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3288c-108">FIN Response Reconciliation がで実行されている各コンピューターでこのレジストリ エントリを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3288c-108">This registry entry must be modified on each computer that FIN Response Reconciliation is running on.</span></span>  
  
3.  <span data-ttu-id="3288c-109">レジストリ エディターの右側のウィンドウでダブルクリック**BAMTrackingEnabled**します。</span><span class="sxs-lookup"><span data-stu-id="3288c-109">In the right pane of the Registry Editor, double-click **BAMTrackingEnabled**.</span></span>  
  
4.  <span data-ttu-id="3288c-110">**DWORD 値の編集** ダイアログ ボックスで、**値データ**ボックスに「 **0** BAM 追跡無効にします。</span><span class="sxs-lookup"><span data-stu-id="3288c-110">In the **Edit DWORD Value** dialog box, in the **Value data** box, type **0** to disable BAM tracking.</span></span>  
  
5.  <span data-ttu-id="3288c-111">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3288c-111">Click **OK**.</span></span>