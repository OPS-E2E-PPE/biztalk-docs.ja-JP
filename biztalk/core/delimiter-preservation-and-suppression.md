---
title: 区切り記号の保存および非表示 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30985b94-625e-411a-8137-1c129bc197bf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cc3fc8f6ba55766d7650d7acb6693487798fa40
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352239"
---
# <a name="delimiter-preservation-and-suppression"></a><span data-ttu-id="3d113-102">区切り記号の保存および非表示</span><span class="sxs-lookup"><span data-stu-id="3d113-102">Delimiter Preservation and Suppression</span></span>

## <a name="overview"></a><span data-ttu-id="3d113-103">概要</span><span class="sxs-lookup"><span data-stu-id="3d113-103">Overview</span></span>
<span data-ttu-id="3d113-104">区切られたレコードに適用される 2 つのプロパティがあります。**空のデータの区切り記号の保存**と**末尾の区切り記号を抑制する**します。</span><span class="sxs-lookup"><span data-stu-id="3d113-104">There are two properties that apply to delimited records: **Preserve Delimiter For Empty Data** and **Suppress Trailing Delimiters**.</span></span> <span data-ttu-id="3d113-105">これらのプロパティを使用すると、フラット ファイル アセンブラーが存在しないデータと末尾の区切り記号に関連付けられている区切り記号を処理する方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="3d113-105">Use these properties to control how the flat file assembler handles delimiters associated with nonexistent data and trailing delimiters.</span></span> <span data-ttu-id="3d113-106">設定すると、**空のデータの区切り記号を保持する**プロパティを**はい**(既定の設定では、) に変換されたフラット ファイル メッセージ内の区切り記号が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3d113-106">When you set the **Preserve Delimiter For Empty Data** property to **Yes** (which is the default setting), delimiters are included in the translated flat file message for:</span></span>  
  
- <span data-ttu-id="3d113-107">データのないフィールドです。</span><span class="sxs-lookup"><span data-stu-id="3d113-107">Fields without data.</span></span>  
  
- <span data-ttu-id="3d113-108">直下のレコードに関連付けられているタグがないデータなし。</span><span class="sxs-lookup"><span data-stu-id="3d113-108">Immediately subordinate records without data that do not have a tag associated with them.</span></span>  
  
  <span data-ttu-id="3d113-109">設定すると、**空のデータの区切り記号を保持する**プロパティを**いいえ**、区切り記号は、レコードおよびフィールドがデータなしの変換されたフラット ファイルには含まれません。</span><span class="sxs-lookup"><span data-stu-id="3d113-109">When you set the **Preserve Delimiter For Empty Data** property to **No**, delimiters are not included in the translated flat file for records and fields without data.</span></span> <span data-ttu-id="3d113-110">さらの設定に関係なく、**空のデータの区切り記号を保持する**プロパティ、タグが定義されているデータなしの直下のレコードに変換されたフラット ファイル メッセージ内の区切り記号は含まれません。</span><span class="sxs-lookup"><span data-stu-id="3d113-110">Further, regardless of the setting of the **Preserve Delimiter For Empty Data** property, delimiters will not be included in the translated flat file message for immediately subordinate records without data for which a tag is defined.</span></span>  
  
  <span data-ttu-id="3d113-111">設定すると、**末尾の区切り記号の抑制**プロパティを**いいえ**(既定の設定では、)、変換されたフラット ファイル メッセージで 1 つまたは複数の末尾の区切り記号を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3d113-111">When you set the **Suppress Trailing Delimiters** property to **No** (which is the default setting), one or more trailing delimiters may be included in the translated flat file message.</span></span> <span data-ttu-id="3d113-112">設定すると、**末尾の区切り記号の非表示**プロパティを**はい**、末尾の区切り記号は、変換されたフラット ファイル メッセージに含まれません。</span><span class="sxs-lookup"><span data-stu-id="3d113-112">When you set the **Suppress Trailing Delimiters** property to **Yes**, trailing delimiters are not included in the translated flat file message.</span></span>  

