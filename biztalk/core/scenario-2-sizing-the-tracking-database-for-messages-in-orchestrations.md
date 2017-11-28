---
title: "シナリオ 2: オーケストレーションでメッセージの追跡データベースのサイズ変更 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Tracking database, database size
ms.assetid: d1cfb8b9-d4e2-4069-8db3-18f72358652b
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62ea6e463dfb3a44e2628f57b632634d7a9bd212
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-2-sizing-the-tracking-database--for-messages-in-orchestrations"></a><span data-ttu-id="63652-102">シナリオ 2: オーケストレーションでメッセージの追跡データベースのサイズ変更</span><span class="sxs-lookup"><span data-stu-id="63652-102">Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations</span></span>
<span data-ttu-id="63652-103">オーケストレーションを含む例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="63652-103">Let's look at an example that includes an orchestration.</span></span> <span data-ttu-id="63652-104">次の図は、ビジネス プロセス全体を示しています。</span><span class="sxs-lookup"><span data-stu-id="63652-104">The following figure displays the entire business process.</span></span> <span data-ttu-id="63652-105">このシナリオでは、メッセージが BizTalk Server に格納され、オーケストレーションを通じて送信されます。メッセージは、オーケストレーション内で変更され、送信ポートを通じて送信されます。</span><span class="sxs-lookup"><span data-stu-id="63652-105">In this scenario, a message comes into BizTalk Server, is sent through an orchestration, is changed within the orchestration, and is then sent out through a send port.</span></span>  
  
 <span data-ttu-id="63652-106">![BizTalk Server メッセージ プロセス](../core/media/biztalk-server-message-process.gif "BizTalk_Server_Message_Process")</span><span class="sxs-lookup"><span data-stu-id="63652-106">![BizTalk Server message process](../core/media/biztalk-server-message-process.gif "BizTalk_Server_Message_Process")</span></span>  
  
 <span data-ttu-id="63652-107">**BizTalk Server メッセージ プロセス**</span><span class="sxs-lookup"><span data-stu-id="63652-107">**The BizTalk Server message process**</span></span>  
  
 <span data-ttu-id="63652-108">このシナリオに関するファクトの一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="63652-108">Here are some of the facts concerning this scenario:</span></span>  
  
-   <span data-ttu-id="63652-109">メッセージのサイズは、5 K です。</span><span class="sxs-lookup"><span data-stu-id="63652-109">The message size is 5K.</span></span>  
  
-   <span data-ttu-id="63652-110">私たちは任意のプロパティを昇格しません。</span><span class="sxs-lookup"><span data-stu-id="63652-110">We are not promoting any properties.</span></span>  
  
-   <span data-ttu-id="63652-111">1 年間に受信メッセージの数は、350万件です。</span><span class="sxs-lookup"><span data-stu-id="63652-111">The number of messages we receive in a year is 3.5 million.</span></span>  
  
-   <span data-ttu-id="63652-112">追跡は、すべてのイベントに対して有効になっています。</span><span class="sxs-lookup"><span data-stu-id="63652-112">Tracking is turned on for all events.</span></span> <span data-ttu-id="63652-113">このシナリオには、次の 6 つのイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="63652-113">There are six events in this scenario:</span></span>  
  
    -   <span data-ttu-id="63652-114">メッセージ M0 の受信</span><span class="sxs-lookup"><span data-stu-id="63652-114">Receipt of message M0</span></span>  
  
    -   <span data-ttu-id="63652-115">受信ポートからのメッセージ M1 の出力</span><span class="sxs-lookup"><span data-stu-id="63652-115">Output of message M1 from the receive port</span></span>  
  
    -   <span data-ttu-id="63652-116">オーケストレーションによるメッセージ M1 の受信</span><span class="sxs-lookup"><span data-stu-id="63652-116">Receipt of message M1 by the orchestration</span></span>  
  
    -   <span data-ttu-id="63652-117">オーケストレーションからのメッセージ M2 の出力</span><span class="sxs-lookup"><span data-stu-id="63652-117">Output of message M2 from the orchestration</span></span>  
  
    -   <span data-ttu-id="63652-118">送信ポートによるメッセージ M2 の受信</span><span class="sxs-lookup"><span data-stu-id="63652-118">Receipt of message M2 by the send port</span></span>  
  
    -   <span data-ttu-id="63652-119">送信パイプラインからのメッセージ M3 の出力</span><span class="sxs-lookup"><span data-stu-id="63652-119">Output of message M3 by the send pipeline</span></span>  
  
