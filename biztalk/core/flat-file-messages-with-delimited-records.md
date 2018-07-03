---
title: 区切られたレコードのあるフラット ファイル メッセージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ad7119b-4e39-43df-9dba-a04382eb6db2
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a3a3924983b52fb48d41f6d2422e054c656e02f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986363"
---
# <a name="flat-file-messages-with-delimited-records"></a><span data-ttu-id="00a22-102">区切られたレコードのあるフラット ファイル メッセージ</span><span class="sxs-lookup"><span data-stu-id="00a22-102">Flat File Messages with Delimited Records</span></span>
<span data-ttu-id="00a22-103">フラット ファイル インスタンス メッセージ内の区切られたレコードには、入れ子のレコード、および事前に定義された文字や文字セットによって分けられている個別のフィールド (データ項目) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="00a22-103">Delimited records within a flat file instance message contain nested records and/or individual fields (items of data) that are separated by a predefined character or set of characters.</span></span> <span data-ttu-id="00a22-104">これらの区切り記号に従って、フィールドが解析されます。</span><span class="sxs-lookup"><span data-stu-id="00a22-104">The fields are parsed according to these separating delimiters.</span></span> <span data-ttu-id="00a22-105">フラット ファイル インスタンス メッセージ内に、次のような区切られたレコードが存在する場合を例として説明します。このレコードには、仮の注文書を基にした 2 つの商品が含まれています。</span><span class="sxs-lookup"><span data-stu-id="00a22-105">For example, consider the following delimited records from a flat file instance message, which contain two line items from a hypothetical purchase order:</span></span>  
  
```  
  
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Electric-120vac,ITEM926-AA|Baby Monitor|1|39.98|Electric-4AA|2004-01-21  
  
```  
  
 <span data-ttu-id="00a22-106">フラット ファイル スキーマのこのレコードの適切な定義を、次のように記述できます。</span><span class="sxs-lookup"><span data-stu-id="00a22-106">A reasonable definition for this record in a flat file schema can be described as follows:</span></span>  
  
- <span data-ttu-id="00a22-107">子区切り記号 (,)、子の順序の接頭辞、およびタグ ITEMS を持つ、区切られたレコードの名前付き項目。</span><span class="sxs-lookup"><span data-stu-id="00a22-107">A delimited record named items with child delimiter (,), child order prefix, and the tag ITEMS.</span></span>  
  
  -   <span data-ttu-id="00a22-108">区切られた A、繰り返しレコードという名前の子区切り記号を持つ項目&#124;、子注文挿入辞、およびタグ アイテム。</span><span class="sxs-lookup"><span data-stu-id="00a22-108">A delimited, repeating record named item with child delimiter &#124;, child order infix, and the tag ITEM.</span></span>  
  
  -   <span data-ttu-id="00a22-109">"partNum" という属性。</span><span class="sxs-lookup"><span data-stu-id="00a22-109">An attribute named "partNum".</span></span>  
  
  -   <span data-ttu-id="00a22-110">"productName" という要素。</span><span class="sxs-lookup"><span data-stu-id="00a22-110">An element named "productName".</span></span>  
  
  -   <span data-ttu-id="00a22-111">"quantity" という要素。</span><span class="sxs-lookup"><span data-stu-id="00a22-111">An element named "quantity".</span></span>  
  
  -   <span data-ttu-id="00a22-112">"USPrice" という要素。</span><span class="sxs-lookup"><span data-stu-id="00a22-112">An element named "USPrice".</span></span>  
  
  -   <span data-ttu-id="00a22-113">"powerSource" という要素。</span><span class="sxs-lookup"><span data-stu-id="00a22-113">An element named "powerSource".</span></span>  
  
