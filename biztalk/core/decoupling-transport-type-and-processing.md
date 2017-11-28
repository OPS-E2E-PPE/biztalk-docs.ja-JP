---
title: "トランスポートの種類の分離と処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transport types, decoupling processing
- processing, decoupling transport types
- transport types
- transport types, service solutions
- service solution tutorial, MQSeries adapters
- processing, service solutions
- service solution tutorial, decoupling transport type and processing
- correlations, MQSeries adapters
- MQSeries adapters, correlations
- MQSeries adapters, service solutions
ms.assetid: 0b2c733a-e2c7-42ff-a733-f712fde38f7e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b14522c6bbf9393bc22f632c4db5eeb5e4a22a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="decoupling-transport-type-and-processing"></a><span data-ttu-id="ea05d-102">トランスポートの種類の分離と処理</span><span class="sxs-lookup"><span data-stu-id="ea05d-102">Decoupling Transport Type and Processing</span></span>
<span data-ttu-id="ea05d-103">サービス指向ソリューションでは、ビジネス プロセスとメッセージの送受信の詳細を明確に区別することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="ea05d-103">In a service oriented solution, a clear line often exists between the business processing and the specifics of transmitting and receiving messages.</span></span> <span data-ttu-id="ea05d-104">これによって、ビジネス プロセスまたはソリューションのメッセージ処理部分を個別に変更できます。</span><span class="sxs-lookup"><span data-stu-id="ea05d-104">This enables you to change the business process or the messaging part of the solution independently.</span></span>  
  
 <span data-ttu-id="ea05d-105">サービス指向ソリューションには、この設計方針に違反する箇所が 1 か所あります。</span><span class="sxs-lookup"><span data-stu-id="ea05d-105">The service oriented solution violates this design principle in one place.</span></span> <span data-ttu-id="ea05d-106">このセクションでは、状況、可能性のある代替方法、および選択された構造について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea05d-106">This section describes the situation, the possible alternatives, and the selected structure.</span></span>  
  
## <a name="correlation-and-the-mqseries-adapter"></a><span data-ttu-id="ea05d-107">関連付けと MQSeries アダプタ</span><span class="sxs-lookup"><span data-stu-id="ea05d-107">Correlation and the MQSeries Adapter</span></span>  
 <span data-ttu-id="ea05d-108">MQSeries アダプタを使用するため、標準の BizTalk Server 関連付け識別子は使用できません。</span><span class="sxs-lookup"><span data-stu-id="ea05d-108">In order to use the MQSeries adapter, you cannot use the standard BizTalk Server correlation identifiers.</span></span> <span data-ttu-id="ea05d-109">独自の関連付け識別子システムを持つ IBM バックエンド システムに関連付け識別子が使用されるためです。</span><span class="sxs-lookup"><span data-stu-id="ea05d-109">This is because the correlation identifier goes to an IBM back-end system that has its own system of correlation identifiers.</span></span> <span data-ttu-id="ea05d-110">代わりに、使用する必要があります、 **MQSeries.MQMD_CorrelId**と**MQSeries.MQMD_MsgID**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="ea05d-110">Instead, you must use the **MQSeries.MQMD_CorrelId** and **MQSeries.MQMD_MsgID** properties.</span></span> <span data-ttu-id="ea05d-111">これらのプロパティを使用すると、トランスポート固有の情報がオーケストレーション (つまり、ビジネス プロセス) に配置されることがあります。</span><span class="sxs-lookup"><span data-stu-id="ea05d-111">Using these properties potentially puts transport-specific information in the orchestration and, thus, in the business process.</span></span>  
  
 <span data-ttu-id="ea05d-112">この依存関係を処理するには、BizTalk Server の関連付け識別子を使用し、カスタム パイプライン コンポーネントを使用して MQSeries の関連付け識別子を変換する方法があります。</span><span class="sxs-lookup"><span data-stu-id="ea05d-112">One way to handle this dependency would be to use the BizTalk Server correlation identifier and use a custom pipeline component to translate the correlation identifier for MQSeries.</span></span> <span data-ttu-id="ea05d-113">これにより、シナリオが複雑になります。</span><span class="sxs-lookup"><span data-stu-id="ea05d-113">This adds complexity to the scenario.</span></span> <span data-ttu-id="ea05d-114">また、トランスポートが変更された場合、2 つのパイプライン コンポーネントを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea05d-114">In addition, if the transport changes, two pipeline components must be changed.</span></span> <span data-ttu-id="ea05d-115">最終的に、パイプライン コンポーネントの依存関係が解決されないで再配置されます。</span><span class="sxs-lookup"><span data-stu-id="ea05d-115">And, ultimately, it relocates the dependency (in the pipeline component) rather than resolving it.</span></span>  
  
 <span data-ttu-id="ea05d-116">別の方法として、MQSeries 固有の関連付け処理を個別のオーケストレーションに分離し、そのオーケストレーションを呼び出す方法があります。</span><span class="sxs-lookup"><span data-stu-id="ea05d-116">Another option would be to isolate the MQSeries-specific correlation handling to a separate orchestration and call that orchestration.</span></span> <span data-ttu-id="ea05d-117">これにより、ビジネス プロセスの独立性が確保されます。</span><span class="sxs-lookup"><span data-stu-id="ea05d-117">This would preserve the independence of the business process.</span></span> <span data-ttu-id="ea05d-118">ただし、オーケストレーション間のコンパイル時の依存関係が発生します。</span><span class="sxs-lookup"><span data-stu-id="ea05d-118">However, this introduces a compile-time dependency between the orchestrations.</span></span> <span data-ttu-id="ea05d-119">トランスポートを変更する場合、両方のオーケストレーションの再コンパイルが必要です (ソリューションのスタブ バージョンからアダプタ バージョンへの移行など)。</span><span class="sxs-lookup"><span data-stu-id="ea05d-119">Modifying the transport requires recompiling both orchestrations (as, for example, in going from the stub to the adapter version of the solution).</span></span> <span data-ttu-id="ea05d-120">また、この呼び出しにより、ソリューションの応答時間が長くなります。</span><span class="sxs-lookup"><span data-stu-id="ea05d-120">The call also adds to the response time for the solution.</span></span>  
  
 <span data-ttu-id="ea05d-121">複雑になりパフォーマンスが低下する可能性を考慮した場合、オーケストレーションの MQSeries の関連付けを直接使用することが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="ea05d-121">Given the additional complexity and possible decrease in performance, it seemed simplest to use the MQSeries correlation directly in the orchestration.</span></span>  
  
 <span data-ttu-id="ea05d-122">アダプターとオーケストレーションの相関関係に関する詳細については、次を参照してください。 [MQSCorrelationSetOrchestration (BizTalk Server サンプル)](../core/mqscorrelationsetorchestration-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="ea05d-122">For more information about the adapter and correlations in orchestrations, see [MQSCorrelationSetOrchestration (BizTalk Server Sample)](../core/mqscorrelationsetorchestration-biztalk-server-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea05d-123">参照</span><span class="sxs-lookup"><span data-stu-id="ea05d-123">See Also</span></span>  
 <span data-ttu-id="ea05d-124">[指向ソリューションのサービスの実装の要点](../core/implementation-highlights-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="ea05d-124">[Implementation Highlights of the Service Oriented Solution](../core/implementation-highlights-of-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="ea05d-125">MQSCorrelationSetOrchestration (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="ea05d-125">MQSCorrelationSetOrchestration (BizTalk Server Sample)</span></span>](../core/mqscorrelationsetorchestration-biztalk-server-sample.md)