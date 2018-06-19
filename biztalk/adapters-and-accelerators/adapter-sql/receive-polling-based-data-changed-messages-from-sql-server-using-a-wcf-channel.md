---
title: WCF チャネル モデルを使用して SQL Server からデータ変更のポーリングに基づいたメッセージを受信 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0f4af71-fb0c-433d-ba74-48ee6487eb1a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb785631d6fe00ea68f57f943dca11ebd1a84b1d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226394"
---
# <a name="receive-polling-based-data-changed-messages-from-sql-server-by-using-the-wcf-channel-model"></a><span data-ttu-id="e68e7-102">WCF チャネル モデルを使用して SQL Server からデータ変更のポーリングに基づいたメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-102">Receive Polling-based Data-changed Messages from SQL Server by Using the WCF Channel Model</span></span>
<span data-ttu-id="e68e7-103">構成することができます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server のテーブルまたはビューのデータの定期的な変更メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-103">You can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive periodic data-change messages for SQL Server tables or views.</span></span> <span data-ttu-id="e68e7-104">データベースをポーリングするアダプターを実行するポーリング ステートメントを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-104">You can specify a polling statement that the adapter executes to poll the database.</span></span> <span data-ttu-id="e68e7-105">ポーリング ステートメントには、SELECT ステートメントまたは結果セットを返すストアド プロシージャを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-105">The polling statement can be a SELECT statement or a stored procedure that returns a result set.</span></span>  
  
 <span data-ttu-id="e68e7-106">アダプターがポーリングをサポートする方法の詳細については、次を参照してください。[呼び出しをポーリングを使用して受信するためのサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)です。</span><span class="sxs-lookup"><span data-stu-id="e68e7-106">For more information on how the adapter supports polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e68e7-107">かどうかは、単一のアプリケーションに複数のポーリング操作を必要がありますを指定する、 **InboundID**接続一意にする URI の一部として接続プロパティです。</span><span class="sxs-lookup"><span data-stu-id="e68e7-107">If you want to have more than one polling operation in a single application, you must specify an **InboundID** connection property as part of the connection URI to make it unique.</span></span> <span data-ttu-id="e68e7-108">指定した受信 ID は、一意にする操作の名前空間に追加されます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-108">The inbound ID you specify is added to the operation namespace to make it unique.</span></span>  
  
## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="e68e7-109">このトピックの内容がポーリングを示しています</span><span class="sxs-lookup"><span data-stu-id="e68e7-109">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="e68e7-110">このトピックの内容を示すため方法、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サポート データを受信するメッセージの変更、用の .NET アプリケーションを作成、**ポーリング**操作します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-110">In this topic, to demonstrate how the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports receiving data change messages, create a .NET application for the **Polling** operation.</span></span> <span data-ttu-id="e68e7-111">このトピックでは、指定、 **PolledDataAvailableStatement**として。</span><span class="sxs-lookup"><span data-stu-id="e68e7-111">For this topic, specify the **PolledDataAvailableStatement** as:</span></span>  
  
```  
SELECT COUNT(*) FROM Employee  
```  
  
 <span data-ttu-id="e68e7-112">**PolledDataAvailableStatement**正の値を含む最初のセルを含む結果セットを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e68e7-112">The **PolledDataAvailableStatement** must return a result set with the first cell containing a positive value.</span></span> <span data-ttu-id="e68e7-113">最初のセルには正の値が含まれていない場合でも、アダプターでは、ポーリング ステートメントは実行されません。</span><span class="sxs-lookup"><span data-stu-id="e68e7-113">If the first cell does not contain a positive value, the adapter does not execute the polling statement.</span></span>  
  
 <span data-ttu-id="e68e7-114">ポーリング ステートメントの一部として、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-114">As part of the polling statement, perform the following operations:</span></span>  
  
1.  <span data-ttu-id="e68e7-115">Employee テーブルからすべての行を選択します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-115">Select all the rows from the Employee table.</span></span>  
  
