---
title: "メッセージ ボックスの待機時間に関する問題のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9eb5789-80bd-40d4-8c27-7ae117fd9232
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e37fc970230bf218bcfd820611fb6b87322e535
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-messagebox-latency-issues"></a><span data-ttu-id="d647a-102">メッセージ ボックスの遅延に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d647a-102">Troubleshooting MessageBox Latency Issues</span></span>
<span data-ttu-id="d647a-103">理想の世界では、メッセージはいずれもメッセージ ボックス データベースに公開された時点で速やかに処理および配信され、メッセージ ボックス データベースのサイズが過剰に増加することはないかもしれません。</span><span class="sxs-lookup"><span data-stu-id="d647a-103">In a perfect world, all messages would be processed and delivered as soon as they were published to the MessageBox database and the MessageBox database would never grow to an excessive size.</span></span> <span data-ttu-id="d647a-104">メッセージ ボックス内に参照されなくなったメッセージがあれば、メッセージ ボックス データベース テーブルを定期的にクリーンアップする SQL エージェント ジョブによってすぐに削除されます。</span><span class="sxs-lookup"><span data-stu-id="d647a-104">Any messages in the MessageBox that were no longer referenced would immediately be removed by the SQL agent jobs that periodically clean up the MessageBox database tables.</span></span>  
  
 <span data-ttu-id="d647a-105">ところが現実の世界では、メッセージが予測可能な一定速度で届くことはまれで、SQL エージェント ジョブがメッセージ ボックス データベース テーブルをクリーンアップするには時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="d647a-105">In real world scenarios, however, messages are not typically received in a predictable, linear fashion and the SQL agent jobs require time to clean up the MessageBox database tables.</span></span>  
  
 <span data-ttu-id="d647a-106">このため、シナリオによっては、メッセージ ボックスのサイズが急速に増加する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d647a-106">Therefore, in some scenarios; the MessageBox can grow fairly large very quickly.</span></span>  
  
 <span data-ttu-id="d647a-107">次の場合はメッセージ ボックスのサイズが過剰に肥大化し、処理全体の妨げとなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d647a-107">The following items can cause the MessageBox to grow excessively large and hinder overall performance:</span></span>  
  
-   <span data-ttu-id="d647a-108">**「ホストの追跡を許可する」オプションを設定のある Biztalk ホスト インスタンスが停止している**です。</span><span class="sxs-lookup"><span data-stu-id="d647a-108">**The Biztalk Host instance that has the "allow Host tracking" option set is stopped**.</span></span> <span data-ttu-id="d647a-109">これは、メッセージ ボックス データベースから BizTalk 追跡データベース (BizTalkDTADb) への追跡データの移動を行うホストです。</span><span class="sxs-lookup"><span data-stu-id="d647a-109">This is the host that is responsible for moving the tracking data from the MessageBox database to the Biztalk Tracking database(BizTalkDTADb).</span></span>  
  
-   <span data-ttu-id="d647a-110">**SQL Server エージェントが実行されていない**これは、[後で、メッセージ ボックスに移動したデータを消去する]、BizTalkDTADb データベースにメッセージ ボックス データベースからデータを移動を行う SQL ジョブが実行されていない場合に発生することができます。</span><span class="sxs-lookup"><span data-stu-id="d647a-110">**SQL Server Agent is not running** This can happen if the SQL jobs responsible for moving data from the MessageBox database to the BizTalkDTADb database [subsequently purging the moved data in the MessageBox] are not running.</span></span> <span data-ttu-id="d647a-111">この問題を回避するため、SQL エージェント サービスを常に実行しておくことが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="d647a-111">It is imperative the SQL Agent Service be running all the time to avoid this problem.</span></span>  
  
-   <span data-ttu-id="d647a-112">**SQL Server ジョブが無効になっている**なしの既定の SQL Server ジョブを無効にする命令型は、SQL Server エージェントが実行されている場合でもです。</span><span class="sxs-lookup"><span data-stu-id="d647a-112">**SQL Server Jobs are disabled** Even if the SQL Server Agent is running, it is imperative that none of the default SQL Server jobs be disabled.</span></span>  
  
