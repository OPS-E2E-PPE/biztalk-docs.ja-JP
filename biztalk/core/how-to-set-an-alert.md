---
title: 警告を設定する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- alerts, creating
- Query Builder [BAM portal], creating alerts
- queries [BAM], aggregations
- Query Builder [BAM portal], activity searches
- Query Builder [BAM portal], aggregation alerts
- queries [BAM], alerts
- aggregations, alerts
ms.assetid: 8745d2c6-5bc0-4d7a-8c17-361535f5c6e6
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 774fbab86c1da1389b813f621c89f38cf0aa7656
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255706"
---
# <a name="how-to-set-an-alert"></a><span data-ttu-id="88b30-102">警告を設定する方法</span><span class="sxs-lookup"><span data-stu-id="88b30-102">How to Set an Alert</span></span>
<span data-ttu-id="88b30-103">警告を設定するには、その警告をアクティビティの検索に接続するか、集計をドリル ダウンします。</span><span class="sxs-lookup"><span data-stu-id="88b30-103">You can set an alert by attaching it to an activity search or drilling down through an aggregation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88b30-104">クエリに警告を設定する前に、そのクエリを実行して、監視する処理にとって警告サイクルの期間が適切かどうかを評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88b30-104">Before setting an alert on a query, you should run the query and evaluate whether the alert cycle durations are appropriate for the process you are monitoring.</span></span> <span data-ttu-id="88b30-105">サイクルの期間が短すぎると、設定途中に警告条件に達し、警告システムで見落とされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="88b30-105">If the cycle duration is too short, it is possible for an alert condition to occur in a transient manner and thus be missed by the alerting system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88b30-106">手順の途中で戻るボタンをクリックすると、"警告: ページの有効期限切れ" というエラー メッセージが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="88b30-106">If you click the back button during these procedures, you may receive the following message: "Warning: page has expired."</span></span> <span data-ttu-id="88b30-107">以前の内容に戻るには、F5 キーを押します</span><span class="sxs-lookup"><span data-stu-id="88b30-107">To return to the previous content, press F5.</span></span> <span data-ttu-id="88b30-108">(F5 キーを複数回押すことが必要になる場合もあります)。</span><span class="sxs-lookup"><span data-stu-id="88b30-108">(You may have to press F5 several times.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88b30-109">ビューで最初の警告を作成するときは、警告にはデータは表示されません。</span><span class="sxs-lookup"><span data-stu-id="88b30-109">When you create the first alert on a view, there will be no data displayed for the alert.</span></span> <span data-ttu-id="88b30-110">警告を定義しても、警告を作成した時点以前の期間から警告データが収集されることはありません。</span><span class="sxs-lookup"><span data-stu-id="88b30-110">Defining an alert does not collect alert data from the time frame before the alert was created.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="88b30-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="88b30-111">Prerequisites</span></span>  
 <span data-ttu-id="88b30-112">このトピックの手順を実行するための前提条件は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="88b30-112">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
-   <span data-ttu-id="88b30-113">展開済みのビューが必要です。</span><span class="sxs-lookup"><span data-stu-id="88b30-113">You must have a deployed view.</span></span>  
  
-   <span data-ttu-id="88b30-114">インスタンス警告には、アクティビティの検索が必要です。</span><span class="sxs-lookup"><span data-stu-id="88b30-114">You must have an activity search for an instance alert.</span></span>  
  
-   <span data-ttu-id="88b30-115">集計警告には、集計データが設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="88b30-115">You must have a populated aggregation for an aggregation alert.</span></span>  
  
### <a name="to-set-an-alert-on-an-activity-search"></a><span data-ttu-id="88b30-116">アクティビティの検索に警告を設定するには</span><span class="sxs-lookup"><span data-stu-id="88b30-116">To set an alert on an activity search</span></span>  
  
1.  <span data-ttu-id="88b30-117">**マイ ビュー**フレームでビューのタスクの一覧を展開するためのビューをクリックします。</span><span class="sxs-lookup"><span data-stu-id="88b30-117">In the **My Views** frame, click a view to expand the list of tasks for the view.</span></span>  
  
