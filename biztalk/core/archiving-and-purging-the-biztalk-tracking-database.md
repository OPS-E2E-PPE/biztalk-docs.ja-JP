---
title: "アーカイブおよび BizTalk 追跡データベースの削除 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, purging
- BizTalk Server, maintaining
- archiving [Tracking database]
- purging
- Tracking database, maintaining
- Tracking database, archiving
- maintaining, Tracking database
- maintaining, BizTalk Server
ms.assetid: 7014cf31-86e8-4829-8055-056442329009
caps.latest.revision: "37"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8fc75f5218ec7a189d28c7120cf23a3047c1752
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="archiving-and-purging-the-biztalk-tracking-database"></a><span data-ttu-id="a43f8-102">BizTalk 追跡データベースのアーカイブおよび削除</span><span class="sxs-lookup"><span data-stu-id="a43f8-102">Archiving and Purging the BizTalk Tracking Database</span></span>
<span data-ttu-id="a43f8-103">BizTalk Server ではシステム上のより多くのデータが処理されるため、BizTalk 追跡 (BizTalkDTADb) データベースのサイズは増え続けます。</span><span class="sxs-lookup"><span data-stu-id="a43f8-103">As BizTalk Server processes more and more data on your system, the BizTalk Tracking (BizTalkDTADb) database continues to grow in size.</span></span> <span data-ttu-id="a43f8-104">サイズが増加してもチェックされないので、システム パフォーマンスが低下し、TDDS (Tracking Data Decode Service) でエラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="a43f8-104">Unchecked growth decreases system performance and may generate errors in the Tracking Data Decode Service (TDDS).</span></span> <span data-ttu-id="a43f8-105">一般的な追跡データに加えて、追跡メッセージもメッセージ ボックス データベースに累積されます。これにより、ディスクのパフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="a43f8-105">In addition to general tracking data, tracked messages can also accumulate in the MessageBox database, causing poor disk performance.</span></span>  
  
 <span data-ttu-id="a43f8-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の以前のバージョンには、追跡メッセージのアーカイブ化および BizTalk 追跡データベースの削除用のサンプル スクリプトが含まれていましたが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では DTA Purge and Archive ジョブの使用により両方のプロセスが自動化されています。</span><span class="sxs-lookup"><span data-stu-id="a43f8-106">While previous versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] included sample scripts for archiving tracked messages and purging the BizTalk Tracking database, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] automates both processes using the DTA Purge and Archive job.</span></span> <span data-ttu-id="a43f8-107">BizTalk 追跡データベースからデータをアーカイブまたは削除することで、システムを正常な状態に保てるだけでなく、アーカイブされた追跡データを将来使用するために保持できます。</span><span class="sxs-lookup"><span data-stu-id="a43f8-107">By archiving and purging data from the BizTalk Tracking database, you can maintain a healthy system, as well as keep your tracking data archived for future use.</span></span> <span data-ttu-id="a43f8-108">BizTalk 追跡データベースのアーカイブは、長期にわたって累積され、ディスク領域を消費するため、定期的にセカンダリ ストレージに移動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a43f8-108">Because BizTalk Tracking database archives accumulate over time and consume disk space, it is a good idea to move the BizTalk Tracking database archives to secondary storage on a regular basis.</span></span>  
  
 <span data-ttu-id="a43f8-109">BizTalk 追跡データベースからデータを削除すると、DTA Purge and Archive ジョブにより、メッセージおよびサービス インスタンスの情報、オーケストレーション イベントの情報、ルール エンジンの追跡データなど、さまざまな種類の追跡情報が削除されます。</span><span class="sxs-lookup"><span data-stu-id="a43f8-109">When you purge data from the BizTalk Tracking database, the DTA Purge and Archive job purges different types of tracking information such as message and service instance information, orchestration event information, and rules engine tracking data.</span></span>  
  
 <span data-ttu-id="a43f8-110">追跡データ レコードの経過期間は、追跡データが BizTalk 追跡データベースに挿入された時刻に基づきます。</span><span class="sxs-lookup"><span data-stu-id="a43f8-110">The age of a tracking data record is based on the time the tracking data was inserted into the BizTalk Tracking database.</span></span> <span data-ttu-id="a43f8-111">DTA Purge and Archive ジョブでは、このタイム スタンプを使用して、そのレコードがデータの有効期間よりも古くなっていないかどうかが継続的にチェックされます。</span><span class="sxs-lookup"><span data-stu-id="a43f8-111">The DTA Purge and Archive job uses the time stamp to continuously verify whether the record is older than the live window of data.</span></span> <span data-ttu-id="a43f8-112">有効期間が過ぎると、そのたびに BizTalk 追跡データベースがアーカイブされ、新しいアーカイブ ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a43f8-112">After every live window period, the BizTalk Tracking database is archived and a new archive file is created.</span></span> <span data-ttu-id="a43f8-113">さらに、ジョブ スケジュールで指定された SQL Server エージェント ジョブの間隔ごとに、完了した追跡データのうち、有効期間を経過しているものがすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="a43f8-113">At each SQL Server Agent job interval specified by the job schedule, all completed tracking data older than the live window period is purged.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a43f8-114"> では、論理削除と物理削除の概念が使用されています。</span><span class="sxs-lookup"><span data-stu-id="a43f8-114"> uses the concept of a soft purge and a hard purge.</span></span> <span data-ttu-id="a43f8-115">論理削除は完了したインスタンスを削除する場合に使用し、物理削除は不完全なインスタンスを削除する場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="a43f8-115">The soft purge is used to purge completed instances, while the hard purge is only used to purge incomplete instances.</span></span>  
  
 <span data-ttu-id="a43f8-116">**論理削除**</span><span class="sxs-lookup"><span data-stu-id="a43f8-116">**Soft purge**</span></span>  
  
 <span data-ttu-id="a43f8-117">DTA Archive and Purge ジョブでは、LiveHours パラメーターと LiveDays パラメーターを加算した値が、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境で管理するデータの有効期間になります。</span><span class="sxs-lookup"><span data-stu-id="a43f8-117">In the DTA Archive and Purge job, the sum of the LiveHours and LiveDays parameters is the live window of data you want to maintain in your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="a43f8-118">この有効期間を経過している完了したインスタンスに関連付けられているデータはすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="a43f8-118">All data associated with a completed instance older than this live window of data is purged.</span></span> <span data-ttu-id="a43f8-119">既定では、DTA Archive and Purge ジョブは有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="a43f8-119">By default, the DTA Archive and Purge job is not enabled.</span></span> <span data-ttu-id="a43f8-120">まずはジョブを構成し、その後で有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a43f8-120">You must first configure and then enable the job.</span></span>  
  
 <span data-ttu-id="a43f8-121">たとえば、20 分ごとを実行する DTA Purge and Archive ジョブを構成し、設定できます有効 = 1、LiveDays = 0。</span><span class="sxs-lookup"><span data-stu-id="a43f8-121">For example, you can configure the DTA Purge and Archive job to run every 20 minutes, and set LiveHours=1 and LiveDays=0.</span></span> <span data-ttu-id="a43f8-122">初めてこの SQL Server エージェント ジョブの実行 (T0) では、アーカイブの作成によって追跡データベースのバックアップが行わされ、このタイムスタンプを持つデータベースでエントリが保存されます。</span><span class="sxs-lookup"><span data-stu-id="a43f8-122">The first time this SQL Server Agent job runs (T0), it takes a backup of the tracking database by creating an archive and an entry is saved in the database with this timestamp.</span></span> <span data-ttu-id="a43f8-123">追跡データを削除するためには正常なアーカイブが必要です。</span><span class="sxs-lookup"><span data-stu-id="a43f8-123">A successful archive is necessary in order to purge tracking data.</span></span> <span data-ttu-id="a43f8-124">アーカイブが正常に行われた場合は、完了後 1 時間を経過したインスタンスに関連付けられたすべてのデータが削除されます。</span><span class="sxs-lookup"><span data-stu-id="a43f8-124">If the archive was successful, then all the data associated with the instances that completed over an hour ago is purged.</span></span> <span data-ttu-id="a43f8-125">ジョブが実行されるたびに、1 時間を経過した完了済みのデータは削除されます。</span><span class="sxs-lookup"><span data-stu-id="a43f8-125">Each time the job runs, completed data over one hour old is purged.</span></span> <span data-ttu-id="a43f8-126">3 回目の実行 (1 時間後) では、過去 1 時間のセグメントで追跡データベースに挿入されたすべてのインスタンスのデータを含む新しいアーカイブが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a43f8-126">On the 3rd run (after one hour), a new archive is created that contains the data for all instances that were inserted into the tracking database in the last one hour segment.</span></span>  
  
 <span data-ttu-id="a43f8-127">次に、DTA Purge and Archive ジョブでアーカイブと削除のステップをどのように構成するかについて、上記の例を使用して説明します。</span><span class="sxs-lookup"><span data-stu-id="a43f8-127">Here is how you would configure the Archive and Purge step in the DTA Purge and Archive job to match the example above:</span></span>  
  
