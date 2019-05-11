---
title: テーブル ループおよびテーブル抽出 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2907aada-f11a-485c-85c8-03092803ccf7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe6660e5fbfb226ff49c394ee83d7205bd6e2dca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291640"
---
# <a name="table-looping-and-table-extractor-functoids"></a><span data-ttu-id="ca88a-102">テーブル ループ functoid およびテーブル抽出 Functoid</span><span class="sxs-lookup"><span data-stu-id="ca88a-102">Table Looping and Table Extractor Functoids</span></span>

## <a name="overview"></a><span data-ttu-id="ca88a-103">概要</span><span class="sxs-lookup"><span data-stu-id="ca88a-103">Overview</span></span>
<span data-ttu-id="ca88a-104">マップでは、一般的な入力インスタンス メッセージ内の各構造の出力インスタンス メッセージ内の 1 つの構造をあります。</span><span class="sxs-lookup"><span data-stu-id="ca88a-104">In a map, you commonly have one structure in the output instance message for each structure in the input instance message.</span></span> <span data-ttu-id="ca88a-105">ただしがあります複数の出力インスタンス構造を生成するために、入力インスタンス構造を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca88a-105">However, there are cases when you need an input instance structure to produce multiple output instance structures.</span></span> <span data-ttu-id="ca88a-106">テーブルドリブン ループでは、このような複数の構造を生成するマップを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ca88a-106">Table-driven looping enables you to create maps generating such multiple structures.</span></span>  
  
 <span data-ttu-id="ca88a-107">テーブル ドリブン ループでは、**テーブル ループ**functoid と**テーブル抽出**functoid。</span><span class="sxs-lookup"><span data-stu-id="ca88a-107">Table-driven looping uses the **Table Looping** functoid and the **Table Extractor** functoid.</span></span> <span data-ttu-id="ca88a-108">**テーブル ループ**functoid が、内部テーブルを構成します。</span><span class="sxs-lookup"><span data-stu-id="ca88a-108">The **Table Looping** functoid has an internal table you configure.</span></span> <span data-ttu-id="ca88a-109">各入力レコードまたはフィールドを**テーブル ループ**functoid は、一度に 1 つずつと、テーブルの行を出力します。</span><span class="sxs-lookup"><span data-stu-id="ca88a-109">For each input record or field, the **Table Looping** functoid outputs the rows of the table, one at a time.</span></span> <span data-ttu-id="ca88a-110">たとえば、入力インスタンス メッセージに 10 個のレコードと 2 つの内部テーブルの行がある場合、**テーブル ループ**functoid の出力で 2 つの 10 個のレコードごとに 20 行の合計。</span><span class="sxs-lookup"><span data-stu-id="ca88a-110">For example, if there are ten records in the input instance message and two rows in the internal table of the **Table Looping**, the functoid outputs a total of twenty rows, two for each of the ten records.</span></span> <span data-ttu-id="ca88a-111">**テーブル抽出**functoid が行から目的の項目を抽出し、出力インスタンス メッセージに渡します。</span><span class="sxs-lookup"><span data-stu-id="ca88a-111">The **Table Extractor** functoid extracts the desired item from a row and passes it on to the output instance message.</span></span>  
  
 <span data-ttu-id="ca88a-112">詳細については、次を参照してください。、**テーブル ループ Functoid のリファレンス**と**テーブル抽出 Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="ca88a-112">For more details, see the **Table Looping Functoid Reference** and **Table Extractor Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="ca88a-113">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ca88a-113">Next steps</span></span>
  
-   [<span data-ttu-id="ca88a-114">テーブル ループ Functoid</span><span class="sxs-lookup"><span data-stu-id="ca88a-114">Table Looping Functoid</span></span>](../core/table-looping-functoid.md)  
  
-   [<span data-ttu-id="ca88a-115">テーブル抽出 Functoid</span><span class="sxs-lookup"><span data-stu-id="ca88a-115">Table Extractor Functoid</span></span>](../core/table-extractor-functoid.md)  
  
-   [<span data-ttu-id="ca88a-116">テーブルドリブン ループの構成</span><span class="sxs-lookup"><span data-stu-id="ca88a-116">Table-Driven Looping Configuration</span></span>](../core/table-driven-looping-configuration.md)  
  
-   [<span data-ttu-id="ca88a-117">テーブルドリブン ループの例</span><span class="sxs-lookup"><span data-stu-id="ca88a-117">Table-Driven Looping Example</span></span>](../core/table-driven-looping-example.md)