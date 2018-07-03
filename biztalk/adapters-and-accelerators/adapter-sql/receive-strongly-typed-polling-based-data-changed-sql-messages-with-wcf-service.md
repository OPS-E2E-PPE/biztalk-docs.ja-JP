---
title: WCF サービス モデルを使用して SQL Server からのポーリングに基づいたデータ変更メッセージを厳密に型指定の受信 |Microsoft Docs
description: .NET アプリケーションを使用して、型指定されたポーリングまたは WCF-SQL アダプターの BizTalk Server で WCF サービスを使用して、厳密に型指定されたポーリングを構成するには
ms.custom: ''
ms.date: 10/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b55eda71-1226-43f2-bc2f-e6b35563210b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adf6f1e322485521504259f24dade00bb33a4539
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012651"
---
# <a name="receive-strongly-typed-polling-based-data-changed-messages-from-sql-server-using-wcf-service-model"></a><span data-ttu-id="5009a-103">WCF サービス モデルを使用して SQL Server からのポーリングに基づいたデータ変更メッセージを厳密に型指定の受信します。</span><span class="sxs-lookup"><span data-stu-id="5009a-103">Receive Strongly-typed Polling-based Data-changed Messages from SQL Server Using WCF Service Model</span></span>
<span data-ttu-id="5009a-104">構成することができます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server から厳密に型指定されたポーリング メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="5009a-104">You can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive strongly-typed polling messages from SQL Server.</span></span> <span data-ttu-id="5009a-105">データベースをポーリングするアダプターを実行するポーリング ステートメントを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="5009a-105">You can specify a polling statement that the adapter executes to poll the database.</span></span> <span data-ttu-id="5009a-106">ポーリング ステートメントには、SELECT ステートメントまたはストアド プロシージャを返す結果セットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5009a-106">The polling statement can be a SELECT statement or a stored procedure that returns a result set.</span></span> <span data-ttu-id="5009a-107">厳密に型指定されたポーリングは、厳密に型指定された結果セットを受信するシナリオで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5009a-107">You must use strongly-typed polling in a scenario where you want to receive a strongly-typed result set.</span></span> <span data-ttu-id="5009a-108">アダプターが厳密に型指定されたポーリングをサポートする方法の詳細については、次を参照してください。[受信呼び出しのポーリングを使用してサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)します。</span><span class="sxs-lookup"><span data-stu-id="5009a-108">For more information on how the adapter supports strongly-typed polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="5009a-109">単一のアプリケーションでは、複数のポーリング操作を必要するかどうか、指定する必要あります、 **InboundID**接続して一意の URI の一部として接続プロパティです。</span><span class="sxs-lookup"><span data-stu-id="5009a-109">If you want to have more than one polling operation in a single application, you must specify an **InboundID** connection property as part of the connection URI to make it unique.</span></span> <span data-ttu-id="5009a-110">指定した受信 ID は一意になるように操作の名前空間に追加されます。</span><span class="sxs-lookup"><span data-stu-id="5009a-110">The inbound ID you specify is added to the operation namespace to make it unique.</span></span>  

## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="5009a-111">このトピックでポーリングしていますか</span><span class="sxs-lookup"><span data-stu-id="5009a-111">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="5009a-112">示すために、このトピックでどのように[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]厳密に型指定されたデータの受信をサポートは、メッセージの変更、.NET アプリケーションを作成しの WCF サービス コントラクトを生成、 **TypedPolling**操作。</span><span class="sxs-lookup"><span data-stu-id="5009a-112">In this topic, to demonstrate how the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports receiving strongly-typed data change messages, create a .NET application and generate the WCF service contract for the **TypedPolling** operation.</span></span> <span data-ttu-id="5009a-113">WCF サービス コントラクトを生成するときに、次を指定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="5009a-113">Make sure you specify the following while generating the WCF service contract:</span></span>  

- <span data-ttu-id="5009a-114">指定する必要があります、 **InboundID**接続 URI の一部として。</span><span class="sxs-lookup"><span data-stu-id="5009a-114">You must specify an **InboundID** as part of the connection URI.</span></span>  

