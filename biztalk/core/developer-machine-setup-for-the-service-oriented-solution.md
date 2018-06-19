---
title: 開発者のコンピュータ設定、サービス指向ソリューション |Microsoft ドキュメント
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
ms.openlocfilehash: cb3407dbccbc4dccc902892cf04fa71991b8d93e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239458"
---
# <a name="developer-machine-setup-for-the-service-oriented-solution"></a><span data-ttu-id="e821e-102">サービス指向ソリューションに対する開発者のコンピュータ設定</span><span class="sxs-lookup"><span data-stu-id="e821e-102">Developer Machine Setup for the Service Oriented Solution</span></span>
<span data-ttu-id="e821e-103">サービス指向のアーキテクチャ (SOA) は、分散システムを構築するためのアプローチです。</span><span class="sxs-lookup"><span data-stu-id="e821e-103">Service Oriented Architecture (SOA) is an approach to building distributed systems.</span></span> <span data-ttu-id="e821e-104">サービス指向ソリューションでは、クライアントで使用できる 1 つのサービスにさまざまなプロトコルを使用して複数のバックエンド システムを集計することができますを示しています。</span><span class="sxs-lookup"><span data-stu-id="e821e-104">The service oriented solution demonstrates how several back-end systems using different protocols can be aggregated into a single service that clients can consume.</span></span> <span data-ttu-id="e821e-105">このソリューションでは、対象となるサービス レベル契約に適した配信やパフォーマンスの特性を保証するアプローチによって、各種のサービスを統合しています。</span><span class="sxs-lookup"><span data-stu-id="e821e-105">This solution integrates services with an approach that guarantees delivery and performance characteristics for the service level agreement that you need to satisfy.</span></span>  
  
 <span data-ttu-id="e821e-106">サービス指向ソリューションは、サービス レベル契約のシナリオをモデル化しています。ソリューションに接続されている BizTalk Server および基幹業務 (LOB) アプリケーション サーバーは、3 秒以内にサービス要求に応答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e821e-106">The service oriented solution is modeled after a service-level agreement scenario in which BizTalk Server and the Line of Business (LOB) application servers connected to it are given three seconds to respond with a service request.</span></span> <span data-ttu-id="e821e-107">この 3 秒間のうちの 1 秒は、BizTalk Server によって消費される場合があります。</span><span class="sxs-lookup"><span data-stu-id="e821e-107">One of those three seconds may be taken up by the BizTalk Server.</span></span>  
  
 <span data-ttu-id="e821e-108">サービス指向ソリューションの 3 つのバージョンがあります。 アダプタ、インライン、およびスタブ。</span><span class="sxs-lookup"><span data-stu-id="e821e-108">There are three versions of the service oriented solution: adapter, inline, and stub.</span></span> <span data-ttu-id="e821e-109">サービス指向ソリューションの 3 つのバージョンの違いの詳細については、次を参照してください。[サービス指向ソリューションを理解する](../core/understanding-the-service-oriented-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="e821e-109">For more information about the differences between three versions of the service-oriented solution, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span> <span data-ttu-id="e821e-110">開発者は、スタブ バージョンのシナリオを使用して、シナリオを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e821e-110">As a developer, you get the scenario running by using the stub version of the scenario.</span></span> <span data-ttu-id="e821e-111">このバージョンを実行するために LOB バックエンド サーバーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e821e-111">This version does not require any LOB back-end servers in order to run.</span></span> <span data-ttu-id="e821e-112">このシナリオの後で、アダプタ バージョンのシナリオを利用することにより、単一のサービスである BizTalk Server から応答を行う場合、さまざまなアダプタやバックエンド サーバーをどのように統合し、構成すればよいかを学習できます。</span><span class="sxs-lookup"><span data-stu-id="e821e-112">After this you can use the adapter version of the scenario to learn how various adapters and back-end servers can be integrated and configured to respond using the BizTalk servers as a single service.</span></span> <span data-ttu-id="e821e-113">また、BizTalk Server およびそのアダプタで発生した待機時間を測定できます。</span><span class="sxs-lookup"><span data-stu-id="e821e-113">You can then measure the latency induced by BizTalk Server and its adapters.</span></span>  
  
 <span data-ttu-id="e821e-114">BizTalk Server の待機時間がサービス要件を上回る場合、インライン バージョンの SOA のインストールと実行によって、LOB アダプタの永続化ポイントを無視できます。</span><span class="sxs-lookup"><span data-stu-id="e821e-114">If the latency for the BizTalk server is in excess of its service requirement, you can bypass the LOB adapter persistence points by installing and running the SOA in-line version.</span></span> <span data-ttu-id="e821e-115">このバージョンは、メッセージ ボックスの永続化ポイントにより、アダプタと後続の待機時間を無視します。</span><span class="sxs-lookup"><span data-stu-id="e821e-115">This version bypasses the adapters and subsequently their latency contributions due to the MessageBox persistence point.</span></span> <span data-ttu-id="e821e-116">代わりに、このインライン バージョンは、DCOM などのリモート プロシージャ コール (RPC) を使用して、バックエンド サーバーと直接対話します。</span><span class="sxs-lookup"><span data-stu-id="e821e-116">Instead, the inline version talks straight to the back-end servers through Remote Procedure Calls (RPC) mechanisms such as DCOM.</span></span>  
  
 <span data-ttu-id="e821e-117">メッセージ ボックスの永続化ポイントの詳細については、次を参照してください。[永続性と、オーケストレーション エンジン](../core/persistence-and-the-orchestration-engine.md)です。</span><span class="sxs-lookup"><span data-stu-id="e821e-117">For more information about the MessageBox persistence point, see [Persistence and the Orchestration Engine](../core/persistence-and-the-orchestration-engine.md).</span></span>  
  
 <span data-ttu-id="e821e-118">この展開ガイドでは、単一のコンピュータにサービス指向ソリューションの 3 つのバージョンをインストールしてテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e821e-118">This deployment guide describes how to install and test the three versions of the service-oriented solution on a single computer.</span></span>  
  
 <span data-ttu-id="e821e-119">サービス指向ソリューションの詳細については、次を参照してください。[サービス指向ソリューションを理解する](../core/understanding-the-service-oriented-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="e821e-119">For more information about the service-oriented solution, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e821e-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e821e-120">In This Section</span></span>  
  
-   [<span data-ttu-id="e821e-121">サービス指向ソリューションをインストールする前に</span><span class="sxs-lookup"><span data-stu-id="e821e-121">Before Installing the Service Oriented Solution</span></span>](../core/before-installing-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="e821e-122">指向ソリューションのスタブ バージョンのサービスをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="e821e-122">How to Install the Stub Version of the Service Oriented Solution</span></span>](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="e821e-123">指向ソリューションのインライン バージョンおよびアダプター バージョンのサービスをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="e821e-123">How to Install the Inline and Adapter Versions of the Service Oriented Solution</span></span>](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="e821e-124">指向ソリューションのサービスを実行する方法</span><span class="sxs-lookup"><span data-stu-id="e821e-124">How to Run the Service Oriented Solution</span></span>](../core/how-to-run-the-service-oriented-solution.md)