---
title: バックアップと復元のベスト プラクティス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aaf721ba-50ce-4334-b86d-e856b54d3486
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 540e8660ccc60d1e927c544beab2548a357a781f
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530518"
---
# <a name="best-practices-for-backup-and-restore"></a><span data-ttu-id="ffc22-102">バックアップと復元のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="ffc22-102">Best Practices for Backup and Restore</span></span>
-   <span data-ttu-id="ffc22-103">**バックアップを作成し、復元プラン**</span><span class="sxs-lookup"><span data-stu-id="ffc22-103">**Create a backup and restore plan**</span></span>  
  
     <span data-ttu-id="ffc22-104">バックアップ プランでは、必ず次の項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="ffc22-104">Be sure your backup plan specifies:</span></span>  
  
    -   <span data-ttu-id="ffc22-105">バックアップの格納先コンピュータ</span><span class="sxs-lookup"><span data-stu-id="ffc22-105">The computer where backups will be stored</span></span>  
  
    -   <span data-ttu-id="ffc22-106">システムのバックアップに使用するプログラム</span><span class="sxs-lookup"><span data-stu-id="ffc22-106">The programs that you will use to back up your system</span></span>  
  
    -   <span data-ttu-id="ffc22-107">バックアップするコンピュータ</span><span class="sxs-lookup"><span data-stu-id="ffc22-107">The computers you want to back up</span></span>  
  
    -   <span data-ttu-id="ffc22-108">バックアップを実行するスケジュール</span><span class="sxs-lookup"><span data-stu-id="ffc22-108">The schedule when backups will occur</span></span>  
  
    -   <span data-ttu-id="ffc22-109">バックアップをアーカイブするオフサイトの場所</span><span class="sxs-lookup"><span data-stu-id="ffc22-109">The offsite location where you will archive backups</span></span>  
  
-   <span data-ttu-id="ffc22-110">**すべての変更の記録を BizTalk Server システムに保持します。**</span><span class="sxs-lookup"><span data-stu-id="ffc22-110">**Keep a written record of all changes to your BizTalk Server system**</span></span>  
  
     <span data-ttu-id="ffc22-111">適用したサービス パック、修正プログラム、QFE など、システムへのすべての変更を必ず記録します。</span><span class="sxs-lookup"><span data-stu-id="ffc22-111">Be sure to write down all changes to your system, such as service packs, hotfixes, and QFEs that have been applied.</span></span> <span data-ttu-id="ffc22-112">できるだけハードウェア障害の発生前に近い状態でシステムを復元するには、このことが不可欠です。</span><span class="sxs-lookup"><span data-stu-id="ffc22-112">This is crucial to getting your system restored as closely as possible to what existed before the hardware failure.</span></span>  
  
-   <span data-ttu-id="ffc22-113">**防止または障害の影響を最小限に抑えるには、次のメジャーを実装します。**</span><span class="sxs-lookup"><span data-stu-id="ffc22-113">**Implement the following measures to help prevent or minimize the effect of a disaster:**</span></span>  
  
    -   <span data-ttu-id="ffc22-114">ソフトウェアおよびファームウェアの更新を利用できるようにしておく。</span><span class="sxs-lookup"><span data-stu-id="ffc22-114">Have your software and firmware updates available.</span></span>  
  
    -   <span data-ttu-id="ffc22-115">すべてのソフトウェア インストール ディスクをすぐに利用できるようにしておく。</span><span class="sxs-lookup"><span data-stu-id="ffc22-115">Have all software installation disks readily available.</span></span> <span data-ttu-id="ffc22-116">これには、専用ドライバーなどのシステム ソフトウェアと、BizTalk Server などのアプリケーション ソフトウェアの両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ffc22-116">This includes both system software such as specialized drivers, and application software such as BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="ffc22-117">サーバーの積極的な監視計画を立てておく。</span><span class="sxs-lookup"><span data-stu-id="ffc22-117">Have a plan to monitor servers proactively.</span></span> <span data-ttu-id="ffc22-118">これは非常に重要です。2 番目のホストでは、障害の発生したホストのオーケストレーション インスタンスを最長で 10 分間、復旧できない場合があるためです。</span><span class="sxs-lookup"><span data-stu-id="ffc22-118">This is very important, since orchestration instances on a failed host may not be recovered by a second host for up to ten minutes.</span></span>  
  
    -   <span data-ttu-id="ffc22-119">ハードウェアの記録をとっておく。</span><span class="sxs-lookup"><span data-stu-id="ffc22-119">Maintain hardware records.</span></span>  
  
    -   <span data-ttu-id="ffc22-120">ソフトウェアの記録をとっておく。</span><span class="sxs-lookup"><span data-stu-id="ffc22-120">Maintain software records.</span></span>  
  
