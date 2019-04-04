---
title: WCF チャネル モデルを使用して Oracle データベースに対する操作を呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- invoking operations, using the WCF channel model
- WCF channel model, invoking operations
- invoking operations
- operations, invoking
ms.assetid: 6dd95c18-8f78-46d0-8845-b74890614c33
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1ff19d925ac8892fdaed62204f4da742d1e86ef
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007419"
---
# <a name="invoke-operations-on-the-oracle-database-using-the-wcf-channel-model"></a><span data-ttu-id="12ae7-102">WCF チャネル モデルを使用して Oracle データベースに対する操作を呼び出す</span><span class="sxs-lookup"><span data-stu-id="12ae7-102">Invoke Operations on the Oracle Database Using the WCF Channel Model</span></span>
<span data-ttu-id="12ae7-103">操作を呼び出すことができます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を使用して、 **IRequestChannel**または**IOutputChannel**図形をアダプターにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-103">You can invoke operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] by using an **IRequestChannel** or **IOutputChannel** shape to send messages to the adapter.</span></span> <span data-ttu-id="12ae7-104">基本的なパターンが、バインドを使用して、必要なチャネル形状をチャネル ファクトリを作成するには (**OracleDBBinding**) と接続 URI から作成されたエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="12ae7-104">The basic pattern is to create a channel factory for the required channel shape by using a binding (**OracleDBBinding**) and an endpoint created from a connection URI.</span></span> <span data-ttu-id="12ae7-105">作成し、**メッセージ**対象の操作のメッセージ スキーマに準拠した SOAP メッセージを表すインスタンス。</span><span class="sxs-lookup"><span data-stu-id="12ae7-105">You then create a **Message** instance that represents a SOAP message that conforms to the message schema for your target operation.</span></span> <span data-ttu-id="12ae7-106">これを送信することができますし、**メッセージ**を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]チャネル ファクトリから作成されたチャネルを使用しています。</span><span class="sxs-lookup"><span data-stu-id="12ae7-106">You can then send this **Message** to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] by using a channel created from the channel factory.</span></span> <span data-ttu-id="12ae7-107">使用する場合、 **IRequestChannel**応答が届きます。</span><span class="sxs-lookup"><span data-stu-id="12ae7-107">If you are using an **IRequestChannel**, you receive a response.</span></span> <span data-ttu-id="12ae7-108">Oracle データベースに対する操作の実行に問題がある場合、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]スロー、 **Microsoft.ServiceModel.Channels.Common.TargetSystemException**します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-108">If there is a problem executing the operation on the Oracle database, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] throws a **Microsoft.ServiceModel.Channels.Common.TargetSystemException**.</span></span>  
  
 <span data-ttu-id="12ae7-109">使用して操作を送信する方法の概要については、 **IRequestChannel** WCF を参照してください「クライアント チャネル レベルのプログラミング」 [ http://go.microsoft.com/fwlink/?LinkId=106081](http://go.microsoft.com/fwlink/?LinkId=106081)します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-109">For an overview of how to send operations using an **IRequestChannel** in WCF, see "Client Channel-Level Programming" at [http://go.microsoft.com/fwlink/?LinkId=106081](http://go.microsoft.com/fwlink/?LinkId=106081).</span></span>  
  
 <span data-ttu-id="12ae7-110">このトピックのセクションでは、操作を呼び出してするのに役立つ情報を提供する、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF チャネル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-110">The sections in this topic provide information to help you invoke operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] using the WCF channel model.</span></span>  
  
## <a name="creating-and-consuming-messages-for-outbound-operations"></a><span data-ttu-id="12ae7-111">作成および送信操作のメッセージを使用します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-111">Creating and Consuming Messages for Outbound Operations</span></span>  
 <span data-ttu-id="12ae7-112">に対して操作を呼び出す、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、いずれかを使用して対象の操作の要求メッセージを送信する、 **IRequestChannel**または**IOutputChannel**します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-112">To invoke an operation on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], you send the request message for the target operation using either an **IRequestChannel** or an **IOutputChannel**.</span></span> <span data-ttu-id="12ae7-113">使用する場合、 **IRequestChannel**アダプターは、応答メッセージで、操作の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-113">If you use an **IRequestChannel** the adapter returns the results of the operation in the response message.</span></span>  
  
 <span data-ttu-id="12ae7-114">詳細については、要求および応答メッセージ スキーマと、各操作のメッセージ アクションを参照してください。[メッセージとメッセージ スキーマの BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-114">For more detailed information about the request and response message schemas and the message actions for each operation, see [Messages and Message Schemas for BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).</span></span>  
  
 <span data-ttu-id="12ae7-115">要求メッセージを作成し、応答メッセージを使用する方法は、ストリーミングは、ノードまたはノード値のストリーミングがアダプターによって実行されるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-115">How you create the request message and consume the response message determines whether node streaming or node-value streaming is performed by the adapter.</span></span> <span data-ttu-id="12ae7-116">これは、さらに、サポートされている操作のエンド ツー エンドの LOB データのストリーミングを実行するかどうか判断します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-116">This in turn determines whether end-to-end streaming of LOB data is performed for supported operations.</span></span>  
  
### <a name="creating-the-request-message"></a><span data-ttu-id="12ae7-117">要求メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-117">Creating the request message</span></span>  
 <span data-ttu-id="12ae7-118">2 つの方法では、要求メッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="12ae7-118">You can create the request message in one of two ways:</span></span>  
  
- <span data-ttu-id="12ae7-119">ノード値に使用できるメッセージを作成するストリーミングを渡す必要がありますでメッセージ本文、 **XmlBodyWriter**ノード値のストリーミングを実装します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-119">To create a message that can be used for node-value streaming you must pass the message body in an **XmlBodyWriter** that implements node-value streaming.</span></span>  
  
- <span data-ttu-id="12ae7-120">ノードの使用できるメッセージを作成するストリーミングを渡すことができますでメッセージ本文、 **XmlReader**します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-120">To create a message that can be used for node streaming you can pass the message body in an **XmlReader**.</span></span>  
  
  <span data-ttu-id="12ae7-121">通常、ノードと値のエンド ツー エンドの要求メッセージ内での Oracle LOB データのストリーミングをサポートするためにストリーミングを使用します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-121">You typically use node-value streaming to support end-to-end streaming of Oracle LOB data in the request message.</span></span> <span data-ttu-id="12ae7-122">この機能をサポートする唯一の操作では、UpdateLOB です。</span><span class="sxs-lookup"><span data-stu-id="12ae7-122">The only operation that supports this feature is UpdateLOB.</span></span>  
  
### <a name="consuming-the-response-message"></a><span data-ttu-id="12ae7-123">応答メッセージの使用</span><span class="sxs-lookup"><span data-stu-id="12ae7-123">Consuming the response message</span></span>  
 <span data-ttu-id="12ae7-124">2 つの方法のいずれかで応答メッセージを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="12ae7-124">You can consume the response message in one of two ways:</span></span>  
  
- <span data-ttu-id="12ae7-125">ストリーミングするノードの値を使用してメッセージを使用して呼び出す必要があります、 **WriteBodyContents**メソッドからの応答でメッセージを渡して、 **XmlDictionaryWriter**ノード値のストリーミングを実装します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-125">To consume the message using node-value streaming you must call the **WriteBodyContents** method on the response message and pass it an **XmlDictionaryWriter** that implements node-value streaming.</span></span>  
  
- <span data-ttu-id="12ae7-126">ノードのストリーミングを使用してメッセージを呼び出すことができますを使用する**GetReaderAtBodyContents**を取得する応答メッセージで、 **XmlReader**します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-126">To consume the message using node streaming you can call **GetReaderAtBodyContents** on the response message to get an **XmlReader**.</span></span>  
  
  <span data-ttu-id="12ae7-127">通常、ノードと値のエンド ツー エンドの応答メッセージでの Oracle LOB データのストリーミングをサポートするためにストリーミングを使用します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-127">You typically use node-value streaming to support end-to-end streaming of Oracle LOB data in the response message.</span></span> <span data-ttu-id="12ae7-128">この機能をサポートする多くの操作があります。</span><span class="sxs-lookup"><span data-stu-id="12ae7-128">There are many operations that support this feature.</span></span>  
  
### <a name="lob-data-and-message-streaming-support"></a><span data-ttu-id="12ae7-129">LOB データおよびメッセージのストリーミング サポート</span><span class="sxs-lookup"><span data-stu-id="12ae7-129">LOB Data and Message Streaming Support</span></span>  
 <span data-ttu-id="12ae7-130">方法の詳細については[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]LOB データのストリーミング サポートを参照してください[Oracle データベース アダプターのラージ オブジェクト データ型のストリーミング](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-130">For more information about how the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports streaming on LOB data, see [Streaming large object data types in Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md).</span></span>  
  
 <span data-ttu-id="12ae7-131">ノード値のエンド ツー エンドの LOB データのストリーミングをサポートするために、コードでは、ストリーミングの実装の詳細については、[ストリーミング Oracle LOB データ型を使用してデータベース、WCF チャネル モデル](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12ae7-131">For more information about implementing node-value streaming in your code to support end-to-end streaming of LOB data, see [Streaming Oracle Database LOB Data Types Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="transaction-support-on-outbound-operations-in-the-wcf-channel-model"></a><span data-ttu-id="12ae7-132">WCF チャネル モデルでの送信操作でトランザクションのサポート。</span><span class="sxs-lookup"><span data-stu-id="12ae7-132">Transaction Support on Outbound Operations in the WCF Channel Model.</span></span>  
 <span data-ttu-id="12ae7-133">アダプターは、Oracle データベースで専用のトランザクション内で呼び出す各操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-133">The adapter executes each operation you invoke inside a dedicated transaction on the Oracle database.</span></span> <span data-ttu-id="12ae7-134">これらのトランザクションの分離レベルを設定して制御することができます、 **TransactionIsolationLevel**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="12ae7-134">You can control the isolation level of these transactions by setting the **TransactionIsolationLevel** binding property.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="12ae7-135">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="12ae7-135">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="12ae7-136">このトピックの例では、SCOTT を使用します。ACCOUNTACTIVITY テーブルです。</span><span class="sxs-lookup"><span data-stu-id="12ae7-136">The example in this topic uses the SCOTT.ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="12ae7-137">これらの成果物を生成するスクリプトは SDK のサンプルで提供されます。</span><span class="sxs-lookup"><span data-stu-id="12ae7-137">A script to generate these artifacts is supplied with the SDK samples.</span></span> <span data-ttu-id="12ae7-138">SDK サンプルの詳細については、[SDK 内のサンプル](../../core/samples-in-the-sdk.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12ae7-138">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="how-do-i-invoke-an-operation-by-using-a-channel"></a><span data-ttu-id="12ae7-139">チャネルを使用して、操作を呼び出す方法</span><span class="sxs-lookup"><span data-stu-id="12ae7-139">How Do I Invoke an Operation by Using a Channel?</span></span>  
 <span data-ttu-id="12ae7-140">使用して、操作を呼び出す、 **IRequestChannel**、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="12ae7-140">To invoke an operation by using an **IRequestChannel**, perform the following steps.</span></span>  
  
#### <a name="how-to-invoke-an-operation-by-using-an-instance-of-irequestchannel"></a><span data-ttu-id="12ae7-141">IRequestChannel のインスタンスを使用して、操作を呼び出す方法</span><span class="sxs-lookup"><span data-stu-id="12ae7-141">How to invoke an operation by using an instance of IRequestChannel</span></span>  
  
1. <span data-ttu-id="12ae7-142">チャネル ファクトリの作成 (**ChannelFactory\<IRequestChannel\>**)。</span><span class="sxs-lookup"><span data-stu-id="12ae7-142">Build a channel factory (**ChannelFactory\<IRequestChannel\>**).</span></span> <span data-ttu-id="12ae7-143">これを行うには、バインドを指定する必要があります (**OracleDBBinding**) とエンドポイント アドレス。</span><span class="sxs-lookup"><span data-stu-id="12ae7-143">To do this, you must specify a binding (**OracleDBBinding**) and an endpoint address.</span></span> <span data-ttu-id="12ae7-144">コードで強制的に、または構成で宣言によって、バインディングとエンドポイント アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="12ae7-144">You can specify the binding and endpoint address either imperatively in your code or declaratively in configuration.</span></span> <span data-ttu-id="12ae7-145">構成でバインディングとエンドポイント アドレスを指定する方法の詳細については、[Oracle データベースを使用してチャネルを作成](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12ae7-145">For more information about how to specify the binding and endpoint address in configuration, see [Create a channel using Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md).</span></span>  
  
   ```  
   // Create a binding  
   OracleDBBinding binding = new OracleDBBinding();  
   // Create an endpoint address by using the connection URI  
   EndpointAddress address = new EndpointAddress("oracledb://ADAPTER");  
   // Create the channel factory  
   ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
   ```  
  
2. <span data-ttu-id="12ae7-146">使用してチャネル ファクトリの名前のパスワード資格情報をユーザーに設定、 **ClientCredentials**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="12ae7-146">Set the user name password credentials for the channel factory by using the **ClientCredentials** property.</span></span>  
  
   ```  
   factory.Credentials.UserName.UserName = "SCOTT";  
   factory.Credentials.UserName.Password = "TIGER";  
   ```  
  
3. <span data-ttu-id="12ae7-147">チャネル ファクトリを開きます。</span><span class="sxs-lookup"><span data-stu-id="12ae7-147">Open the channel factory.</span></span>  
  
   ```  
   factory.Open();  
   ```  
  
4. <span data-ttu-id="12ae7-148">ファクトリからチャネルを取得し、開きます。</span><span class="sxs-lookup"><span data-stu-id="12ae7-148">Get a channel from the factory and open it.</span></span>  
  
   ```  
   IRequestChannel channel = factory.CreateChannel();  
   channel.Open();  
   ```  
  
5. <span data-ttu-id="12ae7-149">作成、**メッセージ**対象の操作のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="12ae7-149">Create a **Message** instance for the target operation.</span></span> <span data-ttu-id="12ae7-150">対象の操作のメッセージのアクションが指定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-150">Be sure that the message action for the target operation is specified.</span></span> <span data-ttu-id="12ae7-151">作成して、この例では、メッセージ本文が渡される、 **XmlReader**ファイル。</span><span class="sxs-lookup"><span data-stu-id="12ae7-151">In this example, the message body is passed by creating an **XmlReader** over a file.</span></span> <span data-ttu-id="12ae7-152">対象の操作は、SCOTT/EMP テーブルでの選択操作です。</span><span class="sxs-lookup"><span data-stu-id="12ae7-152">The target operation is a Select operation on the SCOTT/EMP table.</span></span>  
  
   ```  
   XmlReader readerIn = XmlReader.Create("SelectAllActivity.xml");  
   Message messageIn = Message.CreateMessage(MessageVersion.Default,  
       "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select",  
       readerIn);  
   ```  
  
6. <span data-ttu-id="12ae7-153">呼び出す、**要求**メソッドにメッセージを送信するチャネルを[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]したり応答を受け取ったりします。</span><span class="sxs-lookup"><span data-stu-id="12ae7-153">Invoke the **Request** method on the channel to send the message to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] and receive the reply.</span></span> <span data-ttu-id="12ae7-154">Oracle データベースには、例外が発生すると、アダプターがスローされます、 **TargetSystemException**します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-154">If the Oracle database encounters an exception, the adapter throws a **TargetSystemException**.</span></span> <span data-ttu-id="12ae7-155">(その他の例外は、以外の Oracle の例外の考えられる)。Oracle のエラーの説明を取得することができます、 **InnerException.Message**のプロパティ、 **TargetSystemException**します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-155">(Other exceptions are possible for non Oracle exceptions.) You can get a description of the Oracle error from the **InnerException.Message** property of the **TargetSystemException**.</span></span>  
  
   ```  
   try  
   {  
       Message messageOut = channel.Request(messageIn);  
   }  
   catch (Exception ex)  
   {  
       // handle exception  
   }  
   ```  
  
7. <span data-ttu-id="12ae7-156">応答を処理します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-156">Process the response.</span></span> <span data-ttu-id="12ae7-157">この例で**GetReaderAtBodyContents**がメッセージの本文を取得する応答メッセージで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="12ae7-157">In this example, **GetReaderAtBodyContents** is called on the response message to get the message body.</span></span>  
  
   ```  
   XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
   ```  
  
8. <span data-ttu-id="12ae7-158">完了したら、応答メッセージの処理リーダーおよびメッセージを閉じます。</span><span class="sxs-lookup"><span data-stu-id="12ae7-158">When you are done processing the response message, close the reader and the message.</span></span>  
  
   ```  
   readerOut.Close();  
   messageOut.Close();  
   ```  
  
9. <span data-ttu-id="12ae7-159">完了したら、チャネルとチャネル ファクトリを使用して終了しますか。</span><span class="sxs-lookup"><span data-stu-id="12ae7-159">When you are done using the channel and the channel factory, close them.</span></span> <span data-ttu-id="12ae7-160">ファクトリを閉じることで作成されたすべてのチャネルが閉じられます。</span><span class="sxs-lookup"><span data-stu-id="12ae7-160">Closing the factory will close all channels that were created with it.</span></span>  
  
    ```  
    channel.Close()  
    factory.Close();  
  
    ```  
  
   <span data-ttu-id="12ae7-161">使用してメッセージを送信するのと同じ手順を行う、 **IOutputChannel**以外の図形します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-161">You follow the same steps to send a message using the **IOutputChannel** shape except:</span></span>  
  
-   <span data-ttu-id="12ae7-162">作成する、 **ChannelFactory\<IOutputChannel\>** 手順 1 でします。</span><span class="sxs-lookup"><span data-stu-id="12ae7-162">You create a **ChannelFactory\<IOutputChannel\>** in step 1.</span></span>  
  
-   <span data-ttu-id="12ae7-163">呼び出す、**送信**手順 6. で、チャネル上のメソッド。</span><span class="sxs-lookup"><span data-stu-id="12ae7-163">You call the **Send** method on the channel in step 6.</span></span> <span data-ttu-id="12ae7-164">`channel.Send(messageIn);`。</span><span class="sxs-lookup"><span data-stu-id="12ae7-164">`channel.Send(messageIn);`.</span></span>  
  
-   <span data-ttu-id="12ae7-165">返される応答メッセージが表示されない、 **IOutputChannel**します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-165">There is no response message returned for an **IOutputChannel**.</span></span>  
  
### <a name="example"></a><span data-ttu-id="12ae7-166">例</span><span class="sxs-lookup"><span data-stu-id="12ae7-166">Example</span></span>  
 <span data-ttu-id="12ae7-167">次の例を使用して、選択操作を呼び出す方法を示しています、 **IRequestChannel**チャネル。</span><span class="sxs-lookup"><span data-stu-id="12ae7-167">The following example shows how to invoke a Select operation by using an **IRequestChannel** channel.</span></span> <span data-ttu-id="12ae7-168">使用して、応答メッセージが使用される、 **XmlReader**し、返されるレコードの数は、コンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="12ae7-168">The Select response message is consumed by using an **XmlReader** and the number of records returned is written to the console.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
using System.Xml;  
using System.IO;  
using System.Runtime.Serialization;  
  
namespace RequestChanneSample  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // The Select operation request message  
            const string selectRequestString =  
                "\<Select xmlns=\"http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY\"\>" +  
                    "<COLUMN_NAMES>*</COLUMN_NAMES>" +  
                    "<FILTER>ACCOUNT = 100002</FILTER>" +  
                "</Select>";  
            try  
            {  
                // Create binding -- specify binding properties before you open the factory.  
                OracleDBBinding odbBinding = new OracleDBBinding();  
  
                // Create address.  
                EndpointAddress odbAddress = new EndpointAddress("oracledb://ADAPTER/");  
  
                // Create channel factory from binding and address.  
                ChannelFactory<IRequestChannel> factory =   
                    new ChannelFactory<IRequestChannel>(odbBinding, odbAddress);  
  
                // Specify credentials   
                factory.Credentials.UserName.UserName = "SCOTT";  
                factory.Credentials.UserName.Password = "TIGER";  
  
                // Open the factory.  
                factory.Open();  
  
                // Get a channel.  
                IRequestChannel channel = factory.CreateChannel();  
  
                // Open the channel.  
                channel.Open();  
  
                // Create the request message from the string  
                StringReader strReader = new StringReader(selectRequestString);  
                XmlReader readerIn = XmlReader.Create(strReader);  
  
                Message requestMessage = Message.CreateMessage(MessageVersion.Default,  
                    "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select",  
                    readerIn);  
  
                Send the message and get a respone  
                Message responseMessage = channel.Request(requestMessage);  
  
                // Get an XmlReader from the message  
                XmlReader readerOut = (XmlReader) responseMessage.GetReaderAtBodyContents();  
  
                // Count the number of records returned and write to the console.  
                readerOut.MoveToContent();  
                int numberOfRecordsReturned = 0;  
                while (readerOut.Read())  
                {  
                    if (readerOut.NodeType == XmlNodeType.Element && readerOut.Name == "ACCOUNTACTIVITYRECORDSELECT")  
                        numberOfRecordsReturned++;  
                }  
  
                Console.WriteLine("{0} records returned.", numberOfRecordsReturned);  
  
                // Close the output reader and message  
                readerOut.Close();  
                responseMessage.Close();  
  
                //Close channel  
                channel.Close();  
  
                //Close the factory  
                factory.Close();  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine(ex.Message);  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="12ae7-169">参照</span><span class="sxs-lookup"><span data-stu-id="12ae7-169">See Also</span></span>  
 [<span data-ttu-id="12ae7-170">WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="12ae7-170">Develop Oracle Database applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)