---
title: マップに Functoid の詳細の追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbec5e9c-65b3-4734-a7fc-4ee66cf26eee
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa2af647b8d39b7cb9d4b451537675ac55927462
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361038"
---
# <a name="adding-advanced-functoids-to-a-map"></a><span data-ttu-id="4c2b3-102">マップへの高度な Functoid の追加</span><span class="sxs-lookup"><span data-stu-id="4c2b3-102">Adding Advanced Functoids to a Map</span></span>
<span data-ttu-id="4c2b3-103">Functoid を**詳細**カテゴリは理解し、基本 functoid として分類された、他のカテゴリで、まとめて functoid よりも使用するより複雑な。</span><span class="sxs-lookup"><span data-stu-id="4c2b3-103">Functoids in the **Advanced** category are more complex to understand and use than the functoids in the other categories, together classified as basic functoids.</span></span> <span data-ttu-id="4c2b3-104">複雑なマップを作成する必要がある場合は、高度な functoid を使用します。</span><span class="sxs-lookup"><span data-stu-id="4c2b3-104">You use advanced functoids when you need more complex maps.</span></span> <span data-ttu-id="4c2b3-105">これらのマップは、レコードをカウントする、さまざまな数のサブレコードを持つレコードをループ処理、または任意の複雑なスクリプトを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c2b3-105">These maps might need to count records, loop through records with a variable number of subrecords, or run an arbitrarily complex script.</span></span>  
  
 <span data-ttu-id="4c2b3-106">このセクションで functoid を追加するための手順について説明します、**詳細**正しく、入力と出力パラメーターの設定などをマップするカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="4c2b3-106">This section provides step-by-step instructions for adding functoids in the **Advanced** category to your maps, including correctly setting their input and output parameters.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4c2b3-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4c2b3-107">In This Section</span></span>  
  
-   [<span data-ttu-id="4c2b3-108">ループ マップに Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="4c2b3-108">How to Add Looping Functoids to a Map</span></span>](../core/how-to-add-looping-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="4c2b3-109">値のマッピング (フラット化) Functoid をマップに追加する方法</span><span class="sxs-lookup"><span data-stu-id="4c2b3-109">How to Add Value Mapping (Flattening) Functoids to a Map</span></span>](../core/how-to-add-value-mapping-flattening-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="4c2b3-110">追加する方法にアサート Functoid をマップ</span><span class="sxs-lookup"><span data-stu-id="4c2b3-110">How to Add Assert Functoids to a Map</span></span>](../core/how-to-add-assert-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="4c2b3-111">マップにテーブル抽出 Functoid およびテーブル ループを追加する方法</span><span class="sxs-lookup"><span data-stu-id="4c2b3-111">How to Add Table Looping and Table Extractor Functoids to a Map</span></span>](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="4c2b3-112">マップにスクリプト Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="4c2b3-112">How to Add Scripting Functoids to a Map</span></span>](../core/how-to-add-scripting-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="4c2b3-113">マップに Nil 値 Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="4c2b3-113">How to Add Nil Value Functoids to a Map</span></span>](../core/how-to-add-nil-value-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="4c2b3-114">値のマッピングをマップに Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="4c2b3-114">How to Add Value Mapping Functoids to a Map</span></span>](../core/how-to-add-value-mapping-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="4c2b3-115">マップに一括コピー Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="4c2b3-115">How to Add Mass Copy Functoids to a Map</span></span>](../core/how-to-add-mass-copy-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="4c2b3-116">マップに繰り返し Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="4c2b3-116">How to Add Iteration Functoids to a Map</span></span>](../core/how-to-add-iteration-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="4c2b3-117">マップにインデックス Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="4c2b3-117">How to Add Index Functoids to a Map</span></span>](../core/how-to-add-index-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="4c2b3-118">マップにレコード カウント Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="4c2b3-118">How to Add Record Count Functoids to a Map</span></span>](../core/how-to-add-record-count-functoids-to-a-map.md)