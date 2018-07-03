---
title: Analysis Services を復元して、データベースのサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 490ad0fb-7805-4ebc-9bc5-117d52d7c3a8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cf50a7ef1903d3839aaa9b810e145432b62b552
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020463"
---
# <a name="restoring-analysis-services-and-supporting-databases"></a><span data-ttu-id="2e86a-102">Analysis Services を復元して、サポートするデータベース</span><span class="sxs-lookup"><span data-stu-id="2e86a-102">Restoring Analysis Services and Supporting Databases</span></span>
<span data-ttu-id="2e86a-103">2 つ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services データベースをディザスター リカバリーのシナリオで復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e86a-103">There are two [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services databases that must be restored in a disaster recovery scenario:</span></span>  
  
- <span data-ttu-id="2e86a-104">BAM 分析 (BAMAnalysis)</span><span class="sxs-lookup"><span data-stu-id="2e86a-104">BAM Analysis (BAMAnalysis)</span></span>  
  
- <span data-ttu-id="2e86a-105">追跡 Analysis Server (BizTalkAnalysisdb)</span><span class="sxs-lookup"><span data-stu-id="2e86a-105">Tracking Analysis Server (BizTalkAnalysisdb)</span></span>  
  
  <span data-ttu-id="2e86a-106">BAM[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースがバックアップ BizTalk Server のバックアップ ジョブの一環として BAM が有効になっているが、構成されていない場合。</span><span class="sxs-lookup"><span data-stu-id="2e86a-106">The BAM [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases may be backed up as part of the Backup BizTalk Server job if BAM is enabled but not configured.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2e86a-107">BAM プライマリ インポート データベースは、DTC トランザクションに含まれているためにも、常に、BizTalk Server のバックアップ ジョブの一部としてバックアップします。</span><span class="sxs-lookup"><span data-stu-id="2e86a-107">The BAM Primary Import database is always backed up as part of the Backup BizTalk Server job because it participates in DTC transactions.</span></span>  
  
 <span data-ttu-id="2e86a-108">BAM を有効になっているが、構成されていない場合は、次の BAM データベースを BizTalk Server のバックアップ ジョブの一部になります。</span><span class="sxs-lookup"><span data-stu-id="2e86a-108">The following BAM databases will be part of the Backup BizTalk Server job if BAM is enabled but not configured:</span></span>  
  
- <span data-ttu-id="2e86a-109">BAMStarSchema</span><span class="sxs-lookup"><span data-stu-id="2e86a-109">BAMStarSchema</span></span>  
  
- <span data-ttu-id="2e86a-110">BAMArchive</span><span class="sxs-lookup"><span data-stu-id="2e86a-110">BAMArchive</span></span>  
  
  <span data-ttu-id="2e86a-111">次の手順では、 [Backup BizTalk Server ジョブでデータベースを復元する方法](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)をこれらのデータベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="2e86a-111">Follow the steps in [How to Restore Databases in the Backup BizTalk Server Job](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md) to restore these databases.</span></span>  
  
  <span data-ttu-id="2e86a-112">**それ以外の場合、**</span><span class="sxs-lookup"><span data-stu-id="2e86a-112">**Otherwise,**</span></span>  
  <span data-ttu-id="2e86a-113">**BAM が有効にし、BM.exe を割り当てていることも、適切な BAM データベースのセットがセットとしてまとめて復元する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="2e86a-113">**if BAM is enabled and is also configured with BM.exe, the correct set of BAM databases must be restored together as a set.**</span></span> <span data-ttu-id="2e86a-114">アーカイブ済みのデータの完全なセットは、回復になっていることを確認するには、BAM アーカイブ データベースがバックアップに、BAM アーカイブ、パーティションをコピーした後が、パーティションを BAM プライマリ インポート データベースから削除する前にします。</span><span class="sxs-lookup"><span data-stu-id="2e86a-114">To ensure that a complete set of archived data is recovered, the BAM Archive database is backed up after the partition is copied into the BAM Archive, but before the partition is deleted from the BAM Primary Import database.</span></span> <span data-ttu-id="2e86a-115">これは、最後の手順「アーカイブ終了」です前に、BAM アーカイブ データベースをバックアップするステップを挿入することで各アクティビティのデータ保守 SSIS パッケージを変更することで実行します。</span><span class="sxs-lookup"><span data-stu-id="2e86a-115">This is performed by modifying the data maintenance SSIS package for each activity by inserting a step to back up the BAM Archive database before the last step "End Archiving."</span></span>  
  
  <span data-ttu-id="2e86a-116">BAM データベースの復元手順は、: BAM プライマリ インポート データベースは x の前回のバックアップと復元された場合、に、データ保守 SSIS パッケージが最新の日付に対応する BAM アーカイブおよび BAM スター スキーマ データベースのコピーを復元x の日付より前に実行します。</span><span class="sxs-lookup"><span data-stu-id="2e86a-116">The restore procedure for the BAM databases is: If the BAM Primary Import database is restored with the last backup date of x, restore the copies of the BAM Archive and BAM Star Schema databases that correspond to the latest date when the data maintenance SSIS package was run before the date of x.</span></span>  
  
  <span data-ttu-id="2e86a-117">適切な BAM データベースのセットを特定した後は、復元、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]に記載されている標準的な手順を使用して Analysis Services データベース、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]復元のオンライン ブックの「[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースと[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services データベース。</span><span class="sxs-lookup"><span data-stu-id="2e86a-117">After the correct set of BAM databases is identified, restore the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services databases using standard procedures as documented in the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online for restoring [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e86a-118">参照</span><span class="sxs-lookup"><span data-stu-id="2e86a-118">See Also</span></span>  
 [<span data-ttu-id="2e86a-119">BAM 分析および Tracking Analysis Server データベースのバックアップ</span><span class="sxs-lookup"><span data-stu-id="2e86a-119">Backing Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)