---
title: 位置指定レコードのあるフラット ファイル メッセージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72c17c25-3847-458e-a43e-0dbdc42db749
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3b780953c9a1f2c538b63f47942eae5f4ce60df
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345316"
---
# <a name="flat-file-messages-with-positional-records"></a><span data-ttu-id="6777e-102">位置指定のレコードのあるフラット ファイル メッセージ</span><span class="sxs-lookup"><span data-stu-id="6777e-102">Flat File Messages with Positional Records</span></span>
<span data-ttu-id="6777e-103">フラット ファイル インスタンス メッセージ内の位置指定レコードには、事前に定義された長さの個別のフィールド (データ項目) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6777e-103">Positional records within a flat file instance message contain individual fields (items of data) that are each of a predefined length.</span></span> <span data-ttu-id="6777e-104">フィールドは、これらの長さに従って解析されます。</span><span class="sxs-lookup"><span data-stu-id="6777e-104">The fields are parsed according to these lengths.</span></span> <span data-ttu-id="6777e-105">次に示す､フラット ファイル インスタンス メッセージの位置指定レコードを例として考えてみます。ここでは、出荷先住所を記載し、最初の行に各フィールドに予約される文字数が示されています。</span><span class="sxs-lookup"><span data-stu-id="6777e-105">For example, consider the following positional record from a flat file instance message, which contains a ship to address (the first line shows the number of characters reserved for each field).</span></span>  
  
```  
123456789012345678901234567890123456789012345678901234567890123456789012345  
US        Alice Smith         123 Maple Street    Mill Valley    CA 90952  
```  
  
 <span data-ttu-id="6777e-106">フラット ファイル スキーマ内にあるこのレコードの適切な定義を、次のフィールドを含む shipTo という位置指定レコードとして記述できます。</span><span class="sxs-lookup"><span data-stu-id="6777e-106">A reasonable definition for this record in a flat file schema can be described as a positional record named shipTo that contains the following fields:</span></span>  
  
- <span data-ttu-id="6777e-107">国/地域 (左揃え、長さが 10 文字、オフセットなし) という属性。</span><span class="sxs-lookup"><span data-stu-id="6777e-107">An attribute named country/region that is left-aligned, 10 characters in length, with a zero character offset.</span></span>  
  
- <span data-ttu-id="6777e-108">名前 (左揃え、長さが 20 文字、オフセットなし) という要素。</span><span class="sxs-lookup"><span data-stu-id="6777e-108">An element named name that is left-aligned, 20 characters in length, with a zero character offset.</span></span>  
  
- <span data-ttu-id="6777e-109">番地 (左揃え、長さが 20 文字、オフセットなし) という要素。</span><span class="sxs-lookup"><span data-stu-id="6777e-109">An element named street that is left-aligned, 20 characters in length, with a zero character offset.</span></span>  
  
- <span data-ttu-id="6777e-110">市区町村 (左揃え、長さが 15 文字、オフセットなし) という要素。</span><span class="sxs-lookup"><span data-stu-id="6777e-110">An element named city that is left-aligned, 15 characters in length, with a zero character offset.</span></span>  
  
- <span data-ttu-id="6777e-111">都道府県 (左揃え、長さが 2 文字、オフセットなし) という要素。</span><span class="sxs-lookup"><span data-stu-id="6777e-111">An element named state that is left-aligned, 2 characters in length, with a zero character offset.</span></span>  
  
- <span data-ttu-id="6777e-112">左揃えである zip をという名前の要素、5 文字で、1 文字のオフセットします。</span><span class="sxs-lookup"><span data-stu-id="6777e-112">An element named zip that is left-aligned, 5 characters in length, with a one character offset.</span></span>  
  
  <span data-ttu-id="6777e-113">これらのレコードとフィールドの定義が提供されると、フラット ファイル逆アセンブラーは、このレコードと等価の XML を生成します。次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6777e-113">Given these record and field definitions, the flat file disassembler will produce the following XML equivalent of this record.</span></span>  
  
```  
<shipTo country/region="US">  
    <name>Alice Smith</name>  
    <street>123 Maple Street</street>  
    <city>Mill Valley</city>  
    <state>CA</state>  
    <zip>90952</zip>  
</shipTo>  
  
```  
  
 <span data-ttu-id="6777e-114">位置指定レコードに関連する注意事項を次に示します。これらは、レコードの受信やレコードの作成時におけるレコードの解析方法に影響します。</span><span class="sxs-lookup"><span data-stu-id="6777e-114">There are a number of considerations related to positional records that will affect how the record is parsed when received and constructed when sent, including:</span></span>  
  
- <span data-ttu-id="6777e-115">各フィールドの使用されていない部分を埋めるために使用する文字 (埋め込み文字と呼ばれる)。</span><span class="sxs-lookup"><span data-stu-id="6777e-115">The character used to fill the unused portion of each field, known as the pad character.</span></span> <span data-ttu-id="6777e-116">詳細については、次を参照してください。[フィールド Padding](../core/field-padding.md)します。</span><span class="sxs-lookup"><span data-stu-id="6777e-116">For more information, see [Field Padding](../core/field-padding.md).</span></span>  
  
