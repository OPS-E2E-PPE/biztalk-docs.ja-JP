---
title: WCF チャネル モデルを含む SELECT ステートメントを使用してポーリング Oracle E-business Suite |Microsoft ドキュメント
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
ms.openlocfilehash: 1164cb59bf7fe0e168834f60364cd82f871b3ae0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965744"
---
# <a name="poll-oracle-e-business-suite-using-select-statement-with-the-wcf-channel-model"></a><span data-ttu-id="4e5b2-102">WCF チャネル モデルを含む SELECT ステートメントを使用してポーリング Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="4e5b2-102">Poll Oracle E-Business Suite using SELECT statement with the WCF channel model</span></span>
<span data-ttu-id="4e5b2-103">構成することができます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]メッセージを受信するデータの定期的な変更を継続的にインターフェイスのテーブルをポーリングする SELECT ステートメントを使用して、ビュー、テーブルおよびビュー Oracle E-business suite のインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-103">You can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive periodic data-change messages by using a SELECT statement to continuously poll the interface tables, interface views, tables and views in Oracle E-Business Suite.</span></span> <span data-ttu-id="4e5b2-104">Oracle E-business Suite をポーリングするアダプターが定期的に実行されるポーリング ステートメントと SELECT ステートメントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-104">You can specify a SELECT statement as a polling statement that the adapter executes periodically to poll Oracle E-Business Suite.</span></span> <span data-ttu-id="4e5b2-105">後の投票 PL/SQL コード ブロックを指定することも、アダプターが、ポーリング ステートメントが実行された後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-105">You can also specify a post-poll PL/SQL code block that the adapter executes after the polling statement is executed.</span></span>  
  
 <span data-ttu-id="4e5b2-106">ポーリングを有効にするには、このトピックの説明に従って、特定のバインディング プロパティの条件を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-106">To enable polling, you must specify certain binding properties as described in this topic.</span></span> <span data-ttu-id="4e5b2-107">アダプターがポーリングをサポートする方法の詳細については、次を参照してください。[呼び出しをポーリングを使用して受信するためのサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)です。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-107">For more information about how the adapter supports polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  
  
## <a name="configuring-a-polling-operation-with-oracle-e-business-suite-adapter-binding-properties"></a><span data-ttu-id="4e5b2-108">Oracle E-business Suite アダプターのバインドのプロパティとポーリング操作を構成します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-108">Configuring a Polling Operation with Oracle E-Business Suite Adapter Binding Properties</span></span>  
 <span data-ttu-id="4e5b2-109">次の表、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]データを受信するアダプターの構成に使用するバインドのプロパティがメッセージを変更します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-109">The following table summarizes the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding properties that you use to configure the adapter to receive data change messages.</span></span> <span data-ttu-id="4e5b2-110">これらのバインディング プロパティを指定すると、ポーリング アプリケーションの実行中にあります。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-110">You must specify these binding properties while running the polling application.</span></span>  
  
