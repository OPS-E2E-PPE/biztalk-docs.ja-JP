---
title: "Analysis Services を復元して、サポートされるデータベース |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 490ad0fb-7805-4ebc-9bc5-117d52d7c3a8
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da16bde7b69071b71b794c4c46407feab3ef4512
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="restoring-analysis-services-and-supporting-databases"></a><span data-ttu-id="f29af-102">Analysis Services を復元して、データベースのサポート</span><span class="sxs-lookup"><span data-stu-id="f29af-102">Restoring Analysis Services and Supporting Databases</span></span>
<span data-ttu-id="f29af-103">2 つ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services データベースを障害復旧シナリオに復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f29af-103">There are two [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services databases that must be restored in a disaster recovery scenario:</span></span>  
  
-   <span data-ttu-id="f29af-104">BAM 分析 (BAMAnalysis)</span><span class="sxs-lookup"><span data-stu-id="f29af-104">BAM Analysis (BAMAnalysis)</span></span>  
  
-   <span data-ttu-id="f29af-105">追跡 Analysis Server (BizTalkAnalysisdb)</span><span class="sxs-lookup"><span data-stu-id="f29af-105">Tracking Analysis Server (BizTalkAnalysisdb)</span></span>  
  
 <span data-ttu-id="f29af-106">BAM[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースにバックアップされます、BizTalk Server のバックアップ ジョブの一環として BAM が有効になっているが、構成されていない場合。</span><span class="sxs-lookup"><span data-stu-id="f29af-106">The BAM [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases may be backed up as part of the Backup BizTalk Server job if BAM is enabled but not configured.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f29af-107">BAM プライマリ インポート データベースは、DTC トランザクションに含まれているためにも、常に、BizTalk Server のバックアップ ジョブの一部としてバックアップします。</span><span class="sxs-lookup"><span data-stu-id="f29af-107">The BAM Primary Import database is always backed up as part of the Backup BizTalk Server job because it participates in DTC transactions.</span></span>  
  
 <span data-ttu-id="f29af-108">BAM が有効になっているが、構成されていない場合は、次の BAM データベースを BizTalk Server のバックアップ ジョブの一部になります。</span><span class="sxs-lookup"><span data-stu-id="f29af-108">The following BAM databases will be part of the Backup BizTalk Server job if BAM is enabled but not configured:</span></span>  
  
-   <span data-ttu-id="f29af-109">BAMStarSchema</span><span class="sxs-lookup"><span data-stu-id="f29af-109">BAMStarSchema</span></span>  
  
-   <span data-ttu-id="f29af-110">BAMArchive</span><span class="sxs-lookup"><span data-stu-id="f29af-110">BAMArchive</span></span>  
  
 <span data-ttu-id="f29af-111">手順に従います[BizTalk Server のバックアップ ジョブでデータベースを復元する方法](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)をこれらのデータベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="f29af-111">Follow the steps in [How to Restore Databases in the Backup BizTalk Server Job](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md) to restore these databases.</span></span>  
  
 <span data-ttu-id="f29af-112">**それ以外の場合**</span><span class="sxs-lookup"><span data-stu-id="f29af-112">**Otherwise,**</span></span>  
 <span data-ttu-id="f29af-113">**BAM が有効にし、BM.exe が装備されても、セットとして適切な BAM データベースのセットを一緒に復元する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="f29af-113">**if BAM is enabled and is also configured with BM.exe, the correct set of BAM databases must be restored together as a set.**</span></span> <span data-ttu-id="f29af-114">アーカイブ済みのデータの完全なセットを復元することを確認してください、BAM アーカイブ データベースがバックアップ パーティションを BAM アーカイブにコピーした後は、パーティションを BAM プライマリ インポート データベースから削除する前にします。</span><span class="sxs-lookup"><span data-stu-id="f29af-114">To ensure that a complete set of archived data is recovered, the BAM Archive database is backed up after the partition is copied into the BAM Archive, but before the partition is deleted from the BAM Primary Import database.</span></span> <span data-ttu-id="f29af-115">これは、最後の手順「アーカイブ終了」です前に、BAM アーカイブ データベースをバックアップするステップを挿入することで各アクティビティのデータ保守 SSIS パッケージを変更することで実行します。</span><span class="sxs-lookup"><span data-stu-id="f29af-115">This is performed by modifying the data maintenance SSIS package for each activity by inserting a step to back up the BAM Archive database before the last step "End Archiving."</span></span>  
  
 <span data-ttu-id="f29af-116">BAM データベースの復元手順は、: BAM プライマリ インポート データベースは、x の前回のバックアップと復元は場合、は、データ保守 SSIS パッケージの時に最新の日付に対応する BAM アーカイブ、BAM スター スキーマ データベースのコピーを復元x の日の前に実行します。</span><span class="sxs-lookup"><span data-stu-id="f29af-116">The restore procedure for the BAM databases is: If the BAM Primary Import database is restored with the last backup date of x, restore the copies of the BAM Archive and BAM Star Schema databases that correspond to the latest date when the data maintenance SSIS package was run before the date of x.</span></span>  
  
 <span data-ttu-id="f29af-117">適切な BAM データベースのセットを識別した後は、復元、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]で説明されているように、標準的な手順を使用して Analysis Services データベース、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]復元のオンライン ブック[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースおよび[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services データベースです。</span><span class="sxs-lookup"><span data-stu-id="f29af-117">After the correct set of BAM databases is identified, restore the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services databases using standard procedures as documented in the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online for restoring [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f29af-118">参照</span><span class="sxs-lookup"><span data-stu-id="f29af-118">See Also</span></span>  
 [<span data-ttu-id="f29af-119">BAM 分析をバックアップして、追跡分析サーバー データベース</span><span class="sxs-lookup"><span data-stu-id="f29af-119">Backing Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)