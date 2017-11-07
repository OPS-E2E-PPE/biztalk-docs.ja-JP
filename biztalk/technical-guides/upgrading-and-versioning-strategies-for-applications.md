---
title: "アップグレードとアプリケーションのバージョン方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e881def2-c407-4205-a6b3-5c1fa5144bb4
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf239b00d45d62a0ee3587baaea40482bfe50667
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="upgrading-and-versioning-strategies-for-applications"></a><span data-ttu-id="d3cc9-102">アップグレードとアプリケーションのバージョン管理方法</span><span class="sxs-lookup"><span data-stu-id="d3cc9-102">Upgrading and Versioning Strategies for Applications</span></span>
<span data-ttu-id="d3cc9-103">BizTalk ソリューション サイド バイ サイド、2 つのバージョンを実行する必要がある場合、または新しいバージョンを展開する BizTalk アプリケーションのダウンタイムを使用できない場合、BizTalk アプリケーションのバージョン管理は問題になることができます。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-103">BizTalk application versioning can become an issue when you need to run two versions of a BizTalk solution side-by-side, or if you cannot use BizTalk application downtime to deploy a new version.</span></span> <span data-ttu-id="d3cc9-104">同時に (たとえば、あるありません長時間のオーケストレーション)、ソリューションの 2 つのバージョンを実行する必要はありません、サービスのメンテナンス期間使用できない場合、完全に再現してもかまいません。 以前のバージョンを展開解除し、新しいバージョンをデプロイし、バージョン管理戦略 (アセンブリのバージョン管理なし) として</span><span class="sxs-lookup"><span data-stu-id="d3cc9-104">If you do not need to run two versions of the solution simultaneously (for example, where you have no long-running orchestrations), and service maintenance windows are available, then it is perfectly acceptable to undeploy the old version, and deploy the new version as a versioning strategy (no assembly versioning).</span></span> <span data-ttu-id="d3cc9-105">これが可能なバージョン管理の戦略では、まだファイル バージョン番号のインクリメントをお勧め (バージョンが実行しているコンピューターに展開されていることを確認できますを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-105">This is a possible versioning strategy, although we still recommend incrementing the file version number (to let you know what version is deployed on the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]).</span></span>  
  
## <a name="when-to-use-versioning"></a><span data-ttu-id="d3cc9-106">バージョン管理を使用する場合</span><span class="sxs-lookup"><span data-stu-id="d3cc9-106">When to Use Versioning</span></span>  
 <span data-ttu-id="d3cc9-107">かどうかは、長時間のオーケストレーションをサポートする必要があります、または BizTalk アプリケーションのダウンタイムなしでの BizTalk アプリケーション展開を実行する必要があります、信頼性の高いエンド ツー エンドのプラクティスを実装する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のバージョン管理の戦略、異なるバージョン管理のシナリオです。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-107">If you need to support long-running orchestrations, and/or you need to perform BizTalk application deployments with no BizTalk application downtime, then you need to implement and practice a solid, end-to-end [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] versioning strategy for the different versioning scenarios.</span></span> <span data-ttu-id="d3cc9-108">これは、.NET アセンブリのバージョン管理スキーマ、マップ、パイプライン、パイプライン コンポーネント、オーケストレーション、カスタム アダプターを含む、すべての BizTalk アイテムのバージョン管理、およびカスタム クラスで呼び出されたオーケストレーションとマップ、ビジネス ルール、および BAM です。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-108">This includes .NET assembly versioning and versioning of all BizTalk artifacts, which includes schemas, maps, pipelines, pipeline components, orchestrations, custom adapters, custom classes called in orchestrations and maps, business rules, and BAM.</span></span>  
  
 <span data-ttu-id="d3cc9-109">スキーマのバージョン管理されている内で一意で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パイプラインによって決定されます、ターゲットの名前空間とルート ノードに基づくメッセージのメッセージの種類、スキーマで定義された名前です。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-109">Schema versioning is unique in that the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipelines determine the message type of a message based on the target namespace plus root node name defined in the schema.</span></span> <span data-ttu-id="d3cc9-110">詳細については、次を参照してください。[スキーマの解決パイプライン コンポーネントで](../core/schema-resolution-in-pipeline-components.md)です。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-110">For more information, see [Schema Resolution in Pipeline Components](../core/schema-resolution-in-pipeline-components.md).</span></span> <span data-ttu-id="d3cc9-111">スキーマをバージョンにする場合、バージョン インジケーターは、ターゲットの名前空間の一部をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-111">If you need to version your schemas, a version indicator must be part of the target namespace.</span></span> <span data-ttu-id="d3cc9-112">スキーマのバージョンの変更、ソリューション全体に影響がありそのため、事前に計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-112">Changing the schema version has a ripple effect throughout your solution, and therefore should be planned in advance.</span></span> <span data-ttu-id="d3cc9-113">オーケストレーションのメッセージを作成するときに検索**BizTalk サーバー: 向上 BizTalk プログラミングの 8 ヒントとテクニック**(1 のヒント: マルチパート メッセージ型を使用して常に)。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-113">When creating orchestration messages, search for **BizTalk Server: 8 Tips And Tricks For Better BizTalk Programming** (tip 1: Always Use Multi-Part Message Types).</span></span> <span data-ttu-id="d3cc9-114">このメソッドを使用する柔軟性の向上とスキーマのバージョン管理します。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-114">Use of this method provides greater flexibility when versioning schemas.</span></span>  
  
