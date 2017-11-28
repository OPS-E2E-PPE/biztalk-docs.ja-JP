---
title: "ループをテーブルし、テーブル抽出 Functoid |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2907aada-f11a-485c-85c8-03092803ccf7
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02d4433255ac00d51c88b45bd1a2b5205bd1c735
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="table-looping-and-table-extractor-functoids"></a><span data-ttu-id="dff1f-102">テーブル ループ functoid とテーブル抽出 Functoid</span><span class="sxs-lookup"><span data-stu-id="dff1f-102">Table Looping and Table Extractor Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="dff1f-103">概要</span><span class="sxs-lookup"><span data-stu-id="dff1f-103">Overview</span></span>
<span data-ttu-id="dff1f-104">マップでは、入力インスタンス メッセージの各構造に対し、通常、出力インスタンス メッセージの単一の構造を使用します。</span><span class="sxs-lookup"><span data-stu-id="dff1f-104">In a map, you commonly have one structure in the output instance message for each structure in the input instance message.</span></span> <span data-ttu-id="dff1f-105">ただし、入力インスタンス構造で複数の出力インスタンス構造を生成することが必要な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="dff1f-105">However, there are cases when you need an input instance structure to produce multiple output instance structures.</span></span> <span data-ttu-id="dff1f-106">テーブルドリブン ループを使用すると、このような複数の構造を生成するマップを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dff1f-106">Table-driven looping enables you to create maps generating such multiple structures.</span></span>  
  
 <span data-ttu-id="dff1f-107">テーブルドリブン ループでは、**テーブル ループ**functoid および**テーブル抽出**functoid です。</span><span class="sxs-lookup"><span data-stu-id="dff1f-107">Table-driven looping uses the **Table Looping** functoid and the **Table Extractor** functoid.</span></span> <span data-ttu-id="dff1f-108">**テーブル ループ**functoid が構成する内部テーブルです。</span><span class="sxs-lookup"><span data-stu-id="dff1f-108">The **Table Looping** functoid has an internal table you configure.</span></span> <span data-ttu-id="dff1f-109">各入力レコードまたはフィールドの**テーブル ループ**functoid は一度に 1 つずつ、テーブルの行を出力します。</span><span class="sxs-lookup"><span data-stu-id="dff1f-109">For each input record or field, the **Table Looping** functoid outputs the rows of the table, one at a time.</span></span> <span data-ttu-id="dff1f-110">たとえば、入力インスタンス メッセージに 10 個のレコードと 2 つの内部テーブルの行がある場合、**テーブル ループ**functoid は、合計 2 つの 10 個のレコードのそれぞれの 20 個の行を出力します。</span><span class="sxs-lookup"><span data-stu-id="dff1f-110">For example, if there are ten records in the input instance message and two rows in the internal table of the **Table Looping**, the functoid outputs a total of twenty rows, two for each of the ten records.</span></span> <span data-ttu-id="dff1f-111">**テーブル抽出**functoid が行から目的の項目を抽出し、出力インスタンス メッセージに渡します。</span><span class="sxs-lookup"><span data-stu-id="dff1f-111">The **Table Extractor** functoid extracts the desired item from a row and passes it on to the output instance message.</span></span>  
  
 <span data-ttu-id="dff1f-112">詳細については、次を参照してください。、**テーブル ループ Functoid のリファレンス**と**テーブル抽出 Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="dff1f-112">For more details, see the **Table Looping Functoid Reference** and **Table Extractor Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="dff1f-113">次の手順</span><span class="sxs-lookup"><span data-stu-id="dff1f-113">Next steps</span></span>
  
-   [<span data-ttu-id="dff1f-114">テーブル ループ Functoid</span><span class="sxs-lookup"><span data-stu-id="dff1f-114">Table Looping Functoid</span></span>](../core/table-looping-functoid.md)  
  
-   [<span data-ttu-id="dff1f-115">テーブル抽出 Functoid</span><span class="sxs-lookup"><span data-stu-id="dff1f-115">Table Extractor Functoid</span></span>](../core/table-extractor-functoid.md)  
  
-   [<span data-ttu-id="dff1f-116">テーブルドリブン ループの構成</span><span class="sxs-lookup"><span data-stu-id="dff1f-116">Table-Driven Looping Configuration</span></span>](../core/table-driven-looping-configuration.md)  
  
-   [<span data-ttu-id="dff1f-117">テーブルドリブン ループの例</span><span class="sxs-lookup"><span data-stu-id="dff1f-117">Table-Driven Looping Example</span></span>](../core/table-driven-looping-example.md)