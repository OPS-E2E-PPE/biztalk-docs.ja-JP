---
title: アップグレードと、アプリケーションのバージョンの戦略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e881def2-c407-4205-a6b3-5c1fa5144bb4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bdf9484d04ff895af42a3321d7ff44651c9bb26
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261325"
---
# <a name="upgrading-and-versioning-strategies-for-applications"></a><span data-ttu-id="23a7e-102">アップグレードして、アプリケーションのバージョン管理戦略</span><span class="sxs-lookup"><span data-stu-id="23a7e-102">Upgrading and Versioning Strategies for Applications</span></span>
<span data-ttu-id="23a7e-103">BizTalk ソリューション サイド バイ サイド、2 つのバージョンを実行する必要がある場合、または新しいバージョンを展開する BizTalk アプリケーションのダウンタイムを使用できない場合、BizTalk アプリケーションのバージョン管理は問題になることができます。</span><span class="sxs-lookup"><span data-stu-id="23a7e-103">BizTalk application versioning can become an issue when you need to run two versions of a BizTalk solution side-by-side, or if you cannot use BizTalk application downtime to deploy a new version.</span></span> <span data-ttu-id="23a7e-104">同時に (たとえば、あるありません実行時間の長いオーケストレーション)、ソリューションの 2 つのバージョンを実行する必要はありません、サービスのメンテナンス ウィンドウが使用できない場合は、古いバージョンの展開を解除して、新しいバージョンをデプロイするまったくバージョン管理戦略 (アセンブリのバージョン管理なし) として</span><span class="sxs-lookup"><span data-stu-id="23a7e-104">If you do not need to run two versions of the solution simultaneously (for example, where you have no long-running orchestrations), and service maintenance windows are available, then it is perfectly acceptable to undeploy the old version, and deploy the new version as a versioning strategy (no assembly versioning).</span></span> <span data-ttu-id="23a7e-105">これは、まだファイルのバージョン番号をインクリメントをお勧めの可能なバージョン管理戦略では、(どのようなバージョンが実行しているコンピューターに展開されていることを知らせる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="23a7e-105">This is a possible versioning strategy, although we still recommend incrementing the file version number (to let you know what version is deployed on the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]).</span></span>  
  
## <a name="when-to-use-versioning"></a><span data-ttu-id="23a7e-106">バージョン管理を使用する場合</span><span class="sxs-lookup"><span data-stu-id="23a7e-106">When to Use Versioning</span></span>  
 <span data-ttu-id="23a7e-107">長時間のオーケストレーションをサポートする必要があるかどうかや BizTalk アプリケーションのダウンタイムなしでの BizTalk アプリケーション展開を実行する必要があり、信頼性の高い、エンド ツー エンドのプラクティスを実装する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のバージョン管理戦略、異なるバージョン管理のシナリオ。</span><span class="sxs-lookup"><span data-stu-id="23a7e-107">If you need to support long-running orchestrations, and/or you need to perform BizTalk application deployments with no BizTalk application downtime, then you need to implement and practice a solid, end-to-end [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] versioning strategy for the different versioning scenarios.</span></span> <span data-ttu-id="23a7e-108">カスタム クラスで呼び出されたオーケストレーションとマップ、ビジネス ルール、および BAM、これは、.NET アセンブリのバージョン管理、スキーマ、マップ、パイプライン、パイプライン コンポーネント、オーケストレーション、カスタム アダプターを含むすべての BizTalk アイテムのバージョン管理が含まれます。</span><span class="sxs-lookup"><span data-stu-id="23a7e-108">This includes .NET assembly versioning and versioning of all BizTalk artifacts, which includes schemas, maps, pipelines, pipeline components, orchestrations, custom adapters, custom classes called in orchestrations and maps, business rules, and BAM.</span></span>  
  
 <span data-ttu-id="23a7e-109">スキーマのバージョン管理されている内で一意で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ターゲット名前空間とルート ノードに基づくメッセージのメッセージの種類を決定するパイプライン、スキーマで定義された名前。</span><span class="sxs-lookup"><span data-stu-id="23a7e-109">Schema versioning is unique in that the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipelines determine the message type of a message based on the target namespace plus root node name defined in the schema.</span></span> <span data-ttu-id="23a7e-110">詳細については、次を参照してください。[スキーマの解決パイプライン コンポーネントで](../core/schema-resolution-in-pipeline-components.md)します。</span><span class="sxs-lookup"><span data-stu-id="23a7e-110">For more information, see [Schema Resolution in Pipeline Components](../core/schema-resolution-in-pipeline-components.md).</span></span> <span data-ttu-id="23a7e-111">スキーマをバージョンにする場合のバージョンのインジケーターはターゲット名前空間の一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="23a7e-111">If you need to version your schemas, a version indicator must be part of the target namespace.</span></span> <span data-ttu-id="23a7e-112">スキーマのバージョンを変更して、ソリューション全体に影響が、そのため、事前に計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23a7e-112">Changing the schema version has a ripple effect throughout your solution, and therefore should be planned in advance.</span></span> <span data-ttu-id="23a7e-113">オーケストレーションのメッセージを作成するときに検索**BizTalk サーバー。8 つのヒントとテクニック プログラミングを向上させる BizTalk** (ヒント 1。常に使用してマルチパート メッセージの種類)。</span><span class="sxs-lookup"><span data-stu-id="23a7e-113">When creating orchestration messages, search for **BizTalk Server: 8 Tips And Tricks For Better BizTalk Programming** (tip 1: Always Use Multi-Part Message Types).</span></span> <span data-ttu-id="23a7e-114">このメソッドを使用して柔軟性の向上とスキーマのバージョン管理します。</span><span class="sxs-lookup"><span data-stu-id="23a7e-114">Use of this method provides greater flexibility when versioning schemas.</span></span>  
  
