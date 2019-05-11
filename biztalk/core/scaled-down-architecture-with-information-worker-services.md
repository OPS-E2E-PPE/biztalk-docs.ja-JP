---
title: 縮小された、インフォメーション ワーカー サービス アーキテクチャ |Microsoft Docs
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
ms.assetid: ce1217bf-84a5-4888-89ba-dce85dc38340
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44c31f9fa9683d8a3a7210d324f605cb1689981c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65309350"
---
# <a name="scaled-down-architecture-with-information-worker-services"></a><span data-ttu-id="dd2dd-102">インフォメーション ワーカー サービスを使用した縮小されたアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="dd2dd-102">Scaled Down Architecture with Information Worker Services</span></span>
<span data-ttu-id="dd2dd-103">BizTalk Server の展開のシステム アーキテクチャの詳細については、次を参照してください。 [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)します。</span><span class="sxs-lookup"><span data-stu-id="dd2dd-103">For complete information about the system architecture for BizTalk Server deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="dd2dd-104">次の図は、サンプルは、一部のドメインと BizTalk Server サーバーおよび必要なファイアウォールの数を減らして組み合わせて、インフォメーション ワーカー サービスを含む BizTalk Server アーキテクチャを提供します。</span><span class="sxs-lookup"><span data-stu-id="dd2dd-104">The following figure provides a sample BizTalk Server architecture including the information worker services that combines some of the domains and BizTalk Servers to reduce the number of servers and firewalls you need.</span></span> <span data-ttu-id="dd2dd-105">このアーキテクチャは、ほとんどの分散は、まだその機能に基づいて、BizTalk Server を区切ります。</span><span class="sxs-lookup"><span data-stu-id="dd2dd-105">While this architecture is not the most distributed, it still separates the BizTalk Servers based on their function.</span></span>  
  
 <span data-ttu-id="dd2dd-106">![スケール ダウン トポロジ](../core/media/cd3c85df-40f5-4382-9f8b-b2609f76e8b1.gif "cd3c85df-40f5-4382-9f8b-b2609f76e8b1")</span><span class="sxs-lookup"><span data-stu-id="dd2dd-106">![Scaledown Topology](../core/media/cd3c85df-40f5-4382-9f8b-b2609f76e8b1.gif "cd3c85df-40f5-4382-9f8b-b2609f76e8b1")</span></span>  
  
        Scaled Down Architecture with Information Worker Services  
  
 <span data-ttu-id="dd2dd-107">前の図では、サービス インターフェイス ドメインおよびサービス ドメイン内のサーバーは、BizTalk ホスト、および物理サーバーに対応します。</span><span class="sxs-lookup"><span data-stu-id="dd2dd-107">In the previous figure, the servers in the service interfaces and services domain correspond to BizTalk Hosts, and not physical servers.</span></span> <span data-ttu-id="dd2dd-108">追跡、ホスト インスタンスがスタンドアロン コンピューターにマスター シークレット サーバーおよび管理ツールを保持することをお勧めしますが、送信、処理、および複数のコンピューターで実行しているホストを受信します。</span><span class="sxs-lookup"><span data-stu-id="dd2dd-108">While it is recommended to keep the master secret server and the administrative tools in stand-alone computers, you can have host instances for the tracking, processing, send, and receive hosts running on multiple computers.</span></span> <span data-ttu-id="dd2dd-109">同様に、境界ネットワーク内のサーバーは、論理的な場所に対応します。</span><span class="sxs-lookup"><span data-stu-id="dd2dd-109">Similarly, the servers in the perimeter network correspond to logical locations.</span></span>  
  
 <span data-ttu-id="dd2dd-110">SMTP、Windows メッセージ キュー (MSMQ とも呼ばれます)、ファイル、および SQL の境界ネットワーク内のサーバーは、メール サーバー、キュー、ディレクトリ、または SQL Server それぞれ元の BizTalk 受信および送信ホスト、サービス インターフェイス ドメイン内に対応します。メッセージを送受信します。</span><span class="sxs-lookup"><span data-stu-id="dd2dd-110">The servers in the perimeter network for SMTP, Windows Message Queuing (also known as MSMQ), File, and SQL correspond to the mail servers, queue, directory, or SQL Server respectively from which the BizTalk receive and send hosts in the service interfaces domain receive and send messages.</span></span>  
  
 <span data-ttu-id="dd2dd-111">データ ドメイン内の BAM データベースは、BAM プライマリ インポート、BAM 分析、BAM スター スキーマ、および BAM アーカイブ データベースです。</span><span class="sxs-lookup"><span data-stu-id="dd2dd-111">The BAM databases in the data domain are BAM Primary Import, BAM Analysis, BAM Star Schema, and BAM Archive databases.</span></span> <span data-ttu-id="dd2dd-112">データ ドメイン内の追跡や分析データベースは、BizTalk Server を使用して追跡情報を格納するためのものです。</span><span class="sxs-lookup"><span data-stu-id="dd2dd-112">The Tracking and Analysis databases in the Data domain are the ones BizTalk Server uses for storing tracking information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd2dd-113">参照</span><span class="sxs-lookup"><span data-stu-id="dd2dd-113">See Also</span></span>  
 <span data-ttu-id="dd2dd-114">[縮小されたアーキテクチャ](../core/scaled-down-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="dd2dd-114">[Scaled Down Architecture](../core/scaled-down-architecture.md) </span></span>  
 <span data-ttu-id="dd2dd-115">[インフォメーション ワーカー サービスで大規模な分散アーキテクチャ](../core/large-distributed-architecture-with-information-worker-services.md) </span><span class="sxs-lookup"><span data-stu-id="dd2dd-115">[Large Distributed Architecture with Information Worker Services](../core/large-distributed-architecture-with-information-worker-services.md) </span></span>  
 <span data-ttu-id="dd2dd-116">[セキュリティで保護されたアーキテクチャの設計](../core/designing-a-secure-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="dd2dd-116">[Designing a Secure Architecture](../core/designing-a-secure-architecture.md) </span></span>  
 [<span data-ttu-id="dd2dd-117">BizTalk Server のサンプル アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="dd2dd-117">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)