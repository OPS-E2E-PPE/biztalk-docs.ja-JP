---
title: 文字のエスケープ |Microsoft Docs
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
ms.openlocfilehash: 5f6f1ff202c1ffa96bc696415ab7ec1024ae57e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970651"
---
# <a name="escape-characters"></a><span data-ttu-id="fb780-102">エスケープ文字</span><span class="sxs-lookup"><span data-stu-id="fb780-102">Escape Characters</span></span>

## <a name="overview"></a><span data-ttu-id="fb780-103">概要</span><span class="sxs-lookup"><span data-stu-id="fb780-103">Overview</span></span>
<span data-ttu-id="fb780-104">エスケープ文字とは、特殊な意味を持つ文字の前に置くことによって、その意味を無効化させることのできる単一の文字のことです。</span><span class="sxs-lookup"><span data-stu-id="fb780-104">An escape character is a single character that suppresses any special meaning of the character that follows it.</span></span> <span data-ttu-id="fb780-105">たとえば、次のような特性を持つフラット ファイル レコードを定義したとします。</span><span class="sxs-lookup"><span data-stu-id="fb780-105">For example, if you define a flat file record as having the following characteristics:</span></span>  
  
- <span data-ttu-id="fb780-106">名前 = Record1</span><span class="sxs-lookup"><span data-stu-id="fb780-106">Name = Record1</span></span>  
  
- <span data-ttu-id="fb780-107">[区切り記号]</span><span class="sxs-lookup"><span data-stu-id="fb780-107">Delimited</span></span>  
  
- <span data-ttu-id="fb780-108">子区切り記号 = コンマ (,)</span><span class="sxs-lookup"><span data-stu-id="fb780-108">Child delimiter = comma character (,)</span></span>  
  
- <span data-ttu-id="fb780-109">子の順序 = 接頭辞</span><span class="sxs-lookup"><span data-stu-id="fb780-109">Child order = prefix</span></span>  
  
- <span data-ttu-id="fb780-110">エスケープ文字 = 円記号 (\\)</span><span class="sxs-lookup"><span data-stu-id="fb780-110">Escape character = backslash character (\\)</span></span>  
  
- <span data-ttu-id="fb780-111">タグ = RECORD1</span><span class="sxs-lookup"><span data-stu-id="fb780-111">Tag = RECORD1</span></span>  
  
- <span data-ttu-id="fb780-112">2 つのフィールド (Field1 および Field2)</span><span class="sxs-lookup"><span data-stu-id="fb780-112">Two fields named Field1 and Field2</span></span>  
  
  <span data-ttu-id="fb780-113">今度は、このレコードに次のようなフラット ファイル データを適用したとします。</span><span class="sxs-lookup"><span data-stu-id="fb780-113">Then the following flat file data applies for the record.</span></span>  
  
```  
RECORD1,testfield1\,testfield1,testfield2  
                  ^^  
  
```  
  
 <span data-ttu-id="fb780-114">このデータは、次のような XML に逆アセンブルされます。</span><span class="sxs-lookup"><span data-stu-id="fb780-114">The data will be disassembled into the following fragment of XML.</span></span>  
  
```  
<Record1>  
    <Field1>testfield1,testfield1</Field1>  
    <Field2>testfield2</Field2>  
</Record1>  
  
```  
  
 <span data-ttu-id="fb780-115">変換後の XML レコードを見ると、フラット ファイル レコードに続く行で、エスケープ文字の指定された部分 (`\,`) が単一のコンマ文字に変換され、エスケープ文字は Field1 のデータに現れない点に注目してください。</span><span class="sxs-lookup"><span data-stu-id="fb780-115">Note that the escape character sequence `\,` indicated on the line following the flat file record, has been converted to a single comma character without the escape character in the data for Field1 in the equivalent XML record.</span></span> <span data-ttu-id="fb780-116">また、他の 2 つのコンマとは異なり、コンマ文字はフィールド区切り記号としては解釈されません。</span><span class="sxs-lookup"><span data-stu-id="fb780-116">Furthermore, that comma character was not interpreted as a field delimiter like the other two commas are.</span></span>  
  
 <span data-ttu-id="fb780-117">フラット ファイル アセンブラーが逆の操作を実行 (つまり、XML 形式のレコードを対応するフラット ファイル レコードに変換) した後の Field1 には、コンマの前に、そのデータがフィールド区切り記号ではないことを示すエスケープ文字が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="fb780-117">When the flat file assembler performs the reverse operation, converting the XML version of the record to its equivalent flat file record, the escape character will be inserted before the comma in the middle of Field1, thereby indicating that it should be interpreted as data rather than as a field delimiter.</span></span>  
  
 <span data-ttu-id="fb780-118">BizTalk エディターを使用してフラット ファイル スキーマを作成するときに使用して、スキーマ全体の既定のエスケープ文字を定義することができます、**既定のエスケープ文字**と**既定のエスケープ文字の種類**プロパティ**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="fb780-118">When creating a flat file schema using BizTalk Editor, you can define a default escape character for the entire schema using the **Default Escape Character** and **Default Escape Character Type** properties of the **Schema** node.</span></span> <span data-ttu-id="fb780-119">次に、この既定のエスケープ文字またはを使用して、カスタム レコードに固有のエスケープ文字を使用するか、スキーマで個々 のレコードを構成、**エスケープ文字]** と**エスケープ文字の種類**のプロパティ、**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="fb780-119">Then, you can configure each individual record in the schema to either use this default escape character or a custom, record-specific escape character using the **Escape Character]** and **Escape Character Type** properties of the **Record** node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb780-120">参照</span><span class="sxs-lookup"><span data-stu-id="fb780-120">See Also</span></span>  
- [<span data-ttu-id="fb780-121">特殊文字をフィールド値の一部として解釈させる方法</span><span class="sxs-lookup"><span data-stu-id="fb780-121">Ways to Interpret Special Characters as Part of a Field Value</span></span>](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)  
- <span data-ttu-id="fb780-122">エスケープ文字プロパティ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span><span class="sxs-lookup"><span data-stu-id="fb780-122">Escape character properties  [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span></span>  
    - <span data-ttu-id="fb780-123">既定のエスケープ文字 (フラット ファイル スキーマのノード プロパティ)</span><span class="sxs-lookup"><span data-stu-id="fb780-123">Default Escape Character (Node Property of Flat File Schemas)</span></span>
    - <span data-ttu-id="fb780-124">既定のエスケープ文字の種類 (フラット ファイル スキーマのノード プロパティ)</span><span class="sxs-lookup"><span data-stu-id="fb780-124">Default Escape Character Type (Node Property of Flat File Schemas)</span></span>
    - <span data-ttu-id="fb780-125">エスケープ文字 (フラット ファイル スキーマのノード プロパティ)</span><span class="sxs-lookup"><span data-stu-id="fb780-125">Escape Character (Node Property of Flat File Schemas)</span></span>  
    - <span data-ttu-id="fb780-126">エスケープ文字の種類 (フラット ファイル スキーマのノード プロパティ)</span><span class="sxs-lookup"><span data-stu-id="fb780-126">Escape Character Type (Node Property of Flat File Schemas)</span></span>