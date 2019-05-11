---
title: BAM 分析および Tracking Analysis Server データベースをバックアップする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, DTS packages
- backing up [BAM], Tracking Analysis Server database
- backing up [BAM], OLAP cubes
- backing up [BAM], DTS packages
- purging, OLAP cubes
- Analysis database [BAM], backing up
- scheduling, BAM backups
- backing up [BAM], Analysis database
- OLAP cubes, purging
- backing up, BAM
- backing up [BAM], database order
- DTS packages, backing up
- backing up [BAM], Star Schema database
- backing up [BAM], scheduling
- Tracking Analysis Server database [BAM], backing up
- Star Schema database [BAM], backing up
ms.assetid: d39e3491-ab54-44f2-990a-7b8ee86f0501
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2fdd707375404f26f9310c6c2d38a6f2dfcb4ae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387115"
---
# <a name="how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases"></a><span data-ttu-id="5a60d-102">BAM 分析データベースおよび Tracking Analysis Server データベースをバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="5a60d-102">How to Back Up the BAM Analysis and Tracking Analysis Server Databases</span></span>
<span data-ttu-id="5a60d-103">ビジネス アクティビティ監視 (BAM) 分析データベースおよび Tracking Analysis Server データベースは、SQL Server Analysis Services キューブにコンテンツを保存します。</span><span class="sxs-lookup"><span data-stu-id="5a60d-103">The Business Activity Monitoring (BAM) Analysis database and the Tracking Analysis Server database store content in SQL Server Analysis Services cubes.</span></span> <span data-ttu-id="5a60d-104">BizTalk Server のバックアップ ジョブでは、これらのデータベースをバックアップしません。</span><span class="sxs-lookup"><span data-stu-id="5a60d-104">The Backup BizTalk Server job does not back up these databases.</span></span> <span data-ttu-id="5a60d-105">代わりに、これらのデータベースをバックアップするには、SQL Server 分析マネージャを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a60d-105">Instead, to backup these databases, you must use SQL Server Analysis Manager.</span></span>  
  
 <span data-ttu-id="5a60d-106">これらのデータベースをバックアップした後、OLAP キューブを削除したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="5a60d-106">After you back up these databases, you may want to purge the OLAP cubes.</span></span> <span data-ttu-id="5a60d-107">OLAP キューブを削除するときに、次の手順も実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a60d-107">When you purge the OLAP cubes, you must also perform the following steps:</span></span>  
  
1. <span data-ttu-id="5a60d-108">削除する前に、BAMStarSchema データベースで、OLAP キューブを削除するキューブのファクト テーブルを切り捨てます。</span><span class="sxs-lookup"><span data-stu-id="5a60d-108">Before you purge the OLAP cubes, in the BAMStarSchema database, truncate the fact table(s) for the cube you want to purge.</span></span> <span data-ttu-id="5a60d-109">テーブルの名前付け規則は"bam _*\<CubeName\>*_Facts"です。</span><span class="sxs-lookup"><span data-stu-id="5a60d-109">The table naming convention is "bam_*\<CubeName\>*_Facts".</span></span>  
  