2.  <span data-ttu-id="88b30-118">クリックして、**アクティビティの検索**展開したビューの下のタスクです。</span><span class="sxs-lookup"><span data-stu-id="88b30-118">Click the **Activity Search** task under the view you expanded.</span></span>  
  
3.  <span data-ttu-id="88b30-119">アクティビティの検索を作成します。または、アクティビティの検索を開きます。</span><span class="sxs-lookup"><span data-stu-id="88b30-119">Create or open an activity search.</span></span> <span data-ttu-id="88b30-120">これを行う方法については、次を参照してください。[アクティビティの検索でクエリを作成する方法](../core/how-to-create-a-query-in-activity-search.md)です。</span><span class="sxs-lookup"><span data-stu-id="88b30-120">For information about how to do this, see [How to Create a Query in Activity Search](../core/how-to-create-a-query-in-activity-search.md).</span></span>  
  
4.  <span data-ttu-id="88b30-121">BAM ポータルのコンテンツ フレームをクリックして、**警告の設定**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="88b30-121">In the content frame of the BAM portal, click the **Set Alert** button.</span></span> <span data-ttu-id="88b30-122">コンテンツ フレームによって、警告作成テンプレートが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="88b30-122">The content frame will load with the alert creation template.</span></span>  
  
5.  <span data-ttu-id="88b30-123">**名前**テキスト ボックスに、アラートのわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="88b30-123">In the **Name** text box, type a descriptive name for the alert.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="88b30-124">名は 100 文字を上限と、次の文字を含めることはできません: ~! @# $% ^&amp;\* (); 名前に次の文字を入力する場合、操作を完了するには修正する必要がありますあるエラーを示すテキスト フィールドの周囲に赤い点線の枠が表示されます。</span><span class="sxs-lookup"><span data-stu-id="88b30-124">Names are limited to 100 characters and cannot contain the following characters: ~!@#$%^&amp;\*();  If you enter any of these characters in a name, a dashed red border appears around the text field indicating an error that you must correct to complete the action.</span></span>  
  
6.  <span data-ttu-id="88b30-125">警告をこの時点で有効にしたくない場合はオフ、**アラートが有効になっている**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="88b30-125">If you do not want the alert enabled at this time, clear the **Alert Enabled** check box.</span></span>  
  
7.  <span data-ttu-id="88b30-126">**メッセージ**テキスト ボックスに、アラートがトリガーされたときに配信されたメッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="88b30-126">In the **Message** text box, type the message that is delivered when the alert is triggered.</span></span>  
  
8.  <span data-ttu-id="88b30-127">**優先度**ドロップダウン リストで、このアラートの優先度レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="88b30-127">From the **Priority** drop-down list, choose the priority level for this alert.</span></span> <span data-ttu-id="88b30-128">優先度の設定は、警告が設定された問題の重要度を示します。</span><span class="sxs-lookup"><span data-stu-id="88b30-128">The priority setting indicates the severity of the issue on which the alert was set.</span></span>  
  
9. <span data-ttu-id="88b30-129">**所有者**テキスト ボックスに、この警告の所有者のエイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="88b30-129">In the **Owners** text box, type the aliases of the owners of this alert.</span></span> <span data-ttu-id="88b30-130">複数のユーザー名を入力する場合は、ユーザー名の間にセミコロンを使用します。</span><span class="sxs-lookup"><span data-stu-id="88b30-130">Use semicolons between the names of multiple users.</span></span>  
  
