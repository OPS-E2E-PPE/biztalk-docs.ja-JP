---
title: "指向ソリューションのスタブ バージョンのサービスをインストールする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "53"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adaf5cb0117e0d571e0be0ddd42350ce3af2ba80
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-install-the-stub-version-of-the-service-oriented-solution"></a><span data-ttu-id="61cc9-102">サービス指向ソリューションのスタブ バージョンのインストール方法</span><span class="sxs-lookup"><span data-stu-id="61cc9-102">How to Install the Stub Version of the Service Oriented Solution</span></span>
<span data-ttu-id="61cc9-103">次の手順では、サービス指向ソリューションのスタブ バージョンをインストールするための事前準備を行う方法およびコンピューターにソリューションをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-103">The following steps describe how to prepare your computer before you install the stub version of the service oriented solution, and then how to install the solution on your computer.</span></span>  
  
-   [<span data-ttu-id="61cc9-104">サービス指向ソリューションのスタブ バージョンをインストールするコンピューターを準備します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-104">Prepare the computer for installing the stub version of the Service Oriented Solution</span></span>](#step1)  
  
-   [<span data-ttu-id="61cc9-105">IBM WebSphere MQ Client for Windows をインストールします。</span><span class="sxs-lookup"><span data-stu-id="61cc9-105">Install the IBM WebSphere MQ Client for Windows</span></span>](#step3)  
  
-   [<span data-ttu-id="61cc9-106">サービス指向ソリューションの IIS で仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-106">Create the virtual directories in IIS for the Service Oriented Solution</span></span>](#step5)  
  
-   [<span data-ttu-id="61cc9-107">ビルド サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="61cc9-107">Build the Service Oriented Solution</span></span>](#step7)  
  
-   [<span data-ttu-id="61cc9-108">SSO データベース内のエンタープライズ シングル サインオン (SSO) エントリと値を作成します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-108">Create the Enterprise Single Sign-On (SSO) entries and values in the SSO database</span></span>](#step9)  
  
-   [<span data-ttu-id="61cc9-109">サービス指向ソリューションの BAM 定義を展開します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-109">Deploy the BAM definition for the Service Oriented Solution</span></span>](#step11)  
  
-   [<span data-ttu-id="61cc9-110">サービス指向ソリューションの展開</span><span class="sxs-lookup"><span data-stu-id="61cc9-110">Deploy the Service Oriented Solution</span></span>](#step13)  
  
##  <a name="step1"></a><span data-ttu-id="61cc9-111">サービス指向ソリューションのスタブ バージョンをインストールするコンピューターを準備します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-111">Prepare the computer for installing the stub version of the Service Oriented Solution</span></span>  
  
#### <a name="to-prepare-the-computer-for-installing-the-stub-version-of-the-service-oriented-solution"></a><span data-ttu-id="61cc9-112">サービス指向ソリューションのスタブ バージョンをコンピューターにインストールするための準備を行うには</span><span class="sxs-lookup"><span data-stu-id="61cc9-112">To prepare the computer for installing the stub version of the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="61cc9-113">確認して、 **Default Web Site** ASP.NET を使用するように構成が 2.X です。</span><span class="sxs-lookup"><span data-stu-id="61cc9-113">Make sure that the **Default Web Site** is configured to use ASP.NET 2.X.</span></span>  
  
    1.  <span data-ttu-id="61cc9-114">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、クリックして**インターネット インフォメーション サービス (IIS) マネージャー**.</span><span class="sxs-lookup"><span data-stu-id="61cc9-114">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
    2.  <span data-ttu-id="61cc9-115">**インターネット インフォメーション サービス (IIS) マネージャー**、マシン名を展開**サイト**、展開**Default Web Site**、展開**aspnet_client**、展開**[system_web]**です。</span><span class="sxs-lookup"><span data-stu-id="61cc9-115">In the **Internet Information Services (IIS) Manager**, the machine name, expand  **Sites**, expand **Default Web Site**, expand **aspnet_client**, expand **system_web**.</span></span>  
  
    3.  <span data-ttu-id="61cc9-116">サブフォルダーが 2.X であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-116">Make sure that the sub-folder is 2.X.</span></span>  
  
2.  <span data-ttu-id="61cc9-117">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリック**Services**です。</span><span class="sxs-lookup"><span data-stu-id="61cc9-117">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span> <span data-ttu-id="61cc9-118">使用して、 **Services**コンソールで、次のサービスが実行されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="61cc9-118">Using the **Services** console, make sure that the following services are running:</span></span>  
  
    -   <span data-ttu-id="61cc9-119">**World Wide Web 発行**</span><span class="sxs-lookup"><span data-stu-id="61cc9-119">**World Wide Web Publishing**</span></span>  
  
3.  <span data-ttu-id="61cc9-120">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、 をクリックして**コンピューターの管理**コンソール、および追加し、ローカルの Administrators グループに BizTalk サービス アカウント。</span><span class="sxs-lookup"><span data-stu-id="61cc9-120">Click **Start**, point to **All Programs**, point to **Administrative Tools**, click **Computer Management** console, and then add the BizTalk service account to the local Administrators group.</span></span>  
  
4.  <span data-ttu-id="61cc9-121">Windows SharePoint Services をインストールした場合は、(ルート) を除外する、**既定の Web サイト**Windows SharePoint Services 管理パスから次のようにします をクリック**開始**、 をポイント**すべてのプログラム。**、指す**管理ツール**、順にクリック**SharePoint サーバーの全体管理**です。</span><span class="sxs-lookup"><span data-stu-id="61cc9-121">If you installed Windows SharePoint Services, exclude the (root) of the **Default Web Site** from Windows SharePoint Services Managed Paths as follows: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
    1.  <span data-ttu-id="61cc9-122">**仮想サーバーの構成****仮想サーバーの設定を構成する**です。</span><span class="sxs-lookup"><span data-stu-id="61cc9-122">Under **Virtual Server Configuration**, select **Configure virtual server settings**.</span></span>  
  
    2.  <span data-ttu-id="61cc9-123">**仮想サーバーのリスト**] ページで [**既定の Web サイト**です。</span><span class="sxs-lookup"><span data-stu-id="61cc9-123">On the **Virtual Server List** page, click **Default Web Site**.</span></span>  
  
    3.  <span data-ttu-id="61cc9-124">**仮想サーバーの設定**] ページで [**管理パスの定義**です。</span><span class="sxs-lookup"><span data-stu-id="61cc9-124">On the **Virtual Server Settings** page, click **Define managed paths**.</span></span>  
  
    4.  <span data-ttu-id="61cc9-125">**インクルード パス**のセクションで、**管理パスの定義** ページで、**ルート** をクリックし、**選択したパスの削除**です。</span><span class="sxs-lookup"><span data-stu-id="61cc9-125">In the **Included Paths** section of the **Defined Managed Path** page, select **Root** and then click **Remove selected paths**.</span></span>  
  
    5.  <span data-ttu-id="61cc9-126">コマンド プロンプトで IISReset コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-126">At a command prompt, perform an IISReset.</span></span>  
  
5.  <span data-ttu-id="61cc9-127">コンピュータからログオフして、BizTalk サービス アカウントを使用してコンピュータにログオンします。</span><span class="sxs-lookup"><span data-stu-id="61cc9-127">Log off the computer, and then log on to the computer as the BizTalk service account.</span></span>  
  
6.  <span data-ttu-id="61cc9-128">コマンド プロンプトを開いて、次のコマンドを入力し、<localizedText>Enter</localizedText> キーを押して、%BTSSolutionsPath% 環境変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-128">Open a command prompt, type the following command, and then press ENTER to set the %BTSSolutionsPath% environment.</span></span> <span data-ttu-id="61cc9-129">次に、コマンド プロンプトを終了します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-129">Then, exit the command prompt.</span></span>  
  
    -   <span data-ttu-id="61cc9-130">setx BTSSolutionsPath "[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"</span><span class="sxs-lookup"><span data-stu-id="61cc9-130">setx BTSSolutionsPath "[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="61cc9-131">64 ビット コンピューターを使用する場合は、「%ProgramFiles%」の代わりに「%ProgramFiles%(x86)」と入力してください。</span><span class="sxs-lookup"><span data-stu-id="61cc9-131">If you are using a 64-bit computer, use %ProgramFiles(x86)% instead of %ProgramFiles%.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="61cc9-132">SETX コマンドの詳細については、Microsoft TechNet Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831)です。</span><span class="sxs-lookup"><span data-stu-id="61cc9-132">For more information about the SETX command, see the Microsoft TechNet Web site at [http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831).</span></span>  
  
##  <a name="step3"></a><span data-ttu-id="61cc9-133">IBM WebSphere MQ Client for Windows をインストールします。</span><span class="sxs-lookup"><span data-stu-id="61cc9-133">Install the IBM WebSphere MQ Client for Windows</span></span>  
  
#### <a name="to-install-the-ibm-websphere-mq-client-for-windows"></a><span data-ttu-id="61cc9-134">IBM WebSphere MQ Client for Windows をインストールするには</span><span class="sxs-lookup"><span data-stu-id="61cc9-134">To install the IBM WebSphere MQ Client for Windows</span></span>  
  
1.  <span data-ttu-id="61cc9-135">IBM WebSphere MQ Client for Windows の最新バージョンをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="61cc9-135">Download the latest version of IBM WebSphere MQ Client for Windows.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="61cc9-136">このソリューションのスタブ バージョンで IBM WebSphere Server を使用しない場合でも、クライアント アプリケーションは、IBM WebSphere MQ Client for Windows から提供される amqmdnet.dll ファイルを参照します。このため、IBM WebSphere MQ Client for Windows をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="61cc9-136">Even if the stub version of the solution doesn't require IBM WebSphere Server, the client application references the amqmdnet.dll file provided by IBM WebSphere MQ Client for Windows, so you must install it.</span></span> <span data-ttu-id="61cc9-137">スタブ バージョンのクライアントは、この DLL の API を実際に呼び出しません。</span><span class="sxs-lookup"><span data-stu-id="61cc9-137">The client of the stub version does not actually call an API in the DLL.</span></span> <span data-ttu-id="61cc9-138">クライアント アプリケーションをコンパイルおよび実行する場合のみ、この DLL が必要です。</span><span class="sxs-lookup"><span data-stu-id="61cc9-138">It is required only for compiling and running the client application.</span></span> <span data-ttu-id="61cc9-139">IBM Web サイトから IBM WebSphere MQ Client for Windows をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="61cc9-139">You can download IBM WebSphere MQ Client for Windows from the IBM Web site.</span></span>  
  
2.  <span data-ttu-id="61cc9-140">IBM WebSphere MQ Client for Windows をインストールします。</span><span class="sxs-lookup"><span data-stu-id="61cc9-140">Install IBM WebSphere MQ Client for Windows.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="61cc9-141">IBM WebSphere MQ Client for Windows を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="61cc9-141">You don't need to configure IBM WebSphere MQ Client for Windows.</span></span> <span data-ttu-id="61cc9-142">すべて既定の設定のままにします。</span><span class="sxs-lookup"><span data-stu-id="61cc9-142">Keep all of the default settings.</span></span>  
  
3.  <span data-ttu-id="61cc9-143">.NET アセンブリの WebSphere MQ クラスをグローバル アセンブリ キャッシュ (GAC) に追加します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-143">Add WebSphere MQ classes for the .NET assembly to the global assembly cache (GAC).</span></span>  
  
    1.  <span data-ttu-id="61cc9-144">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリに移動\<IBM MQSeries インストール ディレクトリ\>\bin です。</span><span class="sxs-lookup"><span data-stu-id="61cc9-144">At the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, navigate to the directory \<IBM MQSeries Installation Directory\>\bin.</span></span>  
  
    2.  <span data-ttu-id="61cc9-145">次のコマンドを実行します (gacutil.exe が PATH 環境変数にあることを確認してください)。</span><span class="sxs-lookup"><span data-stu-id="61cc9-145">Run the following command (make sure gacutil.exe is in the path environment):</span></span>  
  
         `gacutil.exe /i amqmdnet.dll`  
  
##  <a name="step5"></a><span data-ttu-id="61cc9-146">サービス指向ソリューションの IIS で仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-146">Create the virtual directories in IIS for the Service Oriented Solution</span></span>  
  
#### <a name="to-create-the-virtual-directories-in-iis-for-the-service-oriented-solution"></a><span data-ttu-id="61cc9-147">サービス指向ソリューションの IIS に仮想ディレクトリを作成するには</span><span class="sxs-lookup"><span data-stu-id="61cc9-147">To create the virtual directories in IIS for the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="61cc9-148">**インターネット インフォメーション サービス (IIS) マネージャー**を右クリックして**アプリケーション プール****アプリケーション プールの追加**です。</span><span class="sxs-lookup"><span data-stu-id="61cc9-148">In the **Internet Information Services (IIS) Manager**, right-click **Application Pools**, select **Add Application Pool**.</span></span>  
  
     <span data-ttu-id="61cc9-149">**アプリケーション プールの追加** ダイアログ ボックスで、「`SSOStubAppPool`で、**名前**テキスト ボックス、およびクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="61cc9-149">On the **Add Application Pool** dialog box, type `SSOStubAppPool` in the **Name** text box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="61cc9-150">サービス指向ソリューションで使用する仮想ディレクトリには、スタブ バージョンのオーケストレーション用に公開する Web サービス、スタブ SAP Web サービス、スタブ Payment Tracker Web サービス、スタブ Pending Transaction Web サービスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="61cc9-150">The virtual directories that service-oriented solution uses include the published Web service for the stub version of orchestrations, the stub SAP Web service, the stub Payment Tracker Web service, and the stub Pending Transaction Web service.</span></span>  
  
2.  <span data-ttu-id="61cc9-151">**インターネット インフォメーション サービス (IIS) マネージャー**作成したアプリケーション プールを右クリックし、クリックして**詳細設定**です。</span><span class="sxs-lookup"><span data-stu-id="61cc9-151">In the **Internet Information Services (IIS) Manager**, right-click the application pool that you just created, and then click **Advanced Settings**.</span></span>  
  
3.  <span data-ttu-id="61cc9-152">右側に列をクリックして、 **Identity**プロパティ、クリックして、省略記号 (**.**) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="61cc9-152">Click in the column to the right of the **Identity** property, and then click the ellipsis (**…**) button.</span></span>  
  
4.  <span data-ttu-id="61cc9-153">**アプリケーション プール Id**ダイアログ ボックスで、**カスタム アカウント**オプションをクリックして**設定**です。</span><span class="sxs-lookup"><span data-stu-id="61cc9-153">In the **Application Pool Identity** dialog box, select the **Custom Account** option, and then click **Set**.</span></span>  
  
5.  <span data-ttu-id="61cc9-154">**資格情報の設定**ダイアログ ボックスで、ユーザー名とパスワードを指定、パスワードを確認して、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="61cc9-154">In the **Set Credentials** dialog box, specify a username and password, confirm the password, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="61cc9-155">このユーザーには、オーケストレーション プロキシ Web サービスを実行する権限が必要です。また、BizTalk Server 管理者グループ、SSO 管理者グループ、または SSO 関連管理者グループのいずれかにこのユーザーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61cc9-155">This user must have permission to execute the Orchestration Proxy Web service, and must be added to one of the BizTalk Server Administrators, SSO Administrators, or SSO Affiliated Administrators groups</span></span>  
  
6.  <span data-ttu-id="61cc9-156">をクリックして**OK**を閉じる、**アプリケーション プール Id**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="61cc9-156">Click **OK** to close the **Application Pool Identity** dialog box.</span></span>  
  
7.  <span data-ttu-id="61cc9-157">**[OK]** をクリックして **[詳細設定]** ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="61cc9-157">Click **OK** to close the **Advanced Settings** dialog box.</span></span>  
  
8.  <span data-ttu-id="61cc9-158">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**を右クリックし、**既定の Web サイト**、 をポイント**新規**とをクリックして**仮想ディレクトリ**を実行する**仮想ディレクトリの作成ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="61cc9-158">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
    1.  <span data-ttu-id="61cc9-159">使用して、**仮想ディレクトリの作成ウィザード**、アダプター バージョン用の Web サービス プロキシの次の仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-159">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the proxy Web service for the adapter version:</span></span>  
  
         <span data-ttu-id="61cc9-160">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub</span><span class="sxs-lookup"><span data-stu-id="61cc9-160">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub</span></span>  
  
         <span data-ttu-id="61cc9-161">パス = \<BizTalk インストール ディレクトリ\>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Stub</span><span class="sxs-lookup"><span data-stu-id="61cc9-161">PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Stub</span></span>  
  
         <span data-ttu-id="61cc9-162">Access Permissions = Read, Run scripts</span><span class="sxs-lookup"><span data-stu-id="61cc9-162">Access Permissions = Read, Run scripts</span></span>  
  
    2.  <span data-ttu-id="61cc9-163">使用して、**仮想ディレクトリの作成ウィザード**、アダプター バージョン用の Web サービス プロキシの次の仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-163">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the proxy Web service for the adapter version:</span></span>  
  
         <span data-ttu-id="61cc9-164">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP</span><span class="sxs-lookup"><span data-stu-id="61cc9-164">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP</span></span>  
  
         <span data-ttu-id="61cc9-165">パス = \<BizTalk インストール ディレクトリ\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP</span><span class="sxs-lookup"><span data-stu-id="61cc9-165">PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP</span></span>  
  
         <span data-ttu-id="61cc9-166">Access Permissions = Read, Run scripts</span><span class="sxs-lookup"><span data-stu-id="61cc9-166">Access Permissions = Read, Run scripts</span></span>  
  
    3.  <span data-ttu-id="61cc9-167">使用して、**仮想ディレクトリの作成ウィザード**、アダプター バージョン用の Web サービス プロキシの次の仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-167">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the proxy Web service for the adapter version:</span></span>  
  
         <span data-ttu-id="61cc9-168">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions</span><span class="sxs-lookup"><span data-stu-id="61cc9-168">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions</span></span>  
  
         <span data-ttu-id="61cc9-169">パス = \<BizTalk インストール ディレクトリ\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans</span><span class="sxs-lookup"><span data-stu-id="61cc9-169">PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans</span></span>  
  
         <span data-ttu-id="61cc9-170">Access Permissions = Read, Run scripts</span><span class="sxs-lookup"><span data-stu-id="61cc9-170">Access Permissions = Read, Run scripts</span></span>  
  
    4.  <span data-ttu-id="61cc9-171">使用して、**仮想ディレクトリの作成ウィザード**、アダプター バージョン用の Web サービス プロキシの次の仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-171">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the proxy Web service for the adapter version:</span></span>  
  
         <span data-ttu-id="61cc9-172">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker</span><span class="sxs-lookup"><span data-stu-id="61cc9-172">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker</span></span>  
  
         <span data-ttu-id="61cc9-173">パス = \<BizTalk インストール ディレクトリ\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PaymentTrack</span><span class="sxs-lookup"><span data-stu-id="61cc9-173">PATH = \<BizTalk Install Directory\>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PaymentTrack</span></span>  
  
         <span data-ttu-id="61cc9-174">Access Permissions = Read, Run scripts</span><span class="sxs-lookup"><span data-stu-id="61cc9-174">Access Permissions = Read, Run scripts</span></span>  
  
9. <span data-ttu-id="61cc9-175">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Web サイト、**展開、 **Default Web Site**を右クリックしてMicrosoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub をクリックして**プロパティ**、し、次のように設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-175">In the **Internet Information Services (IIS) Manager**, expand **Web Sites,** expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="61cc9-176">**仮想ディレクトリ** タブで、設定、**アプリケーション プール**に**SSOStubAppPool**で作成しました。</span><span class="sxs-lookup"><span data-stu-id="61cc9-176">On the **Virtual directory** tab, set the **Application Pool** to **SSOStubAppPool** you just created.</span></span>  
  
    2.  <span data-ttu-id="61cc9-177">をクリックして**ディレクトリ セキュリティ** タブで、をクリックして**編集**で、**認証とアクセス制御**グループ ボックスで、**統合 Windows 認証のみ有効になっている**、し、その他のオフ**認証アクセス**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="61cc9-177">Click **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, select **Only Integrated Windows Authentication enabled**, and then clear other **Authentication access** checkboxes.</span></span> <span data-ttu-id="61cc9-178">をクリックして**OK**を終了します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-178">Click **OK** to exit.</span></span>  
  
10. <span data-ttu-id="61cc9-179">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Web サイト、**展開、 **Default Web Site**を右クリックしてMicrosoft.Samples.BizTalk.WoodgroveBank.StubSAP をクリックして**プロパティ**、し、次のように設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-179">In the **Internet Information Services (IIS) Manager**, expand **Web Sites,** expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="61cc9-180">**仮想ディレクトリ** タブで、設定、**アプリケーション プール**に**SSOStubAppPool**で作成しました。</span><span class="sxs-lookup"><span data-stu-id="61cc9-180">On the **Virtual directory** tab, set the **Application Pool** to **SSOStubAppPool** you just created.</span></span>  
  
    2.  <span data-ttu-id="61cc9-181">をクリックして**ディレクトリ セキュリティ**] タブで、をクリックして**編集**で、**認証とアクセス制御**ボックスで、グループ化し、[ **の匿名アクセスの有効化**.</span><span class="sxs-lookup"><span data-stu-id="61cc9-181">Click **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, and then select **Enable Anonymous Access**.</span></span> <span data-ttu-id="61cc9-182">をクリックして**OK**を終了します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-182">Click **OK** to exit.</span></span>  
  
11. <span data-ttu-id="61cc9-183">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Web サイト、**展開、 **Default Web Site**を右クリックしてMicrosoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions をクリックして**プロパティ**、し、次のように設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-183">In the **Internet Information Services (IIS) Manager**, expand **Web Sites,** expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="61cc9-184">**仮想ディレクトリ** タブで、設定、**アプリケーション プール**に**SSOStubAppPool**で作成しました。</span><span class="sxs-lookup"><span data-stu-id="61cc9-184">On the **Virtual directory** tab, set the **Application Pool** to **SSOStubAppPool** you just created.</span></span>  
  
    2.  <span data-ttu-id="61cc9-185">をクリックして**ディレクトリ セキュリティ**] タブで、をクリックして**編集**で、**認証とアクセス制御**ボックスで、グループ化し、[ **の匿名アクセスの有効化**.</span><span class="sxs-lookup"><span data-stu-id="61cc9-185">Click **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, and then select **Enable Anonymous Access**.</span></span> <span data-ttu-id="61cc9-186">をクリックして**OK**を終了します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-186">Click **OK** to exit.</span></span>  
  
12. <span data-ttu-id="61cc9-187">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Web サイト、**展開、 **Default Web Site**を右クリックしてMicrosoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker をクリックして**プロパティ**、し、次のように設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-187">In the **Internet Information Services (IIS) Manager**, expand **Web Sites,** expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="61cc9-188">**仮想ディレクトリ** タブで、設定、**アプリケーション プール**に**SSOStubAppPool**で作成しました。</span><span class="sxs-lookup"><span data-stu-id="61cc9-188">On the **Virtual directory** tab, set the **Application Pool** to **SSOStubAppPool** you just created.</span></span>  
  
    2.  <span data-ttu-id="61cc9-189">をクリックして**ディレクトリ セキュリティ**] タブで、をクリックして**編集**で、**認証とアクセス制御**ボックスで、グループ化し、[ **の匿名アクセスの有効化**.</span><span class="sxs-lookup"><span data-stu-id="61cc9-189">Click **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, and then select **Enable Anonymous Access**.</span></span> <span data-ttu-id="61cc9-190">をクリックして**OK**を終了します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-190">Click **OK** to exit.</span></span>  
  
##  <a name="step7"></a><span data-ttu-id="61cc9-191">ビルド サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="61cc9-191">Build the Service Oriented Solution</span></span>  
  
#### <a name="to-build-the-service-oriented-solution"></a><span data-ttu-id="61cc9-192">サービス指向ソリューションをビルドするには</span><span class="sxs-lookup"><span data-stu-id="61cc9-192">To build the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="61cc9-193">開始**Visual Studio コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="61cc9-193">Start **Visual Studio Command Prompt**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="61cc9-194">ファイルに**%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Inline\app_code\customerserviceport.asmx.cs**と**%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Stub\app_code\customerserviceport.asmx.cs**17f20caea2afcc8c のすべてのインスタンスを a1054514fc67bded に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="61cc9-194">In the files **%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Inline\app_code\customerserviceport.asmx.cs** and **%BTSInstallPath%\Scenarios\SO\BTSSoln\OrchProxy\Stub\app_code\customerserviceport.asmx.cs**, replace all the instances of 17f20caea2afcc8c with a1054514fc67bded.</span></span>  
  
2.  <span data-ttu-id="61cc9-195">Visual Studio コマンド プロンプトで、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln フォルダーに変更し、次のコマンドを実行して、サービス指向ソリューションのスタブ バージョンをビルドします。</span><span class="sxs-lookup"><span data-stu-id="61cc9-195">At the Visual Studio Command Prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln folder, and then run the following command to build the stub version of service-oriented solution.</span></span>  
  
    -   `SetupBTSSoln.bat`  
  
    > [!NOTE]
    >  <span data-ttu-id="61cc9-196">次に示すファイルで、17f20caea2afcc8c のすべてのインスタンスを現在の公開キー トークンに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="61cc9-196">In the files listed below, replace all the instances of 17f20caea2afcc8c with the current public key token.</span></span>  
    >   
    >  -   <span data-ttu-id="61cc9-197">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_CustomerServiceResponse.btm.cs</span><span class="sxs-lookup"><span data-stu-id="61cc9-197">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_CustomerServiceResponse.btm.cs</span></span>  
    > -   <span data-ttu-id="61cc9-198">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_ErrorResponse.btm.cs</span><span class="sxs-lookup"><span data-stu-id="61cc9-198">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\Aggregate_To_ErrorResponse.btm.cs</span></span>  
    > -   <span data-ttu-id="61cc9-199">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CreditLimitResponse.btm.cs</span><span class="sxs-lookup"><span data-stu-id="61cc9-199">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CreditLimitResponse.btm.cs</span></span>  
    > -   <span data-ttu-id="61cc9-200">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CustomerServiceResponseDenied.btm.cs</span><span class="sxs-lookup"><span data-stu-id="61cc9-200">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_CustomerServiceResponseDenied.btm.cs</span></span>  
    > -   <span data-ttu-id="61cc9-201">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_LastPaymentResponseTimeout.btm.cs</span><span class="sxs-lookup"><span data-stu-id="61cc9-201">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_LastPaymentResponseTimeout.btm.cs</span></span>  
    > -   <span data-ttu-id="61cc9-202">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_PendingTransactionResponse.btm.cs</span><span class="sxs-lookup"><span data-stu-id="61cc9-202">%BTSInstallPath%\Scenarios\SO\BTSSoln\Maps\CustomerServiceRequest_To_PendingTransactionResponse.btm.cs</span></span>  
  
##  <a name="step9"></a><span data-ttu-id="61cc9-203">SSO データベース内のエンタープライズ シングル サインオン (SSO) エントリと値を作成します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-203">Create the Enterprise Single Sign-On (SSO) entries and values in the SSO database</span></span>  
  
#### <a name="to-create-the-enterprise-single-sign-on-sso-entries-and-values-in-the-sso-database"></a><span data-ttu-id="61cc9-204">エンタープライズ シングル サインオン (SSO) エントリおよび SSO データベースの値を作成するには</span><span class="sxs-lookup"><span data-stu-id="61cc9-204">To create the Enterprise Single Sign-On (SSO) entries and values in the SSO database</span></span>  
  
1.  <span data-ttu-id="61cc9-205">コマンド プロンプトを開いて、現在のディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts に変更し、次のコマンドを実行して、エンタープライズ シングル サインオン (SSO) フォルダーに使用する PATH 環境変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-205">Open a command prompt, change the current directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts, and then run the following command to set the PATH environment for the Enterprise Single Sign-On folder.</span></span>  
  
    -   `Set PATH=%PATH%;%ProgramFiles%\"Common Files\Enterprise Single Sign-On"`  
  
2.  <span data-ttu-id="61cc9-206">コマンド プロンプトで、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更します。次に、メモ帳で ConfigStoreApp.xml を開き、ファイルの内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-206">At the command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder, open ConfigStoreApp.xml using Notepad, and then review the contents of the file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="61cc9-207">このファイルは、このシナリオで構成パラメーターを保存するために使用する SSO の構成ストア アプリケーションを定義します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-207">This file defines the configuration store application in SSO that the scenario uses to store configuration parameters.</span></span> <span data-ttu-id="61cc9-208">構成パラメーターのものが、**タイムアウト**(すべて次の 3 つのバージョンで) SAP と通信するために使用される値。</span><span class="sxs-lookup"><span data-stu-id="61cc9-208">Some of the configuration parameters include the **Timeout** value used to communicate with SAP (for all three versions).</span></span> <span data-ttu-id="61cc9-209">このファイルへの変更は、不要です。</span><span class="sxs-lookup"><span data-stu-id="61cc9-209">No changes to this file are necessary.</span></span>  
  
3.  <span data-ttu-id="61cc9-210">コマンド プロンプトで、次のコマンドを実行して、SSO 構成ストア アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-210">At the command prompt, run the following command to create the SSO configuration store application.</span></span>  
  
    -   `ssomanage -createapps ConfigStoreApp.xml`  
  
4.  <span data-ttu-id="61cc9-211">コマンド プロンプトで、メモ帳を使用して SetConfigValuesInSSO.cmd を開き、ファイルの内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-211">At the command prompt, open SetConfigValuesInSSO.cmd using Notepad, and then review the contents of the file</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="61cc9-212">このコマンド ファイルは、SSO データベース内の構成パラメーターの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-212">This command file sets the values of the configuration parameters in the SSO database.</span></span> <span data-ttu-id="61cc9-213">コマンド ファイルの最初にローカル変数の値を設定する SET ステートメントがいくつか含まれます。</span><span class="sxs-lookup"><span data-stu-id="61cc9-213">It contains several set statements that set the values in local variables in the beginning of the command file.</span></span> <span data-ttu-id="61cc9-214">**SAPAdapterTimeout**、 **PendingTransactionsAdapterTimeout**、および**PaymentTrackingAdapterTimeout**値、スタブとアダプターのバージョンで使用されます。</span><span class="sxs-lookup"><span data-stu-id="61cc9-214">The **SAPAdapterTimeout**, **PendingTransactionsAdapterTimeout**, and **PaymentTrackingAdapterTimeout** values are used in the stub and adapter version.</span></span> <span data-ttu-id="61cc9-215">他の値は、インライン バージョンで使用されます。</span><span class="sxs-lookup"><span data-stu-id="61cc9-215">The remaining values are used in the inline version.</span></span> <span data-ttu-id="61cc9-216">スタブ バージョンの場合、このファイルへの変更は不要です。</span><span class="sxs-lookup"><span data-stu-id="61cc9-216">No changes to this file are necessary for stub version.</span></span>  
  
5.  <span data-ttu-id="61cc9-217">コマンド プロンプトで次のように入力します。 `SetConfigValuesInSSO.cmd`、し、ENTER キーを押して、SSO 構成ストア アプリケーションの値を格納します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-217">At the command prompt, type `SetConfigValuesInSSO.cmd`, and then press ENTER to store the values in the SSO configuration store application.</span></span>  
  
6.  <span data-ttu-id="61cc9-218">コマンド プロンプトで、次のコマンドを実行し、SSO のチケットを有効にします。</span><span class="sxs-lookup"><span data-stu-id="61cc9-218">At the command prompt, run the following command to enable tickets in SSO:</span></span>  
  
    -   `ssomanage -tickets yes yes`  
  
##  <a name="step11"></a><span data-ttu-id="61cc9-219">サービス指向ソリューションの BAM 定義を展開します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-219">Deploy the BAM definition for the Service Oriented Solution</span></span>  
  
#### <a name="to-deploy-the-bam-definition-for-the-service-oriented-solution"></a><span data-ttu-id="61cc9-220">サービス指向ソリューションの BAM 定義を展開するには</span><span class="sxs-lookup"><span data-stu-id="61cc9-220">To deploy the BAM definition for the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="61cc9-221">コマンド プロンプトで次のコマンドを入力し、&lt;localizedText&gt;Enter&lt;/localizedText&gt; キーを押します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-221">At a command prompt, type the following command, and then press ENTER.</span></span> <span data-ttu-id="61cc9-222">これには、BAM ユーティリティを検索するパスを設定します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-222">This sets the path to find the BAM utility:</span></span>  
  
    -   <span data-ttu-id="61cc9-223">セット PATH=%PATH%;%programfiles%\Microsoft BizTalk Server\Tracking</span><span class="sxs-lookup"><span data-stu-id="61cc9-223">SET PATH=%PATH%;%programfiles%\Microsoft BizTalk Server\Tracking</span></span>  
  
2.  <span data-ttu-id="61cc9-224">コマンド プロンプトで、ディレクトリを %BTSSolutions%\SO\BTSSoln\BAM フォルダーに変更し、次のコマンドを入力して Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-224">At the command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln\BAM folder, and type the following command, and then press ENTER:</span></span>  
  
    -   `bm deploy-all -DefinitionFile:ServiceLevelTracking.xml`  
  
        > [!NOTE]
        >  <span data-ttu-id="61cc9-225">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="61cc9-225">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
##  <a name="step13"></a><span data-ttu-id="61cc9-226">配置サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="61cc9-226">Deploy the Service Oriented Solution</span></span>  
  
#### <a name="to-deploy-the-service-oriented-solution"></a><span data-ttu-id="61cc9-227">サービス指向ソリューションを展開するには</span><span class="sxs-lookup"><span data-stu-id="61cc9-227">To deploy the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="61cc9-228">コマンド プロンプトを開き、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-228">Open a command prompt and change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder.</span></span>  
  
2.  <span data-ttu-id="61cc9-229">変更、 **DeployStubBinding.cmd**ファイルで、"release"と"debug"と"development"のすべてのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="61cc9-229">Modify the **DeployStubBinding.cmd** file by replacing all the instances of “debug” and “development” with “release”.</span></span>  
  
3.  <span data-ttu-id="61cc9-230">コマンド プロンプトを開き、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-230">Open a command prompt and change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder.</span></span> <span data-ttu-id="61cc9-231">次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-231">Type the following command, and then press ENTER:</span></span>  
  
    -   `DeployStubBinding.cmd`  
  
4.  <span data-ttu-id="61cc9-232">コマンド プロンプトで、次のコマンドを実行し、スタブ バージョンのオーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="61cc9-232">At the command prompt, run the following command to start the orchestrations for the stub version</span></span>  
  
    -   `Startstub.vbs`  
  
## <a name="next-steps"></a><span data-ttu-id="61cc9-233">次の手順</span><span class="sxs-lookup"><span data-stu-id="61cc9-233">Next Steps</span></span>  
 <span data-ttu-id="61cc9-234">サービス指向ソリューションのスタブ バージョンがどのように動作するかをテストする[サービス指向ソリューションの実行方法](../core/how-to-run-the-service-oriented-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="61cc9-234">You test how the stub version of the service-oriented solution works in [How to Run the Service Oriented Solution](../core/how-to-run-the-service-oriented-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61cc9-235">参照</span><span class="sxs-lookup"><span data-stu-id="61cc9-235">See Also</span></span>  
 <span data-ttu-id="61cc9-236">[サービス指向ソリューションをインストールする前に](../core/before-installing-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="61cc9-236">[Before Installing the Service Oriented Solution](../core/before-installing-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="61cc9-237">[指向ソリューションのインライン バージョンおよびアダプター バージョンのサービスをインストールする方法](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="61cc9-237">[How to Install the Inline and Adapter Versions of the Service Oriented Solution](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="61cc9-238">サービス指向ソリューションに対する開発者のコンピューター設定</span><span class="sxs-lookup"><span data-stu-id="61cc9-238">Developer Machine Setup for the Service Oriented Solution</span></span>](../core/developer-machine-setup-for-the-service-oriented-solution.md)