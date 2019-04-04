---
title: メッセージ ボックス データベースを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, MessageBox database
- managing [MessageBox database], deleting
- MessageBox database, deleting
ms.assetid: 51f91fcb-8b97-4b00-9056-6d216c8ccb58
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a025ea29e13ef938a39f9555785177f2c64e922
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023600"
---
# <a name="how-to-delete-a-messagebox-database"></a><span data-ttu-id="723de-102">メッセージ ボックス データベースを削除する方法</span><span class="sxs-lookup"><span data-stu-id="723de-102">How to Delete a MessageBox Database</span></span>
<span data-ttu-id="723de-103">BizTalk グループからメッセージ ボックス データベースを削除するには、BizTalk 管理コンソールまたは Windows Management Instrumentation (WMI) を使用します。</span><span class="sxs-lookup"><span data-stu-id="723de-103">You use the BizTalk Administration Console or Windows Management Instrumentation (WMI) to remove a MessageBox database from a BizTalk group.</span></span> <span data-ttu-id="723de-104">メッセージ ボックス データベースは BizTalk グループから削除するか、または BizTalk Server の展開から完全に削除することができます。</span><span class="sxs-lookup"><span data-stu-id="723de-104">You can remove a MessageBox database from a BizTalk group, or you can delete it from your BizTalk Server deployment entirely.</span></span>  
  
 <span data-ttu-id="723de-105">たとえば、テスト目的に使用したデータベースなど、使用しなくなったメッセージ ボックス データベースを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="723de-105">For example, you can delete a MessageBox database you are no longer using, such as a database used for testing purposes.</span></span>  
  
 <span data-ttu-id="723de-106">BizTalk Server の展開からメッセージ ボックス データベースを完全に削除するには、次の 8 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="723de-106">There are eight steps to permanently and completely removing MessageBox databases from your BizTalk Server deployment:</span></span>  
  
