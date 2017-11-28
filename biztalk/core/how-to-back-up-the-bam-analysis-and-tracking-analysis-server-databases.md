---
title: "バックアップ方法、BAM 分析および Tracking Analysis Server データベース |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e210fbe805e5a942605920e481faa2f1ca7cf2a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases"></a><span data-ttu-id="2e2f7-102">BAM 分析データベースおよび Tracking Analysis Server データベースをバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="2e2f7-102">How to Back Up the BAM Analysis and Tracking Analysis Server Databases</span></span>
<span data-ttu-id="2e2f7-103">ビジネス アクティビティ監視 (BAM) 分析データベースおよび Tracking Analysis Server データベースには、SQL Server Analysis Services キューブの内容が格納されます。</span><span class="sxs-lookup"><span data-stu-id="2e2f7-103">The Business Activity Monitoring (BAM) Analysis database and the Tracking Analysis Server database store content in SQL Server Analysis Services cubes.</span></span> <span data-ttu-id="2e2f7-104">BizTalk Server のバックアップ ジョブでは、これらのデータベースはバックアップされません。</span><span class="sxs-lookup"><span data-stu-id="2e2f7-104">The Backup BizTalk Server job does not back up these databases.</span></span> <span data-ttu-id="2e2f7-105">これらのデータベースをバックアップするには、SQL Server 分析マネージャを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e2f7-105">Instead, to backup these databases, you must use SQL Server Analysis Manager.</span></span>  
  
 <span data-ttu-id="2e2f7-106">これらのデータベースをバックアップした後で、OLAP キューブを削除できます。</span><span class="sxs-lookup"><span data-stu-id="2e2f7-106">After you back up these databases, you may want to purge the OLAP cubes.</span></span> <span data-ttu-id="2e2f7-107">OLAP キューブを削除する場合には、次の手順も実行してください。</span><span class="sxs-lookup"><span data-stu-id="2e2f7-107">When you purge the OLAP cubes, you must also perform the following steps:</span></span>  
  
1.  <span data-ttu-id="2e2f7-108">OLAP キューブを削除する前に、BAMStarSchema データベースで、削除するキューブのファクト テーブルを切り捨てます。</span><span class="sxs-lookup"><span data-stu-id="2e2f7-108">Before you purge the OLAP cubes, in the BAMStarSchema database, truncate the fact table(s) for the cube you want to purge.</span></span> <span data-ttu-id="2e2f7-109">テーブルの名前付け規則は"bam _*\<CubeName >*_Facts"です。</span><span class="sxs-lookup"><span data-stu-id="2e2f7-109">The table naming convention is "bam_*\<CubeName>*_Facts".</span></span>  
  
2.  <span data-ttu-id="2e2f7-110">OLAP キューブを削除した後で、アクティブなキューブ、完了したキューブ、および仮想キューブを完全に処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e2f7-110">After you purge the OLAP cubes, you must fully process active, completed, and virtual cubes.</span></span>  
  
 <span data-ttu-id="2e2f7-111">分析データベースをバックアップする方法については、SQL Server Books Online の「Analysis Services データベースのアーカイブ (Archiving an Analysis Services Database)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e2f7-111">For instructions about backing up the analysis databases, see "Archiving an Analysis Services Database" in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="2e2f7-112">**BAM データベースのバックアップのスケジュール設定**</span><span class="sxs-lookup"><span data-stu-id="2e2f7-112">**Scheduling backups for the BAM databases**</span></span>  
  
 <span data-ttu-id="2e2f7-113">BAM を使用している場合は、バックアップ パッケージの実行がスケジュールされているときに、並行して BAM キューブ プロセスやデータ管理のデータ変換サービス (DTS) パッケージが実行されないか、確認します。</span><span class="sxs-lookup"><span data-stu-id="2e2f7-113">If you are using BAM, verify that neither the BAM cube process nor data maintenance Data Transformation Services (DTS) packages are running when the backup package is scheduled to run.</span></span>  
  
 <span data-ttu-id="2e2f7-114">すべての BAM データベースでスキーマの一貫性を確保するには、BAM アクティビティを展開または展開解除するたびに、BAM データベースおよび DTS パッケージをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="2e2f7-114">To ensure consistent schema across all BAM databases, back up the BAM databases and DTS packages each time you deploy or undeploy a BAM activity.</span></span>  
  
 <span data-ttu-id="2e2f7-115">BAM ビューを展開または展開解除するたびに、BAM 分析データベースおよび BAMStarSchema データベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="2e2f7-115">Back up the BAM Analysis database and BAMStarSchema database each time you deploy or undeploy a BAM view.</span></span>  
  
 <span data-ttu-id="2e2f7-116">次の順序で BAM データベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="2e2f7-116">Back up the BAM databases in the following order:</span></span>  
  
