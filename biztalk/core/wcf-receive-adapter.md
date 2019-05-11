---
title: WCF アダプターの受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86d7f307a9c7dae45e81e8c9c1e5bcf57a6ef6b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266395"
---
# <a name="wcf-receive-adapter"></a><span data-ttu-id="37aa2-102">WCF 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="37aa2-102">WCF Receive Adapter</span></span>
<span data-ttu-id="37aa2-103">WCF は受信要求を処理すると、WCF 受信アダプターの有効です。</span><span class="sxs-lookup"><span data-stu-id="37aa2-103">The WCF receive adapter enables you to receive WCF service requests.</span></span>  
  
## <a name="extracting-the-biztalk-message-body-from-the-soap-message"></a><span data-ttu-id="37aa2-104">SOAP メッセージから BizTalk メッセージ本文の抽出</span><span class="sxs-lookup"><span data-stu-id="37aa2-104">Extracting the BizTalk Message Body from the SOAP Message</span></span>  
 <span data-ttu-id="37aa2-105">次のオプションのいずれかを使用して SOAP メッセージから受信 BizTalk メッセージ本文を取得できます。</span><span class="sxs-lookup"><span data-stu-id="37aa2-105">The inbound BizTalk message body can be extracted from the SOAP message by using one of the following options:</span></span>  
  
- <span data-ttu-id="37aa2-106">SOAP Body 要素のコンテンツを抽出します。</span><span class="sxs-lookup"><span data-stu-id="37aa2-106">Extract the content of the SOAP Body element</span></span>  
  
- <span data-ttu-id="37aa2-107">SOAP エンベロープ全体を抽出します。</span><span class="sxs-lookup"><span data-stu-id="37aa2-107">Extract the entire SOAP envelope</span></span>  
  
- <span data-ttu-id="37aa2-108">XPath 式を使用して SOAP エンベロープ内の要素のコンテンツを抽出します。</span><span class="sxs-lookup"><span data-stu-id="37aa2-108">Extract the content of the element inside the SOAP envelope by using an XPath expression</span></span>  
  
  <span data-ttu-id="37aa2-109">トランスポートのプロパティ ダイアログ ボックスで、これらのオプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="37aa2-109">You can configure these options in the transport properties dialog box.</span></span>  
  
#### <a name="extract-the-content-of-the-soap-body-element"></a><span data-ttu-id="37aa2-110">SOAP Body 要素のコンテンツを抽出します。</span><span class="sxs-lookup"><span data-stu-id="37aa2-110">Extract the Content of the SOAP Body Element</span></span>  
 <span data-ttu-id="37aa2-111">このオプションを選択すると、SOAP Body 要素の内部コンテンツが、SOAP メッセージから読み取られ、BizTalk メッセージのボディ部に配置されます。</span><span class="sxs-lookup"><span data-stu-id="37aa2-111">When this option is selected, the inner content of the SOAP Body element is read from the SOAP message and placed into the body part of the BizTalk message.</span></span>  
  
#### <a name="extract-the-entire-soap-envelope"></a><span data-ttu-id="37aa2-112">全体の SOAP エンベロープを抽出します。</span><span class="sxs-lookup"><span data-stu-id="37aa2-112">Extract the Entire SOAP Envelope</span></span>  
 <span data-ttu-id="37aa2-113">このオプションを選択すると、タグを含む SOAP エンベロープ全体が BizTalk メッセージのボディ部に配置されます。</span><span class="sxs-lookup"><span data-stu-id="37aa2-113">When this option is selected, the entire SOAP envelope including the tag is placed into the body part of the BizTalk message.</span></span>  
  
