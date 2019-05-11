---
title: バックアップ BizTalk Server ジョブのスケジュール |Microsoft Docs
description: BizTalk Server のバックアップ ジョブのパラメーターを構成し、毎月実行、毎週、日単位、または 1 時間ごとに、スケジュールを設定
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
ms.openlocfilehash: 8f3c29d259d8bd8a3cd580c2a945d8cc28b1a68d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384034"
---
# <a name="schedule-the-backup-biztalk-server-job"></a><span data-ttu-id="5d7a7-103">バックアップ BizTalk Server ジョブのスケジュール設定します。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-103">Schedule the Backup BizTalk Server Job</span></span>
<span data-ttu-id="5d7a7-104">バックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブは、SQL Server エージェント サービスにより設定されたスケジュールに従って実行されます。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-104">The Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job runs as scheduled by the SQL Server Agent service.</span></span> <span data-ttu-id="5d7a7-105">頻繁に作成するか、バックアップの実行頻度、バックアップのスケジュールを変更することができる場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SQL Server Management Studio を使用してジョブ。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-105">If you want to create more frequent or less frequent backups, you can change the schedule of the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job by using SQL Server Management Studio.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5d7a7-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="5d7a7-106">Prerequisites</span></span>  
<span data-ttu-id="5d7a7-107">SQL Server の sysadmin 固定サーバー ロールのメンバーであるアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-107">Sign in with an account that is a member of the SQL Server sysadmin fixed server role.</span></span>  
  
## <a name="schedule-the-backup-biztalk-server-job"></a><span data-ttu-id="5d7a7-108">BizTalk Server のバックアップ ジョブのスケジュール設定します。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-108">Schedule the Backup BizTalk Server job</span></span>
  
1. <span data-ttu-id="5d7a7-109">BizTalk 管理データベースをホストする SQL Server で開きます**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-109">On the SQL Server that hosts the BizTalk Management database, open **SQL Server Management Studio**.</span></span>

2. <span data-ttu-id="5d7a7-110">**サーバーへの接続**、データベースが存在すると、BizTalk Server が、認証の種類を選択する SQL Server の名前を入力し、 **Connect**します。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-110">In **Connect to Server**, enter the name of the SQL Server where the BizTalk Server databases reside, select the authentication type, and then **Connect**.</span></span>  
  
3. <span data-ttu-id="5d7a7-111">オブジェクト エクスプ ローラーでダブルクリック**SQL Server エージェント**、し、**ジョブ**します。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-111">In the Object Explorer, double-click **SQL Server Agent**, and then select **Jobs**.</span></span>  
  
4. <span data-ttu-id="5d7a7-112">詳細ペインで右クリックして**BizTalk Server のバックアップ (BizTalkMgmtDb)**、し、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-112">In the details pane, right-click **Backup BizTalk Server (BizTalkMgmtDb)**, and then select **Properties**.</span></span>  
  
5. <span data-ttu-id="5d7a7-113">**ジョブのプロパティ - Backup BizTalk Server (BizTalkMgmtDb)\*\*\*\*ページの選択**を選択します**手順**します。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-113">In the **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)**, under **Select a page**, select **Steps**.</span></span>  
  
6. <span data-ttu-id="5d7a7-114">**ジョブ ステップの一覧**、 **BackupFull**、し、**編集**。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-114">In the **Job step list**, select **BackupFull**, and then select **Edit**.</span></span>  
  
7. <span data-ttu-id="5d7a7-115">**ジョブ ステップのプロパティ - BackupFull**の**コマンド**ボックスに、完全バックアップを実行する頻度を変更することで、コマンドの更新: **'h'** (時間)、**が '** (毎日) **'w'** (毎週)、**います '** (毎月)、 **'y'** (年単位)。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-115">In the **Job Step Properties - BackupFull**, in the **Command** box, update the command by changing the frequency to run a full backup: **'h'** (hourly), **'d'** (daily), **'w'** (weekly), **'m'** (monthly), **'y'** (yearly).</span></span> <span data-ttu-id="5d7a7-116">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-116">Select **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5d7a7-117">最初に、BizTalk Server のバックアップ ジョブの実行時間に、完全バックアップが完了します。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-117">The first time the Backup BizTalk Server job runs, it completes a full backup.</span></span>  
    
