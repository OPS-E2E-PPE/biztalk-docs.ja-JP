---
title: アーカイブし、追跡データベースの削除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7014cf31-86e8-4829-8055-056442329009
caps.latest.revision: 37
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99d1d1e65ff943c2a677abc5e71fea4248955f73
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358969"
---
# <a name="archive-and-purge-the-biztalkdtadb-database"></a><span data-ttu-id="79c45-102">アーカイブおよび BizTalkDTADb データベースの消去</span><span class="sxs-lookup"><span data-stu-id="79c45-102">Archive and Purge the BizTalkDTADb Database</span></span>

## <a name="overview"></a><span data-ttu-id="79c45-103">概要</span><span class="sxs-lookup"><span data-stu-id="79c45-103">Overview</span></span>
<span data-ttu-id="79c45-104">BizTalk Server では、システムの詳細と詳細データを処理すると、BizTalk 追跡 (BizTalkDTADb) データベースはサイズで増え続けています。</span><span class="sxs-lookup"><span data-stu-id="79c45-104">As BizTalk Server processes more and more data on your system, the BizTalk Tracking (BizTalkDTADb) database continues to grow in size.</span></span> <span data-ttu-id="79c45-105">未チェックの増加は、システム パフォーマンスが低下し、エラーで、Tracking Data Decode Service (TDDS) を生成可能性があります。</span><span class="sxs-lookup"><span data-stu-id="79c45-105">Unchecked growth decreases system performance and may generate errors in the Tracking Data Decode Service (TDDS).</span></span> <span data-ttu-id="79c45-106">一般的な追跡データ、他にもディスク パフォーマンスの低下の原因と、メッセージ ボックス データベースに追跡メッセージも蓄積します。</span><span class="sxs-lookup"><span data-stu-id="79c45-106">In addition to general tracking data, tracked messages can also accumulate in the MessageBox database, causing poor disk performance.</span></span>  
  
<span data-ttu-id="79c45-107">BizTalk Server では、DTA Purge and Archive ジョブを使用して両方のプロセスを自動化します。</span><span class="sxs-lookup"><span data-stu-id="79c45-107">BizTalk Server automates both processes using the DTA Purge and Archive job.</span></span> <span data-ttu-id="79c45-108">アーカイブし、BizTalk 追跡データベースからデータを削除、することができます、健全なシステムの管理だけでなく将来使用するためにアーカイブされた追跡データを維持します。</span><span class="sxs-lookup"><span data-stu-id="79c45-108">By archiving and purging data from the BizTalk Tracking database, you can maintain a healthy system, as well as keep your tracking data archived for future use.</span></span> <span data-ttu-id="79c45-109">BizTalk 追跡データベースのアーカイブは時間の経過と共に蓄積されるディスク領域を消費するためは、BizTalk 追跡データベースのアーカイブを定期的にセカンダリ ストレージに移動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="79c45-109">Because BizTalk Tracking database archives accumulate over time and consume disk space, it is a good idea to move the BizTalk Tracking database archives to secondary storage on a regular basis.</span></span>  
  
 <span data-ttu-id="79c45-110">BizTalk 追跡データベースからデータを削除すると、DTA Purge and Archive ジョブは、さまざまな種類のメッセージなどの情報とサービス インスタンス情報、オーケストレーション イベントの情報、およびルール エンジン追跡データの追跡を削除します。</span><span class="sxs-lookup"><span data-stu-id="79c45-110">When you purge data from the BizTalk Tracking database, the DTA Purge and Archive job purges different types of tracking information such as message and service instance information, orchestration event information, and rules engine tracking data.</span></span>  
  
 <span data-ttu-id="79c45-111">データ レコードは、時間に基づいて追跡の有効期間、追跡データは、BizTalk 追跡データベースに挿入されました。</span><span class="sxs-lookup"><span data-stu-id="79c45-111">The age of a tracking data record is based on the time the tracking data was inserted into the BizTalk Tracking database.</span></span> <span data-ttu-id="79c45-112">DTA Purge and Archive ジョブでは、タイムスタンプを使用して、継続的に、レコードがデータの有効期間よりも古いかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="79c45-112">The DTA Purge and Archive job uses the time stamp to continuously verify whether the record is older than the live window of data.</span></span> <span data-ttu-id="79c45-113">すべて有効期間の後に、BizTalk 追跡データベースがアーカイブされ、新しいアーカイブ ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="79c45-113">After every live window period, the BizTalk Tracking database is archived and a new archive file is created.</span></span> <span data-ttu-id="79c45-114">ジョブのスケジュールで指定された各 SQL Server エージェント ジョブ間隔では、すべてが完了した古いデータを追跡よりも、有効期間は消去されます。</span><span class="sxs-lookup"><span data-stu-id="79c45-114">At each SQL Server Agent job interval specified by the job schedule, all completed tracking data older than the live window period is purged.</span></span>  
  
 <span data-ttu-id="79c45-115">BizTalk Server では、論理的な削除と物理削除の概念を使用します。</span><span class="sxs-lookup"><span data-stu-id="79c45-115">BizTalk Server uses the concept of a soft purge and a hard purge.</span></span> <span data-ttu-id="79c45-116">論理削除を使用して、物理削除が不完全なインスタンスを削除する使用のみに完了したインスタンスを消去します。</span><span class="sxs-lookup"><span data-stu-id="79c45-116">The soft purge is used to purge completed instances, while the hard purge is only used to purge incomplete instances.</span></span>  
  
