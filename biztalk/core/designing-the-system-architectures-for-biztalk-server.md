---
title: BizTalk Server のシステム アーキテクチャの設計 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, security
- security, deploying
ms.assetid: b7ded72a-2487-4bb7-9894-cd13235a52c7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a18656a2d4d3827cd38a3f791af2ac856df8ce36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239274"
---
# <a name="designing-the-system-architectures-for-biztalk-server"></a><span data-ttu-id="d7e46-102">BizTalk Server のシステム アーキテクチャの設計</span><span class="sxs-lookup"><span data-stu-id="d7e46-102">Designing the System Architectures for BizTalk Server</span></span>
<span data-ttu-id="d7e46-103">セキュリティ、パフォーマンス、可用性、および運用に関する Microsoft® BizTalk® Server 展開の要件は、ビジネス ニーズ、要件、パートナー、企業規模などにより大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="d7e46-103">The requirements of your Microsoft® BizTalk® Server deployment for security, performance, availability, and operation are highly dependent on your business needs, requirements, partners, company size, and so on.</span></span> <span data-ttu-id="d7e46-104">BizTalk Server コンポーネントのいずれかの構成を典型としてとらえたり、その構成のための規範的なガイダンスを示すことは困難ですが、このセクションでは、大規模なエンタープライズの実稼動環境において、セキュリティで保護された分散構成で BizTalk Server のさまざまな機能を構成する方法に関するガイダンスおよび推奨事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7e46-104">While it is difficult to consider any single configuration of BizTalk Server components as typical and provide prescriptive guidance for it, this section provides guidance and recommendations on how to configure the different BizTalk Server features in a distributed, secure configuration for the production environment of a large enterprise.</span></span>  
  
 <span data-ttu-id="d7e46-105">このセクションで紹介するアーキテクチャは、多層防御を考慮に入れた高度な分散環境での BizTalk Server の展開に関する参照情報を提供することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="d7e46-105">The architectures presented in this section aim to provide you with reference information about deploying BizTalk Server in a highly distributed environment where you take into consideration defense in depth.</span></span> <span data-ttu-id="d7e46-106">BizTalk Server の各アプリケーションには、問題ドメイン、使用するプロトコル、およびソリューションを運用する特定の環境に基づいたセキュリティに関する固有の要件があります。</span><span class="sxs-lookup"><span data-stu-id="d7e46-106">Every application for BizTalk Server is likely to have its own unique set of security requirements based on the problem domain, the protocols used, and the particular environment the solution operates in.</span></span> <span data-ttu-id="d7e46-107">さらに、パフォーマンス、可用性、およびコストに関する検討事項によっても要件は異なります。</span><span class="sxs-lookup"><span data-stu-id="d7e46-107">Performance, availability, and cost considerations further influence these requirements.</span></span> <span data-ttu-id="d7e46-108">このドキュメントで説明するアーキテクチャおよび推奨事項は、実際の企業のニーズ、脅威、および資産に合わせてカスタマイズした独自の BizTalk Server 展開を作成する際の構成要素として使用してください。</span><span class="sxs-lookup"><span data-stu-id="d7e46-108">You should use these architectures and the recommendations within this document as the building blocks to create your own BizTalk Server deployment tailored to the needs, threats and assets of your company.</span></span>  
  
 <span data-ttu-id="d7e46-109">このセクションには、BizTalk Server のさまざまな機能と、サーバーが処理および格納するデータをセキュリティで保護するために BizTalk Server のシステム アーキテクチャを設計する方法と、攻撃や災害などの際に重要なデータとサーバーが危険にさらされる可能性を最小限に抑える分散環境にサーバーを配置する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7e46-109">This section contains information about how you can design the system architecture for BizTalk Server to secure the different features in BizTalk Server, and consequently, secure the data that the servers process and store, and how to place the servers in a distributed environment that minimize the potential for critical data and servers being compromised in the event of an attack or disaster.</span></span> <span data-ttu-id="d7e46-110">このセクションでは、開発環境やテスト環境を構成するための推奨事項と、実稼動環境にアセンブリを展開するための詳細については説明しません。</span><span class="sxs-lookup"><span data-stu-id="d7e46-110">This section does not provide recommendations for configuring development, or test environments, or details for deploying an assembly into a production environment.</span></span> <span data-ttu-id="d7e46-111">アセンブリの展開の詳細については、次を参照してください。 [Understanding BizTalk アプリケーションの展開と管理](../core/understanding-biztalk-application-deployment-and-management.md)です。</span><span class="sxs-lookup"><span data-stu-id="d7e46-111">For more information about deploying assemblies, see [Understanding BizTalk Application Deployment and Management](../core/understanding-biztalk-application-deployment-and-management.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d7e46-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d7e46-112">In This Section</span></span>  
  
-   [<span data-ttu-id="d7e46-113">セキュリティで保護されたアーキテクチャの設計</span><span class="sxs-lookup"><span data-stu-id="d7e46-113">Designing a Secure Architecture</span></span>](../core/designing-a-secure-architecture.md)  
  
-   [<span data-ttu-id="d7e46-114">分散アーキテクチャの設計</span><span class="sxs-lookup"><span data-stu-id="d7e46-114">Designing a Distributed Architecture</span></span>](../core/designing-a-distributed-architecture.md)  
  
-   [<span data-ttu-id="d7e46-115">BizTalk Server のサンプル アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="d7e46-115">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)