- <span data-ttu-id="5009a-115">ポーリング ステートメントを指定する必要があります、 **PollingStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="5009a-115">You must specify a polling statement for the **PollingStatement** binding property.</span></span>  

  <span data-ttu-id="5009a-116">さらに、その他を指定する場合は、ポーリングが関連する。 プロキシ クラスを生成するときに、バインドのプロパティの指定、 **PolledDataAvailableStatement**として。</span><span class="sxs-lookup"><span data-stu-id="5009a-116">Additionally, if you want to specify other polling related binding properties while generating the proxy class, specify the **PolledDataAvailableStatement** as:</span></span>  

```  
SELECT COUNT(*) FROM Employee  
```  

 <span data-ttu-id="5009a-117">**PolledDataAvailableStatement**正の値を格納している最初のセルを含む結果セットを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="5009a-117">The **PolledDataAvailableStatement** must return a result set with the first cell containing a positive value.</span></span> <span data-ttu-id="5009a-118">最初のセルに正の値が含まれていない場合でも、アダプターでは、ポーリング ステートメントは実行されません。</span><span class="sxs-lookup"><span data-stu-id="5009a-118">If the first cell does not contain a positive value, the adapter does not execute the polling statement.</span></span>  

 <span data-ttu-id="5009a-119">ポーリング ステートメントの一部として、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="5009a-119">As part of the polling statement, perform the following operations:</span></span>  

1. <span data-ttu-id="5009a-120">Employee テーブルからすべての行を選択します。</span><span class="sxs-lookup"><span data-stu-id="5009a-120">Select all the rows from the Employee table.</span></span>  

2. <span data-ttu-id="5009a-121">ストアド プロシージャ、EmployeeHistory テーブルに、Employee テーブルからすべてのレコードを移動するには、(MOVE_EMP_DATA) を実行します。</span><span class="sxs-lookup"><span data-stu-id="5009a-121">Execute a stored procedure (MOVE_EMP_DATA) to move all the records from the Employee table to an EmployeeHistory table.</span></span>  

3. <span data-ttu-id="5009a-122">Employee テーブルに新しいレコードを追加するには、(ADD_EMP_DETAILS) ストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="5009a-122">Execute a stored procedure (ADD_EMP_DETAILS) to add a new record to the Employee table.</span></span> <span data-ttu-id="5009a-123">この手順は、従業員の名前、表記、および給与をパラメーターとして受け取ります。</span><span class="sxs-lookup"><span data-stu-id="5009a-123">This procedure takes the employee name, designation, and salary as parameters.</span></span>  

   <span data-ttu-id="5009a-124">これらの操作を実行するは、次を指定する必要があります、 **PollingStatement** WCF サービス コントラクトとヘルパー クラスを生成するときにプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="5009a-124">To perform these operations, you must specify the following for the **PollingStatement** binding property while generating the WCF service contract and helper classes:</span></span>  

