---
title: バックアップと復元の BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe03a75a-1ea6-4ccc-9543-7989ec6b1cff
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b04e6db4a125b2c90e3417c53d77b10e06f63ac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358680"
---
# <a name="backing-up-and-restoring-biztalk-server"></a><span data-ttu-id="112e7-102">BizTalk Server のバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="112e7-102">Backing Up and Restoring BizTalk Server</span></span>
<span data-ttu-id="112e7-103">ハードウェアの障害が発生した場合、BizTalk Server データベースとコンポーネントの適切なバックアップを取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="112e7-103">In the event of hardware failure, having a good backup of your BizTalk Server databases and components is essential.</span></span> <span data-ttu-id="112e7-104">ほとんどまたはまったくデータの損失を回復する適切なバックアップが有効になりません。</span><span class="sxs-lookup"><span data-stu-id="112e7-104">A good backup will enable you to recover with little or no data loss.</span></span> <span data-ttu-id="112e7-105">BizTalk Server を復元する方法は、ハードウェア障害が発生したシステムにインストールするコンポーネントに依存します。</span><span class="sxs-lookup"><span data-stu-id="112e7-105">How you restore BizTalk Server depends on which components were installed on the system where hardware failure occurred.</span></span> <span data-ttu-id="112e7-106">このガイドでは、次のハードウェア障害のシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="112e7-106">This guide covers the following hardware failure scenarios:</span></span>  
  
 <span data-ttu-id="112e7-107">**BizTalk Server を実行しているコンピューターでのハードウェア障害**</span><span class="sxs-lookup"><span data-stu-id="112e7-107">**Hardware failure in the computer running BizTalk Server**</span></span>  
  
 <span data-ttu-id="112e7-108">BizTalk Server を実行しているコンピューターでハードウェア障害は、システムのダウンタイムが発生する可能性があります。 または高可用性のため、BizTalk グループが設計されていない場合は、パフォーマンスを低下します。</span><span class="sxs-lookup"><span data-stu-id="112e7-108">A hardware failure in the computer running BizTalk Server may cause system downtime or degraded performance if the BizTalk group is not designed for high availability.</span></span> <span data-ttu-id="112e7-109">高可用性の BizTalk グループを作成する方法の詳細については、次を参照してください。[高可用性の計画](../core/planning-for-high-availability3.md)します。</span><span class="sxs-lookup"><span data-stu-id="112e7-109">For more information about how to create a highly available BizTalk group, see [Planning for High Availability](../core/planning-for-high-availability3.md).</span></span>  
  
 <span data-ttu-id="112e7-110">ハードウェア障害の後に BizTalk Server を実行するコンピューターを置換できることを確認するには、そのコンピューターで、BizTalk Server コンポーネントをバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="112e7-110">To ensure that you can replace a computer running BizTalk Server after a hardware failure, you must back up the BizTalk Server components on that computer.</span></span> <span data-ttu-id="112e7-111">バックアップを作成して、BizTalk Server を実行しているコンピューターを復元する方法の詳細については、次を参照してください。 [、コンピューターを実行している BizTalk Server のバックアップ](../core/backing-up-a-computer-running-biztalk-server.md)と[BizTalk Server を実行しているコンピューターを回復する](../core/recovering-a-computer-running-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="112e7-111">For more information about how to back up and restore a computer running BizTalk Server, see [Backing Up a Computer Running BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md) and [Recovering a Computer Running BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="112e7-112">**SQL Server を実行しているコンピューターでのハードウェア障害**</span><span class="sxs-lookup"><span data-stu-id="112e7-112">**Hardware failure in the computer running SQL Server**</span></span>  
  
 <span data-ttu-id="112e7-113">SQL Server クラスタ リングを使用して SQL Server を実行するコンピューターのハードウェア障害のリスクを最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="112e7-113">You can minimize the risk of a hardware failure in a computer running SQL Server by using SQL Server clustering.</span></span> <span data-ttu-id="112e7-114">SQL Server クラスタ リングを使用する場合にもただし、ある可能性がありますの場合、BizTalk Server データベースを格納している SQL server を復旧不可能なハードウェア障害が発生したときにします。</span><span class="sxs-lookup"><span data-stu-id="112e7-114">Even when using SQL Server clustering, however, there may be situations when the SQL server(s) containing the BizTalk Server databases experiences an unrecoverable hardware failure.</span></span> <span data-ttu-id="112e7-115">たとえば、全体のデータ層は、障害を検出しました。</span><span class="sxs-lookup"><span data-stu-id="112e7-115">For example, the entire data tier suffered a failure.</span></span> <span data-ttu-id="112e7-116">このような場合は、最新のバックアップされたデータベースのセットを復元することで、BizTalk グループを回復する必要があります。</span><span class="sxs-lookup"><span data-stu-id="112e7-116">In these situations, you must revive the BizTalk group by restoring the most recent set of backed up databases.</span></span>  
  
 <span data-ttu-id="112e7-117">フォールト トレランスを提供する BizTalk Server データベースの詳細については、次を参照してください。 [BizTalk Server データベースの高可用性の実現](../core/providing-high-availability-for-biztalk-server-databases.md)します。</span><span class="sxs-lookup"><span data-stu-id="112e7-117">For more information about providing fault tolerance for the BizTalk Server databases, see [Providing High Availability for BizTalk Server Databases](../core/providing-high-availability-for-biztalk-server-databases.md).</span></span> <span data-ttu-id="112e7-118">場合は、ダウンタイムが発生した SQL Server の致命的なエラーには」の手順に従う必要があります[バックアップと、BizTalk Server データベースを復元](../core/backing-up-and-restoring-the-biztalk-server-databases.md)します。</span><span class="sxs-lookup"><span data-stu-id="112e7-118">In the case of a catastrophic SQL Server failure where downtime has occurred, you should follow the instructions in [Backing Up and Restoring the BizTalk Server Databases](../core/backing-up-and-restoring-the-biztalk-server-databases.md).</span></span>  
  
 <span data-ttu-id="112e7-119">SQL Server と BizTalk Server の両方がインストールされているコンピューターでハードウェア障害が発生した場合、BizTalk Server データベースを復元し、BizTalk Server コンポーネントを回復しください。</span><span class="sxs-lookup"><span data-stu-id="112e7-119">If you experience a hardware failure on a computer where both SQL Server and BizTalk Server are installed, you should restore the BizTalk Server databases, and then recover the BizTalk Server components.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="112e7-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="112e7-120">In This Section</span></span>  
  
-   [<span data-ttu-id="112e7-121">チェックリスト:バックアップと復元</span><span class="sxs-lookup"><span data-stu-id="112e7-121">Checklist: Backup and Restore</span></span>](../core/checklist-backup-and-restore.md)  
  
-   [<span data-ttu-id="112e7-122">バックアップおよび復元のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="112e7-122">Best Practices for Backup and Restore</span></span>](../core/best-practices-for-backup-and-restore.md)  
  
-   [<span data-ttu-id="112e7-123">BizTalk Server データベースのバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="112e7-123">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="112e7-124">BizTalk Server を実行しているコンピューターのディザスター リカバリー</span><span class="sxs-lookup"><span data-stu-id="112e7-124">Disaster Recovery for Computers Running BizTalk Server</span></span>](../core/disaster-recovery-for-computers-running-biztalk-server.md)  
  
-   [<span data-ttu-id="112e7-125">BizTalk Server を実行しているコンピューターのバックアップ</span><span class="sxs-lookup"><span data-stu-id="112e7-125">Backing Up a Computer Running BizTalk Server</span></span>](../core/backing-up-a-computer-running-biztalk-server.md)  
  
-   [<span data-ttu-id="112e7-126">BizTalk Server を実行しているコンピューターの復旧</span><span class="sxs-lookup"><span data-stu-id="112e7-126">Recovering a Computer Running BizTalk Server</span></span>](../core/recovering-a-computer-running-biztalk-server.md)