---
redirect_url: /biztalk/core/creating-peoplesoft-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 7d7c30262fabbbde4f555deb7f0b01c3ef4ffb95
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262989"
---
# <a name="optimize-configuration"></a><span data-ttu-id="d4b0c-101">構成を最適化します。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-101">Optimize configuration</span></span>
<span data-ttu-id="d4b0c-102">このセクションでは、BizTalk adapter for PeopleSoft Enterprise 構成を最適化する方法について説明し、アダプターを設定するためのパラメーターの説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-102">This section contains information about how to optimize your configuration of BizTalk Adapter for PeopleSoft Enterprise and includes parameter descriptions for setting up the adapter.</span></span>  
  
## <a name="message-overload-protection"></a><span data-ttu-id="d4b0c-103">メッセージ オーバー ロードの保護</span><span class="sxs-lookup"><span data-stu-id="d4b0c-103">Message Overload Protection</span></span>  
 <span data-ttu-id="d4b0c-104">`Max Concurrent Calls`パラメーターは、機能、構成を最適化することができます。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-104">The `Max Concurrent Calls` parameter is a feature that enables you to optimize your configuration.</span></span> <span data-ttu-id="d4b0c-105">スループットがバックエンド処理機能を上回るインスタンスでは、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-105">You use this parameter in instances where the throughput exceeds back-end processing capabilities.</span></span> <span data-ttu-id="d4b0c-106">パラメーターを追加するには、アダプターに、**送信ポートのトランスポート プロパティ**メッセージ オーバー ロードの保護をアクティブにする ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-106">You can add the parameter to the adapters in the **Send Port Transport Properties** dialog box to activate message overload protection.</span></span> <span data-ttu-id="d4b0c-107">既定値は -1 です。これは呼び出しが制限されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-107">The default is -1, meaning the calls are unlimited.</span></span>  
  
 <span data-ttu-id="d4b0c-108">BizTalk Server では、送信アダプターにメッセージを送信するときに最初にアダプターからバッチを受信し、呼び出します`TransmitMessage()`で各メッセージを送信するバッチ。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-108">When BizTalk Server submits messages to the transmit adapter, it first receives a batch from the adapter and invokes `TransmitMessage()` on the batch to transmit each message.</span></span> <span data-ttu-id="d4b0c-109">この処理が完了すると、BizTalk Server はバッチで `Done()` を呼び出し、アダプタがバックエンドに対するメッセージ送信を開始します。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-109">When done, BizTalk Server invokes `Done()` on the batch, and the adapter starts transmitting the messages to the back-end.</span></span> <span data-ttu-id="d4b0c-110">BizTalk Server は、前に複数のバッチを取得した場合`Done`が呼び出される、`Done`コマンドが発生することはありません。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-110">If BizTalk Server obtains multiple batches before `Done` is invoked, the `Done` command might never occur.</span></span> <span data-ttu-id="d4b0c-111">バッチ内に含めるメッセージの最大数を設定することで、バックエンドに送信するメッセージを制御できます。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-111">By setting the maximum number of messages in a batch, you can control messages to the back-end.</span></span> <span data-ttu-id="d4b0c-112">このパラメーターを変更するには、1 分で有効です。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-112">Changing this parameter takes effect in a minute.</span></span> <span data-ttu-id="d4b0c-113">BizTalk Server では、SQL database に保存されているアダプター構成に対する変更を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-113">BizTalk Server must retrieve the changes to the adapter configuration that is saved in the SQL database.</span></span>  
  
## <a name="change-the-max-concurrent-calls-parameter"></a><span data-ttu-id="d4b0c-114">Max Concurrent Calls パラメーターを変更します。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-114">Change the Max Concurrent Calls parameter</span></span>  
  
1.  <span data-ttu-id="d4b0c-115">**送信ポートのトランスポート プロパティ** ダイアログ ボックスに、入力、**接続**値。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-115">In the **Send Port Transport Properties** dialog box, enter a **Connection** value.</span></span>  
  
     <span data-ttu-id="d4b0c-116">既定値は、40 セッションです。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-116">The default value is 40 sessions.</span></span> <span data-ttu-id="d4b0c-117">小さい値を使用する場合は、実行時のパフォーマンスの低下があります。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-117">If you use a smaller value, you might experience degradation in run-time performance.</span></span> <span data-ttu-id="d4b0c-118">逆の場合も同様です。大きい値には、実行時エラーの結果、サーバーの機能を超える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-118">The opposite is also true; a bigger value could exceed the ability of the server and result in run-time errors.</span></span>  
  
