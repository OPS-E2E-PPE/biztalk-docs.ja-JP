---
title: データベースの構造とジョブ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PurgeSubscriptionsJob_BizTalkMsgBoxDb job
- MessageBox database, jobs [SQL Server Agent]
- DTA Purge and Archive (BizTalkDTADb) job
- TrackedMessages_Copy_BizTalkMsgBoxDb job
- MessageBox_Message_Cleanup_BizTalkMsgBoxDb job
- MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb job
- Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb job
- jobs [SQL Server Agent], MessageBox database
- CleanupBTFExpiredEntriesJob_BizTalkMgmtDb job
- databases, structure
- Tracking database, jobs [SQL Server Agent]
- jobs [SQL Server Agent], Management database
- Backup BizTalk Server (BizTalkMgmtDb) job
- databases, SQL Server Agent jobs
- Business Rules Engine, jobs [SQL Server Agent]
- jobs, databases
- Management database, jobs [SQL Server Agent]
- MessageBox_UpdateStats_BizTalkMsgBoxDb job
- jobs [SQL Server Agent], Business Rules Engine
- Rules_Database_Cleanup_BizTalkRuleEngineDb job
- MessageBox_Parts_Cleanup_BizTalkMsgBoxDb job
- jobs [SQL Server Agent], Tracking database
- MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb job
ms.assetid: f5f6b17d-0f5e-4821-a7eb-c345234ffc65
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf98ef7fe236261fd3ee65ac6f4695455ba8c704
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240562"
---
# <a name="database-structure-and-jobs"></a><span data-ttu-id="5e612-102">データベース構造とジョブ</span><span class="sxs-lookup"><span data-stu-id="5e612-102">Database Structure and Jobs</span></span>
<span data-ttu-id="5e612-103">このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のデータベース構造とデータベース ジョブについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5e612-103">This topic discusses the database structure and database jobs for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="database-write-diagram"></a><span data-ttu-id="5e612-104">データベース書き込みダイアグラム</span><span class="sxs-lookup"><span data-stu-id="5e612-104">Database Write Diagram</span></span>  
 <span data-ttu-id="5e612-105">次の図は、BizTalk Server データベースに書き込むプロセスとエンティティを示しています。</span><span class="sxs-lookup"><span data-stu-id="5e612-105">The following figure shows the processes and entities that write to the BizTalk Server databases.</span></span>  
  
 <span data-ttu-id="5e612-106">![BizTalk Server データベースに書き込むプロセス](../core/media/ebiz-ops-backup.gif "ebiz_ops_backup")</span><span class="sxs-lookup"><span data-stu-id="5e612-106">![Processes that write to BizTalk Server databases](../core/media/ebiz-ops-backup.gif "ebiz_ops_backup")</span></span>  
  
        Database write diagram showing the processes and entities that write to the BizTalk Server databases  
  
## <a name="biztalk-server-database-jobs"></a><span data-ttu-id="5e612-107">BizTalk Server データベース ジョブ</span><span class="sxs-lookup"><span data-stu-id="5e612-107">BizTalk Server Database Jobs</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5e612-108"> には、BizTalk Server データベースの管理に役立つ次の SQL Server エージェント ジョブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5e612-108"> includes the following SQL Server Agent jobs to assist you in managing the BizTalk Server databases:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e612-109">ジョブの名前は、構成時に指定されたデータベース名によって異なります。</span><span class="sxs-lookup"><span data-stu-id="5e612-109">The names of the jobs change depending on the database names given during configuration.</span></span> <span data-ttu-id="5e612-110">使用している環境で複数のメッセージ ボックス データベースが展開されている場合は、各メッセージ ボックスに対して複数のジョブが存在することになります。</span><span class="sxs-lookup"><span data-stu-id="5e612-110">If you have deployed multiple MessageBox databases in your environment, there will be several jobs for each MessageBox.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="5e612-111">BizTalk 管理 (BizTalkMgmtDb) データベースでは、という名前のストアド プロシージャは**adm_CleanupMgmtDB**です。</span><span class="sxs-lookup"><span data-stu-id="5e612-111">In the BizTalk Management (BizTalkMgmtDb) database, there's a stored procedure named **adm_CleanupMgmtDB**.</span></span> <span data-ttu-id="5e612-112">**このストアド プロシージャを実行しないでください。**</span><span class="sxs-lookup"><span data-stu-id="5e612-112">**DO NOT RUN THIS STORED PROCEDURE!**</span></span> <span data-ttu-id="5e612-113">このストアド プロシージャを実行すると、データベースのエントリがすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="5e612-113">If you do run this stored procedure, all the entries in the database will be deleted.</span></span>  
  
