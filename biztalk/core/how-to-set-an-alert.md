---
title: アラートを設定する方法 |Microsoft Docs
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
ms.openlocfilehash: 116f8ac2a2fd79efec82449339732cde90a547db
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334642"
---
# <a name="how-to-set-an-alert"></a><span data-ttu-id="50f60-102">アラートを設定する方法</span><span class="sxs-lookup"><span data-stu-id="50f60-102">How to Set an Alert</span></span>
<span data-ttu-id="50f60-103">アクティビティの検索にアタッチまたは集計をドリル ダウンして警告を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="50f60-103">You can set an alert by attaching it to an activity search or drilling down through an aggregation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50f60-104">クエリにアラートを設定する前に、クエリを実行し、警告サイクルの期間を監視しているプロセスの適切なかどうかを評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50f60-104">Before setting an alert on a query, you should run the query and evaluate whether the alert cycle durations are appropriate for the process you are monitoring.</span></span> <span data-ttu-id="50f60-105">サイクルの期間が短すぎる場合は、一時的な方法で発生し、そのため、アラート発信システムで見落とされるアラートの条件のことは。</span><span class="sxs-lookup"><span data-stu-id="50f60-105">If the cycle duration is too short, it is possible for an alert condition to occur in a transient manner and thus be missed by the alerting system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50f60-106">これらの手順で、[戻る] ボタンをクリックした場合、次のメッセージが表示される可能性があります。"警告: ページの有効期限が切れています"。</span><span class="sxs-lookup"><span data-stu-id="50f60-106">If you click the back button during these procedures, you may receive the following message: "Warning: page has expired."</span></span> <span data-ttu-id="50f60-107">前のコンテンツに戻り、f5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="50f60-107">To return to the previous content, press F5.</span></span> <span data-ttu-id="50f60-108">(何度も f5 キーを押す必要があります)。</span><span class="sxs-lookup"><span data-stu-id="50f60-108">(You may have to press F5 several times.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50f60-109">ビューの最初のアラートを作成するときに、データ警告の表示されません。</span><span class="sxs-lookup"><span data-stu-id="50f60-109">When you create the first alert on a view, there will be no data displayed for the alert.</span></span> <span data-ttu-id="50f60-110">アラートを定義するデータが収集されないアラート期間から、アラートが作成される前にします。</span><span class="sxs-lookup"><span data-stu-id="50f60-110">Defining an alert does not collect alert data from the time frame before the alert was created.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="50f60-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="50f60-111">Prerequisites</span></span>  
 <span data-ttu-id="50f60-112">このトピックの手順を実行するための前提条件は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="50f60-112">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
-   <span data-ttu-id="50f60-113">展開済みのビューが必要です。</span><span class="sxs-lookup"><span data-stu-id="50f60-113">You must have a deployed view.</span></span>  
  
-   <span data-ttu-id="50f60-114">インスタンス警告には、アクティビティの検索が必要です。</span><span class="sxs-lookup"><span data-stu-id="50f60-114">You must have an activity search for an instance alert.</span></span>  
  
-   <span data-ttu-id="50f60-115">集計警告のデータが設定された集計が必要です。</span><span class="sxs-lookup"><span data-stu-id="50f60-115">You must have a populated aggregation for an aggregation alert.</span></span>  
  
### <a name="to-set-an-alert-on-an-activity-search"></a><span data-ttu-id="50f60-116">アクティビティの検索でアラートを設定するには</span><span class="sxs-lookup"><span data-stu-id="50f60-116">To set an alert on an activity search</span></span>  
  
1.  <span data-ttu-id="50f60-117">**マイ ビュー**フレームで、ビューのタスクの一覧を展開するためのビューをクリックします。</span><span class="sxs-lookup"><span data-stu-id="50f60-117">In the **My Views** frame, click a view to expand the list of tasks for the view.</span></span>  
  
