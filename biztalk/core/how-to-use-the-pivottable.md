---
title: ピボット テーブルを使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM views, pivot tables
- BAM views, previewing data
ms.assetid: af34494b-f577-4d36-9a9e-5d6e9c5fafbe
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51b0400dd5cf1c21aa0c24ac54e2a72ded2e20fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333209"
---
# <a name="how-to-use-the-pivottable"></a><span data-ttu-id="e3690-102">ピボットテーブルの使用方法</span><span class="sxs-lookup"><span data-stu-id="e3690-102">How to Use the PivotTable</span></span>
<span data-ttu-id="e3690-103">ディメンションとメジャーを含む BAM ビューを定義した場合は、そのビューに関連付けられている 1 つまたは複数のピボット テーブルを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3690-103">When you have defined a BAM view that includes dimensions and measures, you need to update one or more PivotTables associated with that view.</span></span>  
  
 <span data-ttu-id="e3690-104">Excel でピボット テーブル レポートは、対話型のテーブルを簡単に結合および大量のデータを比較することができます。</span><span class="sxs-lookup"><span data-stu-id="e3690-104">A PivotTable report in Excel is an interactive table that enables you to easily combine and compare large amounts of data.</span></span> <span data-ttu-id="e3690-105">表示されるデータの別の概要を見て、その行と列の値を回転できます。</span><span class="sxs-lookup"><span data-stu-id="e3690-105">The values in its rows and columns can be rotated to look at different summaries of the displayed data.</span></span> <span data-ttu-id="e3690-106">ピボット テーブルもできますが、集計カウントや平均など、データに対して計算を実行します。</span><span class="sxs-lookup"><span data-stu-id="e3690-106">A PivotTable also enables you perform calculations on the data, such as aggregate counts or averages.</span></span>  
  
 <span data-ttu-id="e3690-107">作成した後は、ピボット テーブルを使用して、この手順の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e3690-107">To use the PivotTable after you have created it, follow the steps in this procedure.</span></span> <span data-ttu-id="e3690-108">ピボット テーブルの使用に関する詳細については、Microsoft Excel のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3690-108">For more information about using PivotTables, see the Microsoft Excel documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3690-109">リアルタイム集計のピボット テーブルを作成するときは、14 ディメンション レベルの最大値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e3690-109">When you create a real-time aggregation pivot table, it can contain a maximum of 14 dimension levels.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e3690-110">Excel ワークシートに複数のピボット テーブルを定義した場合は、結果として得られるテーブルが成長と重なり合う場合は、アクティビティは、大規模なデータセットを返します。</span><span class="sxs-lookup"><span data-stu-id="e3690-110">If you define multiple PivotTables on the Excel Worksheet, it is possible the resulting tables can grow and overlap each other if the Activity returns a large dataset.</span></span> <span data-ttu-id="e3690-111">このシナリオで「ピボット テーブル レポートは、別のピボット テーブル レポートを重ねることはできません」が表示されます、データを更新するとします。</span><span class="sxs-lookup"><span data-stu-id="e3690-111">In this scenario, you will receive "A PivotTable report cannot overlap another PivotTable report" when you refresh the data.</span></span> <span data-ttu-id="e3690-112">列またはテーブルが重なり合うことなくが増大できるピボット テーブルの間で行を追加することで、このエラーを修正することができます。</span><span class="sxs-lookup"><span data-stu-id="e3690-112">You can correct this error by adding addition columns or rows between the pivot tables to allow the tables to grow with out overlapping.</span></span>  
  
### <a name="to-use-the-pivottable"></a><span data-ttu-id="e3690-113">ピボット テーブルの使用</span><span class="sxs-lookup"><span data-stu-id="e3690-113">To use the PivotTable</span></span>  
  
1.  <span data-ttu-id="e3690-114">ピボット テーブルで使用する BAM ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="e3690-114">Create a BAM view to be used with a PivotTable.</span></span> <span data-ttu-id="e3690-115">BAM ビューの作成方法の詳細については、次を参照してください[ビジネス アクティビティ ビューの定義。](../core/defining-a-bam-view.md)</span><span class="sxs-lookup"><span data-stu-id="e3690-115">For more information about creating a BAM view, see [Defining a Business Activity View](../core/defining-a-bam-view.md)</span></span>  
  
2.  <span data-ttu-id="e3690-116">使用して、**ピボット テーブル フィールド リスト**、ドラッグ アンド ドロップ 1 つ以上使用可能なディメンションをピボット テーブル テンプレートの行と列の領域にします。</span><span class="sxs-lookup"><span data-stu-id="e3690-116">Using the **PivotTable Field List**, drag-and-drop one or more available dimensions into the column and row areas of the PivotTable template.</span></span>  
  
3.  <span data-ttu-id="e3690-117">使用して、**ピボット テーブル フィールド リスト**、ドラッグ アンド ドロップ 1 つまたは複数使用できるメジャー データ項目の領域に、ピボット テーブル テンプレートの。</span><span class="sxs-lookup"><span data-stu-id="e3690-117">Using the  **PivotTable Field List**, drag-and-drop one or more available measures into the data items area of the PivotTable template.</span></span>  
  
     <span data-ttu-id="e3690-118">ピボット テーブルを更新すると、サンプル データを含むことが表示されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="e3690-118">As you are updating the PivotTable, you will notice that it is populated with sample data.</span></span> <span data-ttu-id="e3690-119">これは、ピボット テーブルを構成する方法を決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e3690-119">This helps you determine how the PivotTable should be configured.</span></span>  
  
4.  <span data-ttu-id="e3690-120">使用して、**ピボット テーブル**ツールバーで、グラフ、ピボット テーブルと関連付けます。</span><span class="sxs-lookup"><span data-stu-id="e3690-120">Using the **PivotTable** toolbar, associate a chart with the PivotTable.</span></span>  
  
5.  <span data-ttu-id="e3690-121">Excel ブックを保存します。</span><span class="sxs-lookup"><span data-stu-id="e3690-121">Save your Excel workbook.</span></span>