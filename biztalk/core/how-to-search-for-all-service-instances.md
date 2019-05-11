---
title: すべてのサービス インスタンスを検索する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service instances, Query tab [Administration Console]
- Query tab [Administration Console], service instances
- Query tab [Administration Console], searching
- service instances, searching
- instances, services
ms.assetid: 48cb885c-aaf1-44e8-9810-2e70cf63db81
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbc3bc4383d3f2bd36a18adfdac33cca80482a72
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334800"
---
# <a name="how-to-search-for-all-service-instances"></a><span data-ttu-id="5f637-102">すべてのサービス インスタンスを検索する方法</span><span class="sxs-lookup"><span data-stu-id="5f637-102">How to Search for All Service Instances</span></span>
<span data-ttu-id="5f637-103">使用することができます、**クエリ** タブですべてのサービス インスタンスを検索するには、BizTalk Server 管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="5f637-103">You can use the **Query** tab in the BizTalk Server Administration Console to search for all service instances.</span></span> <span data-ttu-id="5f637-104">任意の実行中または中断されたインスタンスがある場合は、特定のサービスの種類の参加を解除することはできません。</span><span class="sxs-lookup"><span data-stu-id="5f637-104">You cannot unenlist a specific service type if there are any running or suspended instances.</span></span> <span data-ttu-id="5f637-105">たとえば、特定のサービスの種類の参加を解除する前に、実行中または中断されたインスタンスがないことを確認するすべてのサービス インスタンスを検索できます。</span><span class="sxs-lookup"><span data-stu-id="5f637-105">For example, before you can unenlist a specific service type, you can search for all service instances to ensure that there are no running or suspended instances.</span></span>  

> [!NOTE]
>  <span data-ttu-id="5f637-106">ときにグループ化とフィルタ リング、URI でのみ送信および受信ポートは、結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f637-106">When Grouping and Filtering by URI, only send and receive ports are displayed in the results.</span></span> <span data-ttu-id="5f637-107">グループ化し、URI でのフィルター処理には、オーケストレーションでは、表示される結果に含まれていないことはできません。</span><span class="sxs-lookup"><span data-stu-id="5f637-107">Grouping and Filtering by URI is not possible for orchestrations, which are not included in the displayed results.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="5f637-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="5f637-108">Prerequisites</span></span>  
 <span data-ttu-id="5f637-109">この手順を実行するには、BizTalk Server Operators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f637-109">To perform this procedure, you must be logged on as a member of the BizTalk Server Operators group.</span></span>  

### <a name="to-search-for-all-service-instances"></a><span data-ttu-id="5f637-110">すべてのサービス インスタンスを検索するには</span><span class="sxs-lookup"><span data-stu-id="5f637-110">To search for all service instances</span></span>  

1. <span data-ttu-id="5f637-111">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="5f637-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="5f637-112">コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、し、[BizTalk グループ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f637-112">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then click the BizTalk group.</span></span>  

3. <span data-ttu-id="5f637-113">詳細ウィンドウでをクリックして、**新しいクエリ**タブ。</span><span class="sxs-lookup"><span data-stu-id="5f637-113">In the details pane, click the **New Query** tab.</span></span>  

4. <span data-ttu-id="5f637-114">**クエリ式**グループに、**値**列で、**進行中のすべてのサービス インスタンス**ドロップダウン リスト ボックスから。</span><span class="sxs-lookup"><span data-stu-id="5f637-114">In the **Query Expression** group, in the **Value** column, select **All In-Progress Service Instances** from the drop-down list box.</span></span>  

