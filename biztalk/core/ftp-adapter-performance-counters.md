---
title: FTP アダプターのパフォーマンス カウンター |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ca5cbe67-9aa3-4194-816e-fab4eb551c07
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dad67f24f37f661e26f4cb56895c6bcad6b0782
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969440"
---
# <a name="ftp-adapter-performance-counters"></a><span data-ttu-id="36e99-102">FTP アダプターのパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="36e99-102">FTP Adapter Performance Counters</span></span>
<span data-ttu-id="36e99-103">パフォーマンス カウンターを使用すると、サービスによってサイトまたはシステムで実行されている作業の具体的な側面を監視できます。</span><span class="sxs-lookup"><span data-stu-id="36e99-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="36e99-104">パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="36e99-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="36e99-105">次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできる、 **BizTalk:FTP Receive Adapter**と**BizTalk:FTP Send Adapter**パフォーマンス オブジェクト カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="36e99-105">The following performance counters are accessible for each host instance under the **BizTalk:FTP Receive Adapter** and the **BizTalk:FTP Send Adapter** performance object categories:</span></span>  
  
|<span data-ttu-id="36e99-106">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="36e99-106">**Category**</span></span>|<span data-ttu-id="36e99-107">**カウンター**</span><span class="sxs-lookup"><span data-stu-id="36e99-107">**Counter**</span></span>|<span data-ttu-id="36e99-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="36e99-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="36e99-109">BizTalk:FTP Receive Adapter</span><span class="sxs-lookup"><span data-stu-id="36e99-109">BizTalk:FTP Receive Adapter</span></span>|<span data-ttu-id="36e99-110">Bytes received</span><span class="sxs-lookup"><span data-stu-id="36e99-110">Bytes received</span></span>|<span data-ttu-id="36e99-111">FTP 受信アダプターによって受信された合計バイト数。</span><span class="sxs-lookup"><span data-stu-id="36e99-111">Total number of bytes received by the FTP receive adapter.</span></span> <span data-ttu-id="36e99-112">このカウンターは、FTP 受信アダプターが FTP サーバーからメッセージを完全に読み取った後で増やされます。</span><span class="sxs-lookup"><span data-stu-id="36e99-112">The counter is incremented after a message is completely read by the FTP receive adapter from the FTP server.</span></span>|  
||<span data-ttu-id="36e99-113">Bytes received/Sec</span><span class="sxs-lookup"><span data-stu-id="36e99-113">Bytes received/Sec</span></span>|<span data-ttu-id="36e99-114">FTP 受信アダプターが 1 秒あたりに受信したバイト数。</span><span class="sxs-lookup"><span data-stu-id="36e99-114">Number of bytes received by the FTP receive adapter per second.</span></span> <span data-ttu-id="36e99-115">このカウンターの対象となるのは、FTP 受信アダプターが FTP サーバーから完全に読み取ったメッセージだけです。</span><span class="sxs-lookup"><span data-stu-id="36e99-115">The counter applies only to messages that have been completely read by the FTP receive adapter from the FTP server.</span></span>|  
||<span data-ttu-id="36e99-116">Messages received</span><span class="sxs-lookup"><span data-stu-id="36e99-116">Messages received</span></span>|<span data-ttu-id="36e99-117">FTP 受信アダプターによって受信された合計メッセージ数。</span><span class="sxs-lookup"><span data-stu-id="36e99-117">Total number of messages received by the FTP receive adapter.</span></span> <span data-ttu-id="36e99-118">このカウンターは、FTP 受信アダプターが FTP サーバーからメッセージを完全に読み取った後で増やされます。</span><span class="sxs-lookup"><span data-stu-id="36e99-118">The counter is incremented after a message is completely read by the FTP receive adapter from the FTP server.</span></span>|  
||<span data-ttu-id="36e99-119">Messages received/Sec</span><span class="sxs-lookup"><span data-stu-id="36e99-119">Messages received/Sec</span></span>|<span data-ttu-id="36e99-120">FTP 受信アダプターが 1 秒あたりに受信したメッセージ数。</span><span class="sxs-lookup"><span data-stu-id="36e99-120">Number of messages received by the FTP receive adapter per second.</span></span> <span data-ttu-id="36e99-121">このカウンターの対象となるのは、FTP 受信アダプターが FTP サーバーから完全に読み取ったメッセージだけです。</span><span class="sxs-lookup"><span data-stu-id="36e99-121">The counter applies only to messages that have been completely read by the FTP receive adapter from the FTP server.</span></span>|  
|<span data-ttu-id="36e99-122">BizTalk:FTP Send Adapter</span><span class="sxs-lookup"><span data-stu-id="36e99-122">BizTalk:FTP Send Adapter</span></span>|<span data-ttu-id="36e99-123">Bytes sent</span><span class="sxs-lookup"><span data-stu-id="36e99-123">Bytes sent</span></span>|<span data-ttu-id="36e99-124">FTP 送信アダプターによって送信された合計バイト数。</span><span class="sxs-lookup"><span data-stu-id="36e99-124">Total number of bytes sent by the FTP send adapter.</span></span> <span data-ttu-id="36e99-125">カウンターは、メッセージが出力先 FTP サーバーに書き込まれた場合にのみ増やされます。</span><span class="sxs-lookup"><span data-stu-id="36e99-125">The counter is incremented only for messages that have been written to the destination FTP server.</span></span>|  
||<span data-ttu-id="36e99-126">Bytes sent/Sec</span><span class="sxs-lookup"><span data-stu-id="36e99-126">Bytes sent/Sec</span></span>|<span data-ttu-id="36e99-127">FTP 送信アダプターによって送信された 1 秒あたりのバイト数。</span><span class="sxs-lookup"><span data-stu-id="36e99-127">Number of bytes sent by the FTP send adapter per second.</span></span> <span data-ttu-id="36e99-128">カウンターは、送信先 FTP サーバーに書き込まれたメッセージにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="36e99-128">The counter applies only to messages that have been written to the destination FTP server.</span></span>|  
||<span data-ttu-id="36e99-129">Messages sent</span><span class="sxs-lookup"><span data-stu-id="36e99-129">Messages sent</span></span>|<span data-ttu-id="36e99-130">FTP 送信アダプターによって送信されたメッセージの総数。</span><span class="sxs-lookup"><span data-stu-id="36e99-130">Total number of messages sent by the FTP send adapter.</span></span> <span data-ttu-id="36e99-131">カウンターは、メッセージが出力先 FTP サーバーに書き込まれた場合にのみ増やされます。</span><span class="sxs-lookup"><span data-stu-id="36e99-131">The counter is incremented only for messages that have been written to the destination FTP server.</span></span>|  
||<span data-ttu-id="36e99-132">Messages Sent/sec</span><span class="sxs-lookup"><span data-stu-id="36e99-132">Messages sent/Sec</span></span>|<span data-ttu-id="36e99-133">FTP 送信アダプターによって送信された 1 秒あたりのメッセージ数。</span><span class="sxs-lookup"><span data-stu-id="36e99-133">Number of messages sent by the FTP send adapter per second.</span></span> <span data-ttu-id="36e99-134">このカウンターの対象となるのは、出力先 FTP サーバーに書き込まれたメッセージだけです。</span><span class="sxs-lookup"><span data-stu-id="36e99-134">The counter applies only to messages that have been written to destination FTP server.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="36e99-135">パフォーマンス カウンターにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="36e99-135">To access performance counters</span></span>  
 <span data-ttu-id="36e99-136">パフォーマンス カウンターにアクセスするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="36e99-136">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="36e99-137">Windows 2008 を使用している場合</span><span class="sxs-lookup"><span data-stu-id="36e99-137">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="36e99-138">をクリックして**開始**、 をポイント**管理ツール**、順にクリック**パフォーマンス モニター**です。</span><span class="sxs-lookup"><span data-stu-id="36e99-138">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="36e99-139">**パフォーマンス モニター** ] ダイアログ ボックスで、展開**の監視ツールを**[**パフォーマンス モニター**、順にクリック**追加**です。</span><span class="sxs-lookup"><span data-stu-id="36e99-139">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="36e99-140">**カウンターの追加** ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **biztalk:ftp**パフォーマンス カウンター オブジェクトおよび監視するカウンターの選択</span><span class="sxs-lookup"><span data-stu-id="36e99-140">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:FTP** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="36e99-141">**インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**です。</span><span class="sxs-lookup"><span data-stu-id="36e99-141">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="36e99-142">使用可能なカウンターのすべてのインスタンスを選択するには、次のように選択します。 \<**すべてのインスタンス**\>です。</span><span class="sxs-lookup"><span data-stu-id="36e99-142">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="36e99-143">カウンターを追加すると、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="36e99-143">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="36e99-144">選択したパフォーマンス カウンターが表示されます、**パフォーマンス モニター**画面。</span><span class="sxs-lookup"><span data-stu-id="36e99-144">The selected performance counters appear on the **Performance Monitor** screen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36e99-145">参照</span><span class="sxs-lookup"><span data-stu-id="36e99-145">See Also</span></span>  
 <span data-ttu-id="36e99-146">[BizTalk Server の監視](../core/monitoring-biztalk-server.md)[クラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)</span><span class="sxs-lookup"><span data-stu-id="36e99-146">[Monitoring BizTalk Server](../core/monitoring-biztalk-server.md) [Considerations for Running Adapter Handlers within a Clustered Host](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)</span></span>