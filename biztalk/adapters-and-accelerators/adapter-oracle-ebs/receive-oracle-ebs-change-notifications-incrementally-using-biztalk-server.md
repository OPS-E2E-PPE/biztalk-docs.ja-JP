---
title: 段階的に BizTalk Server を使用して Oracle E-business Suite の変更通知の受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63dbeacc-ecde-497d-b12d-d5f9944a33f0
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37c596a5a383f55f38f90a367caae45a4ce3ec0e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004852"
---
# <a name="receive-oracle-e-business-suite-change-notifications-incrementally-using-biztalk-server"></a><span data-ttu-id="120ae-102">段階的に BizTalk Server を使用して Oracle E-business Suite の変更通知を受け取る</span><span class="sxs-lookup"><span data-stu-id="120ae-102">Receive Oracle E-Business Suite change notifications incrementally using BizTalk Server</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="120ae-103">説明を簡潔にするため、このトピックには、段階的に通知を受信する方法のみについて説明します。</span><span class="sxs-lookup"><span data-stu-id="120ae-103">For the sake of brevity, this topic only describes how to receive notifications incrementally.</span></span> <span data-ttu-id="120ae-104">ビジネスのシナリオで、オーケストレーションは理想的には受信した通知メッセージの種類を抽出し、後続の操作を実行するためのロジックを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="120ae-104">In business scenarios, the orchestration must ideally include the logic to extract the kind of notification message received and then perform any subsequent operations.</span></span> <span data-ttu-id="120ae-105">つまり、このトピックで説明されているオーケストレーションで説明されているオーケストレーションの上に構築する必要があります[Oracle E-business Suite で特定のタスクを実行するプロセスの通知メッセージ](../../adapters-and-accelerators/adapter-oracle-ebs/process-notification-messages-to-complete-specific-tasks-in-oracle-ebs.md)します。</span><span class="sxs-lookup"><span data-stu-id="120ae-105">In other words, the orchestration described in this topic must be built on top of the orchestration described in [Process Notification Messages to Complete Specific Tasks in Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/process-notification-messages-to-complete-specific-tasks-in-oracle-ebs.md).</span></span>  
  
 <span data-ttu-id="120ae-106">このトピックでは、構成する方法を示します、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle から差分クエリ通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="120ae-106">This topic demonstrates how to configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive incremental query notification messages from Oracle.</span></span> <span data-ttu-id="120ae-107">インクリメンタル通知を示すには、テーブル、ACCOUNTACTIVITY、「処理済み」列を含むについて考えます。</span><span class="sxs-lookup"><span data-stu-id="120ae-107">To demonstrate incremental notifications, we consider a table, ACCOUNTACTIVITY, with a “Processed” column.</span></span> <span data-ttu-id="120ae-108">「処理済み」列の値設定してこのテーブルに新しいレコードが挿入されると、' n ' です。</span><span class="sxs-lookup"><span data-stu-id="120ae-108">When a new record is inserted to this table, the value of the “Processed” column is set to ‘n’.</span></span> <span data-ttu-id="120ae-109">次の手順に従ってインクリメンタル通知を受信するアダプターを構成できます。</span><span class="sxs-lookup"><span data-stu-id="120ae-109">You can configure the adapter to receive incremental notifications by doing the following:</span></span>  
  
- <span data-ttu-id="120ae-110">として「処理済み」列が含まれるすべてのレコードを取得する SELECT ステートメントを使用して通知を登録 'n' です。</span><span class="sxs-lookup"><span data-stu-id="120ae-110">Register for notifications using a SELECT statement that retrieves all records that have “Processed” column as ‘n’.</span></span> <span data-ttu-id="120ae-111">SELECT ステートメントを指定することによって行うことができます、 **NotificationStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="120ae-111">You can do so by specifying the SELECT statement for the **NotificationStatement** binding property.</span></span>  
  
- <span data-ttu-id="120ae-112">行のために通知して、"y"を「処理済み」列を更新します。</span><span class="sxs-lookup"><span data-stu-id="120ae-112">For rows which have been notified for, update the “Processed” column to ‘y’.</span></span>  
  
  <span data-ttu-id="120ae-113">このトピックでは、BizTalk オーケストレーションを作成してこれを実現する BizTalk アプリケーションを構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="120ae-113">This topic demonstrates how to create a BizTalk orchestration and configure a BizTalk application to achieve this.</span></span>  
  
## <a name="configuring-notifications-with-the-oracle-e-business-adapter-binding-properties"></a><span data-ttu-id="120ae-114">Oracle E-business アダプターのバインドのプロパティと通知の構成</span><span class="sxs-lookup"><span data-stu-id="120ae-114">Configuring Notifications with the Oracle E-Business Adapter Binding Properties</span></span>  
 <span data-ttu-id="120ae-115">次の表にまとめたものです、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite から通知を受け取る構成に使用するプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="120ae-115">The table below summarizes the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding properties that you use to configure receiving notifications from Oracle E-Business Suite.</span></span> <span data-ttu-id="120ae-116">受信ポートを構成するときにこれらのバインドのプロパティを指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="120ae-116">You must specify these binding properties while configuring the receive port in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="120ae-117">スキーマを生成するときに、これらのバインドのプロパティを指定することができます、**通知**は必須でない場合でも、操作します。</span><span class="sxs-lookup"><span data-stu-id="120ae-117">You may choose to specify these binding properties when generating the schema for the **Notification** operation, even though it is not mandatory.</span></span> <span data-ttu-id="120ae-118">ポートのバインド ファイルをこのようにする場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]メタデータの生成の一部にもバインドのプロパティで指定する値が含まれているが生成されます。</span><span class="sxs-lookup"><span data-stu-id="120ae-118">If you do so, the port binding file that the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] generates as part of the metadata generation also contains the values you specify for the binding properties.</span></span> <span data-ttu-id="120ae-119">後でこのバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロパティは既に設定されています。 バインドで wcf-custom または Wcf-oracleebs を作成する管理コンソールの受信ポート。</span><span class="sxs-lookup"><span data-stu-id="120ae-119">You can later import this binding file in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create the WCF-custom or WCF-OracleEBS receive port with the binding properties already set.</span></span> <span data-ttu-id="120ae-120">バインド ファイルを使用して受信ポートを作成する方法の詳細については、次を参照してください。 [Oracle E-business Suite へのポート バインド ファイルを、物理ポートを使用してバインディングを構成](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)します。</span><span class="sxs-lookup"><span data-stu-id="120ae-120">For more information about creating a receive port using the binding file, see [Configure a Physical Port Binding Using a Port Binding File to Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md).</span></span>  
  
