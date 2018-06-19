---
title: Functoid の詳細 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82bf2547-5e44-45f8-b577-97e5760a0339
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5002b639df79ece1019c2d013c128f615517ae5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230394"
---
# <a name="advanced-functoids"></a><span data-ttu-id="d78c6-102">高度な Functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-102">Advanced Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="d78c6-103">概要</span><span class="sxs-lookup"><span data-stu-id="d78c6-103">Overview</span></span>
<span data-ttu-id="d78c6-104">高度な Functoid は、使用目的に応じて次の 5 つのグループに分類されます。</span><span class="sxs-lookup"><span data-stu-id="d78c6-104">Advanced functoids fall into five groups, according to their use:</span></span>  
  
-   <span data-ttu-id="d78c6-105">**ループ レコードを管理します。**</span><span class="sxs-lookup"><span data-stu-id="d78c6-105">**Managing looping records.**</span></span> <span data-ttu-id="d78c6-106">**インデックス**、**イテレーション**、**ループ**、 **Nil 値**、**レコード カウント**、**テーブル抽出**、および**テーブル ループ**入力インスタンス メッセージを含むセクションが不明な場合に、さまざまな組み合わせで functoid が使用される繰り返し出現する要素、ループで表される数送信元スキーマのレコードです。</span><span class="sxs-lookup"><span data-stu-id="d78c6-106">The **Index**, **Iteration**, **Looping**, **Nil Value**, **Record Count**, **Table Extractor**, and **Table Looping** functoids are used in various combinations when the input instance message contains sections with an unpredictable number of repeating elements, as represented by looping records in the source schema.</span></span>  
  
-   <span data-ttu-id="d78c6-107">**条件付きのマッピング。**</span><span class="sxs-lookup"><span data-stu-id="d78c6-107">**Conditional mapping.**</span></span> <span data-ttu-id="d78c6-108">**値のマッピング**と**値のマッピング (フラット化)** functoid は、入力インスタンス メッセージから出力インスタンス メッセージへの条件付きのマッピングを提供するために使用します。</span><span class="sxs-lookup"><span data-stu-id="d78c6-108">The **Value Mapping** and **Value Mapping (Flattening)** functoids are used to provide conditional mapping from an input instance message to an output instance message.</span></span> <span data-ttu-id="d78c6-109">最初の入力パラメーターが true の場合、2 番目の入力パラメーターは、出力インスタンス メッセージの指定された要素または属性に配置されます。それ以外の場合、この要素または属性は、出力インスタンス メッセージに作成されません。</span><span class="sxs-lookup"><span data-stu-id="d78c6-109">When their first input parameter is true, the second input parameter is put into the specified element or attribute in the output instance message; otherwise, that element or attribute is not created in the output instance message.</span></span>  
  
-   <span data-ttu-id="d78c6-110">**任意のスクリプト。**</span><span class="sxs-lookup"><span data-stu-id="d78c6-110">**Arbitrary scripting.**</span></span> <span data-ttu-id="d78c6-111">**スクリプト**functoid は、任意のスクリプトを実行するために使用または入力インスタンス メッセージは、出力インスタンス メッセージにマップされているときにコードをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="d78c6-111">The **Scripting** functoid is used to run arbitrary script or compiled code when an input instance message is being mapped to an output instance message.</span></span> <span data-ttu-id="d78c6-112">このようなスクリプトまたはコンパイル済みコードを作成し、送信元インスタンス メッセージ、構成された定数値、別の Functoid の出力、またはこれらの組み合わせから、入力パラメーターを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="d78c6-112">Such script or compiled code can be created so that it accepts input parameters from the source instance message, from configured constant values, from the output of another functoid, or some combination thereof.</span></span>  
  
-   <span data-ttu-id="d78c6-113">**単純なマッピング。**</span><span class="sxs-lookup"><span data-stu-id="d78c6-113">**Simple mapping.**</span></span> <span data-ttu-id="d78c6-114">**一括コピー**出力インスタンス メッセージに入力インスタンス メッセージから任意の深さにサブ要素を含む、要素全体をコピーする functoid を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d78c6-114">The **Mass Copy** functoid can be used to copy an entire element, including its subelements to an arbitrary depth, from an input instance message to an output instance message.</span></span>  
  
