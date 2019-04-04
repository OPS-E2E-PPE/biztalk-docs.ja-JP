---
title: SAP アダプターを使用した WCF チャネル モデルの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, overview
- WCF channel model, creating messages for the SAP adapter
ms.assetid: 6192d637-efac-4580-8880-b5bae9d16f31
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81eba8c28b3bf11eea38624e0a017d8bca9eb9a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013187"
---
# <a name="overview-of-the-wcf-channel-model-with-the-sap-adapter"></a><span data-ttu-id="a8798-102">SAP アダプターを使用した WCF チャネル モデルの概要</span><span class="sxs-lookup"><span data-stu-id="a8798-102">Overview of the WCF channel model with the SAP adapter</span></span>
<span data-ttu-id="a8798-103">SAP システムでは、Rfc、Trfc、Bapi を呼び出すまたは IDOC を SAP システムに送信するには、コードが WCF クライアントとして機能し、送信操作をアダプターに送信します。</span><span class="sxs-lookup"><span data-stu-id="a8798-103">To invoke RFCs, tRFCs, or BAPIs on an SAP system, or to send IDOCS to an SAP system, your code acts as a WCF client and sends outbound operations to the adapter.</span></span> <span data-ttu-id="a8798-104">WCF チャネル モデルでは、コードは、チャネル経由で要求メッセージを送信することによって、アダプターでの操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a8798-104">In the WCF channel model, your code invokes operations on the adapter by sending a request message over a channel.</span></span>  
  
 <span data-ttu-id="a8798-105">TRFC または SAP システムへの RFC サーバーとして機能しには、コードは、WCF サービスとして動作します。</span><span class="sxs-lookup"><span data-stu-id="a8798-105">To act as a tRFC or RFC server to an SAP system, your code behaves as a WCF service.</span></span> <span data-ttu-id="a8798-106">アダプターが、コードで受信操作を呼び出す、-など、RFC または ReceiveIdoc 操作 (SAP システムからの文字列形式で IDOC を受信する)。</span><span class="sxs-lookup"><span data-stu-id="a8798-106">That is, the adapter invokes an inbound operation on your code—for example, an RFC or the ReceiveIdoc operation (to receive an IDOC in string format from an SAP system).</span></span> <span data-ttu-id="a8798-107">このシナリオでは、コードは、アダプターからチャネルを操作の要求メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a8798-107">In this scenario, your code receives a request message for the operation over a channel from the adapter.</span></span>  
  
 <span data-ttu-id="a8798-108">このセクションのトピックの使用の概要を提供する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF チャネル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a8798-108">The topics in this section provide an overview of using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with the WCF channel model.</span></span>  
  
