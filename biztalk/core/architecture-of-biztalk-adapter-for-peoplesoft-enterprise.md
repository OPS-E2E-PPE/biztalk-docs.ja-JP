---
title: "BizTalk Adapter for PeopleSoft Enterprise のアーキテクチャ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validating, XML messages
- architecture
- XML, messages
- XML, validating
ms.assetid: f246e974-a082-430c-ad15-23a5e597738b
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 377e49af3a20302b92a4214959b534c9d0949a93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-of-biztalk-adapter-for-peoplesoft-enterprise"></a><span data-ttu-id="95a73-102">BizTalk Adapter for PeopleSoft Enterprise のアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="95a73-102">Architecture of BizTalk Adapter for PeopleSoft Enterprise</span></span>
<span data-ttu-id="95a73-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise は、基本的な操作の実行中に BizTalk Server から XML メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="95a73-103">During the basic operation of Microsoft BizTalk Adapter for PeopleSoft Enterprise, the adapter receives an XML message from BizTalk Server.</span></span> <span data-ttu-id="95a73-104">この XML メッセージは SOAP エンベロープに埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="95a73-104">It encloses the XML message in a SOAP envelope.</span></span> <span data-ttu-id="95a73-105">BizTalk Adapter for PeopleSoft Enterprise は、SOAP 要求をサーバーに転送します。</span><span class="sxs-lookup"><span data-stu-id="95a73-105">BizTalk Adapter for PeopleSoft Enterprise forwards the SOAP requests to the server.</span></span> <span data-ttu-id="95a73-106">このアダプターは、Jolt トランザクション プロトコルによって PeopleSoft システムに接続する PeopleSoft psjoa クラスを使用して、PeopleSoft システムと通信します。</span><span class="sxs-lookup"><span data-stu-id="95a73-106">The adapter communicates with the PeopleSoft system using the PeopleSoft psjoa classes, which connect to the PeopleSoft system through Jolt Transaction Protocol.</span></span> <span data-ttu-id="95a73-107">PeopleSoft システムは、要求を受信して、ビジネス ロジックを実行します。</span><span class="sxs-lookup"><span data-stu-id="95a73-107">The PeopleSoft system receives the request and executes the business logic.</span></span> <span data-ttu-id="95a73-108">応答は、同様のプロセスによって戻されます。</span><span class="sxs-lookup"><span data-stu-id="95a73-108">The reply is sent back through a similar process.</span></span>  
  
 ![](../core/media/psadapter-01-architecture.gif "PSAdapter_01_Architecture")  
<span data-ttu-id="95a73-109">アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="95a73-109">Adapter Architecture</span></span>  
  
