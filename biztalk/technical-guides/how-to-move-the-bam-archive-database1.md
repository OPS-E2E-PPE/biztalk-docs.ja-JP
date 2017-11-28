---
title: "BAM アーカイブ データベース 1 に移動する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e371321c-6b8d-4be6-a6d2-926f6218db01
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3de3efa20057d39585a005168f7a08fc2d914a4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-the-bam-archive-database"></a><span data-ttu-id="95732-102">BAM アーカイブ データベースを移動する方法</span><span class="sxs-lookup"><span data-stu-id="95732-102">How to Move the BAM Archive Database</span></span>
<span data-ttu-id="95732-103">ここでは、BAM アーカイブ データベースを他のサーバーに移動する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="95732-103">You can use this procedure to move the BAM Archive database to another server.</span></span>  <span data-ttu-id="95732-104">エンド ツー エンドのシナリオの観点から BAM アーカイブ データベースの移動にも 2 つの主要な手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="95732-104">From an end-to-end scenario perspective, moving the BAM Archive database involves two major steps:</span></span>  
  
-   [<span data-ttu-id="95732-105">BAM アーカイブ データベースを移動します。</span><span class="sxs-lookup"><span data-stu-id="95732-105">Moving the BAM Archive Database</span></span>](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_MovingArch)  
  
-   [<span data-ttu-id="95732-106">新しい BAM アーカイブ データベースへの参照を更新</span><span class="sxs-lookup"><span data-stu-id="95732-106">Updating References to the New BAM Archive Database</span></span>](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArch)  
  
## <a name="prerequisites"></a><span data-ttu-id="95732-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="95732-107">Prerequisites</span></span>  
 <span data-ttu-id="95732-108">この手順を実行するには、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定サーバー ロールのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="95732-108">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
##  <span data-ttu-id="95732-109"><a name="BKMK_MovingArch"></a>BAM アーカイブ データベースを移動します。</span><span class="sxs-lookup"><span data-stu-id="95732-109"><a name="BKMK_MovingArch"></a> Moving the BAM Archive Database</span></span>  
 <span data-ttu-id="95732-110">BAM アーカイブ データベースを移動する次の手順で、手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="95732-110">Perform the steps in the following procedure to move the BAM Archive database.</span></span>  
  
#### <a name="to-move-the-bam-archive-database"></a><span data-ttu-id="95732-111">BAM アーカイブ データベースを移動するには</span><span class="sxs-lookup"><span data-stu-id="95732-111">To move the BAM Archive database</span></span>  
  
1.  <span data-ttu-id="95732-112">すべての BAM キューブ更新およびデータ保守 SSIS パッケージを停止するか、BAM アーカイブ データベースを復元が完了するまで実行されないように措置を講じます。</span><span class="sxs-lookup"><span data-stu-id="95732-112">Stop any BAM cube update and data maintenance SSIS packages, or prevent them from running until you have restored the BAM Archive database.</span></span>  
  
2.  <span data-ttu-id="95732-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスをすべて停止します。</span><span class="sxs-lookup"><span data-stu-id="95732-113">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="95732-114">詳細については、トピックを参照してください。[開始方法、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(http://go.microsoft.com/fwlink/?LinkId=154394) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="95732-114">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
3.  <span data-ttu-id="95732-115">IIS サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="95732-115">Stop the IIS service.</span></span>  
  
4.  <span data-ttu-id="95732-116">BAM 警告 Notification service を停止します。</span><span class="sxs-lookup"><span data-stu-id="95732-116">Stop the BAM Alerts Notification service:</span></span>  
  
    1.  <span data-ttu-id="95732-117">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="95732-117">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="95732-118">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="95732-118">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="95732-119">**Net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="95732-119">**Net stop NS$BamAlerts**</span></span>  
  
