---
title: "厳密に型指定されたポーリング ベース データが変更されてから受信 WCF サービスのモデルを使用して SQL Server |Microsoft ドキュメント"
description: ".NET アプリケーションを使用して、型指定されたポーリングまたは WCF-SQL アダプターの BizTalk Server で WCF サービスを使用して、厳密に型指定されたポーリングを構成するには"
ms.custom: 
ms.date: 10/09/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b55eda71-1226-43f2-bc2f-e6b35563210b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c616d2a9f10aae5dbf822676174a0de0d4816c19
ms.sourcegitcommit: f9c6ea3c9cfb8a43f765c0d3b8b07dacaa21fc51
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2017
---
# <a name="receive-strongly-typed-polling-based-data-changed-messages-from-sql-server-using-wcf-service-model"></a><span data-ttu-id="e4072-103">厳密に型指定されたポーリング ベース データが変更されてから受信 WCF サービスのモデルを使用して SQL Server</span><span class="sxs-lookup"><span data-stu-id="e4072-103">Receive Strongly-typed Polling-based Data-changed Messages from SQL Server Using WCF Service Model</span></span>
<span data-ttu-id="e4072-104">構成することができます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server から厳密に型指定されたポーリング メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="e4072-104">You can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive strongly-typed polling messages from SQL Server.</span></span> <span data-ttu-id="e4072-105">データベースをポーリングするアダプターを実行するポーリング ステートメントを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="e4072-105">You can specify a polling statement that the adapter executes to poll the database.</span></span> <span data-ttu-id="e4072-106">ポーリング ステートメントには、SELECT ステートメントまたは結果セットを返すストアド プロシージャを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4072-106">The polling statement can be a SELECT statement or a stored procedure that returns a result set.</span></span> <span data-ttu-id="e4072-107">厳密に型指定された結果セットを受信するシナリオで、厳密に型指定されたポーリングを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4072-107">You must use strongly-typed polling in a scenario where you want to receive a strongly-typed result set.</span></span> <span data-ttu-id="e4072-108">アダプターが厳密に型指定されたポーリングをサポートする方法の詳細については、次を参照してください。[呼び出しをポーリングを使用して受信するためのサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)です。</span><span class="sxs-lookup"><span data-stu-id="e4072-108">For more information on how the adapter supports strongly-typed polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e4072-109">かどうかは、単一のアプリケーションに複数のポーリング操作を必要がありますを指定する、 **InboundID**接続一意にする URI の一部として接続プロパティです。</span><span class="sxs-lookup"><span data-stu-id="e4072-109">If you want to have more than one polling operation in a single application, you must specify an **InboundID** connection property as part of the connection URI to make it unique.</span></span> <span data-ttu-id="e4072-110">指定した受信 ID は、一意にする操作の名前空間に追加されます。</span><span class="sxs-lookup"><span data-stu-id="e4072-110">The inbound ID you specify is added to the operation namespace to make it unique.</span></span>  
  
## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="e4072-111">このトピックの内容がポーリングを示しています</span><span class="sxs-lookup"><span data-stu-id="e4072-111">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="e4072-112">このトピックの内容を示すため方法、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]メッセージの変更、.NET アプリケーションを作成およびの WCF サービス コントラクトを生成する厳密に型指定されたデータの受信をサポート、 **TypedPolling**操作します。</span><span class="sxs-lookup"><span data-stu-id="e4072-112">In this topic, to demonstrate how the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports receiving strongly-typed data change messages, create a .NET application and generate the WCF service contract for the **TypedPolling** operation.</span></span> <span data-ttu-id="e4072-113">WCF サービス コントラクトを生成するときに、次を指定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="e4072-113">Make sure you specify the following while generating the WCF service contract:</span></span>  
  
-   <span data-ttu-id="e4072-114">指定する必要があります、 **InboundID**接続 URI の一部として。</span><span class="sxs-lookup"><span data-stu-id="e4072-114">You must specify an **InboundID** as part of the connection URI.</span></span>  
  
-   <span data-ttu-id="e4072-115">ポーリング ステートメントを指定する必要があります、 **PollingStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="e4072-115">You must specify a polling statement for the **PollingStatement** binding property.</span></span>  
  
 <span data-ttu-id="e4072-116">さらに、その他を指定する場合は、ポーリング関連プロキシ クラスを生成中にバインディングのプロパティを指定して、 **PolledDataAvailableStatement**として。</span><span class="sxs-lookup"><span data-stu-id="e4072-116">Additionally, if you want to specify other polling related binding properties while generating the proxy class, specify the **PolledDataAvailableStatement** as:</span></span>  
  