## <a name="soft-purge"></a><span data-ttu-id="79c45-117">論理削除</span><span class="sxs-lookup"><span data-stu-id="79c45-117">Soft purge</span></span>
  
 <span data-ttu-id="79c45-118">DTA Archive and Purge ジョブでは、加算と LiveDays パラメーターの合計は、BizTalk Server 環境で管理するデータの有効期間。</span><span class="sxs-lookup"><span data-stu-id="79c45-118">In the DTA Archive and Purge job, the sum of the LiveHours and LiveDays parameters is the live window of data you want to maintain in your BizTalk Server environment.</span></span> <span data-ttu-id="79c45-119">データのこの有効期間よりも古い完了したインスタンスに関連付けられているすべてのデータは消去されます。</span><span class="sxs-lookup"><span data-stu-id="79c45-119">All data associated with a completed instance older than this live window of data is purged.</span></span> <span data-ttu-id="79c45-120">既定では、DTA Archive and Purge ジョブは有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="79c45-120">By default, the DTA Archive and Purge job is not enabled.</span></span> <span data-ttu-id="79c45-121">最初に構成して、ジョブを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="79c45-121">You must first configure and then enable the job.</span></span>  
  
 <span data-ttu-id="79c45-122">たとえば、20 分ごとに実行する DTA Purge and Archive ジョブを構成し、設定した = 1、LiveDays = 0。</span><span class="sxs-lookup"><span data-stu-id="79c45-122">For example, you can configure the DTA Purge and Archive job to run every 20 minutes, and set LiveHours=1 and LiveDays=0.</span></span> <span data-ttu-id="79c45-123">初めてこの SQL Server エージェント ジョブの実行 (T0) では、アーカイブの作成によって追跡データベースのバックアップが行わし、エントリは、このタイムスタンプを持つデータベースに保存されます。</span><span class="sxs-lookup"><span data-stu-id="79c45-123">The first time this SQL Server Agent job runs (T0), it takes a backup of the tracking database by creating an archive and an entry is saved in the database with this timestamp.</span></span> <span data-ttu-id="79c45-124">正常なアーカイブは、追跡データを削除するために必要があります。</span><span class="sxs-lookup"><span data-stu-id="79c45-124">A successful archive is necessary in order to purge tracking data.</span></span> <span data-ttu-id="79c45-125">アーカイブが成功した場合、1 時間前に完了したインスタンスに関連付けられているすべてのデータが消去されます。</span><span class="sxs-lookup"><span data-stu-id="79c45-125">If the archive was successful, then all the data associated with the instances that completed over an hour ago is purged.</span></span> <span data-ttu-id="79c45-126">ジョブが実行されるたびに、1 時間前に完了したデータが削除されます。</span><span class="sxs-lookup"><span data-stu-id="79c45-126">Each time the job runs, completed data over one hour old is purged.</span></span> <span data-ttu-id="79c45-127">(1 時間) の後に 3 番目の実行時に、1 時間の最後のセグメントで追跡データベースに挿入されたすべてのインスタンスのデータを含む新しいアーカイブが作成されます。</span><span class="sxs-lookup"><span data-stu-id="79c45-127">On the 3rd run (after one hour), a new archive is created that contains the data for all instances that were inserted into the tracking database in the last one hour segment.</span></span>  
  
 <span data-ttu-id="79c45-128">アーカイブを構成する方法と、削除の例では、一致するように、DTA Purge and Archive ジョブのステップを次に示します。</span><span class="sxs-lookup"><span data-stu-id="79c45-128">Here is how you would configure the Archive and Purge step in the DTA Purge and Archive job to match the example:</span></span>  
  
