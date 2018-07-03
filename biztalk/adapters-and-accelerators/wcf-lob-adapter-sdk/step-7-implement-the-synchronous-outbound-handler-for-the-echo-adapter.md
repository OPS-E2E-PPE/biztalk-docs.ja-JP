---
title: '手順 7: エコー アダプターの同期送信ハンドラーを実装する |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4da4d987-03c4-4817-850b-4c5ca2ba7e62
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e44c26c1708f54cceeb979cf20e5c43a95528a54
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979467"
---
# <a name="step-7-implement-the-synchronous-outbound-handler-for-the-echo-adapter"></a><span data-ttu-id="cd5db-102">手順 7: エコー アダプターの同期送信ハンドラーを実装する.</span><span class="sxs-lookup"><span data-stu-id="cd5db-102">Step 7: Implement the Synchronous Outbound Handler for the Echo Adapter</span></span>
<span data-ttu-id="cd5db-103">![手順 9 の 7](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-7of9.gif "Step_7of9")</span><span class="sxs-lookup"><span data-stu-id="cd5db-103">![Step 7 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-7of9.gif "Step_7of9")</span></span>  
  
 <span data-ttu-id="cd5db-104">**所要時間:** 30 分</span><span class="sxs-lookup"><span data-stu-id="cd5db-104">**Time to complete:** 30 minutes</span></span>  
  
 <span data-ttu-id="cd5db-105">この手順では、エコー アダプターの送信同期の機能を実装します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-105">In this step, you implement the synchronous outbound capability of the Echo adapter.</span></span> <span data-ttu-id="cd5db-106">に従って、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、同期の送信機能をサポートするために実装する必要があります、`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="cd5db-106">According to the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], to support the synchronous outbound capability, you must implement the `Microsoft.ServiceModel.Channels.Common.IOutboundHandler` interface.</span></span> <span data-ttu-id="cd5db-107">エコー アダプターの場合、 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] EchoAdapterOutboundHandler と呼ばれる 1 つの派生クラスが自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="cd5db-107">For the Echo adapter, the [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] automatically generates one derived class called EchoAdapterOutboundHandler.</span></span>  
  
 <span data-ttu-id="cd5db-108">実装する方法の理解を深めるために、EchoAdapterOutboundHandler クラスを更新する次のセクションで、`Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A`着信 WCF 要求メッセージを解析する方法、および応答の送信 WCF メッセージを生成する方法。</span><span class="sxs-lookup"><span data-stu-id="cd5db-108">In the following sections, you update the EchoAdapterOutboundHandler class to get a better understanding of how to implement the `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A`, how to parse the incoming WCF request message, and how to generate outgoing WCF response messages.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cd5db-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="cd5db-109">Prerequisites</span></span>  
 <span data-ttu-id="cd5db-110">この手順を開始する前にする必要がありますが正常に完了して[手順 6: エコー アダプターのメタデータ解決ハンドラーを実装する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-110">Before you begin this step, you must have successfully completed [Step 6: Implement the Metadata Resolve Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md).</span></span> <span data-ttu-id="cd5db-111">基本的な知識`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`も便利です。</span><span class="sxs-lookup"><span data-stu-id="cd5db-111">A basic familiarity with `Microsoft.ServiceModel.Channels.Common.IOutboundHandler` is also helpful.</span></span>  
  
## <a name="the-ioutboundhandler-interface"></a><span data-ttu-id="cd5db-112">IOutboundHandler インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cd5db-112">The IOutboundHandler Interface</span></span>  
 <span data-ttu-id="cd5db-113">`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`として定義されます。</span><span class="sxs-lookup"><span data-stu-id="cd5db-113">The `Microsoft.ServiceModel.Channels.Common.IOutboundHandler` is defined as:</span></span>  
  
```  
public interface IOutboundHandler : IConnectionHandler, IDisposable  
{  
    Message Execute(Message message, TimeSpan timeout);  
}  
```  
  
 <span data-ttu-id="cd5db-114">`Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A`メソッドは、ターゲット システムに対応するメソッドを呼び出すことによって、着信 WCF 要求メッセージを実行し、送信 WCF 応答メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-114">The `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A` method executes the incoming WCF request message by invoking the corresponding method on the target system and then returns an outgoing WCF response message.</span></span> <span data-ttu-id="cd5db-115">そのパラメーターの定義は、次の表のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cd5db-115">The definitions of its parameters are listed in the following table:</span></span>  
  
|<span data-ttu-id="cd5db-116">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="cd5db-116">**Parameter**</span></span>|<span data-ttu-id="cd5db-117">**定義**</span><span class="sxs-lookup"><span data-stu-id="cd5db-117">**Definition**</span></span>|  
|-------------------|--------------------|  
|<span data-ttu-id="cd5db-118">message</span><span class="sxs-lookup"><span data-stu-id="cd5db-118">message</span></span>|<span data-ttu-id="cd5db-119">受信 WCF 要求メッセージ。</span><span class="sxs-lookup"><span data-stu-id="cd5db-119">Incoming WCF request message.</span></span>|  
|<span data-ttu-id="cd5db-120">timeout</span><span class="sxs-lookup"><span data-stu-id="cd5db-120">timeout</span></span>|<span data-ttu-id="cd5db-121">時間間隔が、この操作を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd5db-121">Time interval within which this operation should be completed.</span></span> <span data-ttu-id="cd5db-122">操作をスローする必要があります、`System.TimeoutException`操作を完了する前に、指定したタイムアウト時間を超過した場合。</span><span class="sxs-lookup"><span data-stu-id="cd5db-122">The operation should throw a `System.TimeoutException` if the specified timeout is exceeded before the operation is completed.</span></span>|  
  
 <span data-ttu-id="cd5db-123">アダプターは、一方向の送信 (アダプターで期待される応答メッセージはありません) を実行する場合は、このメソッドは null を返します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-123">If your adapter is performing a one-way send (there is no response message expected by your adapter), this method should return null.</span></span> <span data-ttu-id="cd5db-124">アダプターがによる双方向の操作を実行する場合`Microsoft.ServiceModel.Channels.Common.OperationResult`等しく`Microsoft.ServiceModel.Channels.Common.OperationResult.Empty%2A`、このメソッドは、空の本文で WCF 応答メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-124">If your adapter is performing a two-way operation with `Microsoft.ServiceModel.Channels.Common.OperationResult` equal to `Microsoft.ServiceModel.Channels.Common.OperationResult.Empty%2A`, this method returns a WCF response message with an empty body.</span></span> <span data-ttu-id="cd5db-125">内の値を格納している本文を使用して WCF 応答メッセージを返す必要がありますそれ以外の場合、`Microsoft.ServiceModel.Channels.Common.OperationResult`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="cd5db-125">Otherwise, it should return the WCF response message with a body that contains the values in the `Microsoft.ServiceModel.Channels.Common.OperationResult` object.</span></span> <span data-ttu-id="cd5db-126">応答アクションの文字列を構築するには使用`Microsoft.ServiceModel.Channels.Common.OperationMetadata.OutputMessageAction%2A`します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-126">To construct the response action string, use `Microsoft.ServiceModel.Channels.Common.OperationMetadata.OutputMessageAction%2A`.</span></span>  
  
## <a name="echo-adapter-synchronous-outbound"></a><span data-ttu-id="cd5db-127">エコー アダプターの同期送信</span><span class="sxs-lookup"><span data-stu-id="cd5db-127">Echo Adapter Synchronous Outbound</span></span>  
 <span data-ttu-id="cd5db-128">によって、ターゲット システムの操作を実装する方法はたくさんあります、`Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A`メソッド。</span><span class="sxs-lookup"><span data-stu-id="cd5db-128">Depending on your target system's operations, there are many ways to implement the `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A` method.</span></span> <span data-ttu-id="cd5db-129">エコー アダプターの 3 つの送信操作があるし、割り当てられているノードの Id と表示名。</span><span class="sxs-lookup"><span data-stu-id="cd5db-129">For the Echo adapter, there are three outbound operations, and their assigned node IDs and display names are:</span></span>  
  
- <span data-ttu-id="cd5db-130">string EchoStrings (文字列データ)、ノード ID エコー/EchoString、表示名を = = EchoString</span><span class="sxs-lookup"><span data-stu-id="cd5db-130">string[] EchoStrings(string data), node ID = Echo/EchoString, display name=EchoString</span></span>  
  
- <span data-ttu-id="cd5db-131">EchoGreetings(Greeting greeting)、ノード ID を案内エコー/EchoGreetings、表示名を = = EchoGreetings</span><span class="sxs-lookup"><span data-stu-id="cd5db-131">Greeting[] EchoGreetings(Greeting greeting), node ID=Echo/EchoGreetings, display name=EchoGreetings</span></span>  
  
- <span data-ttu-id="cd5db-132">CustomGreeting EchoCustomGreetingFromFile(Uri greetingInstancePath)、nodeID エコー/EchoCustomGreetingFromFile、表示名を = = EchoGreetings</span><span class="sxs-lookup"><span data-stu-id="cd5db-132">CustomGreeting EchoCustomGreetingFromFile(Uri greetingInstancePath), nodeID=Echo/EchoCustomGreetingFromFile, display name=EchoGreetings</span></span>  
  
  <span data-ttu-id="cd5db-133">正しく着信 WCF 要求メッセージを解析し、送信する WCF 応答メッセージを生成、によって使用される SOAP メッセージ内で、次の要素を理解しておく必要がありますあります、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="cd5db-133">To correctly parse the incoming WCF request message and generate the outgoing WCF response message, you must be familiar with the following elements within the SOAP message used by the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]:</span></span>  
  
  <span data-ttu-id="cd5db-134">受信 WCF 要求メッセージ。</span><span class="sxs-lookup"><span data-stu-id="cd5db-134">For the incoming WCF request message:</span></span>  
  
