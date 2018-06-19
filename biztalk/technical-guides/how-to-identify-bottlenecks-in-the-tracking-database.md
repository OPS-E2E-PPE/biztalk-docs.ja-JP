---
title: 追跡データベースのボトルネックを特定する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b72e726-6225-47a0-8e1d-0f5a9cf745d3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16cd05b6c399d250d8a411f41f56406f19afc9e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297986"
---
# <a name="how-to-identify-bottlenecks-in-the-tracking-database"></a><span data-ttu-id="a1dfd-102">追跡データベースのボトルネックを特定する方法</span><span class="sxs-lookup"><span data-stu-id="a1dfd-102">How to Identify Bottlenecks in the Tracking Database</span></span>
<span data-ttu-id="a1dfd-103">BizTalk 追跡 (BizTalkDTADb) データベースのボトルネックを特定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1dfd-103">To identify bottlenecks in the BizTalk Tracking (BizTalkDTADb) database, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="a1dfd-104">SQL エージェント サービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a1dfd-104">Ensure that the SQL-Agent Service is running.</span></span>  
  
2.  <span data-ttu-id="a1dfd-105">Archive/Purge ジョブが実行され、正常に完了することを確認します。</span><span class="sxs-lookup"><span data-stu-id="a1dfd-105">Ensure that the Archive/Purge Job is running and completing successfully.</span></span>  
  
3.  <span data-ttu-id="a1dfd-106">TrackedMessages_Copy_BizTalkMsgBoxDB ジョブが実行されていて、正常に完了しないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a1dfd-106">Ensure that the TrackedMessages_Copy_BizTalkMsgBoxDB Job is running and completing successfully.</span></span>  
  
4.  <span data-ttu-id="a1dfd-107">DTADb アーカイブとデータベース サイズの増加に対応できるだけの十分な空きディスク領域があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a1dfd-107">Verify that sufficient free disk space is available for the DTADb archives and database growth.</span></span>  
  
5.  <span data-ttu-id="a1dfd-108">専用のホストの追跡を使用し、負荷の下にあるときにホスト Queue Length パフォーマンス カウンターを測定します。</span><span class="sxs-lookup"><span data-stu-id="a1dfd-108">Use a dedicated host for tracking and measure the Host Queue Length performance counter when under load.</span></span>  
  
6.  <span data-ttu-id="a1dfd-109">時間の経過と共に上昇傾向のスプール テーブル サイズのパフォーマンス カウンターを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a1dfd-109">Check the Spool Table size performance counter for an increasing trend over time.</span></span>  
  
7.  <span data-ttu-id="a1dfd-110">Archive/purge ジョブの実行時間の長い実行時間を確認してください。</span><span class="sxs-lookup"><span data-stu-id="a1dfd-110">Check the Archive/Purge job execution duration for long execution times.</span></span>  
  
8.  <span data-ttu-id="a1dfd-111">BizTalk 追跡データベースをホストしているディスク上のディスク (ディスク (秒) パフォーマンス カウンターの読み取り/書き込みごと) の応答性を確認します。</span><span class="sxs-lookup"><span data-stu-id="a1dfd-111">Check disk responsiveness (Disk Seconds per Read/Write performance counter) on the disk hosting the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="a1dfd-112">Dtasp_BackupAndPurgeTrackingDatabase または dtasp_PurgeTrackingDatabase DTA Purge and Archive ジョブによって呼び出されるは、次のパラメーターの値をチューニングを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a1dfd-112">We strongly recommend tuning down the value of the following parameters of the dtasp_BackupAndPurgeTrackingDatabase or dtasp_PurgeTrackingDatabase invoked by the DTA Purge and Archive job:</span></span>  
  
-   <span data-ttu-id="a1dfd-113">@nLiveHourstinyint — (live hours) よりも古いインスタンスに完了した + (live 日) は、関連付けられているすべてのデータと共に削除されます。</span><span class="sxs-lookup"><span data-stu-id="a1dfd-113">@nLiveHours tinyint — Any completed instance older than the (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="a1dfd-114">既定では 0 時間です。</span><span class="sxs-lookup"><span data-stu-id="a1dfd-114">Default is 0 hours.</span></span>  
  
-   <span data-ttu-id="a1dfd-115">@nLiveDaystinyint — (live hours) よりも古いインスタンスに完了した + (live 日) は、関連付けられているすべてのデータと共に削除されます。</span><span class="sxs-lookup"><span data-stu-id="a1dfd-115">@nLiveDays tinyint — Any completed instance older than the (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="a1dfd-116">既定の間隔は 1 日です。</span><span class="sxs-lookup"><span data-stu-id="a1dfd-116">Default interval is 1 day.</span></span>  
  
-   <span data-ttu-id="a1dfd-117">@nHardDeleteDaystinyint — すべてのデータ (不完全な場合でも) これは、削除するよりも古いします。</span><span class="sxs-lookup"><span data-stu-id="a1dfd-117">@nHardDeleteDays tinyint — All data (even if incomplete) older than this will be deleted.</span></span> <span data-ttu-id="a1dfd-118">HardDeleteDays に指定する間隔は、データの有効期間よりも大きい値にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1dfd-118">The time interval specified for HardDeleteDays should be greater than the live window of data.</span></span> <span data-ttu-id="a1dfd-119">データの有効期間は、BizTalk 追跡データベース (BizTalkDTADb) でデータを追跡する間隔になります。</span><span class="sxs-lookup"><span data-stu-id="a1dfd-119">The live window of data is the interval of time for which you want to maintain tracking data in the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="a1dfd-120">この間隔より古いデータは、次のアーカイブ時にアーカイブしてから削除できます。</span><span class="sxs-lookup"><span data-stu-id="a1dfd-120">Anything older than this interval is eligible to be archived at the next archive and then purged.</span></span> <span data-ttu-id="a1dfd-121">既定値は、30 日間です。</span><span class="sxs-lookup"><span data-stu-id="a1dfd-121">Default is 30 days.</span></span>  
  
 <span data-ttu-id="a1dfd-122">これらのパラメーターは、ことをお勧めパフォーマンス ラボ テストで値を使用する次のように対し、実稼働環境でのデータ保持ポリシーに従って設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1dfd-122">These parameters should be set in accordance with data retention policies in a production environment, whereas in a performance lab tests we recommend that you use values as follows:</span></span>  
  
 <span data-ttu-id="a1dfd-123">宣言@dtLastBackupdatetime セット@dtLastBackupGetUTCDate() を =</span><span class="sxs-lookup"><span data-stu-id="a1dfd-123">declare @dtLastBackup datetime set @dtLastBackup = GetUTCDate()</span></span>  
 <span data-ttu-id="a1dfd-124">exec dtasp_PurgeTrackingDatabase 1, 0, 1,@dtLastBackup</span><span class="sxs-lookup"><span data-stu-id="a1dfd-124">exec dtasp_PurgeTrackingDatabase 1, 0, 1, @dtLastBackup</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1dfd-125">参照</span><span class="sxs-lookup"><span data-stu-id="a1dfd-125">See Also</span></span>  
 [<span data-ttu-id="a1dfd-126">データベース層のボトルネック</span><span class="sxs-lookup"><span data-stu-id="a1dfd-126">Bottlenecks in the Database Tier</span></span>](../technical-guides/bottlenecks-in-the-database-tier.md)