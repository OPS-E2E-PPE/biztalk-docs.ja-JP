---
title: 実行中のサービス インスタンスを検索する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service instances, viewing
- service instances, Query tab [Administration Console]
- Query tab [Administration Console], service instances
- Query tab [Administration Console], searching
- service instances, searching
- service instances, running
ms.assetid: fc65bf33-c013-4e6a-b9fd-b4536811e7b4
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9a09a2ed8f5f209549d7eb5246db4c4509eccd1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384019"
---
# <a name="how-to-search-for-running-service-instances"></a><span data-ttu-id="9aed2-102">実行中のサービス インスタンスを検索する方法</span><span class="sxs-lookup"><span data-stu-id="9aed2-102">How to Search for Running Service Instances</span></span>
<span data-ttu-id="9aed2-103">使用することができます、**クエリ** タブで、特定の検索するには、BizTalk Server 管理コンソールに退避された、アクティブ、ブレークポイント、スケジュール、およびサービス インスタンスを再試行しています。</span><span class="sxs-lookup"><span data-stu-id="9aed2-103">You can use the **Query** tab in the BizTalk Server Administration Console to search for a specific dehydrated, active, in breakpoint, scheduled, and retrying service instance.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="9aed2-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="9aed2-104">Prerequisites</span></span>  
 <span data-ttu-id="9aed2-105">この手順を実行するには、BizTalk Server Operators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9aed2-105">To perform this procedure, you must be logged on as a member of the BizTalk Server Operators group.</span></span>  

### <a name="to-search-for-running-service-instances"></a><span data-ttu-id="9aed2-106">実行中のサービス インスタンスを検索するには</span><span class="sxs-lookup"><span data-stu-id="9aed2-106">To search for running service instances</span></span>  

