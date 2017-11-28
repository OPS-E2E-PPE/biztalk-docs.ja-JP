---
title: "構成の最適化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Max Concurrent Calls parameter
- optimizing, configuration
- configuring, optimizing
- messages, overload protection
ms.assetid: df0ae17b-fcfa-4e00-893c-63f4972d3822
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72b185d7738ac48d9a1dc3631c7c9faec9ac4b60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-configuration"></a><span data-ttu-id="a688c-102">構成の最適化</span><span class="sxs-lookup"><span data-stu-id="a688c-102">Optimizing Configuration</span></span>
<span data-ttu-id="a688c-103">このセクションでは、BizTalk Adapter for PeopleSoft Enterprise の構成を最適化する方法について説明します。アダプターをセットアップするためのパラメーターについても説明します。</span><span class="sxs-lookup"><span data-stu-id="a688c-103">This section contains information about how to optimize your configuration of BizTalk Adapter for PeopleSoft Enterprise and includes parameter descriptions for setting up the adapter.</span></span>  
  
## <a name="message-overload-protection"></a><span data-ttu-id="a688c-104">メッセージ オーバーロードの保護</span><span class="sxs-lookup"><span data-stu-id="a688c-104">Message Overload Protection</span></span>  
 <span data-ttu-id="a688c-105">`Max Concurrent Calls` パラメーターは、構成を最適化することができる機能です。</span><span class="sxs-lookup"><span data-stu-id="a688c-105">The `Max Concurrent Calls` parameter is a feature that enables you to optimize your configuration.</span></span> <span data-ttu-id="a688c-106">このパラメータは、スループットがバックエンドの処理機能を上回るインスタンスで使用します。</span><span class="sxs-lookup"><span data-stu-id="a688c-106">You use this parameter in instances where the throughput exceeds back-end processing capabilities.</span></span> <span data-ttu-id="a688c-107">パラメーターを追加するには、アダプターに、**送信ポートのトランスポート プロパティ**メッセージ オーバー ロードの保護を有効にする ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="a688c-107">You can add the parameter to the adapters in the **Send Port Transport Properties** dialog box to activate message overload protection.</span></span> <span data-ttu-id="a688c-108">既定値は -1 です。これは呼び出しが制限されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="a688c-108">The default is -1, meaning the calls are unlimited.</span></span>  
  
 <span data-ttu-id="a688c-109">BizTalk Server は、送信アダプタに対してメッセージを送信するとき、まず、アダプタからバッチを受け取り、バッチで `TransmitMessage()` を呼び出して各メッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="a688c-109">When BizTalk Server submits messages to the transmit adapter, it first receives a batch from the adapter and invokes `TransmitMessage()` on the batch to transmit each message.</span></span> <span data-ttu-id="a688c-110">この処理が完了すると、BizTalk Server はバッチで `Done()` を呼び出し、アダプタがバックエンドに対するメッセージ送信を開始します。</span><span class="sxs-lookup"><span data-stu-id="a688c-110">When done, BizTalk Server invokes `Done()` on the batch, and the adapter starts transmitting the messages to the back-end.</span></span> <span data-ttu-id="a688c-111">BizTalk Server が `Done` を呼び出す前に複数のバッチを取得した場合、`Done` コマンドは発行されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="a688c-111">If BizTalk Server obtains multiple batches before `Done` is invoked, the `Done` command might never occur.</span></span> <span data-ttu-id="a688c-112">バッチ内に含めるメッセージの最大数を設定することで、バックエンドに送信するメッセージを制御できます。</span><span class="sxs-lookup"><span data-stu-id="a688c-112">By setting the maximum number of messages in a batch, you can control messages to the back-end.</span></span> <span data-ttu-id="a688c-113">このパラメータに加えた変更は、すぐに有効になります。</span><span class="sxs-lookup"><span data-stu-id="a688c-113">Changing this parameter takes effect in a minute.</span></span> <span data-ttu-id="a688c-114">BizTalk Server は、SQL データベースに保存されているアダプター構成に対する変更を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a688c-114">BizTalk Server must retrieve the changes to the adapter configuration that is saved in the SQL database.</span></span>  
  
#### <a name="to-change-the-max-concurrent-calls-parameter"></a><span data-ttu-id="a688c-115">Max Concurrent Calls パラメーターを変更するには</span><span class="sxs-lookup"><span data-stu-id="a688c-115">To change the Max Concurrent Calls parameter</span></span>  
  
1.  <span data-ttu-id="a688c-116">**送信ポートのトランスポート プロパティ** ダイアログ ボックスで、入力、**接続**値。</span><span class="sxs-lookup"><span data-stu-id="a688c-116">In the **Send Port Transport Properties** dialog box, enter a **Connection** value.</span></span>  
  
     <span data-ttu-id="a688c-117">既定値は 40 セッションです。</span><span class="sxs-lookup"><span data-stu-id="a688c-117">The default value is 40 sessions.</span></span> <span data-ttu-id="a688c-118">これより小さい値を使用すると、実行時のパフォーマンスが低下することがあります。</span><span class="sxs-lookup"><span data-stu-id="a688c-118">If you use a smaller value, you might experience degradation in run-time performance.</span></span> <span data-ttu-id="a688c-119">逆の場合も同様に、より大きい値を使用するとサーバーの許容量を超え、実行時エラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="a688c-119">The opposite is also true; a bigger value could exceed the ability of the server and result in run-time errors.</span></span>  
  
