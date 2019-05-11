---
title: TIBCO EMS 送信アイテムの作成 |Microsoft Docs
description: 送信ポートを作成し、TIBCO Enterprise Message Service アダプターを BizTalk Server で使用するトランスポートのプロパティを構成します。
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f82609c-1847-4796-a24c-28cb350ec739
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98bc13b59826c7f5e938d4749776adb742f70133
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353585"
---
# <a name="creating--tibco-enterprise-message-service-send-handlers"></a><span data-ttu-id="3feca-103">TIBCO Enterprise Message Service 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="3feca-103">Creating  TIBCO Enterprise Message Service Send Handlers</span></span>
<span data-ttu-id="3feca-104">ここでは、送信ポートを設定して TIBCO Enterprise Message Service (EMS) に接続する方法、およびオーケストレーションに XML を入れ実行時に TIBCO EMS と連携する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="3feca-104">This section explains how to set the send port to connect to TIBCO Enterprise Message Service (EMS) and how to include XML in your orchestration to interact with TIBCO EMS at run time.</span></span>  


## <a name="create-a-send-port"></a><span data-ttu-id="3feca-105">送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="3feca-105">Create a send port</span></span>  
  
1.  <span data-ttu-id="3feca-106">BizTalk Server 管理コンソールで  **BizTalk グループ**、展開**アプリケーション**、アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="3feca-106">In the BizTalk Server Administration Console, expand **BizTalk Group**, expand **Applications**, and then expand your application.</span></span>  
  
