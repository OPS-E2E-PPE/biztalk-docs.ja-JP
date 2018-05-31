---
title: BizTalk ESB Toolkit の概要 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- ESBToolkitV2.introduction
ms.assetid: 98a957b8-5855-4872-b7e7-58a2e1d6b2b8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e44d3a100cdaefe04cf9d3aedfa8cf969811fc5e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976208"
---
# <a name="introduction-to-the-biztalk-esb-toolkit"></a><span data-ttu-id="5ddd3-102">BizTalk ESB Toolkit の概要</span><span class="sxs-lookup"><span data-stu-id="5ddd3-102">Introduction to the BizTalk ESB Toolkit</span></span>
<span data-ttu-id="5ddd3-103">アーキテクチャと Microsoft の内容について説明します[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="5ddd3-103">Explains the architecture and contents of the Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="5ddd3-104">サービスを有効にする柔軟なセキュリティで保護された、エンタープライズ アプリケーションを開発する Enterprise Service Bus (ESB) アーキテクチャ パターンを適用する方法および再利用可能なサービスと新しいエンド ツー エンドに既存のサービスの迅速な組織にも、ドキュメントを示していますビジネス プロセス。</span><span class="sxs-lookup"><span data-stu-id="5ddd3-104">The documentation also demonstrates how to apply an Enterprise Service Bus (ESB) architecture pattern to develop enterprise applications that enable flexible, secure, and reusable services and rapid organization of existing services into new end-to-end business processes.</span></span>  
  
## <a name="what-is-an-enterprise-service-bus"></a><span data-ttu-id="5ddd3-105">Enterprise Service Bus とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="5ddd3-105">What Is an Enterprise Service Bus?</span></span>  
 <span data-ttu-id="5ddd3-106">Enterprise Service Bus は、サービス指向アーキテクチャ (SOA) を有効にするためのインフラストラクチャの実装のコンテキストで広く使用する用語。</span><span class="sxs-lookup"><span data-stu-id="5ddd3-106">The term Enterprise Service Bus is widely used in the context of implementing an infrastructure for enabling Service-Oriented Architecture (SOA).</span></span> <span data-ttu-id="5ddd3-107">ただし、SOA ソリューションの配置を使用して実際の動作では、こと、ESB は包括的なサービス指向インフラストラクチャ (SOI) をビルドに必要な多くのコンポーネントの 1 つだけが示されています。</span><span class="sxs-lookup"><span data-stu-id="5ddd3-107">However, real-world experience with the deployment of SOA solutions has demonstrated that an ESB is only one of many components required to build a comprehensive Service-Oriented Infrastructure (SOI).</span></span> <span data-ttu-id="5ddd3-108">さまざまな方向で進化してきました"ESB"という用語は、— 個々 の ESB ベンダーおよび統合プラットフォーム ベンダーの解釈とは、特定の SOA イニシアティブの要件とその定義が異なります。</span><span class="sxs-lookup"><span data-stu-id="5ddd3-108">The term "ESB" has evolved in a number of directions—its definition varies with the interpretation of individual ESB and integration platform vendors and with the requirements of particular SOA initiatives.</span></span>  
  
 <span data-ttu-id="5ddd3-109">Microsoft が成功した多くの現実世界 SOI 実装から収集した経験に基づき、Microsoft が判断 Enterprise Service Bus で従来エンタープライズ アプリケーション統合 (EAI)、ベース アーキテクチャのパターンのコレクションであることメッセージ指向ミドルウェア、Web サービス、.NET と Java の相互運用性、ホスト システム統合、およびサービス レジストリおよび資産リポジトリとの相互運用。</span><span class="sxs-lookup"><span data-stu-id="5ddd3-109">Based on the experience Microsoft has gathered from many successful real-world SOI implementations, Microsoft considers an Enterprise Service Bus to be a collection of architectural patterns based on traditional Enterprise Application Integration (EAI), message-oriented middleware, Web services, .NET and Java interoperability, host system integration, and interoperability with service registries and asset repositories.</span></span> <span data-ttu-id="5ddd3-110">図 1 は、エンタープライズ サービス バスのアーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="5ddd3-110">Figure 1 illustrates the architecture of an Enterprise Service Bus.</span></span>  
  
 <span data-ttu-id="5ddd3-111">![ESB の概要](../esb-toolkit/media/esboverview.gif "ESBOverview")</span><span class="sxs-lookup"><span data-stu-id="5ddd3-111">![ESB Overview](../esb-toolkit/media/esboverview.gif "ESBOverview")</span></span>  
  
 <span data-ttu-id="5ddd3-112">**図 1**</span><span class="sxs-lookup"><span data-stu-id="5ddd3-112">**Figure 1**</span></span>  
  
 <span data-ttu-id="5ddd3-113">**Enterprise Service Bus アーキテクチャで提供される接続の概要を示したもの**</span><span class="sxs-lookup"><span data-stu-id="5ddd3-113">**A high-level representation of the connectivity provided by the Enterprise Service Bus architecture**</span></span>  

<!---  Old text with old links
## The Industry View of ESB  
 There are many sources of information about ESB design, architecture, infrastructure, and implementation available from industry suppliers, system integrators, and independent sources.  
-->
<!---    
 IBM defines ESB as a system that "...enables a business to make use of a comprehensive, flexible, and consistent approach to integration while also reducing the complexity of the applications being integrated. Due to the complex and varying nature of business needs, ESB is an evolutional progression that unifies message oriented, event driven and service oriented approaches for integrating applications and service." IBM describes the advantages as "...greater reuse of IT assets by separating application logics and integration tasks, so you can reduce the number, size, and complexity of integration interfaces," and the ability to "...add or change services with minimal interruption to existing IT environment; reduce cost and risk involved as business changes and new opportunities arise." For more information, see [WebSphere software](http://go.microsoft.com/fwlink/p/?LinkId=185958)([http://go.microsoft.com/fwlink/p/?LinkId=185958](http://go.microsoft.com/fwlink/p/?LinkId=185958))on the IBM Web site.  
-->
<!---    Old text with old links
 Sonic Solutions provide a comprehensive examination of ESB, discussing the principle aspects, and the IT and business benefits. They describe the requirement for ESB: "To integrate old and new, service-oriented architecture (SOA) needs an infrastructure that can connect any IT resource, whatever its technology or wherever it is deployed." For more information, see [Enterprise Service Bus (ESB)](http://go.microsoft.com/fwlink/p/?LinkId=185959)([http://go.microsoft.com/fwlink/p/?LinkId=185959](http://go.microsoft.com/fwlink/p/?LinkId=185959)) on the Sonic Solutions Web site.  
-->
<!---    Old text with old links
 TIBCO Software define ESB as "...a standards-based communication layer in a service- oriented architecture (SOA) that enables services to be used across multiple communication protocols [to] simplify service deployment and management, and promote service reuse in a heterogeneous environment." They suggest, in order to provide these capabilities, ESBs "...support both open standards and proprietary technologies, including Web services and UDDI-based registries to discover and publish services, Java Message Service (JMS) and other widely deployed messaging protocols, standards-based (XML) transformations, and basic message routing." For more information, see [Enterprise Service Bus (ESB)](http://go.microsoft.com/fwlink/p/?LinkId=185960)([http://go.microsoft.com/fwlink/?LinkId=185960](http://go.microsoft.com/fwlink/p/?LinkId=185960)) on the TIBCO Web site.  
-->
<!---    Old text with old links
 In the description of his book, Enterprise Service Bus, author David Chappell states that "Rather than conform to the hub-and-spoke architecture of traditional enterprise application integration products, ESB provides a highly distributed approach to integration." He adds "...with unique capabilities that allow individual departments or business units to build out their integration projects in incremental, digestible chunks, maintaining their own local control and autonomy, while still being able to connect together each integration project into a larger, more global integration fabric, or grid." For more information, see Enterprise Service Bus by David Chappell:  
-->
<!---    Old text with old links
-   Chappell, David. Enterprise Service Bus. Sebastopol, CA: O'Reilly Media, Inc. 2004.  
-->

  
## <a name="the-biztalk-esb-toolkit"></a><span data-ttu-id="5ddd3-114">BizTalk ESB Toolkit</span><span class="sxs-lookup"><span data-stu-id="5ddd3-114">The BizTalk ESB Toolkit</span></span>
 <span data-ttu-id="5ddd3-115">このドキュメントでは、全体として設計者と開発者に導入 ESB アーキテクチャ概念によってアドレス指定されると、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]、一般に受け入れられた ESB ユース ケースのセットを ESB コンポーネントの機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="5ddd3-115">This documentation, as a whole, introduces architects and developers to ESB architectural concepts as addressed by the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], and explains the functionality of the ESB components through a set of commonly accepted ESB use cases.</span></span>  
  
 <span data-ttu-id="5ddd3-116">このセクションで説明の概要については、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5ddd3-116">This section provides an introduction to the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], and includes the following topics:</span></span>  
  
-   [<span data-ttu-id="5ddd3-117">BizTalk ESB Toolkit の概要</span><span class="sxs-lookup"><span data-stu-id="5ddd3-117">Overview of the BizTalk ESB Toolkit</span></span>](../esb-toolkit/overview-of-the-biztalk-esb-toolkit.md)  
  
-   [<span data-ttu-id="5ddd3-118">BizTalk ESB Toolkit の内容</span><span class="sxs-lookup"><span data-stu-id="5ddd3-118">Contents of the BizTalk ESB Toolkit</span></span>](../esb-toolkit/contents-of-the-biztalk-esb-toolkit.md)  
  
 <span data-ttu-id="5ddd3-119">このドキュメントには、次のトピックのセクションも含まれます。</span><span class="sxs-lookup"><span data-stu-id="5ddd3-119">This documentation also includes the following topic sections:</span></span>  
  
-   [<span data-ttu-id="5ddd3-120">BizTalk ESB Toolkit の作業の開始</span><span class="sxs-lookup"><span data-stu-id="5ddd3-120">Getting Started with the BizTalk ESB Toolkit</span></span>](../esb-toolkit/getting-started-with-the-biztalk-esb-toolkit.md)  
  
-   [<span data-ttu-id="5ddd3-121">主要なシナリオと開発タスク</span><span class="sxs-lookup"><span data-stu-id="5ddd3-121">Key Scenarios and Development Tasks</span></span>](../esb-toolkit/key-scenarios-and-development-tasks.md)  
  
-   [<span data-ttu-id="5ddd3-122">Itinerary Designer を利用してスケジュールを作成する</span><span class="sxs-lookup"><span data-stu-id="5ddd3-122">Creating Itineraries Using Itinerary Designer</span></span>](../esb-toolkit/creating-itineraries-using-itinerary-designer.md)  
  
-   [<span data-ttu-id="5ddd3-123">BizTalk ESB Toolkit サンプル アプリケーション</span><span class="sxs-lookup"><span data-stu-id="5ddd3-123">BizTalk ESB Toolkit Sample Applications</span></span>](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md)  
  
-   [<span data-ttu-id="5ddd3-124">BizTalk ESB Toolkit を変更し、拡張する</span><span class="sxs-lookup"><span data-stu-id="5ddd3-124">Modifying and Extending the BizTalk ESB Toolkit</span></span>](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)  
  
-   [<span data-ttu-id="5ddd3-125">BizTalk ESB Toolkit による管理</span><span class="sxs-lookup"><span data-stu-id="5ddd3-125">Administration with the BizTalk ESB Toolkit</span></span>](../esb-toolkit/administration-with-the-biztalk-esb-toolkit.md)  
  
-   [<span data-ttu-id="5ddd3-126">SOA ガバナンス統合</span><span class="sxs-lookup"><span data-stu-id="5ddd3-126">SOA Governance Integration</span></span>](../esb-toolkit/soa-governance-integration.md)  
  
-   [<span data-ttu-id="5ddd3-127">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5ddd3-127">Troubleshooting</span></span>](../esb-toolkit/troubleshooting-the-biztalk-esb-toolkit.md)