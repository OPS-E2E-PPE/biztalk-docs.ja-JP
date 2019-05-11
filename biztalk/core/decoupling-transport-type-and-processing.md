---
title: トランスポートの種類の分離と処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23a65f525664d44a53760e5cb905e4db10f0f8a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352467"
---
# <a name="decoupling-transport-type-and-processing"></a><span data-ttu-id="6f010-102">トランスポートの種類の分離と処理</span><span class="sxs-lookup"><span data-stu-id="6f010-102">Decoupling Transport Type and Processing</span></span>
<span data-ttu-id="6f010-103">サービス指向ソリューションでは、クリア行は、多くの場合、ビジネス プロセスとメッセージの送受信の詳細の間存在します。</span><span class="sxs-lookup"><span data-stu-id="6f010-103">In a service oriented solution, a clear line often exists between the business processing and the specifics of transmitting and receiving messages.</span></span> <span data-ttu-id="6f010-104">これにより、ビジネス プロセスまたはソリューションのメッセージ処理部分を個別に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="6f010-104">This enables you to change the business process or the messaging part of the solution independently.</span></span>  
  
 <span data-ttu-id="6f010-105">サービス指向ソリューションでは、1 つの場所では、この設計原則に違反します。</span><span class="sxs-lookup"><span data-stu-id="6f010-105">The service oriented solution violates this design principle in one place.</span></span> <span data-ttu-id="6f010-106">このセクションでは、状況、代替、および選択されている構造について説明します。</span><span class="sxs-lookup"><span data-stu-id="6f010-106">This section describes the situation, the possible alternatives, and the selected structure.</span></span>  
  
## <a name="correlation-and-the-mqseries-adapter"></a><span data-ttu-id="6f010-107">関連付けと MQSeries アダプター</span><span class="sxs-lookup"><span data-stu-id="6f010-107">Correlation and the MQSeries Adapter</span></span>  
 <span data-ttu-id="6f010-108">MQSeries アダプターを使用するには、標準の BizTalk Server 関連付け識別子を使用できません。</span><span class="sxs-lookup"><span data-stu-id="6f010-108">In order to use the MQSeries adapter, you cannot use the standard BizTalk Server correlation identifiers.</span></span> <span data-ttu-id="6f010-109">これは、相関関係 id を独自の関連付け識別子システムを持つ IBM バックエンド システムに移動するためです。</span><span class="sxs-lookup"><span data-stu-id="6f010-109">This is because the correlation identifier goes to an IBM back-end system that has its own system of correlation identifiers.</span></span> <span data-ttu-id="6f010-110">代わりに、使用する必要があります、 **MQSeries.MQMD_CorrelId**と**MQSeries.MQMD_MsgID**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="6f010-110">Instead, you must use the **MQSeries.MQMD_CorrelId** and **MQSeries.MQMD_MsgID** properties.</span></span> <span data-ttu-id="6f010-111">オーケストレーションで、そのため、ビジネス プロセスのトランスポートに固有の情報を配置する可能性があるこれらのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="6f010-111">Using these properties potentially puts transport-specific information in the orchestration and, thus, in the business process.</span></span>  
  
 <span data-ttu-id="6f010-112">この依存関係を処理する方法の 1 つは、BizTalk Server 関連付け識別子を使用して、for MQSeries 関連付け識別子を変換するカスタム パイプライン コンポーネントを使用することです。</span><span class="sxs-lookup"><span data-stu-id="6f010-112">One way to handle this dependency would be to use the BizTalk Server correlation identifier and use a custom pipeline component to translate the correlation identifier for MQSeries.</span></span> <span data-ttu-id="6f010-113">これにより、複雑さがシナリオに追加します。</span><span class="sxs-lookup"><span data-stu-id="6f010-113">This adds complexity to the scenario.</span></span> <span data-ttu-id="6f010-114">さらに、トランスポートが変更された場合、2 つのパイプライン コンポーネントを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f010-114">In addition, if the transport changes, two pipeline components must be changed.</span></span> <span data-ttu-id="6f010-115">また、それを解決するのではなく、(パイプラインのコンポーネント) 内の依存関係を再配置が最終的には。</span><span class="sxs-lookup"><span data-stu-id="6f010-115">And, ultimately, it relocates the dependency (in the pipeline component) rather than resolving it.</span></span>  
  
 <span data-ttu-id="6f010-116">別のオプションは、MQSeries 固有の関連付けを個別のオーケストレーション処理を分離し、そのオーケストレーションの呼び出しになります。</span><span class="sxs-lookup"><span data-stu-id="6f010-116">Another option would be to isolate the MQSeries-specific correlation handling to a separate orchestration and call that orchestration.</span></span> <span data-ttu-id="6f010-117">これにより、ビジネス プロセスの独立性が保持されます。</span><span class="sxs-lookup"><span data-stu-id="6f010-117">This would preserve the independence of the business process.</span></span> <span data-ttu-id="6f010-118">ただし、これは、オーケストレーションのコンパイル時の依存関係について説明します。</span><span class="sxs-lookup"><span data-stu-id="6f010-118">However, this introduces a compile-time dependency between the orchestrations.</span></span> <span data-ttu-id="6f010-119">トランスポートを変更するには、両方のオーケストレーション (として、たとえばの移行のスタブからソリューションのアダプター バージョンに) 再コンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f010-119">Modifying the transport requires recompiling both orchestrations (as, for example, in going from the stub to the adapter version of the solution).</span></span> <span data-ttu-id="6f010-120">呼び出しは、ソリューションの応答時間にも追加します。</span><span class="sxs-lookup"><span data-stu-id="6f010-120">The call also adds to the response time for the solution.</span></span>  
  
 <span data-ttu-id="6f010-121">追加の複雑性とパフォーマンスが低下することを指定するには、ことが最も簡単、オーケストレーションから直接 MQSeries の関連付けを使用します。</span><span class="sxs-lookup"><span data-stu-id="6f010-121">Given the additional complexity and possible decrease in performance, it seemed simplest to use the MQSeries correlation directly in the orchestration.</span></span>  
  
 <span data-ttu-id="6f010-122">アダプターとオーケストレーションの相関関係の詳細については、次を参照してください。 [MQSCorrelationSetOrchestration (BizTalk Server サンプル)](../core/mqscorrelationsetorchestration-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="6f010-122">For more information about the adapter and correlations in orchestrations, see [MQSCorrelationSetOrchestration (BizTalk Server Sample)](../core/mqscorrelationsetorchestration-biztalk-server-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f010-123">参照</span><span class="sxs-lookup"><span data-stu-id="6f010-123">See Also</span></span>  
 <span data-ttu-id="6f010-124">[サービスの実装の要点指向のソリューション](../core/implementation-highlights-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="6f010-124">[Implementation Highlights of the Service Oriented Solution](../core/implementation-highlights-of-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="6f010-125">MQSCorrelationSetOrchestration (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="6f010-125">MQSCorrelationSetOrchestration (BizTalk Server Sample)</span></span>](../core/mqscorrelationsetorchestration-biztalk-server-sample.md)