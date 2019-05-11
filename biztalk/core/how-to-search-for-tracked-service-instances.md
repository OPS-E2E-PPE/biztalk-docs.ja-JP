---
title: 追跡サービス インスタンスを検索する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6337df9-8c2e-4d4a-a64b-cc040f83bd91
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1ff8801c272859e6a138fcb1e4e618226de10a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383978"
---
# <a name="how-to-search-for-tracked-service-instances"></a><span data-ttu-id="a9a71-102">追跡サービス インスタンスを検索する方法</span><span class="sxs-lookup"><span data-stu-id="a9a71-102">How to Search for Tracked Service Instances</span></span>
<span data-ttu-id="a9a71-103">使用することができます、**クエリ** タブで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールのすべての追跡サービス インスタンスを検索します。</span><span class="sxs-lookup"><span data-stu-id="a9a71-103">You can use the **Query** tab in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to search for all tracked service instances.</span></span> <span data-ttu-id="a9a71-104">サービス インスタンスを検索するには、サービス クラス、ホスト名、エラー コード、およびサービス インスタンスの状態の有効期間、名、またはインスタンス ID の開始および終了時刻、アセンブリのバージョンと名前で検索することができます。</span><span class="sxs-lookup"><span data-stu-id="a9a71-104">To locate service instances, you can search on the name and version of the assembly, the start and end times of its lifetime, the name or instance ID of the service class, host name, error code, and the state of the service instance.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="a9a71-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="a9a71-105">Prerequisites</span></span>  
 <span data-ttu-id="a9a71-106">この手順を実行する必要がありますがログオンしてのメンバーとして、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators グループ。</span><span class="sxs-lookup"><span data-stu-id="a9a71-106">To perform this procedure, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators group.</span></span>  

### <a name="to-search-for-tracked-service-instances"></a><span data-ttu-id="a9a71-107">追跡サービス インスタンスを検索するには</span><span class="sxs-lookup"><span data-stu-id="a9a71-107">To search for tracked service instances</span></span>  

1. <span data-ttu-id="a9a71-108">クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a9a71-108">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  