- <span data-ttu-id="6777e-117">他の類似しているレコードと区別するために使用されるレコード内の省略可能なタグ。</span><span class="sxs-lookup"><span data-stu-id="6777e-117">An optional tag within the record, used to distinguish the record from other similar records.</span></span> <span data-ttu-id="6777e-118">通常、タグはレコードの先頭にありますが、レコード内の任意の場所に配置できます。</span><span class="sxs-lookup"><span data-stu-id="6777e-118">Tags usually occur at the beginning of the record but allowable anywhere within it.</span></span> <span data-ttu-id="6777e-119">詳細については、次を参照してください。[位置指定レコードのタグ処理](../core/tag-handling-in-positional-records.md)します。</span><span class="sxs-lookup"><span data-stu-id="6777e-119">For more information, see [Tag Handling in Positional Records](../core/tag-handling-in-positional-records.md).</span></span> <span data-ttu-id="6777e-120">位置指定レコードでタグの有無を定義できます。ただし、一度定義されると、その定義に基づいて、タグの存在の有無が決まります。</span><span class="sxs-lookup"><span data-stu-id="6777e-120">Positional records can be defined to have a tag or not have a tag, but once defined, the tag must be present or not, based on the definition.</span></span>  
  
- <span data-ttu-id="6777e-121">固定長のフィールドでのデータの位置揃え方法。埋め込み文字の影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="6777e-121">How data is justified within a fixed length field, relative to the accompanying pad characters.</span></span> <span data-ttu-id="6777e-122">詳細については、次を参照してください。[フィールドの位置揃え](../core/field-justification.md)します。</span><span class="sxs-lookup"><span data-stu-id="6777e-122">For more information, see [Field Justification](../core/field-justification.md).</span></span>  
  
- <span data-ttu-id="6777e-123">位置指定レコードは、他の位置指定レコードまたは区切られたレコード内に入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6777e-123">Positional records nested within other positional or delimited records.</span></span> <span data-ttu-id="6777e-124">詳細については、次を参照してください。[位置指定レコードの入れ子になった](../core/nested-positional-records.md)します。</span><span class="sxs-lookup"><span data-stu-id="6777e-124">For more information, see [Nested Positional Records](../core/nested-positional-records.md).</span></span>  
  
- <span data-ttu-id="6777e-125">特定の文字数ではなく特定のバイト数で指定したフィールド長を持つ位置指定レコード。</span><span class="sxs-lookup"><span data-stu-id="6777e-125">Positional records with field lengths specified as a specific number of bytes rather than a specific number of characters.</span></span> <span data-ttu-id="6777e-126">詳細については、次を参照してください。[位置のカウント (バイト単位)](../core/position-counting-in-bytes.md)します。</span><span class="sxs-lookup"><span data-stu-id="6777e-126">For more information, see [Position Counting in Bytes](../core/position-counting-in-bytes.md).</span></span>  
  
  <span data-ttu-id="6777e-127">位置指定フラット ファイルを使用する方法を理解するために、サンプル、FlatFileReceive フォルダーと FlatFileSend フォルダーにある \Program Files\Microsoft BizTalk Server\SDK\Samples\Pipelines\AssemblerDisassembler を参照してください。\\します。</span><span class="sxs-lookup"><span data-stu-id="6777e-127">To help you better understand how to work with positional flat files, see the samples in the FlatFileReceive and FlatFileSend folders located at \Program Files\Microsoft BizTalk Server\SDK\Samples\Pipelines\AssemblerDisassembler\\.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6777e-128">設定する必要がありますが、フラット ファイルに区切られたおよび位置指定レコードの両方が含まれている場合、**構造**にルート ノードのプロパティ**区切り記号**と**構造**のプロパティいずれかに [レコード] ノードの下位**区切り記号**または**位置指定**に応じて。</span><span class="sxs-lookup"><span data-stu-id="6777e-128">If your flat file contains both delimited and positional records, you must set the **Structure** property of the root node to **Delimited** and the **Structure** property of subordinate record nodes to either **Delimited** or **Positional** as appropriate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6777e-129">位置指定レコードのフィールドの文字制限は、50000000 文字です。</span><span class="sxs-lookup"><span data-stu-id="6777e-129">Fields in positional records have a limit of 50000000 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6777e-130">参照</span><span class="sxs-lookup"><span data-stu-id="6777e-130">See Also</span></span>  
 <span data-ttu-id="6777e-131">[フラット ファイル メッセージの構造](../core/structure-of-a-flat-file-message.md) </span><span class="sxs-lookup"><span data-stu-id="6777e-131">[Structure of a Flat File Message](../core/structure-of-a-flat-file-message.md) </span></span>  
 [<span data-ttu-id="6777e-132">フラット ファイル メッセージのスキーマを作成する方法</span><span class="sxs-lookup"><span data-stu-id="6777e-132">How to Create Schemas for Flat File Messages</span></span>](../core/how-to-create-schemas-for-flat-file-messages.md)