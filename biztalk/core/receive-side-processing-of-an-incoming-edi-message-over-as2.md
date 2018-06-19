---
title: 受信側の処理、受信 EDI メッセージの AS2 経由で |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 118451ab-d847-4f87-80ab-3cf812d71ac3
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fc9069dddf8a8b58ad439ed915fc9afa539c2a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270066"
---
# <a name="receive-side-processing-of-an-incoming-edi-message-over-as2"></a><span data-ttu-id="67ffb-102">AS2 経由での受信 EDI メッセージの受信側の処理</span><span class="sxs-lookup"><span data-stu-id="67ffb-102">Receive-Side Processing of an Incoming EDI Message over AS2</span></span>
<span data-ttu-id="67ffb-103">AS2 経由の EDI メッセージの受信側の処理では、AS2 メッセージの受信、MDN の送信、EDI ペイロードの処理、および EDI 受信確認の送信 (有効になっている場合) が行われます。</span><span class="sxs-lookup"><span data-stu-id="67ffb-103">Receive-side processing of an EDI message over AS2 includes receiving the AS2 message, sending an MDN, processing the EDI payload, and sending EDI acknowledgments (if enabled).</span></span>  
  
 <span data-ttu-id="67ffb-104">AS2EdiReceive 受信パイプラインは、AS2 メッセージを受信し、AS2 メッセージ内の EDI ペイロードを逆アセンブルします。</span><span class="sxs-lookup"><span data-stu-id="67ffb-104">The AS2EdiReceive receive pipeline receives the AS2 message, and disassembles the EDI payload within the AS2 message.</span></span> <span data-ttu-id="67ffb-105">AS2EDISend 送信パイプラインは、AS2 メッセージへの応答としての MDN と、EDI メッセージへの応答として返される EDI 受信確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="67ffb-105">The AS2EDISend send pipeline sends an MDN in response to the AS2 message, and an EDI acknowledgment returned in response to the EDI message.</span></span> <span data-ttu-id="67ffb-106">これらを含めることができます双方向 http パイプラインに送信請求応答の送信ポート (MDN が同期の場合)、または一方向の HTTP 送信ポートと一方向の HTTP 受信ポート (MDN が非同期の場合)。</span><span class="sxs-lookup"><span data-stu-id="67ffb-106">You can include these pipelines in an HTTP two-way solicit response send port (if the MDN is synchronous), or in a one-way HTTP send port and a one-way HTTP receive port (if the MDN is asynchronous).</span></span>  
  
 <span data-ttu-id="67ffb-107">AS2 経由で EDI インターチェンジを受信するために、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="67ffb-107">To receive an EDI interchange over AS2, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will perform the following steps:</span></span>  
  
-   <span data-ttu-id="67ffb-108">受信した AS2 メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="67ffb-108">Processing the received AS2 message</span></span>  
  
-   <span data-ttu-id="67ffb-109">MDN の送信</span><span class="sxs-lookup"><span data-stu-id="67ffb-109">Sending an MDN</span></span>  
  
-   <span data-ttu-id="67ffb-110">受信した EDI ペイロードの処理</span><span class="sxs-lookup"><span data-stu-id="67ffb-110">Processing the received EDI payload</span></span>  
  
-   <span data-ttu-id="67ffb-111">EDI 受信確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="67ffb-111">Sending an EDI Acknowledgment</span></span>  
  
## <a name="processing-the-received-as2-message"></a><span data-ttu-id="67ffb-112">受信した AS2 メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="67ffb-112">Processing the Received AS2 message</span></span>  
 <span data-ttu-id="67ffb-113">AS2EdiReceive 受信パイプラインの AS2 デコーダーが受信 AS2 メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="67ffb-113">The AS2 Decoder in the AS2EdiReceive receive pipeline processes an incoming AS2 message.</span></span> <span data-ttu-id="67ffb-114">この処理は、HTTP アダプターが AS2 メッセージの HTTP ヘッダーから作成する、`InboundHTTPHeaders` コンテキスト プロパティを使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="67ffb-114">It does so using the `InboundHTTPHeaders` context property, which the HTTP adapter creates from the HTTP headers in the AS2 message.</span></span> <span data-ttu-id="67ffb-115">これらのヘッダーには、次の AS2 ヘッダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="67ffb-115">These headers include the following AS2 headers:</span></span>  
  
-   <span data-ttu-id="67ffb-116">AS2-To</span><span class="sxs-lookup"><span data-stu-id="67ffb-116">AS2-To</span></span>  
  
-   <span data-ttu-id="67ffb-117">AS2-From</span><span class="sxs-lookup"><span data-stu-id="67ffb-117">AS2-From</span></span>  
  
-   <span data-ttu-id="67ffb-118">AS2-Version</span><span class="sxs-lookup"><span data-stu-id="67ffb-118">AS2-Version</span></span>  
  
