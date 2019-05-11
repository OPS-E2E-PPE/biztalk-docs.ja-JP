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
ms.openlocfilehash: e68b269cd333706978bb2ef2433f0e5703e72b37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338793"
---
# <a name="how-to-define-measures"></a><span data-ttu-id="48794-102">メジャーを定義する方法</span><span class="sxs-lookup"><span data-stu-id="48794-102">How to Define Measures</span></span>
<span data-ttu-id="48794-103">メジャーでは、アクティビティの計算方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="48794-103">A measure defines how an activity is calculated.</span></span> <span data-ttu-id="48794-104">BAM ビューの作成時、ビューのアクティビティにメジャーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="48794-104">When you create a BAM view you can define a measure for the activity in the view.</span></span> <span data-ttu-id="48794-105">たとえば、発注アクティビティの場合は、PO の合計金額、PO の数、PO の平均金額などを計算できます。</span><span class="sxs-lookup"><span data-stu-id="48794-105">For example, for a purchase order activity, you can calculate the total PO amount, the number of POs, the average PO amount, and so on.</span></span>  
  
 <span data-ttu-id="48794-106">BAM では次のメジャーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="48794-106">BAM supported measures include:</span></span>  
  
-   <span data-ttu-id="48794-107">SUM</span><span class="sxs-lookup"><span data-stu-id="48794-107">Sum</span></span>  
  
-   <span data-ttu-id="48794-108">Count</span><span class="sxs-lookup"><span data-stu-id="48794-108">Count</span></span>  
  
-   <span data-ttu-id="48794-109">平均</span><span class="sxs-lookup"><span data-stu-id="48794-109">Average</span></span>  
  
-   <span data-ttu-id="48794-110">最小</span><span class="sxs-lookup"><span data-stu-id="48794-110">Minimum</span></span>  
  
-   <span data-ttu-id="48794-111">[最大]</span><span class="sxs-lookup"><span data-stu-id="48794-111">Maximum</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48794-112">現在のところ、BAM のリアルタイム集計 (RTA) 機能では、最小値メジャーと最大値メジャーはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="48794-112">The BAM Real-time Aggregation (RTA) feature doesn't currently support Minimum and Maximum measures.</span></span> <span data-ttu-id="48794-113">これらのメジャーを使用することはできますが、Excel のピボットテーブルを RTA としてマークしたとき、最小値と最大値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="48794-113">You can use those measures, but when you mark the Excel pivot table as an RTA, Minimum and Maximum are ignored.</span></span>  
  
### <a name="to-add-new-measures"></a><span data-ttu-id="48794-114">新しいメジャーを追加するには</span><span class="sxs-lookup"><span data-stu-id="48794-114">To add new measures</span></span>  
  
1. <span data-ttu-id="48794-115">BAM ビュー ウィザードで、**次**が表示されるまで、**新しい BAM ビュー。集計ディメンションおよび集計メジャー**ページ。</span><span class="sxs-lookup"><span data-stu-id="48794-115">In the BAM View wizard, click **Next** until you see the **New BAM View: Aggregation Dimensions and Measures** page.</span></span> <span data-ttu-id="48794-116">クリックして**新しいメジャー**します。</span><span class="sxs-lookup"><span data-stu-id="48794-116">Click **New Measures**.</span></span>  
  
2. <span data-ttu-id="48794-117">メジャーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="48794-117">Type a name for your measure.</span></span>  
  
3. <span data-ttu-id="48794-118">ドロップダウン リストから、選択、**基本データ項目**します。</span><span class="sxs-lookup"><span data-stu-id="48794-118">From the drop-down list, select the **Base data item**.</span></span>  
  
4. <span data-ttu-id="48794-119">をクリックして、**集計の種類**を使用します。</span><span class="sxs-lookup"><span data-stu-id="48794-119">Click the **Aggregation type** you want to use.</span></span> <span data-ttu-id="48794-120">選択肢は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="48794-120">The choices include:</span></span>  
  
   -   <span data-ttu-id="48794-121">SUM</span><span class="sxs-lookup"><span data-stu-id="48794-121">Sum</span></span>  
  
   -   <span data-ttu-id="48794-122">Count</span><span class="sxs-lookup"><span data-stu-id="48794-122">Count</span></span>  
  
   -   <span data-ttu-id="48794-123">平均</span><span class="sxs-lookup"><span data-stu-id="48794-123">Average</span></span>  
  
   -   <span data-ttu-id="48794-124">最小 (rta はサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="48794-124">Minimum (not supported for RTAs).</span></span>  
  
   -   <span data-ttu-id="48794-125">最大値 (RTA では未サポート)</span><span class="sxs-lookup"><span data-stu-id="48794-125">Maximum (not supported for RTAs)</span></span>  
  
5. <span data-ttu-id="48794-126">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48794-126">Click **OK**.</span></span> <span data-ttu-id="48794-127">ディメンションとメジャーの追加が完了したら、クリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="48794-127">When you finish adding dimensions and measures, click **Next**.</span></span>  
  
6. <span data-ttu-id="48794-128">**新しい BAM ビュー。概要** ページで、新しいビューに関する情報を確認してクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="48794-128">On the **New BAM View: Summary** page, review the information regarding your new view, and then click **Next**.</span></span>  
  
7. <span data-ttu-id="48794-129">クリックして**完了**を完了する、 **BAM ビュー ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="48794-129">Click **Finish** to complete the **BAM View Wizard**.</span></span>  
  
   <span data-ttu-id="48794-130">BAM ビューにメジャーとディメンションを追加したら、これらの項目を Excel ブックのピボットテーブルに追加できます。</span><span class="sxs-lookup"><span data-stu-id="48794-130">If you added measures and dimensions to your BAM view, you can add those items to the PivotTable in the Excel workbook.</span></span> <span data-ttu-id="48794-131">ピボット テーブルの作成の詳細については、次を参照してください。[ピボット テーブルを使用する方法](../core/how-to-use-the-pivottable.md)します。</span><span class="sxs-lookup"><span data-stu-id="48794-131">For more information about creating a PivotTable, see [How to Use the PivotTable](../core/how-to-use-the-pivottable.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48794-132">参照</span><span class="sxs-lookup"><span data-stu-id="48794-132">See Also</span></span>  
 [<span data-ttu-id="48794-133">ディメンションの定義</span><span class="sxs-lookup"><span data-stu-id="48794-133">Defining Dimensions</span></span>](../core/defining-dimensions.md)