---
title: "PeopleSoft アダプターの送信のアーティファクトを作成 |Microsoft ドキュメント"
description: "送信ポートを作成し、トランスポートのプロパティを送信し、BizTalk Server で PeopleSoft Enterprise アダプターを使用して PeopleSoft にメッセージを送信する最大同時呼び出しを更新"
ms.custom: 
ms.date: 10/19/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce67da59-26a6-44a2-929c-ed3acb21d407
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bc559f4e3c25560540a171b3f47ff25e6f34e89
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="create-peoplesoft-send-artifacts"></a><span data-ttu-id="9bda5-103">PeopleSoft 送信アイテムを作成します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-103">Create PeopleSoft send artifacts</span></span>
<span data-ttu-id="9bda5-104">Microsoft BizTalk Adapter for PeopleSoft Enterprise は、PeopleSoft にアクセスして、使用できるコンポーネントを探索したり、SOAP 要求を処理したりします。</span><span class="sxs-lookup"><span data-stu-id="9bda5-104">Microsoft BizTalk Adapter for PeopleSoft Enterprise accesses PeopleSoft and explores available components or processes SOAP requests.</span></span> <span data-ttu-id="9bda5-105">このトピックでは、PeopleSoft アダプターを使用する BizTalk Server 管理コンソールで、送信の成果物を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-105">This topic shows you how to create the send artifacts in BizTalk Server Administration to use the PeopleSoft adapter.</span></span>


## <a name="create-the-send-port"></a><span data-ttu-id="9bda5-106">送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-106">Create the send port</span></span>

1.  <span data-ttu-id="9bda5-107">BizTalk Server 管理コンソールで、展開**BizTalk グループ**、展開**アプリケーション**、し、目的のアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-107">In the BizTalk Server Administration Console,expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="9bda5-108">右クリック**送信ポート****新規**、し、**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="9bda5-108">Right-click **Send Ports**, select **New**, and then select **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="9bda5-109">**送信ポートのプロパティ**次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9bda5-109">In the **Send Port Properties**, do the following:</span></span>  
  
    1.  <span data-ttu-id="9bda5-110">送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-110">Enter a name for the send port.</span></span> <span data-ttu-id="9bda5-111">たとえば、入力`SSOSendToPeopleSoft`です。</span><span class="sxs-lookup"><span data-stu-id="9bda5-111">For example, enter `SSOSendToPeopleSoft`.</span></span>  
  
    2.  <span data-ttu-id="9bda5-112">**型**ドロップダウン リストで、 **PeopleSoft**です。</span><span class="sxs-lookup"><span data-stu-id="9bda5-112">From the **Type** drop-down list, select **PeopleSoft**.</span></span>  
  
    3.  <span data-ttu-id="9bda5-113">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-113">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="9bda5-114">送信パイプラインのドロップダウン リストから選択**[microsoft.biztalk.defaultpipelines.xmltransmit]**です。</span><span class="sxs-lookup"><span data-stu-id="9bda5-114">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="9bda5-115">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]**です。</span><span class="sxs-lookup"><span data-stu-id="9bda5-115">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="9bda5-116">選択**構成**送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-116">Select **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="9bda5-117">**PeopleSoft トランスポートのプロパティ**次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9bda5-117">In the **PeopleSoft Transport Properties**, do the following:</span></span>  
  
    1.  <span data-ttu-id="9bda5-118">展開**アダプターに必要なプロパティ**、入力と**アプリケーション サーバーのパス**、 **JAVA_HOME**、**ユーザー名**、 **パスワード**、および Peoplesoft システムに接続するための Jar ファイルです。</span><span class="sxs-lookup"><span data-stu-id="9bda5-118">Expand **Adapter Required Properties**, and enter **Application Server Path**, **JAVA_HOME**, **user name**, **password**, and the Jar file for connecting into the Peoplesoft system.</span></span>  
  
         <span data-ttu-id="9bda5-119">ログオン情報を設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9bda5-119">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="9bda5-120">一覧で、PeopleSoft システムを表すよう作成した SSO 関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-120">In the list, select the SSO affiliate application you created to represent the PeopleSoft system.</span></span>  
  
    3.  <span data-ttu-id="9bda5-121">**SSO を使用する****はい**です。</span><span class="sxs-lookup"><span data-stu-id="9bda5-121">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="9bda5-122">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-122">Select **OK**.</span></span>  
  
5.  <span data-ttu-id="9bda5-123">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-123">Select **OK**.</span></span>

