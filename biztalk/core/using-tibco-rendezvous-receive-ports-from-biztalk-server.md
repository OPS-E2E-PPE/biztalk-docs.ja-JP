---
title: 受信スキーマと TIBCO Rendezvous アダプターを使用したイベントの処理 |Microsoft Docs
description: TIBCO Rendezvous のスキーマ、受信側と biztalk TIBCO Rendezvous の BizTalk アダプターを使用してイベント処理の操作します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26cb20f9-4d26-48f6-a5e9-a51348a56538
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d459ac2019ccf20edfd718815c7ee789a9089be5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302387"
---
# <a name="using-tibco-rendezvous-receive-ports-from-biztalk-server"></a><span data-ttu-id="2a395-103">使用して TIBCO Rendezvous から BizTalk Server のポートの受信</span><span class="sxs-lookup"><span data-stu-id="2a395-103">Using TIBCO Rendezvous Receive Ports from BizTalk Server</span></span>

## <a name="overview"></a><span data-ttu-id="2a395-104">概要</span><span class="sxs-lookup"><span data-stu-id="2a395-104">Overview</span></span>
<span data-ttu-id="2a395-105">受信ポートを使用するにはスキーマを提供できる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信メッセージ。</span><span class="sxs-lookup"><span data-stu-id="2a395-105">To use a receive port, you can provide a schema to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for the incoming messages.</span></span> <span data-ttu-id="2a395-106">受信ポートは、特定のサブジェクト名のセットをリッスンするように構成されます。</span><span class="sxs-lookup"><span data-stu-id="2a395-106">A receive port is configured to listen for a particular set of subject names.</span></span> <span data-ttu-id="2a395-107">省略可能なワイルドカード文字を含む複数のサブジェクト名に一致するのにサブジェクト名を使用します。</span><span class="sxs-lookup"><span data-stu-id="2a395-107">It uses a subject name with optional wildcard characters to match multiple subject names.</span></span> <span data-ttu-id="2a395-108">別のポート操作を定義する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のオーケストレーションを指定した文字列に一致する可能性のある各サブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2a395-108">You define different port operations in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration for each possible subject that matches the given string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a395-109">アダプターは、オーケストレーションとメッセージング シナリオの両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="2a395-109">The adapter supports both orchestration and messaging scenarios.</span></span>  
  
## <a name="define-schemas"></a><span data-ttu-id="2a395-110">スキーマを定義します。</span><span class="sxs-lookup"><span data-stu-id="2a395-110">Define schemas</span></span>  
 <span data-ttu-id="2a395-111">たとえば、ポートが、サブジェクト名をリッスンするように構成されている場合**STOCK します。市場です。インデックス。 >** ('**>**' が右側に何を意味するワイルドカード文字)、などのサブジェクト名の操作を定義する有効なことが**STOCK します。市場です。インデックスです。NYSE します。SP500**、**素材です。市場です。インデックスです。TSX.TSX60**など。</span><span class="sxs-lookup"><span data-stu-id="2a395-111">For example, if the port is configured to listen to the subject name, **STOCK.MARKET.INDICES.>** ('**>**' is a wildcard character that means anything else to the right), it would be valid to define operations for subject names such as **STOCK.MARKET.INDICES.NYSE.SP500**, **STOCK.MARKET.INDICES.TSX.TSX60**, and so on.</span></span> <span data-ttu-id="2a395-112">アダプターにより生成されるメッセージで説明されている方法を使用した[Data Type Mapping for TIBCO rendezvous 受信ハンドラー](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)、ルート要素名とリッスンに基づく名前空間を生成しますサブジェクト名と受信したメッセージ。それぞれのサブジェクト名します。</span><span class="sxs-lookup"><span data-stu-id="2a395-112">The adapter generates messages using the strategy described in [Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md), and generates the root element name and namespaces based on the listen subject name and received message subject names respectively.</span></span>  
  
 <span data-ttu-id="2a395-113">前の例では、アダプターには、SP500 イベントは、次のようなメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="2a395-113">In the previous example, the adapter generates a message that looks like the following for the SP500 event:</span></span>  
  
```  
<ns:STOCK.MARKET.INDICES.NYSE.SP500 xmlns:ns='   
http://schemas.microsoft.com/TibcoRendezvous/Types/  
STOCK.MARKET.INDICES.NYSE.GTWILDCARD'  
xmlns:tibrv=' http://schemas.microsoft.com/TibcoRendezvous/Types' … >  
<message body>  
</ns: STOCK.MARKET.INDICES.NYSE.SP500>  
  
```  
  
 <span data-ttu-id="2a395-114">同じ規則を使用するスキーマを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a395-114">You must define a schema that uses the same conventions.</span></span> <span data-ttu-id="2a395-115">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2a395-115">For example:</span></span>  
  
