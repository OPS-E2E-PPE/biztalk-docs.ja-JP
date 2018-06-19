---
title: 'シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ変更 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: 5b8fed48-d9c9-4d1f-a320-d3e23b8b1ec9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b9c99c99485e34f95c6f6a75b86170d73678518
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269722"
---
# <a name="scenario-1-sizing-the-tracking-database--for-simple-biztalk-messages"></a><span data-ttu-id="9c598-102">シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ変更</span><span class="sxs-lookup"><span data-stu-id="9c598-102">Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages</span></span>
<span data-ttu-id="9c598-103">次の図は、BizTalk Server が、メッセージを一切変換せずに単純に送受信するようすを示したものです。</span><span class="sxs-lookup"><span data-stu-id="9c598-103">In the following figure, a simple BizTalk Server message passes in and out of BizTalk Server without undergoing any message transformation.</span></span>  
  
 <span data-ttu-id="9c598-104">![単純な BizTalk Server メッセージ &#45;変換なし](../core/media/simple-bts-message.gif "Simple_BTS_Message")</span><span class="sxs-lookup"><span data-stu-id="9c598-104">![Simple BizTalk Server message &#45; no transformation](../core/media/simple-bts-message.gif "Simple_BTS_Message")</span></span>  
  
 <span data-ttu-id="9c598-105">**単純な BizTalk Server メッセージ - 変換なし**</span><span class="sxs-lookup"><span data-stu-id="9c598-105">**A simple BizTalk Server message - no transformation**</span></span>  
  
 <span data-ttu-id="9c598-106">このシナリオについて前セクションの式を適用する前に、いくつかのファクトを収集しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c598-106">Before you apply the formula in the previous section, you will need to gather some facts about this scenario.</span></span> <span data-ttu-id="9c598-107">この例では、次のファクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="9c598-107">In this example, we use the following:</span></span>  
  
-   <span data-ttu-id="9c598-108">メッセージのサイズは、5 K です。</span><span class="sxs-lookup"><span data-stu-id="9c598-108">The message size is 5K.</span></span>  
  
-   <span data-ttu-id="9c598-109">プロパティの昇格は行われません。</span><span class="sxs-lookup"><span data-stu-id="9c598-109">No properties will be promoted.</span></span>  
  
-   <span data-ttu-id="9c598-110">1 年に受け取るメッセージ数は、350 万件です。</span><span class="sxs-lookup"><span data-stu-id="9c598-110">The number of messages you receive in a year is 3.5 million.</span></span>  
  
-   <span data-ttu-id="9c598-111">追跡は、すべてのイベントに対して有効になっています。</span><span class="sxs-lookup"><span data-stu-id="9c598-111">Tracking is turned on for all events.</span></span> <span data-ttu-id="9c598-112">このシナリオには、次の 4 つのイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="9c598-112">There are four events in this scenario.</span></span> <span data-ttu-id="9c598-113">イベントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9c598-113">The events are:</span></span>  
  
    -   <span data-ttu-id="9c598-114">メッセージ M0 の受信</span><span class="sxs-lookup"><span data-stu-id="9c598-114">Receipt of message M0</span></span>  
  
    -   <span data-ttu-id="9c598-115">受信ポートからのメッセージ M1 の出力</span><span class="sxs-lookup"><span data-stu-id="9c598-115">Output of message M1 from the receive port</span></span>  
  
    -   <span data-ttu-id="9c598-116">送信パイプラインによるメッセージ M1 の受信</span><span class="sxs-lookup"><span data-stu-id="9c598-116">Receipt of message M1 by the transmit pipeline</span></span>  
  
    -   <span data-ttu-id="9c598-117">送信パイプラインからのメッセージ M2 の出力</span><span class="sxs-lookup"><span data-stu-id="9c598-117">Output of message M2 by the send pipeline</span></span>  
  
-   <span data-ttu-id="9c598-118">このシナリオでは、2 つの追加メッセージが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9c598-118">Two additional messages are created in this scenario.</span></span> <span data-ttu-id="9c598-119">メッセージ M0 は受信メッセージであり、BizTalk Server によって作成されるものではありません。</span><span class="sxs-lookup"><span data-stu-id="9c598-119">Message M0 is the incoming message and is therefore not created by BizTalk Server.</span></span> <span data-ttu-id="9c598-120">M1 は受信ポートからの出力メッセージです。M2 は送信ポートからの出力メッセージです。</span><span class="sxs-lookup"><span data-stu-id="9c598-120">Message M1 is the output message from the receive port and M2 is the output from the transmit port.</span></span> <span data-ttu-id="9c598-121">M1 と M2 は BizTalk Server によって作成されます。</span><span class="sxs-lookup"><span data-stu-id="9c598-121">M1 and M2 are created by BizTalk Server.</span></span>  
  
 <span data-ttu-id="9c598-122">この情報を式に適用すると、結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9c598-122">Applying this information to the formula gives the following:</span></span>  
  
```  
[(5*252 bytes) + (10*182 bytes) + (0*5(40 bytes + 0) * 3,500,000]/1024/1024  
[(1620 + 1820 + 0) * 3,500,000]/1024/1024 = 10280.61 MB ~ 10.04 GB per year  
```  
  
## <a name="messages-with-a-single-promoted-property"></a><span data-ttu-id="9c598-123">メッセージのプロパティを 1 つ昇格させた場合</span><span class="sxs-lookup"><span data-stu-id="9c598-123">Messages with a single promoted property</span></span>  
 <span data-ttu-id="9c598-124">この例のシナリオに、もう 1 つファクトを追加してみることにします。</span><span class="sxs-lookup"><span data-stu-id="9c598-124">Let's take another look at this example and add one additional fact to the scenario.</span></span> <span data-ttu-id="9c598-125">元のメッセージのフィールド (サイズは約 10 バイト) を 1 つ昇格させます。</span><span class="sxs-lookup"><span data-stu-id="9c598-125">You want to promote a single field, approximately 10 bytes in size, from the original message.</span></span> <span data-ttu-id="9c598-126">昇格後のフィールドの最大サイズは 256 文字、つまり約 256 バイトです (Unicode 文字の場合は 512 バイト)。</span><span class="sxs-lookup"><span data-stu-id="9c598-126">The maximum size of a promoted field is 256 characters, or approximately 256 bytes (512 bytes if the characters are Unicode).</span></span>  
  
 <span data-ttu-id="9c598-127">このファクトを追加した場合、式は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9c598-127">With this additional fact, the equation now appears as follows:</span></span>  
  
```  
[(2*150 bytes) + (4*230 bytes) + (1*2(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(300 + 920 + 124) * 3,500,000]/1024/1024 = 4486 MB ~ 4.38 GB per year  
```  
  
 <span data-ttu-id="9c598-128">サイズが 10 バイトのフィールドをさらにもう 1 つ昇格させた場合、式は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9c598-128">If you wanted to promote an additional field that is 10 bytes in size, the equation would be:</span></span>  
  
```  
[(2*150 bytes) + (4*230 bytes) + ((1*2*(52 bytes + 10 bytes) + (1*2*(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(300 + 920 + 248) * 3,500,000]/1024/1024 = 4899 MB ~ 4.78 GB per year  
```  
  
 <span data-ttu-id="9c598-129">この結果から、このシナリオでは、単一の 10 バイト プロパティを昇格させた場合、BizTalk 追跡データベースのサイズに加え、1 年あたり 333.79 MB (約 0.33 GB) が追加で必要になることがわかります。</span><span class="sxs-lookup"><span data-stu-id="9c598-129">As you can see, if you promote a single 10-byte property in this scenario, it will add an additional 333.79 MB ~ 0.33 GB per year to the size of the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="9c598-130">同様に、10 バイトのプロパティを 2 つ昇格させた場合は、BizTalk 追跡データベースのサイズに加え、1 年あたり 667.58 MB (約 0.65 GB) の容量が追加で必要になります。</span><span class="sxs-lookup"><span data-stu-id="9c598-130">Promoting two 10-byte properties will add an additional 667.58 MB ~ 0.65 GB of additional space per year to the size of the BizTalk Tracking database.</span></span>  
  
## <a name="messages-with-message-body-tracking-activated"></a><span data-ttu-id="9c598-131">メッセージ本文の追跡を有効にした場合</span><span class="sxs-lookup"><span data-stu-id="9c598-131">Messages with message body tracking activated</span></span>  
 <span data-ttu-id="9c598-132">この例で、さらに、メッセージ本文の追跡を有効にした場合を想定してみましょう。</span><span class="sxs-lookup"><span data-stu-id="9c598-132">In this example, let us also assume that we are planning on activating message body tracking.</span></span> <span data-ttu-id="9c598-133">メッセージ追跡用に、前のセクションで取り上げたもう 1 つの式を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c598-133">We will need to add the second equation for message tracking, shown in the previous section.</span></span> <span data-ttu-id="9c598-134">この場合は、次のような式になります。</span><span class="sxs-lookup"><span data-stu-id="9c598-134">The equation will look like the following for this example:</span></span>  
  
```  
[3,500,000 * 4 * 5KB]/1024 = 68359.375 MB ~ 66.75 GB per year  
  
```  
  
 <span data-ttu-id="9c598-135">2 つの式の結果を加算することにより、BizTalk 追跡データベースのサイズは、年間で約 54.48 GB ～ 54.88 GB 増加すると見積もることができます。</span><span class="sxs-lookup"><span data-stu-id="9c598-135">By adding the results of the two equations, we can estimate that the BizTalk Tracking database will grow approximately 54.48 GB to 54.88 GB per year.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c598-136">参照</span><span class="sxs-lookup"><span data-stu-id="9c598-136">See Also</span></span>  
 <span data-ttu-id="9c598-137">[追跡データベースのサイズをメッセージ変数を使用](../core/using-message-variables-to-size-the-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="9c598-137">[Using Message Variables to Size the Tracking Database](../core/using-message-variables-to-size-the-tracking-database.md) </span></span>  
 <span data-ttu-id="9c598-138">[メッセージ本文を追跡する追跡データベースのサイズ変更](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="9c598-138">[Sizing the Tracking Database to Track Message Bodies](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span></span>  
 <span data-ttu-id="9c598-139">[シナリオ 2: オーケストレーションでメッセージの追跡データベースのサイズ変更](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="9c598-139">[Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span></span>  
 <span data-ttu-id="9c598-140">[シナリオ 4: すべてのメッセージの追跡データベースのサイズ変更](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span><span class="sxs-lookup"><span data-stu-id="9c598-140">[Scenario 4: Sizing the Tracking Database for all Messages](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span></span>  
 [<span data-ttu-id="9c598-141">シナリオ 3: 同報リストに送信されるメッセージの追跡データベースのサイズ変更</span><span class="sxs-lookup"><span data-stu-id="9c598-141">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)