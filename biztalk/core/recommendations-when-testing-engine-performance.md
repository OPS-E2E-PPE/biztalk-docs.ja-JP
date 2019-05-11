---
title: エンジンのパフォーマンスをテストする場合の推奨事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maximum sustainable throughput (MST), best practices
ms.assetid: 0aa9d833-0e7d-4347-a6ca-8d658749b4f2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf1a6712a2ad52dfb82f7a52b341f770eb48c7bb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398070"
---
# <a name="recommendations-when-testing-engine-performance"></a><span data-ttu-id="3ad5d-102">エンジンのパフォーマンスをテストする際の推奨事項</span><span class="sxs-lookup"><span data-stu-id="3ad5d-102">Recommendations When Testing Engine Performance</span></span>
<span data-ttu-id="3ad5d-103">BizTalk エンジンのパフォーマンスをテストするときに、次のガイドラインを後にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ad5d-103">The following guidelines should be followed when testing BizTalk engine performance:</span></span>  
  
 <span data-ttu-id="3ad5d-104">**読み込み動作のプロファイルを知る**が時間の経過と共に処理されるメッセージの観点から、読み込みのプロファイルを把握する重要な 3 つのロード テストが示すように、します。</span><span class="sxs-lookup"><span data-stu-id="3ad5d-104">**Know your load behavior profile** As the three load tests have illustrated, it is critical to know the profile of your load in terms of messages processed over time.</span></span>  <span data-ttu-id="3ad5d-105">これを理解するほどより正確にテストし、調整できます、システムの容量。</span><span class="sxs-lookup"><span data-stu-id="3ad5d-105">The better this is understood, the more accurately you can test and adjust your system capacity.</span></span> <span data-ttu-id="3ad5d-106">ピークのスループット要件すべて把握する場合は、最も保守的なアプローチ作成してから、維持可能な最大のスループットは、同じシステムのサイズまたはピーク時よりも高い負荷があります。</span><span class="sxs-lookup"><span data-stu-id="3ad5d-106">If all you know is your peak throughput requirement, then the most conservative approach would be to size your system so that your maximum sustainable throughput is the same or higher than your peak load.</span></span> <span data-ttu-id="3ad5d-107">ただし、負荷の予測可能な山と谷がある場合より適切に小さく、低コストの全体的なデプロイでのピークの間の回復、システムを最適化できます。</span><span class="sxs-lookup"><span data-stu-id="3ad5d-107">However, if you know that you have predictable peaks and valleys in your load, you can better optimize your system to recover between peaks, resulting in a smaller, less expensive overall deployment.</span></span>  
  
 <span data-ttu-id="3ad5d-108">**早い段階でパフォーマンスをテスト**トラップの実稼働のハードウェアのパフォーマンスをテストする設計と、ソリューションの機能のテストが最後の 1 分まで待機している大きな労力を費やすことを避けます。</span><span class="sxs-lookup"><span data-stu-id="3ad5d-108">**Test performance early** Avoid falling into the trap of investing significant effort in designing and testing the functionality of your solution, but waiting until the last minute to test performance on production hardware.</span></span> <span data-ttu-id="3ad5d-109">開発サイクルでできるだけ早く必要なロード プロファイルをシミュレートするシステムでパフォーマンス テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="3ad5d-109">Run performance tests on your system that simulate the expected load profile as early as you possibly can in your development cycle.</span></span> <span data-ttu-id="3ad5d-110">デザインで何も変更する必要があるかこれを早期に把握するためのアーキテクチャは、時間を調整してもう一度テストします。</span><span class="sxs-lookup"><span data-stu-id="3ad5d-110">If you have to change anything in your design or architecture to achieve your goals knowing this early will give you time to adjust and test again.</span></span>  
  
 <span data-ttu-id="3ad5d-111">**パフォーマンスをテストするときに、予想される負荷プロファイルをエミュレート**はこの 2 つの主要なコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="3ad5d-111">**Emulate your expected load profile when testing performance** There are two primary components to this:</span></span>  
  
1. <span data-ttu-id="3ad5d-112">時間の経過と共にロード プロファイルをエミュレートします。</span><span class="sxs-lookup"><span data-stu-id="3ad5d-112">Emulate the load profile over time.</span></span>  
  
