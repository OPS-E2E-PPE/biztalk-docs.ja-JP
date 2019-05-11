---
title: PeopleSoft アダプターの送信アイテムの作成 |Microsoft Docs
description: 送信ポートを作成し、トランスポートのプロパティを送信し、PeopleSoft Enterprise アダプターを BizTalk server を使用して PeopleSoft にメッセージを送信する最大同時呼び出しを更新
ms.custom: ''
ms.date: 10/19/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce67da59-26a6-44a2-929c-ed3acb21d407
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4857bf6444f30da0162cf7ffbeb8572042ba762
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390433"
---
# <a name="create-peoplesoft-send-artifacts"></a><span data-ttu-id="1ddf2-103">PeopleSoft 送信アイテムを作成します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-103">Create PeopleSoft send artifacts</span></span>
<span data-ttu-id="1ddf2-104">Microsoft BizTalk Adapter for PeopleSoft Enterprise は PeopleSoft にアクセスで使用可能なコンポーネントについて説明し、SOAP 要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-104">Microsoft BizTalk Adapter for PeopleSoft Enterprise accesses PeopleSoft and explores available components or processes SOAP requests.</span></span> <span data-ttu-id="1ddf2-105">このトピックでは、PeopleSoft アダプターを使用する BizTalk Server 管理コンソールで送信アイテムを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-105">This topic shows you how to create the send artifacts in BizTalk Server Administration to use the PeopleSoft adapter.</span></span>


## <a name="create-the-send-port"></a><span data-ttu-id="1ddf2-106">送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-106">Create the send port</span></span>

1.  <span data-ttu-id="1ddf2-107">BizTalk Server 管理コンソールで  **BizTalk グループ**、展開**アプリケーション**、し、目的のアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-107">In the BizTalk Server Administration Console,expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="1ddf2-108">右クリックして**送信ポート**を選択します**新規**、し、**静的な送信請求-応答送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-108">Right-click **Send Ports**, select **New**, and then select **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="1ddf2-109">**送信ポートのプロパティ**次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-109">In the **Send Port Properties**, do the following:</span></span>  
  
    1.  <span data-ttu-id="1ddf2-110">送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-110">Enter a name for the send port.</span></span> <span data-ttu-id="1ddf2-111">たとえば、`SSOSendToPeopleSoft` と入力します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-111">For example, enter `SSOSendToPeopleSoft`.</span></span>  
  
    2.  <span data-ttu-id="1ddf2-112">**型**ドロップダウン リストで、 **PeopleSoft**します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-112">From the **Type** drop-down list, select **PeopleSoft**.</span></span>  
  
    3.  <span data-ttu-id="1ddf2-113">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-113">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="1ddf2-114">送信パイプラインのドロップダウン リストから選択**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-114">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="1ddf2-115">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-115">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="1ddf2-116">選択**構成**送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-116">Select **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="1ddf2-117">**PeopleSoft トランスポートのプロパティ**次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-117">In the **PeopleSoft Transport Properties**, do the following:</span></span>  
  
    1.  <span data-ttu-id="1ddf2-118">展開**アダプターに必要なプロパティ**、入力と**アプリケーション サーバーのパス**、 **JAVA_HOME**、**ユーザー名**、 **パスワード**、および Peoplesoft システムに接続するための Jar ファイル。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-118">Expand **Adapter Required Properties**, and enter **Application Server Path**, **JAVA_HOME**, **user name**, **password**, and the Jar file for connecting into the Peoplesoft system.</span></span>  
  
         <span data-ttu-id="1ddf2-119">ログオン情報を設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-119">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="1ddf2-120">一覧で、PeopleSoft システムを表すよう作成した SSO 関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-120">In the list, select the SSO affiliate application you created to represent the PeopleSoft system.</span></span>  
  
    3.  <span data-ttu-id="1ddf2-121">**SSO を使用**、**はい**します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-121">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="1ddf2-122">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-122">Select **OK**.</span></span>  
  
5.  <span data-ttu-id="1ddf2-123">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-123">Select **OK**.</span></span>

