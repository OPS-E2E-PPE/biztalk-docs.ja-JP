---
title: 付録 D:SMTP サーバーの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7441ba9-a498-42ec-a04d-7f2731407373
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41bc8cc1e86dcf125640ad9997ed4bd8e315d85f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401474"
---
# <a name="appendix-d-create-the-smtp-server"></a><span data-ttu-id="8af73-102">付録 D:SMTP サーバーを作成します。</span><span class="sxs-lookup"><span data-stu-id="8af73-102">Appendix D: Create the SMTP Server</span></span>
<span data-ttu-id="8af73-103">SQL Server データベース メールによって使用される SMTP サーバーを作成します。</span><span class="sxs-lookup"><span data-stu-id="8af73-103">Create the SMTP Server used by SQL Server Database Mail.</span></span>  
  
<span data-ttu-id="8af73-104">次の SQL バージョンのいずれかを使用する場合は、BAM 警告を構成するのには、SQL Server Database Mail が必要です。</span><span class="sxs-lookup"><span data-stu-id="8af73-104">SQL Server Database Mail is required to configure BAM Alerts when using any of the following SQL versions:</span></span> 

* [!INCLUDE[sqlserver2016_md](../includes/sqlserver2016-md.md)]
* [!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)]
* [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] 
  
  <span data-ttu-id="8af73-105">SQL Server Database Mail では SMTP サーバーを使用して BAM 警告を送信します。</span><span class="sxs-lookup"><span data-stu-id="8af73-105">SQL Server Database Mail uses an SMTP Server to send BAM Alerts.</span></span> <span data-ttu-id="8af73-106">SMTP サーバーがインターネット インフォメーション サービス (IIS) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="8af73-106">SMTP Server is included with Internet Information Services (IIS).</span></span> <span data-ttu-id="8af73-107">SMTP インストールできますローカル BizTalk サーバーまたは別のサーバーに iis をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8af73-107">SMTP can be installed locally on the BizTalk Server or on another server with IIS installed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8af73-108">通常、Windows 10、Windows 7 などのクライアント オペレーティング システムでは、SMTP サーバーの機能は含まれません。</span><span class="sxs-lookup"><span data-stu-id="8af73-108">Typically, client operating systems like Windows 10, Windows 7, and so on, do not include SMTP Server capabilities.</span></span> <span data-ttu-id="8af73-109">使用して、Windows Server 上の既存の SMTP サーバーに接続することができます、 *SMTP 電子メール*IIS 内で機能します。</span><span class="sxs-lookup"><span data-stu-id="8af73-109">You can connect to an existing SMTP Server on a Windows Server using the *SMTP E-mail* feature within IIS.</span></span> <span data-ttu-id="8af73-110">*SMTP 電子メール*機能は、SQL Server Database Mail を必要とされる SMTP サーバーではありません。</span><span class="sxs-lookup"><span data-stu-id="8af73-110">The *SMTP E-mail* feature is NOT an SMTP Server, which is required for SQL Server Database Mail.</span></span> <span data-ttu-id="8af73-111">その結果、このトピックでは、インストールして、クライアント オペレーティング システムで SMTP サーバーを構成する手順は含まれません。</span><span class="sxs-lookup"><span data-stu-id="8af73-111">As a result, this topic does not include the steps to install and configure an SMTP Server on client operating systems.</span></span>  

## <a name="install-and-configure-the-smtp-server"></a><span data-ttu-id="8af73-112">SMTP サーバー インストールし、構成</span><span class="sxs-lookup"><span data-stu-id="8af73-112">Install and configure the SMTP server</span></span>  
  
<span data-ttu-id="8af73-113">次の手順が適用されます。</span><span class="sxs-lookup"><span data-stu-id="8af73-113">These steps apply to:</span></span>

* <span data-ttu-id="8af73-114">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="8af73-114">Windows Server 2016</span></span>
* <span data-ttu-id="8af73-115">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="8af73-115">Windows Server 2012 R2</span></span>
* <span data-ttu-id="8af73-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="8af73-116">Windows Server 2012</span></span>
  
