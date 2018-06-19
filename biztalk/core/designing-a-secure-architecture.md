---
title: セキュリティで保護されたアーキテクチャの設計 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- firewalls
- architecture, security
- installation, firewalls
- installation, security
ms.assetid: 93df6a3f-396c-4767-99c8-2145bddf8fdf
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 157c11477efb9dec455e9ac2de81736cd4ea72ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239450"
---
# <a name="designing-a-secure-architecture"></a><span data-ttu-id="4fdd2-102">セキュリティ保護アーキテクチャの設計</span><span class="sxs-lookup"><span data-stu-id="4fdd2-102">Designing a Secure Architecture</span></span>
<span data-ttu-id="4fdd2-103">BizTalk Server の展開のシステム アーキテクチャに関する詳細については、次を参照してください。[サンプル BizTalk Server アーキテクチャ](../core/sample-biztalk-server-architectures.md)です。</span><span class="sxs-lookup"><span data-stu-id="4fdd2-103">For complete information about the system architecture for BizTalk Server deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="4fdd2-104">トピックで示すアーキテクチャ[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)BizTalk 環境を脆弱なセキュリティ上の潜在的な脅威の多くに対処します。</span><span class="sxs-lookup"><span data-stu-id="4fdd2-104">The architecture presented in the topic [Large Distributed Architecture](../core/large-distributed-architecture.md) addresses many of the potential security threats to which a BizTalk environment is vulnerable.</span></span> <span data-ttu-id="4fdd2-105">ただし、ビジネス資産、ビジネスにとって問題である脅威、および資産の保護や脅威が起きた場合の緩和に使用できるリソースを評価し、最適なアーキテクチャを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fdd2-105">However, you need to evaluate your business assets, the threats that are a concern for your business, and the resources you have available to protect your assets and mitigate your potential threats to determine what the best architecture is for you.</span></span> <span data-ttu-id="4fdd2-106">このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アーキテクチャの設計時に検討する追加のセキュリティ オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4fdd2-106">This section provides additional security options you can consider when designing your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] architecture.</span></span>  
  
## <a name="firewalls"></a><span data-ttu-id="4fdd2-107">ファイアウォール</span><span class="sxs-lookup"><span data-stu-id="4fdd2-107">Firewalls</span></span>  
 <span data-ttu-id="4fdd2-108">物理的な (ハードウェア) ファイアウォールまたはソフトウェア ファイアウォールを使用して、環境内のリソースへのアクセスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="4fdd2-108">You can use physical (hardware) or software firewalls to restrict access to the resources in your environment.</span></span> <span data-ttu-id="4fdd2-109">トピックの中に[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)Forefront Threat Management Gateway (TMG) 2010 を使用して、サーバーを作成できますのようなアーキテクチャ ハードウェアまたはサード パーティのソフトウェア ファイアウォールを使用する開くと、別の BizTalk Server コンポーネント間の通信に必要なポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="4fdd2-109">While the topic [Large Distributed Architecture](../core/large-distributed-architecture.md) uses Forefront Threat Management Gateway (TMG) 2010 server, you can create a similar architecture by using hardware or third-party software firewalls, as long as you open and configure the ports required for communication between the different BizTalk Server components.</span></span> <span data-ttu-id="4fdd2-110">BizTalk Server で使用するポートに関する詳細については、次を参照してください。 [BizTalk Server の必須ポートの](../core/required-ports-for-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="4fdd2-110">For more information about the ports BizTalk Server uses, see [Required Ports for BizTalk Server](../core/required-ports-for-biztalk-server.md).</span></span>  
  
## <a name="active-directory"></a><span data-ttu-id="4fdd2-111">Active Directory</span><span class="sxs-lookup"><span data-stu-id="4fdd2-111">Active Directory</span></span>  
 <span data-ttu-id="4fdd2-112">サンプルの展開では、Active Directory® ディレクトリ サービスを使用して、各サーバー グループの周囲に強力なセキュリティの境界を作成します。</span><span class="sxs-lookup"><span data-stu-id="4fdd2-112">In the sample deployment, Active Directory® directory service is used to create a hard security boundary around each group of servers.</span></span> <span data-ttu-id="4fdd2-113">一方向の信頼により、データ ドメインで作成したアカウントで BizTalk Server アプリケーションを実行する場合、処理サーバーで実行している BizTalk Server 以外のアプリケーションの不具合による攻撃から BizTalk Server 環境をさらに保護できます。</span><span class="sxs-lookup"><span data-stu-id="4fdd2-113">With the one-way trusts, you can further protect the BizTalk Server environment from attacks due to flaws in other non-BizTalk Server applications running on the processing servers, as the BizTalk Server applications run under accounts created in the data domain.</span></span> <span data-ttu-id="4fdd2-114">データ ドメインはその他のドメインのアカウントを信頼しないため、別のドメインのアカウントが危険にさらされても、BizTalk Server 環境は脅かされないように保護されています。</span><span class="sxs-lookup"><span data-stu-id="4fdd2-114">Because the data domain does not trust any accounts in any other domain, a compromise of an account in another domain keeps the BizTalk Server environment from being compromised.</span></span>  
  
## <a name="ipsec-and-ssl"></a><span data-ttu-id="4fdd2-115">IPSec および SSL</span><span class="sxs-lookup"><span data-stu-id="4fdd2-115">IPSec and SSL</span></span>  
 <span data-ttu-id="4fdd2-116">使用する環境で、ファイアウォールによって提供されるセキュリティ レベルを必要とする重大な脅威が発生していなくても、データ ドメイン、処理ドメイン、サービス ドメインに接続するネットワーク セグメントがさまざまなネットワーク上の攻撃 (パケット スニッフィングや改ざんなど) から物理的に保護されていない場合は、データをあるサーバーから別のサーバーに移動するときに保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fdd2-116">If your environment does not pose critical threats that require the level of security firewalls provide, but the network segments that connect the data, processing, and services domains are not physically secure from various network attacks (for example packet sniffing or tampering), you still need to protect the data as it goes from one server to another.</span></span> <span data-ttu-id="4fdd2-117">この場合、インターネット プロトコル セキュリティ (IPsec) または Secure Sockets Layer (SSL) を使用して、あるサーバーから別のサーバーへのトラフィックを暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="4fdd2-117">In this case, you can use Internet Protocol security (IPSec) or Secure Sockets Layer (SSL) to encrypt traffic from one server to another.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fdd2-118">参照</span><span class="sxs-lookup"><span data-stu-id="4fdd2-118">See Also</span></span>  
 <span data-ttu-id="4fdd2-119">[分散アーキテクチャの設計](../core/designing-a-distributed-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="4fdd2-119">[Designing a Distributed Architecture](../core/designing-a-distributed-architecture.md) </span></span>  
 <span data-ttu-id="4fdd2-120">[セキュリティの計画](../core/planning-for-security.md) </span><span class="sxs-lookup"><span data-stu-id="4fdd2-120">[Planning for Security](../core/planning-for-security.md) </span></span>  
 <span data-ttu-id="4fdd2-121">[BizTalk Server のシステム アーキテクチャの設計](../core/designing-the-system-architectures-for-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="4fdd2-121">[Designing the System Architectures for BizTalk Server](../core/designing-the-system-architectures-for-biztalk-server.md) </span></span>  
 [<span data-ttu-id="4fdd2-122">BizTalk Server のサンプル アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="4fdd2-122">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)