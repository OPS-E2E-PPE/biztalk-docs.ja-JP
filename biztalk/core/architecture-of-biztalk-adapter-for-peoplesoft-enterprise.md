---
title: BizTalk Adapter for PeopleSoft Enterprise のアーキテクチャ |Microsoft Docs
description: メッセージを受信する方法について説明しますと、メッセージは、方法が検証され、BizTalk Server で、PeopleSoft アダプターを使用する場合は、コンポーネント インターフェイスのメソッドで情報を提供します
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f246e974-a082-430c-ad15-23a5e597738b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d65bfed5d76d4cb78a476ee56c863247a92a7ae
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528808"
---
# <a name="peoplesoft-enterprise-adapter-architecture"></a><span data-ttu-id="ce2ec-103">PeopleSoft Enterprise アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="ce2ec-103">PeopleSoft Enterprise adapter architecture</span></span>
<span data-ttu-id="ce2ec-104">基本の操作中に Microsoft BizTalk Adapter for PeopleSoft Enterprise、アダプターは BizTalk Server から XML メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="ce2ec-104">During the basic operation of Microsoft BizTalk Adapter for PeopleSoft Enterprise, the adapter receives an XML message from BizTalk Server.</span></span> <span data-ttu-id="ce2ec-105">SOAP エンベロープで XML メッセージを囲みます。</span><span class="sxs-lookup"><span data-stu-id="ce2ec-105">It encloses the XML message in a SOAP envelope.</span></span> <span data-ttu-id="ce2ec-106">BizTalk Adapter for PeopleSoft Enterprise では、サーバーに SOAP 要求を転送します。</span><span class="sxs-lookup"><span data-stu-id="ce2ec-106">BizTalk Adapter for PeopleSoft Enterprise forwards the SOAP requests to the server.</span></span> <span data-ttu-id="ce2ec-107">アダプターは、Jolt トランザクション プロトコルによって PeopleSoft システムに接続する PeopleSoft psjoa クラスを使用して PeopleSoft システムと通信します。</span><span class="sxs-lookup"><span data-stu-id="ce2ec-107">The adapter communicates with the PeopleSoft system using the PeopleSoft psjoa classes, which connect to the PeopleSoft system through Jolt Transaction Protocol.</span></span> <span data-ttu-id="ce2ec-108">PeopleSoft システムでは、要求を受信し、ビジネス ロジックを実行します。</span><span class="sxs-lookup"><span data-stu-id="ce2ec-108">The PeopleSoft system receives the request and executes the business logic.</span></span> <span data-ttu-id="ce2ec-109">同様のプロセスを遡って、応答が送信されます。</span><span class="sxs-lookup"><span data-stu-id="ce2ec-109">The reply is sent back through a similar process.</span></span>  
  
 <span data-ttu-id="ce2ec-110">![](../core/media/psadapter-01-architecture.gif "PSAdapter_01_Architecture")</span><span class="sxs-lookup"><span data-stu-id="ce2ec-110">![](../core/media/psadapter-01-architecture.gif "PSAdapter_01_Architecture")</span></span>  

  