## <a name="wcf-channel-model-overview"></a><span data-ttu-id="a8798-109">WCF チャネル モデルの概要</span><span class="sxs-lookup"><span data-stu-id="a8798-109">WCF Channel Model Overview</span></span>  
 <span data-ttu-id="a8798-110">クライアントとサービスは、SOAP メッセージを交換して通信します。</span><span class="sxs-lookup"><span data-stu-id="a8798-110">Clients and services communicate by exchanging SOAP messages.</span></span> <span data-ttu-id="a8798-111">WCF チャネル モデルとは、このメッセージ交換の低レベルの抽象化です。</span><span class="sxs-lookup"><span data-stu-id="a8798-111">The WCF channel model is a low-level abstraction of this message exchange.</span></span> <span data-ttu-id="a8798-112">インターフェイスおよびチャネル スタックと呼ばれる複数層のプロトコル スタックを使用してメッセージを送受信するための型を提供します。</span><span class="sxs-lookup"><span data-stu-id="a8798-112">It provides interfaces and types that enable you to send and receive messages by using a layered protocol stack called a channel stack.</span></span> <span data-ttu-id="a8798-113">チャネルのスタックの各層がで構成され、WCF バインドから各チャネルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a8798-113">Each layer of the stack is composed of a channel, and each channel is created from a WCF binding.</span></span> <span data-ttu-id="a8798-114">最下位の層では、トランスポート チャネルです。</span><span class="sxs-lookup"><span data-stu-id="a8798-114">At the lowest layer is the transport channel.</span></span> <span data-ttu-id="a8798-115">トランスポート チャネルがサービスとクライアント間の基盤トランスポート メカニズムを実装し、として上位レイヤー (および最終的には、コンシューマー側アプリケーション) には、各メッセージを表示、 **System.ServiceModel.Message**します。</span><span class="sxs-lookup"><span data-stu-id="a8798-115">The transport channel implements the underlying transport mechanism between a service and a client and presents each message to the higher layers (and ultimately the consuming application) as a **System.ServiceModel.Message**.</span></span> <span data-ttu-id="a8798-116">WCF**メッセージ**クラスは、SOAP メッセージの抽象化します。</span><span class="sxs-lookup"><span data-stu-id="a8798-116">The WCF **Message** class is an abstraction of a SOAP message.</span></span> <span data-ttu-id="a8798-117">WCF には、基本的な SOAP メッセージ交換パターンなどの要求/応答または一方向のモデル化するチャネル形状と呼ばれるいくつかのチャネル インターフェイスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="a8798-117">WCF provides several channel interfaces, called channel shapes, that model the basic SOAP message exchange patterns, such as request-reply or one-way.</span></span> <span data-ttu-id="a8798-118">WCF トランスポート バインディングは、1 つの実装を提供します。 または、レイヤーの高い複数のチャネル形状はメッセージの送受信に使用できます。</span><span class="sxs-lookup"><span data-stu-id="a8798-118">A WCF transport binding provides an implementation of one or more channel shapes that higher layers can use to send and receive messages.</span></span> <span data-ttu-id="a8798-119">WCF チャネル モデルの詳細については、[チャネル モデルの概要](https://msdn.microsoft.com/library/ms729840.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8798-119">For more information about the WCF channel model, see [Channel Model Overview](https://msdn.microsoft.com/library/ms729840.aspx).</span></span>
  
 <span data-ttu-id="a8798-120">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]は WCF サービスとしての SAP システムを公開する WCF カスタム トランスポート バインドします。</span><span class="sxs-lookup"><span data-stu-id="a8798-120">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is a WCF custom transport binding that exposes an SAP system as a WCF service.</span></span>  
  
## <a name="supported-channel-shapes-for-the-sap-adapter"></a><span data-ttu-id="a8798-121">SAP アダプターのチャネル形状をサポート</span><span class="sxs-lookup"><span data-stu-id="a8798-121">Supported Channel Shapes for the SAP Adapter</span></span>  
 <span data-ttu-id="a8798-122">アダプターは、次の WCF チャネル形状を実装します。</span><span class="sxs-lookup"><span data-stu-id="a8798-122">The adapter implements the following WCF channel shapes:</span></span>  
  
- <span data-ttu-id="a8798-123">**IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**)。</span><span class="sxs-lookup"><span data-stu-id="a8798-123">**IRequestChannel** (**System.ServiceModel.Channels.IRequestChannel**).</span></span> <span data-ttu-id="a8798-124">**IRequestChannel**インターフェイスは、クライアント側の要求/応答メッセージの交換を実装します。</span><span class="sxs-lookup"><span data-stu-id="a8798-124">The **IRequestChannel** interface implements the client side of a request-reply message exchange.</span></span> <span data-ttu-id="a8798-125">使用することができます、 **IRequestChannel**にデータを返す、SAP システムの RFC を呼び出す例については、応答を使用する操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a8798-125">You can use an **IRequestChannel** to perform operations for which you want to consume a response, for example to invoke an RFC on the SAP system that returns data.</span></span>  
  
- <span data-ttu-id="a8798-126">**IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**)。</span><span class="sxs-lookup"><span data-stu-id="a8798-126">**IOutputChannel** (**System.ServiceModel.Channels.IOutputChannel**).</span></span> <span data-ttu-id="a8798-127">この図形は、クライアント側の一方向メッセージ交換を実装します。</span><span class="sxs-lookup"><span data-stu-id="a8798-127">This shape implements the client side of a one-way message exchange.</span></span> <span data-ttu-id="a8798-128">使用することができます、 **IOutputChannel**を任意のデータを返さない SAP システムの RFC を呼び出す例については、応答を使用する必要のない操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a8798-128">You can use an **IOutputChannel** to invoke an operation for which you do not need to consume a response, for example to invoke an RFC on the SAP system that does not return any data.</span></span>  
  
