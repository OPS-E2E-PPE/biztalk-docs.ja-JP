---
title: BizTalk Adapter for JD Edwards OneWorld に追加する |Microsoft Docs
description: BizTalk 管理コンソールに、JD Edwards OneWorld を追加、送信ポートを作成、トランスポートのプロパティを構成および xmlreceive と XMLTransmit パイプラインを使用して、BizTalk Server で JD Edwards OneWorld アダプターを使用する場合
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03126f4e-9156-4c0c-ab5c-0627f0c05263
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: decababef3ece92c99687a4019b15625b1b4c6b7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981395"
---
# <a name="configure-jd-edwards-enterpriseone-artifacts-in-biztalk-administration"></a><span data-ttu-id="00e18-103">BizTalk 管理コンソールで JD Edwards EnterpriseOne の成果物を構成します。</span><span class="sxs-lookup"><span data-stu-id="00e18-103">Configure JD Edwards EnterpriseOne artifacts in BizTalk Administration</span></span>
<span data-ttu-id="00e18-104">Microsoft BizTalk Adapter for JD Edwards OneWorld には、受信ハンドラーと送信ハンドラーの両方のフォルダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="00e18-104">Microsoft BizTalk Adapter for JD Edwards OneWorld contains both the Receive Handler and Send Handler folders.</span></span> <span data-ttu-id="00e18-105">送信ハンドラー フォルダーには、BizTalkServerApplication が含まれています。</span><span class="sxs-lookup"><span data-stu-id="00e18-105">The Send Handler folder contains BizTalkServerApplication.</span></span> <span data-ttu-id="00e18-106">BizTalk Adapter for JD Edwards OneWorld は作成可能です。BizTalk Server とインプロセスで実行され、分離されたホスト プロセスでは実行されません。</span><span class="sxs-lookup"><span data-stu-id="00e18-106">BizTalk Adapter for JD Edwards OneWorld is creatable; it runs in-process with BizTalk Server and does not run in an isolated host process.</span></span>  

## <a name="add-the-adapter-to-biztalk-administration"></a><span data-ttu-id="00e18-107">アダプターを BizTalk 管理コンソールに追加します。</span><span class="sxs-lookup"><span data-stu-id="00e18-107">Add the adapter to BizTalk Administration</span></span> 

1.  <span data-ttu-id="00e18-108">開いている**BizTalk Server 管理**、展開**BizTalk Server 管理**、展開**BizTalk グループ**、順に展開**プラットフォームの設定**.</span><span class="sxs-lookup"><span data-stu-id="00e18-108">Open **BizTalk Server Administration**, expand **BizTalk Server Administration**, expand **BizTalk Group**, and then expand **Platform Settings**.</span></span>  
  
2.  <span data-ttu-id="00e18-109">右クリック**アダプター**を選択します**新規**、選び**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="00e18-109">Right-click **Adapters**, select **New**, and select **Adapter**.</span></span>  
  
3.  <span data-ttu-id="00e18-110">アダプターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="00e18-110">Enter a name for the adapter.</span></span> <span data-ttu-id="00e18-111">たとえば、入力`JDEOneWorld`します。</span><span class="sxs-lookup"><span data-stu-id="00e18-111">For example, enter`JDEOneWorld`.</span></span>  
  
4.  <span data-ttu-id="00e18-112">選択 **[jdeoneworld]** から、**アダプター**一覧**OK**します。</span><span class="sxs-lookup"><span data-stu-id="00e18-112">Select **JDEOneWorld** from the **Adapter** list, and select **OK**.</span></span>  

  
### <a name="check-if-the-adapter-is-working"></a><span data-ttu-id="00e18-113">アダプターが動作しているかどうかは確認します。</span><span class="sxs-lookup"><span data-stu-id="00e18-113">Check if the adapter is working</span></span> 
 <span data-ttu-id="00e18-114">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、調べることで、アダプターが正しく機能していること確認できます、**論理システム**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="00e18-114">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, you can verify that the adapter is functioning correctly by looking at the **Logical System** window.</span></span> <span data-ttu-id="00e18-115">初回のインストレーションでは、このウィンドウは空です。これは、サーバー システムへの接続が未確立で、論理システムが作成されていないからです。</span><span class="sxs-lookup"><span data-stu-id="00e18-115">On initial installation, this window is empty because you have not yet established a connection to the server system, nor have you created any logical systems.</span></span>  
  
 
