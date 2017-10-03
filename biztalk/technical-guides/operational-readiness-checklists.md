---
title: "運用の準備のチェックリスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c308a876-9872-43b3-a1fb-76e81396612f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87da295129a4cb90ecf643cd06eb18ac3e6aa18e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="operational-readiness-checklists"></a><span data-ttu-id="9f688-102">運用の準備のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="9f688-102">Operational Readiness Checklists</span></span>
<span data-ttu-id="9f688-103">運用の準備のチェックリストには、考慮すべき推奨事項と、BizTalk ソリューションを実稼働環境に展開する前に行う必要がありますタスクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9f688-103">The Operational Readiness checklists contain recommendations that you should consider and tasks that you should perform before deploying a BizTalk solution into production.</span></span> <span data-ttu-id="9f688-104">これらのチェックリストには、前提条件ソフトウェアの可用性を高める構成に関する情報が含まれます。 監視、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境、およびテストする手順。</span><span class="sxs-lookup"><span data-stu-id="9f688-104">These checklists include information for configuring prerequisite software, increasing availability, monitoring the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, and procedures for testing.</span></span>  
  
 <span data-ttu-id="9f688-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で依存関係が維持される他の多くの Microsoft テクノロジとなるように、実稼働環境に依存している各テクノロジのタスクを完了する必要がありますので[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境がスムーズに実行されます。</span><span class="sxs-lookup"><span data-stu-id="9f688-105">Because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] maintains dependencies on so many other Microsoft technologies, you should complete the tasks for each dependent technology to help ensure that your production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment runs smoothly.</span></span>  
  
## <a name="typical-prerequisite-software"></a><span data-ttu-id="9f688-106">一般的な前提条件ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="9f688-106">Typical Prerequisite Software</span></span>  
 <span data-ttu-id="9f688-107">前提条件ソフトウェア、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション プラットフォームには通常、次の製品が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9f688-107">Prerequisite software for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application platform typically includes the following products:</span></span>  
  
-   <span data-ttu-id="9f688-108">Windows オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="9f688-108">The Windows operating system</span></span>  
  
