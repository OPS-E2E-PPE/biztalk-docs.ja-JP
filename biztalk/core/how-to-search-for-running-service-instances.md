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
ms.openlocfilehash: 4c61b94b440810fc948ae7e9e51c1897204d28c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023936"
---
# <a name="how-to-search-for-running-service-instances"></a><span data-ttu-id="37313-102">実行中のサービス インスタンスを検索する方法</span><span class="sxs-lookup"><span data-stu-id="37313-102">How to Search for Running Service Instances</span></span>
<span data-ttu-id="37313-103">使用することができます、**クエリ** タブで、特定の検索するには、BizTalk Server 管理コンソールに退避された、アクティブ、ブレークポイント、スケジュール、およびサービス インスタンスを再試行しています。</span><span class="sxs-lookup"><span data-stu-id="37313-103">You can use the **Query** tab in the BizTalk Server Administration Console to search for a specific dehydrated, active, in breakpoint, scheduled, and retrying service instance.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="37313-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="37313-104">Prerequisites</span></span>  
 <span data-ttu-id="37313-105">ここで示す手順を実行するには、BizTalk Server Operators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="37313-105">To perform this procedure, you must be logged on as a member of the BizTalk Server Operators group.</span></span>  

### <a name="to-search-for-running-service-instances"></a><span data-ttu-id="37313-106">実行中のサービス インスタンスを検索するには</span><span class="sxs-lookup"><span data-stu-id="37313-106">To search for running service instances</span></span>  