#### <a name="extract-the-content-of-the-element-by-using-an-xpath-expression"></a><span data-ttu-id="37aa2-114">XPath 式を使用して、要素のコンテンツを抽出します。</span><span class="sxs-lookup"><span data-stu-id="37aa2-114">Extract the Content of the Element by Using an XPath Expression</span></span>  
 <span data-ttu-id="37aa2-115">このオプションを選択すると、BizTalk メッセージのボディ部には、XPath 式である SOAP Body 要素内の要素の内部コンテンツが配置されます。</span><span class="sxs-lookup"><span data-stu-id="37aa2-115">When this option is selected, the inner content of the element inside the SOAP Body element that is located by the XPath expression is placed into the body part of the BizTalk message.</span></span> <span data-ttu-id="37aa2-116">本文要素のデータの残りの部分は無視されます。</span><span class="sxs-lookup"><span data-stu-id="37aa2-116">The rest of the data in the Body element is ignored.</span></span> <span data-ttu-id="37aa2-117">ノード エンコードの種類を指定する必要があります: 例では、XML、Base64、16 進数、または文字列をエンコードするためです。</span><span class="sxs-lookup"><span data-stu-id="37aa2-117">You also need to specify the node encoding—for example, XML, Base64, Hex, or String encoding.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37aa2-118">XML エンコーディングを選択すると、要素の外側のコンテンツは、XPath 式であるし、ボディ部に配置されます。</span><span class="sxs-lookup"><span data-stu-id="37aa2-118">When the XML encoding is selected, the outer content of the element is located by the XPath expression and placed into the body part.</span></span>  
  
## <a name="handling-web-services-headers"></a><span data-ttu-id="37aa2-119">処理の Web サービス ヘッダー</span><span class="sxs-lookup"><span data-stu-id="37aa2-119">Handling Web Services Headers</span></span>  
 <span data-ttu-id="37aa2-120">受信アダプターが BizTalk メッセージ コンテキストに簡単にアクセスを有効にするのには、標準の Web サービス ヘッダーのサブセットを昇格し、これらのヘッダーの値に基づくルーティングします。</span><span class="sxs-lookup"><span data-stu-id="37aa2-120">The receive adapter promotes a subset of the standard Web services headers onto the BizTalk message context to enable easy access and routing based on values of those headers.</span></span> <span data-ttu-id="37aa2-121">次の表は、受信アダプターによってメッセージ コンテキストに保存されるプロパティを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="37aa2-121">The following table lists the properties that will be saved onto the message context by the receive adapter.</span></span> <span data-ttu-id="37aa2-122">プロパティは、次の名前空間で定義されます:http://www.w3.org/2005/addressingと http://schemas.microsoft.com/BizTalk/2006/Adapters/WCF-propertiesします。</span><span class="sxs-lookup"><span data-stu-id="37aa2-122">The properties are defined under the following namespaces: http://www.w3.org/2005/addressing and http://schemas.microsoft.com/BizTalk/2006/Adapters/WCF-properties.</span></span>  
  
