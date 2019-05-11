---
title: Order Handler オブジェクトを使用してバックエンド システムと通信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IOrderHandler interface
- process management solution tutorial, IOrderHandler interface
ms.assetid: b9fe4120-bf2a-4d15-a34b-6b98f026b984
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 919013bbae989d588033437be54ce705179a44f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303005"
---
# <a name="using-the-order-handler-object-to-communicate-with-backend-systems"></a><span data-ttu-id="942da-102">Order Handler オブジェクトを使用してバックエンド システムと通信</span><span class="sxs-lookup"><span data-stu-id="942da-102">Using the Order Handler Object to Communicate with Backend Systems</span></span>
<span data-ttu-id="942da-103">ビジネス プロセス管理ソリューションがある cable provisioning system 最終的な注文を受信する、従来のバックエンド注文システムと通信でした多くの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="942da-103">There are many ways in which the business process management solution could communicate with the legacy back-end order system, the cable provisioning system that receives the final orders.</span></span> <span data-ttu-id="942da-104">ソリューションについては、Microsoft .NET リモート処理機能を使用する[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]provisioning system と通信します。</span><span class="sxs-lookup"><span data-stu-id="942da-104">The solution uses the .NET remoting facilities found in Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] to communicate with the provisioning system.</span></span>  
  
 <span data-ttu-id="942da-105">ソリューションでは、インターフェイスを使用して、バックエンド システムに対するアクセス オブジェクトを定義する一般的な手法を使用します。</span><span class="sxs-lookup"><span data-stu-id="942da-105">The solution uses a common technique of using an interface to define the access object to the back-end system.</span></span> <span data-ttu-id="942da-106">アセンブリは、別のアセンブリでは、クライアントで、インターフェイスを配置することで、コンパイルされたアセンブリにアクセスすることがなくリモート オブジェクトへのアクセスができます。</span><span class="sxs-lookup"><span data-stu-id="942da-106">By putting the interface in a separate assembly the client assembly can have access to the remote object without having to have access to the compiled assembly.</span></span>  
  
 <span data-ttu-id="942da-107">**IOrderHandler**インターフェイスは、バックエンド注文システムと通信するメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="942da-107">The **IOrderHandler** interface defines the methods to communicate with the backend order system.</span></span> <span data-ttu-id="942da-108">インターフェイスには、分析、アクティブ化、取り消し中、および注文を完了するためのメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="942da-108">The interface includes methods for analyzing, activating, canceling, and completing orders.</span></span> <span data-ttu-id="942da-109">サービスの種類、注文がキャンセルされた場合に必要なメソッドを識別するためのメソッドも提供します。</span><span class="sxs-lookup"><span data-stu-id="942da-109">It also provides a method for identifying the service type, a method needed when an order is canceled.</span></span>  
  
 <span data-ttu-id="942da-110">**CableOrder1**、 **CableOrder2**、サテライト オーケストレーションを使用して、 **OrderHandlerWrapper**を実装するオブジェクト**IOrderHandler**.</span><span class="sxs-lookup"><span data-stu-id="942da-110">The **CableOrder1**, **CableOrder2**, and satellite orchestrations use the **OrderHandlerWrapper** object that implements **IOrderHandler**.</span></span> <span data-ttu-id="942da-111">**OrderHandlerWrapper**オブジェクト、さらのリモート インスタンスを呼び出す、 **OrderHandler**オブジェクトによって提供される、 **CableProvisioningSystemServer**実行可能ファイルです。</span><span class="sxs-lookup"><span data-stu-id="942da-111">The **OrderHandlerWrapper** object, in turn, invokes a remote instance of an **OrderHandler** object provided by the **CableProvisioningSystemServer** executable.</span></span> <span data-ttu-id="942da-112">使用した .NET リモート処理通信中に、バックエンド注文システムを同時に、例外処理コンポーネントの再試行機能の使用を有効にするのビジネス要件を満たしている、ラッパー オブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="942da-112">Using the wrapper object meets the business requirement of using .NET remoting to communicate with the back-end order system while, at the same time, enabling use of the retry features of the exception handling components.</span></span>  
  
 <span data-ttu-id="942da-113">1 つ、オーケストレーションで参照されているすべてのオブジェクトをシリアル化できる必要がありますので、 **OrderHandlerWrapper**もシリアル化することができます。</span><span class="sxs-lookup"><span data-stu-id="942da-113">Because one must be able to serialize every object referenced in an orchestration, the **OrderHandlerWrapper** can also be serialized.</span></span> <span data-ttu-id="942da-114">使用して、 **OrderHandlerWrapper**はシリアル化コードをオーケストレーションから分離します。</span><span class="sxs-lookup"><span data-stu-id="942da-114">Using the **OrderHandlerWrapper** isolates the serialization code from the orchestrations.</span></span>  
  
 <span data-ttu-id="942da-115">場合は、コードを見ることがわかりますが、 **OrderHandlerWrapper**オブジェクトを明示的に実装して、 **ISerializable**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="942da-115">If you look at the code, you'll se that the **OrderHandlerWrapper** object explicitly implements the **ISerializable** interface.</span></span> <span data-ttu-id="942da-116">オブジェクトは、既定以外のコンス トラクターを使用しているために、独自のシリアル化を処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="942da-116">The object must handle its own serialization because it uses a non-default constructor.</span></span>  
  
 <span data-ttu-id="942da-117">.NET リモート処理を使用して、バックエンド システムとの通信には、メッセージングを使用するよりも効率的です。</span><span class="sxs-lookup"><span data-stu-id="942da-117">Using .NET remoting to communicate with the backend system is more efficient than using messaging.</span></span> <span data-ttu-id="942da-118">一方で、オーケストレーションのバインドより緊密にバックエンド システムによりも、純粋なメッセージング ソリューションの可能性があります。</span><span class="sxs-lookup"><span data-stu-id="942da-118">On the other hand, it binds the orchestrations more tightly to the back-end system than a pure messaging solution might.</span></span> <span data-ttu-id="942da-119">.NET リモート処理を使用しても防止ソリューション再試行要求に対して組み込みの BizTalk Server の機能を活用します。</span><span class="sxs-lookup"><span data-stu-id="942da-119">Using .NET remoting also prevents the solution from taking advantage of the built-in BizTalk Server features for retrying requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="942da-120">参照</span><span class="sxs-lookup"><span data-stu-id="942da-120">See Also</span></span>  
 <span data-ttu-id="942da-121">[ビジネス プロセス管理ソリューションの実装の要点](../core/implementation-highlights-of-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="942da-121">[Implementation Highlights of the Business Process Management Solution](../core/implementation-highlights-of-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="942da-122">プロセス マネージャーのロジック</span><span class="sxs-lookup"><span data-stu-id="942da-122">Process Manager Logic</span></span>](../core/process-manager-logic.md)