2.  <span data-ttu-id="3feca-107">右クリックして**送信ポート**を選択します**新規**、し、**静的な送信請求-応答送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="3feca-107">Right-click **Send Ports**, select **New**, and then select **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="3feca-108">**送信ポートのプロパティ**次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3feca-108">In the **Send Port Properties**, do the following:</span></span>  
  
    1.  <span data-ttu-id="3feca-109">たとえば、送信ポートの名前を入力`SendToTIBCOEMS`します。</span><span class="sxs-lookup"><span data-stu-id="3feca-109">Type a name for the send port, for example, `SendToTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="3feca-110">**型**ドロップダウン リストで、 **TIBCO EMS**します。</span><span class="sxs-lookup"><span data-stu-id="3feca-110">From the **Type** drop-down list, select **TIBCO EMS**.</span></span>  
  
    3.  <span data-ttu-id="3feca-111">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="3feca-111">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="3feca-112">**送信パイプライン**ドロップダウン リストで、 **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="3feca-112">From the **Send Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span> <span data-ttu-id="3feca-113">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** します。</span><span class="sxs-lookup"><span data-stu-id="3feca-113">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  

        > [!NOTE]
        > <span data-ttu-id="3feca-114">BizTalk Adapter for TIBCO Enterprise Message Service では、受信、送信、および [xmlreceive] の [xmltransmit] を選択することが必要です。</span><span class="sxs-lookup"><span data-stu-id="3feca-114">The BizTalk Adapter for TIBCO Enterprise Message Service requires that you select XMLTransmit for send, and XMLReceive for receive.</span></span>  
  
    6.  <span data-ttu-id="3feca-115">選択**構成**送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="3feca-115">Select **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="3feca-116">**TIBCO EMS トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3feca-116">In the **TIBCO EMS Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="3feca-117">入力**メッセージの処理**、**サーバー接続の定義**、**トランザクションのサポート**、 **Username**、および**パスワード**します。</span><span class="sxs-lookup"><span data-stu-id="3feca-117">Enter **Message Handling**, **Server Connection Definition**, **Transaction Support**, **Username**, and the **password**.</span></span>  
  
         <span data-ttu-id="3feca-118">ログオン情報を設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3feca-118">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="3feca-119">一覧で、TIBCO EMS システムを表すよう作成した関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="3feca-119">In the list, select the affiliate application you created to represent the TIBCO EMS system.</span></span>  
  
    3.  <span data-ttu-id="3feca-120">**SSO を使用**、**はい**します。</span><span class="sxs-lookup"><span data-stu-id="3feca-120">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="3feca-121">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3feca-121">Select **OK**.</span></span>  
  
5.  <span data-ttu-id="3feca-122">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3feca-122">Select **OK**.</span></span> 

## <a name="set-send-port-transport-properties"></a><span data-ttu-id="3feca-123">送信ポート トランスポートのプロパティを設定</span><span class="sxs-lookup"><span data-stu-id="3feca-123">Set send port transport properties</span></span>
<span data-ttu-id="3feca-124">TIBCO Enterprise Message Service トランスポート プロパティは、デザイン時に構成して実行時に使用します。</span><span class="sxs-lookup"><span data-stu-id="3feca-124">The TIBCO Enterprise Message Service transport properties are configured in design time and used in run time.</span></span> <span data-ttu-id="3feca-125">**トランスポートのプロパティ**、接続および資格情報パラメーターに固有の設定、サーバー システムとアクセスしようとしているオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3feca-125">In the **Transport Properties**, you set the connection and credential parameters specific to the server system and the objects you are trying to access.</span></span>  
  
 <span data-ttu-id="3feca-126">![](../core/media/tib-tibcoemssendtransportpropertiess.gif "TIB_TIBCOEMSSendTransportPropertiess")</span><span class="sxs-lookup"><span data-stu-id="3feca-126">![](../core/media/tib-tibcoemssendtransportpropertiess.gif "TIB_TIBCOEMSSendTransportPropertiess")</span></span>  
  
  
1.  <span data-ttu-id="3feca-127">**トランスポートのプロパティ**、展開**システム定義**、し、TIBCO EMS サーバーへの接続に必要なすべての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="3feca-127">In the **Transport Properties**, expand **System Definition**, and enter all required information for connection to the TIBCO EMS server.</span></span>  
  
     <span data-ttu-id="3feca-128">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service を TIBCO EMS に接続するための構成パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3feca-128">You must set configuration parameters to connect Microsoft BizTalk Adapter for TIBCO Enterprise Message Service to TIBCO EMS.</span></span> <span data-ttu-id="3feca-129">**このデータは、大文字小文字を区別します。**</span><span class="sxs-lookup"><span data-stu-id="3feca-129">**This data is case sensitive.**</span></span>  
  
2.  <span data-ttu-id="3feca-130">展開**メッセージの処理**、必要なすべての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="3feca-130">Expand **Message Handling**, and enter all required information.</span></span>  
  
    |<span data-ttu-id="3feca-131">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3feca-131">Parameter</span></span>|<span data-ttu-id="3feca-132">説明</span><span class="sxs-lookup"><span data-stu-id="3feca-132">Description</span></span>|  
    |---------------|-----------------|  
    |`Message Expiration Time`|<span data-ttu-id="3feca-133">メッセージがキューまたはトピックにとどまる時間の長さを表す整数。この時間が経過すると、メッセージは TIBCO EMS サーバーによって削除されます。</span><span class="sxs-lookup"><span data-stu-id="3feca-133">An integer that describes the length of time the message stays on the queue or topic; after the time expires, the message is deleted by the TIBCO EMS server.</span></span><br /><br /> <span data-ttu-id="3feca-134">EMS.Expiration メッセージ プロパティ ヘッダーと同義です。</span><span class="sxs-lookup"><span data-stu-id="3feca-134">It is synonymous to the EMS.Expiration message property header.</span></span> <span data-ttu-id="3feca-135">オーケストレーションによってオーバーライドされることがあります。</span><span class="sxs-lookup"><span data-stu-id="3feca-135">It can be overridden with the orchestration.</span></span><br /><br /> <span data-ttu-id="3feca-136">既定値は 0 ミリ秒であり、メッセージが送信先で期限切れにならないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="3feca-136">Default value is 0 milliseconds, which means that the message will not expire from the destination.</span></span>|  
    |`Message is Persistent`|<span data-ttu-id="3feca-137">メッセージは、受信確認の前に、TIBCO EMS サーバーによってディスクに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="3feca-137">Messages are written to disk by the TIBCO EMS server before they are acknowledged.</span></span><br /><br /> <span data-ttu-id="3feca-138">これは TibcoEMS.DeliveryMode ヘッダー プロパティです。</span><span class="sxs-lookup"><span data-stu-id="3feca-138">This is the TibcoEMS.DeliveryMode header property.</span></span> <span data-ttu-id="3feca-139">アダプターに対するメッセージ受信確認の前に、送信されたメッセージがサーバーによってキューに保存されるように指示します。</span><span class="sxs-lookup"><span data-stu-id="3feca-139">It instructs sent messages to be persisted in the queue by the server before acknowledging reception of the message to the adapter.</span></span><br /><br /> <span data-ttu-id="3feca-140">既定値は **True**です。</span><span class="sxs-lookup"><span data-stu-id="3feca-140">Default value is **True**.</span></span>|  
    |`Message Priority`|<span data-ttu-id="3feca-141">メッセージの優先度を定義する 0 ～ 9 の数値によるランク付け。値が大きいほど優先度が高くなります。</span><span class="sxs-lookup"><span data-stu-id="3feca-141">Numeric ranking from 0 to 9, which defines the priority of the message; the larger the value, the higher the priority.</span></span><br /><br /> <span data-ttu-id="3feca-142">プロパティは、サーバーがメッセージをコンシューマーに配信する順序に影響します (値が大きいほど順番が早くなります)。</span><span class="sxs-lookup"><span data-stu-id="3feca-142">Priority affects the order in which the server delivers messages to consumers (higher values first).</span></span><br /><br /> <span data-ttu-id="3feca-143">JMS 仕様では、0 (最低の優先度) から 9 (最高の優先度) まで 10 レベルの優先度値が定義されています。</span><span class="sxs-lookup"><span data-stu-id="3feca-143">The JMS specification defines ten levels of priority value, from zero (lowest priority) to 9 (highest priority).</span></span> <span data-ttu-id="3feca-144">この仕様では、クライアントが 0 ～ 4 を通常の優先度の段階と想定し、5 ～ 9 を高優先度の段階と想定するように推奨されています。</span><span class="sxs-lookup"><span data-stu-id="3feca-144">The specification suggests that clients consider 0–4 as gradations of normal priority, and priorities 5–9 as gradations of expedited priority.</span></span><br /><br /> <span data-ttu-id="3feca-145">既定値は**4**します。</span><span class="sxs-lookup"><span data-stu-id="3feca-145">Default value is **4**.</span></span>|  
  
3.  <span data-ttu-id="3feca-146">展開**サーバー接続の定義**必要なすべての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="3feca-146">Expand **Server Connection Definition** and enter all required information.</span></span>  
  
    |<span data-ttu-id="3feca-147">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3feca-147">Parameter</span></span>|<span data-ttu-id="3feca-148">説明</span><span class="sxs-lookup"><span data-stu-id="3feca-148">Description</span></span>|  
    |---------------|-----------------|  
    |`Destination`|<span data-ttu-id="3feca-149">必須の設定です。</span><span class="sxs-lookup"><span data-stu-id="3feca-149">Mandatory setting.</span></span> <span data-ttu-id="3feca-150">送信先の名前と種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="3feca-150">Defines the name and type of the destination.</span></span> <span data-ttu-id="3feca-151">例: staticqueue [Q1]。</span><span class="sxs-lookup"><span data-stu-id="3feca-151">For example: staticqueue[Q1].</span></span><br /><br /> <span data-ttu-id="3feca-152">キューまたはトピックは、次の形式を定義します。 {static} {dynamic] Queue [queuename] または {static} {dynamic] Topic [topicname]。</span><span class="sxs-lookup"><span data-stu-id="3feca-152">Defines the queue or topic with the following format: {static}{dynamic]Queue[queuename] or {static}{dynamic]Topic[topicname].</span></span> <span data-ttu-id="3feca-153">**注:** 存在しない宛先にメッセージを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="3feca-153">**Note:**  You can send a message to a destination that does not exist.</span></span> <span data-ttu-id="3feca-154">このような場合は、TIBCO Enterprise Message Service は送信先; を作成します呼ばれる、*動的送信先*します。</span><span class="sxs-lookup"><span data-stu-id="3feca-154">In such a case, TIBCO Enterprise Message Service creates the destination; this is referred to as a *Dynamic Destination*.</span></span> <span data-ttu-id="3feca-155">これはプロデューサーによって作成され、メッセージが消費されてプロデューサーが切断された時点で削除されます。</span><span class="sxs-lookup"><span data-stu-id="3feca-155">This is a destination created by a producer and deleted when the message is consumed and the producer disconnects.</span></span> <span data-ttu-id="3feca-156">A*静的送信先*がのみ作成できる送信先をして、TIBCO Enterprise Message Service 管理者です。</span><span class="sxs-lookup"><span data-stu-id="3feca-156">A *static destination* is a destination which can only created by a TIBCO Enterprise Message Service Administrator.</span></span> <span data-ttu-id="3feca-157">送信先との接続を開いている状態で動的ポートに接続することはできません。BizTalk Adapter for TIBCO Enterprise Message Service はサーバー上の名前の参照メカニズムを利用するからです。</span><span class="sxs-lookup"><span data-stu-id="3feca-157">You cannot connect to a dynamic port when you open a connection to a destination because BizTalk Adapter for TIBCO Enterprise Message Service uses a name lookup mechanism on the server.</span></span> <span data-ttu-id="3feca-158">名前の参照を使用するときは、静的ポートのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3feca-158">Only static ports are visible when you are using the name lookup.</span></span> <span data-ttu-id="3feca-159">動的ポートに接続するときに静的送信先を使用できます。ただし、その名前の送信先が存在しない場合は、送信先が作成されます。</span><span class="sxs-lookup"><span data-stu-id="3feca-159">When connecting to a dynamic port, you can use static destinations; however, if no destination by that name exists, a destination is created.</span></span> <span data-ttu-id="3feca-160">Destination では、ポートを定義するときに、使用する送信先の種類を明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="3feca-160">Destination lets you explicitly specify the type of destination to use when defining the port.</span></span> <span data-ttu-id="3feca-161">宛先の構文が大文字小文字が区別: staticqueue [queue_name]、statictopic [topic_name]、dynamicqueue [queue_name];dynamictopic [topic_name]。</span><span class="sxs-lookup"><span data-stu-id="3feca-161">The syntax for the Destination is not case sensitive: staticqueue[queue_name], statictopic[topic_name], dynamicqueue[queue_name]; dynamictopic[topic_name].</span></span>|  
    |`Port Number`|<span data-ttu-id="3feca-162">TIBCO EMS サーバーがリッスンするポートです。</span><span class="sxs-lookup"><span data-stu-id="3feca-162">Port on which the TIBCO EMS server listens.</span></span>|  
    |`Server Name`|<span data-ttu-id="3feca-163">必須の設定です。</span><span class="sxs-lookup"><span data-stu-id="3feca-163">Mandatory setting.</span></span> <span data-ttu-id="3feca-164">TIBCO EMS サーバーをホストしているシステムの名前です。</span><span class="sxs-lookup"><span data-stu-id="3feca-164">Name of the system hosting the TIBCO EMS server.</span></span>|  
  
4.  <span data-ttu-id="3feca-165">シングル サインオン (SSO) を使用する資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="3feca-165">Provide credentials using Single Sign-On (SSO).</span></span>  
  
     <span data-ttu-id="3feca-166">TIBCO EMS システムにアクセスするには 2 つの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3feca-166">You can use two methods to access the TIBCO EMS system.</span></span> <span data-ttu-id="3feca-167">1 つは資格情報 ([ユーザー名] パラメーターと [パスワード] パラメーター) を使用する方法で、もう 1 つはシングル サインオン (SSO) を使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="3feca-167">You can use Credentials (User Name and Password parameters) or Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="3feca-168">選択**はい**で、**を使用して SSO**でシングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="3feca-168">Select **Yes** in the **Use SSO** to use Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="3feca-169">一覧から関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="3feca-169">Select an affiliate application from the list.</span></span>  
  
         <span data-ttu-id="3feca-170">エンタープライズ シングル サインオン ツールで作成される関連アプリケーションは、TIBCO EMS などのアプリケーションを表します。</span><span class="sxs-lookup"><span data-stu-id="3feca-170">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as TIBCO EMS.</span></span> <span data-ttu-id="3feca-171">BizTalk Adapter for TIBCO EMS は、アプリケーション ユーザーの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="3feca-171">BizTalk Adapter for TIBCO EMS uses the credentials of an application user.</span></span> <span data-ttu-id="3feca-172">これらの資格情報は、指定された関連アプリケーションのサーバー システムの SSO データベースから取得されます。</span><span class="sxs-lookup"><span data-stu-id="3feca-172">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span>  
  
         <span data-ttu-id="3feca-173">関連アプリケーションを作成する方法の詳細については、次を参照してください。[関連アプリケーションを作成する](../core/creating-affiliate-applications5.md)します。</span><span class="sxs-lookup"><span data-stu-id="3feca-173">For more information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications5.md).</span></span>  
  
5.  <span data-ttu-id="3feca-174">**トランザクションをサポートして**を選択します**はい**場合、この送信ポートがトランザクションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="3feca-174">In **Transaction Support**, select **Yes** if this send port will support transactions.</span></span>  
  
     <span data-ttu-id="3feca-175">ポートのトランザクションのサポートを有効にする場合、このポートを使用するすべてのオーケストレーションがトランザクション対応である必要があります。そうでない場合、すべての呼び出しはロールバックされます (コミットされないなど)。</span><span class="sxs-lookup"><span data-stu-id="3feca-175">If you enable transaction support on the port, all orchestrations using this port must be transactional; otherwise, all calls are rolled back (for example, are not committed).</span></span> <span data-ttu-id="3feca-176">オーケストレーションに追加したスコープ オブジェクトによって、トランザクションのライフサイクルが制御されます。</span><span class="sxs-lookup"><span data-stu-id="3feca-176">The scope object added to the orchestration controls the transaction life-cycle.</span></span>  
  
6.  <span data-ttu-id="3feca-177">展開**ユーザーの資格情報**を入力し、**ユーザー名**と**パスワード**TIBCO EMS サーバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3feca-177">Expand **User Credentials** and enter the **User Name** and **Password** to access the TIBCO EMS server.</span></span>  
  
    |<span data-ttu-id="3feca-178">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3feca-178">Parameter</span></span>|<span data-ttu-id="3feca-179">説明</span><span class="sxs-lookup"><span data-stu-id="3feca-179">Description</span></span>|  
    |---------------|-----------------|  
    |`Password`|<span data-ttu-id="3feca-180">TIBCO EMS デーモンとの通信に使用されるユーザーのパスワード。</span><span class="sxs-lookup"><span data-stu-id="3feca-180">The user’s Password used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="3feca-181">選択しなかった場合**使用 SSO**、BizTalk Adapter for TIBCO EMS デーモンとの通信に TIBCO EMS の資格情報パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3feca-181">If you did not select **Use SSO**, you must set credential parameters for the BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
    |`User Name`|<span data-ttu-id="3feca-182">TIBCO EMS デーモンとの通信に使用されるユーザー名。</span><span class="sxs-lookup"><span data-stu-id="3feca-182">Name of a user used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="3feca-183">選択しなかった場合**使用 SSO**、BizTalk Adapter for TIBCO EMS デーモンとの通信に TIBCO EMS の資格情報パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3feca-183">If you did not select **Use SSO**, you must set credential parameters for the BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
  
7.  <span data-ttu-id="3feca-184">クリックして**適用**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="3feca-184">Click **Apply**, and then click **OK**.</span></span>  

   
## <a name="next-steps"></a><span data-ttu-id="3feca-185">次の手順</span><span class="sxs-lookup"><span data-stu-id="3feca-185">Next steps</span></span>
[<span data-ttu-id="3feca-186">受信アイテムの作成</span><span class="sxs-lookup"><span data-stu-id="3feca-186">Create receive artifacts</span></span>](../core/creating-tibco-enterprise-message-service-receive-handlers.md)  
[<span data-ttu-id="3feca-187">TIBCO EMS メッセージ コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="3feca-187">TIBCO EMS message context properties</span></span>](../core/message-context-properties-in-biztalk-server.md)