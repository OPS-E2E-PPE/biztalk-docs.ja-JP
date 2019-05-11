---
title: BAM スター スキーマの Database2 を移動する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a6832ac2-c8c5-4515-883e-26d125d6ace0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 486e8bb9481a08c0f7d017362b6d2a9ab3940a05
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393490"
---
# <a name="how-to-move-the-bam-star-schema-database"></a><span data-ttu-id="e253c-102">BAM スター スキーマ データベースを移動する方法</span><span class="sxs-lookup"><span data-stu-id="e253c-102">How to Move the BAM Star Schema Database</span></span>
<span data-ttu-id="e253c-103">ここでは、BAM スター スキーマ データベースを他のサーバーに移動する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="e253c-103">You can use this procedure to move the BAM Star Schema database to another server.</span></span>  <span data-ttu-id="e253c-104">エンド ツー エンドのシナリオの観点から、BAM スター スキーマ データベースの移動にも 2 つの主要な手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e253c-104">From an end-to-end scenario perspective, moving the BAM Star Schema database involves two major steps:</span></span>  
  
-   [<span data-ttu-id="e253c-105">BAM スター スキーマ データベースを移動します。</span><span class="sxs-lookup"><span data-stu-id="e253c-105">Moving the BAM Star Schema Database</span></span>](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarMoveDB)  
  
-   [<span data-ttu-id="e253c-106">新しい BAM スター スキーマ データベースへの参照を更新しています</span><span class="sxs-lookup"><span data-stu-id="e253c-106">Updating References to the New BAM Star Schema Database</span></span>](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdate)  
  
## <a name="prerequisites"></a><span data-ttu-id="e253c-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="e253c-107">Prerequisites</span></span>  
 <span data-ttu-id="e253c-108">この手順を実行するには、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定サーバー ロールのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e253c-108">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
##  <a name="BKMK_StarMoveDB"></a> <span data-ttu-id="e253c-109">BAM スター スキーマ データベースを移動します。</span><span class="sxs-lookup"><span data-stu-id="e253c-109">Moving the BAM Star Schema Database</span></span>  
 <span data-ttu-id="e253c-110">BAM スター スキーマ データベースを移動する次の手順で、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e253c-110">Perform the steps in the following procedure to move the BAM Star Schema database.</span></span>  
  
#### <a name="to-move-the-bam-star-schema-database"></a><span data-ttu-id="e253c-111">BAM スター スキーマ データベースを移動するには</span><span class="sxs-lookup"><span data-stu-id="e253c-111">To move the BAM Star Schema database</span></span>  
  
1. <span data-ttu-id="e253c-112">BAM キューブ更新/データ保守 SSIS パッケージをすべて停止するか、BAM スター スキーマ データベースの復元が完了するまで実行を回避します。</span><span class="sxs-lookup"><span data-stu-id="e253c-112">Stop any BAM cube update and data maintenance SSIS packages, or prevent them from running until you have restored the BAM Star Schema database.</span></span>  
  
2. <span data-ttu-id="e253c-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスをすべて停止します。</span><span class="sxs-lookup"><span data-stu-id="e253c-113">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="e253c-114">詳細については、トピックを参照してください。[方法を開始、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(<http://go.microsoft.com/fwlink/?LinkId=154394>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="e253c-114">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
3. <span data-ttu-id="e253c-115">IIS サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="e253c-115">Stop the IIS service.</span></span>  
  
4. <span data-ttu-id="e253c-116">BAM 警告 Notification service を停止します。</span><span class="sxs-lookup"><span data-stu-id="e253c-116">Stop the BAM Alerts Notification service:</span></span>  
  
   1.  <span data-ttu-id="e253c-117">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="e253c-117">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2.  <span data-ttu-id="e253c-118">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e253c-118">At the command prompt, type:</span></span>  
  
        <span data-ttu-id="e253c-119">**net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="e253c-119">**Net stop NS$BamAlerts**</span></span>  
  