```  
<xsd:schema  
targetNamespace='   
  
http://schemas.microsoft.com/TibcoRendezvous/Types/STOCK.MARKET.INDICES.N  
YSE.GTWILDCARD'  
xmlns:xsd=' http://www.w3.org/2001/XMLSchema'  
xmlns:tibrv=' http://schemas.microsoft.com/TibcoRendezvous/Types'>  
xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
<xsd:element name='STOCK.MARKET.INDICES.NYSE.SP500'>  
  
 <xs:annotation>  
   <xs:appinfo>  
     <b:recordInfo rootTypeName="STOCK_MARKET_INDICES_NYSE_SP500" />  
   </xs:appinfo>  
  
 </xs:annotation>  
<xsd:complexType>  
<SP500 message definitions goes here>  
</xsd:complexType>  
<xsd:element name='STOCK.MARKET.INDICES.TSX.TSX60'>  
  
 <xs:annotation>  
   <xs:appinfo>  
     <b:recordInfo rootTypeName="STOCK_MARKET_INDICES_TSX_TSX60" />  
   </xs:appinfo>  
  
 </xs:annotation>  
<xsd:complexType>  
<TSX60 message definitions goes here>  
</xsd:complexType>  
  
```  
  
 <span data-ttu-id="2a395-116">使用に注意してください、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **recordInfo/rootTypeName**注釈。</span><span class="sxs-lookup"><span data-stu-id="2a395-116">Note the use of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**recordInfo/rootTypeName** annotation.</span></span> <span data-ttu-id="2a395-117">これに指示する、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]/BizTalk integration のドットを含む名前ではなく、生成された .NET Framework 型の名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="2a395-117">This is to instruct the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]/BizTalk integration to use that name for the generated .NET Framework types, instead of the name that contains dots.</span></span> <span data-ttu-id="2a395-118">何も指定することができます。</span><span class="sxs-lookup"><span data-stu-id="2a395-118">You can specify anything.</span></span> <span data-ttu-id="2a395-119">例では、ドットはアンダー スコアに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="2a395-119">In the examples, the dots are replaced with underscores.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a395-120">ドットで生成される無効な名前が発生する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]開発ツール。</span><span class="sxs-lookup"><span data-stu-id="2a395-120">The dots cause invalid names to be generated by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] development tools.</span></span>  

## <a name="event-processing"></a><span data-ttu-id="2a395-121">イベント処理</span><span class="sxs-lookup"><span data-stu-id="2a395-121">Event processing</span></span>
<span data-ttu-id="2a395-122">Microsoft BizTalk Adapter for TIBCO Rendezvous は、複数のスレッドのキューからイベントをディスパッチします。</span><span class="sxs-lookup"><span data-stu-id="2a395-122">Microsoft BizTalk Adapter for TIBCO Rendezvous dispatches events from a queue on multiple threads.</span></span> <span data-ttu-id="2a395-123">BizTalk Server の受信場所が 1 つの TIBCO Rendezvous イベント キューとディスパッチャー スレッドのプールに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="2a395-123">A BizTalk Server receive location is associated with one TIBCO Rendezvous event queue, and its pool of dispatcher threads.</span></span>  
  
### <a name="memory-use-and-errors"></a><span data-ttu-id="2a395-124">メモリの使用とエラー</span><span class="sxs-lookup"><span data-stu-id="2a395-124">Memory Use and Errors</span></span>  
 <span data-ttu-id="2a395-125">イベントの処理中、アダプターは使用されるリソースを監視します。</span><span class="sxs-lookup"><span data-stu-id="2a395-125">While processing events, the adapter keeps an eye on used resources.</span></span> <span data-ttu-id="2a395-126">メモリの使用量が上限 Watermark を超えると、アダプターはメモリ使用量が下限 Watermark に達するまでイベントのディスパッチを停止します。</span><span class="sxs-lookup"><span data-stu-id="2a395-126">If memory use goes above the high-watermark, the adapter stops dispatching events until it reaches the low-watermark memory consumption.</span></span> <span data-ttu-id="2a395-127">これにより TIBCO Rendezvous メッセージが未証明メッセージとして失われる場合があることに注意してください (TIBCO RV コンシューマーは 60 秒経過したらメッセージをキューから削除します)。</span><span class="sxs-lookup"><span data-stu-id="2a395-127">Note that this might result in TIBCO Rendezvous messages being missed for non certified messages (a TIBCO RV consumer has 60 seconds to remove messages from a queue).</span></span> <span data-ttu-id="2a395-128">このデータ損失はエラーとして報告されます。</span><span class="sxs-lookup"><span data-stu-id="2a395-128">This data loss is reported as an error.</span></span> <span data-ttu-id="2a395-129">アダプターが TIBCO Rendezvous のシステム通知 NO_MEMORY メッセージを受け取ったら、メッセージは既に失われています。</span><span class="sxs-lookup"><span data-stu-id="2a395-129">If the adapter receives a TIBCO Rendezvous system advisory NO_MEMORY message, messages have already been lost.</span></span>  
  
 <span data-ttu-id="2a395-130">BizTalk Adapter for TIBCO Rendezvous は状態を保持しており、状態に応じて異なるタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="2a395-130">BizTalk Adapter for TIBCO Rendezvous maintains a state, and it executes tasks differently based on that state.</span></span> <span data-ttu-id="2a395-131">BizTalk メッセージ エンジンがエラーを報告し、アダプターが証明されたリスナーとして構成されている場合、アダプターは TIBCO Rendezvous にエラーを報告してメッセージを再送信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2a395-131">If the BizTalk Message Engine reports an error, and the adapter is configured to be a certified listener, it reports the error to TIBCO Rendezvous so that it can resubmit the message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a395-132">参照</span><span class="sxs-lookup"><span data-stu-id="2a395-132">See Also</span></span>  
 <span data-ttu-id="2a395-133">[TIBCO Rendezvous の概念](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="2a395-133">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 <span data-ttu-id="2a395-134">[データ型マッピングの TIBCO Rendezvous 受信ハンドラー](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="2a395-134">[Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="2a395-135">TIBCO Rendezvous 受信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="2a395-135">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)