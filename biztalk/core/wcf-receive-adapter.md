---
title: "WCF 受信アダプター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, headers
- receive adapters, Web service headers
- SOAP messages, extracting information
- SOAP messages, WCF adapters
- WCF adapters, receive adapters
- messages, SOAP
- receive adapters, WCF adapters
- Web services, headers
- headers [messages]
- SOAP messages, receive adapters
ms.assetid: 6b3d5df1-5d9d-4240-a98f-ea29c3272e38
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb8ea12087b5884370edce13f3ddc6fd6853c7d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="wcf-receive-adapter"></a><span data-ttu-id="a3674-102">WCF 受信アダプタ</span><span class="sxs-lookup"><span data-stu-id="a3674-102">WCF Receive Adapter</span></span>
<span data-ttu-id="a3674-103">WCF 受信アダプターを使用すると、WCF サービス要求を受信できます。</span><span class="sxs-lookup"><span data-stu-id="a3674-103">The WCF receive adapter enables you to receive WCF service requests.</span></span>  
  
## <a name="extracting-the-biztalk-message-body-from-the-soap-message"></a><span data-ttu-id="a3674-104">SOAP メッセージからの BizTalk メッセージ本文の抽出</span><span class="sxs-lookup"><span data-stu-id="a3674-104">Extracting the BizTalk Message Body from the SOAP Message</span></span>  
 <span data-ttu-id="a3674-105">受信 BizTalk メッセージ本文を SOAP メッセージから抽出するには、次のいずれかのオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3674-105">The inbound BizTalk message body can be extracted from the SOAP message by using one of the following options:</span></span>  
  
-   <span data-ttu-id="a3674-106">SOAP Body 要素のコンテンツを抽出する</span><span class="sxs-lookup"><span data-stu-id="a3674-106">Extract the content of the SOAP Body element</span></span>  
  
-   <span data-ttu-id="a3674-107">SOAP エンベロープ全体を抽出する</span><span class="sxs-lookup"><span data-stu-id="a3674-107">Extract the entire SOAP envelope</span></span>  
  
-   <span data-ttu-id="a3674-108">XPath 式を使用して SOAP エンベロープ内の要素のコンテンツを抽出する</span><span class="sxs-lookup"><span data-stu-id="a3674-108">Extract the content of the element inside the SOAP envelope by using an XPath expression</span></span>  
  
 <span data-ttu-id="a3674-109">[トランスポートのプロパティ] ダイアログ ボックスで、これらのオプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="a3674-109">You can configure these options in the transport properties dialog box.</span></span>  
  
#### <a name="extract-the-content-of-the-soap-body-element"></a><span data-ttu-id="a3674-110">SOAP Body 要素のコンテンツを抽出します。</span><span class="sxs-lookup"><span data-stu-id="a3674-110">Extract the Content of the SOAP Body Element</span></span>  
 <span data-ttu-id="a3674-111">このオプションを選択すると、SOAP Body 要素の内部コンテンツが、SOAP メッセージから読み込まれ、BizTalk メッセージのボディ部に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="a3674-111">When this option is selected, the inner content of the SOAP Body element is read from the SOAP message and placed into the body part of the BizTalk message.</span></span>  
  
#### <a name="extract-the-entire-soap-envelope"></a><span data-ttu-id="a3674-112">全体の SOAP エンベロープを抽出します。</span><span class="sxs-lookup"><span data-stu-id="a3674-112">Extract the Entire SOAP Envelope</span></span>  
 <span data-ttu-id="a3674-113">このオプションを選択すると、SOAP エンベロープ全体 (タグを含む) が BizTalk メッセージのボディ部に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="a3674-113">When this option is selected, the entire SOAP envelope including the tag is placed into the body part of the BizTalk message.</span></span>  
  
