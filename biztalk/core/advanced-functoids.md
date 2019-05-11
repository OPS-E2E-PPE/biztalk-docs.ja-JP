---
title: Functoid の詳細 |Microsoft Docs
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
ms.openlocfilehash: b0e906b7e1c4d7ca71f952441cd22542e9637399
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360503"
---
# <a name="advanced-functoids"></a><span data-ttu-id="10e5e-102">高度な Functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-102">Advanced Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="10e5e-103">概要</span><span class="sxs-lookup"><span data-stu-id="10e5e-103">Overview</span></span>
<span data-ttu-id="10e5e-104">高度な functoid は、使用目的に応じて、5 つのグループに分類されます。</span><span class="sxs-lookup"><span data-stu-id="10e5e-104">Advanced functoids fall into five groups, according to their use:</span></span>  
  
-   <span data-ttu-id="10e5e-105">**ループ レコードを管理します。**</span><span class="sxs-lookup"><span data-stu-id="10e5e-105">**Managing looping records.**</span></span> <span data-ttu-id="10e5e-106">**インデックス**、**イテレーション**、**ループ**、 **Nil 値**、**レコード カウント**、**テーブルエクス トラクター**、および**テーブル ループ**入力インスタンス メッセージには、予期できないいくつかのセクションが含まれている場合、さまざまな組み合わせで functoid が使用される繰り返し出現する要素、ループで表される数送信元スキーマ内のレコード。</span><span class="sxs-lookup"><span data-stu-id="10e5e-106">The **Index**, **Iteration**, **Looping**, **Nil Value**, **Record Count**, **Table Extractor**, and **Table Looping** functoids are used in various combinations when the input instance message contains sections with an unpredictable number of repeating elements, as represented by looping records in the source schema.</span></span>  
  
-   <span data-ttu-id="10e5e-107">**条件付きのマッピング。**</span><span class="sxs-lookup"><span data-stu-id="10e5e-107">**Conditional mapping.**</span></span> <span data-ttu-id="10e5e-108">**値のマッピング**と**値のマッピング (フラット化)** functoid を使用して、入力インスタンス メッセージから出力インスタンス メッセージへの条件付きのマッピングを提供します。</span><span class="sxs-lookup"><span data-stu-id="10e5e-108">The **Value Mapping** and **Value Mapping (Flattening)** functoids are used to provide conditional mapping from an input instance message to an output instance message.</span></span> <span data-ttu-id="10e5e-109">2 番目の入力パラメーターが指定した要素または属性を出力インスタンス メッセージ内に配置されている最初の入力パラメーターが true の場合それ以外の場合、その要素または属性は、出力インスタンス メッセージでは作成されません。</span><span class="sxs-lookup"><span data-stu-id="10e5e-109">When their first input parameter is true, the second input parameter is put into the specified element or attribute in the output instance message; otherwise, that element or attribute is not created in the output instance message.</span></span>  
  
-   <span data-ttu-id="10e5e-110">**任意のスクリプト。**</span><span class="sxs-lookup"><span data-stu-id="10e5e-110">**Arbitrary scripting.**</span></span> <span data-ttu-id="10e5e-111">**Scripting** functoid は、任意のスクリプトを実行するために使用または入力インスタンス メッセージを出力インスタンス メッセージにマップされているときにコードをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="10e5e-111">The **Scripting** functoid is used to run arbitrary script or compiled code when an input instance message is being mapped to an output instance message.</span></span> <span data-ttu-id="10e5e-112">送信元インスタンス メッセージの別の functoid、またはその組み合わせの出力から、構成された定数値から、入力パラメーターを受け入れるように、このようなスクリプトまたはコンパイル済みコードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="10e5e-112">Such script or compiled code can be created so that it accepts input parameters from the source instance message, from configured constant values, from the output of another functoid, or some combination thereof.</span></span>  
  
-   <span data-ttu-id="10e5e-113">**単純なマッピング。**</span><span class="sxs-lookup"><span data-stu-id="10e5e-113">**Simple mapping.**</span></span> <span data-ttu-id="10e5e-114">**一括コピー**出力インスタンス メッセージに入力インスタンス メッセージから任意の深さをそのサブ要素を含む要素全体をコピーする functoid を使用できます。</span><span class="sxs-lookup"><span data-stu-id="10e5e-114">The **Mass Copy** functoid can be used to copy an entire element, including its subelements to an arbitrary depth, from an input instance message to an output instance message.</span></span>  
  
