---
title: BTAHL72XML 処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.XML messages, processing
- acknowledgements, 2.XML messages
- 2.XML messages, message modes
- message modes, 2.XML message
- 2.XML messages
- validating, 2.XML messages
- 2.XML messages, acknowledgements
- 2.XML messages, validating
ms.assetid: 2f12cb44-816c-4773-9db0-9cbc3d1b1aee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e86697884c28d71fa9fb91c8b276293f7d36a588
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204682"
---
# <a name="btahl72xml-processing"></a><span data-ttu-id="572e8-102">BTAHL72XML 処理</span><span class="sxs-lookup"><span data-stu-id="572e8-102">BTAHL72XML Processing</span></span>
<span data-ttu-id="572e8-103">次のコンポーネントで[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) HL7 2. XML (XML でエンコードされた) メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="572e8-103">The following components in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) process HL7 2.XML (XML-encoded) messages:</span></span>  
  
-   <span data-ttu-id="572e8-104">パイプラインとコア ライブラリ:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]です。PipelineCommon.dll と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]です。PipelineMessageCore.dll</span><span class="sxs-lookup"><span data-stu-id="572e8-104">Pipelines and core libraries: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].PipelineCommon.dll and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].PipelineMessageCore.dll</span></span>  
  
-   <span data-ttu-id="572e8-105">アセンブラーおよび逆アセンブラーのライブラリ:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]です。HL72XmlAsm.dll と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]です。HL72XmlDAsm.dll</span><span class="sxs-lookup"><span data-stu-id="572e8-105">Assembler and disassembler libraries: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72XmlAsm.dll and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72XmlDAsm.dll</span></span>  
  
-   <span data-ttu-id="572e8-106">送信アダプターを受信確認 (ACK) の検証用のライブラリ双方向の MLLP:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]です。HL7ACKHelper.dll</span><span class="sxs-lookup"><span data-stu-id="572e8-106">The acknowledgment (ACK) validation library used for the two-way MLLP send adapter: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL7ACKHelper.dll</span></span>  
  
## <a name="xml-message-modes"></a><span data-ttu-id="572e8-107">XML メッセージ モード</span><span class="sxs-lookup"><span data-stu-id="572e8-107">XML Message Modes</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="572e8-108">2. XML メッセージを次のメッセージ モードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="572e8-108"> supports the following message modes for 2.XML messages:</span></span>  
  
-   <span data-ttu-id="572e8-109">パブリッシャーとサブスクライバー (パブリッシュ サブスクライブ) モード</span><span class="sxs-lookup"><span data-stu-id="572e8-109">Publisher-subscriber (pub-sub) mode</span></span>  
  
     <span data-ttu-id="572e8-110">パブリッシャーのブロードキャストとして宣言的または要請されていないが、サブスクライバーのパーティに更新します。</span><span class="sxs-lookup"><span data-stu-id="572e8-110">The publisher broadcasts to a party of subscribers, either as declarative or an unsolicited update.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="572e8-111">および[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]デザイン時の後に、サブスクリプションとパーティを管理することができますので、このモードでは、柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="572e8-111"> and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] provide flexibility to this mode, since you can manage subscriptions and parties after design time.</span></span>  
  
-   <span data-ttu-id="572e8-112">要求-応答モード</span><span class="sxs-lookup"><span data-stu-id="572e8-112">Request-response mode</span></span>  
  
     <span data-ttu-id="572e8-113">Interrogative またはクエリ メッセージ交換を特定のエンティティからの特定の要求の結果、応答メッセージ。</span><span class="sxs-lookup"><span data-stu-id="572e8-113">An interrogative or query message exchange in which a specific request from a specific entity results in a responding message.</span></span>  
  
## <a name="xml-validation"></a><span data-ttu-id="572e8-114">XML 検証</span><span class="sxs-lookup"><span data-stu-id="572e8-114">XML Validation</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="572e8-115">2. の次の検証 XML メッセージを提供します。</span><span class="sxs-lookup"><span data-stu-id="572e8-115"> provides the following validation of 2.XML messages:</span></span>  
  
-   <span data-ttu-id="572e8-116">XML リーダー</span><span class="sxs-lookup"><span data-stu-id="572e8-116">XML reader</span></span>  
  
-   <span data-ttu-id="572e8-117">概略図</span><span class="sxs-lookup"><span data-stu-id="572e8-117">Schematic</span></span>  
  
     <span data-ttu-id="572e8-118">有効にするまたは、パーティがスキーマの検証を無効にするとします。</span><span class="sxs-lookup"><span data-stu-id="572e8-118">You enable or disable schematic validation by the party.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="572e8-119">MSH9.3 メッセージ構造のヘッダー フィールドと MSH12 バージョン ID フィールド (2.3.1、2.4 または 2.5) によって決定される、この処理のために直接、HL7 2. XML スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="572e8-119"> uses the HL7 2.XML schemas directly for this processing, as determined by the MSH9.3 message-structure header field and the MSH12 Version ID field (2.3.1, 2.4, or 2.5).</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="572e8-120">標準の XML 処理機能を使用して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="572e8-120"> uses the standard XML processing capabilities in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="572e8-121">Z セグメント</span><span class="sxs-lookup"><span data-stu-id="572e8-121">Z segment</span></span>  
  
     [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="572e8-122">宣言されていない Z セグメントで宣言されたセグメントが含まれていないことを検証します。</span><span class="sxs-lookup"><span data-stu-id="572e8-122"> validates that no declared segments are included in an undeclared Z segment.</span></span>  
  
## <a name="ack-generation"></a><span data-ttu-id="572e8-123">確認の生成</span><span class="sxs-lookup"><span data-stu-id="572e8-123">ACK Generation</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="572e8-124">2. XML メッセージの受信確認 (Ack) の次の種類をサポートします。</span><span class="sxs-lookup"><span data-stu-id="572e8-124"> supports the following types of acknowledgments (ACKs) for 2.XML messages.</span></span> <span data-ttu-id="572e8-125">HL7 両方エラーの種類と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)](代替) エラーの種類が使用されます。</span><span class="sxs-lookup"><span data-stu-id="572e8-125">Both the HL7 error type and the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] (alternate) error type are used:</span></span>  
  
-   <span data-ttu-id="572e8-126">HL7 元 Ack</span><span class="sxs-lookup"><span data-stu-id="572e8-126">HL7 original ACKs</span></span>  
  
-   <span data-ttu-id="572e8-127">HL7 Ack の強化</span><span class="sxs-lookup"><span data-stu-id="572e8-127">HL7 enhanced ACKs</span></span>  
  
     <span data-ttu-id="572e8-128">コミットがそのまま使用し、アプリケーションの同意</span><span class="sxs-lookup"><span data-stu-id="572e8-128">Commit Accept and Application Accept</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="572e8-129">参照</span><span class="sxs-lookup"><span data-stu-id="572e8-129">See Also</span></span>  
 <span data-ttu-id="572e8-130">[メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="572e8-130">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="572e8-131">HL7 2. XML スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="572e8-131">Using HL7 2.XML Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)