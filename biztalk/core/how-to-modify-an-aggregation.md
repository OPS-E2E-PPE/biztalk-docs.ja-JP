---
title: "集計を変更する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], modifying
- BAM portal, aggregations
ms.assetid: dd5ce211-32d3-4e1d-8ee0-1225ec2c45fb
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6f5f157da15cb53da41d6735524ed502cd35156
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-modify-an-aggregation"></a><span data-ttu-id="a1435-102">集計を変更する方法</span><span class="sxs-lookup"><span data-stu-id="a1435-102">How to Modify an Aggregation</span></span>
<span data-ttu-id="a1435-103">Office Web コンポーネントでは、Excel でピボットテーブル レポートを使用する場合と同じように、ピボットテーブル レポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a1435-103">You use PivotTable reports in Office Web Components the same way you use PivotTable reports in Excel.</span></span> <span data-ttu-id="a1435-104">行、列、およびフィルターの追加や削除を行って集計データのビューを生成し、このビューに基づいて警告を作成できます。</span><span class="sxs-lookup"><span data-stu-id="a1435-104">You can add and remove rows, columns, and filters to generate views of the aggregated data on which you can create alerts.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a1435-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="a1435-105">Prerequisites</span></span>  
 <span data-ttu-id="a1435-106">ここで説明する手順を実行するには、集計を使用しているビューが展開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1435-106">To perform this procedure, you must have a deployed view that contains an aggregation.</span></span>  
  
### <a name="to-modify-an-aggregation"></a><span data-ttu-id="a1435-107">集計を変更するには</span><span class="sxs-lookup"><span data-stu-id="a1435-107">To modify an aggregation</span></span>  
  
1.  <span data-ttu-id="a1435-108">**集計** ページから、**ピボット テーブル フィールド リスト**ウィンドウで、データ行に表示し、行のフィールドを追加するグリッドの左の列にドロップすると、フィールドをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a1435-108">On the **Aggregations** page, from the **PivotTable Field List** window, drag the fields with data that you want to display in rows and drop them onto the left column of the grid to add row fields.</span></span> <span data-ttu-id="a1435-109">[ピボットテーブル フィールド リスト] ウィンドウが表示されない場合は、ピボットテーブル ドロップ領域の輪郭内をクリックし、[フィールド リストを表示する] が表示されているかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a1435-109">If you don't see the field list, click within the outlines of the PivotTable drop areas, and make sure Show Field List appears.</span></span> <span data-ttu-id="a1435-110">レベルを持つフィールドで利用できる詳細レベルを確認するには、該当フィールドの横の正符号 (+) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1435-110">To see what levels of detail are available in fields that have levels, click the plus sign (+) next to the appropriate field.</span></span>  
  
2.  <span data-ttu-id="a1435-111">ラベルのドロップ領域に列全体で表示するデータを持つフィールドをドラッグして**ここに列のフィールドをドロップ**です。</span><span class="sxs-lookup"><span data-stu-id="a1435-111">Drag fields with data that you want to display across columns to the drop area labeled **Drop Column Fields Here**.</span></span> <span data-ttu-id="a1435-112">カウントまたは進行状況のフィールドとして指定されているフィールドのみをこの領域にドラッグできます。</span><span class="sxs-lookup"><span data-stu-id="a1435-112">Only fields that are designated as counts or progress fields can be dragged to this area.</span></span>  
  
3.  <span data-ttu-id="a1435-113">1 つ以上のデータ フィールドを追加する場合は、順序でこれらのフィールドを配置: データ フィールドを右クリックし、[**順序**ショートカット メニューのコマンドを使用して、**順序**] フィールドに移動] メニューの [します。</span><span class="sxs-lookup"><span data-stu-id="a1435-113">If you add more than one data field, arrange these fields in the order you want: right-click a data field, point to **Order** on the shortcut menu, and use the commands on the **Order** menu to move the field.</span></span>  
  
4.  <span data-ttu-id="a1435-114">フィールドの順序を調整するには、1 つの領域から別の領域にフィールドをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a1435-114">To rearrange fields, drag them from one area to another.</span></span> <span data-ttu-id="a1435-115">フィールドを削除するには、PivotTable レポートからフィールドをドラッグしてナビゲーション フレームにドロップします。</span><span class="sxs-lookup"><span data-stu-id="a1435-115">To remove a field, drag it out of the PivotTable report onto the navigation frame.</span></span>  
  
5.  <span data-ttu-id="a1435-116">PivotTable レポートの [集計] 列で、警告を設定する集計が含まれているセルを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="a1435-116">From the totals column in the PivotTable report, right-click the cell containing the total on which you are going to set an alert.</span></span> <span data-ttu-id="a1435-117">選択**警告の作成**アラートの管理ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="a1435-117">Select **Create Alert** to open the Alert Management page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1435-118">参照</span><span class="sxs-lookup"><span data-stu-id="a1435-118">See Also</span></span>  
 <span data-ttu-id="a1435-119">[BAM ポータルの集計 ページ](../core/aggregations-on-the-bam-portal-page.md) </span><span class="sxs-lookup"><span data-stu-id="a1435-119">[Aggregations on the BAM Portal Page](../core/aggregations-on-the-bam-portal-page.md) </span></span>  
 [<span data-ttu-id="a1435-120">警告を設定する方法</span><span class="sxs-lookup"><span data-stu-id="a1435-120">How to Set an Alert</span></span>](../core/how-to-set-an-alert.md)