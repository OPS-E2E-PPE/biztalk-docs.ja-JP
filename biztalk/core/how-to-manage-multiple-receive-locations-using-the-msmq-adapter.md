---
title: "複数の受信、MSMQ アダプタを使用して場所を管理する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, receive locations
- MSMQ adapters, threads
- receive locations, multiple
- threads
- receive locations, MSMQ adapters
- receive locations, threads
- configuring [MSMQ adapters], receive locations
ms.assetid: 5b2ee043-bcc9-443b-84b0-df7f487159eb
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72438551d2ecab09b918808d43e7d7de6d600677
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-manage-multiple-receive-locations-using-the-msmq-adapter"></a><span data-ttu-id="e53c5-102">MSMQ アダプタを使用して複数の受信場所を管理する方法</span><span class="sxs-lookup"><span data-stu-id="e53c5-102">How to Manage Multiple Receive Locations Using the MSMQ Adapter</span></span>
<span data-ttu-id="e53c5-103">MSMQ アダプタは、パフォーマンスを強化するためにマルチスレッド化されています。</span><span class="sxs-lookup"><span data-stu-id="e53c5-103">To increase performance, the MSMQ adapter is multithreaded.</span></span> <span data-ttu-id="e53c5-104">多くの受信場所があり、すべての受信場所に十分な数のスレッドを確保できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e53c5-104">If you have many receive locations, there may not be enough threads available for all the receive locations.</span></span> <span data-ttu-id="e53c5-105">この場合、一部の受信場所でメッセージを取得できなくなります。</span><span class="sxs-lookup"><span data-stu-id="e53c5-105">This prevents some of the receive locations from picking up messages.</span></span> <span data-ttu-id="e53c5-106">この問題を解決するための 3 つの方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e53c5-106">There are three ways to solve this problem:</span></span>  
  
-   <span data-ttu-id="e53c5-107">コンピュータに BizTalk ホストを追加し、ホスト間で受信場所を分担します。</span><span class="sxs-lookup"><span data-stu-id="e53c5-107">Add BizTalk Hosts to your computer and divide the receive locations among the hosts.</span></span> <span data-ttu-id="e53c5-108">ホストを追加すると、より多くのスレッドを受信場所に確保できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e53c5-108">Adding hosts makes more threads available for the receive locations.</span></span>  
  
-   <span data-ttu-id="e53c5-109">設定、**シリアル処理**プロパティを`True`受信場所ごとにします。</span><span class="sxs-lookup"><span data-stu-id="e53c5-109">Set the **Serial Processing** property to `True` on each receive location.</span></span> <span data-ttu-id="e53c5-110">このプロパティを `True` に設定すると、各受信場所に 1 つずつスレッドが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e53c5-110">Setting the property to `True` assigns a single thread to each receive location.</span></span> <span data-ttu-id="e53c5-111">これにより、プール内の使用可能なスレッドが増加します。</span><span class="sxs-lookup"><span data-stu-id="e53c5-111">This leaves more threads available in the pool.</span></span> <span data-ttu-id="e53c5-112">ただし、この方法ではパフォーマンスが低下する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="e53c5-112">However, this may also cause a decrease in performance.</span></span>  
  
-   <span data-ttu-id="e53c5-113">MSMQ アダプターの受信ハンドラーのホストに利用できるスレッドの数を増やすにレジストリを変更します。</span><span class="sxs-lookup"><span data-stu-id="e53c5-113">Modify the registry to increase the number of threads that are available to the host for the MSMQ adapter receive handler.</span></span> <span data-ttu-id="e53c5-114">詳細については、次を参照してください。、**ホスト用 CLR Hosting スレッド値を変更**のセクション[構成パラメーターに影響を与えるアダプター パフォーマンス](../core/configuration-parameters-that-affect-adapter-performance.md)です。</span><span class="sxs-lookup"><span data-stu-id="e53c5-114">For more information see the **Modify the CLR Hosting thread values for the host** section of [Configuration Parameters that Affect Adapter Performance](../core/configuration-parameters-that-affect-adapter-performance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e53c5-115">参照</span><span class="sxs-lookup"><span data-stu-id="e53c5-115">See Also</span></span>  
 [<span data-ttu-id="e53c5-116">MSMQ アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="e53c5-116">Configuring the MSMQ Adapter</span></span>](../core/configuring-the-msmq-adapter.md)