|<span data-ttu-id="120ae-121">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="120ae-121">Binding Property</span></span>|<span data-ttu-id="120ae-122">説明</span><span class="sxs-lookup"><span data-stu-id="120ae-122">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="120ae-123">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="120ae-123">**InboundOperationType**</span></span>|<span data-ttu-id="120ae-124">実行する受信操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="120ae-124">Specifies the inbound operation that you want to perform.</span></span> <span data-ttu-id="120ae-125">通知メッセージを受信するこれを設定**通知**します。</span><span class="sxs-lookup"><span data-stu-id="120ae-125">To receive notification messages, set this to **Notification**.</span></span>|  
|<span data-ttu-id="120ae-126">**NotificationPort**</span><span class="sxs-lookup"><span data-stu-id="120ae-126">**NotificationPort**</span></span>|<span data-ttu-id="120ae-127">Oracle データベースからのデータベース変更通知をリッスンする ODP.NET を開く必要があるポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="120ae-127">Specifies the port number that ODP.NET must open to listen for database change notification from Oracle database.</span></span>|  
|<span data-ttu-id="120ae-128">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="120ae-128">**NotificationStatement**</span></span>|<span data-ttu-id="120ae-129">クエリ通知に登録するために使用する SELECT ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="120ae-129">Specifies the SELECT statement used to register for query notifications.</span></span> <span data-ttu-id="120ae-130">アダプターは、指定した SELECT ステートメントの変更の結果セットの場合にのみ、通知メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="120ae-130">The adapter gets a notification message only when the result set for the specified SELECT statement changes.</span></span>|  
|<span data-ttu-id="120ae-131">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="120ae-131">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="120ae-132">リスナーが開始されると、アダプターがアダプター クライアントに通知を送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="120ae-132">Specifies whether the adapter sends a notification to the adapter clients when the listener is started.</span></span>|  
  
 <span data-ttu-id="120ae-133">これらのプロパティの詳細については、次を参照してください。 [for Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="120ae-133">For a more complete description of these properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="120ae-134">使用する方法の詳細については、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite から通知を受信するさらに読み進める。</span><span class="sxs-lookup"><span data-stu-id="120ae-134">For a complete description of how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive notifications from Oracle E-Business Suite, read further.</span></span>  
  
## <a name="how-this-topic-demonstrates-receiving-notification-messages"></a><span data-ttu-id="120ae-135">このトピックで通知メッセージの受信について説明する方法</span><span class="sxs-lookup"><span data-stu-id="120ae-135">How This Topic Demonstrates Receiving Notification Messages</span></span>  
 <span data-ttu-id="120ae-136">示すために、このトピックでどのように[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]Oracle E-business Suite からのデータベースの増分変更の通知メッセージの受信をサポートするには、ACCOUNTACTIVTY テーブルへの変更の通知を受信するアダプターを構成しますが。</span><span class="sxs-lookup"><span data-stu-id="120ae-136">In this topic, to demonstrate how the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports receiving incremental database change notification messages from Oracle E-Business Suite, we will configure the adapter to receive notifications for changes to the ACCOUNTACTIVTY table.</span></span> <span data-ttu-id="120ae-137">お知らせ ACCOUNTACTIVITY テーブルは、"TID"、「アカウント」および「処理済み」の列であると仮定します。</span><span class="sxs-lookup"><span data-stu-id="120ae-137">Let us assume that the ACCOUNTACTIVITY table has columns “TID”, “Account”, and “Processed”.</span></span> <span data-ttu-id="120ae-138">「処理済み」列の値を設定するたびに新しいレコードを追加すると、' n ' です。</span><span class="sxs-lookup"><span data-stu-id="120ae-138">Whenever a new record is added, the value of the “Processed” column is set to ‘n’.</span></span> <span data-ttu-id="120ae-139">そのため、インクリメンタル通知を取得するは、BizTalk オーケストレーションの一環として、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="120ae-139">So, to get incremental notifications you will have to do the following tasks as part of the BizTalk orchestration:</span></span>  
  
- <span data-ttu-id="120ae-140">「処理済み」であるすべてのレコードに関する通知を受け取ります 'n' です。</span><span class="sxs-lookup"><span data-stu-id="120ae-140">Get notification for all records where “Processed” is ‘n’.</span></span> <span data-ttu-id="120ae-141">通知のステートメントと SELECT ステートメントを指定することで、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="120ae-141">You can do this by specifying a SELECT statement as a notification statement.</span></span>  
  
- <span data-ttu-id="120ae-142">特定のレコードの通知を受け取った後は、「処理」を 'y' に設定します。</span><span class="sxs-lookup"><span data-stu-id="120ae-142">After the notification is received for a certain record, set “Processed” to ‘y’.</span></span> <span data-ttu-id="120ae-143">「処理済み」列を更新する、PROCESS_RECORDS、ストアド プロシージャを実行して、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="120ae-143">You can do this by executing a stored procedure, PROCESS_RECORDS, which updates the “Processed” column.</span></span>  
  
  <span data-ttu-id="120ae-144">インクリメンタル通知の受信を示すために、次の項目行います。</span><span class="sxs-lookup"><span data-stu-id="120ae-144">To demonstrate receiving incremental notifications, we do the following:</span></span>  
  
- <span data-ttu-id="120ae-145">スキーマを生成、**通知**(入力方向の操作)、および**PROCESS_RECORDS** (送信操作) ACCOUNTACTIVITY テーブルにします。</span><span class="sxs-lookup"><span data-stu-id="120ae-145">Generate schema for the **Notification** (inbound operation), and **PROCESS_RECORDS** (outbound operation) on the ACCOUNTACTIVITY table.</span></span>  
  
- <span data-ttu-id="120ae-146">次を含むオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="120ae-146">Create an orchestration that has the following:</span></span>  
  
  -   <span data-ttu-id="120ae-147">通知メッセージを受信する受信場所。</span><span class="sxs-lookup"><span data-stu-id="120ae-147">A receive location to receive notification messages.</span></span> <span data-ttu-id="120ae-148">として、SELECT ステートメントを指定することで、通知を構成できます。</span><span class="sxs-lookup"><span data-stu-id="120ae-148">You can configure for notification by specifying the SELECT statement as:</span></span>  
  
      ```  
      SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’  
      ```  
  
      > [!NOTE]
      >  <span data-ttu-id="120ae-149">スキーマ名とテーブル名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="120ae-149">You must specify the table name along with the schema name.</span></span> <span data-ttu-id="120ae-150">たとえば、 `SCOTT.ACCOUNTACTIVITY`のようにします。</span><span class="sxs-lookup"><span data-stu-id="120ae-150">For example, `SCOTT.ACCOUNTACTIVITY`.</span></span>  
  
  -   <span data-ttu-id="120ae-151">通知が送信されて既に行を更新する送信ポートです。</span><span class="sxs-lookup"><span data-stu-id="120ae-151">A send port to update the rows for which notification has already been sent.</span></span> <span data-ttu-id="120ae-152">通知を受信したレコードの 'y' の「処理済み」列の値を設定するには、このポートに PROCESS_RECORDS ストアド プロシージャが実行されます。</span><span class="sxs-lookup"><span data-stu-id="120ae-152">You will execute the PROCESS_RECORDS stored procedure on this port to set the value of “Processed” column to ‘y’ for the records for which notification is received.</span></span>  
  
       <span data-ttu-id="120ae-153">この操作は、処理された行が更新されるようにメッセージ通知の受信後に実行する必要がありますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="120ae-153">Note that this operation must be executed after receiving the notification messages so that the processed rows are updated.</span></span> <span data-ttu-id="120ae-154">通知応答を待機していると、PROCESS_RECORDS プロシージャを実行する要求メッセージを手動で削除のオーバーヘッドがすぐには、オーケストレーション自体内 PROCESS_RECORDS プロシージャの要求メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="120ae-154">To do away with the overhead of waiting to get the notification response and then manually dropping a request message to execute the PROCESS_RECORDS procedure, you will generate the request message for PROCESS_RECORDS procedure within the orchestration itself.</span></span> <span data-ttu-id="120ae-155">使用して行うことができます、**メッセージの構築**図形をオーケストレーション内。</span><span class="sxs-lookup"><span data-stu-id="120ae-155">You can do so by using the **Construct Message** shape within an orchestration.</span></span>  
  
## <a name="how-to-receive-notification-messages-from-oracle-e-business-suite"></a><span data-ttu-id="120ae-156">Oracle E-business Suite から通知メッセージを受信する方法</span><span class="sxs-lookup"><span data-stu-id="120ae-156">How to Receive Notification Messages from Oracle E-Business Suite</span></span>  
 <span data-ttu-id="120ae-157">Oracle E-business Suite を使用して、操作を実行する[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[Oracle E-business Suite のアプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="120ae-157">Performing an operation on Oracle E-Business Suite using [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves the procedural tasks described in [Building Blocks to create Oracle E-Business Suite Applications](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md).</span></span> <span data-ttu-id="120ae-158">これらのタスクは通知メッセージを受信するアダプターを構成するには。</span><span class="sxs-lookup"><span data-stu-id="120ae-158">To configure the adapter to receive notification messages, these tasks are:</span></span>  
  
1. <span data-ttu-id="120ae-159">BizTalk プロジェクトを作成しのスキーマを生成し、**通知**(入力方向の操作) と**PROCESS_RECORDS** ACCOUNTACTIVITY テーブルでは、手順 (送信操作)。</span><span class="sxs-lookup"><span data-stu-id="120ae-159">Create a BizTalk project, and then generate schema for the **Notification** (inbound operation) and **PROCESS_RECORDS** procedure (outbound operation) on the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="120ae-160">値を指定する、必要に応じて、 **InboundOperationType**、 **NotificationPort**、および**NotificationStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="120ae-160">Optionally, you can specify values for the **InboundOperationType**, **NotificationPort**, and **NotificationStatement** binding properties.</span></span>  
  
2. <span data-ttu-id="120ae-161">Oracle E-business Suite から通知を受信するための BizTalk プロジェクトでは、メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="120ae-161">Create a message in the BizTalk project for receiving notification from Oracle E-Business Suite.</span></span>  
  
3. <span data-ttu-id="120ae-162">PROCESS_RECORDS ストアド プロシージャを実行して、応答メッセージを受信するための BizTalk プロジェクトでは、メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="120ae-162">Create messages in the BizTalk project for executing the PROCESS_RECORDS stored procedure and receiving response messages.</span></span>  
  
4. <span data-ttu-id="120ae-163">次のオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="120ae-163">Create an orchestration that does the following:</span></span>  
  
   -   <span data-ttu-id="120ae-164">Oracle E-business Suite から通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="120ae-164">Receives notification message from Oracle E-Business Suite.</span></span>  
  
   -   <span data-ttu-id="120ae-165">PROCESS_RECORDS プロシージャを実行するメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="120ae-165">Creates a message to execute the PROCESS_RECORDS procedure.</span></span>  
  
   -   <span data-ttu-id="120ae-166">このメッセージを選択し、レコードの更新し、応答を受信する Oracle E-business Suite に送信します。</span><span class="sxs-lookup"><span data-stu-id="120ae-166">Sends this message to Oracle E-Business Suite to select and update the records and receive a response.</span></span>  
  
5. <span data-ttu-id="120ae-167">ビルドし、BizTalk プロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="120ae-167">Build and deploy the BizTalk project.</span></span>  
  
6. <span data-ttu-id="120ae-168">BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="120ae-168">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="120ae-169">受信操作の場合、通知メッセージを受信するように Wcf-custom の一方向のみを構成する必要があります。 または Wcf-oracleebs 受信ポート。</span><span class="sxs-lookup"><span data-stu-id="120ae-169">For inbound operations, like receiving notification messages, you must only configure a one-way WCF-Custom or WCF-OracleEBS receive port.</span></span> <span data-ttu-id="120ae-170">双方向受信ポートは受信操作のサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="120ae-170">Two-way receive ports are not supported for inbound operations.</span></span>  
  
7. <span data-ttu-id="120ae-171">BizTalk アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="120ae-171">Start the BizTalk application.</span></span>  
  
   <span data-ttu-id="120ae-172">このトピックでは、これらのタスクを実行する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="120ae-172">This topic provides instructions to perform these tasks.</span></span>  
  
## <a name="generating-schema"></a><span data-ttu-id="120ae-173">スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="120ae-173">Generating Schema</span></span>  
 <span data-ttu-id="120ae-174">スキーマを生成する必要があります、**通知**操作と**PROCESS_RECORDS**プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="120ae-174">You must generate the schema for the **Notification** operation and **PROCESS_RECORDS** procedure.</span></span> <span data-ttu-id="120ae-175">参照してください[Visual Studio での Oracle E-business Suite 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)スキーマを生成する方法の詳細について。</span><span class="sxs-lookup"><span data-stu-id="120ae-175">See [Retrieving Metadata for Oracle E-Business Suite Operations in Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md) for more information about how to generate the schema.</span></span> <span data-ttu-id="120ae-176">スキーマを生成するときに、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="120ae-176">Perform the following tasks when generating the schema.</span></span> <span data-ttu-id="120ae-177">デザイン時のバインドのプロパティを指定しない場合は、最初の手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="120ae-177">Skip the first step if you do not want to specify the binding properties at design-time.</span></span>  
  
1.  <span data-ttu-id="120ae-178">値を指定**InboundOperationType**、 **NotificationPort**、および**NotificationStatement**スキーマの生成中にプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="120ae-178">Specify a value for **InboundOperationType**, **NotificationPort**, and **NotificationStatement** binding properties while generating the schema.</span></span> <span data-ttu-id="120ae-179">このバインドのプロパティの詳細については、次を参照してください。[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="120ae-179">For more information about this binding property, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="120ae-180">バインドのプロパティを指定する方法については、次を参照してください。 [for Oracle E-business Suite のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)します。</span><span class="sxs-lookup"><span data-stu-id="120ae-180">For instructions on how to specify binding properties, see [Configure the Binding Properties for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md).</span></span>  
  
2.  <span data-ttu-id="120ae-181">コントラクトの種類を選択します。**サービス (受信操作)** します。</span><span class="sxs-lookup"><span data-stu-id="120ae-181">Select the contract type as **Service (Inbound operations)**.</span></span>  
  
3.  <span data-ttu-id="120ae-182">スキーマの生成、**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="120ae-182">Generate schema for the **Notification** operation.</span></span>  
  
4.  <span data-ttu-id="120ae-183">コントラクトの種類を選択します。**クライアント (送信操作)** します。</span><span class="sxs-lookup"><span data-stu-id="120ae-183">Select the contract type as **Client (Outbound operations)**.</span></span>  
  
5.  <span data-ttu-id="120ae-184">スキーマの生成、 **PROCESS_RECORDS**プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="120ae-184">Generate schema for the **PROCESS_RECORDS** procedure.</span></span> <span data-ttu-id="120ae-185">この手順で使用可能な**ACCOUNT_PKG**パッケージ。</span><span class="sxs-lookup"><span data-stu-id="120ae-185">This procedure is available under the **ACCOUNT_PKG** package.</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="120ae-186">メッセージおよびメッセージの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="120ae-186">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="120ae-187">以前に生成したスキーマには、オーケストレーション内のメッセージに必要な「型」について説明します。</span><span class="sxs-lookup"><span data-stu-id="120ae-187">The schema that you generated earlier describes the "types" required for the messages in the orchestration.</span></span> <span data-ttu-id="120ae-188">メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。</span><span class="sxs-lookup"><span data-stu-id="120ae-188">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="120ae-189">スキーマが生成されるは、BizTalk プロジェクトのオーケストレーションからメッセージをリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="120ae-189">Once the schema is generated, you must link it to the messages from the Orchestration view of the BizTalk project.</span></span>  
  
 <span data-ttu-id="120ae-190">このトピックでは、3 つのメッセージを作成する必要があります: 1、Oracle E-business Suite から通知を受け取る、PROCESS_RECORDS プロシージャを実行する 1 つおよびプロシージャの応答を受信する 1 つ。</span><span class="sxs-lookup"><span data-stu-id="120ae-190">For this topic, you must create three messages—one to receive notifications from the Oracle E-Business Suite, one to execute the PROCESS_RECORDS procedure, and one to receive the response for the procedure.</span></span>  
  
 <span data-ttu-id="120ae-191">メッセージを作成し、スキーマにリンクするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="120ae-191">Perform the following steps to create messages and link them to schema.</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="120ae-192">メッセージを作成し、スキーマにリンクするには</span><span class="sxs-lookup"><span data-stu-id="120ae-192">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="120ae-193">オーケストレーションを BizTalk プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="120ae-193">Add an orchestration to the BizTalk project.</span></span> <span data-ttu-id="120ae-194">ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックして**追加**、 をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="120ae-194">From the Solution Explorer, right-click the BizTalk project name, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="120ae-195">BizTalk オーケストレーションの名前を入力し、クリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="120ae-195">Type a name for the BizTalk orchestration and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="120ae-196">開いていない場合は、BizTalk プロジェクトのオーケストレーション ビュー ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="120ae-196">Open the orchestration view window of the BizTalk project, if it is not already open.</span></span> <span data-ttu-id="120ae-197">をクリックして**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="120ae-197">Click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
3.  <span data-ttu-id="120ae-198">**オーケストレーション**、右クリック**メッセージ**、順にクリックします**新しいメッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="120ae-198">In the **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span>  
  
4.  <span data-ttu-id="120ae-199">新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="120ae-199">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="120ae-200">**プロパティ**ウィンドウ **[message_1]** 次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="120ae-200">In the **Properties** pane for **Message_1**, do the following:</span></span>  
  
    |<span data-ttu-id="120ae-201">プロパティ</span><span class="sxs-lookup"><span data-stu-id="120ae-201">Use this</span></span>|<span data-ttu-id="120ae-202">目的</span><span class="sxs-lookup"><span data-stu-id="120ae-202">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="120ae-203">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="120ae-203">Identifier</span></span>|<span data-ttu-id="120ae-204">「`NotifyReceive`.</span><span class="sxs-lookup"><span data-stu-id="120ae-204">Type `NotifyReceive`.</span></span>|  
    |<span data-ttu-id="120ae-205">メッセージ型</span><span class="sxs-lookup"><span data-stu-id="120ae-205">Message Type</span></span>|<span data-ttu-id="120ae-206">ドロップダウン リストから展開**スキーマ**、選択と*OracleNotifyIncremental.OracleEBSBinding.Notification*ここで、 *OracleNotifyIncremental*の名前を指定します。BizTalk プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="120ae-206">From the drop-down list, expand **Schemas**, and select *OracleNotifyIncremental.OracleEBSBinding.Notification*, where *OracleNotifyIncremental* is the name of your BizTalk project.</span></span> <span data-ttu-id="120ae-207">*OracleEBSBinding*に対して生成されたスキーマには、**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="120ae-207">*OracleEBSBinding* is the schema generated for the **Notification** operation.</span></span>|  
  
6.  <span data-ttu-id="120ae-208">手順 3 を 2 つの新しいメッセージを作成する.</span><span class="sxs-lookup"><span data-stu-id="120ae-208">Repeat step 3 to create two new messages.</span></span> <span data-ttu-id="120ae-209">**プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="120ae-209">In the **Properties** pane for the new message, do the following:</span></span>  
  
    |<span data-ttu-id="120ae-210">識別子を設定するには</span><span class="sxs-lookup"><span data-stu-id="120ae-210">Set Identifier to</span></span>|<span data-ttu-id="120ae-211">メッセージの種類を設定</span><span class="sxs-lookup"><span data-stu-id="120ae-211">Set Message Type to</span></span>|  
    |-----------------------|-------------------------|  
    |<span data-ttu-id="120ae-212">手順</span><span class="sxs-lookup"><span data-stu-id="120ae-212">Procedure</span></span>|<span data-ttu-id="120ae-213">*OracleNotifyIncremental.OracleEBSBinding1.PROCESS_RECORDS*ここで、 *OracleEBSBinding1*に対して生成されたスキーマには、 **PROCESS_RECORDS**プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="120ae-213">*OracleNotifyIncremental.OracleEBSBinding1.PROCESS_RECORDS*, where  *OracleEBSBinding1* is the schema generated for the **PROCESS_RECORDS** procedure.</span></span>|  
    |<span data-ttu-id="120ae-214">ProcedureResponse</span><span class="sxs-lookup"><span data-stu-id="120ae-214">ProcedureResponse</span></span>|<span data-ttu-id="120ae-215">*OracleNotifyIncremental.OracleEBSBinding1.PROCESS_RECORDSResponse*</span><span class="sxs-lookup"><span data-stu-id="120ae-215">*OracleNotifyIncremental.OracleEBSBinding1.PROCESS_RECORDSResponse*</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="120ae-216">オーケストレーションのセットアップ</span><span class="sxs-lookup"><span data-stu-id="120ae-216">Setting up the Orchestration</span></span>  
 <span data-ttu-id="120ae-217">使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]for Oracle E-business Suite から通知メッセージを受信し、通知を受信した行を更新します。</span><span class="sxs-lookup"><span data-stu-id="120ae-217">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for receiving notification messages from Oracle E-Business Suite and then updating the rows for which notification was received.</span></span> <span data-ttu-id="120ae-218">このオーケストレーションでの指定した SELECT ステートメントに基づいて、通知メッセージを受信、 **NotificationStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="120ae-218">In this orchestration, the adapter receives the notification message based on the SELECT statement specified for the **NotificationStatement** binding property.</span></span> <span data-ttu-id="120ae-219">通知メッセージは、ファイルの場所で受信されます。</span><span class="sxs-lookup"><span data-stu-id="120ae-219">The notification message is received at a FILE location.</span></span> <span data-ttu-id="120ae-220">応答が受信されると、オーケストレーションは通知を受信した行を更新する PROCESS_RECORDS プロシージャを呼び出すメッセージを構築します。</span><span class="sxs-lookup"><span data-stu-id="120ae-220">Once the response is received, the orchestration constructs a message to invoke the PROCESS_RECORDS procedure, which updates the rows for which notification is received.</span></span> <span data-ttu-id="120ae-221">このメッセージの応答を同じファイルの場所で受信もします。</span><span class="sxs-lookup"><span data-stu-id="120ae-221">The response for this message is also received at the same FILE location.</span></span>  
  
 <span data-ttu-id="120ae-222">そのため、オーケストレーションは、次に含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="120ae-222">So, your orchestration must contain the following:</span></span>  
  
- <span data-ttu-id="120ae-223">一方向の WCF カスタムまたは Wcf-oracleebs 通知メッセージを受信するポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="120ae-223">A one-way WCF-Custom or WCF-OracleEBS receive port to receive notification messages.</span></span>  
  
- <span data-ttu-id="120ae-224">双方向の WCF カスタムまたは Wcf-oracleebs PROCESS_RECORDS プロシージャを実行するメッセージを送信するポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="120ae-224">A two-way WCF-Custom or WCF-OracleEBS send port to send messages to execute the PROCESS_RECORDS procedure.</span></span>  
  
- <span data-ttu-id="120ae-225">A**メッセージの構築**図形をオーケストレーション内での PROCESS_RECORDS プロシージャを実行する、メッセージを構築します。</span><span class="sxs-lookup"><span data-stu-id="120ae-225">A **Construct Message** shape to construct messages, to execute PROCESS_RECORDS procedure, within the orchestration.</span></span>  
  
- <span data-ttu-id="120ae-226">ファイルは、通知メッセージと応答 PROCESS_RECORDS プロシージャを保存するポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="120ae-226">A FILE send port to save the notification message and the response for the PROCESS_RECORDS procedure.</span></span>  
  
- <span data-ttu-id="120ae-227">受信図形と送信図形。</span><span class="sxs-lookup"><span data-stu-id="120ae-227">Receive and send shapes.</span></span>  
  
  <span data-ttu-id="120ae-228">サンプル オーケストレーションでは、次の項目に似ています。</span><span class="sxs-lookup"><span data-stu-id="120ae-228">A sample orchestration resembles the following.</span></span>  
  
  <span data-ttu-id="120ae-229">![Oracle から通知を受信するオーケストレーション](../../adapters-and-accelerators/adapter-oracle-database/media/cef49414-490a-4bd5-a32d-b3f4cde5950a.gif "cef49414-490a-4bd5-a32d-b3f4cde5950a")</span><span class="sxs-lookup"><span data-stu-id="120ae-229">![Orchestration to receive notifications from Oracle](../../adapters-and-accelerators/adapter-oracle-database/media/cef49414-490a-4bd5-a32d-b3f4cde5950a.gif "cef49414-490a-4bd5-a32d-b3f4cde5950a")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="120ae-230">メッセージの構築図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="120ae-230">Adding Message Shapes</span></span>  
 <span data-ttu-id="120ae-231">メッセージの構築図形のごとに、次のプロパティを指定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="120ae-231">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="120ae-232">図形の列に示した名前は、単に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。</span><span class="sxs-lookup"><span data-stu-id="120ae-232">The names listed in the Shape column are the names of the message shapes as displayed in the just-mentioned orchestration.</span></span>  
  
|<span data-ttu-id="120ae-233">図形</span><span class="sxs-lookup"><span data-stu-id="120ae-233">Shape</span></span>|<span data-ttu-id="120ae-234">図形の種類</span><span class="sxs-lookup"><span data-stu-id="120ae-234">Shape Type</span></span>|<span data-ttu-id="120ae-235">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="120ae-235">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="120ae-236">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="120ae-236">ReceiveNotification</span></span>|<span data-ttu-id="120ae-237">Receive</span><span class="sxs-lookup"><span data-stu-id="120ae-237">Receive</span></span>|<span data-ttu-id="120ae-238">-設定**名前**に*ReceiveNotification*</span><span class="sxs-lookup"><span data-stu-id="120ae-238">- Set **Name** to *ReceiveNotification*</span></span><br /><br /> <span data-ttu-id="120ae-239">-設定**アクティブ**に*は True。*</span><span class="sxs-lookup"><span data-stu-id="120ae-239">- Set **Activate** to *True*</span></span>|  
|<span data-ttu-id="120ae-240">SaveNotification</span><span class="sxs-lookup"><span data-stu-id="120ae-240">SaveNotification</span></span>|<span data-ttu-id="120ae-241">Send</span><span class="sxs-lookup"><span data-stu-id="120ae-241">Send</span></span>|<span data-ttu-id="120ae-242">-設定**名前**に*SaveNotification*</span><span class="sxs-lookup"><span data-stu-id="120ae-242">- Set **Name** to *SaveNotification*</span></span>|  
|<span data-ttu-id="120ae-243">SendProcMessage</span><span class="sxs-lookup"><span data-stu-id="120ae-243">SendProcMessage</span></span>|<span data-ttu-id="120ae-244">Send</span><span class="sxs-lookup"><span data-stu-id="120ae-244">Send</span></span>|<span data-ttu-id="120ae-245">-設定**名前**に*SendProcMessage*</span><span class="sxs-lookup"><span data-stu-id="120ae-245">- Set **Name** to *SendProcMessage*</span></span>|  
|<span data-ttu-id="120ae-246">ReceiveProcResponse</span><span class="sxs-lookup"><span data-stu-id="120ae-246">ReceiveProcResponse</span></span>|<span data-ttu-id="120ae-247">Receive</span><span class="sxs-lookup"><span data-stu-id="120ae-247">Receive</span></span>|<span data-ttu-id="120ae-248">-設定**名前**に*ReceiveProcResponse*</span><span class="sxs-lookup"><span data-stu-id="120ae-248">- Set **Name** to *ReceiveProcResponse*</span></span>|  
|<span data-ttu-id="120ae-249">SaveProcResponse</span><span class="sxs-lookup"><span data-stu-id="120ae-249">SaveProcResponse</span></span>|<span data-ttu-id="120ae-250">Send</span><span class="sxs-lookup"><span data-stu-id="120ae-250">Send</span></span>|<span data-ttu-id="120ae-251">-設定**名前**に*SaveProcResponse*</span><span class="sxs-lookup"><span data-stu-id="120ae-251">- Set **Name** to *SaveProcResponse*</span></span>|  
  
### <a name="adding-construct-message-shape"></a><span data-ttu-id="120ae-252">メッセージの構築図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="120ae-252">Adding Construct Message Shape</span></span>  
 <span data-ttu-id="120ae-253">使用することができます、**メッセージの構築**図形をオーケストレーション内で PROCESS_RECORDS プロシージャを実行する要求メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="120ae-253">You can use the **Construct Message** shape to generate a request message within the orchestration to execute the PROCESS_RECORDS procedure.</span></span> <span data-ttu-id="120ae-254">これを行うには、追加する必要があります、**メッセージの構築**図形し、その中を**メッセージの割り当て**図形をオーケストレーションにします。</span><span class="sxs-lookup"><span data-stu-id="120ae-254">To do so, you must add a **Construct Message** shape and within that a **Message Assignment** shape to your orchestration.</span></span> <span data-ttu-id="120ae-255">この例で、**メッセージの割り当て**図形は、プロシージャを実行する Oracle E-business Suite に送信されるメッセージを生成するコードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="120ae-255">For this example, the **Message Assignment** shape invokes code that generates a message that is sent to Oracle E-Business Suite to execute the procedure.</span></span> <span data-ttu-id="120ae-256">**メッセージの割り当て**図形も、Oracle E-business Suite に送信するメッセージに対するアクションを設定します。</span><span class="sxs-lookup"><span data-stu-id="120ae-256">The **Message Assignment** shape also sets the action for the message to be sent to Oracle E-Business Suite.</span></span>  
  
 <span data-ttu-id="120ae-257">メッセージの構築図形で、設定、**メッセージ構築**プロパティを**プロシージャ**します。</span><span class="sxs-lookup"><span data-stu-id="120ae-257">For the construct message shape, set the **Message Constructed** property to **Procedure**.</span></span>  
  
 <span data-ttu-id="120ae-258">応答を生成するコードは、BizTalk プロジェクトと同じ Visual Studio ソリューションの一部になります。</span><span class="sxs-lookup"><span data-stu-id="120ae-258">The code to generate the response could be part of the same Visual Studio solution as your BizTalk project.</span></span> <span data-ttu-id="120ae-259">応答メッセージを生成するためのサンプル コードは、次のように検索します。</span><span class="sxs-lookup"><span data-stu-id="120ae-259">A sample code for generating a response message looks like this.</span></span>  
  
```  
namespace MessageCreator  
{  
    public class MessageCreator  
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
  
 <span data-ttu-id="120ae-260">要求メッセージを生成できるように上記のコードの抜粋をする必要があります (PROCESS_RECORDS 手順) については、XML 要求メッセージに指定された場所で、`XmlFileLocation`変数。</span><span class="sxs-lookup"><span data-stu-id="120ae-260">For the above code excerpt to be able to generate a request message, you must have an XML request message (for the PROCESS_RECORDS procedure) in the location specified for the `XmlFileLocation` variable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="120ae-261">プロジェクトをビルドした後に MessageCreator.dll がプロジェクト ディレクトリに作成されます。</span><span class="sxs-lookup"><span data-stu-id="120ae-261">After you build the project, MessageCreator.dll will be created in the project directory.</span></span> <span data-ttu-id="120ae-262">この DLL は、グローバル アセンブリ キャッシュ (GAC) に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="120ae-262">You must add this DLL to the global assembly cache (GAC).</span></span> <span data-ttu-id="120ae-263">また、BizTalk プロジェクトに参照として、MessageCreator.dll を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="120ae-263">Also, you must add the MessageCreator.dll as a reference in the BizTalk project.</span></span>  
  
 <span data-ttu-id="120ae-264">次のコードを呼び出すには、次の式を追加、**メッセージの割り当て**図形とメッセージのアクションを設定します。</span><span class="sxs-lookup"><span data-stu-id="120ae-264">Add the following expression to invoke this code from the **Message Assignment** shape and to set the action for message.</span></span> <span data-ttu-id="120ae-265">式を追加するには、ダブルクリック、**メッセージの割り当て**図形式エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="120ae-265">To add an expression, double-click the **Message Assignment** shape to open the Expression Editor.</span></span>  
  
```  
Procedure = MessageCreator.MessageCreator.XMLMessageCreator();  
Procedure(WCF.Action) = "PackageApis/SCOTT/ACCOUNT_PKG/PROCESS_RECORDS";  
```  
  
### <a name="adding-ports"></a><span data-ttu-id="120ae-266">ポートの追加</span><span class="sxs-lookup"><span data-stu-id="120ae-266">Adding Ports</span></span>  
 <span data-ttu-id="120ae-267">論理ポートごとに、次のプロパティを指定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="120ae-267">Make sure you specify the following properties for each of the logical ports.</span></span> <span data-ttu-id="120ae-268">ポート列に示した名前は、オーケストレーションで表示されているポートの名前です。</span><span class="sxs-lookup"><span data-stu-id="120ae-268">The names listed in the Port column are the names of the ports as displayed in the orchestration.</span></span>  
  
|<span data-ttu-id="120ae-269">Port</span><span class="sxs-lookup"><span data-stu-id="120ae-269">Port</span></span>|<span data-ttu-id="120ae-270">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="120ae-270">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="120ae-271">OracleNotifyPort</span><span class="sxs-lookup"><span data-stu-id="120ae-271">OracleNotifyPort</span></span>|<span data-ttu-id="120ae-272">-設定**識別子**に*OracleNotifyPort*</span><span class="sxs-lookup"><span data-stu-id="120ae-272">- Set **Identifier** to *OracleNotifyPort*</span></span><br /><br /> <span data-ttu-id="120ae-273">-設定**型**に*OracleNotifyPortType*</span><span class="sxs-lookup"><span data-stu-id="120ae-273">- Set **Type** to *OracleNotifyPortType*</span></span><br /><br /> <span data-ttu-id="120ae-274">-設定**通信パターン**に*一方向*</span><span class="sxs-lookup"><span data-stu-id="120ae-274">- Set **Communication Pattern** to *One-Way*</span></span><br /><br /> <span data-ttu-id="120ae-275">-設定**通信方向**に*受信*</span><span class="sxs-lookup"><span data-stu-id="120ae-275">- Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="120ae-276">SaveMessagePort</span><span class="sxs-lookup"><span data-stu-id="120ae-276">SaveMessagePort</span></span>|<span data-ttu-id="120ae-277">-設定**識別子**に*SaveMessagePort*</span><span class="sxs-lookup"><span data-stu-id="120ae-277">- Set **Identifier** to *SaveMessagePort*</span></span><br /><br /> <span data-ttu-id="120ae-278">-設定**型**に*SaveMessagePortType*</span><span class="sxs-lookup"><span data-stu-id="120ae-278">- Set **Type** to *SaveMessagePortType*</span></span><br /><br /> <span data-ttu-id="120ae-279">-設定**通信パターン**に*一方向*</span><span class="sxs-lookup"><span data-stu-id="120ae-279">- Set **Communication Pattern** to *One-Way*</span></span><br /><br /> <span data-ttu-id="120ae-280">-設定**通信方向**に*送信*</span><span class="sxs-lookup"><span data-stu-id="120ae-280">- Set **Communication Direction** to *Send*</span></span><br /><br /> <span data-ttu-id="120ae-281">-作成操作*通知*します。</span><span class="sxs-lookup"><span data-stu-id="120ae-281">- Create an operation *Notify*.</span></span> <span data-ttu-id="120ae-282">この操作は、通知メッセージに使用されます。</span><span class="sxs-lookup"><span data-stu-id="120ae-282">This operation is used for notification messages.</span></span><br /><br /> <span data-ttu-id="120ae-283">-作成操作*プロシージャ*します。</span><span class="sxs-lookup"><span data-stu-id="120ae-283">- Create an operation *Procedure*.</span></span> <span data-ttu-id="120ae-284">この操作は、応答メッセージに使用されます。</span><span class="sxs-lookup"><span data-stu-id="120ae-284">This operation is used for select response messages.</span></span>|  
|<span data-ttu-id="120ae-285">OracleOutboundPort</span><span class="sxs-lookup"><span data-stu-id="120ae-285">OracleOutboundPort</span></span>|<span data-ttu-id="120ae-286">-設定**識別子**に*OracleOutboundPort*</span><span class="sxs-lookup"><span data-stu-id="120ae-286">- Set **Identifier** to *OracleOutboundPort*</span></span><br /><br /> <span data-ttu-id="120ae-287">-設定**型**に*OracleOutboundPortType*</span><span class="sxs-lookup"><span data-stu-id="120ae-287">- Set **Type** to *OracleOutboundPortType*</span></span><br /><br /> <span data-ttu-id="120ae-288">-設定**通信パターン**に*要求-応答*</span><span class="sxs-lookup"><span data-stu-id="120ae-288">- Set **Communication Pattern** to *Request-Response*</span></span><br /><br /> <span data-ttu-id="120ae-289">-設定**通信方向**に*送受信*</span><span class="sxs-lookup"><span data-stu-id="120ae-289">- Set **Communication Direction** to *Send-Receive*</span></span>|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a><span data-ttu-id="120ae-290">アクション図形のメッセージを指定し、ポートに接続</span><span class="sxs-lookup"><span data-stu-id="120ae-290">Specify Messages for Action Shapes and Connect to Ports</span></span>  
 <span data-ttu-id="120ae-291">次の表では、プロパティとアクション図形のメッセージを指定して、メッセージ ポートにリンクを設定する必要があります、値を指定します。</span><span class="sxs-lookup"><span data-stu-id="120ae-291">The following table specifies the properties and their values that you should set to specify messages for action shapes and to link the messages to the ports.</span></span> <span data-ttu-id="120ae-292">図形の列に示した名前は、前に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。</span><span class="sxs-lookup"><span data-stu-id="120ae-292">The names listed in the Shape column are the names of the message shapes as displayed in the orchestration mentioned earlier.</span></span>  
  
|<span data-ttu-id="120ae-293">図形</span><span class="sxs-lookup"><span data-stu-id="120ae-293">Shape</span></span>|<span data-ttu-id="120ae-294">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="120ae-294">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="120ae-295">ReceiveNotification</span><span class="sxs-lookup"><span data-stu-id="120ae-295">ReceiveNotification</span></span>|<span data-ttu-id="120ae-296">-設定**メッセージ**に*NotifyReceive*</span><span class="sxs-lookup"><span data-stu-id="120ae-296">- Set **Message** to *NotifyReceive*</span></span><br /><br /> <span data-ttu-id="120ae-297">-設定**操作**に*OracleNotifyPort.Notify.Request*</span><span class="sxs-lookup"><span data-stu-id="120ae-297">- Set **Operation** to *OracleNotifyPort.Notify.Request*</span></span>|  
|<span data-ttu-id="120ae-298">SaveNotification</span><span class="sxs-lookup"><span data-stu-id="120ae-298">SaveNotification</span></span>|<span data-ttu-id="120ae-299">-設定**メッセージ**に*NotifyReceive*</span><span class="sxs-lookup"><span data-stu-id="120ae-299">- Set **Message** to *NotifyReceive*</span></span><br /><br /> <span data-ttu-id="120ae-300">-設定**操作**に*SaveMessagePort.Notify.Request*</span><span class="sxs-lookup"><span data-stu-id="120ae-300">- Set **Operation** to *SaveMessagePort.Notify.Request*</span></span>|  
|<span data-ttu-id="120ae-301">SendProcMessage</span><span class="sxs-lookup"><span data-stu-id="120ae-301">SendProcMessage</span></span>|<span data-ttu-id="120ae-302">-設定**メッセージ**に*プロシージャ*</span><span class="sxs-lookup"><span data-stu-id="120ae-302">- Set **Message** to *Procedure*</span></span><br /><br /> <span data-ttu-id="120ae-303">-設定**操作**に*OracleOutboundPort.Procedure.Request*</span><span class="sxs-lookup"><span data-stu-id="120ae-303">- Set **Operation** to *OracleOutboundPort.Procedure.Request*</span></span>|  
|<span data-ttu-id="120ae-304">ReceiveProcResponse</span><span class="sxs-lookup"><span data-stu-id="120ae-304">ReceiveProcResponse</span></span>|<span data-ttu-id="120ae-305">-設定**メッセージ**に*ProcedureResponse*</span><span class="sxs-lookup"><span data-stu-id="120ae-305">- Set **Message** to *ProcedureResponse*</span></span><br /><br /> <span data-ttu-id="120ae-306">-設定**操作**に*OracleOutboundPort.Procedure.Response*</span><span class="sxs-lookup"><span data-stu-id="120ae-306">- Set **Operation** to *OracleOutboundPort.Procedure.Response*</span></span>|  
|<span data-ttu-id="120ae-307">SaveProcResponse</span><span class="sxs-lookup"><span data-stu-id="120ae-307">SaveProcResponse</span></span>|<span data-ttu-id="120ae-308">-設定**メッセージ**に*ProedureResponse*</span><span class="sxs-lookup"><span data-stu-id="120ae-308">- Set **Message** to *ProedureResponse*</span></span><br /><br /> <span data-ttu-id="120ae-309">-設定**操作**に*SaveMessagePort.Procedure.Request*</span><span class="sxs-lookup"><span data-stu-id="120ae-309">- Set **Operation** to *SaveMessagePort.Procedure.Request*</span></span>|  
  
 <span data-ttu-id="120ae-310">これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。</span><span class="sxs-lookup"><span data-stu-id="120ae-310">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="120ae-311">ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="120ae-311">You must now build the BizTalk solution and deploy it to a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="120ae-312">詳細についてを参照してください「オーケストレーションを構築および実行されている」 [ http://go.microsoft.com/fwlink/?LinkId=102359](http://go.microsoft.com/fwlink/?LinkId=102359)します。</span><span class="sxs-lookup"><span data-stu-id="120ae-312">For more information, see "Building and Running Orchestrations" at [http://go.microsoft.com/fwlink/?LinkId=102359](http://go.microsoft.com/fwlink/?LinkId=102359).</span></span>  
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="120ae-313">BizTalk アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="120ae-313">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="120ae-314">先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**ペインで、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="120ae-314">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the **Orchestrations** pane in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="120ae-315">使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールにアプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="120ae-315">You must use the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to configure the application.</span></span> <span data-ttu-id="120ae-316">アプリケーションを構成する方法の詳細についてを参照してください「する方法をアプリケーションの構成」 [ http://go.microsoft.com/fwlink/?LinkID=196961](http://go.microsoft.com/fwlink/?LinkID=196961)します。</span><span class="sxs-lookup"><span data-stu-id="120ae-316">For more information about configuring an application, see "How to Configure an Application" at [http://go.microsoft.com/fwlink/?LinkID=196961](http://go.microsoft.com/fwlink/?LinkID=196961).</span></span>  
  
 <span data-ttu-id="120ae-317">アプリケーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="120ae-317">Configuring an application involves:</span></span>  
  
- <span data-ttu-id="120ae-318">アプリケーションのホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="120ae-318">Selecting a host for the application.</span></span>  
  
- <span data-ttu-id="120ae-319">物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="120ae-319">Mapping the ports that you created in your orchestration to physical ports in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="120ae-320">このオーケストレーションの次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="120ae-320">For this orchestration you must:</span></span>  
  
  - <span data-ttu-id="120ae-321">Wcf-oracleebs 一方向受信ポートまたは物理 Wcf-custom を定義します。</span><span class="sxs-lookup"><span data-stu-id="120ae-321">Define a physical WCF-Custom or WCF-OracleEBS one-way receive port.</span></span> <span data-ttu-id="120ae-322">このポートは、Oracle E-business Suite から送る通知をリッスンします。</span><span class="sxs-lookup"><span data-stu-id="120ae-322">This port listens for notifications coming from Oracle E-Business Suite.</span></span> <span data-ttu-id="120ae-323">受信ポートを作成する方法についてを参照してください[、Oracle E-business アダプターを物理ポート バインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="120ae-323">For information about how to create receive ports, see [Manually Configuring a Physical Port Binding to the Oracle E-Business Adapter](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md).</span></span> <span data-ttu-id="120ae-324">受信ポートのバインドのプロパティを指定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="120ae-324">Make sure you specify the following binding properties for the receive port.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="120ae-325">デザイン時のバインドのプロパティが指定されている場合は、この手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="120ae-325">You do not need to perform this step if you specified the binding properties at design-time.</span></span> <span data-ttu-id="120ae-326">このような場合は、作成、受信ポートで、必要なバインドのプロパティを設定によって作成されたバインド ファイルをインポートすることによって、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="120ae-326">In such a case, you can create a receive port, with the required binding properties set, by importing the binding file created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span> <span data-ttu-id="120ae-327">詳細については、次を参照してください。 [Oracle E-business Suite へのポートのバインド ファイルを物理ポートのバインドを使用して、を構成](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)します。</span><span class="sxs-lookup"><span data-stu-id="120ae-327">For more information see [Configure a Physical Port Binding Using a Port Binding File to Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md).</span></span>  
  
    |<span data-ttu-id="120ae-328">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="120ae-328">Binding Property</span></span>|<span data-ttu-id="120ae-329">値</span><span class="sxs-lookup"><span data-stu-id="120ae-329">Value</span></span>|  
    |----------------------|-----------|  
    |<span data-ttu-id="120ae-330">**InboundOperationType**</span><span class="sxs-lookup"><span data-stu-id="120ae-330">**InboundOperationType**</span></span>|<span data-ttu-id="120ae-331">これを設定**通知**します。</span><span class="sxs-lookup"><span data-stu-id="120ae-331">Set this to **Notification**.</span></span>|  
    |<span data-ttu-id="120ae-332">**NotificationPort**</span><span class="sxs-lookup"><span data-stu-id="120ae-332">**NotificationPort**</span></span>|<span data-ttu-id="120ae-333">Oracle データベースからのデータベース変更通知をリッスンする ODP.NET を開く必要があるポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="120ae-333">Specifies the port number that ODP.NET must open to listen for database change notification from Oracle database.</span></span> <span data-ttu-id="120ae-334">これは、Windows ファイアウォールの例外リストに追加する必要があります、同じポート番号に設定します。</span><span class="sxs-lookup"><span data-stu-id="120ae-334">Set this to the same port number that you must have added to the Windows Firewall exceptions list.</span></span> <span data-ttu-id="120ae-335">Windows ファイアウォールの例外リストにポートを追加する方法については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)します。</span><span class="sxs-lookup"><span data-stu-id="120ae-335">For instructions on how to add ports to Windows Firewall exceptions list, see [http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959).</span></span><br /><br /> <span data-ttu-id="120ae-336">**重要:** これを既定値は-1 に設定すると、通知メッセージを受信する Windows ファイアウォールを完全に無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="120ae-336">**Important:** If you set this to the default value of -1, you will have to completely disable Windows Firewall to receive notification messages.</span></span>|  
    |<span data-ttu-id="120ae-337">**NotificationStatement**</span><span class="sxs-lookup"><span data-stu-id="120ae-337">**NotificationStatement**</span></span>|<span data-ttu-id="120ae-338">これを設定します。</span><span class="sxs-lookup"><span data-stu-id="120ae-338">Set this to:</span></span><br /><br /> `SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’`<br /><br /> <span data-ttu-id="120ae-339">**注:** スキーマ名とテーブル名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="120ae-339">**Note:** You must specify the table name along with the schema name.</span></span> <span data-ttu-id="120ae-340">たとえば、 `SCOTT.ACCOUNTACTIVITY`のようにします。</span><span class="sxs-lookup"><span data-stu-id="120ae-340">For example, `SCOTT.ACCOUNTACTIVITY`.</span></span>|  
    |<span data-ttu-id="120ae-341">**NotifyOnListenerStart**</span><span class="sxs-lookup"><span data-stu-id="120ae-341">**NotifyOnListenerStart**</span></span>|<span data-ttu-id="120ae-342">これを設定**True**します。</span><span class="sxs-lookup"><span data-stu-id="120ae-342">Set this to **True**.</span></span>|  
  
     <span data-ttu-id="120ae-343">異なるバインディング プロパティの詳細については、次を参照してください。[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="120ae-343">For more information about the different binding properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="120ae-344">インターフェイス テーブルの通知を構成する場合は、必要なバインドのプロパティを指定することによってアプリケーション コンテキストを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="120ae-344">If you are configuring notifications for an interface table, you must set the application context by specifying the requisite binding properties.</span></span> <span data-ttu-id="120ae-345">アプリケーション コンテキストの設定の詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。</span><span class="sxs-lookup"><span data-stu-id="120ae-345">For more information about setting the application context see [Set Application Context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
    > 
    > [!NOTE]
    >  <span data-ttu-id="120ae-346">使用して受信操作の実行中に、トランザクション分離レベルとトランザクションのタイムアウトを構成することをお勧めします。、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="120ae-346">We recommend configuring the transaction isolation level and the transaction timeout while performing inbound operations using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="120ae-347">WCF カスタムを構成するときに、サービスの動作を追加することで行うことができますか、Wcf-oracleebs 受信ポート。</span><span class="sxs-lookup"><span data-stu-id="120ae-347">You can do so by adding the service behavior while configuring the WCF-Custom or WCF-OracleEBS receive port.</span></span> <span data-ttu-id="120ae-348">サービスの動作を追加する方法については、次を参照してください。[トランザクション分離レベルの構成と Oracle E-business Suite でのトランザクション タイムアウト](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)します。</span><span class="sxs-lookup"><span data-stu-id="120ae-348">For instruction on how to add the service behavior, see [Configure Transaction Isolation Level and Transaction Timeout with Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md).</span></span>  
  
  - <span data-ttu-id="120ae-349">PROCESS_REOCRDS プロシージャを実行する Oracle E-business Suite にメッセージを送信する物理 Wcf-custom または Wcf-oracleebs 送信ポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="120ae-349">Define a physical WCF-Custom or WCF-OracleEBS send port to send messages to Oracle E-Business Suite to execute the PROCESS_REOCRDS procedure.</span></span> <span data-ttu-id="120ae-350">送信ポートでアクションを指定することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="120ae-350">You must also specify the action in the send port.</span></span>  
  
  - <span data-ttu-id="120ae-351">ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションから Oracle E-business Suite、メッセージをドロップできる場所での場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="120ae-351">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the messages from Oracle E-Business Suite.</span></span> <span data-ttu-id="120ae-352">Wcf-custom または Wcf-oracleebs を通じて実行する PROCESS_RECORDS プロシージャのメッセージの送信ポートと、これらは、Oracle E-business Suite から受信した通知メッセージとなります。</span><span class="sxs-lookup"><span data-stu-id="120ae-352">These will be the notification messages received from Oracle E-Business Suite and messages for the PROCESS_RECORDS procedure you execute through the WCF-Custom or WCF-OracleEBS send port.</span></span>  
  
## <a name="starting-the-application"></a><span data-ttu-id="120ae-353">アプリケーションの起動</span><span class="sxs-lookup"><span data-stu-id="120ae-353">Starting the Application</span></span>  
 <span data-ttu-id="120ae-354">Oracle E-business Suite から通知メッセージを受信するため、PROCESS_RECORDS プロシージャを実行するために、BizTalk アプリケーションを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="120ae-354">You must start the BizTalk application for receiving notification messages from Oracle E-Business Suite and for executing the PROCESS_RECORDS procedure.</span></span> <span data-ttu-id="120ae-355">BizTalk アプリケーションを開始する手順についてで「する方法をオーケストレーションの開始」を参照してください[ http://go.microsoft.com/fwlink/?LinkId=102387](http://go.microsoft.com/fwlink/?LinkId=102387)します。</span><span class="sxs-lookup"><span data-stu-id="120ae-355">For instructions on starting a BizTalk application, see “How to Start an Orchestration” at  [http://go.microsoft.com/fwlink/?LinkId=102387](http://go.microsoft.com/fwlink/?LinkId=102387).</span></span>  
  
 <span data-ttu-id="120ae-356">この段階で、ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="120ae-356">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="120ae-357">Wcf-custom または Wcf-oracleebs 一方向受信ポートが実行されている Oracle E-business Suite から通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="120ae-357">The WCF-Custom or WCF-OracleEBS one-way receive port, which receives the notification messages from Oracle E-Business Suite is running.</span></span>  
  
-   <span data-ttu-id="120ae-358">PROCESS_RECORDS プロシージャを実行するには、Wcf-custom または Wcf-oracleebs 送信ポートが実行されています。</span><span class="sxs-lookup"><span data-stu-id="120ae-358">The WCF-Custom or WCF-OracleEBS send port to execute the PROCESS_RECORDS procedure is running.</span></span>  
  
-   <span data-ttu-id="120ae-359">Oracle E-business Suite からメッセージを受信する、ファイル送信ポートが実行されています。</span><span class="sxs-lookup"><span data-stu-id="120ae-359">The FILE send port, which receives messages from Oracle E-Business Suite, is running.</span></span>  
  
-   <span data-ttu-id="120ae-360">操作の BizTalk オーケストレーションが実行されています。</span><span class="sxs-lookup"><span data-stu-id="120ae-360">The BizTalk orchestration for the operation is running.</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="120ae-361">操作の実行</span><span class="sxs-lookup"><span data-stu-id="120ae-361">Executing the Operation</span></span>  
 <span data-ttu-id="120ae-362">ACCOUNTACTIVITY テーブルが既にレコードの一部であると仮定します。</span><span class="sxs-lookup"><span data-stu-id="120ae-362">Assume that the ACCOUNTACTIVITY table already has some records.</span></span> <span data-ttu-id="120ae-363">また、C:\TestLocation\MessageIn で使用される PROCESS_RECORDS プロシージャを実行する XML メッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="120ae-363">Also, make sure the XML message to execute PROCESS_RECORDS procedure is available at C:\TestLocation\MessageIn.</span></span> <span data-ttu-id="120ae-364">XML ファイルは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="120ae-364">The XML file should resemble the following:</span></span>  
  
```  
<PROCESS_RECORDS xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/SCOTT/ACCOUNT_PKG" />  
```  
  
 <span data-ttu-id="120ae-365">BizTalk オーケストレーションを開始すると、次の一連のアクションが、同じシーケンス内の場所。</span><span class="sxs-lookup"><span data-stu-id="120ae-365">Once the BizTalk orchestration is started, the following set of actions take place, in the same sequence:</span></span>  
  
-   <span data-ttu-id="120ae-366">アダプターは、次のような通知メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="120ae-366">The adapter receives a notification message that resembles the following:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
      <Info>ListenerStarted</Info>   
      <Source>OracleEBSBinding</Source>   
      <Type>Startup</Type>   
    </Notification>  
    ```  
  
     <span data-ttu-id="120ae-367">このメッセージは、通知メッセージを受信する受信ポートが開始されたことを通知します。</span><span class="sxs-lookup"><span data-stu-id="120ae-367">This message notifies that the receive port for receiving the notification messages is started.</span></span> <span data-ttu-id="120ae-368">注意の値、`<Info>`要素は、"ListnerStarted"。</span><span class="sxs-lookup"><span data-stu-id="120ae-368">Note that the value for the `<Info>` element is “ListnerStarted”.</span></span>  
  
-   <span data-ttu-id="120ae-369">アダプターは、PROCESS_RECORDS プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="120ae-369">The adapter executes the PROCESS_RECORDS procedure.</span></span> <span data-ttu-id="120ae-370">Oracle E-business Suite から [次へ] の応答は、手順についてはします。</span><span class="sxs-lookup"><span data-stu-id="120ae-370">The next response from Oracle E-Business Suite is for the procedure.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <PROCESS_RECORDSResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/SCOTT/ACCOUNT_PKG">  
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
  
     <span data-ttu-id="120ae-371">これは、PROCESS_RECORDS プロシージャの一部として、SELECT ステートメントを実行するための応答です。</span><span class="sxs-lookup"><span data-stu-id="120ae-371">This is the response for the SELECT statement execute as part of the PROCESS_RECORDS procedure.</span></span>  
  
-   <span data-ttu-id="120ae-372">PROCESS_RECORDS プロシージャでは、処理を 'y' に設定する行も更新されます。</span><span class="sxs-lookup"><span data-stu-id="120ae-372">The PROCESS_RECORDS procedure also updates the rows to set PROCESSED to ‘y’.</span></span> <span data-ttu-id="120ae-373">そのため、アダプターは、更新操作に別の通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="120ae-373">Hence, the adapter receives another notification for the Update operation.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/">  
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
  
     <span data-ttu-id="120ae-374">なお、`Info`要素には、"Update"が含まれています。</span><span class="sxs-lookup"><span data-stu-id="120ae-374">Note that the `Info` element contains “Update”.</span></span>  
  
-   <span data-ttu-id="120ae-375">2 つ目の通知後に、アダプターでは、PROCESS_RECORDS プロシージャがもう一度実行します。</span><span class="sxs-lookup"><span data-stu-id="120ae-375">After the second notification, the adapter again executes the PROCESS_RECORDS procedure.</span></span> <span data-ttu-id="120ae-376">ただし、今すぐに処理された列が設定されているレコードがないため、' n '、プロシージャは、次のような空の応答を返します。</span><span class="sxs-lookup"><span data-stu-id="120ae-376">However, now because there are no records where PROCESSED column is set to ‘n’, the procedure returns an empty response resembling the following.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <PROCESS_RECORDSResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/SCOTT/ACCOUNT_PKG">  
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
  
## <a name="best-practices"></a><span data-ttu-id="120ae-377">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="120ae-377">Best Practices</span></span>  
 <span data-ttu-id="120ae-378">展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="120ae-378">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the binding file.</span></span> <span data-ttu-id="120ae-379">バインド ファイルを生成した、送信ポートを作成し、同じオーケストレーション用のポートを受信する必要はありませんように構成設定、ファイルからインポートできます。</span><span class="sxs-lookup"><span data-stu-id="120ae-379">Once you generate a binding file, you can import the configuration settings from the file, so that you do not need to create the send ports and receive ports for the same orchestration.</span></span> <span data-ttu-id="120ae-380">バインド ファイルの詳細については、次を参照してください。 [Oracle E-business suite アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)します。</span><span class="sxs-lookup"><span data-stu-id="120ae-380">For more information about binding files, see [Reuse Adapter Bindings with Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="120ae-381">参照</span><span class="sxs-lookup"><span data-stu-id="120ae-381">See Also</span></span>  
 [<span data-ttu-id="120ae-382">Oracle E-business Suite データベース変更通知 BizTalk Server を使用しての受信します。</span><span class="sxs-lookup"><span data-stu-id="120ae-382">Receive Oracle E-Business Suite Database Change Notifications using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-biztalk-server.md)