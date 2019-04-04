---
title: 送信側の AS2 経由で送信 EDI メッセージの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dfb63b22-6e2e-4d4f-b028-301c8d4d53b0
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c00aaae104bfe685945c7b20b62912970582381
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995419"
---
# <a name="send-side-processing-of-an-outgoing-edi-message-over-as2"></a><span data-ttu-id="e3ba4-102">AS2 経由での送信 EDI メッセージの送信側の処理</span><span class="sxs-lookup"><span data-stu-id="e3ba4-102">Send-Side Processing of an Outgoing EDI Message over AS2</span></span>
<span data-ttu-id="e3ba4-103">AS2 経由の EDI メッセージの送信側の処理には、EDI ペイロードを使用した AS2 メッセージの送信と、MDN および EDI 受信確認の受信 (有効な場合) があります。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-103">Send-side processing of an EDI message over AS2 includes sending an AS2 message with the EDI payload and receiving MDN and EDI acknowledgments (if enabled).</span></span>  
  
 <span data-ttu-id="e3ba4-104">AS2EDISend 送信パイプラインは、1 つにまとめた EDI/AS2 メッセージを受信側の取引先に HTTP/HTTPS を経由して送信します。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-104">The AS2EDISend send pipeline sends an assembled EDI/AS2 message to the receiving trading partner over HTTP/HTTPS.</span></span> <span data-ttu-id="e3ba4-105">AS2EDIReceive 受信パイプラインは、AS2 メッセージへの応答としての MDN と、EDI メッセージへの応答として返される EDI 受信確認を受信します。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-105">The AS2EDIReceive receive pipeline receives an MDN returned in response to the AS2 message, and an EDI acknowledgment returned in response to the EDI message.</span></span> <span data-ttu-id="e3ba4-106">これらの各パイプラインは、AS2 メッセージを処理し、AS2 メッセージ内の EDI ペイロードを処理します。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-106">Each of these pipelines processes an AS2 message and processes the EDI payload within an AS2 message.</span></span> <span data-ttu-id="e3ba4-107">これらのパイプラインは、双方向の送信請求 - 応答の HTTP 送信ポートか、一方向の HTTP 送信ポートと一方向の HTTP 受信ポートに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-107">You can include these pipelines in an HTTP two-way solicit response send port, or in a one-way HTTP send port and a one-way HTTP receive port.</span></span>  
  
 <span data-ttu-id="e3ba4-108">AS2 経由で EDI インターチェンジを送信するために、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-108">To send an EDI interchange over AS2, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will perform the following steps:</span></span>  
  
-   <span data-ttu-id="e3ba4-109">EDI ペイロードを送信するための処理</span><span class="sxs-lookup"><span data-stu-id="e3ba4-109">Processing the EDI payload for sending</span></span>  
  
-   <span data-ttu-id="e3ba4-110">AS2 メッセージの送信</span><span class="sxs-lookup"><span data-stu-id="e3ba4-110">Sending the AS2 message</span></span>  
  
-   <span data-ttu-id="e3ba4-111">返された MDN の受信</span><span class="sxs-lookup"><span data-stu-id="e3ba4-111">Receiving the returned MDN</span></span>  
  
-   <span data-ttu-id="e3ba4-112">返された EDI 受信確認の受信</span><span class="sxs-lookup"><span data-stu-id="e3ba4-112">Receiving the returned EDI acknowledgment</span></span>  
  
## <a name="processing-the-edi-payload-for-sending"></a><span data-ttu-id="e3ba4-113">EDI ペイロードを送信するための処理</span><span class="sxs-lookup"><span data-stu-id="e3ba4-113">Processing the EDI Payload for Sending</span></span>  
 <span data-ttu-id="e3ba4-114">AS2 メッセージを作成する前に、AS2EdiSend パイプラインは EDI インターチェンジを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-114">Before creating an AS2 message, the AS2EdiSend pipeline must process the EDI interchange.</span></span> <span data-ttu-id="e3ba4-115">送信バッチ処理が有効になっている場合、トランザクション セットは」の説明に従ってバッチ処理には[バッチ EDI インターチェンジをアセンブル](../core/assembling-a-batched-edi-interchange.md)します。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-115">If outbound batching is enabled, transaction sets will be batched as described in [Assembling a Batched EDI Interchange](../core/assembling-a-batched-edi-interchange.md).</span></span> <span data-ttu-id="e3ba4-116">」の説明に従って、EDI アセンブラーは EDI インターチェンジを作成、 [、EDI アセンブラーのしくみ](../core/how-the-edi-assembler-works.md)します。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-116">The EDI Assembler will create the EDI interchange as described in [How the EDI Assembler Works](../core/how-the-edi-assembler-works.md).</span></span>  
  
