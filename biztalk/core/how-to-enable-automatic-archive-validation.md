---
title: "アーカイブの自動検証を有効にする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validating, archives [Tracking database]
- archiving [Tracking database], validating archive
ms.assetid: 406ca54a-6b1f-4bdb-9bad-bea5ea0f6e66
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 258fcb96bbb9bbb045aeb3f48c2b324502d44940
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-automatic-archive-validation"></a><span data-ttu-id="668a3-102">アーカイブの自動検証を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="668a3-102">How to Enable Automatic Archive Validation</span></span>
<span data-ttu-id="668a3-103">アーカイブ検証を使用すると、アーカイブを作成時に検証することができます。</span><span class="sxs-lookup"><span data-stu-id="668a3-103">Archive validation enables you to validate the archives as they are created.</span></span> <span data-ttu-id="668a3-104">アーカイブの自動検証を有効にするには、セカンダリ データベース サーバー (検証サーバー) をセットアップしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="668a3-104">Before you can enable automatic archive validation, you must set up a secondary database server, also called a validation server.</span></span> <span data-ttu-id="668a3-105">アーカイブ プロセスは単純なバックアップなので、ハードウェアの問題で、ディスク上に格納される実際のイメージが破損する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="668a3-105">Because the archiving process is a simple backup, it is possible that the actual image stored on the disk can be corrupted due to a hardware issue.</span></span>  
  
 <span data-ttu-id="668a3-106">アーカイブ検証機能を使用することで、アーカイブ (バックアップ) が正常に行われ、復元できることを保証できます。</span><span class="sxs-lookup"><span data-stu-id="668a3-106">Using the archive validation feature, you can ensure the archive (backup) was successful and can be restored.</span></span> <span data-ttu-id="668a3-107">アーカイブが作成されると、新しいアーカイブが作成されたことが検証サーバーに通知されます。</span><span class="sxs-lookup"><span data-stu-id="668a3-107">After an archive is created, the validation server is notified that a new archive has been created.</span></span> <span data-ttu-id="668a3-108">検証サーバーではそのアーカイブの復元が試行されます。</span><span class="sxs-lookup"><span data-stu-id="668a3-108">The validation server attempts to restore the archive.</span></span> <span data-ttu-id="668a3-109">検証サーバーは、ジョブを実行しているものとは別の [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] インスタンスにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="668a3-109">A validation server must be another instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] different from the one in which the job is running.</span></span> <span data-ttu-id="668a3-110">検証サーバー上の [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] のバージョンは、データベースをホストするために使用されている [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] と同じバージョンである必要があります。</span><span class="sxs-lookup"><span data-stu-id="668a3-110">The version of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] on the validation server must be the same version as the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] used to host the databases.</span></span>  
  
 <span data-ttu-id="668a3-111">検証サーバーで復元が正常に行われると、その情報が BizTalk 追跡 (BizTalkDTADb) データベースに返送されます。</span><span class="sxs-lookup"><span data-stu-id="668a3-111">If the restore is successful, the validation server communicates this information back to the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="668a3-112">復元が正常に完了するまでは、Purge ジョブによってそれ以上データが削除されません。</span><span class="sxs-lookup"><span data-stu-id="668a3-112">Until a successful restore is completed, the purge job will not purge any more data.</span></span>  
  
 <span data-ttu-id="668a3-113">検証サーバーで復元が正常に行われないと、その情報が BizTalk 追跡データベースに返送されます。</span><span class="sxs-lookup"><span data-stu-id="668a3-113">If the restore is not successful, the validation server communicates this information back to the BizTalk Tracking database.</span></span> <span data-ttu-id="668a3-114">その結果、Purge ジョブは別のアーカイブを作成し、新しいアーカイブの検証が完了するのを待機します。</span><span class="sxs-lookup"><span data-stu-id="668a3-114">The purge job creates another archive and awaits validation of the new archive.</span></span> <span data-ttu-id="668a3-115">これにより、アーカイブの破損によって追跡データが失われるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="668a3-115">This prevents the possibility of a corrupted archive causing you to lose tracking data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="668a3-116">前提条件</span><span class="sxs-lookup"><span data-stu-id="668a3-116">Prerequisites</span></span>  
 <span data-ttu-id="668a3-117">この手順を実行するには、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定サーバー ロールのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="668a3-117">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-enable-automatic-archive-validation"></a><span data-ttu-id="668a3-118">アーカイブの自動検証を有効にするには</span><span class="sxs-lookup"><span data-stu-id="668a3-118">To enable automatic archive validation</span></span>  
  