1.  <span data-ttu-id="723de-107">新しいメッセージの公開を無効にします。</span><span class="sxs-lookup"><span data-stu-id="723de-107">Disable new message publication.</span></span>  
  
     <span data-ttu-id="723de-108">メッセージ ボックス データベースを削除する前に、新しいメッセージの公開を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="723de-108">You must disable the publication of new messages before you delete a MessageBox database.</span></span> <span data-ttu-id="723de-109">新しいメッセージの公開を無効にする方法については、[新しいメッセージの公開を無効にする方法](../core/how-to-disable-new-message-publication.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="723de-109">For information about disabling new message publication, see [How to Disable New Message Publication](../core/how-to-disable-new-message-publication.md).</span></span>  
  
2.  <span data-ttu-id="723de-110">キャッシュ更新間隔に指定した時間が経過するまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="723de-110">Wait for the cache refresh interval to expire.</span></span>  
  
     <span data-ttu-id="723de-111">新しいメッセージの公開を無効にした後、データベースをすぐに削除することはできず、待機時間が発生します。</span><span class="sxs-lookup"><span data-stu-id="723de-111">After you disable the publication of new messages, you must wait before you delete the database.</span></span> <span data-ttu-id="723de-112">待機時間は、CacheRefreshInterval の 2 倍の長さとして定義されています。</span><span class="sxs-lookup"><span data-stu-id="723de-112">The wait time is defined as twice the length of the CacheRefreshInterval.</span></span> <span data-ttu-id="723de-113">CacheRefreshInterval の既定値は 60 秒です。</span><span class="sxs-lookup"><span data-stu-id="723de-113">The default value of CacheRefreshInterval is 60 seconds.</span></span> <span data-ttu-id="723de-114">使用する、**グループ プロパティ**キャッシュ更新間隔を変更するダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="723de-114">You use the **Group Properties** dialog box to change the Cache Refresh.</span></span>  
  
3.  <span data-ttu-id="723de-115">BizTalk グループからメッセージ ボックス データベースを削除します。</span><span class="sxs-lookup"><span data-stu-id="723de-115">Remove the MessageBox database from the BizTalk Group.</span></span>  
  
     <span data-ttu-id="723de-116">BizTalk グループからメッセージ ボックス データベースを削除すると、BizTalk 管理データベースからメッセージ ボックス データベースの参照が削除されます。</span><span class="sxs-lookup"><span data-stu-id="723de-116">Removing the MessageBox database from the BizTalk Group removes the MessageBox reference from the BizTalk Management database.</span></span>  
  
4.  <span data-ttu-id="723de-117">削除したメッセージ ボックス データベースへのキャッシュされた接続を含むホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="723de-117">Restart host instances that contain cached connections to the MessageBox database.</span></span>  
  
     <span data-ttu-id="723de-118">ホスト インスタンスにランタイム エンジンからキャッシュされたデータベースへの接続がある場合、データベースを SQL Server から物理的に削除する前に、ホスト インスタンスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="723de-118">You must restart the host instance before physically deleting the database from SQL Server if cached database connections from the run-time engine are present.</span></span> <span data-ttu-id="723de-119">ホスト インスタンスの開始方法の詳細については、[ホスト インスタンスを開始する方法](../core/how-to-start-a-host-instance.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="723de-119">For information about starting a host instance, see [How to Start a Host Instance](../core/how-to-start-a-host-instance.md).</span></span>  
  
5.  <span data-ttu-id="723de-120">データベースにアクセスする、実行中のホスト インスタンスをすべて停止します。</span><span class="sxs-lookup"><span data-stu-id="723de-120">Stop all in-progress host instances that access the database.</span></span> <span data-ttu-id="723de-121">実行中のホスト インスタンスを停止する方法の詳細については、[ホスト インスタンスを停止する方法](../core/how-to-stop-a-host-instance.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="723de-121">For information about stopping an in-progress host instance, see [How to Stop a Host Instance](../core/how-to-stop-a-host-instance.md).</span></span>  
  
     <span data-ttu-id="723de-122">プライマリ以外のメッセージ ボックス データベースを削除する場合は、実行中のホスト インスタンスを停止する前に、そのメッセージ ボックスへの新しいメッセージの公開を無効にして、次の点を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="723de-122">If you are removing a non-primary MessageBox database, before stopping an in-progress host instance, you should first disable publication of new messages to that message box and make sure that:</span></span>  
  
    -   <span data-ttu-id="723de-123">メッセージ ボックスに実行中のサービス インスタンスがないこと。</span><span class="sxs-lookup"><span data-stu-id="723de-123">There are no running service instances remaining in the message box.</span></span>  
  
    -   <span data-ttu-id="723de-124">メッセージ ボックスに中断されたインスタンスやその他のインスタンスが残っていないこと。</span><span class="sxs-lookup"><span data-stu-id="723de-124">There are no suspended (or any other remaining) instances left in the message box.</span></span>  
  
    -   <span data-ttu-id="723de-125">BAM 追跡データが BizTalk 追跡 (BizTalkDTADb) データベースに移動されている (TrackingData テーブルが空になっている) こと。</span><span class="sxs-lookup"><span data-stu-id="723de-125">BAM tracked data has been moved to the BizTalk Tracking (BizTalkDTADb) database (TrackingData table should be empty).</span></span>  
  
    -   <span data-ttu-id="723de-126">追跡メッセージ本文が BizTalk 追跡 (BizTalkDTADb) データベースに移動されていること。</span><span class="sxs-lookup"><span data-stu-id="723de-126">Tracked message bodies have been moved to the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
6.  <span data-ttu-id="723de-127">バックグラウンドで実行されている SQL Server エージェントのジョブが完了していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="723de-127">Ensure that the background SQL Server Agent job is finished.</span></span>  
  
     <span data-ttu-id="723de-128">メッセージ ボックス データベースを BizTalk Server の展開から完全に削除する前に、バックグラウンドで実行中の SQL Server エージェントのジョブが追跡されたメッセージ本文をすべて TrackingSpool テーブルに転送し終えたことを確認し、TrackingSpool テーブルをバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="723de-128">Before you permanently delete a MessageBox database from your BizTalk Server deployment, you should first ensure that the background SQL Server Agent job has finished transferring all tracked message bodies to the TrackingSpool table, and then back up the TrackingSpool tables.</span></span> <span data-ttu-id="723de-129">バックグラウンドで実行中の SQL Server エージェントのジョブの状態を確認する方法の詳細については、SQL Server Books Online を参照してください。</span><span class="sxs-lookup"><span data-stu-id="723de-129">For information about checking the status of a background SQL Server Agent job, see SQL Server Books Online.</span></span>  
  
7.  <span data-ttu-id="723de-130">TrackingSpool テーブルをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="723de-130">Back up the TrackingSpool tables.</span></span>  
  
     <span data-ttu-id="723de-131">追跡されたメッセージ本文は、TrackingSpool テーブルを外部の記憶域にバックアップするまで、メッセージ ボックス データベースから削除されません。</span><span class="sxs-lookup"><span data-stu-id="723de-131">Tracked message bodies remain in the MessageBox database until you manually back up the TrackingSpool tables into external storage.</span></span> <span data-ttu-id="723de-132">バックアップを行う前に、バックグラウンドで実行中の SQL Server エージェントのジョブにより、Spool テーブルから TrackingSpool テーブルにメッセージ本文が転送されます。</span><span class="sxs-lookup"><span data-stu-id="723de-132">Before the backup happens, a background SQL Server Agent job transfers the message bodies from the Spool table to the TrackingSpool table.</span></span> <span data-ttu-id="723de-133">手動による SQL Server テーブルのバックアップの詳細については、SQL Server Books Online を参照してください。</span><span class="sxs-lookup"><span data-stu-id="723de-133">For information about manually backing up SQL Server tables, see SQL Server Books Online.</span></span>  
  
8.  <span data-ttu-id="723de-134">SQL Server からデータベースを削除します。</span><span class="sxs-lookup"><span data-stu-id="723de-134">Remove the database from SQL Server.</span></span>  
  
     <span data-ttu-id="723de-135">メッセージ ボックス データベースは、BizTalk グループから削除しても、Microsoft SQL Server から物理的に削除されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="723de-135">Deleting a MessageBox database from a BizTalk Group does not physically remove the database from Microsoft SQL Server.</span></span> <span data-ttu-id="723de-136">メッセージ ボックス データベースを完全に削除するには、BizTalk グループからデータベースを削除した後に SQL Server Enterprise Manager または SQL Server Management Studio を使用してデータベースを削除します。</span><span class="sxs-lookup"><span data-stu-id="723de-136">To permanently delete the MessageBox database, you must remove it by using SQL Server Enterprise Manager or SQL Server Management Studio after it is removed from the BizTalk Group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="723de-137">前提条件</span><span class="sxs-lookup"><span data-stu-id="723de-137">Prerequisites</span></span>  
 <span data-ttu-id="723de-138">メッセージ ボックス データベースを管理する管理者は、必要なユーザー権利が必要です。</span><span class="sxs-lookup"><span data-stu-id="723de-138">Administrators who manage MessageBox databases must have the required user rights.</span></span> <span data-ttu-id="723de-139">メッセージ ボックス データベースの管理と新しいメッセージの公開の無効化には、次のユーザー権利が必要です。</span><span class="sxs-lookup"><span data-stu-id="723de-139">You must have the following user rights to manage MessageBox databases and disable new message publication:</span></span>  
  
-   <span data-ttu-id="723de-140">BizTalk Server Administrators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="723de-140">You must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
-   <span data-ttu-id="723de-141">データベースが存在するコンピューターの SQL Server 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="723de-141">You must be a SQL Server Administrator on the computer where the database exists.</span></span>  
  
### <a name="to-delete-a-messagebox-database-from-a-biztalk-group"></a><span data-ttu-id="723de-142">BizTalk グループからメッセージ ボックス データベースを削除するには</span><span class="sxs-lookup"><span data-stu-id="723de-142">To delete a MessageBox database from a BizTalk Group</span></span>  
  
1. <span data-ttu-id="723de-143">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="723de-143">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="723de-144">コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)][BizTalk グループ]、をクリックして**プラットフォームの設定**、 をクリックし、**メッセージ ボックス**します。</span><span class="sxs-lookup"><span data-stu-id="723de-144">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, click **Platform Settings**, and then click **Message Boxes**.</span></span>  
  
3. <span data-ttu-id="723de-145">詳細ウィンドウで、削除、およびクリックするメッセージ ボックス データベースを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="723de-145">In the details pane, right-click the message box database you want to remove, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="723de-146">**メッセージ ボックスのプロパティ**ダイアログ ボックスで、**新しいメッセージの公開を無効にする**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="723de-146">In the **Message Box Properties** dialog box, select the **Disable new message publication** check box.</span></span>  
  
5. <span data-ttu-id="723de-147">BizTalk Server 管理コンソールの [グループ ハブ] ページを使用して、削除するメッセージ ボックス データベースに退避または中断されたメッセージ インスタンスがないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="723de-147">Use the Group Hub page in the BizTalk Server Administration Console to verify that no message instances are dehydrated or suspended on the MessageBox database you are deleting.</span></span>  
  
6. <span data-ttu-id="723de-148">CacheRefreshInterval の 2 倍 の長さの時間待機します。</span><span class="sxs-lookup"><span data-stu-id="723de-148">Wait for a period of time twice the length of the CacheRefreshInterval.</span></span> <span data-ttu-id="723de-149">CacheRefreshInterval の既定値は 60 秒です。</span><span class="sxs-lookup"><span data-stu-id="723de-149">The default value of CacheRefreshInterval is 60 seconds.</span></span>  
  
7. <span data-ttu-id="723de-150">詳細ウィンドウで、削除、およびをクリックするメッセージ ボックス データベースを右クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="723de-150">In the details pane, right-click the MessageBox database that you want to delete, and click **Delete**.</span></span>  
  
8. <span data-ttu-id="723de-151">警告メッセージを読み、次のようにクリックします。 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="723de-151">After reading the warning message, click **OK**.</span></span>  
  
9. <span data-ttu-id="723de-152">コンソール ツリーで BizTalk グループ、をクリックして**プラットフォームの設定**、 をクリックし、**ホスト インスタンス**します。</span><span class="sxs-lookup"><span data-stu-id="723de-152">In the console tree, expand the BizTalk group, click **Platform Settings**, and then click **Host Instances**.</span></span>  
  
10. <span data-ttu-id="723de-153">詳細ペインで、実行中のホスト インスタンスを右クリックし、停止してから再起動します (この操作は、実行中のすべてのホスト インスタンスに対して行います)。</span><span class="sxs-lookup"><span data-stu-id="723de-153">In the details pane, right-click all running host instances, and stop and restart each one.</span></span>  
  
11. <span data-ttu-id="723de-154">メッセージ ボックス データベースが存在するサーバーで、使用している SQL Server のバージョンに応じて SQL Server Enterprise Manager または SQL Server Management Studio を開き、データベースを削除します。</span><span class="sxs-lookup"><span data-stu-id="723de-154">On the server where the MessageBox database resides, open SQL Server Enterprise Manager or SQL Server Management Studio, depending on which version of SQL Server you are using, and then delete the database.</span></span>  
  
     <span data-ttu-id="723de-155">SQL Server でデータベースを削除する方法の詳細については、SQL Server Books Online を参照してください。</span><span class="sxs-lookup"><span data-stu-id="723de-155">For information about how to delete a database in SQL Server, see SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="723de-156">参照</span><span class="sxs-lookup"><span data-stu-id="723de-156">See Also</span></span>  
 <span data-ttu-id="723de-157">[メッセージ ボックス データベースの管理](../core/managing-messagebox-databases.md) </span><span class="sxs-lookup"><span data-stu-id="723de-157">[Managing MessageBox Databases](../core/managing-messagebox-databases.md) </span></span>  
 <span data-ttu-id="723de-158">[新しいメッセージ ボックス データベースを追加する方法](../core/how-to-add-a-new-messagebox-database.md) </span><span class="sxs-lookup"><span data-stu-id="723de-158">[How to Add a New MessageBox Database](../core/how-to-add-a-new-messagebox-database.md) </span></span>  
 <span data-ttu-id="723de-159">[新しいメッセージの公開を無効にする方法](../core/how-to-disable-new-message-publication.md) </span><span class="sxs-lookup"><span data-stu-id="723de-159">[How to Disable New Message Publication](../core/how-to-disable-new-message-publication.md) </span></span>  
 [<span data-ttu-id="723de-160">メッセージ ボックス データベース</span><span class="sxs-lookup"><span data-stu-id="723de-160">The MessageBox Database</span></span>](../core/the-messagebox-database.md)