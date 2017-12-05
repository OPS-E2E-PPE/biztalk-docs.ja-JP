---
title: "BizTalk Server を使用して増分値 Oracle データベースの変更通知を受け取る |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 17cef39f-a1aa-4f46-993f-620008f3890d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eebcd37124e0ddde2171f21b233ca8bd8ce23f55
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="receive-oracle-database-change-notifications-incrementally-using-biztalk-server"></a><span data-ttu-id="104e1-102">BizTalk Server を使用して増分値 Oracle データベースの変更通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="104e1-102">Receive Oracle Database change notifications incrementally using BizTalk Server</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="104e1-103">ここでは簡略化のため、このトピックには、通知を受信する差分方法のみについて説明します。</span><span class="sxs-lookup"><span data-stu-id="104e1-103">For the sake of brevity, this topic only describes how to receive notifications incrementally.</span></span> <span data-ttu-id="104e1-104">ビジネス シナリオで、オーケストレーションは理想的には受信した通知メッセージの種類を抽出し、後続の操作を実行するためのロジックを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="104e1-104">In business scenarios, the orchestration must ideally include the logic to extract the kind of notification message received and then perform any subsequent operations.</span></span> <span data-ttu-id="104e1-105">つまり、上で説明されているオーケストレーションにこのトピックで説明されているオーケストレーションを構築する必要が[BizTalk Sever を使用して Oracle データベースで特定のタスクを完了する通知メッセージを処理](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md)です。</span><span class="sxs-lookup"><span data-stu-id="104e1-105">In other words, the orchestration described in this topic must be built on top of the orchestration described in [Process Notification Messages to complete Specific Tasks in Oracle Database using BizTalk Sever](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md).</span></span>  
  
 <span data-ttu-id="104e1-106">このトピックの内容を構成する方法を示しています、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle から増分クエリ通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="104e1-106">This topic demonstrates how to configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to receive incremental query notification messages from Oracle.</span></span> <span data-ttu-id="104e1-107">インクリメンタル通知を示すためには、ACCOUNTACTIVITY、列を持つテーブルを「処理」を検討します。</span><span class="sxs-lookup"><span data-stu-id="104e1-107">To demonstrate incremental notifications, we consider a table, ACCOUNTACTIVITY, with a “Processed” column.</span></span> <span data-ttu-id="104e1-108">このテーブルに新しいレコードが挿入されると、「処理」列の値 éý 'è' n ' です。</span><span class="sxs-lookup"><span data-stu-id="104e1-108">When a new record is inserted to this table, the value of the “Processed” column is set to ‘n’.</span></span> <span data-ttu-id="104e1-109">通知を受信する差分、次の手順を実行して、アダプターを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="104e1-109">You can configure the adapter to receive incremental notifications by doing the following:</span></span>  
  
-   <span data-ttu-id="104e1-110">として「処理済み」の列が含まれるすべてのレコードを取得する SELECT ステートメントを使用して通知の登録 'n' です。</span><span class="sxs-lookup"><span data-stu-id="104e1-110">Register for notifications using a SELECT statement that retrieves all records that have “Processed” column as ‘n’.</span></span> <span data-ttu-id="104e1-111">これを行うの SELECT ステートメントを指定することによって、 **NotificationStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="104e1-111">You can do so by specifying the SELECT statement for the **NotificationStatement** binding property.</span></span>  
  
-   <span data-ttu-id="104e1-112">通知されている行のためには、'y'「処理」列を更新します。</span><span class="sxs-lookup"><span data-stu-id="104e1-112">For rows which have been notified for, update the “Processed” column to ‘y’.</span></span>  
  
 <span data-ttu-id="104e1-113">このトピックでは、BizTalk オーケストレーションを作成してこれを実現する BizTalk アプリケーションを構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="104e1-113">This topic demonstrates how to create a BizTalk orchestration and configure a BizTalk application to achieve this.</span></span>  
  