```  
exec dtasp_BackupAndPurgeTrackingDatabase  
1, --@nLiveHours 1,   
0, --@nLiveDays   
1, --@nHardDeleteDays   
‘\\server\backup’, --@nvcFolder   
null, --@nvcValidatingServer   
0 --@fForceBackup Soft purge process  
```  
  
 <span data-ttu-id="a43f8-128">前回のバックアップのタイムスタンプが BizTalk 追跡データベースに格納されています。このタイムスタンプの値により、前のアーカイブに含まれている場合のみ、データが削除されます。</span><span class="sxs-lookup"><span data-stu-id="a43f8-128">The time stamp of the last backup is stored in the BizTalk Tracking database and ensures that data is only purged if it is in the previous archive.</span></span> <span data-ttu-id="a43f8-129">さらに高い信頼性を確保する手段として、アーカイブを約 10 分ずつ重複させる措置がとられます。</span><span class="sxs-lookup"><span data-stu-id="a43f8-129">For additional reliability, archives are overlapped by approximately 10 minutes.</span></span> <span data-ttu-id="a43f8-130">上記の例に基づいた論理削除プロセスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="a43f8-130">The following figure, based on the example above, shows the soft purge process.</span></span> <span data-ttu-id="a43f8-131">アーカイブ タスクと削除タスクは必ずしも同時に発生するわけではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a43f8-131">Note that the archiving and purging tasks do not necessarily happen at the same time.</span></span>  
  
 <span data-ttu-id="a43f8-132">**論理削除プロセス**</span><span class="sxs-lookup"><span data-stu-id="a43f8-132">**Soft purge process**</span></span>  
  
 <span data-ttu-id="a43f8-133">![論理削除プロセス](../core/media/archivingandpurging.gif "archivingandpurging")</span><span class="sxs-lookup"><span data-stu-id="a43f8-133">![Soft purge process](../core/media/archivingandpurging.gif "archivingandpurging")</span></span>  
  
 <span data-ttu-id="a43f8-134">**物理削除**</span><span class="sxs-lookup"><span data-stu-id="a43f8-134">**Hard purge**</span></span>  
  
 <span data-ttu-id="a43f8-135">論理削除では完了したインスタンスと関連付けられたデータのみが削除されるため、無期限に実行される多数のループ インスタンスがある場合は、追跡データベースのサイズが増大するばかりか、これらのインスタンスは一切削除されません。</span><span class="sxs-lookup"><span data-stu-id="a43f8-135">Because the soft purge only purges data associated with completed instances, if you have many looping instances that run indefinitely, then your tracking database would grow and these instances would never be purged.</span></span> <span data-ttu-id="a43f8-136">物理削除の日付を使用すると、サービスの存在を示す情報を除き、指定された間隔よりも前のすべての情報を削除することが可能になります。</span><span class="sxs-lookup"><span data-stu-id="a43f8-136">The hard purge date allows all information older than the specified interval to be purged except for information indicating a service's existence.</span></span> <span data-ttu-id="a43f8-137">使用して、物理削除を設定する、  **@nHardDeleteDays**  Archive and Purge でパラメーターは、DTA Archive and Purge ジョブでステップ インします。</span><span class="sxs-lookup"><span data-stu-id="a43f8-137">You set the hard purge using the **@nHardDeleteDays** parameter in the Archive and Purge step in the DTA Archive and Purge job.</span></span> <span data-ttu-id="a43f8-138">物理削除の設定は、必ず論理削除の設定よりも大きい値にしてください。</span><span class="sxs-lookup"><span data-stu-id="a43f8-138">The hard purge setting should always be greater than your soft purge setting.</span></span> <span data-ttu-id="a43f8-139">つまり、  **@nHardDeleteDays** の合計より大きくなければなりません **@nLiveHours** と **@nLiveDays**です。</span><span class="sxs-lookup"><span data-stu-id="a43f8-139">In other words, **@nHardDeleteDays** should be greater than the sum of **@nLiveHours** and **@nLiveDays**.</span></span>  
  
 <span data-ttu-id="a43f8-140">アーカイブおよび削除には、次の表に示す機能があります。</span><span class="sxs-lookup"><span data-stu-id="a43f8-140">Archiving and purging includes the features described in the following table:</span></span>  
  
