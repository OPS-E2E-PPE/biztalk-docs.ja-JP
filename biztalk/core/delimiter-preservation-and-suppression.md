---
title: "区切り記号の保存と抑制 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30985b94-625e-411a-8137-1c129bc197bf
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1195e153eb94215bf8861b4856e4d2135b24443e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="delimiter-preservation-and-suppression"></a><span data-ttu-id="5c34b-102">区切り記号の保存および非表示</span><span class="sxs-lookup"><span data-stu-id="5c34b-102">Delimiter Preservation and Suppression</span></span>

## <a name="overview"></a><span data-ttu-id="5c34b-103">概要</span><span class="sxs-lookup"><span data-stu-id="5c34b-103">Overview</span></span>
<span data-ttu-id="5c34b-104">区切られたレコードに適用される 2 つのプロパティ:**空のデータの区切り記号を保持する**と**[末尾の区切り記号の抑制**です。</span><span class="sxs-lookup"><span data-stu-id="5c34b-104">There are two properties that apply to delimited records: **Preserve Delimiter For Empty Data** and **[Suppress Trailing Delimiters**.</span></span> <span data-ttu-id="5c34b-105">これらのプロパティを使用すると、フラット ファイル アセンブラーが存在しないデータと末尾の区切り記号に関連付けられている区切り記号を処理する方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="5c34b-105">Use these properties to control how the flat file assembler handles delimiters associated with nonexistent data and trailing delimiters.</span></span> <span data-ttu-id="5c34b-106">設定すると、**空のデータの区切り記号を保持する**プロパティを**はい**(既定の設定は)、変換されたフラット ファイル メッセージ内の区切り記号が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5c34b-106">When you set the **Preserve Delimiter For Empty Data** property to **Yes** (which is the default setting), delimiters are included in the translated flat file message for:</span></span>  
  
-   <span data-ttu-id="5c34b-107">データを含んでいないフィールド。</span><span class="sxs-lookup"><span data-stu-id="5c34b-107">Fields without data.</span></span>  
  
-   <span data-ttu-id="5c34b-108">関連付けられたタグを持たず、データを含んでいない直下のレコード。</span><span class="sxs-lookup"><span data-stu-id="5c34b-108">Immediately subordinate records without data that do not have a tag associated with them.</span></span>  
  
 <span data-ttu-id="5c34b-109">設定すると、**空のデータの区切り記号を保持する**プロパティを**いいえ**、区切り記号は、レコードおよびフィールドがデータなしの変換されたフラット ファイルには含まれません。</span><span class="sxs-lookup"><span data-stu-id="5c34b-109">When you set the **Preserve Delimiter For Empty Data** property to **No**, delimiters are not included in the translated flat file for records and fields without data.</span></span> <span data-ttu-id="5c34b-110">さらの設定に関係なく、**空のデータの区切り記号を保持する**プロパティ、タグが定義されているデータなしの直下のレコードに変換されたフラット ファイル メッセージ内の区切り記号は含まれません。</span><span class="sxs-lookup"><span data-stu-id="5c34b-110">Further, regardless of the setting of the **Preserve Delimiter For Empty Data** property, delimiters will not be included in the translated flat file message for immediately subordinate records without data for which a tag is defined.</span></span>  
  
 <span data-ttu-id="5c34b-111">設定すると、**末尾の区切り記号の非表示**プロパティを**なし**(既定の設定は)、変換されたフラット ファイル メッセージに 1 つまたは複数の末尾の区切り記号を含めることがあります。</span><span class="sxs-lookup"><span data-stu-id="5c34b-111">When you set the **Suppress Trailing Delimiters** property to **No** (which is the default setting), one or more trailing delimiters may be included in the translated flat file message.</span></span> <span data-ttu-id="5c34b-112">設定すると、**末尾の区切り記号の非表示**プロパティを**はい**、末尾の区切り記号は、変換されたフラット ファイル メッセージに含まれません。</span><span class="sxs-lookup"><span data-stu-id="5c34b-112">When you set the **Suppress Trailing Delimiters** property to **Yes**, trailing delimiters are not included in the translated flat file message.</span></span>  

## <a name="special-scenarios"></a><span data-ttu-id="5c34b-113">特殊なシナリオ</span><span class="sxs-lookup"><span data-stu-id="5c34b-113">Special scenarios</span></span>  
 <span data-ttu-id="5c34b-114">設定で、動作が原因となった特殊なケースがある、**空のデータの区切り記号を保持する**と**末尾の区切り記号の抑制する状況**プロパティが競合することをがします。</span><span class="sxs-lookup"><span data-stu-id="5c34b-114">There are some special cases where the behaviors caused by the settings of the **Preserve Delimiter For Empty Data** and **Suppress Trailing Delimiters** properties can conflict.</span></span> <span data-ttu-id="5c34b-115">このような場合、後者のプロパティに関連付けられている動作**末尾の区切り記号の抑制**が優先されます。</span><span class="sxs-lookup"><span data-stu-id="5c34b-115">In such cases, the behaviors associated with the latter property, **Suppress Trailing Delimiters**, will take precedence.</span></span> <span data-ttu-id="5c34b-116">また、これら 2 つのプロパティの設定によって競合が発生する可能性が高いと予測される状況もあります。</span><span class="sxs-lookup"><span data-stu-id="5c34b-116">Further, there are some special cases where you will be warned about potential conflicts between the settings you have chosen for these two properties.</span></span>  
  
 <span data-ttu-id="5c34b-117">たとえば、**レコード**次のプロパティ値で定義されたノード。</span><span class="sxs-lookup"><span data-stu-id="5c34b-117">For example, consider a **Record** node defined with the following property values:</span></span>  
  
-   <span data-ttu-id="5c34b-118">ノード名が MyRec である。</span><span class="sxs-lookup"><span data-stu-id="5c34b-118">Node Name is MyRec</span></span>  
  
-   <span data-ttu-id="5c34b-119">タグ識別子が Rec である。</span><span class="sxs-lookup"><span data-stu-id="5c34b-119">Tag Identifier is Rec</span></span>  
  
-   <span data-ttu-id="5c34b-120">子の区切り記号が , である。</span><span class="sxs-lookup"><span data-stu-id="5c34b-120">Child Delimiter is ,</span></span>  
  
-   <span data-ttu-id="5c34b-121">子の順序が挿入辞である。</span><span class="sxs-lookup"><span data-stu-id="5c34b-121">Child Order is Infix</span></span>  
  
 <span data-ttu-id="5c34b-122">5 つ含むに定義されていると**フィールド要素**ノードで次の名前 (も**フィールド属性**ノードまたは下位**レコード**ノード)。</span><span class="sxs-lookup"><span data-stu-id="5c34b-122">And defined to contain five **Field Element** nodes with the following names (they could also be **Field Attribute** nodes or subordinate **Record** nodes):</span></span>  
  
-   <span data-ttu-id="5c34b-123">FieldElem1</span><span class="sxs-lookup"><span data-stu-id="5c34b-123">FieldElem1</span></span>  
  
-   <span data-ttu-id="5c34b-124">FieldElem2</span><span class="sxs-lookup"><span data-stu-id="5c34b-124">FieldElem2</span></span>  
  
-   <span data-ttu-id="5c34b-125">FieldElem3</span><span class="sxs-lookup"><span data-stu-id="5c34b-125">FieldElem3</span></span>  
  
-   <span data-ttu-id="5c34b-126">FieldElem4</span><span class="sxs-lookup"><span data-stu-id="5c34b-126">FieldElem4</span></span>  
  
-   <span data-ttu-id="5c34b-127">FieldElem5</span><span class="sxs-lookup"><span data-stu-id="5c34b-127">FieldElem5</span></span>  
  
 <span data-ttu-id="5c34b-128">次の主に空のこれを表す XML フラグメントを次に、想定**レコード**ノードは、フラット ファイル アセンブラーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="5c34b-128">Next, assume that the following mainly empty XML fragment, representing this **Record** node, is passed to the flat file assembler.</span></span>  
  
```  
<MyRec>  
    <FieldElem1 />  
    <FieldElem2 />  
    <FieldElem3>Val</FieldElem3>  
    <FieldElem4 />  
    <FieldElem5 />  
</MyRec>  
  
```  
  
 <span data-ttu-id="5c34b-129">次の表は、生成される出力と、関連付けられている追加のプロパティの設定に異なる設定に基づいて、関連するスキーマ ノードの要件、**空のデータの区切り記号を保持する**(PDFED) および**末尾の区切り記号の抑制**(STD) プロパティです。</span><span class="sxs-lookup"><span data-stu-id="5c34b-129">The following table shows the output produced, and the associated additional property setting requirements for the relevant schema nodes, based on different settings for the **Preserve Delimiter For Empty Data** (PDFED) and **Suppress Trailing Delimiters** (STD) properties.</span></span>  
  
|<span data-ttu-id="5c34b-130">PDFED 設定</span><span class="sxs-lookup"><span data-stu-id="5c34b-130">PDFED setting</span></span>|<span data-ttu-id="5c34b-131">STD 設定</span><span class="sxs-lookup"><span data-stu-id="5c34b-131">STD setting</span></span>|<span data-ttu-id="5c34b-132">出力</span><span class="sxs-lookup"><span data-stu-id="5c34b-132">Output</span></span>|<span data-ttu-id="5c34b-133">追加のノード要件</span><span class="sxs-lookup"><span data-stu-id="5c34b-133">Additional node requirements</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="5c34b-134">はい</span><span class="sxs-lookup"><span data-stu-id="5c34b-134">Yes</span></span>|<span data-ttu-id="5c34b-135">不可</span><span class="sxs-lookup"><span data-stu-id="5c34b-135">No</span></span>|<span data-ttu-id="5c34b-136">Rec,,,Val,,</span><span class="sxs-lookup"><span data-stu-id="5c34b-136">Rec,,,Val,,</span></span>|<span data-ttu-id="5c34b-137">[なし] :</span><span class="sxs-lookup"><span data-stu-id="5c34b-137">None.</span></span>|  
|<span data-ttu-id="5c34b-138">不可</span><span class="sxs-lookup"><span data-stu-id="5c34b-138">No</span></span>|<span data-ttu-id="5c34b-139">はい</span><span class="sxs-lookup"><span data-stu-id="5c34b-139">Yes</span></span>|<span data-ttu-id="5c34b-140">Rec,Val</span><span class="sxs-lookup"><span data-stu-id="5c34b-140">Rec,Val</span></span>|<span data-ttu-id="5c34b-141">すべて**フィールド要素**ノードは省略可能として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c34b-141">All **Field Element** nodes must be configured as optional.</span></span>|  
|<span data-ttu-id="5c34b-142">はい</span><span class="sxs-lookup"><span data-stu-id="5c34b-142">Yes</span></span>|<span data-ttu-id="5c34b-143">はい</span><span class="sxs-lookup"><span data-stu-id="5c34b-143">Yes</span></span>|<span data-ttu-id="5c34b-144">Rec,,,Val</span><span class="sxs-lookup"><span data-stu-id="5c34b-144">Rec,,,Val</span></span>|<span data-ttu-id="5c34b-145">という名前のノード**FieldElem4**と**FieldElem5**オプションとして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c34b-145">Nodes named **FieldElem4** and **FieldElem5** must be configured as optional.</span></span>|  
|<span data-ttu-id="5c34b-146">不可</span><span class="sxs-lookup"><span data-stu-id="5c34b-146">No</span></span>|<span data-ttu-id="5c34b-147">不可</span><span class="sxs-lookup"><span data-stu-id="5c34b-147">No</span></span>|<span data-ttu-id="5c34b-148">Rec,Val,,</span><span class="sxs-lookup"><span data-stu-id="5c34b-148">Rec,Val,,</span></span>|<span data-ttu-id="5c34b-149">すべて**フィールド要素**ノードは省略可能として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c34b-149">All **Field Element** nodes must be configured as optional.</span></span>|  
  
 <span data-ttu-id="5c34b-150">これらのプロパティ設定で、区切り記号が保存されない設定、または区切り記号を非表示にする設定を行うと、同じスキーマを使用してシリアル化したフラット ファイル データを解析できないという警告を示すメッセージが、次の場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c34b-150">When these property settings specify that delimiters should either not be preserved or should be suppressed, a message warning that it might not be possible to parse the serialized flat file data using the same schema will be issued in the following two cases:</span></span>  
  
-   <span data-ttu-id="5c34b-151">ときに、**レコード**対象のノード、**空のデータの区切り記号を保持する**プロパティに設定されている**いいえ**と**抑制末尾の区切り記号**プロパティに設定されている**はい**、それぞれ、下位が含まれています**フィールド要素**ノード、**フィールド属性**ノード、または**レコード**のタグが指定されていないノードです。</span><span class="sxs-lookup"><span data-stu-id="5c34b-151">When the **Record** node for which the **Preserve Delimiter For Empty Data** property is set to **No** and/or the **Suppress Trailing Delimiters** property is set to **Yes**, respectively, contains subordinate **Field Element** nodes, **Field Attribute** nodes, or **Record** nodes for which no tag is specified.</span></span>  
  
-   <span data-ttu-id="5c34b-152">ときに、下位**フィールド要素**ノード、**フィールド属性**ノード、および**レコード**のタグが指定されていないノードが省略可能な場合に構成されていません (設定して、**Min Occurs**プロパティを 0 に設定)、スキーマにします。</span><span class="sxs-lookup"><span data-stu-id="5c34b-152">When the subordinate **Field Element** nodes, **Field Attribute** nodes, and **Record** nodes for which no tag is specified are not configured to be optional (by setting the **Min Occurs** property set to zero) in the schema.</span></span> <span data-ttu-id="5c34b-153">ときに、**末尾の区切り記号の抑制**プロパティに設定されている**[はい]**最後にのみを構成する必要がこのような下位ノードが省略可能として。</span><span class="sxs-lookup"><span data-stu-id="5c34b-153">When the **Suppress Trailing Delimiters** property is set to **Yes**, only the last such subordinate nodes need to be configured as optional.</span></span> <span data-ttu-id="5c34b-154">ときに、**空のデータの区切り記号を保持する**プロパティに設定されている**なし**、すべての末尾を構成する必要が下位ノードが省略可能として。</span><span class="sxs-lookup"><span data-stu-id="5c34b-154">When the **Preserve Delimiter For Empty Data** property is set to **No**, all trailing subordinate nodes need to be configured as optional.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c34b-155">XML 要素は、(おそらく省略可能) に関連付けられているときに区切り記号は常に保持**レコード**、**フィールド要素**、または**フィールド属性**ノードがまったくないです。レコードが省略可能なフィールドがありませんに依存する場合を除く、ビジネス ドキュメントの XML 表現。</span><span class="sxs-lookup"><span data-stu-id="5c34b-155">Delimiters are always preserved when the XML element associated with a (presumably optional) **Record**, **Field Element**, or **Field Attribute** node are entirely missing from the XML representation of the business document except when a Record follows a missing optional Field.</span></span> <span data-ttu-id="5c34b-156">つまり、データとデータを囲む XML タグが両方とも欠落している場合、対応する区切り記号は、ビジネス ドキュメントのフラット ファイル表記に必ず含まれます。</span><span class="sxs-lookup"><span data-stu-id="5c34b-156">In other words, when the data and its surrounding XML tags are both missing, the corresponding delimiter is always included in the flat file representation of the business document.</span></span>  
  
 <span data-ttu-id="5c34b-157">ここで、欠落した [フィールド要素] の直後に 2 つの [フィールド要素] を持つ子レコードを含むようにスキーマを変更します。</span><span class="sxs-lookup"><span data-stu-id="5c34b-157">Now change the schema to include a child record with two Field Element immediately following a missing Field Element.</span></span> <span data-ttu-id="5c34b-158">使用する子レコード要素が構成されている、& #124 です。(パイプ) 文字を区切り文字として。</span><span class="sxs-lookup"><span data-stu-id="5c34b-158">The child record elements are configured to use the &#124; (pipe) character as a delimiter.</span></span>  
  
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
  
 <span data-ttu-id="5c34b-159">このデータがフラット ファイル逆アセンブラーに渡されると、FieldElem4 の区切り記号は保存されませんが、その後のレコードは正常に区切られます。</span><span class="sxs-lookup"><span data-stu-id="5c34b-159">If this is passed to the flat file disassembler, the delimiters for FieldElem4 will not be preserved but subsequent records will be delimited as expected.</span></span>  
  
```  
,,Val,,Inner1,Inner2,,  
```  
  
## <a name="see-also"></a><span data-ttu-id="5c34b-160">参照</span><span class="sxs-lookup"><span data-stu-id="5c34b-160">See Also</span></span>  
-  [<span data-ttu-id="5c34b-161">区切り記号付きレコードに関する注意点</span><span class="sxs-lookup"><span data-stu-id="5c34b-161">Delimited Record Considerations</span></span>](../core/delimited-record-considerations.md)   
-  <span data-ttu-id="5c34b-162">**空のデータ (フラット ファイル スキーマのノード プロパティ) の区切り記号の保存**と**末尾の区切り記号 (フラット ファイル スキーマのノード プロパティ) を抑制する**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="5c34b-162">**Preserve Delimiter For Empty Data (Node Property of Flat File Schemas)** and **Suppress Trailing Delimiters (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>