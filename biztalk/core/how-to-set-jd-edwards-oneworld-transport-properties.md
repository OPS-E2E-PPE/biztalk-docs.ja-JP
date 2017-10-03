---
title: "JD Edwards OneWorld トランスポートのプロパティを設定する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setting transport properties
- transport properties, setting
ms.assetid: 6d38088b-a496-414e-aae6-d28c5d6398b6
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7abac3b468b8c76b8214e400366144b39f1e2741
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-jd-edwards-oneworld-transport-properties"></a><span data-ttu-id="7a903-102">JD Edwards OneWorld トランスポートのプロパティを設定する方法</span><span class="sxs-lookup"><span data-stu-id="7a903-102">How to Set JD Edwards OneWorld Transport Properties</span></span>
<span data-ttu-id="7a903-103">JD Edwards OneWorld の "トランスポート プロパティ" システム定義は、デザイン時および実行時のログオンに使用されます。</span><span class="sxs-lookup"><span data-stu-id="7a903-103">The JD Edwards OneWorld Transport Property System Definition is used for design and run-time logon.</span></span> <span data-ttu-id="7a903-104">この資格情報を設定するのは、デザイン時に JD Edwards OneWorld ビジネス関数を参照するためと、実行時に呼び出しを行うためです。</span><span class="sxs-lookup"><span data-stu-id="7a903-104">You set these credentials to browse JD Edwards OneWorld business functions at design time and make calls at run time.</span></span>  
  
 <span data-ttu-id="7a903-105">JD Edwards OneWorld への接続が作成されるときに、接続オブジェクトにパラメーターが渡されます (ユーザー、パスワード、環境)。</span><span class="sxs-lookup"><span data-stu-id="7a903-105">When a connection is made to JD Edwards OneWorld, parameters are passed to the connection object (User, Password, Environment).</span></span> <span data-ttu-id="7a903-106">JD Edwards OneWorld Application ビジネス関数のインスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="7a903-106">It returns an instance of the JD Edwards OneWorld aApplication business function.</span></span> <span data-ttu-id="7a903-107">資格情報には、さらにエンタープライズ サーバー/アプリケーション サーバーの名前、およびサービスがリッスンする定義済みの TCP/IP ポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7a903-107">The credentials are further defined by the name of the enterprise/application server, and the defined TCP/IP port on which the service listens.</span></span>  
  
 <span data-ttu-id="7a903-108">エンタープライズ サーバーの名前とポートは、jdeinterop.ini というファイルから読み取られます。</span><span class="sxs-lookup"><span data-stu-id="7a903-108">The enterprise server name and port are read from a file that is named jdeinterop.ini.</span></span> <span data-ttu-id="7a903-109">これらの値は、システム定義での設定値と同一でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="7a903-109">These values must be the same as those that are in the System Definition settings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a903-110">入力値はすべて、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="7a903-110">All entries are case sensitive.</span></span>  
  
## <a name="setting-properties"></a><span data-ttu-id="7a903-111">プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="7a903-111">Setting Properties</span></span>  
 <span data-ttu-id="7a903-112">**トランスポートのプロパティ**ダイアログ ボックスで、サーバーのシステムおよびアクセスしようとしているオブジェクトに固有の接続および資格情報パラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="7a903-112">In the **Transport Properties** dialog box, you set the connection and credential parameters that are specific to the server system and the objects you are trying to access.</span></span>  
  
 <span data-ttu-id="7a903-113">このプロセスの手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7a903-113">The steps in this process are as follows:</span></span>  
  
#### <a name="to-set-transport-properties"></a><span data-ttu-id="7a903-114">トランスポートのプロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="7a903-114">To set transport properties</span></span>  
  
1.  <span data-ttu-id="7a903-115">資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="7a903-115">Provide credentials.</span></span>  
  
     <span data-ttu-id="7a903-116">JD Edwards OneWorld システムにアクセスするには、次の方法があります。</span><span class="sxs-lookup"><span data-stu-id="7a903-116">You can access the JD Edwards OneWorld system using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="7a903-117">ログオン資格情報 (パスワード、ユーザー名): このメソッドを使用する場合は、手順 5. に進みます。</span><span class="sxs-lookup"><span data-stu-id="7a903-117">Logon credentials (Password, User name): If you use this method, go to step 5.</span></span>  
  
    -   <span data-ttu-id="7a903-118">シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="7a903-118">Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="7a903-119">シングル サインオン (SSO) を使用するのには、選択**はい**で、 **SSO を使用する**です。</span><span class="sxs-lookup"><span data-stu-id="7a903-119">To use Single Sign-On (SSO), select **Yes** in the **Use SSO**.</span></span>  
  
     <span data-ttu-id="7a903-120">SSO を設定する方法の詳細については、次を参照してください。[シングル サインオンを使用して](../core/using-single-sign-on3.md)です。</span><span class="sxs-lookup"><span data-stu-id="7a903-120">For more information about how to set up SSO, see [Using Single Sign-On](../core/using-single-sign-on3.md).</span></span>  
  
