---
title: 低待機時間シナリオ Optimizations2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19cd78ce-ad7d-4e4b-8188-a63d707905d5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9e5c8c5e225239461c9509aa50c105e4181ba12
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978627"
---
# <a name="low-latency-scenario-optimizations"></a><span data-ttu-id="87e8d-102">低待機時間シナリオの最適化</span><span class="sxs-lookup"><span data-stu-id="87e8d-102">Low-Latency Scenario Optimizations</span></span>
<span data-ttu-id="87e8d-103">既定では、BizTalk Server は、低待機時間よりもスループットに最適化されています。</span><span class="sxs-lookup"><span data-stu-id="87e8d-103">By default, BizTalk Server is optimized for throughput rather than low-latency.</span></span> <span data-ttu-id="87e8d-104">次の最適化は、待機時間の短縮が必要な場合のシナリオで、BizTalk Server に適用できます。</span><span class="sxs-lookup"><span data-stu-id="87e8d-104">The following optimizations can be applied to BizTalk Server in scenarios where reduced latency is required.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="87e8d-105">これらの最適化は、待機時間が改善されますが、全体的なスループットをいくつかのコストで行うことがあります。</span><span class="sxs-lookup"><span data-stu-id="87e8d-105">These optimizations will improve latency, but may do so at some cost to overall throughput.</span></span>  
  
