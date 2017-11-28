---
title: "中断されたサービス インスタンスを検索する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service instances, viewing
- service instances, Query tab [Administration Console]
- Query tab [Administration Console], service instances
- service instances, suspended
- Query tab [Administration Console], searching
- instances, suspended
- instances, services
ms.assetid: f91b1151-d879-4aa7-afc8-4cf13d928158
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52c0d3ad192ad2cc8f4429f78cfa38ddc97ac837
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-search-for-suspended-service-instances"></a><span data-ttu-id="34388-102">中断されたサービス インスタンスを検索する方法</span><span class="sxs-lookup"><span data-stu-id="34388-102">How to Search for Suspended Service Instances</span></span>
<span data-ttu-id="34388-103">使用することができます、**クエリ** タブで、BizTalk Server 管理コンソールの中断されたサービス インスタンスを検索します。</span><span class="sxs-lookup"><span data-stu-id="34388-103">You can use the **Query** tab in the BizTalk Server Administration Console to search for suspended service instances.</span></span> <span data-ttu-id="34388-104">メッセージの特定のサブセットを検索して、サービス名、種類、ホストなどに関連付けられた特定のメッセージを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="34388-104">You can search for a specific subset of messages to locate a specific message associated with a service name, type, host, etc.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34388-105">終了 (メッセージ未消費) インスタンスは、該当する中断されたサービス インスタンスにエラー コード ("終了 (メッセージ未消費)") として表示されます。</span><span class="sxs-lookup"><span data-stu-id="34388-105">Terminated w/ unconsumed message instances are displayed as an error code (“Terminated with unconsumed messages”) for the pertinent suspended service instances.</span></span> <span data-ttu-id="34388-106">これらのインスタンスは再開できません。</span><span class="sxs-lookup"><span data-stu-id="34388-106">These instances are non-resumable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34388-107">URI またはエラー アダプター名によるグループ化とフィルター選択を行うと、検索結果には送信ポートと受信ポートのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="34388-107">When Grouping and Filtering by URI or error adapter name, only send and receive ports are displayed in the results.</span></span> <span data-ttu-id="34388-108">URI によるグループ化とフィルター選択はオーケストレーションには使用できないので、表示される結果にオーケストレーションは含まれません。</span><span class="sxs-lookup"><span data-stu-id="34388-108">Grouping and Filtering by URI is not possible for orchestrations, which are not included in the displayed results.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="34388-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="34388-109">Prerequisites</span></span>  
 <span data-ttu-id="34388-110">ここで示す手順を実行するには、BizTalk Server Operators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="34388-110">To perform this procedure, you must be logged on as a member of the BizTalk Server Operators group.</span></span>  
  
### <a name="to-search-for-suspended-service-instances"></a><span data-ttu-id="34388-111">中断されたサービス インスタンスを検索するには</span><span class="sxs-lookup"><span data-stu-id="34388-111">To search for suspended service instances</span></span>  
  
