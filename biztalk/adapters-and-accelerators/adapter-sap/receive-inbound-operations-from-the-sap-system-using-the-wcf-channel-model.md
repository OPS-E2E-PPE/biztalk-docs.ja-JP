---
title: WCF チャネル モデルを使用して、SAP システムからの受信操作の受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, streaming inbound flat-file IDOCs
- WCF channel model, receiving inbound operations from the SAP system
- WCF channel model, raising an exception
ms.assetid: d71d0537-fda4-44ab-85dc-6e27aad23caf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7c0c819372cf23842eb5311df8636e55e28c72a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969683"
---
# <a name="receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model"></a><span data-ttu-id="27f57-102">WCF チャネル モデルを使用して、SAP システムからの受信操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="27f57-102">Receive Inbound Operations from the SAP System Using the WCF Channel Model</span></span>
<span data-ttu-id="27f57-103">RFC サーバーとして動作し、SAP システム (IDOC を送信、RFC を呼び出すなど) によって呼び出された操作の受信、経由での SAP プログラム ID からのメッセージをリッスンできるチャネル リスナーを作成する必要があります、 **System.ServiceModel.Channels.IReplyChannel**チャネル形状です。</span><span class="sxs-lookup"><span data-stu-id="27f57-103">To act as an RFC server and receive operations invoked by the SAP system (such as sending an IDOC or invoking an RFC), you must create a channel listener that can listen for messages from a SAP Program ID over a **System.ServiceModel.Channels.IReplyChannel** channel shape.</span></span>  
  
 <span data-ttu-id="27f57-104">チャネル リスナー (**System.ServiceModel.Channels.IChannelListener**) は、特定の WCF エンドポイントからメッセージを受信するために使用する WCF 通信オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="27f57-104">A channel listener (**System.ServiceModel.Channels.IChannelListener**) is a WCF communication object that can be used to receive messages from specific WCF endpoints.</span></span> <span data-ttu-id="27f57-105">チャネル リスナーは、サービスによって、クライアント (SAP システム) によって呼び出されたメッセージを受信できるチャネルを作成するためのファクトリとして機能します。</span><span class="sxs-lookup"><span data-stu-id="27f57-105">The channel listener functions as a factory from which you can create channels over which messages invoked by a client (the SAP system) can be received by your service.</span></span> <span data-ttu-id="27f57-106">チャネル リスナーを作成する、 **Microsoft.Adapters.SAP.SAPBinding**オブジェクトを呼び出すことによって、 **BuildChannelListener**メソッド。</span><span class="sxs-lookup"><span data-stu-id="27f57-106">You create a channel listener by from a **Microsoft.Adapters.SAP.SAPBinding** object by invoking the **BuildChannelListener** method.</span></span> <span data-ttu-id="27f57-107">SAP 接続元の受信操作はこのメソッドを受信する SAP プログラム ID を指定する URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="27f57-107">You supply an SAP connection URI that specifies the SAP Program ID from which inbound operations will be received to this method.</span></span>  
  
 <span data-ttu-id="27f57-108">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サポート、 **IReplyChannel**チャネル形状です。</span><span class="sxs-lookup"><span data-stu-id="27f57-108">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports the **IReplyChannel** channel shape.</span></span> <span data-ttu-id="27f57-109">**IReplyChannel**チャネルが受信要求-応答メッセージ交換パターンをサポートします。</span><span class="sxs-lookup"><span data-stu-id="27f57-109">**IReplyChannel** channels support an inbound request-response message exchange pattern.</span></span> <span data-ttu-id="27f57-110">つまり、外部プログラムが、チャネルとプログラム経由で要求メッセージを送信するパターンは、応答を返します。</span><span class="sxs-lookup"><span data-stu-id="27f57-110">That is, a pattern in which an external program sends a request message over the channel and your program returns a response.</span></span>  
  
 <span data-ttu-id="27f57-111">受信操作を使用する方法の概要については、 **IReplyChannel** WCF では、[サービス チャネル レベルのプログラミング](https://msdn.microsoft.com/library/ms789029.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27f57-111">For an overview of how to receive operations using an **IReplyChannel** in WCF, see [Service Channel-Level Programming](https://msdn.microsoft.com/library/ms789029.aspx).</span></span>
  
 <span data-ttu-id="27f57-112">このセクションでは、SAP システムからの操作の受信に固有の次のトピックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="27f57-112">This section covers the following topics that are specific to receiving operations from a SAP system:</span></span>  
  
-   <span data-ttu-id="27f57-113">チャネル リスナーを使用して特定の操作に対してフィルター処理する方法。</span><span class="sxs-lookup"><span data-stu-id="27f57-113">How to filter for specific operations using the channel listener.</span></span>  
  
-   <span data-ttu-id="27f57-114">SAP システムで例外を発生させる方法。</span><span class="sxs-lookup"><span data-stu-id="27f57-114">How to raise an exception on the SAP system.</span></span>  
  
-   <span data-ttu-id="27f57-115">SAP アダプターからのフラット ファイル Idoc の受信をストリーミングします。</span><span class="sxs-lookup"><span data-stu-id="27f57-115">Streaming inbound flat-file IDOCs from the SAP adapter.</span></span>  
  
-   <span data-ttu-id="27f57-116">SAP システムから操作を受信する方法。</span><span class="sxs-lookup"><span data-stu-id="27f57-116">How to receive operations from the SAP system.</span></span>  
  
## <a name="how-do-i-filter-operations-using-the-channel-listener"></a><span data-ttu-id="27f57-117">チャネル リスナーを使用して操作をフィルター処理する方法</span><span class="sxs-lookup"><span data-stu-id="27f57-117">How Do I Filter Operations Using the Channel Listener?</span></span>  
  
### <a name="using-an-inboundactioncollection-to-filter-operations"></a><span data-ttu-id="27f57-118">InboundActionCollection を使用して操作をフィルター処理するには</span><span class="sxs-lookup"><span data-stu-id="27f57-118">Using an InboundActionCollection to Filter Operations</span></span>  
 <span data-ttu-id="27f57-119">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供、 **Microsoft.ServiceModel.Channels.InboundActionCollection**チャネル リスナーによって受信され、アプリケーション コードに渡されるされる操作をフィルター処理するためのクラス。</span><span class="sxs-lookup"><span data-stu-id="27f57-119">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] provides the **Microsoft.ServiceModel.Channels.InboundActionCollection** class to enable you to filter operations that are received by a channel listener and passed to your application code.</span></span> <span data-ttu-id="27f57-120">特定の操作をフィルターするには、リスナー エンドポイント URI を使用してこのクラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="27f57-120">To filter for specific operations, you create an instance of this class by using the listener endpoint URI.</span></span> <span data-ttu-id="27f57-121">コレクションに対象の操作ごとに (要求) メッセージのアクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="27f57-121">Then you add the (request) message action for each target operation to the collection.</span></span> <span data-ttu-id="27f57-122">最後に、受信アクションのコレクションを追加、 **System.ServiceModel.Channels.BindingParameterCollection**オブジェクトし、チャネル リスナーを作成する呼び出しにこのバインディング パラメーターのコレクションを渡します。</span><span class="sxs-lookup"><span data-stu-id="27f57-122">Finally, you add the inbound action collection to a **System.ServiceModel.Channels.BindingParameterCollection** object and then pass this binding parameter collection into the call to create the channel listener.</span></span>  
  
 <span data-ttu-id="27f57-123">場合は、SAP システムでは、受信アクションのコレクションではない操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="27f57-123">If the SAP system invokes an operation that is not in the inbound action collection:</span></span>  
  