- <span data-ttu-id="cd5db-135">WCF メッセージのアクションの入力操作のノード ID を =</span><span class="sxs-lookup"><span data-stu-id="cd5db-135">The WCF input message action = operation's node ID</span></span>  
  
- <span data-ttu-id="cd5db-136">着信メッセージの本文 = 開始本文の要素が\<displayname\>\<パラメーター名\>{データ}\</parameter 名前\>\</displayname\></span><span class="sxs-lookup"><span data-stu-id="cd5db-136">Incoming message body = The start element of the body is \<displayname\>\<parameter name\>{data}\</parameter name\>\</displayname\></span></span>  
  
  <span data-ttu-id="cd5db-137">送信 WCF 応答メッセージ。</span><span class="sxs-lookup"><span data-stu-id="cd5db-137">For the outgoing WCF response message:</span></span>  
  
- <span data-ttu-id="cd5db-138">WCF メッセージのアクションの出力操作のノード ID を = +"/応答"</span><span class="sxs-lookup"><span data-stu-id="cd5db-138">The WCF output message action = operation's node ID + "/response"</span></span>  
  
- <span data-ttu-id="cd5db-139">メッセージ本文を送信 = 開始本文の要素が\<displayname +"Response"\>、その後に\<displayname +「結果」\>、後に、 \<datatype\>データ\</datatype\>\</displayname+"結果\>\</displayname +"Response"\></span><span class="sxs-lookup"><span data-stu-id="cd5db-139">Outgoing message body = The start element of the body is \<displayname + "Response"\>, followed by \<displayname + "Result"\>, and followed by the \<datatype\>data\</datatype\>\</displayname+"Result\>\</displayname + "Response"\></span></span>  
  
  <span data-ttu-id="cd5db-140">操作など、 **string[] EchoStrings (文字列データ)**、ノード ID と表示名をエコー/EchoStrings を = = EchoStrings:</span><span class="sxs-lookup"><span data-stu-id="cd5db-140">For example, operation **string[] EchoStrings(string data)**, node ID = Echo/EchoStrings, and display name= EchoStrings:</span></span>  
  
  <span data-ttu-id="cd5db-141">WCF メッセージのアクションの入力 ="エコー/EchoStrings";パラメーター名があるため、入力本文は次のように、`data`します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-141">The WCF input message action = "Echo/EchoStrings"; and the input body looks as follows, since the parameter name is `data`.</span></span>  
  
