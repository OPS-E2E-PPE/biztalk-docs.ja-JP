---
title: "ピボット テーブルを使用する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM views, pivot tables
- BAM views, previewing data
ms.assetid: af34494b-f577-4d36-9a9e-5d6e9c5fafbe
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aed416f7a04392804c4c031a69940c4229eabe99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-pivottable"></a><span data-ttu-id="bfb81-102">ピボットテーブルの使用方法</span><span class="sxs-lookup"><span data-stu-id="bfb81-102">How to Use the PivotTable</span></span>
<span data-ttu-id="bfb81-103">ディメンションやビューを含む BAM ビューを定義した場合、そのビューに関連する 1 つ以上のピボットテーブルを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfb81-103">When you have defined a BAM view that includes dimensions and measures, you need to update one or more PivotTables associated with that view.</span></span>  
  
 <span data-ttu-id="bfb81-104">Excel のピボットテーブル レポートは、大量のデータを容易に組み合わせて比較できる対話型のテーブルです。</span><span class="sxs-lookup"><span data-stu-id="bfb81-104">A PivotTable report in Excel is an interactive table that enables you to easily combine and compare large amounts of data.</span></span> <span data-ttu-id="bfb81-105">行や列の値は並べ替えることができ、表示されるデータを別のまとめ方で確認できます。</span><span class="sxs-lookup"><span data-stu-id="bfb81-105">The values in its rows and columns can be rotated to look at different summaries of the displayed data.</span></span> <span data-ttu-id="bfb81-106">また、データに対して集計カウントや平均などの計算を実行できます。</span><span class="sxs-lookup"><span data-stu-id="bfb81-106">A PivotTable also enables you perform calculations on the data, such as aggregate counts or averages.</span></span>  
  
 <span data-ttu-id="bfb81-107">ピボットテーブルを作成して使用するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="bfb81-107">To use the PivotTable after you have created it, follow the steps in this procedure.</span></span> <span data-ttu-id="bfb81-108">ピボットテーブルの使用方法の詳細については、Microsoft Excel のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfb81-108">For more information about using PivotTables, see the Microsoft Excel documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bfb81-109">リアルタイム集計のピボットテーブルを作成する場合は、最大 14 レベルのディメンションを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="bfb81-109">When you create a real-time aggregation pivot table, it can contain a maximum of 14 dimension levels.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bfb81-110">Excel ワークシートで複数のピボットテーブルを定義すると、アクティビティから大きなデータセットが返された場合に、結果のテーブルが増大して重なり合う可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bfb81-110">If you define multiple PivotTables on the Excel Worksheet, it is possible the resulting tables can grow and overlap each other if the Activity returns a large dataset.</span></span> <span data-ttu-id="bfb81-111">このシナリオでは「ピボット テーブル レポートは、別のピボット テーブル レポートを重ねることはできません」が表示されます、データを更新するときにします。</span><span class="sxs-lookup"><span data-stu-id="bfb81-111">In this scenario, you will receive "A PivotTable report cannot overlap another PivotTable report" when you refresh the data.</span></span> <span data-ttu-id="bfb81-112">このエラーを修正するには、テーブルが重なり合うことなく増大できるように、ピボットテーブル間に列または行を追加します。</span><span class="sxs-lookup"><span data-stu-id="bfb81-112">You can correct this error by adding addition columns or rows between the pivot tables to allow the tables to grow with out overlapping.</span></span>  
  
### <a name="to-use-the-pivottable"></a><span data-ttu-id="bfb81-113">ピボットテーブルを使用するには</span><span class="sxs-lookup"><span data-stu-id="bfb81-113">To use the PivotTable</span></span>  
  
1.  <span data-ttu-id="bfb81-114">ピボットテーブルで使用する BAM ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="bfb81-114">Create a BAM view to be used with a PivotTable.</span></span> <span data-ttu-id="bfb81-115">BAM ビューの作成の詳細については、次を参照してください[ビジネス アクティビティ ビューの定義。](../core/defining-a-bam-view.md)</span><span class="sxs-lookup"><span data-stu-id="bfb81-115">For more information about creating a BAM view, see [Defining a Business Activity View](../core/defining-a-bam-view.md)</span></span>  
  
2.  <span data-ttu-id="bfb81-116">使用して、**ピボット テーブル フィールド リスト**、ドラッグ アンド ドロップ 1 つ以上使用可能なディメンションをピボット テーブル テンプレートの行と列の領域にします。</span><span class="sxs-lookup"><span data-stu-id="bfb81-116">Using the **PivotTable Field List**, drag-and-drop one or more available dimensions into the column and row areas of the PivotTable template.</span></span>  
  
3.  <span data-ttu-id="bfb81-117">使用して、**ピボット テーブル フィールド リスト**、ドラッグ アンド ドロップ 1 つ以上使用できるメジャー データ項目の領域に、ピボット テーブル テンプレートのです。</span><span class="sxs-lookup"><span data-stu-id="bfb81-117">Using the  **PivotTable Field List**, drag-and-drop one or more available measures into the data items area of the PivotTable template.</span></span>  
  
     <span data-ttu-id="bfb81-118">ピボットテーブルを更新すると、サンプル データが追加されます。</span><span class="sxs-lookup"><span data-stu-id="bfb81-118">As you are updating the PivotTable, you will notice that it is populated with sample data.</span></span> <span data-ttu-id="bfb81-119">このサンプル データを使用すると、ピボットテーブルの構成方法を判断できます。</span><span class="sxs-lookup"><span data-stu-id="bfb81-119">This helps you determine how the PivotTable should be configured.</span></span>  
  
4.  <span data-ttu-id="bfb81-120">使用して、**ピボット テーブル**ツールバーで、グラフ、ピボット テーブルと関連付けます。</span><span class="sxs-lookup"><span data-stu-id="bfb81-120">Using the **PivotTable** toolbar, associate a chart with the PivotTable.</span></span>  
  
5.  <span data-ttu-id="bfb81-121">Excel のブックを保存します。</span><span class="sxs-lookup"><span data-stu-id="bfb81-121">Save your Excel workbook.</span></span>