---
title: FTP アダプターのパフォーマンス カウンター |Microsoft Docs
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
ms.openlocfilehash: c7710f0dc5cff707aee60892c833ad178eadb9f1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387814"
---
# <a name="ftp-adapter-performance-counters"></a><span data-ttu-id="33ad5-102">FTP アダプターのパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="33ad5-102">FTP Adapter Performance Counters</span></span>
<span data-ttu-id="33ad5-103">パフォーマンス カウンターを使用して、サービスによってサイトまたはシステムで実行される作業の具体的な側面を監視できます。</span><span class="sxs-lookup"><span data-stu-id="33ad5-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="33ad5-104">パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="33ad5-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="33ad5-105">次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできますが、 **BizTalk:FTP Receive Adapter**と**BizTalk:FTP Send Adapter**パフォーマンス オブジェクト カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="33ad5-105">The following performance counters are accessible for each host instance under the **BizTalk:FTP Receive Adapter** and the **BizTalk:FTP Send Adapter** performance object categories:</span></span>  
  
|<span data-ttu-id="33ad5-106">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="33ad5-106">**Category**</span></span>|<span data-ttu-id="33ad5-107">**カウンター**</span><span class="sxs-lookup"><span data-stu-id="33ad5-107">**Counter**</span></span>|<span data-ttu-id="33ad5-108">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="33ad5-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="33ad5-109">BizTalk:FTP 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="33ad5-109">BizTalk:FTP Receive Adapter</span></span>|<span data-ttu-id="33ad5-110">受信したバイト数</span><span class="sxs-lookup"><span data-stu-id="33ad5-110">Bytes received</span></span>|<span data-ttu-id="33ad5-111">受信アダプター、FTP を使用して受信したバイトの合計数。</span><span class="sxs-lookup"><span data-stu-id="33ad5-111">Total number of bytes received by the FTP receive adapter.</span></span> <span data-ttu-id="33ad5-112">メッセージは、FTP を使用して完全に読み取った後、カウンターがインクリメント受信アダプター、FTP サーバーからです。</span><span class="sxs-lookup"><span data-stu-id="33ad5-112">The counter is incremented after a message is completely read by the FTP receive adapter from the FTP server.</span></span>|  
||<span data-ttu-id="33ad5-113">受信バイト数/秒</span><span class="sxs-lookup"><span data-stu-id="33ad5-113">Bytes received/Sec</span></span>|<span data-ttu-id="33ad5-114">FTP で受信したバイト数では、1 秒あたりにアダプターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="33ad5-114">Number of bytes received by the FTP receive adapter per second.</span></span> <span data-ttu-id="33ad5-115">このカウンターの対象にのみ、FTP サーバーから、FTP を使用して完全に読み取られたメッセージの受信アダプター。</span><span class="sxs-lookup"><span data-stu-id="33ad5-115">The counter applies only to messages that have been completely read by the FTP receive adapter from the FTP server.</span></span>|  
||<span data-ttu-id="33ad5-116">受信したメッセージ</span><span class="sxs-lookup"><span data-stu-id="33ad5-116">Messages received</span></span>|<span data-ttu-id="33ad5-117">受信アダプター、FTP を使用して受信したメッセージの合計数。</span><span class="sxs-lookup"><span data-stu-id="33ad5-117">Total number of messages received by the FTP receive adapter.</span></span> <span data-ttu-id="33ad5-118">メッセージは、FTP を使用して完全に読み取った後、カウンターがインクリメント受信アダプター、FTP サーバーからです。</span><span class="sxs-lookup"><span data-stu-id="33ad5-118">The counter is incremented after a message is completely read by the FTP receive adapter from the FTP server.</span></span>|  
||<span data-ttu-id="33ad5-119">メッセージの受信/秒</span><span class="sxs-lookup"><span data-stu-id="33ad5-119">Messages received/Sec</span></span>|<span data-ttu-id="33ad5-120">FTP の受信メッセージの数には、1 秒あたりにアダプターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="33ad5-120">Number of messages received by the FTP receive adapter per second.</span></span> <span data-ttu-id="33ad5-121">このカウンターの対象にのみ、FTP サーバーから、FTP を使用して完全に読み取られたメッセージの受信アダプター。</span><span class="sxs-lookup"><span data-stu-id="33ad5-121">The counter applies only to messages that have been completely read by the FTP receive adapter from the FTP server.</span></span>|  
|<span data-ttu-id="33ad5-122">BizTalk:FTP 送信アダプター</span><span class="sxs-lookup"><span data-stu-id="33ad5-122">BizTalk:FTP Send Adapter</span></span>|<span data-ttu-id="33ad5-123">送信バイト数</span><span class="sxs-lookup"><span data-stu-id="33ad5-123">Bytes sent</span></span>|<span data-ttu-id="33ad5-124">送信アダプター、FTP によって送信されたバイト数の合計数。</span><span class="sxs-lookup"><span data-stu-id="33ad5-124">Total number of bytes sent by the FTP send adapter.</span></span> <span data-ttu-id="33ad5-125">カウンターは、送信先 FTP サーバーに書き込まれたメッセージに対してのみインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="33ad5-125">The counter is incremented only for messages that have been written to the destination FTP server.</span></span>|  
||<span data-ttu-id="33ad5-126">送信バイト数/秒</span><span class="sxs-lookup"><span data-stu-id="33ad5-126">Bytes sent/Sec</span></span>|<span data-ttu-id="33ad5-127">1 秒あたりにアダプターに送信して、FTP によって送信されたバイトの数。</span><span class="sxs-lookup"><span data-stu-id="33ad5-127">Number of bytes sent by the FTP send adapter per second.</span></span> <span data-ttu-id="33ad5-128">カウンターは、送信先 FTP サーバーに書き込まれたメッセージのみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="33ad5-128">The counter applies only to messages that have been written to the destination FTP server.</span></span>|  
||<span data-ttu-id="33ad5-129">送信されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="33ad5-129">Messages sent</span></span>|<span data-ttu-id="33ad5-130">送信アダプター、FTP によって送信されたメッセージの合計数。</span><span class="sxs-lookup"><span data-stu-id="33ad5-130">Total number of messages sent by the FTP send adapter.</span></span> <span data-ttu-id="33ad5-131">カウンターは、送信先 FTP サーバーに書き込まれたメッセージに対してのみインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="33ad5-131">The counter is incremented only for messages that have been written to the destination FTP server.</span></span>|  
||<span data-ttu-id="33ad5-132">メッセージの送信/秒</span><span class="sxs-lookup"><span data-stu-id="33ad5-132">Messages sent/Sec</span></span>|<span data-ttu-id="33ad5-133">1 秒あたりにアダプターに送信して、FTP によって送信されたメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="33ad5-133">Number of messages sent by the FTP send adapter per second.</span></span> <span data-ttu-id="33ad5-134">このカウンターは、送信先 FTP サーバーに書き込まれたメッセージのみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="33ad5-134">The counter applies only to messages that have been written to destination FTP server.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="33ad5-135">パフォーマンス カウンターにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="33ad5-135">To access performance counters</span></span>  
 <span data-ttu-id="33ad5-136">パフォーマンス カウンターにアクセスするのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="33ad5-136">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="33ad5-137">Windows 2008 を使用している場合</span><span class="sxs-lookup"><span data-stu-id="33ad5-137">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="33ad5-138">クリックして**開始**、 をポイント**管理ツール**、順にクリックします**パフォーマンス モニター**します。</span><span class="sxs-lookup"><span data-stu-id="33ad5-138">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="33ad5-139">**パフォーマンス モニター**  ダイアログ ボックスで、展開**監視ツール**を選択します**パフォーマンス モニター**、 をクリックし、**追加**。</span><span class="sxs-lookup"><span data-stu-id="33ad5-139">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="33ad5-140">**カウンターの追加**] ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **[BizTalk:FTP**パフォーマンス カウンター オブジェクトと監視するカウンターを選択します。</span><span class="sxs-lookup"><span data-stu-id="33ad5-140">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:FTP** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="33ad5-141">**インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**します。</span><span class="sxs-lookup"><span data-stu-id="33ad5-141">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="33ad5-142">使用可能なカウンターのインスタンスすべてを選択する\<**すべてのインスタンス**\>します。</span><span class="sxs-lookup"><span data-stu-id="33ad5-142">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="33ad5-143">カウンターを追加すると、次のようにクリックします。 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="33ad5-143">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="33ad5-144">選択したパフォーマンス カウンターが表示される、**パフォーマンス モニター**画面。</span><span class="sxs-lookup"><span data-stu-id="33ad5-144">The selected performance counters appear on the **Performance Monitor** screen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33ad5-145">参照</span><span class="sxs-lookup"><span data-stu-id="33ad5-145">See Also</span></span>  
 <span data-ttu-id="33ad5-146">[BizTalk Server の監視](../core/monitoring-biztalk-server.md)[クラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)</span><span class="sxs-lookup"><span data-stu-id="33ad5-146">[Monitoring BizTalk Server](../core/monitoring-biztalk-server.md) [Considerations for Running Adapter Handlers within a Clustered Host](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)</span></span>