---
title: 囲み文字 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7268f46-9bf6-4c76-9b3a-b4ee0e8db997
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7d88c412c94505600443d351a150b6ca8a6876a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996595"
---
# <a name="wrap-characters"></a><span data-ttu-id="baf2b-102">囲み文字</span><span class="sxs-lookup"><span data-stu-id="baf2b-102">Wrap Characters</span></span>

## <a name="overview"></a><span data-ttu-id="baf2b-103">概要</span><span class="sxs-lookup"><span data-stu-id="baf2b-103">Overview</span></span>
<span data-ttu-id="baf2b-104">囲み文字は単一の文字であり、この文字でフィールド内のデータ文字を囲むことにより、データ文字が持つ特殊な意味を無効にします。</span><span class="sxs-lookup"><span data-stu-id="baf2b-104">A wrap character is a single character that is used to wrap the data characters in a field for the purpose of suppressing any special meaning that any of those data characters would otherwise have.</span></span> <span data-ttu-id="baf2b-105">たとえば、次のような特性を持つフラット ファイル レコードを定義したとします。</span><span class="sxs-lookup"><span data-stu-id="baf2b-105">For example, if you define a flat file record as having the following characteristics:</span></span>  
  
- <span data-ttu-id="baf2b-106">名前 = Record1</span><span class="sxs-lookup"><span data-stu-id="baf2b-106">Name = Record1</span></span>  
  
- <span data-ttu-id="baf2b-107">[区切り記号]</span><span class="sxs-lookup"><span data-stu-id="baf2b-107">Delimited</span></span>  
  
- <span data-ttu-id="baf2b-108">子区切り記号 = コンマ (,)</span><span class="sxs-lookup"><span data-stu-id="baf2b-108">Child delimiter = comma character (,)</span></span>  
  
- <span data-ttu-id="baf2b-109">子の順序 = 挿入辞</span><span class="sxs-lookup"><span data-stu-id="baf2b-109">Child order = infix</span></span>  
  
- <span data-ttu-id="baf2b-110">エスケープ文字 = 円記号 (\\)</span><span class="sxs-lookup"><span data-stu-id="baf2b-110">Escape character = backslash character (\\)</span></span>  
  
- <span data-ttu-id="baf2b-111">タグ = RECORD1</span><span class="sxs-lookup"><span data-stu-id="baf2b-111">Tag = RECORD1</span></span>  
  
