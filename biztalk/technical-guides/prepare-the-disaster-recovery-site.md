---
title: 障害復旧サイトを準備する |Microsoft ドキュメント
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
ms.openlocfilehash: 7a60be6d04d0f73013f67c5fe8e5b0144357fd1f
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008867"
---
# <a name="prepare-the-disaster-recovery-site"></a><span data-ttu-id="27f6f-102">障害復旧サイトを準備します。</span><span class="sxs-lookup"><span data-stu-id="27f6f-102">Prepare the Disaster Recovery Site</span></span>
<span data-ttu-id="27f6f-103">BizTalk Server ログ配布がサポートされている 2 つのシナリオです。</span><span class="sxs-lookup"><span data-stu-id="27f6f-103">BizTalk Server log shipping has two supported scenarios.</span></span> <span data-ttu-id="27f6f-104">1 つは、ログ配布のすべての実稼働インスタンス上のすべてのデータベースの保存場所[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]の 1 つの災害復旧のインスタンスに適用される[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="27f6f-104">One is where log shipping for all databases on all production instances of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] is applied to a single disaster recovery instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="27f6f-105">その他のシナリオは、ログ配布されてのデータベースの実稼働インスタンスごとに[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]の対応するインスタンスに適用される[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]災害復旧サイトにします。</span><span class="sxs-lookup"><span data-stu-id="27f6f-105">The other scenario is where log shipping for the databases for each production instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] is applied to a corresponding instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] at the disaster recovery site.</span></span> <span data-ttu-id="27f6f-106">同じ番号にする完全にサポートされることに注意してください[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]実稼働環境ではより少ない物理サーバーがあるため、障害復旧サイト内のインスタンスをデータベースします。</span><span class="sxs-lookup"><span data-stu-id="27f6f-106">Note that it is fully supported to have the same number of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database instances in the disaster recovery site as there is in production but on fewer physical servers.</span></span> <span data-ttu-id="27f6f-107">このセクションでは、これらの準備についてを説明します。</span><span class="sxs-lookup"><span data-stu-id="27f6f-107">This section provides guidance on these preparations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="27f6f-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="27f6f-108">In This Section</span></span>  
  
-   [<span data-ttu-id="27f6f-109">ディザスター リカバリー SQL Server の準備</span><span class="sxs-lookup"><span data-stu-id="27f6f-109">Preparing the Disaster Recovery SQL Servers</span></span>](../technical-guides/preparing-the-disaster-recovery-sql-servers.md)  
  
-   [<span data-ttu-id="27f6f-110">BAM 分析および Tracking Analysis Server データベースのバックアップ</span><span class="sxs-lookup"><span data-stu-id="27f6f-110">Backing Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)  
  
-   [<span data-ttu-id="27f6f-111">ディザスター リカバリー BizTalk Server の準備</span><span class="sxs-lookup"><span data-stu-id="27f6f-111">Preparing the Disaster Recovery BizTalk Servers</span></span>](../technical-guides/preparing-the-disaster-recovery-biztalk-servers.md)  
  
-   [<span data-ttu-id="27f6f-112">ディザスター リカバリーのためのアプリケーションの準備</span><span class="sxs-lookup"><span data-stu-id="27f6f-112">Preparing Applications for Disaster Recovery</span></span>](../technical-guides/preparing-applications-for-disaster-recovery.md)  
  
-   [<span data-ttu-id="27f6f-113">マスター シークレット サーバーを復元する方法</span><span class="sxs-lookup"><span data-stu-id="27f6f-113">How to Restore the Master Secret Server</span></span>](../technical-guides/how-to-restore-the-master-secret-server.md)