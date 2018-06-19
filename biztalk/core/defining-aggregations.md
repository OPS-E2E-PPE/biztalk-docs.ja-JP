---
title: 集計の定義 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], creating
- Excel add-in [BAM], creating aggregations
- aggregations [BAM], Excel add-in
- aggregations [BAM], about aggregations
ms.assetid: d5bf22d5-f491-4b08-a604-c7158e6e282f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3412615d03fc9a9776d86fddfb062ab343c5aaeb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238450"
---
# <a name="defining-aggregations"></a><span data-ttu-id="d5a1e-102">集計の定義</span><span class="sxs-lookup"><span data-stu-id="d5a1e-102">Defining Aggregations</span></span>
<span data-ttu-id="d5a1e-103">Excel では定義**集計**を事前に計算された要約データを用意することによってクエリの応答時間を向上させるとして、回答には、質問の前に準備ができています。</span><span class="sxs-lookup"><span data-stu-id="d5a1e-103">Excel defines **aggregations** as pre-calculated summaries of data that improve query response time by having the answers ready before the questions are asked.</span></span> <span data-ttu-id="d5a1e-104">たとえば、数十万行が格納されているデータ ウェアハウスのファクト テーブルに対して、特定の 2 つの製品の出荷スケジュールを要求するクエリがあるとします。この計算でファクト テーブルをスキャンする必要があると、応答に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="d5a1e-104">For example, when a data warehouse fact table contains hundreds of thousands of rows, a query requesting the shipping schedules for two particular products can take a long time to answer if the fact table has to be scanned to compute the answer.</span></span> <span data-ttu-id="d5a1e-105">ただし、このクエリの回答となる集計データがあらかじめ計算されていれば、即座に応答できます。</span><span class="sxs-lookup"><span data-stu-id="d5a1e-105">However, the response can be almost immediate if the summarization data to answer this query has been pre-calculated.</span></span>  
  
 <span data-ttu-id="d5a1e-106">次に、事前に計算された集計データの例を示します。</span><span class="sxs-lookup"><span data-stu-id="d5a1e-106">The following figure displays an example of pre-calculated aggregation data.</span></span>  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
<span data-ttu-id="d5a1e-107">事前に計算された集計データ</span><span class="sxs-lookup"><span data-stu-id="d5a1e-107">Pre-calculated Aggregation Data</span></span>  
  
 <span data-ttu-id="d5a1e-108">上の図では、2 か月間に特定の場所への出荷された各製品数の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="d5a1e-108">The above figure summarizes the numbers of each product, shipped to specific locations over a two-month time period.</span></span> <span data-ttu-id="d5a1e-109">Excel は、通常、このようなデータを定義**メジャー**です。</span><span class="sxs-lookup"><span data-stu-id="d5a1e-109">Excel typically defines this data as **measure**.</span></span> <span data-ttu-id="d5a1e-110">にフィルター処理と分類のために使用するデータとして定義**ディメンション**です。</span><span class="sxs-lookup"><span data-stu-id="d5a1e-110">The data used for filtering and categorization, Excel defines as **dimension**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5a1e-111">BAM では [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services の名前付きインスタンスは使用できません。</span><span class="sxs-lookup"><span data-stu-id="d5a1e-111">BAM does not support using named instances for [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services.</span></span>  
  
 <span data-ttu-id="d5a1e-112">多次元データの表示に関するユーザー エクスペリエンスについては、Excel のヘルプでピボット テーブルに関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5a1e-112">For the user experience of browsing multidimensional data, see the Pivot table topic in Excel Help.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5a1e-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d5a1e-113">In This Section</span></span>  
  
-   [<span data-ttu-id="d5a1e-114">メジャーを定義する方法</span><span class="sxs-lookup"><span data-stu-id="d5a1e-114">How to Define Measures</span></span>](../core/how-to-define-measures.md)  
  
-   [<span data-ttu-id="d5a1e-115">ディメンションの定義</span><span class="sxs-lookup"><span data-stu-id="d5a1e-115">Defining Dimensions</span></span>](../core/defining-dimensions.md)  
  
-   [<span data-ttu-id="d5a1e-116">ピボット テーブルを使用する方法</span><span class="sxs-lookup"><span data-stu-id="d5a1e-116">How to Use the PivotTable</span></span>](../core/how-to-use-the-pivottable.md)  
  
-   [<span data-ttu-id="d5a1e-117">リアルタイム集計の定義</span><span class="sxs-lookup"><span data-stu-id="d5a1e-117">Defining Real-Time Aggregations</span></span>](../core/defining-real-time-aggregations.md)  
  
## <a name="see-also"></a><span data-ttu-id="d5a1e-118">参照</span><span class="sxs-lookup"><span data-stu-id="d5a1e-118">See Also</span></span>  
 [<span data-ttu-id="d5a1e-119">BAM ビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="d5a1e-119">Defining a BAM View</span></span>](../core/defining-a-bam-view.md)