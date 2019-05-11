---
title: サービスの実装の要点指向のソリューション |Microsoft Docs
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
ms.openlocfilehash: 47cc270e442964d46307a81c097df18085696107
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332501"
---
# <a name="implementation-highlights-of-the-service-oriented-solution"></a><span data-ttu-id="e08fc-102">サービスの実装の要点指向のソリューション</span><span class="sxs-lookup"><span data-stu-id="e08fc-102">Implementation Highlights of the Service Oriented Solution</span></span>
<span data-ttu-id="e08fc-103">ソリューションでは、特定のコンテキストで特定の問題は解決します。</span><span class="sxs-lookup"><span data-stu-id="e08fc-103">A solution solves a particular problem in a specific context.</span></span> <span data-ttu-id="e08fc-104">サービス指向ソリューションは例外ではありませんし、Microsoft に固有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]とシナリオ。</span><span class="sxs-lookup"><span data-stu-id="e08fc-104">The Service Oriented solution is no exception and is specific to Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the scenario.</span></span> <span data-ttu-id="e08fc-105">Woodgrove Bank シナリオの詳細については、次を参照してください。[サービス指向ソリューションを理解する](../core/understanding-the-service-oriented-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="e08fc-105">For more information about the Woodgrove Bank scenario, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span>  
  
 <span data-ttu-id="e08fc-106">シナリオの開発中に、いくつかの領域は、応答時間を許容できるレベルに削減するためにボトルネックになることがわかりました。</span><span class="sxs-lookup"><span data-stu-id="e08fc-106">While developing the scenario, several areas proved to be bottlenecks in reducing response times to an acceptable level.</span></span> <span data-ttu-id="e08fc-107">アダプターを使用して、バックエンド システムにメッセージを送信すると、応答の取得に長い待ち時間が導入されています。</span><span class="sxs-lookup"><span data-stu-id="e08fc-107">Sending messages to the backend systems using the adapters introduces significant latency in getting back responses.</span></span> <span data-ttu-id="e08fc-108">一般的に、アダプタ自体は非常に低待機時間を提供します。</span><span class="sxs-lookup"><span data-stu-id="e08fc-108">In general, adapters by themselves offer very low latency.</span></span> <span data-ttu-id="e08fc-109">ただし、BizTalk の分散アーキテクチャでは、メッセージ ボックスを使用してオーケストレーションのホスト インスタンスとの通信にアダプターが必要です。</span><span class="sxs-lookup"><span data-stu-id="e08fc-109">However, the distributed architecture of BizTalk requires adapters to communicate with the orchestration host instances using the message box.</span></span> <span data-ttu-id="e08fc-110">このため、データベースへのラウンド トリップが発生して、待機時間が影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="e08fc-110">This introduces round trips to the database and affects latency times.</span></span> <span data-ttu-id="e08fc-111">このため、ソリューション (最速のバージョン) ビルドのインライン バージョン、オーケストレーション自体のアダプター機能は、バックエンド システムを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e08fc-111">For this reason, the inline version of the solution (the fastest version) builds the adapter functionality in the orchestration itself calls the back-end systems directly.</span></span> <span data-ttu-id="e08fc-112">次の 3 つの異なるバックエンド システムでは、可能性のあるバックエンド システムとの通信に次の 3 つの異なるメカニズムを意味します。</span><span class="sxs-lookup"><span data-stu-id="e08fc-112">With three different back-end systems, that means potentially three different mechanisms to communicate with the back-end systems.</span></span>  
  
 <span data-ttu-id="e08fc-113">パフォーマンスの問題のことを証明した別の領域は、構成データからエンタープライズ シングル サインオン (SSO) を取得されました。</span><span class="sxs-lookup"><span data-stu-id="e08fc-113">Another area that proved a performance problem was retrieving configuration data from Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="e08fc-114">取得時間を短縮する一方、利便性や一般性を保持するには、ソリューションは、構成値をローカル キャッシュを使用します。</span><span class="sxs-lookup"><span data-stu-id="e08fc-114">To retain the convenience and universality of SSO while speeding up retrieval time, the solution uses a local cache for configuration values.</span></span> <span data-ttu-id="e08fc-115">SSO を使用すると、構成データの簡単な管理もできます。</span><span class="sxs-lookup"><span data-stu-id="e08fc-115">Using SSO also allows easier management of the configuration data.</span></span> <span data-ttu-id="e08fc-116">待機時間とパフォーマンス要件を満たすホスト インスタンスを追加では、ホスト インスタンスを実行するサーバー上の設定を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e08fc-116">Adding additional host instances to meet latency and performance requirements does not require changing settings on the server running the host instance.</span></span>  
  
 <span data-ttu-id="e08fc-117">コードから直接パイプラインの呼び出しは、ソリューションの別の例外的な要素です。</span><span class="sxs-lookup"><span data-stu-id="e08fc-117">Another unusual element of the solution is calling pipelines directly from code.</span></span> <span data-ttu-id="e08fc-118">これにより、カスタム パイプライン コンポーネントの再利用できます。</span><span class="sxs-lookup"><span data-stu-id="e08fc-118">This allows reuse of the custom pipeline components.</span></span>  
  
 <span data-ttu-id="e08fc-119">最後に、でも上げたい場合は、ソリューションの速度の最後のビットを変更することがいくつかの BizTalk Server の設定があります。</span><span class="sxs-lookup"><span data-stu-id="e08fc-119">Finally, there are several BizTalk Server settings that you can change to squeeze out the last bit of speed from the solution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e08fc-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e08fc-120">In This Section</span></span>  
  
-   [<span data-ttu-id="e08fc-121">バックエンドの呼び出しのインライン化</span><span class="sxs-lookup"><span data-stu-id="e08fc-121">Inlining Back-end Invocation</span></span>](../core/inlining-back-end-invocation.md)  
  
-   [<span data-ttu-id="e08fc-122">サービスで効率的に SSO を使用して指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="e08fc-122">Using SSO Efficiently in the Service Oriented Solution</span></span>](../core/using-sso-efficiently-in-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="e08fc-123">サービスからのパイプラインを使用して指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="e08fc-123">Using Pipelines from the Service Oriented Solution</span></span>](../core/using-pipelines-from-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="e08fc-124">チューニング、サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="e08fc-124">Tuning the Service Oriented Solution</span></span>](../core/tuning-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="e08fc-125">トランスポートの種類の分離と処理</span><span class="sxs-lookup"><span data-stu-id="e08fc-125">Decoupling Transport Type and Processing</span></span>](../core/decoupling-transport-type-and-processing.md)