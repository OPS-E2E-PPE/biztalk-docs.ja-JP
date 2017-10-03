---
title: "バックアップと復元の BizTalk Server |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe03a75a-1ea6-4ccc-9543-7989ec6b1cff
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1adac25b23c69b51e07ed5f30768d046a453887a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="backing-up-and-restoring-biztalk-server"></a><span data-ttu-id="fd198-102">BizTalk Server のバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="fd198-102">Backing Up and Restoring BizTalk Server</span></span>
<span data-ttu-id="fd198-103">ハードウェアに障害が発生した場合に備えて、BizTalk Server のデータベースとコンポーネントの適切なバックアップを取っておくことは、必須の作業です。</span><span class="sxs-lookup"><span data-stu-id="fd198-103">In the event of hardware failure, having a good backup of your BizTalk Server databases and components is essential.</span></span> <span data-ttu-id="fd198-104">適切なバックアップを用意しておけば、データの損失を最小限にとどめて障害から回復することができます。</span><span class="sxs-lookup"><span data-stu-id="fd198-104">A good backup will enable you to recover with little or no data loss.</span></span> <span data-ttu-id="fd198-105">BizTalk Server をどのように復元するかは、ハードウェア障害が発生したシステムにインストールされているコンポーネントによって異なります。</span><span class="sxs-lookup"><span data-stu-id="fd198-105">How you restore BizTalk Server depends on which components were installed on the system where hardware failure occurred.</span></span> <span data-ttu-id="fd198-106">ここでは、次のようなハードウェア障害が発生した場合を想定します。</span><span class="sxs-lookup"><span data-stu-id="fd198-106">This guide covers the following hardware failure scenarios:</span></span>  
  
 <span data-ttu-id="fd198-107">**BizTalk Server を実行しているコンピューターでのハードウェア障害**</span><span class="sxs-lookup"><span data-stu-id="fd198-107">**Hardware failure in the computer running BizTalk Server**</span></span>  
  
 <span data-ttu-id="fd198-108">BizTalk Server を実行しているコンピュータでハードウェア障害が発生した場合、BizTalk グループが高可用性を意図して設計されていないと、システムのダウンタイムやパフォーマンスの低下が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fd198-108">A hardware failure in the computer running BizTalk Server may cause system downtime or degraded performance if the BizTalk group is not designed for high availability.</span></span> <span data-ttu-id="fd198-109">高可用性の BizTalk グループを作成する方法の詳細については、次を参照してください。[高可用性の計画](../core/planning-for-high-availability3.md)です。</span><span class="sxs-lookup"><span data-stu-id="fd198-109">For more information about how to create a highly available BizTalk group, see [Planning for High Availability](../core/planning-for-high-availability3.md).</span></span>  
  
 <span data-ttu-id="fd198-110">ハードウェア障害が発生した後、BizTalk Server を別のコンピュータで実行できるようにするには、最初のコンピュータの BizTalk Server コンポーネントをバックアップしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd198-110">To ensure that you can replace a computer running BizTalk Server after a hardware failure, you must back up the BizTalk Server components on that computer.</span></span> <span data-ttu-id="fd198-111">バックアップし、BizTalk Server を実行しているコンピューターを復元する方法の詳細については、次を参照してください。 [、コンピューターを実行している BizTalk Server のバックアップ](../core/backing-up-a-computer-running-biztalk-server.md)と[BizTalk Server を実行しているコンピューターを回復する](../core/recovering-a-computer-running-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="fd198-111">For more information about how to back up and restore a computer running BizTalk Server, see [Backing Up a Computer Running BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md) and [Recovering a Computer Running BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="fd198-112">**SQL Server を実行しているコンピューターでのハードウェア障害**</span><span class="sxs-lookup"><span data-stu-id="fd198-112">**Hardware failure in the computer running SQL Server**</span></span>  
  
 <span data-ttu-id="fd198-113">SQL Server クラスタリングを使用すると、SQL Server を実行しているコンピュータでハードウェア障害が発生した場合のリスクを最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="fd198-113">You can minimize the risk of a hardware failure in a computer running SQL Server by using SQL Server clustering.</span></span> <span data-ttu-id="fd198-114">ただし、SQL Server クラスタリングを使用していても、BizTalk Server データベースを格納している SQL Server で回復できないハードウェア障害が発生することもあります。</span><span class="sxs-lookup"><span data-stu-id="fd198-114">Even when using SQL Server clustering, however, there may be situations when the SQL server(s) containing the BizTalk Server databases experiences an unrecoverable hardware failure.</span></span> <span data-ttu-id="fd198-115">たとえば、データ層全体に障害が発生した場合などは、</span><span class="sxs-lookup"><span data-stu-id="fd198-115">For example, the entire data tier suffered a failure.</span></span> <span data-ttu-id="fd198-116">最新のバックアップ データベースを復元して、BizTalk グループを回復します。</span><span class="sxs-lookup"><span data-stu-id="fd198-116">In these situations, you must revive the BizTalk group by restoring the most recent set of backed up databases.</span></span>  
  
 <span data-ttu-id="fd198-117">詳細については、BizTalk Server データベースのフォールト トレランスを提供する、次を参照してください。 [BizTalk Server データベースの高可用性の実現](../core/providing-high-availability-for-biztalk-server-databases.md)です。</span><span class="sxs-lookup"><span data-stu-id="fd198-117">For more information about providing fault tolerance for the BizTalk Server databases, see [Providing High Availability for BizTalk Server Databases](../core/providing-high-availability-for-biztalk-server-databases.md).</span></span> <span data-ttu-id="fd198-118">ダウンタイムが発生した致命的な SQL Server の障害の場合の手順に従ってください[をバックアップおよび BizTalk Server データベースの復元](../core/backing-up-and-restoring-the-biztalk-server-databases.md)です。</span><span class="sxs-lookup"><span data-stu-id="fd198-118">In the case of a catastrophic SQL Server failure where downtime has occurred, you should follow the instructions in [Backing Up and Restoring the BizTalk Server Databases](../core/backing-up-and-restoring-the-biztalk-server-databases.md).</span></span>  
  
 <span data-ttu-id="fd198-119">SQL Server と BizTalk Server の両方がインストールされているコンピュータでハードウェア障害が発生した場合は、BizTalk Server データベースを復元した後、BizTalk Server コンポーネントを復元してください。</span><span class="sxs-lookup"><span data-stu-id="fd198-119">If you experience a hardware failure on a computer where both SQL Server and BizTalk Server are installed, you should restore the BizTalk Server databases, and then recover the BizTalk Server components.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fd198-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="fd198-120">In This Section</span></span>  
  
