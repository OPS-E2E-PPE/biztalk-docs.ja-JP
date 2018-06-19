---
title: WCF サービス モデルでストアド プロシージャを使用してポーリング Oracle E-business Suite |Microsoft ドキュメント
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
ms.openlocfilehash: e3fb7ebcbccb1f0edb3370176192f55f0db4985a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967720"
---
# <a name="poll-oracle-e-business-suite-using-stored-procedures-with-the-wcf-service-model"></a><span data-ttu-id="07004-102">WCF サービス モデルでストアド プロシージャを使用してポーリング Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="07004-102">Poll Oracle E-Business Suite using stored procedures with the WCF service model</span></span>
<span data-ttu-id="07004-103">構成することができます、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースを定期的にポーリングするストアド プロシージャを使用して、定期的なデータの変更メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="07004-103">You can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive periodic data-change messages by using stored procedures to periodically poll the Oracle database.</span></span> <span data-ttu-id="07004-104">ストアド プロシージャは、アダプターが Oracle データベースをポーリングする定期的に実行されるポーリング ステートメントとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="07004-104">You can specify a stored procedure as a polling statement that the adapter executes periodically to poll the Oracle database.</span></span>  
  
 <span data-ttu-id="07004-105">ポーリングを有効にするには、このトピックの説明に従って、特定のバインディング プロパティの条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07004-105">To enable polling, you must specify certain binding properties as described in this topic.</span></span>  <span data-ttu-id="07004-106">アダプターがポーリングをサポートする方法の詳細については、次を参照してください。[呼び出しをポーリングを使用して受信するためのサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)です。</span><span class="sxs-lookup"><span data-stu-id="07004-106">For more information about how the adapter supports polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  
  
## <a name="configuring-a-polling-operation-with-oracle-e-business-adapter-binding-properties"></a><span data-ttu-id="07004-107">Oracle E-business アダプターのバインドのプロパティをポーリング操作を構成します。</span><span class="sxs-lookup"><span data-stu-id="07004-107">Configuring a Polling Operation with Oracle E-Business Adapter Binding Properties</span></span>  
 <span data-ttu-id="07004-108">次の表、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインドのプロパティ データの変更メッセージを受信するアダプターを構成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="07004-108">The following table summarizes the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding properties that you use to configure the adapter to receive data-change messages.</span></span> <span data-ttu-id="07004-109">これらのバインディング プロパティを指定すると、ポーリング アプリケーションの実行中にあります。</span><span class="sxs-lookup"><span data-stu-id="07004-109">You must specify these binding properties while running the polling application.</span></span>  
  
