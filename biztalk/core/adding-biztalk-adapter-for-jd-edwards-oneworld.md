---
title: "BizTalk Adapter for JD Edwards OneWorld に追加 |Microsoft ドキュメント"
description: "JD Edwards OneWorld を BizTalk 管理コンソールに追加、送信ポートを作成、トランスポートのプロパティを構成および BizTalk Server で JD Edwards OneWorld アダプターを使用するときに、XMLReceive パイプラインと XMLTransmit パイプラインを使用"
ms.custom: 
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03126f4e-9156-4c0c-ab5c-0627f0c05263
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 784323634d3084efd0b56aac1d5dbc97f2b4329f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="configure-jd-edwards-enterpriseone-artifacts-in-biztalk-administration"></a><span data-ttu-id="31039-103">BizTalk 管理コンソールで JD Edwards EnterpriseOne の成果物を構成します。</span><span class="sxs-lookup"><span data-stu-id="31039-103">Configure JD Edwards EnterpriseOne artifacts in BizTalk Administration</span></span>
<span data-ttu-id="31039-104">Microsoft BizTalk Adapter for JD Edwards OneWorld には、受信ハンドラーと送信ハンドラーの両方のフォルダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="31039-104">Microsoft BizTalk Adapter for JD Edwards OneWorld contains both the Receive Handler and Send Handler folders.</span></span> <span data-ttu-id="31039-105">送信ハンドラー フォルダーには、BizTalkServerApplication が含まれています。</span><span class="sxs-lookup"><span data-stu-id="31039-105">The Send Handler folder contains BizTalkServerApplication.</span></span> <span data-ttu-id="31039-106">BizTalk Adapter for JD Edwards OneWorld は作成可能です。BizTalk Server とインプロセスで実行され、分離されたホスト プロセスでは実行されません。</span><span class="sxs-lookup"><span data-stu-id="31039-106">BizTalk Adapter for JD Edwards OneWorld is creatable; it runs in-process with BizTalk Server and does not run in an isolated host process.</span></span>  

## <a name="add-the-adapter-to-biztalk-administration"></a><span data-ttu-id="31039-107">BizTalk 管理コンソールに、アダプターを追加します。</span><span class="sxs-lookup"><span data-stu-id="31039-107">Add the adapter to BizTalk Administration</span></span> 

1.  <span data-ttu-id="31039-108">開いている**BizTalk Server 管理コンソール**、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、順に展開**のプラットフォームの設定**.</span><span class="sxs-lookup"><span data-stu-id="31039-108">Open **BizTalk Server Administration**, expand **BizTalk Server Administration**, expand **BizTalk Group**, and then expand **Platform Settings**.</span></span>  
  
2.  <span data-ttu-id="31039-109">右クリック**アダプター****新規**を選択して**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="31039-109">Right-click **Adapters**, select **New**, and select **Adapter**.</span></span>  
  
3.  <span data-ttu-id="31039-110">アダプターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="31039-110">Enter a name for the adapter.</span></span> <span data-ttu-id="31039-111">たとえば、入力`JDEOneWorld`です。</span><span class="sxs-lookup"><span data-stu-id="31039-111">For example, enter`JDEOneWorld`.</span></span>  
  
4.  <span data-ttu-id="31039-112">選択**[jdeoneworld]**から、**アダプター**一覧**OK**です。</span><span class="sxs-lookup"><span data-stu-id="31039-112">Select **JDEOneWorld** from the **Adapter** list, and select **OK**.</span></span>  

  
### <a name="check-if-the-adapter-is-working"></a><span data-ttu-id="31039-113">アダプターが動作しているかどうかは確認します。</span><span class="sxs-lookup"><span data-stu-id="31039-113">Check if the adapter is working</span></span> 
 <span data-ttu-id="31039-114">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、できることを確認するを確認して、アダプターが正しく機能している、**論理システム**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="31039-114">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, you can verify that the adapter is functioning correctly by looking at the **Logical System** window.</span></span> <span data-ttu-id="31039-115">初回のインストレーションでは、このウィンドウは空です。これは、サーバー システムへの接続が未確立で、論理システムが作成されていないからです。</span><span class="sxs-lookup"><span data-stu-id="31039-115">On initial installation, this window is empty because you have not yet established a connection to the server system, nor have you created any logical systems.</span></span>  
  
 