10. <span data-ttu-id="88b30-131">**警告セキュリティ**領域で、この警告を参照し、サブスクライブできるようにするには、他のユーザーのためのチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="88b30-131">In the **Alert Security** area, select the check box to allow other users to see this alert and subscribe to it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="88b30-132">警告セキュリティは、プライベートとパブリック間をいつでも切り替えることができます。警告のサブスクライバーが存在しても、この操作に影響はありません。</span><span class="sxs-lookup"><span data-stu-id="88b30-132">You can switch the alert security between private and public at any time; the presence of subscribers to the alert does not affect this action.</span></span> <span data-ttu-id="88b30-133">ただし、警告セキュリティをパブリックからプライベートに切り替えるときは、警告のサブスクライバーが存在するかどうかを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88b30-133">When you switch the alert security from public to private, however, you should consider whether there are any subscribers to the alert.</span></span> <span data-ttu-id="88b30-134">警告のサブスクライバーが存在する場合に、警告がプライベートに切り替えられると、サブスクリプションを編集できなくなります。</span><span class="sxs-lookup"><span data-stu-id="88b30-134">If there are subscribers to the alert, they will have no way to edit their subscription when the alert is made private.</span></span>  
  
11. <span data-ttu-id="88b30-135">右上隅で、**アラートの詳細**領域で、をクリックして、**警告の保存**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="88b30-135">In the upper-right corner of the **Alert Details** area, click the **Save Alert** button.</span></span>  
  
### <a name="to-set-an-alert-on-an-aggregation"></a><span data-ttu-id="88b30-136">集計に警告を設定するには</span><span class="sxs-lookup"><span data-stu-id="88b30-136">To set an alert on an aggregation</span></span>  
  
1.  <span data-ttu-id="88b30-137">**マイ ビュー**フレームでビューのタスクの一覧を展開するためのビューをクリックします。</span><span class="sxs-lookup"><span data-stu-id="88b30-137">In the **My Views** frame, click a view to expand the list of tasks for the view.</span></span>  
  
2.  <span data-ttu-id="88b30-138">クリックして、**集計**内のタスク**マイ ビュー**展開したビューの下。</span><span class="sxs-lookup"><span data-stu-id="88b30-138">Click the **Aggregations** task in **My Views** under the view you expanded.</span></span>  
  
3.  <span data-ttu-id="88b30-139">BAM ポータルのコンテンツ フレームで、ピボットテーブル レポートの集計列のセルを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="88b30-139">In the content frame of the BAM portal, right-click a cell in the totals column of the PivotTable report.</span></span> <span data-ttu-id="88b30-140">これにより、集計を実行できる関数を備えたショートカット メニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="88b30-140">This opens a context menu with functions that are available to perform on the aggregation total.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="88b30-141">集計の特定のコンポーネントに警告を設定するには、その行項目を展開します。</span><span class="sxs-lookup"><span data-stu-id="88b30-141">You can set an alert on a specific component of the aggregation total by expanding that line item.</span></span> <span data-ttu-id="88b30-142">警告を設定するレベルに到達するまで、この方法で後続のレベルを展開できます。</span><span class="sxs-lookup"><span data-stu-id="88b30-142">You can expand succeeding levels in this manner until you reach the level at which you want to set your alert.</span></span>  
  
4.  <span data-ttu-id="88b30-143">コンテキスト メニューの上部には、をクリックして**警告の作成**です。</span><span class="sxs-lookup"><span data-stu-id="88b30-143">At the top of the context menu, click **Create Alert**.</span></span> <span data-ttu-id="88b30-144">コンテンツ フレームによって、警告作成テンプレートが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="88b30-144">The content frame will load with the alert creation template.</span></span>  
  
5.  <span data-ttu-id="88b30-145">**名前**テキスト ボックスに、アラートのわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="88b30-145">In the **Name** text box, type a descriptive name for the alert.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="88b30-146">名は 100 文字を上限と、次の文字を含めることはできません: ~! @# $% ^&amp;\* (); 名前に次の文字を入力する場合、操作を完了するには修正する必要がありますあるエラーを示すテキスト フィールドの周囲に赤い点線の枠が表示されます。</span><span class="sxs-lookup"><span data-stu-id="88b30-146">Names are limited to 100 characters and cannot contain the following characters: ~!@#$%^&amp;\*();  If you enter any of these characters in a name, a dashed red border appears around the text field indicating an error that you must correct to complete the action.</span></span>  
  
