---
title: BAM アーカイブ データベースを 1 に移動する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e371321c-6b8d-4be6-a6d2-926f6218db01
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84dda0937fc0c7b060e483b2ca1585a3d5160ad1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023408"
---
# <a name="how-to-move-the-bam-archive-database"></a><span data-ttu-id="f2a15-102">BAM アーカイブ データベースを移動する方法</span><span class="sxs-lookup"><span data-stu-id="f2a15-102">How to Move the BAM Archive Database</span></span>
<span data-ttu-id="f2a15-103">ここでは、BAM アーカイブ データベースを他のサーバーに移動する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-103">You can use this procedure to move the BAM Archive database to another server.</span></span>  <span data-ttu-id="f2a15-104">エンド ツー エンドのシナリオの観点から BAM アーカイブ データベースの移動にも 2 つの主要な手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f2a15-104">From an end-to-end scenario perspective, moving the BAM Archive database involves two major steps:</span></span>  
  
-   [<span data-ttu-id="f2a15-105">BAM アーカイブ データベースを移動します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-105">Moving the BAM Archive Database</span></span>](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_MovingArch)  
  
-   [<span data-ttu-id="f2a15-106">新しい BAM アーカイブ データベースへの参照を更新しています</span><span class="sxs-lookup"><span data-stu-id="f2a15-106">Updating References to the New BAM Archive Database</span></span>](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArch)  
  
## <a name="prerequisites"></a><span data-ttu-id="f2a15-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="f2a15-107">Prerequisites</span></span>  
 <span data-ttu-id="f2a15-108">この手順を実行するには、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定サーバー ロールのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2a15-108">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
##  <a name="BKMK_MovingArch"></a> <span data-ttu-id="f2a15-109">BAM アーカイブ データベースを移動します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-109">Moving the BAM Archive Database</span></span>  
 <span data-ttu-id="f2a15-110">BAM アーカイブ データベースを移動する次の手順で、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f2a15-110">Perform the steps in the following procedure to move the BAM Archive database.</span></span>  
  
#### <a name="to-move-the-bam-archive-database"></a><span data-ttu-id="f2a15-111">BAM アーカイブ データベースを移動するには</span><span class="sxs-lookup"><span data-stu-id="f2a15-111">To move the BAM Archive database</span></span>  
  
1. <span data-ttu-id="f2a15-112">停止のすべての BAM キューブ更新およびデータ保守 SSIS パッケージ、または BAM アーカイブ データベースを復元するまで実行されないようにします。</span><span class="sxs-lookup"><span data-stu-id="f2a15-112">Stop any BAM cube update and data maintenance SSIS packages, or prevent them from running until you have restored the BAM Archive database.</span></span>  
  
2. <span data-ttu-id="f2a15-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスをすべて停止します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-113">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="f2a15-114">詳細については、トピックを参照してください。[方法を開始、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(<http://go.microsoft.com/fwlink/?LinkId=154394>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="f2a15-114">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
3. <span data-ttu-id="f2a15-115">IIS サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-115">Stop the IIS service.</span></span>  
  
4. <span data-ttu-id="f2a15-116">BAM 警告 Notification service を停止します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-116">Stop the BAM Alerts Notification service:</span></span>  
  
   1.  <span data-ttu-id="f2a15-117">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="f2a15-117">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2.  <span data-ttu-id="f2a15-118">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-118">At the command prompt, type:</span></span>  
  
        <span data-ttu-id="f2a15-119">**net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="f2a15-119">**Net stop NS$BamAlerts**</span></span>  
  
5. <span data-ttu-id="f2a15-120">古いサーバーで、BAM アーカイブ データベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="f2a15-120">Back up the BAM Archive database on the old server.</span></span> <span data-ttu-id="f2a15-121">データベースのバックアップの手順についてに記載された手順に従います[方法:、データベースのバックアップ (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースをバックアップする方法のオンライン ブックの「します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-121">For instructions on backing up a database, follow the instructions at [How to: Back Up a Database (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to back up a database.</span></span>  
  
6. <span data-ttu-id="f2a15-122">BAM アーカイブ データベースのコピーを新しい[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。</span><span class="sxs-lookup"><span data-stu-id="f2a15-122">Copy the BAM Archive database to the new [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
7. <span data-ttu-id="f2a15-123">新しいサーバーで、BAM アーカイブ データベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-123">Restore the BAM Archive database on the new server.</span></span> <span data-ttu-id="f2a15-124">以下の手順については、データベースを復元する方法」の手順に従って[方法: データベース バックアップ (SQL Server Management Studio) を復元](http://go.microsoft.com/fwlink/?LinkId=156511)(<http://go.microsoft.com/fwlink/?LinkId=156511>) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースを復元する方法のオンライン ブックの「します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-124">For instructions on restoring the database, follow the instructions at [How to: Restore a Database Backup (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (<http://go.microsoft.com/fwlink/?LinkId=156511>) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to restore a database.</span></span>  
  
##  <a name="BKMK_UpdateArch"></a> <span data-ttu-id="f2a15-125">新しい BAM アーカイブ データベースへの参照を更新しています</span><span class="sxs-lookup"><span data-stu-id="f2a15-125">Updating References to the New BAM Archive Database</span></span>  
 <span data-ttu-id="f2a15-126">データベースを移動した後は、新しい BAM アーカイブ データベースへのすべての参照を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2a15-126">After you have moved the database, you must update all the references to the new BAM Archive Database.</span></span> <span data-ttu-id="f2a15-127">次の参照を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2a15-127">The following references must be updated:</span></span>  
  
-   <span data-ttu-id="f2a15-128">新しいデータベースとサーバーの名前で、BAM 構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-128">Update the BAM configuration with the new database and server names.</span></span> <span data-ttu-id="f2a15-129">参照してください[BAM 構成を更新する](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchConfig)します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-129">See [To update the BAM configuration](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchConfig).</span></span>  
  
-   <span data-ttu-id="f2a15-130">すべての BAM analysis の SSIS パッケージで新しいサーバーおよびデータベース名を更新します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-130">Update the new server and database names in all BAM analysis SSIS packages.</span></span> <span data-ttu-id="f2a15-131">参照してください[サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新する](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchSSIS)します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-131">See [To update server and database names in all BAM SSIS packages](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchSSIS).</span></span>  
  
###  <a name="BKMK_UpdateArchConfig"></a> <span data-ttu-id="f2a15-132">BAM 構成を更新するには</span><span class="sxs-lookup"><span data-stu-id="f2a15-132">To update the BAM configuration</span></span>  
  
1. <span data-ttu-id="f2a15-133">BAM を復元するときに使用する .xml ファイルのコピーを用意します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-133">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
   1. <span data-ttu-id="f2a15-134">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="f2a15-134">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2. <span data-ttu-id="f2a15-135">BizTalk Server を実行するコンピューター上には、次のフォルダーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2a15-135">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
      - <span data-ttu-id="f2a15-136">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 ビット バージョンの Windows Server にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f2a15-136">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="f2a15-137">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="f2a15-137">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
      - <span data-ttu-id="f2a15-138">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 ビット バージョンの Windows Server にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f2a15-138">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="f2a15-139">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="f2a15-139">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
   3. <span data-ttu-id="f2a15-140">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-140">At the command prompt, type:</span></span>  
  
       <span data-ttu-id="f2a15-141">**Bm.exe config の取得 –filename:BAMConfiguration.xml-サーバー:\<servername\> -データベース:\<データベース\>**</span><span class="sxs-lookup"><span data-stu-id="f2a15-141">**Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername\> -database:\<database\>**</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="f2a15-142">このコマンドを実行するときに、実際の構成情報の取得元のサーバーの名前に置き換えてください\<servername\>の構成情報の取得元のデータベースの実際の名前に置き換えます。\<データベース\>します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-142">When running this command, substitute the actual name of the server from which to get the configuration information for \<servername\> and substitute the actual name of the database from which to get the configuration information for \<database\>.</span></span> <span data-ttu-id="f2a15-143">詳細については、BAM 管理 (BM) ユーティリティを使用して、次を参照してください。[インフラストラクチャ管理コマンド](http://go.microsoft.com/fwlink/?LinkId=156516)(<http://go.microsoft.com/fwlink/?LinkId=156516>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="f2a15-143">For more information about using the BAM Management (BM) utility, see [Infrastructure Management Commands](http://go.microsoft.com/fwlink/?LinkId=156516) (<http://go.microsoft.com/fwlink/?LinkId=156516>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
2. <span data-ttu-id="f2a15-144">BAMConfiguration.xml ファイルを編集し、変更、 **ServerName**で、`<DeploymentUnit Name="ArchivingDatabase">`セクションを新しいサーバー名。</span><span class="sxs-lookup"><span data-stu-id="f2a15-144">Edit the BAMConfiguration.xml file and change the **ServerName** in the `<DeploymentUnit Name="ArchivingDatabase">` section to the new server name.</span></span>  
  
3. <span data-ttu-id="f2a15-145">BAMConfiguration.xml ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="f2a15-145">Save and close the BAMConfiguration.xml file.</span></span>  
  
4. <span data-ttu-id="f2a15-146">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="f2a15-146">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="f2a15-147">BizTalk Server を実行するコンピューター上には、次のフォルダーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2a15-147">On a computer running BizTalk Server, browse to the following folder:</span></span>  
  
   - <span data-ttu-id="f2a15-148">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 ビット バージョンの Windows Server にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f2a15-148">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="f2a15-149">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="f2a15-149">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
   - <span data-ttu-id="f2a15-150">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 ビット バージョンの Windows Server にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f2a15-150">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
      <span data-ttu-id="f2a15-151">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span><span class="sxs-lookup"><span data-stu-id="f2a15-151">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
6. <span data-ttu-id="f2a15-152">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-152">At the command prompt, type:</span></span>  
  
    <span data-ttu-id="f2a15-153">**bm.exe の更新-構成-FileName:BAMConfiguration.xml**</span><span class="sxs-lookup"><span data-stu-id="f2a15-153">**bm.exe update-config -FileName:BAMConfiguration.xml**</span></span>  
  
###  <a name="BKMK_UpdateArchSSIS"></a> <span data-ttu-id="f2a15-154">サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新するには</span><span class="sxs-lookup"><span data-stu-id="f2a15-154">To update server and database names in all BAM SSIS packages</span></span>  
  
1. <span data-ttu-id="f2a15-155">すべての BAM 分析 SSIS パッケージ「bam_dm _」が付いてでサーバーとデータベースの名前を更新します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-155">Update the server and database names in all BAM analysis SSIS packages, which are prefixed with "BAM_DM_".</span></span> <span data-ttu-id="f2a15-156">これを行うには、次のようにクリックします**開始**、 をクリック**すべてのプログラム**、 をクリック**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**、順にクリックします。**SQL Server Business Intelligence Development Studio**します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-156">To do so, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Business Intelligence Development Studio**.</span></span>  
  
2. <span data-ttu-id="f2a15-157">SQL Server Business Intelligence Development Studio で、プロジェクトを新規作成します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-157">In SQL Server Business Intelligence Development Studio, create a new project.</span></span> <span data-ttu-id="f2a15-158">をクリックして**ファイル**、 をクリックして**新規**、 をクリックし、**プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-158">Click **File**, click **New**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="f2a15-159">**新しいプロジェクト**] ダイアログ ボックスで、**プロジェクトの種類**ボックスで、[**ビジネス インテリジェンス プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-159">In the **New Project** dialog box, in the **Project Types** box, click **Business Intelligence Projects**.</span></span> <span data-ttu-id="f2a15-160">右側のウィンドウで、**テンプレート**ボックスで、 **Integration Services プロジェクト**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="f2a15-160">On the right pane, in the **Templates** box, click **Integration Services Project**, and then click **OK**.</span></span>  
  
4. <span data-ttu-id="f2a15-161">**Integration Services プロジェクト** ダイアログ ボックスで、ソリューション エクスプ ローラーで右クリックして**SSIS パッケージ**、順にクリックします**既存パッケージの追加**します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-161">In the **Integration Services Project** dialog box, in Solution Explorer, right-click **SSIS Packages**, and then click **Add Existing Package**.</span></span>  
  
5. <span data-ttu-id="f2a15-162">**既存パッケージのコピーの追加** ダイアログ ボックスで、 **Server**ドロップダウン リスト ボックスで、bam_dm _ のパッケージを格納しているサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-162">In the **Add Copy of Existing Package** dialog box, in the **Server** drop-down list box, select the server that contains the BAM_DM_\* packages.</span></span>  
  
6. <span data-ttu-id="f2a15-163">**パッケージ パス**、省略記号ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2a15-163">In **Package Path**, click the ellipses button.</span></span>  
  
7. <span data-ttu-id="f2a15-164">**SSIS パッケージ** ダイアログ ボックスで、更新、 をクリックするパッケージを選択**ok**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-164">In the **SSIS Package** dialog box, select the package you want to update, click **OK**, and then click **OK**.</span></span>  
  
    <span data-ttu-id="f2a15-165">これで、パッケージがソリューション エクスプローラにリストされました。</span><span class="sxs-lookup"><span data-stu-id="f2a15-165">The package is now listed in Solution Explorer.</span></span>  
  
8. <span data-ttu-id="f2a15-166">ソリューション エクスプ ローラーで、前の手順で追加したパッケージをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2a15-166">In Solution Explorer, double-click the package you added in the previous step.</span></span> <span data-ttu-id="f2a15-167">**接続マネージャー** (画面の下半分に利用可能) タブで、データ ソース数 2 (BAMArchive データベース) をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2a15-167">In **Connection Managers** tab (available towards the lower half of the screen), double-click data source number 2 (BAMArchive database).</span></span>  
  
9. <span data-ttu-id="f2a15-168">**接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスに、サーバーの名前を入力し、 をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-168">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f2a15-169">これは、データ ソースの番号 3 (MSDB データベース) を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-169">Repeat this for data source number 3 (MSDB database).</span></span>  
  
10. <span data-ttu-id="f2a15-170">をクリックして、**パッケージ エクスプ ローラー**  タブで、ダブルクリックして、**変数**フォルダー、しの値を更新、 **ArchivingDatabase**、 **ArchivingServer**、 **PrimaryImportDatabase**、および**PrimaryImportServer**変数。</span><span class="sxs-lookup"><span data-stu-id="f2a15-170">Click the **Package Explorer** tab, double-click the **Variables** folder, and then update the values for the **ArchivingDatabase**, **ArchivingServer**, **PrimaryImportDatabase**, and **PrimaryImportServer** variables.</span></span> <span data-ttu-id="f2a15-171">新しいサーバーやデータベースを指定する値を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2a15-171">You must update the values to point to the new server and database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f2a15-172">すべてのパッケージを更新するには、手順 4 ~ 10 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-172">Repeat step 4 through 10 for all the packages that you want to update.</span></span>  
  
11. <span data-ttu-id="f2a15-173">クリックしてから**ファイル** メニューをクリック**すべて保存**します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-173">Click then **File** menu, and then click **Save All**.</span></span>  
  
12. <span data-ttu-id="f2a15-174">SQL Server Management Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-174">Start the SQL Server Management Studio.</span></span> <span data-ttu-id="f2a15-175">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**順にクリックします**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-175">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Management Studio**.</span></span>  
  
13. <span data-ttu-id="f2a15-176">**サーバーへの接続** ダイアログ ボックスから、**サーバー**型のドロップダウン リスト、選択**Integration Services**。</span><span class="sxs-lookup"><span data-stu-id="f2a15-176">In the **Connect to Server** dialog box, from the **Server** type drop-down list, select **Integration Services**.</span></span>  
  
14. <span data-ttu-id="f2a15-177">サーバー名とサーバー をクリックして接続する資格情報を指定**OK**します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-177">Specify the server name and credentials to connect to the server and click **OK**.</span></span>  
  
15. <span data-ttu-id="f2a15-178">**オブジェクト エクスプ ローラー**、展開**Integration Services**、展開**格納されたパッケージ**、 をクリックし、 **MSDB**します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-178">In the **Object Explorer**, expand **Integration Services**, expand **Stored Packages**, and then click **MSDB**.</span></span>  
  
16. <span data-ttu-id="f2a15-179">**オブジェクト エクスプ ローラーの詳細** タブで、先ほど更新したパッケージを右クリックし、をクリックし、**パッケージのインポート**します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-179">In the **Object Explorer Details** tab, right-click the package that you updated earlier and then click **Import Package**.</span></span>  
  
17. <span data-ttu-id="f2a15-180">**パッケージのインポート** ダイアログ ボックスから、**パッケージの場所**ドロップダウン リストで、**ファイル システム**します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-180">In the **Import Package** dialog box, from the **Package location** drop-down list, select **File System**.</span></span>  
  
18. <span data-ttu-id="f2a15-181">**パッケージ パス**で、保存したプロジェクトに移動し、.dtsx ファイルをクリックして、インポートするパッケージを選択**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-181">In **Package Path**, navigate to your saved project, select the .dtsx file for the package you want to import, and then click **Open**.</span></span>  
  
19. <span data-ttu-id="f2a15-182">自動的に、ボックスに入力して [パッケージ名] ボックス内をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2a15-182">Click inside the Package Name box to automatically populate the box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f2a15-183">すべてのパッケージを更新するには、手順 16 ~ 19 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-183">Repeat step 16 through 19 for all the packages that you want to update.</span></span>  
  
20. <span data-ttu-id="f2a15-184">をクリックして**OK**、順にクリックします**はい**を上書きします。</span><span class="sxs-lookup"><span data-stu-id="f2a15-184">Click **OK**, and then click **Yes** to overwrite.</span></span>  
  
21. <span data-ttu-id="f2a15-185">すべて開始[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービス。</span><span class="sxs-lookup"><span data-stu-id="f2a15-185">Start all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="f2a15-186">詳細については、トピックを参照してください。[方法を開始、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(<http://go.microsoft.com/fwlink/?LinkId=154394>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="f2a15-186">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
22. <span data-ttu-id="f2a15-187">IIS サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-187">Start the IIS service.</span></span>  
  
23. <span data-ttu-id="f2a15-188">BAM 警告 Notification service を開始します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-188">Start the BAM Alerts Notification service:</span></span>  
  
    1.  <span data-ttu-id="f2a15-189">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="f2a15-189">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="f2a15-190">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f2a15-190">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="f2a15-191">**Net start NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="f2a15-191">**Net start NS$BamAlerts**</span></span>  
  
24. <span data-ttu-id="f2a15-192">すべての BAM キューブ更新およびデータ保守 SSIS パッケージを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f2a15-192">Enable any BAM cube update and data maintenance SSIS packages.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="f2a15-193">をお勧め、BAMArchive データベースをホストするサーバーに bam_dm _ \* SSIS パッケージを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2a15-193">As a good practice, you should also move the BAM_DM_\* SSIS packages to the server hosting the BAMArchive database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2a15-194">参照</span><span class="sxs-lookup"><span data-stu-id="f2a15-194">See Also</span></span>  
 [<span data-ttu-id="f2a15-195">データベースの移動</span><span class="sxs-lookup"><span data-stu-id="f2a15-195">Moving Databases</span></span>](../technical-guides/moving-databases.md)