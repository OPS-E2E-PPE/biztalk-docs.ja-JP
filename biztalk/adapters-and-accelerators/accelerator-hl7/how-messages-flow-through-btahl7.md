---
title: BTAHL7 内のメッセージのフロー方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, message processing
- messages, message flow
- BTAHL7, message flow
ms.assetid: dd4599af-500d-4e52-85b2-8b6a28fd3f0a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2b048ee47ca90b47644286cef90b9937b8a20bb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65296380"
---
# <a name="how-messages-flow-through-btahl7"></a><span data-ttu-id="94b45-102">Btahl7 のメッセージのフロー</span><span class="sxs-lookup"><span data-stu-id="94b45-102">How Messages Flow through BTAHL7</span></span>
<span data-ttu-id="94b45-103">Microsoft BizTalk Accelerator for HL7 にインストールするときに ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) を追加する MicrosoftBizTalk のサーバー上に[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]コンポーネントを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アーキテクチャ。</span><span class="sxs-lookup"><span data-stu-id="94b45-103">When you install Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) on top of MicrosoftBizTalk Server, you add [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] components to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] architecture.</span></span> <span data-ttu-id="94b45-104">次の図は、結合されたシステムのアーキテクチャの概要を提供する[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="94b45-104">The following figure shows the combined system, which provides an architectural overview of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].</span></span>  
  
 <span data-ttu-id="94b45-105">![](../../adapters-and-accelerators/accelerator-hl7/media/bcd-hl7-sys-archc.gif "bcd_hl7_sys_archc")</span><span class="sxs-lookup"><span data-stu-id="94b45-105">![](../../adapters-and-accelerators/accelerator-hl7/media/bcd-hl7-sys-archc.gif "bcd_hl7_sys_archc")</span></span>  
  
## <a name="message-processing-flow"></a><span data-ttu-id="94b45-106">メッセージの処理フロー</span><span class="sxs-lookup"><span data-stu-id="94b45-106">Message Processing Flow</span></span>  
 <span data-ttu-id="94b45-107">基幹業務アプリケーションがメッセージを送信すると、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]システムでは、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="94b45-107">When a line-of-business application sends a message to the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] system, the following occurs:</span></span>  
  
1. <span data-ttu-id="94b45-108">場合、メッセージは、HL7 メッセージ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]アダプター (通常は MLLP アダプター) を受信します。</span><span class="sxs-lookup"><span data-stu-id="94b45-108">If the message is an HL7 message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] receives it through an adapter (usually an MLLP adapter).</span></span> <span data-ttu-id="94b45-109">XML メッセージである場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]アダプター (通常は HTTP アダプター) を受信します。</span><span class="sxs-lookup"><span data-stu-id="94b45-109">If it is an XML message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] receives it through an adapter (usually an HTTP adapter).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="94b45-110">すべてのアダプター経由で 2.X と 2.xml の両方の XML メッセージを転送できます。ただし、V2 は、通常、トランスポートはします。MLLP アダプターとする X メッセージは、HTTP アダプターを介して 2. XML メッセージをトランスポートは、通常は。</span><span class="sxs-lookup"><span data-stu-id="94b45-110">You can transport both 2.X and 2.XML messages over any adapter; however, you would usually transport V2.X messages over an MLLP adapter, and you would usually transport 2.XML messages over an HTTP adapter.</span></span>  
  
