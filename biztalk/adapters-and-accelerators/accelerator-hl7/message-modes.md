---
title: メッセージ モード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message modes, about message modes
- messages, message modes
- message modes, HL7 messages
ms.assetid: 2d832b67-6f0e-45e1-95ac-cb80b74a7831
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfce63f527dbe9643228b3b47a509b404e78c510
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009139"
---
# <a name="message-modes"></a><span data-ttu-id="82a76-102">メッセージ モード</span><span class="sxs-lookup"><span data-stu-id="82a76-102">Message Modes</span></span>
<span data-ttu-id="82a76-103">すべての HL7 メッセージの基になる 2 つの基本的な概念があります。</span><span class="sxs-lookup"><span data-stu-id="82a76-103">There are two basic concepts that underlie all HL7 messages.</span></span> <span data-ttu-id="82a76-104">これらの概念はアドレス データを交換する独立したシステムの相互作用し、分散医療システム内で時間の経過と共に相互運用性の要件をサポートする構造を提供する、さまざまな方法です。</span><span class="sxs-lookup"><span data-stu-id="82a76-104">These concepts address different ways in which independent systems that exchange data can interact, and provide a structure that supports the requirements of interoperability over time within a distributed health care system.</span></span> <span data-ttu-id="82a76-105">以下に示す概念は、HL7 デザインの背後にある基になるテーマを定義します。</span><span class="sxs-lookup"><span data-stu-id="82a76-105">The concepts listed below define the underlying themes behind the HL7 design:</span></span>  
  
- <span data-ttu-id="82a76-106">**メッセージ モード**します。</span><span class="sxs-lookup"><span data-stu-id="82a76-106">**Messaging Mode**.</span></span> <span data-ttu-id="82a76-107">情報交換の 3 つの基本的な目的の認識: (interrogative) 情報を要求する (宣言型)、情報をブロードキャストして、システム操作の実行 (命令型) を要求します。</span><span class="sxs-lookup"><span data-stu-id="82a76-107">The recognition of three fundamental purposes for information exchange: to broadcast information (declarative), to request information (interrogative), and to request that the system take an action (imperative).</span></span> <span data-ttu-id="82a76-108">それぞれの目的は、その特定の要件とメッセージ フローのパターン。</span><span class="sxs-lookup"><span data-stu-id="82a76-108">Each of these purposes has its particular requirements and pattern of message flow.</span></span>  
  
- <span data-ttu-id="82a76-109">**受信確認モード**します。</span><span class="sxs-lookup"><span data-stu-id="82a76-109">**Acknowledgment Mode**.</span></span> <span data-ttu-id="82a76-110">疎と緊密をサポートする必要性には、メッセージングのスタイルが結合されています。</span><span class="sxs-lookup"><span data-stu-id="82a76-110">The need to support tightly and loosely coupled styles of messaging.</span></span> <span data-ttu-id="82a76-111">HL7 の受信確認のモードでは、受信者からの応答を必要とするか、メッセージ配信を保証するために、基になるネットワークを有効にする、送信元アプリケーションが有効にします。</span><span class="sxs-lookup"><span data-stu-id="82a76-111">The acknowledgment modes for HL7 enable a sending application either to require a response from the receiver, or to enable the underlying network to guarantee message delivery.</span></span>  
  
- <span data-ttu-id="82a76-112">**ローカリゼーション**します。</span><span class="sxs-lookup"><span data-stu-id="82a76-112">**Localization**.</span></span> <span data-ttu-id="82a76-113">メッセージの仕様にサイト固有の資料を紹介するエンティティを許可することで特定のローカルの要件をサポートするために必要です。</span><span class="sxs-lookup"><span data-stu-id="82a76-113">The need to support specific local requirements by allowing entities to introduce site-specific material into message specifications.</span></span>  
  
