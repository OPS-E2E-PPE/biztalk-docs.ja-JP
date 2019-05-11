---
title: シナリオ 1:単純な BizTalk メッセージの追跡データベースのサイズ調整 |Microsoft Docs
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
ms.openlocfilehash: e559869bfb62439bb5f83a97b528ecf6960e123f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308620"
---
# <a name="scenario-1-sizing-the-tracking-database--for-simple-biztalk-messages"></a><span data-ttu-id="cd8d3-102">シナリオ 1:単純な BizTalk メッセージの追跡データベースのサイズ調整</span><span class="sxs-lookup"><span data-stu-id="cd8d3-102">Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages</span></span>
<span data-ttu-id="cd8d3-103">次の図に、単純な BizTalk Server メッセージは BizTalk Server との間メッセージのすべての変換を実行せずに渡します。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-103">In the following figure, a simple BizTalk Server message passes in and out of BizTalk Server without undergoing any message transformation.</span></span>  
  
 <span data-ttu-id="cd8d3-104">![単純な BizTalk Server メッセージ&#45;変換なし](../core/media/simple-bts-message.gif "Simple_BTS_Message")</span><span class="sxs-lookup"><span data-stu-id="cd8d3-104">![Simple BizTalk Server message &#45; no transformation](../core/media/simple-bts-message.gif "Simple_BTS_Message")</span></span>  
  
 <span data-ttu-id="cd8d3-105">**単純な BizTalk Server メッセージ - 変換なし**</span><span class="sxs-lookup"><span data-stu-id="cd8d3-105">**A simple BizTalk Server message - no transformation**</span></span>  
  
 <span data-ttu-id="cd8d3-106">前のセクションで、数式を適用する前に、このシナリオの詳細については、いくつかファクトを収集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-106">Before you apply the formula in the previous section, you will need to gather some facts about this scenario.</span></span> <span data-ttu-id="cd8d3-107">この例で、次使用します。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-107">In this example, we use the following:</span></span>  
  
- <span data-ttu-id="cd8d3-108">メッセージ サイズは、5 K です。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-108">The message size is 5K.</span></span>  
  
- <span data-ttu-id="cd8d3-109">プロパティは昇格なし。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-109">No properties will be promoted.</span></span>  
  
- <span data-ttu-id="cd8d3-110">1 年間に受信したメッセージの数は、350万です。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-110">The number of messages you receive in a year is 3.5 million.</span></span>  
  
- <span data-ttu-id="cd8d3-111">すべてのイベントの追跡がオンになっているとします。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-111">Tracking is turned on for all events.</span></span> <span data-ttu-id="cd8d3-112">このシナリオには、4 つのイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-112">There are four events in this scenario.</span></span> <span data-ttu-id="cd8d3-113">イベントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-113">The events are:</span></span>  
  
  -   <span data-ttu-id="cd8d3-114">メッセージ M0 の受信</span><span class="sxs-lookup"><span data-stu-id="cd8d3-114">Receipt of message M0</span></span>  
  
  -   <span data-ttu-id="cd8d3-115">受信ポートからメッセージ M1 の出力</span><span class="sxs-lookup"><span data-stu-id="cd8d3-115">Output of message M1 from the receive port</span></span>  
  
  -   <span data-ttu-id="cd8d3-116">送信パイプラインによるメッセージ M1 の受信</span><span class="sxs-lookup"><span data-stu-id="cd8d3-116">Receipt of message M1 by the transmit pipeline</span></span>  
  
  -   <span data-ttu-id="cd8d3-117">送信パイプラインによるメッセージ M2 の出力</span><span class="sxs-lookup"><span data-stu-id="cd8d3-117">Output of message M2 by the send pipeline</span></span>  
  
- <span data-ttu-id="cd8d3-118">このシナリオでは、2 つの追加メッセージが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-118">Two additional messages are created in this scenario.</span></span> <span data-ttu-id="cd8d3-119">メッセージ M0 は受信メッセージを BizTalk Server によって作成されませんが。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-119">Message M0 is the incoming message and is therefore not created by BizTalk Server.</span></span> <span data-ttu-id="cd8d3-120">メッセージ M1 は受信ポートから出力メッセージと M2 は送信ポートから出力します。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-120">Message M1 is the output message from the receive port and M2 is the output from the transmit port.</span></span> <span data-ttu-id="cd8d3-121">M1 と M2 は、BizTalk Server によって作成されます。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-121">M1 and M2 are created by BizTalk Server.</span></span>  
  
  <span data-ttu-id="cd8d3-122">式にこの情報を適用することで、次は。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-122">Applying this information to the formula gives the following:</span></span>  
  
```  
[(5*252 bytes) + (10*182 bytes) + (0*5(40 bytes + 0) * 3,500,000]/1024/1024  
[(1620 + 1820 + 0) * 3,500,000]/1024/1024 = 10280.61 MB ~ 10.04 GB per year  
```  
  
## <a name="messages-with-a-single-promoted-property"></a><span data-ttu-id="cd8d3-123">1 つの昇格させたプロパティを持つメッセージ</span><span class="sxs-lookup"><span data-stu-id="cd8d3-123">Messages with a single promoted property</span></span>  
 <span data-ttu-id="cd8d3-124">この例で、シナリオに 1 つのファクトを追加してみましょう。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-124">Let's take another look at this example and add one additional fact to the scenario.</span></span> <span data-ttu-id="cd8d3-125">元のメッセージのサイズが約 10 バイト、1 つのフィールドを昇格するには。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-125">You want to promote a single field, approximately 10 bytes in size, from the original message.</span></span> <span data-ttu-id="cd8d3-126">昇格させたフィールドの最大サイズは 256 文字、つまり約 256 バイト (512 バイト Unicode 文字の場合) です。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-126">The maximum size of a promoted field is 256 characters, or approximately 256 bytes (512 bytes if the characters are Unicode).</span></span>  
  
 <span data-ttu-id="cd8d3-127">この追加のファクトをこれで、式は次のようです。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-127">With this additional fact, the equation now appears as follows:</span></span>  
  
```  
[(2*150 bytes) + (4*230 bytes) + (1*2(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(300 + 920 + 124) * 3,500,000]/1024/1024 = 4486 MB ~ 4.38 GB per year  
```  
  
 <span data-ttu-id="cd8d3-128">サイズが 10 バイトである追加のフィールドを昇格する場合、式は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-128">If you wanted to promote an additional field that is 10 bytes in size, the equation would be:</span></span>  
  
```  
[(2*150 bytes) + (4*230 bytes) + ((1*2*(52 bytes + 10 bytes) + (1*2*(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(300 + 920 + 248) * 3,500,000]/1024/1024 = 4899 MB ~ 4.78 GB per year  
```  
  
 <span data-ttu-id="cd8d3-129">ご覧のとおり、このシナリオでは、1 つの 10 バイト プロパティを昇格する場合、追加の 333.79 MB が追加されます ~ BizTalk 追跡データベースのサイズを 1 年あたり 0.33 GB。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-129">As you can see, if you promote a single 10-byte property in this scenario, it will add an additional 333.79 MB ~ 0.33 GB per year to the size of the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="cd8d3-130">10 バイトの 2 つのプロパティの昇格は追加 667.58 MB の追加約 0.65 GB、BizTalk 追跡データベースのサイズを 1 年あたり追加の空き領域。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-130">Promoting two 10-byte properties will add an additional 667.58 MB ~ 0.65 GB of additional space per year to the size of the BizTalk Tracking database.</span></span>  
  
## <a name="messages-with-message-body-tracking-activated"></a><span data-ttu-id="cd8d3-131">メッセージがメッセージ本文の追跡をアクティブ化</span><span class="sxs-lookup"><span data-stu-id="cd8d3-131">Messages with message body tracking activated</span></span>  
 <span data-ttu-id="cd8d3-132">この例でも仮定メッセージ本文の追跡をアクティブ化する予定です。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-132">In this example, let us also assume that we are planning on activating message body tracking.</span></span> <span data-ttu-id="cd8d3-133">前のセクションに示すように、メッセージ追跡用に 2 番目の式を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-133">We will need to add the second equation for message tracking, shown in the previous section.</span></span> <span data-ttu-id="cd8d3-134">式は、この例では、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-134">The equation will look like the following for this example:</span></span>  
  
```  
[3,500,000 * 4 * 5KB]/1024 = 68359.375 MB ~ 66.75 GB per year  
  
```  
  
 <span data-ttu-id="cd8d3-135">2 つの式の結果を追加すると、BizTalk 追跡データベースが、1 年あたり約 54.48 GB をことに拡張されますを推定できます。</span><span class="sxs-lookup"><span data-stu-id="cd8d3-135">By adding the results of the two equations, we can estimate that the BizTalk Tracking database will grow approximately 54.48 GB to 54.88 GB per year.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd8d3-136">参照</span><span class="sxs-lookup"><span data-stu-id="cd8d3-136">See Also</span></span>  
 <span data-ttu-id="cd8d3-137">[追跡データベースのサイズにメッセージ変数を使用します。](../core/using-message-variables-to-size-the-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="cd8d3-137">[Using Message Variables to Size the Tracking Database](../core/using-message-variables-to-size-the-tracking-database.md) </span></span>  
 <span data-ttu-id="cd8d3-138">[メッセージ本文を追跡する追跡データベースのサイズ調整](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="cd8d3-138">[Sizing the Tracking Database to Track Message Bodies](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span></span>  
 <span data-ttu-id="cd8d3-139">[シナリオ 2: オーケストレーション内のメッセージの追跡データベースのサイズ調整](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="cd8d3-139">[Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span></span>  
 <span data-ttu-id="cd8d3-140">[シナリオ 4:すべてのメッセージの追跡データベースのサイズ調整](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span><span class="sxs-lookup"><span data-stu-id="cd8d3-140">[Scenario 4: Sizing the Tracking Database for all Messages](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span></span>  
 [<span data-ttu-id="cd8d3-141">シナリオ 3:配布リストに送信されるメッセージの追跡データベースのサイズ調整</span><span class="sxs-lookup"><span data-stu-id="cd8d3-141">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)