## <a name="set-the-transport-properties"></a><span data-ttu-id="9bda5-124">トランスポートのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-124">Set the transport properties</span></span>
<span data-ttu-id="9bda5-125">PeopleSoft トランスポートのプロパティは、設計時および実行時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="9bda5-125">The PeopleSoft transport properties are used for design and run time.</span></span> <span data-ttu-id="9bda5-126">**トランスポートのプロパティ**ダイアログ ボックスで、パラメーターを設定する接続と資格情報を特定サーバーのシステムおよびアクセスしようとしているオブジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="9bda5-126">In the **Transport Properties** dialog box, you set the connection and credential parameters specific to the server system and the objects you are trying to access.</span></span>  
  
 <span data-ttu-id="9bda5-127">![](../core/media/peop-peoplesofttransportpropertiess.gif "Peop_PeopleSoftTransportPropertiess")</span><span class="sxs-lookup"><span data-stu-id="9bda5-127">![](../core/media/peop-peoplesofttransportpropertiess.gif "Peop_PeopleSoftTransportPropertiess")</span></span>  
  
1.  <span data-ttu-id="9bda5-128">[アダプターに必要なプロパティ] を展開し、PeopleSoft サーバーへの接続に必要なすべての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-128">Expand the Adapter Required Properties and fill in all required information for connection to the PeopleSoft server.</span></span>  
  
     <span data-ttu-id="9bda5-129">Microsoft BizTalk Adapter for PeopleSoft Enterprise を PeopleSoft Enterprise に接続するには、構成パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bda5-129">You must set configuration parameters to connect Microsoft BizTalk Adapter for PeopleSoft Enterprise to PeopleSoft Enterprise.</span></span> <span data-ttu-id="9bda5-130">このデータは、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="9bda5-130">This data is case sensitive.</span></span>  
  
    |<span data-ttu-id="9bda5-131">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9bda5-131">Parameter</span></span>|<span data-ttu-id="9bda5-132">Description</span><span class="sxs-lookup"><span data-stu-id="9bda5-132">Description</span></span>|  
    |---------------|-----------------|  
    |`Application Server Path`|<span data-ttu-id="9bda5-133">PeopleSoft Application Server が動作して受信を待ち受けているコンピューターおよびポートを表す文字列。</span><span class="sxs-lookup"><span data-stu-id="9bda5-133">A string representing the computer and port on which the PeopleSoft Application Server is running and listening.</span></span> <span data-ttu-id="9bda5-134">PeopleSoft 8 Application への URL パスの構文は//< computer_name >:\<ポート\>です。</span><span class="sxs-lookup"><span data-stu-id="9bda5-134">The syntax of the URL path to the PeopleSoft 8 Application is //<computer_name>:\<port\>.</span></span> <span data-ttu-id="9bda5-135">PeopleSoft 管理者に問い合わせて、\<ポート\>値。</span><span class="sxs-lookup"><span data-stu-id="9bda5-135">Ask your PeopleSoft administrator for the \<port\> value.</span></span> <span data-ttu-id="9bda5-136">\<ポート\>値は、JOLT プロトコル リスナー ポート、App Server ポートではありません。</span><span class="sxs-lookup"><span data-stu-id="9bda5-136">The \<port\> value is the JOLT protocol listener port, not the App Server port.</span></span> <span data-ttu-id="9bda5-137">既定の JOLT ポートは 9000 です。</span><span class="sxs-lookup"><span data-stu-id="9bda5-137">The default JOLT port is 9000.</span></span>|  
    |`JAVA_HOME`|<span data-ttu-id="9bda5-138">たとえば、JDK インストールを指すように JAVA_HOME 変数を設定します。 **C:\j2sdk1.4.2_08**です。</span><span class="sxs-lookup"><span data-stu-id="9bda5-138">Set the JAVA_HOME variable to point to your JDK installation, for example: **C:\j2sdk1.4.2_08**.</span></span>|  
    |`Password`|<span data-ttu-id="9bda5-139">選択しなかった場合**SSO を使用する**、BizTalk Adapter for PeopleSoft Enterprise サーバー システムにアクセスするための資格情報パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bda5-139">If you did not select **Use SSO**, you must set credential parameters for the BizTalk Adapter for PeopleSoft Enterprise to access the server system.</span></span><br /><br /> <span data-ttu-id="9bda5-140">PeopleSoft システムへのログオンに使用するユーザーのパスワードを表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="9bda5-140">A string representing the user's password for logon to a PeopleSoft system.</span></span> <span data-ttu-id="9bda5-141">文字は表示されませんが、アスタリスク (*) で表されます。</span><span class="sxs-lookup"><span data-stu-id="9bda5-141">The characters do not appear but are represented by asterisks (*).</span></span>|  
    |`PeopleSoft 8.x Jar Files`|<span data-ttu-id="9bda5-142">コンポーネント インターフェイス (PeopleSoft 8 のみ) を使用するには、PeopleSoft Component Interface の jar ファイルが含まれるように CLASSPATH を更新する必要があります</span><span class="sxs-lookup"><span data-stu-id="9bda5-142">To use Ccmponent interfaces (PeopleSoft 8 only) you must update your CLASSPATH to include the PeopleSoft Component Interface jar file.</span></span> <span data-ttu-id="9bda5-143">例: **< PeopleSoft_Home > \web\PSJOA\psjoa.jar**です。</span><span class="sxs-lookup"><span data-stu-id="9bda5-143">For example: **<PeopleSoft_Home>\web\PSJOA\psjoa.jar**.</span></span>|  
    |`User Name`|<span data-ttu-id="9bda5-144">選択しなかった場合**SSO を使用する**、BizTalk Adapter for PeopleSoft Enterprise サーバー システムにアクセスするための資格情報パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bda5-144">If you did not select **Use SSO**, you must set credential parameters for the BizTalk Adapter for PeopleSoft Enterprise to access the server system.</span></span><br /><br /> <span data-ttu-id="9bda5-145">PeopleSoft システムへのログオンに必要なユーザー名を表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="9bda5-145">A string representing a user name required for logon to a PeopleSoft system.</span></span>|  
  
