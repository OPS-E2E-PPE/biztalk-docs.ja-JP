---
title: アーカイブの自動検証を有効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, archives [Tracking database]
- archiving [Tracking database], validating archive
ms.assetid: 406ca54a-6b1f-4bdb-9bad-bea5ea0f6e66
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 257e6de9ce64b8d9e1f2c27bd401b453a1a47cda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337981"
---
# <a name="how-to-enable-automatic-archive-validation"></a><span data-ttu-id="8256b-102">アーカイブの自動検証を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="8256b-102">How to Enable Automatic Archive Validation</span></span>
<span data-ttu-id="8256b-103">アーカイブの検証が作成されるときに、アーカイブを検証することができます。</span><span class="sxs-lookup"><span data-stu-id="8256b-103">Archive validation enables you to validate the archives as they are created.</span></span> <span data-ttu-id="8256b-104">アーカイブの自動検証を有効にする前に、検証サーバーとも呼ばれます。 セカンダリ データベース サーバーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8256b-104">Before you can enable automatic archive validation, you must set up a secondary database server, also called a validation server.</span></span> <span data-ttu-id="8256b-105">アーカイブ プロセスは、単純なバックアップであるために、ハードウェアの問題のため、ディスクに格納されている実際の画像を破損することが可能なです。</span><span class="sxs-lookup"><span data-stu-id="8256b-105">Because the archiving process is a simple backup, it is possible that the actual image stored on the disk can be corrupted due to a hardware issue.</span></span>  
  
 <span data-ttu-id="8256b-106">アーカイブ検証機能を使用して、アーカイブ (バックアップ) が成功し、復元することを保証できます。</span><span class="sxs-lookup"><span data-stu-id="8256b-106">Using the archive validation feature, you can ensure the archive (backup) was successful and can be restored.</span></span> <span data-ttu-id="8256b-107">アーカイブが作成されると、新しいアーカイブが作成されている検証サーバーに通知されます。</span><span class="sxs-lookup"><span data-stu-id="8256b-107">After an archive is created, the validation server is notified that a new archive has been created.</span></span> <span data-ttu-id="8256b-108">検証サーバーは、アーカイブを復元しようとします。</span><span class="sxs-lookup"><span data-stu-id="8256b-108">The validation server attempts to restore the archive.</span></span> <span data-ttu-id="8256b-109">検証サーバーは別のインスタンスである必要があります[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ジョブが実行されているものと異なる。</span><span class="sxs-lookup"><span data-stu-id="8256b-109">A validation server must be another instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] different from the one in which the job is running.</span></span> <span data-ttu-id="8256b-110">バージョンの[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]サーバー検証と同じバージョンをする必要があります、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースをホストするために使用します。</span><span class="sxs-lookup"><span data-stu-id="8256b-110">The version of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] on the validation server must be the same version as the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] used to host the databases.</span></span>  
  
 <span data-ttu-id="8256b-111">復元が成功した場合は、検証サーバーは、BizTalk 追跡 (BizTalkDTADb) データベースに戻すには、この情報を通信します。</span><span class="sxs-lookup"><span data-stu-id="8256b-111">If the restore is successful, the validation server communicates this information back to the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="8256b-112">成功した復元が完了するまで、purge ジョブは、これ以上データが削除されません。</span><span class="sxs-lookup"><span data-stu-id="8256b-112">Until a successful restore is completed, the purge job will not purge any more data.</span></span>  
  
 <span data-ttu-id="8256b-113">復元が成功しなかった場合、検証サーバーは、BizTalk 追跡データベースに戻すには、この情報を通信します。</span><span class="sxs-lookup"><span data-stu-id="8256b-113">If the restore is not successful, the validation server communicates this information back to the BizTalk Tracking database.</span></span> <span data-ttu-id="8256b-114">Purge ジョブでは、別のアーカイブを作成し、新しいアーカイブの検証を待機します。</span><span class="sxs-lookup"><span data-stu-id="8256b-114">The purge job creates another archive and awaits validation of the new archive.</span></span> <span data-ttu-id="8256b-115">これには、アーカイブの破損が追跡データが失われる可能性ができないようにします。</span><span class="sxs-lookup"><span data-stu-id="8256b-115">This prevents the possibility of a corrupted archive causing you to lose tracking data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8256b-116">前提条件</span><span class="sxs-lookup"><span data-stu-id="8256b-116">Prerequisites</span></span>  
 <span data-ttu-id="8256b-117">この手順を実行するには、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定サーバー ロールのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8256b-117">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-enable-automatic-archive-validation"></a><span data-ttu-id="8256b-118">アーカイブの自動検証を有効にするには</span><span class="sxs-lookup"><span data-stu-id="8256b-118">To enable automatic archive validation</span></span>  
  
