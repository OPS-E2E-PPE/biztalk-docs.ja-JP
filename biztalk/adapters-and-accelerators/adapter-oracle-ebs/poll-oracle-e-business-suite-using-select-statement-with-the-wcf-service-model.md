---
title: "WCF サービス モデルで SELECT ステートメントを使用してポーリング Oracle E-business Suite |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 521d58e4-73b1-48a8-9a0a-9e733386c1b5
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2cac950ced0fb0d7133e99bc3d12699f9379bcb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="poll-oracle-e-business-suite-using-select-statement-with-the-wcf-service-model"></a><span data-ttu-id="229a7-102">WCF サービス モデルで SELECT ステートメントを使用してポーリング Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="229a7-102">Poll Oracle E-Business Suite using SELECT statement with the WCF service model</span></span>
<span data-ttu-id="229a7-103">構成することができます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]メッセージを受信するデータの定期的な変更を継続的にインターフェイスのテーブルをポーリングする SELECT ステートメントを使用して、ビュー、テーブルおよびビュー Oracle E-business suite のインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="229a7-103">You can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive periodic data-change messages by using a SELECT statement to continuously poll the interface tables, interface views, tables and views in Oracle E-Business Suite.</span></span> <span data-ttu-id="229a7-104">Oracle E-business Suite をポーリングするアダプターが定期的に実行されるポーリング ステートメントと SELECT ステートメントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="229a7-104">You can specify a SELECT statement as a polling statement that the adapter executes periodically to poll Oracle E-Business Suite.</span></span> <span data-ttu-id="229a7-105">後の投票 PL/SQL コード ブロックを指定することも、アダプターが、ポーリング ステートメントが実行された後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="229a7-105">You can also specify a post-poll PL/SQL code block that the adapter executes after the polling statement is executed.</span></span>  
  
 <span data-ttu-id="229a7-106">ポーリングを有効にするには、このトピックの説明に従って、特定のバインディング プロパティの条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="229a7-106">To enable polling, you must specify certain binding properties as described in this topic.</span></span>  <span data-ttu-id="229a7-107">アダプターがポーリングをサポートする方法の詳細については、次を参照してください。[呼び出しをポーリングを使用して受信するためのサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)です。</span><span class="sxs-lookup"><span data-stu-id="229a7-107">For more information about how the adapter supports polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  
  
## <a name="configuring-a-polling-operation-with-oracle-e-business-suite-adapter-binding-properties"></a><span data-ttu-id="229a7-108">Oracle E-business Suite アダプターのバインドのプロパティとポーリング操作を構成します。</span><span class="sxs-lookup"><span data-stu-id="229a7-108">Configuring a Polling Operation with Oracle E-Business Suite Adapter Binding Properties</span></span>  
 <span data-ttu-id="229a7-109">次の表、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]データを受信するアダプターの構成に使用するバインドのプロパティがメッセージを変更します。</span><span class="sxs-lookup"><span data-stu-id="229a7-109">The following table summarizes the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding properties that you use to configure the adapter to receive data change messages.</span></span> <span data-ttu-id="229a7-110">これらのバインディング プロパティを指定すると、ポーリング アプリケーションの実行中にあります。</span><span class="sxs-lookup"><span data-stu-id="229a7-110">You must specify these binding properties while running the polling application.</span></span>  
  