2.  <span data-ttu-id="d4b0c-119">選択**はい**の**エージェントの更新**runtimeagent.exe および browsingagent.exe の処理を必要な場合に自動的に再起動を強制します。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-119">Select **Yes** for **Refresh Agent** to force the runtimeagent.exe and the browsingagent.exe processes to restart automatically when required.</span></span>  
  
     <span data-ttu-id="d4b0c-120">たとえば、サーバーとの接続が失われた場合や、サーバーに追加したものが Microsoft アダプター ウィザードに表示されない場合に、処理を自動的に再起動することができます。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-120">For example, you want the process to restart automatically if it loses connection with the server, or if you add something to the server and it does not appear in the Microsoft Adapter Wizard for selection.</span></span>  
  
     <span data-ttu-id="d4b0c-121">**エージェントの更新**両方参照エージェントとランタイム エージェント パラメーターを更新します。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-121">The **Refresh Agent** parameter refreshes both the browsing and the run-time agents.</span></span> <span data-ttu-id="d4b0c-122">または次の 1 つ分の遅延の後、runtimeagent.exe 更新プログラムは、呼び出しを送信します。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-122">The runtimeagent.exe updates after a delay of one minute or at the next send call.</span></span>  
  
3.  <span data-ttu-id="d4b0c-123">PeopleSoft システムにアクセスする資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-123">Provide credentials to access the PeopleSoft system.</span></span>  
  
     <span data-ttu-id="d4b0c-124">2 つのメソッドを使用するには、システムにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-124">You can use two methods to access the system:</span></span>  
  
    -   <span data-ttu-id="d4b0c-125">ログイン資格情報 (Transport Properties Login パラメーター)</span><span class="sxs-lookup"><span data-stu-id="d4b0c-125">Login Credentials (Transport Properties Login parameters)</span></span>  
  
    -   <span data-ttu-id="d4b0c-126">シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d4b0c-126">Single Sign-On</span></span>  
  
4.  <span data-ttu-id="d4b0c-127">選択**はい**の**を使用して SSO**でシングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-127">Select **Yes** for **Use SSO** to use Single Sign-On.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d4b0c-128">詳細については、次を参照してください。[アダプターのセキュリティ保護](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)します。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-128">For more information, see [Secure the adapter](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md).</span></span> 
  
5.  <span data-ttu-id="d4b0c-129">一覧で関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-129">Select an affiliate application in the list.</span></span>  
  
     <span data-ttu-id="d4b0c-130">エンタープライズ シングル サインオン ツールによって作成される関連アプリケーションは、PeopleSoft などのアプリケーションを表します。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-130">An affiliate application, created by Enterprise Single Sign-On tools, represents an application such as PeopleSoft.</span></span> <span data-ttu-id="d4b0c-131">Microsoft BizTalk Adapter for PeopleSoft Enterprise では、アプリケーション ユーザーの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-131">Microsoft BizTalk Adapter for PeopleSoft Enterprise uses the credentials of an application user.</span></span> <span data-ttu-id="d4b0c-132">これらの資格情報は、指定された関連アプリケーションのサーバー システムの SSO データベースから取得されます。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-132">These credentials are retrieved from the SSO database for the server system for a specified affiliate application.</span></span> <span data-ttu-id="d4b0c-133">資格情報では、BizTalk プロジェクトを起動したユーザー (アプリケーション ユーザー) のものです。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-133">The credentials are those of the user (the application user) who launched the BizTalk project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d4b0c-134">関連アプリケーションを作成する方法の詳細については、次を参照してください。[関連アプリケーションを作成する](../core/creating-affiliate-applications2.md)、または Microsoft BizTalk Server のオンライン ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-134">For more information about how to create affiliate applications, see [Creating Affiliate Applications](../core/creating-affiliate-applications2.md), or the Microsoft BizTalk Server online Help.</span></span>  
  
6.  <span data-ttu-id="d4b0c-135">接続情報を受け入れるように必要なすべての情報を提供するには、後に次のようにクリックします。**適用**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-135">After providing all required information to accept the connection information, click **Apply**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d4b0c-136">BizTalk Adapter for PeopleSoft Enterprise PeopleSoft へのアクセスの接続パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-136">You must set connection parameters for the BizTalk Adapter for PeopleSoft Enterprise to access PeopleSoft.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4b0c-137">参照</span><span class="sxs-lookup"><span data-stu-id="d4b0c-137">See Also</span></span>  
 [<span data-ttu-id="d4b0c-138">PeopleSoft 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="d4b0c-138">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)