5.  <span data-ttu-id="95732-120">古いサーバーで、BAM アーカイブ データベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="95732-120">Back up the BAM Archive database on the old server.</span></span> <span data-ttu-id="95732-121">データベースをバックアップする方法の手順についてに記載された手順に従います[する方法:、データベースのバックアップ (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]オンライン ブック、データベースをバックアップする方法です。</span><span class="sxs-lookup"><span data-stu-id="95732-121">For instructions on backing up a database, follow the instructions at [How to: Back Up a Database (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to back up a database.</span></span>  
  
6.  <span data-ttu-id="95732-122">BAM アーカイブ データベースに新しいコピー[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。</span><span class="sxs-lookup"><span data-stu-id="95732-122">Copy the BAM Archive database to the new [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
7.  <span data-ttu-id="95732-123">新しいサーバーで、BAM アーカイブ データベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="95732-123">Restore the BAM Archive database on the new server.</span></span> <span data-ttu-id="95732-124">データベースを復元する方法について以下に記載された手順[する方法: データベースのバックアップ (SQL Server Management Studio) を復元](http://go.microsoft.com/fwlink/?LinkId=156511)(http://go.microsoft.com/fwlink/?LinkId=156511) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースを復元する方法のオンライン ブック。</span><span class="sxs-lookup"><span data-stu-id="95732-124">For instructions on restoring the database, follow the instructions at [How to: Restore a Database Backup (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (http://go.microsoft.com/fwlink/?LinkId=156511) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to restore a database.</span></span>  
  
##  <span data-ttu-id="95732-125"><a name="BKMK_UpdateArch"></a>新しい BAM アーカイブ データベースへの参照を更新</span><span class="sxs-lookup"><span data-stu-id="95732-125"><a name="BKMK_UpdateArch"></a> Updating References to the New BAM Archive Database</span></span>  
 <span data-ttu-id="95732-126">データベースを移動した後は、新しい BAM アーカイブ データベースにすべての参照を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95732-126">After you have moved the database, you must update all the references to the new BAM Archive Database.</span></span> <span data-ttu-id="95732-127">次の参照を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95732-127">The following references must be updated:</span></span>  
  
-   <span data-ttu-id="95732-128">新しいデータベースとサーバーの名前で、BAM 構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="95732-128">Update the BAM configuration with the new database and server names.</span></span> <span data-ttu-id="95732-129">参照してください[BAM 構成を更新する](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchConfig)です。</span><span class="sxs-lookup"><span data-stu-id="95732-129">See [To update the BAM configuration](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchConfig).</span></span>  
  
-   <span data-ttu-id="95732-130">すべての BAM analysis の SSIS パッケージで新しいサーバーおよびデータベース名を更新します。</span><span class="sxs-lookup"><span data-stu-id="95732-130">Update the new server and database names in all BAM analysis SSIS packages.</span></span> <span data-ttu-id="95732-131">参照してください[サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新する](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchSSIS)です。</span><span class="sxs-lookup"><span data-stu-id="95732-131">See [To update server and database names in all BAM SSIS packages](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArchSSIS).</span></span>  
  
###  <span data-ttu-id="95732-132"><a name="BKMK_UpdateArchConfig"></a>BAM 構成を更新するには</span><span class="sxs-lookup"><span data-stu-id="95732-132"><a name="BKMK_UpdateArchConfig"></a> To update the BAM configuration</span></span>  
  
1.  <span data-ttu-id="95732-133">BAM を復元するときに使用する .xml ファイルのコピーを用意します。</span><span class="sxs-lookup"><span data-stu-id="95732-133">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
    1.  <span data-ttu-id="95732-134">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="95732-134">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="95732-135">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] が動作しているコンピューターで、次のフォルダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="95732-135">On a computer running [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], browse to the following folder:</span></span>  
  
        -   <span data-ttu-id="95732-136">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 64 ビット バージョンの Windows Server にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="95732-136">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
             <span data-ttu-id="95732-137">**%Programfiles (x86) %\Microsoft BizTalk Server 2010 \tracking**</span><span class="sxs-lookup"><span data-stu-id="95732-137">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
        -   <span data-ttu-id="95732-138">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 32 ビット バージョンの Windows Server にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="95732-138">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
             <span data-ttu-id="95732-139">**%ProgramFiles%\Microsoft BizTalk Server 2010 \tracking**</span><span class="sxs-lookup"><span data-stu-id="95732-139">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
    3.  <span data-ttu-id="95732-140">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="95732-140">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="95732-141">**Bm.exe get-config –filename:BAMConfiguration.xml-サーバー:\<サーバー名 >-データベース:\<データベース >**</span><span class="sxs-lookup"><span data-stu-id="95732-141">**Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername> -database:\<database>**</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="95732-142">このコマンドを実行するときに、サーバーの構成情報の取得元の実際の名前に置き換える\<servername >の構成情報の取得元のデータベースの実際の名前を使用して\<データベース >。</span><span class="sxs-lookup"><span data-stu-id="95732-142">When running this command, substitute the actual name of the server from which to get the configuration information for \<servername> and substitute the actual name of the database from which to get the configuration information for \<database>.</span></span> <span data-ttu-id="95732-143">詳細については、BAM 管理 (BM) ユーティリティを使用して、次を参照してください。[インフラストラクチャ管理コマンド](http://go.microsoft.com/fwlink/?LinkId=156516)(http://go.microsoft.com/fwlink/?LinkId=156516) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="95732-143">For more information about using the BAM Management (BM) utility, see [Infrastructure Management Commands](http://go.microsoft.com/fwlink/?LinkId=156516) (http://go.microsoft.com/fwlink/?LinkId=156516) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
2.  <span data-ttu-id="95732-144">BAMConfiguration.xml ファイルを編集し、変更、 **ServerName**で、`<DeploymentUnit Name="ArchivingDatabase">`セクションに新しいサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="95732-144">Edit the BAMConfiguration.xml file and change the **ServerName** in the `<DeploymentUnit Name="ArchivingDatabase">` section to the new server name.</span></span>  
  
3.  <span data-ttu-id="95732-145">BAMConfiguration.xml ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="95732-145">Save and close the BAMConfiguration.xml file.</span></span>  
  
4.  <span data-ttu-id="95732-146">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="95732-146">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="95732-147">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] が動作しているコンピューターで、次のフォルダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="95732-147">On a computer running [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], browse to the following folder:</span></span>  
  
    -   <span data-ttu-id="95732-148">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 64 ビット バージョンの Windows Server にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="95732-148">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="95732-149">**%Programfiles (x86) %\Microsoft BizTalk Server 2010 \tracking**</span><span class="sxs-lookup"><span data-stu-id="95732-149">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
    -   <span data-ttu-id="95732-150">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 32 ビット バージョンの Windows Server にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="95732-150">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="95732-151">**%ProgramFiles%\Microsoft BizTalk Server 2010 \tracking**</span><span class="sxs-lookup"><span data-stu-id="95732-151">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
6.  <span data-ttu-id="95732-152">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="95732-152">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="95732-153">**bm.exe 更新-config-FileName:BAMConfiguration.xml**</span><span class="sxs-lookup"><span data-stu-id="95732-153">**bm.exe update-config -FileName:BAMConfiguration.xml**</span></span>  
  
###  <span data-ttu-id="95732-154"><a name="BKMK_UpdateArchSSIS"></a>サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新するには</span><span class="sxs-lookup"><span data-stu-id="95732-154"><a name="BKMK_UpdateArchSSIS"></a> To update server and database names in all BAM SSIS packages</span></span>  
  
1.  <span data-ttu-id="95732-155">すべての BAM 分析 SSIS パッケージ「bam_dm _」で始まるサーバーおよびデータベース名を更新します。</span><span class="sxs-lookup"><span data-stu-id="95732-155">Update the server and database names in all BAM analysis SSIS packages, which are prefixed with "BAM_DM_".</span></span> <span data-ttu-id="95732-156">これを行うには、をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**をクリックし、**SQL Server Business Intelligence Development Studio**です。</span><span class="sxs-lookup"><span data-stu-id="95732-156">To do so, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Business Intelligence Development Studio**.</span></span>  
  
2.  <span data-ttu-id="95732-157">SQL Server Business Intelligence Development Studio で、プロジェクトを新規作成します。</span><span class="sxs-lookup"><span data-stu-id="95732-157">In SQL Server Business Intelligence Development Studio, create a new project.</span></span> <span data-ttu-id="95732-158">をクリックして**ファイル**、 をクリックして**新規**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="95732-158">Click **File**, click **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="95732-159">**新しいプロジェクト** ダイアログ ボックスで、**プロジェクトの種類**ボックスで、クリックして**ビジネス インテリジェンス プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="95732-159">In the **New Project** dialog box, in the **Project Types** box, click **Business Intelligence Projects**.</span></span> <span data-ttu-id="95732-160">右側のウィンドウで、**テンプレート**ボックスで、をクリックして**Integration Services プロジェクト**、クリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="95732-160">On the right pane, in the **Templates** box, click **Integration Services Project**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="95732-161">**Integration Services プロジェクト**ダイアログ ボックスで、ソリューション エクスプ ローラーで右クリックし**SSIS パッケージ**、クリックして**既存のパッケージの追加**です。</span><span class="sxs-lookup"><span data-stu-id="95732-161">In the **Integration Services Project** dialog box, in Solution Explorer, right-click **SSIS Packages**, and then click **Add Existing Package**.</span></span>  
  
5.  <span data-ttu-id="95732-162">**既存のパッケージのコピーを追加** ダイアログ ボックスで、**サーバー**ドロップダウン リスト ボックスで、bam_dm _ のパッケージを含むサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="95732-162">In the **Add Copy of Existing Package** dialog box, in the **Server** drop-down list box, select the server that contains the BAM_DM_* packages.</span></span>  
  
6.  <span data-ttu-id="95732-163">**パッケージ パス**、省略記号ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="95732-163">In **Package Path**, click the ellipses button.</span></span>  
  
7.  <span data-ttu-id="95732-164">**SSIS パッケージ** ダイアログ ボックスで、更新するには、をクリックするパッケージを選択**ok**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="95732-164">In the **SSIS Package** dialog box, select the package you want to update, click **OK**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="95732-165">これで、パッケージがソリューション エクスプローラにリストされました。</span><span class="sxs-lookup"><span data-stu-id="95732-165">The package is now listed in Solution Explorer.</span></span>  
  
8.  <span data-ttu-id="95732-166">ソリューション エクスプ ローラーで、前の手順で追加したパッケージをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="95732-166">In Solution Explorer, double-click the package you added in the previous step.</span></span> <span data-ttu-id="95732-167">**接続マネージャー** (画面の下半分に使用可能) タブで、データ ソース番号 2 (BAMArchive データベース) をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="95732-167">In **Connection Managers** tab (available towards the lower half of the screen), double-click data source number 2 (BAMArchive database).</span></span>  
  
9. <span data-ttu-id="95732-168">**接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスで、サーバーの名前を入力し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="95732-168">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="95732-169">データ ソース数 3 (MSDB データベース) に、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="95732-169">Repeat this for data source number 3 (MSDB database).</span></span>  
  
10. <span data-ttu-id="95732-170">クリックして、**パッケージ エクスプ ローラー**  タブをダブルクリックして、**変数**フォルダー、しの値を更新、 **ArchivingDatabase**、 **ArchivingServer**、 **PrimaryImportDatabase**、および**PrimaryImportServer**変数。</span><span class="sxs-lookup"><span data-stu-id="95732-170">Click the **Package Explorer** tab, double-click the **Variables** folder, and then update the values for the **ArchivingDatabase**, **ArchivingServer**, **PrimaryImportDatabase**, and **PrimaryImportServer** variables.</span></span> <span data-ttu-id="95732-171">新しいサーバーやデータベースを指定する値を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95732-171">You must update the values to point to the new server and database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="95732-172">手順 4 ~ 10 を更新するすべてのパッケージを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="95732-172">Repeat step 4 through 10 for all the packages that you want to update.</span></span>  
  
11. <span data-ttu-id="95732-173">クリックしてから**ファイル** メニューをクリックして**すべて保存**です。</span><span class="sxs-lookup"><span data-stu-id="95732-173">Click then **File** menu, and then click **Save All**.</span></span>  
  
12. <span data-ttu-id="95732-174">SQL Server Management Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="95732-174">Start the SQL Server Management Studio.</span></span> <span data-ttu-id="95732-175">をクリックして**開始**、 をクリックして**すべてのプログラム**をクリックして**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**をクリックして**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="95732-175">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Management Studio**.</span></span>  
  
13. <span data-ttu-id="95732-176">**サーバーへの接続** ダイアログ ボックスから、**サーバー**の種類のドロップダウン リスト、選択**Integration Services**です。</span><span class="sxs-lookup"><span data-stu-id="95732-176">In the **Connect to Server** dialog box, from the **Server** type drop-down list, select **Integration Services**.</span></span>  
  
14. <span data-ttu-id="95732-177">サーバー名をクリックして、サーバーへの接続に資格情報を指定**OK**です。</span><span class="sxs-lookup"><span data-stu-id="95732-177">Specify the server name and credentials to connect to the server and click **OK**.</span></span>  
  
15. <span data-ttu-id="95732-178">**オブジェクト エクスプ ローラー**、展開**Integration Services**、展開**格納されたパッケージ**、クリックして**MSDB**です。</span><span class="sxs-lookup"><span data-stu-id="95732-178">In the **Object Explorer**, expand **Integration Services**, expand **Stored Packages**, and then click **MSDB**.</span></span>  
  
16. <span data-ttu-id="95732-179">**オブジェクト エクスプ ローラーの詳細**タブ、以前に更新したパッケージを右クリックし、をクリックして**パッケージのインポート**です。</span><span class="sxs-lookup"><span data-stu-id="95732-179">In the **Object Explorer Details** tab, right-click the package that you updated earlier and then click **Import Package**.</span></span>  
  
17. <span data-ttu-id="95732-180">**パッケージのインポート** ダイアログ ボックスから、**パッケージの場所**ドロップダウン リストで、**ファイル システム**です。</span><span class="sxs-lookup"><span data-stu-id="95732-180">In the **Import Package** dialog box, from the **Package location** drop-down list, select **File System**.</span></span>  
  
18. <span data-ttu-id="95732-181">**パッケージ パス**、保存したプロジェクトに移動し、.dtsx ファイルをインポートして、をクリックするパッケージを選択**開く**です。</span><span class="sxs-lookup"><span data-stu-id="95732-181">In **Package Path**, navigate to your saved project, select the .dtsx file for the package you want to import, and then click **Open**.</span></span>  
  
19. <span data-ttu-id="95732-182">パッケージ名 ボックスに自動的に入力のボックス内をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95732-182">Click inside the Package Name box to automatically populate the box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="95732-183">手順 16 ~ 19 を更新するすべてのパッケージを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="95732-183">Repeat step 16 through 19 for all the packages that you want to update.</span></span>  
  
20. <span data-ttu-id="95732-184">をクリックして**[ok]**、順にクリック**はい**を上書きします。</span><span class="sxs-lookup"><span data-stu-id="95732-184">Click **OK**, and then click **Yes** to overwrite.</span></span>  
  
21. <span data-ttu-id="95732-185">すべて開始[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]services です。</span><span class="sxs-lookup"><span data-stu-id="95732-185">Start all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="95732-186">詳細については、トピックを参照してください。[開始方法、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(http://go.microsoft.com/fwlink/?LinkId=154394) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="95732-186">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
22. <span data-ttu-id="95732-187">IIS サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="95732-187">Start the IIS service.</span></span>  
  
23. <span data-ttu-id="95732-188">BAM 警告 Notification service を開始します。</span><span class="sxs-lookup"><span data-stu-id="95732-188">Start the BAM Alerts Notification service:</span></span>  
  
    1.  <span data-ttu-id="95732-189">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="95732-189">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="95732-190">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="95732-190">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="95732-191">**Net start NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="95732-191">**Net start NS$BamAlerts**</span></span>  
  
24. <span data-ttu-id="95732-192">すべての BAM キューブ更新およびデータ保守 SSIS パッケージを有効にします。</span><span class="sxs-lookup"><span data-stu-id="95732-192">Enable any BAM cube update and data maintenance SSIS packages.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="95732-193">お勧めとしても、BAMArchive データベースをホストするサーバーに bam_dm _ * SSIS パッケージを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95732-193">As a good practice, you should also move the BAM_DM_* SSIS packages to the server hosting the BAMArchive database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95732-194">参照</span><span class="sxs-lookup"><span data-stu-id="95732-194">See Also</span></span>  
 [<span data-ttu-id="95732-195">データベースの移動</span><span class="sxs-lookup"><span data-stu-id="95732-195">Moving Databases</span></span>](../technical-guides/moving-databases.md)