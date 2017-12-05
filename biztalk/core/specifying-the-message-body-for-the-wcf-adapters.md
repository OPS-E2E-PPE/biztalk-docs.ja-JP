---
title: "WCF アダプタのメッセージ本文の指定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF adapters, SOAP messages
- messages, WCF adapters
- WCF adapters, message bodies
- SOAP messages, WCF adapters
ms.assetid: b20364b7-0365-4636-b4d6-bde9c69b8dcb
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 109ad486baa542aff3cd1c4a44804ff2fd79aac5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="specifying-the-message-body-for-the-wcf-adapters"></a><span data-ttu-id="a4bf7-102">WCF アダプタのメッセージ本文の指定</span><span class="sxs-lookup"><span data-stu-id="a4bf7-102">Specifying the Message Body for the WCF Adapters</span></span>
<span data-ttu-id="a4bf7-103">使用することができます、**メッセージ**] タブの [WCF アダプターでは、受信 SOAP メッセージから BizTalk メッセージ本文を抽出する方法を指定して、BizTalk メッセージの本文は、送信 SOAP メッセージに配置されます。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-103">You can use the **Messages** tab in the WCF adapters to specify how the BizTalk message body is extracted from an incoming SOAP message, and how the BizTalk message body is placed in an outgoing SOAP message.</span></span>  
  
## <a name="specifying-how-the-biztalk-message-body-is-extracted-from-an-incoming-soap-message"></a><span data-ttu-id="a4bf7-104">受信 SOAP メッセージからの BizTalk メッセージ本文の抽出方法の指定</span><span class="sxs-lookup"><span data-stu-id="a4bf7-104">Specifying How the BizTalk Message Body Is Extracted from an Incoming SOAP Message</span></span>  
 <span data-ttu-id="a4bf7-105">WCF アダプタを通じて受信する SOAP メッセージから受信 BizTalk メッセージ本文を作成する方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-105">You can control how to create the inbound BizTalk message body from the SOAP messages incoming through the WCF adapters.</span></span> <span data-ttu-id="a4bf7-106">次の図、**メッセージ**Wcf-netnamedpipe のタブがアダプタと送信アダプタを例として受信します。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-106">The following figures show the **Messages** tabs of the WCF-NetNamedPipe receive adapter and send adapter as examples.</span></span>  
  
 <span data-ttu-id="a4bf7-107">![[メッセージ] タブ、WCF 受信アダプター](../core/media/abbaccfc-092c-42c6-9207-fa1af28912ac.gif "abbaccfc-092c-42c6-9207-fa1af28912ac")</span><span class="sxs-lookup"><span data-stu-id="a4bf7-107">![The Messages tab in the WCF receive adapters](../core/media/abbaccfc-092c-42c6-9207-fa1af28912ac.gif "abbaccfc-092c-42c6-9207-fa1af28912ac")</span></span>  
  
 <span data-ttu-id="a4bf7-108">![[メッセージ] タブ、WCF 送信アダプタ](../core/media/58e1d490-5bd9-4571-87b1-4dea6dbfe2de.gif "58e1d490-5bd9-4571-87b1-4dea6dbfe2de")</span><span class="sxs-lookup"><span data-stu-id="a4bf7-108">![The Messages tab in the WCF send adapters](../core/media/58e1d490-5bd9-4571-87b1-4dea6dbfe2de.gif "58e1d490-5bd9-4571-87b1-4dea6dbfe2de")</span></span>  
  
 <span data-ttu-id="a4bf7-109">BizTalk メッセージ本文を作成する方法を指定するで次のオプションのいずれかを選択、**受信 BizTalk メッセージ本文**上記の図のセクション。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-109">To specify how to create the BizTalk message body, select one of the following options in the **Inbound BizTalk message body** section in the preceding figures:</span></span>  
  
-   <span data-ttu-id="a4bf7-110">**-エンベロープ\<Soap:envelope\>**です。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-110">**Envelope -- entire \<soap:Envelope\>**.</span></span> <span data-ttu-id="a4bf7-111">SOAP を使用して**エンベロープ**を BizTalk メッセージのボディ部を作成する受信メッセージの要素。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-111">Uses the SOAP **Envelope** element of an incoming message to create the BizTalk message body part.</span></span> <span data-ttu-id="a4bf7-112">受信メッセージ全体が BizTalk メッセージ本文になります。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-112">The entire incoming message becomes the BizTalk message body.</span></span> <span data-ttu-id="a4bf7-113">このオプションは、すべてのヘッダーを組み込んで BizTalk メッセージ本文を作成する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-113">Use this option to create the BizTalk message body incorporating all the headers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a4bf7-114">SOAP ヘッダーはメッセージ コンテキストに配置されますが、自動的に昇格されません。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-114">The SOAP headers are placed in the message context, but they are not promoted automatically.</span></span> <span data-ttu-id="a4bf7-115">昇格は、カスタム パイプライン コンポーネントで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-115">Promotion can be done in a custom pipeline component.</span></span>  
  
-   <span data-ttu-id="a4bf7-116">**本文--内容\<Soap:body\>要素**です。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-116">**Body -- contents of \<soap:Body\> element**.</span></span> <span data-ttu-id="a4bf7-117">SOAP の内容を使用して**本文**を BizTalk メッセージのボディ部を作成する受信メッセージの要素。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-117">Uses the content of the SOAP **Body** element of an incoming message to create the BizTalk message body part.</span></span> <span data-ttu-id="a4bf7-118">**Body** 要素に複数の子要素がある場合は、最初の要素のみが BizTalk メッセージのボディ部になります。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-118">If the **Body** element has more than one child element, only the first element becomes the BizTalk message body part.</span></span>  
  
-   <span data-ttu-id="a4bf7-119">**パス--本文のパスである内容**です。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-119">**Path -- content located by body path**.</span></span> <span data-ttu-id="a4bf7-120">ボディ パス式を使用して、**本文のパス式**BizTalk メッセージのボディ部を作成するテキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-120">Uses the body path expression in the **Body path expression** text box to create the BizTalk message body part.</span></span> <span data-ttu-id="a4bf7-121">ボディ パス式は、受信メッセージの SOAP **Body** 要素のすぐ下の子要素に対して評価されます。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-121">The body path expression is evaluated against the immediate child element of the SOAP **Body** element of an incoming message.</span></span> <span data-ttu-id="a4bf7-122">受信メッセージにバイナリ データが含まれている場合は、BizTalk メッセージ本文にこのオプションを使用して、タグなしのバイナリ データだけを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-122">When incoming messages have binary data, you can use this option for the BizTalk message body to include only the binary data without any tags.</span></span>  
  
 <span data-ttu-id="a4bf7-123">ときに、**パス--本文のパスで見つかったコンテンツ**オプションを選択して、**ノード エンコード**ボディ パス式で指定したノードの予想されるエンコードの種類を指定するプロパティを構成することができます**本文のパス式**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-123">When the **Path -- content located by body path** option is selected, the **Node encoding** property can be configured to specify the expected encoding type for the node specified by the body path expression in the **Body path expression** text box.</span></span> <span data-ttu-id="a4bf7-124">本文のパス式が複数の要素に一致する場合は、最初に一致した要素のみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-124">If the body path expression matches more than one element, only the first matched element is used.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4bf7-125">**本文のパス式**プロパティ、XML の順方向専用の処理に適した式がサポートされている XPath のみです。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-125">For the **body path expression** property, only the XPath expressions suitable for forward-only processing of XML are supported.</span></span> <span data-ttu-id="a4bf7-126">このプロパティの使用可能な XPath 式の詳細についてを参照してください"ベストの両方長所:: 結合 XPath で、XmlReader" [http://go.microsoft.com/fwlink/?LinkID=75701](http://go.microsoft.com/fwlink/?LinkID=75701)です。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-126">For more information about the XPath expressions available for this property, see "The Best of Both Worlds: Combining XPath with the XmlReader" at [http://go.microsoft.com/fwlink/?LinkID=75701](http://go.microsoft.com/fwlink/?LinkID=75701).</span></span>  
  
 <span data-ttu-id="a4bf7-127">場合、**パス--本文のパスで見つかったコンテンツ**オプションを選択して**ノード エンコード**プロパティに設定されている**文字列**、WCF アダプターは、期待 utf-8 が一致するノードにあります。文字データをエンコードします。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-127">If the **Path -- content located by body path** option is selected and the **Node encoding** property is set to **String**, the WCF adapters expect that the matched node has UTF-8 encoded character data.</span></span> <span data-ttu-id="a4bf7-128">受信メッセージが含まれる場合など、XML の特殊文字の文字データをエスケープ\<と\>、WCF アダプターが BizTalk メッセージのボディ部を作成するときに、エスケープ文字データを復元します。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-128">If the incoming messages include escaped character data for the XML special characters such as \< and \>, the WCF adapters restore the escaped character data when creating the BizTalk message body part.</span></span> <span data-ttu-id="a4bf7-129">たとえば、一致するノードが文字データをようにエスケープ **&lt;FirstName&gt;CONTOSO&lt;/FirstName&gt;**  、WCF アダプタ作成 **\<FirstName\>CONTOSO\</FirstName\>** 受信 biztalk メッセージ本文。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-129">For example, if the matched node has escaped character data such as **&lt;FirstName&gt;CONTOSO&lt;/FirstName&gt;** the WCF adapters create **\<FirstName\>CONTOSO\</FirstName\>** in the inbound BizTalk message body.</span></span>  
  
 <span data-ttu-id="a4bf7-130">場合、**パス--本文のパスで見つかったコンテンツ**オプションを選択して、**ノード エンコード**プロパティに設定されている**16 進数**または**Base64**では、一致するノードが、有効なことができますが**BinHex**または**Base64**シーケンス。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-130">If the **Path -- content located by body path** option is selected and the **Node encoding** property is set to **Hex** or **Base64**, the matched node can have a valid **BinHex** or **Base64** sequence.</span></span> <span data-ttu-id="a4bf7-131">一致するノードに無効なシーケンスがある場合は、WCF クライアントが受け取る**FaultException**、エラー メッセージは、BizTalk Server コンピューターのイベント ログにログに記録され、メッセージは中断されません。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-131">If the matched node has an invalid sequence, the WCF client receives **FaultException**, an error message is logged in the event log on your BizTalk Server computer, and no message is suspended.</span></span>  
  
 <span data-ttu-id="a4bf7-132">場合、**パス--本文のパスで見つかったコンテンツ**オプションを選択して**ノード エンコード**プロパティに設定されている**XML**、WCF アダプタが使用して BizTalk メッセージ本文を作成、ボディ パス式で選択されたノードの外部の XML、**本文のパス式**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-132">If the **Path -- content located by body path** option is selected and the **Node encoding** property is set to **XML**, the WCF adapters create the BizTalk message body with the outer XML of the node selected by the body path expression in the **Body path expression** text box.</span></span>  
  
 <span data-ttu-id="a4bf7-133">指定された一致するノードとしてエンコードされたデータがない場合、**ノード エンコード**プロパティ、空の受信 BizTalk メッセージ本文が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-133">If the matched node does not have data encoded as specified in the **Node encoding** property, an empty inbound BizTalk message body is created.</span></span>  
  
 <span data-ttu-id="a4bf7-134">たとえば、WCF 送信アダプタが WCF クライアントから次の SOAP メッセージを受信したとします。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-134">For example, suppose the WCF send adapters receive the following SOAP message from WCF clients:</span></span>  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess/IOrderProcess/OrderRefresh</a:Action>   
    <a:MessageID>urn:uuid:59e74507-66d0-4d50-be70-c3ec248b6f78</a:MessageID>   
    <a:ReplyTo>  
       <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>   
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessServiceBizTalk</a:To>   
  </s:Header>  
  <s:Body>  
    <Order xmlns="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  
     <OrderDetail>  
       <CustomerID>CONTOSO</CustomerID>   
       <OrderID>00000000</OrderID>   
     </OrderDetail>  
    </Order>  
  </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="a4bf7-135">構成する場合、**受信 BizTalk メッセージ本文**セクションの次の表では、上記の受信 SOAP メッセージに示すように受信 BizTalk メッセージのボディ部になります。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-135">If you configure the **Inbound BizTalk message body** section as shown in the following table, the previous incoming SOAP message becomes the inbound BizTalk message body part.</span></span>  
  
|<span data-ttu-id="a4bf7-136">受信 BizTalk メッセージ本文</span><span class="sxs-lookup"><span data-stu-id="a4bf7-136">Inbound BizTalk message body</span></span>|<span data-ttu-id="a4bf7-137">本文のパス式</span><span class="sxs-lookup"><span data-stu-id="a4bf7-137">Body path expression</span></span>|<span data-ttu-id="a4bf7-138">[ノード エンコード]</span><span class="sxs-lookup"><span data-stu-id="a4bf7-138">Node encoding</span></span>|  
|----------------------------------|--------------------------|-------------------|  
|<span data-ttu-id="a4bf7-139">**-エンベロープ\<Soap:envelope\>**</span><span class="sxs-lookup"><span data-stu-id="a4bf7-139">**Envelope -- entire \<soap:Envelope\>**</span></span>|<span data-ttu-id="a4bf7-140">なし</span><span class="sxs-lookup"><span data-stu-id="a4bf7-140">N/A</span></span>|<span data-ttu-id="a4bf7-141">なし</span><span class="sxs-lookup"><span data-stu-id="a4bf7-141">N/A</span></span>|  
  
 <span data-ttu-id="a4bf7-142">構成する場合、 **BizTalk メッセージ本文**セクションで、WCF アダプタがのみが含まれる受信 BizTalk メッセージのボディ部を作成して、次の表に示すように、**順序**前の要素受信 SOAP メッセージ。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-142">If you configure the **BizTalk message body** section as shown in the following table, the WCF adapters create the inbound BizTalk message body part to contain only the **Order** element in the previous incoming SOAP message.</span></span>  
  
|<span data-ttu-id="a4bf7-143">受信 BizTalk メッセージ本文</span><span class="sxs-lookup"><span data-stu-id="a4bf7-143">Inbound BizTalk message body</span></span>|<span data-ttu-id="a4bf7-144">本文のパス式</span><span class="sxs-lookup"><span data-stu-id="a4bf7-144">Body path expression</span></span>|<span data-ttu-id="a4bf7-145">[ノード エンコード]</span><span class="sxs-lookup"><span data-stu-id="a4bf7-145">Node encoding</span></span>|  
|----------------------------------|--------------------------|-------------------|  
|<span data-ttu-id="a4bf7-146">**本文--内容\<Soap:body\>要素**</span><span class="sxs-lookup"><span data-stu-id="a4bf7-146">**Body -- contents of \<soap:Body\> element**</span></span>|<span data-ttu-id="a4bf7-147">なし</span><span class="sxs-lookup"><span data-stu-id="a4bf7-147">N/A</span></span>|<span data-ttu-id="a4bf7-148">なし</span><span class="sxs-lookup"><span data-stu-id="a4bf7-148">N/A</span></span>|  
  
 <span data-ttu-id="a4bf7-149">構成する場合、 **BizTalk メッセージ本文**セクション ボディ パス式に一致する受信ノードが utf-8 でエンコードされた文字データを持つ次の表に示すように、WCF アダプタが期待されます。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-149">If you configure the **BizTalk message body** section as shown in the following table, the WCF adapters expect that the incoming node that the body path expression matches will have UTF-8 encoded character data.</span></span>  
  
|<span data-ttu-id="a4bf7-150">受信 BizTalk メッセージ本文</span><span class="sxs-lookup"><span data-stu-id="a4bf7-150">Inbound BizTalk message body</span></span>|<span data-ttu-id="a4bf7-151">本文のパス式</span><span class="sxs-lookup"><span data-stu-id="a4bf7-151">Body path expression</span></span>|<span data-ttu-id="a4bf7-152">[ノード エンコード]</span><span class="sxs-lookup"><span data-stu-id="a4bf7-152">Node encoding</span></span>|  
|----------------------------------|--------------------------|-------------------|  
|<span data-ttu-id="a4bf7-153">**本文のパスで見つかったコンテンツ パス--**</span><span class="sxs-lookup"><span data-stu-id="a4bf7-153">**Path -- content located by body path**</span></span>|<span data-ttu-id="a4bf7-154">/* [ローカル名 () = 'Order']/\*[ローカル名 () = 'OrderDetail']/\*[ローカル名 () = 'CustomerID']</span><span class="sxs-lookup"><span data-stu-id="a4bf7-154">/*[local-name()='Order']/\*[local-name()='OrderDetail']/\*[local-name()='CustomerID']</span></span>|<span data-ttu-id="a4bf7-155">**文字列**</span><span class="sxs-lookup"><span data-stu-id="a4bf7-155">**String**</span></span>|  
  
 <span data-ttu-id="a4bf7-156">WCF アダプターは、上記の受信 SOAP メッセージの文字データを使用して**CONTOSO**の**CustomerID**受信 BizTalk メッセージのボディ部を作成する要素。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-156">For the previous incoming SOAP message, the WCF adapters use the character data, **CONTOSO**, of the **CustomerID** element to create the inbound BizTalk message body part.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4bf7-157">XPath の省略構文を使用することはできません**/Order/OrderDetail/CustomerID**、上記の受信 SOAP メッセージにします。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-157">You cannot use the abbreviated syntax of XPath, **/Order/OrderDetail/CustomerID**, for the previous incoming SOAP message.</span></span> <span data-ttu-id="a4bf7-158">これは、XPath の省略構文には、名前空間で宣言されていないノードが返されるため、 **CustomerID**で上記の SOAP メッセージ内の要素が宣言されている、 **http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess**既定の名前空間では名前空間。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-158">This is because the abbreviated syntax of XPath returns the node not declared in a namespace, and the **CustomerID** element in the previous SOAP message is declared in the **http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess** namespace by default namespaces.</span></span>  
  
 <span data-ttu-id="a4bf7-159">構成する場合、 **BizTalk メッセージ本文**セクションの次の表に示すように、 **CustomID**上記の受信 SOAP メッセージ内の要素が有効な必要**BinHex**または**Base64**シーケンス。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-159">If you configure the **BizTalk message body** section as shown in the following table, the **CustomID** element in the previous incoming SOAP message should have a valid **BinHex** or **Base64** sequence.</span></span>  
  
|<span data-ttu-id="a4bf7-160">受信 BizTalk メッセージ本文</span><span class="sxs-lookup"><span data-stu-id="a4bf7-160">Inbound BizTalk message body</span></span>|<span data-ttu-id="a4bf7-161">本文のパス式</span><span class="sxs-lookup"><span data-stu-id="a4bf7-161">Body path expression</span></span>|<span data-ttu-id="a4bf7-162">[ノード エンコード]</span><span class="sxs-lookup"><span data-stu-id="a4bf7-162">Node encoding</span></span>|  
|----------------------------------|--------------------------|-------------------|  
|<span data-ttu-id="a4bf7-163">**本文のパスで見つかったコンテンツ パス--**</span><span class="sxs-lookup"><span data-stu-id="a4bf7-163">**Path -- content located by body path**</span></span>|<span data-ttu-id="a4bf7-164">/* [ローカル名 () = 'Order']/\*[ローカル名 () = 'OrderDetail']/\*[ローカル名 () = 'CustomerID']</span><span class="sxs-lookup"><span data-stu-id="a4bf7-164">/*[local-name()='Order']/\*[local-name()='OrderDetail']/\*[local-name()='CustomerID']</span></span>|<span data-ttu-id="a4bf7-165">**16 進**または**Base64**</span><span class="sxs-lookup"><span data-stu-id="a4bf7-165">**Hex** or **Base64**</span></span>|  
  
 <span data-ttu-id="a4bf7-166">構成する場合、 **BizTalk メッセージ本文**セクションで、WCF アダプタが、表の後に、コードに示すように、上記の受信 SOAP メッセージの受信 BizTalk メッセージ本文を作成、次の表に示すように、します。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-166">If you configure the **BizTalk message body** section as shown in the following table, the WCF adapters create the inbound BizTalk message body for the previous incoming SOAP message as shown in the code after the table.</span></span>  
  
|<span data-ttu-id="a4bf7-167">受信 BizTalk メッセージ本文</span><span class="sxs-lookup"><span data-stu-id="a4bf7-167">Inbound BizTalk message body</span></span>|<span data-ttu-id="a4bf7-168">本文のパス式</span><span class="sxs-lookup"><span data-stu-id="a4bf7-168">Body path expression</span></span>|<span data-ttu-id="a4bf7-169">[ノード エンコード]</span><span class="sxs-lookup"><span data-stu-id="a4bf7-169">Node encoding</span></span>|  
|----------------------------------|--------------------------|-------------------|  
|<span data-ttu-id="a4bf7-170">**本文のパスで見つかったコンテンツ パス--**</span><span class="sxs-lookup"><span data-stu-id="a4bf7-170">**Path -- content located by body path**</span></span>|<span data-ttu-id="a4bf7-171">/* [ローカル名 () = 'Order']/\*[ローカル名 () = 'OrderDetail']/\*[ローカル名 () = 'CustomerID']</span><span class="sxs-lookup"><span data-stu-id="a4bf7-171">/*[local-name()='Order']/\*[local-name()='OrderDetail']/\*[local-name()='CustomerID']</span></span>|<span data-ttu-id="a4bf7-172">**XML**</span><span class="sxs-lookup"><span data-stu-id="a4bf7-172">**XML**</span></span>|  
  
```  
<CustomerID xmlns="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">CONTOSO</CustomerID>   
```  
  
## <a name="specifying-the-source-of-the-outbound-wcf-message-body"></a><span data-ttu-id="a4bf7-173">送信 WCF メッセージ本文の送信元の指定</span><span class="sxs-lookup"><span data-stu-id="a4bf7-173">Specifying the Source of the Outbound WCF Message Body</span></span>  
 <span data-ttu-id="a4bf7-174">WCF アダプタを通じて送信される BizTalk メッセージ本文から送信 WCF メッセージ本文を作成する方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-174">You can control how to create the outbound WCF message body from a BizTalk message body to send through the WCF adapters.</span></span> <span data-ttu-id="a4bf7-175">BizTalk メッセージ本文を送信 WCF メッセージ本文に配置する方法を指定するで次のオプションのいずれかを使用できます、**送信 WCF メッセージ本文**セクションで、**メッセージ** タブで示すように、前のセクションでの数値。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-175">To specify how the BizTalk message body is placed in the outbound WCF message body, you can use one of the following options in the **Outbound WCF message body** section on the **Messages** tab as shown in the figures in the previous section:</span></span>  
  
-   <span data-ttu-id="a4bf7-176">**ボディ--BizTalk 応答メッセージ本文**です。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-176">**Body -- BizTalk response message body**.</span></span> <span data-ttu-id="a4bf7-177">BizTalk メッセージのボディ部を使用して、SOAP のコンテンツを作成する**本文**送信メッセージの要素。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-177">Uses the BizTalk message body part to create the content of the SOAP **Body** element for an outgoing message.</span></span> <span data-ttu-id="a4bf7-178">送信 BizTalk メッセージ本文が、送信 SOAP メッセージの本文になります。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-178">The outgoing BizTalk message body becomes the body of the outbound SOAP message.</span></span>  
  
-   <span data-ttu-id="a4bf7-179">**テンプレート--テンプレートで指定されたコンテンツ**です。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-179">**Template -- content specified by template**.</span></span> <span data-ttu-id="a4bf7-180">提供されているテンプレートを使用して、 **XML** SOAP のコンテンツを作成するテキスト ボックス**本文**送信メッセージの要素。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-180">Uses the template supplied in the **XML** text box to create the content of the SOAP **Body** element for an outgoing message.</span></span> <span data-ttu-id="a4bf7-181">WCF アダプターで**ボディ--BizTalk 応答メッセージ本文**(既定値) オプション文字データやビットマップ イメージなどの XML 以外のメッセージを送信することはできます。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-181">The WCF adapters with **Body -- BizTalk response message body** (the default value) option do not allow sending non-XML message such as character data and bitmap images.</span></span> <span data-ttu-id="a4bf7-182">使用することができます、**テンプレート--テンプレートで指定されたコンテンツ**でエンコードされた XML 以外のメッセージを送信する WCF アダプターのオプション**base64**、 **16 進**、または**文字列**.</span><span class="sxs-lookup"><span data-stu-id="a4bf7-182">You can use the **Template -- content specified by template** option for the WCF adapters to send non-XML messages encoded in **base64**, **hex**, or **string**.</span></span>  
  
 <span data-ttu-id="a4bf7-183">ときに、**テンプレート--テンプレートで指定されたコンテンツ**オプションが選択されている場合、内の任意のテンプレート XML 要素を指定する必要があります、**送信 WCF メッセージ本文 - XML**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-183">When the **Template -- content specified by template** option is selected, you must provide an arbitrary template XML element in the **Outbound WCF message body - XML** text box.</span></span> <span data-ttu-id="a4bf7-184">テンプレート XML 要素は、次を含める必要があります**bts メッセージ本文**要素が 1 回だけテンプレート XML 要素が空のままにしない限り、します。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-184">The template XML element must contain the following **bts-msg-body** element once and only once unless the template XML element is left empty:</span></span>  
  
```  
<bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2010" encoding="[base64|hex|string|xml]"/>  
```  
  
 <span data-ttu-id="a4bf7-185">WCF アダプターによると、BizTalk メッセージ本文のエンコード、**エンコード**XML テンプレートの属性し、し、置換、 **bts メッセージ本文**を作成するときに、エンコードされた BizTalk メッセージ本文の要素送信 WCF メッセージ。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-185">The WCF adapters encode the BizTalk message body according to the **encoding** attribute in the XML template, and then replace the **bts-msg-body** element with the encoded BizTalk message body when creating outbound WCF messages.</span></span> <span data-ttu-id="a4bf7-186">場合、**送信 WCF メッセージ本文 - XML**テキスト ボックスが空のまま、WCF アダプタで BizTalk メッセージ本文をエンコードする**Base64**、し、配置、 **Base64**内のシーケンス、送信 SOAP メッセージの本文。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-186">If the **Outbound WCF message body - XML** text box is left empty, the WCF adapters encode the BizTalk message body in **Base64**, and then place the **Base64** sequence in the outbound SOAP message body.</span></span>  
  
 <span data-ttu-id="a4bf7-187">場合、**エンコード**XML テンプレート内の属性に設定されている**文字列**、WCF アダプターは、XML の特殊文字のなどをutf-8でエンコードされた文字データとしてのBizTalkメッセージのボディ部のエンコード\<と\>エスケープされます。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-187">If the **encoding** attribute in the XML template is set to **string**, the WCF adapters encode the BizTalk message body part as UTF-8 encoded character data, in which the XML special characters such as \< and \> are escaped.</span></span>  
  
 <span data-ttu-id="a4bf7-188">場合、**エンコード**XML テンプレート内の属性に設定されている**base64**または**16 進**、WCF アダプターとして BizTalk メッセージのボディ部のエンコード、 **BinHex**または**Base64**シーケンス。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-188">If the **encoding** attribute in the XML template is set to **base64** or **hex**, the WCF adapters encode the BizTalk message body part as a **BinHex** or **Base64** sequence.</span></span>  
  
 <span data-ttu-id="a4bf7-189">場合、**エンコード**XML テンプレート内の属性に設定されている**xml**、WCF アダプターは、置換、 **bts メッセージ本文**要素を送信 BizTalk メッセージ本文を作成する、送信 WCF メッセージ。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-189">If the **encoding** attribute in the XML template is set to **xml**, the WCF adapters replace the **bts-msg-body** element with the outbound BizTalk message body to create the outgoing WCF message.</span></span>  
  
 <span data-ttu-id="a4bf7-190">たとえば、WCF アダプタで、次の BizTalk メッセージのボディ部を WCF クライアントに送信する必要が生じたとします。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-190">For example, suppose the WCF adapters need to send the following BizTalk message body part to WCF clients:</span></span>  
  
```  
<ns0:Order xmlns:ns0="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  
  <ns0:OrderDetail>  
    <ns0:CustomerID>CONTOSO</ns0:CustomerID>  
    <ns0:OrderID>01A2c</ns0:OrderID>  
  </ns0:OrderDetail>  
</ns0:Order>  
```  
  
 <span data-ttu-id="a4bf7-191">構成する場合、**送信 WCF メッセージ本文**セクションで、表の後に、コードに示すように、WCF アダプタでは送信 WCF メッセージを作成、次の表に示すように、します。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-191">If you configure the **Outbound WCF message body** section as shown in the following table, the WCF adapters create the outbound WCF messages as shown in the code after the table.</span></span>  
  
|<span data-ttu-id="a4bf7-192">送信 WCF メッセージ本文</span><span class="sxs-lookup"><span data-stu-id="a4bf7-192">Outbound WCF message body</span></span>|<span data-ttu-id="a4bf7-193">XML</span><span class="sxs-lookup"><span data-stu-id="a4bf7-193">XML</span></span>|  
|-------------------------------|---------|  
|<span data-ttu-id="a4bf7-194">**ボディ--BizTalk 応答メッセージ本文**</span><span class="sxs-lookup"><span data-stu-id="a4bf7-194">**Body -- BizTalk response message body**</span></span>|<span data-ttu-id="a4bf7-195">なし</span><span class="sxs-lookup"><span data-stu-id="a4bf7-195">N/A</span></span>|  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess/IOrderProcess/Request</a:Action>  
    <a:MessageID>urn:uuid:6a706a54-c4f5-4767-909d-a992c7c26dba</a:MessageID>  
    <a:ReplyTo>  
<a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessService</a:To>  
  </s:Header>  
  <s:Body>  
    <ns0:Order xmlns:ns0="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  
  <ns0:OrderDetail>  
    <ns0:CustomerID>CONTOSO</ns0:CustomerID>  
    <ns0:OrderID>01A2c</ns0:OrderID>  
  </ns0:OrderDetail>  
</ns0:Order>  
  </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="a4bf7-196">構成する場合、**送信 WCF メッセージ本文**セクションで、表の後に、コードに示すように、WCF アダプタでは送信 WCF メッセージを作成、次の表に示すように、します。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-196">If you configure the **Outbound WCF message body** section as shown in the following table, the WCF adapters create the outbound WCF messages as shown in the code after the table.</span></span>  
  
|<span data-ttu-id="a4bf7-197">送信 WCF メッセージ本文</span><span class="sxs-lookup"><span data-stu-id="a4bf7-197">Outbound WCF message body</span></span>|<span data-ttu-id="a4bf7-198">XML</span><span class="sxs-lookup"><span data-stu-id="a4bf7-198">XML</span></span>|  
|-------------------------------|---------|  
|<span data-ttu-id="a4bf7-199">**ボディ--BizTalk 応答メッセージ本文**</span><span class="sxs-lookup"><span data-stu-id="a4bf7-199">**Body -- BizTalk response message body**</span></span>|<span data-ttu-id="a4bf7-200">\<書籍\></span><span class="sxs-lookup"><span data-stu-id="a4bf7-200">\<Book\></span></span><br /><br /> <span data-ttu-id="a4bf7-201">\<**bts メッセージ本文**xmlns ="http://www.microsoft.com/schemas/bts2010"encoding ="**文字列**"/\></span><span class="sxs-lookup"><span data-stu-id="a4bf7-201">\<**bts-msg-body** xmlns="http://www.microsoft.com/schemas/bts2010" encoding="**string**"/\></span></span><br /><br /> <span data-ttu-id="a4bf7-202">\</書籍\></span><span class="sxs-lookup"><span data-stu-id="a4bf7-202">\</Book\></span></span>|  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess/IOrderProcess/Request</a:Action>  
    <a:MessageID>urn:uuid:05dde292-eedd-467e-b0d2-f1b8f0757410</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessService</a:To>  
  </s:Header>  
  <s:Body>  
    <Book><ns0:Order xmlns:ns0="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  <ns0:OrderDetail>    <ns0:CustomerID>CONTOSO</ns0:CustomerID>    <ns0:OrderID> 01A2c</ns0:OrderID>  </ns0:OrderDetail></ns0:Order>  
    </Book>  
  </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="a4bf7-203">構成する場合、**送信 WCF メッセージ本文**セクションで、表の後に、コードに示すように、WCF アダプタでは送信 WCF メッセージを作成、次の表に示すように、します。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-203">If you configure the **Outbound WCF message body** section as shown in the following table, the WCF adapters create the outbound WCF messages as shown in the code after the table.</span></span>  
  
|<span data-ttu-id="a4bf7-204">送信 WCF メッセージ本文</span><span class="sxs-lookup"><span data-stu-id="a4bf7-204">Outbound WCF message body</span></span>|<span data-ttu-id="a4bf7-205">XML</span><span class="sxs-lookup"><span data-stu-id="a4bf7-205">XML</span></span>|  
|-------------------------------|---------|  
|<span data-ttu-id="a4bf7-206">**ボディ--BizTalk 応答メッセージ本文**</span><span class="sxs-lookup"><span data-stu-id="a4bf7-206">**Body -- BizTalk response message body**</span></span>|<span data-ttu-id="a4bf7-207">\<書籍\></span><span class="sxs-lookup"><span data-stu-id="a4bf7-207">\<Book\></span></span><br /><br /> <span data-ttu-id="a4bf7-208">\<**bts メッセージ本文**xmlns ="http://www.microsoft.com/schemas/bts2010"encoding ="**base64**"/\></span><span class="sxs-lookup"><span data-stu-id="a4bf7-208">\<**bts-msg-body** xmlns="http://www.microsoft.com/schemas/bts2010" encoding="**base64**"/\></span></span><br /><br /> <span data-ttu-id="a4bf7-209">\</書籍\></span><span class="sxs-lookup"><span data-stu-id="a4bf7-209">\</Book\></span></span>|  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://ww  
w.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe  
/OrderProcess/IOrderProcess/Request</a:Action>  
    <a:MessageID>urn:uuid:cb3cac6d-a542-4a90-bad8-cdbfa8251112</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessSer  
vice</a:To>  
  </s:Header>  
  <s:Body>  
    <Book>77u/PG5zMDpPcmRlciB4bWxuczpuczA9Imh0dHA6Ly9NaWNyb3NvZnQuU2FtcGxlcy5CaX  
pUYWxrLk5ldE5hbWVkUGlwZS9PcmRlclByb2Nlc3MiPg0KICA8bnMwOk9yZGVyRGV0YWlsPg0KICAgID  
xuczA6Q3VzdG9tZXJJRD5DT05UT1NPPC9uczA6Q3VzdG9tZXJJRD4NCiAgICA8bnMwOk9yZGVySUQ+MD  
FBMmM8L25zMDpPcmRlcklEPg0KICA8L25zMDpPcmRlckRldGFpbD4NCjwvbnMwOk9yZGVyPg==</Book  
>  
  </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="a4bf7-210">構成する場合、**送信 WCF メッセージ本文**セクションで、表の後に、コードに示すように、WCF アダプタでは送信 WCF メッセージを作成、次の表に示すように、します。</span><span class="sxs-lookup"><span data-stu-id="a4bf7-210">If you configure the **Outbound WCF message body** section as shown in the following table, the WCF adapters create the outbound WCF messages as shown in the code after the table.</span></span>  
  
|<span data-ttu-id="a4bf7-211">送信 WCF メッセージ本文</span><span class="sxs-lookup"><span data-stu-id="a4bf7-211">Outbound WCF message body</span></span>|<span data-ttu-id="a4bf7-212">XML</span><span class="sxs-lookup"><span data-stu-id="a4bf7-212">XML</span></span>|  
|-------------------------------|---------|  
|<span data-ttu-id="a4bf7-213">**ボディ--BizTalk 応答メッセージ本文**</span><span class="sxs-lookup"><span data-stu-id="a4bf7-213">**Body -- BizTalk response message body**</span></span>|<span data-ttu-id="a4bf7-214">\<書籍\></span><span class="sxs-lookup"><span data-stu-id="a4bf7-214">\<Book\></span></span><br /><br /> <span data-ttu-id="a4bf7-215">\<**bts メッセージ本文**xmlns ="http://www.microsoft.com/schemas/bts2010"encoding ="**xml**"/\></span><span class="sxs-lookup"><span data-stu-id="a4bf7-215">\<**bts-msg-body** xmlns="http://www.microsoft.com/schemas/bts2010" encoding="**xml**"/\></span></span><br /><br /> <span data-ttu-id="a4bf7-216">\</書籍\></span><span class="sxs-lookup"><span data-stu-id="a4bf7-216">\</Book\></span></span>|  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess/IOrderProcess/Request</a:A  
ction>  
    <a:MessageID>{513C123C-0600-4A1C-BEE2-EF83E0EFEB15}</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessServiceBizTalk</a:To>  
  </s:Header>  
  <s:Body>  
    <Book>  
      <ns0:Order xmlns:ns0="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  
  <ns0:OrderDetail>  
    <ns0:CustomerID>CustomerID_0</ns0:CustomerID>  
    <ns0:OrderID>OrderID_0</ns0:OrderID>  
  </ns0:OrderDetail>  
</ns0:Order>  
    </Book>  
  </s:Body>  
</s:Envelope>  
```