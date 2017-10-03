---
title: "ログ配布 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up, log shipping
- log shipping
ms.assetid: 25bc9724-1c99-43d0-8cd1-3ed8eaa60268
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bd90e23fc99988bb134a77befe3195ca507037d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="log-shipping"></a><span data-ttu-id="7a50a-102">ログ配布</span><span class="sxs-lookup"><span data-stu-id="7a50a-102">Log Shipping</span></span>
<span data-ttu-id="7a50a-103">ログ配布は、システム障害時のダウンタイムを短縮することを目的とした、スタンバイ サーバーの機能です。ウォーム バックアップと呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="7a50a-103">Log shipping provides standby server capabilities, sometimes called a warm backup, which reduces downtime in the event of a system failure.</span></span>  
  
 <span data-ttu-id="7a50a-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には分散データベース設計が採用されているため、バックアップを作成する際は、その復元ポイントをデータベース間で同期させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a50a-104">Due to the distributed database design of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], when you produce backups you must be certain to provide a consistent point to which the backups can be restored.</span></span> <span data-ttu-id="7a50a-105">トランザクションは、複数のデータベースにまたがる場合もあります。いずれか 1 つのデータベースで障害が発生し、復元する必要が生じた場合、関連するすべてのデータベースを特定のポイントまで復元しないと、システムの一貫した状態を維持することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="7a50a-105">Transactions can span multiple databases; if one database goes offline and must be restored, then all related databases must be restored to a single point in time to ensure that the system is in a consistent state.</span></span> <span data-ttu-id="7a50a-106">ただし、必ずしもすべてのデータベースが分散トランザクションに参加しているとは限りません。</span><span class="sxs-lookup"><span data-stu-id="7a50a-106">Not all databases participate in distributed transactions.</span></span> <span data-ttu-id="7a50a-107">詳細については、次を参照してください。[をバックアップおよび BizTalk Server データベースの復元](../core/backing-up-and-restoring-the-biztalk-server-databases.md)です。</span><span class="sxs-lookup"><span data-stu-id="7a50a-107">For more information, see [Backing Up and Restoring the BizTalk Server Databases](../core/backing-up-and-restoring-the-biztalk-server-databases.md).</span></span>  
  
 <span data-ttu-id="7a50a-108">BizTalk Server のバックアップ ジョブでは、データベースのバックアップ セットを生成するプロセスを自動化するために、Microsoft SQL Server のログ マーキング機能を使用しています。</span><span class="sxs-lookup"><span data-stu-id="7a50a-108">The Backup BizTalk Server job uses Microsoft SQL Server log marking to provide an automated process that produces database backup sets.</span></span> <span data-ttu-id="7a50a-109">バックアップ セットには、同期された復元ポイントが定義されています。</span><span class="sxs-lookup"><span data-stu-id="7a50a-109">These backup sets include synchronized points that are used during the restoration process.</span></span> <span data-ttu-id="7a50a-110">BizTalk Server のバックアップ ジョブによって生成された一連のデータベースを復元するプロセスでは、各データベースの最後のログ バックアップ ファイルが、特定のログ マーク (最後から 2 番目のマーク) まで復元されます。</span><span class="sxs-lookup"><span data-stu-id="7a50a-110">As part of the process of restoring a set of databases produced by the Backup BizTalk Server job, the last log backup file for each database is restored to a specific log mark, using the second to last mark.</span></span> <span data-ttu-id="7a50a-111">これにより、各データベースの状態が確実に復元され、データの損失を最小限に抑えることが可能となります。</span><span class="sxs-lookup"><span data-stu-id="7a50a-111">This enables you to restore your databases to a consistent state and significantly reduce the amount of data lost.</span></span> <span data-ttu-id="7a50a-112">重要なことは、最後から 2 番目のログ マークが使用されるという点です。</span><span class="sxs-lookup"><span data-stu-id="7a50a-112">The log mark before the last one should be used.</span></span> <span data-ttu-id="7a50a-113">ログ配布機能は SQL Server にも備わっていますが、BizTalk Server のデータベースをバックアップおよび復元する場合は、BizTalk Server のログ配布機能のみを使用してください。</span><span class="sxs-lookup"><span data-stu-id="7a50a-113">Although SQL Server includes a log shipping feature, you should only use the BizTalk Server log shipping feature when backing up and restoring BizTalk Server databases.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a50a-114">単純復旧モデルはトランザクション ログをバックアップせず、したがって最新のバックアップ以降のアクティビティの記録を保持していないので、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースでの SQL Server 単純復旧モデルの使用はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="7a50a-114">The SQL Server simple recovery model is not supported for use with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases because the simple recovery model does not backup the transaction log and therefore does not maintain a record of activity since the most recent backup.</span></span>  <span data-ttu-id="7a50a-115">完全復旧モデルを使用するように SQL Server を構成して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベース バックアップ セットのデータの整合性を確保します。</span><span class="sxs-lookup"><span data-stu-id="7a50a-115">Configure SQL Server to use the full recovery model to ensure the integrity of data in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database backup sets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a50a-116">参照</span><span class="sxs-lookup"><span data-stu-id="7a50a-116">See Also</span></span>  
 [<span data-ttu-id="7a50a-117">バックアップと復元に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="7a50a-117">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)