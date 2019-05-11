---
title: 未宣言の Z セグメントの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Z segments, 2.X schemas
- 2.X schemas, undeclared Z segments
- segments, undeclared [Z objects]
- Z objects, undeclared segments
ms.assetid: 8878bc93-1833-4bfc-b80e-305e4144739e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0903945fc9fdae1618f8548660c320187a0a71b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255272"
---
# <a name="handling-undeclared-z-segments"></a><span data-ttu-id="a02e1-102">未宣言の Z セグメントの処理</span><span class="sxs-lookup"><span data-stu-id="a02e1-102">Handling Undeclared Z Segments</span></span>
<span data-ttu-id="a02e1-103">Z セグメントの 2 種類があります: Z セグメントで宣言されていない Z セグメントを宣言します。</span><span class="sxs-lookup"><span data-stu-id="a02e1-103">There are two types of Z segments: declared Z segments and undeclared Z segments.</span></span> <span data-ttu-id="a02e1-104">似ているローカルの目的で使用することで、使用する方法に非常に異なるです。</span><span class="sxs-lookup"><span data-stu-id="a02e1-104">While they are similar in that you use them for local purposes, they are very different in how you use them.</span></span>  
  
 <span data-ttu-id="a02e1-105">メッセージ スキーマ、および Microsoft BizTalk Accelerator for HL7 の宣言された Z セグメントの定義を含める ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])、HL7 標準によって定義されるスキーマと同じように、メッセージの処理に使用します。</span><span class="sxs-lookup"><span data-stu-id="a02e1-105">You include the definition of a declared Z segment in a message schema, and Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses it to process a message, just like a schema defined by the HL7 standard.</span></span> <span data-ttu-id="a02e1-106">未宣言の Z セグメントを定義するスキーマがありません。</span><span class="sxs-lookup"><span data-stu-id="a02e1-106">No schema defines an undeclared Z segment.</span></span> <span data-ttu-id="a02e1-107">メッセージの最後に宣言されていない Z セグメントを含めると[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]スキーマに対してそれを処理することがなく通過します。</span><span class="sxs-lookup"><span data-stu-id="a02e1-107">You include an undeclared Z segment at the end of a message, and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] passes through without processing it against a schema.</span></span> <span data-ttu-id="a02e1-108">パーサーとシリアライザーは検証されません。</span><span class="sxs-lookup"><span data-stu-id="a02e1-108">The parser and serializer do not validate it.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="a02e1-109">バイナリ ラージ オブジェクト (BLOB) として扱われます。</span><span class="sxs-lookup"><span data-stu-id="a02e1-109">treats it as a binary large object (BLOB).</span></span> <span data-ttu-id="a02e1-110">のみ確認[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]はセグメント未宣言の Z で、BLOB に、既存の 3 文字のスキーマのタグが含まれていないことの確認ができます。</span><span class="sxs-lookup"><span data-stu-id="a02e1-110">The only check that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does on an undeclared Z segment is verifying that the BLOB does not include any existing three-character schema tag.</span></span>  
  
 <span data-ttu-id="a02e1-111">3 番目の部分、またはマルチパート メッセージの Z の一部として宣言されていない Z セグメントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a02e1-111">You include the undeclared Z segment as the third part, or Z part, of a multi-part message.</span></span> <span data-ttu-id="a02e1-112">メッセージには、ヘッダー、本文、および Z の一部が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a02e1-112">The message includes the header, the body, and the Z part.</span></span> <span data-ttu-id="a02e1-113">Z の一部では、"Z"文字で始まるセグメント ID を持ちます。</span><span class="sxs-lookup"><span data-stu-id="a02e1-113">The Z part has a segment ID starting with the letter "Z".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a02e1-114">Zpart は、データを常に含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a02e1-114">The Zpart must always contain data.</span></span> <span data-ttu-id="a02e1-115">エラー状態でストリームの結果の null を指定します。</span><span class="sxs-lookup"><span data-stu-id="a02e1-115">Specifying null for the stream results in an error condition.</span></span> <span data-ttu-id="a02e1-116">データが含まれていない場合、Zpart [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Zpart で「空」という単語を挿入します。</span><span class="sxs-lookup"><span data-stu-id="a02e1-116">If no data is included in the Zpart, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] inserts the word "Empty" in the Zpart.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="a02e1-117">コンテキスト プロパティを使用して**ZPartPresent** Z の一部をシリアル化するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="a02e1-117">uses the context property **ZPartPresent** to determine whether to serialize the Z part.</span></span>  
> 
> [!CAUTION]
>  <span data-ttu-id="a02e1-118">Microsoft では、ANSI 文字を含む Zsegment 動作が予測可能な結果を ANSI 文字セットで Zsegments をテストします。</span><span class="sxs-lookup"><span data-stu-id="a02e1-118">Microsoft has tested Zsegments with ANSI character sets, with the result that Zsegment behavior with ANSI characters is predictable.</span></span> <span data-ttu-id="a02e1-119">ただし、Zsegments で他の文字セットを使用してが予期しない動作にあります。</span><span class="sxs-lookup"><span data-stu-id="a02e1-119">However, using other character sets in Zsegments may result in unpredictable behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a02e1-120">参照</span><span class="sxs-lookup"><span data-stu-id="a02e1-120">See Also</span></span>  
 <span data-ttu-id="a02e1-121">[Z オブジェクト HL7 2.X スキーマの拡張](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="a02e1-121">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="a02e1-122">[宣言された Z セグメントの作成](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span><span class="sxs-lookup"><span data-stu-id="a02e1-122">[Creating Declared Z Segments](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span></span>  
 <span data-ttu-id="a02e1-123">[スキーマでカスタム データ型の作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="a02e1-123">[Creating Custom Data Types in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span></span>  
 [<span data-ttu-id="a02e1-124">スキーマでのカスタム テーブルの作成</span><span class="sxs-lookup"><span data-stu-id="a02e1-124">Creating Custom Tables in Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)