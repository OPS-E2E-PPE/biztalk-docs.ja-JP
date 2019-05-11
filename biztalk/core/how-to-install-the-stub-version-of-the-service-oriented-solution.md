---
title: 指向ソリューションのスタブ バージョンのサービスをインストールする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IIS, installing virtual directories [service solutions]
- service solution tutorial, IIS virtual directories
- service solution tutorial, stub version
- deploying, BAM solutions [service solutions]
- service solution tutorial, solutions [BAM]
- service solution tutorial, service solutions
- SSO, configuring
- IBM WebSphere MQ Client
- service solution tutorial, IBM WebSphere MQ Client
- installing, tutorials
- service solutions, deploying
- service solution tutorial, SSO
- BAM, deploying solutions
- service solution tutorial, building solutions
- service solution tutorial, installing
ms.assetid: 45de7681-4df0-47a4-a02c-509140423a1e
caps.latest.revision: 53
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ecb7da2662649fe9744c5a4744b50834b2b87bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336986"
---
# <a name="how-to-install-the-stub-version-of-the-service-oriented-solution"></a><span data-ttu-id="8703a-102">指向ソリューションのスタブ バージョンのサービスをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="8703a-102">How to Install the Stub Version of the Service Oriented Solution</span></span>
<span data-ttu-id="8703a-103">次の手順では、サービス指向ソリューションのスタブ バージョンをインストールする前に、コンピューターを準備する方法と、コンピューターにソリューションをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8703a-103">The following steps describe how to prepare your computer before you install the stub version of the service oriented solution, and then how to install the solution on your computer.</span></span>  
  