- <span data-ttu-id="27f57-124">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムを次のメッセージで例外の例外を呼び出し元に返します。"受信 RFC 呼び出し [RFC_NAME] を Rfc サーバーが処理されない"。</span><span class="sxs-lookup"><span data-stu-id="27f57-124">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] returns an EXCEPTION exception to the caller on the SAP system with the following message: "The incoming RFC call [RFC_NAME] on the Rfc Server is not handled".</span></span> <span data-ttu-id="27f57-125">このメッセージの [RFC_NAME] は、RFC (たとえば、IDOC_INBOUND_ASYNCHRONOUS) の名前です。</span><span class="sxs-lookup"><span data-stu-id="27f57-125">In this message, [RFC_NAME] is the name of the RFC (for example, IDOC_INBOUND_ASYNCHRONOUS).</span></span>  
  
- <span data-ttu-id="27f57-126">アダプターがスローされます、 **Microsoft.ServiceModel.Channels.Common.AdapterException**受信した操作を示すメッセージを使用します。</span><span class="sxs-lookup"><span data-stu-id="27f57-126">The adapter throws a **Microsoft.ServiceModel.Channels.Common.AdapterException** with a message that indicates the operation that was received.</span></span> <span data-ttu-id="27f57-127">この例外を使用する方法の例は、このトピックの最後の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27f57-127">For an example of how to use this exception, see the example at the end of this topic.</span></span>  
  
  <span data-ttu-id="27f57-128">次のコード例を使用する方法を示しています、 **InboundActionCollection** Z_RFC_MKD_DIV、1 つの RFC をフィルター処理するチャネル リスナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="27f57-128">The following code example shows how to use an **InboundActionCollection** to create a channel listener that filters for a single RFC, Z_RFC_MKD_DIV.</span></span>  
  
```  
// The connection Uri must specify listener parameters (or an R-type destination in saprfc.ini)  
// and credentials.  
Uri listeneraddress =  
    new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGATEWAY&ListenerGwHost=YourSAPHost&ListenerProgramId=SAPAdapter");  
  
// Create a binding and set AcceptCredentialsInUri to true  
SAPBinding binding = new SAPBinding();  
binding.AcceptCredentialsInUri = true;  
  
// Create an InboundActionCollection and add the message actions to listen for,  
// only the actions added to the InboundActionCollection are received on the channel.  
// In this case a single action is specified: http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV  
InboundActionCollection actions = new InboundActionCollection(listeneraddress);  
actions.Add("http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV");  
  
// Create a BindingParameterCollection and add the InboundActionCollection  
BindingParameterCollection bpcol = new BindingParameterCollection();  
bpcol.Add(actions);  
  
// Create the channel listener by specifying the binding parameter collection (to filter for the Z_RFC_MKD_DIV action)  
listener = binding.BuildChannelListener<IReplyChannel>(listeneraddress, bpcol);  
```  
  