1.  <span data-ttu-id="31039-116">**BizTalk Server 管理コンソール**、展開**プラットフォームの設定**、展開**アダプター**、し、 **jdeoneworld**です。</span><span class="sxs-lookup"><span data-stu-id="31039-116">In **BizTalk Server Administration**, expand **Platform Settings**, expand **Adapters**, and then select **JDEOneWorld**.</span></span>  
  
2.  <span data-ttu-id="31039-117">詳細ウィンドウで右クリック**BizTalkServerApplication**を選択して**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="31039-117">In the details pane, right-click **BizTalkServerApplication**, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="31039-118">選択、**プロパティ**タブです。</span><span class="sxs-lookup"><span data-stu-id="31039-118">Select the **Properties** tab.</span></span>  
  
4.  <span data-ttu-id="31039-119">SQL 接続パラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="31039-119">Set the SQL Connection parameters.</span></span>  
  
    -   <span data-ttu-id="31039-120">**SQL データベース パラメーターを定義する**SQL Server 名とデータベースがインストール時に設定します。</span><span class="sxs-lookup"><span data-stu-id="31039-120">**Define SQL Database Parameters -** The SQL Server Name and Database are those you set at installation.</span></span> <span data-ttu-id="31039-121">これは、テキスト領域がサーバーと、このアダプターのデータベースを再定義できることです。</span><span class="sxs-lookup"><span data-stu-id="31039-121">This is the text area that you can redefine the server and database for this adapter.</span></span>  
  
5.  <span data-ttu-id="31039-122">選択**閉じる**を終了する、**論理システム**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="31039-122">Select **Close** to exit the **Logical System** window.</span></span>  
  
     <span data-ttu-id="31039-123">次のステップでは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して論理システムを追加します。</span><span class="sxs-lookup"><span data-stu-id="31039-123">Your next step is to add a logical system using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  

## <a name="create-the-send-port"></a><span data-ttu-id="31039-124">送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="31039-124">Create the send port</span></span>  
  
1.  <span data-ttu-id="31039-125">**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="31039-125">In **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand your application.</span></span>  
  
2.  <span data-ttu-id="31039-126">右クリック**送信ポート****新規**、し、**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="31039-126">Right-click **Send Ports**, select **New**, and then select **Static Solicit-Response Send Port**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="31039-127">使用することも**静的な一方向ポート**です。</span><span class="sxs-lookup"><span data-stu-id="31039-127">You can also use **Static One-Way Port**.</span></span>  
  
3.  <span data-ttu-id="31039-128">**送信ポートのプロパティ**、select、**名前**フィールド、および送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="31039-128">In the **Send Port Properties**, select the **Name** field, and enter a send port name.</span></span> <span data-ttu-id="31039-129">たとえば、入力**SendToJDE**です。</span><span class="sxs-lookup"><span data-stu-id="31039-129">For example, enter **SendToJDE**.</span></span>  
  
4.  <span data-ttu-id="31039-130">**型**ドロップダウン リストで、 **[jdeoneworld]**です。</span><span class="sxs-lookup"><span data-stu-id="31039-130">In the **Type** drop-down list, select **JDEOneWorld**.</span></span>  
  
5.  <span data-ttu-id="31039-131">**URI**ドロップダウン リストで、送信ハンドラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="31039-131">In the **URI** drop-down list, select the send handler.</span></span>  
  