- <span data-ttu-id="00a22-114">"shipDate" という省略可能な要素。</span><span class="sxs-lookup"><span data-stu-id="00a22-114">An optional element named "shipDate".</span></span>  
  
  <span data-ttu-id="00a22-115">これらのレコードとフィールドの定義が提供されると、フラット ファイル逆アセンブラーは、これらのレコードと同等の次の XML を生成します。</span><span class="sxs-lookup"><span data-stu-id="00a22-115">Given these record and field definitions, the flat file disassembler produces the following XML equivalent of these records.</span></span>  
  
```  
  
<items>  
    <item partNum="872-AA">  
        <productName>Lawnmower</productName>  
        <quantity>1</quantity>  
        <USPrice>148.95</USPrice>  
        <powerSource>Electric-120vac</powerSource>  
    </item>  
    <item partNum="926-AA">  
        <productName>Baby Monitor</productName>  
        <quantity>1</quantity>  
        <USPrice>39.98</USPrice>  
        <powerSource>Electric-4AA</powerSource>  
        <shipDate>2004-01-21</shipDate>  
    </item>  
</items>  
  
```  
  
 <span data-ttu-id="00a22-116">区切られたレコードに関連する注意事項を次に示します。これらは、送信時レコードの受信および作成の際のレコードの解析方法に影響します。</span><span class="sxs-lookup"><span data-stu-id="00a22-116">There are a number of considerations related to delimited records that will affect how the record is parsed when received and constructed when sent, including:</span></span>  
  
- <span data-ttu-id="00a22-117">データの一部として扱われるために区切り文字の解釈のオーバーライドにしようされる文字です。</span><span class="sxs-lookup"><span data-stu-id="00a22-117">The character or characters used to override the interpretation of delimiters so that they are treated as part of the data.</span></span> <span data-ttu-id="00a22-118">詳細については、次を参照してください。[フィールド値の一部としての特殊文字の解釈方法](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)します。</span><span class="sxs-lookup"><span data-stu-id="00a22-118">For more information, see [Ways to Interpret Special Characters as Part of a Field Value](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md).</span></span>  
  
- <span data-ttu-id="00a22-119">他の類似しているレコードと区別するために使用される、レコードの先頭の省略可能なタグ。</span><span class="sxs-lookup"><span data-stu-id="00a22-119">An optional tag at the beginning of the record, used to distinguish the record from other similar records.</span></span> <span data-ttu-id="00a22-120">詳細については、次を参照してください。[区切られたレコードのタグ処理](../core/tag-handling-in-delimited-records.md)します。</span><span class="sxs-lookup"><span data-stu-id="00a22-120">For more information, see [Tag Handling in Delimited Records](../core/tag-handling-in-delimited-records.md).</span></span>  
  
- <span data-ttu-id="00a22-121">埋め込み文字に関連する最小長のフィールド内のデータの位置揃え方法。</span><span class="sxs-lookup"><span data-stu-id="00a22-121">How data is justified within fields with minimum lengths, relative to the accompanying pad characters.</span></span> <span data-ttu-id="00a22-122">詳細については、次を参照してください。[フィールド Padding](../core/field-padding.md)、[フィールドの位置揃え](../core/field-justification.md)、および[最小フィールド長区切られたレコードの](../core/minimum-field-lengths-within-delimited-records.md)します。</span><span class="sxs-lookup"><span data-stu-id="00a22-122">For more information, see [Field Padding](../core/field-padding.md), [Field Justification](../core/field-justification.md), and [Minimum Field Lengths Within Delimited Records](../core/minimum-field-lengths-within-delimited-records.md).</span></span>  
  
- <span data-ttu-id="00a22-123">位置指定レコードは、他の区切られたレコード内に入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="00a22-123">Positional records nested within other delimited records.</span></span> <span data-ttu-id="00a22-124">詳細については、次を参照してください。[入れ子になった位置指定レコードとレコードの区切り](../core/nested-positional-and-delimited-records.md)します。</span><span class="sxs-lookup"><span data-stu-id="00a22-124">For more information, see [Nested Positional and Delimited Records](../core/nested-positional-and-delimited-records.md).</span></span>  
  
