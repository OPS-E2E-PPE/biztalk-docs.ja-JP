---
title: BTAHL72X フラット ファイル処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ACKs
- 2.X messages, disassembler
- property promotion, MSH-header schemas
- disassembler, validating messages
- HL7, errors
- 2.X messages, validating headers
- acknowledgements, generating
- assembler, validating messages
- messages, multi-part messages
- property promotion, property schemas
- generating aknowledgements
- messages, 2.X messages
- schemas, MSH-header schemas
- 2.X messages, validating message bodies
- 2.X messages
- schemas, property schemas
- message modes, 2.X messages
- errors, HL7 error format
- flat files
- validating, messages
- schemas, property promotion
- headers, validating
- 2.X messages, message modes
- 2.X messages, header validation
- 2.X messages, parsing flat files
ms.assetid: c92e2f70-0bfa-4bc8-8044-4a6e62cabee3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a0220d44386eed94efbddc1a5a22fe6704a7780
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975555"
---
# <a name="btahl72x-flat-file-processing"></a><span data-ttu-id="6ddf3-102">BTAHL72X フラット ファイル処理</span><span class="sxs-lookup"><span data-stu-id="6ddf3-102">BTAHL72X Flat File Processing</span></span>
<span data-ttu-id="6ddf3-103">Microsoft BizTalk Accelerator for HL7 の次のコンポーネント ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) プロセス HL7 2.X (HL7 でエンコードされた) メッセージ。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-103">The following components in Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) process HL7 2.X (HL7-encoded) messages:</span></span>  
  
- <span data-ttu-id="6ddf3-104">パイプラインとコア ライブラリ:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。PipelineCommon.dll と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。PipelineMessageCore.dll</span><span class="sxs-lookup"><span data-stu-id="6ddf3-104">Pipelines and core libraries: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].PipelineCommon.dll and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].PipelineMessageCore.dll</span></span>  
  
- <span data-ttu-id="6ddf3-105">アセンブラーおよび逆アセンブラー ライブラリ:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。HL72fAsm.dll と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。HL72fDAsm.dll</span><span class="sxs-lookup"><span data-stu-id="6ddf3-105">Assembler and disassembler libraries: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72fAsm.dll and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72fDAsm.dll</span></span>  
  
- <span data-ttu-id="6ddf3-106">送信アダプターのための双方向の MLLP 受信確認 (ACK) 検証ライブラリ:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。HL7ACKHelper.dll</span><span class="sxs-lookup"><span data-stu-id="6ddf3-106">The acknowledgment (ACK) validation library used for the two-way MLLP send adapter: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL7ACKHelper.dll</span></span>  
  
## <a name="hl7-message-modes"></a><span data-ttu-id="6ddf3-107">HL7 メッセージ モード</span><span class="sxs-lookup"><span data-stu-id="6ddf3-107">HL7 Message Modes</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="6ddf3-108"> 2.X のメッセージを次のメッセージ モードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-108"> supports the following message modes for 2.X messages:</span></span>  
  
- <span data-ttu-id="6ddf3-109">パブリッシャーとサブスクライバー (パブリッシュ-サブスクライブ) モード</span><span class="sxs-lookup"><span data-stu-id="6ddf3-109">Publisher-subscriber (pub-sub) mode</span></span>  
  
   <span data-ttu-id="6ddf3-110">パブリッシャーにブロードキャストする宣言型または要請されていないが、サブスクライバーのパーティを更新します。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-110">The publisher broadcasts to a party of subscribers, either as declarative or an unsolicited update.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6ddf3-111"> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]デザイン時後のサブスクリプションとパーティを管理できるため、このモードでは、柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-111"> and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] provide flexibility to this mode, since you can manage subscriptions and parties after design time.</span></span>  
  
- <span data-ttu-id="6ddf3-112">要求-応答モード</span><span class="sxs-lookup"><span data-stu-id="6ddf3-112">Request-response mode</span></span>  
  
   <span data-ttu-id="6ddf3-113">Interrogative またはクエリ メッセージ交換を特定のエンティティから特定の要求の結果、応答メッセージ。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-113">An interrogative or query message exchange in which a specific request from a specific entity results in a responding message.</span></span>  
  
## <a name="flat-file-parsing"></a><span data-ttu-id="6ddf3-114">フラット ファイル解析</span><span class="sxs-lookup"><span data-stu-id="6ddf3-114">Flat File Parsing</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="6ddf3-115"> 解析 HL7 2.X を 3 つの部分にマルチパート メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6ddf3-115"> parses HL7 2.X multi-part messages into three parts:</span></span>  
  
