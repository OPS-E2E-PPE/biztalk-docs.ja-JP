---
title: すべてのサービス インスタンスを検索する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: e96622fad23c28c0d4147f64a11cc540e88e7f97
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "22255122"
---
# <a name="how-to-search-for-all-service-instances"></a><span data-ttu-id="978c8-102">すべてのサービス インスタンスを検索する方法</span><span class="sxs-lookup"><span data-stu-id="978c8-102">How to Search for All Service Instances</span></span>
<span data-ttu-id="978c8-103">使用することができます、 **クエリ**  タブで、BizTalk Server 管理コンソールのすべてのサービス インスタンスを検索します。</span><span class="sxs-lookup"><span data-stu-id="978c8-103">You can use the **Query** tab in the BizTalk Server Administration Console to search for all service instances.</span></span> <span data-ttu-id="978c8-104">実行中のインスタンスまたは中断されたインスタンスがある場合、特定のサービスの種類の参加を解除することはできません。</span><span class="sxs-lookup"><span data-stu-id="978c8-104">You cannot unenlist a specific service type if there are any running or suspended instances.</span></span> <span data-ttu-id="978c8-105">特定のサービスの種類の参加を解除する前に、すべてのサービス インスタンスを検索して、実行中または中断されたインスタンスがないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="978c8-105">For example, before you can unenlist a specific service type, you can search for all service instances to ensure that there are no running or suspended instances.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="978c8-106">URI によるグループ化とフィルター選択を行うと、検索結果には送信ポートと受信ポートのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="978c8-106">When Grouping and Filtering by URI, only send and receive ports are displayed in the results.</span></span> <span data-ttu-id="978c8-107">URI によるグループ化とフィルター選択はオーケストレーションには使用できないので、表示される結果にオーケストレーションは含まれません。</span><span class="sxs-lookup"><span data-stu-id="978c8-107">Grouping and Filtering by URI is not possible for orchestrations, which are not included in the displayed results.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="978c8-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="978c8-108">Prerequisites</span></span>  
 <span data-ttu-id="978c8-109">ここで示す手順を実行するには、BizTalk Server Operators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="978c8-109">To perform this procedure, you must be logged on as a member of the BizTalk Server Operators group.</span></span>  
  
### <a name="to-search-for-all-service-instances"></a><span data-ttu-id="978c8-110">すべてのサービス インスタンスを検索するには</span><span class="sxs-lookup"><span data-stu-id="978c8-110">To search for all service instances</span></span>  
  
