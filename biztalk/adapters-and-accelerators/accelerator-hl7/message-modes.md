---
title: "モードをメッセージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message modes, about message modes
- messages, message modes
- message modes, HL7 messages
ms.assetid: 2d832b67-6f0e-45e1-95ac-cb80b74a7831
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b09a610d000ae6beaef75b1ed0144d1597d517b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-modes"></a><span data-ttu-id="b0079-102">メッセージ モード</span><span class="sxs-lookup"><span data-stu-id="b0079-102">Message Modes</span></span>
<span data-ttu-id="b0079-103">HL7 のすべてのメッセージの基になる 2 つの基本的な概念があります。</span><span class="sxs-lookup"><span data-stu-id="b0079-103">There are two basic concepts that underlie all HL7 messages.</span></span> <span data-ttu-id="b0079-104">これらの概念はアドレス データを交換する独立したシステムの相互作用し、分散医療システム内で時間の経過と共に相互運用性の要件をサポートする構造を提供する、さまざまな方法です。</span><span class="sxs-lookup"><span data-stu-id="b0079-104">These concepts address different ways in which independent systems that exchange data can interact, and provide a structure that supports the requirements of interoperability over time within a distributed health care system.</span></span> <span data-ttu-id="b0079-105">以下に示す概念は、HL7 デザインの背後にある、基になるテーマを定義します。</span><span class="sxs-lookup"><span data-stu-id="b0079-105">The concepts listed below define the underlying themes behind the HL7 design:</span></span>  
  
-   <span data-ttu-id="b0079-106">**メッセージ モード**です。</span><span class="sxs-lookup"><span data-stu-id="b0079-106">**Messaging Mode**.</span></span> <span data-ttu-id="b0079-107">情報交換用の 3 つの基本的な目的の認識: 要求の情報 (interrogative) に情報を (宣言) をブロードキャストして、システムのアクションを実行 (強制) を要求します。</span><span class="sxs-lookup"><span data-stu-id="b0079-107">The recognition of three fundamental purposes for information exchange: to broadcast information (declarative), to request information (interrogative), and to request that the system take an action (imperative).</span></span> <span data-ttu-id="b0079-108">それぞれの目的は、その特定の要件とメッセージ フローのパターン。</span><span class="sxs-lookup"><span data-stu-id="b0079-108">Each of these purposes has its particular requirements and pattern of message flow.</span></span>  
  
-   <span data-ttu-id="b0079-109">**受信確認モード**です。</span><span class="sxs-lookup"><span data-stu-id="b0079-109">**Acknowledgment Mode**.</span></span> <span data-ttu-id="b0079-110">緊密にし、疎をサポートするために必要では、メッセージングのスタイルが結合されています。</span><span class="sxs-lookup"><span data-stu-id="b0079-110">The need to support tightly and loosely coupled styles of messaging.</span></span> <span data-ttu-id="b0079-111">HL7 の受信確認応答モードでは、受信側からの応答を必要とするか、メッセージ配信を保証するために、基になるネットワークを有効にする、送信元アプリケーションが有効にします。</span><span class="sxs-lookup"><span data-stu-id="b0079-111">The acknowledgment modes for HL7 enable a sending application either to require a response from the receiver, or to enable the underlying network to guarantee message delivery.</span></span>  
  
-   <span data-ttu-id="b0079-112">**ローカリゼーション**です。</span><span class="sxs-lookup"><span data-stu-id="b0079-112">**Localization**.</span></span> <span data-ttu-id="b0079-113">メッセージの仕様にサイト固有の情報を紹介するエンティティを許可することで、ローカルの特定の要件をサポートするために必要です。</span><span class="sxs-lookup"><span data-stu-id="b0079-113">The need to support specific local requirements by allowing entities to introduce site-specific material into message specifications.</span></span>  
  
-   <span data-ttu-id="b0079-114">**進化**です。</span><span class="sxs-lookup"><span data-stu-id="b0079-114">**Evolution**.</span></span> <span data-ttu-id="b0079-115">標準のバージョン間の相互運用性を有効にすると、多くのインターフェイスと多くのアプリケーションのサイトをサポートするために必要です。</span><span class="sxs-lookup"><span data-stu-id="b0079-115">The need to support sites with many interfaces and many applications by enabling interoperability between standard versions.</span></span> <span data-ttu-id="b0079-116">これにより、すべてのインターフェイスの同時アップグレードを必要とするのではなく、段階インターフェイスのアップグレードにエンティティです。</span><span class="sxs-lookup"><span data-stu-id="b0079-116">This enables entities to stage interface upgrades, as opposed to requiring simultaneous upgrades of all interfaces.</span></span>  
  
 <span data-ttu-id="b0079-117">次の関数の[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 上記の要件をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b0079-117">The following functions of [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) support the above requirements:</span></span>  
  
-   <span data-ttu-id="b0079-118">HL7 受信確認モード。</span><span class="sxs-lookup"><span data-stu-id="b0079-118">HL7 acknowledgment modes.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="b0079-119">アプリケーションの受信確認を元のメッセージの送信者に渡すことによって、元の受信確認モードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b0079-119"> supports the original acknowledgment mode by passing application acknowledgments back to the original message sender.</span></span>  
  
-   <span data-ttu-id="b0079-120">さまざまなメッセージング モード。</span><span class="sxs-lookup"><span data-stu-id="b0079-120">Different messaging modes.</span></span> <span data-ttu-id="b0079-121">これにより、複数の送信先にブロードキャストを有効にされ、関連付けられているクエリの応答にクエリを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="b0079-121">This enables broadcast to multiple destinations, and ties together queries to the associated query response.</span></span>  
  
-   <span data-ttu-id="b0079-122">XML エンコーディングのパイプで区切られたなど、複数のバージョンをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b0079-122">Support for multiple versions, including XML and pipe-delimited encodings.</span></span>  
  
-   <span data-ttu-id="b0079-123">さまざまな環境を有効にする HL7 バージョンとアップグレードの間のマッピング。</span><span class="sxs-lookup"><span data-stu-id="b0079-123">Mapping between HL7 versions to enable diverse environments and upgrades.</span></span>  
  
-   <span data-ttu-id="b0079-124">オーケストレーション内でのローカライズ (カスタマイズ)。</span><span class="sxs-lookup"><span data-stu-id="b0079-124">Localization (customization) within orchestration.</span></span>  
  
-   <span data-ttu-id="b0079-125">デバッグと新しいインターフェイスの評価をサポートするツールです。</span><span class="sxs-lookup"><span data-stu-id="b0079-125">Tools to support debugging and evaluation of new interfaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0079-126">参照</span><span class="sxs-lookup"><span data-stu-id="b0079-126">See Also</span></span>  
 <span data-ttu-id="b0079-127">[HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="b0079-127">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="b0079-128">[HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="b0079-128">[Using HL7 2.X Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span></span>  
 <span data-ttu-id="b0079-129">[HL7 2. XML スキーマを使用します。](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="b0079-129">[Using HL7 2.XML Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span></span>  
 <span data-ttu-id="b0079-130">[メッセージの種類およびイベント](../../adapters-and-accelerators/accelerator-hl7/message-types-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="b0079-130">[Message Types and Events](../../adapters-and-accelerators/accelerator-hl7/message-types-and-events.md) </span></span>  
 [<span data-ttu-id="b0079-131">HL7 メッセージ</span><span class="sxs-lookup"><span data-stu-id="b0079-131">HL7 Messaging</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)