### <a name="manually-filtering-operations"></a><span data-ttu-id="27f57-129">手動でフィルター処理</span><span class="sxs-lookup"><span data-stu-id="27f57-129">Manually Filtering Operations</span></span>  
 <span data-ttu-id="27f57-130">チャネル リスナーを受信アクションのコレクションを指定しない場合、SAP システムによって呼び出されるすべての操作はコードに渡すされます。</span><span class="sxs-lookup"><span data-stu-id="27f57-130">If you do not specify an inbound action collection for the channel listener, then all operations invoked by the SAP system will be passed to your code.</span></span> <span data-ttu-id="27f57-131">手動で、受信要求のメッセージのアクションを確認してこのような操作をフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="27f57-131">You can manually filter such operations by checking the message action of inbound requests.</span></span>  
  
 <span data-ttu-id="27f57-132">そのコンテンツに基づいて操作をフィルター処理するシナリオもあります。</span><span class="sxs-lookup"><span data-stu-id="27f57-132">There may also be scenarios in which you want to filter an operation based on its content.</span></span> <span data-ttu-id="27f57-133">例での Idoc を受信している場合。</span><span class="sxs-lookup"><span data-stu-id="27f57-133">For example if you are receiving IDOCs in:</span></span>  
  
- <span data-ttu-id="27f57-134">文字列の形式 (、 **ReceiveIDocFormat**プロパティのバインドは**文字列**) すべて; ReceiveIdoc 操作を使用して Idoc を受信します。</span><span class="sxs-lookup"><span data-stu-id="27f57-134">String format (the **ReceiveIDocFormat** binding property is **String**); all IDOCs are received using the ReceiveIdoc operation.</span></span>  
  
- <span data-ttu-id="27f57-135">Rfc 形式 (、 **ReceiveIDocFormat**プロパティのバインドは**Rfc**) すべて; IDOC_INBOUND_ASYNCHRONOUS RFC または INBOUND_IDOC_PROCESS RFC を使用して Idoc を受信します。</span><span class="sxs-lookup"><span data-stu-id="27f57-135">Rfc format (the **ReceiveIDocFormat** binding property is **Rfc**); all IDOCs are received using either the IDOC_INBOUND_ASYNCHRONOUS RFC or the INBOUND_IDOC_PROCESS RFC.</span></span>  
  
  <span data-ttu-id="27f57-136">実装するこのシナリオでは、IDOC の種類) など、コード内の特定の IDOC パラメーターに基づくフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="27f57-136">In this scenario you may want to implement filtering based on specific IDOC parameters (such as the IDOC type) in your code.</span></span>  
  
  <span data-ttu-id="27f57-137">操作を手動でフィルター処理する場合にエラーを返すことができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]処理しない操作。</span><span class="sxs-lookup"><span data-stu-id="27f57-137">When you filter operations manually, you can return a fault to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] for operations that you don't handle.</span></span> <span data-ttu-id="27f57-138">これにより、SAP システムの呼び出し元に例外の例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="27f57-138">This will raise the EXCEPTION exception to the caller on the SAP System.</span></span> <span data-ttu-id="27f57-139">SAP で例外が発生しない場合は、空の応答を返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="27f57-139">You can also return an empty response if you don't want to raise an exception on SAP.</span></span>  
  
  <span data-ttu-id="27f57-140">次のコードでは、Z_RFC_MKD_DIV 操作を手動でフィルター処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="27f57-140">The following code shows how to filter manually for the Z_RFC_MKD_DIV operation.</span></span>  
  
```  
// Get the message from the channel  
RequestContext rc = channel.ReceiveRequest();  
Message reqMessage = rc.RequestMessage;  
  
// Filter based on the message action.  
if (reqMessage.Headers.Action == "http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV")  
{  
  
    // Process message and return response.  
    ...  
  
}  
else  
{  
    // If this isn't the correct message return an empty response or a fault message.  
    // This example returns an empty response.  
    rc.Reply(Message.CreateMessage(MessageVersion.Default, reqMessage.Headers.Action + "/response"));  
}  
```  
  
