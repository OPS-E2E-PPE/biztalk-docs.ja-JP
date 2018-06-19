---
title: BizTalk 追跡データベースからデータを削除 |Microsoft ドキュメント
description: BizTalk server 追跡データベース (BizTalkDTADB) を消去する dtasp_PurgeTrackingDatabase ストアド プロシージャを構成します。
ms.custom: ''
ms.date: 10/11/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cdf12866-442d-4c1f-b10f-ebf8d665d521
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06217a7d5012eb402698ad35e76ccfc886952f6e
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
ms.locfileid: "23129707"
---
# <a name="purge-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="e2be5-103">BizTalk 追跡データベースからデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="e2be5-103">Purge Data from the BizTalk Tracking Database</span></span>
<span data-ttu-id="e2be5-104">BizTalk 追跡 (BizTalkDTADb) データベースからデータを削除すると、DTA Purge and Archive ジョブにより、メッセージおよびサービス インスタンスの情報、オーケストレーション イベントの情報、ルール エンジン追跡データなど、さまざまな種類の追跡情報が BizTalk 追跡 (BizTalkDTADb) データベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="e2be5-104">When you purge data from the BizTalk Tracking (BizTalkDTADb) database, the DTA Purge and Archive job purges different types of tracking information such as message and service instance information, orchestration event information, and rules engine tracking data from the BizTalk Tracking (BizTalkDTADb) database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e2be5-105">BizTalk 追跡 (BizTalkDTADb) データベースは、この手順を使用してもアーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="e2be5-105">The BizTalk Tracking (BizTalkDTADb) database is not archived using this procedure.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="e2be5-106">追跡が有効になっていない状態で例外がキャッチされてオーケストレーションで処理されると、開始状態の孤立した追跡インスタンスおよび例外情報が、BizTalk 追跡 (BizTalkDTADb) データベースに挿入される場合があります。</span><span class="sxs-lookup"><span data-stu-id="e2be5-106">If an exception is caught and handled in an orchestration without tracking turned on, an orphaned tracking instance with a Started state and exception information may be inserted into the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="e2be5-107">このレコードは、データベースを削除した後も残ります。</span><span class="sxs-lookup"><span data-stu-id="e2be5-107">This record will remain after purging the database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e2be5-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="e2be5-108">Prerequisites</span></span>  
<span data-ttu-id="e2be5-109">この手順を実行するには、SQL Server の sysadmin 固定サーバー ロールのメンバーであるアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="e2be5-109">Sign in with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
## <a name="purge-data-from-the-biztalk-tracking-database"></a><span data-ttu-id="e2be5-110">BizTalk 追跡データベースからデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="e2be5-110">Purge data from the BizTalk Tracking database</span></span>  
  
1.  <span data-ttu-id="e2be5-111">BizTalk 追跡 (BizTalkDTADb) データベースをホストする SQL Server で開く **SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="e2be5-111">On the SQL Server that hosts the BizTalk Tracking (BizTalkDTADb) database, open **SQL Server Management Studio**.</span></span> 
  
2.  <span data-ttu-id="e2be5-112">**サーバーへの接続**, 、BizTalk 追跡 (BizTalkDTADb) データベースが存在する SQL server の名前を入力、認証の種類を入力し、 **接続** SQL サーバーに接続します。</span><span class="sxs-lookup"><span data-stu-id="e2be5-112">In **Connect to Server**, enter the name of the SQL server where the BizTalk Tracking (BizTalkDTADb) database resides, enter the authentication type, and then select **Connect** to connect to the SQL server.</span></span> 
  
3.  <span data-ttu-id="e2be5-113">ダブルクリックして**SQL Server エージェント**、し、**ジョブ**です。</span><span class="sxs-lookup"><span data-stu-id="e2be5-113">Double-click **SQL Server Agent**, and then select **Jobs**.</span></span>  
  