2.  <span data-ttu-id="a688c-120">選択**はい**の**エージェントの更新**runtimeagent.exe および browsingagent.exe の処理を必要時に自動的に再起動を強制します。</span><span class="sxs-lookup"><span data-stu-id="a688c-120">Select **Yes** for **Refresh Agent** to force the runtimeagent.exe and the browsingagent.exe processes to restart automatically when required.</span></span>  
  
     <span data-ttu-id="a688c-121">たとえば、サーバーとの接続が失われた場合や、サーバーに追加したものが Microsoft アダプター ウィザードに表示されない場合に、処理を自動的に再起動することができます。</span><span class="sxs-lookup"><span data-stu-id="a688c-121">For example, you want the process to restart automatically if it loses connection with the server, or if you add something to the server and it does not appear in the Microsoft Adapter Wizard for selection.</span></span>  
  
     <span data-ttu-id="a688c-122">**エージェントの更新**パラメーターの参照とランタイム エージェントの両方を更新します。</span><span class="sxs-lookup"><span data-stu-id="a688c-122">The **Refresh Agent** parameter refreshes both the browsing and the run-time agents.</span></span> <span data-ttu-id="a688c-123">runtimeagent.exe は、1 分間の遅延後または次の send 呼び出し時に更新されます。</span><span class="sxs-lookup"><span data-stu-id="a688c-123">The runtimeagent.exe updates after a delay of one minute or at the next send call.</span></span>  
  
3.  <span data-ttu-id="a688c-124">PeopleSoft システムにアクセスするための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="a688c-124">Provide credentials to access the PeopleSoft system.</span></span>  
  
     <span data-ttu-id="a688c-125">システムへのアクセスには、2 つの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a688c-125">You can use two methods to access the system:</span></span>  
  
    -   <span data-ttu-id="a688c-126">ログイン資格情報 (Transport Properties Login パラメーター)</span><span class="sxs-lookup"><span data-stu-id="a688c-126">Login Credentials (Transport Properties Login parameters)</span></span>  
  
    -   <span data-ttu-id="a688c-127">シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="a688c-127">Single Sign-On</span></span>  
  
4.  <span data-ttu-id="a688c-128">選択**はい**の**SSO を使用する**でのシングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="a688c-128">Select **Yes** for **Use SSO** to use Single Sign-On.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a688c-129">詳細については、次を参照してください。[シングル サインオンを使用して](../core/using-single-sign-on2.md)です。</span><span class="sxs-lookup"><span data-stu-id="a688c-129">For more information, see [Using Single Sign-On](../core/using-single-sign-on2.md).</span></span>  
  
5.  <span data-ttu-id="a688c-130">一覧で関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a688c-130">Select an affiliate application in the list.</span></span>  
  
     <span data-ttu-id="a688c-131">エンタープライズ シングル サインオン ツールで作成される関連アプリケーションは、PeopleSoft などのアプリケーションを表します。</span><span class="sxs-lookup"><span data-stu-id="a688c-131">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as PeopleSoft.</span></span> <span data-ttu-id="a688c-132">BizTalk Adapter for PeopleSoft Enterprise は、アプリケーション ユーザーの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="a688c-132">Microsoft BizTalk Adapter for PeopleSoft Enterprise uses the credentials of an application user.</span></span> <span data-ttu-id="a688c-133">これらの資格情報は、指定された関連アプリケーションのサーバー システムの SSO データベースから取得されます。</span><span class="sxs-lookup"><span data-stu-id="a688c-133">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span> <span data-ttu-id="a688c-134">取得される資格情報は、BizTalk プロジェクトを起動したユーザー (アプリケーション ユーザー) の資格情報です。</span><span class="sxs-lookup"><span data-stu-id="a688c-134">The credentials are those of the user (the application user) who launched the BizTalk project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a688c-135">関連アプリケーションを作成する方法の詳細については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications2.md)、または Microsoft BizTalk Server のオンライン ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="a688c-135">For more information about how to create affiliate applications, see [Creating Affiliate Applications](../core/creating-affiliate-applications2.md), or the Microsoft BizTalk Server online Help.</span></span>  
  
6.  <span data-ttu-id="a688c-136">接続情報を受け入れるように必要なすべての情報を提供すると、をクリックして**適用**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="a688c-136">After providing all required information to accept the connection information, click **Apply**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="a688c-137">PeopleSoft にアクセスするには、BizTalk Adapter for PeopleSoft Enterprise に接続パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a688c-137">You must set connection parameters for the BizTalk Adapter for PeopleSoft Enterprise to access PeopleSoft.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a688c-138">参照</span><span class="sxs-lookup"><span data-stu-id="a688c-138">See Also</span></span>  
 [<span data-ttu-id="a688c-139">PeopleSoft 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="a688c-139">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)