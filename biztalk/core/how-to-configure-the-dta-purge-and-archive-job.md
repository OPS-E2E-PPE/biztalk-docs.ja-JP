---
title: "構成 DTA Purge and Archive ジョブをする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 2015-11-09
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- purging, configuring
- DTA Purge and Archive job, configuring
- archiving [Tracking database], DTA Purge and Archive job
- archiving [Tracking database], configuring
- purging, DTA Purge and Archive job
ms.assetid: 156ccf9b-284f-4b96-a395-92936e8cebcf
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f4985e657f26945aa2fdc168b273dbfdb159efc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-dta-purge-and-archive-job"></a><span data-ttu-id="4086a-102">DTA Purge and Archive ジョブを構成する方法</span><span class="sxs-lookup"><span data-stu-id="4086a-102">How to Configure the DTA Purge and Archive Job</span></span>
<span data-ttu-id="4086a-103">BizTalk 追跡データベース (BizTalkDTADb) からデータをアーカイブまたは削除する前に、DTA Purge and Archive (BizTalkDTADb) ジョブを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4086a-103">Before you can archive or purge data from the BizTalk Tracking (BizTalkDTADb) database, you must configure the DTA Purge and Archive (BizTalkDTADb) job.</span></span> <span data-ttu-id="4086a-104">このジョブを構成して、プロシージャを呼び出す、dtasp_BackupAndPurgeTrackingDatabase ストア、構成する必要があります、6 つのパラメーターを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="4086a-104">This job is configured to call the dtasp_BackupAndPurgeTrackingDatabase store procedure, which uses six parameters you must configure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4086a-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="4086a-105">Prerequisites</span></span>  
 <span data-ttu-id="4086a-106">これらの手順に従うには、SQL Server の sysadmin 固定サーバー ロールのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4086a-106">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to follow these steps.</span></span>  
  
### <a name="to-configure-the-dta-purge-and-archive-job"></a><span data-ttu-id="4086a-107">DTA purge and archive ジョブを構成するには</span><span class="sxs-lookup"><span data-stu-id="4086a-107">To configure the DTA purge and archive job</span></span>  
  
1.  <span data-ttu-id="4086a-108">BizTalk 追跡 (BizTalkDTADb) データベースをホストする SQL Server で開く**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="4086a-108">On the SQL Server that hosts the BizTalk Tracking (BizTalkDTADb) database, open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="4086a-109">**サーバーへの接続**、SQL server の名前、BizTalk 追跡 (BizTalkDTADb) データベースが存在して入力し、認証の種類を選択し、**接続**SQL サーバーに接続します。</span><span class="sxs-lookup"><span data-stu-id="4086a-109">In **Connect to Server**, enter the name of the SQL server where the BizTalk Tracking (BizTalkDTADb) database resides, enter the authentication type, and then select **Connect** to connect to the SQL server.</span></span>  
  
3.  <span data-ttu-id="4086a-110">**Microsoft SQL Server Management Studio**をダブルクリックして**SQL Server エージェント**、クリックして**ジョブ**です。</span><span class="sxs-lookup"><span data-stu-id="4086a-110">In **Microsoft SQL Server Management Studio**, double-click **SQL Server Agent**, and then click **Jobs**.</span></span>  
  
4.  <span data-ttu-id="4086a-111">**オブジェクト エクスプ ローラーの詳細** ウィンドウを右クリックして**DTA Purge and Archive (BizTalkDTADb)**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="4086a-111">In the **Object Explorer Details** pane, right-click **DTA Purge and Archive (BizTalkDTADb)**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="4086a-112">**ジョブのプロパティ - DTA Purge and Archive (BizTalkDTADb)**ダイアログ ボックスで、**ページの選択**をクリックして**手順**です。</span><span class="sxs-lookup"><span data-stu-id="4086a-112">In the **Job Properties - DTA Purge and Archive (BizTalkDTADb)** dialog box, under **Select a page**, click **Steps**.</span></span>  
  