6.  <span data-ttu-id="31039-132">**[ OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="31039-132">Select **OK**.</span></span> 

## <a name="configure-the-transport-properties"></a><span data-ttu-id="31039-133">トランスポートのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="31039-133">Configure the transport properties</span></span>
<span data-ttu-id="31039-134">JD Edwards OneWorld の "トランスポート プロパティ" システム定義は、デザイン時および実行時のログオンに使用されます。</span><span class="sxs-lookup"><span data-stu-id="31039-134">The JD Edwards OneWorld Transport Property System Definition is used for design and run-time logon.</span></span> <span data-ttu-id="31039-135">この資格情報を設定するのは、デザイン時に JD Edwards OneWorld ビジネス関数を参照するためと、実行時に呼び出しを行うためです。</span><span class="sxs-lookup"><span data-stu-id="31039-135">You set these credentials to browse JD Edwards OneWorld business functions at design time and make calls at run time.</span></span>  
  
 <span data-ttu-id="31039-136">JD Edwards OneWorld への接続が作成されるときに、接続オブジェクトにパラメーターが渡されます (ユーザー、パスワード、環境)。</span><span class="sxs-lookup"><span data-stu-id="31039-136">When a connection is made to JD Edwards OneWorld, parameters are passed to the connection object (User, Password, Environment).</span></span> <span data-ttu-id="31039-137">JD Edwards OneWorld Application ビジネス関数のインスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="31039-137">It returns an instance of the JD Edwards OneWorld aApplication business function.</span></span> <span data-ttu-id="31039-138">資格情報には、さらにエンタープライズ サーバー/アプリケーション サーバーの名前、およびサービスがリッスンする定義済みの TCP/IP ポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="31039-138">The credentials are further defined by the name of the enterprise/application server, and the defined TCP/IP port on which the service listens.</span></span>  
  
 <span data-ttu-id="31039-139">エンタープライズ サーバーの名前とポートは、jdeinterop.ini というファイルから読み取られます。</span><span class="sxs-lookup"><span data-stu-id="31039-139">The enterprise server name and port are read from a file that is named jdeinterop.ini.</span></span> <span data-ttu-id="31039-140">これらの値は、システム定義での設定値と同一でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="31039-140">These values must be the same as those that are in the System Definition settings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31039-141">入力値はすべて、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="31039-141">All entries are case sensitive.</span></span>  
  
### <a name="set-the-properties"></a><span data-ttu-id="31039-142">プロパティを設定します</span><span class="sxs-lookup"><span data-stu-id="31039-142">Set the properties</span></span>  
 <span data-ttu-id="31039-143">**トランスポートのプロパティ**ダイアログ ボックスで、サーバーのシステムおよびアクセスしようとしているオブジェクトに固有の接続および資格情報パラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="31039-143">In the **Transport Properties** dialog box, you set the connection and credential parameters that are specific to the server system and the objects you are trying to access.</span></span>  
  
1.  <span data-ttu-id="31039-144">資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="31039-144">Provide credentials.</span></span> <span data-ttu-id="31039-145">JD Edwards OneWorld システムにアクセスするには、次の方法があります。</span><span class="sxs-lookup"><span data-stu-id="31039-145">You can access the JD Edwards OneWorld system using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="31039-146">ログオン資格情報 (パスワード、ユーザー名): このメソッドを使用する場合は、手順 5. に進みます。</span><span class="sxs-lookup"><span data-stu-id="31039-146">Logon credentials (Password, User name): If you use this method, go to step 5.</span></span>  
  
    -   <span data-ttu-id="31039-147">シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="31039-147">Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="31039-148">シングル サインオン (SSO) を使用するのには、選択**はい**で、 **SSO を使用する**です。</span><span class="sxs-lookup"><span data-stu-id="31039-148">To use Single Sign-On (SSO), select **Yes** in the **Use SSO**.</span></span>  
  
     <span data-ttu-id="31039-149">SSO を設定する方法の詳細については、次を参照してください[アダプターのセキュリティ。](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)</span><span class="sxs-lookup"><span data-stu-id="31039-149">For more information about how to set up SSO, see [Security in the adapter](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)</span></span>  
  
3.  <span data-ttu-id="31039-150">一覧で関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="31039-150">Select an affiliate application in the list.</span></span>  
  
     <span data-ttu-id="31039-151">エンタープライズ シングル サインオンのツールによって作成される関連アプリケーションはそれぞれ、JD Edwards OneWorld などの特定のアプリケーションを表します。</span><span class="sxs-lookup"><span data-stu-id="31039-151">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as JD Edwards OneWorld.</span></span> <span data-ttu-id="31039-152">Microsoft BizTalk Adapter for JD Edwards OneWorld では、アプリケーション ユーザーの資格情報が使用されます。</span><span class="sxs-lookup"><span data-stu-id="31039-152">Microsoft BizTalk Adapter for JD Edwards OneWorld uses the credentials of an application user.</span></span> <span data-ttu-id="31039-153">この資格情報は、指定された関連アプリケーションのサーバー システムの SSO 資格情報データベースから取得されます。</span><span class="sxs-lookup"><span data-stu-id="31039-153">These credentials are retrieved from the SSO Credentials database for the server system for a specified affiliate application.</span></span> <span data-ttu-id="31039-154">取得される資格情報は、BizTalk Server プロジェクトを起動したアプリケーション ユーザーの資格情報です。</span><span class="sxs-lookup"><span data-stu-id="31039-154">The credentials are those of the application user who launched the BizTalk Server project.</span></span>  
  
     <span data-ttu-id="31039-155">詳細については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications3.md)です。</span><span class="sxs-lookup"><span data-stu-id="31039-155">For more information, see [Creating Affiliate Applications](../core/creating-affiliate-applications3.md).</span></span>  
  