```  
exec dtasp_BackupAndPurgeTrackingDatabase  
1, --@nLiveHours 1,   
0, --@nLiveDays   
1, --@nHardDeleteDays   
‘\\server\backup’, --@nvcFolder   
null, --@nvcValidatingServer   
0 --@fForceBackup Soft purge process  
```  
  
 <span data-ttu-id="79c45-129">最後のバックアップのタイムスタンプは、BizTalk 追跡データベースに格納され、により、前のアーカイブに存在する場合に、データが消去のみです。</span><span class="sxs-lookup"><span data-stu-id="79c45-129">The time stamp of the last backup is stored in the BizTalk Tracking database and ensures that data is only purged if it is in the previous archive.</span></span> <span data-ttu-id="79c45-130">その他の信頼性のアーカイブは、約 10 分が重なっています。</span><span class="sxs-lookup"><span data-stu-id="79c45-130">For additional reliability, archives are overlapped by approximately 10 minutes.</span></span> <span data-ttu-id="79c45-131">上記の例に基づいて、次の図は、論理削除プロセスを示します。</span><span class="sxs-lookup"><span data-stu-id="79c45-131">The following figure, based on the example above, shows the soft purge process.</span></span> <span data-ttu-id="79c45-132">アーカイブと削除タスクとは限りません実行されないと同時に注意してください。</span><span class="sxs-lookup"><span data-stu-id="79c45-132">Note that the archiving and purging tasks do not necessarily happen at the same time.</span></span>  
  
 <span data-ttu-id="79c45-133">**論理削除プロセス**</span><span class="sxs-lookup"><span data-stu-id="79c45-133">**Soft purge process**</span></span>  
  
 <span data-ttu-id="79c45-134">![論理削除プロセス](../core/media/archivingandpurging.gif "archivingandpurging")</span><span class="sxs-lookup"><span data-stu-id="79c45-134">![Soft purge process](../core/media/archivingandpurging.gif "archivingandpurging")</span></span>  
  
## <a name="hard-purge"></a><span data-ttu-id="79c45-135">物理削除</span><span class="sxs-lookup"><span data-stu-id="79c45-135">Hard purge</span></span>
  
 <span data-ttu-id="79c45-136">ソフト削除のためのみ、追跡データベースのサイズが増大してこれらのインスタンスは一切削除されません、無限に実行される多数のループ インスタンスがある場合は、完了したインスタンスに関連付けられているデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="79c45-136">Because the soft purge only purges data associated with completed instances, if you have many looping instances that run indefinitely, then your tracking database would grow and these instances would never be purged.</span></span> <span data-ttu-id="79c45-137">物理削除の日付では、消去、サービスの存在を示す情報を除き、指定された間隔よりも古いすべての情報を許可します。</span><span class="sxs-lookup"><span data-stu-id="79c45-137">The hard purge date allows all information older than the specified interval to be purged except for information indicating a service's existence.</span></span> <span data-ttu-id="79c45-138">使用して、物理削除を設定する、 <strong>@nHardDeleteDays</strong> Archive and Purge でパラメーターは、DTA Archive and Purge ジョブでステップ インします。</span><span class="sxs-lookup"><span data-stu-id="79c45-138">You set the hard purge using the <strong>@nHardDeleteDays</strong> parameter in the Archive and Purge step in the DTA Archive and Purge job.</span></span> <span data-ttu-id="79c45-139">物理削除の設定は、論理削除の設定よりも大きいは常にします。</span><span class="sxs-lookup"><span data-stu-id="79c45-139">The hard purge setting should always be greater than your soft purge setting.</span></span> <span data-ttu-id="79c45-140">つまり、 <strong>@nHardDeleteDays</strong>の合計より大きくなければなりません<strong>@nLiveHours</strong>と <strong>@nLiveDays</strong>します。</span><span class="sxs-lookup"><span data-stu-id="79c45-140">In other words, <strong>@nHardDeleteDays</strong> should be greater than the sum of <strong>@nLiveHours</strong> and <strong>@nLiveDays</strong>.</span></span>  
  
 <span data-ttu-id="79c45-141">アーカイブと削除には、次の表で説明する機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="79c45-141">Archiving and purging includes the features described in the following table:</span></span>  
  