-   <span data-ttu-id="67ffb-119">MessageID</span><span class="sxs-lookup"><span data-stu-id="67ffb-119">MessageID</span></span>  
  
-   <span data-ttu-id="67ffb-120">OriginalMessageID (MDN のみ)</span><span class="sxs-lookup"><span data-stu-id="67ffb-120">OriginalMessageID (for MDNs only)</span></span>  
  
-   <span data-ttu-id="67ffb-121">Disposition-Notification-To (MDN が要求されている場合)</span><span class="sxs-lookup"><span data-stu-id="67ffb-121">Disposition-Notification-To (if an MDN is requested)</span></span>  
  
-   <span data-ttu-id="67ffb-122">Receipt-Delivery-Option (MDN が要求されている場合)</span><span class="sxs-lookup"><span data-stu-id="67ffb-122">Receipt-Delivery-Option (if an MDN is requested)</span></span>  
  
-   <span data-ttu-id="67ffb-123">Signed-Receipt-MICalg (MDN が要求されている場合)</span><span class="sxs-lookup"><span data-stu-id="67ffb-123">Signed-Receipt-MICalg (if an MDN is requested)</span></span>  
  
 <span data-ttu-id="67ffb-124">AS2 デコーダーは、これらのヘッダーをメッセージのコンテキストに昇格させます。</span><span class="sxs-lookup"><span data-stu-id="67ffb-124">The AS2 Decoder will promote these headers to the context of the message.</span></span> <span data-ttu-id="67ffb-125">これは、後は、次の:</span><span class="sxs-lookup"><span data-stu-id="67ffb-125">It then does the following:</span></span>  
  
