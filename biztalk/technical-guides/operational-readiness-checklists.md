---
title: 運用準備チェックリスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c308a876-9872-43b3-a1fb-76e81396612f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b304b843806ed5550dd623d9980794a141083432
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400761"
---
# <a name="operational-readiness-checklists"></a><span data-ttu-id="be734-102">運用準備チェックリスト</span><span class="sxs-lookup"><span data-stu-id="be734-102">Operational Readiness Checklists</span></span>
<span data-ttu-id="be734-103">運用準備チェックリストには、考慮すべき推奨事項とタスクを運用環境に BizTalk ソリューションをデプロイする前に実行する必要がありますが含まれています。</span><span class="sxs-lookup"><span data-stu-id="be734-103">The Operational Readiness checklists contain recommendations that you should consider and tasks that you should perform before deploying a BizTalk solution into production.</span></span> <span data-ttu-id="be734-104">これらのチェックリストには、可用性の向上、前提条件のソフトウェアを構成するための情報が含まれます。 監視、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境、およびテストする手順。</span><span class="sxs-lookup"><span data-stu-id="be734-104">These checklists include information for configuring prerequisite software, increasing availability, monitoring the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, and procedures for testing.</span></span>  
  
 <span data-ttu-id="be734-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で依存関係が保持される他の多くの Microsoft テクノロジ、運用環境を確保しやすく依存している各テクノロジのタスクを完了する必要がありますので[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境をスムーズに実行します。</span><span class="sxs-lookup"><span data-stu-id="be734-105">Because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] maintains dependencies on so many other Microsoft technologies, you should complete the tasks for each dependent technology to help ensure that your production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment runs smoothly.</span></span>  
  
## <a name="typical-prerequisite-software"></a><span data-ttu-id="be734-106">一般的な前提条件ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="be734-106">Typical Prerequisite Software</span></span>  
 <span data-ttu-id="be734-107">前提条件のソフトウェア、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション プラットフォームには通常、次の製品が含まれています。</span><span class="sxs-lookup"><span data-stu-id="be734-107">Prerequisite software for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application platform typically includes the following products:</span></span>  
  
- <span data-ttu-id="be734-108">Windows オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="be734-108">The Windows operating system</span></span>  
  
- <span data-ttu-id="be734-109">SQL Server</span><span class="sxs-lookup"><span data-stu-id="be734-109">SQL Server</span></span> 
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- <span data-ttu-id="be734-110">Visual Studio (用に開発、実行時ではなく)</span><span class="sxs-lookup"><span data-stu-id="be734-110">Visual Studio (for development purposes, not at run time)</span></span>  
  
## <a name="additional-components"></a><span data-ttu-id="be734-111">その他のコンポーネント</span><span class="sxs-lookup"><span data-stu-id="be734-111">Additional Components</span></span>  
 <span data-ttu-id="be734-112">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション プラットフォームでは、次のソフトウェア コンポーネントのいくつか必要がありますも。</span><span class="sxs-lookup"><span data-stu-id="be734-112">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application platform may also require several of the following software components:</span></span>  
  
- <span data-ttu-id="be734-113">インターネット インフォメーション サービス (IIS)</span><span class="sxs-lookup"><span data-stu-id="be734-113">Internet Information Services (IIS)</span></span>  
  
- <span data-ttu-id="be734-114">SharePoint</span><span class="sxs-lookup"><span data-stu-id="be734-114">SharePoint</span></span>
  
- <span data-ttu-id="be734-115">Microsoft Office Excel</span><span class="sxs-lookup"><span data-stu-id="be734-115">Microsoft Office Excel</span></span> 
  
  > [!NOTE]  
  >  <span data-ttu-id="be734-116">BizTalk Server には、Microsoft Office の 32 ビット バージョンのみがサポートしています。</span><span class="sxs-lookup"><span data-stu-id="be734-116">BizTalk Server supports only the 32-bit version of Microsoft Office.</span></span>  
  