2. <span data-ttu-id="94b45-111">メッセージは、逆アセンブラー、および検証による解析のため、受信パイプラインを介してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="94b45-111">The message is routed through the receive pipeline for parsing by the disassembler, and validation.</span></span>  
  
   1. <span data-ttu-id="94b45-112">受信メッセージが HL7 メッセージで、フラット ファイル逆アセンブラー (逆アセンブラー) により XML にアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="94b45-112">If the incoming message is an HL7 message, the flat file disassembler (DASM) disassembles it into XML.</span></span> <span data-ttu-id="94b45-113">受信メッセージが XML メッセージの場合、XML 逆アセンブラーが逆アセンブルします。</span><span class="sxs-lookup"><span data-stu-id="94b45-113">If the incoming message is an XML message, the XML DASM disassembles it.</span></span>  
  
   2. <span data-ttu-id="94b45-114">受信メッセージがバッチ メッセージの場合は、個別のメッセージに、逆アセンブラーが逆アセンブルします。</span><span class="sxs-lookup"><span data-stu-id="94b45-114">If the incoming message is a batch message, the disassembler disassembles into the individual messages.</span></span> <span data-ttu-id="94b45-115">(詳細については、次を参照してください[バッチ メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md)と[メッセージのバッチ処理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)。)。</span><span class="sxs-lookup"><span data-stu-id="94b45-115">(For more details, see [Batch Message Processing](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md) and [Message Batching](../../adapters-and-accelerators/accelerator-hl7/message-batching.md).)</span></span>  
  
   3. <span data-ttu-id="94b45-116">逆アセンブラーは、メッセージを検証します。</span><span class="sxs-lookup"><span data-stu-id="94b45-116">The DASM then validates the message.</span></span>  
  
   4. <span data-ttu-id="94b45-117">双方向を使用する場合 MLLP 受信アダプター、逆アセンブラーは、メッセージを検証した場合と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]を元のメッセージを受信した同じアダプターでメッセージの元の送信者に受信確認 (ACK) を送信します。</span><span class="sxs-lookup"><span data-stu-id="94b45-117">If you use a two-way MLLP receive adapter, and if the disassembler has validated the message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends an acknowledgment (ACK) to the original sender of the message through the same adapter that received the original message.</span></span> <span data-ttu-id="94b45-118">ない場合は、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]否定受信確認応答 (NAK) を送信します。</span><span class="sxs-lookup"><span data-stu-id="94b45-118">If not, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends a negative acknowledgment (NAK).</span></span> <span data-ttu-id="94b45-119">(この手順を実行する方法、ACK の構成に依存します。</span><span class="sxs-lookup"><span data-stu-id="94b45-119">(How this step is accomplished depends on the ACK configuration.</span></span> <span data-ttu-id="94b45-120">詳細については、次を参照してください[ACK メッセージ モード](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)。)。</span><span class="sxs-lookup"><span data-stu-id="94b45-120">For details, see [ACK Message Modes](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md).)</span></span>  
  
   5. <span data-ttu-id="94b45-121">双方向を使わない場合 MLLP 受信アダプターが、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ACK または Ack または NAK (NAKs) を生成し、により、メッセージ ボックス データベースにします。</span><span class="sxs-lookup"><span data-stu-id="94b45-121">If you do not use a two-way MLLP receive adapter, then [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates an ACK or ACKs (or NAK or NAKs) and deposits it into the MessageBox database.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="94b45-122">(MLLP) だけでなく他のアダプターのいずれかを使用できる送信ポートの構成に基づいて適切なパーティにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="94b45-122">then routes it to the appropriate parties based on the send port configuration, which could use any of the other adapters (besides MLLP).</span></span>  
  
      <span data-ttu-id="94b45-123">プロセスのより完全な一覧は、XML 逆アセンブラーとフラット ファイルの実行を参照してください。 [BizTalk Accelerator for HL7 コンポーネント](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)します。</span><span class="sxs-lookup"><span data-stu-id="94b45-123">For a more complete listing of the processes performed in the flat file and XML disassemblers, see [BizTalk Accelerator for HL7 Components](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md).</span></span>  
  
3. <span data-ttu-id="94b45-124">メッセージは、アダプターと受信パイプラインを通過したら[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージ ボックス データベースにメッセージを渡します。</span><span class="sxs-lookup"><span data-stu-id="94b45-124">After the message passes through the adapter and the receive pipeline, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] passes the message into the MessageBox database.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="94b45-125">次に、メッセージの送信先を決定します。</span><span class="sxs-lookup"><span data-stu-id="94b45-125">then determines where to send the message next.</span></span> <span data-ttu-id="94b45-126">メッセージがオーケストレーションの一部である場合は、オーケストレーション エンジンにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="94b45-126">If the message is part of an orchestration, it sends the message to the Orchestration Engine.</span></span>  
  
4. <span data-ttu-id="94b45-127">オーケストレーション エンジンは、メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="94b45-127">The Orchestration Engine processes the message.</span></span>  
  
   1. <span data-ttu-id="94b45-128">マップは、メッセージに影響する場合、マップは、その規則に従ってメッセージを変換します。</span><span class="sxs-lookup"><span data-stu-id="94b45-128">If a map affects the message, the map transforms the message according to its rules.</span></span>  
  
   2. <span data-ttu-id="94b45-129">ビジネス ルールを設定している場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]外のパイプライン、オーケストレーション エンジンで可能性のあるビジネス ルール エンジン (BRE) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="94b45-129">If you have set up a business rule, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] invokes the Business Rule Engine (BRE) outside of the pipelines, potentially in the Orchestration Engine.</span></span>  
  
   3. <span data-ttu-id="94b45-130">オーケストレーション エンジンは、メッセージをメッセージ ボックス データベースに送信し、オーケストレーションの処理が続行されます。</span><span class="sxs-lookup"><span data-stu-id="94b45-130">The Orchestration Engine sends the message back to the MessageBox database, and then continues processing the orchestration.</span></span>  
  
