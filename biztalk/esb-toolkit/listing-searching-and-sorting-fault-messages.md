---
title: "一覧表示、検索、および並べ替えのエラー メッセージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 850b9682-8eba-4a3f-8508-d3eefcd715b7
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 768dd7f51ff09bad76115f8a7e2a95a11ce47981
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="listing-searching-and-sorting-fault-messages"></a><span data-ttu-id="29255-102">一覧表示、検索、および並べ替えのエラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="29255-102">Listing, Searching, and Sorting Fault Messages</span></span>
<span data-ttu-id="29255-103">ESB の管理ポータルのホーム ページを使用すると、Microsoft BizTalk Server 内で実行されているアプリケーションの状態の全体的なビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="29255-103">You can use the Home page of the ESB Management Portal to obtain an overall view of the status of the applications executing within Microsoft BizTalk Server.</span></span> <span data-ttu-id="29255-104">エラー ページを使用できるさまざまな条件に基づいて、エラー メッセージをクエリします。</span><span class="sxs-lookup"><span data-stu-id="29255-104">The Faults page can be used to query for fault messages, based on a range of criteria.</span></span>  
  
### <a name="to-see-an-overview-of-the-status-of-current-biztalk-server-applications"></a><span data-ttu-id="29255-105">現在の BizTalk Server アプリケーションの状態の概要を表示するには</span><span class="sxs-lookup"><span data-stu-id="29255-105">To see an overview of the status of current BizTalk Server applications</span></span>  
  
1.  <span data-ttu-id="29255-106">開く、[ポータルのホーム ページ](../esb-toolkit/portal-home-page.md)です。</span><span class="sxs-lookup"><span data-stu-id="29255-106">Open the [Portal Home Page](../esb-toolkit/portal-home-page.md).</span></span> <span data-ttu-id="29255-107">このページには、アプリケーション全体の状態、エラーの概要、Universal Description, Discovery, and Integration (UDDI) の登録、およびエラーとアプリケーションの種類によっての内訳を表示するグラフの最近の要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="29255-107">This page displays the overall application state, a summary of faults, recent requests for Universal Description, Discovery, and Integration (UDDI) registration, and charts that show a breakdown of faults by type and by application.</span></span>  
  
2.  <span data-ttu-id="29255-108">情報を表示するアプリケーションを選択するをクリックして、**アプリケーションの選択**最初のグラフの上にリンクし、選択するか表示されるインストール済みの BizTalk Server アプリケーションの一覧にあるチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="29255-108">To select the applications for which you want to view information, click the **Select Applications** link above the first chart, and then select or clear the check boxes in the list of installed BizTalk Server applications that appears.</span></span>  
  
3.  <span data-ttu-id="29255-109">ポータルが情報を表示する期間を変更するには、次のように選択します。**時間、日、週、月、四半期、年、**または**すべて**最初のグラフ上のドロップダウン リストでします。</span><span class="sxs-lookup"><span data-stu-id="29255-109">To change the period for which the portal displays information, select **Hour, Day, Week, Month, Quarter, Year,** or **ALL** in the drop-down list above the first chart.</span></span>  
  
4.  <span data-ttu-id="29255-110">アプリケーションと、表示期間の一覧で、ホーム ページに使用する既定の設定を変更するで設定を編集、[ポータルの [設定] ページ](../esb-toolkit/portal-my-settings-page.md)です。</span><span class="sxs-lookup"><span data-stu-id="29255-110">To change the default settings used on the Home page for the list of applications and the display period, edit the settings on the [Portal My Settings Page](../esb-toolkit/portal-my-settings-page.md).</span></span>  
  
### <a name="to-list-search-for-and-sort-fault-messages-in-the-esb-management-portal"></a><span data-ttu-id="29255-111">この一覧を表示すると、検索、および並べ替えエラー ESB の管理ポータルでメッセージ</span><span class="sxs-lookup"><span data-stu-id="29255-111">To list, search for, and sort fault messages in the ESB Management Portal</span></span>  
  
1.  <span data-ttu-id="29255-112">開く、[設定 ページをフォールト](../esb-toolkit/fault-settings-page.md)です。</span><span class="sxs-lookup"><span data-stu-id="29255-112">Open the [Fault Settings Page](../esb-toolkit/fault-settings-page.md).</span></span> <span data-ttu-id="29255-113">このページは、各エラーのプロパティの切り詰められた一覧を表示し、さまざまな条件でエラーの分析をサポートします。</span><span class="sxs-lookup"><span data-stu-id="29255-113">This page displays a truncated list of properties for each fault and supports analysis of faults by a range of criteria.</span></span>  
  
2.  <span data-ttu-id="29255-114">ページに表示されるエラーの一覧をフィルター処理するには、エラーの一覧の上のテキスト ボックス、ドロップダウン リストを使用します。</span><span class="sxs-lookup"><span data-stu-id="29255-114">To filter the list of faults displayed on the page, use the drop-down lists and text boxes above the list of faults.</span></span> <span data-ttu-id="29255-115">アプリケーション、期間、エラー コード番号、エラー カテゴリの名前、エラーの種類のテキスト、最小値/最大エラーの重大度で表示される行をフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="29255-115">You can filter the rows displayed by application, period, fault code number, fault category name, error type text, and minimum/maximum fault severity.</span></span> <span data-ttu-id="29255-116">空のままにするコントロールのいずれかのこの条件には、その値に関係なくすべてのメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="29255-116">Leave any of the controls empty to retrieve all messages irrespective of their value for this criterion.</span></span>  
  
3.  <span data-ttu-id="29255-117">をクリックして**フィルターの適用**一致するエラーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="29255-117">Click **Apply Filters** to see the list of matching faults.</span></span> <span data-ttu-id="29255-118">非常に大きな障害データベースでフィルター処理がの結果を表示するのには数秒間かかる場合がありますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="29255-118">Note that filtering on very large fault databases may take a few seconds to display results.</span></span>  
  
4.  <span data-ttu-id="29255-119">適切な値の選択ページで、またはより少ない行を表示するには**1 ページあたりのレコード**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="29255-119">To display more or fewer rows in the page, select the appropriate value in the **Records Per Page** drop-down list.</span></span>  
  
5.  <span data-ttu-id="29255-120">エラー メッセージの一覧を並べ替えるには、列見出しをクリックします。</span><span class="sxs-lookup"><span data-stu-id="29255-120">To sort the list of fault messages, click a column heading.</span></span> <span data-ttu-id="29255-121">行を逆順に並べ替えるには、するには、同じ列の見出しをもう一度をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29255-121">To sort the rows in reverse order, click the same column heading again.</span></span>  
  
6.  <span data-ttu-id="29255-122">をクリックして**Excel にエクスポート**Microsoft Excel で表示できる形式でのエラー メッセージの完全な一覧をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="29255-122">Click **Export To Excel** to download the complete list of fault messages in a format that you can view in Microsoft Excel.</span></span>