4.  <span data-ttu-id="31039-156">展開して、 **JD Edwards OneWorld システム**ノードと JD Edwards OneWorld サーバーに接続に必要なすべての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="31039-156">Expand the **JD Edwards OneWorld system** node and enter all required information for connection to the JD Edwards OneWorld server.</span></span>  
  
     ![](../core/media/jdedadapter-02-jdesystem.gif "JDEdAdapter_02_JDESystem")  
  
     <span data-ttu-id="31039-157">接続パラメーターの設定が完了すると、JD Edwards OneWorld システムの内容を参照できるようになります。</span><span class="sxs-lookup"><span data-stu-id="31039-157">After you set the connection parameters, you can browse a JD Edwards OneWorld system.</span></span> <span data-ttu-id="31039-158">詳細については、次を参照してください。[を BizTalk Server プロジェクトに JD Edwards OneWorld スキーマをインポートする](../core/importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md)です。</span><span class="sxs-lookup"><span data-stu-id="31039-158">For more information, see [Importing JD Edwards OneWorld Schemas into BizTalk Server Projects](../core/importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md).</span></span>  
  
5.  <span data-ttu-id="31039-159">呼び出し、たとえば 200 の数を示す値を入力**Max Concurrent Calls**必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="31039-159">Enter a value representing the number of calls, for example 200, in **Max Concurrent Calls** if it is required.</span></span>  
  
     <span data-ttu-id="31039-160">`Max Concurrent Calls`パラメーターを使用して、構成を最適化することができます。</span><span class="sxs-lookup"><span data-stu-id="31039-160">The `Max Concurrent Calls` parameter lets you optimize your configuration.</span></span> <span data-ttu-id="31039-161">スループットがバックエンドの処理能力を上回る場合に、このパラメーターを使用してメッセージ オーバーロード保護をアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="31039-161">You use this parameter in instances where the throughput exceeds back-end processing capabilities, to activate message-overload protection.</span></span> <span data-ttu-id="31039-162">既定値は -1 で、これは呼び出しの数が無制限であることを示します。</span><span class="sxs-lookup"><span data-stu-id="31039-162">The default is -1, which means that the calls are unlimited.</span></span>  
  
     <span data-ttu-id="31039-163">BizTalk Server が送信アダプターにメッセージを送信するときに、BizTalk Server は最初にアダプターからバッチを 1 つ受け取ります。</span><span class="sxs-lookup"><span data-stu-id="31039-163">When BizTalk Server submits messages to the transmit adapter, it first receives a batch from the adapter.</span></span> <span data-ttu-id="31039-164">`TransmitMessage` をそのバッチに対して起動して、各メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="31039-164">It invokes `TransmitMessage` on the batch to transmit each message.</span></span> <span data-ttu-id="31039-165">この処理が完了すると、BizTalk Server はバッチで `Done` を呼び出し、アダプタがバックエンドに対するメッセージ送信を開始します。</span><span class="sxs-lookup"><span data-stu-id="31039-165">When done, BizTalk Server invokes `Done` on the batch, and the adapter starts transmitting the messages to the back-end.</span></span> <span data-ttu-id="31039-166">BizTalk Server が複数のバッチを受け取ってから `Done` を呼び出しても、メッセージは送信されません。</span><span class="sxs-lookup"><span data-stu-id="31039-166">If BizTalk Server obtains multiple batches before invoking `Done`, it might never occur.</span></span> <span data-ttu-id="31039-167">バッチ内に含めるメッセージの最大数を設定することで、バックエンドに送信するメッセージを制御できます。</span><span class="sxs-lookup"><span data-stu-id="31039-167">By setting the maximum number of messages in a batch, you can control messages to the back-end.</span></span>  
  
     <span data-ttu-id="31039-168">このパラメーターの変更が反映されるまで最大 1 分程度かかります。BizTalk Server は、SQL データベースに保存されたアダプター構成に対する変更を取得する必要があるからです。</span><span class="sxs-lookup"><span data-stu-id="31039-168">Changing this parameter takes effect within one minute; BizTalk Server must retrieve the changes to the adapter configuration saved in the SQL database.</span></span>  
  