## <a name="set-the-transport-properties"></a><span data-ttu-id="1ddf2-124">トランスポートのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-124">Set the transport properties</span></span>
<span data-ttu-id="1ddf2-125">PeopleSoft トランスポートのプロパティはデザインに使用し、実行時間。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-125">The PeopleSoft transport properties are used for design and run time.</span></span> <span data-ttu-id="1ddf2-126">**トランスポートのプロパティ**ダイアログ ボックスで、接続および資格情報パラメーターに固有の設定、サーバー システムとアクセスしようとしているオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-126">In the **Transport Properties** dialog box, you set the connection and credential parameters specific to the server system and the objects you are trying to access.</span></span>  
  
 <span data-ttu-id="1ddf2-127">![](../core/media/peop-peoplesofttransportpropertiess.gif "Peop_PeopleSoftTransportPropertiess")</span><span class="sxs-lookup"><span data-stu-id="1ddf2-127">![](../core/media/peop-peoplesofttransportpropertiess.gif "Peop_PeopleSoftTransportPropertiess")</span></span>  
  
1.  <span data-ttu-id="1ddf2-128">アダプターの必要なプロパティを展開し、PeopleSoft サーバーへの接続に必要なすべての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-128">Expand the Adapter Required Properties and fill in all required information for connection to the PeopleSoft server.</span></span>  
  
     <span data-ttu-id="1ddf2-129">Microsoft BizTalk Adapter for PeopleSoft Enterprise を PeopleSoft Enterprise に接続する構成パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-129">You must set configuration parameters to connect Microsoft BizTalk Adapter for PeopleSoft Enterprise to PeopleSoft Enterprise.</span></span> <span data-ttu-id="1ddf2-130">このデータは、大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-130">This data is case sensitive.</span></span>  
  
    |<span data-ttu-id="1ddf2-131">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1ddf2-131">Parameter</span></span>|<span data-ttu-id="1ddf2-132">説明</span><span class="sxs-lookup"><span data-stu-id="1ddf2-132">Description</span></span>|  
    |---------------|-----------------|  
    |`Application Server Path`|<span data-ttu-id="1ddf2-133">ポートのロックを実行しているが、PeopleSoft Application Server がリッスンしているコンピューターを表す文字列。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-133">A string representing the computer and port on which the PeopleSoft Application Server is running and listening.</span></span> <span data-ttu-id="1ddf2-134">PeopleSoft 8 Application への URL パスの構文は//< computer_name >:\<ポート\>します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-134">The syntax of the URL path to the PeopleSoft 8 Application is //<computer_name>:\<port\>.</span></span> <span data-ttu-id="1ddf2-135">PeopleSoft 管理者に問い合わせて、\<ポート\>値。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-135">Ask your PeopleSoft administrator for the \<port\> value.</span></span> <span data-ttu-id="1ddf2-136">\<ポート\>値は、JOLT プロトコル リスナー ポート、App Server ポートではありません。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-136">The \<port\> value is the JOLT protocol listener port, not the App Server port.</span></span> <span data-ttu-id="1ddf2-137">既定の JOLT ポートは 9000 ですです。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-137">The default JOLT port is 9000.</span></span>|  
    |`JAVA_HOME`|<span data-ttu-id="1ddf2-138">たとえば、JDK のインストール をポイントする JAVA_HOME 変数を設定します。**C:\j2sdk1.4.2_08**します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-138">Set the JAVA_HOME variable to point to your JDK installation, for example: **C:\j2sdk1.4.2_08**.</span></span>|  
    |`Password`|<span data-ttu-id="1ddf2-139">選択しなかった場合**使用 SSO**、BizTalk Adapter for PeopleSoft Enterprise サーバー システムにアクセスするための資格情報パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-139">If you did not select **Use SSO**, you must set credential parameters for the BizTalk Adapter for PeopleSoft Enterprise to access the server system.</span></span><br /><br /> <span data-ttu-id="1ddf2-140">PeopleSoft システムへのログオン ユーザーのパスワードを表す文字列。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-140">A string representing the user's password for logon to a PeopleSoft system.</span></span> <span data-ttu-id="1ddf2-141">文字は表示されませんが、アスタリスク (\*) で表されます。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-141">The characters do not appear but are represented by asterisks (\*).</span></span>|  
    |`PeopleSoft 8.x Jar Files`|<span data-ttu-id="1ddf2-142">コンポーネントを使用するには、インターフェイス (PeopleSoft 8 のみ)、クラスパスに含める、PeopleSoft コンポーネント インターフェイスを更新する必要があります jar ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-142">To use Ccmponent interfaces (PeopleSoft 8 only) you must update your CLASSPATH to include the PeopleSoft Component Interface jar file.</span></span> <span data-ttu-id="1ddf2-143">例: **< PeopleSoft_Home > \web\PSJOA\psjoa.jar**します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-143">For example: **<PeopleSoft_Home>\web\PSJOA\psjoa.jar**.</span></span>|  
    |`User Name`|<span data-ttu-id="1ddf2-144">選択しなかった場合**使用 SSO**、BizTalk Adapter for PeopleSoft Enterprise サーバー システムにアクセスするための資格情報パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-144">If you did not select **Use SSO**, you must set credential parameters for the BizTalk Adapter for PeopleSoft Enterprise to access the server system.</span></span><br /><br /> <span data-ttu-id="1ddf2-145">PeopleSoft システムへのログオンに必要なユーザー名を表す文字列。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-145">A string representing a user name required for logon to a PeopleSoft system.</span></span>|  
  