|<span data-ttu-id="229a7-111">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="229a7-111">Binding Property</span></span>|<span data-ttu-id="229a7-112">Description</span><span class="sxs-lookup"><span data-stu-id="229a7-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="229a7-113">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="229a7-113">**InboundOperationType**</span></span>|<span data-ttu-id="229a7-114">実行するかどうかを示す**ポーリング**または**通知**操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="229a7-114">Specifies whether you want to perform **Polling** or **Notification** inbound operation.</span></span> <span data-ttu-id="229a7-115">既定値は**ポーリング**です。</span><span class="sxs-lookup"><span data-stu-id="229a7-115">Default is **Polling**.</span></span>|  
|<span data-ttu-id="229a7-116">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="229a7-116">**PolledDataAvailableStatement**</span></span>|<span data-ttu-id="229a7-117">すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="229a7-117">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="229a7-118">レコードがある場合にのみ、SELECT ステートメントを指定するため、 **PollingInput**プロパティのバインドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="229a7-118">Only if a record is available, the SELECT statement you specify for the **PollingInput** binding property will be executed.</span></span>|  
|<span data-ttu-id="229a7-119">**PollingInterval**</span><span class="sxs-lookup"><span data-stu-id="229a7-119">**PollingInterval**</span></span>|<span data-ttu-id="229a7-120">秒単位で間隔を指定、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]の指定されたステートメントの実行、 **PolledDataAvailableStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="229a7-120">Specifies the interval, in seconds, at which the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="229a7-121">既定値は 30 秒です。</span><span class="sxs-lookup"><span data-stu-id="229a7-121">The default is 30 seconds.</span></span> <span data-ttu-id="229a7-122">ポーリング間隔では、連続するポーリングの間隔を決定します。</span><span class="sxs-lookup"><span data-stu-id="229a7-122">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="229a7-123">ステートメントは、指定した期間内で実行される、アダプター休止状態に入ります残り時間の間隔。</span><span class="sxs-lookup"><span data-stu-id="229a7-123">If the statement is executed within the specified interval, the adapter sleeps for the remaining time in the interval.</span></span>|  
|<span data-ttu-id="229a7-124">**PollingInput**</span><span class="sxs-lookup"><span data-stu-id="229a7-124">**PollingInput**</span></span>|<span data-ttu-id="229a7-125">ポーリング ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="229a7-125">Specifies the polling statement.</span></span> <span data-ttu-id="229a7-126">SELECT ステートメントを使用してポーリングを行うには、このバインディングのプロパティの SELECT ステートメントを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="229a7-126">To poll using a SELECT statement, you must specify a SELECT statement for this binding property.</span></span> <span data-ttu-id="229a7-127">既定値は null です。</span><span class="sxs-lookup"><span data-stu-id="229a7-127">The default is null.</span></span><br /><br /> <span data-ttu-id="229a7-128">値を指定する必要があります**PollingInput**ポーリングを有効にするプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="229a7-128">You must specify a value for **PollingInput** binding property to enable polling.</span></span> <span data-ttu-id="229a7-129">ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="229a7-129">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span>|  
|<span data-ttu-id="229a7-130">**PollingAction**</span><span class="sxs-lookup"><span data-stu-id="229a7-130">**PollingAction**</span></span>|<span data-ttu-id="229a7-131">ポーリング操作のアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="229a7-131">Specifies the action for the polling operation.</span></span> <span data-ttu-id="229a7-132">使用して、操作の生成、サービス インターフェイスからのポーリング動作を指定できます、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="229a7-132">You can determine the polling action from the service interface generated for the operation using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span>|  
|<span data-ttu-id="229a7-133">**PostPollStatement**</span><span class="sxs-lookup"><span data-stu-id="229a7-133">**PostPollStatement**</span></span>|<span data-ttu-id="229a7-134">指定されたステートメントの後に実行されるステートメント ブロックを指定します、 **PollingInput**プロパティのバインドを実行します。</span><span class="sxs-lookup"><span data-stu-id="229a7-134">Specifies a statement block that is executed after the statement specified by the **PollingInput** binding property is executed.</span></span>|  
|<span data-ttu-id="229a7-135">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="229a7-135">**PollWhileDataFound**</span></span>|<span data-ttu-id="229a7-136">指定するかどうか、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ポーリング間隔を無視し、継続的にデータで使用できる場合、テーブルをポーリングするポーリング ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="229a7-136">Specifies whether the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ignores the polling interval and continuously executes the polling statement, if data is available in the table being polled.</span></span> <span data-ttu-id="229a7-137">テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔でポーリング ステートメントを実行する元に戻します。</span><span class="sxs-lookup"><span data-stu-id="229a7-137">If no data is available in the table, the adapter reverts to execute the polling statement at the specified polling interval.</span></span> <span data-ttu-id="229a7-138">既定値は false です。</span><span class="sxs-lookup"><span data-stu-id="229a7-138">Default is false.</span></span>|  
  
 <span data-ttu-id="229a7-139">これらのプロパティの詳細については、次を参照してください。 [Oracle E-business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="229a7-139">For a more complete description of these properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="229a7-140">使用する方法の詳細については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]さらに、Oracle データベースをポーリングするには、読み取る。</span><span class="sxs-lookup"><span data-stu-id="229a7-140">For a complete description of how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll the Oracle database, read further.</span></span>  
  
## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="229a7-141">このトピックの内容がポーリングを示しています</span><span class="sxs-lookup"><span data-stu-id="229a7-141">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="229a7-142">このトピックの内容を示すために方法、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] SELECT ステートメントを使用してメッセージを変更するデータの受信をサポート、ポーリングを続けた、 **MS_SAMPLE_EMPLOYEE**インターフェイス テーブルに、**アプリケーション オブジェクト ライブラリ**アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="229a7-142">In this topic, to demonstrate how the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports receiving data change messages using SELECT statements, you poll the **MS_SAMPLE_EMPLOYEE** interface table in the **Application Object Library** application.</span></span> <span data-ttu-id="229a7-143">次の表は、Oracle E-business Suite でこれらのオブジェクトを作成するサンプルに用意されている create_apps_artifacts.sql スクリプトを実行するときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="229a7-143">This table is created when you run the create_apps_artifacts.sql script provided with the samples to create these objects in Oracle E-Business Suite.</span></span>  
  
 <span data-ttu-id="229a7-144">ポーリング操作を示すためは、次を操作します。</span><span class="sxs-lookup"><span data-stu-id="229a7-144">To demonstrate a polling operation, we do the following:</span></span>  
  
-   <span data-ttu-id="229a7-145">SELECT ステートメントを指定、 **PolledDataAvailableStatement**データがある場所のインターフェイス テーブルでポーリング (MS_SAMPLE_EMPLOYEE) を決定するプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="229a7-145">Specify a SELECT statement for the **PolledDataAvailableStatement** binding property to determine where the interface table being polled (MS_SAMPLE_EMPLOYEE) has any data.</span></span> <span data-ttu-id="229a7-146">この例では、このバインディングのプロパティとしてを設定できます。</span><span class="sxs-lookup"><span data-stu-id="229a7-146">In this example, you can set this binding property as:</span></span>  
  
    ```  
    SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE  
    ```  
  
     <span data-ttu-id="229a7-147">これにより、MS_SAMPLE_EMPLOYEE インターフェイス テーブルにレコードの一部がある場合にのみ、アダプターが、ポーリング ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="229a7-147">This ensures that the adapter executes the polling statement only when the MS_SAMPLE_EMPLOYEE interface table has some records.</span></span>  
  