### <a name="install-smtp-server"></a><span data-ttu-id="8af73-117">SMTP サーバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8af73-117">Install SMTP Server</span></span>  
   
1.  <span data-ttu-id="8af73-118">**サーバー マネージャー**、**ダッシュ ボード**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="8af73-118">In **Server Manager**, select **Dashboard** in the left pane.</span></span>  
  
3.  <span data-ttu-id="8af73-119">選択**役割と機能の追加**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-119">Select **Add roles and features**.</span></span> <span data-ttu-id="8af73-120">**役割と機能の追加**から開くこともできます、**管理**右上隅のメニュー。</span><span class="sxs-lookup"><span data-stu-id="8af73-120">**Add Roles and Features** can also be opened from the **Manage** menu in the top right-hand corner.</span></span>  
  
4.  <span data-ttu-id="8af73-121">**開始する前に**、**次**。</span><span class="sxs-lookup"><span data-stu-id="8af73-121">In **Before You Begin**, select **Next**.</span></span>  
  
5.  <span data-ttu-id="8af73-122">選択**役割ベースまたは機能ベースのインストール**を選択し、**次**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-122">Select **Role-based or feature-based installation**, and select **Next**.</span></span>  
  
6.  <span data-ttu-id="8af73-123">選択**サーバー プールからサーバーを選択**、目的のサーバーを選択し、**次**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-123">Select **Select a server from the server pool**, select the desired server, and select **Next**.</span></span> <span data-ttu-id="8af73-124">**サーバーの選択**ウィンドウを使用して追加されているサーバーを一覧表示**サーバーの追加**で**サーバー マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-124">The **Server Selection** window lists the servers that have been added using **Add Server** in **Server Manager**.</span></span> <span data-ttu-id="8af73-125">既定では、ローカル サーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8af73-125">By default, it selects the local server.</span></span>  
  
7.  <span data-ttu-id="8af73-126">**サーバーの役割**を選択します**次**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-126">In **Server Roles**, select **Next**.</span></span>  
  
8.  <span data-ttu-id="8af73-127">**機能**、確認**SMTP サーバー**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-127">In **Features**, check **SMTP Server**.</span></span> <span data-ttu-id="8af73-128">選択を求められたら、**機能の追加**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-128">If prompted, select **Add Features**.</span></span> <span data-ttu-id="8af73-129">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8af73-129">Select **Next**.</span></span>  
  
9. <span data-ttu-id="8af73-130">**確認**を選択します**必要な場合に、移行先サーバーを自動的に再起動**、選択および**インストール**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-130">In **Confirmation**, select **Restart the destination server automatically if required**, and select **Install**.</span></span> <span data-ttu-id="8af73-131">完了すると、選択**閉じる**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-131">When complete, select **Close**.</span></span>  

### <a name="configure-the-smtp-server"></a><span data-ttu-id="8af73-132">SMTP サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="8af73-132">Configure the SMTP Server</span></span>  
 <span data-ttu-id="8af73-133">次の手順では、IIS 6.0 マネージャーを使用して、SMTP 仮想サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="8af73-133">The following steps configure the SMTP Virtual Server using the IIS 6.0 Manager:</span></span>  
  
1.  <span data-ttu-id="8af73-134">IIS マネージャーを開きます。スタートでは、検索**inetmgr6.exe**、し、開きます。</span><span class="sxs-lookup"><span data-stu-id="8af73-134">Open the IIS Manager: In Start, search for **inetmgr6.exe**, and open it.</span></span>  
  