1.  <span data-ttu-id="34388-112">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="34388-112">Click **Start**, click **All Programs**, click **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="34388-113">コンソール ツリーで  **BizTalk Server 管理コンソール**、し、BizTalk グループ をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34388-113">In the console tree, expand **BizTalk Server Administration**, and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="34388-114">詳細ウィンドウで、をクリックして、**新しいクエリ**タブです。</span><span class="sxs-lookup"><span data-stu-id="34388-114">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="34388-115">**クエリ式**グループにおいて、**値**列で、選択**中断サービス インスタンスの**ドロップダウン リスト ボックスからです。</span><span class="sxs-lookup"><span data-stu-id="34388-115">In the **Query Expression** group, in the **Value** column, select **Suspended Service Instances** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="34388-116">**フィールド名**列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(**\***)、次の 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="34388-116">In the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select one or more of the following:</span></span>  
  
    |<span data-ttu-id="34388-117">アイテム</span><span class="sxs-lookup"><span data-stu-id="34388-117">Item</span></span>|<span data-ttu-id="34388-118">Description</span><span class="sxs-lookup"><span data-stu-id="34388-118">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="34388-119">**Application Name**</span><span class="sxs-lookup"><span data-stu-id="34388-119">**Application Name**</span></span>|<span data-ttu-id="34388-120">BizTalk Server アプリケーションの名前です。</span><span class="sxs-lookup"><span data-stu-id="34388-120">The name of the BizTalk Server application.</span></span>|  
    |<span data-ttu-id="34388-121">**作成日時**</span><span class="sxs-lookup"><span data-stu-id="34388-121">**Creation Time**</span></span>|<span data-ttu-id="34388-122">中断されたサービス インスタンスの中で、指定した日付の前または後に作成されたインスタンスを検索します。</span><span class="sxs-lookup"><span data-stu-id="34388-122">Find suspended service instances created before or after the specified date.</span></span>|  
    |<span data-ttu-id="34388-123">**エラー アダプター**</span><span class="sxs-lookup"><span data-stu-id="34388-123">**Error Adapter**</span></span>|<span data-ttu-id="34388-124">中断されたサービス インスタンスをアダプターの種類でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="34388-124">You can group or filter suspended service instances by adapter type.</span></span> <span data-ttu-id="34388-125">例: ファイル、FTP、HTTP、MQSeries、MSMQ、POP3、SMTP、SOAP、または Windows SharePoint Services です。</span><span class="sxs-lookup"><span data-stu-id="34388-125">For example: FILE, FTP, HTTP, MQSeries, MSMQ, POP3, SMTP, SOAP,  or Windows SharePoint Services.</span></span> <span data-ttu-id="34388-126">**注:**クエリの結果に指定したアダプターの使用中にエラーが発生、BizTalk Server ランタイムの実行時にアダプター フィールドは設定のみです。</span><span class="sxs-lookup"><span data-stu-id="34388-126">**Note:**  In the query results, the adapter field is only populated when the BizTalk Server runtime runs into an error while using the specified adater.</span></span> <span data-ttu-id="34388-127">ランタイムでアダプターのエラーが検出されなかった場合、クエリ結果の "エラー アダプター" フィールドは空になります。</span><span class="sxs-lookup"><span data-stu-id="34388-127">If the runtime does not find an error with the adapter, in the query results, the Error Adapter field is empty.</span></span>|  
    |<span data-ttu-id="34388-128">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="34388-128">**Error Code**</span></span>|<span data-ttu-id="34388-129">中断されたサービス インスタンスをエラー コードでグループ化またはフィルター選択して、そのエラー コードで中断されたすべてのサービス インスタンスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="34388-129">You can group or filter suspended service instances by error code to show all that service instances have been suspended with that error code.</span></span>|  
    |<span data-ttu-id="34388-130">**エラーの説明**</span><span class="sxs-lookup"><span data-stu-id="34388-130">**Error Description**</span></span>|<span data-ttu-id="34388-131">中断されたサービス インスタンスを、指定したエラーの説明でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="34388-131">You can group or filter suspended service instances with the specified error description.</span></span>|  
    |<span data-ttu-id="34388-132">**結果をグループ化**</span><span class="sxs-lookup"><span data-stu-id="34388-132">**Group Results By**</span></span>|<span data-ttu-id="34388-133">アダプター、アプリケーション、エラー コード、エラーの説明、ホスト名、サービス クラス、サービス インスタンスの状態、サービス名、または URI で結果をグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="34388-133">You can group or filter results by adapter, application, error code, error description, host name, service class, service instance status, service name, or URI.</span></span>|  
    |<span data-ttu-id="34388-134">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="34388-134">**Host Name**</span></span>|<span data-ttu-id="34388-135">中断されたサービス インスタンスをホスト名でグループ化またはフィルター選択します。</span><span class="sxs-lookup"><span data-stu-id="34388-135">Group or filter suspended service instances by host name.</span></span>|  
    |<span data-ttu-id="34388-136">**インスタンスの状態**</span><span class="sxs-lookup"><span data-stu-id="34388-136">**Instance Status**</span></span>|<span data-ttu-id="34388-137">中断されたインスタンスの中で再開できないインスタンスまたは再開できるインスタンスを検索できます。</span><span class="sxs-lookup"><span data-stu-id="34388-137">You can search for suspended but not resumable instances, or suspended and resumable instances.</span></span>|  
    |<span data-ttu-id="34388-138">**最大一致数**</span><span class="sxs-lookup"><span data-stu-id="34388-138">**Maximum Matches**</span></span>|<span data-ttu-id="34388-139">一致項目の表示数を指定します。</span><span class="sxs-lookup"><span data-stu-id="34388-139">The number of matches to display.</span></span>|  
    |<span data-ttu-id="34388-140">**サービス クラス**</span><span class="sxs-lookup"><span data-stu-id="34388-140">**Service Class**</span></span>|<span data-ttu-id="34388-141">[分離アダプター]、[メッセージング]、[メッセージング、分離アダプター]、[MSMQT]、[オーケストレーション]、または [ルーティング エラー報告] を指定して検索できます。</span><span class="sxs-lookup"><span data-stu-id="34388-141">You can search for isolated adapters; messaging; messaging, and isolated adapters; MSMQT; Orchestration; or Routing Failure Report.</span></span>|  
    |<span data-ttu-id="34388-142">**サービス名**</span><span class="sxs-lookup"><span data-stu-id="34388-142">**Service Name**</span></span>|<span data-ttu-id="34388-143">中断されたサービス インスタンスをサービス名でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="34388-143">You can group or filter suspended service instances by service name.</span></span>|  
    |<span data-ttu-id="34388-144">**サービスの種類 ID**</span><span class="sxs-lookup"><span data-stu-id="34388-144">**Service Type ID**</span></span>|<span data-ttu-id="34388-145">中断されたサービス インスタンスをサービスの種類 ID でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="34388-145">You can group or filter suspended service instances by service type ID.</span></span>|  
    |<span data-ttu-id="34388-146">**[中断時間]**</span><span class="sxs-lookup"><span data-stu-id="34388-146">**Suspension Time**</span></span>|<span data-ttu-id="34388-147">指定した日付の前または後に中断されたサービス インスタンスをグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="34388-147">You can group or filter suspended service instances suspended before or after the specified date.</span></span>|  
    |<span data-ttu-id="34388-148">**URI**</span><span class="sxs-lookup"><span data-stu-id="34388-148">**URI**</span></span>|<span data-ttu-id="34388-149">中断されたサービス インスタンスを URI でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="34388-149">You can group or filter suspended service instances by URI.</span></span> <span data-ttu-id="34388-150">**注:**クエリの結果に URI にのみ設定されます指定 URI に送信中にエラーが発生、BizTalk Server ランタイムを実行するとします。</span><span class="sxs-lookup"><span data-stu-id="34388-150">**Note:**  In the query results, the URI is only populated when the BizTalk Server runtime runs into an error while sending to the specified URI.</span></span> <span data-ttu-id="34388-151">URI への送信中にランタイムでエラーが検出されなかった場合、クエリ結果の "URI" フィールドは空になるか、または URI が利用できないことが表示されます。</span><span class="sxs-lookup"><span data-stu-id="34388-151">If the runtime does not find an error when sending to the URI, in the query results, the URI field is empty or shows "URI unavailable."</span></span>|  
  
6.  <span data-ttu-id="34388-152">完了、**値**で行う選択範囲の適切な列、**フィールド名**列です。</span><span class="sxs-lookup"><span data-stu-id="34388-152">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  
  
7.  <span data-ttu-id="34388-153">実行し、必要に応じて、クエリに行を追加、**フィールド名**、**演算子**、および**値**列、およびクリック**実行クエリ**です。</span><span class="sxs-lookup"><span data-stu-id="34388-153">Continue adding additional lines to the query as appropriate, by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34388-154">参照</span><span class="sxs-lookup"><span data-stu-id="34388-154">See Also</span></span>  
 <span data-ttu-id="34388-155">[管理コンソールの [クエリ] タブを使用します。](../core/using-the-administration-console-query-tab.md)</span><span class="sxs-lookup"><span data-stu-id="34388-155">[Using the Administration Console Query Tab](../core/using-the-administration-console-query-tab.md)</span></span>