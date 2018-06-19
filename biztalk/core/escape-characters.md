---
title: エスケープ文字 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3af800b9-d31b-487a-9a06-6eda47d1574e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e961a205b77a9944a497d6e6cbed0df71f63e03
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246130"
---
# <a name="escape-characters"></a><span data-ttu-id="f2729-102">エスケープ文字</span><span class="sxs-lookup"><span data-stu-id="f2729-102">Escape Characters</span></span>

## <a name="overview"></a><span data-ttu-id="f2729-103">概要</span><span class="sxs-lookup"><span data-stu-id="f2729-103">Overview</span></span>
<span data-ttu-id="f2729-104">エスケープ文字とは、特殊な意味を持つ文字の前に置くことによって、その意味を無効化させることのできる単一の文字のことです。</span><span class="sxs-lookup"><span data-stu-id="f2729-104">An escape character is a single character that suppresses any special meaning of the character that follows it.</span></span> <span data-ttu-id="f2729-105">たとえば、次のような特性を持つフラット ファイル レコードを定義したとします。</span><span class="sxs-lookup"><span data-stu-id="f2729-105">For example, if you define a flat file record as having the following characteristics:</span></span>  
  
-   <span data-ttu-id="f2729-106">名前 = Record1</span><span class="sxs-lookup"><span data-stu-id="f2729-106">Name = Record1</span></span>  
  
-   <span data-ttu-id="f2729-107">[区切り記号]</span><span class="sxs-lookup"><span data-stu-id="f2729-107">Delimited</span></span>  
  
-   <span data-ttu-id="f2729-108">子区切り記号 = コンマ (,)</span><span class="sxs-lookup"><span data-stu-id="f2729-108">Child delimiter = comma character (,)</span></span>  
  
-   <span data-ttu-id="f2729-109">子の順序 = 接頭辞</span><span class="sxs-lookup"><span data-stu-id="f2729-109">Child order = prefix</span></span>  
  
-   <span data-ttu-id="f2729-110">エスケープ文字 = 円記号 (\\)</span><span class="sxs-lookup"><span data-stu-id="f2729-110">Escape character = backslash character (\\)</span></span>  
  
-   <span data-ttu-id="f2729-111">タグ = RECORD1</span><span class="sxs-lookup"><span data-stu-id="f2729-111">Tag = RECORD1</span></span>  
  
-   <span data-ttu-id="f2729-112">2 つのフィールド (Field1 および Field2)</span><span class="sxs-lookup"><span data-stu-id="f2729-112">Two fields named Field1 and Field2</span></span>  
  
 <span data-ttu-id="f2729-113">今度は、このレコードに次のようなフラット ファイル データを適用したとします。</span><span class="sxs-lookup"><span data-stu-id="f2729-113">Then the following flat file data applies for the record.</span></span>  
  
```  
RECORD1,testfield1\,testfield1,testfield2  
                  ^^  
  
```  
  
 <span data-ttu-id="f2729-114">このデータは、次のような XML に逆アセンブルされます。</span><span class="sxs-lookup"><span data-stu-id="f2729-114">The data will be disassembled into the following fragment of XML.</span></span>  
  
```  
<Record1>  
    <Field1>testfield1,testfield1</Field1>  
    <Field2>testfield2</Field2>  
</Record1>  
  
```  
  
 <span data-ttu-id="f2729-115">変換後の XML レコードを見ると、フラット ファイル レコードに続く行で、エスケープ文字の指定された部分 (`\,`) が単一のコンマ文字に変換され、エスケープ文字は Field1 のデータに現れない点に注目してください。</span><span class="sxs-lookup"><span data-stu-id="f2729-115">Note that the escape character sequence `\,` indicated on the line following the flat file record, has been converted to a single comma character without the escape character in the data for Field1 in the equivalent XML record.</span></span> <span data-ttu-id="f2729-116">また、他の 2 つのコンマとは異なり、コンマ文字はフィールド区切り記号としては解釈されません。</span><span class="sxs-lookup"><span data-stu-id="f2729-116">Furthermore, that comma character was not interpreted as a field delimiter like the other two commas are.</span></span>  
  
 <span data-ttu-id="f2729-117">フラット ファイル アセンブラーが逆の操作を実行 (つまり、XML 形式のレコードを対応するフラット ファイル レコードに変換) した後の Field1 には、コンマの前に、そのデータがフィールド区切り記号ではないことを示すエスケープ文字が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="f2729-117">When the flat file assembler performs the reverse operation, converting the XML version of the record to its equivalent flat file record, the escape character will be inserted before the comma in the middle of Field1, thereby indicating that it should be interpreted as data rather than as a field delimiter.</span></span>  
  
 <span data-ttu-id="f2729-118">BizTalk エディターを使用してフラット ファイル スキーマを作成するときにを使用して、スキーマ全体に対する既定のエスケープ文字を定義することができます、**既定のエスケープ文字**と**既定のエスケープ文字の種類**プロパティ**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="f2729-118">When creating a flat file schema using BizTalk Editor, you can define a default escape character for the entire schema using the **Default Escape Character** and **Default Escape Character Type** properties of the **Schema** node.</span></span> <span data-ttu-id="f2729-119">次に、この既定のエスケープ文字またはカスタムのレコードに固有のエスケープ文字を使用して、使用するスキーマで個々 のレコードを構成できる、**エスケープ文字]** と**エスケープ文字の種類**のプロパティ、**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="f2729-119">Then, you can configure each individual record in the schema to either use this default escape character or a custom, record-specific escape character using the **Escape Character]** and **Escape Character Type** properties of the **Record** node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2729-120">参照</span><span class="sxs-lookup"><span data-stu-id="f2729-120">See Also</span></span>  
- [<span data-ttu-id="f2729-121">フィールドの値の一部として特殊文字を解釈する方法</span><span class="sxs-lookup"><span data-stu-id="f2729-121">Ways to Interpret Special Characters as Part of a Field Value</span></span>](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)  
- <span data-ttu-id="f2729-122">エスケープ文字プロパティ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span><span class="sxs-lookup"><span data-stu-id="f2729-122">Escape character properties  [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span></span>  
    - <span data-ttu-id="f2729-123">既定のエスケープ文字 (フラット ファイル スキーマのノード プロパティ)</span><span class="sxs-lookup"><span data-stu-id="f2729-123">Default Escape Character (Node Property of Flat File Schemas)</span></span>
    - <span data-ttu-id="f2729-124">既定のエスケープ文字の種類 (フラット ファイル スキーマのノード プロパティ)</span><span class="sxs-lookup"><span data-stu-id="f2729-124">Default Escape Character Type (Node Property of Flat File Schemas)</span></span>
    - <span data-ttu-id="f2729-125">エスケープ文字 (フラット ファイル スキーマのノード プロパティ)</span><span class="sxs-lookup"><span data-stu-id="f2729-125">Escape Character (Node Property of Flat File Schemas)</span></span>  
    - <span data-ttu-id="f2729-126">エスケープ文字の種類 (フラット ファイル スキーマのノード プロパティ)</span><span class="sxs-lookup"><span data-stu-id="f2729-126">Escape Character Type (Node Property of Flat File Schemas)</span></span>