---
title: メッセージを検索する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, viewing
- messages, searching
- Query tab [Administration Console], searching
- Query tab [Administration Console], messages
ms.assetid: c751d23f-913a-4325-81da-a36d61c07e8b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5443cc021bd5f97621f44d295432c99834bdaed
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "22255282"
---
# <a name="how-to-search-for-messages"></a><span data-ttu-id="6fd35-102">メッセージを検索する方法</span><span class="sxs-lookup"><span data-stu-id="6fd35-102">How to Search for Messages</span></span>
<span data-ttu-id="6fd35-103">使用することができます、 **クエリ** メッセージの特定のクラスを検索するには、BizTalk Server 管理コンソールでタブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fd35-103">You can use the **Query** tab in the BizTalk Server Administration Console to search for a specific class of messages.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6fd35-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="6fd35-104">Prerequisites</span></span>  
 <span data-ttu-id="6fd35-105">ここで示す手順を実行するには、BizTalk Server Operators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fd35-105">To perform this procedure, you must be logged on as a member of the BizTalk Server Operators group.</span></span>  
  
### <a name="to-search-for-messages"></a><span data-ttu-id="6fd35-106">メッセージを検索するには</span><span class="sxs-lookup"><span data-stu-id="6fd35-106">To search for messages</span></span>  
  
