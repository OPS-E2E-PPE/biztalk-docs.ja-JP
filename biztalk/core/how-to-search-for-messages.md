---
title: "メッセージを検索する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, viewing
- messages, searching
- Query tab [Administration Console], searching
- Query tab [Administration Console], messages
ms.assetid: c751d23f-913a-4325-81da-a36d61c07e8b
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5443cc021bd5f97621f44d295432c99834bdaed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-search-for-messages"></a><span data-ttu-id="eda1b-102">メッセージを検索する方法</span><span class="sxs-lookup"><span data-stu-id="eda1b-102">How to Search for Messages</span></span>
<span data-ttu-id="eda1b-103">使用することができます、**クエリ** タブでメッセージの特定のクラスを検索するには、BizTalk Server 管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="eda1b-103">You can use the **Query** tab in the BizTalk Server Administration Console to search for a specific class of messages.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="eda1b-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="eda1b-104">Prerequisites</span></span>  
 <span data-ttu-id="eda1b-105">ここで示す手順を実行するには、BizTalk Server Operators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eda1b-105">To perform this procedure, you must be logged on as a member of the BizTalk Server Operators group.</span></span>  
  
### <a name="to-search-for-messages"></a><span data-ttu-id="eda1b-106">メッセージを検索するには</span><span class="sxs-lookup"><span data-stu-id="eda1b-106">To search for messages</span></span>  
  