|<span data-ttu-id="a43f8-141">機能</span><span class="sxs-lookup"><span data-stu-id="a43f8-141">Feature</span></span>|<span data-ttu-id="a43f8-142">Description</span><span class="sxs-lookup"><span data-stu-id="a43f8-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a43f8-143">物理削除</span><span class="sxs-lookup"><span data-stu-id="a43f8-143">Hard purge</span></span>|<span data-ttu-id="a43f8-144">指定された日付よりも前の不完全なインスタンスの情報を削除するように、時間間隔を構成できます。</span><span class="sxs-lookup"><span data-stu-id="a43f8-144">Enables you to configure a time interval to purge information for incomplete instances older than a specified date.</span></span>|  
|<span data-ttu-id="a43f8-145">追跡メッセージの追跡データベースへのコピー</span><span class="sxs-lookup"><span data-stu-id="a43f8-145">Copying tracked messages to tracking database</span></span>|<span data-ttu-id="a43f8-146">CopyTrackedMessageToDTA オプションを使用すると、追跡メッセージをメッセージ ボックス サーバーから BizTalk 追跡データベースに直接コピーできます。</span><span class="sxs-lookup"><span data-stu-id="a43f8-146">Using the CopyTrackedMessageToDTA option, you can directly copy tracked messages from the MessageBox servers to your BizTalk Tracking database.</span></span> <span data-ttu-id="a43f8-147">これは、DTA Purge and Archive ジョブを使用してデータを削除するために必要です。</span><span class="sxs-lookup"><span data-stu-id="a43f8-147">This is required in order to purge data using the DTA Purge and Archive job.</span></span>|  
|<span data-ttu-id="a43f8-148">アーカイブ検証</span><span class="sxs-lookup"><span data-stu-id="a43f8-148">Archive validation</span></span>|<span data-ttu-id="a43f8-149">必要に応じて作成するときに、アーカイブを検証するセカンダリ データベースのサーバーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="a43f8-149">Enables you to optionally set up a secondary database server to validate the archives as they are created.</span></span>|  
|<span data-ttu-id="a43f8-150">BizTalk 追跡データベースの複数のバージョンに対する追跡サポート</span><span class="sxs-lookup"><span data-stu-id="a43f8-150">Tracking support for multiple BizTalk Tracking database versions</span></span>|<span data-ttu-id="a43f8-151">[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] および [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] データベース アーカイブで追跡サポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a43f8-151">Enables you to use tracking support with [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] and [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] database archives.</span></span>|  
|<span data-ttu-id="a43f8-152">追跡データの削減</span><span class="sxs-lookup"><span data-stu-id="a43f8-152">Reduction of tracking data</span></span>|<span data-ttu-id="a43f8-153">生成された追跡情報を減らさずに、格納された追跡データの量を大幅に削減します。</span><span class="sxs-lookup"><span data-stu-id="a43f8-153">Substantially reduces the amount of tracking data stored without reducing any tracking information generated.</span></span> <span data-ttu-id="a43f8-154">その結果、追跡データベースのサイズの増大速度が遅くなります。</span><span class="sxs-lookup"><span data-stu-id="a43f8-154">This results in slower growth of the tracking database.</span></span>|  
|<span data-ttu-id="a43f8-155">高速な追跡操作 (データベース スキーマの大幅な最適化)</span><span class="sxs-lookup"><span data-stu-id="a43f8-155">Faster tracking operations, significant optimization in database schemas</span></span>|<span data-ttu-id="a43f8-156">大規模データベースのメッセージやサービス インスタンスを検索するために追跡タスクを使用できます。この機能は大幅に最適化されています。</span><span class="sxs-lookup"><span data-stu-id="a43f8-156">Enables you to use tracking tasks for finding messages and service instances on large databases; this feature has been significantly optimized.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="a43f8-157">性能上の問題があり、BizTalk 追跡データベースを削除することで一時的に対処している場合、追跡情報を収集しないように BizTalk を構成するには、グローバル追跡を無効にすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="a43f8-157">If you are having performance issues that are momentarily addressed by purging the BizTalk tracking database, and you want to configure BizTalk to no longer collect tracking information, you may want to consider turning off global tracking.</span></span> <span data-ttu-id="a43f8-158">グローバル追跡をオフにする方法については、「グローバル追跡を無効にする方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a43f8-158">For information about turning off global tracking, see How to Turn Off Global Tracking.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a43f8-159">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a43f8-159">In This Section</span></span>  
  
