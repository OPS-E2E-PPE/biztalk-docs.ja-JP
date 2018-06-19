---
title: BizTalk Server を使用して SQL からの受信通知の差分クエリ |Microsoft ドキュメント
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
ms.openlocfilehash: 6fc9eda3ba1bee61b4737428f41870fc31504e3a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967928"
---
# <a name="receive-query-notifications-incrementally-from-sql-using-biztalk-server"></a><span data-ttu-id="246b1-102">BizTalk Server を使用して SQL からの受信通知の差分クエリ</span><span class="sxs-lookup"><span data-stu-id="246b1-102">Receive Query Notifications Incrementally from SQL using BizTalk Server</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="246b1-103">ここでは簡略化のため、このトピックには、通知を受信する差分方法のみについて説明します。</span><span class="sxs-lookup"><span data-stu-id="246b1-103">For the sake of brevity, this topic only describes how to receive notifications incrementally.</span></span> <span data-ttu-id="246b1-104">ビジネス シナリオで、オーケストレーションは理想的には受信した通知メッセージの種類を抽出し、後続の操作を実行するためのロジックを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="246b1-104">In business scenarios, the orchestration must ideally include the logic to extract the kind of notification message received and then perform any subsequent operations.</span></span> <span data-ttu-id="246b1-105">つまり、上で説明されているオーケストレーションにこのトピックで説明されているオーケストレーションを構築する必要が[を BizTalk Server を使用して SQL の特定のタスクの完了の通知メッセージを処理](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)です。</span><span class="sxs-lookup"><span data-stu-id="246b1-105">In other words, the orchestration described in this topic must be built on top of the orchestration described in [Process notification messages to complete specific tasks in SQL using BizTalk Server](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md).</span></span>  
  
 <span data-ttu-id="246b1-106">このトピックの内容を構成する方法を示しています、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server データベースから増分クエリ通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="246b1-106">This topic demonstrates how to configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive incremental query notification messages from a SQL Server database.</span></span> <span data-ttu-id="246b1-107">インクリメンタル通知を示すためには、テーブル、従業員、"Status"列を含むを検討してください。</span><span class="sxs-lookup"><span data-stu-id="246b1-107">To demonstrate incremental notifications, consider a table, Employee, with a “Status” column.</span></span> <span data-ttu-id="246b1-108">このテーブルに新しいレコードが挿入されると、[状態] 列の値は 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="246b1-108">When a new record is inserted to this table, the value of the Status column is set to 0.</span></span> <span data-ttu-id="246b1-109">通知を受信する差分、次の手順を実行して、アダプターを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="246b1-109">You can configure the adapter to receive incremental notifications by doing the following:</span></span>  
  
-   <span data-ttu-id="246b1-110">[状態] 列が 0 であるすべてのレコードを取得する SQL ステートメントを使用して通知を登録します。</span><span class="sxs-lookup"><span data-stu-id="246b1-110">Register for notifications using a SQL statement that retrieves all records that have Status column as 0.</span></span> <span data-ttu-id="246b1-111">これを行うための SQL ステートメントを指定することによって、 **NotificationStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="246b1-111">You can do so by specifying the SQL statement for the **NotificationStatement** binding property.</span></span>  
  
-   <span data-ttu-id="246b1-112">通知のメッセージが受信された行のためには、1 にステータス列を更新します。</span><span class="sxs-lookup"><span data-stu-id="246b1-112">For rows for which notification messages have been received, update the Status column to 1.</span></span>  
  
 <span data-ttu-id="246b1-113">このトピックでは、BizTalk オーケストレーションを作成してこれを実現する BizTalk アプリケーションを構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="246b1-113">This topic demonstrates how to create a BizTalk orchestration and configure a BizTalk application to achieve this.</span></span>  
  
## <a name="configuring-notifications-with-the-sql-adapter-binding-properties"></a><span data-ttu-id="246b1-114">SQL アダプターのプロパティのバインドと通知の構成</span><span class="sxs-lookup"><span data-stu-id="246b1-114">Configuring Notifications with the SQL Adapter Binding Properties</span></span>  
 <span data-ttu-id="246b1-115">次の表、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドのプロパティ構成の SQL Server から通知を受信するために使用します。</span><span class="sxs-lookup"><span data-stu-id="246b1-115">The following table summarizes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding properties that you use to configure receiving notifications from SQL Server.</span></span> <span data-ttu-id="246b1-116">受信ポートを構成するときにこれらのバインディング プロパティを指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="246b1-116">You must specify these binding properties while configuring the receive port in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="246b1-117">スキーマを生成するときに、これらのバインディング プロパティを指定することもできます、**通知**操作、必須ではない場合でもです。</span><span class="sxs-lookup"><span data-stu-id="246b1-117">You may choose to specify these binding properties when generating the schema for the **Notification** operation, even though it is not mandatory.</span></span> <span data-ttu-id="246b1-118">これを行うと、ポートのバインド ファイル、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成され、メタデータの生成の一部では、バインドのプロパティを指定する値も含まれます。</span><span class="sxs-lookup"><span data-stu-id="246b1-118">If you do so, the port binding file that the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] generates as part of the metadata generation also contains the values you specify for the binding properties.</span></span> <span data-ttu-id="246b1-119">このバインド ファイルを後でインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロパティは既に設定されています。 バインドで wcf-custom または WCF SQL を作成する管理コンソールの受信ポート。</span><span class="sxs-lookup"><span data-stu-id="246b1-119">You can later import this binding file in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create the WCF-custom or WCF-SQL receive port with the binding properties already set.</span></span> <span data-ttu-id="246b1-120">詳細については、バインド ファイルを使用するポートを作成する、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="246b1-120">For more information about creating a port using the binding file, see [Configure a physical port binding using a port binding file to use the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).</span></span>  
  
|<span data-ttu-id="246b1-121">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="246b1-121">Binding Property</span></span>|<span data-ttu-id="246b1-122">Description</span><span class="sxs-lookup"><span data-stu-id="246b1-122">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="246b1-123">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="246b1-123">**InboundOperationType**</span></span>|<span data-ttu-id="246b1-124">受信操作を実行することを指定します。</span><span class="sxs-lookup"><span data-stu-id="246b1-124">Specifies the inbound operation that you want to perform.</span></span> <span data-ttu-id="246b1-125">通知メッセージを受信するには、これを設定**通知**です。</span><span class="sxs-lookup"><span data-stu-id="246b1-125">To receive notification messages, set this to **Notification**.</span></span>|  
|<span data-ttu-id="246b1-126">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="246b1-126">**NotificationStatement**</span></span>|<span data-ttu-id="246b1-127">SQL ステートメントを指定します (選択または EXEC\<ストアド プロシージャ\>) のクエリ通知を登録するために使用します。</span><span class="sxs-lookup"><span data-stu-id="246b1-127">Specifies the SQL statement (SELECT or EXEC \<stored procedure\>) used to register for query notifications.</span></span> <span data-ttu-id="246b1-128">アダプターは、指定された SQL ステートメントの変更の結果セットの場合にのみ、SQL Server から通知メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="246b1-128">The adapter gets a notification message from SQL Server only when the result set for the specified SQL statement changes.</span></span>|  
|<span data-ttu-id="246b1-129">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="246b1-129">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="246b1-130">リスナーが開始されたときに、アダプターがアダプターのクライアントに通知を送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="246b1-130">Specifies whether the adapter sends a notification to the adapter clients when the listener is started.</span></span>|  
  
 <span data-ttu-id="246b1-131">これらのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="246b1-131">For a more complete description of these properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="246b1-132">使用する方法の詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]さらに通知を受信する SQL Server から、読み取る。</span><span class="sxs-lookup"><span data-stu-id="246b1-132">For a complete description of how to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to receive notifications from SQL Server, read further.</span></span>  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages"></a><span data-ttu-id="246b1-133">どのように、このトピックでは通知メッセージの受信を示しています</span><span class="sxs-lookup"><span data-stu-id="246b1-133">How This Topic Demonstrates Receiving Notification Messages</span></span>  
 <span data-ttu-id="246b1-134">示すためにどのように[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]SQL Server からの通知メッセージの受信をサポートするには、このトピックは Employee テーブルへの変更の通知を受信するアダプターを構成する方法をデモンストレーションします。</span><span class="sxs-lookup"><span data-stu-id="246b1-134">To demonstrate how the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports receiving notification messages from SQL Server, this topic will demonstrate how to configure the adapter to receive notifications for changes to an Employee table.</span></span> <span data-ttu-id="246b1-135">Employee テーブルの列 Employee_ID、名、および状態であると仮定します。</span><span class="sxs-lookup"><span data-stu-id="246b1-135">Assume that the Employee table has columns Employee_ID, Name, and Status.</span></span> <span data-ttu-id="246b1-136">新しい従業員が追加されるたびに、[状態] 列の値は 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="246b1-136">Whenever a new employee is added, the value of the Status column is set to 0.</span></span>  
  
 <span data-ttu-id="246b1-137">通知の受信を示すためには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="246b1-137">To demonstrate receiving notifications, do the following:</span></span>  
  
