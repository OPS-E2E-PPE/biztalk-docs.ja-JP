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
ms.openlocfilehash: 8ac96e6784ed73dce415c78ff5f559d52be42395
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396833"
---
# <a name="using-message-variables-to-size-the-tracking-database"></a><span data-ttu-id="8f5fd-102">追跡データベースのサイズにメッセージ変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="8f5fd-102">Using Message Variables to Size the Tracking Database</span></span>
<span data-ttu-id="8f5fd-103">Microsoft で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、大きさ、BizTalk 追跡 (BizTalkDTADb) データベースになるか、指定した期間にわたって変数の数を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="8f5fd-103">In Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can use a number of variables to determine how large the BizTalk Tracking (BizTalkDTADb) database will become over a given period of time.</span></span> <span data-ttu-id="8f5fd-104">これらの変数は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8f5fd-104">These variables are:</span></span>  
  
- <span data-ttu-id="8f5fd-105">使用パイプライン数</span><span class="sxs-lookup"><span data-stu-id="8f5fd-105">Number of pipelines used</span></span>  
  
- <span data-ttu-id="8f5fd-106">関連するオーケストレーションの数</span><span class="sxs-lookup"><span data-stu-id="8f5fd-106">Number of orchestrations involved</span></span>  
  
- <span data-ttu-id="8f5fd-107">生成されたイベント数</span><span class="sxs-lookup"><span data-stu-id="8f5fd-107">Number of events generated</span></span>  
  
- <span data-ttu-id="8f5fd-108">追跡メッセージのプロパティの数</span><span class="sxs-lookup"><span data-stu-id="8f5fd-108">Number of message properties tracked</span></span>  
  
- <span data-ttu-id="8f5fd-109">作成された追加のメッセージの数</span><span class="sxs-lookup"><span data-stu-id="8f5fd-109">Number of additional messages created</span></span>  
  
- <span data-ttu-id="8f5fd-110">指定した時間帯で受信したメッセージの推定数</span><span class="sxs-lookup"><span data-stu-id="8f5fd-110">Estimated number of messages received in the specified timeframe</span></span>  
  
  <span data-ttu-id="8f5fd-111">BizTalk 追跡データベースのサイズの見積もりに使用する数式は容易ですが、中には、BizTalk Server の実装を使用する各メッセージの受信および送信プロセスに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f5fd-111">While the equation you use to estimate the size of the BizTalk Tracking database is straightforward, you must apply it to each incoming and outgoing message process that uses the BizTalk Server implementation.</span></span> <span data-ttu-id="8f5fd-112">つまり、個々 のメッセージ シナリオのこの式を適用し、最終的な推定データベース サイズを取得する結果を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f5fd-112">In other words, you will need to apply this equation for every distinct message scenario and then add up the results to obtain the final estimated database size.</span></span> <span data-ttu-id="8f5fd-113">このドキュメントでは、2 つのシナリオに注目します。</span><span class="sxs-lookup"><span data-stu-id="8f5fd-113">In this document we will look at two scenarios.</span></span> <span data-ttu-id="8f5fd-114">シナリオでは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8f5fd-114">The scenarios are:</span></span>  
  
1. <span data-ttu-id="8f5fd-115">メッセージの受信や、メッセージに変換し、結果のメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="8f5fd-115">Receiving a message, transforming the message, and then sending the resulting message</span></span>  
  
2. <span data-ttu-id="8f5fd-116">結果のメッセージを送信し、メッセージを使用してビジネス プロセスを実行しているメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="8f5fd-116">Receiving a message, running a business process using the message, and then sending the resulting message.</span></span>  
  
   <span data-ttu-id="8f5fd-117">BizTalk Server のインストールに存在するこれら両方のシナリオがあり、各シナリオは、追跡データのさまざまな量を生成します。</span><span class="sxs-lookup"><span data-stu-id="8f5fd-117">Both of these scenarios may be present in a BizTalk Server installation, and each scenario generates a different amount of tracking data.</span></span> <span data-ttu-id="8f5fd-118">BizTalk Server のインストール用に生成されたデータの追跡の合計は、すべてのシナリオの合計です。</span><span class="sxs-lookup"><span data-stu-id="8f5fd-118">The total tracking data generated for the BizTalk Server installation is the sum of all the scenarios.</span></span>  
  
   <span data-ttu-id="8f5fd-119">以下は、式で使用されるいくつかの変数です。</span><span class="sxs-lookup"><span data-stu-id="8f5fd-119">The following are some variables used in the equation:</span></span>  
  
