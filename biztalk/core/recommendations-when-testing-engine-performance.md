---
title: "エンジンのパフォーマンスをテストする場合の推奨事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: maximum sustainable throughput (MST), best practices
ms.assetid: 0aa9d833-0e7d-4347-a6ca-8d658749b4f2
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06fc2d81ca8121fe625a30258070281d2b3ff4bc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="recommendations-when-testing-engine-performance"></a><span data-ttu-id="b275e-102">エンジンのパフォーマンスをテストする際の推奨事項</span><span class="sxs-lookup"><span data-stu-id="b275e-102">Recommendations When Testing Engine Performance</span></span>
<span data-ttu-id="b275e-103">BizTalk エンジンのパフォーマンスをテストする際は、次のガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="b275e-103">The following guidelines should be followed when testing BizTalk engine performance:</span></span>  
  
 <span data-ttu-id="b275e-104">**プロファイルの読み込み動作を知る**3 つのロード テストが示すようにすることが重要の時間の経過と共に処理されるメッセージの観点からロード プロファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="b275e-104">**Know your load behavior profile** As the three load tests have illustrated, it is critical to know the profile of your load in terms of messages processed over time.</span></span>  <span data-ttu-id="b275e-105">この点の理解を深めると、システムの容量のテストや調整をより正確に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b275e-105">The better this is understood, the more accurately you can test and adjust your system capacity.</span></span> <span data-ttu-id="b275e-106">ピークのスループット要件だけを把握している場合、最も保守的なアプローチは、維持できる最大のスループットがピーク時の負荷と同じかそれよりも高くなるように、システムの容量を調整することです。</span><span class="sxs-lookup"><span data-stu-id="b275e-106">If all you know is your peak throughput requirement, then the most conservative approach would be to size your system so that your maximum sustainable throughput is the same or higher than your peak load.</span></span> <span data-ttu-id="b275e-107">ただし、負荷の最大値と最小値を予測できる場合、回復するシステムの最適化を最大値で行うことをお勧めします。これによって、全体の展開が小さく低コストになります。</span><span class="sxs-lookup"><span data-stu-id="b275e-107">However, if you know that you have predictable peaks and valleys in your load, you can better optimize your system to recover between peaks, resulting in a smaller, less expensive overall deployment.</span></span>  
  
 <span data-ttu-id="b275e-108">**パフォーマンスを早い段階テスト**を実稼働のハードウェアのパフォーマンスをテストする設計され、ソリューションの機能のテストが 1 分間実行されるまで待機で大幅な労力をかけてのトラップを避けます。</span><span class="sxs-lookup"><span data-stu-id="b275e-108">**Test performance early** Avoid falling into the trap of investing significant effort in designing and testing the functionality of your solution, but waiting until the last minute to test performance on production hardware.</span></span> <span data-ttu-id="b275e-109">開発サイクルでできるだけ早く必要なロード プロファイルをシミュレートするパフォーマンス テストをシステム上で実行します。</span><span class="sxs-lookup"><span data-stu-id="b275e-109">Run performance tests on your system that simulate the expected load profile as early as you possibly can in your development cycle.</span></span> <span data-ttu-id="b275e-110">設計またはアーキテクチャの設定を変更する必要がある場合、このことを早く把握すると、調整やテストを再度行う時間が確保されます。</span><span class="sxs-lookup"><span data-stu-id="b275e-110">If you have to change anything in your design or architecture to achieve your goals knowing this early will give you time to adjust and test again.</span></span>  
  
 <span data-ttu-id="b275e-111">**パフォーマンスをテストするときに、予想されるロード プロファイルをエミュレート**をこの 2 つの主要なコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="b275e-111">**Emulate your expected load profile when testing performance** There are two primary components to this:</span></span>  
  
1.  <span data-ttu-id="b275e-112">時間の経過と共にロード プロファイルをエミュレートする。</span><span class="sxs-lookup"><span data-stu-id="b275e-112">Emulate the load profile over time.</span></span>  
  
