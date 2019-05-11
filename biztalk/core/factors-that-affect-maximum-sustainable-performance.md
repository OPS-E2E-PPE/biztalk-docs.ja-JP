---
title: 維持可能な最大のパフォーマンスに影響する要因 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maximum sustainable throughput (MST), maintenance
- monitoring, maximum sustainable thoughput (MST)
- maintaining, maximum sustainable thoughput (MST)
- maximum sustainable throughput (MST), monitoring
- maximum sustainable throughput (MST), load patterns
- maximum sustainable throughput (MST), sustainable load test
- sustainable performance
ms.assetid: 99b99655-bc77-425c-a133-204781d7c430
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4f14a1915f70856342f61c8c41f5fbb90233205
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345888"
---
# <a name="factors-that-affect-maximum-sustainable-performance"></a><span data-ttu-id="e74cb-102">維持可能な最大パフォーマンスに影響を及ぼす要因</span><span class="sxs-lookup"><span data-stu-id="e74cb-102">Factors that Affect Maximum Sustainable Performance</span></span>
<span data-ttu-id="e74cb-103">最大持続可能スループットが直接多岐にわたって利用可能なサーバー リソース、ソリューション、メッセージのサイズ、および全体的なメッセージ負荷で使用される機能の種類などの要因によって影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="e74cb-103">Maximum sustainable throughput is directly impacted by a wide range of factors such as available server resources, the type of features used in the solution, message size, and overall message load.</span></span> <span data-ttu-id="e74cb-104">すぐにわかりにくいも、検討を他の要素があります。</span><span class="sxs-lookup"><span data-stu-id="e74cb-104">There are other factors to be considered though that may not be immediately obvious.</span></span> <span data-ttu-id="e74cb-105">維持可能な最大のパフォーマンスを推定する際にも、次の要因を検討してください。</span><span class="sxs-lookup"><span data-stu-id="e74cb-105">The following factors should also be considered when estimating maximum sustainable performance:</span></span>  
  
## <a name="load-patterns"></a><span data-ttu-id="e74cb-106">ロード パターン</span><span class="sxs-lookup"><span data-stu-id="e74cb-106">Load Patterns</span></span>  
 <span data-ttu-id="e74cb-107">メッセージは、通常は、一貫性のある予測可能な速度での BizTalk Server 環境の運用環境にフローしません。</span><span class="sxs-lookup"><span data-stu-id="e74cb-107">Messages do not typically flow into a production BizTalk Server environment at a predictable, consistent rate.</span></span> <span data-ttu-id="e74cb-108">一般的には、ビジネス上のニーズは上下谷に評価する BizTalk Server 変数メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="e74cb-108">More typically, business needs dictate that BizTalk Server process messages at a variable rate which exhibits peaks and valleys.</span></span> <span data-ttu-id="e74cb-109">ピークが発生すると、BizTalk Server 処理要件可能性がありますにすばやく移動からごくわずか overdrive の条件をメッセージが処理されるよりも速く受信場所。</span><span class="sxs-lookup"><span data-stu-id="e74cb-109">When peaks occur, the BizTalk Server processing requirements may quickly jump from negligible to an overdrive condition where messages are received faster than they are processed.</span></span> <span data-ttu-id="e74cb-110">このシナリオで BizTalk が適切なサブスクライバーに未処理のメッセージを配信するまでに公開されたメッセージがメッセージ ボックス データベース バックログします。</span><span class="sxs-lookup"><span data-stu-id="e74cb-110">In this scenario, published messages are backlogged in the MessageBox database until BizTalk delivers the backlogged messages to the appropriate subscribers.</span></span> <span data-ttu-id="e74cb-111">BizTalk Server が負荷のピーク期間の間でメッセージのバックログが蓄積されたプロセスをできる限り、これは問題になりません。</span><span class="sxs-lookup"><span data-stu-id="e74cb-111">As long as BizTalk Server is able to process the backlog of messages accumulated between peak load periods then this is not problematic.</span></span>  
  
 <span data-ttu-id="e74cb-112">BizTalk Server 環境へのメッセージ フローの通常の変数パターン、テストのシナリオを実行する、長期間にわたって、ソリューションが必要なスループットは無期限に、ピーク ロードから回復を維持できることを確認します。推移します。</span><span class="sxs-lookup"><span data-stu-id="e74cb-112">Because of the typically variable pattern of message flow into a BizTalk Server environment, testing scenarios should be run for an extended period of time to ensure that the solution can sustain the desired throughput indefinitely, recovering from all peak loads over time.</span></span>  
  
## <a name="monitoring-and-maintenance-activities"></a><span data-ttu-id="e74cb-113">監視および保守アクティビティ</span><span class="sxs-lookup"><span data-stu-id="e74cb-113">Monitoring and Maintenance activities</span></span>  
 <span data-ttu-id="e74cb-114">運用環境のソリューションの有効期間、中に監視のホストがあるし、メンテナンス作業と BizTalk のパフォーマンスに影響を与えることができますが、テスト シナリオに組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="e74cb-114">During the life of a production solution, there is a host of monitoring and maintenance activities that can impact BizTalk performance and so should be factored into any testing scenarios.</span></span> <span data-ttu-id="e74cb-115">これらのアクティビティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e74cb-115">These activities include:</span></span>  
  
-   <span data-ttu-id="e74cb-116">**BizTalk 管理コンソール クエリ**これらのクエリがリソースを消費し、種類と、クエリの頻度に応じて全体的なスループットに影響します。</span><span class="sxs-lookup"><span data-stu-id="e74cb-116">**BizTalk Administration Console queries** These queries consume resources and affect overall throughput depending on the type and frequency of the query.</span></span>  
  
-   <span data-ttu-id="e74cb-117">**バックアップ、アーカイブ、および削除アクティビティ**もこれらのアクティビティはリソースを消費し、テスト シナリオに組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="e74cb-117">**Backup, archiving, and purging activities** These activities also consume resources and should be factored into any testing scenarios.</span></span> <span data-ttu-id="e74cb-118">BizTalk Server のすべてのデータベースは定期的にバックアップする必要があり、トランザクション ログの切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="e74cb-118">All BizTalk Server databases should be backed up periodically and their transaction logs truncated.</span></span> <span data-ttu-id="e74cb-119">実行されません、トランザクション ログ可能性がありますオフが大きくなり、すべてのトランザクション データベースの使用可能なディスク領域を消費します。</span><span class="sxs-lookup"><span data-stu-id="e74cb-119">If this is not performed the transaction log may grow un-checked and consume all of the available disk space for the transaction database.</span></span> <span data-ttu-id="e74cb-120">追跡データベース定期的に削除する必要があります、追跡が使用されている場合と大きくなりすぎないようにする必要に応じたアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="e74cb-120">If tracking is being used, the tracking database must periodically be purged and optionally archived to keep it from growing too large.</span></span> <span data-ttu-id="e74cb-121">BizTalk Server データベースの保守の詳細についてを参照してください[Backing Up and BizTalk Server データベースの復元](../core/backing-up-and-restoring-biztalk-server-databases.md)します。</span><span class="sxs-lookup"><span data-stu-id="e74cb-121">For more information about maintaining BizTalk Server databases, please see [Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e74cb-122">参照</span><span class="sxs-lookup"><span data-stu-id="e74cb-122">See Also</span></span>  
 [<span data-ttu-id="e74cb-123">維持可能な最大の追跡スループットの測定</span><span class="sxs-lookup"><span data-stu-id="e74cb-123">Measuring Maximum Sustainable Tracking Throughput</span></span>](../core/measuring-maximum-sustainable-tracking-throughput.md)