|<span data-ttu-id="8f5fd-120">変数</span><span class="sxs-lookup"><span data-stu-id="8f5fd-120">Variable</span></span>|<span data-ttu-id="8f5fd-121">説明</span><span class="sxs-lookup"><span data-stu-id="8f5fd-121">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="8f5fd-122">**Nserv**</span><span class="sxs-lookup"><span data-stu-id="8f5fd-122">**Nserv**</span></span>|<span data-ttu-id="8f5fd-123">複数のサービス (パイプラインの数) + オーケストレーション数</span><span class="sxs-lookup"><span data-stu-id="8f5fd-123">Number of services (number of pipelines + number of orchestrations)</span></span>|  
|<span data-ttu-id="8f5fd-124">**イベント**</span><span class="sxs-lookup"><span data-stu-id="8f5fd-124">**Events**</span></span>|<span data-ttu-id="8f5fd-125">生成されたメッセージのイベントの数</span><span class="sxs-lookup"><span data-stu-id="8f5fd-125">Number of generated message events</span></span>|  
|<span data-ttu-id="8f5fd-126">**Properties**</span><span class="sxs-lookup"><span data-stu-id="8f5fd-126">**Properties**</span></span>|<span data-ttu-id="8f5fd-127">追跡メッセージのプロパティの数</span><span class="sxs-lookup"><span data-stu-id="8f5fd-127">Number of message properties tracked</span></span>|  
|<span data-ttu-id="8f5fd-128">**PropSize**</span><span class="sxs-lookup"><span data-stu-id="8f5fd-128">**PropSize**</span></span>|<span data-ttu-id="8f5fd-129">サイズ (バイト単位)、昇格させたプロパティ (フィールド)</span><span class="sxs-lookup"><span data-stu-id="8f5fd-129">Size (in bytes) of the promoted property (field)</span></span>|  
|<span data-ttu-id="8f5fd-130">**CMsgs**</span><span class="sxs-lookup"><span data-stu-id="8f5fd-130">**CMsgs**</span></span>|<span data-ttu-id="8f5fd-131">受信メッセージごとに作成された追加のメッセージの数</span><span class="sxs-lookup"><span data-stu-id="8f5fd-131">Number of additional messages created per incoming message</span></span>|  
|<span data-ttu-id="8f5fd-132">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="8f5fd-132">**Msgs**</span></span>|<span data-ttu-id="8f5fd-133">特定の期間中に受信メッセージの推定数</span><span class="sxs-lookup"><span data-stu-id="8f5fd-133">Number of estimated incoming messages in a given time period</span></span>|  
|<span data-ttu-id="8f5fd-134">**式の MsgSize**</span><span class="sxs-lookup"><span data-stu-id="8f5fd-134">**MsgSize**</span></span>|<span data-ttu-id="8f5fd-135">メッセージ サイズ</span><span class="sxs-lookup"><span data-stu-id="8f5fd-135">Message size</span></span>|  
|<span data-ttu-id="8f5fd-136">**MsgNum**</span><span class="sxs-lookup"><span data-stu-id="8f5fd-136">**MsgNum**</span></span>|<span data-ttu-id="8f5fd-137">受信メッセージごとに追跡されるメッセージ数</span><span class="sxs-lookup"><span data-stu-id="8f5fd-137">Number of messages tracked for each incoming message</span></span>|  
  
 <span data-ttu-id="8f5fd-138">式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8f5fd-138">The equation is as follows:</span></span>  
  
```  
[((Nserv * 150 bytes) + (Events * 230 bytes) + (Properties * CMsgs*(52 bytes + PropSize))) * Msgs]/1024/1024 = Data size in MB  
```  
  
 <span data-ttu-id="8f5fd-139">この式は、メッセージによって生成される追跡データのみを計算し、オーケストレーション デバッガーに対して生成された追跡データは含まれません。</span><span class="sxs-lookup"><span data-stu-id="8f5fd-139">This equation calculates only the tracking data generated by the messages and does not include the tracking data generated for the Orchestration Debugger.</span></span> <span data-ttu-id="8f5fd-140">BizTalk 追跡データベースのサイズを推定するには、各メッセージ プロセスには、次の数式を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f5fd-140">You must apply this formula to each message process to estimate the size of the BizTalk Tracking database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f5fd-141">参照</span><span class="sxs-lookup"><span data-stu-id="8f5fd-141">See Also</span></span>  
 <span data-ttu-id="8f5fd-142">[メッセージ本文を追跡する追跡データベースのサイズ調整](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="8f5fd-142">[Sizing the Tracking Database to Track Message Bodies](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span></span>  
 <span data-ttu-id="8f5fd-143">[シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ調整](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span><span class="sxs-lookup"><span data-stu-id="8f5fd-143">[Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span></span>  
 <span data-ttu-id="8f5fd-144">[シナリオ 2: オーケストレーション内のメッセージの追跡データベースのサイズ調整](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="8f5fd-144">[Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span></span>  
 <span data-ttu-id="8f5fd-145">[シナリオ 4:すべてのメッセージの追跡データベースのサイズ調整](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span><span class="sxs-lookup"><span data-stu-id="8f5fd-145">[Scenario 4: Sizing the Tracking Database for all Messages](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md) </span></span>  
 [<span data-ttu-id="8f5fd-146">シナリオ 3:配布リストに送信されるメッセージの追跡データベースのサイズ調整</span><span class="sxs-lookup"><span data-stu-id="8f5fd-146">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)