-   <span data-ttu-id="229a7-148">SELECT ステートメントを指定、 **PollingInput**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="229a7-148">Specify a SELECT statement for the **PollingInput** binding property.</span></span> <span data-ttu-id="229a7-149">このステートメントは、MS_SAMPLE_EMPLOYEE インターフェイス テーブル内のすべての行を取得します。</span><span class="sxs-lookup"><span data-stu-id="229a7-149">This statement retrieves all the rows in the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="229a7-150">この例では、このバインディングのプロパティとしてを設定できます。</span><span class="sxs-lookup"><span data-stu-id="229a7-150">In this example, you can set this binding property as:</span></span>  
  
    ```  
    SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="229a7-151">SELECT ステートメントで使用される FOR UPDATE 句の詳細については、次を参照してください。 [Oracle E-business Suite からデータ変更のポーリングに基づいたメッセージを受信](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md)です。</span><span class="sxs-lookup"><span data-stu-id="229a7-151">For information about the FOR UPDATE clause used in the SELECT statement, see [Receive polling-based data-changed messages from Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md).</span></span>  
  
-   <span data-ttu-id="229a7-152">一部として、DELETE ステートメントを指定、 **PostPollStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="229a7-152">Specify a DELETE statement as part of the **PostPollStatement** binding property.</span></span> <span data-ttu-id="229a7-153">このステートメントは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルからすべてのデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="229a7-153">This statement will delete all data from MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="229a7-154">この例では、このバインディングのプロパティとしてを設定できます。</span><span class="sxs-lookup"><span data-stu-id="229a7-154">In this example, you can set this binding property as:</span></span>  
  
    ```  
    DELETE FROM MS_SAMPLE_EMPLOYEE  
    ```  
  
     <span data-ttu-id="229a7-155">これが発生した後、次回の指定されたステートメント**PollingInput**は実行すると、それはフェッチできませんすべてのデータ。</span><span class="sxs-lookup"><span data-stu-id="229a7-155">After this happens, the next time the statement specified for **PollingInput** will be executed, it will not fetch any data.</span></span>  
  
-   <span data-ttu-id="229a7-156">多くのデータは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルに追加される、まで、新しいレコードを含む MS_SAMPLE_EMPLOYEE インターフェイス テーブルを再作成する必要がありますのでにポーリング メッセージを取得できません。</span><span class="sxs-lookup"><span data-stu-id="229a7-156">Until more data is added to the MS_SAMPLE_EMPLOYEE interface table, you will not get any polling messages so you must repopulate the MS_SAMPLE_EMPLOYEE interface table with new records.</span></span> <span data-ttu-id="229a7-157">サンプルに用意されている insert_apps_data.sql スクリプトを実行して、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="229a7-157">You can do so by running the insert_apps_data.sql script provided with the samples.</span></span> <span data-ttu-id="229a7-158">このスクリプトを実行した後、次のポーリング操作によって新しいレコードをテーブルに挿入がフェッチされます。</span><span class="sxs-lookup"><span data-stu-id="229a7-158">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span>  
  
## <a name="configuring-polling-in-the-wcf-service-model"></a><span data-ttu-id="229a7-159">WCF サービス モデルでのポーリングを構成します。</span><span class="sxs-lookup"><span data-stu-id="229a7-159">Configuring Polling in the WCF Service Model</span></span>  
 <span data-ttu-id="229a7-160">使用してインターフェイス テーブルをポーリングする、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]モデルでは、WCF サービス、行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="229a7-160">To poll an interface table using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with the WCF service model, you must:</span></span>  
  
-   <span data-ttu-id="229a7-161">WCF サービス コントラクト (インターフェイス) を生成、**ポーリング**MS_SAMPLE_EMPLOYEE インターフェイス テーブルで操作します。</span><span class="sxs-lookup"><span data-stu-id="229a7-161">Generate a WCF service contract (interface) for the **Poll** operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="229a7-162">これを行うには、使用して、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="229a7-162">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
-   <span data-ttu-id="229a7-163">このインターフェイスから WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="229a7-163">Implement a WCF service from this interface.</span></span>  
  
-   <span data-ttu-id="229a7-164">サービス ホストを使用してこの WCF サービスをホスト (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="229a7-164">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="229a7-165">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="229a7-165">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="229a7-166">このトピックの例では、MS_SAMPLE_EMPLOYEE インターフェイス テーブルをポーリングします。</span><span class="sxs-lookup"><span data-stu-id="229a7-166">The examples in this topic poll the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="229a7-167">テーブルを生成するスクリプトは、サンプルの値が提供されます。</span><span class="sxs-lookup"><span data-stu-id="229a7-167">A script to generate the table is supplied with the samples.</span></span> <span data-ttu-id="229a7-168">サンプルの詳細については、次を参照してください。 [Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="229a7-168">For more information about the samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="229a7-169">サンプルは、 **SelectPolling_ServiceModel**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプルです。</span><span class="sxs-lookup"><span data-stu-id="229a7-169">A sample, **SelectPolling_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="229a7-170">WCF サービス コントラクトとクラス</span><span class="sxs-lookup"><span data-stu-id="229a7-170">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="229a7-171">使用することができます、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) およびサポートするためのクラスを作成する、**ポーリング**操作します。</span><span class="sxs-lookup"><span data-stu-id="229a7-171">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **Polling** operation.</span></span> <span data-ttu-id="229a7-172">詳細については、WCF サービス コントラクトを生成する、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="229a7-172">For more information about generating a WCF service contract, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="229a7-173">WCF サービス コントラクト (インターフェイス)</span><span class="sxs-lookup"><span data-stu-id="229a7-173">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="229a7-174">次のコードに対して生成される WCF サービス コントラクト (インターフェイス) を示しています、**ポーリング**MS_SAMPLE_EMPLOYEE インターフェイス テーブルで操作します。</span><span class="sxs-lookup"><span data-stu-id="229a7-174">The following code shows the WCF service contract (interface) generated for the **Poll** operation on MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
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
  
### <a name="the-message-contracts"></a><span data-ttu-id="229a7-175">メッセージ コントラクト</span><span class="sxs-lookup"><span data-stu-id="229a7-175">The Message Contracts</span></span>  
 <span data-ttu-id="229a7-176">次に、メッセージ コントラクトを**ポーリング**MS_SAMPLE_EMPLOYEE インターフェイス テーブルで操作します。</span><span class="sxs-lookup"><span data-stu-id="229a7-176">Following is the message contract for the **Poll** operation on MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
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
  
### <a name="wcf-service-class"></a><span data-ttu-id="229a7-177">WCF サービス クラス</span><span class="sxs-lookup"><span data-stu-id="229a7-177">WCF Service Class</span></span>  
 <span data-ttu-id="229a7-178">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をサービス コントラクト (インターフェイス) から実装、WCF サービス クラスのスタブを持つファイルも生成します。</span><span class="sxs-lookup"><span data-stu-id="229a7-178">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="229a7-179">ファイルの名前は、OracleEBSBindingService.cs です。</span><span class="sxs-lookup"><span data-stu-id="229a7-179">The name of the file is OracleEBSBindingService.cs.</span></span> <span data-ttu-id="229a7-180">処理するロジックを挿入することができます、**ポーリング**このクラスに直接操作します。</span><span class="sxs-lookup"><span data-stu-id="229a7-180">You can insert the logic to process the **Poll** operation directly into this class.</span></span> <span data-ttu-id="229a7-181">次のコードによって生成された WCF サービス クラスを示しています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="229a7-181">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
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
  
## <a name="receiving-inbound-messages-for-the-poll-operation-using-a-select-statement"></a><span data-ttu-id="229a7-182">SELECT ステートメントを使用してポーリング操作の着信メッセージを受信</span><span class="sxs-lookup"><span data-stu-id="229a7-182">Receiving Inbound Messages for the Poll Operation Using a SELECT Statement</span></span>  
 <span data-ttu-id="229a7-183">このセクションの内容を使用してポーリングの受信メッセージを受信する .NET アプリケーションを記述する方法の手順を説明する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="229a7-183">This section provides instructions on how to write a .NET application to receive inbound polling messages using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
#### <a name="to-receive-polling-messages-using-a-select-statement"></a><span data-ttu-id="229a7-184">SELECT ステートメントを使用してポーリング メッセージを受信するには</span><span class="sxs-lookup"><span data-stu-id="229a7-184">To receive polling messages using a SELECT statement</span></span>  
  
1.  <span data-ttu-id="229a7-185">使用して、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) およびためのヘルパー クラスを生成する、**ポーリング**MS_SAMPLE_EMPLOYEE インターフェイス テーブルで操作します。</span><span class="sxs-lookup"><span data-stu-id="229a7-185">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **Poll** operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="229a7-186">詳細については、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="229a7-186">For more information, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span> <span data-ttu-id="229a7-187">サービス コントラクトとヘルパー クラスを生成するときに、必要に応じてバインドのプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="229a7-187">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="229a7-188">これは、生成された構成ファイルで正しく設定されていることを保証します。</span><span class="sxs-lookup"><span data-stu-id="229a7-188">This guarantees that they are properly set in the generated configuration file.</span></span>  
  
2.  <span data-ttu-id="229a7-189">手順 1. で生成されたインターフェイスとヘルパー クラスからの WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="229a7-189">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="229a7-190">**ポーリング**から受信したデータの処理エラーが発生した場合、このクラスのメソッドは、ポーリング トランザクションが中止例外をスローできます、**ポーリング**操作ですそれ以外の場合メソッドではありません。何かを返します。</span><span class="sxs-lookup"><span data-stu-id="229a7-190">The **Poll** method of this class can throw an exception to abort the polling transaction, if an error is encountered processing the data received from the **Poll** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="229a7-191">次のように、WCF サービス クラスを属性する必要があります。</span><span class="sxs-lookup"><span data-stu-id="229a7-191">You must attribute the WCF service class as follows:</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
     <span data-ttu-id="229a7-192">内で、**ポーリング**メソッドを直接、アプリケーション ロジックを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="229a7-192">Within the **Poll** method, you can implement your application logic directly.</span></span> <span data-ttu-id="229a7-193">このクラスは、OracleEBSBindingService.cs で確認できます。</span><span class="sxs-lookup"><span data-stu-id="229a7-193">This class can be found in OracleEBSBindingService.cs.</span></span> <span data-ttu-id="229a7-194">この例では、このコードはサブ クラス、 **OracleEBSBindingService**クラスです。</span><span class="sxs-lookup"><span data-stu-id="229a7-194">This code in this example sub-classes the **OracleEBSBindingService** class.</span></span> <span data-ttu-id="229a7-195">このコードでポーリング メッセージを受信、コンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="229a7-195">In this code, the polling message received and is written to the console.</span></span>  
  
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
  
3.  <span data-ttu-id="229a7-196">URI の一部として資格情報を渡すを防ぐ次のクラスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="229a7-196">You must implement the following class to avoid passing credentials as part of the URI.</span></span> <span data-ttu-id="229a7-197">アプリケーションの後半では、資格情報を渡すには、このクラスがインスタンス化されします。</span><span class="sxs-lookup"><span data-stu-id="229a7-197">In the latter part of the application, you will instantiate this class to pass on the credentials.</span></span>  
  
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
  
4.  <span data-ttu-id="229a7-198">作成、 **OracleEBSBinding**とバインドのプロパティを指定することによって、ポーリング操作を構成します。</span><span class="sxs-lookup"><span data-stu-id="229a7-198">Create an **OracleEBSBinding** and configure the polling operation by specifying the binding properties.</span></span> <span data-ttu-id="229a7-199">これは、コードで明示的にまたは構成で宣言によって行うことができます。</span><span class="sxs-lookup"><span data-stu-id="229a7-199">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="229a7-200">指定する必要がありますには、少なくとも、 **InboundOperationType**、 **PolledDataAvailableStatement**、 **PollingInput**、および**PollingAction**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="229a7-200">At a minimum, you must specify the **InboundOperationType**, **PolledDataAvailableStatement**, **PollingInput**, and **PollingAction** binding properties.</span></span>  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    binding.InboundOperationType = InboundOperation.Polling;  
    binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
    binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
    binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
    binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
    ```  
  