1. <span data-ttu-id="00e18-116">**BizTalk Server 管理**、展開**プラットフォームの設定**、展開**アダプター**、し、 **jdeoneworld**します。</span><span class="sxs-lookup"><span data-stu-id="00e18-116">In **BizTalk Server Administration**, expand **Platform Settings**, expand **Adapters**, and then select **JDEOneWorld**.</span></span>  
  
2. <span data-ttu-id="00e18-117">詳細ペインで右クリックして**BizTalkServerApplication**を選択し、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="00e18-117">In the details pane, right-click **BizTalkServerApplication**, and select **Properties**.</span></span>  
  
3. <span data-ttu-id="00e18-118">選択、**プロパティ**タブ。</span><span class="sxs-lookup"><span data-stu-id="00e18-118">Select the **Properties** tab.</span></span>  
  
4. <span data-ttu-id="00e18-119">SQL 接続パラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="00e18-119">Set the SQL Connection parameters.</span></span>  
  
   -   <span data-ttu-id="00e18-120">**SQL データベース パラメーターを定義する**SQL Server 名とデータベースはインストール時に設定するものです。</span><span class="sxs-lookup"><span data-stu-id="00e18-120">**Define SQL Database Parameters -** The SQL Server Name and Database are those you set at installation.</span></span> <span data-ttu-id="00e18-121">これは、サーバーと、このアダプターのデータベースを再定義できますをテキスト領域です。</span><span class="sxs-lookup"><span data-stu-id="00e18-121">This is the text area that you can redefine the server and database for this adapter.</span></span>  
  
5. <span data-ttu-id="00e18-122">選択**閉じる**を終了する、**論理システム**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="00e18-122">Select **Close** to exit the **Logical System** window.</span></span>  
  
    <span data-ttu-id="00e18-123">次のステップでは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して論理システムを追加します。</span><span class="sxs-lookup"><span data-stu-id="00e18-123">Your next step is to add a logical system using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  

## <a name="create-the-send-port"></a><span data-ttu-id="00e18-124">送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="00e18-124">Create the send port</span></span>  
  
1.  <span data-ttu-id="00e18-125">**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="00e18-125">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand your application.</span></span>  
  
2.  <span data-ttu-id="00e18-126">右クリックして**送信ポート**を選択します**新規**、し、**静的な送信請求-応答送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="00e18-126">Right-click **Send Ports**, select **New**, and then select **Static Solicit-Response Send Port**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="00e18-127">使用することも**静的な一方向ポート**します。</span><span class="sxs-lookup"><span data-stu-id="00e18-127">You can also use **Static One-Way Port**.</span></span>  
  
3.  <span data-ttu-id="00e18-128">**送信ポートのプロパティ**を選択、**名前**フィールド、および送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="00e18-128">In the **Send Port Properties**, select the **Name** field, and enter a send port name.</span></span> <span data-ttu-id="00e18-129">たとえば、入力**SendToJDE**します。</span><span class="sxs-lookup"><span data-stu-id="00e18-129">For example, enter **SendToJDE**.</span></span>  
  
4.  <span data-ttu-id="00e18-130">**型**ドロップダウン リストで、 **[jdeoneworld]** します。</span><span class="sxs-lookup"><span data-stu-id="00e18-130">In the **Type** drop-down list, select **JDEOneWorld**.</span></span>  
  
5.  <span data-ttu-id="00e18-131">**URI**ドロップダウン リストで、送信ハンドラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="00e18-131">In the **URI** drop-down list, select the send handler.</span></span>  
  
