---
title: メッセージ ボックスの待機時間に関する問題のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9eb5789-80bd-40d4-8c27-7ae117fd9232
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d62bbe76a618b03c4cd57d764152e250ecbc3ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295705"
---
# <a name="troubleshooting-messagebox-latency-issues"></a><span data-ttu-id="8db38-102">メッセージ ボックスの遅延に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="8db38-102">Troubleshooting MessageBox Latency Issues</span></span>
<span data-ttu-id="8db38-103">理想の世界には、すべてのメッセージを処理およびメッセージ ボックス データベースに公開されたときと、メッセージ ボックス データベースは、過剰なサイズには拡張しないと、すぐに配信して。</span><span class="sxs-lookup"><span data-stu-id="8db38-103">In a perfect world, all messages would be processed and delivered as soon as they were published to the MessageBox database and the MessageBox database would never grow to an excessive size.</span></span> <span data-ttu-id="8db38-104">メッセージ ボックス データベースのテーブルを定期的にクリーンアップする SQL エージェント ジョブによって参照されなくなったすべてのメッセージ、メッセージ ボックス データベースにすぐに削除されます。</span><span class="sxs-lookup"><span data-stu-id="8db38-104">Any messages in the MessageBox that were no longer referenced would immediately be removed by the SQL agent jobs that periodically clean up the MessageBox database tables.</span></span>  
  
 <span data-ttu-id="8db38-105">ただし、実際のシナリオ メッセージは通常、予測可能な線形的に受信されないと、SQL エージェント ジョブがメッセージ ボックス データベースのテーブルをクリーンアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8db38-105">In real world scenarios, however, messages are not typically received in a predictable, linear fashion and the SQL agent jobs require time to clean up the MessageBox database tables.</span></span>  
  
 <span data-ttu-id="8db38-106">そのため、一部のシナリオで非常に短時間で、メッセージ ボックス データベースが非常に大きなに拡張できます。</span><span class="sxs-lookup"><span data-stu-id="8db38-106">Therefore, in some scenarios; the MessageBox can grow fairly large very quickly.</span></span>  
  
 <span data-ttu-id="8db38-107">次の項目には、メッセージ ボックスに、過度に大規模で妨げの全体的なパフォーマンスの拡張が発生します。</span><span class="sxs-lookup"><span data-stu-id="8db38-107">The following items can cause the MessageBox to grow excessively large and hinder overall performance:</span></span>  
  
-   <span data-ttu-id="8db38-108">**「ホストの追跡を許可する」オプションが設定されている Biztalk ホスト インスタンスが停止している**します。</span><span class="sxs-lookup"><span data-stu-id="8db38-108">**The Biztalk Host instance that has the "allow Host tracking" option set is stopped**.</span></span> <span data-ttu-id="8db38-109">これは、Biztalk 追跡 database(BizTalkDTADb) をメッセージ ボックス データベースから追跡データの移動を担当するホストです。</span><span class="sxs-lookup"><span data-stu-id="8db38-109">This is the host that is responsible for moving the tracking data from the MessageBox database to the Biztalk Tracking database(BizTalkDTADb).</span></span>  
  
-   <span data-ttu-id="8db38-110">**SQL Server エージェントが実行されていない**これは、[その後、メッセージ ボックスに移動したデータを消去する]、BizTalkDTADb データベースにメッセージ ボックス データベースからデータを移動を行う SQL ジョブが実行されていない場合に発生することができます。</span><span class="sxs-lookup"><span data-stu-id="8db38-110">**SQL Server Agent is not running** This can happen if the SQL jobs responsible for moving data from the MessageBox database to the BizTalkDTADb database [subsequently purging the moved data in the MessageBox] are not running.</span></span> <span data-ttu-id="8db38-111">SQL エージェント サービスは、この問題を回避するために、すべての時間を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8db38-111">It is imperative the SQL Agent Service be running all the time to avoid this problem.</span></span>  
  
-   <span data-ttu-id="8db38-112">**SQL Server ジョブが無効になっている**命令型の既定の SQL Server ジョブのいずれも無効にすることは、SQL Server エージェントが実行されている場合でもです。</span><span class="sxs-lookup"><span data-stu-id="8db38-112">**SQL Server Jobs are disabled** Even if the SQL Server Agent is running, it is imperative that none of the default SQL Server jobs be disabled.</span></span>  
  
