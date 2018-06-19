---
title: 囲み文字 |Microsoft ドキュメント
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
ms.openlocfilehash: f95ed10811232b15762c31bfc435ac7772a53b3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290034"
---
# <a name="wrap-characters"></a><span data-ttu-id="f45ec-102">囲み文字</span><span class="sxs-lookup"><span data-stu-id="f45ec-102">Wrap Characters</span></span>

## <a name="overview"></a><span data-ttu-id="f45ec-103">概要</span><span class="sxs-lookup"><span data-stu-id="f45ec-103">Overview</span></span>
<span data-ttu-id="f45ec-104">囲み文字は単一の文字であり、この文字でフィールド内のデータ文字を囲むことにより、データ文字が持つ特殊な意味を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f45ec-104">A wrap character is a single character that is used to wrap the data characters in a field for the purpose of suppressing any special meaning that any of those data characters would otherwise have.</span></span> <span data-ttu-id="f45ec-105">たとえば、次のような特性を持つフラット ファイル レコードを定義したとします。</span><span class="sxs-lookup"><span data-stu-id="f45ec-105">For example, if you define a flat file record as having the following characteristics:</span></span>  
  
-   <span data-ttu-id="f45ec-106">名前 = Record1</span><span class="sxs-lookup"><span data-stu-id="f45ec-106">Name = Record1</span></span>  
  
-   <span data-ttu-id="f45ec-107">[区切り記号]</span><span class="sxs-lookup"><span data-stu-id="f45ec-107">Delimited</span></span>  
  
-   <span data-ttu-id="f45ec-108">子区切り記号 = コンマ (,)</span><span class="sxs-lookup"><span data-stu-id="f45ec-108">Child delimiter = comma character (,)</span></span>  
  
-   <span data-ttu-id="f45ec-109">子の順序 = 挿入辞</span><span class="sxs-lookup"><span data-stu-id="f45ec-109">Child order = infix</span></span>  
  
-   <span data-ttu-id="f45ec-110">エスケープ文字 = 円記号 (\\)</span><span class="sxs-lookup"><span data-stu-id="f45ec-110">Escape character = backslash character (\\)</span></span>  
  
-   <span data-ttu-id="f45ec-111">タグ = RECORD1</span><span class="sxs-lookup"><span data-stu-id="f45ec-111">Tag = RECORD1</span></span>  
  
