---
title: テーブル ループ Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Table Looping functoids
- Table Looping functoids, about Table Looping functoids
ms.assetid: 6189a789-afe7-4e72-a778-2b0374db8f69
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 140d173f9aa037174190d03bffad181423dfab5d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291682"
---
# <a name="table-looping-functoid"></a><span data-ttu-id="ff152-102">テーブル ループ Functoid</span><span class="sxs-lookup"><span data-stu-id="ff152-102">Table Looping Functoid</span></span>
<span data-ttu-id="ff152-103">**テーブル ループ**functoid では、出力インスタンス メッセージの作成に使用する出力値のテーブルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ff152-103">The **Table Looping** functoid enables you to create a table of output values to use in creating the output instance message.</span></span> <span data-ttu-id="ff152-104">テーブル内のデータは、リンクおよび定数で構成できます。</span><span class="sxs-lookup"><span data-stu-id="ff152-104">The data in the table can consist of links and constants.</span></span> <span data-ttu-id="ff152-105">最初の入力パラメーター、**テーブル ループ**functoid は、スコープを構成します。 または、何回レコードがループします。</span><span class="sxs-lookup"><span data-stu-id="ff152-105">The first input parameter to the **Table Looping** functoid configures the scope, or how many times the records will loop.</span></span> <span data-ttu-id="ff152-106">2 番目のパラメーターの入力、**テーブル ループ**functoid によって列の数は、テーブル、および残りの入力は、任意の順序で、テーブルのセル値を定義します。</span><span class="sxs-lookup"><span data-stu-id="ff152-106">The second input parameter for the **Table Looping** functoid determines how many columns are in the table, and the remaining inputs define possible cell values for the table, in no particular order.</span></span> <span data-ttu-id="ff152-107">これらのプロパティの使用方法の詳細については、次を参照してください。 [Table-Driven ループの構成](../core/table-driven-looping-configuration.md)します。</span><span class="sxs-lookup"><span data-stu-id="ff152-107">For more information about working with these properties, see [Table-Driven Looping Configuration](../core/table-driven-looping-configuration.md).</span></span> <span data-ttu-id="ff152-108">参照してください[Table-Driven ループ例](../core/table-driven-looping-example.md)します。</span><span class="sxs-lookup"><span data-stu-id="ff152-108">Also see [Table-Driven Looping Example](../core/table-driven-looping-example.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff152-109">**テーブル ループ**functoid に接続されているループ レコードに繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="ff152-109">The **Table Looping** functoid repeats with the looping record it is connected to.</span></span> <span data-ttu-id="ff152-110">各反復処理内でテーブル ループ グリッドの各行は、複数の出力を生成するループに 1 回のループします。</span><span class="sxs-lookup"><span data-stu-id="ff152-110">Within each iteration, it loops once per row in the table looping grid, producing multiple output loops.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff152-111">参照</span><span class="sxs-lookup"><span data-stu-id="ff152-111">See Also</span></span>  
 <span data-ttu-id="ff152-112">[テーブル抽出 Functoid](../core/table-extractor-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="ff152-112">[Table Extractor Functoid](../core/table-extractor-functoid.md) </span></span>  
 <span data-ttu-id="ff152-113">[マップにテーブル抽出 Functoid およびテーブル ループを追加する方法](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="ff152-113">[How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="ff152-114">[高度な Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="ff152-114">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="ff152-115">[インデックス Functoid](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="ff152-115">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="ff152-116">[繰り返し Functoid](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="ff152-116">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 <span data-ttu-id="ff152-117">[ループ Functoid](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="ff152-117">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="ff152-118">レコード カウント Functoid</span><span class="sxs-lookup"><span data-stu-id="ff152-118">Record Count Functoid</span></span>](../core/record-count-functoid.md)