- <span data-ttu-id="be734-117">SQL Server</span><span class="sxs-lookup"><span data-stu-id="be734-117">SQL Server</span></span>
  
- <span data-ttu-id="be734-118">SQLXML</span><span class="sxs-lookup"><span data-stu-id="be734-118">SQLXML</span></span> 
  
- <span data-ttu-id="be734-119">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="be734-119">.NET Framework</span></span> 
  
- <span data-ttu-id="be734-120">特定の機能を有効にする Microsoft 以外のコンポーネント[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプター。</span><span class="sxs-lookup"><span data-stu-id="be734-120">Non-Microsoft components to enable functionality for certain [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapters.</span></span>  
  
  <span data-ttu-id="be734-121">さまざまな Windows オペレーティング システムのバージョンの BizTalk アプリケーション プラットフォームの特定の機能に必要な依存関係のソフトウェアの詳細については、次を参照してください[新機能、インストール、構成、アップグレード](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="be734-121">For more information about the dependency software that is required for specific features of the BizTalk application platform for various Windows operating system versions, see [What's New, Installation, Configuration, and Upgrade](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span>
- 
  
## <a name="next-steps"></a><span data-ttu-id="be734-122">次のステップ</span><span class="sxs-lookup"><span data-stu-id="be734-122">Next steps</span></span>
  
-   [<span data-ttu-id="be734-123">チェックリスト:BizTalk Server の概要</span><span class="sxs-lookup"><span data-stu-id="be734-123">Checklist: Getting Started with BizTalk Server</span></span>](http://msdn.microsoft.com/library/37d265cd-c393-46ac-ac21-129a1511359b)  
  
-   [<span data-ttu-id="be734-124">チェックリスト:Windows Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="be734-124">Checklist: Configuring Windows Server</span></span>](../technical-guides/checklist-configuring-windows-server.md)  
  
-   [<span data-ttu-id="be734-125">チェックリスト:インターネット インフォメーション サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="be734-125">Checklist: Configuring Internet Information Services</span></span>](../technical-guides/checklist-configuring-internet-information-services.md)  
  
-   [<span data-ttu-id="be734-126">チェックリスト:SQL Server の構成</span><span class="sxs-lookup"><span data-stu-id="be734-126">Checklist: Configuring SQL Server</span></span>](~/technical-guides/checklist-configuring-sql-server.md)  
  
-   [<span data-ttu-id="be734-127">チェックリスト:BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="be734-127">Checklist: Configuring BizTalk Server</span></span>](../technical-guides/checklist-configuring-biztalk-server.md)  
  
-   [<span data-ttu-id="be734-128">チェックリスト:フォールト トレランスまたは負荷分散と高可用性を実現します。</span><span class="sxs-lookup"><span data-stu-id="be734-128">Checklist: Providing High Availability with Fault Tolerance or Load Balancing</span></span>](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)  
  
-   [<span data-ttu-id="be734-129">チェックリスト:ディザスター リカバリーによる可用性の向上</span><span class="sxs-lookup"><span data-stu-id="be734-129">Checklist: Increasing Availability with Disaster Recovery</span></span>](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)  
  
-   [<span data-ttu-id="be734-130">チェックリスト:運用準備状況の監視</span><span class="sxs-lookup"><span data-stu-id="be734-130">Checklist: Monitoring Operational Readiness</span></span>](../technical-guides/checklist-monitoring-operational-readiness.md)  
  
-   [<span data-ttu-id="be734-131">チェックリスト:メンテナンスと BizTalk Server データベースのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="be734-131">Checklist: Maintaining and Troubleshooting BizTalk Server Databases</span></span>](~/technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="be734-132">チェックリスト:運用準備のテスト</span><span class="sxs-lookup"><span data-stu-id="be734-132">Checklist: Testing Operational Readiness</span></span>](../technical-guides/checklist-testing-operational-readiness.md)