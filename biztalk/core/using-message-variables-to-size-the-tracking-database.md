---
title: メッセージ変数を使用して、追跡データベースのサイズを |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message variables [Tracking database], CMsgs
- message variables [Tracking database], Events
- message variables [Tracking database], Properties
- Tracking database, database size
- message variables [Tracking database], Nserv
- message variables [Tracking database], Msgs
- message variables [Tracking database], PropSize
- message variables [Tracking database]
- message variables [Tracking database], MsgSize
- message variables [Tracking database], MsgNum
- Tracking database, messages
ms.assetid: 2d31ae25-3d16-4002-b5a5-dca25e764ecd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5418cdf79499302e6127db7fb66f108825a0d8c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287842"
---
# <a name="using-message-variables-to-size-the-tracking-database"></a><span data-ttu-id="fc336-102">メッセージ変数を使用して追跡データベースのサイズを求める方法</span><span class="sxs-lookup"><span data-stu-id="fc336-102">Using Message Variables to Size the Tracking Database</span></span>
<span data-ttu-id="fc336-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、BizTalk の追跡 (BizTalkDTADb) データベースのサイズが一定期間経過後にどのくらいのサイズになるかを、各種の変数を使って求めることができます。</span><span class="sxs-lookup"><span data-stu-id="fc336-103">In Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can use a number of variables to determine how large the BizTalk Tracking (BizTalkDTADb) database will become over a given period of time.</span></span> <span data-ttu-id="fc336-104">これらの変数を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fc336-104">These variables are:</span></span>  
  
-   <span data-ttu-id="fc336-105">使用パイプライン数</span><span class="sxs-lookup"><span data-stu-id="fc336-105">Number of pipelines used</span></span>  
  
-   <span data-ttu-id="fc336-106">関連するオーケストレーション数</span><span class="sxs-lookup"><span data-stu-id="fc336-106">Number of orchestrations involved</span></span>  
  
-   <span data-ttu-id="fc336-107">生成されたイベント数</span><span class="sxs-lookup"><span data-stu-id="fc336-107">Number of events generated</span></span>  
  
-   <span data-ttu-id="fc336-108">追跡対象のメッセージ プロパティ数</span><span class="sxs-lookup"><span data-stu-id="fc336-108">Number of message properties tracked</span></span>  
  
-   <span data-ttu-id="fc336-109">追加的に作成されるメッセージ数</span><span class="sxs-lookup"><span data-stu-id="fc336-109">Number of additional messages created</span></span>  
  
-   <span data-ttu-id="fc336-110">指定の期間に受け取ったメッセージの推定数</span><span class="sxs-lookup"><span data-stu-id="fc336-110">Estimated number of messages received in the specified timeframe</span></span>  
  
 <span data-ttu-id="fc336-111">BizTalk の追跡データベースのサイズを見積もるための式はそれほど複雑なものではありません。ただし、この式は、BizTalk Server 環境で使用されるすべての受信/送信メッセージ プロセスに対して適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc336-111">While the equation you use to estimate the size of the BizTalk Tracking database is straightforward, you must apply it to each incoming and outgoing message process that uses the BizTalk Server implementation.</span></span> <span data-ttu-id="fc336-112">つまり、個々のメッセージ シナリオに対してこの式を適用し、その結果を総計して初めて、最終的な推定データベース サイズを得ることができます。</span><span class="sxs-lookup"><span data-stu-id="fc336-112">In other words, you will need to apply this equation for every distinct message scenario and then add up the results to obtain the final estimated database size.</span></span> <span data-ttu-id="fc336-113">このドキュメントでは、次の 2 つのシナリオを想定しています。</span><span class="sxs-lookup"><span data-stu-id="fc336-113">In this document we will look at two scenarios.</span></span> <span data-ttu-id="fc336-114">シナリオでは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fc336-114">The scenarios are:</span></span>  
  
1.  <span data-ttu-id="fc336-115">メッセージを受信し、そのメッセージを変換して、結果のメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="fc336-115">Receiving a message, transforming the message, and then sending the resulting message</span></span>  
  
2.  <span data-ttu-id="fc336-116">メッセージを受信し、そのメッセージを使ってビジネス プロセスを実行して、結果のメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="fc336-116">Receiving a message, running a business process using the message, and then sending the resulting message.</span></span>  
  
 <span data-ttu-id="fc336-117">どちらも、BizTalk Server 環境で想定されるシナリオですが、追跡データの量はシナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="fc336-117">Both of these scenarios may be present in a BizTalk Server installation, and each scenario generates a different amount of tracking data.</span></span> <span data-ttu-id="fc336-118">BizTalk Server 環境で生成される総追跡データは、これらすべてのシナリオを合計した値になります。</span><span class="sxs-lookup"><span data-stu-id="fc336-118">The total tracking data generated for the BizTalk Server installation is the sum of all the scenarios.</span></span>  
  
 <span data-ttu-id="fc336-119">式に用いられている変数には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="fc336-119">The following are some variables used in the equation:</span></span>  
  