```  
SELECT COUNT(*) FROM Employee  
```  
  
 <span data-ttu-id="e4072-117">**PolledDataAvailableStatement**正の値を含む最初のセルを含む結果セットを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4072-117">The **PolledDataAvailableStatement** must return a result set with the first cell containing a positive value.</span></span> <span data-ttu-id="e4072-118">最初のセルには正の値が含まれていない場合でも、アダプターでは、ポーリング ステートメントは実行されません。</span><span class="sxs-lookup"><span data-stu-id="e4072-118">If the first cell does not contain a positive value, the adapter does not execute the polling statement.</span></span>  
  
 <span data-ttu-id="e4072-119">ポーリング ステートメントの一部として、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e4072-119">As part of the polling statement, perform the following operations:</span></span>  
  
1.  <span data-ttu-id="e4072-120">Employee テーブルからすべての行を選択します。</span><span class="sxs-lookup"><span data-stu-id="e4072-120">Select all the rows from the Employee table.</span></span>  
  
2.  <span data-ttu-id="e4072-121">ストアド プロシージャ、EmployeeHistory テーブルには Employee テーブルからすべてのレコードを移動するには、(MOVE_EMP_DATA) を実行します。</span><span class="sxs-lookup"><span data-stu-id="e4072-121">Execute a stored procedure (MOVE_EMP_DATA) to move all the records from the Employee table to an EmployeeHistory table.</span></span>  
  
3.  <span data-ttu-id="e4072-122">Employee テーブルに新しいレコードを追加するには、(ADD_EMP_DETAILS) ストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="e4072-122">Execute a stored procedure (ADD_EMP_DETAILS) to add a new record to the Employee table.</span></span> <span data-ttu-id="e4072-123">この手順は、従業員名、指定、および給与をパラメーターとして受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e4072-123">This procedure takes the employee name, designation, and salary as parameters.</span></span>  
  
 <span data-ttu-id="e4072-124">これらの操作を実行するは、次を指定する必要があります、 **PollingStatement** WCF サービス コントラクトとヘルパー クラスを生成するときにプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="e4072-124">To perform these operations, you must specify the following for the **PollingStatement** binding property while generating the WCF service contract and helper classes:</span></span>  
  