2.  <span data-ttu-id="1ddf2-146">入力、**追加パラメーター**値の日付をキーとして使用する場合に、別の形式があります。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-146">Enter an **Additional parameters** value when a date is used as a key; it has a different format.</span></span> <span data-ttu-id="1ddf2-147">YYYY-MM-DD では、既定の形式を示します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-147">YYYY-MM-DD is the default format.</span></span>  
  
3.  <span data-ttu-id="1ddf2-148">入力、**同時実行制御**で呼び出し、たとえば 200 の数を表す値**最大同時呼び出し数**必要な場合。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-148">Enter a **Concurrency control** value representing the number of calls, for example 200, in **Max Concurrent Calls** if it is required.</span></span>  
  
     <span data-ttu-id="1ddf2-149">**最大同時呼び出し数**パラメーターは、バック エンド サーバーは、データの量を処理できない場合に、オーバー ロードの保護をアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-149">The **Max Concurrent Calls** parameter activates an overload protection if the back-end server cannot process the amount of data.</span></span> <span data-ttu-id="1ddf2-150">同時呼び出しは、対象のアダプターはまだありません返信要求です。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-150">A concurrent call is a request for which the adapter does not yet have a reply.</span></span> <span data-ttu-id="1ddf2-151">設定**最大同時呼び出し数**スループットがバックエンド処理機能を上回るインスタンスでします。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-151">Set **Max Concurrent Calls** in instances where the throughput exceeds back-end processing capabilities.</span></span>  
  
     <span data-ttu-id="1ddf2-152">既定値のこのフィールドが-1 の場合に発生します保護れないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-152">The default value for this field is -1, meaning no protection occurs.</span></span>  
  
     <span data-ttu-id="1ddf2-153">BizTalk Server 送信アダプターでは、要求を送信して、同時実行の数が呼び出しまたはの設定値を超える場合**最大同時呼び出し数**、同時呼び出しの数まで、要求が保存された送信スレッド設定値を下回るまで減少します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-153">If BizTalk Server submits a request to the Transmit adapter, and the number of concurrent calls equals or exceeds the value set for **Max Concurrent Calls**, the thread submitting the request is saved until the concurrent calls number decreases to below the set value.</span></span>  

## <a name="update-max-concurrent-calls"></a><span data-ttu-id="1ddf2-154">最大同時呼び出しを更新します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-154">Update Max Concurrent Calls</span></span>

