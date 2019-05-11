---
title: SOA ガバナンス統合 BizTalk Server で ESB Toolkit |Microsoft Docs
description: BizTalk Server で ESB Toolkit を使用した、SOA ベースのシステムおよびサードパーティの統合に関する課題の一覧
caps.latest.revision: 3
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccb5ac2d-cd90-414d-a6c7-045a8fe9450b
ms.author: mandia
ms.openlocfilehash: c2dcdc9f40d31a8ea037b1475cdb7a9a1380de44
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268793"
---
# <a name="soa-governance-integration"></a><span data-ttu-id="64431-103">SOA ガバナンス統合</span><span class="sxs-lookup"><span data-stu-id="64431-103">SOA Governance Integration</span></span>
<span data-ttu-id="64431-104">エンタープライズ レベルのアプリケーションでは、ビジネス要件、政府の法律制定、サービス レベル アグリーメント (Sla) など、顧客およびパートナーの要望を取引先に準拠できる堅牢で信頼性の高い管理機能をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="64431-104">Enterprise-level applications must support robust and reliable management features to be able to comply with business requirements, government legislation, service level agreements (SLAs), and customer and trading partner expectations.</span></span> <span data-ttu-id="64431-105">実行時のガバナンスについて重点的に具体的には、課題と要件、サービス指向アーキテクチャ (SOA) を正常に実行 – ベースのシステムをこれらの要件を満たします。</span><span class="sxs-lookup"><span data-stu-id="64431-105">Run-time governance focuses specifically on the challenges of, and requirements for, successfully running service-oriented architecture (SOA)–based systems that meet these requirements.</span></span> <span data-ttu-id="64431-106">ビジネス システムによって提供されるサービスの品質は、その成功または失敗を定義する主要な要素です。</span><span class="sxs-lookup"><span data-stu-id="64431-106">The quality of service delivered by a business system is the predominant factor that defines its success or failure.</span></span>  

## <a name="soa-challenges"></a><span data-ttu-id="64431-107">SOA における課題</span><span class="sxs-lookup"><span data-stu-id="64431-107">SOA challenges</span></span>  
 <span data-ttu-id="64431-108">さまざまな課題は、次のようを運用環境に SOA ベースのシステムを展開する企業に直面します。</span><span class="sxs-lookup"><span data-stu-id="64431-108">Businesses deploying SOA-based systems into production face a number of challenges, including the following:</span></span>  

-   <span data-ttu-id="64431-109">メンテナンスと、アップグレードのコストを最小限に抑えることと、増分更新を許可します。</span><span class="sxs-lookup"><span data-stu-id="64431-109">Minimizing the cost of maintenance and upgrades, and allowing incremental updates</span></span>  

-   <span data-ttu-id="64431-110">ビジネス プロセス管理および構成ツールを使用して迅速な変更を許可します。</span><span class="sxs-lookup"><span data-stu-id="64431-110">Allowing rapid change through business process management and composition tools</span></span>  

-   <span data-ttu-id="64431-111">エンド ツー エンドのセキュリティこれは信頼とメッセージの送信者、受信者、およびコンテンツのプライバシーの保護が含まれます。</span><span class="sxs-lookup"><span data-stu-id="64431-111">End-to-end security; this includes trust and protection of the privacy of message senders, receivers, and content</span></span>  

-   <span data-ttu-id="64431-112">識別する、管理、および発生すると、例外を修復します。</span><span class="sxs-lookup"><span data-stu-id="64431-112">Identifying, managing, and repairing exceptions as they occur</span></span>  

-   <span data-ttu-id="64431-113">サービスとコンシューマーの分離</span><span class="sxs-lookup"><span data-stu-id="64431-113">Decoupling of services and consumers</span></span>  

-   <span data-ttu-id="64431-114">測定とコストの問題をオフセットする SOA アプリケーションのビジネス価値を証明します。</span><span class="sxs-lookup"><span data-stu-id="64431-114">Measuring and proving the business value of SOA applications to offset cost concerns</span></span>  

-   <span data-ttu-id="64431-115">重複またはそれ以外の場合に不要なサービスの急増の制御 (管理)</span><span class="sxs-lookup"><span data-stu-id="64431-115">Control (governance) of the proliferation of duplicate or otherwise unnecessary services</span></span>  

-   <span data-ttu-id="64431-116">潜在的なユーザーが初期の開発コストを削減するために必要な適切なサービスの id をサポートすること</span><span class="sxs-lookup"><span data-stu-id="64431-116">Facilitating the identification of the appropriate services required by potential users to reduce initial development cost</span></span>  

-   <span data-ttu-id="64431-117">コストと継続的なメンテナンスのリスクを最小限に抑える変更をサービスのライフ サイクルを管理します。</span><span class="sxs-lookup"><span data-stu-id="64431-117">Managing the life cycle of services to minimize the cost and risk of ongoing maintenance and change</span></span>  

-   <span data-ttu-id="64431-118">適切なサービス (切り離し、場所、トランスポート、ポリシー、標準、およびスタイルのメッセージング) の実際の使用量を簡略化します。</span><span class="sxs-lookup"><span data-stu-id="64431-118">Simplifying the actual usage of appropriate services (decoupling location, transport, policies, standards, and messaging styles)</span></span>  

-   <span data-ttu-id="64431-119">使用してユーザーをサービスでは、場所、および理由を識別するために使用される機能の報告</span><span class="sxs-lookup"><span data-stu-id="64431-119">Reporting facilities used to identify who is using which service, where, and why</span></span>  

## <a name="next-steps"></a><span data-ttu-id="64431-120">次のステップ</span><span class="sxs-lookup"><span data-stu-id="64431-120">Next steps</span></span>
 <span data-ttu-id="64431-121">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] 2 つの実行時のガバナンスをサード パーティ製システムとの統合をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="64431-121">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports integration with two third-party run-time governance systems:</span></span>  

- <span data-ttu-id="64431-122">**Sentinet SOA 競合回避モジュールと BizTalk Server の拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="64431-122">**Sentinet SOA Resolver and BizTalk Server Extensions**.</span></span> <span data-ttu-id="64431-123">Sentinet の拡張の詳細については[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]機能を参照してください[Sentinet による BizTalk ESB Toolkit 機能を拡張する](../technical-guides/extending-biztalk-esb-toolkit-capabilities-with-sentinet.md)します。</span><span class="sxs-lookup"><span data-stu-id="64431-123">For more information on how Sentinet extends [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] capabilities, see [Extending BizTalk ESB Toolkit Capabilities with Sentinet](../technical-guides/extending-biztalk-esb-toolkit-capabilities-with-sentinet.md).</span></span>

- <span data-ttu-id="64431-124">[SOA BizTalk 管理ポイント](../esb-toolkit/soa-biztalk-management-point.md)SOA Software, Inc. から</span><span class="sxs-lookup"><span data-stu-id="64431-124">[SOA BizTalk Management Point](../esb-toolkit/soa-biztalk-management-point.md) from SOA Software, Inc.</span></span>  

- <span data-ttu-id="64431-125">[AmberPoint BizTalk Nano エージェント](../esb-toolkit/amberpoint-biztalk-nano-agent.md)AmberPoint, inc.</span><span class="sxs-lookup"><span data-stu-id="64431-125">[AmberPoint BizTalk Nano Agent](../esb-toolkit/amberpoint-biztalk-nano-agent.md) from AmberPoint, Inc.</span></span>
