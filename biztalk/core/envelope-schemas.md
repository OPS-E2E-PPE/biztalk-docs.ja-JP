---
title: エンベロープ スキーマ |Microsoft Docs
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
ms.openlocfilehash: 7d4637bbe0fcfecea0bf4c6e134eb131935315c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349522"
---
# <a name="envelope-schemas"></a><span data-ttu-id="4b6eb-102">エンベロープ スキーマ</span><span class="sxs-lookup"><span data-stu-id="4b6eb-102">Envelope Schemas</span></span>

## <a name="overview"></a><span data-ttu-id="4b6eb-103">概要</span><span class="sxs-lookup"><span data-stu-id="4b6eb-103">Overview</span></span>
<span data-ttu-id="4b6eb-104">すべてのビジネス ドキュメントの XML スキーマを作成する同じ方法では、エンベロープ スキーマを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4b6eb-104">You can create an envelope schema in all of the same ways that you can create an XML schema for a business document.</span></span> <span data-ttu-id="4b6eb-105">スキーマを作成するには、整形式の XML エンベロープ インスタンス メッセージから、またはドキュメント型定義 (DTD) または Xml-data reduced (XDR) エンベロープ スキーマ表現。</span><span class="sxs-lookup"><span data-stu-id="4b6eb-105">You can create a schema from a well-formed XML envelope instance message, or from Document Type Definition (DTD) or XML-Data reduced (XDR) representations of the envelope schema.</span></span> <span data-ttu-id="4b6eb-106">または、かどうかは、他のスキーマと組み合わせて、新しいスキーマを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4b6eb-106">Or, you can create a new schema, either in conjunction with other schemas or not.</span></span> <span data-ttu-id="4b6eb-107">エンベロープ スキーマは一般にはるかに小さいため、ほとんどのビジネス ドキュメント スキーマよりも複雑な少なく新しいエンベロープ スキーマの作成は、通常、利用可能な方法です。</span><span class="sxs-lookup"><span data-stu-id="4b6eb-107">Because envelope schemas are generally much smaller and less complicated than most business document schemas, creating new envelope schemas is usually a viable alternative.</span></span>  
  
 <span data-ttu-id="4b6eb-108">エンベロープ スキーマとしてスキーマを定義するには、設定する必要があります、**エンベロープ**のプロパティ、**スキーマ**ノード値に**はい**します。</span><span class="sxs-lookup"><span data-stu-id="4b6eb-108">To define a schema as an envelope schema, you need to set the **Envelope** property of the **Schema** node to the value **Yes**.</span></span> <span data-ttu-id="4b6eb-109">エンベロープ スキーマを定義するときに、エンベロープをポイントする必要があります**ボディ XPath**のみを含む親ノードに、\<任意\>子要素。</span><span class="sxs-lookup"><span data-stu-id="4b6eb-109">When you define an envelope schema, you should point the envelope's **Body XPath** to the parent node that contains only the \<any\> child element.</span></span> <span data-ttu-id="4b6eb-110">XML アセンブラーのエンベロープを使用するためには、親ノードは、他の要素を含めないでください。</span><span class="sxs-lookup"><span data-stu-id="4b6eb-110">In order for the XML assembler to use the envelope, the parent node must not contain any other elements.</span></span>  
  
 <span data-ttu-id="4b6eb-111">設定すると**エンベロープ**プロパティを**はい**、(メッセージの本文と呼ばれます)、XML インスタンス メッセージの実際のメッセージの内容が、ルート中のどこかに存在することを意味**レコード**で指定したとおり、このスキーマのノード、**ボディ XPath**そのノードのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="4b6eb-111">When you set **Envelope** property to **Yes**, it means that the actual message content of the XML instance message (called the body of the message) is present somewhere inside the root **Record** node of this schema, as specified by the **Body XPath** property of that node.</span></span> <span data-ttu-id="4b6eb-112">そのため、さまざまな条件に基づいて追加のプロパティを設定することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b6eb-112">Therefore, you must also set additional properties based on a variety of conditions:</span></span>  
  
-   <span data-ttu-id="4b6eb-113">設定する必要があるエンベロープ スキーマの単一のルートにある場合、**ボディ XPath**そのルートのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="4b6eb-113">If an envelope schema has a single root, you must set the **Body XPath** property for that root.</span></span>  
  
-   <span data-ttu-id="4b6eb-114">エンベロープ スキーマに複数のルートがある場合、**ルート参照**プロパティが設定されていない、設定する必要があります、**ボディ XPath**のすべてのルートのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="4b6eb-114">If an envelope schema has multiple roots and the **Root Reference** property is not set, you must set the **Body XPath** property for all roots.</span></span>  
  
-   <span data-ttu-id="4b6eb-115">エンベロープ スキーマに複数のルートがある場合、**ルート参照**プロパティの設定は、設定する必要があります、**ボディ XPath**プロパティの対応するルート**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="4b6eb-115">If an envelope schema has multiple roots and the **Root Reference** property is set, you must set the **Body XPath** property of the corresponding root **Record** node.</span></span> <span data-ttu-id="4b6eb-116">必要に応じて設定することができます、**ボディ XPath**残りのルートのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="4b6eb-116">You can optionally set the **Body XPath** property for the remaining roots.</span></span>  
  
-   <span data-ttu-id="4b6eb-117">エンベロープ スキーマにルートを 1 つまたは複数のルートの設定のかどうかに関係なく、 **[ルート参照**プロパティは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="4b6eb-117">Regardless of whether an envelope schema has a single root or multiple roots, setting the **[Root Reference** property is not required.</span></span>  

<span data-ttu-id="4b6eb-118">これらのプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="4b6eb-118">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4b6eb-119">参照</span><span class="sxs-lookup"><span data-stu-id="4b6eb-119">See Also</span></span>  
 <span data-ttu-id="4b6eb-120">[さまざまな種類の BizTalk スキーマ](../core/different-types-of-biztalk-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="4b6eb-120">[Different Types of BizTalk Schemas](../core/different-types-of-biztalk-schemas.md) </span></span>  
 [<span data-ttu-id="4b6eb-121">エンベロープ用スキーマの作成方法</span><span class="sxs-lookup"><span data-stu-id="4b6eb-121">How to Create Schemas for Envelopes</span></span>](../core/how-to-create-schemas-for-envelopes.md)