<span data-ttu-id="1ddf2-155">`Max Concurrent Calls`パラメーターは、機能、構成を最適化することができます。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-155">The `Max Concurrent Calls` parameter is a feature that enables you to optimize your configuration.</span></span> <span data-ttu-id="1ddf2-156">スループットがバックエンド処理機能を上回るインスタンスでは、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-156">You use this parameter in instances where the throughput exceeds back-end processing capabilities.</span></span> <span data-ttu-id="1ddf2-157">パラメーターを追加するには、アダプターに、**送信ポートのトランスポート プロパティ**メッセージ オーバー ロードの保護をアクティブにする ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-157">You can add the parameter to the adapters in the **Send Port Transport Properties** dialog box to activate message overload protection.</span></span> <span data-ttu-id="1ddf2-158">既定値は -1 です。これは呼び出しが制限されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-158">The default is -1, meaning the calls are unlimited.</span></span>  
  
<span data-ttu-id="1ddf2-159">BizTalk Server では、送信アダプターにメッセージを送信するときに最初にアダプターからバッチを受信し、呼び出します`TransmitMessage()`で各メッセージを送信するバッチ。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-159">When BizTalk Server submits messages to the transmit adapter, it first receives a batch from the adapter and invokes `TransmitMessage()` on the batch to transmit each message.</span></span> <span data-ttu-id="1ddf2-160">この処理が完了すると、BizTalk Server はバッチで `Done()` を呼び出し、アダプタがバックエンドに対するメッセージ送信を開始します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-160">When done, BizTalk Server invokes `Done()` on the batch, and the adapter starts transmitting the messages to the back-end.</span></span> <span data-ttu-id="1ddf2-161">BizTalk Server は、前に複数のバッチを取得した場合`Done`が呼び出される、`Done`コマンドが発生することはありません。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-161">If BizTalk Server obtains multiple batches before `Done` is invoked, the `Done` command might never occur.</span></span> <span data-ttu-id="1ddf2-162">バッチ内に含めるメッセージの最大数を設定することで、バックエンドに送信するメッセージを制御できます。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-162">By setting the maximum number of messages in a batch, you can control messages to the back-end.</span></span> <span data-ttu-id="1ddf2-163">このパラメーターを変更するには、1 分で有効です。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-163">Changing this parameter takes effect in a minute.</span></span> <span data-ttu-id="1ddf2-164">BizTalk Server では、SQL database に保存されているアダプター構成に対する変更を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-164">BizTalk Server must retrieve the changes to the adapter configuration that is saved in the SQL database.</span></span>  
  
### <a name="change-the-max-concurrent-calls-parameter"></a><span data-ttu-id="1ddf2-165">Max Concurrent Calls パラメーターを変更します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-165">Change the Max Concurrent Calls parameter</span></span>  
  
1.  <span data-ttu-id="1ddf2-166">**送信ポートのトランスポート プロパティ** ダイアログ ボックスに、入力、**接続**値。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-166">In the **Send Port Transport Properties** dialog box, enter a **Connection** value.</span></span>  
  
     <span data-ttu-id="1ddf2-167">既定値は、40 セッションです。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-167">The default value is 40 sessions.</span></span> <span data-ttu-id="1ddf2-168">小さい値を使用する場合は、実行時のパフォーマンスの低下があります。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-168">If you use a smaller value, you might experience degradation in run-time performance.</span></span> <span data-ttu-id="1ddf2-169">逆の場合も同様です。大きい値には、実行時エラーの結果、サーバーの機能を超える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-169">The opposite is also true; a bigger value could exceed the ability of the server and result in run-time errors.</span></span>  
  
2.  <span data-ttu-id="1ddf2-170">選択**はい**の**エージェントの更新**runtimeagent.exe および browsingagent.exe の処理を必要な場合に自動的に再起動を強制します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-170">Select **Yes** for **Refresh Agent** to force the runtimeagent.exe and the browsingagent.exe processes to restart automatically when required.</span></span>  
  
     <span data-ttu-id="1ddf2-171">たとえば、サーバーとの接続が失われた場合や、サーバーに追加したものが Microsoft アダプター ウィザードに表示されない場合に、処理を自動的に再起動することができます。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-171">For example, you want the process to restart automatically if it loses connection with the server, or if you add something to the server and it does not appear in the Microsoft Adapter Wizard for selection.</span></span>  
  
     <span data-ttu-id="1ddf2-172">**エージェントの更新**両方参照エージェントとランタイム エージェント パラメーターを更新します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-172">The **Refresh Agent** parameter refreshes both the browsing and the run-time agents.</span></span> <span data-ttu-id="1ddf2-173">または次の 1 つ分の遅延の後、runtimeagent.exe 更新プログラムは、呼び出しを送信します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-173">The runtimeagent.exe updates after a delay of one minute or at the next send call.</span></span>  
  
