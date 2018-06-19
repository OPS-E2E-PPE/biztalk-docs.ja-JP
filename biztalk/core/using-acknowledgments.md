---
title: 受信確認の使用 |Microsoft ドキュメント
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
ms.openlocfilehash: 0c3a5363ee70a67c5882088af9fa3d2f4b805823
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288186"
---
# <a name="using-acknowledgments"></a><span data-ttu-id="dcbbf-102">受信確認の使用</span><span class="sxs-lookup"><span data-stu-id="dcbbf-102">Using Acknowledgments</span></span>
<span data-ttu-id="dcbbf-103">BizTalk メッセージング エンジンは、ポートを通じたメッセージの処理中に発生した条件に応じて、肯定受信確認応答 (ACK) および否定受信確認応答 (NACK) を生成します。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-103">The BizTalk Messaging Engine generates positive acknowledgments (ACK) and negative acknowledgments (NACK) in response to conditions encountered during the processing of a message through a port.</span></span> <span data-ttu-id="dcbbf-104">BizTalk Server では、メッセージの転送が成功したことを示す受信確認、および転送の失敗やメッセージの中断を示す否定受信確認応答を作成します。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-104">BizTalk Server publishes a positive acknowledgment to indicate successful transmission of a message and a negative acknowledgment to indicate transmission failure and suspension of a message.</span></span>  
  
## <a name="why-use-acknowledgments"></a><span data-ttu-id="dcbbf-105">受信確認を使用する理由</span><span class="sxs-lookup"><span data-stu-id="dcbbf-105">Why Use Acknowledgments?</span></span>  
 <span data-ttu-id="dcbbf-106">受信確認および否定受信確認応答は、強力なフィードバックを提供します。このフィードバックを使用して、メッセージが送信先に到達したかどうか、途中で問題が発生したかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-106">Positive and negative acknowledgments provide strong feedback that you can use to determine if a message arrived at its destination or encountered one or more problems along the way.</span></span> <span data-ttu-id="dcbbf-107">たとえば、受信確認は、次の場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-107">For example, acknowledgments are useful when:</span></span>  
  
-   <span data-ttu-id="dcbbf-108">スキーマの検証や他のエラーの調査を行うため、新しい取引先の受信ポートを監視する。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-108">You want to monitor a receive port for a new trading partner for schema validation and other errors.</span></span>  
  
-   <span data-ttu-id="dcbbf-109">取引先に承認用のローン要求が正常に送信された場合に、"インプロセス" としてその状態をマークする。または、転送に失敗した場合 (取引先のサーバーがダウンしている場合など) に "失敗" としてその状態をマークする。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-109">You want to mark the status of a loan request sent out for approval as "in process" if it is successfully sent to a partner for approval or "failed" if transmission fails (for example, if the partner's server is down).</span></span>  
  
-   <span data-ttu-id="dcbbf-110">複数の注文書を含むインターチェンジを処理し、転送された注文数または転送に失敗した注文数を追跡する。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-110">You process interchanges containing multiple purchase orders and want to track the number of orders that are transmitted or fail transmission.</span></span>  
  
 <span data-ttu-id="dcbbf-111">フィルターを使用するコンテンツ ベースのルーティングと受信確認を使用して、これらの各シナリオを実現できます。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-111">You can accomplish each of these scenarios by using acknowledgments and content-based routing that uses filters.</span></span>  
  
## <a name="routing-acknowledgments"></a><span data-ttu-id="dcbbf-112">受信確認のルーティング</span><span class="sxs-lookup"><span data-stu-id="dcbbf-112">Routing Acknowledgments</span></span>  
 <span data-ttu-id="dcbbf-113">ACK または NACK が生成されると、ACK/NACK を発生させたメッセージのすべてのメッセージ コンテキスト プロパティが降格します。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-113">When an ACK or NACK is published, all of the message context properties from the message that caused the ACK/NACK are demoted.</span></span> <span data-ttu-id="dcbbf-114">昇格させたプロパティは、受信確認に流れません。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-114">Any properties that were promoted do not flow to the acknowledgment.</span></span> <span data-ttu-id="dcbbf-115">受信確認をルーティングする次のプロパティを使用してフィルターを作成、 **BTS**名前空間。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-115">To route an acknowledgment, build a filter using the following properties from the **BTS** namespace:</span></span>  
  
