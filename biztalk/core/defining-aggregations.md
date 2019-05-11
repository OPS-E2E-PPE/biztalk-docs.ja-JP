---
title: 集計の定義 |Microsoft Docs
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
ms.openlocfilehash: a379e27e7805aa7e4b67ad3c94afba65b546c7a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352476"
---
# <a name="defining-aggregations"></a><span data-ttu-id="e732c-102">集計の定義</span><span class="sxs-lookup"><span data-stu-id="e732c-102">Defining Aggregations</span></span>
<span data-ttu-id="e732c-103">Excel では定義**集計**として事前に計算された要約データをクエリの応答時間を向上させることで答えをあらかじめ、質問の前にします。</span><span class="sxs-lookup"><span data-stu-id="e732c-103">Excel defines **aggregations** as pre-calculated summaries of data that improve query response time by having the answers ready before the questions are asked.</span></span> <span data-ttu-id="e732c-104">たとえば、数十万行が格納されているデータ ウェアハウスのファクト テーブルに対して、特定の 2 つの製品の出荷スケジュールを要求するクエリがあるとします。この計算でファクト テーブルをスキャンする必要があると、応答に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="e732c-104">For example, when a data warehouse fact table contains hundreds of thousands of rows, a query requesting the shipping schedules for two particular products can take a long time to answer if the fact table has to be scanned to compute the answer.</span></span> <span data-ttu-id="e732c-105">ただし、このクエリの回答となる集計データがあらかじめ計算されていれば、即座に応答できます。</span><span class="sxs-lookup"><span data-stu-id="e732c-105">However, the response can be almost immediate if the summarization data to answer this query has been pre-calculated.</span></span>  
  
 <span data-ttu-id="e732c-106">次に、事前に計算された集計データの例を示します。</span><span class="sxs-lookup"><span data-stu-id="e732c-106">The following figure displays an example of pre-calculated aggregation data.</span></span>  
  
 <span data-ttu-id="e732c-107">![](../core/media/bam-olap-cube.gif "bam_olap_cube")</span><span class="sxs-lookup"><span data-stu-id="e732c-107">![](../core/media/bam-olap-cube.gif "bam_olap_cube")</span></span>  
<span data-ttu-id="e732c-108">事前に計算された集計データ</span><span class="sxs-lookup"><span data-stu-id="e732c-108">Pre-calculated Aggregation Data</span></span>  
  
 <span data-ttu-id="e732c-109">上の図では、2 か月間に特定の場所への出荷された各製品数の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="e732c-109">The above figure summarizes the numbers of each product, shipped to specific locations over a two-month time period.</span></span> <span data-ttu-id="e732c-110">Excel は、通常、としては、このデータを定義**メジャー**します。</span><span class="sxs-lookup"><span data-stu-id="e732c-110">Excel typically defines this data as **measure**.</span></span> <span data-ttu-id="e732c-111">にフィルター処理と分類のために使用するデータとして定義します**ディメンション**します。</span><span class="sxs-lookup"><span data-stu-id="e732c-111">The data used for filtering and categorization, Excel defines as **dimension**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e732c-112">BAM では、名前付きインスタンスの使用はサポートしません[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services。</span><span class="sxs-lookup"><span data-stu-id="e732c-112">BAM does not support using named instances for [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services.</span></span>  
  
 <span data-ttu-id="e732c-113">多次元データの表示、ユーザー エクスペリエンスは、Excel のヘルプでピボット テーブルに関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e732c-113">For the user experience of browsing multidimensional data, see the Pivot table topic in Excel Help.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e732c-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e732c-114">In This Section</span></span>  
  
-   [<span data-ttu-id="e732c-115">メジャーを定義する方法</span><span class="sxs-lookup"><span data-stu-id="e732c-115">How to Define Measures</span></span>](../core/how-to-define-measures.md)  
  
-   [<span data-ttu-id="e732c-116">ディメンションの定義</span><span class="sxs-lookup"><span data-stu-id="e732c-116">Defining Dimensions</span></span>](../core/defining-dimensions.md)  
  
-   [<span data-ttu-id="e732c-117">ピボット テーブルを使用する方法</span><span class="sxs-lookup"><span data-stu-id="e732c-117">How to Use the PivotTable</span></span>](../core/how-to-use-the-pivottable.md)  
  
-   [<span data-ttu-id="e732c-118">リアルタイム集計の定義</span><span class="sxs-lookup"><span data-stu-id="e732c-118">Defining Real-Time Aggregations</span></span>](../core/defining-real-time-aggregations.md)  
  
## <a name="see-also"></a><span data-ttu-id="e732c-119">参照</span><span class="sxs-lookup"><span data-stu-id="e732c-119">See Also</span></span>  
 [<span data-ttu-id="e732c-120">BAM ビューの定義</span><span class="sxs-lookup"><span data-stu-id="e732c-120">Defining a BAM View</span></span>](../core/defining-a-bam-view.md)