- <span data-ttu-id="a8798-129">**IReplyChannel** (**System.ServiceModel.Channels.IReplyChannel**)。</span><span class="sxs-lookup"><span data-stu-id="a8798-129">**IReplyChannel** (**System.ServiceModel.Channels.IReplyChannel**).</span></span> <span data-ttu-id="a8798-130">この図形は、要求/応答メッセージ交換のサービス側を実装します。</span><span class="sxs-lookup"><span data-stu-id="a8798-130">This shape implements the service side of a request-reply message exchange.</span></span> <span data-ttu-id="a8798-131">使用することができます、 **IReplyChannel** RFC、tRFC またはサーバーを実装するか、SAP システムから Idoc を受信します。</span><span class="sxs-lookup"><span data-stu-id="a8798-131">You can use an **IReplyChannel** to implement an RFC or tRFC server or to receive IDOCs from a SAP system.</span></span>  
  
  <span data-ttu-id="a8798-132">などの任意の WCF バインド、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]ファクトリ パターンを使用して、アプリケーション コードへのチャネルを提供します。</span><span class="sxs-lookup"><span data-stu-id="a8798-132">Like any WCF binding, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses a factory pattern to provide channels to application code.</span></span> <span data-ttu-id="a8798-133">使用する、 **Microsoft.Adapters.SAPBinding**オブジェクトのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a8798-133">You use a **Microsoft.Adapters.SAPBinding** object to create instances of:</span></span>  
  
- <span data-ttu-id="a8798-134">**System.ServiceModel.ChannelFactory\<IRequestChannel\>** を提供する**IRequestChannel**チャネル アダプターの要求-応答操作の呼び出しに使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a8798-134">**System.ServiceModel.ChannelFactory\<IRequestChannel\>** to provide **IRequestChannel** channels you can use to invoke request-response operations on the adapter.</span></span>  
  
- <span data-ttu-id="a8798-135">**System.ServiceModel.ChannelFactory\<IOutputChannel\>** を提供する**IOutputChannel**チャネル アダプターの一方向の操作の呼び出しに使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a8798-135">**System.ServiceModel.ChannelFactory\<IOutputChannel\>** to provide **IOutputChannel** channels you can use to invoke one-way operations on the adapter.</span></span>  
  
- <span data-ttu-id="a8798-136">**System.ServiceModel.IChannelListener\<IReplyChannel\>** を提供する**IReplyChannel**チャネル アダプターから受信要求-応答操作に使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a8798-136">**System.ServiceModel.IChannelListener\<IReplyChannel\>** to provide **IReplyChannel** channels you can use to receive request-response operations from the adapter.</span></span>  
  
## <a name="creating-messages-for-the-sap-adapter-in-the-wcf-channel-model"></a><span data-ttu-id="a8798-137">WCF チャネル モデルで SAP アダプターのメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="a8798-137">Creating Messages for the SAP Adapter in the WCF Channel Model</span></span>  
 <span data-ttu-id="a8798-138">WCF では、 **System.ServiceModel.Channels.Message**クラスでのメモリを提供する SOAP メッセージの表現。</span><span class="sxs-lookup"><span data-stu-id="a8798-138">In WCF the **System.ServiceModel.Channels.Message** class provides an in memory representation of a SOAP message.</span></span> <span data-ttu-id="a8798-139">作成する、**メッセージ**静的を呼び出すことによってインスタンス**Message.Create**メソッド。</span><span class="sxs-lookup"><span data-stu-id="a8798-139">You create a **Message** instance by invoking the static **Message.Create** method.</span></span>  
  
 <span data-ttu-id="a8798-140">2 つの重要な部分を SOAP メッセージを構築する際に指定する必要があります、**メッセージ**インスタンスに送信する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a8798-140">There are two important parts to the SOAP message that you must specify when you construct a **Message** instance to send to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
