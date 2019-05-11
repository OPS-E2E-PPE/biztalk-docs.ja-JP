---
title: フィールドに関する考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d7f1853-60ed-49c2-a592-61bde5445d36
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2dfcc57be3e28a2882f1430cb87c672031dbc496
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388087"
---
# <a name="field-considerations"></a><span data-ttu-id="e418e-102">フィールドに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="e418e-102">Field Considerations</span></span>
<span data-ttu-id="e418e-103">使用する場合は、点に注意する必要がありますの考慮事項がいくつか**フィールド要素**と**フィールド属性**スキーマ内のノード。</span><span class="sxs-lookup"><span data-stu-id="e418e-103">There are a number of considerations that you should keep in mind when working with **Field Element** and **Field Attribute** nodes within your schemas.</span></span> <span data-ttu-id="e418e-104">これには、これらのノードの種類、およびフィールド長、フィールドの位置揃え、およびフィールドの余白の指定に関連する具体的な考慮事項のそれぞれを使用する場合に関する基本的な特徴が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e418e-104">This includes the basic distinctions regarding when to use each of these nodes types, as well as more specific considerations related to the specification of field lengths, field justification, and field padding.</span></span> <span data-ttu-id="e418e-105">このセクションでは、これらの考慮事項についての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e418e-105">This section provides information about these considerations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e418e-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e418e-106">In This Section</span></span>  
  
-   <span data-ttu-id="e418e-107">[[フィールド要素] ノードと[フィールド属性] ノード](../core/field-element-nodes-vs-field-attribute-nodes.md)</span><span class="sxs-lookup"><span data-stu-id="e418e-107">[Field Element Nodes vs. Field Attribute Nodes](../core/field-element-nodes-vs-field-attribute-nodes.md)</span></span>  
  
-   [<span data-ttu-id="e418e-108">カスタム日付時刻形式</span><span class="sxs-lookup"><span data-stu-id="e418e-108">Custom Date-Time Formats</span></span>](../core/custom-date-time-formats.md)  
  
-   [<span data-ttu-id="e418e-109">フィールドへの文字の埋め込み</span><span class="sxs-lookup"><span data-stu-id="e418e-109">Field Padding</span></span>](../core/field-padding.md)  
  
-   [<span data-ttu-id="e418e-110">フィールドの位置揃え</span><span class="sxs-lookup"><span data-stu-id="e418e-110">Field Justification</span></span>](../core/field-justification.md)  
  
-   [<span data-ttu-id="e418e-111">位置指定レコードにおけるフィールド位置の仕様</span><span class="sxs-lookup"><span data-stu-id="e418e-111">Specification of Field Positions within Positional Records</span></span>](../core/specification-of-field-positions-within-positional-records.md)  
  
-   [<span data-ttu-id="e418e-112">区切られたレコードの最小フィールド長</span><span class="sxs-lookup"><span data-stu-id="e418e-112">Minimum Field Lengths Within Delimited Records</span></span>](../core/minimum-field-lengths-within-delimited-records.md)