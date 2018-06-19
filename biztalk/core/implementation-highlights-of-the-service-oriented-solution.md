---
title: サービスの実装の要点指向ソリューション |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, performance
- performance, service solutions
- service solution tutorial, implementing
ms.assetid: 3dbd8dfd-45b7-4290-ba07-b0c5e6264629
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c593c24c72e5666525001e6a52e2b0bf6eac2de
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257754"
---
# <a name="implementation-highlights-of-the-service-oriented-solution"></a><span data-ttu-id="d32c1-102">指向ソリューションのサービスの実装の要点</span><span class="sxs-lookup"><span data-stu-id="d32c1-102">Implementation Highlights of the Service Oriented Solution</span></span>
<span data-ttu-id="d32c1-103">ソリューションは、特定のコンテキストの特定の問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="d32c1-103">A solution solves a particular problem in a specific context.</span></span> <span data-ttu-id="d32c1-104">サービス指向ソリューションも例外ではなく、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] とそのシナリオに固有のソリューションです。</span><span class="sxs-lookup"><span data-stu-id="d32c1-104">The Service Oriented solution is no exception and is specific to Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the scenario.</span></span> <span data-ttu-id="d32c1-105">Woodgrove Bank シナリオの詳細については、次を参照してください。[サービス指向ソリューションを理解する](../core/understanding-the-service-oriented-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="d32c1-105">For more information about the Woodgrove Bank scenario, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span>  
  
 <span data-ttu-id="d32c1-106">シナリオを開発する際、応答時間を許容できるレベルに減らす上でボトルネックになる領域がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="d32c1-106">While developing the scenario, several areas proved to be bottlenecks in reducing response times to an acceptable level.</span></span> <span data-ttu-id="d32c1-107">アダプタを使用してメッセージをバックエンド システムに送信すると、応答を返す待機時間が長くなります。</span><span class="sxs-lookup"><span data-stu-id="d32c1-107">Sending messages to the backend systems using the adapters introduces significant latency in getting back responses.</span></span> <span data-ttu-id="d32c1-108">通常、アダプタ自体の待機時間は非常に短いものです。</span><span class="sxs-lookup"><span data-stu-id="d32c1-108">In general, adapters by themselves offer very low latency.</span></span> <span data-ttu-id="d32c1-109">ただし、BizTalk の分散アーキテクチャには、メッセージ ボックスを使用してオーケストレーションのホスト インスタンスと通信するアダプタが必要です。</span><span class="sxs-lookup"><span data-stu-id="d32c1-109">However, the distributed architecture of BizTalk requires adapters to communicate with the orchestration host instances using the message box.</span></span> <span data-ttu-id="d32c1-110">このため、データベースへのラウンド トリップが発生して、待機時間が影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="d32c1-110">This introduces round trips to the database and affects latency times.</span></span> <span data-ttu-id="d32c1-111">そのため、インライン バージョンのソリューション (最速のバージョン) は、オーケストレーション自体がバックエンド システムを直接呼び出すようにアダプタの機能を構築します。</span><span class="sxs-lookup"><span data-stu-id="d32c1-111">For this reason, the inline version of the solution (the fastest version) builds the adapter functionality in the orchestration itself calls the back-end systems directly.</span></span> <span data-ttu-id="d32c1-112">バックエンド システムが 3 種類あるため、3 つの異なるメカニズムを使用して、バックエンド システムと通信する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d32c1-112">With three different back-end systems, that means potentially three different mechanisms to communicate with the back-end systems.</span></span>  
  
 <span data-ttu-id="d32c1-113">パフォーマンスの問題が発生した別の領域では、エンタープライズ シングル サインオン (SSO) から構成データを取得していました。</span><span class="sxs-lookup"><span data-stu-id="d32c1-113">Another area that proved a performance problem was retrieving configuration data from Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="d32c1-114">取得時間を短縮する一方で利便性や一般性を保持するため、このソリューションでは、構成値にローカル キャッシュを使用します。</span><span class="sxs-lookup"><span data-stu-id="d32c1-114">To retain the convenience and universality of SSO while speeding up retrieval time, the solution uses a local cache for configuration values.</span></span> <span data-ttu-id="d32c1-115">SSO を使用しても、構成データを簡単に管理できます。</span><span class="sxs-lookup"><span data-stu-id="d32c1-115">Using SSO also allows easier management of the configuration data.</span></span> <span data-ttu-id="d32c1-116">待機時間とパフォーマンスの要件を満たすホスト インスタンスを追加する場合、ホスト インスタンスを実行するサーバーの設定を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d32c1-116">Adding additional host instances to meet latency and performance requirements does not require changing settings on the server running the host instance.</span></span>  
  
 <span data-ttu-id="d32c1-117">このソリューションの他の例外的な要素では、コードから直接パイプラインを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d32c1-117">Another unusual element of the solution is calling pipelines directly from code.</span></span> <span data-ttu-id="d32c1-118">このため、カスタム パイプライン コンポーネントを再利用できます。</span><span class="sxs-lookup"><span data-stu-id="d32c1-118">This allows reuse of the custom pipeline components.</span></span>  
  
 <span data-ttu-id="d32c1-119">最後に、このソリューションの速度を少しでも上げたい場合、複数の BizTalk Server 設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="d32c1-119">Finally, there are several BizTalk Server settings that you can change to squeeze out the last bit of speed from the solution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d32c1-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d32c1-120">In This Section</span></span>  
  
-   [<span data-ttu-id="d32c1-121">バック エンド呼び出しのインライン展開</span><span class="sxs-lookup"><span data-stu-id="d32c1-121">Inlining Back-end Invocation</span></span>](../core/inlining-back-end-invocation.md)  
  
-   [<span data-ttu-id="d32c1-122">指向ソリューションのサービスで SSO の効率的な使用</span><span class="sxs-lookup"><span data-stu-id="d32c1-122">Using SSO Efficiently in the Service Oriented Solution</span></span>](../core/using-sso-efficiently-in-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="d32c1-123">サービスからパイプラインを使用して指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="d32c1-123">Using Pipelines from the Service Oriented Solution</span></span>](../core/using-pipelines-from-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="d32c1-124">チューニング サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="d32c1-124">Tuning the Service Oriented Solution</span></span>](../core/tuning-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="d32c1-125">トランスポートの種類の分離と処理</span><span class="sxs-lookup"><span data-stu-id="d32c1-125">Decoupling Transport Type and Processing</span></span>](../core/decoupling-transport-type-and-processing.md)