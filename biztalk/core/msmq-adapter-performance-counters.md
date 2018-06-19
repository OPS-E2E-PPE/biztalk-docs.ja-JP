---
title: MSMQ アダプターのパフォーマンス カウンター |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab8b0342-c6c2-4113-ae54-359df28e5d30
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be7580ae6551fca18ee0a3b9b14b194006efd62e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971848"
---
# <a name="msmq-adapter-performance-counters"></a><span data-ttu-id="d040b-102">MSMQ アダプターのパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="d040b-102">MSMQ Adapter Performance Counters</span></span>
<span data-ttu-id="d040b-103">パフォーマンス カウンターを使用すると、サービスによってサイトまたはシステムで実行されている作業の具体的な側面を監視できます。</span><span class="sxs-lookup"><span data-stu-id="d040b-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="d040b-104">パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d040b-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="d040b-105">次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできる、 **BizTalk:MSMQ Receive Adapter**と**BizTalk:MSMQ Send Adapter**パフォーマンス オブジェクト カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="d040b-105">The following performance counters are accessible for each host instance under the **BizTalk:MSMQ Receive Adapter** and the **BizTalk:MSMQ Send Adapter** performance object categories:</span></span>  
  
|<span data-ttu-id="d040b-106">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="d040b-106">**Category**</span></span>|<span data-ttu-id="d040b-107">**カウンター**</span><span class="sxs-lookup"><span data-stu-id="d040b-107">**Counter**</span></span>|<span data-ttu-id="d040b-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="d040b-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="d040b-109">BizTalk:MSMQ Receive Adapter</span><span class="sxs-lookup"><span data-stu-id="d040b-109">BizTalk:MSMQ Receive Adapter</span></span>|<span data-ttu-id="d040b-110">Bytes received</span><span class="sxs-lookup"><span data-stu-id="d040b-110">Bytes received</span></span>|<span data-ttu-id="d040b-111">MSMQ 受信アダプターによって受信された合計バイト数。</span><span class="sxs-lookup"><span data-stu-id="d040b-111">Total number of bytes received by the MSMQ receive adapter.</span></span> <span data-ttu-id="d040b-112">このカウンターは、MSMQ 受信アダプターが送信元のキューからメッセージを完全に読み取った後で増やされます。</span><span class="sxs-lookup"><span data-stu-id="d040b-112">The counter is incremented after a message is completely read by the MSMQ receive adapter from the source queue.</span></span>|  
||<span data-ttu-id="d040b-113">Bytes received/Sec</span><span class="sxs-lookup"><span data-stu-id="d040b-113">Bytes received/Sec</span></span>|<span data-ttu-id="d040b-114">MSMQ 受信アダプターが 1 秒あたりに受信したバイト数。</span><span class="sxs-lookup"><span data-stu-id="d040b-114">Number of bytes received by the MSMQ receive adapter per second.</span></span> <span data-ttu-id="d040b-115">このカウンターの対象となるのは、MSMQ 受信アダプターが送信元のキューから完全に読み取ったメッセージだけです。</span><span class="sxs-lookup"><span data-stu-id="d040b-115">The counter applies only to messages that have been completely read by the MSMQ receive adapter from the source queue.</span></span>|  
||<span data-ttu-id="d040b-116">Messages received</span><span class="sxs-lookup"><span data-stu-id="d040b-116">Messages received</span></span>|<span data-ttu-id="d040b-117">MSMQ 受信アダプターが受信したメッセージの総数。</span><span class="sxs-lookup"><span data-stu-id="d040b-117">Total number of messages received by the MSMQ receive adapter.</span></span> <span data-ttu-id="d040b-118">このカウンターは、MSMQ 受信アダプターが送信元のキューからメッセージを完全に読み取った後で増やされます。</span><span class="sxs-lookup"><span data-stu-id="d040b-118">The counter is incremented after a message is completely read by the MSMQ receive adapter from the source queue.</span></span>|  
||<span data-ttu-id="d040b-119">Messages received/Sec</span><span class="sxs-lookup"><span data-stu-id="d040b-119">Messages received/Sec</span></span>|<span data-ttu-id="d040b-120">MSMQ 受信アダプターが 1 秒あたりに受信したメッセージ数。</span><span class="sxs-lookup"><span data-stu-id="d040b-120">Number of messages received by the MSMQ receive adapter per second.</span></span> <span data-ttu-id="d040b-121">このカウンターの対象となるのは、MSMQ 受信アダプターが送信元のキューから完全に読み取ったメッセージだけです。</span><span class="sxs-lookup"><span data-stu-id="d040b-121">The counter applies only to messages that have been completely read by the MSMQ receive adapter from the source queue.</span></span>|  
|<span data-ttu-id="d040b-122">BizTalk:MSMQ Send Adapter</span><span class="sxs-lookup"><span data-stu-id="d040b-122">BizTalk:MSMQ Send Adapter</span></span>|<span data-ttu-id="d040b-123">Bytes sent</span><span class="sxs-lookup"><span data-stu-id="d040b-123">Bytes sent</span></span>|<span data-ttu-id="d040b-124">MSMQ 送信アダプターによって送信された合計バイト数。</span><span class="sxs-lookup"><span data-stu-id="d040b-124">Total number of bytes sent by the MSMQ send adapter.</span></span> <span data-ttu-id="d040b-125">カウンターは、メッセージが送信先キューに到達した場合にのみ増やされます。</span><span class="sxs-lookup"><span data-stu-id="d040b-125">The counter is incremented only for messages that have reached the destination queue.</span></span>|  
||<span data-ttu-id="d040b-126">Bytes sent/Sec</span><span class="sxs-lookup"><span data-stu-id="d040b-126">Bytes sent/Sec</span></span>|<span data-ttu-id="d040b-127">MSMQ 送信アダプターによって送信された 1 秒あたりのバイト数。</span><span class="sxs-lookup"><span data-stu-id="d040b-127">Number of bytes sent by the MSMQ send adapter per second.</span></span> <span data-ttu-id="d040b-128">このカウンターの対象となるのは、送信先キューに到達したメッセージだけです。</span><span class="sxs-lookup"><span data-stu-id="d040b-128">The counter applies only to messages that have reached the destination queue.</span></span>|  
||<span data-ttu-id="d040b-129">Messages sent</span><span class="sxs-lookup"><span data-stu-id="d040b-129">Messages sent</span></span>|<span data-ttu-id="d040b-130">MSMQ 送信アダプターによって送信されたメッセージの総数。</span><span class="sxs-lookup"><span data-stu-id="d040b-130">Total number of messages sent by the MSMQ send adapter.</span></span> <span data-ttu-id="d040b-131">カウンターは、メッセージが送信先キューに到達した場合にのみ増やされます。</span><span class="sxs-lookup"><span data-stu-id="d040b-131">The counter is incremented only for messages that have reached the destination queue.</span></span>|  
||<span data-ttu-id="d040b-132">Messages Sent/sec</span><span class="sxs-lookup"><span data-stu-id="d040b-132">Messages sent/Sec</span></span>|<span data-ttu-id="d040b-133">MSMQ 送信アダプターによって送信された 1 秒あたりのメッセージ数。</span><span class="sxs-lookup"><span data-stu-id="d040b-133">Number of messages sent by the MSMQ send adapter per second.</span></span> <span data-ttu-id="d040b-134">このカウンターの対象となるのは、送信先キューに到達したメッセージだけです。</span><span class="sxs-lookup"><span data-stu-id="d040b-134">The counter applies only to messages that have reached the destination queue.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="d040b-135">パフォーマンス カウンターにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="d040b-135">To access performance counters</span></span>  
 <span data-ttu-id="d040b-136">パフォーマンス カウンターにアクセスするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d040b-136">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="d040b-137">Windows 2008 を使用している場合</span><span class="sxs-lookup"><span data-stu-id="d040b-137">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="d040b-138">をクリックして**開始**、 をポイント**管理ツール**、順にクリック**パフォーマンス モニター**です。</span><span class="sxs-lookup"><span data-stu-id="d040b-138">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="d040b-139">**パフォーマンス モニター** ] ダイアログ ボックスで、展開**の監視ツールを**[**パフォーマンス モニター**、順にクリック**追加**です。</span><span class="sxs-lookup"><span data-stu-id="d040b-139">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="d040b-140">**カウンターの追加** ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **biztalk:msmq**パフォーマンス カウンター オブジェクトおよび監視するカウンターの選択</span><span class="sxs-lookup"><span data-stu-id="d040b-140">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:MSMQ** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="d040b-141">**インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**です。</span><span class="sxs-lookup"><span data-stu-id="d040b-141">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="d040b-142">使用可能なカウンターのすべてのインスタンスを選択するには、次のように選択します。 \<**すべてのインスタンス**\>です。</span><span class="sxs-lookup"><span data-stu-id="d040b-142">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="d040b-143">カウンターを追加すると、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d040b-143">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="d040b-144">選択したパフォーマンス カウンターが表示されます、**パフォーマンス モニター**画面。</span><span class="sxs-lookup"><span data-stu-id="d040b-144">The selected performance counters appear on the **Performance Monitor** screen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d040b-145">参照</span><span class="sxs-lookup"><span data-stu-id="d040b-145">See Also</span></span>  
 <span data-ttu-id="d040b-146">[MSMQ での LoadGen 2007 の使用](../core/using-loadgen-2007-with-msmq.md) </span><span class="sxs-lookup"><span data-stu-id="d040b-146">[Using LoadGen 2007 with MSMQ](../core/using-loadgen-2007-with-msmq.md) </span></span>  
 [<span data-ttu-id="d040b-147">MSMQ アダプターのパフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="d040b-147">Optimizing Performance of the MSMQ Adapter</span></span>](../core/optimizing-performance-of-the-msmq-adapter.md)