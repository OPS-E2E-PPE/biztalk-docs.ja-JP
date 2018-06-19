---
title: BAM ポータルにアクティビティの検索ページ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], searching
- Activity Search page [BAM portal]
- BAM portal, activity searches
ms.assetid: 24a5111c-026f-4f77-8a17-65955aafd24c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 670d73cb33d9e3cc3aa1a9162cf929382a4dd58a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225122"
---
# <a name="activity-search-on-the-bam-portal-page"></a><span data-ttu-id="e403f-102">BAM ポータル ページでのアクティビティの検索</span><span class="sxs-lookup"><span data-stu-id="e403f-102">Activity Search on the BAM Portal Page</span></span>
<span data-ttu-id="e403f-103">ビジネス エンド ユーザー、開発者、およびビジネス アナリストは、BAM データを検索して特定のプロセスの特定のケースを見つける必要があるときに、BAM ポータル ページを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e403f-103">Business end users, developers, and business analysts can use the BAM portal page when they need to perform searches against BAM data to find specific cases of a particular process.</span></span> <span data-ttu-id="e403f-104">このようなプロセスが、BAM アクティビティとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="e403f-104">These processes are defined as BAM activities.</span></span> <span data-ttu-id="e403f-105">BAM アクティビティは、注文書やローンの申し込みなど、ビジネスの作業単位を表します。</span><span class="sxs-lookup"><span data-stu-id="e403f-105">A BAM activity represents a unit of work in a business, such as a purchase order or loan application.</span></span>  
  
## <a name="how-an-activity-search-works"></a><span data-ttu-id="e403f-106">アクティビティ検索の機能</span><span class="sxs-lookup"><span data-stu-id="e403f-106">How an activity search works</span></span>  
 <span data-ttu-id="e403f-107">アクティビティの検索では、追跡されている値と、BAM ビューで利用可能なアイテムを指定する条件を満たす活動を検索して、アクティビティを表示し、編集したり、それらに基づくアラートを作成できるように、BAM データに対して検索を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="e403f-107">An activity search allows you to perform searches against BAM data to find activities that match criteria you specify based on tracked values and items available in a BAM view, and to display the activities so that you can edit them or create alerts based on them.</span></span>  
  
 <span data-ttu-id="e403f-108">検索用に作成したクエリは、保存して再利用できます。</span><span class="sxs-lookup"><span data-stu-id="e403f-108">Queries that you create for your searches can be saved and reused.</span></span> <span data-ttu-id="e403f-109">また、作成したクエリを警告の基準としても使用できます。</span><span class="sxs-lookup"><span data-stu-id="e403f-109">You can also use them as the basis for an alert, for example, "Notify me any time a purchase order arrives from the specified customer."</span></span> <span data-ttu-id="e403f-110">たとえば、指定した顧客からの注文書が到着したときに通知を希望する場合などです。コンテンツ ページの上部にあるボタンを使用すると、クエリを保存したり、開いたり、実行したりできるだけでなく、警告を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="e403f-110">You use the buttons at the top of the content page to save, open, and run queries, as well as to set alerts.</span></span>  
  
 <span data-ttu-id="e403f-111">アクティビティの検索では、監視するアクティビティを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="e403f-111">Activity searches allow you to locate the activities that you want to monitor.</span></span> <span data-ttu-id="e403f-112">アクティビティの検索を作成したら、その検索を使用して、目的のイベントを通知する警告を作成できます。</span><span class="sxs-lookup"><span data-stu-id="e403f-112">Once you create an activity search, you can use that search to create an alert that will notify you of events that are of interest.</span></span>  
  
## <a name="the-activity-search-page"></a><span data-ttu-id="e403f-113">[アクティビティの検索] ページ</span><span class="sxs-lookup"><span data-stu-id="e403f-113">The Activity Search page</span></span>  
 <span data-ttu-id="e403f-114">[アクティビティの検索] ページは、コンテンツ フレーム内にあり、次に示す 3 つの主要セクションに分かれています。</span><span class="sxs-lookup"><span data-stu-id="e403f-114">The Activity Search page is divided into three main sections inside the Content frame:</span></span>  
  
-   <span data-ttu-id="e403f-115">**クエリ**: このセクションでは、特定の追跡対象データ項目に基づいて検索句を作成してアクティビティを検索するユーザー。</span><span class="sxs-lookup"><span data-stu-id="e403f-115">**Query**: This section allows users to search for activities by building search clauses based on specific tracked data items.</span></span> <span data-ttu-id="e403f-116">検索句は必要に応じて追加および削除できます。</span><span class="sxs-lookup"><span data-stu-id="e403f-116">The user can add and remove clauses as required.</span></span>  
  
-   <span data-ttu-id="e403f-117">**列の選択**: このセクションに指定できるものから、データの項目を検索条件に一致するかどうか、レコードを返す、ビューの使用可能です。</span><span class="sxs-lookup"><span data-stu-id="e403f-117">**Column Chooser**: This section allows users to specify which items of data, from those available in that view, to return if any records match the search criteria.</span></span>  
  
-   <span data-ttu-id="e403f-118">**結果**: このセクションで、クエリの結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="e403f-118">**Results**: Results of the query display in this section.</span></span>  
  
 <span data-ttu-id="e403f-119">アクティビティの検索と、アクティビティの検索ページの詳細については、次を参照してください。 [BAM ポータルでのアクティビティの検索](../core/activity-searches-in-the-bam-portal.md)です。</span><span class="sxs-lookup"><span data-stu-id="e403f-119">For more information about activity searches and the Activity Search page, see [Activity Searches in the BAM Portal](../core/activity-searches-in-the-bam-portal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e403f-120">参照</span><span class="sxs-lookup"><span data-stu-id="e403f-120">See Also</span></span>  
 <span data-ttu-id="e403f-121">[BAM ポータル](../core/bam-portal.md) </span><span class="sxs-lookup"><span data-stu-id="e403f-121">[BAM Portal](../core/bam-portal.md) </span></span>  
 <span data-ttu-id="e403f-122">[BAM アクティビティのイベント ストリームの実装](../core/implementing-bam-activities-with-event-streams.md) </span><span class="sxs-lookup"><span data-stu-id="e403f-122">[Implementing BAM Activities with Event Streams](../core/implementing-bam-activities-with-event-streams.md) </span></span>  
 [<span data-ttu-id="e403f-123">警告マネージャーで、BAM ポータル ページ</span><span class="sxs-lookup"><span data-stu-id="e403f-123">Alert Manager on the BAM Portal Page</span></span>](../core/alert-manager-on-the-bam-portal-page.md)