2. <span data-ttu-id="a9a71-109">コンソール ツリーで、展開**BizTalk Server 管理**、し、[BizTalk グループ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9a71-109">In the console tree, expand **BizTalk Server Administration**, and then click the BizTalk group.</span></span>  

3. <span data-ttu-id="a9a71-110">詳細ウィンドウでをクリックして、**新しいクエリ**タブ。</span><span class="sxs-lookup"><span data-stu-id="a9a71-110">In the details pane, click the **New Query** tab.</span></span>  

4. <span data-ttu-id="a9a71-111">**クエリ式**グループに、**値**列で、**追跡サービス インスタンス**ドロップダウン リスト ボックスから。</span><span class="sxs-lookup"><span data-stu-id="a9a71-111">In the **Query Expression** group, in the **Value** column, select **Tracked Service Instances** from the drop-down list box.</span></span>  

5. <span data-ttu-id="a9a71-112">**フィールド名**列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(\* *\\* \* \*)、次の 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="a9a71-112">In the **Field Name** column, in the empty drop-down list box next to the asterisk (\*\*\\*\*\*), select one or more of the following:</span></span>  


   |          <span data-ttu-id="a9a71-113">アイテム</span><span class="sxs-lookup"><span data-stu-id="a9a71-113">Item</span></span>           |                     <span data-ttu-id="a9a71-114">説明</span><span class="sxs-lookup"><span data-stu-id="a9a71-114">Description</span></span>                      |
   |-------------------------|------------------------------------------------------|
   |    <span data-ttu-id="a9a71-115">**アセンブリ名**</span><span class="sxs-lookup"><span data-stu-id="a9a71-115">**Assembly Name**</span></span>    |    <span data-ttu-id="a9a71-116">サービス インスタンスのアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="a9a71-116">Name of the assembly for the service instance.</span></span>    |
   |  <span data-ttu-id="a9a71-117">**アセンブリのバージョン**</span><span class="sxs-lookup"><span data-stu-id="a9a71-117">**Assembly Version**</span></span>   |           <span data-ttu-id="a9a71-118">サービス インスタンスのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="a9a71-118">Version of the service instance.</span></span>           |
   |      <span data-ttu-id="a9a71-119">**[終了時刻]**</span><span class="sxs-lookup"><span data-stu-id="a9a71-119">**End Time**</span></span>       |          <span data-ttu-id="a9a71-120">サービス インスタンスの終了時刻。</span><span class="sxs-lookup"><span data-stu-id="a9a71-120">End time of the service instance.</span></span>           |
   |     <span data-ttu-id="a9a71-121">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="a9a71-121">**Error Code**</span></span>      | <span data-ttu-id="a9a71-122">サービス インスタンスに関連付けられたエラー コード。</span><span class="sxs-lookup"><span data-stu-id="a9a71-122">Any error code associated with the service instance.</span></span> |
   |      <span data-ttu-id="a9a71-123">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="a9a71-123">**Host Name**</span></span>      |        <span data-ttu-id="a9a71-124">サービス インスタンスのホスト名。</span><span class="sxs-lookup"><span data-stu-id="a9a71-124">The host name of the service instance.</span></span>        |
   |   <span data-ttu-id="a9a71-125">**最大一致数**</span><span class="sxs-lookup"><span data-stu-id="a9a71-125">**Maximum Matches**</span></span>   |          <span data-ttu-id="a9a71-126">表示する一致の数。</span><span class="sxs-lookup"><span data-stu-id="a9a71-126">The number of matches to display.</span></span>           |
   |    <span data-ttu-id="a9a71-127">**サービス クラス**</span><span class="sxs-lookup"><span data-stu-id="a9a71-127">**Service Class**</span></span>    |          <span data-ttu-id="a9a71-128">サービス インスタンスのクラスです。</span><span class="sxs-lookup"><span data-stu-id="a9a71-128">The class of the service instance.</span></span>          |
   | <span data-ttu-id="a9a71-129">**サービス インスタンス ID**</span><span class="sxs-lookup"><span data-stu-id="a9a71-129">**Service Instance ID**</span></span> |               <span data-ttu-id="a9a71-130">サービス インスタンス id。</span><span class="sxs-lookup"><span data-stu-id="a9a71-130">The service instance ID.</span></span>               |
   |    <span data-ttu-id="a9a71-131">**[サービス名]**</span><span class="sxs-lookup"><span data-stu-id="a9a71-131">**Service Name**</span></span>     |          <span data-ttu-id="a9a71-132">サービス インスタンスの名前。</span><span class="sxs-lookup"><span data-stu-id="a9a71-132">The name of the service instance.</span></span>           |
   |     <span data-ttu-id="a9a71-133">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="a9a71-133">**Start Time**</span></span>      |       <span data-ttu-id="a9a71-134">サービス インスタンスの開始時刻。</span><span class="sxs-lookup"><span data-stu-id="a9a71-134">The start time of the service instance.</span></span>        |
   |        <span data-ttu-id="a9a71-135">**State**</span><span class="sxs-lookup"><span data-stu-id="a9a71-135">**State**</span></span>        |          <span data-ttu-id="a9a71-136">サービス インスタンスの状態。</span><span class="sxs-lookup"><span data-stu-id="a9a71-136">The state of the service instance.</span></span>          |


6. <span data-ttu-id="a9a71-137">完了、**値**で行った選択の適切な列、**フィールド名**列。</span><span class="sxs-lookup"><span data-stu-id="a9a71-137">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  

7. <span data-ttu-id="a9a71-138">適切なクエリを実行して行を追加、**フィールド名**、**演算子**、および**値**列、およびクリック**実行クエリ**します。</span><span class="sxs-lookup"><span data-stu-id="a9a71-138">Continue adding additional lines to the query as appropriate by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="a9a71-139">参照</span><span class="sxs-lookup"><span data-stu-id="a9a71-139">See Also</span></span>  
 <span data-ttu-id="a9a71-140">[管理コンソールの [クエリ] タブの使用](../core/using-the-administration-console-query-tab.md)</span><span class="sxs-lookup"><span data-stu-id="a9a71-140">[Using the Administration Console Query Tab](../core/using-the-administration-console-query-tab.md)</span></span>