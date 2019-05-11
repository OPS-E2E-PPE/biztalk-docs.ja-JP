---
title: 追跡メッセージ イベントを検索する方法 |Microsoft Docs
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
ms.openlocfilehash: fabfa18a4dda37d1d2e59361d74b4ecc147a1703
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334793"
---
# <a name="how-to-search-for-tracked-message-events"></a><span data-ttu-id="7b728-102">追跡メッセージ イベントを検索する方法</span><span class="sxs-lookup"><span data-stu-id="7b728-102">How to Search for Tracked Message Events</span></span>
<span data-ttu-id="7b728-103">使用することができます、**新しいクエリ** タブで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]追跡メッセージ イベントの管理コンソールを検索します。</span><span class="sxs-lookup"><span data-stu-id="7b728-103">You can use the **New Query** tab in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to search for tracked message events.</span></span>  <span data-ttu-id="7b728-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールのメッセージ本文とメッセージ プロパティの追跡を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7b728-104">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console you can enable message body and message property tracking.</span></span> <span data-ttu-id="7b728-105">クエリ結果ペインには、スキーマ情報、イベントの種類、サービス インスタンス ID に、生成されたメッセージのすべての昇格させたプロパティなど、メッセージ イベントに関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="7b728-105">In the Query Results pane you can view information about the message event, including schema information, event type, service instance ID, and all the promoted properties for the generated message.</span></span>  

> [!NOTE]
>  <span data-ttu-id="7b728-106">実際のメッセージ本文を表示するために呼び出すことができます、**メッセージの詳細**コンテキスト メニューのおよび移動メッセージ部分 タブをクリックまたはメッセージを保存、結果の一覧から呼び出すことによって表示**ファイルに保存**から、コンテキスト メニュー。</span><span class="sxs-lookup"><span data-stu-id="7b728-106">In order to view the actual message body, you can invoke the **Message Details** context menu and go to the “Message Parts” tab, or save the message from the result list view by invoking **Save to File** from the context menu.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="7b728-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="7b728-107">Prerequisites</span></span>  
 <span data-ttu-id="7b728-108">この手順を実行する必要がありますがログオンしてのメンバーとして、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators グループ。</span><span class="sxs-lookup"><span data-stu-id="7b728-108">To perform this procedure, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators group.</span></span>  

### <a name="to-search-for-tracked-message-items"></a><span data-ttu-id="7b728-109">追跡メッセージの項目を検索するには</span><span class="sxs-lookup"><span data-stu-id="7b728-109">To search for tracked message items</span></span>  

1. <span data-ttu-id="7b728-110">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7b728-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  