|<span data-ttu-id="dcbbf-116">プロパティ名</span><span class="sxs-lookup"><span data-stu-id="dcbbf-116">Property name</span></span>|<span data-ttu-id="dcbbf-117">データ型</span><span class="sxs-lookup"><span data-stu-id="dcbbf-117">Data type</span></span>|<span data-ttu-id="dcbbf-118">Description</span><span class="sxs-lookup"><span data-stu-id="dcbbf-118">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="dcbbf-119">BTS.AckFailureCategory</span><span class="sxs-lookup"><span data-stu-id="dcbbf-119">BTS.AckFailureCategory</span></span>|<span data-ttu-id="dcbbf-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="dcbbf-120">xs:int</span></span>|<span data-ttu-id="dcbbf-121">識別、 **ErrorCategory**場所と中断理由を提供します。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-121">Identifies the **ErrorCategory**, which gives the place and reason for the suspension.</span></span>|  
|<span data-ttu-id="dcbbf-122">BTS.AckFailureCode</span><span class="sxs-lookup"><span data-stu-id="dcbbf-122">BTS.AckFailureCode</span></span>|<span data-ttu-id="dcbbf-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="dcbbf-123">xs:string</span></span>|<span data-ttu-id="dcbbf-124">識別、 **ErrorCode**場所と中断理由を提供します。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-124">Identifies the **ErrorCode**, which gives the place and reason for the suspension.</span></span>|  
|<span data-ttu-id="dcbbf-125">BTS.AckType</span><span class="sxs-lookup"><span data-stu-id="dcbbf-125">BTS.AckType</span></span>|<span data-ttu-id="dcbbf-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="dcbbf-126">xs:string</span></span>|<span data-ttu-id="dcbbf-127">受信確認の値は ACK、否定受信確認応答の値は NACK です。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-127">Value is ACK for a positive acknowledgment and NACK for a negative acknowledgment.</span></span>|  
|<span data-ttu-id="dcbbf-128">BTS.AckID</span><span class="sxs-lookup"><span data-stu-id="dcbbf-128">BTS.AckID</span></span>|<span data-ttu-id="dcbbf-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="dcbbf-129">xs:string</span></span>|<span data-ttu-id="dcbbf-130">識別、 **MessageID**元のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-130">Identifies the **MessageID** of the original message.</span></span>|  
|<span data-ttu-id="dcbbf-131">BTS.AckOwnerID</span><span class="sxs-lookup"><span data-stu-id="dcbbf-131">BTS.AckOwnerID</span></span>|<span data-ttu-id="dcbbf-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="dcbbf-132">xs:string</span></span>|<span data-ttu-id="dcbbf-133">元のメッセージのインスタンス ID を確認します。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-133">Identifies the instance ID from the original message.</span></span>|  
|<span data-ttu-id="dcbbf-134">BTS.CorrelationToken</span><span class="sxs-lookup"><span data-stu-id="dcbbf-134">BTS.CorrelationToken</span></span>|<span data-ttu-id="dcbbf-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="dcbbf-135">xs:string</span></span>|<span data-ttu-id="dcbbf-136">元のメッセージの関連付けトークン (存在する場合) を確認します。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-136">Identifies the correlation token from the original message if one is present.</span></span>|  
|<span data-ttu-id="dcbbf-137">BTS.AckDescription</span><span class="sxs-lookup"><span data-stu-id="dcbbf-137">BTS.AckDescription</span></span>|<span data-ttu-id="dcbbf-138">xs:string</span><span class="sxs-lookup"><span data-stu-id="dcbbf-138">xs:string</span></span>|<span data-ttu-id="dcbbf-139">識別、 **ErrorDescription**場所と中断理由を提供します。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-139">Identifies the **ErrorDescription**, which gives the place and reason for the suspension.</span></span>|  
|<span data-ttu-id="dcbbf-140">BTS.AckSendPortID</span><span class="sxs-lookup"><span data-stu-id="dcbbf-140">BTS.AckSendPortID</span></span>|<span data-ttu-id="dcbbf-141">xs:string</span><span class="sxs-lookup"><span data-stu-id="dcbbf-141">xs:string</span></span>|<span data-ttu-id="dcbbf-142">識別、 **SendPortID**元のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-142">Identifies the **SendPortID** from the original message.</span></span>|  
|<span data-ttu-id="dcbbf-143">BTS.AckSendPortName</span><span class="sxs-lookup"><span data-stu-id="dcbbf-143">BTS.AckSendPortName</span></span>|<span data-ttu-id="dcbbf-144">xs:string</span><span class="sxs-lookup"><span data-stu-id="dcbbf-144">xs:string</span></span>|<span data-ttu-id="dcbbf-145">識別、 **SendPortName**元のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-145">Identifies the **SendPortName** from the original message.</span></span>|  
|<span data-ttu-id="dcbbf-146">BTS.AckOutboundTransportLocation</span><span class="sxs-lookup"><span data-stu-id="dcbbf-146">BTS.AckOutboundTransportLocation</span></span>|<span data-ttu-id="dcbbf-147">xs:string</span><span class="sxs-lookup"><span data-stu-id="dcbbf-147">xs:string</span></span>|<span data-ttu-id="dcbbf-148">識別、 **OutboundTransportLocation**元のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-148">Identifies the **OutboundTransportLocation** from the original message.</span></span>|  
|<span data-ttu-id="dcbbf-149">BTS.AckReceivePortID</span><span class="sxs-lookup"><span data-stu-id="dcbbf-149">BTS.AckReceivePortID</span></span>|<span data-ttu-id="dcbbf-150">xs:string</span><span class="sxs-lookup"><span data-stu-id="dcbbf-150">xs:string</span></span>|<span data-ttu-id="dcbbf-151">識別、 **ReceivePortID**元のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-151">Identifies the **ReceivePortID** from the original message.</span></span>|  
|<span data-ttu-id="dcbbf-152">BTS.AckReceivePortName</span><span class="sxs-lookup"><span data-stu-id="dcbbf-152">BTS.AckReceivePortName</span></span>|<span data-ttu-id="dcbbf-153">xs:string</span><span class="sxs-lookup"><span data-stu-id="dcbbf-153">xs:string</span></span>|<span data-ttu-id="dcbbf-154">識別、 **ReceivePortName**元のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-154">Identifies the **ReceivePortName** from the original message.</span></span>|  
|<span data-ttu-id="dcbbf-155">BTS.AckInboundTransportLocation</span><span class="sxs-lookup"><span data-stu-id="dcbbf-155">BTS.AckInboundTransportLocation</span></span>|<span data-ttu-id="dcbbf-156">xs:string</span><span class="sxs-lookup"><span data-stu-id="dcbbf-156">xs:string</span></span>|<span data-ttu-id="dcbbf-157">識別、 **InboundTransportLocation**元のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-157">Identifies the **InboundTransportLocation** from the original message.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="dcbbf-158">エラー情報を含むプロパティは、配信確認で示されるので、ACK に存在しません。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-158">The properties that contain error information are not present in ACKs because they signal a positive delivery.</span></span>  
  