6.  <span data-ttu-id="31039-169">選択**はい**の**エージェントの更新**runtimeagent.exe および browsingagent.exe の処理を必要時に自動的に再起動を強制します。</span><span class="sxs-lookup"><span data-stu-id="31039-169">Select **Yes** for **Refresh Agent** to force the runtimeagent.exe and the browsingagent.exe processes to restart automatically when required.</span></span>  
  
     <span data-ttu-id="31039-170">たとえば、サーバーとの接続が失われた場合や、サーバーに追加したものが Microsoft アダプター ウィザードに表示されない場合に、処理を自動的に再起動することができます。</span><span class="sxs-lookup"><span data-stu-id="31039-170">For example, you want the process to restart automatically if it loses connection with the server, or if you add something to the server and it does not appear in the Microsoft Adapter Wizard for selection.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="31039-171">browsingagent.exe が最新の状態に更新されるのは、ユーザーが現在の参照セッションを終了したときです。</span><span class="sxs-lookup"><span data-stu-id="31039-171">The browsingagent.exe does not refresh until you exit the current browsing session.</span></span> <span data-ttu-id="31039-172">たとえば、終了する必要があります、**項目の生成された追加**参照セッションとを browsingagent.exe を更新します。</span><span class="sxs-lookup"><span data-stu-id="31039-172">For example, you must exit the **Add generated item** browsing session and reenter to update the browsingagent.exe.</span></span>  
  
7.  <span data-ttu-id="31039-173">必要なすべての情報を提供すると、をクリックして**適用**、クリックして**[ok]**の接続情報を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="31039-173">After providing all required information, click **Apply**, and then click **OK** to accept the connection information.</span></span>  
  
     <span data-ttu-id="31039-174">JD Edwards OneWorld にアクセスするには、BizTalk Adapter for JD Edwards OneWorld の接続パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31039-174">You must set connection parameters for BizTalk Adapter for JD Edwards OneWorld to access JD Edwards OneWorld.</span></span>  
  
### <a name="adapter-required-properties"></a><span data-ttu-id="31039-175">必要なアダプターのプロパティ</span><span class="sxs-lookup"><span data-stu-id="31039-175">Adapter required properties</span></span>  
 <span data-ttu-id="31039-176">コントロール パネルでグローバル環境変数を設定しなかった場合は、このセクションで設定できます。</span><span class="sxs-lookup"><span data-stu-id="31039-176">If you did not set global environment variables in Control Panel, you can do so in this section.</span></span>  
  
|<span data-ttu-id="31039-177">パラメーター</span><span class="sxs-lookup"><span data-stu-id="31039-177">Parameter</span></span>|<span data-ttu-id="31039-178">Description</span><span class="sxs-lookup"><span data-stu-id="31039-178">Description</span></span>|  
|---------------|-----------------|  
|`Host`|<span data-ttu-id="31039-179">ホスト サーバーのコンピューター名の名前を入力 (たとえば、 `actsvr1`); またはコンピューターの IP アドレス (たとえば、 `123.456.0.789`)。</span><span class="sxs-lookup"><span data-stu-id="31039-179">Type the name of the host server computer name (for example, `actsvr1`); or the IP address of the computer (for example, `123.456.0.789`).</span></span>|  
|<span data-ttu-id="31039-180">JAVA_HOME</span><span class="sxs-lookup"><span data-stu-id="31039-180">JAVA_HOME</span></span>|<span data-ttu-id="31039-181">JDK インストール ディレクトリの完全パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="31039-181">Type the complete path of your JDK installation.</span></span>|  
|<span data-ttu-id="31039-182">JD Edwards 環境</span><span class="sxs-lookup"><span data-stu-id="31039-182">JDE Edwards Environment</span></span>|<span data-ttu-id="31039-183">たとえば、JD Edwards OneWorld の環境の名前を入力`DV7333`です。</span><span class="sxs-lookup"><span data-stu-id="31039-183">Type the name of an environment in JD Edwards OneWorld, for example, `DV7333`.</span></span><br /><br /> <span data-ttu-id="31039-184">DV7333 は開発環境の一般名、PY7333 はプロトタイプ環境の一般名、PD7333 は実稼働環境の一般名です。</span><span class="sxs-lookup"><span data-stu-id="31039-184">DV7333 is a common name for the development environment, PY7333 is common for the prototype environment, and PD7333 is common for the production environment.</span></span>|  
|<span data-ttu-id="31039-185">JDEdwards JAR ファイル</span><span class="sxs-lookup"><span data-stu-id="31039-185">JDEdwards JAR Files</span></span>|<span data-ttu-id="31039-186">各 JAR ファイルの完全なパスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="31039-186">Enter the complete path and file name for each JAR file:</span></span><br /><br /> <span data-ttu-id="31039-187">-Connector.jar</span><span class="sxs-lookup"><span data-stu-id="31039-187">-   Connector.jar</span></span><br /><span data-ttu-id="31039-188">-Kernel.jar</span><span class="sxs-lookup"><span data-stu-id="31039-188">-   Kernel.jar</span></span><br /><span data-ttu-id="31039-189">-JDEJAccess.jar</span><span class="sxs-lookup"><span data-stu-id="31039-189">-   JDEJAccess.jar</span></span><br /><span data-ttu-id="31039-190">-JDEActionalInterop.jar</span><span class="sxs-lookup"><span data-stu-id="31039-190">-   JDEActionalInterop.jar</span></span><br /><br /> <span data-ttu-id="31039-191">jar ファイルの区切りにはセミコロン (;) を使用し、スペースは入れません。</span><span class="sxs-lookup"><span data-stu-id="31039-191">Each jar file must be separated with a semi-colon (;) and no space.</span></span> <span data-ttu-id="31039-192">例:</span><span class="sxs-lookup"><span data-stu-id="31039-192">For example:</span></span><br /><br /> `<drive>\Connector.jar;<drive>\Kernel.jar;`|  
|<span data-ttu-id="31039-193">Password</span><span class="sxs-lookup"><span data-stu-id="31039-193">Password</span></span>|<span data-ttu-id="31039-194">指定されたユーザーのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="31039-194">Type the password of the specified user.</span></span>|  
|<span data-ttu-id="31039-195">ポート</span><span class="sxs-lookup"><span data-stu-id="31039-195">Port</span></span>|<span data-ttu-id="31039-196">データを交換するポート番号を入力 (たとえば、 `6009`)。</span><span class="sxs-lookup"><span data-stu-id="31039-196">Type the port number that will exchange data (for example, `6009`).</span></span>|  
|<span data-ttu-id="31039-197">[ユーザー名]</span><span class="sxs-lookup"><span data-stu-id="31039-197">User Name</span></span>|<span data-ttu-id="31039-198">JD Edwards OneWorld システムへのログオンに使用する JD Edwards OneWorld ユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="31039-198">Type a JD Edwards OneWorld user name that will be used to log on to the JD Edwards OneWorld system.</span></span>|  

