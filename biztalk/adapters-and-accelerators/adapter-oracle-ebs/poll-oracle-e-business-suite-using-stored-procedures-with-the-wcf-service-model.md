---
title: ストアド プロシージャを使用して WCF サービス モデルとポーリング Oracle E-business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47dcb866-9161-4b28-9481-2761794ce805
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2d01bcfd2b004042ce69f4843bb9ae7bb2f323f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007411"
---
# <a name="poll-oracle-e-business-suite-using-stored-procedures-with-the-wcf-service-model"></a><span data-ttu-id="75341-102">ストアド プロシージャを使用して WCF サービス モデルとポーリング Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="75341-102">Poll Oracle E-Business Suite using stored procedures with the WCF service model</span></span>
<span data-ttu-id="75341-103">構成することができます、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースを定期的にポーリングするストアド プロシージャを使用して、定期的なデータ変更メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="75341-103">You can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive periodic data-change messages by using stored procedures to periodically poll the Oracle database.</span></span> <span data-ttu-id="75341-104">ストアド プロシージャは、Oracle データベースをポーリングするアダプターを定期的に実行するポーリング ステートメントとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="75341-104">You can specify a stored procedure as a polling statement that the adapter executes periodically to poll the Oracle database.</span></span>  

 <span data-ttu-id="75341-105">ポーリングを有効にする、このトピックの説明に従って、特定のバインド プロパティの条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75341-105">To enable polling, you must specify certain binding properties as described in this topic.</span></span>  <span data-ttu-id="75341-106">アダプターがポーリングをサポートする方法の詳細については、[受信呼び出しのポーリングを使用してサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75341-106">For more information about how the adapter supports polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  

## <a name="configuring-a-polling-operation-with-oracle-e-business-adapter-binding-properties"></a><span data-ttu-id="75341-107">Oracle E-business アダプターのバインドのプロパティをポーリング操作を構成します。</span><span class="sxs-lookup"><span data-stu-id="75341-107">Configuring a Polling Operation with Oracle E-Business Adapter Binding Properties</span></span>  
 <span data-ttu-id="75341-108">次の表にまとめたものです、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインドのプロパティのデータ変更メッセージを受信するアダプターを構成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="75341-108">The following table summarizes the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding properties that you use to configure the adapter to receive data-change messages.</span></span> <span data-ttu-id="75341-109">ポーリング アプリケーションを実行中に、これらのバインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75341-109">You must specify these binding properties while running the polling application.</span></span>  