## <a name="configuring-notifications-with-the-oracle-database-adapter-binding-properties"></a><span data-ttu-id="104e1-114">Oracle データベース アダプターのプロパティをバインドに通知を構成します。</span><span class="sxs-lookup"><span data-stu-id="104e1-114">Configuring Notifications with the Oracle Database Adapter Binding Properties</span></span>  
 <span data-ttu-id="104e1-115">次の表、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドのプロパティ、Oracle データベースから通知の受信を構成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="104e1-115">The following table summarizes the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] binding properties that you use to configure receiving notifications from the Oracle database.</span></span> <span data-ttu-id="104e1-116">受信ポートを構成するときにこれらのバインディング プロパティを指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="104e1-116">You must specify these binding properties while configuring the receive port in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="104e1-117">スキーマを生成するときに、これらのバインディング プロパティを指定することもできます、**通知**操作、必須ではない場合でもです。</span><span class="sxs-lookup"><span data-stu-id="104e1-117">You may choose to specify these binding properties when generating the schema for the **Notification** operation, even though it is not mandatory.</span></span> <span data-ttu-id="104e1-118">これを行うと、ポートのバインド ファイル、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成され、メタデータの生成の一部では、バインドのプロパティを指定する値も含まれます。</span><span class="sxs-lookup"><span data-stu-id="104e1-118">If you do so, the port binding file that the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] generates as part of the metadata generation also contains the values you specify for the binding properties.</span></span> <span data-ttu-id="104e1-119">このバインド ファイルを後でインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロパティは既に設定されています。 バインドで wcf-custom または Wcf-oracledb を作成する管理コンソールの受信ポート。</span><span class="sxs-lookup"><span data-stu-id="104e1-119">You can later import this binding file in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create the WCF-custom or WCF-OracleDB receive port with the binding properties already set.</span></span> <span data-ttu-id="104e1-120">バインド ファイルを使用して受信ポートの作成の詳細については、次を参照してください。 [Oracle データベースへのポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="104e1-120">For more information about creating a receive port using the binding file, see [Configure a physical port binding using a port binding file to Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).</span></span>  
  
|<span data-ttu-id="104e1-121">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="104e1-121">Binding Property</span></span>|<span data-ttu-id="104e1-122">Description</span><span class="sxs-lookup"><span data-stu-id="104e1-122">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="104e1-123">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="104e1-123">**InboundOperationType**</span></span>|<span data-ttu-id="104e1-124">受信操作を実行することを指定します。</span><span class="sxs-lookup"><span data-stu-id="104e1-124">Specifies the inbound operation that you want to perform.</span></span> <span data-ttu-id="104e1-125">通知メッセージを受信するには、これを設定**通知**です。</span><span class="sxs-lookup"><span data-stu-id="104e1-125">To receive notification messages, set this to **Notification**.</span></span>|  
|<span data-ttu-id="104e1-126">**NotificationPort**</span><span class="sxs-lookup"><span data-stu-id="104e1-126">**NotificationPort**</span></span>|<span data-ttu-id="104e1-127">ODP.NET が Oracle データベースからデータベースの変更通知をリッスンするように開く必要があるポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="104e1-127">Specifies the port number that ODP.NET must open to listen for database change notification from Oracle database.</span></span>|  
|<span data-ttu-id="104e1-128">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="104e1-128">**NotificationStatement**</span></span>|<span data-ttu-id="104e1-129">クエリ通知の登録に使用する SELECT ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="104e1-129">Specifies the SELECT statement used to register for query notifications.</span></span> <span data-ttu-id="104e1-130">アダプターは、指定した SELECT ステートメントの変更の結果セットの場合にのみ、通知メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="104e1-130">The adapter gets a notification message only when the result set for the specified SELECT statement changes.</span></span>|  
|<span data-ttu-id="104e1-131">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="104e1-131">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="104e1-132">リスナーが開始されたときに、アダプターがアダプターのクライアントに通知を送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="104e1-132">Specifies whether the adapter sends a notification to the adapter clients when the listener is started.</span></span>|  
  
 <span data-ttu-id="104e1-133">これらのプロパティの詳細については、次を参照してください。 [BizTalk Adapter 用 Oracle Database バインド プロパティの操作](https://msdn.microsoft.com/library/dd788467.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="104e1-133">For a more complete description of these properties, see [Working with BizTalk Adapter for Oracle Database Binding Properties](https://msdn.microsoft.com/library/dd788467.aspx).</span></span> <span data-ttu-id="104e1-134">使用する方法の詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]さらに通知を受信する Oracle データベースから、読み取る。</span><span class="sxs-lookup"><span data-stu-id="104e1-134">For a complete description of how to use the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to receive notifications from the Oracle database, read further.</span></span>  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages"></a><span data-ttu-id="104e1-135">どのように、このトピックでは通知メッセージの受信を示しています</span><span class="sxs-lookup"><span data-stu-id="104e1-135">How This Topic Demonstrates Receiving Notification Messages</span></span>  
 <span data-ttu-id="104e1-136">このトピックの内容を示すためにどのように[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ACCOUNTACTIVTY テーブルへの変更の通知を受信するアダプターを構成して、Oracle データベースからのデータベースの増分変更の通知メッセージの受信をサポートするには、おです。</span><span class="sxs-lookup"><span data-stu-id="104e1-136">In this topic, to demonstrate how the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports receiving incremental database change notification messages from the Oracle database, we will configure the adapter to receive notifications for changes to the ACCOUNTACTIVTY table.</span></span> <span data-ttu-id="104e1-137">お知らせ ACCOUNTACTIVITY テーブルの列"TID"、「アカウント」および「処理」であると仮定します。</span><span class="sxs-lookup"><span data-stu-id="104e1-137">Let us assume that the ACCOUNTACTIVITY table has columns “TID”, “Account”, and “Processed”.</span></span> <span data-ttu-id="104e1-138">新しいレコードを追加するたびに、「処理済み」の列の設定は 'n' です。</span><span class="sxs-lookup"><span data-stu-id="104e1-138">Whenever a new record is added, the value of the “Processed” column is set to ‘n’.</span></span> <span data-ttu-id="104e1-139">そのため、インクリメンタル通知を取得する必要を BizTalk オーケストレーションの一部として、次のタスクを行うには。</span><span class="sxs-lookup"><span data-stu-id="104e1-139">So, to get incremental notifications you will have to do the following tasks as part of the BizTalk orchestration:</span></span>  
  
-   <span data-ttu-id="104e1-140">ここで、「処理」はすべてのレコードの通知を受け取る 'n' です。</span><span class="sxs-lookup"><span data-stu-id="104e1-140">Get notification for all records where “Processed” is ‘n’.</span></span> <span data-ttu-id="104e1-141">通知のステートメントと SELECT ステートメントを指定することによって、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="104e1-141">You can do this by specifying a SELECT statement as a notification statement.</span></span>  
  
-   <span data-ttu-id="104e1-142">特定のレコードに対して、通知を受け取った後に、'y'「処理」を設定します。</span><span class="sxs-lookup"><span data-stu-id="104e1-142">After the notification is received for a certain record, set “Processed” to ‘y’.</span></span> <span data-ttu-id="104e1-143">PROCESS_RECORDS で、「処理」列を更新し、ストアド プロシージャを実行することによって、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="104e1-143">You can do this by executing a stored procedure, PROCESS_RECORDS, which updates the “Processed” column.</span></span>  
  
 <span data-ttu-id="104e1-144">インクリメンタル通知の受信を示すためは、次を操作します。</span><span class="sxs-lookup"><span data-stu-id="104e1-144">To demonstrate receiving incremental notifications, we do the following:</span></span>  
  
-   <span data-ttu-id="104e1-145">スキーマを生成、**通知**(受信操作)、および**PROCESS_RECORDS** (送信操作) ACCOUNTACTIVITY テーブルにします。</span><span class="sxs-lookup"><span data-stu-id="104e1-145">Generate schema for the **Notification** (inbound operation), and **PROCESS_RECORDS** (outbound operation) on the ACCOUNTACTIVITY table.</span></span>  
  
-   <span data-ttu-id="104e1-146">次のあるオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="104e1-146">Create an orchestration that has the following:</span></span>  
  
    -   <span data-ttu-id="104e1-147">通知メッセージを受信する受信場所。</span><span class="sxs-lookup"><span data-stu-id="104e1-147">A receive location to receive notification messages.</span></span> <span data-ttu-id="104e1-148">通知として SELECT ステートメントを指定することによって構成できます。</span><span class="sxs-lookup"><span data-stu-id="104e1-148">You can configure for notification by specifying the SELECT statement as:</span></span>  
  
        ```  
        SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="104e1-149">スキーマ名と共に、テーブル名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="104e1-149">You must specify the table name along with the schema name.</span></span> <span data-ttu-id="104e1-150">たとえば、 `SCOTT.ACCOUNTACTIVITY`のようにします。</span><span class="sxs-lookup"><span data-stu-id="104e1-150">For example, `SCOTT.ACCOUNTACTIVITY`.</span></span>  
  
    -   <span data-ttu-id="104e1-151">通知が既に送信されている行を更新する送信ポートです。</span><span class="sxs-lookup"><span data-stu-id="104e1-151">A send port to update the rows for which notification has already been sent.</span></span> <span data-ttu-id="104e1-152">PROCESS_RECORDS ストアド プロシージャは、通知を受信したレコードの 'y'「処理」列の値を設定するには、このポートで実行されます。</span><span class="sxs-lookup"><span data-stu-id="104e1-152">You will execute the PROCESS_RECORDS stored procedure on this port to set the value of “Processed” column to ‘y’ for the records for which notification is received.</span></span>  
  
         <span data-ttu-id="104e1-153">この操作は、処理された行が更新されるようにメッセージ通知の受信後に実行する必要がありますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="104e1-153">Note that this operation must be executed after receiving the notification messages so that the processed rows are updated.</span></span> <span data-ttu-id="104e1-154">通知応答を取得するまで待機し、PROCESS_RECORDS プロシージャを実行する要求メッセージを手動で削除のオーバーヘッドが除去には、オーケストレーション自体内 PROCESS_RECORDS プロシージャの要求メッセージを生成するされます。</span><span class="sxs-lookup"><span data-stu-id="104e1-154">To do away with the overhead of waiting to get the notification response and then manually dropping a request message to execute the PROCESS_RECORDS procedure, you will generate the request message for PROCESS_RECORDS procedure within the orchestration itself.</span></span> <span data-ttu-id="104e1-155">これを行うを使用して、**メッセージの構築**図形をオーケストレーション内です。</span><span class="sxs-lookup"><span data-stu-id="104e1-155">You can do so by using the **Construct Message** shape within an orchestration.</span></span>  
  
## <a name="how-to-receive-notification-messages-from-the-oracle-database"></a><span data-ttu-id="104e1-156">Oracle データベースから通知メッセージを受信する方法</span><span class="sxs-lookup"><span data-stu-id="104e1-156">How to Receive Notification Messages from the Oracle database</span></span>  
 <span data-ttu-id="104e1-157">Oracle データベースを使用して、操作を実行[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明する手順のタスクでは、[の Oracle データベースと BizTalk アプリケーションを開発する基盤](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="104e1-157">Performing an operation on the Oracle database using [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves the procedural tasks described in [Building blocks to develop BizTalk Applications with Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md).</span></span> <span data-ttu-id="104e1-158">これらのタスクは通知メッセージを受信アダプターを構成するのには。</span><span class="sxs-lookup"><span data-stu-id="104e1-158">To configure the adapter to receive notification messages, these tasks are:</span></span>  
  
1.  <span data-ttu-id="104e1-159">BizTalk プロジェクトを作成しのスキーマを生成、**通知**(受信操作) と**PROCESS_RECORDS** ACCOUNTACTIVITY テーブルで、手順 (送信操作)。</span><span class="sxs-lookup"><span data-stu-id="104e1-159">Create a BizTalk project, and then generate schema for the **Notification** (inbound operation) and **PROCESS_RECORDS** procedure (outbound operation) on the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="104e1-160">必要に応じての値を指定することができます、 **InboundOperationType**、 **NotificationPort**、および**NotificationStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="104e1-160">Optionally, you can specify values for the **InboundOperationType**, **NotificationPort**, and **NotificationStatement** binding properties.</span></span>  
  
2.  <span data-ttu-id="104e1-161">Oracle データベースから通知を受信するための BizTalk プロジェクトでメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="104e1-161">Create a message in the BizTalk project for receiving notification from the Oracle database.</span></span>  
  
3.  <span data-ttu-id="104e1-162">PROCESS_RECORDS ストアド プロシージャを実行して、応答メッセージの送受信用の BizTalk プロジェクトでメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="104e1-162">Create messages in the BizTalk project for executing the PROCESS_RECORDS stored procedure and receiving response messages.</span></span>  
  
4.  <span data-ttu-id="104e1-163">次のオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="104e1-163">Create an orchestration that does the following:</span></span>  
  
    -   <span data-ttu-id="104e1-164">Oracle データベースから通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="104e1-164">Receives notification message from the Oracle database.</span></span>  
  
    -   <span data-ttu-id="104e1-165">PROCESS_RECORDS プロシージャを実行するメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="104e1-165">Creates a message to execute the PROCESS_RECORDS procedure.</span></span>  
  
    -   <span data-ttu-id="104e1-166">Oracle データベースを選択して、レコードを更新し、応答を受信するには、このメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="104e1-166">Sends this message to the Oracle database to select and update the records and receive a response.</span></span>  
  
5.  <span data-ttu-id="104e1-167">構築し、BizTalk プロジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="104e1-167">Build and deploy the BizTalk project.</span></span>  
  
6.  <span data-ttu-id="104e1-168">BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="104e1-168">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="104e1-169">通知メッセージを受信するように、受信操作の一方向の WCF カスタムのみを構成する必要があります。 または Wcf-oracledb 受信ポート。</span><span class="sxs-lookup"><span data-stu-id="104e1-169">For inbound operations, like receiving notification messages, you must only configure a one-way WCF-Custom or WCF-OracleDB receive port.</span></span> <span data-ttu-id="104e1-170">双方向受信ポートが受信操作のサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="104e1-170">Two-way receive ports are not supported for inbound operations.</span></span>  
  
7.  <span data-ttu-id="104e1-171">BizTalk アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="104e1-171">Start the BizTalk application.</span></span>  
  
 <span data-ttu-id="104e1-172">このトピックでは、これらのタスクを実行する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="104e1-172">This topic provides instructions to perform these tasks.</span></span>  
  
## <a name="generating-schema"></a><span data-ttu-id="104e1-173">スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="104e1-173">Generating Schema</span></span>  
 <span data-ttu-id="104e1-174">スキーマを生成する必要があります、**通知**操作と**PROCESS_RECORDS**プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="104e1-174">You must generate the schema for the **Notification** operation and **PROCESS_RECORDS** procedure.</span></span> <span data-ttu-id="104e1-175">参照してください[Visual Studio での Oracle 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)スキーマを生成する方法についての詳細。</span><span class="sxs-lookup"><span data-stu-id="104e1-175">See [Retrieve metadata for Oracle operations in Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md) for more information about how to generate the schema.</span></span> <span data-ttu-id="104e1-176">スキーマを生成するときに、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="104e1-176">Perform the following tasks when generating the schema.</span></span> <span data-ttu-id="104e1-177">デザイン時のバインドのプロパティを指定しない場合は、最初の手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="104e1-177">Skip the first step if you do not want to specify the binding properties at design-time.</span></span>  
  
1.  <span data-ttu-id="104e1-178">値を指定**InboundOperationType**、 **NotificationPort**、および**NotificationStatement**スキーマの生成中にプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="104e1-178">Specify a value for **InboundOperationType**, **NotificationPort**, and **NotificationStatement** binding properties while generating the schema.</span></span> <span data-ttu-id="104e1-179">このバインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter 用 Oracle Database バインド プロパティの操作](https://msdn.microsoft.com/library/dd788467.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="104e1-179">For more information about this binding property, see [Working with BizTalk Adapter for Oracle Database Binding Properties](https://msdn.microsoft.com/library/dd788467.aspx).</span></span> <span data-ttu-id="104e1-180">バインドのプロパティを指定する方法については、次を参照してください。[バインドのプロパティを指定する](https://msdn.microsoft.com/library/dd788420.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="104e1-180">For instructions on how to specify binding properties, see [Specifying Binding Properties](https://msdn.microsoft.com/library/dd788420.aspx).</span></span>  
  
2.  <span data-ttu-id="104e1-181">コントラクトの種類を選択して**サービス (入力方向の操作)**です。</span><span class="sxs-lookup"><span data-stu-id="104e1-181">Select the contract type as **Service (Inbound operations)**.</span></span>  
  
3.  <span data-ttu-id="104e1-182">スキーマを生成、**通知**操作します。</span><span class="sxs-lookup"><span data-stu-id="104e1-182">Generate schema for the **Notification** operation.</span></span>  
  
4.  <span data-ttu-id="104e1-183">コントラクトの種類を選択して**クライアント (送信操作)**です。</span><span class="sxs-lookup"><span data-stu-id="104e1-183">Select the contract type as **Client (Outbound operations)**.</span></span>  
  
5.  <span data-ttu-id="104e1-184">スキーマを生成、 **PROCESS_RECORDS**プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="104e1-184">Generate schema for the **PROCESS_RECORDS** procedure.</span></span> <span data-ttu-id="104e1-185">この手順で使用可能な**ACCOUNT_PKG**パッケージです。</span><span class="sxs-lookup"><span data-stu-id="104e1-185">This procedure is available under the **ACCOUNT_PKG** package.</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="104e1-186">メッセージとメッセージの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="104e1-186">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="104e1-187">以前に生成したスキーマには、オーケストレーション内のメッセージに対して必要な「種類」がについて説明します。</span><span class="sxs-lookup"><span data-stu-id="104e1-187">The schema that you generated earlier describes the "types" required for the messages in the orchestration.</span></span> <span data-ttu-id="104e1-188">メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。</span><span class="sxs-lookup"><span data-stu-id="104e1-188">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="104e1-189">スキーマが生成されるは、BizTalk プロジェクトのオーケストレーションの種類からのメッセージをリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="104e1-189">Once the schema is generated, you must link it to the messages from the Orchestration view of the BizTalk project.</span></span>  
  
 <span data-ttu-id="104e1-190">このトピックでは、3 つのメッセージを作成する必要があります: PROCESS_RECORDS プロシージャを実行して、プロシージャの応答を受信する Oracle データベースから通知を受け取るいずれか。</span><span class="sxs-lookup"><span data-stu-id="104e1-190">For this topic, you must create three messages—one to receive notifications from the Oracle database, one to execute the PROCESS_RECORDS procedure, and one to receive the response for the procedure.</span></span>  
  
 <span data-ttu-id="104e1-191">メッセージを作成し、それらのスキーマにリンクするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="104e1-191">Perform the following steps to create messages and link them to schema.</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="104e1-192">メッセージを作成し、スキーマにリンクするには</span><span class="sxs-lookup"><span data-stu-id="104e1-192">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="104e1-193">オーケストレーションを BizTalk プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="104e1-193">Add an orchestration to the BizTalk project.</span></span> <span data-ttu-id="104e1-194">ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックし、**追加**、クリックして**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="104e1-194">From the Solution Explorer, right-click the BizTalk project name, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="104e1-195">BizTalk オーケストレーションの名前を入力し、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="104e1-195">Type a name for the BizTalk orchestration and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="104e1-196">まだ開いていない場合は、BizTalk プロジェクトのオーケストレーション ビュー ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="104e1-196">Open the orchestration view window of the BizTalk project, if it is not already open.</span></span> <span data-ttu-id="104e1-197">をクリックして**ビュー**、 をポイント**その他のウィンドウ**、順にクリック**オーケストレーション ビュー**です。</span><span class="sxs-lookup"><span data-stu-id="104e1-197">Click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
3.  <span data-ttu-id="104e1-198">**オーケストレーション ビュー**を右クリックして**メッセージ**、クリックして**新しいメッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="104e1-198">In the **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span>  
  
4.  <span data-ttu-id="104e1-199">新しく作成されたメッセージを右クリックし [**プロパティ] ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="104e1-199">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="104e1-200">**プロパティ**ウィンドウ**Message_1**を次の操作します。</span><span class="sxs-lookup"><span data-stu-id="104e1-200">In the **Properties** pane for **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="104e1-201">プロパティ</span><span class="sxs-lookup"><span data-stu-id="104e1-201">Use this</span></span>|<span data-ttu-id="104e1-202">目的</span><span class="sxs-lookup"><span data-stu-id="104e1-202">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="104e1-203">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="104e1-203">Identifier</span></span>|<span data-ttu-id="104e1-204">「`NotifyReceive`.</span><span class="sxs-lookup"><span data-stu-id="104e1-204">Type `NotifyReceive`.</span></span>|  
    |<span data-ttu-id="104e1-205">メッセージの種類</span><span class="sxs-lookup"><span data-stu-id="104e1-205">Message Type</span></span>|<span data-ttu-id="104e1-206">ドロップダウン リストから、展開**スキーマ**を選択し、 *OracleNotifyIncremental.OracleDBBinding.Notification*ここで、 *OracleNotifyIncremental*の名前を指定します。BizTalk プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="104e1-206">From the drop-down list, expand **Schemas**, and select *OracleNotifyIncremental.OracleDBBinding.Notification*, where *OracleNotifyIncremental* is the name of your BizTalk project.</span></span> <span data-ttu-id="104e1-207">*OracleDBBinding*に対して生成されたスキーマは、**通知**操作します。</span><span class="sxs-lookup"><span data-stu-id="104e1-207">*OracleDBBinding* is the schema generated for the **Notification** operation.</span></span>|  
  
6.  <span data-ttu-id="104e1-208">手順 3 を繰り返して 2 つの新しいメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="104e1-208">Repeat step 3 to create two new messages.</span></span> <span data-ttu-id="104e1-209">**プロパティ**新しいメッセージ ウィンドウ、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="104e1-209">In the **Properties** pane for the new message, do the following:</span></span>  
  
    |<span data-ttu-id="104e1-210">識別子に設定します。</span><span class="sxs-lookup"><span data-stu-id="104e1-210">Set Identifier to</span></span>|<span data-ttu-id="104e1-211">メッセージの種類を設定</span><span class="sxs-lookup"><span data-stu-id="104e1-211">Set Message Type to</span></span>|  
    |-----------------------|-------------------------|  
    |<span data-ttu-id="104e1-212">手順</span><span class="sxs-lookup"><span data-stu-id="104e1-212">Procedure</span></span>|<span data-ttu-id="104e1-213">*OracleNotifyIncremental.OracleDBBinding1.PROCESS_RECORDS*ここで、 *OracleDBBinding1*に対して生成されたスキーマは、 **PROCESS_RECORDS**プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="104e1-213">*OracleNotifyIncremental.OracleDBBinding1.PROCESS_RECORDS*, where  *OracleDBBinding1* is the schema generated for the **PROCESS_RECORDS** procedure.</span></span>|  
    |<span data-ttu-id="104e1-214">ProcedureResponse</span><span class="sxs-lookup"><span data-stu-id="104e1-214">ProcedureResponse</span></span>|<span data-ttu-id="104e1-215">*OracleNotifyIncremental.OracleDBBinding1.PROCESS_RECORDSResponse*</span><span class="sxs-lookup"><span data-stu-id="104e1-215">*OracleNotifyIncremental.OracleDBBinding1.PROCESS_RECORDSResponse*</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="104e1-216">オーケストレーションを設定します。</span><span class="sxs-lookup"><span data-stu-id="104e1-216">Setting up the Orchestration</span></span>  
 <span data-ttu-id="104e1-217">使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の Oracle データベースから通知メッセージを受信し、通知を受信した行を更新します。</span><span class="sxs-lookup"><span data-stu-id="104e1-217">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for receiving notification messages from the Oracle database and then updating the rows for which notification was received.</span></span> <span data-ttu-id="104e1-218">このオーケストレーションでの指定した SELECT ステートメントに基づく通知メッセージを受信、 **NotificationStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="104e1-218">In this orchestration, the adapter receives the notification message based on the SELECT statement specified for the **NotificationStatement** binding property.</span></span> <span data-ttu-id="104e1-219">通知メッセージは、ファイルの場所で受信されます。</span><span class="sxs-lookup"><span data-stu-id="104e1-219">The notification message is received at a FILE location.</span></span> <span data-ttu-id="104e1-220">応答が受信されると、オーケストレーションは、通知を受信した行を更新する、PROCESS_RECORDS プロシージャを呼び出すためのメッセージを構築します。</span><span class="sxs-lookup"><span data-stu-id="104e1-220">Once the response is received, the orchestration constructs a message to invoke the PROCESS_RECORDS procedure, which updates the rows for which notification is received.</span></span> <span data-ttu-id="104e1-221">このメッセージの応答を同じファイルの場所にも受信します。</span><span class="sxs-lookup"><span data-stu-id="104e1-221">The response for this message is also received at the same FILE location.</span></span>  
  
 <span data-ttu-id="104e1-222">そのため、オーケストレーションは、次が必要があります。</span><span class="sxs-lookup"><span data-stu-id="104e1-222">So, your orchestration must contain the following:</span></span>  
  
-   <span data-ttu-id="104e1-223">一方向の WCF カスタムまたは Wcf-oracledb 通知メッセージを受信するポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="104e1-223">A one-way WCF-Custom or WCF-OracleDB receive port to receive notification messages.</span></span>  
  
-   <span data-ttu-id="104e1-224">双方向の WCF カスタムまたは Wcf-oracledb PROCESS_RECORDS プロシージャを実行するメッセージを送信するポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="104e1-224">A two-way WCF-Custom or WCF-OracleDB send port to send messages to execute the PROCESS_RECORDS procedure.</span></span>  
  
-   <span data-ttu-id="104e1-225">A**メッセージの構築**図形をオーケストレーション内での PROCESS_RECORDS プロシージャを実行する、メッセージを構築します。</span><span class="sxs-lookup"><span data-stu-id="104e1-225">A **Construct Message** shape to construct messages, to execute PROCESS_RECORDS procedure, within the orchestration.</span></span>  
  
-   <span data-ttu-id="104e1-226">ファイルは、通知メッセージと PROCESS_RECORDS プロシージャへの応答を保存するポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="104e1-226">A FILE send port to save the notification message and the response for the PROCESS_RECORDS procedure.</span></span>  
  
-   <span data-ttu-id="104e1-227">受信図形と送信図形。</span><span class="sxs-lookup"><span data-stu-id="104e1-227">Receive and send shapes.</span></span>  
  
 <span data-ttu-id="104e1-228">サンプル オーケストレーションには、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="104e1-228">A sample orchestration resembles the following.</span></span>  
  
 <span data-ttu-id="104e1-229">![Oracle から通知を受信するオーケストレーション](../../adapters-and-accelerators/adapter-oracle-database/media/cef49414-490a-4bd5-a32d-b3f4cde5950a.gif "cef49414-490a-4bd5-a32d-b3f4cde5950a")</span><span class="sxs-lookup"><span data-stu-id="104e1-229">![Orchestration to receive notifications from Oracle](../../adapters-and-accelerators/adapter-oracle-database/media/cef49414-490a-4bd5-a32d-b3f4cde5950a.gif "cef49414-490a-4bd5-a32d-b3f4cde5950a")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="104e1-230">メッセージの構築図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="104e1-230">Adding Message Shapes</span></span>  
 <span data-ttu-id="104e1-231">メッセージの構築図形のごとに、次のプロパティを指定することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="104e1-231">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="104e1-232">図形 列に表示名は、単に記載されているオーケストレーションに表示されるメッセージの構築図形の名前です。</span><span class="sxs-lookup"><span data-stu-id="104e1-232">The names listed in the Shape column are the names of the message shapes as displayed in the just-mentioned orchestration.</span></span>  
  
|<span data-ttu-id="104e1-233">図形</span><span class="sxs-lookup"><span data-stu-id="104e1-233">Shape</span></span>|<span data-ttu-id="104e1-234">図形の種類</span><span class="sxs-lookup"><span data-stu-id="104e1-234">Shape Type</span></span>|<span data-ttu-id="104e1-235">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="104e1-235">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="104e1-236">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="104e1-236">ReceiveNotification</span></span>|<span data-ttu-id="104e1-237">Receive</span><span class="sxs-lookup"><span data-stu-id="104e1-237">Receive</span></span>|<span data-ttu-id="104e1-238">-設定**名前**に*ReceiveNotification*</span><span class="sxs-lookup"><span data-stu-id="104e1-238">- Set **Name** to *ReceiveNotification*</span></span><br /><br /> <span data-ttu-id="104e1-239">-設定**アクティブ**に*は True。*</span><span class="sxs-lookup"><span data-stu-id="104e1-239">- Set **Activate** to *True*</span></span>|  
|<span data-ttu-id="104e1-240">SaveNotification</span><span class="sxs-lookup"><span data-stu-id="104e1-240">SaveNotification</span></span>|<span data-ttu-id="104e1-241">Send</span><span class="sxs-lookup"><span data-stu-id="104e1-241">Send</span></span>|<span data-ttu-id="104e1-242">-設定**名前**に*SaveNotification*</span><span class="sxs-lookup"><span data-stu-id="104e1-242">- Set **Name** to *SaveNotification*</span></span>|  
|<span data-ttu-id="104e1-243">SendProcMessage</span><span class="sxs-lookup"><span data-stu-id="104e1-243">SendProcMessage</span></span>|<span data-ttu-id="104e1-244">Send</span><span class="sxs-lookup"><span data-stu-id="104e1-244">Send</span></span>|<span data-ttu-id="104e1-245">-設定**名前**に*SendProcMessage*</span><span class="sxs-lookup"><span data-stu-id="104e1-245">- Set **Name** to *SendProcMessage*</span></span>|  
|<span data-ttu-id="104e1-246">ReceiveProcResponse</span><span class="sxs-lookup"><span data-stu-id="104e1-246">ReceiveProcResponse</span></span>|<span data-ttu-id="104e1-247">Receive</span><span class="sxs-lookup"><span data-stu-id="104e1-247">Receive</span></span>|<span data-ttu-id="104e1-248">-設定**名前**に*ReceiveProcResponse*</span><span class="sxs-lookup"><span data-stu-id="104e1-248">- Set **Name** to *ReceiveProcResponse*</span></span>|  
|<span data-ttu-id="104e1-249">SaveProcResponse</span><span class="sxs-lookup"><span data-stu-id="104e1-249">SaveProcResponse</span></span>|<span data-ttu-id="104e1-250">Send</span><span class="sxs-lookup"><span data-stu-id="104e1-250">Send</span></span>|<span data-ttu-id="104e1-251">-設定**名前**に*SaveProcResponse*</span><span class="sxs-lookup"><span data-stu-id="104e1-251">- Set **Name** to *SaveProcResponse*</span></span>|  
  
### <a name="adding-construct-message-shape"></a><span data-ttu-id="104e1-252">メッセージの構築図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="104e1-252">Adding Construct Message Shape</span></span>  
 <span data-ttu-id="104e1-253">使用することができます、**メッセージの構築**図形 PROCESS_RECORDS プロシージャを実行するオーケストレーション内で要求メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="104e1-253">You can use the **Construct Message** shape to generate a request message within the orchestration to execute the PROCESS_RECORDS procedure.</span></span> <span data-ttu-id="104e1-254">これを行うには、追加する必要があります、**メッセージの構築**図形という、**メッセージの割り当て**図形をオーケストレーションにします。</span><span class="sxs-lookup"><span data-stu-id="104e1-254">To do so, you must add a **Construct Message** shape and within that a **Message Assignment** shape to your orchestration.</span></span> <span data-ttu-id="104e1-255">この例で、**メッセージの割り当て**図形は、プロシージャを実行する Oracle データベースに送信されるメッセージを生成するコードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="104e1-255">For this example, the **Message Assignment** shape invokes code that generates a message that is sent to the Oracle database to execute the procedure.</span></span> <span data-ttu-id="104e1-256">**メッセージの割り当て**図形も、Oracle データベースに送信されるメッセージのアクションを設定します。</span><span class="sxs-lookup"><span data-stu-id="104e1-256">The **Message Assignment** shape also sets the action for the message to be sent to the Oracle database.</span></span>  
  
 <span data-ttu-id="104e1-257">メッセージの構築図形、設定、**メッセージ構築**プロパティを**プロシージャ**です。</span><span class="sxs-lookup"><span data-stu-id="104e1-257">For the construct message shape, set the **Message Constructed** property to **Procedure**.</span></span>  
  
 <span data-ttu-id="104e1-258">応答を生成するコードは、BizTalk プロジェクトと同じ Visual Studio ソリューションの一部になります。</span><span class="sxs-lookup"><span data-stu-id="104e1-258">The code to generate the response could be part of the same Visual Studio solution as your BizTalk project.</span></span> <span data-ttu-id="104e1-259">応答メッセージを生成するためのサンプル コードは、次のように検索します。</span><span class="sxs-lookup"><span data-stu-id="104e1-259">A sample code for generating a response message looks like this.</span></span>  
  
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
            XmlFileLocation = "C:\\TestLocation\\MessageIn";  
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
  
 <span data-ttu-id="104e1-260">要求メッセージを生成できるように上記のコード例でする必要があります (PROCESS_RECORDS プロシージャ) の場合、XML 要求メッセージの指定した場所に、`XmlFileLocation`変数。</span><span class="sxs-lookup"><span data-stu-id="104e1-260">For the above code excerpt to be able to generate a request message, you must have an XML request message (for the PROCESS_RECORDS procedure) in the location specified for the `XmlFileLocation` variable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="104e1-261">プロジェクトをビルドした後、MessageCreator.dll はプロジェクト ディレクトリに作成されます。</span><span class="sxs-lookup"><span data-stu-id="104e1-261">After you build the project, MessageCreator.dll will be created in the project directory.</span></span> <span data-ttu-id="104e1-262">グローバル アセンブリ キャッシュ (GAC) には、この DLL を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="104e1-262">You must add this DLL to the global assembly cache (GAC).</span></span> <span data-ttu-id="104e1-263">また、BizTalk プロジェクトに参照として、MessageCreator.dll を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="104e1-263">Also, you must add the MessageCreator.dll as a reference in the BizTalk project.</span></span>  
  
 <span data-ttu-id="104e1-264">次のコードを呼び出すには、次の式を追加、**メッセージの割り当て**図形とメッセージのアクションを設定します。</span><span class="sxs-lookup"><span data-stu-id="104e1-264">Add the following expression to invoke this code from the **Message Assignment** shape and to set the action for message.</span></span> <span data-ttu-id="104e1-265">式を追加するにはダブルクリック、**メッセージの割り当て**図形式エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="104e1-265">To add an expression, double-click the **Message Assignment** shape to open the Expression Editor.</span></span>  
  
```  
Procedure = SampleMessageCreator.SampleMessageCreator.XMLMessageCreator();  
Procedure(WCF.Action) = "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/PROCESS_RECORDS";  
```  
  
### <a name="adding-ports"></a><span data-ttu-id="104e1-266">ポートの追加</span><span class="sxs-lookup"><span data-stu-id="104e1-266">Adding Ports</span></span>  
 <span data-ttu-id="104e1-267">論理ポートごとに、次のプロパティを指定することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="104e1-267">Make sure you specify the following properties for each of the logical ports.</span></span> <span data-ttu-id="104e1-268">ポート列に表示される名前は、オーケストレーションで表示されているポートの名前です。</span><span class="sxs-lookup"><span data-stu-id="104e1-268">The names listed in the Port column are the names of the ports as displayed in the orchestration.</span></span>  
  
|<span data-ttu-id="104e1-269">ポート</span><span class="sxs-lookup"><span data-stu-id="104e1-269">Port</span></span>|<span data-ttu-id="104e1-270">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="104e1-270">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="104e1-271">OracleNotifyPort</span><span class="sxs-lookup"><span data-stu-id="104e1-271">OracleNotifyPort</span></span>|<span data-ttu-id="104e1-272">-設定**識別子**に*OracleNotifyPort*</span><span class="sxs-lookup"><span data-stu-id="104e1-272">- Set **Identifier** to *OracleNotifyPort*</span></span><br /><br /> <span data-ttu-id="104e1-273">-設定**型**に*OracleNotifyPortType*</span><span class="sxs-lookup"><span data-stu-id="104e1-273">- Set **Type** to *OracleNotifyPortType*</span></span><br /><br /> <span data-ttu-id="104e1-274">-設定**通信パターン**に*一方向*</span><span class="sxs-lookup"><span data-stu-id="104e1-274">- Set **Communication Pattern** to *One-Way*</span></span><br /><br /> <span data-ttu-id="104e1-275">-設定**通信方向**に*受信*</span><span class="sxs-lookup"><span data-stu-id="104e1-275">- Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="104e1-276">SaveMessagePort</span><span class="sxs-lookup"><span data-stu-id="104e1-276">SaveMessagePort</span></span>|<span data-ttu-id="104e1-277">-設定**識別子**に*SaveMessagePort*</span><span class="sxs-lookup"><span data-stu-id="104e1-277">- Set **Identifier** to *SaveMessagePort*</span></span><br /><br /> <span data-ttu-id="104e1-278">-設定**型**に*SaveMessagePortType*</span><span class="sxs-lookup"><span data-stu-id="104e1-278">- Set **Type** to *SaveMessagePortType*</span></span><br /><br /> <span data-ttu-id="104e1-279">-設定**通信パターン**に*一方向*</span><span class="sxs-lookup"><span data-stu-id="104e1-279">- Set **Communication Pattern** to *One-Way*</span></span><br /><br /> <span data-ttu-id="104e1-280">-設定**通信方向**に*送信*</span><span class="sxs-lookup"><span data-stu-id="104e1-280">- Set **Communication Direction** to *Send*</span></span><br /><br /> <span data-ttu-id="104e1-281">操作を作成する*通知*です。</span><span class="sxs-lookup"><span data-stu-id="104e1-281">- Create an operation *Notify*.</span></span> <span data-ttu-id="104e1-282">この操作は、通知メッセージに使用されます。</span><span class="sxs-lookup"><span data-stu-id="104e1-282">This operation is used for notification messages.</span></span><br /><br /> <span data-ttu-id="104e1-283">操作を作成する*プロシージャ*です。</span><span class="sxs-lookup"><span data-stu-id="104e1-283">- Create an operation *Procedure*.</span></span> <span data-ttu-id="104e1-284">この操作は、応答メッセージを使用します。</span><span class="sxs-lookup"><span data-stu-id="104e1-284">This operation is used for select response messages.</span></span>|  
|<span data-ttu-id="104e1-285">OracleOutboundPort</span><span class="sxs-lookup"><span data-stu-id="104e1-285">OracleOutboundPort</span></span>|<span data-ttu-id="104e1-286">-設定**識別子**に*OracleOutboundPort*</span><span class="sxs-lookup"><span data-stu-id="104e1-286">- Set **Identifier** to *OracleOutboundPort*</span></span><br /><br /> <span data-ttu-id="104e1-287">-設定**型**に*OracleOutboundPortType*</span><span class="sxs-lookup"><span data-stu-id="104e1-287">- Set **Type** to *OracleOutboundPortType*</span></span><br /><br /> <span data-ttu-id="104e1-288">-設定**通信パターン**に*要求-応答*</span><span class="sxs-lookup"><span data-stu-id="104e1-288">- Set **Communication Pattern** to *Request-Response*</span></span><br /><br /> <span data-ttu-id="104e1-289">-設定**通信方向**に*送受信*</span><span class="sxs-lookup"><span data-stu-id="104e1-289">- Set **Communication Direction** to *Send-Receive*</span></span>|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a><span data-ttu-id="104e1-290">アクション図形のメッセージを指定し、ポートに接続</span><span class="sxs-lookup"><span data-stu-id="104e1-290">Specify Messages for Action Shapes and Connect to Ports</span></span>  
 <span data-ttu-id="104e1-291">次の表は、プロパティとアクション図形のメッセージを指定して、メッセージ、ポートにリンクを設定する必要があります、値を指定します。</span><span class="sxs-lookup"><span data-stu-id="104e1-291">The following table specifies the properties and their values that you should set to specify messages for action shapes and to link the messages to the ports.</span></span> <span data-ttu-id="104e1-292">図形 列に表示名は、既に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。</span><span class="sxs-lookup"><span data-stu-id="104e1-292">The names listed in the Shape column are the names of the message shapes as displayed in the orchestration mentioned earlier.</span></span>  
  
|<span data-ttu-id="104e1-293">図形</span><span class="sxs-lookup"><span data-stu-id="104e1-293">Shape</span></span>|<span data-ttu-id="104e1-294">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="104e1-294">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="104e1-295">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="104e1-295">ReceiveNotification</span></span>|<span data-ttu-id="104e1-296">-設定**メッセージ**に*NotifyReceive*</span><span class="sxs-lookup"><span data-stu-id="104e1-296">- Set **Message** to *NotifyReceive*</span></span><br /><br /> <span data-ttu-id="104e1-297">-設定**操作**に*OracleNotifyPort.Notify.Request*</span><span class="sxs-lookup"><span data-stu-id="104e1-297">- Set **Operation** to *OracleNotifyPort.Notify.Request*</span></span>|  
|<span data-ttu-id="104e1-298">SaveNotification</span><span class="sxs-lookup"><span data-stu-id="104e1-298">SaveNotification</span></span>|<span data-ttu-id="104e1-299">-設定**メッセージ**に*NotifyReceive*</span><span class="sxs-lookup"><span data-stu-id="104e1-299">- Set **Message** to *NotifyReceive*</span></span><br /><br /> <span data-ttu-id="104e1-300">-設定**操作**に*SaveMessagePort.Notify.Request*</span><span class="sxs-lookup"><span data-stu-id="104e1-300">- Set **Operation** to *SaveMessagePort.Notify.Request*</span></span>|  
|<span data-ttu-id="104e1-301">SendProcMessage</span><span class="sxs-lookup"><span data-stu-id="104e1-301">SendProcMessage</span></span>|<span data-ttu-id="104e1-302">-設定**メッセージ**に*プロシージャ*</span><span class="sxs-lookup"><span data-stu-id="104e1-302">- Set **Message** to *Procedure*</span></span><br /><br /> <span data-ttu-id="104e1-303">-設定**操作**に*OracleOutboundPort.Procedure.Request*</span><span class="sxs-lookup"><span data-stu-id="104e1-303">- Set **Operation** to *OracleOutboundPort.Procedure.Request*</span></span>|  
|<span data-ttu-id="104e1-304">ReceiveProcResponse</span><span class="sxs-lookup"><span data-stu-id="104e1-304">ReceiveProcResponse</span></span>|<span data-ttu-id="104e1-305">-設定**メッセージ**に*ProcedureResponse*</span><span class="sxs-lookup"><span data-stu-id="104e1-305">- Set **Message** to *ProcedureResponse*</span></span><br /><br /> <span data-ttu-id="104e1-306">-設定**操作**に*OracleOutboundPort.Procedure.Response*</span><span class="sxs-lookup"><span data-stu-id="104e1-306">- Set **Operation** to *OracleOutboundPort.Procedure.Response*</span></span>|  
|<span data-ttu-id="104e1-307">SaveProcResponse</span><span class="sxs-lookup"><span data-stu-id="104e1-307">SaveProcResponse</span></span>|<span data-ttu-id="104e1-308">-設定**メッセージ**に*ProedureResponse*</span><span class="sxs-lookup"><span data-stu-id="104e1-308">- Set **Message** to *ProedureResponse*</span></span><br /><br /> <span data-ttu-id="104e1-309">-設定**操作**に*SaveMessagePort.Procedure.Request*</span><span class="sxs-lookup"><span data-stu-id="104e1-309">- Set **Operation** to *SaveMessagePort.Procedure.Request*</span></span>|  
  
 <span data-ttu-id="104e1-310">これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。</span><span class="sxs-lookup"><span data-stu-id="104e1-310">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="104e1-311">今すぐ BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="104e1-311">You must now build the BizTalk solution and deploy it to a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="104e1-312">詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。</span><span class="sxs-lookup"><span data-stu-id="104e1-312">For more information, see [Building and Running Orchestrations](../../core/building-and-running-orchestrations.md).</span></span>  
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="104e1-313">BizTalk アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="104e1-313">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="104e1-314">以前に作成したオーケストレーションが下に表示、BizTalk プロジェクトを配置した後、**オーケストレーション**ペインで、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="104e1-314">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the **Orchestrations** pane in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="104e1-315">使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="104e1-315">You must use the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to configure the application.</span></span> <span data-ttu-id="104e1-316">チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。</span><span class="sxs-lookup"><span data-stu-id="104e1-316">For a walkthrough, see [Walkthrough: Deploying a Basic BizTalk Application](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).</span></span>
  
 <span data-ttu-id="104e1-317">アプリケーションの構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="104e1-317">Configuring an application involves:</span></span>  
  
-   <span data-ttu-id="104e1-318">アプリケーションのホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="104e1-318">Selecting a host for the application.</span></span>  
  
-   <span data-ttu-id="104e1-319">物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="104e1-319">Mapping the ports that you created in your orchestration to physical ports in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="104e1-320">このオーケストレーションの次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="104e1-320">For this orchestration you must:</span></span>  
  
    -   <span data-ttu-id="104e1-321">物理 Wcf-custom を定義するか、Wcf-oracledb 一方向の受信ポートです。</span><span class="sxs-lookup"><span data-stu-id="104e1-321">Define a physical WCF-Custom or WCF-OracleDB one-way receive port.</span></span> <span data-ttu-id="104e1-322">このポートは、Oracle データベースからの通知をリッスンします。</span><span class="sxs-lookup"><span data-stu-id="104e1-322">This port listens for notifications coming from the Oracle database.</span></span> <span data-ttu-id="104e1-323">受信ポートを作成する方法についてを参照してください[Oracle データベース アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="104e1-323">For information about how to create receive ports, see [Manually configure a physical port binding to the Oracle Database Adapter](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md).</span></span> <span data-ttu-id="104e1-324">受信ポートのバインドのプロパティを指定することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="104e1-324">Make sure you specify the following binding properties for the receive port.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="104e1-325">デザイン時のバインドのプロパティを指定した場合、この手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="104e1-325">You do not need to perform this step if you specified the binding properties at design-time.</span></span> <span data-ttu-id="104e1-326">このような場合は、することができます、受信ポートを作成、必要なバインド プロパティを設定、によって作成されたバインド ファイルをインポートすることによって、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="104e1-326">In such a case, you can create a receive port, with the required binding properties set, by importing the binding file created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span> <span data-ttu-id="104e1-327">詳細については、次を参照してください。 [Oracle データベースへのポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="104e1-327">For more information see [Configure a physical port binding using a port binding file to Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).</span></span>  
  
        |<span data-ttu-id="104e1-328">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="104e1-328">Binding Property</span></span>|<span data-ttu-id="104e1-329">値</span><span class="sxs-lookup"><span data-stu-id="104e1-329">Value</span></span>|  
        |----------------------|-----------|  
        |<span data-ttu-id="104e1-330">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="104e1-330">**InboundOperationType**</span></span>|<span data-ttu-id="104e1-331">これを設定して**通知**です。</span><span class="sxs-lookup"><span data-stu-id="104e1-331">Set this to **Notification**.</span></span>|  
        |<span data-ttu-id="104e1-332">**NotificationPort**</span><span class="sxs-lookup"><span data-stu-id="104e1-332">**NotificationPort**</span></span>|<span data-ttu-id="104e1-333">ODP.NET が Oracle データベースからデータベースの変更通知をリッスンするように開く必要があるポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="104e1-333">Specifies the port number that ODP.NET must open to listen for database change notification from Oracle database.</span></span> <span data-ttu-id="104e1-334">これは、Windows ファイアウォールの例外一覧に追加する必要があります同じポート番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="104e1-334">Set this to the same port number that you must have added to the Windows Firewall exceptions list.</span></span> <span data-ttu-id="104e1-335">Windows ファイアウォールの例外リストにポートを追加する方法については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)です。</span><span class="sxs-lookup"><span data-stu-id="104e1-335">For instructions on how to add ports to Windows Firewall exceptions list, see [http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959).</span></span><br /><br /> <span data-ttu-id="104e1-336">**重要:**これを既定値は-1 を設定する場合は、通知メッセージを受け取るための Windows ファイアウォールを完全に無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="104e1-336">**Important:** If you set this to the default value of -1, you will have to completely disable Windows Firewall to receive notification messages.</span></span>|  
        |<span data-ttu-id="104e1-337">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="104e1-337">**NotificationStatement**</span></span>|<span data-ttu-id="104e1-338">これを設定します。</span><span class="sxs-lookup"><span data-stu-id="104e1-338">Set this to:</span></span><br /><br /> `SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’`<br /><br /> <span data-ttu-id="104e1-339">**注:**スキーマ名とテーブル名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="104e1-339">**Note:** You must specify the table name along with the schema name.</span></span> <span data-ttu-id="104e1-340">たとえば、 `SCOTT.ACCOUNTACTIVITY`のようにします。</span><span class="sxs-lookup"><span data-stu-id="104e1-340">For example, `SCOTT.ACCOUNTACTIVITY`.</span></span>|  
        |<span data-ttu-id="104e1-341">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="104e1-341">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="104e1-342">これを設定して**True**です。</span><span class="sxs-lookup"><span data-stu-id="104e1-342">Set this to **True**.</span></span>|  
  
         <span data-ttu-id="104e1-343">異なるバインディングのプロパティの詳細については、次を参照してください。 [BizTalk Adapter 用 Oracle Database バインド プロパティの操作](https://msdn.microsoft.com/library/dd788467.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="104e1-343">For more information about the different binding properties, see [Working with BizTalk Adapter for Oracle Database Binding Properties](https://msdn.microsoft.com/library/dd788467.aspx).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="104e1-344">使用して受信操作の実行中に、トランザクション分離レベルとトランザクションのタイムアウトを構成することをお勧め、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="104e1-344">We recommend configuring the transaction isolation level and the transaction timeout while performing inbound operations using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="104e1-345">サービスを追加することで、Wcf-custom または Wcf-oracledb を構成するときに動作の受信ポートを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="104e1-345">You can do so by adding the service behavior while configuring the WCF-Custom or WCF-OracleDB receive port.</span></span> <span data-ttu-id="104e1-346">サービスの動作を追加する方法については、次を参照してください。[トランザクション分離レベルの構成とトランザクションのタイムアウト](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md)です。</span><span class="sxs-lookup"><span data-stu-id="104e1-346">For instruction on how to add the service behavior, see [Configure Transaction Isolation Level and Transaction Timeout](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md).</span></span>  
  
    -   <span data-ttu-id="104e1-347">PROCESS_REOCRDS プロシージャを実行する Oracle データベースにメッセージを送信する物理 Wcf-custom または Wcf-oracledb 送信ポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="104e1-347">Define a physical WCF-Custom or WCF-OracleDB send port to send messages to the Oracle database to execute the PROCESS_REOCRDS procedure.</span></span> <span data-ttu-id="104e1-348">送信ポートでアクションを指定することもあります。</span><span class="sxs-lookup"><span data-stu-id="104e1-348">You must also specify the action in the send port.</span></span>  
  
    -   <span data-ttu-id="104e1-349">ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが Oracle データベースからメッセージをドロップ場所に場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="104e1-349">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the messages from the Oracle database.</span></span> <span data-ttu-id="104e1-350">これらは、Oracle データベースから受信した通知メッセージと WCF カスタムを通じて実行 PROCESS_RECORDS プロシージャのメッセージか Wcf-oracledb 送信ポート。</span><span class="sxs-lookup"><span data-stu-id="104e1-350">These will be the notification messages received from the Oracle database and messages for the PROCESS_RECORDS procedure you execute through the WCF-Custom or WCF-OracleDB send port.</span></span>  
  
## <a name="starting-the-application"></a><span data-ttu-id="104e1-351">アプリケーションの起動</span><span class="sxs-lookup"><span data-stu-id="104e1-351">Starting the Application</span></span>  
 <span data-ttu-id="104e1-352">Oracle データベースから通知メッセージを受信して、PROCESS_RECORDS 手順を実行するために、BizTalk アプリケーションを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="104e1-352">You must start the BizTalk application for receiving notification messages from the Oracle database and for executing the PROCESS_RECORDS procedure.</span></span> <span data-ttu-id="104e1-353">BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。</span><span class="sxs-lookup"><span data-stu-id="104e1-353">For instructions on starting a BizTalk application, see [How to Start an Orchestration](../../core/how-to-start-an-orchestration.md).</span></span>  
  
 <span data-ttu-id="104e1-354">この段階で確認します。</span><span class="sxs-lookup"><span data-stu-id="104e1-354">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="104e1-355">Wcf-custom または Wcf-oracledb 一方向の受信ポートで、データベースが実行されている Oracle から通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="104e1-355">The WCF-Custom or WCF-OracleDB one-way receive port, which receives the notification messages from the Oracle database is running.</span></span>  
  
-   <span data-ttu-id="104e1-356">PROCESS_RECORDS プロシージャを実行する Wcf-custom または Wcf-oracledb 送信ポートが実行されています。</span><span class="sxs-lookup"><span data-stu-id="104e1-356">The WCF-Custom or WCF-OracleDB send port to execute the PROCESS_RECORDS procedure is running.</span></span>  
  
-   <span data-ttu-id="104e1-357">Oracle データベースからメッセージを受信する FILE 送信ポートが実行されています。</span><span class="sxs-lookup"><span data-stu-id="104e1-357">The FILE send port, which receives messages from the Oracle database, is running.</span></span>  
  
-   <span data-ttu-id="104e1-358">操作の BizTalk オーケストレーションが実行されています。</span><span class="sxs-lookup"><span data-stu-id="104e1-358">The BizTalk orchestration for the operation is running.</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="104e1-359">操作の実行</span><span class="sxs-lookup"><span data-stu-id="104e1-359">Executing the Operation</span></span>  
 <span data-ttu-id="104e1-360">ACCOUNTACTIVITY テーブルが既にレコードの一部であると仮定します。</span><span class="sxs-lookup"><span data-stu-id="104e1-360">Assume that the ACCOUNTACTIVITY table already has some records.</span></span> <span data-ttu-id="104e1-361">また、C:\TestLocation\MessageIn で使用される PROCESS_RECORDS プロシージャを実行する XML メッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="104e1-361">Also, make sure the XML message to execute PROCESS_RECORDS procedure is available at C:\TestLocation\MessageIn.</span></span> <span data-ttu-id="104e1-362">XML ファイルは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="104e1-362">The XML file should resemble the following:</span></span>  
  
```  
<PROCESS_RECORDS xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG"/>  
```  
  
 <span data-ttu-id="104e1-363">BizTalk オーケストレーションが開始されると、次の一連のアクションが実行、同じ順序で。</span><span class="sxs-lookup"><span data-stu-id="104e1-363">Once the BizTalk orchestration is started, the following set of actions take place, in the same sequence:</span></span>  
  
-   <span data-ttu-id="104e1-364">アダプターは、次のような通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="104e1-364">The adapter receives a notification message that resembles the following:</span></span>  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?\>   
    <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
      <Info>ListenerStarted</Info>   
      <Source>OracleDBBinding</Source>   
      <Type>Startup</Type>   
    </Notification>  
    ```  
  
     <span data-ttu-id="104e1-365">このメッセージは、通知メッセージを受信する受信ポートが開始されたことを通知します。</span><span class="sxs-lookup"><span data-stu-id="104e1-365">This message notifies that the receive port for receiving the notification messages is started.</span></span> <span data-ttu-id="104e1-366">なおの値、`<Info>`要素は、"ListnerStarted"です。</span><span class="sxs-lookup"><span data-stu-id="104e1-366">Note that the value for the `<Info>` element is “ListnerStarted”.</span></span>  
  
-   <span data-ttu-id="104e1-367">アダプターでは、PROCESS_RECORDS プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="104e1-367">The adapter executes the PROCESS_RECORDS procedure.</span></span> <span data-ttu-id="104e1-368">Oracle データベースから次の応答では、プロシージャのです。</span><span class="sxs-lookup"><span data-stu-id="104e1-368">The next response from the Oracle database is for the procedure.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <PROCESS_RECORDSResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
      <TABLE_DATA>  
        <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
          <xs:element msdata:IsDataSet="true" name="NewDataSet">  
            <xs:complexType>  
              <xs:sequence>  
                <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                  <xs:complexType>  
                    <xs:sequence>  
                      <xs:element minOccurs="0" name="TID" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="ACCOUNT" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="PROCESSED" type="xs:string" />   
                    </xs:sequence>  
                  </xs:complexType>  
                </xs:element>  
              </xs:sequence>  
            </xs:complexType>  
          </xs:element>  
        </xs:schema>  
        <diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
        <NewDataSet xmlns="">  
          <NewTable>  
            <TID>1</TID>   
            <ACCOUNT>100001</ACCOUNT>   
            <PROCESSED>n</PROCESSED>   
          </NewTable>  
          <NewTable>  
            ......  
            ......  
          </NewTable>  
          ......  
          ......  
        </NewDataSet>  
        </diffgr:diffgram>  
      </TABLE_DATA>  
    </PROCESS_RECORDSResponse>  
    ```  
  
     <span data-ttu-id="104e1-369">これは、PROCESS_RECORDS 手順の一部として、SELECT ステートメントの実行の応答です。</span><span class="sxs-lookup"><span data-stu-id="104e1-369">This is the response for the SELECT statement execute as part of the PROCESS_RECORDS procedure.</span></span>  
  
-   <span data-ttu-id="104e1-370">PROCESS_RECORDS プロシージャでは、'y' に処理を設定する行も更新します。</span><span class="sxs-lookup"><span data-stu-id="104e1-370">The PROCESS_RECORDS procedure also updates the rows to set PROCESSED to ‘y’.</span></span> <span data-ttu-id="104e1-371">そのため、アダプターは、更新操作に別の通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="104e1-371">Hence, the adapter receives another notification for the Update operation.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification/">  
      <Details>  
        <NotificationDetails>  
          <ResourceName>SCOTT.ACCOUNTACTIVITY</ResourceName>   
          <Info>32</Info>   
          <QueryId>0</QueryId>   
        </NotificationDetails>  
      </Details>  
      <Info>Update</Info>   
      <ResourceNames>  
        <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">SCOTT.ACCOUNTACTIVITY</string>   
      </ResourceNames>  
      <Source>Data</Source>   
      <Type>Change</Type>   
    </Notification>  
    ```  
  
     <span data-ttu-id="104e1-372">なお、`Info`要素には、「Update」が含まれています。</span><span class="sxs-lookup"><span data-stu-id="104e1-372">Note that the `Info` element contains “Update”.</span></span>  
  
-   <span data-ttu-id="104e1-373">2 番目の通知後、アダプターは再度 PROCESS_RECORDS プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="104e1-373">After the second notification, the adapter again executes the PROCESS_RECORDS procedure.</span></span> <span data-ttu-id="104e1-374">ただし、今すぐに処理された列が設定されているレコードがないため ' n '、プロシージャは、次のような空の応答を返します。</span><span class="sxs-lookup"><span data-stu-id="104e1-374">However, now because there are no records where PROCESSED column is set to ‘n’, the procedure returns an empty response resembling the following.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <PROCESS_RECORDSResponse xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG">  
      <TABLE_DATA>  
        <xs:schema id="NewDataSet" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
          <xs:element msdata:IsDataSet="true" name="NewDataSet">  
            <xs:complexType>  
              <xs:sequence>  
                <xs:element minOccurs="0" maxOccurs="unbounded" name="NewTable">  
                  <xs:complexType>  
                    <xs:sequence>  
                      <xs:element minOccurs="0" name="TID" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="ACCOUNT" type="xs:decimal" />   
                      <xs:element minOccurs="0" name="PROCESSED" type="xs:string" />   
                    </xs:sequence>  
                  </xs:complexType>  
                </xs:element>  
              </xs:sequence>  
            </xs:complexType>  
          </xs:element>  
        </xs:schema>  
        <diffgr:diffgram xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
          <NewDataSet xmlns="" />   
        </diffgr:diffgram>  
      </TABLE_DATA>  
    </PROCESS_RECORDSResponse>  
    ```  
  
## <a name="best-practices"></a><span data-ttu-id="104e1-375">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="104e1-375">Best Practices</span></span>  
 <span data-ttu-id="104e1-376">展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="104e1-376">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the binding file.</span></span> <span data-ttu-id="104e1-377">バインド ファイルを生成したできるように、送信ポートを作成し、同じオーケストレーション用のポートを受信する必要はありません、ファイルから構成設定をインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="104e1-377">Once you generate a binding file, you can import the configuration settings from the file, so that you do not need to create the send ports and receive ports for the same orchestration.</span></span> <span data-ttu-id="104e1-378">バインド ファイルの詳細については、次を参照してください。 [Oracle データベース アダプターの再利用バインド](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)です。</span><span class="sxs-lookup"><span data-stu-id="104e1-378">For more information about binding files, see [Reuse Oracle Database Adapter bindings](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="104e1-379">参照</span><span class="sxs-lookup"><span data-stu-id="104e1-379">See Also</span></span>  
 [<span data-ttu-id="104e1-380">BizTalk Server を使用して Oracle データベースの変更通知を受け取る</span><span class="sxs-lookup"><span data-stu-id="104e1-380">Receiving Oracle Database Change Notifications Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)