#### <a name="extract-the-content-of-the-element-by-using-an-xpath-expression"></a><span data-ttu-id="a3674-114">EXPath 式を使用して要素のコンテンツを抽出する</span><span class="sxs-lookup"><span data-stu-id="a3674-114">Extract the Content of the Element by Using an XPath Expression</span></span>  
 <span data-ttu-id="a3674-115">このオプションを選択すると、XPath 式で見つかった、SOAP Body 要素内にある要素の内部コンテンツが、BizTalk メッセージのボディ部に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="a3674-115">When this option is selected, the inner content of the element inside the SOAP Body element that is located by the XPath expression is placed into the body part of the BizTalk message.</span></span> <span data-ttu-id="a3674-116">Body 要素内の残りのデータは無視されます。</span><span class="sxs-lookup"><span data-stu-id="a3674-116">The rest of the data in the Body element is ignored.</span></span> <span data-ttu-id="a3674-117">ノード エンコードの種類を指定する必要があります: 例では、XML、Base64、16 進数、または文字列をエンコードするためです。</span><span class="sxs-lookup"><span data-stu-id="a3674-117">You also need to specify the node encoding—for example, XML, Base64, Hex, or String encoding.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3674-118">XML エンコードを選択すると、要素の外部コンテンツが、XPath 式で検出され、ボディ部に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="a3674-118">When the XML encoding is selected, the outer content of the element is located by the XPath expression and placed into the body part.</span></span>  
  
## <a name="handling-web-services-headers"></a><span data-ttu-id="a3674-119">Web サービス ヘッダーの処理</span><span class="sxs-lookup"><span data-stu-id="a3674-119">Handling Web Services Headers</span></span>  
 <span data-ttu-id="a3674-120">受信アダプターでは、標準 Web サービス ヘッダーのサブセットを BizTalk メッセージ コンテキストに昇格させて、これらのヘッダーの値に基づいたアクセスおよびルーティングを容易にします。</span><span class="sxs-lookup"><span data-stu-id="a3674-120">The receive adapter promotes a subset of the standard Web services headers onto the BizTalk message context to enable easy access and routing based on values of those headers.</span></span> <span data-ttu-id="a3674-121">次の表に、受信アダプターによってメッセージ コンテキストに保存されるプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="a3674-121">The following table lists the properties that will be saved onto the message context by the receive adapter.</span></span> <span data-ttu-id="a3674-122">プロパティは、次の名前空間で定義されて: http://www.w3.org/2005/addressing および http://schemas.microsoft.com/BizTalk/2006/Adapters/WCF-properties です。</span><span class="sxs-lookup"><span data-stu-id="a3674-122">The properties are defined under the following namespaces: http://www.w3.org/2005/addressing and http://schemas.microsoft.com/BizTalk/2006/Adapters/WCF-properties.</span></span>  
  
