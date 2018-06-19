---
title: 結果一覧のサイズを制御する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- results list [Orchestration Debugger], deleting columns
- results list [Orchestration Debugger], limiting list size
- Orchestration Debugger, results list
- results list [Orchestration Designer]
- results list [Orchestration Debugger], adding columns
ms.assetid: 4d41003f-5ea9-4599-8ec0-737c342ffdbd
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80787e4c7dbac57aca9c787943846e924a1a7870
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249738"
---
# <a name="how-to-control-the-size-of-the-results-list"></a><span data-ttu-id="25e5b-102">結果一覧のサイズを制御する方法</span><span class="sxs-lookup"><span data-stu-id="25e5b-102">How to Control the Size of the Results List</span></span>
<span data-ttu-id="25e5b-103">**グループ ハブ**のページ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、クエリの結果ペインには表示するためにスクロールする必要のある情報の非常に多くの列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="25e5b-103">On the **Group Hub** page of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, the Query results pane contains so many columns of information that you need to scroll to view them.</span></span> <span data-ttu-id="25e5b-104">ウィンドウの列を追加または削除して、必要な情報だけを表示できます。</span><span class="sxs-lookup"><span data-stu-id="25e5b-104">You can add or remove columns in the pane to display only the information that you need.</span></span> <span data-ttu-id="25e5b-105">列を追加または削除をクリックして、クエリ結果ペインの任意の部分を右クリックして**列の追加/削除**コンテキスト メニューの します。</span><span class="sxs-lookup"><span data-stu-id="25e5b-105">To add or remove columns, right-click any part of the Query results pane and click **Add/Remove Columns** on the context menu.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="25e5b-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="25e5b-106">Prerequisites</span></span>  
 <span data-ttu-id="25e5b-107">メンバーとしてログオンする必要があります、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループにこの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="25e5b-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to perform this procedure.</span></span>  
  
### <a name="to-add-or-remove-columns-in-the-results-list"></a><span data-ttu-id="25e5b-108">結果一覧の列を追加または削除するには</span><span class="sxs-lookup"><span data-stu-id="25e5b-108">To add or remove columns in the results list</span></span>  
  
1.  <span data-ttu-id="25e5b-109">任意のセルを右クリックし、**クエリの結果**一覧をクリックして**列の追加/削除**コンテキスト メニューの します。</span><span class="sxs-lookup"><span data-stu-id="25e5b-109">Right-click any cell in the **Query results** list, and then click **Add/Remove Columns** on the context menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="25e5b-110">右側にある 結果の一覧に既に存在している項目が表示されます**表示列**です。</span><span class="sxs-lookup"><span data-stu-id="25e5b-110">Items that are already present in the results list appear on the right side under **Displayed Columns**.</span></span> <span data-ttu-id="25e5b-111">下にある左側にあるが、結果一覧に存在しないアイテムが表示されます**使用可能な列**です。</span><span class="sxs-lookup"><span data-stu-id="25e5b-111">Items that are not present in the results list appear on the left side under **Available Columns**.</span></span>  
  
2.  <span data-ttu-id="25e5b-112">列を追加するからの項目のいずれかを選択**使用可能な列** をクリック**追加**その列の一覧に移動する**表示列**です。</span><span class="sxs-lookup"><span data-stu-id="25e5b-112">To add a column, select one of the items from **Available Columns** and click **Add** to move that column to the list of **Displayed Columns**.</span></span>  
  
3.  <span data-ttu-id="25e5b-113">列を削除するからの項目のいずれかを選択**表示列** をクリック**削除**その列の一覧に移動する**使用可能な列**です。</span><span class="sxs-lookup"><span data-stu-id="25e5b-113">To remove a column, select one of the items from **Displayed Columns** and click **Remove** to move that column to the list of **Available Columns**.</span></span>  
  
 <span data-ttu-id="25e5b-114">クエリから返される結果の数は、クエリの作成または実行時に、用意されているフィルターを使用して制御できます。</span><span class="sxs-lookup"><span data-stu-id="25e5b-114">You can control the number of results that the query returns by using the filters that are provided when you create or run a query.</span></span>  
  
