---
title: "位置指定レコードにおけるフィールド位置の仕様 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33c2eee3-ec30-46c5-a143-a3d2e2f265a6
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91a253c76e8f3394897514716978e1902cf2e3d8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="specification-of-field-positions-within-positional-records"></a><span data-ttu-id="42608-102">位置指定レコードにおけるフィールド位置の仕様</span><span class="sxs-lookup"><span data-stu-id="42608-102">Specification of Field Positions within Positional Records</span></span>
<span data-ttu-id="42608-103">位置指定レコードを定義するには、そのレコードに含まれるフィールドの位置情報と長さ情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42608-103">To define a positional record, you must provide information about the positions and lengths of the fields within that record.</span></span> <span data-ttu-id="42608-104">レコードにサブレコードが含まれている場合、サブレコードに含まれるフィールドの位置と長さが集計されて、上位レコードの情報が生成されます。</span><span class="sxs-lookup"><span data-stu-id="42608-104">If the record contains subrecords, the positions and lengths of the fields in the subrecord are rolled up to contribute to the information about the containing record.</span></span>  
  
 <span data-ttu-id="42608-105">指定した値の合計、**位置指定オフセット**と**位置指定値**、特定のプロパティ**フィールド要素**または**フィールド属性**ノードが、対応するフィールドに割り当てられる文字数を決定します。</span><span class="sxs-lookup"><span data-stu-id="42608-105">The sum of the values you specify for the **Positional Offset** and **Positional Length** properties for a particular **Field Element** or **Field Attribute** node determines the number of characters dedicated to the corresponding field.</span></span> <span data-ttu-id="42608-106">レコードおよびそのサブレコードに含まれるすべてのフィールドについて、このような一連の合計値を取得することによって各フィールドの境界が決定されます。</span><span class="sxs-lookup"><span data-stu-id="42608-106">The series of these sums across all of the fields in the record and any of its subrecords determine the boundaries of the fields in the records.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42608-107">ときに、**カウント位置 (バイト単位)**のプロパティ、**スキーマ**に設定されているノード**はい**、**位置指定値**と**位置のオフセット**プロパティは、文字ではなくバイト数を指定します。</span><span class="sxs-lookup"><span data-stu-id="42608-107">When the **Count Positions In Bytes** property of the **Schema** node is set to **Yes**, the **Positional Length** and **Position Offset** properties specify bytes rather than characters.</span></span>  