-   [<span data-ttu-id="a43f8-160">チェックリスト: がアーカイブ化および BizTalk 追跡データベースを削除</span><span class="sxs-lookup"><span data-stu-id="a43f8-160">Checklist: Archiving and Purging the BizTalk Tracking Database</span></span>](../core/checklist-archiving-and-purging-the-biztalk-tracking-database.md)  
  
-   [<span data-ttu-id="a43f8-161">アーカイブおよび BizTalk 追跡データベースからデータを削除するために BTS_BACKUP_USERS ロールを構成する方法</span><span class="sxs-lookup"><span data-stu-id="a43f8-161">How to Configure the BTS_BACKUP_USERS Role for Archiving and Purging Data from the BizTalk Tracking Database</span></span>](../core/configure-bts_backup_users-role-to-archive-and-purge-from-tracking-database.md)  
  
-   [<span data-ttu-id="a43f8-162">DTA Purge and Archive ジョブを構成する方法</span><span class="sxs-lookup"><span data-stu-id="a43f8-162">How to Configure the DTA Purge and Archive Job</span></span>](../core/how-to-configure-the-dta-purge-and-archive-job.md)  
  
-   [<span data-ttu-id="a43f8-163">BizTalk 追跡データベースからデータを削除する方法</span><span class="sxs-lookup"><span data-stu-id="a43f8-163">How to Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)  
  
