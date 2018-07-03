---
title: SELECT ステートメントを使用して WCF サービス モデルとポーリング Oracle E-business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 521d58e4-73b1-48a8-9a0a-9e733386c1b5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8484acc15d2328ab444a8df6e55dc0ff952899a6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000699"
---
# <a name="poll-oracle-e-business-suite-using-select-statement-with-the-wcf-service-model"></a><span data-ttu-id="c2116-102">SELECT ステートメントを使用して WCF サービス モデルとポーリング Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="c2116-102">Poll Oracle E-Business Suite using SELECT statement with the WCF service model</span></span>
<span data-ttu-id="c2116-103">構成することができます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を継続的に、インターフェイス テーブルをポーリングする SELECT ステートメントを使用して、定期的なデータ変更メッセージを受信するビュー、テーブル、および Oracle E-business Suite でのビューのインターフェイスします。</span><span class="sxs-lookup"><span data-stu-id="c2116-103">You can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive periodic data-change messages by using a SELECT statement to continuously poll the interface tables, interface views, tables and views in Oracle E-Business Suite.</span></span> <span data-ttu-id="c2116-104">Oracle E-business Suite をポーリングするアダプターを定期的に実行するポーリング ステートメントと SELECT ステートメントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c2116-104">You can specify a SELECT statement as a polling statement that the adapter executes periodically to poll Oracle E-Business Suite.</span></span> <span data-ttu-id="c2116-105">ポスト ポーリング PL/SQL コード ブロックを指定することも、アダプターがポーリング ステートメントが実行された後に実行します。</span><span class="sxs-lookup"><span data-stu-id="c2116-105">You can also specify a post-poll PL/SQL code block that the adapter executes after the polling statement is executed.</span></span>  

 <span data-ttu-id="c2116-106">ポーリングを有効にする、このトピックの説明に従って、特定のバインド プロパティの条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2116-106">To enable polling, you must specify certain binding properties as described in this topic.</span></span>  <span data-ttu-id="c2116-107">アダプターがポーリングをサポートする方法の詳細については、次を参照してください。[受信呼び出しのポーリングを使用してサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)します。</span><span class="sxs-lookup"><span data-stu-id="c2116-107">For more information about how the adapter supports polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  

## <a name="configuring-a-polling-operation-with-oracle-e-business-suite-adapter-binding-properties"></a><span data-ttu-id="c2116-108">Oracle E-business Suite アダプターのバインドのプロパティをポーリング操作を構成します。</span><span class="sxs-lookup"><span data-stu-id="c2116-108">Configuring a Polling Operation with Oracle E-Business Suite Adapter Binding Properties</span></span>  
 <span data-ttu-id="c2116-109">次の表にまとめたものです、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]メッセージのバインドのプロパティを使用するデータを受信するアダプターの構成を変更します。</span><span class="sxs-lookup"><span data-stu-id="c2116-109">The following table summarizes the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding properties that you use to configure the adapter to receive data change messages.</span></span> <span data-ttu-id="c2116-110">ポーリング アプリケーションを実行中に、これらのバインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2116-110">You must specify these binding properties while running the polling application.</span></span>  


