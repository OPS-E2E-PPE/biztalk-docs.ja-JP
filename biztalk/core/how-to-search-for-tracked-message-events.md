---
title: 追跡メッセージ イベントを検索する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18df4cf7-c307-4175-926c-9be9f30b29ed
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6a3597d0d68dbd79de6c23e7b6d4b222b9c8376
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "25973440"
---
# <a name="how-to-search-for-tracked-message-events"></a><span data-ttu-id="eeeb7-102">追跡メッセージ イベントを検索する方法</span><span class="sxs-lookup"><span data-stu-id="eeeb7-102">How to Search for Tracked Message Events</span></span>
<span data-ttu-id="eeeb7-103">使用することができます、**新しいクエリ** タブで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]追跡メッセージ イベントの管理コンソールを検索します。</span><span class="sxs-lookup"><span data-stu-id="eeeb7-103">You can use the **New Query** tab in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to search for tracked message events.</span></span>  <span data-ttu-id="eeeb7-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールから、メッセージ本文とメッセージ プロパティの追跡を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="eeeb7-104">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console you can enable message body and message property tracking.</span></span> <span data-ttu-id="eeeb7-105">クエリ結果ペインで、メッセージ イベントに関する情報を表示できます。表示内容には、スキーマ情報、イベントの種類、サービス インスタンス ID、および生成されたメッセージの昇格させたすべてのプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="eeeb7-105">In the Query Results pane you can view information about the message event, including schema information, event type, service instance ID, and all the promoted properties for the generated message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eeeb7-106">実際のメッセージ本文を表示するために呼び出すことができます、 **メッセージの詳細** コンテキスト メニューのおよび移動メッセージ部分 タブをクリックするか、またはメッセージを保存結果のリストから呼び出すことによって表示 **をファイルに保存** 、コンテキスト メニューからです。</span><span class="sxs-lookup"><span data-stu-id="eeeb7-106">In order to view the actual message body, you can invoke the **Message Details** context menu and go to the “Message Parts” tab, or save the message from the result list view by invoking **Save to File** from the context menu.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="eeeb7-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="eeeb7-107">Prerequisites</span></span>  
 <span data-ttu-id="eeeb7-108">ここで示す手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eeeb7-108">To perform this procedure, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators group.</span></span>  
  
### <a name="to-search-for-tracked-message-items"></a><span data-ttu-id="eeeb7-109">追跡対象のメッセージ項目を検索するには</span><span class="sxs-lookup"><span data-stu-id="eeeb7-109">To search for tracked message items</span></span>  
  