<span data-ttu-id="42608-108">これらのプロパティの詳細を参照してください[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="42608-108">See more details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="positional-offset-property"></a><span data-ttu-id="42608-109">"位置指定オフセット" プロパティ</span><span class="sxs-lookup"><span data-stu-id="42608-109">Positional Offset property</span></span>  
 <span data-ttu-id="42608-110">フラット ファイル逆アセンブラーは、フラット ファイル インスタンス メッセージを変換する同等の XML インスタンス メッセージには、ときに、指定した値、**位置指定オフセット**プロパティは無視される文字 (またはバイト数) の数を定義します。インスタンス メッセージ内の位置にある経由でスキップされました。</span><span class="sxs-lookup"><span data-stu-id="42608-110">When the flat file disassembler is converting a flat file instance message into an equivalent XML instance message, the value you specify for the **Positional Offset** property defines a number of characters (or bytes) that are ignored and skipped over at that position in the instance message.</span></span> <span data-ttu-id="42608-111">つまり、その開始位置と長さで発生した情報 (後者で指定された、**位置指定オフセット**プロパティ) で、フラット ファイル インスタンス メッセージはコピーされません、メッセージの XML バージョンにします。</span><span class="sxs-lookup"><span data-stu-id="42608-111">In other words, any information occurring at that starting position and length (the latter as specified by the **Positional Offset** property) in the flat file instance message will not be copied into the XML version of the message.</span></span>  
  
 <span data-ttu-id="42608-112">フラット ファイル アセンブラーは、変換すると、XML インスタンス メッセージを同等のフラット ファイル インスタンス メッセージに、値を指定するため、**位置指定オフセット**で埋められた文字 (またはバイト数) の数を定義します。作成中のフラット ファイル インスタンス メッセージ内の開始位置にスペース文字。</span><span class="sxs-lookup"><span data-stu-id="42608-112">When the flat file assembler is converting an XML instance message into an equivalent flat file instance message, the value you specify for the **Positional Offset** property defines a number of characters (or bytes) that are filled with space characters at that starting position within the flat file instance message being created.</span></span> <span data-ttu-id="42608-113">オフセット位置に挿入される文字としては、常にスペースが使用されます。この文字は変更できません。</span><span class="sxs-lookup"><span data-stu-id="42608-113">The space character is always used to fill offset positions; the character used is not configurable.</span></span>  
  
 <span data-ttu-id="42608-114">**位置指定オフセット**プロパティは、位置指定レコードの内容を解釈するための柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="42608-114">The **Positional Offset** property provides flexibility for interpreting the contents of positional records.</span></span> <span data-ttu-id="42608-115">このプロパティを使用すると、0 以外の値に設定されたフィールドの前にある固定長データを無視できます。</span><span class="sxs-lookup"><span data-stu-id="42608-115">Essentially, this property allows you to ignore any fixed length data that precedes the field for which it is set to a nonzero value.</span></span> <span data-ttu-id="42608-116">無視できる固定長データとしては、XML からフラット ファイルへの変換時に、フラット ファイル インスタンス メッセージに含める必要のないフィールドや定数データ (フィールドに関連付けられたタグなど) などがあります。</span><span class="sxs-lookup"><span data-stu-id="42608-116">That fixed length data might be one or more entire fields of data or some type of constant data, such as a tag associated with the field, that does not need to be included in the XML equivalent of the flat file instance message.</span></span> <span data-ttu-id="42608-117">詳細については、次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42608-117">For more information, see the example that follows.</span></span>  
  
## <a name="positional-length-property"></a><span data-ttu-id="42608-118">"位置指定値" プロパティ</span><span class="sxs-lookup"><span data-stu-id="42608-118">Positional Length property</span></span>  
 <span data-ttu-id="42608-119">フラット ファイル逆アセンブラーは、フラット ファイル インスタンス メッセージを変換する同等の XML インスタンス メッセージには、ときに、指定した値、**位置指定値**プロパティである文字 (またはバイト数) の数を定義します。インスタンス メッセージ内の位置にあるフィールドに関連付けられました。</span><span class="sxs-lookup"><span data-stu-id="42608-119">When the flat file disassembler is converting a flat file instance message into an equivalent XML instance message, the value you specify for the **Positional Length** property defines the number of characters (or bytes) that are associated with the field at that position in the instance message.</span></span> <span data-ttu-id="42608-120">フラット ファイル インスタンス メッセージ内の位置と長さの開始と、関連付けられているによって提供される追加の情報に従って、フィールド内のデータで構成される対応する情報**Justification**と**埋め込み文字**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="42608-120">The information occurring at that starting position and length in the flat file instance message constitutes the data in the field, subject to the additional information provided by the associated **Justification** and **Pad Character** properties.</span></span> <span data-ttu-id="42608-121">妥当性とフィールドの埋め込みに関する概念の詳細については、次を参照してください。[フィールドの位置揃え](../core/field-justification.md)と[フィールド Padding](../core/field-padding.md)です。</span><span class="sxs-lookup"><span data-stu-id="42608-121">For more conceptual information about justification and field padding, see [Field Justification](../core/field-justification.md) and [Field Padding](../core/field-padding.md).</span></span>  
  
 <span data-ttu-id="42608-122">フラット ファイル アセンブラーは、変換すると、XML インスタンス メッセージを同等のフラット ファイル インスタンス メッセージに、指定した値、**位置指定値**文字 (またはバイト数) の数を定義するプロパティの使用そのフィールドに関連付けられているデータを書き込んでいます。</span><span class="sxs-lookup"><span data-stu-id="42608-122">When the flat file assembler is converting an XML instance message into an equivalent flat file instance message, the value you specify for the **Positional Length** property defines a number of characters (or bytes) available for writing the data associated with that field.</span></span> <span data-ttu-id="42608-123">データの文字数が、指定されたフィールド長よりも少ない場合、適切な埋め込み文字数で長さの違いが調整されます。</span><span class="sxs-lookup"><span data-stu-id="42608-123">If there are fewer data characters than the specified length of the field, the relevant pad character is used to fill up the difference.</span></span> <span data-ttu-id="42608-124">フィールドの指定された長さより多くのデータの文字がある場合、先頭または末尾のデータは切り捨てられますの設定に基づいて、 **Justification**プロパティ、フラット ファイル インスタンス メッセージが含まれていません構成されます。</span><span class="sxs-lookup"><span data-stu-id="42608-124">If there are more data characters than the specified length of the field, the beginning or end of the data is truncated based on the setting of the **Justification** property and not included in the flat file instance message being constructed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42608-125">左揃えデータの場合、右端の部分が切り詰められます (破棄される)。</span><span class="sxs-lookup"><span data-stu-id="42608-125">The trailing portion of left-aligned data is truncated and discarded.</span></span> <span data-ttu-id="42608-126">右揃えデータの場合、左端の部分が切り詰められます (破棄される)。</span><span class="sxs-lookup"><span data-stu-id="42608-126">The leading portion of right-aligned data is truncated and discarded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42608-127">例</span><span class="sxs-lookup"><span data-stu-id="42608-127">Example</span></span>  
 <span data-ttu-id="42608-128">レコードのフィールドが、次のように定義されているとします。</span><span class="sxs-lookup"><span data-stu-id="42608-128">Consider the following field definitions for a record.</span></span>  
  
|<span data-ttu-id="42608-129">フィールド ノード名</span><span class="sxs-lookup"><span data-stu-id="42608-129">Field node name</span></span>|<span data-ttu-id="42608-130">Offset</span><span class="sxs-lookup"><span data-stu-id="42608-130">Offset</span></span>|<span data-ttu-id="42608-131">長さ</span><span class="sxs-lookup"><span data-stu-id="42608-131">Length</span></span>|<span data-ttu-id="42608-132">埋め込み文字</span><span class="sxs-lookup"><span data-stu-id="42608-132">Pad Character</span></span>|<span data-ttu-id="42608-133">根拠</span><span class="sxs-lookup"><span data-stu-id="42608-133">Justification</span></span>|  
|---------------------|------------|------------|-------------------|-------------------|  
|<span data-ttu-id="42608-134">Field1</span><span class="sxs-lookup"><span data-stu-id="42608-134">Field1</span></span>|<span data-ttu-id="42608-135">0</span><span class="sxs-lookup"><span data-stu-id="42608-135">0</span></span>|<span data-ttu-id="42608-136">6</span><span class="sxs-lookup"><span data-stu-id="42608-136">6</span></span>|<span data-ttu-id="42608-137">既定 (スペース)</span><span class="sxs-lookup"><span data-stu-id="42608-137">Default (space)</span></span>|<span data-ttu-id="42608-138">Left</span><span class="sxs-lookup"><span data-stu-id="42608-138">Left</span></span>|  
|<span data-ttu-id="42608-139">Field2</span><span class="sxs-lookup"><span data-stu-id="42608-139">Field2</span></span>|<span data-ttu-id="42608-140">0</span><span class="sxs-lookup"><span data-stu-id="42608-140">0</span></span>|<span data-ttu-id="42608-141">4</span><span class="sxs-lookup"><span data-stu-id="42608-141">4</span></span>|*|<span data-ttu-id="42608-142">Right</span><span class="sxs-lookup"><span data-stu-id="42608-142">Right</span></span>|  
|<span data-ttu-id="42608-143">Field3</span><span class="sxs-lookup"><span data-stu-id="42608-143">Field3</span></span>|<span data-ttu-id="42608-144">2</span><span class="sxs-lookup"><span data-stu-id="42608-144">2</span></span>|<span data-ttu-id="42608-145">6</span><span class="sxs-lookup"><span data-stu-id="42608-145">6</span></span>|*|<span data-ttu-id="42608-146">Left</span><span class="sxs-lookup"><span data-stu-id="42608-146">Left</span></span>|  
|<span data-ttu-id="42608-147">Field4</span><span class="sxs-lookup"><span data-stu-id="42608-147">Field4</span></span>|<span data-ttu-id="42608-148">4</span><span class="sxs-lookup"><span data-stu-id="42608-148">4</span></span>|<span data-ttu-id="42608-149">6</span><span class="sxs-lookup"><span data-stu-id="42608-149">6</span></span>|<span data-ttu-id="42608-150">既定 (スペース)</span><span class="sxs-lookup"><span data-stu-id="42608-150">Default (space)</span></span>|<span data-ttu-id="42608-151">Right</span><span class="sxs-lookup"><span data-stu-id="42608-151">Right</span></span>|  
  
 <span data-ttu-id="42608-152">また、これらのフィールド定義を持つレコードの開始位置から、次のような文字列を挿入するとします (1 行目は文字の位置を示しています)。</span><span class="sxs-lookup"><span data-stu-id="42608-152">And the following stream of characters is encountered at the starting point of a record with these field definitions (the first line is for counting character positions).</span></span>  
  
```  
123456789012345678901234567890123456789012345678901234567890  
abc   **12345678**skip  here  
```  
  
 <span data-ttu-id="42608-153">このサンプル レコード データにこれらのフィールド定義を適用した場合、フラット ファイル逆アセンブラーは、次のような XML インスタンス メッセージを生成します (太字部分はデータ)。</span><span class="sxs-lookup"><span data-stu-id="42608-153">When these field definitions are applied to this sample record data, the flat file disassembler produces the following XML equivalent (with the data shown in bold type).</span></span>  
  
```  
<Field1>abc</Field1>  
<Field2>12</Field2>  
<Field3>5678</Field3>  
<Field4>here</Field4>  
```  
  
 <span data-ttu-id="42608-154">次に、このデータが具体的にどのように解析されるかを説明します。</span><span class="sxs-lookup"><span data-stu-id="42608-154">The following observations are relevant to how this data is parsed:</span></span>  
  
-   <span data-ttu-id="42608-155">Field1 に関連付けられている文字 (長さ 6、オフセットなし)、"`abc` "、XML では、空白文字は Field1 の (既定値) の埋め込み文字と Field1 が左揃えとして定義されているため、スペースは含まれません。</span><span class="sxs-lookup"><span data-stu-id="42608-155">The characters associated with Field1 (length 6 with no offset) are "`abc` ", but the spaces are not included in the XML because the space character is the (default) pad character for Field1 and Field1 is defined as left-aligned.</span></span>  
  
-   <span data-ttu-id="42608-156">Field2 (長さ 4、オフセットなし) に関連付けられる文字は "`**12`" ですが、XML にアスタリスクは追加されません。Field2 ではアスタリスクが埋め込み文字であり、右揃えとして定義されているためです。</span><span class="sxs-lookup"><span data-stu-id="42608-156">The characters associated with Field2 (length 4 with no offset) are "`**12`", but the asterisks are not included in the XML because the asterisk character is the pad character defined for Field2 and Field2 is defined as right-aligned.</span></span>  
  
-   <span data-ttu-id="42608-157">Field3 (長さ 6、オフセット 2) に関連付けられる文字は "`345678**`" ですが、オフセットの関係上、XML に 3 と 4 は追加されません。</span><span class="sxs-lookup"><span data-stu-id="42608-157">The characters associated with Field3 (length 6 plus an offset of 2) are "`345678**`", but the 3 and 4 are not included in the XML because of the offset.</span></span> <span data-ttu-id="42608-158">また、XML にアスタリスクは追加されません。Field3 ではアスタリスクが埋め込み文字であり、左揃えとして定義されているためです。</span><span class="sxs-lookup"><span data-stu-id="42608-158">The asterisks are also not included in the XML because the asterisk character is the pad character defined for Field2 and Field2 is defined as left-aligned.</span></span>  
  
-   <span data-ttu-id="42608-159">Field4 (長さ 6、オフセット 4) に関連付けられる文字は "`skip  here`" ですが、オフセットの関係上、XML に "`skip`" は追加されません。</span><span class="sxs-lookup"><span data-stu-id="42608-159">The characters associated with Field4 (length 6 plus an offset of 4) are "`skip  here`", but the character sequence "`skip`" is not included in the XML because of the offset.</span></span> <span data-ttu-id="42608-160">また、XML に 2 つのスペースは追加されません。Field4 ではスペースが既定の埋め込み文字であり、右揃えとして定義されているためです。</span><span class="sxs-lookup"><span data-stu-id="42608-160">The two space characters are also not included in the XML because the space character is the (default) pad character for Field4 and Field4 is defined as right-aligned.</span></span>  
  
 <span data-ttu-id="42608-161">2 つの例外を除き、同じフラット ファイル データを生成する場合、この例では、フラット ファイル逆アセンブラーによって生成される XML は、同じフィールド定義を使用して、フラット ファイル アセンブラーに渡される、: 破棄されたオフセット シーケンス 34 スキップは、空白文字で埋められますと(で示された、`^`データの次の行の文字)。</span><span class="sxs-lookup"><span data-stu-id="42608-161">If the XML produced by the flat file disassembler in this example is passed to the flat file assembler using the same field definitions, the same flat file data is produced, with two exceptions: the discarded offset sequences 34 and skip are filled with space characters (indicated with the `^` character in the line following the data).</span></span>  
  
```  
123456789012345678901234567890123456789012345678901234567890  
abc   **12  5678**      here  
          ^^      ^^^^  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="42608-162">参照</span><span class="sxs-lookup"><span data-stu-id="42608-162">See Also</span></span>  
-  [<span data-ttu-id="42608-163">フィールドに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="42608-163">Field Considerations</span></span>](../core/field-considerations.md)    
-  [<span data-ttu-id="42608-164">フィールドの位置揃え</span><span class="sxs-lookup"><span data-stu-id="42608-164">Field Justification</span></span>](../core/field-justification.md)   
-  [<span data-ttu-id="42608-165">フィールドの埋め込み</span><span class="sxs-lookup"><span data-stu-id="42608-165">Field Padding</span></span>](../core/field-padding.md)   
- <span data-ttu-id="42608-166">詳細については、次のプロパティで[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span><span class="sxs-lookup"><span data-stu-id="42608-166">More info on the following properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span></span>  
    - <span data-ttu-id="42608-167">位置のカウント (バイト) (フラット ファイル スキーマのノード プロパティ)</span><span class="sxs-lookup"><span data-stu-id="42608-167">Count Positions In Bytes (Node Property of Flat File Schemas)</span></span>  
    - <span data-ttu-id="42608-168">位置揃え (フラット ファイル スキーマのノード プロパティ)</span><span class="sxs-lookup"><span data-stu-id="42608-168">Justification (Node Property of Flat File Schemas)</span></span>  
    - <span data-ttu-id="42608-169">埋め込み文字 (フラット ファイル スキーマのノード プロパティ)</span><span class="sxs-lookup"><span data-stu-id="42608-169">Pad Character (Node Property of Flat File Schemas)</span></span> 
    - <span data-ttu-id="42608-170">位置指定オフセット (フラット ファイル スキーマのノード プロパティ)</span><span class="sxs-lookup"><span data-stu-id="42608-170">Positional Offset (Node Property of Flat File Schemas)</span></span>
    - <span data-ttu-id="42608-171">位置指定値 (フラット ファイル スキーマのノード プロパティ)</span><span class="sxs-lookup"><span data-stu-id="42608-171">Positional Length (Node Property of Flat File Schemas)</span></span>