-   [<span data-ttu-id="a43f8-164">BizTalk 追跡データベースからデータを手動で削除する方法</span><span class="sxs-lookup"><span data-stu-id="a43f8-164">How to Manually Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)  
  
-   [<span data-ttu-id="a43f8-165">アーカイブの自動検証を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="a43f8-165">How to Enable Automatic Archive Validation</span></span>](../core/how-to-enable-automatic-archive-validation.md)  
  
-   [<span data-ttu-id="a43f8-166">BizTalk 追跡データベースに追跡されるメッセージをコピーする方法</span><span class="sxs-lookup"><span data-stu-id="a43f8-166">How to Copy Tracked Messages into the BizTalk Tracking Database</span></span>](../core/how-to-copy-tracked-messages-into-the-biztalk-tracking-database.md)  
  
-   [<span data-ttu-id="a43f8-167">アーカイブおよび削除のプロセスのパフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="a43f8-167">Improving the Performance of the Archiving and Purging Process</span></span>](../core/improving-the-performance-of-the-archiving-and-purging-process.md)  
  
-   [<span data-ttu-id="a43f8-168">グローバル追跡を無効にする方法</span><span class="sxs-lookup"><span data-stu-id="a43f8-168">How to Turn Off Global Tracking</span></span>](../core/how-to-turn-off-global-tracking.md)