-   <span data-ttu-id="63652-120">このシナリオでは、3 つの追加メッセージが作成されます。</span><span class="sxs-lookup"><span data-stu-id="63652-120">Three additional messages are created in this scenario.</span></span> <span data-ttu-id="63652-121">メッセージ M0 は受信メッセージであり、BizTalk Server によって作成されるものではありません。</span><span class="sxs-lookup"><span data-stu-id="63652-121">Message M0 is the incoming message and is therefore not created by BizTalk Server.</span></span> <span data-ttu-id="63652-122">メッセージ M1 は、受信ポートからの出力メッセージです。メッセージ M2 は、オーケストレーションからの出力メッセージです。メッセージ M3 は、転送ポートからの出力メッセージです。</span><span class="sxs-lookup"><span data-stu-id="63652-122">Message M1 is the output message from the receive port, M2 is the output message from the orchestration, and M3 is the output message from the transmit port.</span></span>  
  
 <span data-ttu-id="63652-123">式にこの情報を適用するには、次の結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="63652-123">Applying this information to the formula gives the following result:</span></span>  
  
```  
[(3*150 bytes) + (6*230 bytes) + (0*0(52 bytes + 0) * 3,500,000]/1024/1024  
[(450 + 1380 + 0) * 3,500,000]/1024/1024 = 6108 MB ~ 5.96 GB per year  
```  
  
## <a name="messages-in-orchestrations-with-a-single-promoted-property"></a><span data-ttu-id="63652-124">オーケストレーション内のメッセージ (プロパティを 1 つ昇格した場合)</span><span class="sxs-lookup"><span data-stu-id="63652-124">Messages in orchestrations with a single promoted property</span></span>  
 <span data-ttu-id="63652-125">前述の例のように、このシナリオのフィールドを 1 つ昇格してみましょう。</span><span class="sxs-lookup"><span data-stu-id="63652-125">Now let's promote a single field in this scenario, as in the earlier example.</span></span> <span data-ttu-id="63652-126">昇格させるプロパティのサイズは、約 10 バイトです。</span><span class="sxs-lookup"><span data-stu-id="63652-126">The promoted property is approximately 10 bytes in size.</span></span> <span data-ttu-id="63652-127">次のような式のようになりました。</span><span class="sxs-lookup"><span data-stu-id="63652-127">The equation now looks like this:</span></span>  
  
```  
[((3*150 bytes) + (6*230 bytes) + (1*3*(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(450 + 1380 + 186) * 3,500,000]/1024/1024 = 6729 MB ~ 6.57 GB per year  
```  
  
 <span data-ttu-id="63652-128">サイズの 20 バイトである追加のプロパティを昇格させる必要がある場合、数式は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="63652-128">If you need to promote an additional property that is 20 bytes in size, the formula now looks like this:</span></span>  
  
```  
[(3*150 bytes) + (6*230 bytes) + ((1*3*(52 bytes + 10 bytes) + (1*3*(52 bytes + 20 bytes)) * 3,500,000]/1024/1024  
[(450 + 1380 + 372) * 3,500,000]/1024/1024 = 7350 MB ~ 7.18 GB per year  
```  
  
## <a name="messages-in-orchestrations-with-message-body-tracking-activated"></a><span data-ttu-id="63652-129">オーケストレーション内のメッセージ (メッセージ本文の追跡を有効にした場合)</span><span class="sxs-lookup"><span data-stu-id="63652-129">Messages in orchestrations with message body tracking activated</span></span>  
 <span data-ttu-id="63652-130">メッセージの追跡を行う場合、必要な追加領域の計算結果は、前述のシナリオの結果 (1 年ごとに 50.1 GB) と同じです。</span><span class="sxs-lookup"><span data-stu-id="63652-130">If you want to accommodate message tracking, the result from calculating the additional space needed is identical to the result in the earlier scenario, or 50.1 GB per year.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63652-131">参照</span><span class="sxs-lookup"><span data-stu-id="63652-131">See Also</span></span>  
 <span data-ttu-id="63652-132">[追跡データベースのサイズをメッセージ変数を使用](../core/using-message-variables-to-size-the-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="63652-132">[Using Message Variables to Size the Tracking Database](../core/using-message-variables-to-size-the-tracking-database.md) </span></span>  
 <span data-ttu-id="63652-133">[メッセージ本文を追跡する追跡データベースのサイズ変更](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="63652-133">[Sizing the Tracking Database to Track Message Bodies](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span></span>  
 <span data-ttu-id="63652-134">[シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ変更](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span><span class="sxs-lookup"><span data-stu-id="63652-134">[Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span></span>  
 <span data-ttu-id="63652-135">[シナリオ 4: すべてのメッセージの追跡データベースのサイズ変更](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span><span class="sxs-lookup"><span data-stu-id="63652-135">[Scenario 4: Sizing the Tracking Database for all Messages](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span></span>  
 [<span data-ttu-id="63652-136">シナリオ 3: 同報リストに送信されるメッセージの追跡データベースのサイズ変更</span><span class="sxs-lookup"><span data-stu-id="63652-136">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)