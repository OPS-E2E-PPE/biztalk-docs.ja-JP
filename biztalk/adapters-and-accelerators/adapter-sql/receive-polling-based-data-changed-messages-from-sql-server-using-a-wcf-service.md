---
title: WCF サービス モデルを使用して SQL Server からのポーリングに基づいたデータ変更メッセージの受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8713dd38-65ff-4d89-b23b-a93c06c5ff22
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47e7ddbd3270019fee68659cb36047f7084c356d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988419"
---
# <a name="receive-polling-based-data-changed-messages-from-sql-server-using-the-wcf-service-model"></a><span data-ttu-id="99109-102">WCF サービス モデルを使用して SQL Server からのポーリングに基づいたデータ変更メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="99109-102">Receive Polling-based Data-changed Messages from SQL Server Using the WCF Service Model</span></span>
<span data-ttu-id="99109-103">構成することができます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server テーブルまたはビューの定期的なデータ変更メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="99109-103">You can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive periodic data-change messages for SQL Server tables or views.</span></span> <span data-ttu-id="99109-104">データベースをポーリングするアダプターを実行するポーリング ステートメントを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="99109-104">You can specify a polling statement that the adapter executes to poll the database.</span></span> <span data-ttu-id="99109-105">ポーリング ステートメントには、SELECT ステートメントまたはストアド プロシージャを返す結果セットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="99109-105">The polling statement can be a SELECT statement or a stored procedure that returns a result set.</span></span>  

 <span data-ttu-id="99109-106">アダプターがポーリングをサポートする方法の詳細については、次を参照してください。 [SQL アダプターを使用して SQL Server でのポーリング](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="99109-106">For more information on how the adapter supports polling, see [Polling in SQL Server using the SQL adapter](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md).</span></span>  

> [!NOTE]
>  <span data-ttu-id="99109-107">このトピックでは、使用する方法を示します、**ポーリング**ポーリング メッセージを使用する操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="99109-107">This topic demonstrates how to use the **Polling** inbound operation to use polling messages.</span></span> <span data-ttu-id="99109-108">ポーリング操作のメッセージがない厳密に型指定します。</span><span class="sxs-lookup"><span data-stu-id="99109-108">The message for the Polling operation is not strongly-typed.</span></span> <span data-ttu-id="99109-109">使用する必要がありますを厳密に型指定されたポーリング メッセージを取得する場合、 **TypedPolling**操作。</span><span class="sxs-lookup"><span data-stu-id="99109-109">If you want to get strongly-typed polling message, you must use the **TypedPolling** operation.</span></span> <span data-ttu-id="99109-110">使用することも必要があります、 **TypedPolling**工程に単一のアプリケーションで複数の操作をポーリングします。</span><span class="sxs-lookup"><span data-stu-id="99109-110">You must also use the **TypedPolling** operation to have multiple polling operations in a single application.</span></span> <span data-ttu-id="99109-111">手順を実行する方法について**TypedPolling**操作を参照してください[SQL Server を使用して WCF サービス モデルからデータ変更のポーリングに基づいたメッセージを受信厳密に型指定された](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-sql-messages-with-wcf-service.md)します。</span><span class="sxs-lookup"><span data-stu-id="99109-111">For instructions on how to perform **TypedPolling** operation, see [Receive Strongly-typed Polling-based Data-changed Messages from SQL Server Using WCF Service Model](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-sql-messages-with-wcf-service.md).</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="99109-112">単一のアプリケーションでは、複数のポーリング操作を必要するかどうか、指定する必要あります、 **InboundID**接続して一意の URI の一部として接続プロパティです。</span><span class="sxs-lookup"><span data-stu-id="99109-112">If you want to have more than one polling operation in a single application, you must specify an **InboundID** connection property as part of the connection URI to make it unique.</span></span> <span data-ttu-id="99109-113">指定した受信 ID は一意になるように操作の名前空間に追加されます。</span><span class="sxs-lookup"><span data-stu-id="99109-113">The inbound ID you specify is added to the operation namespace to make it unique.</span></span>  

## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="99109-114">このトピックでポーリングしていますか</span><span class="sxs-lookup"><span data-stu-id="99109-114">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="99109-115">示すために、このトピックでどのように[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]データの受信をサポートは、メッセージの変更、.NET アプリケーションを作成しの WCF サービス コントラクトを生成、**ポーリング**操作。</span><span class="sxs-lookup"><span data-stu-id="99109-115">In this topic, to demonstrate how the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports receiving data change messages, create a .NET application and generate the WCF service contract for the **Polling** operation.</span></span> <span data-ttu-id="99109-116">ポーリングを指定する場合は、関連するプロパティをバインド WCF サービス コントラクトを生成するときに、指定、 **PolledDataAvailableStatement**として。</span><span class="sxs-lookup"><span data-stu-id="99109-116">If you want to specify the polling related binding properties while generating the WCF service contract, specify the **PolledDataAvailableStatement** as:</span></span>  

```  
SELECT COUNT(*) FROM Employee  
```  

 <span data-ttu-id="99109-117">**PolledDataAvailableStatement**正の値を格納している最初のセルを含む結果セットを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="99109-117">The **PolledDataAvailableStatement** must return a result set with the first cell containing a positive value.</span></span> <span data-ttu-id="99109-118">最初のセルに正の値が含まれていない場合でも、アダプターでは、ポーリング ステートメントは実行されません。</span><span class="sxs-lookup"><span data-stu-id="99109-118">If the first cell does not contain a positive value, the adapter does not execute the polling statement.</span></span>  

 <span data-ttu-id="99109-119">ポーリング ステートメントの一部として、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="99109-119">As part of the polling statement, perform the following operations:</span></span>  

1. <span data-ttu-id="99109-120">Employee テーブルからすべての行を選択します。</span><span class="sxs-lookup"><span data-stu-id="99109-120">Select all the rows from the Employee table.</span></span>  

2. <span data-ttu-id="99109-121">ストアド プロシージャ、EmployeeHistory テーブルに、Employee テーブルからすべてのレコードを移動するには、(MOVE_EMP_DATA) を実行します。</span><span class="sxs-lookup"><span data-stu-id="99109-121">Execute a stored procedure (MOVE_EMP_DATA) to move all the records from the Employee table to an EmployeeHistory table.</span></span>  

3. <span data-ttu-id="99109-122">Employee テーブルに新しいレコードを追加するには、(ADD_EMP_DETAILS) ストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="99109-122">Execute a stored procedure (ADD_EMP_DETAILS) to add a new record to the Employee table.</span></span> <span data-ttu-id="99109-123">この手順は、従業員の名前、表記、および給与をパラメーターとして受け取ります。</span><span class="sxs-lookup"><span data-stu-id="99109-123">This procedure takes the employee name, designation, and salary as parameters.</span></span>  

   <span data-ttu-id="99109-124">これらの操作を実行するは、次を指定する必要があります、 **PollingStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="99109-124">To perform these operations, you must specify the following for the **PollingStatement** binding property:</span></span>  

```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  

 <span data-ttu-id="99109-125">ポーリング ステートメントが実行された後に、Employee テーブルからすべてのレコードが選択されているし、SQL Server からメッセージを受信しました。</span><span class="sxs-lookup"><span data-stu-id="99109-125">After the polling statement is executed, all the records from the Employee table are selected and the message from SQL Server is received.</span></span> <span data-ttu-id="99109-126">アダプターによって MOVE_EMP_DATA ストアド プロシージャの実行後は、すべてのレコードが EmployeeHistory テーブルに移動されます。</span><span class="sxs-lookup"><span data-stu-id="99109-126">After the MOVE_EMP_DATA stored procedure is executed by the adapter, all the records are moved to the EmployeeHistory table.</span></span> <span data-ttu-id="99109-127">次に、Employee テーブルに新しいレコードを追加する ADD_EMP_DETAILS ストアド プロシージャが実行されます。</span><span class="sxs-lookup"><span data-stu-id="99109-127">Then, the ADD_EMP_DETAILS stored procedure is executed to add a new record to the Employee table.</span></span> <span data-ttu-id="99109-128">次のポーリングの実行は、1 つのレコードのみ戻ります。</span><span class="sxs-lookup"><span data-stu-id="99109-128">The next polling execution will only return a single record.</span></span> <span data-ttu-id="99109-129">このサイクルでは、サービス ホストを終了するまで続けられます。</span><span class="sxs-lookup"><span data-stu-id="99109-129">This cycle continues until you close the service host.</span></span>  

## <a name="configuring-a-polling-query-with-the-sql-adapter-binding-properties"></a><span data-ttu-id="99109-130">SQL アダプターのプロパティのバインドと、ポーリング クエリの構成</span><span class="sxs-lookup"><span data-stu-id="99109-130">Configuring a Polling Query with the SQL Adapter Binding Properties</span></span>  
 <span data-ttu-id="99109-131">次の表にまとめたものです、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドのプロパティのデータ変更メッセージを受信するアダプターを構成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="99109-131">The following table summarizes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding properties that you use to configure the adapter to receive data-change messages.</span></span> <span data-ttu-id="99109-132">ポーリングの .NET アプリケーションの一部として、これらのバインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99109-132">You must specify these binding properties as part of the .NET application for polling.</span></span>  


|         <span data-ttu-id="99109-133">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="99109-133">Binding Property</span></span>         |                                                                                                                                                                                                                                         <span data-ttu-id="99109-134">説明</span><span class="sxs-lookup"><span data-stu-id="99109-134">Description</span></span>                                                                                                                                                                                                                                          |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="99109-135">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="99109-135">**InboundOperationType**</span></span>     |                                                                                                                                                                             <span data-ttu-id="99109-136">実行するかどうかを指定します**ポーリング**、 **TypedPolling**、または**通知**操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="99109-136">Specifies whether you want to perform **Polling**, **TypedPolling**, or **Notification** inbound operation.</span></span> <span data-ttu-id="99109-137">既定値は**ポーリング**します。</span><span class="sxs-lookup"><span data-stu-id="99109-137">Default is **Polling**.</span></span>                                                                                                                                                                              |
| <span data-ttu-id="99109-138">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="99109-138">**PolledDataAvailableStatement**</span></span> |                                                                                       <span data-ttu-id="99109-139">すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="99109-139">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="99109-140">SQL ステートメントには、結果の行と列で構成されるセットを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="99109-140">The SQL statement must return a result set consisting of rows and columns.</span></span> <span data-ttu-id="99109-141">SQL ステートメントが指定した行を使用できる場合のみ、 **PollingStatement**プロパティのバインドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="99109-141">Only if a row is available, the SQL statement specified for the **PollingStatement** binding property will be executed.</span></span>                                                                                       |
|   <span data-ttu-id="99109-142">**PollingIntervalInSeconds**</span><span class="sxs-lookup"><span data-stu-id="99109-142">**PollingIntervalInSeconds**</span></span>   |                         <span data-ttu-id="99109-143">秒単位で間隔を指定、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]に指定されたステートメントが実行される、 **PolledDataAvailableStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="99109-143">Specifies the interval, in seconds, at which the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="99109-144">既定値は 30 秒です。</span><span class="sxs-lookup"><span data-stu-id="99109-144">The default is 30 seconds.</span></span> <span data-ttu-id="99109-145">ポーリング間隔は、連続するポーリングの間隔を決定します。</span><span class="sxs-lookup"><span data-stu-id="99109-145">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="99109-146">ステートメントは、指定した期間内で実行される、アダプターは、残りの時間間隔での待機します。</span><span class="sxs-lookup"><span data-stu-id="99109-146">If the statement is executed within the specified interval, the adapter waits for the remaining time in the interval.</span></span>                          |
|       <span data-ttu-id="99109-147">**PollingStatement**</span><span class="sxs-lookup"><span data-stu-id="99109-147">**PollingStatement**</span></span>       | <span data-ttu-id="99109-148">SQL Server データベースのテーブルをポーリングする SQL ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="99109-148">Specifies the SQL statement to poll the SQL Server database table.</span></span> <span data-ttu-id="99109-149">単純な SELECT ステートメントまたはストアド プロシージャのポーリング ステートメントを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="99109-149">You can specify a simple SELECT statement or a stored procedure for the polling statement.</span></span> <span data-ttu-id="99109-150">既定値は null です。</span><span class="sxs-lookup"><span data-stu-id="99109-150">The default is null.</span></span> <span data-ttu-id="99109-151">値を指定する必要があります**PollingStatement**ポーリングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="99109-151">You must specify a value for **PollingStatement** to enable polling.</span></span> <span data-ttu-id="99109-152">ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="99109-152">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="99109-153">セミコロンで区切られた SQL ステートメントの任意の数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="99109-153">You can specify any number of SQL statements separated by a semi-colon.</span></span> |
|      <span data-ttu-id="99109-154">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="99109-154">**PollWhileDataFound**</span></span>      |                            <span data-ttu-id="99109-155">指定するかどうか、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ポーリング間隔を無視し、継続的に指定された SQL ステートメントを実行、 **PolledDataAvailableStatement**データがポーリングされるテーブルで使用できる場合は、プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="99109-155">Specifies whether the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ignores the polling interval and continuously executes the SQL statement specified for the **PolledDataAvailableStatement** binding property, if data is available in the table being polled.</span></span> <span data-ttu-id="99109-156">テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔で SQL ステートメントを実行する元に戻します。</span><span class="sxs-lookup"><span data-stu-id="99109-156">If no data is available in the table, the adapter reverts to execute the SQL statement at the specified polling interval.</span></span> <span data-ttu-id="99109-157">既定値は**false**します。</span><span class="sxs-lookup"><span data-stu-id="99109-157">Default is **false**.</span></span>                             |

 <span data-ttu-id="99109-158">これらのプロパティの詳細については、次を参照してください。 [for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="99109-158">For a more complete description of these properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="99109-159">使用する方法の詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を SQL Server をポーリングするには、さらに読み進める。</span><span class="sxs-lookup"><span data-stu-id="99109-159">For a complete description of how to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to poll SQL Server, read further.</span></span>  

## <a name="configuring-polling-in-the-wcf-service-model"></a><span data-ttu-id="99109-160">WCF サービス モデルでのポーリングの構成</span><span class="sxs-lookup"><span data-stu-id="99109-160">Configuring Polling in the WCF Service Model</span></span>  
 <span data-ttu-id="99109-161">受信する、**ポーリング**WCF サービス モデルを使用するときに操作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99109-161">To receive the **Polling** operation when you use the WCF service model, you must:</span></span>  

1. <span data-ttu-id="99109-162">WCF サービス コントラクト (インターフェイス) を生成、**ポーリング**アダプターによって公開されているメタデータから操作します。</span><span class="sxs-lookup"><span data-stu-id="99109-162">Generate a WCF service contract (interface) for the **Polling** operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="99109-163">これを行うには、使用する可能性があります、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="99109-163">To do this, you could use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span>  

2. <span data-ttu-id="99109-164">このインターフェイスからの WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="99109-164">Implement a WCF service from this interface.</span></span>  

3. <span data-ttu-id="99109-165">サービス ホストを使用してこの WCF サービス ホスト (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="99109-165">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  

## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="99109-166">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="99109-166">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="99109-167">このトピックの例では、Employee テーブルをポーリングします。</span><span class="sxs-lookup"><span data-stu-id="99109-167">The examples in this topic poll the Employee table.</span></span> <span data-ttu-id="99109-168">この例は、MOVE_EMP_DATA と ADD_EMP_DETAILS にも使用ストアド プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="99109-168">The example also uses the MOVE_EMP_DATA and ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="99109-169">これらの成果物を生成するスクリプトは、サンプルで提供されます。</span><span class="sxs-lookup"><span data-stu-id="99109-169">A script to generate these artifacts is supplied with the samples.</span></span> <span data-ttu-id="99109-170">サンプルの詳細については、次を参照してください。 [SQL アダプタのサンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="99109-170">For more information about the samples, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span> <span data-ttu-id="99109-171">サンプルについては、 **Polling_ServiceModel**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="99109-171">A sample, **Polling_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  

## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="99109-172">WCF サービス コントラクトとクラス</span><span class="sxs-lookup"><span data-stu-id="99109-172">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="99109-173">使用することができます、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) とサポートのクラスを作成する、**ポーリング**操作。</span><span class="sxs-lookup"><span data-stu-id="99109-173">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **Polling** operation.</span></span> <span data-ttu-id="99109-174">WCF サービス コントラクトを生成する詳細については、次を参照してください。 [SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="99109-174">For more information about generating a WCF service contract, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  

### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="99109-175">WCF サービス コントラクト (インターフェイス)</span><span class="sxs-lookup"><span data-stu-id="99109-175">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="99109-176">次のコードに対して生成された WCF サービス コントラクト (インターフェイス) を示しています、**ポーリング**操作。</span><span class="sxs-lookup"><span data-stu-id="99109-176">The following code shows the WCF service contract (interface) generated for the **Polling** operation.</span></span>  

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

### <a name="the-message-contracts"></a><span data-ttu-id="99109-177">メッセージ コントラクト</span><span class="sxs-lookup"><span data-stu-id="99109-177">The Message Contracts</span></span>  
 <span data-ttu-id="99109-178">メッセージ コントラクトの名前空間を変更した、 **InboundID**接続 URI を指定した場合のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="99109-178">The message contract namespace is modified by the **InboundID** parameter in the connection URI, if specified.</span></span> <span data-ttu-id="99109-179">この例では、接続 URI の受信の ID を指定されませんでした。</span><span class="sxs-lookup"><span data-stu-id="99109-179">In this example, you did not specify an inbound ID in the connection URI.</span></span> <span data-ttu-id="99109-180">要求メッセージは、データセットを返します。</span><span class="sxs-lookup"><span data-stu-id="99109-180">The request message returns a DataSet.</span></span>  

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

### <a name="wcf-service-class"></a><span data-ttu-id="99109-181">WCF サービス クラス</span><span class="sxs-lookup"><span data-stu-id="99109-181">WCF Service Class</span></span>  
 <span data-ttu-id="99109-182">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をサービス コントラクト (インターフェイス) から実装された WCF サービス クラスのスタブを持つファイルも生成されます。</span><span class="sxs-lookup"><span data-stu-id="99109-182">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="99109-183">ファイルの名前は、SqlAdapterBindingService.cs です。</span><span class="sxs-lookup"><span data-stu-id="99109-183">The name of the file is SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="99109-184">処理するロジックを挿入することができます、**ポーリング**このクラスに直接操作します。</span><span class="sxs-lookup"><span data-stu-id="99109-184">You can insert the logic to process the **Polling** operation directly into this class.</span></span> <span data-ttu-id="99109-185">次のコードによって生成される WCF サービス クラスを示しています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="99109-185">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  

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

## <a name="receiving-inbound-messages-for-polling-operation"></a><span data-ttu-id="99109-186">ポーリング操作の着信メッセージを受信</span><span class="sxs-lookup"><span data-stu-id="99109-186">Receiving Inbound Messages for Polling Operation</span></span>  
 <span data-ttu-id="99109-187">このセクションを使用してポーリングの受信メッセージを受信する .NET アプリケーションを作成する方法の説明、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="99109-187">This section provides instructions on how to write a .NET application to receive inbound polling messages using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

#### <a name="to-receive-polling-messages-from-the-sql-adapter"></a><span data-ttu-id="99109-188">SQL アダプタからポーリング メッセージを受信するには</span><span class="sxs-lookup"><span data-stu-id="99109-188">To receive polling messages from the SQL adapter</span></span>  

1. <span data-ttu-id="99109-189">使用して、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) とのヘルパー クラスを生成する、**ポーリング**操作。</span><span class="sxs-lookup"><span data-stu-id="99109-189">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **Polling** operation.</span></span> <span data-ttu-id="99109-190">詳細については、次を参照してください。 [SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="99109-190">For more information, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span> <span data-ttu-id="99109-191">必要に応じて、サービス コントラクトとヘルパー クラスを生成するときにバインドのプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="99109-191">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="99109-192">これは、生成された構成ファイルで設定は正しくことを保証します。</span><span class="sxs-lookup"><span data-stu-id="99109-192">This guarantees that they are properly set in the generated configuration file.</span></span>  

2. <span data-ttu-id="99109-193">手順 1. で生成されたインターフェイスとヘルパー クラスからの WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="99109-193">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="99109-194">**ポーリング**から受信したデータの処理エラーが発生した場合、このクラスのメソッドは、ポーリング トランザクションを中止する例外をスローできます、**ポーリング**操作ですそれ以外の場合、メソッドでは。何も返しません。</span><span class="sxs-lookup"><span data-stu-id="99109-194">The **Polling** method of this class can throw an exception to abort the polling transaction, if an error is encountered processing the data received from the **Polling** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="99109-195">次のように、WCF サービス クラスを属性する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99109-195">You must attribute the WCF service class as follows:</span></span>  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  

    <span data-ttu-id="99109-196">内で、**ポーリング**メソッドを直接、アプリケーション ロジックを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="99109-196">Within the **Polling** method, you can implement your application logic directly.</span></span> <span data-ttu-id="99109-197">このクラスは、SqlAdapterBindingService.cs で確認できます。</span><span class="sxs-lookup"><span data-stu-id="99109-197">This class can be found in SqlAdapterBindingService.cs.</span></span> <span data-ttu-id="99109-198">この例では、このコードはサブ クラス、 **SqlAdapterBindingService**クラス。</span><span class="sxs-lookup"><span data-stu-id="99109-198">This code in this example sub-classes the **SqlAdapterBindingService** class.</span></span> <span data-ttu-id="99109-199">このコードでは、データセットとして受信したポーリング メッセージは、コンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="99109-199">In this code, the polling message received as a DataSet is written to the console.</span></span>  

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

3. <span data-ttu-id="99109-200">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]資格情報を受け入れません接続 URI の一部として、SQL Server データベースの資格情報を渡すには、次のクラスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99109-200">Because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not accept credentials as part of the connection URI, you must implement the following class to pass credentials for the SQL Server database.</span></span> <span data-ttu-id="99109-201">アプリケーションの後半部分の SQL Server 資格情報を渡すには、このクラスをインスタンス化されます。</span><span class="sxs-lookup"><span data-stu-id="99109-201">In the latter part of the application, you will instantiate this class to pass on the SQL Server credentials.</span></span>  

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

4. <span data-ttu-id="99109-202">作成、 **SqlAdapterBinding**とバインドのプロパティを指定することで、ポーリング操作を構成します。</span><span class="sxs-lookup"><span data-stu-id="99109-202">Create a **SqlAdapterBinding** and configure the polling operation by specifying the binding properties.</span></span> <span data-ttu-id="99109-203">コードで明示的に、または構成で宣言的に、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="99109-203">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="99109-204">指定する必要がありますには、少なくとも、 **InboundOperationType**、 **PolledDataAvailableStatement**、および**PollingStatement**します。</span><span class="sxs-lookup"><span data-stu-id="99109-204">At a minimum, you must specify the **InboundOperationType**, **PolledDataAvailableStatement**, and **PollingStatement**.</span></span>  

   ```  
   SqlAdapterBinding binding = new SqlAdapterBinding();  
   binding.InboundOperationType = InboundOperation.Polling;  
   binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
   binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
   ```  

5. <span data-ttu-id="99109-205">SQL Server データベースの資格情報を指定するには、インスタンス化する、 **PollingCredentials**手順 3 で作成したクラス。</span><span class="sxs-lookup"><span data-stu-id="99109-205">Specify SQL Server database credentials by instantiating the **PollingCredentials** class you created in Step 3.</span></span>  

   ```  
   PollingCredentials credentials = new PollingCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  
   ```  

6. <span data-ttu-id="99109-206">手順 2 で作成した WCF サービスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="99109-206">Create an instance of the WCF service created in step 2.</span></span>  

   ```  
   // create service instance  
   PollingService service = new PollingService();  
   ```  

7. <span data-ttu-id="99109-207">インスタンスを作成**System.ServiceModel.ServiceHost** WCF サービスと基本の接続 URI を使用しています。</span><span class="sxs-lookup"><span data-stu-id="99109-207">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="99109-208">基本の接続 URI は、指定されている場合、受信の ID を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="99109-208">The base connection URI cannot contain the inbound ID, if specified.</span></span> <span data-ttu-id="99109-209">ここで、資格情報を指定することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="99109-209">You should also specify the credentials here.</span></span>  

   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
   ServiceHost serviceHost = new ServiceHost(service, baseUri);  
   serviceHost.Description.Behaviors.Add(credentials);  

   ```  

8. <span data-ttu-id="99109-210">サービス ホストにサービス エンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="99109-210">Add a service endpoint to the service host.</span></span> <span data-ttu-id="99109-211">これを行うには :</span><span class="sxs-lookup"><span data-stu-id="99109-211">To do this:</span></span>  

   -   <span data-ttu-id="99109-212">手順 4. で作成したバインドを使用します。</span><span class="sxs-lookup"><span data-stu-id="99109-212">Use the binding created in step 4.</span></span>  

   -   <span data-ttu-id="99109-213">接続の資格情報を含む URI を指定し、必要に応じて、受信の id。</span><span class="sxs-lookup"><span data-stu-id="99109-213">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  

   -   <span data-ttu-id="99109-214">"PollingOperation"としてコントラクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="99109-214">Specify the contract as "PollingOperation".</span></span>  

   ```  
   // Add service endpoint: be sure to specify PollingOperation as the contract  
   Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
   serviceHost.AddServiceEndpoint("PollingOperation", binding, ConnectionUri);  
   ```  

9. <span data-ttu-id="99109-215">ポーリングのデータを受信するには、サービス ホストを開きます。</span><span class="sxs-lookup"><span data-stu-id="99109-215">To receive polling data, open the service host.</span></span> <span data-ttu-id="99109-216">アダプターは、クエリが結果セットを返すたびにデータを返します。</span><span class="sxs-lookup"><span data-stu-id="99109-216">The adapter will return data whenever the query returns a result set.</span></span>  

    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  

10. <span data-ttu-id="99109-217">ポーリングを終了するには、サービス ホストを閉じます。</span><span class="sxs-lookup"><span data-stu-id="99109-217">To terminate polling, close the service host.</span></span>  

    > [!IMPORTANT]
    >  <span data-ttu-id="99109-218">アダプターは、サービス ホストが閉じられるまでポーリングを続行します。</span><span class="sxs-lookup"><span data-stu-id="99109-218">The adapter will continue to poll until the service host is closed.</span></span>  

    ```  
    serviceHost.Close();  
    ```  

### <a name="example"></a><span data-ttu-id="99109-219">例</span><span class="sxs-lookup"><span data-stu-id="99109-219">Example</span></span>  
 <span data-ttu-id="99109-220">次の例では、Employee テーブルに実行されるポーリング クエリを示します。</span><span class="sxs-lookup"><span data-stu-id="99109-220">The following example shows a polling query that executes the Employee table.</span></span> <span data-ttu-id="99109-221">ポーリング ステートメントは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="99109-221">The polling statement performs the following tasks:</span></span>  

1. <span data-ttu-id="99109-222">Employee テーブルからすべてのレコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="99109-222">Selects all the records from the Employee table.</span></span>  

2. <span data-ttu-id="99109-223">EmployeeHistory テーブルに、Employee テーブルからすべてのレコードを移動する MOVE_EMP_DATA ストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="99109-223">Executes the MOVE_EMP_DATA stored procedure to move all records from Employee table to EmployeeHistory table.</span></span>  

3. <span data-ttu-id="99109-224">Employee テーブルに 1 つのレコードを追加する ADD_EMP_DETAILS ストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="99109-224">Executes the ADD_EMP_DETAILS stored procedure to add a single record to the Employee table.</span></span>  

   <span data-ttu-id="99109-225">ポーリングの最初のメッセージは、Employee テーブルからすべてのレコードが格納されます。</span><span class="sxs-lookup"><span data-stu-id="99109-225">The first polling message will contain all the records from the Employee table.</span></span> <span data-ttu-id="99109-226">その後ポーリング メッセージ ADD_EMP_DETAILS ストアド プロシージャによって挿入された最後のレコードのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="99109-226">The subsequent polling messages will contain only the last record inserted by the ADD_EMP_DETAILS stored procedure.</span></span> <span data-ttu-id="99109-227">アダプターのポーリングを押して、サービス ホストを終了するまでは引き続き`<RETURN>`します。</span><span class="sxs-lookup"><span data-stu-id="99109-227">The adapter will continue to poll until you close the service host by pressing `<RETURN>`.</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="99109-228">参照</span><span class="sxs-lookup"><span data-stu-id="99109-228">See Also</span></span>  
 [<span data-ttu-id="99109-229">SQL Server をポーリングする WCF サービス モデルでの SQL アダプタの使用</span><span class="sxs-lookup"><span data-stu-id="99109-229">Poll SQL Server using the SQL Adapter with WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)