8. <span data-ttu-id="5d7a7-118">追加構成<strong>@frequency</strong>パラメーター。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-118">Configure additional <strong>@frequency</strong> parameters:</span></span>  
  
   - <span data-ttu-id="5d7a7-119"><strong>@ForceFullBackupAfterPartialSetFailure</strong>:既定値は **false**です。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-119"><strong>@ForceFullBackupAfterPartialSetFailure</strong>: The default value is **false**.</span></span> <span data-ttu-id="5d7a7-120">ときに**false**完全バックアップが行われるまでは、次のサイクルの完全バックアップの失敗は、システムが待機する場合は、します。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-120">When **false**, if the full backup fails, the system waits for the next cycle until the full backup is made.</span></span>  
    
     > [!NOTE]
     >  <span data-ttu-id="5d7a7-121">場合、 <strong>@frequency</strong>設定は時間の長い (毎週、毎月、毎年) など、このパラメーターを設定**false**危険な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-121">If your <strong>@frequency</strong> setting is long (like weekly, monthly, yearly), then setting this parameter to **false** could be dangerous.</span></span> <span data-ttu-id="5d7a7-122">このシナリオでこのフラグを設定する最適な場合があります**true**します。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-122">In this scenario, it may be best to set this flag to **true**.</span></span> <span data-ttu-id="5d7a7-123">ときに**true**、毎回の障害が発生した、システムを強制的に完全バックアップを作成します。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-123">When **true**, every time there is a failure, the system forces itself to create a full backup.</span></span> <span data-ttu-id="5d7a7-124">、小さなパフォーマンスに影響がある可能性がありますが、回復可能なシステムが safter します。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-124">There may be a small performance impact, but it’s safter to have a recoverable system.</span></span>
  
   - <span data-ttu-id="5d7a7-125"><strong>@BackupHour</strong>:デフォルトの値は NULL です。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-125"><strong>@BackupHour</strong>: The default valueis NULL.</span></span> <span data-ttu-id="5d7a7-126">このパラメーターは直接関連して <strong>@Frequency</strong>します。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-126">This parameter is directly related to <strong>@Frequency</strong>.</span></span> <span data-ttu-id="5d7a7-127">頻度設定すると**h**フル バックアップを実行する曜日を 1 時間を設定する (時間)。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-127">When you set the frequency to **h** (hourly), you set which hour of the day you want the full backup to run.</span></span> <span data-ttu-id="5d7a7-128">0 (深夜) から 23 (11 PM) までの値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-128">You can choose a value between 0 (midnight) to 23 (11 PM).</span></span> <span data-ttu-id="5d7a7-129">空白のまま、完全バックアップは 1 時間ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-129">If left blank, the full backup runs every hour.</span></span>  
    
      > [!NOTE]
       >  <span data-ttu-id="5d7a7-130">0 ~ 23 の範囲 (たとえば、100 または-1) 外の数値をこのパラメーターを設定すると、0 に、システム強制的します。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-130">If you set this parameter with a number outside the 0 to 23 range (for example, 100 or -1), the system forces it to 0.</span></span>
  
   - <span data-ttu-id="5d7a7-131"><strong>@UseLocalTime</strong>:ローカル時刻を使用するという余分なパラメーター。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-131"><strong>@UseLocalTime</strong>: An extra parameter that states to use local time.</span></span> <span data-ttu-id="5d7a7-132">既定では、ジョブは、UTC 時刻で動作します。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-132">By default, the job works with UTC time.</span></span> <span data-ttu-id="5d7a7-133">(これは、UTC + 10 時間) オーストラリアに住んでいる場合は、午前 0 時ではなく、午前 10 時に、バックアップが実行されます。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-133">So if you live in Australia (which is UTC + 10 hours), your backup runs at 10am rather than midnight.</span></span> <span data-ttu-id="5d7a7-134">これを設定するベスト プラクティスとして推奨が**1** (true)。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-134">As a best practice, it is recommended to set this to **1** (true).</span></span>  
  