2.  <span data-ttu-id="8af73-135">コンピューター名を展開します。</span><span class="sxs-lookup"><span data-stu-id="8af73-135">Expand the computer name.</span></span> <span data-ttu-id="8af73-136">右クリックして **[SMTP Virtual Server #1]**、選択と**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-136">Right-click **[SMTP Virtual Server #1]**, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="8af73-137">**アクセス**] タブで、[、**リレー**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8af73-137">In the **Access** tab, select the **Relay** button.</span></span>  
  
4.  <span data-ttu-id="8af73-138">選択**追加**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-138">Select **Add**.</span></span> <span data-ttu-id="8af73-139">**1 台のコンピューター**、入力`127.0.0.1`を選択し、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="8af73-139">For **Single Computer**, enter `127.0.0.1`, and select **OK**.</span></span>  
  
     <span data-ttu-id="8af73-140">127.0.0.1 を追加すると、この SMTP サーバーからメッセージを送信するローカル サーバーが許可されていること。</span><span class="sxs-lookup"><span data-stu-id="8af73-140">By adding 127.0.0.1, we are allowing the local server to send messages from this SMTP Server.</span></span> <span data-ttu-id="8af73-141">この SMTP サーバーからメッセージを送信する追加のコンピューターを設定する場合は、その IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="8af73-141">If you want additional computers to send messages from this SMTP server, enter their IP addresses.</span></span>  
  
5.  <span data-ttu-id="8af73-142">**配信**] タブで [**送信セキュリティ**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-142">In the **Delivery** tab, select **Outbound Security**.</span></span> <span data-ttu-id="8af73-143">次の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="8af73-143">Choose from the following:</span></span>  
  
     <span data-ttu-id="8af73-144">**匿名アクセス**:アカウント名やパスワードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="8af73-144">**Anonymous access**: An account name or password is not required.</span></span> <span data-ttu-id="8af73-145">このオプションは、SMTP サーバーの認証を無効にします。</span><span class="sxs-lookup"><span data-stu-id="8af73-145">This option disables authentication for the SMTP Server.</span></span>  
  
     <span data-ttu-id="8af73-146">**基本認証**:アカウント名とパスワードはクリア テキストとして送信に接続しているサーバーの。</span><span class="sxs-lookup"><span data-stu-id="8af73-146">**Basic authentication**: The account name and password of the server that you are connecting to are sent as clear text.</span></span> <span data-ttu-id="8af73-147">入力したこのアカウントからメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="8af73-147">This account you enter transmits the e-mails.</span></span> <span data-ttu-id="8af73-148">個人アカウントや Exchange アカウントに電子メールを送信するときに、基本認証を選択できます。</span><span class="sxs-lookup"><span data-stu-id="8af73-148">Basic Authentication can be selected when sending e-mail to a personal account or an Exchange account.</span></span> <span data-ttu-id="8af73-149">有効にするため、資格情報はクリア テキストで渡されるをお勧め**TLS 暗号化**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-149">Because the credentials are passed in clear text, it is recommended to enable **TLS encryption**.</span></span>  
  
     <span data-ttu-id="8af73-150">**統合 Windows 認証**:Windows ドメイン アカウント名とパスワードは、認証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8af73-150">**Integrated Windows Authentication**: The Windows domain account name and password are used to authenticate.</span></span> <span data-ttu-id="8af73-151">入力したアカウントからメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="8af73-151">The account you enter transmits the e-mails.</span></span>  
  
     <span data-ttu-id="8af73-152">**TLS 暗号化**:同様に、SSL、TLS には、接続がセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="8af73-152">**TLS encryption**: Similar to SSL, TLS secures the connection.</span></span> <span data-ttu-id="8af73-153">有効なの SSL サーバー証明書がこのサーバーにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8af73-153">Requires a valid SSL server certificate installed on this server.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="8af73-154">Exchange アカウントを含む、個人用の電子メール アカウントを使用して SMTP のコア機能をテストする次のように選択します。**への匿名アクセス**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-154">To test core SMTP functionality with a personal e-mail account, including an Exchange account, select **Anonymous access**.</span></span> <span data-ttu-id="8af73-155">基本認証を選択すると、SMTP は AUTH コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8af73-155">When Basic authentication is selected, SMTP uses the AUTH command.</span></span> <span data-ttu-id="8af73-156">一部の電子メール プロバイダーにより AUTH コマンドが失敗します。</span><span class="sxs-lookup"><span data-stu-id="8af73-156">Some e-mail providers may fail because of the AUTH command.</span></span> <span data-ttu-id="8af73-157">AUTH コマンドが失敗した場合、エラーは、SMTP サーバー上の Windows イベント ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="8af73-157">If the AUTH command fails, an error may be logged in the Windows event logs on the SMTP Server.</span></span>  
  
6.  <span data-ttu-id="8af73-158">**配信**] タブで [**送信接続**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-158">In the **Delivery** tab, select **Outbound connections**.</span></span> <span data-ttu-id="8af73-159">既定では、TCP ポートは 25 です。</span><span class="sxs-lookup"><span data-stu-id="8af73-159">By default, the TCP Port is 25.</span></span> <span data-ttu-id="8af73-160">ファイアウォール内で開いている場合、別のポートを入力できます。</span><span class="sxs-lookup"><span data-stu-id="8af73-160">A different port can be entered if it is open within your firewall.</span></span> <span data-ttu-id="8af73-161">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8af73-161">Select **OK**.</span></span>  
  
7.  <span data-ttu-id="8af73-162">**配信**] タブで [**詳細**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-162">In the **Delivery** tab, select **Advanced**.</span></span> <span data-ttu-id="8af73-163">既定で、**完全修飾ドメイン名**ローカル サーバーの一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8af73-163">By default, the **Fully Qualified Domain Name** of the local server is listed.</span></span> <span data-ttu-id="8af73-164">インターネット プロバイダーによって、**スマート ホスト**プロパティを空にできます。</span><span class="sxs-lookup"><span data-stu-id="8af73-164">Depending on the internet provider, the **Smart Host** property can remain empty.</span></span> <span data-ttu-id="8af73-165">スマート ホストが必要なことを確認するインターネット プロバイダーに連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8af73-165">You may need to contact the internet provider to confirm if a Smart Host is required.</span></span> <span data-ttu-id="8af73-166">それ以外の場合、smtp を入力することができます。*EMailProvider*。 com です。</span><span class="sxs-lookup"><span data-stu-id="8af73-166">Otherwise, you may be able to enter smtp.*EMailProvider*.com.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8af73-167">A**スマート ホスト**、リレー ホストでは、すべての送信メッセージをルーティングする、Exchange Server で使用する専用サーバーとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="8af73-167">A **Smart Host**, also known as a relay host, is a dedicated server used by an Exchange Server to route all outgoing messages.</span></span> <span data-ttu-id="8af73-168">**スマートホスト**がメッセージを受信すると、**スマートホスト**はメッセージをリモートドメインに転送します。</span><span class="sxs-lookup"><span data-stu-id="8af73-168">When the **Smart Host** receives the messages, the **Smart Host** forwards the messages to a remote domain.</span></span> <span data-ttu-id="8af73-169">目標、**スマート ホスト**Exchange Server のパフォーマンスを向上させることです。</span><span class="sxs-lookup"><span data-stu-id="8af73-169">The goal of a **Smart Host** is to improve performance of an Exchange Server.</span></span> <span data-ttu-id="8af73-170">スマート ホストにのみ、Exchange サーバーが送信されます。接続が確立されるまでは、繰り返しではなく、リモート ドメインお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="8af73-170">The Exchange Server only transmits to the smart host; instead of repeatedly contacting the remote domain until a connection is made.</span></span>  
  
8.  <span data-ttu-id="8af73-171">選択**OK**をすべてのウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="8af73-171">Select **OK** to close all windows.</span></span>  
  
9. <span data-ttu-id="8af73-172">SMTP サーバーを再起動します。右クリック **[SMTP Virtual Server #1]** を選択します**停止**、し、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-172">Restart the SMTP Server: Right-click **[SMTP Virtual Server #1]**, select **Stop**, and then select **Start**.</span></span> <span data-ttu-id="8af73-173">SMTP サーバー設定を適用するには、再起動が必要です。</span><span class="sxs-lookup"><span data-stu-id="8af73-173">A restart is needed to apply the SMTP Server settings.</span></span> 

  
## <a name="windows-server-2008-r2-install-and-configure-smtp-server"></a><span data-ttu-id="8af73-174">Windows Server 2008 R2:SMTP サーバー インストールし、構成</span><span class="sxs-lookup"><span data-stu-id="8af73-174">Windows Server 2008 R2: Install and Configure SMTP Server</span></span>  
  
### <a name="install-smtp-server"></a><span data-ttu-id="8af73-175">SMTP サーバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8af73-175">Install SMTP Server</span></span>  
 <span data-ttu-id="8af73-176">次の手順では、SMTP サーバーの機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8af73-176">The following steps install the SMTP Server feature:</span></span>  
  
1.  <span data-ttu-id="8af73-177">**サーバー マネージャー**を選択します**機能**、選び**機能の追加**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-177">In **Server Manager**, select **Features**, and select **Add Features**.</span></span>  
  
3.  <span data-ttu-id="8af73-178">**機能の追加**、 **SMTP サーバー**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-178">In **Add Features**, select **SMTP Server**.</span></span> <span data-ttu-id="8af73-179">選択を求められたら、**必要な役割サービスの追加**を選択し、**次**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-179">If prompted, select **Add Required Role Services**, and select **Next**.</span></span>  
  
4.  <span data-ttu-id="8af73-180">選択して、インストールを続行**次**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-180">Continue with the installation by selecting **Next**.</span></span>  
  
5.  <span data-ttu-id="8af73-181">**インストール オプションの確認**ウィンドウで、**インストール**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-181">In the **Confirm Installation Selections** window, select **Install**.</span></span> <span data-ttu-id="8af73-182">完了すると、選択**閉じる**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-182">When complete, select **Close**.</span></span>  
  
### <a name="configure-the-smtp-server"></a><span data-ttu-id="8af73-183">SMTP サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="8af73-183">Configure the SMTP Server</span></span>  
 <span data-ttu-id="8af73-184">次の手順では、IIS 6.0 マネージャーを使用して、SMTP 仮想サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="8af73-184">The following steps configure the SMTP Virtual Server using the IIS 6.0 Manager:</span></span>  
  
1.  <span data-ttu-id="8af73-185">開く、IIS 6.0 マネージャー。**開始**、検索**IIS**、選択および**インターネット インフォメーション サービス (IIS) 6.0 マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-185">Open the IIS 6.0 Manager: In **Start**, search for **IIS**, and select **Internet Information Services (IIS) 6.0 Manager**.</span></span>  
  
2.  <span data-ttu-id="8af73-186">コンピューター名を展開します。</span><span class="sxs-lookup"><span data-stu-id="8af73-186">Expand the computer name.</span></span> <span data-ttu-id="8af73-187">右クリックして **[SMTP Virtual Server #1]**、選択と**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-187">Right-click **[SMTP Virtual Server #1]**, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="8af73-188">**アクセス**] タブで、[、**リレー**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8af73-188">In the **Access** tab, select the **Relay** button.</span></span>  
  
4.  <span data-ttu-id="8af73-189">選択**追加**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-189">Select **Add**.</span></span> <span data-ttu-id="8af73-190">**1 台のコンピューター**、入力`127.0.0.1`を選択し、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="8af73-190">For **Single Computer**, enter `127.0.0.1`, and select **OK**.</span></span>  
  
     <span data-ttu-id="8af73-191">127.0.0.1 を追加すると、この SMTP サーバーからメッセージを送信するローカル サーバーが許可されていること。</span><span class="sxs-lookup"><span data-stu-id="8af73-191">By adding 127.0.0.1, we are allowing the local server to send messages from this SMTP Server.</span></span> <span data-ttu-id="8af73-192">この SMTP サーバーからメッセージを送信する追加のコンピューターを設定する場合は、その IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="8af73-192">If you want additional computers to send messages from this SMTP server, enter their IP addresses.</span></span>  
  
5.  <span data-ttu-id="8af73-193">**配信**] タブで [**送信セキュリティ**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-193">In the **Delivery** tab, select **Outbound Security**.</span></span> <span data-ttu-id="8af73-194">次の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="8af73-194">Choose from the following:</span></span>  
  
     <span data-ttu-id="8af73-195">**匿名アクセス**:アカウント名やパスワードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="8af73-195">**Anonymous access**: An account name or password is not required.</span></span> <span data-ttu-id="8af73-196">このオプションは、SMTP サーバーの認証を無効にします。</span><span class="sxs-lookup"><span data-stu-id="8af73-196">This option disables authentication for the SMTP Server.</span></span>  
  
     <span data-ttu-id="8af73-197">**基本認証**:アカウント名とパスワードはクリア テキストとして送信に接続しているサーバーの。</span><span class="sxs-lookup"><span data-stu-id="8af73-197">**Basic authentication**: The account name and password of the server that you are connecting to are sent as clear text.</span></span> <span data-ttu-id="8af73-198">個人アカウントや Exchange アカウントに電子メールを送信するときに、基本認証を選択できます。</span><span class="sxs-lookup"><span data-stu-id="8af73-198">Basic Authentication can be selected when sending e-mail to a personal account or an Exchange account.</span></span> <span data-ttu-id="8af73-199">有効にするため、資格情報はクリア テキストで渡されるをお勧め**TLS 暗号化**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-199">Because the credentials are passed in clear text, it is recommended to enable **TLS encryption**.</span></span>  
  
     <span data-ttu-id="8af73-200">**統合 Windows 認証**:Windows ドメイン アカウント名とパスワードは、認証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8af73-200">**Integrated Windows Authentication**: The Windows domain account name and password are used to authenticate.</span></span> <span data-ttu-id="8af73-201">入力したアカウントからメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="8af73-201">The account you enter transmits the e-mails.</span></span>  
  
     <span data-ttu-id="8af73-202">**TLS 暗号化**:同様に、SSL、TLS には、接続がセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="8af73-202">**TLS encryption**: Similar to SSL, TLS secures the connection.</span></span> <span data-ttu-id="8af73-203">有効なの SSL サーバー証明書がこのサーバーにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8af73-203">Requires a valid SSL server certificate installed on this server.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="8af73-204">Exchange アカウントを含む、個人用の電子メール アカウントを使用して SMTP のコア機能をテストする次のように選択します。**への匿名アクセス**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-204">To test core SMTP functionality with a personal e-mail account, including an Exchange account, select **Anonymous access**.</span></span> <span data-ttu-id="8af73-205">基本認証を選択すると、SMTP は AUTH コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8af73-205">When Basic authentication is selected, SMTP uses the AUTH command.</span></span> <span data-ttu-id="8af73-206">一部の電子メール プロバイダーにより AUTH コマンドが失敗します。</span><span class="sxs-lookup"><span data-stu-id="8af73-206">Some e-mail providers may fail because of the AUTH command.</span></span> <span data-ttu-id="8af73-207">AUTH コマンドが失敗した場合、エラーは、SMTP サーバー上の Windows イベント ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="8af73-207">If the AUTH command fails, an error may be logged in the Windows event logs on the SMTP Server.</span></span>  
  
6.  <span data-ttu-id="8af73-208">**配信**] タブで [**送信接続**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-208">In the **Delivery** tab, select **Outbound connections**.</span></span> <span data-ttu-id="8af73-209">既定では、TCP ポートは 25 です。</span><span class="sxs-lookup"><span data-stu-id="8af73-209">By default, the TCP Port is 25.</span></span> <span data-ttu-id="8af73-210">ファイアウォール内で開いている場合、別のポートを入力できます。</span><span class="sxs-lookup"><span data-stu-id="8af73-210">A different port can be entered if it is open within your firewall.</span></span> <span data-ttu-id="8af73-211">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8af73-211">Select **OK**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="8af73-212">TCP ポートは受信接続と送信接続に使用できます。</span><span class="sxs-lookup"><span data-stu-id="8af73-212">The TCP Port can be used for Inbound connections and Outbound connections.</span></span>  
  
7.  <span data-ttu-id="8af73-213">**配信**] タブで [**詳細**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-213">In the **Delivery** tab, select **Advanced**.</span></span> <span data-ttu-id="8af73-214">既定で、**完全修飾ドメイン名**ローカル サーバーの一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8af73-214">By default, the **Fully Qualified Domain Name** of the local server is listed.</span></span> <span data-ttu-id="8af73-215">インターネット プロバイダーによって、**スマート ホスト**プロパティを空にできます。</span><span class="sxs-lookup"><span data-stu-id="8af73-215">Depending on the internet provider, the **Smart Host** property can remain empty.</span></span> <span data-ttu-id="8af73-216">スマート ホストが必要なことを確認するインターネット プロバイダーに連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8af73-216">You may need to contact the internet provider to confirm if a Smart Host is required.</span></span> <span data-ttu-id="8af73-217">それ以外の場合、smtp を入力することができます。*EMailProvider*。 com です。</span><span class="sxs-lookup"><span data-stu-id="8af73-217">Otherwise, you may be able to enter smtp.*EMailProvider*.com.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8af73-218">A**スマート ホスト**、リレー ホストでは、すべての送信メッセージをルーティングする、Exchange Server で使用する専用サーバーとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="8af73-218">A **Smart Host**, also known as a relay host, is a dedicated server used by an Exchange Server to route all outgoing messages.</span></span> <span data-ttu-id="8af73-219">**スマートホスト**がメッセージを受信すると、**スマートホスト**はメッセージをリモートドメインに転送します。</span><span class="sxs-lookup"><span data-stu-id="8af73-219">When the **Smart Host** receives the messages, the **Smart Host** forwards the messages to a remote domain.</span></span> <span data-ttu-id="8af73-220">目標、**スマート ホスト**Exchange Server のパフォーマンスを向上させることです。</span><span class="sxs-lookup"><span data-stu-id="8af73-220">The goal of a **Smart Host** is to improve performance of an Exchange Server.</span></span> <span data-ttu-id="8af73-221">スマート ホストにのみ、Exchange サーバーが送信されます。接続が確立されるまでは、繰り返しではなく、リモート ドメインお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="8af73-221">The Exchange Server only transmits to the smart host; instead of repeatedly contacting the remote domain until a connection is made.</span></span>  
  
8.  <span data-ttu-id="8af73-222">選択**OK**をすべてのウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="8af73-222">Select **OK** to close all windows.</span></span>  
  
9. <span data-ttu-id="8af73-223">SMTP サーバー設定を適用するには、再起動が必要です。</span><span class="sxs-lookup"><span data-stu-id="8af73-223">A restart is needed to apply the SMTP Server settings.</span></span> <span data-ttu-id="8af73-224">SMTP サーバーを再起動するには。右クリック **[SMTP Virtual Server #1]** を選択します**停止**、し、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="8af73-224">To restart the SMTP Server: Right-click **[SMTP Virtual Server #1]**, select **Stop**, and then select **Start**.</span></span>  
  
  
## <a name="test-the-smtp-server"></a><span data-ttu-id="8af73-225">SMTP サーバーをテストします。</span><span class="sxs-lookup"><span data-stu-id="8af73-225">Test the SMTP Server</span></span>  
 <span data-ttu-id="8af73-226">Telnet を使用して、SMTP サーバーの構成をテストできます。</span><span class="sxs-lookup"><span data-stu-id="8af73-226">Telnet can be used to test the SMTP Server configuration.</span></span> <span data-ttu-id="8af73-227">次の手順では、電子メール アドレスに構成されている SMTP サーバーを使用してメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="8af73-227">The following steps send a message using your configured SMTP Server to an e-mail address.</span></span> <span data-ttu-id="8af73-228">[http://support.microsoft.com/kb/153119](http://support.microsoft.com/kb/153119) telnet コマンドの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="8af73-228">[http://support.microsoft.com/kb/153119](http://support.microsoft.com/kb/153119) provides descriptions of the telnet commands.</span></span>  
  
1. <span data-ttu-id="8af73-229">管理者としてコマンド ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="8af73-229">Open a command window as Administrator.</span></span>
  
2. <span data-ttu-id="8af73-230">コマンド プロンプトで、次のように入力します:</span><span class="sxs-lookup"><span data-stu-id="8af73-230">In the command prompt, type:</span></span>  
  
    `telnet localhost 25`  
  
    <span data-ttu-id="8af73-231">Telnet がインストールされていない場合は、」と入力してインストールします。</span><span class="sxs-lookup"><span data-stu-id="8af73-231">If telnet is not installed, install it by typing:</span></span>  
  
    `pkgmgr /iu:"TelnetClient"`  
  
3. <span data-ttu-id="8af73-232">」と入力して、通信を開始します。</span><span class="sxs-lookup"><span data-stu-id="8af73-232">Start communication by typing:</span></span>  
  
    `EHLO server`  
  
4. <span data-ttu-id="8af73-233">メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="8af73-233">Enter the Mail From address:</span></span>  
  
    `MAIL FROM: *YourEmailAddress*@*YourProvider*.com`  
  
    <span data-ttu-id="8af73-234">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8af73-234">For example, enter:</span></span>  
  
    `MAIL FROM: EmailAddress@outlook.com`  
  
5. <span data-ttu-id="8af73-235">メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="8af73-235">Enter the Mail To address:</span></span>  
  
    `RCPT TO: *YourEmailAddress*@*YourProvider*.com`  
  
    <span data-ttu-id="8af73-236">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8af73-236">For example, enter:</span></span>  
  
    `RCPT TO: EmailAddress@outlook.com`  
  
6. <span data-ttu-id="8af73-237">」と入力してデータを送信する準備が完了したら、SMTP サーバーに指示します。</span><span class="sxs-lookup"><span data-stu-id="8af73-237">Tell the SMTP Server you are ready to send data by typing:</span></span>  
  
    `DATA`  
  
7. <span data-ttu-id="8af73-238">」と入力して件名を入力します。</span><span class="sxs-lookup"><span data-stu-id="8af73-238">Enter the Subject by typing:</span></span>  
  
    `Subject: Test Message`  
  
8. <span data-ttu-id="8af73-239">Enter をキーを 2 回押します。</span><span class="sxs-lookup"><span data-stu-id="8af73-239">Hit Enter twice.</span></span>  
  
9. <span data-ttu-id="8af73-240">」と入力して、メッセージ本文を入力します。</span><span class="sxs-lookup"><span data-stu-id="8af73-240">Enter the message body by typing:</span></span>  
  
     `This is the message body of the test message.`  
  
10. <span data-ttu-id="8af73-241">Enter キーを押します、ピリオド (.) を入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8af73-241">Hit Enter, type a period (.), and hit Enter.</span></span>  
  
    <span data-ttu-id="8af73-242">電子メール メッセージの RCPT TO アドレスを確認します。</span><span class="sxs-lookup"><span data-stu-id="8af73-242">Check the RCPT TO address for the e-mail message.</span></span> <span data-ttu-id="8af73-243">電子メールの配信 (フォルダーを確認して受信トレイと迷惑メール)、メッセージがない場合は正常に送信されませんし、SMTP Queue フォルダー (C:\inetpub\mailroot\Queue) に存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8af73-243">If the e-mail is not delivered (Check your Inbox and Spam folder), then the message was not successfully sent, and may reside in the SMTP Queue folder (C:\inetpub\mailroot\Queue).</span></span>  
  