```  
<EchoStrings>  
<data>{data}  
</data>  
</EchoStrings>  
```  
  
 <span data-ttu-id="cd5db-142">WCF メッセージのアクションの出力 =「エコー/EchoStrings/応答」;データ型があるため、出力本文は次のように、**文字列**します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-142">The WCF output message action = "Echo/EchoStrings/response"; and the output body looks as follows, since the data type is **string**.</span></span>  
  
```  
<EchoStringsResponse>  
<EchoStringsResult>  
<string>{data}</string>  
</EchoStringsResult>  
</EchoStringsResponse>  
```  
  
 <span data-ttu-id="cd5db-143">着信 WCF 要求メッセージを解析するときに使用できます、 `System.Xml.XmlDictionaryReader` WCF 応答メッセージを作成するときは、WCF メッセージ内のコンテンツを取得、使用することができます、`System.Xml.XmlWriter`するようにします。</span><span class="sxs-lookup"><span data-stu-id="cd5db-143">When parsing the incoming WCF request message, you can use the `System.Xml.XmlDictionaryReader` to retrieve content within the WCF message; when composing the WCF response message, you can use the `System.Xml.XmlWriter` to do so.</span></span>  
  
## <a name="implementing-the-ioutboundhandler"></a><span data-ttu-id="cd5db-144">IOutboundHandler を実装します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-144">Implementing the IOutboundHandler</span></span>  
 <span data-ttu-id="cd5db-145">Execute メソッドを実装する、`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-145">You implement the Execute method of the `Microsoft.ServiceModel.Channels.Common.IOutboundHandler`.</span></span> <span data-ttu-id="cd5db-146">最初に、取得、`Microsoft.ServiceModel.Channels.Common.OperationMetadata`オブジェクトに基づく入力メッセージのアクション。</span><span class="sxs-lookup"><span data-stu-id="cd5db-146">First, gets a `Microsoft.ServiceModel.Channels.Common.OperationMetadata` object based on the input message action.</span></span> <span data-ttu-id="cd5db-147">受信 WCF メッセージを解析し、操作のたびに基に、関連付けられている echo 機能を実行します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-147">Then, parses the incoming WCF message and executes the associated echo functionality based on each operation.</span></span> <span data-ttu-id="cd5db-148">最後に、送信メッセージの本文の形式を使用して、送信 WCF 応答メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-148">Finally, creates an outgoing WCF response message by using the format of outgoing message body.</span></span>  
  
#### <a name="to-implement-the-execute-method-of-the-echoadapteroutboundhandler-class"></a><span data-ttu-id="cd5db-149">EchoAdapterOutboundHandler クラスの Execute メソッドを実装するには</span><span class="sxs-lookup"><span data-stu-id="cd5db-149">To implement the Execute method of the EchoAdapterOutboundHandler class</span></span>  
  
1.  <span data-ttu-id="cd5db-150">ソリューション エクスプ ローラーで、 **EchoAdapterOutboundHandler.cs**ファイル。</span><span class="sxs-lookup"><span data-stu-id="cd5db-150">In Solution Explorer, double-click the **EchoAdapterOutboundHandler.cs** file.</span></span>  
  
2.  <span data-ttu-id="cd5db-151">Visual Studio エディターで次の 2 つの追加のディレクティブを使用して既存のセットにディレクティブを使用します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-151">In the Visual Studio editor, add the following two using directives to the existing set of using directives.</span></span>  
  
    ```csharp  
    using System.Xml;  
    using System.IO;  
    ```  
  
3.  <span data-ttu-id="cd5db-152">内で、 **Execute**メソッドを次に、既存のロジックを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="cd5db-152">Inside the **Execute** method, replace the existing logic with the following:</span></span>  
  
    1.  <span data-ttu-id="cd5db-153">このロジックは、要求された操作を確認します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-153">This logic verifies the requested operation.</span></span>  
  
    2.  <span data-ttu-id="cd5db-154">取得、`Microsoft.ServiceModel.Channels.Common.OperationMetadata`オブジェクトに基づく入力メッセージの SOAP アクション。</span><span class="sxs-lookup"><span data-stu-id="cd5db-154">It gets the `Microsoft.ServiceModel.Channels.Common.OperationMetadata` object based on the SOAP input message action.</span></span>  
  
    3.  <span data-ttu-id="cd5db-155">アクションの種類に基づき、WCF 要求メッセージを解析し、適切な操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-155">Based on the action type, it parses the WCF request message and invokes the appropriate operation.</span></span>  
  
    ```csharp  
    // Trace input message  
    EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Verbose, "http://Microsoft.Adapters.Samples.Sql/TraceCode/InputWcfMessage", "Input WCF Message", this, new MessageTraceRecord(message));  
    // Timeout is not supported in this sample  
    OperationMetadata om = this.MetadataLookup.GetOperationDefinitionFromInputMessageAction(message.Headers.Action, timeout);  
    if (om == null)  
    {  
        throw new AdapterException("Invalid operation metadata for " + message.Headers.Action);  
    }  
    if (timeout.Equals(TimeSpan.Zero))  
    {  
        throw new AdapterException("time out is zero");  
    }  
  
    switch (message.Headers.Action)  
    {  
        case "Echo/EchoStrings":  
            return ExecuteEchoStrings(om as ParameterizedOperationMetadata, message, timeout);  
  
        case "Echo/EchoGreetings":  
            return ExecuteEchoGreetings(om as ParameterizedOperationMetadata, message, timeout);  
  
        case "Echo/EchoCustomGreetingFromFile":  
            return ExecuteEchoCustomGreetingFromFile(om, message, timeout);  
    }  
    return null;              
    ```  
  
4.  <span data-ttu-id="cd5db-156">ここで追加、 **ExecuteEchoStrings** string[] EchoStrings (文字列データ) の操作を処理するメソッド。</span><span class="sxs-lookup"><span data-stu-id="cd5db-156">Now add the **ExecuteEchoStrings** method to handle the string[] EchoStrings(string data) operation.</span></span> <span data-ttu-id="cd5db-157">このヘルパー関数は、WCF 要求メッセージ、echoInUpperCase URI 要素が設定されているかどうかにチェックを読み取りを true にそうである場合は、入力文字列を count 変数が示すとおりの回数だけに大文字に変換します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-157">This helper function reads the WCF request message, checks to see if the echoInUpperCase URI element is set to true; if so, it converts the input string to upper case as many times as the count variable indicates.</span></span> <span data-ttu-id="cd5db-158">次に、WCF 応答メッセージの形式で生成: \<EchoStringsResponse\>\<EchoStringResult\>\<文字列\>{データ}\</string\> \</EchoStringResult\>\</EchoStringsResponse\>します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-158">Then, it generates the WCF response message in the format of: \<EchoStringsResponse\>\<EchoStringResult\>\<string\>{data}\</string\>\</EchoStringResult\>\</EchoStringsResponse\>.</span></span>  
  
    ```csharp  
    private Message ExecuteEchoStrings(ParameterizedOperationMetadata om, Message message, TimeSpan timeout)  
    {  
        // ** Read the WCF request  
        // ** <EchoStrings><name>{text}</name></EchoStrings>  
        XmlDictionaryReader inputReader = message.GetReaderAtBodyContents();  
        while (inputReader.Read())  
        {  
            if ((String.IsNullOrEmpty(inputReader.Prefix) && inputReader.Name.Equals("data"))  
                || inputReader.Name.Equals(inputReader.Prefix + ":" + "data")) break;  
        }  
        inputReader.Read();  
        // if the connection property "echoInUpperCase" is set to true, it echoes the data in upper case  
        bool echoInUpperCase = this.Connection.ConnectionFactory.ConnectionUri.EchoInUpperCase;  
        string inputValue = echoInUpperCase ? inputReader.Value.ToUpper() : inputReader.Value;  
        int arrayCount = this.Connection.ConnectionFactory.Adapter.Count;  
  
        // ** Generate the WCF response  
        // ** <EchoStringsResponse><EchoStringResult>{Name}</EchoStringResult></EchoStringsResponse >  
        StringBuilder outputString = new StringBuilder();  
        XmlWriterSettings settings = new XmlWriterSettings();  
        settings.OmitXmlDeclaration = true;  
        XmlWriter replywriter = XmlWriter.Create(outputString, settings);  
        replywriter.WriteStartElement(om.DisplayName + "Response", EchoAdapter.SERVICENAMESPACE);  
        replywriter.WriteStartElement(om.DisplayName + "Result", EchoAdapter.SERVICENAMESPACE);  
        if (om.OperationResult.IsArray)  
        {  
            for (int count = 0; count < arrayCount; count++)  
            {  
                replywriter.WriteElementString("string", "http://schemas.microsoft.com/2003/10/Serialization/Arrays", inputValue);  
            }  
        }  
        replywriter.WriteEndElement();  
        replywriter.WriteEndElement();  
        replywriter.Close();  
        XmlReader replyReader = XmlReader.Create(new StringReader(outputString.ToString()));  
        return Message.CreateMessage(message.Version, om.OutputMessageAction, replyReader);  
    }  
    ```  
  
5.  <span data-ttu-id="cd5db-159">追加することで引き続き、 **ExecuteEchoGreetings** EchoGreetings 操作を処理するメソッド。</span><span class="sxs-lookup"><span data-stu-id="cd5db-159">Continue by adding the **ExecuteEchoGreetings** method to handle the EchoGreetings operation.</span></span> <span data-ttu-id="cd5db-160">このヘルパー関数は、WCF 要求メッセージを読み取り、操作とした型の解決、`ResolveOperationMetadata`と`ResolveTypeMetadata`のメソッド、`Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler`インターフェイス、し、次の形式を使用して WCF 応答メッセージを生成: \<EchoGreetingsResponse\>\<EchoGreetingsResult\>... メッセージ.\</EchoGreetingsResult\>\</EchoGreetingsResponse\>します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-160">This helper function reads the WCF request message, resolves operation and type by the `ResolveOperationMetadata` and `ResolveTypeMetadata` methods of the `Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler` interface, and then generates the WCF response message using the format of: \<EchoGreetingsResponse\>\<EchoGreetingsResult\>…message…\</EchoGreetingsResult\>\</EchoGreetingsResponse\>.</span></span>  
  
    ```csharp  
    private Message ExecuteEchoGreetings(ParameterizedOperationMetadata om, Message message, TimeSpan timeout)  
    {  
        // NOTE this method doesn't return response in upper case based on   
        // connection property echoInUpperCase  
  
        // ** Read the WCF request  
        String inputValue = String.Empty;  
        using (XmlDictionaryReader inputReader = message.GetReaderAtBodyContents())  
        {  
  
            bool foundGreeting = inputReader.ReadToDescendant("greeting");  
            if (foundGreeting)  
            {  
                inputValue = inputReader.ReadInnerXml();  
            }  
        }  
  
        int arrayCount = this.Connection.ConnectionFactory.Adapter.Count;  
  
        // ** Generate the WCF response  
        StringBuilder outputString = new StringBuilder();  
        XmlWriterSettings settings = new XmlWriterSettings();  
        settings.OmitXmlDeclaration = true;  
        XmlWriter replywriter = XmlWriter.Create(outputString, settings);  
        replywriter.WriteStartElement(om.DisplayName + "Response", EchoAdapter.SERVICENAMESPACE);  
        replywriter.WriteStartElement(om.DisplayName + "Result", EchoAdapter.SERVICENAMESPACE);  
        for(int i = 0; i < arrayCount; i++ )  
        {  
            ComplexQualifiedType cqtResult = om.OperationResult.QualifiedType as ComplexQualifiedType;  
            StructuredTypeMetadata tmResult = MetadataLookup.GetTypeDefinition(cqtResult.TypeId, timeout) as StructuredTypeMetadata;  
            replywriter.WriteStartElement(tmResult.TypeName, tmResult.TypeNamespace);  
            replywriter.WriteRaw(inputValue);  
            replywriter.WriteEndElement();  
        }  
        replywriter.WriteEndElement();  
        replywriter.WriteEndElement();  
        replywriter.Close();  
        XmlReader replyReader = XmlReader.Create(new StringReader(outputString.ToString()));  
        return Message.CreateMessage(message.Version, om.OutputMessageAction, replyReader);  
    }  
    ```  
  
6.  <span data-ttu-id="cd5db-161">ここで追加、 **ExecuteEchoCustomGreetingFromFile** EchoCustomGreetingFromFile 操作を処理するメソッド。</span><span class="sxs-lookup"><span data-stu-id="cd5db-161">Now add the **ExecuteEchoCustomGreetingFromFile** method to handle the EchoCustomGreetingFromFile operation.</span></span> <span data-ttu-id="cd5db-162">指定したファイルからメッセージを読み取るこのヘルパー関数は、WCF 要求メッセージを読み取るし、次の形式を使用して WCF 応答メッセージを生成: \<EchoGreetingsFromFileResponse\> \<EchoGreetingsFromFileResult\>... メッセージ.\</EchoGreetingsFromFileResult\>\</EchoGreetingsFromFileResponse\>します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-162">This helper function reads the WCF request message, reads the message from the specified file, and then generates the  WCF response message using the format of: \<EchoGreetingsFromFileResponse\>\<EchoGreetingsFromFileResult\>…message…\</EchoGreetingsFromFileResult\>\</EchoGreetingsFromFileResponse\>.</span></span>  
  
    ```csharp  
    private Message ExecuteEchoCustomGreetingFromFile(OperationMetadata om, Message message, TimeSpan timeout)  
    {  
        // NOTE this method doesn't return response in upper case based on   
        // connection property echoInUpperCase  
  
        // ** Read the WCF request  
        Uri path;  
        using (XmlDictionaryReader inputReader = message.GetReaderAtBodyContents())  
        {  
            inputReader.MoveToContent();  
            inputReader.ReadStartElement(om.DisplayName);  
            inputReader.MoveToContent();  
            // The path contains the location of the XML file that contains the instance of Greeting object to read   
            path = new Uri(inputReader.ReadElementContentAsString());  
            inputReader.ReadEndElement();  
        }  
  
        // ** Generate the WCF response  
        StringBuilder outputString = new StringBuilder();  
        XmlWriterSettings settings = new XmlWriterSettings();  
        settings.OmitXmlDeclaration = true;  
        XmlWriter replywriter = XmlWriter.Create(outputString, settings);  
        replywriter.WriteStartElement(om.DisplayName + "Response", EchoAdapter.SERVICENAMESPACE);  
        replywriter.WriteStartElement(om.DisplayName + "Result", EchoAdapter.SERVICENAMESPACE);  
        // Read the XML file and set it to the reply writer here  
        FileStream stream = new FileStream(path.AbsolutePath, FileMode.Open);  
        XmlDictionaryReader xdr = XmlDictionaryReader.CreateTextReader(stream, new XmlDictionaryReaderQuotas());  
        xdr.MoveToContent();  
        string rawGreeting = xdr.ReadInnerXml();  
        replywriter.WriteRaw(rawGreeting);  
        replywriter.WriteEndElement();  
        replywriter.WriteEndElement();  
        replywriter.Close();  
        XmlReader replyReader = XmlReader.Create(new StringReader(outputString.ToString()));  
        return Message.CreateMessage(message.Version, om.OutputMessageAction, replyReader);  
    }  
    ```  
  
7.  <span data-ttu-id="cd5db-163">Visual Studio での**ファイル** メニューのをクリックして**すべて保存**します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-163">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
8.  <span data-ttu-id="cd5db-164">**[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd5db-164">On the **Build** menu, click **Build Solution**.</span></span> <span data-ttu-id="cd5db-165">これは、エラーなしでコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd5db-165">It should compile without errors.</span></span> <span data-ttu-id="cd5db-166">そうでない場合は、上記のすべての手順に従っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-166">If not, ensure that you have followed every step above.</span></span> <span data-ttu-id="cd5db-167">ここで、安全に Visual Studio を終了したりに進んでください[手順 8: エコー アダプターの同期受信ハンドラーを実装する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-167">Now, you can safely close Visual Studio or continue on to [Step 8: Implement the Synchronous Inbound Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md).</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="cd5db-168">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="cd5db-168">What Did I Just Do?</span></span>  
 <span data-ttu-id="cd5db-169">この手順では、エコー アダプターの同期送信メッセージング機能を実装する方法について説明しました。</span><span class="sxs-lookup"><span data-stu-id="cd5db-169">In this step, you learned how to implement the synchronous outbound messaging functionality of the Echo adapter.</span></span> <span data-ttu-id="cd5db-170">実装してこれを行うには`Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A`のメソッド、`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-170">To do so, you implemented the `Microsoft.ServiceModel.Channels.Common.IOutboundHandler.Execute%2A` method of the `Microsoft.ServiceModel.Channels.Common.IOutboundHandler`.</span></span> <span data-ttu-id="cd5db-171">このメソッドは、着信 WCF 要求メッセージを解析、必要なアクションを実行し送信する WCF 応答メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-171">This method parsed the incoming WCF request message, performed the necessary actions, and then generated the outgoing WCF response message.</span></span>  
  
 <span data-ttu-id="cd5db-172">WCF を使用して、着信 WCF 要求メッセージの具体的には、`System.ServiceModel.Channels.Message.Headers.Action%2A`をさらに受信したメッセージの本文の基本的な構造を理解することによって入力メッセージのアクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-172">Specifically, for the incoming WCF request message, you used WCF `System.ServiceModel.Channels.Message.Headers.Action%2A` to retrieve the input message action by further understanding the basic structure of the incoming message body.</span></span> <span data-ttu-id="cd5db-173">使用して、送信する WCF 応答メッセージの`Microsoft.ServiceModel.Channels.Common.OperationMetadata.OutputMessageAction%2A`をさらに、送信メッセージの本文の基本的な構造を理解することにより、出力メッセージのアクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-173">For the outgoing WCF response message, you used `Microsoft.ServiceModel.Channels.Common.OperationMetadata.OutputMessageAction%2A` to retrieve the output message action by further understanding the basic structure of the outgoing message body.</span></span> <span data-ttu-id="cd5db-174">使用して解析し、WCF メッセージを作成する、`System.Xml.XmlDictionaryReader`に着信 WCF 要求メッセージを読み取って、使用`System.Xml.XmlWriter`送信 WCF 応答メッセージを記述します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-174">When parsing and composing WCF messages, you used `System.Xml.XmlDictionaryReader` to read the incoming WCF request message and used `System.Xml.XmlWriter` to write an outgoing WCF response message.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="cd5db-175">次の手順</span><span class="sxs-lookup"><span data-stu-id="cd5db-175">Next Steps</span></span>  
<span data-ttu-id="cd5db-176">ビルドしてエコー アダプターを展開します。</span><span class="sxs-lookup"><span data-stu-id="cd5db-176">Build and deploy the Echo adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd5db-177">参照</span><span class="sxs-lookup"><span data-stu-id="cd5db-177">See Also</span></span>  
 <span data-ttu-id="cd5db-178">[手順 6: エコー アダプターのメタデータ解決ハンドラーを実装します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="cd5db-178">[Step 6: Implement the Metadata Resolve Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="cd5db-179">手順 8: エコー アダプターの同期受信ハンドラーを実装する</span><span class="sxs-lookup"><span data-stu-id="cd5db-179">Step 8: Implement the Synchronous Inbound Handler for the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md)