2. <span data-ttu-id="5a60d-110">OLAP キューブを削除した後では、アクティブ、完了、および仮想キューブを完全に処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a60d-110">After you purge the OLAP cubes, you must fully process active, completed, and virtual cubes.</span></span>  
  
   <span data-ttu-id="5a60d-111">分析データベースをバックアップする方法の詳細については、「アーカイブ Analysis Services データベースの」SQL Server オンライン ブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a60d-111">For instructions about backing up the analysis databases, see "Archiving an Analysis Services Database" in SQL Server Books Online.</span></span>  
  
   <span data-ttu-id="5a60d-112">**BAM データベースのバックアップのスケジュール設定**</span><span class="sxs-lookup"><span data-stu-id="5a60d-112">**Scheduling backups for the BAM databases**</span></span>  
  
   <span data-ttu-id="5a60d-113">BAM を使用している場合は、バックアップ パッケージの実行がスケジュールされるときにも、BAM キューブ プロセスやデータ メンテナンス データ変換サービス (DTS) パッケージが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5a60d-113">If you are using BAM, verify that neither the BAM cube process nor data maintenance Data Transformation Services (DTS) packages are running when the backup package is scheduled to run.</span></span>  
  
   <span data-ttu-id="5a60d-114">すべての BAM データベース間で一貫したスキーマを確実にデプロイしたり、BAM アクティビティを展開解除するたびを BAM データベースおよび DTS パッケージをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="5a60d-114">To ensure consistent schema across all BAM databases, back up the BAM databases and DTS packages each time you deploy or undeploy a BAM activity.</span></span>  
  
   <span data-ttu-id="5a60d-115">展開または BAM ビューを展開解除するたびに、BAM 分析データベースおよび BAMStarSchema データベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="5a60d-115">Back up the BAM Analysis database and BAMStarSchema database each time you deploy or undeploy a BAM view.</span></span>  
  
   <span data-ttu-id="5a60d-116">次の順序で BAM データベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="5a60d-116">Back up the BAM databases in the following order:</span></span>  
  
3. <span data-ttu-id="5a60d-117">BAMPrimaryImport データベースおよび他の BizTalk Server データベースをバックアップする BizTalk Server のバックアップ ジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a60d-117">Run the Backup BizTalk Server job to back up the BAMPrimaryImport database and your other BizTalk Server databases.</span></span>  
  
4. <span data-ttu-id="5a60d-118">すべてのアクティビティを BAM データ保守 DTS パッケージを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a60d-118">Run the BAM data maintenance DTS package for all activities.</span></span>  
  
    <span data-ttu-id="5a60d-119">DTS パッケージでは、次の手順を組み込むし、定期的に実行するパッケージのスケジュール設定します。</span><span class="sxs-lookup"><span data-stu-id="5a60d-119">Incorporate these steps into a DTS package, and schedule the package to run on a regular basis.</span></span> <span data-ttu-id="5a60d-120">データの整合性を確保するには、いないことを確認の他の BAM キューブまたはデータ保守 DTS パッケージがこのバックアップ パッケージの実行がスケジュールされるときに実行します。</span><span class="sxs-lookup"><span data-stu-id="5a60d-120">To ensure data integrity, make sure no other BAM cubing or data maintenance DTS packages run when this backup package is scheduled to run.</span></span>  
  
    <span data-ttu-id="5a60d-121">BAMArchive データベースが失敗した場合、BAMArchive データベースをバックアップするパーティションを BAMArchive データベースにコピーした後、BAMPrimaryImport データベースからパーティションを削除する前に、アーカイブされたデータの完全なセットを回復できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5a60d-121">To ensure that you can recover a complete set of archived data if the BAMArchive database fails, back up the BAMArchive database after you copy the partition into the BAMArchive database, but before you delete the partition from the BAMPrimaryImport database.</span></span> <span data-ttu-id="5a60d-122">これを行うには、変更、DTS パッケージの最後のステップの前に、BAMArchive データベースをバックアップするステップを挿入するには、各アクティビティのデータ管理 DTS パッケージ「アーカイブ終了」です。</span><span class="sxs-lookup"><span data-stu-id="5a60d-122">To do this, modify the data maintenance DTS package for each activity to insert a step to back up the BAMArchive database before the last step in the DTS package, "End Archiving."</span></span>  
  
5. <span data-ttu-id="5a60d-123">BAMAnalysis データベースおよび BAMStarSchema データベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="5a60d-123">Back up the BAMAnalysis database, and then the BAMStarSchema database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a60d-124">参照</span><span class="sxs-lookup"><span data-stu-id="5a60d-124">See Also</span></span>  
 [<span data-ttu-id="5a60d-125">BizTalk Server データベースのバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="5a60d-125">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)