```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  

 <span data-ttu-id="5009a-125">ポーリング ステートメントが実行された後に、Employee テーブルからすべてのレコードが選択されているし、SQL Server からメッセージを受信しました。</span><span class="sxs-lookup"><span data-stu-id="5009a-125">After the polling statement is executed, all the records from the Employee table are selected and the message from SQL Server is received.</span></span> <span data-ttu-id="5009a-126">アダプターによって MOVE_EMP_DATA ストアド プロシージャの実行後は、すべてのレコードが EmployeeHistory テーブルに移動されます。</span><span class="sxs-lookup"><span data-stu-id="5009a-126">After the MOVE_EMP_DATA stored procedure is executed by the adapter, all the records are moved to the EmployeeHistory table.</span></span> <span data-ttu-id="5009a-127">次に、Employee テーブルに新しいレコードを追加する ADD_EMP_DETAILS ストアド プロシージャが実行されます。</span><span class="sxs-lookup"><span data-stu-id="5009a-127">Then, the ADD_EMP_DETAILS stored procedure is executed to add a new record to the Employee table.</span></span> <span data-ttu-id="5009a-128">次のポーリングの実行は、1 つのレコードのみ戻ります。</span><span class="sxs-lookup"><span data-stu-id="5009a-128">The next polling execution will only return a single record.</span></span> <span data-ttu-id="5009a-129">このサイクルでは、サービス ホストを終了するまで続けられます。</span><span class="sxs-lookup"><span data-stu-id="5009a-129">This cycle continues until you close the service host.</span></span>  

## <a name="configuring-typed-polling-with-the-sql-adapter-binding-properties"></a><span data-ttu-id="5009a-130">SQL アダプターのプロパティのバインドで型指定されたポーリングを構成します。</span><span class="sxs-lookup"><span data-stu-id="5009a-130">Configuring Typed Polling with the SQL Adapter Binding Properties</span></span>  
 <span data-ttu-id="5009a-131">次の表にまとめたものです、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドのプロパティのデータ変更メッセージを受信するアダプターを構成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="5009a-131">The following table summarizes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding properties that you use to configure the adapter to receive data-change messages.</span></span> <span data-ttu-id="5009a-132">他にも、 **PollingStatement**バインディングのプロパティすべて他のバインドのプロパティこのセクションに記載が必要な .NET アプリケーションの実行中にします。</span><span class="sxs-lookup"><span data-stu-id="5009a-132">Other than the **PollingStatement** binding property, all the other binding properties listed in this section are required while running the .NET application.</span></span> <span data-ttu-id="5009a-133">指定する必要があります、 **PollingStatement** WCF サービス コントラクトを生成する前にプロパティをバインド**TypedPolling**操作。</span><span class="sxs-lookup"><span data-stu-id="5009a-133">You must specify the **PollingStatement** binding property before generating the WCF service contract **TypedPolling** operation.</span></span>  


|         <span data-ttu-id="5009a-134">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="5009a-134">Binding Property</span></span>         |                                                                                                                                                                                                                                                                                              <span data-ttu-id="5009a-135">説明</span><span class="sxs-lookup"><span data-stu-id="5009a-135">Description</span></span>                                                                                                                                                                                                                                                                                              |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="5009a-136">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="5009a-136">**InboundOperationType**</span></span>     |                                                                                                                                                                                             <span data-ttu-id="5009a-137">実行するかどうかを指定します**ポーリング**、 **TypedPolling**、または**通知**操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="5009a-137">Specifies whether you want to perform **Polling**, **TypedPolling**, or **Notification** inbound operation.</span></span> <span data-ttu-id="5009a-138">既定値は**ポーリング**します。</span><span class="sxs-lookup"><span data-stu-id="5009a-138">Default is **Polling**.</span></span> <span data-ttu-id="5009a-139">設定を厳密に型指定されたポーリング メッセージを受信する**TypedPolling**します。</span><span class="sxs-lookup"><span data-stu-id="5009a-139">To receive strongly-typed polling messages, set this to **TypedPolling**.</span></span>                                                                                                                                                                                             |
| <span data-ttu-id="5009a-140">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="5009a-140">**PolledDataAvailableStatement**</span></span> |                                                                                                                                           <span data-ttu-id="5009a-141">すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="5009a-141">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="5009a-142">SQL ステートメントには、結果の行と列で構成されるセットを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="5009a-142">The SQL statement must return a result set consisting of rows and columns.</span></span> <span data-ttu-id="5009a-143">SQL ステートメントが指定した行を使用できる場合のみ、 **PollingStatement**プロパティのバインドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="5009a-143">Only if a row is available, the SQL statement specified for the **PollingStatement** binding property will be executed.</span></span>                                                                                                                                            |
|   <span data-ttu-id="5009a-144">**PollingIntervalInSeconds**</span><span class="sxs-lookup"><span data-stu-id="5009a-144">**PollingIntervalInSeconds**</span></span>   |                                                                              <span data-ttu-id="5009a-145">秒単位で間隔を指定、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]に指定されたステートメントが実行される、 **PolledDataAvailableStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="5009a-145">Specifies the interval, in seconds, at which the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="5009a-146">既定値は 30 秒です。</span><span class="sxs-lookup"><span data-stu-id="5009a-146">The default is 30 seconds.</span></span> <span data-ttu-id="5009a-147">ポーリング間隔は、連続するポーリングの間隔を決定します。</span><span class="sxs-lookup"><span data-stu-id="5009a-147">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="5009a-148">ステートメントは、指定した期間内で実行される、アダプターは、残りの時間間隔での待機します。</span><span class="sxs-lookup"><span data-stu-id="5009a-148">If the statement is executed within the specified interval, the adapter waits for the remaining time in the interval.</span></span>                                                                              |
|       <span data-ttu-id="5009a-149">**PollingStatement**</span><span class="sxs-lookup"><span data-stu-id="5009a-149">**PollingStatement**</span></span>       | <span data-ttu-id="5009a-150">SQL Server データベースのテーブルをポーリングする SQL ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="5009a-150">Specifies the SQL statement to poll the SQL Server database table.</span></span> <span data-ttu-id="5009a-151">単純な SELECT ステートメントまたはストアド プロシージャのポーリング ステートメントを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="5009a-151">You can specify a simple SELECT statement or a stored procedure for the polling statement.</span></span> <span data-ttu-id="5009a-152">既定値は null です。</span><span class="sxs-lookup"><span data-stu-id="5009a-152">The default is null.</span></span> <span data-ttu-id="5009a-153">値を指定する必要があります**PollingStatement**ポーリングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="5009a-153">You must specify a value for **PollingStatement** to enable polling.</span></span> <span data-ttu-id="5009a-154">ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="5009a-154">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="5009a-155">セミコロンで区切られた SQL ステートメントの任意の数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5009a-155">You can specify any number of SQL statements separated by a semi-colon.</span></span> <span data-ttu-id="5009a-156">**重要:** の**TypedPolling**メタデータを生成する前にこのバインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5009a-156">**Important:**  For **TypedPolling**, you must specify this binding property before generating metadata.</span></span> |
|      <span data-ttu-id="5009a-157">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="5009a-157">**PollWhileDataFound**</span></span>      |                                                                                 <span data-ttu-id="5009a-158">指定するかどうか、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ポーリング間隔を無視し、継続的に指定された SQL ステートメントを実行、 **PolledDataAvailableStatement**データがポーリングされるテーブルで使用できる場合は、プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="5009a-158">Specifies whether the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ignores the polling interval and continuously executes the SQL statement specified for the **PolledDataAvailableStatement** binding property, if data is available in the table being polled.</span></span> <span data-ttu-id="5009a-159">テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔で SQL ステートメントを実行する元に戻します。</span><span class="sxs-lookup"><span data-stu-id="5009a-159">If no data is available in the table, the adapter reverts to execute the SQL statement at the specified polling interval.</span></span> <span data-ttu-id="5009a-160">既定値は**false**します。</span><span class="sxs-lookup"><span data-stu-id="5009a-160">Default is **false**.</span></span>                                                                                 |

 <span data-ttu-id="5009a-161">これらのプロパティの詳細については、次を参照してください。 [for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="5009a-161">For a more complete description of these properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="5009a-162">使用する方法の詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を SQL Server をポーリングするには、さらに読み進める。</span><span class="sxs-lookup"><span data-stu-id="5009a-162">For a complete description of how to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to poll SQL Server, read further.</span></span>  

## <a name="configure-strongly-typed-polling-in-the-wcf-service-model"></a><span data-ttu-id="5009a-163">WCF サービス モデルで厳密に型指定されたポーリングを構成します。</span><span class="sxs-lookup"><span data-stu-id="5009a-163">Configure Strongly-typed Polling in the WCF Service Model</span></span>  
 <span data-ttu-id="5009a-164">受信する、**ポーリング**WCF サービス モデルを使用するときに操作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5009a-164">To receive the **Polling** operation when you use the WCF service model, you must:</span></span>  

1. <span data-ttu-id="5009a-165">WCF サービス コントラクト (インターフェイス) を生成、 **TypedPolling**アダプターによって公開されているメタデータから操作します。</span><span class="sxs-lookup"><span data-stu-id="5009a-165">Generate a WCF service contract (interface) for the **TypedPolling** operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="5009a-166">これを行うには、使用する可能性があります、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="5009a-166">To do this, you could use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span> <span data-ttu-id="5009a-167">生成中にこの例では、WCF サービス コントラクトを確認します。</span><span class="sxs-lookup"><span data-stu-id="5009a-167">While generating the WCF service contract for this example, make sure:</span></span>  

   -   <span data-ttu-id="5009a-168">指定した、 **InboundID**として**従業員**します。</span><span class="sxs-lookup"><span data-stu-id="5009a-168">You specify the **InboundID** as **Employee**.</span></span>  

   -   <span data-ttu-id="5009a-169">ポーリング ステートメントを指定する、 **PollingStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="5009a-169">You specify a polling statement for the **PollingStatement** binding property.</span></span> <span data-ttu-id="5009a-170">この例では、ポーリング ステートメントとしてを指定します。</span><span class="sxs-lookup"><span data-stu-id="5009a-170">For this example, specify the polling statement as:</span></span>  

       ```  
       SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000  
       ```  

2. <span data-ttu-id="5009a-171">このインターフェイスからの WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="5009a-171">Implement a WCF service from this interface.</span></span>  

3. <span data-ttu-id="5009a-172">サービス ホストを使用してこの WCF サービス ホスト (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="5009a-172">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  

## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="5009a-173">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="5009a-173">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="5009a-174">このトピックの例では、Employee テーブルをポーリングします。</span><span class="sxs-lookup"><span data-stu-id="5009a-174">The examples in this topic poll the Employee table.</span></span> <span data-ttu-id="5009a-175">この例は、MOVE_EMP_DATA と ADD_EMP_DETAILS にも使用ストアド プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="5009a-175">The example also uses the MOVE_EMP_DATA and ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="5009a-176">これらの成果物を生成するスクリプトは、サンプルで提供されます。</span><span class="sxs-lookup"><span data-stu-id="5009a-176">A script to generate these artifacts is supplied with the samples.</span></span> <span data-ttu-id="5009a-177">サンプルの詳細については、次を参照してください。 [SQL アダプタのサンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="5009a-177">For more information about the samples, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span> <span data-ttu-id="5009a-178">サンプルについては、 **TypedPolling_ServiceModel**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="5009a-178">A sample, **TypedPolling_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  

## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="5009a-179">WCF サービス コントラクトとクラス</span><span class="sxs-lookup"><span data-stu-id="5009a-179">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="5009a-180">使用することができます、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) とサポートのクラスを作成する、 **TypedPolling**操作。</span><span class="sxs-lookup"><span data-stu-id="5009a-180">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **TypedPolling** operation.</span></span> <span data-ttu-id="5009a-181">WCF サービス コントラクトを生成する詳細については、次を参照してください。 [SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="5009a-181">For more information about generating a WCF service contract, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  

### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="5009a-182">WCF サービス コントラクト (インターフェイス)</span><span class="sxs-lookup"><span data-stu-id="5009a-182">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="5009a-183">次のコードに対して生成された WCF サービス コントラクト (インターフェイス) を示しています、 **TypedPolling**操作。</span><span class="sxs-lookup"><span data-stu-id="5009a-183">The following code shows the WCF service contract (interface) generated for the **TypedPolling** operation.</span></span>  

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

### <a name="the-message-contracts"></a><span data-ttu-id="5009a-184">メッセージ コントラクト</span><span class="sxs-lookup"><span data-stu-id="5009a-184">The Message Contracts</span></span>  
 <span data-ttu-id="5009a-185">メッセージ コントラクトの名前空間を変更した、 **InboundID**接続 URI を指定した場合のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="5009a-185">The message contract namespace is modified by the **InboundID** parameter in the connection URI, if specified.</span></span> <span data-ttu-id="5009a-186">この例では、受信 ID としてを指定した**従業員**します。</span><span class="sxs-lookup"><span data-stu-id="5009a-186">In this example, you specified the inbound ID as **Employee**.</span></span> <span data-ttu-id="5009a-187">要求メッセージは、厳密に型指定された結果セットを返します。</span><span class="sxs-lookup"><span data-stu-id="5009a-187">The request message returns a strongly-typed result set.</span></span>  

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

### <a name="wcf-service-class"></a><span data-ttu-id="5009a-188">WCF サービス クラス</span><span class="sxs-lookup"><span data-stu-id="5009a-188">WCF Service Class</span></span>  
 <span data-ttu-id="5009a-189">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をサービス コントラクト (インターフェイス) から実装された WCF サービス クラスのスタブを持つファイルも生成されます。</span><span class="sxs-lookup"><span data-stu-id="5009a-189">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="5009a-190">ファイルの名前は、SqlAdapterBindingService.cs です。</span><span class="sxs-lookup"><span data-stu-id="5009a-190">The name of the file is SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="5009a-191">処理するロジックを挿入することができます、 **TypedPolling**このクラスに直接操作します。</span><span class="sxs-lookup"><span data-stu-id="5009a-191">You can insert the logic to process the **TypedPolling** operation directly into this class.</span></span> <span data-ttu-id="5009a-192">次のコードによって生成される WCF サービス クラスを示しています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="5009a-192">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  

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

## <a name="receive-strongly-typed-inbound-messages-for-polling-operation"></a><span data-ttu-id="5009a-193">ポーリング操作の厳密に型指定された受信メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="5009a-193">Receive Strongly-typed Inbound Messages for Polling Operation</span></span>  
 <span data-ttu-id="5009a-194">このセクションを使用して厳密に型指定された受信ポーリング メッセージを受信する .NET アプリケーションを作成する方法の説明、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="5009a-194">This section provides instructions on how to write a .NET application to receive strongly-typed inbound polling messages using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

1. <span data-ttu-id="5009a-195">使用して、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) とのヘルパー クラスを生成する、 **TypedPolling**操作。</span><span class="sxs-lookup"><span data-stu-id="5009a-195">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **TypedPolling** operation.</span></span> <span data-ttu-id="5009a-196">この例では、WCF サービス コントラクトを生成するときに、次を指定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="5009a-196">Make sure you specify the following while generating the WCF service contract for this example:</span></span>  

   - <span data-ttu-id="5009a-197">指定する必要があります、 **InboundID**として**従業員**します。</span><span class="sxs-lookup"><span data-stu-id="5009a-197">You must specify the **InboundID** as **Employee**.</span></span>  

   - <span data-ttu-id="5009a-198">ポーリング ステートメントを指定する必要があります、 **PollingStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="5009a-198">You must specify a polling statement for the **PollingStatement** binding property.</span></span> <span data-ttu-id="5009a-199">この例では、ポーリング ステートメントとしてを指定します。</span><span class="sxs-lookup"><span data-stu-id="5009a-199">For this example, specify the polling statement as:</span></span>  

     ```  
     SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000  
     ```  

     <span data-ttu-id="5009a-200">詳細については、次を参照してください。 [SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="5009a-200">For more information, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span> <span data-ttu-id="5009a-201">必要に応じて、サービス コントラクトとヘルパー クラスを生成するときにバインドのプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="5009a-201">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="5009a-202">これは、生成された構成ファイルで設定は正しくことを保証します。</span><span class="sxs-lookup"><span data-stu-id="5009a-202">This guarantees that they are properly set in the generated configuration file.</span></span>  

2. <span data-ttu-id="5009a-203">手順 1. で生成されたインターフェイスとヘルパー クラスからの WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="5009a-203">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="5009a-204">**TypedPolling**から受信したデータの処理エラーが発生した場合、このクラスのメソッドは、ポーリング トランザクションを中止する例外をスローできます、 **TypedPolling**操作そうしないと、。メソッドは何も返しません。</span><span class="sxs-lookup"><span data-stu-id="5009a-204">The **TypedPolling** method of this class can throw an exception to abort the polling transaction, if an error is encountered processing the data received from the **TypedPolling** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="5009a-205">次のように、WCF サービス クラスを属性する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5009a-205">You must attribute the WCF service class as follows:</span></span>  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  

    <span data-ttu-id="5009a-206">内で、 **TypedPolling**メソッドを直接、アプリケーション ロジックを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="5009a-206">Within the **TypedPolling** method, you can implement your application logic directly.</span></span> <span data-ttu-id="5009a-207">このクラスは、SqlAdapterBindingService.cs で確認できます。</span><span class="sxs-lookup"><span data-stu-id="5009a-207">This class can be found in SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="5009a-208">この例では、このコードはサブ クラス、 **SqlAdapterBindingService**クラス。</span><span class="sxs-lookup"><span data-stu-id="5009a-208">This code in this example sub-classes the **SqlAdapterBindingService** class.</span></span> <span data-ttu-id="5009a-209">このコードでは、厳密に型指定された結果セットとして受信したポーリング メッセージは、コンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="5009a-209">In this code, the polling message received as a strongly-typed result set is written to the console.</span></span>  

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

3. <span data-ttu-id="5009a-210">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]資格情報を受け入れません接続 URI の一部として、SQL Server データベースの資格情報を渡すには、次のクラスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5009a-210">Because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not accept credentials as part of the connection URI, you must implement the following class to pass credentials for the SQL Server database.</span></span> <span data-ttu-id="5009a-211">アプリケーションの後半部分の SQL Server 資格情報を渡すには、このクラスをインスタンス化されます。</span><span class="sxs-lookup"><span data-stu-id="5009a-211">In the latter part of the application, you will instantiate this class to pass on the SQL Server credentials.</span></span>  

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

4. <span data-ttu-id="5009a-212">作成、 **SqlAdapterBinding**とバインドのプロパティを指定することで、ポーリング操作を構成します。</span><span class="sxs-lookup"><span data-stu-id="5009a-212">Create a **SqlAdapterBinding** and configure the polling operation by specifying the binding properties.</span></span> <span data-ttu-id="5009a-213">コードで明示的に、または構成で宣言的に、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5009a-213">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="5009a-214">指定する必要がありますには、少なくとも、 **InboundOperationType**、 **PolledDataAvailableStatement**、および**PollingStatement**します。</span><span class="sxs-lookup"><span data-stu-id="5009a-214">At a minimum, you must specify the **InboundOperationType**, **PolledDataAvailableStatement**, and **PollingStatement**.</span></span>  

   ```  
   SqlAdapterBinding binding = new SqlAdapterBinding();  
   binding.InboundOperationType = InboundOperation.TypedPolling;  
   binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
   binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
   ```  

5. <span data-ttu-id="5009a-215">SQL Server データベースの資格情報を指定するには、インスタンス化する、 **PollingCredentials**手順 3 で作成したクラス。</span><span class="sxs-lookup"><span data-stu-id="5009a-215">Specify SQL Server database credentials by instantiating the **PollingCredentials** class you created in Step 3.</span></span>  

   ```  
   PollingCredentials credentials = new PollingCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  
   ```  

6. <span data-ttu-id="5009a-216">手順 2 で作成した WCF サービスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5009a-216">Create an instance of the WCF service created in step 2.</span></span>  

   ```  
   // create service instance  
   PollingService service = new PollingService();  
   ```  

7. <span data-ttu-id="5009a-217">インスタンスを作成**System.ServiceModel.ServiceHost** WCF サービスと基本の接続 URI を使用しています。</span><span class="sxs-lookup"><span data-stu-id="5009a-217">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="5009a-218">基本の接続 URI は、受信の ID を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="5009a-218">The base connection URI cannot contain the inbound ID.</span></span> <span data-ttu-id="5009a-219">ここで、資格情報を指定することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="5009a-219">You must also specify the credentials here.</span></span>  

   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
   ServiceHost serviceHost = new ServiceHost(service, baseUri);  
   serviceHost.Description.Behaviors.Add(credentials);  

   ```  

