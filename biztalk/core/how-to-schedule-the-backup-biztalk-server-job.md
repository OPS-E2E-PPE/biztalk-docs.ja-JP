---
title: バックアップの BizTalk Server のジョブのスケジュールを設定 |Microsoft ドキュメント
description: BizTalk Server のバックアップ ジョブのパラメーターを構成および実行毎月、毎週、日単位、または 1 時間ごとに、スケジュールを設定
ms.custom: ''
ms.date: 11/02/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e89fff4-da87-4cdc-acc4-46f03c3269fc
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f09ca97f65605ac3bf427d1c1fcc322a14feb53
ms.sourcegitcommit: 9aaed443492b74729171fef79c634bff561af929
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2017
ms.locfileid: "23980754"
---
# <a name="schedule-the-backup-biztalk-server-job"></a><span data-ttu-id="2fa8d-103">バックアップの BizTalk Server ジョブのスケジュール</span><span class="sxs-lookup"><span data-stu-id="2fa8d-103">Schedule the Backup BizTalk Server Job</span></span>
<span data-ttu-id="2fa8d-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブは、SQL Server エージェント サービスにより設定されたスケジュールに従って実行されます。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-104">The Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job runs as scheduled by the SQL Server Agent service.</span></span> <span data-ttu-id="2fa8d-105">バックアップの実行頻度を変更するには、SQL Server Management Studio を使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブのスケジュールを変更します。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-105">If you want to create more frequent or less frequent backups, you can change the schedule of the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job by using SQL Server Management Studio.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2fa8d-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="2fa8d-106">Prerequisites</span></span>  
<span data-ttu-id="2fa8d-107">SQL Server の sysadmin 固定サーバー ロールのメンバーであるアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-107">Sign in with an account that is a member of the SQL Server sysadmin fixed server role.</span></span>  
  
## <a name="schedule-the-backup-biztalk-server-job"></a><span data-ttu-id="2fa8d-108">BizTalk Server のバックアップ ジョブのスケジュール</span><span class="sxs-lookup"><span data-stu-id="2fa8d-108">Schedule the Backup BizTalk Server job</span></span>
  
1.  <span data-ttu-id="2fa8d-109">BizTalk 管理データベースをホストする SQL Server で開く**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-109">On the SQL Server that hosts the BizTalk Management database, open **SQL Server Management Studio**.</span></span>

2.  <span data-ttu-id="2fa8d-110">**サーバーへの接続**、ここでデータベースが存在する、BizTalk Server は、認証の種類を選択します。 SQL Server の名前を入力し、**接続**です。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-110">In **Connect to Server**, enter the name of the SQL Server where the BizTalk Server databases reside, select the authentication type, and then **Connect**.</span></span>  
  
3.  <span data-ttu-id="2fa8d-111">オブジェクト エクスプ ローラーでダブルクリック**SQL Server エージェント**、し、**ジョブ**です。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-111">In the Object Explorer, double-click **SQL Server Agent**, and then select **Jobs**.</span></span>  
  
4.  <span data-ttu-id="2fa8d-112">詳細ウィンドウで右クリック**Backup BizTalk Server (BizTalkMgmtDb)**、し、**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-112">In the details pane, right-click **Backup BizTalk Server (BizTalkMgmtDb)**, and then select **Properties**.</span></span>  
  
5.  <span data-ttu-id="2fa8d-113">**ジョブのプロパティ - Backup BizTalk Server (BizTalkMgmtDb)****ページの選択****手順**です。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-113">In the **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)**, under **Select a page**, select **Steps**.</span></span>  
  
6.  <span data-ttu-id="2fa8d-114">**ジョブ ステップの一覧** **BackupFull**、し、**編集**です。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-114">In the **Job step list**, select **BackupFull**, and then select **Edit**.</span></span>  
  