## <a name="special-scenarios"></a><span data-ttu-id="3d113-113">特殊なシナリオ</span><span class="sxs-lookup"><span data-stu-id="3d113-113">Special scenarios</span></span>  
 <span data-ttu-id="3d113-114">設定で、動作が原因となったいくつかの特殊なケースがある、**空のデータの区切り記号を保持する**と**末尾の区切り記号の非表示**プロパティが競合することができます。</span><span class="sxs-lookup"><span data-stu-id="3d113-114">There are some special cases where the behaviors caused by the settings of the **Preserve Delimiter For Empty Data** and **Suppress Trailing Delimiters** properties can conflict.</span></span> <span data-ttu-id="3d113-115">このような場合、後者のプロパティに関連付けられた動作**末尾の区切り記号の抑制**が優先されます。</span><span class="sxs-lookup"><span data-stu-id="3d113-115">In such cases, the behaviors associated with the latter property, **Suppress Trailing Delimiters**, will take precedence.</span></span> <span data-ttu-id="3d113-116">さらに、これら 2 つのプロパティ用に選択した設定との間の潜在的な競合について、その場所する警告がいくつかの特殊なケースがあります。</span><span class="sxs-lookup"><span data-stu-id="3d113-116">Further, there are some special cases where you will be warned about potential conflicts between the settings you have chosen for these two properties.</span></span>  
  
 <span data-ttu-id="3d113-117">たとえば、**レコード**次のプロパティ値で定義されたノード。</span><span class="sxs-lookup"><span data-stu-id="3d113-117">For example, consider a **Record** node defined with the following property values:</span></span>  
  
- <span data-ttu-id="3d113-118">ノード名が myrec であります。</span><span class="sxs-lookup"><span data-stu-id="3d113-118">Node Name is MyRec</span></span>  
  
- <span data-ttu-id="3d113-119">タグ識別子が Rec</span><span class="sxs-lookup"><span data-stu-id="3d113-119">Tag Identifier is Rec</span></span>  
  
- <span data-ttu-id="3d113-120">子区切り記号は、</span><span class="sxs-lookup"><span data-stu-id="3d113-120">Child Delimiter is ,</span></span>  
  
- <span data-ttu-id="3d113-121">子の順序が挿入辞です。</span><span class="sxs-lookup"><span data-stu-id="3d113-121">Child Order is Infix</span></span>  
  
  <span data-ttu-id="3d113-122">5 つを格納する定義済みおよび**フィールド要素**ノードで次の名前 (可能性もあります**フィールド属性**ノードまたは下位**レコード**ノード)。</span><span class="sxs-lookup"><span data-stu-id="3d113-122">And defined to contain five **Field Element** nodes with the following names (they could also be **Field Attribute** nodes or subordinate **Record** nodes):</span></span>  
  
- <span data-ttu-id="3d113-123">FieldElem1</span><span class="sxs-lookup"><span data-stu-id="3d113-123">FieldElem1</span></span>  
  
- <span data-ttu-id="3d113-124">FieldElem2</span><span class="sxs-lookup"><span data-stu-id="3d113-124">FieldElem2</span></span>  
  
- <span data-ttu-id="3d113-125">FieldElem3</span><span class="sxs-lookup"><span data-stu-id="3d113-125">FieldElem3</span></span>  
  
- <span data-ttu-id="3d113-126">FieldElem4</span><span class="sxs-lookup"><span data-stu-id="3d113-126">FieldElem4</span></span>  
  
- <span data-ttu-id="3d113-127">FieldElem5</span><span class="sxs-lookup"><span data-stu-id="3d113-127">FieldElem5</span></span>  
  
  <span data-ttu-id="3d113-128">主に空のこれを表す XML フラグメントを次に、想定**レコード**ノードは、フラット ファイル アセンブラーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="3d113-128">Next, assume that the following mainly empty XML fragment, representing this **Record** node, is passed to the flat file assembler.</span></span>  
  
```  
<MyRec>  
    <FieldElem1 />  
    <FieldElem2 />  
    <FieldElem3>Val</FieldElem3>  
    <FieldElem4 />  
    <FieldElem5 />  
</MyRec>  
  
```  
  
 <span data-ttu-id="3d113-129">次の表は、生成される出力と関連付けられている追加のプロパティごとに異なる設定に基づいて、関連するスキーマ ノードの要件の設定、**空のデータの区切り記号を保持する**(PDFED) と**末尾の区切り記号の抑制**(STD) プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3d113-129">The following table shows the output produced, and the associated additional property setting requirements for the relevant schema nodes, based on different settings for the **Preserve Delimiter For Empty Data** (PDFED) and **Suppress Trailing Delimiters** (STD) properties.</span></span>  
  