|<span data-ttu-id="4e5b2-111">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="4e5b2-111">Binding Property</span></span>|<span data-ttu-id="4e5b2-112">Description</span><span class="sxs-lookup"><span data-stu-id="4e5b2-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="4e5b2-113">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="4e5b2-113">**InboundOperationType**</span></span>|<span data-ttu-id="4e5b2-114">実行するかどうかを示す**ポーリング**または**通知**操作を受信します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-114">Specifies whether you want to perform **Polling** or **Notification** inbound operation.</span></span> <span data-ttu-id="4e5b2-115">既定値は**ポーリング**です。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-115">Default is **Polling**.</span></span>|  
|<span data-ttu-id="4e5b2-116">**PolledDataAvailableStatement**</span><span class="sxs-lookup"><span data-stu-id="4e5b2-116">**PolledDataAvailableStatement**</span></span>|<span data-ttu-id="4e5b2-117">すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-117">Specifies the SQL statement that the adapter executes to determine whether any data is available for polling.</span></span> <span data-ttu-id="4e5b2-118">レコードがある場合にのみ、SELECT ステートメントを指定するため、 **PollingInput**プロパティのバインドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-118">Only if a record is available, the SELECT statement you specify for the **PollingInput** binding property will be executed.</span></span>|  
|<span data-ttu-id="4e5b2-119">**PollingInterval**</span><span class="sxs-lookup"><span data-stu-id="4e5b2-119">**PollingInterval**</span></span>|<span data-ttu-id="4e5b2-120">秒単位で間隔を指定、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]の指定されたステートメントの実行、 **PolledDataAvailableStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-120">Specifies the interval, in seconds, at which the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] executes the statement specified for the **PolledDataAvailableStatement** binding property.</span></span> <span data-ttu-id="4e5b2-121">既定値は 30 秒です。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-121">The default is 30 seconds.</span></span> <span data-ttu-id="4e5b2-122">ポーリング間隔では、連続するポーリングの間隔を決定します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-122">The polling interval determines the time interval between successive polls.</span></span> <span data-ttu-id="4e5b2-123">ステートメントは、指定した期間内で実行される、アダプター休止状態に入ります残り時間の間隔。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-123">If the statement is executed within the specified interval, the adapter sleeps for the remaining time in the interval.</span></span>|  
|<span data-ttu-id="4e5b2-124">**PollingInput**</span><span class="sxs-lookup"><span data-stu-id="4e5b2-124">**PollingInput**</span></span>|<span data-ttu-id="4e5b2-125">ポーリング ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-125">Specifies the polling statement.</span></span> <span data-ttu-id="4e5b2-126">SELECT ステートメントを使用してポーリングを行うには、このバインディングのプロパティの SELECT ステートメントを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-126">To poll using a SELECT statement, you must specify a SELECT statement for this binding property.</span></span> <span data-ttu-id="4e5b2-127">既定値は null です。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-127">The default is null.</span></span><br /><br /> <span data-ttu-id="4e5b2-128">値を指定する必要があります**PollingInput**ポーリングを有効にするプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-128">You must specify a value for **PollingInput** binding property to enable polling.</span></span> <span data-ttu-id="4e5b2-129">ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-129">The polling statement is executed only if there is data available for polling, which is determined by the **PolledDataAvailableStatement** binding property.</span></span>|  
|<span data-ttu-id="4e5b2-130">**PollingAction**</span><span class="sxs-lookup"><span data-stu-id="4e5b2-130">**PollingAction**</span></span>|<span data-ttu-id="4e5b2-131">ポーリング操作のアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-131">Specifies the action for the polling operation.</span></span> <span data-ttu-id="4e5b2-132">使用して、操作の生成、サービス インターフェイスからのポーリング動作を指定できます、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-132">You can determine the polling action from the service interface generated for the operation using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span>|  
|<span data-ttu-id="4e5b2-133">**PostPollStatement**</span><span class="sxs-lookup"><span data-stu-id="4e5b2-133">**PostPollStatement**</span></span>|<span data-ttu-id="4e5b2-134">指定されたステートメントの後に実行されるステートメント ブロックを指定します、 **PollingInput**プロパティのバインドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-134">Specifies a statement block that is executed after the statement specified by the **PollingInput** binding property is executed.</span></span>|  
|<span data-ttu-id="4e5b2-135">**PollWhileDataFound**</span><span class="sxs-lookup"><span data-stu-id="4e5b2-135">**PollWhileDataFound**</span></span>|<span data-ttu-id="4e5b2-136">指定するかどうか、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ポーリング間隔を無視し、継続的にデータで使用できる場合、テーブルをポーリングするポーリング ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-136">Specifies whether the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ignores the polling interval and continuously executes the polling statement, if data is available in the table being polled.</span></span> <span data-ttu-id="4e5b2-137">テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔でポーリング ステートメントを実行する元に戻します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-137">If no data is available in the table, the adapter reverts to execute the polling statement at the specified polling interval.</span></span> <span data-ttu-id="4e5b2-138">既定値は false です。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-138">Default is false.</span></span>|  
  
 <span data-ttu-id="4e5b2-139">これらのプロパティの詳細については、次を参照してください。 [Oracle E-business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-139">For a more complete description of these properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="4e5b2-140">使用する方法の詳細については、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースをポーリングするには、このトピックの残りの部分を参照します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-140">For a complete description of how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll the Oracle database, read the remainder of this topic.</span></span>  
  
## <a name="how-this-topic-demonstrates-polling"></a><span data-ttu-id="4e5b2-141">このトピックの内容がポーリングを示しています</span><span class="sxs-lookup"><span data-stu-id="4e5b2-141">How This Topic Demonstrates Polling</span></span>  
 <span data-ttu-id="4e5b2-142">このトピックの内容を示すために方法、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] SELECT ステートメントを使用してメッセージを変更するデータの受信をサポート、ポーリングを続けた、 **MS_SAMPLE_EMPLOYEE**インターフェイス テーブルに、**アプリケーション オブジェクト ライブラリ**アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-142">In this topic, to demonstrate how the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports receiving data change messages using SELECT statements, you poll the **MS_SAMPLE_EMPLOYEE** interface table in the **Application Object Library** application.</span></span> <span data-ttu-id="4e5b2-143">次の表は、Oracle E-business Suite でこれらのオブジェクトを作成するサンプルに用意されている create_apps_artifacts.sql スクリプトを実行するときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-143">This table is created when you run the create_apps_artifacts.sql script provided with the samples to create these objects in Oracle E-Business Suite.</span></span>  
  
 <span data-ttu-id="4e5b2-144">ポーリング操作を示すためは、次を操作します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-144">To demonstrate a polling operation, we do the following:</span></span>  
  