## <a name="how-do-i-raise-an-exception-on-the-sap-system"></a><span data-ttu-id="27f57-141">SAP システムで例外を発生させる方法</span><span class="sxs-lookup"><span data-stu-id="27f57-141">How Do I Raise an Exception on the SAP System?</span></span>  
 <span data-ttu-id="27f57-142">SAP システムの呼び出し元にエラーを示すには、SOAP エラーで要求メッセージに返信することができます。</span><span class="sxs-lookup"><span data-stu-id="27f57-142">To indicate an error to the caller on the SAP system you can reply to a request message with a SOAP fault.</span></span> <span data-ttu-id="27f57-143">SOAP エラーに戻ったら、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプターは、SAP システムで、呼び出し元に例外例外を返します。</span><span class="sxs-lookup"><span data-stu-id="27f57-143">When you return a SOAP fault to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], the adapter returns an EXCEPTION exception to the caller on the SAP system.</span></span> <span data-ttu-id="27f57-144">例外メッセージは、SOAP エラーの要素から作成されます。</span><span class="sxs-lookup"><span data-stu-id="27f57-144">The exception message is created from the elements of the SOAP fault.</span></span>  
  
 <span data-ttu-id="27f57-145">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次の優先順位に従って SAP 例外のメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="27f57-145">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] creates the message for the SAP EXCEPTION according to the following order of precedence:</span></span>  
  
1.  <span data-ttu-id="27f57-146">SOAP エラーに詳細オブジェクトが含まれている場合は、アダプターを文字列の詳細をシリアル化し、例外メッセージは、この文字列に設定されます。</span><span class="sxs-lookup"><span data-stu-id="27f57-146">If the SOAP fault contains a detail object, the adapter serializes the detail to a string and the exception message is set to this string.</span></span>  
  
2.  <span data-ttu-id="27f57-147">SOAP エラーに理由が含まれている場合、例外メッセージは、その値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="27f57-147">If the SOAP fault contains a reason, the exception message is set to its value.</span></span>  
  
3.  <span data-ttu-id="27f57-148">それ以外の場合、アダプターがシリアル化、 **MessageFault**文字列および例外メッセージをオブジェクト自体がこの文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="27f57-148">Otherwise, the adapter serializes the **MessageFault** object itself to a string and the exception message is set to this string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27f57-149">アダプターでは、SAP システムで発生する例外で返された例外メッセージを作成するのにエラー メッセージのみが使用します。そのため、これらのエンティティに設定した値は、責任は完全にです。</span><span class="sxs-lookup"><span data-stu-id="27f57-149">The adapter only uses the fault message to create the exception message returned in the exception raised on the SAP system; therefore, the values that you set for these entities is completely up to you.</span></span>  
  
 <span data-ttu-id="27f57-150">WCF の提供、 **System.ServiceModel.Channels.MessageFault**の SOAP エラー、メモリ内表現をカプセル化するクラス。</span><span class="sxs-lookup"><span data-stu-id="27f57-150">WCF provides the **System.ServiceModel.Channels.MessageFault** class to encapsulate an in-memory representation of a SOAP fault.</span></span> <span data-ttu-id="27f57-151">Static のいずれかを使用するオーバー ロードされた**MessageFault.CreateFault**元となることができますし、エラー メッセージを作成するを呼び出して、適切な新しい SOAP エラーを作成するメソッドを**Message.CreateMessage**オーバー ロードします。</span><span class="sxs-lookup"><span data-stu-id="27f57-151">You can use any of the static, overloaded **MessageFault.CreateFault** methods to create a new SOAP fault from which you can then create a fault message by invoking the appropriate **Message.CreateMessage** overload.</span></span> <span data-ttu-id="27f57-152">WCF は、のオーバー ロードも用意されています。 **CreateMessage**を使用せず、エラー メッセージを作成する、 **MessageFault**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="27f57-152">WCF also provides overloads of **CreateMessage** that create a fault message without using a **MessageFault** object.</span></span>  
  
 <span data-ttu-id="27f57-153">使用する、 **System.ServiceModel.Channels.RequestContext.Reply**をアダプターにフォールト メッセージを返すメソッド。</span><span class="sxs-lookup"><span data-stu-id="27f57-153">You use the **System.ServiceModel.Channels.RequestContext.Reply** method to return the fault message to the adapter.</span></span> <span data-ttu-id="27f57-154">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]メッセージのアクションを任意の値に設定できるように、エラー メッセージのメッセージのアクションは無視されます。</span><span class="sxs-lookup"><span data-stu-id="27f57-154">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] ignores the message action for fault messages, so you can set the message action to any value.</span></span>  
  
 <span data-ttu-id="27f57-155">次の例にエラー メッセージを返す方法を示しています、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="27f57-155">The following example shows how to return a fault message to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="27f57-156">この例では、チャネル リスナーとチャネルを作成する手順を省略します。</span><span class="sxs-lookup"><span data-stu-id="27f57-156">This example omits the steps to create the channel listener and channel.</span></span>  
  
```  
RequestContext rc = channel.ReceiveRequest();  
…  
// Start processing the inbound message  
…  
// If an error is encountered return a fault to the SAP system  
// This example uses CreateMessage overload to create a fault message.  
// The overload takes a SOAP version, fault code, reason, and message action  
// The SAP adapter ignores the message action for a fault so you can set it to any value you want.   
Message faultMessage = Message.CreateMessage(MessageVersion.Default, new FaultCode("SAP Example Fault"), "Testing SAP Faults", rc.RequestMessage.Headers.Action + "/fault");  
  
rc.Reply(faultMessage);  
```  
  
