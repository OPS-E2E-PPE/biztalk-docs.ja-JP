---
title: "BAM Analysis Server およびスター スキーマ データベース名への参照を更新する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- restoring [BAM], Analysis database
- Analysis database [BAM], restoring
- restoring, BAM
- restoring [BAM], updating references
- BAM, restoring
- Analysis database [BAM], updating references
ms.assetid: cbe5e500-0a25-427e-bc76-1eae24b3e5f3
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4f98129efd2f7c027ecb6c3e69d494ff2e96e8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-references-to-the-bam-analysis-server-and-star-schema-database-names"></a><span data-ttu-id="83b80-102">BAM Analysis Server およびスター スキーマ データベース名への参照を更新する方法</span><span class="sxs-lookup"><span data-stu-id="83b80-102">How to Update References to the BAM Analysis Server and Star Schema Database Names</span></span>
<span data-ttu-id="83b80-103">BAMAnalysis および BAMStarSchema データベースがバックアップされていれば、システムまたはデータに障害が発生したときには、別のコンピューターにバックアップを復元でき、さらにその名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="83b80-103">If you backed up your BAMAnalysis and BAMStarSchema databases, in the event of a system or data failure you can restore that backup to a different computer and you can rename the backup.</span></span>  
  
 <span data-ttu-id="83b80-104">BAM Analysis Server または BAMStarSchema データベースを復元する」の手順を実行[、データベースを復元する方法](../core/how-to-restore-your-databases.md)です。</span><span class="sxs-lookup"><span data-stu-id="83b80-104">To restore the BAM Analysis Server or BAMStarSchema databases, perform the steps in [How to Restore Your Databases](../core/how-to-restore-your-databases.md).</span></span> <span data-ttu-id="83b80-105">さらに、BAM データ変換サービス (DTS) パッケージを新しいサーバー名およびデータベース名に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83b80-105">In addition, you must update the BAM Data Transformation Services (DTS) packages with the new server name and database name.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="83b80-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="83b80-106">Prerequisites</span></span>  
 <span data-ttu-id="83b80-107">メンバーとしてログオンする必要があります、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループにこの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="83b80-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to perform this procedure.</span></span>  
  
### <a name="to-update-references-to-the-bam-analysis-server-and-bam-star-schema-database-name-sql-server-2008-r2sp1"></a><span data-ttu-id="83b80-108">BAM Analysis Server および BAM スター スキーマ データベース名への参照を更新するには (SQL Server 2008 R2/SP1)</span><span class="sxs-lookup"><span data-stu-id="83b80-108">To update references to the BAM Analysis Server and BAM Star Schema database name (SQL Server 2008 R2/SP1)</span></span>  
  
1.  <span data-ttu-id="83b80-109">すべての BAM キューブ更新およびデータ保守 SSIS パッケージを停止するか、BAMAnalysis または BAMStarSchema データベースの復元が完了するまで実行されないように措置を講じます。</span><span class="sxs-lookup"><span data-stu-id="83b80-109">Stop any BAM cube update and data maintenance SSIS packages, or prevent them from running until you have restored the BAMAnalysis or BAMStarSchema databases.</span></span>  
  
