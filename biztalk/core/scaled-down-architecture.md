---
title: 縮小されたアーキテクチャ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, small distributions
- architecture, examples
ms.assetid: e25798aa-4a1e-418c-9e0c-db964e8b5a80
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 770276aceab5c0de64615f457c20d6d1945a63b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399976"
---
# <a name="scaled-down-architecture"></a><span data-ttu-id="eef93-102">縮小されたアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="eef93-102">Scaled Down Architecture</span></span>
<span data-ttu-id="eef93-103">システム アーキテクチャの詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開を参照してください[Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)します。</span><span class="sxs-lookup"><span data-stu-id="eef93-103">For complete information about the system architecture for[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="eef93-104">次の図は、サンプル[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アーキテクチャをいくつかのドメインとサーバーの数を減らすための BizTalk Server を結合し、ファイアウォールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eef93-104">The following figure provides a sample [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] architecture that combines some of the domains and BizTalk Servers to reduce the number of servers and firewalls you need.</span></span> <span data-ttu-id="eef93-105">このアーキテクチャは、ほとんどの分散は、まだその機能に基づいて、BizTalk Server を区切ります。</span><span class="sxs-lookup"><span data-stu-id="eef93-105">While this architecture is not the most distributed, it still separates the BizTalk Servers based on their function.</span></span>  
  
 <span data-ttu-id="eef93-106">![縮小されたアーキテクチャ](../core/media/16ebc4ef-ff64-495b-bcac-5c1fd70ca173.gif "16ebc4ef-ff64-495b-bcac-5c1fd70ca173")</span><span class="sxs-lookup"><span data-stu-id="eef93-106">![Scaled down architecture](../core/media/16ebc4ef-ff64-495b-bcac-5c1fd70ca173.gif "16ebc4ef-ff64-495b-bcac-5c1fd70ca173")</span></span>  
  
        Scaled Down Architecture  
  
 <span data-ttu-id="eef93-107">前の図では、サービス インターフェイス ドメインおよびサービス ドメイン内のサーバーは、BizTalk ホスト、および物理サーバーに対応します。</span><span class="sxs-lookup"><span data-stu-id="eef93-107">In the previous figure, the servers in the service interfaces and services domain correspond to BizTalk Hosts, and not physical servers.</span></span> <span data-ttu-id="eef93-108">追跡、ホスト インスタンスがスタンドアロン コンピューターにマスター シークレット サーバーおよび管理ツールを保持することをお勧めしますが、送信、処理、および複数のコンピューターで実行しているホストを受信します。</span><span class="sxs-lookup"><span data-stu-id="eef93-108">While it is recommended to keep the master secret server and the administrative tools in stand-alone computers, you can have host instances for the tracking, processing, send, and receive hosts running on multiple computers.</span></span> <span data-ttu-id="eef93-109">同様に、境界ネットワーク内のサーバーは、論理的な場所に対応します。</span><span class="sxs-lookup"><span data-stu-id="eef93-109">Similarly, the servers in the perimeter network correspond to logical locations.</span></span>  
  
 <span data-ttu-id="eef93-110">SMTP、メッセージ キュー、ファイル、および SQL の境界ネットワーク内のサーバーは、メール サーバー、キュー、ディレクトリ、または SQL Server、BizTalk それぞれ元の受信および送信メッセージの送受信を処理およびサービス ドメイン内のホストに対応します。</span><span class="sxs-lookup"><span data-stu-id="eef93-110">The servers in the perimeter network for SMTP, Message Queuing, File, and SQL correspond to the mail servers, queue, directory, or SQL Server respectively from which the BizTalk receive and send hosts in the processing and services domain receive and send messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eef93-111">参照</span><span class="sxs-lookup"><span data-stu-id="eef93-111">See Also</span></span>  
 <span data-ttu-id="eef93-112">[縮小されたアーキテクチャ情報ワーカー サービスを使用](../core/scaled-down-architecture-with-information-worker-services.md) </span><span class="sxs-lookup"><span data-stu-id="eef93-112">[Scaled Down Architecture with Information Worker Services](../core/scaled-down-architecture-with-information-worker-services.md) </span></span>  
 <span data-ttu-id="eef93-113">[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="eef93-113">[Large Distributed Architecture](../core/large-distributed-architecture.md) </span></span>  
 <span data-ttu-id="eef93-114">[セキュリティで保護されたアーキテクチャの設計](../core/designing-a-secure-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="eef93-114">[Designing a Secure Architecture](../core/designing-a-secure-architecture.md) </span></span>  
 [<span data-ttu-id="eef93-115">BizTalk Server のサンプル アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="eef93-115">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)