|<span data-ttu-id="5e612-114">[ジョブ]</span><span class="sxs-lookup"><span data-stu-id="5e612-114">Job</span></span>|<span data-ttu-id="5e612-115">Description</span><span class="sxs-lookup"><span data-stu-id="5e612-115">Description</span></span>|  
|---------|-----------------|  
|<span data-ttu-id="5e612-116">BizTalk Server のバックアップ (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="5e612-116">Backup BizTalk Server (BizTalkMgmtDb)</span></span>|<span data-ttu-id="5e612-117">このジョブは、BizTalk Server データベースの完全データベース バックアップとログ バックアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e612-117">This job performs full database and log backups of the BizTalk Server databases.</span></span> <span data-ttu-id="5e612-118">構成して、このジョブの実行に関する詳細については、次を参照してください。[をバックアップおよび BizTalk Server データベースの復元](../core/backing-up-and-restoring-biztalk-server-databases.md)です。</span><span class="sxs-lookup"><span data-stu-id="5e612-118">For more information about configuring and running this job, see [Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md).</span></span>|  
|<span data-ttu-id="5e612-119">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span><span class="sxs-lookup"><span data-stu-id="5e612-119">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span></span>|<span data-ttu-id="5e612-120">このジョブは、BizTalk 管理 (BizTalkMgmtDb) データベース内にある期限が切れた BizTalk Framework (BTF) エントリをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="5e612-120">This job cleans up expired BizTalk Framework (BTF) entries in the BizTalk Management (BizTalkMgmtDb) database.</span></span>|  
|<span data-ttu-id="5e612-121">DTA Purge and Archive (BizTalkDTADb)</span><span class="sxs-lookup"><span data-stu-id="5e612-121">DTA Purge and Archive (BizTalkDTADb)</span></span>|<span data-ttu-id="5e612-122">このジョブは、BizTalk 追跡 (BizTalkDTADb) データベースのデータを自動的にアーカイブして古いデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="5e612-122">This job automatically archives data in the BizTalk Tracking (BizTalkDTADb) database and purges obsolete data.</span></span> <span data-ttu-id="5e612-123">構成して、このジョブの実行に関する詳細については、次を参照してください。[アーカイブ化および BizTalk 追跡データベースを削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="5e612-123">For more information about configuring and running this job, see [Archiving and Purging the BizTalk Tracking Database](../core/archiving-and-purging-the-biztalk-tracking-database.md).</span></span>|  
|<span data-ttu-id="5e612-124">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="5e612-124">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span></span>|<span data-ttu-id="5e612-125">このジョブは、BizTalk Server ホスト インスタンス (NT サービス) の停止を検出し、そのホスト インスタンスで行われていたすべての作業を解放して、別のホスト インスタンスが作業できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5e612-125">This job detects when a BizTalk Server host instance (NT service) has stopped and releases all work that was being done by that host instance so that it can be worked on by another host instance.</span></span>|  
|<span data-ttu-id="5e612-126">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="5e612-126">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span></span>|<span data-ttu-id="5e612-127">このジョブは、BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベース テーブルで、サブスクライバーによって参照されなくなったすべてのメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="5e612-127">This job removes all messages that are no longer being referenced by any subscribers in the BizTalk MessageBox (BizTalkMsgBoxDb) database tables.</span></span> <span data-ttu-id="5e612-128">**注意:** MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb ジョブによって開始された、スケジュールされていないジョブです。</span><span class="sxs-lookup"><span data-stu-id="5e612-128">**Caution:**  This is an unscheduled job which is started by the MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb job.</span></span> <span data-ttu-id="5e612-129">このジョブを手動で開始しないでください。</span><span class="sxs-lookup"><span data-stu-id="5e612-129">Do not manually start this job.</span></span>|  
|<span data-ttu-id="5e612-130">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="5e612-130">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span></span>|<span data-ttu-id="5e612-131">このジョブは、メッセージの参照カウント ログを管理し、サブスクライバーによってジョブが参照されなくなったかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="5e612-131">This job manages the reference count logs for messages and determines when a message is no longer referenced by any subscriber.</span></span> <span data-ttu-id="5e612-132">**注:** でもこのジョブによって呼び出されるストアド プロシージャがストアド プロシージャを継続的に実行することを確認するためのロジックを含む、1 分ごと 1 回実行するこの SQL Server エージェント ジョブがスケジュールされていると思っています。</span><span class="sxs-lookup"><span data-stu-id="5e612-132">**Note:**  Even thought this SQL Server Agent job is scheduled to run once per minute, the stored procedure that is called by this job contains logic to ensure that the stored procedure runs continually.</span></span> <span data-ttu-id="5e612-133">この動作は仕様によるものなので、変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="5e612-133">This is by design behavior and should not be modified.</span></span>|  
|<span data-ttu-id="5e612-134">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="5e612-134">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span></span>|<span data-ttu-id="5e612-135">このジョブは、BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベース テーブルで、メッセージによって参照されなくなったすべてのメッセージ部分を削除します。</span><span class="sxs-lookup"><span data-stu-id="5e612-135">This job removes all message parts that are no longer being referenced by any messages in the BizTalk MessageBox (BizTalkMsgBoxDb) database tables.</span></span> <span data-ttu-id="5e612-136">すべてのメッセージは、実際のメッセージ データを含んでいる 1 つまたは複数のメッセージ部分で構成されています。</span><span class="sxs-lookup"><span data-stu-id="5e612-136">All messages are made up of one or more message parts, which contain the actual message data.</span></span>|  
|<span data-ttu-id="5e612-137">MessageBox_UpdateStats_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="5e612-137">MessageBox_UpdateStats_BizTalkMsgBoxDb</span></span>|<span data-ttu-id="5e612-138">このジョブは、BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースの統計を手動で更新します。</span><span class="sxs-lookup"><span data-stu-id="5e612-138">This job manually updates the statistics for the BizTalk MessageBox (BizTalkMsgBoxDb) database.</span></span>|  
|<span data-ttu-id="5e612-139">BizTalk Server の監視</span><span class="sxs-lookup"><span data-stu-id="5e612-139">Monitor BizTalk Server</span></span>|<span data-ttu-id="5e612-140">このジョブは、孤立したインスタンスなど、既知の問題について BizTalkMgmtDb、BizTalkMsgBoxDb および BizTalkDTADb データベースをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="5e612-140">This job scans the BizTalkMgmtDb, BizTalkMsgBoxDb and BizTalkDTADb database for any known issues, including orphaned instances.</span></span>|  
|<span data-ttu-id="5e612-141">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="5e612-141">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span></span>|<span data-ttu-id="5e612-142">このジョブは、複数のメッセージ ボックスを展開する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="5e612-142">This job is needed for multiple MessageBox deployments.</span></span> <span data-ttu-id="5e612-143">下位のメッセージ ボックスに変更を適用した後の、マスター メッセージ ボックスの一括終了などの操作アクションを非同期で実行します。</span><span class="sxs-lookup"><span data-stu-id="5e612-143">It asynchronously performs operational actions such as bulk terminate on the master MessageBox after those changes have been applied to the subordinate MessageBox.</span></span>|  
|<span data-ttu-id="5e612-144">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="5e612-144">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span></span>|<span data-ttu-id="5e612-145">このジョブは、使用されていないサブスクリプションの述語を BizTalk Server メッセージ ボックス (BizTalkMsgBoxDb) データベースから削除します。</span><span class="sxs-lookup"><span data-stu-id="5e612-145">This job purges unused subscription predicates from the BizTalk Server MessageBox (BizTalkMsgBoxDb) database.</span></span>|  
|<span data-ttu-id="5e612-146">Rules_Database_Cleanup_BizTalkRuleEngineDb</span><span class="sxs-lookup"><span data-stu-id="5e612-146">Rules_Database_Cleanup_BizTalkRuleEngineDb</span></span>|<span data-ttu-id="5e612-147">このジョブは、古い監査データをルール エンジン (BizTalkRuleEngineDb) データベースから 90 日ごとに自動的に削除します。</span><span class="sxs-lookup"><span data-stu-id="5e612-147">This job automatically purges old audit data from the Rule Engine (BizTalkRuleEngineDb) database every 90 days.</span></span> <span data-ttu-id="5e612-148">また、このジョブは、ルール エンジン (BizTalkRuleEngineDb) データベースから 3 日ごとに古い履歴データ (展開/展開解除通知など) を削除します。</span><span class="sxs-lookup"><span data-stu-id="5e612-148">This job also purges old history data (deploy/undeploy notifications) from the Rule Engine (BizTalkRuleEngineDb) database every 3 days.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5e612-149">参照</span><span class="sxs-lookup"><span data-stu-id="5e612-149">See Also</span></span>  
 [<span data-ttu-id="5e612-150">メッセージング エンジン</span><span class="sxs-lookup"><span data-stu-id="5e612-150">The Messaging Engine</span></span>](../core/the-messaging-engine.md)