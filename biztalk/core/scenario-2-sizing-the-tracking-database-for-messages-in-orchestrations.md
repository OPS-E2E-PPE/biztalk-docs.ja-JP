---
title: 'シナリオ 2: オーケストレーション内のメッセージの追跡データベースのサイズ調整 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: d1cfb8b9-d4e2-4069-8db3-18f72358652b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e3a62df0431611c294a123835d7cc2faddca474
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308612"
---
# <a name="scenario-2-sizing-the-tracking-database--for-messages-in-orchestrations"></a><span data-ttu-id="a1bd8-102">シナリオ 2: オーケストレーション内のメッセージの追跡データベースのサイズ調整</span><span class="sxs-lookup"><span data-stu-id="a1bd8-102">Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations</span></span>
<span data-ttu-id="a1bd8-103">オーケストレーションを含む例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="a1bd8-103">Let's look at an example that includes an orchestration.</span></span> <span data-ttu-id="a1bd8-104">次の図は、ビジネス プロセス全体を表示します。</span><span class="sxs-lookup"><span data-stu-id="a1bd8-104">The following figure displays the entire business process.</span></span> <span data-ttu-id="a1bd8-105">このシナリオでメッセージが BizTalk Server に、オーケストレーションを通じて送信されますが、オーケストレーション内で変更および送信ポート経由送信されます。</span><span class="sxs-lookup"><span data-stu-id="a1bd8-105">In this scenario, a message comes into BizTalk Server, is sent through an orchestration, is changed within the orchestration, and is then sent out through a send port.</span></span>  
  
 <span data-ttu-id="a1bd8-106">![BizTalk Server メッセージ プロセス](../core/media/biztalk-server-message-process.gif "BizTalk_Server_Message_Process")</span><span class="sxs-lookup"><span data-stu-id="a1bd8-106">![BizTalk Server message process](../core/media/biztalk-server-message-process.gif "BizTalk_Server_Message_Process")</span></span>  
  
 <span data-ttu-id="a1bd8-107">**BizTalk Server メッセージ プロセス**</span><span class="sxs-lookup"><span data-stu-id="a1bd8-107">**The BizTalk Server message process**</span></span>  
  
 <span data-ttu-id="a1bd8-108">このシナリオに関するファクトの一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a1bd8-108">Here are some of the facts concerning this scenario:</span></span>  
  
- <span data-ttu-id="a1bd8-109">メッセージ サイズは、5 K です。</span><span class="sxs-lookup"><span data-stu-id="a1bd8-109">The message size is 5K.</span></span>  
  
- <span data-ttu-id="a1bd8-110">私たちは任意のプロパティを昇格しません。</span><span class="sxs-lookup"><span data-stu-id="a1bd8-110">We are not promoting any properties.</span></span>  
  
- <span data-ttu-id="a1bd8-111">1 年間に受信メッセージの数は、350万です。</span><span class="sxs-lookup"><span data-stu-id="a1bd8-111">The number of messages we receive in a year is 3.5 million.</span></span>  
  
- <span data-ttu-id="a1bd8-112">すべてのイベントの追跡がオンになっているとします。</span><span class="sxs-lookup"><span data-stu-id="a1bd8-112">Tracking is turned on for all events.</span></span> <span data-ttu-id="a1bd8-113">このシナリオには、6 つのイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="a1bd8-113">There are six events in this scenario:</span></span>  
  
  -   <span data-ttu-id="a1bd8-114">メッセージ M0 の受信</span><span class="sxs-lookup"><span data-stu-id="a1bd8-114">Receipt of message M0</span></span>  
  
  -   <span data-ttu-id="a1bd8-115">受信ポートからメッセージ M1 の出力</span><span class="sxs-lookup"><span data-stu-id="a1bd8-115">Output of message M1 from the receive port</span></span>  
  
  -   <span data-ttu-id="a1bd8-116">オーケストレーションによるメッセージ M1 の受信</span><span class="sxs-lookup"><span data-stu-id="a1bd8-116">Receipt of message M1 by the orchestration</span></span>  
  
  -   <span data-ttu-id="a1bd8-117">オーケストレーションからのメッセージ M2 の出力</span><span class="sxs-lookup"><span data-stu-id="a1bd8-117">Output of message M2 from the orchestration</span></span>  
  
  -   <span data-ttu-id="a1bd8-118">送信ポートによるメッセージ M2 の受信</span><span class="sxs-lookup"><span data-stu-id="a1bd8-118">Receipt of message M2 by the send port</span></span>  
  
  -   <span data-ttu-id="a1bd8-119">送信パイプラインによるメッセージ M3 の出力</span><span class="sxs-lookup"><span data-stu-id="a1bd8-119">Output of message M3 by the send pipeline</span></span>  
  