## <a name="use-the-xmltransmit-and-xmlreceive-pipelines"></a><span data-ttu-id="31039-199">XMLTransmit および XMLReceive パイプラインを使用します</span><span class="sxs-lookup"><span data-stu-id="31039-199">Use the XMLTransmit and XMLReceive pipelines</span></span>
<span data-ttu-id="31039-200">Microsoft BizTalk Adapter for JD Edwards OneWorld では、送信、XMLTransmit および XMLReceive を選択し、受信パイプラインが必要です。</span><span class="sxs-lookup"><span data-stu-id="31039-200">Microsoft BizTalk Adapter for JD Edwards OneWorld requires that you select XMLTransmit and XMLReceive for the send and receive pipelines.</span></span>  
  
1.  <span data-ttu-id="31039-201">**BizTalk Server 管理コンソール**、展開**アプリケーション**、し、アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="31039-201">In **BizTalk Server Administration**, expand **Applications**, and then expand your application.</span></span>  
  
2.  <span data-ttu-id="31039-202">選択**送信ポート**を送信ポートを右クリックし、**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="31039-202">Select **Send Ports**, right-click your send port, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="31039-203">**送信ポート プロパティ**を次の操作します。</span><span class="sxs-lookup"><span data-stu-id="31039-203">In the **Send Ports Properties**, do the following:</span></span>  
  
    1.  <span data-ttu-id="31039-204">送信パイプラインを選択して、**送信パイプライン**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="31039-204">Select the send pipeline from the **Send Pipeline** drop-down list.</span></span>  
  
    2.  <span data-ttu-id="31039-205">受信パイプラインを選択、**受信パイプライン**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="31039-205">Select the Receive pipeline from the **Receive Pipeline** drop-down list.</span></span>  
  
4.  <span data-ttu-id="31039-206">**[ OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="31039-206">Select **OK**.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="31039-207">次の手順</span><span class="sxs-lookup"><span data-stu-id="31039-207">Next steps</span></span>
[<span data-ttu-id="31039-208">Visual Studio にアダプター スキーマをインポートします。</span><span class="sxs-lookup"><span data-stu-id="31039-208">Import adapter schemas into Visual Studio</span></span>](importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md)  
[<span data-ttu-id="31039-209">メッセージ コンテキストのプロパティの使用</span><span class="sxs-lookup"><span data-stu-id="31039-209">Use Message Context Properties</span></span>](using-message-context-properties2.md)