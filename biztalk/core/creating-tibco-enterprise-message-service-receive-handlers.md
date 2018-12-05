---
title: TIBCO EMS の作成の成果物を受け取る |Microsoft ドキュメント
description: 受信ポートを作成し、BizTalk Server で、TIBCO Enterprise Message Service アダプタを使用するトランスポートのプロパティを設定
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1307e3c-0237-4f19-a642-58e694fe95d0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf5810dc012c7aa5dcc2fbdfcecd9d59d066ced7
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015377"
---
# <a name="create-tibco-ems-receive-artifacts"></a><span data-ttu-id="da8f7-103">TIBCO EMS の作成の成果物の受信</span><span class="sxs-lookup"><span data-stu-id="da8f7-103">Create TIBCO EMS receive artifacts</span></span>

## <a name="overview"></a><span data-ttu-id="da8f7-104">概要</span><span class="sxs-lookup"><span data-stu-id="da8f7-104">Overview</span></span>
<span data-ttu-id="da8f7-105">TIBCO Enterprise Message Service の受信元は、特定のキューまたはトピックを登録して関連メッセージを受信するリスナー サービスです。</span><span class="sxs-lookup"><span data-stu-id="da8f7-105">TIBCO Enterprise Message Service receiver is a listener service that registers a particular Queue or Topic and receives the relative messages.</span></span> <span data-ttu-id="da8f7-106">BizTalk Adapter for TIBCO Enterprise Message Service は、新しいセッションを開いて、最初に TIBCO Enterprise Message Service を登録し、その後、メッセージを受信するためにポーリングを継続します。</span><span class="sxs-lookup"><span data-stu-id="da8f7-106">BizTalk Adapter for TIBCO Enterprise Message Service first registers with TIBCO Enterprise Message Service by opening a new session, and then it continues polling to receive messages..</span></span> <span data-ttu-id="da8f7-107">このセクションでは、TIBCO Enterprise Message Service に接続するために受信ポートを設定する方法と、実行時に TIBCO EMS と対話するためにオーケストレーションに XML を含める方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="da8f7-107">This section explains how to set the receive port to connect to TIBCO Enterprise Message Service and how to include XML in your orchestration to interact with TIBCO EMS at run time.</span></span>  

## <a name="create-a-receive-port"></a><span data-ttu-id="da8f7-108">受信ポートを作成する</span><span class="sxs-lookup"><span data-stu-id="da8f7-108">Create a receive port</span></span>  
  
1.  <span data-ttu-id="da8f7-109">BizTalk Server 管理コンソールで、展開**BizTalk グループ**、展開**アプリケーション**、し、アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="da8f7-109">In the BizTalk Server Administration Console, expand **BizTalk Group**, expand **Applications**, and then expand your application.</span></span>  
  
2.  <span data-ttu-id="da8f7-110">右クリック**受信ポート\*\*\*\*新規**、順にクリック**一方向受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="da8f7-110">Right-click **Receive Ports**, select **New**, and then click **One-way Receive Ports**.</span></span>  
  
