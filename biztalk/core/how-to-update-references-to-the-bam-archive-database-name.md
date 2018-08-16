---
title: BAM アーカイブ データベース名への参照を更新する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Archive database [BAM], restoring
- restoring, BAM
- restoring [BAM], Archive database
- restoring [BAM], updating references
- Archive database [BAM], updating references
- BAM, restoring
ms.assetid: a0b8543e-6fc1-412e-b74e-683352d9c49e
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0df87a548c2a6a5a207673d96a984e16287f04a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256418"
---
# <a name="how-to-update-references-to-the-bam-archive-database-name"></a><span data-ttu-id="7eed0-102">BAM アーカイブ データベース名への参照を更新する方法</span><span class="sxs-lookup"><span data-stu-id="7eed0-102">How to Update References to the BAM Archive Database Name</span></span>
<span data-ttu-id="7eed0-103">BAMArchive データベースがバックアップされていれば、システムまたはデータの障害が発生したときに、バックアップを復元し、さらに、その名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="7eed0-103">If you backed up your BAMArchive databases, in the event of a system or data failure you can restore that backup and rename it.</span></span>  
  
 <span data-ttu-id="7eed0-104">BAMArchive データベースを復元する」の手順を実行[、データベースを復元する方法](../core/how-to-restore-your-databases.md)です。</span><span class="sxs-lookup"><span data-stu-id="7eed0-104">To restore the BAMArchive databases, perform the steps in [How to Restore Your Databases](../core/how-to-restore-your-databases.md).</span></span> <span data-ttu-id="7eed0-105">これらの手順を実行したうえで、次の手順を実行します (詳細な手順については後述)。</span><span class="sxs-lookup"><span data-stu-id="7eed0-105">In addition, you must perform these general steps, which are followed by a procedure that describes the steps in detail:</span></span>  
  
-   <span data-ttu-id="7eed0-106">BAM DTS パッケージを、新しいサーバー名およびデータベース名で更新します。</span><span class="sxs-lookup"><span data-stu-id="7eed0-106">Update the BAM DTS packages with the new server name and database name.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7eed0-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="7eed0-107">Prerequisites</span></span>  
 <span data-ttu-id="7eed0-108">メンバーとしてログオンする必要があります、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループにこの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7eed0-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to perform this procedure.</span></span>  
  
### <a name="to-update-references-to-the-bam-archive-database-name-sql-server-2008-r2sp1"></a><span data-ttu-id="7eed0-109">BAM アーカイブ データベース名への参照を更新するには (SQL Server 2008 R2/SP1)</span><span class="sxs-lookup"><span data-stu-id="7eed0-109">To update references to the BAM Archive database name (SQL Server 2008 R2/SP1)</span></span>  
  
1.  <span data-ttu-id="7eed0-110">すべての BAM キューブ更新およびデータ保守 DTS パッケージを停止するか、BAMArchive データベースの復元が完了するまで実行されないように措置を講じます。</span><span class="sxs-lookup"><span data-stu-id="7eed0-110">Stop any BAM cube update and data maintenance DTS packages, or prevent them from running until you have restored the BAMArchive database.</span></span>  
  
2.  <span data-ttu-id="7eed0-111">(を BAM イベント バス サービスを含む)、BizTalk アプリケーション サービスを停止するため、データベースに多くのデータをインポートするのには試行されません。</span><span class="sxs-lookup"><span data-stu-id="7eed0-111">Stop the BizTalk Application service (which includes the BAM Event Bus service) so it does not try to import more data into the database.</span></span>  
  
    1.  <span data-ttu-id="7eed0-112">をクリックして**開始**、 をクリックして**実行**、し、入力**services.msc**です。</span><span class="sxs-lookup"><span data-stu-id="7eed0-112">Click **Start**, click **Run**, and then type **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="7eed0-113">右クリックし、 **BizTalk Service BizTalk Group: BizTalkServerApplication**サービスを提供し、クリックして**停止**です。</span><span class="sxs-lookup"><span data-stu-id="7eed0-113">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service and then click **Stop**.</span></span>  
  
3.  <span data-ttu-id="7eed0-114">をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft SQL Server 2008 R2**、クリックして**SQL Server Business Intelligence Development Studio**.</span><span class="sxs-lookup"><span data-stu-id="7eed0-114">Click **Start**, click **Programs**, click **Microsoft SQL Server 2008 R2**, and then click **SQL Server Business Intelligence Development Studio**.</span></span>  
  
4.  <span data-ttu-id="7eed0-115">SQL Server Business Intelligence Development Studio で、プロジェクトを新規作成します。</span><span class="sxs-lookup"><span data-stu-id="7eed0-115">In SQL Server Business Intelligence Development Studio, create a new project.</span></span> <span data-ttu-id="7eed0-116">をクリックして**ファイル**、 をクリックして**新規**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="7eed0-116">Click **File**, click **New**, and then click **Project**.</span></span>  
  
5.  <span data-ttu-id="7eed0-117">**新しいプロジェクト**ダイアログ ボックスで、**テンプレート**、 をクリックして**Integration Services プロジェクト**、クリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="7eed0-117">In the **New Project** dialog box, in **Templates**, click **Integration Services Project**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="7eed0-118">**Integration Services プロジェクト**ダイアログ ボックスで、**ソリューション エクスプ ローラー**を右クリックして**SSIS パッケージ**、順にクリック**の既存パッケージの追加**.</span><span class="sxs-lookup"><span data-stu-id="7eed0-118">In the **Integration Services Project** dialog box, in **Solution Explorer**, right-click **SSIS Packages**, and then click **Add Existing Package**.</span></span>  
  