2.  <span data-ttu-id="50f60-118">をクリックして、**アクティビティの検索**展開したビューで作業します。</span><span class="sxs-lookup"><span data-stu-id="50f60-118">Click the **Activity Search** task under the view you expanded.</span></span>  
  
3.  <span data-ttu-id="50f60-119">作成するか、アクティビティの検索を開きます。</span><span class="sxs-lookup"><span data-stu-id="50f60-119">Create or open an activity search.</span></span> <span data-ttu-id="50f60-120">これを行う方法については、次を参照してください。[アクティビティの検索でクエリを作成する方法](../core/how-to-create-a-query-in-activity-search.md)します。</span><span class="sxs-lookup"><span data-stu-id="50f60-120">For information about how to do this, see [How to Create a Query in Activity Search](../core/how-to-create-a-query-in-activity-search.md).</span></span>  
  
4.  <span data-ttu-id="50f60-121">BAM ポータルのコンテンツのフレームで、**警告の設定**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="50f60-121">In the content frame of the BAM portal, click the **Set Alert** button.</span></span> <span data-ttu-id="50f60-122">コンテンツ フレーム、警告作成テンプレートが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="50f60-122">The content frame will load with the alert creation template.</span></span>  
  
5.  <span data-ttu-id="50f60-123">**名前**テキスト ボックスに、アラートのわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="50f60-123">In the **Name** text box, type a descriptive name for the alert.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="50f60-124">名前は 100 文字に制限と、次の文字を含めることはできません: ~! @# $% ^&amp;\* (); これらの文字を名前で入力すると、エラーを修正して、操作を完了することを示すテキスト フィールドの周囲赤い点線の枠が表示されます。</span><span class="sxs-lookup"><span data-stu-id="50f60-124">Names are limited to 100 characters and cannot contain the following characters: ~!@#$%^&amp;\*();  If you enter any of these characters in a name, a dashed red border appears around the text field indicating an error that you must correct to complete the action.</span></span>  
  
6.  <span data-ttu-id="50f60-125">警告をこの時点で有効にしたくない場合はオフ、**アラートが有効になっている**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="50f60-125">If you do not want the alert enabled at this time, clear the **Alert Enabled** check box.</span></span>  
  
7.  <span data-ttu-id="50f60-126">**メッセージ**テキスト ボックスに、アラートがトリガーされたときに配信されたメッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="50f60-126">In the **Message** text box, type the message that is delivered when the alert is triggered.</span></span>  
  
8.  <span data-ttu-id="50f60-127">**優先度**ドロップダウン リストで、このアラートの優先度レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="50f60-127">From the **Priority** drop-down list, choose the priority level for this alert.</span></span> <span data-ttu-id="50f60-128">優先順位の設定では、アラートが設定されている問題の重大度を示します。</span><span class="sxs-lookup"><span data-stu-id="50f60-128">The priority setting indicates the severity of the issue on which the alert was set.</span></span>  
  
9. <span data-ttu-id="50f60-129">**所有者**テキスト ボックスに、このアラートの所有者のエイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="50f60-129">In the **Owners** text box, type the aliases of the owners of this alert.</span></span> <span data-ttu-id="50f60-130">複数のユーザーの名の間のセミコロンを使用します。</span><span class="sxs-lookup"><span data-stu-id="50f60-130">Use semicolons between the names of multiple users.</span></span>  
  
10. <span data-ttu-id="50f60-131">**警告セキュリティ**領域で、この警告を参照し、サブスクライブするには、他のユーザーを許可するチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="50f60-131">In the **Alert Security** area, select the check box to allow other users to see this alert and subscribe to it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="50f60-132">いつでも警告セキュリティは、プライベートとパブリック間を切り替えることができます。警告のサブスクライバーの存在は、この操作には影響しません。</span><span class="sxs-lookup"><span data-stu-id="50f60-132">You can switch the alert security between private and public at any time; the presence of subscribers to the alert does not affect this action.</span></span> <span data-ttu-id="50f60-133">ただし、プライベートからパブリック警告セキュリティを切り替えると、警告にサブスクライバーが存在するかどうかを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50f60-133">When you switch the alert security from public to private, however, you should consider whether there are any subscribers to the alert.</span></span> <span data-ttu-id="50f60-134">警告のサブスクライバーがある場合、方法はありません、アラートがプライベートに行われたときに、サブスクリプションを編集します。</span><span class="sxs-lookup"><span data-stu-id="50f60-134">If there are subscribers to the alert, they will have no way to edit their subscription when the alert is made private.</span></span>  
  