|         <span data-ttu-id="75341-110">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="75341-110">Binding Property</span></span>         |                                                                                                                                                                                                                                                                       <span data-ttu-id="75341-111">説明</span><span class="sxs-lookup"><span data-stu-id="75341-111">Description</span></span>                                                                                                                                                                                                                                                                       |
|----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="75341-112">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="75341-112">**InboundOperationType**</span></span>     |                                                                                                                                                                                                                   <span data-ttu-id="75341-113">実行するかどうかを指定します、**ポーリング**または**通知**操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="75341-113">Specifies whether you want to perform a **Polling** or **Notification** inbound operation.</span></span> <span data-ttu-id="75341-114">既定値は**ポーリング**します。</span><span class="sxs-lookup"><span data-stu-id="75341-114">Default is **Polling**.</span></span>                                                                                                                                                                                                                    |
| <span data-ttu-id="75341-115">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="75341-115">**PolledDataAvailableStatement**</span></span> |                                                                                                                                                       <span data-ttu-id="75341-116">すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="75341-116">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="75341-117">指定したストアド プロシージャのレコードを使用できる場合にのみ、 **PollingInput**プロパティのバインドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="75341-117">Only if a record is available, the stored procedure you specified for the **PollingInput** binding property will be executed.</span></span>                                                                                                                                                       |
|       <span data-ttu-id="75341-118">**PollingInterval**</span><span class="sxs-lookup"><span data-stu-id="75341-118">**PollingInterval**</span></span>        |                                           <span data-ttu-id="75341-119">秒単位で間隔を指定、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]に指定されたステートメントが実行される、 **PolledDataAvailableStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="75341-119">Specifies the interval, in seconds, at which the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="75341-120">既定値は 30 秒です。</span><span class="sxs-lookup"><span data-stu-id="75341-120">The default is 30 seconds.</span></span> <span data-ttu-id="75341-121">ポーリング間隔は、連続するポーリングの間隔を決定します。</span><span class="sxs-lookup"><span data-stu-id="75341-121">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="75341-122">ステートメントは、指定した期間内で実行される、アダプターが間隔内の残りの時間の間スリープします。</span><span class="sxs-lookup"><span data-stu-id="75341-122">If the statement is executed within the specified interval, the adapter sleeps for the remaining time in the interval.</span></span>                                            |
|         <span data-ttu-id="75341-123">**PollingInput**</span><span class="sxs-lookup"><span data-stu-id="75341-123">**PollingInput**</span></span>         | <span data-ttu-id="75341-124">ポーリング ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="75341-124">Specifies the polling statement.</span></span> <span data-ttu-id="75341-125">ストアド プロシージャを使用してポーリングする、このバインドのプロパティの全体の要求メッセージを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75341-125">To poll using a stored procedure, you must specify the entire request message for this binding property.</span></span> <span data-ttu-id="75341-126">要求メッセージは、送信操作としてストアド プロシージャを呼び出すため、アダプターに送信すると、同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="75341-126">The request message must be the same that you send to the adapter for invoking the stored procedure as an outbound operation.</span></span> <span data-ttu-id="75341-127">既定値は null です。</span><span class="sxs-lookup"><span data-stu-id="75341-127">The default is null.</span></span><br /><br /> <span data-ttu-id="75341-128">値を指定する必要があります**PollingInput**ポーリングを有効にするプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="75341-128">You must specify a value for **PollingInput** binding property to enable polling.</span></span> <span data-ttu-id="75341-129">ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="75341-129">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span> |
|        <span data-ttu-id="75341-130">**PollingAction**</span><span class="sxs-lookup"><span data-stu-id="75341-130">**PollingAction**</span></span>         |                                                                                                                                                          <span data-ttu-id="75341-131">ポーリング操作のアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="75341-131">Specifies the action for the polling operation.</span></span> <span data-ttu-id="75341-132">使用して、操作に対して生成されたサービスのインターフェイスからポーリング アクションを決定することができます、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="75341-132">You can determine the polling action from the service interface generated for the operation using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span>                                                                                                                                                           |
|      <span data-ttu-id="75341-133">**PostPollStatement**</span><span class="sxs-lookup"><span data-stu-id="75341-133">**PostPollStatement**</span></span>       |                                                                                                                                                                                                            <span data-ttu-id="75341-134">指定されたステートメントの後に実行されるステートメント ブロックを指定します、 **PollingInput**プロパティのバインドを実行します。</span><span class="sxs-lookup"><span data-stu-id="75341-134">Specifies a statement block that is executed after the statement specified by the **PollingInput** binding property is executed.</span></span>                                                                                                                                                                                                             |
|      <span data-ttu-id="75341-135">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="75341-135">**PollWhileDataFound**</span></span>      |                                                                               <span data-ttu-id="75341-136">指定するかどうか、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ポーリング間隔を無視し、継続的にデータがポーリングされるテーブルで使用できる場合に、ポーリング ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="75341-136">Specifies whether the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ignores the polling interval and continuously executes the polling statement, if data is available in the table being polled.</span></span> <span data-ttu-id="75341-137">テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔でポーリング ステートメントを実行する元に戻します。</span><span class="sxs-lookup"><span data-stu-id="75341-137">If no data is available in the table, the adapter reverts to execute the polling statement at the specified polling interval.</span></span> <span data-ttu-id="75341-138">既定値は false です。</span><span class="sxs-lookup"><span data-stu-id="75341-138">Default is false.</span></span>                                                                               |

 <span data-ttu-id="75341-139">これらのプロパティの詳細については、[Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75341-139">For a more complete description of these properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="75341-140">使用する方法の詳細については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]をポーリングするには、次のセクションを参照しています。</span><span class="sxs-lookup"><span data-stu-id="75341-140">For a complete description of how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll, read the following sections.</span></span>  

## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="75341-141">このトピックでポーリングしていますか</span><span class="sxs-lookup"><span data-stu-id="75341-141">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="75341-142">示すために、このトピックでどのように[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]データの変更、GET_ACTIVITYS を使用するストアド プロシージャを使用して、メッセージの受信をサポートには、Oracle データベースで ACCOUNTACTIVITY テーブルをポーリングするプロシージャが格納されています。</span><span class="sxs-lookup"><span data-stu-id="75341-142">In this topic, to demonstrate how the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports receiving data change messages using stored procedures, you use the GET_ACTIVITYS stored procedure to poll the ACCOUNTACTIVITY table in the Oracle database.</span></span> <span data-ttu-id="75341-143">このストアド プロシージャは ACCOUNT_PKG パッケージで使用できます。</span><span class="sxs-lookup"><span data-stu-id="75341-143">This stored procedure is available with the ACCOUNT_PKG package.</span></span> <span data-ttu-id="75341-144">データベースでこれらのオブジェクトを作成するサンプルに付属の SQL スクリプトを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="75341-144">You can run the SQL scripts provided with the samples to create these objects in the database.</span></span>  

> [!NOTE]
>  <span data-ttu-id="75341-145">例では、このトピックでのポーリングに、ACCOUNTACTIVITY の表に、ベース データベース テーブルは、サンプルに付属のスクリプトを実行してこれを作成します。</span><span class="sxs-lookup"><span data-stu-id="75341-145">The example in this topic polls the ACCOUNTACTIVITY table, which is a base database table created by running the scripts provided with the samples.</span></span> <span data-ttu-id="75341-146">インターフェイス テーブルなど、他のテーブルをポーリングするには、このトピックの説明に従って、同じような手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75341-146">You must perform similar procedures as described in this topic to poll any other table, including interface tables.</span></span>  

 <span data-ttu-id="75341-147">ポーリング操作を説明するために、次の項目行います。</span><span class="sxs-lookup"><span data-stu-id="75341-147">To demonstrate a polling operation, we do the following:</span></span>  

-   <span data-ttu-id="75341-148">SELECT ステートメントを指定、 **PolledDataAvailableStatement**データがある、テーブルの中にポーリングされます (ACCOUNTACTIVITY) を決定するプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="75341-148">Specify a SELECT statement for the **PolledDataAvailableStatement** binding property to determine where the table being polled (ACCOUNTACTIVITY) has any data.</span></span> <span data-ttu-id="75341-149">この例では、としては、このバインド プロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="75341-149">In this example, you can set this binding property as:</span></span>  

    ```  
    SELECT COUNT (*) FROM ACCOUNTACTIVITY  
    ```  

     <span data-ttu-id="75341-150">これにより、ACCOUNTACTIVITY テーブルにいくつかのレコードがある場合にのみ、アダプターがポーリング ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="75341-150">This ensures that the adapter executes the polling statement only when the ACCOUNTACTIVITY table has some records.</span></span>  

-   <span data-ttu-id="75341-151">一部として、要求メッセージを提供することで、GET_ACTIVITYS、ストアド プロシージャを実行、 **PollingInput**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="75341-151">Execute a stored procedure, GET_ACTIVITYS, by providing the request message as part of the **PollingInput** binding property.</span></span> <span data-ttu-id="75341-152">このストアド プロシージャは ACCOUNTACTIVITY テーブル内のすべての行を取得し、アダプターから応答メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="75341-152">This stored procedure will retrieve all the rows in the ACCOUNTACTIVITY table and you will get a response message from the adapter.</span></span>  

-   <span data-ttu-id="75341-153">ブロックを実行する PL/SQL の一部として、 **PostPollStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="75341-153">Execute a PL/SQL block as part of the **PostPollStatement** binding property.</span></span> <span data-ttu-id="75341-154">このステートメントは、ACCOUNTACTIVITY テーブルからのすべてのデータをデータベース内の別のテーブルに移動されます。</span><span class="sxs-lookup"><span data-stu-id="75341-154">This statement will move all data from ACCOUNTACTIVITY table to another table in the database.</span></span> <span data-ttu-id="75341-155">これは、次回後**PollingInput**が実行すると、それをフェッチできませんすべてのデータとその GET_ACTIVITYS ストアド プロシージャは空の応答メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="75341-155">After this happens, the next time **PollingInput** is executed, it will not fetch any data and hence the GET_ACTIVITYS stored procedure will return an empty response message.</span></span>  

-   <span data-ttu-id="75341-156">多くのデータは ACCOUNTACTIVITY テーブルに追加されるまで新しいレコードを含む ACCOUNTACTIVITY テーブルを再作成する必要がありますので、空の応答メッセージを取得する続けます。</span><span class="sxs-lookup"><span data-stu-id="75341-156">Until more data is added to the ACCOUNTACTIVITY table, you will continue to get empty response messages so you must repopulate the ACCOUNTACTIVITY table with new records.</span></span> <span data-ttu-id="75341-157">サンプルで提供される more_activity_data.sql スクリプトを実行して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="75341-157">You can do so by running the more_activity_data.sql script provided with the samples.</span></span> <span data-ttu-id="75341-158">このスクリプトを実行した後、次のポーリング操作によって新しいレコードをテーブルに挿入がフェッチされます。</span><span class="sxs-lookup"><span data-stu-id="75341-158">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span>  

## <a name="configuring-polling-in-the-wcf-service-model"></a><span data-ttu-id="75341-159">WCF サービス モデルでのポーリングの構成</span><span class="sxs-lookup"><span data-stu-id="75341-159">Configuring Polling in the WCF Service Model</span></span>  
 <span data-ttu-id="75341-160">使用したストアド プロシージャを使用してポーリングする、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] WCF サービス モデルでは、する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75341-160">To poll using stored procedures with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with the WCF service model, you must:</span></span>  

