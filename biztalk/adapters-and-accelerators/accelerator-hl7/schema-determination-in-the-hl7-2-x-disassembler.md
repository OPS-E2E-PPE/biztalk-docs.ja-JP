---
title: HL7 2.X 逆アセンブラーのスキーマの決定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- header segments [2.X]
- 2.X messages, header segments
- messages, parsing messages
- MSH
- disassembler, parsing messages
- 2.X messages, MSH
ms.assetid: afd45c4c-2feb-44eb-b3bd-49fe114eb893
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fcdd3b0ba6565aff4d401c8e43ae2f86fc37384
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010259"
---
# <a name="schema-determination-in-the-hl7-2x-disassembler"></a><span data-ttu-id="5dc26-102">HL7 2.X 逆アセンブラーのスキーマ決定</span><span class="sxs-lookup"><span data-stu-id="5dc26-102">Schema Determination in the HL7 2.X Disassembler</span></span>
<span data-ttu-id="5dc26-103">HL7 2.X のメッセージには、本文のセグメント数と、省略可能な Z セグメントの後にヘッダー セグメント (MSH) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5dc26-103">HL7 2.X messages contain a header segment (MSH), followed by a number of body segments and an optional number of Z segments.</span></span> <span data-ttu-id="5dc26-104">MSH には、21 のフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5dc26-104">MSH contains 21 fields.</span></span>  
  
 <span data-ttu-id="5dc26-105">メッセージが到着すると、2.X のエンジンを使用して、メッセージ本文を解析するスキーマを決定するヘッダーを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="5dc26-105">When a message arrives, the 2.X engine reads the header to determine the schema to use to parse the message body.</span></span> <span data-ttu-id="5dc26-106">次の一連のイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="5dc26-106">The following sequence of events occurs:</span></span>  
  
1. <span data-ttu-id="5dc26-107">逆アセンブラーが MSH3 の値を読み取ります (送信元パーティ)、次の検証オプションを決定します。</span><span class="sxs-lookup"><span data-stu-id="5dc26-107">The disassembler reads the value of MSH3 (source party) to determine the following validation options:</span></span>  
  
   1.  <span data-ttu-id="5dc26-108">本文の XML の検証を実行するかどうか</span><span class="sxs-lookup"><span data-stu-id="5dc26-108">Whether to perform XML validation for the body</span></span>  
  
   2.  <span data-ttu-id="5dc26-109">本文データのフィールドを入力するカスタム データを検証するかどうか</span><span class="sxs-lookup"><span data-stu-id="5dc26-109">Whether to validate custom data type fields in the body data</span></span>  
  
   3.  <span data-ttu-id="5dc26-110">末尾の本体に区切り記号を許可するかどうか</span><span class="sxs-lookup"><span data-stu-id="5dc26-110">Whether to allow trailing delimiters in the body</span></span>  
  
   4.  <span data-ttu-id="5dc26-111">ボディ スキーマのターゲットの名前空間には (**TargetNS**)</span><span class="sxs-lookup"><span data-stu-id="5dc26-111">What the target namespace of the body schema is (**TargetNS**)</span></span>  
  
2. <span data-ttu-id="5dc26-112">逆アセンブラーは、本文のルート ノード名を確認するには、MSH9 と MSH12 を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="5dc26-112">The disassembler then reads MSH9 and MSH12 to determine the root node name of the body.</span></span> <span data-ttu-id="5dc26-113">アルゴリズムは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5dc26-113">The algorithm is as follows:</span></span>  
  
   ```  
   Body schema type = TargetNS + "#" + MSH9.1 + MSH9.2 + MSH12.1 (with dots removed) + MSH12.2 (or GLO if the value is blank) + MSH12.3 (or DEF if the value is blank)  
   ```  
  
    <span data-ttu-id="5dc26-114">Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 後続のメッセージ ヘッダー内の区切り記号は常に許可します。</span><span class="sxs-lookup"><span data-stu-id="5dc26-114">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) always allows trailing delimiters in a message header.</span></span> <span data-ttu-id="5dc26-115">エンジンは、それぞれの行の最初の 3 つの文字がセグメント識別子を調べます。</span><span class="sxs-lookup"><span data-stu-id="5dc26-115">The engine examines the segment identifier that is the first three characters of each line.</span></span> <span data-ttu-id="5dc26-116">に保持ボディ スキーマを定義するすべてのセグメントの XML を生成します。</span><span class="sxs-lookup"><span data-stu-id="5dc26-116">It keeps on generating XML for all segments that the body schema defines.</span></span> <span data-ttu-id="5dc26-117">未定義のセグメントを見つけたときに、そのセグメントを Z セグメントとして扱います。</span><span class="sxs-lookup"><span data-stu-id="5dc26-117">When it encounters an undefined segment, it treats that segment as a Z segment.</span></span> <span data-ttu-id="5dc26-118">その時点からは、未定義のすべてのセグメントは、メッセージの Z の一部を構成します。</span><span class="sxs-lookup"><span data-stu-id="5dc26-118">From that point on, all undefined segments constitute the Z part of the message.</span></span> <span data-ttu-id="5dc26-119">[次へ] の MSH では、このメッセージの終了をマークします。</span><span class="sxs-lookup"><span data-stu-id="5dc26-119">The next MSH marks the end of this message.</span></span> <span data-ttu-id="5dc26-120">バッチ メッセージの場合、[次へ] MSH または BTS (バッチ トレーラー セグメント タグ) は、メッセージの最後をマークします。</span><span class="sxs-lookup"><span data-stu-id="5dc26-120">For batch messages, the next MSH or BTS (the batch trailer segment tag) marks the end of a message.</span></span> <span data-ttu-id="5dc26-121">Z セグメントには、スキーマで宣言されているあるセグメントのみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5dc26-121">A Z segment can only contain segments that are undeclared in a schema.</span></span> <span data-ttu-id="5dc26-122">宣言されたセグメントが発生するエラーになります。</span><span class="sxs-lookup"><span data-stu-id="5dc26-122">It is an error to encounter a declared segment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dc26-123">参照</span><span class="sxs-lookup"><span data-stu-id="5dc26-123">See Also</span></span>  
 <span data-ttu-id="5dc26-124">[メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="5dc26-124">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="5dc26-125">BTAHL72X フラット ファイル処理</span><span class="sxs-lookup"><span data-stu-id="5dc26-125">BTAHL72X Flat File Processing</span></span>](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)