---
title: 運用の準備のチェックリスト |Microsoft ドキュメント
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
ms.openlocfilehash: f9e9297e5539fd95f316ebbf6239a5d017ec4ecf
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="operational-readiness-checklists"></a><span data-ttu-id="c7108-102">運用の準備のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="c7108-102">Operational Readiness Checklists</span></span>
<span data-ttu-id="c7108-103">運用の準備のチェックリストには、考慮すべき推奨事項と、BizTalk ソリューションを実稼働環境に展開する前に行う必要がありますタスクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c7108-103">The Operational Readiness checklists contain recommendations that you should consider and tasks that you should perform before deploying a BizTalk solution into production.</span></span> <span data-ttu-id="c7108-104">これらのチェックリストには、前提条件ソフトウェアの可用性を高める構成に関する情報が含まれます。 監視、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境、およびテストする手順。</span><span class="sxs-lookup"><span data-stu-id="c7108-104">These checklists include information for configuring prerequisite software, increasing availability, monitoring the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, and procedures for testing.</span></span>  
  
 <span data-ttu-id="c7108-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で依存関係が維持される他の多くの Microsoft テクノロジとなるように、実稼働環境に依存している各テクノロジのタスクを完了する必要がありますので[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境がスムーズに実行されます。</span><span class="sxs-lookup"><span data-stu-id="c7108-105">Because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] maintains dependencies on so many other Microsoft technologies, you should complete the tasks for each dependent technology to help ensure that your production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment runs smoothly.</span></span>  
  
## <a name="typical-prerequisite-software"></a><span data-ttu-id="c7108-106">一般的な前提条件ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="c7108-106">Typical Prerequisite Software</span></span>  
 <span data-ttu-id="c7108-107">前提条件ソフトウェア、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション プラットフォームには通常、次の製品が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c7108-107">Prerequisite software for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application platform typically includes the following products:</span></span>  
  
-   <span data-ttu-id="c7108-108">Windows オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="c7108-108">The Windows operating system</span></span>  
  
-   <span data-ttu-id="c7108-109">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c7108-109">SQL Server</span></span> 
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   <span data-ttu-id="c7108-110">Visual Studio (開発目的で、実行時ではなく)</span><span class="sxs-lookup"><span data-stu-id="c7108-110">Visual Studio (for development purposes, not at run time)</span></span>  
  
## <a name="additional-components"></a><span data-ttu-id="c7108-111">その他のコンポーネント</span><span class="sxs-lookup"><span data-stu-id="c7108-111">Additional Components</span></span>  
 <span data-ttu-id="c7108-112">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション プラットフォームもかかる場合、次のソフトウェア コンポーネントのいくつか。</span><span class="sxs-lookup"><span data-stu-id="c7108-112">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application platform may also require several of the following software components:</span></span>  
  
-   <span data-ttu-id="c7108-113">インターネット インフォメーション サービス (IIS)</span><span class="sxs-lookup"><span data-stu-id="c7108-113">Internet Information Services (IIS)</span></span>  
  
-   <span data-ttu-id="c7108-114">SharePoint</span><span class="sxs-lookup"><span data-stu-id="c7108-114">SharePoint</span></span>
  
-   <span data-ttu-id="c7108-115">Microsoft Office Excel</span><span class="sxs-lookup"><span data-stu-id="c7108-115">Microsoft Office Excel</span></span> 
  
    > [!NOTE]  
    >  <span data-ttu-id="c7108-116">BizTalk Server には、Microsoft Office の 32 ビット バージョンのみがサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c7108-116">BizTalk Server supports only the 32-bit version of Microsoft Office.</span></span>  
  
-   <span data-ttu-id="c7108-117">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c7108-117">SQL Server</span></span>
  
-   <span data-ttu-id="c7108-118">SQLXML</span><span class="sxs-lookup"><span data-stu-id="c7108-118">SQLXML</span></span> 
  
-   <span data-ttu-id="c7108-119">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="c7108-119">.NET Framework</span></span> 
  
-   <span data-ttu-id="c7108-120">特定の機能を有効にする Microsoft 以外のコンポーネント[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプター。</span><span class="sxs-lookup"><span data-stu-id="c7108-120">Non-Microsoft components to enable functionality for certain [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapters.</span></span>  
  
 <span data-ttu-id="c7108-121">さまざまな Windows オペレーティング システムのバージョンの BizTalk アプリケーション プラットフォームの特定の機能に必要な依存関係のソフトウェアの詳細については、次を参照してください[は新規、インストール、構成、およびアップグレード](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="c7108-121">For more information about the dependency software that is required for specific features of the BizTalk application platform for various Windows operating system versions, see [What's New, Installation, Configuration, and Upgrade](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span>
- 
  
## <a name="next-steps"></a><span data-ttu-id="c7108-122">次の手順</span><span class="sxs-lookup"><span data-stu-id="c7108-122">Next steps</span></span>
  
-   [<span data-ttu-id="c7108-123">チェックリスト: BizTalk Server の概要</span><span class="sxs-lookup"><span data-stu-id="c7108-123">Checklist: Getting Started with BizTalk Server</span></span>](http://msdn.microsoft.com/library/37d265cd-c393-46ac-ac21-129a1511359b)  
  
-   [<span data-ttu-id="c7108-124">チェックリスト: Windows Server の構成</span><span class="sxs-lookup"><span data-stu-id="c7108-124">Checklist: Configuring Windows Server</span></span>](../technical-guides/checklist-configuring-windows-server.md)  
  
-   [<span data-ttu-id="c7108-125">チェックリスト: インターネット インフォメーション サービスの構成</span><span class="sxs-lookup"><span data-stu-id="c7108-125">Checklist: Configuring Internet Information Services</span></span>](../technical-guides/checklist-configuring-internet-information-services.md)  
  
-   [<span data-ttu-id="c7108-126">チェックリスト: SQL Server の構成</span><span class="sxs-lookup"><span data-stu-id="c7108-126">Checklist: Configuring SQL Server</span></span>](~/technical-guides/checklist-configuring-sql-server.md)  
  
-   [<span data-ttu-id="c7108-127">チェックリスト: BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="c7108-127">Checklist: Configuring BizTalk Server</span></span>](../technical-guides/checklist-configuring-biztalk-server.md)  
  
-   [<span data-ttu-id="c7108-128">チェックリスト: フォールト トレランスまたは負荷分散を使用した高可用性の実現</span><span class="sxs-lookup"><span data-stu-id="c7108-128">Checklist: Providing High Availability with Fault Tolerance or Load Balancing</span></span>](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)  
  
-   [<span data-ttu-id="c7108-129">チェックリスト: ディザスター リカバリーによる可用性の向上</span><span class="sxs-lookup"><span data-stu-id="c7108-129">Checklist: Increasing Availability with Disaster Recovery</span></span>](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)  
  
-   [<span data-ttu-id="c7108-130">チェックリスト: 運用準備の監視</span><span class="sxs-lookup"><span data-stu-id="c7108-130">Checklist: Monitoring Operational Readiness</span></span>](../technical-guides/checklist-monitoring-operational-readiness.md)  
  
-   [<span data-ttu-id="c7108-131">チェックリスト: BizTalk Server のメンテナンスとトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c7108-131">Checklist: Maintaining and Troubleshooting BizTalk Server Databases</span></span>](~/technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="c7108-132">チェックリスト: 運用準備のテスト</span><span class="sxs-lookup"><span data-stu-id="c7108-132">Checklist: Testing Operational Readiness</span></span>](../technical-guides/checklist-testing-operational-readiness.md)