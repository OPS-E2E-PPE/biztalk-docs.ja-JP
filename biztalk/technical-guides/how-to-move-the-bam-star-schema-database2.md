---
title: "BAM スター スキーマ Database2 を移動する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6832ac2-c8c5-4515-883e-26d125d6ace0
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00567514d3a3ce197065ffdfbf499ebba46c6b06
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-the-bam-star-schema-database"></a><span data-ttu-id="d17db-102">BAM スター スキーマ データベースを移動する方法</span><span class="sxs-lookup"><span data-stu-id="d17db-102">How to Move the BAM Star Schema Database</span></span>
<span data-ttu-id="d17db-103">ここでは、BAM スター スキーマ データベースを他のサーバーに移動する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="d17db-103">You can use this procedure to move the BAM Star Schema database to another server.</span></span>  <span data-ttu-id="d17db-104">エンド ツー エンドのシナリオの観点から、BAM スター スキーマ データベースの移動にも 2 つの主要な手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d17db-104">From an end-to-end scenario perspective, moving the BAM Star Schema database involves two major steps:</span></span>  
  
-   [<span data-ttu-id="d17db-105">BAM スター スキーマ データベースを移動します。</span><span class="sxs-lookup"><span data-stu-id="d17db-105">Moving the BAM Star Schema Database</span></span>](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarMoveDB)  
  
-   [<span data-ttu-id="d17db-106">新しい BAM スター スキーマ データベースへの参照を更新</span><span class="sxs-lookup"><span data-stu-id="d17db-106">Updating References to the New BAM Star Schema Database</span></span>](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdate)  
  
## <a name="prerequisites"></a><span data-ttu-id="d17db-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="d17db-107">Prerequisites</span></span>  
 <span data-ttu-id="d17db-108">この手順を実行するには、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定サーバー ロールのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d17db-108">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
##  <span data-ttu-id="d17db-109"><a name="BKMK_StarMoveDB"></a>BAM スター スキーマ データベースを移動します。</span><span class="sxs-lookup"><span data-stu-id="d17db-109"><a name="BKMK_StarMoveDB"></a> Moving the BAM Star Schema Database</span></span>  
 <span data-ttu-id="d17db-110">BAM スター スキーマ データベースを移動する次の手順で、手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d17db-110">Perform the steps in the following procedure to move the BAM Star Schema database.</span></span>  
  
#### <a name="to-move-the-bam-star-schema-database"></a><span data-ttu-id="d17db-111">BAM スター スキーマ データベースを移動するには</span><span class="sxs-lookup"><span data-stu-id="d17db-111">To move the BAM Star Schema database</span></span>  
  
1.  <span data-ttu-id="d17db-112">BAM キューブ更新/データ保守 SSIS パッケージをすべて停止するか、BAM スター スキーマ データベースの復元が完了するまで実行を回避します。</span><span class="sxs-lookup"><span data-stu-id="d17db-112">Stop any BAM cube update and data maintenance SSIS packages, or prevent them from running until you have restored the BAM Star Schema database.</span></span>  
  
2.  <span data-ttu-id="d17db-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスをすべて停止します。</span><span class="sxs-lookup"><span data-stu-id="d17db-113">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="d17db-114">詳細については、トピックを参照してください。[開始方法、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(http://go.microsoft.com/fwlink/?LinkId=154394) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="d17db-114">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
3.  <span data-ttu-id="d17db-115">IIS サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="d17db-115">Stop the IIS service.</span></span>  
  
4.  <span data-ttu-id="d17db-116">BAM 警告 Notification service を停止します。</span><span class="sxs-lookup"><span data-stu-id="d17db-116">Stop the BAM Alerts Notification service:</span></span>  
  
    1.  <span data-ttu-id="d17db-117">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-117">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="d17db-118">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d17db-118">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="d17db-119">**Net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="d17db-119">**Net stop NS$BamAlerts**</span></span>  
  
