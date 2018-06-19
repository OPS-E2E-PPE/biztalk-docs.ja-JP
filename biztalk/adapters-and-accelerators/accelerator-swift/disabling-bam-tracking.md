---
title: BAM の追跡を無効化 |Microsoft ドキュメント
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
ms.openlocfilehash: e4e734bd31147ecacc8bbbe98d98297edfb4f0de
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209050"
---
# <a name="disabling-bam-tracking"></a><span data-ttu-id="509dc-102">BAM 追跡を無効にします。</span><span class="sxs-lookup"><span data-stu-id="509dc-102">Disabling BAM Tracking</span></span>
<span data-ttu-id="509dc-103">既定では、FIN 対応調整の BAM の追跡が有効にします。</span><span class="sxs-lookup"><span data-stu-id="509dc-103">By default, BAM tracking is enabled for FIN Response Reconciliation.</span></span> <span data-ttu-id="509dc-104">無効にできますとおりです。</span><span class="sxs-lookup"><span data-stu-id="509dc-104">You can disable it as follows.</span></span>  
  
### <a name="to-disable-bam-tracking-for-frr"></a><span data-ttu-id="509dc-105">BAM FRR の追跡を無効にするには</span><span class="sxs-lookup"><span data-stu-id="509dc-105">To disable BAM tracking for FRR</span></span>  
  
1.  <span data-ttu-id="509dc-106">をクリックして**開始**、 をクリックして**実行**、型**regedit**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="509dc-106">Click **Start**, click **Run**, type **regedit**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="509dc-107">レジストリ エディターの左側のウィンドウでは、SWIFT/FRR のマイ コンピューター/HKEY_LOCAL_MACHINE/ソフトウェア/Microsoft/BizTalk Accelerator に移動します。</span><span class="sxs-lookup"><span data-stu-id="509dc-107">In the left pane of the Registry Editor, move to My Computer/HKEY_LOCAL_MACHINE/SOFTWARE/Microsoft/BizTalk Accelerator for SWIFT/FRR.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="509dc-108">FIN 対応調整がで実行されている各コンピューターでは、このレジストリ エントリを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="509dc-108">This registry entry must be modified on each computer that FIN Response Reconciliation is running on.</span></span>  
  
3.  <span data-ttu-id="509dc-109">レジストリ エディターの右側のウィンドウでダブルクリック**BAMTrackingEnabled**です。</span><span class="sxs-lookup"><span data-stu-id="509dc-109">In the right pane of the Registry Editor, double-click **BAMTrackingEnabled**.</span></span>  
  
4.  <span data-ttu-id="509dc-110">**DWORD 値の編集** ダイアログ ボックスで、**値のデータ**ボックスに、入力**0** BAM の追跡を無効にします。</span><span class="sxs-lookup"><span data-stu-id="509dc-110">In the **Edit DWORD Value** dialog box, in the **Value data** box, type **0** to disable BAM tracking.</span></span>  
  
5.  <span data-ttu-id="509dc-111">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="509dc-111">Click **OK**.</span></span>