## <a name="peoplesoft-component-interface-methods"></a><span data-ttu-id="95a73-110">PeopleSoft コンポーネント インターフェイス メソッド</span><span class="sxs-lookup"><span data-stu-id="95a73-110">PeopleSoft Component Interface Methods</span></span>  
 <span data-ttu-id="95a73-111">PeopleSoft コンポーネント インターフェイスに提供されている基本 API は、本質的に低レベルです。</span><span class="sxs-lookup"><span data-stu-id="95a73-111">The basic APIs that are provided by the PeopleSoft component interface are low-level in nature.</span></span> <span data-ttu-id="95a73-112">クライアントは、これらの API について複数の呼び出しを要求します。</span><span class="sxs-lookup"><span data-stu-id="95a73-112">The client requires multiple invocations of these APIs.</span></span> <span data-ttu-id="95a73-113">たとえば、コンポーネント インターフェイスのインスタンスのプロパティを取得する場合、クライアントは低レベルの Get メソッドを呼び出した後、1 つ以上の呼び出しによってキーの値を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95a73-113">For example, to obtain the property of an instance of a component interface, the client needs one or more calls to set the key values followed by a low-level Get method call.</span></span> <span data-ttu-id="95a73-114">さらに、プロパティを取得するには、複数の呼び出しを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95a73-114">It must then send multiple calls to get the properties.</span></span> <span data-ttu-id="95a73-115">BizTalk Adapter for PeopleSoft Enterprise を使用すると、標準メソッド (Get、Create、Find、Update) の新しいセットが提供されるので、クライアントは 1 回の呼び出しを行うだけで同じ結果を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="95a73-115">With BizTalk Adapter for PeopleSoft Enterprise, a new set of standard methods (Get, Create, Find, and Update) are provided in such a way that the client is required to make a single call to accomplish the same result.</span></span> <span data-ttu-id="95a73-116">つまり、BizTalk Adapter for PeopleSoft Enterprise がクライアントの代わりに複数の呼び出しを実行することになります。</span><span class="sxs-lookup"><span data-stu-id="95a73-116">You do this by having BizTalk Adapter for PeopleSoft Enterprise perform multiple calls on behalf of the client.</span></span> <span data-ttu-id="95a73-117">メソッドの詳細については、次を参照してください。[付録 a: コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)です。</span><span class="sxs-lookup"><span data-stu-id="95a73-117">For more information about the methods, see [Appendix A: Component Interface Methods](../core/appendix-a-component-interface-methods.md).</span></span>  
  
 <span data-ttu-id="95a73-118">PeopleSoft のスキーマを作成するには、BizTalk Adapter for PeopleSoft Enterprise で PeopleSoft コンポーネント インターフェイスの定義またはメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="95a73-118">To create a schema for PeopleSoft, BizTalk Adapter for PeopleSoft Enterprise retrieves the PeopleSoft component interface definitions or metadata.</span></span>  
  
 <span data-ttu-id="95a73-119">BizTalk Adapter for PeopleSoft Enterprise の送信機能はコンポーネント インターフェイスに基づいているので、PeopleSoft Integration Broker は不要です。</span><span class="sxs-lookup"><span data-stu-id="95a73-119">BizTalk Adapter for PeopleSoft Enterprise is based on component interfaces for the Send functionality and does not require the PeopleSoft Integration Broker.</span></span> <span data-ttu-id="95a73-120">コンポーネント インターフェイスは Web サービスとして公開され、BizTalk Server からアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="95a73-120">The component interfaces are exposed as Web services, which can be accessed from BizTalk Server.</span></span>  
  
### <a name="validation"></a><span data-ttu-id="95a73-121">検証</span><span class="sxs-lookup"><span data-stu-id="95a73-121">Validation</span></span>  
 <span data-ttu-id="95a73-122">BizTalk Adapter for PeopleSoft Enterprise では、BizTalk Server から XML メッセージを受信すると、2 レベルの検証が実行されます。</span><span class="sxs-lookup"><span data-stu-id="95a73-122">When BizTalk Adapter for PeopleSoft Enterprise receives an XML message from BizTalk Server, two levels of validation are performed:</span></span>  
  
-   <span data-ttu-id="95a73-123">XML メッセージが XML 仕様に関して有効である必要があります。</span><span class="sxs-lookup"><span data-stu-id="95a73-123">The XML message must be valid with regard to XML specification.</span></span>  
  
-   <span data-ttu-id="95a73-124">XML メッセージが、特定の Web サービスによる要求と一致している必要があります (たとえば、データ型などのインターフェイスの一致)。</span><span class="sxs-lookup"><span data-stu-id="95a73-124">The XML message must match what is required by the specific Web service (for example, interface matching such as data types).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95a73-125">ビジネス ロジックに関する検証は実行されません。これは PeopleSoft システムのドメインなので、BizTalk Adapter for PeopleSoft Enterprise に対して透過的だからです。</span><span class="sxs-lookup"><span data-stu-id="95a73-125">There is no validation with regard to business logic, which is the domain of the PeopleSoft system, and is transparent to BizTalk Adapter for PeopleSoft Enterprise.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95a73-126">参照</span><span class="sxs-lookup"><span data-stu-id="95a73-126">See Also</span></span>  
 <span data-ttu-id="95a73-127">[作業の開始](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="95a73-127">[Getting Started](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md) </span></span>  
 [<span data-ttu-id="95a73-128">計画とアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="95a73-128">Planning and Architecture</span></span>](../core/planning-and-architecture13.md)