2.  <span data-ttu-id="e68e7-116">ストアド プロシージャ、EmployeeHistory テーブルには Employee テーブルからすべてのレコードを移動するには、(MOVE_EMP_DATA) を実行します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-116">Execute a stored procedure (MOVE_EMP_DATA) to move all the records from the Employee table to an EmployeeHistory table.</span></span>  
  
3.  <span data-ttu-id="e68e7-117">Employee テーブルに新しいレコードを追加するには、(ADD_EMP_DETAILS) ストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-117">Execute a stored procedure (ADD_EMP_DETAILS) to add a new record to the Employee table.</span></span> <span data-ttu-id="e68e7-118">この手順は、従業員名、指定、および給与をパラメーターとして受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e68e7-118">This procedure takes the employee name, designation, and salary as parameters.</span></span>  
  
 <span data-ttu-id="e68e7-119">これらの操作を実行するは、次を指定する必要があります、 **PollingStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="e68e7-119">To perform these operations, you must specify the following for the **PollingStatement** binding property:</span></span>  
  
```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  
  
 <span data-ttu-id="e68e7-120">ポーリング ステートメントが実行された後に、Employee テーブルのすべてのレコードが選択されており、SQL Server からメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-120">After the polling statement is executed, all the records from the Employee table are selected and the message from SQL Server is received.</span></span> <span data-ttu-id="e68e7-121">アダプターによって MOVE_EMP_DATA ストアド プロシージャを実行すると、すべてのレコードが EmployeeHistory テーブルに移動されます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-121">Once the MOVE_EMP_DATA stored procedure is executed by the adapter, all the records are moved to the EmployeeHistory table.</span></span> <span data-ttu-id="e68e7-122">次に、Employee テーブルに新しいレコードを追加する ADD_EMP_DETAILS ストアド プロシージャが実行されます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-122">Then, the ADD_EMP_DETAILS stored procedure is executed to add a new record to the Employee table.</span></span> <span data-ttu-id="e68e7-123">次のポーリングの実行には、1 つのレコードだけを返します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-123">The next polling execution will only return a single record.</span></span> <span data-ttu-id="e68e7-124">このサイクルは、チャネル リスナーを閉じるまで続けられます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-124">This cycle continues until you close the channel listener.</span></span>  
  
## <a name="configuring-a-polling-query-with-the-sql-adapter-binding-properties"></a><span data-ttu-id="e68e7-125">SQL アダプターのプロパティのバインドと、ポーリング クエリの構成</span><span class="sxs-lookup"><span data-stu-id="e68e7-125">Configuring a Polling Query with the SQL Adapter Binding Properties</span></span>  
 <span data-ttu-id="e68e7-126">次の表、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドのプロパティ データの変更メッセージを受信するアダプターを構成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-126">The following table summarizes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding properties that you use to configure the adapter to receive data-change messages.</span></span> <span data-ttu-id="e68e7-127">ポーリングに使用できる .NET アプリケーションの一部としてこれらのバインディング プロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e68e7-127">You must specify these binding properties as part of the .NET application for polling.</span></span>  
  
|<span data-ttu-id="e68e7-128">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="e68e7-128">Binding Property</span></span>|<span data-ttu-id="e68e7-129">Description</span><span class="sxs-lookup"><span data-stu-id="e68e7-129">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="e68e7-130">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="e68e7-130">**InboundOperationType**</span></span>|<span data-ttu-id="e68e7-131">実行するかどうかを指定します**ポーリング**、 **TypedPolling**、または**通知**操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-131">Specifies whether you want to perform **Polling**, **TypedPolling**, or **Notification** inbound operation.</span></span> <span data-ttu-id="e68e7-132">既定値は**ポーリング**です。</span><span class="sxs-lookup"><span data-stu-id="e68e7-132">Default is **Polling**.</span></span>|  
|<span data-ttu-id="e68e7-133">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="e68e7-133">**PolledDataAvailableStatement**</span></span>|<span data-ttu-id="e68e7-134">すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-134">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="e68e7-135">SQL ステートメントには、結果の行と列で構成されるセットを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e68e7-135">The SQL statement must return a result set consisting of rows and columns.</span></span> <span data-ttu-id="e68e7-136">SQL ステートメントが指定した行がある場合のみ、 **PollingStatement**プロパティのバインドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-136">Only if a row is available, the SQL statement specified for the **PollingStatement** binding property will be executed.</span></span>|  
|<span data-ttu-id="e68e7-137">**PollingIntervalInSeconds**</span><span class="sxs-lookup"><span data-stu-id="e68e7-137">**PollingIntervalInSeconds**</span></span>|<span data-ttu-id="e68e7-138">秒単位で間隔を指定、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]の指定されたステートメントの実行、 **PolledDataAvailableStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="e68e7-138">Specifies the interval, in seconds, at which the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="e68e7-139">既定値は 30 秒です。</span><span class="sxs-lookup"><span data-stu-id="e68e7-139">The default is 30 seconds.</span></span> <span data-ttu-id="e68e7-140">ポーリング間隔では、連続するポーリングの間隔を決定します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-140">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="e68e7-141">ステートメントは、指定した期間内で実行される、アダプターは、間隔の残り時間を待機します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-141">If the statement is executed within the specified interval, the adapter waits for the remaining time in the interval.</span></span>|  
|<span data-ttu-id="e68e7-142">**PollingStatement**</span><span class="sxs-lookup"><span data-stu-id="e68e7-142">**PollingStatement**</span></span>|<span data-ttu-id="e68e7-143">SQL Server データベース テーブルをポーリングする SQL ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-143">Specifies the SQL statement to poll the SQL Server database table.</span></span> <span data-ttu-id="e68e7-144">単純な SELECT ステートメントまたはストアド プロシージャのポーリング ステートメントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-144">You can specify a simple SELECT statement or a stored procedure for the polling statement.</span></span> <span data-ttu-id="e68e7-145">既定値は null です。</span><span class="sxs-lookup"><span data-stu-id="e68e7-145">The default is null.</span></span> <span data-ttu-id="e68e7-146">値を指定する必要があります**PollingStatement**ポーリングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e68e7-146">You must specify a value for **PollingStatement** to enable polling.</span></span> <span data-ttu-id="e68e7-147">ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="e68e7-147">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="e68e7-148">セミコロンで区切られた SQL ステートメントの任意の数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-148">You can specify any number of SQL statements separated by a semi-colon.</span></span>|  
|<span data-ttu-id="e68e7-149">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="e68e7-149">**PollWhileDataFound**</span></span>|<span data-ttu-id="e68e7-150">指定するかどうか、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ポーリング間隔を無視し、継続的に指定された SQL ステートメントを実行、 **PolledDataAvailableStatement**をポーリングするテーブルにデータがある場合、プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="e68e7-150">Specifies whether the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ignores the polling interval and continuously executes the SQL statement specified for the **PolledDataAvailableStatement** binding property, if data is available in the table being polled.</span></span> <span data-ttu-id="e68e7-151">テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔で SQL ステートメントを実行する元に戻します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-151">If no data is available in the table, the adapter reverts to execute the SQL statement at the specified polling interval.</span></span> <span data-ttu-id="e68e7-152">既定値は**false**です。</span><span class="sxs-lookup"><span data-stu-id="e68e7-152">Default is **false**.</span></span>|  
  
 <span data-ttu-id="e68e7-153">これらのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="e68e7-153">For a more complete description of these properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="e68e7-154">使用する方法の詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を SQL Server をポーリングするには、このトピックの残りの部分を読み取る。</span><span class="sxs-lookup"><span data-stu-id="e68e7-154">For a complete description of how to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to poll SQL Server, read the remainder of this topic.</span></span>  
  
## <a name="consuming-the-polling-request-message"></a><span data-ttu-id="e68e7-155">ポーリング要求メッセージの使用</span><span class="sxs-lookup"><span data-stu-id="e68e7-155">Consuming the Polling Request Message</span></span>  
 <span data-ttu-id="e68e7-156">アダプターを呼び出す、**ポーリング**SQL Server データベースをポーリングするようにコードで操作します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-156">The adapter invokes the **Polling** operation on your code to poll the SQL Server database.</span></span> <span data-ttu-id="e68e7-157">つまり、アダプターは、IInputChannel チャネル形状経由で受信したポーリング要求メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-157">That is, the adapter sends a Polling request message that you receive over an IInputChannel channel shape.</span></span> <span data-ttu-id="e68e7-158">ポーリング要求メッセージには、PollingStatement バインディング プロパティで指定されたクエリの結果セットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e68e7-158">The Polling request message contains the result set of the query specified by the PollingStatement binding property.</span></span> <span data-ttu-id="e68e7-159">2 つの方法のいずれかでポーリング メッセージを利用できます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-159">You can consume the Polling message in one of two ways:</span></span>  
  
-   <span data-ttu-id="e68e7-160">呼び出す必要がありますをストリーミングするノードの値を使用してメッセージを使用する、 **WriteBodyContents**メソッド、応答でメッセージを渡します、 **XmlDictionaryWriter**ノード値のストリーミングを実装します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-160">To consume the message using node-value streaming you must call the **WriteBodyContents** method on the response message and pass it an **XmlDictionaryWriter** that implements node-value streaming.</span></span>  
  
-   <span data-ttu-id="e68e7-161">ノードのストリーミングを使用してメッセージを呼び出すことができますを使用する**GetReaderAtBodyContents**を取得する応答メッセージで、 **XmlReader**です。</span><span class="sxs-lookup"><span data-stu-id="e68e7-161">To consume the message using node streaming you can call **GetReaderAtBodyContents** on the response message to get an **XmlReader**.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="e68e7-162">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="e68e7-162">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="e68e7-163">このトピックの例では、Employee テーブルをポーリングします。</span><span class="sxs-lookup"><span data-stu-id="e68e7-163">The examples in this topic poll the Employee table.</span></span> <span data-ttu-id="e68e7-164">この例は、MOVE_EMP_DATA と ADD_EMP_DETAILS にも使用ストアド プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="e68e7-164">The example also uses the MOVE_EMP_DATA and ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="e68e7-165">これらの成果物を生成するスクリプトは、サンプルの値が提供されます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-165">A script to generate these artifacts is supplied with the samples.</span></span> <span data-ttu-id="e68e7-166">サンプルの詳細については、次を参照してください。 [SQL アダプタ サンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="e68e7-166">For more information about the samples, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span> <span data-ttu-id="e68e7-167">サンプルは、 **Polling_ChannelModel**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプルです。</span><span class="sxs-lookup"><span data-stu-id="e68e7-167">A sample, **Polling_ChannelModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="receiving-inbound-messages-for-polling-operation-using-the-wcf-channel-model"></a><span data-ttu-id="e68e7-168">WCF チャネル モデルを使用してポーリング操作の着信メッセージを受信</span><span class="sxs-lookup"><span data-stu-id="e68e7-168">Receiving Inbound Messages for Polling Operation Using the WCF Channel Model</span></span>  
 <span data-ttu-id="e68e7-169">このセクションの内容を使用してポーリングの受信メッセージを受信する .NET アプリケーション (チャネル モデル) を記述する方法の手順を説明する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e68e7-169">This section provides instructions on how to write a .NET application (channel model) to receive inbound polling messages using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
#### <a name="to-receive-polling-messages-from-the-sql-adapter"></a><span data-ttu-id="e68e7-170">SQL アダプタからポーリング メッセージを受信するには</span><span class="sxs-lookup"><span data-stu-id="e68e7-170">To receive polling messages from the SQL adapter</span></span>  
  
1.  <span data-ttu-id="e68e7-171">Microsoft Visual c# プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e68e7-171">Create a Microsoft Visual C# project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="e68e7-172">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-172">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="e68e7-173">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`、 `Microsoft.ServiceModel.Channels`、 `System.ServiceModel`、および`System.Runtime.Serialization`です。</span><span class="sxs-lookup"><span data-stu-id="e68e7-173">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, and `System.Runtime.Serialization`.</span></span>  
  