- <span data-ttu-id="00a22-125">埋め込み文字に関連する固定長のフィールド内のデータの位置揃え方法。</span><span class="sxs-lookup"><span data-stu-id="00a22-125">How data is justified within a fixed length field, relative to its accompanying pad characters.</span></span> <span data-ttu-id="00a22-126">詳細については、次を参照してください。[フィールドの位置揃え](../core/field-justification.md)します。</span><span class="sxs-lookup"><span data-stu-id="00a22-126">For more information, see [Field Justification](../core/field-justification.md).</span></span>  
  
- <span data-ttu-id="00a22-127">区切り記号の位置に関する注意事項は、区切られるデータに関連します。</span><span class="sxs-lookup"><span data-stu-id="00a22-127">Considerations concerning the positioning of delimiters relate to the data that they delimit.</span></span> <span data-ttu-id="00a22-128">詳細については、次を参照してください。[子の順序に関する注意事項](../core/child-order-considerations.md)します。</span><span class="sxs-lookup"><span data-stu-id="00a22-128">For more information, see [Child Order Considerations](../core/child-order-considerations.md).</span></span>  
  
- <span data-ttu-id="00a22-129">フラット ファイル メッセージを受信および送信する際の区切り記号の保存および非表示。</span><span class="sxs-lookup"><span data-stu-id="00a22-129">Preservation and suppression of delimiters when flat file messages are received and sent.</span></span> <span data-ttu-id="00a22-130">詳細については、次を参照してください。[区切り記号の保存と抑制](../core/delimiter-preservation-and-suppression.md)します。</span><span class="sxs-lookup"><span data-stu-id="00a22-130">For more information, see [Delimiter Preservation and Suppression](../core/delimiter-preservation-and-suppression.md).</span></span>  
  
  <span data-ttu-id="00a22-131">区切られたフラット ファイルを使用する方法を理解するために、サンプル、FlatFileReceive フォルダーと FlatFileSend フォルダーにあるを参照してください。 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Pipelines\AssemblerDisassembler\\します。</span><span class="sxs-lookup"><span data-stu-id="00a22-131">To help you better understand how to work with delimited flat files, see the samples in the FlatFileReceive and FlatFileSend folders located at [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Pipelines\AssemblerDisassembler\\.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00a22-132">設定する必要がありますが、フラット ファイルに区切られたおよび位置指定レコードの両方が含まれている場合、**構造**にルート ノードのプロパティ**区切り記号**と**構造**のプロパティいずれかに [レコード] ノードの下位**区切り記号**または**位置指定**に応じて。</span><span class="sxs-lookup"><span data-stu-id="00a22-132">If your flat file contains both delimited and positional records, you must set the **Structure** property of the root node to **Delimited** and the **Structure** property of subordinate record nodes to either **Delimited** or **Positional** as appropriate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00a22-133">フラット ファイルの区切られたフィールドの文字制限は、50000000 文字です。</span><span class="sxs-lookup"><span data-stu-id="00a22-133">Delimited fields in flat files have a limit of 50000000 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00a22-134">参照</span><span class="sxs-lookup"><span data-stu-id="00a22-134">See Also</span></span>  
 <span data-ttu-id="00a22-135">[フラット ファイル メッセージの構造](../core/structure-of-a-flat-file-message.md) </span><span class="sxs-lookup"><span data-stu-id="00a22-135">[Structure of a Flat File Message](../core/structure-of-a-flat-file-message.md) </span></span>  
 <span data-ttu-id="00a22-136">[フラット ファイル メッセージのスキーマを作成する方法](../core/how-to-create-schemas-for-flat-file-messages.md) </span><span class="sxs-lookup"><span data-stu-id="00a22-136">[How to Create Schemas for Flat File Messages](../core/how-to-create-schemas-for-flat-file-messages.md) </span></span>  
 [<span data-ttu-id="00a22-137">フラット ファイル レコードの移行</span><span class="sxs-lookup"><span data-stu-id="00a22-137">Migrating Flat File Records</span></span>](../core/migrating-flat-file-records.md)