## <a name="negative-acknowledgment-message-body"></a><span data-ttu-id="dcbbf-159">否定受信確認応答のメッセージ本文</span><span class="sxs-lookup"><span data-stu-id="dcbbf-159">Negative Acknowledgment Message Body</span></span>  
 <span data-ttu-id="dcbbf-160">受信確認および否定受信確認応答に関する重要な情報の多くは、コンテキスト プロパティに格納されています。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-160">Much of the important information about a positive or negative acknowledgment is contained in the context properties.</span></span> <span data-ttu-id="dcbbf-161">コンテキスト プロパティ以外に、NACK には、SOAP エラーを含むメッセージの本文部分があります。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-161">In addition to the context properties, NACKs also contain a message body part containing a SOAP fault.</span></span> <span data-ttu-id="dcbbf-162">SOAP エラーの形式を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-162">The format of the SOAP fault is as follows:</span></span>  
  
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
  
 <span data-ttu-id="dcbbf-163">アダプターによって生成される例外メッセージは、ErrorDescription 要素の SOAP 詳細セクションにあります。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-163">The exception message raised by the adapter is in the SOAP Detail section in the ErrorDescription element.</span></span>  
  
### <a name="accessing-the-message-body-from-an-orchestration"></a><span data-ttu-id="dcbbf-164">オーケストレーションからメッセージ本文へアクセスする</span><span class="sxs-lookup"><span data-stu-id="dcbbf-164">Accessing the Message Body from an Orchestration</span></span>  
 <span data-ttu-id="dcbbf-165">配信通知を必要とするオーケストレーション ポートを使用している場合、送信エラーがスローされる DeliveryFailureException は、NACK メッセージ本文に含まれる SOAP エラーからシリアル化解除されます。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-165">If you have an orchestration port that requires delivery notification, the DeliveryFailureException that is thrown on a transmission failure is deserialized from the SOAP fault that is contained in the NACK message body.</span></span> <span data-ttu-id="dcbbf-166">オーケストレーションの例外のメッセージ文字列にアクセスするには、DeliveryFailureException を SoapException にキャストし、次のコードで示されるように InnerXml にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-166">To access the exception message string from within your orchestration, cast the DeliveryFailureException to a SoapException and then access the InnerXml as shown in the following code:</span></span>  
  