3.  <span data-ttu-id="7a903-121">一覧で関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7a903-121">Select an affiliate application in the list.</span></span>  
  
     <span data-ttu-id="7a903-122">エンタープライズ シングル サインオンのツールによって作成される関連アプリケーションはそれぞれ、JD Edwards OneWorld などの特定のアプリケーションを表します。</span><span class="sxs-lookup"><span data-stu-id="7a903-122">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as JD Edwards OneWorld.</span></span> <span data-ttu-id="7a903-123">Microsoft BizTalk Adapter for JD Edwards OneWorld では、アプリケーション ユーザーの資格情報が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7a903-123">Microsoft BizTalk Adapter for JD Edwards OneWorld uses the credentials of an application user.</span></span> <span data-ttu-id="7a903-124">この資格情報は、指定された関連アプリケーションのサーバー システムの SSO 資格情報データベースから取得されます。</span><span class="sxs-lookup"><span data-stu-id="7a903-124">These credentials are retrieved from the SSO Credentials database for the server system for a specified affiliate application.</span></span> <span data-ttu-id="7a903-125">取得される資格情報は、BizTalk Server プロジェクトを起動したアプリケーション ユーザーの資格情報です。</span><span class="sxs-lookup"><span data-stu-id="7a903-125">The credentials are those of the application user who launched the BizTalk Server project.</span></span>  
  
     <span data-ttu-id="7a903-126">詳細については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications3.md)です。</span><span class="sxs-lookup"><span data-stu-id="7a903-126">For more information, see [Creating Affiliate Applications](../core/creating-affiliate-applications3.md).</span></span>  
  
4.  <span data-ttu-id="7a903-127">展開して、 **JD Edwards OneWorld システム**ノードと JD Edwards OneWorld サーバーに接続に必要なすべての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="7a903-127">Expand the **JD Edwards OneWorld system** node and enter all required information for connection to the JD Edwards OneWorld server.</span></span>  
  
     ![](../core/media/jdedadapter-02-jdesystem.gif "JDEdAdapter_02_JDESystem")  
  
     <span data-ttu-id="7a903-128">接続パラメーターの設定が完了すると、JD Edwards OneWorld システムの内容を参照できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7a903-128">After you set the connection parameters, you can browse a JD Edwards OneWorld system.</span></span> <span data-ttu-id="7a903-129">詳細については、次を参照してください。[を BizTalk Server プロジェクトに JD Edwards OneWorld スキーマをインポートする](../core/importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md)です。</span><span class="sxs-lookup"><span data-stu-id="7a903-129">For more information, see [Importing JD Edwards OneWorld Schemas into BizTalk Server Projects](../core/importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md).</span></span>  
  