-   <span data-ttu-id="d78c6-115">**トラブルシューティング**です。</span><span class="sxs-lookup"><span data-stu-id="d78c6-115">**Troubleshooting**.</span></span> <span data-ttu-id="d78c6-116">**Assert** functoid を使用して要素の値に関する仮定をテストできます。</span><span class="sxs-lookup"><span data-stu-id="d78c6-116">The **Assert** functoid can be used to test your assumptions about element values.</span></span>  
  
## <a name="available-functoids"></a><span data-ttu-id="d78c6-117">使用可能な functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-117">Available functoids</span></span>
  
 <span data-ttu-id="d78c6-118">**詳細**functoid には。</span><span class="sxs-lookup"><span data-stu-id="d78c6-118">The **Advanced** functoids are:</span></span> 

* <span data-ttu-id="d78c6-119">アサート Functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-119">Assert Functoid</span></span>
* <span data-ttu-id="d78c6-120">インデックス Functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-120">Index Functoid</span></span> 
* <span data-ttu-id="d78c6-121">繰り返し Functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-121">Iteration Functoid</span></span> 
* <span data-ttu-id="d78c6-122">ループ Functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-122">Looping Functoid</span></span> 
* <span data-ttu-id="d78c6-123">一括コピー Functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-123">Mass Copy Functoid</span></span> 
* <span data-ttu-id="d78c6-124">Nil 値 Functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-124">Nil Value Functoid</span></span>
* <span data-ttu-id="d78c6-125">レコード カウント Functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-125">Record Count Functoid</span></span> 
* <span data-ttu-id="d78c6-126">スクリプト Functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-126">Scripting Functoid</span></span> 
* <span data-ttu-id="d78c6-127">テーブル ループ functoid とテーブル抽出 Functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-127">Table Looping and Table Extractor Functoids</span></span>
* <span data-ttu-id="d78c6-128">値のマッピング Functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-128">Value Mapping Functoid</span></span>
* <span data-ttu-id="d78c6-129">値のマッピング (フラット化) Functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-129">Value Mapping (Flattening) Functoid</span></span>

<span data-ttu-id="d78c6-130">これらの functoid の詳細については、 **Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="d78c6-130">More details on these functoids are in the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="d78c6-131">次の手順</span><span class="sxs-lookup"><span data-stu-id="d78c6-131">Next steps</span></span>
  
-   [<span data-ttu-id="d78c6-132">アサート Functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-132">Assert Functoid</span></span>](../core/assert-functoid.md)  
  
-   [<span data-ttu-id="d78c6-133">インデックス Functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-133">Index Functoid</span></span>](../core/index-functoid.md)  
  
-   [<span data-ttu-id="d78c6-134">繰り返し Functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-134">Iteration Functoid</span></span>](../core/iteration-functoid.md)  
  
-   [<span data-ttu-id="d78c6-135">ループ Functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-135">Looping Functoid</span></span>](../core/looping-functoid.md)  
  
-   [<span data-ttu-id="d78c6-136">一括コピー Functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-136">Mass Copy Functoid</span></span>](../core/mass-copy-functoid.md)  
  
-   [<span data-ttu-id="d78c6-137">Nil 値 Functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-137">Nil Value Functoid</span></span>](../core/nil-value-functoid.md)  
  
-   [<span data-ttu-id="d78c6-138">レコード カウント Functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-138">Record Count Functoid</span></span>](../core/record-count-functoid.md)  
  
-   [<span data-ttu-id="d78c6-139">テーブル ループ functoid とテーブル抽出 Functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-139">Table Looping and Table Extractor Functoids</span></span>](../core/table-looping-and-table-extractor-functoids.md)  
  
-   [<span data-ttu-id="d78c6-140">値のマッピング Functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-140">Value Mapping Functoid</span></span>](../core/value-mapping-functoid.md)  
  
-   [<span data-ttu-id="d78c6-141">値のマッピング (フラット化) Functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-141">Value Mapping (Flattening) Functoid</span></span>](../core/value-mapping-flattening-functoid.md)  
  
-   [<span data-ttu-id="d78c6-142">スクリプト Functoid</span><span class="sxs-lookup"><span data-stu-id="d78c6-142">Scripting Functoid</span></span>](../core/scripting-functoid.md)