8. <span data-ttu-id="5009a-220">サービス ホストにサービス エンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="5009a-220">Add a service endpoint to the service host.</span></span> <span data-ttu-id="5009a-221">これを行うには :</span><span class="sxs-lookup"><span data-stu-id="5009a-221">To do this:</span></span>  

   -   <span data-ttu-id="5009a-222">手順 4. で作成したバインドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5009a-222">Use the binding created in step 4.</span></span>  

   -   <span data-ttu-id="5009a-223">接続の資格情報を含む URI を指定し、必要に応じて、受信の id。</span><span class="sxs-lookup"><span data-stu-id="5009a-223">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  

   -   <span data-ttu-id="5009a-224">"TypedPolling_Employee"としてコントラクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="5009a-224">Specify the contract as "TypedPolling_Employee".</span></span>  

   ```  
   // Add service endpoint: be sure to specify TypedPolling_Employee as the contract  
   Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?InboundID=Employee");  
   serviceHost.AddServiceEndpoint("TypedPolling_Employee", binding, ConnectionUri);  
   ```  

9. <span data-ttu-id="5009a-225">ポーリングのデータを受信するには、サービス ホストを開きます。</span><span class="sxs-lookup"><span data-stu-id="5009a-225">To receive polling data, open the service host.</span></span> <span data-ttu-id="5009a-226">アダプターは、クエリが結果セットを返すたびにデータを返します。</span><span class="sxs-lookup"><span data-stu-id="5009a-226">The adapter will return data whenever the query returns a result set.</span></span>  

    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  