## <a name="component-interface-methods"></a><span data-ttu-id="ce2ec-111">コンポーネント インターフェイス メソッド</span><span class="sxs-lookup"><span data-stu-id="ce2ec-111">Component Interface Methods</span></span>  
 <span data-ttu-id="ce2ec-112">PeopleSoft コンポーネント インターフェイスで提供される基本的な Api は、本質的に低レベルです。</span><span class="sxs-lookup"><span data-stu-id="ce2ec-112">The basic APIs that are provided by the PeopleSoft component interface are low-level in nature.</span></span> <span data-ttu-id="ce2ec-113">クライアントでは、これらの Api の複数の呼び出しが必要です。</span><span class="sxs-lookup"><span data-stu-id="ce2ec-113">The client requires multiple invocations of these APIs.</span></span> <span data-ttu-id="ce2ec-114">たとえば、コンポーネント インターフェイスのインスタンスのプロパティを取得する、クライアントでは、低レベルの Get メソッドの呼び出し後にキー値を設定する 1 つまたは複数の呼び出しに必要です。</span><span class="sxs-lookup"><span data-stu-id="ce2ec-114">For example, to obtain the property of an instance of a component interface, the client needs one or more calls to set the key values followed by a low-level Get method call.</span></span> <span data-ttu-id="ce2ec-115">プロパティを取得する複数の呼び出しに送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce2ec-115">It must then send multiple calls to get the properties.</span></span> <span data-ttu-id="ce2ec-116">BizTalk Adapter for PeopleSoft Enterprise では、標準的なメソッド (Get、作成、検索、および更新) の新しいセットは、クライアントが、同じ結果を 1 回の呼び出しに必要であるような方法で提供されます。</span><span class="sxs-lookup"><span data-stu-id="ce2ec-116">With BizTalk Adapter for PeopleSoft Enterprise, a new set of standard methods (Get, Create, Find, and Update) are provided in such a way that the client is required to make a single call to accomplish the same result.</span></span> <span data-ttu-id="ce2ec-117">これは BizTalk Adapter for PeopleSoft Enterprise がクライアントの代わりに複数の呼び出しを実行することで行います。</span><span class="sxs-lookup"><span data-stu-id="ce2ec-117">You do this by having BizTalk Adapter for PeopleSoft Enterprise perform multiple calls on behalf of the client.</span></span> <span data-ttu-id="ce2ec-118">メソッドの詳細については、次を参照してください[付録 a:。コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)します。</span><span class="sxs-lookup"><span data-stu-id="ce2ec-118">For more information about the methods, see [Appendix A: Component Interface Methods](../core/appendix-a-component-interface-methods.md).</span></span>  
  
 <span data-ttu-id="ce2ec-119">PeopleSoft のスキーマを作成するには、BizTalk Adapter for PeopleSoft Enterprise は PeopleSoft コンポーネント インターフェイスの定義またはメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="ce2ec-119">To create a schema for PeopleSoft, BizTalk Adapter for PeopleSoft Enterprise retrieves the PeopleSoft component interface definitions or metadata.</span></span>  
  
 <span data-ttu-id="ce2ec-120">BizTalk Adapter for PeopleSoft Enterprise では、送信機能はコンポーネント インターフェイスに基づいており、PeopleSoft Integration Broker は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ce2ec-120">BizTalk Adapter for PeopleSoft Enterprise is based on component interfaces for the Send functionality and does not require the PeopleSoft Integration Broker.</span></span> <span data-ttu-id="ce2ec-121">コンポーネントのインターフェイスは、BizTalk Server からアクセスできるは、Web サービスとして公開されます。</span><span class="sxs-lookup"><span data-stu-id="ce2ec-121">The component interfaces are exposed as Web services, which can be accessed from BizTalk Server.</span></span>  
  
### <a name="validation"></a><span data-ttu-id="ce2ec-122">検証</span><span class="sxs-lookup"><span data-stu-id="ce2ec-122">Validation</span></span>  
 <span data-ttu-id="ce2ec-123">BizTalk Adapter for PeopleSoft Enterprise では、BizTalk Server から XML メッセージを受信、2 つのレベルの検証が実行されます。</span><span class="sxs-lookup"><span data-stu-id="ce2ec-123">When BizTalk Adapter for PeopleSoft Enterprise receives an XML message from BizTalk Server, two levels of validation are performed:</span></span>  
  
-   <span data-ttu-id="ce2ec-124">XML メッセージは、XML 仕様に関して有効である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce2ec-124">The XML message must be valid with regard to XML specification.</span></span>  
  
-   <span data-ttu-id="ce2ec-125">XML メッセージでは、特定の Web サービス (たとえば、インターフェイスなどのデータ型の一致) で必要なものと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce2ec-125">The XML message must match what is required by the specific Web service (for example, interface matching such as data types).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce2ec-126">PeopleSoft システムのドメインと BizTalk Adapter for PeopleSoft Enterprise に対して透過的ですが、ビジネス ロジックに関する検証は行われません。</span><span class="sxs-lookup"><span data-stu-id="ce2ec-126">There is no validation with regard to business logic, which is the domain of the PeopleSoft system, and is transparent to BizTalk Adapter for PeopleSoft Enterprise.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce2ec-127">参照</span><span class="sxs-lookup"><span data-stu-id="ce2ec-127">See Also</span></span>  
 [<span data-ttu-id="ce2ec-128">作業の開始</span><span class="sxs-lookup"><span data-stu-id="ce2ec-128">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md)   