2.  <span data-ttu-id="b275e-113">可能な限り、評価に十分な時間をかけてテストを実行する。</span><span class="sxs-lookup"><span data-stu-id="b275e-113">Run the test long enough to evaluate if it is sustainable.</span></span>  
  
 <span data-ttu-id="b275e-114">一般的に使用される日次サイクルで運用している場合、持続性を検証するため、少なくとも 1 日の間パフォーマンス テストを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b275e-114">If, as is commonly the case, your cycles are daily in nature you should plan to run performance tests for at least one day to validate sustainability.</span></span> <span data-ttu-id="b275e-115">テスト時間が長いほど効果的です。</span><span class="sxs-lookup"><span data-stu-id="b275e-115">The longer that you run the tests, the better.</span></span>  
  
 <span data-ttu-id="b275e-116">**実稼働の構成をエミュレート**例、数値、およびポートの種類、ホストとホスト インスタンスの構成、データベースの構成、およびアダプターのセットアップ。</span><span class="sxs-lookup"><span data-stu-id="b275e-116">**Emulate the production configuration** For example, the number and type of ports, the host and host instance configuration, database configuration, and adapter setup.</span></span> <span data-ttu-id="b275e-117">構成の変更がパフォーマンスに大きな影響を与えないと仮定しないでください。</span><span class="sxs-lookup"><span data-stu-id="b275e-117">Don’t assume that configuration changes will not significantly impact performance.</span></span>  
  
 <span data-ttu-id="b275e-118">**実際のメッセージを使用して**メッセージのサイズとメッセージの複雑さのパフォーマンスに影響を与える、ため必ずおよびテスト メッセージ スキーマと実稼働環境で参照しようとするインスタンスが同じでします。</span><span class="sxs-lookup"><span data-stu-id="b275e-118">**Use real messages** Message sizes and message complexity affect performance, so be sure and test with the same message schemas and instances that you plan to see in production.</span></span>  
  
 <span data-ttu-id="b275e-119">**パフォーマンス テスト中に、通常の動作をエミュレート**ロード テストに、バックアップの定期的なデータベース クエリなど、標準の操作のアクティビティが含まれていませんし、削除、維持可能なスループットに影響は、必ずようにします。パフォーマンスおよび容量テストの実行中にこれらのタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="b275e-119">**Emulate your normal operations during performance tests** Though the load tests did not include them, standard operations activities such as periodic database queries, backups, and purging will affect your sustainable throughput, so make sure you are performing these tasks during your performance and capacity test runs.</span></span> <span data-ttu-id="b275e-120">実稼働環境で DTA 追跡と BAM 追跡を使用する予定の場合は、それも含めます。</span><span class="sxs-lookup"><span data-stu-id="b275e-120">This includes both DTA and BAM tracking, if you plan to use them in production.</span></span>  
  
 <span data-ttu-id="b275e-121">**メッセージ ボックスに、I/O サブシステムの速度は、成功の鍵**実行したロード テストは、このビルドアウト専用メッセージ ボックス データベース ファイルの高速記憶域エリア ネットワークの使用を作成します。この場合でも、クリーンアップ ジョブは、SQL データ ファイルのアイドル時間をほとんど 0 の状態にしました。</span><span class="sxs-lookup"><span data-stu-id="b275e-121">**The speed of the I/O subsystem for the MessageBox is a key success factor** The load tests that were performed made use of a fast Storage Area Network for the MessageBox database files that is dedicated to this build-out. Even in this case, the cleanup jobs were able to drive the idle time to near zero for the SQL data file.</span></span> <span data-ttu-id="b275e-122">I/O サブシステムは、運用システムのボトルネックによくなります。</span><span class="sxs-lookup"><span data-stu-id="b275e-122">The I/O subsystem is frequently a bottleneck in production systems.</span></span> <span data-ttu-id="b275e-123">SQL の I/O を最適化する一般的な方法は、可能な場合、データベース データ ファイルとログ ファイルを別々の物理ドライブに格納することです。</span><span class="sxs-lookup"><span data-stu-id="b275e-123">A common strategy to optimize SQL I/O is to place the database data file(s) and log file(s) on separate physical drives, if possible.</span></span>  
  
 <span data-ttu-id="b275e-124">**すべてのメッセージ ボックス サーバーで SQL エージェントが実行されていることを確認**明らかに、クリーンアップ ジョブはことはありません、SQL エージェントが実行されていない場合に実行してください。 これらが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b275e-124">**Make sure the SQL Agent is running on all MessageBox servers** Clearly, the cleanup jobs will never run if the SQL Agent is not running, so make sure these are running.</span></span>  
  
 <span data-ttu-id="b275e-125">**スプールの深さは主要な指標**他の指標に関係なくこのメジャーは、する場合は、システムはされているクリップが発生するかを評価する迅速かつ簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="b275e-125">**Spool depth is a key indicator** Regardless of other indicators, this measure will give you a quick and easy way to assess if your system is being overdriven or not.</span></span>