|<span data-ttu-id="07004-110">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="07004-110">Binding Property</span></span>|<span data-ttu-id="07004-111">Description</span><span class="sxs-lookup"><span data-stu-id="07004-111">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="07004-112">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="07004-112">**InboundOperationType**</span></span>|<span data-ttu-id="07004-113">実行するかどうかを指定します、**ポーリング**または**通知**操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="07004-113">Specifies whether you want to perform a **Polling** or **Notification** inbound operation.</span></span> <span data-ttu-id="07004-114">既定値は**ポーリング**です。</span><span class="sxs-lookup"><span data-stu-id="07004-114">Default is **Polling**.</span></span>|  
|<span data-ttu-id="07004-115">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="07004-115">**PolledDataAvailableStatement**</span></span>|<span data-ttu-id="07004-116">すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="07004-116">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="07004-117">レコードがある場合にのみ、ストアド プロシージャに指定した、 **PollingInput**プロパティのバインドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="07004-117">Only if a record is available, the stored procedure you specified for the **PollingInput** binding property will be executed.</span></span>|  
|<span data-ttu-id="07004-118">**PollingInterval**</span><span class="sxs-lookup"><span data-stu-id="07004-118">**PollingInterval**</span></span>|<span data-ttu-id="07004-119">秒単位で間隔を指定、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]の指定されたステートメントの実行、 **PolledDataAvailableStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="07004-119">Specifies the interval, in seconds, at which the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="07004-120">既定値は 30 秒です。</span><span class="sxs-lookup"><span data-stu-id="07004-120">The default is 30 seconds.</span></span> <span data-ttu-id="07004-121">ポーリング間隔では、連続するポーリングの間隔を決定します。</span><span class="sxs-lookup"><span data-stu-id="07004-121">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="07004-122">ステートメントは、指定した期間内で実行される、アダプター休止状態に入ります残り時間の間隔。</span><span class="sxs-lookup"><span data-stu-id="07004-122">If the statement is executed within the specified interval, the adapter sleeps for the remaining time in the interval.</span></span>|  
|<span data-ttu-id="07004-123">**PollingInput**</span><span class="sxs-lookup"><span data-stu-id="07004-123">**PollingInput**</span></span>|<span data-ttu-id="07004-124">ポーリング ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="07004-124">Specifies the polling statement.</span></span> <span data-ttu-id="07004-125">ポーリングのストアド プロシージャを使用するには、要求メッセージ全体をこのバインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07004-125">To poll using a stored procedure, you must specify the entire request message for this binding property.</span></span> <span data-ttu-id="07004-126">要求メッセージは、送信操作として、ストアド プロシージャを呼び出すため、アダプターに送信すると、同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="07004-126">The request message must be the same that you send to the adapter for invoking the stored procedure as an outbound operation.</span></span> <span data-ttu-id="07004-127">既定値は null です。</span><span class="sxs-lookup"><span data-stu-id="07004-127">The default is null.</span></span><br /><br /> <span data-ttu-id="07004-128">値を指定する必要があります**PollingInput**ポーリングを有効にするプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="07004-128">You must specify a value for **PollingInput** binding property to enable polling.</span></span> <span data-ttu-id="07004-129">ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="07004-129">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span>|  
|<span data-ttu-id="07004-130">**PollingAction**</span><span class="sxs-lookup"><span data-stu-id="07004-130">**PollingAction**</span></span>|<span data-ttu-id="07004-131">ポーリング操作のアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="07004-131">Specifies the action for the polling operation.</span></span> <span data-ttu-id="07004-132">使用して、操作の生成、サービス インターフェイスからのポーリング動作を指定できます、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="07004-132">You can determine the polling action from the service interface generated for the operation using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span>|  
|<span data-ttu-id="07004-133">**PostPollStatement**</span><span class="sxs-lookup"><span data-stu-id="07004-133">**PostPollStatement**</span></span>|<span data-ttu-id="07004-134">指定されたステートメントの後に実行されるステートメント ブロックを指定します、 **PollingInput**プロパティのバインドを実行します。</span><span class="sxs-lookup"><span data-stu-id="07004-134">Specifies a statement block that is executed after the statement specified by the **PollingInput** binding property is executed.</span></span>|  
|<span data-ttu-id="07004-135">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="07004-135">**PollWhileDataFound**</span></span>|<span data-ttu-id="07004-136">指定するかどうか、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ポーリング間隔を無視し、継続的にデータで使用できる場合、テーブルをポーリングするポーリング ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="07004-136">Specifies whether the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ignores the polling interval and continuously executes the polling statement, if data is available in the table being polled.</span></span> <span data-ttu-id="07004-137">テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔でポーリング ステートメントを実行する元に戻します。</span><span class="sxs-lookup"><span data-stu-id="07004-137">If no data is available in the table, the adapter reverts to execute the polling statement at the specified polling interval.</span></span> <span data-ttu-id="07004-138">既定値は false です。</span><span class="sxs-lookup"><span data-stu-id="07004-138">Default is false.</span></span>|  
  
 <span data-ttu-id="07004-139">これらのプロパティの詳細については、次を参照してください。 [Oracle E-business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="07004-139">For a more complete description of these properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="07004-140">使用する方法の詳細については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]をポーリングするには、次のセクションを参照します。</span><span class="sxs-lookup"><span data-stu-id="07004-140">For a complete description of how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll, read the following sections.</span></span>  
  
## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="07004-141">このトピックの内容がポーリングを示しています</span><span class="sxs-lookup"><span data-stu-id="07004-141">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="07004-142">このトピックの内容を示すため方法、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]データの変更、GET_ACTIVITYS を使用するストアド プロシージャを使用して、メッセージの受信をサポートには、Oracle データベースで ACCOUNTACTIVITY テーブルをポーリングするプロシージャが格納されています。</span><span class="sxs-lookup"><span data-stu-id="07004-142">In this topic, to demonstrate how the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports receiving data change messages using stored procedures, you use the GET_ACTIVITYS stored procedure to poll the ACCOUNTACTIVITY table in the Oracle database.</span></span> <span data-ttu-id="07004-143">このストアド プロシージャは ACCOUNT_PKG パッケージで使用できます。</span><span class="sxs-lookup"><span data-stu-id="07004-143">This stored procedure is available with the ACCOUNT_PKG package.</span></span> <span data-ttu-id="07004-144">データベースでこれらのオブジェクトを作成するサンプルに用意されている SQL スクリプトを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="07004-144">You can run the SQL scripts provided with the samples to create these objects in the database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07004-145">このトピックのポーリングで、ACCOUNTACTIVITY の表に、これはベース データベース テーブルによって作成されたサンプルに用意されているスクリプトを実行する例です。</span><span class="sxs-lookup"><span data-stu-id="07004-145">The example in this topic polls the ACCOUNTACTIVITY table, which is a base database table created by running the scripts provided with the samples.</span></span> <span data-ttu-id="07004-146">インターフェイス テーブルなど、他のテーブルをポーリングするには、このトピックの説明に従って、同様の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07004-146">You must perform similar procedures as described in this topic to poll any other table, including interface tables.</span></span>  
  
 <span data-ttu-id="07004-147">ポーリング操作を示すためは、次を操作します。</span><span class="sxs-lookup"><span data-stu-id="07004-147">To demonstrate a polling operation, we do the following:</span></span>  
  
-   <span data-ttu-id="07004-148">SELECT ステートメントを指定、 **PolledDataAvailableStatement**データがある場所のテーブルでポーリング (ACCOUNTACTIVITY) を決定するプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="07004-148">Specify a SELECT statement for the **PolledDataAvailableStatement** binding property to determine where the table being polled (ACCOUNTACTIVITY) has any data.</span></span> <span data-ttu-id="07004-149">この例では、このバインディングのプロパティとしてを設定できます。</span><span class="sxs-lookup"><span data-stu-id="07004-149">In this example, you can set this binding property as:</span></span>  
  
    ```  
    SELECT COUNT (*) FROM ACCOUNTACTIVITY  
    ```  
  
     <span data-ttu-id="07004-150">これにより、ACCOUNTACTIVITY テーブルにレコードの一部がある場合にのみ、アダプターが、ポーリング ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="07004-150">This ensures that the adapter executes the polling statement only when the ACCOUNTACTIVITY table has some records.</span></span>  
  
-   <span data-ttu-id="07004-151">一部として要求メッセージを提供することによって、GET_ACTIVITYS、ストアド プロシージャの実行、 **PollingInput**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="07004-151">Execute a stored procedure, GET_ACTIVITYS, by providing the request message as part of the **PollingInput** binding property.</span></span> <span data-ttu-id="07004-152">このストアド プロシージャは ACCOUNTACTIVITY テーブル内のすべての行を取得し、アダプターから応答メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="07004-152">This stored procedure will retrieve all the rows in the ACCOUNTACTIVITY table and you will get a response message from the adapter.</span></span>  
  