2. <span data-ttu-id="7b728-111">コンソール ツリーで、展開**BizTalk Server 管理**、し、[BizTalk グループ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b728-111">In the console tree, expand **BizTalk Server Administration**, and then click the BizTalk group.</span></span>  

3. <span data-ttu-id="7b728-112">詳細ウィンドウでをクリックして、**新しいクエリ**タブ。</span><span class="sxs-lookup"><span data-stu-id="7b728-112">In the details pane, click the **New Query** tab.</span></span>  

4. <span data-ttu-id="7b728-113">**クエリ式**グループに、**値**列で、**追跡メッセージ イベント**ドロップダウン リスト ボックスから。</span><span class="sxs-lookup"><span data-stu-id="7b728-113">In the **Query Expression** group, in the **Value** column, select **Tracked Message Events** from the drop-down list box.</span></span>  

5. <span data-ttu-id="7b728-114">**フィールド名**列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(\* *\\* \* \*)、次の 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="7b728-114">In the **Field Name** column, in the empty drop-down list box next to the asterisk (\*\*\\*\*\*), select one or more of the following:</span></span>  


   |                        <span data-ttu-id="7b728-115">アイテム</span><span class="sxs-lookup"><span data-stu-id="7b728-115">Item</span></span>                         |                                              <span data-ttu-id="7b728-116">説明</span><span class="sxs-lookup"><span data-stu-id="7b728-116">Description</span></span>                                               |
   |-----------------------------------------------------|--------------------------------------------------------------------------------------------------------|
   |                  <span data-ttu-id="7b728-117">**作成時刻**</span><span class="sxs-lookup"><span data-stu-id="7b728-117">**Creation Time**</span></span>                  |                                   <span data-ttu-id="7b728-118">メッセージが作成された時刻。</span><span class="sxs-lookup"><span data-stu-id="7b728-118">The time the message was created.</span></span>                                    |
   |                   <span data-ttu-id="7b728-119">**イベントの種類**</span><span class="sxs-lookup"><span data-stu-id="7b728-119">**Event Type**</span></span>                    |                                    <span data-ttu-id="7b728-120">追跡対象のイベントの種類。</span><span class="sxs-lookup"><span data-stu-id="7b728-120">The type of event being tracked.</span></span>                                    |
   |                 <span data-ttu-id="7b728-121">**最大一致数**</span><span class="sxs-lookup"><span data-stu-id="7b728-121">**Maximum Matches**</span></span>                 |                                   <span data-ttu-id="7b728-122">表示する一致の数。</span><span class="sxs-lookup"><span data-stu-id="7b728-122">The number of matches to display.</span></span>                                    |
   |                      <span data-ttu-id="7b728-123">**パーティ**</span><span class="sxs-lookup"><span data-stu-id="7b728-123">**Party**</span></span>                      |                                <span data-ttu-id="7b728-124">メッセージを送信した組織です。</span><span class="sxs-lookup"><span data-stu-id="7b728-124">The organization that sent the message.</span></span>                                 |
   |                      <span data-ttu-id="7b728-125">**[ポート]**</span><span class="sxs-lookup"><span data-stu-id="7b728-125">**Port**</span></span>                       |                                 <span data-ttu-id="7b728-126">メッセージの処理に使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="7b728-126">The port used to process the message.</span></span>                                  |
   |                   <span data-ttu-id="7b728-127">**スキーマ名**</span><span class="sxs-lookup"><span data-stu-id="7b728-127">**Schema Name**</span></span>                   |                                <span data-ttu-id="7b728-128">メッセージで使用されるスキーマの名前です。</span><span class="sxs-lookup"><span data-stu-id="7b728-128">Name of the schema used by the message.</span></span>                                 |
   |               <span data-ttu-id="7b728-129">**サービス インスタンス ID**</span><span class="sxs-lookup"><span data-stu-id="7b728-129">**Service Instance ID**</span></span>               |                             <span data-ttu-id="7b728-130">メッセージで使用するサービス インスタンスの ID。</span><span class="sxs-lookup"><span data-stu-id="7b728-130">The service instance ID used for the message.</span></span>                              |
   |                       <span data-ttu-id="7b728-131">**URI**</span><span class="sxs-lookup"><span data-stu-id="7b728-131">**URI**</span></span>                       |                                     <span data-ttu-id="7b728-132">メッセージで使用する URI。</span><span class="sxs-lookup"><span data-stu-id="7b728-132">The URI used for the message.</span></span>                                      |
   | <span data-ttu-id="7b728-133">**\<追跡対象プロパティのスキーマ名を選択します。\>**</span><span class="sxs-lookup"><span data-stu-id="7b728-133">**\<Select a Schema Name for Tracked Properties\>**</span></span> | <span data-ttu-id="7b728-134">スキーマを選択するときにそのスキーマで昇格させたプロパティは、クエリで使用可能なです。</span><span class="sxs-lookup"><span data-stu-id="7b728-134">When you select a schema, any promoted properties in that schema are eligible to be used in the query.</span></span> |


6. <span data-ttu-id="7b728-135">完了、**値**で行った選択の適切な列、**フィールド名**列。</span><span class="sxs-lookup"><span data-stu-id="7b728-135">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  

7. <span data-ttu-id="7b728-136">適切なクエリを実行して行を追加、**フィールド名**、**演算子**、および**値**列、およびクリック**実行クエリ**します。</span><span class="sxs-lookup"><span data-stu-id="7b728-136">Continue adding additional lines to the query as appropriate by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="7b728-137">参照</span><span class="sxs-lookup"><span data-stu-id="7b728-137">See Also</span></span>  
 <span data-ttu-id="7b728-138">[管理コンソールの [クエリ] タブの使用](../core/using-the-administration-console-query-tab.md)</span><span class="sxs-lookup"><span data-stu-id="7b728-138">[Using the Administration Console Query Tab](../core/using-the-administration-console-query-tab.md)</span></span>