5. <span data-ttu-id="94b45-131">サブスクリプションの場合、に基づいて[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージの送信ポートにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="94b45-131">Based on the subscription, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] routes the message to the send port.</span></span>  
  
6. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="94b45-132">(該当する) 場合、次を処理するため、送信パイプラインでメッセージをルーティングします。 アセンブリおよび検証します。</span><span class="sxs-lookup"><span data-stu-id="94b45-132">routes the message through the send pipeline for the following processing (if applicable): assembly and validation.</span></span>  
  
   1. <span data-ttu-id="94b45-133">メッセージでは、HL7 場合 2.X メッセージ、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] XML からフラット ファイル アセンブラー (ASM) が HL7 にメッセージをアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="94b45-133">If the message will be an HL7 2.X message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] assembles the message from XML into HL7 by the flat file assembler (ASM).</span></span> <span data-ttu-id="94b45-134">受信メッセージが XML メッセージの場合、XML 逆アセンブラーによってアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="94b45-134">If the incoming message will be an XML message, the XML DASM assembles it.</span></span>  
  
   2. <span data-ttu-id="94b45-135">メッセージは、バッチ メッセージの一部になる場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチ メッセージに各メッセージをアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="94b45-135">If the message will be part of a batch message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] assembles each message into the batch message.</span></span> <span data-ttu-id="94b45-136">(詳細については、次を参照してください[バッチ メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md)と[メッセージのバッチ処理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)。)。</span><span class="sxs-lookup"><span data-stu-id="94b45-136">(For more details, see [Batch Message Processing](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md) and [Message Batching](../../adapters-and-accelerators/accelerator-hl7/message-batching.md).)</span></span>  
  
   3. <span data-ttu-id="94b45-137">ASM (送信パーティの構成設定を使用して有効になっている) 場合、メッセージを検証します。</span><span class="sxs-lookup"><span data-stu-id="94b45-137">The ASM validates the message (if enabled through send-party configuration settings).</span></span>  
  
      <span data-ttu-id="94b45-138">プロセスのより完全な一覧は、フラット ファイルと XML アセンブラーで実行を参照してください[BizTalk Accelerator for HL7 コンポーネント](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)します。</span><span class="sxs-lookup"><span data-stu-id="94b45-138">For a more complete listing of the processes performed in the flat file and XML assemblers, see [BizTalk Accelerator for HL7 Components](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md).</span></span>  
  
7. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="94b45-139">アダプターでメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="94b45-139">sends the message through an adapter.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="94b45-140">アダプターの数を 2.X メッセージや 2. XML メッセージを転送することができます。ただし、ほとんどのシステムは、2.X MLLP アダプターでは、メッセージと HTTP アダプターを介して 2. XML メッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="94b45-140">You can transport 2.X messages and 2.XML messages over a number of adapters; however, most systems transport 2.X messages over an MLLP adapter, and 2.XML messages over an HTTP adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94b45-141">参照</span><span class="sxs-lookup"><span data-stu-id="94b45-141">See Also</span></span>  
 [<span data-ttu-id="94b45-142">BTAHL7 によるメッセージのルーティング方法</span><span class="sxs-lookup"><span data-stu-id="94b45-142">How BTAHL7 Routes Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/how-btahl7-routes-messages.md)