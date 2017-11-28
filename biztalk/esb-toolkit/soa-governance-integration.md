---
title: "BizTalk Server で ESB Toolkit の SOA ガバナンス統合 |Microsoft ドキュメント"
description: "BizTalk Server で ESB ツールキットを使用して、SOA ベースのシステムおよびサード パーティ統合での課題の一覧"
caps.latest.revision: "3"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ccb5ac2d-cd90-414d-a6c7-045a8fe9450b
ms.author: mandia
ms.openlocfilehash: 9e1489e01a8918d1dfa7ca61a69d57f5d7316f68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="soa-governance-integration"></a><span data-ttu-id="66c02-103">SOA ガバナンスの統合</span><span class="sxs-lookup"><span data-stu-id="66c02-103">SOA Governance Integration</span></span>
<span data-ttu-id="66c02-104">エンタープライズ レベルのアプリケーションでは、ビジネス要件、政府法律、サービス レベル アグリーメント (Sla)、および顧客とパートナーの要望を取引に従っていることができる堅牢性と信頼性の管理機能をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="66c02-104">Enterprise-level applications must support robust and reliable management features to be able to comply with business requirements, government legislation, service level agreements (SLAs), and customer and trading partner expectations.</span></span> <span data-ttu-id="66c02-105">実行時のガバナンス焦点を具体的にはの課題と要件については、サービス指向アーキテクチャ (SOA) を正常に実行する – ベースのこれらの要件を満たすシステムです。</span><span class="sxs-lookup"><span data-stu-id="66c02-105">Run-time governance focuses specifically on the challenges of, and requirements for, successfully running service-oriented architecture (SOA)–based systems that meet these requirements.</span></span> <span data-ttu-id="66c02-106">ビジネス システムによって提供されるサービスの品質は、その成功または失敗を定義する主要な要素です。</span><span class="sxs-lookup"><span data-stu-id="66c02-106">The quality of service delivered by a business system is the predominant factor that defines its success or failure.</span></span>  

## <a name="soa-challenges"></a><span data-ttu-id="66c02-107">SOA の課題</span><span class="sxs-lookup"><span data-stu-id="66c02-107">SOA challenges</span></span>  
 <span data-ttu-id="66c02-108">運用環境に SOA ベースのシステムを展開する企業は、多くの課題は、次のように直面します。</span><span class="sxs-lookup"><span data-stu-id="66c02-108">Businesses deploying SOA-based systems into production face a number of challenges, including the following:</span></span>  
  
-   <span data-ttu-id="66c02-109">メンテナンスおよびアップグレードのコストを最小限に抑えると、増分更新を許可します。</span><span class="sxs-lookup"><span data-stu-id="66c02-109">Minimizing the cost of maintenance and upgrades, and allowing incremental updates</span></span>  
  
-   <span data-ttu-id="66c02-110">ビジネス プロセスの管理と構成ツールを使って迅速な変更を許可します。</span><span class="sxs-lookup"><span data-stu-id="66c02-110">Allowing rapid change through business process management and composition tools</span></span>  
  
-   <span data-ttu-id="66c02-111">エンド ツー エンドのセキュリティこれは信頼とメッセージの送信者、受信者、およびコンテンツのプライバシーの保護に含まれます。</span><span class="sxs-lookup"><span data-stu-id="66c02-111">End-to-end security; this includes trust and protection of the privacy of message senders, receivers, and content</span></span>  
  
-   <span data-ttu-id="66c02-112">識別する、管理、および発生すると、例外を修復します。</span><span class="sxs-lookup"><span data-stu-id="66c02-112">Identifying, managing, and repairing exceptions as they occur</span></span>  
  
-   <span data-ttu-id="66c02-113">サービスとコンシューマーの分離</span><span class="sxs-lookup"><span data-stu-id="66c02-113">Decoupling of services and consumers</span></span>  
  