## <a name="using-factoring-for-assembly-versioning"></a><span data-ttu-id="23a7e-115">アセンブリのバージョン管理のファクタリングを使用してください。</span><span class="sxs-lookup"><span data-stu-id="23a7e-115">Using Factoring for Assembly Versioning</span></span>  
 <span data-ttu-id="23a7e-116">実行時間の長いオーケストレーション、サイド バイ サイドでのデプロイや、ダウンタイムのないアップグレードをサポートする必要がある場合は、アセンブリのバージョン管理とパッケージ化戦略を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23a7e-116">If you need to support long-running orchestrations, side-by-side deployments, or no-downtime upgrades, then you should implement an assembly versioning and packaging strategy.</span></span> <span data-ttu-id="23a7e-117">BizTalk アイテムのアセンブリのバージョン管理を実行するために BizTalk ソリューションのアセンブリ必要がある考慮するを許可するように (パッケージ)[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バージョン管理します。</span><span class="sxs-lookup"><span data-stu-id="23a7e-117">In order to perform assembly versioning of BizTalk artifacts, your BizTalk solution assemblies need to be factored (packaged) in such a way to allow for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] versioning.</span></span>  <span data-ttu-id="23a7e-118">ファクタリングの 3 つの種類があります。</span><span class="sxs-lookup"><span data-stu-id="23a7e-118">There are three types of factoring:</span></span>  
  
-   <span data-ttu-id="23a7e-119">**なしのファクタリング**</span><span class="sxs-lookup"><span data-stu-id="23a7e-119">**No factoring**</span></span>  
  
     <span data-ttu-id="23a7e-120">すべての BizTalk アイテムは、1 つのアセンブリには。</span><span class="sxs-lookup"><span data-stu-id="23a7e-120">All BizTalk artifacts are in one assembly.</span></span> <span data-ttu-id="23a7e-121">これは、最も理解し、デプロイしますが、最小限の柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="23a7e-121">This is the easiest to understand and deploy, but provides the least amount of flexibility.</span></span>  
  
-   <span data-ttu-id="23a7e-122">**完全なファクタリング**</span><span class="sxs-lookup"><span data-stu-id="23a7e-122">**Full factoring**</span></span>  
  
     <span data-ttu-id="23a7e-123">各 BizTalk アイテムが、独自のアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="23a7e-123">Each BizTalk artifact is in its own assembly.</span></span> <span data-ttu-id="23a7e-124">これにより、最高の柔軟性を提供しますが、最も複雑なデプロイを理解するには。</span><span class="sxs-lookup"><span data-stu-id="23a7e-124">This provides the most flexibility, but is the most complex to deploy and understand.</span></span>  
  
