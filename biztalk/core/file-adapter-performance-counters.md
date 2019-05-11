---
title: ファイル アダプターのパフォーマンス カウンター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 343465b4-6b20-4a24-b4b1-138548c572cc
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5920638764e274137ca7a2d94ab11248ae1b200f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345559"
---
# <a name="file-adapter-performance-counters"></a><span data-ttu-id="22882-102">ファイル アダプターのパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="22882-102">File Adapter Performance Counters</span></span>
<span data-ttu-id="22882-103">パフォーマンス カウンターを使用して、サービスによってサイトまたはシステムで実行される作業の具体的な側面を監視できます。</span><span class="sxs-lookup"><span data-stu-id="22882-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="22882-104">パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="22882-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="22882-105">次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできますが、 **biztalk: ファイル受信アダプター**と**biztalk: ファイル送信アダプター**パフォーマンス オブジェクト カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="22882-105">The following performance counters are accessible for each host instance under the **BizTalk:FILE Receive Adapter** and the **BizTalk:FILE Send Adapter** performance object categories:</span></span>  
  
|<span data-ttu-id="22882-106">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="22882-106">**Category**</span></span>|<span data-ttu-id="22882-107">**カウンター**</span><span class="sxs-lookup"><span data-stu-id="22882-107">**Counter**</span></span>|<span data-ttu-id="22882-108">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="22882-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="22882-109">Biztalk: ファイル受信アダプター</span><span class="sxs-lookup"><span data-stu-id="22882-109">BizTalk:FILE Receive Adapter</span></span>|<span data-ttu-id="22882-110">受信したバイト数</span><span class="sxs-lookup"><span data-stu-id="22882-110">Bytes received</span></span>|<span data-ttu-id="22882-111">ファイルで受信したバイトの合計数には、アダプターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="22882-111">Total number of bytes received by the file receive adapter.</span></span> <span data-ttu-id="22882-112">メッセージがアダプターによってファイル システムから完全に読み取った後、カウンターがインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="22882-112">The counter is incremented after a message is completely read by the adapter from the file system.</span></span>|  
||<span data-ttu-id="22882-113">バイトの受信/秒</span><span class="sxs-lookup"><span data-stu-id="22882-113">Byte received/Sec</span></span>|<span data-ttu-id="22882-114">1 秒あたりにアダプターを受信するファイルで受信したバイト数。</span><span class="sxs-lookup"><span data-stu-id="22882-114">Number of bytes received by the file receive adapter per second.</span></span> <span data-ttu-id="22882-115">このカウンターは、ファイル アダプターがファイル システムから完全に読み取られたメッセージのみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="22882-115">The counter applies only to messages that have been completely read by the file adapter from the file system.</span></span>|  
||<span data-ttu-id="22882-116">再試行を削除します。</span><span class="sxs-lookup"><span data-stu-id="22882-116">Delete retries</span></span>|<span data-ttu-id="22882-117">ファイル受信アダプター回数は、読み取られたファイルを削除しようとします。</span><span class="sxs-lookup"><span data-stu-id="22882-117">Number of times the file receive adapter attempts to delete a file that has been read.</span></span>|  
||<span data-ttu-id="22882-118">ロック エラー</span><span class="sxs-lookup"><span data-stu-id="22882-118">Lock failures</span></span>|<span data-ttu-id="22882-119">回数、ファイル受信アダプターは、ファイルのロックに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="22882-119">Number of times the file receive adapter failed to lock the file.</span></span>|  
||<span data-ttu-id="22882-120">ロックの失敗数/秒</span><span class="sxs-lookup"><span data-stu-id="22882-120">Lock failures/sec</span></span>|<span data-ttu-id="22882-121">ファイル受信アダプター回数は 1 秒あたりのファイルをロックできませんでした。</span><span class="sxs-lookup"><span data-stu-id="22882-121">Number of times the file receive adapter failed to lock the file per second.</span></span>|  
||<span data-ttu-id="22882-122">受信したメッセージ</span><span class="sxs-lookup"><span data-stu-id="22882-122">Messages received</span></span>|<span data-ttu-id="22882-123">ファイルが受信したメッセージの合計数には、アダプターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="22882-123">Total number of messages received by the file receive adapter.</span></span> <span data-ttu-id="22882-124">メッセージは、ファイルによって完全に読み取った後、カウンターがインクリメント ファイル システムからの受信アダプター。</span><span class="sxs-lookup"><span data-stu-id="22882-124">The counter is incremented after a message is completely read by the file receive adapter from the file system.</span></span>|  
||<span data-ttu-id="22882-125">メッセージの受信/秒</span><span class="sxs-lookup"><span data-stu-id="22882-125">Messages received/Sec</span></span>|<span data-ttu-id="22882-126">1 秒あたりにアダプターを受信するファイルが受信したメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="22882-126">Number of messages received by the file receive adapter per second.</span></span> <span data-ttu-id="22882-127">このカウンターの対象にのみ、ファイル システムからファイルが完全に読み取られたメッセージの受信アダプター。</span><span class="sxs-lookup"><span data-stu-id="22882-127">The counter applies only to messages that have been completely read by the file receive adapter from the file system.</span></span>|  
||<span data-ttu-id="22882-128">バッチの作成に時間</span><span class="sxs-lookup"><span data-stu-id="22882-128">Time to build batch</span></span>|<span data-ttu-id="22882-129">ファイルに要した平均時間の受信アダプターがバッチの作成にします。</span><span class="sxs-lookup"><span data-stu-id="22882-129">Average time taken by file receive adapter to build a batch.</span></span>|  
|<span data-ttu-id="22882-130">Biztalk: ファイル送信アダプター</span><span class="sxs-lookup"><span data-stu-id="22882-130">BizTalk:FILE Send Adapter</span></span>|<span data-ttu-id="22882-131">送信バイト数</span><span class="sxs-lookup"><span data-stu-id="22882-131">Bytes sent</span></span>|<span data-ttu-id="22882-132">ファイルから送信されたバイトの合計数は送信アダプターです。</span><span class="sxs-lookup"><span data-stu-id="22882-132">Total number of bytes sent by the file send adapter.</span></span> <span data-ttu-id="22882-133">カウンターは、ファイル システムに完全に書き込まれたメッセージに対してのみインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="22882-133">The counter is incremented only for messages that have been completely written to file system.</span></span>|  
||<span data-ttu-id="22882-134">送信バイト数/秒</span><span class="sxs-lookup"><span data-stu-id="22882-134">Bytes sent/Sec</span></span>|<span data-ttu-id="22882-135">ファイルから送信されたバイト数では、1 秒あたりにアダプターを送信します。</span><span class="sxs-lookup"><span data-stu-id="22882-135">Number of bytes sent by the file send adapter per second.</span></span> <span data-ttu-id="22882-136">このカウンターは、ファイル システムに完全に書き込まれたメッセージのみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="22882-136">The counter applies only to messages that have been completely written to file system.</span></span>|  
||<span data-ttu-id="22882-137">送信されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="22882-137">Messages sent</span></span>|<span data-ttu-id="22882-138">ファイルから送信されたメッセージの合計数は送信アダプターです。</span><span class="sxs-lookup"><span data-stu-id="22882-138">Total number of messages sent by the file send adapter.</span></span> <span data-ttu-id="22882-139">カウンターは、ファイル システムに完全に書き込まれたメッセージに対してのみインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="22882-139">The counter is incremented only for messages that have been completely written to file system.</span></span>|  
||<span data-ttu-id="22882-140">メッセージの送信/秒</span><span class="sxs-lookup"><span data-stu-id="22882-140">Messages sent/Sec</span></span>|<span data-ttu-id="22882-141">ファイルから送信されたメッセージの数は、1 秒あたりにアダプターを送信します。</span><span class="sxs-lookup"><span data-stu-id="22882-141">Number of messages sent by the file send adapter per second.</span></span> <span data-ttu-id="22882-142">このカウンターは、ファイル システムに完全に書き込まれたメッセージのみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="22882-142">The counter applies only to messages that have been completely written to file system.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="22882-143">パフォーマンス カウンターにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="22882-143">To access performance counters</span></span>  
 <span data-ttu-id="22882-144">パフォーマンス カウンターにアクセスするのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="22882-144">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="22882-145">Windows 2008 を使用している場合</span><span class="sxs-lookup"><span data-stu-id="22882-145">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="22882-146">クリックして**開始**、 をポイント**管理ツール**、順にクリックします**パフォーマンス モニター**します。</span><span class="sxs-lookup"><span data-stu-id="22882-146">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="22882-147">**パフォーマンス モニター**  ダイアログ ボックスで、展開**監視ツール**を選択します**パフォーマンス モニター**、 をクリックし、**追加**。</span><span class="sxs-lookup"><span data-stu-id="22882-147">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="22882-148">**カウンターの追加** ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **biztalk: ファイル**パフォーマンス カウンター オブジェクトと監視するカウンターを選択します。</span><span class="sxs-lookup"><span data-stu-id="22882-148">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:FILE** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="22882-149">**インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**します。</span><span class="sxs-lookup"><span data-stu-id="22882-149">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="22882-150">使用可能なカウンターのインスタンスすべてを選択する\<**すべてのインスタンス**\>します。</span><span class="sxs-lookup"><span data-stu-id="22882-150">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="22882-151">カウンターを追加すると、次のようにクリックします。 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="22882-151">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="22882-152">選択したパフォーマンス カウンターが表示される、**パフォーマンス モニター**画面。</span><span class="sxs-lookup"><span data-stu-id="22882-152">The selected performance counters appear on the **Performance Monitor** screen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22882-153">参照</span><span class="sxs-lookup"><span data-stu-id="22882-153">See Also</span></span>  
 [<span data-ttu-id="22882-154">パフォーマンス維持の計画</span><span class="sxs-lookup"><span data-stu-id="22882-154">Planning for Sustained Performance</span></span>](../core/planning-for-sustained-performance.md)