2.  <span data-ttu-id="83b80-110">BizTalk アプリケーション サービス (BAM イベント バス サービスを含む) を停止することにより、データベースにデータがそれ以上インポートされないようにします。</span><span class="sxs-lookup"><span data-stu-id="83b80-110">Stop the BizTalk Application service (which includes the BAM Event Bus service) so it does not try to import more data into the databases.</span></span>  
  
    1.  <span data-ttu-id="83b80-111">をクリックして**開始**、 をクリックして**実行**、し、入力**services.msc**です。</span><span class="sxs-lookup"><span data-stu-id="83b80-111">Click **Start**, click **Run**, and then type **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="83b80-112">右クリックし、 **BizTalk Service BizTalk Group: BizTalkServerApplication**サービスを提供し、クリックして**停止**です。</span><span class="sxs-lookup"><span data-stu-id="83b80-112">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service and then click **Stop**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="83b80-113">サービスを停止する別の方法は、使用する、 **Net Stop**コマンド。</span><span class="sxs-lookup"><span data-stu-id="83b80-113">Another way to stop a service is to use the **Net Stop** command.</span></span> <span data-ttu-id="83b80-114">Net Stop を使用して BizTalk サービスを停止するを開き、**コマンド プロンプト**(Windows Server 2008 または Windows Vista を使用して場合、は、コマンド プロンプトを使用して、起動**管理者として実行**) と入力します: `Net Stop BTSSvc$BizTalkServerApplication`キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="83b80-114">To stop the BizTalk service using Net Stop, open a **Command Prompt** (If using Windows Server 2008 or Windows Vista, start the Command Prompt using **Run As Administrator**) and type the following: `Net Stop BTSSvc$BizTalkServerApplication` then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="83b80-115">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**、クリックして**SQL Server Business Intelligence Development Studio**.</span><span class="sxs-lookup"><span data-stu-id="83b80-115">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, and then click **SQL Server Business Intelligence Development Studio**.</span></span>  
  
4.  <span data-ttu-id="83b80-116">SQL Server Business Intelligence Development Studio で、プロジェクトを新規作成します。</span><span class="sxs-lookup"><span data-stu-id="83b80-116">In SQL Server Business Intelligence Development Studio, create a new project.</span></span> <span data-ttu-id="83b80-117">をクリックして**ファイル**、 をクリックして**新規**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="83b80-117">Click **File**, click **New**, and then click **Project**.</span></span>  
  
5.  <span data-ttu-id="83b80-118">**新しいプロジェクト**ダイアログ ボックスで、**テンプレート**、 をクリックして**Integration Services プロジェクト**、クリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="83b80-118">In the **New Project** dialog box, in **Templates**, click **Integration Services Project**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="83b80-119">**Integration Services プロジェクト**ダイアログ ボックスで、**ソリューション エクスプ ローラー**を右クリックして**SSIS パッケージ**、順にクリック**の既存パッケージの追加**.</span><span class="sxs-lookup"><span data-stu-id="83b80-119">In the **Integration Services Project** dialog box, in **Solution Explorer**, right-click **SSIS Packages**, and then click **Add Existing Package**.</span></span>  
  
7.  <span data-ttu-id="83b80-120">**既存のパッケージのコピーを追加** ダイアログ ボックスで、**サーバー**ドロップダウン リスト ボックスで、BAM_AN パッケージを含むサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="83b80-120">In the **Add Copy of Existing Package** dialog box, in the **Server** drop-down list box, select the server that contains the BAM_AN package.</span></span>  
  
8.  <span data-ttu-id="83b80-121">**パッケージ パス**、省略記号ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="83b80-121">In **Package Path**, click the ellipses button.</span></span>  
  
9. <span data-ttu-id="83b80-122">**SSIS パッケージ** ダイアログ ボックスで BAM_AN パッケージを選択して、をクリックして**ok**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="83b80-122">In the **SSIS Package** dialog box, select the BAM_AN package, click **OK**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="83b80-123">これで、パッケージがソリューション エクスプローラにリストされました。</span><span class="sxs-lookup"><span data-stu-id="83b80-123">The package is now listed in Solution Explorer.</span></span>  
  
10. <span data-ttu-id="83b80-124">**ソリューション エクスプ ローラー**、BAM_AN パッケージをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="83b80-124">In **Solution Explorer**, double-click the BAM_AN package.</span></span> <span data-ttu-id="83b80-125">**接続マネージャー**、データベース番号 3 (MSDB データベース) をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="83b80-125">In **Connection Managers**, double-click database number 3 (MSDB database).</span></span>  
  