## <a name="sending-the-as2-message"></a><span data-ttu-id="e3ba4-117">AS2 メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-117">Sending the AS2 Message</span></span>  
 <span data-ttu-id="e3ba4-118">AS2 送信パイプラインの AS2 エンコーダーは、最初にアグリーメントの解決を実行して、送信メッセージの処理に使用するアグリーメントのプロパティを特定します。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-118">The AS2 Encoder in the AS2 send pipeline first performs agreement resolution to determine the agreement properties to be used to process the outgoing message.</span></span> <span data-ttu-id="e3ba4-119">詳細については、[送信 AS2 メッセージのアグリーメントの解決](../core/agreement-resolution-for-outgoing-as2-messages.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-119">For more information, see [Agreement Resolution for Outgoing AS2 Messages](../core/agreement-resolution-for-outgoing-as2-messages.md).</span></span>  
  
 <span data-ttu-id="e3ba4-120">AS2 エンコーダーは、AS2 メッセージを送信するために必要な一連の HTTP ヘッダーを構築します。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-120">The AS2 Encoder builds the set of HTTP headers required to send an AS2 message.</span></span> <span data-ttu-id="e3ba4-121">これらのヘッダーは `HTTP.UserHttpHeaders` コンテキスト プロパティに追加されます。このコンテキスト プロパティは、複数のヘッダー値から成る単一の文字列です。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-121">It adds these headers to the `HTTP.UserHttpHeaders` context property, which is a single string of header values.</span></span> <span data-ttu-id="e3ba4-122">AS2 エンコーダーは、次の AS2 ヘッダーを `HTTP.UserHttpHeaders` 内に構築します。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-122">The AS2 Encoder builds the following AS2 headers in `HTTP.UserHttpHeaders`.</span></span> <span data-ttu-id="e3ba4-123">AS2 メッセージには、これらのヘッダーが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-123">These headers must be in the AS2 messages.</span></span>  
  
- <span data-ttu-id="e3ba4-124">AS2-To</span><span class="sxs-lookup"><span data-stu-id="e3ba4-124">AS2-To</span></span>  
  
- <span data-ttu-id="e3ba4-125">AS2-From</span><span class="sxs-lookup"><span data-stu-id="e3ba4-125">AS2-From</span></span>  
  
- <span data-ttu-id="e3ba4-126">AS2-Version</span><span class="sxs-lookup"><span data-stu-id="e3ba4-126">AS2-Version</span></span>  
  
- <span data-ttu-id="e3ba4-127">MessageID</span><span class="sxs-lookup"><span data-stu-id="e3ba4-127">MessageID</span></span>  
  
- <span data-ttu-id="e3ba4-128">OriginalMessageID (MDN のみ)</span><span class="sxs-lookup"><span data-stu-id="e3ba4-128">OriginalMessageID (for MDNs only)</span></span>  
  
  <span data-ttu-id="e3ba4-129">場合、 **mdn を要求する**プロパティがチェックされ、パイプラインはメッセージの対応するプロパティとその値に廃棄で通知を確認メッセージの配信オプション、およびの Signed-receipt-micalg AS2 ヘッダーを設定場合に「pcks7 署名」に署名済みの受信プロトコルの AS2 ヘッダーを設定、**署名付き MDN を要求**プロパティがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-129">If the **Request MDN** property is checked, the pipeline will set the Disposition-Notification-To, Receipt-Delivery-Option, and Signed-Receipt-MICalg AS2 headers in the message to the values in the corresponding properties; and it will set the Signed-Receipt-Protocol AS2 header to "pcks7-signature" if the **Request signed MDN** property is checked.</span></span>  
  
  <span data-ttu-id="e3ba4-130">`HTTP.UserHttpHeaders` コンテキスト プロパティが存在しない場合は、AS2 エンコーダーによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-130">If the `HTTP.UserHttpHeaders` context property does not exist, the AS2 Encoder will create it.</span></span> <span data-ttu-id="e3ba4-131">`HTTP.UserHttpHeaders` コンテキスト プロパティが既に存在する場合、新規作成はされず、AS2 エンコーダーはそのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-131">If `HTTP.UserHttpHeaders` already exists, the AS2 Encoder will use it, rather than creating it.</span></span> <span data-ttu-id="e3ba4-132">ユーザーが `HTTP.UserHttpHeaders` を作成し、ヘッダーを書き込んで、メッセージのコンテキストに書き込んだ場合、AS2 エンコーダーではこれらのヘッダーが使用され、他のソースからのヘッダーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-132">If you create `HTTP.UserHttpHeaders`, write headers to it, and then write it to the context of the message, the AS2 Encoder will use those headers, and they will take priority over headers from other sources.</span></span> <span data-ttu-id="e3ba4-133">ただし、AS2-From ヘッダーは例外で、常にアグリーメントのプロパティから取得されます。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-133">The exception to that is the AS2-From header, which is always taken from the agreement properties.</span></span>  
  
  <span data-ttu-id="e3ba4-134">`HTTP.UserHttpHeaders` に AS2 ヘッダーが存在しない場合は、AS2 エンコーダーによって単一のコンテキスト プロパティから追加されます。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-134">If an AS2 header is not in `HTTP.UserHttpHeaders`, the AS2 Encoder will add it from single context properties.</span></span> <span data-ttu-id="e3ba4-135">これは、ユーザーがメッセージのコンテキストに AS2 ヘッダーを昇格させるか書き込むことによって、AS2 ヘッダーを追加できることを意味します (AS2 ヘッダーが `HTTP.UserHttpHeaders` に存在しない場合)。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-135">This means that you can add AS2 headers by promoting or writing them to the context of the message (if they are not already in `HTTP.UserHttpHeaders`).</span></span> <span data-ttu-id="e3ba4-136">`HTTP.UserHttpHeaders`に AS2 ヘッダーが存在せず、コンテキストのプロパティとしても存在しない場合、AS2 エンコーダーは、アグリーメントのプロパティから AS2 ヘッダーを `HTTP.UserHttpHeaders` に追加します。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-136">If an AS2 header is neither in `HTTP.UserHttpHeaders`, nor present as a property in the context, the AS2 Encoder will add it from agreement properties into `HTTP.UserHttpHeaders`.</span></span>  
  
  <span data-ttu-id="e3ba4-137">AS2 エンコーダーは、`HTTP.UserHttpHeaders` プロパティでヘッダーを構築した後、そのヘッダーをメッセージのコンテキストに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-137">After the AS2 Encoder builds the headers in the `HTTP.UserHttpHeaders` property, it writes it to the context of the message.</span></span> <span data-ttu-id="e3ba4-138">HTTP アダプターは `HTTP.UserHttpHeaders` を取得し、`HTTP.UserHttpHeaders` のヘッダー値をメッセージの前に付加します。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-138">The HTTP Adapter picks up `HTTP.UserHttpHeaders`, and prepends the header values from `HTTP.UserHttpHeaders` into the message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3ba4-139">AS2 トランスポートは、HTTP アダプターと共に使用することだけが想定されています。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-139">AS2 transport is intended to work only with the HTTP adapter.</span></span> <span data-ttu-id="e3ba4-140">ただし、適切なコンテキスト プロパティを手動で設定すると、FILE アダプターを使用して AS2 メッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-140">However, if you manually set the appropriate context properties, you can use the FILE Adapter to transport AS2 messages.</span></span> <span data-ttu-id="e3ba4-141">詳細については、[FILE 送信ポートを経由で AS2 メッセージの送信](../core/sending-an-as2-message-over-a-file-send-port.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-141">For more information, see [Sending an AS2 Message over a FILE Send Port](../core/sending-an-as2-message-over-a-file-send-port.md).</span></span>  
  