9. <span data-ttu-id="5d7a7-135">**ジョブのプロパティ - Backup BizTalk Server (BizTalkMgmtDb)**[**ページの選択**、] をクリックして**スケジュール**します。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-135">In the **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)**, under **Select a page**, click **Schedules**.</span></span>  
  
10. <span data-ttu-id="5d7a7-136">**スケジュール一覧**、 をクリックして**MarkAndBackupLogSched**、 をクリックし、**編集**。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-136">In the **Schedule list**, click **MarkAndBackupLogSched**, and then click **Edit**.</span></span>  
  
11. <span data-ttu-id="5d7a7-137">**ジョブ スケジュールのプロパティ - MarkAndBackupLogSched**、スケジュールの種類を選択**定期的**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-137">In the **Job Schedule Properties - MarkAndBackupLogSched**, in Schedule type, select **Recurring** from the drop-down list.</span></span>  
  
     <span data-ttu-id="5d7a7-138">ジョブは、既定のスケジュールでは、15 分ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-138">By default, the job is scheduled to run every 15 minutes.</span></span>  
     
    > [!NOTE]
    >  <span data-ttu-id="5d7a7-139">に従って、要件が最初のテスト、運用環境では、この値を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-139">You can change this value according to your requirements, but first test in non-production environment.</span></span> <span data-ttu-id="5d7a7-140">バックアップの頻度で不足の結果をこの値に設定し、SQL 環境内のバック グラウンドの負荷を追加します。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-140">Setting this value too low results in frequent backups, and adds to the background load in your SQL environment.</span></span> <span data-ttu-id="5d7a7-141">値が高すぎるを設定すると、トランザクション ログのサイズを増やすことがあり、パフォーマンスに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-141">Setting this value too high may increase the size of transaction logs, and impact performance.</span></span> <span data-ttu-id="5d7a7-142">場合によっては、既定値のままにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-142">In some situations, it is recommended to leave the default value.</span></span>    
  
12. <span data-ttu-id="5d7a7-143">必要な場合、スケジュールを更新し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-143">Update the schedule if desired, and then select **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5d7a7-144">[ジョブのスケジュール設定](https://docs.microsoft.com/sql/ssms/agent/schedule-a-job)について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-144">[Scheduling Jobs](https://docs.microsoft.com/sql/ssms/agent/schedule-a-job) provides more details.</span></span>
  
13. <span data-ttu-id="5d7a7-145">**ジョブのプロパティ - Backup BizTalk Server (BizTalkMgmtDb)**、 をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="5d7a7-145">In the **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)**, click **OK**.</span></span>  
  
## <a name="more-good-stuff"></a><span data-ttu-id="5d7a7-146">便利な機能</span><span class="sxs-lookup"><span data-stu-id="5d7a7-146">More good stuff</span></span>  
 <span data-ttu-id="5d7a7-147">[バックアップ BizTalk Server ジョブを構成します。](../core/how-to-configure-the-backup-biztalk-server-job.md) </span><span class="sxs-lookup"><span data-stu-id="5d7a7-147">[Configure the Backup BizTalk Server Job](../core/how-to-configure-the-backup-biztalk-server-job.md) </span></span>  
 <span data-ttu-id="5d7a7-148">[ログ配布用の送信先システムを構成します。](../core/how-to-configure-the-destination-system-for-log-shipping.md) </span><span class="sxs-lookup"><span data-stu-id="5d7a7-148">[Configure the Destination System for Log Shipping](../core/how-to-configure-the-destination-system-for-log-shipping.md) </span></span>  
 <span data-ttu-id="5d7a7-149">[データベースを復元します。](../core/how-to-restore-your-databases.md) </span><span class="sxs-lookup"><span data-stu-id="5d7a7-149">[Restore Your Databases](../core/how-to-restore-your-databases.md) </span></span>  
 [<span data-ttu-id="5d7a7-150">バックアップおよび復元に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="5d7a7-150">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)
