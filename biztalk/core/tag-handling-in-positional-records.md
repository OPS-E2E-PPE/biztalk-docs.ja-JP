---
title: 位置指定レコードの処理をタグ付け |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c85d695-6dc9-4200-a453-dc576832adca
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fe1ec096926dc8737c6657ca99fb3cb90b59673
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291626"
---
# <a name="tag-handling-in-positional-records"></a><span data-ttu-id="e4d15-102">タグは位置指定レコードの処理</span><span class="sxs-lookup"><span data-stu-id="e4d15-102">Tag Handling in Positional Records</span></span>

## <a name="overview"></a><span data-ttu-id="e4d15-103">概要</span><span class="sxs-lookup"><span data-stu-id="e4d15-103">Overview</span></span>
<span data-ttu-id="e4d15-104">位置指定レコードには、よく知られているから別のレコードの種類を 1 つのあいまいさを解消するために使用すると、タグと呼ばれる文字のシーケンスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e4d15-104">Positional records can include a well-known sequence of characters, known as a tag, which can be used to disambiguate one type of record from another.</span></span> <span data-ttu-id="e4d15-105">これにより、適切なを正しく識別するためにフラット ファイル逆アセンブラー**レコード**フラット ファイル レコードを正しく解析に必要な情報を含むスキーマのノード。</span><span class="sxs-lookup"><span data-stu-id="e4d15-105">This allows the flat file disassembler to properly identify the appropriate **Record** node in the schema that contains the information required to correctly parse the flat file record.</span></span>  
  
 <span data-ttu-id="e4d15-106">使用することができます、 **[タグ識別子**と**タグ オフセット**プロパティ、タグと位置指定レコード内の位置を指定するためにします。</span><span class="sxs-lookup"><span data-stu-id="e4d15-106">You can use the **[Tag Identifier** and **Tag Offset** properties together to specify the tag and its position within a positional record.</span></span> <span data-ttu-id="e4d15-107">これにより、タグの設定によって、位置指定レコードと内で発生することに注意してください、**位置指定値**と**位置指定オフセット**内のさまざまなフィールドのプロパティレコードのタグは、1 つに関連付けられているデータの一部として解釈できるまたはこれらのフィールドします。</span><span class="sxs-lookup"><span data-stu-id="e4d15-107">Note that this allows the tag to occur anywhere within the positional record and that depending on your settings for the **Positional Length** and **Positional Offset** properties of the various fields within the record, the tag can be interpreted as part of data associated with one or more of these fields.</span></span>  
  
 <span data-ttu-id="e4d15-108">**位置指定オフセット**プロパティでは、レコード内のデータから、タグを個別に処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="e4d15-108">The **Positional Offset** property also allows you to treat the tag separately from the data in the record.</span></span> <span data-ttu-id="e4d15-109">たとえば、タグは、レコードの先頭が発生し、4 文字の長さの場合、は、値を設定できます、**位置指定オフセット**4 つ、これにより効率的にスキップするレコードの最初のフィールドのプロパティ、最初のフィールドの値がレコードの同等の XML 形式に変換するときの位置指定レコードのタグ。</span><span class="sxs-lookup"><span data-stu-id="e4d15-109">For example, if the tag occurs at the beginning of the record and is four characters in length, you could set the value of the **Positional Offset** property of the first field in the record to four, thereby effectively skipping over the positional record tag when the value of the first field is translated in the equivalent XML format of the record.</span></span>  

<span data-ttu-id="e4d15-110">これらのプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e4d15-110">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e4d15-111">参照</span><span class="sxs-lookup"><span data-stu-id="e4d15-111">See Also</span></span>  
 [<span data-ttu-id="e4d15-112">位置指定レコードに関する注意</span><span class="sxs-lookup"><span data-stu-id="e4d15-112">Positional Record Considerations</span></span>](../core/positional-record-considerations.md)   
