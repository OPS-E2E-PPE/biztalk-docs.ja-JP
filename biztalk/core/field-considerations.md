---
title: フィールドに関する考慮事項 |Microsoft ドキュメント
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
ms.openlocfilehash: 861f8d8bacb7c0110c9ccbfdf55f8f0547c79bad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245786"
---
# <a name="field-considerations"></a><span data-ttu-id="8368f-102">フィールドに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="8368f-102">Field Considerations</span></span>
<span data-ttu-id="8368f-103">使用する場合は、点に注意する必要がありますの考慮事項の数がある**フィールド要素**と**フィールド属性**スキーマ内のノードです。</span><span class="sxs-lookup"><span data-stu-id="8368f-103">There are a number of considerations that you should keep in mind when working with **Field Element** and **Field Attribute** nodes within your schemas.</span></span> <span data-ttu-id="8368f-104">注意事項としては、これらの各ノードの使用時期に関する基本的な相違点に関するものがあります。また、フィールド長、フィールドの位置揃え、およびフィールドへの文字の埋め込みの設定に関する注意事項もあります。</span><span class="sxs-lookup"><span data-stu-id="8368f-104">This includes the basic distinctions regarding when to use each of these nodes types, as well as more specific considerations related to the specification of field lengths, field justification, and field padding.</span></span> <span data-ttu-id="8368f-105">このセクションでは、これらの注意事項に関する情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="8368f-105">This section provides information about these considerations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8368f-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8368f-106">In This Section</span></span>  
  
-   [<span data-ttu-id="8368f-107">フィールド要素 ノードとします。フィールド属性 ノード</span><span class="sxs-lookup"><span data-stu-id="8368f-107">Field Element Nodes vs. Field Attribute Nodes</span></span>](../core/field-element-nodes-vs-field-attribute-nodes.md)  
  
-   [<span data-ttu-id="8368f-108">カスタムの日付/時刻書式</span><span class="sxs-lookup"><span data-stu-id="8368f-108">Custom Date-Time Formats</span></span>](../core/custom-date-time-formats.md)  
  
-   [<span data-ttu-id="8368f-109">フィールドの埋め込み</span><span class="sxs-lookup"><span data-stu-id="8368f-109">Field Padding</span></span>](../core/field-padding.md)  
  
-   [<span data-ttu-id="8368f-110">フィールドの位置揃え</span><span class="sxs-lookup"><span data-stu-id="8368f-110">Field Justification</span></span>](../core/field-justification.md)  
  
-   [<span data-ttu-id="8368f-111">位置指定レコードにおけるフィールド位置の仕様</span><span class="sxs-lookup"><span data-stu-id="8368f-111">Specification of Field Positions within Positional Records</span></span>](../core/specification-of-field-positions-within-positional-records.md)  
  
-   [<span data-ttu-id="8368f-112">区切られたレコード内の最小フィールド長</span><span class="sxs-lookup"><span data-stu-id="8368f-112">Minimum Field Lengths Within Delimited Records</span></span>](../core/minimum-field-lengths-within-delimited-records.md)