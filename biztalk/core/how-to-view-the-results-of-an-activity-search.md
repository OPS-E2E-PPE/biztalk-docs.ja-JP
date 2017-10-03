---
title: "アクティビティの検索の結果を表示する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- queries [BAM], activity searches
- queries [BAM], viewing results
- Query Builder [BAM portal], activity searches
- queries [BAM], executing
- Query Builder [BAM portal], executing queries
- Query Builder [BAM portal], viewing details
- queries [BAM], viewing details
- Query Builder [BAM portal], viewing results
ms.assetid: d45cd777-d798-4f3b-ad9a-5121168d7b99
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c5e96da9ed256557306cc4d69ad529161fa3342
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-view-the-results-of-an-activity-search"></a><span data-ttu-id="16d7d-102">アクティビティの検索の結果を表示する方法</span><span class="sxs-lookup"><span data-stu-id="16d7d-102">How to View the Results of an Activity Search</span></span>
<span data-ttu-id="16d7d-103">ユーザーをクリックして、クエリの結果を表示できます、**クエリの実行**BAM ポータルのコンテンツ フレームの上部のセクションでボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="16d7d-103">Users can view the results of a query by clicking the **Execute Query** button in the upper section of the content frame of the BAM portal.</span></span> <span data-ttu-id="16d7d-104">クエリの結果に表示されます、**結果**フレームの下部のセクションです。</span><span class="sxs-lookup"><span data-stu-id="16d7d-104">The results of the query are displayed in the **Results** section at the bottom of the frame.</span></span>  
  
 <span data-ttu-id="16d7d-105">アクティビティの検索の結果は各行に 1 レコードずつ表示されます。</span><span class="sxs-lookup"><span data-stu-id="16d7d-105">The results of an activity search are displayed with one record per row.</span></span> <span data-ttu-id="16d7d-106">各レコードから成るデータとマイルス トーンは、列の選択 で選択されているしで配置された順に表示されます、**に表示される項目**ボックス。</span><span class="sxs-lookup"><span data-stu-id="16d7d-106">Each record consists of the data and milestones selected in the column chooser and are displayed in the order in which they were arranged in the **Items to show** box.</span></span>  
  
 <span data-ttu-id="16d7d-107">返されたレコードの詳細を確認するには、行内の任意の場所をクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="16d7d-107">To get additional details about a returned record you can click anywhere in the row.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="16d7d-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="16d7d-108">Prerequisites</span></span>  
 <span data-ttu-id="16d7d-109">このトピックの手順を実行するには、アクティビティが展開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="16d7d-109">You must have a deployed activity to perform the procedures in this topic.</span></span> <span data-ttu-id="16d7d-110">これを行う方法については、次を参照してください。[を適用し、追跡プロファイルを削除する方法](../core/how-to-apply-and-remove-a-tracking-profile.md)です。</span><span class="sxs-lookup"><span data-stu-id="16d7d-110">For information about how to do this, see [How to Apply and Remove a Tracking Profile](../core/how-to-apply-and-remove-a-tracking-profile.md).</span></span>  
  
## <a name="return-results"></a><span data-ttu-id="16d7d-111">結果を返す</span><span class="sxs-lookup"><span data-stu-id="16d7d-111">Return results</span></span>  
  
#### <a name="to-execute-a-query-to-return-results"></a><span data-ttu-id="16d7d-112">結果を返すクエリを実行するには</span><span class="sxs-lookup"><span data-stu-id="16d7d-112">To execute a query to return results</span></span>  
  
1.  <span data-ttu-id="16d7d-113">をクリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BAM ポータル Web サイト**です。</span><span class="sxs-lookup"><span data-stu-id="16d7d-113">Click **Start**, point to **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BAM Portal Web Site**.</span></span>  
  
2.  <span data-ttu-id="16d7d-114">**マイ ビュー**  ウィンドウで、アクティビティの検索を作成するビューをクリックします。</span><span class="sxs-lookup"><span data-stu-id="16d7d-114">In the **My Views** pane, click a view for which you are creating the activity search.</span></span>  
  
3.  <span data-ttu-id="16d7d-115">そのビューに関連するアクティビティをクリックし、コンテンツ フレームにそのアクティビティを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="16d7d-115">Click an activity associated with the view to load that activity in the content frame.</span></span>  
  
4.  <span data-ttu-id="16d7d-116">アクティビティの検索を作成するか、既存のアクティビティの検索を開きます。</span><span class="sxs-lookup"><span data-stu-id="16d7d-116">Create an activity search or open an existing activity search.</span></span> <span data-ttu-id="16d7d-117">作成またはアクティビティの検索を開く方法については、次を参照してください。[アクティビティの検索でクエリを作成する方法](../core/how-to-create-a-query-in-activity-search.md)です。</span><span class="sxs-lookup"><span data-stu-id="16d7d-117">For information about creating or opening activity searches, see [How to Create a Query in Activity Search](../core/how-to-create-a-query-in-activity-search.md).</span></span>  
  