11. <span data-ttu-id="83b80-126">**接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスで、MSDB サーバーの名前を入力し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="83b80-126">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the MSDB server, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="83b80-127">クリックして、**パッケージ エクスプ ローラー**  タブをダブルクリックして、**変数**フォルダー、およびプライマリ インポート サーバー名と主キーの値をインポートし、更新プログラムのデータベース名。</span><span class="sxs-lookup"><span data-stu-id="83b80-127">Click the **Package Explorer** tab, double-click the **Variables** folder, and then update the values for the primary import server name and primary import database name.</span></span>  
  
13. <span data-ttu-id="83b80-128">をクリックして**ファイル**、クリックして**すべてを保存**です。</span><span class="sxs-lookup"><span data-stu-id="83b80-128">Click **File**, and then click **Save All**.</span></span>  
  
14. <span data-ttu-id="83b80-129">**Microsoft SQL Server Management Studio**をクリックして**接続**です。</span><span class="sxs-lookup"><span data-stu-id="83b80-129">In **Microsoft SQL Server Management Studio**, click **Connect**.</span></span>  
  
15. <span data-ttu-id="83b80-130">をクリックして**Integration Services**をダブルクリックして**格納されたパッケージ**、 をクリックして**MSDB**BAM_AN パッケージを右クリックし、クリックして**パッケージのインポート**.</span><span class="sxs-lookup"><span data-stu-id="83b80-130">Click **Integration Services**, double-click **Stored Packages**, click **MSDB**, right-click the BAM_AN package, and then click **Import Package**.</span></span>  
  
16. <span data-ttu-id="83b80-131">**パッケージのインポート**ダイアログ ボックスで、**パッケージの場所****ファイル システム**です。</span><span class="sxs-lookup"><span data-stu-id="83b80-131">In the **Import Package** dialog box, in **Package location**, select **File System**.</span></span>  
  
17. <span data-ttu-id="83b80-132">**パッケージ パス**、保存したプロジェクトに移動し、BAM_AN を選択\*.dtsx ファイル、およびクリック**開く**です。</span><span class="sxs-lookup"><span data-stu-id="83b80-132">In **Package Path**, navigate to your saved project, select the BAM_AN\*.dtsx file, and then click **Open**.</span></span>  
  
18. <span data-ttu-id="83b80-133">内をクリックし、**パッケージ名**ボックスに自動的に入力します。</span><span class="sxs-lookup"><span data-stu-id="83b80-133">Click inside the **Package Name** box to automatically populate the box.</span></span>  
  
19. <span data-ttu-id="83b80-134">をクリックして**[ok]**、順にクリック**はい**を上書きします。</span><span class="sxs-lookup"><span data-stu-id="83b80-134">Click **OK**, and then click **Yes** to overwrite.</span></span>  
  
20. <span data-ttu-id="83b80-135">BizTalk Server アプリケーション サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="83b80-135">Restart the BizTalk Application service.</span></span>  
  
    1.  <span data-ttu-id="83b80-136">をクリックして**開始**、 をクリックして**実行**、し、入力**services.msc**です。</span><span class="sxs-lookup"><span data-stu-id="83b80-136">Click **Start**, click **Run**, and then type **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="83b80-137">右クリックし、 **BizTalk Service BizTalk Group: BizTalkServerApplication**サービスを提供し、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="83b80-137">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service and then click **Start**.</span></span>  
  
21. <span data-ttu-id="83b80-138">すべての BAM キューブ更新およびデータ保守 SSIS パッケージを有効にします。</span><span class="sxs-lookup"><span data-stu-id="83b80-138">Enable any BAM cube update and data maintenance SSIS packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83b80-139">参照</span><span class="sxs-lookup"><span data-stu-id="83b80-139">See Also</span></span>  
 [<span data-ttu-id="83b80-140">バックアップおよび BAM を復元します。</span><span class="sxs-lookup"><span data-stu-id="83b80-140">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)