-   [<span data-ttu-id="8703a-104">サービス指向ソリューションのスタブ バージョンをインストールするコンピューターを準備します。</span><span class="sxs-lookup"><span data-stu-id="8703a-104">Prepare the computer for installing the stub version of the Service Oriented Solution</span></span>](#step1)  
  
-   [<span data-ttu-id="8703a-105">IBM WebSphere MQ Client for Windows をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8703a-105">Install the IBM WebSphere MQ Client for Windows</span></span>](#step3)  
  
-   [<span data-ttu-id="8703a-106">仮想ディレクトリが IIS でサービス指向ソリューションの作成します。</span><span class="sxs-lookup"><span data-stu-id="8703a-106">Create the virtual directories in IIS for the Service Oriented Solution</span></span>](#step5)  
  
-   [<span data-ttu-id="8703a-107">ビルド サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="8703a-107">Build the Service Oriented Solution</span></span>](#step7)  
  
-   [<span data-ttu-id="8703a-108">SSO データベース内のエンタープライズ シングル サインオン (SSO) エントリと値を作成します。</span><span class="sxs-lookup"><span data-stu-id="8703a-108">Create the Enterprise Single Sign-On (SSO) entries and values in the SSO database</span></span>](#step9)  
  
-   [<span data-ttu-id="8703a-109">サービス指向ソリューションの BAM 定義を展開します。</span><span class="sxs-lookup"><span data-stu-id="8703a-109">Deploy the BAM definition for the Service Oriented Solution</span></span>](#step11)  
  
-   [<span data-ttu-id="8703a-110">サービス指向ソリューションの展開</span><span class="sxs-lookup"><span data-stu-id="8703a-110">Deploy the Service Oriented Solution</span></span>](#step13)  
  
##  <a name="step1"></a> <span data-ttu-id="8703a-111">サービス指向ソリューションのスタブ バージョンをインストールするコンピューターを準備します。</span><span class="sxs-lookup"><span data-stu-id="8703a-111">Prepare the computer for installing the stub version of the Service Oriented Solution</span></span>  
  
#### <a name="to-prepare-the-computer-for-installing-the-stub-version-of-the-service-oriented-solution"></a><span data-ttu-id="8703a-112">サービス指向ソリューションのスタブ バージョンをインストールするため、コンピューターを準備するには</span><span class="sxs-lookup"><span data-stu-id="8703a-112">To prepare the computer for installing the stub version of the Service Oriented Solution</span></span>  
  
1. <span data-ttu-id="8703a-113">必ず、**既定の Web サイト**ASP.NET を使用するように構成 2.X。</span><span class="sxs-lookup"><span data-stu-id="8703a-113">Make sure that the **Default Web Site** is configured to use ASP.NET 2.X.</span></span>  
  
   1.  <span data-ttu-id="8703a-114">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**.</span><span class="sxs-lookup"><span data-stu-id="8703a-114">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
   2.  <span data-ttu-id="8703a-115">**インターネット インフォメーション サービス (IIS) マネージャー**、マシン名を展開**サイト**、展開**既定の Web サイト**、展開**aspnet_client**、展開 **[system_web]** します。</span><span class="sxs-lookup"><span data-stu-id="8703a-115">In the **Internet Information Services (IIS) Manager**, the machine name, expand  **Sites**, expand **Default Web Site**, expand **aspnet_client**, expand **system_web**.</span></span>  
  
   3.  <span data-ttu-id="8703a-116">サブフォルダーが 2.X であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8703a-116">Make sure that the sub-folder is 2.X.</span></span>  
  
2. <span data-ttu-id="8703a-117">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**サービス**します。</span><span class="sxs-lookup"><span data-stu-id="8703a-117">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span> <span data-ttu-id="8703a-118">使用して、**サービス**コンソールで、次のサービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8703a-118">Using the **Services** console, make sure that the following services are running:</span></span>  
  
   -   <span data-ttu-id="8703a-119">**World Wide Web の発行**</span><span class="sxs-lookup"><span data-stu-id="8703a-119">**World Wide Web Publishing**</span></span>  
  
3. <span data-ttu-id="8703a-120">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、 をクリックして**コンピュータの管理**コンソール、および追加し、ローカルの Administrators グループに BizTalk サービス アカウント。</span><span class="sxs-lookup"><span data-stu-id="8703a-120">Click **Start**, point to **All Programs**, point to **Administrative Tools**, click **Computer Management** console, and then add the BizTalk service account to the local Administrators group.</span></span>  
  
4. <span data-ttu-id="8703a-121">Windows SharePoint Services をインストールした場合の (ルート) を除外する、**既定の Web サイト**Windows SharePoint Services 管理パスから次のようにします。をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**SharePoint Central Administration**。</span><span class="sxs-lookup"><span data-stu-id="8703a-121">If you installed Windows SharePoint Services, exclude the (root) of the **Default Web Site** from Windows SharePoint Services Managed Paths as follows: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
   1.  <span data-ttu-id="8703a-122">**仮想サーバーの構成**、**仮想サーバー設定を構成**します。</span><span class="sxs-lookup"><span data-stu-id="8703a-122">Under **Virtual Server Configuration**, select **Configure virtual server settings**.</span></span>  
  
   2.  <span data-ttu-id="8703a-123">**仮想サーバーのリスト**] ページで [**既定の Web サイト**します。</span><span class="sxs-lookup"><span data-stu-id="8703a-123">On the **Virtual Server List** page, click **Default Web Site**.</span></span>  
  
   3.  <span data-ttu-id="8703a-124">**仮想サーバーの設定**] ページで [**管理パスの定義**します。</span><span class="sxs-lookup"><span data-stu-id="8703a-124">On the **Virtual Server Settings** page, click **Define managed paths**.</span></span>  
  
   4.  <span data-ttu-id="8703a-125">**インクルード パス**のセクション、**管理パスの定義**] ページで、[**ルート**順にクリックします**選択したパスの削除**します。</span><span class="sxs-lookup"><span data-stu-id="8703a-125">In the **Included Paths** section of the **Defined Managed Path** page, select **Root** and then click **Remove selected paths**.</span></span>  
  
   5.  <span data-ttu-id="8703a-126">コマンド プロンプトで IISReset コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8703a-126">At a command prompt, perform an IISReset.</span></span>  
  
5. <span data-ttu-id="8703a-127">コンピュータからログオフして、BizTalk サービス アカウントを使用してコンピュータにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8703a-127">Log off the computer, and then log on to the computer as the BizTalk service account.</span></span>  
  
6. <span data-ttu-id="8703a-128">コマンド プロンプトを開き、次のコマンドを入力し、enter キーを押して、%btssolutionspath% 環境変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="8703a-128">Open a command prompt, type the following command, and then press ENTER to set the %BTSSolutionsPath% environment.</span></span> <span data-ttu-id="8703a-129">次に、コマンド プロンプトを終了します。</span><span class="sxs-lookup"><span data-stu-id="8703a-129">Then, exit the command prompt.</span></span>  
  
   - <span data-ttu-id="8703a-130">setx %btssolutionspath%"[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"</span><span class="sxs-lookup"><span data-stu-id="8703a-130">setx BTSSolutionsPath "[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"</span></span>  
  
     > [!NOTE]
     >  <span data-ttu-id="8703a-131">64 ビット コンピューターを使用する場合は、「%ProgramFiles%」の代わりに「%ProgramFiles%(x86)」と入力してください。</span><span class="sxs-lookup"><span data-stu-id="8703a-131">If you are using a 64-bit computer, use %ProgramFiles(x86)% instead of %ProgramFiles%.</span></span>  
  
     > [!NOTE]
     >  <span data-ttu-id="8703a-132">SETX コマンドの詳細については、Microsoft TechNet Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831)します。</span><span class="sxs-lookup"><span data-stu-id="8703a-132">For more information about the SETX command, see the Microsoft TechNet Web site at [http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831).</span></span>  
  
##  <a name="step3"></a> <span data-ttu-id="8703a-133">IBM WebSphere MQ Client for Windows をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8703a-133">Install the IBM WebSphere MQ Client for Windows</span></span>  
  
#### <a name="to-install-the-ibm-websphere-mq-client-for-windows"></a><span data-ttu-id="8703a-134">IBM WebSphere MQ Client for Windows をインストールするには</span><span class="sxs-lookup"><span data-stu-id="8703a-134">To install the IBM WebSphere MQ Client for Windows</span></span>  
  
1. <span data-ttu-id="8703a-135">IBM WebSphere MQ Client for Windows の最新バージョンをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8703a-135">Download the latest version of IBM WebSphere MQ Client for Windows.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="8703a-136">ソリューションのスタブ バージョンで IBM WebSphere Server を必要としない場合でも、クライアント アプリケーションはインストールする必要がありますので、IBM WebSphere MQ Client for Windows、によって提供される amqmdnet.dll ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="8703a-136">Even if the stub version of the solution doesn't require IBM WebSphere Server, the client application references the amqmdnet.dll file provided by IBM WebSphere MQ Client for Windows, so you must install it.</span></span> <span data-ttu-id="8703a-137">スタブ バージョンのクライアントでは、API は実際には、DLL で呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="8703a-137">The client of the stub version does not actually call an API in the DLL.</span></span> <span data-ttu-id="8703a-138">コンパイルして、クライアント アプリケーションの実行にのみ必要になります。</span><span class="sxs-lookup"><span data-stu-id="8703a-138">It is required only for compiling and running the client application.</span></span> <span data-ttu-id="8703a-139">IBM Web サイトから IBM WebSphere MQ Client for Windows をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="8703a-139">You can download IBM WebSphere MQ Client for Windows from the IBM Web site.</span></span>  
  
2. <span data-ttu-id="8703a-140">IBM WebSphere MQ Client for Windows をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8703a-140">Install IBM WebSphere MQ Client for Windows.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="8703a-141">IBM WebSphere MQ Client for Windows を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8703a-141">You don't need to configure IBM WebSphere MQ Client for Windows.</span></span> <span data-ttu-id="8703a-142">すべての既定の設定を保持します。</span><span class="sxs-lookup"><span data-stu-id="8703a-142">Keep all of the default settings.</span></span>  
  
3. <span data-ttu-id="8703a-143">グローバル アセンブリ キャッシュ (GAC) に .NET アセンブリの WebSphere MQ クラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="8703a-143">Add WebSphere MQ classes for the .NET assembly to the global assembly cache (GAC).</span></span>  
  
   1. <span data-ttu-id="8703a-144">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリに移動\<IBM MQSeries インストール ディレクトリ\>\bin です。</span><span class="sxs-lookup"><span data-stu-id="8703a-144">At the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, navigate to the directory \<IBM MQSeries Installation Directory\>\bin.</span></span>  
  
   2. <span data-ttu-id="8703a-145">次のコマンドを実行します (gacutil.exe が path 環境ことを確認してください)。</span><span class="sxs-lookup"><span data-stu-id="8703a-145">Run the following command (make sure gacutil.exe is in the path environment):</span></span>  
  
       `gacutil.exe /i amqmdnet.dll`  
  
##  <a name="step5"></a> <span data-ttu-id="8703a-146">仮想ディレクトリが IIS でサービス指向ソリューションの作成します。</span><span class="sxs-lookup"><span data-stu-id="8703a-146">Create the virtual directories in IIS for the Service Oriented Solution</span></span>  
  
#### <a name="to-create-the-virtual-directories-in-iis-for-the-service-oriented-solution"></a><span data-ttu-id="8703a-147">サービス指向ソリューションの IIS を仮想ディレクトリを作成するには</span><span class="sxs-lookup"><span data-stu-id="8703a-147">To create the virtual directories in IIS for the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="8703a-148">**インターネット インフォメーション サービス (IIS) マネージャー**を右クリックして**アプリケーション プール**、**アプリケーション プールの追加**します。</span><span class="sxs-lookup"><span data-stu-id="8703a-148">In the **Internet Information Services (IIS) Manager**, right-click **Application Pools**, select **Add Application Pool**.</span></span>  
  
     <span data-ttu-id="8703a-149">**アプリケーション プールの追加**ダイアログ ボックスに「`SSOStubAppPool`で、**名前**テキスト ボックス、およびクリック**ok**します。</span><span class="sxs-lookup"><span data-stu-id="8703a-149">On the **Add Application Pool** dialog box, type `SSOStubAppPool` in the **Name** text box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="8703a-150">スタブ バージョンのオーケストレーション、スタブ SAP Web サービス、スタブ Payment Tracker Web サービス、およびスタブ Pending Transaction Web サービスのサービス指向ソリューションで使用が公開された Web が含まれている仮想ディレクトリ サービスします。</span><span class="sxs-lookup"><span data-stu-id="8703a-150">The virtual directories that service-oriented solution uses include the published Web service for the stub version of orchestrations, the stub SAP Web service, the stub Payment Tracker Web service, and the stub Pending Transaction Web service.</span></span>  
  
2.  <span data-ttu-id="8703a-151">**インターネット インフォメーション サービス (IIS) マネージャー**作成したアプリケーション プールを右クリックし、クリックして**詳細設定**します。</span><span class="sxs-lookup"><span data-stu-id="8703a-151">In the **Internet Information Services (IIS) Manager**, right-click the application pool that you just created, and then click **Advanced Settings**.</span></span>  
  
3.  <span data-ttu-id="8703a-152">右側に列をクリックして、 **Identity**プロパティ、クリックして、省略記号 (**...**) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8703a-152">Click in the column to the right of the **Identity** property, and then click the ellipsis (**…**) button.</span></span>  
  
4.  <span data-ttu-id="8703a-153">**アプリケーション プール Id**ダイアログ ボックスで、**カスタム アカウント**オプションをクリックして**設定**します。</span><span class="sxs-lookup"><span data-stu-id="8703a-153">In the **Application Pool Identity** dialog box, select the **Custom Account** option, and then click **Set**.</span></span>  
  
5.  <span data-ttu-id="8703a-154">**資格情報の設定**ダイアログ ボックスで、ユーザー名とパスワードを指定、パスワードの確認 をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="8703a-154">In the **Set Credentials** dialog box, specify a username and password, confirm the password, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8703a-155">このユーザーには、オーケストレーション プロキシ Web サービスを実行する権限が必要です。また、BizTalk Server 管理者グループ、SSO 管理者グループ、または SSO 関連管理者グループのいずれかにこのユーザーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8703a-155">This user must have permission to execute the Orchestration Proxy Web service, and must be added to one of the BizTalk Server Administrators, SSO Administrators, or SSO Affiliated Administrators groups</span></span>  
  
6.  <span data-ttu-id="8703a-156">をクリックして**OK**を閉じる、**アプリケーション プール Id**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="8703a-156">Click **OK** to close the **Application Pool Identity** dialog box.</span></span>  
  
7.  <span data-ttu-id="8703a-157">**[OK]** をクリックして **[詳細設定]** ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="8703a-157">Click **OK** to close the **Advanced Settings** dialog box.</span></span>  
  
8.  <span data-ttu-id="8703a-158">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**を右クリックし、**既定の Web サイト**、 をポイント**新規**とクリックして**仮想ディレクトリ**を実行する**仮想ディレクトリの作成ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="8703a-158">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
    1.  <span data-ttu-id="8703a-159">使用して、**仮想ディレクトリの作成ウィザード**、アダプター バージョンの Web サービス プロキシの次の仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="8703a-159">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the proxy Web service for the adapter version:</span></span>  
  
         <span data-ttu-id="8703a-160">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub</span><span class="sxs-lookup"><span data-stu-id="8703a-160">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub</span></span>  
  
         <span data-ttu-id="8703a-161">PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Stub</span><span class="sxs-lookup"><span data-stu-id="8703a-161">PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Stub</span></span>  
  
         <span data-ttu-id="8703a-162">Access Permissions = Read, Run scripts</span><span class="sxs-lookup"><span data-stu-id="8703a-162">Access Permissions = Read, Run scripts</span></span>  
  
    2.  <span data-ttu-id="8703a-163">使用して、**仮想ディレクトリの作成ウィザード**、アダプター バージョンの Web サービス プロキシの次の仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="8703a-163">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the proxy Web service for the adapter version:</span></span>  
  
         <span data-ttu-id="8703a-164">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP</span><span class="sxs-lookup"><span data-stu-id="8703a-164">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP</span></span>  
  
         <span data-ttu-id="8703a-165">PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP</span><span class="sxs-lookup"><span data-stu-id="8703a-165">PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP</span></span>  
  
         <span data-ttu-id="8703a-166">Access Permissions = Read, Run scripts</span><span class="sxs-lookup"><span data-stu-id="8703a-166">Access Permissions = Read, Run scripts</span></span>  
  
    3.  <span data-ttu-id="8703a-167">使用して、**仮想ディレクトリの作成ウィザード**、アダプター バージョンの Web サービス プロキシの次の仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="8703a-167">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the proxy Web service for the adapter version:</span></span>  
  
         <span data-ttu-id="8703a-168">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions</span><span class="sxs-lookup"><span data-stu-id="8703a-168">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions</span></span>  
  
         <span data-ttu-id="8703a-169">PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans</span><span class="sxs-lookup"><span data-stu-id="8703a-169">PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans</span></span>  
  
         <span data-ttu-id="8703a-170">Access Permissions = Read, Run scripts</span><span class="sxs-lookup"><span data-stu-id="8703a-170">Access Permissions = Read, Run scripts</span></span>  
  
    4.  <span data-ttu-id="8703a-171">使用して、**仮想ディレクトリの作成ウィザード**、アダプター バージョンの Web サービス プロキシの次の仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="8703a-171">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the proxy Web service for the adapter version:</span></span>  
  
         <span data-ttu-id="8703a-172">エイリアス Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker を =</span><span class="sxs-lookup"><span data-stu-id="8703a-172">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker</span></span>  
  
         <span data-ttu-id="8703a-173">PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PaymentTrack</span><span class="sxs-lookup"><span data-stu-id="8703a-173">PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PaymentTrack</span></span>  
  
         <span data-ttu-id="8703a-174">Access Permissions = Read, Run scripts</span><span class="sxs-lookup"><span data-stu-id="8703a-174">Access Permissions = Read, Run scripts</span></span>  
  
9. <span data-ttu-id="8703a-175">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Web サイト、** 展開、**既定の Web サイト**、右クリックMicrosoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub、 をクリックして**プロパティ**、し、次のように設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="8703a-175">In the **Internet Information Services (IIS) Manager**, expand **Web Sites,** expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="8703a-176">**仮想ディレクトリ**タブで、設定、**アプリケーション プール**に**SSOStubAppPool**で作成しました。</span><span class="sxs-lookup"><span data-stu-id="8703a-176">On the **Virtual directory** tab, set the **Application Pool** to **SSOStubAppPool** you just created.</span></span>  
  
    2.  <span data-ttu-id="8703a-177">をクリックして**ディレクトリ セキュリティ**] タブで [**編集**で、**認証とアクセス制御**グループ ボックスで、**統合 Windows 認証のみ有効になっている**、し、その他のオプションをオフ**認証アクセス**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="8703a-177">Click **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, select **Only Integrated Windows Authentication enabled**, and then clear other **Authentication access** checkboxes.</span></span> <span data-ttu-id="8703a-178">クリックして**OK**を終了します。</span><span class="sxs-lookup"><span data-stu-id="8703a-178">Click **OK** to exit.</span></span>  
  
10. <span data-ttu-id="8703a-179">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Web サイト、** 展開、**既定の Web サイト**、右クリックMicrosoft.Samples.BizTalk.WoodgroveBank.StubSAP、 をクリックして**プロパティ**、し、次のように設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="8703a-179">In the **Internet Information Services (IIS) Manager**, expand **Web Sites,** expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="8703a-180">**仮想ディレクトリ**タブで、設定、**アプリケーション プール**に**SSOStubAppPool**で作成しました。</span><span class="sxs-lookup"><span data-stu-id="8703a-180">On the **Virtual directory** tab, set the **Application Pool** to **SSOStubAppPool** you just created.</span></span>  
  
    2.  <span data-ttu-id="8703a-181">をクリックして**ディレクトリ セキュリティ** タブで **編集**で、**認証とアクセス制御**ボックスで、グループ化し、 **の匿名アクセスの有効化**.</span><span class="sxs-lookup"><span data-stu-id="8703a-181">Click **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, and then select **Enable Anonymous Access**.</span></span> <span data-ttu-id="8703a-182">クリックして**OK**を終了します。</span><span class="sxs-lookup"><span data-stu-id="8703a-182">Click **OK** to exit.</span></span>  
  
11. <span data-ttu-id="8703a-183">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Web サイト、** 展開、**既定の Web サイト**、右クリックMicrosoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions、 をクリックして**プロパティ**、し、次のように設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="8703a-183">In the **Internet Information Services (IIS) Manager**, expand **Web Sites,** expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="8703a-184">**仮想ディレクトリ**タブで、設定、**アプリケーション プール**に**SSOStubAppPool**で作成しました。</span><span class="sxs-lookup"><span data-stu-id="8703a-184">On the **Virtual directory** tab, set the **Application Pool** to **SSOStubAppPool** you just created.</span></span>  
  
    2.  <span data-ttu-id="8703a-185">をクリックして**ディレクトリ セキュリティ** タブで **編集**で、**認証とアクセス制御**ボックスで、グループ化し、 **の匿名アクセスの有効化**.</span><span class="sxs-lookup"><span data-stu-id="8703a-185">Click **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, and then select **Enable Anonymous Access**.</span></span> <span data-ttu-id="8703a-186">クリックして**OK**を終了します。</span><span class="sxs-lookup"><span data-stu-id="8703a-186">Click **OK** to exit.</span></span>  
  
12. <span data-ttu-id="8703a-187">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Web サイト、** 展開、**既定の Web サイト**、右クリックMicrosoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker、 をクリックして**プロパティ**、し、次のように設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="8703a-187">In the **Internet Information Services (IIS) Manager**, expand **Web Sites,** expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="8703a-188">**仮想ディレクトリ**タブで、設定、**アプリケーション プール**に**SSOStubAppPool**で作成しました。</span><span class="sxs-lookup"><span data-stu-id="8703a-188">On the **Virtual directory** tab, set the **Application Pool** to **SSOStubAppPool** you just created.</span></span>  
  
    2.  <span data-ttu-id="8703a-189">をクリックして**ディレクトリ セキュリティ** タブで **編集**で、**認証とアクセス制御**ボックスで、グループ化し、 **の匿名アクセスの有効化**.</span><span class="sxs-lookup"><span data-stu-id="8703a-189">Click **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, and then select **Enable Anonymous Access**.</span></span> <span data-ttu-id="8703a-190">クリックして**OK**を終了します。</span><span class="sxs-lookup"><span data-stu-id="8703a-190">Click **OK** to exit.</span></span>  
  
##  <a name="step7"></a> <span data-ttu-id="8703a-191">ビルド サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="8703a-191">Build the Service Oriented Solution</span></span>  
  
#### <a name="to-build-the-service-oriented-solution"></a><span data-ttu-id="8703a-192">サービス指向ソリューションを構築するには</span><span class="sxs-lookup"><span data-stu-id="8703a-192">To build the Service Oriented Solution</span></span>  
  
1. <span data-ttu-id="8703a-193">開始**Visual Studio コマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="8703a-193">Start **Visual Studio Command Prompt**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="8703a-194">ファイルに **%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Inline\app_code\customerserviceport.asmx.cs**と **%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Stub\app_code\customerserviceport.asmx.cs**17f20caea2afcc8c のすべてのインスタンスを a1054514fc67bded に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8703a-194">In the files **%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Inline\app_code\customerserviceport.asmx.cs** and **%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Stub\app_code\customerserviceport.asmx.cs**, replace all the instances of 17f20caea2afcc8c with a1054514fc67bded.</span></span>  
  
2. <span data-ttu-id="8703a-195">Visual Studio コマンド プロンプトでディレクトリを %BTSSolutionsPath%\SO\BTSSoln フォルダーに変更し、サービス指向ソリューションのスタブ バージョンをビルドする次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8703a-195">At the Visual Studio Command Prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln folder, and then run the following command to build the stub version of service-oriented solution.</span></span>  
  
   -   `SetupBTSSoln.bat`  
  
   > [!NOTE]
   >  <span data-ttu-id="8703a-196">以下のファイルで、17f20caea2afcc8c のすべてのインスタンスを現在の公開キー トークンに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8703a-196">In the files listed below, replace all the instances of 17f20caea2afcc8c with the current public key token.</span></span>  
   > 
   > - <span data-ttu-id="8703a-197">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_CustomerServiceResponse.btm.cs</span><span class="sxs-lookup"><span data-stu-id="8703a-197">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_CustomerServiceResponse.btm.cs</span></span>  
   >   -   <span data-ttu-id="8703a-198">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_ErrorResponse.btm.cs</span><span class="sxs-lookup"><span data-stu-id="8703a-198">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_ErrorResponse.btm.cs</span></span>  
   >   -   <span data-ttu-id="8703a-199">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CreditLimitResponse.btm.cs</span><span class="sxs-lookup"><span data-stu-id="8703a-199">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CreditLimitResponse.btm.cs</span></span>  
   >   -   <span data-ttu-id="8703a-200">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CustomerServiceResponseDenied.btm.cs</span><span class="sxs-lookup"><span data-stu-id="8703a-200">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CustomerServiceResponseDenied.btm.cs</span></span>  
   >   -   <span data-ttu-id="8703a-201">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_LastPaymentResponseTimeout.btm.cs</span><span class="sxs-lookup"><span data-stu-id="8703a-201">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_LastPaymentResponseTimeout.btm.cs</span></span>  
   >   -   <span data-ttu-id="8703a-202">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_PendingTransactionResponse.btm.cs</span><span class="sxs-lookup"><span data-stu-id="8703a-202">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_PendingTransactionResponse.btm.cs</span></span>  
  
##  <a name="step9"></a> <span data-ttu-id="8703a-203">SSO データベース内のエンタープライズ シングル サインオン (SSO) エントリと値を作成します。</span><span class="sxs-lookup"><span data-stu-id="8703a-203">Create the Enterprise Single Sign-On (SSO) entries and values in the SSO database</span></span>  
  
#### <a name="to-create-the-enterprise-single-sign-on-sso-entries-and-values-in-the-sso-database"></a><span data-ttu-id="8703a-204">SSO データベースで、エンタープライズ シングル サインオン (SSO) エントリと値を作成するには</span><span class="sxs-lookup"><span data-stu-id="8703a-204">To create the Enterprise Single Sign-On (SSO) entries and values in the SSO database</span></span>  
  
1.  <span data-ttu-id="8703a-205">コマンド プロンプトを開き、BTSSolutionsPath%\SO\BTSSoln\Scripts % に現在のディレクトリを変更し、エンタープライズ シングル サインオン フォルダーのパスの環境を設定するのには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8703a-205">Open a command prompt, change the current directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts, and then run the following command to set the PATH environment for the Enterprise Single Sign-On folder.</span></span>  
  
    -   `Set PATH=%PATH%;%ProgramFiles%\"Common Files\Enterprise Single Sign-On"`  
  
2.  <span data-ttu-id="8703a-206">コマンド プロンプトでディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更を開いて、メモ帳で ConfigStoreApp.xml ファイルの内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="8703a-206">At the command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder, open ConfigStoreApp.xml using Notepad, and then review the contents of the file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8703a-207">このファイルは、構成パラメーターを格納するシナリオを使用して sso 構成ストアのアプリケーションを定義します。</span><span class="sxs-lookup"><span data-stu-id="8703a-207">This file defines the configuration store application in SSO that the scenario uses to store configuration parameters.</span></span> <span data-ttu-id="8703a-208">一部の構成パラメーターを含める、**タイムアウト**(のすべての 3 つのバージョン) SAP との通信に使用される値。</span><span class="sxs-lookup"><span data-stu-id="8703a-208">Some of the configuration parameters include the **Timeout** value used to communicate with SAP (for all three versions).</span></span> <span data-ttu-id="8703a-209">このファイルへの変更は、不要です。</span><span class="sxs-lookup"><span data-stu-id="8703a-209">No changes to this file are necessary.</span></span>  
  
3.  <span data-ttu-id="8703a-210">コマンド プロンプトで、SSO 構成ストア アプリケーションを作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8703a-210">At the command prompt, run the following command to create the SSO configuration store application.</span></span>  
  
    -   `ssomanage -createapps ConfigStoreApp.xml`  
  
4.  <span data-ttu-id="8703a-211">コマンド プロンプトで メモ帳を使用して SetConfigValuesInSSO.cmd を開き、ファイルの内容を確認</span><span class="sxs-lookup"><span data-stu-id="8703a-211">At the command prompt, open SetConfigValuesInSSO.cmd using Notepad, and then review the contents of the file</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8703a-212">このコマンド ファイルは、SSO データベース内の構成パラメーターの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="8703a-212">This command file sets the values of the configuration parameters in the SSO database.</span></span> <span data-ttu-id="8703a-213">コマンド ファイルの先頭で、ローカル変数に値を設定するいくつかの set ステートメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8703a-213">It contains several set statements that set the values in local variables in the beginning of the command file.</span></span> <span data-ttu-id="8703a-214">**SAPAdapterTimeout**、 **PendingTransactionsAdapterTimeout**、および**PaymentTrackingAdapterTimeout**値、スタブとアダプターのバージョンで使用されます。</span><span class="sxs-lookup"><span data-stu-id="8703a-214">The **SAPAdapterTimeout**, **PendingTransactionsAdapterTimeout**, and **PaymentTrackingAdapterTimeout** values are used in the stub and adapter version.</span></span> <span data-ttu-id="8703a-215">他の値は、インライン バージョンで使用されます。</span><span class="sxs-lookup"><span data-stu-id="8703a-215">The remaining values are used in the inline version.</span></span> <span data-ttu-id="8703a-216">このファイルに対する変更は、スタブ バージョンの場合ではありません。</span><span class="sxs-lookup"><span data-stu-id="8703a-216">No changes to this file are necessary for stub version.</span></span>  
  
5.  <span data-ttu-id="8703a-217">コマンド プロンプトで「 `SetConfigValuesInSSO.cmd`、し、enter キーを押して、SSO 構成ストア アプリケーションで値を格納します。</span><span class="sxs-lookup"><span data-stu-id="8703a-217">At the command prompt, type `SetConfigValuesInSSO.cmd`, and then press ENTER to store the values in the SSO configuration store application.</span></span>  
  
6.  <span data-ttu-id="8703a-218">コマンド プロンプトで、SSO のチケットを有効にするのには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8703a-218">At the command prompt, run the following command to enable tickets in SSO:</span></span>  
  
    -   `ssomanage -tickets yes yes`  
  
##  <a name="step11"></a> <span data-ttu-id="8703a-219">サービス指向ソリューションの BAM 定義を展開します。</span><span class="sxs-lookup"><span data-stu-id="8703a-219">Deploy the BAM definition for the Service Oriented Solution</span></span>  
  
#### <a name="to-deploy-the-bam-definition-for-the-service-oriented-solution"></a><span data-ttu-id="8703a-220">サービス指向ソリューションの BAM 定義を展開するには</span><span class="sxs-lookup"><span data-stu-id="8703a-220">To deploy the BAM definition for the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="8703a-221">コマンド プロンプトで次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8703a-221">At a command prompt, type the following command, and then press ENTER.</span></span> <span data-ttu-id="8703a-222">これは、BAM ユーティリティへのパスを設定します。</span><span class="sxs-lookup"><span data-stu-id="8703a-222">This sets the path to find the BAM utility:</span></span>  
  
    -   <span data-ttu-id="8703a-223">SET PATH=%PATH%;%programfiles%\Microsoft BizTalk Server\Tracking</span><span class="sxs-lookup"><span data-stu-id="8703a-223">SET PATH=%PATH%;%programfiles%\Microsoft BizTalk Server\Tracking</span></span>  
  
2.  <span data-ttu-id="8703a-224">コマンド プロンプトで %BTSSolutionsPath%\SO\BTSSoln\BAM フォルダーにディレクトリを変更して、次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8703a-224">At the command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln\BAM folder, and type the following command, and then press ENTER:</span></span>  
  
    -   `bm deploy-all -DefinitionFile:ServiceLevelTracking.xml`  
  
        > [!NOTE]
        >  <span data-ttu-id="8703a-225">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="8703a-225">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
##  <a name="step13"></a> <span data-ttu-id="8703a-226">デプロイ サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="8703a-226">Deploy the Service Oriented Solution</span></span>  
  
#### <a name="to-deploy-the-service-oriented-solution"></a><span data-ttu-id="8703a-227">サービス指向ソリューションをデプロイするには</span><span class="sxs-lookup"><span data-stu-id="8703a-227">To deploy the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="8703a-228">コマンド プロンプトを開き、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更します。</span><span class="sxs-lookup"><span data-stu-id="8703a-228">Open a command prompt and change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder.</span></span>  
  
2.  <span data-ttu-id="8703a-229">変更、 **DeployStubBinding.cmd** "debug"と「開発」のすべてのインスタンスを「リリース」に置き換えることによりファイル。</span><span class="sxs-lookup"><span data-stu-id="8703a-229">Modify the **DeployStubBinding.cmd** file by replacing all the instances of “debug” and “development” with “release”.</span></span>  
  
3.  <span data-ttu-id="8703a-230">コマンド プロンプトを開き、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更します。</span><span class="sxs-lookup"><span data-stu-id="8703a-230">Open a command prompt and change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder.</span></span> <span data-ttu-id="8703a-231">次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8703a-231">Type the following command, and then press ENTER:</span></span>  
  
    -   `DeployStubBinding.cmd`  
  
4.  <span data-ttu-id="8703a-232">コマンド プロンプトでは、スタブ バージョン用のオーケストレーションを開始するには、次のコマンドを実行します</span><span class="sxs-lookup"><span data-stu-id="8703a-232">At the command prompt, run the following command to start the orchestrations for the stub version</span></span>  
  
    -   `Startstub.vbs`  
  
## <a name="next-steps"></a><span data-ttu-id="8703a-233">次の手順</span><span class="sxs-lookup"><span data-stu-id="8703a-233">Next Steps</span></span>  
 <span data-ttu-id="8703a-234">サービス指向ソリューションのスタブ バージョンがどのように動作するかをテストする[サービス指向ソリューションを実行する方法](../core/how-to-run-the-service-oriented-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="8703a-234">You test how the stub version of the service-oriented solution works in [How to Run the Service Oriented Solution](../core/how-to-run-the-service-oriented-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8703a-235">参照</span><span class="sxs-lookup"><span data-stu-id="8703a-235">See Also</span></span>  
 <span data-ttu-id="8703a-236">[サービス指向ソリューションをインストールする前に](../core/before-installing-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="8703a-236">[Before Installing the Service Oriented Solution](../core/before-installing-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="8703a-237">[指向ソリューションのインライン バージョンおよびアダプター バージョンのサービスをインストールする方法](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="8703a-237">[How to Install the Inline and Adapter Versions of the Service Oriented Solution](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="8703a-238">サービス指向ソリューションに対する開発者のコンピューター設定</span><span class="sxs-lookup"><span data-stu-id="8703a-238">Developer Machine Setup for the Service Oriented Solution</span></span>](../core/developer-machine-setup-for-the-service-oriented-solution.md)