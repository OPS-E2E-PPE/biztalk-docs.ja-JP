---
title: "指向ソリューションのインライン バージョンおよびアダプター バージョンのサービスをインストールする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificate services
- service solution tutorial, affiliat applications [SSO]
- service solution tutorial, adapter version
- service solution tutorial, Web services
- service solution tutorial, definition files [BAM]
- service solution tutorial, COM+ applications
- service solution tutorial, virtual directories
- service solution tutorial, testing connectivity
- TI components
- MQSeries queues, creating
- service solution tutorial, deploying
- service solution tutorial, MQSeries adapters
- service solution tutorial, mainframe CICS applications
- service solution tutorial, certificate services
- service solution tutorial, back-end systems
- service solution tutorial, MQSeries queues
- service solution tutorial, remote environments
- certificates, creating requests
- service solution tutorial, starting service
- service solution tutorial, TI components
- service solution tutorial, inline version
- CICS application
- service solution tutorial, installing
- service solution tutorial, deleting stub version
- service solution tutorial, certificates
ms.assetid: 6050cfe9-4e94-4a55-8b24-fbcc74d9e8f4
caps.latest.revision: "97"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb7de8939037f9e7647c62c1164e3c3de3ab378c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution"></a><span data-ttu-id="c6126-102">サービス指向ソリューションのインライン バージョンおよびアダプター バージョンをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="c6126-102">How to Install the Inline and Adapter Versions of the Service Oriented Solution</span></span>
<span data-ttu-id="c6126-103">次の手順では、サービス指向ソリューションのインライン バージョンおよびアダプタ バージョンをコンピュータにインストールするための準備を行う方法、およびコンピュータにソリューションをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c6126-103">The following steps describe how to prepare the computer for installing the inline and adapter versions of the service oriented solution, and how to install the solution on this computer.</span></span>  
  