-   <span data-ttu-id="246b1-138">スキーマを生成、**通知**(受信操作)、および**選択**(送信操作) Employee テーブルにします。</span><span class="sxs-lookup"><span data-stu-id="246b1-138">Generate schema for the **Notification** (inbound operation), and **Select** (outbound operation) on the Employee table.</span></span>  
  
-   <span data-ttu-id="246b1-139">次のあるオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="246b1-139">Create an orchestration that has the following:</span></span>  
  
    -   <span data-ttu-id="246b1-140">通知メッセージを受信する受信場所。</span><span class="sxs-lookup"><span data-stu-id="246b1-140">A receive location to receive notification messages.</span></span> <span data-ttu-id="246b1-141">通知として SELECT ステートメントを指定することによって構成できます。</span><span class="sxs-lookup"><span data-stu-id="246b1-141">You can configure for notification by specifying the SELECT statement as:</span></span>  
  
        ```  
        SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="246b1-142">具体的には、これで示すように、ステートメント内の列名の SELECT ステートメントを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="246b1-142">You must specifically specify the column names in the statement as shown in this SELECT statement.</span></span> <span data-ttu-id="246b1-143">また、スキーマ名と共に、テーブル名を必ず指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="246b1-143">Also, you must always specify the table name along with the schema name.</span></span> <span data-ttu-id="246b1-144">たとえば、 `dbo.Employee`のようにします。</span><span class="sxs-lookup"><span data-stu-id="246b1-144">For example, `dbo.Employee`.</span></span>  
  
    -   <span data-ttu-id="246b1-145">通知が既に送信されている行を更新する送信ポートです。</span><span class="sxs-lookup"><span data-stu-id="246b1-145">A send port to update the rows for which notification has already been sent.</span></span> <span data-ttu-id="246b1-146">1 に [状態] 列の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="246b1-146">You do so by setting the value in the Status column to 1.</span></span> <span data-ttu-id="246b1-147">選択操作の一部としてこのは、アダプターに、次のメッセージを送信することによって行うことができます。</span><span class="sxs-lookup"><span data-stu-id="246b1-147">You can do this as part of the Select operation by sending the following message to the adapter.</span></span>  
  
        ```  
        <Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
          <Columns>Employee_ID,Name,Status</Columns>  
          <Query>where Status=0;UPDATE Employee SET Status=1 WHERE Status=0</Query>  
        </Select>  
        ```  
  
         <span data-ttu-id="246b1-148">一部としてこのメッセージに、 `<Query>` [状態] 列を更新する UPDATE ステートメントを指定する要素。</span><span class="sxs-lookup"><span data-stu-id="246b1-148">In this message, as part of the `<Query>` element, you specify the UPDATE statement to update the Status column.</span></span> <span data-ttu-id="246b1-149">この操作は、処理された行が更新されるようにメッセージ通知の受信後に実行する必要がありますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="246b1-149">Note that this operation must be executed after receiving the notification messages so that the processed rows are updated.</span></span> <span data-ttu-id="246b1-150">通知応答を取得するまで待機し、行を更新する要求メッセージを手動で削除のオーバーヘッドが除去には、オーケストレーション自体内の行を更新するため、要求メッセージを生成するされます。</span><span class="sxs-lookup"><span data-stu-id="246b1-150">To do away with the overhead of waiting to get the notification response and then manually dropping a request message to update the rows, you will generate the request message for updating the rows within the orchestration itself.</span></span> <span data-ttu-id="246b1-151">これを行うを使用して、**メッセージの構築**図形をオーケストレーション内です。</span><span class="sxs-lookup"><span data-stu-id="246b1-151">You can do so by using the **Construct Message** shape within an orchestration.</span></span>  
  
## <a name="how-to-receive-notification-messages-from-the-sql-server-database"></a><span data-ttu-id="246b1-152">SQL Server データベースから通知メッセージを受信する方法</span><span class="sxs-lookup"><span data-stu-id="246b1-152">How to Receive Notification Messages from the SQL Server Database</span></span>  
 <span data-ttu-id="246b1-153">SQL Server データベースを使用して、操作を実行[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明する手順のタスクでは、 [SQL アダプターと BizTalk アプリケーションを開発する基盤](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="246b1-153">Performing an operation on the SQL Server database using [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves the procedural tasks described in [Building blocks to develop BizTalk applications with the SQL adapter](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md).</span></span> <span data-ttu-id="246b1-154">これらのタスクは通知メッセージを受信アダプターを構成するのには。</span><span class="sxs-lookup"><span data-stu-id="246b1-154">To configure the adapter to receive notification messages, these tasks are:</span></span>  
  
1.  <span data-ttu-id="246b1-155">BizTalk プロジェクトを作成しのスキーマを生成、**通知**(受信操作) と**選択**(送信操作) Employee テーブルにします。</span><span class="sxs-lookup"><span data-stu-id="246b1-155">Create a BizTalk project, and then generate schema for the **Notification** (inbound operation) and **Select** (outbound operation) on the Employee table.</span></span> <span data-ttu-id="246b1-156">必要に応じての値を指定することができます、 **InboundOperationType**と**NotificationStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="246b1-156">Optionally, you can specify values for the **InboundOperationType** and **NotificationStatement** binding properties.</span></span>  
  
2.  <span data-ttu-id="246b1-157">SQL Server データベースから通知を受信するための BizTalk プロジェクトでメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="246b1-157">Create a message in the BizTalk project for receiving notification from the SQL Server database.</span></span>  
  
3.  <span data-ttu-id="246b1-158">SQL Server データベース上の情報を選択を実行して、応答メッセージの受信用の BizTalk プロジェクトでメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="246b1-158">Create messages in the BizTalk project for performing the Select information on the SQL Server database and receiving response messages.</span></span>  
  
4.  <span data-ttu-id="246b1-159">次のオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="246b1-159">Create an orchestration that does the following:</span></span>  
  
    -   <span data-ttu-id="246b1-160">SQL Server から通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="246b1-160">Receives notification message from SQL Server.</span></span>  
  
    -   <span data-ttu-id="246b1-161">選択し、通知を受信した行を更新するメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="246b1-161">Creates a message to select and update the rows for which notification is received.</span></span>  
  
    -   <span data-ttu-id="246b1-162">行を更新する SQL Server にこのメッセージを送信し、応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="246b1-162">Sends this message to the SQL Server to update the rows and receives a response.</span></span>  
  
5.  <span data-ttu-id="246b1-163">構築し、BizTalk プロジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="246b1-163">Build and deploy the BizTalk project.</span></span>  
  
6.  <span data-ttu-id="246b1-164">BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="246b1-164">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="246b1-165">通知メッセージを受信するように、受信操作の一方向の WCF カスタムのみを構成する必要があります。 または WCF SQL 受信ポート。</span><span class="sxs-lookup"><span data-stu-id="246b1-165">For inbound operations, like receiving notification messages, you must only configure a one-way WCF-Custom or WCF-SQL receive port.</span></span> <span data-ttu-id="246b1-166">双方向の WCF カスタムまたは WCF SQL 受信ポートの受信操作はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="246b1-166">Two-way WCF-Custom or WCF-SQL receive ports are not supported for inbound operations.</span></span>  
  
7.  <span data-ttu-id="246b1-167">BizTalk アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="246b1-167">Start the BizTalk application.</span></span>  
  
 <span data-ttu-id="246b1-168">このトピックでは、これらのタスクを実行する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="246b1-168">This topic provides instructions to perform these tasks.</span></span>  
  
## <a name="sample-based-on-this-topic"></a><span data-ttu-id="246b1-169">このトピックの内容に基づくサンプル</span><span class="sxs-lookup"><span data-stu-id="246b1-169">Sample Based on This Topic</span></span>  
 <span data-ttu-id="246b1-170">サンプルは、IncrementalNotification、このトピックの内容に基づいてが付属して、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="246b1-170">A sample, IncrementalNotification, based on this topic is provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="246b1-171">詳細については、次を参照してください。 [SQL アダプタ サンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="246b1-171">For more information, see [Samples for the SQL adapter](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).</span></span>  
  
## <a name="generating-schema"></a><span data-ttu-id="246b1-172">スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="246b1-172">Generating Schema</span></span>  
 <span data-ttu-id="246b1-173">スキーマを生成する必要があります、**通知**操作と**選択**Employee テーブルに対して操作します。</span><span class="sxs-lookup"><span data-stu-id="246b1-173">You must generate the schema for the **Notification** operation and **Select** operation on Employee table.</span></span> <span data-ttu-id="246b1-174">参照してください[SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)スキーマを生成する方法についての詳細。</span><span class="sxs-lookup"><span data-stu-id="246b1-174">See [Get metadata for SQL Server operations in Visual Studio using the SQL adapter](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md) for more information about how to generate the schema.</span></span> <span data-ttu-id="246b1-175">スキーマを生成するときに、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="246b1-175">Perform the following tasks when generating the schema.</span></span> <span data-ttu-id="246b1-176">デザイン時のバインドのプロパティを指定しない場合は、最初の手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="246b1-176">Skip the first step if you do not want to specify the binding properties at design time.</span></span>  
  
1.  <span data-ttu-id="246b1-177">値を指定**InboundOperationType**と**NotificationStatement**スキーマの生成中にプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="246b1-177">Specify a value for **InboundOperationType** and **NotificationStatement** binding properties while generating the schema.</span></span> <span data-ttu-id="246b1-178">このバインドのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="246b1-178">For more information about this binding property, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="246b1-179">バインドのプロパティを指定する方法については、次を参照してください。 [SQL アダプターのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="246b1-179">For instructions on how to specify binding properties, see [Configure the binding properties for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).</span></span>  
  
2.  <span data-ttu-id="246b1-180">コントラクトの種類を選択して**サービス (入力方向の操作)** です。</span><span class="sxs-lookup"><span data-stu-id="246b1-180">Select the contract type as **Service (Inbound operations)**.</span></span>  
  
3.  <span data-ttu-id="246b1-181">スキーマを生成、**通知**操作します。</span><span class="sxs-lookup"><span data-stu-id="246b1-181">Generate schema for the **Notification** operation.</span></span>  
  
4.  <span data-ttu-id="246b1-182">コントラクトの種類を選択して**クライアント (送信操作)** です。</span><span class="sxs-lookup"><span data-stu-id="246b1-182">Select the contract type as **Client (Outbound operations)**.</span></span>  
  
5.  <span data-ttu-id="246b1-183">スキーマを生成、**選択**操作**従業員**テーブル。</span><span class="sxs-lookup"><span data-stu-id="246b1-183">Generate schema for the **Select** operation on **Employee** table.</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="246b1-184">メッセージとメッセージの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="246b1-184">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="246b1-185">以前に生成したスキーマには、オーケストレーション内のメッセージに対して必要な「種類」がについて説明します。</span><span class="sxs-lookup"><span data-stu-id="246b1-185">The schema that you generated earlier describes the "types" required for the messages in the orchestration.</span></span> <span data-ttu-id="246b1-186">メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。</span><span class="sxs-lookup"><span data-stu-id="246b1-186">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="246b1-187">スキーマが生成されるは、BizTalk プロジェクトのオーケストレーションの種類からのメッセージをリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="246b1-187">Once the schema is generated, you must link it to the messages from the Orchestration view of the BizTalk project.</span></span>  
  
 <span data-ttu-id="246b1-188">このトピックでは、3 つのメッセージを作成する必要があります-通知を受信する SQL Server データベース、Select 操作を実行する 1 つの Select 操作の応答を受信する 1 つからいずれか。</span><span class="sxs-lookup"><span data-stu-id="246b1-188">For this topic, you must create three messages—one to receive notifications from the SQL Server database, one to perform the Select operation, and one to receive the response for Select operation.</span></span>  
  
 <span data-ttu-id="246b1-189">メッセージを作成し、それらのスキーマにリンクするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="246b1-189">Perform the following steps to create messages and link them to schema.</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="246b1-190">メッセージを作成し、スキーマにリンクするには</span><span class="sxs-lookup"><span data-stu-id="246b1-190">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="246b1-191">オーケストレーションを BizTalk プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="246b1-191">Add an orchestration to the BizTalk project.</span></span> <span data-ttu-id="246b1-192">ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックし、**追加**、クリックして**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="246b1-192">From the Solution Explorer, right-click the BizTalk project name, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="246b1-193">BizTalk オーケストレーションの名前を入力し、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="246b1-193">Type a name for the BizTalk orchestration and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="246b1-194">まだ開いていない場合は、BizTalk プロジェクトのオーケストレーション ビュー ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="246b1-194">Open the orchestration view window of the BizTalk project, if it is not already open.</span></span> <span data-ttu-id="246b1-195">をクリックして**ビュー**、 をポイント**その他のウィンドウ**、順にクリック**オーケストレーション ビュー**です。</span><span class="sxs-lookup"><span data-stu-id="246b1-195">Click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
3.  <span data-ttu-id="246b1-196">**オーケストレーション ビュー**を右クリックして**メッセージ**、クリックして**新しいメッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="246b1-196">In the **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span>  
  
4.  <span data-ttu-id="246b1-197">新しく作成されたメッセージを右クリックし [**プロパティ] ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="246b1-197">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="246b1-198">**プロパティ**ウィンドウ**Message_1**を次の操作します。</span><span class="sxs-lookup"><span data-stu-id="246b1-198">In the **Properties** pane for **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="246b1-199">プロパティ</span><span class="sxs-lookup"><span data-stu-id="246b1-199">Use this</span></span>|<span data-ttu-id="246b1-200">目的</span><span class="sxs-lookup"><span data-stu-id="246b1-200">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="246b1-201">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="246b1-201">Identifier</span></span>|<span data-ttu-id="246b1-202">「`NotifyReceive`.</span><span class="sxs-lookup"><span data-stu-id="246b1-202">Type `NotifyReceive`.</span></span>|  
    |<span data-ttu-id="246b1-203">メッセージの種類</span><span class="sxs-lookup"><span data-stu-id="246b1-203">Message Type</span></span>|<span data-ttu-id="246b1-204">ドロップダウン リストから、展開**スキーマ**を選択して*SQLNotify.Notification*ここで、 *SQLNotify* BizTalk プロジェクトの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="246b1-204">From the drop-down list, expand **Schemas**, and select *SQLNotify.Notification*, where *SQLNotify* is the name of your BizTalk project.</span></span> <span data-ttu-id="246b1-205">*通知*に対して生成されたスキーマは、**通知**操作します。</span><span class="sxs-lookup"><span data-stu-id="246b1-205">*Notification* is the schema generated for the **Notification** operation.</span></span>|  
  
6.  <span data-ttu-id="246b1-206">手順 3 を繰り返して 2 つの新しいメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="246b1-206">Repeat step 3 to create two new messages.</span></span> <span data-ttu-id="246b1-207">**プロパティ**新しいメッセージ ウィンドウ、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="246b1-207">In the **Properties** pane for the new message, do the following:</span></span>  
  
    |<span data-ttu-id="246b1-208">識別子に設定します。</span><span class="sxs-lookup"><span data-stu-id="246b1-208">Set Identifier to</span></span>|<span data-ttu-id="246b1-209">メッセージの種類を設定</span><span class="sxs-lookup"><span data-stu-id="246b1-209">Set Message Type to</span></span>|  
    |-----------------------|-------------------------|  
    |<span data-ttu-id="246b1-210">Select</span><span class="sxs-lookup"><span data-stu-id="246b1-210">Select</span></span>|<span data-ttu-id="246b1-211">*SQLNotify.TableOperation_dbo_Employee.Select*ここで、 *TableOperation_dbo_Employee*に対して生成されたスキーマは、**選択**操作</span><span class="sxs-lookup"><span data-stu-id="246b1-211">*SQLNotify.TableOperation_dbo_Employee.Select*, where  *TableOperation_dbo_Employee* is the schema generated for the **Select** operation</span></span>|  
    |<span data-ttu-id="246b1-212">SelectResponse</span><span class="sxs-lookup"><span data-stu-id="246b1-212">SelectResponse</span></span>|<span data-ttu-id="246b1-213">*SQLNotify.TableOperation_dbo_Employee.SelectResponse*</span><span class="sxs-lookup"><span data-stu-id="246b1-213">*SQLNotify.TableOperation_dbo_Employee.SelectResponse*</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="246b1-214">オーケストレーションを設定します。</span><span class="sxs-lookup"><span data-stu-id="246b1-214">Setting up the Orchestration</span></span>  
 <span data-ttu-id="246b1-215">使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の SQL Server データベースから通知メッセージを受信し、通知を受信した行を更新します。</span><span class="sxs-lookup"><span data-stu-id="246b1-215">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for receiving notification messages from the SQL Server database and then updating the rows for which notification was received.</span></span> <span data-ttu-id="246b1-216">このオーケストレーションでの指定した SELECT ステートメントに基づく通知メッセージを受信、 **NotificationStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="246b1-216">In this orchestration, the adapter receives the notification message based on the SELECT statement specified for the **NotificationStatement** binding property.</span></span> <span data-ttu-id="246b1-217">通知メッセージは、ファイルの場所で受信されます。</span><span class="sxs-lookup"><span data-stu-id="246b1-217">The notification message is received at a FILE location.</span></span> <span data-ttu-id="246b1-218">応答が受信されると、オーケストレーションは、通知を受信した行の更新に使用されるメッセージを構築します。</span><span class="sxs-lookup"><span data-stu-id="246b1-218">Once the response is received, the orchestration constructs a message that will be used to update the rows for which notification is received.</span></span> <span data-ttu-id="246b1-219">このメッセージの応答を同じファイルの場所にも受信します。</span><span class="sxs-lookup"><span data-stu-id="246b1-219">The response for this message is also received at the same FILE location.</span></span>  
  
 <span data-ttu-id="246b1-220">そのため、オーケストレーションは、次が必要があります。</span><span class="sxs-lookup"><span data-stu-id="246b1-220">So, your orchestration must contain the following:</span></span>  
  
-   <span data-ttu-id="246b1-221">一方向の受信ポートを通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="246b1-221">A one-way receive port to receive notification messages.</span></span>  
  
-   <span data-ttu-id="246b1-222">双方向の送信ポートの行を更新し、同じの応答を受信するメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="246b1-222">A two-way send port to send messages to update rows and receive response for the same.</span></span>  
  
-   <span data-ttu-id="246b1-223">A**メッセージの構築**図形をオーケストレーション内で、更新操作を実行する、メッセージを構築します。</span><span class="sxs-lookup"><span data-stu-id="246b1-223">A **Construct Message** shape to construct messages, to execute the Update operation, within the orchestration.</span></span>  
  
-   <span data-ttu-id="246b1-224">ファイルは、更新操作の応答を保存するポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="246b1-224">A FILE send port to save the response for the Update operation.</span></span>  
  
-   <span data-ttu-id="246b1-225">受信図形と送信図形。</span><span class="sxs-lookup"><span data-stu-id="246b1-225">Receive and send shapes.</span></span>  
  
 <span data-ttu-id="246b1-226">サンプル オーケストレーションには、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="246b1-226">A sample orchestration resembles the following.</span></span>  
  
 <span data-ttu-id="246b1-227">![SQL Server の通知を受信するオーケストレーション](../../adapters-and-accelerators/adapter-sql/media/f13ad3b8-8161-42e5-a521-424bbf549ad5.gif "f13ad3b8-8161-42e5-a521-424bbf549ad5")</span><span class="sxs-lookup"><span data-stu-id="246b1-227">![Orchestration to receive SQL Server notifications](../../adapters-and-accelerators/adapter-sql/media/f13ad3b8-8161-42e5-a521-424bbf549ad5.gif "f13ad3b8-8161-42e5-a521-424bbf549ad5")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="246b1-228">メッセージの構築図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="246b1-228">Adding Message Shapes</span></span>  
 <span data-ttu-id="246b1-229">メッセージの構築図形のごとに、次のプロパティを指定することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="246b1-229">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="246b1-230">図形 列に表示名は、単に記載されているオーケストレーションに表示されるメッセージの構築図形の名前です。</span><span class="sxs-lookup"><span data-stu-id="246b1-230">The names listed in the Shape column are the names of the message shapes as displayed in the just-mentioned orchestration.</span></span>  
  
|<span data-ttu-id="246b1-231">図形</span><span class="sxs-lookup"><span data-stu-id="246b1-231">Shape</span></span>|<span data-ttu-id="246b1-232">図形の種類</span><span class="sxs-lookup"><span data-stu-id="246b1-232">Shape Type</span></span>|<span data-ttu-id="246b1-233">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="246b1-233">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="246b1-234">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="246b1-234">ReceiveNotification</span></span>|<span data-ttu-id="246b1-235">Receive</span><span class="sxs-lookup"><span data-stu-id="246b1-235">Receive</span></span>|<span data-ttu-id="246b1-236">-設定**名前**に*ReceiveNotification*</span><span class="sxs-lookup"><span data-stu-id="246b1-236">- Set **Name** to *ReceiveNotification*</span></span><br /><br /> <span data-ttu-id="246b1-237">-設定**アクティブ**に*は True。*</span><span class="sxs-lookup"><span data-stu-id="246b1-237">- Set **Activate** to *True*</span></span>|  
|<span data-ttu-id="246b1-238">SaveNotification</span><span class="sxs-lookup"><span data-stu-id="246b1-238">SaveNotification</span></span>|<span data-ttu-id="246b1-239">Send</span><span class="sxs-lookup"><span data-stu-id="246b1-239">Send</span></span>|<span data-ttu-id="246b1-240">-設定**名前**に*SaveNotification*</span><span class="sxs-lookup"><span data-stu-id="246b1-240">- Set **Name** to *SaveNotification*</span></span>|  
|<span data-ttu-id="246b1-241">SendSelectMessage</span><span class="sxs-lookup"><span data-stu-id="246b1-241">SendSelectMessage</span></span>|<span data-ttu-id="246b1-242">Send</span><span class="sxs-lookup"><span data-stu-id="246b1-242">Send</span></span>|<span data-ttu-id="246b1-243">-設定**名前**に*SendSelectMessage*</span><span class="sxs-lookup"><span data-stu-id="246b1-243">- Set **Name** to *SendSelectMessage*</span></span>|  
|<span data-ttu-id="246b1-244">ReceiveSelectResponse</span><span class="sxs-lookup"><span data-stu-id="246b1-244">ReceiveSelectResponse</span></span>|<span data-ttu-id="246b1-245">Receive</span><span class="sxs-lookup"><span data-stu-id="246b1-245">Receive</span></span>|<span data-ttu-id="246b1-246">-設定**名前**に*ReceiveSelectResponse*</span><span class="sxs-lookup"><span data-stu-id="246b1-246">- Set **Name** to *ReceiveSelectResponse*</span></span>|  
|<span data-ttu-id="246b1-247">SaveSelectResponse</span><span class="sxs-lookup"><span data-stu-id="246b1-247">SaveSelectResponse</span></span>|<span data-ttu-id="246b1-248">Send</span><span class="sxs-lookup"><span data-stu-id="246b1-248">Send</span></span>|<span data-ttu-id="246b1-249">-設定**名前**に*SaveSelectResponse*</span><span class="sxs-lookup"><span data-stu-id="246b1-249">- Set **Name** to *SaveSelectResponse*</span></span>|  
  
### <a name="adding-construct-message-shape"></a><span data-ttu-id="246b1-250">メッセージの構築図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="246b1-250">Adding Construct Message Shape</span></span>  
 <span data-ttu-id="246b1-251">使用することができます、**メッセージの構築**図形を選択操作を実行する操作内で要求メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="246b1-251">You can use the **Construct Message** shape to generate a request message within the operation to perform the Select operation.</span></span> <span data-ttu-id="246b1-252">これを行うには、追加する必要があります、**メッセージの構築**図形という、**メッセージの割り当て**図形をオーケストレーションにします。</span><span class="sxs-lookup"><span data-stu-id="246b1-252">To do so, you must add a **Construct Message** shape and within that a **Message Assignment** shape to your orchestration.</span></span> <span data-ttu-id="246b1-253">この例で、**メッセージの割り当て**図形が選択操作を実行する SQL Server に送信されるメッセージを生成するコードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="246b1-253">For this example, the **Message Assignment** shape invokes code that generates a message that is sent to SQL Server to perform the Select operation.</span></span> <span data-ttu-id="246b1-254">**メッセージの割り当て**図形も、SQL Server に送信するメッセージに対するアクションを設定します。</span><span class="sxs-lookup"><span data-stu-id="246b1-254">The **Message Assignment** shape also sets the action for the message to be sent to SQL Server.</span></span>  
  
 <span data-ttu-id="246b1-255">メッセージの構築図形、設定、**メッセージ構築**プロパティを**選択**です。</span><span class="sxs-lookup"><span data-stu-id="246b1-255">For the construct message shape, set the **Message Constructed** property to **Select**.</span></span>  
  
 <span data-ttu-id="246b1-256">応答を生成するコードは、BizTalk プロジェクトと同じ Visual Studio ソリューションの一部になります。</span><span class="sxs-lookup"><span data-stu-id="246b1-256">The code to generate the response could be part of the same Visual Studio solution as your BizTalk project.</span></span> <span data-ttu-id="246b1-257">応答メッセージを生成するためのサンプル コードは、次のように検索します。</span><span class="sxs-lookup"><span data-stu-id="246b1-257">A sample code for generating a response message looks like this.</span></span>  
  
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
  
 <span data-ttu-id="246b1-258">要求メッセージを生成できる上記のコードの抜粋をする必要があります (従業員テーブルに対する Select 操作) の XML 要求メッセージの指定した場所に、`XmlFileLocation`変数。</span><span class="sxs-lookup"><span data-stu-id="246b1-258">For the preceding code excerpt to be able to generate a request message, you must have an XML request message (for the Select operation on the Employee table) in the location specified for the `XmlFileLocation` variable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="246b1-259">プロジェクトをビルドした後、SampleMessageCreator.dll はプロジェクト ディレクトリに作成されます。</span><span class="sxs-lookup"><span data-stu-id="246b1-259">After you build the project, SampleMessageCreator.dll will be created in the project directory.</span></span> <span data-ttu-id="246b1-260">グローバル アセンブリ キャッシュ (GAC) には、この DLL を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="246b1-260">You must add this DLL to the global assembly cache (GAC).</span></span> <span data-ttu-id="246b1-261">また、BizTalk プロジェクトに参照として、SampleMessageCreator.dll を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="246b1-261">Also, you must add the SampleMessageCreator.dll as a reference in the BizTalk project.</span></span>  
  
 <span data-ttu-id="246b1-262">次のコードを呼び出すには、次の式を追加、**メッセージの割り当て**図形とメッセージのアクションを設定します。</span><span class="sxs-lookup"><span data-stu-id="246b1-262">Add the following expression to invoke this code from the **Message Assignment** shape and to set the action for message.</span></span> <span data-ttu-id="246b1-263">式を追加するにはダブルクリック、**メッセージの割り当て**図形式エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="246b1-263">To add an expression, double-click the **Message Assignment** shape to open the Expression Editor.</span></span>  
  
```  
Select = SampleMessageCreator.SampleMessageCreator.XMLMessageCreator();  
Select(WCF.Action) = "TableOp/Select/dbo/Employee";  
```  
  
### <a name="adding-ports"></a><span data-ttu-id="246b1-264">ポートの追加</span><span class="sxs-lookup"><span data-stu-id="246b1-264">Adding Ports</span></span>  
 <span data-ttu-id="246b1-265">論理ポートごとに、次のプロパティを指定することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="246b1-265">Make sure you specify the following properties for each of the logical ports.</span></span> <span data-ttu-id="246b1-266">ポート列に表示される名前は、オーケストレーションで表示されているポートの名前です。</span><span class="sxs-lookup"><span data-stu-id="246b1-266">The names listed in the Port column are the names of the ports as displayed in the orchestration.</span></span>  
  
|<span data-ttu-id="246b1-267">ポート</span><span class="sxs-lookup"><span data-stu-id="246b1-267">Port</span></span>|<span data-ttu-id="246b1-268">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="246b1-268">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="246b1-269">SQLNotifyPort</span><span class="sxs-lookup"><span data-stu-id="246b1-269">SQLNotifyPort</span></span>|<span data-ttu-id="246b1-270">-設定**識別子**に*SQLNotifyPort*</span><span class="sxs-lookup"><span data-stu-id="246b1-270">- Set **Identifier** to *SQLNotifyPort*</span></span><br /><br /> <span data-ttu-id="246b1-271">-設定**型**に*SQLNotifyPortType*</span><span class="sxs-lookup"><span data-stu-id="246b1-271">- Set **Type** to *SQLNotifyPortType*</span></span><br /><br /> <span data-ttu-id="246b1-272">-設定**通信パターン**に*一方向*</span><span class="sxs-lookup"><span data-stu-id="246b1-272">- Set **Communication Pattern** to *One-Way*</span></span><br /><br /> <span data-ttu-id="246b1-273">-設定**通信方向**に*受信*</span><span class="sxs-lookup"><span data-stu-id="246b1-273">- Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="246b1-274">SaveMessagePort</span><span class="sxs-lookup"><span data-stu-id="246b1-274">SaveMessagePort</span></span>|<span data-ttu-id="246b1-275">-設定**識別子**に*SaveMessagePort*</span><span class="sxs-lookup"><span data-stu-id="246b1-275">- Set **Identifier** to *SaveMessagePort*</span></span><br /><br /> <span data-ttu-id="246b1-276">-設定**型**に*SaveMessagePortType*</span><span class="sxs-lookup"><span data-stu-id="246b1-276">- Set **Type** to *SaveMessagePortType*</span></span><br /><br /> <span data-ttu-id="246b1-277">-設定**通信パターン**に*一方向*</span><span class="sxs-lookup"><span data-stu-id="246b1-277">- Set **Communication Pattern** to *One-Way*</span></span><br /><br /> <span data-ttu-id="246b1-278">-設定**通信方向**に*送信*</span><span class="sxs-lookup"><span data-stu-id="246b1-278">- Set **Communication Direction** to *Send*</span></span><br /><br /> <span data-ttu-id="246b1-279">操作を作成する*通知*です。</span><span class="sxs-lookup"><span data-stu-id="246b1-279">- Create an operation *Notify*.</span></span> <span data-ttu-id="246b1-280">この操作は、通知メッセージに使用されます。</span><span class="sxs-lookup"><span data-stu-id="246b1-280">This operation is used for notification messages.</span></span><br /><br /> <span data-ttu-id="246b1-281">操作を作成する*選択*です。</span><span class="sxs-lookup"><span data-stu-id="246b1-281">- Create an operation *Select*.</span></span> <span data-ttu-id="246b1-282">この操作は、応答メッセージを使用します。</span><span class="sxs-lookup"><span data-stu-id="246b1-282">This operation is used for select response messages.</span></span>|  
|<span data-ttu-id="246b1-283">SQLOutboundPort</span><span class="sxs-lookup"><span data-stu-id="246b1-283">SQLOutboundPort</span></span>|<span data-ttu-id="246b1-284">-設定**識別子**に*SQLOutboundPort*</span><span class="sxs-lookup"><span data-stu-id="246b1-284">- Set **Identifier** to *SQLOutboundPort*</span></span><br /><br /> <span data-ttu-id="246b1-285">-設定**型**に*SQLOutboundPortType*</span><span class="sxs-lookup"><span data-stu-id="246b1-285">- Set **Type** to *SQLOutboundPortType*</span></span><br /><br /> <span data-ttu-id="246b1-286">-設定**通信パターン**に*要求-応答*</span><span class="sxs-lookup"><span data-stu-id="246b1-286">- Set **Communication Pattern** to *Request-Response*</span></span><br /><br /> <span data-ttu-id="246b1-287">-設定**通信方向**に*送受信*</span><span class="sxs-lookup"><span data-stu-id="246b1-287">- Set **Communication Direction** to *Send-Receive*</span></span>|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a><span data-ttu-id="246b1-288">アクション図形のメッセージを指定し、ポートに接続</span><span class="sxs-lookup"><span data-stu-id="246b1-288">Specify Messages for Action Shapes and Connect to Ports</span></span>  
 <span data-ttu-id="246b1-289">次の表は、プロパティとアクション図形のメッセージを指定して、メッセージ、ポートにリンクを設定する必要があります、値を指定します。</span><span class="sxs-lookup"><span data-stu-id="246b1-289">The following table specifies the properties and their values that you should set to specify messages for action shapes and to link the messages to the ports.</span></span> <span data-ttu-id="246b1-290">図形 列に表示名は、既に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。</span><span class="sxs-lookup"><span data-stu-id="246b1-290">The names listed in the Shape column are the names of the message shapes as displayed in the orchestration mentioned earlier.</span></span>  
  
|<span data-ttu-id="246b1-291">図形</span><span class="sxs-lookup"><span data-stu-id="246b1-291">Shape</span></span>|<span data-ttu-id="246b1-292">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="246b1-292">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="246b1-293">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="246b1-293">ReceiveNotification</span></span>|<span data-ttu-id="246b1-294">-設定**メッセージ**に*NotifyReceive*</span><span class="sxs-lookup"><span data-stu-id="246b1-294">- Set **Message** to *NotifyReceive*</span></span><br /><br /> <span data-ttu-id="246b1-295">-設定**操作**に*SQLNotifyPort.Notify.Request*</span><span class="sxs-lookup"><span data-stu-id="246b1-295">- Set **Operation** to *SQLNotifyPort.Notify.Request*</span></span>|  
|<span data-ttu-id="246b1-296">SaveNotification</span><span class="sxs-lookup"><span data-stu-id="246b1-296">SaveNotification</span></span>|<span data-ttu-id="246b1-297">-設定**メッセージ**に*NotifyReceive*</span><span class="sxs-lookup"><span data-stu-id="246b1-297">- Set **Message** to *NotifyReceive*</span></span><br /><br /> <span data-ttu-id="246b1-298">-設定**操作**に*SaveMessagePort.Notify.Request*</span><span class="sxs-lookup"><span data-stu-id="246b1-298">- Set **Operation** to *SaveMessagePort.Notify.Request*</span></span>|  
|<span data-ttu-id="246b1-299">SendSelectMessage</span><span class="sxs-lookup"><span data-stu-id="246b1-299">SendSelectMessage</span></span>|<span data-ttu-id="246b1-300">-設定**メッセージ**に*選択*</span><span class="sxs-lookup"><span data-stu-id="246b1-300">- Set **Message** to *Select*</span></span><br /><br /> <span data-ttu-id="246b1-301">-設定**操作**に*SQLOutboundPort.Select.Request*</span><span class="sxs-lookup"><span data-stu-id="246b1-301">- Set **Operation** to *SQLOutboundPort.Select.Request*</span></span>|  
|<span data-ttu-id="246b1-302">ReceiveSelectResponse</span><span class="sxs-lookup"><span data-stu-id="246b1-302">ReceiveSelectResponse</span></span>|<span data-ttu-id="246b1-303">-設定**メッセージ**に*SelectResponse*</span><span class="sxs-lookup"><span data-stu-id="246b1-303">- Set **Message** to *SelectResponse*</span></span><br /><br /> <span data-ttu-id="246b1-304">-設定**操作**に*SQLOutboundPort.Select.Response*</span><span class="sxs-lookup"><span data-stu-id="246b1-304">- Set **Operation** to *SQLOutboundPort.Select.Response*</span></span>|  
|<span data-ttu-id="246b1-305">SaveSelectResponse</span><span class="sxs-lookup"><span data-stu-id="246b1-305">SaveSelectResponse</span></span>|<span data-ttu-id="246b1-306">-設定**メッセージ**に*SelectResponse*</span><span class="sxs-lookup"><span data-stu-id="246b1-306">- Set **Message** to *SelectResponse*</span></span><br /><br /> <span data-ttu-id="246b1-307">-設定**操作**に*SaveMessagePort.Select.Request*</span><span class="sxs-lookup"><span data-stu-id="246b1-307">- Set **Operation** to *SaveMessagePort.Select.Request*</span></span>|  
  
 <span data-ttu-id="246b1-308">これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。</span><span class="sxs-lookup"><span data-stu-id="246b1-308">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="246b1-309">今すぐ BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="246b1-309">You must now build the BizTalk solution and deploy it to a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="246b1-310">詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。</span><span class="sxs-lookup"><span data-stu-id="246b1-310">For more information, see [Building and Running Orchestrations](../../core/building-and-running-orchestrations.md).</span></span>
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="246b1-311">BizTalk アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="246b1-311">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="246b1-312">以前に作成したオーケストレーションが下に表示、BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="246b1-312">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the **Orchestrations** pane in the BizTalk Server Administration console.</span></span> <span data-ttu-id="246b1-313">BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="246b1-313">You must use the BizTalk Server Administration console to configure the application.</span></span> <span data-ttu-id="246b1-314">チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。</span><span class="sxs-lookup"><span data-stu-id="246b1-314">For a walkthrough, see [Walkthrough: Deploying a Basic BizTalk Application](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).</span></span>
  
 <span data-ttu-id="246b1-315">アプリケーションの構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="246b1-315">Configuring an application involves:</span></span>  
  
-   <span data-ttu-id="246b1-316">アプリケーションのホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="246b1-316">Selecting a host for the application.</span></span>  
  
-   <span data-ttu-id="246b1-317">BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。</span><span class="sxs-lookup"><span data-stu-id="246b1-317">Mapping the ports that you created in your orchestration to physical ports in the BizTalk Server Administration console.</span></span> <span data-ttu-id="246b1-318">このオーケストレーションの次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="246b1-318">For this orchestration you must:</span></span>  
  
    -   <span data-ttu-id="246b1-319">物理 Wcf-custom を定義するか、WCF SQL 一方向の受信ポートです。</span><span class="sxs-lookup"><span data-stu-id="246b1-319">Define a physical WCF-Custom or WCF-SQL one-way receive port.</span></span> <span data-ttu-id="246b1-320">このポートは、SQL Server データベースからの通知をリッスンします。</span><span class="sxs-lookup"><span data-stu-id="246b1-320">This port listens for notifications coming from the SQL Server database.</span></span> <span data-ttu-id="246b1-321">ポートを作成する方法については、次を参照してください。 [SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="246b1-321">For information about how to create ports, see [Manually configure a physical port binding to the SQL adapter](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md).</span></span> <span data-ttu-id="246b1-322">受信ポートのバインドのプロパティを指定することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="246b1-322">Make sure you specify the following binding properties for the receive port.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="246b1-323">デザイン時のバインドのプロパティを指定した場合、この手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="246b1-323">You do not need to perform this step if you specified the binding properties at design time.</span></span> <span data-ttu-id="246b1-324">このような場合は、WCF カスタムを作成または WCF SQL 受信ポート、必要なバインド プロパティを設定、によって作成されたバインド ファイルをインポートすることによって、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="246b1-324">In such a case, you can create a WCF-custom or WCF-SQL receive port, with the required binding properties set, by importing the binding file created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span> <span data-ttu-id="246b1-325">詳細については、次を参照してください。 [SQL アダプターを使用するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="246b1-325">For more information see [Configure a physical port binding using a port binding file to use the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).</span></span>  
  
        |<span data-ttu-id="246b1-326">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="246b1-326">Binding Property</span></span>|<span data-ttu-id="246b1-327">値</span><span class="sxs-lookup"><span data-stu-id="246b1-327">Value</span></span>|  
        |----------------------|-----------|  
        |<span data-ttu-id="246b1-328">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="246b1-328">**InboundOperationType**</span></span>|<span data-ttu-id="246b1-329">これを設定して**通知**です。</span><span class="sxs-lookup"><span data-stu-id="246b1-329">Set this to **Notification**.</span></span>|  
        |<span data-ttu-id="246b1-330">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="246b1-330">**NotificationStatement**</span></span>|<span data-ttu-id="246b1-331">これを設定します。</span><span class="sxs-lookup"><span data-stu-id="246b1-331">Set this to:</span></span><br /><br /> `SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0`<br /><br /> <span data-ttu-id="246b1-332">**注:** する必要があります具体的には、列名を指定、ステートメントで次の SELECT ステートメントで示すようにします。</span><span class="sxs-lookup"><span data-stu-id="246b1-332">**Note:** You must specifically specify the column names in the statement as shown in this SELECT statement.</span></span> <span data-ttu-id="246b1-333">また、スキーマ名と共に、テーブル名を必ず指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="246b1-333">Also, you must always specify the table name along with the schema name.</span></span> <span data-ttu-id="246b1-334">たとえば、 `dbo.Employee`のようにします。</span><span class="sxs-lookup"><span data-stu-id="246b1-334">For example, `dbo.Employee`.</span></span>|  
        |<span data-ttu-id="246b1-335">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="246b1-335">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="246b1-336">これを設定して**True**です。</span><span class="sxs-lookup"><span data-stu-id="246b1-336">Set this to **True**.</span></span>|  
  
         <span data-ttu-id="246b1-337">異なるバインディングのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="246b1-337">For more information about the different binding properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="246b1-338">使用して受信操作の実行中に、トランザクション分離レベルとトランザクションのタイムアウトを構成することをお勧め、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="246b1-338">We recommend configuring the transaction isolation level and the transaction timeout while performing inbound operations using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="246b1-339">サービスを追加することで、Wcf-custom または WCF SQL の構成中に動作の受信ポートを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="246b1-339">You can do so by adding the service behavior while configuring the WCF-Custom or WCF-SQL receive port.</span></span> <span data-ttu-id="246b1-340">サービスの動作を追加する方法については、次を参照してください。[トランザクション分離レベルの構成と SQL を使用したトランザクションのタイムアウト](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)です。</span><span class="sxs-lookup"><span data-stu-id="246b1-340">For instruction on how to add the service behavior, see [Configure Transaction Isolation Level and Transaction Timeout with SQL](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md).</span></span>  
  
    -   <span data-ttu-id="246b1-341">SQL Server データベースにメッセージを送信する物理 Wcf-custom または WCF-SQL 送信ポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="246b1-341">Define a physical WCF-Custom or WCF-SQL send port to send messages to the SQL Server database.</span></span> <span data-ttu-id="246b1-342">送信ポートでアクションを指定することもあります。</span><span class="sxs-lookup"><span data-stu-id="246b1-342">You must also specify the action in the send port.</span></span>  
  
    -   <span data-ttu-id="246b1-343">ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが、SQL Server データベースからメッセージをドロップ場所に場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="246b1-343">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the messages from the SQL Server database.</span></span> <span data-ttu-id="246b1-344">これらは、SQL Server から受信した通知メッセージと、選択のメッセージと更新操作、Wcf-custom または WCF SQL を使用して実行する送信ポート。</span><span class="sxs-lookup"><span data-stu-id="246b1-344">These will be the notification messages received from SQL Server and messages for the Select and Update operation you perform through the WCF-Custom or WCF-SQL send port.</span></span>  
  
## <a name="starting-the-application"></a><span data-ttu-id="246b1-345">アプリケーションの起動</span><span class="sxs-lookup"><span data-stu-id="246b1-345">Starting the Application</span></span>  
 <span data-ttu-id="246b1-346">SQL Server データベースから通知メッセージを受信して、Select および Update の後続の操作を実行するために、BizTalk アプリケーションを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="246b1-346">You must start the BizTalk application for receiving notification messages from the SQL Server database and for performing the subsequent Select and Update operations.</span></span> <span data-ttu-id="246b1-347">BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。</span><span class="sxs-lookup"><span data-stu-id="246b1-347">For instructions on starting a BizTalk application, see [How to Start an Orchestration](../../core/how-to-start-an-orchestration.md).</span></span>
  
 <span data-ttu-id="246b1-348">この段階で確認します。</span><span class="sxs-lookup"><span data-stu-id="246b1-348">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="246b1-349">Wcf-custom または WCF SQL 一方向の受信ポートで、データベースが実行されている SQL Server から通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="246b1-349">The WCF-Custom or WCF-SQL one-way receive port, which receives the notification messages from the SQL Server database is running.</span></span>  
  
-   <span data-ttu-id="246b1-350">実行する Wcf-custom または WCF-SQL 送信ポートを選択し、Employee テーブルでの Update 操作が実行されています。</span><span class="sxs-lookup"><span data-stu-id="246b1-350">The WCF-Custom or WCF-SQL send port to perform Select and Update operations on the Employee table is running.</span></span>  
  
-   <span data-ttu-id="246b1-351">SQL Server からメッセージを受信する FILE 送信ポートが実行されています。</span><span class="sxs-lookup"><span data-stu-id="246b1-351">The FILE send port, which receives messages from SQL Server, is running.</span></span>  
  
-   <span data-ttu-id="246b1-352">操作の BizTalk オーケストレーションが実行されています。</span><span class="sxs-lookup"><span data-stu-id="246b1-352">The BizTalk orchestration for the operation is running.</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="246b1-353">操作の実行</span><span class="sxs-lookup"><span data-stu-id="246b1-353">Executing the Operation</span></span>  
 <span data-ttu-id="246b1-354">この操作を実行するには、Employee テーブルにレコードを挿入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="246b1-354">To execute this operation, you must insert a record into the Employee table.</span></span> <span data-ttu-id="246b1-355">次の内容でレコードを挿入すると仮定お知らせします。</span><span class="sxs-lookup"><span data-stu-id="246b1-355">Let us assume you insert a record with following details:</span></span>  
  
```  
Name = John Smith  
Designation = Manager  
Salary = 100000  
```  
  
 <span data-ttu-id="246b1-356">またを実行する、XML メッセージを選択し、更新操作は C:\TestLocation\MessageIn で利用できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="246b1-356">Also, make sure the XML message to perform Select and Update operations is available at C:\TestLocation\MessageIn.</span></span> <span data-ttu-id="246b1-357">XML ファイルは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="246b1-357">The XML file should resemble the following:</span></span>  
  
```  
<Select xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
  <Columns>Employee_ID,Name,Status</Columns>  
  <Query>where Status=0;UPDATE Employee SET Status=1 WHERE Status=0</Query>  
