---
title: "Order Handler オブジェクトを使用して、バックエンド システムと通信する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IOrderHandler interface
- process management solution tutorial, IOrderHandler interface
ms.assetid: b9fe4120-bf2a-4d15-a34b-6b98f026b984
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d7621c4e5737def0e9fc0682de709ae57f98790
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-order-handler-object-to-communicate-with-backend-systems"></a><span data-ttu-id="483c3-102">Order Handler オブジェクトを使用して、バックエンド システムと通信するには</span><span class="sxs-lookup"><span data-stu-id="483c3-102">Using the Order Handler Object to Communicate with Backend Systems</span></span>
<span data-ttu-id="483c3-103">最終的な注文を受信する既存のバックエンド システムである Cable Provisioning System とビジネス プロセス管理ソリューションが通信する方法は多数存在します。</span><span class="sxs-lookup"><span data-stu-id="483c3-103">There are many ways in which the business process management solution could communicate with the legacy back-end order system, the cable provisioning system that receives the final orders.</span></span> <span data-ttu-id="483c3-104">このソリューションでは、Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] で提供されている .NET リモート処理機能を使用して Provisioning System と通信します。</span><span class="sxs-lookup"><span data-stu-id="483c3-104">The solution uses the .NET remoting facilities found in Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] to communicate with the provisioning system.</span></span>  
  
 <span data-ttu-id="483c3-105">このソリューションでは、インターフェイスを使用してバックエンド システムに対するアクセス オブジェクトを定義する一般的な方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="483c3-105">The solution uses a common technique of using an interface to define the access object to the back-end system.</span></span> <span data-ttu-id="483c3-106">独立したアセンブリにインターフェイスを配置することにより、クライアント アセンブリは、コンパイルされたアセンブリにアクセスする必要なく、リモート オブジェクトにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="483c3-106">By putting the interface in a separate assembly the client assembly can have access to the remote object without having to have access to the compiled assembly.</span></span>  
  
 <span data-ttu-id="483c3-107">**IOrderHandler**インターフェイスが、バックエンド注文システムと通信するメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="483c3-107">The **IOrderHandler** interface defines the methods to communicate with the backend order system.</span></span> <span data-ttu-id="483c3-108">このインターフェイスには、注文の分析、アクティブ化、取り消し、および完了を行うためのメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="483c3-108">The interface includes methods for analyzing, activating, canceling, and completing orders.</span></span> <span data-ttu-id="483c3-109">サービスの種類、注文が取り消されたときに必要なメソッドを識別するためのメソッドも用意されています。</span><span class="sxs-lookup"><span data-stu-id="483c3-109">It also provides a method for identifying the service type, a method needed when an order is canceled.</span></span>  
  
 <span data-ttu-id="483c3-110">**CableOrder1**、 **CableOrder2**、サテライト オーケストレーションを使用して、 **OrderHandlerWrapper**を実装するオブジェクト**IOrderHandler**.</span><span class="sxs-lookup"><span data-stu-id="483c3-110">The **CableOrder1**, **CableOrder2**, and satellite orchestrations use the **OrderHandlerWrapper** object that implements **IOrderHandler**.</span></span> <span data-ttu-id="483c3-111">**OrderHandlerWrapper**オブジェクト、さらのリモート インスタンスを起動、 **OrderHandler**オブジェクトによって提供される、 **CableProvisioningSystemServer**実行可能ファイルです。</span><span class="sxs-lookup"><span data-stu-id="483c3-111">The **OrderHandlerWrapper** object, in turn, invokes a remote instance of an **OrderHandler** object provided by the **CableProvisioningSystemServer** executable.</span></span> <span data-ttu-id="483c3-112">ラッパー オブジェクトを使用することにより、バックエンドの注文システムと通信するために .NET リモート処理を使用するビジネス要件が満たされ、例外処理コンポーネントの再試行機能の使用が有効になります。</span><span class="sxs-lookup"><span data-stu-id="483c3-112">Using the wrapper object meets the business requirement of using .NET remoting to communicate with the back-end order system while, at the same time, enabling use of the retry features of the exception handling components.</span></span>  
  
 <span data-ttu-id="483c3-113">いずれかのオーケストレーションで参照されているすべてのオブジェクトをシリアル化できる必要がありますので、 **OrderHandlerWrapper**もシリアル化することができます。</span><span class="sxs-lookup"><span data-stu-id="483c3-113">Because one must be able to serialize every object referenced in an orchestration, the **OrderHandlerWrapper** can also be serialized.</span></span> <span data-ttu-id="483c3-114">使用して、 **OrderHandlerWrapper**オーケストレーションからシリアル化コードを分離します。</span><span class="sxs-lookup"><span data-stu-id="483c3-114">Using the **OrderHandlerWrapper** isolates the serialization code from the orchestrations.</span></span>  
  
 <span data-ttu-id="483c3-115">Se がわかる場合は、コードを見るを**OrderHandlerWrapper**オブジェクトが明示的に実装する、 **ISerializable**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="483c3-115">If you look at the code, you'll se that the **OrderHandlerWrapper** object explicitly implements the **ISerializable** interface.</span></span> <span data-ttu-id="483c3-116">このオブジェクトは既定以外のコンストラクタを使用するので、自身のシリアル化を処理する必要があるのです。</span><span class="sxs-lookup"><span data-stu-id="483c3-116">The object must handle its own serialization because it uses a non-default constructor.</span></span>  
  
 <span data-ttu-id="483c3-117">バックエンド システムと通信するために .NET リモート処理を使用することは、メッセージングを使用するよりも効率的で、</span><span class="sxs-lookup"><span data-stu-id="483c3-117">Using .NET remoting to communicate with the backend system is more efficient than using messaging.</span></span> <span data-ttu-id="483c3-118">単純なメッセージング ソリューションを使用した場合よりも、オーケストレーションがバックエンド システムに緊密にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="483c3-118">On the other hand, it binds the orchestrations more tightly to the back-end system than a pure messaging solution might.</span></span> <span data-ttu-id="483c3-119">また、.NET リモート処理を使用することにより、BizTalk Server の組み込みの機能が再試行要求に対して使用される状況を回避できます。</span><span class="sxs-lookup"><span data-stu-id="483c3-119">Using .NET remoting also prevents the solution from taking advantage of the built-in BizTalk Server features for retrying requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="483c3-120">参照</span><span class="sxs-lookup"><span data-stu-id="483c3-120">See Also</span></span>  
 <span data-ttu-id="483c3-121">[ビジネス プロセス管理ソリューションの実装の要点](../core/implementation-highlights-of-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="483c3-121">[Implementation Highlights of the Business Process Management Solution](../core/implementation-highlights-of-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="483c3-122">プロセス マネージャのロジック</span><span class="sxs-lookup"><span data-stu-id="483c3-122">Process Manager Logic</span></span>](../core/process-manager-logic.md)