-   [<span data-ttu-id="c6126-104">サービス指向ソリューションのアダプターとインライン バージョンをインストールするコンピューターを準備します</span><span class="sxs-lookup"><span data-stu-id="c6126-104">Prepare the computer for installing the adapter and inline versions of the Service Oriented Solution</span></span>](#step1)  
  
-   [<span data-ttu-id="c6126-105">サービス指向ソリューションのスタブ バージョンを削除します。</span><span class="sxs-lookup"><span data-stu-id="c6126-105">Remove the stub version of the Service Oriented Solution</span></span>](#step3)  
  
-   [<span data-ttu-id="c6126-106">アクセスするサービス指向ソリューションのバックエンド システムを準備します。</span><span class="sxs-lookup"><span data-stu-id="c6126-106">Prepare the back-end systems for the Service Oriented Solution to access</span></span>](#step5)  
  
-   [<span data-ttu-id="c6126-107">セキュリティで保護されたソケット レイヤー (SSL) の Web サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-107">Configure the Web server for Secure Socket Layers (SSL)</span></span>](#step7)  
  
-   [<span data-ttu-id="c6126-108">バックエンド システム用の Web サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-108">Create the Web services for the back-end systems</span></span>](#step9)  
  
-   [<span data-ttu-id="c6126-109">サービス指向ソリューションの TI コンポーネントを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-109">Create the TI component for the Service Oriented Solution</span></span>](#step11)  
  
-   [<span data-ttu-id="c6126-110">Web サービスのオーケストレーションの仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-110">Create the virtual directories for the orchestration Web services</span></span>](#step13)  
  
-   [<span data-ttu-id="c6126-111">ビルド サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="c6126-111">Build the Service Oriented Solution</span></span>](#step15)  
  
-   [<span data-ttu-id="c6126-112">SSO 関連アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-112">Create the SSO affiliate applications</span></span>](#step17)  
  
-   [<span data-ttu-id="c6126-113">サービス指向ソリューションの BAM 定義ファイルを配置します。</span><span class="sxs-lookup"><span data-stu-id="c6126-113">Deploy the BAM definition file for the Service Oriented Solution</span></span>](#step19)  
  
-   [<span data-ttu-id="c6126-114">配置サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="c6126-114">Deploy the Service Oriented Solution</span></span>](#step21)  
  
-   [<span data-ttu-id="c6126-115">メインフレームが利用できない場合は、スタブ Pending Transactions Web サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-115">Configure the stub Pending Transactions Web Services when a mainframe is not available</span></span>](#step23)  
  
-   [<span data-ttu-id="c6126-116">開始、サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="c6126-116">Start the Service Oriented Solution</span></span>](#step25)  
  
> [!NOTE]
>  <span data-ttu-id="c6126-117">サービス指向ソリューションはフォルダーにある\< *BizTalk Server のインストール フォルダー*> \SDK\Scenarios\SO です。</span><span class="sxs-lookup"><span data-stu-id="c6126-117">The service oriented solution is located in the folder \<*BizTalk Server Installation Folder*>\SDK\Scenarios\SO.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6126-118">このソリューションに対応するメインフレームがない場合、ポートのバインドを変更して、Pending Transactions のスタブ Web サービスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6126-118">If you don’t have a mainframe for the solution, you can modify the port binding to use the stub Web service for Pending Transactions.</span></span> <span data-ttu-id="c6126-119">メインフレームのトランザクションをエミュレートするため、Web サービスは、ローカルにトランザクションを生成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-119">The Web service generates transactions locally to emulate the mainframe transactions.</span></span>  
  
##  <span data-ttu-id="c6126-120"><a name="step1"></a>サービス指向ソリューションのアダプターとインライン バージョンをインストールするコンピューターを準備します</span><span class="sxs-lookup"><span data-stu-id="c6126-120"><a name="step1"></a> Prepare the computer for installing the adapter and inline versions of the Service Oriented Solution</span></span>  
  
#### <a name="to-prepare-the-computer-for-installing-the-adapter-and-inline-versions-of-the-service-oriented-solution"></a><span data-ttu-id="c6126-121">サービス指向ソリューションのアダプター バージョンおよびインライン バージョンをコンピューターにインストールするための準備を行うには</span><span class="sxs-lookup"><span data-stu-id="c6126-121">To prepare the computer for installing the adapter and inline versions of the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="c6126-122">Windows SharePoint Services をインストールした場合 (ルートを除外)、既定の Web サイトの Windows SharePoint Services 管理パスから次のようにします  をクリック**開始**、 をポイント**すべてのプログラム**、 をポイント。**管理ツール**、クリックして**SharePoint サーバーの全体管理**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-122">If you installed Windows SharePoint Services, exclude the (root) of the Default Web Site from Windows SharePoint Services Managed Paths as follows: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
    1.  <span data-ttu-id="c6126-123">**仮想サーバーの構成****仮想サーバーの設定を構成する**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-123">Under **Virtual Server Configuration**, select **Configure virtual server settings**.</span></span>  
  
    2.  <span data-ttu-id="c6126-124">**仮想サーバーのリスト**] ページで [**既定の Web サイト**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-124">On the **Virtual Server List** page, click **Default Web Site**.</span></span>  
  
    3.  <span data-ttu-id="c6126-125">**仮想サーバーの設定**] ページで [**管理パスの定義**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-125">On the **Virtual Server Settings** page, click **Define managed paths**.</span></span>  
  
    4.  <span data-ttu-id="c6126-126">**インクルード パス**のセクションで、**管理パスの定義** ページで、**ルート** をクリックし、**選択したパスの削除**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-126">In the **Included Paths** section of the **Defined Managed Path** page, select **Root** and then click **Remove selected paths**.</span></span>  
  
    5.  <span data-ttu-id="c6126-127">コマンド プロンプトで IISReset コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c6126-127">At a command prompt, perform an IISReset.</span></span>  
  
2.  <span data-ttu-id="c6126-128">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、 をクリックして**コンピューターの管理**コンソール、および追加し、ローカルの Administrators グループに BizTalk サービス アカウント。</span><span class="sxs-lookup"><span data-stu-id="c6126-128">Click **Start**, point to **All Programs**, point to **Administrative Tools**, click **Computer Management** console, and then add the BizTalk service account to the local Administrators group.</span></span>  
  
3.  <span data-ttu-id="c6126-129">コンピュータからログオフして、BizTalk サービス アカウントを使用してコンピュータにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c6126-129">Log off the computer, and then log on to the computer as the BizTalk service account.</span></span>  
  
4.  <span data-ttu-id="c6126-130">コマンド プロンプトで、次のコマンドを入力し、&lt;localizedText&gt;Enter&lt;/localizedText&gt; キーを押して、%BTSSolutionsPath% 環境変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="c6126-130">At a command prompt, type the following command, and then press ENTER to set the %BTSSolutionsPath% environment variable.</span></span> <span data-ttu-id="c6126-131">次に、コマンド プロンプトを終了します。</span><span class="sxs-lookup"><span data-stu-id="c6126-131">Then, exit the command prompt.</span></span>  
  
    -   <span data-ttu-id="c6126-132">setx BTSSolutionsPath [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"</span><span class="sxs-lookup"><span data-stu-id="c6126-132">setx BTSSolutionsPath [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios"</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c6126-133">64 ビット コンピューターを使用する場合は、「%ProgramFiles%」の代わりに「%ProgramFiles%(x86)」と入力してください。</span><span class="sxs-lookup"><span data-stu-id="c6126-133">If you are using a 64-bit computer, use %ProgramFiles(x86)% instead of %ProgramFiles%.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c6126-134">SETX コマンドの詳細については、Microsoft TechNet Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831)です。</span><span class="sxs-lookup"><span data-stu-id="c6126-134">For more information about the SETX command, see the Microsoft TechNet Web site at [http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831).</span></span>  
  
##  <span data-ttu-id="c6126-135"><a name="step3"></a>サービス指向ソリューションのスタブ バージョンを削除します。</span><span class="sxs-lookup"><span data-stu-id="c6126-135"><a name="step3"></a> Remove the stub version of the Service Oriented Solution</span></span>  
  
#### <a name="to-remove-the-stub-version-of-the-service-oriented-solution"></a><span data-ttu-id="c6126-136">サービス指向ソリューションのスタブ バージョンを削除するには</span><span class="sxs-lookup"><span data-stu-id="c6126-136">To remove the stub version of the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="c6126-137">開く、 **BizTalk Server 管理コンソール**次のように: をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-137">Open the **BizTalk Server Administration Console** as follows: Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="c6126-138">**BizTalk Server 管理コンソール**、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**を右クリックして**[btsscn.so.customerservice]**、クリックして**停止**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-138">In the **BizTalk Server Administration Console**, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, right-click **BTSScn.SO.CustomerService**, and then click **Stop**.</span></span> <span data-ttu-id="c6126-139">**アプリケーションの停止**ダイアログ ボックスで、**完全停止 - インスタンスを終了**、クリックして**停止**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-139">In the **Stop Application** dialog box, select **Full Stop - Terminate Instances**, and then click **Stop**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-140">インライン バージョンおよびアダプター バージョンをインストールするために、スタブ バージョンを削除する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c6126-140">You don't need to remove the stub version for installing the inline and adapter versions.</span></span> <span data-ttu-id="c6126-141">すべてのバージョンを一緒に配置する場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="c6126-141">If you want to put all the versions together, you should skip this step.</span></span>  
  
3.  <span data-ttu-id="c6126-142">コマンド プロンプトを開いて次のコマンドを入力し、&lt;localizedText&gt;Enter&lt;/localizedText&gt; キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c6126-142">Open a command prompt, type the following command, and then press ENTER.</span></span> <span data-ttu-id="c6126-143">このコマンドは、既定のスクリプト ホストを CScript.exe に変更します。</span><span class="sxs-lookup"><span data-stu-id="c6126-143">This command changes the default script host to CScript.exe:</span></span>  
  
    -   `cscript /H:CScript`  
  
4.  <span data-ttu-id="c6126-144">コマンド プロンプトで、現在のディレクトリを %BTSSolutonsPath%\SO\BTSSoln\Scripts フォルダーに変更し、次のコマンドを入力して &lt;localizedText&gt;Enter&lt;/localizedText&gt; キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c6126-144">At the command prompt, change the current directory to %BTSSolutonsPath%\SO\BTSSoln\Scripts folder, type the following command, and then press ENTER:</span></span>  
  
    -   `UnEnlistStub.vbs`  
  
5.  <span data-ttu-id="c6126-145">コマンド プロンプトで次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c6126-145">At the command prompt, type the following command, and then press ENTER:</span></span>  
  
    -   `UndeployStub.vbs`  
  
6.  <span data-ttu-id="c6126-146">コマンド プロンプトで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c6126-146">At the command prompt, run the following command</span></span>  
  
     <span data-ttu-id="c6126-147">SET PATH=%PATH%;[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking"</span><span class="sxs-lookup"><span data-stu-id="c6126-147">SET PATH=%PATH%;[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking"</span></span>  
  
     <span data-ttu-id="c6126-148">これで、BAM ユーティリティを参照するためのパスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="c6126-148">This sets the path to find the BAM utilities.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-149">64 ビット コンピューターを使用している場合は、入力`%ProgramFiles(x86)%`の代わりに`%ProgramFiles%`です。</span><span class="sxs-lookup"><span data-stu-id="c6126-149">If you are using a 64-bit computer, type `%ProgramFiles(x86)%` instead of `%ProgramFiles%`.</span></span>  
  
7.  <span data-ttu-id="c6126-150">コマンド プロンプトで、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\BAM フォルダーに変更し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c6126-150">At the command prompt, change the directory to %BTSSolutionsPath%\SO\BTSSoln\BAM, and then run the following command:</span></span>  
  
    -   `bm remove-all -DefinitionFile:ServiceLevelTracking.xml`  
  
8.  <span data-ttu-id="c6126-151">コマンド プロンプトでのディレクトリに移動\<*エンタープライズ シングル サインオンをインストール ディレクトリ*>、および次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c6126-151">At the command prompt, change the directory to \<*Enterprise Single Sign-On Install Directory*>, and then run the following command:</span></span>  
  
    -   `ssomanage -tickets no no`  
  
9. <span data-ttu-id="c6126-152">コマンド プロンプトで次のコマンドを実行し、WoodgroveBank.CustomerService SSO 関連アプリケーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="c6126-152">At the command prompt, run the following command to delete the WoodgroveBank.CustomerService SSO Affiliated application:</span></span>  
  
    -   `ssomanage -deleteapp WoodgroveBank.CustomerService`  
  
10. <span data-ttu-id="c6126-153">コマンド プロンプトで次のコマンドを実行し、スタブ バージョンで使用される Web サイトを削除します。</span><span class="sxs-lookup"><span data-stu-id="c6126-153">At the command prompt, run the following commands to delete the Web sites used by the stub version.</span></span> <span data-ttu-id="c6126-154">Iisvdir.vbs の詳細については、Microsoft TechNet Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=67830](http://go.microsoft.com/fwlink/?LinkId=67830)です。</span><span class="sxs-lookup"><span data-stu-id="c6126-154">For more information about iisvdir.vbs, see the Microsoft TechNet Web site at [http://go.microsoft.com/fwlink/?LinkId=67830](http://go.microsoft.com/fwlink/?LinkId=67830).</span></span>  
  
    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub`  
  
    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP`  
  
    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions`  
  
    -   `iisvdir /delete W3SVC/1/ROOT/Microsoft.Samples.BizTalk.WoodgroveBank.StubPaymentTracker`  
  
11. <span data-ttu-id="c6126-155">次のようにインターネット インフォメーション サービス (IIS) マネージャーを開始: をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**をクリックして**インターネット インフォメーション サービス (IIS) マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-155">Start Internet Information Services (IIS) Manager as follows: Click **Start**, point to **All Programs**, point to **Administration Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
    -   <span data-ttu-id="c6126-156">展開、**アプリケーション プール**の以前の Web アプリケーションを作成したアプリケーション プールを右クリックしをクリックして**削除**、順にクリック**[ok]**確認ダイアログでダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="c6126-156">Expand the **Application Pools**, right-click the application pool you crated for the previous Web applications, click **Delete**, and then click **OK** in the confirmation dialog box.</span></span>  
  
12. <span data-ttu-id="c6126-157">をクリックして**開始**、 をポイント**コントロール パネルの** 、 をクリックして**プログラム追加と削除**、IBM WebSphere MQ Client for Windows をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="c6126-157">Click **Start**, point to **Control Panel**, click **Add or Remove Programs**, and then uninstall the IBM WebSphere MQ Client for Windows.</span></span>  
  
13. <span data-ttu-id="c6126-158">開始**Visual Studio コマンド プロンプト**し、スタブ バージョン用にインストールした amqmdnet.dll を削除するのには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c6126-158">Start **Visual Studio Command Prompt** and then run the following command to delete the amqmdnet.dll you installed for the stub version.</span></span>  
  
    -   `gacutil /u amqmdnet`  
  
##  <span data-ttu-id="c6126-159"><a name="step5"></a>アクセスするサービス指向ソリューションのバックエンド システムを準備します。</span><span class="sxs-lookup"><span data-stu-id="c6126-159"><a name="step5"></a> Prepare the back-end systems for the Service Oriented Solution to access</span></span>  
  
#### <a name="to-install-the-required-applications-for-the-back-end-systems-for-the-service-oriented-solution-to-access"></a><span data-ttu-id="c6126-160">サービス指向ソリューションがアクセスするバックエンド システムに必要なアプリケーションをインストールするには</span><span class="sxs-lookup"><span data-stu-id="c6126-160">To install the required applications for the back-end systems for the Service Oriented Solution to access</span></span>  
  
1.  <span data-ttu-id="c6126-161">ローカル コンピューターに IBM WebSphere MQ for Windows のバージョン 5.3 サーバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c6126-161">Install IBM WebSphere MQ for Windows Version 5.3 Server on the local computer.</span></span>  
  
    1.  <span data-ttu-id="c6126-162">すべての設定を既定のままにします。</span><span class="sxs-lookup"><span data-stu-id="c6126-162">Keep all the default settings.</span></span> <span data-ttu-id="c6126-163">セットアップ、**既定の構成**の最後に、 **WebSphere MQ ウィザードの準備**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-163">Set up the **Default Configuration** at the end of the **Prepare WebSphere MQ Wizard**.</span></span> <span data-ttu-id="c6126-164">キュー マネージャーは、qm _ という名前\<*コンピューター名*>。</span><span class="sxs-lookup"><span data-stu-id="c6126-164">The queue manager is named as QM_\<*your computer name*>.</span></span>  
  
    2.  <span data-ttu-id="c6126-165">フィックス パック 10 (CSD10) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c6126-165">Install the Fix Pack 10 (CSD10).</span></span> <span data-ttu-id="c6126-166">すべての設定を既定のままにします。</span><span class="sxs-lookup"><span data-stu-id="c6126-166">Keep all the default settings.</span></span>  
  
2.  <span data-ttu-id="c6126-167">MQSeries エージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c6126-167">Install the MQSeries Agent.</span></span>  
  
    1.  <span data-ttu-id="c6126-168">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] セットアップ プログラムを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="c6126-168">Rerun the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] setup program.</span></span>  
  
    2.  <span data-ttu-id="c6126-169">**プログラムのメンテナンス**] ページで、[**変更**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-169">On the **Program Maintenance** page, select **Modify**, and then click **Next**.</span></span>  
  
    3.  <span data-ttu-id="c6126-170">**コンポーネントのインストール** ページで、展開、**追加のソフトウェア**ノードをクリックして**MQSeries エージェント**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-170">On the **Component Installation** page, expand the **Additional Software** node, and then select **MQSeries Agent**.</span></span>  
  
    4.  <span data-ttu-id="c6126-171">**完了**ことを確認] ページで、 **[BizTalk MQSeries エージェント構成ウィザードの**が選択されていません。</span><span class="sxs-lookup"><span data-stu-id="c6126-171">On the **Completion** page, make sure that **Launch BizTalk MQSeries Agent Configuration Wizard** is not selected.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-172">**MQSeries エージェント**for Windows がインストールされている チェック ボックスは、IBM WebSphere MQ の後にのみアクティブ化されています。</span><span class="sxs-lookup"><span data-stu-id="c6126-172">The **MQSeries Agent** check box is activated only after the IBM WebSphere MQ for Windows is installed.</span></span>  
  
3.  <span data-ttu-id="c6126-173">開く、 **Visual Studio コマンド プロンプト**、ディレクトリに移動、 \< *IBM MQSeries インストール ディレクトリ*> \bin フォルダーに、その後、次のコマンド。</span><span class="sxs-lookup"><span data-stu-id="c6126-173">Open a **Visual Studio Command Prompt**, change the directory to the \<*IBM MQSeries Installation Directory*>\bin folder, and then run the following command:</span></span>  
  
    -   `gacutil /i amqmdnet.dll`  
  
4.  <span data-ttu-id="c6126-174">メインフレームにアクセスするために Microsoft Host Integration Server 2004 をインストールする場合、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c6126-174">Install Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] if you want to install Microsoft Host Integration Server 2004 to access the mainframe.</span></span> <span data-ttu-id="c6126-175">セットアップ プログラムでの**オプション**] ページで、[ **Visual c# .NET**、し、その他のコンポーネントのチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="c6126-175">In the setup program, on the **Options** page, select **Visual C# .NET**, and then clear other components checkboxes.</span></span> <span data-ttu-id="c6126-176">もその他のコンポーネントをインストールする必要はありません、 **Visual c# .NET**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-176">You don't need to install other components than the **Visual C# .NET**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-177">Host Integration Server 2004 の TI デザイナーを使用する場合、[!INCLUDE[btsVStudioNet2003](../includes/btsvstudionet2003-md.md)] が必要です。</span><span class="sxs-lookup"><span data-stu-id="c6126-177">The TI Designer in Host Integration Server 2004 requires [!INCLUDE[btsVStudioNet2003](../includes/btsvstudionet2003-md.md)].</span></span>  
  
5.  <span data-ttu-id="c6126-178">インストールし、メインフレームにアクセスした場合は、Microsoft Host Integration Server 2004 を構成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-178">Install and configure Microsoft Host Integration Server 2004 if you have a mainframe to be accessed.</span></span> <span data-ttu-id="c6126-179">すべての設定を既定のままにします。</span><span class="sxs-lookup"><span data-stu-id="c6126-179">Keep all the default settings.</span></span>  
  
#### <a name="to-create-the-mqseries-queues"></a><span data-ttu-id="c6126-180">MQSeries キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="c6126-180">To create the MQSeries queues</span></span>  
  
1.  <span data-ttu-id="c6126-181">WebSphere MQ エクスプ ローラーを開き、展開**キュー マネージャー**、キューを作成するキュー マネージャーを展開します。</span><span class="sxs-lookup"><span data-stu-id="c6126-181">Open the WebSphere MQ Explorer, expand **Queue Managers**, and then expand the queue manager in which you want to create the queues.</span></span> <span data-ttu-id="c6126-182">通常、キュー マネージャーの名前 qm _ として\<*コンピューター名*>。</span><span class="sxs-lookup"><span data-stu-id="c6126-182">Typically, a queue manager is named as QM_\<*your computer name*>.</span></span>  
  
2.  <span data-ttu-id="c6126-183">WebSphere MQ エクスプ ローラーを右クリックして**キュー**、 をポイント**新規**をクリックして**ローカル キュー**のアダプター バージョン用の次のローカル キューを作成し、解決方法:</span><span class="sxs-lookup"><span data-stu-id="c6126-183">In the WebSphere MQ Explorer, right-click **Queues**, point to **New**, click **Local Queue**, and then create the following local queues for the adapter version of the solution:</span></span>  
  
    -   <span data-ttu-id="c6126-184">AdapterSOAInputQueue</span><span class="sxs-lookup"><span data-stu-id="c6126-184">AdapterSOAInputQueue</span></span>  
  
    -   <span data-ttu-id="c6126-185">AdapterSOAOutputQueue</span><span class="sxs-lookup"><span data-stu-id="c6126-185">AdapterSOAOutputQueue</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-186">キューでは MQSeries クラスターを共有できますが、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="c6126-186">The queues can share an MQSeries cluster, but they are not required to do so.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-187">MQSeries キュー マネージャーの名前およびキューの名前では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="c6126-187">MQSeries queue manager names and queue names are case sensitive.</span></span>  
  
3.  <span data-ttu-id="c6126-188">前のステップを繰り返して、インライン バージョン用の次のローカル キューを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-188">Repeat the previous step to create the following local queues for the inline version:</span></span>  
  
    -   <span data-ttu-id="c6126-189">InlineSOAOutputQueue</span><span class="sxs-lookup"><span data-stu-id="c6126-189">InlineSOAOutputQueue</span></span>  
  
    -   <span data-ttu-id="c6126-190">InlineSOAInputQueue</span><span class="sxs-lookup"><span data-stu-id="c6126-190">InlineSOAInputQueue</span></span>  
  
4.  <span data-ttu-id="c6126-191">前のステップを繰り返して、Payment Tracker シミュレーター用の次のローカル キューを作成します </span><span class="sxs-lookup"><span data-stu-id="c6126-191">Repeat the previous step to create the following local queues for the Payment Tracker simulator.</span></span> <span data-ttu-id="c6126-192">(Payment Tracker シミュレーターはアダプター バージョンおよびインライン バージョンの両方で使用されます)。</span><span class="sxs-lookup"><span data-stu-id="c6126-192">(The Payment Tracker simulator is used in both the adapter and inline versions):</span></span>  
  
    -   <span data-ttu-id="c6126-193">LastPaymentsInputQueue</span><span class="sxs-lookup"><span data-stu-id="c6126-193">LastPaymentsInputQueue</span></span>  
  
    -   <span data-ttu-id="c6126-194">LastPaymentsOutputQueue</span><span class="sxs-lookup"><span data-stu-id="c6126-194">LastPaymentsOutputQueue</span></span>  
  
#### <a name="to-complete-configuration-of-the-mqseries-adapter"></a><span data-ttu-id="c6126-195">MQSeries アダプターの構成を完了するには</span><span class="sxs-lookup"><span data-stu-id="c6126-195">To complete configuration of the MQSeries adapter</span></span>  
  
1.  <span data-ttu-id="c6126-196">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk MQSeries エージェント構成ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-196">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk MQSeries Agent Configuration Wizard**.</span></span>  
  
2.  <span data-ttu-id="c6126-197">**ようこそ** ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-197">On the **Welcome** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="c6126-198">**アプリケーション Id** ] ページで、[**このユーザー**、ユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="c6126-198">On the **Application Identity** page, select **This User**, and then enter the user name and password.</span></span> <span data-ttu-id="c6126-199">MQSeries エージェントの COM+ アプリケーションは、このユーザー アカウントで実行されます。</span><span class="sxs-lookup"><span data-stu-id="c6126-199">The COM+ application for the MQSeries Agent will run under this user account.</span></span> <span data-ttu-id="c6126-200">このチュートリアルでは、BizTalk サービスが使用するユーザー アカウントとして同じものを使用します。</span><span class="sxs-lookup"><span data-stu-id="c6126-200">For this walkthrough, use the same user account that the BizTalk service is using.</span></span> <span data-ttu-id="c6126-201">ない場合は、ユーザー アカウントに、MQSeries アダプターをホストする BizTalk サービスを追加する必要があります、 **CreatorOwner** COM + アプリケーションの役割です。</span><span class="sxs-lookup"><span data-stu-id="c6126-201">If it is not, the user accounts for BizTalk services hosting the MQSeries Adapter must be added to the **CreatorOwner** role of the COM+ application.</span></span>  
  
4.  <span data-ttu-id="c6126-202">をクリックして**はい**上、 **MQSConfigWiz**ダイアログ ボックスで、前の手順で入力したユーザー アカウントが管理者特権を持っている場合。</span><span class="sxs-lookup"><span data-stu-id="c6126-202">Click **Yes** on the **MQSConfigWiz** dialog box, if prompted that the user account that you entered in the previous step has the administrative privilege.</span></span>  
  
5.  <span data-ttu-id="c6126-203">**ロールの名前**] ページで [**次**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-203">On the **Name of Role** page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="c6126-204">**MQSAgent COM + アプリケーションを作成する** ページで、をクリックして**次へ**、順にクリック**完了**上、**完了**ページ。</span><span class="sxs-lookup"><span data-stu-id="c6126-204">On the **Creating the MQSAgent COM+ Application** page, click **Next**, and then click **Finish** on the **Completion** page.</span></span>  
  
#### <a name="to-configure-the-mainframe-cics-application"></a><span data-ttu-id="c6126-205">メインフレームの CICS アプリケーションを構成するには</span><span class="sxs-lookup"><span data-stu-id="c6126-205">To configure the mainframe CICS application</span></span>  
  
1.  <span data-ttu-id="c6126-206">メモ帳を使用して %BTSSolutionsPath%\SO\MFAccess\HISTIComponent フォルダーの bizcbl.txt とその "コピー ブック" (MainFrameProgramVTCS2Description.txt) を開き、内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="c6126-206">Using Notepad, open the bizcbl.txt and its "copy book" (MainFrameProgramVTCS2Description.txt) in the %BTSSolutionsPath%\SO\MFAccess\HISTIComponent folder, and then review the contents.</span></span>  
  
    -   <span data-ttu-id="c6126-207">bizcbl.txt には、アカウント番号入力からランダム アカウント ステートメントを返す COBOL プロシージャが記述されています。</span><span class="sxs-lookup"><span data-stu-id="c6126-207">Bizcbl.txt includes the COBOL procedure returning the randomized account statements from account number input.</span></span>  
  
    -   <span data-ttu-id="c6126-208">MainFrameProgramVTCS2Descriptoin.txt には、入出力データ情報を記述する COMMAREA が記述されています。</span><span class="sxs-lookup"><span data-stu-id="c6126-208">MainFrameProgramVTCS2Descriptoin.txt contains COMMAREA which describes the input and output data information.</span></span> <span data-ttu-id="c6126-209">COMMAREA は、呼び出し元プログラムと呼び出し先プログラムの間でデータをやり取りするために使用する連続したメモリ ブロックです。</span><span class="sxs-lookup"><span data-stu-id="c6126-209">COMMAREA is a block of contiguous memory used to pass data back and forth between called and calling programs.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-210">コピー ブックを使用してトランザクション インテグレーター (TI) メタデータ ファイルを生成し、[!INCLUDE[vs2010](../includes/vs2010-md.md)] で TI デザイナー プラグインを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c6126-210">You can also use the copy book to generate the Transaction Integrator (TI) metadata file using [!INCLUDE[vs2010](../includes/vs2010-md.md)] with the TI Designer plug-in.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-211">以降のステップは正常な配置を行うために非常に重要な操作ですが、一般的には BizTalk Server 開発者は行いません。</span><span class="sxs-lookup"><span data-stu-id="c6126-211">Although the following steps are crucial to the successful deployment, they are not usually performed by the BizTalk Server developer.</span></span> <span data-ttu-id="c6126-212">メインフレームの担当者に依頼して、メインフレーム環境を適切に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6126-212">You must rely on the mainframe personnel to properly configure the mainframe environment.</span></span> <span data-ttu-id="c6126-213">このチュートリアルで必要なソフトウェアは、一般的にほとんどのメインフレーム環境にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="c6126-213">The software required for this walkthrough is usually installed in the most mainframe environments.</span></span> <span data-ttu-id="c6126-214">最小のメインフレーム オペレーティング システムの環境の詳細については、Host Integration Server のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6126-214">For more information about the minimum mainframe operating system environment, see the Host Integration Server documentation.</span></span>  
  
2.  <span data-ttu-id="c6126-215">FTP などを使用して、ホストに COBOL コードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="c6126-215">Copy the COBOL code to the host by method like FTP.</span></span>  
  
3.  <span data-ttu-id="c6126-216">COBOL コードとコピー ブックをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="c6126-216">Compile the COBOL code and copy book.</span></span> <span data-ttu-id="c6126-217">次のコードは、COBOL コンパイラ用のジョブ制御言語 (JCL) のサンプルです。</span><span class="sxs-lookup"><span data-stu-id="c6126-217">The following code shows a sample of Job Control Language (JCL) for the COBOL compiler.</span></span>  
  
    ```  
    //COB      EXEC PGM=IGYCRCTL,  
    //            PARM=&COBPARM,  
    //            REGION=&REG  
    //STEPLIB  DD DSN=&COMPINDX..SIGYCOMP,DISP=SHR  
    //SYSLIB   DD DSN=&INDEX..SDFHCOB,DISP=SHR  
    //         DD DSN=&INDEX..SDFHMAC,DISP=SHR  
    //         DD DSN=&HLQ..&COMP..COBCOPY,DISP=SHR  
    //SYSPRINT DD SYSOUT=&OUTC  
    //*SYSPRINT DD DSN=&&INPUT,DISP=(,PASS),UNIT=SYSDA,  
    //*         SPACE=(TRK,(100,50)),  
    //*         DCB=(DSORG=PS,LRECL=121,BLKSIZE=2420,RECFM=FBA)  
    //SYSIN    DD DSN=&&SYSCIN,DISP=(OLD,DELETE)  
    //SYSLIN   DD DSN=&&LOADSET,  
    //            DISP=(MOD,PASS),  
    //            UNIT=&WORK,  
    //            SPACE=(80,(250,100))  
    //SYSUT1   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT2   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT3   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT4   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT5   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT6   DD UNIT=&WORK,SPACE=(460,(350,150))  
    //SYSUT7   DD UNIT=&WORK,SPACE=(460,(350,150))  
    ```  
  
4.  <span data-ttu-id="c6126-218">コンパイルしたソースをリンク編集して、実行可能ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-218">Link edit the compiled source to create the executable.</span></span> <span data-ttu-id="c6126-219">次のコードは、COBOL リンク編集用の JCL のサンプルです。</span><span class="sxs-lookup"><span data-stu-id="c6126-219">The following code shows a sample of JCL for COBOL link edit.</span></span>  
  
    ```  
    //LKED     EXEC PGM=IEWL,REGION=&REG,  
    //            PARM=&LNKPARM,COND=(5,LT,COB)  
    //SYSLIB   DD DSN=&INDEX..SDFHLOAD,DISP=SHR  
    //         DD DSN=CEE.SCEELKED,DISP=SHR  
    //         DD DSN=&TCPINDX..SEZATCP,DISP=SHR  
    //SYSLMOD  DD DSN=&LMINDX..&COMP..LOADLIB,DISP=SHR  
    //SYSUT1   DD UNIT=&WORK,  
    //            DCB=BLKSIZE=1024,  
    //            SPACE=(1024,(200,20))  
    //SYSPRINT DD SYSOUT=&OUTC  
    //SYSLIN   DD DSN=&&LOADSET,DISP=(OLD,DELETE)  
    //         DD DSN=&&COPYLINK,DISP=(OLD,DELETE)  
    ```  
  
5.  <span data-ttu-id="c6126-220">CICS メインフレーム アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-220">Configure the CICS mainframe application.</span></span>  
  
    -   <span data-ttu-id="c6126-221">このステップでは、メインフレーム システム プログラマまたは CICS 開発者が TCPIPSERVICE、セッション、接続、トランザクション、およびプログラム リソース定義をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6126-221">In this step, the mainframe systems programmer or CICS developer must install TCPIPSERVICE, Session, Connection, Transaction, and Program resource definitions.</span></span>  
  
    -   <span data-ttu-id="c6126-222">メインフレーム管理者に、IP アドレス、ポート番号、およびアクセス可能なプログラムへのリンク名を問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="c6126-222">You should consult with mainframe administrators to get an IP address, port number, and a Link to Program name that you can access.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c6126-223">このチュートリアルは、メインフレームで CICS アプリケーションを使用し、トランザクション用のプログラミング モデルが TCP/IP (Enhanced Listener Mode (ELM) リンク) であることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c6126-223">This walkthrough assumes that the mainframe uses a CICS application server and that the programming model for the transaction is TCP/IP (Enhanced Listener Mode (ELM) Link).</span></span>  
  
##  <span data-ttu-id="c6126-224"><a name="step7"></a>セキュリティで保護されたソケット レイヤー (SSL) の Web サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-224"><a name="step7"></a> Configure the Web server for Secure Socket Layers (SSL)</span></span>  
  
#### <a name="to-install-certificate-services"></a><span data-ttu-id="c6126-225">証明書サービスをインストールするには</span><span class="sxs-lookup"><span data-stu-id="c6126-225">To install Certificate Services</span></span>  
  
1.  <span data-ttu-id="c6126-226">をクリックして**開始**、] をポイント**コントロール パネルの [**、順にクリック**プログラム追加と削除**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-226">Click **Start**, point to **Control Panel**, and then click **Add or Remove Programs**.</span></span>  
  
2.  <span data-ttu-id="c6126-227">**プログラム追加と削除**ダイアログ ボックスで、をクリックして**Windows コンポーネントの追加/削除**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-227">In the **Add or Remove Programs** dialog box, click **Add/Remove Windows Components**.</span></span>  
  
3.  <span data-ttu-id="c6126-228">**Windows コンポーネント ウィザード**を選択、**証明書サービス**、 をクリックして**次へ**、しに従って、画面に表示されるインストールを完了する指示します。</span><span class="sxs-lookup"><span data-stu-id="c6126-228">In the **Windows Components Wizard**, select the **Certificate Services**, click **Next**, and then follow the on-screen instructions to complete the installation.</span></span>  
  
#### <a name="to-create-a-certificate-request"></a><span data-ttu-id="c6126-229">証明書要求を作成するには</span><span class="sxs-lookup"><span data-stu-id="c6126-229">To create a certificate request</span></span>  
  
1.  <span data-ttu-id="c6126-230">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Web サイト**を右クリックし、**既定の Web サイト**をクリックして**プロパティ**、をクリックして、**ディレクトリ セキュリティ** タブをクリックして**サーバー証明書**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-230">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, click **Properties**, click the **Directory Security** tab, and then click **Server Certificate**.</span></span>  
  
2.  <span data-ttu-id="c6126-231">**へようこそ**のページ、 **Web サーバー証明書ウィザード**、 をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-231">On the **Welcome** page of the **Web Server Certificate Wizard**, click **Next**.</span></span>  
  
3.  <span data-ttu-id="c6126-232">**サービス証明書**] ページで、[**新しい証明書を作成**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-232">On the **Service Certificate** page, select **Create a new certificate**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="c6126-233">**証明書の要求** ページで、をクリックして**ここで、要求を準備するが、後で送信**、クリックして**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-233">On the **Delayed or Immediate Request** page, click **Prepare the request now, but send it later**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="c6126-234">**名とセキュリティ設定** ページで、すべての設定の既定では、保持して、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-234">On the **Name and Security Settings** page, keep all the default settings, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="c6126-235">**組織情報**ページで、会社の組織と組織単位名を入力し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-235">On the **Organization Information** page, type your company's organization and organizational unit names, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="c6126-236">**サイトの一般名** ページで、コンピューター名を入力、**共通名**ボックスし、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-236">On the **Your Site's Common Name** page, type your computer name in the **Common name** box, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="c6126-237">**地理情報** ページで、地理的な情報を入力してをクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-237">On the **Geographical Information** page, fill out your geographical information, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="c6126-238">**証明書要求ファイル名** ページで、入力`c:\certreq.txt`で、**ファイル名**ボックスし、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-238">On the **Certificate Request File Name** page, type `c:\certreq.txt` in the **File name** box, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="c6126-239">**要求ファイルの概要** ページで、をクリックして**次へ**、順にクリック**完了**上、**完了**ページ。</span><span class="sxs-lookup"><span data-stu-id="c6126-239">On the **Request File Summary** page, click **Next**, and then click **Finish** on the **Completion** page.</span></span>  
  
#### <a name="to-submit-the-certificate-request-to-the-certification-authority"></a><span data-ttu-id="c6126-240">証明機関に証明書の要求を送信するには</span><span class="sxs-lookup"><span data-stu-id="c6126-240">To submit the certificate request to the Certification Authority</span></span>  
  
1.  <span data-ttu-id="c6126-241">Internet Explorer で、[アドレス] ボックスで、次のように入力します。 `http://localhost/certsrvt`、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c6126-241">In Internet Explorer, in the Address box, type `http://localhost/certsrvt`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="c6126-242">**へようこそ**  ページで、をクリックして**証明書を要求**、クリックして**高度な証明書の要求**上、**証明書を要求**ページです。</span><span class="sxs-lookup"><span data-stu-id="c6126-242">On the **Welcome** page, click **Request a Certificate**, and then click **Advanced certificate request** on the **Request a Certificate** page.</span></span>  
  
3.  <span data-ttu-id="c6126-243">**証明書の要求の高度な**] ページで [ **PKCS #10 ファイルまたは base64 でエンコードされた PKCS #7 ファイルを使用して更新の要求にエンコードされた base64 を使用して、証明書要求を送信**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-243">On the **Advanced Certificate Request** page, click **Submit a certificate request using a base64 encoded PKCS #10 file or a renewal request using a base64 encoded PKCS #7 file**.</span></span>  
  
4.  <span data-ttu-id="c6126-244">"証明書の要求を作成するには"貼り付けますの手順で作成した c:\certreq.txt からすべてのテキストをコピー、**保存されている要求**ボックスに、**証明書の要求または更新の要求を送信**クリックして、ページ、**送信**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-244">Copy all the text from the c:\certreq.txt that you created in the procedure "To create a certificate request", paste it to the **Saved Request** box on the **Submit a Certificate Request or Renewal Request** page, and then click **Submit**.</span></span>  
  
#### <a name="to-issue-a-certificate-using-certification-authority-management-tool"></a><span data-ttu-id="c6126-245">証明機関管理ツールを使用して証明書を発行するには</span><span class="sxs-lookup"><span data-stu-id="c6126-245">To issue a certificate using Certification Authority management tool</span></span>  
  
1.  <span data-ttu-id="c6126-246">をクリックして**開始**、 をポイント**管理ツール**、順にクリック**証明機関**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-246">Click **Start**, point to **Administrative Tools**, and then click **Certification Authority**.</span></span>  
  
2.  <span data-ttu-id="c6126-247">**証明機関**コンソールで、証明機関の名前を展開し、展開、**保留中の要求**、前の手順では、ポイントに送信した証明書の要求を右クリックして**すべてのタスク**、クリックして**問題**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-247">In the **Certification Authority** console, expand your certification authority's name, expand the **Pending Request**, right-click the certificate request that you submitted in the previous step, point to **All Tasks**, and then click **Issue**.</span></span>  
  
3.  <span data-ttu-id="c6126-248">閉じる、**証明機関**コンソールです。</span><span class="sxs-lookup"><span data-stu-id="c6126-248">Close the **Certification Authority** console.</span></span>  
  
#### <a name="to-download-the-certificate-to-the-web-server"></a><span data-ttu-id="c6126-249">証明書を Web サーバーにダウンロードするには</span><span class="sxs-lookup"><span data-stu-id="c6126-249">To download the certificate to the Web server</span></span>  
  
1.  <span data-ttu-id="c6126-250">Internet Explorer で、[アドレス] ボックスで、次のように入力します。 `http://localhost/certsrvt`、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c6126-250">In Internet Explorer, in the Address box, type `http://localhost/certsrvt`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="c6126-251">**ようこそ** ページで、をクリックして**保留中の証明書の要求の状態を表示**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-251">On the **Welcome** page, click **View the status of a pending certificate request**.</span></span>  
  
3.  <span data-ttu-id="c6126-252">**保留中の証明書要求の状態を表示** ページで、証明書をクリックして**要求**証明書の要求を作成するには」の手順で作成しました。</span><span class="sxs-lookup"><span data-stu-id="c6126-252">On the **View the Status of a Pending Certificate Request** page, click the certificate **request** that you created in the procedure "To create a certificate request".</span></span>  
  
4.  <span data-ttu-id="c6126-253">**証明書は発行** ページでのエンコード スキームのいずれかを選択してをクリックして**証明書のダウンロード**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-253">On the **Certificate Issued** page, select either of the encoding schemes, and then click **Download certificate**.</span></span>  
  
5.  <span data-ttu-id="c6126-254">**セキュリティ警告**ダイアログ ボックスで、をクリックして**保存**、し、証明書を c:\certnew.cer として保存します。</span><span class="sxs-lookup"><span data-stu-id="c6126-254">On the **Security Warning** dialog box, click **Save**, and then save the certificate as c:\certnew.cer.</span></span>  
  
#### <a name="to-install-the-certificate-to-the-web-server"></a><span data-ttu-id="c6126-255">Web サーバーに証明書をインストールするには</span><span class="sxs-lookup"><span data-stu-id="c6126-255">To install the certificate to the Web server</span></span>  
  
1.  <span data-ttu-id="c6126-256">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**を右クリックし、**既定の Web サイト**証明書の要求を作成するし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-256">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site** for which you created the certificate request, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="c6126-257">**プロパティ**ダイアログ ボックスで、をクリックして、**ディレクトリ セキュリティ** タブをクリックして**サーバー証明書**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-257">On the **Properties** dialog box, click the **Directory Security** tab, and then click **Server Certificate**.</span></span>  
  
3.  <span data-ttu-id="c6126-258">**へようこそ**のページ、 **Web サーバー証明書ウィザード**、 をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-258">On the **Welcome** page of the **Web Server Certificate Wizard**, click **Next**.</span></span>  
  
4.  <span data-ttu-id="c6126-259">**保留中の証明書の要求**] ページで、[**保留中の要求を処理し、証明書をインストール**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-259">On the **Pending Certificate Request** page, select **Process the pending request and install the certificate**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="c6126-260">**保留中の要求を処理** ページで、入力`c:\certnew.cer`で、**パスとファイル名**テキスト ボックス、およびクリック**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-260">On the **Process a Pending Request** page, type `c:\certnew.cer` in the **Path and file name** text box, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="c6126-261">をクリックして**次へ**上、 **SSL ポート** ページで、をクリックして**次へ**上、**証明書の概要** ページで、をクリックして**を完了**上、**確認**ページ。</span><span class="sxs-lookup"><span data-stu-id="c6126-261">Click **Next** on the **SSL Port** page, click **Next** on the **Certificate Summery** page, and then click **Finish** on the **Confirmation** page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-262">このチュートリアルでは、証明書サービスと Web サーバーの両方を同じコンピューターにインストールするため、ローカル コンピューターの信頼されたルート証明機関のストアにサーバー証明書をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c6126-262">In this walkthrough you don't need to install the server certificate to the Trusted Root Certification Authorities store on the local computer because both Certificate Services and Web server are installed on the same computer.</span></span>  
  
##  <span data-ttu-id="c6126-263"><a name="step9"></a>バックエンド システム用の Web サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-263"><a name="step9"></a> Create the Web services for the back-end systems</span></span>  
  
#### <a name="to-create-a-new-iis-application-pool-for-the-pending-transaction-web-services"></a><span data-ttu-id="c6126-264">Pending Transaction Web サービス用に新しいアプリケーション プールを作成するには</span><span class="sxs-lookup"><span data-stu-id="c6126-264">To create a new IIS application pool for the Pending Transaction Web services</span></span>  
  
1.  <span data-ttu-id="c6126-265">**インターネット インフォメーション サービス (IIS) マネージャー**を右クリックして**アプリケーション プール****新規**、し、 **のアプリケーションプール**.</span><span class="sxs-lookup"><span data-stu-id="c6126-265">In the **Internet Information Services (IIS) Manager**, right-click **Application Pools**, select **New**, and then select **Application Pool**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-266">サービス指向ソリューションでは、この Web サービスを使用してメインフレームにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c6126-266">The service oriented solution accesses the mainframe through this Web service.</span></span>  
  
2.  <span data-ttu-id="c6126-267">**新しいアプリケーション プールの追加** ダイアログ ボックスに、入力、**アプリケーション プール ID** (任意の値) をクリックし、 **ok**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-267">On the **Add New Application Pool** dialog box, enter the **Application pool ID** (any value), and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="c6126-268">**インターネット インフォメーション サービス (IIS) マネージャー**作成したアプリケーション プールを右クリックし、**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-268">In the **Internet Information Services (IIS) Manager**, right-click the application pool that you just created, and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="c6126-269">**プロパティ** ページで、をクリックして、 **Identity**  タブで **構成可能**、入力、**ユーザー名**と**パスワード**、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-269">On the **Properties** page, click the **Identity** tab, select **Configurable**, enter the **User name** and **Password**, and then click **OK**.</span></span> <span data-ttu-id="c6126-270">このチュートリアルでは、BizTalk サービスが使用するユーザー アカウントとして同じものを使用します。</span><span class="sxs-lookup"><span data-stu-id="c6126-270">For this walkthrough, use the same user account that the BizTalk service is using.</span></span>  
  
#### <a name="to-create-the-pendingtransactions-web-service-for-runtime"></a><span data-ttu-id="c6126-271">ランタイム用の PendingTransactions Web サービスを作成するには</span><span class="sxs-lookup"><span data-stu-id="c6126-271">To create the PendingTransactions Web service for runtime</span></span>  
  
1.  <span data-ttu-id="c6126-272">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**を右クリックし、**既定の Web サイト**、 をポイント**新規**とをクリックして**仮想ディレクトリ**を実行する**仮想ディレクトリの作成ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-272">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
     <span data-ttu-id="c6126-273">使用して、**仮想ディレクトリの作成ウィザード**、スタブ SAP Web サービスの次の仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-273">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the stub SAP Web service:</span></span>  
  
     <span data-ttu-id="c6126-274">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions</span><span class="sxs-lookup"><span data-stu-id="c6126-274">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions</span></span>  
  
     <span data-ttu-id="c6126-275">パス = \< *BizTalk インストール ディレクトリ*> \SDK\Scenarios\SO\MFAccess\PendingTransactions</span><span class="sxs-lookup"><span data-stu-id="c6126-275">PATH = \<*BizTalk Install Directory*>\SDK\Scenarios\SO\MFAccess\PendingTransactions</span></span>  
  
     <span data-ttu-id="c6126-276">Access Permissions = Read, Run scripts</span><span class="sxs-lookup"><span data-stu-id="c6126-276">Access Permissions = Read, Run scripts</span></span>  
  
2.  <span data-ttu-id="c6126-277">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**、展開、**既定の Web サイト**を右クリックしてクリックして、Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-277">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions, and then click **Properties**.</span></span>  
  
    1.  <span data-ttu-id="c6126-278">**ディレクトリ セキュリティ** タブで、をクリックして**編集**を変更する**認証とアクセス制御**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-278">In the **Directory Security** tab, click **Edit** to modify **Authentication and access control**.</span></span> <span data-ttu-id="c6126-279">選択**基本認証 (パスワードはクリア テキストで送信)**、し、その他をオフに**認証アクセス**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="c6126-279">Select **Basic authentication (password is sent in clear text)**, and clear other **Authentication access** checkboxes.</span></span> <span data-ttu-id="c6126-280">をクリックして**OK**を閉じる、**認証方法** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="c6126-280">Click **OK** to close the **Authentication Methods** dialog box.</span></span>  
  
    2.  <span data-ttu-id="c6126-281">**ディレクトリ セキュリティ** タブで、をクリックして**編集**下にある、**セキュリティで保護された通信**ボックスで、グループ化し、確認**セキュリティで保護されたチャネル (SSL)**で、**セキュリティ保護された通信** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="c6126-281">In the **Directory Security** tab, click **Edit** under the **Secure Communication** group box, and then check **Require secure channel (SSL)** in the **Secure Communications** dialog box.</span></span>  
  
    3.  <span data-ttu-id="c6126-282">**仮想ディレクトリ** タブで、設定、**アプリケーション プール**Pending Transaction Web サービスの新しい IIS アプリケーション プールの作成"するには」手順で作成したアプリケーション プールにします。</span><span class="sxs-lookup"><span data-stu-id="c6126-282">In the **Virtual Directory** tab, set the **Application Pool** to the application pool that you created in the procedure "To create a new IIS application pool for the Pending Transaction Web services".</span></span>  
  
#### <a name="to-create-the-pendingtransactions-web-service-for-development-environment"></a><span data-ttu-id="c6126-283">開発環境用の PendingTransactions Web サービスを作成するには</span><span class="sxs-lookup"><span data-stu-id="c6126-283">To create the PendingTransactions Web service for development environment</span></span>  
  
1.  <span data-ttu-id="c6126-284">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**を右クリックし、**既定の Web サイト**、 をポイント**新規**とをクリックして**仮想ディレクトリ**を実行する**仮想ディレクトリの作成ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-284">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
     <span data-ttu-id="c6126-285">使用して、**仮想ディレクトリの作成ウィザード**、スタブ SAP Web サービスの次の仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-285">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the stub SAP Web service:</span></span>  
  
     <span data-ttu-id="c6126-286">Alias = PendingTransactions</span><span class="sxs-lookup"><span data-stu-id="c6126-286">Alias = PendingTransactions</span></span>  
  
     <span data-ttu-id="c6126-287">パス = \< *BizTalk インストール ディレクトリ*> \SDK\Scenarios\SO\MFAccess\PendingTransactions</span><span class="sxs-lookup"><span data-stu-id="c6126-287">PATH = \<*BizTalk Install Directory*>\SDK\Scenarios\SO\MFAccess\PendingTransactions</span></span>  
  
     <span data-ttu-id="c6126-288">Access Permissions = Read, Run scripts</span><span class="sxs-lookup"><span data-stu-id="c6126-288">Access Permissions = Read, Run scripts</span></span>  
  
2.  <span data-ttu-id="c6126-289">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Web サイト**、展開、**既定の Web サイト**PendingTransactions を右クリックし、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-289">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, expand the **Default Web Site**, right-click PendingTransactions, and then click **Properties**.</span></span>  
  
    1.  <span data-ttu-id="c6126-290">**ディレクトリ セキュリティ** タブで、をクリックして**編集**を変更する**認証とアクセス制御**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-290">In the **Directory Security** tab, click **Edit** to modify **Authentication and access control**.</span></span> <span data-ttu-id="c6126-291">選択**への匿名アクセスを有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-291">Select **Enable anonymous access**.</span></span> <span data-ttu-id="c6126-292">をクリックして**OK**を終了します。</span><span class="sxs-lookup"><span data-stu-id="c6126-292">Click **OK** to exit.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c6126-293">開発環境用の PendingTransactions Web アプリケーションは [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で使用します。</span><span class="sxs-lookup"><span data-stu-id="c6126-293">The PendingTransactions Web application for development environment will be used by [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="c6126-294">この Web アプリケーションは実稼働環境では不要です。</span><span class="sxs-lookup"><span data-stu-id="c6126-294">You don't need this Web application for production environment.</span></span>  
  
    2.  <span data-ttu-id="c6126-295">**仮想ディレクトリ** タブで、設定、**アプリケーション プール**Pending Transaction Web サービスの新しい IIS アプリケーション プールの作成"するには」手順で作成したアプリケーション プールにします。</span><span class="sxs-lookup"><span data-stu-id="c6126-295">In the **Virtual Directory** tab, set the **Application Pool** to the application pool that you created in the procedure "To create a new IIS application pool for the Pending Transaction Web services".</span></span>  
  
#### <a name="to-create-the-stub-sap-web-service"></a><span data-ttu-id="c6126-296">スタブ SAP Web サービスを作成するには</span><span class="sxs-lookup"><span data-stu-id="c6126-296">To create the Stub SAP Web service</span></span>  
  
1.  <span data-ttu-id="c6126-297">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**を右クリックし、**既定の Web サイト**、 をポイント**新規**とをクリックして**仮想ディレクトリ**を実行する**仮想ディレクトリの作成ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-297">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
     <span data-ttu-id="c6126-298">使用して、**仮想ディレクトリの作成ウィザード**、スタブ SAP Web サービスの次の仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-298">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the stub SAP Web service:</span></span>  
  
     <span data-ttu-id="c6126-299">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP</span><span class="sxs-lookup"><span data-stu-id="c6126-299">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP</span></span>  
  
     <span data-ttu-id="c6126-300">パス = \< *BizTalk インストール ディレクトリ*> \SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP</span><span class="sxs-lookup"><span data-stu-id="c6126-300">PATH = \<*BizTalk Install Directory*>\SDK\Scenarios\SO\BTSSoln\StubWebServices\SAP</span></span>  
  
     <span data-ttu-id="c6126-301">Access Permissions = Read, Run scripts</span><span class="sxs-lookup"><span data-stu-id="c6126-301">Access Permissions = Read, Run scripts</span></span>  
  
2.  <span data-ttu-id="c6126-302">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**、展開、**既定の Web サイト**を右クリックしてMicrosoft.Samples.BizTalk.WoodgroveBank.StubSAP をクリックして**プロパティ**、し、次のように設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="c6126-302">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="c6126-303">**仮想ディレクトリ** タブで、設定、**アプリケーション プール**に\< *YourAppPool*> 新しい IIS アプリケーションを作成するには」の手順で作成します。プール Pending Transaction Web サービスの"です。</span><span class="sxs-lookup"><span data-stu-id="c6126-303">In the **Virtual directory** tab, set the **Application Pool** to \<*YourAppPool*> that you created in the procedure "To create a new IIS application pool for the Pending Transaction Web services".</span></span>  
  
    2.  <span data-ttu-id="c6126-304">**ディレクトリ セキュリティ**] タブで、をクリックして**編集**で、**認証とアクセス制御**ボックスで、グループ化し、[ **への匿名アクセスを有効にします。**.</span><span class="sxs-lookup"><span data-stu-id="c6126-304">In the **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, and then select **Enable anonymous access**.</span></span> <span data-ttu-id="c6126-305">をクリックして**OK**を終了します。</span><span class="sxs-lookup"><span data-stu-id="c6126-305">Click **OK** to exit.</span></span>  
  
##  <span data-ttu-id="c6126-306"><a name="step11"></a>サービス指向ソリューションの TI コンポーネントを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-306"><a name="step11"></a> Create the TI component for the Service Oriented Solution</span></span>  
  
#### <a name="to-create-a-com-application-for-the-ti-component"></a><span data-ttu-id="c6126-307">TI コンポーネント用の COM+ アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="c6126-307">To create a COM+ application for the TI component</span></span>  
  
1.  <span data-ttu-id="c6126-308">コマンド プロンプトで %systemroot%\system32\com\comexp.msc を実行します。</span><span class="sxs-lookup"><span data-stu-id="c6126-308">At a command prompt, run %systemroot%\system32\com\comexp.msc.</span></span>  
  
2.  <span data-ttu-id="c6126-309">**コンポーネント サービス**コンソールで、**コンポーネント サービス**、展開**コンピューター**、展開**マイ コンピューター**を右クリックして**COM + アプリケーション**、指す**新規**、順にクリック**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-309">In **Component Services** console, expand **Component Services**, expand **Computers**, expand **My Computer**, right-click **COM+ Application**, point to **New**, and then click **Application**.</span></span>  
  
    1.  <span data-ttu-id="c6126-310">**へようこそ**  ページで、をクリックして**次へ**、順にクリック**空のアプリケーションを作成**上、**のインストールまたは新しいアプリケーションを作成**ページ。</span><span class="sxs-lookup"><span data-stu-id="c6126-310">On the **Welcome** page, click **Next**, and then click **Create an empty application** on the **Install or Create a New Application** page.</span></span>  
  
    2.  <span data-ttu-id="c6126-311">型`BTSScn SO TI Component`で、**新しいアプリケーションの名前を入力**ボックスで、**サーバー アプリケーション**として**ライセンス認証の種類**、クリックして**次へ**.</span><span class="sxs-lookup"><span data-stu-id="c6126-311">Type `BTSScn SO TI Component` in the **Enter a name for the new application** box, select **Server application** as **Activation type**, and then click **Next**.</span></span>  
  
    3.  <span data-ttu-id="c6126-312">**アカウント**のグループ ボックス、**アプリケーション Id の設定**] ページで、[**このユーザー**、ユーザー名とパスワードを入力し、**ユーザー**と**パスワード**ボックス。</span><span class="sxs-lookup"><span data-stu-id="c6126-312">In the **Account** group box of the **Set Application Identity** page, select **This user**, and then type the user name and password in the **User** and **Password** boxes.</span></span> <span data-ttu-id="c6126-313">作成する COM+ アプリケーションは、このユーザー アカウントで実行されます。</span><span class="sxs-lookup"><span data-stu-id="c6126-313">The new COM+ application will run under this user account.</span></span> <span data-ttu-id="c6126-314">このユーザー アカウントは、ローカルの HIS Runtime Users グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6126-314">This user account must be a member of local HIS Runtime Users group.</span></span> <span data-ttu-id="c6126-315">このチュートリアルでは、BizTalk サービスが使用するユーザー アカウントとして同じものを使用します。</span><span class="sxs-lookup"><span data-stu-id="c6126-315">For this walkthrough, use the same user account that the BizTalk service is using.</span></span>  
  
    4.  <span data-ttu-id="c6126-316">**アプリケーション ロールの追加**] ページで [**次**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-316">On the **Add Application Roles** page, click **Next**.</span></span>  
  
    5.  <span data-ttu-id="c6126-317">**にユーザー ロールを追加** ページで、展開**CreatorOwner**、 をクリックして**ユーザー**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-317">On the **Add Users to Roles** page, expand **CreatorOwner**, click **Users**, and then click **Add**.</span></span>  
  
    6.  <span data-ttu-id="c6126-318">**[ユーザーまたはグループ**] ダイアログ ボックスで、メインフレームにアクセスするために使用されるユーザー アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6126-318">On the **Select Users or Groups** dialog box, select a user account that will be used for accessing the mainframe.</span></span> <span data-ttu-id="c6126-319">このチュートリアルでは、UserID ローカル アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="c6126-319">For this walkthrough, add UserID local account.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c6126-320">TI コンポーネントを使用して CICS トランザクションにアクセスする場合、.NET リモート コンポーネントをホストしている COM+ アプリケーションまたは Web アプリケーションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6126-320">To access the CICS transaction through the TI component, you can use the COM+ application or the Web application hosting the .NET Remoting component.</span></span> <span data-ttu-id="c6126-321">このチュートリアルではメインフレームへのアクセスに TI コンポーネント用の COM+ アプリケーションおよび COM 相互運用を使用して、パフォーマンスを向上させます。</span><span class="sxs-lookup"><span data-stu-id="c6126-321">This walkthrough uses the COM+ application and COM Interop for TI components to access the mainframe to improve performance.</span></span>  
  
    7.  <span data-ttu-id="c6126-322">**完了**] ページで [**完了**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-322">On the **Completion** page, click **Finish**.</span></span>  
  
#### <a name="to-create-a-remote-environment-to-access-the-mainframe"></a><span data-ttu-id="c6126-323">メインフレームにアクセスするためのリモート環境を作成するには</span><span class="sxs-lookup"><span data-stu-id="c6126-323">To create a Remote Environment to access the mainframe</span></span>  
  
1.  <span data-ttu-id="c6126-324">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Host Integration Server 2004**、順にクリック**TI マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-324">Click **Start**, point to **All Programs**, point to **Microsoft Host Integration Server 2004**, and then click **TI Manager**.</span></span>  
  
2.  <span data-ttu-id="c6126-325">**TI マネージャー**コンソールで **トランザクション インテグレーター (構成)**、展開**Windows Initiated Processing**を右クリックして**リモート環境**、指す**新規**、順にクリック**リモート環境**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-325">In the **TI Manager** console, click **Transaction Integrator (Configuration)**, expand **Windows Initiated Processing**, right-click **Remote Environments**, point to **New**, and then click **Remote Environment**.</span></span>  
  
    1.  <span data-ttu-id="c6126-326">**ようこそ** ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-326">On the **Welcome** page, click **Next**.</span></span>  
  
    2.  <span data-ttu-id="c6126-327">**新しいリモート環境の構成** ページで、入力、**リモート アプリケーション名**、クリックして**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-327">On the **Configure a New Remote Environment** page, type the **Remote Application Name**, and then click **Next**.</span></span> <span data-ttu-id="c6126-328">このチュートリアルでは、Mainframe_TCP という名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="c6126-328">For this walkthrough, use Mainframe_TCP for the name.</span></span>  
  
    3.  <span data-ttu-id="c6126-329">**ホスト環境の構成とプログラミング モデル**] ページで、[ **CICS**の**ターゲット ホスト**と**ELM リンク**の**プログラミング モデル**、クリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-329">On the **Configure Host Environment and Programming Model** page, select **CICS** for the **Target host** and **ELM Link** for the **Programming model**, and then click **Next**.</span></span>  
  
    4.  <span data-ttu-id="c6126-330">**エンドポイント TCP/IP の構成** ページにメインフレームの IP アドレスを入力、 **IP/DNS アドレス**ボックスし、をクリックして**編集**ポート番号を追加します。</span><span class="sxs-lookup"><span data-stu-id="c6126-330">On **the Configure Endpoint TCP/IP** page, type the IP address for your mainframe in the **IP/DNS address** box, and then click **Edit** to add the port number.</span></span> <span data-ttu-id="c6126-331">HIS COM は、このエンドポイント アドレスを使用してトランザクションにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c6126-331">Your HIS COM will access the transactions through the endpoint address.</span></span>  
  
    5.  <span data-ttu-id="c6126-332">**完了**] ページで [**完了**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-332">On the **Completion** page, click **Finish**.</span></span>  
  
#### <a name="to-create-the-ti-component-for-the-service-oriented-solution"></a><span data-ttu-id="c6126-333">サービス指向ソリューション用の TI コンポーネントを作成するには</span><span class="sxs-lookup"><span data-stu-id="c6126-333">To create the TI Component for the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="c6126-334">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Host Integration Server 2004**、順にクリック**TI マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-334">Click **Start**, point to **All Programs**, point to **Microsoft Host Integration Server 2004**, and then click **TI Manager**.</span></span>  
  
2.  <span data-ttu-id="c6126-335">**TI マネージャー**コンソールで、をクリックして**トランザクション インテグレーター (構成)**をクリックして**Windows Initiated Processing**、順にクリック**オブジェクト**.</span><span class="sxs-lookup"><span data-stu-id="c6126-335">In the **TI Manager** console, click **Transaction Integrator (Configuration)**, click **Windows Initiated Processing**, and then click **Objects**.</span></span> <span data-ttu-id="c6126-336">右クリック**オブジェクト**をクリックして**新規**、順にクリック**オブジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-336">Right-click **Objects**, click **New**, and then click **Object**.</span></span>  
  
    1.  <span data-ttu-id="c6126-337">**ようこそ** ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-337">On the **Welcome** page, click **Next**.</span></span>  
  
    2.  <span data-ttu-id="c6126-338">**指定または検索オブジェクト** ページで **参照**、%BTSSolutionsPath%\SO\MFAccess\HISTIComponent フォルダーの SOHISTIUsingCOM.TLB を選択し、クリックして**次へ**.</span><span class="sxs-lookup"><span data-stu-id="c6126-338">On the **Specify Or Locate An Object** page, click **Browse**, choose the SOHISTIUsingCOM.TLB in the %BTSSolutionsPath%\SO\MFAccess\HISTIComponent folder, and then click **Next**.</span></span>  
  
    3.  <span data-ttu-id="c6126-339">**COM オブジェクトの環境特性の定義**] ページで、[ **BTSScn SO TI Component**の**COM + アプリケーション**、クリックして**[次へ]**.</span><span class="sxs-lookup"><span data-stu-id="c6126-339">On the **Define Environment Characteristics for The COM Object** page, select **BTSScn SO TI Component** for the **COM+ application**, and then click **Next**.</span></span>  
  
    4.  <span data-ttu-id="c6126-340">**リモート環境の定義** ページで、前の手順で作成したリモート環境を選択して、**リモート環境では、し、次へ をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="c6126-340">On the **Define Remote Environment** page, select the remote environment that you created in the previous procedure for the **Remote environment, and then click Next.**</span></span>  
  
    5.  <span data-ttu-id="c6126-341">**WIP オブジェクトの作成** ページで、をクリックして**次へ**、順にクリック**完了**上、**完了**ページ。</span><span class="sxs-lookup"><span data-stu-id="c6126-341">On the **Creation of WIP Objects** page, click **Next**, and then click **Finish** on the **Completion** page.</span></span>  
  
#### <a name="to-test-the-connectivity-to-the-mainframe"></a><span data-ttu-id="c6126-342">メインフレームへの接続をテストするには</span><span class="sxs-lookup"><span data-stu-id="c6126-342">To test the connectivity to the mainframe</span></span>  
  
1.  <span data-ttu-id="c6126-343">Windows エクスプローラーで %BTSSolutionsPath%\SO\MFAccess\HISTISimpleTester フォルダーを開き、Interop.SOHISTIUsingCOM.dll.reg ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6126-343">In Windows Explorer, browse to the %BTSSolutionsPath%\SO\MFAccess\HISTISimpleTester folder, and then double-click the Interop.SOHISTIUsingCOM.dll.reg file.</span></span> <span data-ttu-id="c6126-344">これにより、ランタイム呼び出し可能ラッパー (RCW) を経由して TI コンポーネントを呼び出す HISTISimpleTester アプリケーションのレジストリ値が追加されます。</span><span class="sxs-lookup"><span data-stu-id="c6126-344">This adds registry values for the HISTISimpleTester application to call the TI component through the Runtime Callable Wrapper (RCW).</span></span>  
  
2.  <span data-ttu-id="c6126-345">Windows エクスプローラーで %BTSSolutionsPath%\SO\MFAccess\ フォルダーを開き、SetupMFAccess.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="c6126-345">In Windows Explorer, browse to the %BTSSolutionsPath%\SO\MFAccess\ folder, and then run SetupMFAccess.bat.</span></span>  
  
3.  <span data-ttu-id="c6126-346">Windows エクスプローラーで %BTSSolutionsPath%\SO\MFAccess\HISTISimpleTester\bin\Debug フォルダーに移動し、BTSScnSOHISTIComponentSimpleTester.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="c6126-346">In Windows Explorer, navigate to the %BTSSolutionsPath%\SO\MFAccess\HISTISimpleTester\bin\Debug folder, and then run BTSScnSOHISTIComponentSimpleTester.exe.</span></span>  
  
    -   <span data-ttu-id="c6126-347">HISTISimpleTester アプリケーションでクリックして**Call Mainframe Program - COM を使用して**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-347">In the HISTISimpleTester application, click **Call Mainframe Program - Using COM**.</span></span> <span data-ttu-id="c6126-348">メインフレームで実行されている COBOL アプリケーションから、5 レコードが返されます。</span><span class="sxs-lookup"><span data-stu-id="c6126-348">It returns five records from the COBOL application running on the mainframe.</span></span>  
  
##  <span data-ttu-id="c6126-349"><a name="step13"></a>Web サービスのオーケストレーションの仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-349"><a name="step13"></a> Create the virtual directories for the orchestration Web services</span></span>  
  
#### <a name="to-create-the-virtual-directories-for-the-orchestration-web-services"></a><span data-ttu-id="c6126-350">オーケストレーション Web サービス用の仮想ディレクトリを作成するには</span><span class="sxs-lookup"><span data-stu-id="c6126-350">To create the virtual directories for the orchestration Web services</span></span>  
  
1.  <span data-ttu-id="c6126-351">**インターネット インフォメーション サービス (IIS) マネージャー**を右クリックして**アプリケーション プール****新規**、し、 **のアプリケーションプール**.</span><span class="sxs-lookup"><span data-stu-id="c6126-351">In the **Internet Information Services (IIS) Manager**, right-click **Application Pools**, select **New**, and then select **Application Pool**.</span></span>  
  
    1.  <span data-ttu-id="c6126-352">**新しいアプリケーション プールの追加** ダイアログ ボックスに、入力、**アプリケーション プール ID** (任意の値) をクリックし、 **ok**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-352">On the **Add New Application Pool** dialog box, enter the **Application pool ID** (any value), and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="c6126-353">作成したアプリケーション プールを右クリックし、**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-353">Right-click the application pool that you just created, and then select **Properties**.</span></span>  
  
    3.  <span data-ttu-id="c6126-354">**プロパティ** ページで、をクリックして、 **Identity**  タブで **構成可能**、入力、**ユーザー名**と**パスワード**、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-354">On the **Properties** page, click the **Identity** tab, select **Configurable**, enter the **User name** and **Password**, and then click **OK**.</span></span> <span data-ttu-id="c6126-355">このチュートリアルでは、BizTalk サービスが使用しているユーザー アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="c6126-355">For this walkthrough use the same user account that the BizTalk service is using.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-356">このユーザーには、オーケストレーション プロキシ Web サービスを実行する権限が必要です。また、BizTalk Server 管理者グループ、SSO 管理者グループ、または SSO 関連管理者グループのいずれかにこのユーザーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6126-356">This user must have permission to execute the Orchestration Proxy Web service, and must be added to one of the BizTalk Server Administrators, SSO Administrators, or SSO Affiliated Administrators groups</span></span>  
  
2.  <span data-ttu-id="c6126-357">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**を右クリックし、**既定の Web サイト**、 をポイント**新規**とをクリックして**仮想ディレクトリ**を実行する**仮想ディレクトリの作成ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-357">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
     <span data-ttu-id="c6126-358">使用して、**仮想ディレクトリの作成ウィザード**、アダプター バージョン用の Web サービス プロキシの次の仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-358">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the proxy Web service for the adapter version:</span></span>  
  
     <span data-ttu-id="c6126-359">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter</span><span class="sxs-lookup"><span data-stu-id="c6126-359">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter</span></span>  
  
     <span data-ttu-id="c6126-360">パス = \< *BizTalk インストール ディレクトリ*> \SDK\Scenarios\SO\BTSSoln\OrchProxy\Adapter</span><span class="sxs-lookup"><span data-stu-id="c6126-360">PATH = \<*BizTalk Install Directory*>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Adapter</span></span>  
  
     <span data-ttu-id="c6126-361">Access Permissions = Read, Run scripts</span><span class="sxs-lookup"><span data-stu-id="c6126-361">Access Permissions = Read, Run scripts</span></span>  
  
3.  <span data-ttu-id="c6126-362">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Web サイト、**展開、 **Default Web Site**を右クリックしてMicrosoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter をクリックして**プロパティ**、し、次のように設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="c6126-362">In the **Internet Information Services (IIS) Manager**, expand **Web Sites,** expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="c6126-363">**仮想ディレクトリ** タブで、設定、**アプリケーション プール**に\< *YourAppPool*> 前の手順で作成しました。</span><span class="sxs-lookup"><span data-stu-id="c6126-363">In the **Virtual directory** tab, set the **Application Pool** to \<*YourAppPool*> that you created in the previous step.</span></span>  
  
    2.  <span data-ttu-id="c6126-364">**ディレクトリ セキュリティ** タブで、をクリックして**編集**で、**認証とアクセス制御**グループ ボックスで、**統合 Windows 認証のみ有効になっている**、し、その他のオフ**認証アクセス**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="c6126-364">In the **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, select **Only Integrated Windows Authentication enabled**, and then clear other **Authentication access** checkboxes.</span></span> <span data-ttu-id="c6126-365">をクリックして**OK**を終了します。</span><span class="sxs-lookup"><span data-stu-id="c6126-365">Click **OK** to exit.</span></span>  
  
4.  <span data-ttu-id="c6126-366">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**を右クリックし、**既定の Web サイト**、 をポイント**新規**とをクリックして**仮想ディレクトリ**を実行する**仮想ディレクトリの作成ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-366">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
     <span data-ttu-id="c6126-367">使用して、**仮想ディレクトリの作成ウィザード**、インライン バージョン用の Web サービス プロキシの次の仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-367">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for the proxy Web service for the inline version:</span></span>  
  
     <span data-ttu-id="c6126-368">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline</span><span class="sxs-lookup"><span data-stu-id="c6126-368">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline</span></span>  
  
     <span data-ttu-id="c6126-369">パス = \< *BizTalk インストール ディレクトリ*> \SDK\Scenarios\SO\BTSSoln\OrchProxy\Inline</span><span class="sxs-lookup"><span data-stu-id="c6126-369">PATH = \<*BizTalk Install Directory*>\SDK\Scenarios\SO\BTSSoln\OrchProxy\Inline</span></span>  
  
     <span data-ttu-id="c6126-370">Access Permissions = Read, Run scripts</span><span class="sxs-lookup"><span data-stu-id="c6126-370">Access Permissions = Read, Run scripts</span></span>  
  
5.  <span data-ttu-id="c6126-371">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**、展開、**既定の Web サイト**を右クリックしてMicrosoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline をクリックして**プロパティ**、し、次のように設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="c6126-371">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="c6126-372">**仮想ディレクトリ** タブで、設定、**アプリケーション プール**に\< *YourAppPool*> で作成しました。</span><span class="sxs-lookup"><span data-stu-id="c6126-372">On the **Virtual directory** tab, set the **Application Pool** to \<*YourAppPool*> you just created.</span></span>  
  
    2.  <span data-ttu-id="c6126-373">をクリックして**ディレクトリ セキュリティ** タブで、をクリックして**編集**で、**認証とアクセス制御**グループ ボックスで、**統合 Windows 認証のみ有効になっている**、し、その他のオフ**認証アクセス**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="c6126-373">Click **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, select **Only Integrated Windows Authentication enabled**, and then clear other **Authentication access** checkboxes.</span></span> <span data-ttu-id="c6126-374">をクリックして**OK**を終了します。</span><span class="sxs-lookup"><span data-stu-id="c6126-374">Click **OK** to exit.</span></span>  
  
##  <span data-ttu-id="c6126-375"><a name="step15"></a>ビルド サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="c6126-375"><a name="step15"></a> Build the Service Oriented Solution</span></span>  
  
#### <a name="to-build-the-service-oriented-solution"></a><span data-ttu-id="c6126-376">サービス指向ソリューションをビルドするには</span><span class="sxs-lookup"><span data-stu-id="c6126-376">To build the Service Oriented solution</span></span>  
  
-   <span data-ttu-id="c6126-377">コマンド プロンプトでディレクトリを変更 BTSSolutionsPath%\SO\BTSSoln、型 % `SetupBTSSoln.bat`、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c6126-377">At a command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln, type `SetupBTSSoln.bat`, and then press ENTER.</span></span> <span data-ttu-id="c6126-378">SetupBTSSoln.bat では、次のタスクが実行されます。</span><span class="sxs-lookup"><span data-stu-id="c6126-378">The SetupBTSSoln.bat performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="c6126-379">SO ソリューションのアセンブリに署名を一意の厳密な名前キー (SNK) を作成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-379">Creates a unique strong name key (SNK) for signing the assemblies of the SO Solution.</span></span>  
  
    -   <span data-ttu-id="c6126-380">SNK から公開キー トークンを抽出し、公開キー トークンを使用してバインド ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="c6126-380">Extracts the public key token from the SNK and updates the binding files with the public token.</span></span>  
  
    -   <span data-ttu-id="c6126-381">SO ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="c6126-381">Builds the SO solution.</span></span>  
  
    -   <span data-ttu-id="c6126-382">%BTSSolutionsPath%\Common フォルダーに SSOApplicationConfig を作成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-382">Builds the SSOApplicationConfig in the %BTSSolutionsPath%\Common folder.</span></span>  
  
##  <span data-ttu-id="c6126-383"><a name="step17"></a>SSO 関連アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-383"><a name="step17"></a> Create the SSO affiliate applications</span></span>  
  
#### <a name="to-create-the-sso-affiliate-applications"></a><span data-ttu-id="c6126-384">SSO 関連アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="c6126-384">To create the SSO affiliate applications</span></span>  
  
1.  <span data-ttu-id="c6126-385">コマンド プロンプトを開いて、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更します。</span><span class="sxs-lookup"><span data-stu-id="c6126-385">Open a command prompt, and then change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder.</span></span>  
  
2.  <span data-ttu-id="c6126-386">コマンド プロンプトで、メモ帳を使用して PendTransAffApp.xml を開き、内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="c6126-386">At the command prompt, open the PendTransAffApp.xml using Notepad, and review it.</span></span> <span data-ttu-id="c6126-387">このファイルへの変更は、不要です。</span><span class="sxs-lookup"><span data-stu-id="c6126-387">No changes to this file are necessary.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-388">PendTransAffApp.xml では、Pending Transactions バックエンド システム用の SSO 関連アプリケーション WoodgroveBank.PendingTransactions が定義されています。</span><span class="sxs-lookup"><span data-stu-id="c6126-388">The PendTransAffApp.xml file defines the SSO affiliate application, WoodgroveBank.PendingTransactions, for the Pending Transactions back-end system.</span></span> <span data-ttu-id="c6126-389">また、SSO 関連アプリケーションのユーザー グループと管理者グループも定義されています。</span><span class="sxs-lookup"><span data-stu-id="c6126-389">It also defines the user and administrative groups for the SSO affiliate application.</span></span> <span data-ttu-id="c6126-390">このチュートリアルでは、使用**BizTalk Application Users**と**BizTalk Server 管理者**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-390">For this walkthrough, use **BizTalk Application Users** and **BizTalk Server Administrators**.</span></span>  
    >   
    >  <span data-ttu-id="c6126-391">SSO 関連アプリケーションの別のグループを使用する場合は、Active Directory で (任意の名前) を持つ Windows グループを作成し、変更する必要があります、 **appAdminAccount**と**appUserAccount**PendTransAffApp.xml 内のノードです。</span><span class="sxs-lookup"><span data-stu-id="c6126-391">If you want to use different groups for the SSO affiliate application, you need to create Windows groups (with any name) in the Active Directory, and then change the **appAdminAccount** and **appUserAccount** nodes in the PendTransAffApp.xml.</span></span> <span data-ttu-id="c6126-392">これを行う場合は、値を設定する必要があります**groupApp**の属性**フラグ**ノードを"yes"です。</span><span class="sxs-lookup"><span data-stu-id="c6126-392">If you do this, you should set the value for **groupApp** attribute of **flags** node to "yes".</span></span>  
    >   
    >  <span data-ttu-id="c6126-393">SSO 関連アプリケーションの詳細については、次を参照してください。 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)です。</span><span class="sxs-lookup"><span data-stu-id="c6126-393">For more information about SSO affiliate applications, see [SSO Affiliate Applications](../core/sso-affiliate-applications.md).</span></span>  
  
3.  <span data-ttu-id="c6126-394">コマンド プロンプトで、メモ帳を使用して PendTransUserMap.xml ファイルを開き、次のように編集します。</span><span class="sxs-lookup"><span data-stu-id="c6126-394">At the command prompt, open the PendTransUserMap.xml file using Notepad, and then make the following edits:</span></span>  
  
    ```  
    <mapping>  
      <windowsDomain><DomainName></windowsDomain>  
      <windowsUserId><UserID></windowsUserId>  
      <externalUserId><ExternalUserID></externalUserId>  
    </mapping>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-395">PendTransUserMap.xml ファイルには、Pending Transactions バックエンド システム用のユーザー マッピングが保存されています。</span><span class="sxs-lookup"><span data-stu-id="c6126-395">The PendTransUserMap.xml file contains the user mappings for the Pending Transactions back-end system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-396">**ExternalUserId**ノード、Pending Transactions バックエンド システムの外部ユーザー ID を使用します。</span><span class="sxs-lookup"><span data-stu-id="c6126-396">For the **externalUserId** node, use the external user ID for the Pending Transactions back-end system.</span></span> <span data-ttu-id="c6126-397">このチュートリアルでは、外部 ID として UserID を使用します。</span><span class="sxs-lookup"><span data-stu-id="c6126-397">For this walkthrough, use UserID for the external ID.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-398">**WindowsUserId**ノード、ユーザー入力名に、 **externalUserId**にマップされます。</span><span class="sxs-lookup"><span data-stu-id="c6126-398">For the **windowsUserId** node, enter the user name which the **externalUserId** will map to.</span></span> <span data-ttu-id="c6126-399">ドメイン グループとドメイン ユーザー アカウントの両方を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6126-399">You can use both a domain group and a domain user account.</span></span> <span data-ttu-id="c6126-400">このユーザーは、Pending Transactions バックエンド システムの使用が許可されたグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6126-400">This user must be a member of the group that will be allowed to use the Pending Transactions back-end system.</span></span> <span data-ttu-id="c6126-401">このチュートリアルでは、BizTalk サービスのユーザー名を使用します。</span><span class="sxs-lookup"><span data-stu-id="c6126-401">For this walkthrough, use the user name of the BizTalk service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-402">**WindowsDomain**  ノードのドメイン名を入力、 **windowsUserId**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-402">For the **windowsDomain** node, enter the domain name of the **windowsUserId**.</span></span>  
  
4.  <span data-ttu-id="c6126-403">コマンド プロンプトで、メモ帳を使用して PmntTrckAffApp.xml ファイルを開き、ファイルの内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="c6126-403">At the command prompt, open the PmntTrckAffApp.xml file using Notepad, and review the contents of the file.</span></span> <span data-ttu-id="c6126-404">このファイルへの変更は、不要です。</span><span class="sxs-lookup"><span data-stu-id="c6126-404">No changes to this file are necessary.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-405">PmntTrckAffApp.xml では、Payment Tracker バックエンド システム用の SSO 関連アプリケーション WoodgroveBank.PaymentTracker が定義されています。</span><span class="sxs-lookup"><span data-stu-id="c6126-405">The PmntTrckAffApp.xml file defines the SSO affiliate application, WoodgroveBank.PaymentTracker, for the Payment Tracker back-end system.</span></span>  
  
5.  <span data-ttu-id="c6126-406">コマンド プロンプトで、メモ帳を使用して PmntTrckUserMap.xml ファイルを開き、次のように編集します。</span><span class="sxs-lookup"><span data-stu-id="c6126-406">At the command prompt, open the PmntTrckUserMap.xml file using Notepad, and then make the following edits:</span></span>  
  
    ```  
    <mapping>  
      <windowsDomain><DomainName></windowsDomain>  
      <windowsUserId><UserID></windowsUserId>  
      <externalUserId><ExternalUserID></externalUserId>  
    </mapping>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-407">Payment Tracker SSO 関連アプリケーションは MQSeries アダプターによって使用され、マップされた外部ユーザー IDおよびパスワードが MQSeries ヘッダー プロパティを使用して送信されます。</span><span class="sxs-lookup"><span data-stu-id="c6126-407">The Payment Tracker SSO affiliated application will be used for the MQSeries Adapter and the mapped external user ID/password are sent through MQSeries header properties.</span></span> <span data-ttu-id="c6126-408">MQSeries アダプターが実行されている場合、MQSeries サーバーは BizTalk サービス アカウントのみを検証します。</span><span class="sxs-lookup"><span data-stu-id="c6126-408">The MQSeries Server validates only the BizTalk service account, under which MQSeries Adapter is running.</span></span> <span data-ttu-id="c6126-409">外部ユーザーの資格情報は検証しません。</span><span class="sxs-lookup"><span data-stu-id="c6126-409">It doesn't validate any external user credential.</span></span>  
    >   
    >  <span data-ttu-id="c6126-410">SSO の詳細については、MQSeries アダプタのアプリケーションをそれ以後を参照してください[方法を構成する MQSeries アダプターの受信場所と送信ポートに](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)です。</span><span class="sxs-lookup"><span data-stu-id="c6126-410">For more information about SSO affiliated applications for the MQSeries Adapter, see [How to Configure MQSeries Adapter Receive Locations and Send Ports](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-411">PmntTrckUserMap.xml ファイルには、Payment Tracker バックエンド システム用の SSO ユーザー マッピングが保存されています。</span><span class="sxs-lookup"><span data-stu-id="c6126-411">The PmntTrckUserMap.xml file contains the SSO user mappings for the Payment Tracker back-end system.</span></span> <span data-ttu-id="c6126-412">Payment Tracker シミュレーター プログラムでは、ユーザー認証が成功する条件と失敗する条件の両方がシミュレートされます。</span><span class="sxs-lookup"><span data-stu-id="c6126-412">The Payment Tracker simulator program simulates both success and failure conditions for user authentication.</span></span>  
    >   
    >  <span data-ttu-id="c6126-413">プログラム文字で始まるすべてのユーザー Id の認証に成功**PT** (たとえば、 **PTUserID**)、すべてのユーザーで始まっていない Id の認証に失敗したと**PT**.</span><span class="sxs-lookup"><span data-stu-id="c6126-413">The program successfully authenticates all user IDs that begin with the letters **PT** (for example, **PTUserID**), and fails to authenticate any user IDs that do not begin with **PT**.</span></span> <span data-ttu-id="c6126-414">このため、テストする条件に応じて、適切なユーザー ID を選択できます。</span><span class="sxs-lookup"><span data-stu-id="c6126-414">This enables you to choose the appropriate user ID depending on the condition that you would like to test.</span></span> <span data-ttu-id="c6126-415">全体を繰り返すことができますも**マッピング**各ユーザー ID のノードと同じファイル内の複数のマッピングを定義します。</span><span class="sxs-lookup"><span data-stu-id="c6126-415">You can also repeat the entire **mapping** node for each user ID and define multiple mappings in the same file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-416">**ExternalUserId**ノード、Payment Tracker バックエンド システムの外部ユーザー ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="c6126-416">For the **externalUserId** node, enter the external user ID for the Payment Tracker back-end system.</span></span> <span data-ttu-id="c6126-417">このチュートリアルでは、外部 ID として PTUserID を使用します。</span><span class="sxs-lookup"><span data-stu-id="c6126-417">For this walkthrough, use PTUserID for the external ID.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-418">**WindowsUserId**ノード、ユーザー入力名に、 **externalUserId**にマップされます。</span><span class="sxs-lookup"><span data-stu-id="c6126-418">For the **windowsUserId** node, enter the user name which the **externalUserId** will map to.</span></span> <span data-ttu-id="c6126-419">このユーザーは、Payment Tracker バックエンド システムの使用が許可されたグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6126-419">This user must be a member of the group that will be allowed to use the Payment Tracker back-end system.</span></span> <span data-ttu-id="c6126-420">このチュートリアルでは、BizTalk サービスのユーザー名を使用します。</span><span class="sxs-lookup"><span data-stu-id="c6126-420">For this walkthrough, use the user name of the BizTalk service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-421">**WindowsDomain**  ノードのドメイン名を入力、 **windowsUserId**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-421">For the **windowsDomain** node, enter the domain name of the **windowsUserId**.</span></span>  
  
6.  <span data-ttu-id="c6126-422">コマンド プロンプトで、メモ帳を使用して ConfigStoreApp.xml ファイルを開き、ファイルの内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="c6126-422">At the command prompt, open the ConfigStoreApp.xml file using Notepad, and then review the contents of the file.</span></span>  
  
     <span data-ttu-id="c6126-423">このファイルは、このシナリオで構成パラメータを保存するために使用する SSO の構成ストア アプリケーションを定義します。</span><span class="sxs-lookup"><span data-stu-id="c6126-423">This file defines the configuration store application in SSO that the scenario uses to keep configuration parameters.</span></span> <span data-ttu-id="c6126-424">一部の構成パラメーターには、アダプター バージョンとインライン バージョンの両方の SAP との通信時に使用されるタイムアウト値と、インライン バージョンの使用時に使用するキュー マネージャーの名前およびキューが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c6126-424">Some of the configuration parameters include the Timeout value when communicating with SAP (for both the adapter and inline versions) and the name of the queue manager and queues to use when using the inline version.</span></span> <span data-ttu-id="c6126-425">このファイルへの変更は、不要です。</span><span class="sxs-lookup"><span data-stu-id="c6126-425">No changes to this file are necessary.</span></span>  
  
7.  <span data-ttu-id="c6126-426">コマンド プロンプトで、メモ帳を使用して SetConfigValuesInSSO.cmd ファイルを開き、次の表に従ってファイルの内容を確認および変更します。</span><span class="sxs-lookup"><span data-stu-id="c6126-426">At the command prompt, open the SetConfigValuesInSSO.cmd file using Notepad, review and change the contents of the file as the following table.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-427">このコマンド ファイルは、SSO データベースの構成パラメーターの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="c6126-427">This command file sets the values for the configuration parameters in the SSO database.</span></span> <span data-ttu-id="c6126-428">コマンド ファイルの最初にローカル変数の値を割り当てる SET ステートメントがいくつか含まれます。</span><span class="sxs-lookup"><span data-stu-id="c6126-428">It contains several set commands that assign the values to local variables in the beginning of the command file.</span></span>  
    >   
    >  <span data-ttu-id="c6126-429">SAPAdapterTimeout、PendingTransactionsAdapterTimeout、および PaymentTrackingAdapterTimeout の値は、アダプター バージョンで使用されます。</span><span class="sxs-lookup"><span data-stu-id="c6126-429">The SAPAdapterTimeout, PendingTransactionsAdapterTimeout, and PaymentTrackingAdapterTimeout values are used in the adapter version.</span></span> <span data-ttu-id="c6126-430">他の値は、インライン バージョンで使用されます。</span><span class="sxs-lookup"><span data-stu-id="c6126-430">The remaining values are used in the inline version.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-431">入力することができます""(2 つの二重引用符) マークされている既定値の\<ユーザー指定 > 次の表にします。</span><span class="sxs-lookup"><span data-stu-id="c6126-431">You can enter " " (two double quotes) for the default values marked \<User Specified> in the following table.</span></span>  
  
    |<span data-ttu-id="c6126-432">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c6126-432">Parameter</span></span>|<span data-ttu-id="c6126-433">既定値</span><span class="sxs-lookup"><span data-stu-id="c6126-433">Default Value</span></span>|<span data-ttu-id="c6126-434">Description</span><span class="sxs-lookup"><span data-stu-id="c6126-434">Description</span></span>|  
    |---------------|-------------------|-----------------|  
    |<span data-ttu-id="c6126-435">SAPAdapterTimeout</span><span class="sxs-lookup"><span data-stu-id="c6126-435">SAPAdapterTimeout</span></span>|<span data-ttu-id="c6126-436">20000</span><span class="sxs-lookup"><span data-stu-id="c6126-436">20000</span></span>|<span data-ttu-id="c6126-437">SAP バックエンドに対する要求の最大タイムアウト (ミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="c6126-437">Max timeout (millisecond) for a request to the SAP back-end</span></span>|  
    |<span data-ttu-id="c6126-438">SAPInlineTimeout</span><span class="sxs-lookup"><span data-stu-id="c6126-438">SAPInlineTimeout</span></span>|<span data-ttu-id="c6126-439">20000</span><span class="sxs-lookup"><span data-stu-id="c6126-439">20000</span></span>|<span data-ttu-id="c6126-440">SAP バックエンドに対する要求の最大タイムアウト (ミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="c6126-440">Max timeout (millisecond) for a request to the SAP back-end</span></span>|  
    |<span data-ttu-id="c6126-441">SAPInlineHostName</span><span class="sxs-lookup"><span data-stu-id="c6126-441">SAPInlineHostName</span></span>|<span data-ttu-id="c6126-442">\<指定されたユーザー ></span><span class="sxs-lookup"><span data-stu-id="c6126-442">\<User Specified></span></span>|<span data-ttu-id="c6126-443">SAP バックエンド識別子。</span><span class="sxs-lookup"><span data-stu-id="c6126-443">SAP back-end identifier</span></span>|  
    |<span data-ttu-id="c6126-444">SAPInlineClientNumber</span><span class="sxs-lookup"><span data-stu-id="c6126-444">SAPInlineClientNumber</span></span>|<span data-ttu-id="c6126-445">\<指定されたユーザー ></span><span class="sxs-lookup"><span data-stu-id="c6126-445">\<User Specified></span></span>|<span data-ttu-id="c6126-446">SAP クライアント番号。</span><span class="sxs-lookup"><span data-stu-id="c6126-446">SAP Client number</span></span>|  
    |<span data-ttu-id="c6126-447">SAPInlineSystemNumber</span><span class="sxs-lookup"><span data-stu-id="c6126-447">SAPInlineSystemNumber</span></span>|<span data-ttu-id="c6126-448">\<指定されたユーザー ></span><span class="sxs-lookup"><span data-stu-id="c6126-448">\<User Specified></span></span>|<span data-ttu-id="c6126-449">SAP システム番号。</span><span class="sxs-lookup"><span data-stu-id="c6126-449">SAP System number</span></span>|  
    |<span data-ttu-id="c6126-450">SAPInlineUserName</span><span class="sxs-lookup"><span data-stu-id="c6126-450">SAPInlineUserName</span></span>|<span data-ttu-id="c6126-451">\<指定されたユーザー ></span><span class="sxs-lookup"><span data-stu-id="c6126-451">\<User Specified></span></span>|<span data-ttu-id="c6126-452">SAP バックエンドへの接続に使用するユーザー名。</span><span class="sxs-lookup"><span data-stu-id="c6126-452">The user name used to connect to the SAP back-end</span></span>|  
    |<span data-ttu-id="c6126-453">SAPInlinePassword</span><span class="sxs-lookup"><span data-stu-id="c6126-453">SAPInlinePassword</span></span>|<span data-ttu-id="c6126-454">\<指定されたユーザー ></span><span class="sxs-lookup"><span data-stu-id="c6126-454">\<User Specified></span></span>|<span data-ttu-id="c6126-455">SAP バックエンドへの接続に使用するパスワード。</span><span class="sxs-lookup"><span data-stu-id="c6126-455">The password used to connect to the SAP back-end</span></span>|  
    |<span data-ttu-id="c6126-456">PendingTransactionsAdapterTimeout</span><span class="sxs-lookup"><span data-stu-id="c6126-456">PendingTransactionsAdapterTimeout</span></span>|<span data-ttu-id="c6126-457">20000</span><span class="sxs-lookup"><span data-stu-id="c6126-457">20000</span></span>|<span data-ttu-id="c6126-458">Pending Transactions サーバーに対する要求の最大タイムアウト (ミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="c6126-458">Max timeout (millisecond) for a request to the Pending Transactions server</span></span>|  
    |<span data-ttu-id="c6126-459">PendingTransactionsInlineTimeout</span><span class="sxs-lookup"><span data-stu-id="c6126-459">PendingTransactionsInlineTimeout</span></span>|<span data-ttu-id="c6126-460">20000</span><span class="sxs-lookup"><span data-stu-id="c6126-460">20000</span></span>|<span data-ttu-id="c6126-461">Pending Transactions サーバーに対する要求の最大タイムアウト (ミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="c6126-461">Max timeout (millisecond) for a request to the Pending Transactions server</span></span>|  
    |<span data-ttu-id="c6126-462">PendingTransactionsInlineURL</span><span class="sxs-lookup"><span data-stu-id="c6126-462">PendingTransactionsInlineURL</span></span>|<span data-ttu-id="c6126-463">https://\<*コンピューター名*>/Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions/PendTransWS.asmx</span><span class="sxs-lookup"><span data-stu-id="c6126-463">https://\<*your computer name*>/Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactions/PendTransWS.asmx</span></span>|<span data-ttu-id="c6126-464">Pending Transactions サービスの URL。</span><span class="sxs-lookup"><span data-stu-id="c6126-464">URL of the Pending Transactions service.</span></span> <span data-ttu-id="c6126-465">\<*コンピューター名*> と一致する必要があります、**共通名**証明書の要求を作成するには」の手順でします。</span><span class="sxs-lookup"><span data-stu-id="c6126-465">\<*Your computer name*> must match the **common name** in the procedure "To create a certificate request".</span></span> <span data-ttu-id="c6126-466">"Localhost"を使用する必要がありますいない\<*コンピューター名*>。</span><span class="sxs-lookup"><span data-stu-id="c6126-466">You must not use "localhost" for \<*Your computer name*>.</span></span>|  
    |<span data-ttu-id="c6126-467">PendingTransactionsInlineSSOAffiliateApp</span><span class="sxs-lookup"><span data-stu-id="c6126-467">PendingTransactionsInlineSSOAffiliateApp</span></span>|<span data-ttu-id="c6126-468">WoodgroveBank.PendingTransactions</span><span class="sxs-lookup"><span data-stu-id="c6126-468">WoodgroveBank.PendingTransactions</span></span>|<span data-ttu-id="c6126-469">Pending Transactions SSO アプリケーション名。</span><span class="sxs-lookup"><span data-stu-id="c6126-469">Pending Transactions SSO application name</span></span>|  
    |<span data-ttu-id="c6126-470">PaymentTrackingAdapterTimeout</span><span class="sxs-lookup"><span data-stu-id="c6126-470">PaymentTrackingAdapterTimeout</span></span>|<span data-ttu-id="c6126-471">20000</span><span class="sxs-lookup"><span data-stu-id="c6126-471">20000</span></span>|<span data-ttu-id="c6126-472">Payment Tracking システムに対する要求の最大タイムアウト (ミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="c6126-472">Max timeout (millisecond) for a request to the Payment Tracking system</span></span>|  
    |<span data-ttu-id="c6126-473">PaymentTrackingInlineTimeout</span><span class="sxs-lookup"><span data-stu-id="c6126-473">PaymentTrackingInlineTimeout</span></span>|<span data-ttu-id="c6126-474">20000</span><span class="sxs-lookup"><span data-stu-id="c6126-474">20000</span></span>|<span data-ttu-id="c6126-475">Payment Tracking システムに対する要求の最大タイムアウト (ミリ秒)。</span><span class="sxs-lookup"><span data-stu-id="c6126-475">Max timeout (millisecond) for a request to the Payment Tracking system</span></span>|  
    |<span data-ttu-id="c6126-476">PaymentTrackingInlineQManager</span><span class="sxs-lookup"><span data-stu-id="c6126-476">PaymentTrackingInlineQManager</span></span>|<span data-ttu-id="c6126-477">\<ユーザー指定 > (通常 qm _\<*コンピューター名*>)。</span><span class="sxs-lookup"><span data-stu-id="c6126-477">\<User Specified> (Typically QM_\<*your computer name*>).</span></span>|<span data-ttu-id="c6126-478">MQSeries キュー マネージャーの名前。</span><span class="sxs-lookup"><span data-stu-id="c6126-478">MQSeries Queue Manager name</span></span>|  
    |<span data-ttu-id="c6126-479">PaymentTrackingInlineMQChannelDefinition</span><span class="sxs-lookup"><span data-stu-id="c6126-479">PaymentTrackingInlineMQChannelDefinition</span></span>|<span data-ttu-id="c6126-480">" " (二重引用符を 2 つ入力してください)</span><span class="sxs-lookup"><span data-stu-id="c6126-480">" " (need to enter the two double quotes).</span></span>|<span data-ttu-id="c6126-481">ローカルの場合は空の文字列。または、リモート MQ サーバーのフォーマットされたチャネル名。</span><span class="sxs-lookup"><span data-stu-id="c6126-481">Empty string if local, or formatted channel name of the remote MQ server.</span></span> <span data-ttu-id="c6126-482">IBM WebSphere MQ を構成するすべての既定の設定を保持する場合、チャネル定義になる時\<*コンピューター名*>/tcp/\<*コンピューター名*> (1414) です。</span><span class="sxs-lookup"><span data-stu-id="c6126-482">If you keep all default settings in configuring IBM WebSphere MQ, the channel definition will be S__\<*your computer name*>/TCP/\<*your computer name*>(1414).</span></span>|  
    |<span data-ttu-id="c6126-483">PaymentTrackingInlineRequestQueue</span><span class="sxs-lookup"><span data-stu-id="c6126-483">PaymentTrackingInlineRequestQueue</span></span>|<span data-ttu-id="c6126-484">LastPaymentsInputQueue</span><span class="sxs-lookup"><span data-stu-id="c6126-484">LastPaymentsInputQueue</span></span>|<span data-ttu-id="c6126-485">Payment Tracking 要求用の MQ キュー名。</span><span class="sxs-lookup"><span data-stu-id="c6126-485">The MQ Queue name for payment tracking requests</span></span>|  
    |<span data-ttu-id="c6126-486">PaymentTrackingInlineResponseQueue</span><span class="sxs-lookup"><span data-stu-id="c6126-486">PaymentTrackingInlineResponseQueue</span></span>|<span data-ttu-id="c6126-487">LastPaymentsOutputQueue</span><span class="sxs-lookup"><span data-stu-id="c6126-487">LastPaymentsOutputQueue</span></span>|<span data-ttu-id="c6126-488">Payment Tracking 応答用の MQ キュー名。</span><span class="sxs-lookup"><span data-stu-id="c6126-488">The MQ Queue name for payment tracking responses</span></span>|  
    |<span data-ttu-id="c6126-489">PaymentTrackingInlineSSOAffiliateApp</span><span class="sxs-lookup"><span data-stu-id="c6126-489">PaymentTrackingInlineSSOAffiliateApp</span></span>|<span data-ttu-id="c6126-490">WoodgroveBank.PaymentTracker</span><span class="sxs-lookup"><span data-stu-id="c6126-490">WoodgroveBank.PaymentTracker</span></span>|<span data-ttu-id="c6126-491">Payment Tracking SSO アプリケーション名。</span><span class="sxs-lookup"><span data-stu-id="c6126-491">Payment tracking SSO application name</span></span>|  
    |<span data-ttu-id="c6126-492">StubSAPWebServiceURL</span><span class="sxs-lookup"><span data-stu-id="c6126-492">StubSAPWebServiceURL</span></span>|<span data-ttu-id="c6126-493">http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP/StubSAPWS.asmx</span><span class="sxs-lookup"><span data-stu-id="c6126-493">http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubSAP/StubSAPWS.asmx</span></span>|<span data-ttu-id="c6126-494">Credit Limit SAP システムのスタブ Web サービス URL。</span><span class="sxs-lookup"><span data-stu-id="c6126-494">The stub Web service URL of the Credit Limit SAP system</span></span>|  
  
8.  <span data-ttu-id="c6126-495">コマンド プロンプトで次のコマンドを実行して、PATH 環境変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="c6126-495">At the command prompt, run the following command to set the PATH environment:</span></span>  
  
    -   `SET PATH=%PATH%;"%CommonProgramFiles%\Enterprise Single Sign-On"`  
  
9. <span data-ttu-id="c6126-496">コマンド プロンプトで CreateInitialConfigInSSO.cmd を実行します。</span><span class="sxs-lookup"><span data-stu-id="c6126-496">At the command prompt, run the CreateInitialConfigInSSO.cmd.</span></span> <span data-ttu-id="c6126-497">これは、SSO 関連アプリケーション、SSO 構成ストア アプリケーション、および関連アプリケーションのユーザー マッピングを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-497">It creates the SSO Affiliate Applications, the SSO configuration store application, and the user mappings for the affiliate applications.</span></span> <span data-ttu-id="c6126-498">その後で、SetConfigValuesInSSO.cmd が実行され、SSO 構成ストア アプリケーションに構成値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="c6126-498">Then, it executes the SetConfigValuesInSSO.cmd to store configuration values in the SSO configuration store application.</span></span>  
  
10. <span data-ttu-id="c6126-499">コマンド プロンプトで次のコマンドを実行して、Pending Transactions 関連アプリケーション用のユーザー資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="c6126-499">At the command prompt, run the following command to set the user credential for the Pending Transactions affiliate application.</span></span> <span data-ttu-id="c6126-500">使用して、 \< **DomainName**> と\< **UserID**> の PendTransUserMap.xml に定義されている、 \<WindowsDomain >\\<WindowsUserId\>です。</span><span class="sxs-lookup"><span data-stu-id="c6126-500">Use the \<**DomainName**> and \<**UserID**> defined in the PendTransUserMap.xml for the \<WindowsDomain>\\<WindowsUserId\>.</span></span> <span data-ttu-id="c6126-501">このコマンドでは、このチュートリアルで使用している外部ユーザー (UserID) のパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="c6126-501">This command asks you to enter the password of the external user, UserID, used in this walkthrough.</span></span>  
  
    -   `ssomanage -setcredentials <WindowsDomain>\<WindowsUserId> WoodgroveBank.PendingTransactions`  
  
11. <span data-ttu-id="c6126-502">コマンド プロンプトで次のコマンドを実行して、Payment Tracker 関連アプリケーション用のユーザー資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="c6126-502">At the command prompt, run the following command to set the user credential for the Payment Tracker affiliate application.</span></span> <span data-ttu-id="c6126-503">使用して、 \< **DomainName**> と\< **UserID**> の PmntTrckUserMap.xml に定義されている、 \<WindowsDomain >\\< WindowsUserId\>.</span><span class="sxs-lookup"><span data-stu-id="c6126-503">Use the \<**DomainName**> and \<**UserID**> defined in the PmntTrckUserMap.xml for the \<WindowsDomain>\\<WindowsUserId\>.</span></span> <span data-ttu-id="c6126-504">このコマンドでは、このチュートリアルで使用している外部ユーザー (PTUserID) のパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="c6126-504">This command asks you to enter the password of the external user, PTUserID, used in this walkthrough.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-505">Payment Tracker シミュレーターは、外部ユーザー資格情報の検証を行いません。</span><span class="sxs-lookup"><span data-stu-id="c6126-505">The Payment Tracker simulator doesn't validate the external user credential.</span></span> <span data-ttu-id="c6126-506">PTUserID のパスワードとして任意の値を入力できます。</span><span class="sxs-lookup"><span data-stu-id="c6126-506">You can enter any password for the PTUserID.</span></span>  
  
    -   `ssomanage -setcredentials < WindowsDomain >\< WindowsUserId > WoodgroveBank.PaymentTracker`  
  
##  <span data-ttu-id="c6126-507"><a name="step19"></a>サービス指向ソリューションの BAM 定義ファイルを配置します。</span><span class="sxs-lookup"><span data-stu-id="c6126-507"><a name="step19"></a> Deploy the BAM definition file for the Service Oriented Solution</span></span>  
  
#### <a name="to-deploy-the-bam-definition-file-for-the-service-oriented-solution"></a><span data-ttu-id="c6126-508">サービス指向ソリューションの BAM 定義ファイルを展開するには</span><span class="sxs-lookup"><span data-stu-id="c6126-508">To deploy the BAM definition file for the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="c6126-509">コマンド プロンプトを開いて、次のコマンドを入力し、&lt;localizedText&gt;Enter&lt;/localizedText&gt; キーを押して、BAM ユーティリティを参照するためのパスを設定します。</span><span class="sxs-lookup"><span data-stu-id="c6126-509">Open a command prompt, type the following command, and then press ENTER to set the path to find the BAM utilities:</span></span>  
  
    -   <span data-ttu-id="c6126-510">SET PATH=%PATH%;[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking"</span><span class="sxs-lookup"><span data-stu-id="c6126-510">SET PATH=%PATH%;[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking"</span></span>  
  
2.  <span data-ttu-id="c6126-511">コマンド プロンプトで、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\BAM に変更し、次のコマンドを入力して &lt;localizedText&gt;Enter&lt;/localizedText&gt; キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c6126-511">At the command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln\BAM, type the following command, and then press ENTER:</span></span>  
  
    -   `bm deploy-all -DefinitionFile:ServiceLevelTracking.xml`  
  
##  <span data-ttu-id="c6126-512"><a name="step21"></a>配置サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="c6126-512"><a name="step21"></a> Deploy the Service Oriented Solution</span></span>  
  
#### <a name="to-edit-the-binding-files-for-the-service-oriented-solution"></a><span data-ttu-id="c6126-513">サービス指向ソリューションのバインド ファイルを編集するには</span><span class="sxs-lookup"><span data-stu-id="c6126-513">To edit the binding files for the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="c6126-514">コマンド プロンプトで、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更します。次に、メモ帳を使用して Deployallbinding.xml を開き、次のように編集します。</span><span class="sxs-lookup"><span data-stu-id="c6126-514">At a command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder, open the Deployallbinding.xml using Notepad, and then make the following edits:</span></span>  
  
    -   <span data-ttu-id="c6126-515">SET MGMT_DB_SERVER のサーバー名および MBMT_DB を、BizTalk Server が使用するサーバー名およびデータベースに変更します。</span><span class="sxs-lookup"><span data-stu-id="c6126-515">Change the name of the server in the SET MGMT_DB_SERVER and MBMT_DB to the name of the server and database that BizTalk Server is using.</span></span>  
  
    -   <span data-ttu-id="c6126-516">SOLNDIR 変数の値を "%BTSSolutionsPath%\SO\BTSSoln" に変更します。</span><span class="sxs-lookup"><span data-stu-id="c6126-516">Change the value of the SOLNDIR variable to "%BTSSolutionsPath%\SO\BTSSoln".</span></span>  
  
2.  <span data-ttu-id="c6126-517">コマンド プロンプトで、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Bindings フォルダーに変更します。</span><span class="sxs-lookup"><span data-stu-id="c6126-517">At a command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Bindings folder.</span></span>  
  
3.  <span data-ttu-id="c6126-518">アダプター バージョンの場合は、メモ帳を使用して AdapterSOAOrchBindings.xml を開き、次のように編集します。</span><span class="sxs-lookup"><span data-stu-id="c6126-518">For the adapter version, open the AdapterSOAOrchBindings.xml using Notepad, and then edit as follows:</span></span>  
  
    -   <span data-ttu-id="c6126-519">__MQ_SERVER_NAME のすべての出現を置換\_\_ MQSeries サーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="c6126-519">Replace all occurrences of __MQ_SERVER_NAME\_\_ with the MQSeries Server name.</span></span>  
  
    -   <span data-ttu-id="c6126-520">__MQ_QMANAGER_NAME のすべての出現を置換\_\_ MQSeries キュー マネージャ名。</span><span class="sxs-lookup"><span data-stu-id="c6126-520">Replace all occurrences of __MQ_QMANAGER_NAME\_\_ with the MQSeries Queue Manager name.</span></span>  
  
    -   <span data-ttu-id="c6126-521">__PT_WS_SERVER_NAME のすべての出現を置換\_\_文字列で"\<アドレス > https://\__PT_WS_SERVER_NAME\_\_"は、サーバー名、保留中のトランザクションWeb サービスを展開します。</span><span class="sxs-lookup"><span data-stu-id="c6126-521">Replace all occurrences of __PT_WS_SERVER_NAME\_\_ in the string "\<Address>https://\__PT_WS_SERVER_NAME\_\_" with the server name where the Pending Transactions Web service is deployed.</span></span> <span data-ttu-id="c6126-522">サーバー名が一致する必要があります、**共通名**の手順で、"Web サーバーの SSL の構成"です。</span><span class="sxs-lookup"><span data-stu-id="c6126-522">The server name must match the **common name** in the step, "To configure the Web server for SSL".</span></span> <span data-ttu-id="c6126-523">localhost を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="c6126-523">You shouldn't use localhost.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-524">バインド ファイル AdapterSOAOrchBindings.xml はスタブ Web サービスを、</span><span class="sxs-lookup"><span data-stu-id="c6126-524">The binding file, AdapterSOAOrchBindings.xml, uses the stub Web service for:</span></span>  
    >   
    >  1.  <span data-ttu-id="c6126-525">Credit Limit バックエンド SAP システム</span><span class="sxs-lookup"><span data-stu-id="c6126-525">The Credit Limit back-end SAP system.</span></span>  
    > 2.  <span data-ttu-id="c6126-526">Payment Tracking バックエンド システムとの統合を行う MQSeries アダプター</span><span class="sxs-lookup"><span data-stu-id="c6126-526">The MQSeries adapter to integrate with the Payment Tracking back-end system.</span></span>  
    > 3.  <span data-ttu-id="c6126-527">HIS TI .NET コンポーネントを呼び出してメインフレーム バックエンド システムとの統合を行う Pending Transactions Web サービスとして使用します。</span><span class="sxs-lookup"><span data-stu-id="c6126-527">The Pending Transactions Web service to call the HIS TI .NET component to integrate with the mainframe back-end system.</span></span>  
    >   
    >  <span data-ttu-id="c6126-528">メインフレームを使用しない場合は、スタブ Web サービスを使用して Pending Transactions システム用のデータを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6126-528">If you aren’t using the mainframe, you must use the stub Web service to generate data for the Pending Transactions system.</span></span>  
  
4.  <span data-ttu-id="c6126-529">インライン バージョンの場合は、メモ帳を使用して InlineSOAOrchBindings.xml を開き、次のように編集します。</span><span class="sxs-lookup"><span data-stu-id="c6126-529">For the inline version, open the InlineSOAOrchBindings.xml using Notepad, and then edit as follows:</span></span>  
  
    -   <span data-ttu-id="c6126-530">__MQ_SERVER_NAME のすべての出現を置換\_\_ MQSeries サーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="c6126-530">Replace all occurrences of __MQ_SERVER_NAME\_\_ with the MQSeries Server name.</span></span>  
  
    -   <span data-ttu-id="c6126-531">__MQ_QMANAGER_NAME のすべての出現を置換\_\_ MQSeries キュー マネージャ名。</span><span class="sxs-lookup"><span data-stu-id="c6126-531">Replace all occurrences of __MQ_QMANAGER_NAME\_\_ with the MQSeries Queue Manager name.</span></span>  
  
#### <a name="to-deploy-the-service-oriented-solution"></a><span data-ttu-id="c6126-532">サービス指向ソリューションを展開するには</span><span class="sxs-lookup"><span data-stu-id="c6126-532">To deploy the Service Oriented solution</span></span>  
  
-   <span data-ttu-id="c6126-533">コマンド プロンプトで、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更し、次のコマンドを入力して &lt;localizedText&gt;Enter&lt;/localizedText&gt; キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c6126-533">At a command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder, type the following command, and then press ENTER.</span></span>  
  
    -   `Deployallbinding.cmd`  
  
    > [!NOTE]
    >  <span data-ttu-id="c6126-534">Deployallbinding.cmd を実行すると、BTSScn.SO.CustomerService という名前の BizTalk アプリケーションが作成され、アダプター バージョンおよびインライン バージョン用のバインド ファイルがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="c6126-534">The Deployallbinding.cmd creates the BizTalk application named BTSScn.SO.CustomerService and imports binding files for the adapter and inline versions.</span></span>  
  
##  <span data-ttu-id="c6126-535"><a name="step23"></a>メインフレームが利用できない場合は、スタブ Pending Transactions Web サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-535"><a name="step23"></a> Configure the stub Pending Transactions Web Services when a mainframe is not available</span></span>  
  
#### <a name="to-configure-the-stub-pending-transactions-web-service-for-using-the-adapter-version-without-a-mainframe"></a><span data-ttu-id="c6126-536">スタブ Pending Transactions Web サービスを構成するには (メインフレームを使用せず、アダプター バージョンを使用する場合)</span><span class="sxs-lookup"><span data-stu-id="c6126-536">To configure the stub Pending Transactions Web service (for using the adapter version without a mainframe)</span></span>  
  
1.  <span data-ttu-id="c6126-537">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**を右クリックし、**既定の Web サイト**、 をポイント**新規**とをクリックして**仮想ディレクトリ**を実行する**仮想ディレクトリの作成ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-537">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
     <span data-ttu-id="c6126-538">使用して、**仮想ディレクトリの作成ウィザード**、スタブ Pending Transactions Web サービス アダプター バージョン用の次の仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-538">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for stub Pending Transactions Web service for the adapter version:</span></span>  
  
     <span data-ttu-id="c6126-539">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions</span><span class="sxs-lookup"><span data-stu-id="c6126-539">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions</span></span>  
  
     <span data-ttu-id="c6126-540">パス = \< *BizTalk インストール ディレクトリ*> \SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans</span><span class="sxs-lookup"><span data-stu-id="c6126-540">PATH = \<*BizTalk Install Directory*>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans</span></span>  
  
     <span data-ttu-id="c6126-541">Access Permissions = Read, Run scripts</span><span class="sxs-lookup"><span data-stu-id="c6126-541">Access Permissions = Read, Run scripts</span></span>  
  
2.  <span data-ttu-id="c6126-542">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**、展開、**既定の Web サイト**を右クリックしてMicrosoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions をクリックして**プロパティ**、し、次のようを使用して設定を変更、**プロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="c6126-542">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions, click **Properties**, and then modify the settings as follows using the **Properties** dialog box.</span></span>  
  
    1.  <span data-ttu-id="c6126-543">**仮想ディレクトリ** タブで、設定、**アプリケーション プール**に\< *YourAppPool*> 向けの IIS の仮想ディレクトリを作成するには」の手順で作成します。ソリューション"です。</span><span class="sxs-lookup"><span data-stu-id="c6126-543">In the **Virtual directory** tab, set the **Application Pool** to \<*YourAppPool*> you created in the step, "To create the virtual directories in IIS for the solution".</span></span>  
  
    2.  <span data-ttu-id="c6126-544">**ディレクトリ セキュリティ**] タブで、をクリックして**編集**で、**認証とアクセス制御**ボックスで、グループ化し、[ **への匿名アクセスを有効にします。**.</span><span class="sxs-lookup"><span data-stu-id="c6126-544">In the **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, and then select **Enable anonymous access**.</span></span> <span data-ttu-id="c6126-545">をクリックして**OK**を終了します。</span><span class="sxs-lookup"><span data-stu-id="c6126-545">Click **OK** to exit.</span></span>  
  
3.  <span data-ttu-id="c6126-546">**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、[btsscn.so.customerservice] を展開し、**送信ポート**を右クリックして**[pendingtransactionsolicitresponseport]**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-546">In the **BizTalk Server Administration Console**, expand **BizTalk Group**, expand **Applications**, expand BTSScn.SO.CustomerService, expand **Send Ports**, right-click **PendingTransactionSolicitResponsePort**, and then click **Properties**.</span></span>  
  
    1.  <span data-ttu-id="c6126-547">**全般** ページで、をクリックして**構成**を表示する、**トランスポートのプロパティ** ダイアログ ボックスし、変更、 **Web サービス URL**にスタブ Pending Transaction Web サービスをたとえば。</span><span class="sxs-lookup"><span data-stu-id="c6126-547">In the **General** page, click **Configure** to display the **Transport Properties** dialog box, and then modify the **Web Service URL** to the stub Pending Transaction Web service, for example:</span></span>  
  
         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions/StubPendTransWS.asmx`  
  
    2.  <span data-ttu-id="c6126-548">すべてのダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c6126-548">Close all of the dialog boxes.</span></span>  
  
#### <a name="to-configure-the-stub-pending-transactions-web-service-for-using-the-inline-version-without-a-mainframe"></a><span data-ttu-id="c6126-549">スタブ Pending Transactions Web サービスを構成するには (メインフレームを使用せず、インライン バージョンを使用する場合)</span><span class="sxs-lookup"><span data-stu-id="c6126-549">To configure the stub Pending Transactions Web service (for using the inline version without a mainframe)</span></span>  
  
1.  <span data-ttu-id="c6126-550">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**を右クリックし、**既定の Web サイト**、 をポイント**新規**とをクリックして**仮想ディレクトリ**を実行する**仮想ディレクトリの作成ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="c6126-550">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, right-click the **Default Web Site**, point to **New**, and then click **Virtual Directory** to run **Virtual Directory Creation Wizard**.</span></span>  
  
     <span data-ttu-id="c6126-551">使用して、**仮想ディレクトリの作成ウィザード**、スタブ Pending Transactions Web サービス アダプター バージョン用の次の仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6126-551">Using the **Virtual Directory Creation Wizard**, create the following virtual directory for stub Pending Transactions Web service for the adapter version:</span></span>  
  
     <span data-ttu-id="c6126-552">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions</span><span class="sxs-lookup"><span data-stu-id="c6126-552">Alias = Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions</span></span>  
  
     <span data-ttu-id="c6126-553">パス = \< *BizTalk インストール ディレクトリ*> \SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans</span><span class="sxs-lookup"><span data-stu-id="c6126-553">PATH = \<*BizTalk Install Directory*>\SDK\Scenarios\SO\BTSSoln\StubWebServices\PendingTrans</span></span>  
  
     <span data-ttu-id="c6126-554">Access Permissions = Read, Run scripts</span><span class="sxs-lookup"><span data-stu-id="c6126-554">Access Permissions = Read, Run scripts</span></span>  
  
2.  <span data-ttu-id="c6126-555">**インターネット インフォメーション サービス (IIS) マネージャー**、展開**Websites**、展開、**既定の Web サイト**を右クリックしてMicrosoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions をクリックして**プロパティ**、し、次のように設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="c6126-555">In the **Internet Information Services (IIS) Manager**, expand **Web Sites**, expand the **Default Web Site**, right-click Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions, click **Properties**, and then modify the settings as follows:</span></span>  
  
    1.  <span data-ttu-id="c6126-556">**仮想ディレクトリ** タブで、設定、**アプリケーション プール**に\< *YourAppPool*> 向けの IIS の仮想ディレクトリを作成するには」の手順で作成します。ソリューション"です。</span><span class="sxs-lookup"><span data-stu-id="c6126-556">In the **Virtual directory** tab, set the **Application Pool** to \<*YourAppPool*> you created in the step, "To create the virtual directories in IIS for the solution".</span></span>  
  
    2.  <span data-ttu-id="c6126-557">**ディレクトリ セキュリティ**] タブで、をクリックして**編集**で、**認証とアクセス制御**ボックスで、グループ化し、[ **への匿名アクセスを有効にします。**.</span><span class="sxs-lookup"><span data-stu-id="c6126-557">In the **Directory Security** tab, click **Edit** in the **Authentication and access control** group box, and then select **Enable anonymous access**.</span></span> <span data-ttu-id="c6126-558">をクリックして**OK**を終了します。</span><span class="sxs-lookup"><span data-stu-id="c6126-558">Click **OK** to exit.</span></span>  
  
3.  <span data-ttu-id="c6126-559">コマンド プロンプトを開いて、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更します。</span><span class="sxs-lookup"><span data-stu-id="c6126-559">Open a command prompt, and then change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder.</span></span>  
  
4.  <span data-ttu-id="c6126-560">コマンド プロンプトで、メモ帳を使用して SetConfigValuesInSSO.cmd ファイルを開きの値を設定、 **PendingTransactionsInlineURL**スタブ Pending Transaction Web サービスの URL にします。</span><span class="sxs-lookup"><span data-stu-id="c6126-560">At the command prompt, open the SetConfigValuesInSSO.cmd file using Notepad, and then set the value of the **PendingTransactionsInlineURL** to the URL of the stub Pending Transaction Web Service.</span></span>  
  
    -   `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.StubPendingTransactions/StubPendTransWS.asmx`  
  
5.  <span data-ttu-id="c6126-561">コマンド プロンプトで「`SetConfigValuesInSSO.cmd`」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c6126-561">At the command prompt, type `SetConfigValuesInSSO.cmd`, and then press ENTER.</span></span>  
  
##  <span data-ttu-id="c6126-562"><a name="step25"></a>開始、サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="c6126-562"><a name="step25"></a> Start the Service Oriented Solution</span></span>  
  
#### <a name="to-start-the-service-oriented-solution"></a><span data-ttu-id="c6126-563">サービス指向ソリューションを開始するには</span><span class="sxs-lookup"><span data-stu-id="c6126-563">To start the Service Oriented Solution</span></span>  
  
1.  <span data-ttu-id="c6126-564">コマンド プロンプトを開き、ディレクトリを %BTSSolutionsPath%\SO\BTSSoln\Scripts フォルダーに変更して、次のコマンドを入力し Enter キーを押します。これにより、インライン バージョンおよびアダプター バージョン用のすべてのオーケストレーションが開始されます。</span><span class="sxs-lookup"><span data-stu-id="c6126-564">Open a command prompt, change the directory to the %BTSSolutionsPath%\SO\BTSSoln\Scripts folder, type the following command, and then press ENTER to start all orchestrations for the inline and adapter versions.</span></span>  
  
    -   `startAll.vbs`  
  
2.  <span data-ttu-id="c6126-565">サービス指向ソリューションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c6126-565">Run the service-oriented solution.</span></span> <span data-ttu-id="c6126-566">ソリューションの実行の詳細については、次を参照してください。[サービス指向ソリューションの実行方法](../core/how-to-run-the-service-oriented-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="c6126-566">For more information about running the solution, see [How to Run the Service Oriented Solution](../core/how-to-run-the-service-oriented-solution.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c6126-567">次の手順</span><span class="sxs-lookup"><span data-stu-id="c6126-567">Next Steps</span></span>  
 <span data-ttu-id="c6126-568">サービス指向ソリューションのインライン バージョンおよびアダプター バージョンをテストする[サービス指向ソリューションの実行方法](../core/how-to-run-the-service-oriented-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="c6126-568">You test the inline and adapter version of the service-oriented solution in [How to Run the Service Oriented Solution](../core/how-to-run-the-service-oriented-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6126-569">参照</span><span class="sxs-lookup"><span data-stu-id="c6126-569">See Also</span></span>  
 <span data-ttu-id="c6126-570">[サービス指向ソリューションをインストールする前に](../core/before-installing-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="c6126-570">[Before Installing the Service Oriented Solution](../core/before-installing-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="c6126-571">[指向ソリューションのスタブ バージョンのサービスをインストールする方法](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="c6126-571">[How to Install the Stub Version of the Service Oriented Solution](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="c6126-572">開発者のコンピュータ設定、サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="c6126-572">Developer Machine Setup for the Service Oriented Solution</span></span>](../core/developer-machine-setup-for-the-service-oriented-solution.md)