---
title: 位置指定レコードに関する考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f383d34-60a6-430f-ab0f-b1fc35cde568
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96a03a10f14123f001ee100e65a3a423f362d94f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396214"
---
# <a name="positional-record-considerations"></a><span data-ttu-id="9ecba-102">位置指定レコードに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="9ecba-102">Positional Record Considerations</span></span>
<span data-ttu-id="9ecba-103">おく必要がありますに注意を使用する場合位置指定の考慮事項がいくつか**レコード**スキーマ内のノード。</span><span class="sxs-lookup"><span data-stu-id="9ecba-103">There are a number of considerations that you should keep in mind when working with positional **Record** nodes within your schemas.</span></span> <span data-ttu-id="9ecba-104">これには、タグ処理、位置指定レコードの入れ子、位置のカウント方法、およびフィールド位置の計算方法に関する考慮事項が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9ecba-104">This includes the considerations about tag handling, positional record nesting, how positions are counted, and how field positions are calculated.</span></span> <span data-ttu-id="9ecba-105">このセクションでは、これらの考慮事項についての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="9ecba-105">This section provides information about these considerations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9ecba-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9ecba-106">In This Section</span></span>  
  
-   [<span data-ttu-id="9ecba-107">位置指定レコードのタグ処理</span><span class="sxs-lookup"><span data-stu-id="9ecba-107">Tag Handling in Positional Records</span></span>](../core/tag-handling-in-positional-records.md)  
  
-   [<span data-ttu-id="9ecba-108">入れ子になっている位置指定レコード</span><span class="sxs-lookup"><span data-stu-id="9ecba-108">Nested Positional Records</span></span>](../core/nested-positional-records.md)  
  
-   [<span data-ttu-id="9ecba-109">位置のカウント (バイト単位)</span><span class="sxs-lookup"><span data-stu-id="9ecba-109">Position Counting in Bytes</span></span>](../core/position-counting-in-bytes.md)  
  
-   [<span data-ttu-id="9ecba-110">フィールド位置の計算</span><span class="sxs-lookup"><span data-stu-id="9ecba-110">Field Position Calculation</span></span>](../core/field-position-calculation.md)