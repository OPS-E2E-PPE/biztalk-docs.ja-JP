---
title: 集計を変更する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], modifying
- BAM portal, aggregations
ms.assetid: dd5ce211-32d3-4e1d-8ee0-1225ec2c45fb
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a073b454a270de2e7ac4f78c421513936d8f7ecd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336147"
---
# <a name="how-to-modify-an-aggregation"></a><span data-ttu-id="a93d6-102">集計を変更する方法</span><span class="sxs-lookup"><span data-stu-id="a93d6-102">How to Modify an Aggregation</span></span>
<span data-ttu-id="a93d6-103">Office Web コンポーネントが Excel でピボット テーブルを使用する場合と同様のレポートでは、ピボット テーブル レポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="a93d6-103">You use PivotTable reports in Office Web Components the same way you use PivotTable reports in Excel.</span></span> <span data-ttu-id="a93d6-104">追加し、行、列、およびアラートを作成することができます、集計されたデータのビューを生成するためのフィルターを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="a93d6-104">You can add and remove rows, columns, and filters to generate views of the aggregated data on which you can create alerts.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a93d6-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="a93d6-105">Prerequisites</span></span>  
 <span data-ttu-id="a93d6-106">この手順を実行するには、集計を含むビューが展開が必要です。</span><span class="sxs-lookup"><span data-stu-id="a93d6-106">To perform this procedure, you must have a deployed view that contains an aggregation.</span></span>  
  
### <a name="to-modify-an-aggregation"></a><span data-ttu-id="a93d6-107">集計を変更するには</span><span class="sxs-lookup"><span data-stu-id="a93d6-107">To modify an aggregation</span></span>  
  
1.  <span data-ttu-id="a93d6-108">**集計** ページから、**ピボット テーブル フィールド リスト**ウィンドウで、行に表示し、行のフィールドを追加するグリッドの左の列にドロップするデータを含むフィールドをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a93d6-108">On the **Aggregations** page, from the **PivotTable Field List** window, drag the fields with data that you want to display in rows and drop them onto the left column of the grid to add row fields.</span></span> <span data-ttu-id="a93d6-109">ピボット テーブルのドロップ領域の輪郭内をクリックし、確認は、フィールドの一覧が表示されない場合は、フィールド リストの表示が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a93d6-109">If you don't see the field list, click within the outlines of the PivotTable drop areas, and make sure Show Field List appears.</span></span> <span data-ttu-id="a93d6-110">レベルが設定されたフィールドに詳細のレベルが使用可能なを表示するには、適切なフィールドの横にあるプラス記号 (+) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a93d6-110">To see what levels of detail are available in fields that have levels, click the plus sign (+) next to the appropriate field.</span></span>  
  
2.  <span data-ttu-id="a93d6-111">ラベルのドロップ領域に列全体を表示するデータ フィールドをドラッグして**ここに列フィールドをドロップ**します。</span><span class="sxs-lookup"><span data-stu-id="a93d6-111">Drag fields with data that you want to display across columns to the drop area labeled **Drop Column Fields Here**.</span></span> <span data-ttu-id="a93d6-112">フィールドだけをカウントとして指定された、または進行状況のフィールドは、この領域にドラッグできます。</span><span class="sxs-lookup"><span data-stu-id="a93d6-112">Only fields that are designated as counts or progress fields can be dragged to this area.</span></span>  
  
3.  <span data-ttu-id="a93d6-113">配置する順序でこれらのフィールドの 1 つ以上のデータ フィールドを追加する場合: データ フィールドを右クリックし、**順序**ショートカット メニューのコマンドを使用して、**順序**フィールドを移動するメニュー。</span><span class="sxs-lookup"><span data-stu-id="a93d6-113">If you add more than one data field, arrange these fields in the order you want: right-click a data field, point to **Order** on the shortcut menu, and use the commands on the **Order** menu to move the field.</span></span>  
  
4.  <span data-ttu-id="a93d6-114">フィールドを再配置するには 1 つの領域から別にそれらをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a93d6-114">To rearrange fields, drag them from one area to another.</span></span> <span data-ttu-id="a93d6-115">フィールドを削除するには、ピボット テーブル レポートのナビゲーション フレームに外にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a93d6-115">To remove a field, drag it out of the PivotTable report onto the navigation frame.</span></span>  
  
5.  <span data-ttu-id="a93d6-116">ピボット テーブル レポートの合計 列からアラートを設定しようとするが合計を含むセルを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="a93d6-116">From the totals column in the PivotTable report, right-click the cell containing the total on which you are going to set an alert.</span></span> <span data-ttu-id="a93d6-117">選択**アラートの作成**アラートの管理ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="a93d6-117">Select **Create Alert** to open the Alert Management page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a93d6-118">参照</span><span class="sxs-lookup"><span data-stu-id="a93d6-118">See Also</span></span>  
 <span data-ttu-id="a93d6-119">[BAM ポータルでの集計 ページ](../core/aggregations-on-the-bam-portal-page.md) </span><span class="sxs-lookup"><span data-stu-id="a93d6-119">[Aggregations on the BAM Portal Page](../core/aggregations-on-the-bam-portal-page.md) </span></span>  
 [<span data-ttu-id="a93d6-120">アラートを設定する方法</span><span class="sxs-lookup"><span data-stu-id="a93d6-120">How to Set an Alert</span></span>](../core/how-to-set-an-alert.md)