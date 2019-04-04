---
title: BizTalk Server を使用して Oracle データベースの変更通知の受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 495a29bc-72f6-4140-8160-0b917d935503
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8bd67791e56d941d58cb0b221bf7ad63bb3778f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985043"
---
# <a name="receive-oracle-database-change-notifications-using-biztalk-server"></a><span data-ttu-id="b202d-102">BizTalk Server を使用して Oracle データベースの変更通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="b202d-102">Receive Oracle Database Change Notifications Using BizTalk Server</span></span>
<span data-ttu-id="b202d-103">構成することができます、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースからデータベース変更通知のメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="b202d-103">You can configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to receive database change notification messages from the Oracle database.</span></span> <span data-ttu-id="b202d-104">アダプターが Oracle データベースを使用した通知の登録を使用する SELECT ステートメントを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="b202d-104">You can specify a SELECT statement that the adapter uses to register for notifications with the Oracle database.</span></span> <span data-ttu-id="b202d-105">登録通知の場合、SELECT ステートメントの結果セットが変更されたときに通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="b202d-105">The adapter receives a notification message when the result set for the SELECT statement, registered for notification, changes.</span></span> <span data-ttu-id="b202d-106">アダプターが通知をサポートする方法の詳細については、[データベース変更通知の受信、Oracle データベース アダプターの使用に関する考慮事項](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b202d-106">For more information about how the adapter supports notification, see [Considerations for Receiving Database Change Notifications using the Oracle Database Adapter](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md).</span></span>  
  
 <span data-ttu-id="b202d-107">構成することがいくつかのシナリオを次に、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Oracle データベースから通知を受け取る。</span><span class="sxs-lookup"><span data-stu-id="b202d-107">Following are some scenarios in which you can configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] to receive notifications from the Oracle database:</span></span>  
  
- <span data-ttu-id="b202d-108">アダプター クライアントの最後の通知以降、データベース テーブルに加えられたこれらの変更だけなど「インクリメント」の通知のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="b202d-108">Adapter clients get only “incremental” notification, for example, only for those changes that were made to a database table since the last notification.</span></span>  
  