- <span data-ttu-id="75341-161">ポーリングするものを使用してストアド プロシージャの WCF サービス コントラクト (インターフェイス) を生成します。</span><span class="sxs-lookup"><span data-stu-id="75341-161">Generate a WCF service contract (interface) for the stored procedure using which you are going to poll.</span></span> <span data-ttu-id="75341-162">この例での WCF サービス コントラクトを生成する必要があります、 **GET_ACTIVITYS**受信操作としてストアド プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="75341-162">For this example, you must generate the WCF service contract for the **GET_ACTIVITYS** stored procedure as an inbound operation.</span></span> <span data-ttu-id="75341-163">これを行うには、使用する可能性があります、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="75341-163">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  

- <span data-ttu-id="75341-164">このインターフェイスからの WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="75341-164">Implement a WCF service from this interface.</span></span>  

- <span data-ttu-id="75341-165">サービス ホストを使用してこの WCF サービス ホスト (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="75341-165">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  

## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="75341-166">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="75341-166">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="75341-167">このトピックでのポーリング、GET_ACTIVITYS を使用して ACCOUNTACTIVITY データベース テーブルの例はストアド プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="75341-167">The examples in this topic poll the ACCOUNTACTIVITY database table using the GET_ACTIVITYS stored procedure.</span></span> <span data-ttu-id="75341-168">テーブルとストアド プロシージャを生成するスクリプトは、サンプルで提供されます。</span><span class="sxs-lookup"><span data-stu-id="75341-168">A script to generate the table and the stored procedure is supplied with the samples.</span></span> <span data-ttu-id="75341-169">サンプルの詳細については、[Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75341-169">For more information about the samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="75341-170">サンプルについては、 **StoredProcPolling_ServiceModel**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="75341-170">A sample, **StoredProcPolling_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  

## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="75341-171">WCF サービス コントラクトとクラス</span><span class="sxs-lookup"><span data-stu-id="75341-171">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="75341-172">使用することができます、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) とサポートのクラスを作成する、 **GET_ACTIVITYS**操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="75341-172">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **GET_ACTIVITYS** inbound operation.</span></span> <span data-ttu-id="75341-173">WCF サービス コントラクトを生成する詳細については、[WCF クライアントまたは Oracle E-business Suite ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75341-173">For more information about generating a WCF service contract, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  

### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="75341-174">WCF サービス コントラクト (インターフェイス)</span><span class="sxs-lookup"><span data-stu-id="75341-174">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="75341-175">次のコードに対して生成された WCF サービス コントラクト (インターフェイス) を示しています、 **GET_ACTIVITYS**操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="75341-175">The following code shows the WCF service contract (interface) generated for the **GET_ACTIVITYS** inbound operation.</span></span>  

```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/", ConfigurationName="PollingPackageApis_APPS_ACCOUNT_PKG")]  
public interface PollingPackageApis_APPS_ACCOUNT_PKG {  

    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/PollingPackageApis/APPS/ACCOUNT_PKG) of message GET_ACTIVITYS   
    // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="PollingPackageApis/APPS/ACCOUNT_PKG/GET_ACTIVITYS")]  
    void GET_ACTIVITYS(GET_ACTIVITYS request);  
}  
```  

### <a name="the-message-contracts"></a><span data-ttu-id="75341-176">メッセージ コントラクト</span><span class="sxs-lookup"><span data-stu-id="75341-176">The Message Contracts</span></span>  
 <span data-ttu-id="75341-177">メッセージ コントラクトを次に、 **GET_ACTIVITYS**操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="75341-177">Following is the message contract for the **GET_ACTIVITYS** inbound operation.</span></span>  

```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="GET_ACTIVITYS", WrapperNamespace="http://schemas.microsoft.com/OracleEBS/2008/05/PollingPackageApis/APPS/ACCOUNT_PK" +  
    "G", IsWrapped=true)]  
public partial class GET_ACTIVITYS {  

    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/PollingPackageApis/APPS/ACCOUNT_PK" +  
        "G", Order=0)]  
    public schemas.microsoft.com.OracleEBS._2008._05.RecordTypes.APPS.ACCOUNT_PKG.GET_ACTIVITYS.OUTRECSRecord[] OUTRECS;  

    public GET_ACTIVITYS() {  
    }  

    public GET_ACTIVITYS(schemas.microsoft.com.OracleEBS._2008._05.RecordTypes.APPS.ACCOUNT_PKG.GET_ACTIVITYS.OUTRECSRecord[] OUTRECS) {  
        this.OUTRECS = OUTRECS;  
    }  
}  
```  

### <a name="wcf-service-class"></a><span data-ttu-id="75341-178">WCF サービス クラス</span><span class="sxs-lookup"><span data-stu-id="75341-178">WCF Service Class</span></span>  
 <span data-ttu-id="75341-179">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をサービス コントラクト (インターフェイス) から実装された WCF サービス クラスのスタブを持つファイルも生成されます。</span><span class="sxs-lookup"><span data-stu-id="75341-179">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="75341-180">ファイルの名前は、OracleEBSBindingService.cs です。</span><span class="sxs-lookup"><span data-stu-id="75341-180">The name of the file is OracleEBSBindingService.cs.</span></span> <span data-ttu-id="75341-181">処理するロジックを挿入することができます、 **GET_ACTIVITYS**このクラスに直接操作します。</span><span class="sxs-lookup"><span data-stu-id="75341-181">You can insert the logic to process the **GET_ACTIVITYS** operation directly into this class.</span></span> <span data-ttu-id="75341-182">次のコードによって生成される WCF サービス クラスを示しています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="75341-182">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  

```  
namespace OracleEBSBindingNamespace {  

    public class OracleEBSBindingService : PollingPackageApis_APPS_ACCOUNT_PKG {  

        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/PollingPackageApis/APPS/ACCOUNT_PKG) of message GET_ACTIVITYS   
        // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
        public virtual void GET_ACTIVITYS(GET_ACTIVITYS request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  

## <a name="receiving-inbound-messages-for-polling-using-a-stored-procedure"></a><span data-ttu-id="75341-183">ストアド プロシージャを使用してポーリングの受信メッセージの受信</span><span class="sxs-lookup"><span data-stu-id="75341-183">Receiving Inbound Messages For Polling Using a Stored Procedure</span></span>  
 <span data-ttu-id="75341-184">このセクションを使用してポーリングの受信メッセージを受信する .NET アプリケーションを作成する方法の説明、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="75341-184">This section provides instructions on how to write a .NET application to receive inbound polling messages using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  

#### <a name="to-receive-polling-messages-using-a-stored-procedure"></a><span data-ttu-id="75341-185">ストアド プロシージャを使用してポーリング メッセージを受信するには</span><span class="sxs-lookup"><span data-stu-id="75341-185">To receive polling messages using a stored procedure</span></span>  

1. <span data-ttu-id="75341-186">使用して、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) とのヘルパー クラスを生成する、 **GET_ACTIVITYS**操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="75341-186">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **GET_ACTIVITYS** inbound operation.</span></span> <span data-ttu-id="75341-187">詳細については、[WCF クライアントまたは Oracle E-business Suite ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75341-187">For more information, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span> <span data-ttu-id="75341-188">必要に応じて、サービス コントラクトとヘルパー クラスを生成するときにバインドのプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="75341-188">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="75341-189">これは、生成された構成ファイルで設定は正しくことを保証します。</span><span class="sxs-lookup"><span data-stu-id="75341-189">This guarantees that they are properly set in the generated configuration file.</span></span>  

2. <span data-ttu-id="75341-190">手順 1. で生成されたインターフェイスとヘルパー クラスからの WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="75341-190">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="75341-191">**GET_ACTIVITYS**から受信したデータの処理エラーが発生した場合、このクラスのメソッドは、ポーリング トランザクションを中止する例外をスローできます、 **GET_ACTIVITYS**操作です。メソッドは何も返しません。</span><span class="sxs-lookup"><span data-stu-id="75341-191">The **GET_ACTIVITYS** method of this class can throw an exception to abort the polling transaction, if an error is encountered processing the data received from the **GET_ACTIVITYS** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="75341-192">次のように、WCF サービス クラスを属性する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75341-192">You must attribute the WCF service class as follows:</span></span>  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  

    <span data-ttu-id="75341-193">内で、 **GET_ACTIVITYS**メソッドを直接、アプリケーション ロジックを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="75341-193">Within the **GET_ACTIVITYS** method, you can implement your application logic directly.</span></span> <span data-ttu-id="75341-194">このクラスは、OracleEBSBindingService.cs で確認できます。</span><span class="sxs-lookup"><span data-stu-id="75341-194">This class can be found in OracleEBSBindingService.cs.</span></span> <span data-ttu-id="75341-195">この例では、このコードはサブ クラス、 **OracleEBSBindingService**クラス。</span><span class="sxs-lookup"><span data-stu-id="75341-195">This code in this example sub-classes the **OracleEBSBindingService** class.</span></span> <span data-ttu-id="75341-196">このコードでは、ポーリング メッセージは、受信され、コンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="75341-196">In this code, the polling message received and is written to the console.</span></span>  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  

   public class PollingService : OracleEBSBindingNamespace.OracleEBSBindingService  
   {  
       public override void  GET_ACTIVITYS(GET_ACTIVITYS request)  
       {  
           Console.WriteLine("\nNew Polling Records Received");  
           Console.WriteLine("*************************************************");  
           Console.WriteLine("Tx Id\tAccount\tAmount\tProcessed");  
           for (int i = 0; i < request.OUTRECS.Length; i++)  
           {  
               Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
               request.OUTRECS[i].TID,  
               request.OUTRECS[i].ACCOUNT,  
               request.OUTRECS[i].AMOUNT,  
               request.OUTRECS[i].PROCESSED);  
           }  
           Console.WriteLine("*************************************************");  
           Console.WriteLine("\nHit <RETURN> to stop polling");  
       }  
   }  
   ```  

3. <span data-ttu-id="75341-197">URI の一部として資格情報を渡すことを回避するために、次のクラスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75341-197">You must implement the following class to avoid passing credentials as part of the URI.</span></span> <span data-ttu-id="75341-198">アプリケーションの後半部分の資格情報を渡すには、このクラスをインスタンス化されます。</span><span class="sxs-lookup"><span data-stu-id="75341-198">In the latter part of the application, you will instantiate this class to pass on the credentials.</span></span>  

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

4. <span data-ttu-id="75341-199">作成、 **OracleEBSBinding**とバインドのプロパティを指定することで、ポーリング操作を構成します。</span><span class="sxs-lookup"><span data-stu-id="75341-199">Create an **OracleEBSBinding** and configure the polling operation by specifying the binding properties.</span></span> <span data-ttu-id="75341-200">コードで明示的に、または構成で宣言的に、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="75341-200">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="75341-201">指定する必要がありますには、少なくとも、 **InboundOperationType**、 **PolledDataAvailableStatement**、 **PollingInput**、および**PollingAction**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="75341-201">At a minimum, you must specify the **InboundOperationType**, **PolledDataAvailableStatement**, **PollingInput**, and **PollingAction** binding properties.</span></span>  

   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   binding.InboundOperationType = InboundOperation.Polling;  
   binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM ACCOUNTACTIVITY";  
   binding.PollingInput = "<GET_ACTIVITYS xmlns='http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/APPS/ACCOUNT_PKG'><INRECS>OPEN ? FOR SELECT * FROM ACCOUNTACTIVITY</INRECS></GET_ACTIVITYS>";  
   binding.PollingAction = "PollingPackageApis/APPS/ACCOUNT_PKG/GET_ACTIVITYS";  
   binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
   ```  

   > [!NOTE]
   >  <span data-ttu-id="75341-202">注意の値、 **PollingInput**を呼び出すための要求メッセージにはプロパティのバインドが含まれています、 **GET_ACTIVITYS**送信操作としてストアド プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="75341-202">Note that the value for the **PollingInput** binding property contains the request message for invoking the **GET_ACTIVITYS** stored procedure as an outbound operation.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="75341-203">この例ではデータベース テーブルをポーリングするため必要はありませんアプリケーション コンテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="75341-203">In this example, because you are polling a database table, you do not need to set the applications context.</span></span> <span data-ttu-id="75341-204">ただし場合は、インターフェイス テーブルをポーリングする必要がありますコンテキストを設定するアプリケーションを指定して、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="75341-204">However, if you were polling an interface table, you must set the applications context by specifying the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="75341-205">アプリケーションのコンテキストの詳細については、[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75341-205">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  

5. <span data-ttu-id="75341-206">Oracle E-business Suite の資格情報を指定するには、インスタンス化する、 **PollingCredentials**手順 3 で作成したクラス。</span><span class="sxs-lookup"><span data-stu-id="75341-206">Specify Oracle E-Business Suite credentials by instantiating the **PollingCredentials** class you created in Step 3.</span></span>  

   ```  
   PollingCredentials credentials = new PollingCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  
   ```  

6. <span data-ttu-id="75341-207">手順 2 で作成した WCF サービスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="75341-207">Create an instance of the WCF service created in step 2.</span></span>  

   ```  
   // create service instance  
   PollingService service = new PollingService();  
   ```  

7. <span data-ttu-id="75341-208">インスタンスを作成**System.ServiceModel.ServiceHost** WCF サービスと基本の接続 URI を使用しています。</span><span class="sxs-lookup"><span data-stu-id="75341-208">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="75341-209">基本の接続 URI は、指定されている場合、受信の ID を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="75341-209">The base connection URI cannot contain the inbound ID, if specified.</span></span> <span data-ttu-id="75341-210">また、資格情報をここで渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="75341-210">You must also pass the credentials here.</span></span>  

   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
   ServiceHost serviceHost = new ServiceHost(service, baseUri);  
   serviceHost.Description.Behaviors.Add(credentials);  

   ```  

8. <span data-ttu-id="75341-211">サービス ホストにサービス エンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="75341-211">Add a service endpoint to the service host.</span></span> <span data-ttu-id="75341-212">これを行うには :</span><span class="sxs-lookup"><span data-stu-id="75341-212">To do this:</span></span>  

   -   <span data-ttu-id="75341-213">手順 4. で作成したバインドを使用します。</span><span class="sxs-lookup"><span data-stu-id="75341-213">Use the binding created in step 4.</span></span>  

   -   <span data-ttu-id="75341-214">接続の資格情報を含む URI を指定し、必要に応じて、受信の id。</span><span class="sxs-lookup"><span data-stu-id="75341-214">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  

   -   <span data-ttu-id="75341-215">MS_SAMPLE_EMPLOYEE インターフェイス テーブルをポーリングするには、"PollingPackageApis_APPS_ACCOUNT_PKG"としてコントラクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="75341-215">Specify the contract as "PollingPackageApis_APPS_ACCOUNT_PKG" to poll the MS_SAMPLE_EMPLOYEE interface table.</span></span>  

   ```  
   // Add service endpoint: be sure to specify PollingPackageApis_APPS_ACCOUNT_PKG as the contract  
   Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
   serviceHost.AddServiceEndpoint("PollingPackageApis_APPS_ACCOUNT_PKG", binding, ConnectionUri);  
   ```  

9. <span data-ttu-id="75341-216">ポーリングのデータを受信するには、サービス ホストを開きます。</span><span class="sxs-lookup"><span data-stu-id="75341-216">To receive polling data, open the service host.</span></span> <span data-ttu-id="75341-217">アダプターは、クエリが結果セットを返すたびにデータを返します。</span><span class="sxs-lookup"><span data-stu-id="75341-217">The adapter will return data whenever the query returns a result set.</span></span>  

    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  

10. <span data-ttu-id="75341-218">ポーリングを終了するには、サービス ホストを閉じます。</span><span class="sxs-lookup"><span data-stu-id="75341-218">To terminate polling, close the service host.</span></span>  

    > [!IMPORTANT]
    >  <span data-ttu-id="75341-219">アダプターは、サービス ホストが閉じられるまでポーリングを続行します。</span><span class="sxs-lookup"><span data-stu-id="75341-219">The adapter will continue to poll until the service host is closed.</span></span>  

    ```  
    serviceHost.Close();  
    ```  

### <a name="example"></a><span data-ttu-id="75341-220">例</span><span class="sxs-lookup"><span data-stu-id="75341-220">Example</span></span>  
 <span data-ttu-id="75341-221">次の例では、使用、GET_ACTIVITYS ACCOUNTACTIVITY データベース テーブルをポーリングするポーリング アプリケーション ストアド プロシージャを示します。</span><span class="sxs-lookup"><span data-stu-id="75341-221">The following example shows a polling application that polls the ACCOUNTACTIVITY database table using the GET_ACTIVITYS stored procedure.</span></span> <span data-ttu-id="75341-222">**PollingInput** ACCOUNTACTIVITY テーブルからすべてのデータを読み取る GET_ACTIVITYS ストアド プロシージャを呼び出す要求メッセージを含むプロパティのバインドと、ポーリング後ステートメントは、ACCOUNTACTIVITY からすべてのデータを移動しますACTIVITYHISTORY テーブル。</span><span class="sxs-lookup"><span data-stu-id="75341-222">The **PollingInput** binding property contains the request message to invoke the GET_ACTIVITYS stored procedure that reads all the data from the ACCOUNTACTIVITY table and the post poll statement moves all the data from ACCOUNTACTIVITY to ACTIVITYHISTORY table.</span></span>  

 <span data-ttu-id="75341-223">最初のポーリング メッセージは、ACCOUNTACTIVITY テーブルからすべてのレコードを提供します。</span><span class="sxs-lookup"><span data-stu-id="75341-223">The first polling message gives all the records from the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="75341-224">ポーリング後ステートメント、レコードが削除されるため、後続のポーリング メッセージはレコードがありません。</span><span class="sxs-lookup"><span data-stu-id="75341-224">Subsequent polling messages will not contain any records because the post poll statement deletes the records.</span></span> <span data-ttu-id="75341-225">多くのデータは ACCOUNTACTIVITY テーブルに追加されるまで、新しいレコードを含む ACCOUNTACTIVITY テーブルを再作成する必要がありますのでにポーリング メッセージを取得できません。</span><span class="sxs-lookup"><span data-stu-id="75341-225">Until more data is added to the ACCOUNTACTIVITY table, you will not get any polling messages so you must repopulate the ACCOUNTACTIVITY table with new records.</span></span> <span data-ttu-id="75341-226">サンプルで提供される more_activity_data.sql スクリプトを実行して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="75341-226">You can do so by running the more_activity_data.sql script provided with the samples.</span></span>  

 <span data-ttu-id="75341-227">このスクリプトを実行した後、次のポーリング操作によって新しいレコードをテーブルに挿入がフェッチされます。</span><span class="sxs-lookup"><span data-stu-id="75341-227">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span> <span data-ttu-id="75341-228">アダプターのポーリングを押して、サービス ホストを終了するまでは引き続き`<RETURN>`します。</span><span class="sxs-lookup"><span data-stu-id="75341-228">The adapter will continue to poll until you close the service host by pressing `<RETURN>`.</span></span>  

```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using Microsoft.Adapters.OracleEBS;  
using Microsoft.ServiceModel.Channels;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Collections.ObjectModel;  

namespace StoredProcPolling_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  

    public class PollingService : OracleEBSBindingNamespace.OracleEBSBindingService  
    {  
        public override void  GET_ACTIVITYS(GET_ACTIVITYS request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Tx Id\tAccount\tAmount\tProcessed");  
            for (int i = 0; i < request.OUTRECS.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.OUTRECS[i].TID,  
                request.OUTRECS[i].ACCOUNT,  
                request.OUTRECS[i].AMOUNT,  
                request.OUTRECS[i].PROCESSED);  
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

                OracleEBSBinding binding = new OracleEBSBinding();  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM ACCOUNTACTIVITY";  
                binding.PollingInput = "<GET_ACTIVITYS xmlns='http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/APPS/ACCOUNT_PKG'><INRECS>OPEN ? FOR SELECT * FROM ACCOUNTACTIVITY</INRECS></GET_ACTIVITYS>";  
                binding.PollingAction = "PollingPackageApis/APPS/ACCOUNT_PKG/GET_ACTIVITYS";  
                binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  

                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  

                // This URI is used to initialize the ServiceHost. It cannot contain  
                // an InboundID; otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  

                PollingCredentials credentials = new PollingCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  

                Console.WriteLine("Opening service host...");  
                PollingService service = new PollingService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("PollingPackageApis_APPS_ACCOUNT_PKG", binding, ConnectionUri);  
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

## <a name="see-also"></a><span data-ttu-id="75341-229">参照</span><span class="sxs-lookup"><span data-stu-id="75341-229">See Also</span></span>  
 [<span data-ttu-id="75341-230">WCF サービス モデルを使用してポーリング Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="75341-230">Poll Oracle E-Business Suite using the WCF service model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-the-wcf-service-model.md)