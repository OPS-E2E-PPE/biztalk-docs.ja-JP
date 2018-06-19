---
title: 維持可能な最大のパフォーマンスに影響する要因 |Microsoft ドキュメント
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
ms.openlocfilehash: be96ad552abef66e2a401e334da1c27ee0e08cd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245842"
---
# <a name="factors-that-affect-maximum-sustainable-performance"></a><span data-ttu-id="b9703-102">維持可能な最大パフォーマンスに影響を及ぼす要因</span><span class="sxs-lookup"><span data-stu-id="b9703-102">Factors that Affect Maximum Sustainable Performance</span></span>
<span data-ttu-id="b9703-103">維持可能な最大スループットは、使用可能なサーバー リソース、ソリューションで使用される機能の種類、メッセージ サイズ、全体的なメッセージ負荷などのさまざまな要因によって直接的な影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="b9703-103">Maximum sustainable throughput is directly impacted by a wide range of factors such as available server resources, the type of features used in the solution, message size, and overall message load.</span></span> <span data-ttu-id="b9703-104">直接的ではないながらも、検討を要するその他の要因もあります。</span><span class="sxs-lookup"><span data-stu-id="b9703-104">There are other factors to be considered though that may not be immediately obvious.</span></span> <span data-ttu-id="b9703-105">維持可能な最大パフォーマンスを予測する際は、以下の要因を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="b9703-105">The following factors should also be considered when estimating maximum sustainable performance:</span></span>  
  
## <a name="load-patterns"></a><span data-ttu-id="b9703-106">ロード パターン</span><span class="sxs-lookup"><span data-stu-id="b9703-106">Load Patterns</span></span>  
 <span data-ttu-id="b9703-107">通常、予測可能な一定のレートでメッセージが BizTalk Server の運用環境に送信されることはありません。</span><span class="sxs-lookup"><span data-stu-id="b9703-107">Messages do not typically flow into a production BizTalk Server environment at a predictable, consistent rate.</span></span> <span data-ttu-id="b9703-108">一般的なビジネス要件では、BizTalk Server を使用してメッセージを処理するレートは上下に変動します。</span><span class="sxs-lookup"><span data-stu-id="b9703-108">More typically, business needs dictate that BizTalk Server process messages at a variable rate which exhibits peaks and valleys.</span></span> <span data-ttu-id="b9703-109">ピーク時には BizTalk Server の処理要件は短時間で最小からオーバードライブ状態まで上昇し、メッセージの処理レートよりも受信レートが上回ります。</span><span class="sxs-lookup"><span data-stu-id="b9703-109">When peaks occur, the BizTalk Server processing requirements may quickly jump from negligible to an overdrive condition where messages are received faster than they are processed.</span></span> <span data-ttu-id="b9703-110">このシナリオでは、公開されたメッセージは、バックログされたメッセージが BizTalk によって適切なサブスクライバーに配信されるまで、メッセージ ボックス データベースにバックログされます。</span><span class="sxs-lookup"><span data-stu-id="b9703-110">In this scenario, published messages are backlogged in the MessageBox database until BizTalk delivers the backlogged messages to the appropriate subscribers.</span></span> <span data-ttu-id="b9703-111">BizTalk Server が、ピーク ロード期間に蓄積されたメッセージのバックログを処理できる限り、これが問題になることはありません。</span><span class="sxs-lookup"><span data-stu-id="b9703-111">As long as BizTalk Server is able to process the backlog of messages accumulated between peak load periods then this is not problematic.</span></span>  
  
 <span data-ttu-id="b9703-112">BizTalk Server 環境へのメッセージ フローの一般的なパターンは変動するので、テスト シナリオを一定期間実行して、ソリューションが目的のスループットを維持可能で、時間と共にピーク ロードから回復できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b9703-112">Because of the typically variable pattern of message flow into a BizTalk Server environment, testing scenarios should be run for an extended period of time to ensure that the solution can sustain the desired throughput indefinitely, recovering from all peak loads over time.</span></span>  
  
## <a name="monitoring-and-maintenance-activities"></a><span data-ttu-id="b9703-113">監視および保守アクティビティ</span><span class="sxs-lookup"><span data-stu-id="b9703-113">Monitoring and Maintenance activities</span></span>  
 <span data-ttu-id="b9703-114">運用ソリューションの稼働時には、多くの監視および保守アクティビティが生じます。これらのアクティビティは BizTalk のパフォーマンスに影響する可能性があるので、テスト シナリオに組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9703-114">During the life of a production solution, there is a host of monitoring and maintenance activities that can impact BizTalk performance and so should be factored into any testing scenarios.</span></span> <span data-ttu-id="b9703-115">このようなアクティビティには、以下のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9703-115">These activities include:</span></span>  
  
-   <span data-ttu-id="b9703-116">**BizTalk 管理コンソール クエリ**これらのクエリがリソースを消費し、種類と、クエリの頻度に応じて全体的なスループットに影響します。</span><span class="sxs-lookup"><span data-stu-id="b9703-116">**BizTalk Administration Console queries** These queries consume resources and affect overall throughput depending on the type and frequency of the query.</span></span>  
  
-   <span data-ttu-id="b9703-117">**バックアップ、アーカイブ、および削除アクティビティ**もこれらのアクティビティはリソースを消費し、テスト シナリオに組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9703-117">**Backup, archiving, and purging activities** These activities also consume resources and should be factored into any testing scenarios.</span></span> <span data-ttu-id="b9703-118">すべての BizTalk Server データベースを定期的にバックアップし、トランザクション ログを整理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9703-118">All BizTalk Server databases should be backed up periodically and their transaction logs truncated.</span></span> <span data-ttu-id="b9703-119">この処理を行わない場合、トランザクション ログのサイズが大きくなり、トランザクション データベースのディスク領域がいっぱいになることがあります。</span><span class="sxs-lookup"><span data-stu-id="b9703-119">If this is not performed the transaction log may grow un-checked and consume all of the available disk space for the transaction database.</span></span> <span data-ttu-id="b9703-120">追跡を使用している場合、追跡データベースの定期的なデータ削除および必要に応じたアーカイブを行うことによって、このデータベースのサイズが大きくなりすぎる状況を回避する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9703-120">If tracking is being used, the tracking database must periodically be purged and optionally archived to keep it from growing too large.</span></span> <span data-ttu-id="b9703-121">BizTalk Server データベースの保守の詳細についてを参照してください[をバックアップおよび BizTalk Server データベースの復元](../core/backing-up-and-restoring-biztalk-server-databases.md)です。</span><span class="sxs-lookup"><span data-stu-id="b9703-121">For more information about maintaining BizTalk Server databases, please see [Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9703-122">参照</span><span class="sxs-lookup"><span data-stu-id="b9703-122">See Also</span></span>  
 [<span data-ttu-id="b9703-123">維持可能な最大の追跡スループットの測定</span><span class="sxs-lookup"><span data-stu-id="b9703-123">Measuring Maximum Sustainable Tracking Throughput</span></span>](../core/measuring-maximum-sustainable-tracking-throughput.md)