## <a name="increase-the-biztalk-server-host-internal-message-queue-size"></a><span data-ttu-id="87e8d-106">BizTalk Server ホストの内部メッセージ キューのサイズを増やす</span><span class="sxs-lookup"><span data-stu-id="87e8d-106">Increase the BizTalk Server host internal message queue size</span></span>  
 <span data-ttu-id="87e8d-107">各 BizTalk ホストには、内部のメモリ内キューがあります。</span><span class="sxs-lookup"><span data-stu-id="87e8d-107">Each BizTalk host has its own internal in-memory queue.</span></span> <span data-ttu-id="87e8d-108">低待機時間シナリオのパフォーマンスを向上させるためには、100 ~ 10,000 の既定値からこのキューのサイズを大ききます。</span><span class="sxs-lookup"><span data-stu-id="87e8d-108">Increase the size of this queue from the default value of 100 to 10000 to improve performance for a low-latency scenario.</span></span> <span data-ttu-id="87e8d-109">内部メッセージ キューのサイズの値を変更する方法の詳細については、[リソース ベースのスロットル設定の変更方法](http://go.microsoft.com/fwlink/?LinkID=208366)(http://go.microsoft.com/fwlink/?LinkID=208366) 、BizTalk Server のドキュメントにを参照してください。</span><span class="sxs-lookup"><span data-stu-id="87e8d-109">For more information about modifying the value of the internal message queue size, see [How to Modify Resource Based Throttling Settings](http://go.microsoft.com/fwlink/?LinkID=208366) (http://go.microsoft.com/fwlink/?LinkID=208366) in the BizTalk Server documentation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="87e8d-110">内部メッセージ キュー サイズの値を増やすと、ホスト インスタンスによって使用されるメモリが増加します。</span><span class="sxs-lookup"><span data-stu-id="87e8d-110">Increasing the internal message queue size value will increase the memory used by the host instance.</span></span>  
  
## <a name="increase-the-biztalk-server-host-in-process-messages"></a><span data-ttu-id="87e8d-111">BizTalk Server ホストのインプロセス メッセージを向上します。</span><span class="sxs-lookup"><span data-stu-id="87e8d-111">Increase the BizTalk Server host in-process messages</span></span>  
 <span data-ttu-id="87e8d-112">パフォーマンスを向上させるために 1000 ~ 10,000 個の既定値からのプロセスでメッセージを増やします。</span><span class="sxs-lookup"><span data-stu-id="87e8d-112">Increase the in-process messages from the default value of 1000 to 10,000 to improve performance.</span></span> <span data-ttu-id="87e8d-113">インプロセス メッセージの値を変更する方法の詳細については、[ホスト制限の既定の設定を変更する方法](http://go.microsoft.com/fwlink/?LinkID=208366)(http://go.microsoft.com/fwlink/?LinkID=208366) 、BizTalk Server のドキュメントにを参照してください。</span><span class="sxs-lookup"><span data-stu-id="87e8d-113">For more information about modifying the value of the in-process messages, see [How to Modify the Default Host Throttling Settings](http://go.microsoft.com/fwlink/?LinkID=208366) (http://go.microsoft.com/fwlink/?LinkID=208366) in the BizTalk Server documentation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="87e8d-114">内部メッセージ キュー サイズの値を増やすと、ホスト インスタンスによって使用されるメモリが増加します。</span><span class="sxs-lookup"><span data-stu-id="87e8d-114">Increasing the internal message queue size value will increase the memory used by the host instance.</span></span>  
  
## <a name="optimize-orchestrations-for-low-latency"></a><span data-ttu-id="87e8d-115">低待機時間のオーケストレーションを最適化します。</span><span class="sxs-lookup"><span data-stu-id="87e8d-115">Optimize orchestrations for low latency</span></span>  
 <span data-ttu-id="87e8d-116">「低待機時間シナリオ オーケストレーションを最適化するための推奨事項」セクションで推奨事項に従って[オーケストレーション パフォーマンスの最適化](../technical-guides/optimizing-orchestration-performance.md)します。</span><span class="sxs-lookup"><span data-stu-id="87e8d-116">Follow the recommendations in the “Recommendations for optimizing orchestrations for low latency scenarios” section of [Optimizing Orchestration Performance](../technical-guides/optimizing-orchestration-performance.md).</span></span>  
  
## <a name="configure-polling-intervals"></a><span data-ttu-id="87e8d-117">ポーリング間隔を構成します。</span><span class="sxs-lookup"><span data-stu-id="87e8d-117">Configure polling intervals</span></span>  
 <span data-ttu-id="87e8d-118">設定ダッシュ ボードを使用すると、BizTalk グループ全体で特定のホストのポーリング間隔を構成できます。</span><span class="sxs-lookup"><span data-stu-id="87e8d-118">Use the Settings Dashboard to configure the polling intervals of a given host, across the BizTalk Group.</span></span> <span data-ttu-id="87e8d-119">ポーリング間隔を変更するには。</span><span class="sxs-lookup"><span data-stu-id="87e8d-119">To change Polling Intervals:</span></span>  
  
1. <span data-ttu-id="87e8d-120">**BizTalk Server 管理コンソール**、展開**BizTalk Server 管理**を右クリックして**BizTalk グループ**、 をクリックし、**設定**.</span><span class="sxs-lookup"><span data-stu-id="87e8d-120">In the **BizTalk Server Administration Console**, expand **BizTalk Server Administration**, right-click **BizTalk Group**, and then click **Settings**.</span></span>  
  
2. <span data-ttu-id="87e8d-121">**BizTalk 設定ダッシュ ボード** ダイアログ ボックスで、**ホスト** ページの 、**全般** タブの **ポーリング間隔**が表示されます**メッセージング**と**オーケストレーション**値。</span><span class="sxs-lookup"><span data-stu-id="87e8d-121">In the **BizTalk Settings Dashboard** dialog box, on the **Hosts** page, on the **General** tab, under **Polling Intervals**, you will find the **Messaging** and **Orchestration** values.</span></span> <span data-ttu-id="87e8d-122">既定では、2 つの値が 500 ミリ秒に設定されます。</span><span class="sxs-lookup"><span data-stu-id="87e8d-122">By default, both these values are set to 500 milliseconds.</span></span>  
  
   <span data-ttu-id="87e8d-123">次の表では、BizTalk プロセス内の 64 ビット ホスト (RxHost、TxHost および PxHost) でのテストに使用したポーリング値を示します。</span><span class="sxs-lookup"><span data-stu-id="87e8d-123">The following table lists the polling values that we used for testing on the BizTalk in-process 64-bit Hosts (RxHost, TxHost and PxHost).</span></span> <span data-ttu-id="87e8d-124">ポーリングを無効にするには、テーブルに一覧されている非常に大きな数値にポーリング間隔を設定できます。</span><span class="sxs-lookup"><span data-stu-id="87e8d-124">To disable polling, you can set the polling interval to a very big number as listed in the table.</span></span>  
  
|<span data-ttu-id="87e8d-125">サーバーのホスト</span><span class="sxs-lookup"><span data-stu-id="87e8d-125">Server Hosts</span></span>|<span data-ttu-id="87e8d-126">メッセージング</span><span class="sxs-lookup"><span data-stu-id="87e8d-126">Messaging</span></span>|<span data-ttu-id="87e8d-127">オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="87e8d-127">Orchestration</span></span>|  
|------------------|---------------|-------------------|  
|<span data-ttu-id="87e8d-128">**RxHost**</span><span class="sxs-lookup"><span data-stu-id="87e8d-128">**RxHost**</span></span><br /><br /> <span data-ttu-id="87e8d-129">のみが公開されますので、一方向で、BizTalk メッセージ ボックスへの着信メッセージの受信場所、RxHost でポーリングは必要ありません (ホストの受信)。</span><span class="sxs-lookup"><span data-stu-id="87e8d-129">Because we are only publishing incoming messages to the BizTalk message box through a one-way receive location, polling is not required on the RxHost (receive host).</span></span>|<span data-ttu-id="87e8d-130">200000</span><span class="sxs-lookup"><span data-stu-id="87e8d-130">200000</span></span>|<span data-ttu-id="87e8d-131">200000</span><span class="sxs-lookup"><span data-stu-id="87e8d-131">200000</span></span>|  
|<span data-ttu-id="87e8d-132">**TxHost**</span><span class="sxs-lookup"><span data-stu-id="87e8d-132">**TxHost**</span></span><br /><br /> <span data-ttu-id="87e8d-133">BizTalk メッセージ ボックスからメッセージング インスタンスを受信しましたがのみ、ために、TxHost (送信ホスト) でポーリングのオーケストレーションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="87e8d-133">Because we are only receiving messaging instances from the BizTalk message box, orchestration polling is not required on the TxHost (send host).</span></span>|<span data-ttu-id="87e8d-134">50</span><span class="sxs-lookup"><span data-stu-id="87e8d-134">50</span></span>|<span data-ttu-id="87e8d-135">200000</span><span class="sxs-lookup"><span data-stu-id="87e8d-135">200000</span></span>|  
|<span data-ttu-id="87e8d-136">**PxHost**</span><span class="sxs-lookup"><span data-stu-id="87e8d-136">**PxHost**</span></span><br /><br /> <span data-ttu-id="87e8d-137">BizTalk メッセージ ボックスからオーケストレーション インスタンスを受信しましたがのみ、ためポーリングのメッセージングは、(処理ホスト) PxHost で必要ありません。</span><span class="sxs-lookup"><span data-stu-id="87e8d-137">Because we are only receiving orchestration instances from the BizTalk message box, messaging polling is not required on the PxHost (Processing host).</span></span>|<span data-ttu-id="87e8d-138">200000</span><span class="sxs-lookup"><span data-stu-id="87e8d-138">200000</span></span>|<span data-ttu-id="87e8d-139">50</span><span class="sxs-lookup"><span data-stu-id="87e8d-139">50</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87e8d-140">参照</span><span class="sxs-lookup"><span data-stu-id="87e8d-140">See Also</span></span>  
 [<span data-ttu-id="87e8d-141">BizTalk Server パフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="87e8d-141">Optimizing BizTalk Server Performance</span></span>](../technical-guides/optimizing-biztalk-server-performance.md)