---
title: トランスポートの送信ポートの詳細オプションを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, transport options [send ports]
- configuring, send ports
- send ports, transport options
- managing [send ports], configuring
- managing [send ports], transport options
ms.assetid: b0033e09-3c18-4e53-a470-e12978e61ba1
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86c61a7d77b3fbb4ebda539863223fa4ae12ed51
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340155"
---
# <a name="how-to-configure-transport-advanced-options-for-a-send-port"></a><span data-ttu-id="722b0-102">トランスポートを構成する方法の詳細、送信ポートのオプション</span><span class="sxs-lookup"><span data-stu-id="722b0-102">How to Configure Transport Advanced Options for a Send Port</span></span>
<span data-ttu-id="722b0-103">BizTalk Server 管理コンソールを使用して、トランスポートの送信ポートの詳細オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="722b0-103">Use the BizTalk Server Administration console to configure transport advanced options for a send port.</span></span> <span data-ttu-id="722b0-104">これらのオプションは、メッセージ エラー発生時のメッセージの送信ポートのサービス ウィンドウ スケジュールを再試行する回数などの送信ポートでメッセージを処理する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="722b0-104">These options determine how messages are handled by the send port, such as the number of times to retry sending messages on message failure and the service window schedule for the port.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="722b0-105">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** アダプターの種類に応じて、動的送信ポートで順次配送を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="722b0-105">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, you can enable ordered delivery for dynamic send ports, depending on the adapter type.</span></span> <span data-ttu-id="722b0-106">このオプションはのみアダプターの種類の使用可能なファイル アダプターや FTP アダプターなどの静的送信ポートの順次配送を保証する場所。</span><span class="sxs-lookup"><span data-stu-id="722b0-106">This option is only available for the adapter types where ordered delivery is guaranteed for static send ports, such as the File adapter, or the FTP adapter.</span></span>
> 
> <span data-ttu-id="722b0-107">6 つのメッセージを検討してください。M1、M2、M3、M4、M5、および M6 します。</span><span class="sxs-lookup"><span data-stu-id="722b0-107">Consider six messages: M1, M2, M3, M4, M5, and M6.</span></span> <span data-ttu-id="722b0-108">M1、M3、M5 については、ファイルの場所のものです。</span><span class="sxs-lookup"><span data-stu-id="722b0-108">M1, M3, M5 are meant for a file location.</span></span> <span data-ttu-id="722b0-109">M2、M4、および M6 については、FTP のものです。</span><span class="sxs-lookup"><span data-stu-id="722b0-109">M2, M4, and M6 are meant for FTP.</span></span> <span data-ttu-id="722b0-110">順次配送の動的送信ポートにより、M1、M3、および M5 が順序付けです。 確認してください。M2、M4、および M6 はそれぞれ並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="722b0-110">The ordered delivery dynamic send port makes sure that M1, M3, and M5 are ordered; and M2, M4, and M6 are ordered respectively.</span></span> 
> 
> <span data-ttu-id="722b0-111">順次配送をサポートしていないこれらのアダプター型の構成に使用できるすべての動的送信ポート プロパティはありません。</span><span class="sxs-lookup"><span data-stu-id="722b0-111">For those adapter types that don't support ordered delivery, there aren't any dynamic send port properties available to configure.</span></span> <span data-ttu-id="722b0-112">トランスポート オプションは、実行時に自動的に決定されます。</span><span class="sxs-lookup"><span data-stu-id="722b0-112">Their transport options are automatically determined at run time.</span></span>  
> 
> <span data-ttu-id="722b0-113">**以前のバージョンの BizTalk**動的ポートを使用する、トランスポートのオプションは実行時に自動的に決定するための構成に使用できる任意のプロパティはありません。</span><span class="sxs-lookup"><span data-stu-id="722b0-113">**For previous BizTalk versions** that use dynamic ports, there aren't any properties available to configure because the transport options are automatically determined at run time.</span></span>

  
## <a name="prerequisites"></a><span data-ttu-id="722b0-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="722b0-114">Prerequisites</span></span>  
 <span data-ttu-id="722b0-115">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="722b0-115">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="722b0-116">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="722b0-116">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="controlling-send-port-priority"></a><span data-ttu-id="722b0-117">送信ポートの優先度を制御します。</span><span class="sxs-lookup"><span data-stu-id="722b0-117">Controlling Send Port Priority</span></span>  
 <span data-ttu-id="722b0-118">トランスポートの詳細オプションの優先順位の設定は、メッセージがメッセージ ボックスから削除されます順序を制御します。</span><span class="sxs-lookup"><span data-stu-id="722b0-118">The Priority setting of the Transport Advanced Options controls the order in which messages are removed from the message box.</span></span> <span data-ttu-id="722b0-119">優先順位の高いポートより高い優先度のポートより重要なその他の送信を基準とした 1 つのホスト内のポート優先度の低いポートよりも先に処理されます。</span><span class="sxs-lookup"><span data-stu-id="722b0-119">Ports with a higher priority will be processed earlier than ports with a lower priority making the higher priority ports more important relative to other send ports within a single host.</span></span>  
  
 <span data-ttu-id="722b0-120">優先順位は低い応答時間は、特定の種類の要求を必要とするシナリオで役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="722b0-120">Priority is useful in scenarios requiring low response times for certain types of requests.</span></span> <span data-ttu-id="722b0-121">たとえば、複数ある場合は、通常の要求と対話型の要求を処理するためのさまざまなシステムに接続するポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="722b0-121">For example, if there are multiple send ports that connect to different systems for processing normal requests and interactive requests.</span></span> <span data-ttu-id="722b0-122">できるだけ早く処理されることを確認する対話型の要求が送信されたときに対話型の要求が短い応答時間を必要とします。</span><span class="sxs-lookup"><span data-stu-id="722b0-122">The interactive requests require a low response time, so when an interactive request is submitted, you want to ensure it is processed as soon as possible.</span></span>  
  
 <span data-ttu-id="722b0-123">BizTalk Server は、メッセージ ボックスに優先順位が異なるメッセージの処理に公平にしません。</span><span class="sxs-lookup"><span data-stu-id="722b0-123">BizTalk Server does not attempt to be fair in the processing of messages with different priorities in the message box.</span></span> <span data-ttu-id="722b0-124">同じ場合は、処理するときに、メッセージ ボックスに、2 つの異なる優先度を持つ項目の数を開始、優先順位の低い項目の処理のみすべて高優先度が処理されたアイテムの。</span><span class="sxs-lookup"><span data-stu-id="722b0-124">If there are equal numbers of items with two different priorities in the message box when processing begins, the lower priority items will be processed only after all high priority items have been processed.</span></span> <span data-ttu-id="722b0-125">優先度の高い項目のボリュームは、すばらしいが場合、は、優先度の低い項目は処理されない可能性が。</span><span class="sxs-lookup"><span data-stu-id="722b0-125">If the volume of high priority items is great, it is possible that items with a lower priority will never be processed.</span></span> <span data-ttu-id="722b0-126">つまり、優先順位の低い項目は、スタベーションが発生します。</span><span class="sxs-lookup"><span data-stu-id="722b0-126">In other words, the lower priority items will experience starvation.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="722b0-127">メッセージの枯渇のリスクを最小限に抑えるには、すべてのメッセージを処理するために現実的な負荷の下で、アプリケーションを十分にテストします。</span><span class="sxs-lookup"><span data-stu-id="722b0-127">To minimize the risk of message starvation, thoroughly test your application under realistic loads to ensure all messages are processed.</span></span> <span data-ttu-id="722b0-128">ソリューションをテストするエラーは、未処理のメッセージがあります。</span><span class="sxs-lookup"><span data-stu-id="722b0-128">Failure to test your solution may result in unprocessed messages.</span></span>  
  
 <span data-ttu-id="722b0-129">内部的には、BizTalk Server は、すべてのサブスクリプションに優先順位を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="722b0-129">Internally, BizTalk Server assigns a priority to every subscription.</span></span> <span data-ttu-id="722b0-130">優先度は 1 (最も高い優先度) から 10 (最も低い優先度) の任意の数であることができます。</span><span class="sxs-lookup"><span data-stu-id="722b0-130">Priority can be any number from 1 (highest priority) to 10 (lowest priority).</span></span> <span data-ttu-id="722b0-131">既定の優先度が 7 サブスクリプションとサブスクリプションを関連付けるための 5 をアクティブ化のためであるため、メッセージの関連付けは配信サブスクリプションをアクティブ化するよりも前。</span><span class="sxs-lookup"><span data-stu-id="722b0-131">Because the default priority is 7 for activating subscriptions and 5 for correlating subscriptions, correlating messages will be delivered earlier than activating subscriptions.</span></span>  
  
