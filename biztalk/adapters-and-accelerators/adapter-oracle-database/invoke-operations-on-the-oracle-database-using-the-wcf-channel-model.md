---
title: WCF チャネル モデルを使用して Oracle データベースに対する操作を呼び出す |Microsoft ドキュメント
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
ms.openlocfilehash: 65eb19845bf4e103b4abe2466e58fb09a96c23c9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962784"
---
# <a name="invoke-operations-on-the-oracle-database-using-the-wcf-channel-model"></a><span data-ttu-id="131f6-102">WCF チャネル モデルを使用して Oracle データベースに対する操作を呼び出す</span><span class="sxs-lookup"><span data-stu-id="131f6-102">Invoke Operations on the Oracle Database Using the WCF Channel Model</span></span>
<span data-ttu-id="131f6-103">に対して操作を呼び出すことができます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を使用して、 **IRequestChannel**または**IOutputChannel**図形をアダプターにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="131f6-103">You can invoke operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] by using an **IRequestChannel** or **IOutputChannel** shape to send messages to the adapter.</span></span> <span data-ttu-id="131f6-104">基本的なパターンは、バインドを使用して、必要なチャネル形状をチャネル ファクトリを作成する (**OracleDBBinding**) と接続 URI から作成されたエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="131f6-104">The basic pattern is to create a channel factory for the required channel shape by using a binding (**OracleDBBinding**) and an endpoint created from a connection URI.</span></span> <span data-ttu-id="131f6-105">作成し、**メッセージ**をターゲットの操作用のメッセージ スキーマに準拠する SOAP メッセージを表すインスタンス。</span><span class="sxs-lookup"><span data-stu-id="131f6-105">You then create a **Message** instance that represents a SOAP message that conforms to the message schema for your target operation.</span></span> <span data-ttu-id="131f6-106">これを送信することができますし、**メッセージ**を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]チャネル ファクトリから作成されたチャネルを使用しています。</span><span class="sxs-lookup"><span data-stu-id="131f6-106">You can then send this **Message** to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] by using a channel created from the channel factory.</span></span> <span data-ttu-id="131f6-107">使用している場合、 **IRequestChannel**応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="131f6-107">If you are using an **IRequestChannel**, you receive a response.</span></span> <span data-ttu-id="131f6-108">Oracle データベースで操作の実行に問題がある場合、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]スロー、 **Microsoft.ServiceModel.Channels.Common.TargetSystemException**です。</span><span class="sxs-lookup"><span data-stu-id="131f6-108">If there is a problem executing the operation on the Oracle database, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] throws a **Microsoft.ServiceModel.Channels.Common.TargetSystemException**.</span></span>  
  
 <span data-ttu-id="131f6-109">使用して操作を送信する方法の概要については、 **IRequestChannel** WCF を参照してください「クライアント チャネル レベルのプログラミング」 [http://go.microsoft.com/fwlink/?LinkId=106081](http://go.microsoft.com/fwlink/?LinkId=106081)です。</span><span class="sxs-lookup"><span data-stu-id="131f6-109">For an overview of how to send operations using an **IRequestChannel** in WCF, see "Client Channel-Level Programming" at [http://go.microsoft.com/fwlink/?LinkId=106081](http://go.microsoft.com/fwlink/?LinkId=106081).</span></span>  
  
 <span data-ttu-id="131f6-110">このトピックのセクションでは、操作の呼び出しに役立つ情報を提供する、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF チャネル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="131f6-110">The sections in this topic provide information to help you invoke operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] using the WCF channel model.</span></span>  
  
