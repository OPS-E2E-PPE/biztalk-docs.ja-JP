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
ms.openlocfilehash: d971338680c1cf9351b179bd94e253b4d69437c5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399381"
---
# <a name="prepare-your-computer-for-installation"></a><span data-ttu-id="c2829-102">コンピューターのインストールを準備します。</span><span class="sxs-lookup"><span data-stu-id="c2829-102">Prepare Your Computer for Installation</span></span>
<span data-ttu-id="c2829-103">このトピックでは、インストール、すべてのソフトウェア前提条件の構成しアカウントの作成とアクセス許可を設定して、コンピューターを準備する手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c2829-103">This topic lists the steps to prepare your computer by installing and configuring all software prerequisites, and then creating accounts and setting permissions.</span></span>  

> [!TIP] 
> <span data-ttu-id="c2829-104">統合 MVP は、前提条件、および BizTalk Server をインストールする場合は、非常に詳細なステップ バイ ステップ ガイドを準備します。[BizTalk 2013 のインストールおよび構成パート 1](http://sandroaspbiztalkblog.wordpress.com/2013/05/05/biztalk-2013-installation-and-configuration-important-considerations-before-set-up-the-server-part-1/)します。</span><span class="sxs-lookup"><span data-stu-id="c2829-104">An integration MVP prepared a very detailed step-by-step guide to install the prerequisites, and BizTalk Server:  [BizTalk 2013 Installation and Configuration part 1](http://sandroaspbiztalkblog.wordpress.com/2013/05/05/biztalk-2013-installation-and-configuration-important-considerations-before-set-up-the-server-part-1/).</span></span>  
> 
> <span data-ttu-id="c2829-105">ユーザー アクセス制御 (UAC) または Windows ファイアウォールを無効にするなど、いくつかの手順は Microsoft がお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="c2829-105">Some steps are not recommended by Microsoft, such as disabling User Access Control (UAC) or Windows Firewall.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="c2829-106">表示されている順序でこれらのタスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="c2829-106">Complete these tasks in the order listed.</span></span>  
  
##  <a name="BKMK_InstUpdates"></a> <span data-ttu-id="c2829-107">Windows 更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c2829-107">Install Windows Updates</span></span>  
  
- <span data-ttu-id="c2829-108">**Windows 7**:[開始] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2829-108">**Windows 7**: Click Start.</span></span> <span data-ttu-id="c2829-109">**検索**テキスト ボックスに「 **Windows Update**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-109">In the **Search** text box, type **Windows Update**.</span></span>  
  
- <span data-ttu-id="c2829-110">**Windows 8.1、Windows Server 2012、および Windows Server 2012 R2**:キーボードと型の Windows ボタンをクリックします。 **Windows Update**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-110">**Windows 8.1, Windows Server 2012, and Windows Server 2012 R2**: Click the Windows button on the keyboard and type **Windows Update**.</span></span> <span data-ttu-id="c2829-111">検索結果から次のようにクリックします。 **Windows Update**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-111">From the search results, click **Windows Update**.</span></span>  
  
  <span data-ttu-id="c2829-112">更新プログラムのインストール後、コンピューターを再起動する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="c2829-112">After installing updates, you may need to restart the computer.</span></span>  
  
##  <a name="BKMK_IIS"></a> <span data-ttu-id="c2829-113">インターネット インフォメーション サービスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c2829-113">Enable Internet Information Services</span></span>  
 <span data-ttu-id="c2829-114">Microsoft インターネット インフォメーション サービス (IIS) など、多くの BizTalk Server 機能の Web アプリケーション インフラストラクチャを提供します。</span><span class="sxs-lookup"><span data-stu-id="c2829-114">Microsoft Internet Information Services (IIS) provides a Web application infrastructure for many BizTalk Server features, including:</span></span>  
  
-   <span data-ttu-id="c2829-115">HTTP アダプター</span><span class="sxs-lookup"><span data-stu-id="c2829-115">HTTP adapter</span></span>  
  
-   <span data-ttu-id="c2829-116">SOAP アダプター</span><span class="sxs-lookup"><span data-stu-id="c2829-116">SOAP adapter</span></span>  
  
-   <span data-ttu-id="c2829-117">Windows SharePoint Services アダプター</span><span class="sxs-lookup"><span data-stu-id="c2829-117">Windows SharePoint Services adapter</span></span>  
  
-   <span data-ttu-id="c2829-118">SSL (Secure Sockets Layer) 暗号化</span><span class="sxs-lookup"><span data-stu-id="c2829-118">Secure Sockets Layer (SSL) encryption</span></span>  
  
-   <span data-ttu-id="c2829-119">BAM ポータル</span><span class="sxs-lookup"><span data-stu-id="c2829-119">BAM Portal</span></span>  
  
#### <a name="install-iis"></a><span data-ttu-id="c2829-120">IIS をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c2829-120">Install IIS</span></span>

<span data-ttu-id="c2829-121">特定のインストールの手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2829-121">For the specific install steps, see:</span></span> 

[<span data-ttu-id="c2829-122">IIS (Windows 8 および Windows Server 2012) のインストールします。</span><span class="sxs-lookup"><span data-stu-id="c2829-122">Install IIS (Windows 8 and Windows Server 2012)</span></span>](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/installing-iis-8-on-windows-server-2012)

[<span data-ttu-id="c2829-123">IIS (Windows 7 および Windows Vista) のインストールします。</span><span class="sxs-lookup"><span data-stu-id="c2829-123">Install IIS (Windows 7 and Windows Vista)</span></span>](https://docs.microsoft.com/iis/install/installing-iis-7/installing-iis-on-windows-vista-and-windows-7)


<span data-ttu-id="c2829-124">既定のチェックのオプションに加えて、IIS をインストールするときに、次も確認します。</span><span class="sxs-lookup"><span data-stu-id="c2829-124">When you install IIS, in addition to the default checked options, also check the following:</span></span>  
  
- <span data-ttu-id="c2829-125">**Web 管理ツール**:確認します。</span><span class="sxs-lookup"><span data-stu-id="c2829-125">**Web Management Tools**: Also check:</span></span>  
  
    - <span data-ttu-id="c2829-126">IIS 6 管理互換性:</span><span class="sxs-lookup"><span data-stu-id="c2829-126">IIS 6 Management Compatibility:</span></span>  
  
        - <span data-ttu-id="c2829-127">IIS 6 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="c2829-127">IIS 6 Management Console</span></span>  
  
        - <span data-ttu-id="c2829-128">IIS メタベースおよび IIS 6 構成との互換性</span><span class="sxs-lookup"><span data-stu-id="c2829-128">IIS Metabase and IIS 6 configuration compatibility</span></span>  
  
    - <span data-ttu-id="c2829-129">IIS 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="c2829-129">IIS Management Console</span></span>  
  
- <span data-ttu-id="c2829-130">**World Wide Web サービス**:展開**セキュリティ**も選択します。</span><span class="sxs-lookup"><span data-stu-id="c2829-130">**World Wide Web Services**: Expand **Security** and also select:</span></span>  
  
    - <span data-ttu-id="c2829-131">基本認証</span><span class="sxs-lookup"><span data-stu-id="c2829-131">Basic Authentication</span></span>  
  
    - <span data-ttu-id="c2829-132">[Windows 認証]</span><span class="sxs-lookup"><span data-stu-id="c2829-132">Windows Authentication</span></span>  

<span data-ttu-id="c2829-133">また、次の点を検討してください。</span><span class="sxs-lookup"><span data-stu-id="c2829-133">Also consider the following:</span></span>  
  
- <span data-ttu-id="c2829-134">**.Net framework 3.5 の機能**: .NET Framework 4.5 と .NET Framework 3.5 は、BizTalk Adapter Pack を使用する .Net アプリケーションを開発に使用できます。</span><span class="sxs-lookup"><span data-stu-id="c2829-134">**.Net Framework 3.5 Features**: .NET Framework 4.5 and .NET Framework 3.5 can be used to develop .Net applications involving the BizTalk Adapter Pack.</span></span> <span data-ttu-id="c2829-135">通常、 **.NET Framework 4.5 機能**が既にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="c2829-135">Typically, **.NET Framework 4.5 Features** is already installed.</span></span> <span data-ttu-id="c2829-136">このコンピューターで、アプリケーションを作成する .NET Framework 3.5 を使用する場合 **.Net Framework 3.5 の機能**もインストールできます。</span><span class="sxs-lookup"><span data-stu-id="c2829-136">If you will use .NET Framework 3.5 to create applications on this computer, then **.Net Framework 3.5 Features** can also be installed.</span></span>  
  
- <span data-ttu-id="c2829-137">**メッセージ キュー**:チェックして、ローカルの MSMQ ストアを作成するには、MSMQ アダプターを使用している場合**メッセージ キュー**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-137">**Message Queuing**: If you are using the MSMQ adapter, you can create a local MSMQ store by checking **Message Queuing**.</span></span>  
  
- <span data-ttu-id="c2829-138">**SMTP サーバー**:チェックして、ローカルの SMTP サーバーを作成するには、SMTP アダプタを使用している場合**SMTP サーバー**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-138">**SMTP Server**: If you are using the SMTP adapter, you can create a local SMTP Server by checking **SMTP Server**.</span></span>  
  
- <span data-ttu-id="c2829-139">**Windows Identity Foundation 3.5**:Windows Identity Foundation (WIF) は、CSOM インストール オプションを使用する場合、SharePoint アダプターで必要です。</span><span class="sxs-lookup"><span data-stu-id="c2829-139">**Windows Identity Foundation 3.5**: Windows Identity Foundation (WIF) is required by the SharePoint adapter when using the CSOM installation option.</span></span> <span data-ttu-id="c2829-140">[付録 b:Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)SharePoint アダプターの CSOM インストール オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c2829-140">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) describes the CSOM installation option for the SharePoint adapter.</span></span>    
  
 
##  <a name="BKMK_XLS"></a> <span data-ttu-id="c2829-141">Microsoft Office Excel をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c2829-141">Install Microsoft Office Excel</span></span>  
  
1. <span data-ttu-id="c2829-142">Microsoft Office のセットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="c2829-142">Run the Microsoft Office setup.</span></span>  
  
2. <span data-ttu-id="c2829-143">表示されたら、**インストールの種類**画面で、**カスタム インストール**、し、**次**。</span><span class="sxs-lookup"><span data-stu-id="c2829-143">When you reach the **Type of Installation** screen, select **Custom Install**, and then select **Next**.</span></span>  
  
3. <span data-ttu-id="c2829-144">**カスタム セットアップ**画面で、 **Excel**、し、**次**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-144">On the **Custom Setup** screen, select **Excel**, and then select **Next**.</span></span>  
  
4. <span data-ttu-id="c2829-145">**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2829-145">Select **Install**.</span></span>  
  
5. <span data-ttu-id="c2829-146">**セットアップの完了**を選択します**完了**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-146">In **Setup Completed**, select **Finish**.</span></span>  
  
   <span data-ttu-id="c2829-147">**その他**</span><span class="sxs-lookup"><span data-stu-id="c2829-147">**Additional**</span></span>  
  
-   <span data-ttu-id="c2829-148">BizTalk Server は、32 ビット版の Microsoft Office のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="c2829-148">BizTalk Server supports only 32-bit version of Microsoft Office.</span></span>  
  
-   <span data-ttu-id="c2829-149">Microsoft Office Excel でビジネス アクティビティ監視 (BAM) では、BizTalk Server が必要です。</span><span class="sxs-lookup"><span data-stu-id="c2829-149">Microsoft Office Excel is required by Business Activity Monitoring (BAM) in BizTalk Server.</span></span> <span data-ttu-id="c2829-150">BAM の Office Excel では、監視するビジネス プロセスを定義します。</span><span class="sxs-lookup"><span data-stu-id="c2829-150">The BAM Office Excel Workbook defines the business processes you want to monitor.</span></span> <span data-ttu-id="c2829-151">この BAM Excel ブックでは、BAM によって収集されたデータをどのようにビジネス ユーザーの画面に表示するかを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="c2829-151">You also use the BAM Excel Workbook to define the way business users see the data collected by BAM.</span></span>  
  
-   <span data-ttu-id="c2829-152">BAM.xla を Excel に正しく読み込むにインストール**アプリケーション用の Visual Basic**  **Office 共有機能**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-152">To successfully load BAM.xla into Excel, install **Visual Basic for Applications** under **Office Shared Features**.</span></span> <span data-ttu-id="c2829-153">それ以外の場合、エラーが発生「このブックは、VBA プロジェクト、ActiveX コントロールおよびその他のプログラミング関連の機能を紛失が」</span><span class="sxs-lookup"><span data-stu-id="c2829-153">Otherwise, you may get error “This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.”</span></span>  
  
##  <a name="BKMK_VS"></a> <span data-ttu-id="c2829-154">Visual Studio をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c2829-154">Install Visual Studio</span></span>  
  
1. <span data-ttu-id="c2829-155">Visual Studio のセットアップを管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="c2829-155">Run the Visual Studio setup as Administrator.</span></span>  
  
2. <span data-ttu-id="c2829-156">ライセンス条項に同意し、をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-156">Accept the license agreement and click **Next**.</span></span>  
  
3. <span data-ttu-id="c2829-157">**インストールするオプション機能**、必要なオプションを選択しを選択します。**インストール**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-157">In **Optional features to install**, select the options you need and then select **Install**.</span></span> <span data-ttu-id="c2829-158">BizTalk Server は、オプション機能を必要としません。</span><span class="sxs-lookup"><span data-stu-id="c2829-158">BizTalk Server does not require any of the optional features.</span></span>  
  
4. <span data-ttu-id="c2829-159">**完了**ページ、ウィンドウを閉じるか、をクリックして**起動**Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="c2829-159">On the **Finish** page, close the window or click **Launch** to open Visual Studio.</span></span>  
  
   <span data-ttu-id="c2829-160">**その他**</span><span class="sxs-lookup"><span data-stu-id="c2829-160">**Additional**</span></span>  
  
-   <span data-ttu-id="c2829-161">BizTalk Server をインストールする前に Visual Studio をインストールして、Visual Studio チーム エクスプ ローラーにアップグレードし、する必要がありますから BizTalk Server インストールを修復する場合、\*\*コントロール パネルの \*\* / **プログラム**オプション。</span><span class="sxs-lookup"><span data-stu-id="c2829-161">If you install Visual Studio before installing BizTalk Server, and then upgrade to Visual Studio Team Explorer, you may need to repair your BizTalk Server installation from the **Control Panel** / **Programs** option.</span></span>  
  
-   <span data-ttu-id="c2829-162">Visual Studio では、Microsoft SQL Server Express は自動的にインストールされますが、BizTalk Server では使用しません。</span><span class="sxs-lookup"><span data-stu-id="c2829-162">Visual Studio automatically installs Microsoft SQL Server Express; which is not used by BizTalk Server.</span></span> <span data-ttu-id="c2829-163">ベスト プラクティスとして、Microsoft SQL Server Express をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="c2829-163">As a best practice, uninstall Microsoft SQL Server Express.</span></span>  
  
-   <span data-ttu-id="c2829-164">BizTalk Server 開発ツールは、Visual Studio をベースとして動作します。</span><span class="sxs-lookup"><span data-stu-id="c2829-164">The BizTalk Server development tools are based on Visual Studio.</span></span> <span data-ttu-id="c2829-165">少なくとも、BizTalk Server をインストールする前に、Visual Studio の Microsoft Visual c#® .NET コンポーネントをインストールする必要があります**開発ツールおよび SDK**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-165">At a minimum, you must install the Microsoft Visual C#® .NET component of Visual Studio before you install the BizTalk Server**Developer Tools and SDK**.</span></span>  
  
-   <span data-ttu-id="c2829-166">Visual Studio は*いない*アプリケーション開発やデバッグが必要な実稼働コンピューター (ランタイムのみ)、BizTalk Server をインストールするかどうかに必要な。</span><span class="sxs-lookup"><span data-stu-id="c2829-166">Visual Studio is *not* required if you are installing BizTalk Server on a production computer (runtime only), on which no application development or debugging is required.</span></span>  
  
-   <span data-ttu-id="c2829-167">BizTalk Server ランタイムでは、.NET Framework 4.5 が必要です。</span><span class="sxs-lookup"><span data-stu-id="c2829-167">The BizTalk Server runtime requires .NET Framework 4.5.</span></span> <span data-ttu-id="c2829-168">Windows Communication Foundation (WCF) アダプターまたは WCF インターセプターをインストールする場合、.NET Framework 3.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="c2829-168">The .NET Framework 3.0 is required if the Windows Communication Foundation (WCF) adapter or WCF Interceptor is installed.</span></span>  
  
##  <a name="BKMK_SQL"></a> <span data-ttu-id="c2829-169">SQL Server をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c2829-169">Install SQL Server</span></span>  
 <span data-ttu-id="c2829-170">インストール[SQL Server 2008 R2](http://msdn.microsoft.com/library/bb500395\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c2829-170">Install [SQL Server 2008 R2](http://msdn.microsoft.com/library/bb500395\(v=sql.105\).aspx)</span></span>  
  
 <span data-ttu-id="c2829-171">インストール[SQL Server 2012](http://msdn.microsoft.com/library/bb500469\(v=sql.110\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c2829-171">Install [SQL Server 2012](http://msdn.microsoft.com/library/bb500469\(v=sql.110\).aspx)</span></span>  
  
 <span data-ttu-id="c2829-172">インストール[SQL Server 2014](http://msdn.microsoft.com/library/bb500469\(v=sql.120\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c2829-172">Install [SQL Server 2014](http://msdn.microsoft.com/library/bb500469\(v=sql.120\).aspx)</span></span>  
  
 <span data-ttu-id="c2829-173">SQL Server をインストールするときに、次の機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2829-173">When you install SQL Server, select the following features:</span></span>  
  
- <span data-ttu-id="c2829-174">データベース エンジン サービス</span><span class="sxs-lookup"><span data-stu-id="c2829-174">Database Engine Services</span></span>  
  
  -   <span data-ttu-id="c2829-175">SQL Server のレプリケーション</span><span class="sxs-lookup"><span data-stu-id="c2829-175">SQL Server Replication</span></span>  
  
  -   <span data-ttu-id="c2829-176">フルテキスト検索</span><span class="sxs-lookup"><span data-stu-id="c2829-176">Full-Text Search</span></span>  
  
- <span data-ttu-id="c2829-177">Analysis Services</span><span class="sxs-lookup"><span data-stu-id="c2829-177">Analysis Services</span></span>  
  
- <span data-ttu-id="c2829-178">Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c2829-178">Reporting Services</span></span>  
  
- <span data-ttu-id="c2829-179">共有機能</span><span class="sxs-lookup"><span data-stu-id="c2829-179">Shared Features</span></span>  
  
  -   <span data-ttu-id="c2829-180">SQL Server Data Tools (SQL Server 2014/SQL Server 2012) または Business Intelligence Development Studio (SQL Server 2008 R2)</span><span class="sxs-lookup"><span data-stu-id="c2829-180">SQL Server Data Tools (SQL Server 2014 / SQL Server 2012) or Business Intelligence Development Studio (SQL Server 2008 R2)</span></span>  
  
       [<span data-ttu-id="c2829-181">SQL Server 2014 Data Tools をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c2829-181">Download SQL Server 2014 Data Tools</span></span>](http://www.microsoft.com/download/details.aspx?id=42313)  
  
  -   <span data-ttu-id="c2829-182">クライアント ツール接続</span><span class="sxs-lookup"><span data-stu-id="c2829-182">Client Tools Connectivity</span></span>  
  
  -   <span data-ttu-id="c2829-183">Integration Services</span><span class="sxs-lookup"><span data-stu-id="c2829-183">Integration Services</span></span>  
  
  -   <span data-ttu-id="c2829-184">管理ツール - 基本</span><span class="sxs-lookup"><span data-stu-id="c2829-184">Management Tools - Basic</span></span>  
  
      -   <span data-ttu-id="c2829-185">管理ツール - 完全</span><span class="sxs-lookup"><span data-stu-id="c2829-185">Management Tools - Complete</span></span>  
  
  <span data-ttu-id="c2829-186">**その他**</span><span class="sxs-lookup"><span data-stu-id="c2829-186">**Additional**</span></span>  
  
- <span data-ttu-id="c2829-187">BizTalk Server では、バイナリ照合順序を除く、大文字と小文字を区別する/区別しないすべての SQL Server 照合順序がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c2829-187">BizTalk Server supports all case-sensitive and case-insensitive SQL Server collations except for binary collations.</span></span> <span data-ttu-id="c2829-188">バイナリ照合順序はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="c2829-188">Binary collations are not supported.</span></span>  
  
- <span data-ttu-id="c2829-189">最適なパフォーマンスは、Microsoft では、SQL Server の Enterprise Edition を使用してお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c2829-189">For optimal performance, Microsoft recommends using the Enterprise Edition of SQL Server.</span></span> <span data-ttu-id="c2829-190">参照してください[SQL Server 2008 R2 エディション](http://msdn.microsoft.com/library/cc645993\(v=sql.105\).aspx)、 [SQL Server 2012 エディション](http://msdn.microsoft.com/library/cc645993\(v=sql.110\).aspx)、または[SQL Server 2014 エディション](http://msdn.microsoft.com/library/cc645993\(v=sql.120\).aspx)します。</span><span class="sxs-lookup"><span data-stu-id="c2829-190">See [SQL Server 2008 R2 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.105\).aspx), [SQL Server 2012 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.110\).aspx), or [SQL Server 2014 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.120\).aspx).</span></span>  
  
- <span data-ttu-id="c2829-191">サービス パックと Windows 更新プログラムがサポートされて、インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2829-191">Service packs and Windows Updates are supported and should be installed.</span></span>  
  
- <span data-ttu-id="c2829-192">BizTalk Server と SQL Server が別々 のコンピューター上にある場合は、分散トランザクション コーディネーター (MS DTC) は、コンピューター間のトランザクションを処理します。</span><span class="sxs-lookup"><span data-stu-id="c2829-192">When BizTalk Server and SQL Server are on separate computers, Distributed Transaction Coordinator (MS DTC) handles the transactions between the computers.</span></span> <span data-ttu-id="c2829-193">SQL Server AlwaysOn 機能は、MSDTC トランザクションをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="c2829-193">The SQL Server AlwaysOn feature does not support MSDTC transactions.</span></span> <span data-ttu-id="c2829-194">SQL Server AlwaysOn 機能がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c2829-194">The SQL Server AlwaysOn feature is not supported.</span></span>  
  
##  <a name="BKMK_MQSeries"></a> <span data-ttu-id="c2829-195">MQSeries の前提条件をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c2829-195">Install MQSeries Prerequisites</span></span>  
 <span data-ttu-id="c2829-196">**MQSeries アダプター**:BizTalk Server のインストールと共に自動的にインストールします。</span><span class="sxs-lookup"><span data-stu-id="c2829-196">**MQSeries adapter**: Automatically installed with the BizTalk Server installation.</span></span>  
  
 <span data-ttu-id="c2829-197">**MQSeries Client (MQSC) アダプター**:</span><span class="sxs-lookup"><span data-stu-id="c2829-197">**MQSeries Client (MQSC) adapter**:</span></span>  
  
1. <span data-ttu-id="c2829-198">Host Integration Server (HIS) インストールを実行します。</span><span class="sxs-lookup"><span data-stu-id="c2829-198">Run the Host Integration Server (HIS) installation</span></span>  
  
2. <span data-ttu-id="c2829-199">コンポーネントのインストール、展開**BizTalk Adapters**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-199">In component installation, expand **BizTalk Adapters**.</span></span>  
  
3. <span data-ttu-id="c2829-200">選択**BizTalk Adapter for WebSphere MQ (クライアント ベース)** します。</span><span class="sxs-lookup"><span data-stu-id="c2829-200">Select **BizTalk Adapter for WebSphere MQ (Client-Based)**.</span></span>  
  
   <span data-ttu-id="c2829-201">**サポートされている IBM WebSphere MQ バージョン**:</span><span class="sxs-lookup"><span data-stu-id="c2829-201">**Supported IBM WebSphere MQ versions**:</span></span>  
  
-   <span data-ttu-id="c2829-202">IBM WebSphere MQ 6.0.2.12 以降</span><span class="sxs-lookup"><span data-stu-id="c2829-202">IBM WebSphere MQ 6.0.2.12 and later</span></span>  
  
-   <span data-ttu-id="c2829-203">IBM WebSphere MQ 7.0.1.9 以降</span><span class="sxs-lookup"><span data-stu-id="c2829-203">IBM WebSphere MQ 7.0.1.9 and later</span></span>  
  
-   <span data-ttu-id="c2829-204">IBM WebSphere MQ 7.1.0.5 以降</span><span class="sxs-lookup"><span data-stu-id="c2829-204">IBM WebSphere MQ 7.1.0.5 and later</span></span>  
  
-   <span data-ttu-id="c2829-205">IBM WebSphere MQ 7.5.0.3 以降</span><span class="sxs-lookup"><span data-stu-id="c2829-205">IBM WebSphere MQ 7.5.0.3 and later</span></span>  
  
-   <span data-ttu-id="c2829-206">IBM WebSphere MQ 8 (実行時に限定。 管理 Api)</span><span class="sxs-lookup"><span data-stu-id="c2829-206">IBM WebSphere MQ 8 (limited to runtime; no administration APIs)</span></span>  
  
     <span data-ttu-id="c2829-207">MQ バージョン 8 のサポートが含まれます[Host Integration Server CU3](https://support.microsoft.com/kb/3019572)します。</span><span class="sxs-lookup"><span data-stu-id="c2829-207">MQ version 8 support is included with [Host Integration Server CU3](https://support.microsoft.com/kb/3019572).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2829-208">特定の WebSphere MQ バージョンが表示されない場合 MQ など 5.x では、その後はサポートされていませんこの BizTalk Server のバージョン。</span><span class="sxs-lookup"><span data-stu-id="c2829-208">If a specific WebSphere MQ version is not listed, like MQ 5.x, then it is not supported with this BizTalk Server version.</span></span>  
  
 <span data-ttu-id="c2829-209">**その他**</span><span class="sxs-lookup"><span data-stu-id="c2829-209">**Additional**</span></span>  
  
- <span data-ttu-id="c2829-210">ベスト プラクティスとして常に最新の WebSphere MQ 修正パックをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c2829-210">As a best practice, always install the latest WebSphere MQ fix pack.</span></span> <span data-ttu-id="c2829-211">参照してください[ http://www.ibm.com/support/docview.wss?uid=swg27006037](http://www.ibm.com/support/docview.wss?uid=swg27006037)します。</span><span class="sxs-lookup"><span data-stu-id="c2829-211">See [http://www.ibm.com/support/docview.wss?uid=swg27006037](http://www.ibm.com/support/docview.wss?uid=swg27006037).</span></span>  
  
- <span data-ttu-id="c2829-212">IBM WebSphere MQ は、Windows 以外のコンピューターにインストールする場合は、インストール、 **MQSAgent COM + アプリケーション**(MQSConfigWiz.exe) と**MQSeries Server for Windows**同じコンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="c2829-212">If IBM WebSphere MQ is installed on a non-Windows computer, install the **MQSAgent COM+ application** (MQSConfigWiz.exe) and **MQSeries Server for Windows** on the same computer.</span></span> <span data-ttu-id="c2829-213">IBM WebSphere MQ が Windows コンピューターにインストールされている場合、 **MQSAgent COM + アプリケーション**と**MQSeries Server for Windows**プログラムがないために使用および必要な。</span><span class="sxs-lookup"><span data-stu-id="c2829-213">If IBM WebSphere MQ is installed on a Windows computer, then the **MQSAgent COM+ application** and **MQSeries Server for Windows** program are not used or needed.</span></span>  
  
   <span data-ttu-id="c2829-214">**MQSConfigWiz.exe** BizTalk Server インストール ファイルに含まれています。</span><span class="sxs-lookup"><span data-stu-id="c2829-214">**MQSConfigWiz.exe** is included in the BizTalk Server installation files.</span></span>  
  
   <span data-ttu-id="c2829-215">**MQSeries Server for Windows** Microsoft プログラムでないし、IBM WebSphere MQ プログラムから入手する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2829-215">**MQSeries Server for Windows** is not a Microsoft program and must be obtained with your IBM WebSphere MQ program.</span></span>  
  
- <span data-ttu-id="c2829-216">[MQSeries アダプター](http://technet.microsoft.com/library/aa547973\(v=BTS.80\).aspx)異なるコンポーネント構成など、MQSeries アダプターについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="c2829-216">[MQSeries Adapter](http://technet.microsoft.com/library/aa547973\(v=BTS.80\).aspx) provides more information on the MQSeries adapter, including configuring the different components.</span></span> <span data-ttu-id="c2829-217">[BizTalk Server:MQSeries と MQSeries Client (MQSC) アダプター](http://social.technet.microsoft.com/wiki/contents/articles/18316.biztalk-server-mqseries-and-mqseries-client-mqsc-adapters.aspx) MQSeries と MQSC のアダプターの追加の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="c2829-217">[BizTalk Server: MQSeries and MQSeries Client (MQSC) adapters](http://social.technet.microsoft.com/wiki/contents/articles/18316.biztalk-server-mqseries-and-mqseries-client-mqsc-adapters.aspx) provides additional details on the MQSeries and MQSC adapters.</span></span>  
  
- <span data-ttu-id="c2829-218">IBM WebSphere はマイクロソフト製品ではないは Microsoft によってサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c2829-218">IBM WebSphere is not a Microsoft product and is not supported by Microsoft.</span></span> <span data-ttu-id="c2829-219">Microsoft では、このプログラムの適合性に関する保証はありません。</span><span class="sxs-lookup"><span data-stu-id="c2829-219">Microsoft makes no guarantees about the suitability of this program.</span></span> <span data-ttu-id="c2829-220">ダウンロードの手順を含む、IBM WebSphere MQ の詳細については、www.ibm.com を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2829-220">For more information about IBM WebSphere MQ, including download instructions, see www.ibm.com.</span></span>  
  
##  <a name="BKMK_BAMAlerts"></a> <span data-ttu-id="c2829-221">BAM 警告</span><span class="sxs-lookup"><span data-stu-id="c2829-221">BAM Alerts</span></span>  
 <span data-ttu-id="c2829-222">BAM 警告の SQL Server 2012 と新しいバージョンでは、SQL Server でデータベース メールを使用します。</span><span class="sxs-lookup"><span data-stu-id="c2829-222">BAM Alerts with SQL Server 2012 and newer versions use Database Mail in SQL Server.</span></span> <span data-ttu-id="c2829-223">BAM 警告では、SQL Server 2008 R2 と以前のバージョンでは、SQL Notification Services を使用します。</span><span class="sxs-lookup"><span data-stu-id="c2829-223">BAM Alerts with SQL Server 2008 R2 and older versions use SQL Notification Services.</span></span> <span data-ttu-id="c2829-224">インストールまたは BAM 警告の構成、前に SQL Server での Notification Services またはデータベース メールを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2829-224">Before installing or configuring BAM Alerts, you must configure the Notification Services or Database Mail in SQL Server.</span></span>  
  
###  <a name="BKMK_DBMail"></a> <span data-ttu-id="c2829-225">SQL Server 2012/2014 を使用して BAM 警告</span><span class="sxs-lookup"><span data-stu-id="c2829-225">BAM Alerts using SQL Server 2012/2014</span></span>  
 <span data-ttu-id="c2829-226">構成[SQL Server 2012 データベース メール](http://msdn.microsoft.com/library/hh245116\(v=sql.110\).aspx)します。</span><span class="sxs-lookup"><span data-stu-id="c2829-226">Configure [SQL Server 2012 Database Mail](http://msdn.microsoft.com/library/hh245116\(v=sql.110\).aspx).</span></span>  
  
 <span data-ttu-id="c2829-227">構成[SQL Server 2014 Database Mail](http://msdn.microsoft.com/library/hh245116\(v=sql.120\).aspx)します。</span><span class="sxs-lookup"><span data-stu-id="c2829-227">Configure [SQL Server 2014 Database Mail](http://msdn.microsoft.com/library/hh245116\(v=sql.120\).aspx).</span></span>  
  
 <span data-ttu-id="c2829-228">**その他**</span><span class="sxs-lookup"><span data-stu-id="c2829-228">**Additional**</span></span>  
  
-   <span data-ttu-id="c2829-229">データベース メールでは、SMTP サーバーを使用して、BAM 警告を送信します。</span><span class="sxs-lookup"><span data-stu-id="c2829-229">Database Mail uses an SMTP server to send the BAM Alerts.</span></span> <span data-ttu-id="c2829-230">SMTP サーバーは、BizTalk サーバーまたは別の IIS サーバー上でローカルにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="c2829-230">SMTP Server can be installed locally on the BizTalk Server or on another IIS server.</span></span> <span data-ttu-id="c2829-231">[付録 d:SMTP サーバーの作成](../install-and-config-guides/appendix-d-create-the-smtp-server.md)をインストールして、SMTP サーバーを構成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2829-231">[Appendix D: Create the SMTP Server](../install-and-config-guides/appendix-d-create-the-smtp-server.md) lists the steps to install and configure a SMTP Server.</span></span>  
  
###  <a name="BKMK_SSNS"></a> <span data-ttu-id="c2829-232">SQL Server 2008 R2 の SQL Server の 2005 Notification Services をインストールを使用して BAM 警告</span><span class="sxs-lookup"><span data-stu-id="c2829-232">BAM Alerts using SQL Server 2008 R2 – Install SQL Server 2005 Notification Services</span></span>  
  
1. <span data-ttu-id="c2829-233">移動して[Microsoft SQL Server 2005 SP4 用 Feature Pack](http://go.microsoft.com/fwlink/p/?LinkId=286285)します。</span><span class="sxs-lookup"><span data-stu-id="c2829-233">Go to [Feature Pack for Microsoft SQL Server 2005 SP4](http://go.microsoft.com/fwlink/p/?LinkId=286285).</span></span>  
  
2. <span data-ttu-id="c2829-234">ダウンロードして、次のコンポーネントに適したプラットフォーム パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c2829-234">Download and install the appropriate platform package for the following components:</span></span>  
  
    <span data-ttu-id="c2829-235">**Microsoft SQL Server Native Client**</span><span class="sxs-lookup"><span data-stu-id="c2829-235">**Microsoft SQL Server Native Client**</span></span>  
  
   - <span data-ttu-id="c2829-236">HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli.msi>"X86 パッケージ (sqlncli.msi)</span><span class="sxs-lookup"><span data-stu-id="c2829-236">HYPERLINK "<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli.msi>" X86 Package (sqlncli.msi)</span></span>  
  
   - <span data-ttu-id="c2829-237">HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli_x64.msi>"X64 パッケージ (sqlncli_x64.msi)</span><span class="sxs-lookup"><span data-stu-id="c2829-237">HYPERLINK "<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli_x64.msi>" X64 Package (sqlncli_x64.msi)</span></span>  
  
     <span data-ttu-id="c2829-238">**Microsoft SQL Server 2005 管理オブジェクト コレクション**</span><span class="sxs-lookup"><span data-stu-id="c2829-238">**Microsoft SQL Server 2005 Management Objects Collection**</span></span>  
  
   - <span data-ttu-id="c2829-239">HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO.msi>"X86 パッケージ (SQLServer2005_XMO.msi)</span><span class="sxs-lookup"><span data-stu-id="c2829-239">HYPERLINK "<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO.msi>" X86 Package (SQLServer2005_XMO.msi)</span></span>  
  
   - <span data-ttu-id="c2829-240">HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO_x64.msi>"X64 パッケージ (SQLServer2005_XMO_x64.msi)</span><span class="sxs-lookup"><span data-stu-id="c2829-240">HYPERLINK "<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO_x64.msi>" X64 Package (SQLServer2005_XMO_x64.msi)</span></span>  
  
     <span data-ttu-id="c2829-241">**Microsoft SQL Server 2005 Notification Services クライアント コンポーネント**</span><span class="sxs-lookup"><span data-stu-id="c2829-241">**Microsoft SQL Server 2005 Notification Services Client Components**</span></span>  
  
   - <span data-ttu-id="c2829-242">HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS.msi>"X86 パッケージ (SQLServer2005_NS.msi)</span><span class="sxs-lookup"><span data-stu-id="c2829-242">HYPERLINK "<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS.msi>" X86 Package (SQLServer2005_NS.msi)</span></span>  
  
   - <span data-ttu-id="c2829-243">HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS_x64.msi>"X64 パッケージ (SQLServer2005_NS_x64.msi)</span><span class="sxs-lookup"><span data-stu-id="c2829-243">HYPERLINK "<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS_x64.msi>" X64 Package (SQLServer2005_NS_x64.msi)</span></span>  
  
   <span data-ttu-id="c2829-244">**その他**</span><span class="sxs-lookup"><span data-stu-id="c2829-244">**Additional**</span></span>  
  
-   <span data-ttu-id="c2829-245">SQL Notification Services は; を構成する必要はありません。BizTalk Server にインストールされているだけです。</span><span class="sxs-lookup"><span data-stu-id="c2829-245">SQL Notification Services does not need to be configured; only installed on the BizTalk Server.</span></span>  
  
##  <a name="BKMK_WIF"></a> <span data-ttu-id="c2829-246">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="c2829-246">Windows Identity Foundation</span></span>  
  
|                                                              |                                                                                                                                                                                      |
|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="c2829-247">Windows 8.1、Windows Server 2012、および Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="c2829-247">Windows 8.1, Windows Server 2012, and Windows Server 2012 R2</span></span> |                                <span data-ttu-id="c2829-248">Windows Identity Foundation が機能として、オペレーティング システムに含まれている**オンまたはオフにする Windows 機能**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-248">Windows Identity Foundation is included with the operating system as a Feature in **Turn Windows features on or off**.</span></span>                                |
|                      <span data-ttu-id="c2829-249">Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="c2829-249">Windows Vista SP1</span></span>                       | <span data-ttu-id="c2829-250">ダウンロードできます[Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331) HYPERLINK"<http://www.microsoft.com/download/details.aspx?id=17331>"。</span><span class="sxs-lookup"><span data-stu-id="c2829-250">Download available at [Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331) HYPERLINK "<http://www.microsoft.com/download/details.aspx?id=17331>" .</span></span> |
  
 <span data-ttu-id="c2829-251">**その他**</span><span class="sxs-lookup"><span data-stu-id="c2829-251">**Additional**</span></span>  
  
-   <span data-ttu-id="c2829-252">Windows Identity Foundation (WIF) は、SharePoint アダプターまたは SharePoint クライアント側オブジェクト モデル (CSOM) を使用すると SharePoint Online に必要です。</span><span class="sxs-lookup"><span data-stu-id="c2829-252">Windows Identity Foundation (WIF) is required for the SharePoint adapter or SharePoint Online when used with SharePoint Client Side Object Model (CSOM).</span></span> <span data-ttu-id="c2829-253">具体的な内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c2829-253">Specifically:</span></span>  
  
    |<span data-ttu-id="c2829-254">インストール オプション</span><span class="sxs-lookup"><span data-stu-id="c2829-254">Installation Option</span></span>|<span data-ttu-id="c2829-255">WIF が必要</span><span class="sxs-lookup"><span data-stu-id="c2829-255">WIF Required</span></span>|  
    |-------------------------|------------------|  
    |<span data-ttu-id="c2829-256">CSOM を使用した SharePoint アダプター</span><span class="sxs-lookup"><span data-stu-id="c2829-256">SharePoint Adapter with CSOM</span></span>|<span data-ttu-id="c2829-257">はい</span><span class="sxs-lookup"><span data-stu-id="c2829-257">Yes</span></span>|  
    |<span data-ttu-id="c2829-258">SharePoint Online CSOM を使用しました。</span><span class="sxs-lookup"><span data-stu-id="c2829-258">SharePoint Online with CSOM</span></span>|<span data-ttu-id="c2829-259">はい</span><span class="sxs-lookup"><span data-stu-id="c2829-259">Yes</span></span>|  
    |<span data-ttu-id="c2829-260">SharePoint アダプター Web サービスを (非推奨)</span><span class="sxs-lookup"><span data-stu-id="c2829-260">SharePoint Adapter Web Service (deprecated)</span></span>|<span data-ttu-id="c2829-261">いいえ</span><span class="sxs-lookup"><span data-stu-id="c2829-261">No</span></span>|  
    |<span data-ttu-id="c2829-262">SharePoint なし</span><span class="sxs-lookup"><span data-stu-id="c2829-262">No SharePoint</span></span>|<span data-ttu-id="c2829-263">いいえ</span><span class="sxs-lookup"><span data-stu-id="c2829-263">No</span></span>|  
  
-   <span data-ttu-id="c2829-264">[付録 b:Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)SharePoint のインストール オプションで特定の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c2829-264">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) provides specific information on the SharePoint installation options.</span></span>  
  
##  <a name="BKMK_WSS"></a> <span data-ttu-id="c2829-265">インストールおよび Microsoft SharePoint の構成</span><span class="sxs-lookup"><span data-stu-id="c2829-265">Install and Configure Microsoft SharePoint</span></span>  
 <span data-ttu-id="c2829-266">インストール[SharePoint 2013](http://technet.microsoft.com/library/cc303424.aspx)</span><span class="sxs-lookup"><span data-stu-id="c2829-266">Install [SharePoint 2013](http://technet.microsoft.com/library/cc303424.aspx)</span></span>  
  
 <span data-ttu-id="c2829-267">インストール[SharePoint Online サービス](http://technet.microsoft.com/library/jj819267.aspx)</span><span class="sxs-lookup"><span data-stu-id="c2829-267">Install [SharePoint Online Service](http://technet.microsoft.com/library/jj819267.aspx)</span></span>  
  
 <span data-ttu-id="c2829-268">インストール[SharePoint Server 2010](http://technet.microsoft.com/library/cc303424\(v=office.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c2829-268">Install [SharePoint Server 2010](http://technet.microsoft.com/library/cc303424\(v=office.14\).aspx)</span></span>  
  
 <span data-ttu-id="c2829-269">インストール[SharePoint 2007](http://technet.microsoft.com/library/cc303424\(v=office.12\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c2829-269">Install [SharePoint 2007](http://technet.microsoft.com/library/cc303424\(v=office.12\).aspx)</span></span>  
  
 <span data-ttu-id="c2829-270">**その他**</span><span class="sxs-lookup"><span data-stu-id="c2829-270">**Additional**</span></span>  
  
-   <span data-ttu-id="c2829-271">SharePoint をインストールする場合は、残りの BizTalk Server の前提条件を続行する前にこれを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2829-271">If you are installing SharePoint, you must do so before continuing with the remaining BizTalk Server prerequisites.</span></span>  
  
-   <span data-ttu-id="c2829-272">インストールと SharePoint の構成は、次の手順で構成されます。</span><span class="sxs-lookup"><span data-stu-id="c2829-272">Installing and configuring SharePoint consists of the following procedures:</span></span>  
  
    -   <span data-ttu-id="c2829-273">SharePoint をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c2829-273">Install SharePoint</span></span>  
  
    -   <span data-ttu-id="c2829-274">SharePoint を構成します。</span><span class="sxs-lookup"><span data-stu-id="c2829-274">Configure SharePoint</span></span>  
  
    -   <span data-ttu-id="c2829-275">仮想サーバーとして既定の Web サイトを拡張します。</span><span class="sxs-lookup"><span data-stu-id="c2829-275">Extend the default Web site as a virtual server</span></span>  
  
-   <span data-ttu-id="c2829-276">[付録 b:Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)BizTalk Server の SharePoint アダプターのインストール オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c2829-276">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) describes the SharePoint adapter installation options for BizTalk Server.</span></span>  
  
-   <span data-ttu-id="c2829-277">SharePoint アダプターを使用する場合は、SharePoint サービス Web サービスではなく新しい CSOM オプションをインストール勧め説明されている[付録 b:Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="c2829-277">When using the SharePoint adapter, it is recommended to install the new CSOM option instead of the SharePoint Service Web Service; described at [Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md).</span></span>  
  
##  <a name="BKMK_SharedMem"></a> <span data-ttu-id="c2829-278">共有メモリ プロトコルを無効にします。</span><span class="sxs-lookup"><span data-stu-id="c2829-278">Disable the Shared Memory Protocol</span></span>  
  
1. <span data-ttu-id="c2829-279">**[SQL Server 構成マネージャー]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="c2829-279">Open **SQL Server Configuration Manager**.</span></span>  
  
2. <span data-ttu-id="c2829-280">**SQL Server 構成マネージャー**、展開**SQL Server ネットワーク構成**、し、 **MSSQLSERVER のプロトコル**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-280">In **SQL Server Configuration Manager**, expand **SQL Server Network Configuration**, and then select **Protocols for MSSQLSERVER**.</span></span>  
  
3. <span data-ttu-id="c2829-281">**[共有メモリ]** を右クリックし、**[無効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2829-281">Right-click **Shared Memory**, and then select **Disable**.</span></span>  
  
4. <span data-ttu-id="c2829-282">選択**SQL Server サービス**を右クリックして**SQL Server (MSSQLSERVER)**、し、**停止**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-282">Select **SQL Server Services**, right-click **SQL Server (MSSQLSERVER)**, and then select **Stop**.</span></span> <span data-ttu-id="c2829-283">右クリックし、サービスが停止したら、 **SQL Server (MSSQLSERVER)** もう一度、し、**開始**。</span><span class="sxs-lookup"><span data-stu-id="c2829-283">After the service has stopped, right-click **SQL Server (MSSQLSERVER)** again, and then select **Start**.</span></span>  
  
5. <span data-ttu-id="c2829-284">**SQL Server 構成マネージャー**を終了します。</span><span class="sxs-lookup"><span data-stu-id="c2829-284">Close **SQL Server Configuration Manager**.</span></span>  
  
   <span data-ttu-id="c2829-285">**その他**</span><span class="sxs-lookup"><span data-stu-id="c2829-285">**Additional**</span></span>  
  
-   <span data-ttu-id="c2829-286">ある種のストレス条件下では (たとえば、同じコンピューターから複数のクライアントが SQL Server にアクセスしている場合)、SQL Server の共有メモリ プロトコルが原因で BizTalk Server のパフォーマンスが低下することがあります。</span><span class="sxs-lookup"><span data-stu-id="c2829-286">Under certain stress conditions (such as clients accessing SQL Server from the same computer), the SQL Server Shared Memory protocol may lower BizTalk Server performance.</span></span> <span data-ttu-id="c2829-287">この問題を解決するには、SQL Server ネットワークの構成で、共有メモリ ネットワーク プロトコルを無効にします。</span><span class="sxs-lookup"><span data-stu-id="c2829-287">You can resolve this behavior by disabling the Shared Memory network protocol in SQL Server Network Configuration.</span></span>  
  
-   <span data-ttu-id="c2829-288">ReplaceThisText</span><span class="sxs-lookup"><span data-stu-id="c2829-288">ReplaceThisText</span></span>  
  
##  <a name="BKMK_LocalAdmin"></a> <span data-ttu-id="c2829-289">ローカルの Administrators グループに参加します。</span><span class="sxs-lookup"><span data-stu-id="c2829-289">Join the Local Administrators Group</span></span>  
 <span data-ttu-id="c2829-290">**Windows Server 2012** :[Windows Server 2012:ローカル管理者グループにアカウントを追加する方法](http://social.technet.microsoft.com/wiki/contents/articles/13436.windows-server-2012-how-to-add-an-account-to-a-local-administrator-group.aspx)</span><span class="sxs-lookup"><span data-stu-id="c2829-290">**Windows Server 2012** : [Windows Server 2012: How to Add an Account to a Local Administrator Group](http://social.technet.microsoft.com/wiki/contents/articles/13436.windows-server-2012-how-to-add-an-account-to-a-local-administrator-group.aspx)</span></span>  
  
 <span data-ttu-id="c2829-291">**Windows 8.1**:Windows 8 でローカル ユーザーとグループを開くには、キーボードと型の Windows ボタンをクリックして**グループ**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-291">**Windows 8.1**: To open Local Users and Groups on Windows 8, click the Windows button on the keyboard and type **groups**.</span></span> <span data-ttu-id="c2829-292">[検索] ウィンドウで、次のようにクリックします。**設定**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-292">In the Search window, click **Settings**.</span></span> <span data-ttu-id="c2829-293">結果ウィンドウで次のようにクリックします。**ローカル ユーザーとグループの編集**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-293">In the Results window, click **Edit local users and groups**.</span></span> <span data-ttu-id="c2829-294">クリックして**グループ**し、アカウントを追加する管理者をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2829-294">Click **Groups** and then double-click Administrators to add an account.</span></span>  
  
 <span data-ttu-id="c2829-295">**Windows 7 SP1**:[開始] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2829-295">**Windows 7 SP1**: Click Start.</span></span> <span data-ttu-id="c2829-296">**検索**テキスト ボックスに「**コンピュータの管理**、 をクリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="c2829-296">In the **Search** text box, type **Computer Management**, and click it to open.</span></span> <span data-ttu-id="c2829-297">展開**ローカル ユーザーとグループ**、 をクリックして**グループ**、し、アカウントを追加する管理者をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2829-297">Expand **Local Users and Groups**, click **Groups**, and then double-click Administrators to add an account.</span></span>  
  
 <span data-ttu-id="c2829-298">**その他**</span><span class="sxs-lookup"><span data-stu-id="c2829-298">**Additional**</span></span>  
  
-   <span data-ttu-id="c2829-299">インストールして、BizTalk Server を構成するには、ローカルの Administrators グループのメンバーがあります。</span><span class="sxs-lookup"><span data-stu-id="c2829-299">You must be a member of the local Administrators group to install and configure BizTalk Server.</span></span>  
  
##  <a name="BKMK_AppLog"></a> <span data-ttu-id="c2829-300">アプリケーション イベント ログを構成します。</span><span class="sxs-lookup"><span data-stu-id="c2829-300">Configure the Application Event Log</span></span>  
  
1. <span data-ttu-id="c2829-301">開いている**イベント ビューアー**:</span><span class="sxs-lookup"><span data-stu-id="c2829-301">Open **Event Viewer**:</span></span>  
  
    <span data-ttu-id="c2829-302">**Windows Server 2012** :キーボードと型の Windows ボタンをクリックします。**イベント ビューアー**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-302">**Windows Server 2012** : Click the Windows button on the keyboard and type **Event Viewer**.</span></span> <span data-ttu-id="c2829-303">結果ウィンドウで次のようにクリックします。**イベント ビューアー**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-303">In the Results window, click **Event Viewer**.</span></span>  
  
    <span data-ttu-id="c2829-304">**Windows 8.1**:キーボードと型の Windows ボタンをクリックします。**イベント ビューアー**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-304">**Windows 8.1**: Click the Windows button on the keyboard and type **Event Viewer**.</span></span> <span data-ttu-id="c2829-305">[検索] ウィンドウで、次のようにクリックします。**設定**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-305">In the Search window, click **Settings**.</span></span> <span data-ttu-id="c2829-306">結果ウィンドウで次のようにクリックします。**イベント ログを表示**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-306">In the Results window, click **View event logs**.</span></span>  
  
    <span data-ttu-id="c2829-307">**Windows 7 SP1**:[開始] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2829-307">**Windows 7 SP1**: Click Start.</span></span> <span data-ttu-id="c2829-308">**検索**テキスト ボックスに「**イベント ビューアー** をクリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="c2829-308">In the **Search** text box, type **Event Viewer**, and click it to open.</span></span>  
  
2. <span data-ttu-id="c2829-309">展開**Windows ログ**を右クリックして**アプリケーション**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-309">Expand **Windows Logs**, right-click **Application**, and then click **Properties**.</span></span> <span data-ttu-id="c2829-310">**ログ プロパティ**:</span><span class="sxs-lookup"><span data-stu-id="c2829-310">In **Log Properties**:</span></span>  
  
   -   <span data-ttu-id="c2829-311">使用可能な空き領域を確認するには、**[ログ サイズ]** と **[最大ログ サイズ]** のプロパティを比較します。</span><span class="sxs-lookup"><span data-stu-id="c2829-311">To determine the available space, compare the **Log Size** and the **Maximum log size** properties.</span></span>  
  
   -   <span data-ttu-id="c2829-312">多くの領域を提供するには、上位の番号を入力します。**最大ログ サイズ**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-312">To provide more space, enter a higher number in **Maximum log size**.</span></span>  
  
   -   <span data-ttu-id="c2829-313">ログの空き領域がなくなったときに古いイベントが上書きされるようにするには、**[必要に応じてイベントを上書きする]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2829-313">To enable overwriting of old events when the log becomes full, select **Overwrite events as needed**.</span></span>  
  
   -   <span data-ttu-id="c2829-314">ログ イベントを消去するには、**[ログの消去]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2829-314">To clear the log events, select **Clear log**.</span></span>  
  
3. <span data-ttu-id="c2829-315">をクリックして**OK**を閉じる、**イベント ビューアー**します。</span><span class="sxs-lookup"><span data-stu-id="c2829-315">Click **OK** to close the **Event Viewer**.</span></span>  
  
   <span data-ttu-id="c2829-316">**その他**</span><span class="sxs-lookup"><span data-stu-id="c2829-316">**Additional**</span></span>  
  
-   <span data-ttu-id="c2829-317">BizTalk Server のセットアップを実行すると、イベントの記録がアプリケーション イベント ログに保存されます。</span><span class="sxs-lookup"><span data-stu-id="c2829-317">BizTalk Server setup keeps a record of events in the Application Event Log.</span></span> <span data-ttu-id="c2829-318">インストールされる BizTalk Server の機能によっては、ログの空き領域を超える大きさのログが作成されることもあります。</span><span class="sxs-lookup"><span data-stu-id="c2829-318">Depending on the BizTalk Server features installed, the amount of space required in the log may exceed its limit.</span></span> <span data-ttu-id="c2829-319">BizTalk Server のセットアップ中に、アプリケーション イベント ログの領域が不足している場合、インストールは失敗します。</span><span class="sxs-lookup"><span data-stu-id="c2829-319">If the application event log runs out of space during BizTalk Server setup, the installation fails.</span></span> <span data-ttu-id="c2829-320">アプリケーション イベント ログの設定を変更すれば、この失敗を回避できます。</span><span class="sxs-lookup"><span data-stu-id="c2829-320">Changing the Application Event Log settings prevents this failure.</span></span>  
  
## <a name="next"></a><span data-ttu-id="c2829-321">Next</span><span class="sxs-lookup"><span data-stu-id="c2829-321">Next</span></span>  
 [<span data-ttu-id="c2829-322">BizTalk Server の機能とコンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="c2829-322">Choose BizTalk Server Features and Components</span></span>](http://msdn.microsoft.com/library/b8c43fcf-9e5c-48ba-830b-13a5177e30f0)  
  
## <a name="see-also"></a><span data-ttu-id="c2829-323">参照</span><span class="sxs-lookup"><span data-stu-id="c2829-323">See Also</span></span>  
 <span data-ttu-id="c2829-324">[BizTalk Server 2013 および 2013 R2 のインストールの概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span><span class="sxs-lookup"><span data-stu-id="c2829-324">[Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span></span>  
 <span data-ttu-id="c2829-325">[付録 a:サイレント インストール](../install-and-config-guides/appendix-a-silent-installation.md) </span><span class="sxs-lookup"><span data-stu-id="c2829-325">[Appendix A: Silent Installation](../install-and-config-guides/appendix-a-silent-installation.md) </span></span>  
 <span data-ttu-id="c2829-326">[付録 b:Microsoft SharePoint アダプターをインストールします。](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="c2829-326">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) </span></span>  
 <span data-ttu-id="c2829-327">[付録 c:再頒布可能 CAB ファイル](../install-and-config-guides/appendix-c-redistributable-cab-files.md) </span><span class="sxs-lookup"><span data-stu-id="c2829-327">[Appendix C: Redistributable CAB Files](../install-and-config-guides/appendix-c-redistributable-cab-files.md) </span></span>  
 [<span data-ttu-id="c2829-328">付録 d:SMTP サーバーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2829-328">Appendix D: Create the SMTP Server</span></span>](../install-and-config-guides/appendix-d-create-the-smtp-server.md)
