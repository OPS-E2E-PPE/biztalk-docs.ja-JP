---
title: TIBCO EMS 送信アーティファクトを作成 |Microsoft ドキュメント
description: 送信ポートを作成し、BizTalk Server で、TIBCO Enterprise Message Service アダプタを使用するトランスポートのプロパティを構成します。
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
ms.openlocfilehash: 570693f4d5644f0ea850a53ec537ce30db5ca568
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014185"
---
# <a name="creating--tibco-enterprise-message-service-send-handlers"></a><span data-ttu-id="7bd7e-103">TIBCO Enterprise Message Service 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="7bd7e-103">Creating  TIBCO Enterprise Message Service Send Handlers</span></span>
<span data-ttu-id="7bd7e-104">ここでは、送信ポートを設定して TIBCO Enterprise Message Service (EMS) に接続する方法、およびオーケストレーションに XML を入れ実行時に TIBCO EMS と連携する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-104">This section explains how to set the send port to connect to TIBCO Enterprise Message Service (EMS) and how to include XML in your orchestration to interact with TIBCO EMS at run time.</span></span>  


## <a name="create-a-send-port"></a><span data-ttu-id="7bd7e-105">送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-105">Create a send port</span></span>  
  
1.  <span data-ttu-id="7bd7e-106">BizTalk Server 管理コンソールで、展開**BizTalk グループ**、展開**アプリケーション**、し、アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-106">In the BizTalk Server Administration Console, expand **BizTalk Group**, expand **Applications**, and then expand your application.</span></span>  
  
2.  <span data-ttu-id="7bd7e-107">右クリック**送信ポート****新規**、し、**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-107">Right-click **Send Ports**, select **New**, and then select **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="7bd7e-108">**送信ポートのプロパティ**次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-108">In the **Send Port Properties**, do the following:</span></span>  
  
    1.  <span data-ttu-id="7bd7e-109">たとえば、送信ポートの名前を入力`SendToTIBCOEMS`です。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-109">Type a name for the send port, for example, `SendToTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="7bd7e-110">**型**ドロップダウン リストで、 **TIBCO EMS**です。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-110">From the **Type** drop-down list, select **TIBCO EMS**.</span></span>  
  
    3.  <span data-ttu-id="7bd7e-111">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-111">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="7bd7e-112">**送信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpipelines.xmltransmit]** です。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-112">From the **Send Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span> <span data-ttu-id="7bd7e-113">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** です。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-113">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  

        > [!NOTE]
        > <span data-ttu-id="7bd7e-114">BizTalk Adapter for TIBCO Enterprise Message Service では、受信、送信、および [xmlreceive] の [xmltransmit] を選択することが必要です。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-114">The BizTalk Adapter for TIBCO Enterprise Message Service requires that you select XMLTransmit for send, and XMLReceive for receive.</span></span>  
  
    6.  <span data-ttu-id="7bd7e-115">選択**構成**送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-115">Select **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="7bd7e-116">**TIBCO EMS トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-116">In the **TIBCO EMS Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="7bd7e-117">入力**メッセージ処理**、**サーバー接続の定義**、**トランザクション サポート**、 **Username**、および**パスワード**です。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-117">Enter **Message Handling**, **Server Connection Definition**, **Transaction Support**, **Username**, and the **password**.</span></span>  
  
         <span data-ttu-id="7bd7e-118">ログオン情報を設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-118">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="7bd7e-119">一覧で、TIBCO EMS システムを表すよう作成した関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-119">In the list, select the affiliate application you created to represent the TIBCO EMS system.</span></span>  
  
    3.  <span data-ttu-id="7bd7e-120">**SSO を使用する****はい**です。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-120">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="7bd7e-121">**[ OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-121">Select **OK**.</span></span>  
  
