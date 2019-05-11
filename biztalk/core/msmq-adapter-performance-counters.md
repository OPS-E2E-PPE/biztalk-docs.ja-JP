---
title: MSMQ アダプターのパフォーマンス カウンター |Microsoft Docs
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
ms.openlocfilehash: 11214cd0698ac2d158523524f3e9cfdc59946cf5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263663"
---
# <a name="msmq-adapter-performance-counters"></a><span data-ttu-id="6ed38-102">MSMQ アダプターのパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="6ed38-102">MSMQ Adapter Performance Counters</span></span>
<span data-ttu-id="6ed38-103">パフォーマンス カウンターを使用して、サービスによってサイトまたはシステムで実行される作業の具体的な側面を監視できます。</span><span class="sxs-lookup"><span data-stu-id="6ed38-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="6ed38-104">パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6ed38-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="6ed38-105">次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできますが、 **BizTalk:MSMQ Receive Adapter**と**BizTalk:MSMQ Send Adapter**パフォーマンス オブジェクト カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="6ed38-105">The following performance counters are accessible for each host instance under the **BizTalk:MSMQ Receive Adapter** and the **BizTalk:MSMQ Send Adapter** performance object categories:</span></span>  
  
|<span data-ttu-id="6ed38-106">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="6ed38-106">**Category**</span></span>|<span data-ttu-id="6ed38-107">**カウンター**</span><span class="sxs-lookup"><span data-stu-id="6ed38-107">**Counter**</span></span>|<span data-ttu-id="6ed38-108">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="6ed38-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="6ed38-109">BizTalk:MSMQ 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="6ed38-109">BizTalk:MSMQ Receive Adapter</span></span>|<span data-ttu-id="6ed38-110">受信したバイト数</span><span class="sxs-lookup"><span data-stu-id="6ed38-110">Bytes received</span></span>|<span data-ttu-id="6ed38-111">受信アダプター、MSMQ で受信したバイトの合計数。</span><span class="sxs-lookup"><span data-stu-id="6ed38-111">Total number of bytes received by the MSMQ receive adapter.</span></span> <span data-ttu-id="6ed38-112">メッセージは MSMQ によって完全に読み取った後、カウンターがインクリメント元キューから受信アダプター。</span><span class="sxs-lookup"><span data-stu-id="6ed38-112">The counter is incremented after a message is completely read by the MSMQ receive adapter from the source queue.</span></span>|  
||<span data-ttu-id="6ed38-113">受信バイト数/秒</span><span class="sxs-lookup"><span data-stu-id="6ed38-113">Bytes received/Sec</span></span>|<span data-ttu-id="6ed38-114">1 秒あたりにアダプターを受信する、MSMQ で受信したバイト数。</span><span class="sxs-lookup"><span data-stu-id="6ed38-114">Number of bytes received by the MSMQ receive adapter per second.</span></span> <span data-ttu-id="6ed38-115">このカウンターの対象にのみ、MSMQ によって完全に読み取られたメッセージは受信元キューからアダプター。</span><span class="sxs-lookup"><span data-stu-id="6ed38-115">The counter applies only to messages that have been completely read by the MSMQ receive adapter from the source queue.</span></span>|  
||<span data-ttu-id="6ed38-116">受信したメッセージ</span><span class="sxs-lookup"><span data-stu-id="6ed38-116">Messages received</span></span>|<span data-ttu-id="6ed38-117">受信アダプター、MSMQ の受信メッセージの合計数。</span><span class="sxs-lookup"><span data-stu-id="6ed38-117">Total number of messages received by the MSMQ receive adapter.</span></span> <span data-ttu-id="6ed38-118">メッセージは MSMQ によって完全に読み取った後、カウンターがインクリメント元キューから受信アダプター。</span><span class="sxs-lookup"><span data-stu-id="6ed38-118">The counter is incremented after a message is completely read by the MSMQ receive adapter from the source queue.</span></span>|  
||<span data-ttu-id="6ed38-119">メッセージの受信/秒</span><span class="sxs-lookup"><span data-stu-id="6ed38-119">Messages received/Sec</span></span>|<span data-ttu-id="6ed38-120">1 秒あたりにアダプターを受信する MSMQ の受信メッセージの数。</span><span class="sxs-lookup"><span data-stu-id="6ed38-120">Number of messages received by the MSMQ receive adapter per second.</span></span> <span data-ttu-id="6ed38-121">このカウンターの対象にのみ、MSMQ によって完全に読み取られたメッセージは受信元キューからアダプター。</span><span class="sxs-lookup"><span data-stu-id="6ed38-121">The counter applies only to messages that have been completely read by the MSMQ receive adapter from the source queue.</span></span>|  
|<span data-ttu-id="6ed38-122">BizTalk:MSMQ 送信アダプター</span><span class="sxs-lookup"><span data-stu-id="6ed38-122">BizTalk:MSMQ Send Adapter</span></span>|<span data-ttu-id="6ed38-123">送信バイト数</span><span class="sxs-lookup"><span data-stu-id="6ed38-123">Bytes sent</span></span>|<span data-ttu-id="6ed38-124">送信アダプター、MSMQ から送信されたバイトの合計数。</span><span class="sxs-lookup"><span data-stu-id="6ed38-124">Total number of bytes sent by the MSMQ send adapter.</span></span> <span data-ttu-id="6ed38-125">カウンターは、メッセージが送信先キューに到達した場合にのみ増やされます。</span><span class="sxs-lookup"><span data-stu-id="6ed38-125">The counter is incremented only for messages that have reached the destination queue.</span></span>|  
||<span data-ttu-id="6ed38-126">送信バイト数/秒</span><span class="sxs-lookup"><span data-stu-id="6ed38-126">Bytes sent/Sec</span></span>|<span data-ttu-id="6ed38-127">1 秒あたりにアダプターに送信して、MSMQ から送信されたバイトの数。</span><span class="sxs-lookup"><span data-stu-id="6ed38-127">Number of bytes sent by the MSMQ send adapter per second.</span></span> <span data-ttu-id="6ed38-128">カウンターは、送信先キューに到達したメッセージのみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6ed38-128">The counter applies only to messages that have reached the destination queue.</span></span>|  
||<span data-ttu-id="6ed38-129">送信されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="6ed38-129">Messages sent</span></span>|<span data-ttu-id="6ed38-130">送信アダプター、MSMQ によって送信されたメッセージの合計数。</span><span class="sxs-lookup"><span data-stu-id="6ed38-130">Total number of messages sent by the MSMQ send adapter.</span></span> <span data-ttu-id="6ed38-131">カウンターは、メッセージが送信先キューに到達した場合にのみ増やされます。</span><span class="sxs-lookup"><span data-stu-id="6ed38-131">The counter is incremented only for messages that have reached the destination queue.</span></span>|  
||<span data-ttu-id="6ed38-132">メッセージの送信/秒</span><span class="sxs-lookup"><span data-stu-id="6ed38-132">Messages sent/Sec</span></span>|<span data-ttu-id="6ed38-133">1 秒あたりにアダプターに送信して、MSMQ によって送信されたメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="6ed38-133">Number of messages sent by the MSMQ send adapter per second.</span></span> <span data-ttu-id="6ed38-134">カウンターは、送信先キューに到達したメッセージのみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6ed38-134">The counter applies only to messages that have reached the destination queue.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="6ed38-135">パフォーマンス カウンターにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="6ed38-135">To access performance counters</span></span>  
 <span data-ttu-id="6ed38-136">パフォーマンス カウンターにアクセスするのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ed38-136">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="6ed38-137">Windows 2008 を使用している場合</span><span class="sxs-lookup"><span data-stu-id="6ed38-137">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="6ed38-138">クリックして**開始**、 をポイント**管理ツール**、順にクリックします**パフォーマンス モニター**します。</span><span class="sxs-lookup"><span data-stu-id="6ed38-138">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="6ed38-139">**パフォーマンス モニター**  ダイアログ ボックスで、展開**監視ツール**を選択します**パフォーマンス モニター**、 をクリックし、**追加**。</span><span class="sxs-lookup"><span data-stu-id="6ed38-139">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="6ed38-140">**カウンターの追加**] ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **[BizTalk:MSMQ**パフォーマンス カウンター オブジェクトと監視するカウンターを選択します。</span><span class="sxs-lookup"><span data-stu-id="6ed38-140">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:MSMQ** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="6ed38-141">**インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**します。</span><span class="sxs-lookup"><span data-stu-id="6ed38-141">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="6ed38-142">使用可能なカウンターのインスタンスすべてを選択する\<**すべてのインスタンス**\>します。</span><span class="sxs-lookup"><span data-stu-id="6ed38-142">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="6ed38-143">カウンターを追加すると、次のようにクリックします。 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="6ed38-143">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="6ed38-144">選択したパフォーマンス カウンターが表示される、**パフォーマンス モニター**画面。</span><span class="sxs-lookup"><span data-stu-id="6ed38-144">The selected performance counters appear on the **Performance Monitor** screen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ed38-145">参照</span><span class="sxs-lookup"><span data-stu-id="6ed38-145">See Also</span></span>  
 <span data-ttu-id="6ed38-146">[MSMQ での LoadGen 2007 の使用](../core/using-loadgen-2007-with-msmq.md) </span><span class="sxs-lookup"><span data-stu-id="6ed38-146">[Using LoadGen 2007 with MSMQ](../core/using-loadgen-2007-with-msmq.md) </span></span>  
 [<span data-ttu-id="6ed38-147">MSMQ アダプターのパフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="6ed38-147">Optimizing Performance of the MSMQ Adapter</span></span>](../core/optimizing-performance-of-the-msmq-adapter.md)