## <a name="creating-and-consuming-messages-for-outbound-operations"></a><span data-ttu-id="131f6-111">作成および送信操作のメッセージを使用</span><span class="sxs-lookup"><span data-stu-id="131f6-111">Creating and Consuming Messages for Outbound Operations</span></span>  
 <span data-ttu-id="131f6-112">に対して操作を呼び出す、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、いずれかを使用して、ターゲット操作の要求メッセージを送信する、 **IRequestChannel**または**IOutputChannel**です。</span><span class="sxs-lookup"><span data-stu-id="131f6-112">To invoke an operation on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], you send the request message for the target operation using either an **IRequestChannel** or an **IOutputChannel**.</span></span> <span data-ttu-id="131f6-113">使用する場合、 **IRequestChannel**アダプターは、応答メッセージの操作の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="131f6-113">If you use an **IRequestChannel** the adapter returns the results of the operation in the response message.</span></span>  
  
 <span data-ttu-id="131f6-114">詳細については、要求および応答メッセージ スキーマと、各操作のメッセージ アクションに関する情報を参照してください。[メッセージと BizTalk Adapter 用 Oracle Database のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="131f6-114">For more detailed information about the request and response message schemas and the message actions for each operation, see [Messages and Message Schemas for BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).</span></span>  
  
 <span data-ttu-id="131f6-115">要求メッセージを作成および応答メッセージを取得する方法は、ノードのストリーミングまたはノードと値のストリーミングがアダプターによって実行されるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="131f6-115">How you create the request message and consume the response message determines whether node streaming or node-value streaming is performed by the adapter.</span></span> <span data-ttu-id="131f6-116">これは、さらに、サポートされている操作のエンド ツー エンドの LOB データのストリーミングを実行するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="131f6-116">This in turn determines whether end-to-end streaming of LOB data is performed for supported operations.</span></span>  
  
### <a name="creating-the-request-message"></a><span data-ttu-id="131f6-117">要求メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="131f6-117">Creating the request message</span></span>  
 <span data-ttu-id="131f6-118">2 つの方法では、要求メッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="131f6-118">You can create the request message in one of two ways:</span></span>  
  
-   <span data-ttu-id="131f6-119">ノード値に使用できるメッセージの作成にストリーミングを渡す必要がありますでメッセージ本文、 **XmlBodyWriter**ノード値のストリーミングを実装します。</span><span class="sxs-lookup"><span data-stu-id="131f6-119">To create a message that can be used for node-value streaming you must pass the message body in an **XmlBodyWriter** that implements node-value streaming.</span></span>  
  
-   <span data-ttu-id="131f6-120">ノードを使用できるメッセージの作成にストリーミングを渡すことができますでメッセージ本文、 **XmlReader**です。</span><span class="sxs-lookup"><span data-stu-id="131f6-120">To create a message that can be used for node streaming you can pass the message body in an **XmlReader**.</span></span>  
  
 <span data-ttu-id="131f6-121">通常、ノードと値のエンド ツー エンドの要求メッセージ内での Oracle LOB データのストリーミングをサポートするためにストリーミングを使用します。</span><span class="sxs-lookup"><span data-stu-id="131f6-121">You typically use node-value streaming to support end-to-end streaming of Oracle LOB data in the request message.</span></span> <span data-ttu-id="131f6-122">この機能をサポートする唯一の操作は、UpdateLOB です。</span><span class="sxs-lookup"><span data-stu-id="131f6-122">The only operation that supports this feature is UpdateLOB.</span></span>  
  
### <a name="consuming-the-response-message"></a><span data-ttu-id="131f6-123">応答メッセージの使用</span><span class="sxs-lookup"><span data-stu-id="131f6-123">Consuming the response message</span></span>  
 <span data-ttu-id="131f6-124">2 つの方法のいずれかで応答メッセージを利用できます。</span><span class="sxs-lookup"><span data-stu-id="131f6-124">You can consume the response message in one of two ways:</span></span>  
  
-   <span data-ttu-id="131f6-125">呼び出す必要がありますをストリーミングするノードの値を使用してメッセージを使用する、 **WriteBodyContents**メソッド、応答でメッセージを渡します、 **XmlDictionaryWriter**ノード値のストリーミングを実装します。</span><span class="sxs-lookup"><span data-stu-id="131f6-125">To consume the message using node-value streaming you must call the **WriteBodyContents** method on the response message and pass it an **XmlDictionaryWriter** that implements node-value streaming.</span></span>  
  
-   <span data-ttu-id="131f6-126">ノードのストリーミングを使用してメッセージを呼び出すことができますを使用する**GetReaderAtBodyContents**を取得する応答メッセージで、 **XmlReader**です。</span><span class="sxs-lookup"><span data-stu-id="131f6-126">To consume the message using node streaming you can call **GetReaderAtBodyContents** on the response message to get an **XmlReader**.</span></span>  
  
 <span data-ttu-id="131f6-127">通常、ノードと値のエンド ツー エンドの応答メッセージの Oracle LOB データのストリーミングをサポートするためにストリーミングを使用します。</span><span class="sxs-lookup"><span data-stu-id="131f6-127">You typically use node-value streaming to support end-to-end streaming of Oracle LOB data in the response message.</span></span> <span data-ttu-id="131f6-128">この機能をサポートするさまざまな操作があります。</span><span class="sxs-lookup"><span data-stu-id="131f6-128">There are many operations that support this feature.</span></span>  
  
### <a name="lob-data-and-message-streaming-support"></a><span data-ttu-id="131f6-129">LOB データおよびメッセージのストリーミング サポート</span><span class="sxs-lookup"><span data-stu-id="131f6-129">LOB Data and Message Streaming Support</span></span>  
 <span data-ttu-id="131f6-130">方法の詳細については[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]LOB データのストリーミング サポートを参照してください[Oracle データベース アダプターのラージ オブジェクト データ型をストリーミング](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="131f6-130">For more information about how the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports streaming on LOB data, see [Streaming large object data types in Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md).</span></span>  
  
 <span data-ttu-id="131f6-131">ノード値のエンド ツー エンドの LOB データのストリーミングをサポートするために、コードでは、ストリーミングの実装の詳細については、次を参照してください。[ストリーミング Oracle LOB データ型を使用してデータベース、WCF チャネル モデル](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)です。</span><span class="sxs-lookup"><span data-stu-id="131f6-131">For more information about implementing node-value streaming in your code to support end-to-end streaming of LOB data, see [Streaming Oracle Database LOB Data Types Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="transaction-support-on-outbound-operations-in-the-wcf-channel-model"></a><span data-ttu-id="131f6-132">WCF チャネル モデルでの送信操作でトランザクションのサポート。</span><span class="sxs-lookup"><span data-stu-id="131f6-132">Transaction Support on Outbound Operations in the WCF Channel Model.</span></span>  
 <span data-ttu-id="131f6-133">アダプターは、Oracle データベースで専用のトランザクションの内部呼び出しの各操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="131f6-133">The adapter executes each operation you invoke inside a dedicated transaction on the Oracle database.</span></span> <span data-ttu-id="131f6-134">これらのトランザクションの分離レベルを設定して制御することができます、 **TransactionIsolationLevel**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="131f6-134">You can control the isolation level of these transactions by setting the **TransactionIsolationLevel** binding property.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="131f6-135">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="131f6-135">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="131f6-136">このトピックの例では、SCOTT を使用します。ACCOUNTACTIVITY テーブルです。</span><span class="sxs-lookup"><span data-stu-id="131f6-136">The example in this topic uses the SCOTT.ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="131f6-137">これらの成果物を生成するスクリプトは、SDK サンプルの値が提供されます。</span><span class="sxs-lookup"><span data-stu-id="131f6-137">A script to generate these artifacts is supplied with the SDK samples.</span></span> <span data-ttu-id="131f6-138">SDK サンプルの詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)です。</span><span class="sxs-lookup"><span data-stu-id="131f6-138">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="how-do-i-invoke-an-operation-by-using-a-channel"></a><span data-ttu-id="131f6-139">チャネルを使用して、操作を呼び出す方法</span><span class="sxs-lookup"><span data-stu-id="131f6-139">How Do I Invoke an Operation by Using a Channel?</span></span>  
 <span data-ttu-id="131f6-140">使用して、操作を呼び出す、 **IRequestChannel**、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="131f6-140">To invoke an operation by using an **IRequestChannel**, perform the following steps.</span></span>  
  
#### <a name="how-to-invoke-an-operation-by-using-an-instance-of-irequestchannel"></a><span data-ttu-id="131f6-141">IRequestChannel のインスタンスを使用して、操作を呼び出す方法</span><span class="sxs-lookup"><span data-stu-id="131f6-141">How to invoke an operation by using an instance of IRequestChannel</span></span>  
  
1.  <span data-ttu-id="131f6-142">チャネル ファクトリを作成 (**ChannelFactory\<IRequestChannel\>**)。</span><span class="sxs-lookup"><span data-stu-id="131f6-142">Build a channel factory (**ChannelFactory\<IRequestChannel\>**).</span></span> <span data-ttu-id="131f6-143">これを行うには、バインドを指定する必要があります (**OracleDBBinding**) およびエンドポイント アドレス。</span><span class="sxs-lookup"><span data-stu-id="131f6-143">To do this, you must specify a binding (**OracleDBBinding**) and an endpoint address.</span></span> <span data-ttu-id="131f6-144">コードで命令として記述または構成で宣言によって、バインドとエンドポイント アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="131f6-144">You can specify the binding and endpoint address either imperatively in your code or declaratively in configuration.</span></span> <span data-ttu-id="131f6-145">構成でバインディングとエンドポイント アドレスを指定する方法の詳細については、次を参照してください。 [Oracle データベースを使用して、チャネルの作成](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="131f6-145">For more information about how to specify the binding and endpoint address in configuration, see [Create a channel using Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md).</span></span>  
  
    ```  
    // Create a binding  
    OracleDBBinding binding = new OracleDBBinding();  
    // Create an endpoint address by using the connection URI  
    EndpointAddress address = new EndpointAddress("oracledb://ADAPTER");  
    // Create the channel factory  
    ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
    ```  
  
2.  <span data-ttu-id="131f6-146">使用してチャネル ファクトリの名前のパスワードの資格情報をユーザーに設定、 **ClientCredentials**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="131f6-146">Set the user name password credentials for the channel factory by using the **ClientCredentials** property.</span></span>  
  
    ```  
    factory.Credentials.UserName.UserName = "SCOTT";  
    factory.Credentials.UserName.Password = "TIGER";  
    ```  
  
3.  <span data-ttu-id="131f6-147">チャネル ファクトリを開きます。</span><span class="sxs-lookup"><span data-stu-id="131f6-147">Open the channel factory.</span></span>  
  
    ```  
    factory.Open();  
    ```  
  
4.  <span data-ttu-id="131f6-148">工場出荷時にチャネルを取得し、開きます。</span><span class="sxs-lookup"><span data-stu-id="131f6-148">Get a channel from the factory and open it.</span></span>  
  
    ```  
    IRequestChannel channel = factory.CreateChannel();  
    channel.Open();  
    ```  
  
5.  <span data-ttu-id="131f6-149">作成、**メッセージ**ターゲット操作のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="131f6-149">Create a **Message** instance for the target operation.</span></span> <span data-ttu-id="131f6-150">ターゲットの操作のメッセージ アクションが指定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="131f6-150">Be sure that the message action for the target operation is specified.</span></span> <span data-ttu-id="131f6-151">この例では、メッセージ本文が作成することで渡される、 **XmlReader**ファイル。</span><span class="sxs-lookup"><span data-stu-id="131f6-151">In this example, the message body is passed by creating an **XmlReader** over a file.</span></span> <span data-ttu-id="131f6-152">ターゲットの操作は、SCOTT/EMP テーブルでの選択操作です。</span><span class="sxs-lookup"><span data-stu-id="131f6-152">The target operation is a Select operation on the SCOTT/EMP table.</span></span>  
  
    ```  
    XmlReader readerIn = XmlReader.Create("SelectAllActivity.xml");  
    Message messageIn = Message.CreateMessage(MessageVersion.Default,  
        "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select",  
        readerIn);  
    ```  
  
6.  <span data-ttu-id="131f6-153">呼び出す、**要求**メッセージを送信するチャネルのメソッド、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]と返信を受信します。</span><span class="sxs-lookup"><span data-stu-id="131f6-153">Invoke the **Request** method on the channel to send the message to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] and receive the reply.</span></span> <span data-ttu-id="131f6-154">Oracle データベースには、例外が発生すると、アダプターをスロー、 **TargetSystemException**です。</span><span class="sxs-lookup"><span data-stu-id="131f6-154">If the Oracle database encounters an exception, the adapter throws a **TargetSystemException**.</span></span> <span data-ttu-id="131f6-155">(その他の例外は、以外の Oracle 例外の考えられる)。Oracle のエラーの説明を取得することができます、 **InnerException.Message**のプロパティ、 **TargetSystemException**です。</span><span class="sxs-lookup"><span data-stu-id="131f6-155">(Other exceptions are possible for non Oracle exceptions.) You can get a description of the Oracle error from the **InnerException.Message** property of the **TargetSystemException**.</span></span>  
  
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
  
7.  <span data-ttu-id="131f6-156">応答を処理します。</span><span class="sxs-lookup"><span data-stu-id="131f6-156">Process the response.</span></span> <span data-ttu-id="131f6-157">この例では**GetReaderAtBodyContents**メッセージ本文を取得する応答メッセージで呼び出されるとします。</span><span class="sxs-lookup"><span data-stu-id="131f6-157">In this example, **GetReaderAtBodyContents** is called on the response message to get the message body.</span></span>  
  
    ```  
    XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
    ```  
  
8.  <span data-ttu-id="131f6-158">完了したら、リーダーとメッセージを閉じる、応答メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="131f6-158">When you are done processing the response message, close the reader and the message.</span></span>  
  
    ```  
    readerOut.Close();  
    messageOut.Close();  
    ```  
  
9. <span data-ttu-id="131f6-159">完了すると、チャネルおよびチャネル ファクトリを使用してそれらを閉じます。</span><span class="sxs-lookup"><span data-stu-id="131f6-159">When you are done using the channel and the channel factory, close them.</span></span> <span data-ttu-id="131f6-160">ファクトリを閉じると、それを使用して作成されたすべてのチャネルが閉じられます。</span><span class="sxs-lookup"><span data-stu-id="131f6-160">Closing the factory will close all channels that were created with it.</span></span>  
  
    ```  
    channel.Close()  
    factory.Close();  
  
    ```  
  
 <span data-ttu-id="131f6-161">同じ手順を使用してメッセージを送信する、 **IOutputChannel**以外の図形します。</span><span class="sxs-lookup"><span data-stu-id="131f6-161">You follow the same steps to send a message using the **IOutputChannel** shape except:</span></span>  
  
-   <span data-ttu-id="131f6-162">作成する、 **ChannelFactory\<IOutputChannel\>** 手順 1 でします。</span><span class="sxs-lookup"><span data-stu-id="131f6-162">You create a **ChannelFactory\<IOutputChannel\>** in step 1.</span></span>  
  
-   <span data-ttu-id="131f6-163">呼び出す、**送信**手順 6. でチャネル上のメソッドです。</span><span class="sxs-lookup"><span data-stu-id="131f6-163">You call the **Send** method on the channel in step 6.</span></span> <span data-ttu-id="131f6-164">`channel.Send(messageIn);`」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="131f6-164">`channel.Send(messageIn);`.</span></span>  
  
-   <span data-ttu-id="131f6-165">に対して返される応答メッセージが表示されない、 **IOutputChannel**です。</span><span class="sxs-lookup"><span data-stu-id="131f6-165">There is no response message returned for an **IOutputChannel**.</span></span>  
  
### <a name="example"></a><span data-ttu-id="131f6-166">例</span><span class="sxs-lookup"><span data-stu-id="131f6-166">Example</span></span>  
 <span data-ttu-id="131f6-167">次の例を使用して、選択操作を呼び出す方法を示しています、 **IRequestChannel**チャネル。</span><span class="sxs-lookup"><span data-stu-id="131f6-167">The following example shows how to invoke a Select operation by using an **IRequestChannel** channel.</span></span> <span data-ttu-id="131f6-168">使用して、応答メッセージが表示される、 **XmlReader**され返されたレコードの数が、コンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="131f6-168">The Select response message is consumed by using an **XmlReader** and the number of records returned is written to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="131f6-169">参照</span><span class="sxs-lookup"><span data-stu-id="131f6-169">See Also</span></span>  
 [<span data-ttu-id="131f6-170">WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="131f6-170">Develop Oracle Database applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)