7.  <span data-ttu-id="7eed0-119">**既存のパッケージのコピーを追加** ダイアログ ボックスで、**サーバー**ドロップダウン リスト ボックスで、BAM_DM パッケージを含むサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7eed0-119">In the **Add Copy of Existing Package** dialog box, in the **Server** drop-down list box, select the server that contains the BAM_DM package.</span></span>  
  
8.  <span data-ttu-id="7eed0-120">**パッケージ パス**、省略記号ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7eed0-120">In **Package Path**, click the ellipses button.</span></span>  
  
9. <span data-ttu-id="7eed0-121">**SSIS パッケージ** ダイアログ ボックスで、BAM_DM パッケージを選択して、をクリックして**ok**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="7eed0-121">In the **SSIS Package** dialog box, select the BAM_DM package, click **OK**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="7eed0-122">これで、パッケージがソリューション エクスプローラにリストされました。</span><span class="sxs-lookup"><span data-stu-id="7eed0-122">The package is now listed in Solution Explorer.</span></span>  
  
10. <span data-ttu-id="7eed0-123">**ソリューション エクスプ ローラー**、BAM_DM パッケージをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="7eed0-123">In **Solution Explorer**, double-click the BAM_DM package.</span></span> <span data-ttu-id="7eed0-124">**接続マネージャー**、データベース番号 3 (MSDB データベース) をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="7eed0-124">In **Connection Managers**, double-click database number 3 (MSDB database).</span></span>  
  
11. <span data-ttu-id="7eed0-125">**接続マネージャー**  ダイアログ ボックスで、**サーバー名**ボックスで、MSDB サーバーの名前を入力し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="7eed0-125">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the MSDB server, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="7eed0-126">クリックして、**パッケージ エクスプ ローラー**  タブをダブルクリックして、**変数**フォルダー、およびプライマリ インポート サーバー名と主キーの値をインポートし、更新プログラムのデータベース名。</span><span class="sxs-lookup"><span data-stu-id="7eed0-126">Click the **Package Explorer** tab, double-click the **Variables** folder, and then update the values for the primary import server name and primary import database name.</span></span>  
  
13. <span data-ttu-id="7eed0-127">をクリックして**ファイル**、クリックして**すべてを保存**です。</span><span class="sxs-lookup"><span data-stu-id="7eed0-127">Click **File**, and then click **Save All**.</span></span>  
  
14. <span data-ttu-id="7eed0-128">**Microsoft SQL Server Management Studio**をクリックして**接続**です。</span><span class="sxs-lookup"><span data-stu-id="7eed0-128">In **Microsoft SQL Server Management Studio**, click **Connect**.</span></span>  
  
15. <span data-ttu-id="7eed0-129">をクリックして**Integration Services**をダブルクリックして**格納されたパッケージ**、 をクリックして**MSDB**、BAM_DM パッケージを右クリックし、クリックして**パッケージのインポート**.</span><span class="sxs-lookup"><span data-stu-id="7eed0-129">Click **Integration Services**, double-click **Stored Packages**, click **MSDB**, right-click the BAM_DM package, and then click **Import Package**.</span></span>  
  
16. <span data-ttu-id="7eed0-130">**パッケージのインポート**ダイアログ ボックスで、**パッケージの場所****ファイル システム**です。</span><span class="sxs-lookup"><span data-stu-id="7eed0-130">In the **Import Package** dialog box, in **Package location**, select **File System**.</span></span>  
  
17. <span data-ttu-id="7eed0-131">**パッケージのパス**、保存したプロジェクトに移動し、選択、BAM_DM\*.dtsx ファイル、およびクリック**開く**です。</span><span class="sxs-lookup"><span data-stu-id="7eed0-131">In **Package Path**, navigate to your saved project, select the BAM_DM\*.dtsx file, and then click **Open**.</span></span>  
  
18. <span data-ttu-id="7eed0-132">内をクリックし、**パッケージ名**ボックスに自動的に入力します。</span><span class="sxs-lookup"><span data-stu-id="7eed0-132">Click inside the **Package Name** box to automatically populate the box.</span></span>  
  
19. <span data-ttu-id="7eed0-133">をクリックして **[ok]**、順にクリック**はい**を上書きします。</span><span class="sxs-lookup"><span data-stu-id="7eed0-133">Click **OK**, and then click **Yes** to overwrite.</span></span>  
  
20. <span data-ttu-id="7eed0-134">BizTalk Server アプリケーション サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="7eed0-134">Restart the BizTalk Application service.</span></span>  
  
    1.  <span data-ttu-id="7eed0-135">をクリックして**開始**、 をクリックして**実行**、し、入力**services.msc**です。</span><span class="sxs-lookup"><span data-stu-id="7eed0-135">Click **Start**, click **Run**, and then type **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="7eed0-136">右クリックし、 **BizTalk Service BizTalk Group: BizTalkServerApplication**サービスを提供し、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="7eed0-136">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service and then click **Start**.</span></span>  
  
21. <span data-ttu-id="7eed0-137">すべての BAM キューブ更新およびデータ保守 SSIS パッケージを有効にします。</span><span class="sxs-lookup"><span data-stu-id="7eed0-137">Enable any BAM cube update and data maintenance SSIS packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eed0-138">参照</span><span class="sxs-lookup"><span data-stu-id="7eed0-138">See Also</span></span>  
 [<span data-ttu-id="7eed0-139">バックアップおよび BAM を復元します。</span><span class="sxs-lookup"><span data-stu-id="7eed0-139">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)