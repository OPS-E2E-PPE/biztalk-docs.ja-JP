---
title: "FRR オーケストレーション |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, promoted properties
- orchestrations, message subscriptions
- promoted properties, messages
- FRR, orchestrations
- subscriptions, messages
- orchestrations, reconciliation time-out
- messages, message/response correlation
- message/response correlation
- promoted properties, FIN Response Reconciliation
- orchestrations, FRR
- outbound messages
- FIN Response Reconciliation, promoted properties
- direct bindings
- reconciliation time-out
- bindings, direct
- messages, subscriptions
- subscriptions, orchestrations
- messages, outbound
- MessageBox database
ms.assetid: ea8d31c2-ac3b-44ac-8064-d008da4f7f72
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43dd7d6245546f8d35760bfe2ed2224482d9d4bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="frr-orchestration"></a><span data-ttu-id="5c7c9-102">FRR オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="5c7c9-102">FRR Orchestration</span></span>
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="5c7c9-103">FRR オーケストレーションで FRR を実装します。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-103"> implements FRR through the FRR orchestration.</span></span> <span data-ttu-id="5c7c9-104">オーケストレーションでは、FIN 応答の相関トークンと一致するどうか、元のメッセージのメッセージ ID を決定します。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-104">The orchestration determines whether the Correlation Token of the FIN response matches the message ID of the original message.</span></span> <span data-ttu-id="5c7c9-105">SAA にメッセージを送信する送信ポートで実行される送信機能と SAA からメッセージを受信する受信場所で実行される受信機能は、並列でメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-105">It processes the message in parallel with the send functions performed by the send port that sends the message to SAA, and with the receive functions performed by the receive location that receives the message from SAA.</span></span>  
  
 <span data-ttu-id="5c7c9-106">最上位のレベルでは、オーケストレーションのインスタンスは、以下の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-106">At the highest level, an instance of the orchestration does the following processing:</span></span>  
  
