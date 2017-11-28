---
title: "BizTalk Server のログ配布災害復旧を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d65015c-de53-4590-b644-5c2f66f763db
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16f2cf9e1d8b717ff42536ef9c0dba79132b9663
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-biztalk-server-log-shipping-for-disaster-recovery"></a><span data-ttu-id="d9dba-102">BizTalk Server のログ配布災害復旧を使用します。</span><span class="sxs-lookup"><span data-stu-id="d9dba-102">Using BizTalk Server Log Shipping for Disaster Recovery</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d9dba-103">実装してデータベースのデータベースを使用してスタンバイ機能ログ配布します。</span><span class="sxs-lookup"><span data-stu-id="d9dba-103"> implements database standby capabilities through the use of database log shipping.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d9dba-104">ログ配布は、スタンバイ サーバーで実稼働データベース サーバーが失敗した場合に、データベース処理を再開できるように、データベースとトランザクション ログ ファイルの復元とバックアップを自動化します。</span><span class="sxs-lookup"><span data-stu-id="d9dba-104"> log shipping automates the backup and restore of database and transaction log files, allowing a standby server to resume database processing in the event that the production database server fails.</span></span>  
  
## <a name="how-log-shipping-works"></a><span data-ttu-id="d9dba-105">どのログ配布のしくみ</span><span class="sxs-lookup"><span data-stu-id="d9dba-105">How Log Shipping Works</span></span>  
 <span data-ttu-id="d9dba-106">[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]によって使用されるエージェント ジョブ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のログ配布は、実稼働環境で使用されている移行元サーバーと既定 (BizTalk Server のバックアップ ジョブで実行するすべての時刻) では 15 分ごと、スタンバイ状態として使用する移行先サーバー間でデータを同期します。</span><span class="sxs-lookup"><span data-stu-id="d9dba-106">The [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for log shipping synchronize data between the source server used in production and the destination server used as a standby every 15 minutes by default (every time that the Backup BizTalk Server job runs).</span></span>  
  
## <a name="using-log-shipping-for-disaster-recovery"></a><span data-ttu-id="d9dba-107">ログ配布の障害復旧の使用</span><span class="sxs-lookup"><span data-stu-id="d9dba-107">Using Log Shipping for Disaster Recovery</span></span>  
 <span data-ttu-id="d9dba-108">使用する場合、次の操作を[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ災害復旧のための配布。</span><span class="sxs-lookup"><span data-stu-id="d9dba-108">Do the following when using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping for disaster recovery:</span></span>  
  
-   <span data-ttu-id="d9dba-109">トピックの手順に従って[チェックリスト: 可用性と災害復旧を増やす](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)、稼働環境の可用性を向上させる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]災害復旧を使用して環境。</span><span class="sxs-lookup"><span data-stu-id="d9dba-109">Follow the steps in the topic [Checklist: Increasing Availability with Disaster Recovery](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md) to increase availability of a production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment using disaster recovery.</span></span>  
  
-   <span data-ttu-id="d9dba-110">障害回復サーバーに実稼働負荷を処理する能力があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9dba-110">Verify that the disaster recovery servers have the capacity to handle production load.</span></span>  
  
     <span data-ttu-id="d9dba-111">スタンバイ サーバーが、同一または類似した使用可能なリソース (CPU とメモリまたはディスク) として、実稼働サーバーであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9dba-111">Ensure that the standby servers have the same or similar resources available (CPU/memory/disk) as the production servers.</span></span>  
  
-   <span data-ttu-id="d9dba-112">災害復旧ルーチンの詳細が明確になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9dba-112">Ensure that the specifics of your disaster recovery routine are well documented.</span></span>  
  
     <span data-ttu-id="d9dba-113">障害復旧の準備、実装の詳細のすべてのステップを文書化します。</span><span class="sxs-lookup"><span data-stu-id="d9dba-113">Document every step of your disaster recovery preparation and implementation in detail.</span></span> <span data-ttu-id="d9dba-114">ストライキ都合の良いときが障害復旧手順を実装する責任者が、最初の曜日を開始するいると仮定ため頻度の低い災害は作業し、初めてこれでは。</span><span class="sxs-lookup"><span data-stu-id="d9dba-114">Disaster seldom strikes when it is convenient so assume that the parties responsible for implementing the disaster recovery procedure are starting their first day of work and will be doing this for the first time.</span></span>  
  
-   <span data-ttu-id="d9dba-115">障害復旧サイトに通常のテスト、プラクティス フェールオーバーの一環として、新しい BizTalk として特にアプリケーションが配置実稼働環境でします。</span><span class="sxs-lookup"><span data-stu-id="d9dba-115">As part of regular testing, practice failover to the disaster recovery site, especially as new BizTalk applications are put in production.</span></span>  
  
     <span data-ttu-id="d9dba-116">正規のテストとスムーズに実行できることができることを確認するためのメンテナンスの一環としてテスト フェールオーバーを実行します。</span><span class="sxs-lookup"><span data-stu-id="d9dba-116">Perform failover testing as a part of regular testing and maintenance to ensure that it can be performed smoothly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9dba-117">参照</span><span class="sxs-lookup"><span data-stu-id="d9dba-117">See Also</span></span>  
 [<span data-ttu-id="d9dba-118">災害復旧</span><span class="sxs-lookup"><span data-stu-id="d9dba-118">Disaster Recovery</span></span>](../technical-guides/disaster-recovery.md)