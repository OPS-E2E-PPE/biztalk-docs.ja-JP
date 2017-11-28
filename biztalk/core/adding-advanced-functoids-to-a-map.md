---
title: "マップに Functoid を 詳細の追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbec5e9c-65b3-4734-a7fc-4ee66cf26eee
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fad75ed2c5c6779801e38f0c4b8f4505696bb476
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adding-advanced-functoids-to-a-map"></a><span data-ttu-id="6b4d7-102">マップへの高度な Functoid の追加</span><span class="sxs-lookup"><span data-stu-id="6b4d7-102">Adding Advanced Functoids to a Map</span></span>
<span data-ttu-id="6b4d7-103">Functoid の**詳細**カテゴリは理解し、基本 functoid として分類された、他のカテゴリで、まとめて functoid よりも使用するより複雑です。</span><span class="sxs-lookup"><span data-stu-id="6b4d7-103">Functoids in the **Advanced** category are more complex to understand and use than the functoids in the other categories, together classified as basic functoids.</span></span> <span data-ttu-id="6b4d7-104">高度 Functoid は、より複雑なマップが必要な場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="6b4d7-104">You use advanced functoids when you need more complex maps.</span></span> <span data-ttu-id="6b4d7-105">このようなマップでは、レコードのカウント、不特定数のサブレコードを持つレコードのループ処理、または複雑なスクリプトの実行などの処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="6b4d7-105">These maps might need to count records, loop through records with a variable number of subrecords, or run an arbitrarily complex script.</span></span>  
  
 <span data-ttu-id="6b4d7-106">このセクションで functoid を追加する手順については、 **[詳細設定]**入力と出力パラメーターを正しく設定するなど、マップにカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="6b4d7-106">This section provides step-by-step instructions for adding functoids in the **Advanced** category to your maps, including correctly setting their input and output parameters.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6b4d7-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6b4d7-107">In This Section</span></span>  
  
-   [<span data-ttu-id="6b4d7-108">マップにループ Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="6b4d7-108">How to Add Looping Functoids to a Map</span></span>](../core/how-to-add-looping-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="6b4d7-109">値のマッピング (フラット化) Functoid をマップに追加する方法</span><span class="sxs-lookup"><span data-stu-id="6b4d7-109">How to Add Value Mapping (Flattening) Functoids to a Map</span></span>](../core/how-to-add-value-mapping-flattening-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="6b4d7-110">追加する方法、マップにアサート Functoid</span><span class="sxs-lookup"><span data-stu-id="6b4d7-110">How to Add Assert Functoids to a Map</span></span>](../core/how-to-add-assert-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="6b4d7-111">テーブル ループを追加する方法と、マップにテーブル抽出 Functoid</span><span class="sxs-lookup"><span data-stu-id="6b4d7-111">How to Add Table Looping and Table Extractor Functoids to a Map</span></span>](../core/how-to-add-table-looping-and-table-extractor-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="6b4d7-112">スクリプト Functoid をマップに追加する方法</span><span class="sxs-lookup"><span data-stu-id="6b4d7-112">How to Add Scripting Functoids to a Map</span></span>](../core/how-to-add-scripting-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="6b4d7-113">マップに Nil 値 Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="6b4d7-113">How to Add Nil Value Functoids to a Map</span></span>](../core/how-to-add-nil-value-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="6b4d7-114">値のマッピング Functoid をマップに追加する方法</span><span class="sxs-lookup"><span data-stu-id="6b4d7-114">How to Add Value Mapping Functoids to a Map</span></span>](../core/how-to-add-value-mapping-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="6b4d7-115">マップに一括コピー Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="6b4d7-115">How to Add Mass Copy Functoids to a Map</span></span>](../core/how-to-add-mass-copy-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="6b4d7-116">繰り返し Functoid をマップに追加する方法</span><span class="sxs-lookup"><span data-stu-id="6b4d7-116">How to Add Iteration Functoids to a Map</span></span>](../core/how-to-add-iteration-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="6b4d7-117">インデックス Functoid をマップに追加する方法</span><span class="sxs-lookup"><span data-stu-id="6b4d7-117">How to Add Index Functoids to a Map</span></span>](../core/how-to-add-index-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="6b4d7-118">マップにレコード カウント Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="6b4d7-118">How to Add Record Count Functoids to a Map</span></span>](../core/how-to-add-record-count-functoids-to-a-map.md)