---
title: WCF チャネル モデルを使用して Oracle データベースでのポーリングに基づいたデータ変更メッセージの受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, receiving polling-based messages
- how to, receive polling-based messages by using the WCF channel model
ms.assetid: 13f501e4-cff7-497c-a9da-fdd6382c779f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6398b4c92fc4490b5cb55ad665131e58081a2bdd
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529476"
---
# <a name="receive-polling-based-data-changed-messages-in-oracle-database-using-the-wcf-channel-model"></a><span data-ttu-id="7f500-102">WCF チャネル モデルを使用して Oracle データベースでのポーリングに基づいたデータ変更メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="7f500-102">Receive Polling-based Data-changed Messages in Oracle Database using the WCF Channel Model</span></span>
<span data-ttu-id="7f500-103">構成することができます、 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle データベースのテーブルまたはビューのデータ変更をポーリングします。</span><span class="sxs-lookup"><span data-stu-id="7f500-103">You can configure the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] to poll an Oracle database table or view for any data changes.</span></span> <span data-ttu-id="7f500-104">アダプターには、このようなポーリング操作を実行するには、Oracle のテーブルまたはビューが続く省略可能の PL/SQL コード ブロックをに対して SQL クエリを定期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="7f500-104">To perform such a polling operation, the adapter periodically executes a SQL query against an Oracle table or view followed by an optional PL/SQL code block.</span></span> <span data-ttu-id="7f500-105">によって SQL クエリの結果が返されるし、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]受信 POLLINGSTMT 操作の設定、厳密に型指定された結果として、コードにします。</span><span class="sxs-lookup"><span data-stu-id="7f500-105">The results of the SQL query are then returned by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to your code as a strongly-typed result set in an inbound POLLINGSTMT operation.</span></span> <span data-ttu-id="7f500-106">使用してデータベースを構成し、Oracle のポーリングを実行するためのメカニズムの詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle データベース アダプターのポーリングに基づいたデータ変更メッセージを受信](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="7f500-106">For more information about the mechanism used to configure and perform polling on an Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Receive polling-based data-changed messages in Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md).</span></span> <span data-ttu-id="7f500-107">続行する前に、このトピックで確認することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7f500-107">It is strongly recommended that you read this topic before proceeding.</span></span>  
  
 <span data-ttu-id="7f500-108">構成する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ポーリングと Oracle データベースのテーブルまたはビューのインスタンスにバインドのプロパティを設定して**OracleDBBinding**します。</span><span class="sxs-lookup"><span data-stu-id="7f500-108">You configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to poll and Oracle database table or view by setting binding properties on an instance of **OracleDBBinding**.</span></span> <span data-ttu-id="7f500-109">WCF チャネル モデルで、このバインディングを使用する取得できますチャネル リスナーを作成、 **IInputChannel** POLLINGSTMT 操作をアダプターから受信するチャネル。</span><span class="sxs-lookup"><span data-stu-id="7f500-109">In the WCF channel model, you then use this binding to build a channel listener from which you can get an **IInputChannel** channel to receive the POLLINGSTMT operation from the adapter.</span></span>  
  
 <span data-ttu-id="7f500-110">受信操作を使用する方法の概要については、 **IInputChannel** WCF では、次を参照してください。[サービス チャネル レベルのプログラミング](https://msdn.microsoft.com/library/ms789029.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="7f500-110">For an overview of how to receive operations using an **IInputChannel** in WCF, see [Service Channel-Level Programming](https://msdn.microsoft.com/library/ms789029.aspx).</span></span> 
  
 <span data-ttu-id="7f500-111">このトピックのセクションでは、Oracle データベースのテーブルのポーリングを実行するために情報を提供して、WCF を使用して、ビュー モデルのチャネルします。</span><span class="sxs-lookup"><span data-stu-id="7f500-111">The sections in this topic provide information to help you perform polling on Oracle database tables and views using the WCF channel model.</span></span>  
  
## <a name="consuming-the-pollingstmt-request-message"></a><span data-ttu-id="7f500-112">POLLINGSTMT 要求メッセージの使用</span><span class="sxs-lookup"><span data-stu-id="7f500-112">Consuming the POLLINGSTMT request message</span></span>  
 <span data-ttu-id="7f500-113">アダプターは、Oracle データベースをポーリングする、コードに POLLINGSTMT 操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="7f500-113">The adapter invokes the POLLINGSTMT operation on your code to poll the Oracle database.</span></span> <span data-ttu-id="7f500-114">つまり、アダプターが経由で受信した POLLINGSTMT 要求メッセージを送信、 **IInputChannel**チャネル形状です。</span><span class="sxs-lookup"><span data-stu-id="7f500-114">That is, the adapter sends a POLLINGSTMT request message that you receive over an **IInputChannel** channel shape.</span></span> <span data-ttu-id="7f500-115">POLLINGSTMT 要求メッセージにはで指定されたクエリの結果セットが含まれています、 **PollingStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="7f500-115">The POLLINGSTMT request message contains the result set of the query specified by the **PollingStatement** binding property.</span></span> <span data-ttu-id="7f500-116">2 つの方法のいずれかで POLLINGSTMT メッセージを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7f500-116">You can consume the POLLINGSTMT message in one of two ways:</span></span>  
  
- <span data-ttu-id="7f500-117">ストリーミングするノードの値を使用してメッセージを使用して呼び出す必要があります、 **WriteBodyContents**メソッドからの応答でメッセージを渡して、 **XmlDictionaryWriter**ノード値のストリーミングを実装します。</span><span class="sxs-lookup"><span data-stu-id="7f500-117">To consume the message using node-value streaming you must call the **WriteBodyContents** method on the response message and pass it an **XmlDictionaryWriter** that implements node-value streaming.</span></span>  
  
- <span data-ttu-id="7f500-118">ノードのストリーミングを使用してメッセージを呼び出すことができますを使用する**GetReaderAtBodyContents**を取得する応答メッセージで、 **XmlReader**します。</span><span class="sxs-lookup"><span data-stu-id="7f500-118">To consume the message using node streaming you can call **GetReaderAtBodyContents** on the response message to get an **XmlReader**.</span></span>  
  
  <span data-ttu-id="7f500-119">通常、ノードと値のデータ列を Oracle LOB を含む結果セットを使用するストリーミングを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f500-119">You typically use node-value streaming to consume result sets that contain Oracle LOB data columns.</span></span>  
  
  <span data-ttu-id="7f500-120">POLLINGSTMT 操作のメッセージ構造の詳細については、次を参照してください。[ポーリング操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-polling-operations2.md)します。</span><span class="sxs-lookup"><span data-stu-id="7f500-120">For more information about the message structure of the POLLINGSTMT operation, see [Message Schemas for the Polling Operations](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-polling-operations2.md).</span></span>  
  
  <span data-ttu-id="7f500-121">方法の詳細については[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]LOB データのストリーミング サポートを参照してください[Oracle データベース アダプターのラージ オブジェクト データ型のストリーミング](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="7f500-121">For more information about how the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports streaming on LOB data, see [Streaming large object data types in Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md).</span></span>  
  
  <span data-ttu-id="7f500-122">ノード値のエンド ツー エンドの LOB データのストリーミングをサポートするために、コードでは、ストリーミングの実装の詳細については、次を参照してください。[ストリーミング Oracle LOB データ型を使用してデータベース、WCF チャネル モデル](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="7f500-122">For more information about implementing node-value streaming in your code to support end-to-end streaming of LOB data, see [Streaming Oracle Database LOB Data Types Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="7f500-123">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="7f500-123">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="7f500-124">このトピックの例では、SCOTT を使用します。ACCOUNTACTIVITY テーブルし、SCOTT します。ACCOUNT_PKG します。PROCESS_ACTIVITY 関数。</span><span class="sxs-lookup"><span data-stu-id="7f500-124">The example in this topic uses the SCOTT.ACCOUNTACTIVITY table and the SCOTT.ACCOUNT_PKG.PROCESS_ACTIVITY function.</span></span> <span data-ttu-id="7f500-125">これらの成果物を生成するスクリプトは、サンプルで提供されます。</span><span class="sxs-lookup"><span data-stu-id="7f500-125">A script to generate these artifacts is supplied with the samples.</span></span> <span data-ttu-id="7f500-126">例では、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="7f500-126">The example performs the following operations:</span></span>  
  
- <span data-ttu-id="7f500-127">ポーリング ステートメントの一部として、すべてのレコードを選択する ACCOUNTACTIVITY テーブルと、コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7f500-127">As part of the polling statement, selects all the records from the ACCOUNTACTIVITY table and displays on the console.</span></span>  
  
- <span data-ttu-id="7f500-128">ポーリング後ステートメントの一部としては、この例は、ACTIVITYHISTORY テーブル ACCOUNTACTIVITY テーブルからすべてのレコードに移動する PROCESS_ACTIVITY 関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="7f500-128">As part of the post poll statement, the example invokes the PROCESS_ACTIVITY function that moves all the records from ACCOUNTACTIVITY table to ACTIVITYHISTORY table.</span></span>  
  
- <span data-ttu-id="7f500-129">ACCOUNTACTIVITY テーブルに対する後続のアンケートでは、すべてのレコードは返されません。</span><span class="sxs-lookup"><span data-stu-id="7f500-129">Subsequent polls on the ACCOUNTACTIVITY table do not return any records.</span></span> <span data-ttu-id="7f500-130">ただし、ポーリング操作の一部として複数のレコードを返す例を実行する場合に、ACCOUNTACTIVITY テーブルで一部のレコードを挿入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f500-130">However, if you want the example to return more records as part of the polling operation, you must insert some records in the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="7f500-131">サンプルで提供される more_activity_data.sql スクリプトを実行して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7f500-131">You can do so by running the more_activity_data.sql script provided with the samples.</span></span>  
  
  <span data-ttu-id="7f500-132">サンプルの詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="7f500-132">For more information about the samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="how-do-i-poll-an-oracle-database-using-an-iinputchannel"></a><span data-ttu-id="7f500-133">IInputChannel を使用して Oracle データベースをポーリングする方法は?</span><span class="sxs-lookup"><span data-stu-id="7f500-133">How Do I Poll an Oracle Database Using an IInputChannel?</span></span>  
 <span data-ttu-id="7f500-134">Oracle データベースのテーブルまたは WCF チャネル モデルを使用して、データ変更メッセージを受信するビューをポーリングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7f500-134">To poll an Oracle database table or view to receive data-change messages using the WCF channel model, perform the following steps.</span></span>  
  
#### <a name="to-receive-data-changed-messages-using-an-iinputchannel"></a><span data-ttu-id="7f500-135">IInputChannel を使用して、データ変更メッセージを受信するには</span><span class="sxs-lookup"><span data-stu-id="7f500-135">To receive data-changed messages using an IInputChannel</span></span>  
  
1. <span data-ttu-id="7f500-136">Visual c# プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="7f500-136">Create a Visual C# project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="7f500-137">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7f500-137">For this topic, create a console application.</span></span>  
  
2. <span data-ttu-id="7f500-138">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.OracleDB`、 `Microsoft.ServiceModel.Channels`、 `System.ServiceModel`、および`System.Runtime.Serialization`します。</span><span class="sxs-lookup"><span data-stu-id="7f500-138">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleDB`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, and `System.Runtime.Serialization`.</span></span>  
  
3. <span data-ttu-id="7f500-139">Program.cs ファイルを開き、次の名前空間を追加します。</span><span class="sxs-lookup"><span data-stu-id="7f500-139">Open the Program.cs file and add the following namespaces:</span></span>  
  
   -   `Microsoft.Adapters.OracleDB`  
  
   -   `Microsoft.ServiceModel.Channels`  
  
   -   `System.ServiceModel`  
  
   -   `System.ServiceModel.Description`  
  
   -   `System.ServiceModel.Channels`  
  
   -   `System.Xml`  
  
   -   `System.Runtime.Serialization`  
  
   -   `System.IO`  
  
   -   `Microsoft.ServiceModel.Channels.Common`  
  
4. <span data-ttu-id="7f500-140">インスタンスを作成**OracleDBBinding**ポーリングを構成するために必要なバインドのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="7f500-140">Create an instance of **OracleDBBinding** and set the binding properties required to configure polling.</span></span> <span data-ttu-id="7f500-141">設定する必要がありますには、少なくとも、 **InboundOperationType**、 **PollingStatement**、および**PollingInterval**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="7f500-141">At a minimum you must set the **InboundOperationType**, **PollingStatement**, and **PollingInterval** binding properties.</span></span> <span data-ttu-id="7f500-142">この例では、設定することも、 **PostPollStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="7f500-142">For this example, you also set the **PostPollStatement** binding property.</span></span> <span data-ttu-id="7f500-143">ポーリングを構成するためのプロパティのバインドの詳細については、次を参照してください。 [Oracle データベース アダプターのポーリングに基づいたデータ変更メッセージを受信](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="7f500-143">For more information about binding properties used to configure polling, see [Receive polling-based data-changed messages in Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md).</span></span>  
  
   ```  
   OracleDBBinding binding = new OracleDBBinding();  
   binding.InboundOperationType = InboundOperation.Polling;  
   binding.PollingInterval = 30;  
   binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
   binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;"  
   ```  
  
5. <span data-ttu-id="7f500-144">バインディング パラメーターのコレクションを作成し、資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="7f500-144">Create a binding parameter collection and set the credentials.</span></span>  
  
   ```  
   ClientCredentials credentials = new ClientCredentials();  
   credentials.UserName.UserName = "SCOTT";  
   credentials.UserName.Password = "TIGER";  
  
   BindingParameterCollection bindingParams = new BindingParameterCollection();  
   bindingParams.Add(credentials);  
   ```  
  
6. <span data-ttu-id="7f500-145">チャネル リスナーを作成し、開きます。</span><span class="sxs-lookup"><span data-stu-id="7f500-145">Create a channel listener and open it.</span></span> <span data-ttu-id="7f500-146">呼び出すことによって、リスナーを作成する**BuildChannelListener < IInputChannel\>** メソッドを**OracleDBBinding**します。</span><span class="sxs-lookup"><span data-stu-id="7f500-146">You create the listener by invoking **BuildChannelListener<IInputChannel\>** method on the **OracleDBBinding**.</span></span> <span data-ttu-id="7f500-147">POLLINGSTMT 操作のターゲット名前空間を変更するには、接続 URI の PollingId プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="7f500-147">You can modify the target namespace for the POLLINGSTMT operation by setting the PollingId property in the connection URI.</span></span> <span data-ttu-id="7f500-148">アダプターの接続 URI の詳細については、次を参照してください。 [Oracle Database 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="7f500-148">For more information about the adapter connection URI, see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
   ```  
   IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
   listener.Open();  
   ```  
  
7. <span data-ttu-id="7f500-149">取得、 **IInputChannel**チャネルを呼び出すことによって、 **AcceptChannel**メソッド リスナーを開きます。</span><span class="sxs-lookup"><span data-stu-id="7f500-149">Get an **IInputChannel** channel by invoking the **AcceptChannel** method on the listener and open it.</span></span>  
  
   ```  
   IInputChannel channel = listener.AcceptChannel();  
   channel.Open();  
   ```  
  
8. <span data-ttu-id="7f500-150">呼び出す**受信**POLLINGSTMT の次のメッセージをアダプターから取得するチャネル。</span><span class="sxs-lookup"><span data-stu-id="7f500-150">Invoke **Receive** on the channel to get the next POLLINGSTMT message from the adapter.</span></span>  
  
   ```  
   Message message = channel.Receive();  
   ```  
  
9. <span data-ttu-id="7f500-151">POLLINGSTMT 操作によって返される結果セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f500-151">Consume the result set returned by the POLLINGSTMT operation.</span></span> <span data-ttu-id="7f500-152">いずれかを使用してメッセージを処理することができます、 **XmlReader**または**XmlDictionaryWriter**します。</span><span class="sxs-lookup"><span data-stu-id="7f500-152">You can consume the message using either an **XmlReader** or an **XmlDictionaryWriter**.</span></span>  
  
    ```  
    XmlReader reader = message.GetReaderAtBodyContents();  
    ```  
  
10. <span data-ttu-id="7f500-153">要求の処理が完了したら、チャネルを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7f500-153">Close the channel when you have completed processing the request.</span></span>  
  
    ```  
    channel.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="7f500-154">POLLINGSTMT 操作の処理が完了した後、チャネルを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f500-154">You must close the channel after you have finished processing the POLLINGSTMT operation.</span></span> <span data-ttu-id="7f500-155">チャネルを閉じない、コードの動作に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7f500-155">Failure to close the channel may affect the behavior of your code.</span></span>  
  
11. <span data-ttu-id="7f500-156">データ変更メッセージの受信が完了したら、リスナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7f500-156">Close the listener when you are finished receiving data-changed messages.</span></span>  
  
    ```  
    listener.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="7f500-157">リスナーを閉じる、リスナーを使用して作成されるチャネルは閉じられません。</span><span class="sxs-lookup"><span data-stu-id="7f500-157">Closing the listener does not close channels created using the listener.</span></span> <span data-ttu-id="7f500-158">各チャネル リスナーを使用して作成を明示的に閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f500-158">You must explicitly close each channel created using the listener.</span></span>  
  
### <a name="example"></a><span data-ttu-id="7f500-159">例</span><span class="sxs-lookup"><span data-stu-id="7f500-159">Example</span></span>  
 <span data-ttu-id="7f500-160">次の例は、構成する方法を示します、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF を使用して操作チャネル モデルの Oracle データベースのテーブルおよびビューをポーリングして、POLLLINGSTMT を受信します。</span><span class="sxs-lookup"><span data-stu-id="7f500-160">The following example shows how to configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to poll Oracle database tables and views and receive the POLLLINGSTMT operation using the WCF channel model.</span></span> <span data-ttu-id="7f500-161">使用して POLLINGSTMT 操作で返される結果がコンソールに書き込まれる、 **XmlReader**します。</span><span class="sxs-lookup"><span data-stu-id="7f500-161">The result set returned in the POLLINGSTMT operation is written to the console by using an **XmlReader**.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, WCF LOB Adapter SDK, and Oracle Database adapter namepaces  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Add this namespace for channel model  
using System.ServiceModel.Channels;  
  
using System.Xml;  
using System.Runtime.Serialization;  
using System.IO;  
  
// Include this namespace for the WCF LOB Adapter SDK and Oracle exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
namespace OraclePollingCM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Uri connectionUri = new Uri("oracleDB://ADAPTER/");  
  
            IChannelListener<IInputChannel> listener = null;  
            IInputChannel channel = null;  
  
            // set timeout to receive POLLINGSTMT message  
            TimeSpan messageTimeout = new TimeSpan(0, 0, 30);  
  
            Console.WriteLine("Sample Started");  
  
            try  
            {  
                // Create a binding: specify the InboundOperationType, PollingInterval (in seconds), the           
                // PollingStatement,and the PostPollStatement.  
                OracleDBBinding binding = new OracleDBBinding();  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PollingInterval = 30;  
                binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
                binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
  
                // Create a binding parameter collection and set the credentials  
                ClientCredentials credentials = new ClientCredentials();  
                credentials.UserName.UserName = "SCOTT";  
                credentials.UserName.Password = "TIGER";  
  
                BindingParameterCollection bindingParams = new BindingParameterCollection();  
                bindingParams.Add(credentials);  
  
                Console.WriteLine("Opening listener");  
                // get a listener  from the binding  
                listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
                listener.Open();  
  
                Console.WriteLine("Opening channel");  
                // get a channel from the listener  
                channel = listener.AcceptChannel();  
                channel.Open();  
  
                Console.WriteLine("Channel opened -- waiting for polled data");  
                Console.WriteLine("Receive request timeout is {0}", messageTimeout);  
  
                // Poll five times with the specified message timeout   
                // If a timeout occurs polling will be aborted  
                for (int i = 0; i < 5; i++)  
                {  
                    Console.WriteLine("Polling: " + i);  
                    Message message = null;  
                    XmlReader reader = null;  
                    try  
                    {  
                        //Message is received so process the results  
                        message = channel.Receive(messageTimeout);  
                    }  
                    catch (System.TimeoutException toEx)  
                    {  
                        Console.WriteLine("\nNo data for request number {0}: {1}", i + 1, toEx.Message);  
                        continue;  
                    }  
  
                    // Get the query results using an XML reader  
                    try  
                    {  
                        reader = message.GetReaderAtBodyContents();  
                    }  
                    catch (Exception ex)  
                    {  
                        Console.WriteLine("Exception :" + ex);  
                        throw;  
                    }  
  
                    // Write the TID, ACCOUNT, AMOUNT, and TRANSDATE for each record to the Console  
                    Console.WriteLine("\nPolling data received for request number {0}", i+1);  
                    Console.WriteLine("Tx ID\tACCOUNT\tAMOUNT\tTx DATE");  
  
                    while (reader.Read())  
                    {  
                        if (reader.IsStartElement())  
                        {  
                            switch (reader.Name)  
                            {  
                                case "POLLINGSTMTRECORD":  
                                    Console.Write("\n");  
                                    break;  
  
                                case "TID":  
                                    reader.Read();  
                                    Console.Write(reader.ReadString() + "\t");  
                                    break;  
  
                                case "ACCOUNT":  
                                    reader.Read();  
                                    Console.Write(reader.ReadString() + "\t");  
                                    break;  
                                case "AMOUNT":  
                                    reader.Read();  
                                    Console.Write(reader.ReadString() + "\t");  
                                    break;  
  
                                case "TRANSDATE":  
                                    reader.Read();  
                                    Console.Write(reader.ReadString() + "\t");  
                                    break;  
  
                                default:  
                                    break;  
                            }  
                        }  
                    }  
  
                    // return the cursor  
                    Console.WriteLine();  
  
                    // close the reader  
                    reader.Close();  
  
                    //            To save the polling data to a file you can REPLACE the code above with the following  
                    //  
                    //            XmlDocument doc = new XmlDocument();  
                    //            doc.Load(reader);  
                    //            using (XmlWriter writer = XmlWriter.Create("PollingOutput.xml"))  
                    //            {  
                    //                doc.WriteTo(writer);  
                    //            }  
                    message.Close();  
                }  
  
                Console.WriteLine("\nPolling done -- hit <RETURN> to finish");  
                Console.ReadLine();  
            }  
            catch (TargetSystemException tex)  
            {  
                Console.WriteLine("Exception occurred on the Oracle Database");  
                Console.WriteLine(tex.InnerException.Message);  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the Oracle Database");  
                Console.WriteLine(cex.InnerException.Message);  
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
                // IMPORTANT: close the channel and listener to stop polling  
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
  
## <a name="see-also"></a><span data-ttu-id="7f500-162">参照</span><span class="sxs-lookup"><span data-stu-id="7f500-162">See Also</span></span>  
 [<span data-ttu-id="7f500-163">WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="7f500-163">Develop Oracle Database applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)