1.  <span data-ttu-id="6fd35-107">をクリックして **開始**, 、 をクリックして **すべてのプログラム**, 、 をクリックして [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], 、 をクリックし、 **BizTalk Server 管理コンソール**します。</span><span class="sxs-lookup"><span data-stu-id="6fd35-107">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="6fd35-108">コンソール ツリーで、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] を展開し、[BizTalk グループ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fd35-108">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="6fd35-109">詳細ペインでクリックして、 **新しいクエリ**  タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fd35-109">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="6fd35-110">**クエリ式** グループの **値** 列で、選択 **メッセージ** ドロップダウン リスト ボックスからです。</span><span class="sxs-lookup"><span data-stu-id="6fd35-110">In the **Query Expression** group, in the **Value** column, select **Messages** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="6fd35-111">**フィールド名** 列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(**\***)、次の 1 つ以上選択します。</span><span class="sxs-lookup"><span data-stu-id="6fd35-111">In the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select one or more of the following:</span></span>  
  
    |<span data-ttu-id="6fd35-112">アイテム</span><span class="sxs-lookup"><span data-stu-id="6fd35-112">Item</span></span>|<span data-ttu-id="6fd35-113">Description</span><span class="sxs-lookup"><span data-stu-id="6fd35-113">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="6fd35-114">**作成日時**</span><span class="sxs-lookup"><span data-stu-id="6fd35-114">**Creation Time**</span></span>|<span data-ttu-id="6fd35-115">指定した日時の前または後に作成されたメッセージを検索します。</span><span class="sxs-lookup"><span data-stu-id="6fd35-115">Find messages created before or after the specified date.</span></span>|  
    |<span data-ttu-id="6fd35-116">**エラー アダプター**</span><span class="sxs-lookup"><span data-stu-id="6fd35-116">**Error Adapter**</span></span>|<span data-ttu-id="6fd35-117">グループ化することができますかアダプターの種類別にメッセージをフィルター処理: ファイル、FTP、HTTP、MQSeries、MSMQ、POP3、SMTP、SOAP、または Windows SharePoint Services です。</span><span class="sxs-lookup"><span data-stu-id="6fd35-117">You can group or filter messages by adapter type: FILE, FTP, HTTP, MQSeries, MSMQ, POP3, SMTP, SOAP, or Windows SharePoint Services.</span></span>|  
    |<span data-ttu-id="6fd35-118">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="6fd35-118">**Error Code**</span></span>|<span data-ttu-id="6fd35-119">メッセージをエラー コードでグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="6fd35-119">You can group or filter messages by error code.</span></span>|  
    |<span data-ttu-id="6fd35-120">**エラーの説明**</span><span class="sxs-lookup"><span data-stu-id="6fd35-120">**Error Description**</span></span>|<span data-ttu-id="6fd35-121">メッセージをエラーの説明でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="6fd35-121">You can group or filter messages by error description.</span></span>|  
    |<span data-ttu-id="6fd35-122">**ホスト名**</span><span class="sxs-lookup"><span data-stu-id="6fd35-122">**Host Name**</span></span>|<span data-ttu-id="6fd35-123">メッセージをホスト名でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="6fd35-123">You can group or filter messages by host name.</span></span>|  
    |<span data-ttu-id="6fd35-124">**インスタンスの状態**</span><span class="sxs-lookup"><span data-stu-id="6fd35-124">**Instance Status**</span></span>|<span data-ttu-id="6fd35-125">メッセージを参照しているサービス インスタンスの状態です。</span><span class="sxs-lookup"><span data-stu-id="6fd35-125">The status of the service instance referencing the message.</span></span> <span data-ttu-id="6fd35-126">すべてのインスタンスの次の種類を検索することができます。 すべての実行中のインスタンス、中断されたすべてのインスタンス、アクティブなインスタンス、退避済みのインスタンス、すぐに実行インスタンス、スケジュール済みのインスタンス、中断、再開不可のインスタンスまたは一時停止、再開可能なインスタンス。</span><span class="sxs-lookup"><span data-stu-id="6fd35-126">You can search for all of the following types of instances: all running instances, all suspended instances, active instances, dehydrated instances, ready-to-run instances, scheduled instances, suspended but not resumable instances, or suspended and resumable instances.</span></span>|  
    |<span data-ttu-id="6fd35-127">**最大一致数**</span><span class="sxs-lookup"><span data-stu-id="6fd35-127">**Maximum Matches**</span></span>|<span data-ttu-id="6fd35-128">一致項目の表示数を指定します。</span><span class="sxs-lookup"><span data-stu-id="6fd35-128">The number of matches to display.</span></span>|  
    |<span data-ttu-id="6fd35-129">**メッセージ ID**</span><span class="sxs-lookup"><span data-stu-id="6fd35-129">**Message ID**</span></span>|<span data-ttu-id="6fd35-130">メッセージをメッセージ ID でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="6fd35-130">You can group or filter messages by message ID.</span></span>|  
    |<span data-ttu-id="6fd35-131">**メッセージの状態**</span><span class="sxs-lookup"><span data-stu-id="6fd35-131">**Message Status**</span></span>|<span data-ttu-id="6fd35-132">消費済み、処理中、中断、中断 (再開不可)、中断 (再開可能)、キューに登録済み、キューに登録済み (処理の待機中)、キューに登録済み (配信スケジュール済み)、およびキューに登録済み (再試行の待機中) の状態のメッセージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="6fd35-132">You can search for messages with consumed, in process, suspended, suspended but not resumable, suspended and resumable, queued, queued but awaiting processing, queued but scheduled for later delivery, and queued but waiting to retry.</span></span>|  
    |<span data-ttu-id="6fd35-133">**メッセージの種類**</span><span class="sxs-lookup"><span data-stu-id="6fd35-133">**Message Type**</span></span>|<span data-ttu-id="6fd35-134">メッセージをメッセージの種類でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="6fd35-134">You can group or filter messages by message type.</span></span>|  
    |<span data-ttu-id="6fd35-135">**サービス クラス**</span><span class="sxs-lookup"><span data-stu-id="6fd35-135">**Service Class**</span></span>|<span data-ttu-id="6fd35-136">[分離アダプター]、[メッセージング]、[メッセージング、分離アダプター]、[MSMQT]、[オーケストレーション]、または [ルーティング エラー報告] を指定して検索できます。</span><span class="sxs-lookup"><span data-stu-id="6fd35-136">You can search for isolated adapters; messaging; messaging, and isolated adapters; MSMQT; Orchestration; or Routing Failure Report.</span></span>|  
    |<span data-ttu-id="6fd35-137">**サービス インスタンス ID**</span><span class="sxs-lookup"><span data-stu-id="6fd35-137">**Service Instance ID**</span></span>|<span data-ttu-id="6fd35-138">メッセージをサービス インスタンス ID でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="6fd35-138">You can group or filter messages by service instance ID.</span></span>|  
    |<span data-ttu-id="6fd35-139">**サービス名**</span><span class="sxs-lookup"><span data-stu-id="6fd35-139">**Service Name**</span></span>|<span data-ttu-id="6fd35-140">メッセージをサービス名でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="6fd35-140">You can group or filter messages by service name.</span></span>|  
    |<span data-ttu-id="6fd35-141">**サービスの種類 ID**</span><span class="sxs-lookup"><span data-stu-id="6fd35-141">**Service Type ID**</span></span>|<span data-ttu-id="6fd35-142">メッセージをサービスの種類 ID でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="6fd35-142">You can group or filter messages by service type ID.</span></span>|  
    |<span data-ttu-id="6fd35-143">**URI**</span><span class="sxs-lookup"><span data-stu-id="6fd35-143">**URI**</span></span>|<span data-ttu-id="6fd35-144">メッセージを URI でグループ化またはフィルター選択できます。</span><span class="sxs-lookup"><span data-stu-id="6fd35-144">You can group or filter messages by URI.</span></span>|  
  
6.  <span data-ttu-id="6fd35-145">完了、 **値** 列に適切な選択範囲にすると、 **フィールド名** 列です。</span><span class="sxs-lookup"><span data-stu-id="6fd35-145">Complete the **Value** column as appropriate for the selection you made in the **Field Name** column.</span></span>  
  
7.  <span data-ttu-id="6fd35-146">完了することで、必要に応じてクエリに行を追加、 **フィールド名**, 、**演算子**, 、および **値** 列、およびクリック **クエリの実行**します。</span><span class="sxs-lookup"><span data-stu-id="6fd35-146">Continue adding additional lines to the query as appropriate, by completing the **Field Name**, **Operator**, and **Values** columns, and then click **Run Query**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fd35-147">参照</span><span class="sxs-lookup"><span data-stu-id="6fd35-147">See Also</span></span>  
 <span data-ttu-id="6fd35-148">[管理コンソールの [クエリ] タブの使用](../core/using-the-administration-console-query-tab.md)</span><span class="sxs-lookup"><span data-stu-id="6fd35-148">[Using the Administration Console Query Tab](../core/using-the-administration-console-query-tab.md)</span></span>