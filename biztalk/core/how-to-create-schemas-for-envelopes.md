---
title: エンベロープ用スキーマの作成方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae1c991c-447f-497e-803c-1cb8cad2846b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c3da9c438de2f6fb6140e33f986631c5bf3e12b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989643"
---
# <a name="create-schemas-for-envelopes"></a><span data-ttu-id="c8c6e-102">エンベロープ用スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="c8c6e-102">Create Schemas for Envelopes</span></span>

## <a name="overview"></a><span data-ttu-id="c8c6e-103">概要</span><span class="sxs-lookup"><span data-stu-id="c8c6e-103">Overview</span></span>
<span data-ttu-id="c8c6e-104">」の説明に従って XML メッセージ スキーマの作成後に[XML メッセージ用スキーマの作成](../core/how-to-create-schemas-for-xml-messages.md)設定、**エンベロープ**のプロパティ、**スキーマ**ノード**を[はい]**.</span><span class="sxs-lookup"><span data-stu-id="c8c6e-104">After creating an XML message schema as described in [Creating Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md), set the **Envelope** property of the **Schema** node to **Yes**.</span></span> <span data-ttu-id="c8c6e-105">複数のルート ノードが存在するかどうかなど、エンベロープ スキーマの特性によっては、エンベロープ固有のプロパティを追加設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8c6e-105">Depending on certain characteristics of your envelope schema, such as whether there are multiple root nodes, you will need to set several other envelope-specific properties.</span></span> <span data-ttu-id="c8c6e-106">詳細については、[エンベロープ スキーマ](../core/envelope-schemas.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c6e-106">For more information, see [Envelope Schemas](../core/envelope-schemas.md).</span></span>  

 <span data-ttu-id="c8c6e-107">エンベロープの "ボディ XPath" プロパティは、ドキュメント要素を格納する要素を示します。</span><span class="sxs-lookup"><span data-stu-id="c8c6e-107">The body XPath property of the envelope points to the element that contains the document elements.</span></span> <span data-ttu-id="c8c6e-108">XPath が指し示す実際の要素が、このドキュメントに属しているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c8c6e-108">The actual element where the XPath points to does not belong to the document.</span></span>  

## <a name="see-also"></a><span data-ttu-id="c8c6e-109">参照</span><span class="sxs-lookup"><span data-stu-id="c8c6e-109">See Also</span></span>  
- [<span data-ttu-id="c8c6e-110">プロジェクト内のスキーマの管理</span><span class="sxs-lookup"><span data-stu-id="c8c6e-110">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)
- <span data-ttu-id="c8c6e-111">**エンベロープ**プロパティ [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="c8c6e-111">**Envelope** property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