6.  <span data-ttu-id="00e18-132">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="00e18-132">Select **OK**.</span></span> 

## <a name="configure-the-transport-properties"></a><span data-ttu-id="00e18-133">トランスポートのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="00e18-133">Configure the transport properties</span></span>
<span data-ttu-id="00e18-134">JD Edwards OneWorld の "トランスポート プロパティ" システム定義は、デザイン時および実行時のログオンに使用されます。</span><span class="sxs-lookup"><span data-stu-id="00e18-134">The JD Edwards OneWorld Transport Property System Definition is used for design and run-time logon.</span></span> <span data-ttu-id="00e18-135">この資格情報を設定するのは、デザイン時に JD Edwards OneWorld ビジネス関数を参照するためと、実行時に呼び出しを行うためです。</span><span class="sxs-lookup"><span data-stu-id="00e18-135">You set these credentials to browse JD Edwards OneWorld business functions at design time and make calls at run time.</span></span>  
  
 <span data-ttu-id="00e18-136">JD Edwards OneWorld への接続が作成されるときに、接続オブジェクトにパラメーターが渡されます (ユーザー、パスワード、環境)。</span><span class="sxs-lookup"><span data-stu-id="00e18-136">When a connection is made to JD Edwards OneWorld, parameters are passed to the connection object (User, Password, Environment).</span></span> <span data-ttu-id="00e18-137">JD Edwards OneWorld Application ビジネス関数のインスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="00e18-137">It returns an instance of the JD Edwards OneWorld aApplication business function.</span></span> <span data-ttu-id="00e18-138">資格情報には、さらにエンタープライズ サーバー/アプリケーション サーバーの名前、およびサービスがリッスンする定義済みの TCP/IP ポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="00e18-138">The credentials are further defined by the name of the enterprise/application server, and the defined TCP/IP port on which the service listens.</span></span>  
  
 <span data-ttu-id="00e18-139">エンタープライズ サーバーの名前とポートは、jdeinterop.ini というファイルから読み取られます。</span><span class="sxs-lookup"><span data-stu-id="00e18-139">The enterprise server name and port are read from a file that is named jdeinterop.ini.</span></span> <span data-ttu-id="00e18-140">これらの値は、システム定義での設定値と同一でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="00e18-140">These values must be the same as those that are in the System Definition settings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00e18-141">入力値はすべて、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="00e18-141">All entries are case sensitive.</span></span>  
  
### <a name="set-the-properties"></a><span data-ttu-id="00e18-142">プロパティを設定します</span><span class="sxs-lookup"><span data-stu-id="00e18-142">Set the properties</span></span>  
 <span data-ttu-id="00e18-143">**トランスポートのプロパティ**ダイアログ ボックスで、サーバー システムやアクセスしようとしているオブジェクトに固有の接続および資格情報パラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="00e18-143">In the **Transport Properties** dialog box, you set the connection and credential parameters that are specific to the server system and the objects you are trying to access.</span></span>  
  
1.  <span data-ttu-id="00e18-144">資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="00e18-144">Provide credentials.</span></span> <span data-ttu-id="00e18-145">JD Edwards OneWorld システムにアクセスするには、次の方法があります。</span><span class="sxs-lookup"><span data-stu-id="00e18-145">You can access the JD Edwards OneWorld system using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="00e18-146">ログオン資格情報 (パスワード、ユーザー名): このメソッドを使用する場合は、手順 5. に進みます。</span><span class="sxs-lookup"><span data-stu-id="00e18-146">Logon credentials (Password, User name): If you use this method, go to step 5.</span></span>  
  
    -   <span data-ttu-id="00e18-147">シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="00e18-147">Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="00e18-148">シングル サインオン (SSO) を使用する**はい**で、**を使用して SSO**します。</span><span class="sxs-lookup"><span data-stu-id="00e18-148">To use Single Sign-On (SSO), select **Yes** in the **Use SSO**.</span></span>  
  
     <span data-ttu-id="00e18-149">SSO を設定する方法の詳細については、次を参照してください[アダプターのセキュリティ。](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)</span><span class="sxs-lookup"><span data-stu-id="00e18-149">For more information about how to set up SSO, see [Security in the adapter](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)</span></span>  
  