-   <span data-ttu-id="4e5b2-145">SELECT ステートメントを指定、 **PolledDataAvailableStatement**データがある場所のインターフェイス テーブルでポーリング (MS_SAMPLE_EMPLOYEE) を決定するプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-145">Specify a SELECT statement for the **PolledDataAvailableStatement** binding property to determine where the interface table being polled (MS_SAMPLE_EMPLOYEE) has any data.</span></span> <span data-ttu-id="4e5b2-146">この例では、このバインディングのプロパティとしてを設定できます。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-146">In this example, you can set this binding property as:</span></span>  
  
    ```  
    SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE  
    ```  
  
     <span data-ttu-id="4e5b2-147">これにより、MS_SAMPLE_EMPLOYEE インターフェイス テーブルにレコードの一部がある場合にのみ、アダプターが、ポーリング ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-147">This ensures that the adapter executes the polling statement only when the MS_SAMPLE_EMPLOYEE interface table has some records.</span></span>  
  
-   <span data-ttu-id="4e5b2-148">SELECT ステートメントを指定、 **PollingInput**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-148">Specify a SELECT statement for the **PollingInput** binding property.</span></span> <span data-ttu-id="4e5b2-149">このステートメントは、MS_SAMPLE_EMPLOYEE インターフェイス テーブル内のすべての行を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-149">This statement retrieves all the rows in the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="4e5b2-150">この例では、このバインディングのプロパティとしてを設定できます。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-150">In this example, you can set this binding property as:</span></span>  
  
    ```  
    SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="4e5b2-151">SELECT ステートメントで使用される FOR UPDATE 句の詳細については、次を参照してください。 [Oracle E-business Suite からデータ変更のポーリングに基づいたメッセージを受信](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md)です。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-151">For information about the FOR UPDATE clause used in the SELECT statement, see [Receive polling-based data-changed messages from Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md).</span></span>  
  
-   <span data-ttu-id="4e5b2-152">一部として、DELETE ステートメントを指定、 **PostPollStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-152">Specify a DELETE statement as part of the **PostPollStatement** binding property.</span></span> <span data-ttu-id="4e5b2-153">このステートメントは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルからすべてのデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-153">This statement will delete all data from MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="4e5b2-154">この例では、このバインディングのプロパティとしてを設定できます。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-154">In this example, you can set this binding property as:</span></span>  
  
    ```  
    DELETE FROM MS_SAMPLE_EMPLOYEE  
    ```  
  
     <span data-ttu-id="4e5b2-155">これが発生した後、次回の指定されたステートメント**PollingInput**は実行すると、それはフェッチできませんすべてのデータ。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-155">After this happens, the next time the statement specified for **PollingInput** will be executed, it will not fetch any data.</span></span>  
  
-   <span data-ttu-id="4e5b2-156">多くのデータは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルに追加される、まで、新しいレコードを含む MS_SAMPLE_EMPLOYEE インターフェイス テーブルを再作成する必要がありますのでにポーリング メッセージを取得できません。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-156">Until more data is added to the MS_SAMPLE_EMPLOYEE interface table, you will not get any polling messages so you must repopulate the MS_SAMPLE_EMPLOYEE interface table with new records.</span></span> <span data-ttu-id="4e5b2-157">サンプルに用意されている insert_apps_data.sql スクリプトを実行して、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-157">You can do so by running the insert_apps_data.sql script provided with the samples.</span></span> <span data-ttu-id="4e5b2-158">このスクリプトを実行した後、次のポーリング操作によって新しいレコードをテーブルに挿入がフェッチされます。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-158">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span>  
  
## <a name="consuming-the-polling-request-message"></a><span data-ttu-id="4e5b2-159">ポーリング要求メッセージの使用</span><span class="sxs-lookup"><span data-stu-id="4e5b2-159">Consuming the Polling Request Message</span></span>  
 <span data-ttu-id="4e5b2-160">アダプターは、Oracle E-business Suite をポーリングするようにコードでポーリング操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-160">The adapter invokes the polling operation on your code to poll the Oracle E-Business Suite.</span></span> <span data-ttu-id="4e5b2-161">つまり、アダプターは、IInputChannel チャネル形状経由で受信したポーリング要求メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-161">That is, the adapter sends a polling request message that you receive over an IInputChannel channel shape.</span></span> <span data-ttu-id="4e5b2-162">ポーリング要求メッセージにはで指定されたクエリの結果セットが含まれています、 **PollingInput**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-162">The polling request message contains the result set of the query specified by the **PollingInput** binding property.</span></span> <span data-ttu-id="4e5b2-163">2 つの方法のいずれかでポーリング メッセージを利用できます。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-163">You can consume the polling message in one of two ways:</span></span>  
  
-   <span data-ttu-id="4e5b2-164">ノード値のストリーミングを使用してメッセージを処理するには、呼び出す必要があります、 **WriteBodyContents**メソッド、応答でメッセージを渡します、 **XmlDictionaryWriter**ノード値のストリーミングを実装します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-164">To consume the message using node-value streaming, you must call the **WriteBodyContents** method on the response message and pass it an **XmlDictionaryWriter** that implements node-value streaming.</span></span>  
  
-   <span data-ttu-id="4e5b2-165">ノードのストリーミングを使用してメッセージを処理するには、呼び出すことができます**GetReaderAtBodyContents**を取得する応答メッセージで、 **XmlReader**です。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-165">To consume the message using node streaming, you can call **GetReaderAtBodyContents** on the response message to get an **XmlReader**.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="4e5b2-166">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="4e5b2-166">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="4e5b2-167">このトピックの例では、MS_SAMPLE_EMPLOYEE インターフェイス テーブルをポーリングします。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-167">The examples in this topic poll the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="4e5b2-168">テーブルを生成するスクリプトは、サンプルの値が提供されます。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-168">A script to generate the table is supplied with the samples.</span></span> <span data-ttu-id="4e5b2-169">サンプルの詳細については、次を参照してください。 [Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-169">For more information about the samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="4e5b2-170">サンプルは、 **SelectPolling_ChannelModel**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプルです。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-170">A sample, **SelectPolling_ChannelModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="receiving-inbound-messages-for-polling-operation-using-the-wcf-channel-model"></a><span data-ttu-id="4e5b2-171">WCF チャネル モデルを使用してポーリング操作の着信メッセージを受信</span><span class="sxs-lookup"><span data-stu-id="4e5b2-171">Receiving Inbound Messages for Polling Operation Using the WCF Channel Model</span></span>  
 <span data-ttu-id="4e5b2-172">このセクションの内容を使用してポーリングの受信メッセージを受信する .NET アプリケーション (チャネル モデル) を記述する方法の手順を説明する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-172">This section provides instructions on how to write a .NET application (channel model) to receive inbound polling messages using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
#### <a name="to-receive-polling-messages-from-the-adapter"></a><span data-ttu-id="4e5b2-173">アダプターからポーリング メッセージを受信するには</span><span class="sxs-lookup"><span data-stu-id="4e5b2-173">To receive polling messages from the adapter</span></span>  
  
1.  <span data-ttu-id="4e5b2-174">Microsoft Visual C#® プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-174">Create a Microsoft Visual C#® project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="4e5b2-175">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-175">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="4e5b2-176">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.OracleEBS`、 `Microsoft.ServiceModel.Channels`、 `System.ServiceModel`、および`System.Runtime.Serialization`です。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-176">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, and `System.Runtime.Serialization`.</span></span>  
  
