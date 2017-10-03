---
title: "バックアップの BizTalk Server のジョブをスケジュールする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up, scheduling
- backing up, backup jobs
- scheduling, backup jobs
ms.assetid: 6e89fff4-da87-4cdc-acc4-46f03c3269fc
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d6b40ae933874e1c25cb3a93dbbeab514ef5dfe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-schedule-the-backup-biztalk-server-job"></a><span data-ttu-id="31fbb-102">BizTalk Server のバックアップ ジョブのスケジュールを設定する方法</span><span class="sxs-lookup"><span data-stu-id="31fbb-102">How to Schedule the Backup BizTalk Server Job</span></span>
<span data-ttu-id="31fbb-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブは、SQL Server エージェント サービスにより設定されたスケジュールに従って実行されます。</span><span class="sxs-lookup"><span data-stu-id="31fbb-103">The Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job runs as scheduled by the SQL Server Agent service.</span></span> <span data-ttu-id="31fbb-104">バックアップの実行頻度を変更するには、SQL Server Management Studio を使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブのスケジュールを変更します。</span><span class="sxs-lookup"><span data-stu-id="31fbb-104">If you want to create more frequent or less frequent backups, you can change the schedule of the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job by using SQL Server Management Studio.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="31fbb-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="31fbb-105">Prerequisites</span></span>  
 <span data-ttu-id="31fbb-106">この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="31fbb-106">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-schedule-the-backup-biztalk-server-job-sql-server-2008"></a><span data-ttu-id="31fbb-107">BizTalk Server のバックアップ ジョブ (SQL Server 2008) をスケジュールするには</span><span class="sxs-lookup"><span data-stu-id="31fbb-107">To schedule the Backup BizTalk Server job (SQL Server 2008)</span></span>  
  
1.  <span data-ttu-id="31fbb-108">を BizTalk 管理データベースが格納されているコンピューターでをクリックして**開始**、をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**、をクリックして**Microsoft SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="31fbb-108">On the computer that contains the BizTalk Management database, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, and then click **Microsoft SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="31fbb-109">**サーバーへの接続** ダイアログ ボックスで、BizTalk Server がデータベース、SQL Server の名前が存在するを指定し、適切な認証の種類をクリックし、**接続**です。</span><span class="sxs-lookup"><span data-stu-id="31fbb-109">In the **Connect to Server** dialog box, specify the name of the SQL Server where the BizTalk Server databases reside and the appropriate authentication type, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="31fbb-110">オブジェクト エクスプ ローラーをダブルクリックして**SQL Server エージェント**、クリックして**ジョブ**です。</span><span class="sxs-lookup"><span data-stu-id="31fbb-110">In the Object Explorer, double-click **SQL Server Agent**, and then click **Jobs**.</span></span>  
  
4.  <span data-ttu-id="31fbb-111">詳細ウィンドウで右クリック**Backup BizTalk Server (BizTalkMgmtDb)**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="31fbb-111">In the details pane, right-click **Backup BizTalk Server (BizTalkMgmtDb)**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="31fbb-112">**ジョブのプロパティ - Backup BizTalk Server (BizTalkMgmtDb)**ダイアログ ボックスで、**ページの選択**をクリックして**手順**です。</span><span class="sxs-lookup"><span data-stu-id="31fbb-112">In the **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)** dialog box, under **Select a page**, click **Steps**.</span></span>  
  
6.  <span data-ttu-id="31fbb-113">**ジョブ ステップの一覧**をクリックして**BackupFull**、順にクリック**編集**です。</span><span class="sxs-lookup"><span data-stu-id="31fbb-113">In the **Job step list**, click **BackupFull**, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="31fbb-114">**ジョブ ステップのプロパティ - BackupFull**  ダイアログ ボックスで、**コマンド**ボックスで、完全バックアップを実行する間隔を頻度を変更することで、コマンドを編集: **'h'**(1 時間ごと)、**が '** (毎日) **'w'** (毎週)、 **am'** (毎月)、 **'y'** (毎年) をクリックし、 **ok**.</span><span class="sxs-lookup"><span data-stu-id="31fbb-114">In the **Job Step Properties - BackupFull** dialog box, in the **Command** box, edit the command by changing the frequency to the desired interval at which to perform a full backup: **'h'** (hourly), **'d'** (daily), **'w'** (weekly), **'m'** (monthly), **'y'** (yearly), and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="31fbb-115">新しく設定した間隔で BizTalk Server のバックアップ ジョブが最初に実行される際には、完全バックアップが実行されます。</span><span class="sxs-lookup"><span data-stu-id="31fbb-115">The first time the Backup BizTalk Server job is run during a new period, a full backup is performed.</span></span>  
  
