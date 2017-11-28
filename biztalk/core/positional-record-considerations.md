---
title: "位置指定レコードに関する考慮事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f383d34-60a6-430f-ab0f-b1fc35cde568
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7d42dd70b91d3e11231f6d140b6c3b217045a0e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="positional-record-considerations"></a><span data-ttu-id="3b2d2-102">位置指定レコードに関する注意点</span><span class="sxs-lookup"><span data-stu-id="3b2d2-102">Positional Record Considerations</span></span>
<span data-ttu-id="3b2d2-103">おく必要がありますに注意を操作するときに位置指定の考慮事項の数がある**レコード**スキーマ内のノードです。</span><span class="sxs-lookup"><span data-stu-id="3b2d2-103">There are a number of considerations that you should keep in mind when working with positional **Record** nodes within your schemas.</span></span> <span data-ttu-id="3b2d2-104">注意事項には、タグ処理、位置指定レコードの入れ子、位置のカウント方法、およびフィールド位置の計算方法が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3b2d2-104">This includes the considerations about tag handling, positional record nesting, how positions are counted, and how field positions are calculated.</span></span> <span data-ttu-id="3b2d2-105">このセクションでは、これらの注意事項に関する情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="3b2d2-105">This section provides information about these considerations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3b2d2-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3b2d2-106">In This Section</span></span>  
  
-   [<span data-ttu-id="3b2d2-107">位置指定レコードのタグ処理</span><span class="sxs-lookup"><span data-stu-id="3b2d2-107">Tag Handling in Positional Records</span></span>](../core/tag-handling-in-positional-records.md)  
  
-   [<span data-ttu-id="3b2d2-108">入れ子になった位置指定レコード</span><span class="sxs-lookup"><span data-stu-id="3b2d2-108">Nested Positional Records</span></span>](../core/nested-positional-records.md)  
  
-   [<span data-ttu-id="3b2d2-109">位置のカウント (バイト単位)</span><span class="sxs-lookup"><span data-stu-id="3b2d2-109">Position Counting in Bytes</span></span>](../core/position-counting-in-bytes.md)  
  
-   [<span data-ttu-id="3b2d2-110">フィールド位置の計算</span><span class="sxs-lookup"><span data-stu-id="3b2d2-110">Field Position Calculation</span></span>](../core/field-position-calculation.md)