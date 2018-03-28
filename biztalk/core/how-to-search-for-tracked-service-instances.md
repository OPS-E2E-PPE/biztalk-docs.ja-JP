---
title: 追跡対象サービス インスタンスを検索する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6337df9-8c2e-4d4a-a64b-cc040f83bd91
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08e5a7fa563e175d6a1d784e546bd399e20d3c21
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-search-for-tracked-service-instances"></a><span data-ttu-id="4cb79-102">追跡対象サービス インスタンスを検索する方法</span><span class="sxs-lookup"><span data-stu-id="4cb79-102">How to Search for Tracked Service Instances</span></span>
<span data-ttu-id="4cb79-103">使用することができます、**クエリ** タブで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールのすべての追跡対象サービス インスタンスを検索します。</span><span class="sxs-lookup"><span data-stu-id="4cb79-103">You can use the **Query** tab in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to search for all tracked service instances.</span></span> <span data-ttu-id="4cb79-104">サービス インスタンスを検索するには、アセンブリの名前とバージョン、有効期間の開始時刻と終了時刻、サービス クラスの名前またはインスタンス ID、ホスト名、エラー コード、サービス インスタンスの状態に基づいて検索できます。</span><span class="sxs-lookup"><span data-stu-id="4cb79-104">To locate service instances, you can search on the name and version of the assembly, the start and end times of its lifetime, the name or instance ID of the service class, host name, error code, and the state of the service instance.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4cb79-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="4cb79-105">Prerequisites</span></span>  
 <span data-ttu-id="4cb79-106">ここで示す手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cb79-106">To perform this procedure, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators group.</span></span>  
  
### <a name="to-search-for-tracked-service-instances"></a><span data-ttu-id="4cb79-107">追跡対象サービス インスタンスを検索するには</span><span class="sxs-lookup"><span data-stu-id="4cb79-107">To search for tracked service instances</span></span>  
  
1.  <span data-ttu-id="4cb79-108">をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="4cb79-108">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2.  <span data-ttu-id="4cb79-109">コンソール ツリーで  **BizTalk Server 管理コンソール**, 、し、BizTalk グループ をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cb79-109">In the console tree, expand **BizTalk Server Administration**, and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="4cb79-110">詳細ペインでクリックして、 **新しいクエリ**  タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cb79-110">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="4cb79-111">**クエリ式** グループの **値** 列で、選択 **追跡サービス インスタンス** ドロップダウン リスト ボックスからです。</span><span class="sxs-lookup"><span data-stu-id="4cb79-111">In the **Query Expression** group, in the **Value** column, select **Tracked Service Instances** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="4cb79-112">**フィールド名** 列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(**\***)、次の 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="4cb79-112">In the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select one or more of the following:</span></span>  
  
    |<span data-ttu-id="4cb79-113">アイテム</span><span class="sxs-lookup"><span data-stu-id="4cb79-113">Item</span></span>|<span data-ttu-id="4cb79-114">Description</span><span class="sxs-lookup"><span data-stu-id="4cb79-114">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="4cb79-115">**アセンブリ名**</span><span class="sxs-lookup"><span data-stu-id="4cb79-115">**Assembly Name**</span></span>|<span data-ttu-id="4cb79-116">サービス インスタンスのアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="4cb79-116">Name of the assembly for the service instance.</span></span>|  
    |<span data-ttu-id="4cb79-117">**アセンブリのバージョン**</span><span class="sxs-lookup"><span data-stu-id="4cb79-117">**Assembly Version**</span></span>|<span data-ttu-id="4cb79-118">サービス インスタンスのバージョン。</span><span class="sxs-lookup"><span data-stu-id="4cb79-118">Version of the service instance.</span></span>|  
    |<span data-ttu-id="4cb79-119">**終了時刻**</span><span class="sxs-lookup"><span data-stu-id="4cb79-119">**End Time**</span></span>|<span data-ttu-id="4cb79-120">サービス インスタンスの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="4cb79-120">End time of the service instance.</span></span>|  
    |<span data-ttu-id="4cb79-121">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="4cb79-121">**Error Code**</span></span>|<span data-ttu-id="4cb79-122">サービス インスタンスに関連付けられているエラー コード。</span><span class="sxs-lookup"><span data-stu-id="4cb79-122">Any error code associated with the service instance.</span></span>|  
    |<span data-ttu-id="4cb79-123">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="4cb79-123">**Host Name**</span></span>|<span data-ttu-id="4cb79-124">サービス インスタンスのホスト名。</span><span class="sxs-lookup"><span data-stu-id="4cb79-124">The host name of the service instance.</span></span>|  
    |<span data-ttu-id="4cb79-125">**最大一致数**</span><span class="sxs-lookup"><span data-stu-id="4cb79-125">**Maximum Matches**</span></span>|<span data-ttu-id="4cb79-126">一致項目の表示数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4cb79-126">The number of matches to display.</span></span>|  
    |<span data-ttu-id="4cb79-127">**サービス クラス**</span><span class="sxs-lookup"><span data-stu-id="4cb79-127">**Service Class**</span></span>|<span data-ttu-id="4cb79-128">サービス インスタンスのクラス。</span><span class="sxs-lookup"><span data-stu-id="4cb79-128">The class of the service instance.</span></span>|  
    |<span data-ttu-id="4cb79-129">**サービス インスタンス ID**</span><span class="sxs-lookup"><span data-stu-id="4cb79-129">**Service Instance ID**</span></span>|<span data-ttu-id="4cb79-130">サービス インスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="4cb79-130">The service instance ID.</span></span>|  
    |<span data-ttu-id="4cb79-131">**サービス名**</span><span class="sxs-lookup"><span data-stu-id="4cb79-131">**Service Name**</span></span>|<span data-ttu-id="4cb79-132">サービス インスタンスの名前。</span><span class="sxs-lookup"><span data-stu-id="4cb79-132">The name of the service instance.</span></span>|  
    |<span data-ttu-id="4cb79-133">**開始時刻**</span><span class="sxs-lookup"><span data-stu-id="4cb79-133">**Start Time**</span></span>|<span data-ttu-id="4cb79-134">サービス インスタンスの開始時刻。</span><span class="sxs-lookup"><span data-stu-id="4cb79-134">The start time of the service instance.</span></span>|  
    |<span data-ttu-id="4cb79-135">**状態**</span><span class="sxs-lookup"><span data-stu-id="4cb79-135">**State**</span></span>|<span data-ttu-id="4cb79-136">サービス インスタンスの状態。</span><span class="sxs-lookup"><span data-stu-id="4cb79-136">The state of the service instance.</span></span>|  
  
6.  <span data-ttu-id="4cb79-137">完了、 **値** 列に適切な選択範囲にすると、 **フィールド名** 列です。</span><span class="sxs-lookup"><span data-stu-id="4cb79-137">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  
  
7.  <span data-ttu-id="4cb79-138">完了することで、必要に応じてクエリに行を追加、 **フィールド名**, 、**演算子**, 、および **値** 列、およびクリック **クエリの実行**します。</span><span class="sxs-lookup"><span data-stu-id="4cb79-138">Continue adding additional lines to the query as appropriate by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cb79-139">参照</span><span class="sxs-lookup"><span data-stu-id="4cb79-139">See Also</span></span>  
 <span data-ttu-id="4cb79-140">[管理コンソールの [クエリ] タブの使用](../core/using-the-administration-console-query-tab.md)</span><span class="sxs-lookup"><span data-stu-id="4cb79-140">[Using the Administration Console Query Tab](../core/using-the-administration-console-query-tab.md)</span></span>