## <a name="streaming-inbound-flat-file-idocs-from-the-sap-adapter"></a><span data-ttu-id="27f57-157">受信フラット ファイル Idoc を SAP アダプターからストリーミング</span><span class="sxs-lookup"><span data-stu-id="27f57-157">Streaming Inbound Flat-File IDOCs from the SAP Adapter</span></span>  
 <span data-ttu-id="27f57-158">(String) Idoc 受信 ReceiveIdoc 操作でアダプターからのフラット ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27f57-158">You receive flat-file (string) IDOCs from the adapter in the inbound ReceiveIdoc operation.</span></span> <span data-ttu-id="27f57-159">IDOC データは、この操作で 1 つのノードの下の文字列として表されます。</span><span class="sxs-lookup"><span data-stu-id="27f57-159">The IDOC data is represented as a string under a single node in this operation.</span></span> <span data-ttu-id="27f57-160">このため、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]ノード値の要求メッセージのストリーミングをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="27f57-160">For this reason, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports node-value streaming on the request message.</span></span> <span data-ttu-id="27f57-161">ノード値のストリーミングを実行するのには、呼び出すことによって ReceiveIdoc 操作の要求メッセージを使用する必要があります、 **Message.WriteBodyContents**メソッドを**System.Xml.XmlDictionaryWriter**ですIDOC データをストリーミングすることができます。</span><span class="sxs-lookup"><span data-stu-id="27f57-161">To perform node-value streaming, you must consume the request message for the ReceiveIdoc operation by invoking the **Message.WriteBodyContents** method with a **System.Xml.XmlDictionaryWriter** that is capable of streaming the IDOC data.</span></span> <span data-ttu-id="27f57-162">これを行う方法については、[WCF チャネル モデルを使用して SAP でのフラット ファイル Idoc のストリーミング](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27f57-162">For information about how to do this, see [Streaming Flat-File IDOCs in SAP using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="how-do-i-receive-operations-from-a-sap-system-using-an-ireplychannel"></a><span data-ttu-id="27f57-163">IReplyChannel を使用して SAP システムから操作を受信する方法</span><span class="sxs-lookup"><span data-stu-id="27f57-163">How Do I Receive Operations from a SAP System Using an IReplyChannel?</span></span>  
 <span data-ttu-id="27f57-164">WCF チャネル モデルを使用して、SAP システムから操作を受信するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27f57-164">To receive operations from a SAP system by using the WCF channel model, perform the following steps.</span></span>  
  
#### <a name="to-receive-operations-from-the-sap-system-using-an-ireplychannel"></a><span data-ttu-id="27f57-165">操作を IReplyChannel を使用して、SAP システムから受信するには</span><span class="sxs-lookup"><span data-stu-id="27f57-165">To receive operations from the SAP system using an IReplyChannel</span></span>  
  
1.  <span data-ttu-id="27f57-166">インスタンスを作成**SAPBinding**を受信する操作に必要なバインドのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="27f57-166">Create an instance of **SAPBinding** and set the binding properties required to for the operations you want to receive.</span></span> <span data-ttu-id="27f57-167">設定する必要がありますには、少なくとも、 **AcceptCredentialsInUri**プロパティを true にバインドします。</span><span class="sxs-lookup"><span data-stu-id="27f57-167">At a minimum you must set the **AcceptCredentialsInUri** binding property to true.</span></span> <span data-ttu-id="27f57-168">TRFC サーバーとして機能しを設定する必要があります、 **TidDatabaseConnectionString**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="27f57-168">To act as a tRFC server, you must set the **TidDatabaseConnectionString** binding property.</span></span> <span data-ttu-id="27f57-169">バインド プロパティの詳細については、[mySAP Business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27f57-169">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
    ```  
    SAPBinding binding = new SAPBinding();  
    binding.AcceptCredentialsInUri = true;  
    ```  
  
2.  <span data-ttu-id="27f57-170">作成、 **BindingParameterCollection**を追加し、 **InboundActionCollection**を受信する操作のアクションを格納しています。</span><span class="sxs-lookup"><span data-stu-id="27f57-170">Create a **BindingParameterCollection** and add an **InboundActionCollection** that contains the actions of the operations that you want to receive.</span></span> <span data-ttu-id="27f57-171">アダプターでは、その他のすべての操作の SAP システムに例外を返します。</span><span class="sxs-lookup"><span data-stu-id="27f57-171">The adapter will return an exception to the SAP system for all other operations.</span></span> <span data-ttu-id="27f57-172">このステップは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="27f57-172">This step is optional.</span></span> <span data-ttu-id="27f57-173">詳細については、[WCF チャネル モデルを使用して、SAP システムからの受信操作の受信](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27f57-173">For more information, see [Receiving Inbound Operations from the SAP System Using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md).</span></span>  
  
    ```  
    InboundActionCollection actions = new InboundActionCollection(listeneraddress);  
    actions.Add("http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV");  
    BindingParameterCollection bpcol = new BindingParameterCollection();  
    bpcol.Add(actions);  
    ```  
  
3.  <span data-ttu-id="27f57-174">呼び出してチャネル リスナーを作成して**BuildChannelListener < IReplyChannel\>** メソッドを**SAPBinding**を開きます。</span><span class="sxs-lookup"><span data-stu-id="27f57-174">Create a channel listener by invoking **BuildChannelListener<IReplyChannel\>** method on the **SAPBinding** and open it.</span></span> <span data-ttu-id="27f57-175">このメソッドにパラメーターの 1 つとして、SAP 接続 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="27f57-175">You specify the SAP connection URI as one of the parameters to this method.</span></span> <span data-ttu-id="27f57-176">接続 URI は、SAP システムの RFC 転送先のパラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="27f57-176">The connection URI must contain parameters for an RFC Destination on the SAP system.</span></span> <span data-ttu-id="27f57-177">SAP 接続 URI の詳細については、[SAP システム接続 URI の作成](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27f57-177">For more information about the SAP connection URI, see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span> <span data-ttu-id="27f57-178">作成した場合、 **BindingParameterCollection**手順 3 で指定することもこのチャネル リスナーを作成するときにします。</span><span class="sxs-lookup"><span data-stu-id="27f57-178">If you created a **BindingParameterCollection** in step 3, you also specify this when you create the channel listener.</span></span>  
  
    ```  
    Uri listeneraddress =  
        new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGATEWAY&ListenerGwHost=YourSAPHost&ListenerProgramId=SAPAdapter");  
    IChannelListener<IReplyChannel> listener = binding.BuildChannelListener<IReplyChannel>(connectionUri, bpcol);  
    listener.Open();  
    ```  
  
4.  <span data-ttu-id="27f57-179">取得、 **IReplyChannel**チャネルを呼び出すことによって、 **AcceptChannel**メソッド リスナーを開きます。</span><span class="sxs-lookup"><span data-stu-id="27f57-179">Get an **IReplyChannel** channel by invoking the **AcceptChannel** method on the listener and open it.</span></span>  
  
    ```  
    IReplyChannel channel = listener.AcceptChannel();  
    channel.Open();  
    ```  
  
5.  <span data-ttu-id="27f57-180">呼び出す**ReceiveRequest**で次の操作をアダプターから要求メッセージを取得するチャネル。</span><span class="sxs-lookup"><span data-stu-id="27f57-180">Invoke **ReceiveRequest** on the channel to get the request message for the next operation from the adapter.</span></span>  
  
    ```  
    RequestContext rc = channel.ReceiveRequest();  
    ```  
  
6.  <span data-ttu-id="27f57-181">アダプターによって送信された要求メッセージを消費します。</span><span class="sxs-lookup"><span data-stu-id="27f57-181">Consume the request message sent by the adapter.</span></span> <span data-ttu-id="27f57-182">要求メッセージを取得する、 **RequestMessage**のプロパティ、 **RequestContext**します。</span><span class="sxs-lookup"><span data-stu-id="27f57-182">You get the request message from the **RequestMessage** property of the **RequestContext**.</span></span> <span data-ttu-id="27f57-183">いずれかを使用してメッセージを処理することができます、 **XmlReader**または**XmlDictionaryWriter**します。</span><span class="sxs-lookup"><span data-stu-id="27f57-183">You can consume the message using either an **XmlReader** or an **XmlDictionaryWriter**.</span></span>  
  
    ```  
    XmlReader reader = (XmlReader)rc.RequestMessage.GetReaderAtBodyContents();  
    ```  
  
7.  <span data-ttu-id="27f57-184">SAP システムへの応答またはエラーを返すことによって、操作を完了します。</span><span class="sxs-lookup"><span data-stu-id="27f57-184">Complete the operation by returning a response or fault to the SAP system:</span></span>  
  
    1.  <span data-ttu-id="27f57-185">メッセージを処理し、アダプターに応答メッセージを返すことによって、SAP システムへの応答を返します。</span><span class="sxs-lookup"><span data-stu-id="27f57-185">Process the message and return a response to the SAP system by returning the response message to the adapter.</span></span> <span data-ttu-id="27f57-186">この例では、空のメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="27f57-186">This example returns an empty message.</span></span>  
  
        ```  
        respMessage = Message.CreateMessage(MessageVersion.Default, rc.RequestMessage.Headers.Action + "/response");  
        rc.Reply(respMessage);  
        ```  
  
    2.  <span data-ttu-id="27f57-187">SAP システムをアダプターにフォールト メッセージを返すことによって、例外を返します。</span><span class="sxs-lookup"><span data-stu-id="27f57-187">Return an exception to the SAP system by returning a fault message to the adapter.</span></span> <span data-ttu-id="27f57-188">メッセージのアクション、エラー コード、および理由は、任意の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="27f57-188">You can use any value for the message action, fault code, and reason.</span></span>  
  
        ```  
        MessageFault fault = MessageFault.CreateFault(new FaultCode("ProcFault"), "Processing Error");  
        Message respMessage = Message.CreateMessage(MessageVersion.Default, fault, String.Empty);  
        rc.Reply(respMessage);  
        ```  
  
8.  <span data-ttu-id="27f57-189">メッセージを送信した後は、要求コンテキストを閉じます。</span><span class="sxs-lookup"><span data-stu-id="27f57-189">Close the request context after you have sent the message.</span></span>  
  
    ```  
    rc.Close();  
    ```  
  
9. <span data-ttu-id="27f57-190">要求の処理が完了したら、チャネルを閉じます。</span><span class="sxs-lookup"><span data-stu-id="27f57-190">Close the channel when you have completed processing the request.</span></span>  
  
    ```  
    channel.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="27f57-191">操作の処理が完了した後、チャネルを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="27f57-191">You must close the channel after you have finished processing the operation.</span></span> <span data-ttu-id="27f57-192">チャネルを閉じない、コードの動作に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="27f57-192">Failure to close the channel may affect the behavior of your code.</span></span>  
  
10. <span data-ttu-id="27f57-193">SAP システムからの操作の受信が完了したら、リスナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="27f57-193">Close the listener when you are finished receiving operations from the SAP system.</span></span>  
  
    ```  
    listener.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="27f57-194">完了したら、リスナーを明示的に閉じる必要がありますを使用します。それ以外の場合、プログラムが適切に動作しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="27f57-194">You must explicitly close the listener when you are done using it; otherwise, your program may not behave properly.</span></span> <span data-ttu-id="27f57-195">リスナーを閉じる、リスナーを使用して作成されるチャネルは閉じられません。</span><span class="sxs-lookup"><span data-stu-id="27f57-195">Closing the listener does not close channels created using the listener.</span></span> <span data-ttu-id="27f57-196">各チャネル リスナーを使用して作成を明示的に閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="27f57-196">You must also explicitly close each channel created using the listener.</span></span>  
  
### <a name="example"></a><span data-ttu-id="27f57-197">例</span><span class="sxs-lookup"><span data-stu-id="27f57-197">Example</span></span>  
 <span data-ttu-id="27f57-198">次の例では、RFC、SAP システムから Z_RFC_MKD_DIV を受信します。</span><span class="sxs-lookup"><span data-stu-id="27f57-198">The following example receives an RFC, Z_RFC_MKD_DIV from the SAP system.</span></span> <span data-ttu-id="27f57-199">この RFC では、2 つの数値を除算します。</span><span class="sxs-lookup"><span data-stu-id="27f57-199">This RFC divides two numbers.</span></span> <span data-ttu-id="27f57-200">この例では実装を使用して、 **InboundActionCollection** Z_RFC_MKD_DIV 操作とは、次のメッセージが受信したときにフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="27f57-200">The implementation in this example uses an **InboundActionCollection** to filter for the Z_RFC_MKD_DIV operation and does the following when a message is received:</span></span>  
  
-   <span data-ttu-id="27f57-201">除数がゼロ以外の場合は、除算の結果をコンソールに出力し、SAP システムを返します。</span><span class="sxs-lookup"><span data-stu-id="27f57-201">If the divisor is non-zero, it writes the result of the division to the console and returns it to the SAP system.</span></span>  
  
-   <span data-ttu-id="27f57-202">除数がゼロの場合、結果の例外メッセージをコンソールに出力し、SAP システムにエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="27f57-202">If the divisor is zero, it writes the resulting exception message to the console and returns a fault to the SAP system.</span></span>  
  
-   <span data-ttu-id="27f57-203">SAP システムによって、他の操作を送信する場合は、コンソールにメッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="27f57-203">If any other operation is sent by the SAP system, it writes a message to the console.</span></span> <span data-ttu-id="27f57-204">この場合、アダプター自体は、SAP システムにエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="27f57-204">In this case, the adapter itself returns a fault to the SAP system.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.Runtime.Serialization;  
using System.Xml;  
using System.IO;  
  
// Add WCF, Adapter LOB SDK, and SAP Adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Add this namespace to use Channel Model   
using System.ServiceModel.Channels;  
  
// Include this namespace for Adapter LOB SDK and SAP exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
// This sample demonstrates using the adapter as an rfc server over a channel.  
// The sample implements an RFC, Z_RFC_MKD_DIV that divides two numbers and returns the result  
// 1)  A SAPBinding instance is created and configured (AcceptCredentialsInUri is set true)  
// 2)  A binding parameter collection is created with an InboundAction collection that specifies  
//     target RFC (Z_RFC_MKD_DIV) so that only messages with this action will be received by the  
//     listener (and channel).  
// 3)  An <IReplyChannel> listener is created from the binding and binding parameter collection  
// 4)  A channel is created and opened to receive a request  
// 6)  When Z_RFC_MKD_DIV is received the two parameters are divided and the parameters and result  
//     are written to the console, then the result is returned to the adapter by using a template  
//     message.  
// 7)  If a divide by 0 occurs the exception message is written to the console and a  
//     fault is returned to the SAP system  
// 8)  If any other operation is received an error message is written to the console and the adapter  
///    returns a fault to the SAP system  
// 9)  IMPORTANT you must close the channel and listener to deregister them from the SAP Program ID.  
namespace SapRfcServerCM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Variables to hold the listener and channel  
            IChannelListener<IReplyChannel> listener = null;  
            IReplyChannel channel = null;  
  
            Console.WriteLine("Sample started");  
            Console.WriteLine("Initializing and creating channel listener -- please wait");  
            try  
            {  
  
                // The connection Uri must specify listener parameters (or an R-type destination in saprfc.ini)  
                // and also credentials.  
                Uri listeneraddress =  
                    new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGATEWAY&ListenerGwHost=YourSAPHost&ListenerProgramId=SAPAdapter");  
  
                // Create a binding -- set AcceptCredentialsInUri true  
                SAPBinding binding = new SAPBinding();  
                binding.AcceptCredentialsInUri = true;  
  
                // Create a binding parameter collection with a list of SOAP actions to listen on  
                // in this case: http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV  
                // This ensures that only these actions are received on the channel.  
                InboundActionCollection actions = new InboundActionCollection(listeneraddress);  
                actions.Add("http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_DIV");  
                BindingParameterCollection bpcol = new BindingParameterCollection();  
                bpcol.Add(actions);  
  
                // Pass the Uri and the binding parameter collection (to specify the Z_RFC_MKD_DIV action)  
                listener = binding.BuildChannelListener<IReplyChannel>(listeneraddress, bpcol);  
  
                Console.WriteLine("Opening listener");  
                // Open the listener  
                listener.Open();  
  
                // Get an IReplyChannel  
                channel = listener.AcceptChannel();  
  
                Console.WriteLine("Opening channel");  
                // Open the channel  
                channel.Open();  
  
                Console.WriteLine("\nReady to receive Z_RFC_MKD_DIV RFC");  
  
                try  
                {  
                    // Get the message from the channel  
                    RequestContext rc = channel.ReceiveRequest();  
  
                    // Get the request message sent by SAP  
                    Message reqMessage = rc.RequestMessage;  
  
                    // get the message body  
                    XmlReader reader = reqMessage.GetReaderAtBodyContents();  
  
                    reader.ReadStartElement("Z_RFC_MKD_DIV");  
                    reader.ReadElementString("DEST");  
                    int x_in = int.Parse(reader.ReadElementString("X"));  
                    int y_in = int.Parse(reader.ReadElementString("Y"));  
                    reader.ReadEndElement();  
  
                    Console.WriteLine("\nRfc Received");  
                    Console.WriteLine("X =\t\t" + x_in);  
                    Console.WriteLine("Y =\t\t" + y_in);  
  
                    Message messageOut = null;  
  
                    try   
                    {  
                        int result_out = x_in/y_in;  
  
                        Console.WriteLine("RESULT =\t" + result_out.ToString());  
  
                        string out_xml = "<Z_RFC_MKD_DIVResponse xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\"><RESULT>" + result_out + "</RESULT></Z_RFC_MKD_DIVResponse>";  
                        StringReader sr = new StringReader(out_xml);  
                        reader = XmlReader.Create(sr);  
  
                        // create a response message  
                        // be sure to specify the response action  
                        messageOut = Message.CreateMessage(MessageVersion.Default, reqMessage.Headers.Action + "/response", reader);  
  
                    }  
                    catch (DivideByZeroException ex)  
                    {  
                        Console.WriteLine();  
                        Console.WriteLine(ex.Message + " Returning fault to SAP");  
  
                        // Create a message that contains a fault  
                        // The fault code and message action can be any value  
  
                        messageOut = Message.CreateMessage(MessageVersion.Default, new FaultCode("Fault"), ex.Message, string.Empty);  
                    }  
  
                    // Send the reply  
                    rc.Reply(messageOut);  
  
                    // Close the request context  
                    rc.Close();  
  
                }  
                catch (AdapterException aex)  
                {  
                    // Will get here if the message received was not in the InboundActionCollection  
                    Console.WriteLine();  
                    Console.WriteLine(aex.Message);  
                }  
  
                // Wait for a key to exit  
                Console.WriteLine("\nHit <RETURN> to end");  
                Console.ReadLine();  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the SAP system");  
                Console.WriteLine(cex.InnerException.Message);  
            }  
            catch (TargetSystemException tex)  
            {  
                Console.WriteLine("Exception occurred on the SAP system");  
                Console.WriteLine(tex.InnerException.Message);  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
            }  
            finally  
            {  
                // IMPORTANT: close the channel and listener to stop listening on the Program ID  
                if (channel != null)  
                {  
                    if (channel.State == CommunicationState.Opened)  
                        channel.Close();  
                    else  
                        channel.Abort();  
                }  
  
                if (listener != null)  
                {  
                    if (listener.State == CommunicationState.Opened)  
                        listener.Close();  
                    else  
                        listener.Abort();  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="27f57-205">参照</span><span class="sxs-lookup"><span data-stu-id="27f57-205">See Also</span></span>  
[<span data-ttu-id="27f57-206">WCF チャネル モデルを使用してアプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="27f57-206">Develop applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)