-   <span data-ttu-id="07004-153">一部としての PL/SQL ブロックの実行、 **PostPollStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="07004-153">Execute a PL/SQL block as part of the **PostPollStatement** binding property.</span></span> <span data-ttu-id="07004-154">このステートメントは、データベース内の別のテーブルに ACCOUNTACTIVITY テーブルからすべてのデータが移動されます。</span><span class="sxs-lookup"><span data-stu-id="07004-154">This statement will move all data from ACCOUNTACTIVITY table to another table in the database.</span></span> <span data-ttu-id="07004-155">これは、次回後**PollingInput**が実行すると、それはフェッチできませんすべてのデータとため GET_ACTIVITYS ストアド プロシージャは空の応答メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="07004-155">After this happens, the next time **PollingInput** is executed, it will not fetch any data and hence the GET_ACTIVITYS stored procedure will return an empty response message.</span></span>  
  
-   <span data-ttu-id="07004-156">多くのデータは ACCOUNTACTIVITY テーブルに追加するまでは引き続き新しいレコードを含む ACCOUNTACTIVITY テーブルを再作成する必要がありますので、空の応答メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="07004-156">Until more data is added to the ACCOUNTACTIVITY table, you will continue to get empty response messages so you must repopulate the ACCOUNTACTIVITY table with new records.</span></span> <span data-ttu-id="07004-157">サンプルに用意されている more_activity_data.sql スクリプトを実行して、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="07004-157">You can do so by running the more_activity_data.sql script provided with the samples.</span></span> <span data-ttu-id="07004-158">このスクリプトを実行した後、次のポーリング操作によって新しいレコードをテーブルに挿入がフェッチされます。</span><span class="sxs-lookup"><span data-stu-id="07004-158">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span>  
  
## <a name="configuring-polling-in-the-wcf-service-model"></a><span data-ttu-id="07004-159">WCF サービス モデルでのポーリングを構成します。</span><span class="sxs-lookup"><span data-stu-id="07004-159">Configuring Polling in the WCF Service Model</span></span>  
 <span data-ttu-id="07004-160">ポーリングを持つストアド プロシージャを使用して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]モデルでは、WCF サービス、行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="07004-160">To poll using stored procedures with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with the WCF service model, you must:</span></span>  
  
-   <span data-ttu-id="07004-161">ポーリングすることにこれを使用して、ストアド プロシージャの WCF サービス コントラクト (インターフェイス) を生成します。</span><span class="sxs-lookup"><span data-stu-id="07004-161">Generate a WCF service contract (interface) for the stored procedure using which you are going to poll.</span></span> <span data-ttu-id="07004-162">この例では、WCF サービス コントラクトを生成する必要があります、 **GET_ACTIVITYS**ストアド プロシージャとして、受信操作になります。</span><span class="sxs-lookup"><span data-stu-id="07004-162">For this example, you must generate the WCF service contract for the **GET_ACTIVITYS** stored procedure as an inbound operation.</span></span> <span data-ttu-id="07004-163">これを行うには、使用して、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="07004-163">To do this, you could use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
-   <span data-ttu-id="07004-164">このインターフェイスから WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="07004-164">Implement a WCF service from this interface.</span></span>  
  