|<span data-ttu-id="fc336-120">変数</span><span class="sxs-lookup"><span data-stu-id="fc336-120">Variable</span></span>|<span data-ttu-id="fc336-121">Description</span><span class="sxs-lookup"><span data-stu-id="fc336-121">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="fc336-122">**Nserv**</span><span class="sxs-lookup"><span data-stu-id="fc336-122">**Nserv**</span></span>|<span data-ttu-id="fc336-123">サービス数 (パイプライン数 + オーケストレーション数)</span><span class="sxs-lookup"><span data-stu-id="fc336-123">Number of services (number of pipelines + number of orchestrations)</span></span>|  
|<span data-ttu-id="fc336-124">**イベント**</span><span class="sxs-lookup"><span data-stu-id="fc336-124">**Events**</span></span>|<span data-ttu-id="fc336-125">生成されるメッセージ イベント数</span><span class="sxs-lookup"><span data-stu-id="fc336-125">Number of generated message events</span></span>|  
|<span data-ttu-id="fc336-126">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="fc336-126">**Properties**</span></span>|<span data-ttu-id="fc336-127">追跡対象のメッセージ プロパティ数</span><span class="sxs-lookup"><span data-stu-id="fc336-127">Number of message properties tracked</span></span>|  
|<span data-ttu-id="fc336-128">**PropSize**</span><span class="sxs-lookup"><span data-stu-id="fc336-128">**PropSize**</span></span>|<span data-ttu-id="fc336-129">昇格させたプロパティ (フィールド) のサイズ (バイト単位)</span><span class="sxs-lookup"><span data-stu-id="fc336-129">Size (in bytes) of the promoted property (field)</span></span>|  
|<span data-ttu-id="fc336-130">**CMsgs**</span><span class="sxs-lookup"><span data-stu-id="fc336-130">**CMsgs**</span></span>|<span data-ttu-id="fc336-131">1 つの受信メッセージにつき追加的に作成されるメッセージ数</span><span class="sxs-lookup"><span data-stu-id="fc336-131">Number of additional messages created per incoming message</span></span>|  
|<span data-ttu-id="fc336-132">**メッセージの最大数**</span><span class="sxs-lookup"><span data-stu-id="fc336-132">**Msgs**</span></span>|<span data-ttu-id="fc336-133">一定期間における受信メッセージの推定数</span><span class="sxs-lookup"><span data-stu-id="fc336-133">Number of estimated incoming messages in a given time period</span></span>|  
|<span data-ttu-id="fc336-134">**式の MsgSize**</span><span class="sxs-lookup"><span data-stu-id="fc336-134">**MsgSize**</span></span>|<span data-ttu-id="fc336-135">メッセージのサイズ</span><span class="sxs-lookup"><span data-stu-id="fc336-135">Message size</span></span>|  
|<span data-ttu-id="fc336-136">**MsgNum**</span><span class="sxs-lookup"><span data-stu-id="fc336-136">**MsgNum**</span></span>|<span data-ttu-id="fc336-137">受信メッセージごとに追跡されるメッセージ数</span><span class="sxs-lookup"><span data-stu-id="fc336-137">Number of messages tracked for each incoming message</span></span>|  
  
 <span data-ttu-id="fc336-138">式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fc336-138">The equation is as follows:</span></span>  
  
```  
[((Nserv * 150 bytes) + (Events * 230 bytes) + (Properties * CMsgs*(52 bytes + PropSize))) * Msgs]/1024/1024 = Data size in MB  
```  
  
 <span data-ttu-id="fc336-139">この式では、メッセージによって生成される追跡データのみが計算されます。オーケストレーション デバッガー用に生成される追跡データは含まれません。</span><span class="sxs-lookup"><span data-stu-id="fc336-139">This equation calculates only the tracking data generated by the messages and does not include the tracking data generated for the Orchestration Debugger.</span></span> <span data-ttu-id="fc336-140">BizTalk の追跡データベースのサイズを見積もるには、各メッセージ プロセスに対してこの式を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc336-140">You must apply this formula to each message process to estimate the size of the BizTalk Tracking database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc336-141">参照</span><span class="sxs-lookup"><span data-stu-id="fc336-141">See Also</span></span>  
 <span data-ttu-id="fc336-142">[メッセージ本文を追跡する追跡データベースのサイズ変更](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="fc336-142">[Sizing the Tracking Database to Track Message Bodies](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span></span>  
 <span data-ttu-id="fc336-143">[シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ変更](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span><span class="sxs-lookup"><span data-stu-id="fc336-143">[Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span></span>  
 <span data-ttu-id="fc336-144">[シナリオ 2: オーケストレーションでメッセージの追跡データベースのサイズ変更](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="fc336-144">[Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span></span>  
 <span data-ttu-id="fc336-145">[シナリオ 4: すべてのメッセージの追跡データベースのサイズ変更](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span><span class="sxs-lookup"><span data-stu-id="fc336-145">[Scenario 4: Sizing the Tracking Database for all Messages](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span></span>  
 [<span data-ttu-id="fc336-146">シナリオ 3: 同報リストに送信されるメッセージの追跡データベースのサイズ変更</span><span class="sxs-lookup"><span data-stu-id="fc336-146">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)