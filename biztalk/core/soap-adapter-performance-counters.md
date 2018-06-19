---
title: SOAP アダプターのパフォーマンス カウンター |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40b54d4e-0a2e-483f-982a-97ab9fb59202
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 543c982a68d2a940b4800711d757f4fb159611de
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974520"
---
# <a name="soap-adapter-performance-counters"></a><span data-ttu-id="5d6b2-102">SOAP アダプターのパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="5d6b2-102">SOAP Adapter Performance Counters</span></span>
<span data-ttu-id="5d6b2-103">パフォーマンス カウンターを使用すると、サービスによってサイトまたはシステムで実行されている作業の具体的な側面を監視できます。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="5d6b2-104">パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="5d6b2-105">次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできる、 **BizTalk:SOAP 受信アダプター**と**BizTalk:SOAP 送信アダプター**パフォーマンス オブジェクト カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-105">The following performance counters are accessible for each host instance under the **BizTalk:SOAP Receive Adapter** and the **BizTalk:SOAP Send Adapter** performance object categories:</span></span>  
  
|<span data-ttu-id="5d6b2-106">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="5d6b2-106">**Category**</span></span>|<span data-ttu-id="5d6b2-107">**カウンター**</span><span class="sxs-lookup"><span data-stu-id="5d6b2-107">**Counter**</span></span>|<span data-ttu-id="5d6b2-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="5d6b2-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="5d6b2-109">BizTalk:SOAP 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="5d6b2-109">BizTalk:SOAP Receive Adapter</span></span>|<span data-ttu-id="5d6b2-110">Messages received</span><span class="sxs-lookup"><span data-stu-id="5d6b2-110">Messages received</span></span>|<span data-ttu-id="5d6b2-111">SOAP 受信アダプターが受信したメッセージの総数。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-111">Total number of messages received by the SOAP receive adapter.</span></span> <span data-ttu-id="5d6b2-112">このカウンターは、アダプターが SOAP クライアントから要求メッセージを完全に読み取った後で増やされます。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-112">The counter is incremented after a request message is completely read by the adapter from the SOAP client.</span></span>|  
||<span data-ttu-id="5d6b2-113">Messages received/Sec</span><span class="sxs-lookup"><span data-stu-id="5d6b2-113">Messages received/Sec</span></span>|<span data-ttu-id="5d6b2-114">SOAP 受信アダプターが 1 秒あたりに受信したメッセージ数。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-114">Number of messages received by the SOAP receive adapter per second.</span></span> <span data-ttu-id="5d6b2-115">このカウンターの対象となるのは、アダプターが SOAP クライアントから完全に読み取った要求メッセージだけです。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-115">The counter applies only to request messages that have been completely read by the adapter from the SOAP client.</span></span>|  
|<span data-ttu-id="5d6b2-116">BizTalk:SOAP 送信アダプター</span><span class="sxs-lookup"><span data-stu-id="5d6b2-116">BizTalk:SOAP Send Adapter</span></span>|<span data-ttu-id="5d6b2-117">Messages sent</span><span class="sxs-lookup"><span data-stu-id="5d6b2-117">Messages sent</span></span>|<span data-ttu-id="5d6b2-118">SOAP 送信アダプターによって送信されたメッセージの総数。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-118">Total number of messages sent by the SOAP send adapter.</span></span> <span data-ttu-id="5d6b2-119">カウンターは、メッセージが送信先 URL に到達した場合にのみ増やされます。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-119">The counter is incremented only for messages that have reached the destination URL.</span></span>|  
||<span data-ttu-id="5d6b2-120">Messages Sent/sec</span><span class="sxs-lookup"><span data-stu-id="5d6b2-120">Messages sent/Sec</span></span>|<span data-ttu-id="5d6b2-121">SOAP 送信アダプターによって送信された 1 秒あたりのメッセージ数。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-121">Number of messages sent by the SOAP send adapter per second.</span></span> <span data-ttu-id="5d6b2-122">送信先 URL に到達したメッセージのみが対象となります。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-122">The counter applies only to messages that have reached the destination URL.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="5d6b2-123">パフォーマンス カウンターにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="5d6b2-123">To access performance counters</span></span>  
 <span data-ttu-id="5d6b2-124">パフォーマンス カウンターにアクセスするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-124">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-server-2008"></a><span data-ttu-id="5d6b2-125">Windows Server 2008 を使用している場合</span><span class="sxs-lookup"><span data-stu-id="5d6b2-125">If you are using Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="5d6b2-126">をクリックして**開始**、 をポイント**管理ツール**、順にクリック**パフォーマンス モニター**です。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-126">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="5d6b2-127">**パフォーマンス モニター** ] ダイアログ ボックスで、展開**の監視ツールを**[**パフォーマンス モニター**、順にクリック**追加**です。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-127">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="5d6b2-128">**カウンターの追加** ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **BizTalk:SOAP**パフォーマンス カウンター オブジェクトおよび監視するカウンターの選択</span><span class="sxs-lookup"><span data-stu-id="5d6b2-128">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:SOAP** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="5d6b2-129">**インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**です。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-129">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span> <span data-ttu-id="5d6b2-130">使用可能なカウンターのすべてのインスタンスを選択するには、次のように選択します。 \<**すべてのインスタンス**\>です。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-130">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="5d6b2-131">カウンターを追加すると、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-131">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="5d6b2-132">選択したパフォーマンス カウンターが表示されます、**パフォーマンス モニター**画面。</span><span class="sxs-lookup"><span data-stu-id="5d6b2-132">The selected performance counters appear on the **Performance Monitor** screen.</span></span>