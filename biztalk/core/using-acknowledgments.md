---
title: 受信確認の使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, publishing
- messages, acknowledgements
- BTS.AckSendPortID property
- BTS.AckSendPortName property
- BTS.AckType property
- BTS.AckFailureCode property
- BTS.AckID property
- acknowledgements, positive
- SOAP fault
- BTS.AckReceivePortID property
- BTS.AckReceivePortName property
- BTS.AckInboundTransportLocation property
- BTS.AckOutboundTransportLocation property
- messages, successful transmission
- BTS.AckDescription property
- orchestrations, messages
- acknowledgements, negative
- BTS.CorrelationToken property
- BTS.AckFailureCategory property
- positive acknowledgements (ACK)
- BTS.AckOwnerID property
ms.assetid: 2e5986d4-9633-4b7b-8ff3-fa3da93c5400
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec79910977625c7e93bac1e70b0f482a0db67677
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399950"
---
# <a name="using-acknowledgments"></a><span data-ttu-id="43055-102">受信確認の使用</span><span class="sxs-lookup"><span data-stu-id="43055-102">Using Acknowledgments</span></span>
<span data-ttu-id="43055-103">BizTalk メッセージング エンジンは、ポート経由でメッセージの処理中に発生した状態に肯定受信確認応答 (ACK) および否定受信確認応答 (NACK) を生成します。</span><span class="sxs-lookup"><span data-stu-id="43055-103">The BizTalk Messaging Engine generates positive acknowledgments (ACK) and negative acknowledgments (NACK) in response to conditions encountered during the processing of a message through a port.</span></span> <span data-ttu-id="43055-104">BizTalk Server では、メッセージの送信が成功を示す肯定受信確認と転送の失敗やメッセージの中断を示す否定受信確認応答をパブリッシュします。</span><span class="sxs-lookup"><span data-stu-id="43055-104">BizTalk Server publishes a positive acknowledgment to indicate successful transmission of a message and a negative acknowledgment to indicate transmission failure and suspension of a message.</span></span>  
  
## <a name="why-use-acknowledgments"></a><span data-ttu-id="43055-105">受信確認を使用する理由</span><span class="sxs-lookup"><span data-stu-id="43055-105">Why Use Acknowledgments?</span></span>  
 <span data-ttu-id="43055-106">肯定および否定受信確認は、メッセージが送信先に到着したか、途中の 1 つまたは複数の問題が発生したかを判断するために使用できる強力なフィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="43055-106">Positive and negative acknowledgments provide strong feedback that you can use to determine if a message arrived at its destination or encountered one or more problems along the way.</span></span> <span data-ttu-id="43055-107">たとえば、受信確認は便利な場合です。</span><span class="sxs-lookup"><span data-stu-id="43055-107">For example, acknowledgments are useful when:</span></span>  
  
- <span data-ttu-id="43055-108">スキーマ検証のための新しい取引先パートナーとその他のエラーの受信ポートを監視するには。</span><span class="sxs-lookup"><span data-stu-id="43055-108">You want to monitor a receive port for a new trading partner for schema validation and other errors.</span></span>  
  