```  
// Cast the DeliveryFailureException to a SoapException…  
System.Web.Services.Protocols.SoapException se = (System.Web.Services.Protocols.SoapException)e.InnerException;  
System.Diagnostics.Trace.WriteLine(se.Detail.InnerXml);  
//e is an Microsoft.XLANGs.BaseTypes.DeliveryFailureException  
//object type created in an Exception handler  
```  
  
 <span data-ttu-id="dcbbf-167">上記のサンプル コードは、次のような XML フラグメントを返します。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-167">The preceding code sample returns an XML fragment similar to the following:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<ns0:NACK Type="NACK" xmlns:ns0="http://schema.microsoft.com/BizTalk/2003/NACKMessage.xsd">  
  <NAckID>{FFB1A60B-E593-4620-8897-4E9C7030A937}</NAckID>  
  <ErrorCode>0xc0c01658</ErrorCode>  
  <ErrorCategory>0</ErrorCategory>  
  <ErrorDescription>There was a failure executing the send pipeline: "Microsoft.BizTalk.DefaultPipelines.XMLTransmit, Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" Source: "XML assembler" Send Port: "Failed Message" URI: "C:\Projects\Sample\Locations\Response\FM_%MessageID%.xml" Reason: This Assembler cannot retrieve a document specification using this type: "http://Sample#Unknown".</ErrorDescription>  
</ns0:NACK>  
```  
  
## <a name="when-is-an-acknowledgment-published"></a><span data-ttu-id="dcbbf-168">受信確認が生成される場合とは</span><span class="sxs-lookup"><span data-stu-id="dcbbf-168">When Is an Acknowledgment Published?</span></span>  
 <span data-ttu-id="dcbbf-169">少なくとも 1 つのサブスクリプションが一致する場合、肯定受信確認応答 (ACK) および否定受信確認応答 (NACK) の両方が障害発生時点のメッセージ ボックス データベースに生成されます。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-169">Both positive (ACK) and negative (NACK) acknowledgments are published to the MessageBox database at the point of failure provided there is at least one matching subscription.</span></span> <span data-ttu-id="dcbbf-170">たとえば、受信ポートから読み込まれるメッセージに一致するスキーマを BizTalk Server が検出できず、NACK サブスクリプションがない場合、メッセージが中断され (失敗したメッセージのルーティングが無効の場合)、NACK は生成されません。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-170">For example, if BizTalk Server cannot find a matching schema for a message read from a receive port and there are no NACK subscriptions, it suspends the message (if failed message routing has not been enabled) and does not publish a NACK</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcbbf-171">参照</span><span class="sxs-lookup"><span data-stu-id="dcbbf-171">See Also</span></span>  
 <span data-ttu-id="dcbbf-172">[エラー処理](../core/error-handling.md) </span><span class="sxs-lookup"><span data-stu-id="dcbbf-172">[Error Handling](../core/error-handling.md) </span></span>  
 [<span data-ttu-id="dcbbf-173">失敗したメッセージのルーティングを使用します。</span><span class="sxs-lookup"><span data-stu-id="dcbbf-173">Using Failed Message Routing</span></span>](../core/using-failed-message-routing.md)