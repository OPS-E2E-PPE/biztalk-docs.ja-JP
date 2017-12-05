---
title: "ファイル アダプターのパフォーマンス カウンター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 343465b4-6b20-4a24-b4b1-138548c572cc
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d48cf2cf203ed001611bb30e3c9f1d5746a903e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="file-adapter-performance-counters"></a><span data-ttu-id="ebf21-102">ファイル アダプターのパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="ebf21-102">File Adapter Performance Counters</span></span>
<span data-ttu-id="ebf21-103">パフォーマンス カウンターを使用すると、サービスによってサイトまたはシステムで実行されている作業の具体的な側面を監視できます。</span><span class="sxs-lookup"><span data-stu-id="ebf21-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="ebf21-104">パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ebf21-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="ebf21-105">次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできる、 **biztalk: ファイル受信アダプター**と**biztalk: ファイル送信アダプター**パフォーマンス オブジェクト カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="ebf21-105">The following performance counters are accessible for each host instance under the **BizTalk:FILE Receive Adapter** and the **BizTalk:FILE Send Adapter** performance object categories:</span></span>  
  
|<span data-ttu-id="ebf21-106">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="ebf21-106">**Category**</span></span>|<span data-ttu-id="ebf21-107">**カウンター**</span><span class="sxs-lookup"><span data-stu-id="ebf21-107">**Counter**</span></span>|<span data-ttu-id="ebf21-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="ebf21-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="ebf21-109">BizTalk:ファイル受信アダプター</span><span class="sxs-lookup"><span data-stu-id="ebf21-109">BizTalk:FILE Receive Adapter</span></span>|<span data-ttu-id="ebf21-110">Bytes received</span><span class="sxs-lookup"><span data-stu-id="ebf21-110">Bytes received</span></span>|<span data-ttu-id="ebf21-111">ファイル受信アダプターによって受信された合計バイト数。</span><span class="sxs-lookup"><span data-stu-id="ebf21-111">Total number of bytes received by the file receive adapter.</span></span> <span data-ttu-id="ebf21-112">このカウンターは、アダプターがファイル システムからメッセージを完全に読み取った後で増やされます。</span><span class="sxs-lookup"><span data-stu-id="ebf21-112">The counter is incremented after a message is completely read by the adapter from the file system.</span></span>|  
||<span data-ttu-id="ebf21-113">Byte received/Sec</span><span class="sxs-lookup"><span data-stu-id="ebf21-113">Byte received/Sec</span></span>|<span data-ttu-id="ebf21-114">ファイル受信アダプターが 1 秒あたりに受信したバイト数。</span><span class="sxs-lookup"><span data-stu-id="ebf21-114">Number of bytes received by the file receive adapter per second.</span></span> <span data-ttu-id="ebf21-115">このカウンターの対象となるのは、ファイル アダプターがファイル システムから完全に読み取ったメッセージだけです。</span><span class="sxs-lookup"><span data-stu-id="ebf21-115">The counter applies only to messages that have been completely read by the file adapter from the file system.</span></span>|  
||<span data-ttu-id="ebf21-116">Delete retries</span><span class="sxs-lookup"><span data-stu-id="ebf21-116">Delete retries</span></span>|<span data-ttu-id="ebf21-117">ファイル受信アダプターが、読み取ったファイルの削除を試みた回数。</span><span class="sxs-lookup"><span data-stu-id="ebf21-117">Number of times the file receive adapter attempts to delete a file that has been read.</span></span>|  
||<span data-ttu-id="ebf21-118">Lock failures</span><span class="sxs-lookup"><span data-stu-id="ebf21-118">Lock failures</span></span>|<span data-ttu-id="ebf21-119">ファイル受信アダプターがファイルのロックに失敗した回数。</span><span class="sxs-lookup"><span data-stu-id="ebf21-119">Number of times the file receive adapter failed to lock the file.</span></span>|  
||<span data-ttu-id="ebf21-120">Lock failures/sec</span><span class="sxs-lookup"><span data-stu-id="ebf21-120">Lock failures/sec</span></span>|<span data-ttu-id="ebf21-121">ファイル受信アダプターがファイルのロックに失敗した 1 秒あたりの回数。</span><span class="sxs-lookup"><span data-stu-id="ebf21-121">Number of times the file receive adapter failed to lock the file per second.</span></span>|  
||<span data-ttu-id="ebf21-122">Messages received</span><span class="sxs-lookup"><span data-stu-id="ebf21-122">Messages received</span></span>|<span data-ttu-id="ebf21-123">ファイル受信アダプターが受信したメッセージの総数。</span><span class="sxs-lookup"><span data-stu-id="ebf21-123">Total number of messages received by the file receive adapter.</span></span> <span data-ttu-id="ebf21-124">このカウンターは、ファイル受信アダプターがファイル システムからメッセージを完全に読み取った後で増やされます。</span><span class="sxs-lookup"><span data-stu-id="ebf21-124">The counter is incremented after a message is completely read by the file receive adapter from the file system.</span></span>|  
||<span data-ttu-id="ebf21-125">Messages received/Sec</span><span class="sxs-lookup"><span data-stu-id="ebf21-125">Messages received/Sec</span></span>|<span data-ttu-id="ebf21-126">ファイル受信アダプターが 1 秒あたりに受信したメッセージ数。</span><span class="sxs-lookup"><span data-stu-id="ebf21-126">Number of messages received by the file receive adapter per second.</span></span> <span data-ttu-id="ebf21-127">このカウンターの対象となるのは、ファイル受信アダプターがファイル システムから完全に読み取ったメッセージだけです。</span><span class="sxs-lookup"><span data-stu-id="ebf21-127">The counter applies only to messages that have been completely read by the file receive adapter from the file system.</span></span>|  
||<span data-ttu-id="ebf21-128">Time to build batch</span><span class="sxs-lookup"><span data-stu-id="ebf21-128">Time to build batch</span></span>|<span data-ttu-id="ebf21-129">ファイル受信アダプターがバッチの作成に要した平均時間。</span><span class="sxs-lookup"><span data-stu-id="ebf21-129">Average time taken by file receive adapter to build a batch.</span></span>|  
|<span data-ttu-id="ebf21-130">BizTalk:ファイル送信アダプター</span><span class="sxs-lookup"><span data-stu-id="ebf21-130">BizTalk:FILE Send Adapter</span></span>|<span data-ttu-id="ebf21-131">Bytes sent</span><span class="sxs-lookup"><span data-stu-id="ebf21-131">Bytes sent</span></span>|<span data-ttu-id="ebf21-132">ファイル送信アダプターによって送信された合計バイト数。</span><span class="sxs-lookup"><span data-stu-id="ebf21-132">Total number of bytes sent by the file send adapter.</span></span> <span data-ttu-id="ebf21-133">カウンターは、メッセージがファイル システムに完全に書き込まれた場合にのみ増やされます。</span><span class="sxs-lookup"><span data-stu-id="ebf21-133">The counter is incremented only for messages that have been completely written to file system.</span></span>|  
||<span data-ttu-id="ebf21-134">Bytes sent/Sec</span><span class="sxs-lookup"><span data-stu-id="ebf21-134">Bytes sent/Sec</span></span>|<span data-ttu-id="ebf21-135">ファイル送信アダプターによって送信された 1 秒あたりのバイト数。</span><span class="sxs-lookup"><span data-stu-id="ebf21-135">Number of bytes sent by the file send adapter per second.</span></span> <span data-ttu-id="ebf21-136">このカウンターの対象となるのは、ファイル システムに完全に書き込まれたメッセージだけです。</span><span class="sxs-lookup"><span data-stu-id="ebf21-136">The counter applies only to messages that have been completely written to file system.</span></span>|  
||<span data-ttu-id="ebf21-137">Messages sent</span><span class="sxs-lookup"><span data-stu-id="ebf21-137">Messages sent</span></span>|<span data-ttu-id="ebf21-138">ファイル送信アダプターによって送信されたメッセージの総数。</span><span class="sxs-lookup"><span data-stu-id="ebf21-138">Total number of messages sent by the file send adapter.</span></span> <span data-ttu-id="ebf21-139">カウンターは、メッセージがファイル システムに完全に書き込まれた場合にのみ増やされます。</span><span class="sxs-lookup"><span data-stu-id="ebf21-139">The counter is incremented only for messages that have been completely written to file system.</span></span>|  
||<span data-ttu-id="ebf21-140">Messages Sent/sec</span><span class="sxs-lookup"><span data-stu-id="ebf21-140">Messages sent/Sec</span></span>|<span data-ttu-id="ebf21-141">ファイル送信アダプターによって送信された 1 秒あたりのメッセージ数。</span><span class="sxs-lookup"><span data-stu-id="ebf21-141">Number of messages sent by the file send adapter per second.</span></span> <span data-ttu-id="ebf21-142">このカウンターの対象となるのは、ファイル システムに完全に書き込まれたメッセージだけです。</span><span class="sxs-lookup"><span data-stu-id="ebf21-142">The counter applies only to messages that have been completely written to file system.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="ebf21-143">パフォーマンス カウンターにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="ebf21-143">To access performance counters</span></span>  
 <span data-ttu-id="ebf21-144">パフォーマンス カウンターにアクセスするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ebf21-144">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="ebf21-145">Windows 2008 を使用している場合</span><span class="sxs-lookup"><span data-stu-id="ebf21-145">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="ebf21-146">をクリックして**開始**、 をポイント**管理ツール**、順にクリック**パフォーマンス モニター**です。</span><span class="sxs-lookup"><span data-stu-id="ebf21-146">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="ebf21-147">**パフォーマンス モニター** ] ダイアログ ボックスで、展開**の監視ツールを**[**パフォーマンス モニター**、順にクリック**追加**です。</span><span class="sxs-lookup"><span data-stu-id="ebf21-147">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="ebf21-148">**カウンターの追加** ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **biztalk: ファイル**パフォーマンス カウンター オブジェクトおよび監視するカウンターの選択</span><span class="sxs-lookup"><span data-stu-id="ebf21-148">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:FILE** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="ebf21-149">**インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**です。</span><span class="sxs-lookup"><span data-stu-id="ebf21-149">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="ebf21-150">使用可能なカウンターのすべてのインスタンスを選択するには、次のように選択します。 \<**すべてのインスタンス**\>です。</span><span class="sxs-lookup"><span data-stu-id="ebf21-150">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="ebf21-151">カウンターを追加すると、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="ebf21-151">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="ebf21-152">選択したパフォーマンス カウンターが表示されます、**パフォーマンス モニター**画面。</span><span class="sxs-lookup"><span data-stu-id="ebf21-152">The selected performance counters appear on the **Performance Monitor** screen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebf21-153">参照</span><span class="sxs-lookup"><span data-stu-id="ebf21-153">See Also</span></span>  
 [<span data-ttu-id="ebf21-154">パフォーマンス維持の計画</span><span class="sxs-lookup"><span data-stu-id="ebf21-154">Planning for Sustained Performance</span></span>](../core/planning-for-sustained-performance.md)