-   [<span data-ttu-id="fd198-121">チェックリスト: バックアップと復元</span><span class="sxs-lookup"><span data-stu-id="fd198-121">Checklist: Backup and Restore</span></span>](../core/checklist-backup-and-restore.md)  
  
-   [<span data-ttu-id="fd198-122">バックアップと復元のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="fd198-122">Best Practices for Backup and Restore</span></span>](../core/best-practices-for-backup-and-restore.md)  
  
-   [<span data-ttu-id="fd198-123">バックアップと、BizTalk Server データベースの復元</span><span class="sxs-lookup"><span data-stu-id="fd198-123">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="fd198-124">BizTalk Server を実行しているコンピューターの災害復旧</span><span class="sxs-lookup"><span data-stu-id="fd198-124">Disaster Recovery for Computers Running BizTalk Server</span></span>](../core/disaster-recovery-for-computers-running-biztalk-server.md)  
  
-   [<span data-ttu-id="fd198-125">BizTalk Server を実行しているコンピューターのバックアップ</span><span class="sxs-lookup"><span data-stu-id="fd198-125">Backing Up a Computer Running BizTalk Server</span></span>](../core/backing-up-a-computer-running-biztalk-server.md)  
  
-   [<span data-ttu-id="fd198-126">BizTalk Server を実行しているコンピューターの回復</span><span class="sxs-lookup"><span data-stu-id="fd198-126">Recovering a Computer Running BizTalk Server</span></span>](../core/recovering-a-computer-running-biztalk-server.md)