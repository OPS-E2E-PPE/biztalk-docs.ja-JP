---
title: メジャーを定義する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], creating measures
- aggregations [BAM], measures
- BAM views, measures
ms.assetid: fd3dfe6b-cc63-4306-8aad-a9d2a9af01e8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 536ed57c16d135153765ad1f0d8b3a208106b8b2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004123"
---
# <a name="how-to-define-measures"></a><span data-ttu-id="1a79b-102">メジャーを定義する方法</span><span class="sxs-lookup"><span data-stu-id="1a79b-102">How to Define Measures</span></span>
<span data-ttu-id="1a79b-103">メジャーでは、アクティビティの計算方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="1a79b-103">A measure defines how an activity is calculated.</span></span> <span data-ttu-id="1a79b-104">BAM ビューの作成時、ビューのアクティビティにメジャーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="1a79b-104">When you create a BAM view you can define a measure for the activity in the view.</span></span> <span data-ttu-id="1a79b-105">たとえば、発注アクティビティの場合は、PO の合計金額、PO の数、PO の平均金額などを計算できます。</span><span class="sxs-lookup"><span data-stu-id="1a79b-105">For example, for a purchase order activity, you can calculate the total PO amount, the number of POs, the average PO amount, and so on.</span></span>  
  
 <span data-ttu-id="1a79b-106">BAM では次のメジャーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1a79b-106">BAM supported measures include:</span></span>  
  
-   <span data-ttu-id="1a79b-107">SUM</span><span class="sxs-lookup"><span data-stu-id="1a79b-107">Sum</span></span>  
  
-   <span data-ttu-id="1a79b-108">Count</span><span class="sxs-lookup"><span data-stu-id="1a79b-108">Count</span></span>  
  
-   <span data-ttu-id="1a79b-109">平均</span><span class="sxs-lookup"><span data-stu-id="1a79b-109">Average</span></span>  
  
-   <span data-ttu-id="1a79b-110">最小</span><span class="sxs-lookup"><span data-stu-id="1a79b-110">Minimum</span></span>  
  
-   <span data-ttu-id="1a79b-111">[最大]</span><span class="sxs-lookup"><span data-stu-id="1a79b-111">Maximum</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a79b-112">現在のところ、BAM のリアルタイム集計 (RTA) 機能では、最小値メジャーと最大値メジャーはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1a79b-112">The BAM Real-time Aggregation (RTA) feature doesn't currently support Minimum and Maximum measures.</span></span> <span data-ttu-id="1a79b-113">これらのメジャーを使用することはできますが、Excel のピボットテーブルを RTA としてマークしたとき、最小値と最大値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="1a79b-113">You can use those measures, but when you mark the Excel pivot table as an RTA, Minimum and Maximum are ignored.</span></span>  
  
### <a name="to-add-new-measures"></a><span data-ttu-id="1a79b-114">新しいメジャーを追加するには</span><span class="sxs-lookup"><span data-stu-id="1a79b-114">To add new measures</span></span>  
  
1. <span data-ttu-id="1a79b-115">BAM ビュー ウィザードで、**次**が表示されるまで、**新しい BAM ビュー: 集計ディメンションおよび集計メジャー**ページ。</span><span class="sxs-lookup"><span data-stu-id="1a79b-115">In the BAM View wizard, click **Next** until you see the **New BAM View: Aggregation Dimensions and Measures** page.</span></span> <span data-ttu-id="1a79b-116">クリックして**新しいメジャー**します。</span><span class="sxs-lookup"><span data-stu-id="1a79b-116">Click **New Measures**.</span></span>  
  
2. <span data-ttu-id="1a79b-117">メジャーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a79b-117">Type a name for your measure.</span></span>  
  
3. <span data-ttu-id="1a79b-118">ドロップダウン リストから、選択、**基本データ項目**します。</span><span class="sxs-lookup"><span data-stu-id="1a79b-118">From the drop-down list, select the **Base data item**.</span></span>  
  
4. <span data-ttu-id="1a79b-119">をクリックして、**集計の種類**を使用します。</span><span class="sxs-lookup"><span data-stu-id="1a79b-119">Click the **Aggregation type** you want to use.</span></span> <span data-ttu-id="1a79b-120">選択肢は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1a79b-120">The choices include:</span></span>  
  
   -   <span data-ttu-id="1a79b-121">SUM</span><span class="sxs-lookup"><span data-stu-id="1a79b-121">Sum</span></span>  
  
   -   <span data-ttu-id="1a79b-122">Count</span><span class="sxs-lookup"><span data-stu-id="1a79b-122">Count</span></span>  
  
   -   <span data-ttu-id="1a79b-123">平均</span><span class="sxs-lookup"><span data-stu-id="1a79b-123">Average</span></span>  
  
   -   <span data-ttu-id="1a79b-124">最小 (rta はサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="1a79b-124">Minimum (not supported for RTAs).</span></span>  
  
   -   <span data-ttu-id="1a79b-125">最大値 (RTA では未サポート)</span><span class="sxs-lookup"><span data-stu-id="1a79b-125">Maximum (not supported for RTAs)</span></span>  
  
5. <span data-ttu-id="1a79b-126">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a79b-126">Click **OK**.</span></span> <span data-ttu-id="1a79b-127">ディメンションとメジャーの追加が完了したら、クリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="1a79b-127">When you finish adding dimensions and measures, click **Next**.</span></span>  
  
6. <span data-ttu-id="1a79b-128">**新しい BAM ビュー: 概要** ページで、新しいビューに関する情報を確認してをクリックし、**次**。</span><span class="sxs-lookup"><span data-stu-id="1a79b-128">On the **New BAM View: Summary** page, review the information regarding your new view, and then click **Next**.</span></span>  
  
7. <span data-ttu-id="1a79b-129">クリックして**完了**を完了する、 **BAM ビュー ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="1a79b-129">Click **Finish** to complete the **BAM View Wizard**.</span></span>  
  
   <span data-ttu-id="1a79b-130">BAM ビューにメジャーとディメンションを追加したら、これらの項目を Excel ブックのピボットテーブルに追加できます。</span><span class="sxs-lookup"><span data-stu-id="1a79b-130">If you added measures and dimensions to your BAM view, you can add those items to the PivotTable in the Excel workbook.</span></span> <span data-ttu-id="1a79b-131">ピボット テーブルの作成の詳細については、[ピボット テーブルを使用する方法](../core/how-to-use-the-pivottable.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a79b-131">For more information about creating a PivotTable, see [How to Use the PivotTable](../core/how-to-use-the-pivottable.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a79b-132">参照</span><span class="sxs-lookup"><span data-stu-id="1a79b-132">See Also</span></span>  
 [<span data-ttu-id="1a79b-133">ディメンションの定義</span><span class="sxs-lookup"><span data-stu-id="1a79b-133">Defining Dimensions</span></span>](../core/defining-dimensions.md)