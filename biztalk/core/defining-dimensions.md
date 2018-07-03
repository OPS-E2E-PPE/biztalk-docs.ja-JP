---
title: ディメンションの定義 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], dimensions
- BAM, dimensions
- BAM views, dimensions
- Excel add-in [BAM], creating dimensions
- dimensions [BAM]
ms.assetid: c00e0c45-eef2-42d9-832c-4be08d79203f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be3c55298b58d2d5ca51652ed9911c901235863e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013659"
---
# <a name="defining-dimensions"></a><span data-ttu-id="7e57a-102">ディメンションの定義</span><span class="sxs-lookup"><span data-stu-id="7e57a-102">Defining Dimensions</span></span>
<span data-ttu-id="7e57a-103">Microsoft Excel では、ディメンションをカテゴリとして定義し、それによってテーブルのデータを分析に使用できるようにレベル分けします。</span><span class="sxs-lookup"><span data-stu-id="7e57a-103">Microsoft Excel defines dimensions as categories used to organize data in a table into levels that will be used for analysis.</span></span> <span data-ttu-id="7e57a-104">たとえば、場所データのディメンションの場合、市や都道府県、国/地域などのレベルが考えられます。</span><span class="sxs-lookup"><span data-stu-id="7e57a-104">For example, a location data dimension might contain levels such as city, state/province, and country/region.</span></span> <span data-ttu-id="7e57a-105">BAM ビュー ウィザードで BAM ビューを作成すると、次の 1 つ以上の種類のディメンションを追加できます。</span><span class="sxs-lookup"><span data-stu-id="7e57a-105">When creating BAM Views in the BAM View wizard, you can add one or more of the following dimension types:</span></span>  
  
- [<span data-ttu-id="7e57a-106">進捗ディメンション</span><span class="sxs-lookup"><span data-stu-id="7e57a-106">Progress Dimension</span></span>](../core/progress-dimension.md)  
  
- [<span data-ttu-id="7e57a-107">データ ディメンション</span><span class="sxs-lookup"><span data-stu-id="7e57a-107">Data Dimension</span></span>](../core/data-dimension.md)  
  
- [<span data-ttu-id="7e57a-108">時間ディメンション</span><span class="sxs-lookup"><span data-stu-id="7e57a-108">Time Dimension</span></span>](../core/time-dimension.md)  
  
- [<span data-ttu-id="7e57a-109">数値範囲ディメンション</span><span class="sxs-lookup"><span data-stu-id="7e57a-109">Numeric Range Dimension</span></span>](../core/numeric-range-dimension.md)  
  
  <span data-ttu-id="7e57a-110">![](../core/media/bam-olap-cube.gif "bam_olap_cube")</span><span class="sxs-lookup"><span data-stu-id="7e57a-110">![](../core/media/bam-olap-cube.gif "bam_olap_cube")</span></span>  
  <span data-ttu-id="7e57a-111">事前に計算された集計データ</span><span class="sxs-lookup"><span data-stu-id="7e57a-111">Pre-calculated Aggregation Data</span></span>  
  
  <span data-ttu-id="7e57a-112">新しいディメンションは BAM ビュー ウィザードで追加します。</span><span class="sxs-lookup"><span data-stu-id="7e57a-112">You add new dimensions in the BAM View wizard.</span></span> <span data-ttu-id="7e57a-113">ディメンションを追加するには、先にウィザードを使用してビジネス アクティビティ ビューを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e57a-113">Before you can add dimensions, you need to use the wizard to create business activity views.</span></span> <span data-ttu-id="7e57a-114">詳細については、ウィザードを使用して、次を参照してください。[ビジネス アクティビティの定義および Excel でのビュー](../core/defining-business-activities-and-views-in-excel.md)します。</span><span class="sxs-lookup"><span data-stu-id="7e57a-114">For more information about using the wizard, see [Define Business Activities and Views in Excel](../core/defining-business-activities-and-views-in-excel.md).</span></span>  
  
### <a name="to-add-new-dimensions"></a><span data-ttu-id="7e57a-115">新しいディメンションを追加するには</span><span class="sxs-lookup"><span data-stu-id="7e57a-115">To add new dimensions</span></span>  
  
1.  <span data-ttu-id="7e57a-116">BAM ビュー ウィザードで、**次**が表示されるまで、**新しい BAM ビュー: 集計ディメンションおよび集計メジャー**ページ。</span><span class="sxs-lookup"><span data-stu-id="7e57a-116">In the BAM View wizard, click **Next** until you see the **New BAM View: Aggregation Dimensions and Measures** page.</span></span> <span data-ttu-id="7e57a-117">クリックして**新しいディメンションの**します。</span><span class="sxs-lookup"><span data-stu-id="7e57a-117">Click **New Dimensions**.</span></span>  
  
2.  <span data-ttu-id="7e57a-118">ディメンションの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="7e57a-118">Type a name for the dimension.</span></span>  
  
3.  <span data-ttu-id="7e57a-119">一覧からディメンションの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e57a-119">From the drop-down list, select a dimension type.</span></span>  
  
4.  <span data-ttu-id="7e57a-120">選択したディメンションの種類に基づいて、適切なデータを入力し、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="7e57a-120">Based on the dimension type you selected, fill in the appropriate data, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e57a-121">参照</span><span class="sxs-lookup"><span data-stu-id="7e57a-121">See Also</span></span>  
 [<span data-ttu-id="7e57a-122">進捗ディメンション</span><span class="sxs-lookup"><span data-stu-id="7e57a-122">Progress Dimension</span></span>](../core/progress-dimension.md)