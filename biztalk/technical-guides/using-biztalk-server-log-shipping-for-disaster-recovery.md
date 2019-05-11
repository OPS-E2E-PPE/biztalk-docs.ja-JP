---
title: BizTalk Server ログ配布のディザスター リカバリーを使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d65015c-de53-4590-b644-5c2f66f763db
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9dc2ab707bb4620fdb4b45db2750514758f21300
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400357"
---
# <a name="using-biztalk-server-log-shipping-for-disaster-recovery"></a><span data-ttu-id="90c18-102">BizTalk Server ログ配布のディザスター リカバリーを使用します。</span><span class="sxs-lookup"><span data-stu-id="90c18-102">Using BizTalk Server Log Shipping for Disaster Recovery</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="90c18-103">実装は、データベースを使用してスタンバイの機能をデータベース ログ配布します。</span><span class="sxs-lookup"><span data-stu-id="90c18-103">implements database standby capabilities through the use of database log shipping.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="90c18-104">ログ配布は、バックアップと、スタンバイ サーバー データベースが実稼働データベース サーバーが失敗したことに処理を再開できるように、データベースとトランザクション ログ ファイルの復元を自動化します。</span><span class="sxs-lookup"><span data-stu-id="90c18-104">log shipping automates the backup and restore of database and transaction log files, allowing a standby server to resume database processing in the event that the production database server fails.</span></span>  
  
## <a name="how-log-shipping-works"></a><span data-ttu-id="90c18-105">どのログ配布のしくみ</span><span class="sxs-lookup"><span data-stu-id="90c18-105">How Log Shipping Works</span></span>  
 <span data-ttu-id="90c18-106">[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]によって使用されるエージェント ジョブ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のログ配布は、実稼働環境で使用するソース サーバーと (BizTalk Server のバックアップ ジョブで実行するすべての時刻) を既定で 15 分ごと、スタンバイ状態として使用する移行先サーバーの間でデータを同期します。</span><span class="sxs-lookup"><span data-stu-id="90c18-106">The [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent jobs used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for log shipping synchronize data between the source server used in production and the destination server used as a standby every 15 minutes by default (every time that the Backup BizTalk Server job runs).</span></span>  
  
## <a name="using-log-shipping-for-disaster-recovery"></a><span data-ttu-id="90c18-107">ディザスター リカバリーのログ配布を使用します。</span><span class="sxs-lookup"><span data-stu-id="90c18-107">Using Log Shipping for Disaster Recovery</span></span>  
 <span data-ttu-id="90c18-108">使用する場合、次の操作[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ ディザスター リカバリーのための配布。</span><span class="sxs-lookup"><span data-stu-id="90c18-108">Do the following when using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping for disaster recovery:</span></span>  
  
- <span data-ttu-id="90c18-109">トピックの手順に従って[チェックリスト。ディザスター リカバリーによる可用性の向上](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)、運用環境の可用性を向上させる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ディザスター リカバリーを使用して環境。</span><span class="sxs-lookup"><span data-stu-id="90c18-109">Follow the steps in the topic [Checklist: Increasing Availability with Disaster Recovery](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md) to increase availability of a production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment using disaster recovery.</span></span>  
  
- <span data-ttu-id="90c18-110">ディザスター リカバリー server に運用環境の負荷を処理する能力があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="90c18-110">Verify that the disaster recovery servers have the capacity to handle production load.</span></span>  
  
   <span data-ttu-id="90c18-111">スタンバイ サーバーに、同じまたは類似した使用可能なリソース (CPU/メモリ/ディスク) として、運用サーバーがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="90c18-111">Ensure that the standby servers have the same or similar resources available (CPU/memory/disk) as the production servers.</span></span>  
  
- <span data-ttu-id="90c18-112">ディザスター リカバリ ルーチンの詳細がも記載されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="90c18-112">Ensure that the specifics of your disaster recovery routine are well documented.</span></span>  
  
   <span data-ttu-id="90c18-113">障害復旧の準備、実装の詳細の各手順を文書化します。</span><span class="sxs-lookup"><span data-stu-id="90c18-113">Document every step of your disaster recovery preparation and implementation in detail.</span></span> <span data-ttu-id="90c18-114">Strikes 都合の良いときがディザスター リカバリーの手順を実装するために必要な責任は、最初の日の開始されていると仮定ため頻度の低いディザスターは動作し、最初にこれが。</span><span class="sxs-lookup"><span data-stu-id="90c18-114">Disaster seldom strikes when it is convenient so assume that the parties responsible for implementing the disaster recovery procedure are starting their first day of work and will be doing this for the first time.</span></span>  
  
- <span data-ttu-id="90c18-115">ディザスター リカバリー サイトに通常のテスト、実際にフェールオーバーの一環として、新しい BizTalk として特にアプリケーションが配置実稼働環境でします。</span><span class="sxs-lookup"><span data-stu-id="90c18-115">As part of regular testing, practice failover to the disaster recovery site, especially as new BizTalk applications are put in production.</span></span>  
  
   <span data-ttu-id="90c18-116">通常のテストとスムーズに実行することができますを確認するためのメンテナンスの一部としてテスト フェールオーバーを実行します。</span><span class="sxs-lookup"><span data-stu-id="90c18-116">Perform failover testing as a part of regular testing and maintenance to ensure that it can be performed smoothly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90c18-117">参照</span><span class="sxs-lookup"><span data-stu-id="90c18-117">See Also</span></span>  
 [<span data-ttu-id="90c18-118">ディザスター リカバリー</span><span class="sxs-lookup"><span data-stu-id="90c18-118">Disaster Recovery</span></span>](../technical-guides/disaster-recovery.md)