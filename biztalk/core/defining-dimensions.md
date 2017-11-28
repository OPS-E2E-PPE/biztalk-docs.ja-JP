---
title: "ディメンションの定義 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], dimensions
- BAM, dimensions
- BAM views, dimensions
- Excel add-in [BAM], creating dimensions
- dimensions [BAM]
ms.assetid: c00e0c45-eef2-42d9-832c-4be08d79203f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 916e8f29d7f1e48a7bab5f9ad78e65cb78e51802
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="defining-dimensions"></a><span data-ttu-id="185b8-102">ディメンションの定義</span><span class="sxs-lookup"><span data-stu-id="185b8-102">Defining Dimensions</span></span>
<span data-ttu-id="185b8-103">Microsoft Excel では、ディメンションをカテゴリとして定義し、それによってテーブルのデータを分析に使用できるようにレベル分けします。</span><span class="sxs-lookup"><span data-stu-id="185b8-103">Microsoft Excel defines dimensions as categories used to organize data in a table into levels that will be used for analysis.</span></span> <span data-ttu-id="185b8-104">たとえば、場所データのディメンションの場合、市や都道府県、国/地域などのレベルが考えられます。</span><span class="sxs-lookup"><span data-stu-id="185b8-104">For example, a location data dimension might contain levels such as city, state/province, and country/region.</span></span> <span data-ttu-id="185b8-105">BAM ビュー ウィザードで BAM ビューを作成すると、次の 1 つ以上の種類のディメンションを追加できます。</span><span class="sxs-lookup"><span data-stu-id="185b8-105">When creating BAM Views in the BAM View wizard, you can add one or more of the following dimension types:</span></span>  
  
-   [<span data-ttu-id="185b8-106">進捗ディメンション</span><span class="sxs-lookup"><span data-stu-id="185b8-106">Progress Dimension</span></span>](../core/progress-dimension.md)  
  
-   [<span data-ttu-id="185b8-107">データ ディメンション</span><span class="sxs-lookup"><span data-stu-id="185b8-107">Data Dimension</span></span>](../core/data-dimension.md)  
  
-   [<span data-ttu-id="185b8-108">時間ディメンション</span><span class="sxs-lookup"><span data-stu-id="185b8-108">Time Dimension</span></span>](../core/time-dimension.md)  
  
-   [<span data-ttu-id="185b8-109">数値範囲ディメンション</span><span class="sxs-lookup"><span data-stu-id="185b8-109">Numeric Range Dimension</span></span>](../core/numeric-range-dimension.md)  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
<span data-ttu-id="185b8-110">事前に計算された集計データ</span><span class="sxs-lookup"><span data-stu-id="185b8-110">Pre-calculated Aggregation Data</span></span>  
  
 <span data-ttu-id="185b8-111">新しいディメンションは BAM ビュー ウィザードで追加します。</span><span class="sxs-lookup"><span data-stu-id="185b8-111">You add new dimensions in the BAM View wizard.</span></span> <span data-ttu-id="185b8-112">ディメンションを追加するには、先にウィザードを使用してビジネス アクティビティ ビューを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="185b8-112">Before you can add dimensions, you need to use the wizard to create business activity views.</span></span> <span data-ttu-id="185b8-113">詳細については、ウィザードを使用して、次を参照してください。[ビジネス アクティビティの定義および Excel でビュー](../core/defining-business-activities-and-views-in-excel.md)です。</span><span class="sxs-lookup"><span data-stu-id="185b8-113">For more information about using the wizard, see [Define Business Activities and Views in Excel](../core/defining-business-activities-and-views-in-excel.md).</span></span>  
  
### <a name="to-add-new-dimensions"></a><span data-ttu-id="185b8-114">新しいディメンションを追加するには</span><span class="sxs-lookup"><span data-stu-id="185b8-114">To add new dimensions</span></span>  
  
1.  <span data-ttu-id="185b8-115">BAM ビュー ウィザードで、をクリックして**次**が表示されるまで、**新しい BAM ビュー: 集計ディメンションおよび集計メジャー**ページ。</span><span class="sxs-lookup"><span data-stu-id="185b8-115">In the BAM View wizard, click **Next** until you see the **New BAM View: Aggregation Dimensions and Measures** page.</span></span> <span data-ttu-id="185b8-116">をクリックして**新しいディメンションの**します。</span><span class="sxs-lookup"><span data-stu-id="185b8-116">Click **New Dimensions**.</span></span>  
  
2.  <span data-ttu-id="185b8-117">ディメンションの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="185b8-117">Type a name for the dimension.</span></span>  
  
3.  <span data-ttu-id="185b8-118">一覧からディメンションの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="185b8-118">From the drop-down list, select a dimension type.</span></span>  
  
4.  <span data-ttu-id="185b8-119">選択したディメンションの種類に基づいて、適切なデータを入力し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="185b8-119">Based on the dimension type you selected, fill in the appropriate data, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="185b8-120">参照</span><span class="sxs-lookup"><span data-stu-id="185b8-120">See Also</span></span>  
 [<span data-ttu-id="185b8-121">進捗ディメンション</span><span class="sxs-lookup"><span data-stu-id="185b8-121">Progress Dimension</span></span>](../core/progress-dimension.md)