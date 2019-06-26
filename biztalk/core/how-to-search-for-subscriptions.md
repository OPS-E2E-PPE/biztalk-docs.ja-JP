---
title: サブスクリプションを検索する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Query tab [Administration Console], subscriptions
- Query tab [Administration Console], searching
- subscriptions, viewing
- subscriptions, searching
ms.assetid: 95f8fd20-2750-412b-a67b-18976e7706e2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 475510273ec8d97c7aa848667967c6917fc2c61c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334801"
---
# <a name="how-to-search-for-subscriptions"></a><span data-ttu-id="14f3b-102">サブスクリプションを検索する方法</span><span class="sxs-lookup"><span data-stu-id="14f3b-102">How to Search for Subscriptions</span></span>
<span data-ttu-id="14f3b-103">使用することができます、**クエリ** タブでサブスクリプションを検索するには、BizTalk Server 管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="14f3b-103">You can use the **Query** tab in the BizTalk Server Administration Console to search for subscriptions.</span></span> <span data-ttu-id="14f3b-104">これは、すべてのシステムで定義されているサブスクリプションを確認する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="14f3b-104">This is useful when you want to review all of the subscriptions defined in the system.</span></span> <span data-ttu-id="14f3b-105">ルーティング エラーのトラブルシューティングを行うため、ルーティング エラーの原因と、かどうかこれらのいずれかが正しく構成されていない、表示するサブスクリプションを確認できます。</span><span class="sxs-lookup"><span data-stu-id="14f3b-105">When troubleshooting routing failures, you can review subscriptions to see if any of them are improperly configured, thereby causing the routing failure.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="14f3b-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="14f3b-106">Prerequisites</span></span>  
 <span data-ttu-id="14f3b-107">この手順を実行するには、BizTalk Server Operators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f3b-107">To perform this procedure, you must be logged on as a member of the BizTalk Server Operators group.</span></span>  

### <a name="to-search-for-subscriptions"></a><span data-ttu-id="14f3b-108">サブスクリプションを検索するには</span><span class="sxs-lookup"><span data-stu-id="14f3b-108">To search for subscriptions</span></span>  

1. <span data-ttu-id="14f3b-109">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="14f3b-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  

2. <span data-ttu-id="14f3b-110">コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、し、[BizTalk グループ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14f3b-110">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then click the BizTalk group.</span></span>  

3. <span data-ttu-id="14f3b-111">詳細ウィンドウでをクリックして、**新しいクエリ**タブ。</span><span class="sxs-lookup"><span data-stu-id="14f3b-111">In the details pane, click the **New Query** tab.</span></span>  

4. <span data-ttu-id="14f3b-112">**クエリ式**グループに、**値**列で、**サブスクリプション**ドロップダウン リスト ボックスから。</span><span class="sxs-lookup"><span data-stu-id="14f3b-112">In the **Query Expression** group, in the **Value** column, select **Subscriptions** from the drop-down list box.</span></span>  

5. <span data-ttu-id="14f3b-113">**フィールド名**列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(\* *\\* \* \*)、次の 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="14f3b-113">In the **Field Name** column, in the empty drop-down list box next to the asterisk (\*\*\\*\*\*), select one or more of the following:</span></span>  


   |          <span data-ttu-id="14f3b-114">アイテム</span><span class="sxs-lookup"><span data-stu-id="14f3b-114">Item</span></span>           |                                    <span data-ttu-id="14f3b-115">説明</span><span class="sxs-lookup"><span data-stu-id="14f3b-115">Description</span></span>                                    |
   |-------------------------|-----------------------------------------------------------------------------------|
   |   <span data-ttu-id="14f3b-116">**最大一致数**</span><span class="sxs-lookup"><span data-stu-id="14f3b-116">**Maximum Matches**</span></span>   |                         <span data-ttu-id="14f3b-117">表示する一致の数。</span><span class="sxs-lookup"><span data-stu-id="14f3b-117">The number of matches to display.</span></span>                         |
   | <span data-ttu-id="14f3b-118">**サービス インスタンス ID**</span><span class="sxs-lookup"><span data-stu-id="14f3b-118">**Service Instance ID**</span></span> |               <span data-ttu-id="14f3b-119">サービス インスタンス ID でサブスクリプションをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="14f3b-119">You can filter subscriptions by service instance ID.</span></span>                |
   |    <span data-ttu-id="14f3b-120">**[サービス名]**</span><span class="sxs-lookup"><span data-stu-id="14f3b-120">**Service Name**</span></span>     |                   <span data-ttu-id="14f3b-121">サブスクリプションは、サービス名でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="14f3b-121">You can filter subscriptions by service name.</span></span>                   |
   |  <span data-ttu-id="14f3b-122">**サブスクリプションの種類**</span><span class="sxs-lookup"><span data-stu-id="14f3b-122">**Subscription Type**</span></span>  | <span data-ttu-id="14f3b-123">アクティベーションのサブスクリプションでサブスクリプションをフィルターすることも、インスタンスのサブスクリプションを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="14f3b-123">You can filter subscriptions by Activation Subscription or Instance Subscription.</span></span> |


6. <span data-ttu-id="14f3b-124">完了、**値**で行った選択の適切な列、**フィールド名**列。</span><span class="sxs-lookup"><span data-stu-id="14f3b-124">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  

7. <span data-ttu-id="14f3b-125">実行して、必要に応じて、クエリに行を追加、**フィールド名**、**演算子**、および**値**列、およびクリック**実行クエリ**します。</span><span class="sxs-lookup"><span data-stu-id="14f3b-125">Continue adding additional lines to the query as appropriate, by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="14f3b-126">参照</span><span class="sxs-lookup"><span data-stu-id="14f3b-126">See Also</span></span>  
 <span data-ttu-id="14f3b-127">[管理コンソールの [クエリ] タブの使用](../core/using-the-administration-console-query-tab.md)</span><span class="sxs-lookup"><span data-stu-id="14f3b-127">[Using the Administration Console Query Tab](../core/using-the-administration-console-query-tab.md)</span></span>