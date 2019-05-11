---
title: 'シナリオ 3: 配布リストにメッセージが出力を送信の追跡データベースのサイズ調整 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: bc6e0da0-46d1-42d6-8ec9-29a28719fbb3
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b757f262077bbd4185cda312f479d08ef7a3229c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308499"
---
# <a name="scenario-3-sizing-the-tracking-database--for-messages-sent-out-to-distribution-lists"></a><span data-ttu-id="501ea-102">シナリオ 3: 配布リストに送信されるメッセージの追跡データベースのサイズ調整</span><span class="sxs-lookup"><span data-stu-id="501ea-102">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>
<span data-ttu-id="501ea-103">次の図では、オーケストレーション処理の適用し、オーケストレーション内で変更が、同報リストを通じて複数の送信ポートに送信し、メッセージがあります。</span><span class="sxs-lookup"><span data-stu-id="501ea-103">In the following figure, you have a message that proceeds through an orchestration, is changed within the orchestration, and is then sent out to several different send ports through a distribution list.</span></span>  
  
 <span data-ttu-id="501ea-104">![複数のポートにオーケストレーションでメッセージを](../core/media/biztalk-server-message-orch-multiple-ports.gif "BizTalk_Server_message_orch_multiple_ports")</span><span class="sxs-lookup"><span data-stu-id="501ea-104">![Message through an orchestration to multiple ports](../core/media/biztalk-server-message-orch-multiple-ports.gif "BizTalk_Server_message_orch_multiple_ports")</span></span>  
  
 <span data-ttu-id="501ea-105">**オーケストレーション処理の適用し、複数のポートに送信するメッセージを BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="501ea-105">**BizTalk Server message that proceeds through an orchestration and is sent out to several different ports**</span></span>  
  
 <span data-ttu-id="501ea-106">このシナリオに関するファクトの一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="501ea-106">Here are some of the facts concerning this scenario:</span></span>  
  
- <span data-ttu-id="501ea-107">メッセージ サイズは、10 K です。</span><span class="sxs-lookup"><span data-stu-id="501ea-107">The message size is 10K.</span></span>  
  
- <span data-ttu-id="501ea-108">任意のプロパティは昇格しません。</span><span class="sxs-lookup"><span data-stu-id="501ea-108">You are not promoting any properties.</span></span>  
  
- <span data-ttu-id="501ea-109">1 年間に受信したメッセージの数は、350万です。</span><span class="sxs-lookup"><span data-stu-id="501ea-109">The number of messages you receive in a year is 3.5 million.</span></span>  
  
- <span data-ttu-id="501ea-110">すべてのイベントの追跡がオンになっているとします。</span><span class="sxs-lookup"><span data-stu-id="501ea-110">Tracking is turned on for all events.</span></span> <span data-ttu-id="501ea-111">このシナリオには、5 つのイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="501ea-111">There are five events in this scenario:</span></span>  
  
  -   <span data-ttu-id="501ea-112">メッセージ M0 の受信</span><span class="sxs-lookup"><span data-stu-id="501ea-112">Receipt of message M0</span></span>  
  
  -   <span data-ttu-id="501ea-113">受信ポートからメッセージ M1 の出力</span><span class="sxs-lookup"><span data-stu-id="501ea-113">Output of message M1 from the receive port</span></span>  
  
  -   <span data-ttu-id="501ea-114">送信ポートによるメッセージ M3 の出力</span><span class="sxs-lookup"><span data-stu-id="501ea-114">Output of message M3 by the send port</span></span>  
  
  -   <span data-ttu-id="501ea-115">送信ポートによるメッセージ M4 の出力</span><span class="sxs-lookup"><span data-stu-id="501ea-115">Output of message M4 by the send port</span></span>  
  
  -   <span data-ttu-id="501ea-116">送信ポートによるメッセージ M5 の出力</span><span class="sxs-lookup"><span data-stu-id="501ea-116">Output of message M5 by the send port</span></span>  
  
  <span data-ttu-id="501ea-117">式にこの情報を適用するには、次の。</span><span class="sxs-lookup"><span data-stu-id="501ea-117">Applying this information to the equation gives the following:</span></span>  
  