5. <span data-ttu-id="e253c-120">古いサーバーで、BAM スター スキーマ データベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="e253c-120">Back up the BAM Star Schema database on the old server.</span></span> <span data-ttu-id="e253c-121">データベースのバックアップの手順についてに記載された手順に従います[方法。データベースのバックアップ (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースをバックアップする方法のオンライン ブックの「します。</span><span class="sxs-lookup"><span data-stu-id="e253c-121">For instructions on backing up a database, follow the instructions at [How to: Back Up a Database (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to back up a database.</span></span>  
  
6. <span data-ttu-id="e253c-122">BAM スター スキーマ データベースのコピーを新しい[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。</span><span class="sxs-lookup"><span data-stu-id="e253c-122">Copy the BAM Star Schema database to the new [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
7. <span data-ttu-id="e253c-123">新しいサーバーで、BAM スター スキーマ データベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="e253c-123">Restore the BAM Star Schema database on the new server.</span></span> <span data-ttu-id="e253c-124">以下の手順については、データベースを復元する方法」の手順に従って[方法。データベースのバックアップ (SQL Server Management Studio) 復元](http://go.microsoft.com/fwlink/?LinkId=156511)(<http://go.microsoft.com/fwlink/?LinkId=156511>) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースを復元する方法のオンライン ブックの「します。</span><span class="sxs-lookup"><span data-stu-id="e253c-124">For instructions on restoring the database, follow the instructions at [How to: Restore a Database Backup (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (<http://go.microsoft.com/fwlink/?LinkId=156511>) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to restore a database.</span></span>  
  
##  <a name="BKMK_StarUpdate"></a> <span data-ttu-id="e253c-125">新しい BAM スター スキーマ データベースへの参照を更新しています</span><span class="sxs-lookup"><span data-stu-id="e253c-125">Updating References to the New BAM Star Schema Database</span></span>  
 <span data-ttu-id="e253c-126">データベースを移動した後は、新しい BAM スター スキーマ データベースに対するすべての参照を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e253c-126">After you have moved the database, you must update all the references to the new BAM Star Schema Database.</span></span> <span data-ttu-id="e253c-127">次の参照を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e253c-127">The following references must be updated:</span></span>  
  
-   <span data-ttu-id="e253c-128">新しいデータベースとサーバーの名前で、BAM 構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="e253c-128">Update the BAM configuration with the new database and server names.</span></span> <span data-ttu-id="e253c-129">参照してください[BAM 構成を更新する](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdateBAMConfig)します。</span><span class="sxs-lookup"><span data-stu-id="e253c-129">See [To update the BAM configuration](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdateBAMConfig).</span></span>  
  
-   <span data-ttu-id="e253c-130">すべての BAM analysis の SSIS パッケージで新しいサーバーおよびデータベース名を更新します。</span><span class="sxs-lookup"><span data-stu-id="e253c-130">Update the new server and database names in all BAM analysis SSIS packages.</span></span> <span data-ttu-id="e253c-131">参照してください[サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新する](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdateRef)します。</span><span class="sxs-lookup"><span data-stu-id="e253c-131">See [To update server and database names in all BAM SSIS packages](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdateRef).</span></span>  
  
-   <span data-ttu-id="e253c-132">サーバーとデータベースの新しい名前のデータ ソースのすべての OLAP キューブを更新します。</span><span class="sxs-lookup"><span data-stu-id="e253c-132">Update the new server and database names in data sources for all non-OLAP cubes.</span></span> <span data-ttu-id="e253c-133">参照してください[サーバーと OLAP 以外のすべてのキューブのデータ ソース内のデータベース名を更新する](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_UpdateDS_non_OLAP)します。</span><span class="sxs-lookup"><span data-stu-id="e253c-133">See [To update server and database names in data sources for all non-OLAP cubes](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_UpdateDS_non_OLAP).</span></span>  
  
###  <a name="BKMK_StarUpdateBAMConfig"></a> <span data-ttu-id="e253c-134">BAM 構成を更新するには</span><span class="sxs-lookup"><span data-stu-id="e253c-134">To update the BAM configuration</span></span>  
  
1. <span data-ttu-id="e253c-135">BAM を復元するときに使用する .xml ファイルのコピーを用意します。</span><span class="sxs-lookup"><span data-stu-id="e253c-135">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
   1. <span data-ttu-id="e253c-136">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="e253c-136">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2. <span data-ttu-id="e253c-137">BizTalk Server を実行するコンピューター上には、次のフォルダーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e253c-137">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
      - <span data-ttu-id="e253c-138">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 ビット バージョンの Windows Server にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e253c-138">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="e253c-139">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="e253c-139">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
      - <span data-ttu-id="e253c-140">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 ビット バージョンの Windows Server にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e253c-140">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="e253c-141">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="e253c-141">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
   3. <span data-ttu-id="e253c-142">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e253c-142">At the command prompt, type:</span></span>  
  
       <span data-ttu-id="e253c-143">**Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername\> -database:\<database\>**</span><span class="sxs-lookup"><span data-stu-id="e253c-143">**Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername\> -database:\<database\>**</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="e253c-144">このコマンドを実行するときに、実際の構成情報の取得元のサーバーの名前に置き換えてください\<servername\>の構成情報の取得元のデータベースの実際の名前に置き換えます。\<データベース\>します。</span><span class="sxs-lookup"><span data-stu-id="e253c-144">When running this command, substitute the actual name of the server from which to get the configuration information for \<servername\> and substitute the actual name of the database from which to get the configuration information for \<database\>.</span></span> <span data-ttu-id="e253c-145">詳細については、BAM 管理 (BM) ユーティリティを使用して、次を参照してください。[インフラストラクチャ管理コマンド](http://go.microsoft.com/fwlink/?LinkId=156516)(<http://go.microsoft.com/fwlink/?LinkId=156516>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="e253c-145">For more information about using the BAM Management (BM) utility, see [Infrastructure Management Commands](http://go.microsoft.com/fwlink/?LinkId=156516) (<http://go.microsoft.com/fwlink/?LinkId=156516>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
2. <span data-ttu-id="e253c-146">BAMConfiguration.xml ファイルを編集し、変更、 **ServerName**で、`<DeploymentUnit Name="StarSchemaDatabase">`セクションを新しいサーバー名。</span><span class="sxs-lookup"><span data-stu-id="e253c-146">Edit the BAMConfiguration.xml file and change the **ServerName** in the `<DeploymentUnit Name="StarSchemaDatabase">` section to the new server name.</span></span>  
  
3. <span data-ttu-id="e253c-147">BAMConfiguration.xml ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="e253c-147">Save and close the BAMConfiguration.xml file.</span></span>  
  
4. <span data-ttu-id="e253c-148">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="e253c-148">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="e253c-149">BizTalk Server を実行するコンピューター上には、次のフォルダーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e253c-149">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
   - <span data-ttu-id="e253c-150">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 ビット バージョンの Windows Server にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e253c-150">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="e253c-151">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="e253c-151">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
   - <span data-ttu-id="e253c-152">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 ビット バージョンの Windows Server にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e253c-152">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="e253c-153">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="e253c-153">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
6. <span data-ttu-id="e253c-154">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e253c-154">At the command prompt, type:</span></span>  
  
    <span data-ttu-id="e253c-155">**bm.exe update-config -FileName:BAMConfiguration.xml**</span><span class="sxs-lookup"><span data-stu-id="e253c-155">**bm.exe update-config -FileName:BAMConfiguration.xml**</span></span>  
  
###  <a name="BKMK_StarUpdateRef"></a> <span data-ttu-id="e253c-156">サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新するには</span><span class="sxs-lookup"><span data-stu-id="e253c-156">To update server and database names in all BAM SSIS packages</span></span>  
  
1.  <span data-ttu-id="e253c-157">すべての BAM 分析 SSIS パッケージ「bam_an _」が付いてでサーバーとデータベースの名前を更新します。</span><span class="sxs-lookup"><span data-stu-id="e253c-157">Update the server and database names in all BAM analysis SSIS packages, which are prefixed with "BAM_AN_".</span></span> <span data-ttu-id="e253c-158">これを行うには、次のようにクリックします**開始**、 をクリック**すべてのプログラム**、 をクリック**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**、順にクリックします。**SQL Server Business Intelligence Development Studio**します。</span><span class="sxs-lookup"><span data-stu-id="e253c-158">To do so, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Business Intelligence Development Studio**.</span></span>  
  
2.  <span data-ttu-id="e253c-159">SQL Server Business Intelligence Development Studio で、プロジェクトを新規作成します。</span><span class="sxs-lookup"><span data-stu-id="e253c-159">In SQL Server Business Intelligence Development Studio, create a new project.</span></span> <span data-ttu-id="e253c-160">をクリックして**ファイル**、 をクリックして**新規**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="e253c-160">Click **File**, click **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="e253c-161">**新しいプロジェクト**] ダイアログ ボックスで、**プロジェクトの種類**ボックスで、[**ビジネス インテリジェンス プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="e253c-161">In the **New Project** dialog box, in the **Project Types** box, click **Business Intelligence Projects**.</span></span> <span data-ttu-id="e253c-162">右側のウィンドウで、**テンプレート**ボックスで、 **Integration Services プロジェクト**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="e253c-162">On the right pane, in the **Templates** box, click **Integration Services Project**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="e253c-163">**Integration Services プロジェクト** ダイアログ ボックスで、ソリューション エクスプ ローラーで右クリックして**SSIS パッケージ**、順にクリックします**既存パッケージの追加**します。</span><span class="sxs-lookup"><span data-stu-id="e253c-163">In the **Integration Services Project** dialog box, in Solution Explorer, right-click **SSIS Packages**, and then click **Add Existing Package**.</span></span>  
  
5.  <span data-ttu-id="e253c-164">**既存パッケージのコピーの追加** ダイアログ ボックスで、 **Server**ドロップダウン リスト ボックスで bam_an _ のパッケージを格納しているサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e253c-164">In the **Add Copy of Existing Package** dialog box, in the **Server** drop-down list box, select the server that contains the BAM_AN_\* packages.</span></span>  
  
6.  <span data-ttu-id="e253c-165">**パッケージ パス**、省略記号ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e253c-165">In **Package Path**, click the ellipses button.</span></span>  
  
7.  <span data-ttu-id="e253c-166">**SSIS パッケージ** ダイアログ ボックスで、更新、 をクリックするパッケージを選択**ok**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="e253c-166">In the **SSIS Package** dialog box, select the package you want to update, click **OK**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="e253c-167">これで、パッケージがソリューション エクスプローラにリストされました。</span><span class="sxs-lookup"><span data-stu-id="e253c-167">The package is now listed in Solution Explorer.</span></span>  
  
8.  <span data-ttu-id="e253c-168">ソリューション エクスプ ローラーで、前の手順で追加したパッケージをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="e253c-168">In Solution Explorer, double-click the package you added in the previous step.</span></span> <span data-ttu-id="e253c-169">**接続マネージャー** (画面の下半分に利用可能) タブで、データ ソース数 2 (BAMStarSchema データベース) をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="e253c-169">In **Connection Managers** tab (available towards the lower half of the screen), double-click data source number 2 (BAMStarSchema database).</span></span>  
  
9. <span data-ttu-id="e253c-170">**接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスに、サーバーの名前を入力し、 をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="e253c-170">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e253c-171">これは、データ ソースの番号 3 (MSDB データベース) を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e253c-171">Repeat this for data source number 3 (MSDB database).</span></span>  
  
10. <span data-ttu-id="e253c-172">**接続マネージャー**  タブで、データ ソース番号 4 (BAMAnalysis データベース) をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="e253c-172">In the **Connection Managers** tab, double-click data source number 4 (BAMAnalysis database).</span></span> <span data-ttu-id="e253c-173">**Analysis Services 接続マネージャーの追加**ダイアログ ボックスで、をクリックして**編集**します。</span><span class="sxs-lookup"><span data-stu-id="e253c-173">In the **Add Analysis Services Connection Manager** dialog box, click **Edit**.</span></span>  
  
11. <span data-ttu-id="e253c-174">**接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスをサーバーの名前を入力し、をクリックして**ok**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="e253c-174">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server, click **OK**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="e253c-175">をクリックして、**パッケージ エクスプ ローラー**  タブで、ダブルクリックして、**変数**フォルダー、しの値を更新、 **AnalysisDatabase**、 **AnalysisServer**、 **PrimaryImportDatabase**、 **PrimaryImportServer**、 **StarSchemaDatabase**、および**StarSchemaServer**変数。</span><span class="sxs-lookup"><span data-stu-id="e253c-175">Click the **Package Explorer** tab, double-click the **Variables** folder, and then update the values for the **AnalysisDatabase**, **AnalysisServer**, **PrimaryImportDatabase**, **PrimaryImportServer**, **StarSchemaDatabase**, and **StarSchemaServer** variables.</span></span> <span data-ttu-id="e253c-176">新しいサーバーやデータベースを指定する値を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e253c-176">You must update the values to point to the new server and database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e253c-177">すべてのパッケージを更新するには、手順 4 ~ 12 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e253c-177">Repeat step 4 through 12 for all the packages that you want to update.</span></span>  
  
13. <span data-ttu-id="e253c-178">クリックしてから**ファイル** メニューをクリック**すべて保存**します。</span><span class="sxs-lookup"><span data-stu-id="e253c-178">Click then **File** menu, and then click **Save All**.</span></span>  
  
14. <span data-ttu-id="e253c-179">SQL Server Management Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="e253c-179">Start the SQL Server Management Studio.</span></span> <span data-ttu-id="e253c-180">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**順にクリックします**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="e253c-180">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Management Studio**.</span></span>  
  
15. <span data-ttu-id="e253c-181">**サーバーへの接続** ダイアログ ボックスから、**サーバー**型のドロップダウン リスト、選択**Integration Services**。</span><span class="sxs-lookup"><span data-stu-id="e253c-181">In the **Connect to Server** dialog box, from the **Server** type drop-down list, select **Integration Services**.</span></span>  
  
16. <span data-ttu-id="e253c-182">サーバー名とサーバー をクリックして接続する資格情報を指定**OK**します。</span><span class="sxs-lookup"><span data-stu-id="e253c-182">Specify the server name and credentials to connect to the server and click **OK**.</span></span>  
  
17. <span data-ttu-id="e253c-183">**オブジェクト エクスプ ローラー**、展開**Integration Services**、展開**格納されたパッケージ**、 をクリックし、 **MSDB**します。</span><span class="sxs-lookup"><span data-stu-id="e253c-183">In the **Object Explorer**, expand **Integration Services**, expand **Stored Packages**, and then click **MSDB**.</span></span>  
  
18. <span data-ttu-id="e253c-184">**オブジェクト エクスプ ローラーの詳細** タブで、先ほど更新したパッケージを右クリックし、をクリックし、**パッケージのインポート**します。</span><span class="sxs-lookup"><span data-stu-id="e253c-184">In the **Object Explorer Details** tab, right-click the package that you updated earlier and then click **Import Package**.</span></span>  
  
19. <span data-ttu-id="e253c-185">**パッケージのインポート** ダイアログ ボックスから、**パッケージの場所**ドロップダウン リストで、**ファイル システム**します。</span><span class="sxs-lookup"><span data-stu-id="e253c-185">In the **Import Package** dialog box, from the **Package location** drop-down list, select **File System**.</span></span>  
  
20. <span data-ttu-id="e253c-186">**パッケージ パス**で、保存したプロジェクトに移動し、.dtsx ファイルをクリックして、インポートするパッケージを選択**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="e253c-186">In **Package Path**, navigate to your saved project, select the .dtsx file for the package you want to import, and then click **Open**.</span></span>  
  
21. <span data-ttu-id="e253c-187">自動的に、ボックスに入力して [パッケージ名] ボックス内をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e253c-187">Click inside the Package Name box to automatically populate the box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e253c-188">すべてのパッケージを更新するには、手順 18 ~ 21 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e253c-188">Repeat step 18 through 21 for all the packages that you want to update.</span></span>  
  
22. <span data-ttu-id="e253c-189">をクリックして **[ok]**、順にクリック**はい**を上書きします。</span><span class="sxs-lookup"><span data-stu-id="e253c-189">Click **OK**, and then click **Yes** to overwrite.</span></span>  
  
23. <span data-ttu-id="e253c-190">すべての BAM キューブ更新およびデータ保守 SSIS パッケージを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e253c-190">Enable any BAM cube update and data maintenance SSIS packages.</span></span>  
  
###  <a name="BKMK_UpdateDS_non_OLAP"></a> <span data-ttu-id="e253c-191">サーバーと OLAP 以外のすべてのキューブのデータ ソース内のデータベース名を更新するには</span><span class="sxs-lookup"><span data-stu-id="e253c-191">To update server and database names in data sources for all non-OLAP cubes</span></span>  
  
1. <span data-ttu-id="e253c-192">すべての OLAP キューブのデータ ソースのサーバーおよびデータベース名を更新します。</span><span class="sxs-lookup"><span data-stu-id="e253c-192">Update the server and database names in data sources for all non-OLAP cubes.</span></span> <span data-ttu-id="e253c-193">これを行うには、次のようにクリックします**開始**、 をクリック**すべてのプログラム**、 をクリック**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**、順にクリックします。**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="e253c-193">To do so, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Management Studio**.</span></span>  
  
2. <span data-ttu-id="e253c-194">**サーバーへの接続** ダイアログ ボックスの**サーバーの種類**ドロップダウン リストを**Analysis Services**認証方法を選択して、サーバー名を指定 (および資格情報の入力が必要な場合)、をクリックし、 **Connect**します。</span><span class="sxs-lookup"><span data-stu-id="e253c-194">In the **Connect to Server** dialog box, for the **Server type** drop-down list select **Analysis Services**, provide the server name, select an authentication method (and provide credentials if required), and then click **Connect**.</span></span>  
  
3. <span data-ttu-id="e253c-195">オブジェクト エクスプ ローラーで、**データベース**、展開**BAMAnalysis**、展開**データソース**、データ ソースをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="e253c-195">In the Object Explorer, expand **Databases**, expand **BAMAnalysis**, expand **Data Sources**, and then double-click a data source.</span></span>  
  
4. <span data-ttu-id="e253c-196">**データ ソースのプロパティ** ダイアログ ボックスで、省略記号ボタンをクリックします **(...)。** に対して、**接続文字列**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e253c-196">In the **Data Source Properties** dialog box, click the ellipsis button **(…)** against the **Connection String** property.</span></span>  
  
5. <span data-ttu-id="e253c-197">**接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスを BAMStarSchema データベースをホストするサーバーの名前を入力し、をクリックして**OK**順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="e253c-197">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server hosting the BAMStarSchema database, click **OK**, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="e253c-198">すべて開始[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービス。</span><span class="sxs-lookup"><span data-stu-id="e253c-198">Start all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="e253c-199">詳細については、トピックを参照してください。[方法を開始、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(<http://go.microsoft.com/fwlink/?LinkId=154394>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="e253c-199">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
7. <span data-ttu-id="e253c-200">IIS サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="e253c-200">Start the IIS service.</span></span>  
  
8. <span data-ttu-id="e253c-201">BAM 警告 Notification service を開始します。</span><span class="sxs-lookup"><span data-stu-id="e253c-201">Start the BAM Alerts Notification service:</span></span>  
  
   1.  <span data-ttu-id="e253c-202">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="e253c-202">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2.  <span data-ttu-id="e253c-203">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e253c-203">At the command prompt, type:</span></span>  
  
        <span data-ttu-id="e253c-204">**Net start NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="e253c-204">**Net start NS$BamAlerts**</span></span>  
  
9. <span data-ttu-id="e253c-205">すべての不完全なトレース インスタンスを解決します。</span><span class="sxs-lookup"><span data-stu-id="e253c-205">Resolve any incomplete trace instances.</span></span>  <span data-ttu-id="e253c-206">不完全な BAM アクティビティ インスタンスの解決方法の詳細については、次を参照してください。[不完全なアクティビティ インスタンスの解決方法](http://go.microsoft.com/fwlink/?LinkId=151475)(http://go.microsoft.com/fwlink/?LinkId=151475)します。</span><span class="sxs-lookup"><span data-stu-id="e253c-206">For information about resolving incomplete BAM activity instances, see [How to Resolve Incomplete Activity Instances](http://go.microsoft.com/fwlink/?LinkId=151475) (http://go.microsoft.com/fwlink/?LinkId=151475).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="e253c-207">をお勧め、BAMStarSchema データベースをホストするサーバーに bam_an _ \* SSIS パッケージを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e253c-207">As a good practice, you should also move the BAM_AN_\* SSIS packages to the server hosting the BAMStarSchema database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e253c-208">参照</span><span class="sxs-lookup"><span data-stu-id="e253c-208">See Also</span></span>  
 [<span data-ttu-id="e253c-209">データベースの移動</span><span class="sxs-lookup"><span data-stu-id="e253c-209">Moving Databases</span></span>](../technical-guides/moving-databases.md)