- <span data-ttu-id="b202d-109">アダプター クライアントが複数を構成する場合は、データベース テーブルに多数の行を挿入して、受信負荷分散通知を受信する場所。</span><span class="sxs-lookup"><span data-stu-id="b202d-109">If large number of rows are inserted into a database table, the adapter clients can configure multiple receive locations to load-balance receiving notifications.</span></span>  
  
  <span data-ttu-id="b202d-110">アダプターのクライアントは、通知メッセージを受信、受信した通知の種類に基づいて特定のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b202d-110">Once the adapter clients receive a notification message, they can perform specific tasks based on the kind of notification received.</span></span> <span data-ttu-id="b202d-111">たとえばが実行される挿入の通知を受信した場合、タスクの 1 つのセットと別の一連のタスク、更新通知を受信した場合は、このような方法で、BizTalk オーケストレーションを設計できます。</span><span class="sxs-lookup"><span data-stu-id="b202d-111">For example, a BizTalk orchestration can be designed in such a way that it performs one set of tasks if an insert notification is received and another set of tasks if an update notification is received.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="b202d-112">Oracle データベースとアダプター クライアントの間のネットワークの停止がある場合、通知は送信されませんアダプター クライアントのネットワークの停止の期間中に Oracle データベースで行われた変更で、その後です。</span><span class="sxs-lookup"><span data-stu-id="b202d-112">If there is a network outage between the Oracle database and the adapter client, the notifications will not be sent to the adapter clients for the changes done on the Oracle database during the period of network outage, and thereafter.</span></span> <span data-ttu-id="b202d-113">したがって、重要なシナリオの通知の操作ではなく、ポーリング操作を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b202d-113">Therefore, you must use the Polling operation instead of the Notification operation for critical scenarios.</span></span>  
  
 <span data-ttu-id="b202d-114">このセクションのトピックでは、これらの各シナリオのアダプターを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b202d-114">The topics in this section provide information on how to configure the adapter for each of these scenarios.</span></span> <span data-ttu-id="b202d-115">使用して Oracle データベースからの通知の取得を開始する、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、特定のバインド プロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b202d-115">To start getting notifications from the Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], you must specify certain binding properties.</span></span> <span data-ttu-id="b202d-116">通知に関連するバインド プロパティの詳細については、[バインドのプロパティの操作](https://msdn.microsoft.com/library/dd788467.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b202d-116">For more information about the binding properties related to notifications, see [Working with binding properties](https://msdn.microsoft.com/library/dd788467.aspx).</span></span> <span data-ttu-id="b202d-117">通知メッセージの構造に関する詳細については、[通知操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-notification-operation1.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b202d-117">For more information about structure of notification messages, see [Message Schemas for the Notification Operation](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-notification-operation1.md).</span></span>  
  
 <span data-ttu-id="b202d-118">Oracle データベースから通知を受信することを確認します。</span><span class="sxs-lookup"><span data-stu-id="b202d-118">For receiving notifications from the Oracle database, make sure:</span></span>  
  
-   <span data-ttu-id="b202d-119">10.2 以降の Oracle データベースのバージョンに接続するには、アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b202d-119">You use the adapter to connect to Oracle database version 10.2 or later.</span></span> <span data-ttu-id="b202d-120">10.2 より前の oracle データベースのバージョンでは、通知はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="b202d-120">Oracle database versions prior to 10.2 do not support notifications.</span></span>  
  
-   <span data-ttu-id="b202d-121">通知の Oracle への接続に使用する資格情報が`change notification`特権。</span><span class="sxs-lookup"><span data-stu-id="b202d-121">The credentials you use to connect to Oracle for notifications has `change notification` privilege.</span></span> <span data-ttu-id="b202d-122">この特権は、データベース変更通知を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="b202d-122">This privilege is required for receiving database change notifications.</span></span> <span data-ttu-id="b202d-123">これを行うには、管理者特権を使用して Oracle データベースへの接続し、SQL プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b202d-123">To do so, connect to Oracle database using administrative privileges and then type the following command on the SQL prompt.</span></span>  
  
    ```  
    grant change notification to <user name>  
    ```  
  
-   <span data-ttu-id="b202d-124">Oracle データベースからデータベース変更通知を受信するために使用する ODP.NET する TCP ポートで決定します。</span><span class="sxs-lookup"><span data-stu-id="b202d-124">Decide on a TCP port you want ODP.NET to use for receiving database change notifications from Oracle database.</span></span> <span data-ttu-id="b202d-125">Windows ファイアウォールの例外リストには、そのポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="b202d-125">Add that port to Windows Firewall exceptions list.</span></span> <span data-ttu-id="b202d-126">Windows ファイアウォールの例外リストにポートを追加する方法については、[ http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b202d-126">For instructions on how to add ports to Windows Firewall exceptions list, see [http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959).</span></span> <span data-ttu-id="b202d-127">同じポート番号を指定する必要があります、 **NotificationPort**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="b202d-127">You must provide the same port number for the **NotificationPort** binding property.</span></span> <span data-ttu-id="b202d-128">バインディング プロパティの詳細については、[バインドのプロパティの操作](https://msdn.microsoft.com/library/dd788467.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b202d-128">For more information about the binding property, see [Working with binding properties](https://msdn.microsoft.com/library/dd788467.aspx).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b202d-129">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b202d-129">In This Section</span></span>  
  
-   [<span data-ttu-id="b202d-130">Oracle データベース アダプターを使用して、データベース変更通知を受信するための考慮事項</span><span class="sxs-lookup"><span data-stu-id="b202d-130">Considerations for Receiving Database Change Notifications Using the Oracle Database Adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)  
  
-   [<span data-ttu-id="b202d-131">BizTalk Server を使用して Oracle データベースで特定のタスクを実行する通知メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="b202d-131">Processing Notification Messages to Complete Specific Tasks in Oracle Database using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md)  
  
-   [<span data-ttu-id="b202d-132">段階的に BizTalk Server を使用して Oracle データベースの変更通知を受け取る</span><span class="sxs-lookup"><span data-stu-id="b202d-132">Receiving Oracle Database Change Notifications Incrementally Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md)  
  
-   [<span data-ttu-id="b202d-133">複数の受信側の Oracle データベースの変更通知の受信場所</span><span class="sxs-lookup"><span data-stu-id="b202d-133">Receiving Oracle Database Change Notifications On Multiple Receive Locations</span></span>](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-on-multiple-receive-locations.md)  
  
-   [<span data-ttu-id="b202d-134">後の Oracle データベース変更通知を受信する受信場所のブレーク ダウン</span><span class="sxs-lookup"><span data-stu-id="b202d-134">Receiving Oracle Database Change Notifications After a Receive Location Breakdown</span></span>](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-after-a-receive-location-breakdown.md)  
  
## <a name="see-also"></a><span data-ttu-id="b202d-135">参照</span><span class="sxs-lookup"><span data-stu-id="b202d-135">See Also</span></span>  
[<span data-ttu-id="b202d-136">Oracle データベースと BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="b202d-136">Building Blocks to Develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)