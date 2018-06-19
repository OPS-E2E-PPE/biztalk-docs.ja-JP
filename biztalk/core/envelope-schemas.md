---
title: エンベロープ スキーマ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af296c30-95dc-4fef-9aa3-bea2f2cd8caf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9008e77e388a93b1750c9b9ba34679ed519db459
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970608"
---
# <a name="envelope-schemas"></a><span data-ttu-id="ea749-102">エンベロープ スキーマ</span><span class="sxs-lookup"><span data-stu-id="ea749-102">Envelope Schemas</span></span>

## <a name="overview"></a><span data-ttu-id="ea749-103">概要</span><span class="sxs-lookup"><span data-stu-id="ea749-103">Overview</span></span>
<span data-ttu-id="ea749-104">エンベロープ スキーマは、ビジネス ドキュメントの XML スキーマを作成するときとまったく同じように作成できます。</span><span class="sxs-lookup"><span data-stu-id="ea749-104">You can create an envelope schema in all of the same ways that you can create an XML schema for a business document.</span></span> <span data-ttu-id="ea749-105">スキーマは、整形式 XML のエンベロープ インスタンス メッセージから作成することも、ドキュメント型定義 (DTD) または XDR (XML-Data Reduced) 形式のエンベロープ スキーマから作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ea749-105">You can create a schema from a well-formed XML envelope instance message, or from Document Type Definition (DTD) or XML-Data reduced (XDR) representations of the envelope schema.</span></span> <span data-ttu-id="ea749-106">あるいは、他のスキーマと組み合わせて新しいスキーマを作成したり、まったく新しいスキーマを一から作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ea749-106">Or, you can create a new schema, either in conjunction with other schemas or not.</span></span> <span data-ttu-id="ea749-107">一般に、エンベロープ スキーマは、ビジネス ドキュメント スキーマよりも小規模かつ単純であるため、新しいエンベロープ スキーマを作成してもそれほど手間はかかりません。</span><span class="sxs-lookup"><span data-stu-id="ea749-107">Because envelope schemas are generally much smaller and less complicated than most business document schemas, creating new envelope schemas is usually a viable alternative.</span></span>  
  
 <span data-ttu-id="ea749-108">エンベロープ スキーマとしてスキーマを定義するには、設定する必要があります、**エンベロープ**のプロパティ、**スキーマ**値ノード**はい**です。</span><span class="sxs-lookup"><span data-stu-id="ea749-108">To define a schema as an envelope schema, you need to set the **Envelope** property of the **Schema** node to the value **Yes**.</span></span> <span data-ttu-id="ea749-109">エンベロープ スキーマを定義するときは、エンベロープをポイントする必要があります**ボディ XPath**のみを含む親ノードに、\<任意\>子要素です。</span><span class="sxs-lookup"><span data-stu-id="ea749-109">When you define an envelope schema, you should point the envelope's **Body XPath** to the parent node that contains only the \<any\> child element.</span></span> <span data-ttu-id="ea749-110">親ノードに他の要素が含まれていると、XML アセンブラーがそのエンベロープを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ea749-110">In order for the XML assembler to use the envelope, the parent node must not contain any other elements.</span></span>  
  
 <span data-ttu-id="ea749-111">設定すると**エンベロープ**プロパティを**はい**、(メッセージの本文と呼ばれます)、XML インスタンス メッセージの実際のメッセージの内容が、ルート内のどこかに存在することを意味**レコード**で指定したとおり、このスキーマのノード、**ボディ XPath**そのノードのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="ea749-111">When you set **Envelope** property to **Yes**, it means that the actual message content of the XML instance message (called the body of the message) is present somewhere inside the root **Record** node of this schema, as specified by the **Body XPath** property of that node.</span></span> <span data-ttu-id="ea749-112">したがって、さまざまな条件に基づいて、追加のプロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea749-112">Therefore, you must also set additional properties based on a variety of conditions:</span></span>  
  
-   <span data-ttu-id="ea749-113">設定する必要があります、エンベロープ スキーマに単一のルートがある場合、**ボディ XPath**そのルートのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="ea749-113">If an envelope schema has a single root, you must set the **Body XPath** property for that root.</span></span>  
  
-   <span data-ttu-id="ea749-114">エンベロープ スキーマに複数のルートがある場合、**ルート参照**プロパティが設定されていない、設定する必要があります、**ボディ XPath**のすべてのルートのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="ea749-114">If an envelope schema has multiple roots and the **Root Reference** property is not set, you must set the **Body XPath** property for all roots.</span></span>  
  
-   <span data-ttu-id="ea749-115">エンベロープ スキーマに複数のルートがある場合、**ルート参照**プロパティが設定されて、設定する必要があります、**ボディ XPath** 、対応するルートのプロパティ**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="ea749-115">If an envelope schema has multiple roots and the **Root Reference** property is set, you must set the **Body XPath** property of the corresponding root **Record** node.</span></span> <span data-ttu-id="ea749-116">必要に応じて設定することができます、**ボディ XPath**残りのルートのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="ea749-116">You can optionally set the **Body XPath** property for the remaining roots.</span></span>  
  
-   <span data-ttu-id="ea749-117">エンベロープ スキーマが単一のルートまたは複数のルートの設定にあるかどうかに関係なく、 **[ルート参照**プロパティは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ea749-117">Regardless of whether an envelope schema has a single root or multiple roots, setting the **[Root Reference** property is not required.</span></span>  

<span data-ttu-id="ea749-118">これらのプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ea749-118">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ea749-119">参照</span><span class="sxs-lookup"><span data-stu-id="ea749-119">See Also</span></span>  
 <span data-ttu-id="ea749-120">[BizTalk スキーマの種類](../core/different-types-of-biztalk-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="ea749-120">[Different Types of BizTalk Schemas](../core/different-types-of-biztalk-schemas.md) </span></span>  
 [<span data-ttu-id="ea749-121">エンベロープ用スキーマを作成する方法</span><span class="sxs-lookup"><span data-stu-id="ea749-121">How to Create Schemas for Envelopes</span></span>](../core/how-to-create-schemas-for-envelopes.md)