---
title: テーブル ループ Functoid |Microsoft ドキュメント
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
ms.openlocfilehash: 6c5e5f2967fb48bfe896c26246db1630266812f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278242"
---
# <a name="table-looping-functoid"></a><span data-ttu-id="29021-102">テーブル ループ Functoid</span><span class="sxs-lookup"><span data-stu-id="29021-102">Table Looping Functoid</span></span>
<span data-ttu-id="29021-103">**テーブル ループ**functoid では、出力インスタンス メッセージの作成に使用する出力値のテーブルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="29021-103">The **Table Looping** functoid enables you to create a table of output values to use in creating the output instance message.</span></span> <span data-ttu-id="29021-104">テーブル内のデータには、リンクおよび定数を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="29021-104">The data in the table can consist of links and constants.</span></span> <span data-ttu-id="29021-105">最初の入力パラメーター、**テーブル ループ**functoid は、スコープを構成するか、何回レコードがループします。</span><span class="sxs-lookup"><span data-stu-id="29021-105">The first input parameter to the **Table Looping** functoid configures the scope, or how many times the records will loop.</span></span> <span data-ttu-id="29021-106">2 番目の入力パラメーター、**テーブル ループ**functoid では、テーブルに列の数を決定し、残りの入力が順不同でセル、テーブルの値を定義します。</span><span class="sxs-lookup"><span data-stu-id="29021-106">The second input parameter for the **Table Looping** functoid determines how many columns are in the table, and the remaining inputs define possible cell values for the table, in no particular order.</span></span> <span data-ttu-id="29021-107">これらのプロパティの使用の詳細については、次を参照してください。 [Table-Driven ループの構成](../core/table-driven-looping-configuration.md)です。</span><span class="sxs-lookup"><span data-stu-id="29021-107">For more information about working with these properties, see [Table-Driven Looping Configuration](../core/table-driven-looping-configuration.md).</span></span> <span data-ttu-id="29021-108">参照してください[Table-Driven ループ例](../core/table-driven-looping-example.md)です。</span><span class="sxs-lookup"><span data-stu-id="29021-108">Also see [Table-Driven Looping Example](../core/table-driven-looping-example.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="29021-109">**テーブル ループ**に接続されているループ レコードに functoid が繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="29021-109">The **Table Looping** functoid repeats with the looping record it is connected to.</span></span> <span data-ttu-id="29021-110">個々の繰り返し処理では、テーブル ループ グリッドの各行につき 1 回のループ処理が実行され、結果的に複数の出力ループが生成されます。</span><span class="sxs-lookup"><span data-stu-id="29021-110">Within each iteration, it loops once per row in the table looping grid, producing multiple output loops.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29021-111">参照</span><span class="sxs-lookup"><span data-stu-id="29021-111">See Also</span></span>  
 <span data-ttu-id="29021-112">[テーブル抽出 Functoid](../core/table-extractor-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="29021-112">[Table Extractor Functoid](../core/table-extractor-functoid.md) </span></span>  
 <span data-ttu-id="29021-113">[テーブル ループを追加する方法と、マップにテーブル抽出 Functoid](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="29021-113">[How to Add Table Looping and Table Extractor Functoids to a Map](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="29021-114">[高度な Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="29021-114">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="29021-115">[インデックス Functoid](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="29021-115">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="29021-116">[繰り返し Functoid](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="29021-116">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 <span data-ttu-id="29021-117">[ループ Functoid](../core/looping-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="29021-117">[Looping Functoid](../core/looping-functoid.md) </span></span>  
 [<span data-ttu-id="29021-118">レコード カウント Functoid</span><span class="sxs-lookup"><span data-stu-id="29021-118">Record Count Functoid</span></span>](../core/record-count-functoid.md)