5.  <span data-ttu-id="7bd7e-122">**[ OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-122">Select **OK**.</span></span> 

## <a name="set-send-port-transport-properties"></a><span data-ttu-id="7bd7e-123">送信ポート トランスポートのプロパティを設定</span><span class="sxs-lookup"><span data-stu-id="7bd7e-123">Set send port transport properties</span></span>
<span data-ttu-id="7bd7e-124">TIBCO Enterprise Message Service トランスポート プロパティは、デザイン時に構成して実行時に使用します。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-124">The TIBCO Enterprise Message Service transport properties are configured in design time and used in run time.</span></span> <span data-ttu-id="7bd7e-125">**トランスポートのプロパティ**、接続および資格情報のパラメーターに固有の設定、サーバー システムおよびアクセスしようとしているオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-125">In the **Transport Properties**, you set the connection and credential parameters specific to the server system and the objects you are trying to access.</span></span>  
  
 ![](../core/media/tib-tibcoemssendtransportpropertiess.gif "TIB_TIBCOEMSSendTransportPropertiess")  
  
  
1.  <span data-ttu-id="7bd7e-126">**トランスポートのプロパティ**、展開**システム定義**、し、TIBCO EMS サーバーに接続に必要なすべての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-126">In the **Transport Properties**, expand **System Definition**, and enter all required information for connection to the TIBCO EMS server.</span></span>  
  
     <span data-ttu-id="7bd7e-127">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service を TIBCO EMS に接続するための構成パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-127">You must set configuration parameters to connect Microsoft BizTalk Adapter for TIBCO Enterprise Message Service to TIBCO EMS.</span></span> <span data-ttu-id="7bd7e-128">**このデータは、大文字小文字を区別します。**</span><span class="sxs-lookup"><span data-stu-id="7bd7e-128">**This data is case sensitive.**</span></span>  
  
2.  <span data-ttu-id="7bd7e-129">展開**メッセージの処理**、必要なすべての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-129">Expand **Message Handling**, and enter all required information.</span></span>  
  
    |<span data-ttu-id="7bd7e-130">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7bd7e-130">Parameter</span></span>|<span data-ttu-id="7bd7e-131">Description</span><span class="sxs-lookup"><span data-stu-id="7bd7e-131">Description</span></span>|  
    |---------------|-----------------|  
    |`Message Expiration Time`|<span data-ttu-id="7bd7e-132">メッセージがキューまたはトピックにとどまる時間の長さを表す整数。この時間が経過すると、メッセージは TIBCO EMS サーバーによって削除されます。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-132">An integer that describes the length of time the message stays on the queue or topic; after the time expires, the message is deleted by the TIBCO EMS server.</span></span><br /><br /> <span data-ttu-id="7bd7e-133">EMS.Expiration メッセージ プロパティ ヘッダーと同義です。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-133">It is synonymous to the EMS.Expiration message property header.</span></span> <span data-ttu-id="7bd7e-134">オーケストレーションによって上書きされることがあります。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-134">It can be overridden with the orchestration.</span></span><br /><br /> <span data-ttu-id="7bd7e-135">既定値は 0 ミリ秒であり、メッセージが送信先で期限切れにならないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-135">Default value is 0 milliseconds, which means that the message will not expire from the destination.</span></span>|  
    |`Message is Persistent`|<span data-ttu-id="7bd7e-136">メッセージは、受信確認の前に、TIBCO EMS サーバーによってディスクに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-136">Messages are written to disk by the TIBCO EMS server before they are acknowledged.</span></span><br /><br /> <span data-ttu-id="7bd7e-137">これは TibcoEMS.DeliveryMode ヘッダー プロパティです。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-137">This is the TibcoEMS.DeliveryMode header property.</span></span> <span data-ttu-id="7bd7e-138">アダプターに対するメッセージ受信確認の前に、送信されたメッセージがサーバーによってキューに保存されるように指示します。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-138">It instructs sent messages to be persisted in the queue by the server before acknowledging reception of the message to the adapter.</span></span><br /><br /> <span data-ttu-id="7bd7e-139">既定値は **True**です。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-139">Default value is **True**.</span></span>|  
    |`Message Priority`|<span data-ttu-id="7bd7e-140">メッセージの優先度を定義する 0 ～ 9 の数値によるランク付け。値が大きいほど優先度が高くなります。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-140">Numeric ranking from 0 to 9, which defines the priority of the message; the larger the value, the higher the priority.</span></span><br /><br /> <span data-ttu-id="7bd7e-141">プロパティは、サーバーがメッセージをコンシューマーに配信する順序に影響します (値が大きいほど順番が早くなります)。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-141">Priority affects the order in which the server delivers messages to consumers (higher values first).</span></span><br /><br /> <span data-ttu-id="7bd7e-142">JMS 仕様では、0 (最低の優先度) から 9 (最高の優先度) まで 10 レベルの優先度値が定義されています。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-142">The JMS specification defines ten levels of priority value, from zero (lowest priority) to 9 (highest priority).</span></span> <span data-ttu-id="7bd7e-143">この仕様では、クライアントが 0 ～ 4 を通常の優先度の段階と想定し、5 ～ 9 を高優先度の段階と想定するように推奨されています。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-143">The specification suggests that clients consider 0–4 as gradations of normal priority, and priorities 5–9 as gradations of expedited priority.</span></span><br /><br /> <span data-ttu-id="7bd7e-144">既定値は**4**です。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-144">Default value is **4**.</span></span>|  
  
3.  <span data-ttu-id="7bd7e-145">展開**サーバー接続の定義**し必要なすべての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-145">Expand **Server Connection Definition** and enter all required information.</span></span>  
  
    |<span data-ttu-id="7bd7e-146">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7bd7e-146">Parameter</span></span>|<span data-ttu-id="7bd7e-147">Description</span><span class="sxs-lookup"><span data-stu-id="7bd7e-147">Description</span></span>|  
    |---------------|-----------------|  
    |`Destination`|<span data-ttu-id="7bd7e-148">必須の設定です。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-148">Mandatory setting.</span></span> <span data-ttu-id="7bd7e-149">送信先の名前と種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-149">Defines the name and type of the destination.</span></span> <span data-ttu-id="7bd7e-150">例: staticqueue [Q1] です。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-150">For example: staticqueue[Q1].</span></span><br /><br /> <span data-ttu-id="7bd7e-151">キューまたはトピックは、次の形式を定義します。 {static} {dynamic] Queue [queuename] または {static} {dynamic] Topic [topicname] です。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-151">Defines the queue or topic with the following format: {static}{dynamic]Queue[queuename] or {static}{dynamic]Topic[topicname].</span></span> <span data-ttu-id="7bd7e-152">**注:** が存在しない送信先にメッセージを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-152">**Note:**  You can send a message to a destination that does not exist.</span></span> <span data-ttu-id="7bd7e-153">このような場合は、TIBCO Enterprise Message Service を作成、変換先です。これを呼びます、*動的送信先*です。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-153">In such a case, TIBCO Enterprise Message Service creates the destination; this is referred to as a *Dynamic Destination*.</span></span> <span data-ttu-id="7bd7e-154">これはプロデューサーによって作成され、メッセージが消費されてプロデューサーが切断された時点で削除されます。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-154">This is a destination created by a producer and deleted when the message is consumed and the producer disconnects.</span></span> <span data-ttu-id="7bd7e-155">A*静的送信先*は送信先ですのみ作成できますが、TIBCO Enterprise Message Service 管理者。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-155">A *static destination* is a destination which can only created by a TIBCO Enterprise Message Service Administrator.</span></span> <span data-ttu-id="7bd7e-156">送信先との接続を開いている状態で動的ポートに接続することはできません。BizTalk Adapter for TIBCO Enterprise Message Service はサーバー上の名前の参照メカニズムを利用するからです。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-156">You cannot connect to a dynamic port when you open a connection to a destination because BizTalk Adapter for TIBCO Enterprise Message Service uses a name lookup mechanism on the server.</span></span> <span data-ttu-id="7bd7e-157">名前の参照を使用するときは、静的ポートのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-157">Only static ports are visible when you are using the name lookup.</span></span> <span data-ttu-id="7bd7e-158">動的ポートに接続するときに静的送信先を使用できます。ただし、その名前の送信先が存在しない場合は、送信先が作成されます。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-158">When connecting to a dynamic port, you can use static destinations; however, if no destination by that name exists, a destination is created.</span></span> <span data-ttu-id="7bd7e-159">Destination では、ポートを定義するときに、使用する送信先の種類を明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-159">Destination lets you explicitly specify the type of destination to use when defining the port.</span></span> <span data-ttu-id="7bd7e-160">転送先の構文が大文字小文字を区別: staticqueue [queue_name] statictopic [topic_name] dynamicqueue [queue_name];dynamictopic [topic_name] です。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-160">The syntax for the Destination is not case sensitive: staticqueue[queue_name], statictopic[topic_name], dynamicqueue[queue_name]; dynamictopic[topic_name].</span></span>|  
    |`Port Number`|<span data-ttu-id="7bd7e-161">TIBCO EMS サーバーがリッスンするポートです。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-161">Port on which the TIBCO EMS server listens.</span></span>|  
    |`Server Name`|<span data-ttu-id="7bd7e-162">必須の設定です。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-162">Mandatory setting.</span></span> <span data-ttu-id="7bd7e-163">TIBCO EMS サーバーをホストしているシステムの名前です。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-163">Name of the system hosting the TIBCO EMS server.</span></span>|  
  
4.  <span data-ttu-id="7bd7e-164">シングル サインオン (SSO) を使用する資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-164">Provide credentials using Single Sign-On (SSO).</span></span>  
  
     <span data-ttu-id="7bd7e-165">TIBCO EMS システムにアクセスするには 2 つの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-165">You can use two methods to access the TIBCO EMS system.</span></span> <span data-ttu-id="7bd7e-166">1 つは資格情報 ([ユーザー名] パラメーターと [パスワード] パラメーター) を使用する方法で、もう 1 つはシングル サインオン (SSO) を使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-166">You can use Credentials (User Name and Password parameters) or Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="7bd7e-167">選択**はい**で、 **SSO を使用する**でのシングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-167">Select **Yes** in the **Use SSO** to use Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="7bd7e-168">一覧から関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-168">Select an affiliate application from the list.</span></span>  
  
         <span data-ttu-id="7bd7e-169">エンタープライズ シングル サインオン ツールで作成される関連アプリケーションは、TIBCO EMS などのアプリケーションを表します。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-169">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as TIBCO EMS.</span></span> <span data-ttu-id="7bd7e-170">BizTalk Adapter for TIBCO EMS は、アプリケーション ユーザーの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-170">BizTalk Adapter for TIBCO EMS uses the credentials of an application user.</span></span> <span data-ttu-id="7bd7e-171">これらの資格情報は、指定された関連アプリケーションのサーバー システムの SSO データベースから取得されます。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-171">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span>  
  
         <span data-ttu-id="7bd7e-172">関連アプリケーションを作成する方法の詳細については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications5.md)です。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-172">For more information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications5.md).</span></span>  
  
