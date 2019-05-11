---
title: サービスの開発者のコンピューター設定指向のソリューション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developer servers
- service solution tutorial, deployment prerequisites
- service solution tutorial, developer servers
ms.assetid: a088696f-c1ee-4578-ac02-af29b6de086b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7a296118d9154d51ffc1dba22524a50cc7e76b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351594"
---
# <a name="developer-machine-setup-for-the-service-oriented-solution"></a><span data-ttu-id="5b19a-102">指向ソリューションのサービスの開発者のコンピュータ設定</span><span class="sxs-lookup"><span data-stu-id="5b19a-102">Developer Machine Setup for the Service Oriented Solution</span></span>
<span data-ttu-id="5b19a-103">サービス指向アーキテクチャ (SOA) は、分散システムを構築する方法です。</span><span class="sxs-lookup"><span data-stu-id="5b19a-103">Service Oriented Architecture (SOA) is an approach to building distributed systems.</span></span> <span data-ttu-id="5b19a-104">サービス指向ソリューションでは、クライアントが利用できる 1 つのサービスに集約できるさまざまなプロトコルを使用して複数のバックエンド システムを示します。</span><span class="sxs-lookup"><span data-stu-id="5b19a-104">The service oriented solution demonstrates how several back-end systems using different protocols can be aggregated into a single service that clients can consume.</span></span> <span data-ttu-id="5b19a-105">このソリューションでは、配信およびパフォーマンスの特性を満たすために必要なサービス レベル アグリーメントを保証するアプローチとサービスを統合します。</span><span class="sxs-lookup"><span data-stu-id="5b19a-105">This solution integrates services with an approach that guarantees delivery and performance characteristics for the service level agreement that you need to satisfy.</span></span>  
  
 <span data-ttu-id="5b19a-106">サービス指向ソリューションがモデルに BizTalk Server および基幹業務 (LOB) アプリケーション サーバーが接続されたサービス レベル アグリーメントによってシナリオには、サービス要求に応答する 3 秒が与えられます。</span><span class="sxs-lookup"><span data-stu-id="5b19a-106">The service oriented solution is modeled after a service-level agreement scenario in which BizTalk Server and the Line of Business (LOB) application servers connected to it are given three seconds to respond with a service request.</span></span> <span data-ttu-id="5b19a-107">この 3 秒間のいずれかが占有されます、BizTalk Server でします。</span><span class="sxs-lookup"><span data-stu-id="5b19a-107">One of those three seconds may be taken up by the BizTalk Server.</span></span>  
  
 <span data-ttu-id="5b19a-108">サービス指向ソリューションの 3 つのバージョンがあります。 アダプタ、インライン、およびスタブ。</span><span class="sxs-lookup"><span data-stu-id="5b19a-108">There are three versions of the service oriented solution: adapter, inline, and stub.</span></span> <span data-ttu-id="5b19a-109">サービス指向ソリューションの 3 つのバージョンの違いの詳細については、次を参照してください。[サービス指向ソリューションを理解する](../core/understanding-the-service-oriented-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="5b19a-109">For more information about the differences between three versions of the service-oriented solution, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span> <span data-ttu-id="5b19a-110">開発者は、シナリオのスタブ バージョンを使用して実行中のシナリオを取得します。</span><span class="sxs-lookup"><span data-stu-id="5b19a-110">As a developer, you get the scenario running by using the stub version of the scenario.</span></span> <span data-ttu-id="5b19a-111">このバージョンでは、実行するには、LOB バックエンド サーバーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5b19a-111">This version does not require any LOB back-end servers in order to run.</span></span> <span data-ttu-id="5b19a-112">その後は、さまざまな方法のアダプターとバック エンド サーバーを統合および 1 つのサービスとして、BizTalk server を使用して応答するのにように構成シナリオのアダプター バージョンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5b19a-112">After this you can use the adapter version of the scenario to learn how various adapters and back-end servers can be integrated and configured to respond using the BizTalk servers as a single service.</span></span> <span data-ttu-id="5b19a-113">BizTalk Server およびそのアダプターで誘発される待機時間を測定できます。</span><span class="sxs-lookup"><span data-stu-id="5b19a-113">You can then measure the latency induced by BizTalk Server and its adapters.</span></span>  
  
 <span data-ttu-id="5b19a-114">BizTalk server の待機時間は、そのサービスの要件を超える場合は、インストールし、SOA で行のバージョンを実行して、LOB アダプタの永続化ポイントをバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="5b19a-114">If the latency for the BizTalk server is in excess of its service requirement, you can bypass the LOB adapter persistence points by installing and running the SOA in-line version.</span></span> <span data-ttu-id="5b19a-115">このバージョンは、アダプタと後続のメッセージ ボックスの永続化ポイントが原因の待機時間の投稿をバイパスします。</span><span class="sxs-lookup"><span data-stu-id="5b19a-115">This version bypasses the adapters and subsequently their latency contributions due to the MessageBox persistence point.</span></span> <span data-ttu-id="5b19a-116">代わりに、インライン バージョンは、DCOM などのリモート プロシージャ コール (RPC) メカニズムによってバックエンド サーバーに直接アクセスで説明します。</span><span class="sxs-lookup"><span data-stu-id="5b19a-116">Instead, the inline version talks straight to the back-end servers through Remote Procedure Calls (RPC) mechanisms such as DCOM.</span></span>  
  
 <span data-ttu-id="5b19a-117">メッセージ ボックスの永続化ポイントの詳細については、次を参照してください。[永続性とオーケストレーション エンジン](../core/persistence-and-the-orchestration-engine.md)します。</span><span class="sxs-lookup"><span data-stu-id="5b19a-117">For more information about the MessageBox persistence point, see [Persistence and the Orchestration Engine](../core/persistence-and-the-orchestration-engine.md).</span></span>  
  
 <span data-ttu-id="5b19a-118">このデプロイ ガイドでは、インストールし、1 台のコンピューターでサービス指向ソリューションの 3 つのバージョンをテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5b19a-118">This deployment guide describes how to install and test the three versions of the service-oriented solution on a single computer.</span></span>  
  
 <span data-ttu-id="5b19a-119">サービス指向ソリューションの詳細については、次を参照してください。[サービス指向ソリューションを理解する](../core/understanding-the-service-oriented-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="5b19a-119">For more information about the service-oriented solution, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5b19a-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5b19a-120">In This Section</span></span>  
  
-   [<span data-ttu-id="5b19a-121">サービス指向ソリューションをインストールする前に</span><span class="sxs-lookup"><span data-stu-id="5b19a-121">Before Installing the Service Oriented Solution</span></span>](../core/before-installing-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="5b19a-122">指向ソリューションのスタブ バージョンのサービスをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="5b19a-122">How to Install the Stub Version of the Service Oriented Solution</span></span>](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="5b19a-123">指向ソリューションのインライン バージョンおよびアダプター バージョンのサービスをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="5b19a-123">How to Install the Inline and Adapter Versions of the Service Oriented Solution</span></span>](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="5b19a-124">指向ソリューションのサービスを実行する方法</span><span class="sxs-lookup"><span data-stu-id="5b19a-124">How to Run the Service Oriented Solution</span></span>](../core/how-to-run-the-service-oriented-solution.md)