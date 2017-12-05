---
title: "BTAHL7 内のメッセージのフロー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, message processing
- messages, message flow
- BTAHL7, message flow
ms.assetid: dd4599af-500d-4e52-85b2-8b6a28fd3f0a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33f06c896b58b2ba57c8c1bcee598d23f81b7700
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="how-messages-flow-through-btahl7"></a><span data-ttu-id="966f0-102">BTAHL7 内のメッセージのフロー</span><span class="sxs-lookup"><span data-stu-id="966f0-102">How Messages Flow through BTAHL7</span></span>
<span data-ttu-id="966f0-103">インストールするときに[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) の上に[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]追加する BizTalk Server[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]コンポーネントを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アーキテクチャ。</span><span class="sxs-lookup"><span data-stu-id="966f0-103">When you install [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) on top of [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server, you add [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] components to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] architecture.</span></span> <span data-ttu-id="966f0-104">次の図は、結合されたシステム、アーキテクチャの概要を説明[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="966f0-104">The following figure shows the combined system, which provides an architectural overview of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].</span></span>  
  
 <span data-ttu-id="966f0-105">![](../../adapters-and-accelerators/accelerator-hl7/media/bcd-hl7-sys-archc.gif "bcd_hl7_sys_archc")</span><span class="sxs-lookup"><span data-stu-id="966f0-105">![](../../adapters-and-accelerators/accelerator-hl7/media/bcd-hl7-sys-archc.gif "bcd_hl7_sys_archc")</span></span>  
  
## <a name="message-processing-flow"></a><span data-ttu-id="966f0-106">メッセージの処理フロー</span><span class="sxs-lookup"><span data-stu-id="966f0-106">Message Processing Flow</span></span>  
 <span data-ttu-id="966f0-107">基幹業務アプリケーションがメッセージを送信すると、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]システムでは、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="966f0-107">When a line-of-business application sends a message to the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] system, the following occurs:</span></span>  
  
1.  <span data-ttu-id="966f0-108">場合、メッセージは、HL7 メッセージ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]アダプター (通常は MLLP アダプター) を受信します。</span><span class="sxs-lookup"><span data-stu-id="966f0-108">If the message is an HL7 message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] receives it through an adapter (usually an MLLP adapter).</span></span> <span data-ttu-id="966f0-109">XML メッセージである場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]アダプター (通常は HTTP アダプター) を受信します。</span><span class="sxs-lookup"><span data-stu-id="966f0-109">If it is an XML message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] receives it through an adapter (usually an HTTP adapter).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="966f0-110">すべてのアダプター経由で 2.X と 2. の両方の XML メッセージを転送できます。ただし、V2 を通常トランスポートとします。MLLP アダプターでは、over X メッセージでは、HTTP アダプターを介して 2. XML メッセージをトランスポートが通常します。</span><span class="sxs-lookup"><span data-stu-id="966f0-110">You can transport both 2.X and 2.XML messages over any adapter; however, you would usually transport V2.X messages over an MLLP adapter, and you would usually transport 2.XML messages over an HTTP adapter.</span></span>  
  