8.  <span data-ttu-id="31fbb-116">**ジョブのプロパティ - Backup BizTalk Server (BizTalkMgmtDb)**ダイアログ ボックスで、**ページの選択**をクリックして**スケジュール**です。</span><span class="sxs-lookup"><span data-stu-id="31fbb-116">In the **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)** dialog box, under **Select a page**, click **Schedules**.</span></span>  
  
9. <span data-ttu-id="31fbb-117">**スケジュール一覧**、 をクリックして**MarkAndBackupLogSched**、クリックして**編集**です。</span><span class="sxs-lookup"><span data-stu-id="31fbb-117">In the **Schedule list**, click **MarkAndBackupLogSched**, and then click **Edit**.</span></span>  
  
10. <span data-ttu-id="31fbb-118">**ジョブ スケジュールのプロパティ - MarkAndBackupLogSched**スケジュールの種類を選択 ダイアログ ボックス**定期的**(既に選択されていない) 場合は、ドロップダウン リスト ボックスからです。</span><span class="sxs-lookup"><span data-stu-id="31fbb-118">In the **Job Schedule Properties - MarkAndBackupLogSched** dialog box, in Schedule type, select **Recurring** from the drop-down list box (if it is not already selected).</span></span>  
  
     <span data-ttu-id="31fbb-119">既定では、ジョブが 15 分おきに実行されるようにスケジュールが設定されます。</span><span class="sxs-lookup"><span data-stu-id="31fbb-119">By default, the job is scheduled to run every 15 minutes.</span></span>  
  
11. <span data-ttu-id="31fbb-120">必要に応じて、スケジュールを更新し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="31fbb-120">Update the schedule as desired, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="31fbb-121">SQL Server エージェント ジョブのスケジュール設定に関する詳細については、次を参照してください"[ジョブのスケジュール](http://go.microsoft.com/fwlink/?LinkId=195887)。"。</span><span class="sxs-lookup"><span data-stu-id="31fbb-121">For more information about scheduling SQL Server Agent jobs, see "[Scheduling Jobs](http://go.microsoft.com/fwlink/?LinkId=195887)."</span></span>  
  
12. <span data-ttu-id="31fbb-122">**ジョブのプロパティ - Backup BizTalk Server (BizTalkMgmtDb)**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="31fbb-122">In the **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31fbb-123">参照</span><span class="sxs-lookup"><span data-stu-id="31fbb-123">See Also</span></span>  
 <span data-ttu-id="31fbb-124">[バックアップの BizTalk Server ジョブを構成する方法](../core/how-to-configure-the-backup-biztalk-server-job.md) </span><span class="sxs-lookup"><span data-stu-id="31fbb-124">[How to Configure the Backup BizTalk Server Job](../core/how-to-configure-the-backup-biztalk-server-job.md) </span></span>  
 <span data-ttu-id="31fbb-125">[ログ配布用に送信先システムを構成する方法](../core/how-to-configure-the-destination-system-for-log-shipping.md) </span><span class="sxs-lookup"><span data-stu-id="31fbb-125">[How to Configure the Destination System for Log Shipping](../core/how-to-configure-the-destination-system-for-log-shipping.md) </span></span>  
 <span data-ttu-id="31fbb-126">[データベースを復元する方法](../core/how-to-restore-your-databases.md) </span><span class="sxs-lookup"><span data-stu-id="31fbb-126">[How to Restore Your Databases](../core/how-to-restore-your-databases.md) </span></span>  
 [<span data-ttu-id="31fbb-127">バックアップと復元に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="31fbb-127">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)