-   <span data-ttu-id="8db38-113">**BizTalkDTADb データベースのサイズが過剰**これは、BizTalkDTADb データベースが非常に大きなに長い時間がかかる BizTalkDTADb データベースに挿入の原因が増加した場合に発生することができます。</span><span class="sxs-lookup"><span data-stu-id="8db38-113">**BizTalkDTADb database grows excessively** This can happen if the BizTalkDTADb database grows very large, causing inserts into the BizTalkDTADb database to take longer.</span></span> <span data-ttu-id="8db38-114">このような場合、データの移動 Tracking Data Delivery Service (TDDS) が低下し、メッセージ ボックス データベースで、バックログが蓄積の原因します。</span><span class="sxs-lookup"><span data-stu-id="8db38-114">When this happens the movement of data by Tracking Data Delivery Service (TDDS) slows down, causing a backlog build up in the MessageBox database.</span></span> <span data-ttu-id="8db38-115">この問題を回避するには、SQL server のアーカイブを実行し、ジョブ、BizTalkDTADb データベースを定期的に削除の操作に必要があります。</span><span class="sxs-lookup"><span data-stu-id="8db38-115">To avoid this problem it is important to run the SQL server archive and purge jobs periodically on the BizTalkDTADb databases.</span></span>  
  
-   <span data-ttu-id="8db38-116">**過剰なディスク I/O の待機時間**かどうか、メッセージ ボックス データベースにデータの着信レートが、システムが処理できるよりも高速と BizTalkDTADb データベースにデータを移動バックログが蓄積されるメッセージ ボックス データベースにします。</span><span class="sxs-lookup"><span data-stu-id="8db38-116">**Excessive Disk I/O Latency** If the incoming rate of data into the MessageBox database is faster than which the system can process and move the data to the BizTalkDTADb database, backlog can build up in the MessageBox database.</span></span> <span data-ttu-id="8db38-117">バックログがに伴って増加し続ける場合は、これは非常に深刻な問題と時間の経過と共にシステム パフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="8db38-117">If the backlog continues to grow unabated, this is a very serious problem and system performance will degrade over time.</span></span> <span data-ttu-id="8db38-118">この問題を軽減する方法の 1 つは、高速なディスクをインストールまたはアップグレード、ハードウェア、システムが時間の経過と共に発生するメッセージ バックログから回復できるようにするには。</span><span class="sxs-lookup"><span data-stu-id="8db38-118">One way to alleviate this problem is to install faster disks and/or upgrade the hardware to help ensure that the system is capable of recovering from any message backlogs experienced over time.</span></span>  
  
## <a name="plan-for-the-future"></a><span data-ttu-id="8db38-119">将来を計画します。</span><span class="sxs-lookup"><span data-stu-id="8db38-119">Plan for the Future</span></span>  
 <span data-ttu-id="8db38-120">上記ベスト プラクティスに従っている場合でも追跡データの量が BizTalkDTADb に移動する時間の経過と共にデータベースは非常に大ききます。</span><span class="sxs-lookup"><span data-stu-id="8db38-120">Even though all the best practices above are followed, over time the volume of tracking data moved to the BizTalkDTADb database will grow very large.</span></span> <span data-ttu-id="8db38-121">システムを最適に実行を続行するために、追跡データを定期的にアーカイブするデータベース メンテナンス プランを実装するために重要です。</span><span class="sxs-lookup"><span data-stu-id="8db38-121">It is important to implement a database maintenance plan to periodically archive tracking data so that the system can continue to perform optimally.</span></span>  
  
 <span data-ttu-id="8db38-122">BizTalkDTADb データベースに保持できる履歴データの量は、システムにプッシュされたメッセージの量によって異なります。</span><span class="sxs-lookup"><span data-stu-id="8db38-122">The amount of historical data that can be retained in the BizTalkDTADb database depends on the volume of messages pushed through the system.</span></span> <span data-ttu-id="8db38-123">システムを対象にしない高負荷やスループットがこのデータベースの増加率が低速と BizTalkDTADb データベースでの複数の履歴データを保持することができます。</span><span class="sxs-lookup"><span data-stu-id="8db38-123">For systems that are not subjected to high stress and throughput this database will grow at a slower rate and it will be possible to retain more historical data in the BizTalkDTADb database.</span></span>  
  
 <span data-ttu-id="8db38-124">実行時のパフォーマンスが犠牲にならないように、BizTalkDTADb データベースに最小限のデータを保持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8db38-124">It is recommended to retain minimal data in the BizTalkDTADb database so that runtime performance is not sacrificed.</span></span>