- <span data-ttu-id="82a76-114">**進化**します。</span><span class="sxs-lookup"><span data-stu-id="82a76-114">**Evolution**.</span></span> <span data-ttu-id="82a76-115">Standard のバージョン間の相互運用性を有効にすると、多くのインターフェイスと、多くのアプリケーションのサイトをサポートするために必要です。</span><span class="sxs-lookup"><span data-stu-id="82a76-115">The need to support sites with many interfaces and many applications by enabling interoperability between standard versions.</span></span> <span data-ttu-id="82a76-116">これにより、すべてのインターフェイスを同時にアップグレードを必要とするのではなく、ステージ インターフェイスのアップグレードにエンティティができます。</span><span class="sxs-lookup"><span data-stu-id="82a76-116">This enables entities to stage interface upgrades, as opposed to requiring simultaneous upgrades of all interfaces.</span></span>  
  
  <span data-ttu-id="82a76-117">Microsoft BizTalk Accelerator for HL7 の次の関数 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 上記の要件をサポートします。</span><span class="sxs-lookup"><span data-stu-id="82a76-117">The following functions of Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) support the above requirements:</span></span>  
  
- <span data-ttu-id="82a76-118">HL7 の受信確認モード。</span><span class="sxs-lookup"><span data-stu-id="82a76-118">HL7 acknowledgment modes.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="82a76-119"> アプリケーションの受信確認を元のメッセージの送信者に渡すことによって、元の受信確認のモードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="82a76-119"> supports the original acknowledgment mode by passing application acknowledgments back to the original message sender.</span></span>  
  
- <span data-ttu-id="82a76-120">さまざまなメッセージング モード。</span><span class="sxs-lookup"><span data-stu-id="82a76-120">Different messaging modes.</span></span> <span data-ttu-id="82a76-121">これにより、複数の送信先へのブロードキャストと関連付けられているクエリの応答にクエリを連結します。</span><span class="sxs-lookup"><span data-stu-id="82a76-121">This enables broadcast to multiple destinations, and ties together queries to the associated query response.</span></span>  
  
- <span data-ttu-id="82a76-122">などの XML エンコーディングをパイプで区切られた複数のバージョンのサポート。</span><span class="sxs-lookup"><span data-stu-id="82a76-122">Support for multiple versions, including XML and pipe-delimited encodings.</span></span>  
  
- <span data-ttu-id="82a76-123">さまざまな環境を有効にする HL7 バージョンとアップグレードの間のマッピング。</span><span class="sxs-lookup"><span data-stu-id="82a76-123">Mapping between HL7 versions to enable diverse environments and upgrades.</span></span>  
  
- <span data-ttu-id="82a76-124">オーケストレーション内でのローカライズ (カスタマイズ)。</span><span class="sxs-lookup"><span data-stu-id="82a76-124">Localization (customization) within orchestration.</span></span>  
  
- <span data-ttu-id="82a76-125">デバッグと新しいインターフェイスの評価をサポートするツールです。</span><span class="sxs-lookup"><span data-stu-id="82a76-125">Tools to support debugging and evaluation of new interfaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a76-126">参照</span><span class="sxs-lookup"><span data-stu-id="82a76-126">See Also</span></span>  
 <span data-ttu-id="82a76-127">[HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="82a76-127">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="82a76-128">[HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="82a76-128">[Using HL7 2.X Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span></span>  
 <span data-ttu-id="82a76-129">[HL7 2. XML スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="82a76-129">[Using HL7 2.XML Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span></span>  
 <span data-ttu-id="82a76-130">[メッセージの種類とイベント](../../adapters-and-accelerators/accelerator-hl7/message-types-and-events.md) </span><span class="sxs-lookup"><span data-stu-id="82a76-130">[Message Types and Events](../../adapters-and-accelerators/accelerator-hl7/message-types-and-events.md) </span></span>  
 [<span data-ttu-id="82a76-131">HL7 メッセージング</span><span class="sxs-lookup"><span data-stu-id="82a76-131">HL7 Messaging</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)