7.  <span data-ttu-id="2fa8d-115">**ジョブ ステップのプロパティ - BackupFull**で、**コマンド**ボックスで、完全バックアップを実行する頻度を変更することで、コマンドを更新します **'h'** (1 時間ごと)、**が '。** (毎日) **'w'** (毎週)、 **am'** (毎月)、 **'y'** (毎年)。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-115">In the **Job Step Properties - BackupFull**, in the **Command** box, update the command by changing the frequency to run a full backup: **'h'** (hourly), **'d'** (daily), **'w'** (weekly), **'m'** (monthly), **'y'** (yearly).</span></span> <span data-ttu-id="2fa8d-116">**[ OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-116">Select **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2fa8d-117">BizTalk Server のバックアップ ジョブを初めて実行するには、完全バックアップが完了します。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-117">The first time the Backup BizTalk Server job runs, it completes a full backup.</span></span>  
    
8.  <span data-ttu-id="2fa8d-118">追加の構成 **@frequency** パラメーター。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-118">Configure additional **@frequency** parameters:</span></span>  
  
    - <span data-ttu-id="2fa8d-119">**@ForceFullBackupAfterPartialSetFailure**: 既定値は**false**です。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-119">**@ForceFullBackupAfterPartialSetFailure**: The default value is **false**.</span></span> <span data-ttu-id="2fa8d-120">ときに**false**次回のサイクル、完全バックアップが行われるまで、完全バックアップが失敗したら、システムが待機する場合、します。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-120">When **false**, if the full backup fails, the system waits for the next cycle until the full backup is made.</span></span>  
    
        > [!NOTE]
        >  <span data-ttu-id="2fa8d-121">場合、  **@frequency** 設定が長い (毎週、月、毎年) などし、このパラメーターを設定**false**危険な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-121">If your **@frequency** setting is long (like weekly, monthly, yearly), then setting this parameter to **false** could be dangerous.</span></span> <span data-ttu-id="2fa8d-122">このシナリオである可能性がありますにこのフラグを設定することをお**true**です。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-122">In this scenario, it may be best to set this flag to **true**.</span></span> <span data-ttu-id="2fa8d-123">ときに**true**、毎回の障害が発生した、システム強制的に完全バックアップを作成します。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-123">When **true**, every time there is a failure, the system forces itself to create a full backup.</span></span> <span data-ttu-id="2fa8d-124">小さいパフォーマンスに影響がある可能性がありますが、回復可能なシステムが safter です。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-124">There may be a small performance impact, but it’s safter to have a recoverable system.</span></span>
  
    - <span data-ttu-id="2fa8d-125">**@BackupHour**: デフォルトの値は NULL です。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-125">**@BackupHour**: The default valueis NULL.</span></span> <span data-ttu-id="2fa8d-126">このパラメーターに直接関係する **@Frequency**です。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-126">This parameter is directly related to **@Frequency**.</span></span> <span data-ttu-id="2fa8d-127">頻度を設定すると**h**完全バックアップを実行する曜日を 1 時間を設定する (時間単位)。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-127">When you set the frequency to **h** (hourly), you set which hour of the day you want the full backup to run.</span></span> <span data-ttu-id="2fa8d-128">0 (深夜) から 23 (11 PM) までの値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-128">You can choose a value between 0 (midnight) to 23 (11 PM).</span></span> <span data-ttu-id="2fa8d-129">空白の場合、完全バックアップには、1 時間ごとが実行されます。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-129">If left blank, the full backup runs every hour.</span></span>  
    
       > [!NOTE]
        >  <span data-ttu-id="2fa8d-130">(たとえば、100 または-1) 0 ~ 23 の範囲外の数値でこのパラメーターを設定する場合、システム リテラルに 0 です。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-130">If you set this parameter with a number outside the 0 to 23 range (for example, 100 or -1), the system forces it to 0.</span></span>
  
    - <span data-ttu-id="2fa8d-131">**@UseLocalTime**: ローカル時刻を使用する状態余分なパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-131">**@UseLocalTime**: An extra parameter that states to use local time.</span></span> <span data-ttu-id="2fa8d-132">既定では、ジョブは UTC 時刻で動作します。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-132">By default, the job works with UTC time.</span></span> <span data-ttu-id="2fa8d-133">したがってオーストラリア (これは、UTC + 10 時間) に住んでいる場合は、午前 0 時ではなく、午前 10 時、バックアップが実行されます。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-133">So if you live in Australia (which is UTC + 10 hours), your backup runs at 10am rather than midnight.</span></span> <span data-ttu-id="2fa8d-134">ベスト プラクティスとしてお勧めこの**1** (true)。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-134">As a best practice, it is recommended to set this to **1** (true).</span></span>  
  