|<span data-ttu-id="3d113-130">PDFED 設定</span><span class="sxs-lookup"><span data-stu-id="3d113-130">PDFED setting</span></span>|<span data-ttu-id="3d113-131">STD 設定</span><span class="sxs-lookup"><span data-stu-id="3d113-131">STD setting</span></span>|<span data-ttu-id="3d113-132">[出力]</span><span class="sxs-lookup"><span data-stu-id="3d113-132">Output</span></span>|<span data-ttu-id="3d113-133">その他のノード要件</span><span class="sxs-lookup"><span data-stu-id="3d113-133">Additional node requirements</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="3d113-134">はい</span><span class="sxs-lookup"><span data-stu-id="3d113-134">Yes</span></span>|<span data-ttu-id="3d113-135">いいえ</span><span class="sxs-lookup"><span data-stu-id="3d113-135">No</span></span>|<span data-ttu-id="3d113-136">Rec、、、、および Val</span><span class="sxs-lookup"><span data-stu-id="3d113-136">Rec,,,Val,,</span></span>|<span data-ttu-id="3d113-137">[なし] :</span><span class="sxs-lookup"><span data-stu-id="3d113-137">None.</span></span>|  
|<span data-ttu-id="3d113-138">いいえ</span><span class="sxs-lookup"><span data-stu-id="3d113-138">No</span></span>|<span data-ttu-id="3d113-139">はい</span><span class="sxs-lookup"><span data-stu-id="3d113-139">Yes</span></span>|<span data-ttu-id="3d113-140">推奨値、Val</span><span class="sxs-lookup"><span data-stu-id="3d113-140">Rec,Val</span></span>|<span data-ttu-id="3d113-141">すべて**フィールド要素**ノードは省略可能として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d113-141">All **Field Element** nodes must be configured as optional.</span></span>|  
|<span data-ttu-id="3d113-142">はい</span><span class="sxs-lookup"><span data-stu-id="3d113-142">Yes</span></span>|<span data-ttu-id="3d113-143">はい</span><span class="sxs-lookup"><span data-stu-id="3d113-143">Yes</span></span>|<span data-ttu-id="3d113-144">推奨値、Val</span><span class="sxs-lookup"><span data-stu-id="3d113-144">Rec,,,Val</span></span>|<span data-ttu-id="3d113-145">という名前のノード**FieldElem4**と**FieldElem5**オプションとして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d113-145">Nodes named **FieldElem4** and **FieldElem5** must be configured as optional.</span></span>|  
|<span data-ttu-id="3d113-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="3d113-146">No</span></span>|<span data-ttu-id="3d113-147">いいえ</span><span class="sxs-lookup"><span data-stu-id="3d113-147">No</span></span>|<span data-ttu-id="3d113-148">推奨値、Val、および</span><span class="sxs-lookup"><span data-stu-id="3d113-148">Rec,Val,,</span></span>|<span data-ttu-id="3d113-149">すべて**フィールド要素**ノードは省略可能として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d113-149">All **Field Element** nodes must be configured as optional.</span></span>|  
  
 <span data-ttu-id="3d113-150">これらのプロパティ設定が区切り記号が必要がありますか、保持されませんまたは抑制するか、同じスキーマを使用してシリアル化されたフラット ファイル データを解析できない可能性がある、警告メッセージことを指定する場合は、次の 2 つのケースで発行されます。</span><span class="sxs-lookup"><span data-stu-id="3d113-150">When these property settings specify that delimiters should either not be preserved or should be suppressed, a message warning that it might not be possible to parse the serialized flat file data using the same schema will be issued in the following two cases:</span></span>  
  
-   <span data-ttu-id="3d113-151">ときに、**レコード**対象のノード、**空のデータの区切り記号を保持する**プロパティに設定されて**いいえ**と**抑制末尾の区切り記号**プロパティに設定されて**はい**、それぞれ、下位が含まれています**フィールド要素**ノード、**フィールド属性**ノード、または**レコード**のタグが指定されていないノード。</span><span class="sxs-lookup"><span data-stu-id="3d113-151">When the **Record** node for which the **Preserve Delimiter For Empty Data** property is set to **No** and/or the **Suppress Trailing Delimiters** property is set to **Yes**, respectively, contains subordinate **Field Element** nodes, **Field Attribute** nodes, or **Record** nodes for which no tag is specified.</span></span>  
  