-   <span data-ttu-id="ffc22-121">**ハードウェアまたはソフトウェア レベルで、組織内のフォールト トレランスを実装します。**</span><span class="sxs-lookup"><span data-stu-id="ffc22-121">**Implement fault tolerance in your organization at the hardware or software level**</span></span>  
  
     <span data-ttu-id="ffc22-122">クラスタと RAID (Redundant Array of Independent Disks) を実装することで、ハードウェア障害からシステムを守ることができます。</span><span class="sxs-lookup"><span data-stu-id="ffc22-122">Implementing clusters and redundant array of independent disks (RAID) helps ensure that your system can survive a hardware failure.</span></span>  
  
-   <span data-ttu-id="ffc22-123">**安全な場所に定期的にバックアップ メディアをアーカイブします。**</span><span class="sxs-lookup"><span data-stu-id="ffc22-123">**Archive the backup media on a regular basis in a secure location**</span></span>  
  
     <span data-ttu-id="ffc22-124">バックアップ メディアを定期的にアーカイブするスケジュールを作成し、アーカイブを安全な別の場所に保管します。</span><span class="sxs-lookup"><span data-stu-id="ffc22-124">Create a schedule for archiving your backup media on a regular basis and keep the archives in a secure, offsite location.</span></span> <span data-ttu-id="ffc22-125">こうしておくと、必要なときにバックアップを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ffc22-125">This ensures that you have a backup available when you need it.</span></span>  
  
-   <span data-ttu-id="ffc22-126">**バックアップの整合性を確認し、エラーが発生せず、発生します。**</span><span class="sxs-lookup"><span data-stu-id="ffc22-126">**Verify the integrity of your backups and that they occur without error**</span></span>  
  
     <span data-ttu-id="ffc22-127">すべてのバックアップ ジョブを監視して、完了までにエラーが発生していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ffc22-127">Monitor all of your backup jobs and ensure that they complete without any errors.</span></span>  
  
-   <span data-ttu-id="ffc22-128">**使用可能な予備のハードウェアと同じです。**</span><span class="sxs-lookup"><span data-stu-id="ffc22-128">**Keep identical spare hardware available**</span></span>  
  
     <span data-ttu-id="ffc22-129">同じハードウェアを予備として用意しておくことで、欠陥が見つかったハードウェアをすぐに交換して稼動させることができます。</span><span class="sxs-lookup"><span data-stu-id="ffc22-129">Having identical spare hardware available ensures that you can quickly replace defective hardware to get up-and-running more quickly.</span></span>  
  
-   <span data-ttu-id="ffc22-130">**文書化し、回復手順をテストします。**</span><span class="sxs-lookup"><span data-stu-id="ffc22-130">**Document and test your recovery procedures**</span></span>  
  
     <span data-ttu-id="ffc22-131">システムを実稼働する前には、必ずディザスター リカバリー テストを実施することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ffc22-131">Ideally, disaster recovery testing should be conducted before running your system in production.</span></span> <span data-ttu-id="ffc22-132">適切な計画を立てて事前テストを実施することで、IT スタッフが BizTalk Server システムを確実に復旧できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ffc22-132">Having plans in place and performing prerelease testing will ensure that your IT staff can recover your BizTalk Server systems.</span></span> <span data-ttu-id="ffc22-133">一般に、システム バックアップから実際使用するハードウェアに復元する作業を定期的に試行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffc22-133">This generally means that you must periodically attempt to retore the system backup to the actual hardware you will use</span></span>  
  
-   <span data-ttu-id="ffc22-134">**ディザスター リカバリー手順に関して IT スタッフをトレーニングします。**</span><span class="sxs-lookup"><span data-stu-id="ffc22-134">**Train your IT staff on disaster recovery procedures**</span></span>  
  
     <span data-ttu-id="ffc22-135">システムの復旧が必要な場合に備え、IT スタッフの態勢を整えておきます。</span><span class="sxs-lookup"><span data-stu-id="ffc22-135">Ensure that your IT staff is prepared to recover the system should the need arise.</span></span>  
  
-   <span data-ttu-id="ffc22-136">**テスト環境でのバックアップから復元を演習します。**</span><span class="sxs-lookup"><span data-stu-id="ffc22-136">**Practice restoring from backup in a test environment**</span></span>  
  
     <span data-ttu-id="ffc22-137">テスト環境で BizTalk Server システムの復元を演習し、障害が発生したとき確実に実稼動環境に復元できるようにしておきます。</span><span class="sxs-lookup"><span data-stu-id="ffc22-137">Practice restoring your BizTalk Server system in a test environment to ensure that you can restore it to your production environment if a failure occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffc22-138">参照</span><span class="sxs-lookup"><span data-stu-id="ffc22-138">See Also</span></span>  
 [<span data-ttu-id="ffc22-139">BizTalk Server のバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="ffc22-139">Backing Up and Restoring BizTalk Server</span></span>](../core/backing-up-and-restoring-biztalk-server.md)