```  
[(5*252 bytes) + (10*182 bytes) + (0*5(40 bytes + 0) * 3,500,000]/1024/1024  
[(1620 + 1820 + 0) * 3,500,000]/1024/1024 = 10280.61 MB ~ 10.04 GB per year  
```  
  
## <a name="messages-in-an-orchestration-that-are-sent-out-to-a-distribution-list-with-a-single-promoted-property"></a><span data-ttu-id="501ea-118">オーケストレーション内の 1 つ昇格させたプロパティを使用して、配布リストに送信されるメッセージ</span><span class="sxs-lookup"><span data-stu-id="501ea-118">Messages in an orchestration that are sent out to a distribution list with a single promoted property</span></span>  
 <span data-ttu-id="501ea-119">この例では、前述のシナリオで行ったようは、1 つのプロパティ、サイズ、約 10 バイトみましょうを昇格させます。</span><span class="sxs-lookup"><span data-stu-id="501ea-119">In this example, let's promote a single property, approximately 10 bytes in size, as we did in an earlier scenario.</span></span> <span data-ttu-id="501ea-120">これで、式のようになります。</span><span class="sxs-lookup"><span data-stu-id="501ea-120">The equation now looks like this:</span></span>  
  
```  
[((5*150 bytes) + (10*230 bytes) + (1*5(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(750 + 2300 + 260) * 3,500,000]/1024/1024 = 11048 MB ~ 10.79 GB per year  
```  
  
 <span data-ttu-id="501ea-121">サイズの 20 バイトである追加のプロパティを昇格する場合、式を今すぐようになります。</span><span class="sxs-lookup"><span data-stu-id="501ea-121">If we promote an additional property that is 20 bytes in size the equation now looks like this:</span></span>  
  
```  
[((5*150 bytes) + (10*230 bytes) + ((1*5(52 bytes + 10 bytes) + (1*5(52 bytes + 20 bytes)) * 3,500,000]/1024/1024  
[(750 + 2300 + 670) * 3,500,000]/1024/1024 = 12417 MB ~ 12.13 GB per year  
```  
  
## <a name="messages-in-an-orchestration-that-are-sent-out-to-a-distribution-list-with-message-body-tracking-activated"></a><span data-ttu-id="501ea-122">送信されるオーケストレーション内のメッセージの配布リストをメッセージ本文の追跡とアクティブ化</span><span class="sxs-lookup"><span data-stu-id="501ea-122">Messages in an orchestration that are sent out to a distribution list with message body tracking activated</span></span>  
 <span data-ttu-id="501ea-123">メッセージの追跡する場合、式は次の例を次のようになります。</span><span class="sxs-lookup"><span data-stu-id="501ea-123">If you want to accommodate message tracking, the equation will look like the following for this example:</span></span>  
  
```  
[3,500,000 * 6 * 5KB]/1024 = 102539.06 MB ~ 100.14 GB per year  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="501ea-124">参照</span><span class="sxs-lookup"><span data-stu-id="501ea-124">See Also</span></span>  
 <span data-ttu-id="501ea-125">[追跡データベースのサイズにメッセージ変数を使用します。](../core/using-message-variables-to-size-the-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="501ea-125">[Using Message Variables to Size the Tracking Database](../core/using-message-variables-to-size-the-tracking-database.md) </span></span>  
 <span data-ttu-id="501ea-126">[メッセージ本文を追跡する追跡データベースのサイズ調整](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="501ea-126">[Sizing the Tracking Database to Track Message Bodies](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span></span>  
 <span data-ttu-id="501ea-127">[シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ調整](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span><span class="sxs-lookup"><span data-stu-id="501ea-127">[Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span></span>  
 <span data-ttu-id="501ea-128">[シナリオ 2: オーケストレーション内のメッセージの追跡データベースのサイズ調整](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="501ea-128">[Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span></span>  
 [<span data-ttu-id="501ea-129">シナリオ 4:すべてのメッセージの追跡データベースのサイズ調整</span><span class="sxs-lookup"><span data-stu-id="501ea-129">Scenario 4: Sizing the Tracking Database for all Messages</span></span>](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)