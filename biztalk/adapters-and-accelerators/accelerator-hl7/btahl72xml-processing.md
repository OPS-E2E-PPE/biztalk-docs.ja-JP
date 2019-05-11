---
title: BTAHL72XML 処理 |Microsoft Docs
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
ms.openlocfilehash: 76ddf6ebce9cb9e473a348f1abca6a1af49abb02
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251443"
---
# <a name="btahl72xml-processing"></a><span data-ttu-id="235ba-102">BTAHL72XML 処理</span><span class="sxs-lookup"><span data-stu-id="235ba-102">BTAHL72XML Processing</span></span>
<span data-ttu-id="235ba-103">Microsoft BizTalk Accelerator for HL7 の次のコンポーネント ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) HL7 2. XML (XML でエンコードされた) メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="235ba-103">The following components in Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) process HL7 2.XML (XML-encoded) messages:</span></span>  
  
- <span data-ttu-id="235ba-104">パイプラインとコア ライブラリ:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。PipelineCommon.dll と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。PipelineMessageCore.dll</span><span class="sxs-lookup"><span data-stu-id="235ba-104">Pipelines and core libraries: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].PipelineCommon.dll and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].PipelineMessageCore.dll</span></span>  
  
- <span data-ttu-id="235ba-105">アセンブラーおよび逆アセンブラー ライブラリ:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。HL72XmlAsm.dll と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。HL72XmlDAsm.dll</span><span class="sxs-lookup"><span data-stu-id="235ba-105">Assembler and disassembler libraries: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72XmlAsm.dll and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72XmlDAsm.dll</span></span>  
  
- <span data-ttu-id="235ba-106">送信アダプターのための双方向の MLLP 受信確認 (ACK) 検証ライブラリ:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。HL7ACKHelper.dll</span><span class="sxs-lookup"><span data-stu-id="235ba-106">The acknowledgment (ACK) validation library used for the two-way MLLP send adapter: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL7ACKHelper.dll</span></span>  
  
## <a name="xml-message-modes"></a><span data-ttu-id="235ba-107">XML メッセージ モード</span><span class="sxs-lookup"><span data-stu-id="235ba-107">XML Message Modes</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="235ba-108">2. XML メッセージの次のメッセージ モードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="235ba-108">supports the following message modes for 2.XML messages:</span></span>  
  
- <span data-ttu-id="235ba-109">パブリッシャーとサブスクライバー (パブリッシュ-サブスクライブ) モード</span><span class="sxs-lookup"><span data-stu-id="235ba-109">Publisher-subscriber (pub-sub) mode</span></span>  
  
   <span data-ttu-id="235ba-110">パブリッシャーにブロードキャストする宣言型または要請されていないが、サブスクライバーのパーティを更新します。</span><span class="sxs-lookup"><span data-stu-id="235ba-110">The publisher broadcasts to a party of subscribers, either as declarative or an unsolicited update.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="235ba-111">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]デザイン時後のサブスクリプションとパーティを管理できるため、このモードでは、柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="235ba-111">and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] provide flexibility to this mode, since you can manage subscriptions and parties after design time.</span></span>  
  
- <span data-ttu-id="235ba-112">要求-応答モード</span><span class="sxs-lookup"><span data-stu-id="235ba-112">Request-response mode</span></span>  
  
   <span data-ttu-id="235ba-113">Interrogative またはクエリ メッセージ交換を特定のエンティティから特定の要求の結果、応答メッセージ。</span><span class="sxs-lookup"><span data-stu-id="235ba-113">An interrogative or query message exchange in which a specific request from a specific entity results in a responding message.</span></span>  
  
## <a name="xml-validation"></a><span data-ttu-id="235ba-114">XML 検証</span><span class="sxs-lookup"><span data-stu-id="235ba-114">XML Validation</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="235ba-115">2. の次の検証 XML メッセージを提供します。</span><span class="sxs-lookup"><span data-stu-id="235ba-115">provides the following validation of 2.XML messages:</span></span>  
  
- <span data-ttu-id="235ba-116">XML リーダー</span><span class="sxs-lookup"><span data-stu-id="235ba-116">XML reader</span></span>  
  
- <span data-ttu-id="235ba-117">概略図</span><span class="sxs-lookup"><span data-stu-id="235ba-117">Schematic</span></span>  
  
   <span data-ttu-id="235ba-118">有効にするまたはで、パーティがスキーマの検証を無効にします。</span><span class="sxs-lookup"><span data-stu-id="235ba-118">You enable or disable schematic validation by the party.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="235ba-119">MSH9.3 メッセージ構造のヘッダー フィールドと MSH12 バージョン ID フィールド (2.3.1 や 2.4、2.5) によって決定される、この処理には直接、HL7 2. XML スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="235ba-119">uses the HL7 2.XML schemas directly for this processing, as determined by the MSH9.3 message-structure header field and the MSH12 Version ID field (2.3.1, 2.4, or 2.5).</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="235ba-120">標準の XML 処理機能を使用して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="235ba-120">uses the standard XML processing capabilities in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="235ba-121">Z セグメント</span><span class="sxs-lookup"><span data-stu-id="235ba-121">Z segment</span></span>  
  
   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="235ba-122">未宣言の Z セグメントで宣言されたセグメントが含まれていないことを検証します。</span><span class="sxs-lookup"><span data-stu-id="235ba-122">validates that no declared segments are included in an undeclared Z segment.</span></span>  
  
## <a name="ack-generation"></a><span data-ttu-id="235ba-123">確認の生成</span><span class="sxs-lookup"><span data-stu-id="235ba-123">ACK Generation</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="235ba-124">2. XML メッセージの受信確認 (Ack) の次の種類をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="235ba-124">supports the following types of acknowledgments (ACKs) for 2.XML messages.</span></span> <span data-ttu-id="235ba-125">HL7 両方エラーの種類と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)](代替) エラーの種類が使用されます。</span><span class="sxs-lookup"><span data-stu-id="235ba-125">Both the HL7 error type and the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] (alternate) error type are used:</span></span>  
  
-   <span data-ttu-id="235ba-126">HL7 の元の確認</span><span class="sxs-lookup"><span data-stu-id="235ba-126">HL7 original ACKs</span></span>  
  
-   <span data-ttu-id="235ba-127">HL7 の Ack を強化します。</span><span class="sxs-lookup"><span data-stu-id="235ba-127">HL7 enhanced ACKs</span></span>  
  
     <span data-ttu-id="235ba-128">コミットがそのまま使用し、アプリケーションの同意</span><span class="sxs-lookup"><span data-stu-id="235ba-128">Commit Accept and Application Accept</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="235ba-129">参照</span><span class="sxs-lookup"><span data-stu-id="235ba-129">See Also</span></span>  
 <span data-ttu-id="235ba-130">[メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="235ba-130">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="235ba-131">HL7 2. XML スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="235ba-131">Using HL7 2.XML Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)