1. <span data-ttu-id="9aed2-107">クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="9aed2-107">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="9aed2-108">コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、し、[BizTalk グループ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9aed2-108">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then click the BizTalk group.</span></span>  

3. <span data-ttu-id="9aed2-109">詳細ウィンドウでをクリックして、**新しいクエリ**タブ。</span><span class="sxs-lookup"><span data-stu-id="9aed2-109">In the details pane, click the **New Query** tab.</span></span>  

4. <span data-ttu-id="9aed2-110">**クエリ式**グループに、**値**列で、**サービス インスタンスを実行している**ドロップダウン リスト ボックスから。</span><span class="sxs-lookup"><span data-stu-id="9aed2-110">In the **Query Expression** group, in the **Value** column, select **Running Service Instances** from the drop-down list box.</span></span>  

5. <span data-ttu-id="9aed2-111">**フィールド名**列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(\* *\\* \* \*)、次の 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="9aed2-111">In the **Field Name** column, in the empty drop-down list box next to the asterisk (\*\*\\*\*\*), select one or more of the following:</span></span>  


   |          <span data-ttu-id="9aed2-112">アイテム</span><span class="sxs-lookup"><span data-stu-id="9aed2-112">Item</span></span>          |                                                             <span data-ttu-id="9aed2-113">説明</span><span class="sxs-lookup"><span data-stu-id="9aed2-113">Description</span></span>                                                             |
   |------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
   |  <span data-ttu-id="9aed2-114">**Application Name**</span><span class="sxs-lookup"><span data-stu-id="9aed2-114">**Application Name**</span></span>  |                                                   <span data-ttu-id="9aed2-115">BizTalk Server アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="9aed2-115">The BizTalk Server application.</span></span>                                                   |
   |   <span data-ttu-id="9aed2-116">**作成時刻**</span><span class="sxs-lookup"><span data-stu-id="9aed2-116">**Creation Time**</span></span>    |                             <span data-ttu-id="9aed2-117">検索する前に、または指定日付より後に作成されたサービス インスタンスを実行しています。</span><span class="sxs-lookup"><span data-stu-id="9aed2-117">Find running service instances created before or after the specified date.</span></span>                              |
   |  <span data-ttu-id="9aed2-118">**結果をグループ化**</span><span class="sxs-lookup"><span data-stu-id="9aed2-118">**Group Results By**</span></span>  |  <span data-ttu-id="9aed2-119">アプリケーション、操作の種類、サービス クラス、サービス インスタンスの状態、保留中のホスト名またはサービス名で結果をグループ化することができます。</span><span class="sxs-lookup"><span data-stu-id="9aed2-119">You can group results by application, host name, pending operation type, service class, service instance status, or service name.</span></span>  |
   |     <span data-ttu-id="9aed2-120">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="9aed2-120">**Host Name**</span></span>      |                                                    <span data-ttu-id="9aed2-121">BizTalk ホストの名前。</span><span class="sxs-lookup"><span data-stu-id="9aed2-121">The name of the BizTalk Host.</span></span>                                                    |
   |  <span data-ttu-id="9aed2-122">**インスタンスの状態**</span><span class="sxs-lookup"><span data-stu-id="9aed2-122">**Instance Status**</span></span>   |             <span data-ttu-id="9aed2-123">インスタンス、およびスケジュール済みのインスタンスを実行する準備がアクティブなインスタンス、退避済みのインスタンスを検索できます。</span><span class="sxs-lookup"><span data-stu-id="9aed2-123">You can search for active instances, dehydrated instances, ready to run instances, and scheduled instances.</span></span>             |
   |  <span data-ttu-id="9aed2-124">**最大一致数**</span><span class="sxs-lookup"><span data-stu-id="9aed2-124">**Maximum Matches**</span></span>   |                                                  <span data-ttu-id="9aed2-125">表示する一致の数。</span><span class="sxs-lookup"><span data-stu-id="9aed2-125">The number of matches to display.</span></span>                                                  |
   | <span data-ttu-id="9aed2-126">**保留中の操作**</span><span class="sxs-lookup"><span data-stu-id="9aed2-126">**Pending Operations**</span></span> |                      <span data-ttu-id="9aed2-127">中断または終了の保留中のサービス インスタンスの実行を検索することができます。</span><span class="sxs-lookup"><span data-stu-id="9aed2-127">You can search for running service instances that are pending suspension or termination.</span></span>                       |
   |   <span data-ttu-id="9aed2-128">**サービス クラス**</span><span class="sxs-lookup"><span data-stu-id="9aed2-128">**Service Class**</span></span>    | <span data-ttu-id="9aed2-129">分離アダプターは; を検索することができます。メッセージング。メッセージング、および分離アダプタです。MSMQT;オーケストレーションです。または、ルーティング エラー報告します。</span><span class="sxs-lookup"><span data-stu-id="9aed2-129">You can search for isolated adapters; messaging; messaging, and isolated adapters; MSMQT; Orchestration; or Routing Failure Report.</span></span> |
   |    <span data-ttu-id="9aed2-130">**[サービス名]**</span><span class="sxs-lookup"><span data-stu-id="9aed2-130">**Service Name**</span></span>    |                                 <span data-ttu-id="9aed2-131">グループ化したり、フィルター処理をサービス名でサービス インスタンスを実行します。</span><span class="sxs-lookup"><span data-stu-id="9aed2-131">You can group or filter running service instances by service name.</span></span>                                  |
   |  <span data-ttu-id="9aed2-132">**サービスの種類 ID**</span><span class="sxs-lookup"><span data-stu-id="9aed2-132">**Service Type ID**</span></span>   |                                        <span data-ttu-id="9aed2-133">グループ化したりフィルター サービスがメッセージ ID を入力します</span><span class="sxs-lookup"><span data-stu-id="9aed2-133">You can group or filter messages by service type ID.</span></span>                                         |


6. <span data-ttu-id="9aed2-134">完了、**値**で行った選択の適切な列、**フィールド名**列。</span><span class="sxs-lookup"><span data-stu-id="9aed2-134">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  

7. <span data-ttu-id="9aed2-135">実行して、必要に応じて、クエリに行を追加、**フィールド名**、**演算子**、および**値**列、およびクリック**実行クエリ**します。</span><span class="sxs-lookup"><span data-stu-id="9aed2-135">Continue adding additional lines to the query as appropriate, by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="9aed2-136">参照</span><span class="sxs-lookup"><span data-stu-id="9aed2-136">See Also</span></span>  
 <span data-ttu-id="9aed2-137">[管理コンソールの [クエリ] タブの使用](../core/using-the-administration-console-query-tab.md)</span><span class="sxs-lookup"><span data-stu-id="9aed2-137">[Using the Administration Console Query Tab](../core/using-the-administration-console-query-tab.md)</span></span>