5. <span data-ttu-id="5f637-115">**フィールド名**列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(\* *\\* \* \*)、次の 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="5f637-115">In the **Field Name** column, in the empty drop-down list box next to the asterisk (\*\*\\*\*\*), select one or more of the following:</span></span>  


   |        <span data-ttu-id="5f637-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5f637-116">Use this</span></span>         |                                                                                                              <span data-ttu-id="5f637-117">目的</span><span class="sxs-lookup"><span data-stu-id="5f637-117">To do this</span></span>                                                                                                              |
   |-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  <span data-ttu-id="5f637-118">**Application Name**</span><span class="sxs-lookup"><span data-stu-id="5f637-118">**Application Name**</span></span>   |                                                                                                   <span data-ttu-id="5f637-119">BizTalk Server アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="5f637-119">The BizTalk Server application.</span></span>                                                                                                    |
   |    <span data-ttu-id="5f637-120">**作成時刻**</span><span class="sxs-lookup"><span data-stu-id="5f637-120">**Creation Time**</span></span>    |                                                                                <span data-ttu-id="5f637-121">指定した日付の前後に作成されたすべてのサービス インスタンスを検索します。</span><span class="sxs-lookup"><span data-stu-id="5f637-121">Find all service instances created before or after the specified date.</span></span>                                                                                |
   |  <span data-ttu-id="5f637-122">**結果をグループ化**</span><span class="sxs-lookup"><span data-stu-id="5f637-122">**Group Results By**</span></span>   |                                                              <span data-ttu-id="5f637-123">アプリケーション、ホスト名、サービス クラス、サービス インスタンスの状態、またはサービス名で結果をグループ化することができます。</span><span class="sxs-lookup"><span data-stu-id="5f637-123">You can group results by application, host name, service class, service instance status, or service name.</span></span>                                                               |
   |      <span data-ttu-id="5f637-124">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="5f637-124">**Host Name**</span></span>      |                                                                                                    <span data-ttu-id="5f637-125">BizTalk ホストの名前。</span><span class="sxs-lookup"><span data-stu-id="5f637-125">The name of the BizTalk Host.</span></span>                                                                                                     |
   |   <span data-ttu-id="5f637-126">**インスタンスの状態**</span><span class="sxs-lookup"><span data-stu-id="5f637-126">**Instance Status**</span></span>   | <span data-ttu-id="5f637-127">実行中のすべてのインスタンス、中断されたすべてのインスタンス、アクティブなインスタンス、退避済みのインスタンスを検索すること、インスタンス、スケジュール済みのインスタンス、中断、再開不可のインスタンスまたは一時停止、再開可能なインスタンスを実行する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="5f637-127">You can search for all running instances, all suspended instances, active instances, dehydrated instances, ready to run instances, scheduled instances, suspended but not resumable instances, or suspended and resumable instances.</span></span> |
   |   <span data-ttu-id="5f637-128">**最大一致数**</span><span class="sxs-lookup"><span data-stu-id="5f637-128">**Maximum Matches**</span></span>   |               <span data-ttu-id="5f637-129">一致項目の数 (必須) を表示します。</span><span class="sxs-lookup"><span data-stu-id="5f637-129">The number of matches to display (required).</span></span> <span data-ttu-id="5f637-130">これは通常、50、既定値に設定します。</span><span class="sxs-lookup"><span data-stu-id="5f637-130">This is usually set to 50, the default.</span></span><br /><br /> <span data-ttu-id="5f637-131">結果をグループ化する場合、グループ、レコードの合計数ではない数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f637-131">When you include Group Results By, this displays the number of groups, not the total number of records.</span></span>               |
   |    <span data-ttu-id="5f637-132">**サービス クラス**</span><span class="sxs-lookup"><span data-stu-id="5f637-132">**Service Class**</span></span>    |                                                 <span data-ttu-id="5f637-133">分離アダプターは; を検索することができます。メッセージング。メッセージング、および分離アダプタです。MSMQT;オーケストレーションです。または、ルーティング エラー報告します。</span><span class="sxs-lookup"><span data-stu-id="5f637-133">You can search for isolated adapters; messaging; messaging, and isolated adapters; MSMQT; Orchestration; or Routing Failure Report.</span></span>                                                  |
   | <span data-ttu-id="5f637-134">**サービス インスタンス ID**</span><span class="sxs-lookup"><span data-stu-id="5f637-134">**Service Instance ID**</span></span> |                                                                                  <span data-ttu-id="5f637-135">グループ化したり、サービス インスタンスをサービス インスタンス ID でフィルター処理</span><span class="sxs-lookup"><span data-stu-id="5f637-135">You can group or filter service instances by service instance ID.</span></span>                                                                                   |
   |    <span data-ttu-id="5f637-136">**[サービス名]**</span><span class="sxs-lookup"><span data-stu-id="5f637-136">**Service Name**</span></span>     |                                                                                      <span data-ttu-id="5f637-137">グループ化またはサービス インスタンスをサービス名でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="5f637-137">You can group or filter service instances by service name.</span></span>                                                                                      |
   |   <span data-ttu-id="5f637-138">**サービスの種類 ID**</span><span class="sxs-lookup"><span data-stu-id="5f637-138">**Service Type ID**</span></span>   |                                                                                    <span data-ttu-id="5f637-139">グループ化したり、サービス インスタンスをサービスの種類 ID でフィルター処理</span><span class="sxs-lookup"><span data-stu-id="5f637-139">You can group or filter service instances by service type ID.</span></span>                                                                                     |


6. <span data-ttu-id="5f637-140">完了、**値**で行った選択の適切な列、**フィールド名**列。</span><span class="sxs-lookup"><span data-stu-id="5f637-140">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  

7. <span data-ttu-id="5f637-141">実行して、必要に応じて、クエリに行を追加、**フィールド名**、**演算子**、および**値**列、およびクリック**実行クエリ**します。</span><span class="sxs-lookup"><span data-stu-id="5f637-141">Continue adding additional lines to the query as appropriate, by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="5f637-142">参照</span><span class="sxs-lookup"><span data-stu-id="5f637-142">See Also</span></span>  
 <span data-ttu-id="5f637-143">[管理コンソールの [クエリ] タブの使用](../core/using-the-administration-console-query-tab.md)</span><span class="sxs-lookup"><span data-stu-id="5f637-143">[Using the Administration Console Query Tab](../core/using-the-administration-console-query-tab.md)</span></span>