3.  <span data-ttu-id="00e18-150">一覧で関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="00e18-150">Select an affiliate application in the list.</span></span>  
  
     <span data-ttu-id="00e18-151">エンタープライズ シングル サインオンのツールによって作成される関連アプリケーションはそれぞれ、JD Edwards OneWorld などの特定のアプリケーションを表します。</span><span class="sxs-lookup"><span data-stu-id="00e18-151">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as JD Edwards OneWorld.</span></span> <span data-ttu-id="00e18-152">Microsoft BizTalk Adapter for JD Edwards OneWorld では、アプリケーション ユーザーの資格情報が使用されます。</span><span class="sxs-lookup"><span data-stu-id="00e18-152">Microsoft BizTalk Adapter for JD Edwards OneWorld uses the credentials of an application user.</span></span> <span data-ttu-id="00e18-153">この資格情報は、指定された関連アプリケーションのサーバー システムの SSO 資格情報データベースから取得されます。</span><span class="sxs-lookup"><span data-stu-id="00e18-153">These credentials are retrieved from the SSO Credentials database for the server system for a specified affiliate application.</span></span> <span data-ttu-id="00e18-154">取得される資格情報は、BizTalk Server プロジェクトを起動したアプリケーション ユーザーの資格情報です。</span><span class="sxs-lookup"><span data-stu-id="00e18-154">The credentials are those of the application user who launched the BizTalk Server project.</span></span>  
  
     <span data-ttu-id="00e18-155">詳細については、次を参照してください。[関連アプリケーションを作成する](../core/creating-affiliate-applications3.md)します。</span><span class="sxs-lookup"><span data-stu-id="00e18-155">For more information, see [Creating Affiliate Applications](../core/creating-affiliate-applications3.md).</span></span>  
  
4.  <span data-ttu-id="00e18-156">展開、 **JD Edwards OneWorld システム**ノードし、JD Edwards OneWorld サーバーへの接続に必要なすべての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="00e18-156">Expand the **JD Edwards OneWorld system** node and enter all required information for connection to the JD Edwards OneWorld server.</span></span>  
  
     <span data-ttu-id="00e18-157">![](../core/media/jdedadapter-02-jdesystem.gif "JDEdAdapter_02_JDESystem")</span><span class="sxs-lookup"><span data-stu-id="00e18-157">![](../core/media/jdedadapter-02-jdesystem.gif "JDEdAdapter_02_JDESystem")</span></span>  
  
     <span data-ttu-id="00e18-158">接続パラメーターの設定が完了すると、JD Edwards OneWorld システムの内容を参照できるようになります。</span><span class="sxs-lookup"><span data-stu-id="00e18-158">After you set the connection parameters, you can browse a JD Edwards OneWorld system.</span></span> <span data-ttu-id="00e18-159">詳細については、次を参照してください。[を BizTalk Server プロジェクトに JD Edwards OneWorld スキーマをインポートする](../core/importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md)します。</span><span class="sxs-lookup"><span data-stu-id="00e18-159">For more information, see [Importing JD Edwards OneWorld Schemas into BizTalk Server Projects](../core/importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md).</span></span>  
  
