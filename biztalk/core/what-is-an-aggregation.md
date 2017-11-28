---
title: "集計とは何ですか。 | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- OLAP cubes, BAM
- BAM, aggregations
- BAM, OLAP cubes
- aggregations [BAM], OLAP cubes
- aggregations [BAM], about aggregations
- aggregations [BAM]
ms.assetid: 77d40602-ef56-4a5b-a18f-56ccbff573a4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df24dced4d7075e85b8b002bf90b821ce745f91e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-an-aggregation"></a><span data-ttu-id="1e807-103">集計とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="1e807-103">What Is an Aggregation?</span></span>
<span data-ttu-id="1e807-104">Excel では、集計を事前計算された要約データとして定義し、質問の答えをあらかじめ用意しておくことで、クエリの応答時間を短縮します。</span><span class="sxs-lookup"><span data-stu-id="1e807-104">Excel defines aggregations as pre-calculated summaries of data that improve query response time by having the answers ready before the questions are asked.</span></span> <span data-ttu-id="1e807-105">たとえば、数十万行が格納されているデータ ウェアハウスのファクト テーブルに対して、特定の 2 つの製品の出荷スケジュールを要求するクエリがあるとします。この計算でファクト テーブルをスキャンする必要があると、応答に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="1e807-105">For example, when a data warehouse fact table contains hundreds of thousands of rows, a query requesting the shipping schedules for two particular products can take a long time to answer if the fact table has to be scanned to compute the answer.</span></span> <span data-ttu-id="1e807-106">ただし、このクエリの回答となる集計データがあらかじめ計算されていれば、即座に応答できます。</span><span class="sxs-lookup"><span data-stu-id="1e807-106">However, the response can be almost immediate if the summarization data to answer this query has been pre-calculated.</span></span>  
  
 <span data-ttu-id="1e807-107">次に、事前に計算された集計データの例を示します。</span><span class="sxs-lookup"><span data-stu-id="1e807-107">The following figure displays an example of pre-calculated aggregation data.</span></span>  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
<span data-ttu-id="1e807-108">BAM OLAP キューブ</span><span class="sxs-lookup"><span data-stu-id="1e807-108">BAM OLAP Cube</span></span>  
  
 <span data-ttu-id="1e807-109">上の図では、2 か月間に特定の場所への出荷された各製品数の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="1e807-109">The above figure summarizes the numbers of each product, shipped to specific locations over a two-month time period.</span></span> <span data-ttu-id="1e807-110">通常、Excel では、このデータをメジャーとして定義し、</span><span class="sxs-lookup"><span data-stu-id="1e807-110">Excel typically defines this data as measure.</span></span> <span data-ttu-id="1e807-111">フィルター選択または分類に使用するデータをディメンションとして定義します。</span><span class="sxs-lookup"><span data-stu-id="1e807-111">The data used for filtering and categorization, Excel defines as dimension.</span></span>  
  
 <span data-ttu-id="1e807-112">多次元データのユーザー エクスペリエンスについては、Excel のヘルプでピボットテーブルに関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e807-112">For the user experience of browsing multidimensional data, see the PivotTable topic in Excel Help.</span></span>  
  
 <span data-ttu-id="1e807-113">特定のビューで利用できるデータに基づいた多次元アクティビティの集計を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="1e807-113">You can create multidimensional activity aggregations based on the data available in a specific view.</span></span> <span data-ttu-id="1e807-114">多次元アクティビティの集計には、メジャー (金額など、集計するデータ) とディメンション (州や都市など、フィルター選択またはグループ化に使用するデータ) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1e807-114">Those aggregations contain measures (data to aggregate, such as dollar amount) and dimensions (used for filtering or grouping, such as State and City).</span></span>  
  
 <span data-ttu-id="1e807-115">集計は、オンライン分析処理 (OLAP) キューブの形式またはリアルタイム集計として作成できます。OLAP キューブは特定の時点のスナップショットを表し、リアルタイム集計は、ビジネス シナリオに基づいており、多次元構造を使用してリアルタイムでデータを参照できます。</span><span class="sxs-lookup"><span data-stu-id="1e807-115">You can create the aggregations in the form of online analytical processing (OLAP) cubes, which represent a snapshot of the business at a specific time, or as real-time aggregations, which the business scenario determines and you see using the multidimensional structure in real time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1e807-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1e807-116">In This Section</span></span>  
  
-   [<span data-ttu-id="1e807-117">スケジュール済みの集計</span><span class="sxs-lookup"><span data-stu-id="1e807-117">Scheduled Aggregations</span></span>](../core/scheduled-aggregations.md)  
  
-   [<span data-ttu-id="1e807-118">リアルタイム集計</span><span class="sxs-lookup"><span data-stu-id="1e807-118">Real-Time Aggregations</span></span>](../core/real-time-aggregations.md)