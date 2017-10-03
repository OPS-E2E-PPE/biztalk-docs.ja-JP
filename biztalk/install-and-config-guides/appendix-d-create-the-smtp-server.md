---
title: "付録 d: SMTP サーバーの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7441ba9-a498-42ec-a04d-7f2731407373
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f4d4acc35f5cb38be5f783ee7c4017c8ada83e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="appendix-d-create-the-smtp-server"></a><span data-ttu-id="b652a-102">付録 D: SMTP サーバーの作成</span><span class="sxs-lookup"><span data-stu-id="b652a-102">Appendix D: Create the SMTP Server</span></span>
<span data-ttu-id="b652a-103">SQL Server Database Mail で使用される SMTP サーバーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b652a-103">Create the SMTP Server used by SQL Server Database Mail.</span></span>  
  
<span data-ttu-id="b652a-104">次の SQL バージョンのいずれかを使用する場合は、BAM 警告の構成に SQL Server Database Mail が必要です。</span><span class="sxs-lookup"><span data-stu-id="b652a-104">SQL Server Database Mail is required to configure BAM Alerts when using any of the following SQL versions:</span></span> 

* [!INCLUDE[sqlserver2016_md](../includes/sqlserver2016-md.md)]
* [!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)]
* [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] 
  
 <span data-ttu-id="b652a-105">SQL Server Database Mail では SMTP サーバーを使用して BAM 警告を送信します。</span><span class="sxs-lookup"><span data-stu-id="b652a-105">SQL Server Database Mail uses an SMTP Server to send BAM Alerts.</span></span> <span data-ttu-id="b652a-106">SMTP サーバーは、インターネット インフォメーション サービス (IIS) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="b652a-106">SMTP Server is included with Internet Information Services (IIS).</span></span> <span data-ttu-id="b652a-107">SMTP サーバーは BizTalk Server のローカル、または IIS のインストールされた別のサーバーにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="b652a-107">SMTP can be installed locally on the BizTalk Server or on another server with IIS installed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b652a-108">通常、Windows 10 や Windows 7 などのクライアント オペレーティング システムには、SMTP サーバーの機能は含まれません。</span><span class="sxs-lookup"><span data-stu-id="b652a-108">Typically, client operating systems like Windows 10, Windows 7, and so on, do not include SMTP Server capabilities.</span></span> <span data-ttu-id="b652a-109">IIS 内の *SMTP Email* 機能を使用して、Windows Server の既存の SMTP サーバーに接続することができます。</span><span class="sxs-lookup"><span data-stu-id="b652a-109">You can connect to an existing SMTP Server on a Windows Server using the *SMTP E-mail* feature within IIS.</span></span> <span data-ttu-id="b652a-110">*SMTP Email* 機能は、SQL Server Database Mail で必要とされる SMTP サーバーではないため、</span><span class="sxs-lookup"><span data-stu-id="b652a-110">The *SMTP E-mail* feature is NOT an SMTP Server, which is required for SQL Server Database Mail.</span></span> <span data-ttu-id="b652a-111">このトピックではクライアント オペレーティング システムでの SMTP サーバーのインストールと構成手順は省きます。</span><span class="sxs-lookup"><span data-stu-id="b652a-111">As a result, this topic does not include the steps to install and configure an SMTP Server on client operating systems.</span></span>  

## <a name="install-and-configure-the-smtp-server"></a><span data-ttu-id="b652a-112">SMTP サーバーのインストールと構成</span><span class="sxs-lookup"><span data-stu-id="b652a-112">Install and configure the SMTP server</span></span>  
  
<span data-ttu-id="b652a-113">この手順の適用対象:</span><span class="sxs-lookup"><span data-stu-id="b652a-113">These steps apply to:</span></span>

* <span data-ttu-id="b652a-114">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="b652a-114">Windows Server 2016</span></span>
* <span data-ttu-id="b652a-115">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="b652a-115">Windows Server 2012 R2</span></span>
* <span data-ttu-id="b652a-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="b652a-116">Windows Server 2012</span></span>
  