- <span data-ttu-id="a1bd8-120">このシナリオでは、3 つの追加メッセージが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a1bd8-120">Three additional messages are created in this scenario.</span></span> <span data-ttu-id="a1bd8-121">メッセージ M0 は受信メッセージを BizTalk Server によって作成されませんが。</span><span class="sxs-lookup"><span data-stu-id="a1bd8-121">Message M0 is the incoming message and is therefore not created by BizTalk Server.</span></span> <span data-ttu-id="a1bd8-122">M1、M2 の受信ポートから出力メッセージは、メッセージがオーケストレーションからの出力メッセージと M3 は送信ポートから出力メッセージです。</span><span class="sxs-lookup"><span data-stu-id="a1bd8-122">Message M1 is the output message from the receive port, M2 is the output message from the orchestration, and M3 is the output message from the transmit port.</span></span>  
  
  <span data-ttu-id="a1bd8-123">式にこの情報を適用するには、次の結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="a1bd8-123">Applying this information to the formula gives the following result:</span></span>  
  
```  
[(3*150 bytes) + (6*230 bytes) + (0*0(52 bytes + 0) * 3,500,000]/1024/1024  
[(450 + 1380 + 0) * 3,500,000]/1024/1024 = 6108 MB ~ 5.96 GB per year  
```  
  
## <a name="messages-in-orchestrations-with-a-single-promoted-property"></a><span data-ttu-id="a1bd8-124">1 つ昇格させたプロパティを使用してオーケストレーション内のメッセージ</span><span class="sxs-lookup"><span data-stu-id="a1bd8-124">Messages in orchestrations with a single promoted property</span></span>  
 <span data-ttu-id="a1bd8-125">これで、先ほどの例のように、このシナリオの 1 つのフィールドを昇格させてみましょう。</span><span class="sxs-lookup"><span data-stu-id="a1bd8-125">Now let's promote a single field in this scenario, as in the earlier example.</span></span> <span data-ttu-id="a1bd8-126">昇格させたプロパティは、約 10 バイトです。</span><span class="sxs-lookup"><span data-stu-id="a1bd8-126">The promoted property is approximately 10 bytes in size.</span></span> <span data-ttu-id="a1bd8-127">これで、式のようになります。</span><span class="sxs-lookup"><span data-stu-id="a1bd8-127">The equation now looks like this:</span></span>  
  
```  
[((3*150 bytes) + (6*230 bytes) + (1*3*(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(450 + 1380 + 186) * 3,500,000]/1024/1024 = 6729 MB ~ 6.57 GB per year  
```  
  
 <span data-ttu-id="a1bd8-128">サイズの 20 バイトである追加のプロパティを昇格させる必要がある場合、数式はこれのようになります。</span><span class="sxs-lookup"><span data-stu-id="a1bd8-128">If you need to promote an additional property that is 20 bytes in size, the formula now looks like this:</span></span>  
  
```  
[(3*150 bytes) + (6*230 bytes) + ((1*3*(52 bytes + 10 bytes) + (1*3*(52 bytes + 20 bytes)) * 3,500,000]/1024/1024  
[(450 + 1380 + 372) * 3,500,000]/1024/1024 = 7350 MB ~ 7.18 GB per year  
```  
  
## <a name="messages-in-orchestrations-with-message-body-tracking-activated"></a><span data-ttu-id="a1bd8-129">メッセージ本文の追跡でオーケストレーション内のメッセージがアクティブ化</span><span class="sxs-lookup"><span data-stu-id="a1bd8-129">Messages in orchestrations with message body tracking activated</span></span>  
 <span data-ttu-id="a1bd8-130">メッセージの追跡する場合は、必要な追加の領域の計算結果と同じです、結果、前述のシナリオまたは 50.1 GB で 1 年間。</span><span class="sxs-lookup"><span data-stu-id="a1bd8-130">If you want to accommodate message tracking, the result from calculating the additional space needed is identical to the result in the earlier scenario, or 50.1 GB per year.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1bd8-131">参照</span><span class="sxs-lookup"><span data-stu-id="a1bd8-131">See Also</span></span>  
 <span data-ttu-id="a1bd8-132">[追跡データベースのサイズにメッセージ変数を使用します。](../core/using-message-variables-to-size-the-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="a1bd8-132">[Using Message Variables to Size the Tracking Database](../core/using-message-variables-to-size-the-tracking-database.md) </span></span>  
 <span data-ttu-id="a1bd8-133">[メッセージ本文を追跡する追跡データベースのサイズ調整](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="a1bd8-133">[Sizing the Tracking Database to Track Message Bodies](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span></span>  
 <span data-ttu-id="a1bd8-134">[シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ調整](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span><span class="sxs-lookup"><span data-stu-id="a1bd8-134">[Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span></span>  
 <span data-ttu-id="a1bd8-135">[シナリオ 4:すべてのメッセージの追跡データベースのサイズ調整](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span><span class="sxs-lookup"><span data-stu-id="a1bd8-135">[Scenario 4: Sizing the Tracking Database for all Messages](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span></span>  
 [<span data-ttu-id="a1bd8-136">シナリオ 3:配布リストに送信されるメッセージの追跡データベースのサイズ調整</span><span class="sxs-lookup"><span data-stu-id="a1bd8-136">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)