3.  <span data-ttu-id="e68e7-174">Program.cs ファイルを開き、次の名前空間を追加します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-174">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.Sql`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Description`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
4.  <span data-ttu-id="e68e7-175">接続 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-175">Specify a connection URI.</span></span> <span data-ttu-id="e68e7-176">アダプターの接続 URI の詳細については、次を参照してください。 [SQL Server の接続 URI を作成する](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="e68e7-176">For more information about the adapter connection URI, see [Create the SQL Server connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
    ```  
    Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
    ```  
  
5.  <span data-ttu-id="e68e7-177">インスタンスを作成する**SqlAdapterBinding**ポーリングを構成するために必要なバインドのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-177">Create an instance of **SqlAdapterBinding** and set the binding properties required to configure polling.</span></span> <span data-ttu-id="e68e7-178">設定する必要がありますには、少なくとも、 **InboundOperationType**、 **PolledDataAvailableStatement**、および**PollingStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="e68e7-178">At a minimum you must set the **InboundOperationType**, **PolledDataAvailableStatement**, and **PollingStatement** binding properties.</span></span> <span data-ttu-id="e68e7-179">ポーリングを構成するためのプロパティのバインドの詳細については、次を参照してください。[呼び出しをポーリングを使用して受信するためのサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)です。</span><span class="sxs-lookup"><span data-stu-id="e68e7-179">For more information about binding properties used to configure polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  
  
    ```  
    SqlAdapterBinding binding = new SqlAdapterBinding();  
    binding.InboundOperationType = InboundOperation.Polling;  
    binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
    binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
    ```  
  