### <a name="install-smtp-server"></a><span data-ttu-id="b652a-117">SMTP サーバーのインストール</span><span class="sxs-lookup"><span data-stu-id="b652a-117">Install SMTP Server</span></span>  
   
1.  <span data-ttu-id="b652a-118">**[サーバー マネージャー]** で、左ペインにある **[ダッシュボード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-118">In **Server Manager**, select **Dashboard** in the left pane.</span></span>  
  
3.  <span data-ttu-id="b652a-119">**[役割と機能の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-119">Select **Add roles and features**.</span></span> <span data-ttu-id="b652a-120">**[役割と機能の追加]** は、右上隅にある **[管理]** メニューから開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="b652a-120">**Add Roles and Features** can also be opened from the **Manage** menu in the top right-hand corner.</span></span>  
  
4.  <span data-ttu-id="b652a-121">**[はじめに]** で、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-121">In **Before You Begin**, select **Next**.</span></span>  
  
5.  <span data-ttu-id="b652a-122">**[役割ベースまたは機能ベースのインストール]**、**[次へ]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-122">Select **Role-based or feature-based installation**, and select **Next**.</span></span>  
  
6.  <span data-ttu-id="b652a-123">**[サーバー プールからサーバーを選択]** を選択し、必要なサーバーを選択して **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-123">Select **Select a server from the server pool**, select the desired server, and select **Next**.</span></span> <span data-ttu-id="b652a-124">**[サーバーの選択]** ウィンドウには、**[サーバー マネージャー]** の **[サーバーの追加]** で追加したサーバーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b652a-124">The **Server Selection** window lists the servers that have been added using **Add Server** in **Server Manager**.</span></span> <span data-ttu-id="b652a-125">既定では、ローカル サーバーが選択されます。</span><span class="sxs-lookup"><span data-stu-id="b652a-125">By default, it selects the local server.</span></span>  
  
7.  <span data-ttu-id="b652a-126">**[サーバーの役割]** で **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-126">In **Server Roles**, select **Next**.</span></span>  
  
8.  <span data-ttu-id="b652a-127">**[機能]** で、**[SMTP サーバー]** のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b652a-127">In **Features**, check **SMTP Server**.</span></span> <span data-ttu-id="b652a-128">メッセージが表示されたら、**[機能の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-128">If prompted, select **Add Features**.</span></span> <span data-ttu-id="b652a-129">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-129">Select **Next**.</span></span>  
  
9. <span data-ttu-id="b652a-130">**[確認]** で、**[必要に応じて対象サーバーを自動的に再起動する]** を選択し、**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-130">In **Confirmation**, select **Restart the destination server automatically if required**, and select **Install**.</span></span> <span data-ttu-id="b652a-131">完了したら、**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-131">When complete, select **Close**.</span></span>  

### <a name="configure-the-smtp-server"></a><span data-ttu-id="b652a-132">SMTP サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="b652a-132">Configure the SMTP Server</span></span>  
 <span data-ttu-id="b652a-133">IIS 6.0 マネージャーを使用して SMTP 仮想サーバーを構成するには、次の手順を実行します:</span><span class="sxs-lookup"><span data-stu-id="b652a-133">The following steps configure the SMTP Virtual Server using the IIS 6.0 Manager:</span></span>  
  
1.  <span data-ttu-id="b652a-134">IIS マネージャーを開く: [スタート] で、**inetmgr6.exe** を検索して開きます。</span><span class="sxs-lookup"><span data-stu-id="b652a-134">Open the IIS Manager: In Start, search for **inetmgr6.exe**, and open it.</span></span>  
  
2.  <span data-ttu-id="b652a-135">コンピューター名を展開します。</span><span class="sxs-lookup"><span data-stu-id="b652a-135">Expand the computer name.</span></span> <span data-ttu-id="b652a-136">**[SMTP Virtual Server #1]** を右クリックして **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-136">Right-click **[SMTP Virtual Server #1]**, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="b652a-137">**[アクセス]** タブの **[リレー]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-137">In the **Access** tab, select the **Relay** button.</span></span>  
  
4.  <span data-ttu-id="b652a-138">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-138">Select **Add**.</span></span> <span data-ttu-id="b652a-139">**[1 台のコンピューター]** で、「`127.0.0.1`」と入力して **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-139">For **Single Computer**, enter `127.0.0.1`, and select **OK**.</span></span>  
  
     <span data-ttu-id="b652a-140">「127.0.0.1」を追加することで、ローカル サーバーがこの SMTP サーバーからメッセージを送信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b652a-140">By adding 127.0.0.1, we are allowing the local server to send messages from this SMTP Server.</span></span> <span data-ttu-id="b652a-141">他にこの SMTP サーバーからメッセージを送信するコンピューターがある場合は、その IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="b652a-141">If you want additional computers to send messages from this SMTP server, enter their IP addresses.</span></span>  
  
5.  <span data-ttu-id="b652a-142">**[配信]** タブで **[送信のセキュリティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-142">In the **Delivery** tab, select **Outbound Security**.</span></span> <span data-ttu-id="b652a-143">以下から選択します:</span><span class="sxs-lookup"><span data-stu-id="b652a-143">Choose from the following:</span></span>  
  
     <span data-ttu-id="b652a-144">**匿名アクセス**: アカウント名やパスワードは不要です。</span><span class="sxs-lookup"><span data-stu-id="b652a-144">**Anonymous access**: An account name or password is not required.</span></span> <span data-ttu-id="b652a-145">このオプションを使用すると、SMTP サーバーの認証が無効になります。</span><span class="sxs-lookup"><span data-stu-id="b652a-145">This option disables authentication for the SMTP Server.</span></span>  
  
     <span data-ttu-id="b652a-146">**基本認証**: 接続先のサーバーのアカウント名とパスワードがクリア テキストとして送信されます。</span><span class="sxs-lookup"><span data-stu-id="b652a-146">**Basic authentication**: The account name and password of the server that you are connecting to are sent as clear text.</span></span> <span data-ttu-id="b652a-147">入力したこのアカウントからメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="b652a-147">This account you enter transmits the e-mails.</span></span> <span data-ttu-id="b652a-148">基本認証は、個人アカウントや Exchange アカウントにメールを送信する場合に選択できます。</span><span class="sxs-lookup"><span data-stu-id="b652a-148">Basic Authentication can be selected when sending e-mail to a personal account or an Exchange account.</span></span> <span data-ttu-id="b652a-149">資格情報がクリア テキストとして渡されるため、**[TLS 暗号化]** を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b652a-149">Because the credentials are passed in clear text, it is recommended to enable **TLS encryption**.</span></span>  
  
     <span data-ttu-id="b652a-150">**統合 Windows 認証**: Windows のドメイン アカウント名とパスワードが認証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b652a-150">**Integrated Windows Authentication**: The Windows domain account name and password are used to authenticate.</span></span> <span data-ttu-id="b652a-151">入力したアカウントからメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="b652a-151">The account you enter transmits the e-mails.</span></span>  
  
     <span data-ttu-id="b652a-152">**TLS 暗号化**: SSL と同様に、TLS では安全な接続が確保されます。</span><span class="sxs-lookup"><span data-stu-id="b652a-152">**TLS encryption**: Similar to SSL, TLS secures the connection.</span></span> <span data-ttu-id="b652a-153">有効な SSL サーバー証明書がこのサーバーにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b652a-153">Requires a valid SSL server certificate installed on this server.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="b652a-154">個人用メール アカウント (Exchange アカウントを含む) を使用して SMTP のコア機能をテストするには、**[匿名アクセス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-154">To test core SMTP functionality with a personal e-mail account, including an Exchange account, select **Anonymous access**.</span></span> <span data-ttu-id="b652a-155">基本認証を選択している場合、SMTP は AUTH コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b652a-155">When Basic authentication is selected, SMTP uses the AUTH command.</span></span> <span data-ttu-id="b652a-156">メールのプロバイダーによっては、AUTH コマンドが原因でエラーが生じる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b652a-156">Some e-mail providers may fail because of the AUTH command.</span></span> <span data-ttu-id="b652a-157">AUTH コマンドに失敗した場合は、SMTP サーバーの Windows イベント ログにエラーが記録される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b652a-157">If the AUTH command fails, an error may be logged in the Windows event logs on the SMTP Server.</span></span>  
  
6.  <span data-ttu-id="b652a-158">**[配信]** タブで **[送信接続]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-158">In the **Delivery** tab, select **Outbound connections**.</span></span> <span data-ttu-id="b652a-159">既定の TCP ポートは 25 です。</span><span class="sxs-lookup"><span data-stu-id="b652a-159">By default, the TCP Port is 25.</span></span> <span data-ttu-id="b652a-160">ファイアウォール内で空いていれば、他のポートを入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="b652a-160">A different port can be entered if it is open within your firewall.</span></span> <span data-ttu-id="b652a-161">[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-161">Select **OK**.</span></span>  
  
7.  <span data-ttu-id="b652a-162">**[配信]** タブで **[詳細設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-162">In the **Delivery** tab, select **Advanced**.</span></span> <span data-ttu-id="b652a-163">既定では、ローカル サーバーの**完全修飾ドメイン名**が一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b652a-163">By default, the **Fully Qualified Domain Name** of the local server is listed.</span></span> <span data-ttu-id="b652a-164">インターネット プロバイダーによっては、**スマート ホスト**のプロパティを空白にしておくことができます。</span><span class="sxs-lookup"><span data-stu-id="b652a-164">Depending on the internet provider, the **Smart Host** property can remain empty.</span></span> <span data-ttu-id="b652a-165">スマート ホストが必要かどうか、インターネット プロバイダーに問い合わせる必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="b652a-165">You may need to contact the internet provider to confirm if a Smart Host is required.</span></span> <span data-ttu-id="b652a-166">または、「smtp.*EMailProvider*.com」と入力します。</span><span class="sxs-lookup"><span data-stu-id="b652a-166">Otherwise, you may be able to enter smtp.*EMailProvider*.com.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b652a-167">**スマート ホスト**は別名リレー ホストと呼ばれ、Exchange Server でのすべての送信メッセージのルーティングに使用される専用サーバーです。</span><span class="sxs-lookup"><span data-stu-id="b652a-167">A **Smart Host**, also known as a relay host, is a dedicated server used by an Exchange Server to route all outgoing messages.</span></span> <span data-ttu-id="b652a-168">**スマート ホスト**がメッセージを受信すると、メッセージはリモート ドメインへ転送されます。****</span><span class="sxs-lookup"><span data-stu-id="b652a-168">When the **Smart Host** receives the messages, the **Smart Host** forwards the messages to a remote domain.</span></span> <span data-ttu-id="b652a-169">**スマート ホスト** の目的は、Exchange Server のパフォーマンスを向上させることです。</span><span class="sxs-lookup"><span data-stu-id="b652a-169">The goal of a **Smart Host** is to improve performance of an Exchange Server.</span></span> <span data-ttu-id="b652a-170">Exchange Server は、接続が確立するまでリモート ドメインに繰り返し通信する代わりに、スマート ホストにのみ送信します。</span><span class="sxs-lookup"><span data-stu-id="b652a-170">The Exchange Server only transmits to the smart host; instead of repeatedly contacting the remote domain until a connection is made.</span></span>  
  
8.  <span data-ttu-id="b652a-171">**[OK]** をクリックして、すべてのウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b652a-171">Select **OK** to close all windows.</span></span>  
  
9. <span data-ttu-id="b652a-172">SMTP Server を再起動する: **[SMTP Virtual Server #1]** を右クリックして、**[停止]** を選択し、**[起動]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-172">Restart the SMTP Server: Right-click **[SMTP Virtual Server #1]**, select **Stop**, and then select **Start**.</span></span> <span data-ttu-id="b652a-173">SMTP サーバーの設定を適用するには、再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b652a-173">A restart is needed to apply the SMTP Server settings.</span></span> 

  
## <a name="windows-server-2008-r2-install-and-configure-smtp-server"></a><span data-ttu-id="b652a-174">Windows Server 2008 R2: SMTP サーバーのインストールと構成</span><span class="sxs-lookup"><span data-stu-id="b652a-174">Windows Server 2008 R2: Install and Configure SMTP Server</span></span>  
  
### <a name="install-smtp-server"></a><span data-ttu-id="b652a-175">SMTP サーバーのインストール</span><span class="sxs-lookup"><span data-stu-id="b652a-175">Install SMTP Server</span></span>  
 <span data-ttu-id="b652a-176">SMTP サーバー機能をインストールするには、次の手順を実行します:</span><span class="sxs-lookup"><span data-stu-id="b652a-176">The following steps install the SMTP Server feature:</span></span>  
  
1.  <span data-ttu-id="b652a-177">**[サーバー マネージャー]** で、**[機能]**、**[機能の追加]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-177">In **Server Manager**, select **Features**, and select **Add Features**.</span></span>  
  
3.  <span data-ttu-id="b652a-178">**[機能の追加]** で、**[SMTP サーバー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-178">In **Add Features**, select **SMTP Server**.</span></span> <span data-ttu-id="b652a-179">メッセージが表示されたら、**[必要な役割サービスを追加]**、**[次へ]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-179">If prompted, select **Add Required Role Services**, and select **Next**.</span></span>  
  
4.  <span data-ttu-id="b652a-180">**[次へ]** を選択してインストールを続けます。</span><span class="sxs-lookup"><span data-stu-id="b652a-180">Continue with the installation by selecting **Next**.</span></span>  
  
5.  <span data-ttu-id="b652a-181">**[インストール オプションの確認]** ウィンドウで、**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-181">In the **Confirm Installation Selections** window, select **Install**.</span></span> <span data-ttu-id="b652a-182">完了したら、**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-182">When complete, select **Close**.</span></span>  
  
### <a name="configure-the-smtp-server"></a><span data-ttu-id="b652a-183">SMTP サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="b652a-183">Configure the SMTP Server</span></span>  
 <span data-ttu-id="b652a-184">IIS 6.0 マネージャーを使用して SMTP 仮想サーバーを構成するには、次の手順を実行します:</span><span class="sxs-lookup"><span data-stu-id="b652a-184">The following steps configure the SMTP Virtual Server using the IIS 6.0 Manager:</span></span>  
  
1.  <span data-ttu-id="b652a-185">IIS 6.0 マネージャーを開く: **[スタート]** で、**IIS** を検索し、**[インターネット インフォメーション サービス (IIS) 6.0 マネージャー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-185">Open the IIS 6.0 Manager: In **Start**, search for **IIS**, and select **Internet Information Services (IIS) 6.0 Manager**.</span></span>  
  
2.  <span data-ttu-id="b652a-186">コンピューター名を展開します。</span><span class="sxs-lookup"><span data-stu-id="b652a-186">Expand the computer name.</span></span> <span data-ttu-id="b652a-187">**[SMTP Virtual Server #1]** を右クリックして **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-187">Right-click **[SMTP Virtual Server #1]**, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="b652a-188">**[アクセス]** タブの **[リレー]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-188">In the **Access** tab, select the **Relay** button.</span></span>  
  
4.  <span data-ttu-id="b652a-189">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-189">Select **Add**.</span></span> <span data-ttu-id="b652a-190">**[1 台のコンピューター]** で、「`127.0.0.1`」と入力して **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-190">For **Single Computer**, enter `127.0.0.1`, and select **OK**.</span></span>  
  
     <span data-ttu-id="b652a-191">「127.0.0.1」を追加することで、ローカル サーバーがこの SMTP サーバーからメッセージを送信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b652a-191">By adding 127.0.0.1, we are allowing the local server to send messages from this SMTP Server.</span></span> <span data-ttu-id="b652a-192">他にこの SMTP サーバーからメッセージを送信するコンピューターがある場合は、その IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="b652a-192">If you want additional computers to send messages from this SMTP server, enter their IP addresses.</span></span>  
  
5.  <span data-ttu-id="b652a-193">**[配信]** タブで **[送信のセキュリティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-193">In the **Delivery** tab, select **Outbound Security**.</span></span> <span data-ttu-id="b652a-194">以下から選択します:</span><span class="sxs-lookup"><span data-stu-id="b652a-194">Choose from the following:</span></span>  
  
     <span data-ttu-id="b652a-195">**匿名アクセス**: アカウント名やパスワードは不要です。</span><span class="sxs-lookup"><span data-stu-id="b652a-195">**Anonymous access**: An account name or password is not required.</span></span> <span data-ttu-id="b652a-196">このオプションを使用すると、SMTP サーバーの認証が無効になります。</span><span class="sxs-lookup"><span data-stu-id="b652a-196">This option disables authentication for the SMTP Server.</span></span>  
  
     <span data-ttu-id="b652a-197">**基本認証**: 接続先のサーバーのアカウント名とパスワードがクリア テキストとして送信されます。</span><span class="sxs-lookup"><span data-stu-id="b652a-197">**Basic authentication**: The account name and password of the server that you are connecting to are sent as clear text.</span></span> <span data-ttu-id="b652a-198">基本認証は、個人アカウントや Exchange アカウントにメールを送信する場合に選択できます。</span><span class="sxs-lookup"><span data-stu-id="b652a-198">Basic Authentication can be selected when sending e-mail to a personal account or an Exchange account.</span></span> <span data-ttu-id="b652a-199">資格情報がクリア テキストとして渡されるため、**[TLS 暗号化]** を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b652a-199">Because the credentials are passed in clear text, it is recommended to enable **TLS encryption**.</span></span>  
  
     <span data-ttu-id="b652a-200">**統合 Windows 認証**: Windows のドメイン アカウント名とパスワードが認証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b652a-200">**Integrated Windows Authentication**: The Windows domain account name and password are used to authenticate.</span></span> <span data-ttu-id="b652a-201">入力したアカウントからメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="b652a-201">The account you enter transmits the e-mails.</span></span>  
  
     <span data-ttu-id="b652a-202">**TLS 暗号化**: SSL と同様に、TLS では安全な接続が確保されます。</span><span class="sxs-lookup"><span data-stu-id="b652a-202">**TLS encryption**: Similar to SSL, TLS secures the connection.</span></span> <span data-ttu-id="b652a-203">有効な SSL サーバー証明書がこのサーバーにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b652a-203">Requires a valid SSL server certificate installed on this server.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="b652a-204">個人用メール アカウント (Exchange アカウントを含む) を使用して SMTP のコア機能をテストするには、**[匿名アクセス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-204">To test core SMTP functionality with a personal e-mail account, including an Exchange account, select **Anonymous access**.</span></span> <span data-ttu-id="b652a-205">基本認証を選択している場合、SMTP は AUTH コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b652a-205">When Basic authentication is selected, SMTP uses the AUTH command.</span></span> <span data-ttu-id="b652a-206">メールのプロバイダーによっては、AUTH コマンドが原因でエラーが生じる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b652a-206">Some e-mail providers may fail because of the AUTH command.</span></span> <span data-ttu-id="b652a-207">AUTH コマンドに失敗した場合は、SMTP サーバーの Windows イベント ログにエラーが記録される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b652a-207">If the AUTH command fails, an error may be logged in the Windows event logs on the SMTP Server.</span></span>  
  
6.  <span data-ttu-id="b652a-208">**[配信]** タブで **[送信接続]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-208">In the **Delivery** tab, select **Outbound connections**.</span></span> <span data-ttu-id="b652a-209">既定の TCP ポートは 25 です。</span><span class="sxs-lookup"><span data-stu-id="b652a-209">By default, the TCP Port is 25.</span></span> <span data-ttu-id="b652a-210">ファイアウォール内で空いていれば、他のポートを入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="b652a-210">A different port can be entered if it is open within your firewall.</span></span> <span data-ttu-id="b652a-211">[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-211">Select **OK**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="b652a-212">TCP ポートは、受信接続と送信接続に使用できます。</span><span class="sxs-lookup"><span data-stu-id="b652a-212">The TCP Port can be used for Inbound connections and Outbound connections.</span></span>  
  
7.  <span data-ttu-id="b652a-213">**[配信]** タブで **[詳細設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-213">In the **Delivery** tab, select **Advanced**.</span></span> <span data-ttu-id="b652a-214">既定では、ローカル サーバーの**完全修飾ドメイン名**が一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b652a-214">By default, the **Fully Qualified Domain Name** of the local server is listed.</span></span> <span data-ttu-id="b652a-215">インターネット プロバイダーによっては、**スマート ホスト**のプロパティを空白にしておくことができます。</span><span class="sxs-lookup"><span data-stu-id="b652a-215">Depending on the internet provider, the **Smart Host** property can remain empty.</span></span> <span data-ttu-id="b652a-216">スマート ホストが必要かどうか、インターネット プロバイダーに問い合わせる必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="b652a-216">You may need to contact the internet provider to confirm if a Smart Host is required.</span></span> <span data-ttu-id="b652a-217">または、「smtp.*EMailProvider*.com」と入力します。</span><span class="sxs-lookup"><span data-stu-id="b652a-217">Otherwise, you may be able to enter smtp.*EMailProvider*.com.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b652a-218">**スマート ホスト**は別名リレー ホストと呼ばれ、Exchange Server でのすべての送信メッセージのルーティングに使用される専用サーバーです。</span><span class="sxs-lookup"><span data-stu-id="b652a-218">A **Smart Host**, also known as a relay host, is a dedicated server used by an Exchange Server to route all outgoing messages.</span></span> <span data-ttu-id="b652a-219">**スマート ホスト**がメッセージを受信すると、メッセージはリモート ドメインへ転送されます。****</span><span class="sxs-lookup"><span data-stu-id="b652a-219">When the **Smart Host** receives the messages, the **Smart Host** forwards the messages to a remote domain.</span></span> <span data-ttu-id="b652a-220">**スマート ホスト** の目的は、Exchange Server のパフォーマンスを向上させることです。</span><span class="sxs-lookup"><span data-stu-id="b652a-220">The goal of a **Smart Host** is to improve performance of an Exchange Server.</span></span> <span data-ttu-id="b652a-221">Exchange Server は、接続が確立するまでリモート ドメインに繰り返し通信する代わりに、スマート ホストにのみ送信します。</span><span class="sxs-lookup"><span data-stu-id="b652a-221">The Exchange Server only transmits to the smart host; instead of repeatedly contacting the remote domain until a connection is made.</span></span>  
  
8.  <span data-ttu-id="b652a-222">**[OK]** をクリックして、すべてのウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b652a-222">Select **OK** to close all windows.</span></span>  
  
9. <span data-ttu-id="b652a-223">SMTP サーバーの設定を適用するには、再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b652a-223">A restart is needed to apply the SMTP Server settings.</span></span> <span data-ttu-id="b652a-224">SMTP Server を再起動する: **[SMTP Virtual Server #1]** を右クリックして、**[停止]** を選択し、**[起動]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b652a-224">To restart the SMTP Server: Right-click **[SMTP Virtual Server #1]**, select **Stop**, and then select **Start**.</span></span>  
  
  
## <a name="test-the-smtp-server"></a><span data-ttu-id="b652a-225">SMTP サーバーのテスト</span><span class="sxs-lookup"><span data-stu-id="b652a-225">Test the SMTP Server</span></span>  
 <span data-ttu-id="b652a-226">Telnet を使用して、SMTP サーバーの構成をテストできます。</span><span class="sxs-lookup"><span data-stu-id="b652a-226">Telnet can be used to test the SMTP Server configuration.</span></span> <span data-ttu-id="b652a-227">次の手順では、構成した SMTP サーバーを使用して、メール アドレスにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="b652a-227">The following steps send a message using your configured SMTP Server to an e-mail address.</span></span> <span data-ttu-id="b652a-228">telnet コマンドについては、[http://support.microsoft.com/kb/153119](http://support.microsoft.com/kb/153119) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b652a-228">[http://support.microsoft.com/kb/153119](http://support.microsoft.com/kb/153119) provides descriptions of the telnet commands.</span></span>  
  
1.  <span data-ttu-id="b652a-229">管理者としてコマンド ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="b652a-229">Open a command window as Administrator.</span></span>
  
2.  <span data-ttu-id="b652a-230">コマンド プロンプトで、次のように入力します:</span><span class="sxs-lookup"><span data-stu-id="b652a-230">In the command prompt, type:</span></span>  
  
     `telnet localhost 25`  
  
     <span data-ttu-id="b652a-231">telnet がインストールされていない場合は、次のように入力してインストールします:</span><span class="sxs-lookup"><span data-stu-id="b652a-231">If telnet is not installed, install it by typing:</span></span>  
  
     `pkgmgr /iu:"TelnetClient"`  
  
3.  <span data-ttu-id="b652a-232">次のように入力して通信を開始します:</span><span class="sxs-lookup"><span data-stu-id="b652a-232">Start communication by typing:</span></span>  
  
     `EHLO server`  
  
4.  <span data-ttu-id="b652a-233">送信者アドレスを入力します:</span><span class="sxs-lookup"><span data-stu-id="b652a-233">Enter the Mail From address:</span></span>  
  
     `MAIL FROM: *YourEmailAddress*@*YourProvider*.com`  
  
     <span data-ttu-id="b652a-234">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b652a-234">For example, enter:</span></span>  
  
     `MAIL FROM: EmailAddress@outlook.com`  
  
5.  <span data-ttu-id="b652a-235">送信先アドレスを入力します:</span><span class="sxs-lookup"><span data-stu-id="b652a-235">Enter the Mail To address:</span></span>  
  
     `RCPT TO: *YourEmailAddress*@*YourProvider*.com`  
  
     <span data-ttu-id="b652a-236">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b652a-236">For example, enter:</span></span>  
  
     `RCPT TO: EmailAddress@outlook.com`  
  
6.  <span data-ttu-id="b652a-237">次のように入力して SMTP サーバーにデータの送信準備ができたことを伝えます:</span><span class="sxs-lookup"><span data-stu-id="b652a-237">Tell the SMTP Server you are ready to send data by typing:</span></span>  
  
     `DATA`  
  
7.  <span data-ttu-id="b652a-238">次のように入力して件名を入力します:</span><span class="sxs-lookup"><span data-stu-id="b652a-238">Enter the Subject by typing:</span></span>  
  
     `Subject: Test Message`  
  
8.  <span data-ttu-id="b652a-239">Enter キーを 2 回押します。</span><span class="sxs-lookup"><span data-stu-id="b652a-239">Hit Enter twice.</span></span>  
  
9. <span data-ttu-id="b652a-240">次のようにメッセージ本文を入力します:</span><span class="sxs-lookup"><span data-stu-id="b652a-240">Enter the message body by typing:</span></span>  
  
     `This is the message body of the test message.`  
  
10. <span data-ttu-id="b652a-241">Enter を押し、ピリオド (.) を入力して、Enter を押します。</span><span class="sxs-lookup"><span data-stu-id="b652a-241">Hit Enter, type a period (.), and hit Enter.</span></span>  
  
 <span data-ttu-id="b652a-242">メール メッセージの RCPT TO アドレスを確認します。</span><span class="sxs-lookup"><span data-stu-id="b652a-242">Check the RCPT TO address for the e-mail message.</span></span> <span data-ttu-id="b652a-243">メールが配信されない場合は (受信トレイと迷惑メール フォルダーを確認してください)、メッセージが正常に送信されておらず、SMTP キュー フォルダー (C:\inetpub\mailroot\Queue) に残っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b652a-243">If the e-mail is not delivered (Check your Inbox and Spam folder), then the message was not successfully sent, and may reside in the SMTP Queue folder (C:\inetpub\mailroot\Queue).</span></span>  
  