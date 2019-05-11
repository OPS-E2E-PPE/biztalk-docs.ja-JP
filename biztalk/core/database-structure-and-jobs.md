---
title: データベースの構造とジョブ |Microsoft Docs
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
ms.openlocfilehash: f5cf9b5ec724e0070b7425732a74c50d3873bd67
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352588"
---
# <a name="database-structure-and-jobs"></a><span data-ttu-id="61e54-102">データベース構造とジョブ</span><span class="sxs-lookup"><span data-stu-id="61e54-102">Database Structure and Jobs</span></span>
<span data-ttu-id="61e54-103">このトピックでは、データベースの構造とデータベース ジョブについて説明します。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="61e54-103">This topic discusses the database structure and database jobs for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="database-write-diagram"></a><span data-ttu-id="61e54-104">データベース書き込みダイアグラム</span><span class="sxs-lookup"><span data-stu-id="61e54-104">Database Write Diagram</span></span>  
 <span data-ttu-id="61e54-105">次の図は、プロセスと、BizTalk Server データベースに書き込むエンティティを示します。</span><span class="sxs-lookup"><span data-stu-id="61e54-105">The following figure shows the processes and entities that write to the BizTalk Server databases.</span></span>  
  
 <span data-ttu-id="61e54-106">![BizTalk Server データベースに書き込むプロセス](../core/media/ebiz-ops-backup.gif "ebiz_ops_backup")</span><span class="sxs-lookup"><span data-stu-id="61e54-106">![Processes that write to BizTalk Server databases](../core/media/ebiz-ops-backup.gif "ebiz_ops_backup")</span></span>  
  
        Database write diagram showing the processes and entities that write to the BizTalk Server databases  
  
## <a name="biztalk-server-database-jobs"></a><span data-ttu-id="61e54-107">BizTalk Server データベース ジョブ</span><span class="sxs-lookup"><span data-stu-id="61e54-107">BizTalk Server Database Jobs</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="61e54-108">BizTalk Server データベースの管理に役立つ次の SQL Server エージェント ジョブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="61e54-108">includes the following SQL Server Agent jobs to assist you in managing the BizTalk Server databases:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61e54-109">ジョブの名前は、構成時に指定されたデータベース名によって変化します。</span><span class="sxs-lookup"><span data-stu-id="61e54-109">The names of the jobs change depending on the database names given during configuration.</span></span> <span data-ttu-id="61e54-110">環境内で複数のメッセージ ボックス データベースを展開した場合は、各メッセージ ボックスに対して複数のジョブがあります。</span><span class="sxs-lookup"><span data-stu-id="61e54-110">If you have deployed multiple MessageBox databases in your environment, there will be several jobs for each MessageBox.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="61e54-111">BizTalk 管理 (BizTalkMgmtDb) データベースでは、という名前のストアド プロシージャ**adm_CleanupMgmtDB**します。</span><span class="sxs-lookup"><span data-stu-id="61e54-111">In the BizTalk Management (BizTalkMgmtDb) database, there's a stored procedure named **adm_CleanupMgmtDB**.</span></span> <span data-ttu-id="61e54-112">**このストアド プロシージャを実行できません。**</span><span class="sxs-lookup"><span data-stu-id="61e54-112">**DO NOT RUN THIS STORED PROCEDURE!**</span></span> <span data-ttu-id="61e54-113">このストアド プロシージャを実行する場合は、データベース内のすべてのエントリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="61e54-113">If you do run this stored procedure, all the entries in the database will be deleted.</span></span>  
  