11. <span data-ttu-id="50f60-135">右上隅にある、**アラートの詳細**領域で、をクリックして、**警告の保存**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="50f60-135">In the upper-right corner of the **Alert Details** area, click the **Save Alert** button.</span></span>  
  
### <a name="to-set-an-alert-on-an-aggregation"></a><span data-ttu-id="50f60-136">集計の警告を設定するには</span><span class="sxs-lookup"><span data-stu-id="50f60-136">To set an alert on an aggregation</span></span>  
  
1.  <span data-ttu-id="50f60-137">**マイ ビュー**フレームで、ビューのタスクの一覧を展開するためのビューをクリックします。</span><span class="sxs-lookup"><span data-stu-id="50f60-137">In the **My Views** frame, click a view to expand the list of tasks for the view.</span></span>  
  
2.  <span data-ttu-id="50f60-138">をクリックして、**集計**でタスク**マイ ビュー**展開したビューの下。</span><span class="sxs-lookup"><span data-stu-id="50f60-138">Click the **Aggregations** task in **My Views** under the view you expanded.</span></span>  
  
3.  <span data-ttu-id="50f60-139">BAM ポータルのコンテンツのフレームには、ピボット テーブル レポートの合計列のセルを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="50f60-139">In the content frame of the BAM portal, right-click a cell in the totals column of the PivotTable report.</span></span> <span data-ttu-id="50f60-140">関数、集計を実行するにを使用したコンテキスト メニューが開きます。</span><span class="sxs-lookup"><span data-stu-id="50f60-140">This opens a context menu with functions that are available to perform on the aggregation total.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="50f60-141">できる警告を設定する集計の特定のコンポーネントに合計をその行項目を展開します。</span><span class="sxs-lookup"><span data-stu-id="50f60-141">You can set an alert on a specific component of the aggregation total by expanding that line item.</span></span> <span data-ttu-id="50f60-142">警告を設定するレベルに到達するまでは、この方法で後続のレベルを展開できます。</span><span class="sxs-lookup"><span data-stu-id="50f60-142">You can expand succeeding levels in this manner until you reach the level at which you want to set your alert.</span></span>  
  
4.  <span data-ttu-id="50f60-143">コンテキスト メニューの上部にある次のようにクリックします。**アラートの作成**です。</span><span class="sxs-lookup"><span data-stu-id="50f60-143">At the top of the context menu, click **Create Alert**.</span></span> <span data-ttu-id="50f60-144">コンテンツ フレーム、警告作成テンプレートが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="50f60-144">The content frame will load with the alert creation template.</span></span>  
  
5.  <span data-ttu-id="50f60-145">**名前**テキスト ボックスに、アラートのわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="50f60-145">In the **Name** text box, type a descriptive name for the alert.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="50f60-146">名前は 100 文字に制限と、次の文字を含めることはできません: ~! @# $% ^&amp;\* (); これらの文字を名前で入力すると、エラーを修正して、操作を完了することを示すテキスト フィールドの周囲赤い点線の枠が表示されます。</span><span class="sxs-lookup"><span data-stu-id="50f60-146">Names are limited to 100 characters and cannot contain the following characters: ~!@#$%^&amp;\*();  If you enter any of these characters in a name, a dashed red border appears around the text field indicating an error that you must correct to complete the action.</span></span>  
  