|<span data-ttu-id="79c45-142">機能</span><span class="sxs-lookup"><span data-stu-id="79c45-142">Feature</span></span>|<span data-ttu-id="79c45-143">説明</span><span class="sxs-lookup"><span data-stu-id="79c45-143">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="79c45-144">物理削除</span><span class="sxs-lookup"><span data-stu-id="79c45-144">Hard purge</span></span>|<span data-ttu-id="79c45-145">指定した日付よりも古い不完全なインスタンスの情報を削除する時間間隔を構成できます。</span><span class="sxs-lookup"><span data-stu-id="79c45-145">Enables you to configure a time interval to purge information for incomplete instances older than a specified date.</span></span>|  
|<span data-ttu-id="79c45-146">追跡データベースに追跡されたメッセージのコピー</span><span class="sxs-lookup"><span data-stu-id="79c45-146">Copying tracked messages to tracking database</span></span>|<span data-ttu-id="79c45-147">CopyTrackedMessageToDTA オプションを使用して直接コピーできます追跡メッセージ、メッセージ ボックス サーバーから BizTalk 追跡データベースにします。</span><span class="sxs-lookup"><span data-stu-id="79c45-147">Using the CopyTrackedMessageToDTA option, you can directly copy tracked messages from the MessageBox servers to your BizTalk Tracking database.</span></span> <span data-ttu-id="79c45-148">これは、DTA Purge and Archive ジョブを使用してデータを削除するために必要です。</span><span class="sxs-lookup"><span data-stu-id="79c45-148">This is required in order to purge data using the DTA Purge and Archive job.</span></span>|  
|<span data-ttu-id="79c45-149">アーカイブの検証</span><span class="sxs-lookup"><span data-stu-id="79c45-149">Archive validation</span></span>|<span data-ttu-id="79c45-150">必要に応じてサーバーを設定するセカンダリ データベースが作成されるときに、アーカイブを検証することができます。</span><span class="sxs-lookup"><span data-stu-id="79c45-150">Enables you to optionally set up a secondary database server to validate the archives as they are created.</span></span>|  
|<span data-ttu-id="79c45-151">複数の BizTalk 追跡データベースのバージョンに対する追跡サポート</span><span class="sxs-lookup"><span data-stu-id="79c45-151">Tracking support for multiple BizTalk Tracking database versions</span></span>|<span data-ttu-id="79c45-152">BizTalk Server で追跡を使用することをサポートできるようにデータベース アーカイブです。</span><span class="sxs-lookup"><span data-stu-id="79c45-152">Enables you to use tracking support with BizTalk Server database archives.</span></span>|  
|<span data-ttu-id="79c45-153">追跡データの削減</span><span class="sxs-lookup"><span data-stu-id="79c45-153">Reduction of tracking data</span></span>|<span data-ttu-id="79c45-154">生成された追跡情報を減らさずに格納された追跡データの量を大幅に削減します。</span><span class="sxs-lookup"><span data-stu-id="79c45-154">Substantially reduces the amount of tracking data stored without reducing any tracking information generated.</span></span> <span data-ttu-id="79c45-155">これにより、追跡データベースの増加が遅くなります。</span><span class="sxs-lookup"><span data-stu-id="79c45-155">This results in slower growth of the tracking database.</span></span>|  
|<span data-ttu-id="79c45-156">高速な操作、データベース スキーマの大幅な最適化を追跡</span><span class="sxs-lookup"><span data-stu-id="79c45-156">Faster tracking operations, significant optimization in database schemas</span></span>|<span data-ttu-id="79c45-157">大規模なデータベースは; でメッセージとサービス インスタンスを検索するための追跡のタスクを使用することができます。この機能が大幅に最適化されています。</span><span class="sxs-lookup"><span data-stu-id="79c45-157">Enables you to use tracking tasks for finding messages and service instances on large databases; this feature has been significantly optimized.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="79c45-158">一時的に、BizTalk 追跡データベースを削除することで対処はパフォーマンスの問題が発生した、不要になった追跡情報を収集する BizTalk を構成する場合は、グローバル追跡を無効にすることを検討する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="79c45-158">If you are having performance issues that are momentarily addressed by purging the BizTalk tracking database, and you want to configure BizTalk to no longer collect tracking information, you may want to consider turning off global tracking.</span></span> <span data-ttu-id="79c45-159">参照してください[グローバル追跡をオフに](../core/how-to-turn-off-global-tracking.md)します。</span><span class="sxs-lookup"><span data-stu-id="79c45-159">See [Turn Off Global Tracking](../core/how-to-turn-off-global-tracking.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="79c45-160">次のステップ</span><span class="sxs-lookup"><span data-stu-id="79c45-160">Next steps</span></span>
  
-   [<span data-ttu-id="79c45-161">チェックリスト:アーカイブおよび BizTalk 追跡データベースの削除</span><span class="sxs-lookup"><span data-stu-id="79c45-161">Checklist: Archiving and Purging the BizTalk Tracking Database</span></span>](../core/checklist-archiving-and-purging-the-biztalk-tracking-database.md)  
  
-   [<span data-ttu-id="79c45-162">BizTalk 追跡データベースのデータをアーカイブおよび削除するために BTS_BACKUP_USERS ロールを構成する</span><span class="sxs-lookup"><span data-stu-id="79c45-162">Configure the BTS_BACKUP_USERS Role for Archiving and Purging Data from the BizTalk Tracking Database</span></span>](../core/configure-bts_backup_users-role-to-archive-and-purge-from-tracking-database.md)  
  
-   [<span data-ttu-id="79c45-163">DTA Purge and Archive ジョブの構成</span><span class="sxs-lookup"><span data-stu-id="79c45-163">Configure the DTA Purge and Archive Job</span></span>](../core/how-to-configure-the-dta-purge-and-archive-job.md)  
  
-   [<span data-ttu-id="79c45-164">BizTalk 追跡データベースからデータを削除する</span><span class="sxs-lookup"><span data-stu-id="79c45-164">Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)  
  
-   [<span data-ttu-id="79c45-165">BizTalk 追跡データベースからデータを手動で削除する</span><span class="sxs-lookup"><span data-stu-id="79c45-165">Manually Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)  
  
-   [<span data-ttu-id="79c45-166">アーカイブの自動検証の有効化</span><span class="sxs-lookup"><span data-stu-id="79c45-166">Enable Automatic Archive Validation</span></span>](../core/how-to-enable-automatic-archive-validation.md)  
  
-   [<span data-ttu-id="79c45-167">追跡メッセージを BizTalk 追跡データベースにコピーする</span><span class="sxs-lookup"><span data-stu-id="79c45-167">Copy Tracked Messages into the BizTalk Tracking Database</span></span>](../core/how-to-copy-tracked-messages-into-the-biztalk-tracking-database.md)  
  
-   [<span data-ttu-id="79c45-168">アーカイブおよび削除のプロセスのパフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="79c45-168">Improving the Performance of the Archiving and Purging Process</span></span>](../core/improving-the-performance-of-the-archiving-and-purging-process.md)  
  
-   [<span data-ttu-id="79c45-169">グローバル追跡の無効化</span><span class="sxs-lookup"><span data-stu-id="79c45-169">Turn Off Global Tracking</span></span>](../core/how-to-turn-off-global-tracking.md)