```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  
  
 <span data-ttu-id="e4072-125">ポーリング ステートメントが実行された後に、Employee テーブルのすべてのレコードが選択されており、SQL Server からメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="e4072-125">After the polling statement is executed, all the records from the Employee table are selected and the message from SQL Server is received.</span></span> <span data-ttu-id="e4072-126">アダプターによって MOVE_EMP_DATA ストアド プロシージャの実行後は、すべてのレコードが EmployeeHistory テーブルに移動されます。</span><span class="sxs-lookup"><span data-stu-id="e4072-126">After the MOVE_EMP_DATA stored procedure is executed by the adapter, all the records are moved to the EmployeeHistory table.</span></span> <span data-ttu-id="e4072-127">次に、Employee テーブルに新しいレコードを追加する ADD_EMP_DETAILS ストアド プロシージャが実行されます。</span><span class="sxs-lookup"><span data-stu-id="e4072-127">Then, the ADD_EMP_DETAILS stored procedure is executed to add a new record to the Employee table.</span></span> <span data-ttu-id="e4072-128">次のポーリングの実行には、1 つのレコードだけを返します。</span><span class="sxs-lookup"><span data-stu-id="e4072-128">The next polling execution will only return a single record.</span></span> <span data-ttu-id="e4072-129">このサイクルは、サービス ホストを終了するまで続けられます。</span><span class="sxs-lookup"><span data-stu-id="e4072-129">This cycle continues until you close the service host.</span></span>  
  
## <a name="configuring-typed-polling-with-the-sql-adapter-binding-properties"></a><span data-ttu-id="e4072-130">SQL アダプターのプロパティをバインドに型指定されたポーリングを構成します。</span><span class="sxs-lookup"><span data-stu-id="e4072-130">Configuring Typed Polling with the SQL Adapter Binding Properties</span></span>  
 <span data-ttu-id="e4072-131">次の表、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドのプロパティ データの変更メッセージを受信するアダプターを構成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="e4072-131">The following table summarizes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding properties that you use to configure the adapter to receive data-change messages.</span></span> <span data-ttu-id="e4072-132">以外の場合、 **PollingStatement**バインディング プロパティでは、バインド プロパティをすべてここで示した必要な .NET アプリケーションの実行中にします。</span><span class="sxs-lookup"><span data-stu-id="e4072-132">Other than the **PollingStatement** binding property, all the other binding properties listed in this section are required while running the .NET application.</span></span> <span data-ttu-id="e4072-133">指定する必要があります、 **PollingStatement** WCF サービス コントラクトを生成する前にプロパティのバインド**TypedPolling**操作します。</span><span class="sxs-lookup"><span data-stu-id="e4072-133">You must specify the **PollingStatement** binding property before generating the WCF service contract **TypedPolling** operation.</span></span>  
  
|<span data-ttu-id="e4072-134">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="e4072-134">Binding Property</span></span>|<span data-ttu-id="e4072-135">Description</span><span class="sxs-lookup"><span data-stu-id="e4072-135">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="e4072-136">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="e4072-136">**InboundOperationType**</span></span>|<span data-ttu-id="e4072-137">実行するかどうかを指定します**ポーリング**、 **TypedPolling**、または**通知**操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="e4072-137">Specifies whether you want to perform **Polling**, **TypedPolling**, or **Notification** inbound operation.</span></span> <span data-ttu-id="e4072-138">既定値は**ポーリング**です。</span><span class="sxs-lookup"><span data-stu-id="e4072-138">Default is **Polling**.</span></span> <span data-ttu-id="e4072-139">厳密に型指定されたポーリング メッセージを受信するには、これを設定**TypedPolling**です。</span><span class="sxs-lookup"><span data-stu-id="e4072-139">To receive strongly-typed polling messages, set this to **TypedPolling**.</span></span>|  
|<span data-ttu-id="e4072-140">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="e4072-140">**PolledDataAvailableStatement**</span></span>|<span data-ttu-id="e4072-141">すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="e4072-141">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="e4072-142">SQL ステートメントには、結果の行と列で構成されるセットを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4072-142">The SQL statement must return a result set consisting of rows and columns.</span></span> <span data-ttu-id="e4072-143">SQL ステートメントが指定した行がある場合のみ、 **PollingStatement**プロパティのバインドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="e4072-143">Only if a row is available, the SQL statement specified for the **PollingStatement** binding property will be executed.</span></span>|  
|<span data-ttu-id="e4072-144">**PollingIntervalInSeconds**</span><span class="sxs-lookup"><span data-stu-id="e4072-144">**PollingIntervalInSeconds**</span></span>|<span data-ttu-id="e4072-145">秒単位で間隔を指定、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]の指定されたステートメントの実行、 **PolledDataAvailableStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="e4072-145">Specifies the interval, in seconds, at which the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="e4072-146">既定値は 30 秒です。</span><span class="sxs-lookup"><span data-stu-id="e4072-146">The default is 30 seconds.</span></span> <span data-ttu-id="e4072-147">ポーリング間隔では、連続するポーリングの間隔を決定します。</span><span class="sxs-lookup"><span data-stu-id="e4072-147">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="e4072-148">ステートメントは、指定した期間内で実行される、アダプターは、間隔の残り時間を待機します。</span><span class="sxs-lookup"><span data-stu-id="e4072-148">If the statement is executed within the specified interval, the adapter waits for the remaining time in the interval.</span></span>|  
|<span data-ttu-id="e4072-149">**PollingStatement**</span><span class="sxs-lookup"><span data-stu-id="e4072-149">**PollingStatement**</span></span>|<span data-ttu-id="e4072-150">SQL Server データベース テーブルをポーリングする SQL ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="e4072-150">Specifies the SQL statement to poll the SQL Server database table.</span></span> <span data-ttu-id="e4072-151">単純な SELECT ステートメントまたはストアド プロシージャのポーリング ステートメントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e4072-151">You can specify a simple SELECT statement or a stored procedure for the polling statement.</span></span> <span data-ttu-id="e4072-152">既定値は null です。</span><span class="sxs-lookup"><span data-stu-id="e4072-152">The default is null.</span></span> <span data-ttu-id="e4072-153">値を指定する必要があります**PollingStatement**ポーリングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e4072-153">You must specify a value for **PollingStatement** to enable polling.</span></span> <span data-ttu-id="e4072-154">ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="e4072-154">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="e4072-155">セミコロンで区切られた SQL ステートメントの任意の数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e4072-155">You can specify any number of SQL statements separated by a semi-colon.</span></span> <span data-ttu-id="e4072-156">**重要:**の**TypedPolling**メタデータを生成する前にこのバインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4072-156">**Important:**  For **TypedPolling**, you must specify this binding property before generating metadata.</span></span>|  
|<span data-ttu-id="e4072-157">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="e4072-157">**PollWhileDataFound**</span></span>|<span data-ttu-id="e4072-158">指定するかどうか、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ポーリング間隔を無視し、継続的に指定された SQL ステートメントを実行、 **PolledDataAvailableStatement**をポーリングするテーブルにデータがある場合、プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="e4072-158">Specifies whether the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ignores the polling interval and continuously executes the SQL statement specified for the **PolledDataAvailableStatement** binding property, if data is available in the table being polled.</span></span> <span data-ttu-id="e4072-159">テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔で SQL ステートメントを実行する元に戻します。</span><span class="sxs-lookup"><span data-stu-id="e4072-159">If no data is available in the table, the adapter reverts to execute the SQL statement at the specified polling interval.</span></span> <span data-ttu-id="e4072-160">既定値は**false**です。</span><span class="sxs-lookup"><span data-stu-id="e4072-160">Default is **false**.</span></span>|  
  
 <span data-ttu-id="e4072-161">これらのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="e4072-161">For a more complete description of these properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="e4072-162">使用する方法の詳細については、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL サーバーのポーリングを読みます。</span><span class="sxs-lookup"><span data-stu-id="e4072-162">For a complete description of how to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to poll SQL Server, read further.</span></span>  
  
## <a name="configure-strongly-typed-polling-in-the-wcf-service-model"></a><span data-ttu-id="e4072-163">WCF サービス モデルで厳密に型指定されたポーリングを構成します。</span><span class="sxs-lookup"><span data-stu-id="e4072-163">Configure Strongly-typed Polling in the WCF Service Model</span></span>  
 <span data-ttu-id="e4072-164">受信する、**ポーリング**WCF サービス モデルを使用して操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4072-164">To receive the **Polling** operation when you use the WCF service model, you must:</span></span>  
  
1.  <span data-ttu-id="e4072-165">WCF サービス コントラクト (インターフェイス) を生成、 **TypedPolling**アダプターによって公開されるメタデータから操作します。</span><span class="sxs-lookup"><span data-stu-id="e4072-165">Generate a WCF service contract (interface) for the **TypedPolling** operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="e4072-166">これを行うには、使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e4072-166">To do this, you could use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span> <span data-ttu-id="e4072-167">この例の WCF サービス コントラクトを生成するときに確認します。</span><span class="sxs-lookup"><span data-stu-id="e4072-167">While generating the WCF service contract for this example, make sure:</span></span>  
  
    -   <span data-ttu-id="e4072-168">指定する、 **InboundID**として**従業員**です。</span><span class="sxs-lookup"><span data-stu-id="e4072-168">You specify the **InboundID** as **Employee**.</span></span>  
  
    -   <span data-ttu-id="e4072-169">ポーリング ステートメントを指定する、 **PollingStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="e4072-169">You specify a polling statement for the **PollingStatement** binding property.</span></span> <span data-ttu-id="e4072-170">この例では、ポーリング ステートメントとして指定します。</span><span class="sxs-lookup"><span data-stu-id="e4072-170">For this example, specify the polling statement as:</span></span>  
  
        ```  
        SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000  
        ```  
  
2.  <span data-ttu-id="e4072-171">このインターフェイスから WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="e4072-171">Implement a WCF service from this interface.</span></span>  
  
3.  <span data-ttu-id="e4072-172">サービス ホストを使用してこの WCF サービスをホスト (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="e4072-172">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="e4072-173">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="e4072-173">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="e4072-174">このトピックの例では、Employee テーブルをポーリングします。</span><span class="sxs-lookup"><span data-stu-id="e4072-174">The examples in this topic poll the Employee table.</span></span> <span data-ttu-id="e4072-175">この例は、MOVE_EMP_DATA と ADD_EMP_DETAILS にも使用ストアド プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="e4072-175">The example also uses the MOVE_EMP_DATA and ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="e4072-176">これらの成果物を生成するスクリプトは、サンプルの値が提供されます。</span><span class="sxs-lookup"><span data-stu-id="e4072-176">A script to generate these artifacts is supplied with the samples.</span></span> <span data-ttu-id="e4072-177">サンプルの詳細については、次を参照してください。 [SQL アダプタ サンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="e4072-177">For more information about the samples, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span> <span data-ttu-id="e4072-178">サンプルは、 **TypedPolling_ServiceModel**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプルです。</span><span class="sxs-lookup"><span data-stu-id="e4072-178">A sample, **TypedPolling_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="e4072-179">WCF サービス コントラクトとクラス</span><span class="sxs-lookup"><span data-stu-id="e4072-179">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="e4072-180">使用することができます、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) およびサポートするためのクラスを作成する、 **TypedPolling**操作します。</span><span class="sxs-lookup"><span data-stu-id="e4072-180">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **TypedPolling** operation.</span></span> <span data-ttu-id="e4072-181">詳細については、WCF サービス コントラクトを生成する、次を参照してください。 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="e4072-181">For more information about generating a WCF service contract, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="e4072-182">WCF サービス コントラクト (インターフェイス)</span><span class="sxs-lookup"><span data-stu-id="e4072-182">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="e4072-183">次のコードに対して生成される WCF サービス コントラクト (インターフェイス) を示しています、 **TypedPolling**操作します。</span><span class="sxs-lookup"><span data-stu-id="e4072-183">The following code shows the WCF service contract (interface) generated for the **TypedPolling** operation.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/", ConfigurationName="TypedPolling_Employee")]  
public interface TypedPolling_Employee {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee) of message TypedPolling  
    // does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="TypedPolling")]  
    void TypedPolling(TypedPolling request);  
}  
```  
  