1.  <span data-ttu-id="668a3-119">検証サーバーで、をクリックして**開始**をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP2**、順にクリック**SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="668a3-119">On the validation server, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="668a3-120">**サーバーへの接続** ダイアログ ボックスで、指定の名前、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]する復元プロセスのテストを実行してアーカイブし、をクリックして**接続**への接続に、適切な SQL Server。</span><span class="sxs-lookup"><span data-stu-id="668a3-120">In the **Connect to Server** dialog box, specify the name of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] where you can validate the archive by performing a test of the restore process, and then click **Connect** to connect to the appropriate SQL Server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="668a3-121">アーカイブを検証しているときにシステム パフォーマンスが低下するため、このサーバーを別の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベース サーバーにはしないでください。</span><span class="sxs-lookup"><span data-stu-id="668a3-121">This server should not be another [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database server as it reduces system performance when validating the archive.</span></span>  
  
3.  <span data-ttu-id="668a3-122">**Microsoft SQL Server Management Studio**、 をクリックして**ファイル**、 をクリックして**開く**、クリックして**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="668a3-122">In **Microsoft SQL Server Management Studio**, click **File**, click **Open**, and then click **File**.</span></span>  
  
4.  <span data-ttu-id="668a3-123">**ファイルを開く** ダイアログ ボックスで、次の SQL スクリプトを参照します。</span><span class="sxs-lookup"><span data-stu-id="668a3-123">In the **Open File** dialog box, browse to the following SQL script:</span></span>  
  
    ```  
    %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\BTS_Tracking_ValidateArchive.sql  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="668a3-124">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を実行しているコンピューターから検証サーバーにスクリプトをコピーする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="668a3-124">You might need to copy the script from the computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to the validation server.</span></span>  
  
5.  <span data-ttu-id="668a3-125">クリックして、**クエリ** メニューをクリックして**Execute**です。</span><span class="sxs-lookup"><span data-stu-id="668a3-125">Click the **Query** menu, and then click **Execute**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="668a3-126">BTS_Tracking_ValidateArchive.sql スクリプトは、BizTalk 追跡 (BizTalkDTADb) データベースをアーカイブしているフォルダーがネットワーク共有の場合のみ機能します。</span><span class="sxs-lookup"><span data-stu-id="668a3-126">The BTS_Tracking_ValidateArchive.sql script only works if the folder where you are archiving your BizTalk Tracking (BizTalkDTADb) database is a network share.</span></span>  
  
     <span data-ttu-id="668a3-127">この BTS_Tracking_ValidateArchive.sql スクリプトによって、ValidateArchive という SQL Server エージェント ジョブが作成されます。</span><span class="sxs-lookup"><span data-stu-id="668a3-127">The BTS_Tracking_ValidateArchive.sql script creates a SQL Server Agent job called ValidateArchive.</span></span>  
  
6.  <span data-ttu-id="668a3-128">アーカイブおよび削除のプロセスは可能性のあるに対するアクセスや、別の SQL Server でデータベースを更新するため、関連する SQL Server インスタンス間のリンク サーバーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="668a3-128">The archiving and purging process potentially accesses and/or updates databases in different SQL Servers, so you must set up linked servers between the involved SQL Server instances.</span></span> <span data-ttu-id="668a3-129">**SQL Server Management Studio**をダブルクリックして**Server オブジェクト**を右クリックして**リンク サーバー**、順にクリック**新規リンク サーバー**.</span><span class="sxs-lookup"><span data-stu-id="668a3-129">In **SQL Server Management Studio**, double-click **Server Objects**, right-click **Linked Servers**, and then click **New Linked Server**.</span></span>  
  
     <span data-ttu-id="668a3-130">次のそれぞれの間にリンク サーバーを設定してください。</span><span class="sxs-lookup"><span data-stu-id="668a3-130">You must set up linked server between:</span></span>  
  
    -   <span data-ttu-id="668a3-131">異なるサーバー上に存在する場合は、各 BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースと BizTalk 追跡 (BizTalkDTADb) データベース。</span><span class="sxs-lookup"><span data-stu-id="668a3-131">Each of your BizTalk MessageBox (BizTalkMsgBoxDb) databases and the BizTalk Tracking (BizTalkDTADb) database if they reside on different servers.</span></span>  
  
    -   <span data-ttu-id="668a3-132">BizTalk 追跡 (BizTalkDTADb) データベースとアーカイブ検証用の検証サーバー。</span><span class="sxs-lookup"><span data-stu-id="668a3-132">The BizTalk Tracking (BizTalkDTADb) database and the validating server for archive validation.</span></span>  
  
    -   <span data-ttu-id="668a3-133">BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースをホストしているコンピューター上の SQL Server エージェントのサービス アカウントは、リンク サーバー上の BizTalk 追跡 (BizTalkDTADb) データベースの db_datareader 権限および db_datawriter 権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="668a3-133">The service accounts for the SQL Server Agent on the computer hosting the BizTalk MessageBox (BizTalkMsgBoxDb) database must have the db_datareader and db_datawriter permissions for the BizTalk Tracking (BizTalkDTADb) database on the linked server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="668a3-134">ジョブの実行に使用するアカウントには、両方のデータベースに Database Operator (DBO) 特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="668a3-134">The account used for running the job should have Database Operator (DBO) privileges on both the databases.</span></span>  
  
7.  <span data-ttu-id="668a3-135">**新規リンク サーバー**ダイアログ ボックスの**全般**] ページの [**リンク サーバー**にリンクするサーバーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="668a3-135">In the **New Linked Server** dialog box, on the **General** page, in **Linked server**, enter the name of the server you want to link to.</span></span>  
  
     <span data-ttu-id="668a3-136">たとえば、BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベース、BizTalk 追跡 (BizTalkDTADb) データベース、または検証サーバーをホストしているサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="668a3-136">For example, the server hosting the BizTalk MessageBox (BizTalkMsgBoxDb) database, BizTalk Tracking (BizTalkDTADb) database, or the validation server.</span></span>  
  
8.  <span data-ttu-id="668a3-137">[**サーバーの種類**、] をクリックして**SQL Server**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="668a3-137">Under **Server type**, click **SQL Server**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="668a3-138">**Microsoft SQL Server Management Studio**をダブルクリックして**SQL Server エージェント**、クリックして**ジョブ**です。</span><span class="sxs-lookup"><span data-stu-id="668a3-138">In **Microsoft SQL Server Management Studio**, double-click **SQL Server Agent**, and then click **Jobs**.</span></span>  
  
10. <span data-ttu-id="668a3-139">**オブジェクト エクスプ ローラーの詳細** ウィンドウを右クリックして**ValidateArchive**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="668a3-139">In the **Object Explorer Details** pane, right-click **ValidateArchive**, and then click **Properties**.</span></span>  
  
11. <span data-ttu-id="668a3-140">**ジョブのプロパティ - ValidateArchive**ダイアログ ボックスで、**ページの選択**をクリックして**手順**です。</span><span class="sxs-lookup"><span data-stu-id="668a3-140">In the **Job Properties - ValidateArchive** dialog box, under **Select a page**, click **Steps**.</span></span>  
  
12. <span data-ttu-id="668a3-141">**ジョブ ステップの一覧**、 をクリックして**検証**、クリックして**編集**です。</span><span class="sxs-lookup"><span data-stu-id="668a3-141">In the **Job step list**, click **validate**, and then click **Edit**.</span></span>  
  
13. <span data-ttu-id="668a3-142">**全般**] ページの [、**コマンド**ボックスで、コマンドで、 **exec dtasp_ValidateArchive null の場合、null**、置換 null の場合、null では、BizTalk をホストしているサーバーの名前クリックして、単一引用符、二重引用符で囲まれた、BizTalk 追跡データベースの名前を続けて追跡データベースで囲まれた**OK**です。</span><span class="sxs-lookup"><span data-stu-id="668a3-142">On the **General** page, in the **Command** box, in the command, **exec dtasp_ValidateArchive null, null**, replace null, null with the name of the server hosting the BizTalk Tracking database, surrounded by single quotes, followed by the name of the BizTalk Tracking database, surrounded by quotes, and then click **OK**.</span></span> <span data-ttu-id="668a3-143">例:</span><span class="sxs-lookup"><span data-stu-id="668a3-143">For example:</span></span>  
  
     <span data-ttu-id="668a3-144">**exec dtasp_ValidateArchive '**  *\<TrackingServerName >* **'、'**  *\<TrackingDatabaseName >* **'**</span><span class="sxs-lookup"><span data-stu-id="668a3-144">**exec dtasp_ValidateArchive '** *\<TrackingServerName>* **', '** *\<TrackingDatabaseName>* **'**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="668a3-145">ValidateArchive ジョブにはスケジュールが設定されていません。このジョブのスケジュールは構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="668a3-145">The ValidateArchive job does not have a schedule and you should not configure a schedule for it.</span></span> <span data-ttu-id="668a3-146">代わりに、アーカイブが作成されるときに、DTA Purge and Archive (BizTalkDTADb) ジョブがこのジョブを自動的に開始します。</span><span class="sxs-lookup"><span data-stu-id="668a3-146">Instead, the DTA Purge and Archive (BizTalkDTADb) job starts this job automatically when an archive is created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="668a3-147">参照</span><span class="sxs-lookup"><span data-stu-id="668a3-147">See Also</span></span>  
 [<span data-ttu-id="668a3-148">BizTalk 追跡データベースのアーカイブおよび削除</span><span class="sxs-lookup"><span data-stu-id="668a3-148">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)