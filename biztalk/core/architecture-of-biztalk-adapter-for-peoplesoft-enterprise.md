---
title: BizTalk Adapter for PeopleSoft Enterprise のアーキテクチャ |Microsoft ドキュメント
description: メッセージを受信する方法について説明します、メッセージがどのように検証すると、BizTalk Server で、PeopleSoft アダプターを使用する場合は、コンポーネント インターフェイス メソッドの情報を提供
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
ms.openlocfilehash: 3eb0f43dacdbd6036ef59fa3fe16102d4fe12379
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013697"
---
# <a name="peoplesoft-enterprise-adapter-architecture"></a><span data-ttu-id="0c450-103">PeopleSoft Enterprise アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="0c450-103">PeopleSoft Enterprise adapter architecture</span></span>
<span data-ttu-id="0c450-104">Microsoft BizTalk Adapter for PeopleSoft Enterprise は、基本的な操作の実行中に BizTalk Server から XML メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="0c450-104">During the basic operation of Microsoft BizTalk Adapter for PeopleSoft Enterprise, the adapter receives an XML message from BizTalk Server.</span></span> <span data-ttu-id="0c450-105">この XML メッセージは SOAP エンベロープに埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="0c450-105">It encloses the XML message in a SOAP envelope.</span></span> <span data-ttu-id="0c450-106">BizTalk Adapter for PeopleSoft Enterprise は、SOAP 要求をサーバーに転送します。</span><span class="sxs-lookup"><span data-stu-id="0c450-106">BizTalk Adapter for PeopleSoft Enterprise forwards the SOAP requests to the server.</span></span> <span data-ttu-id="0c450-107">このアダプターは、Jolt トランザクション プロトコルによって PeopleSoft システムに接続する PeopleSoft psjoa クラスを使用して、PeopleSoft システムと通信します。</span><span class="sxs-lookup"><span data-stu-id="0c450-107">The adapter communicates with the PeopleSoft system using the PeopleSoft psjoa classes, which connect to the PeopleSoft system through Jolt Transaction Protocol.</span></span> <span data-ttu-id="0c450-108">PeopleSoft システムは、要求を受信して、ビジネス ロジックを実行します。</span><span class="sxs-lookup"><span data-stu-id="0c450-108">The PeopleSoft system receives the request and executes the business logic.</span></span> <span data-ttu-id="0c450-109">応答は、同様のプロセスによって戻されます。</span><span class="sxs-lookup"><span data-stu-id="0c450-109">The reply is sent back through a similar process.</span></span>  
  
 ![](../core/media/psadapter-01-architecture.gif "PSAdapter_01_Architecture")  

  