## <a name="processing-the-returned-mdn"></a><span data-ttu-id="e3ba4-142">返された MDN の処理</span><span class="sxs-lookup"><span data-stu-id="e3ba4-142">Processing the Returned MDN</span></span>  
 <span data-ttu-id="e3ba4-143">MDN が有効になっている場合、双方向送信ポートに関連付けられた受信パイプラインは、AS2 メッセージの受信側パーティから MDN を受信します。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-143">If an MDN is enabled, the receive pipeline associated with the two-way send port receives the MDN from the party that receives the AS2 message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3ba4-144">受信 mdn メッセージに対して、AS2 送信パイプラインを実行する処理の詳細については、[送信 MDN の送信](../core/sending-an-outgoing-mdn.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-144">For more information about the processing that the AS2 send pipelines perform on incoming MDNs, see [Sending an Outgoing MDN](../core/sending-an-outgoing-mdn.md).</span></span>  
  
## <a name="processing-the-returned-edi-acknowledgment"></a><span data-ttu-id="e3ba4-145">返された EDI 受信確認の処理</span><span class="sxs-lookup"><span data-stu-id="e3ba4-145">Processing the Returned EDI Acknowledgment</span></span>  
 <span data-ttu-id="e3ba4-146">EDI 受信確認が有効な場合、双方向送信ポートに関連付けられている受信パイプラインは、EDI メッセージの受信者からの EDI 受信確認も受信します (BizTalk EDI ACK メッセージ タイプに対してフィルターを適用するため)。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-146">If an EDI acknowledgment is enabled, the receive pipeline associated with the two-way send port also receives an EDI acknowledgment from the receiver of the EDI message (because it filters on the BizTalk EDI ACK message type).</span></span> <span data-ttu-id="e3ba4-147">詳細については、[受信確認の処理](../core/processing-a-received-acknowledgment.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3ba4-147">For more information, see [Processing a Received Acknowledgment](../core/processing-a-received-acknowledgment.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3ba4-148">参照</span><span class="sxs-lookup"><span data-stu-id="e3ba4-148">See Also</span></span>  
 [<span data-ttu-id="e3ba4-149">BizTalk Server が AS2 メッセージを送信する方法</span><span class="sxs-lookup"><span data-stu-id="e3ba4-149">How BizTalk Server Sends AS2 Messages</span></span>](../core/how-biztalk-server-sends-as2-messages.md)