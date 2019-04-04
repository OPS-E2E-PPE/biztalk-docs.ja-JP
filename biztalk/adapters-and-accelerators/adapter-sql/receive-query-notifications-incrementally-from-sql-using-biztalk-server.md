---
title: BizTalk Server を使用して SQL から段階的クエリ通知の受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a6972e01-80be-47be-986a-c2e4e0fb0cd1
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e278b4e25db6c62127d2aac4ee8d29c3c422e463
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007763"
---
# <a name="receive-query-notifications-incrementally-from-sql-using-biztalk-server"></a><span data-ttu-id="d1afa-102">BizTalk Server を使用して SQL から段階的クエリ通知を受け取る</span><span class="sxs-lookup"><span data-stu-id="d1afa-102">Receive Query Notifications Incrementally from SQL using BizTalk Server</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="d1afa-103">説明を簡潔にするため、このトピックには、段階的に通知を受信する方法のみについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-103">For the sake of brevity, this topic only describes how to receive notifications incrementally.</span></span> <span data-ttu-id="d1afa-104">ビジネスのシナリオで、オーケストレーションは理想的には受信した通知メッセージの種類を抽出し、後続の操作を実行するためのロジックを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1afa-104">In business scenarios, the orchestration must ideally include the logic to extract the kind of notification message received and then perform any subsequent operations.</span></span> <span data-ttu-id="d1afa-105">つまり、このトピックで説明されているオーケストレーションで説明されているオーケストレーションの上に構築する必要があります[BizTalk Server を使用して SQL の特定のタスクを実行する通知メッセージを処理](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-105">In other words, the orchestration described in this topic must be built on top of the orchestration described in [Process notification messages to complete specific tasks in SQL using BizTalk Server](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md).</span></span>  
  
 <span data-ttu-id="d1afa-106">このトピックでは、構成する方法を示します、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server データベースからの増分クエリ通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-106">This topic demonstrates how to configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive incremental query notification messages from a SQL Server database.</span></span> <span data-ttu-id="d1afa-107">インクリメンタル通知を示すために、従業員、列を持つテーブルを"Status"を検討してください。</span><span class="sxs-lookup"><span data-stu-id="d1afa-107">To demonstrate incremental notifications, consider a table, Employee, with a “Status” column.</span></span> <span data-ttu-id="d1afa-108">このテーブルに新しいレコードが挿入されると、[状態] 列の値は 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-108">When a new record is inserted to this table, the value of the Status column is set to 0.</span></span> <span data-ttu-id="d1afa-109">次の手順に従ってインクリメンタル通知を受信するアダプターを構成できます。</span><span class="sxs-lookup"><span data-stu-id="d1afa-109">You can configure the adapter to receive incremental notifications by doing the following:</span></span>  
  
- <span data-ttu-id="d1afa-110">0 の状態 列であるすべてのレコードを取得する SQL ステートメントを使用して通知を登録します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-110">Register for notifications using a SQL statement that retrieves all records that have Status column as 0.</span></span> <span data-ttu-id="d1afa-111">SQL ステートメントを指定することによって行うことができます、 **NotificationStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="d1afa-111">You can do so by specifying the SQL statement for the **NotificationStatement** binding property.</span></span>  
  
- <span data-ttu-id="d1afa-112">行の通知のメッセージが受信された場合に、1 に、状態列を更新します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-112">For rows for which notification messages have been received, update the Status column to 1.</span></span>  
  
  <span data-ttu-id="d1afa-113">このトピックでは、BizTalk オーケストレーションを作成してこれを実現する BizTalk アプリケーションを構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-113">This topic demonstrates how to create a BizTalk orchestration and configure a BizTalk application to achieve this.</span></span>  
  
## <a name="configuring-notifications-with-the-sql-adapter-binding-properties"></a><span data-ttu-id="d1afa-114">SQL アダプター バインドのプロパティを使用した通知の構成</span><span class="sxs-lookup"><span data-stu-id="d1afa-114">Configuring Notifications with the SQL Adapter Binding Properties</span></span>  
 <span data-ttu-id="d1afa-115">次の表にまとめたものです、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドのプロパティ構成の SQL Server から通知を受信するために使用します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-115">The following table summarizes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding properties that you use to configure receiving notifications from SQL Server.</span></span> <span data-ttu-id="d1afa-116">受信ポートを構成するときにこれらのバインドのプロパティを指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="d1afa-116">You must specify these binding properties while configuring the receive port in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1afa-117">スキーマを生成するときに、これらのバインドのプロパティを指定することができます、**通知**は必須でない場合でも、操作します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-117">You may choose to specify these binding properties when generating the schema for the **Notification** operation, even though it is not mandatory.</span></span> <span data-ttu-id="d1afa-118">ポートのバインド ファイルをこのようにする場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部にもバインドのプロパティで指定する値が含まれているが生成されます。</span><span class="sxs-lookup"><span data-stu-id="d1afa-118">If you do so, the port binding file that the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] generates as part of the metadata generation also contains the values you specify for the binding properties.</span></span> <span data-ttu-id="d1afa-119">後でこのバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロパティは既に設定されています。 バインドで wcf-custom または WCF SQL を作成する管理コンソールの受信ポート。</span><span class="sxs-lookup"><span data-stu-id="d1afa-119">You can later import this binding file in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create the WCF-custom or WCF-SQL receive port with the binding properties already set.</span></span> <span data-ttu-id="d1afa-120">バインド ファイルを使用してポートを作成する方法の詳細については、[SQL アダプターを使用するポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1afa-120">For more information about creating a port using the binding file, see [Configure a physical port binding using a port binding file to use the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).</span></span>  
  