6.  <span data-ttu-id="4086a-113">**ジョブ ステップの一覧**、 をクリックして**、アーカイブし、削除**、クリックして**編集**です。</span><span class="sxs-lookup"><span data-stu-id="4086a-113">In the **Job step list**, click **Archive and Purge**, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="4086a-114">**全般**] ページの [、**コマンド**ボックスで、必要に応じて、次のパラメーターを編集し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="4086a-114">On the **General** page, in the **Command** box, edit the following parameters as appropriate, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="4086a-115">@nLiveHourstinyint — (live hours) よりも古いインスタンスに完了した + (live 日) は、関連付けられているすべてのデータと共に削除されます。</span><span class="sxs-lookup"><span data-stu-id="4086a-115">@nLiveHours tinyint — Any completed instance older than the (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="4086a-116">これは、必須のパラメーターに既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="4086a-116">This is a required parameter with no default value.</span></span>  
  
    -   <span data-ttu-id="4086a-117">@nLiveDaystinyint — (live hours) よりも古いインスタンスに完了した + (live 日) は、関連付けられているすべてのデータと共に削除されます。</span><span class="sxs-lookup"><span data-stu-id="4086a-117">@nLiveDays tinyint — Any completed instance older than the (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="4086a-118">既定の間隔は、0 日です。</span><span class="sxs-lookup"><span data-stu-id="4086a-118">Default interval is 0 days.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="4086a-119">BizTalk 追跡データベース (BizTalkDTADb) では、LiveHours と LiveDays を加算した値が、BizTalk Server 環境で管理するデータの有効期間になります。</span><span class="sxs-lookup"><span data-stu-id="4086a-119">For the purposes of the BizTalk Tracking (BizTalkDTADb) database, the sum of LiveHours plus LiveDays is the live window of data you want to maintain in your BizTalk Server environment.</span></span> <span data-ttu-id="4086a-120">有効期間より前に完了したインスタンスに関連付けられているデータはすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="4086a-120">All data associated with a completed instance older than the live window of data is deleted.</span></span>  
  
    -   <span data-ttu-id="4086a-121">@nHardDeleteDaystinyint — すべてのデータ (不完全な場合でも) これは、削除するよりも古いします。</span><span class="sxs-lookup"><span data-stu-id="4086a-121">@nHardDeleteDays tinyint — All data (even if incomplete) older than this will be deleted.</span></span> <span data-ttu-id="4086a-122">HardDeleteDays に指定する間隔は、データの有効期間よりも大きい値にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4086a-122">The time interval specified for HardDeleteDays should be greater than the live window of data.</span></span> <span data-ttu-id="4086a-123">データの有効期間は、BizTalk 追跡データベース (BizTalkDTADb) でデータを追跡する間隔になります。</span><span class="sxs-lookup"><span data-stu-id="4086a-123">The live window of data is the interval of time for which you want to maintain tracking data in the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="4086a-124">この間隔より古いデータは、次のアーカイブ時にアーカイブしてから削除できます。</span><span class="sxs-lookup"><span data-stu-id="4086a-124">Anything older than this interval is eligible to be archived at the next archive and then purged.</span></span> <span data-ttu-id="4086a-125">既定では 0 日です。</span><span class="sxs-lookup"><span data-stu-id="4086a-125">Default is 0 days.</span></span>  
  
    -   <span data-ttu-id="4086a-126">@nvcFoldernvarchar (1024) — バックアップ ファイルを配置するフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="4086a-126">@nvcFolder nvarchar(1024) — Folder in which to put the backup files.</span></span> <span data-ttu-id="4086a-127">これは、必須のパラメーターに既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="4086a-127">This is a required parameter with no default value.</span></span>  
  
    -   <span data-ttu-id="4086a-128">@nvcValidatingServersysname — 検証を実行するサーバー。</span><span class="sxs-lookup"><span data-stu-id="4086a-128">@nvcValidatingServer sysname — Server on which validation will be done.</span></span> <span data-ttu-id="4086a-129">NULL 値は検証が行われないことを示します。</span><span class="sxs-lookup"><span data-stu-id="4086a-129">NULL value indicates no validation is being done.</span></span> <span data-ttu-id="4086a-130">既定値は NULL</span><span class="sxs-lookup"><span data-stu-id="4086a-130">Default is NULL.</span></span>  
  
    -   <span data-ttu-id="4086a-131">@fForceBackupint — 既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="4086a-131">@fForceBackup int — Default is 0.</span></span> <span data-ttu-id="4086a-132">これは、将来の使用に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="4086a-132">This is reserved for future use.</span></span>  
  
     <span data-ttu-id="4086a-133">編集済みのコマンドは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="4086a-133">The edited command should look similar to the following.</span></span> <span data-ttu-id="4086a-134">次の例では 1 時間の有効期間と 1 日の物理削除です。</span><span class="sxs-lookup"><span data-stu-id="4086a-134">In the following example, there is a live window of 1 hour and a hard purge of 1 day:</span></span>  
  
    ```  
    exec dtasp_BackupAndPurgeTrackingDatabase 1, 0, 1, '\\MyBizTalkServer\backup', null, 0  
    ```  
  
8.  <span data-ttu-id="4086a-135">**ジョブのプロパティ - DTA Purge and Archive (BizTalkDTADb)**ダイアログ ボックスで、**ページの選択**、 をクリックして**全般**を選択、**有効**チェック ボックスをクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="4086a-135">On the **Job Properties - DTA Purge and Archive (BizTalkDTADb)** dialog box, under **Select a page**, click **General**, select the **Enabled** check box, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4086a-136">参照</span><span class="sxs-lookup"><span data-stu-id="4086a-136">See Also</span></span>  
 [<span data-ttu-id="4086a-137">BizTalk 追跡データベースのアーカイブおよび削除</span><span class="sxs-lookup"><span data-stu-id="4086a-137">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)