5.  <span data-ttu-id="7a903-130">呼び出し、たとえば 200 の数を示す値を入力**Max Concurrent Calls**必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="7a903-130">Enter a value representing the number of calls, for example 200, in **Max Concurrent Calls** if it is required.</span></span>  
  
     <span data-ttu-id="7a903-131">`Max Concurrent Calls`パラメーターを使用して、構成を最適化することができます。</span><span class="sxs-lookup"><span data-stu-id="7a903-131">The `Max Concurrent Calls` parameter lets you optimize your configuration.</span></span> <span data-ttu-id="7a903-132">スループットがバックエンドの処理能力を上回る場合に、このパラメーターを使用してメッセージ オーバーロード保護をアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="7a903-132">You use this parameter in instances where the throughput exceeds back-end processing capabilities, to activate message-overload protection.</span></span> <span data-ttu-id="7a903-133">既定値は -1 で、これは呼び出しの数が無制限であることを示します。</span><span class="sxs-lookup"><span data-stu-id="7a903-133">The default is -1, which means that the calls are unlimited.</span></span>  
  
     <span data-ttu-id="7a903-134">BizTalk Server が送信アダプターにメッセージを送信するときに、BizTalk Server は最初にアダプターからバッチを 1 つ受け取ります。</span><span class="sxs-lookup"><span data-stu-id="7a903-134">When BizTalk Server submits messages to the transmit adapter, it first receives a batch from the adapter.</span></span> <span data-ttu-id="7a903-135">`TransmitMessage` をそのバッチに対して起動して、各メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="7a903-135">It invokes `TransmitMessage` on the batch to transmit each message.</span></span> <span data-ttu-id="7a903-136">この処理が完了すると、BizTalk Server はバッチで `Done` を呼び出し、アダプタがバックエンドに対するメッセージ送信を開始します。</span><span class="sxs-lookup"><span data-stu-id="7a903-136">When done, BizTalk Server invokes `Done` on the batch, and the adapter starts transmitting the messages to the back-end.</span></span> <span data-ttu-id="7a903-137">BizTalk Server が複数のバッチを受け取ってから `Done` を呼び出しても、メッセージは送信されません。</span><span class="sxs-lookup"><span data-stu-id="7a903-137">If BizTalk Server obtains multiple batches before invoking `Done`, it might never occur.</span></span> <span data-ttu-id="7a903-138">バッチ内に含めるメッセージの最大数を設定することで、バックエンドに送信するメッセージを制御できます。</span><span class="sxs-lookup"><span data-stu-id="7a903-138">By setting the maximum number of messages in a batch, you can control messages to the back-end.</span></span>  
  
     <span data-ttu-id="7a903-139">このパラメーターの変更が反映されるまで最大 1 分程度かかります。BizTalk Server は、SQL データベースに保存されたアダプター構成に対する変更を取得する必要があるからです。</span><span class="sxs-lookup"><span data-stu-id="7a903-139">Changing this parameter takes effect within one minute; BizTalk Server must retrieve the changes to the adapter configuration saved in the SQL database.</span></span>  
  
6.  <span data-ttu-id="7a903-140">選択**はい**の**エージェントの更新**runtimeagent.exe および browsingagent.exe の処理を必要時に自動的に再起動を強制します。</span><span class="sxs-lookup"><span data-stu-id="7a903-140">Select **Yes** for **Refresh Agent** to force the runtimeagent.exe and the browsingagent.exe processes to restart automatically when required.</span></span>  
  
     <span data-ttu-id="7a903-141">たとえば、サーバーとの接続が失われた場合や、サーバーに追加したものが Microsoft アダプター ウィザードに表示されない場合に、処理を自動的に再起動することができます。</span><span class="sxs-lookup"><span data-stu-id="7a903-141">For example, you want the process to restart automatically if it loses connection with the server, or if you add something to the server and it does not appear in the Microsoft Adapter Wizard for selection.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a903-142">browsingagent.exe が最新の状態に更新されるのは、ユーザーが現在の参照セッションを終了したときです。</span><span class="sxs-lookup"><span data-stu-id="7a903-142">The browsingagent.exe does not refresh until you exit the current browsing session.</span></span> <span data-ttu-id="7a903-143">たとえば、終了する必要があります、**項目の生成された追加**参照セッションとを browsingagent.exe を更新します。</span><span class="sxs-lookup"><span data-stu-id="7a903-143">For example, you must exit the **Add generated item** browsing session and reenter to update the browsingagent.exe.</span></span>  
  
7.  <span data-ttu-id="7a903-144">必要なすべての情報を提供すると、をクリックして**適用**、クリックして**[ok]**の接続情報を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="7a903-144">After providing all required information, click **Apply**, and then click **OK** to accept the connection information.</span></span>  
  
     <span data-ttu-id="7a903-145">JD Edwards OneWorld にアクセスするには、BizTalk Adapter for JD Edwards OneWorld の接続パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a903-145">You must set connection parameters for BizTalk Adapter for JD Edwards OneWorld to access JD Edwards OneWorld.</span></span>  
  
### <a name="adapter-required-properties"></a><span data-ttu-id="7a903-146">アダプターに必要なプロパティ</span><span class="sxs-lookup"><span data-stu-id="7a903-146">Adapter Required Properties</span></span>  
 <span data-ttu-id="7a903-147">コントロール パネルでグローバル環境変数を設定しなかった場合は、このセクションで設定できます。</span><span class="sxs-lookup"><span data-stu-id="7a903-147">If you did not set global environment variables in Control Panel, you can do so in this section.</span></span>  
  