-   [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]<span data-ttu-id="9f688-109">SP1 または[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f688-109"> SP1 or [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]<span data-ttu-id="9f688-110">(開発目的の実行時ではなく)</span><span class="sxs-lookup"><span data-stu-id="9f688-110"> (for development purposes, not at run time)</span></span>  
  
## <a name="additional-components"></a><span data-ttu-id="9f688-111">その他のコンポーネント</span><span class="sxs-lookup"><span data-stu-id="9f688-111">Additional Components</span></span>  
 <span data-ttu-id="9f688-112">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション プラットフォームもかかる場合、次のソフトウェア コンポーネントのいくつか。</span><span class="sxs-lookup"><span data-stu-id="9f688-112">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application platform may also require several of the following software components:</span></span>  
  
-   <span data-ttu-id="9f688-113">インターネット インフォメーション サービス (IIS)</span><span class="sxs-lookup"><span data-stu-id="9f688-113">Internet Information Services (IIS)</span></span>  
  
-   <span data-ttu-id="9f688-114">Windows SharePoint® Services 2010</span><span class="sxs-lookup"><span data-stu-id="9f688-114">Windows SharePoint® Services 2010</span></span>  
  
-   <span data-ttu-id="9f688-115">SharePoint Foundation 2010</span><span class="sxs-lookup"><span data-stu-id="9f688-115">SharePoint Foundation 2010</span></span>  
  
-   <span data-ttu-id="9f688-116">Microsoft Office SharePoint Server 2007 Service Pack 1 (SP1) (MOSS)</span><span class="sxs-lookup"><span data-stu-id="9f688-116">Microsoft Office SharePoint Server 2007 Service Pack 1 (SP1) (MOSS)</span></span>  
  
-   <span data-ttu-id="9f688-117">SP1 または SP2、Windows SharePoint Services 3.0</span><span class="sxs-lookup"><span data-stu-id="9f688-117">Windows SharePoint Services 3.0 with SP1 or SP2</span></span>  
  
-   <span data-ttu-id="9f688-118">Microsoft Office Excel 2010 または 2007</span><span class="sxs-lookup"><span data-stu-id="9f688-118">Microsoft Office Excel 2010 or 2007</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="9f688-119">Microsoft Office 2010 の 32 ビット バージョンのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9f688-119"> supports only the 32-bit version of Microsoft Office 2010.</span></span>  
  
-   <span data-ttu-id="9f688-120">SQL Server 2005 Notification Services</span><span class="sxs-lookup"><span data-stu-id="9f688-120">SQL Server 2005 Notification Services</span></span>  
  
-   <span data-ttu-id="9f688-121">SQLXML 4.0 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="9f688-121">SQLXML 4.0 with Service Pack 1</span></span>  
  
-   <span data-ttu-id="9f688-122">.NET framework 1.0</span><span class="sxs-lookup"><span data-stu-id="9f688-122">.NET Framework 1.0</span></span>  
  
-   <span data-ttu-id="9f688-123">.NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="9f688-123">.NET Framework 2.0</span></span>  
  
-   <span data-ttu-id="9f688-124">.NET framework 3.0</span><span class="sxs-lookup"><span data-stu-id="9f688-124">.NET Framework 3.0</span></span>  
  
-   <span data-ttu-id="9f688-125">Microsoft .NET Framework 4 および .Net Framework 3.5 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="9f688-125">Microsoft .NET Framework 4 and .Net Framework 3.5 with Service Pack 1 (SP1)</span></span>  
  
-   <span data-ttu-id="9f688-126">特定の機能を有効にする Microsoft 以外のコンポーネント[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプター。</span><span class="sxs-lookup"><span data-stu-id="9f688-126">Non-Microsoft components to enable functionality for certain [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapters.</span></span>  
  
 <span data-ttu-id="9f688-127">さまざまな Windows オペレーティング システムのバージョンの BizTalk アプリケーション プラットフォームの特定の機能に必要な依存関係ソフトウェアに関する詳細についてを参照してください「機能の依存関係の一覧」で、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]インストールし、特定の Windows オペレーティング システムのバージョンのガイドをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="9f688-127">For more information about the dependency software that is required for specific features of the BizTalk application platform for various Windows operating system versions, see the "Feature Dependency Matrix" section in the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] installation and upgrade guide for the specific Windows operating system version.</span></span> <span data-ttu-id="9f688-128">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]インストールおよびアップグレード ガイドはいただけます[http://go.microsoft.com/fwlink/?LinkID=152913](http://go.microsoft.com/fwlink/?LinkID=152913)です。</span><span class="sxs-lookup"><span data-stu-id="9f688-128">The [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] installation and upgrade guides are available at [http://go.microsoft.com/fwlink/?LinkID=152913](http://go.microsoft.com/fwlink/?LinkID=152913).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9f688-129">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9f688-129">In This Section</span></span>  
  
-   [<span data-ttu-id="9f688-130">チェックリスト: BizTalk Server の概要</span><span class="sxs-lookup"><span data-stu-id="9f688-130">Checklist: Getting Started with BizTalk Server</span></span>](http://msdn.microsoft.com/library/37d265cd-c393-46ac-ac21-129a1511359b)  
  
-   [<span data-ttu-id="9f688-131">チェックリスト: Windows Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="9f688-131">Checklist: Configuring Windows Server</span></span>](../technical-guides/checklist-configuring-windows-server.md)  
  
-   [<span data-ttu-id="9f688-132">チェックリスト: インターネット インフォメーション サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="9f688-132">Checklist: Configuring Internet Information Services</span></span>](../technical-guides/checklist-configuring-internet-information-services.md)  
  
-   [<span data-ttu-id="9f688-133">チェックリスト: SQL Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="9f688-133">Checklist: Configuring SQL Server</span></span>](~/technical-guides/checklist-configuring-sql-server.md)  
  
-   [<span data-ttu-id="9f688-134">チェックリスト: BizTalk Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="9f688-134">Checklist: Configuring BizTalk Server</span></span>](../technical-guides/checklist-configuring-biztalk-server.md)  
  
-   [<span data-ttu-id="9f688-135">チェックリスト: フォールト トレランスと負荷分散と高可用性を実現します。</span><span class="sxs-lookup"><span data-stu-id="9f688-135">Checklist: Providing High Availability with Fault Tolerance or Load Balancing</span></span>](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)  
  
-   [<span data-ttu-id="9f688-136">チェックリスト: 災害復旧と可用性の向上</span><span class="sxs-lookup"><span data-stu-id="9f688-136">Checklist: Increasing Availability with Disaster Recovery</span></span>](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)  
  
-   [<span data-ttu-id="9f688-137">チェックリスト: 監視の運用の準備</span><span class="sxs-lookup"><span data-stu-id="9f688-137">Checklist: Monitoring Operational Readiness</span></span>](../technical-guides/checklist-monitoring-operational-readiness.md)  
  
-   [<span data-ttu-id="9f688-138">チェックリスト: を維持し、BizTalk Server データベースのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="9f688-138">Checklist: Maintaining and Troubleshooting BizTalk Server Databases</span></span>](~/technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="9f688-139">チェックリスト: テスト運用の準備</span><span class="sxs-lookup"><span data-stu-id="9f688-139">Checklist: Testing Operational Readiness</span></span>](../technical-guides/checklist-testing-operational-readiness.md)