|<span data-ttu-id="37aa2-123">[ヘッダー]</span><span class="sxs-lookup"><span data-stu-id="37aa2-123">Header</span></span>|<span data-ttu-id="37aa2-124">BizTalk プロパティ名</span><span class="sxs-lookup"><span data-stu-id="37aa2-124">BizTalk property name</span></span>|<span data-ttu-id="37aa2-125">昇格の有無</span><span class="sxs-lookup"><span data-stu-id="37aa2-125">Is promoted?</span></span>|  
|------------|---------------------------|------------------|  
|<span data-ttu-id="37aa2-126">操作</span><span class="sxs-lookup"><span data-stu-id="37aa2-126">Action</span></span>|<span data-ttu-id="37aa2-127">操作</span><span class="sxs-lookup"><span data-stu-id="37aa2-127">Action</span></span>|<span data-ttu-id="37aa2-128">はい</span><span class="sxs-lookup"><span data-stu-id="37aa2-128">Yes</span></span>|  
|<span data-ttu-id="37aa2-129">MessageID</span><span class="sxs-lookup"><span data-stu-id="37aa2-129">MessageID</span></span>|<span data-ttu-id="37aa2-130">MessageID</span><span class="sxs-lookup"><span data-stu-id="37aa2-130">MessageID</span></span>|<span data-ttu-id="37aa2-131">いいえ</span><span class="sxs-lookup"><span data-stu-id="37aa2-131">No</span></span>|  
|<span data-ttu-id="37aa2-132">目的</span><span class="sxs-lookup"><span data-stu-id="37aa2-132">To</span></span>|<span data-ttu-id="37aa2-133">目的</span><span class="sxs-lookup"><span data-stu-id="37aa2-133">To</span></span>|<span data-ttu-id="37aa2-134">はい</span><span class="sxs-lookup"><span data-stu-id="37aa2-134">Yes</span></span>|  
|<span data-ttu-id="37aa2-135">ReplyTo アドレス/</span><span class="sxs-lookup"><span data-stu-id="37aa2-135">ReplyTo/Address</span></span>|<span data-ttu-id="37aa2-136">ReplyTo</span><span class="sxs-lookup"><span data-stu-id="37aa2-136">ReplyTo</span></span>|<span data-ttu-id="37aa2-137">はい</span><span class="sxs-lookup"><span data-stu-id="37aa2-137">Yes</span></span>|  
|<span data-ttu-id="37aa2-138">/アドレス</span><span class="sxs-lookup"><span data-stu-id="37aa2-138">From/Address</span></span>|<span data-ttu-id="37aa2-139">From</span><span class="sxs-lookup"><span data-stu-id="37aa2-139">From</span></span>|<span data-ttu-id="37aa2-140">はい</span><span class="sxs-lookup"><span data-stu-id="37aa2-140">Yes</span></span>|  
|<span data-ttu-id="37aa2-141">シーケンス識別子/</span><span class="sxs-lookup"><span data-stu-id="37aa2-141">Sequence/Identifier</span></span>|<span data-ttu-id="37aa2-142">SequenceId</span><span class="sxs-lookup"><span data-stu-id="37aa2-142">SequenceId</span></span>|<span data-ttu-id="37aa2-143">はい</span><span class="sxs-lookup"><span data-stu-id="37aa2-143">Yes</span></span>|  
|<span data-ttu-id="37aa2-144">シーケンス/MessageNumber</span><span class="sxs-lookup"><span data-stu-id="37aa2-144">Sequence/MessageNumber</span></span>|<span data-ttu-id="37aa2-145">SequenceNumber</span><span class="sxs-lookup"><span data-stu-id="37aa2-145">SequenceNumber</span></span>|<span data-ttu-id="37aa2-146">はい</span><span class="sxs-lookup"><span data-stu-id="37aa2-146">Yes</span></span>|  
|<span data-ttu-id="37aa2-147">シーケンス/LastMessage</span><span class="sxs-lookup"><span data-stu-id="37aa2-147">Sequence/LastMessage</span></span>|<span data-ttu-id="37aa2-148">SequenceLastMessage</span><span class="sxs-lookup"><span data-stu-id="37aa2-148">SequenceLastMessage</span></span>|<span data-ttu-id="37aa2-149">はい</span><span class="sxs-lookup"><span data-stu-id="37aa2-149">Yes</span></span>|  
|<span data-ttu-id="37aa2-150">\<soap ヘッダー:\></span><span class="sxs-lookup"><span data-stu-id="37aa2-150">\<soap:Header\></span></span>|<span data-ttu-id="37aa2-151">InboundHeaders</span><span class="sxs-lookup"><span data-stu-id="37aa2-151">InboundHeaders</span></span>|<span data-ttu-id="37aa2-152">いいえ</span><span class="sxs-lookup"><span data-stu-id="37aa2-152">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37aa2-153">参照</span><span class="sxs-lookup"><span data-stu-id="37aa2-153">See Also</span></span>  
 <span data-ttu-id="37aa2-154">[WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="37aa2-154">[Specifying the Message Body for the WCF Adapters](../core/specifying-the-message-body-for-the-wcf-adapters.md) </span></span>  
 <span data-ttu-id="37aa2-155">[WCF 送信アダプタ](../core/wcf-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="37aa2-155">[WCF Send Adapter](../core/wcf-send-adapter.md) </span></span>  
 [<span data-ttu-id="37aa2-156">WCF アダプターについて</span><span class="sxs-lookup"><span data-stu-id="37aa2-156">What Are the WCF Adapters?</span></span>](../core/what-are-the-wcf-adapters.md)