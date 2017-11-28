---
title: "設定する方法の TIBCO Rendezvous の受信パイプライン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive pipelines, setting
- setting receive pipelines
- pipelines, setting
ms.assetid: d40e0225-0313-4e9b-8d92-464870aabf71
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dd29852ab41af0d5b1f4ed0d184c158a23b5ae7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-receive-pipelines-for-tibco-rendezvous"></a><span data-ttu-id="1408c-102">TIBCO Rendezvous 用の受信パイプラインを設定する方法</span><span class="sxs-lookup"><span data-stu-id="1408c-102">How to Set Receive Pipelines for TIBCO Rendezvous</span></span>
<span data-ttu-id="1408c-103">Microsoft BizTalk Adapter for TIBCO Rendezvous では、受信ハンドラーと受信パイプラインを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1408c-103">Microsoft BizTalk Adapter for TIBCO Rendezvous requires that you set the receive handler and receive pipeline.</span></span>  
  
### <a name="to-set-the-pipeline"></a><span data-ttu-id="1408c-104">パイプラインを設定するには</span><span class="sxs-lookup"><span data-stu-id="1408c-104">To set the pipeline</span></span>  
  
1.  <span data-ttu-id="1408c-105">設定、**受信ハンドラー**に**BizTalkServerIsolatedHost**一覧にします。</span><span class="sxs-lookup"><span data-stu-id="1408c-105">Set the **Receive Handler** to **BizTalkServerIsolatedHost** in the list.</span></span>  
  
2.  <span data-ttu-id="1408c-106">設定、**受信パイプライン**に**XMLReceive**または同等のパイプライン。</span><span class="sxs-lookup"><span data-stu-id="1408c-106">Set the **Receive Pipeline** to **XMLReceive** or any equivalent pipeline.</span></span>  
  
3.  <span data-ttu-id="1408c-107">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1408c-107">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1408c-108">参照</span><span class="sxs-lookup"><span data-stu-id="1408c-108">See Also</span></span>  
 [<span data-ttu-id="1408c-109">作成元の TIBCO Rendezvous 受信ハンドラー</span><span class="sxs-lookup"><span data-stu-id="1408c-109">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)