1.  <span data-ttu-id="eda1b-107">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="eda1b-107">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="eda1b-108">コンソール ツリーで、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] を展開し、[BizTalk グループ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eda1b-108">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="eda1b-109">詳細ウィンドウで、をクリックして、**新しいクエリ**タブです。</span><span class="sxs-lookup"><span data-stu-id="eda1b-109">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="eda1b-110">**クエリ式**グループにおいて、**値**列で、選択**メッセージ**ドロップダウン リスト ボックスからです。</span><span class="sxs-lookup"><span data-stu-id="eda1b-110">In the **Query Expression** group, in the **Value** column, select **Messages** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="eda1b-111">**フィールド名**列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(**\***)、次の 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="eda1b-111">In the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select one or more of the following:</span></span>  
  
    |<span data-ttu-id="eda1b-112">アイテム</span><span class="sxs-lookup"><span data-stu-id="eda1b-112">Item</span></span>|<span data-ttu-id="eda1b-113">Description</span><span class="sxs-lookup"><span data-stu-id="eda1b-113">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="eda1b-114">**作成日時**</span><span class="sxs-lookup"><span data-stu-id="eda1b-114">**Creation Time**</span></span>|<span data-ttu-id="eda1b-115">指定した日時の前または後に作成されたメッセージを検索します。</span><span class="sxs-lookup"><span data-stu-id="eda1b-115">Find messages created before or after the specified date.</span></span>|  
    |<span data-ttu-id="eda1b-116">**エラー アダプター**</span><span class="sxs-lookup"><span data-stu-id="eda1b-116">**Error Adapter**</span></span>|<span data-ttu-id="eda1b-117">グループ化できますまたはアダプターの種類別にメッセージをフィルター処理: ファイル、FTP、HTTP、MQSeries、MSMQ、POP3、SMTP、SOAP、または Windows SharePoint Services です。</span><span class="sxs-lookup"><span data-stu-id="eda1b-117">You can group or filter messages by adapter type: FILE, FTP, HTTP, MQSeries, MSMQ, POP3, SMTP, SOAP, or Windows SharePoint Services.</span></span>|  
    |<span data-ttu-id="eda1b-118">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="eda1b-118">**Error Code**</span></span>|<span data-ttu-id="eda1b-119">メッセージをエラー コードでグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="eda1b-119">You can group or filter messages by error code.</span></span>|  
    |<span data-ttu-id="eda1b-120">**エラーの説明**</span><span class="sxs-lookup"><span data-stu-id="eda1b-120">**Error Description**</span></span>|<span data-ttu-id="eda1b-121">メッセージをエラーの説明でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="eda1b-121">You can group or filter messages by error description.</span></span>|  
    |<span data-ttu-id="eda1b-122">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="eda1b-122">**Host Name**</span></span>|<span data-ttu-id="eda1b-123">メッセージをホスト名でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="eda1b-123">You can group or filter messages by host name.</span></span>|  
    |<span data-ttu-id="eda1b-124">**インスタンスの状態**</span><span class="sxs-lookup"><span data-stu-id="eda1b-124">**Instance Status**</span></span>|<span data-ttu-id="eda1b-125">メッセージを参照しているサービス インスタンスの状態です。</span><span class="sxs-lookup"><span data-stu-id="eda1b-125">The status of the service instance referencing the message.</span></span> <span data-ttu-id="eda1b-126">すべてのインスタンスの次の種類を検索することができますすべての実行中のインスタンス、中断されたすべてのインスタンス、アクティブなインスタンス、退避済みのインスタンス、実行するための準備完了のインスタンス、スケジュール済みのインスタンス、再開不可のインスタンスが中断または一時停止、再開可能な状態。インスタンス。</span><span class="sxs-lookup"><span data-stu-id="eda1b-126">You can search for all of the following types of instances: all running instances, all suspended instances, active instances, dehydrated instances, ready-to-run instances, scheduled instances, suspended but not resumable instances, or suspended and resumable instances.</span></span>|  
    |<span data-ttu-id="eda1b-127">**最大一致数**</span><span class="sxs-lookup"><span data-stu-id="eda1b-127">**Maximum Matches**</span></span>|<span data-ttu-id="eda1b-128">一致項目の表示数を指定します。</span><span class="sxs-lookup"><span data-stu-id="eda1b-128">The number of matches to display.</span></span>|  
    |<span data-ttu-id="eda1b-129">**メッセージ ID**</span><span class="sxs-lookup"><span data-stu-id="eda1b-129">**Message ID**</span></span>|<span data-ttu-id="eda1b-130">メッセージをメッセージ ID でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="eda1b-130">You can group or filter messages by message ID.</span></span>|  
    |<span data-ttu-id="eda1b-131">**メッセージの状態**</span><span class="sxs-lookup"><span data-stu-id="eda1b-131">**Message Status**</span></span>|<span data-ttu-id="eda1b-132">消費済み、処理中、中断、中断 (再開不可)、中断 (再開可能)、キューに登録済み、キューに登録済み (処理の待機中)、キューに登録済み (配信スケジュール済み)、およびキューに登録済み (再試行の待機中) の状態のメッセージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="eda1b-132">You can search for messages with consumed, in process, suspended, suspended but not resumable, suspended and resumable, queued, queued but awaiting processing, queued but scheduled for later delivery, and queued but waiting to retry.</span></span>|  
    |<span data-ttu-id="eda1b-133">**メッセージの種類**</span><span class="sxs-lookup"><span data-stu-id="eda1b-133">**Message Type**</span></span>|<span data-ttu-id="eda1b-134">メッセージをメッセージの種類でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="eda1b-134">You can group or filter messages by message type.</span></span>|  
    |<span data-ttu-id="eda1b-135">**サービス クラス**</span><span class="sxs-lookup"><span data-stu-id="eda1b-135">**Service Class**</span></span>|<span data-ttu-id="eda1b-136">[分離アダプター]、[メッセージング]、[メッセージング、分離アダプター]、[MSMQT]、[オーケストレーション]、または [ルーティング エラー報告] を指定して検索できます。</span><span class="sxs-lookup"><span data-stu-id="eda1b-136">You can search for isolated adapters; messaging; messaging, and isolated adapters; MSMQT; Orchestration; or Routing Failure Report.</span></span>|  
    |<span data-ttu-id="eda1b-137">**サービス インスタンス ID**</span><span class="sxs-lookup"><span data-stu-id="eda1b-137">**Service Instance ID**</span></span>|<span data-ttu-id="eda1b-138">メッセージをサービス インスタンス ID でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="eda1b-138">You can group or filter messages by service instance ID.</span></span>|  
    |<span data-ttu-id="eda1b-139">**サービス名**</span><span class="sxs-lookup"><span data-stu-id="eda1b-139">**Service Name**</span></span>|<span data-ttu-id="eda1b-140">メッセージをサービス名でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="eda1b-140">You can group or filter messages by service name.</span></span>|  
    |<span data-ttu-id="eda1b-141">**サービスの種類 ID**</span><span class="sxs-lookup"><span data-stu-id="eda1b-141">**Service Type ID**</span></span>|<span data-ttu-id="eda1b-142">メッセージをサービスの種類 ID でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="eda1b-142">You can group or filter messages by service type ID.</span></span>|  
    |<span data-ttu-id="eda1b-143">**URI**</span><span class="sxs-lookup"><span data-stu-id="eda1b-143">**URI**</span></span>|<span data-ttu-id="eda1b-144">メッセージを URI でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="eda1b-144">You can group or filter messages by URI.</span></span>|  
  
6.  <span data-ttu-id="eda1b-145">完了、**値**で行う選択範囲の適切な列、**フィールド名**列です。</span><span class="sxs-lookup"><span data-stu-id="eda1b-145">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  
  
7.  <span data-ttu-id="eda1b-146">実行し、必要に応じて、クエリに行を追加、**フィールド名**、**演算子**、および**値**列、およびクリック**実行クエリ**です。</span><span class="sxs-lookup"><span data-stu-id="eda1b-146">Continue adding additional lines to the query as appropriate, by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eda1b-147">参照</span><span class="sxs-lookup"><span data-stu-id="eda1b-147">See Also</span></span>  
 <span data-ttu-id="eda1b-148">[管理コンソールの [クエリ] タブを使用します。](../core/using-the-administration-console-query-tab.md)</span><span class="sxs-lookup"><span data-stu-id="eda1b-148">[Using the Administration Console Query Tab](../core/using-the-administration-console-query-tab.md)</span></span>