6.  <span data-ttu-id="e68e7-180">バインディング パラメーターのコレクションを作成し、資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-180">Create a binding parameter collection and set the credentials.</span></span>  
  
    ```  
    ClientCredentials credentials = new ClientCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
  
    BindingParameterCollection bindingParams = new BindingParameterCollection();  
    bindingParams.Add(credentials);  
    ```  
  
7.  <span data-ttu-id="e68e7-181">チャネル リスナーを作成し、開きます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-181">Create a channel listener and open it.</span></span> <span data-ttu-id="e68e7-182">呼び出すことによって、リスナーを作成する**BuildChannelListener < IInputChannel\>** メソッドを**SqlAdapterBinding**です。</span><span class="sxs-lookup"><span data-stu-id="e68e7-182">You create the listener by invoking **BuildChannelListener<IInputChannel\>** method on the **SqlAdapterBinding**.</span></span>  
  
    ```  
    IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
    listener.Open();  
    ```  
  
8.  <span data-ttu-id="e68e7-183">取得、 **IInputChannel**を呼び出してチャネル、 **AcceptChannel**リスナーでメソッドを開きます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-183">Get an **IInputChannel** channel by invoking the **AcceptChannel** method on the listener and open it.</span></span>  
  
    ```  
    IInputChannel channel = listener.AcceptChannel();  
    channel.Open();  
    ```  
  