1.  <span data-ttu-id="978c8-111">をクリックして **開始**, 、 をクリックして **すべてのプログラム**, 、 をクリックして [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], 、 をクリックし、 **BizTalk Server 管理コンソール**します。</span><span class="sxs-lookup"><span data-stu-id="978c8-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="978c8-112">コンソール ツリーで、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] を展開し、[BizTalk グループ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="978c8-112">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="978c8-113">詳細ペインでクリックして、 **新しいクエリ**  タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="978c8-113">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="978c8-114">**クエリ式** グループの **値** 列で、選択 **進行中のすべてのサービス インスタンス** ドロップダウン リスト ボックスからです。</span><span class="sxs-lookup"><span data-stu-id="978c8-114">In the **Query Expression** group, in the **Value** column, select **All In-Progress Service Instances** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="978c8-115">**フィールド名** 列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(**\***)、次の 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="978c8-115">In the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select one or more of the following:</span></span>  
  
    |<span data-ttu-id="978c8-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="978c8-116">Use this</span></span>|<span data-ttu-id="978c8-117">目的</span><span class="sxs-lookup"><span data-stu-id="978c8-117">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="978c8-118">**アプリケーション名**</span><span class="sxs-lookup"><span data-stu-id="978c8-118">**Application Name**</span></span>|<span data-ttu-id="978c8-119">BizTalk Server アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="978c8-119">The BizTalk Server application.</span></span>|  
    |<span data-ttu-id="978c8-120">**作成日時**</span><span class="sxs-lookup"><span data-stu-id="978c8-120">**Creation Time**</span></span>|<span data-ttu-id="978c8-121">指定した日付の前または後に作成されたすべてのサービス インスタンスを検索します。</span><span class="sxs-lookup"><span data-stu-id="978c8-121">Find all service instances created before or after the specified date.</span></span>|  
    |<span data-ttu-id="978c8-122">**結果をグループ化**</span><span class="sxs-lookup"><span data-stu-id="978c8-122">**Group Results By**</span></span>|<span data-ttu-id="978c8-123">アプリケーション、ホスト名、サービス クラス、サービス インスタンスの状態、またはサービス名で結果をグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="978c8-123">You can group results by application, host name, service class, service instance status, or service name.</span></span>|  
    |<span data-ttu-id="978c8-124">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="978c8-124">**Host Name**</span></span>|<span data-ttu-id="978c8-125">BizTalk ホストの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="978c8-125">The name of the BizTalk Host.</span></span>|  
    |<span data-ttu-id="978c8-126">**インスタンスの状態**</span><span class="sxs-lookup"><span data-stu-id="978c8-126">**Instance Status**</span></span>|<span data-ttu-id="978c8-127">実行中のすべてのインスタンス、中断されたすべてのインスタンス、アクティブなインスタンス、退避済みのインスタンス、実行準備完了のインスタンス、スケジュール済みのインスタンス、中断された再開不可のインスタンス、または中断された再開可能なインスタンスを検索できます。</span><span class="sxs-lookup"><span data-stu-id="978c8-127">You can search for all running instances, all suspended instances, active instances, dehydrated instances, ready to run instances, scheduled instances, suspended but not resumable instances, or suspended and resumable instances.</span></span>|  
    |<span data-ttu-id="978c8-128">**最大一致数**</span><span class="sxs-lookup"><span data-stu-id="978c8-128">**Maximum Matches**</span></span>|<span data-ttu-id="978c8-129">一致項目の表示数を指定します (必須)。</span><span class="sxs-lookup"><span data-stu-id="978c8-129">The number of matches to display (required).</span></span> <span data-ttu-id="978c8-130">通常は 50 (既定値) に設定します。</span><span class="sxs-lookup"><span data-stu-id="978c8-130">This is usually set to 50, the default.</span></span><br /><br /> <span data-ttu-id="978c8-131">[結果をグループ化する条件] を選択した場合、レコード数の合計ではなく、グループ数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="978c8-131">When you include Group Results By, this displays the number of groups, not the total number of records.</span></span>|  
    |<span data-ttu-id="978c8-132">**サービス クラス**</span><span class="sxs-lookup"><span data-stu-id="978c8-132">**Service Class**</span></span>|<span data-ttu-id="978c8-133">[分離アダプター]、[メッセージング]、[メッセージング、分離アダプター]、[MSMQT]、[オーケストレーション]、または [ルーティング エラー報告] を指定して検索できます。</span><span class="sxs-lookup"><span data-stu-id="978c8-133">You can search for isolated adapters; messaging; messaging, and isolated adapters; MSMQT; Orchestration; or Routing Failure Report.</span></span>|  
    |<span data-ttu-id="978c8-134">**サービス インスタンス ID**</span><span class="sxs-lookup"><span data-stu-id="978c8-134">**Service Instance ID**</span></span>|<span data-ttu-id="978c8-135">サービス インスタンスをサービス インスタンス ID でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="978c8-135">You can group or filter service instances by service instance ID.</span></span>|  
    |<span data-ttu-id="978c8-136">**サービス名**</span><span class="sxs-lookup"><span data-stu-id="978c8-136">**Service Name**</span></span>|<span data-ttu-id="978c8-137">サービス インスタンスをサービス名でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="978c8-137">You can group or filter service instances by service name.</span></span>|  
    |<span data-ttu-id="978c8-138">**サービスの種類 ID**</span><span class="sxs-lookup"><span data-stu-id="978c8-138">**Service Type ID**</span></span>|<span data-ttu-id="978c8-139">サービス インスタンスをサービスの種類 ID でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="978c8-139">You can group or filter service instances by service type ID.</span></span>|  
  
6.  <span data-ttu-id="978c8-140">完了、 **値** 列に適切な選択範囲にすると、 **フィールド名** 列です。</span><span class="sxs-lookup"><span data-stu-id="978c8-140">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  
  
7.  <span data-ttu-id="978c8-141">完了することで、必要に応じてクエリに行を追加、 **フィールド名**, 、**演算子**, 、および **値** 列、およびクリック **クエリの実行**します。</span><span class="sxs-lookup"><span data-stu-id="978c8-141">Continue adding additional lines to the query as appropriate, by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="978c8-142">参照</span><span class="sxs-lookup"><span data-stu-id="978c8-142">See Also</span></span>  
 <span data-ttu-id="978c8-143">[管理コンソールの [クエリ] タブの使用](../core/using-the-administration-console-query-tab.md)</span><span class="sxs-lookup"><span data-stu-id="978c8-143">[Using the Administration Console Query Tab](../core/using-the-administration-console-query-tab.md)</span></span>