1.  <span data-ttu-id="eeeb7-110">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="eeeb7-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2.  <span data-ttu-id="eeeb7-111">コンソール ツリーで  **BizTalk Server 管理コンソール**, 、し、BizTalk グループ をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eeeb7-111">In the console tree, expand **BizTalk Server Administration**, and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="eeeb7-112">詳細ペインでクリックして、 **新しいクエリ**  タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="eeeb7-112">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="eeeb7-113">**クエリ式** グループの **値** 列で、選択 **追跡メッセージ イベント** ドロップダウン リスト ボックスからです。</span><span class="sxs-lookup"><span data-stu-id="eeeb7-113">In the **Query Expression** group, in the **Value** column, select **Tracked Message Events** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="eeeb7-114">**フィールド名** 列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(**\***)、次の 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="eeeb7-114">In the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select one or more of the following:</span></span>  
  
    |<span data-ttu-id="eeeb7-115">アイテム</span><span class="sxs-lookup"><span data-stu-id="eeeb7-115">Item</span></span>|<span data-ttu-id="eeeb7-116">Description</span><span class="sxs-lookup"><span data-stu-id="eeeb7-116">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="eeeb7-117">**作成日時**</span><span class="sxs-lookup"><span data-stu-id="eeeb7-117">**Creation Time**</span></span>|<span data-ttu-id="eeeb7-118">メッセージが作成された時刻。</span><span class="sxs-lookup"><span data-stu-id="eeeb7-118">The time the message was created.</span></span>|  
    |<span data-ttu-id="eeeb7-119">**イベントの種類**</span><span class="sxs-lookup"><span data-stu-id="eeeb7-119">**Event Type**</span></span>|<span data-ttu-id="eeeb7-120">追跡対象のイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="eeeb7-120">The type of event being tracked.</span></span>|  
    |<span data-ttu-id="eeeb7-121">**最大一致数**</span><span class="sxs-lookup"><span data-stu-id="eeeb7-121">**Maximum Matches**</span></span>|<span data-ttu-id="eeeb7-122">一致項目の表示数を指定します。</span><span class="sxs-lookup"><span data-stu-id="eeeb7-122">The number of matches to display.</span></span>|  
    |<span data-ttu-id="eeeb7-123">**パーティ**</span><span class="sxs-lookup"><span data-stu-id="eeeb7-123">**Party**</span></span>|<span data-ttu-id="eeeb7-124">メッセージを送信した組織。</span><span class="sxs-lookup"><span data-stu-id="eeeb7-124">The organization that sent the message.</span></span>|  
    |<span data-ttu-id="eeeb7-125">**ポート**</span><span class="sxs-lookup"><span data-stu-id="eeeb7-125">**Port**</span></span>|<span data-ttu-id="eeeb7-126">メッセージの処理に使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="eeeb7-126">The port used to process the message.</span></span>|  
    |<span data-ttu-id="eeeb7-127">**スキーマ名**</span><span class="sxs-lookup"><span data-stu-id="eeeb7-127">**Schema Name**</span></span>|<span data-ttu-id="eeeb7-128">メッセージで使用されているスキーマの名前。</span><span class="sxs-lookup"><span data-stu-id="eeeb7-128">Name of the schema used by the message.</span></span>|  
    |<span data-ttu-id="eeeb7-129">**サービス インスタンス ID**</span><span class="sxs-lookup"><span data-stu-id="eeeb7-129">**Service Instance ID**</span></span>|<span data-ttu-id="eeeb7-130">メッセージに使用されているサービス インスタンス ID。</span><span class="sxs-lookup"><span data-stu-id="eeeb7-130">The service instance ID used for the message.</span></span>|  
    |<span data-ttu-id="eeeb7-131">**URI**</span><span class="sxs-lookup"><span data-stu-id="eeeb7-131">**URI**</span></span>|<span data-ttu-id="eeeb7-132">メッセージに使用されている URI。</span><span class="sxs-lookup"><span data-stu-id="eeeb7-132">The URI used for the message.</span></span>|  
    |<span data-ttu-id="eeeb7-133">**\<追跡対象のプロパティのスキーマ名を選択します。\>**</span><span class="sxs-lookup"><span data-stu-id="eeeb7-133">**\<Select a Schema Name for Tracked Properties\>**</span></span>|<span data-ttu-id="eeeb7-134">スキーマを選択すると、そのスキーマ内の任意の昇格させたプロパティをクエリで使用できます。</span><span class="sxs-lookup"><span data-stu-id="eeeb7-134">When you select a schema, any promoted properties in that schema are eligible to be used in the query.</span></span>|  
  
6.  <span data-ttu-id="eeeb7-135">完了、 **値** 列に適切な選択範囲にすると、 **フィールド名** 列です。</span><span class="sxs-lookup"><span data-stu-id="eeeb7-135">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  
  
7.  <span data-ttu-id="eeeb7-136">完了することで、必要に応じてクエリに行を追加、 **フィールド名**, 、**演算子**, 、および **値** 列、およびクリック **クエリの実行**します。</span><span class="sxs-lookup"><span data-stu-id="eeeb7-136">Continue adding additional lines to the query as appropriate by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeeb7-137">参照</span><span class="sxs-lookup"><span data-stu-id="eeeb7-137">See Also</span></span>  
 <span data-ttu-id="eeeb7-138">[管理コンソールの [クエリ] タブの使用](../core/using-the-administration-console-query-tab.md)</span><span class="sxs-lookup"><span data-stu-id="eeeb7-138">[Using the Administration Console Query Tab](../core/using-the-administration-console-query-tab.md)</span></span>