2.  <span data-ttu-id="966f0-111">メッセージは、逆アセンブラー、および検証によって解析するため、受信パイプラインを介してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="966f0-111">The message is routed through the receive pipeline for parsing by the disassembler, and validation.</span></span>  
  
    1.  <span data-ttu-id="966f0-112">HL7 メッセージを受信メッセージには、フラット ファイル逆アセンブラー (DASM) により XML に分解します。</span><span class="sxs-lookup"><span data-stu-id="966f0-112">If the incoming message is an HL7 message, the flat file disassembler (DASM) disassembles it into XML.</span></span> <span data-ttu-id="966f0-113">受信メッセージが XML メッセージの場合は、XML 逆アセンブラーは、逆アセンブルします。</span><span class="sxs-lookup"><span data-stu-id="966f0-113">If the incoming message is an XML message, the XML DASM disassembles it.</span></span>  
  
    2.  <span data-ttu-id="966f0-114">受信メッセージがバッチ メッセージの場合は、個別のメッセージに逆アセンブラーが逆アセンブルします。</span><span class="sxs-lookup"><span data-stu-id="966f0-114">If the incoming message is a batch message, the disassembler disassembles into the individual messages.</span></span> <span data-ttu-id="966f0-115">(詳細については、次を参照してください[バッチ メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md)と[メッセージのバッチ処理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)。)。</span><span class="sxs-lookup"><span data-stu-id="966f0-115">(For more details, see [Batch Message Processing](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md) and [Message Batching](../../adapters-and-accelerators/accelerator-hl7/message-batching.md).)</span></span>  
  
    3.  <span data-ttu-id="966f0-116">逆アセンブラーは、メッセージを検証します。</span><span class="sxs-lookup"><span data-stu-id="966f0-116">The DASM then validates the message.</span></span>  
  
    4.  <span data-ttu-id="966f0-117">双方向を使用する場合 MLLP の受信アダプターが、逆アセンブラーが、メッセージを検証した場合と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]を元のメッセージを受信した同じアダプターでメッセージの元の送信者に確認 (ACK) を送信します。</span><span class="sxs-lookup"><span data-stu-id="966f0-117">If you use a two-way MLLP receive adapter, and if the disassembler has validated the message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends an acknowledgment (ACK) to the original sender of the message through the same adapter that received the original message.</span></span> <span data-ttu-id="966f0-118">ない場合は、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]否定受信確認応答 (NAK) を送信します。</span><span class="sxs-lookup"><span data-stu-id="966f0-118">If not, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends a negative acknowledgment (NAK).</span></span> <span data-ttu-id="966f0-119">(この手順を実行する方法によって異なります、ACK 構成。</span><span class="sxs-lookup"><span data-stu-id="966f0-119">(How this step is accomplished depends on the ACK configuration.</span></span> <span data-ttu-id="966f0-120">詳細については、「 [ACK メッセージ モード](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)。)</span><span class="sxs-lookup"><span data-stu-id="966f0-120">For details, see [ACK Message Modes](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md).)</span></span>  
  
    5.  <span data-ttu-id="966f0-121">双方向を使わない場合 MLLP の受信アダプター、し、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ACK または Ack または NAK (NAKs) を生成し、MessageBox データベースに展開します。</span><span class="sxs-lookup"><span data-stu-id="966f0-121">If you do not use a two-way MLLP receive adapter, then [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates an ACK or ACKs (or NAK or NAKs) and deposits it into the MessageBox database.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="966f0-122">(MLLP) だけでなく他のアダプターのいずれかを使用する送信ポートの構成に基づいて、適切なパーティにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="966f0-122"> then routes it to the appropriate parties based on the send port configuration, which could use any of the other adapters (besides MLLP).</span></span>  
  
     <span data-ttu-id="966f0-123">プロセスのより完全な一覧は、XML 逆アセンブラーとフラット ファイルで実行されるを参照してください[BizTalk Accelerator for HL7 コンポーネント](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)です。</span><span class="sxs-lookup"><span data-stu-id="966f0-123">For a more complete listing of the processes performed in the flat file and XML disassemblers, see [BizTalk Accelerator for HL7 Components](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md).</span></span>  
  
3.  <span data-ttu-id="966f0-124">メッセージは、アダプターと受信パイプラインを通過した後[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]MessageBox データベースにメッセージを渡します。</span><span class="sxs-lookup"><span data-stu-id="966f0-124">After the message passes through the adapter and the receive pipeline, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] passes the message into the MessageBox database.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="966f0-125">次に、メッセージを送信する場所を決定します。</span><span class="sxs-lookup"><span data-stu-id="966f0-125"> then determines where to send the message next.</span></span> <span data-ttu-id="966f0-126">メッセージがオーケストレーションの一部である場合は、オーケストレーション エンジンにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="966f0-126">If the message is part of an orchestration, it sends the message to the Orchestration Engine.</span></span>  
  