-   <span data-ttu-id="f45ec-112">3 つのフィールド (Field1、Field2、および Field3) は、囲み文字にシャープ記号 (#) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f45ec-112">Three fields named Field1, Field2, and Field3, each defined to use the number sign character (#) as their wrap character.</span></span>  
  
 <span data-ttu-id="f45ec-113">今度は、このレコードに次のようなフラット ファイル データを適用したとします。</span><span class="sxs-lookup"><span data-stu-id="f45ec-113">Then the following flat file data applies for the record.</span></span>  
  
```  
RECORD1#field1#,#field2#,#field3#  
  
```  
  
 <span data-ttu-id="f45ec-114">データは、XML の次のフラグメントに逆アセンブルします。</span><span class="sxs-lookup"><span data-stu-id="f45ec-114">The data is disassembled into the following fragment of XML.</span></span>  
  
```  
<Record1>  
    <Field1></Field1>  
    <Field2></Field2>  
    <Field3></Field3>  
</Record1>  
  
```  
  
 <span data-ttu-id="f45ec-115">太字のデータ文字 (Field1、Field2、および Field3) の囲み文字 (#) は削除されるので注意してください。</span><span class="sxs-lookup"><span data-stu-id="f45ec-115">Note that the wrap characters (#) surrounding the bolded data characters field1, field2, and field3 have been removed.</span></span>  
  
 <span data-ttu-id="f45ec-116">各の元のシーケンスを生成する、フィールドのデータの文字の前後に囲み文字が挿入、フラット ファイル アセンブラーでは、XML 形式のレコードを同等のフラット ファイル レコードに変換する逆の操作を実行するときにフラット ファイルの文字です。</span><span class="sxs-lookup"><span data-stu-id="f45ec-116">When the flat file assembler performs the reverse operation, converting the XML version of the record to its equivalent flat file record, the wrap characters are inserted before and after the data characters of each of the fields, yielding the original sequence of flat file characters.</span></span>  
  
 <span data-ttu-id="f45ec-117">定義されたエスケープ文字と囲み文字を同時に使用できます。</span><span class="sxs-lookup"><span data-stu-id="f45ec-117">The defined escape character can be used in conjunction with the defined wrap character.</span></span> <span data-ttu-id="f45ec-118">たとえば、Field1 の値が次のように変更されると仮定します (太字で表記)。</span><span class="sxs-lookup"><span data-stu-id="f45ec-118">For example, suppose the value of Field1 is changed as follows (shown in bold type).</span></span>  
  
```  
<Record1>  
    <Field1></Field1>  
    <Field2>field2</Field2>  
    <Field3>field3</Field3>  
</Record1>  
  
```  
  
 <span data-ttu-id="f45ec-119">提供されているレコードとフィールドの定義でこの XML フラグメントをアセンブルすると、フラット ファイルの文字が次の順序で生成されます (エスケープのシャープ記号を太字で表記)。</span><span class="sxs-lookup"><span data-stu-id="f45ec-119">When this XML fragment is assembled, using the record and field definitions provided, the following sequence of flat file characters is produced (the escaped number sign character sequence is shown in bold type).</span></span>  
  
```  
RECORD1#field1#,#field2#,#field3#  
  
```  
  
 <span data-ttu-id="f45ec-120">BizTalk エディターを使用してフラット ファイル スキーマを作成するときにを使用して、スキーマ全体の既定の囲み文字を定義することができます、**既定の囲み文字**と**既定の囲み文字の種類**のプロパティ、**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="f45ec-120">When creating a flat file schema using BizTalk Editor, you can define a default wrap character for the entire schema using the **Default Wrap Character** and **Default Wrap Character Type** properties of the **Schema** node.</span></span> <span data-ttu-id="f45ec-121">次に、この既定の囲み文字または、独自のカスタム フィールドに固有の囲み文字を使用して、使用するスキーマの各フィールドを構成、**囲み文字**と**囲み文字の種類**プロパティ、**フィールド要素**または**フィールド属性**フラット ファイル スキーマのノードです。</span><span class="sxs-lookup"><span data-stu-id="f45ec-121">Then, you can configure each individual field in the schema to either use this default wrap character or a custom, field-specific wrap character using the **Wrap Character** and **Wrap Character Type** properties of the **Field Element** or **Field Attribute** nodes in flat file schemas.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f45ec-122">参照</span><span class="sxs-lookup"><span data-stu-id="f45ec-122">See Also</span></span>  
- [<span data-ttu-id="f45ec-123">フィールドの値の一部として特殊文字を解釈する方法</span><span class="sxs-lookup"><span data-stu-id="f45ec-123">Ways to Interpret Special Characters as Part of a Field Value</span></span>](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)  
- <span data-ttu-id="f45ec-124">文字のプロパティをラップ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span><span class="sxs-lookup"><span data-stu-id="f45ec-124">Wrap character properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span></span>  
    -  <span data-ttu-id="f45ec-125">既定の囲み文字 (フラット ファイル スキーマのノード プロパティ</span><span class="sxs-lookup"><span data-stu-id="f45ec-125">Default Wrap Character (Node Property of Flat File Schemas</span></span>
    -  <span data-ttu-id="f45ec-126">既定囲み文字の種類 (フラット ファイル スキーマのノード プロパティ</span><span class="sxs-lookup"><span data-stu-id="f45ec-126">Default Wrap Character Type (Node Property of Flat File Schemas</span></span>
    -  <span data-ttu-id="f45ec-127">囲み文字 (フラット ファイル スキーマのノード プロパティ</span><span class="sxs-lookup"><span data-stu-id="f45ec-127">Wrap Character (Node Property of Flat File Schemas</span></span>  
    -  <span data-ttu-id="f45ec-128">囲み文字の種類 (フラット ファイル スキーマのノード プロパティ</span><span class="sxs-lookup"><span data-stu-id="f45ec-128">Wrap Character Type (Node Property of Flat File Schemas</span></span>