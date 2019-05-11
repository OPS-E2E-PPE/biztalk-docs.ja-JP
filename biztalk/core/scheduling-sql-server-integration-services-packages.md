---
title: スケジュール SQL Server Integration Services パッケージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 037ae2cf-c352-4823-95df-9a723f2b5a81
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cbdb19b5b1f8ae7d800742c0dd211e772f98c7c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308004"
---
# <a name="scheduling-sql-server-integration-services-packages"></a><span data-ttu-id="c9e4a-102">スケジュール SQL Server Integration Services パッケージ</span><span class="sxs-lookup"><span data-stu-id="c9e4a-102">Scheduling SQL Server Integration Services Packages</span></span>
<span data-ttu-id="c9e4a-103">ユーザーは、オンライン分析処理 (OLAP) キューブに格納されたデータに基づいている BAM ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-103">Users create BAM views based on data stored in an online analytical processing (OLAP) cube.</span></span> <span data-ttu-id="c9e4a-104">キューブ更新 Integration Services パッケージは、OLAP ビューに正しいデータが反映されるように、キューブ内のデータを更新します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-104">The Cube Update Integration Services package refreshes the data in the cube so that OLAP views reflect the correct data.</span></span>  
  
 <span data-ttu-id="c9e4a-105">OLAP ビューを利用するのに少なくとも 1 回は、このパッケージを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-105">You must run this package at least once for the OLAP views to work.</span></span> <span data-ttu-id="c9e4a-106">継続的なメンテナンスは、パッケージを定期的に実行をスケジュールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-106">For ongoing maintenance, you should schedule the package to run on a regular basis.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c9e4a-107">BAM スター スキーマ データベースを復元または停止するかどうかは[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]キューブ更新 Integration Services パッケージを実行する前にデータ ソースを更新する必要があります[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]分析マネージャーまたはパッケージを実行する前に、OLAP サービスを再起動します正常にします。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-107">If you restored the BAM Star Schema database or stopped [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] before running the Cube Update Integration Services package, you must refresh the data sources in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Manager or restart the OLAP service before you can run the package successfully.</span></span>  
  
 <span data-ttu-id="c9e4a-108">1 回または一定の間隔では、特定の時点で実行する保存されたパッケージをスケジュールすることができます。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-108">You can schedule a saved package to execute at specific times, either once or at recurring intervals.</span></span> <span data-ttu-id="c9e4a-109">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-109">For example:</span></span>  
  
- <span data-ttu-id="c9e4a-110">毎日の午前 0 時です。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-110">Daily at midnight.</span></span>  
  
- <span data-ttu-id="c9e4a-111">毎週日曜日 06:00 です。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-111">Weekly on Sunday at 06:00.</span></span>  
  