-   <span data-ttu-id="6ddf3-116">ヘッダー MSH パーツ</span><span class="sxs-lookup"><span data-stu-id="6ddf3-116">Header-MSH part</span></span>  
  
-   <span data-ttu-id="6ddf3-117">ボディ部</span><span class="sxs-lookup"><span data-stu-id="6ddf3-117">Body part</span></span>  
  
-   <span data-ttu-id="6ddf3-118">Z の一部</span><span class="sxs-lookup"><span data-stu-id="6ddf3-118">Z part</span></span>  
  
## <a name="hl7-header-validation"></a><span data-ttu-id="6ddf3-119">HL7 ヘッダーの検証</span><span class="sxs-lookup"><span data-stu-id="6ddf3-119">HL7 Header Validation</span></span>  
 <span data-ttu-id="6ddf3-120">HL7 の逆アセンブラーとアセンブラーは、メッセージを処理できることを確認するには、2.X のメッセージのヘッダーの構造とスキーマの検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-120">The HL7 disassembler and assembler perform structural and schematic validation of the header of a 2.X message, in order to verify that it can process the message.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="6ddf3-121"> 一般的なヘッダー スキーマ、MSH_25_GLO_DEF の概略図の検証を行います。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-121"> bases the schematic validation on the common header schema, MSH_25_GLO_DEF.</span></span>  
  
 <span data-ttu-id="6ddf3-122">たとえば、MSH1 と MSH2 フィールドが整形パーサーを決定します。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-122">For instance, the parser determines that the MSH1 and MSH2 fields are well formed.</span></span> <span data-ttu-id="6ddf3-123">MSH1 には、1 つだけの文字が必要です。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-123">MSH1 must have only one character.</span></span> <span data-ttu-id="6ddf3-124">文字を繰り返すことがないと、2 ~ 4 つの文字、MSH2 があります。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-124">MSH2 must be between two and four characters, and no characters can repeat.</span></span>  
  
## <a name="hl7-body-validation"></a><span data-ttu-id="6ddf3-125">HL7 の本文の検証</span><span class="sxs-lookup"><span data-stu-id="6ddf3-125">HL7 Body Validation</span></span>  
 <span data-ttu-id="6ddf3-126">HL7 の逆アセンブラーとアセンブラーは、2.X のメッセージの本文の基本的な構造の検証とスキーマの検証を有効にした場合実行します。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-126">The HL7 disassembler and assembler perform basic structural validation of the body of a 2.X message, and schematic validation, if you enable it.</span></span>  
  
 <span data-ttu-id="6ddf3-127">本文の基本的な構造検証を[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]常に実行する、次の検証が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-127">The basic structural validation of the body, which [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] always performs, includes verifying the following:</span></span>  
  
- <span data-ttu-id="6ddf3-128">セグメントで 3 つの文字があること</span><span class="sxs-lookup"><span data-stu-id="6ddf3-128">That there are three characters in segments</span></span>  
  
- <span data-ttu-id="6ddf3-129">セグメント区切り記号が\<CR\>または\<CR\>\<LF\> (最後のセグメントは省略可能)</span><span class="sxs-lookup"><span data-stu-id="6ddf3-129">That the segment delimiter is \<CR\> or \<CR\>\<LF\> (optional for the last segment)</span></span>  
  
- <span data-ttu-id="6ddf3-130">フィールド区切り記号が適切であります。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-130">That field delimiters are appropriate</span></span>  
  
- <span data-ttu-id="6ddf3-131">未宣言の Z セグメント (定義済みの 3 文字セグメント タグ) で宣言されたセグメントがないこと</span><span class="sxs-lookup"><span data-stu-id="6ddf3-131">That there are no declared segments (with a defined three-character segment tag) in an undeclared Z segment</span></span>  
  
  <span data-ttu-id="6ddf3-132">本文のスキーマ検証がより広範な次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-132">More extensive schema validation of the body includes the following:</span></span>  
  
- <span data-ttu-id="6ddf3-133">末尾のフィールドの区切り記号</span><span class="sxs-lookup"><span data-stu-id="6ddf3-133">Trailing-field delimiters</span></span>  
  
   <span data-ttu-id="6ddf3-134">ヘッダー MSH セグメントとセグメントの本文</span><span class="sxs-lookup"><span data-stu-id="6ddf3-134">In Header-MSH segment and body segments</span></span>  
  
- <span data-ttu-id="6ddf3-135">Z セグメント</span><span class="sxs-lookup"><span data-stu-id="6ddf3-135">Z segment</span></span>  
  