9. <span data-ttu-id="e68e7-184">呼び出す**受信**POLLINGSTMT の次のメッセージをアダプターから取得するチャネル。</span><span class="sxs-lookup"><span data-stu-id="e68e7-184">Invoke **Receive** on the channel to get the next POLLINGSTMT message from the adapter.</span></span>  
  
    ```  
    Message message = channel.Receive();  
    ```  
  
10. <span data-ttu-id="e68e7-185">POLLINGSTMT 操作によって返される結果セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-185">Consume the result set returned by the POLLINGSTMT operation.</span></span> <span data-ttu-id="e68e7-186">いずれかを使用してメッセージを処理することができます、 **XmlReader**または**XmlDictionaryWriter**です。</span><span class="sxs-lookup"><span data-stu-id="e68e7-186">You can consume the message using either an **XmlReader** or an **XmlDictionaryWriter**.</span></span>  
  
    ```  
    XmlReader reader = message.GetReaderAtBodyContents();  
    ```  
  
11. <span data-ttu-id="e68e7-187">要求の処理を完了すると、チャネルを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-187">Close the channel when you have completed processing the request.</span></span>  
  
    ```  
    channel.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e68e7-188">POLLINGSTMT 操作の処理が完了した後は、チャネルを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e68e7-188">You must close the channel after you have finished processing the POLLINGSTMT operation.</span></span> <span data-ttu-id="e68e7-189">チャネルを閉じない、コードの動作に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e68e7-189">Failure to close the channel may affect the behavior of your code.</span></span>  
  
12. <span data-ttu-id="e68e7-190">メッセージのデータ変更の受信が完了したら、リスナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e68e7-190">Close the listener when you are finished receiving data-changed messages.</span></span>  
  
    ```  
    listener.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e68e7-191">リスナーを閉じる、リスナーを使用して作成されるチャネルは閉じられません。</span><span class="sxs-lookup"><span data-stu-id="e68e7-191">Closing the listener does not close channels created using the listener.</span></span> <span data-ttu-id="e68e7-192">リスナーを使用して作成された各チャネルを明示的に閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e68e7-192">You must explicitly close each channel created using the listener.</span></span>  
  