### <a name="the-message-contracts"></a><span data-ttu-id="e4072-184">メッセージ コントラクト</span><span class="sxs-lookup"><span data-stu-id="e4072-184">The Message Contracts</span></span>  
 <span data-ttu-id="e4072-185">メッセージ コントラクトの名前空間の変更では、 **InboundID**接続 URI を指定した場合のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="e4072-185">The message contract namespace is modified by the **InboundID** parameter in the connection URI, if specified.</span></span> <span data-ttu-id="e4072-186">この例でとして着信 ID を指定した**従業員**です。</span><span class="sxs-lookup"><span data-stu-id="e4072-186">In this example, you specified the inbound ID as **Employee**.</span></span> <span data-ttu-id="e4072-187">要求メッセージは、厳密に型指定された結果セットを返します。</span><span class="sxs-lookup"><span data-stu-id="e4072-187">The request message returns a strongly-typed result set.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="TypedPolling", WrapperNamespace="http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee", IsWrapped=true)]  
public partial class TypedPolling {  
  
[System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee", Order=0)]  
    public schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet0[] TypedPollingResultSet0;  
  
[System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee", Order=1)]  
    public schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet1[] TypedPollingResultSet1;  
  
    public TypedPolling() {  
    }  
  
    public TypedPolling(schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet0[] TypedPollingResultSet0, schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet1[] TypedPollingResultSet1) {  
        this.TypedPollingResultSet0 = TypedPollingResultSet0;  
        this.TypedPollingResultSet1 = TypedPollingResultSet1;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a><span data-ttu-id="e4072-188">WCF サービス クラス</span><span class="sxs-lookup"><span data-stu-id="e4072-188">WCF Service Class</span></span>  
 <span data-ttu-id="e4072-189">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をサービス コントラクト (インターフェイス) から実装、WCF サービス クラスのスタブを持つファイルも生成します。</span><span class="sxs-lookup"><span data-stu-id="e4072-189">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="e4072-190">ファイルの名前は、SqlAdapterBindingService.cs です。</span><span class="sxs-lookup"><span data-stu-id="e4072-190">The name of the file is SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="e4072-191">処理するロジックを挿入することができます、 **TypedPolling**このクラスに直接操作します。</span><span class="sxs-lookup"><span data-stu-id="e4072-191">You can insert the logic to process the **TypedPolling** operation directly into this class.</span></span> <span data-ttu-id="e4072-192">次のコードによって生成された WCF サービス クラスを示しています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e4072-192">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
```  
namespace SqlAdapterBindingNamespace {  
  
    public class SqlAdapterBindingService : TypedPolling_Employee {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee) of message TypedPolling  
        // does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
        public virtual void TypedPolling(TypedPolling request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receive-strongly-typed-inbound-messages-for-polling-operation"></a><span data-ttu-id="e4072-193">ポーリング操作の厳密に型指定されたメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="e4072-193">Receive Strongly-typed Inbound Messages for Polling Operation</span></span>  
 <span data-ttu-id="e4072-194">このセクションの内容を使用して受信ポーリングの厳密に型指定されたメッセージを受信する .NET アプリケーションを記述する方法の手順を説明する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e4072-194">This section provides instructions on how to write a .NET application to receive strongly-typed inbound polling messages using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
1.  <span data-ttu-id="e4072-195">使用して、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) およびためのヘルパー クラスを生成する、 **TypedPolling**操作します。</span><span class="sxs-lookup"><span data-stu-id="e4072-195">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **TypedPolling** operation.</span></span> <span data-ttu-id="e4072-196">この例の WCF サービス コントラクトを生成するときに、次を指定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="e4072-196">Make sure you specify the following while generating the WCF service contract for this example:</span></span>  
  
    -   <span data-ttu-id="e4072-197">指定する必要があります、 **InboundID**として**従業員**です。</span><span class="sxs-lookup"><span data-stu-id="e4072-197">You must specify the **InboundID** as **Employee**.</span></span>  
  
    -   <span data-ttu-id="e4072-198">ポーリング ステートメントを指定する必要があります、 **PollingStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="e4072-198">You must specify a polling statement for the **PollingStatement** binding property.</span></span> <span data-ttu-id="e4072-199">この例では、ポーリング ステートメントとして指定します。</span><span class="sxs-lookup"><span data-stu-id="e4072-199">For this example, specify the polling statement as:</span></span>  
  
        ```  
        SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000  
        ```  
  
     <span data-ttu-id="e4072-200">詳細については、次を参照してください。 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="e4072-200">For more information, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span> <span data-ttu-id="e4072-201">サービス コントラクトとヘルパー クラスを生成するときに、必要に応じてバインドのプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="e4072-201">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="e4072-202">これは、生成された構成ファイルで正しく設定されていることを保証します。</span><span class="sxs-lookup"><span data-stu-id="e4072-202">This guarantees that they are properly set in the generated configuration file.</span></span>  
  
2.  <span data-ttu-id="e4072-203">手順 1. で生成されたインターフェイスとヘルパー クラスからの WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="e4072-203">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="e4072-204">**TypedPolling**から受信したデータの処理エラーが発生した場合、このクラスのメソッドは、ポーリング トランザクションが中止例外をスローできます、 **TypedPolling**操作以外の場合、メソッドは何も返しません。</span><span class="sxs-lookup"><span data-stu-id="e4072-204">The **TypedPolling** method of this class can throw an exception to abort the polling transaction, if an error is encountered processing the data received from the **TypedPolling** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="e4072-205">次のように、WCF サービス クラスを属性する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4072-205">You must attribute the WCF service class as follows:</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
     <span data-ttu-id="e4072-206">内で、 **TypedPolling**メソッドを直接、アプリケーション ロジックを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="e4072-206">Within the **TypedPolling** method, you can implement your application logic directly.</span></span> <span data-ttu-id="e4072-207">このクラスは、SqlAdapterBindingService.cs で確認できます。</span><span class="sxs-lookup"><span data-stu-id="e4072-207">This class can be found in SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="e4072-208">この例では、このコードはサブ クラス、 **SqlAdapterBindingService**クラスです。</span><span class="sxs-lookup"><span data-stu-id="e4072-208">This code in this example sub-classes the **SqlAdapterBindingService** class.</span></span> <span data-ttu-id="e4072-209">このコードでは、厳密に型指定された結果セットとして受信したポーリング メッセージは、コンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="e4072-209">In this code, the polling message received as a strongly-typed result set is written to the console.</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
        public override void TypedPolling(TypedPolling request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Employee ID\tName\tDesignation\tSalary");  
  
            for (int i = 0; i < request.TypedPollingResultSet0.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.TypedPollingResultSet0[i].Employee_ID,  
                request.TypedPollingResultSet0[i].Name,  
                request.TypedPollingResultSet0[i].Designation,  
                request.TypedPollingResultSet0[i].Salary);  
            }  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("\nHit <RETURN> to stop polling");  
        }  
    }  
    ```  
  
3.  <span data-ttu-id="e4072-210">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]資格情報を受け入れません接続 URI の一部として、SQL Server データベースの資格情報を渡すには、次のクラスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4072-210">Because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not accept credentials as part of the connection URI, you must implement the following class to pass credentials for the SQL Server database.</span></span> <span data-ttu-id="e4072-211">アプリケーションの後半で、SQL Server 資格情報を渡すには、このクラスがインスタンス化されします。</span><span class="sxs-lookup"><span data-stu-id="e4072-211">In the latter part of the application, you will instantiate this class to pass on the SQL Server credentials.</span></span>  
  
    ```  
    class PollingCredentials : ClientCredentials, IServiceBehavior  
    {  
        public void AddBindingParameters(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase, Collection<ServiceEndpoint> endpoints, BindingParameterCollection bindingParameters)  
        {  
            bindingParameters.Add(this);  
        }  
  
        public void ApplyDispatchBehavior(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        public void Validate(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        protected override ClientCredentials CloneCore()  
        {  
            ClientCredentials clone = new PollingCredentials();  
            clone.UserName.UserName = this.UserName.UserName;  
            clone.UserName.Password = this.UserName.Password;  
            return clone;  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="e4072-212">作成、 **SqlAdapterBinding**とバインドのプロパティを指定することによって、ポーリング操作を構成します。</span><span class="sxs-lookup"><span data-stu-id="e4072-212">Create a **SqlAdapterBinding** and configure the polling operation by specifying the binding properties.</span></span> <span data-ttu-id="e4072-213">これは、コードで明示的にまたは構成で宣言によって行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e4072-213">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="e4072-214">指定する必要がありますには、少なくとも、 **InboundOperationType**、 **PolledDataAvailableStatement**、および**PollingStatement**です。</span><span class="sxs-lookup"><span data-stu-id="e4072-214">At a minimum, you must specify the **InboundOperationType**, **PolledDataAvailableStatement**, and **PollingStatement**.</span></span>  
  
    ```  
    SqlAdapterBinding binding = new SqlAdapterBinding();  
    binding.InboundOperationType = InboundOperation.TypedPolling;  
    binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
    binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
    ```  
  
5.  <span data-ttu-id="e4072-215">SQL Server データベース資格情報を指定するには、インスタンス化する、 **PollingCredentials**手順 3. で作成したクラスです。</span><span class="sxs-lookup"><span data-stu-id="e4072-215">Specify SQL Server database credentials by instantiating the **PollingCredentials** class you created in Step 3.</span></span>  
  
    ```  
    PollingCredentials credentials = new PollingCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
    ```  
  
6.  <span data-ttu-id="e4072-216">手順 2 で作成した WCF サービスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e4072-216">Create an instance of the WCF service created in step 2.</span></span>  
  
    ```  
    // create service instance  
    PollingService service = new PollingService();  
    ```  
  
7.  <span data-ttu-id="e4072-217">インスタンスを作成する**System.ServiceModel.ServiceHost** WCF サービスと基本接続 URI を使用しています。</span><span class="sxs-lookup"><span data-stu-id="e4072-217">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="e4072-218">基本の接続 URI は、着信 ID を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="e4072-218">The base connection URI cannot contain the inbound ID.</span></span> <span data-ttu-id="e4072-219">また、ここで、資格情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4072-219">You must also specify the credentials here.</span></span>  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
    ServiceHost serviceHost = new ServiceHost(service, baseUri);  
    serviceHost.Description.Behaviors.Add(credentials);  
  
    ```  
  
8.  <span data-ttu-id="e4072-220">サービス ホストにサービス エンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="e4072-220">Add a service endpoint to the service host.</span></span> <span data-ttu-id="e4072-221">これを行うには :</span><span class="sxs-lookup"><span data-stu-id="e4072-221">To do this:</span></span>  
  
    -   <span data-ttu-id="e4072-222">手順 4. で作成したバインディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4072-222">Use the binding created in step 4.</span></span>  
  
    -   <span data-ttu-id="e4072-223">接続の資格情報を含む URI を指定し、必要に応じて、入力方向の id。</span><span class="sxs-lookup"><span data-stu-id="e4072-223">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  
  
    -   <span data-ttu-id="e4072-224">"TypedPolling_Employee"としてコントラクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e4072-224">Specify the contract as "TypedPolling_Employee".</span></span>  
  
    ```  
    // Add service endpoint: be sure to specify TypedPolling_Employee as the contract  
    Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?InboundID=Employee");  
    serviceHost.AddServiceEndpoint("TypedPolling_Employee", binding, ConnectionUri);  
    ```  
  
9. <span data-ttu-id="e4072-225">ポーリングのデータを受信するには、サービス ホストを開きます。</span><span class="sxs-lookup"><span data-stu-id="e4072-225">To receive polling data, open the service host.</span></span> <span data-ttu-id="e4072-226">アダプターは、クエリが結果セットを返すときにデータを返します。</span><span class="sxs-lookup"><span data-stu-id="e4072-226">The adapter will return data whenever the query returns a result set.</span></span>  
  
    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  
  
10. <span data-ttu-id="e4072-227">ポーリングを終了するには、サービス ホストを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e4072-227">To terminate polling, close the service host.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e4072-228">アダプターは、サービス ホストが閉じられるまでポーリングを続行します。</span><span class="sxs-lookup"><span data-stu-id="e4072-228">The adapter will continue to poll until the service host is closed.</span></span>  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a><span data-ttu-id="e4072-229">例</span><span class="sxs-lookup"><span data-stu-id="e4072-229">Example</span></span>  
 <span data-ttu-id="e4072-230">次の例では、Employee テーブルに実行されるポーリング クエリを示します。</span><span class="sxs-lookup"><span data-stu-id="e4072-230">The following example shows a polling query that executes the Employee table.</span></span> <span data-ttu-id="e4072-231">ポーリング ステートメントでは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="e4072-231">The polling statement performs the following tasks:</span></span>  
  
1.  <span data-ttu-id="e4072-232">Employee テーブルからすべてのレコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4072-232">Selects all the records from the Employee table.</span></span>  
  
2.  <span data-ttu-id="e4072-233">EmployeeHistory テーブルに、Employee テーブルからすべてのレコードを移動する MOVE_EMP_DATA ストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="e4072-233">Executes the MOVE_EMP_DATA stored procedure to move all records from Employee table to EmployeeHistory table.</span></span>  
  
3.  <span data-ttu-id="e4072-234">Employee テーブルに 1 つのレコードを追加する ADD_EMP_DETAILS ストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="e4072-234">Executes the ADD_EMP_DETAILS stored procedure to add a single record to the Employee table.</span></span>  
  
 <span data-ttu-id="e4072-235">ポーリングの最初のメッセージは、Employee テーブルのすべてのレコードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e4072-235">The first polling message will contain all the records from the Employee table.</span></span> <span data-ttu-id="e4072-236">その後ポーリング メッセージ ADD_EMP_DETAILS ストアド プロシージャによって挿入された最後のレコードのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e4072-236">The subsequent polling messages will contain only the last record inserted by the ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="e4072-237">アダプターはポーリングを押して、サービス ホストを終了するまで引き続き`<RETURN>`します。</span><span class="sxs-lookup"><span data-stu-id="e4072-237">The adapter will continue to poll until you close the service host by pressing `<RETURN>`.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
using Microsoft.Adapters.Sql;  
using Microsoft.ServiceModel.Channels;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Collections.ObjectModel;  
  
namespace TypedPolling_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
        public override void TypedPolling(TypedPolling request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Employee ID\tName\tDesignation\tSalary");  
  
            for (int i = 0; i < request.TypedPollingResultSet0.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.TypedPollingResultSet0[i].Employee_ID,  
                request.TypedPollingResultSet0[i].Name,  
                request.TypedPollingResultSet0[i].Designation,  
                request.TypedPollingResultSet0[i].Salary);  
            }  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("\nHit <RETURN> to stop polling");  
        }  
    }  
  
