---
title: メッセージ変数を使用して、追跡データベースのサイズを |Microsoft Docs
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
ms.openlocfilehash: 9ef731d12155ae20d7f78aaaf4a5f990b76affba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985683"
---
# <a name="using-message-variables-to-size-the-tracking-database"></a><span data-ttu-id="8625e-102">メッセージ変数を使用して追跡データベースのサイズを求める方法</span><span class="sxs-lookup"><span data-stu-id="8625e-102">Using Message Variables to Size the Tracking Database</span></span>
<span data-ttu-id="8625e-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、BizTalk の追跡 (BizTalkDTADb) データベースのサイズが一定期間経過後にどのくらいのサイズになるかを、各種の変数を使って求めることができます。</span><span class="sxs-lookup"><span data-stu-id="8625e-103">In Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can use a number of variables to determine how large the BizTalk Tracking (BizTalkDTADb) database will become over a given period of time.</span></span> <span data-ttu-id="8625e-104">これらの変数を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8625e-104">These variables are:</span></span>  
  
- <span data-ttu-id="8625e-105">使用パイプライン数</span><span class="sxs-lookup"><span data-stu-id="8625e-105">Number of pipelines used</span></span>  
  
- <span data-ttu-id="8625e-106">関連するオーケストレーション数</span><span class="sxs-lookup"><span data-stu-id="8625e-106">Number of orchestrations involved</span></span>  
  
- <span data-ttu-id="8625e-107">生成されたイベント数</span><span class="sxs-lookup"><span data-stu-id="8625e-107">Number of events generated</span></span>  
  
- <span data-ttu-id="8625e-108">追跡対象のメッセージ プロパティ数</span><span class="sxs-lookup"><span data-stu-id="8625e-108">Number of message properties tracked</span></span>  
  
- <span data-ttu-id="8625e-109">追加的に作成されるメッセージ数</span><span class="sxs-lookup"><span data-stu-id="8625e-109">Number of additional messages created</span></span>  
  
- <span data-ttu-id="8625e-110">指定の期間に受け取ったメッセージの推定数</span><span class="sxs-lookup"><span data-stu-id="8625e-110">Estimated number of messages received in the specified timeframe</span></span>  
  
  <span data-ttu-id="8625e-111">BizTalk の追跡データベースのサイズを見積もるための式はそれほど複雑なものではありません。ただし、この式は、BizTalk Server 環境で使用されるすべての受信/送信メッセージ プロセスに対して適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8625e-111">While the equation you use to estimate the size of the BizTalk Tracking database is straightforward, you must apply it to each incoming and outgoing message process that uses the BizTalk Server implementation.</span></span> <span data-ttu-id="8625e-112">つまり、個々のメッセージ シナリオに対してこの式を適用し、その結果を総計して初めて、最終的な推定データベース サイズを得ることができます。</span><span class="sxs-lookup"><span data-stu-id="8625e-112">In other words, you will need to apply this equation for every distinct message scenario and then add up the results to obtain the final estimated database size.</span></span> <span data-ttu-id="8625e-113">このドキュメントでは、次の 2 つのシナリオを想定しています。</span><span class="sxs-lookup"><span data-stu-id="8625e-113">In this document we will look at two scenarios.</span></span> <span data-ttu-id="8625e-114">シナリオでは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8625e-114">The scenarios are:</span></span>  
  
1. <span data-ttu-id="8625e-115">メッセージを受信し、そのメッセージを変換して、結果のメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="8625e-115">Receiving a message, transforming the message, and then sending the resulting message</span></span>  
  
2. <span data-ttu-id="8625e-116">メッセージを受信し、そのメッセージを使ってビジネス プロセスを実行して、結果のメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="8625e-116">Receiving a message, running a business process using the message, and then sending the resulting message.</span></span>  
  
   <span data-ttu-id="8625e-117">どちらも、BizTalk Server 環境で想定されるシナリオですが、追跡データの量はシナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="8625e-117">Both of these scenarios may be present in a BizTalk Server installation, and each scenario generates a different amount of tracking data.</span></span> <span data-ttu-id="8625e-118">BizTalk Server 環境で生成される総追跡データは、これらすべてのシナリオを合計した値になります。</span><span class="sxs-lookup"><span data-stu-id="8625e-118">The total tracking data generated for the BizTalk Server installation is the sum of all the scenarios.</span></span>  
  
   <span data-ttu-id="8625e-119">式に用いられている変数には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="8625e-119">The following are some variables used in the equation:</span></span>  
  