## <a name="columns-in-the-query-results-list"></a><span data-ttu-id="25e5b-115">クエリ結果一覧の列</span><span class="sxs-lookup"><span data-stu-id="25e5b-115">Columns in the Query Results List</span></span>  
 <span data-ttu-id="25e5b-116">クエリの結果は、クエリを開始したビューの下部にある [クエリ結果] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="25e5b-116">The query results are displayed in the Query results pane at the bottom of the view that originated the query.</span></span> <span data-ttu-id="25e5b-117">結果一覧に直接アクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="25e5b-117">You cannot directly access the results list.</span></span> <span data-ttu-id="25e5b-118">ショートカット メニューには、現在アクティブなビューで選択されているレコードに対して実行できるすべての操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="25e5b-118">The context menu shows all of the actions you can perform on the selected record within the currently active view.</span></span> <span data-ttu-id="25e5b-119">たとえば、レコードにサービス インスタンス ID が含まれている場合は、サービス関連の操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="25e5b-119">For example, if the record contains a Service Instance ID, then service-related actions appear.</span></span> <span data-ttu-id="25e5b-120">また、メッセージ ID が含まれている場合は、メッセージ関連の操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="25e5b-120">If there is a Message ID, then message-related actions appear.</span></span>  
  
 <span data-ttu-id="25e5b-121">この完全な一覧に含まれている情報がすべて必要であるとは限らないので、表示する列のみを選択したり、削除した列を元に戻したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="25e5b-121">Because you might not need all the information contained in this complete list, you can select only those columns you want to view, or you can replace columns that you removed.</span></span> <span data-ttu-id="25e5b-122">時間によって、結果一覧を並べ替えると、並べ替えると、インスタンス、ミリ秒単位まで場合でも、(ミリ秒) が一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="25e5b-122">When you sort the results list by time, the instances sort up to milliseconds, even if no milliseconds appear on the list.</span></span> <span data-ttu-id="25e5b-123">保存されているクエリを再利用した場合、結果には、クエリを実行するたびに選択した列のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="25e5b-123">When you reuse a saved query the results show only the columns selected each time the query is run.</span></span>  
  
 <span data-ttu-id="25e5b-124">次の表は、結果一覧に表示される項目の完全な一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="25e5b-124">The following table shows a complete list of the items that appear in the results list.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="25e5b-125">**サービスまたはメッセージのフィールド**</span><span class="sxs-lookup"><span data-stu-id="25e5b-125">**Service or Message field**</span></span>|<span data-ttu-id="25e5b-126">**Description**</span><span class="sxs-lookup"><span data-stu-id="25e5b-126">**Description**</span></span>|  