- <span data-ttu-id="43055-109">正常に承認のため、パートナーに送信されるか (たとえば、パートナーのサーバーでは、ダウン) 場合、送信が失敗した場合は「失敗」の場合は、「インプロセス」として承認用に送信、ローン申請の状態をマークするには。</span><span class="sxs-lookup"><span data-stu-id="43055-109">You want to mark the status of a loan request sent out for approval as "in process" if it is successfully sent to a partner for approval or "failed" if transmission fails (for example, if the partner's server is down).</span></span>  
  
- <span data-ttu-id="43055-110">複数の購買発注書を含むインターチェンジを処理し、送信または転送に失敗した注文数を追跡します。</span><span class="sxs-lookup"><span data-stu-id="43055-110">You process interchanges containing multiple purchase orders and want to track the number of orders that are transmitted or fail transmission.</span></span>  
  
  <span data-ttu-id="43055-111">これらの各シナリオは、受信確認とフィルターを使用するコンテンツ ベース ルーティングを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="43055-111">You can accomplish each of these scenarios by using acknowledgments and content-based routing that uses filters.</span></span>  
  
## <a name="routing-acknowledgments"></a><span data-ttu-id="43055-112">受信確認のルーティング</span><span class="sxs-lookup"><span data-stu-id="43055-112">Routing Acknowledgments</span></span>  
 <span data-ttu-id="43055-113">ACK または NACK が発行されると、すべての ACK または NACK を原因となったメッセージからメッセージ コンテキスト プロパティは降格されます。</span><span class="sxs-lookup"><span data-stu-id="43055-113">When an ACK or NACK is published, all of the message context properties from the message that caused the ACK/NACK are demoted.</span></span> <span data-ttu-id="43055-114">昇格されたプロパティは、受信確認をフローしません。</span><span class="sxs-lookup"><span data-stu-id="43055-114">Any properties that were promoted do not flow to the acknowledgment.</span></span> <span data-ttu-id="43055-115">受信確認をルーティングするには、次のプロパティを使用してフィルターを作成、 **BTS**名前空間。</span><span class="sxs-lookup"><span data-stu-id="43055-115">To route an acknowledgment, build a filter using the following properties from the **BTS** namespace:</span></span>  
  
|<span data-ttu-id="43055-116">プロパティ名</span><span class="sxs-lookup"><span data-stu-id="43055-116">Property name</span></span>|<span data-ttu-id="43055-117">データ型</span><span class="sxs-lookup"><span data-stu-id="43055-117">Data type</span></span>|<span data-ttu-id="43055-118">説明</span><span class="sxs-lookup"><span data-stu-id="43055-118">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="43055-119">BTS します。AckFailureCategory</span><span class="sxs-lookup"><span data-stu-id="43055-119">BTS.AckFailureCategory</span></span>|<span data-ttu-id="43055-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="43055-120">xs:int</span></span>|<span data-ttu-id="43055-121">識別、 **ErrorCategory**場所と、中断の理由を提供します。</span><span class="sxs-lookup"><span data-stu-id="43055-121">Identifies the **ErrorCategory**, which gives the place and reason for the suspension.</span></span>|  
|<span data-ttu-id="43055-122">BTS.AckFailureCode</span><span class="sxs-lookup"><span data-stu-id="43055-122">BTS.AckFailureCode</span></span>|<span data-ttu-id="43055-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="43055-123">xs:string</span></span>|<span data-ttu-id="43055-124">識別、 **ErrorCode**場所と、中断の理由を提供します。</span><span class="sxs-lookup"><span data-stu-id="43055-124">Identifies the **ErrorCode**, which gives the place and reason for the suspension.</span></span>|  
|<span data-ttu-id="43055-125">BTS.AckType</span><span class="sxs-lookup"><span data-stu-id="43055-125">BTS.AckType</span></span>|<span data-ttu-id="43055-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="43055-126">xs:string</span></span>|<span data-ttu-id="43055-127">値は、肯定受信確認と NACK の ACK を否定受信確認の場合です。</span><span class="sxs-lookup"><span data-stu-id="43055-127">Value is ACK for a positive acknowledgment and NACK for a negative acknowledgment.</span></span>|  
|<span data-ttu-id="43055-128">BTS します。AckID</span><span class="sxs-lookup"><span data-stu-id="43055-128">BTS.AckID</span></span>|<span data-ttu-id="43055-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="43055-129">xs:string</span></span>|<span data-ttu-id="43055-130">識別、 **MessageID**元のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="43055-130">Identifies the **MessageID** of the original message.</span></span>|  
|<span data-ttu-id="43055-131">BTS.AckOwnerID</span><span class="sxs-lookup"><span data-stu-id="43055-131">BTS.AckOwnerID</span></span>|<span data-ttu-id="43055-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="43055-132">xs:string</span></span>|<span data-ttu-id="43055-133">元のメッセージ インスタンス ID を識別します。</span><span class="sxs-lookup"><span data-stu-id="43055-133">Identifies the instance ID from the original message.</span></span>|  
|<span data-ttu-id="43055-134">BTS.CorrelationToken</span><span class="sxs-lookup"><span data-stu-id="43055-134">BTS.CorrelationToken</span></span>|<span data-ttu-id="43055-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="43055-135">xs:string</span></span>|<span data-ttu-id="43055-136">1 つが存在する場合は、元のメッセージの関連付けトークンを識別します。</span><span class="sxs-lookup"><span data-stu-id="43055-136">Identifies the correlation token from the original message if one is present.</span></span>|  
|<span data-ttu-id="43055-137">BTS します。AckDescription</span><span class="sxs-lookup"><span data-stu-id="43055-137">BTS.AckDescription</span></span>|<span data-ttu-id="43055-138">xs:string</span><span class="sxs-lookup"><span data-stu-id="43055-138">xs:string</span></span>|<span data-ttu-id="43055-139">識別、 **ErrorDescription**場所と、中断の理由を提供します。</span><span class="sxs-lookup"><span data-stu-id="43055-139">Identifies the **ErrorDescription**, which gives the place and reason for the suspension.</span></span>|  
|<span data-ttu-id="43055-140">BTS.AckSendPortID</span><span class="sxs-lookup"><span data-stu-id="43055-140">BTS.AckSendPortID</span></span>|<span data-ttu-id="43055-141">xs:string</span><span class="sxs-lookup"><span data-stu-id="43055-141">xs:string</span></span>|<span data-ttu-id="43055-142">識別、 **SendPortID**元のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="43055-142">Identifies the **SendPortID** from the original message.</span></span>|  
|<span data-ttu-id="43055-143">BTS.AckSendPortName</span><span class="sxs-lookup"><span data-stu-id="43055-143">BTS.AckSendPortName</span></span>|<span data-ttu-id="43055-144">xs:string</span><span class="sxs-lookup"><span data-stu-id="43055-144">xs:string</span></span>|<span data-ttu-id="43055-145">識別、 **SendPortName**元のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="43055-145">Identifies the **SendPortName** from the original message.</span></span>|  
|<span data-ttu-id="43055-146">BTS します。AckOutboundTransportLocation</span><span class="sxs-lookup"><span data-stu-id="43055-146">BTS.AckOutboundTransportLocation</span></span>|<span data-ttu-id="43055-147">xs:string</span><span class="sxs-lookup"><span data-stu-id="43055-147">xs:string</span></span>|<span data-ttu-id="43055-148">識別、 **OutboundTransportLocation**元のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="43055-148">Identifies the **OutboundTransportLocation** from the original message.</span></span>|  
|<span data-ttu-id="43055-149">BTS します。AckReceivePortID</span><span class="sxs-lookup"><span data-stu-id="43055-149">BTS.AckReceivePortID</span></span>|<span data-ttu-id="43055-150">xs:string</span><span class="sxs-lookup"><span data-stu-id="43055-150">xs:string</span></span>|<span data-ttu-id="43055-151">識別、 **ReceivePortID**元のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="43055-151">Identifies the **ReceivePortID** from the original message.</span></span>|  
|<span data-ttu-id="43055-152">BTS.AckReceivePortName</span><span class="sxs-lookup"><span data-stu-id="43055-152">BTS.AckReceivePortName</span></span>|<span data-ttu-id="43055-153">xs:string</span><span class="sxs-lookup"><span data-stu-id="43055-153">xs:string</span></span>|<span data-ttu-id="43055-154">識別、 **ReceivePortName**元のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="43055-154">Identifies the **ReceivePortName** from the original message.</span></span>|  
|<span data-ttu-id="43055-155">BTS します。AckInboundTransportLocation</span><span class="sxs-lookup"><span data-stu-id="43055-155">BTS.AckInboundTransportLocation</span></span>|<span data-ttu-id="43055-156">xs:string</span><span class="sxs-lookup"><span data-stu-id="43055-156">xs:string</span></span>|<span data-ttu-id="43055-157">識別、 **InboundTransportLocation**元のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="43055-157">Identifies the **InboundTransportLocation** from the original message.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="43055-158">エラー情報を含むプロパティは、ので、正の配信は Ack に存在しません。</span><span class="sxs-lookup"><span data-stu-id="43055-158">The properties that contain error information are not present in ACKs because they signal a positive delivery.</span></span>  
  
## <a name="negative-acknowledgment-message-body"></a><span data-ttu-id="43055-159">否定受信確認応答メッセージの本文</span><span class="sxs-lookup"><span data-stu-id="43055-159">Negative Acknowledgment Message Body</span></span>  
 <span data-ttu-id="43055-160">多くの肯定または否定応答に関する重要な情報は、コンテキスト プロパティに含まれています。</span><span class="sxs-lookup"><span data-stu-id="43055-160">Much of the important information about a positive or negative acknowledgment is contained in the context properties.</span></span> <span data-ttu-id="43055-161">Nack メッセージには、コンテキストのプロパティだけでなく、SOAP エラーを含むメッセージのボディ部も含まれます。</span><span class="sxs-lookup"><span data-stu-id="43055-161">In addition to the context properties, NACKs also contain a message body part containing a SOAP fault.</span></span> <span data-ttu-id="43055-162">SOAP エラーの形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="43055-162">The format of the SOAP fault is as follows:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<SOAP:Envelope xmlns:SOAP="http://schemas.xmlsoap.org/soap/envelope/" SOAP:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
  <SOAP:Body>  
    <SOAP:Fault>  
      <faultcode>Microsoft BizTalk Server Negative Acknowledgment </faultcode>  
      <faultstring>An error occurred while processing the message, refer to the details section for more information </faultstring>  
      <faultactor>C:\Projects\Sample\Locations\Response\FM_%MessageID%.xml</faultactor>  
      <detail>  
        <ns0:NACK Type="NACK" xmlns:ns0="http://schema.microsoft.com/BizTalk/2003/NACKMessage.xsd">  
          <NAckID>{FFB1A60B-E593-4620-8897-4E9C7030A937}</NAckID>  
          <ErrorCode>0xc0c01658</ErrorCode>  
          <ErrorCategory>0</ErrorCategory>  
          <ErrorDescription>There was a failure executing the send pipeline: "Microsoft.BizTalk.DefaultPipelines.XMLTransmit, Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" Source: "XML assembler" Send Port: "Failed Message" URI: "C:\Projects\Sample\Locations\Response\FM_%MessageID%.xml" Reason: This Assembler cannot retrieve a document specification using this type: "http://Sample#Unknown".  </ErrorDescription>  
        </ns0:NACK>  
      </detail>  
    </SOAP:Fault>  
  </SOAP:Body>  
</SOAP:Envelope>  
```  
  
 <span data-ttu-id="43055-163">アダプターによって発生した例外メッセージは、ErrorDescription 要素の SOAP 詳細セクションでです。</span><span class="sxs-lookup"><span data-stu-id="43055-163">The exception message raised by the adapter is in the SOAP Detail section in the ErrorDescription element.</span></span>  
  
### <a name="accessing-the-message-body-from-an-orchestration"></a><span data-ttu-id="43055-164">オーケストレーションからメッセージの本文にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="43055-164">Accessing the Message Body from an Orchestration</span></span>  
 <span data-ttu-id="43055-165">配信通知を必要とするオーケストレーション ポートがある場合は、転送エラーの発生時にスローされる DeliveryFailureException は、NACK メッセージ本文に含まれる SOAP エラーから逆シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="43055-165">If you have an orchestration port that requires delivery notification, the DeliveryFailureException that is thrown on a transmission failure is deserialized from the SOAP fault that is contained in the NACK message body.</span></span> <span data-ttu-id="43055-166">オーケストレーション内から例外メッセージ文字列にアクセスするには、DeliveryFailureException を SoapException にキャストし、次のコードに示すようにし、InnerXml にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="43055-166">To access the exception message string from within your orchestration, cast the DeliveryFailureException to a SoapException and then access the InnerXml as shown in the following code:</span></span>  
  
```  
// Cast the DeliveryFailureException to a SoapException…  
System.Web.Services.Protocols.SoapException se = (System.Web.Services.Protocols.SoapException)e.InnerException;  
System.Diagnostics.Trace.WriteLine(se.Detail.InnerXml);  
//e is an Microsoft.XLANGs.BaseTypes.DeliveryFailureException  
//object type created in an Exception handler  
```  
  
 <span data-ttu-id="43055-167">上記のコード サンプルは、次のような XML フラグメントを返します。</span><span class="sxs-lookup"><span data-stu-id="43055-167">The preceding code sample returns an XML fragment similar to the following:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<ns0:NACK Type="NACK" xmlns:ns0="http://schema.microsoft.com/BizTalk/2003/NACKMessage.xsd">  
  <NAckID>{FFB1A60B-E593-4620-8897-4E9C7030A937}</NAckID>  
  <ErrorCode>0xc0c01658</ErrorCode>  
  <ErrorCategory>0</ErrorCategory>  
  <ErrorDescription>There was a failure executing the send pipeline: "Microsoft.BizTalk.DefaultPipelines.XMLTransmit, Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" Source: "XML assembler" Send Port: "Failed Message" URI: "C:\Projects\Sample\Locations\Response\FM_%MessageID%.xml" Reason: This Assembler cannot retrieve a document specification using this type: "http://Sample#Unknown".</ErrorDescription>  
</ns0:NACK>  
```  
  
## <a name="when-is-an-acknowledgment-published"></a><span data-ttu-id="43055-168">受信確認が発行される場合</span><span class="sxs-lookup"><span data-stu-id="43055-168">When Is an Acknowledgment Published?</span></span>  
 <span data-ttu-id="43055-169">少なくとも 1 つの一致するサブスクリプションが提供される (ACK) の正と負の値 (NACK) の受信確認の両方が失敗した時点で、メッセージ ボックス データベースに発行されます。</span><span class="sxs-lookup"><span data-stu-id="43055-169">Both positive (ACK) and negative (NACK) acknowledgments are published to the MessageBox database at the point of failure provided there is at least one matching subscription.</span></span> <span data-ttu-id="43055-170">たとえば、受信ポートからメッセージを読み取るし、NACK サブスクリプションがないために、BizTalk Server では、一致するスキーマを見つけることができない場合、メッセージが中断 (かどうか失敗したメッセージのルーティングが有効でない)、NACK を公開しません</span><span class="sxs-lookup"><span data-stu-id="43055-170">For example, if BizTalk Server cannot find a matching schema for a message read from a receive port and there are no NACK subscriptions, it suspends the message (if failed message routing has not been enabled) and does not publish a NACK</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43055-171">参照</span><span class="sxs-lookup"><span data-stu-id="43055-171">See Also</span></span>  
 <span data-ttu-id="43055-172">[エラー処理](../core/error-handling.md) </span><span class="sxs-lookup"><span data-stu-id="43055-172">[Error Handling](../core/error-handling.md) </span></span>  
 [<span data-ttu-id="43055-173">失敗したメッセージのルーティングを使用します。</span><span class="sxs-lookup"><span data-stu-id="43055-173">Using Failed Message Routing</span></span>](../core/using-failed-message-routing.md)