|<span data-ttu-id="8625e-120">変数</span><span class="sxs-lookup"><span data-stu-id="8625e-120">Variable</span></span>|<span data-ttu-id="8625e-121">説明</span><span class="sxs-lookup"><span data-stu-id="8625e-121">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="8625e-122">**Nserv**</span><span class="sxs-lookup"><span data-stu-id="8625e-122">**Nserv**</span></span>|<span data-ttu-id="8625e-123">サービス数 (パイプライン数 + オーケストレーション数)</span><span class="sxs-lookup"><span data-stu-id="8625e-123">Number of services (number of pipelines + number of orchestrations)</span></span>|  
|<span data-ttu-id="8625e-124">**イベント**</span><span class="sxs-lookup"><span data-stu-id="8625e-124">**Events**</span></span>|<span data-ttu-id="8625e-125">生成されるメッセージ イベント数</span><span class="sxs-lookup"><span data-stu-id="8625e-125">Number of generated message events</span></span>|  
|<span data-ttu-id="8625e-126">**Properties**</span><span class="sxs-lookup"><span data-stu-id="8625e-126">**Properties**</span></span>|<span data-ttu-id="8625e-127">追跡対象のメッセージ プロパティ数</span><span class="sxs-lookup"><span data-stu-id="8625e-127">Number of message properties tracked</span></span>|  
|<span data-ttu-id="8625e-128">**PropSize**</span><span class="sxs-lookup"><span data-stu-id="8625e-128">**PropSize**</span></span>|<span data-ttu-id="8625e-129">昇格させたプロパティ (フィールド) のサイズ (バイト単位)</span><span class="sxs-lookup"><span data-stu-id="8625e-129">Size (in bytes) of the promoted property (field)</span></span>|  
|<span data-ttu-id="8625e-130">**CMsgs**</span><span class="sxs-lookup"><span data-stu-id="8625e-130">**CMsgs**</span></span>|<span data-ttu-id="8625e-131">1 つの受信メッセージにつき追加的に作成されるメッセージ数</span><span class="sxs-lookup"><span data-stu-id="8625e-131">Number of additional messages created per incoming message</span></span>|  
|<span data-ttu-id="8625e-132">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="8625e-132">**Msgs**</span></span>|<span data-ttu-id="8625e-133">一定期間における受信メッセージの推定数</span><span class="sxs-lookup"><span data-stu-id="8625e-133">Number of estimated incoming messages in a given time period</span></span>|  
|<span data-ttu-id="8625e-134">**式の MsgSize**</span><span class="sxs-lookup"><span data-stu-id="8625e-134">**MsgSize**</span></span>|<span data-ttu-id="8625e-135">メッセージ サイズ</span><span class="sxs-lookup"><span data-stu-id="8625e-135">Message size</span></span>|  
|<span data-ttu-id="8625e-136">**MsgNum**</span><span class="sxs-lookup"><span data-stu-id="8625e-136">**MsgNum**</span></span>|<span data-ttu-id="8625e-137">受信メッセージごとに追跡されるメッセージ数</span><span class="sxs-lookup"><span data-stu-id="8625e-137">Number of messages tracked for each incoming message</span></span>|  
  
 <span data-ttu-id="8625e-138">式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8625e-138">The equation is as follows:</span></span>  
  
```  
[((Nserv * 150 bytes) + (Events * 230 bytes) + (Properties * CMsgs*(52 bytes + PropSize))) * Msgs]/1024/1024 = Data size in MB  
```  
  
 <span data-ttu-id="8625e-139">この式では、メッセージによって生成される追跡データのみが計算されます。オーケストレーション デバッガー用に生成される追跡データは含まれません。</span><span class="sxs-lookup"><span data-stu-id="8625e-139">This equation calculates only the tracking data generated by the messages and does not include the tracking data generated for the Orchestration Debugger.</span></span> <span data-ttu-id="8625e-140">BizTalk の追跡データベースのサイズを見積もるには、各メッセージ プロセスに対してこの式を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8625e-140">You must apply this formula to each message process to estimate the size of the BizTalk Tracking database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8625e-141">参照</span><span class="sxs-lookup"><span data-stu-id="8625e-141">See Also</span></span>  
 <span data-ttu-id="8625e-142">[メッセージ本文を追跡する追跡データベースのサイズ調整](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="8625e-142">[Sizing the Tracking Database to Track Message Bodies](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span></span>  
 <span data-ttu-id="8625e-143">[シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ調整](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span><span class="sxs-lookup"><span data-stu-id="8625e-143">[Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span></span>  
 <span data-ttu-id="8625e-144">[シナリオ 2: オーケストレーション内のメッセージの追跡データベースのサイズ調整](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="8625e-144">[Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span></span>  
 <span data-ttu-id="8625e-145">[シナリオ 4: すべてのメッセージの追跡データベースのサイズ調整](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span><span class="sxs-lookup"><span data-stu-id="8625e-145">[Scenario 4: Sizing the Tracking Database for all Messages](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span></span>  
 [<span data-ttu-id="8625e-146">シナリオ 3: 同報リストに送信されるメッセージの追跡データベースのサイズ調整</span><span class="sxs-lookup"><span data-stu-id="8625e-146">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)