1. <span data-ttu-id="37313-107">クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="37313-107">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="37313-108">コンソール ツリーで、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] を展開し、[BizTalk グループ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37313-108">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then click the BizTalk group.</span></span>  

3. <span data-ttu-id="37313-109">詳細ウィンドウでをクリックして、**新しいクエリ**タブ。</span><span class="sxs-lookup"><span data-stu-id="37313-109">In the details pane, click the **New Query** tab.</span></span>  

4. <span data-ttu-id="37313-110">**クエリ式**グループに、**値**列で、**サービス インスタンスを実行している**ドロップダウン リスト ボックスから。</span><span class="sxs-lookup"><span data-stu-id="37313-110">In the **Query Expression** group, in the **Value** column, select **Running Service Instances** from the drop-down list box.</span></span>  

5. <span data-ttu-id="37313-111">**フィールド名**列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(\* *\\* \* \*)、次の 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="37313-111">In the **Field Name** column, in the empty drop-down list box next to the asterisk (\*\*\\*\*\*), select one or more of the following:</span></span>  


   |          <span data-ttu-id="37313-112">アイテム</span><span class="sxs-lookup"><span data-stu-id="37313-112">Item</span></span>          |                                                             <span data-ttu-id="37313-113">説明</span><span class="sxs-lookup"><span data-stu-id="37313-113">Description</span></span>                                                             |
   |------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
   |  <span data-ttu-id="37313-114">**Application Name**</span><span class="sxs-lookup"><span data-stu-id="37313-114">**Application Name**</span></span>  |                                                   <span data-ttu-id="37313-115">BizTalk Server アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="37313-115">The BizTalk Server application.</span></span>                                                   |
   |   <span data-ttu-id="37313-116">**作成時刻**</span><span class="sxs-lookup"><span data-stu-id="37313-116">**Creation Time**</span></span>    |                             <span data-ttu-id="37313-117">指定した日付の前または後に作成された実行中のサービス インスタンスを検索します。</span><span class="sxs-lookup"><span data-stu-id="37313-117">Find running service instances created before or after the specified date.</span></span>                              |
   |  <span data-ttu-id="37313-118">**結果をグループ化**</span><span class="sxs-lookup"><span data-stu-id="37313-118">**Group Results By**</span></span>  |  <span data-ttu-id="37313-119">アプリケーション、ホスト名、保留中の操作の種類、サービス クラス、サービス インスタンスの状態、またはサービス名で結果をグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="37313-119">You can group results by application, host name, pending operation type, service class, service instance status, or service name.</span></span>  |
   |     <span data-ttu-id="37313-120">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="37313-120">**Host Name**</span></span>      |                                                    <span data-ttu-id="37313-121">BizTalk ホストの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="37313-121">The name of the BizTalk Host.</span></span>                                                    |
   |  <span data-ttu-id="37313-122">**インスタンスの状態**</span><span class="sxs-lookup"><span data-stu-id="37313-122">**Instance Status**</span></span>   |             <span data-ttu-id="37313-123">アクティブなインスタンス、退避済みのインスタンス、実行準備完了のインスタンス、およびスケジュール済みのインスタンスを検索できます。</span><span class="sxs-lookup"><span data-stu-id="37313-123">You can search for active instances, dehydrated instances, ready to run instances, and scheduled instances.</span></span>             |
   |  <span data-ttu-id="37313-124">**最大一致数**</span><span class="sxs-lookup"><span data-stu-id="37313-124">**Maximum Matches**</span></span>   |                                                  <span data-ttu-id="37313-125">一致項目の表示数を指定します。</span><span class="sxs-lookup"><span data-stu-id="37313-125">The number of matches to display.</span></span>                                                  |
   | <span data-ttu-id="37313-126">**保留中の操作**</span><span class="sxs-lookup"><span data-stu-id="37313-126">**Pending Operations**</span></span> |                      <span data-ttu-id="37313-127">中断または終了の操作が保留されている、実行中のサービス インスタンスを検索できます。</span><span class="sxs-lookup"><span data-stu-id="37313-127">You can search for running service instances that are pending suspension or termination.</span></span>                       |
   |   <span data-ttu-id="37313-128">**サービス クラス**</span><span class="sxs-lookup"><span data-stu-id="37313-128">**Service Class**</span></span>    | <span data-ttu-id="37313-129">[分離アダプター]、[メッセージング]、[メッセージング、分離アダプター]、[MSMQT]、[オーケストレーション]、または [ルーティング エラー報告] を指定して検索できます。</span><span class="sxs-lookup"><span data-stu-id="37313-129">You can search for isolated adapters; messaging; messaging, and isolated adapters; MSMQT; Orchestration; or Routing Failure Report.</span></span> |
   |    <span data-ttu-id="37313-130">**[サービス名]**</span><span class="sxs-lookup"><span data-stu-id="37313-130">**Service Name**</span></span>    |                                 <span data-ttu-id="37313-131">実行中のサービス インスタンスをサービス名でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="37313-131">You can group or filter running service instances by service name.</span></span>                                  |
   |  <span data-ttu-id="37313-132">**サービスの種類 ID**</span><span class="sxs-lookup"><span data-stu-id="37313-132">**Service Type ID**</span></span>   |                                        <span data-ttu-id="37313-133">メッセージをサービスの種類 ID でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="37313-133">You can group or filter messages by service type ID.</span></span>                                         |


6. <span data-ttu-id="37313-134">完了、**値**で行った選択の適切な列、**フィールド名**列。</span><span class="sxs-lookup"><span data-stu-id="37313-134">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  

7. <span data-ttu-id="37313-135">実行して、必要に応じて、クエリに行を追加、**フィールド名**、**演算子**、および**値**列、およびクリック**実行クエリ**します。</span><span class="sxs-lookup"><span data-stu-id="37313-135">Continue adding additional lines to the query as appropriate, by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="37313-136">参照</span><span class="sxs-lookup"><span data-stu-id="37313-136">See Also</span></span>  
 <span data-ttu-id="37313-137">[管理コンソールの [クエリ] タブの使用](../core/using-the-administration-console-query-tab.md)</span><span class="sxs-lookup"><span data-stu-id="37313-137">[Using the Administration Console Query Tab](../core/using-the-administration-console-query-tab.md)</span></span>