2.  <span data-ttu-id="9bda5-146">入力、**追加パラメーター**日付がキーとして使用するときの値とは別の形式です。</span><span class="sxs-lookup"><span data-stu-id="9bda5-146">Enter an **Additional parameters** value when a date is used as a key; it has a different format.</span></span> <span data-ttu-id="9bda5-147">既定の形式は YYYY-MM-DD です。</span><span class="sxs-lookup"><span data-stu-id="9bda5-147">YYYY-MM-DD is the default format.</span></span>  
  
3.  <span data-ttu-id="9bda5-148">入力、**同時実行制御**で呼び出し、たとえば 200 の数を表す値**Max Concurrent Calls**必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="9bda5-148">Enter a **Concurrency control** value representing the number of calls, for example 200, in **Max Concurrent Calls** if it is required.</span></span>  
  
     <span data-ttu-id="9bda5-149">**Max Concurrent Calls**パラメーターは、バック エンド サーバーがデータの量を処理できない場合に、オーバー ロードの保護をアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="9bda5-149">The **Max Concurrent Calls** parameter activates an overload protection if the back-end server cannot process the amount of data.</span></span> <span data-ttu-id="9bda5-150">同時呼び出しとは、アダプターがまだ返信を受信していない要求のことです。</span><span class="sxs-lookup"><span data-stu-id="9bda5-150">A concurrent call is a request for which the adapter does not yet have a reply.</span></span> <span data-ttu-id="9bda5-151">設定**Max Concurrent Calls**場合、スループットがバックエンドの処理能力を超えています。</span><span class="sxs-lookup"><span data-stu-id="9bda5-151">Set **Max Concurrent Calls** in instances where the throughput exceeds back-end processing capabilities.</span></span>  
  
     <span data-ttu-id="9bda5-152">このフィールドの既定値は -1 です。保護は発生しません。</span><span class="sxs-lookup"><span data-stu-id="9bda5-152">The default value for this field is -1, meaning no protection occurs.</span></span>  
  
     <span data-ttu-id="9bda5-153">BizTalk Server が送信アダプターに要求を送信し、同時実行の数が呼び出しまたはに設定された値を超えて 場合**Max Concurrent Calls**、同時呼び出しの数まで、要求を保存送信スレッド設定された値以下に低下します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-153">If BizTalk Server submits a request to the Transmit adapter, and the number of concurrent calls equals or exceeds the value set for **Max Concurrent Calls**, the thread submitting the request is saved until the concurrent calls number decreases to below the set value.</span></span>  

## <a name="update-max-concurrent-calls"></a><span data-ttu-id="9bda5-154">最大同時呼び出しを更新します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-154">Update Max Concurrent Calls</span></span>