9.  <span data-ttu-id="2fa8d-135">**ジョブのプロパティ - Backup BizTalk Server (BizTalkMgmtDb)****ページの選択**をクリックして**スケジュール**です。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-135">In the **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)**, under **Select a page**, click **Schedules**.</span></span>  
  
10. <span data-ttu-id="2fa8d-136">**スケジュール一覧**、 をクリックして**MarkAndBackupLogSched**、クリックして**編集**です。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-136">In the **Schedule list**, click **MarkAndBackupLogSched**, and then click **Edit**.</span></span>  
  
11. <span data-ttu-id="2fa8d-137">**ジョブ スケジュールのプロパティ - MarkAndBackupLogSched**、スケジュールの種類の選択**定期的**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-137">In the **Job Schedule Properties - MarkAndBackupLogSched**, in Schedule type, select **Recurring** from the drop-down list.</span></span>  
  
     <span data-ttu-id="2fa8d-138">既定では、ジョブが 15 分おきに実行されるようにスケジュールが設定されます。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-138">By default, the job is scheduled to run every 15 minutes.</span></span>  
     
    > [!NOTE]
    >  <span data-ttu-id="2fa8d-139">に従って、要件が、運用環境以外の最初のテストには、この値を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-139">You can change this value according to your requirements, but first test in non-production environment.</span></span> <span data-ttu-id="2fa8d-140">頻繁なバックアップで低すぎる結果をこの値に設定し、SQL 環境内で負荷を背景に追加します。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-140">Setting this value too low results in frequent backups, and adds to the background load in your SQL environment.</span></span> <span data-ttu-id="2fa8d-141">この値が大きすぎるを設定すると、トランザクション ログのサイズを増やすことがあり、パフォーマンスに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-141">Setting this value too high may increase the size of transaction logs, and impact performance.</span></span> <span data-ttu-id="2fa8d-142">一部の状況で、既定値のままにしておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-142">In some situations, it is recommended to leave the default value.</span></span>    
  
12. <span data-ttu-id="2fa8d-143">必要な場合、スケジュールを更新し、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-143">Update the schedule if desired, and then select **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2fa8d-144">[ジョブのスケジュール](https://docs.microsoft.com/sql/ssms/agent/schedule-a-job)詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-144">[Scheduling Jobs](https://docs.microsoft.com/sql/ssms/agent/schedule-a-job) provides more details.</span></span>
  
13. <span data-ttu-id="2fa8d-145">**ジョブのプロパティ - Backup BizTalk Server (BizTalkMgmtDb)** をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="2fa8d-145">In the **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)**, click **OK**.</span></span>  
  
## <a name="more-good-stuff"></a><span data-ttu-id="2fa8d-146">便利な機能</span><span class="sxs-lookup"><span data-stu-id="2fa8d-146">More good stuff</span></span>  
 <span data-ttu-id="2fa8d-147">[バックアップの BizTalk Server のジョブを構成します。](../core/how-to-configure-the-backup-biztalk-server-job.md) </span><span class="sxs-lookup"><span data-stu-id="2fa8d-147">[Configure the Backup BizTalk Server Job](../core/how-to-configure-the-backup-biztalk-server-job.md) </span></span>  
 <span data-ttu-id="2fa8d-148">[ログ配布の送信先システムを構成します。](../core/how-to-configure-the-destination-system-for-log-shipping.md) </span><span class="sxs-lookup"><span data-stu-id="2fa8d-148">[Configure the Destination System for Log Shipping](../core/how-to-configure-the-destination-system-for-log-shipping.md) </span></span>  
 <span data-ttu-id="2fa8d-149">[データベースを復元します。](../core/how-to-restore-your-databases.md) </span><span class="sxs-lookup"><span data-stu-id="2fa8d-149">[Restore Your Databases](../core/how-to-restore-your-databases.md) </span></span>  
 [<span data-ttu-id="2fa8d-150">バックアップおよび復元に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="2fa8d-150">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)
