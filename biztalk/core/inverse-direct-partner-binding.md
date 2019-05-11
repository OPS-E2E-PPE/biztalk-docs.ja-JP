---
title: 逆のパートナーの直接バインド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, partners
- process management solution tutorial, partner binding
ms.assetid: 4cf8717a-2098-46f4-8f58-9d05fb562e2a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ead2c7e7ddf7a56d9a7746f47a7a3fbf1822d7f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330000"
---
# <a name="inverse-direct-partner-binding"></a><span data-ttu-id="78748-102">逆のパートナーの直接バインド</span><span class="sxs-lookup"><span data-stu-id="78748-102">Inverse Direct Partner Binding</span></span>
<span data-ttu-id="78748-103">ビジネス プロセス管理ソリューションは、アプリケーションを停止することがなく処理ステージの順序を変更できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="78748-103">The Business Process Management solution is designed so that you can change the order processing stages without stopping the application.</span></span> <span data-ttu-id="78748-104">処理ステージを分離するために (**CableOrder1**、 **CableOrder2**)、プロセス マネージャから (**OrderManager**)、ソリューションのさまざまな手法を使用します。これらのオーケストレーション ポートをバインドします。</span><span class="sxs-lookup"><span data-stu-id="78748-104">In order to decouple the processing stages (**CableOrder1**, **CableOrder2**) from the process manager (**OrderManager**), the solution uses a different technique for binding ports among these orchestrations.</span></span>  
  
 <span data-ttu-id="78748-105">バインドの通常の形式である直接バインド、 **OrderManager**オーケストレーションは、パートナー オーケストレーションのポートのプロパティの値として処理ステージ オーケストレーションを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="78748-105">In the usual form of binding, direct binding, the **OrderManager** orchestration would use the process stage orchestration as the value for the Partner Orchestration Port property.</span></span> <span data-ttu-id="78748-106">このような直接バインドで、 **OrderManager**オーケストレーションの処理ステージ (バージョンを含む) 厳密な名前によって異なります。</span><span class="sxs-lookup"><span data-stu-id="78748-106">In direct binding like this the **OrderManager** orchestration depends on the strong names (which include the versions) of the process stages.</span></span> <span data-ttu-id="78748-107">これにより、再デプロイせず処理ステージを変更不可能な**OrderManager**オーケストレーションします。</span><span class="sxs-lookup"><span data-stu-id="78748-107">This makes it impossible to alter the process stages without re-deploying the **OrderManager** orchestration.</span></span> <span data-ttu-id="78748-108">直接バインドの詳細については、次を参照してください。[ポートのバインド](../core/port-bindings.md)します。</span><span class="sxs-lookup"><span data-stu-id="78748-108">For more information about direct binding, see [Port Bindings](../core/port-bindings.md).</span></span> <span data-ttu-id="78748-109">直接バインドには、この方法を示す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="78748-109">Direct Binding might be illustrated this way:</span></span>  
  
 <span data-ttu-id="78748-110">![逆のパートナーの直接バインドの図](../core/media/bpm-inverse-direct-binding.gif "BPM_Inverse_Direct_Binding")</span><span class="sxs-lookup"><span data-stu-id="78748-110">![Diagram of Inverse Direct Partner Binding](../core/media/bpm-inverse-direct-binding.gif "BPM_Inverse_Direct_Binding")</span></span>  
  
 <span data-ttu-id="78748-111">逆のパートナーの直接バインド、受信側のオーケストレーションには、発信元のオーケストレーションではなく、バインディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="78748-111">In inverse direct partner binding, the receiving orchestration specifies the binding, rather than the originating orchestration.</span></span> <span data-ttu-id="78748-112">上のポート、 **OrderManager**自体にバインドされただけです。</span><span class="sxs-lookup"><span data-stu-id="78748-112">The port on the **OrderManager** is simply bound to itself.</span></span> <span data-ttu-id="78748-113">上のポートは、 **OrderManager**が指定されて、 **PartnerOrchestrationPort**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="78748-113">That is, the port on the **OrderManager** is specified for the **PartnerOrchestrationPort** property.</span></span> <span data-ttu-id="78748-114">ただし、処理ステージ オーケストレーションを適切な使用**OrderManager**ポートの値として、 **PartnerOrchestrationPort**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="78748-114">However, the process stage orchestrations use the appropriate **OrderManager** port as the value for the **PartnerOrchestrationPort** property.</span></span> <span data-ttu-id="78748-115">分離され、 **OrderManager**処理ステージ オーケストレーションのバージョンから再デプロイしなくても変更することを許可し、 **OrderManager**します。</span><span class="sxs-lookup"><span data-stu-id="78748-115">This decouples the **OrderManager** from the versions of the process stage orchestrations and allows them to be changed without redeploying the **OrderManager**.</span></span> <span data-ttu-id="78748-116">直接バインドでは、このような分離することはできません。</span><span class="sxs-lookup"><span data-stu-id="78748-116">Direct binding would not allow this decoupling.</span></span> <span data-ttu-id="78748-117">逆の直接パートナーがバインドには、この方法を示す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="78748-117">Inverse direct partner binding might be shown this way:</span></span>  
  
 <span data-ttu-id="78748-118">![直接バインドの図](../core/media/bpm-direct-binding.gif "BPM_Direct_Binding")</span><span class="sxs-lookup"><span data-stu-id="78748-118">![Diagram of Direct Binding](../core/media/bpm-direct-binding.gif "BPM_Direct_Binding")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78748-119">逆の直接バインドも配布リストなどの方法でパートナー オーケストレーションと通信できます。</span><span class="sxs-lookup"><span data-stu-id="78748-119">Inverse direct binding also allows for communicating with partner orchestrations in a distribution-list like way.</span></span> <span data-ttu-id="78748-120">**OrderManger**すべてのステージとの通信に 1 つのポートを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="78748-120">The **OrderManger** can use a single port to communicate with all stages.</span></span> <span data-ttu-id="78748-121">これにより、追加したり、オーケストレーションを再設計せずステージを削除できます。</span><span class="sxs-lookup"><span data-stu-id="78748-121">This enables you to add and remove stages without redesigning the orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78748-122">参照</span><span class="sxs-lookup"><span data-stu-id="78748-122">See Also</span></span>  
 <span data-ttu-id="78748-123">[ビジネス プロセス管理ソリューションの実装の要点](../core/implementation-highlights-of-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="78748-123">[Implementation Highlights of the Business Process Management Solution](../core/implementation-highlights-of-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="78748-124">プロセス マネージャーのロジック</span><span class="sxs-lookup"><span data-stu-id="78748-124">Process Manager Logic</span></span>](../core/process-manager-logic.md)