<span data-ttu-id="9bda5-155">`Max Concurrent Calls` パラメーターは、構成を最適化することができる機能です。</span><span class="sxs-lookup"><span data-stu-id="9bda5-155">The `Max Concurrent Calls` parameter is a feature that enables you to optimize your configuration.</span></span> <span data-ttu-id="9bda5-156">このパラメータは、スループットがバックエンドの処理機能を上回るインスタンスで使用します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-156">You use this parameter in instances where the throughput exceeds back-end processing capabilities.</span></span> <span data-ttu-id="9bda5-157">パラメーターを追加するには、アダプターに、**送信ポートのトランスポート プロパティ**メッセージ オーバー ロードの保護を有効にする ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="9bda5-157">You can add the parameter to the adapters in the **Send Port Transport Properties** dialog box to activate message overload protection.</span></span> <span data-ttu-id="9bda5-158">既定値は -1 です。これは呼び出しが制限されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-158">The default is -1, meaning the calls are unlimited.</span></span>  
  
<span data-ttu-id="9bda5-159">BizTalk Server は、送信アダプタに対してメッセージを送信するとき、まず、アダプタからバッチを受け取り、バッチで `TransmitMessage()` を呼び出して各メッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-159">When BizTalk Server submits messages to the transmit adapter, it first receives a batch from the adapter and invokes `TransmitMessage()` on the batch to transmit each message.</span></span> <span data-ttu-id="9bda5-160">この処理が完了すると、BizTalk Server はバッチで `Done()` を呼び出し、アダプタがバックエンドに対するメッセージ送信を開始します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-160">When done, BizTalk Server invokes `Done()` on the batch, and the adapter starts transmitting the messages to the back-end.</span></span> <span data-ttu-id="9bda5-161">BizTalk Server が `Done` を呼び出す前に複数のバッチを取得した場合、`Done` コマンドは発行されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="9bda5-161">If BizTalk Server obtains multiple batches before `Done` is invoked, the `Done` command might never occur.</span></span> <span data-ttu-id="9bda5-162">バッチ内に含めるメッセージの最大数を設定することで、バックエンドに送信するメッセージを制御できます。</span><span class="sxs-lookup"><span data-stu-id="9bda5-162">By setting the maximum number of messages in a batch, you can control messages to the back-end.</span></span> <span data-ttu-id="9bda5-163">このパラメータに加えた変更は、すぐに有効になります。</span><span class="sxs-lookup"><span data-stu-id="9bda5-163">Changing this parameter takes effect in a minute.</span></span> <span data-ttu-id="9bda5-164">BizTalk Server は、SQL データベースに保存されているアダプター構成に対する変更を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bda5-164">BizTalk Server must retrieve the changes to the adapter configuration that is saved in the SQL database.</span></span>  
  
### <a name="change-the-max-concurrent-calls-parameter"></a><span data-ttu-id="9bda5-165">Max Concurrent Calls パラメーターを変更します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-165">Change the Max Concurrent Calls parameter</span></span>  
  
1.  <span data-ttu-id="9bda5-166">**送信ポートのトランスポート プロパティ** ダイアログ ボックスで、入力、**接続**値。</span><span class="sxs-lookup"><span data-stu-id="9bda5-166">In the **Send Port Transport Properties** dialog box, enter a **Connection** value.</span></span>  
  
     <span data-ttu-id="9bda5-167">既定値は 40 セッションです。</span><span class="sxs-lookup"><span data-stu-id="9bda5-167">The default value is 40 sessions.</span></span> <span data-ttu-id="9bda5-168">これより小さい値を使用すると、実行時のパフォーマンスが低下することがあります。</span><span class="sxs-lookup"><span data-stu-id="9bda5-168">If you use a smaller value, you might experience degradation in run-time performance.</span></span> <span data-ttu-id="9bda5-169">逆の場合も同様に、より大きい値を使用するとサーバーの許容量を超え、実行時エラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="9bda5-169">The opposite is also true; a bigger value could exceed the ability of the server and result in run-time errors.</span></span>  
  