-   <span data-ttu-id="23a7e-125">**最適なファクタリング**</span><span class="sxs-lookup"><span data-stu-id="23a7e-125">**Optimal factoring**</span></span>  
  
     <span data-ttu-id="23a7e-126">どこかに間に「ファクタリングありません」と「完全なファクタリング」は、BizTalk アプリケーションの詳細な分析に基づいています。</span><span class="sxs-lookup"><span data-stu-id="23a7e-126">Somewhere in-between “no factoring” and “full factoring” based on in-depth analysis of your BizTalk applications.</span></span> <span data-ttu-id="23a7e-127">バージョン管理、だけでなくこれにより、BizTalk ホストの設計を簡単に実装することです。</span><span class="sxs-lookup"><span data-stu-id="23a7e-127">In addition to versioning, this allows you to easily implement your BizTalk Host design.</span></span> <span data-ttu-id="23a7e-128">これは、BizTalk アイテム間の関係を探すことによって実現されます。</span><span class="sxs-lookup"><span data-stu-id="23a7e-128">This is achieved by looking for relationships among BizTalk artifacts.</span></span> <span data-ttu-id="23a7e-129">成果物をまとめてバージョン管理では常には、同じアセンブリを通常格納できます。</span><span class="sxs-lookup"><span data-stu-id="23a7e-129">Artifacts that are always versioned together can typically be put in the same assembly.</span></span> <span data-ttu-id="23a7e-130">成果物の独立したバージョン管理が必要な場合は、異なるアセンブリに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23a7e-130">If independent versioning of the artifacts is required, then they must be put in different assemblies.</span></span> <span data-ttu-id="23a7e-131">これは、レベルを実現するを取り除いたものです。</span><span class="sxs-lookup"><span data-stu-id="23a7e-131">This is the level of factoring you want to achieve.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="23a7e-132">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="23a7e-132">Additional Resources</span></span>  
  
 <span data-ttu-id="23a7e-133">定義し、確認する必要がありますのサイド バイ サイドで配置方法を提供する solid のバージョン管理戦略を実践します。</span><span class="sxs-lookup"><span data-stu-id="23a7e-133">Define and practice a solid versioning strategy to ensure it provides any side-by-side deployment strategies you might need.</span></span> <span data-ttu-id="23a7e-134">BizTalk Server アプリケーションのアップグレードおよびバージョン管理戦略のリソースを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="23a7e-134">Resources for BizTalk Server application upgrade and versioning strategies include the following:</span></span>  
  
-   [<span data-ttu-id="23a7e-135">アプリケーションの更新</span><span class="sxs-lookup"><span data-stu-id="23a7e-135">Updating an Application</span></span>](../technical-guides/updating-an-application.md)  
  
-   [<span data-ttu-id="23a7e-136">BizTalk アプリケーションの更新</span><span class="sxs-lookup"><span data-stu-id="23a7e-136">Updating BizTalk Applications</span></span>](../core/updating-biztalk-applications.md)
  
-   [<span data-ttu-id="23a7e-137">BizTalk Server プロジェクトのバージョン管理</span><span class="sxs-lookup"><span data-stu-id="23a7e-137">BizTalk Server Project Versioning</span></span>](../core/biztalk-server-project-versioning.md)  
  
-   [<span data-ttu-id="23a7e-138">BizTalk Server アプリケーションの展開を理解します。</span><span class="sxs-lookup"><span data-stu-id="23a7e-138">Understanding BizTalk Server Application Deployment</span></span>](../core/understanding-biztalk-application-deployment-and-management.md)


  
## <a name="see-also"></a><span data-ttu-id="23a7e-139">参照</span><span class="sxs-lookup"><span data-stu-id="23a7e-139">See Also</span></span>  
 [<span data-ttu-id="23a7e-140">チェックリスト:BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="23a7e-140">Checklist: Configuring BizTalk Server</span></span>](../technical-guides/checklist-configuring-biztalk-server.md)