3.  <span data-ttu-id="da8f7-111">**受信ポートのプロパティ** ウィンドウで、**全般** ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="da8f7-111">In the **Receive Port Properties** window, on the **General** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="da8f7-112">**名前**フィールドに「`ReceiveFromTIBCOEMS`です。</span><span class="sxs-lookup"><span data-stu-id="da8f7-112">In the **Name** field, type `ReceiveFromTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="da8f7-113">**認証**グループ ボックスで、認証の使用時のメッセージの処理方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="da8f7-113">In the **Authentication** group box, specify how messages are handled when using authentication.</span></span>  
  
    3.  <span data-ttu-id="da8f7-114">選択、**失敗したメッセージの有効化のルーティングを**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="da8f7-114">Select the **Enable routing for failed messages** checkbox.</span></span>  
  
4.  <span data-ttu-id="da8f7-115">**受信場所** ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="da8f7-115">On the **Receive Locations** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="da8f7-116">**[新規作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da8f7-116">Click **New**.</span></span>  
  
    2.  <span data-ttu-id="da8f7-117">**受信場所**ウィンドウで、**全般** ページで、入力、**名前**受信場所のです。</span><span class="sxs-lookup"><span data-stu-id="da8f7-117">In the **Receive Locations** window, on the **General** page, type the **Name** of the receive location.</span></span>  
  
    3.  <span data-ttu-id="da8f7-118">**型**ドロップダウン一覧で、トランスポートの種類を選択してから、**受信ハンドラー**ドロップダウン一覧で、トランスポート アドレスを選択します。</span><span class="sxs-lookup"><span data-stu-id="da8f7-118">From the **Type** drop-down list, select the transport type, and from the **Receive handler** drop-down list, select the transport address.</span></span>  
  
    4.  <span data-ttu-id="da8f7-119">**受信パイプライン**ドロップダウン リストで、受信パイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="da8f7-119">From the **Receive pipeline** drop-down list, select the receive pipeline.</span></span>  
  
    5.  <span data-ttu-id="da8f7-120">**スケジュール**] ページで、[、**開始日**と**終了日**ドキュメントの受信を制限します。</span><span class="sxs-lookup"><span data-stu-id="da8f7-120">On the **Schedule** page, select the **Start date** and the **End date** to restrict receiving documents.</span></span>  
  
    6.  <span data-ttu-id="da8f7-121">選択、**有効にするサービス時間帯**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="da8f7-121">Select the **Enable service window** checkbox.</span></span>  
  
    7.  <span data-ttu-id="da8f7-122">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da8f7-122">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="da8f7-123">**受信マップ**ページで、選択したポートでドキュメントを変換するための受信マップを選択します。</span><span class="sxs-lookup"><span data-stu-id="da8f7-123">On the **Inbound Maps** page, select the inbound maps for transforming documents on the selected port.</span></span>  
  
6.  <span data-ttu-id="da8f7-124">**追跡** ページで、必要なメッセージ本文の追跡と追跡メッセージのプロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="da8f7-124">On the **Tracking** page, select the desired tracking message bodies and tracking message properties.</span></span>  
  
7.  <span data-ttu-id="da8f7-125">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da8f7-125">Click **OK**.</span></span>  

## <a name="set-the-receive-port-transport-properties"></a><span data-ttu-id="da8f7-126">受信ポートのトランスポート プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="da8f7-126">Set the receive port transport properties</span></span>
<span data-ttu-id="da8f7-127">TIBCO Enterprise Message System (EMS) の受信場所を**URL**と**Target Namespace** TIBCO EMS システムには、必要な唯一の構成値。</span><span class="sxs-lookup"><span data-stu-id="da8f7-127">For a TIBCO Enterprise Message System (EMS) receive location, the **URL** and **Target Namespace** to the TIBCO EMS System are the only configuration values required.</span></span>    
 
1.  <span data-ttu-id="da8f7-128">展開して、**システム定義**し、TIBCO EMS サーバーに接続に必要なすべての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="da8f7-128">Expand the **System Definition** and enter all required information for connection to the TIBCO EMS server.</span></span>  
  
2.  <span data-ttu-id="da8f7-129">展開**メッセージの処理**し必要なすべての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="da8f7-129">Expand **Message Handling** and enter all required information.</span></span>  
  
    |<span data-ttu-id="da8f7-130">パラメーター</span><span class="sxs-lookup"><span data-stu-id="da8f7-130">Parameter</span></span>|<span data-ttu-id="da8f7-131">Description</span><span class="sxs-lookup"><span data-stu-id="da8f7-131">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="da8f7-132">**メッセージ セレクター**</span><span class="sxs-lookup"><span data-stu-id="da8f7-132">**Message Selector**</span></span>|<span data-ttu-id="da8f7-133">メッセージは、メッセージに関してこの文字列が True と評価された場合にのみ送信先で受信されます。</span><span class="sxs-lookup"><span data-stu-id="da8f7-133">Messages are received only if this string evaluates to True with the message in the destination.</span></span><br /><br /> <span data-ttu-id="da8f7-134">受信ポートは、このフィールドに記述された式に一致するヘッダー プロパティを含むメッセージのみを受信できます。</span><span class="sxs-lookup"><span data-stu-id="da8f7-134">Allows the receive port to retrieve only messages that contain header properties that match the expression described in this field.</span></span><br /><br /> <span data-ttu-id="da8f7-135">メッセージ セレクターの構文は、SQL92 条件式構文のサブセットに基づいています。</span><span class="sxs-lookup"><span data-stu-id="da8f7-135">The syntax of message selectors is based on a subset of the SQL92 conditional expression syntax.</span></span> <span data-ttu-id="da8f7-136">構文については、TIBCO EMS のユーザー ガイドで詳しく説明されています。</span><span class="sxs-lookup"><span data-stu-id="da8f7-136">The syntax is fully described in the TIBCO EMS users guide.</span></span><br /><br /> <span data-ttu-id="da8f7-137">たとえば、メッセージに NewsType という名前のヘッダー プロパティが含まれている場合、受信ポートでは、種類が Sports または Editorial のメッセージのみを取得できます。</span><span class="sxs-lookup"><span data-stu-id="da8f7-137">For example, if a message contains a header property name NewsType, a receive port can retrieve only those that are of type Sports or Editorial.</span></span>|  
    |<span data-ttu-id="da8f7-138">**再試行の回数**</span><span class="sxs-lookup"><span data-stu-id="da8f7-138">**Retry Count**</span></span>|<span data-ttu-id="da8f7-139">トランスポートの再試行の回数です。</span><span class="sxs-lookup"><span data-stu-id="da8f7-139">The retry count for the transport.</span></span> <span data-ttu-id="da8f7-140">既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="da8f7-140">Default value is 0.</span></span>|  
    |<span data-ttu-id="da8f7-141">**再試行の間隔**</span><span class="sxs-lookup"><span data-stu-id="da8f7-141">**Retry Interval**</span></span>|<span data-ttu-id="da8f7-142">アダプターが再試行を開始するまでに待機する時間です。</span><span class="sxs-lookup"><span data-stu-id="da8f7-142">The period of time the adapter waits before initiating a retry.</span></span> <span data-ttu-id="da8f7-143">既定値は、5 分です。</span><span class="sxs-lookup"><span data-stu-id="da8f7-143">Default value is five minutes.</span></span>|  
  
3.  <span data-ttu-id="da8f7-144">展開して、**サーバー接続の定義**し必要なすべての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="da8f7-144">Expand the **Server Connection Definition** and enter all required information.</span></span>  
  
    |<span data-ttu-id="da8f7-145">パラメーター</span><span class="sxs-lookup"><span data-stu-id="da8f7-145">Parameter</span></span>|<span data-ttu-id="da8f7-146">Description</span><span class="sxs-lookup"><span data-stu-id="da8f7-146">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="da8f7-147">**変換先**</span><span class="sxs-lookup"><span data-stu-id="da8f7-147">**Destination**</span></span>|<span data-ttu-id="da8f7-148">必須の設定です。</span><span class="sxs-lookup"><span data-stu-id="da8f7-148">Mandatory setting.</span></span> <span data-ttu-id="da8f7-149">送信先の名前と種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="da8f7-149">Defines the name and type of the destination.</span></span> <span data-ttu-id="da8f7-150">キューまたはトピックを Queue[queue.name] または Topic[topic.name] という形式で定義します。</span><span class="sxs-lookup"><span data-stu-id="da8f7-150">Defines the queue or topic with the following format: Queue[queue.name] or Topic[topic.name].</span></span>|  
    |<span data-ttu-id="da8f7-151">**[ポート番号]**</span><span class="sxs-lookup"><span data-stu-id="da8f7-151">**Port Number**</span></span>|<span data-ttu-id="da8f7-152">TIBCO EMS サーバーがリッスンするポートです。</span><span class="sxs-lookup"><span data-stu-id="da8f7-152">Port on which the TIBCO EMS server listens.</span></span>|  
    |<span data-ttu-id="da8f7-153">**[サーバー名]**</span><span class="sxs-lookup"><span data-stu-id="da8f7-153">**Server Name**</span></span>|<span data-ttu-id="da8f7-154">必須の設定です。</span><span class="sxs-lookup"><span data-stu-id="da8f7-154">Mandatory setting.</span></span> <span data-ttu-id="da8f7-155">TIBCO EMS サーバーをホストしているシステムの名前です。</span><span class="sxs-lookup"><span data-stu-id="da8f7-155">Name of the system hosting the TIBCO EMS server.</span></span>|  
  
4.  <span data-ttu-id="da8f7-156">シングル サインオン (SSO) を使用する資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="da8f7-156">Provide credentials using Single Sign-On (SSO).</span></span>  
  
     <span data-ttu-id="da8f7-157">TIBCO EMS システムへのアクセスには、2 つの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="da8f7-157">There are two methods that you can use to access the TIBCO EMS system.</span></span> <span data-ttu-id="da8f7-158">資格情報 (ユーザー名とパスワードのパラメーター) を使用するまたはシングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="da8f7-158">You can use Credentials (user name and password parameters) or Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="da8f7-159">選択**はい**で**SSO を使用する**でのシングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="da8f7-159">Select **Yes** in **Use SSO** to use Single Sign-On.</span></span>  
  
    -   <span data-ttu-id="da8f7-160">一覧で関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="da8f7-160">Select an affiliate application in the list.</span></span>  
  
         <span data-ttu-id="da8f7-161">エンタープライズ シングル サインオン ツールで作成される関連アプリケーションは、TIBCO EMS などのアプリケーションを表します。</span><span class="sxs-lookup"><span data-stu-id="da8f7-161">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as TIBCO EMS.</span></span> <span data-ttu-id="da8f7-162">Microsoft BizTalk Adapter for TIBCO EMS は、アプリケーション ユーザーの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="da8f7-162">Microsoft BizTalk Adapter for TIBCO EMS uses the credentials of an application user.</span></span> <span data-ttu-id="da8f7-163">これらの資格情報は、指定された関連アプリケーションのサーバー システムの SSO データベースから取得されます。</span><span class="sxs-lookup"><span data-stu-id="da8f7-163">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span>  
  
         <span data-ttu-id="da8f7-164">関連アプリケーションを作成する方法の詳細については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications5.md)です。</span><span class="sxs-lookup"><span data-stu-id="da8f7-164">For more information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications5.md).</span></span>  
  
5.  <span data-ttu-id="da8f7-165">展開**ユーザーの資格情報**を入力し、**ユーザー名**と**パスワード**TIBCO EMS サーバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="da8f7-165">Expand **User Credentials** and enter the **User Name** and **Password** to access the TIBCO EMS server.</span></span>  
  
    |<span data-ttu-id="da8f7-166">パラメーター</span><span class="sxs-lookup"><span data-stu-id="da8f7-166">Parameter</span></span>|<span data-ttu-id="da8f7-167">Description</span><span class="sxs-lookup"><span data-stu-id="da8f7-167">Description</span></span>|  
    |---------------|-----------------|  
    |`Password`|<span data-ttu-id="da8f7-168">TIBCO EMS デーモンとの通信に使用するユーザーのパスワードです。</span><span class="sxs-lookup"><span data-stu-id="da8f7-168">The user’s password that is used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="da8f7-169">選択しなかった場合**SSO を使用する**、BizTalk Adapter for TIBCO EMS デーモンと通信するために TIBCO EMS の資格情報パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da8f7-169">If you did not select **Use SSO**, you must set credential parameters for BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
    |`User Name`|<span data-ttu-id="da8f7-170">TIBCO EMS デーモンとの通信に使用するユーザーの名前です。</span><span class="sxs-lookup"><span data-stu-id="da8f7-170">Name of a user that is used to communicate with a TIBCO EMS daemon.</span></span><br /><br /> <span data-ttu-id="da8f7-171">選択しなかった場合**SSO を使用する**、BizTalk Adapter for TIBCO EMS デーモンと通信するために TIBCO EMS の資格情報パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da8f7-171">If you did not select **Use SSO**, you must set credential parameters for BizTalk Adapter for TIBCO EMS to communicate with a TIBCO EMS daemon.</span></span>|  
  
6.  <span data-ttu-id="da8f7-172">をクリックして**適用**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="da8f7-172">Click **Apply**, and then click **OK**.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="da8f7-173">次の手順</span><span class="sxs-lookup"><span data-stu-id="da8f7-173">Next steps</span></span>
[<span data-ttu-id="da8f7-174">TIBCO EMS メッセージ コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="da8f7-174">TIBCO EMS message context properties</span></span>](../core/message-context-properties-in-biztalk-server.md)