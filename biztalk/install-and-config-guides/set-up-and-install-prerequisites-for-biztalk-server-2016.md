---
title: 設定し、BizTalk Server 2016 の前提条件のインストール |Microsoft ドキュメント
description: インストールして、必要なソフトウェアと BizTalk Server 2016 用の設定を構成する手順
author: MandiOhlinger
manager: anneta
ms.prod: biztalk-server
ms.custom: ''
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa70b621-903a-4cfa-9cb0-c6a82ed8f733
caps.latest.revision: 11
ms.author: mandia
ms.openlocfilehash: 666cddaab4d23fa69b0ae488f665e2eda5182c05
ms.sourcegitcommit: 770523695b34cc54db81f7ab7eba46f2bc19baec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
ms.locfileid: "31816966"
---
# <a name="set-up-and-install-prerequisites-for-biztalk-server-2016"></a><span data-ttu-id="aa791-103">BizTalk Server 2016 のセットアップとインストールの前提条件</span><span class="sxs-lookup"><span data-stu-id="aa791-103">Set up and install prerequisites for BizTalk Server 2016</span></span>
<span data-ttu-id="aa791-104">サーバーのセットアップとソフトウェアのインストール/構成の前提条件。</span><span class="sxs-lookup"><span data-stu-id="aa791-104">Set up the server, and install and configure the software prerequisites.</span></span>

## <a name="join-the-administrators-group"></a><span data-ttu-id="aa791-105">管理者グループに参加します。</span><span class="sxs-lookup"><span data-stu-id="aa791-105">Join the Administrators Group</span></span>
<span data-ttu-id="aa791-106">BizTalk Server をインストールして構成するには、ローカル コンピューターで管理者アカウントを利用してサーバーにサインインします。</span><span class="sxs-lookup"><span data-stu-id="aa791-106">To install and configure BizTalk Server, sign in to the server using an administrator account on the local computer.</span></span> <span data-ttu-id="aa791-107">BizTalk Server を管理しているユーザー アカウントがあれば、それをローカル Administrators グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="aa791-107">Add any user accounts that are administering the BizTalk Server to the local Administrators group:</span></span>

