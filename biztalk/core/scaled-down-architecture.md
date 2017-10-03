---
title: "縮小されたアーキテクチャ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, small distributions
- architecture, examples
ms.assetid: e25798aa-4a1e-418c-9e0c-db964e8b5a80
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a112f3f737a1a5aec0cfac16b7689d3dada1e8ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scaled-down-architecture"></a><span data-ttu-id="65c68-102">縮小されたアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="65c68-102">Scaled Down Architecture</span></span>
<span data-ttu-id="65c68-103">詳細については、システムのアーキテクチャの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開を参照してください[サンプル BizTalk Server アーキテクチャ](../core/sample-biztalk-server-architectures.md)です。</span><span class="sxs-lookup"><span data-stu-id="65c68-103">For complete information about the system architecture for[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="65c68-104">次の図は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のサンプル アーキテクチャを示しています。このアーキテクチャでは、一部のドメインと BizTalk Server を組み合わせて、必要なサーバーおよびファイアウォールの数を削減します。</span><span class="sxs-lookup"><span data-stu-id="65c68-104">The following figure provides a sample [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] architecture that combines some of the domains and BizTalk Servers to reduce the number of servers and firewalls you need.</span></span> <span data-ttu-id="65c68-105">このアーキテクチャは、最も分散されたアーキテクチャではありませんが、BizTalk Server をその機能に基づいて分離しています。</span><span class="sxs-lookup"><span data-stu-id="65c68-105">While this architecture is not the most distributed, it still separates the BizTalk Servers based on their function.</span></span>  
  
 <span data-ttu-id="65c68-106">![縮小されたアーキテクチャ](../core/media/16ebc4ef-ff64-495b-bcac-5c1fd70ca173.gif "16ebc4ef-ff64-495b-bcac-5c1fd70ca173")</span><span class="sxs-lookup"><span data-stu-id="65c68-106">![Scaled down architecture](../core/media/16ebc4ef-ff64-495b-bcac-5c1fd70ca173.gif "16ebc4ef-ff64-495b-bcac-5c1fd70ca173")</span></span>  
  
        Scaled Down Architecture  
  
 <span data-ttu-id="65c68-107">上記の図では、サービス インターフェイスおよびサービス ドメイン内のサーバーは、物理サーバーではなく BizTalk ホストに対応しています。</span><span class="sxs-lookup"><span data-stu-id="65c68-107">In the previous figure, the servers in the service interfaces and services domain correspond to BizTalk Hosts, and not physical servers.</span></span> <span data-ttu-id="65c68-108">マスタ シークレット サーバーおよび管理ツールはスタンドアロン コンピュータに保持しておくことをお勧めしますが、複数のコンピュータ上で実行している追跡ホスト、処理ホスト、送信ホスト、および受信ホスト用にホスト インスタンスを配置できます。</span><span class="sxs-lookup"><span data-stu-id="65c68-108">While it is recommended to keep the master secret server and the administrative tools in stand-alone computers, you can have host instances for the tracking, processing, send, and receive hosts running on multiple computers.</span></span> <span data-ttu-id="65c68-109">同様に、境界ネットワーク内のサーバーは、論理的な場所に対応しています。</span><span class="sxs-lookup"><span data-stu-id="65c68-109">Similarly, the servers in the perimeter network correspond to logical locations.</span></span>  
  
 <span data-ttu-id="65c68-110">境界ネットワーク内にある、SMTP、メッセージ キュー、ファイル、SQL 用のサーバーはそれぞれ、メール サーバー、キュー、ディレクトリ、SQL Server に対応し、処理ドメインおよびサービス ドメイン内の BizTalk 受信ホストおよび送信ホストはここからメッセージの送受信を行います。</span><span class="sxs-lookup"><span data-stu-id="65c68-110">The servers in the perimeter network for SMTP, Message Queuing, File, and SQL correspond to the mail servers, queue, directory, or SQL Server respectively from which the BizTalk receive and send hosts in the processing and services domain receive and send messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65c68-111">参照</span><span class="sxs-lookup"><span data-stu-id="65c68-111">See Also</span></span>  
 <span data-ttu-id="65c68-112">[縮小されたインフォメーション ワーカー サービスのアーキテクチャ](../core/scaled-down-architecture-with-information-worker-services.md) </span><span class="sxs-lookup"><span data-stu-id="65c68-112">[Scaled Down Architecture with Information Worker Services](../core/scaled-down-architecture-with-information-worker-services.md) </span></span>  
 <span data-ttu-id="65c68-113">[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="65c68-113">[Large Distributed Architecture](../core/large-distributed-architecture.md) </span></span>  
 <span data-ttu-id="65c68-114">[セキュリティで保護されたアーキテクチャの設計](../core/designing-a-secure-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="65c68-114">[Designing a Secure Architecture](../core/designing-a-secure-architecture.md) </span></span>  
 [<span data-ttu-id="65c68-115">BizTalk Server のサンプル アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="65c68-115">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)