5.  <span data-ttu-id="229a7-201">インターフェイス テーブルをポーリングするため、アプリケーションのコンテキストも設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="229a7-201">Because you are polling an interface table, you must also set the applications context.</span></span> <span data-ttu-id="229a7-202">アプリケーション コンテキストおよびアプリケーションのコンテキストの設定に必要なバインドのプロパティの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。</span><span class="sxs-lookup"><span data-stu-id="229a7-202">For more information about application context and the binding properties required for setting application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
6.  <span data-ttu-id="229a7-203">Oracle E-business Suite の資格情報を指定するには、インスタンス化する、 **PollingCredentials**手順 3. で作成したクラスです。</span><span class="sxs-lookup"><span data-stu-id="229a7-203">Specify Oracle E-Business Suite credentials by instantiating the **PollingCredentials** class you created in Step 3.</span></span>  
  
    ```  
    PollingCredentials credentials = new PollingCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
    ```  
  
7.  <span data-ttu-id="229a7-204">手順 2 で作成した WCF サービスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="229a7-204">Create an instance of the WCF service created in step 2.</span></span>  
  
    ```  
    // create service instance  
    PollingService service = new PollingService();  
    ```  
  
8.  <span data-ttu-id="229a7-205">インスタンスを作成する**System.ServiceModel.ServiceHost** WCF サービスと基本接続 URI を使用しています。</span><span class="sxs-lookup"><span data-stu-id="229a7-205">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="229a7-206">基本の接続 URI は、指定されている場合、受信の ID を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="229a7-206">The base connection URI cannot contain the inbound ID, if specified.</span></span> <span data-ttu-id="229a7-207">資格情報を次に渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="229a7-207">You must also pass the credentials here.</span></span>  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
    ServiceHost serviceHost = new ServiceHost(service, baseUri);  
    serviceHost.Description.Behaviors.Add(credentials);  
  
    ```  
  
9. <span data-ttu-id="229a7-208">サービス ホストにサービス エンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="229a7-208">Add a service endpoint to the service host.</span></span> <span data-ttu-id="229a7-209">これを行うには :</span><span class="sxs-lookup"><span data-stu-id="229a7-209">To do this:</span></span>  
  
    -   <span data-ttu-id="229a7-210">手順 4. で作成したバインディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="229a7-210">Use the binding created in step 4.</span></span>  
  
    -   <span data-ttu-id="229a7-211">接続の資格情報を含む URI を指定し、必要に応じて、入力方向の id。</span><span class="sxs-lookup"><span data-stu-id="229a7-211">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  
  
    -   <span data-ttu-id="229a7-212">MS_SAMPLE_EMPLOYEE インターフェイス テーブルをポーリングするには、"InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE"としてコントラクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="229a7-212">Specify the contract as "InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE" to poll the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
    ```  
    // Add service endpoint: be sure to specify InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE as the contract  
    Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
    serviceHost.AddServiceEndpoint("InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE", binding, ConnectionUri);  
    ```  
  
10. <span data-ttu-id="229a7-213">ポーリングのデータを受信するには、サービス ホストを開きます。</span><span class="sxs-lookup"><span data-stu-id="229a7-213">To receive polling data, open the service host.</span></span> <span data-ttu-id="229a7-214">アダプターは、クエリが結果セットを返すときにデータを返します。</span><span class="sxs-lookup"><span data-stu-id="229a7-214">The adapter will return data whenever the query returns a result set.</span></span>  
  
    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  
  
11. <span data-ttu-id="229a7-215">ポーリングを終了するには、サービス ホストを閉じます。</span><span class="sxs-lookup"><span data-stu-id="229a7-215">To terminate polling, close the service host.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="229a7-216">アダプターは、サービス ホストが閉じられるまでポーリングを続行します。</span><span class="sxs-lookup"><span data-stu-id="229a7-216">The adapter will continue to poll until the service host is closed.</span></span>  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a><span data-ttu-id="229a7-217">例</span><span class="sxs-lookup"><span data-stu-id="229a7-217">Example</span></span>  
 <span data-ttu-id="229a7-218">次の例では、MS_SAMPLE_EMPLOYEE インターフェイス テーブルをポーリングするポーリング アプリケーションを示します。</span><span class="sxs-lookup"><span data-stu-id="229a7-218">The following example shows a polling application that polls the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="229a7-219">**PollingInput**プロパティには、MS_SAMPLE_EMPLOYEE テーブルからすべてのデータを読み取る select ステートメントが含まれているし、ポーリング後ステートメントは、同じテーブルからすべてのデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="229a7-219">The **PollingInput** property contains the select statement that reads all the data from the MS_SAMPLE_EMPLOYEE table and the post poll statement deletes all the data from the same table.</span></span> <span data-ttu-id="229a7-220">ポーリングの最初のメッセージは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルからすべてのレコードを示します。</span><span class="sxs-lookup"><span data-stu-id="229a7-220">The first polling message gives all the records from the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="229a7-221">ポーリング後ステートメントは、レコードを削除するため、後続のポーリング メッセージはレコードがありません。</span><span class="sxs-lookup"><span data-stu-id="229a7-221">Subsequent polling messages will not contain any records because the post poll statement deletes the records.</span></span> <span data-ttu-id="229a7-222">多くのデータは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルに追加される、まで、ポーリングのすべてのメッセージは取得しません。</span><span class="sxs-lookup"><span data-stu-id="229a7-222">Until more data is added to the MS_SAMPLE_EMPLOYEE interface table, you will not get any polling messages.</span></span> <span data-ttu-id="229a7-223">そのため、新しいレコードを含む MS_SAMPLE_EMPLOYEE インターフェイス テーブルを再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="229a7-223">So, you must repopulate the MS_SAMPLE_EMPLOYEE interface table with new records.</span></span> <span data-ttu-id="229a7-224">サンプルに用意されている insert_apps_data.sql スクリプトを実行して、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="229a7-224">You can do so by running the insert_apps_data.sql script provided with the samples.</span></span> <span data-ttu-id="229a7-225">このスクリプトを実行した後、次のポーリング操作によって新しいレコードをテーブルに挿入がフェッチされます。</span><span class="sxs-lookup"><span data-stu-id="229a7-225">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span> <span data-ttu-id="229a7-226">アダプターはポーリングを押して、サービス ホストを終了するまで引き続き`<RETURN>`します。</span><span class="sxs-lookup"><span data-stu-id="229a7-226">The adapter will continue to poll until you close the service host by pressing `<RETURN>`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="229a7-227">参照</span><span class="sxs-lookup"><span data-stu-id="229a7-227">See Also</span></span>  
 [<span data-ttu-id="229a7-228">WCF サービス モデルを使用してポーリング Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="229a7-228">Poll Oracle E-Business Suite using the WCF service model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-the-wcf-service-model.md)