3.  <span data-ttu-id="4e5b2-177">Program.cs ファイルを開き、次の名前空間を追加します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-177">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Description`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
4.  <span data-ttu-id="4e5b2-178">接続 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-178">Specify a connection URI.</span></span> <span data-ttu-id="4e5b2-179">アダプターの接続 URI の詳細については、次を参照してください。 [Oracle E-business Suite 接続 URI を作成する](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-179">For more information about the adapter connection URI, see [Create the Oracle E-Business Suite connection URI](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md).</span></span>  
  
    ```  
    Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
    ```  
  
5.  <span data-ttu-id="4e5b2-180">インスタンスを作成する**OracleEBSBinding**ポーリングを構成するために必要なバインドのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-180">Create an instance of **OracleEBSBinding** and set the binding properties required to configure polling.</span></span> <span data-ttu-id="4e5b2-181">設定する必要がありますには、少なくとも、 **InboundOperationType**、 **PolledDataAvailableStatement**、 **PollingInput**、および**PollingAction**バインディング プロパティです。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-181">At a minimum you must set the **InboundOperationType**, **PolledDataAvailableStatement**, **PollingInput**, and **PollingAction** binding properties.</span></span> <span data-ttu-id="4e5b2-182">ポーリングを構成するためのプロパティのバインドの詳細については、次を参照してください。[呼び出しをポーリングを使用して受信するためのサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)です。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-182">For more information about binding properties used to configure polling, see [Support for Inbound Calls Using Polling](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).</span></span>  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    binding.InboundOperationType = InboundOperation.Polling;  
    binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
    binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
    binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
    binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
    ```  
  
6.  <span data-ttu-id="4e5b2-183">インターフェイス テーブルをポーリングするため、アプリケーションのコンテキストも設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-183">Because you are polling an interface table, you must also set the applications context.</span></span> <span data-ttu-id="4e5b2-184">アプリケーション コンテキストおよびアプリケーションのコンテキストの設定に必要なバインド プロパティの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-184">For more information about application context and binding properties required for setting application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
    ```  
    binding.OracleUserName = "<Enter user name here>";  
    binding.OraclePassword = "<Enter password here>";  
    binding.OracleEBSResponsibilityName = "<Enter responsibility here>";  
    ```  
  
7.  <span data-ttu-id="4e5b2-185">バインディング パラメーターのコレクションを作成し、資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-185">Create a binding parameter collection and set the credentials.</span></span>  
  
    ```  
    ClientCredentials credentials = new ClientCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
  
    BindingParameterCollection bindingParams = new BindingParameterCollection();  
    bindingParams.Add(credentials);  
    ```  
  
8.  <span data-ttu-id="4e5b2-186">チャネル リスナーを作成し、開きます。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-186">Create a channel listener and open it.</span></span> <span data-ttu-id="4e5b2-187">呼び出すことによって、リスナーを作成する**BuildChannelListener < IInputChannel\>** メソッドを**OracleEBSBinding**です。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-187">You create the listener by invoking **BuildChannelListener<IInputChannel\>** method on the **OracleEBSBinding**.</span></span>  
  
    ```  
    IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
    listener.Open();  
    ```  
  
9. <span data-ttu-id="4e5b2-188">取得、 **IInputChannel**を呼び出してチャネル、 **AcceptChannel**リスナーでメソッドを開きます。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-188">Get an **IInputChannel** channel by invoking the **AcceptChannel** method on the listener and open it.</span></span>  
  
    ```  
    IInputChannel channel = listener.AcceptChannel();  
    channel.Open();  
    ```  
  
10. <span data-ttu-id="4e5b2-189">呼び出す**受信**アダプターから次の受信メッセージを取得するチャネル。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-189">Invoke **Receive** on the channel to get the next inbound message from the adapter.</span></span>  
  
    ```  
    Message message = channel.Receive();  
    ```  
  
11. <span data-ttu-id="4e5b2-190">入力方向の操作によって返される結果セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-190">Consume the result set returned by the inbound operation.</span></span> <span data-ttu-id="4e5b2-191">いずれかを使用してメッセージを処理することができます、 **XmlReader**または**XmlDictionaryWriter**です。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-191">You can consume the message using either an **XmlReader** or an **XmlDictionaryWriter**.</span></span>  
  
    ```  
    XmlReader reader = message.GetReaderAtBodyContents();  
    ```  
  
12. <span data-ttu-id="4e5b2-192">要求の処理を完了すると、チャネルを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-192">Close the channel when you have completed processing the request.</span></span>  
  
    ```  
    channel.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="4e5b2-193">受信操作の処理が完了した後は、チャネルを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-193">You must close the channel after you have finished processing the inbound operation.</span></span> <span data-ttu-id="4e5b2-194">チャネルを閉じない、コードの動作に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-194">Failure to close the channel may affect the behavior of your code.</span></span>  
  