</Select>  
```  
  
 <span data-ttu-id="246b1-358">レコードが挿入されると、次の一連のアクションが実行、同じ順序で。</span><span class="sxs-lookup"><span data-stu-id="246b1-358">Once the record is inserted, the following set of actions take place, in the same sequence:</span></span>  
  
-   <span data-ttu-id="246b1-359">アダプターは、次のような通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="246b1-359">The adapter receives a notification message that resembles the following:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Insert</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     <span data-ttu-id="246b1-360">このメッセージは、Employee テーブルのレコードが挿入されたことを通知します。</span><span class="sxs-lookup"><span data-stu-id="246b1-360">This message notifies that a record was inserted in the Employee table.</span></span> <span data-ttu-id="246b1-361">なおの値、`<Info>`要素は、"Insert"です。</span><span class="sxs-lookup"><span data-stu-id="246b1-361">Note that the value for the `<Info>` element is “Insert”.</span></span>  
  
-   <span data-ttu-id="246b1-362">アダプターは、Select 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="246b1-362">The adapter executes the Select operation.</span></span> <span data-ttu-id="246b1-363">XML の選択操作には、Update ステートメントも含まれているため、Update ステートメントも実行します。</span><span class="sxs-lookup"><span data-stu-id="246b1-363">Because the Select operation XML also includes an Update statement, the Update statement is also executed.</span></span> <span data-ttu-id="246b1-364">SQL Server から次の応答では、Select ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="246b1-364">The next response from SQL Server is for the Select statement.</span></span>  
  
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
  
     <span data-ttu-id="246b1-365">この応答は、Employee テーブルにレコードが挿入された、そのレコードの状態は 0 を示します。</span><span class="sxs-lookup"><span data-stu-id="246b1-365">This response shows that a record was inserted into the Employee table and the Status for that record is 0.</span></span>  
  
-   <span data-ttu-id="246b1-366">Select ステートメントの一部として、Update ステートメントの実行もと、新しいレコードの状態 列が 1 に変更されました。</span><span class="sxs-lookup"><span data-stu-id="246b1-366">As part of the Select statement, the Update statement is also executed and the Status column for the new record is changed to 1.</span></span> <span data-ttu-id="246b1-367">SQL Server から別の通知をもう一度トリガーこれと、次のような対応する通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="246b1-367">This again triggers another notification from SQL Server and the adapter receives a corresponding notification message, that resembles the following:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Update</Info>   
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     <span data-ttu-id="246b1-368">このメッセージは、Employee テーブルのレコードが更新されたことを通知します。</span><span class="sxs-lookup"><span data-stu-id="246b1-368">This message notifies that a record was updated in the Employee table.</span></span> <span data-ttu-id="246b1-369">なおの値、`<Info>`要素は、「更新」です。</span><span class="sxs-lookup"><span data-stu-id="246b1-369">Note that the value for the `<Info>` element is “Update”.</span></span>  
  
-   <span data-ttu-id="246b1-370">2 番目の通知後は、アダプターは、Select ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="246b1-370">After the second notification, the adapter executes the Select statement.</span></span> <span data-ttu-id="246b1-371">ただし、0 と状態があるので、レコードがありません、ため、アダプターは、次のような空の応答を取得します。</span><span class="sxs-lookup"><span data-stu-id="246b1-371">However, because there are no records now that have Status as 0, the adapter gets an empty response resembling the following.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <SelectResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <SelectResult />   
    </SelectResponse>  
    ```  
  
## <a name="best-practices"></a><span data-ttu-id="246b1-372">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="246b1-372">Best Practices</span></span>  
 <span data-ttu-id="246b1-373">展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="246b1-373">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the binding file.</span></span> <span data-ttu-id="246b1-374">バインド ファイルを生成したできるように、送信ポートを作成し、同じオーケストレーション用のポートを受信する必要はありません、ファイルから構成設定をインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="246b1-374">Once you generate a binding file, you can import the configuration settings from the file, so that you do not need to create the send ports and receive ports for the same orchestration.</span></span> <span data-ttu-id="246b1-375">バインド ファイルの詳細については、次を参照してください。[アダプターのバインドが SQL の再利用](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)です。</span><span class="sxs-lookup"><span data-stu-id="246b1-375">For more information about binding files, see [Reuse SQL adapter bindings](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="246b1-376">参照</span><span class="sxs-lookup"><span data-stu-id="246b1-376">See Also</span></span>  
 [<span data-ttu-id="246b1-377">BizTalk Server を使用して SQL クエリ通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="246b1-377">Receive SQL Query Notifications using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)