    class PollingCredentials : ClientCredentials, IServiceBehavior  
    {  
        public void AddBindingParameters(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase, Collection<ServiceEndpoint> endpoints, BindingParameterCollection bindingParameters)  
        {  
            bindingParameters.Add(this);  
        }  
  
        public void ApplyDispatchBehavior(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        public void Validate(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        protected override ClientCredentials CloneCore()  
        {  
            ClientCredentials clone = new PollingCredentials();  
            clone.UserName.UserName = this.UserName.UserName;  
            clone.UserName.Password = this.UserName.Password;  
            return clone;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost serviceHost = null;  
            try  
            {  
                Console.WriteLine("Sample started...");  
                Console.WriteLine("Press any key to start polling...");  
                Console.ReadLine();  
  
                SqlAdapterBinding binding = new SqlAdapterBinding();  
                binding.InboundOperationType = InboundOperation.TypedPolling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
                binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
                Console.WriteLine("Binding properties assigned...");  
  
                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?InboundId=Employee");  
  
                // This URI is used to initialize the ServiceHost. It cannot contain  
                // the InboundID; otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
  
                PollingCredentials credentials = new PollingCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                Console.WriteLine("Opening service host...");  
                PollingService service = new PollingService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("TypedPolling_Employee", binding, ConnectionUri);  
                serviceHost.Open();  
                Console.WriteLine("Service host opened...");  
                Console.WriteLine("Polling started...");  
                Console.ReadLine();  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("Exception :" + e.Message);  
                Console.ReadLine();  
  
                /* If there is an error it will be specified in the inner exception */  
                if (e.InnerException != null)  
                {  
                    Console.WriteLine("InnerException: " + e.InnerException.Message);  
                    Console.ReadLine();  
                }  
            }  
            finally  
            {  
                // IMPORTANT: you must close the ServiceHost to stop polling  
                if (serviceHost.State == CommunicationState.Opened)  
                    serviceHost.Close();  
                else  
                    serviceHost.Abort();  
            }  
        }  
    }  
}  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="e4072-238">参照</span><span class="sxs-lookup"><span data-stu-id="e4072-238">See Also</span></span>  
 [<span data-ttu-id="e4072-239">WCF サービス モデルで、SQL アダプターを使用して SQL サーバーにポーリング</span><span class="sxs-lookup"><span data-stu-id="e4072-239">Poll SQL Server using the SQL Adapter with WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)