-   <span data-ttu-id="66c02-114">測定し、コストに関する注意事項をオフセットする SOA アプリケーションのビジネス価値を証明します。</span><span class="sxs-lookup"><span data-stu-id="66c02-114">Measuring and proving the business value of SOA applications to offset cost concerns</span></span>  
  
-   <span data-ttu-id="66c02-115">重複しているか、それ以外の場合に不要なサービスの急増のコントロール (管理)</span><span class="sxs-lookup"><span data-stu-id="66c02-115">Control (governance) of the proliferation of duplicate or otherwise unnecessary services</span></span>  
  
-   <span data-ttu-id="66c02-116">初期開発コストを削減する潜在的なユーザーに必要な適切なサービスの識別を容易にすること</span><span class="sxs-lookup"><span data-stu-id="66c02-116">Facilitating the identification of the appropriate services required by potential users to reduce initial development cost</span></span>  
  
-   <span data-ttu-id="66c02-117">コストとメンテナンスのリスクを最小限に抑える変更をサービスのライフ サイクルを管理します。</span><span class="sxs-lookup"><span data-stu-id="66c02-117">Managing the life cycle of services to minimize the cost and risk of ongoing maintenance and change</span></span>  
  
-   <span data-ttu-id="66c02-118">適切なサービスの (場所、トランスポート、ポリシー、標準の分離とスタイルのメッセージング) 実際の使用率の簡略化</span><span class="sxs-lookup"><span data-stu-id="66c02-118">Simplifying the actual usage of appropriate services (decoupling location, transport, policies, standards, and messaging styles)</span></span>  
  
-   <span data-ttu-id="66c02-119">ユーザー、サービスを使用する、場所、およびその理由を識別するための機能の報告</span><span class="sxs-lookup"><span data-stu-id="66c02-119">Reporting facilities used to identify who is using which service, where, and why</span></span>  

## <a name="next-steps"></a><span data-ttu-id="66c02-120">次の手順</span><span class="sxs-lookup"><span data-stu-id="66c02-120">Next steps</span></span>
 <span data-ttu-id="66c02-121">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] 2 つの実行時のガバナンスをサード パーティ製システムとの統合をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="66c02-121">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports integration with two third-party run-time governance systems:</span></span>  
  
-   <span data-ttu-id="66c02-122">**Sentinet SOA 競合回避モジュールおよび BizTalk Server の拡張**です。</span><span class="sxs-lookup"><span data-stu-id="66c02-122">**Sentinet SOA Resolver and BizTalk Server Extensions**.</span></span> <span data-ttu-id="66c02-123">Sentinet の拡張の詳細については[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]機能を参照してください[Sentinet で BizTalk ESB Toolkit 機能を拡張する](../technical-guides/extending-biztalk-esb-toolkit-capabilities-with-sentinet.md)です。</span><span class="sxs-lookup"><span data-stu-id="66c02-123">For more information on how Sentinet extends [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] capabilities, see [Extending BizTalk ESB Toolkit Capabilities with Sentinet](../technical-guides/extending-biztalk-esb-toolkit-capabilities-with-sentinet.md).</span></span>
  
-   <span data-ttu-id="66c02-124">[BizTalk 管理ポイントの SOA](../esb-toolkit/soa-biztalk-management-point.md) SOA ソフトウェア, inc. から</span><span class="sxs-lookup"><span data-stu-id="66c02-124">[SOA BizTalk Management Point](../esb-toolkit/soa-biztalk-management-point.md) from SOA Software, Inc.</span></span>  
  
-   <span data-ttu-id="66c02-125">[AmberPoint BizTalk Nano エージェント](../esb-toolkit/amberpoint-biztalk-nano-agent.md)AmberPoint, inc. から</span><span class="sxs-lookup"><span data-stu-id="66c02-125">[AmberPoint BizTalk Nano Agent](../esb-toolkit/amberpoint-biztalk-nano-agent.md) from AmberPoint, Inc.</span></span>