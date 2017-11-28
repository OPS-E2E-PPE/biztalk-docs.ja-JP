---
title: "分散アーキテクチャの設計 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- clustering, SQL Servers
- SQL Server, clustering
ms.assetid: 8a8f1710-4d53-42bf-b5e5-2be3b43813b4
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 156c7107abfd0fd140a5e7b07f06d00eabf7c961
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="designing-a-distributed-architecture"></a><span data-ttu-id="6e29c-102">分散アーキテクチャの設計</span><span class="sxs-lookup"><span data-stu-id="6e29c-102">Designing a Distributed Architecture</span></span>
<span data-ttu-id="6e29c-103">BizTalk Server の展開のシステム アーキテクチャに関する詳細については、次を参照してください。[サンプル BizTalk Server アーキテクチャ](../core/sample-biztalk-server-architectures.md)です。</span><span class="sxs-lookup"><span data-stu-id="6e29c-103">For complete information about the system architecture for BizTalk Server deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="6e29c-104">トピックで示すアーキテクチャ[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)BizTalk 環境を脆弱なセキュリティ上の潜在的な脅威の多くに対処します。</span><span class="sxs-lookup"><span data-stu-id="6e29c-104">The architecture presented in the topic [Large Distributed Architecture](../core/large-distributed-architecture.md) addresses many of the potential security threats to which a BizTalk environment is vulnerable.</span></span> <span data-ttu-id="6e29c-105">アーキテクチャを設計する際に優先度の一覧でセキュリティを高に設定する必要がある一方で、分散環境には高可用性、スケーラビリティ、パフォーマンスなどの追加の考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="6e29c-105">While security should be high on your list of priorities when designing your architecture, there are additional considerations in a distributed environment, such as high-availability, scalability, and performance.</span></span> <span data-ttu-id="6e29c-106">このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アーキテクチャの設計時に検討する追加のオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6e29c-106">This section provides additional options you can consider when designing your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] architecture.</span></span>  
  
## <a name="domains"></a><span data-ttu-id="6e29c-107">ドメイン</span><span class="sxs-lookup"><span data-stu-id="6e29c-107">Domains</span></span>  
 <span data-ttu-id="6e29c-108">インターネットによる通信を主に利用する会社では、企業ドメインからイントラネット サービスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="6e29c-108">If your company performs mostly Internet-facing communications, you can remove the intranet services from the corporate domain.</span></span> <span data-ttu-id="6e29c-109">逆に、BizTalk Server を使用してイントラネット経由で他のアプリケーションやビジネス パートナーに接続する場合、境界ネットワークを削除できます。</span><span class="sxs-lookup"><span data-stu-id="6e29c-109">Conversely, if you use BizTalk Server to connect to other applications or business partners that connect through the intranet, you can remove the perimeter network.</span></span> <span data-ttu-id="6e29c-110">場合は、会社は、インターネットとイントラネットに接続された通信の両方を少数のパートナーでは、境界ネットワークとイントラネット サービスを組み合わせることを検討する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e29c-110">If your company does both Internet and intranet-facing communications with a small number of partners, you may consider combining the intranet services and the perimeter network.</span></span>  
  
 <span data-ttu-id="6e29c-111">データ ドメイン内の処理サーバーと SQL Server 間の通信の遅延を最小限にする必要がある場合で、ネットワーク スニッフィング、パケットの改ざん、ホストの偽装など、内部ネットワーク内のセキュリティに関する問題の心配がない場合、処理ドメインとデータ ドメイン間のファイアウォールを削除し、それらのドメインをマージできます。</span><span class="sxs-lookup"><span data-stu-id="6e29c-111">If you want to minimize the latency in the communication between the processing servers and the SQL Servers in the data domain, and security issues such as network sniffing, tampering of packets, and host spoofing in the internal network are not a concern, you can remove the firewall between the processing and data domain, and merge these domains.</span></span> <span data-ttu-id="6e29c-112">インターネット プロトコル セキュリティ (IPsec) または Secure Sockets Layer (SSL) を使用して、あるサーバーから別のサーバーにデータが移動するときにそのデータを保護することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e29c-112">It is recommended you then use Internet Protocol security (IPSec) or Secure Sockets Layer (SSL) to protect the data as it goes from one server to another.</span></span>  
  
## <a name="sql-server-clustering"></a><span data-ttu-id="6e29c-113">SQL Server クラスタリング</span><span class="sxs-lookup"><span data-stu-id="6e29c-113">SQL Server clustering</span></span>  
 <span data-ttu-id="6e29c-114">このセクションでは詳しくは説明しませんが、フェールオーバー保護のためにデータベースをクラスタ化することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e29c-114">Although not described in detail in this section, we strongly recommend clustering your databases for failover protection.</span></span> <span data-ttu-id="6e29c-115">SQL Server 2008 フェールオーバー クラスタ リングの詳細については、Microsoft MSDN Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=131016](http://go.microsoft.com/fwlink/?LinkId=131016)です。</span><span class="sxs-lookup"><span data-stu-id="6e29c-115">For more information about SQL Server 2008 failover clustering, see the Microsoft MSDN Web site at [http://go.microsoft.com/fwlink/?LinkId=131016](http://go.microsoft.com/fwlink/?LinkId=131016).</span></span>  
  
## <a name="messagebox-database"></a><span data-ttu-id="6e29c-116">メッセージ ボックス データベース</span><span class="sxs-lookup"><span data-stu-id="6e29c-116">MessageBox database</span></span>  
 <span data-ttu-id="6e29c-117">会社のメッセージ スループットの要件によっては、メッセージ ボックス データベースを追加 (または削除) することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e29c-117">Depending on the message throughput requirements for your company, you may need to add (or remove) MessageBox databases.</span></span> <span data-ttu-id="6e29c-118">複数のメッセージ ボックスの詳細については、次を参照してください。 [Scaled-Out データベース](../core/scaled-out-databases.md)です。</span><span class="sxs-lookup"><span data-stu-id="6e29c-118">For more information about multiple messagebox, see [Scaled-Out Databases](../core/scaled-out-databases.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e29c-119">参照</span><span class="sxs-lookup"><span data-stu-id="6e29c-119">See Also</span></span>  
 <span data-ttu-id="6e29c-120">[セキュリティで保護されたアーキテクチャの設計](../core/designing-a-secure-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="6e29c-120">[Designing a Secure Architecture](../core/designing-a-secure-architecture.md) </span></span>  
 <span data-ttu-id="6e29c-121">[高可用性の計画](../core/planning-for-high-availability3.md) </span><span class="sxs-lookup"><span data-stu-id="6e29c-121">[Planning for High Availability](../core/planning-for-high-availability3.md) </span></span>  
 <span data-ttu-id="6e29c-122">[パフォーマンス維持の計画](../core/planning-for-sustained-performance.md) </span><span class="sxs-lookup"><span data-stu-id="6e29c-122">[Planning for Sustained Performance](../core/planning-for-sustained-performance.md) </span></span>  
 <span data-ttu-id="6e29c-123">[BizTalk Server のシステム アーキテクチャの設計](../core/designing-the-system-architectures-for-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="6e29c-123">[Designing the System Architectures for BizTalk Server](../core/designing-the-system-architectures-for-biztalk-server.md) </span></span>  
 [<span data-ttu-id="6e29c-124">BizTalk Server のサンプル アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="6e29c-124">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)