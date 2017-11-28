---
title: "位置指定レコードの処理をタグ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c85d695-6dc9-4200-a453-dc576832adca
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 804647b3cf43b9b6747b2e5f50e05e38313b03d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tag-handling-in-positional-records"></a><span data-ttu-id="03917-102">位置指定レコードのタグ処理</span><span class="sxs-lookup"><span data-stu-id="03917-102">Tag Handling in Positional Records</span></span>

## <a name="overview"></a><span data-ttu-id="03917-103">概要</span><span class="sxs-lookup"><span data-stu-id="03917-103">Overview</span></span>
<span data-ttu-id="03917-104">位置指定レコードには、特定のタイプのレコードを明確に区別するための、事前に定義された文字列 (タグなど) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="03917-104">Positional records can include a well-known sequence of characters, known as a tag, which can be used to disambiguate one type of record from another.</span></span> <span data-ttu-id="03917-105">これにより、適切なを正しく識別するフラット ファイル逆アセンブラー**レコード**フラット ファイル レコードを正しく解析に必要な情報を含むスキーマのノードです。</span><span class="sxs-lookup"><span data-stu-id="03917-105">This allows the flat file disassembler to properly identify the appropriate **Record** node in the schema that contains the information required to correctly parse the flat file record.</span></span>  
  
 <span data-ttu-id="03917-106">使用することができます、 **[タグ識別子**と**タグ オフセット**プロパティ、タグと位置指定レコード内の位置を指定するためにします。</span><span class="sxs-lookup"><span data-stu-id="03917-106">You can use the **[Tag Identifier** and **Tag Offset** properties together to specify the tag and its position within a positional record.</span></span> <span data-ttu-id="03917-107">これにより、タグ内に発生する任意の場所と、位置指定レコードの設定によって、ことに注意してください、**位置指定値**と**位置指定オフセット**内でさまざまなフィールドのプロパティレコードのタグは、1 つに関連付けられているデータの一部として解釈できるまたはこれらのフィールドです。</span><span class="sxs-lookup"><span data-stu-id="03917-107">Note that this allows the tag to occur anywhere within the positional record and that depending on your settings for the **Positional Length** and **Positional Offset** properties of the various fields within the record, the tag can be interpreted as part of data associated with one or more of these fields.</span></span>  
  
 <span data-ttu-id="03917-108">**位置指定オフセット**プロパティでは、レコード内のデータからタグを個別に処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="03917-108">The **Positional Offset** property also allows you to treat the tag separately from the data in the record.</span></span> <span data-ttu-id="03917-109">たとえば、タグがレコードの先頭に、4 文字の長さの場合は、値を設定でした、**位置指定オフセット**4、これにより効率的にスキップするレコードの最初のフィールドのプロパティ、最初のフィールドの値は、レコードの同等の XML 形式に変換するときにタグを位置指定レコード。</span><span class="sxs-lookup"><span data-stu-id="03917-109">For example, if the tag occurs at the beginning of the record and is four characters in length, you could set the value of the **Positional Offset** property of the first field in the record to four, thereby effectively skipping over the positional record tag when the value of the first field is translated in the equivalent XML format of the record.</span></span>  

<span data-ttu-id="03917-110">これらのプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="03917-110">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="03917-111">参照</span><span class="sxs-lookup"><span data-stu-id="03917-111">See Also</span></span>  
 [<span data-ttu-id="03917-112">位置指定レコードに関する注意点</span><span class="sxs-lookup"><span data-stu-id="03917-112">Positional Record Considerations</span></span>](../core/positional-record-considerations.md)   