5.  <span data-ttu-id="00e18-160">呼び出しでは、たとえば 200 の数を示す値を入力**最大同時呼び出し数**必要な場合。</span><span class="sxs-lookup"><span data-stu-id="00e18-160">Enter a value representing the number of calls, for example 200, in **Max Concurrent Calls** if it is required.</span></span>  
  
     <span data-ttu-id="00e18-161">`Max Concurrent Calls`パラメーターでは、構成を最適化することができます。</span><span class="sxs-lookup"><span data-stu-id="00e18-161">The `Max Concurrent Calls` parameter lets you optimize your configuration.</span></span> <span data-ttu-id="00e18-162">スループットがバックエンドの処理能力を上回る場合に、このパラメーターを使用してメッセージ オーバーロード保護をアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="00e18-162">You use this parameter in instances where the throughput exceeds back-end processing capabilities, to activate message-overload protection.</span></span> <span data-ttu-id="00e18-163">既定値は -1 で、これは呼び出しの数が無制限であることを示します。</span><span class="sxs-lookup"><span data-stu-id="00e18-163">The default is -1, which means that the calls are unlimited.</span></span>  
  
     <span data-ttu-id="00e18-164">BizTalk Server が送信アダプターにメッセージを送信するときに、BizTalk Server は最初にアダプターからバッチを 1 つ受け取ります。</span><span class="sxs-lookup"><span data-stu-id="00e18-164">When BizTalk Server submits messages to the transmit adapter, it first receives a batch from the adapter.</span></span> <span data-ttu-id="00e18-165">`TransmitMessage` をそのバッチに対して起動して、各メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="00e18-165">It invokes `TransmitMessage` on the batch to transmit each message.</span></span> <span data-ttu-id="00e18-166">この処理が完了すると、BizTalk Server はバッチで `Done` を呼び出し、アダプタがバックエンドに対するメッセージ送信を開始します。</span><span class="sxs-lookup"><span data-stu-id="00e18-166">When done, BizTalk Server invokes `Done` on the batch, and the adapter starts transmitting the messages to the back-end.</span></span> <span data-ttu-id="00e18-167">BizTalk Server が複数のバッチを受け取ってから `Done` を呼び出しても、メッセージは送信されません。</span><span class="sxs-lookup"><span data-stu-id="00e18-167">If BizTalk Server obtains multiple batches before invoking `Done`, it might never occur.</span></span> <span data-ttu-id="00e18-168">バッチ内に含めるメッセージの最大数を設定することで、バックエンドに送信するメッセージを制御できます。</span><span class="sxs-lookup"><span data-stu-id="00e18-168">By setting the maximum number of messages in a batch, you can control messages to the back-end.</span></span>  
  
     <span data-ttu-id="00e18-169">このパラメーターの変更が反映されるまで最大 1 分程度かかります。BizTalk Server は、SQL データベースに保存されたアダプター構成に対する変更を取得する必要があるからです。</span><span class="sxs-lookup"><span data-stu-id="00e18-169">Changing this parameter takes effect within one minute; BizTalk Server must retrieve the changes to the adapter configuration saved in the SQL database.</span></span>  
  
6.  <span data-ttu-id="00e18-170">選択**はい**の**エージェントの更新**runtimeagent.exe および browsingagent.exe の処理を必要な場合に自動的に再起動を強制します。</span><span class="sxs-lookup"><span data-stu-id="00e18-170">Select **Yes** for **Refresh Agent** to force the runtimeagent.exe and the browsingagent.exe processes to restart automatically when required.</span></span>  
  
     <span data-ttu-id="00e18-171">たとえば、サーバーとの接続が失われた場合や、サーバーに追加したものが Microsoft アダプター ウィザードに表示されない場合に、処理を自動的に再起動することができます。</span><span class="sxs-lookup"><span data-stu-id="00e18-171">For example, you want the process to restart automatically if it loses connection with the server, or if you add something to the server and it does not appear in the Microsoft Adapter Wizard for selection.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="00e18-172">browsingagent.exe が最新の状態に更新されるのは、ユーザーが現在の参照セッションを終了したときです。</span><span class="sxs-lookup"><span data-stu-id="00e18-172">The browsingagent.exe does not refresh until you exit the current browsing session.</span></span> <span data-ttu-id="00e18-173">たとえば、終了する必要があります、**項目の追加生成**閲覧セッションを browsingagent.exe を更新します。</span><span class="sxs-lookup"><span data-stu-id="00e18-173">For example, you must exit the **Add generated item** browsing session and reenter to update the browsingagent.exe.</span></span>  
  