10. <span data-ttu-id="5009a-227">ポーリングを終了するには、サービス ホストを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5009a-227">To terminate polling, close the service host.</span></span>  

    > [!IMPORTANT]
    >  <span data-ttu-id="5009a-228">アダプターは、サービス ホストが閉じられるまでポーリングを続行します。</span><span class="sxs-lookup"><span data-stu-id="5009a-228">The adapter will continue to poll until the service host is closed.</span></span>  

    ```  
    serviceHost.Close();  
    ```  

### <a name="example"></a><span data-ttu-id="5009a-229">例</span><span class="sxs-lookup"><span data-stu-id="5009a-229">Example</span></span>  
 <span data-ttu-id="5009a-230">次の例では、Employee テーブルに実行されるポーリング クエリを示します。</span><span class="sxs-lookup"><span data-stu-id="5009a-230">The following example shows a polling query that executes the Employee table.</span></span> <span data-ttu-id="5009a-231">ポーリング ステートメントは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="5009a-231">The polling statement performs the following tasks:</span></span>  

1. <span data-ttu-id="5009a-232">Employee テーブルからすべてのレコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="5009a-232">Selects all the records from the Employee table.</span></span>  

2. <span data-ttu-id="5009a-233">EmployeeHistory テーブルに、Employee テーブルからすべてのレコードを移動する MOVE_EMP_DATA ストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="5009a-233">Executes the MOVE_EMP_DATA stored procedure to move all records from Employee table to EmployeeHistory table.</span></span>  