13. <span data-ttu-id="4e5b2-195">メッセージのデータ変更の受信が完了したら、リスナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-195">Close the listener when you are finished receiving data-changed messages.</span></span>  
  
    ```  
    listener.Close()  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="4e5b2-196">リスナーを閉じる、リスナーを使用して作成されるチャネルは閉じられません。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-196">Closing the listener does not close channels created using the listener.</span></span> <span data-ttu-id="4e5b2-197">リスナーを使用して作成された各チャネルを明示的に閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-197">You must explicitly close each channel created using the listener.</span></span>  
  
### <a name="example"></a><span data-ttu-id="4e5b2-198">例</span><span class="sxs-lookup"><span data-stu-id="4e5b2-198">Example</span></span>  
 <span data-ttu-id="4e5b2-199">次の例では、MS_SAMPLE_EMPLOYEE インターフェイス テーブルをポーリングするポーリング アプリケーションを示します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-199">The following example shows a polling application that polls the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="4e5b2-200">**PollingInput**プロパティには、MS_SAMPLE_EMPLOYEE テーブルからすべてのデータを読み取る select ステートメントが含まれているし、ポーリング後ステートメントは、同じテーブルからすべてのデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-200">The **PollingInput** property contains the select statement that reads all the data from the MS_SAMPLE_EMPLOYEE table and the post poll statement deletes all the data from the same table.</span></span> <span data-ttu-id="4e5b2-201">ポーリング メッセージを書き込む`C:\PollingOutput.xml`です。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-201">The polling message is written to `C:\PollingOutput.xml`.</span></span>  
  
 <span data-ttu-id="4e5b2-202">多くのデータが MS_SAMPLE_EMPLOYEE インターフェイス テーブルに追加されるまで、後続のポーリング メッセージはレコードがありません。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-202">Subsequent polling messages will not contain any records until more data is added to the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="4e5b2-203">サンプルに用意されている insert_apps_data.sql スクリプトを実行して、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-203">You can do so by running the insert_apps_data.sql script provided with the samples.</span></span> <span data-ttu-id="4e5b2-204">このスクリプトを実行した後、次のポーリング操作によって新しいレコードをテーブルに挿入がフェッチされます。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-204">After you run this script, the next polling operation will fetch the new records inserted into the table.</span></span> <span data-ttu-id="4e5b2-205">アダプターはポーリングを押して、サービス ホストを終了するまで引き続き\<返す\>です。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-205">The adapter will continue to poll until you close the service host by pressing \<RETURN\>.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4e5b2-206">参照</span><span class="sxs-lookup"><span data-stu-id="4e5b2-206">See Also</span></span>  
 [<span data-ttu-id="4e5b2-207">WCF チャネル モデルを使用して Oracle E-business Suite アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="4e5b2-207">Develop Oracle E-Business Suite applications using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)