|<span data-ttu-id="25e5b-127">サービス名</span><span class="sxs-lookup"><span data-stu-id="25e5b-127">Service Name</span></span>|<span data-ttu-id="25e5b-128">サービス インスタンスの名前。</span><span class="sxs-lookup"><span data-stu-id="25e5b-128">Name of the service instance.</span></span>|  
|<span data-ttu-id="25e5b-129">[イベントの種類]</span><span class="sxs-lookup"><span data-stu-id="25e5b-129">Event Type</span></span>|<span data-ttu-id="25e5b-130">サービスの種類。たとえば、メッセージング (パイプラインとして報告されます)、オーケストレーション、トランスポート アダプターなどがあります。</span><span class="sxs-lookup"><span data-stu-id="25e5b-130">Type of service (for example, messaging (reported as Pipeline), orchestration, transport adapter).</span></span>|  
|<span data-ttu-id="25e5b-131">[エラーの説明]</span><span class="sxs-lookup"><span data-stu-id="25e5b-131">Error Description</span></span>|<span data-ttu-id="25e5b-132">エラーが発生した場合、その説明。</span><span class="sxs-lookup"><span data-stu-id="25e5b-132">Description of the error if one occurred.</span></span>|  
|<span data-ttu-id="25e5b-133">状態</span><span class="sxs-lookup"><span data-stu-id="25e5b-133">State</span></span>|<span data-ttu-id="25e5b-134">クエリを実行したときの操作の状態。</span><span class="sxs-lookup"><span data-stu-id="25e5b-134">State of the operation when the query was run.</span></span>|  
|<span data-ttu-id="25e5b-135">エラー コード</span><span class="sxs-lookup"><span data-stu-id="25e5b-135">Error Code</span></span>|<span data-ttu-id="25e5b-136">エラーが発生した場合、そのコード。</span><span class="sxs-lookup"><span data-stu-id="25e5b-136">Code of the error if one occurred.</span></span>|  
|<span data-ttu-id="25e5b-137">解読証明書</span><span class="sxs-lookup"><span data-stu-id="25e5b-137">Decryption Certificate</span></span>|<span data-ttu-id="25e5b-138">メッセージまたはサービスに関係する証明書情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="25e5b-138">Shows the certificate information relating to the message or service.</span></span>|  
|<span data-ttu-id="25e5b-139">Duration</span><span class="sxs-lookup"><span data-stu-id="25e5b-139">Duration</span></span>|<span data-ttu-id="25e5b-140">操作が完了するまでの時間。</span><span class="sxs-lookup"><span data-stu-id="25e5b-140">Time for the operation to complete.</span></span>|  
|<span data-ttu-id="25e5b-141">ポート名</span><span class="sxs-lookup"><span data-stu-id="25e5b-141">Port Name</span></span>|<span data-ttu-id="25e5b-142">インスタンスのフローに含まれるポート。</span><span class="sxs-lookup"><span data-stu-id="25e5b-142">Port involved in the flow of the instance.</span></span>|  
|<span data-ttu-id="25e5b-143">署名</span><span class="sxs-lookup"><span data-stu-id="25e5b-143">Signature</span></span>|<span data-ttu-id="25e5b-144">メッセージのデジタル署名情報。</span><span class="sxs-lookup"><span data-stu-id="25e5b-144">Digital signature information of the message.</span></span>|  
|<span data-ttu-id="25e5b-145">サイズ</span><span class="sxs-lookup"><span data-stu-id="25e5b-145">Size</span></span>|<span data-ttu-id="25e5b-146">メッセージのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="25e5b-146">Size of the message in bytes.</span></span>|  
|<span data-ttu-id="25e5b-147">Start Time</span><span class="sxs-lookup"><span data-stu-id="25e5b-147">Start Time</span></span>|<span data-ttu-id="25e5b-148">操作の開始時刻。</span><span class="sxs-lookup"><span data-stu-id="25e5b-148">Time the operation started.</span></span>|  
|<span data-ttu-id="25e5b-149">[終了時刻]</span><span class="sxs-lookup"><span data-stu-id="25e5b-149">End Time</span></span>|<span data-ttu-id="25e5b-150">操作の終了時刻します。</span><span class="sxs-lookup"><span data-stu-id="25e5b-150">Time the operation ended.</span></span>|  
|<span data-ttu-id="25e5b-151">[部分カウント]</span><span class="sxs-lookup"><span data-stu-id="25e5b-151">Part Count</span></span>|<span data-ttu-id="25e5b-152">メッセージ内のパートの数。</span><span class="sxs-lookup"><span data-stu-id="25e5b-152">Number of parts in the message.</span></span>|  
|<span data-ttu-id="25e5b-153">Party</span><span class="sxs-lookup"><span data-stu-id="25e5b-153">Party</span></span>|<span data-ttu-id="25e5b-154">操作を開始したパーティの識別子。</span><span class="sxs-lookup"><span data-stu-id="25e5b-154">Identifier of the party starting the operation.</span></span>|  
|<span data-ttu-id="25e5b-155">[URI]</span><span class="sxs-lookup"><span data-stu-id="25e5b-155">URI</span></span>|<span data-ttu-id="25e5b-156">開始したパーティの URI。</span><span class="sxs-lookup"><span data-stu-id="25e5b-156">URI of the initiating party.</span></span>|  
|<span data-ttu-id="25e5b-157">TimeStamp</span><span class="sxs-lookup"><span data-stu-id="25e5b-157">TimeStamp</span></span>|<span data-ttu-id="25e5b-158">操作の開始時刻。</span><span class="sxs-lookup"><span data-stu-id="25e5b-158">Time the operation started.</span></span>|  
|<span data-ttu-id="25e5b-159">Host</span><span class="sxs-lookup"><span data-stu-id="25e5b-159">Host</span></span>|<span data-ttu-id="25e5b-160">サービス インスタンスを実行している BizTalk ホストの名前。</span><span class="sxs-lookup"><span data-stu-id="25e5b-160">Name of the BizTalk Host running the service instance.</span></span>|  
|<span data-ttu-id="25e5b-161">アセンブリ名</span><span class="sxs-lookup"><span data-stu-id="25e5b-161">Assembly Name</span></span>|<span data-ttu-id="25e5b-162">サービス インスタンスを実装する .NET アセンブリの名前です。</span><span class="sxs-lookup"><span data-stu-id="25e5b-162">Name of the .NET assembly that implements the service instance.</span></span>|  
|<span data-ttu-id="25e5b-163">アセンブリのバージョン</span><span class="sxs-lookup"><span data-stu-id="25e5b-163">Assembly Version</span></span>|<span data-ttu-id="25e5b-164">関連アセンブリのバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="25e5b-164">Version number of the related assembly.</span></span>|  
|<span data-ttu-id="25e5b-165">展開時刻</span><span class="sxs-lookup"><span data-stu-id="25e5b-165">Deployment Time</span></span>|<span data-ttu-id="25e5b-166">サービス インスタンス アセンブリが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に展開された時刻。</span><span class="sxs-lookup"><span data-stu-id="25e5b-166">Time that the service instance assembly deployed into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>|  
|<span data-ttu-id="25e5b-167">アクティビティ ID</span><span class="sxs-lookup"><span data-stu-id="25e5b-167">Activity ID</span></span>|<span data-ttu-id="25e5b-168">一意のサービス インスタンスのアクティビティ (たとえば、同じ ID を持つパイプラインとオーケストレーションによって送信または受信されたメッセージ) を識別します。</span><span class="sxs-lookup"><span data-stu-id="25e5b-168">Identifies unique service instance activity (for example, messages sent/received by the pipeline/orchestration have the same ID).</span></span>|  
|<span data-ttu-id="25e5b-169">[サービス インスタンス ID]</span><span class="sxs-lookup"><span data-stu-id="25e5b-169">Service Instance ID</span></span>|<span data-ttu-id="25e5b-170">グローバル一意識別子 (GUID) をサービス インスタンスの実行を識別します。</span><span class="sxs-lookup"><span data-stu-id="25e5b-170">Globally unique identifier (GUID) that identifies a run of a service instance.</span></span>|  
|<span data-ttu-id="25e5b-171">メッセージ インスタンス ID</span><span class="sxs-lookup"><span data-stu-id="25e5b-171">Message Instance ID</span></span>|<span data-ttu-id="25e5b-172">メッセージ インスタンスを識別するグローバル一意識別子 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="25e5b-172">Globally unique identifier (GUID) that identifies a message instance.</span></span>|  
|<span data-ttu-id="25e5b-173">サービス ID</span><span class="sxs-lookup"><span data-stu-id="25e5b-173">Service ID</span></span>|<span data-ttu-id="25e5b-174">サービスを識別するグローバル一意識別子 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="25e5b-174">Globally unique identifier (GUID) that identifies a service.</span></span>|  
|<span data-ttu-id="25e5b-175">[サービス クラス]</span><span class="sxs-lookup"><span data-stu-id="25e5b-175">Service Class</span></span>|<span data-ttu-id="25e5b-176">クラスの種類 (パイプラインまたはオーケストレーション)。</span><span class="sxs-lookup"><span data-stu-id="25e5b-176">Type of class (pipeline or orchestration).</span></span>|  
|<span data-ttu-id="25e5b-177">サービス クラス ID</span><span class="sxs-lookup"><span data-stu-id="25e5b-177">Service Class ID</span></span>|<span data-ttu-id="25e5b-178">サービス (オーケストレーションなど) を識別する、サービスに依存しない GUID。</span><span class="sxs-lookup"><span data-stu-id="25e5b-178">A service-independent GUID that identifies a service (for example, orchestration).</span></span>|  
|<span data-ttu-id="25e5b-179">アイコン</span><span class="sxs-lookup"><span data-stu-id="25e5b-179">Icon</span></span>|<span data-ttu-id="25e5b-180">結果行のアイコン。</span><span class="sxs-lookup"><span data-stu-id="25e5b-180">Icon of the result row.</span></span>|  
|<span data-ttu-id="25e5b-181">[アダプター]</span><span class="sxs-lookup"><span data-stu-id="25e5b-181">Adapter</span></span>|<span data-ttu-id="25e5b-182">操作で使用されたアダプター。</span><span class="sxs-lookup"><span data-stu-id="25e5b-182">Adapter used in the operation.</span></span>|