4.  <span data-ttu-id="e2be5-114">**オブジェクト エクスプ ローラーの詳細**を右クリックして**DTA Purge and Archive (BizTalkDTADb)**、し、**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="e2be5-114">In **Object Explorer Details**, right-click **DTA Purge and Archive (BizTalkDTADb)**, and then select **Properties**.</span></span>  
  
5.  <span data-ttu-id="e2be5-115">**ジョブのプロパティ - DTA Purge and Archive (BizTalkDTADb)****ページの選択****手順**です。</span><span class="sxs-lookup"><span data-stu-id="e2be5-115">In **Job Properties - DTA Purge and Archive (BizTalkDTADb)**, under **Select a page**, select **Steps**.</span></span>  
  
6.  <span data-ttu-id="e2be5-116">**ジョブ ステップの一覧** **、アーカイブし、削除**、し、**編集**です。</span><span class="sxs-lookup"><span data-stu-id="e2be5-116">In **Job step list**, select **Archive and Purge**, and then select **Edit**.</span></span>  
  
7.  <span data-ttu-id="e2be5-117">**ジョブ ステップのプロパティ - Archive and Purge**の**全般**] ページの [、**コマンド**ボックスで、変更**exec dtasp_BackupAndPurgeTrackingDatabase**に**exec dtasp_PurgeTrackingDatabase**です。</span><span class="sxs-lookup"><span data-stu-id="e2be5-117">In **Job Step Properties - Archive and Purge**, on the **General** page, in the **Command** box, change **exec dtasp_BackupAndPurgeTrackingDatabase** to **exec dtasp_PurgeTrackingDatabase**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="e2be5-118">**Exec dtasp_PurgeTrackingDatabase** ストアド プロシージャでは、BizTalk 追跡 (BizTalkDTADb) データベースはアーカイブされません。</span><span class="sxs-lookup"><span data-stu-id="e2be5-118">The **exec dtasp_PurgeTrackingDatabase** stored procedure does not archive the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="e2be5-119">このオプションを使用する前に、アーカイブ済みの追跡データが不要であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e2be5-119">Before using this option, be certain that you no longer require archived tracking data.</span></span>  
  
8.  <span data-ttu-id="e2be5-120">**コマンド**ボックスで、次のパラメーターを更新し、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="e2be5-120">In the **Command** box, update the following parameters, and then select **OK**.</span></span>  
  
    -   <span data-ttu-id="e2be5-121">@nHours tinyint — 完了したインスタンスを (ライブ時間) + (live 日) が関連付けられているすべてのデータと共に削除されます。</span><span class="sxs-lookup"><span data-stu-id="e2be5-121">@nHours tinyint — Any completed instance older than (live hours) + (live days) will be deleted along with all associated data.</span></span>  
  
    -   <span data-ttu-id="e2be5-122">@nDays tinyint — 完了したインスタンスを (ライブ時間) + (live 日) が関連付けられているすべてのデータと共に削除されます。</span><span class="sxs-lookup"><span data-stu-id="e2be5-122">@nDays tinyint — Any completed instance older than (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="e2be5-123">既定の間隔は 1 日です。</span><span class="sxs-lookup"><span data-stu-id="e2be5-123">Default interval is 1 day.</span></span>  
  
    -   <span data-ttu-id="e2be5-124">@nHardDays tinyint — データが不完全な場合でもこの日数より古いすべてのデータは削除されます。</span><span class="sxs-lookup"><span data-stu-id="e2be5-124">@nHardDays tinyint — All data older than this day will be deleted, even if the data is incomplete.</span></span> <span data-ttu-id="e2be5-125">HardDeleteDays に指定する間隔は、データの有効期間よりも大きい値にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2be5-125">The time interval specified for HardDeleteDays should be greater than the live window of data.</span></span> <span data-ttu-id="e2be5-126">データの有効期間は、BizTalk 追跡データベース (BizTalkDTADb) でデータを追跡する間隔になります。</span><span class="sxs-lookup"><span data-stu-id="e2be5-126">The live window of data is the interval of time for which you want to maintain tracking data in the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="e2be5-127">この間隔より古いデータは、次のアーカイブ時にアーカイブしてから削除できます。</span><span class="sxs-lookup"><span data-stu-id="e2be5-127">Anything older than this interval is eligible to be archived at the next archive and then purged.</span></span>  
  
    -   <span data-ttu-id="e2be5-128">@dtLastBackup この設定 **GetUTCDate()** BizTalk 追跡 (BizTalkDTADb) データベースからデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="e2be5-128">@dtLastBackup — Set this to **GetUTCDate()** to purge data from the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="e2be5-129">設定すると **NULL**, 、データは、データベースから削除されません。</span><span class="sxs-lookup"><span data-stu-id="e2be5-129">When set to **NULL**, data is not purged from the database.</span></span>  

    -  <span data-ttu-id="e2be5-130">@fHardDeleteRunningInstances int - 既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="e2be5-130">@fHardDeleteRunningInstances int - Default is 0.</span></span> <span data-ttu-id="e2be5-131">1 に設定すると、そのすべてを削除よりも古いサービス インスタンスを実行している、@nHardDeleteDays値。</span><span class="sxs-lookup"><span data-stu-id="e2be5-131">When set to 1, it deletes all running service instances older than the @nHardDeleteDays value.</span></span>  
    
        > [!NOTE] 
        > <span data-ttu-id="e2be5-132">@fHardDeleteRunningInstancesプロパティは、以降で利用可能な[BizTalk Server 2016 の累積更新プログラム 1年](https://support.microsoft.com/help/3208238/cumulative-update-1-for-microsoft-biztalk-server-2016)、 [BizTalk Server 2013 R2 の累積更新プログラム 6年](https://support.microsoft.com/en-us/help/4020020/cumulative-update-package-6-for-biztalk-server-2013-r2)、および[BizTalk Server 2013 の累積的な更新プログラム 5 適用](https://support.microsoft.com/help/3194301/cumulative-update-5-for-biztalk-server-2013)です。</span><span class="sxs-lookup"><span data-stu-id="e2be5-132">The @fHardDeleteRunningInstances property is available starting with [BizTalk Server 2016 Cumulative Update 1](https://support.microsoft.com/help/3208238/cumulative-update-1-for-microsoft-biztalk-server-2016), [BizTalk Server 2013 R2 Cumulative Update 6](https://support.microsoft.com/en-us/help/4020020/cumulative-update-package-6-for-biztalk-server-2013-r2), and [BizTalk Server 2013 Cumulative Update 5](https://support.microsoft.com/help/3194301/cumulative-update-5-for-biztalk-server-2013).</span></span>   

    <span data-ttu-id="e2be5-133">編集したスクリプトは、次のようにはなります。</span><span class="sxs-lookup"><span data-stu-id="e2be5-133">Your edited script looks similar to the following:</span></span>  
  
    ```  
    declare @dtLastBackup datetime set @dtLastBackup = GetUTCDate() exec dtasp_PurgeTrackingDatabase 1, 0, 1, @dtLastBackup, 1  
    ```  
    
9. <span data-ttu-id="e2be5-134">**ジョブのプロパティ - DTA Purge and Archive (BizTalkDTADb)** ダイアログ ボックスで、**ページの選択****全般**を選択、**有効**チェック ボックスをオンし、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="e2be5-134">On the **Job Properties - DTA Purge and Archive (BizTalkDTADb)** dialog box, under **Select a page**, select **General**, select the **Enabled** check box, and then select **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2be5-135">参照</span><span class="sxs-lookup"><span data-stu-id="e2be5-135">See Also</span></span>  
 [<span data-ttu-id="e2be5-136">BizTalk 追跡データベースのアーカイブおよび削除</span><span class="sxs-lookup"><span data-stu-id="e2be5-136">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)