- <span data-ttu-id="a8798-141">メッセージのアクションは、SOAP メッセージ ヘッダーの一部である文字列です。</span><span class="sxs-lookup"><span data-stu-id="a8798-141">The message action is a string that is part of the SOAP message header.</span></span> <span data-ttu-id="a8798-142">メッセージのアクションを呼び出す必要がある操作を識別する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a8798-142">The message action identifies the operation that should be invoked on [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="a8798-143">SAP システムで SD_RFC_CUSTOMER_GET RFC を呼び出すように指定したメッセージのアクションを次に示します:`http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET`します。</span><span class="sxs-lookup"><span data-stu-id="a8798-143">The following shows the message action that is specified to invoke the SD_RFC_CUSTOMER_GET RFC on an SAP system: `http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET`.</span></span>  
  
- <span data-ttu-id="a8798-144">メッセージの本文には、操作のパラメーターのデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a8798-144">The message body contains the parameter data for the operation.</span></span> <span data-ttu-id="a8798-145">メッセージ本文が想定されているメッセージのスキーマに対応する、整形式 xml で構成される、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]要求された操作をします。</span><span class="sxs-lookup"><span data-stu-id="a8798-145">The message body is composed of well-formed XML that corresponds to the message schema expected by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] for the requested operation.</span></span> <span data-ttu-id="a8798-146">次のメッセージ本文には、SAP システムで SD_RFC_CUSTOMER_GET RFC のパラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a8798-146">The following message body contains the parameters for the SD_RFC_CUSTOMER_GET RFC on an SAP system.</span></span>  
  
  ```  
  <SD_RFC_CUSTOMER_GET xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> <KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>  
  ```  
  
  <span data-ttu-id="a8798-147">については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]メッセージ スキーマと操作のアクションのメッセージを参照してください[メッセージと BizTalk adapter for mySAP Business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)します。</span><span class="sxs-lookup"><span data-stu-id="a8798-147">For information about the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] message schemas and message actions for operations, see [Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).</span></span>  
  
  <span data-ttu-id="a8798-148">**Message.Create**メソッドがオーバー ロードされ、メッセージ本文を提供するためのさまざまなオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="a8798-148">The **Message.Create** method is overloaded and offers many different options for providing the message body.</span></span> <span data-ttu-id="a8798-149">次のコードを作成する方法を示しています、**メッセージ**インスタンスを使用して、 **System.Xml.XmlReader**メッセージ本文を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8798-149">The following code shows how to create a **Message** instance by using an **System.Xml.XmlReader** to supply the message body.</span></span> <span data-ttu-id="a8798-150">このコードは、メッセージ本文は文字列定数から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="a8798-150">In this code, the message body is read from a string constant.</span></span>  
  
