---
title: SELECT ステートメントを使用して、WCF チャネル モデルとポーリング Oracle E-business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 495b9010-856f-4782-bd19-1522bc3eb950
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57288b62249e7ba3de7fb9fb8e5667c3247f5829
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375007"
---
# <a name="poll-oracle-e-business-suite-using-select-statement-with-the-wcf-channel-model"></a><span data-ttu-id="96c01-102">SELECT ステートメントを使用して、WCF チャネル モデルとポーリング Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="96c01-102">Poll Oracle E-Business Suite using SELECT statement with the WCF channel model</span></span>
<span data-ttu-id="96c01-103">構成することができます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を継続的に、インターフェイス テーブルをポーリングする SELECT ステートメントを使用して、定期的なデータ変更メッセージを受信するビュー、テーブル、および Oracle E-business Suite でのビューのインターフェイスします。</span><span class="sxs-lookup"><span data-stu-id="96c01-103">You can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive periodic data-change messages by using a SELECT statement to continuously poll the interface tables, interface views, tables and views in Oracle E-Business Suite.</span></span> <span data-ttu-id="96c01-104">Oracle E-business Suite をポーリングするアダプターを定期的に実行するポーリング ステートメントと SELECT ステートメントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="96c01-104">You can specify a SELECT statement as a polling statement that the adapter executes periodically to poll Oracle E-Business Suite.</span></span> <span data-ttu-id="96c01-105">ポスト ポーリング PL/SQL コード ブロックを指定することも、アダプターがポーリング ステートメントが実行された後に実行します。</span><span class="sxs-lookup"><span data-stu-id="96c01-105">You can also specify a post-poll PL/SQL code block that the adapter executes after the polling statement is executed.</span></span>  

 <span data-ttu-id="96c01-106">ポーリングを有効にする、このトピックの説明に従って、特定のバインド プロパティの条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c01-106">To enable polling, you must specify certain binding properties as described in this topic.</span></span> <span data-ttu-id="96c01-107">アダプターがポーリングをサポートする方法の詳細については、次を参照してください。[受信呼び出しのポーリングを使用してサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)します。</span><span class="sxs-lookup"><span data-stu-id="96c01-107">For more information about how the adapter supports polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  

## <a name="configuring-a-polling-operation-with-oracle-e-business-suite-adapter-binding-properties"></a><span data-ttu-id="96c01-108">Oracle E-business Suite アダプターのバインドのプロパティをポーリング操作を構成します。</span><span class="sxs-lookup"><span data-stu-id="96c01-108">Configuring a Polling Operation with Oracle E-Business Suite Adapter Binding Properties</span></span>  
 <span data-ttu-id="96c01-109">次の表にまとめたものです、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]メッセージのバインドのプロパティを使用するデータを受信するアダプターの構成を変更します。</span><span class="sxs-lookup"><span data-stu-id="96c01-109">The following table summarizes the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding properties that you use to configure the adapter to receive data change messages.</span></span> <span data-ttu-id="96c01-110">ポーリング アプリケーションを実行中に、これらのバインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c01-110">You must specify these binding properties while running the polling application.</span></span>  


