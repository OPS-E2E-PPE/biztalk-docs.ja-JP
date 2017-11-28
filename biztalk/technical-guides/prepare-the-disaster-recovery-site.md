---
title: "障害復旧サイトを準備する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b66f3c8-afe0-4ac0-b925-8f780d14bd4b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2119de8d5f8625943374d262b063491d2dafa6d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="prepare-the-disaster-recovery-site"></a><span data-ttu-id="9a792-102">障害復旧サイトを準備します。</span><span class="sxs-lookup"><span data-stu-id="9a792-102">Prepare the Disaster Recovery Site</span></span>
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="9a792-103">ログ配布では、サポートされている 2 つのシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="9a792-103"> log shipping has two supported scenarios.</span></span> <span data-ttu-id="9a792-104">1 つは、ログ配布のすべての実稼働インスタンス上のすべてのデータベースの保存場所[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]の 1 つの災害復旧のインスタンスに適用される[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="9a792-104">One is where log shipping for all databases on all production instances of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] is applied to a single disaster recovery instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="9a792-105">その他のシナリオは、ログ配布されてのデータベースの実稼働インスタンスごとに[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]の対応するインスタンスに適用される[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]災害復旧サイトにします。</span><span class="sxs-lookup"><span data-stu-id="9a792-105">The other scenario is where log shipping for the databases for each production instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] is applied to a corresponding instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] at the disaster recovery site.</span></span> <span data-ttu-id="9a792-106">同じ番号にする完全にサポートされることに注意してください[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]実稼働環境ではより少ない物理サーバーがあるため、障害復旧サイト内のインスタンスをデータベースします。</span><span class="sxs-lookup"><span data-stu-id="9a792-106">Note that it is fully supported to have the same number of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database instances in the disaster recovery site as there is in production but on fewer physical servers.</span></span> <span data-ttu-id="9a792-107">このセクションでは、これらの準備についてを説明します。</span><span class="sxs-lookup"><span data-stu-id="9a792-107">This section provides guidance on these preparations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9a792-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9a792-108">In This Section</span></span>  
  
-   [<span data-ttu-id="9a792-109">障害復旧 SQL サーバーを準備します。</span><span class="sxs-lookup"><span data-stu-id="9a792-109">Preparing the Disaster Recovery SQL Servers</span></span>](../technical-guides/preparing-the-disaster-recovery-sql-servers.md)  
  
-   [<span data-ttu-id="9a792-110">BAM 分析をバックアップして、追跡分析サーバー データベース</span><span class="sxs-lookup"><span data-stu-id="9a792-110">Backing Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)  
  
-   [<span data-ttu-id="9a792-111">災害復旧の BizTalk サーバーを準備します。</span><span class="sxs-lookup"><span data-stu-id="9a792-111">Preparing the Disaster Recovery BizTalk Servers</span></span>](../technical-guides/preparing-the-disaster-recovery-biztalk-servers.md)  
  
-   [<span data-ttu-id="9a792-112">アプリケーションの災害復旧の準備</span><span class="sxs-lookup"><span data-stu-id="9a792-112">Preparing Applications for Disaster Recovery</span></span>](../technical-guides/preparing-applications-for-disaster-recovery.md)  
  
-   [<span data-ttu-id="9a792-113">マスター シークレット サーバーを復元する方法</span><span class="sxs-lookup"><span data-stu-id="9a792-113">How to Restore the Master Secret Server</span></span>](../technical-guides/how-to-restore-the-master-secret-server.md)