|<span data-ttu-id="a3674-123">Header</span><span class="sxs-lookup"><span data-stu-id="a3674-123">Header</span></span>|<span data-ttu-id="a3674-124">BizTalk プロパティ名</span><span class="sxs-lookup"><span data-stu-id="a3674-124">BizTalk property name</span></span>|<span data-ttu-id="a3674-125">昇格の有無</span><span class="sxs-lookup"><span data-stu-id="a3674-125">Is promoted?</span></span>|  
|------------|---------------------------|------------------|  
|<span data-ttu-id="a3674-126">操作</span><span class="sxs-lookup"><span data-stu-id="a3674-126">Action</span></span>|<span data-ttu-id="a3674-127">操作</span><span class="sxs-lookup"><span data-stu-id="a3674-127">Action</span></span>|<span data-ttu-id="a3674-128">はい</span><span class="sxs-lookup"><span data-stu-id="a3674-128">Yes</span></span>|  
|<span data-ttu-id="a3674-129">MessageID</span><span class="sxs-lookup"><span data-stu-id="a3674-129">MessageID</span></span>|<span data-ttu-id="a3674-130">MessageID</span><span class="sxs-lookup"><span data-stu-id="a3674-130">MessageID</span></span>|<span data-ttu-id="a3674-131">不可</span><span class="sxs-lookup"><span data-stu-id="a3674-131">No</span></span>|  
|<span data-ttu-id="a3674-132">変換先</span><span class="sxs-lookup"><span data-stu-id="a3674-132">To</span></span>|<span data-ttu-id="a3674-133">変換先</span><span class="sxs-lookup"><span data-stu-id="a3674-133">To</span></span>|<span data-ttu-id="a3674-134">はい</span><span class="sxs-lookup"><span data-stu-id="a3674-134">Yes</span></span>|  
|<span data-ttu-id="a3674-135">ReplyTo/Address</span><span class="sxs-lookup"><span data-stu-id="a3674-135">ReplyTo/Address</span></span>|<span data-ttu-id="a3674-136">ReplyTo</span><span class="sxs-lookup"><span data-stu-id="a3674-136">ReplyTo</span></span>|<span data-ttu-id="a3674-137">はい</span><span class="sxs-lookup"><span data-stu-id="a3674-137">Yes</span></span>|  
|<span data-ttu-id="a3674-138">From/Address</span><span class="sxs-lookup"><span data-stu-id="a3674-138">From/Address</span></span>|<span data-ttu-id="a3674-139">From</span><span class="sxs-lookup"><span data-stu-id="a3674-139">From</span></span>|<span data-ttu-id="a3674-140">はい</span><span class="sxs-lookup"><span data-stu-id="a3674-140">Yes</span></span>|  
|<span data-ttu-id="a3674-141">Sequence/Identifier</span><span class="sxs-lookup"><span data-stu-id="a3674-141">Sequence/Identifier</span></span>|<span data-ttu-id="a3674-142">SequenceId</span><span class="sxs-lookup"><span data-stu-id="a3674-142">SequenceId</span></span>|<span data-ttu-id="a3674-143">はい</span><span class="sxs-lookup"><span data-stu-id="a3674-143">Yes</span></span>|  
|<span data-ttu-id="a3674-144">Sequence/MessageNumber</span><span class="sxs-lookup"><span data-stu-id="a3674-144">Sequence/MessageNumber</span></span>|<span data-ttu-id="a3674-145">SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="a3674-145">SequenceNumber</span></span>|<span data-ttu-id="a3674-146">はい</span><span class="sxs-lookup"><span data-stu-id="a3674-146">Yes</span></span>|  
|<span data-ttu-id="a3674-147">Sequence/LastMessage</span><span class="sxs-lookup"><span data-stu-id="a3674-147">Sequence/LastMessage</span></span>|<span data-ttu-id="a3674-148">SequenceLastMessage</span><span class="sxs-lookup"><span data-stu-id="a3674-148">SequenceLastMessage</span></span>|<span data-ttu-id="a3674-149">はい</span><span class="sxs-lookup"><span data-stu-id="a3674-149">Yes</span></span>|  
|<span data-ttu-id="a3674-150">\<Soap:header ></span><span class="sxs-lookup"><span data-stu-id="a3674-150">\<soap:Header></span></span>|<span data-ttu-id="a3674-151">InboundHeaders</span><span class="sxs-lookup"><span data-stu-id="a3674-151">InboundHeaders</span></span>|<span data-ttu-id="a3674-152">不可</span><span class="sxs-lookup"><span data-stu-id="a3674-152">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3674-153">参照</span><span class="sxs-lookup"><span data-stu-id="a3674-153">See Also</span></span>  
 <span data-ttu-id="a3674-154">[WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="a3674-154">[Specifying the Message Body for the WCF Adapters](../core/specifying-the-message-body-for-the-wcf-adapters.md) </span></span>  
 <span data-ttu-id="a3674-155">[WCF 送信アダプタ](../core/wcf-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="a3674-155">[WCF Send Adapter](../core/wcf-send-adapter.md) </span></span>  
 [<span data-ttu-id="a3674-156">WCF アダプタは?</span><span class="sxs-lookup"><span data-stu-id="a3674-156">What Are the WCF Adapters?</span></span>](../core/what-are-the-wcf-adapters.md)