-   <span data-ttu-id="10e5e-115">**トラブルシューティング**します。</span><span class="sxs-lookup"><span data-stu-id="10e5e-115">**Troubleshooting**.</span></span> <span data-ttu-id="10e5e-116">**Assert** functoid を使用して要素の値に関する仮定をテストできます。</span><span class="sxs-lookup"><span data-stu-id="10e5e-116">The **Assert** functoid can be used to test your assumptions about element values.</span></span>  
  
## <a name="available-functoids"></a><span data-ttu-id="10e5e-117">使用可能な functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-117">Available functoids</span></span>
  
 <span data-ttu-id="10e5e-118">**詳細**functoid には。</span><span class="sxs-lookup"><span data-stu-id="10e5e-118">The **Advanced** functoids are:</span></span> 

* <span data-ttu-id="10e5e-119">アサート Functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-119">Assert Functoid</span></span>
* <span data-ttu-id="10e5e-120">インデックス Functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-120">Index Functoid</span></span> 
* <span data-ttu-id="10e5e-121">繰り返し Functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-121">Iteration Functoid</span></span> 
* <span data-ttu-id="10e5e-122">ループ Functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-122">Looping Functoid</span></span> 
* <span data-ttu-id="10e5e-123">一括コピー Functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-123">Mass Copy Functoid</span></span> 
* <span data-ttu-id="10e5e-124">Nil 値 Functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-124">Nil Value Functoid</span></span>
* <span data-ttu-id="10e5e-125">レコード カウント Functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-125">Record Count Functoid</span></span> 
* <span data-ttu-id="10e5e-126">スクリプト Functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-126">Scripting Functoid</span></span> 
* <span data-ttu-id="10e5e-127">テーブル ループ functoid およびテーブル抽出 Functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-127">Table Looping and Table Extractor Functoids</span></span>
* <span data-ttu-id="10e5e-128">値のマッピング Functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-128">Value Mapping Functoid</span></span>
* <span data-ttu-id="10e5e-129">値のマッピング (フラット化) Functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-129">Value Mapping (Flattening) Functoid</span></span>

<span data-ttu-id="10e5e-130">これらの functoid について詳しくは、 **Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="10e5e-130">More details on these functoids are in the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="10e5e-131">次のステップ</span><span class="sxs-lookup"><span data-stu-id="10e5e-131">Next steps</span></span>
  
-   [<span data-ttu-id="10e5e-132">アサート Functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-132">Assert Functoid</span></span>](../core/assert-functoid.md)  
  
-   [<span data-ttu-id="10e5e-133">インデックス Functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-133">Index Functoid</span></span>](../core/index-functoid.md)  
  
-   [<span data-ttu-id="10e5e-134">繰り返し Functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-134">Iteration Functoid</span></span>](../core/iteration-functoid.md)  
  
-   [<span data-ttu-id="10e5e-135">ループ Functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-135">Looping Functoid</span></span>](../core/looping-functoid.md)  
  
-   [<span data-ttu-id="10e5e-136">一括コピー Functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-136">Mass Copy Functoid</span></span>](../core/mass-copy-functoid.md)  
  
-   [<span data-ttu-id="10e5e-137">Nil 値 Functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-137">Nil Value Functoid</span></span>](../core/nil-value-functoid.md)  
  
-   [<span data-ttu-id="10e5e-138">レコード カウント Functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-138">Record Count Functoid</span></span>](../core/record-count-functoid.md)  
  
-   [<span data-ttu-id="10e5e-139">テーブル ループ Functoid とテーブル抽出 Functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-139">Table Looping and Table Extractor Functoids</span></span>](../core/table-looping-and-table-extractor-functoids.md)  
  
-   [<span data-ttu-id="10e5e-140">値のマッピング Functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-140">Value Mapping Functoid</span></span>](../core/value-mapping-functoid.md)  
  
-   [<span data-ttu-id="10e5e-141">値のマッピング (フラット化) Functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-141">Value Mapping (Flattening) Functoid</span></span>](../core/value-mapping-flattening-functoid.md)  
  
-   [<span data-ttu-id="10e5e-142">スクリプト Functoid</span><span class="sxs-lookup"><span data-stu-id="10e5e-142">Scripting Functoid</span></span>](../core/scripting-functoid.md)