2. <span data-ttu-id="3ad5d-113">維持可能な場合に評価する十分な時間、テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="3ad5d-113">Run the test long enough to evaluate if it is sustainable.</span></span>  
  
   <span data-ttu-id="3ad5d-114">サイクルが本質的に毎日ケースは一般的では、持続性を検証するには少なくとも 1 日のパフォーマンス テストを実行する計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ad5d-114">If, as is commonly the case, your cycles are daily in nature you should plan to run performance tests for at least one day to validate sustainability.</span></span> <span data-ttu-id="3ad5d-115">長いほど良い、テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="3ad5d-115">The longer that you run the tests, the better.</span></span>  
  
   <span data-ttu-id="3ad5d-116">**運用環境の構成をエミュレート**例、数値、およびポートの種類、ホストとホスト インスタンスの構成、データベースの構成、およびアダプターのセットアップ。</span><span class="sxs-lookup"><span data-stu-id="3ad5d-116">**Emulate the production configuration** For example, the number and type of ports, the host and host instance configuration, database configuration, and adapter setup.</span></span> <span data-ttu-id="3ad5d-117">ある構成の変更が大幅にパフォーマンスに影響しないと仮定しないでください。</span><span class="sxs-lookup"><span data-stu-id="3ad5d-117">Don’t assume that configuration changes will not significantly impact performance.</span></span>  
  
   <span data-ttu-id="3ad5d-118">**実際のメッセージを使用して**メッセージのサイズとメッセージの複雑さのパフォーマンスに影響を与えるためを必ずメッセージ スキーマと実稼働環境でする予定のインスタンスを使用してテストします。</span><span class="sxs-lookup"><span data-stu-id="3ad5d-118">**Use real messages** Message sizes and message complexity affect performance, so be sure and test with the same message schemas and instances that you plan to see in production.</span></span>  
  
   <span data-ttu-id="3ad5d-119">**パフォーマンス テスト中に、通常の動作をエミュレート**ロード テストに定期的にデータベースのクエリでは、バックアップなどの標準の操作のアクティビティが含まれていませんし、削除、維持可能なスループットに影響は、そのためことを確認しますパフォーマンスと容量のテストの実行中に、これらのタスクを実行しています。</span><span class="sxs-lookup"><span data-stu-id="3ad5d-119">**Emulate your normal operations during performance tests** Though the load tests did not include them, standard operations activities such as periodic database queries, backups, and purging will affect your sustainable throughput, so make sure you are performing these tasks during your performance and capacity test runs.</span></span> <span data-ttu-id="3ad5d-120">運用環境で使用する場合 DTA と BAM の追跡が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3ad5d-120">This includes both DTA and BAM tracking, if you plan to use them in production.</span></span>  
  
   <span data-ttu-id="3ad5d-121">**メッセージ ボックスに、I/O サブシステムの速度は、成功の鍵**実行したロード テストは、メッセージ ボックス データベース ファイルは、このビルドアウト専用の高速記憶域ネットワークの使用を作成します。この場合でも、クリーンアップ ジョブは、SQL データ ファイルのゼロをほぼのアイドル時間をできました。</span><span class="sxs-lookup"><span data-stu-id="3ad5d-121">**The speed of the I/O subsystem for the MessageBox is a key success factor** The load tests that were performed made use of a fast Storage Area Network for the MessageBox database files that is dedicated to this build-out. Even in this case, the cleanup jobs were able to drive the idle time to near zero for the SQL data file.</span></span> <span data-ttu-id="3ad5d-122">I/O サブシステムは、実稼働システムのボトルネックでがよくあります。</span><span class="sxs-lookup"><span data-stu-id="3ad5d-122">The I/O subsystem is frequently a bottleneck in production systems.</span></span> <span data-ttu-id="3ad5d-123">SQL の I/O を最適化するために一般的な戦略は、データベース データ ファイルを配置し、ログの別の物理ドライブにファイルを可能な場合です。</span><span class="sxs-lookup"><span data-stu-id="3ad5d-123">A common strategy to optimize SQL I/O is to place the database data file(s) and log file(s) on separate physical drives, if possible.</span></span>  
  
   <span data-ttu-id="3ad5d-124">**すべてのメッセージ ボックス サーバーで SQL エージェントが実行されていることを確認**明らかに、クリーンアップ ジョブはことはありません実行 SQL エージェントが実行されていない場合、これらが実行されているようにします。</span><span class="sxs-lookup"><span data-stu-id="3ad5d-124">**Make sure the SQL Agent is running on all MessageBox servers** Clearly, the cleanup jobs will never run if the SQL Agent is not running, so make sure these are running.</span></span>  
  
   <span data-ttu-id="3ad5d-125">**スプールの深さがキー インジケーター**他のインジケーターに関係なくこのメジャーが表示されますか、システムは過度がされている場合を評価する迅速かつ簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="3ad5d-125">**Spool depth is a key indicator** Regardless of other indicators, this measure will give you a quick and easy way to assess if your system is being overdriven or not.</span></span>