## <a name="using-factoring-for-assembly-versioning"></a><span data-ttu-id="d3cc9-115">アセンブリのバージョン管理のファクタリングを使用します。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-115">Using Factoring for Assembly Versioning</span></span>  
 <span data-ttu-id="d3cc9-116">長時間のオーケストレーション、サイド バイ サイド展開やダウンタイムのないアップグレードをサポートする必要がある場合は、アセンブリのバージョン管理とパッケージ化戦略を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-116">If you need to support long-running orchestrations, side-by-side deployments, or no-downtime upgrades, then you should implement an assembly versioning and packaging strategy.</span></span> <span data-ttu-id="d3cc9-117">BizTalk アイテムのアセンブリのバージョン管理を実行するために、BizTalk ソリューションのアセンブリ必要がある考慮する (パッケージ) を許可するように[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バージョン管理します。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-117">In order to perform assembly versioning of BizTalk artifacts, your BizTalk solution assemblies need to be factored (packaged) in such a way to allow for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] versioning.</span></span>  <span data-ttu-id="d3cc9-118">リファクタリングに関する次の 3 つの種類があります。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-118">There are three types of factoring:</span></span>  
  
-   <span data-ttu-id="d3cc9-119">**ありませんファクタリング**</span><span class="sxs-lookup"><span data-stu-id="d3cc9-119">**No factoring**</span></span>  
  
     <span data-ttu-id="d3cc9-120">すべての BizTalk アイテムは、1 つのアセンブリでです。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-120">All BizTalk artifacts are in one assembly.</span></span> <span data-ttu-id="d3cc9-121">これは、最も理解および展開するが最低限の柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-121">This is the easiest to understand and deploy, but provides the least amount of flexibility.</span></span>  
  
-   <span data-ttu-id="d3cc9-122">**完全ファクタリング**</span><span class="sxs-lookup"><span data-stu-id="d3cc9-122">**Full factoring**</span></span>  
  
     <span data-ttu-id="d3cc9-123">各 BizTalk 成果物は、独自のアセンブリでです。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-123">Each BizTalk artifact is in its own assembly.</span></span> <span data-ttu-id="d3cc9-124">これは、最大限の柔軟性を提供が複雑では、最もを展開し、理解します。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-124">This provides the most flexibility, but is the most complex to deploy and understand.</span></span>  
  
-   <span data-ttu-id="d3cc9-125">**最適なファクタリング**</span><span class="sxs-lookup"><span data-stu-id="d3cc9-125">**Optimal factoring**</span></span>  
  
     <span data-ttu-id="d3cc9-126">どこかに中間「ファクタリングなし」と「完全ファクタリング」は、BizTalk アプリケーションの詳細な分析に基づいています。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-126">Somewhere in-between “no factoring” and “full factoring” based on in-depth analysis of your BizTalk applications.</span></span> <span data-ttu-id="d3cc9-127">バージョン管理、に加えてこれにより、BizTalk ホストの設計を簡単に実装できます。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-127">In addition to versioning, this allows you to easily implement your BizTalk Host design.</span></span> <span data-ttu-id="d3cc9-128">これは、BizTalk アイテム間の関係を探すことにより実現されます。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-128">This is achieved by looking for relationships among BizTalk artifacts.</span></span> <span data-ttu-id="d3cc9-129">常には、バージョンが一緒にいる成果物は、同じアセンブリに通常配置できます。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-129">Artifacts that are always versioned together can typically be put in the same assembly.</span></span> <span data-ttu-id="d3cc9-130">成果物の独立したバージョンが必要な場合は、異なるアセンブリに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-130">If independent versioning of the artifacts is required, then they must be put in different assemblies.</span></span> <span data-ttu-id="d3cc9-131">これは、レベルを実現したいのファクタリングします。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-131">This is the level of factoring you want to achieve.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="d3cc9-132">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="d3cc9-132">Additional Resources</span></span>  
  
 <span data-ttu-id="d3cc9-133">定義し、練習をする必要がありますのサイド バイ サイドの配置方法を提供することを確認する方法を純色のバージョン管理します。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-133">Define and practice a solid versioning strategy to ensure it provides any side-by-side deployment strategies you might need.</span></span> <span data-ttu-id="d3cc9-134">BizTalk Server アプリケーションのアップグレードおよびバージョン管理の戦略のリソースを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-134">Resources for BizTalk Server application upgrade and versioning strategies include the following:</span></span>  
  
-   [<span data-ttu-id="d3cc9-135">アプリケーションの更新</span><span class="sxs-lookup"><span data-stu-id="d3cc9-135">Updating an Application</span></span>](../technical-guides/updating-an-application.md)  
  
-   [<span data-ttu-id="d3cc9-136">BizTalk アプリケーションの更新</span><span class="sxs-lookup"><span data-stu-id="d3cc9-136">Updating BizTalk Applications</span></span>](../core/updating-biztalk-applications.md)
  
-   [<span data-ttu-id="d3cc9-137">BizTalk Server プロジェクトのバージョン管理</span><span class="sxs-lookup"><span data-stu-id="d3cc9-137">BizTalk Server Project Versioning</span></span>](../core/biztalk-server-project-versioning.md)  
  
-   [<span data-ttu-id="d3cc9-138">BizTalk Server アプリケーションの展開を理解します。</span><span class="sxs-lookup"><span data-stu-id="d3cc9-138">Understanding BizTalk Server Application Deployment</span></span>](../core/understanding-biztalk-application-deployment-and-management.md)


  
## <a name="see-also"></a><span data-ttu-id="d3cc9-139">参照</span><span class="sxs-lookup"><span data-stu-id="d3cc9-139">See Also</span></span>  
 [<span data-ttu-id="d3cc9-140">チェックリスト: BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="d3cc9-140">Checklist: Configuring BizTalk Server</span></span>](../technical-guides/checklist-configuring-biztalk-server.md)