5.  <span data-ttu-id="16d7d-118">クリックして、**クエリの実行**ポータルのコンテンツ フレームの上部にあるボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="16d7d-118">Click the **Execute Query** button located at the top of the content frame of the portal.</span></span>  
  
6.  <span data-ttu-id="16d7d-119">クエリの出力を表示するスクロール、**結果** コンテンツ フレームの領域。</span><span class="sxs-lookup"><span data-stu-id="16d7d-119">Scroll down to view the output of the query in the **Results** area of the content frame.</span></span>  
  
## <a name="view-results-information"></a><span data-ttu-id="16d7d-120">結果情報の表示</span><span class="sxs-lookup"><span data-stu-id="16d7d-120">View results information</span></span>  
 <span data-ttu-id="16d7d-121">クエリによって返された項目の詳細なステータス情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="16d7d-121">You can view detailed status for items returned by the query.</span></span> <span data-ttu-id="16d7d-122">次の補足情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="16d7d-122">Additional details that are displayed are:</span></span>  
  
-   <span data-ttu-id="16d7d-123">関連するマイルストーンとデータで構成されるアクティビティ ステータス</span><span class="sxs-lookup"><span data-stu-id="16d7d-123">Activity status, consisting of associated milestones and data</span></span>  
  
-   <span data-ttu-id="16d7d-124">関連ドキュメント</span><span class="sxs-lookup"><span data-stu-id="16d7d-124">Related documents</span></span>  
  
-   <span data-ttu-id="16d7d-125">関連アクティビティ</span><span class="sxs-lookup"><span data-stu-id="16d7d-125">Related activities</span></span>  
  
 <span data-ttu-id="16d7d-126">をクリックして、管理者によるアシスタンスを要求するさらに、**アシスタンス**下のボタン、**関連アクティビティ**コンテンツ フレーム内の領域。</span><span class="sxs-lookup"><span data-stu-id="16d7d-126">In addition, you can request assistance from your administrator by clicking the **Assistance** button below the **Related Activities** area in the content frame.</span></span>  
  
#### <a name="to-view-detailed-status-information-on-results"></a><span data-ttu-id="16d7d-127">結果の詳細なステータス情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="16d7d-127">To view detailed status information on results</span></span>  
  
1.  <span data-ttu-id="16d7d-128">前述の手順に従い、結果を返すクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="16d7d-128">Follow the previous procedure to execute a query to return results.</span></span>  
  
2.  <span data-ttu-id="16d7d-129">行をクリックして、結果項目の詳細なステータス情報を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="16d7d-129">Click a row to load the detailed status information for the result item.</span></span>  
  
3.  <span data-ttu-id="16d7d-130">目的の詳細情報を含んだ領域が折りたたまれている場合は、領域のラベルの横にあるプラス記号 (+) をクリックして、開きます。</span><span class="sxs-lookup"><span data-stu-id="16d7d-130">If the area containing the detailed information you are interested in is collapsed, click the plus sign (+) next to the area label to open it.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="16d7d-131">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="16d7d-131">In This Section</span></span>  
  
-   [<span data-ttu-id="16d7d-132">アクティビティの状態</span><span class="sxs-lookup"><span data-stu-id="16d7d-132">Activity Status</span></span>](../core/activity-status.md)  
  
-   [<span data-ttu-id="16d7d-133">関連ドキュメント</span><span class="sxs-lookup"><span data-stu-id="16d7d-133">Related Documents</span></span>](../core/related-documents.md)  
  
-   [<span data-ttu-id="16d7d-134">関連するアクティビティ</span><span class="sxs-lookup"><span data-stu-id="16d7d-134">Related Activities</span></span>](../core/related-activities.md)  
  
-   [<span data-ttu-id="16d7d-135">アシスタンスを要求します。</span><span class="sxs-lookup"><span data-stu-id="16d7d-135">Request Assistance</span></span>](../core/request-assistance.md)  
  
## <a name="see-also"></a><span data-ttu-id="16d7d-136">参照</span><span class="sxs-lookup"><span data-stu-id="16d7d-136">See Also</span></span>  
 [<span data-ttu-id="16d7d-137">BAM ポータルでのアクティビティの検索</span><span class="sxs-lookup"><span data-stu-id="16d7d-137">Activity Searches in the BAM Portal</span></span>](../core/activity-searches-in-the-bam-portal.md)