-   <span data-ttu-id="07004-165">サービス ホストを使用してこの WCF サービスをホスト (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="07004-165">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="07004-166">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="07004-166">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="07004-167">このトピックのポーリング、GET_ACTIVITYS を使用した ACCOUNTACTIVITY データベース テーブルの例はストアド プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="07004-167">The examples in this topic poll the ACCOUNTACTIVITY database table using the GET_ACTIVITYS stored procedure.</span></span> <span data-ttu-id="07004-168">テーブルおよびストアド プロシージャを生成するスクリプトは、サンプルの値が提供されます。</span><span class="sxs-lookup"><span data-stu-id="07004-168">A script to generate the table and the stored procedure is supplied with the samples.</span></span> <span data-ttu-id="07004-169">サンプルの詳細については、次を参照してください。 [Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="07004-169">For more information about the samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="07004-170">サンプルは、 **StoredProcPolling_ServiceModel**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプルです。</span><span class="sxs-lookup"><span data-stu-id="07004-170">A sample, **StoredProcPolling_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="07004-171">WCF サービス コントラクトとクラス</span><span class="sxs-lookup"><span data-stu-id="07004-171">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="07004-172">使用することができます、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) およびサポートするためのクラスを作成する、 **GET_ACTIVITYS**操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="07004-172">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF service contract (interface) and supporting classes for the **GET_ACTIVITYS** inbound operation.</span></span> <span data-ttu-id="07004-173">詳細については、WCF サービス コントラクトを生成する、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="07004-173">For more information about generating a WCF service contract, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="07004-174">WCF サービス コントラクト (インターフェイス)</span><span class="sxs-lookup"><span data-stu-id="07004-174">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="07004-175">次のコードに対して生成される WCF サービス コントラクト (インターフェイス) を示しています、 **GET_ACTIVITYS**操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="07004-175">The following code shows the WCF service contract (interface) generated for the **GET_ACTIVITYS** inbound operation.</span></span>  
  
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
  
### <a name="the-message-contracts"></a><span data-ttu-id="07004-176">メッセージ コントラクト</span><span class="sxs-lookup"><span data-stu-id="07004-176">The Message Contracts</span></span>  
 <span data-ttu-id="07004-177">次に、メッセージ コントラクトを**GET_ACTIVITYS**操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="07004-177">Following is the message contract for the **GET_ACTIVITYS** inbound operation.</span></span>  
  
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
  
### <a name="wcf-service-class"></a><span data-ttu-id="07004-178">WCF サービス クラス</span><span class="sxs-lookup"><span data-stu-id="07004-178">WCF Service Class</span></span>  
 <span data-ttu-id="07004-179">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をサービス コントラクト (インターフェイス) から実装、WCF サービス クラスのスタブを持つファイルも生成します。</span><span class="sxs-lookup"><span data-stu-id="07004-179">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="07004-180">ファイルの名前は、OracleEBSBindingService.cs です。</span><span class="sxs-lookup"><span data-stu-id="07004-180">The name of the file is OracleEBSBindingService.cs.</span></span> <span data-ttu-id="07004-181">処理するロジックを挿入することができます、 **GET_ACTIVITYS**このクラスに直接操作します。</span><span class="sxs-lookup"><span data-stu-id="07004-181">You can insert the logic to process the **GET_ACTIVITYS** operation directly into this class.</span></span> <span data-ttu-id="07004-182">次のコードによって生成された WCF サービス クラスを示しています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="07004-182">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
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
  
## <a name="receiving-inbound-messages-for-polling-using-a-stored-procedure"></a><span data-ttu-id="07004-183">ストアド プロシージャを使用してポーリングの受信メッセージの受信</span><span class="sxs-lookup"><span data-stu-id="07004-183">Receiving Inbound Messages For Polling Using a Stored Procedure</span></span>  
 <span data-ttu-id="07004-184">このセクションの内容を使用してポーリングの受信メッセージを受信する .NET アプリケーションを記述する方法の手順を説明する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="07004-184">This section provides instructions on how to write a .NET application to receive inbound polling messages using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
#### <a name="to-receive-polling-messages-using-a-stored-procedure"></a><span data-ttu-id="07004-185">ストアド プロシージャを使用してポーリング メッセージを受信するには</span><span class="sxs-lookup"><span data-stu-id="07004-185">To receive polling messages using a stored procedure</span></span>  
  
1.  <span data-ttu-id="07004-186">使用して、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) およびためのヘルパー クラスを生成する、 **GET_ACTIVITYS**操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="07004-186">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF service contract (interface) and helper classes for the **GET_ACTIVITYS** inbound operation.</span></span> <span data-ttu-id="07004-187">詳細については、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="07004-187">For more information, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span> <span data-ttu-id="07004-188">サービス コントラクトとヘルパー クラスを生成するときに、必要に応じてバインドのプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="07004-188">You can optionally specify the binding properties while generating the service contract and helper classes.</span></span> <span data-ttu-id="07004-189">これは、生成された構成ファイルで正しく設定されていることを保証します。</span><span class="sxs-lookup"><span data-stu-id="07004-189">This guarantees that they are properly set in the generated configuration file.</span></span>  
  
