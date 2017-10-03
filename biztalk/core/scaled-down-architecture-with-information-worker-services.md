---
title: "縮小されたアーキテクチャでは、インフォメーション ワーカー サービス |Microsoft ドキュメント"
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
ms.assetid: ce1217bf-84a5-4888-89ba-dce85dc38340
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d02558e5904bf740c09ea0db614b2189555ac75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scaled-down-architecture-with-information-worker-services"></a><span data-ttu-id="63be5-102">インフォメーション ワーカー サービスを使用した縮小されたアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="63be5-102">Scaled Down Architecture with Information Worker Services</span></span>
<span data-ttu-id="63be5-103">BizTalk Server の展開のシステム アーキテクチャに関する詳細については、次を参照してください。[サンプル BizTalk Server アーキテクチャ](../core/sample-biztalk-server-architectures.md)です。</span><span class="sxs-lookup"><span data-stu-id="63be5-103">For complete information about the system architecture for BizTalk Server deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="63be5-104">次の図は、インフォメーション ワーカー サービスを含むサンプル BizTalk Server アーキテクチャを示しています。このアーキテクチャでは、ドメインの一部と BizTalk Server を組み合わせて、必要なサーバーおよびファイアウォールの数を削減します。</span><span class="sxs-lookup"><span data-stu-id="63be5-104">The following figure provides a sample BizTalk Server architecture including the information worker services that combines some of the domains and BizTalk Servers to reduce the number of servers and firewalls you need.</span></span> <span data-ttu-id="63be5-105">このアーキテクチャは、最も分散されたアーキテクチャではありませんが、BizTalk Server をその機能に基づいて分離しています。</span><span class="sxs-lookup"><span data-stu-id="63be5-105">While this architecture is not the most distributed, it still separates the BizTalk Servers based on their function.</span></span>  
  
 <span data-ttu-id="63be5-106">![スケール ダウン トポロジ](../core/media/cd3c85df-40f5-4382-9f8b-b2609f76e8b1.gif "cd3c85df-40f5-4382-9f8b-b2609f76e8b1")</span><span class="sxs-lookup"><span data-stu-id="63be5-106">![Scaledown Topology](../core/media/cd3c85df-40f5-4382-9f8b-b2609f76e8b1.gif "cd3c85df-40f5-4382-9f8b-b2609f76e8b1")</span></span>  
  
        Scaled Down Architecture with Information Worker Services  
  
 <span data-ttu-id="63be5-107">上記の図では、サービス インターフェイスおよびサービス ドメイン内のサーバーは、物理サーバーではなく BizTalk ホストに対応しています。</span><span class="sxs-lookup"><span data-stu-id="63be5-107">In the previous figure, the servers in the service interfaces and services domain correspond to BizTalk Hosts, and not physical servers.</span></span> <span data-ttu-id="63be5-108">マスタ シークレット サーバーおよび管理ツールはスタンドアロン コンピュータに保持しておくことをお勧めしますが、複数のコンピュータ上で実行している追跡ホスト、処理ホスト、送信ホスト、および受信ホスト用にホスト インスタンスを配置できます。</span><span class="sxs-lookup"><span data-stu-id="63be5-108">While it is recommended to keep the master secret server and the administrative tools in stand-alone computers, you can have host instances for the tracking, processing, send, and receive hosts running on multiple computers.</span></span> <span data-ttu-id="63be5-109">同様に、境界ネットワーク内のサーバーは、論理的な場所に対応しています。</span><span class="sxs-lookup"><span data-stu-id="63be5-109">Similarly, the servers in the perimeter network correspond to logical locations.</span></span>  
  
 <span data-ttu-id="63be5-110">境界ネットワーク内にある、SMTP、Windows メッセージ キュー (MSMQ)、ファイル、SQL 用のサーバーはそれぞれメール サーバー、キュー、ディレクトリ、SQL Server に対応し、サービス インターフェイス ドメイン内の BizTalk 受信ホストと送信ホストはここからメッセージの送受信を行います。</span><span class="sxs-lookup"><span data-stu-id="63be5-110">The servers in the perimeter network for SMTP, Windows Message Queuing (also known as MSMQ), File, and SQL correspond to the mail servers, queue, directory, or SQL Server respectively from which the BizTalk receive and send hosts in the service interfaces domain receive and send messages.</span></span>  
  
 <span data-ttu-id="63be5-111">データ ドメイン内の BAM データベースは、BAM プライマリ インポート データベース、BAM 分析データベース、BAM スター スキーマ データベース、および BAM アーカイブ データベースです。</span><span class="sxs-lookup"><span data-stu-id="63be5-111">The BAM databases in the data domain are BAM Primary Import, BAM Analysis, BAM Star Schema, and BAM Archive databases.</span></span> <span data-ttu-id="63be5-112">データ ドメイン内の追跡データベースおよび分析データベースは、BizTalk Server で追跡情報を格納する際に使用するデータベースです。</span><span class="sxs-lookup"><span data-stu-id="63be5-112">The Tracking and Analysis databases in the Data domain are the ones BizTalk Server uses for storing tracking information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63be5-113">参照</span><span class="sxs-lookup"><span data-stu-id="63be5-113">See Also</span></span>  
 <span data-ttu-id="63be5-114">[縮小されたアーキテクチャ](../core/scaled-down-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="63be5-114">[Scaled Down Architecture](../core/scaled-down-architecture.md) </span></span>  
 <span data-ttu-id="63be5-115">[インフォメーション ワーカー サービスで大規模な分散アーキテクチャ](../core/large-distributed-architecture-with-information-worker-services.md) </span><span class="sxs-lookup"><span data-stu-id="63be5-115">[Large Distributed Architecture with Information Worker Services](../core/large-distributed-architecture-with-information-worker-services.md) </span></span>  
 <span data-ttu-id="63be5-116">[セキュリティで保護されたアーキテクチャの設計](../core/designing-a-secure-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="63be5-116">[Designing a Secure Architecture](../core/designing-a-secure-architecture.md) </span></span>  
 [<span data-ttu-id="63be5-117">BizTalk Server のサンプル アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="63be5-117">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)