1. <span data-ttu-id="8256b-119">検証サーバーで、をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP2**、 をクリックし、 **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="8256b-119">On the validation server, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP2**, and then click **SQL Server Management Studio**.</span></span>  
  
2. <span data-ttu-id="8256b-120">**サーバーへの接続** ダイアログ ボックスでの名前を指定します、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 、復元プロセスのテストを実行してアーカイブをクリックできます**Connect**への接続に、適切な SQL Server。</span><span class="sxs-lookup"><span data-stu-id="8256b-120">In the **Connect to Server** dialog box, specify the name of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] where you can validate the archive by performing a test of the restore process, and then click **Connect** to connect to the appropriate SQL Server.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="8256b-121">このサーバーしないで別[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース サーバーのアーカイブを検証するときに、システム パフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="8256b-121">This server should not be another [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database server as it reduces system performance when validating the archive.</span></span>  
  
3. <span data-ttu-id="8256b-122">**Microsoft SQL Server Management Studio**、 をクリックして**ファイル**、 をクリックして**オープン**、 をクリックし、**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="8256b-122">In **Microsoft SQL Server Management Studio**, click **File**, click **Open**, and then click **File**.</span></span>  
  
4. <span data-ttu-id="8256b-123">**ファイルを開く** ダイアログ ボックスで、次の SQL スクリプトを参照します。</span><span class="sxs-lookup"><span data-stu-id="8256b-123">In the **Open File** dialog box, browse to the following SQL script:</span></span>  
  
   ```  
   %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\BTS_Tracking_ValidateArchive.sql  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="8256b-124">スクリプトを実行しているコンピューターからコピーする必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]検証サーバーにします。</span><span class="sxs-lookup"><span data-stu-id="8256b-124">You might need to copy the script from the computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to the validation server.</span></span>  
  
5. <span data-ttu-id="8256b-125">をクリックして、**クエリ** メニューをクリック**Execute**します。</span><span class="sxs-lookup"><span data-stu-id="8256b-125">Click the **Query** menu, and then click **Execute**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="8256b-126">この BTS_Tracking_ValidateArchive.sql スクリプトは、BizTalk 追跡 (BizTalkDTADb) データベースをアーカイブするフォルダーがネットワーク共有である場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="8256b-126">The BTS_Tracking_ValidateArchive.sql script only works if the folder where you are archiving your BizTalk Tracking (BizTalkDTADb) database is a network share.</span></span>  
  
    <span data-ttu-id="8256b-127">この BTS_Tracking_ValidateArchive.sql スクリプトは、ValidateArchive という SQL Server エージェント ジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="8256b-127">The BTS_Tracking_ValidateArchive.sql script creates a SQL Server Agent job called ValidateArchive.</span></span>  
  
6. <span data-ttu-id="8256b-128">アーカイブおよび削除のプロセスは可能性のあるアクセスや、別の SQL Server でデータベースを更新するため、関連する SQL Server インスタンス間のリンク サーバーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8256b-128">The archiving and purging process potentially accesses and/or updates databases in different SQL Servers, so you must set up linked servers between the involved SQL Server instances.</span></span> <span data-ttu-id="8256b-129">**SQL Server Management Studio**、 をダブルクリックします**サーバー オブジェクト**、右クリック**リンク サーバー**、順にクリックします**新しいリンク サーバー**.</span><span class="sxs-lookup"><span data-stu-id="8256b-129">In **SQL Server Management Studio**, double-click **Server Objects**, right-click **Linked Servers**, and then click **New Linked Server**.</span></span>  
  
    <span data-ttu-id="8256b-130">間にリンク サーバーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8256b-130">You must set up linked server between:</span></span>  
  
   -   <span data-ttu-id="8256b-131">各 BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースと異なるサーバー上に存在する場合、BizTalk 追跡 (BizTalkDTADb) データベース。</span><span class="sxs-lookup"><span data-stu-id="8256b-131">Each of your BizTalk MessageBox (BizTalkMsgBoxDb) databases and the BizTalk Tracking (BizTalkDTADb) database if they reside on different servers.</span></span>  
  
   -   <span data-ttu-id="8256b-132">BizTalk 追跡 (BizTalkDTADb) データベースとアーカイブ検証用の検証サーバー。</span><span class="sxs-lookup"><span data-stu-id="8256b-132">The BizTalk Tracking (BizTalkDTADb) database and the validating server for archive validation.</span></span>  
  
   -   <span data-ttu-id="8256b-133">BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースをホストするコンピューター上の SQL Server エージェント サービス アカウント、リンク サーバーで、BizTalk 追跡 (BizTalkDTADb) データベースの db_datareader と db_datawriter 権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="8256b-133">The service accounts for the SQL Server Agent on the computer hosting the BizTalk MessageBox (BizTalkMsgBoxDb) database must have the db_datareader and db_datawriter permissions for the BizTalk Tracking (BizTalkDTADb) database on the linked server.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="8256b-134">ジョブの実行に使用されるアカウントは、両方のデータベースに Database Operator (DBO) 特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="8256b-134">The account used for running the job should have Database Operator (DBO) privileges on both the databases.</span></span>  
  
7. <span data-ttu-id="8256b-135">**新しいリンク サーバー**  ダイアログ ボックスで、**全般** ページの **リンク サーバー**にリンクするサーバーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8256b-135">In the **New Linked Server** dialog box, on the **General** page, in **Linked server**, enter the name of the server you want to link to.</span></span>  
  
    <span data-ttu-id="8256b-136">たとえば、BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベース、BizTalk 追跡 (BizTalkDTADb) データベース、または検証サーバーをホストしているサーバー。</span><span class="sxs-lookup"><span data-stu-id="8256b-136">For example, the server hosting the BizTalk MessageBox (BizTalkMsgBoxDb) database, BizTalk Tracking (BizTalkDTADb) database, or the validation server.</span></span>  
  
8. <span data-ttu-id="8256b-137">[**サーバーの種類**、] をクリックして**SQL Server**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="8256b-137">Under **Server type**, click **SQL Server**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="8256b-138">**Microsoft SQL Server Management Studio**、ダブルクリックして**SQL Server エージェント**、順にクリックします**ジョブ**します。</span><span class="sxs-lookup"><span data-stu-id="8256b-138">In **Microsoft SQL Server Management Studio**, double-click **SQL Server Agent**, and then click **Jobs**.</span></span>  
  
10. <span data-ttu-id="8256b-139">**オブジェクト エクスプ ローラーの詳細**ウィンドウで、右クリック**ValidateArchive**、 をクリックし、**プロパティ**。</span><span class="sxs-lookup"><span data-stu-id="8256b-139">In the **Object Explorer Details** pane, right-click **ValidateArchive**, and then click **Properties**.</span></span>  
  
11. <span data-ttu-id="8256b-140">**ジョブのプロパティ - ValidateArchive**ダイアログ ボックスで、**ページの選択**、 をクリックして**手順**します。</span><span class="sxs-lookup"><span data-stu-id="8256b-140">In the **Job Properties - ValidateArchive** dialog box, under **Select a page**, click **Steps**.</span></span>  
  
12. <span data-ttu-id="8256b-141">**ジョブ ステップの一覧**、 をクリックして**検証**、 をクリックし、**編集**します。</span><span class="sxs-lookup"><span data-stu-id="8256b-141">In the **Job step list**, click **validate**, and then click **Edit**.</span></span>  
  
13. <span data-ttu-id="8256b-142">**全般**] ページの [、**コマンド**ボックスで、コマンドで、 **exec dtasp_ValidateArchive null の場合、null**、置換 null の場合、null では、BizTalk をホストするサーバーの名前追跡で囲まれたデータベースの単一引用符、二重引用符で囲まれた、BizTalk 追跡データベースの名前が続くし、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="8256b-142">On the **General** page, in the **Command** box, in the command, **exec dtasp_ValidateArchive null, null**, replace null, null with the name of the server hosting the BizTalk Tracking database, surrounded by single quotes, followed by the name of the BizTalk Tracking database, surrounded by quotes, and then click **OK**.</span></span> <span data-ttu-id="8256b-143">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8256b-143">For example:</span></span>  
  
     <span data-ttu-id="8256b-144">**exec dtasp_ValidateArchive '** *\<TrackingServerName\>* **', '** *\<TrackingDatabaseName\>* **'**</span><span class="sxs-lookup"><span data-stu-id="8256b-144">**exec dtasp_ValidateArchive '** *\<TrackingServerName\>* **', '** *\<TrackingDatabaseName\>* **'**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8256b-145">ValidateArchive ジョブにスケジュールがないし、そのスケジュールを構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="8256b-145">The ValidateArchive job does not have a schedule and you should not configure a schedule for it.</span></span> <span data-ttu-id="8256b-146">代わりに、DTA Purge and Archive (BizTalkDTADb) ジョブの開始、アーカイブの作成時に自動的には、このジョブ。</span><span class="sxs-lookup"><span data-stu-id="8256b-146">Instead, the DTA Purge and Archive (BizTalkDTADb) job starts this job automatically when an archive is created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8256b-147">参照</span><span class="sxs-lookup"><span data-stu-id="8256b-147">See Also</span></span>  
 [<span data-ttu-id="8256b-148">BizTalk 追跡データベースのアーカイブおよび削除</span><span class="sxs-lookup"><span data-stu-id="8256b-148">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)