|<span data-ttu-id="7a903-148">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7a903-148">Parameter</span></span>|<span data-ttu-id="7a903-149">Description</span><span class="sxs-lookup"><span data-stu-id="7a903-149">Description</span></span>|  
|---------------|-----------------|  
|`Host`|<span data-ttu-id="7a903-150">ホスト サーバーのコンピューター名の名前を入力 (たとえば、 `actsvr1`); またはコンピューターの IP アドレス (たとえば、 `123.456.0.789`)。</span><span class="sxs-lookup"><span data-stu-id="7a903-150">Type the name of the host server computer name (for example, `actsvr1`); or the IP address of the computer (for example, `123.456.0.789`).</span></span>|  
|<span data-ttu-id="7a903-151">JAVA_HOME</span><span class="sxs-lookup"><span data-stu-id="7a903-151">JAVA_HOME</span></span>|<span data-ttu-id="7a903-152">JDK インストール ディレクトリの完全パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="7a903-152">Type the complete path of your JDK installation.</span></span>|  
|<span data-ttu-id="7a903-153">JD Edwards 環境</span><span class="sxs-lookup"><span data-stu-id="7a903-153">JDE Edwards Environment</span></span>|<span data-ttu-id="7a903-154">たとえば、JD Edwards OneWorld の環境の名前を入力`DV7333`です。</span><span class="sxs-lookup"><span data-stu-id="7a903-154">Type the name of an environment in JD Edwards OneWorld, for example, `DV7333`.</span></span><br /><br /> <span data-ttu-id="7a903-155">DV7333 は開発環境の一般名、PY7333 はプロトタイプ環境の一般名、PD7333 は実稼働環境の一般名です。</span><span class="sxs-lookup"><span data-stu-id="7a903-155">DV7333 is a common name for the development environment, PY7333 is common for the prototype environment, and PD7333 is common for the production environment.</span></span>|  
|<span data-ttu-id="7a903-156">JDEdwards JAR ファイル</span><span class="sxs-lookup"><span data-stu-id="7a903-156">JDEdwards JAR Files</span></span>|<span data-ttu-id="7a903-157">各 JAR ファイルの完全なパスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="7a903-157">Enter the complete path and file name for each JAR file:</span></span><br /><br /> <span data-ttu-id="7a903-158">-Connector.jar</span><span class="sxs-lookup"><span data-stu-id="7a903-158">-   Connector.jar</span></span><br /><span data-ttu-id="7a903-159">-Kernel.jar</span><span class="sxs-lookup"><span data-stu-id="7a903-159">-   Kernel.jar</span></span><br /><span data-ttu-id="7a903-160">-JDEJAccess.jar</span><span class="sxs-lookup"><span data-stu-id="7a903-160">-   JDEJAccess.jar</span></span><br /><span data-ttu-id="7a903-161">-JDEActionalInterop.jar</span><span class="sxs-lookup"><span data-stu-id="7a903-161">-   JDEActionalInterop.jar</span></span><br /><br /> <span data-ttu-id="7a903-162">jar ファイルの区切りにはセミコロン (;) を使用し、スペースは入れません。</span><span class="sxs-lookup"><span data-stu-id="7a903-162">Each jar file must be separated with a semi-colon (;) and no space.</span></span> <span data-ttu-id="7a903-163">例:</span><span class="sxs-lookup"><span data-stu-id="7a903-163">For example:</span></span><br /><br /> `<drive>\Connector.jar;<drive>\Kernel.jar;`|  
|<span data-ttu-id="7a903-164">Password</span><span class="sxs-lookup"><span data-stu-id="7a903-164">Password</span></span>|<span data-ttu-id="7a903-165">指定されたユーザーのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="7a903-165">Type the password of the specified user.</span></span>|  
|<span data-ttu-id="7a903-166">ポート</span><span class="sxs-lookup"><span data-stu-id="7a903-166">Port</span></span>|<span data-ttu-id="7a903-167">データを交換するポート番号を入力 (たとえば、 `6009`)。</span><span class="sxs-lookup"><span data-stu-id="7a903-167">Type the port number that will exchange data (for example, `6009`).</span></span>|  
|<span data-ttu-id="7a903-168">[ユーザー名]</span><span class="sxs-lookup"><span data-stu-id="7a903-168">User Name</span></span>|<span data-ttu-id="7a903-169">JD Edwards OneWorld システムへのログオンに使用する JD Edwards OneWorld ユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="7a903-169">Type a JD Edwards OneWorld user name that will be used to log on to the JD Edwards OneWorld system.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a903-170">参照</span><span class="sxs-lookup"><span data-stu-id="7a903-170">See Also</span></span>  
 [<span data-ttu-id="7a903-171">JD Edwards OneWorld 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="7a903-171">Creating JD Edwards OneWorld Send Handlers</span></span>](../core/creating-jd-edwards-oneworld-send-handlers.md)