### <a name="example"></a><span data-ttu-id="e68e7-193">例</span><span class="sxs-lookup"><span data-stu-id="e68e7-193">Example</span></span>  
 <span data-ttu-id="e68e7-194">次の例では、Employee テーブルに実行されるポーリング クエリを示します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-194">The following example shows a polling query that executes the Employee table.</span></span> <span data-ttu-id="e68e7-195">ポーリング ステートメントでは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-195">The polling statement performs the following tasks:</span></span>  
  
-   <span data-ttu-id="e68e7-196">Employee テーブルからすべてのレコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-196">Selects all the records from the Employee table.</span></span>  
  
-   <span data-ttu-id="e68e7-197">EmployeeHistory テーブルに、Employee テーブルからすべてのレコードを移動する MOVE_EMP_DATA ストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-197">Executes the MOVE_EMP_DATA stored procedure to move all records from Employee table to EmployeeHistory table.</span></span>  
  
-   <span data-ttu-id="e68e7-198">Employee テーブルに 1 つのレコードを追加する ADD_EMP_DETAILS ストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-198">Executes the ADD_EMP_DETAILS stored procedure to add a single record to the Employee table.</span></span>  
  
 <span data-ttu-id="e68e7-199">ポーリングのメッセージは保存`C:\PollingOutput.xml`です。</span><span class="sxs-lookup"><span data-stu-id="e68e7-199">The polling messages are saved at `C:\PollingOutput.xml`.</span></span>  
  
```  
using System;  
using Microsoft.Adapters.Sql;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
  
using System.Xml;  
  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Console.WriteLine("Sample started. This sample will poll 5 times and will perform the following tasks:");  
            Console.WriteLine("Press any key to start polling...");  
            Console.ReadLine();  
            IChannelListener<IInputChannel> listener = null;  
  
            IInputChannel channel = null;  
  
            try  
            {  
                TimeSpan messageTimeout = new TimeSpan(0, 0, 30);  
  
                SqlAdapterBinding binding = new SqlAdapterBinding();  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
                binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
  
                Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
  
                ClientCredentials credentials = new ClientCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                BindingParameterCollection bindingParams = new BindingParameterCollection();  
                bindingParams.Add(credentials);  
  
                listener = binding.BuildChannelListener<IInputChannel>(ConnectionUri, bindingParams);  
                listener.Open();  
  
                channel = listener.AcceptChannel();  
                channel.Open();  
  
                Console.WriteLine("Channel and Listener opened...");  
                Console.WriteLine("\nWaiting for polled data...");  
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
  
                    XmlDocument doc = new XmlDocument();  
                    doc.Load(reader);  
                    using (XmlWriter writer = XmlWriter.Create("C:\\PollingOutput.xml"))  
                    {  
                        doc.WriteTo(writer);  
                        Console.WriteLine("The polling response is saved at 'C:\\PollingOutput.xml'");  
                    }  
  
                    // return the cursor  
                    Console.WriteLine();  
  
                    // close the reader  
                    reader.Close();  
  
                    message.Close();  
                }  
                Console.WriteLine("\nPolling done -- hit <RETURN> to finish");  
                Console.ReadLine();  
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
  
## <a name="see-also"></a><span data-ttu-id="e68e7-200">参照</span><span class="sxs-lookup"><span data-stu-id="e68e7-200">See Also</span></span>  
[<span data-ttu-id="e68e7-201">WCF チャネル モデルを使用して SQL アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="e68e7-201">Develop SQL applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)