-   <span data-ttu-id="d647a-113">**BizTalkDTADb データベースのサイズが過剰**BizTalkDTADb データベースが非常に大きく、原因で時間がかかって BizTalkDTADb データベースに挿入する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="d647a-113">**BizTalkDTADb database grows excessively** This can happen if the BizTalkDTADb database grows very large, causing inserts into the BizTalkDTADb database to take longer.</span></span> <span data-ttu-id="d647a-114">このような状態になると、TDDS (Tracking Data Delivery Service) によるデータの移動速度が低下し、メッセージ ボックス データベースにバックログが蓄積されるようになります。</span><span class="sxs-lookup"><span data-stu-id="d647a-114">When this happens the movement of data by Tracking Data Delivery Service (TDDS) slows down, causing a backlog build up in the MessageBox database.</span></span> <span data-ttu-id="d647a-115">この問題を回避するには、BizTalkDTADb データベースに対して SQL Server のアーカイブと削除のジョブを定期的に実行することが重要になります。</span><span class="sxs-lookup"><span data-stu-id="d647a-115">To avoid this problem it is important to run the SQL server archive and purge jobs periodically on the BizTalkDTADb databases.</span></span>  
  
-   <span data-ttu-id="d647a-116">**過剰なディスク I/O の待機時間**かどうか、メッセージ ボックス データベースにデータの着信レート、システムが処理できるよりも高速であり、BizTalkDTADb データベースにデータを移動バックログが蓄積されるメッセージ ボックス データベースにします。</span><span class="sxs-lookup"><span data-stu-id="d647a-116">**Excessive Disk I/O Latency** If the incoming rate of data into the MessageBox database is faster than which the system can process and move the data to the BizTalkDTADb database, backlog can build up in the MessageBox database.</span></span> <span data-ttu-id="d647a-117">バックログが増加し続けることは深刻な問題であり、システムのパフォーマンスが時間の経過に伴って低下します。</span><span class="sxs-lookup"><span data-stu-id="d647a-117">If the backlog continues to grow unabated, this is a very serious problem and system performance will degrade over time.</span></span> <span data-ttu-id="d647a-118">この問題を軽減する 1 つの方法は、時間の経過と共に発生するメッセージ バックログからシステムが確実に回復できるように、より高速なディスクの導入やハードウェアのアップグレードを行うことです。</span><span class="sxs-lookup"><span data-stu-id="d647a-118">One way to alleviate this problem is to install faster disks and/or upgrade the hardware to help ensure that the system is capable of recovering from any message backlogs experienced over time.</span></span>  
  
## <a name="plan-for-the-future"></a><span data-ttu-id="d647a-119">将来の計画</span><span class="sxs-lookup"><span data-stu-id="d647a-119">Plan for the Future</span></span>  
 <span data-ttu-id="d647a-120">上記のすべてのベスト プラクティスに従ったとしても、時間の経過と共に、BizTalkDTADb データベースに移動される追跡データの量は非常に大きくなります。</span><span class="sxs-lookup"><span data-stu-id="d647a-120">Even though all the best practices above are followed, over time the volume of tracking data moved to the BizTalkDTADb database will grow very large.</span></span> <span data-ttu-id="d647a-121">システムが最適なパフォーマンスを維持できるように、追跡データを定期的にアーカイブするデータベース メンテナンス プランを実装することが重要です。</span><span class="sxs-lookup"><span data-stu-id="d647a-121">It is important to implement a database maintenance plan to periodically archive tracking data so that the system can continue to perform optimally.</span></span>  
  
 <span data-ttu-id="d647a-122">BizTalkDTADb データベースに保持できる履歴データの量は、システムを経由してプッシュされるメッセージの量に応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="d647a-122">The amount of historical data that can be retained in the BizTalkDTADb database depends on the volume of messages pushed through the system.</span></span> <span data-ttu-id="d647a-123">高い負荷やスループットが発生しないシステムでは、このデータベースのサイズは比較的緩やかに増加するため、より多くの履歴データを BizTalkDTADb データベースに保持することができます。</span><span class="sxs-lookup"><span data-stu-id="d647a-123">For systems that are not subjected to high stress and throughput this database will grow at a slower rate and it will be possible to retain more historical data in the BizTalkDTADb database.</span></span>  
  
 <span data-ttu-id="d647a-124">実行時のパフォーマンスを損なわないように、BizTalkDTADb データベースに保持するデータは最小限にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d647a-124">It is recommended to retain minimal data in the BizTalkDTADb database so that runtime performance is not sacrificed.</span></span>