- <span data-ttu-id="6ddf3-136">XSD でサポートされていると、カスタムのデータ型</span><span class="sxs-lookup"><span data-stu-id="6ddf3-136">XSD-supported and custom data type</span></span>  
  
   <span data-ttu-id="6ddf3-137">サポートされている XSD と XSD 以外の型 (TS (タイムスタンプ)、DT (date)、TM (時間)、および TN (電話番号)</span><span class="sxs-lookup"><span data-stu-id="6ddf3-137">XSD supported and non-XSD types (TS (Time Stamp), DT (date), TM (time), and TN (telephone number)</span></span>  
  
- <span data-ttu-id="6ddf3-138">列挙型</span><span class="sxs-lookup"><span data-stu-id="6ddf3-138">Enumerations</span></span>  
  
   <span data-ttu-id="6ddf3-139">ID (HL7 定義テーブル) とは (ユーザー定義テーブル)</span><span class="sxs-lookup"><span data-stu-id="6ddf3-139">ID (HL7-defined tables) and IS (user-defined tables)</span></span>  
  
- <span data-ttu-id="6ddf3-140">Optionality</span><span class="sxs-lookup"><span data-stu-id="6ddf3-140">Optionality</span></span>  
  
   <span data-ttu-id="6ddf3-141">必須およびオプション</span><span class="sxs-lookup"><span data-stu-id="6ddf3-141">Required and optional</span></span>  
  
- <span data-ttu-id="6ddf3-142">繰り返し</span><span class="sxs-lookup"><span data-stu-id="6ddf3-142">Repetition</span></span>  
  
   <span data-ttu-id="6ddf3-143">セグメントとフィールド</span><span class="sxs-lookup"><span data-stu-id="6ddf3-143">Segment and field</span></span>  
  
- <span data-ttu-id="6ddf3-144">エスケープ シーケンス</span><span class="sxs-lookup"><span data-stu-id="6ddf3-144">Escape sequences</span></span>  
  
   <span data-ttu-id="6ddf3-145">文字エン コード、書式、および文字セット</span><span class="sxs-lookup"><span data-stu-id="6ddf3-145">Encoding characters, formatting, and character sets</span></span>  
  
  <span data-ttu-id="6ddf3-146">有効またはから受信した、または (送信元パーティの逆アセンブラー、アセンブラーの送信先パーティ) の特定のパーティに送信されるすべてのメッセージの概略図の検証を無効にするとします。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-146">You enable or disable schematic validation for all messages received from or sent to a specific party (source party for the disassembler, destination party for the assembler).</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="6ddf3-147"> MSH9.3 メッセージ構造のヘッダー フィールド (2.3.1、2.4、または 2.5)、MSH12 バージョン ID フィールドおよび設定名前空間によって決定される、この処理を直接使用して、HL7 2.X スキーマ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-147"> uses the HL7 2.X schemas directly for this processing, as determined by the MSH9.3 message-structure header field, the MSH12 Version ID field (2.3.1, 2.4, or 2.5), and the namespace setting in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
## <a name="hl7-disassembler-processing"></a><span data-ttu-id="6ddf3-148">HL7 の逆アセンブラーの処理</span><span class="sxs-lookup"><span data-stu-id="6ddf3-148">HL7 Disassembler Processing</span></span>  
 <span data-ttu-id="6ddf3-149">HL7 の逆アセンブラーでは、HL7 メッセージの受信を処理するための XML セグメントに解析します。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-149">The HL7 disassembler parses incoming HL7 messages into XML segments for processing.</span></span> <span data-ttu-id="6ddf3-150">メッセージを解析する際、逆アセンブラーは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-150">As it parses the messages, the disassembler performs the following tasks:</span></span>  
  
-   <span data-ttu-id="6ddf3-151">ハンドルのエスケープ シーケンス</span><span class="sxs-lookup"><span data-stu-id="6ddf3-151">Handles escape sequences</span></span>  
  
-   <span data-ttu-id="6ddf3-152">必須/任意のプロパティのチェックを処理します。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-152">Handles checks of the required/optional properties</span></span>  
  
-   <span data-ttu-id="6ddf3-153">Z セグメントで未定義または予期しないセグメントをハンドルが定義されている (Z セグメントの説明は、次を参照してください。 [Z オブジェクト経由でメッセージをカスタマイズする](../../adapters-and-accelerators/accelerator-hl7/customizing-messages-through-z-objects.md))。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-153">Handles defined segments and undefined or unexpected Z segments (for a description of Z segments, see [Customizing Messages through Z Objects](../../adapters-and-accelerators/accelerator-hl7/customizing-messages-through-z-objects.md)).</span></span>  
  
-   <span data-ttu-id="6ddf3-154">(なる Z セグメントが宣言されていない) インスタンスの末尾に予期しないセグメントを無視します。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-154">Ignores unexpected segments at the end of an instance (which become undeclared Z segments)</span></span>  
  
## <a name="error-reporting"></a><span data-ttu-id="6ddf3-155">[エラー報告]</span><span class="sxs-lookup"><span data-stu-id="6ddf3-155">Error Reporting</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="6ddf3-156"> 標準 HL7 エラー形式では、セグメント、シーケンス、フィールド、およびエラー コードを含むほとんどのエラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-156"> reports most errors in standard HL7 error format, which include the segment, sequence, field, and error code.</span></span> <span data-ttu-id="6ddf3-157">ただし、エラー条件がありますなどすべての使用できるようにする、たとえば、スキーマが存在しない場合。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-157">However, the error condition may be such that not all of these are available, for instance, if no schema is present.</span></span> <span data-ttu-id="6ddf3-158">、このようなケースを処理する[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]代替でエラーが報告できる[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エラー形式。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-158">To handle such cases, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] can report errors in an alternate [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] error format.</span></span> <span data-ttu-id="6ddf3-159">メッセージのエラー セグメントに 2 つの部分が含まれています: 1 つは HL7 エラー、1 つの別名[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エラー。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-159">The error segment in a message includes two parts: one for the HL7 error and one for the alternative [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] error.</span></span>  
  
## <a name="ack-generation"></a><span data-ttu-id="6ddf3-160">確認の生成</span><span class="sxs-lookup"><span data-stu-id="6ddf3-160">ACK Generation</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="6ddf3-161"> 2.X のメッセージの受信確認 (Ack) の次の種類をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-161"> supports the following types of acknowledgments (ACKs) for 2.X messages.</span></span> <span data-ttu-id="6ddf3-162">HL7 両方エラーの種類と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)](代替) エラーの種類が使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-162">Both the HL7 error type and the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] (alternate) error type are used:</span></span>  
  
-   <span data-ttu-id="6ddf3-163">元のメッセージと ACK のマッピング</span><span class="sxs-lookup"><span data-stu-id="6ddf3-163">Mapping original message and ACK</span></span>  
  
-   <span data-ttu-id="6ddf3-164">HL7 の元の確認</span><span class="sxs-lookup"><span data-stu-id="6ddf3-164">HL7 original ACKs</span></span>  
  
-   <span data-ttu-id="6ddf3-165">HL7 の Ack を強化します。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-165">HL7 enhanced ACKs</span></span>  
  
     <span data-ttu-id="6ddf3-166">コミットがそのまま使用し、アプリケーションの同意</span><span class="sxs-lookup"><span data-stu-id="6ddf3-166">Commit Accept and Application Accept</span></span>  
  
-   <span data-ttu-id="6ddf3-167">静的/プロキシの確認</span><span class="sxs-lookup"><span data-stu-id="6ddf3-167">Static/proxy ACK</span></span>  
  
     <span data-ttu-id="6ddf3-168">ACK または NAK</span><span class="sxs-lookup"><span data-stu-id="6ddf3-168">ACK or NAK</span></span>  
  
## <a name="property-promotion"></a><span data-ttu-id="6ddf3-169">プロパティの昇格</span><span class="sxs-lookup"><span data-stu-id="6ddf3-169">Property Promotion</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="6ddf3-170"> 2.X の次のプロパティの昇格をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-170"> supports promoting the following 2.X properties:</span></span>  
  
-   <span data-ttu-id="6ddf3-171">プロパティ スキーマ</span><span class="sxs-lookup"><span data-stu-id="6ddf3-171">Property schema</span></span>  
  
-   <span data-ttu-id="6ddf3-172">MSH ヘッダー スキーマ</span><span class="sxs-lookup"><span data-stu-id="6ddf3-172">MSH-header schema</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6ddf3-173">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6ddf3-173">In This Section</span></span>  
  
-   [<span data-ttu-id="6ddf3-174">HL7 2.X 逆アセンブラーのスキーマ決定</span><span class="sxs-lookup"><span data-stu-id="6ddf3-174">Schema Determination in the HL7 2.X Disassembler</span></span>](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md)  
  
-   [<span data-ttu-id="6ddf3-175">HL7 2.X アセンブラーのスキーマ決定</span><span class="sxs-lookup"><span data-stu-id="6ddf3-175">Schema Determination in the HL7 2.X Assembler</span></span>](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md)  
  
## <a name="see-also"></a><span data-ttu-id="6ddf3-176">参照</span><span class="sxs-lookup"><span data-stu-id="6ddf3-176">See Also</span></span>  
 <span data-ttu-id="6ddf3-177">[メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="6ddf3-177">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 <span data-ttu-id="6ddf3-178">[HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="6ddf3-178">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 [<span data-ttu-id="6ddf3-179">HL7 2.X スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="6ddf3-179">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)