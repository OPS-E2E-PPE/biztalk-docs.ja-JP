---
title: "逆のパートナーの直接バインド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- bindings, partners
- process management solution tutorial, partner binding
ms.assetid: 4cf8717a-2098-46f4-8f58-9d05fb562e2a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6c9fe5e51f9f63ea098fa623dafbceeb670e75f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="inverse-direct-partner-binding"></a><span data-ttu-id="42f2e-102">逆のパートナーの直接バインド</span><span class="sxs-lookup"><span data-stu-id="42f2e-102">Inverse Direct Partner Binding</span></span>
<span data-ttu-id="42f2e-103">ビジネス プロセス管理ソリューションは、アプリケーションを停止せずに注文処理ステージを変更できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="42f2e-103">The Business Process Management solution is designed so that you can change the order processing stages without stopping the application.</span></span> <span data-ttu-id="42f2e-104">処理ステージを分離するために (**CableOrder1**、 **CableOrder2**)、プロセス マネージャから (**OrderManager**)、ソリューションのさまざまな手法を使用します。これらのオーケストレーション ポートをバインドします。</span><span class="sxs-lookup"><span data-stu-id="42f2e-104">In order to decouple the processing stages (**CableOrder1**, **CableOrder2**) from the process manager (**OrderManager**), the solution uses a different technique for binding ports among these orchestrations.</span></span>  
  
 <span data-ttu-id="42f2e-105">直接バインド、バインドの通常の形式で、 **OrderManager**オーケストレーションは、パートナー オーケストレーションのポートのプロパティの値として処理ステージ オーケストレーションを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="42f2e-105">In the usual form of binding, direct binding, the **OrderManager** orchestration would use the process stage orchestration as the value for the Partner Orchestration Port property.</span></span> <span data-ttu-id="42f2e-106">次のように直接バインドで、 **OrderManager**オーケストレーションは、厳密な名前 (バージョンを含む) の処理ステージによって異なります。</span><span class="sxs-lookup"><span data-stu-id="42f2e-106">In direct binding like this the **OrderManager** orchestration depends on the strong names (which include the versions) of the process stages.</span></span> <span data-ttu-id="42f2e-107">再配置することがなく処理ステージを変更不可能になります、 **OrderManager**オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="42f2e-107">This makes it impossible to alter the process stages without re-deploying the **OrderManager** orchestration.</span></span> <span data-ttu-id="42f2e-108">直接バインドの詳細については、次を参照してください。[ポートのバインド](../core/port-bindings.md)です。</span><span class="sxs-lookup"><span data-stu-id="42f2e-108">For more information about direct binding, see [Port Bindings](../core/port-bindings.md).</span></span> <span data-ttu-id="42f2e-109">直接バインドは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="42f2e-109">Direct Binding might be illustrated this way:</span></span>  
  
 <span data-ttu-id="42f2e-110">![逆のパートナーの直接バインドの図](../core/media/bpm-inverse-direct-binding.gif "BPM_Inverse_Direct_Binding")</span><span class="sxs-lookup"><span data-stu-id="42f2e-110">![Diagram of Inverse Direct Partner Binding](../core/media/bpm-inverse-direct-binding.gif "BPM_Inverse_Direct_Binding")</span></span>  
  
 <span data-ttu-id="42f2e-111">逆のパートナーの直接バインドでは、発信元オーケストレーションではなく受信オーケストレーションがバインドを指定します。</span><span class="sxs-lookup"><span data-stu-id="42f2e-111">In inverse direct partner binding, the receiving orchestration specifies the binding, rather than the originating orchestration.</span></span> <span data-ttu-id="42f2e-112">上のポート、 **OrderManager**が単にそれ自体にバインドされています。</span><span class="sxs-lookup"><span data-stu-id="42f2e-112">The port on the **OrderManager** is simply bound to itself.</span></span> <span data-ttu-id="42f2e-113">上のポートは、 **OrderManager**が指定されて、 **PartnerOrchestrationPort**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="42f2e-113">That is, the port on the **OrderManager** is specified for the **PartnerOrchestrationPort** property.</span></span> <span data-ttu-id="42f2e-114">ただし、処理ステージ オーケストレーションを適切な使用**OrderManager**ポートの値として、 **PartnerOrchestrationPort**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="42f2e-114">However, the process stage orchestrations use the appropriate **OrderManager** port as the value for the **PartnerOrchestrationPort** property.</span></span> <span data-ttu-id="42f2e-115">これは、切り離し、 **OrderManager**処理ステージ オーケストレーションのバージョンを再デプロイしなくても変更することができ、 **OrderManager**です。</span><span class="sxs-lookup"><span data-stu-id="42f2e-115">This decouples the **OrderManager** from the versions of the process stage orchestrations and allows them to be changed without redeploying the **OrderManager**.</span></span> <span data-ttu-id="42f2e-116">直接バインドでは、この分離はできません。</span><span class="sxs-lookup"><span data-stu-id="42f2e-116">Direct binding would not allow this decoupling.</span></span> <span data-ttu-id="42f2e-117">逆のパートナーの直接バインドは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="42f2e-117">Inverse direct partner binding might be shown this way:</span></span>  
  
 <span data-ttu-id="42f2e-118">![直接バインドの図](../core/media/bpm-direct-binding.gif "BPM_Direct_Binding")</span><span class="sxs-lookup"><span data-stu-id="42f2e-118">![Diagram of Direct Binding](../core/media/bpm-direct-binding.gif "BPM_Direct_Binding")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42f2e-119">逆の直接バインドでは、同報リストのような方法でパートナー オーケストレーションとやり取りすることもできます。</span><span class="sxs-lookup"><span data-stu-id="42f2e-119">Inverse direct binding also allows for communicating with partner orchestrations in a distribution-list like way.</span></span> <span data-ttu-id="42f2e-120">**OrderManger** 1 つのポートを使用して、すべてのステージと通信できます。</span><span class="sxs-lookup"><span data-stu-id="42f2e-120">The **OrderManger** can use a single port to communicate with all stages.</span></span> <span data-ttu-id="42f2e-121">したがって、オーケストレーションを再設計しないで、ステージを追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="42f2e-121">This enables you to add and remove stages without redesigning the orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42f2e-122">参照</span><span class="sxs-lookup"><span data-stu-id="42f2e-122">See Also</span></span>  
 <span data-ttu-id="42f2e-123">[ビジネス プロセス管理ソリューションの実装の要点](../core/implementation-highlights-of-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="42f2e-123">[Implementation Highlights of the Business Process Management Solution](../core/implementation-highlights-of-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="42f2e-124">プロセス マネージャのロジック</span><span class="sxs-lookup"><span data-stu-id="42f2e-124">Process Manager Logic</span></span>](../core/process-manager-logic.md)