4.  <span data-ttu-id="966f0-127">オーケストレーション エンジンでは、メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="966f0-127">The Orchestration Engine processes the message.</span></span>  
  
    1.  <span data-ttu-id="966f0-128">マップは、メッセージに影響する場合、マップは、規則に従ってメッセージを変換します。</span><span class="sxs-lookup"><span data-stu-id="966f0-128">If a map affects the message, the map transforms the message according to its rules.</span></span>  
  
    2.  <span data-ttu-id="966f0-129">ビジネス ルールを設定した場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]パイプライン、オーケストレーション エンジンに可能性のある外部でビジネス ルール エンジン (BRE) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="966f0-129">If you have set up a business rule, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] invokes the Business Rule Engine (BRE) outside of the pipelines, potentially in the Orchestration Engine.</span></span>  
  
    3.  <span data-ttu-id="966f0-130">オーケストレーション エンジンは、メッセージをメッセージ ボックス データベースに送信し、オーケストレーションの処理が続行されます。</span><span class="sxs-lookup"><span data-stu-id="966f0-130">The Orchestration Engine sends the message back to the MessageBox database, and then continues processing the orchestration.</span></span>  
  
5.  <span data-ttu-id="966f0-131">サブスクリプションの場合、に基づいて[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージの送信ポートにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="966f0-131">Based on the subscription, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] routes the message to the send port.</span></span>  
  
6.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="966f0-132">(該当する場合)、次を処理するため、送信パイプラインでメッセージをルーティングします。 アセンブリおよび検証します。</span><span class="sxs-lookup"><span data-stu-id="966f0-132"> routes the message through the send pipeline for the following processing (if applicable): assembly and validation.</span></span>  
  
    1.  <span data-ttu-id="966f0-133">メッセージは、HL7 なる場合 2.X メッセージ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]XML からフラット ファイル アセンブラー (ASM) で HL7 にメッセージをアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="966f0-133">If the message will be an HL7 2.X message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] assembles the message from XML into HL7 by the flat file assembler (ASM).</span></span> <span data-ttu-id="966f0-134">受信メッセージが XML メッセージの場合、XML 逆アセンブラーにアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="966f0-134">If the incoming message will be an XML message, the XML DASM assembles it.</span></span>  
  
    2.  <span data-ttu-id="966f0-135">メッセージ バッチ メッセージの一部となる場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチ メッセージに各メッセージをアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="966f0-135">If the message will be part of a batch message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] assembles each message into the batch message.</span></span> <span data-ttu-id="966f0-136">(詳細については、次を参照してください[バッチ メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md)と[メッセージのバッチ処理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)。)。</span><span class="sxs-lookup"><span data-stu-id="966f0-136">(For more details, see [Batch Message Processing](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md) and [Message Batching](../../adapters-and-accelerators/accelerator-hl7/message-batching.md).)</span></span>  
  
    3.  <span data-ttu-id="966f0-137">ASM では、(送信パーティの構成の設定で有効になっている) 場合にメッセージが検証されます。</span><span class="sxs-lookup"><span data-stu-id="966f0-137">The ASM validates the message (if enabled through send-party configuration settings).</span></span>  
  
     <span data-ttu-id="966f0-138">プロセスのより完全な一覧は、XML アセンブラーとフラット ファイルで実行されるを参照してください[BizTalk Accelerator for HL7 コンポーネント](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)です。</span><span class="sxs-lookup"><span data-stu-id="966f0-138">For a more complete listing of the processes performed in the flat file and XML assemblers, see [BizTalk Accelerator for HL7 Components](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md).</span></span>  
  
7.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="966f0-139">アダプターでメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="966f0-139"> sends the message through an adapter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="966f0-140">アダプターの数を 2.X メッセージや 2. XML メッセージを転送することができます。ただし、ほとんどのシステムは、MLLP アダプターを経由 2.X メッセージと HTTP アダプターを介して 2. XML メッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="966f0-140">You can transport 2.X messages and 2.XML messages over a number of adapters; however, most systems transport 2.X messages over an MLLP adapter, and 2.XML messages over an HTTP adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="966f0-141">参照</span><span class="sxs-lookup"><span data-stu-id="966f0-141">See Also</span></span>  
 [<span data-ttu-id="966f0-142">BTAHL7 によるメッセージのルーティング方法</span><span class="sxs-lookup"><span data-stu-id="966f0-142">How BTAHL7 Routes Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/how-btahl7-routes-messages.md)