3. <span data-ttu-id="5009a-234">Employee テーブルに 1 つのレコードを追加する ADD_EMP_DETAILS ストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="5009a-234">Executes the ADD_EMP_DETAILS stored procedure to add a single record to the Employee table.</span></span>  

   <span data-ttu-id="5009a-235">ポーリングの最初のメッセージは、Employee テーブルからすべてのレコードが格納されます。</span><span class="sxs-lookup"><span data-stu-id="5009a-235">The first polling message will contain all the records from the Employee table.</span></span> <span data-ttu-id="5009a-236">その後ポーリング メッセージ ADD_EMP_DETAILS ストアド プロシージャによって挿入された最後のレコードのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5009a-236">The subsequent polling messages will contain only the last record inserted by the ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="5009a-237">アダプターのポーリングを押して、サービス ホストを終了するまでは引き続き`<RETURN>`します。</span><span class="sxs-lookup"><span data-stu-id="5009a-237">The adapter will continue to poll until you close the service host by pressing `<RETURN>`.</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="5009a-238">参照</span><span class="sxs-lookup"><span data-stu-id="5009a-238">See Also</span></span>  
 [<span data-ttu-id="5009a-239">SQL Server をポーリングする WCF サービス モデルでの SQL アダプタの使用</span><span class="sxs-lookup"><span data-stu-id="5009a-239">Poll SQL Server using the SQL Adapter with WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)
