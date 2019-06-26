---
title: 構成 DTA Purge and Archive ジョブ |Microsoft ドキュメント
description: BizTalk server 追跡データベースを維持するために SQL Server エージェントで、DTA Purge and Archive ジョブのパラメーターを設定します。
ms.custom: ''
ms.date: 10/11/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 156ccf9b-284f-4b96-a395-92936e8cebcf
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69b9b221a26ad844aa23b65ada5a8c6cce38cf8c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386095"
---
# <a name="configure-the-dta-purge-and-archive-job"></a><span data-ttu-id="80cd1-103">構成 DTA Purge and Archive ジョブ</span><span class="sxs-lookup"><span data-stu-id="80cd1-103">Configure the DTA Purge and Archive Job</span></span>
<span data-ttu-id="80cd1-104">BizTalk 追跡データベース (BizTalkDTADb) からデータをアーカイブまたは削除する前に、DTA Purge and Archive (BizTalkDTADb) ジョブを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80cd1-104">Before you can archive or purge data from the BizTalk Tracking (BizTalkDTADb) database, you must configure the DTA Purge and Archive (BizTalkDTADb) job.</span></span> <span data-ttu-id="80cd1-105">このジョブを構成して、プロシージャを呼び出す、dtasp_BackupAndPurgeTrackingDatabase ストア、構成する必要があります、6 つのパラメーターを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="80cd1-105">This job is configured to call the dtasp_BackupAndPurgeTrackingDatabase store procedure, which uses six parameters you must configure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="80cd1-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="80cd1-106">Prerequisites</span></span>  
 <span data-ttu-id="80cd1-107">SQL Server の sysadmin 固定サーバー ロールのメンバーであるアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="80cd1-107">Sign in with an account that is a member of the SQL Server sysadmin fixed server role.</span></span>  
  
## <a name="configure-the-dta-purge-and-archive-job"></a><span data-ttu-id="80cd1-108">構成 DTA purge and archive ジョブ</span><span class="sxs-lookup"><span data-stu-id="80cd1-108">Configure the DTA purge and archive job</span></span>  
  
1.  <span data-ttu-id="80cd1-109">BizTalk 追跡 (BizTalkDTADb) データベースをホストする SQL Server で開く**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="80cd1-109">On the SQL Server that hosts the BizTalk Tracking (BizTalkDTADb) database, open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="80cd1-110">**サーバーへの接続**、SQL server の名前、BizTalk 追跡 (BizTalkDTADb) データベースが存在して入力し、認証の種類を選択し、**接続**SQL サーバーに接続します。</span><span class="sxs-lookup"><span data-stu-id="80cd1-110">In **Connect to Server**, enter the name of the SQL server where the BizTalk Tracking (BizTalkDTADb) database resides, enter the authentication type, and then select **Connect** to connect to the SQL server.</span></span>  
  
3. <span data-ttu-id="80cd1-111">ダブルクリックして**SQL Server エージェント**、し、**ジョブ**です。</span><span class="sxs-lookup"><span data-stu-id="80cd1-111">Double-click **SQL Server Agent**, and then select **Jobs**.</span></span>  
  
4.  <span data-ttu-id="80cd1-112">**オブジェクト エクスプ ローラーの詳細**を右クリックして**DTA Purge and Archive (BizTalkDTADb)** 、し、**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="80cd1-112">In **Object Explorer Details**, right-click **DTA Purge and Archive (BizTalkDTADb)**, and then select **Properties**.</span></span>  
  
5.  <span data-ttu-id="80cd1-113">**ジョブのプロパティ - DTA Purge and Archive (BizTalkDTADb)** **ページの選択** **手順**です。</span><span class="sxs-lookup"><span data-stu-id="80cd1-113">In **Job Properties - DTA Purge and Archive (BizTalkDTADb)**, under **Select a page**, select **Steps**.</span></span>  
  
