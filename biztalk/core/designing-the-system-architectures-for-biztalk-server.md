---
title: BizTalk Server のシステム アーキテクチャの設計 |Microsoft Docs
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
ms.openlocfilehash: 7e201f408303ef5a45d512bfbdcafda4c4732a73
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351685"
---
# <a name="designing-the-system-architectures-for-biztalk-server"></a><span data-ttu-id="72b50-102">BizTalk Server のシステム アーキテクチャの設計</span><span class="sxs-lookup"><span data-stu-id="72b50-102">Designing the System Architectures for BizTalk Server</span></span>
<span data-ttu-id="72b50-103">Microsoft® BizTalk® Server 配置のセキュリティ、パフォーマンス、可用性、および操作の要件は、ビジネス ニーズ、要件、パートナー、会社の規模、および具合に大きく依存します。</span><span class="sxs-lookup"><span data-stu-id="72b50-103">The requirements of your Microsoft® BizTalk® Server deployment for security, performance, availability, and operation are highly dependent on your business needs, requirements, partners, company size, and so on.</span></span> <span data-ttu-id="72b50-104">一般的な BizTalk Server コンポーネントのいずれかの構成を検討し、そのための規範ガイダンスを提供することは困難です、このセクションではガイダンスと推奨事項を BizTalk Server のさまざまな機能を構成する方法、大規模な企業の運用環境の分散、セキュリティで保護された構成。</span><span class="sxs-lookup"><span data-stu-id="72b50-104">While it is difficult to consider any single configuration of BizTalk Server components as typical and provide prescriptive guidance for it, this section provides guidance and recommendations on how to configure the different BizTalk Server features in a distributed, secure configuration for the production environment of a large enterprise.</span></span>  
  
 <span data-ttu-id="72b50-105">このセクションで紹介するアーキテクチャは、防御について考慮対象として行う高度な分散環境で BizTalk Server の展開に関する参照情報を提供することを目指します。</span><span class="sxs-lookup"><span data-stu-id="72b50-105">The architectures presented in this section aim to provide you with reference information about deploying BizTalk Server in a highly distributed environment where you take into consideration defense in depth.</span></span> <span data-ttu-id="72b50-106">BizTalk Server のすべてのアプリケーションが問題ドメイン、使用されているプロトコルに基づくセキュリティ要件の独自セットがあり、特定の環境ソリューションで動作します。</span><span class="sxs-lookup"><span data-stu-id="72b50-106">Every application for BizTalk Server is likely to have its own unique set of security requirements based on the problem domain, the protocols used, and the particular environment the solution operates in.</span></span> <span data-ttu-id="72b50-107">パフォーマンス、可用性、およびコストの注意点は、これらの要件に影響します。</span><span class="sxs-lookup"><span data-stu-id="72b50-107">Performance, availability, and cost considerations further influence these requirements.</span></span> <span data-ttu-id="72b50-108">独自のニーズ、脅威と、会社の資産に応じた BizTalk Server の展開を作成するのに構成要素としてこれらのアーキテクチャと、このドキュメント内の推奨事項を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72b50-108">You should use these architectures and the recommendations within this document as the building blocks to create your own BizTalk Server deployment tailored to the needs, threats and assets of your company.</span></span>  
  
 <span data-ttu-id="72b50-109">このセクションにはでサーバーを配置する方法と、BizTalk Server のさまざまな機能をセキュリティで保護する BizTalk Server のシステム アーキテクチャを設計し、その結果、サーバーの処理や保存、データをセキュリティで保護する方法の詳細情報が含まれています、分散環境の重要なデータとサーバーが、攻撃や災害が発生した場合に侵害される可能性が最小限にします。</span><span class="sxs-lookup"><span data-stu-id="72b50-109">This section contains information about how you can design the system architecture for BizTalk Server to secure the different features in BizTalk Server, and consequently, secure the data that the servers process and store, and how to place the servers in a distributed environment that minimize the potential for critical data and servers being compromised in the event of an attack or disaster.</span></span> <span data-ttu-id="72b50-110">このセクションでは、構成、開発に関する推奨事項を提供またはテスト環境を運用環境にアセンブリを展開するための詳細はできません。</span><span class="sxs-lookup"><span data-stu-id="72b50-110">This section does not provide recommendations for configuring development, or test environments, or details for deploying an assembly into a production environment.</span></span> <span data-ttu-id="72b50-111">アセンブリの展開の詳細については、次を参照してください。 [Understanding BizTalk アプリケーションの展開と管理](../core/understanding-biztalk-application-deployment-and-management.md)します。</span><span class="sxs-lookup"><span data-stu-id="72b50-111">For more information about deploying assemblies, see [Understanding BizTalk Application Deployment and Management](../core/understanding-biztalk-application-deployment-and-management.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="72b50-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="72b50-112">In This Section</span></span>  
  
-   [<span data-ttu-id="72b50-113">セキュリティ保護アーキテクチャの設計</span><span class="sxs-lookup"><span data-stu-id="72b50-113">Designing a Secure Architecture</span></span>](../core/designing-a-secure-architecture.md)  
  
-   [<span data-ttu-id="72b50-114">分散アーキテクチャの設計</span><span class="sxs-lookup"><span data-stu-id="72b50-114">Designing a Distributed Architecture</span></span>](../core/designing-a-distributed-architecture.md)  
  
-   [<span data-ttu-id="72b50-115">BizTalk Server のサンプル アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="72b50-115">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)