7.  <span data-ttu-id="00e18-174">必要なすべての情報を提供するには、後に次のようにクリックします。**適用**、順にクリックします **[ok]** の接続情報を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="00e18-174">After providing all required information, click **Apply**, and then click **OK** to accept the connection information.</span></span>  
  
     <span data-ttu-id="00e18-175">JD Edwards OneWorld にアクセスするには、BizTalk Adapter for JD Edwards OneWorld の接続パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00e18-175">You must set connection parameters for BizTalk Adapter for JD Edwards OneWorld to access JD Edwards OneWorld.</span></span>  
  
### <a name="adapter-required-properties"></a><span data-ttu-id="00e18-176">必要なアダプターのプロパティ</span><span class="sxs-lookup"><span data-stu-id="00e18-176">Adapter required properties</span></span>  
 <span data-ttu-id="00e18-177">コントロール パネルでグローバル環境変数を設定しなかった場合は、このセクションで設定できます。</span><span class="sxs-lookup"><span data-stu-id="00e18-177">If you did not set global environment variables in Control Panel, you can do so in this section.</span></span>  
  
|<span data-ttu-id="00e18-178">パラメーター</span><span class="sxs-lookup"><span data-stu-id="00e18-178">Parameter</span></span>|<span data-ttu-id="00e18-179">説明</span><span class="sxs-lookup"><span data-stu-id="00e18-179">Description</span></span>|  
|---------------|-----------------|  
|`Host`|<span data-ttu-id="00e18-180">ホスト サーバーのコンピューター名の名前を入力 (たとえば、 `actsvr1`); またはコンピューターの IP アドレス (たとえば、 `123.456.0.789`)。</span><span class="sxs-lookup"><span data-stu-id="00e18-180">Type the name of the host server computer name (for example, `actsvr1`); or the IP address of the computer (for example, `123.456.0.789`).</span></span>|  
|<span data-ttu-id="00e18-181">JAVA_HOME</span><span class="sxs-lookup"><span data-stu-id="00e18-181">JAVA_HOME</span></span>|<span data-ttu-id="00e18-182">JDK インストール ディレクトリの完全パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="00e18-182">Type the complete path of your JDK installation.</span></span>|  
|<span data-ttu-id="00e18-183">JD Edwards 環境</span><span class="sxs-lookup"><span data-stu-id="00e18-183">JDE Edwards Environment</span></span>|<span data-ttu-id="00e18-184">たとえば、JD Edwards oneworld では、環境の名前を入力`DV7333`します。</span><span class="sxs-lookup"><span data-stu-id="00e18-184">Type the name of an environment in JD Edwards OneWorld, for example, `DV7333`.</span></span><br /><br /> <span data-ttu-id="00e18-185">DV7333 は開発環境の一般名、PY7333 はプロトタイプ環境の一般名、PD7333 は実稼働環境の一般名です。</span><span class="sxs-lookup"><span data-stu-id="00e18-185">DV7333 is a common name for the development environment, PY7333 is common for the prototype environment, and PD7333 is common for the production environment.</span></span>|  
|<span data-ttu-id="00e18-186">JDEdwards JAR ファイル</span><span class="sxs-lookup"><span data-stu-id="00e18-186">JDEdwards JAR Files</span></span>|<span data-ttu-id="00e18-187">各 JAR ファイルの完全なパスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="00e18-187">Enter the complete path and file name for each JAR file:</span></span><br /><br /> <span data-ttu-id="00e18-188">-Connector.jar</span><span class="sxs-lookup"><span data-stu-id="00e18-188">-   Connector.jar</span></span><br /><span data-ttu-id="00e18-189">-Kernel.jar</span><span class="sxs-lookup"><span data-stu-id="00e18-189">-   Kernel.jar</span></span><br /><span data-ttu-id="00e18-190">-JDEJAccess.jar</span><span class="sxs-lookup"><span data-stu-id="00e18-190">-   JDEJAccess.jar</span></span><br /><span data-ttu-id="00e18-191">-JDEActionalInterop.jar</span><span class="sxs-lookup"><span data-stu-id="00e18-191">-   JDEActionalInterop.jar</span></span><br /><br /> <span data-ttu-id="00e18-192">jar ファイルの区切りにはセミコロン (;) を使用し、スペースは入れません。</span><span class="sxs-lookup"><span data-stu-id="00e18-192">Each jar file must be separated with a semi-colon (;) and no space.</span></span> <span data-ttu-id="00e18-193">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="00e18-193">For example:</span></span><br /><br /> `<drive>\Connector.jar;<drive>\Kernel.jar;`|  
|<span data-ttu-id="00e18-194">パスワード</span><span class="sxs-lookup"><span data-stu-id="00e18-194">Password</span></span>|<span data-ttu-id="00e18-195">指定したユーザーのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="00e18-195">Type the password of the specified user.</span></span>|  
|<span data-ttu-id="00e18-196">Port</span><span class="sxs-lookup"><span data-stu-id="00e18-196">Port</span></span>|<span data-ttu-id="00e18-197">データを交換するポート番号を入力 (たとえば、 `6009`)。</span><span class="sxs-lookup"><span data-stu-id="00e18-197">Type the port number that will exchange data (for example, `6009`).</span></span>|  
|<span data-ttu-id="00e18-198">[ユーザー名]</span><span class="sxs-lookup"><span data-stu-id="00e18-198">User Name</span></span>|<span data-ttu-id="00e18-199">JD Edwards OneWorld システムへのログオンに使用する JD Edwards OneWorld ユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="00e18-199">Type a JD Edwards OneWorld user name that will be used to log on to the JD Edwards OneWorld system.</span></span>|  

