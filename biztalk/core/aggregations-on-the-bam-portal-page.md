---
title: BAM ポータルでの集計ページ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], alerts
- aggregations [BAM], viewing results
- alerts, aggregations
- Aggregations page [BAM portal]
- BAM portal, aggregations
ms.assetid: 6bc1a6f2-9e9a-4db6-aaa1-188ed2f2641f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5b242091e72ec4bc0ae56fdf27be5228583b7b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360157"
---
# <a name="aggregations-on-the-bam-portal-page"></a><span data-ttu-id="6a7fc-102">BAM ポータルでの集計 ページ</span><span class="sxs-lookup"><span data-stu-id="6a7fc-102">Aggregations on the BAM Portal Page</span></span>
<span data-ttu-id="6a7fc-103">ビジネス エンドユーザー、開発者、およびビジネス アナリストはデータ セットのデータ セットの特性を伝達事前計算済みの集計、集計のデータを提示する必要がある場合、BAM ポータル ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="6a7fc-103">Business end users, developers, and business analysts use the BAM portal page when they need to present aggregated data, which are precalculated summaries of a data set that convey representative characteristics of that data set.</span></span> <span data-ttu-id="6a7fc-104">BAM ポータルの [集計] ページでは、グラフィカルなグラフとピボット テーブル レポートの形式で集計データを表示できます。</span><span class="sxs-lookup"><span data-stu-id="6a7fc-104">The Aggregations page of the BAM portal allows you to display aggregated data in the form of a graphical chart and accompanying PivotTable report.</span></span>  
  
## <a name="the-aggregations-page"></a><span data-ttu-id="6a7fc-105">[集計] ページ</span><span class="sxs-lookup"><span data-stu-id="6a7fc-105">The Aggregations page</span></span>  
 <span data-ttu-id="6a7fc-106">[集計] ページをまとめて、プロセスやビジネス全体の正常性を伝達するアクティビティの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a7fc-106">The Aggregations page displays the results of an activity that collectively convey the health of the process or of the overall business.</span></span> <span data-ttu-id="6a7fc-107">たとえば、ユーザーは各請求書 (「評価、」400 が拒否されると、「資金割当中」で、有料と 100 の 100 件でも 400) による処理の段階に達しているの観点から受け取った 1,000 の請求書の内訳を表示する単純な円グラフを表示することがあります。</span><span class="sxs-lookup"><span data-stu-id="6a7fc-107">For example, a user may want to see a simple pie chart that shows a breakdown of the 1,000 invoices received in terms of what stage of processing has been reached by each invoice (400 still in "evaluation," 400 rejected, 100 paid, and 100 still in "fund allocation").</span></span>  
  
### <a name="creating-alerts-for-aggregations"></a><span data-ttu-id="6a7fc-108">集計に関する警告を作成します。</span><span class="sxs-lookup"><span data-stu-id="6a7fc-108">Creating alerts for aggregations</span></span>  
 <span data-ttu-id="6a7fc-109">("通知プロセスの「評価」段階に 500 件を超えた請求書がある場合)、アラートを作成するための基礎として集計を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6a7fc-109">You can use aggregations as the basis for creating an alert ("Notify me if there are ever more than 500 invoices in the "evaluation" stage of the process).</span></span> <span data-ttu-id="6a7fc-110">これを行うには、ピボット テーブルの任意のセルを右クリックして選択**警告の設定**、またはセルをクリックします をクリックして、**警告の設定**ピボット テーブル レポートの右ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a7fc-110">To do this, you right-click any PivotTable cell and select **Set Alert**, or you click a cell and click the **Set Alert** button to the right of the PivotTable report.</span></span> <span data-ttu-id="6a7fc-111">アラートの作成の詳細については、次を参照してください。[アラートを設定する方法](../core/how-to-set-an-alert.md)します。</span><span class="sxs-lookup"><span data-stu-id="6a7fc-111">For more information about creating an alert, see [How to Set an Alert](../core/how-to-set-an-alert.md).</span></span>  
  
### <a name="viewing-individual-results-of-aggregations"></a><span data-ttu-id="6a7fc-112">集計の個別の結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="6a7fc-112">Viewing individual results of aggregations</span></span>  
 <span data-ttu-id="6a7fc-113">集計の数値 (「評価」の中の 400 請求など) を選択します。 また、集計の個別の結果を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a7fc-113">You can also select any aggregate amount (for example, 400 invoices still in "evaluation") and see the individual results for the aggregation.</span></span> <span data-ttu-id="6a7fc-114">個々 の結果にアクセスするには、ピボット テーブルの任意のセルを右クリックし、選択**結果の表示**します。</span><span class="sxs-lookup"><span data-stu-id="6a7fc-114">You access the individual results by right-clicking any PivotTable cell and selecting **Show Results**.</span></span> <span data-ttu-id="6a7fc-115">この操作に応答して、アクティビティの検索ページに送信する、および検索自体は自動的に構築され、(この例では、それぞれ 400 の請求書の 1 つのレコード) では、結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a7fc-115">In response to this action, you are sent to the Activity Search page, the search itself is automatically constructed, and the results are displayed (in this example, one record for each of the 400 invoices).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a7fc-116">一部の BAM ビューには、それらに関連付けられている集計はありませんのでない可能性があります、ビューの作成方法によって、アクセスできる情報.</span><span class="sxs-lookup"><span data-stu-id="6a7fc-116">Some BAM views do not have aggregations associated with them, and so there may be no information to access depending on how the view was created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a7fc-117">参照</span><span class="sxs-lookup"><span data-stu-id="6a7fc-117">See Also</span></span>  
 <span data-ttu-id="6a7fc-118">[BAM ポータル](../core/bam-portal.md) </span><span class="sxs-lookup"><span data-stu-id="6a7fc-118">[BAM Portal](../core/bam-portal.md) </span></span>  
 <span data-ttu-id="6a7fc-119">[BAM ポータルのアクティビティの検索ページ](../core/activity-search-on-the-bam-portal-page.md) </span><span class="sxs-lookup"><span data-stu-id="6a7fc-119">[Activity Search on the BAM Portal Page](../core/activity-search-on-the-bam-portal-page.md) </span></span>  
 [<span data-ttu-id="6a7fc-120">BAM ポータル ページの警告マネージャー</span><span class="sxs-lookup"><span data-stu-id="6a7fc-120">Alert Manager on the BAM Portal Page</span></span>](../core/alert-manager-on-the-bam-portal-page.md)