1.  <span data-ttu-id="5c7c9-107">元の送信メッセージのコピーはキャッシュ SAA のメッセージ ボックス データベースをリッスンしてバインドされます。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-107">Caches a copy of the original outbound message bound for SAA by listening on the MessageBox.</span></span>  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5c7c9-108">オーケストレーションのインスタンスを作成時に[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージ ボックスに、元のメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-108"> creates an instance of the orchestration when [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] routes the original message to the MessageBox.</span></span>  
  
2.  <span data-ttu-id="5c7c9-109">待機[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]SAA からメッセージ ボックス データベースへの FIN 応答を発行します。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-109">Waits for [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to publish a FIN response from SAA to the MessageBox.</span></span>  
  
3.  <span data-ttu-id="5c7c9-110">セットは、FIN 応答の性質によって、元のメッセージのコピーのプロパティを昇格します。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-110">Sets promoted properties of the copy of the original message depending upon the nature of the FIN response.</span></span>  
  
4.  <span data-ttu-id="5c7c9-111">元のメッセージのコピーをメッセージ ボックス データベースに発行します。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-111">Publishes the copy of the original message back to the MessageBox.</span></span> <span data-ttu-id="5c7c9-112">カスタム ハンドラーを取得するサブスクライブし、必要に応じてメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-112">Custom handlers can then subscribe to, retrieve, and handle the message as required.</span></span>  
  
## <a name="subscription-to-outbound-messages"></a><span data-ttu-id="5c7c9-113">送信メッセージへのサブスクリプション</span><span class="sxs-lookup"><span data-stu-id="5c7c9-113">Subscription to Outbound Messages</span></span>  
 <span data-ttu-id="5c7c9-114">FRR オーケストレーションはメッセージ ボックスに直接バインドします。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-114">The FRR orchestration is directly bound to the MessageBox.</span></span> <span data-ttu-id="5c7c9-115">FRR オーケストレーションは、すべての送信メッセージに SWIFT ネットワークは、バインドされている次のプロパティをサブスクライブすることによって検証エラーを含まないをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-115">The FRR orchestration subscribes to all outbound messages bound for the SWIFT network that do not contain validation errors, by subscribing to the following properties:</span></span>  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="5c7c9-116">_Failed false を = = (されている SWIFT の逆アセンブラーの検証プロセスで)</span><span class="sxs-lookup"><span data-stu-id="5c7c9-116">_Failed==False (as set by the SWIFT Disassembler validation process)</span></span>  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="5c7c9-117">_Swiftbound true を = = (プロセスによって設定された、SWIFT 逆アセンブラーの構成)</span><span class="sxs-lookup"><span data-stu-id="5c7c9-117">_Swiftbound==True (as set by the SWIFT Disassembler configuration process)</span></span>  
  
## <a name="messageresponse-correlation"></a><span data-ttu-id="5c7c9-118">メッセージと応答の相関関係</span><span class="sxs-lookup"><span data-stu-id="5c7c9-118">Message/Response Correlation</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5c7c9-119">次のプロパティを比較することによって元の送信 FIN メッセージを受信 FIN 応答メッセージを相互に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-119"> correlates the original outbound FIN message to the inbound FIN response message by comparing the following properties:</span></span>  
  
-   <span data-ttu-id="5c7c9-120">FIN 応答の MQMD_CorrelID コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="5c7c9-120">The MQMD_CorrelID context property of the FIN response</span></span>  
  
-   <span data-ttu-id="5c7c9-121">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MTXYY の送信メッセージの _FRRCorrelationToken プロパティです。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-121">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRCorrelationToken property of the outbound MTXYY message.</span></span> <span data-ttu-id="5c7c9-122">このプロパティは、受信パイプラインのパーティの解決ステージによって昇格されます。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-122">This property is promoted by the party-resolution stage of the receive pipeline.</span></span>  
  
 <span data-ttu-id="5c7c9-123">これらのプロパティの値を同一にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-123">The values of these properties must be identical.</span></span> <span data-ttu-id="5c7c9-124">メッセージの送信パイプラインのエンコーダーの段階に SWIFT の値を送信メッセージの MQMD_MsgID プロパティを設定するがバインドされている、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRCorrelationToken プロパティです。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-124">The encoder stage of the send pipeline for messages bound for SWIFT sets the MQMD_MsgID property of the outgoing message to the value of the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRCorrelationToken property.</span></span> <span data-ttu-id="5c7c9-125">SAA は、MQMD_MsgID の値を応答メッセージの MQMD_CorrelID プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-125">SAA sets the MQMD_CorrelID property of the response message to the value of MQMD_MsgID.</span></span>  
  
## <a name="setting-of-promoted-properties"></a><span data-ttu-id="5c7c9-126">昇格させたプロパティの設定</span><span class="sxs-lookup"><span data-stu-id="5c7c9-126">Setting of Promoted Properties</span></span>  
 <span data-ttu-id="5c7c9-127">FIN 応答の受信と、元のメッセージのコピーへの関連付け、FRR オーケストレーションは応答の性質によって、元のメッセージのコピーの次の昇格させたプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-127">After receiving a FIN response and correlating it to the copy of the original message, the FRR orchestration sets the following promoted properties of the copy of the original message according to the nature of the response:</span></span>  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="5c7c9-128">応答が NAK 場合の応答が ACK または False の場合は True に _FRRFailed</span><span class="sxs-lookup"><span data-stu-id="5c7c9-128">_FRRFailed to True if the response was an ACK or False if the response was a NAK</span></span>  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="5c7c9-129">応答が NAK であった場合、次の値のいずれかの _FRRFailedReason:</span><span class="sxs-lookup"><span data-stu-id="5c7c9-129">_FRRFailedReason to the one of the following values, if the response was a NAK:</span></span>  
  
    -   <span data-ttu-id="5c7c9-130">*\<ErrorCode >* (MTS21_FIN_ACKNAK 負受信確認メッセージの 405 フィールド) から</span><span class="sxs-lookup"><span data-stu-id="5c7c9-130">*\<ErrorCode>* (from the 405 field of the MTS21_FIN_ACKNAK negative-acknowledgment message)</span></span>  
  
    -   <span data-ttu-id="5c7c9-131">(MQ 系列パン/NAN メッセージ) から TransportError</span><span class="sxs-lookup"><span data-stu-id="5c7c9-131">TransportError (from an MQ Series PAN/NAN message)</span></span>  
  
    -   <span data-ttu-id="5c7c9-132">(MT015 (DNK) メッセージ) から DelayedNAK</span><span class="sxs-lookup"><span data-stu-id="5c7c9-132">DelayedNAK (from an MT015 (DNK) message)</span></span>  
  
    -   <span data-ttu-id="5c7c9-133">AbortReceived (、MT019 から (中止通知) メッセージ)</span><span class="sxs-lookup"><span data-stu-id="5c7c9-133">AbortReceived (from an MT019 (Abort Notification) message)</span></span>  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="5c7c9-134">TimedOut に _FRRFailedReason 場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]タイムアウト期間内の応答を受信しませんでした。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-134">_FRRFailedReason to TimedOut if [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] did not receive a response within the timeout period.</span></span> <span data-ttu-id="5c7c9-135">FRR 遅延タイムアウトの詳細については、後述の「「調整タイムアウト」を参照してください。 または[FRR 遅延タイムアウトの設定](../../adapters-and-accelerators/accelerator-swift/setting-the-frr-delay-time-out.md)です。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-135">For more information about the FRR Delay Time-out, see the "Reconciliation Time-Out" section below or [Setting the FRR Delay Time-Out](../../adapters-and-accelerators/accelerator-swift/setting-the-frr-delay-time-out.md).</span></span>  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="5c7c9-136">_SendingServiceType [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span><span class="sxs-lookup"><span data-stu-id="5c7c9-136">_SendingServiceType to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService</span></span>  
  
-   <span data-ttu-id="5c7c9-137">BTS です。応答メッセージの種類に対応する値を操作します。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-137">BTS.Operation to the value corresponding to the type of message response.</span></span> <span data-ttu-id="5c7c9-138">詳細については、次を参照してください。 [FRR 送信ポートを作成するカスタム ハンドラーに送信の](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)します。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-138">For more information, see [Creating the FRR Send Ports for Sending to the Custom Handlers](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md).</span></span>  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="5c7c9-139">MQ 系列パン/NAN メッセージ (MQ Series トランスポート レベル ACK/NAK) _FrrSendTransport</span><span class="sxs-lookup"><span data-stu-id="5c7c9-139">_FrrSendTransport for an MQ Series PAN/NAN message (MQ Series transport-level ACK/NAK)</span></span>  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="5c7c9-140">_FrrSend010NDW MT010 メッセージ (警告の配信不能)</span><span class="sxs-lookup"><span data-stu-id="5c7c9-140">_FrrSend010NDW for an MT010 message (Non-Delivery Warning)</span></span>  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="5c7c9-141">_FrrSend011Delivered MT011 メッセージ (配信通知)</span><span class="sxs-lookup"><span data-stu-id="5c7c9-141">_FrrSend011Delivered for an MT011 message (Delivery Notification)</span></span>  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="5c7c9-142">_FrrSend012SenderACK MT012 メッセージ (通知の送信側)</span><span class="sxs-lookup"><span data-stu-id="5c7c9-142">_FrrSend012SenderACK for an MT012 message (Sender Notification)</span></span>  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="5c7c9-143">_FrrSend015DNK MT015 メッセージ (DNK、または遅延 NAK)</span><span class="sxs-lookup"><span data-stu-id="5c7c9-143">_FrrSend015DNK for an MT015 message (DNK, or Delayed NAK)</span></span>  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="5c7c9-144">_FrrSend019Abort MT019 メッセージ (通知の中止)</span><span class="sxs-lookup"><span data-stu-id="5c7c9-144">_FrrSend019Abort for an MT019 message (Abort Notification)</span></span>  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="5c7c9-145">_FrrSendS21ACK MTS21_FIN_ACKNAK 受信確認メッセージ (、LT によって送信された FIN メッセージの ACK)</span><span class="sxs-lookup"><span data-stu-id="5c7c9-145">_FrrSendS21ACK for an MTS21_FIN_ACKNAK acknowledgment message (ACK of a FIN message sent by an LT)</span></span>  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="5c7c9-146">_FrrSendS21NAK MTS21_FIN_ACKNAK 負受信確認メッセージ (NAK、LT によって送信された FIN メッセージの)</span><span class="sxs-lookup"><span data-stu-id="5c7c9-146">_FrrSendS21NAK for an MTS21_FIN_ACKNAK negative-acknowledgment message (NAK of a FIN message sent by an LT)</span></span>  
  
## <a name="direct-binding"></a><span data-ttu-id="5c7c9-147">直接バインド</span><span class="sxs-lookup"><span data-stu-id="5c7c9-147">Direct Binding</span></span>  
 <span data-ttu-id="5c7c9-148">オーケストレーションがメッセージ ボックスには、オーケストレーションはサブスクリプションによって定義されているは、入力を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-148">Receive inputs for the orchestration are defined by subscriptions that the orchestration makes to the MessageBox.</span></span> <span data-ttu-id="5c7c9-149">コンテキスト プロパティと、オーケストレーションによって昇格された値は、オーケストレーションがメッセージ ボックスに公開されるメッセージの送信の出力を定義します。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-149">Context properties and values promoted by the orchestration define the send outputs for a message that the orchestration publishes to the MessageBox.</span></span> <span data-ttu-id="5c7c9-150">メッセージ ボックスに直接このバインディングのため、オーケストレーションは、次の中から切り離されます。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-150">Because of this direct binding to the MessageBox, the orchestration is decoupled from the following:</span></span>  
  
-   <span data-ttu-id="5c7c9-151">物理受信 SAA へのルーティング用のバックエンド アプリケーションから送信メッセージを受信する場所</span><span class="sxs-lookup"><span data-stu-id="5c7c9-151">The physical receive locations that receive outbound messages from the back-end application for routing to SAA</span></span>  
  
-   <span data-ttu-id="5c7c9-152">送信する送信ポートからのメッセージの FIN[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]に SWIFT Alliance アクセス (SAA)</span><span class="sxs-lookup"><span data-stu-id="5c7c9-152">The send ports that send outbound FIN messages from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to the SWIFT Alliance Access (SAA)</span></span>  
  
-   <span data-ttu-id="5c7c9-153">SAA から着信 FIN 応答メッセージを受信する受信場所</span><span class="sxs-lookup"><span data-stu-id="5c7c9-153">The receive locations that receive incoming FIN response messages from SAA</span></span>  
  
-   <span data-ttu-id="5c7c9-154">SAA によって FIN 応答を格納する場所、物理 MQSeries キュー</span><span class="sxs-lookup"><span data-stu-id="5c7c9-154">The physical MQSeries queues where FIN responses are deposited by SAA</span></span>  
  
## <a name="reconciliation-time-out"></a><span data-ttu-id="5c7c9-155">調整のタイムアウト</span><span class="sxs-lookup"><span data-stu-id="5c7c9-155">Reconciliation Time-Out</span></span>  
 <span data-ttu-id="5c7c9-156">ときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]FRR オーケストレーション、FIN 応答を待機しているオーケストレーションの開始の新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-156">When [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] creates a new instance of the FRR orchestration, the orchestration starts waiting for FIN responses.</span></span> <span data-ttu-id="5c7c9-157">実行時に、それが待機するようにいない応答を無期限にいくつかの期間の後にタイムアウトにオーケストレーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-157">At run time, you must configure the orchestration to time out after some duration, so that it will not wait for the response indefinitely.</span></span> <span data-ttu-id="5c7c9-158">タイムアウト期間が経過すると、FRR オーケストレーションが昇格、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRFailedReason プロパティし TimedOut に設定します。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-158">When the time-out duration expires, the FRR orchestration promotes the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRFailedReason property and sets it to TimedOut.</span></span> <span data-ttu-id="5c7c9-159">メッセージ ボックスにメッセージを公開し、終了します。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-159">It then publishes messages out to the MessageBox, and terminates.</span></span> <span data-ttu-id="5c7c9-160">タイムアウトする場合は、相関 ID が削除されます。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-160">If you time out, the correlation ID is gone.</span></span>  
  
 <span data-ttu-id="5c7c9-161">タイムアウトになったメッセージ (元の送信メッセージのコピー) を処理するためのカスタム ハンドラーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-161">You can create a custom handler to process timed-out messages (the copy of the original outbound message).</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="5c7c9-162">そのためのオーケストレーションの待ち受け図形を使用して、します。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-162"> would accomplish this by using a Listen shape in the orchestration.</span></span> <span data-ttu-id="5c7c9-163">詳細については、次を参照してください。 [FRR 遅延タイムアウトの設定](../../adapters-and-accelerators/accelerator-swift/setting-the-frr-delay-time-out.md)です。</span><span class="sxs-lookup"><span data-stu-id="5c7c9-163">For more information, see [Setting the FRR Delay Time-Out](../../adapters-and-accelerators/accelerator-swift/setting-the-frr-delay-time-out.md).</span></span>