```  
//create an XML message to send to the SAP system  
//We are invoking the SD_RFC_CUSTOMER_GET RFC.  
//The XML below specifies that we want to search for customers with names starting with "AB"  
string inputXml = "<SD_RFC_CUSTOMER_GET xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"> <KUNNR i:nil=\"true\" xmlns:i=\"http://www.w3.org/2001/XMLSchema-instance\"> </KUNNR> <NAME1>AB*</NAME1> <CUSTOMER_T> </CUSTOMER_T> </SD_RFC_CUSTOMER_GET>";  
  
//create an XML reader from the input XML  
XmlReader reader = XmlReader.Create(new MemoryStream(Encoding.Default.GetBytes(inputXml)));  
  
//create a WCF message from the XML reader  
Message inputMessge = Message.CreateMessage(MessageVersion.Soap11, "http://Microsoft.LobServices.Sap/2007/03/Rfc/SD_RFC_CUSTOMER_GET", reader);  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="a8798-151">メッセージのアクションを指定する必要があります、**メッセージ**インスタンス。</span><span class="sxs-lookup"><span data-stu-id="a8798-151">You must provide a message action in your **Message** instance.</span></span> <span data-ttu-id="a8798-152">これは、通常はときに、**メッセージ**インスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a8798-152">This is typically done when the **Message** instance is created.</span></span>  
  
## <a name="streaming-support-on-the-sap-adapter-in-the-wcf-channel-model"></a><span data-ttu-id="a8798-153">WCF チャネル モデルで SAP アダプターのストリーミング サポート</span><span class="sxs-lookup"><span data-stu-id="a8798-153">Streaming Support on the SAP Adapter in the WCF Channel Model</span></span>  
 <span data-ttu-id="a8798-154">作成し、SAP アダプターと交換するメッセージを使用する方法、コードとアダプター間のメッセージをストリーミングする方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="a8798-154">How you create and consume the messages that you exchange with the SAP adapter determines how the message is streamed between your code and the adapter.</span></span>  
  
### <a name="node-streaming"></a><span data-ttu-id="a8798-155">ノードのストリーミング</span><span class="sxs-lookup"><span data-stu-id="a8798-155">Node streaming</span></span>  
 <span data-ttu-id="a8798-156">ノードのストリーミングは、ストリーミング、SendIdoc および ReceiveIdoc 操作を除くすべての操作はサポートされてのみレベルです。</span><span class="sxs-lookup"><span data-stu-id="a8798-156">Node streaming is the only level of streaming supported for all operations except the SendIdoc and ReceiveIdoc operations.</span></span>  
  
 <span data-ttu-id="a8798-157">ノードが、メッセージのストリーミングを実行すること。</span><span class="sxs-lookup"><span data-stu-id="a8798-157">To perform node streaming for a message, you:</span></span>  
  
-   <span data-ttu-id="a8798-158">使用して、送信メッセージを作成、 **XmlReader**メッセージ本文を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8798-158">Create an outbound message using an **XmlReader** to supply the message body.</span></span>  
  
-   <span data-ttu-id="a8798-159">受信メッセージを使用して、処理、 **XmlReader**します。</span><span class="sxs-lookup"><span data-stu-id="a8798-159">Consume an inbound message using an **XmlReader**.</span></span> <span data-ttu-id="a8798-160">呼び出すことで、リーダーを取得する、 **GetReaderAtBodyContents**受信メソッド**メッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="a8798-160">You get the reader by calling the **GetReaderAtBodyContents** method on the inbound **Message**.</span></span>  
  
### <a name="node-value-streaming"></a><span data-ttu-id="a8798-161">ノード値のストリーミング</span><span class="sxs-lookup"><span data-stu-id="a8798-161">Node-value Streaming</span></span>  
 <span data-ttu-id="a8798-162">SendIdoc と ReceiveIdoc 操作には、1 つの XML ノードの下の文字列で IDOC データが含まれるので (\<idocData\>)、アダプターがサポートされますノード-値これらの操作にストリーミングします。</span><span class="sxs-lookup"><span data-stu-id="a8798-162">Because the SendIdoc and ReceiveIdoc operations contain the IDOC data in a string under a single XML node (\<idocData\>), the adapter supports node-value streaming on these operations.</span></span>  
  
 <span data-ttu-id="a8798-163">ノード値のストリームのこれらの操作を実行するのには、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="a8798-163">To perform node-value streaming for these operations, you can:</span></span>  
  
- <span data-ttu-id="a8798-164">SendIdoc 要求メッセージ (送信) を使用して、作成、 **BodyWriter**ノード値が、メッセージ本文を指定するストリーミングを実装します。</span><span class="sxs-lookup"><span data-stu-id="a8798-164">Create the SendIdoc request message (outbound) using a **BodyWriter** that implements node-value streaming to supply the message body.</span></span>  
  
- <span data-ttu-id="a8798-165">ReceiveIdoc 要求メッセージを処理 (受信) を呼び出して、 **WriteBodyContents**メソッドを持つメッセージを**XmlDictionaryWriter**ノード値のストリーミングを実装します。</span><span class="sxs-lookup"><span data-stu-id="a8798-165">Consume the ReceiveIdoc request message (inbound) by calling the **WriteBodyContents** method on the message with an **XmlDictionaryWriter** that implements node-value streaming.</span></span>  
  
  <span data-ttu-id="a8798-166">WCF チャネル モデルを使用してフラット ファイル (string) Idoc をストリームの詳細については、[WCF チャネル モデルを使用して SAP でのフラット ファイル Idoc のストリーミング](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8798-166">For more information about streaming flat file (string) IDOCs using the WCF channel model, see [Streaming Flat-File IDOCs in SAP using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8798-167">参照</span><span class="sxs-lookup"><span data-stu-id="a8798-167">See Also</span></span>  
[<span data-ttu-id="a8798-168">WCF チャネル モデルを使用してアプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="a8798-168">Develop applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)