---
title: BAM ポータルのアクティビティの検索 ページ |Microsoft Docs
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
ms.openlocfilehash: 6b01e85495f0cf673c5c781e3accaaf1fc340025
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994123"
---
# <a name="activity-search-on-the-bam-portal-page"></a><span data-ttu-id="62522-102">BAM ポータル ページでのアクティビティの検索</span><span class="sxs-lookup"><span data-stu-id="62522-102">Activity Search on the BAM Portal Page</span></span>
<span data-ttu-id="62522-103">ビジネス エンド ユーザー、開発者、およびビジネス アナリストは、BAM データを検索して特定のプロセスの特定のケースを見つける必要があるときに、BAM ポータル ページを使用できます。</span><span class="sxs-lookup"><span data-stu-id="62522-103">Business end users, developers, and business analysts can use the BAM portal page when they need to perform searches against BAM data to find specific cases of a particular process.</span></span> <span data-ttu-id="62522-104">このようなプロセスが、BAM アクティビティとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="62522-104">These processes are defined as BAM activities.</span></span> <span data-ttu-id="62522-105">BAM アクティビティは、注文書やローンの申し込みなど、ビジネスの作業単位を表します。</span><span class="sxs-lookup"><span data-stu-id="62522-105">A BAM activity represents a unit of work in a business, such as a purchase order or loan application.</span></span>  
  
## <a name="how-an-activity-search-works"></a><span data-ttu-id="62522-106">アクティビティ検索の機能</span><span class="sxs-lookup"><span data-stu-id="62522-106">How an activity search works</span></span>  
 <span data-ttu-id="62522-107">アクティビティの検索では、追跡対象の値と、BAM ビューで使用できる項目を指定する条件を満たすアクティビティを検索して、アクティビティを表示し、編集したり、それらに基づくアラートを作成するために、BAM データに対して検索を実行できます。</span><span class="sxs-lookup"><span data-stu-id="62522-107">An activity search allows you to perform searches against BAM data to find activities that match criteria you specify based on tracked values and items available in a BAM view, and to display the activities so that you can edit them or create alerts based on them.</span></span>  
  
 <span data-ttu-id="62522-108">検索用に作成したクエリは、保存して再利用できます。</span><span class="sxs-lookup"><span data-stu-id="62522-108">Queries that you create for your searches can be saved and reused.</span></span> <span data-ttu-id="62522-109">また、作成したクエリを警告の基準としても使用できます。</span><span class="sxs-lookup"><span data-stu-id="62522-109">You can also use them as the basis for an alert, for example, "Notify me any time a purchase order arrives from the specified customer."</span></span> <span data-ttu-id="62522-110">たとえば、指定した顧客からの注文書が到着したときに通知を希望する場合などです。コンテンツ ページの上部にあるボタンを使用すると、クエリを保存したり、開いたり、実行したりできるだけでなく、警告を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="62522-110">You use the buttons at the top of the content page to save, open, and run queries, as well as to set alerts.</span></span>  
  
 <span data-ttu-id="62522-111">アクティビティの検索では、監視するアクティビティを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="62522-111">Activity searches allow you to locate the activities that you want to monitor.</span></span> <span data-ttu-id="62522-112">アクティビティの検索を作成したら、その検索を使用して、目的のイベントを通知する警告を作成できます。</span><span class="sxs-lookup"><span data-stu-id="62522-112">Once you create an activity search, you can use that search to create an alert that will notify you of events that are of interest.</span></span>  
  
## <a name="the-activity-search-page"></a><span data-ttu-id="62522-113">[アクティビティの検索] ページ</span><span class="sxs-lookup"><span data-stu-id="62522-113">The Activity Search page</span></span>  
 <span data-ttu-id="62522-114">[アクティビティの検索] ページは、コンテンツ フレーム内にあり、次に示す 3 つの主要セクションに分かれています。</span><span class="sxs-lookup"><span data-stu-id="62522-114">The Activity Search page is divided into three main sections inside the Content frame:</span></span>  
  
- <span data-ttu-id="62522-115">**クエリ**: このセクションは、特定の追跡データ項目に基づいて検索句を作成してアクティビティを検索するユーザーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="62522-115">**Query**: This section allows users to search for activities by building search clauses based on specific tracked data items.</span></span> <span data-ttu-id="62522-116">検索句は必要に応じて追加および削除できます。</span><span class="sxs-lookup"><span data-stu-id="62522-116">The user can add and remove clauses as required.</span></span>  
  
- <span data-ttu-id="62522-117">**列の選択**: このセクションではユーザーからのデータのアイテムを指定する検索条件に一致するかどうか、レコードを返す、ビューの使用可能です。</span><span class="sxs-lookup"><span data-stu-id="62522-117">**Column Chooser**: This section allows users to specify which items of data, from those available in that view, to return if any records match the search criteria.</span></span>  
  
- <span data-ttu-id="62522-118">**結果**: このセクションでは、クエリの結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="62522-118">**Results**: Results of the query display in this section.</span></span>  
  
  <span data-ttu-id="62522-119">アクティビティの検索とアクティビティの検索ページの詳細については、次を参照してください。 [BAM ポータルでのアクティビティの検索](../core/activity-searches-in-the-bam-portal.md)します。</span><span class="sxs-lookup"><span data-stu-id="62522-119">For more information about activity searches and the Activity Search page, see [Activity Searches in the BAM Portal](../core/activity-searches-in-the-bam-portal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62522-120">参照</span><span class="sxs-lookup"><span data-stu-id="62522-120">See Also</span></span>  
 <span data-ttu-id="62522-121">[BAM ポータル](../core/bam-portal.md) </span><span class="sxs-lookup"><span data-stu-id="62522-121">[BAM Portal](../core/bam-portal.md) </span></span>  
 <span data-ttu-id="62522-122">[イベント ストリームを使用した BAM アクティビティを実装します。](../core/implementing-bam-activities-with-event-streams.md) </span><span class="sxs-lookup"><span data-stu-id="62522-122">[Implementing BAM Activities with Event Streams](../core/implementing-bam-activities-with-event-streams.md) </span></span>  
 [<span data-ttu-id="62522-123">BAM ポータル ページの警告マネージャー</span><span class="sxs-lookup"><span data-stu-id="62522-123">Alert Manager on the BAM Portal Page</span></span>](../core/alert-manager-on-the-bam-portal-page.md)