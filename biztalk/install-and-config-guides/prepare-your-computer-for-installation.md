---
title: "コンピューターのインストールの準備 |Microsoft ドキュメント"
ms.custom: 
ms.date: 2016-03-15
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53df7a2f-638b-4921-a97f-736760248526
caps.latest.revision: "32"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a493c1a0ef38e9be5e229ff82f8773211adfe765
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="prepare-your-computer-for-installation"></a><span data-ttu-id="f4795-102">インストールのためのコンピューターの準備</span><span class="sxs-lookup"><span data-stu-id="f4795-102">Prepare Your Computer for Installation</span></span>
<span data-ttu-id="f4795-103">ここでは、コンピューターの準備を整える手順について説明します。必要なソフトウェアをすべてインストールして構成し、アカウントを作成してアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="f4795-103">This topic lists the steps to prepare your computer by installing and configuring all software prerequisites, and then creating accounts and setting permissions.</span></span>  

> [!TIP] 
> <span data-ttu-id="f4795-104">統合に詳しいユーザーが、前提条件と BizTalk Server をインストールするとても詳細な手順が説明された「[BizTalk 2013 Installation and Configuration part 1](http://sandroaspbiztalkblog.wordpress.com/2013/05/05/biztalk-2013-installation-and-configuration-important-considerations-before-set-up-the-server-part-1/)」 (BizTalk 2013 のインストールおよび構成パート 1) を用意しました。</span><span class="sxs-lookup"><span data-stu-id="f4795-104">An integration MVP prepared a very detailed step-by-step guide to install the prerequisites, and BizTalk Server:  [BizTalk 2013 Installation and Configuration part 1](http://sandroaspbiztalkblog.wordpress.com/2013/05/05/biztalk-2013-installation-and-configuration-important-considerations-before-set-up-the-server-part-1/).</span></span>  
> 
> <span data-ttu-id="f4795-105">ユーザー アクセス制御 (UAC) や Windows ファイアウォールの無効化など、いくつかの手順はマイクロソフトでは推奨していません。</span><span class="sxs-lookup"><span data-stu-id="f4795-105">Some steps are not recommended by Microsoft, such as disabling User Access Control (UAC) or Windows Firewall.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="f4795-106">ここに示している順序どおりに作業は実行してください。</span><span class="sxs-lookup"><span data-stu-id="f4795-106">Complete these tasks in the order listed.</span></span>  
  
##  <a name="BKMK_InstUpdates"></a> <span data-ttu-id="f4795-107">Windows の更新プログラムをインストールする</span><span class="sxs-lookup"><span data-stu-id="f4795-107">Install Windows Updates</span></span>  
  
-   <span data-ttu-id="f4795-108">**Windows 7**: [スタート] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-108">**Windows 7**: Click Start.</span></span> <span data-ttu-id="f4795-109">[**検索**] テキスト ボックスで、「**Windows Update**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="f4795-109">In the **Search** text box, type **Windows Update**.</span></span>  
  
-   <span data-ttu-id="f4795-110">**Windows 8.1､[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] および [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2**: キーボードの Windows ボタンをクリックして「**Windows Update**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="f4795-110">**Windows 8.1, [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)], and [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2**: Click the Windows button on the keyboard and type **Windows Update**.</span></span> <span data-ttu-id="f4795-111">[検索結果] ウィンドウで、[**Windows Update**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-111">From the search results, click **Windows Update**.</span></span>  
  
 <span data-ttu-id="f4795-112">更新プログラムのインストール後、コンピューターを再起動する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f4795-112">After installing updates, you may need to restart the computer.</span></span>  
  
##  <a name="BKMK_IIS"></a> <span data-ttu-id="f4795-113">インターネット インフォメーション サービス (IIS) の有効化</span><span class="sxs-lookup"><span data-stu-id="f4795-113">Enable Internet Information Services</span></span>  
 <span data-ttu-id="f4795-114">Microsoft インターネット インフォメーション サービス (IIS) は、以下を含む [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のさまざまな機能によって使用される Web アプリケーション インフラストラクチャです。</span><span class="sxs-lookup"><span data-stu-id="f4795-114">Microsoft Internet Information Services (IIS) provides a Web application infrastructure for many [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features, including:</span></span>  
  
-   <span data-ttu-id="f4795-115">HTTP アダプター</span><span class="sxs-lookup"><span data-stu-id="f4795-115">HTTP adapter</span></span>  
  
-   <span data-ttu-id="f4795-116">SOAP アダプター</span><span class="sxs-lookup"><span data-stu-id="f4795-116">SOAP adapter</span></span>  
  
-   <span data-ttu-id="f4795-117">Windows SharePoint Services アダプター</span><span class="sxs-lookup"><span data-stu-id="f4795-117">Windows SharePoint Services adapter</span></span>  
  
-   <span data-ttu-id="f4795-118">SSL (Secure Sockets Layer) 暗号化</span><span class="sxs-lookup"><span data-stu-id="f4795-118">Secure Sockets Layer (SSL) encryption</span></span>  
  
-   <span data-ttu-id="f4795-119">BAM ポータル</span><span class="sxs-lookup"><span data-stu-id="f4795-119">BAM Portal</span></span>  
  
#### <a name="install-iis-75-on-windows-7-sp1"></a><span data-ttu-id="f4795-120">Windows 7 SP1 に IIS 7.5 をインストールする</span><span class="sxs-lookup"><span data-stu-id="f4795-120">Install IIS 7.5 on Windows 7 SP1</span></span>  
  
1.  <span data-ttu-id="f4795-121">[**スタート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4795-121">Select **Start**.</span></span> <span data-ttu-id="f4795-122">[**検索**] テキスト ボックスに「**プログラムと機能**」と入力し、開きます。</span><span class="sxs-lookup"><span data-stu-id="f4795-122">In the **Search** text box, type **Programs and Features**, and open it.</span></span>  
  
2.  <span data-ttu-id="f4795-123">[**Windows の機能の有効化または無効化**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4795-123">Select**Turn Windows features on or off**.</span></span>  
  
3.  <span data-ttu-id="f4795-124">[**インターネット インフォメーション サービス**] を選択して、[**インターネット インフォメーション サービス**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="f4795-124">Select**Internet Information Services** and expand **Internet Information Services**.</span></span> <span data-ttu-id="f4795-125">既定でオンになっているオプションのほか、次の項目もオンにします:</span><span class="sxs-lookup"><span data-stu-id="f4795-125">In addition to the default checked options, also check the following:</span></span>  
  
    -   <span data-ttu-id="f4795-126">[**Web 管理ツール**]: 次の項目もオンにします。</span><span class="sxs-lookup"><span data-stu-id="f4795-126">**Web Management Tools**: Also check:</span></span>  
  
        -   <span data-ttu-id="f4795-127">IIS 6 管理互換:</span><span class="sxs-lookup"><span data-stu-id="f4795-127">IIS 6 Management Compatibility:</span></span>  
  
            -   <span data-ttu-id="f4795-128">IIS 6 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="f4795-128">IIS 6 Management Console</span></span>  
  
            -   <span data-ttu-id="f4795-129">IIS メタベースおよび IIS 6 構成との互換性</span><span class="sxs-lookup"><span data-stu-id="f4795-129">IIS Metabase and IIS 6 configuration compatibility</span></span>  
  
        -   <span data-ttu-id="f4795-130">IIS 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="f4795-130">IIS Management Console</span></span>  
  
    -   <span data-ttu-id="f4795-131">[**World Wide Web サービス**]: [**セキュリティ**] を展開し、次も選択します。</span><span class="sxs-lookup"><span data-stu-id="f4795-131">**World Wide Web Services**: Expand **Security** and also select:</span></span>  
  
        -   <span data-ttu-id="f4795-132">基本認証</span><span class="sxs-lookup"><span data-stu-id="f4795-132">Basic Authentication</span></span>  
  
        -   <span data-ttu-id="f4795-133">[Windows 認証]</span><span class="sxs-lookup"><span data-stu-id="f4795-133">Windows Authentication</span></span>  
  
4.  <span data-ttu-id="f4795-134">[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4795-134">Select **OK**.</span></span> <span data-ttu-id="f4795-135">完了したら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-135">When complete, click **Close**.</span></span>  
  
 <span data-ttu-id="f4795-136">[http://go.microsoft.com/fwlink/p/?LinkId=257033](http://go.microsoft.com/fwlink/p/?LinkId=257033) にも、Windows 7 で IIS を有効にする手順が記載されています。</span><span class="sxs-lookup"><span data-stu-id="f4795-136">[http://go.microsoft.com/fwlink/p/?LinkId=257033](http://go.microsoft.com/fwlink/p/?LinkId=257033) also lists the steps to enable IIS on Windows 7.</span></span>  
  
#### <a name="install-iis-80-on-windows-8"></a><span data-ttu-id="f4795-137">Windows 8 に IIS 8.0 をインストールする</span><span class="sxs-lookup"><span data-stu-id="f4795-137">Install IIS 8.0 on Windows 8</span></span>  
  
1.  <span data-ttu-id="f4795-138">キーボードの Windows ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="f4795-138">Select the Windows button on your keyboard.</span></span> <span data-ttu-id="f4795-139">「**プログラムと機能**」と入力して [**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4795-139">Type **Programs and Features** and select**Settings**.</span></span> <span data-ttu-id="f4795-140">[検索結果] ウィンドウで、[**プログラムと機能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4795-140">In the Results window, select **Programs and Features**.</span></span>  
  
2.  <span data-ttu-id="f4795-141">[**Windows の機能の有効化または無効化**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4795-141">Select **Turn Windows features on or off**.</span></span>  
  
3.  <span data-ttu-id="f4795-142">[**インターネット インフォメーション サービス**] を選択して、[**インターネット インフォメーション サービス**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="f4795-142">Select **Internet Information Services** and expand **Internet Information Services**.</span></span> <span data-ttu-id="f4795-143">既定でオンになっているオプションのほか、次の項目も選択します:</span><span class="sxs-lookup"><span data-stu-id="f4795-143">In addition to the default checked options, also select the following:</span></span>  
  
    -   <span data-ttu-id="f4795-144">[**Web 管理ツール**]: 次の項目もオンにします。</span><span class="sxs-lookup"><span data-stu-id="f4795-144">**Web Management Tools**: Also check:</span></span>  
  
        -   <span data-ttu-id="f4795-145">IIS 6 管理互換:</span><span class="sxs-lookup"><span data-stu-id="f4795-145">IIS 6 Management Compatibility:</span></span>  
  
            -   <span data-ttu-id="f4795-146">IIS 6 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="f4795-146">IIS 6 Management Console</span></span>  
  
            -   <span data-ttu-id="f4795-147">IIS メタベースおよび IIS 6 構成との互換性</span><span class="sxs-lookup"><span data-stu-id="f4795-147">IIS Metabase and IIS 6 configuration compatibility</span></span>  
  
        -   <span data-ttu-id="f4795-148">IIS 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="f4795-148">IIS Management Console</span></span>  
  
    -   <span data-ttu-id="f4795-149">[**World Wide Web サービス**]: [**セキュリティ**] を展開し、次の項目もオンにします。</span><span class="sxs-lookup"><span data-stu-id="f4795-149">**World Wide Web Services**: Expand **Security** and also check:</span></span>  
  
        -   <span data-ttu-id="f4795-150">基本認証</span><span class="sxs-lookup"><span data-stu-id="f4795-150">Basic Authentication</span></span>  
  
        -   <span data-ttu-id="f4795-151">[Windows 認証]</span><span class="sxs-lookup"><span data-stu-id="f4795-151">Windows Authentication</span></span>  
  
4.  <span data-ttu-id="f4795-152">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-152">Click **OK**.</span></span> <span data-ttu-id="f4795-153">完了したら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-153">When complete, click **Close**.</span></span>  
  
 <span data-ttu-id="f4795-154">[http://go.microsoft.com/fwlink/p/?LinkID=291297](http://go.microsoft.com/fwlink/p/?LinkID=291297) にも、Windows 8 で IIS を有効にする手順が記載されています。</span><span class="sxs-lookup"><span data-stu-id="f4795-154">[http://go.microsoft.com/fwlink/p/?LinkID=291297](http://go.microsoft.com/fwlink/p/?LinkID=291297) also lists the steps to enable IIS on Windows 8.</span></span>  
  
#### <a name="install-iis-80-on-windows-server-2012"></a><span data-ttu-id="f4795-155">Windows Server 2012 に IIS 8.0 をインストールする</span><span class="sxs-lookup"><span data-stu-id="f4795-155">Install IIS 8.0 on Windows Server 2012</span></span>  
  
1.  <span data-ttu-id="f4795-156">[**サーバー マネージャー**] を開いて、左ペインにある [**ダッシュボード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-156">Open **Server Manager** and click **Dashboard** in the left pane.</span></span>  
  
2.  <span data-ttu-id="f4795-157">[**役割と機能の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-157">Click **Add roles and features**.</span></span> <span data-ttu-id="f4795-158">[**役割と機能の追加**] は、右上にある [**管理**] メニューから開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="f4795-158">**Add Roles and Features** can also be opened from the **Manage** menu in the top right-hand corner.</span></span>  
  
3.  <span data-ttu-id="f4795-159">[**開始する前に**] ウィンドウで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-159">On the **Before You Begin** window, click **Next**.</span></span>  
  
4.  <span data-ttu-id="f4795-160">[**インストールの種類**] ウィンドウで、[**役割ベースまたは機能ベースのインストール**] をクリックして [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-160">On the **Installation Type** window, click **Role-based or feature-based installation**, and click **Next**.</span></span>  
  
5.  <span data-ttu-id="f4795-161">[**サーバーの選択**] ウィンドウで、[**サーバー プールからサーバーを選択**] をクリックして使用するサーバーをクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-161">On the **Server Selection** window, click **Select a server from the server pool**, click the desired server, and click **Next**.</span></span>  
  
     <span data-ttu-id="f4795-162">[**サーバーの選択**] ウィンドウには、[**サーバー マネージャー**] の [**サーバーの追加**] で追加したサーバーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4795-162">The **Server Selection** window lists the servers that have been added using **Add Server** in **Server Manager**.</span></span> <span data-ttu-id="f4795-163">既定では、ローカル サーバーが選択されます。</span><span class="sxs-lookup"><span data-stu-id="f4795-163">By default, it selects the local server.</span></span> <span data-ttu-id="f4795-164">「[サーバー マネージャーへのサーバーの追加](http://go.microsoft.com/fwlink/p/?LinkID=241353)」に、[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] での [**サーバーの追加**] の使用手順が記載されています。</span><span class="sxs-lookup"><span data-stu-id="f4795-164">[Add Servers to Server Manager](http://go.microsoft.com/fwlink/p/?LinkID=241353) lists the steps to use **Add Server** on [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)].</span></span>  
  
6.  <span data-ttu-id="f4795-165">[**サーバーの役割**] ウィンドウで、[**Web サーバー (IIS)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-165">On the **Server Roles** window, click **Web Server (IIS)**.</span></span> <span data-ttu-id="f4795-166">確認のメッセージが表示されたら、[**機能を追加**] をクリックして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-166">If prompted, click **Add Features**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="f4795-167">[**機能**] ウィンドウで既定のオプションを有効にしたまま、次の内容も検討してください。</span><span class="sxs-lookup"><span data-stu-id="f4795-167">On the **Features** window, keep the default options enabled and also consider the following:</span></span>  
  
     <span data-ttu-id="f4795-168">**.Net Framework 3.5 の機能**: [!INCLUDE[dotnet45](../includes/dotnet45-md.md)] と [!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)] を使用して、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] を使用した .Net アプリケーションを開発できます。</span><span class="sxs-lookup"><span data-stu-id="f4795-168">**.Net Framework 3.5 Features**: [!INCLUDE[dotnet45](../includes/dotnet45-md.md)] and [!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)] can be used to develop .Net applications involving the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="f4795-169">通常、**[!INCLUDE[dotnet45](../includes/dotnet45-md.md)] の機能**は既にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="f4795-169">Typically, **[!INCLUDE[dotnet45](../includes/dotnet45-md.md)] Features** is already installed.</span></span> <span data-ttu-id="f4795-170">このコンピューターで [!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)] を使用してアプリケーションを作成する場合は、**.Net Framework 3.5 の機能**もインストールできます。</span><span class="sxs-lookup"><span data-stu-id="f4795-170">If you will use [!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)] to create applications on this computer, then **.Net Framework 3.5 Features** can also be installed.</span></span>  
  
     <span data-ttu-id="f4795-171">**メッセージ キュー**: MSMQ アダプターを使用する場合は、[**メッセージ キュー**] をオンにしてローカルの MSMQ ストアを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f4795-171">**Message Queuing**: If you are using the MSMQ adapter, you can create a local MSMQ store by checking **Message Queuing**.</span></span>  
  
     <span data-ttu-id="f4795-172">**SMTP サーバー**: SMTP アダプターを使用する場合は、[**SMTP サーバー**] をオンにしてローカルの SMTP サーバーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f4795-172">**SMTP Server**: If you are using the SMTP adapter, you can create a local SMTP Server by checking **SMTP Server**.</span></span>  
  
     <span data-ttu-id="f4795-173">**Windows Identity Foundation 3.5**: Windows Identity Foundation (WIF) は、CSOM インストール オプションを使用する際に [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] アダプターで必要になります。</span><span class="sxs-lookup"><span data-stu-id="f4795-173">**Windows Identity Foundation 3.5**: Windows Identity Foundation (WIF) is required by the [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] adapter when using the CSOM installation option.</span></span> <span data-ttu-id="f4795-174">「[付録 B: Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)」では、[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] アダプターの CSOM インストール オプションについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="f4795-174">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) describes the CSOM installation option for the [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] adapter.</span></span>  
  
     <span data-ttu-id="f4795-175">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-175">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="f4795-176">[**Web サーバーの役割 (IIS)**] ウィンドウで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-176">On the **Web Server Role (IIS)** window, click **Next**.</span></span>  
  
9. <span data-ttu-id="f4795-177">[**役割サービス**] ウィンドウ ([**Web サーバーの役割 (IIS)**] の下) で、次のオプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-177">On the **Role Services** window (under **Web Server Role (IIS)**), click the following options:</span></span>  
  
     <span data-ttu-id="f4795-178">[**セキュリティ**]: 既定のオプションに加えて、次の項目もクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-178">**Security**: In addition to the default options, also click:</span></span>  
  
    -   <span data-ttu-id="f4795-179">基本認証</span><span class="sxs-lookup"><span data-stu-id="f4795-179">Basic Authentication</span></span>  
  
    -   <span data-ttu-id="f4795-180">[Windows 認証]</span><span class="sxs-lookup"><span data-stu-id="f4795-180">Windows Authentication</span></span>  
  
     <span data-ttu-id="f4795-181">[**アプリケーション開発**]: [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では既定のオプションで十分です。</span><span class="sxs-lookup"><span data-stu-id="f4795-181">**Application Development**: The default options are sufficient for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="f4795-182">このコンピューターで他の IIS ベースのアプリケーションをホストする場合は、必要な役割をオンにします。</span><span class="sxs-lookup"><span data-stu-id="f4795-182">If you host other IIS-based applications on this computer, check the needed roles.</span></span>  
  
     <span data-ttu-id="f4795-183">**管理ツール**: 既定のオプションに加えて、次の項目もクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-183">**Management Tools**: In addition to the default options, also click:</span></span>  
  
    -   <span data-ttu-id="f4795-184">IIS 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="f4795-184">IIS Management Console</span></span>  
  
    -   <span data-ttu-id="f4795-185">IIS 6 管理互換:</span><span class="sxs-lookup"><span data-stu-id="f4795-185">IIS 6 Management Compatibility:</span></span>  
  
        -   <span data-ttu-id="f4795-186">IIS 6 メタベース互換性</span><span class="sxs-lookup"><span data-stu-id="f4795-186">IIS 6 Metabase Compatibility</span></span>  
  
        -   <span data-ttu-id="f4795-187">IIS 6 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="f4795-187">IIS 6 Management Console</span></span>  
  
     <span data-ttu-id="f4795-188">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-188">Click **Next**.</span></span>  
  
10. <span data-ttu-id="f4795-189">[**確認**] ウィンドウで [**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-189">On the **Confirmation** window, click **Install**.</span></span> <span data-ttu-id="f4795-190">完了したら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-190">When complete, click **Close**.</span></span>  
  
 <span data-ttu-id="f4795-191">[http://go.microsoft.com/fwlink/p/?LinkID=291297](http://go.microsoft.com/fwlink/p/?LinkID=291297) にも、[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] で IIS を有効にする手順が記載されています。</span><span class="sxs-lookup"><span data-stu-id="f4795-191">[http://go.microsoft.com/fwlink/p/?LinkID=291297](http://go.microsoft.com/fwlink/p/?LinkID=291297) also lists the steps to enable IIS on [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)].</span></span>  
  
##  <a name="BKMK_XLS"></a> <span data-ttu-id="f4795-192">Microsoft Office Excel のインストール</span><span class="sxs-lookup"><span data-stu-id="f4795-192">Install Microsoft Office Excel</span></span>  
  
1.  <span data-ttu-id="f4795-193">Microsoft Office のセットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="f4795-193">Run the Microsoft Office setup.</span></span>  
  
2.  <span data-ttu-id="f4795-194">[**インストールの種類**] 画面が表示されたら、[**カスタム インストール**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4795-194">When you reach the **Type of Installation** screen, select **Custom Install**, and then select **Next**.</span></span>  
  
3.  <span data-ttu-id="f4795-195">[**カスタム セットアップ**] 画面で、[**Excel**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4795-195">On the **Custom Setup** screen, select **Excel**, and then select **Next**.</span></span>  
  
4.  <span data-ttu-id="f4795-196">[**インストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4795-196">Select **Install**.</span></span>  
  
5.  <span data-ttu-id="f4795-197">[**セットアップが完了しました**] 画面で、[**終了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4795-197">In **Setup Completed**, select **Finish**.</span></span>  
  
 <span data-ttu-id="f4795-198">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="f4795-198">**Additional**</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f4795-199"> は、32 ビット版の Microsoft Office のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f4795-199"> supports only 32-bit version of Microsoft Office.</span></span>  
  
-   <span data-ttu-id="f4795-200">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のビジネス アクティビティの監視 (BAM) では、Microsoft Office Excel が必要です。</span><span class="sxs-lookup"><span data-stu-id="f4795-200">Microsoft Office Excel is required by Business Activity Monitoring (BAM) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="f4795-201">BAM の Office Excel では、監視するビジネス プロセスを定義します。</span><span class="sxs-lookup"><span data-stu-id="f4795-201">The BAM Office Excel Workbook defines the business processes you want to monitor.</span></span> <span data-ttu-id="f4795-202">この BAM Excel ブックでは、BAM によって収集されたデータをどのようにビジネス ユーザーの画面に表示するかを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="f4795-202">You also use the BAM Excel Workbook to define the way business users see the data collected by BAM.</span></span>  
  
-   <span data-ttu-id="f4795-203">BAM.xla を Excel に正しく読み込むには、[**Office 共有機能**] の下の [**Visual Basic for Applications**] をインストールします。</span><span class="sxs-lookup"><span data-stu-id="f4795-203">To successfully load BAM.xla into Excel, install **Visual Basic for Applications** under **Office Shared Features**.</span></span> <span data-ttu-id="f4795-204">これを行わない場合は、「このブックにある、VBA プロジェクト、ActiveX コントロール、およびその他のプログラミング関連の機能は失われています。」というエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f4795-204">Otherwise, you may get error “This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.”</span></span>  
  
##  <a name="BKMK_VS"></a> <span data-ttu-id="f4795-205">Visual Studio のインストール</span><span class="sxs-lookup"><span data-stu-id="f4795-205">Install Visual Studio</span></span>  
  
1.  <span data-ttu-id="f4795-206">Visual Studio のセットアップを管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="f4795-206">Run the Visual Studio setup as Administrator.</span></span>  
  
2.  <span data-ttu-id="f4795-207">ライセンス契約に同意して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-207">Accept the license agreement and click **Next**.</span></span>  
  
3.  <span data-ttu-id="f4795-208">[**インストールするオプション機能**] で必要なオプションを選択し、[**インストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4795-208">In **Optional features to install**, select the options you need and then select **Install**.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f4795-209"> には必須のオプション機能はありません。</span><span class="sxs-lookup"><span data-stu-id="f4795-209"> does not require any of the optional features.</span></span>  
  
4.  <span data-ttu-id="f4795-210">[**完了**] ページで、ウィンドウを閉じるか [**起動**] をクリックして Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="f4795-210">On the **Finish** page, close the window or click **Launch** to open Visual Studio.</span></span>  
  
 <span data-ttu-id="f4795-211">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="f4795-211">**Additional**</span></span>  
  
-   <span data-ttu-id="f4795-212">Visual Studio をインストールしてから [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールし、Visual Studio チーム エクスプローラーにアップグレードする場合、インストール済みの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を [**コントロール パネル**] の [**プログラム**] から修復する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f4795-212">If you install Visual Studio before installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and then upgrade to Visual Studio Team Explorer, you may need to repair your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation from the **Control Panel** / **Programs** option.</span></span>  
  
-   <span data-ttu-id="f4795-213">Visual Studio では、Microsoft SQL Server Express は自動的にインストールされますが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では使用しません。</span><span class="sxs-lookup"><span data-stu-id="f4795-213">Visual Studio automatically installs Microsoft SQL Server Express; which is not used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="f4795-214">Microsoft SQL Server Express をアンインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f4795-214">As a best practice, uninstall Microsoft SQL Server Express.</span></span>  
  
-   <span data-ttu-id="f4795-215">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 開発ツールは、Visual Studio をベースとして動作します。</span><span class="sxs-lookup"><span data-stu-id="f4795-215">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] development tools are based on Visual Studio.</span></span> <span data-ttu-id="f4795-216">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **開発ツールと SDK** をインストールする前に、少なくとも Visual Studio の Microsoft Visual C#® .NET コンポーネントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4795-216">At a minimum, you must install the Microsoft Visual C#® .NET component of Visual Studio before you install the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**Developer Tools and SDK**.</span></span>  
  
-   <span data-ttu-id="f4795-217">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールするコンピューターが実稼働用 (ランタイムのみ) であり、アプリ開発やデバッグを行わない場合は、Visual Studio は*不要*です。</span><span class="sxs-lookup"><span data-stu-id="f4795-217">Visual Studio is *not* required if you are installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on a production computer (runtime only), on which no application development or debugging is required.</span></span>  
  
-   <span data-ttu-id="f4795-218">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイムでは、[!INCLUDE[dotnet45](../includes/dotnet45-md.md)] が必要です。</span><span class="sxs-lookup"><span data-stu-id="f4795-218">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime requires [!INCLUDE[dotnet45](../includes/dotnet45-md.md)].</span></span> <span data-ttu-id="f4795-219">Windows Communication Foundation (WCF) アダプターまたは WCF インターセプターをインストールする場合は、.NET Framework 3.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="f4795-219">The .NET Framework 3.0 is required if the Windows Communication Foundation (WCF) adapter or WCF Interceptor is installed.</span></span>  
  
##  <a name="BKMK_SQL"></a> <span data-ttu-id="f4795-220">SQL Server のインストール</span><span class="sxs-lookup"><span data-stu-id="f4795-220">Install SQL Server</span></span>  
 <span data-ttu-id="f4795-221">[SQL Server 2008 R2](http://msdn.microsoft.com/library/bb500395\(v=sql.105\).aspx) のインストール</span><span class="sxs-lookup"><span data-stu-id="f4795-221">Install [SQL Server 2008 R2](http://msdn.microsoft.com/library/bb500395\(v=sql.105\).aspx)</span></span>  
  
 <span data-ttu-id="f4795-222">[SQL Server 2012](http://msdn.microsoft.com/library/bb500469\(v=sql.110\).aspx) のインストール</span><span class="sxs-lookup"><span data-stu-id="f4795-222">Install [SQL Server 2012](http://msdn.microsoft.com/library/bb500469\(v=sql.110\).aspx)</span></span>  
  
 <span data-ttu-id="f4795-223">[SQL Server 2014 ](http://msdn.microsoft.com/library/bb500469\(v=sql.120\).aspx) のインストール</span><span class="sxs-lookup"><span data-stu-id="f4795-223">Install [SQL Server 2014](http://msdn.microsoft.com/library/bb500469\(v=sql.120\).aspx)</span></span>  
  
 <span data-ttu-id="f4795-224">[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] をインストールするときには、次の機能を選択します:</span><span class="sxs-lookup"><span data-stu-id="f4795-224">When you install [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], select the following features:</span></span>  
  
-   <span data-ttu-id="f4795-225">データベース エンジン サービス</span><span class="sxs-lookup"><span data-stu-id="f4795-225">Database Engine Services</span></span>  
  
    -   <span data-ttu-id="f4795-226">SQL Server のレプリケーション</span><span class="sxs-lookup"><span data-stu-id="f4795-226">SQL Server Replication</span></span>  
  
    -   <span data-ttu-id="f4795-227">フルテキスト検索</span><span class="sxs-lookup"><span data-stu-id="f4795-227">Full-Text Search</span></span>  
  
-   <span data-ttu-id="f4795-228">Analysis Services</span><span class="sxs-lookup"><span data-stu-id="f4795-228">Analysis Services</span></span>  
  
-   <span data-ttu-id="f4795-229">Reporting Services</span><span class="sxs-lookup"><span data-stu-id="f4795-229">Reporting Services</span></span>  
  
-   <span data-ttu-id="f4795-230">共有機能</span><span class="sxs-lookup"><span data-stu-id="f4795-230">Shared Features</span></span>  
  
    -   <span data-ttu-id="f4795-231">SQL Server Data Tools (SQL Server 2014 / SQL Server 2012) または Business Intelligence Development Studio (SQL Server 2008 R2)</span><span class="sxs-lookup"><span data-stu-id="f4795-231">SQL Server Data Tools (SQL Server 2014 / SQL Server 2012) or Business Intelligence Development Studio (SQL Server 2008 R2)</span></span>  
  
         [<span data-ttu-id="f4795-232">SQL Server 2014 Data Tools のダウンロード</span><span class="sxs-lookup"><span data-stu-id="f4795-232">Download SQL Server 2014 Data Tools</span></span>](http://www.microsoft.com/download/details.aspx?id=42313)  
  
    -   <span data-ttu-id="f4795-233">クライアント ツール接続</span><span class="sxs-lookup"><span data-stu-id="f4795-233">Client Tools Connectivity</span></span>  
  
    -   <span data-ttu-id="f4795-234">Integration Services</span><span class="sxs-lookup"><span data-stu-id="f4795-234">Integration Services</span></span>  
  
    -   <span data-ttu-id="f4795-235">管理ツール - 基本</span><span class="sxs-lookup"><span data-stu-id="f4795-235">Management Tools - Basic</span></span>  
  
        -   <span data-ttu-id="f4795-236">管理ツール - 完全</span><span class="sxs-lookup"><span data-stu-id="f4795-236">Management Tools - Complete</span></span>  
  
 <span data-ttu-id="f4795-237">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="f4795-237">**Additional**</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f4795-238"> では、バイナリ照合順序を除く、大文字と小文字を区別する/区別しないすべての SQL 照合順序がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f4795-238"> supports all case-sensitive and case-insensitive SQL Server collations except for binary collations.</span></span> <span data-ttu-id="f4795-239">バイナリ照合順序はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="f4795-239">Binary collations are not supported.</span></span>  
  
-   <span data-ttu-id="f4795-240">最適なパフォーマンスを得るには、SQL Server の Enterprise Edition を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f4795-240">For optimal performance, Microsoft recommends using the Enterprise Edition of SQL Server.</span></span> <span data-ttu-id="f4795-241">詳細は、「[SQL Server 2008 R2 の各エディションがサポートする機能](http://msdn.microsoft.com/library/cc645993\(v=sql.105\).aspx)」、「[SQL Server 2012 の各エディションがサポートする機能](http://msdn.microsoft.com/library/cc645993\(v=sql.110\).aspx)」または「[SQL Server 2014 の各エディションがサポートする機能](http://msdn.microsoft.com/library/cc645993\(v=sql.120\).aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f4795-241">See [SQL Server 2008 R2 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.105\).aspx), [SQL Server 2012 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.110\).aspx), or [SQL Server 2014 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.120\).aspx).</span></span>  
  
-   <span data-ttu-id="f4795-242">Service Pack および Windows Updates はいずれもサポートされており、インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4795-242">Service packs and Windows Updates are supported and should be installed.</span></span>  
  
-   <span data-ttu-id="f4795-243">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] および [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] が別のコンピューターにインストールされている場合、分散トランザクション コーディネーター (MS DTC) がコンピューター間のトランザクションを処理します。</span><span class="sxs-lookup"><span data-stu-id="f4795-243">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] are on separate computers, Distributed Transaction Coordinator (MS DTC) handles the transactions between the computers.</span></span> <span data-ttu-id="f4795-244">[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] の AlwaysOn 機能は MSDTC トランザクションをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f4795-244">The [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] AlwaysOn feature does not support MSDTC transactions.</span></span> <span data-ttu-id="f4795-245">[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] の AlwaysOn 機能はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="f4795-245">The [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] AlwaysOn feature is not supported.</span></span>  
  
##  <a name="BKMK_MQSeries"></a> <span data-ttu-id="f4795-246">MQSeries に必要なソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="f4795-246">Install MQSeries Prerequisites</span></span>  
 <span data-ttu-id="f4795-247">**MQSeries アダプター**: BizTalk Server のインストール時に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f4795-247">**MQSeries adapter**: Automatically installed with the BizTalk Server installation.</span></span>  
  
 <span data-ttu-id="f4795-248">**MQSeries Client (MQSC) アダプター**:</span><span class="sxs-lookup"><span data-stu-id="f4795-248">**MQSeries Client (MQSC) adapter**:</span></span>  
  
1.  <span data-ttu-id="f4795-249">Host Integration Server (HIS) インストールの実行</span><span class="sxs-lookup"><span data-stu-id="f4795-249">Run the Host Integration Server (HIS) installation</span></span>  
  
2.  <span data-ttu-id="f4795-250">コンポーネントのインストールで、[**BizTalk アダプター**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="f4795-250">In component installation, expand **BizTalk Adapters**.</span></span>  
  
3.  <span data-ttu-id="f4795-251">[**BizTalk Adapter for WebSphere MQ (クライアント ベース)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4795-251">Select **BizTalk Adapter for WebSphere MQ (Client-Based)**.</span></span>  
  
 <span data-ttu-id="f4795-252">**サポート対象の IBM WebSphere MQ バージョン**:</span><span class="sxs-lookup"><span data-stu-id="f4795-252">**Supported IBM WebSphere MQ versions**:</span></span>  
  
-   <span data-ttu-id="f4795-253">IBM WebSphere MQ 6.0.2.12 以降</span><span class="sxs-lookup"><span data-stu-id="f4795-253">IBM WebSphere MQ 6.0.2.12 and later</span></span>  
  
-   <span data-ttu-id="f4795-254">IBM WebSphere MQ 7.0.1.9 以降</span><span class="sxs-lookup"><span data-stu-id="f4795-254">IBM WebSphere MQ 7.0.1.9 and later</span></span>  
  
-   <span data-ttu-id="f4795-255">IBM WebSphere MQ 7.1.0.5 以降</span><span class="sxs-lookup"><span data-stu-id="f4795-255">IBM WebSphere MQ 7.1.0.5 and later</span></span>  
  
-   <span data-ttu-id="f4795-256">IBM WebSphere MQ 7.5.0.3 以降</span><span class="sxs-lookup"><span data-stu-id="f4795-256">IBM WebSphere MQ 7.5.0.3 and later</span></span>  
  
-   <span data-ttu-id="f4795-257">IBM WebSphere MQ 8 (実行時に限定。管理 API はなし)</span><span class="sxs-lookup"><span data-stu-id="f4795-257">IBM WebSphere MQ 8 (limited to runtime; no administration APIs)</span></span>  
  
     <span data-ttu-id="f4795-258">MQ バージョン 8 は [Host Integration Server CU3](https://support.microsoft.com/kb/3019572) でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f4795-258">MQ version 8 support is included with [Host Integration Server CU3](https://support.microsoft.com/kb/3019572).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4795-259">MQ 5.x など、特定の WebSphere MQ バージョンが記載されていない場合、それはこの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] バージョンでサポートされません。</span><span class="sxs-lookup"><span data-stu-id="f4795-259">If a specific WebSphere MQ version is not listed, like MQ 5.x, then it is not supported with this [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] version.</span></span>  
  
 <span data-ttu-id="f4795-260">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="f4795-260">**Additional**</span></span>  
  
-   <span data-ttu-id="f4795-261">常に最新の WebSphere MQ 修正パックをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f4795-261">As a best practice, always install the latest WebSphere MQ fix pack.</span></span> <span data-ttu-id="f4795-262">[http://www.ibm.com/support/docview.wss?uid=swg27006037](http://www.ibm.com/support/docview.wss?uid=swg27006037) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4795-262">See [http://www.ibm.com/support/docview.wss?uid=swg27006037](http://www.ibm.com/support/docview.wss?uid=swg27006037).</span></span>  
  
-   <span data-ttu-id="f4795-263">IBM WebSphere MQ が Windows 以外のコンピューターにインストールされている場合は、同じコンピューターに **MQSAgent COM+ アプリ** (MQSConfigWiz.exe) と **MQSeries Server for Windows** をインストールします。</span><span class="sxs-lookup"><span data-stu-id="f4795-263">If IBM WebSphere MQ is installed on a non-Windows computer, install the **MQSAgent COM+ application** (MQSConfigWiz.exe) and **MQSeries Server for Windows** on the same computer.</span></span> <span data-ttu-id="f4795-264">IBM WebSphere MQ が Windows コンピューターにインストールされている場合は、**MQSAgent COM+ アプリ**と **MQSeries Server for Windows** プログラムは使用することも必要になることもありません。</span><span class="sxs-lookup"><span data-stu-id="f4795-264">If IBM WebSphere MQ is installed on a Windows computer, then the **MQSAgent COM+ application** and **MQSeries Server for Windows** program are not used or needed.</span></span>  
  
     <span data-ttu-id="f4795-265">**MQSConfigWiz.exe** は [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストール ファイルに含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4795-265">**MQSConfigWiz.exe** is included in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation files.</span></span>  
  
     <span data-ttu-id="f4795-266">**MQSeries Server for Windows** はマイクロソフトのプログラムではありませんので、IBM WebSphere MQ プログラムから入手する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4795-266">**MQSeries Server for Windows** is not a Microsoft program and must be obtained with your IBM WebSphere MQ program.</span></span>  
  
-   <span data-ttu-id="f4795-267">「[MQSeries アダプター](http://technet.microsoft.com/library/aa547973\(v=BTS.80\).aspx)」には、異なるコンポーネント構成など、MQSeries アダプターに関する詳細情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="f4795-267">[MQSeries Adapter](http://technet.microsoft.com/library/aa547973\(v=BTS.80\).aspx) provides more information on the MQSeries adapter, including configuring the different components.</span></span> <span data-ttu-id="f4795-268">[BizTalk Server: 「MQSeries と MQSeries Client (MQSC) のアダプター](http://social.technet.microsoft.com/wiki/contents/articles/18316.biztalk-server-mqseries-and-mqseries-client-mqsc-adapters.aspx)」には、MQSeries と MQSC のアダプターの詳細が記載されています。</span><span class="sxs-lookup"><span data-stu-id="f4795-268">[BizTalk Server: MQSeries and MQSeries Client (MQSC) adapters](http://social.technet.microsoft.com/wiki/contents/articles/18316.biztalk-server-mqseries-and-mqseries-client-mqsc-adapters.aspx) provides additional details on the MQSeries and MQSC adapters.</span></span>  
  
-   <span data-ttu-id="f4795-269">IBM WebSphere はマイクロソフト製品ではないため、マイクロソフトによるサポートはありません。</span><span class="sxs-lookup"><span data-stu-id="f4795-269">IBM WebSphere is not a Microsoft product and is not supported by Microsoft.</span></span> <span data-ttu-id="f4795-270">マイクロソフトでは、このプログラムの適合性に関して一切の保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="f4795-270">Microsoft makes no guarantees about the suitability of this program.</span></span> <span data-ttu-id="f4795-271">IBM WebSphere MQ のダウンロード方法をはじめとする詳細については、www.ibm.com をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f4795-271">For more information about IBM WebSphere MQ, including download instructions, see www.ibm.com.</span></span>  
  
##  <a name="BKMK_BAMAlerts"></a> <span data-ttu-id="f4795-272">BAM 警告</span><span class="sxs-lookup"><span data-stu-id="f4795-272">BAM Alerts</span></span>  
 <span data-ttu-id="f4795-273">[!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)] または [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] での BAM 警告では、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] のデータベース メールを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4795-273">BAM Alerts with [!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)] or [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] uses Database Mail in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="f4795-274">[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] の BAM 警告では SQL Notification Services を使用します。</span><span class="sxs-lookup"><span data-stu-id="f4795-274">BAM Alerts with [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] uses SQL Notification Services.</span></span> <span data-ttu-id="f4795-275">BAM 警告をインストール、構成する前に、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] で通知サービスまたはデータベース メールを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4795-275">Before installing or configuring BAM Alerts, you must configure the Notification Services or Database Mail in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
###  <a name="BKMK_DBMail"></a> <span data-ttu-id="f4795-276">SQL Server 2012/2014 での BAM 警告</span><span class="sxs-lookup"><span data-stu-id="f4795-276">BAM Alerts using SQL Server 2012/2014</span></span>  
 <span data-ttu-id="f4795-277">[SQL Server 2012 データベース メールの構成](http://msdn.microsoft.com/library/hh245116\(v=sql.110\).aspx)を行います。</span><span class="sxs-lookup"><span data-stu-id="f4795-277">Configure [SQL Server 2012 Database Mail](http://msdn.microsoft.com/library/hh245116\(v=sql.110\).aspx).</span></span>  
  
 <span data-ttu-id="f4795-278">[SQL Server 2014 データベース メールの構成](http://msdn.microsoft.com/library/hh245116\(v=sql.120\).aspx)を行います。</span><span class="sxs-lookup"><span data-stu-id="f4795-278">Configure [SQL Server 2014 Database Mail](http://msdn.microsoft.com/library/hh245116\(v=sql.120\).aspx).</span></span>  
  
 <span data-ttu-id="f4795-279">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="f4795-279">**Additional**</span></span>  
  
-   <span data-ttu-id="f4795-280">データベース メールでは SMTP サーバーを使用して BAM 警告を送信します。</span><span class="sxs-lookup"><span data-stu-id="f4795-280">Database Mail uses an SMTP server to send the BAM Alerts.</span></span> <span data-ttu-id="f4795-281">SMTP サーバーはローカルで [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、または別の IIS サーバーにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="f4795-281">SMTP Server can be installed locally on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or on another IIS server.</span></span> <span data-ttu-id="f4795-282">「[付録 D: SMTP サーバーの作成](../install-and-config-guides/appendix-d-create-the-smtp-server.md)」には、SMTP サーバーのインストールおよび構成手順があります。</span><span class="sxs-lookup"><span data-stu-id="f4795-282">[Appendix D: Create the SMTP Server](../install-and-config-guides/appendix-d-create-the-smtp-server.md) lists the steps to install and configure a SMTP Server.</span></span>  
  
###  <a name="BKMK_SSNS"></a> <span data-ttu-id="f4795-283">SQL Server 2008 R2 を使用する BAM 警告 - SQL Server 2005 通知サービスのインストール</span><span class="sxs-lookup"><span data-stu-id="f4795-283">BAM Alerts using SQL Server 2008 R2 – Install SQL Server 2005 Notification Services</span></span>  
  
1.  <span data-ttu-id="f4795-284">「[Microsoft SQL Server 2005 SP4 用 Feature Pack](http://go.microsoft.com/fwlink/p/?LinkId=286285)」にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f4795-284">Go to [Feature Pack for Microsoft SQL Server 2005 SP4](http://go.microsoft.com/fwlink/p/?LinkId=286285).</span></span>  
  
2.  <span data-ttu-id="f4795-285">次のコンポーネントに適したプラットフォーム パッケージをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="f4795-285">Download and install the appropriate platform package for the following components:</span></span>  
  
     <span data-ttu-id="f4795-286">**Microsoft SQL Server Native Client**</span><span class="sxs-lookup"><span data-stu-id="f4795-286">**Microsoft SQL Server Native Client**</span></span>  
  
    -   <span data-ttu-id="f4795-287">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli.msi" X86 Package (sqlncli.msi)</span><span class="sxs-lookup"><span data-stu-id="f4795-287">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli.msi" X86 Package (sqlncli.msi)</span></span>  
  
    -   <span data-ttu-id="f4795-288">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli_x64.msi" X64 Package (sqlncli_x64.msi)</span><span class="sxs-lookup"><span data-stu-id="f4795-288">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli_x64.msi" X64 Package (sqlncli_x64.msi)</span></span>  
  
     <span data-ttu-id="f4795-289">**Microsoft SQL Server 2005 管理オブジェクト コレクション**</span><span class="sxs-lookup"><span data-stu-id="f4795-289">**Microsoft SQL Server 2005 Management Objects Collection**</span></span>  
  
    -   <span data-ttu-id="f4795-290">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO.msi" X86 Package (SQLServer2005_XMO.msi)</span><span class="sxs-lookup"><span data-stu-id="f4795-290">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO.msi" X86 Package (SQLServer2005_XMO.msi)</span></span>  
  
    -   <span data-ttu-id="f4795-291">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO_x64.msi" X64 Package (SQLServer2005_XMO_x64.msi)</span><span class="sxs-lookup"><span data-stu-id="f4795-291">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO_x64.msi" X64 Package (SQLServer2005_XMO_x64.msi)</span></span>  
  
     <span data-ttu-id="f4795-292">**Microsoft SQL Server 2005 Notification Services クライアント コンポーネント**</span><span class="sxs-lookup"><span data-stu-id="f4795-292">**Microsoft SQL Server 2005 Notification Services Client Components**</span></span>  
  
    -   <span data-ttu-id="f4795-293">HYPERLINK"http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS.msi"X86 パッケージ (SQLServer2005_NS.msi)</span><span class="sxs-lookup"><span data-stu-id="f4795-293">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS.msi" X86 Package (SQLServer2005_NS.msi)</span></span>  
  
    -   <span data-ttu-id="f4795-294">HYPERLINK"http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS_x64.msi"X64 パッケージ (SQLServer2005_NS_x64.msi)</span><span class="sxs-lookup"><span data-stu-id="f4795-294">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS_x64.msi" X64 Package (SQLServer2005_NS_x64.msi)</span></span>  
  
 <span data-ttu-id="f4795-295">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="f4795-295">**Additional**</span></span>  
  
-   <span data-ttu-id="f4795-296">SQL Notification Services を構成する必要はありません。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にインストールするだけです。</span><span class="sxs-lookup"><span data-stu-id="f4795-296">SQL Notification Services does not need to be configured; only installed on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
##  <a name="BKMK_WIF"></a> <span data-ttu-id="f4795-297">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="f4795-297">Windows Identity Foundation</span></span>  
  
|||  
|-|-|  
|[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]<span data-ttu-id="f4795-298"> 8.1、[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]、[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2</span><span class="sxs-lookup"><span data-stu-id="f4795-298"> 8.1, [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)], and [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2</span></span>|<span data-ttu-id="f4795-299">Windows Identity Foundation は [**Windows の機能の有効化または無効化**] に表示される機能としてオペレーティング システムに含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4795-299">Windows Identity Foundation is included with the operating system as a Feature in **Turn Windows features on or off**.</span></span>|  
|[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]<span data-ttu-id="f4795-300"> SP1</span><span class="sxs-lookup"><span data-stu-id="f4795-300"> SP1</span></span>|<span data-ttu-id="f4795-301">「[Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331) HYPERLINK "http://www.microsoft.com/download/details.aspx?id=17331"」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="f4795-301">Download available at [Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331) HYPERLINK "http://www.microsoft.com/download/details.aspx?id=17331" .</span></span>|  
  
 <span data-ttu-id="f4795-302">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="f4795-302">**Additional**</span></span>  
  
-   <span data-ttu-id="f4795-303">Windows Identity Foundation (WIF) は、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] アダプターまたは SharePoint Online で、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] クライアント側オブジェクト モデル (CSOM) と共に使用する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="f4795-303">Windows Identity Foundation (WIF) is required for the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] adapter or SharePoint Online when used with [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Client Side Object Model (CSOM).</span></span> <span data-ttu-id="f4795-304">具体的な内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f4795-304">Specifically:</span></span>  
  
    |<span data-ttu-id="f4795-305">インストール オプション</span><span class="sxs-lookup"><span data-stu-id="f4795-305">Installation Option</span></span>|<span data-ttu-id="f4795-306">WIF が必要</span><span class="sxs-lookup"><span data-stu-id="f4795-306">WIF Required</span></span>|  
    |-------------------------|------------------|  
    |[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]<span data-ttu-id="f4795-307"> CSOM を使用したアダプター</span><span class="sxs-lookup"><span data-stu-id="f4795-307"> Adapter with CSOM</span></span>|<span data-ttu-id="f4795-308">可</span><span class="sxs-lookup"><span data-stu-id="f4795-308">Yes</span></span>|  
    |<span data-ttu-id="f4795-309">CSOM を使用した SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f4795-309">SharePoint Online with CSOM</span></span>|<span data-ttu-id="f4795-310">必要</span><span class="sxs-lookup"><span data-stu-id="f4795-310">Yes</span></span>|  
    |[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]<span data-ttu-id="f4795-311"> アダプター Web サービス (廃止)</span><span class="sxs-lookup"><span data-stu-id="f4795-311"> Adapter Web Service (deprecated)</span></span>|<span data-ttu-id="f4795-312">不可</span><span class="sxs-lookup"><span data-stu-id="f4795-312">No</span></span>|  
    |<span data-ttu-id="f4795-313">SharePoint なし</span><span class="sxs-lookup"><span data-stu-id="f4795-313">No SharePoint</span></span>|<span data-ttu-id="f4795-314">不可</span><span class="sxs-lookup"><span data-stu-id="f4795-314">No</span></span>|  
  
-   <span data-ttu-id="f4795-315">「[付録 B: Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)」には、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] の具体的なインストール オプションの情報があります。</span><span class="sxs-lookup"><span data-stu-id="f4795-315">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) provides specific information on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] installation options.</span></span>  
  
##  <a name="BKMK_WSS"></a> <span data-ttu-id="f4795-316">Microsoft SharePoint のインストールと構成</span><span class="sxs-lookup"><span data-stu-id="f4795-316">Install and Configure Microsoft SharePoint</span></span>  
 <span data-ttu-id="f4795-317">[SharePoint 2013](http://technet.microsoft.com/library/cc303424.aspx) をインストールする</span><span class="sxs-lookup"><span data-stu-id="f4795-317">Install [SharePoint 2013](http://technet.microsoft.com/library/cc303424.aspx)</span></span>  
  
 <span data-ttu-id="f4795-318">[SharePoint Online Service](http://technet.microsoft.com/library/jj819267.aspx) をインストールする</span><span class="sxs-lookup"><span data-stu-id="f4795-318">Install [SharePoint Online Service](http://technet.microsoft.com/library/jj819267.aspx)</span></span>  
  
 <span data-ttu-id="f4795-319">[SharePoint Server 2010](http://technet.microsoft.com/library/cc303424\(v=office.14\).aspx) をインストールする</span><span class="sxs-lookup"><span data-stu-id="f4795-319">Install [SharePoint Server 2010](http://technet.microsoft.com/library/cc303424\(v=office.14\).aspx)</span></span>  
  
 <span data-ttu-id="f4795-320">[SharePoint 2007](http://technet.microsoft.com/library/cc303424\(v=office.12\).aspx) をインストールする</span><span class="sxs-lookup"><span data-stu-id="f4795-320">Install [SharePoint 2007](http://technet.microsoft.com/library/cc303424\(v=office.12\).aspx)</span></span>  
  
 <span data-ttu-id="f4795-321">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="f4795-321">**Additional**</span></span>  
  
-   <span data-ttu-id="f4795-322">SharePoint は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の動作に必要な他のソフトウェアよりも前にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4795-322">If you are installing SharePoint, you must do so before continuing with the remaining [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] prerequisites.</span></span>  
  
-   <span data-ttu-id="f4795-323">SharePoint のインストールと構成の手順は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f4795-323">Installing and configuring SharePoint consists of the following procedures:</span></span>  
  
    -   <span data-ttu-id="f4795-324">SharePoint をインストールする</span><span class="sxs-lookup"><span data-stu-id="f4795-324">Install SharePoint</span></span>  
  
    -   <span data-ttu-id="f4795-325">SharePoint を構成する</span><span class="sxs-lookup"><span data-stu-id="f4795-325">Configure SharePoint</span></span>  
  
    -   <span data-ttu-id="f4795-326">既定の Web サイトを仮想サーバーとして拡張する</span><span class="sxs-lookup"><span data-stu-id="f4795-326">Extend the default Web site as a virtual server</span></span>  
  
-   <span data-ttu-id="f4795-327">「[付録 B: Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)」には、BizTalk Server の SharePoint アダプターのインストール オプションに関する情報があります。</span><span class="sxs-lookup"><span data-stu-id="f4795-327">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) describes the SharePoint adapter installation options for BizTalk Server.</span></span>  
  
-   <span data-ttu-id="f4795-328">SharePoint アダプターを使用する際は、SharePoint サービスの Web サービスの代わりに新しい CSOM オプションをインストールすることをお勧めします。詳細は「[付録 B: Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f4795-328">When using the SharePoint adapter, it is recommended to install the new CSOM option instead of the SharePoint Service Web Service; described at [Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md).</span></span>  
  
##  <a name="BKMK_SharedMem"></a> <span data-ttu-id="f4795-329">共有メモリ プロトコルの無効化</span><span class="sxs-lookup"><span data-stu-id="f4795-329">Disable the Shared Memory Protocol</span></span>  
  
1.  <span data-ttu-id="f4795-330">[**SQL Server 構成マネージャー**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="f4795-330">Open **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="f4795-331">**SQL Server 構成マネージャー**で、[**SQL Server ネットワークの構成**] を展開して [**MSSQLSERVER のプロトコル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4795-331">In **SQL Server Configuration Manager**, expand **SQL Server Network Configuration**, and then select **Protocols for MSSQLSERVER**.</span></span>  
  
3.  <span data-ttu-id="f4795-332">[**共有メモリ**] を右クリックし、[**無効**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4795-332">Right-click **Shared Memory**, and then select **Disable**.</span></span>  
  
4.  <span data-ttu-id="f4795-333">[**SQL Server サービス**] を選択し、[**SQL Server (MSSQLSERVER)**] を右クリックして、[**停止**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4795-333">Select **SQL Server Services**, right-click **SQL Server (MSSQLSERVER)**, and then select **Stop**.</span></span> <span data-ttu-id="f4795-334">サービスが停止したら、[**SQL Server (MSSQLSERVER)**] をもう一度右クリックして [**開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4795-334">After the service has stopped, right-click **SQL Server (MSSQLSERVER)** again, and then select **Start**.</span></span>  
  
5.  <span data-ttu-id="f4795-335">**SQL Server 構成マネージャー**を終了します。</span><span class="sxs-lookup"><span data-stu-id="f4795-335">Close **SQL Server Configuration Manager**.</span></span>  
  
 <span data-ttu-id="f4795-336">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="f4795-336">**Additional**</span></span>  
  
-   <span data-ttu-id="f4795-337">ある種のストレス条件下では (たとえば、同じコンピューターから複数のクライアントが SQL Server にアクセスしている場合)、SQL Server の共有メモリ プロトコルが原因で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のパフォーマンスが低下することがあります。</span><span class="sxs-lookup"><span data-stu-id="f4795-337">Under certain stress conditions (such as clients accessing SQL Server from the same computer), the SQL Server Shared Memory protocol may lower [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance.</span></span> <span data-ttu-id="f4795-338">この動作を解決するには、共有メモリ ネットワーク プロトコルを無効にするよう SQL Server ネットワークの構成で設定します。</span><span class="sxs-lookup"><span data-stu-id="f4795-338">You can resolve this behavior by disabling the Shared Memory network protocol in SQL Server Network Configuration.</span></span>  
  
-   <span data-ttu-id="f4795-339">ReplaceThisText</span><span class="sxs-lookup"><span data-stu-id="f4795-339">ReplaceThisText</span></span>  
  
##  <a name="BKMK_LocalAdmin"></a><span data-ttu-id="f4795-340">ローカルの Administrators グループへの参加</span><span class="sxs-lookup"><span data-stu-id="f4795-340">Join the Local Administrators Group</span></span>  
 <span data-ttu-id="f4795-341">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]** : [Windows Server 2012: ローカル管理者グループにアカウントを追加する方法](http://social.technet.microsoft.com/wiki/contents/articles/13436.windows-server-2012-how-to-add-an-account-to-a-local-administrator-group.aspx)</span><span class="sxs-lookup"><span data-stu-id="f4795-341">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]** : [Windows Server 2012: How to Add an Account to a Local Administrator Group](http://social.technet.microsoft.com/wiki/contents/articles/13436.windows-server-2012-how-to-add-an-account-to-a-local-administrator-group.aspx)</span></span>  
  
 <span data-ttu-id="f4795-342">**Windows 8.1**: Windows 8 でローカルのユーザーとグループを開くには、キーボードの Windows ボタンをクリックして「**グループ**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="f4795-342">**Windows 8.1**: To open Local Users and Groups on Windows 8, click the Windows button on the keyboard and type **groups**.</span></span> <span data-ttu-id="f4795-343">[検索] ウィンドウで、[**設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-343">In the Search window, click **Settings**.</span></span> <span data-ttu-id="f4795-344">[検索結果] ウィンドウで、[**ローカル ユーザーとグループの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-344">In the Results window, click **Edit local users and groups**.</span></span> <span data-ttu-id="f4795-345">[**グループ**] をクリックし、[Administrators] をダブルクリックしてアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="f4795-345">Click **Groups** and then double-click Administrators to add an account.</span></span>  
  
 <span data-ttu-id="f4795-346">**Windows 7 SP1**: [スタート] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-346">**Windows 7 SP1**: Click Start.</span></span> <span data-ttu-id="f4795-347">[**検索**] テキスト ボックスに「**コンピューターの管理**」と入力し、クリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="f4795-347">In the **Search** text box, type **Computer Management**, and click it to open.</span></span> <span data-ttu-id="f4795-348">[**ローカル ユーザーとグループ**] を展開し、[**グループ**] をクリックしてから [Administrator] をダブルクリックしてアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="f4795-348">Expand **Local Users and Groups**, click **Groups**, and then double-click Administrators to add an account.</span></span>  
  
 <span data-ttu-id="f4795-349">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="f4795-349">**Additional**</span></span>  
  
-   <span data-ttu-id="f4795-350">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストール、構成するには、ローカル管理者グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4795-350">You must be a member of the local Administrators group to install and configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
##  <a name="BKMK_AppLog"></a> <span data-ttu-id="f4795-351">アプリケーション イベント ログの構成</span><span class="sxs-lookup"><span data-stu-id="f4795-351">Configure the Application Event Log</span></span>  
  
1.  <span data-ttu-id="f4795-352">**イベント ビューアー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="f4795-352">Open **Event Viewer**:</span></span>  
  
     <span data-ttu-id="f4795-353">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]**: キーボードの Windows ボタンをクリックして「**イベント ビューアー**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="f4795-353">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]** : Click the Windows button on the keyboard and type **Event Viewer**.</span></span> <span data-ttu-id="f4795-354">[検索結果] ウィンドウで、[**イベント ビューアー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-354">In the Results window, click **Event Viewer**.</span></span>  
  
     <span data-ttu-id="f4795-355">**Windows 8.1**: キーボードの Windows ボタンをクリックして「**イベント ビューアー**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="f4795-355">**Windows 8.1**: Click the Windows button on the keyboard and type **Event Viewer**.</span></span> <span data-ttu-id="f4795-356">[検索] ウィンドウで、[**設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-356">In the Search window, click **Settings**.</span></span> <span data-ttu-id="f4795-357">[検索結果] ウィンドウで、[**イベント ログの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-357">In the Results window, click **View event logs**.</span></span>  
  
     <span data-ttu-id="f4795-358">**Windows 7 SP1**: [スタート] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-358">**Windows 7 SP1**: Click Start.</span></span> <span data-ttu-id="f4795-359">[**検索**] テキスト ボックスに**「イベント ビューアー」**と入力し、クリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="f4795-359">In the **Search** text box, type **Event Viewer**, and click it to open.</span></span>  
  
2.  <span data-ttu-id="f4795-360">[**Windows ログ**] を展開し、[**アプリケーション**] を右クリックして [**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4795-360">Expand **Windows Logs**, right-click **Application**, and then click **Properties**.</span></span> <span data-ttu-id="f4795-361">[**ログのプロパティ**]:</span><span class="sxs-lookup"><span data-stu-id="f4795-361">In **Log Properties**:</span></span>  
  
    -   <span data-ttu-id="f4795-362">使用可能な空き領域を確認するには、[**ログ サイズ**] と [**最大ログ サイズ**] のプロパティを比較します。</span><span class="sxs-lookup"><span data-stu-id="f4795-362">To determine the available space, compare the **Log Size** and the **Maximum log size** properties.</span></span>  
  
    -   <span data-ttu-id="f4795-363">空き領域を増やすには、[**最大ログ サイズ**] の数値を増やします。</span><span class="sxs-lookup"><span data-stu-id="f4795-363">To provide more space, enter a higher number in **Maximum log size**.</span></span>  
  
    -   <span data-ttu-id="f4795-364">ログの空き領域がなくなったときに古いイベントが上書きされるようにするには、[**必要に応じてイベントを上書きする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4795-364">To enable overwriting of old events when the log becomes full, select **Overwrite events as needed**.</span></span>  
  
    -   <span data-ttu-id="f4795-365">ログ イベントを消去するには、[**ログの消去**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4795-365">To clear the log events, select **Clear log**.</span></span>  
  
3.  <span data-ttu-id="f4795-366">[**OK**] をクリックして [**イベント ビューアー**] を閉じます。</span><span class="sxs-lookup"><span data-stu-id="f4795-366">Click **OK** to close the **Event Viewer**.</span></span>  
  
 <span data-ttu-id="f4795-367">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="f4795-367">**Additional**</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f4795-368"> のセットアップを実行すると、イベントの記録がアプリケーション イベント ログに保存されます。</span><span class="sxs-lookup"><span data-stu-id="f4795-368"> setup keeps a record of events in the Application Event Log.</span></span> <span data-ttu-id="f4795-369">インストールされる [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の機能によっては、ログの空き領域を超える大きさのログが作成されることもあります。</span><span class="sxs-lookup"><span data-stu-id="f4795-369">Depending on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features installed, the amount of space required in the log may exceed its limit.</span></span> <span data-ttu-id="f4795-370">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のセットアップ中にアプリケーション イベント ログの領域が不足すると、インストールは失敗します。</span><span class="sxs-lookup"><span data-stu-id="f4795-370">If the application event log runs out of space during [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup, the installation fails.</span></span> <span data-ttu-id="f4795-371">アプリケーション イベント ログの設定を変更すれば、この失敗を回避できます。</span><span class="sxs-lookup"><span data-stu-id="f4795-371">Changing the Application Event Log settings prevents this failure.</span></span>  
  
## <a name="next"></a><span data-ttu-id="f4795-372">Next</span><span class="sxs-lookup"><span data-stu-id="f4795-372">Next</span></span>  
 [<span data-ttu-id="f4795-373">BizTalk Server の機能とコンポーネントの選択</span><span class="sxs-lookup"><span data-stu-id="f4795-373">Choose BizTalk Server Features and Components</span></span>](http://msdn.microsoft.com/library/b8c43fcf-9e5c-48ba-830b-13a5177e30f0)  
  
## <a name="see-also"></a><span data-ttu-id="f4795-374">参照</span><span class="sxs-lookup"><span data-stu-id="f4795-374">See Also</span></span>  
 <span data-ttu-id="f4795-375">[BizTalk Server 2013 および 2013 R2 のインストール概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span><span class="sxs-lookup"><span data-stu-id="f4795-375">[Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span></span>  
 <span data-ttu-id="f4795-376">[付録 A: サイレント インストール](../install-and-config-guides/appendix-a-silent-installation.md) </span><span class="sxs-lookup"><span data-stu-id="f4795-376">[Appendix A: Silent Installation](../install-and-config-guides/appendix-a-silent-installation.md) </span></span>  
 <span data-ttu-id="f4795-377">[付録 B: Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="f4795-377">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) </span></span>  
 <span data-ttu-id="f4795-378">[付録 C: 再配布可能な CAB ファイル](../install-and-config-guides/appendix-c-redistributable-cab-files.md) </span><span class="sxs-lookup"><span data-stu-id="f4795-378">[Appendix C: Redistributable CAB Files](../install-and-config-guides/appendix-c-redistributable-cab-files.md) </span></span>  
 [<span data-ttu-id="f4795-379">付録 D: SMTP サーバーの作成</span><span class="sxs-lookup"><span data-stu-id="f4795-379">Appendix D: Create the SMTP Server</span></span>](../install-and-config-guides/appendix-d-create-the-smtp-server.md)