- <span data-ttu-id="baf2b-112">3 つのフィールド (Field1、Field2、および Field3) は、囲み文字にシャープ記号 (#) を使用します。</span><span class="sxs-lookup"><span data-stu-id="baf2b-112">Three fields named Field1, Field2, and Field3, each defined to use the number sign character (#) as their wrap character.</span></span>  
  
  <span data-ttu-id="baf2b-113">今度は、このレコードに次のようなフラット ファイル データを適用したとします。</span><span class="sxs-lookup"><span data-stu-id="baf2b-113">Then the following flat file data applies for the record.</span></span>  
  
```  
RECORD1#field1#,#field2#,#field3#  
  
```  
  
 <span data-ttu-id="baf2b-114">データは、次の XML のフラグメントに逆アセンブルします。</span><span class="sxs-lookup"><span data-stu-id="baf2b-114">The data is disassembled into the following fragment of XML.</span></span>  
  
```  
<Record1>  
    <Field1></Field1>  
    <Field2></Field2>  
    <Field3></Field3>  
</Record1>  
  
```  
  
 <span data-ttu-id="baf2b-115">太字のデータ文字 (Field1、Field2、および Field3) の囲み文字 (#) は削除されるので注意してください。</span><span class="sxs-lookup"><span data-stu-id="baf2b-115">Note that the wrap characters (#) surrounding the bolded data characters field1, field2, and field3 have been removed.</span></span>  
  
 <span data-ttu-id="baf2b-116">各の元のシーケンスを生成、フィールドのデータの文字の前後に囲み文字を挿入、フラット ファイル アセンブラーでは、レコードの XML バージョンを同等のフラット ファイル レコードに変換する逆の操作を実行するときフラット ファイルの文字。</span><span class="sxs-lookup"><span data-stu-id="baf2b-116">When the flat file assembler performs the reverse operation, converting the XML version of the record to its equivalent flat file record, the wrap characters are inserted before and after the data characters of each of the fields, yielding the original sequence of flat file characters.</span></span>  
  
 <span data-ttu-id="baf2b-117">定義されたエスケープ文字と囲み文字を同時に使用できます。</span><span class="sxs-lookup"><span data-stu-id="baf2b-117">The defined escape character can be used in conjunction with the defined wrap character.</span></span> <span data-ttu-id="baf2b-118">たとえば、Field1 の値が次のように変更されると仮定します (太字で表記)。</span><span class="sxs-lookup"><span data-stu-id="baf2b-118">For example, suppose the value of Field1 is changed as follows (shown in bold type).</span></span>  
  
```  
<Record1>  
    <Field1></Field1>  
    <Field2>field2</Field2>  
    <Field3>field3</Field3>  
</Record1>  
  
```  
  
 <span data-ttu-id="baf2b-119">提供されているレコードとフィールドの定義でこの XML フラグメントをアセンブルすると、フラット ファイルの文字が次の順序で生成されます (エスケープのシャープ記号を太字で表記)。</span><span class="sxs-lookup"><span data-stu-id="baf2b-119">When this XML fragment is assembled, using the record and field definitions provided, the following sequence of flat file characters is produced (the escaped number sign character sequence is shown in bold type).</span></span>  
  
```  
RECORD1#field1#,#field2#,#field3#  
  
```  
  
 <span data-ttu-id="baf2b-120">BizTalk エディターを使用してフラット ファイル スキーマを作成するときに使用して、スキーマ全体の既定の囲み文字を定義することができます、**既定の囲み文字**と**既定の囲み文字の種類**のプロパティ、**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="baf2b-120">When creating a flat file schema using BizTalk Editor, you can define a default wrap character for the entire schema using the **Default Wrap Character** and **Default Wrap Character Type** properties of the **Schema** node.</span></span> <span data-ttu-id="baf2b-121">次に、この既定の囲み文字またはを使用して、カスタム フィールド固有の囲み文字を使用するか、スキーマの各フィールドを構成、**囲み文字**と**囲み文字の種類**プロパティ、**フィールド要素**または**フィールド属性**フラット ファイル スキーマのノード。</span><span class="sxs-lookup"><span data-stu-id="baf2b-121">Then, you can configure each individual field in the schema to either use this default wrap character or a custom, field-specific wrap character using the **Wrap Character** and **Wrap Character Type** properties of the **Field Element** or **Field Attribute** nodes in flat file schemas.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="baf2b-122">参照</span><span class="sxs-lookup"><span data-stu-id="baf2b-122">See Also</span></span>  
- [<span data-ttu-id="baf2b-123">特殊文字をフィールド値の一部として解釈させる方法</span><span class="sxs-lookup"><span data-stu-id="baf2b-123">Ways to Interpret Special Characters as Part of a Field Value</span></span>](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)  
- <span data-ttu-id="baf2b-124">文字のプロパティをラップ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span><span class="sxs-lookup"><span data-stu-id="baf2b-124">Wrap character properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span></span>  
    -  <span data-ttu-id="baf2b-125">既定の囲み文字 (フラット ファイル スキーマのノード プロパティ</span><span class="sxs-lookup"><span data-stu-id="baf2b-125">Default Wrap Character (Node Property of Flat File Schemas</span></span>
    -  <span data-ttu-id="baf2b-126">既定囲み文字の種類 (フラット ファイル スキーマのノード プロパティ</span><span class="sxs-lookup"><span data-stu-id="baf2b-126">Default Wrap Character Type (Node Property of Flat File Schemas</span></span>
    -  <span data-ttu-id="baf2b-127">囲み文字 (フラット ファイル スキーマのノード プロパティ</span><span class="sxs-lookup"><span data-stu-id="baf2b-127">Wrap Character (Node Property of Flat File Schemas</span></span>  
    -  <span data-ttu-id="baf2b-128">囲み文字の種類 (フラット ファイル スキーマのノード プロパティ</span><span class="sxs-lookup"><span data-stu-id="baf2b-128">Wrap Character Type (Node Property of Flat File Schemas</span></span>