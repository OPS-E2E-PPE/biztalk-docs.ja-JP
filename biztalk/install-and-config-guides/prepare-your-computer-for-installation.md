---
title: コンピューターのインストールの準備 |Microsoft Docs
ms.custom: ''
ms.date: 03/15/2016
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53df7a2f-638b-4921-a97f-736760248526
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bba64728220eb2fc5be99153892d68e93eb8e22c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017208"
---
# <a name="prepare-your-computer-for-installation"></a><span data-ttu-id="8c5dc-102">インストールのためのコンピューターの準備</span><span class="sxs-lookup"><span data-stu-id="8c5dc-102">Prepare Your Computer for Installation</span></span>
<span data-ttu-id="8c5dc-103">ここでは、コンピューターの準備を整える手順について説明します。必要なソフトウェアをすべてインストールして構成し、アカウントを作成してアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-103">This topic lists the steps to prepare your computer by installing and configuring all software prerequisites, and then creating accounts and setting permissions.</span></span>  

> [!TIP] 
> <span data-ttu-id="8c5dc-104">統合に詳しいユーザーが、前提条件と BizTalk Server をインストールするとても詳細な手順が説明された「[BizTalk 2013 Installation and Configuration part 1](http://sandroaspbiztalkblog.wordpress.com/2013/05/05/biztalk-2013-installation-and-configuration-important-considerations-before-set-up-the-server-part-1/)」 (BizTalk 2013 のインストールおよび構成パート 1) を用意しました。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-104">An integration MVP prepared a very detailed step-by-step guide to install the prerequisites, and BizTalk Server:  [BizTalk 2013 Installation and Configuration part 1](http://sandroaspbiztalkblog.wordpress.com/2013/05/05/biztalk-2013-installation-and-configuration-important-considerations-before-set-up-the-server-part-1/).</span></span>  
> 
> <span data-ttu-id="8c5dc-105">ユーザー アクセス制御 (UAC) や Windows ファイアウォールの無効化など、いくつかの手順はマイクロソフトでは推奨していません。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-105">Some steps are not recommended by Microsoft, such as disabling User Access Control (UAC) or Windows Firewall.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="8c5dc-106">ここに示している順序どおりに作業は実行してください。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-106">Complete these tasks in the order listed.</span></span>  
  
##  <a name="BKMK_InstUpdates"></a> <span data-ttu-id="8c5dc-107">Windows の更新プログラムをインストールする</span><span class="sxs-lookup"><span data-stu-id="8c5dc-107">Install Windows Updates</span></span>  
  
- <span data-ttu-id="8c5dc-108">**Windows 7**: [スタート] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-108">**Windows 7**: Click Start.</span></span> <span data-ttu-id="8c5dc-109">**[検索]** テキスト ボックスで、「**Windows Update**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-109">In the **Search** text box, type **Windows Update**.</span></span>  
  
- <span data-ttu-id="8c5dc-110">**Windows 8.1、Windows Server 2012、および Windows Server 2012 R2**: キーボードの Windows ボタンをクリックします。 **Windows Update**します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-110">**Windows 8.1, Windows Server 2012, and Windows Server 2012 R2**: Click the Windows button on the keyboard and type **Windows Update**.</span></span> <span data-ttu-id="8c5dc-111">検索結果] ウィンドウで、**[Windows Update]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-111">From the search results, click **Windows Update**.</span></span>  
  
  <span data-ttu-id="8c5dc-112">更新プログラムのインストール後、コンピューターを再起動する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-112">After installing updates, you may need to restart the computer.</span></span>  
  
##  <a name="BKMK_IIS"></a> <span data-ttu-id="8c5dc-113">インターネット インフォメーション サービス (IIS) の有効化</span><span class="sxs-lookup"><span data-stu-id="8c5dc-113">Enable Internet Information Services</span></span>  
 <span data-ttu-id="8c5dc-114">Microsoft インターネット インフォメーション サービス (IIS) など、多くの BizTalk Server 機能の Web アプリケーション インフラストラクチャを提供します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-114">Microsoft Internet Information Services (IIS) provides a Web application infrastructure for many BizTalk Server features, including:</span></span>  
  
-   <span data-ttu-id="8c5dc-115">HTTP アダプター</span><span class="sxs-lookup"><span data-stu-id="8c5dc-115">HTTP adapter</span></span>  
  
-   <span data-ttu-id="8c5dc-116">SOAP アダプター</span><span class="sxs-lookup"><span data-stu-id="8c5dc-116">SOAP adapter</span></span>  
  
-   <span data-ttu-id="8c5dc-117">Windows SharePoint Services アダプター</span><span class="sxs-lookup"><span data-stu-id="8c5dc-117">Windows SharePoint Services adapter</span></span>  
  
-   <span data-ttu-id="8c5dc-118">SSL (Secure Sockets Layer) 暗号化</span><span class="sxs-lookup"><span data-stu-id="8c5dc-118">Secure Sockets Layer (SSL) encryption</span></span>  
  
-   <span data-ttu-id="8c5dc-119">BAM ポータル</span><span class="sxs-lookup"><span data-stu-id="8c5dc-119">BAM Portal</span></span>  
  
#### <a name="install-iis"></a><span data-ttu-id="8c5dc-120">IIS をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-120">Install IIS</span></span>

<span data-ttu-id="8c5dc-121">特定のインストールの手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-121">For the specific install steps, see:</span></span> 

[<span data-ttu-id="8c5dc-122">IIS (Windows 8 および Windows Server 2012) のインストールします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-122">Install IIS (Windows 8 and Windows Server 2012)</span></span>](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/installing-iis-8-on-windows-server-2012)

[<span data-ttu-id="8c5dc-123">IIS (Windows 7 および Windows Vista) のインストールします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-123">Install IIS (Windows 7 and Windows Vista)</span></span>](https://docs.microsoft.com/iis/install/installing-iis-7/installing-iis-on-windows-vista-and-windows-7)


<span data-ttu-id="8c5dc-124">既定のチェックのオプションに加えて、IIS をインストールするときに、次も確認します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-124">When you install IIS, in addition to the default checked options, also check the following:</span></span>  
  
- <span data-ttu-id="8c5dc-125">**[Web 管理ツール]**: 次の項目もオンにします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-125">**Web Management Tools**: Also check:</span></span>  
  
    - <span data-ttu-id="8c5dc-126">IIS 6 管理互換:</span><span class="sxs-lookup"><span data-stu-id="8c5dc-126">IIS 6 Management Compatibility:</span></span>  
  
        - <span data-ttu-id="8c5dc-127">IIS 6 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="8c5dc-127">IIS 6 Management Console</span></span>  
  
        - <span data-ttu-id="8c5dc-128">IIS メタベースおよび IIS 6 構成との互換性</span><span class="sxs-lookup"><span data-stu-id="8c5dc-128">IIS Metabase and IIS 6 configuration compatibility</span></span>  
  
    - <span data-ttu-id="8c5dc-129">IIS 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="8c5dc-129">IIS Management Console</span></span>  
  
- <span data-ttu-id="8c5dc-130">**[World Wide Web サービス]**: **[セキュリティ]** を展開し、次も選択します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-130">**World Wide Web Services**: Expand **Security** and also select:</span></span>  
  
    - <span data-ttu-id="8c5dc-131">基本認証</span><span class="sxs-lookup"><span data-stu-id="8c5dc-131">Basic Authentication</span></span>  
  
    - <span data-ttu-id="8c5dc-132">[Windows 認証]</span><span class="sxs-lookup"><span data-stu-id="8c5dc-132">Windows Authentication</span></span>  

<span data-ttu-id="8c5dc-133">次のことも考慮してください。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-133">Also consider the following:</span></span>  
  
- <span data-ttu-id="8c5dc-134">**.Net framework 3.5 の機能**: .NET Framework 4.5 と .NET Framework 3.5 は、BizTalk Adapter Pack を使用する .Net アプリケーションを開発に使用できます。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-134">**.Net Framework 3.5 Features**: .NET Framework 4.5 and .NET Framework 3.5 can be used to develop .Net applications involving the BizTalk Adapter Pack.</span></span> <span data-ttu-id="8c5dc-135">通常、 **.NET Framework 4.5 機能**が既にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-135">Typically, **.NET Framework 4.5 Features** is already installed.</span></span> <span data-ttu-id="8c5dc-136">このコンピューターで、アプリケーションを作成する .NET Framework 3.5 を使用する場合 **.Net Framework 3.5 の機能**もインストールできます。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-136">If you will use .NET Framework 3.5 to create applications on this computer, then **.Net Framework 3.5 Features** can also be installed.</span></span>  
  
- <span data-ttu-id="8c5dc-137">**メッセージ キュー**: MSMQ アダプターを使用する場合は、**[メッセージ キュー]** をオンにしてローカルの MSMQ ストアを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-137">**Message Queuing**: If you are using the MSMQ adapter, you can create a local MSMQ store by checking **Message Queuing**.</span></span>  
  
- <span data-ttu-id="8c5dc-138">**SMTP サーバー**: SMTP アダプターを使用する場合は、**[SMTP サーバー]** をオンにしてローカルの SMTP サーバーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-138">**SMTP Server**: If you are using the SMTP adapter, you can create a local SMTP Server by checking **SMTP Server**.</span></span>  
  
- <span data-ttu-id="8c5dc-139">**Windows Identity Foundation 3.5**: CSOM インストール オプションを使用する場合に、SharePoint アダプターによって Windows Identity Foundation (WIF) が必要です。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-139">**Windows Identity Foundation 3.5**: Windows Identity Foundation (WIF) is required by the SharePoint adapter when using the CSOM installation option.</span></span> <span data-ttu-id="8c5dc-140">[付録 b: Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)SharePoint アダプターの CSOM インストール オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-140">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) describes the CSOM installation option for the SharePoint adapter.</span></span>    
  
 
##  <a name="BKMK_XLS"></a> <span data-ttu-id="8c5dc-141">Microsoft Office Excel のインストール</span><span class="sxs-lookup"><span data-stu-id="8c5dc-141">Install Microsoft Office Excel</span></span>  
  
1. <span data-ttu-id="8c5dc-142">Microsoft Office のセットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-142">Run the Microsoft Office setup.</span></span>  
  
2. <span data-ttu-id="8c5dc-143">**[インストールの種類]** 画面が表示されたら、**[カスタム インストール]** を選択し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-143">When you reach the **Type of Installation** screen, select **Custom Install**, and then select **Next**.</span></span>  
  
3. <span data-ttu-id="8c5dc-144">**[カスタム セットアップ]** 画面で、**[Excel]** を選択し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-144">On the **Custom Setup** screen, select **Excel**, and then select **Next**.</span></span>  
  
4. <span data-ttu-id="8c5dc-145">**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-145">Select **Install**.</span></span>  
  
5. <span data-ttu-id="8c5dc-146">**[セットアップが完了しました]** 画面で、**[終了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-146">In **Setup Completed**, select **Finish**.</span></span>  
  
   <span data-ttu-id="8c5dc-147">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="8c5dc-147">**Additional**</span></span>  
  
-   <span data-ttu-id="8c5dc-148">BizTalk Server は、32 ビット版の Microsoft Office のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-148">BizTalk Server supports only 32-bit version of Microsoft Office.</span></span>  
  
-   <span data-ttu-id="8c5dc-149">Microsoft Office Excel でビジネス アクティビティ監視 (BAM) では、BizTalk Server が必要です。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-149">Microsoft Office Excel is required by Business Activity Monitoring (BAM) in BizTalk Server.</span></span> <span data-ttu-id="8c5dc-150">BAM の Office Excel では、監視するビジネス プロセスを定義します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-150">The BAM Office Excel Workbook defines the business processes you want to monitor.</span></span> <span data-ttu-id="8c5dc-151">この BAM Excel ブックでは、BAM によって収集されたデータをどのようにビジネス ユーザーの画面に表示するかを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-151">You also use the BAM Excel Workbook to define the way business users see the data collected by BAM.</span></span>  
  
-   <span data-ttu-id="8c5dc-152">BAM.xla を Excel に正しく読み込むには、**[Office 共有機能]** の下の **[Visual Basic for Applications]** をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-152">To successfully load BAM.xla into Excel, install **Visual Basic for Applications** under **Office Shared Features**.</span></span> <span data-ttu-id="8c5dc-153">これを行わない場合は、「このブックにある、VBA プロジェクト、ActiveX コントロール、およびその他のプログラミング関連の機能は失われています。」というエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-153">Otherwise, you may get error “This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.”</span></span>  
  
##  <a name="BKMK_VS"></a> <span data-ttu-id="8c5dc-154">Visual Studio のインストール</span><span class="sxs-lookup"><span data-stu-id="8c5dc-154">Install Visual Studio</span></span>  
  
1. <span data-ttu-id="8c5dc-155">Visual Studio のセットアップを管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-155">Run the Visual Studio setup as Administrator.</span></span>  
  
2. <span data-ttu-id="8c5dc-156">ライセンス契約に同意して、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-156">Accept the license agreement and click **Next**.</span></span>  
  
3. <span data-ttu-id="8c5dc-157">**[インストールするオプション機能]** で必要なオプションを選択し、**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-157">In **Optional features to install**, select the options you need and then select **Install**.</span></span> <span data-ttu-id="8c5dc-158">BizTalk Server は、オプション機能を必要としません。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-158">BizTalk Server does not require any of the optional features.</span></span>  
  
4. <span data-ttu-id="8c5dc-159">**[完了]** ページで、ウィンドウを閉じるか **[起動]** をクリックして Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-159">On the **Finish** page, close the window or click **Launch** to open Visual Studio.</span></span>  
  
   <span data-ttu-id="8c5dc-160">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="8c5dc-160">**Additional**</span></span>  
  
-   <span data-ttu-id="8c5dc-161">BizTalk Server をインストールする前に Visual Studio をインストールして、Visual Studio チーム エクスプ ローラーにアップグレードし、する必要がありますから BizTalk Server インストールを修復する場合、**コントロール パネルの ** / **プログラム**オプション。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-161">If you install Visual Studio before installing BizTalk Server, and then upgrade to Visual Studio Team Explorer, you may need to repair your BizTalk Server installation from the **Control Panel** / **Programs** option.</span></span>  
  
-   <span data-ttu-id="8c5dc-162">Visual Studio では、Microsoft SQL Server Express は自動的にインストールされますが、BizTalk Server では使用しません。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-162">Visual Studio automatically installs Microsoft SQL Server Express; which is not used by BizTalk Server.</span></span> <span data-ttu-id="8c5dc-163">Microsoft SQL Server Express をアンインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-163">As a best practice, uninstall Microsoft SQL Server Express.</span></span>  
  
-   <span data-ttu-id="8c5dc-164">BizTalk Server 開発ツールは、Visual Studio をベースとして動作します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-164">The BizTalk Server development tools are based on Visual Studio.</span></span> <span data-ttu-id="8c5dc-165">少なくとも、BizTalk Server をインストールする前に、Visual Studio の Microsoft Visual c#® .NET コンポーネントをインストールする必要があります**開発ツールおよび SDK**します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-165">At a minimum, you must install the Microsoft Visual C#® .NET component of Visual Studio before you install the BizTalk Server**Developer Tools and SDK**.</span></span>  
  
-   <span data-ttu-id="8c5dc-166">Visual Studio は*いない*アプリケーション開発やデバッグが必要な実稼働コンピューター (ランタイムのみ)、BizTalk Server をインストールするかどうかに必要な。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-166">Visual Studio is *not* required if you are installing BizTalk Server on a production computer (runtime only), on which no application development or debugging is required.</span></span>  
  
-   <span data-ttu-id="8c5dc-167">BizTalk Server ランタイムでは、.NET Framework 4.5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-167">The BizTalk Server runtime requires .NET Framework 4.5.</span></span> <span data-ttu-id="8c5dc-168">Windows Communication Foundation (WCF) アダプターまたは WCF インターセプターをインストールする場合は、.NET Framework 3.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-168">The .NET Framework 3.0 is required if the Windows Communication Foundation (WCF) adapter or WCF Interceptor is installed.</span></span>  
  
##  <a name="BKMK_SQL"></a> <span data-ttu-id="8c5dc-169">SQL Server のインストール</span><span class="sxs-lookup"><span data-stu-id="8c5dc-169">Install SQL Server</span></span>  
 <span data-ttu-id="8c5dc-170">[SQL Server 2008 R2](http://msdn.microsoft.com/library/bb500395\(v=sql.105\).aspx) のインストール</span><span class="sxs-lookup"><span data-stu-id="8c5dc-170">Install [SQL Server 2008 R2](http://msdn.microsoft.com/library/bb500395\(v=sql.105\).aspx)</span></span>  
  
 <span data-ttu-id="8c5dc-171">[SQL Server 2012](http://msdn.microsoft.com/library/bb500469\(v=sql.110\).aspx) のインストール</span><span class="sxs-lookup"><span data-stu-id="8c5dc-171">Install [SQL Server 2012](http://msdn.microsoft.com/library/bb500469\(v=sql.110\).aspx)</span></span>  
  
 <span data-ttu-id="8c5dc-172">[SQL Server 2014 ](http://msdn.microsoft.com/library/bb500469\(v=sql.120\).aspx) のインストール</span><span class="sxs-lookup"><span data-stu-id="8c5dc-172">Install [SQL Server 2014](http://msdn.microsoft.com/library/bb500469\(v=sql.120\).aspx)</span></span>  
  
 <span data-ttu-id="8c5dc-173">SQL Server をインストールするときに、次の機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-173">When you install SQL Server, select the following features:</span></span>  
  
- <span data-ttu-id="8c5dc-174">データベース エンジン サービス</span><span class="sxs-lookup"><span data-stu-id="8c5dc-174">Database Engine Services</span></span>  
  
  -   <span data-ttu-id="8c5dc-175">SQL Server のレプリケーション</span><span class="sxs-lookup"><span data-stu-id="8c5dc-175">SQL Server Replication</span></span>  
  
  -   <span data-ttu-id="8c5dc-176">フルテキスト検索</span><span class="sxs-lookup"><span data-stu-id="8c5dc-176">Full-Text Search</span></span>  
  
- <span data-ttu-id="8c5dc-177">Analysis Services</span><span class="sxs-lookup"><span data-stu-id="8c5dc-177">Analysis Services</span></span>  
  
- <span data-ttu-id="8c5dc-178">Reporting Services</span><span class="sxs-lookup"><span data-stu-id="8c5dc-178">Reporting Services</span></span>  
  
- <span data-ttu-id="8c5dc-179">共有機能</span><span class="sxs-lookup"><span data-stu-id="8c5dc-179">Shared Features</span></span>  
  
  -   <span data-ttu-id="8c5dc-180">SQL Server Data Tools (SQL Server 2014 / SQL Server 2012) または Business Intelligence Development Studio (SQL Server 2008 R2)</span><span class="sxs-lookup"><span data-stu-id="8c5dc-180">SQL Server Data Tools (SQL Server 2014 / SQL Server 2012) or Business Intelligence Development Studio (SQL Server 2008 R2)</span></span>  
  
       [<span data-ttu-id="8c5dc-181">SQL Server 2014 Data Tools のダウンロード</span><span class="sxs-lookup"><span data-stu-id="8c5dc-181">Download SQL Server 2014 Data Tools</span></span>](http://www.microsoft.com/download/details.aspx?id=42313)  
  
  -   <span data-ttu-id="8c5dc-182">クライアント ツール接続</span><span class="sxs-lookup"><span data-stu-id="8c5dc-182">Client Tools Connectivity</span></span>  
  
  -   <span data-ttu-id="8c5dc-183">Integration Services</span><span class="sxs-lookup"><span data-stu-id="8c5dc-183">Integration Services</span></span>  
  
  -   <span data-ttu-id="8c5dc-184">管理ツール - 基本</span><span class="sxs-lookup"><span data-stu-id="8c5dc-184">Management Tools - Basic</span></span>  
  
      -   <span data-ttu-id="8c5dc-185">管理ツール - 完全</span><span class="sxs-lookup"><span data-stu-id="8c5dc-185">Management Tools - Complete</span></span>  
  
  <span data-ttu-id="8c5dc-186">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="8c5dc-186">**Additional**</span></span>  
  
- <span data-ttu-id="8c5dc-187">BizTalk Server では、バイナリ照合順序を除く、大文字と小文字を区別する/区別しないすべての SQL Server 照合順序がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-187">BizTalk Server supports all case-sensitive and case-insensitive SQL Server collations except for binary collations.</span></span> <span data-ttu-id="8c5dc-188">バイナリ照合順序はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-188">Binary collations are not supported.</span></span>  
  
- <span data-ttu-id="8c5dc-189">最適なパフォーマンスを得るには、SQL Server の Enterprise Edition を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-189">For optimal performance, Microsoft recommends using the Enterprise Edition of SQL Server.</span></span> <span data-ttu-id="8c5dc-190">詳細は、「[SQL Server 2008 R2 の各エディションがサポートする機能](http://msdn.microsoft.com/library/cc645993\(v=sql.105\).aspx)」、「[SQL Server 2012 の各エディションがサポートする機能](http://msdn.microsoft.com/library/cc645993\(v=sql.110\).aspx)」または「[SQL Server 2014 の各エディションがサポートする機能](http://msdn.microsoft.com/library/cc645993\(v=sql.120\).aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-190">See [SQL Server 2008 R2 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.105\).aspx), [SQL Server 2012 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.110\).aspx), or [SQL Server 2014 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.120\).aspx).</span></span>  
  
- <span data-ttu-id="8c5dc-191">Service Pack および Windows Updates はいずれもサポートされており、インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-191">Service packs and Windows Updates are supported and should be installed.</span></span>  
  
- <span data-ttu-id="8c5dc-192">BizTalk Server と SQL Server が別々 のコンピューター上にある場合は、分散トランザクション コーディネーター (MS DTC) は、コンピューター間のトランザクションを処理します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-192">When BizTalk Server and SQL Server are on separate computers, Distributed Transaction Coordinator (MS DTC) handles the transactions between the computers.</span></span> <span data-ttu-id="8c5dc-193">SQL Server AlwaysOn 機能は、MSDTC トランザクションをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-193">The SQL Server AlwaysOn feature does not support MSDTC transactions.</span></span> <span data-ttu-id="8c5dc-194">SQL Server AlwaysOn 機能がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-194">The SQL Server AlwaysOn feature is not supported.</span></span>  
  
##  <a name="BKMK_MQSeries"></a> <span data-ttu-id="8c5dc-195">MQSeries に必要なソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="8c5dc-195">Install MQSeries Prerequisites</span></span>  
 <span data-ttu-id="8c5dc-196">**MQSeries アダプター**: BizTalk Server のインストール時に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-196">**MQSeries adapter**: Automatically installed with the BizTalk Server installation.</span></span>  
  
 <span data-ttu-id="8c5dc-197">**MQSeries Client (MQSC) アダプター**:</span><span class="sxs-lookup"><span data-stu-id="8c5dc-197">**MQSeries Client (MQSC) adapter**:</span></span>  
  
1. <span data-ttu-id="8c5dc-198">Host Integration Server (HIS) インストールの実行</span><span class="sxs-lookup"><span data-stu-id="8c5dc-198">Run the Host Integration Server (HIS) installation</span></span>  
  
2. <span data-ttu-id="8c5dc-199">コンポーネントのインストールで、**[BizTalk アダプター]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-199">In component installation, expand **BizTalk Adapters**.</span></span>  
  
3. <span data-ttu-id="8c5dc-200">**[BizTalk Adapter for WebSphere MQ (クライアント ベース)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-200">Select **BizTalk Adapter for WebSphere MQ (Client-Based)**.</span></span>  
  
   <span data-ttu-id="8c5dc-201">**サポート対象の IBM WebSphere MQ バージョン**:</span><span class="sxs-lookup"><span data-stu-id="8c5dc-201">**Supported IBM WebSphere MQ versions**:</span></span>  
  
-   <span data-ttu-id="8c5dc-202">IBM WebSphere MQ 6.0.2.12 以降</span><span class="sxs-lookup"><span data-stu-id="8c5dc-202">IBM WebSphere MQ 6.0.2.12 and later</span></span>  
  
-   <span data-ttu-id="8c5dc-203">IBM WebSphere MQ 7.0.1.9 以降</span><span class="sxs-lookup"><span data-stu-id="8c5dc-203">IBM WebSphere MQ 7.0.1.9 and later</span></span>  
  
-   <span data-ttu-id="8c5dc-204">IBM WebSphere MQ 7.1.0.5 以降</span><span class="sxs-lookup"><span data-stu-id="8c5dc-204">IBM WebSphere MQ 7.1.0.5 and later</span></span>  
  
-   <span data-ttu-id="8c5dc-205">IBM WebSphere MQ 7.5.0.3 以降</span><span class="sxs-lookup"><span data-stu-id="8c5dc-205">IBM WebSphere MQ 7.5.0.3 and later</span></span>  
  
-   <span data-ttu-id="8c5dc-206">IBM WebSphere MQ 8 (実行時に限定。管理 API はなし)</span><span class="sxs-lookup"><span data-stu-id="8c5dc-206">IBM WebSphere MQ 8 (limited to runtime; no administration APIs)</span></span>  
  
     <span data-ttu-id="8c5dc-207">MQ バージョン 8 は [Host Integration Server CU3](https://support.microsoft.com/kb/3019572) でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-207">MQ version 8 support is included with [Host Integration Server CU3](https://support.microsoft.com/kb/3019572).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c5dc-208">特定の WebSphere MQ バージョンが表示されない場合 MQ など 5.x では、その後はサポートされていませんこの BizTalk Server のバージョン。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-208">If a specific WebSphere MQ version is not listed, like MQ 5.x, then it is not supported with this BizTalk Server version.</span></span>  
  
 <span data-ttu-id="8c5dc-209">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="8c5dc-209">**Additional**</span></span>  
  
- <span data-ttu-id="8c5dc-210">常に最新の WebSphere MQ 修正パックをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-210">As a best practice, always install the latest WebSphere MQ fix pack.</span></span> <span data-ttu-id="8c5dc-211">参照してください[ http://www.ibm.com/support/docview.wss?uid=swg27006037](http://www.ibm.com/support/docview.wss?uid=swg27006037)します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-211">See [http://www.ibm.com/support/docview.wss?uid=swg27006037](http://www.ibm.com/support/docview.wss?uid=swg27006037).</span></span>  
  
- <span data-ttu-id="8c5dc-212">IBM WebSphere MQ が Windows 以外のコンピューターにインストールされている場合は、同じコンピューターに **MQSAgent COM+ アプリ** (MQSConfigWiz.exe) と **MQSeries Server for Windows** をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-212">If IBM WebSphere MQ is installed on a non-Windows computer, install the **MQSAgent COM+ application** (MQSConfigWiz.exe) and **MQSeries Server for Windows** on the same computer.</span></span> <span data-ttu-id="8c5dc-213">IBM WebSphere MQ が Windows コンピューターにインストールされている場合は、**MQSAgent COM+ アプリ**と **MQSeries Server for Windows** プログラムは使用することも必要になることもありません。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-213">If IBM WebSphere MQ is installed on a Windows computer, then the **MQSAgent COM+ application** and **MQSeries Server for Windows** program are not used or needed.</span></span>  
  
   <span data-ttu-id="8c5dc-214">**MQSConfigWiz.exe** BizTalk Server インストール ファイルに含まれています。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-214">**MQSConfigWiz.exe** is included in the BizTalk Server installation files.</span></span>  
  
   <span data-ttu-id="8c5dc-215">**MQSeries Server for Windows** はマイクロソフトのプログラムではありませんので、IBM WebSphere MQ プログラムから入手する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-215">**MQSeries Server for Windows** is not a Microsoft program and must be obtained with your IBM WebSphere MQ program.</span></span>  
  
- <span data-ttu-id="8c5dc-216">「[MQSeries アダプター](http://technet.microsoft.com/library/aa547973\(v=BTS.80\).aspx)」には、異なるコンポーネント構成など、MQSeries アダプターに関する詳細情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-216">[MQSeries Adapter](http://technet.microsoft.com/library/aa547973\(v=BTS.80\).aspx) provides more information on the MQSeries adapter, including configuring the different components.</span></span> <span data-ttu-id="8c5dc-217">[BizTalk Server: 「MQSeries と MQSeries Client (MQSC) のアダプター](http://social.technet.microsoft.com/wiki/contents/articles/18316.biztalk-server-mqseries-and-mqseries-client-mqsc-adapters.aspx)」には、MQSeries と MQSC のアダプターの詳細が記載されています。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-217">[BizTalk Server: MQSeries and MQSeries Client (MQSC) adapters](http://social.technet.microsoft.com/wiki/contents/articles/18316.biztalk-server-mqseries-and-mqseries-client-mqsc-adapters.aspx) provides additional details on the MQSeries and MQSC adapters.</span></span>  
  
- <span data-ttu-id="8c5dc-218">IBM WebSphere はマイクロソフト製品ではないため、マイクロソフトによるサポートはありません。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-218">IBM WebSphere is not a Microsoft product and is not supported by Microsoft.</span></span> <span data-ttu-id="8c5dc-219">マイクロソフトでは、このプログラムの適合性に関して一切の保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-219">Microsoft makes no guarantees about the suitability of this program.</span></span> <span data-ttu-id="8c5dc-220">IBM WebSphere MQ のダウンロード方法をはじめとする詳細については、www.ibm.com をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-220">For more information about IBM WebSphere MQ, including download instructions, see www.ibm.com.</span></span>  
  
##  <a name="BKMK_BAMAlerts"></a> <span data-ttu-id="8c5dc-221">BAM 警告</span><span class="sxs-lookup"><span data-stu-id="8c5dc-221">BAM Alerts</span></span>  
 <span data-ttu-id="8c5dc-222">BAM 警告の SQL Server 2012 と新しいバージョンでは、SQL Server でデータベース メールを使用します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-222">BAM Alerts with SQL Server 2012 and newer versions use Database Mail in SQL Server.</span></span> <span data-ttu-id="8c5dc-223">BAM 警告では、SQL Server 2008 R2 と以前のバージョンでは、SQL Notification Services を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-223">BAM Alerts with SQL Server 2008 R2 and older versions use SQL Notification Services.</span></span> <span data-ttu-id="8c5dc-224">インストールまたは BAM 警告の構成、前に SQL Server での Notification Services またはデータベース メールを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-224">Before installing or configuring BAM Alerts, you must configure the Notification Services or Database Mail in SQL Server.</span></span>  
  
###  <a name="BKMK_DBMail"></a> <span data-ttu-id="8c5dc-225">SQL Server 2012/2014 での BAM 警告</span><span class="sxs-lookup"><span data-stu-id="8c5dc-225">BAM Alerts using SQL Server 2012/2014</span></span>  
 <span data-ttu-id="8c5dc-226">[SQL Server 2012 データベース メールの構成](http://msdn.microsoft.com/library/hh245116\(v=sql.110\).aspx)を行います。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-226">Configure [SQL Server 2012 Database Mail](http://msdn.microsoft.com/library/hh245116\(v=sql.110\).aspx).</span></span>  
  
 <span data-ttu-id="8c5dc-227">[SQL Server 2014 データベース メールの構成](http://msdn.microsoft.com/library/hh245116\(v=sql.120\).aspx)を行います。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-227">Configure [SQL Server 2014 Database Mail](http://msdn.microsoft.com/library/hh245116\(v=sql.120\).aspx).</span></span>  
  
 <span data-ttu-id="8c5dc-228">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="8c5dc-228">**Additional**</span></span>  
  
-   <span data-ttu-id="8c5dc-229">データベース メールでは SMTP サーバーを使用して BAM 警告を送信します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-229">Database Mail uses an SMTP server to send the BAM Alerts.</span></span> <span data-ttu-id="8c5dc-230">SMTP サーバーは、BizTalk サーバーまたは別の IIS サーバー上でローカルにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-230">SMTP Server can be installed locally on the BizTalk Server or on another IIS server.</span></span> <span data-ttu-id="8c5dc-231">「[付録 D: SMTP サーバーの作成](../install-and-config-guides/appendix-d-create-the-smtp-server.md)」には、SMTP サーバーのインストールおよび構成手順があります。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-231">[Appendix D: Create the SMTP Server](../install-and-config-guides/appendix-d-create-the-smtp-server.md) lists the steps to install and configure a SMTP Server.</span></span>  
  
###  <a name="BKMK_SSNS"></a> <span data-ttu-id="8c5dc-232">SQL Server 2008 R2 を使用する BAM 警告 - SQL Server 2005 通知サービスのインストール</span><span class="sxs-lookup"><span data-stu-id="8c5dc-232">BAM Alerts using SQL Server 2008 R2 – Install SQL Server 2005 Notification Services</span></span>  
  
1. <span data-ttu-id="8c5dc-233">「[Microsoft SQL Server 2005 SP4 用 Feature Pack](http://go.microsoft.com/fwlink/p/?LinkId=286285)」にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-233">Go to [Feature Pack for Microsoft SQL Server 2005 SP4](http://go.microsoft.com/fwlink/p/?LinkId=286285).</span></span>  
  
2. <span data-ttu-id="8c5dc-234">次のコンポーネントに適したプラットフォーム パッケージをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-234">Download and install the appropriate platform package for the following components:</span></span>  
  
    <span data-ttu-id="8c5dc-235">**Microsoft SQL Server Native Client**</span><span class="sxs-lookup"><span data-stu-id="8c5dc-235">**Microsoft SQL Server Native Client**</span></span>  
  
   - <span data-ttu-id="8c5dc-236">HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli.msi>"X86 パッケージ (sqlncli.msi)</span><span class="sxs-lookup"><span data-stu-id="8c5dc-236">HYPERLINK "<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli.msi>" X86 Package (sqlncli.msi)</span></span>  
  
   - <span data-ttu-id="8c5dc-237">HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli_x64.msi>"X64 パッケージ (sqlncli_x64.msi)</span><span class="sxs-lookup"><span data-stu-id="8c5dc-237">HYPERLINK "<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli_x64.msi>" X64 Package (sqlncli_x64.msi)</span></span>  
  
     <span data-ttu-id="8c5dc-238">**Microsoft SQL Server 2005 管理オブジェクト コレクション**</span><span class="sxs-lookup"><span data-stu-id="8c5dc-238">**Microsoft SQL Server 2005 Management Objects Collection**</span></span>  
  
   - <span data-ttu-id="8c5dc-239">HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO.msi>"X86 パッケージ (SQLServer2005_XMO.msi)</span><span class="sxs-lookup"><span data-stu-id="8c5dc-239">HYPERLINK "<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO.msi>" X86 Package (SQLServer2005_XMO.msi)</span></span>  
  
   - <span data-ttu-id="8c5dc-240">HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO_x64.msi>"X64 パッケージ (SQLServer2005_XMO_x64.msi)</span><span class="sxs-lookup"><span data-stu-id="8c5dc-240">HYPERLINK "<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO_x64.msi>" X64 Package (SQLServer2005_XMO_x64.msi)</span></span>  
  
     <span data-ttu-id="8c5dc-241">**Microsoft SQL Server 2005 Notification Services クライアント コンポーネント**</span><span class="sxs-lookup"><span data-stu-id="8c5dc-241">**Microsoft SQL Server 2005 Notification Services Client Components**</span></span>  
  
   - <span data-ttu-id="8c5dc-242">HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS.msi>"X86 パッケージ (SQLServer2005_NS.msi)</span><span class="sxs-lookup"><span data-stu-id="8c5dc-242">HYPERLINK "<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS.msi>" X86 Package (SQLServer2005_NS.msi)</span></span>  
  
   - <span data-ttu-id="8c5dc-243">HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS_x64.msi>"X64 パッケージ (SQLServer2005_NS_x64.msi)</span><span class="sxs-lookup"><span data-stu-id="8c5dc-243">HYPERLINK "<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS_x64.msi>" X64 Package (SQLServer2005_NS_x64.msi)</span></span>  
  
   <span data-ttu-id="8c5dc-244">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="8c5dc-244">**Additional**</span></span>  
  
-   <span data-ttu-id="8c5dc-245">SQL Notification Services は; を構成する必要はありません。BizTalk Server にインストールされているだけです。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-245">SQL Notification Services does not need to be configured; only installed on the BizTalk Server.</span></span>  
  
##  <a name="BKMK_WIF"></a> <span data-ttu-id="8c5dc-246">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="8c5dc-246">Windows Identity Foundation</span></span>  
  
|                                                              |                                                                                                                                                                                      |
|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8c5dc-247">Windows 8.1、Windows Server 2012、および Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="8c5dc-247">Windows 8.1, Windows Server 2012, and Windows Server 2012 R2</span></span> |                                <span data-ttu-id="8c5dc-248">Windows Identity Foundation は **[Windows の機能の有効化または無効化]** に表示される機能としてオペレーティング システムに含まれています。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-248">Windows Identity Foundation is included with the operating system as a Feature in **Turn Windows features on or off**.</span></span>                                |
|                      <span data-ttu-id="8c5dc-249">Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="8c5dc-249">Windows Vista SP1</span></span>                       | <span data-ttu-id="8c5dc-250">ダウンロードできます[Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331) HYPERLINK"<http://www.microsoft.com/download/details.aspx?id=17331>"。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-250">Download available at [Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331) HYPERLINK "<http://www.microsoft.com/download/details.aspx?id=17331>" .</span></span> |
  
 <span data-ttu-id="8c5dc-251">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="8c5dc-251">**Additional**</span></span>  
  
-   <span data-ttu-id="8c5dc-252">Windows Identity Foundation (WIF) は、SharePoint アダプターまたは SharePoint クライアント側オブジェクト モデル (CSOM) を使用すると SharePoint Online に必要です。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-252">Windows Identity Foundation (WIF) is required for the SharePoint adapter or SharePoint Online when used with SharePoint Client Side Object Model (CSOM).</span></span> <span data-ttu-id="8c5dc-253">具体的な内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-253">Specifically:</span></span>  
  
    |<span data-ttu-id="8c5dc-254">インストール オプション</span><span class="sxs-lookup"><span data-stu-id="8c5dc-254">Installation Option</span></span>|<span data-ttu-id="8c5dc-255">WIF が必要</span><span class="sxs-lookup"><span data-stu-id="8c5dc-255">WIF Required</span></span>|  
    |-------------------------|------------------|  
    |<span data-ttu-id="8c5dc-256">CSOM を使用した SharePoint アダプター</span><span class="sxs-lookup"><span data-stu-id="8c5dc-256">SharePoint Adapter with CSOM</span></span>|<span data-ttu-id="8c5dc-257">はい</span><span class="sxs-lookup"><span data-stu-id="8c5dc-257">Yes</span></span>|  
    |<span data-ttu-id="8c5dc-258">CSOM を使用した SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8c5dc-258">SharePoint Online with CSOM</span></span>|<span data-ttu-id="8c5dc-259">はい</span><span class="sxs-lookup"><span data-stu-id="8c5dc-259">Yes</span></span>|  
    |<span data-ttu-id="8c5dc-260">SharePoint アダプター Web サービスを (非推奨)</span><span class="sxs-lookup"><span data-stu-id="8c5dc-260">SharePoint Adapter Web Service (deprecated)</span></span>|<span data-ttu-id="8c5dc-261">いいえ</span><span class="sxs-lookup"><span data-stu-id="8c5dc-261">No</span></span>|  
    |<span data-ttu-id="8c5dc-262">SharePoint なし</span><span class="sxs-lookup"><span data-stu-id="8c5dc-262">No SharePoint</span></span>|<span data-ttu-id="8c5dc-263">いいえ</span><span class="sxs-lookup"><span data-stu-id="8c5dc-263">No</span></span>|  
  
-   <span data-ttu-id="8c5dc-264">[付録 b: Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)SharePoint のインストール オプションで特定の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-264">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) provides specific information on the SharePoint installation options.</span></span>  
  
##  <a name="BKMK_WSS"></a> <span data-ttu-id="8c5dc-265">Microsoft SharePoint のインストールと構成</span><span class="sxs-lookup"><span data-stu-id="8c5dc-265">Install and Configure Microsoft SharePoint</span></span>  
 <span data-ttu-id="8c5dc-266">[SharePoint 2013](http://technet.microsoft.com/library/cc303424.aspx) をインストールする</span><span class="sxs-lookup"><span data-stu-id="8c5dc-266">Install [SharePoint 2013](http://technet.microsoft.com/library/cc303424.aspx)</span></span>  
  
 <span data-ttu-id="8c5dc-267">[SharePoint Online Service](http://technet.microsoft.com/library/jj819267.aspx) をインストールする</span><span class="sxs-lookup"><span data-stu-id="8c5dc-267">Install [SharePoint Online Service](http://technet.microsoft.com/library/jj819267.aspx)</span></span>  
  
 <span data-ttu-id="8c5dc-268">[SharePoint Server 2010](http://technet.microsoft.com/library/cc303424\(v=office.14\).aspx) をインストールする</span><span class="sxs-lookup"><span data-stu-id="8c5dc-268">Install [SharePoint Server 2010](http://technet.microsoft.com/library/cc303424\(v=office.14\).aspx)</span></span>  
  
 <span data-ttu-id="8c5dc-269">[SharePoint 2007](http://technet.microsoft.com/library/cc303424\(v=office.12\).aspx) をインストールする</span><span class="sxs-lookup"><span data-stu-id="8c5dc-269">Install [SharePoint 2007](http://technet.microsoft.com/library/cc303424\(v=office.12\).aspx)</span></span>  
  
 <span data-ttu-id="8c5dc-270">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="8c5dc-270">**Additional**</span></span>  
  
-   <span data-ttu-id="8c5dc-271">SharePoint をインストールする場合は、残りの BizTalk Server の前提条件を続行する前にこれを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-271">If you are installing SharePoint, you must do so before continuing with the remaining BizTalk Server prerequisites.</span></span>  
  
-   <span data-ttu-id="8c5dc-272">SharePoint のインストールと構成の手順は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-272">Installing and configuring SharePoint consists of the following procedures:</span></span>  
  
    -   <span data-ttu-id="8c5dc-273">SharePoint をインストールする</span><span class="sxs-lookup"><span data-stu-id="8c5dc-273">Install SharePoint</span></span>  
  
    -   <span data-ttu-id="8c5dc-274">SharePoint を構成する</span><span class="sxs-lookup"><span data-stu-id="8c5dc-274">Configure SharePoint</span></span>  
  
    -   <span data-ttu-id="8c5dc-275">既定の Web サイトを仮想サーバーとして拡張する</span><span class="sxs-lookup"><span data-stu-id="8c5dc-275">Extend the default Web site as a virtual server</span></span>  
  
-   <span data-ttu-id="8c5dc-276">「[付録 B: Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)」には、BizTalk Server の SharePoint アダプターのインストール オプションに関する情報があります。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-276">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) describes the SharePoint adapter installation options for BizTalk Server.</span></span>  
  
-   <span data-ttu-id="8c5dc-277">SharePoint アダプターを使用する際は、SharePoint サービスの Web サービスの代わりに新しい CSOM オプションをインストールすることをお勧めします。詳細は「[付録 B: Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-277">When using the SharePoint adapter, it is recommended to install the new CSOM option instead of the SharePoint Service Web Service; described at [Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md).</span></span>  
  
##  <a name="BKMK_SharedMem"></a> <span data-ttu-id="8c5dc-278">共有メモリ プロトコルの無効化</span><span class="sxs-lookup"><span data-stu-id="8c5dc-278">Disable the Shared Memory Protocol</span></span>  
  
1. <span data-ttu-id="8c5dc-279">**[SQL Server 構成マネージャー]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-279">Open **SQL Server Configuration Manager**.</span></span>  
  
2. <span data-ttu-id="8c5dc-280">**SQL Server 構成マネージャー**で、**[SQL Server ネットワークの構成]** を展開して **[MSSQLSERVER のプロトコル]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-280">In **SQL Server Configuration Manager**, expand **SQL Server Network Configuration**, and then select **Protocols for MSSQLSERVER**.</span></span>  
  
3. <span data-ttu-id="8c5dc-281">**[共有メモリ]** を右クリックし、**[無効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-281">Right-click **Shared Memory**, and then select **Disable**.</span></span>  
  
4. <span data-ttu-id="8c5dc-282">**[SQL Server サービス]** を選択し、**[SQL Server (MSSQLSERVER)]** を右クリックして、**[停止]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-282">Select **SQL Server Services**, right-click **SQL Server (MSSQLSERVER)**, and then select **Stop**.</span></span> <span data-ttu-id="8c5dc-283">サービスが停止したら、**[SQL Server (MSSQLSERVER)]** をもう一度右クリックして **[開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-283">After the service has stopped, right-click **SQL Server (MSSQLSERVER)** again, and then select **Start**.</span></span>  
  
5. <span data-ttu-id="8c5dc-284">**SQL Server 構成マネージャー**を終了します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-284">Close **SQL Server Configuration Manager**.</span></span>  
  
   <span data-ttu-id="8c5dc-285">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="8c5dc-285">**Additional**</span></span>  
  
-   <span data-ttu-id="8c5dc-286">ある種のストレス条件下では (たとえば、同じコンピューターから複数のクライアントが SQL Server にアクセスしている場合)、SQL Server の共有メモリ プロトコルが原因で BizTalk Server のパフォーマンスが低下することがあります。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-286">Under certain stress conditions (such as clients accessing SQL Server from the same computer), the SQL Server Shared Memory protocol may lower BizTalk Server performance.</span></span> <span data-ttu-id="8c5dc-287">この動作を解決するには、共有メモリ ネットワーク プロトコルを無効にするよう SQL Server ネットワークの構成で設定します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-287">You can resolve this behavior by disabling the Shared Memory network protocol in SQL Server Network Configuration.</span></span>  
  
-   <span data-ttu-id="8c5dc-288">ReplaceThisText</span><span class="sxs-lookup"><span data-stu-id="8c5dc-288">ReplaceThisText</span></span>  
  
##  <a name="BKMK_LocalAdmin"></a><span data-ttu-id="8c5dc-289">ローカルの Administrators グループへの参加</span><span class="sxs-lookup"><span data-stu-id="8c5dc-289">Join the Local Administrators Group</span></span>  
 <span data-ttu-id="8c5dc-290">**Windows Server 2012** : [Windows Server 2012: ローカル管理者グループにアカウントを追加する方法](http://social.technet.microsoft.com/wiki/contents/articles/13436.windows-server-2012-how-to-add-an-account-to-a-local-administrator-group.aspx)</span><span class="sxs-lookup"><span data-stu-id="8c5dc-290">**Windows Server 2012** : [Windows Server 2012: How to Add an Account to a Local Administrator Group](http://social.technet.microsoft.com/wiki/contents/articles/13436.windows-server-2012-how-to-add-an-account-to-a-local-administrator-group.aspx)</span></span>  
  
 <span data-ttu-id="8c5dc-291">**Windows 8.1**: Windows 8 でローカルのユーザーとグループを開くには、キーボードの Windows ボタンをクリックして「**グループ**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-291">**Windows 8.1**: To open Local Users and Groups on Windows 8, click the Windows button on the keyboard and type **groups**.</span></span> <span data-ttu-id="8c5dc-292">検索] ウィンドウで、**[設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-292">In the Search window, click **Settings**.</span></span> <span data-ttu-id="8c5dc-293">検索結果] ウィンドウで、**[ローカル ユーザーとグループの編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-293">In the Results window, click **Edit local users and groups**.</span></span> <span data-ttu-id="8c5dc-294">**[グループ]** をクリックし、[Administrators をダブルクリックしてアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-294">Click **Groups** and then double-click Administrators to add an account.</span></span>  
  
 <span data-ttu-id="8c5dc-295">**Windows 7 SP1**: [スタート] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-295">**Windows 7 SP1**: Click Start.</span></span> <span data-ttu-id="8c5dc-296">**[検索]** テキスト ボックスに「**コンピューターの管理**」と入力し、クリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-296">In the **Search** text box, type **Computer Management**, and click it to open.</span></span> <span data-ttu-id="8c5dc-297">**[ローカル ユーザーとグループ]** を展開し、**[グループ]** をクリックしてから [Administrator をダブルクリックしてアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-297">Expand **Local Users and Groups**, click **Groups**, and then double-click Administrators to add an account.</span></span>  
  
 <span data-ttu-id="8c5dc-298">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="8c5dc-298">**Additional**</span></span>  
  
-   <span data-ttu-id="8c5dc-299">インストールして、BizTalk Server を構成するには、ローカルの Administrators グループのメンバーがあります。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-299">You must be a member of the local Administrators group to install and configure BizTalk Server.</span></span>  
  
##  <a name="BKMK_AppLog"></a> <span data-ttu-id="8c5dc-300">アプリケーション イベント ログの構成</span><span class="sxs-lookup"><span data-stu-id="8c5dc-300">Configure the Application Event Log</span></span>  
  
1. <span data-ttu-id="8c5dc-301">**イベント ビューアー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-301">Open **Event Viewer**:</span></span>  
  
    <span data-ttu-id="8c5dc-302">**Windows Server 2012** : キーボードの Windows ボタンをクリックします。**イベント ビューアー**します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-302">**Windows Server 2012** : Click the Windows button on the keyboard and type **Event Viewer**.</span></span> <span data-ttu-id="8c5dc-303">検索結果] ウィンドウで、**[イベント ビューアー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-303">In the Results window, click **Event Viewer**.</span></span>  
  
    <span data-ttu-id="8c5dc-304">**Windows 8.1**: キーボードの Windows ボタンをクリックして「**イベント ビューアー**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-304">**Windows 8.1**: Click the Windows button on the keyboard and type **Event Viewer**.</span></span> <span data-ttu-id="8c5dc-305">検索] ウィンドウで、**[設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-305">In the Search window, click **Settings**.</span></span> <span data-ttu-id="8c5dc-306">検索結果] ウィンドウで、**[イベント ログの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-306">In the Results window, click **View event logs**.</span></span>  
  
    <span data-ttu-id="8c5dc-307">**Windows 7 SP1**: [スタート] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-307">**Windows 7 SP1**: Click Start.</span></span> <span data-ttu-id="8c5dc-308">**[検索]** テキスト ボックスに **「イベント ビューアー」** と入力し、クリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-308">In the **Search** text box, type **Event Viewer**, and click it to open.</span></span>  
  
2. <span data-ttu-id="8c5dc-309">**[Windows ログ]** を展開し、**[アプリケーション]** を右クリックして **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-309">Expand **Windows Logs**, right-click **Application**, and then click **Properties**.</span></span> <span data-ttu-id="8c5dc-310">**[ログのプロパティ]**:</span><span class="sxs-lookup"><span data-stu-id="8c5dc-310">In **Log Properties**:</span></span>  
  
   -   <span data-ttu-id="8c5dc-311">使用可能な空き領域を確認するには、**[ログ サイズ]** と **[最大ログ サイズ]** のプロパティを比較します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-311">To determine the available space, compare the **Log Size** and the **Maximum log size** properties.</span></span>  
  
   -   <span data-ttu-id="8c5dc-312">空き領域を増やすには、**[最大ログ サイズ]** の数値を増やします。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-312">To provide more space, enter a higher number in **Maximum log size**.</span></span>  
  
   -   <span data-ttu-id="8c5dc-313">ログの空き領域がなくなったときに古いイベントが上書きされるようにするには、**[必要に応じてイベントを上書きする]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-313">To enable overwriting of old events when the log becomes full, select **Overwrite events as needed**.</span></span>  
  
   -   <span data-ttu-id="8c5dc-314">ログ イベントを消去するには、**[ログの消去]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-314">To clear the log events, select **Clear log**.</span></span>  
  
3. <span data-ttu-id="8c5dc-315">**[OK]** をクリックして **[イベント ビューアー]** を閉じます。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-315">Click **OK** to close the **Event Viewer**.</span></span>  
  
   <span data-ttu-id="8c5dc-316">**追加情報**</span><span class="sxs-lookup"><span data-stu-id="8c5dc-316">**Additional**</span></span>  
  
-   <span data-ttu-id="8c5dc-317">BizTalk Server のセットアップを実行すると、イベントの記録がアプリケーション イベント ログに保存されます。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-317">BizTalk Server setup keeps a record of events in the Application Event Log.</span></span> <span data-ttu-id="8c5dc-318">インストールされる BizTalk Server の機能によっては、ログの空き領域を超える大きさのログが作成されることもあります。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-318">Depending on the BizTalk Server features installed, the amount of space required in the log may exceed its limit.</span></span> <span data-ttu-id="8c5dc-319">BizTalk Server のセットアップ中に、アプリケーション イベント ログの領域が不足している場合、インストールは失敗します。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-319">If the application event log runs out of space during BizTalk Server setup, the installation fails.</span></span> <span data-ttu-id="8c5dc-320">アプリケーション イベント ログの設定を変更すれば、この失敗を回避できます。</span><span class="sxs-lookup"><span data-stu-id="8c5dc-320">Changing the Application Event Log settings prevents this failure.</span></span>  
  
## <a name="next"></a><span data-ttu-id="8c5dc-321">Next</span><span class="sxs-lookup"><span data-stu-id="8c5dc-321">Next</span></span>  
 [<span data-ttu-id="8c5dc-322">BizTalk Server の機能とコンポーネントの選択</span><span class="sxs-lookup"><span data-stu-id="8c5dc-322">Choose BizTalk Server Features and Components</span></span>](http://msdn.microsoft.com/library/b8c43fcf-9e5c-48ba-830b-13a5177e30f0)  
  
## <a name="see-also"></a><span data-ttu-id="8c5dc-323">参照</span><span class="sxs-lookup"><span data-stu-id="8c5dc-323">See Also</span></span>  
 <span data-ttu-id="8c5dc-324">[BizTalk Server 2013 および 2013 R2 のインストール概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span><span class="sxs-lookup"><span data-stu-id="8c5dc-324">[Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span></span>  
 <span data-ttu-id="8c5dc-325">[付録 A: サイレント インストール](../install-and-config-guides/appendix-a-silent-installation.md) </span><span class="sxs-lookup"><span data-stu-id="8c5dc-325">[Appendix A: Silent Installation](../install-and-config-guides/appendix-a-silent-installation.md) </span></span>  
 <span data-ttu-id="8c5dc-326">[付録 B: Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="8c5dc-326">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) </span></span>  
 <span data-ttu-id="8c5dc-327">[付録 C: 再配布可能な CAB ファイル](../install-and-config-guides/appendix-c-redistributable-cab-files.md) </span><span class="sxs-lookup"><span data-stu-id="8c5dc-327">[Appendix C: Redistributable CAB Files](../install-and-config-guides/appendix-c-redistributable-cab-files.md) </span></span>  
 [<span data-ttu-id="8c5dc-328">付録 D: SMTP サーバーの作成</span><span class="sxs-lookup"><span data-stu-id="8c5dc-328">Appendix D: Create the SMTP Server</span></span>](../install-and-config-guides/appendix-d-create-the-smtp-server.md)