## <a name="configure-the-transport-options"></a><span data-ttu-id="722b0-132">トランスポート オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="722b0-132">Configure the transport options</span></span> 
  
1.  <span data-ttu-id="722b0-133">開いている**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="722b0-133">Open **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="722b0-134">BizTalk グループを展開し、BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="722b0-134">Expand the BizTalk group, and then expand your BizTalk application.</span></span>  
  
3.  <span data-ttu-id="722b0-135">選択**送信ポート**、構成、および選択し、送信ポートを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="722b0-135">Select **Send Ports**, right-click the send port to configure, and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="722b0-136">左側のウィンドウで次のように選択します。**トランスポートの詳細オプション**します。</span><span class="sxs-lookup"><span data-stu-id="722b0-136">In the left pane, select **Transport Advanced Options**.</span></span>  
  
5.  <span data-ttu-id="722b0-137">次の表に示すように、トランスポート オプションを構成し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="722b0-137">Configure the transport options as described in the following table, and then select **OK**.</span></span>  <span data-ttu-id="722b0-138">動的送信ポートでは、次のプロパティの一部のみです。</span><span class="sxs-lookup"><span data-stu-id="722b0-138">Only some of the following properties are available for dynamic send ports.</span></span>
  
    |<span data-ttu-id="722b0-139">プロパティ</span><span class="sxs-lookup"><span data-stu-id="722b0-139">Use this</span></span>|<span data-ttu-id="722b0-140">目的</span><span class="sxs-lookup"><span data-stu-id="722b0-140">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="722b0-141">**再試行の回数**</span><span class="sxs-lookup"><span data-stu-id="722b0-141">**Retry count**</span></span>|<span data-ttu-id="722b0-142">メッセージのエラーでメッセージを再送信する送信ポートの回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="722b0-142">Specify the number of times for the send port to resend a message on message failure.</span></span> <span data-ttu-id="722b0-143">既定値は 3 です。許容範囲は 0 ~ 1,000 です。</span><span class="sxs-lookup"><span data-stu-id="722b0-143">The default is 3; the allowed range is from 0 through 1,000.</span></span>|  
    |<span data-ttu-id="722b0-144">**再試行の間隔**</span><span class="sxs-lookup"><span data-stu-id="722b0-144">**Retry interval**</span></span>|<span data-ttu-id="722b0-145">メッセージの再送を試みる間隔を分単位で間隔を指定します。</span><span class="sxs-lookup"><span data-stu-id="722b0-145">Specify the interval in minutes between message resend attempts.</span></span> <span data-ttu-id="722b0-146">既定値は 5 です。許容範囲は 0 ~ 525,600 します。</span><span class="sxs-lookup"><span data-stu-id="722b0-146">The default is 5; the allowed range is from 0 through 525,600.</span></span>|  
    |<span data-ttu-id="722b0-147">**[Priority]**</span><span class="sxs-lookup"><span data-stu-id="722b0-147">**Priority**</span></span>|<span data-ttu-id="722b0-148">再送の優先順位を設定します。</span><span class="sxs-lookup"><span data-stu-id="722b0-148">Set the priority of the resend attempt.</span></span>|  
    |<span data-ttu-id="722b0-149">**順次配送**</span><span class="sxs-lookup"><span data-stu-id="722b0-149">**Ordered delivery**</span></span>|<span data-ttu-id="722b0-150">受信の順序でメッセージを送信するには、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="722b0-150">Select this check box to send messages in order of receipt.</span></span>|  
    |<span data-ttu-id="722b0-151">**現在のメッセージの失敗したときに後続のメッセージの送信を停止します。**</span><span class="sxs-lookup"><span data-stu-id="722b0-151">**Stop sending subsequent messages on current message failure**</span></span>|<span data-ttu-id="722b0-152">失敗したメッセージに続く後続のメッセージの送信を停止するには、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="722b0-152">Select this check box to stop sending subsequent messages that follow a failed message.</span></span> <span data-ttu-id="722b0-153">このオプションは、使用可能な場合にのみ、**順次配送**オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="722b0-153">This option is available only when the **Ordered delivery** option is selected.</span></span>|  
    |<span data-ttu-id="722b0-154">**失敗したメッセージのルーティングを有効にします。**</span><span class="sxs-lookup"><span data-stu-id="722b0-154">**Enable routing for failed messages**</span></span>|<span data-ttu-id="722b0-155">失敗したメッセージのルーティングを有効にするには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="722b0-155">Select this option to enable routing for failed messages.</span></span>|  
    |<span data-ttu-id="722b0-156">**サービス時間帯を有効にします。**</span><span class="sxs-lookup"><span data-stu-id="722b0-156">**Enable service window**</span></span>|<span data-ttu-id="722b0-157">送信ポートがあります、開始時刻と停止時刻を指定することによって 1 日の期間を指定するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="722b0-157">Select this option to specify the time period each day during which the send port will be operational by specifying a start time and stop time.</span></span>|  
    |<span data-ttu-id="722b0-158">**[開始時刻]**</span><span class="sxs-lookup"><span data-stu-id="722b0-158">**Start time**</span></span>|<span data-ttu-id="722b0-159">毎日、送信ポートがメッセージの送信を開始する時刻を指定します。</span><span class="sxs-lookup"><span data-stu-id="722b0-159">Specify the time each day at which the send port starts sending messages.</span></span> <span data-ttu-id="722b0-160">このオプションは、使用可能な場合にのみ、**有効にするサービス時間帯**オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="722b0-160">This option is available only when the **Enable service window** option is selected.</span></span>|  
    |<span data-ttu-id="722b0-161">**停止時刻**</span><span class="sxs-lookup"><span data-stu-id="722b0-161">**Stop time**</span></span>|<span data-ttu-id="722b0-162">毎日、送信ポートがメッセージの送信を停止する時刻を指定します。</span><span class="sxs-lookup"><span data-stu-id="722b0-162">Specify the time each day at which the send port stops sending messages.</span></span> <span data-ttu-id="722b0-163">このオプションは、使用可能な場合にのみ、**有効にするサービス時間帯**オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="722b0-163">This option is available only when the **Enable service window** option is selected.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="722b0-164">参照</span><span class="sxs-lookup"><span data-stu-id="722b0-164">See Also</span></span>  
[<span data-ttu-id="722b0-165">メッセージの配信を順序付け</span><span class="sxs-lookup"><span data-stu-id="722b0-165">Ordered Delivery of Messages</span></span>](../core/ordered-delivery-of-messages.md)  
 [<span data-ttu-id="722b0-166">送信ポートの作成および構成</span><span class="sxs-lookup"><span data-stu-id="722b0-166">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)