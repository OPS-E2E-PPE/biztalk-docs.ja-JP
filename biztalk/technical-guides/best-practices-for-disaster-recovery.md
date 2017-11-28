---
title: "災害復旧のためのベスト プラクティス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: afbb0a57-0d31-4a2f-847c-02b40361c0ed
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e988055205203c5c4bc7a4d9d6e84706414967c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-disaster-recovery"></a><span data-ttu-id="6201f-102">災害復旧のためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="6201f-102">Best Practices for Disaster Recovery</span></span>
<span data-ttu-id="6201f-103">災害復旧のためのベスト プラクティスについて[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]を参照してください[バックアップと復元のベスト プラクティス](http://go.microsoft.com/fwlink/?LinkId=151391)(http://go.microsoft.com/fwlink/?LinkId=151391) で[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="6201f-103">For information about best practices for disaster recovery for [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], see [Best Practices for Backup and Restore](http://go.microsoft.com/fwlink/?LinkId=151391) (http://go.microsoft.com/fwlink/?LinkId=151391) in [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
 <span data-ttu-id="6201f-104">**バックアップを作成し、復元の計画**</span><span class="sxs-lookup"><span data-stu-id="6201f-104">**Create a backup and restore plan**</span></span>  
  
-   <span data-ttu-id="6201f-105">バックアップ プランでは、必ず次の項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="6201f-105">Be sure your backup plan specifies:</span></span>  
  
    -   <span data-ttu-id="6201f-106">バックアップの格納先コンピュータ</span><span class="sxs-lookup"><span data-stu-id="6201f-106">The computer where backups will be stored</span></span>  
  
    -   <span data-ttu-id="6201f-107">システムのバックアップに使用するプログラム</span><span class="sxs-lookup"><span data-stu-id="6201f-107">The programs that you will use to back up your system</span></span>  
  
    -   <span data-ttu-id="6201f-108">バックアップするコンピュータ</span><span class="sxs-lookup"><span data-stu-id="6201f-108">The computers you want to back up</span></span>  
  
    -   <span data-ttu-id="6201f-109">バックアップを実行するスケジュール</span><span class="sxs-lookup"><span data-stu-id="6201f-109">The schedule when backups will occur</span></span>  
  
    -   <span data-ttu-id="6201f-110">バックアップをアーカイブするオフサイトの場所</span><span class="sxs-lookup"><span data-stu-id="6201f-110">The offsite location where you will archive backups</span></span>  
  
 <span data-ttu-id="6201f-111">**BizTalk Server システムへのすべての変更の記録を維持します。**</span><span class="sxs-lookup"><span data-stu-id="6201f-111">**Keep a written record of all changes to your BizTalk Server system**</span></span>  
  
-   <span data-ttu-id="6201f-112">適用したサービス パック、修正プログラム、QFE など、システムへのすべての変更を必ず記録します。</span><span class="sxs-lookup"><span data-stu-id="6201f-112">Be sure to write down all changes to your system, such as service packs, hotfixes, and QFEs that have been applied.</span></span> <span data-ttu-id="6201f-113">できるだけハードウェア障害の発生前に近い状態でシステムを復元するには、このことが不可欠です。</span><span class="sxs-lookup"><span data-stu-id="6201f-113">This is crucial to getting your system restored as closely as possible to what existed before the hardware failure.</span></span>  
  
 <span data-ttu-id="6201f-114">**防止または障害の影響を最小限に抑えるには次のメジャーを実装します。**</span><span class="sxs-lookup"><span data-stu-id="6201f-114">**Implement the following measures to help prevent or minimize the effect of a disaster**</span></span>  
  
-   <span data-ttu-id="6201f-115">ソフトウェアおよびファームウェアの更新を利用できるようにしておく。</span><span class="sxs-lookup"><span data-stu-id="6201f-115">Have your software and firmware updates available.</span></span>  
  
-   <span data-ttu-id="6201f-116">すべてのソフトウェア ディスクをすぐに利用できるようにしておく。</span><span class="sxs-lookup"><span data-stu-id="6201f-116">Have all software disks readily available.</span></span>  
  
-   <span data-ttu-id="6201f-117">サーバーの積極的な監視計画を立てておく。</span><span class="sxs-lookup"><span data-stu-id="6201f-117">Have a plan to monitor servers proactively.</span></span> <span data-ttu-id="6201f-118">これは、機能は、最大 10 分の 2 つ目のホストで障害が発生したホストのオーケストレーション インスタンスがリカバリいない可能性がありますので非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="6201f-118">This is very important since orchestration instances on a failed host may not be recovered by a second host for up to 10 minutes.</span></span>  
  
-   <span data-ttu-id="6201f-119">ハードウェアの記録をとっておく。</span><span class="sxs-lookup"><span data-stu-id="6201f-119">Maintain hardware records.</span></span>  
  
-   <span data-ttu-id="6201f-120">ソフトウェアの記録をとっておく。</span><span class="sxs-lookup"><span data-stu-id="6201f-120">Maintain software records.</span></span>  
  
 <span data-ttu-id="6201f-121">**ハードウェアまたはソフトウェア レベルで、組織内のフォールト トレランスを実装します。**</span><span class="sxs-lookup"><span data-stu-id="6201f-121">**Implement fault tolerance in your organization at the hardware or software level**</span></span>  
  
-   <span data-ttu-id="6201f-122">クラスタと RAID (Redundant Array of Independent Disks) を実装することで、ハードウェア障害からシステムを守ることができます。</span><span class="sxs-lookup"><span data-stu-id="6201f-122">Implementing clusters and redundant array of independent disks (RAID) helps ensure that your system can survive a hardware failure.</span></span>  
  
 <span data-ttu-id="6201f-123">**アーカイブを定期的に安全な場所にバックアップ メディア**</span><span class="sxs-lookup"><span data-stu-id="6201f-123">**Archive the backup media on a regular basis in a secure location**</span></span>  
  
-   <span data-ttu-id="6201f-124">バックアップ メディアを定期的にアーカイブするスケジュールを作成し、アーカイブを安全な別の場所に保管します。</span><span class="sxs-lookup"><span data-stu-id="6201f-124">Create a schedule for archiving your backup media on a regular basis and keep the archives in a secure, offsite location.</span></span> <span data-ttu-id="6201f-125">こうしておくと、必要なときにバックアップを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6201f-125">This ensures that you have a backup available when you need it.</span></span>  
  
 <span data-ttu-id="6201f-126">**バックアップの整合性を確認し、エラーはありません**</span><span class="sxs-lookup"><span data-stu-id="6201f-126">**Verify the integrity of your backups and that they occur without error**</span></span>  
  
-   <span data-ttu-id="6201f-127">すべてのバックアップ ジョブを監視して、完了までにエラーが発生していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6201f-127">Monitor all of your backup jobs and ensure that they complete without any errors.</span></span>  
  
 <span data-ttu-id="6201f-128">**使用可能な同一の予備のハードウェアします。**</span><span class="sxs-lookup"><span data-stu-id="6201f-128">**Keep identical spare hardware available**</span></span>  
  
-   <span data-ttu-id="6201f-129">同じハードウェアを予備として利用可能なを置くことは、欠陥のあるハードウェアを開始してより迅速に実行されている迅速に置換できることになります。</span><span class="sxs-lookup"><span data-stu-id="6201f-129">Having identical spare hardware available ensures that you can quickly replace defective hardware to get up and running more quickly.</span></span>  
  
 <span data-ttu-id="6201f-130">**文書化し、回復手順のテスト**</span><span class="sxs-lookup"><span data-stu-id="6201f-130">**Document and test your recovery procedures**</span></span>  
  
-   <span data-ttu-id="6201f-131">システムを実稼動する前には、必ず災害復旧テストを実施します。</span><span class="sxs-lookup"><span data-stu-id="6201f-131">Disaster recovery testing should be conducted before ever running your system in production.</span></span> <span data-ttu-id="6201f-132">適切な計画を立てて事前テストを実施することで、IT スタッフが BizTalk Server システムを確実に復旧できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6201f-132">Having plans in place and performing prerelease testing will ensure that your IT staff can recover your BizTalk Server systems.</span></span>  
  
 <span data-ttu-id="6201f-133">**災害復旧手順に関して、IT スタッフをトレーニングします。**</span><span class="sxs-lookup"><span data-stu-id="6201f-133">**Train your IT staff on disaster recovery procedures**</span></span>  
  
-   <span data-ttu-id="6201f-134">システムの復旧が必要な場合に備え、IT スタッフの態勢を整えておきます。</span><span class="sxs-lookup"><span data-stu-id="6201f-134">Ensure that your IT staff is prepared to recover the system should the need arise.</span></span>  
  
 <span data-ttu-id="6201f-135">**テスト環境でのバックアップから復元を演習します。**</span><span class="sxs-lookup"><span data-stu-id="6201f-135">**Practice restoring from a backup in a test environment**</span></span>  
  
-   <span data-ttu-id="6201f-136">テスト環境で BizTalk Server システムの復元を演習し、障害が発生したとき確実に実稼動環境に復元できるようにしておきます。</span><span class="sxs-lookup"><span data-stu-id="6201f-136">Practice restoring your BizTalk Server system in a test environment to ensure that you can restore it to your production environment if a failure occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6201f-137">参照</span><span class="sxs-lookup"><span data-stu-id="6201f-137">See Also</span></span>  
 [<span data-ttu-id="6201f-138">災害復旧</span><span class="sxs-lookup"><span data-stu-id="6201f-138">Disaster Recovery</span></span>](../technical-guides/disaster-recovery.md)