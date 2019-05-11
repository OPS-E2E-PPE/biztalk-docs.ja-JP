---
title: 分散アーキテクチャの設計 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- clustering, SQL Servers
- SQL Server, clustering
ms.assetid: 8a8f1710-4d53-42bf-b5e5-2be3b43813b4
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3e495fd45074398fbdedec2e4b8e3fb544f9e55
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389720"
---
# <a name="designing-a-distributed-architecture"></a><span data-ttu-id="35c0a-102">分散アーキテクチャの設計</span><span class="sxs-lookup"><span data-stu-id="35c0a-102">Designing a Distributed Architecture</span></span>
<span data-ttu-id="35c0a-103">BizTalk Server の展開のシステム アーキテクチャの詳細については、次を参照してください。 [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)します。</span><span class="sxs-lookup"><span data-stu-id="35c0a-103">For complete information about the system architecture for BizTalk Server deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="35c0a-104">トピックに示されているアーキテクチャ[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)BizTalk 環境を脆弱性のある潜在的なセキュリティ脅威の多くを解決します。</span><span class="sxs-lookup"><span data-stu-id="35c0a-104">The architecture presented in the topic [Large Distributed Architecture](../core/large-distributed-architecture.md) addresses many of the potential security threats to which a BizTalk environment is vulnerable.</span></span> <span data-ttu-id="35c0a-105">アーキテクチャを設計するときに、セキュリティが高優先順位の一覧にする必要がありますが、高可用性、スケーラビリティ、パフォーマンスなどの分散環境で追加の考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="35c0a-105">While security should be high on your list of priorities when designing your architecture, there are additional considerations in a distributed environment, such as high-availability, scalability, and performance.</span></span> <span data-ttu-id="35c0a-106">このセクションを設計するときに検討する追加のオプションを提供する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アーキテクチャ。</span><span class="sxs-lookup"><span data-stu-id="35c0a-106">This section provides additional options you can consider when designing your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] architecture.</span></span>  
  
## <a name="domains"></a><span data-ttu-id="35c0a-107">ドメイン</span><span class="sxs-lookup"><span data-stu-id="35c0a-107">Domains</span></span>  
 <span data-ttu-id="35c0a-108">会社では、ほとんどのインターネットによる通信を実行する場合は、会社のドメインからイントラネット サービスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="35c0a-108">If your company performs mostly Internet-facing communications, you can remove the intranet services from the corporate domain.</span></span> <span data-ttu-id="35c0a-109">逆に、他のアプリケーションや、イントラネット経由で接続するビジネス パートナーへの接続に BizTalk Server を使用する場合は、境界ネットワークを削除できます。</span><span class="sxs-lookup"><span data-stu-id="35c0a-109">Conversely, if you use BizTalk Server to connect to other applications or business partners that connect through the intranet, you can remove the perimeter network.</span></span> <span data-ttu-id="35c0a-110">存在する場合、会社はパートナーの数が少ないインターネットおよびイントラネットによる通信の両方に、イントラネット サービスと境界ネットワークを組み合わせることを検討できます。</span><span class="sxs-lookup"><span data-stu-id="35c0a-110">If your company does both Internet and intranet-facing communications with a small number of partners, you may consider combining the intranet services and the perimeter network.</span></span>  
  
 <span data-ttu-id="35c0a-111">場合は、データ ドメイン内の SQL サーバーの処理サーバーとの間の通信での待機時間を最小限に抑えたいし、セキュリティ問題など、ネットワーク スニッフィング、パケットの改ざん、ホストの内部ネットワークで偽装が問題ではありません、処理とデータのドメイン間のファイアウォールを削除し、これらのドメインをマージします。</span><span class="sxs-lookup"><span data-stu-id="35c0a-111">If you want to minimize the latency in the communication between the processing servers and the SQL Servers in the data domain, and security issues such as network sniffing, tampering of packets, and host spoofing in the internal network are not a concern, you can remove the firewall between the processing and data domain, and merge these domains.</span></span> <span data-ttu-id="35c0a-112">インターネット プロトコル セキュリティ (IPSec) または Secure Sockets Layer (SSL) を別に 1 つのサーバーから移動するデータを保護するために使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="35c0a-112">It is recommended you then use Internet Protocol security (IPSec) or Secure Sockets Layer (SSL) to protect the data as it goes from one server to another.</span></span>  
  
## <a name="sql-server-clustering"></a><span data-ttu-id="35c0a-113">SQL Server クラスタ リング</span><span class="sxs-lookup"><span data-stu-id="35c0a-113">SQL Server clustering</span></span>  
 <span data-ttu-id="35c0a-114">このセクションで詳しく説明しませんがフェールオーバー保護のため、データベースをクラスタ リングを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="35c0a-114">Although not described in detail in this section, we strongly recommend clustering your databases for failover protection.</span></span> <span data-ttu-id="35c0a-115">SQL Server 2008 フェールオーバー クラスタ リングの詳細については、Microsoft MSDN Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=131016](http://go.microsoft.com/fwlink/?LinkId=131016)します。</span><span class="sxs-lookup"><span data-stu-id="35c0a-115">For more information about SQL Server 2008 failover clustering, see the Microsoft MSDN Web site at [http://go.microsoft.com/fwlink/?LinkId=131016](http://go.microsoft.com/fwlink/?LinkId=131016).</span></span>  
  
## <a name="messagebox-database"></a><span data-ttu-id="35c0a-116">メッセージ ボックス データベース</span><span class="sxs-lookup"><span data-stu-id="35c0a-116">MessageBox database</span></span>  
 <span data-ttu-id="35c0a-117">会社のメッセージ スループット要件によっては、メッセージ ボックス データベースの追加 (または削除) する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35c0a-117">Depending on the message throughput requirements for your company, you may need to add (or remove) MessageBox databases.</span></span> <span data-ttu-id="35c0a-118">複数のメッセージ ボックスの詳細については、次を参照してください。 [Scaled-Out データベース](../core/scaled-out-databases.md)します。</span><span class="sxs-lookup"><span data-stu-id="35c0a-118">For more information about multiple messagebox, see [Scaled-Out Databases](../core/scaled-out-databases.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35c0a-119">参照</span><span class="sxs-lookup"><span data-stu-id="35c0a-119">See Also</span></span>  
 <span data-ttu-id="35c0a-120">[セキュリティで保護されたアーキテクチャの設計](../core/designing-a-secure-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="35c0a-120">[Designing a Secure Architecture](../core/designing-a-secure-architecture.md) </span></span>  
 <span data-ttu-id="35c0a-121">[高可用性の計画](../core/planning-for-high-availability3.md) </span><span class="sxs-lookup"><span data-stu-id="35c0a-121">[Planning for High Availability](../core/planning-for-high-availability3.md) </span></span>  
 <span data-ttu-id="35c0a-122">[パフォーマンス維持の計画](../core/planning-for-sustained-performance.md) </span><span class="sxs-lookup"><span data-stu-id="35c0a-122">[Planning for Sustained Performance](../core/planning-for-sustained-performance.md) </span></span>  
 <span data-ttu-id="35c0a-123">[BizTalk Server のシステム アーキテクチャの設計](../core/designing-the-system-architectures-for-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="35c0a-123">[Designing the System Architectures for BizTalk Server](../core/designing-the-system-architectures-for-biztalk-server.md) </span></span>  
 [<span data-ttu-id="35c0a-124">BizTalk Server のサンプル アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="35c0a-124">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)