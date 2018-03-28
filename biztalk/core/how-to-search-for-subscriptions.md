---
title: サブスクリプションを検索する方法 |Microsoft ドキュメント
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f1830a4c1dddfa3dcfc2a1177b69410dd8ee0ac
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-search-for-subscriptions"></a><span data-ttu-id="9d3d4-102">サブスクリプションを検索する方法</span><span class="sxs-lookup"><span data-stu-id="9d3d4-102">How to Search for Subscriptions</span></span>
<span data-ttu-id="9d3d4-103">使用することができます、 **クエリ** サブスクリプションを検索するには、BizTalk Server 管理コンソールでタブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d3d4-103">You can use the **Query** tab in the BizTalk Server Administration Console to search for subscriptions.</span></span> <span data-ttu-id="9d3d4-104">これは、システム内に定義されているすべてのサブスクリプションを確認する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="9d3d4-104">This is useful when you want to review all of the subscriptions defined in the system.</span></span> <span data-ttu-id="9d3d4-105">ルーティング エラーのトラブルシューティングを行う際、構成が正しくないためにエラーの原因となっているサブスクリプションがあるかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="9d3d4-105">When troubleshooting routing failures, you can review subscriptions to see if any of them are improperly configured, thereby causing the routing failure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9d3d4-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="9d3d4-106">Prerequisites</span></span>  
 <span data-ttu-id="9d3d4-107">ここで示す手順を実行するには、BizTalk Server Operators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d3d4-107">To perform this procedure, you must be logged on as a member of the BizTalk Server Operators group.</span></span>  
  
### <a name="to-search-for-subscriptions"></a><span data-ttu-id="9d3d4-108">サブスクリプションを検索するには</span><span class="sxs-lookup"><span data-stu-id="9d3d4-108">To search for subscriptions</span></span>  
  
1.  <span data-ttu-id="9d3d4-109">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="9d3d4-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2.  <span data-ttu-id="9d3d4-110">コンソール ツリーで、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] を展開し、[BizTalk グループ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d3d4-110">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="9d3d4-111">詳細ペインでクリックして、 **新しいクエリ**  タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d3d4-111">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="9d3d4-112">**クエリ式** グループの **値** 列で、選択 **サブスクリプション** ドロップダウン リスト ボックスからです。</span><span class="sxs-lookup"><span data-stu-id="9d3d4-112">In the **Query Expression** group, in the **Value** column, select **Subscriptions** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="9d3d4-113">**フィールド名** 列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(**\***)、次の 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="9d3d4-113">In the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select one or more of the following:</span></span>  
  
    |<span data-ttu-id="9d3d4-114">アイテム</span><span class="sxs-lookup"><span data-stu-id="9d3d4-114">Item</span></span>|<span data-ttu-id="9d3d4-115">Description</span><span class="sxs-lookup"><span data-stu-id="9d3d4-115">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="9d3d4-116">**最大一致数**</span><span class="sxs-lookup"><span data-stu-id="9d3d4-116">**Maximum Matches**</span></span>|<span data-ttu-id="9d3d4-117">一致項目の表示数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d3d4-117">The number of matches to display.</span></span>|  
    |<span data-ttu-id="9d3d4-118">**サービス インスタンス ID**</span><span class="sxs-lookup"><span data-stu-id="9d3d4-118">**Service Instance ID**</span></span>|<span data-ttu-id="9d3d4-119">サブスクリプションをサービス インスタンス ID でフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="9d3d4-119">You can filter subscriptions by service instance ID.</span></span>|  
    |<span data-ttu-id="9d3d4-120">**サービス名**</span><span class="sxs-lookup"><span data-stu-id="9d3d4-120">**Service Name**</span></span>|<span data-ttu-id="9d3d4-121">サブスクリプションをサービス名でフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="9d3d4-121">You can filter subscriptions by service name.</span></span>|  
    |<span data-ttu-id="9d3d4-122">**サブスクリプションの種類**</span><span class="sxs-lookup"><span data-stu-id="9d3d4-122">**Subscription Type**</span></span>|<span data-ttu-id="9d3d4-123">サブスクリプションをアクティベーションのサブスクリプションまたはインスタンスのサブスクリプションでフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="9d3d4-123">You can filter subscriptions by Activation Subscription or Instance Subscription.</span></span>|  
  
6.  <span data-ttu-id="9d3d4-124">完了、 **値** 列に適切な選択範囲にすると、 **フィールド名** 列です。</span><span class="sxs-lookup"><span data-stu-id="9d3d4-124">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  
  
7.  <span data-ttu-id="9d3d4-125">完了することで、必要に応じてクエリに行を追加、 **フィールド名**, 、**演算子**, 、および **値** 列、およびクリック **クエリの実行**します。</span><span class="sxs-lookup"><span data-stu-id="9d3d4-125">Continue adding additional lines to the query as appropriate, by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d3d4-126">参照</span><span class="sxs-lookup"><span data-stu-id="9d3d4-126">See Also</span></span>  
 <span data-ttu-id="9d3d4-127">[管理コンソールの [クエリ] タブの使用](../core/using-the-administration-console-query-tab.md)</span><span class="sxs-lookup"><span data-stu-id="9d3d4-127">[Using the Administration Console Query Tab](../core/using-the-administration-console-query-tab.md)</span></span>