|         <span data-ttu-id="96c01-111">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="96c01-111">Binding Property</span></span>         |                                                                                                                                                                                                                            <span data-ttu-id="96c01-112">説明</span><span class="sxs-lookup"><span data-stu-id="96c01-112">Description</span></span>                                                                                                                                                                                                                             |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="96c01-113">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="96c01-113">**InboundOperationType**</span></span>     |                                                                                                                                                                          <span data-ttu-id="96c01-114">実行するかどうかを指定します**ポーリング**または**通知**操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="96c01-114">Specifies whether you want to perform **Polling** or **Notification** inbound operation.</span></span> <span data-ttu-id="96c01-115">既定値は**ポーリング**します。</span><span class="sxs-lookup"><span data-stu-id="96c01-115">Default is **Polling**.</span></span>                                                                                                                                                                          |
| <span data-ttu-id="96c01-116">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="96c01-116">**PolledDataAvailableStatement**</span></span> |                                                                                                             <span data-ttu-id="96c01-117">すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="96c01-117">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="96c01-118">指定した SELECT ステートメントのレコードを使用できる場合にのみ、 **PollingInput**プロパティのバインドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="96c01-118">Only if a record is available, the SELECT statement you specify for the **PollingInput** binding property will be executed.</span></span>                                                                                                              |
|       <span data-ttu-id="96c01-119">**PollingInterval**</span><span class="sxs-lookup"><span data-stu-id="96c01-119">**PollingInterval**</span></span>        | <span data-ttu-id="96c01-120">秒単位で間隔を指定、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]に指定されたステートメントが実行される、 **PolledDataAvailableStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="96c01-120">Specifies the interval, in seconds, at which the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="96c01-121">既定値は 30 秒です。</span><span class="sxs-lookup"><span data-stu-id="96c01-121">The default is 30 seconds.</span></span> <span data-ttu-id="96c01-122">ポーリング間隔は、連続するポーリングの間隔を決定します。</span><span class="sxs-lookup"><span data-stu-id="96c01-122">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="96c01-123">ステートメントは、指定した期間内で実行される、アダプターが間隔内の残りの時間の間スリープします。</span><span class="sxs-lookup"><span data-stu-id="96c01-123">If the statement is executed within the specified interval, the adapter sleeps for the remaining time in the interval.</span></span> |
|         <span data-ttu-id="96c01-124">**PollingInput**</span><span class="sxs-lookup"><span data-stu-id="96c01-124">**PollingInput**</span></span>         |                         <span data-ttu-id="96c01-125">ポーリング ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="96c01-125">Specifies the polling statement.</span></span> <span data-ttu-id="96c01-126">SELECT ステートメントを使用してポーリングする、このバインドのプロパティの SELECT ステートメントを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c01-126">To poll using a SELECT statement, you must specify a SELECT statement for this binding property.</span></span> <span data-ttu-id="96c01-127">既定値は null です。</span><span class="sxs-lookup"><span data-stu-id="96c01-127">The default is null.</span></span><br /><br /> <span data-ttu-id="96c01-128">値を指定する必要があります**PollingInput**ポーリングを有効にするプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="96c01-128">You must specify a value for **PollingInput** binding property to enable polling.</span></span> <span data-ttu-id="96c01-129">ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="96c01-129">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span>                          |
|        <span data-ttu-id="96c01-130">**PollingAction**</span><span class="sxs-lookup"><span data-stu-id="96c01-130">**PollingAction**</span></span>         |                                                                                                                <span data-ttu-id="96c01-131">ポーリング操作のアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="96c01-131">Specifies the action for the polling operation.</span></span> <span data-ttu-id="96c01-132">使用して、操作に対して生成されたサービスのインターフェイスからポーリング アクションを決定することができます、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="96c01-132">You can determine the polling action from the service interface generated for the operation using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span>                                                                                                                |
|      <span data-ttu-id="96c01-133">**PostPollStatement**</span><span class="sxs-lookup"><span data-stu-id="96c01-133">**PostPollStatement**</span></span>       |                                                                                                                                                                  <span data-ttu-id="96c01-134">指定されたステートメントの後に実行されるステートメント ブロックを指定します、 **PollingInput**プロパティのバインドを実行します。</span><span class="sxs-lookup"><span data-stu-id="96c01-134">Specifies a statement block that is executed after the statement specified by the **PollingInput** binding property is executed.</span></span>                                                                                                                                                                  |
|      <span data-ttu-id="96c01-135">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="96c01-135">**PollWhileDataFound**</span></span>      |                                    <span data-ttu-id="96c01-136">指定するかどうか、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ポーリング間隔を無視し、継続的にデータがポーリングされるテーブルで使用できる場合に、ポーリング ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="96c01-136">Specifies whether the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ignores the polling interval and continuously executes the polling statement, if data is available in the table being polled.</span></span> <span data-ttu-id="96c01-137">テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔でポーリング ステートメントを実行する元に戻します。</span><span class="sxs-lookup"><span data-stu-id="96c01-137">If no data is available in the table, the adapter reverts to execute the polling statement at the specified polling interval.</span></span> <span data-ttu-id="96c01-138">既定値は false です。</span><span class="sxs-lookup"><span data-stu-id="96c01-138">Default is false.</span></span>                                     |

 <span data-ttu-id="96c01-139">これらのプロパティの詳細については、次を参照してください。 [Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="96c01-139">For a more complete description of these properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="96c01-140">使用する方法の詳細については、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースをポーリングするには、このトピックの残りの部分を参照します。</span><span class="sxs-lookup"><span data-stu-id="96c01-140">For a complete description of how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll the Oracle database, read the remainder of this topic.</span></span>  

## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="96c01-141">このトピックでポーリングしていますか</span><span class="sxs-lookup"><span data-stu-id="96c01-141">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="96c01-142">示すために、このトピックの「方法、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] SELECT ステートメントを使用してメッセージを変更するデータの受信をサポート、ポーリングすると、 **MS_SAMPLE_EMPLOYEE**インターフェイス テーブルに、**アプリケーション オブジェクト ライブラリ**アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="96c01-142">In this topic, to demonstrate how the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports receiving data change messages using SELECT statements, you poll the **MS_SAMPLE_EMPLOYEE** interface table in the **Application Object Library** application.</span></span> <span data-ttu-id="96c01-143">Oracle E-business Suite でこれらのオブジェクトを作成するサンプルで提供される create_apps_artifacts.sql スクリプトを実行するときに、このテーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="96c01-143">This table is created when you run the create_apps_artifacts.sql script provided with the samples to create these objects in Oracle E-Business Suite.</span></span>  

 <span data-ttu-id="96c01-144">ポーリング操作を説明するために、次の項目行います。</span><span class="sxs-lookup"><span data-stu-id="96c01-144">To demonstrate a polling operation, we do the following:</span></span>  

-   <span data-ttu-id="96c01-145">SELECT ステートメントを指定、 **PolledDataAvailableStatement**データがある場所インターフェイス テーブルの中にポーリングされます (MS_SAMPLE_EMPLOYEE) を決定するプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="96c01-145">Specify a SELECT statement for the **PolledDataAvailableStatement** binding property to determine where the interface table being polled (MS_SAMPLE_EMPLOYEE) has any data.</span></span> <span data-ttu-id="96c01-146">この例では、としては、このバインド プロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="96c01-146">In this example, you can set this binding property as:</span></span>  

    ```  
    SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE  
    ```  

     <span data-ttu-id="96c01-147">これにより、MS_SAMPLE_EMPLOYEE インターフェイス テーブルにいくつかのレコードがある場合にのみ、アダプターがポーリング ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="96c01-147">This ensures that the adapter executes the polling statement only when the MS_SAMPLE_EMPLOYEE interface table has some records.</span></span>  

-   <span data-ttu-id="96c01-148">SELECT ステートメントを指定、 **PollingInput**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="96c01-148">Specify a SELECT statement for the **PollingInput** binding property.</span></span> <span data-ttu-id="96c01-149">このステートメントは、MS_SAMPLE_EMPLOYEE インターフェイス テーブル内のすべての行を取得します。</span><span class="sxs-lookup"><span data-stu-id="96c01-149">This statement retrieves all the rows in the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="96c01-150">この例では、としては、このバインド プロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="96c01-150">In this example, you can set this binding property as:</span></span>  

    ```  
    SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE  
    ```  

    > [!NOTE]
    >  <span data-ttu-id="96c01-151">SELECT ステートメントで使用される FOR UPDATE 句の詳細については、次を参照してください。 [Oracle E-business Suite からのポーリングに基づいたデータ変更メッセージを受信](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md)します。</span><span class="sxs-lookup"><span data-stu-id="96c01-151">For information about the FOR UPDATE clause used in the SELECT statement, see [Receive polling-based data-changed messages from Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md).</span></span>  

-   <span data-ttu-id="96c01-152">DELETE ステートメントを指定の一部として、 **PostPollStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="96c01-152">Specify a DELETE statement as part of the **PostPollStatement** binding property.</span></span> <span data-ttu-id="96c01-153">このステートメントは、すべてのデータを MS_SAMPLE_EMPLOYEE インターフェイス テーブルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="96c01-153">This statement will delete all data from MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="96c01-154">この例では、としては、このバインド プロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="96c01-154">In this example, you can set this binding property as:</span></span>  

    ```  
    DELETE FROM MS_SAMPLE_EMPLOYEE  
    ```  

     <span data-ttu-id="96c01-155">このような場合は、次回の指定されたステートメント**PollingInput**は実行すると、それをフェッチできませんすべてのデータ。</span><span class="sxs-lookup"><span data-stu-id="96c01-155">After this happens, the next time the statement specified for **PollingInput** will be executed, it will not fetch any data.</span></span>  

-   <span data-ttu-id="96c01-156">多くのデータは MS_SAMPLE_EMPLOYEE インターフェイス テーブルに追加されるまで、新しいレコードを含む MS_SAMPLE_EMPLOYEE インターフェイス テーブルを再作成する必要がありますのでにポーリング メッセージを取得できません。</span><span class="sxs-lookup"><span data-stu-id="96c01-156">Until more data is added to the MS_SAMPLE_EMPLOYEE interface table, you will not get any polling messages so you must repopulate the MS_SAMPLE_EMPLOYEE interface table with new records.</span></span> <span data-ttu-id="96c01-157">サンプルで提供される insert_apps_data.sql スクリプトを実行して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="96c01-157">You can do so by running the insert_apps_data.sql script provided with the samples.</span></span> <span data-ttu-id="96c01-158">このスクリプトを実行した後、次のポーリング操作によって新しいレコードをテーブルに挿入がフェッチされます。</span><span class="sxs-lookup"><span data-stu-id="96c01-158">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span>  

## <a name="consuming-the-polling-request-message"></a><span data-ttu-id="96c01-159">ポーリング要求メッセージの使用</span><span class="sxs-lookup"><span data-stu-id="96c01-159">Consuming the Polling Request Message</span></span>  
 <span data-ttu-id="96c01-160">アダプターは、Oracle E-business Suite をポーリングするようにコードでは、ポーリング操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="96c01-160">The adapter invokes the polling operation on your code to poll the Oracle E-Business Suite.</span></span> <span data-ttu-id="96c01-161">つまり、アダプターは、IInputChannel のチャネル形状の上に表示されるポーリング要求メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="96c01-161">That is, the adapter sends a polling request message that you receive over an IInputChannel channel shape.</span></span> <span data-ttu-id="96c01-162">ポーリング要求メッセージにはで指定されたクエリの結果セットが含まれています、 **PollingInput**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="96c01-162">The polling request message contains the result set of the query specified by the **PollingInput** binding property.</span></span> <span data-ttu-id="96c01-163">2 つの方法のいずれかでポーリング メッセージを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="96c01-163">You can consume the polling message in one of two ways:</span></span>  

-   <span data-ttu-id="96c01-164">ノード値のストリーミングを使用してメッセージを処理するには、呼び出す必要がある、 **WriteBodyContents**メソッドからの応答でメッセージを渡して、 **XmlDictionaryWriter**ノード値のストリーミングを実装します。</span><span class="sxs-lookup"><span data-stu-id="96c01-164">To consume the message using node-value streaming, you must call the **WriteBodyContents** method on the response message and pass it an **XmlDictionaryWriter** that implements node-value streaming.</span></span>  

-   <span data-ttu-id="96c01-165">ノードのストリーミングを使用してメッセージを処理するには、呼び出すことができます**GetReaderAtBodyContents**を取得する応答メッセージで、 **XmlReader**します。</span><span class="sxs-lookup"><span data-stu-id="96c01-165">To consume the message using node streaming, you can call **GetReaderAtBodyContents** on the response message to get an **XmlReader**.</span></span>  

## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="96c01-166">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="96c01-166">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="96c01-167">このトピックの例では、MS_SAMPLE_EMPLOYEE インターフェイス テーブルをポーリングします。</span><span class="sxs-lookup"><span data-stu-id="96c01-167">The examples in this topic poll the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="96c01-168">テーブルを生成するスクリプトは、サンプルで提供されます。</span><span class="sxs-lookup"><span data-stu-id="96c01-168">A script to generate the table is supplied with the samples.</span></span> <span data-ttu-id="96c01-169">サンプルの詳細については、次を参照してください。 [Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="96c01-169">For more information about the samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="96c01-170">サンプルについては、 **SelectPolling_ChannelModel**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="96c01-170">A sample, **SelectPolling_ChannelModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  

## <a name="receiving-inbound-messages-for-polling-operation-using-the-wcf-channel-model"></a><span data-ttu-id="96c01-171">WCF チャネル モデルを使用してポーリング操作の着信メッセージを受信</span><span class="sxs-lookup"><span data-stu-id="96c01-171">Receiving Inbound Messages for Polling Operation Using the WCF Channel Model</span></span>  
 <span data-ttu-id="96c01-172">このセクションを使用してポーリングの受信メッセージを受信する .NET アプリケーション (チャネル モデル) を作成する方法に関する説明、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="96c01-172">This section provides instructions on how to write a .NET application (channel model) to receive inbound polling messages using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  

#### <a name="to-receive-polling-messages-from-the-adapter"></a><span data-ttu-id="96c01-173">アダプターからポーリング メッセージを受信するには</span><span class="sxs-lookup"><span data-stu-id="96c01-173">To receive polling messages from the adapter</span></span>  

1. <span data-ttu-id="96c01-174">Microsoft Visual C#® プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="96c01-174">Create a Microsoft Visual C#® project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="96c01-175">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="96c01-175">For this topic, create a console application.</span></span>  

2. <span data-ttu-id="96c01-176">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.OracleEBS`、 `Microsoft.ServiceModel.Channels`、 `System.ServiceModel`、および`System.Runtime.Serialization`します。</span><span class="sxs-lookup"><span data-stu-id="96c01-176">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, and `System.Runtime.Serialization`.</span></span>  

3. <span data-ttu-id="96c01-177">Program.cs ファイルを開き、次の名前空間を追加します。</span><span class="sxs-lookup"><span data-stu-id="96c01-177">Open the Program.cs file and add the following namespaces:</span></span>  

   -   `Microsoft.Adapters.OracleEBS`  

   -   `System.ServiceModel`  

   -   `System.ServiceModel.Description`  

   -   `System.ServiceModel.Channels`  

   -   `System.Xml`  

4. <span data-ttu-id="96c01-178">接続 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="96c01-178">Specify a connection URI.</span></span> <span data-ttu-id="96c01-179">アダプターの接続 URI の詳細については、次を参照してください。 [Oracle E-business Suite 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="96c01-179">For more information about the adapter connection URI, see [Create the Oracle E-Business Suite connection URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md).</span></span>  

   ```  
   Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
   ```  

5. <span data-ttu-id="96c01-180">インスタンスを作成**OracleEBSBinding**ポーリングを構成するために必要なバインドのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="96c01-180">Create an instance of **OracleEBSBinding** and set the binding properties required to configure polling.</span></span> <span data-ttu-id="96c01-181">設定する必要がありますには、少なくとも、 **InboundOperationType**、 **PolledDataAvailableStatement**、 **PollingInput**、および**PollingAction**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="96c01-181">At a minimum you must set the **InboundOperationType**, **PolledDataAvailableStatement**, **PollingInput**, and **PollingAction** binding properties.</span></span> <span data-ttu-id="96c01-182">ポーリングを構成するためのプロパティのバインドの詳細については、次を参照してください。[受信呼び出しのポーリングを使用してサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)します。</span><span class="sxs-lookup"><span data-stu-id="96c01-182">For more information about binding properties used to configure polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  

   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   binding.InboundOperationType = InboundOperation.Polling;  
   binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
   binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
   binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
   binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
   ```  

6. <span data-ttu-id="96c01-183">インターフェイス テーブルをポーリングするため、アプリケーションのコンテキストを設定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="96c01-183">Because you are polling an interface table, you must also set the applications context.</span></span> <span data-ttu-id="96c01-184">アプリケーションのコンテキストとアプリケーション コンテキストの設定に必要なバインドのプロパティの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。</span><span class="sxs-lookup"><span data-stu-id="96c01-184">For more information about application context and binding properties required for setting application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  

   ```  
   binding.OracleUserName = "<Enter user name here>";  
   binding.OraclePassword = "<Enter password here>";  
   binding.OracleEBSResponsibilityName = "<Enter responsibility here>";  
   ```  

7. <span data-ttu-id="96c01-185">バインディング パラメーターのコレクションを作成し、資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="96c01-185">Create a binding parameter collection and set the credentials.</span></span>  

   ```  
   ClientCredentials credentials = new ClientCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  

   BindingParameterCollection bindingParams = new BindingParameterCollection();  
   bindingParams.Add(credentials);  
   ```  

8. <span data-ttu-id="96c01-186">チャネル リスナーを作成し、開きます。</span><span class="sxs-lookup"><span data-stu-id="96c01-186">Create a channel listener and open it.</span></span> <span data-ttu-id="96c01-187">呼び出すことによって、リスナーを作成する**BuildChannelListener < IInputChannel\>** メソッドを**OracleEBSBinding**します。</span><span class="sxs-lookup"><span data-stu-id="96c01-187">You create the listener by invoking **BuildChannelListener<IInputChannel\>** method on the **OracleEBSBinding**.</span></span>  

   ```  
   IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
   listener.Open();  
   ```  

9. <span data-ttu-id="96c01-188">取得、 **IInputChannel**チャネルを呼び出すことによって、 **AcceptChannel**メソッド リスナーを開きます。</span><span class="sxs-lookup"><span data-stu-id="96c01-188">Get an **IInputChannel** channel by invoking the **AcceptChannel** method on the listener and open it.</span></span>  

    ```  
    IInputChannel channel = listener.AcceptChannel();  
    channel.Open();  
    ```  

10. <span data-ttu-id="96c01-189">呼び出す**受信**アダプターから次の受信メッセージを取得するチャネル。</span><span class="sxs-lookup"><span data-stu-id="96c01-189">Invoke **Receive** on the channel to get the next inbound message from the adapter.</span></span>  

    ```  
    Message message = channel.Receive();  
    ```  

11. <span data-ttu-id="96c01-190">受信操作によって返される結果セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="96c01-190">Consume the result set returned by the inbound operation.</span></span> <span data-ttu-id="96c01-191">いずれかを使用してメッセージを処理することができます、 **XmlReader**または**XmlDictionaryWriter**します。</span><span class="sxs-lookup"><span data-stu-id="96c01-191">You can consume the message using either an **XmlReader** or an **XmlDictionaryWriter**.</span></span>  

    ```  
    XmlReader reader = message.GetReaderAtBodyContents();  
    ```  

12. <span data-ttu-id="96c01-192">要求の処理が完了したら、チャネルを閉じます。</span><span class="sxs-lookup"><span data-stu-id="96c01-192">Close the channel when you have completed processing the request.</span></span>  

    ```  
    channel.Close()  
    ```  

    > [!IMPORTANT]
    >  <span data-ttu-id="96c01-193">受信操作の処理が完了した後、チャネルを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c01-193">You must close the channel after you have finished processing the inbound operation.</span></span> <span data-ttu-id="96c01-194">チャネルを閉じない、コードの動作に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="96c01-194">Failure to close the channel may affect the behavior of your code.</span></span>  

13. <span data-ttu-id="96c01-195">データ変更メッセージの受信が完了したら、リスナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="96c01-195">Close the listener when you are finished receiving data-changed messages.</span></span>  

    ```  
    listener.Close()  
    ```  

    > [!IMPORTANT]
    >  <span data-ttu-id="96c01-196">リスナーを閉じる、リスナーを使用して作成されるチャネルは閉じられません。</span><span class="sxs-lookup"><span data-stu-id="96c01-196">Closing the listener does not close channels created using the listener.</span></span> <span data-ttu-id="96c01-197">各チャネル リスナーを使用して作成を明示的に閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c01-197">You must explicitly close each channel created using the listener.</span></span>  

### <a name="example"></a><span data-ttu-id="96c01-198">例</span><span class="sxs-lookup"><span data-stu-id="96c01-198">Example</span></span>  
 <span data-ttu-id="96c01-199">次の例では、MS_SAMPLE_EMPLOYEE インターフェイス テーブルをポーリングするポーリング アプリケーションを示します。</span><span class="sxs-lookup"><span data-stu-id="96c01-199">The following example shows a polling application that polls the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="96c01-200">**PollingInput**プロパティには、MS_SAMPLE_EMPLOYEE テーブルからすべてのデータを読み取る select ステートメントが含まれているし、ポーリング後ステートメントは、同じテーブルからすべてのデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="96c01-200">The **PollingInput** property contains the select statement that reads all the data from the MS_SAMPLE_EMPLOYEE table and the post poll statement deletes all the data from the same table.</span></span> <span data-ttu-id="96c01-201">ポーリング メッセージを書き込む`C:\PollingOutput.xml`します。</span><span class="sxs-lookup"><span data-stu-id="96c01-201">The polling message is written to `C:\PollingOutput.xml`.</span></span>  

 <span data-ttu-id="96c01-202">後続のポーリング メッセージではより多くのデータが MS_SAMPLE_EMPLOYEE インターフェイス テーブルに追加されるまで任意のレコードは含まれません。</span><span class="sxs-lookup"><span data-stu-id="96c01-202">Subsequent polling messages will not contain any records until more data is added to the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="96c01-203">サンプルで提供される insert_apps_data.sql スクリプトを実行して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="96c01-203">You can do so by running the insert_apps_data.sql script provided with the samples.</span></span> <span data-ttu-id="96c01-204">このスクリプトを実行した後、次のポーリング操作によって新しいレコードをテーブルに挿入がフェッチされます。</span><span class="sxs-lookup"><span data-stu-id="96c01-204">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span> <span data-ttu-id="96c01-205">アダプターのポーリングを押して、サービス ホストを終了するまでは引き続き\<返す\>します。</span><span class="sxs-lookup"><span data-stu-id="96c01-205">The adapter will continue to poll until you close the service host by pressing \<RETURN\>.</span></span>  

```  
using System;  
using Microsoft.Adapters.OracleEBS;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Xml;  

namespace SelectPolling_ChannelModel  
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

                OracleEBSBinding binding = new OracleEBSBinding();  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
                binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
                binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
                binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
                binding.OracleUserName = "<Enter user name here>";  
                binding.OraclePassword = "<Enter password here>";  
                binding.OracleEBSResponsibilityName = "<Enter responsibility here>";  

                Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name?");  

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
                Console.ReadLine();  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                    Console.ReadLine();  
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

## <a name="see-also"></a><span data-ttu-id="96c01-206">参照</span><span class="sxs-lookup"><span data-stu-id="96c01-206">See Also</span></span>  
 [<span data-ttu-id="96c01-207">WCF チャネル モデルを使用して Oracle E-business Suite のアプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="96c01-207">Develop Oracle E-Business Suite applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)