2.  <span data-ttu-id="07004-190">手順 1. で生成されたインターフェイスとヘルパー クラスからの WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="07004-190">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="07004-191">**GET_ACTIVITYS**から受信したデータの処理エラーが発生した場合、このクラスのメソッドは、ポーリング トランザクションが中止例外をスローできます、 **GET_ACTIVITYS**操作以外の場合メソッドは何も返しません。</span><span class="sxs-lookup"><span data-stu-id="07004-191">The **GET_ACTIVITYS** method of this class can throw an exception to abort the polling transaction, if an error is encountered processing the data received from the **GET_ACTIVITYS** operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="07004-192">次のように、WCF サービス クラスを属性する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07004-192">You must attribute the WCF service class as follows:</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
     <span data-ttu-id="07004-193">内で、 **GET_ACTIVITYS**メソッドを直接、アプリケーション ロジックを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="07004-193">Within the **GET_ACTIVITYS** method, you can implement your application logic directly.</span></span> <span data-ttu-id="07004-194">このクラスは、OracleEBSBindingService.cs で確認できます。</span><span class="sxs-lookup"><span data-stu-id="07004-194">This class can be found in OracleEBSBindingService.cs.</span></span> <span data-ttu-id="07004-195">この例では、このコードはサブ クラス、 **OracleEBSBindingService**クラスです。</span><span class="sxs-lookup"><span data-stu-id="07004-195">This code in this example sub-classes the **OracleEBSBindingService** class.</span></span> <span data-ttu-id="07004-196">このコードでポーリング メッセージを受信、コンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="07004-196">In this code, the polling message received and is written to the console.</span></span>  
  
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
  
3.  <span data-ttu-id="07004-197">URI の一部として資格情報を渡すを防ぐ次のクラスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07004-197">You must implement the following class to avoid passing credentials as part of the URI.</span></span> <span data-ttu-id="07004-198">アプリケーションの後半では、資格情報を渡すには、このクラスがインスタンス化されします。</span><span class="sxs-lookup"><span data-stu-id="07004-198">In the latter part of the application, you will instantiate this class to pass on the credentials.</span></span>  
  
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
  
4.  <span data-ttu-id="07004-199">作成、 **OracleEBSBinding**とバインドのプロパティを指定することによって、ポーリング操作を構成します。</span><span class="sxs-lookup"><span data-stu-id="07004-199">Create an **OracleEBSBinding** and configure the polling operation by specifying the binding properties.</span></span> <span data-ttu-id="07004-200">これは、コードで明示的にまたは構成で宣言によって行うことができます。</span><span class="sxs-lookup"><span data-stu-id="07004-200">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="07004-201">指定する必要がありますには、少なくとも、 **InboundOperationType**、 **PolledDataAvailableStatement**、 **PollingInput**、および**PollingAction**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="07004-201">At a minimum, you must specify the **InboundOperationType**, **PolledDataAvailableStatement**, **PollingInput**, and **PollingAction** binding properties.</span></span>  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    binding.InboundOperationType = InboundOperation.Polling;  
    binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM ACCOUNTACTIVITY";  
    binding.PollingInput = "<GET_ACTIVITYS xmlns='http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/APPS/ACCOUNT_PKG'><INRECS>OPEN ? FOR SELECT * FROM ACCOUNTACTIVITY</INRECS></GET_ACTIVITYS>";  
    binding.PollingAction = "PollingPackageApis/APPS/ACCOUNT_PKG/GET_ACTIVITYS";  
    binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="07004-202">注意してくださいの値、 **PollingInput**を呼び出すための要求メッセージにはプロパティのバインドが含まれています、 **GET_ACTIVITYS**ストアド プロシージャとして送信操作です。</span><span class="sxs-lookup"><span data-stu-id="07004-202">Note that the value for the **PollingInput** binding property contains the request message for invoking the **GET_ACTIVITYS** stored procedure as an outbound operation.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="07004-203">この例では、データベース テーブルをポーリングするためする必要はありませんアプリケーション コンテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="07004-203">In this example, because you are polling a database table, you do not need to set the applications context.</span></span> <span data-ttu-id="07004-204">ただし場合は、インターフェイス テーブルがポーリングする必要がありますコンテキストを設定するアプリケーションを指定して、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="07004-204">However, if you were polling an interface table, you must set the applications context by specifying the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="07004-205">アプリケーション コンテキストの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。</span><span class="sxs-lookup"><span data-stu-id="07004-205">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