## <a name="use-the-xmltransmit-and-xmlreceive-pipelines"></a><span data-ttu-id="00e18-200">XMLTransmit および XMLReceive パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="00e18-200">Use the XMLTransmit and XMLReceive pipelines</span></span>
<span data-ttu-id="00e18-201">Microsoft の BizTalk Adapter for JD Edwards OneWorld では、送信 XMLTransmit および XMLReceive を選択すること、および受信パイプラインが必要です。</span><span class="sxs-lookup"><span data-stu-id="00e18-201">Microsoft BizTalk Adapter for JD Edwards OneWorld requires that you select XMLTransmit and XMLReceive for the send and receive pipelines.</span></span>  
  
1.  <span data-ttu-id="00e18-202">**BizTalk Server 管理**、展開**アプリケーション**、アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="00e18-202">In **BizTalk Server Administration**, expand **Applications**, and then expand your application.</span></span>  
  
2.  <span data-ttu-id="00e18-203">選択**送信ポート**を送信ポートを右クリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="00e18-203">Select **Send Ports**, right-click your send port, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="00e18-204">**送信ポートのプロパティ**次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="00e18-204">In the **Send Ports Properties**, do the following:</span></span>  
  
    1.  <span data-ttu-id="00e18-205">送信パイプラインを選択、**送信パイプライン**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="00e18-205">Select the send pipeline from the **Send Pipeline** drop-down list.</span></span>  
  
    2.  <span data-ttu-id="00e18-206">受信パイプラインを選択、**受信パイプライン**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="00e18-206">Select the Receive pipeline from the **Receive Pipeline** drop-down list.</span></span>  
  
4.  <span data-ttu-id="00e18-207">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="00e18-207">Select **OK**.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="00e18-208">次のステップ</span><span class="sxs-lookup"><span data-stu-id="00e18-208">Next steps</span></span>
[<span data-ttu-id="00e18-209">Visual Studio へのアダプター スキーマのインポート</span><span class="sxs-lookup"><span data-stu-id="00e18-209">Import adapter schemas into Visual Studio</span></span>](importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md)  
[<span data-ttu-id="00e18-210">メッセージ コンテキストのプロパティの使用</span><span class="sxs-lookup"><span data-stu-id="00e18-210">Use Message Context Properties</span></span>](using-message-context-properties2.md)