|<span data-ttu-id="61e54-114">[ジョブ]</span><span class="sxs-lookup"><span data-stu-id="61e54-114">Job</span></span>|<span data-ttu-id="61e54-115">説明</span><span class="sxs-lookup"><span data-stu-id="61e54-115">Description</span></span>|  
|---------|-----------------|  
|<span data-ttu-id="61e54-116">BizTalk Server (BizTalkMgmtDb) のバックアップします。</span><span class="sxs-lookup"><span data-stu-id="61e54-116">Backup BizTalk Server (BizTalkMgmtDb)</span></span>|<span data-ttu-id="61e54-117">このジョブは、データベース全体と、BizTalk Server データベースのログ バックアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="61e54-117">This job performs full database and log backups of the BizTalk Server databases.</span></span> <span data-ttu-id="61e54-118">構成して、このジョブを実行する方法の詳細についてを参照してください。 [Backing Up and BizTalk Server データベースの復元](../core/backing-up-and-restoring-biztalk-server-databases.md)します。</span><span class="sxs-lookup"><span data-stu-id="61e54-118">For more information about configuring and running this job, see [Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md).</span></span>|  
|<span data-ttu-id="61e54-119">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span><span class="sxs-lookup"><span data-stu-id="61e54-119">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span></span>|<span data-ttu-id="61e54-120">このジョブは、BizTalk 管理 (BizTalkMgmtDb) データベースの有効期限が切れた BizTalk Framework (BTF) エントリをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="61e54-120">This job cleans up expired BizTalk Framework (BTF) entries in the BizTalk Management (BizTalkMgmtDb) database.</span></span>|  
|<span data-ttu-id="61e54-121">DTA Purge and Archive (BizTalkDTADb)</span><span class="sxs-lookup"><span data-stu-id="61e54-121">DTA Purge and Archive (BizTalkDTADb)</span></span>|<span data-ttu-id="61e54-122">このジョブを自動的に BizTalk 追跡 (BizTalkDTADb) データベース内のデータをアーカイブして古いデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="61e54-122">This job automatically archives data in the BizTalk Tracking (BizTalkDTADb) database and purges obsolete data.</span></span> <span data-ttu-id="61e54-123">構成して、このジョブを実行する方法の詳細についてを参照してください。[アーカイブおよび BizTalk 追跡データベースの削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="61e54-123">For more information about configuring and running this job, see [Archiving and Purging the BizTalk Tracking Database](../core/archiving-and-purging-the-biztalk-tracking-database.md).</span></span>|  
|<span data-ttu-id="61e54-124">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="61e54-124">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span></span>|<span data-ttu-id="61e54-125">このジョブは、BizTalk Server ホスト インスタンス (NT サービス) が停止し、別のホスト インスタンスによってに作業できるように、そのホスト インスタンスで行われていたすべての作業を解放するときに検出します。</span><span class="sxs-lookup"><span data-stu-id="61e54-125">This job detects when a BizTalk Server host instance (NT service) has stopped and releases all work that was being done by that host instance so that it can be worked on by another host instance.</span></span>|  
|<span data-ttu-id="61e54-126">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="61e54-126">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span></span>|<span data-ttu-id="61e54-127">このジョブは、不要になった BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースのテーブルで、サブスクライバーによって参照されているすべてのメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="61e54-127">This job removes all messages that are no longer being referenced by any subscribers in the BizTalk MessageBox (BizTalkMsgBoxDb) database tables.</span></span> <span data-ttu-id="61e54-128">**注意が必要です。** これは、MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb ジョブによって起動される、スケジュールされていないジョブです。</span><span class="sxs-lookup"><span data-stu-id="61e54-128">**Caution:**  This is an unscheduled job which is started by the MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb job.</span></span> <span data-ttu-id="61e54-129">この仕事を手動で開始します。</span><span class="sxs-lookup"><span data-stu-id="61e54-129">Do not manually start this job.</span></span>|  
|<span data-ttu-id="61e54-130">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="61e54-130">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span></span>|<span data-ttu-id="61e54-131">このジョブは、メッセージの参照カウント ログを管理し、メッセージは、サブスクライバーによって参照されなくなったときに決定します。</span><span class="sxs-lookup"><span data-stu-id="61e54-131">This job manages the reference count logs for messages and determines when a message is no longer referenced by any subscriber.</span></span> <span data-ttu-id="61e54-132">**注:** この SQL Server エージェント ジョブをスケジュール設定すると、このジョブによって呼び出されるストアド プロシージャには、1 分ごとには、ストアド プロシージャを継続的に実行することを確認するためのロジックが含まれています考えられています。</span><span class="sxs-lookup"><span data-stu-id="61e54-132">**Note:**  Even thought this SQL Server Agent job is scheduled to run once per minute, the stored procedure that is called by this job contains logic to ensure that the stored procedure runs continually.</span></span> <span data-ttu-id="61e54-133">これは、デザインの動作ではあり、変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="61e54-133">This is by design behavior and should not be modified.</span></span>|  
|<span data-ttu-id="61e54-134">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="61e54-134">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span></span>|<span data-ttu-id="61e54-135">このジョブは、不要になった BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースのテーブルで、メッセージによって参照されているすべてのメッセージ部分を削除します。</span><span class="sxs-lookup"><span data-stu-id="61e54-135">This job removes all message parts that are no longer being referenced by any messages in the BizTalk MessageBox (BizTalkMsgBoxDb) database tables.</span></span> <span data-ttu-id="61e54-136">すべてのメッセージは実際のメッセージ データを含む 1 つまたは複数のメッセージ部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="61e54-136">All messages are made up of one or more message parts, which contain the actual message data.</span></span>|  
|<span data-ttu-id="61e54-137">MessageBox_UpdateStats_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="61e54-137">MessageBox_UpdateStats_BizTalkMsgBoxDb</span></span>|<span data-ttu-id="61e54-138">このジョブは、BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースの統計を手動で更新します。</span><span class="sxs-lookup"><span data-stu-id="61e54-138">This job manually updates the statistics for the BizTalk MessageBox (BizTalkMsgBoxDb) database.</span></span>|  
|<span data-ttu-id="61e54-139">BizTalk Server を監視します。</span><span class="sxs-lookup"><span data-stu-id="61e54-139">Monitor BizTalk Server</span></span>|<span data-ttu-id="61e54-140">このジョブのスキャン、BizTalkMgmtDb、BizTalkMsgBoxDb および BizTalkDTADb データベースなど、既知の問題を孤立したインスタンス。</span><span class="sxs-lookup"><span data-stu-id="61e54-140">This job scans the BizTalkMgmtDb, BizTalkMsgBoxDb and BizTalkDTADb database for any known issues, including orphaned instances.</span></span>|  
|<span data-ttu-id="61e54-141">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="61e54-141">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span></span>|<span data-ttu-id="61e54-142">このジョブは、複数のメッセージ ボックスの展開に必要です。</span><span class="sxs-lookup"><span data-stu-id="61e54-142">This job is needed for multiple MessageBox deployments.</span></span> <span data-ttu-id="61e54-143">非同期的に、下位のメッセージ ボックスにそれらの変更が適用された後に、マスター メッセージ ボックスの一括終了などの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="61e54-143">It asynchronously performs operational actions such as bulk terminate on the master MessageBox after those changes have been applied to the subordinate MessageBox.</span></span>|  
|<span data-ttu-id="61e54-144">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="61e54-144">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span></span>|<span data-ttu-id="61e54-145">このジョブは、BizTalk Server メッセージ ボックス (BizTalkMsgBoxDb) データベースから未使用のサブスクリプションの述語を削除します。</span><span class="sxs-lookup"><span data-stu-id="61e54-145">This job purges unused subscription predicates from the BizTalk Server MessageBox (BizTalkMsgBoxDb) database.</span></span>|  
|<span data-ttu-id="61e54-146">Rules_Database_Cleanup_BizTalkRuleEngineDb</span><span class="sxs-lookup"><span data-stu-id="61e54-146">Rules_Database_Cleanup_BizTalkRuleEngineDb</span></span>|<span data-ttu-id="61e54-147">このジョブに自動的に古い監査データ削除ルール エンジン (BizTalkRuleEngineDb) データベースから 90 日ごと。</span><span class="sxs-lookup"><span data-stu-id="61e54-147">This job automatically purges old audit data from the Rule Engine (BizTalkRuleEngineDb) database every 90 days.</span></span> <span data-ttu-id="61e54-148">このジョブも古い履歴データ (展開/展開解除通知) ルール エンジン (BizTalkRuleEngineDb) データベースから 3 日ごと削除します。</span><span class="sxs-lookup"><span data-stu-id="61e54-148">This job also purges old history data (deploy/undeploy notifications) from the Rule Engine (BizTalkRuleEngineDb) database every 3 days.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61e54-149">参照</span><span class="sxs-lookup"><span data-stu-id="61e54-149">See Also</span></span>  
 [<span data-ttu-id="61e54-150">メッセージング エンジン</span><span class="sxs-lookup"><span data-stu-id="61e54-150">The Messaging Engine</span></span>](../core/the-messaging-engine.md)