3.  <span data-ttu-id="1ddf2-174">PeopleSoft システムにアクセスする資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-174">Provide credentials to access the PeopleSoft system.</span></span>  
  
     <span data-ttu-id="1ddf2-175">2 つのメソッドを使用するには、システムにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-175">You can use two methods to access the system:</span></span>  
  
    -   <span data-ttu-id="1ddf2-176">ログイン資格情報 (Transport Properties Login パラメーター)</span><span class="sxs-lookup"><span data-stu-id="1ddf2-176">Login Credentials (Transport Properties Login parameters)</span></span>  
  
    -   <span data-ttu-id="1ddf2-177">シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="1ddf2-177">Single Sign-On</span></span>  
  
4.  <span data-ttu-id="1ddf2-178">選択**はい**の**を使用して SSO**でシングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-178">Select **Yes** for **Use SSO** to use Single Sign-On.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1ddf2-179">詳細については、次を参照してください。[アダプターのセキュリティ保護](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-179">For more information, see [Secure the adapter](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md).</span></span> 
  
5.  <span data-ttu-id="1ddf2-180">一覧で関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-180">Select an affiliate application in the list.</span></span>  
  
     <span data-ttu-id="1ddf2-181">エンタープライズ シングル サインオン ツールによって作成される関連アプリケーションは、PeopleSoft などのアプリケーションを表します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-181">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as PeopleSoft.</span></span> <span data-ttu-id="1ddf2-182">Microsoft BizTalk Adapter for PeopleSoft Enterprise では、アプリケーション ユーザーの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-182">Microsoft BizTalk Adapter for PeopleSoft Enterprise uses the credentials of an application user.</span></span> <span data-ttu-id="1ddf2-183">これらの資格情報は、指定された関連アプリケーションのサーバー システムの SSO データベースから取得されます。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-183">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span> <span data-ttu-id="1ddf2-184">資格情報では、BizTalk プロジェクトを起動したユーザー (アプリケーション ユーザー) のものです。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-184">The credentials are those of the user (the application user) who launched the BizTalk project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1ddf2-185">関連アプリケーションを作成する方法の詳細については、次を参照してください。[関連アプリケーションを作成する](../core/creating-affiliate-applications2.md)、または Microsoft BizTalk Server のオンライン ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-185">For more information about how to create affiliate applications, see [Creating Affiliate Applications](../core/creating-affiliate-applications2.md), or the Microsoft BizTalk Server online Help.</span></span>  
  
6.  <span data-ttu-id="1ddf2-186">接続情報を受け入れるように必要なすべての情報を提供するには、後に次のようにクリックします。**適用**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-186">After providing all required information to accept the connection information, click **Apply**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="1ddf2-187">BizTalk Adapter for PeopleSoft Enterprise PeopleSoft へのアクセスの接続パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-187">You must set connection parameters for the BizTalk Adapter for PeopleSoft Enterprise to access PeopleSoft.</span></span>  
  

## <a name="next"></a><span data-ttu-id="1ddf2-188">Next</span><span class="sxs-lookup"><span data-stu-id="1ddf2-188">Next</span></span>
  
[<span data-ttu-id="1ddf2-189">PeopleSoft スキーマを BizTalk Server プロジェクトにインポートします。</span><span class="sxs-lookup"><span data-stu-id="1ddf2-189">Import PeopleSoft Schemas into BizTalk Server Projects</span></span>](../core/importing-peoplesoft-schemas-into-biztalk-server-projects.md)  
[<span data-ttu-id="1ddf2-190">PeopleSoft からの受信</span><span class="sxs-lookup"><span data-stu-id="1ddf2-190">Receive from PeopleSoft</span></span>](../core/receiving-from-peoplesoft.md)