5.  <span data-ttu-id="07004-206">Oracle E-business Suite の資格情報を指定するには、インスタンス化する、 **PollingCredentials**手順 3. で作成したクラスです。</span><span class="sxs-lookup"><span data-stu-id="07004-206">Specify Oracle E-Business Suite credentials by instantiating the **PollingCredentials** class you created in Step 3.</span></span>  
  
    ```  
    PollingCredentials credentials = new PollingCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
    ```  
  
6.  <span data-ttu-id="07004-207">手順 2 で作成した WCF サービスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="07004-207">Create an instance of the WCF service created in step 2.</span></span>  
  
    ```  
    // create service instance  
    PollingService service = new PollingService();  
    ```  
  
7.  <span data-ttu-id="07004-208">インスタンスを作成する**System.ServiceModel.ServiceHost** WCF サービスと基本接続 URI を使用しています。</span><span class="sxs-lookup"><span data-stu-id="07004-208">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="07004-209">基本の接続 URI は、指定されている場合、受信の ID を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="07004-209">The base connection URI cannot contain the inbound ID, if specified.</span></span> <span data-ttu-id="07004-210">資格情報を次に渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="07004-210">You must also pass the credentials here.</span></span>  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
    ServiceHost serviceHost = new ServiceHost(service, baseUri);  
    serviceHost.Description.Behaviors.Add(credentials);  
  
    ```  
  
8.  <span data-ttu-id="07004-211">サービス ホストにサービス エンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="07004-211">Add a service endpoint to the service host.</span></span> <span data-ttu-id="07004-212">これを行うには :</span><span class="sxs-lookup"><span data-stu-id="07004-212">To do this:</span></span>  
  
    -   <span data-ttu-id="07004-213">手順 4. で作成したバインディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="07004-213">Use the binding created in step 4.</span></span>  
  
    -   <span data-ttu-id="07004-214">接続の資格情報を含む URI を指定し、必要に応じて、入力方向の id。</span><span class="sxs-lookup"><span data-stu-id="07004-214">Specify a connection URI that contains credentials and, if required, an inbound ID.</span></span>  
  
    -   <span data-ttu-id="07004-215">MS_SAMPLE_EMPLOYEE インターフェイス テーブルをポーリングするには、"PollingPackageApis_APPS_ACCOUNT_PKG"としてコントラクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="07004-215">Specify the contract as "PollingPackageApis_APPS_ACCOUNT_PKG" to poll the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
    ```  
    // Add service endpoint: be sure to specify PollingPackageApis_APPS_ACCOUNT_PKG as the contract  
    Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
    serviceHost.AddServiceEndpoint("PollingPackageApis_APPS_ACCOUNT_PKG", binding, ConnectionUri);  
    ```  
  
9. <span data-ttu-id="07004-216">ポーリングのデータを受信するには、サービス ホストを開きます。</span><span class="sxs-lookup"><span data-stu-id="07004-216">To receive polling data, open the service host.</span></span> <span data-ttu-id="07004-217">アダプターは、クエリが結果セットを返すときにデータを返します。</span><span class="sxs-lookup"><span data-stu-id="07004-217">The adapter will return data whenever the query returns a result set.</span></span>  
  
    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  
  
10. <span data-ttu-id="07004-218">ポーリングを終了するには、サービス ホストを閉じます。</span><span class="sxs-lookup"><span data-stu-id="07004-218">To terminate polling, close the service host.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="07004-219">アダプターは、サービス ホストが閉じられるまでポーリングを続行します。</span><span class="sxs-lookup"><span data-stu-id="07004-219">The adapter will continue to poll until the service host is closed.</span></span>  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a><span data-ttu-id="07004-220">例</span><span class="sxs-lookup"><span data-stu-id="07004-220">Example</span></span>  
 <span data-ttu-id="07004-221">次の例では、ストアド プロシージャを使用して、GET_ACTIVITYS ACCOUNTACTIVITY データベース テーブルをポーリングするポーリング アプリケーションを示します。</span><span class="sxs-lookup"><span data-stu-id="07004-221">The following example shows a polling application that polls the ACCOUNTACTIVITY database table using the GET_ACTIVITYS stored procedure.</span></span> <span data-ttu-id="07004-222">**PollingInput** ACCOUNTACTIVITY テーブルからすべてのデータを読み取る GET_ACTIVITYS ストアド プロシージャを呼び出す要求メッセージにはプロパティのバインドが含まれており、ポーリング後ステートメント ACCOUNTACTIVITY からすべてのデータを移動します。ACTIVITYHISTORY テーブル。</span><span class="sxs-lookup"><span data-stu-id="07004-222">The **PollingInput** binding property contains the request message to invoke the GET_ACTIVITYS stored procedure that reads all the data from the ACCOUNTACTIVITY table and the post poll statement moves all the data from ACCOUNTACTIVITY to ACTIVITYHISTORY table.</span></span>  
  
 <span data-ttu-id="07004-223">ポーリングの最初のメッセージは、ACCOUNTACTIVITY テーブルからすべてのレコードを示します。</span><span class="sxs-lookup"><span data-stu-id="07004-223">The first polling message gives all the records from the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="07004-224">ポーリング後ステートメントは、レコードを削除するため、後続のポーリング メッセージはレコードがありません。</span><span class="sxs-lookup"><span data-stu-id="07004-224">Subsequent polling messages will not contain any records because the post poll statement deletes the records.</span></span> <span data-ttu-id="07004-225">多くのデータは、ACCOUNTACTIVITY テーブルに追加される、まで、新しいレコードを含む ACCOUNTACTIVITY テーブルを再作成する必要がありますのでにポーリング メッセージを取得できません。</span><span class="sxs-lookup"><span data-stu-id="07004-225">Until more data is added to the ACCOUNTACTIVITY table, you will not get any polling messages so you must repopulate the ACCOUNTACTIVITY table with new records.</span></span> <span data-ttu-id="07004-226">サンプルに用意されている more_activity_data.sql スクリプトを実行して、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="07004-226">You can do so by running the more_activity_data.sql script provided with the samples.</span></span>  
  
 <span data-ttu-id="07004-227">このスクリプトを実行した後、次のポーリング操作によって新しいレコードをテーブルに挿入がフェッチされます。</span><span class="sxs-lookup"><span data-stu-id="07004-227">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span> <span data-ttu-id="07004-228">アダプターはポーリングを押して、サービス ホストを終了するまで引き続き`<RETURN>`します。</span><span class="sxs-lookup"><span data-stu-id="07004-228">The adapter will continue to poll until you close the service host by pressing `<RETURN>`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="07004-229">参照</span><span class="sxs-lookup"><span data-stu-id="07004-229">See Also</span></span>  
 [<span data-ttu-id="07004-230">WCF サービス モデルを使用してポーリング Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="07004-230">Poll Oracle E-Business Suite using the WCF service model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-the-wcf-service-model.md)