2.  <span data-ttu-id="9bda5-170">選択**はい**の**エージェントの更新**runtimeagent.exe および browsingagent.exe の処理を必要時に自動的に再起動を強制します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-170">Select **Yes** for **Refresh Agent** to force the runtimeagent.exe and the browsingagent.exe processes to restart automatically when required.</span></span>  
  
     <span data-ttu-id="9bda5-171">たとえば、サーバーとの接続が失われた場合や、サーバーに追加したものが Microsoft アダプター ウィザードに表示されない場合に、処理を自動的に再起動することができます。</span><span class="sxs-lookup"><span data-stu-id="9bda5-171">For example, you want the process to restart automatically if it loses connection with the server, or if you add something to the server and it does not appear in the Microsoft Adapter Wizard for selection.</span></span>  
  
     <span data-ttu-id="9bda5-172">**エージェントの更新**パラメーターの参照とランタイム エージェントの両方を更新します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-172">The **Refresh Agent** parameter refreshes both the browsing and the run-time agents.</span></span> <span data-ttu-id="9bda5-173">runtimeagent.exe は、1 分間の遅延後または次の send 呼び出し時に更新されます。</span><span class="sxs-lookup"><span data-stu-id="9bda5-173">The runtimeagent.exe updates after a delay of one minute or at the next send call.</span></span>  
  
3.  <span data-ttu-id="9bda5-174">PeopleSoft システムにアクセスするための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-174">Provide credentials to access the PeopleSoft system.</span></span>  
  
     <span data-ttu-id="9bda5-175">システムへのアクセスには、2 つの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9bda5-175">You can use two methods to access the system:</span></span>  
  
    -   <span data-ttu-id="9bda5-176">ログイン資格情報 (Transport Properties Login パラメーター)</span><span class="sxs-lookup"><span data-stu-id="9bda5-176">Login Credentials (Transport Properties Login parameters)</span></span>  
  
    -   <span data-ttu-id="9bda5-177">シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="9bda5-177">Single Sign-On</span></span>  
  
4.  <span data-ttu-id="9bda5-178">選択**はい**の**SSO を使用する**でのシングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-178">Select **Yes** for **Use SSO** to use Single Sign-On.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9bda5-179">詳細については、次を参照してください。[アダプターをセキュリティで保護された](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)です。</span><span class="sxs-lookup"><span data-stu-id="9bda5-179">For more information, see [Secure the adapter](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md).</span></span> 
  
5.  <span data-ttu-id="9bda5-180">一覧で関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-180">Select an affiliate application in the list.</span></span>  
  
     <span data-ttu-id="9bda5-181">エンタープライズ シングル サインオン ツールで作成される関連アプリケーションは、PeopleSoft などのアプリケーションを表します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-181">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as PeopleSoft.</span></span> <span data-ttu-id="9bda5-182">BizTalk Adapter for PeopleSoft Enterprise は、アプリケーション ユーザーの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="9bda5-182">Microsoft BizTalk Adapter for PeopleSoft Enterprise uses the credentials of an application user.</span></span> <span data-ttu-id="9bda5-183">これらの資格情報は、指定された関連アプリケーションのサーバー システムの SSO データベースから取得されます。</span><span class="sxs-lookup"><span data-stu-id="9bda5-183">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span> <span data-ttu-id="9bda5-184">取得される資格情報は、BizTalk プロジェクトを起動したユーザー (アプリケーション ユーザー) の資格情報です。</span><span class="sxs-lookup"><span data-stu-id="9bda5-184">The credentials are those of the user (the application user) who launched the BizTalk project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9bda5-185">関連アプリケーションを作成する方法の詳細については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications2.md)、または Microsoft BizTalk Server のオンライン ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="9bda5-185">For more information about how to create affiliate applications, see [Creating Affiliate Applications](../core/creating-affiliate-applications2.md), or the Microsoft BizTalk Server online Help.</span></span>  
  
6.  <span data-ttu-id="9bda5-186">接続情報を受け入れるように必要なすべての情報を提供すると、をクリックして**適用**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="9bda5-186">After providing all required information to accept the connection information, click **Apply**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="9bda5-187">PeopleSoft にアクセスするには、BizTalk Adapter for PeopleSoft Enterprise に接続パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bda5-187">You must set connection parameters for the BizTalk Adapter for PeopleSoft Enterprise to access PeopleSoft.</span></span>  
  

## <a name="next"></a><span data-ttu-id="9bda5-188">Next</span><span class="sxs-lookup"><span data-stu-id="9bda5-188">Next</span></span>
  
[<span data-ttu-id="9bda5-189">PeopleSoft スキーマを BizTalk Server プロジェクトにインポートします。</span><span class="sxs-lookup"><span data-stu-id="9bda5-189">Import PeopleSoft Schemas into BizTalk Server Projects</span></span>](../core/importing-peoplesoft-schemas-into-biztalk-server-projects.md)  
[<span data-ttu-id="9bda5-190">PeopleSoft からの受信</span><span class="sxs-lookup"><span data-stu-id="9bda5-190">Receive from PeopleSoft</span></span>](../core/receiving-from-peoplesoft.md)