5.  <span data-ttu-id="d17db-120">古いサーバーで、BAM スター スキーマ データベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="d17db-120">Back up the BAM Star Schema database on the old server.</span></span> <span data-ttu-id="d17db-121">データベースをバックアップする方法の手順についてに記載された手順に従います[する方法:、データベースのバックアップ (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]オンライン ブック、データベースをバックアップする方法です。</span><span class="sxs-lookup"><span data-stu-id="d17db-121">For instructions on backing up a database, follow the instructions at [How to: Back Up a Database (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to back up a database.</span></span>  
  
6.  <span data-ttu-id="d17db-122">新しい BAM スター スキーマ データベースをコピー[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。</span><span class="sxs-lookup"><span data-stu-id="d17db-122">Copy the BAM Star Schema database to the new [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
7.  <span data-ttu-id="d17db-123">新しいサーバーで、BAM スター スキーマ データベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="d17db-123">Restore the BAM Star Schema database on the new server.</span></span> <span data-ttu-id="d17db-124">データベースを復元する方法について以下に記載された手順[する方法: データベースのバックアップ (SQL Server Management Studio) を復元](http://go.microsoft.com/fwlink/?LinkId=156511)(http://go.microsoft.com/fwlink/?LinkId=156511) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースを復元する方法のオンライン ブック。</span><span class="sxs-lookup"><span data-stu-id="d17db-124">For instructions on restoring the database, follow the instructions at [How to: Restore a Database Backup (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (http://go.microsoft.com/fwlink/?LinkId=156511) in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online on how to restore a database.</span></span>  
  
##  <span data-ttu-id="d17db-125"><a name="BKMK_StarUpdate"></a>新しい BAM スター スキーマ データベースへの参照を更新</span><span class="sxs-lookup"><span data-stu-id="d17db-125"><a name="BKMK_StarUpdate"></a> Updating References to the New BAM Star Schema Database</span></span>  
 <span data-ttu-id="d17db-126">データベースを移動した後は、新しい BAM スター スキーマ データベースに対するすべての参照を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d17db-126">After you have moved the database, you must update all the references to the new BAM Star Schema Database.</span></span> <span data-ttu-id="d17db-127">次の参照を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d17db-127">The following references must be updated:</span></span>  
  
-   <span data-ttu-id="d17db-128">新しいデータベースとサーバーの名前で、BAM 構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="d17db-128">Update the BAM configuration with the new database and server names.</span></span> <span data-ttu-id="d17db-129">参照してください[BAM 構成を更新する](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdateBAMConfig)です。</span><span class="sxs-lookup"><span data-stu-id="d17db-129">See [To update the BAM configuration](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdateBAMConfig).</span></span>  
  
-   <span data-ttu-id="d17db-130">すべての BAM analysis の SSIS パッケージで新しいサーバーおよびデータベース名を更新します。</span><span class="sxs-lookup"><span data-stu-id="d17db-130">Update the new server and database names in all BAM analysis SSIS packages.</span></span> <span data-ttu-id="d17db-131">参照してください[サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新する](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdateRef)です。</span><span class="sxs-lookup"><span data-stu-id="d17db-131">See [To update server and database names in all BAM SSIS packages](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdateRef).</span></span>  
  
-   <span data-ttu-id="d17db-132">サーバーとデータベースの新しい名前のデータ ソースに、OLAP 以外のすべてのキューブを更新します。</span><span class="sxs-lookup"><span data-stu-id="d17db-132">Update the new server and database names in data sources for all non-OLAP cubes.</span></span> <span data-ttu-id="d17db-133">参照してください[サーバーと、OLAP 以外のすべてのキューブのデータ ソースのデータベース名を更新する](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_UpdateDS_non_OLAP)です。</span><span class="sxs-lookup"><span data-stu-id="d17db-133">See [To update server and database names in data sources for all non-OLAP cubes](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_UpdateDS_non_OLAP).</span></span>  
  
###  <span data-ttu-id="d17db-134"><a name="BKMK_StarUpdateBAMConfig"></a>BAM 構成を更新するには</span><span class="sxs-lookup"><span data-stu-id="d17db-134"><a name="BKMK_StarUpdateBAMConfig"></a> To update the BAM configuration</span></span>  
  
1.  <span data-ttu-id="d17db-135">BAM を復元するときに使用する .xml ファイルのコピーを用意します。</span><span class="sxs-lookup"><span data-stu-id="d17db-135">Get a copy of the .xml file used for restoring BAM:</span></span>  
  
    1.  <span data-ttu-id="d17db-136">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-136">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="d17db-137">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] が動作しているコンピューターで、次のフォルダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="d17db-137">On a computer running [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], browse to the following folder:</span></span>  
  
        -   <span data-ttu-id="d17db-138">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 64 ビット バージョンの Windows Server にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="d17db-138">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
             <span data-ttu-id="d17db-139">**%Programfiles (x86) %\Microsoft BizTalk Server 2010 \tracking**</span><span class="sxs-lookup"><span data-stu-id="d17db-139">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
        -   <span data-ttu-id="d17db-140">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 32 ビット バージョンの Windows Server にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="d17db-140">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
             <span data-ttu-id="d17db-141">**%ProgramFiles%\Microsoft BizTalk Server 2010 \tracking**</span><span class="sxs-lookup"><span data-stu-id="d17db-141">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
    3.  <span data-ttu-id="d17db-142">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d17db-142">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="d17db-143">**Bm.exe get-config –filename:BAMConfiguration.xml-サーバー:\<サーバー名 >-データベース:\<データベース >**</span><span class="sxs-lookup"><span data-stu-id="d17db-143">**Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername> -database:\<database>**</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="d17db-144">このコマンドを実行するときに、サーバーの構成情報の取得元の実際の名前に置き換える\<servername >の構成情報の取得元のデータベースの実際の名前を使用して\<データベース >。</span><span class="sxs-lookup"><span data-stu-id="d17db-144">When running this command, substitute the actual name of the server from which to get the configuration information for \<servername> and substitute the actual name of the database from which to get the configuration information for \<database>.</span></span> <span data-ttu-id="d17db-145">詳細については、BAM 管理 (BM) ユーティリティを使用して、次を参照してください。[インフラストラクチャ管理コマンド](http://go.microsoft.com/fwlink/?LinkId=156516)(http://go.microsoft.com/fwlink/?LinkId=156516) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="d17db-145">For more information about using the BAM Management (BM) utility, see [Infrastructure Management Commands](http://go.microsoft.com/fwlink/?LinkId=156516) (http://go.microsoft.com/fwlink/?LinkId=156516) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
2.  <span data-ttu-id="d17db-146">BAMConfiguration.xml ファイルを編集し、変更、 **ServerName**で、`<DeploymentUnit Name="StarSchemaDatabase">`セクションに新しいサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="d17db-146">Edit the BAMConfiguration.xml file and change the **ServerName** in the `<DeploymentUnit Name="StarSchemaDatabase">` section to the new server name.</span></span>  
  
3.  <span data-ttu-id="d17db-147">BAMConfiguration.xml ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="d17db-147">Save and close the BAMConfiguration.xml file.</span></span>  
  
4.  <span data-ttu-id="d17db-148">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-148">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="d17db-149">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] が動作しているコンピューターで、次のフォルダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="d17db-149">On a computer running [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], browse to the following folder:</span></span>  
  
    -   <span data-ttu-id="d17db-150">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 64 ビット バージョンの Windows Server にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="d17db-150">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="d17db-151">**%Programfiles (x86) %\Microsoft BizTalk Server 2010 \tracking**</span><span class="sxs-lookup"><span data-stu-id="d17db-151">**%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
    -   <span data-ttu-id="d17db-152">場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 32 ビット バージョンの Windows Server にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="d17db-152">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 32-bit version of Windows Server:</span></span>  
  
         <span data-ttu-id="d17db-153">**%ProgramFiles%\Microsoft BizTalk Server 2010 \tracking**</span><span class="sxs-lookup"><span data-stu-id="d17db-153">**%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**</span></span>  
  
6.  <span data-ttu-id="d17db-154">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d17db-154">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="d17db-155">**bm.exe 更新-config-FileName:BAMConfiguration.xml**</span><span class="sxs-lookup"><span data-stu-id="d17db-155">**bm.exe update-config -FileName:BAMConfiguration.xml**</span></span>  
  
###  <span data-ttu-id="d17db-156"><a name="BKMK_StarUpdateRef"></a>サーバーとすべての BAM SSIS パッケージ内のデータベース名を更新するには</span><span class="sxs-lookup"><span data-stu-id="d17db-156"><a name="BKMK_StarUpdateRef"></a> To update server and database names in all BAM SSIS packages</span></span>  
  
1.  <span data-ttu-id="d17db-157">すべての BAM 分析 SSIS パッケージ「bam_an _」で始まるサーバーおよびデータベース名を更新します。</span><span class="sxs-lookup"><span data-stu-id="d17db-157">Update the server and database names in all BAM analysis SSIS packages, which are prefixed with "BAM_AN_".</span></span> <span data-ttu-id="d17db-158">これを行うには、をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**をクリックし、**SQL Server Business Intelligence Development Studio**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-158">To do so, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Business Intelligence Development Studio**.</span></span>  
  
2.  <span data-ttu-id="d17db-159">SQL Server Business Intelligence Development Studio で、プロジェクトを新規作成します。</span><span class="sxs-lookup"><span data-stu-id="d17db-159">In SQL Server Business Intelligence Development Studio, create a new project.</span></span> <span data-ttu-id="d17db-160">をクリックして**ファイル**、 をクリックして**新規**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-160">Click **File**, click **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="d17db-161">**新しいプロジェクト** ダイアログ ボックスで、**プロジェクトの種類**ボックスで、クリックして**ビジネス インテリジェンス プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-161">In the **New Project** dialog box, in the **Project Types** box, click **Business Intelligence Projects**.</span></span> <span data-ttu-id="d17db-162">右側のウィンドウで、**テンプレート**ボックスで、をクリックして**Integration Services プロジェクト**、クリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-162">On the right pane, in the **Templates** box, click **Integration Services Project**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="d17db-163">**Integration Services プロジェクト**ダイアログ ボックスで、ソリューション エクスプ ローラーで右クリックし**SSIS パッケージ**、クリックして**既存のパッケージの追加**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-163">In the **Integration Services Project** dialog box, in Solution Explorer, right-click **SSIS Packages**, and then click **Add Existing Package**.</span></span>  
  
5.  <span data-ttu-id="d17db-164">**既存のパッケージのコピーを追加** ダイアログ ボックスで、**サーバー**ドロップダウン リスト ボックスで、bam_an _ のパッケージを含むサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d17db-164">In the **Add Copy of Existing Package** dialog box, in the **Server** drop-down list box, select the server that contains the BAM_AN_* packages.</span></span>  
  
6.  <span data-ttu-id="d17db-165">**パッケージ パス**、省略記号ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d17db-165">In **Package Path**, click the ellipses button.</span></span>  
  
7.  <span data-ttu-id="d17db-166">**SSIS パッケージ** ダイアログ ボックスで、更新するには、をクリックするパッケージを選択**ok**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-166">In the **SSIS Package** dialog box, select the package you want to update, click **OK**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d17db-167">これで、パッケージがソリューション エクスプローラにリストされました。</span><span class="sxs-lookup"><span data-stu-id="d17db-167">The package is now listed in Solution Explorer.</span></span>  
  
8.  <span data-ttu-id="d17db-168">ソリューション エクスプ ローラーで、前の手順で追加したパッケージをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="d17db-168">In Solution Explorer, double-click the package you added in the previous step.</span></span> <span data-ttu-id="d17db-169">**接続マネージャー** (画面の下半分に使用可能) タブで、データ ソース番号 2 (BAMStarSchema データベース) をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="d17db-169">In **Connection Managers** tab (available towards the lower half of the screen), double-click data source number 2 (BAMStarSchema database).</span></span>  
  
9. <span data-ttu-id="d17db-170">**接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスで、サーバーの名前を入力し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-170">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d17db-171">データ ソース数 3 (MSDB データベース) に、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d17db-171">Repeat this for data source number 3 (MSDB database).</span></span>  
  
10. <span data-ttu-id="d17db-172">**接続マネージャー**  タブで、データ ソース番号 4 (BAMAnalysis データベース) をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="d17db-172">In the **Connection Managers** tab, double-click data source number 4 (BAMAnalysis database).</span></span> <span data-ttu-id="d17db-173">**Analysis Services 接続マネージャーの追加**ダイアログ ボックスで、をクリックして**編集**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-173">In the **Add Analysis Services Connection Manager** dialog box, click **Edit**.</span></span>  
  
11. <span data-ttu-id="d17db-174">**接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスをサーバーの名前を入力し、をクリックして**ok**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-174">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server, click **OK**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="d17db-175">クリックして、**パッケージ エクスプ ローラー**  タブをダブルクリックして、**変数**フォルダー、しの値を更新、 **AnalysisDatabase**、 **AnalysisServer**、 **PrimaryImportDatabase**、 **PrimaryImportServer**、 **StarSchemaDatabase**、および**StarSchemaServer**変数。</span><span class="sxs-lookup"><span data-stu-id="d17db-175">Click the **Package Explorer** tab, double-click the **Variables** folder, and then update the values for the **AnalysisDatabase**, **AnalysisServer**, **PrimaryImportDatabase**, **PrimaryImportServer**, **StarSchemaDatabase**, and **StarSchemaServer** variables.</span></span> <span data-ttu-id="d17db-176">新しいサーバーやデータベースを指定する値を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d17db-176">You must update the values to point to the new server and database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d17db-177">手順 4 ~ 12 を更新するすべてのパッケージを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d17db-177">Repeat step 4 through 12 for all the packages that you want to update.</span></span>  
  
13. <span data-ttu-id="d17db-178">クリックしてから**ファイル** メニューをクリックして**すべて保存**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-178">Click then **File** menu, and then click **Save All**.</span></span>  
  
14. <span data-ttu-id="d17db-179">SQL Server Management Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="d17db-179">Start the SQL Server Management Studio.</span></span> <span data-ttu-id="d17db-180">をクリックして**開始**、 をクリックして**すべてのプログラム**をクリックして**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**をクリックして**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-180">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Management Studio**.</span></span>  
  
15. <span data-ttu-id="d17db-181">**サーバーへの接続** ダイアログ ボックスから、**サーバー**の種類のドロップダウン リスト、選択**Integration Services**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-181">In the **Connect to Server** dialog box, from the **Server** type drop-down list, select **Integration Services**.</span></span>  
  
16. <span data-ttu-id="d17db-182">サーバー名をクリックして、サーバーへの接続に資格情報を指定**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-182">Specify the server name and credentials to connect to the server and click **OK**.</span></span>  
  
17. <span data-ttu-id="d17db-183">**オブジェクト エクスプ ローラー**、展開**Integration Services**、展開**格納されたパッケージ**、クリックして**MSDB**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-183">In the **Object Explorer**, expand **Integration Services**, expand **Stored Packages**, and then click **MSDB**.</span></span>  
  
18. <span data-ttu-id="d17db-184">**オブジェクト エクスプ ローラーの詳細**タブ、以前に更新したパッケージを右クリックし、をクリックして**パッケージのインポート**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-184">In the **Object Explorer Details** tab, right-click the package that you updated earlier and then click **Import Package**.</span></span>  
  
19. <span data-ttu-id="d17db-185">**パッケージのインポート** ダイアログ ボックスから、**パッケージの場所**ドロップダウン リストで、**ファイル システム**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-185">In the **Import Package** dialog box, from the **Package location** drop-down list, select **File System**.</span></span>  
  
20. <span data-ttu-id="d17db-186">**パッケージ パス**、保存したプロジェクトに移動し、.dtsx ファイルをインポートして、をクリックするパッケージを選択**開く**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-186">In **Package Path**, navigate to your saved project, select the .dtsx file for the package you want to import, and then click **Open**.</span></span>  
  
21. <span data-ttu-id="d17db-187">パッケージ名 ボックスに自動的に入力のボックス内をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d17db-187">Click inside the Package Name box to automatically populate the box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d17db-188">手順 18 21 ~ を更新するすべてのパッケージを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d17db-188">Repeat step 18 through 21 for all the packages that you want to update.</span></span>  
  
22. <span data-ttu-id="d17db-189">をクリックして**[ok]**、順にクリック**はい**を上書きします。</span><span class="sxs-lookup"><span data-stu-id="d17db-189">Click **OK**, and then click **Yes** to overwrite.</span></span>  
  
23. <span data-ttu-id="d17db-190">すべての BAM キューブ更新およびデータ保守 SSIS パッケージを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d17db-190">Enable any BAM cube update and data maintenance SSIS packages.</span></span>  
  
###  <span data-ttu-id="d17db-191"><a name="BKMK_UpdateDS_non_OLAP"></a>サーバーと、OLAP 以外のすべてのキューブのデータ ソースのデータベース名を更新するには</span><span class="sxs-lookup"><span data-stu-id="d17db-191"><a name="BKMK_UpdateDS_non_OLAP"></a> To update server and database names in data sources for all non-OLAP cubes</span></span>  
  
1.  <span data-ttu-id="d17db-192">すべての OLAP キューブのデータ ソースにサーバーおよびデータベース名を更新します。</span><span class="sxs-lookup"><span data-stu-id="d17db-192">Update the server and database names in data sources for all non-OLAP cubes.</span></span> <span data-ttu-id="d17db-193">これを行うには、をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**または**Microsoft SQL Server 2008 SP1**をクリックし、**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-193">To do so, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2** or **Microsoft SQL Server 2008 SP1**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="d17db-194">**サーバーへの接続** ダイアログ ボックスの**サーバーの種類**ドロップダウン リストを選択**Analysis Services**サーバー名を指定、認証方法を選択します (および資格情報を提供に必要な場合) をクリックし、**接続**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-194">In the **Connect to Server** dialog box, for the **Server type** drop-down list select **Analysis Services**, provide the server name, select an authentication method (and provide credentials if required), and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="d17db-195">オブジェクト エクスプ ローラーで、**データベース**、展開**BAMAnalysis**、展開**データ ソース**、データ ソースをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="d17db-195">In the Object Explorer, expand **Databases**, expand **BAMAnalysis**, expand **Data Sources**, and then double-click a data source.</span></span>  
  
4.  <span data-ttu-id="d17db-196">**データ ソースのプロパティ** ダイアログ ボックスで、省略記号ボタンをクリックして**(...)**に対して、**接続文字列**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="d17db-196">In the **Data Source Properties** dialog box, click the ellipsis button **(…)** against the **Connection String** property.</span></span>  
  
5.  <span data-ttu-id="d17db-197">**接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスを BAMStarSchema データベースをホストしているサーバーの名前を入力し、をクリックして**OK**をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-197">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the server hosting the BAMStarSchema database, click **OK**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="d17db-198">すべて開始[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]services です。</span><span class="sxs-lookup"><span data-stu-id="d17db-198">Start all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="d17db-199">詳細については、トピックを参照してください。[開始方法、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(http://go.microsoft.com/fwlink/?LinkId=154394) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="d17db-199">For more information, see the topic [How To Start, Stop, Pause, Resume, or Restart BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
7.  <span data-ttu-id="d17db-200">IIS サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="d17db-200">Start the IIS service.</span></span>  
  
8.  <span data-ttu-id="d17db-201">BAM 警告 Notification service を開始します。</span><span class="sxs-lookup"><span data-stu-id="d17db-201">Start the BAM Alerts Notification service:</span></span>  
  
    1.  <span data-ttu-id="d17db-202">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="d17db-202">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="d17db-203">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d17db-203">At the command prompt, type:</span></span>  
  
         <span data-ttu-id="d17db-204">**Net start NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="d17db-204">**Net start NS$BamAlerts**</span></span>  
  
9. <span data-ttu-id="d17db-205">不完全なアクティビティ インスタンスを解決します。</span><span class="sxs-lookup"><span data-stu-id="d17db-205">Resolve any incomplete trace instances.</span></span>  <span data-ttu-id="d17db-206">不完全な BAM アクティビティ インスタンスを解決する方法については、次を参照してください。[不完全なアクティビティ インスタンスの解決方法](http://go.microsoft.com/fwlink/?LinkId=151475)(http://go.microsoft.com/fwlink/?LinkId=151475)。</span><span class="sxs-lookup"><span data-stu-id="d17db-206">For information about resolving incomplete BAM activity instances, see [How to Resolve Incomplete Activity Instances](http://go.microsoft.com/fwlink/?LinkId=151475) (http://go.microsoft.com/fwlink/?LinkId=151475).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="d17db-207">お勧めとしても、BAMStarSchema データベースをホストするサーバーに bam_an _ * SSIS パッケージを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d17db-207">As a good practice, you should also move the BAM_AN_* SSIS packages to the server hosting the BAMStarSchema database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d17db-208">参照</span><span class="sxs-lookup"><span data-stu-id="d17db-208">See Also</span></span>  
 [<span data-ttu-id="d17db-209">データベースの移動</span><span class="sxs-lookup"><span data-stu-id="d17db-209">Moving Databases</span></span>](../technical-guides/moving-databases.md)