## <a name="component-interface-methods"></a><span data-ttu-id="0c450-110">コンポーネント インターフェイス メソッド</span><span class="sxs-lookup"><span data-stu-id="0c450-110">Component Interface Methods</span></span>  
 <span data-ttu-id="0c450-111">PeopleSoft コンポーネント インターフェイスに提供されている基本 API は、本質的に低レベルです。</span><span class="sxs-lookup"><span data-stu-id="0c450-111">The basic APIs that are provided by the PeopleSoft component interface are low-level in nature.</span></span> <span data-ttu-id="0c450-112">クライアントは、これらの API について複数の呼び出しを要求します。</span><span class="sxs-lookup"><span data-stu-id="0c450-112">The client requires multiple invocations of these APIs.</span></span> <span data-ttu-id="0c450-113">たとえば、コンポーネント インターフェイスのインスタンスのプロパティを取得する場合、クライアントは低レベルの Get メソッドを呼び出した後、1 つ以上の呼び出しによってキーの値を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c450-113">For example, to obtain the property of an instance of a component interface, the client needs one or more calls to set the key values followed by a low-level Get method call.</span></span> <span data-ttu-id="0c450-114">さらに、プロパティを取得するには、複数の呼び出しを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c450-114">It must then send multiple calls to get the properties.</span></span> <span data-ttu-id="0c450-115">BizTalk Adapter for PeopleSoft Enterprise を使用すると、標準メソッド (Get、Create、Find、Update) の新しいセットが提供されるので、クライアントは 1 回の呼び出しを行うだけで同じ結果を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="0c450-115">With BizTalk Adapter for PeopleSoft Enterprise, a new set of standard methods (Get, Create, Find, and Update) are provided in such a way that the client is required to make a single call to accomplish the same result.</span></span> <span data-ttu-id="0c450-116">つまり、BizTalk Adapter for PeopleSoft Enterprise がクライアントの代わりに複数の呼び出しを実行することになります。</span><span class="sxs-lookup"><span data-stu-id="0c450-116">You do this by having BizTalk Adapter for PeopleSoft Enterprise perform multiple calls on behalf of the client.</span></span> <span data-ttu-id="0c450-117">メソッドの詳細については、次を参照してください。[付録 a: コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)です。</span><span class="sxs-lookup"><span data-stu-id="0c450-117">For more information about the methods, see [Appendix A: Component Interface Methods](../core/appendix-a-component-interface-methods.md).</span></span>  
  
 <span data-ttu-id="0c450-118">PeopleSoft のスキーマを作成するには、BizTalk Adapter for PeopleSoft Enterprise で PeopleSoft コンポーネント インターフェイスの定義またはメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="0c450-118">To create a schema for PeopleSoft, BizTalk Adapter for PeopleSoft Enterprise retrieves the PeopleSoft component interface definitions or metadata.</span></span>  
  
 <span data-ttu-id="0c450-119">BizTalk Adapter for PeopleSoft Enterprise の送信機能はコンポーネント インターフェイスに基づいているので、PeopleSoft Integration Broker は不要です。</span><span class="sxs-lookup"><span data-stu-id="0c450-119">BizTalk Adapter for PeopleSoft Enterprise is based on component interfaces for the Send functionality and does not require the PeopleSoft Integration Broker.</span></span> <span data-ttu-id="0c450-120">コンポーネント インターフェイスは Web サービスとして公開され、BizTalk Server からアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0c450-120">The component interfaces are exposed as Web services, which can be accessed from BizTalk Server.</span></span>  
  
### <a name="validation"></a><span data-ttu-id="0c450-121">検証</span><span class="sxs-lookup"><span data-stu-id="0c450-121">Validation</span></span>  
 <span data-ttu-id="0c450-122">BizTalk Adapter for PeopleSoft Enterprise では、BizTalk Server から XML メッセージを受信すると、2 レベルの検証が実行されます。</span><span class="sxs-lookup"><span data-stu-id="0c450-122">When BizTalk Adapter for PeopleSoft Enterprise receives an XML message from BizTalk Server, two levels of validation are performed:</span></span>  
  
-   <span data-ttu-id="0c450-123">XML メッセージが XML 仕様に関して有効である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c450-123">The XML message must be valid with regard to XML specification.</span></span>  
  
-   <span data-ttu-id="0c450-124">XML メッセージが、特定の Web サービスによる要求と一致している必要があります (たとえば、データ型などのインターフェイスの一致)。</span><span class="sxs-lookup"><span data-stu-id="0c450-124">The XML message must match what is required by the specific Web service (for example, interface matching such as data types).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c450-125">ビジネス ロジックに関する検証は実行されません。これは PeopleSoft システムのドメインなので、BizTalk Adapter for PeopleSoft Enterprise に対して透過的だからです。</span><span class="sxs-lookup"><span data-stu-id="0c450-125">There is no validation with regard to business logic, which is the domain of the PeopleSoft system, and is transparent to BizTalk Adapter for PeopleSoft Enterprise.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c450-126">参照</span><span class="sxs-lookup"><span data-stu-id="0c450-126">See Also</span></span>  
 [<span data-ttu-id="0c450-127">作業の開始</span><span class="sxs-lookup"><span data-stu-id="0c450-127">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md)   