-   <span data-ttu-id="67ffb-126">アグリーメントの解決を実行して、受信メッセージの処理に使用するパーティのプロパティを特定します。</span><span class="sxs-lookup"><span data-stu-id="67ffb-126">Performs agreement resolution to determine the properties to be used to process the incoming message.</span></span> <span data-ttu-id="67ffb-127">詳細については、次を参照してください。[受信 AS2 メッセージのアグリーメントの解決](../core/agreement-resolution-for-incoming-as2-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="67ffb-127">For more information, see [Agreement Resolution for Incoming AS2 Messages](../core/agreement-resolution-for-incoming-as2-messages.md).</span></span>  
  
-   <span data-ttu-id="67ffb-128">使用して送信者の認証、 **AS2-から**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="67ffb-128">Authenticates the sender using the **AS2-From** property.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="67ffb-129">AS2 受信パイプライン処理の詳細については、受信 AS2 メッセージに対して実行しを参照してください[受信 AS2 メッセージを処理](../core/processing-an-incoming-as2-message.md)です。</span><span class="sxs-lookup"><span data-stu-id="67ffb-129">For more information about the processing that the AS2 receive pipelines perform on incoming AS2 messages, see [Processing an Incoming AS2 Message](../core/processing-an-incoming-as2-message.md).</span></span>  
  
## <a name="sending-an-mdn"></a><span data-ttu-id="67ffb-130">MDN の送信</span><span class="sxs-lookup"><span data-stu-id="67ffb-130">Sending an MDN</span></span>  
 <span data-ttu-id="67ffb-131">MDN が有効にされている場合、AS2EdiReceive パイプラインは MDN を生成し、メッセージボックスにドロップします。</span><span class="sxs-lookup"><span data-stu-id="67ffb-131">If an MDN was enabled, the AS2EdiReceive pipeline generates an MDN and drops it into the MessageBox.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67ffb-132">送信 Mdn に対して行う AS2 受信パイプライン処理の詳細についてを参照してください[送信 MDN の生成](../core/generating-an-outgoing-mdn.md)です。</span><span class="sxs-lookup"><span data-stu-id="67ffb-132">For more information about the processing that the AS2 receive pipelines perform on outgoing MDNs, see [Generating an Outgoing MDN](../core/generating-an-outgoing-mdn.md).</span></span>  
  
 <span data-ttu-id="67ffb-133">**同期モード**</span><span class="sxs-lookup"><span data-stu-id="67ffb-133">**Synchronous Mode**</span></span>  
  
 <span data-ttu-id="67ffb-134">EDI メッセージが AS2 経由で同期モードで送信される場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はその同期接続を経由して MDN を返し、接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="67ffb-134">If an EDI message is sent over AS2 in synchronous mode, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will return the MDN over that synchronous connection and then close the connection.</span></span> <span data-ttu-id="67ffb-135">接続が閉じられているので、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はその接続経由で EDI 受信確認 (997、TA1、または CONTRL) を返信できません。</span><span class="sxs-lookup"><span data-stu-id="67ffb-135">Since the connection has been closed, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot return an EDI acknowledgment (997, TA1, or CONTRL) over that connection.</span></span> <span data-ttu-id="67ffb-136">EDI 受信確認は、AS2 経由で常に非同期に送信されます。</span><span class="sxs-lookup"><span data-stu-id="67ffb-136">EDI acknowledgments are always sent asynchronously over AS2.</span></span>  
  
 <span data-ttu-id="67ffb-137">MDN は AS2EDIReceive パイプラインによって生成され、メッセージ ボックスにルーティングされた後、要求 - 応答の受信ポートの一部である AS2Send パイプラインによって自動的に取得されます。</span><span class="sxs-lookup"><span data-stu-id="67ffb-137">The MDN will be generated by the AS2EDIReceive pipeline, routed by that pipeline to the MessageBox, and then automatically picked up by the AS2Send pipeline that is part of the request response receive port.</span></span>  
  
 <span data-ttu-id="67ffb-138">**非同期モード**</span><span class="sxs-lookup"><span data-stu-id="67ffb-138">**Asynchronous Mode**</span></span>  
  
 <span data-ttu-id="67ffb-139">EDIINT/AS2 でエンコードされたメッセージが HTTP/HTTPS トランスポート経由で非同期モードで送信される場合は、MDN を個別に返すための送信ポートを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67ffb-139">If an EDIINT/AS2-encoded message is sent over HTTP/HTTPS transport in asynchronous mode, you must create a send port to return the MDN separately.</span></span> <span data-ttu-id="67ffb-140">この送信ポートは、非同期の MDN および EDI 受信確認の両方を返すように構成できます。</span><span class="sxs-lookup"><span data-stu-id="67ffb-140">You can configure this send port to return both asynchronous MDNs and EDI acknowledgments.</span></span> <span data-ttu-id="67ffb-141">これが動的送信ポートである場合は、メッセージのヘッダーの Receipt-Delivery-Notification 行にあるアドレスを使用してメッセージを取引先にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="67ffb-141">If it is a dynamic send port, it will use the address in the Receipt-Delivery-Notification line in the header of the message to route the message to the trading partner.</span></span> <span data-ttu-id="67ffb-142">静的送信ポートである場合は、ポート プロパティで設定されたアドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="67ffb-142">If it is a static send port, it will use the address configured in port properties.</span></span> <span data-ttu-id="67ffb-143">この送信ポートは、`EdiIntAS.IsAS2AsynchronousMDN==True` フィルター式を使用して非同期 MDN をサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="67ffb-143">This send port subscribes to the asynchronous MDN by using an `EdiIntAS.IsAS2AsynchronousMDN==True` filter expression.</span></span>  
  
 <span data-ttu-id="67ffb-144">非同期処理では、AS2EdiReceive パイプラインは MDN だけでなく HTTP 応答も生成します。</span><span class="sxs-lookup"><span data-stu-id="67ffb-144">In asynchronous processing, the AS2EdiReceive pipeline will generate an HTTP response in addition to the MDN.</span></span> <span data-ttu-id="67ffb-145">受信ポートは、受信ポートと送信パーティ間の HTTP 接続を経由して元の送信者に HTTP 応答を返し、元の送信者がその接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="67ffb-145">The receive port returns the HTTP response to the original sender over the HTTP connection between the receive port and the sending party, which closes that connection.</span></span> <span data-ttu-id="67ffb-146">これが必要なのは、同期接続が MDN によって閉じられないためです。</span><span class="sxs-lookup"><span data-stu-id="67ffb-146">This is necessary because the synchronous connection is not closed by the MDN.</span></span>  
  
 <span data-ttu-id="67ffb-147">BizTalk が EDIINT/AS2 でエンコードされたメッセージを HTTP/HTTPS 経由で送受信できても、EDI でエンコードされたペイロードの処理が失敗する場合、元のメッセージの送信者は、AS2 の処理が成功したことを示す MDN と EDI の処理が失敗したことを示す EDI 受信確認の両方を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="67ffb-147">If BizTalk transports an EDIINT/AS2-encoded message over HTTP/HTTPS, but processing of the EDI-encoded payload fails, the sender of the original message would receive both an MDN indicating successful AS2 processing and an EDI acknowledgment indicating a failure in EDI processing.</span></span> <span data-ttu-id="67ffb-148">EDI でエンコードされたペイロードは中断され、エラーが通知されます。</span><span class="sxs-lookup"><span data-stu-id="67ffb-148">The EDI-encoded payload would be suspended and an error would be posted.</span></span>  
  
## <a name="processing-the-received-edi-payload"></a><span data-ttu-id="67ffb-149">受信した EDI ペイロードの処理</span><span class="sxs-lookup"><span data-stu-id="67ffb-149">Processing the Received EDI Payload</span></span>  
 <span data-ttu-id="67ffb-150">場合、**受信バッチ処理オプション**に設定されているアグリーメントの EDI**分割されたインターチェンジ**、AS2EdiReceive 受信パイプラインは、双方向に関連付けられている要求の応答の受信場所の解析、EDI メッセージを EDI トランザクションごとに個別の XML メッセージに設定します。</span><span class="sxs-lookup"><span data-stu-id="67ffb-150">If the **Inbound batch processing option** for an EDI agreement is set to **Split Interchange**, the AS2EdiReceive receive pipeline associated with the two-way request response receive location parses the EDI message into a separate XML message for each EDI transaction set.</span></span> <span data-ttu-id="67ffb-151">場合、**受信バッチ処理オプション**に設定されている**インターチェンジの保存**、受信パイプラインは EDI メッセージを解析できません。</span><span class="sxs-lookup"><span data-stu-id="67ffb-151">If the **Inbound batch processing option** is set to **Preserve Interchange**, the receive pipeline will not parse the EDI message.</span></span>  
  
 <span data-ttu-id="67ffb-152">受信パイプラインは、XML トランザクション セットまたは保存された EDI インターチェンジを、BizTalk のメッセージ ボックスにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="67ffb-152">The receive pipeline routes the XML transaction sets or the preserved EDI interchange to the BizTalk MessageBox.</span></span>  
  
 <span data-ttu-id="67ffb-153">メッセージをバックエンド アプリケーションにルーティングする必要がある場合は、送信ポートが XML メッセージを取得してアプリケーションにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="67ffb-153">If the message is to be routed to a back-end application, a send port picks up the XML message and routes it to the application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67ffb-154">この送信ポートの種類は任意で決定できます。</span><span class="sxs-lookup"><span data-stu-id="67ffb-154">This send port can be of any type.</span></span>  
  
## <a name="sending-the-edi-acknowledgment"></a><span data-ttu-id="67ffb-155">EDI 受信確認の送信</span><span class="sxs-lookup"><span data-stu-id="67ffb-155">Sending the EDI Acknowledgment</span></span>  
 <span data-ttu-id="67ffb-156">EDI 受信確認が有効にされている場合、AS2EdiReceive 受信パイプラインの EDI 逆アセンブラーによって EDI 受信確認が生成されます (有効になっている場合)。</span><span class="sxs-lookup"><span data-stu-id="67ffb-156">If an EDI acknowledgment was enabled, the EDI Disassembler in the AS2EdiReceive receive pipeline will generate EDI acknowledgments (if enabled).</span></span> <span data-ttu-id="67ffb-157">EDI 受信確認は、AS2EdiSend 送信パイプラインによって、別の一方向送信ポートで送信される必要があります。</span><span class="sxs-lookup"><span data-stu-id="67ffb-157">The EDI acknowledgments must be sent by the AS2EdiSend send pipeline in a separate one-way send port.</span></span>  
  
 <span data-ttu-id="67ffb-158">双方向の要求-応答を設定した場合の受信ポートの EDI および AS2 メッセージを応答として同期 MDN または (非同期 MDN の場合)、HTTP 応答を返す、**要求-応答で送信パイプラインに確認をルーティングの受信ポート**プロパティ (設定、**ローカル ホストの設定**で一方向 EDI アグリーメントのページ、**アグリーメントのプロパティ** ダイアログ ボックス) は無視されます。</span><span class="sxs-lookup"><span data-stu-id="67ffb-158">If you set up a two-way request-response receive port for EDI/AS2 messages to return a synchronous MDN or an HTTP response (in the case of an asynchronous MDN), the **Route ACK to send pipeline on request-response receive port** property (set in the **Local Host Settings** page of the one-way EDI agreement in the **Agreement Properties** dialog box) will be ignored.</span></span> <span data-ttu-id="67ffb-159">このプロパティがオンになっていても、送信パイプラインは EDI 受信確認ではなく同期 MDN または HTTP 応答を返します。</span><span class="sxs-lookup"><span data-stu-id="67ffb-159">Even if this property is checked, the send pipeline will return either a synchronous MDN or an HTTP response, not an EDI acknowledgment.</span></span>  
  
 <span data-ttu-id="67ffb-160">詳細については、次を参照してください。 [EDI 受信確認を送信する](../core/sending-an-edi-acknowledgment.md)です。</span><span class="sxs-lookup"><span data-stu-id="67ffb-160">For more information, see [Sending an EDI Acknowledgment](../core/sending-an-edi-acknowledgment.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67ffb-161">参照</span><span class="sxs-lookup"><span data-stu-id="67ffb-161">See Also</span></span>  
 [<span data-ttu-id="67ffb-162">BizTalk Server が AS2 メッセージを受信する方法</span><span class="sxs-lookup"><span data-stu-id="67ffb-162">How BizTalk Server Receives AS2 Messages</span></span>](../core/how-biztalk-server-receives-as2-messages.md)