6.  <span data-ttu-id="50f60-147">警告をこの時点で有効にしたくない場合はオフ、**アラートが有効になっている**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="50f60-147">If you do not want the alert enabled at this time, clear the **Alert Enabled** check box.</span></span>  
  
7.  <span data-ttu-id="50f60-148">**メッセージ**テキスト ボックスに、アラートがトリガーされたときに配信されたメッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="50f60-148">In the **Message** text box, type the message that is delivered when the alert is triggered.</span></span>  
  
8.  <span data-ttu-id="50f60-149">**優先度**ドロップダウン リストで、このアラートの優先度レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="50f60-149">From the **Priority** drop-down list, choose the priority level for this alert.</span></span> <span data-ttu-id="50f60-150">優先順位の設定では、アラートが設定されている問題の重大度を示します。</span><span class="sxs-lookup"><span data-stu-id="50f60-150">The priority setting indicates the severity of the issue on which the alert was set.</span></span>  
  
9. <span data-ttu-id="50f60-151">**所有者**テキスト ボックスに、このアラートの所有者のエイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="50f60-151">In the **Owners** text box, type the aliases of the owners of this alert.</span></span> <span data-ttu-id="50f60-152">複数のユーザーの名の間のセミコロンを使用します。</span><span class="sxs-lookup"><span data-stu-id="50f60-152">Use semicolons between the names of multiple users.</span></span>  
  
10. <span data-ttu-id="50f60-153">**しきい値**領域から、比較の条件を選択、**カウント**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="50f60-153">In the **Threshold** area, select a comparison condition from the **Count** drop-down list.</span></span>  
  
11. <span data-ttu-id="50f60-154">**期間**テキスト ボックスに、しきい値を測定する時間単位の数を入力します。</span><span class="sxs-lookup"><span data-stu-id="50f60-154">In the **Duration** text box, enter the number of time units across which the threshold is measured.</span></span>  
  
12. <span data-ttu-id="50f60-155">**期間**ドロップダウン リストで、時間の単位を選択します。</span><span class="sxs-lookup"><span data-stu-id="50f60-155">From the **Duration** drop-down list, select the unit of time.</span></span>  
  
13. <span data-ttu-id="50f60-156">**警告セキュリティ**領域で、この警告を参照し、サブスクライブするには、他のユーザーを許可するチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="50f60-156">In the **Alert Security** area, select the check box to allow other users to see this alert and subscribe to it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="50f60-157">いつでも警告セキュリティは、プライベートとパブリック間を切り替えることができます。警告のサブスクライバーの存在は、この操作には影響しません。</span><span class="sxs-lookup"><span data-stu-id="50f60-157">You can switch the alert security between private and public at any time; the presence of subscribers to the alert does not affect this action.</span></span> <span data-ttu-id="50f60-158">ただし、プライベートからパブリック警告セキュリティを切り替えると、警告にサブスクライバーが存在するかどうかを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50f60-158">When you switch the alert security from public to private, however, you should consider whether there are any subscribers to the alert.</span></span> <span data-ttu-id="50f60-159">警告のサブスクライバーがある場合、方法はありません、アラートがプライベートに行われたときに、サブスクリプションを編集します。</span><span class="sxs-lookup"><span data-stu-id="50f60-159">If there are subscribers to the alert, they will have no way to edit their subscription when the alert is made private.</span></span>  
  
14. <span data-ttu-id="50f60-160">右上隅にある、**アラートの詳細**領域で、をクリックして、**警告の保存**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="50f60-160">In the upper-right corner of the **Alert Details** area, click the **Save Alert** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50f60-161">参照</span><span class="sxs-lookup"><span data-stu-id="50f60-161">See Also</span></span>  
 [<span data-ttu-id="50f60-162">アクティビティの検索でクエリを作成する方法</span><span class="sxs-lookup"><span data-stu-id="50f60-162">How to Create a Query in Activity Search</span></span>](../core/how-to-create-a-query-in-activity-search.md)