-   <span data-ttu-id="3d113-152">ときに従属要素**フィールド要素**ノード、**フィールド属性**ノード、および**レコード**をオプションにする対象のタグが指定されていないノードが構成されていません (設定して、**Min Occurs**プロパティを 0 に設定)、スキーマにします。</span><span class="sxs-lookup"><span data-stu-id="3d113-152">When the subordinate **Field Element** nodes, **Field Attribute** nodes, and **Record** nodes for which no tag is specified are not configured to be optional (by setting the **Min Occurs** property set to zero) in the schema.</span></span> <span data-ttu-id="3d113-153">ときに、**末尾の区切り記号の非表示**プロパティに設定されて**はい**最後にのみこのような下位ノードが「省略可能として構成する必要。</span><span class="sxs-lookup"><span data-stu-id="3d113-153">When the **Suppress Trailing Delimiters** property is set to **Yes**, only the last such subordinate nodes need to be configured as optional.</span></span> <span data-ttu-id="3d113-154">ときに、**空のデータの区切り記号を保持する**プロパティに設定されて**いいえ**、すべての末尾の下位ノードが「省略可能として構成する必要です。</span><span class="sxs-lookup"><span data-stu-id="3d113-154">When the **Preserve Delimiter For Empty Data** property is set to **No**, all trailing subordinate nodes need to be configured as optional.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d113-155">XML 要素は、(おそらく省略可能) に関連付けられているときに区切り記号は常に保持**レコード**、**フィールド要素**、または**フィールド属性**ノードがまったくないです。レコードが不足している省略可能なフィールドに依存する場合を除く、ビジネス ドキュメントの XML 表現。</span><span class="sxs-lookup"><span data-stu-id="3d113-155">Delimiters are always preserved when the XML element associated with a (presumably optional) **Record**, **Field Element**, or **Field Attribute** node are entirely missing from the XML representation of the business document except when a Record follows a missing optional Field.</span></span> <span data-ttu-id="3d113-156">言い換えると、データとその周囲の XML タグが両方ともがない、対応する区切り記号は常に含まれます、ビジネス ドキュメントのフラット ファイル表記でします。</span><span class="sxs-lookup"><span data-stu-id="3d113-156">In other words, when the data and its surrounding XML tags are both missing, the corresponding delimiter is always included in the flat file representation of the business document.</span></span>  
  
 <span data-ttu-id="3d113-157">不足しているフィールド要素の直後に続く 2 つのフィールド要素に子レコードを含めるスキーマを変更します。</span><span class="sxs-lookup"><span data-stu-id="3d113-157">Now change the schema to include a child record with two Field Element immediately following a missing Field Element.</span></span> <span data-ttu-id="3d113-158">子レコード要素を使用するように構成、 &#124; (パイプ) 文字を区切り文字として。</span><span class="sxs-lookup"><span data-stu-id="3d113-158">The child record elements are configured to use the &#124; (pipe) character as a delimiter.</span></span>  
  
```  
<MyRec>  
    <FieldElem1 />  
    <FieldElem2 />  
    <FieldElem3>Val</FieldElem3>  
    <!-- <FieldElem4 /> -->  
    <ChildRec>  
        <InnerFieldElement1>Inner1</InnerFieldElement1>   
        <InnerFieldElement2>Inner2</InnerFieldElement1>  
    </ChildRec>  
    <FieldElem5 />  
</MyRec>  
  
```  
  
 <span data-ttu-id="3d113-159">これは、フラット ファイル逆アセンブラーに渡される、FieldElem4 の区切り記号は保存されませんが、その後のレコードは期待どおりに区切られます。</span><span class="sxs-lookup"><span data-stu-id="3d113-159">If this is passed to the flat file disassembler, the delimiters for FieldElem4 will not be preserved but subsequent records will be delimited as expected.</span></span>  
  
```  
,,Val,,Inner1,Inner2,,  
```  
  
## <a name="see-also"></a><span data-ttu-id="3d113-160">参照</span><span class="sxs-lookup"><span data-stu-id="3d113-160">See Also</span></span>  
- [<span data-ttu-id="3d113-161">区切り記号付きレコードに関する注意</span><span class="sxs-lookup"><span data-stu-id="3d113-161">Delimited Record Considerations</span></span>](../core/delimited-record-considerations.md)   
- <span data-ttu-id="3d113-162">**空のデータ (フラット ファイル スキーマのノード プロパティ) の区切り記号の保存**と**末尾の区切り記号 (フラット ファイル スキーマのノード プロパティ) を非表示** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="3d113-162">**Preserve Delimiter For Empty Data (Node Property of Flat File Schemas)** and **Suppress Trailing Delimiters (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
