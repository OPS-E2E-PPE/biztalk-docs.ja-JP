---
title: "WCF サービス モデルを使用して SQL Server からデータ変更のポーリングに基づいたメッセージを受信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8713dd38-65ff-4d89-b23b-a93c06c5ff22
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ff5ca099733a59fc5aa64c9ebbe261375f1a488
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="receive-polling-based-data-changed-messages-from-sql-server-using-the-wcf-service-model"></a><span data-ttu-id="e2448-102">WCF サービス モデルを使用して SQL Server からのデータ変更のポーリングに基づいたメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="e2448-102">Receive Polling-based Data-changed Messages from SQL Server Using the WCF Service Model</span></span>
<span data-ttu-id="e2448-103">構成することができます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server のテーブルまたはビューのデータの定期的な変更メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="e2448-103">You can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive periodic data-change messages for SQL Server tables or views.</span></span> <span data-ttu-id="e2448-104">データベースをポーリングするアダプターを実行するポーリング ステートメントを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="e2448-104">You can specify a polling statement that the adapter executes to poll the database.</span></span> <span data-ttu-id="e2448-105">ポーリング ステートメントには、SELECT ステートメントまたは結果セットを返すストアド プロシージャを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2448-105">The polling statement can be a SELECT statement or a stored procedure that returns a result set.</span></span>  
  
 <span data-ttu-id="e2448-106">アダプターがポーリングをサポートする方法の詳細については、次を参照してください。 [SQL アダプタを使用して SQL Server でのポーリング](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="e2448-106">For more information on how the adapter supports polling, see [Polling in SQL Server using the SQL adapter](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2448-107">このトピックを使用する方法を示します、**ポーリング**ポーリング メッセージを使用する操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="e2448-107">This topic demonstrates how to use the **Polling** inbound operation to use polling messages.</span></span> <span data-ttu-id="e2448-108">ポーリング操作のメッセージがない厳密に型指定します。</span><span class="sxs-lookup"><span data-stu-id="e2448-108">The message for the Polling operation is not strongly-typed.</span></span> <span data-ttu-id="e2448-109">使用する必要がありますを厳密に型指定されたポーリング メッセージを取得する場合、 **TypedPolling**操作します。</span><span class="sxs-lookup"><span data-stu-id="e2448-109">If you want to get strongly-typed polling message, you must use the **TypedPolling** operation.</span></span> <span data-ttu-id="e2448-110">使用することも必要があります、 **TypedPolling**工程に単一のアプリケーションで複数の操作をポーリングします。</span><span class="sxs-lookup"><span data-stu-id="e2448-110">You must also use the **TypedPolling** operation to have multiple polling operations in a single application.</span></span> <span data-ttu-id="e2448-111">実行する方法の詳細について**TypedPolling**操作を参照してください[SQL Server を使用して WCF サービス モデルからデータ変更のポーリングに基づいたメッセージを受信厳密に型指定された](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-sql-messages-with-wcf-service.md)です。</span><span class="sxs-lookup"><span data-stu-id="e2448-111">For instructions on how to perform **TypedPolling** operation, see [Receive Strongly-typed Polling-based Data-changed Messages from SQL Server Using WCF Service Model](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-sql-messages-with-wcf-service.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e2448-112">かどうかは、単一のアプリケーションに複数のポーリング操作を必要がありますを指定する、 **InboundID**接続一意にする URI の一部として接続プロパティです。</span><span class="sxs-lookup"><span data-stu-id="e2448-112">If you want to have more than one polling operation in a single application, you must specify an **InboundID** connection property as part of the connection URI to make it unique.</span></span> <span data-ttu-id="e2448-113">指定した受信 ID は、一意にする操作の名前空間に追加されます。</span><span class="sxs-lookup"><span data-stu-id="e2448-113">The inbound ID you specify is added to the operation namespace to make it unique.</span></span>  
  
## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="e2448-114">このトピックの内容がポーリングを示しています</span><span class="sxs-lookup"><span data-stu-id="e2448-114">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="e2448-115">このトピックの内容を示すため方法、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]メッセージの変更、.NET アプリケーションを作成およびの WCF サービス コントラクトを生成するデータの受信をサポート、**ポーリング**操作します。</span><span class="sxs-lookup"><span data-stu-id="e2448-115">In this topic, to demonstrate how the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports receiving data change messages, create a .NET application and generate the WCF service contract for the **Polling** operation.</span></span> <span data-ttu-id="e2448-116">ポーリングを指定する場合は、関連するバインドのプロパティを WCF サービス コントラクトを生成するときに、指定、 **PolledDataAvailableStatement**として。</span><span class="sxs-lookup"><span data-stu-id="e2448-116">If you want to specify the polling related binding properties while generating the WCF service contract, specify the **PolledDataAvailableStatement** as:</span></span>  
  
```  
SELECT COUNT(*) FROM Employee  
```  
  
 <span data-ttu-id="e2448-117">**PolledDataAvailableStatement**正の値を含む最初のセルを含む結果セットを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2448-117">The **PolledDataAvailableStatement** must return a result set with the first cell containing a positive value.</span></span> <span data-ttu-id="e2448-118">最初のセルには正の値が含まれていない場合でも、アダプターでは、ポーリング ステートメントは実行されません。</span><span class="sxs-lookup"><span data-stu-id="e2448-118">If the first cell does not contain a positive value, the adapter does not execute the polling statement.</span></span>  
  
 <span data-ttu-id="e2448-119">ポーリング ステートメントの一部として、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e2448-119">As part of the polling statement, perform the following operations:</span></span>  
  
1.  <span data-ttu-id="e2448-120">Employee テーブルからすべての行を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2448-120">Select all the rows from the Employee table.</span></span>  
  
2.  <span data-ttu-id="e2448-121">ストアド プロシージャ、EmployeeHistory テーブルには Employee テーブルからすべてのレコードを移動するには、(MOVE_EMP_DATA) を実行します。</span><span class="sxs-lookup"><span data-stu-id="e2448-121">Execute a stored procedure (MOVE_EMP_DATA) to move all the records from the Employee table to an EmployeeHistory table.</span></span>  
  
3.  <span data-ttu-id="e2448-122">Employee テーブルに新しいレコードを追加するには、(ADD_EMP_DETAILS) ストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2448-122">Execute a stored procedure (ADD_EMP_DETAILS) to add a new record to the Employee table.</span></span> <span data-ttu-id="e2448-123">この手順は、従業員名、指定、および給与をパラメーターとして受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e2448-123">This procedure takes the employee name, designation, and salary as parameters.</span></span>  
  
 <span data-ttu-id="e2448-124">これらの操作を実行するは、次を指定する必要があります、 **PollingStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="e2448-124">To perform these operations, you must specify the following for the **PollingStatement** binding property:</span></span>  
  
```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  
  
 <span data-ttu-id="e2448-125">ポーリング ステートメントが実行された後に、Employee テーブルのすべてのレコードが選択されており、SQL Server からメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="e2448-125">After the polling statement is executed, all the records from the Employee table are selected and the message from SQL Server is received.</span></span> <span data-ttu-id="e2448-126">アダプターによって MOVE_EMP_DATA ストアド プロシージャの実行後は、すべてのレコードが EmployeeHistory テーブルに移動されます。</span><span class="sxs-lookup"><span data-stu-id="e2448-126">After the MOVE_EMP_DATA stored procedure is executed by the adapter, all the records are moved to the EmployeeHistory table.</span></span> <span data-ttu-id="e2448-127">次に、Employee テーブルに新しいレコードを追加する ADD_EMP_DETAILS ストアド プロシージャが実行されます。</span><span class="sxs-lookup"><span data-stu-id="e2448-127">Then, the ADD_EMP_DETAILS stored procedure is executed to add a new record to the Employee table.</span></span> <span data-ttu-id="e2448-128">次のポーリングの実行には、1 つのレコードだけを返します。</span><span class="sxs-lookup"><span data-stu-id="e2448-128">The next polling execution will only return a single record.</span></span> <span data-ttu-id="e2448-129">このサイクルは、サービス ホストを終了するまで続けられます。</span><span class="sxs-lookup"><span data-stu-id="e2448-129">This cycle continues until you close the service host.</span></span>  
  
## <a name="configuring-a-polling-query-with-the-sql-adapter-binding-properties"></a><span data-ttu-id="e2448-130">SQL アダプターのプロパティのバインドと、ポーリング クエリの構成</span><span class="sxs-lookup"><span data-stu-id="e2448-130">Configuring a Polling Query with the SQL Adapter Binding Properties</span></span>  
 <span data-ttu-id="e2448-131">次の表、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドのプロパティ データの変更メッセージを受信するアダプターを構成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="e2448-131">The following table summarizes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding properties that you use to configure the adapter to receive data-change messages.</span></span> <span data-ttu-id="e2448-132">ポーリングに使用できる .NET アプリケーションの一部としてこれらのバインディング プロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2448-132">You must specify these binding properties as part of the .NET application for polling.</span></span>  
  
|<span data-ttu-id="e2448-133">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="e2448-133">Binding Property</span></span>|<span data-ttu-id="e2448-134">Description</span><span class="sxs-lookup"><span data-stu-id="e2448-134">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="e2448-135">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="e2448-135">**InboundOperationType**</span></span>|<span data-ttu-id="e2448-136">実行するかどうかを指定します**ポーリング**、 **TypedPolling**、または**通知**操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="e2448-136">Specifies whether you want to perform **Polling**, **TypedPolling**, or **Notification** inbound operation.</span></span> <span data-ttu-id="e2448-137">既定値は**ポーリング**です。</span><span class="sxs-lookup"><span data-stu-id="e2448-137">Default is **Polling**.</span></span>|  
|<span data-ttu-id="e2448-138">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="e2448-138">**PolledDataAvailableStatement**</span></span>|<span data-ttu-id="e2448-139">すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="e2448-139">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="e2448-140">SQL ステートメントには、結果の行と列で構成されるセットを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2448-140">The SQL statement must return a result set consisting of rows and columns.</span></span> <span data-ttu-id="e2448-141">SQL ステートメントが指定した行がある場合のみ、 **PollingStatement**プロパティのバインドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="e2448-141">Only if a row is available, the SQL statement specified for the **PollingStatement** binding property will be executed.</span></span>|  
|<span data-ttu-id="e2448-142">**PollingIntervalInSeconds**</span><span class="sxs-lookup"><span data-stu-id="e2448-142">**PollingIntervalInSeconds**</span></span>|<span data-ttu-id="e2448-143">秒単位で間隔を指定、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]の指定されたステートメントの実行、 **PolledDataAvailableStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="e2448-143">Specifies the interval, in seconds, at which the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="e2448-144">既定値は 30 秒です。</span><span class="sxs-lookup"><span data-stu-id="e2448-144">The default is 30 seconds.</span></span> <span data-ttu-id="e2448-145">ポーリング間隔では、連続するポーリングの間隔を決定します。</span><span class="sxs-lookup"><span data-stu-id="e2448-145">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="e2448-146">ステートメントは、指定した期間内で実行される、アダプターは、間隔の残り時間を待機します。</span><span class="sxs-lookup"><span data-stu-id="e2448-146">If the statement is executed within the specified interval, the adapter waits for the remaining time in the interval.</span></span>|  
|<span data-ttu-id="e2448-147">**PollingStatement**</span><span class="sxs-lookup"><span data-stu-id="e2448-147">**PollingStatement**</span></span>|<span data-ttu-id="e2448-148">SQL Server データベース テーブルをポーリングする SQL ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="e2448-148">Specifies the SQL statement to poll the SQL Server database table.</span></span> <span data-ttu-id="e2448-149">単純な SELECT ステートメントまたはストアド プロシージャのポーリング ステートメントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e2448-149">You can specify a simple SELECT statement or a stored procedure for the polling statement.</span></span> <span data-ttu-id="e2448-150">既定値は null です。</span><span class="sxs-lookup"><span data-stu-id="e2448-150">The default is null.</span></span> <span data-ttu-id="e2448-151">値を指定する必要があります**PollingStatement**ポーリングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e2448-151">You must specify a value for **PollingStatement** to enable polling.</span></span> <span data-ttu-id="e2448-152">ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="e2448-152">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="e2448-153">セミコロンで区切られた SQL ステートメントの任意の数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e2448-153">You can specify any number of SQL statements separated by a semi-colon.</span></span>|  
|<span data-ttu-id="e2448-154">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="e2448-154">**PollWhileDataFound**</span></span>|<span data-ttu-id="e2448-155">指定するかどうか、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ポーリング間隔を無視し、継続的に指定された SQL ステートメントを実行、 **PolledDataAvailableStatement**をポーリングするテーブルにデータがある場合、プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="e2448-155">Specifies whether the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ignores the polling interval and continuously executes the SQL statement specified for the **PolledDataAvailableStatement** binding property, if data is available in the table being polled.</span></span> <span data-ttu-id="e2448-156">テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔で SQL ステートメントを実行する元に戻します。</span><span class="sxs-lookup"><span data-stu-id="e2448-156">If no data is available in the table, the adapter reverts to execute the SQL statement at the specified polling interval.</span></span> <span data-ttu-id="e2448-157">既定値は**false**です。</span><span class="sxs-lookup"><span data-stu-id="e2448-157">Default is **false**.</span></span>|  
  
 <span data-ttu-id="e2448-158">これらのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="e2448-158">For a more complete description of these properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="e2448-159">使用する方法の詳細については、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL サーバーのポーリングを読みます。</span><span class="sxs-lookup"><span data-stu-id="e2448-159">For a complete description of how to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to poll SQL Server, read further.</span></span>  
  
## <a name="configuring-polling-in-the-wcf-service-model"></a><span data-ttu-id="e2448-160">WCF サービス モデルでのポーリングを構成します。</span><span class="sxs-lookup"><span data-stu-id="e2448-160">Configuring Polling in the WCF Service Model</span></span>  
 <span data-ttu-id="e2448-161">受信する、**ポーリング**WCF サービス モデルを使用して操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2448-161">To receive the **Polling** operation when you use the WCF service model, you must:</span></span>  
  
1.  <span data-ttu-id="e2448-162">WCF サービス コントラクト (インターフェイス) を生成、**ポーリング**アダプターによって公開されるメタデータから操作します。</span><span class="sxs-lookup"><span data-stu-id="e2448-162">Generate a WCF service contract (interface) for the **Polling** operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="e2448-163">これを行うには、使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e2448-163">To do this, you could use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span>  
  
2.  <span data-ttu-id="e2448-164">このインターフェイスから WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="e2448-164">Implement a WCF service from this interface.</span></span>  
  
3.  <span data-ttu-id="e2448-165">サービス ホストを使用してこの WCF サービスをホスト (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="e2448-165">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="e2448-166">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="e2448-166">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="e2448-167">このトピックの例では、Employee テーブルをポーリングします。</span><span class="sxs-lookup"><span data-stu-id="e2448-167">The examples in this topic poll the Employee table.</span></span> <span data-ttu-id="e2448-168">この例は、MOVE_EMP_DATA と ADD_EMP_DETAILS にも使用ストアド プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="e2448-168">The example also uses the MOVE_EMP_DATA and ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="e2448-169">これらの成果物を生成するスクリプトは、サンプルの値が提供されます。</span><span class="sxs-lookup"><span data-stu-id="e2448-169">A script to generate these artifacts is supplied with the samples.</span></span> <span data-ttu-id="e2448-170">サンプルの詳細については、次を参照してください。 [SQL アダプタ サンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="e2448-170">For more information about the samples, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span> <span data-ttu-id="e2448-171">サンプルは、 **Polling_ServiceModel**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプルです。</span><span class="sxs-lookup"><span data-stu-id="e2448-171">A sample, **Polling_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="e2448-172">WCF サービス コントラクトとクラス</span><span class="sxs-lookup"><span data-stu-id="e2448-172">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="e2448-173">使用することができます、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) およびサポートするためのクラスを作成する、**ポーリング**操作します。</span><span class="sxs-lookup"><span data-stu-id="e2448-173">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **Polling** operation.</span></span> <span data-ttu-id="e2448-174">詳細については、WCF サービス コントラクトを生成する、次を参照してください。 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="e2448-174">For more information about generating a WCF service contract, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="e2448-175">WCF サービス コントラクト (インターフェイス)</span><span class="sxs-lookup"><span data-stu-id="e2448-175">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="e2448-176">次のコードに対して生成される WCF サービス コントラクト (インターフェイス) を示しています、**ポーリング**操作します。</span><span class="sxs-lookup"><span data-stu-id="e2448-176">The following code shows the WCF service contract (interface) generated for the **Polling** operation.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/", ConfigurationName="PollingOperation")]  
public interface PollingOperation {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/Polling/) of message Polling  
    // does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="Polling")]  
    [System.ServiceModel.XmlSerializerFormatAttribute()]  
    void Polling(Polling request);  
}  
```  
  
### <a name="the-message-contracts"></a><span data-ttu-id="e2448-177">メッセージ コントラクト</span><span class="sxs-lookup"><span data-stu-id="e2448-177">The Message Contracts</span></span>  
 <span data-ttu-id="e2448-178">メッセージ コントラクトの名前空間の変更では、 **InboundID**接続 URI を指定した場合のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="e2448-178">The message contract namespace is modified by the **InboundID** parameter in the connection URI, if specified.</span></span> <span data-ttu-id="e2448-179">この例では、接続 URI の入力方向の ID を指定されていません。</span><span class="sxs-lookup"><span data-stu-id="e2448-179">In this example, you did not specify an inbound ID in the connection URI.</span></span> <span data-ttu-id="e2448-180">要求メッセージは、データセットを返します。</span><span class="sxs-lookup"><span data-stu-id="e2448-180">The request message returns a DataSet.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Polling", WrapperNamespace="http://schemas.microsoft.com/Sql/2008/05/Polling/", IsWrapped=true)]  
public partial class Polling {  
  
[System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/Polling/", Order=0)]  
    [System.Xml.Serialization.XmlArrayAttribute(IsNullable=true)]  
    [System.Xml.Serialization.XmlArrayItemAttribute("DataSet", Namespace="http://schemas.datacontract.org/2004/07/System.Data", IsNullable=false)]  
    public System.Data.DataSet[] PolledData;  
  
    public Polling() {  
    }  
  
    public Polling(System.Data.DataSet[] PolledData) {  
        this.PolledData = PolledData;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a><span data-ttu-id="e2448-181">WCF サービス クラス</span><span class="sxs-lookup"><span data-stu-id="e2448-181">WCF Service Class</span></span>  
 <span data-ttu-id="e2448-182">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をサービス コントラクト (インターフェイス) から実装、WCF サービス クラスのスタブを持つファイルも生成します。</span><span class="sxs-lookup"><span data-stu-id="e2448-182">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="e2448-183">ファイルの名前は、SqlAdapterBindingService.cs です。</span><span class="sxs-lookup"><span data-stu-id="e2448-183">The name of the file is SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="e2448-184">処理するロジックを挿入することができます、**ポーリング**このクラスに直接操作します。</span><span class="sxs-lookup"><span data-stu-id="e2448-184">You can insert the logic to process the **Polling** operation directly into this class.</span></span> <span data-ttu-id="e2448-185">次のコードによって生成された WCF サービス クラスを示しています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e2448-185">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
```  
namespace SqlAdapterBindingNamespace {  
  
    public class SqlAdapterBindingService : PollingOperation {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/Polling/) of message Polling   
        // does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
        public virtual void Polling(Polling request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-inbound-messages-for-polling-operation"></a><span data-ttu-id="e2448-186">ポーリング操作の着信メッセージを受信</span><span class="sxs-lookup"><span data-stu-id="e2448-186">Receiving Inbound Messages for Polling Operation</span></span>  
 <span data-ttu-id="e2448-187">このセクションの内容を使用してポーリングの受信メッセージを受信する .NET アプリケーションを記述する方法の手順を説明する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e2448-187">This section provides instructions on how to write a .NET application to receive inbound polling messages using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
#### <a name="to-receive-polling-messages-from-the-sql-adapter"></a><span data-ttu-id="e2448-188">SQL アダプタからポーリング メッセージを受信するには</span><span class="sxs-lookup"><span data-stu-id="e2448-188">To receive polling messages from the SQL adapter</span></span>  
  
1.  <span data-ttu-id="e2448-189">使用して、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) およびためのヘルパー クラスを生成する、**ポーリング**操作します。</span><span class="sxs-lookup"><span data-stu-id="e2448-189">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **Polling** operation.</span></span> <span data-ttu-id="e2448-190">詳細については、次を参照してください。 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="e2448-190">For more information, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span> <span data-ttu-id="e2448-191">サービス コントラクトとヘルパー クラスを生成するときに、必要に応じてバインドのプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="e2448-191">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="e2448-192">これは、生成された構成ファイルで正しく設定されていることを保証します。</span><span class="sxs-lookup"><span data-stu-id="e2448-192">This guarantees that they are properly set in the generated configuration file.</span></span>  
  
2.  <span data-ttu-id="e2448-193">手順 1. で生成されたインターフェイスとヘルパー クラスからの WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="e2448-193">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="e2448-194">**ポーリング**から受信したデータの処理エラーが発生した場合、このクラスのメソッドは、ポーリング トランザクションが中止例外をスローできます、**ポーリング**操作ですそれ以外の場合、メソッドは。何も返しません。</span><span class="sxs-lookup"><span data-stu-id="e2448-194">The **Polling** method of this class can throw an exception to abort the polling transaction, if an error is encountered processing the data received from the **Polling** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="e2448-195">次のように、WCF サービス クラスを属性する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2448-195">You must attribute the WCF service class as follows:</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
     <span data-ttu-id="e2448-196">内で、**ポーリング**メソッドを直接、アプリケーション ロジックを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="e2448-196">Within the **Polling** method, you can implement your application logic directly.</span></span> <span data-ttu-id="e2448-197">このクラスは、SqlAdapterBindingService.cs で確認できます。</span><span class="sxs-lookup"><span data-stu-id="e2448-197">This class can be found in SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="e2448-198">この例では、このコードはサブ クラス、 **SqlAdapterBindingService**クラスです。</span><span class="sxs-lookup"><span data-stu-id="e2448-198">This code in this example sub-classes the **SqlAdapterBindingService** class.</span></span> <span data-ttu-id="e2448-199">このコードでは、データセットとして受信したポーリング メッセージは、コンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="e2448-199">In this code, the polling message received as a DataSet is written to the console.</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
  
    public override void Polling(Polling request)  
    {  
        Console.WriteLine("\nNew Polling Records Received");  
        Console.WriteLine("*************************************************");  
        DataSet[] dataArray = request.PolledData;  
        foreach (DataTable tab in dataArray[0].Tables)  
        {  
            foreach (DataRow row in tab.Rows)  
            {  
                for (int i = 0; i < tab.Columns.Count; i++)  
                {  
                    Console.WriteLine(row[i]);  
                }  
            }  
        }  
        Console.WriteLine("*************************************************");  
        Console.WriteLine("\nHit <RETURN> to stop polling");  
        }  
    }  
    ```  
  
3.  <span data-ttu-id="e2448-200">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]資格情報を受け入れません接続 URI の一部として、SQL Server データベースの資格情報を渡すには、次のクラスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2448-200">Because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not accept credentials as part of the connection URI, you must implement the following class to pass credentials for the SQL Server database.</span></span> <span data-ttu-id="e2448-201">アプリケーションの後半で、SQL Server 資格情報を渡すには、このクラスがインスタンス化されします。</span><span class="sxs-lookup"><span data-stu-id="e2448-201">In the latter part of the application, you will instantiate this class to pass on the SQL Server credentials.</span></span>  
  
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
  
4.  <span data-ttu-id="e2448-202">作成、 **SqlAdapterBinding**とバインドのプロパティを指定することによって、ポーリング操作を構成します。</span><span class="sxs-lookup"><span data-stu-id="e2448-202">Create a **SqlAdapterBinding** and configure the polling operation by specifying the binding properties.</span></span> <span data-ttu-id="e2448-203">これは、コードで明示的にまたは構成で宣言によって行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e2448-203">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="e2448-204">指定する必要がありますには、少なくとも、 **InboundOperationType**、 **PolledDataAvailableStatement**、および**PollingStatement**です。</span><span class="sxs-lookup"><span data-stu-id="e2448-204">At a minimum, you must specify the **InboundOperationType**, **PolledDataAvailableStatement**, and **PollingStatement**.</span></span>  
  
    ```  
    SqlAdapterBinding binding = new SqlAdapterBinding();  
    binding.InboundOperationType = InboundOperation.Polling;  
    binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
    binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
    ```  
  
5.  <span data-ttu-id="e2448-205">SQL Server データベース資格情報を指定するには、インスタンス化する、 **PollingCredentials**手順 3. で作成したクラスです。</span><span class="sxs-lookup"><span data-stu-id="e2448-205">Specify SQL Server database credentials by instantiating the **PollingCredentials** class you created in Step 3.</span></span>  
  
    ```  
    PollingCredentials credentials = new PollingCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
    ```  
  
6.  <span data-ttu-id="e2448-206">手順 2 で作成した WCF サービスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e2448-206">Create an instance of the WCF service created in step 2.</span></span>  
  
    ```  
    // create service instance  
    PollingService service = new PollingService();  
    ```  
  
7.  <span data-ttu-id="e2448-207">インスタンスを作成する**System.ServiceModel.ServiceHost** WCF サービスと基本接続 URI を使用しています。</span><span class="sxs-lookup"><span data-stu-id="e2448-207">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="e2448-208">基本の接続 URI は、指定されている場合、受信の ID を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="e2448-208">The base connection URI cannot contain the inbound ID, if specified.</span></span> <span data-ttu-id="e2448-209">また、ここで、資格情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2448-209">You should also specify the credentials here.</span></span>  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
    ServiceHost serviceHost = new ServiceHost(service, baseUri);  
    serviceHost.Description.Behaviors.Add(credentials);  
  
    ```  
  
8.  <span data-ttu-id="e2448-210">サービス ホストにサービス エンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="e2448-210">Add a service endpoint to the service host.</span></span> <span data-ttu-id="e2448-211">これを行うには :</span><span class="sxs-lookup"><span data-stu-id="e2448-211">To do this:</span></span>  
  
    -   <span data-ttu-id="e2448-212">手順 4. で作成したバインディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2448-212">Use the binding created in step 4.</span></span>  
  
    -   <span data-ttu-id="e2448-213">接続の資格情報を含む URI を指定し、必要に応じて、入力方向の id。</span><span class="sxs-lookup"><span data-stu-id="e2448-213">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  
  
    -   <span data-ttu-id="e2448-214">"PollingOperation"としてコントラクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e2448-214">Specify the contract as "PollingOperation".</span></span>  
  
    ```  
    // Add service endpoint: be sure to specify PollingOperation as the contract  
    Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
    serviceHost.AddServiceEndpoint("PollingOperation", binding, ConnectionUri);  
    ```  
  
9. <span data-ttu-id="e2448-215">ポーリングのデータを受信するには、サービス ホストを開きます。</span><span class="sxs-lookup"><span data-stu-id="e2448-215">To receive polling data, open the service host.</span></span> <span data-ttu-id="e2448-216">アダプターは、クエリが結果セットを返すときにデータを返します。</span><span class="sxs-lookup"><span data-stu-id="e2448-216">The adapter will return data whenever the query returns a result set.</span></span>  
  
    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  
  
10. <span data-ttu-id="e2448-217">ポーリングを終了するには、サービス ホストを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e2448-217">To terminate polling, close the service host.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e2448-218">アダプターは、サービス ホストが閉じられるまでポーリングを続行します。</span><span class="sxs-lookup"><span data-stu-id="e2448-218">The adapter will continue to poll until the service host is closed.</span></span>  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a><span data-ttu-id="e2448-219">例</span><span class="sxs-lookup"><span data-stu-id="e2448-219">Example</span></span>  
 <span data-ttu-id="e2448-220">次の例では、Employee テーブルに実行されるポーリング クエリを示します。</span><span class="sxs-lookup"><span data-stu-id="e2448-220">The following example shows a polling query that executes the Employee table.</span></span> <span data-ttu-id="e2448-221">ポーリング ステートメントでは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2448-221">The polling statement performs the following tasks:</span></span>  
  
1.  <span data-ttu-id="e2448-222">Employee テーブルからすべてのレコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2448-222">Selects all the records from the Employee table.</span></span>  
  
2.  <span data-ttu-id="e2448-223">EmployeeHistory テーブルに、Employee テーブルからすべてのレコードを移動する MOVE_EMP_DATA ストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2448-223">Executes the MOVE_EMP_DATA stored procedure to move all records from Employee table to EmployeeHistory table.</span></span>  
  
3.  <span data-ttu-id="e2448-224">Employee テーブルに 1 つのレコードを追加する ADD_EMP_DETAILS ストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2448-224">Executes the ADD_EMP_DETAILS stored procedure to add a single record to the Employee table.</span></span>  
  
 <span data-ttu-id="e2448-225">ポーリングの最初のメッセージは、Employee テーブルのすべてのレコードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e2448-225">The first polling message will contain all the records from the Employee table.</span></span> <span data-ttu-id="e2448-226">その後ポーリング メッセージ ADD_EMP_DETAILS ストアド プロシージャによって挿入された最後のレコードのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e2448-226">The subsequent polling messages will contain only the last record inserted by the ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="e2448-227">アダプターはポーリングを押して、サービス ホストを終了するまで引き続き`<RETURN>`します。</span><span class="sxs-lookup"><span data-stu-id="e2448-227">The adapter will continue to poll until you close the service host by pressing `<RETURN>`.</span></span>  
  
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
using System.Data;  
  
namespace Polling_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
  
        public override void Polling(Polling request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            DataSet[] dataArray = request.PolledData;  
            foreach (DataTable tab in dataArray[0].Tables)  
            {  
                foreach (DataRow row in tab.Rows)  
                {  
                    for (int i = 0; i < tab.Columns.Count; i++)  
                    {  
                        Console.WriteLine(row[i]);  
                    }  
                }  
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
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
                binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
                Console.WriteLine("Binding properties assigned...");  
  
                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId (if any) that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
  
                // This URI is used to initialize the ServiceHost. It cannot contain  
                // a query_string (InboundID); otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
  
                PollingCredentials credentials = new PollingCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                Console.WriteLine("Opening service host...");  
                PollingService service = new PollingService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("PollingOperation", binding, ConnectionUri);  
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
  
## <a name="see-also"></a><span data-ttu-id="e2448-228">参照</span><span class="sxs-lookup"><span data-stu-id="e2448-228">See Also</span></span>  
 [<span data-ttu-id="e2448-229">WCF サービス モデルで、SQL アダプターを使用して SQL サーバーにポーリング</span><span class="sxs-lookup"><span data-stu-id="e2448-229">Poll SQL Server using the SQL Adapter with WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)