6.  <span data-ttu-id="80cd1-114">**ジョブ ステップの一覧** **、アーカイブし、削除**、し、**編集**です。</span><span class="sxs-lookup"><span data-stu-id="80cd1-114">In the **Job step list**, select **Archive and Purge**, and then select **Edit**.</span></span>  
  
7.  <span data-ttu-id="80cd1-115">**全般**で、**コマンド**ボックスで、次のパラメーターを更新し、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="80cd1-115">In **General**, in the **Command** box, update the following parameters, and then select **OK**.</span></span>  
  
    -   <span data-ttu-id="80cd1-116">@nLiveHourstinyint — (live hours) よりも古いインスタンスに完了した + (live 日) は、関連付けられているすべてのデータと共に削除されます。</span><span class="sxs-lookup"><span data-stu-id="80cd1-116">@nLiveHours tinyint — Any completed instance older than the (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="80cd1-117">これは、必須のパラメーターに既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="80cd1-117">This is a required parameter with no default value.</span></span>  
  
    -   <span data-ttu-id="80cd1-118">@nLiveDaystinyint — (live hours) よりも古いインスタンスに完了した + (live 日) は、関連付けられているすべてのデータと共に削除されます。</span><span class="sxs-lookup"><span data-stu-id="80cd1-118">@nLiveDays tinyint — Any completed instance older than the (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="80cd1-119">既定の間隔は、0 日です。</span><span class="sxs-lookup"><span data-stu-id="80cd1-119">Default interval is 0 days.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="80cd1-120">BizTalk 追跡データベース (BizTalkDTADb) では、LiveHours と LiveDays を加算した値が、BizTalk Server 環境で管理するデータの有効期間になります。</span><span class="sxs-lookup"><span data-stu-id="80cd1-120">For the purposes of the BizTalk Tracking (BizTalkDTADb) database, the sum of LiveHours plus LiveDays is the live window of data you want to maintain in your BizTalk Server environment.</span></span> <span data-ttu-id="80cd1-121">有効期間より前に完了したインスタンスに関連付けられているデータはすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="80cd1-121">All data associated with a completed instance older than the live window of data is deleted.</span></span>  
  
    -   <span data-ttu-id="80cd1-122">@nHardDeleteDaystinyint — すべてのデータ (不完全な場合でも) これは、削除するよりも古いします。</span><span class="sxs-lookup"><span data-stu-id="80cd1-122">@nHardDeleteDays tinyint — All data (even if incomplete) older than this will be deleted.</span></span> <span data-ttu-id="80cd1-123">HardDeleteDays に指定する間隔は、データの有効期間よりも大きい値にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="80cd1-123">The time interval specified for HardDeleteDays should be greater than the live window of data.</span></span> <span data-ttu-id="80cd1-124">データの有効期間は、BizTalk 追跡データベース (BizTalkDTADb) でデータを追跡する間隔になります。</span><span class="sxs-lookup"><span data-stu-id="80cd1-124">The live window of data is the interval of time for which you want to maintain tracking data in the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="80cd1-125">この間隔より古いデータは、次のアーカイブ時にアーカイブしてから削除できます。</span><span class="sxs-lookup"><span data-stu-id="80cd1-125">Anything older than this interval is eligible to be archived at the next archive and then purged.</span></span> <span data-ttu-id="80cd1-126">既定では 0 日です。</span><span class="sxs-lookup"><span data-stu-id="80cd1-126">Default is 0 days.</span></span>  
  
    -   <span data-ttu-id="80cd1-127">@nvcFoldernvarchar (1024) — バックアップ ファイルを配置するフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="80cd1-127">@nvcFolder nvarchar(1024) — Folder in which to put the backup files.</span></span> <span data-ttu-id="80cd1-128">これは、必須のパラメーターに既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="80cd1-128">This is a required parameter with no default value.</span></span>  
  
    -   <span data-ttu-id="80cd1-129">@nvcValidatingServersysname — 検証を実行するサーバー。</span><span class="sxs-lookup"><span data-stu-id="80cd1-129">@nvcValidatingServer sysname — Server on which validation will be done.</span></span> <span data-ttu-id="80cd1-130">NULL 値は検証が行われないことを示します。</span><span class="sxs-lookup"><span data-stu-id="80cd1-130">NULL value indicates no validation is being done.</span></span> <span data-ttu-id="80cd1-131">既定値は NULL</span><span class="sxs-lookup"><span data-stu-id="80cd1-131">Default is NULL.</span></span>  
  
    -   <span data-ttu-id="80cd1-132">@fForceBackupint — 既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="80cd1-132">@fForceBackup int — Default is 0.</span></span> <span data-ttu-id="80cd1-133">これは、将来の使用に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="80cd1-133">This is reserved for future use.</span></span>  
  
    -   <span data-ttu-id="80cd1-134">@fHardDeleteRunningInstancesint - 既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="80cd1-134">@fHardDeleteRunningInstances int - Default is 0.</span></span> <span data-ttu-id="80cd1-135">1 に設定すると、そのすべてを削除よりも古いサービス インスタンスを実行している、@nHardDeleteDays値。</span><span class="sxs-lookup"><span data-stu-id="80cd1-135">When set to 1, it deletes all running service instances older than the @nHardDeleteDays value.</span></span> 
    
        > [!NOTE]
        > <span data-ttu-id="80cd1-136">@fHardDeleteRunningInstancesプロパティは、以降で利用可能な[BizTalk Server 2016 の累積更新プログラム 1年](https://support.microsoft.com/help/3208238/cumulative-update-1-for-microsoft-biztalk-server-2016)、 [BizTalk Server 2013 R2 の累積更新プログラム 6年](https://support.microsoft.com/en-us/help/4020020/cumulative-update-package-6-for-biztalk-server-2013-r2)、および[BizTalk Server 2013 の累積的な更新プログラム 5 適用](https://support.microsoft.com/help/3194301/cumulative-update-5-for-biztalk-server-2013)です。</span><span class="sxs-lookup"><span data-stu-id="80cd1-136">The @fHardDeleteRunningInstances property is available starting with [BizTalk Server 2016 Cumulative Update 1](https://support.microsoft.com/help/3208238/cumulative-update-1-for-microsoft-biztalk-server-2016), [BizTalk Server 2013 R2 Cumulative Update 6](https://support.microsoft.com/en-us/help/4020020/cumulative-update-package-6-for-biztalk-server-2013-r2), and [BizTalk Server 2013 Cumulative Update 5](https://support.microsoft.com/help/3194301/cumulative-update-5-for-biztalk-server-2013).</span></span>  
  
    <span data-ttu-id="80cd1-137">編集したコマンドは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="80cd1-137">Your edited command should look similar to the following.</span></span> <span data-ttu-id="80cd1-138">次の例では 1 時間の有効期間、物理削除の 1 日、および削除を実行中のすべてサービス インスタンスが 1 日よりも古い。</span><span class="sxs-lookup"><span data-stu-id="80cd1-138">In the following example, there is a live window of 1 hour, a hard purge of 1 day, and deletes all running service instances older than 1 day:</span></span>  
  
    ```  
    exec dtasp_BackupAndPurgeTrackingDatabase 1, 0, 1, '\\MyBizTalkServer\backup', null, 0, 1  
    ```  
  
8.  <span data-ttu-id="80cd1-139">**ジョブのプロパティ - DTA Purge and Archive (BizTalkDTADb)** ダイアログ ボックスで、**ページの選択** **全般**を選択、**有効**チェック ボックスをオンし、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="80cd1-139">On the **Job Properties - DTA Purge and Archive (BizTalkDTADb)** dialog box, under **Select a page**, select **General**, select the **Enabled** check box, and then select **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80cd1-140">参照</span><span class="sxs-lookup"><span data-stu-id="80cd1-140">See Also</span></span>  
 [<span data-ttu-id="80cd1-141">BizTalk 追跡データベースのアーカイブおよび削除</span><span class="sxs-lookup"><span data-stu-id="80cd1-141">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)
