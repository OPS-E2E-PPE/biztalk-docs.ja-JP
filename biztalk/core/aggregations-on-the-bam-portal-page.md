---
title: "BAM ポータルの集計ページ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], alerts
- aggregations [BAM], viewing results
- alerts, aggregations
- Aggregations page [BAM portal]
- BAM portal, aggregations
ms.assetid: 6bc1a6f2-9e9a-4db6-aaa1-188ed2f2641f
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a61df22bf5d07bd1b4d955f2baf884459de52998
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="aggregations-on-the-bam-portal-page"></a><span data-ttu-id="5e46e-102">BAM ポータル ページでの集計</span><span class="sxs-lookup"><span data-stu-id="5e46e-102">Aggregations on the BAM Portal Page</span></span>
<span data-ttu-id="5e46e-103">ビジネス エンド ユーザー、開発者、およびビジネス アナリストは、集計データを提供する必要があるときに BAM ポータル ページを使用します。集計データとは、データセットを事前に計算してまとめたもので、データセットが表す特性を伝達します。</span><span class="sxs-lookup"><span data-stu-id="5e46e-103">Business end users, developers, and business analysts use the BAM portal page when they need to present aggregated data, which are precalculated summaries of a data set that convey representative characteristics of that data set.</span></span> <span data-ttu-id="5e46e-104">BAM ポータルの [集計] ページを使用すると、グラフィカルなグラフやピボットテーブル レポートの形式で集計データを表示できます。</span><span class="sxs-lookup"><span data-stu-id="5e46e-104">The Aggregations page of the BAM portal allows you to display aggregated data in the form of a graphical chart and accompanying PivotTable report.</span></span>  
  
## <a name="the-aggregations-page"></a><span data-ttu-id="5e46e-105">[集計] ページ</span><span class="sxs-lookup"><span data-stu-id="5e46e-105">The Aggregations page</span></span>  
 <span data-ttu-id="5e46e-106">[集計] ページでは、プロセスの状態またはビジネス全体の状態をまとめて伝達する、アクティビティの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e46e-106">The Aggregations page displays the results of an activity that collectively convey the health of the process or of the overall business.</span></span> <span data-ttu-id="5e46e-107">たとえば、受け取った 1,000 件の請求書の内訳を、各請求書の処理段階という観点から示す ("評価中" が 400 件、拒否が 400 件、支払済みが 100 件、"資金割当中" が 100 件など) 簡単な円グラフをユーザーが参照する場合などに利用できます。</span><span class="sxs-lookup"><span data-stu-id="5e46e-107">For example, a user may want to see a simple pie chart that shows a breakdown of the 1,000 invoices received in terms of what stage of processing has been reached by each invoice (400 still in "evaluation," 400 rejected, 100 paid, and 100 still in "fund allocation").</span></span>  
  
### <a name="creating-alerts-for-aggregations"></a><span data-ttu-id="5e46e-108">集計に関する警告の作成</span><span class="sxs-lookup"><span data-stu-id="5e46e-108">Creating alerts for aggregations</span></span>  
 <span data-ttu-id="5e46e-109">集計を基にして警告を作成できます。たとえば、プロセスの "評価" 段階に達した請求書が 500 件を超えた場合に通知するように設定できます。</span><span class="sxs-lookup"><span data-stu-id="5e46e-109">You can use aggregations as the basis for creating an alert ("Notify me if there are ever more than 500 invoices in the "evaluation" stage of the process).</span></span> <span data-ttu-id="5e46e-110">これを行うには、ピボット テーブルの任意のセルを右クリックして選択**警告の設定**、セルをクリックし、をクリックするか、**警告の設定**ピボット テーブル レポートの右側にあるボタンです。</span><span class="sxs-lookup"><span data-stu-id="5e46e-110">To do this, you right-click any PivotTable cell and select **Set Alert**, or you click a cell and click the **Set Alert** button to the right of the PivotTable report.</span></span> <span data-ttu-id="5e46e-111">警告の作成の詳細については、次を参照してください。[警告を設定する方法](../core/how-to-set-an-alert.md)です。</span><span class="sxs-lookup"><span data-stu-id="5e46e-111">For more information about creating an alert, see [How to Set an Alert](../core/how-to-set-an-alert.md).</span></span>  
  
### <a name="viewing-individual-results-of-aggregations"></a><span data-ttu-id="5e46e-112">集計の個別の結果の表示</span><span class="sxs-lookup"><span data-stu-id="5e46e-112">Viewing individual results of aggregations</span></span>  
 <span data-ttu-id="5e46e-113">集計の数値 (たとえば、"評価中" の 400 件の請求書) を選択して、集計の個別の結果を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="5e46e-113">You can also select any aggregate amount (for example, 400 invoices still in "evaluation") and see the individual results for the aggregation.</span></span> <span data-ttu-id="5e46e-114">個々 の結果にアクセスするには、ピボット テーブルの任意のセルを右クリックしを選択すると**結果の表示**です。</span><span class="sxs-lookup"><span data-stu-id="5e46e-114">You access the individual results by right-clicking any PivotTable cell and selecting **Show Results**.</span></span> <span data-ttu-id="5e46e-115">この操作によって、[アクティビティの検索] ページが表示されます。検索自体は自動的に構築され、その結果が表示されます (この例では、400 件の各請求書に対してレコードが 1 件ずつ表示されます)。</span><span class="sxs-lookup"><span data-stu-id="5e46e-115">In response to this action, you are sent to the Activity Search page, the search itself is automatically constructed, and the results are displayed (in this example, one record for each of the 400 invoices).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e46e-116">一部の BAM ビューには、集計が関連付けられていません。そのため、ビューの作成方法によっては、アクセスできる情報が存在しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="5e46e-116">Some BAM views do not have aggregations associated with them, and so there may be no information to access depending on how the view was created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e46e-117">参照</span><span class="sxs-lookup"><span data-stu-id="5e46e-117">See Also</span></span>  
 <span data-ttu-id="5e46e-118">[BAM ポータル](../core/bam-portal.md) </span><span class="sxs-lookup"><span data-stu-id="5e46e-118">[BAM Portal](../core/bam-portal.md) </span></span>  
 <span data-ttu-id="5e46e-119">[BAM ポータルにアクティビティの検索 ページ](../core/activity-search-on-the-bam-portal-page.md) </span><span class="sxs-lookup"><span data-stu-id="5e46e-119">[Activity Search on the BAM Portal Page](../core/activity-search-on-the-bam-portal-page.md) </span></span>  
 [<span data-ttu-id="5e46e-120">警告マネージャーで、BAM ポータル ページ</span><span class="sxs-lookup"><span data-stu-id="5e46e-120">Alert Manager on the BAM Portal Page</span></span>](../core/alert-manager-on-the-bam-portal-page.md)