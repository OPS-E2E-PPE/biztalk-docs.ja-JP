---
title: "BizTalk ESB Toolkit の概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ESBToolkitV2.introduction
ms.assetid: 98a957b8-5855-4872-b7e7-58a2e1d6b2b8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9763e55c44fc3ea45ab93127ffae8c9c742f0dc9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="introduction-to-the-biztalk-esb-toolkit"></a><span data-ttu-id="75497-102">BizTalk ESB Toolkit の概要</span><span class="sxs-lookup"><span data-stu-id="75497-102">Introduction to the BizTalk ESB Toolkit</span></span>
<span data-ttu-id="75497-103">アーキテクチャと Microsoft の内容について説明します[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="75497-103">Explains the architecture and contents of the Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="75497-104">サービスを有効にする柔軟なセキュリティで保護された、エンタープライズ アプリケーションを開発する Enterprise Service Bus (ESB) アーキテクチャ パターンを適用する方法および再利用可能なサービスと新しいエンド ツー エンドに既存のサービスの迅速な組織にも、ドキュメントを示していますビジネス プロセス。</span><span class="sxs-lookup"><span data-stu-id="75497-104">The documentation also demonstrates how to apply an Enterprise Service Bus (ESB) architecture pattern to develop enterprise applications that enable flexible, secure, and reusable services and rapid organization of existing services into new end-to-end business processes.</span></span>  
  
## <a name="what-is-an-enterprise-service-bus"></a><span data-ttu-id="75497-105">Enterprise Service Bus とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="75497-105">What Is an Enterprise Service Bus?</span></span>  
 <span data-ttu-id="75497-106">Enterprise Service Bus は、サービス指向アーキテクチャ (SOA) を有効にするためのインフラストラクチャの実装のコンテキストで広く使用する用語。</span><span class="sxs-lookup"><span data-stu-id="75497-106">The term Enterprise Service Bus is widely used in the context of implementing an infrastructure for enabling Service-Oriented Architecture (SOA).</span></span> <span data-ttu-id="75497-107">ただし、SOA ソリューションの配置を使用して実際の動作では、こと、ESB は包括的なサービス指向インフラストラクチャ (SOI) をビルドに必要な多くのコンポーネントの 1 つだけが示されています。</span><span class="sxs-lookup"><span data-stu-id="75497-107">However, real-world experience with the deployment of SOA solutions has demonstrated that an ESB is only one of many components required to build a comprehensive Service-Oriented Infrastructure (SOI).</span></span> <span data-ttu-id="75497-108">さまざまな方向で進化してきました"ESB"という用語は、— 個々 の ESB ベンダーおよび統合プラットフォーム ベンダーの解釈とは、特定の SOA イニシアティブの要件とその定義が異なります。</span><span class="sxs-lookup"><span data-stu-id="75497-108">The term "ESB" has evolved in a number of directions—its definition varies with the interpretation of individual ESB and integration platform vendors and with the requirements of particular SOA initiatives.</span></span>  
  
 <span data-ttu-id="75497-109">Microsoft が成功した多くの現実世界 SOI 実装から収集した経験に基づき、Microsoft が判断 Enterprise Service Bus で従来エンタープライズ アプリケーション統合 (EAI)、ベース アーキテクチャのパターンのコレクションであることメッセージ指向ミドルウェア、Web サービス、.NET と Java の相互運用性、ホスト システム統合、およびサービス レジストリおよび資産リポジトリとの相互運用。</span><span class="sxs-lookup"><span data-stu-id="75497-109">Based on the experience Microsoft has gathered from many successful real-world SOI implementations, Microsoft considers an Enterprise Service Bus to be a collection of architectural patterns based on traditional Enterprise Application Integration (EAI), message-oriented middleware, Web services, .NET and Java interoperability, host system integration, and interoperability with service registries and asset repositories.</span></span> <span data-ttu-id="75497-110">図 1 は、エンタープライズ サービス バスのアーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="75497-110">Figure 1 illustrates the architecture of an Enterprise Service Bus.</span></span>  
  
 <span data-ttu-id="75497-111">![ESB の概要](../esb-toolkit/media/esboverview.gif "ESBOverview")</span><span class="sxs-lookup"><span data-stu-id="75497-111">![ESB Overview](../esb-toolkit/media/esboverview.gif "ESBOverview")</span></span>  
  
 <span data-ttu-id="75497-112">**図 1**</span><span class="sxs-lookup"><span data-stu-id="75497-112">**Figure 1**</span></span>  
  
 <span data-ttu-id="75497-113">**Enterprise Service Bus アーキテクチャで提供される接続の概要を示したもの**</span><span class="sxs-lookup"><span data-stu-id="75497-113">**A high-level representation of the connectivity provided by the Enterprise Service Bus architecture**</span></span>  

<span data-ttu-id="75497-114">\<!---古いリンクを含む古いテキスト</span><span class="sxs-lookup"><span data-stu-id="75497-114">\<!---  Old text with old links</span></span>
## <a name="the-industry-view-of-esb"></a><span data-ttu-id="75497-115">ESB の業界ビュー</span><span class="sxs-lookup"><span data-stu-id="75497-115">The Industry View of ESB</span></span>  
 <span data-ttu-id="75497-116">ESB デザイン、アーキテクチャ、インフラストラクチャ、および実装に関する情報の多くのソースが業界サプライヤー、システム インテグレーターと独立したソースから入手できます。</span><span class="sxs-lookup"><span data-stu-id="75497-116">There are many sources of information about ESB design, architecture, infrastructure, and implementation available from industry suppliers, system integrators, and independent sources.</span></span>  
<span data-ttu-id="75497-117">-->
\<!---</span><span class="sxs-lookup"><span data-stu-id="75497-117">-->
\<!---</span></span>    
 <span data-ttu-id="75497-118">IBM システムとしての ESB の定義を".. .enables 包括的な柔軟なのでを使用して、一貫した方法でも統合されているアプリケーションの複雑さを削減しながら統合にするのには business です。</span><span class="sxs-lookup"><span data-stu-id="75497-118">IBM defines ESB as a system that "...enables a business to make use of a comprehensive, flexible, and consistent approach to integration while also reducing the complexity of the applications being integrated.</span></span> <span data-ttu-id="75497-119">性質の複雑でさまざまなビジネス ニーズ、ESB はメッセージ指向を統一する evolutional 進行、イベント ドリブンおよびサービス指向アプリケーションとサービスを統合するための方法です。"</span><span class="sxs-lookup"><span data-stu-id="75497-119">Due to the complex and varying nature of business needs, ESB is an evolutional progression that unifies message oriented, event driven and service oriented approaches for integrating applications and service."</span></span> <span data-ttu-id="75497-120">IBM と利点を説明する".. の数、サイズ、および統合インターフェイスの複雑さを減らすことができますので、アプリケーション ロジックと統合タスクを分離することで IT 資産 .greater を再利用"と、権限を許可する".. 最小限に抑えて .add または変更のサービス既存の IT 環境の中断コストとビジネスの変化に伴うリスクを軽減し、新しいビジネス チャンスが発生する。"</span><span class="sxs-lookup"><span data-stu-id="75497-120">IBM describes the advantages as "...greater reuse of IT assets by separating application logics and integration tasks, so you can reduce the number, size, and complexity of integration interfaces," and the ability to "...add or change services with minimal interruption to existing IT environment; reduce cost and risk involved as business changes and new opportunities arise."</span></span> <span data-ttu-id="75497-121">詳細については、次を参照してください。 [WebSphere ソフトウェア](http://go.microsoft.com/fwlink/p/?LinkId=185958)([http://go.microsoft.com/fwlink/p/?LinkId=185958](http://go.microsoft.com/fwlink/p/?LinkId=185958))、IBM の Web サイトにします。</span><span class="sxs-lookup"><span data-stu-id="75497-121">For more information, see [WebSphere software](http://go.microsoft.com/fwlink/p/?LinkId=185958)([http://go.microsoft.com/fwlink/p/?LinkId=185958](http://go.microsoft.com/fwlink/p/?LinkId=185958))on the IBM Web site.</span></span>  
<span data-ttu-id="75497-122">-->
\<!---Sonic ソリューションに提供される、ESB の包括的な検査 IT 原則の側面について説明するリンクが以前に古いテキストとビジネスの利点があります。</span><span class="sxs-lookup"><span data-stu-id="75497-122">-->
\<!---    Old text with old links Sonic Solutions provide a comprehensive examination of ESB, discussing the principle aspects, and the IT and business benefits.</span></span> <span data-ttu-id="75497-123">ESB の要件について説明します"新旧を統合するサービス指向アーキテクチャ (SOA) 必要がありますが接続できる、IT リソース、どのようなインフラストラクチャのテクノロジまたは展開されている任意の場所。"。</span><span class="sxs-lookup"><span data-stu-id="75497-123">They describe the requirement for ESB: "To integrate old and new, service-oriented architecture (SOA) needs an infrastructure that can connect any IT resource, whatever its technology or wherever it is deployed."</span></span> <span data-ttu-id="75497-124">詳細については、次を参照してください。 [Enterprise Service Bus (ESB)](http://go.microsoft.com/fwlink/p/?LinkId=185959)([http://go.microsoft.com/fwlink/p/?LinkId=185959](http://go.microsoft.com/fwlink/p/?LinkId=185959)) Sonic ソリューションの Web サイトにします。</span><span class="sxs-lookup"><span data-stu-id="75497-124">For more information, see [Enterprise Service Bus (ESB)](http://go.microsoft.com/fwlink/p/?LinkId=185959)([http://go.microsoft.com/fwlink/p/?LinkId=185959](http://go.microsoft.com/fwlink/p/?LinkId=185959)) on the Sonic Solutions Web site.</span></span>  
<span data-ttu-id="75497-125">-->
\<!---古いリンク TIBCO ソフトウェアと共に古いテキストを定義として ESB".. をするために複数の通信プロトコルに [] サービスの展開を簡略化するサービスを有効にするサービス指向アーキテクチャ (SOA) で .a 標準ベースの通信レイヤーと管理、異機種混在環境でサービスを再利用を昇格します"。</span><span class="sxs-lookup"><span data-stu-id="75497-125">-->
\<!---    Old text with old links TIBCO Software define ESB as "...a standards-based communication layer in a service- oriented architecture (SOA) that enables services to be used across multiple communication protocols [to] simplify service deployment and management, and promote service reuse in a heterogeneous environment."</span></span> <span data-ttu-id="75497-126">Esb、これらの機能を提供するため、提案、".. 共にオープン標準と Web サービスを検出して発行 UDDI ベース レジストリなど、独自のテクノロジー .support services、Java Message Service (JMS) およびその他の広く導入されています。メッセージング プロトコル、標準に準拠した (XML) 変換、および基本的なメッセージをルーティングします。"</span><span class="sxs-lookup"><span data-stu-id="75497-126">They suggest, in order to provide these capabilities, ESBs "...support both open standards and proprietary technologies, including Web services and UDDI-based registries to discover and publish services, Java Message Service (JMS) and other widely deployed messaging protocols, standards-based (XML) transformations, and basic message routing."</span></span> <span data-ttu-id="75497-127">詳細については、次を参照してください。 [Enterprise Service Bus (ESB)](http://go.microsoft.com/fwlink/p/?LinkId=185960)([http://go.microsoft.com/fwlink/?LinkId=185960](http://go.microsoft.com/fwlink/p/?LinkId=185960)) TIBCO Web サイトです。</span><span class="sxs-lookup"><span data-stu-id="75497-127">For more information, see [Enterprise Service Bus (ESB)](http://go.microsoft.com/fwlink/p/?LinkId=185960)([http://go.microsoft.com/fwlink/?LinkId=185960](http://go.microsoft.com/fwlink/p/?LinkId=185960)) on the TIBCO Web site.</span></span>  
<span data-ttu-id="75497-128">-->
\<!---、著書 Enterprise Service Bus の説明にリンクが以前に古いテキスト作成者 David chappell 氏ことを示す"ではなくより従来のエンタープライズ アプリケーション統合製品のハブ アンド スポーク アーキテクチャに準拠して、ESB は、高分散方法の統合。"</span><span class="sxs-lookup"><span data-stu-id="75497-128">-->
\<!---    Old text with old links In the description of his book, Enterprise Service Bus, author David Chappell states that "Rather than conform to the hub-and-spoke architecture of traditional enterprise application integration products, ESB provides a highly distributed approach to integration."</span></span> <span data-ttu-id="75497-129">追加".. 個々 の部門または事業単位を作成できるようにする過ぎた固有の機能が同時に接続する独自のローカル管理と、自律的なを維持する、増分、という事実のチャンクで、統合プロジェクトの出力ごと統合プロジェクトより大きいより多くのグローバル統合ファブリック、またはグリッドです。"</span><span class="sxs-lookup"><span data-stu-id="75497-129">He adds "...with unique capabilities that allow individual departments or business units to build out their integration projects in incremental, digestible chunks, maintaining their own local control and autonomy, while still being able to connect together each integration project into a larger, more global integration fabric, or grid."</span></span> <span data-ttu-id="75497-130">詳細については、David chappell 氏によって Enterprise Service Bus を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75497-130">For more information, see Enterprise Service Bus by David Chappell:</span></span>  
<span data-ttu-id="75497-131">-->
\<!---古いリンクを含む古いテキスト</span><span class="sxs-lookup"><span data-stu-id="75497-131">-->
\<!---    Old text with old links</span></span>
-   <span data-ttu-id="75497-132">Chappell、David です。</span><span class="sxs-lookup"><span data-stu-id="75497-132">Chappell, David.</span></span> <span data-ttu-id="75497-133">Enterprise Service Bus。</span><span class="sxs-lookup"><span data-stu-id="75497-133">Enterprise Service Bus.</span></span> <span data-ttu-id="75497-134">◆、CA: o ' reilly のメディア, inc.2004.</span><span class="sxs-lookup"><span data-stu-id="75497-134">Sebastopol, CA: O'Reilly Media, Inc. 2004.</span></span>  
-->

  
## <a name="the-biztalk-esb-toolkit"></a><span data-ttu-id="75497-135">BizTalk ESB Toolkit</span><span class="sxs-lookup"><span data-stu-id="75497-135">The BizTalk ESB Toolkit</span></span>
 <span data-ttu-id="75497-136">このドキュメントでは、全体として設計者と開発者に導入 ESB アーキテクチャ概念によってアドレス指定されると、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]、一般に受け入れられた ESB ユース ケースのセットを ESB コンポーネントの機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="75497-136">This documentation, as a whole, introduces architects and developers to ESB architectural concepts as addressed by the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], and explains the functionality of the ESB components through a set of commonly accepted ESB use cases.</span></span>  
  
 <span data-ttu-id="75497-137">このセクションで説明の概要については、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="75497-137">This section provides an introduction to the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], and includes the following topics:</span></span>  
  
-   [<span data-ttu-id="75497-138">BizTalk ESB Toolkit の概要</span><span class="sxs-lookup"><span data-stu-id="75497-138">Overview of the BizTalk ESB Toolkit</span></span>](../esb-toolkit/overview-of-the-biztalk-esb-toolkit.md)  
  
-   [<span data-ttu-id="75497-139">BizTalk ESB Toolkit の内容</span><span class="sxs-lookup"><span data-stu-id="75497-139">Contents of the BizTalk ESB Toolkit</span></span>](../esb-toolkit/contents-of-the-biztalk-esb-toolkit.md)  
  
 <span data-ttu-id="75497-140">このドキュメントには、次のトピックのセクションも含まれます。</span><span class="sxs-lookup"><span data-stu-id="75497-140">This documentation also includes the following topic sections:</span></span>  
  
-   [<span data-ttu-id="75497-141">BizTalk ESB Toolkit の概要</span><span class="sxs-lookup"><span data-stu-id="75497-141">Getting Started with the BizTalk ESB Toolkit</span></span>](../esb-toolkit/getting-started-with-the-biztalk-esb-toolkit.md)  
  
-   [<span data-ttu-id="75497-142">主要なシナリオおよび開発タスク</span><span class="sxs-lookup"><span data-stu-id="75497-142">Key Scenarios and Development Tasks</span></span>](../esb-toolkit/key-scenarios-and-development-tasks.md)  
  
-   [<span data-ttu-id="75497-143">Itinerary Designer を使用して日程を作成します。</span><span class="sxs-lookup"><span data-stu-id="75497-143">Creating Itineraries Using Itinerary Designer</span></span>](../esb-toolkit/creating-itineraries-using-itinerary-designer.md)  
  
-   [<span data-ttu-id="75497-144">BizTalk ESB Toolkit のサンプル アプリケーション</span><span class="sxs-lookup"><span data-stu-id="75497-144">BizTalk ESB Toolkit Sample Applications</span></span>](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md)  
  
-   [<span data-ttu-id="75497-145">変更して、BizTalk ESB Toolkit の拡張</span><span class="sxs-lookup"><span data-stu-id="75497-145">Modifying and Extending the BizTalk ESB Toolkit</span></span>](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)  
  
-   [<span data-ttu-id="75497-146">BizTalk ESB Toolkit を使用した管理</span><span class="sxs-lookup"><span data-stu-id="75497-146">Administration with the BizTalk ESB Toolkit</span></span>](../esb-toolkit/administration-with-the-biztalk-esb-toolkit.md)  
  
-   [<span data-ttu-id="75497-147">SOA ガバナンスの統合</span><span class="sxs-lookup"><span data-stu-id="75497-147">SOA Governance Integration</span></span>](../esb-toolkit/soa-governance-integration.md)  
  
-   [<span data-ttu-id="75497-148">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="75497-148">Troubleshooting</span></span>](../esb-toolkit/troubleshooting-the-biztalk-esb-toolkit.md)