---
title: "テーブル抽出 Functoid |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Table Extractor functoids
- Table Extractor functoids, about Table Extractor functoids
ms.assetid: cb5f6f15-f4e1-46d3-846e-6e2664699b62
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 837762dcf1bd0814494f05712eb7d616cdfa7180
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="table-extractor-functoid"></a><span data-ttu-id="56ed2-102">テーブル抽出 Functoid</span><span class="sxs-lookup"><span data-stu-id="56ed2-102">Table Extractor Functoid</span></span>
<span data-ttu-id="56ed2-103">**テーブル抽出**functoid ときにルーピング グリッドの各行から抽出するには、どのデータを決定する、**テーブル ループ**functoid が行を表示します。</span><span class="sxs-lookup"><span data-stu-id="56ed2-103">The **Table Extractor** functoid determines which data to extract from each row of the looping grid as the **Table Looping** functoid presents the rows.</span></span> <span data-ttu-id="56ed2-104">1 つ必要**テーブル抽出**functoid が各出力フィールドです。</span><span class="sxs-lookup"><span data-stu-id="56ed2-104">You need one **Table Extractor** functoid for each output field.</span></span> <span data-ttu-id="56ed2-105">たとえば、入力インスタンス メッセージのアドレスが 1 つの形式であり、出力インスタンス メッセージで 2 つの形式のアドレスが必要とされるとします。各フォーマットはタグ付きです。</span><span class="sxs-lookup"><span data-stu-id="56ed2-105">For example, suppose your input instance message had an address in a single format, but your output instance message needed the address in two formats with each format tagged.</span></span> <span data-ttu-id="56ed2-106">必要がありますが、**テーブル抽出**functoid、タグおよびアドレスの各要素に対してです。</span><span class="sxs-lookup"><span data-stu-id="56ed2-106">Then you would need a **Table Extractor** functoid for the tag and for each element of the address.</span></span> <span data-ttu-id="56ed2-107">構成の詳細については、**テーブル抽出**functoid を参照してください[Table-Driven ループの構成](../core/table-driven-looping-configuration.md)です。</span><span class="sxs-lookup"><span data-stu-id="56ed2-107">For more information about configuring the **Table Extractor** functoid, see [Table-Driven Looping Configuration](../core/table-driven-looping-configuration.md).</span></span> <span data-ttu-id="56ed2-108">参照してください[Table-Driven ループ例](../core/table-driven-looping-example.md)です。</span><span class="sxs-lookup"><span data-stu-id="56ed2-108">Also see [Table-Driven Looping Example](../core/table-driven-looping-example.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56ed2-109">参照</span><span class="sxs-lookup"><span data-stu-id="56ed2-109">See Also</span></span>  
 <span data-ttu-id="56ed2-110">[テーブル ループ Functoid](../core/table-looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="56ed2-110">[Table Looping Functoid](../core/table-looping-functoid.md) </span></span>  
 <span data-ttu-id="56ed2-111">[テーブル ループを追加する方法と、マップにテーブル抽出 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="56ed2-111">[How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="56ed2-112">[高度な Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="56ed2-112">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="56ed2-113">[インデックス Functoid](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="56ed2-113">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="56ed2-114">[繰り返し Functoid](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="56ed2-114">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 <span data-ttu-id="56ed2-115">[ループ Functoid](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="56ed2-115">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="56ed2-116">レコード カウント Functoid</span><span class="sxs-lookup"><span data-stu-id="56ed2-116">Record Count Functoid</span></span>](../core/record-count-functoid.md)