- <span data-ttu-id="c9e4a-112">月の初日または最終日。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-112">The first or last day of the month.</span></span>  
  
  <span data-ttu-id="c9e4a-113">スケジュールされたパッケージによって実行されます[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]をジョブとして。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-113">A scheduled package is executed by [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] as a job.</span></span>  
  
  <span data-ttu-id="c9e4a-114">実行する方法についての[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、パッケージを参照してください[ http://go.microsoft.com/fwlink/?LinkId=125738](http://go.microsoft.com/fwlink/?LinkId=125738)します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-114">For information about running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] packages, see [http://go.microsoft.com/fwlink/?LinkId=125738](http://go.microsoft.com/fwlink/?LinkId=125738).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9e4a-115">既定では、アーカイブとキューブ作成の BAM SSIS パッケージのログ記録は有効になってし、msdb データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-115">By default, logging for archiving and cubing BAM SSIS packages is turned on and is stored in the msdb database.</span></span> <span data-ttu-id="c9e4a-116">超過、BAM アクティビティの数が多いによる SSIS イベント ログ データの重要なボリュームがあります。 または頻繁に実行して BAM の SSIS パッケージを所有しています。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-116">Overtime, this may result in a significant volume of SSIS event log data caused by large number of BAM activities or frequent execution of BAM owned SSIS packages.</span></span> <span data-ttu-id="c9e4a-117">これを解決するには、これらのエントリは主にデバッグに使用されるため、古いログ エントリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-117">To resolve this, you can delete the old log entries because these entries are used primarily for debugging.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c9e4a-118">前提条件</span><span class="sxs-lookup"><span data-stu-id="c9e4a-118">Prerequisites</span></span>  
 <span data-ttu-id="c9e4a-119">これらの手順を実行する BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-119">You must be logged on as a member of the BizTalk Server Administrators group to perform these procedures.</span></span>  
  
### <a name="to-run-the-cube-update-integration-services-package"></a><span data-ttu-id="c9e4a-120">キューブ更新 Integration Services パッケージを実行するには</span><span class="sxs-lookup"><span data-stu-id="c9e4a-120">To run the Cube Update Integration Services package</span></span>  
  
1.  <span data-ttu-id="c9e4a-121">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP1**または**Microsoft SQL Server 2008 R2**順にクリックします**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-121">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP1** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="c9e4a-122">**サーバーへの接続** ダイアログ ボックスで、**サーバーの種類**ドロップダウン リストで、 **Integration Services**します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-122">In the **Connect to server** dialog box, in the **Server type** drop-down list, select **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="c9e4a-123">**サーバー名**ドロップダウン リストで、パッケージを実行しているサーバーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-123">In the **Server name** drop-down list, select the name of the server on which you are running the package.</span></span>  
  
4.  <span data-ttu-id="c9e4a-124">**認証**ドロップダウン リストで、サーバーへの接続に使用する認証の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-124">In the **Authentication** drop-down list, select the type of authentication that you are using to connect to the server.</span></span>  
  
5.  <span data-ttu-id="c9e4a-125">必要に応じて、ユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-125">If necessary, type your user name and password.</span></span>  
  
6.  <span data-ttu-id="c9e4a-126">**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-126">Click **Connect**.</span></span>  
  
7.  <span data-ttu-id="c9e4a-127">コンソール ツリーで、展開**Integration Services**、展開**格納されたパッケージ**、 をクリックし、 **MSDB**します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-127">In the console tree, expand **Integration Services**, expand **Stored Packages**, and then click **MSDB**.</span></span>  
  
8.  <span data-ttu-id="c9e4a-128">右クリックし、 **bam_an _\<ビュー名\>** パッケージ化、およびクリックして**パッケージの実行**します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-128">Right-click the **BAM_AN_\<View name\>** package, and then click **Run Package**.</span></span>  
  
### <a name="to-run-the-maintaining-bam-data-integration-services-package"></a><span data-ttu-id="c9e4a-129">BAM データの管理 Integration Services パッケージを実行するには</span><span class="sxs-lookup"><span data-stu-id="c9e4a-129">To run the Maintaining BAM Data Integration Services package</span></span>  
  
1.  <span data-ttu-id="c9e4a-130">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP1**または**Microsoft SQL Server 2008 R2**順にクリックします**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-130">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP1** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="c9e4a-131">**サーバーへの接続** ダイアログ ボックスで、**サーバーの種類**ドロップダウン リストで、 **Integration Services**します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-131">In the **Connect to server** dialog box, in the **Server type** drop-down list, select **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="c9e4a-132">**サーバー名**ドロップダウン リストで、パッケージを実行しているサーバーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-132">In the **Server name** drop-down list, select the name of the server on which you are running the package.</span></span>  
  
4.  <span data-ttu-id="c9e4a-133">**認証**ドロップダウン リストで、サーバーへの接続に使用する認証の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-133">In the **Authentication** drop-down list, select the type of authentication that you are using to connect to the server.</span></span>  
  
5.  <span data-ttu-id="c9e4a-134">必要に応じて、ユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-134">If necessary, type your user name and password.</span></span>  
  
6.  <span data-ttu-id="c9e4a-135">**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-135">Click **Connect**.</span></span>  
  
7.  <span data-ttu-id="c9e4a-136">コンソール ツリーで、展開**Integration Services**、展開**格納されたパッケージ**、 をクリックし、 **MSDB**します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-136">In the console tree, expand **Integration Services**, expand **Stored Packages**, and then click **MSDB**.</span></span>  
  
8.  <span data-ttu-id="c9e4a-137">右クリックし、 **bam_dm _\<アクティビティ名\>** パッケージ化、およびクリックして**パッケージの実行**します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-137">Right-click the **BAM_DM_\<Activity name\>** package, and then click **Run Package**.</span></span>  
  
### <a name="to-schedule-the-packages-to-run-regularly"></a><span data-ttu-id="c9e4a-138">定期的に実行するパッケージをスケジュールするには</span><span class="sxs-lookup"><span data-stu-id="c9e4a-138">To schedule the packages to run regularly</span></span>  
  
1.  <span data-ttu-id="c9e4a-139">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP1**または**Microsoft SQL Server 2008 R2**順にクリックします**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-139">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP1** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="c9e4a-140">**サーバーへの接続** ダイアログ ボックスで、**サーバーの種類**ドロップダウン リストで、**データベース エンジン**します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-140">In the **Connect to server** dialog box, in the **Server type** drop-down list, select **Database Engine**.</span></span>  
  
3.  <span data-ttu-id="c9e4a-141">**サーバー名**ドロップダウン リストで、パッケージを実行しているサーバーの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-141">In the **Server name** drop-down list, select the name of the server on which you are running the package.</span></span>  
  
4.  <span data-ttu-id="c9e4a-142">**認証**ドロップダウン リストで、サーバーへの接続に使用する認証の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-142">In the **Authentication** drop-down list, select the type of authentication that you are using to connect to the server.</span></span>  
  
5.  <span data-ttu-id="c9e4a-143">必要に応じて、ユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-143">If necessary, type your user name and password.</span></span>  
  
6.  <span data-ttu-id="c9e4a-144">**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-144">Click **Connect**.</span></span>  
  
7.  <span data-ttu-id="c9e4a-145">コンソール ツリーで、サーバーを展開し、選択**SQL Server エージェント**します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-145">In the console tree, expand your server, and select **SQL Server Agent**.</span></span>  
  
8.  <span data-ttu-id="c9e4a-146">場合**SQL Server エージェント**は右クリックし、無効になっています。 **SQL Server エージェント**、し、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-146">If **SQL Server Agent** is disabled, right-click **SQL Server Agent**, and then select **Start**.</span></span>  
  
9. <span data-ttu-id="c9e4a-147">右クリック**SQL Server エージェント**、選び**新しいジョブ**します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-147">Right-click **SQL Server Agent**, and select  **New Job**.</span></span>  
  
10. <span data-ttu-id="c9e4a-148">**新しいジョブ**ダイアログ ボックスで、ジョブの名前を入力、**名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-148">In the **New Job** dialog box, type a name for the job in the **Name** text box.</span></span>  
  
11. <span data-ttu-id="c9e4a-149">**ページの選択**ウィンドウで、をクリックして**手順**、順にクリックします**新規**します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-149">In the **Select a page** window, click **Steps**, and then click **New**.</span></span> <span data-ttu-id="c9e4a-150">開き、**新しいジョブ ステップ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-150">This opens the **New Job Step** dialog box.</span></span>  
  
12. <span data-ttu-id="c9e4a-151">**ステップ名**テキスト ボックスに、ステップの識別名を入力します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-151">In the **Step name** text box, type an identifying name for the step.</span></span>  
  
13. <span data-ttu-id="c9e4a-152">**型**ドロップダウン リストで、 **SQL Server Integration Services パッケージ**し、**パッケージ ソース**ドロップダウン リストで、 **SSIS パッケージ ストア**.</span><span class="sxs-lookup"><span data-stu-id="c9e4a-152">In the **Type** drop-down list, select **SQL Server Integration Services Package** and in the **Package source** drop-down list, select **SSIS Package Store**.</span></span>  
  
14. <span data-ttu-id="c9e4a-153">**Server**ドロップダウン リストで、ジョブを実行しているサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-153">In the **Server** drop-down list, select the server on which you are running the job.</span></span>  
  
15. <span data-ttu-id="c9e4a-154">ファイル セレクター ボタンをクリックして、**パッケージ**テキスト ボックスに、スケジュールを設定するパッケージを選択します (いずれか、 **bam_dm _\<アクティビティ名\>** または**bam_an _\<ビュー名\>** パッケージ)、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-154">Click the file selector button for the **Package** text box, select the package you are scheduling (either the **BAM_DM_\<Activity name\>** or **BAM_AN_\<View name\>** package), and then click **OK**.</span></span>  
  
16. <span data-ttu-id="c9e4a-155">**ページの選択**ウィンドウで、をクリックして**スケジュール**、順にクリックします**新規**します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-155">In the **Select a page** window, click **Schedules**, and then click **New**.</span></span> <span data-ttu-id="c9e4a-156">開き、**新しいジョブ スケジュール** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-156">This opens the **New Job Schedule** dialog box.</span></span>  
  
17. <span data-ttu-id="c9e4a-157">**名前**テキスト ボックスに、スケジュールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-157">In the **Name** text box, type a name for the schedule.</span></span>  
  
18. <span data-ttu-id="c9e4a-158">頻度のフィールドを使用してスケジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-158">Create your schedule using the frequency fields.</span></span>  
  
19. <span data-ttu-id="c9e4a-159">**[OK]** をクリックしてジョブを保存します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-159">Click **OK** to save the job.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c9e4a-160">SQL Server の既定以外のインスタンスに BAM を構成する場合、BAM_AN_POCube DTSPackage は取得しませんスケジュール/実行正確に。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-160">If BAM is configured with a non-default instance of SQL Server, then the BAM_AN_POCube DTSPackage does not get scheduled/executed accurately.</span></span> <span data-ttu-id="c9e4a-161">継続して実行するパッケージを許可する構成ファイルを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-161">You need to modify the configuration file to allow packages to continue running.</span></span> <span data-ttu-id="c9e4a-162">詳細については、ある「変更の内容の構成ファイル」セクションを参照してください[ http://go.microsoft.com/fwlink/?LinkId=196768](http://go.microsoft.com/fwlink/?LinkId=196768)します。</span><span class="sxs-lookup"><span data-stu-id="c9e4a-162">For more information, refer to the "Modifying the Contents of the Configuration File" section at [http://go.microsoft.com/fwlink/?LinkId=196768](http://go.microsoft.com/fwlink/?LinkId=196768).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9e4a-163">参照</span><span class="sxs-lookup"><span data-stu-id="c9e4a-163">See Also</span></span>  
 [<span data-ttu-id="c9e4a-164">BAM データベースの管理</span><span class="sxs-lookup"><span data-stu-id="c9e4a-164">Managing BAM Databases</span></span>](../core/managing-bam-databases.md)