|         <span data-ttu-id="c2116-111">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="c2116-111">Binding Property</span></span>         |                                                                                                                                                                                                                            <span data-ttu-id="c2116-112">説明</span><span class="sxs-lookup"><span data-stu-id="c2116-112">Description</span></span>                                                                                                                                                                                                                             |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="c2116-113">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="c2116-113">**InboundOperationType**</span></span>     |                                                                                                                                                                          <span data-ttu-id="c2116-114">実行するかどうかを指定します**ポーリング**または**通知**操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="c2116-114">Specifies whether you want to perform **Polling** or **Notification** inbound operation.</span></span> <span data-ttu-id="c2116-115">既定値は**ポーリング**します。</span><span class="sxs-lookup"><span data-stu-id="c2116-115">Default is **Polling**.</span></span>                                                                                                                                                                          |
| <span data-ttu-id="c2116-116">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="c2116-116">**PolledDataAvailableStatement**</span></span> |                                                                                                             <span data-ttu-id="c2116-117">すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="c2116-117">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="c2116-118">指定した SELECT ステートメントのレコードを使用できる場合にのみ、 **PollingInput**プロパティのバインドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="c2116-118">Only if a record is available, the SELECT statement you specify for the **PollingInput** binding property will be executed.</span></span>                                                                                                              |
|       <span data-ttu-id="c2116-119">**PollingInterval**</span><span class="sxs-lookup"><span data-stu-id="c2116-119">**PollingInterval**</span></span>        | <span data-ttu-id="c2116-120">秒単位で間隔を指定、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]に指定されたステートメントが実行される、 **PolledDataAvailableStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="c2116-120">Specifies the interval, in seconds, at which the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="c2116-121">既定値は 30 秒です。</span><span class="sxs-lookup"><span data-stu-id="c2116-121">The default is 30 seconds.</span></span> <span data-ttu-id="c2116-122">ポーリング間隔は、連続するポーリングの間隔を決定します。</span><span class="sxs-lookup"><span data-stu-id="c2116-122">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="c2116-123">ステートメントは、指定した期間内で実行される、アダプターが間隔内の残りの時間の間スリープします。</span><span class="sxs-lookup"><span data-stu-id="c2116-123">If the statement is executed within the specified interval, the adapter sleeps for the remaining time in the interval.</span></span> |
|         <span data-ttu-id="c2116-124">**PollingInput**</span><span class="sxs-lookup"><span data-stu-id="c2116-124">**PollingInput**</span></span>         |                         <span data-ttu-id="c2116-125">ポーリング ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="c2116-125">Specifies the polling statement.</span></span> <span data-ttu-id="c2116-126">SELECT ステートメントを使用してポーリングする、このバインドのプロパティの SELECT ステートメントを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2116-126">To poll using a SELECT statement, you must specify a SELECT statement for this binding property.</span></span> <span data-ttu-id="c2116-127">既定値は null です。</span><span class="sxs-lookup"><span data-stu-id="c2116-127">The default is null.</span></span><br /><br /> <span data-ttu-id="c2116-128">値を指定する必要があります**PollingInput**ポーリングを有効にするプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="c2116-128">You must specify a value for **PollingInput** binding property to enable polling.</span></span> <span data-ttu-id="c2116-129">ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="c2116-129">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span>                          |
|        <span data-ttu-id="c2116-130">**PollingAction**</span><span class="sxs-lookup"><span data-stu-id="c2116-130">**PollingAction**</span></span>         |                                                                                                                <span data-ttu-id="c2116-131">ポーリング操作のアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c2116-131">Specifies the action for the polling operation.</span></span> <span data-ttu-id="c2116-132">使用して、操作に対して生成されたサービスのインターフェイスからポーリング アクションを決定することができます、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c2116-132">You can determine the polling action from the service interface generated for the operation using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span>                                                                                                                |
|      <span data-ttu-id="c2116-133">**PostPollStatement**</span><span class="sxs-lookup"><span data-stu-id="c2116-133">**PostPollStatement**</span></span>       |                                                                                                                                                                  <span data-ttu-id="c2116-134">指定されたステートメントの後に実行されるステートメント ブロックを指定します、 **PollingInput**プロパティのバインドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c2116-134">Specifies a statement block that is executed after the statement specified by the **PollingInput** binding property is executed.</span></span>                                                                                                                                                                  |
|      <span data-ttu-id="c2116-135">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="c2116-135">**PollWhileDataFound**</span></span>      |                                    <span data-ttu-id="c2116-136">指定するかどうか、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ポーリング間隔を無視し、継続的にデータがポーリングされるテーブルで使用できる場合に、ポーリング ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="c2116-136">Specifies whether the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ignores the polling interval and continuously executes the polling statement, if data is available in the table being polled.</span></span> <span data-ttu-id="c2116-137">テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔でポーリング ステートメントを実行する元に戻します。</span><span class="sxs-lookup"><span data-stu-id="c2116-137">If no data is available in the table, the adapter reverts to execute the polling statement at the specified polling interval.</span></span> <span data-ttu-id="c2116-138">既定値は false です。</span><span class="sxs-lookup"><span data-stu-id="c2116-138">Default is false.</span></span>                                     |

 <span data-ttu-id="c2116-139">これらのプロパティの詳細については、次を参照してください。 [Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="c2116-139">For a more complete description of these properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="c2116-140">使用する方法の詳細については、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースをポーリングするさらに読み進める。</span><span class="sxs-lookup"><span data-stu-id="c2116-140">For a complete description of how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll the Oracle database, read further.</span></span>  

## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="c2116-141">このトピックでポーリングしていますか</span><span class="sxs-lookup"><span data-stu-id="c2116-141">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="c2116-142">示すために、このトピックの「方法、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] SELECT ステートメントを使用してメッセージを変更するデータの受信をサポート、ポーリングすると、 **MS_SAMPLE_EMPLOYEE**インターフェイス テーブルに、**アプリケーション オブジェクト ライブラリ**アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="c2116-142">In this topic, to demonstrate how the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports receiving data change messages using SELECT statements, you poll the **MS_SAMPLE_EMPLOYEE** interface table in the **Application Object Library** application.</span></span> <span data-ttu-id="c2116-143">Oracle E-business Suite でこれらのオブジェクトを作成するサンプルで提供される create_apps_artifacts.sql スクリプトを実行するときに、このテーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c2116-143">This table is created when you run the create_apps_artifacts.sql script provided with the samples to create these objects in Oracle E-Business Suite.</span></span>  

 <span data-ttu-id="c2116-144">ポーリング操作を説明するために、次の項目行います。</span><span class="sxs-lookup"><span data-stu-id="c2116-144">To demonstrate a polling operation, we do the following:</span></span>  

-   <span data-ttu-id="c2116-145">SELECT ステートメントを指定、 **PolledDataAvailableStatement**データがある場所インターフェイス テーブルの中にポーリングされます (MS_SAMPLE_EMPLOYEE) を決定するプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="c2116-145">Specify a SELECT statement for the **PolledDataAvailableStatement** binding property to determine where the interface table being polled (MS_SAMPLE_EMPLOYEE) has any data.</span></span> <span data-ttu-id="c2116-146">この例では、としては、このバインド プロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="c2116-146">In this example, you can set this binding property as:</span></span>  

    ```  
    SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE  
    ```  

     <span data-ttu-id="c2116-147">これにより、MS_SAMPLE_EMPLOYEE インターフェイス テーブルにいくつかのレコードがある場合にのみ、アダプターがポーリング ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="c2116-147">This ensures that the adapter executes the polling statement only when the MS_SAMPLE_EMPLOYEE interface table has some records.</span></span>  

-   <span data-ttu-id="c2116-148">SELECT ステートメントを指定、 **PollingInput**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="c2116-148">Specify a SELECT statement for the **PollingInput** binding property.</span></span> <span data-ttu-id="c2116-149">このステートメントは、MS_SAMPLE_EMPLOYEE インターフェイス テーブル内のすべての行を取得します。</span><span class="sxs-lookup"><span data-stu-id="c2116-149">This statement retrieves all the rows in the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="c2116-150">この例では、としては、このバインド プロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="c2116-150">In this example, you can set this binding property as:</span></span>  

    ```  
    SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE  
    ```  

    > [!NOTE]
    >  <span data-ttu-id="c2116-151">SELECT ステートメントで使用される FOR UPDATE 句の詳細については、次を参照してください。 [Oracle E-business Suite からのポーリングに基づいたデータ変更メッセージを受信](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md)します。</span><span class="sxs-lookup"><span data-stu-id="c2116-151">For information about the FOR UPDATE clause used in the SELECT statement, see [Receive polling-based data-changed messages from Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md).</span></span>  

-   <span data-ttu-id="c2116-152">DELETE ステートメントを指定の一部として、 **PostPollStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="c2116-152">Specify a DELETE statement as part of the **PostPollStatement** binding property.</span></span> <span data-ttu-id="c2116-153">このステートメントは、すべてのデータを MS_SAMPLE_EMPLOYEE インターフェイス テーブルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="c2116-153">This statement will delete all data from MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="c2116-154">この例では、としては、このバインド プロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="c2116-154">In this example, you can set this binding property as:</span></span>  

    ```  
    DELETE FROM MS_SAMPLE_EMPLOYEE  
    ```  

     <span data-ttu-id="c2116-155">このような場合は、次回の指定されたステートメント**PollingInput**は実行すると、それをフェッチできませんすべてのデータ。</span><span class="sxs-lookup"><span data-stu-id="c2116-155">After this happens, the next time the statement specified for **PollingInput** will be executed, it will not fetch any data.</span></span>  

-   <span data-ttu-id="c2116-156">多くのデータは MS_SAMPLE_EMPLOYEE インターフェイス テーブルに追加されるまで、新しいレコードを含む MS_SAMPLE_EMPLOYEE インターフェイス テーブルを再作成する必要がありますのでにポーリング メッセージを取得できません。</span><span class="sxs-lookup"><span data-stu-id="c2116-156">Until more data is added to the MS_SAMPLE_EMPLOYEE interface table, you will not get any polling messages so you must repopulate the MS_SAMPLE_EMPLOYEE interface table with new records.</span></span> <span data-ttu-id="c2116-157">サンプルで提供される insert_apps_data.sql スクリプトを実行して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c2116-157">You can do so by running the insert_apps_data.sql script provided with the samples.</span></span> <span data-ttu-id="c2116-158">このスクリプトを実行した後、次のポーリング操作によって新しいレコードをテーブルに挿入がフェッチされます。</span><span class="sxs-lookup"><span data-stu-id="c2116-158">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span>  

## <a name="configuring-polling-in-the-wcf-service-model"></a><span data-ttu-id="c2116-159">WCF サービス モデルでのポーリングの構成</span><span class="sxs-lookup"><span data-stu-id="c2116-159">Configuring Polling in the WCF Service Model</span></span>  
 <span data-ttu-id="c2116-160">使用してインターフェイス テーブルをポーリングする、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] WCF サービス モデルでは、する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2116-160">To poll an interface table using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with the WCF service model, you must:</span></span>  