1.  <span data-ttu-id="aa791-108">[スタート] メニューで **[コンピューターの管理]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="aa791-108">In the Start menu, open **Computer Management**.</span></span>

    * <span data-ttu-id="aa791-109">あるいは、**[管理ツール]** を開き、**[コンピューターの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-109">Or, open **Administrative Tools**, and then select **Computer Management**.</span></span>
    * <span data-ttu-id="aa791-110">あるいは、**[サーバー マネージャー]** を開き、**[ツール]** を選択し、**[コンピューターの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-110">Or, open **Server Manager**, select **Tools**, and then select **Computer Management**.</span></span>
  
2.  <span data-ttu-id="aa791-111">**[ローカル ユーザーとグループ]** を展開し、**[グループ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-111">Expand **Local Users and Groups**, and select **Groups**.</span></span>
3.  <span data-ttu-id="aa791-112">**[監理者]** グループを右クリックし、**[グループに追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-112">Right-click the **Administrators** group, and select **Add to Group**.</span></span> <span data-ttu-id="aa791-113">アカウントを**追加**し、**[OK]** を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="aa791-113">**Add** your accounts, and select **OK** to save your changes.</span></span> 

## <a name="change-the-computer-name-optional"></a><span data-ttu-id="aa791-114">(省略可能) コンピューター名を変更します。</span><span class="sxs-lookup"><span data-stu-id="aa791-114">Change the computer name (optional)</span></span>
<span data-ttu-id="aa791-115">コンピューター名が 15 文字より長い場合は、BizTalk Server の構成は失敗します。</span><span class="sxs-lookup"><span data-stu-id="aa791-115">If your computer name is longer than 15 characters, then BizTalk Server configuration fails.</span></span> <span data-ttu-id="aa791-116">コンピューター名を 15 文字未満に変更します。</span><span class="sxs-lookup"><span data-stu-id="aa791-116">To change the computer name to less than 15 characters:</span></span>

1.  <span data-ttu-id="aa791-117">**[サーバー マネージャー]** > **[ダッシュボード]** で **[ローカル サーバー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-117">In **Server Manager** > **Dashboard**, select **Local Server**.</span></span> 
2.  <span data-ttu-id="aa791-118">**[プロパティ]** で、コンピューターの名前プロパティを選択し、変更します。</span><span class="sxs-lookup"><span data-stu-id="aa791-118">In **Properties**, select the Computer name property to change it.</span></span>
3. <span data-ttu-id="aa791-119">コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="aa791-119">Restart the computer.</span></span> 

<span data-ttu-id="aa791-120">**関連項目**: Windows PowerShell [Rename-Computer](https://technet.microsoft.com/library/hh849792.aspx)</span><span class="sxs-lookup"><span data-stu-id="aa791-120">**SEE ALSO** : Windows PowerShell [Rename-Computer](https://technet.microsoft.com/library/hh849792.aspx)</span></span>

## <a name="enable-network-dtc-access"></a><span data-ttu-id="aa791-121">ネットワーク DTC アクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="aa791-121">Enable Network DTC Access</span></span>
<span data-ttu-id="aa791-122">BizTalk と SQL Server が別々のコンピューターにインストールされている場合、BizTalk Server と SQL Server でネットワーク DTC アクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="aa791-122">If BizTalk and SQL Server are installed on separate computers, then enable Network DTC Access on the BizTalk Server and the SQL Server.</span></span> 

1. <span data-ttu-id="aa791-123">[スタート] メニューで、"dcomcnfg" を開きます。</span><span class="sxs-lookup"><span data-stu-id="aa791-123">In the Start menu, open "dcomcnfg".</span></span>

    * <span data-ttu-id="aa791-124">あるいは、**[管理ツール]** を開き、**[コンポーネント サービス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-124">Or, open **Administrative Tools**, and then select **Component Services**.</span></span>
    * <span data-ttu-id="aa791-125">あるいは、**[サーバー マネージャー]** を開き、**[ツール]** を選択し、**[コンポーネント サービス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-125">Or, open **Server Manager**, select **Tools**, and then select **Component Services**.</span></span>
  
2. <span data-ttu-id="aa791-126">**[コンポーネント サービス]**、**[コンピューター]**、**[マイ コンピューター]**、**[分散トランザクション コーディネーター]** の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="aa791-126">Expand **Component Services**, expand **Computers**, expand **My Computer**,  and expand **Distributed Transaction Coordinator**.</span></span>
3. <span data-ttu-id="aa791-127">**[ローカル DTC]** を右クリックし、**[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-127">Right-click **Local DTC**, and select **Properties**.</span></span>
4. <span data-ttu-id="aa791-128">**[セキュリティ]** タブに移動し、次の項目を確認します。</span><span class="sxs-lookup"><span data-stu-id="aa791-128">Go to the **Security** tab, and check the following:</span></span>  
    * <span data-ttu-id="aa791-129">ネットワーク DTC アクセス</span><span class="sxs-lookup"><span data-stu-id="aa791-129">Network DTC Access</span></span>
    * <span data-ttu-id="aa791-130">受信を許可する</span><span class="sxs-lookup"><span data-stu-id="aa791-130">Allow Inbound</span></span>
    * <span data-ttu-id="aa791-131">送信を許可する</span><span class="sxs-lookup"><span data-stu-id="aa791-131">Allow Outbound</span></span>
    * <span data-ttu-id="aa791-132">認証を必要としない</span><span class="sxs-lookup"><span data-stu-id="aa791-132">No Authentication Required</span></span>
5. <span data-ttu-id="aa791-133">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-133">Select **OK**.</span></span> <span data-ttu-id="aa791-134">MS DTC を再起動するメッセージが表示されたら、選択**はい**です。</span><span class="sxs-lookup"><span data-stu-id="aa791-134">If prompted to restart MS DTC, select **Yes**.</span></span> 

<span data-ttu-id="aa791-135">追加の設定が必要な場合、「[MSDTC を使用した問題のトラブルシューティング](../core/troubleshooting-problems-with-msdtc.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa791-135">For additional settings that may be needed, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>

## <a name="configure-application-event-log-optional"></a><span data-ttu-id="aa791-136">(省略可能) アプリケーション イベント ログを構成します。</span><span class="sxs-lookup"><span data-stu-id="aa791-136">Configure Application Event Log (optional)</span></span>

<span data-ttu-id="aa791-137">BizTalk Server のセットアップを実行すると、イベントの記録がアプリケーション イベント ログに保存されます。</span><span class="sxs-lookup"><span data-stu-id="aa791-137">BizTalk Server setup keeps a record of events in the Application Event Log.</span></span> <span data-ttu-id="aa791-138">インストールされる BizTalk Server の機能によっては、ログの空き領域を超える大きさのログが作成されることもあります。</span><span class="sxs-lookup"><span data-stu-id="aa791-138">Depending on the BizTalk Server features installed, the amount of space required in the log may exceed its limit.</span></span> <span data-ttu-id="aa791-139">セットアップ中にアプリケーション イベント ログの領域が不足すると、インストールは失敗します。</span><span class="sxs-lookup"><span data-stu-id="aa791-139">If the application event log runs out of space during the setup, the installation fails.</span></span> <span data-ttu-id="aa791-140">アプリケーション イベント ログの設定を変更すれば、この失敗を回避できます。</span><span class="sxs-lookup"><span data-stu-id="aa791-140">Changing the Application Event Log settings prevents this failure.</span></span>

1. <span data-ttu-id="aa791-141">[スタート] メニューで、**[イベント ビューアー]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="aa791-141">In the Start menu, open **Event Viewer**:</span></span>

    * <span data-ttu-id="aa791-142">あるいは、**[管理ツール]** を開き、**[イベント ビューアー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-142">Or, open **Administrative Tools**, and then select **Event Viewer**.</span></span>
    * <span data-ttu-id="aa791-143">あるいは、**[サーバー マネージャー]** を開き、**[ツール]** を選択し、**[イベント ビューアー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-143">Or, open **Server Manager**, select **Tools**, and then select **Event Viewer**.</span></span>
  
2. <span data-ttu-id="aa791-144">**[Windows ログ]** を展開し、**[アプリケーション]** を右クリックして **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-144">Expand **Windows Logs**, right-click **Application**, and then select **Properties**.</span></span> 
3. <span data-ttu-id="aa791-145">使用可能な空き領域を確認するには、**[ログ サイズ]** と **[最大ログ サイズ]** のプロパティを比較します。</span><span class="sxs-lookup"><span data-stu-id="aa791-145">To determine the available space, compare the **Log Size** and the **Maximum log size** properties.</span></span> 

    * <span data-ttu-id="aa791-146">空き領域を増やすには、**[最大ログ サイズ]** の数値を増やします。</span><span class="sxs-lookup"><span data-stu-id="aa791-146">To add space, enter a higher number in **Maximum log size**.</span></span>
    * <span data-ttu-id="aa791-147">ログの空き領域がなくなったときに古いイベントが上書きされるようにするには、**[必要に応じてイベントを上書きする]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-147">To enable overwriting of old events when the log becomes full, select **Overwrite events as needed**.</span></span>
    * <span data-ttu-id="aa791-148">ログ イベントを消去するには、**[ログの消去]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-148">To clear the log events, select **Clear log**.</span></span>

4. <span data-ttu-id="aa791-149">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-149">Select **OK**.</span></span>

## <a name="edge-cant-be-opened-optional"></a><span data-ttu-id="aa791-150">エッジは、(省略可能) 開くことができません。</span><span class="sxs-lookup"><span data-stu-id="aa791-150">Edge can’t be opened (optional)</span></span>

<span data-ttu-id="aa791-151">Microsoft Edge の利用時に次のメッセージが表示されます:</span><span class="sxs-lookup"><span data-stu-id="aa791-151">When using Edge, the following message displays:</span></span>  
`Microsoft Edge can't be opened using the Built-in Administrator account. Sign in with a different account and try again.`

<span data-ttu-id="aa791-152">ビルトイン Administrator アカウントで Microsoft Edge を開くには:</span><span class="sxs-lookup"><span data-stu-id="aa791-152">To allow Edge to open using the built-in administrator account:</span></span>

1. <span data-ttu-id="aa791-153">[スタート] メニューで、**[ローカル セキュリティ ポリシー]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="aa791-153">In the Start menu, open **Local Security Policy**.</span></span> <span data-ttu-id="aa791-154">あるいは、**[サーバー マネージャー]** を開き、**[ツール]** を選択し、**[ローカル セキュリティ ポリシー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-154">Or, open **Server Manager**, select **Tools**, and then select **Local Security Policy**.</span></span>
2.  <span data-ttu-id="aa791-155">**[ローカル ポリシー]** を展開し、**[セキュリティ オプション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-155">Expand **Local Policies**, and select **Security Options**.</span></span> 
3.  <span data-ttu-id="aa791-156">**[ユーザー アカウント制御: ビルトイン Administrator アカウントのための管理者承認モード]** ポリシーに移動し、ポリシーを**有効にします**。</span><span class="sxs-lookup"><span data-stu-id="aa791-156">Go to the **User Account Control: Admin Approval Mode for the Built-in Administrator account** policy, and **Enable** the policy.</span></span> 
4. <span data-ttu-id="aa791-157">**[OK]** を選択し、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="aa791-157">Select **OK**, and restart your computer.</span></span>

## <a name="install-windows-updates"></a><span data-ttu-id="aa791-158">Windows の更新プログラムをインストールする</span><span class="sxs-lookup"><span data-stu-id="aa791-158">Install Windows Updates</span></span>

<span data-ttu-id="aa791-159">必ず最新の重要な Windows 更新プログラムをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="aa791-159">Be sure to install the latest critical Windows updates.</span></span> 

1. <span data-ttu-id="aa791-160">[スタート] メニューで、**[Windows の更新プログラム]** を開き、更新がないか確認します。</span><span class="sxs-lookup"><span data-stu-id="aa791-160">On the Start menu, open **Windows Updates**, and check for updates.</span></span> <span data-ttu-id="aa791-161">**[設定]** を開き、**[更新とセキュリティ]** を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="aa791-161">You can also open **Settings**, and select **Update and security**.</span></span>
2. <span data-ttu-id="aa791-162">更新プログラムのインストール後、コンピューターを再起動する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="aa791-162">After installing updates, you may need to restart the computer.</span></span>

## <a name="enable-iis"></a><span data-ttu-id="aa791-163">IIS を有効にします。</span><span class="sxs-lookup"><span data-stu-id="aa791-163">Enable IIS</span></span>
<span data-ttu-id="aa791-164">BizTalk Server の機能のうち、IIS を必要とするものは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aa791-164">BizTalk Server requires IIS for the following features:</span></span>

- <span data-ttu-id="aa791-165">HTTP アダプター</span><span class="sxs-lookup"><span data-stu-id="aa791-165">HTTP adapter</span></span>
- <span data-ttu-id="aa791-166">SOAP アダプター</span><span class="sxs-lookup"><span data-stu-id="aa791-166">SOAP adapter</span></span>
- <span data-ttu-id="aa791-167">Windows SharePoint Services アダプター</span><span class="sxs-lookup"><span data-stu-id="aa791-167">Windows SharePoint Services adapter</span></span>
- <span data-ttu-id="aa791-168">SSL (Secure Sockets Layer) 暗号化</span><span class="sxs-lookup"><span data-stu-id="aa791-168">Secure Sockets Layer (SSL) encryption</span></span>
- <span data-ttu-id="aa791-169">BAM ポータル</span><span class="sxs-lookup"><span data-stu-id="aa791-169">BAM Portal</span></span>
- <span data-ttu-id="aa791-170">EDI</span><span class="sxs-lookup"><span data-stu-id="aa791-170">EDI</span></span>

<span data-ttu-id="aa791-171">IIS は**役割**または**機能**としてオペレーティング システムに付属します。OS によって役割または機能になります。</span><span class="sxs-lookup"><span data-stu-id="aa791-171">IIS is included with the operating system as a **Role** or a **Feature**, depending on the OS.</span></span> <span data-ttu-id="aa791-172">インストール方法:</span><span class="sxs-lookup"><span data-stu-id="aa791-172">To install:</span></span>

1. <span data-ttu-id="aa791-173">[スタート] メニューで、**[Windows の機能の有効化または無効化]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa791-173">In the Start menu, open **Turn Windows Features on or off**.</span></span> <span data-ttu-id="aa791-174">あるいは、**[サーバー マネージャー]** を開き、**[管理]** を選択し、**[役割と機能の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-174">Or, open **Server Manager**, select **Manage**, and then select **Add roles and features**.</span></span>
2. <span data-ttu-id="aa791-175">**[インターネット インフォメーション サービス]** または **[Web サーバー (IIS)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-175">Select **Internet Information Services** or **Web Server (IIS)**.</span></span> <span data-ttu-id="aa791-176">既定でオンになっているオプションのほか、次の項目も選択します:</span><span class="sxs-lookup"><span data-stu-id="aa791-176">In addition to the default checked options, also select the following:</span></span> 

    <span data-ttu-id="aa791-177">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="aa791-177">**Windows 10**</span></span>
    - <span data-ttu-id="aa791-178">**[Web 管理ツール]** で、次の項目もオンにします:</span><span class="sxs-lookup"><span data-stu-id="aa791-178">In **Web Management Tools**, also check:</span></span>  
        - <span data-ttu-id="aa791-179">IIS 6 管理互換</span><span class="sxs-lookup"><span data-stu-id="aa791-179">IIS 6 Management Compatibility</span></span>
        - <span data-ttu-id="aa791-180">IIS 6 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="aa791-180">IIS 6 Management Console</span></span>
        - <span data-ttu-id="aa791-181">IIS 6 スクリプト ツール (adsutil.vbs のインストール)</span><span class="sxs-lookup"><span data-stu-id="aa791-181">IIS 6 Scripting Tools (Installs adsutil.vbs)</span></span>
        - <span data-ttu-id="aa791-182">IIS メタベースおよび IIS 6 構成との互換性</span><span class="sxs-lookup"><span data-stu-id="aa791-182">IIS Metabase and IIS 6 configuration compatibility</span></span>
        - <span data-ttu-id="aa791-183">IIS 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="aa791-183">IIS Management Console</span></span>
    - <span data-ttu-id="aa791-184">**[World Wide Web サービス]** で **[セキュリティ]** を展開し、次の項目もオンにします:</span><span class="sxs-lookup"><span data-stu-id="aa791-184">In **World Wide Web Services**, expand **Security** and also check:</span></span>
        - <span data-ttu-id="aa791-185">基本認証</span><span class="sxs-lookup"><span data-stu-id="aa791-185">Basic Authentication</span></span>
        - <span data-ttu-id="aa791-186">[Windows 認証]</span><span class="sxs-lookup"><span data-stu-id="aa791-186">Windows Authentication</span></span>    

    <span data-ttu-id="aa791-187">**Windows Server**</span><span class="sxs-lookup"><span data-stu-id="aa791-187">**Windows Server**</span></span>
    - <span data-ttu-id="aa791-188">**[セキュリティ]** で、次の項目もオンにします:</span><span class="sxs-lookup"><span data-stu-id="aa791-188">In **Security**, also check:</span></span> 
        - <span data-ttu-id="aa791-189">基本認証</span><span class="sxs-lookup"><span data-stu-id="aa791-189">Basic Authentication</span></span>
        - <span data-ttu-id="aa791-190">[Windows 認証]</span><span class="sxs-lookup"><span data-stu-id="aa791-190">Windows Authentication</span></span>    
    - <span data-ttu-id="aa791-191">**[管理ツール]** で、次の項目もオンにします:</span><span class="sxs-lookup"><span data-stu-id="aa791-191">In **Management Tools**, also check:</span></span>  
        - <span data-ttu-id="aa791-192">IIS 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="aa791-192">IIS Management Console</span></span>
        - <span data-ttu-id="aa791-193">IIS 6 管理互換</span><span class="sxs-lookup"><span data-stu-id="aa791-193">IIS 6 Management Compatibility</span></span>
        - <span data-ttu-id="aa791-194">IIS 6 メタベース互換性</span><span class="sxs-lookup"><span data-stu-id="aa791-194">IIS 6 Metabase compatibility</span></span>
        - <span data-ttu-id="aa791-195">IIS 6 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="aa791-195">IIS 6 Management Console</span></span>
        - <span data-ttu-id="aa791-196">IIS 6 スクリプト ツール (adsutil.vbs のインストール)</span><span class="sxs-lookup"><span data-stu-id="aa791-196">IIS 6 Scripting Tools (Installs adsutil.vbs)</span></span>

3. <span data-ttu-id="aa791-197">インストールを続行します。コンピューターの再起動が求められたら再起動します。</span><span class="sxs-lookup"><span data-stu-id="aa791-197">Continue with the installation, and restart the computer if prompted.</span></span> 

<span data-ttu-id="aa791-198">**関連項目**: [Windows 8 または Windows Server 2012](http://www.iis.net/learn/get-started/whats-new-in-iis-8/installing-iis-8-on-windows-server-2012) に IIS をインストールする</span><span class="sxs-lookup"><span data-stu-id="aa791-198">**SEE ALSO** : Install IIS on [Windows 8 or Windows Server 2012](http://www.iis.net/learn/get-started/whats-new-in-iis-8/installing-iis-8-on-windows-server-2012).</span></span>


## <a name="run-64-bit-bam-portal-optional"></a><span data-ttu-id="aa791-199">64 ビットの BAM ポータル (オプション) を実行します。</span><span class="sxs-lookup"><span data-stu-id="aa791-199">Run 64-bit BAM portal (optional)</span></span>
<span data-ttu-id="aa791-200">BAM ポータルを使用しない場合は、このセクションを省略できます。</span><span class="sxs-lookup"><span data-stu-id="aa791-200">If you don't use the BAM portal, then you can skip this section.</span></span> 

<span data-ttu-id="aa791-201">BAM ポータルは、32 ビット モードで動作します。</span><span class="sxs-lookup"><span data-stu-id="aa791-201">The BAM Portal runs in 32-bit mode.</span></span> <span data-ttu-id="aa791-202">64 ビット環境でインターネット インフォメーション サービス (IIS) を使用している場合は、32 ビット モードで実行するアプリケーション プールを設定します。</span><span class="sxs-lookup"><span data-stu-id="aa791-202">If you are using Internet Information Services (IIS) in a 64-bit environment, then set the application pool to run in 32-bit mode.</span></span> 

#### <a name="using-adsutilvbs"></a><span data-ttu-id="aa791-203">adsutil.vbs を利用する</span><span class="sxs-lookup"><span data-stu-id="aa791-203">Using adsutil.vbs</span></span>
1.  <span data-ttu-id="aa791-204">管理者としてコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="aa791-204">Open a command prompt as administrator.</span></span> 
2.  <span data-ttu-id="aa791-205">コマンド プロンプトで、次のように入力します:</span><span class="sxs-lookup"><span data-stu-id="aa791-205">In the command prompt, type:</span></span>  
    `cscript c:\inetpub\adminscripts\adsutil.vbs SET W3SVC/AppPools/Enable32bitAppOnWin64 1`
3. <span data-ttu-id="aa791-206">Enter を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-206">Select Enter.</span></span>

#### <a name="using-iis-manager"></a><span data-ttu-id="aa791-207">IIS マネージャーを利用する</span><span class="sxs-lookup"><span data-stu-id="aa791-207">Using IIS Manager</span></span>
1. <span data-ttu-id="aa791-208">[スタート] メニューで、"inetmgr" を開きます。</span><span class="sxs-lookup"><span data-stu-id="aa791-208">In the Start menu, open "inetmgr".</span></span>
2.  <span data-ttu-id="aa791-209">コンピューター名を展開して、**[アプリケーション プール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-209">Expand the computer name, and select **Application Pools**.</span></span>
3.  <span data-ttu-id="aa791-210">**[DefaultAppPool]** を右クリックし、**[詳細設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-210">Right-click **DefaultAppPool**, and select **Advanced Settings**.</span></span> 
4.  <span data-ttu-id="aa791-211">**[32 ビット アプリケーションの有効化]** の値を **[True]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="aa791-211">Change the value of **Enable 32-bit Applications** to **True**.</span></span> 
5.  <span data-ttu-id="aa791-212">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-212">Select **OK**.</span></span>

## <a name="install-windows-identity-foundation-wif-optional"></a><span data-ttu-id="aa791-213">Windows Identity Foundation をインストールする (省略可能)</span><span class="sxs-lookup"><span data-stu-id="aa791-213">Install Windows Identity Foundation (WIF) (optional)</span></span>
<span data-ttu-id="aa791-214">SharePoint Services アダプターを使用する場合、BizTalk Server には、WIF が必要です。</span><span class="sxs-lookup"><span data-stu-id="aa791-214">If you use the SharePoint Services adapter, BizTalk Server requires WIF.</span></span> <span data-ttu-id="aa791-215">SharePoint Services アダプターを使用しない場合、このセクションを省略できます。</span><span class="sxs-lookup"><span data-stu-id="aa791-215">If you don't use the SharePoint Services adapter, you can skip this section.</span></span>

<span data-ttu-id="aa791-216">Windows Identity Foundation はオペレーティング システムに**機能**として付属します。</span><span class="sxs-lookup"><span data-stu-id="aa791-216">Windows Identity Foundation is included with the operating system as a **Feature**.</span></span>

1. <span data-ttu-id="aa791-217">[スタート] メニューで、**[Windows の機能の有効化または無効化]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa791-217">In the Start menu, open **Turn Windows Features on or off**.</span></span> <span data-ttu-id="aa791-218">あるいは、**[サーバー マネージャー]** を開き、**[管理]** を選択し、**[役割と機能の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-218">Or, open **Server Manager**, select **Manage**, and then select **Add roles and features**.</span></span>
2. <span data-ttu-id="aa791-219">**[Windows Identity Foundation 3.5]** を選択し、インストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="aa791-219">Select **Windows Identity Foundation 3.5**, and continue with the installation.</span></span> 
3. <span data-ttu-id="aa791-220">再起動を促すメッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="aa791-220">Restart the computer if prompted.</span></span>

## <a name="install--configure-smtp-server-optional"></a><span data-ttu-id="aa791-221">インストールして SMTP サーバー (省略可能) を構成するには.</span><span class="sxs-lookup"><span data-stu-id="aa791-221">Install & configure SMTP Server (optional)</span></span>
<span data-ttu-id="aa791-222">BAM 警告を使用する場合、BizTalk Server には、SMTP サーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="aa791-222">If you use BAM Alerts, BizTalk Server requires SMTP Server.</span></span> <span data-ttu-id="aa791-223">BAM 警告を使用しない場合、このセクションを省略できます。</span><span class="sxs-lookup"><span data-stu-id="aa791-223">If you don't use BAM Alerts, you can skip this section.</span></span>

<span data-ttu-id="aa791-224">SQL Server Database Mail では SMTP サーバーを使用して BAM 警告を送信します。</span><span class="sxs-lookup"><span data-stu-id="aa791-224">SQL Server Database Mail uses an SMTP Server to send BAM Alerts.</span></span> <span data-ttu-id="aa791-225">SMTP サーバーは BizTalk Server のローカル、または IIS のインストールされた別のサーバーにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="aa791-225">SMTP Server can be installed locally on the BizTalk Server or on another server with IIS installed.</span></span> <span data-ttu-id="aa791-226">SMTP サーバーは、Windows 8.1 や Windows 10 のようなクライアント オペレーティング システムでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="aa791-226">SMTP Server is not available on client operating systems, such as Windows 8.1 or Windows 10.</span></span> 

<span data-ttu-id="aa791-227">SMTP サーバーは**機能**としてサーバー オペレーティング システムに付属します。</span><span class="sxs-lookup"><span data-stu-id="aa791-227">SMTP Server is included with server operating systems as a **Feature**.</span></span>

1. <span data-ttu-id="aa791-228">[スタート] メニューで、**[Windows の機能の有効化または無効化]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa791-228">In the Start menu, open **Turn Windows Features on or off**.</span></span> <span data-ttu-id="aa791-229">あるいは、**[サーバー マネージャー]** を開き、**[管理]** を選択し、**[役割と機能の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-229">Or, open **Server Manager**, select **Manage**, and then select **Add roles and features**.</span></span>
2. <span data-ttu-id="aa791-230">**[SMTP サーバー]** を選択し、インストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="aa791-230">Select **SMTP Server**, and continue with the installation.</span></span> 
3. <span data-ttu-id="aa791-231">再起動を促すメッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="aa791-231">Restart the computer if prompted.</span></span>

## <a name="install-excel-2016-or-2013-optional"></a><span data-ttu-id="aa791-232">Excel 2016 または 2013 (省略可能) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="aa791-232">Install Excel 2016 or 2013 (optional)</span></span>
<span data-ttu-id="aa791-233">ビジネス アクティビティ監視 (BAM) を使用する場合、BizTalk Server には、Excel が必要です。</span><span class="sxs-lookup"><span data-stu-id="aa791-233">If you use Business Activity Monitoring (BAM), BizTalk Server requires Excel.</span></span> <span data-ttu-id="aa791-234">BAM を使用しない場合、このセクションを省略できます。</span><span class="sxs-lookup"><span data-stu-id="aa791-234">If you don't use BAM, you can skip this section.</span></span>

<span data-ttu-id="aa791-235">BAM の Office Excel では、監視するビジネス プロセスを定義します。</span><span class="sxs-lookup"><span data-stu-id="aa791-235">The BAM Office Excel Workbook defines the business processes you want to monitor.</span></span> <span data-ttu-id="aa791-236">この BAM Excel ブックでは、BAM によって収集されたデータをどのようにビジネス ユーザーの画面に表示するかを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="aa791-236">You also use the BAM Excel Workbook to define the way business users see the data collected by BAM.</span></span>

> [!IMPORTANT] 
> * <span data-ttu-id="aa791-237">BizTalk Server は、32 ビット版の Microsoft Office のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="aa791-237">BizTalk Server supports only 32-bit version of Microsoft Office.</span></span> 
> * <span data-ttu-id="aa791-238">BAM.xla を Excel に正しく読み込むには、(**[Office 共有機能]** の下の) **[Visual Basic for Applications]** をインストールします。</span><span class="sxs-lookup"><span data-stu-id="aa791-238">To successfully load BAM.xla into Excel, install **Visual Basic for Applications** (under **Office Shared Features**).</span></span> <span data-ttu-id="aa791-239">インストールしない場合、次のエラーが表示されることがあります: `This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.`</span><span class="sxs-lookup"><span data-stu-id="aa791-239">Otherwise, you may get error: `This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.`</span></span>

#### <a name="install-excel-2016"></a><span data-ttu-id="aa791-240">Excel 2016 をインストールする</span><span class="sxs-lookup"><span data-stu-id="aa791-240">Install Excel 2016</span></span>

<span data-ttu-id="aa791-241">Office 2016 は "クイック実行" または "C2R インストーラー" でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="aa791-241">Office 2016 is installed using "Click-to-Run" or "C2R Installer".</span></span> <span data-ttu-id="aa791-242">C2R インストールでは、Office 内のすべてのプログラムがダウンロードされ、インストールされます。</span><span class="sxs-lookup"><span data-stu-id="aa791-242">The C2R installation downloads and installs all programs within Office.</span></span> <span data-ttu-id="aa791-243">BAM の場合、必要なのは Excel のみです。</span><span class="sxs-lookup"><span data-stu-id="aa791-243">For BAM, we only need Excel.</span></span> <span data-ttu-id="aa791-244">この問題を回避するには、[Office 2016 展開ツール](https://www.microsoft.com/download/details.aspx?id=49117)をダウンロードしてインストールし、C2R インストーラーをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="aa791-244">To work around this, download and install the [Office 2016 Deployment Tool](https://www.microsoft.com/download/details.aspx?id=49117) to customize the C2R installer.</span></span>

1. <span data-ttu-id="aa791-245">[Office 2016 展開ツール](https://www.microsoft.com/download/details.aspx?id=49117)をダウンロードし、インストールします。</span><span class="sxs-lookup"><span data-stu-id="aa791-245">Download and install the [Office 2016 Deployment Tool](https://www.microsoft.com/download/details.aspx?id=49117).</span></span>
2. <span data-ttu-id="aa791-246">解凍した Office 2016 展開ツール ファイルが含まれるフォルダーで、メモ帳などのテキスト エディターで **configuration.xml** ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="aa791-246">In the folder with the Office 2016 Deployment Tool files you extracted, open the **configuration.xml** file with a text editor, such as notepad.</span></span>
3. <span data-ttu-id="aa791-247">`<Configuration>` セクションを次のように置換します。</span><span class="sxs-lookup"><span data-stu-id="aa791-247">Replace the `<Configuration>` section with the following:</span></span>  

    ```
    <Configuration>
    <Add SourcePath="D:\" OfficeClientEdition="32">
    <Product ID="O365ProPlusRetail" >
      <Language ID="en-us" />
      <ExcludeApp ID="Access" />
      <ExcludeApp ID="Groove" />
      <ExcludeApp ID="InfoPath" />
      <ExcludeApp ID="Lync" />
      <ExcludeApp ID="OneDrive" />
      <ExcludeApp ID="OneNote" />
      <ExcludeApp ID="Outlook" />
      <ExcludeApp ID="PowerPoint" />
      <ExcludeApp ID="Project" />
      <ExcludeApp ID="Publisher" />
      <ExcludeApp ID="SharePointDesigner" />
      <ExcludeApp ID="Visio" />
      <ExcludeApp ID="Word" />
    </Product>
    </Add>
    </Configuration>
    ```
    
    <span data-ttu-id="aa791-248">“SourcePath” を Office 2016 ISO ファイルの場所に置換します。</span><span class="sxs-lookup"><span data-stu-id="aa791-248">Replace “SourcePath” with the location of your Office 2016 ISO file.</span></span>
4. <span data-ttu-id="aa791-249">Office 2016 展開ツール ファイルが含まれるフォルダーで、**SHIFT** キーを押したままフォルダー内の何もない領域を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="aa791-249">In the folder with the Office 2016 Deployment Tool files, hold down the **SHIFT** key, and right-click an empty area in the folder.</span></span> <span data-ttu-id="aa791-250">**[コマンド ウィンドウをここで開く]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-250">Select **Open command window here**.</span></span> 
5. <span data-ttu-id="aa791-251">を入力し、Excel インストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="aa791-251">Start the Excel installation by entering the following:</span></span>  
  `setup.exe /configure configuration.xml`

    > [!TIP]
    > <span data-ttu-id="aa791-252">`setup.exe /download configuration.xml` は必要な Office セットアップ ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="aa791-252">`setup.exe /download configuration.xml` downloads the required office setup files.</span></span>
 
6. <span data-ttu-id="aa791-253">[Excel] を選択し、インストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="aa791-253">Select Excel, and continue with the installation.</span></span> 
 
<span data-ttu-id="aa791-254">**関連項目**: [Office 展開ツールのオプションの構成](https://technet.microsoft.com/library/jj219426.aspx)と [Office 2016 または 2013 のインストール](https://support.office.com/article/Install-Office-on-your-PC-or-Mac-4414eaaf-0478-48be-9c42-23adc4716658)</span><span class="sxs-lookup"><span data-stu-id="aa791-254">**SEE ALSO** : [Configuration options for the Office Deployment Tool](https://technet.microsoft.com/library/jj219426.aspx) and [Install Office 2016 or 2013](https://support.office.com/article/Install-Office-on-your-PC-or-Mac-4414eaaf-0478-48be-9c42-23adc4716658)</span></span>

#### <a name="install-excel-2013"></a><span data-ttu-id="aa791-255">Excel 2013 をインストールする</span><span class="sxs-lookup"><span data-stu-id="aa791-255">Install Excel 2013</span></span>
1. <span data-ttu-id="aa791-256">Microsoft Office のセットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="aa791-256">Run the Microsoft Office setup.</span></span>
2. <span data-ttu-id="aa791-257">**[カスタム インストール]** を選択し、[Excel] を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-257">Select a **Custom Install**, and select Excel.</span></span>
3. <span data-ttu-id="aa791-258">インストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="aa791-258">Continue with the installation.</span></span>   

## <a name="install-visual-c-redistributable-package"></a><span data-ttu-id="aa791-259">Visual C 再頒布可能パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="aa791-259">Install Visual C++ redistributable package</span></span>

<span data-ttu-id="aa791-260">ダウンロードしてインストール、 [Visual C 再頒布可能パッケージ](https://support.microsoft.com/help/3179560/update-for-visual-c-2013-and-visual-c-redistributable-package)です。</span><span class="sxs-lookup"><span data-stu-id="aa791-260">Download and install the [Visual C++ redistributable package](https://support.microsoft.com/help/3179560/update-for-visual-c-2013-and-visual-c-redistributable-package).</span></span> <span data-ttu-id="aa791-261">Visual Studio 2015 が使用されている場合でも、2013 バージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="aa791-261">The 2013 version is required, even though Visual Studio 2015 is used.</span></span>

<span data-ttu-id="aa791-262">[Visual C をダウンロード](https://support.microsoft.com/help/2977003/the-latest-supported-visual-c-downloads)使用可能なすべてのバージョンを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="aa791-262">The [Visual C++ downloads](https://support.microsoft.com/help/2977003/the-latest-supported-visual-c-downloads) lists all the available versions.</span></span>

## <a name="install-visual-studio-2015-optional"></a><span data-ttu-id="aa791-263">Visual Studio 2015 をインストールします (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="aa791-263">Install Visual Studio 2015 (optional)</span></span>
<span data-ttu-id="aa791-264">開発ツールで BizTalk プロジェクトを作成するために、BizTalk Server は Visual Studio を必要とします。</span><span class="sxs-lookup"><span data-stu-id="aa791-264">BizTalk Server requires Visual Studio to create BizTalk projects using the development tools.</span></span> <span data-ttu-id="aa791-265">これがステージングまたは運用サーバーの場合、あるいは BizTalk 開発を行っていない場合、このセクションを省略できます。</span><span class="sxs-lookup"><span data-stu-id="aa791-265">If this is a staging or production server, or you're not doing any BizTalk development, then skip this section.</span></span>

<span data-ttu-id="aa791-266">Visual Studio Enterprise Edition が推奨されますが、Professional 版と Community 版もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="aa791-266">Visual Studio Enterprise Edition is recommended, but Professional and Community editions are also supported.</span></span> 

1. <span data-ttu-id="aa791-267">Visual Studio のセットアップを管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="aa791-267">Run the Visual Studio setup as Administrator.</span></span>
2. <span data-ttu-id="aa791-268">**既定**のインストールを選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-268">Select a **Default** installation.</span></span> <span data-ttu-id="aa791-269">BizTalk Server は、オプション機能を必要としません。</span><span class="sxs-lookup"><span data-stu-id="aa791-269">BizTalk Server does not require any of the optional features.</span></span>

    > [!NOTE]
    > <span data-ttu-id="aa791-270">BizTalk プロジェクト以外でも Visual Studio を使用する場合、**カスタム** インストールを選択して他の機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="aa791-270">If you use Visual Studio for more than BizTalk projects, then select the **Custom** installation to install other features.</span></span> <span data-ttu-id="aa791-271">一般的に使用される機能に、Microsoft Web Developer Tools、Microsoft Office Developer Tools、PowerShell Tools for Visual Studio、ClickOnce Publishing Tools があります。</span><span class="sxs-lookup"><span data-stu-id="aa791-271">Some commonly-used features include Microsoft Web Developer Tools, Microsoft Office Developer Tools, PowerShell Tools for Visual Studio, and ClickOnce Publishing Tools.</span></span>
 
3. <span data-ttu-id="aa791-272">インストールを続行します。コンピューターの再起動が求められたら再起動します。</span><span class="sxs-lookup"><span data-stu-id="aa791-272">Continue with the installation, and restart your computer if prompted.</span></span>

<span data-ttu-id="aa791-273">**関連項目**: [Visual Studio のインストール](https://msdn.microsoft.com/library/e2h7fzkw.aspx)</span><span class="sxs-lookup"><span data-stu-id="aa791-273">**SEE ALSO** : [Installing Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx)</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="aa791-274">BizTalk Server をインストールする前に Visual Studio をインストールし、その後 Visual Studio Team Explorer にアップグレードする場合、BizTalk Server インストールの修復が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="aa791-274">If you install Visual Studio before installing BizTalk Server, and then upgrade to Visual Studio Team Explorer, you may need to repair your BizTalk Server installation.</span></span>
> - <span data-ttu-id="aa791-275">Visual Studio では、Microsoft SQL Server Express は自動的にインストールされますが、BizTalk Server では使用しません。</span><span class="sxs-lookup"><span data-stu-id="aa791-275">Visual Studio automatically installs Microsoft SQL Server Express; which is not used by BizTalk Server.</span></span> <span data-ttu-id="aa791-276">Microsoft SQL Server Express をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="aa791-276">Uninstall Microsoft SQL Server Express.</span></span> <span data-ttu-id="aa791-277">Microsoft SQL Server Compact もアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="aa791-277">You can also uninstall Microsoft SQL Server Compact.</span></span>  
> - <span data-ttu-id="aa791-278">BizTalk Server 開発ツールは、Visual Studio をベースとして動作します。</span><span class="sxs-lookup"><span data-stu-id="aa791-278">The BizTalk Server development tools are based on Visual Studio.</span></span> <span data-ttu-id="aa791-279">BizTalk Server 開発ツールと SDK をインストールする前に、少なくとも Microsoft Visual C#® .NET コンポーネントをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="aa791-279">At a minimum, install the Microsoft Visual C#® .NET component before you install the BizTalk Server Developer Tools and SDK.</span></span>
> - <span data-ttu-id="aa791-280">BizTalk Server ランタイムには、.NET Framework 4.6 が必要です。</span><span class="sxs-lookup"><span data-stu-id="aa791-280">The BizTalk Server runtime requires .NET Framework 4.6.</span></span> <span data-ttu-id="aa791-281">Windows Communication Foundation (WCF) アダプターまたは WCF インターセプターがインストールされている場合、.NET Framework 3.0 が必要</span><span class="sxs-lookup"><span data-stu-id="aa791-281">If the Windows Communication Foundation (WCF) adapter or WCF Interceptor is installed, then .NET Framework 3.0 is required</span></span>

#### <a name="uninstall-sql-server-express"></a><span data-ttu-id="aa791-282">SQL Server Express をアンインストールする</span><span class="sxs-lookup"><span data-stu-id="aa791-282">Uninstall SQL Server Express</span></span>
1. <span data-ttu-id="aa791-283">[スタート] メニューで、**[プログラムと機能]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="aa791-283">In the Start menu, open **Programs and Features**.</span></span> <span data-ttu-id="aa791-284">あるいは、**[コントロール パネル]** を開いて **[プログラムのアンインストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-284">Or, open the **Control Panel**, and select **Uninstall a program**.</span></span>
2. <span data-ttu-id="aa791-285">アンインストール:</span><span class="sxs-lookup"><span data-stu-id="aa791-285">Uninstall:</span></span> 
    - <span data-ttu-id="aa791-286">Microsoft SQL Server 2014 Express LocalDb</span><span class="sxs-lookup"><span data-stu-id="aa791-286">Microsoft SQL Server 2014 Express LocalDb</span></span>
    - <span data-ttu-id="aa791-287">Microsoft SQL Server Compact 4.0 SP1 x64 ENU</span><span class="sxs-lookup"><span data-stu-id="aa791-287">Microsoft SQL Server Compact 4.0 SP1 x64 ENU</span></span>
    - <span data-ttu-id="aa791-288">Microsoft SQL Server 2016 LocalDB (SQL Server 2016 Express LocalDB)</span><span class="sxs-lookup"><span data-stu-id="aa791-288">Microsoft SQL Server 2016 LocalDB (SQL Server 2016 Express LocalDB)</span></span>
    
3. <span data-ttu-id="aa791-289">アンインストールを続行します。コンピューターの再起動が求められたら再起動します。</span><span class="sxs-lookup"><span data-stu-id="aa791-289">Continue with the uninstall, and restart your computer if prompted.</span></span> 

## <a name="install-sql-server-2016"></a><span data-ttu-id="aa791-290">SQL Server 2016 のインストール</span><span class="sxs-lookup"><span data-stu-id="aa791-290">Install SQL Server 2016</span></span>
<span data-ttu-id="aa791-291">BizTalk Server には SQL Server が必要です。</span><span class="sxs-lookup"><span data-stu-id="aa791-291">BizTalk Server requires SQL Server.</span></span> <span data-ttu-id="aa791-292">SQL Server は、BizTalk と同じコンピューターにインストールすることも、別のコンピューターにインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="aa791-292">SQL Server can be installed on the same computer as BizTalk, or on a different computer.</span></span> <span data-ttu-id="aa791-293">ほとんどの運用環境では、BizTalk と SQL を別々のサーバーにインストールします。</span><span class="sxs-lookup"><span data-stu-id="aa791-293">Most production environments install BizTalk and SQL on separate servers.</span></span> 

> [!IMPORTANT]
> - <span data-ttu-id="aa791-294">SQL Server Express Edition は推奨されず、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="aa791-294">SQL Server Express Edition is not recommended or supported.</span></span> <span data-ttu-id="aa791-295">Express Edition には、BizTalk Server に必要な特定の機能が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="aa791-295">The Express edition does not include certain features needed by BizTalk Server.</span></span>
> - <span data-ttu-id="aa791-296">BizTalk Server は SQL Standard Edition をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="aa791-296">BizTalk Server supports SQL Standard Edition.</span></span> <span data-ttu-id="aa791-297">ただし、ビジネス アクティビティの監視のリアルタイム集計 (BAM RTA) を使用するには、SQL Server Enterprise Edition をインストールします。</span><span class="sxs-lookup"><span data-stu-id="aa791-297">However, to use Business Activity Monitoring real-time aggregation (BAM RTA), install SQL Server Enterprise Edition.</span></span> <span data-ttu-id="aa791-298">BAM リアルタイム集計 (RTA) は、SQL Server の Standard Edition ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="aa791-298">BAM real-time aggregation (RTA) is not supported in the Standard Edition of SQL Server.</span></span>
> - <span data-ttu-id="aa791-299">BizTalk Server SDK の全機能を使用する場合や、Visual Studio から BizTalk Server アプリケーションを展開する場合には、SQL Server 開発ツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="aa791-299">To fully use the BizTalk Server SDK or deploy BizTalk Server applications from a Visual Studio, install the SQL Server Development Tools.</span></span>
> - <span data-ttu-id="aa791-300">BizTalk Server では、バイナリ照合順序を除く、大文字と小文字を区別する/区別しないすべての SQL Server 照合順序がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="aa791-300">BizTalk Server supports all case-sensitive and case-insensitive SQL Server collations except for binary collations.</span></span> <span data-ttu-id="aa791-301">バイナリ照合順序はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="aa791-301">Binary collations are not supported.</span></span>

<span data-ttu-id="aa791-302">**特定のインストール手順については、次を参照してください。** [SQL Server 2016 のインストール](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup)または[SQL Server 2014 のインストール](https://msdn.microsoft.com/library/bb500469(v=sql.120).aspx)です。</span><span class="sxs-lookup"><span data-stu-id="aa791-302">**For specific install steps, see** [Install SQL Server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup) or [Install SQL Server 2014](https://msdn.microsoft.com/library/bb500469(v=sql.120).aspx).</span></span>

1. <span data-ttu-id="aa791-303">SQL Server のインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="aa791-303">Start the SQL Server installation.</span></span> 
2. <span data-ttu-id="aa791-304">機能セットアップ中に、以下の項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-304">During the Feature setup, select the following:</span></span>
    - <span data-ttu-id="aa791-305">データベース エンジン サービス</span><span class="sxs-lookup"><span data-stu-id="aa791-305">Database Engine Services</span></span>
        - <span data-ttu-id="aa791-306">SQL Server のレプリケーション</span><span class="sxs-lookup"><span data-stu-id="aa791-306">SQL Server Replication</span></span>
        - <span data-ttu-id="aa791-307">R Services (In-database) (**省略可能な**; でヒント[SQL Server R Services](https://docs.microsoft.com/sql/advanced-analytics/r/sql-server-r-services))</span><span class="sxs-lookup"><span data-stu-id="aa791-307">R Services (in-Database) (**optional**; info at [SQL Server R Services](https://docs.microsoft.com/sql/advanced-analytics/r/sql-server-r-services))</span></span>
        - <span data-ttu-id="aa791-308">検索のためのフルテキスト抽出とセマンティック抽出</span><span class="sxs-lookup"><span data-stu-id="aa791-308">Full-Text and Semantic Extractions for Search</span></span>
    - <span data-ttu-id="aa791-309">Analysis Services</span><span class="sxs-lookup"><span data-stu-id="aa791-309">Analysis Services</span></span>
    - <span data-ttu-id="aa791-310">Reporting Services - ネイティブ</span><span class="sxs-lookup"><span data-stu-id="aa791-310">Reporting Services - Native</span></span>
    - <span data-ttu-id="aa791-311">共有機能</span><span class="sxs-lookup"><span data-stu-id="aa791-311">Shared Features</span></span>
        - <span data-ttu-id="aa791-312">クライアント ツール接続</span><span class="sxs-lookup"><span data-stu-id="aa791-312">Client Tools Connectivity</span></span>
        - <span data-ttu-id="aa791-313">Integration Services</span><span class="sxs-lookup"><span data-stu-id="aa791-313">Integration Services</span></span>

    > [!NOTE]
    > <span data-ttu-id="aa791-314">**SQL Server Data Tools** は SQL Server の既定インストールには含まれていません。</span><span class="sxs-lookup"><span data-stu-id="aa791-314">**SQL Server Data Tools** is not included in the default installation of SQL Server.</span></span> <span data-ttu-id="aa791-315">必要ありませんがでダウンロードできます[SQL Server Data Tools (SSDT)](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt)です。</span><span class="sxs-lookup"><span data-stu-id="aa791-315">It isn't required, but can be downloaded at [SQL Server Data Tools (SSDT)](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt).</span></span> <span data-ttu-id="aa791-316">[**SQL Server Management Studio (SSMS)**](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms) をダウンロードします。これは、Azure SQL Database を含め、サポートされているあらゆるバージョンの SQL Server で動作します。</span><span class="sxs-lookup"><span data-stu-id="aa791-316">Download [**SQL Server Management Studio (SSMS)**](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms) that works with all supported versions of SQL Server, including Azure SQL Database.</span></span> <span data-ttu-id="aa791-317">ただし、BAM を使用する場合は、リモートの SSIS に接続するには、宛先 SSIS サーバーと同じバージョンの SSMS をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa791-317">However, to connect to remote SSIS when using BAM, you need to install the same version of SSMS as the destination SSIS server.</span></span> <span data-ttu-id="aa791-318">たとえば、 [SSMS 16 をインストールします *。x* ](https://docs.microsoft.com/sql/ssms/sql-server-management-studio-changelog-ssms?view=sql-server-2017#previous-ssms-releases) SQL 2016 SSIS への接続に関連するドライバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="aa791-318">For example, [install SSMS 16.*x*](https://docs.microsoft.com/sql/ssms/sql-server-management-studio-changelog-ssms?view=sql-server-2017#previous-ssms-releases) to install the related drivers to connect to SQL 2016 SSIS.</span></span> <span data-ttu-id="aa791-319">SSMS 17 です。*x* SQL 2016 SSIS に接続できません。</span><span class="sxs-lookup"><span data-stu-id="aa791-319">SSMS 17.*x* cannot connect to SQL 2016 SSIS.</span></span> <span data-ttu-id="aa791-320">複数のバージョンの SSMS はインストールされていることができます。</span><span class="sxs-lookup"><span data-stu-id="aa791-320">You can have multiple versions of SSMS installed.</span></span> 

3. <span data-ttu-id="aa791-321">インストールを続行します。コンピューターの再起動が求められたら再起動します。</span><span class="sxs-lookup"><span data-stu-id="aa791-321">Continue with the installation, and restart the computer if prompted.</span></span>

## <a name="disable-shared-memory"></a><span data-ttu-id="aa791-322">共有メモリを無効にします。</span><span class="sxs-lookup"><span data-stu-id="aa791-322">Disable Shared Memory</span></span>

1. <span data-ttu-id="aa791-323">**[SQL Server 構成マネージャー]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="aa791-323">Open **SQL Server Configuration Manager**.</span></span>
2. <span data-ttu-id="aa791-324">SQL Server 構成マネージャーで、展開**SQL Server ネットワーク構成**、し、 **MSSQLSERVER のプロトコル**です。</span><span class="sxs-lookup"><span data-stu-id="aa791-324">In SQL Server Configuration Manager, expand **SQL Server Network Configuration**, and then select **Protocols for MSSQLSERVER**.</span></span>
3. <span data-ttu-id="aa791-325">**[共有メモリ]** を右クリックし、**[無効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-325">Right-click **Shared Memory**, and then select **Disable**.</span></span>
4. <span data-ttu-id="aa791-326">選択**SQL Server サービス**、SQL を右クリックして**Server (MSSQLSERVER)**、し、**停止**です。</span><span class="sxs-lookup"><span data-stu-id="aa791-326">Select **SQL Server Services**, right-click SQL **Server (MSSQLSERVER)**, and then select **Stop**.</span></span> <span data-ttu-id="aa791-327">右クリックし、サービスが停止したら、 **SQL Server (MSSQLSERVER)**、し、**開始**です。</span><span class="sxs-lookup"><span data-stu-id="aa791-327">After the service has stopped, right-click **SQL Server (MSSQLSERVER)**, and then select **Start**.</span></span>
5. <span data-ttu-id="aa791-328">**SQL Server 構成マネージャー**を終了します。</span><span class="sxs-lookup"><span data-stu-id="aa791-328">Close **SQL Server Configuration Manager**.</span></span>

<span data-ttu-id="aa791-329">通常、共有メモリ プロトコルには、SQL Server と同じコンピューターにインストールされているクライアント (BizTalk Server) のみに影響します。</span><span class="sxs-lookup"><span data-stu-id="aa791-329">Typically, the Shared Memory protocol only impacts clients (BizTalk Server) that are installed on the same computer as SQL Server.</span></span> <span data-ttu-id="aa791-330">ある種のストレス条件下では (たとえば、同じコンピューターから複数のクライアントが SQL Server にアクセスしている場合)、SQL Server の共有メモリ プロトコルが原因で BizTalk Server のパフォーマンスが低下することがあります。</span><span class="sxs-lookup"><span data-stu-id="aa791-330">Under certain stress conditions (such as clients accessing SQL Server from the same computer), the SQL Server Shared Memory protocol may lower BizTalk Server performance.</span></span> <span data-ttu-id="aa791-331">共有メモリ ネットワーク プロトコルを無効にすると、この解決します。</span><span class="sxs-lookup"><span data-stu-id="aa791-331">Disabling the Shared Memory network protocol resolves this.</span></span>

> [!TIP]
> <span data-ttu-id="aa791-332">SQL Server エージェントが共有メモリを無効にした後を開始し、確認に失敗したかどうか[SQL Server 用 ODBC Driver 13.1](https://www.microsoft.com/download/details.aspx?id=53339)がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="aa791-332">If SQL Server Agent fails to start after disabling Shared Memory, then confirm [ODBC Driver 13.1 for SQL Server](https://www.microsoft.com/download/details.aspx?id=53339) is installed.</span></span>

## <a name="install-sql-xml-4"></a><span data-ttu-id="aa791-333">SQL XML 4 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="aa791-333">Install SQL XML 4</span></span>
<span data-ttu-id="aa791-334">BizTalk Server ランタイム、管理ツール、および BAM で必要です。</span><span class="sxs-lookup"><span data-stu-id="aa791-334">Required for BizTalk Server Runtime, Administrative Tools, and BAM.</span></span> 

<span data-ttu-id="aa791-335">ダウンロードしてインストール[SqlXml 4.0](https://www.microsoft.com/download/details.aspx?id=30403)です。</span><span class="sxs-lookup"><span data-stu-id="aa791-335">Download and install [SqlXml 4.0](https://www.microsoft.com/download/details.aspx?id=30403).</span></span>

## <a name="configure-sql-database-mail-optional"></a><span data-ttu-id="aa791-336">(省略可能) SQL データベース メールを構成します。</span><span class="sxs-lookup"><span data-stu-id="aa791-336">Configure SQL Database Mail (optional)</span></span>
<span data-ttu-id="aa791-337">BAM 警告を使用する場合、BizTalk Server には、SQL Server Database Mail が必要です。</span><span class="sxs-lookup"><span data-stu-id="aa791-337">If you use BAM Alerts, BizTalk Server requires SQL Server Database Mail.</span></span> <span data-ttu-id="aa791-338">BAM 警告を使用しない場合は、このセクションはスキップしてください。</span><span class="sxs-lookup"><span data-stu-id="aa791-338">If you don't use BAM Alerts, then skip this section.</span></span> 

<span data-ttu-id="aa791-339">**関連項目**: [データベース メール](https://docs.microsoft.com/sql/relational-databases/database-mail/database-mail)に詳細があります。</span><span class="sxs-lookup"><span data-stu-id="aa791-339">**SEE ALSO** : More on [Database Mail](https://docs.microsoft.com/sql/relational-databases/database-mail/database-mail).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="aa791-340">SMTP サーバーのサーバー名と TCP ポート番号を知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa791-340">You need to know the server name and TCP port number for the SMTP Server.</span></span> <span data-ttu-id="aa791-341">この同じコンピューターでは IIS と SMTP サーバーをインストールした場合、ローカル SMTP サーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa791-341">If you installed IIS and SMTP Server on this same computer, then you use the local SMTP Server.</span></span> <span data-ttu-id="aa791-342">SMTP サーバーが認証を必要とする場合、ユーザー名とパスワードを用意します。</span><span class="sxs-lookup"><span data-stu-id="aa791-342">If the SMTP server requires authentication, then have the user name and password ready.</span></span>
> - <span data-ttu-id="aa791-343">BAM ポータルと BAM 警告は別々の機能です。</span><span class="sxs-lookup"><span data-stu-id="aa791-343">The BAM portal and BAM Alerts are separate features.</span></span> <span data-ttu-id="aa791-344">BAM 警告を使用している場合、SQL Server Database Mail が必要です。</span><span class="sxs-lookup"><span data-stu-id="aa791-344">If you are using BAM Alerts, then SQL Server Database Mail is required.</span></span> <span data-ttu-id="aa791-345">BAM 警告を使用していない場合、SQL Server Database Mail は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="aa791-345">If you are not using BAM Alerts, then SQL Server Database Mail is not required.</span></span>

<span data-ttu-id="aa791-346">**特定の構成手順については、次を参照してください。**: 構成[SQL Server 2016 データベース メール](https://docs.microsoft.com/sql/relational-databases/database-mail/configure-database-mail)または[SQL Server 2014 データベース メール](https://msdn.microsoft.com/library/hh245116(v=sql.120).aspx)です。</span><span class="sxs-lookup"><span data-stu-id="aa791-346">**For specific configuration steps, see**: Configure [SQL Server 2016 Database Mail](https://docs.microsoft.com/sql/relational-databases/database-mail/configure-database-mail) or [SQL Server 2014 Database Mail](https://msdn.microsoft.com/library/hh245116(v=sql.120).aspx).</span></span>

   
<span data-ttu-id="aa791-347">テスト メールを送信するには:</span><span class="sxs-lookup"><span data-stu-id="aa791-347">To send a test email:</span></span> 
1.  <span data-ttu-id="aa791-348">**[データベース メール]** を右クリックし、**[テスト電子メールの送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-348">Right-click **Database Mail**, and select **Send Test E-Mail**.</span></span> 
2.  <span data-ttu-id="aa791-349">**[宛先:]** メール アドレスを入力し、**[テスト電子メールの送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa791-349">Enter a **To:** email address, and select **Send Test E-Mail**.</span></span>  
 
<span data-ttu-id="aa791-350">**[宛先:]** の受信者がメールを受信すると、データベース メールが構成されます。</span><span class="sxs-lookup"><span data-stu-id="aa791-350">If the **To:** recipient receives the email, then Database Mail is configured.</span></span> 

## <a name="install-winscp-optional"></a><span data-ttu-id="aa791-351">(省略可能) WinSCP をインストールします。</span><span class="sxs-lookup"><span data-stu-id="aa791-351">Install WinSCP (optional)</span></span>
<span data-ttu-id="aa791-352">FTP アダプタで必要です。</span><span class="sxs-lookup"><span data-stu-id="aa791-352">Required by the FTP adapter.</span></span> <span data-ttu-id="aa791-353">FTP アダプターを使用しない場合は、このセクションをスキップします。</span><span class="sxs-lookup"><span data-stu-id="aa791-353">If you don't use the FTP adapter, then skip this section.</span></span> 

<span data-ttu-id="aa791-354">ダウンロードしてインストール[WinSCP](http://winscp.net)です。</span><span class="sxs-lookup"><span data-stu-id="aa791-354">Download and install [WinSCP](http://winscp.net).</span></span> 

## <a name="next-step"></a><span data-ttu-id="aa791-355">次の手順</span><span class="sxs-lookup"><span data-stu-id="aa791-355">Next step</span></span>
<span data-ttu-id="aa791-356">[BizTalk Server 2016](../install-and-config-guides/install-biztalk-server-2016.md) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="aa791-356">Install [BizTalk Server 2016](../install-and-config-guides/install-biztalk-server-2016.md).</span></span>