5.  <span data-ttu-id="7bd7e-173">**トランザクションをサポート****はい**この送信ポートがトランザクションをサポートする場合。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-173">In **Transaction Support**, select **Yes** if this send port will support transactions.</span></span>  
  
     <span data-ttu-id="7bd7e-174">ポートのトランザクションのサポートを有効にする場合、このポートを使用するすべてのオーケストレーションがトランザクション対応である必要があります。そうでない場合、すべての呼び出しはロールバックされます (コミットされないなど)。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-174">If you enable transaction support on the port, all orchestrations using this port must be transactional; otherwise, all calls are rolled back (for example, are not committed).</span></span> <span data-ttu-id="7bd7e-175">オーケストレーションに追加したスコープ オブジェクトによって、トランザクションのライフサイクルが制御されます。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-175">The scope object added to the orchestration controls the transaction life-cycle.</span></span>  
  
6.  <span data-ttu-id="7bd7e-176">展開**ユーザーの資格情報**を入力し、**ユーザー名**と**パスワード**TIBCO EMS サーバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-176">Expand **User Credentials** and enter the **User Name** and **Password** to access the TIBCO EMS server.</span></span>  
  
    |<span data-ttu-id="7bd7e-177">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7bd7e-177">Parameter</span></span>|<span data-ttu-id="7bd7e-178">Description</span><span class="sxs-lookup"><span data-stu-id="7bd7e-178">Description</span></span>|  
    |---------------|-----------------|  
    |`Password`|<span data-ttu-id="7bd7e-179">TIBCO EMS デーモンとの通信に使用されるユーザーのパスワード。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-179">The user’s Password used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="7bd7e-180">選択しなかった場合**SSO を使用する**、BizTalk Adapter for TIBCO EMS デーモンと通信するために TIBCO EMS の資格情報パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-180">If you did not select **Use SSO**, you must set credential parameters for the BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
    |`User Name`|<span data-ttu-id="7bd7e-181">TIBCO EMS デーモンとの通信に使用されるユーザー名。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-181">Name of a user used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="7bd7e-182">選択しなかった場合**SSO を使用する**、BizTalk Adapter for TIBCO EMS デーモンと通信するために TIBCO EMS の資格情報パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-182">If you did not select **Use SSO**, you must set credential parameters for the BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
  
7.  <span data-ttu-id="7bd7e-183">をクリックして**適用**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="7bd7e-183">Click **Apply**, and then click **OK**.</span></span>  

   
## <a name="next-steps"></a><span data-ttu-id="7bd7e-184">次の手順</span><span class="sxs-lookup"><span data-stu-id="7bd7e-184">Next steps</span></span>
[<span data-ttu-id="7bd7e-185">作成の成果物の受信</span><span class="sxs-lookup"><span data-stu-id="7bd7e-185">Create receive artifacts</span></span>](../core/creating-tibco-enterprise-message-service-receive-handlers.md)  
[<span data-ttu-id="7bd7e-186">TIBCO EMS メッセージ コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="7bd7e-186">TIBCO EMS message context properties</span></span>](../core/message-context-properties-in-biztalk-server.md)