- <span data-ttu-id="c2116-161">WCF サービス コントラクト (インターフェイス) を生成、**ポーリング**MS_SAMPLE_EMPLOYEE インターフェイス テーブルで操作します。</span><span class="sxs-lookup"><span data-stu-id="c2116-161">Generate a WCF service contract (interface) for the **Poll** operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="c2116-162">これを行うには、使用する可能性があります、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c2116-162">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  

- <span data-ttu-id="c2116-163">このインターフェイスからの WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="c2116-163">Implement a WCF service from this interface.</span></span>  

- <span data-ttu-id="c2116-164">サービス ホストを使用してこの WCF サービス ホスト (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="c2116-164">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  

## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="c2116-165">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="c2116-165">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="c2116-166">このトピックの例では、MS_SAMPLE_EMPLOYEE インターフェイス テーブルをポーリングします。</span><span class="sxs-lookup"><span data-stu-id="c2116-166">The examples in this topic poll the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="c2116-167">テーブルを生成するスクリプトは、サンプルで提供されます。</span><span class="sxs-lookup"><span data-stu-id="c2116-167">A script to generate the table is supplied with the samples.</span></span> <span data-ttu-id="c2116-168">サンプルの詳細については、次を参照してください。 [Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="c2116-168">For more information about the samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="c2116-169">サンプルについては、 **SelectPolling_ServiceModel**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="c2116-169">A sample, **SelectPolling_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  

## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="c2116-170">WCF サービス コントラクトとクラス</span><span class="sxs-lookup"><span data-stu-id="c2116-170">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="c2116-171">使用することができます、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) とサポートのクラスを作成する、**ポーリング**操作。</span><span class="sxs-lookup"><span data-stu-id="c2116-171">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **Polling** operation.</span></span> <span data-ttu-id="c2116-172">WCF サービス コントラクトを生成する詳細については、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="c2116-172">For more information about generating a WCF service contract, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  

### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="c2116-173">WCF サービス コントラクト (インターフェイス)</span><span class="sxs-lookup"><span data-stu-id="c2116-173">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="c2116-174">次のコードに対して生成された WCF サービス コントラクト (インターフェイス) を示しています、**ポーリング**MS_SAMPLE_EMPLOYEE インターフェイス テーブルに対する操作。</span><span class="sxs-lookup"><span data-stu-id="c2116-174">The following code shows the WCF service contract (interface) generated for the **Poll** operation on MS_SAMPLE_EMPLOYEE interface table.</span></span>  

```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/", ConfigurationName="InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE")]  
public interface InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE {  

    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE) of message Poll   
    // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE")]  
    void Poll(Poll request);  
}  
```  

### <a name="the-message-contracts"></a><span data-ttu-id="c2116-175">メッセージ コントラクト</span><span class="sxs-lookup"><span data-stu-id="c2116-175">The Message Contracts</span></span>  
 <span data-ttu-id="c2116-176">メッセージ コントラクトを次に、**ポーリング**MS_SAMPLE_EMPLOYEE インターフェイス テーブルに対する操作。</span><span class="sxs-lookup"><span data-stu-id="c2116-176">Following is the message contract for the **Poll** operation on MS_SAMPLE_EMPLOYEE interface table.</span></span>  

```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Poll", WrapperNamespace="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE" +  
    "_EMPLOYEE", IsWrapped=true)]  
public partial class Poll {  

    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE" +  
        "_EMPLOYEE", Order=0)]  
    public schemas.microsoft.com.OracleEBS._2008._05.TableViewRecord.APPS.MS_SAMPLE_EMPLOYEE.SelectRecord[] DATA;  

    public Poll() {  
    }  

    public Poll(schemas.microsoft.com.OracleEBS._2008._05.TableViewRecord.APPS.MS_SAMPLE_EMPLOYEE.SelectRecord[] DATA) {  
        this.DATA = DATA;  
    }  
}  
```  

### <a name="wcf-service-class"></a><span data-ttu-id="c2116-177">WCF サービス クラス</span><span class="sxs-lookup"><span data-stu-id="c2116-177">WCF Service Class</span></span>  
 <span data-ttu-id="c2116-178">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をサービス コントラクト (インターフェイス) から実装された WCF サービス クラスのスタブを持つファイルも生成されます。</span><span class="sxs-lookup"><span data-stu-id="c2116-178">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="c2116-179">ファイルの名前は、OracleEBSBindingService.cs です。</span><span class="sxs-lookup"><span data-stu-id="c2116-179">The name of the file is OracleEBSBindingService.cs.</span></span> <span data-ttu-id="c2116-180">処理するロジックを挿入することができます、**ポーリング**このクラスに直接操作します。</span><span class="sxs-lookup"><span data-stu-id="c2116-180">You can insert the logic to process the **Poll** operation directly into this class.</span></span> <span data-ttu-id="c2116-181">次のコードによって生成される WCF サービス クラスを示しています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c2116-181">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  

```  
namespace OracleEBSBindingNamespace {  

    public class OracleEBSBindingService : InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE {  

        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE) of message Poll   
        // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
        public virtual void Poll(Poll request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  

## <a name="receiving-inbound-messages-for-the-poll-operation-using-a-select-statement"></a><span data-ttu-id="c2116-182">SELECT ステートメントを使用して、ポーリング操作の受信メッセージの受信</span><span class="sxs-lookup"><span data-stu-id="c2116-182">Receiving Inbound Messages for the Poll Operation Using a SELECT Statement</span></span>  
 <span data-ttu-id="c2116-183">このセクションを使用してポーリングの受信メッセージを受信する .NET アプリケーションを作成する方法の説明、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c2116-183">This section provides instructions on how to write a .NET application to receive inbound polling messages using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  

#### <a name="to-receive-polling-messages-using-a-select-statement"></a><span data-ttu-id="c2116-184">SELECT ステートメントを使用してポーリング メッセージを受信するには</span><span class="sxs-lookup"><span data-stu-id="c2116-184">To receive polling messages using a SELECT statement</span></span>  

1. <span data-ttu-id="c2116-185">使用して、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) とのヘルパー クラスを生成する、**ポーリング**MS_SAMPLE_EMPLOYEE インターフェイス テーブルで操作します。</span><span class="sxs-lookup"><span data-stu-id="c2116-185">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **Poll** operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="c2116-186">詳細については、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="c2116-186">For more information, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span> <span data-ttu-id="c2116-187">必要に応じて、サービス コントラクトとヘルパー クラスを生成するときにバインドのプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="c2116-187">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="c2116-188">これは、生成された構成ファイルで設定は正しくことを保証します。</span><span class="sxs-lookup"><span data-stu-id="c2116-188">This guarantees that they are properly set in the generated configuration file.</span></span>  

2. <span data-ttu-id="c2116-189">手順 1. で生成されたインターフェイスとヘルパー クラスからの WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="c2116-189">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="c2116-190">**ポーリング**から受信したデータの処理エラーが発生した場合、このクラスのメソッドは、ポーリング トランザクションを中止する例外をスローできます、**ポーリング**操作ですそれ以外の場合メソッドではありません。何も返されます。</span><span class="sxs-lookup"><span data-stu-id="c2116-190">The **Poll** method of this class can throw an exception to abort the polling transaction, if an error is encountered processing the data received from the **Poll** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="c2116-191">次のように、WCF サービス クラスを属性する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2116-191">You must attribute the WCF service class as follows:</span></span>  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  

    <span data-ttu-id="c2116-192">内で、**ポーリング**メソッドを直接、アプリケーション ロジックを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="c2116-192">Within the **Poll** method, you can implement your application logic directly.</span></span> <span data-ttu-id="c2116-193">このクラスは、OracleEBSBindingService.cs で確認できます。</span><span class="sxs-lookup"><span data-stu-id="c2116-193">This class can be found in OracleEBSBindingService.cs.</span></span> <span data-ttu-id="c2116-194">この例では、このコードはサブ クラス、 **OracleEBSBindingService**クラス。</span><span class="sxs-lookup"><span data-stu-id="c2116-194">This code in this example sub-classes the **OracleEBSBindingService** class.</span></span> <span data-ttu-id="c2116-195">このコードでは、ポーリング メッセージは、受信され、コンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="c2116-195">In this code, the polling message received and is written to the console.</span></span>  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  

   public class PollingService : OracleEBSBindingNamespace.OracleEBSBindingService  
   {  
       public override void Poll(Poll request)  
       {  
           Console.WriteLine("\nNew Polling Records Received");  
           Console.WriteLine("*************************************************");  
           Console.WriteLine("Emp No\tName\tDesignation\tSalary");  
           for (int i = 0; i < request.DATA.Length; i++)  
           {  
               Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
               request.DATA[i].EMP_NO,  
               request.DATA[i].NAME,  
               request.DATA[i].DESIGNATION,  
               request.DATA[i].SALARY);  
           }  
           Console.WriteLine("*************************************************");  
           Console.WriteLine("\nHit <RETURN> to stop polling");  
       }  
   }  
   ```  

3. <span data-ttu-id="c2116-196">URI の一部として資格情報を渡すことを回避するために、次のクラスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2116-196">You must implement the following class to avoid passing credentials as part of the URI.</span></span> <span data-ttu-id="c2116-197">アプリケーションの後半部分の資格情報を渡すには、このクラスをインスタンス化されます。</span><span class="sxs-lookup"><span data-stu-id="c2116-197">In the latter part of the application, you will instantiate this class to pass on the credentials.</span></span>  

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

4. <span data-ttu-id="c2116-198">作成、 **OracleEBSBinding**とバインドのプロパティを指定することで、ポーリング操作を構成します。</span><span class="sxs-lookup"><span data-stu-id="c2116-198">Create an **OracleEBSBinding** and configure the polling operation by specifying the binding properties.</span></span> <span data-ttu-id="c2116-199">コードで明示的に、または構成で宣言的に、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c2116-199">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="c2116-200">指定する必要がありますには、少なくとも、 **InboundOperationType**、 **PolledDataAvailableStatement**、 **PollingInput**、および**PollingAction**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="c2116-200">At a minimum, you must specify the **InboundOperationType**, **PolledDataAvailableStatement**, **PollingInput**, and **PollingAction** binding properties.</span></span>  

   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   binding.InboundOperationType = InboundOperation.Polling;  
   binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
   binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
   binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
   binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
   ```  

5. <span data-ttu-id="c2116-201">インターフェイス テーブルをポーリングするため、アプリケーションのコンテキストを設定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="c2116-201">Because you are polling an interface table, you must also set the applications context.</span></span> <span data-ttu-id="c2116-202">アプリケーションのコンテキストとアプリケーション コンテキストの設定に必要なバインドのプロパティの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。</span><span class="sxs-lookup"><span data-stu-id="c2116-202">For more information about application context and the binding properties required for setting application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  

   ```  
   binding.OracleUserName = "myOracleEBSUserName";  
   binding.OraclePassword = "myOracleEBSPassword";  
   binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
   ```  

6. <span data-ttu-id="c2116-203">Oracle E-business Suite の資格情報を指定するには、インスタンス化する、 **PollingCredentials**手順 3 で作成したクラス。</span><span class="sxs-lookup"><span data-stu-id="c2116-203">Specify Oracle E-Business Suite credentials by instantiating the **PollingCredentials** class you created in Step 3.</span></span>  

   ```  
   PollingCredentials credentials = new PollingCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  
   ```  

7. <span data-ttu-id="c2116-204">手順 2 で作成した WCF サービスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2116-204">Create an instance of the WCF service created in step 2.</span></span>  

   ```  
   // create service instance  
   PollingService service = new PollingService();  
   ```  

8. <span data-ttu-id="c2116-205">インスタンスを作成**System.ServiceModel.ServiceHost** WCF サービスと基本の接続 URI を使用しています。</span><span class="sxs-lookup"><span data-stu-id="c2116-205">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="c2116-206">基本の接続 URI は、指定されている場合、受信の ID を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="c2116-206">The base connection URI cannot contain the inbound ID, if specified.</span></span> <span data-ttu-id="c2116-207">また、資格情報をここで渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2116-207">You must also pass the credentials here.</span></span>  

   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
   ServiceHost serviceHost = new ServiceHost(service, baseUri);  
   serviceHost.Description.Behaviors.Add(credentials);  

   ```  

9. <span data-ttu-id="c2116-208">サービス ホストにサービス エンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="c2116-208">Add a service endpoint to the service host.</span></span> <span data-ttu-id="c2116-209">これを行うには :</span><span class="sxs-lookup"><span data-stu-id="c2116-209">To do this:</span></span>  

   - <span data-ttu-id="c2116-210">手順 4. で作成したバインドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c2116-210">Use the binding created in step 4.</span></span>  

   - <span data-ttu-id="c2116-211">接続の資格情報を含む URI を指定し、必要に応じて、受信の id。</span><span class="sxs-lookup"><span data-stu-id="c2116-211">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  

   - <span data-ttu-id="c2116-212">MS_SAMPLE_EMPLOYEE インターフェイス テーブルをポーリングするには、"InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE"としてコントラクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c2116-212">Specify the contract as "InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE" to poll the MS_SAMPLE_EMPLOYEE interface table.</span></span>  

     ```  
     // Add service endpoint: be sure to specify InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE as the contract  
     Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
     serviceHost.AddServiceEndpoint("InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE", binding, ConnectionUri);  
     ```  

10. <span data-ttu-id="c2116-213">ポーリングのデータを受信するには、サービス ホストを開きます。</span><span class="sxs-lookup"><span data-stu-id="c2116-213">To receive polling data, open the service host.</span></span> <span data-ttu-id="c2116-214">アダプターは、クエリが結果セットを返すたびにデータを返します。</span><span class="sxs-lookup"><span data-stu-id="c2116-214">The adapter will return data whenever the query returns a result set.</span></span>  

    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  

11. <span data-ttu-id="c2116-215">ポーリングを終了するには、サービス ホストを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c2116-215">To terminate polling, close the service host.</span></span>  

    > [!IMPORTANT]
    >  <span data-ttu-id="c2116-216">アダプターは、サービス ホストが閉じられるまでポーリングを続行します。</span><span class="sxs-lookup"><span data-stu-id="c2116-216">The adapter will continue to poll until the service host is closed.</span></span>  

    ```  
    serviceHost.Close();  
    ```  

### <a name="example"></a><span data-ttu-id="c2116-217">例</span><span class="sxs-lookup"><span data-stu-id="c2116-217">Example</span></span>  
 <span data-ttu-id="c2116-218">次の例では、MS_SAMPLE_EMPLOYEE インターフェイス テーブルをポーリングするポーリング アプリケーションを示します。</span><span class="sxs-lookup"><span data-stu-id="c2116-218">The following example shows a polling application that polls the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="c2116-219">**PollingInput**プロパティには、MS_SAMPLE_EMPLOYEE テーブルからすべてのデータを読み取る select ステートメントが含まれているし、ポーリング後ステートメントは、同じテーブルからすべてのデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="c2116-219">The **PollingInput** property contains the select statement that reads all the data from the MS_SAMPLE_EMPLOYEE table and the post poll statement deletes all the data from the same table.</span></span> <span data-ttu-id="c2116-220">最初のポーリング メッセージは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルからすべてのレコードを提供します。</span><span class="sxs-lookup"><span data-stu-id="c2116-220">The first polling message gives all the records from the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="c2116-221">ポーリング後ステートメント、レコードが削除されるため、後続のポーリング メッセージはレコードがありません。</span><span class="sxs-lookup"><span data-stu-id="c2116-221">Subsequent polling messages will not contain any records because the post poll statement deletes the records.</span></span> <span data-ttu-id="c2116-222">多くのデータは MS_SAMPLE_EMPLOYEE インターフェイス テーブルに追加されるまで、すべてのメッセージのポーリングは利用できません。</span><span class="sxs-lookup"><span data-stu-id="c2116-222">Until more data is added to the MS_SAMPLE_EMPLOYEE interface table, you will not get any polling messages.</span></span> <span data-ttu-id="c2116-223">そのため、新しいレコードを含む MS_SAMPLE_EMPLOYEE インターフェイス テーブルを再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2116-223">So, you must repopulate the MS_SAMPLE_EMPLOYEE interface table with new records.</span></span> <span data-ttu-id="c2116-224">サンプルで提供される insert_apps_data.sql スクリプトを実行して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c2116-224">You can do so by running the insert_apps_data.sql script provided with the samples.</span></span> <span data-ttu-id="c2116-225">このスクリプトを実行した後、次のポーリング操作によって新しいレコードをテーブルに挿入がフェッチされます。</span><span class="sxs-lookup"><span data-stu-id="c2116-225">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span> <span data-ttu-id="c2116-226">アダプターのポーリングを押して、サービス ホストを終了するまでは引き続き`<RETURN>`します。</span><span class="sxs-lookup"><span data-stu-id="c2116-226">The adapter will continue to poll until you close the service host by pressing `<RETURN>`.</span></span>  

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

namespace SelectPolling_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  

    public class PollingService : OracleEBSBindingNamespace.OracleEBSBindingService  
    {  
        public override void Poll(Poll request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Emp No\tName\tDesignation\tSalary");  
            for (int i = 0; i < request.DATA.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.DATA[i].EMP_NO,  
                request.DATA[i].NAME,  
                request.DATA[i].DESIGNATION,  
                request.DATA[i].SALARY);  
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
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
                binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
                binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
                binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
                binding.OracleUserName = "myOracleEBSUserName";  
                binding.OraclePassword = "myOracleEBSPassword";  
                binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  

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
                serviceHost.AddServiceEndpoint("InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE", binding, ConnectionUri);  
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

## <a name="see-also"></a><span data-ttu-id="c2116-227">参照</span><span class="sxs-lookup"><span data-stu-id="c2116-227">See Also</span></span>  
 [<span data-ttu-id="c2116-228">WCF サービス モデルを使用してポーリング Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="c2116-228">Poll Oracle E-Business Suite using the WCF service model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-the-wcf-service-model.md)