---
title: ログ配布 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, log shipping
- log shipping
ms.assetid: 25bc9724-1c99-43d0-8cd1-3ed8eaa60268
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fb0eb7d8c10d8e186f009cda82480490ef0df9e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380554"
---
# <a name="log-shipping"></a><span data-ttu-id="f7ab4-102">ログ配布</span><span class="sxs-lookup"><span data-stu-id="f7ab4-102">Log Shipping</span></span>
<span data-ttu-id="f7ab4-103">ログ配布は、ダウンタイムを短縮する、システム障害が発生した場合、ウォーム バックアップとも呼ばれるスタンバイ サーバーの機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="f7ab4-103">Log shipping provides standby server capabilities, sometimes called a warm backup, which reduces downtime in the event of a system failure.</span></span>  
  
 <span data-ttu-id="f7ab4-104">分散データベース設計が[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]あります間で同期させる特定のバックアップを作成するときに、バックアップを復元できます をポイントします。</span><span class="sxs-lookup"><span data-stu-id="f7ab4-104">Due to the distributed database design of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], when you produce backups you must be certain to provide a consistent point to which the backups can be restored.</span></span> <span data-ttu-id="f7ab4-105">トランザクションが複数のデータベースにまたがることができます。場合、1 つのデータベースがオフラインになり、復元する必要がありますし、関連のすべてのデータベース復元しなければなりません 1 つのポイントでシステムが一貫性のある状態であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f7ab4-105">Transactions can span multiple databases; if one database goes offline and must be restored, then all related databases must be restored to a single point in time to ensure that the system is in a consistent state.</span></span> <span data-ttu-id="f7ab4-106">すべてのデータベースは、分散トランザクションに参加します。</span><span class="sxs-lookup"><span data-stu-id="f7ab4-106">Not all databases participate in distributed transactions.</span></span> <span data-ttu-id="f7ab4-107">詳細については、次を参照してください。[バックアップと、BizTalk Server データベースを復元](../core/backing-up-and-restoring-the-biztalk-server-databases.md)します。</span><span class="sxs-lookup"><span data-stu-id="f7ab4-107">For more information, see [Backing Up and Restoring the BizTalk Server Databases](../core/backing-up-and-restoring-the-biztalk-server-databases.md).</span></span>  
  
 <span data-ttu-id="f7ab4-108">Microsoft SQL Server のログ マーキングを使用してデータベースのバックアップ セットを生成する自動プロセスを提供する BizTalk Server のバックアップ ジョブ。</span><span class="sxs-lookup"><span data-stu-id="f7ab4-108">The Backup BizTalk Server job uses Microsoft SQL Server log marking to provide an automated process that produces database backup sets.</span></span> <span data-ttu-id="f7ab4-109">これらのバックアップ セットには、復元プロセス中に使用する同期ポイントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f7ab4-109">These backup sets include synchronized points that are used during the restoration process.</span></span> <span data-ttu-id="f7ab4-110">BizTalk Server のバックアップ ジョブによって生成されたデータベースのセットを復元するプロセスの一環として、各データベースの前回のログ バックアップ ファイルは、2 番目の最後の記号を使用して、特定のログ マークに復元されます。</span><span class="sxs-lookup"><span data-stu-id="f7ab4-110">As part of the process of restoring a set of databases produced by the Backup BizTalk Server job, the last log backup file for each database is restored to a specific log mark, using the second to last mark.</span></span> <span data-ttu-id="f7ab4-111">これにより、データベースを一貫性のある状態に復元し、失われたデータの量を大幅に短縮することができます。</span><span class="sxs-lookup"><span data-stu-id="f7ab4-111">This enables you to restore your databases to a consistent state and significantly reduce the amount of data lost.</span></span> <span data-ttu-id="f7ab4-112">ログ マーク前に、最後の 1 つを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7ab4-112">The log mark before the last one should be used.</span></span> <span data-ttu-id="f7ab4-113">SQL Server には、ログ配布機能が含まれますが、のみをバックアップして、BizTalk Server データベースを復元するときの BizTalk Server ログ配布機能を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7ab4-113">Although SQL Server includes a log shipping feature, you should only use the BizTalk Server log shipping feature when backing up and restoring BizTalk Server databases.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7ab4-114">使用するため、SQL Server 単純復旧モデルがサポートされていません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを単純復旧モデル、トランザクション ログをバックアップできませんし、そのため、最新のバックアップ以降のアクティビティのレコードを保持はしないためです。</span><span class="sxs-lookup"><span data-stu-id="f7ab4-114">The SQL Server simple recovery model is not supported for use with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases because the simple recovery model does not backup the transaction log and therefore does not maintain a record of activity since the most recent backup.</span></span>  <span data-ttu-id="f7ab4-115">内のデータの整合性を確保する、完全復旧モデルを使用する SQL Server を構成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース バックアップ セットです。</span><span class="sxs-lookup"><span data-stu-id="f7ab4-115">Configure SQL Server to use the full recovery model to ensure the integrity of data in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database backup sets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7ab4-116">参照</span><span class="sxs-lookup"><span data-stu-id="f7ab4-116">See Also</span></span>  
 [<span data-ttu-id="f7ab4-117">バックアップおよび復元に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="f7ab4-117">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)