1.  <span data-ttu-id="2e2f7-117">BizTalk Server のバックアップ ジョブを実行して、BAMPrimaryImport データベースおよび他の BizTalk Server データベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="2e2f7-117">Run the Backup BizTalk Server job to back up the BAMPrimaryImport database and your other BizTalk Server databases.</span></span>  
  
2.  <span data-ttu-id="2e2f7-118">すべてのアクティビティに対して、BAM データ管理 DTS パッケージを実行します。</span><span class="sxs-lookup"><span data-stu-id="2e2f7-118">Run the BAM data maintenance DTS package for all activities.</span></span>  
  
     <span data-ttu-id="2e2f7-119">これらの手順を DTS パッケージに組み込み、パッケージが定期的に実行されるようにスケジュール設定します。</span><span class="sxs-lookup"><span data-stu-id="2e2f7-119">Incorporate these steps into a DTS package, and schedule the package to run on a regular basis.</span></span> <span data-ttu-id="2e2f7-120">確実にデータの整合性を保つためには、このバックアップ パッケージの実行がスケジュールされているときに、並行して他の BAM キューブまたはデータ管理 DTS パッケージが実行されることのないようにします。</span><span class="sxs-lookup"><span data-stu-id="2e2f7-120">To ensure data integrity, make sure no other BAM cubing or data maintenance DTS packages run when this backup package is scheduled to run.</span></span>  
  
     <span data-ttu-id="2e2f7-121">BAMArchive データベースでエラーが発生した場合に、アーカイブしたデータの完全なセットを確実に回復できるようにするには、BAMArchive データベースのバックアップは、パーティションを BAMArchive データベースにコピーした後、パーティションを BAMPrimaryImport データベースから削除する前に行います。</span><span class="sxs-lookup"><span data-stu-id="2e2f7-121">To ensure that you can recover a complete set of archived data if the BAMArchive database fails, back up the BAMArchive database after you copy the partition into the BAMArchive database, but before you delete the partition from the BAMPrimaryImport database.</span></span> <span data-ttu-id="2e2f7-122">そのためには、各アクティビティのデータ管理 DTS パッケージを変更して、DTS パッケージの最後の手順 "アーカイブ終了" の前に、BAMArchive データベースをバックアップする手順を挿入します。</span><span class="sxs-lookup"><span data-stu-id="2e2f7-122">To do this, modify the data maintenance DTS package for each activity to insert a step to back up the BAMArchive database before the last step in the DTS package, "End Archiving."</span></span>  
  
3.  <span data-ttu-id="2e2f7-123">BAMAnalysis データベースおよび BAMStarSchema メッセージ スキーマをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="2e2f7-123">Back up the BAMAnalysis database, and then the BAMStarSchema database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e2f7-124">参照</span><span class="sxs-lookup"><span data-stu-id="2e2f7-124">See Also</span></span>  
 [<span data-ttu-id="2e2f7-125">バックアップと、BizTalk Server データベースの復元</span><span class="sxs-lookup"><span data-stu-id="2e2f7-125">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)