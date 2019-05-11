---
title: セキュリティで保護されたアーキテクチャの設計 |Microsoft Docs
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
ms.openlocfilehash: cacd6bf8414ac91e2fb6d7846fd3b650c90b6912
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351682"
---
# <a name="designing-a-secure-architecture"></a><span data-ttu-id="61366-102">セキュリティで保護されたアーキテクチャの設計</span><span class="sxs-lookup"><span data-stu-id="61366-102">Designing a Secure Architecture</span></span>
<span data-ttu-id="61366-103">BizTalk Server の展開のシステム アーキテクチャの詳細については、次を参照してください。 [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)します。</span><span class="sxs-lookup"><span data-stu-id="61366-103">For complete information about the system architecture for BizTalk Server deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="61366-104">トピックに示されているアーキテクチャ[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)BizTalk 環境を脆弱性のある潜在的なセキュリティ脅威の多くを解決します。</span><span class="sxs-lookup"><span data-stu-id="61366-104">The architecture presented in the topic [Large Distributed Architecture](../core/large-distributed-architecture.md) addresses many of the potential security threats to which a BizTalk environment is vulnerable.</span></span> <span data-ttu-id="61366-105">ただし、ビジネス資産、ビジネス、および資産を保護するための最適なアーキテクチャを特定する、潜在的な脅威を軽減するために使用可能なリソースである問題のある脅威を評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61366-105">However, you need to evaluate your business assets, the threats that are a concern for your business, and the resources you have available to protect your assets and mitigate your potential threats to determine what the best architecture is for you.</span></span> <span data-ttu-id="61366-106">このセクションでは、設計するときに検討する追加のセキュリティ オプション、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アーキテクチャ。</span><span class="sxs-lookup"><span data-stu-id="61366-106">This section provides additional security options you can consider when designing your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] architecture.</span></span>  
  
## <a name="firewalls"></a><span data-ttu-id="61366-107">ファイアウォール</span><span class="sxs-lookup"><span data-stu-id="61366-107">Firewalls</span></span>  
 <span data-ttu-id="61366-108">物理的な (ハードウェア) ファイアウォールまたはソフトウェア ファイアウォールを使用すると、環境内のリソースへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="61366-108">You can use physical (hardware) or software firewalls to restrict access to the resources in your environment.</span></span> <span data-ttu-id="61366-109">トピックの中に[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)Forefront Threat Management Gateway (TMG) 2010 を使用してサーバーを作成同様のアーキテクチャ ハードウェアまたはサード パーティのソフトウェアのファイアウォールを使用する開くと、さまざまな BizTalk Server コンポーネント間の通信に必要なポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="61366-109">While the topic [Large Distributed Architecture](../core/large-distributed-architecture.md) uses Forefront Threat Management Gateway (TMG) 2010 server, you can create a similar architecture by using hardware or third-party software firewalls, as long as you open and configure the ports required for communication between the different BizTalk Server components.</span></span> <span data-ttu-id="61366-110">BizTalk Server で使用するポートの詳細については、次を参照してください。 [BizTalk Server の必須ポートの](../core/required-ports-for-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="61366-110">For more information about the ports BizTalk Server uses, see [Required Ports for BizTalk Server](../core/required-ports-for-biztalk-server.md).</span></span>  
  
## <a name="active-directory"></a><span data-ttu-id="61366-111">Active Directory</span><span class="sxs-lookup"><span data-stu-id="61366-111">Active Directory</span></span>  
 <span data-ttu-id="61366-112">サンプルの配置、Active Directory® ディレクトリ サービスは、各サーバー グループの周囲のハード セキュリティ境界の作成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="61366-112">In the sample deployment, Active Directory® directory service is used to create a hard security boundary around each group of servers.</span></span> <span data-ttu-id="61366-113">一方向の信頼では、BizTalk Server がアプリケーションのデータ ドメインで作成されたアカウントで実行すると、処理サーバーで実行されている他の BizTalk Server 以外のアプリケーションでの欠陥が原因の攻撃から BizTalk Server 環境をさらに保護できます。</span><span class="sxs-lookup"><span data-stu-id="61366-113">With the one-way trusts, you can further protect the BizTalk Server environment from attacks due to flaws in other non-BizTalk Server applications running on the processing servers, as the BizTalk Server applications run under accounts created in the data domain.</span></span> <span data-ttu-id="61366-114">データ ドメインが、他のドメインのアカウントを信頼していないため、別のドメイン内のアカウントのセキュリティ侵害は侵害状態から BizTalk Server 環境を保持します。</span><span class="sxs-lookup"><span data-stu-id="61366-114">Because the data domain does not trust any accounts in any other domain, a compromise of an account in another domain keeps the BizTalk Server environment from being compromised.</span></span>  
  
## <a name="ipsec-and-ssl"></a><span data-ttu-id="61366-115">IPSec および SSL</span><span class="sxs-lookup"><span data-stu-id="61366-115">IPSec and SSL</span></span>  
 <span data-ttu-id="61366-116">環境内には重要なは、ファイアウォールのセキュリティのレベルを必要とする脅威を提供するが、処理、データを接続するネットワーク セグメントを引き起こすことはありませんし、サービスのドメインがさまざまなネットワーク攻撃 (パケットから物理的にセキュリティで保護された場合スニッフィングまたは改ざん) 別に 1 つのサーバーから移動すると、データを保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61366-116">If your environment does not pose critical threats that require the level of security firewalls provide, but the network segments that connect the data, processing, and services domains are not physically secure from various network attacks (for example packet sniffing or tampering), you still need to protect the data as it goes from one server to another.</span></span> <span data-ttu-id="61366-117">この場合、1 つのサーバーからのトラフィックの暗号化には、インターネット プロトコル セキュリティ (IPSec) または Secure Sockets Layer (SSL) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="61366-117">In this case, you can use Internet Protocol security (IPSec) or Secure Sockets Layer (SSL) to encrypt traffic from one server to another.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61366-118">参照</span><span class="sxs-lookup"><span data-stu-id="61366-118">See Also</span></span>  
 <span data-ttu-id="61366-119">[分散アーキテクチャの設計](../core/designing-a-distributed-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="61366-119">[Designing a Distributed Architecture](../core/designing-a-distributed-architecture.md) </span></span>  
 <span data-ttu-id="61366-120">[セキュリティの計画](../core/planning-for-security.md) </span><span class="sxs-lookup"><span data-stu-id="61366-120">[Planning for Security](../core/planning-for-security.md) </span></span>  
 <span data-ttu-id="61366-121">[BizTalk Server のシステム アーキテクチャの設計](../core/designing-the-system-architectures-for-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="61366-121">[Designing the System Architectures for BizTalk Server](../core/designing-the-system-architectures-for-biztalk-server.md) </span></span>  
 [<span data-ttu-id="61366-122">BizTalk Server のサンプル アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="61366-122">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)