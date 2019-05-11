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
ms.openlocfilehash: 255236d6a28ee82fa4131b2189a97c9d0962c7d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339003"
---
# <a name="create-schemas-for-envelopes"></a><span data-ttu-id="e59fd-102">エンベロープ用スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="e59fd-102">Create Schemas for Envelopes</span></span>

## <a name="overview"></a><span data-ttu-id="e59fd-103">概要</span><span class="sxs-lookup"><span data-stu-id="e59fd-103">Overview</span></span>
<span data-ttu-id="e59fd-104">」の説明に従って XML メッセージ スキーマの作成後に[XML メッセージ用スキーマの作成](../core/how-to-create-schemas-for-xml-messages.md)設定、**エンベロープ**のプロパティ、**スキーマ**ノード**を[はい]**.</span><span class="sxs-lookup"><span data-stu-id="e59fd-104">After creating an XML message schema as described in [Creating Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md), set the **Envelope** property of the **Schema** node to **Yes**.</span></span> <span data-ttu-id="e59fd-105">複数のルート ノードが存在するかどうかなど、エンベロープ スキーマの特性によっては、エンベロープ固有のプロパティを追加設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e59fd-105">Depending on certain characteristics of your envelope schema, such as whether there are multiple root nodes, you will need to set several other envelope-specific properties.</span></span> <span data-ttu-id="e59fd-106">詳細については、次を参照してください。[エンベロープ スキーマ](../core/envelope-schemas.md)します。</span><span class="sxs-lookup"><span data-stu-id="e59fd-106">For more information, see [Envelope Schemas](../core/envelope-schemas.md).</span></span>  

 <span data-ttu-id="e59fd-107">エンベロープの "ボディ XPath" プロパティは、ドキュメント要素を格納する要素を示します。</span><span class="sxs-lookup"><span data-stu-id="e59fd-107">The body XPath property of the envelope points to the element that contains the document elements.</span></span> <span data-ttu-id="e59fd-108">XPath が指し示す実際の要素が、このドキュメントに属しているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="e59fd-108">The actual element where the XPath points to does not belong to the document.</span></span>  

## <a name="see-also"></a><span data-ttu-id="e59fd-109">参照</span><span class="sxs-lookup"><span data-stu-id="e59fd-109">See Also</span></span>  
- [<span data-ttu-id="e59fd-110">プロジェクト内のスキーマの管理</span><span class="sxs-lookup"><span data-stu-id="e59fd-110">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)
- <span data-ttu-id="e59fd-111">**エンベロープ**プロパティ [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="e59fd-111">**Envelope** property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
