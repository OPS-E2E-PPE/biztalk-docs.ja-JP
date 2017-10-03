---
title: "HTTPSSO (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- SSO, examples
- SSO, HTTP adapters
- examples, HTTP adapters
- HTTP adapters, SSO
- examples, SSO
ms.assetid: 322360df-81d2-4a73-9512-bda9382351a2
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f056b05c492e0ca4151c5a70652ee74ea46a464
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="httpsso-biztalk-server-sample"></a><span data-ttu-id="a2b71-102">HTTPSSO (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="a2b71-102">HTTPSSO (BizTalk Server Sample)</span></span>
<span data-ttu-id="a2b71-103">HTTPSSO サンプルでは、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP アダプタでエンタープライズ シングル サインオン (SSO) を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-103">The HTTPSSO sample demonstrates how to use the Enterprise Single Sign-On (SSO) feature with the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2b71-104">このサンプルは、64 ビット オペレーティング システムに対応していません。</span><span class="sxs-lookup"><span data-stu-id="a2b71-104">This sample is not supported on 64-bit operating systems.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="a2b71-105">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="a2b71-105">What This Sample Does</span></span>  
 <span data-ttu-id="a2b71-106">このサンプルでは、SSO と BizTalk HTTP 送信アダプターおよび受信アダプターを使用して、SSO により、Windows が資格情報を認証した後に、ユーザーが Microsoft Windows 以外のシステムにログオンするために他の資格情報を指定せずに済む方法をシミュレートするエンドツーエンド シナリオを示します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-106">This sample demonstrates an end-to-end scenario that uses SSO and the BizTalk HTTP Send and Receive adapters to simulate how SSO allows a user to avoid supplying additional credentials to log on to non-Microsoft Windows systems after Windows authenticates them.</span></span>  
  
 <span data-ttu-id="a2b71-107">このサンプルでは、SSO の管理モジュールとマッピング モジュールを使用して、SSO の相互運用機能クライアント DLL により、関連アプリケーションと SSO マッピングも作成します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-107">The sample also uses the administration and mapping modules of SSO to create affiliate application and SSO mappings using the interop client DLL of SSO.</span></span>  
  
 <span data-ttu-id="a2b71-108">エンドツーエンド シナリオの次の側面を実装することで、SSO の使用を示します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-108">The sample demonstrates the use of SSO by implementing the following aspects of an end-to-end scenario:</span></span>  
  
-   <span data-ttu-id="a2b71-109">Windows 統合認証を使用するように構成された、Microsoft インターネット インフォメーション サービス (IIS) 仮想ディレクトリで表されるユーザー インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="a2b71-109">User interface, represented by a Microsoft Internet Information Services (IIS) virtual directory configured to use Windows integrated authentication.</span></span>  
  
-   <span data-ttu-id="a2b71-110">基本認証を使用するように構成された IIS 仮想ディレクトリで表されるバックエンド システム。</span><span class="sxs-lookup"><span data-stu-id="a2b71-110">Back-end system, represented by an IIS virtual directory configured to use basic authentication.</span></span>  
  
-   <span data-ttu-id="a2b71-111">SQL サンプル データベース Northwind で表されるバックエンド データベース。</span><span class="sxs-lookup"><span data-stu-id="a2b71-111">Back-end database, represented by the SQL sample database Northwind.</span></span>  
  
 <span data-ttu-id="a2b71-112">このサンプルは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と SSO がインストールされていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="a2b71-112">This sample assumes that you have installed [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SSO.</span></span> <span data-ttu-id="a2b71-113">管理者特権が必要[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]IIS、SSO、および COM + は Windows XP Professional にします。</span><span class="sxs-lookup"><span data-stu-id="a2b71-113">You must have administrator privileges for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], IIS, SSO, and COM+ on Windows XP Professional.</span></span> <span data-ttu-id="a2b71-114">SSO 管理者、BizTalk Server 管理者、および BizTalk 分離ホスト ユーザーの各 Windows グループのメンバであることも必要です。</span><span class="sxs-lookup"><span data-stu-id="a2b71-114">You must also be a member of SSO Administrators, BizTalk Server Administrators, and BizTalk Isolated Host Users Windows groups.</span></span>  
  
 <span data-ttu-id="a2b71-115">このサンプルを効果的に使用するには、SSO と BizTalk HTTP アダプタに関する十分な知識があることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="a2b71-115">Effective use of this sample assumes that you have sufficient knowledge of SSO and the BizTalk HTTP adapter.</span></span> <span data-ttu-id="a2b71-116">たとえば、SSO のコンテキストで関連アプリケーションとは何かを理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2b71-116">For example, you should know what an affiliate application is in the context of SSO.</span></span> <span data-ttu-id="a2b71-117">これらのトピックについては、次を参照してください。[を使用して SSO](../core/using-sso.md)です。</span><span class="sxs-lookup"><span data-stu-id="a2b71-117">For information about these topics, see [Using SSO](../core/using-sso.md).</span></span> <span data-ttu-id="a2b71-118">参照してください[HTTP アダプター](../core/http-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="a2b71-118">Also see [HTTP Adapter](../core/http-adapter.md).</span></span>  
  
 <span data-ttu-id="a2b71-119">構成が完了すると、このサンプルは次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-119">After you complete the configuration, this sample works as follows:</span></span>  
  
1.  <span data-ttu-id="a2b71-120">クリックすると、**完了**でこのサンプルのユーザー インターフェイスを構成するウィザード アプリケーションを Internet Explorer のインスタンスが起動し、BizTalk HTTP Receive DLL の URL を渡します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-120">When you click **Finish** in the wizard application that comprises the user interface for this sample, an instance of Internet Explorer starts and passes the URL of the BizTalk HTTP Receive DLL.</span></span>  
  
2.  <span data-ttu-id="a2b71-121">BizTalk Server は SSO を利用して、基本認証で構成された IIS 仮想ディレクトリのファイル EmployeeData.aspx に HTTP 要求を効率的に転送します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-121">BizTalk Server, with the help of SSO, effectively forwards the HTTP request to the file EmployeeData.aspx in an IIS virtual directory that has been configured with basic authentication.</span></span> <span data-ttu-id="a2b71-122">この ASPX ファイルは、Windows 以外のバックエンド システムへのエントリ ポイントをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="a2b71-122">This ASPX file simulates the entry point into a non-Windows back-end system.</span></span> <span data-ttu-id="a2b71-123">SSO を使用しているために、HTTP 要求には、シミュレートされたバックエンド システムへのログオン アカウントをシミュレートする構成済みの資格情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a2b71-123">Because you are using SSO, the HTTP request includes the configured credentials that simulate a logon account to the simulated back-end system.</span></span>  
  
3.  <span data-ttu-id="a2b71-124">ASPX ファイルは、変更された SQL サンプル データベース Northwind にアクセスし、シミュレートされたバックエンド システム資格情報に対応する従業員データを取得します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-124">The ASPX file accesses a modified version of the SQL sample database Northwind to retrieve employee data corresponding to the simulated back-end system credentials.</span></span>  
  
4.  <span data-ttu-id="a2b71-125">ASPX ファイルは、取得された従業員データを HTTP 応答で返します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-125">The ASPX file returns the retrieved employee data in an HTTP response.</span></span>  
  
5.  <span data-ttu-id="a2b71-126">BizTalk Server は HTTP 応答を Internet Explorer にルーティングし、Internet Explorer は返された従業員データをユーザーに表示します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-126">BizTalk Server routes the HTTP response to Internet Explorer, which displays the returned employee data to the user.</span></span>  
  
 <span data-ttu-id="a2b71-127">BizTalk Server と SSO を省略し、ファイル EmployeeData.aspx を直接参照すると、[Windows] ダイアログ ボックスが表示され、資格情報を要求されます。</span><span class="sxs-lookup"><span data-stu-id="a2b71-127">If you bypass BizTalk Server and SSO, and browse directly to the file EmployeeData.aspx, a Windows dialog box will prompt you for your credentials.</span></span>  
  
 <span data-ttu-id="a2b71-128">コマンド ライン ユーティリティ ssomanage.exe を使用して関連アプリケーションやユーザー マッピングの作成など、SSO を構成する方法を示すサンプルについては、次を参照してください。[管理 (BizTalk Server サンプル)](../core/manage-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="a2b71-128">For a sample that shows how to use the command-line utility ssomanage.exe to configure SSO, such as creating affiliate applications and user mappings, see [Manage (BizTalk Server Sample)](../core/manage-biztalk-server-sample.md).</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="a2b71-129">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="a2b71-129">Where to Find This Sample</span></span>  
 <span data-ttu-id="a2b71-130">\<*パスのサンプル*> \SSO\HTTPSSO\\</span><span class="sxs-lookup"><span data-stu-id="a2b71-130">\<*Samples Path*>\SSO\HTTPSSO\\</span></span>  
  
 <span data-ttu-id="a2b71-131">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="a2b71-131">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="a2b71-132">ファイル</span><span class="sxs-lookup"><span data-stu-id="a2b71-132">File(s)</span></span>|<span data-ttu-id="a2b71-133">Description</span><span class="sxs-lookup"><span data-stu-id="a2b71-133">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a2b71-134">AssemblyInfo.cs、SsoSample.csproj</span><span class="sxs-lookup"><span data-stu-id="a2b71-134">AssemblyInfo.cs, SsoSample.csproj</span></span>|<span data-ttu-id="a2b71-135">この HTTP SSO サンプルのプロジェクト ファイルと関連ファイルです。</span><span class="sxs-lookup"><span data-stu-id="a2b71-135">Project and related files for this HTTP SSO sample.</span></span>|  
|<span data-ttu-id="a2b71-136">SsoSample.cs</span><span class="sxs-lookup"><span data-stu-id="a2b71-136">SsoSample.cs</span></span>|<span data-ttu-id="a2b71-137">このサンプルの多くを構成する HTTP SSO グラフィカル アプリケーションの最上位の Microsoft Visual C# ソース ファイルです。</span><span class="sxs-lookup"><span data-stu-id="a2b71-137">Top-level Microsoft Visual C# source file for the HTTP SSO graphical application that constitutes much of this sample.</span></span> <span data-ttu-id="a2b71-138">このファイルには、という名前のクラスで、SSO 構成コードが含まれています。 **SsoConfigurator**が最終的にこのサンプルのポイント。</span><span class="sxs-lookup"><span data-stu-id="a2b71-138">This file contains the SSO configuration code, in a class named **SsoConfigurator** that is ultimately the point of this sample.</span></span>|  
|<span data-ttu-id="a2b71-139">\Scripts フォルダー内のファイル: </span><span class="sxs-lookup"><span data-stu-id="a2b71-139">In the \Scripts folder:</span></span><br /><br /> <span data-ttu-id="a2b71-140">EmployeeData.aspx</span><span class="sxs-lookup"><span data-stu-id="a2b71-140">EmployeeData.aspx</span></span>|<span data-ttu-id="a2b71-141">従業員が直接または SSO を使用して個人データを表示する要求を開始したときに、バックエンド データベース (この場合は SQL Northwind データベース) へのアクセスと照会に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2b71-141">Used to access and query the back-end database (in this case, the SQL Northwind database) when an employee initiates a request to view personal data, either directly or by using SSO.</span></span>|  
|<span data-ttu-id="a2b71-142">\Scripts フォルダー内のファイル: </span><span class="sxs-lookup"><span data-stu-id="a2b71-142">In the \Scripts folder:</span></span><br /><br /> <span data-ttu-id="a2b71-143">ValidateUser.aspx</span><span class="sxs-lookup"><span data-stu-id="a2b71-143">ValidateUser.aspx</span></span>|<span data-ttu-id="a2b71-144">ユーザーを検証し、直接または SSO を使用してそのユーザーが検証されたかどうかを報告する単純なテストです。</span><span class="sxs-lookup"><span data-stu-id="a2b71-144">Simple test to validate a user and report if that user was validated, either directly or by using SSO.</span></span>|  
|<span data-ttu-id="a2b71-145">\UI フォルダー内のファイル: </span><span class="sxs-lookup"><span data-stu-id="a2b71-145">In the \UI folder:</span></span><br /><br /> <span data-ttu-id="a2b71-146">AddApplication.cs、AddApplication.resx、AddMapping.cs、AddMapping.resx、App.ico、BtsPage.cs、BtsPage.resx、ExecutePage.cs、ExecutePage.resx、FinishPage.cs、FinishPage.resx、IisPage.cs、IisPage.resx、InfoPage.cs、InfoPage.resx、PageBase.cs、PageBase.resx、SsoPage.cs、SsoPage.resx、SsoSampleWizard.cs、SsoSampleWizard.resx、WelcomePage.cs、WelcomePage.resx、WorkPage.cs、WorkPage.resx</span><span class="sxs-lookup"><span data-stu-id="a2b71-146">AddApplication.cs, AddApplication.resx, AddMapping.cs, AddMapping.resx, App.ico, BtsPage.cs, BtsPage.resx, ExecutePage.cs, ExecutePage.resx, FinishPage.cs, FinishPage.resx, IisPage.cs, IisPage.resx, InfoPage.cs, InfoPage.resx, PageBase.cs, PageBase.resx, SsoPage.cs, SsoPage.resx, SsoSampleWizard.cs, SsoSampleWizard.resx, WelcomePage.cs, WelcomePage.resx, WorkPage.cs, WorkPage.resx</span></span>|<span data-ttu-id="a2b71-147">このサンプルの多くを構成する HTTP SSO グラフィカル アプリケーションの補助 Visual C# ソース ファイル、および関連する XML 形式のリソース ファイルです。</span><span class="sxs-lookup"><span data-stu-id="a2b71-147">Auxiliary Visual C# source files, and their associated XML-formatted resource files, for the HTTP SSO graphical application that constitutes much of this sample.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="a2b71-148">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="a2b71-148">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-httpsso-sample"></a><span data-ttu-id="a2b71-149">HTTPSSO サンプルをビルドして初期化するには</span><span class="sxs-lookup"><span data-stu-id="a2b71-149">To build and initialize the HTTPSSO sample</span></span>  
  
1.  <span data-ttu-id="a2b71-150">Microsoft インターネット インフォメーション サービス (IIS) が基本認証に使用できるローカル Windows アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-150">Create a local Windows account that Microsoft Internet Information Services (IIS) can use for basic authentication.</span></span> <span data-ttu-id="a2b71-151">SSO は、Windows ドメイン アカウントをこのローカル Windows アカウントにマップします。</span><span class="sxs-lookup"><span data-stu-id="a2b71-151">SSO maps the Windows domain account to this local Windows account.</span></span> <span data-ttu-id="a2b71-152">たとえば、自分の姓を使用してローカル Windows アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-152">For example, use your last name to create a local Windows account.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a2b71-153">ドメイン コントローラ上で実行している場合は、ドメイン アカウントを作成し、ログオンしたドメイン アカウントをこのアカウントにマップできます。</span><span class="sxs-lookup"><span data-stu-id="a2b71-153">If you are running on a domain controller, you can create domain accounts and map your logged on domain account to this account.</span></span>  
  
2.  <span data-ttu-id="a2b71-154">Microsoft SQL Server の Enterprise Manager を使用して開き、**従業員**Northwind サンプル データベースのテーブルが表示され、作成した、さまざまなサンプル データを含む、ローカル Windows アカウントに対応する行を追加列です。</span><span class="sxs-lookup"><span data-stu-id="a2b71-154">Using Microsoft SQL Server Enterprise Manager, open the **Employees** table in the Northwind sample database, and then add a row corresponding to the local Windows account that you just created, including sample data for the various columns.</span></span> <span data-ttu-id="a2b71-155">Employees テーブルの LastName 列に追加した値は、手順 1. で追加したローカル Windows アカウントのユーザー名と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2b71-155">The value you add to the LastName column in the Employees table must be the same as the user name of the local Windows account you added in step 1.</span></span>  
  
3.  <span data-ttu-id="a2b71-156">ASP.NET アカウント (ASPNET) に Northwind データベースの読み取り特権があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-156">Ensure the ASP.NET account (ASPNET) has read privileges to the Northwind database.</span></span>  
  
4.  <span data-ttu-id="a2b71-157">Visual Studio を使用して、プロジェクト ファイル SsoSample.csproj を開きます。</span><span class="sxs-lookup"><span data-stu-id="a2b71-157">Open the project file SsoSample.csproj using Visual Studio.</span></span>  
  
5.  <span data-ttu-id="a2b71-158">**[ビルド]** メニューの **[ソリューションのビルド]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2b71-158">On the **Build** menu, click **Build Solution**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a2b71-159">ビルドを続行する前に、ソリューションを保存するように要求されます。</span><span class="sxs-lookup"><span data-stu-id="a2b71-159">You may be asked to save a solution file before the build can proceed.</span></span>  
  
     <span data-ttu-id="a2b71-160">プロジェクトの次の BizTalk アセンブリ参照が見つからない場合は、アセンブリ参照を削除し、表示された場所から再追加してから、もう一度ビルドします。</span><span class="sxs-lookup"><span data-stu-id="a2b71-160">If you cannot find the following BizTalk assembly references for the project, delete them, re-add them from the indicated locations, and build again:</span></span>  
  
    -   <span data-ttu-id="a2b71-161">**Microsoft.BizTalk.ExplorerOM**です。</span><span class="sxs-lookup"><span data-stu-id="a2b71-161">**Microsoft.BizTalk.ExplorerOM**.</span></span> <span data-ttu-id="a2b71-162">既定では、Microsoft.BizTalk.ExplorerOM.dll ファイルは、フォルダーにあります[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Developer Tools\\です。</span><span class="sxs-lookup"><span data-stu-id="a2b71-162">By default, the Microsoft.BizTalk.ExplorerOM.dll file is located in the folder [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Developer Tools\\.</span></span>  
  
    -   <span data-ttu-id="a2b71-163">**Microsoft.BizTalk.SSOClient.Interop**です。</span><span class="sxs-lookup"><span data-stu-id="a2b71-163">**Microsoft.BizTalk.SSOClient.Interop**.</span></span> <span data-ttu-id="a2b71-164">既定では、Microsoft.BizTalk.Interop.SSOClient.dll ファイル フォルダーにある、 \< *ProgramFiles*> でのシングル サインオン \Common Files\Enterprise\\です。</span><span class="sxs-lookup"><span data-stu-id="a2b71-164">By default, the Microsoft.BizTalk.Interop.SSOClient.dll file is located in the folder \<*ProgramFiles*>\Common Files\Enterprise Single Sign-On\\.</span></span>  
  
     <span data-ttu-id="a2b71-165">これにより、次のフォルダに実行可能ファイル SsoSample.exe が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a2b71-165">This produces the executable file SsoSample.exe in the following folder:</span></span>  
  
     <span data-ttu-id="a2b71-166">\<*パスのサンプル*> \SSO\HTTPSSO\bin\Debug\\</span><span class="sxs-lookup"><span data-stu-id="a2b71-166">\<*Samples Path*>\SSO\HTTPSSO\bin\Debug\\</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="a2b71-167">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="a2b71-167">Running This Sample</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2b71-168">ワーカー プロセス分離モードを使用して IIS 6.0 でこのサンプルを実行すると、両方の仮想ディレクトリに対してアプリケーション プールが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a2b71-168">If you run this sample on IIS 6.0 in Worker Process Isolation Mode, application pools are created for both virtual directories.</span></span> <span data-ttu-id="a2b71-169">Windows アカウントでこれらの 2 つのアプリケーション プールの ID を手動で構成する必要があります (ID はインターネット インフォメーション サービス マネージャで構成できます)。</span><span class="sxs-lookup"><span data-stu-id="a2b71-169">You must manually configure identity for these two application pools in your Windows account (you can configure identity in Internet Information Services Manager).</span></span>  
  
#### <a name="to-run-the-httpsso-sample"></a><span data-ttu-id="a2b71-170">HTTPSSO サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="a2b71-170">To run the HTTPSSO sample</span></span>  
  
1.  <span data-ttu-id="a2b71-171">次のフォルダにある実行可能ファイル SsoSample.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-171">Run the executable file SsoSample.exe, found in the following folder:</span></span>  
  
     <span data-ttu-id="a2b71-172">\<*パスのサンプル*> \SSO\HTTPSSO\bin\Debug\\</span><span class="sxs-lookup"><span data-stu-id="a2b71-172">\<*Samples Path*>\SSO\HTTPSSO\bin\Debug\\</span></span>  
  
     <span data-ttu-id="a2b71-173">このサンプルのウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="a2b71-173">The wizard application for this sample opens.</span></span>  
  
2.  <span data-ttu-id="a2b71-174">[ようこそ] ページで、IIS、SSO、および BizTalk を構成するため、既定の設定を受け入れるし、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="a2b71-174">On the Welcome page, accept the default setting for configuring IIS, SSO, and BizTalk, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="a2b71-175">[IIS の構成] ページで、作成、およびをクリックする 2 つの IIS 仮想ディレクトリの既定の設定を受け入れる**次**です。</span><span class="sxs-lookup"><span data-stu-id="a2b71-175">On the IIS Configuration page, accept the default settings for the two IIS virtual directories you want to create, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="a2b71-176">[SSO 構成] ページを使用してアクセスされる関連アプリケーション用の既定の設定を受け入れ、**アプリケーションに追加**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2b71-176">On the SSO Configuration page, accept the default settings for the affiliate application, which is accessible using the **Add application** button.</span></span>  
  
5.  <span data-ttu-id="a2b71-177">[SSO 構成] ページで、ほとんどのユーザー マッピングの既定の設定を受け入れるを使用してアクセス、**追加マッピング**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2b71-177">On the SSO Configuration page, accept most of the default settings for the user mappings, accessible using the **Add mapping** button.</span></span> <span data-ttu-id="a2b71-178">このサンプルをビルドおよび初期化したときに追加したローカル Windows アカウントに基づいて、次の 2 つの設定に値を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-178">Provide values for the following two settings based on the local Windows account you added when building and initializing this sample.</span></span>  
  
    |<span data-ttu-id="a2b71-179">設定</span><span class="sxs-lookup"><span data-stu-id="a2b71-179">Setting</span></span>|<span data-ttu-id="a2b71-180">値</span><span class="sxs-lookup"><span data-stu-id="a2b71-180">Value</span></span>|  
    |-------------|-----------|  
    |<span data-ttu-id="a2b71-181">外部ユーザー名</span><span class="sxs-lookup"><span data-stu-id="a2b71-181">External user name</span></span>|<span data-ttu-id="a2b71-182">追加したローカルの Windows ユーザー アカウント名に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a2b71-182">Set to the added local Windows user account name.</span></span>|  
    |<span data-ttu-id="a2b71-183">外部ユーザーのパスワード</span><span class="sxs-lookup"><span data-stu-id="a2b71-183">External user password</span></span>|<span data-ttu-id="a2b71-184">追加したローカルの Windows ユーザー アカウントのパスワードに設定されます。</span><span class="sxs-lookup"><span data-stu-id="a2b71-184">Set to the added local Windows user account password.</span></span>|  
  
6.  <span data-ttu-id="a2b71-185">SSO 構成 ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="a2b71-185">On the SSO Configuration page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="a2b71-186">[BizTalk 構成] ページで、送信の既定の設定を受け入れると受信ポート、およびをクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="a2b71-186">On the BizTalk Configuration page, accept the default settings for the send and receive ports, and so on, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a2b71-187">既定の送信ポート設定を変更することができます**EmployeeData.aspx**に**ValidateUser.aspx**の Employee テーブルから取得されたサンプル データではなく、単純なユーザー検証を表示する場合、Northwinds SQL データベースです。</span><span class="sxs-lookup"><span data-stu-id="a2b71-187">You can change the default send port setting from **EmployeeData.aspx** to **ValidateUser.aspx** if you want to see simple user validation rather than sample data pulled from the Employee table of the Northwinds SQL database.</span></span> <span data-ttu-id="a2b71-188">この変更の変更をクリックした後、ブラウザーに表示される出力の性質**完了**手順 9. でします。</span><span class="sxs-lookup"><span data-stu-id="a2b71-188">Making this change changes the nature of the output displayed in the browser after clicking **Finish** in step 9.</span></span>  
  
8.  <span data-ttu-id="a2b71-189">実行される IIS、SSO、および BizTalk の各構成に対応する状態メッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-189">Review the status messages corresponding to the IIS, SSO, and BizTalk configuration being performed.</span></span> <span data-ttu-id="a2b71-190">このフェーズで実行されるコードを検索することができます、 **IisConfigurator**、 **SsoConfigurator**、および**BtsConfigurator**ファイル SsoSample.cs で定義されたクラスです。</span><span class="sxs-lookup"><span data-stu-id="a2b71-190">You can find the code that is run during this phase in the **IisConfigurator**, **SsoConfigurator**, and **BtsConfigurator** classes defined in the file SsoSample.cs.</span></span> <span data-ttu-id="a2b71-191">構成が完了した後にをクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="a2b71-191">After configuration has completed, click **Next**.</span></span>  
  
9. <span data-ttu-id="a2b71-192">ウィザード アプリケーションの最後のページ上の既定の設定を受け入れる**でブラウザーを開始**(チェック ボックスがオンし、テキスト ボックスに URL http://localhost/SsoSampleBizTalkHttpReceive/BTSHttpReceive.dll?\<メッセージ/>)、をクリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="a2b71-192">On the final page of the wizard application, accept the default settings for **Start browser at** (a selected check box and a text box with the URL http://localhost/SsoSampleBizTalkHttpReceive/BTSHttpReceive.dll?\<message/>), and then click **Finish**.</span></span>  
  
     <span data-ttu-id="a2b71-193">Internet Explorer のインスタンスが開き、Northwinds SQL データベースの Employee テーブルに追加した従業員データのサンプルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2b71-193">An instance of Internet Explorer will open, and soon display the sample employee data that you added to the Employee table of the Northwinds SQL database.</span></span>  
  
 <span data-ttu-id="a2b71-194">比較のために、BizTalk と SSO を省略し、次の ASPX ファイルのいずれかを直接参照します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-194">For comparison purposes, you can bypass BizTalk and SSO and browse directly to either of the ASPX files:</span></span>  
  
-   <span data-ttu-id="a2b71-195">http://localhost/SsoSampleServerApplication/ValidateUser.aspx</span><span class="sxs-lookup"><span data-stu-id="a2b71-195">http://localhost/SsoSampleServerApplication/ValidateUser.aspx</span></span>  
  
-   <span data-ttu-id="a2b71-196">http://localhost/SsoSampleServerApplication/EmployeeData.aspx</span><span class="sxs-lookup"><span data-stu-id="a2b71-196">http://localhost/SsoSampleServerApplication/EmployeeData.aspx</span></span>  
  
 <span data-ttu-id="a2b71-197">どちらの場合も、BizTalk と SSO を省略しているため、IIS から認証情報を要求されます (前に作成したローカル Windows アカウントの情報を使用します)。</span><span class="sxs-lookup"><span data-stu-id="a2b71-197">In both cases, because you bypass BizTalk and SSO, you are prompted for your authentication information by IIS (use the local Windows account information you created previously).</span></span>  
  
## <a name="comments"></a><span data-ttu-id="a2b71-198">コメント</span><span class="sxs-lookup"><span data-stu-id="a2b71-198">Comments</span></span>  
 <span data-ttu-id="a2b71-199">SsoSample.exe ウィザード アプリケーションは、2 つの IIS 仮想ディレクトリを構成します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-199">The SsoSample.exe wizard application configures two IIS virtual directories:</span></span>  
  
-   <span data-ttu-id="a2b71-200">最初の仮想ディレクトリは Windows 統合認証で構成され、BizTalk HTTP 受信 ISAPI 拡張に対応します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-200">The first virtual directory is configured with Windows integrated authentication and corresponds to the BizTalk HTTP Receive ISAPI extension.</span></span> <span data-ttu-id="a2b71-201">次のフォルダにある .dll ファイル BTSHTTPReceive.dll に関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2b71-201">It must be associated with the .dll file BTSHTTPReceive.dll located in the following folder:</span></span>  
  
     <span data-ttu-id="a2b71-202">\<*インストール パス*> \HttpReceive</span><span class="sxs-lookup"><span data-stu-id="a2b71-202">\<*Install Path*>\HttpReceive</span></span>  
  
-   <span data-ttu-id="a2b71-203">2 番目の仮想ディレクトリは基本認証で構成され、ユーザーを認証するためにユーザー ID とパスワードを受け取るバックエンド システムをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="a2b71-203">The second virtual directory is configured with basic authentication and simulates a back-end system that accepts a user ID and password to authenticate the user.</span></span> <span data-ttu-id="a2b71-204">次のフォルダにある ASPX ファイル ValidateUser.aspx と EmployeeData.aspx のいずれかに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2b71-204">It must be associated with one or the other of the ASPX files, ValidateUser.aspx or EmployeeData.aspx, located in the following folder:</span></span>  
  
     <span data-ttu-id="a2b71-205">\<*パスのサンプル*> \SSO\HTTPSSO\Scripts</span><span class="sxs-lookup"><span data-stu-id="a2b71-205">\<*Samples Path*>\SSO\HTTPSSO\Scripts</span></span>  
  
 <span data-ttu-id="a2b71-206">SsoSample.exe ウィザード アプリケーションを使用して、1 つ以上の関連アプリケーションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="a2b71-206">You can use the SsoSample.exe wizard application to configure one or more affiliate applications.</span></span> <span data-ttu-id="a2b71-207">これらの関連アプリケーションごとに、1 つまたは複数のユーザー マッピングを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a2b71-207">For each of these affiliate applications, you can create one or more user mappings.</span></span> <span data-ttu-id="a2b71-208">これらの各ユーザー マッピングは、Windows ユーザー アカウントを、特定のバックエンド システムへのアクセスに使用するアカウントにマップします。</span><span class="sxs-lookup"><span data-stu-id="a2b71-208">Each of these user mappings maps a Windows user account to an account that you use to access a specific back-end system.</span></span> <span data-ttu-id="a2b71-209">このサンプルでは、そのアカウントは、実際のバックエンド システムをシミュレートする 2 番目の IIS 仮想ディレクトリでの認証に使用する、ローカル Windows アカウントです。</span><span class="sxs-lookup"><span data-stu-id="a2b71-209">In this sample, that account is a local Windows account that you use to authenticate with the second IIS virtual directory that is simulating a genuine back-end system.</span></span>  
  
 <span data-ttu-id="a2b71-210">このサンプルを再実行するには、複数の選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="a2b71-210">To rerun this sample, you have several choices:</span></span>  
  
-   <span data-ttu-id="a2b71-211">Internet Explorer で、次の URL を直接参照します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-211">Browse directly to the following URL in Internet Explorer:</span></span>  
  
     <span data-ttu-id="a2b71-212">http://localhost/SsoSampleBizTalkHttpReceive/BTSHttpReceive.dll?\<メッセージ/></span><span class="sxs-lookup"><span data-stu-id="a2b71-212">http://localhost/SsoSampleBizTalkHttpReceive/BTSHttpReceive.dll?\<message/></span></span>  
  
-   <span data-ttu-id="a2b71-213">ウィザード アプリケーションを再実行します。ただし、最初のページの構成チェック ボックスをすべてオフにします。</span><span class="sxs-lookup"><span data-stu-id="a2b71-213">Run the wizard application again, but clear all of the configuration check boxes on the first page.</span></span>  
  
-   <span data-ttu-id="a2b71-214">ウィザード アプリケーションを再実行します。最初のページの構成チェック ボックスはすべてオンのままにしますが、構成エラーが発生しないように、その他の BizTalk アイテム、関連アプリケーションなどを慎重かつ適切に構成します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-214">Run the wizard application again, leave the configuration check boxes selected in the first page, but carefully and appropriately configure additional BizTalk items, affiliate applications, and so on, so that configuration errors do not occur.</span></span>  
  
 <span data-ttu-id="a2b71-215">このサンプルからクリーンアップするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-215">To clean up from this sample, use the following procedure.</span></span>  
  
#### <a name="to-clean-up-from-this-sample"></a><span data-ttu-id="a2b71-216">このサンプルからクリーンアップするには</span><span class="sxs-lookup"><span data-stu-id="a2b71-216">To clean up from this sample</span></span>  
  
1.  <span data-ttu-id="a2b71-217">ローカル Windows アカウントを削除するなど、適宜、実行した手動構成を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-217">As appropriate, reverse the manual configuration that you performed, such as removing the local Windows account.</span></span>  
  
2.  <span data-ttu-id="a2b71-218">仮想ディレクトリに対応する IIS アプリケーションを削除した後、このサンプルで作成された IIS 仮想ディレクトリを削除します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-218">Remove IIS applications that correspond to the virtual directories, and then delete the IIS virtual directories created by this sample.</span></span>  
  
3.  <span data-ttu-id="a2b71-219">BizTalk 管理コンソールを使用して、参加解除した後、このサンプルに関連付けられている送信ポートを削除します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-219">Using BizTalk Administration console, unenlist and then delete the send port associated with this sample.</span></span> <span data-ttu-id="a2b71-220">このサンプルに関連付けられている受信ポート (およびその受信場所) を削除します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-220">Then delete the receive port (and its receive location) associated with this sample.</span></span>  
  
4.  <span data-ttu-id="a2b71-221">Ssomanage アプリケーションを使用して (\program files \common files \enterprise シングル サイン オンである\\) をこのサンプルの SSO アプリケーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="a2b71-221">Use the Ssomanage application (located in \Program Files\Common Files\Enterprise Single Sign-On\\) to delete the SSO application for this sample:</span></span>  
  
    ```  
    Ssomanage –deleteapp SsoSampleApplication  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a2b71-222">参照</span><span class="sxs-lookup"><span data-stu-id="a2b71-222">See Also</span></span>  
 [<span data-ttu-id="a2b71-223">SSO (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="a2b71-223">SSO (BizTalk Server Samples Folder)</span></span>](../core/sso-biztalk-server-samples-folder.md)