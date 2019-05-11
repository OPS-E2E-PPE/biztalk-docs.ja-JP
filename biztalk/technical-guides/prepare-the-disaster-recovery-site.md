---
title: ディザスター リカバリー サイトの準備 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b66f3c8-afe0-4ac0-b925-8f780d14bd4b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b59adfbbb9ae8d995c3518eaa5c7491fa0179a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65252863"
---
# <a name="prepare-the-disaster-recovery-site"></a><span data-ttu-id="f06e9-102">ディザスター リカバリー サイトを準備します。</span><span class="sxs-lookup"><span data-stu-id="f06e9-102">Prepare the Disaster Recovery Site</span></span>
<span data-ttu-id="f06e9-103">BizTalk Server ログ配布がサポートされている 2 つのシナリオ。</span><span class="sxs-lookup"><span data-stu-id="f06e9-103">BizTalk Server log shipping has two supported scenarios.</span></span> <span data-ttu-id="f06e9-104">1 つは、ログのすべての実稼働インスタンス上のすべてのデータベースの配布[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]の 1 つの災害復旧のインスタンスに適用される[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f06e9-104">One is where log shipping for all databases on all production instances of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] is applied to a single disaster recovery instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="f06e9-105">その他のシナリオは、配布の各実稼働インスタンス用のデータベースのログの保存場所[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]の対応するインスタンスに適用される[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ディザスター リカバリー サイトにします。</span><span class="sxs-lookup"><span data-stu-id="f06e9-105">The other scenario is where log shipping for the databases for each production instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] is applied to a corresponding instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] at the disaster recovery site.</span></span> <span data-ttu-id="f06e9-106">同じ番号にする完全にサポートされることに注意してください。[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]が運用環境で、より少ない物理サーバーでは、ディザスター リカバリー サイトのインスタンスをデータベース。</span><span class="sxs-lookup"><span data-stu-id="f06e9-106">Note that it is fully supported to have the same number of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database instances in the disaster recovery site as there is in production but on fewer physical servers.</span></span> <span data-ttu-id="f06e9-107">ここでは、これらの準備作業のガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="f06e9-107">This section provides guidance on these preparations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f06e9-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f06e9-108">In This Section</span></span>  
  
-   [<span data-ttu-id="f06e9-109">ディザスター リカバリー SQL Server の準備</span><span class="sxs-lookup"><span data-stu-id="f06e9-109">Preparing the Disaster Recovery SQL Servers</span></span>](../technical-guides/preparing-the-disaster-recovery-sql-servers.md)  
  
-   [<span data-ttu-id="f06e9-110">BAM 分析および Tracking Analysis Server データベースのバックアップ</span><span class="sxs-lookup"><span data-stu-id="f06e9-110">Backing Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)  
  
-   [<span data-ttu-id="f06e9-111">ディザスター リカバリー BizTalk Server の準備</span><span class="sxs-lookup"><span data-stu-id="f06e9-111">Preparing the Disaster Recovery BizTalk Servers</span></span>](../technical-guides/preparing-the-disaster-recovery-biztalk-servers.md)  
  
-   [<span data-ttu-id="f06e9-112">ディザスター リカバリーのためのアプリケーションの準備</span><span class="sxs-lookup"><span data-stu-id="f06e9-112">Preparing Applications for Disaster Recovery</span></span>](../technical-guides/preparing-applications-for-disaster-recovery.md)  
  
-   [<span data-ttu-id="f06e9-113">マスター シークレット サーバーを復元する方法</span><span class="sxs-lookup"><span data-stu-id="f06e9-113">How to Restore the Master Secret Server</span></span>](../technical-guides/how-to-restore-the-master-secret-server.md)