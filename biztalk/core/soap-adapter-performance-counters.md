---
title: SOAP アダプターのパフォーマンス カウンター |Microsoft Docs
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
ms.openlocfilehash: d5f13708fc59c02a9a74b652508aa74cf1a36f00
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314043"
---
# <a name="soap-adapter-performance-counters"></a><span data-ttu-id="c25d9-102">SOAP アダプターのパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="c25d9-102">SOAP Adapter Performance Counters</span></span>
<span data-ttu-id="c25d9-103">パフォーマンス カウンターを使用して、サービスによってサイトまたはシステムで実行される作業の具体的な側面を監視できます。</span><span class="sxs-lookup"><span data-stu-id="c25d9-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="c25d9-104">パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c25d9-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="c25d9-105">次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできますが、 **BizTalk:SOAP 受信アダプター**と**BizTalk:SOAP 送信アダプター**パフォーマンス オブジェクト カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="c25d9-105">The following performance counters are accessible for each host instance under the **BizTalk:SOAP Receive Adapter** and the **BizTalk:SOAP Send Adapter** performance object categories:</span></span>  
  
|<span data-ttu-id="c25d9-106">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="c25d9-106">**Category**</span></span>|<span data-ttu-id="c25d9-107">**カウンター**</span><span class="sxs-lookup"><span data-stu-id="c25d9-107">**Counter**</span></span>|<span data-ttu-id="c25d9-108">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="c25d9-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="c25d9-109">BizTalk:SOAP 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="c25d9-109">BizTalk:SOAP Receive Adapter</span></span>|<span data-ttu-id="c25d9-110">受信したメッセージ</span><span class="sxs-lookup"><span data-stu-id="c25d9-110">Messages received</span></span>|<span data-ttu-id="c25d9-111">受信アダプター、SOAP の受信メッセージの合計数。</span><span class="sxs-lookup"><span data-stu-id="c25d9-111">Total number of messages received by the SOAP receive adapter.</span></span> <span data-ttu-id="c25d9-112">要求メッセージがアダプターによって SOAP クライアントから完全に読み取られた後、カウンターがインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="c25d9-112">The counter is incremented after a request message is completely read by the adapter from the SOAP client.</span></span>|  
||<span data-ttu-id="c25d9-113">メッセージの受信/秒</span><span class="sxs-lookup"><span data-stu-id="c25d9-113">Messages received/Sec</span></span>|<span data-ttu-id="c25d9-114">1 秒あたりにアダプターを受信する SOAP の受信メッセージの数。</span><span class="sxs-lookup"><span data-stu-id="c25d9-114">Number of messages received by the SOAP receive adapter per second.</span></span> <span data-ttu-id="c25d9-115">このカウンターは、アダプターによって SOAP クライアントから完全に読み取られた要求メッセージのみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c25d9-115">The counter applies only to request messages that have been completely read by the adapter from the SOAP client.</span></span>|  
|<span data-ttu-id="c25d9-116">BizTalk:SOAP 送信アダプター</span><span class="sxs-lookup"><span data-stu-id="c25d9-116">BizTalk:SOAP Send Adapter</span></span>|<span data-ttu-id="c25d9-117">送信されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="c25d9-117">Messages sent</span></span>|<span data-ttu-id="c25d9-118">送信アダプター、SOAP で送信されたメッセージの合計数。</span><span class="sxs-lookup"><span data-stu-id="c25d9-118">Total number of messages sent by the SOAP send adapter.</span></span> <span data-ttu-id="c25d9-119">カウンターは、送信先 URL に到達したメッセージに対してのみインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="c25d9-119">The counter is incremented only for messages that have reached the destination URL.</span></span>|  
||<span data-ttu-id="c25d9-120">メッセージの送信/秒</span><span class="sxs-lookup"><span data-stu-id="c25d9-120">Messages sent/Sec</span></span>|<span data-ttu-id="c25d9-121">1 秒あたりにアダプターに送信して、SOAP で送信されるメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="c25d9-121">Number of messages sent by the SOAP send adapter per second.</span></span> <span data-ttu-id="c25d9-122">カウンターは、送信先 URL に到達したメッセージのみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c25d9-122">The counter applies only to messages that have reached the destination URL.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="c25d9-123">パフォーマンス カウンターにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="c25d9-123">To access performance counters</span></span>  
 <span data-ttu-id="c25d9-124">パフォーマンス カウンターにアクセスするのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c25d9-124">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-server-2008"></a><span data-ttu-id="c25d9-125">Windows Server 2008 を使用している場合</span><span class="sxs-lookup"><span data-stu-id="c25d9-125">If you are using Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="c25d9-126">クリックして**開始**、 をポイント**管理ツール**、順にクリックします**パフォーマンス モニター**します。</span><span class="sxs-lookup"><span data-stu-id="c25d9-126">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="c25d9-127">**パフォーマンス モニター**  ダイアログ ボックスで、展開**監視ツール**を選択します**パフォーマンス モニター**、 をクリックし、**追加**。</span><span class="sxs-lookup"><span data-stu-id="c25d9-127">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="c25d9-128">**カウンターの追加** ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **BizTalk:SOAP**パフォーマンス カウンター オブジェクトと監視するカウンターを選択します。</span><span class="sxs-lookup"><span data-stu-id="c25d9-128">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:SOAP** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="c25d9-129">**インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**します。</span><span class="sxs-lookup"><span data-stu-id="c25d9-129">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span> <span data-ttu-id="c25d9-130">使用可能なカウンターのインスタンスすべてを選択する\<**すべてのインスタンス**\>します。</span><span class="sxs-lookup"><span data-stu-id="c25d9-130">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="c25d9-131">カウンターを追加すると、次のようにクリックします。 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="c25d9-131">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="c25d9-132">選択したパフォーマンス カウンターが表示される、**パフォーマンス モニター**画面。</span><span class="sxs-lookup"><span data-stu-id="c25d9-132">The selected performance counters appear on the **Performance Monitor** screen.</span></span>