|<span data-ttu-id="d1afa-121">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="d1afa-121">Binding Property</span></span>|<span data-ttu-id="d1afa-122">説明</span><span class="sxs-lookup"><span data-stu-id="d1afa-122">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="d1afa-123">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="d1afa-123">**InboundOperationType**</span></span>|<span data-ttu-id="d1afa-124">実行する受信操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-124">Specifies the inbound operation that you want to perform.</span></span> <span data-ttu-id="d1afa-125">通知メッセージを受信するこれを設定**通知**します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-125">To receive notification messages, set this to **Notification**.</span></span>|  
|<span data-ttu-id="d1afa-126">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="d1afa-126">**NotificationStatement**</span></span>|<span data-ttu-id="d1afa-127">SQL ステートメントを指定します (SELECT または EXEC\<ストアド プロシージャ\>) のクエリ通知を登録するために使用します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-127">Specifies the SQL statement (SELECT or EXEC \<stored procedure\>) used to register for query notifications.</span></span> <span data-ttu-id="d1afa-128">アダプターは、指定された SQL ステートメントの変更の結果セットの場合にのみ、SQL Server から通知メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-128">The adapter gets a notification message from SQL Server only when the result set for the specified SQL statement changes.</span></span>|  
|<span data-ttu-id="d1afa-129">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="d1afa-129">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="d1afa-130">リスナーが開始されると、アダプターがアダプター クライアントに通知を送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-130">Specifies whether the adapter sends a notification to the adapter clients when the listener is started.</span></span>|  
  
 <span data-ttu-id="d1afa-131">これらのプロパティの詳細については、[for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1afa-131">For a more complete description of these properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="d1afa-132">使用する方法の詳細については、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server からの通知を受信するさらに読み進める。</span><span class="sxs-lookup"><span data-stu-id="d1afa-132">For a complete description of how to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive notifications from SQL Server, read further.</span></span>  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages"></a><span data-ttu-id="d1afa-133">このトピックで通知メッセージの受信について説明する方法</span><span class="sxs-lookup"><span data-stu-id="d1afa-133">How This Topic Demonstrates Receiving Notification Messages</span></span>  
 <span data-ttu-id="d1afa-134">示すためにどのように[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]SQL Server からの通知メッセージの受信をサポートするには、このトピックでは、Employee テーブルへの変更の通知を受信するアダプターを構成する方法を示しますが。</span><span class="sxs-lookup"><span data-stu-id="d1afa-134">To demonstrate how the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports receiving notification messages from SQL Server, this topic will demonstrate how to configure the adapter to receive notifications for changes to an Employee table.</span></span> <span data-ttu-id="d1afa-135">Employee テーブルの列 Employee_ID、名、および状態であると仮定します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-135">Assume that the Employee table has columns Employee_ID, Name, and Status.</span></span> <span data-ttu-id="d1afa-136">新しい従業員が追加されたときに、[状態] 列の値が 0 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d1afa-136">Whenever a new employee is added, the value of the Status column is set to 0.</span></span>  
  
 <span data-ttu-id="d1afa-137">通知の受信を示すためには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d1afa-137">To demonstrate receiving notifications, do the following:</span></span>  
  
-   <span data-ttu-id="d1afa-138">スキーマを生成、**通知**(入力方向の操作)、および**選択**(送信操作) Employee テーブルにします。</span><span class="sxs-lookup"><span data-stu-id="d1afa-138">Generate schema for the **Notification** (inbound operation), and **Select** (outbound operation) on the Employee table.</span></span>  
  
-   <span data-ttu-id="d1afa-139">次を含むオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-139">Create an orchestration that has the following:</span></span>  
  
    -   <span data-ttu-id="d1afa-140">通知メッセージを受信する受信場所。</span><span class="sxs-lookup"><span data-stu-id="d1afa-140">A receive location to receive notification messages.</span></span> <span data-ttu-id="d1afa-141">として、SELECT ステートメントを指定することで、通知を構成できます。</span><span class="sxs-lookup"><span data-stu-id="d1afa-141">You can configure for notification by specifying the SELECT statement as:</span></span>  
  
        ```  
        SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="d1afa-142">具体的には、これで示すように、ステートメント内の列名の SELECT ステートメントを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1afa-142">You must specifically specify the column names in the statement as shown in this SELECT statement.</span></span> <span data-ttu-id="d1afa-143">また、スキーマ名とテーブル名を必ず指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1afa-143">Also, you must always specify the table name along with the schema name.</span></span> <span data-ttu-id="d1afa-144">たとえば、 `dbo.Employee`のようにします。</span><span class="sxs-lookup"><span data-stu-id="d1afa-144">For example, `dbo.Employee`.</span></span>  
  
    -   <span data-ttu-id="d1afa-145">通知が送信されて既に行を更新する送信ポートです。</span><span class="sxs-lookup"><span data-stu-id="d1afa-145">A send port to update the rows for which notification has already been sent.</span></span> <span data-ttu-id="d1afa-146">これを 1 に、[状態] 列の値を設定して行います。</span><span class="sxs-lookup"><span data-stu-id="d1afa-146">You do so by setting the value in the Status column to 1.</span></span> <span data-ttu-id="d1afa-147">アダプターに次のメッセージを送信することによって、選択操作の一部として、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d1afa-147">You can do this as part of the Select operation by sending the following message to the adapter.</span></span>  
  
        ```  
        <Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
          <Columns>Employee_ID,Name,Status</Columns>  
          <Query>where Status=0;UPDATE Employee SET Status=1 WHERE Status=0</Query>  
        </Select>  
        ```  
  
         <span data-ttu-id="d1afa-148">一部としてこのメッセージで、`<Query>`要素では、[状態] 列を更新する UPDATE ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-148">In this message, as part of the `<Query>` element, you specify the UPDATE statement to update the Status column.</span></span> <span data-ttu-id="d1afa-149">この操作は、処理された行が更新されるようにメッセージ通知の受信後に実行する必要がありますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d1afa-149">Note that this operation must be executed after receiving the notification messages so that the processed rows are updated.</span></span> <span data-ttu-id="d1afa-150">通知応答を待機していると、行を更新する要求メッセージを手動で削除のオーバーヘッドがすぐには、オーケストレーション自体内の行を更新するための要求メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="d1afa-150">To do away with the overhead of waiting to get the notification response and then manually dropping a request message to update the rows, you will generate the request message for updating the rows within the orchestration itself.</span></span> <span data-ttu-id="d1afa-151">使用して行うことができます、**メッセージの構築**図形をオーケストレーション内。</span><span class="sxs-lookup"><span data-stu-id="d1afa-151">You can do so by using the **Construct Message** shape within an orchestration.</span></span>  
  
## <a name="how-to-receive-notification-messages-from-the-sql-server-database"></a><span data-ttu-id="d1afa-152">SQL Server データベースから通知メッセージを受信する方法</span><span class="sxs-lookup"><span data-stu-id="d1afa-152">How to Receive Notification Messages from the SQL Server Database</span></span>  
 <span data-ttu-id="d1afa-153">SQL Server データベースを使用して、操作を実行[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-153">Performing an operation on the SQL Server database using [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves the procedural tasks described in [Building blocks to develop BizTalk applications with the SQL adapter](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md).</span></span> <span data-ttu-id="d1afa-154">これらのタスクは通知メッセージを受信するアダプターを構成するには。</span><span class="sxs-lookup"><span data-stu-id="d1afa-154">To configure the adapter to receive notification messages, these tasks are:</span></span>  
  
1. <span data-ttu-id="d1afa-155">BizTalk プロジェクトを作成しのスキーマを生成し、**通知**(入力方向の操作) と**選択**(送信操作) Employee テーブルにします。</span><span class="sxs-lookup"><span data-stu-id="d1afa-155">Create a BizTalk project, and then generate schema for the **Notification** (inbound operation) and **Select** (outbound operation) on the Employee table.</span></span> <span data-ttu-id="d1afa-156">値を指定する、必要に応じて、 **InboundOperationType**と**NotificationStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="d1afa-156">Optionally, you can specify values for the **InboundOperationType** and **NotificationStatement** binding properties.</span></span>  
  
2. <span data-ttu-id="d1afa-157">SQL Server データベースから通知を受信するための BizTalk プロジェクトでは、メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-157">Create a message in the BizTalk project for receiving notification from the SQL Server database.</span></span>  
  
3. <span data-ttu-id="d1afa-158">SQL Server データベースの選択についてを実行して、応答メッセージの受信用の BizTalk プロジェクトでは、メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-158">Create messages in the BizTalk project for performing the Select information on the SQL Server database and receiving response messages.</span></span>  
  
4. <span data-ttu-id="d1afa-159">次のオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-159">Create an orchestration that does the following:</span></span>  
  
   -   <span data-ttu-id="d1afa-160">SQL Server から通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-160">Receives notification message from SQL Server.</span></span>  
  
   -   <span data-ttu-id="d1afa-161">選択し、通知を受信した行を更新するメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-161">Creates a message to select and update the rows for which notification is received.</span></span>  
  
   -   <span data-ttu-id="d1afa-162">行を更新する SQL Server にこのメッセージを送信し、応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-162">Sends this message to the SQL Server to update the rows and receives a response.</span></span>  
  
5. <span data-ttu-id="d1afa-163">ビルドし、BizTalk プロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-163">Build and deploy the BizTalk project.</span></span>  
  
6. <span data-ttu-id="d1afa-164">BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-164">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d1afa-165">受信操作の場合、通知メッセージを受信するように Wcf-custom の一方向のみを構成する必要があります。 または WCF SQL 受信ポート。</span><span class="sxs-lookup"><span data-stu-id="d1afa-165">For inbound operations, like receiving notification messages, you must only configure a one-way WCF-Custom or WCF-SQL receive port.</span></span> <span data-ttu-id="d1afa-166">Wcf-custom または WCF-SQL の双方向受信ポートの受信操作はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d1afa-166">Two-way WCF-Custom or WCF-SQL receive ports are not supported for inbound operations.</span></span>  
  
7. <span data-ttu-id="d1afa-167">BizTalk アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-167">Start the BizTalk application.</span></span>  
  
   <span data-ttu-id="d1afa-168">このトピックでは、これらのタスクを実行する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-168">This topic provides instructions to perform these tasks.</span></span>  
  
## <a name="sample-based-on-this-topic"></a><span data-ttu-id="d1afa-169">このトピックに基づくサンプル</span><span class="sxs-lookup"><span data-stu-id="d1afa-169">Sample Based on This Topic</span></span>  
 <span data-ttu-id="d1afa-170">サンプル IncrementalNotification、このトピックの「に基づいてが付属、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-170">A sample, IncrementalNotification, based on this topic is provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="d1afa-171">詳細については、[SQL アダプタのサンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1afa-171">For more information, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span>  
  
## <a name="generating-schema"></a><span data-ttu-id="d1afa-172">スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-172">Generating Schema</span></span>  
 <span data-ttu-id="d1afa-173">スキーマを生成する必要があります、**通知**操作と**選択**従業員テーブルに対する操作。</span><span class="sxs-lookup"><span data-stu-id="d1afa-173">You must generate the schema for the **Notification** operation and **Select** operation on Employee table.</span></span> <span data-ttu-id="d1afa-174">参照してください[SQL アダプタを使用して Visual Studio で SQL Server 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)スキーマを生成する方法の詳細について。</span><span class="sxs-lookup"><span data-stu-id="d1afa-174">See [Get metadata for SQL Server operations in Visual Studio using the SQL adapter](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md) for more information about how to generate the schema.</span></span> <span data-ttu-id="d1afa-175">スキーマを生成するときに、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-175">Perform the following tasks when generating the schema.</span></span> <span data-ttu-id="d1afa-176">デザイン時のバインドのプロパティを指定しない場合は、最初の手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="d1afa-176">Skip the first step if you do not want to specify the binding properties at design time.</span></span>  
  
1.  <span data-ttu-id="d1afa-177">値を指定**InboundOperationType**と**NotificationStatement**スキーマの生成中にプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="d1afa-177">Specify a value for **InboundOperationType** and **NotificationStatement** binding properties while generating the schema.</span></span> <span data-ttu-id="d1afa-178">このバインドのプロパティの詳細については、[for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1afa-178">For more information about this binding property, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="d1afa-179">バインドのプロパティを指定する方法については、[SQL アダプタのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1afa-179">For instructions on how to specify binding properties, see [Configure the binding properties for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).</span></span>  
  
2.  <span data-ttu-id="d1afa-180">コントラクトの種類を選択します。**サービス (受信操作)** します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-180">Select the contract type as **Service (Inbound operations)**.</span></span>  
  
3.  <span data-ttu-id="d1afa-181">スキーマの生成、**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="d1afa-181">Generate schema for the **Notification** operation.</span></span>  
  
4.  <span data-ttu-id="d1afa-182">コントラクトの種類を選択します。**クライアント (送信操作)** します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-182">Select the contract type as **Client (Outbound operations)**.</span></span>  
  
5.  <span data-ttu-id="d1afa-183">スキーマの生成、**選択**操作**従業員**テーブル。</span><span class="sxs-lookup"><span data-stu-id="d1afa-183">Generate schema for the **Select** operation on **Employee** table.</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="d1afa-184">メッセージおよびメッセージの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-184">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="d1afa-185">以前に生成したスキーマには、オーケストレーション内のメッセージに必要な「型」について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-185">The schema that you generated earlier describes the "types" required for the messages in the orchestration.</span></span> <span data-ttu-id="d1afa-186">メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。</span><span class="sxs-lookup"><span data-stu-id="d1afa-186">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="d1afa-187">スキーマが生成されるは、BizTalk プロジェクトのオーケストレーションからメッセージをリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1afa-187">Once the schema is generated, you must link it to the messages from the Orchestration view of the BizTalk project.</span></span>  
  
 <span data-ttu-id="d1afa-188">このトピックでは、3 つのメッセージを作成する必要があります: SQL Server データベースや選択の操作を実行する 1 つの Select 操作の応答を受信する 1 つから通知を受信する 1 つ。</span><span class="sxs-lookup"><span data-stu-id="d1afa-188">For this topic, you must create three messages—one to receive notifications from the SQL Server database, one to perform the Select operation, and one to receive the response for Select operation.</span></span>  
  
 <span data-ttu-id="d1afa-189">メッセージを作成し、スキーマにリンクするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-189">Perform the following steps to create messages and link them to schema.</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="d1afa-190">メッセージを作成し、スキーマにリンクするには</span><span class="sxs-lookup"><span data-stu-id="d1afa-190">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="d1afa-191">オーケストレーションを BizTalk プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-191">Add an orchestration to the BizTalk project.</span></span> <span data-ttu-id="d1afa-192">ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックして**追加**、 をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-192">From the Solution Explorer, right-click the BizTalk project name, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="d1afa-193">BizTalk オーケストレーションの名前を入力し、クリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-193">Type a name for the BizTalk orchestration and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="d1afa-194">開いていない場合は、BizTalk プロジェクトのオーケストレーション ビュー ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="d1afa-194">Open the orchestration view window of the BizTalk project, if it is not already open.</span></span> <span data-ttu-id="d1afa-195">をクリックして**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-195">Click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
3.  <span data-ttu-id="d1afa-196">**オーケストレーション**、右クリック**メッセージ**、順にクリックします**新しいメッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-196">In the **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span>  
  
4.  <span data-ttu-id="d1afa-197">新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-197">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="d1afa-198">**プロパティ**ウィンドウ **[message_1]** 次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d1afa-198">In the **Properties** pane for **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="d1afa-199">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d1afa-199">Use this</span></span>|<span data-ttu-id="d1afa-200">目的</span><span class="sxs-lookup"><span data-stu-id="d1afa-200">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d1afa-201">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="d1afa-201">Identifier</span></span>|<span data-ttu-id="d1afa-202">「`NotifyReceive`.</span><span class="sxs-lookup"><span data-stu-id="d1afa-202">Type `NotifyReceive`.</span></span>|  
    |<span data-ttu-id="d1afa-203">メッセージ型</span><span class="sxs-lookup"><span data-stu-id="d1afa-203">Message Type</span></span>|<span data-ttu-id="d1afa-204">ドロップダウン リストから展開**スキーマ**、選択と*SQLNotify.Notification*ここで、 *SQLNotify* BizTalk プロジェクトの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-204">From the drop-down list, expand **Schemas**, and select *SQLNotify.Notification*, where *SQLNotify* is the name of your BizTalk project.</span></span> <span data-ttu-id="d1afa-205">*通知*に対して生成されたスキーマには、**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="d1afa-205">*Notification* is the schema generated for the **Notification** operation.</span></span>|  
  
6.  <span data-ttu-id="d1afa-206">手順 3 を 2 つの新しいメッセージを作成する.</span><span class="sxs-lookup"><span data-stu-id="d1afa-206">Repeat step 3 to create two new messages.</span></span> <span data-ttu-id="d1afa-207">**プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-207">In the **Properties** pane for the new message, do the following:</span></span>  
  
    |<span data-ttu-id="d1afa-208">識別子を設定するには</span><span class="sxs-lookup"><span data-stu-id="d1afa-208">Set Identifier to</span></span>|<span data-ttu-id="d1afa-209">メッセージの種類を設定</span><span class="sxs-lookup"><span data-stu-id="d1afa-209">Set Message Type to</span></span>|  
    |-----------------------|-------------------------|  
    |<span data-ttu-id="d1afa-210">Select</span><span class="sxs-lookup"><span data-stu-id="d1afa-210">Select</span></span>|<span data-ttu-id="d1afa-211">*SQLNotify.TableOperation_dbo_Employee.Select*ここで、 *TableOperation_dbo_Employee*に対して生成されたスキーマには、**選択**操作</span><span class="sxs-lookup"><span data-stu-id="d1afa-211">*SQLNotify.TableOperation_dbo_Employee.Select*, where  *TableOperation_dbo_Employee* is the schema generated for the **Select** operation</span></span>|  
    |<span data-ttu-id="d1afa-212">SelectResponse</span><span class="sxs-lookup"><span data-stu-id="d1afa-212">SelectResponse</span></span>|<span data-ttu-id="d1afa-213">*SQLNotify.TableOperation_dbo_Employee.SelectResponse*</span><span class="sxs-lookup"><span data-stu-id="d1afa-213">*SQLNotify.TableOperation_dbo_Employee.SelectResponse*</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="d1afa-214">オーケストレーションのセットアップ</span><span class="sxs-lookup"><span data-stu-id="d1afa-214">Setting up the Orchestration</span></span>  
 <span data-ttu-id="d1afa-215">使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の SQL Server データベースから通知メッセージを受信し、通知を受信した行を更新します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-215">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for receiving notification messages from the SQL Server database and then updating the rows for which notification was received.</span></span> <span data-ttu-id="d1afa-216">このオーケストレーションでの指定した SELECT ステートメントに基づいて、通知メッセージを受信、 **NotificationStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="d1afa-216">In this orchestration, the adapter receives the notification message based on the SELECT statement specified for the **NotificationStatement** binding property.</span></span> <span data-ttu-id="d1afa-217">通知メッセージは、ファイルの場所で受信されます。</span><span class="sxs-lookup"><span data-stu-id="d1afa-217">The notification message is received at a FILE location.</span></span> <span data-ttu-id="d1afa-218">応答が受信されると、オーケストレーションは、通知を受信した行を更新するために使用するメッセージを構築します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-218">Once the response is received, the orchestration constructs a message that will be used to update the rows for which notification is received.</span></span> <span data-ttu-id="d1afa-219">このメッセージの応答を同じファイルの場所で受信もします。</span><span class="sxs-lookup"><span data-stu-id="d1afa-219">The response for this message is also received at the same FILE location.</span></span>  
  
 <span data-ttu-id="d1afa-220">そのため、オーケストレーションは、次に含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1afa-220">So, your orchestration must contain the following:</span></span>  
  
- <span data-ttu-id="d1afa-221">一方向の受信の通知メッセージを受信するポート。</span><span class="sxs-lookup"><span data-stu-id="d1afa-221">A one-way receive port to receive notification messages.</span></span>  
  
- <span data-ttu-id="d1afa-222">双方向の送信ポートの行を更新し、同じ応答を受信するメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-222">A two-way send port to send messages to update rows and receive response for the same.</span></span>  
  
- <span data-ttu-id="d1afa-223">A**メッセージの構築**図形をオーケストレーション内で、更新操作を実行する、メッセージを構築します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-223">A **Construct Message** shape to construct messages, to execute the Update operation, within the orchestration.</span></span>  
  
- <span data-ttu-id="d1afa-224">ファイルは、更新操作の応答を保存するポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-224">A FILE send port to save the response for the Update operation.</span></span>  
  
- <span data-ttu-id="d1afa-225">受信図形と送信図形。</span><span class="sxs-lookup"><span data-stu-id="d1afa-225">Receive and send shapes.</span></span>  
  
  <span data-ttu-id="d1afa-226">サンプル オーケストレーションでは、次の項目に似ています。</span><span class="sxs-lookup"><span data-stu-id="d1afa-226">A sample orchestration resembles the following.</span></span>  
  
  <span data-ttu-id="d1afa-227">![SQL Server 通知を受信するオーケストレーション](../../adapters-and-accelerators/adapter-sql/media/f13ad3b8-8161-42e5-a521-424bbf549ad5.gif "f13ad3b8-8161-42e5-a521-424bbf549ad5")</span><span class="sxs-lookup"><span data-stu-id="d1afa-227">![Orchestration to receive SQL Server notifications](../../adapters-and-accelerators/adapter-sql/media/f13ad3b8-8161-42e5-a521-424bbf549ad5.gif "f13ad3b8-8161-42e5-a521-424bbf549ad5")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="d1afa-228">メッセージの構築図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-228">Adding Message Shapes</span></span>  
 <span data-ttu-id="d1afa-229">メッセージの構築図形のごとに、次のプロパティを指定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-229">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="d1afa-230">図形の列に示した名前は、単に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。</span><span class="sxs-lookup"><span data-stu-id="d1afa-230">The names listed in the Shape column are the names of the message shapes as displayed in the just-mentioned orchestration.</span></span>  
  
|<span data-ttu-id="d1afa-231">図形</span><span class="sxs-lookup"><span data-stu-id="d1afa-231">Shape</span></span>|<span data-ttu-id="d1afa-232">図形の種類</span><span class="sxs-lookup"><span data-stu-id="d1afa-232">Shape Type</span></span>|<span data-ttu-id="d1afa-233">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="d1afa-233">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="d1afa-234">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="d1afa-234">ReceiveNotification</span></span>|<span data-ttu-id="d1afa-235">Receive</span><span class="sxs-lookup"><span data-stu-id="d1afa-235">Receive</span></span>|<span data-ttu-id="d1afa-236">-設定**名前**に*ReceiveNotification*</span><span class="sxs-lookup"><span data-stu-id="d1afa-236">- Set **Name** to *ReceiveNotification*</span></span><br /><br /> <span data-ttu-id="d1afa-237">-設定**アクティブ**に*は True。*</span><span class="sxs-lookup"><span data-stu-id="d1afa-237">- Set **Activate** to *True*</span></span>|  
|<span data-ttu-id="d1afa-238">SaveNotification</span><span class="sxs-lookup"><span data-stu-id="d1afa-238">SaveNotification</span></span>|<span data-ttu-id="d1afa-239">Send</span><span class="sxs-lookup"><span data-stu-id="d1afa-239">Send</span></span>|<span data-ttu-id="d1afa-240">-設定**名前**に*SaveNotification*</span><span class="sxs-lookup"><span data-stu-id="d1afa-240">- Set **Name** to *SaveNotification*</span></span>|  
|<span data-ttu-id="d1afa-241">SendSelectMessage</span><span class="sxs-lookup"><span data-stu-id="d1afa-241">SendSelectMessage</span></span>|<span data-ttu-id="d1afa-242">Send</span><span class="sxs-lookup"><span data-stu-id="d1afa-242">Send</span></span>|<span data-ttu-id="d1afa-243">-設定**名前**に*SendSelectMessage*</span><span class="sxs-lookup"><span data-stu-id="d1afa-243">- Set **Name** to *SendSelectMessage*</span></span>|  
|<span data-ttu-id="d1afa-244">ReceiveSelectResponse</span><span class="sxs-lookup"><span data-stu-id="d1afa-244">ReceiveSelectResponse</span></span>|<span data-ttu-id="d1afa-245">Receive</span><span class="sxs-lookup"><span data-stu-id="d1afa-245">Receive</span></span>|<span data-ttu-id="d1afa-246">-設定**名前**に*ReceiveSelectResponse*</span><span class="sxs-lookup"><span data-stu-id="d1afa-246">- Set **Name** to *ReceiveSelectResponse*</span></span>|  
|<span data-ttu-id="d1afa-247">SaveSelectResponse</span><span class="sxs-lookup"><span data-stu-id="d1afa-247">SaveSelectResponse</span></span>|<span data-ttu-id="d1afa-248">Send</span><span class="sxs-lookup"><span data-stu-id="d1afa-248">Send</span></span>|<span data-ttu-id="d1afa-249">-設定**名前**に*SaveSelectResponse*</span><span class="sxs-lookup"><span data-stu-id="d1afa-249">- Set **Name** to *SaveSelectResponse*</span></span>|  
  
### <a name="adding-construct-message-shape"></a><span data-ttu-id="d1afa-250">メッセージの構築図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-250">Adding Construct Message Shape</span></span>  
 <span data-ttu-id="d1afa-251">使用することができます、**メッセージの構築**図形を選択操作を実行する操作に含まれる要求メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-251">You can use the **Construct Message** shape to generate a request message within the operation to perform the Select operation.</span></span> <span data-ttu-id="d1afa-252">これを行うには、追加する必要があります、**メッセージの構築**図形し、その中を**メッセージの割り当て**図形をオーケストレーションにします。</span><span class="sxs-lookup"><span data-stu-id="d1afa-252">To do so, you must add a **Construct Message** shape and within that a **Message Assignment** shape to your orchestration.</span></span> <span data-ttu-id="d1afa-253">この例で、**メッセージの割り当て**図形が選択操作を実行する SQL Server に送信されるメッセージを生成するコードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-253">For this example, the **Message Assignment** shape invokes code that generates a message that is sent to SQL Server to perform the Select operation.</span></span> <span data-ttu-id="d1afa-254">**メッセージの割り当て**図形も、SQL Server に送信するメッセージに対するアクションを設定します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-254">The **Message Assignment** shape also sets the action for the message to be sent to SQL Server.</span></span>  
  
 <span data-ttu-id="d1afa-255">メッセージの構築図形で、設定、**メッセージ構築**プロパティを**選択**します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-255">For the construct message shape, set the **Message Constructed** property to **Select**.</span></span>  
  
 <span data-ttu-id="d1afa-256">応答を生成するコードは、BizTalk プロジェクトと同じ Visual Studio ソリューションの一部になります。</span><span class="sxs-lookup"><span data-stu-id="d1afa-256">The code to generate the response could be part of the same Visual Studio solution as your BizTalk project.</span></span> <span data-ttu-id="d1afa-257">応答メッセージを生成するためのサンプル コードは、次のように検索します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-257">A sample code for generating a response message looks like this.</span></span>  
  
```  
namespace SampleMessageCreator  
{  
    public class SampleMessageCreator  
    {  
        private static XmlDocument Message;  
        private static string XmlFileLocation;  
        private static string ResponseDoc;  
        public static XmlDocument XMLMessageCreator()  
        {  
            XmlFileLocation = "C:\\TestLocation\\CreateMessage";  
            try  
            {  
                ResponseDoc = (Directory.GetFiles(XmlFileLocation, "*.xml", SearchOption.TopDirectoryOnly))[0];  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Trying to get XML from: " + XmlFileLocation);  
                Console.WriteLine("EXCEPTION: " + ex.ToString());  
                throw ex;  
            }  
            //Create Message From XML  
            Message = new XmlDocument();  
            Message.PreserveWhitespace = true;  
            Message.Load(ResponseDoc);  
            return Message;  
        }   
    }  
}  
```  
  
 <span data-ttu-id="d1afa-258">要求メッセージを生成できるように上記のコードの抜粋、する必要があります (Employee テーブルの選択の操作) の XML 要求メッセージに指定された場所で、`XmlFileLocation`変数。</span><span class="sxs-lookup"><span data-stu-id="d1afa-258">For the preceding code excerpt to be able to generate a request message, you must have an XML request message (for the Select operation on the Employee table) in the location specified for the `XmlFileLocation` variable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1afa-259">プロジェクトをビルドした後に SampleMessageCreator.dll がプロジェクト ディレクトリに作成されます。</span><span class="sxs-lookup"><span data-stu-id="d1afa-259">After you build the project, SampleMessageCreator.dll will be created in the project directory.</span></span> <span data-ttu-id="d1afa-260">この DLL は、グローバル アセンブリ キャッシュ (GAC) に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1afa-260">You must add this DLL to the global assembly cache (GAC).</span></span> <span data-ttu-id="d1afa-261">また、BizTalk プロジェクトに参照として、SampleMessageCreator.dll を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1afa-261">Also, you must add the SampleMessageCreator.dll as a reference in the BizTalk project.</span></span>  
  
 <span data-ttu-id="d1afa-262">次のコードを呼び出すには、次の式を追加、**メッセージの割り当て**図形とメッセージのアクションを設定します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-262">Add the following expression to invoke this code from the **Message Assignment** shape and to set the action for message.</span></span> <span data-ttu-id="d1afa-263">式を追加するには、ダブルクリック、**メッセージの割り当て**図形式エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="d1afa-263">To add an expression, double-click the **Message Assignment** shape to open the Expression Editor.</span></span>  
  
```  
Select = SampleMessageCreator.SampleMessageCreator.XMLMessageCreator();  
Select(WCF.Action) = "TableOp/Select/dbo/Employee";  
```  
  
### <a name="adding-ports"></a><span data-ttu-id="d1afa-264">ポートの追加</span><span class="sxs-lookup"><span data-stu-id="d1afa-264">Adding Ports</span></span>  
 <span data-ttu-id="d1afa-265">論理ポートごとに、次のプロパティを指定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-265">Make sure you specify the following properties for each of the logical ports.</span></span> <span data-ttu-id="d1afa-266">ポート列に示した名前は、オーケストレーションで表示されているポートの名前です。</span><span class="sxs-lookup"><span data-stu-id="d1afa-266">The names listed in the Port column are the names of the ports as displayed in the orchestration.</span></span>  
  
|<span data-ttu-id="d1afa-267">Port</span><span class="sxs-lookup"><span data-stu-id="d1afa-267">Port</span></span>|<span data-ttu-id="d1afa-268">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="d1afa-268">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="d1afa-269">SQLNotifyPort</span><span class="sxs-lookup"><span data-stu-id="d1afa-269">SQLNotifyPort</span></span>|<span data-ttu-id="d1afa-270">-設定**識別子**に*SQLNotifyPort*</span><span class="sxs-lookup"><span data-stu-id="d1afa-270">- Set **Identifier** to *SQLNotifyPort*</span></span><br /><br /> <span data-ttu-id="d1afa-271">-設定**型**に*SQLNotifyPortType*</span><span class="sxs-lookup"><span data-stu-id="d1afa-271">- Set **Type** to *SQLNotifyPortType*</span></span><br /><br /> <span data-ttu-id="d1afa-272">-設定**通信パターン**に*一方向*</span><span class="sxs-lookup"><span data-stu-id="d1afa-272">- Set **Communication Pattern** to *One-Way*</span></span><br /><br /> <span data-ttu-id="d1afa-273">-設定**通信方向**に*受信*</span><span class="sxs-lookup"><span data-stu-id="d1afa-273">- Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="d1afa-274">SaveMessagePort</span><span class="sxs-lookup"><span data-stu-id="d1afa-274">SaveMessagePort</span></span>|<span data-ttu-id="d1afa-275">-設定**識別子**に*SaveMessagePort*</span><span class="sxs-lookup"><span data-stu-id="d1afa-275">- Set **Identifier** to *SaveMessagePort*</span></span><br /><br /> <span data-ttu-id="d1afa-276">-設定**型**に*SaveMessagePortType*</span><span class="sxs-lookup"><span data-stu-id="d1afa-276">- Set **Type** to *SaveMessagePortType*</span></span><br /><br /> <span data-ttu-id="d1afa-277">-設定**通信パターン**に*一方向*</span><span class="sxs-lookup"><span data-stu-id="d1afa-277">- Set **Communication Pattern** to *One-Way*</span></span><br /><br /> <span data-ttu-id="d1afa-278">-設定**通信方向**に*送信*</span><span class="sxs-lookup"><span data-stu-id="d1afa-278">- Set **Communication Direction** to *Send*</span></span><br /><br /> <span data-ttu-id="d1afa-279">-作成操作*通知*します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-279">- Create an operation *Notify*.</span></span> <span data-ttu-id="d1afa-280">この操作は、通知メッセージに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1afa-280">This operation is used for notification messages.</span></span><br /><br /> <span data-ttu-id="d1afa-281">-作成操作*選択*します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-281">- Create an operation *Select*.</span></span> <span data-ttu-id="d1afa-282">この操作は、応答メッセージに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1afa-282">This operation is used for select response messages.</span></span>|  
|<span data-ttu-id="d1afa-283">SQLOutboundPort</span><span class="sxs-lookup"><span data-stu-id="d1afa-283">SQLOutboundPort</span></span>|<span data-ttu-id="d1afa-284">-設定**識別子**に*SQLOutboundPort*</span><span class="sxs-lookup"><span data-stu-id="d1afa-284">- Set **Identifier** to *SQLOutboundPort*</span></span><br /><br /> <span data-ttu-id="d1afa-285">-設定**型**に*SQLOutboundPortType*</span><span class="sxs-lookup"><span data-stu-id="d1afa-285">- Set **Type** to *SQLOutboundPortType*</span></span><br /><br /> <span data-ttu-id="d1afa-286">-設定**通信パターン**に*要求-応答*</span><span class="sxs-lookup"><span data-stu-id="d1afa-286">- Set **Communication Pattern** to *Request-Response*</span></span><br /><br /> <span data-ttu-id="d1afa-287">-設定**通信方向**に*送受信*</span><span class="sxs-lookup"><span data-stu-id="d1afa-287">- Set **Communication Direction** to *Send-Receive*</span></span>|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a><span data-ttu-id="d1afa-288">アクション図形のメッセージを指定し、ポートに接続</span><span class="sxs-lookup"><span data-stu-id="d1afa-288">Specify Messages for Action Shapes and Connect to Ports</span></span>  
 <span data-ttu-id="d1afa-289">次の表では、プロパティとアクション図形のメッセージを指定して、メッセージ ポートにリンクを設定する必要があります、値を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-289">The following table specifies the properties and their values that you should set to specify messages for action shapes and to link the messages to the ports.</span></span> <span data-ttu-id="d1afa-290">図形の列に示した名前は、前に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。</span><span class="sxs-lookup"><span data-stu-id="d1afa-290">The names listed in the Shape column are the names of the message shapes as displayed in the orchestration mentioned earlier.</span></span>  
  
|<span data-ttu-id="d1afa-291">図形</span><span class="sxs-lookup"><span data-stu-id="d1afa-291">Shape</span></span>|<span data-ttu-id="d1afa-292">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="d1afa-292">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="d1afa-293">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="d1afa-293">ReceiveNotification</span></span>|<span data-ttu-id="d1afa-294">-設定**メッセージ**に*NotifyReceive*</span><span class="sxs-lookup"><span data-stu-id="d1afa-294">- Set **Message** to *NotifyReceive*</span></span><br /><br /> <span data-ttu-id="d1afa-295">-設定**操作**に*SQLNotifyPort.Notify.Request*</span><span class="sxs-lookup"><span data-stu-id="d1afa-295">- Set **Operation** to *SQLNotifyPort.Notify.Request*</span></span>|  
|<span data-ttu-id="d1afa-296">SaveNotification</span><span class="sxs-lookup"><span data-stu-id="d1afa-296">SaveNotification</span></span>|<span data-ttu-id="d1afa-297">-設定**メッセージ**に*NotifyReceive*</span><span class="sxs-lookup"><span data-stu-id="d1afa-297">- Set **Message** to *NotifyReceive*</span></span><br /><br /> <span data-ttu-id="d1afa-298">-設定**操作**に*SaveMessagePort.Notify.Request*</span><span class="sxs-lookup"><span data-stu-id="d1afa-298">- Set **Operation** to *SaveMessagePort.Notify.Request*</span></span>|  
|<span data-ttu-id="d1afa-299">SendSelectMessage</span><span class="sxs-lookup"><span data-stu-id="d1afa-299">SendSelectMessage</span></span>|<span data-ttu-id="d1afa-300">-設定**メッセージ**に*を選択します*</span><span class="sxs-lookup"><span data-stu-id="d1afa-300">- Set **Message** to *Select*</span></span><br /><br /> <span data-ttu-id="d1afa-301">-設定**操作**に*SQLOutboundPort.Select.Request*</span><span class="sxs-lookup"><span data-stu-id="d1afa-301">- Set **Operation** to *SQLOutboundPort.Select.Request*</span></span>|  
|<span data-ttu-id="d1afa-302">ReceiveSelectResponse</span><span class="sxs-lookup"><span data-stu-id="d1afa-302">ReceiveSelectResponse</span></span>|<span data-ttu-id="d1afa-303">-設定**メッセージ**に*SelectResponse*</span><span class="sxs-lookup"><span data-stu-id="d1afa-303">- Set **Message** to *SelectResponse*</span></span><br /><br /> <span data-ttu-id="d1afa-304">-設定**操作**に*SQLOutboundPort.Select.Response*</span><span class="sxs-lookup"><span data-stu-id="d1afa-304">- Set **Operation** to *SQLOutboundPort.Select.Response*</span></span>|  
|<span data-ttu-id="d1afa-305">SaveSelectResponse</span><span class="sxs-lookup"><span data-stu-id="d1afa-305">SaveSelectResponse</span></span>|<span data-ttu-id="d1afa-306">-設定**メッセージ**に*SelectResponse*</span><span class="sxs-lookup"><span data-stu-id="d1afa-306">- Set **Message** to *SelectResponse*</span></span><br /><br /> <span data-ttu-id="d1afa-307">-設定**操作**に*SaveMessagePort.Select.Request*</span><span class="sxs-lookup"><span data-stu-id="d1afa-307">- Set **Operation** to *SaveMessagePort.Select.Request*</span></span>|  
  
 <span data-ttu-id="d1afa-308">これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-308">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="d1afa-309">ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-309">You must now build the BizTalk solution and deploy it to a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d1afa-310">詳細については、[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1afa-310">For more information, see [Building and Running Orchestrations](../../core/building-and-running-orchestrations.md).</span></span>
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="d1afa-311">BizTalk アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-311">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="d1afa-312">先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="d1afa-312">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the **Orchestrations** pane in the BizTalk Server Administration console.</span></span> <span data-ttu-id="d1afa-313">BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1afa-313">You must use the BizTalk Server Administration console to configure the application.</span></span> <span data-ttu-id="d1afa-314">チュートリアルについては、[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1afa-314">For a walkthrough, see [Walkthrough: Deploying a Basic BizTalk Application](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).</span></span>
  
 <span data-ttu-id="d1afa-315">アプリケーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1afa-315">Configuring an application involves:</span></span>  
  
- <span data-ttu-id="d1afa-316">アプリケーションのホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-316">Selecting a host for the application.</span></span>  
  
- <span data-ttu-id="d1afa-317">BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。</span><span class="sxs-lookup"><span data-stu-id="d1afa-317">Mapping the ports that you created in your orchestration to physical ports in the BizTalk Server Administration console.</span></span> <span data-ttu-id="d1afa-318">このオーケストレーションの次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1afa-318">For this orchestration you must:</span></span>  
  
  - <span data-ttu-id="d1afa-319">WCF-SQL の一方向受信ポートまたは物理 Wcf-custom を定義します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-319">Define a physical WCF-Custom or WCF-SQL one-way receive port.</span></span> <span data-ttu-id="d1afa-320">このポートは、SQL Server データベースから通知をリッスンします。</span><span class="sxs-lookup"><span data-stu-id="d1afa-320">This port listens for notifications coming from the SQL Server database.</span></span> <span data-ttu-id="d1afa-321">ポートを作成する方法については、[SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1afa-321">For information about how to create ports, see [Manually configure a physical port binding to the SQL adapter](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md).</span></span> <span data-ttu-id="d1afa-322">受信ポートのバインドのプロパティを指定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-322">Make sure you specify the following binding properties for the receive port.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d1afa-323">デザイン時のバインドのプロパティを指定した場合、この手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d1afa-323">You do not need to perform this step if you specified the binding properties at design time.</span></span> <span data-ttu-id="d1afa-324">このような場合は、WCF カスタムを作成または WCF-SQL によって作成されたバインド ファイルをインポートすることによって、必要なバインドのプロパティを設定すると、ポートを受信する、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-324">In such a case, you can create a WCF-custom or WCF-SQL receive port, with the required binding properties set, by importing the binding file created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span> <span data-ttu-id="d1afa-325">詳細については、[SQL アダプターを使用するポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1afa-325">For more information see [Configure a physical port binding using a port binding file to use the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).</span></span>  
  
    |<span data-ttu-id="d1afa-326">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="d1afa-326">Binding Property</span></span>|<span data-ttu-id="d1afa-327">値</span><span class="sxs-lookup"><span data-stu-id="d1afa-327">Value</span></span>|  
    |----------------------|-----------|  
    |<span data-ttu-id="d1afa-328">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="d1afa-328">**InboundOperationType**</span></span>|<span data-ttu-id="d1afa-329">これを設定**通知**します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-329">Set this to **Notification**.</span></span>|  
    |<span data-ttu-id="d1afa-330">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="d1afa-330">**NotificationStatement**</span></span>|<span data-ttu-id="d1afa-331">これを設定します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-331">Set this to:</span></span><br /><br /> `SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0`<br /><br /> <span data-ttu-id="d1afa-332">**注:** この SELECT ステートメントで示すように、ステートメントで列名に指定すること具体的にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1afa-332">**Note:** You must specifically specify the column names in the statement as shown in this SELECT statement.</span></span> <span data-ttu-id="d1afa-333">また、スキーマ名とテーブル名を必ず指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1afa-333">Also, you must always specify the table name along with the schema name.</span></span> <span data-ttu-id="d1afa-334">たとえば、 `dbo.Employee`のようにします。</span><span class="sxs-lookup"><span data-stu-id="d1afa-334">For example, `dbo.Employee`.</span></span>|  
    |<span data-ttu-id="d1afa-335">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="d1afa-335">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="d1afa-336">これを設定**True**します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-336">Set this to **True**.</span></span>|  
  
     <span data-ttu-id="d1afa-337">異なるバインディング プロパティの詳細については、[for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1afa-337">For more information about the different binding properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d1afa-338">使用して受信操作の実行中に、トランザクション分離レベルとトランザクションのタイムアウトを構成することをお勧めします。、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-338">We recommend configuring the transaction isolation level and the transaction timeout while performing inbound operations using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="d1afa-339">ように、サービスを追加することで、Wcf-custom または WCF SQL を構成するときに動作の受信ポートを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d1afa-339">You can do so by adding the service behavior while configuring the WCF-Custom or WCF-SQL receive port.</span></span> <span data-ttu-id="d1afa-340">サービスの動作を追加する方法については、[トランザクション分離レベルの構成と SQL を使用したトランザクション タイムアウト](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1afa-340">For instruction on how to add the service behavior, see [Configure Transaction Isolation Level and Transaction Timeout with SQL](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md).</span></span>  
  
  - <span data-ttu-id="d1afa-341">SQL Server データベースにメッセージを送信する物理 Wcf-custom または WCF-SQL 送信ポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-341">Define a physical WCF-Custom or WCF-SQL send port to send messages to the SQL Server database.</span></span> <span data-ttu-id="d1afa-342">送信ポートでアクションを指定することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1afa-342">You must also specify the action in the send port.</span></span>  
  
  - <span data-ttu-id="d1afa-343">ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーション、SQL Server データベースからメッセージをドロップできる場所での場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-343">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the messages from the SQL Server database.</span></span> <span data-ttu-id="d1afa-344">これらは、SQL Server から受信した通知メッセージとメッセージを選択し、Wcf-custom または WCF SQL を使用して実行する更新操作がポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-344">These will be the notification messages received from SQL Server and messages for the Select and Update operation you perform through the WCF-Custom or WCF-SQL send port.</span></span>  
  
## <a name="starting-the-application"></a><span data-ttu-id="d1afa-345">アプリケーションの起動</span><span class="sxs-lookup"><span data-stu-id="d1afa-345">Starting the Application</span></span>  
 <span data-ttu-id="d1afa-346">SQL Server データベースから通知メッセージを受信するため、後続の Select および Update 操作を実行するために、BizTalk アプリケーションを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1afa-346">You must start the BizTalk application for receiving notification messages from the SQL Server database and for performing the subsequent Select and Update operations.</span></span> <span data-ttu-id="d1afa-347">BizTalk アプリケーションを開始する手順については、[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1afa-347">For instructions on starting a BizTalk application, see [How to Start an Orchestration](../../core/how-to-start-an-orchestration.md).</span></span>
  
 <span data-ttu-id="d1afa-348">この段階で、ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-348">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="d1afa-349">Wcf-custom または WCF SQL 一方向の受信ポートで、データベースが実行されている SQL Server から通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-349">The WCF-Custom or WCF-SQL one-way receive port, which receives the notification messages from the SQL Server database is running.</span></span>  
  
-   <span data-ttu-id="d1afa-350">実行する Wcf-custom または WCF-SQL 送信ポートを選択し、Employee テーブルの更新操作が実行されています。</span><span class="sxs-lookup"><span data-stu-id="d1afa-350">The WCF-Custom or WCF-SQL send port to perform Select and Update operations on the Employee table is running.</span></span>  
  
-   <span data-ttu-id="d1afa-351">SQL Server からメッセージを受信する、ファイル送信ポートが実行されています。</span><span class="sxs-lookup"><span data-stu-id="d1afa-351">The FILE send port, which receives messages from SQL Server, is running.</span></span>  
  
-   <span data-ttu-id="d1afa-352">操作の BizTalk オーケストレーションが実行されています。</span><span class="sxs-lookup"><span data-stu-id="d1afa-352">The BizTalk orchestration for the operation is running.</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="d1afa-353">操作の実行</span><span class="sxs-lookup"><span data-stu-id="d1afa-353">Executing the Operation</span></span>  
 <span data-ttu-id="d1afa-354">この操作を実行するには、Employee テーブルにレコードを挿入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1afa-354">To execute this operation, you must insert a record into the Employee table.</span></span> <span data-ttu-id="d1afa-355">お知らせ、次の詳細情報を持つレコードを挿入するとします。</span><span class="sxs-lookup"><span data-stu-id="d1afa-355">Let us assume you insert a record with following details:</span></span>  
  
```  
Name = John Smith  
Designation = Manager  
Salary = 100000  
```  
  
 <span data-ttu-id="d1afa-356">また、実行する XML メッセージを選択し、更新操作は C:\TestLocation\MessageIn を確認します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-356">Also, make sure the XML message to perform Select and Update operations is available at C:\TestLocation\MessageIn.</span></span> <span data-ttu-id="d1afa-357">XML ファイルは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d1afa-357">The XML file should resemble the following:</span></span>  
  
```  
<Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
  <Columns>Employee_ID,Name,Status</Columns>  
  <Query>where Status=0;UPDATE Employee SET Status=1 WHERE Status=0</Query>  
</Select>  
```  
  
 <span data-ttu-id="d1afa-358">レコードが挿入されると、次の一連のアクションが、同じシーケンス内の場所。</span><span class="sxs-lookup"><span data-stu-id="d1afa-358">Once the record is inserted, the following set of actions take place, in the same sequence:</span></span>  
  
-   <span data-ttu-id="d1afa-359">アダプターは、次のような通知メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d1afa-359">The adapter receives a notification message that resembles the following:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Insert</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     <span data-ttu-id="d1afa-360">このメッセージは、Employee テーブルにレコードが挿入されたことを通知します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-360">This message notifies that a record was inserted in the Employee table.</span></span> <span data-ttu-id="d1afa-361">注意の値、`<Info>`要素は、"Insert"。</span><span class="sxs-lookup"><span data-stu-id="d1afa-361">Note that the value for the `<Info>` element is “Insert”.</span></span>  
  
-   <span data-ttu-id="d1afa-362">アダプターは、選択操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-362">The adapter executes the Select operation.</span></span> <span data-ttu-id="d1afa-363">選択操作で XML には、Update ステートメントも含まれているため、Update ステートメントも実行されます。</span><span class="sxs-lookup"><span data-stu-id="d1afa-363">Because the Select operation XML also includes an Update statement, the Update statement is also executed.</span></span> <span data-ttu-id="d1afa-364">SQL Server から次の応答は、Select ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="d1afa-364">The next response from SQL Server is for the Select statement.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <SelectResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <SelectResult>  
        <Employee xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
          <Employee_ID>10006</Employee_ID>   
          <Name>John</Name>   
          <Status>0</Status>  
        </Employee>  
      </SelectResult>  
    </SelectResponse>  
    ```  
  
     <span data-ttu-id="d1afa-365">この応答は、Employee テーブルにレコードが挿入された、そのレコードの状態は 0 を示します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-365">This response shows that a record was inserted into the Employee table and the Status for that record is 0.</span></span>  
  
-   <span data-ttu-id="d1afa-366">Select ステートメントの一部として、Update ステートメントが実行されることも、新しいレコードの状態 列が 1 に変更されました。</span><span class="sxs-lookup"><span data-stu-id="d1afa-366">As part of the Select statement, the Update statement is also executed and the Status column for the new record is changed to 1.</span></span> <span data-ttu-id="d1afa-367">SQL Server から別の通知をもう一度トリガーこれと対応する、次のような通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-367">This again triggers another notification from SQL Server and the adapter receives a corresponding notification message, that resembles the following:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Update</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     <span data-ttu-id="d1afa-368">このメッセージは、Employee テーブルにレコードが更新されたことを通知します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-368">This message notifies that a record was updated in the Employee table.</span></span> <span data-ttu-id="d1afa-369">注意の値、`<Info>`要素は、「更新」します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-369">Note that the value for the `<Info>` element is “Update”.</span></span>  
  
-   <span data-ttu-id="d1afa-370">2 番目の通知後は、アダプターは、Select ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-370">After the second notification, the adapter executes the Select statement.</span></span> <span data-ttu-id="d1afa-371">ただし、0 としてステータスがあるので、レコードがありません、ため、アダプターは、次のような空の応答を取得します。</span><span class="sxs-lookup"><span data-stu-id="d1afa-371">However, because there are no records now that have Status as 0, the adapter gets an empty response resembling the following.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <SelectResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <SelectResult />   
    </SelectResponse>  
    ```  
  
## <a name="best-practices"></a><span data-ttu-id="d1afa-372">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="d1afa-372">Best Practices</span></span>  
 <span data-ttu-id="d1afa-373">展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="d1afa-373">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the binding file.</span></span> <span data-ttu-id="d1afa-374">バインド ファイルを生成した、送信ポートを作成し、同じオーケストレーション用のポートを受信する必要はありませんように構成設定、ファイルからインポートできます。</span><span class="sxs-lookup"><span data-stu-id="d1afa-374">Once you generate a binding file, you can import the configuration settings from the file, so that you do not need to create the send ports and receive ports for the same orchestration.</span></span> <span data-ttu-id="d1afa-375">バインド ファイルの詳細については、[再利用の SQL アダプター バインド](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1afa-375">For more information about binding files, see [Reuse SQL adapter bindings](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d1afa-376">参照</span><span class="sxs-lookup"><span data-stu-id="d1afa-376">See Also</span></span>  
 [<span data-ttu-id="d1afa-377">BizTalk Server を使用して SQL クエリ通知を受け取る</span><span class="sxs-lookup"><span data-stu-id="d1afa-377">Receive SQL Query Notifications using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)