6.  <span data-ttu-id="88b30-147">警告をこの時点で有効にしたくない場合はオフ、**アラートが有効になっている**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="88b30-147">If you do not want the alert enabled at this time, clear the **Alert Enabled** check box.</span></span>  
  
7.  <span data-ttu-id="88b30-148">**メッセージ**テキスト ボックスに、アラートがトリガーされたときに配信されたメッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="88b30-148">In the **Message** text box, type the message that is delivered when the alert is triggered.</span></span>  
  
8.  <span data-ttu-id="88b30-149">**優先度**ドロップダウン リストで、このアラートの優先度レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="88b30-149">From the **Priority** drop-down list, choose the priority level for this alert.</span></span> <span data-ttu-id="88b30-150">優先度の設定は、警告が設定された問題の重要度を示します。</span><span class="sxs-lookup"><span data-stu-id="88b30-150">The priority setting indicates the severity of the issue on which the alert was set.</span></span>  
  
9. <span data-ttu-id="88b30-151">**所有者**テキスト ボックスに、この警告の所有者のエイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="88b30-151">In the **Owners** text box, type the aliases of the owners of this alert.</span></span> <span data-ttu-id="88b30-152">複数のユーザー名を入力する場合は、ユーザー名の間にセミコロンを使用します。</span><span class="sxs-lookup"><span data-stu-id="88b30-152">Use semicolons between the names of multiple users.</span></span>  
  
10. <span data-ttu-id="88b30-153">**しきい値**領域から、比較の条件を選択、**カウント**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="88b30-153">In the **Threshold** area, select a comparison condition from the **Count** drop-down list.</span></span>  
  
11. <span data-ttu-id="88b30-154">**期間**テキスト ボックスで、しきい値を測定する時間単位の数を入力します。</span><span class="sxs-lookup"><span data-stu-id="88b30-154">In the **Duration** text box, enter the number of time units across which the threshold is measured.</span></span>  
  
12. <span data-ttu-id="88b30-155">**期間**ドロップダウン リストで、時間の単位を選択します。</span><span class="sxs-lookup"><span data-stu-id="88b30-155">From the **Duration** drop-down list, select the unit of time.</span></span>  
  
13. <span data-ttu-id="88b30-156">**警告セキュリティ**領域で、この警告を参照し、サブスクライブできるようにするには、他のユーザーのためのチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="88b30-156">In the **Alert Security** area, select the check box to allow other users to see this alert and subscribe to it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="88b30-157">警告セキュリティは、プライベートとパブリック間をいつでも切り替えることができます。警告のサブスクライバーが存在しても、この操作に影響はありません。</span><span class="sxs-lookup"><span data-stu-id="88b30-157">You can switch the alert security between private and public at any time; the presence of subscribers to the alert does not affect this action.</span></span> <span data-ttu-id="88b30-158">ただし、警告セキュリティをパブリックからプライベートに切り替えるときは、警告のサブスクライバーが存在するかどうかを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88b30-158">When you switch the alert security from public to private, however, you should consider whether there are any subscribers to the alert.</span></span> <span data-ttu-id="88b30-159">警告のサブスクライバーが存在する場合に、警告がプライベートに切り替えられると、サブスクリプションを編集できなくなります。</span><span class="sxs-lookup"><span data-stu-id="88b30-159">If there are subscribers to the alert, they will have no way to edit their subscription when the alert is made private.</span></span>  
  
14. <span data-ttu-id="88b30-160">右上隅で、**アラートの詳細**領域で、をクリックして、**警告の保存**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="88b30-160">In the upper-right corner of the **Alert Details** area, click the **Save Alert** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88b30-161">参照</span><span class="sxs-lookup"><span data-stu-id="88b30-161">See Also</span></span>  
 [<span data-ttu-id="88b30-162">アクティビティの検索でクエリを作成する方法</span><span class="sxs-lookup"><span data-stu-id="88b30-162">How to Create a Query in Activity Search</span></span>](../core/how-to-create-a-query-in-activity-search.md)