---
title: "ビジネス プロセス管理ソリューションをインストールする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- installing, examples
- process management solution tutorial, installing
- process management solution tutorial, deployment prerequisites
ms.assetid: 930f3bb1-05e6-4b02-852d-6139aaf341f0
caps.latest.revision: "61"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22b16e8c33dfdbf44b000cc9a048e86a5869d616
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-install-the-business-process-management-solution"></a><span data-ttu-id="99715-102">ビジネス プロセス管理ソリューションのインストール方法</span><span class="sxs-lookup"><span data-stu-id="99715-102">How to Install the Business Process Management Solution</span></span>
<span data-ttu-id="99715-103">次の手順では、ビジネス プロセス管理 (BPM) ソリューションをコンピューターにインストールするための準備方法と、このコンピューターにソリューションをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="99715-103">The following steps describe how to prepare the computer for installing the Business Process Management (BPM) solution, and how to install the solution on this computer.</span></span>  
  
-   [<span data-ttu-id="99715-104">ビジネス プロセス管理ソリューションをインストールするコンピューターを準備します。</span><span class="sxs-lookup"><span data-stu-id="99715-104">Prepare the computer for installing the Business Process Management Solution</span></span>](#step1)  
  
     <span data-ttu-id="99715-105">準備手順では、受信ポートと送信ポートによって使用される SQL データベース、フォルダー、およびキューを作成します。</span><span class="sxs-lookup"><span data-stu-id="99715-105">In the preparation step, you create the folders, queues, and SQL database that will be used by the receive and send ports.</span></span> <span data-ttu-id="99715-106">また、クライアント アプリケーションである CSRWebApp および OrderBroker プロキシ Web サービスに使用する 2 つの仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="99715-106">You also create the two virtual directories for the client application, CSRWebApp, and the OrderBroker proxy Web Service.</span></span>  
  
-   [<span data-ttu-id="99715-107">ビジネス プロセス管理ソリューションをインストールするのには、コンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="99715-107">Configure the computer for installing the Business Process Management Solution</span></span>](#step3)  
  
-   [<span data-ttu-id="99715-108">ビジネス プロセス管理ソリューションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="99715-108">Install the Business Process Management Solution</span></span>](#step5)  
  
> [!NOTE]
>  <span data-ttu-id="99715-109">ソリューションを展開するには、いくつかのバッチ ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="99715-109">You will run some batch files to deploy the solution.</span></span> <span data-ttu-id="99715-110">スクリプトが正常終了したことを確認できるように、バッチ ファイルの出力をテキスト ファイルにリダイレクトすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="99715-110">We recommend that you redirect the output of the batch files to a text file to verify that the script completed successfully.</span></span>  
  
##  <span data-ttu-id="99715-111"><a name="step1"></a>ビジネス プロセス管理ソリューションをインストールするコンピューターを準備します。</span><span class="sxs-lookup"><span data-stu-id="99715-111"><a name="step1"></a> Prepare the computer for installing the Business Process Management Solution</span></span>  
  
#### <a name="to-prepare-the-computer-for-installing-the-business-process-management-solution"></a><span data-ttu-id="99715-112">ビジネス プロセス管理ソリューションをコンピューターにインストールするための準備を行うには</span><span class="sxs-lookup"><span data-stu-id="99715-112">To prepare the computer for installing the Business Process Management Solution</span></span>  
  
1.  <span data-ttu-id="99715-113">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリック**Services**です。</span><span class="sxs-lookup"><span data-stu-id="99715-113">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span> <span data-ttu-id="99715-114">使用して、 **Services**コンソールで、次のサービスが実行されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="99715-114">Using the **Services** console, make sure that the following services are running:</span></span>  
  
    -   <span data-ttu-id="99715-115">**FTP 発行**</span><span class="sxs-lookup"><span data-stu-id="99715-115">**FTP Publishing**</span></span>  
  
    -   <span data-ttu-id="99715-116">**メッセージ キュー**</span><span class="sxs-lookup"><span data-stu-id="99715-116">**Message Queuing**</span></span>  
  
    -   <span data-ttu-id="99715-117">**World Wide Web 発行**</span><span class="sxs-lookup"><span data-stu-id="99715-117">**World Wide Web Publishing**</span></span>  
  
2.  <span data-ttu-id="99715-118">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、 をクリックして**コンピューターの管理**コンソール、および追加し、ローカルの Administrators グループに BizTalk サービス アカウント。</span><span class="sxs-lookup"><span data-stu-id="99715-118">Click **Start**, point to **All Programs**, point to **Administrative Tools**, click **Computer Management** console, and then add the BizTalk service account to the local Administrators group.</span></span>  
  
3.  <span data-ttu-id="99715-119">Windows SharePoint Services をインストールした場合は、(ルート) を除外する、**既定の Web サイト**Windows SharePoint Services 管理パスから次のようにします をクリック**開始**、 をポイント**すべてのプログラム。**、指す**管理ツール**、順にクリック**SharePoint サーバーの全体管理**です。</span><span class="sxs-lookup"><span data-stu-id="99715-119">If you installed Windows SharePoint Services, exclude the (root) of the **Default Web Site** from Windows SharePoint Services Managed Paths as follows: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
    1.  <span data-ttu-id="99715-120">**仮想サーバーの構成****仮想サーバーの設定を構成する**です。</span><span class="sxs-lookup"><span data-stu-id="99715-120">Under **Virtual Server Configuration**, select **Configure virtual server settings**.</span></span>  
  
    2.  <span data-ttu-id="99715-121">**仮想サーバーのリスト**] ページで [**既定の Web サイト**です。</span><span class="sxs-lookup"><span data-stu-id="99715-121">On the **Virtual Server List** page, click **Default Web Site**.</span></span>  
  
    3.  <span data-ttu-id="99715-122">**仮想サーバーの設定**] ページで [**管理パスの定義**です。</span><span class="sxs-lookup"><span data-stu-id="99715-122">On the **Virtual Server Settings** page, click **Define managed paths**.</span></span>  
  
    4.  <span data-ttu-id="99715-123">**インクルード パス**のセクションで、**管理パスの定義** ページで、**ルート** をクリックし、**選択したパスの削除**です。</span><span class="sxs-lookup"><span data-stu-id="99715-123">In the **Included Paths** section of the **Defined Managed Path** page, select **Root** and then click **Remove selected paths**.</span></span>  
  
    5.  <span data-ttu-id="99715-124">コマンド プロンプトで IISReset コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="99715-124">At a command prompt, perform an IISReset.</span></span>  
  
##  <span data-ttu-id="99715-125"><a name="step3"></a>ビジネス プロセス管理ソリューションをインストールするのには、コンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="99715-125"><a name="step3"></a> Configure the computer for installing the Business Process Management Solution</span></span>  
  
#### <a name="to-configure-the-computer-for-installing-the-business-process-management-solution"></a><span data-ttu-id="99715-126">ビジネス プロセス管理ソリューションをコンピューターにインストールするための構成を行うには</span><span class="sxs-lookup"><span data-stu-id="99715-126">To configure the computer for installing the Business Process Management Solution</span></span>  
  
1.  <span data-ttu-id="99715-127">コンピュータからログオフして、BizTalk サービス アカウントを使用してコンピュータにログオンします。</span><span class="sxs-lookup"><span data-stu-id="99715-127">Log off the computer, and then log on to the computer as the BizTalk service account.</span></span>  
  
2.  <span data-ttu-id="99715-128">コマンド プロンプトを開き、次のコマンドを入力して Enter キーを押し、%BTSSolutionsPath% 環境変数に E2E ソリューションのベース フォルダーを設定します。</span><span class="sxs-lookup"><span data-stu-id="99715-128">Open a command prompt, type the following command, and then press ENTER to set the %BTSSolutionsPath% environment variable to indicate the base folder for the E2E solutions.</span></span> <span data-ttu-id="99715-129">次に、コマンド プロンプトを終了します。</span><span class="sxs-lookup"><span data-stu-id="99715-129">Then, exit the command prompt.</span></span>  
  
    -   `setx BTSSolutionsPath "%ProgramFiles%\Microsoft BizTalk Server 2009\SDK\Scenarios"`  
  
        > [!NOTE]
        >  <span data-ttu-id="99715-130">64 ビット コンピューターを使用する場合は、「%ProgramFiles%」の代わりに「%ProgramFiles%(x86)」と入力してください。</span><span class="sxs-lookup"><span data-stu-id="99715-130">If you are using a 64-bit computer, use %ProgramFiles(x86)% instead of %ProgramFiles%.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="99715-131">SETX コマンドの詳細については、Microsoft TechNet Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831)です。</span><span class="sxs-lookup"><span data-stu-id="99715-131">For more information about the SETX command, see the Microsoft TechNet Web site at [http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831).</span></span>  
  
3.  <span data-ttu-id="99715-132">コマンド プロンプトを開き、現在のディレクトリを %BTSSolutionsPath%\BPM\HistoryDB フォルダーに型に変更`CreateDatabase.cmd`、履歴データベースを作成するには ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="99715-132">Open a command prompt, change the current directory to %BTSSolutionsPath%\BPM\HistoryDB folder, type `CreateDatabase.cmd`, and press ENTER to create the history database.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="99715-133">SQL 送信アダプターのハンドラーとして指定されたホストを実行するユーザーには、SouthridgeVideoHistory データベースのストアド プロシージャを実行する権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="99715-133">The user running the host specified as the handler for the SQL send adapter must have permissions to execute stored procedures on the SouthridgeVideoHistory database.</span></span>  
  
4.  <span data-ttu-id="99715-134">コマンド プロンプトで次のコマンドを実行し、既定のスクリプト ホストを CScript.exe に変更します。</span><span class="sxs-lookup"><span data-stu-id="99715-134">At a command prompt, run the following command to change the default script host to CScript.exe</span></span>  
  
    -   `CScript /H:CScript`  
  
5.  <span data-ttu-id="99715-135">コマンド プロンプトで、次のコマンドを実行して、CSRWebApp Web アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="99715-135">At a command prompt, run the following command to create the CSRWebApp Web application</span></span>  
  
    -   `iisvdir /create "Default Web Site" CSRWebApp "%BTSSolutionsPath%\BPM\CSRWebApp"`  
  
        > [!NOTE]
        >  <span data-ttu-id="99715-136">Iisvdir.vbs の詳細については、Microsoft TechNet Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=67830](http://go.microsoft.com/fwlink/?LinkId=67830)です。</span><span class="sxs-lookup"><span data-stu-id="99715-136">For more information about iisvdir.vbs, see the Microsoft TechNet Web site at [http://go.microsoft.com/fwlink/?LinkId=67830](http://go.microsoft.com/fwlink/?LinkId=67830).</span></span>  
  
6.  <span data-ttu-id="99715-137">コマンド プロンプトで、次のコマンドを実行し、OrderBroker_Proxy の新しい IIS 仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="99715-137">At a command prompt, run the following command to create a new IIS virtual directory for OrderBroker_Proxy.</span></span>  
  
    -   `iisvdir /create "Default Web Site" BTSScn.BPM.OrderBroker_Proxy "%BTSSolutionsPath%\BPM\OrderBroker_Proxy"`  
  
    > [!NOTE]
    >  <span data-ttu-id="99715-138">Web アプリケーションは、インターネット インフォメーション サービス (IIS) マネージャーを使用して作成することができます。</span><span class="sxs-lookup"><span data-stu-id="99715-138">You can use Internet Information Services (IIS) Manager to create the Web Application.</span></span> <span data-ttu-id="99715-139">IIS 7.0 でアプリケーションを作成する方法の詳細については、マニュアルを参照して、IIS 7.0 で[http://go.microsoft.com/fwlink/?LinkId=59263](http://go.microsoft.com/fwlink/?LinkId=59263)です。</span><span class="sxs-lookup"><span data-stu-id="99715-139">For more information about how to create applications in IIS 7.0, see the IIS 7.0 Documentation at [http://go.microsoft.com/fwlink/?LinkId=59263](http://go.microsoft.com/fwlink/?LinkId=59263).</span></span>  
  
7.  <span data-ttu-id="99715-140">新しい IIS アプリケーション プールを作成し、次のように、BizTalk 分離ホスト ユーザー グループと IIS_WPG グループのメンバーであるユーザーとしてその id を設定します。</span><span class="sxs-lookup"><span data-stu-id="99715-140">Create a new IIS application pool and set its identity as a user that is a member of the BizTalk Isolated Host Users group and the IIS_WPG group, as follows:</span></span>  
  
    1.  <span data-ttu-id="99715-141">インターネット インフォメーション サービス (IIS) マネージャーを右クリックして**アプリケーション プール****新規**、し、**アプリケーション プール**です。</span><span class="sxs-lookup"><span data-stu-id="99715-141">In Internet Information Services (IIS) Manager, right-click **Application Pools**, select **New**, and then select **Application Pool**.</span></span>  
  
    2.  <span data-ttu-id="99715-142">型、**アプリケーション プール ID** (任意の値)、をクリックし、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="99715-142">Type the **Application pool ID** (any value), and then click **OK**.</span></span>  
  
    3.  <span data-ttu-id="99715-143">アプリケーション プールを選択し、作成したを右クリックして**詳細設定**です。</span><span class="sxs-lookup"><span data-stu-id="99715-143">Right-click the application pool that you created, and then select **Advanced Settings**.</span></span>  
  
    4.  <span data-ttu-id="99715-144">展開**プロセス モデル**、右側の列をクリックして、 **Identity**に設定して、をクリック**しています.**</span><span class="sxs-lookup"><span data-stu-id="99715-144">Expand **Process Model**, click in the right-column for the **Identity** setting, and then click **…**</span></span>  
  
    5.  <span data-ttu-id="99715-145">ユーザー アカウントを選択 (どちらか、**ビルドでアカウント**または**カスタム アカウント**) を作成し、windows \temp ディレクトリにファイルを実行するアクセス許可を持ちます。</span><span class="sxs-lookup"><span data-stu-id="99715-145">Select a user account (either a **Build-in account** or **Custom account** ) that has permissions to create and execute files in the Windows\Temp directory.</span></span> <span data-ttu-id="99715-146">BizTalk を構成した際に、BizTalk 分離ホスト ユーザー グループに追加されるユーザーに対して、これらの権限が設定されています。</span><span class="sxs-lookup"><span data-stu-id="99715-146">When you configured BizTalk, the configuration process already set these permissions for the user it added to the BizTalk Isolated Host Users group.</span></span> <span data-ttu-id="99715-147">したがって、望ましいのは、同じユーザーを指定することです。</span><span class="sxs-lookup"><span data-stu-id="99715-147">Specifying the same user is a good choice.</span></span>  
  
8.  <span data-ttu-id="99715-148">インターネット インフォメーション サービス (IIS) マネージャーでは、展開**Websites**、展開**既定の Web サイト**を右クリックして**BTSScn.BPM.OrderBroker_Proxy** をポイント**アプリケーションの管理**、クリックして**詳細設定**です。</span><span class="sxs-lookup"><span data-stu-id="99715-148">In Internet Information Services (IIS) Manager, expand **Web Sites**, expand **Default Web Site**, right-click **BTSScn.BPM.OrderBroker_Proxy**, point to **Manage Application**, and then click **Advanced Settings**.</span></span>  
  
9. <span data-ttu-id="99715-149">設定**アプリケーション プール**前の手順で作成したアプリケーション プールにします。</span><span class="sxs-lookup"><span data-stu-id="99715-149">Set **Application Pool** to the application pool that you  created in the previous step.</span></span>  
  
10. <span data-ttu-id="99715-150">前の 2 つの手順を繰り返します、 **CSRWebApp**アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="99715-150">Repeat the previous two steps for the **CSRWebApp** application.</span></span>  
  
11. <span data-ttu-id="99715-151">これらの変更が直ちに有効になるように、IIS をリセットします。</span><span class="sxs-lookup"><span data-stu-id="99715-151">Reset IIS to make sure all these changes take effect immediately.</span></span> <span data-ttu-id="99715-152">これを行うには、実行**iisreset**コマンド プロンプトでします。</span><span class="sxs-lookup"><span data-stu-id="99715-152">To do this, run **iisreset** at a command prompt.</span></span>  
  
12. <span data-ttu-id="99715-153">コマンド プロンプトで、現在のフォルダーを %btssolutionspath%\bpm\scripts、型に変更`CreateQueues.vbs`、し、enter キーを押して次のプライベート キューを作成します。</span><span class="sxs-lookup"><span data-stu-id="99715-153">At a command prompt, change the current folder to the %BTSSolutionsPath%\BPM\Scripts, type `CreateQueues.vbs`, and then press ENTER to create the following private queues.</span></span>  
  
    |<span data-ttu-id="99715-154">名前</span><span class="sxs-lookup"><span data-stu-id="99715-154">Name</span></span>|<span data-ttu-id="99715-155">トランザクション</span><span class="sxs-lookup"><span data-stu-id="99715-155">Transactional</span></span>|<span data-ttu-id="99715-156">トランザクション プロトコル</span><span class="sxs-lookup"><span data-stu-id="99715-156">Transaction protocol</span></span>|  
    |----------|-------------------|--------------------------|  
    |<span data-ttu-id="99715-157">ToFacilitiesQ</span><span class="sxs-lookup"><span data-stu-id="99715-157">ToFacilitiesQ</span></span>|<span data-ttu-id="99715-158">はい</span><span class="sxs-lookup"><span data-stu-id="99715-158">Yes</span></span>|<span data-ttu-id="99715-159">ネイティブ</span><span class="sxs-lookup"><span data-stu-id="99715-159">Native</span></span>|  
    |<span data-ttu-id="99715-160">FromFacilitiesQ</span><span class="sxs-lookup"><span data-stu-id="99715-160">FromFacilitiesQ</span></span>|<span data-ttu-id="99715-161">はい</span><span class="sxs-lookup"><span data-stu-id="99715-161">Yes</span></span>|<span data-ttu-id="99715-162">ネイティブ</span><span class="sxs-lookup"><span data-stu-id="99715-162">Native</span></span>|  
    |<span data-ttu-id="99715-163">FromFixedOrdersQ</span><span class="sxs-lookup"><span data-stu-id="99715-163">FromFixedOrdersQ</span></span>|<span data-ttu-id="99715-164">はい</span><span class="sxs-lookup"><span data-stu-id="99715-164">Yes</span></span>|<span data-ttu-id="99715-165">ネイティブ</span><span class="sxs-lookup"><span data-stu-id="99715-165">Native</span></span>|  
    |<span data-ttu-id="99715-166">ToServicingSystemQ</span><span class="sxs-lookup"><span data-stu-id="99715-166">ToServicingSystemQ</span></span>|<span data-ttu-id="99715-167">はい</span><span class="sxs-lookup"><span data-stu-id="99715-167">Yes</span></span>|<span data-ttu-id="99715-168">ネイティブ</span><span class="sxs-lookup"><span data-stu-id="99715-168">Native</span></span>|  
    |<span data-ttu-id="99715-169">ToCSRSystemQ</span><span class="sxs-lookup"><span data-stu-id="99715-169">ToCSRSystemQ</span></span>|<span data-ttu-id="99715-170">不可</span><span class="sxs-lookup"><span data-stu-id="99715-170">No</span></span>|<span data-ttu-id="99715-171">HTTP</span><span class="sxs-lookup"><span data-stu-id="99715-171">HTTP</span></span>|  
    |<span data-ttu-id="99715-172">ToVendorSystemQ</span><span class="sxs-lookup"><span data-stu-id="99715-172">ToVendorSystemQ</span></span>|<span data-ttu-id="99715-173">不可</span><span class="sxs-lookup"><span data-stu-id="99715-173">No</span></span>|<span data-ttu-id="99715-174">HTTP</span><span class="sxs-lookup"><span data-stu-id="99715-174">HTTP</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="99715-175">使用することができます**コンピューターの管理**スナップインで、キューを作成します。</span><span class="sxs-lookup"><span data-stu-id="99715-175">You can use **Computer Management** snap-in to create the queues.</span></span> <span data-ttu-id="99715-176">プライベート キューを作成する方法の詳細については、マニュアルを参照して、メッセージ キュー [http://go.microsoft.com/fwlink/?LinkId=59264](http://go.microsoft.com/fwlink/?LinkId=59264)です。</span><span class="sxs-lookup"><span data-stu-id="99715-176">For more information about how to create a private queue, see the Message Queuing documentation at [http://go.microsoft.com/fwlink/?LinkId=59264](http://go.microsoft.com/fwlink/?LinkId=59264).</span></span> <span data-ttu-id="99715-177">MSMQ 3.0 をインストールする方法の詳細については、マニュアルを参照して、メッセージ キュー [http://go.microsoft.com/fwlink/?LinkId=59265](http://go.microsoft.com/fwlink/?LinkId=59265)です。</span><span class="sxs-lookup"><span data-stu-id="99715-177">For more information about how to install MSMQ 3.0, see the Message Queuing documentation at [http://go.microsoft.com/fwlink/?LinkId=59265](http://go.microsoft.com/fwlink/?LinkId=59265).</span></span>  
  
13. <span data-ttu-id="99715-178">コマンド プロンプトで、現在のフォルダーを %btssolutionspath%\bpm\scripts、型に変更`CreateTestDirectories.cmd`、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="99715-178">At a command prompt, change the current folder to the %BTSSolutionsPath%\BPM\Scripts, type `CreateTestDirectories.cmd`, and then press ENTER.</span></span>  
  
    -   <span data-ttu-id="99715-179">次のフォルダーが %SystemDrive%\BPMTest フォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="99715-179">The following folders are crated in %SystemDrive%\BPMTest folder</span></span>  
  
         <span data-ttu-id="99715-180">CSRResponse-DSP</span><span class="sxs-lookup"><span data-stu-id="99715-180">CSRResponse-DSP</span></span>  
  
         <span data-ttu-id="99715-181">VendorResponse-DSP</span><span class="sxs-lookup"><span data-stu-id="99715-181">VendorResponse-DSP</span></span>  
  
         <span data-ttu-id="99715-182">OrderErrors-SP</span><span class="sxs-lookup"><span data-stu-id="99715-182">OrderErrors-SP</span></span>  
  
         <span data-ttu-id="99715-183">ErrorResponse-RP-TestRL</span><span class="sxs-lookup"><span data-stu-id="99715-183">ErrorResponse-RP-TestRL</span></span>  
  
         <span data-ttu-id="99715-184">Facilities-SP</span><span class="sxs-lookup"><span data-stu-id="99715-184">Facilities-SP</span></span>  
  
         <span data-ttu-id="99715-185">Facilities-RP-TestRL</span><span class="sxs-lookup"><span data-stu-id="99715-185">Facilities-RP-TestRL</span></span>  
  
         <span data-ttu-id="99715-186">HistoryInsert-SP</span><span class="sxs-lookup"><span data-stu-id="99715-186">HistoryInsert-SP</span></span>  
  
         <span data-ttu-id="99715-187">HistoryUpdate-SP</span><span class="sxs-lookup"><span data-stu-id="99715-187">HistoryUpdate-SP</span></span>  
  
         <span data-ttu-id="99715-188">Order-RP-TestRL</span><span class="sxs-lookup"><span data-stu-id="99715-188">Order-RP-TestRL</span></span>  
  
         <span data-ttu-id="99715-189">ServicingSystem-SP</span><span class="sxs-lookup"><span data-stu-id="99715-189">ServicingSystem-SP</span></span>  
  
         <span data-ttu-id="99715-190">Vendor-RP-TestRL</span><span class="sxs-lookup"><span data-stu-id="99715-190">Vendor-RP-TestRL</span></span>  
  
         <span data-ttu-id="99715-191">BizTalkErrors-SP</span><span class="sxs-lookup"><span data-stu-id="99715-191">BizTalkErrors-SP</span></span>  
  
    -   <span data-ttu-id="99715-192">FromVendor フォルダーは、%SystemDrive%\Inetpub\ftproot フォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="99715-192">FromVendor folder is created in the %SystemDrive%\Inetpub\ftproot folder.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="99715-193">Windows システムのインストール先が C ドライブでない場合は、%SystemDrive% を C: に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="99715-193">If the Windows system is not installed on the C drive, you should replace %SystemDrive% with C:.</span></span> <span data-ttu-id="99715-194">フォルダー名は、BPM ソリューションが提供するバインド ファイルのアドレスに一致させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="99715-194">You have to match the folder names to the address in the binding files that the BPM solution provides.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="99715-195">BizTalk サービス アカウントには、FromVendor フォルダーへの読み取り/書き込み権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="99715-195">The BizTalk service account must have read/write permission to the FromVendor folder.</span></span>  
  
##  <span data-ttu-id="99715-196"><a name="step5"></a>ビジネス プロセス管理ソリューションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="99715-196"><a name="step5"></a> Install the Business Process Management Solution</span></span>  
  
#### <a name="to-install-the-business-process-management-solution"></a><span data-ttu-id="99715-197">ビジネス プロセス管理ソリューションをインストールするには</span><span class="sxs-lookup"><span data-stu-id="99715-197">To install the Business Process Management Solution</span></span>  
  
1.  <span data-ttu-id="99715-198">コマンド プロンプトで、現在のフォルダーを %btssolutionspath%\bpm、型に変更`SetupBPM.bat`、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="99715-198">At a command prompt, change the current folder to %BTSSolutionsPath%\BPM, type `SetupBPM.bat`, and then press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="99715-199">ファイルに SetupBPM.bat を実行する前に**%BTSInstallPath%/SDK/Scenarios/BPM/CSDWebApp/App_WebReferences/SouthridgeVideo_OrderBroker/OrderBrokerOrch_OrderPort.wsdl**と**%BTSInstallPath%/SDK/Scenarios/BPM/OrderBroker_Proxy/App_Code/OrderBrokerOrch_OrderPort.asmx.cs**8f8bbebbb3fb375a のすべてのインスタンスを XXXXXXXXXXXXXXXX に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="99715-199">Before running SetupBPM.bat, in the files **%BTSInstallPath%/SDK/Scenarios/BPM/CSDWebApp/App_WebReferences/SouthridgeVideo_OrderBroker/OrderBrokerOrch_OrderPort.wsdl** and **%BTSInstallPath%/SDK/Scenarios/BPM/OrderBroker_Proxy/App_Code/OrderBrokerOrch_OrderPort.asmx.cs**, replace all instances of 8f8bbebbb3fb375a with XXXXXXXXXXXXXXXX.</span></span>  
  
     <span data-ttu-id="99715-200">SetupBPM.bat では、次のタスクが実行されます。</span><span class="sxs-lookup"><span data-stu-id="99715-200">The SetupBPM.bat performs the following tasks:</span></span>  
  
    1.  <span data-ttu-id="99715-201">BPM ソリューションのアセンブリに署名するための、一意の厳密な名前のキー (SNK) を作成します。</span><span class="sxs-lookup"><span data-stu-id="99715-201">Creates a unique strong name key (SNK) for signing the assemblies of the BPM Solution.</span></span>  
  
    2.  <span data-ttu-id="99715-202">SNK から公開キー トークンを抽出します。</span><span class="sxs-lookup"><span data-stu-id="99715-202">Extracts the public key token from the SNK.</span></span>  
  
    3.  <span data-ttu-id="99715-203">公開キー トークンを使用してバインド ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="99715-203">Updates the binding files with the public token.</span></span>  
  
    4.  <span data-ttu-id="99715-204">BPM ソリューションを作成し、OpsAdapter をインストールします。</span><span class="sxs-lookup"><span data-stu-id="99715-204">Builds the BPM solution, and installs OpsAdapter.</span></span>  
  
    5.  <span data-ttu-id="99715-205">%BTSSolutionsPath%\Common フォルダーに SSOApplicationConfig を作成します。</span><span class="sxs-lookup"><span data-stu-id="99715-205">Builds the SSOApplicationConfig in the %BTSSolutionsPath%\Common folder.</span></span>  
  
2.  <span data-ttu-id="99715-206">ビジネス ルール エンジン展開ウィザードを使用して、Southridge Video ビジネス ルールを展開します。</span><span class="sxs-lookup"><span data-stu-id="99715-206">Deploy the Southridge Video business rules using the Business Rule Engine Deployment Wizard:</span></span>  
  
    1.  <span data-ttu-id="99715-207">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**ビジネス ルール エンジン展開ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="99715-207">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rules Engine Deployment Wizard**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="99715-208">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="99715-208">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="99715-209">これを行うには、アプリケーションを右クリックし、**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="99715-209">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
    2.  <span data-ttu-id="99715-210">**ようこそ** ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="99715-210">On the **Welcome** page, click **Next**.</span></span>  
  
    3.  <span data-ttu-id="99715-211">**展開タスク**] ページで、[**インポート ポリシー/ボキャブラリをファイルからデータベースに発行し、**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="99715-211">On the **Deployment Task** page, select **Import and publish Policy/Vocabulary to database from file**, and then click **Next**.</span></span>  
  
    4.  <span data-ttu-id="99715-212">**ポリシー ストア** ページでその他のすべての設定の既定では、保持してクリックし、、**次**です。</span><span class="sxs-lookup"><span data-stu-id="99715-212">On the **Policy Store** page, keep all other default settings, and then click **Next**.</span></span>  
  
    5.  <span data-ttu-id="99715-213">**インポート ルール エンジン ポリシー/ボキャブラリ ファイル** ページで、をクリックして**参照**%BTSSolutionsPath%\BPM\Rules フォルダーの DecodeAndValidateOrderRules.xml ファイルを選択して、クリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="99715-213">On the **Import Rules Engine Policy/Vocabulary file** page, click **Browse**, select the DecodeAndValidateOrderRules.xml file in the %BTSSolutionsPath%\BPM\Rules folder, and then click **Next**.</span></span>  
  
    6.  <span data-ttu-id="99715-214">**準備ができて** ページで、をクリックして**次**、し、**ポリシー/ボキャブラリをインポートする** ページで、をクリックして**次へ**</span><span class="sxs-lookup"><span data-stu-id="99715-214">On the **Ready** page, click **Next**, and then on the **Importing Policy/Vocabulary** page, click **Next**</span></span>  
  
    7.  <span data-ttu-id="99715-215">[完了] ページで、**ウィザードを再実行**ウィザードを再度開き、をクリックする**完了**です。</span><span class="sxs-lookup"><span data-stu-id="99715-215">On the Completion page, select **Run the wizard again** to open the Wizard again, and then click **Finish**.</span></span>  
  
    8.  <span data-ttu-id="99715-216">**ようこそ** ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="99715-216">On the **Welcome** page, click **Next**.</span></span>  
  
    9. <span data-ttu-id="99715-217">**展開タスク**] ページで、[ **DeployPolicy**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="99715-217">On the **Deployment Task** page, select **DeployPolicy**, and then click **Next**.</span></span>  
  
    10. <span data-ttu-id="99715-218">**ポリシー ストア** ページでその他のすべての設定の既定では、保持してクリックし、、**次**です。</span><span class="sxs-lookup"><span data-stu-id="99715-218">On the **Policy Store** page, keep all other default settings, and then click **Next**.</span></span>  
  
    11. <span data-ttu-id="99715-219">**ポリシーの展開**] ページで、[ **DecodeAndValidateOrder 1.0**で、**ルール エンジン ポリシー**クリックしてドロップダウン リスト、**次**.</span><span class="sxs-lookup"><span data-stu-id="99715-219">On the **Deploy Policy** page, select **DecodeAndValidateOrder 1.0** in the **Rule Engine Policy** drop-down list, and then click **Next**.</span></span>  
  
    12. <span data-ttu-id="99715-220">**準備ができて** ページで、をクリックして**次**、し、**ポリシーの展開** ページで、をクリックして**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="99715-220">On the **Ready** page, click **Next**, and then on the **Deploying Policy** page, click **Next**.</span></span>  
  
    13. <span data-ttu-id="99715-221">[完了] ページで、をクリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="99715-221">On the Completion page, click **Finish**.</span></span>  
  
3.  <span data-ttu-id="99715-222">BPM ソリューションを 64 ビット コンピューターにインストールする場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="99715-222">If you install the BPM solution on a 64-bit computer, then</span></span>  
  
    1.  <span data-ttu-id="99715-223">フォローとして 32 ビット コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`%SYSTEMROOT%\SYSWOW64\CMD.EXE`、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="99715-223">Open a 32-bit command prompt as follow: Click **Start**, click **Run**, type `%SYSTEMROOT%\SYSWOW64\CMD.EXE`, and then press ENTER.</span></span>  
  
    2.  <span data-ttu-id="99715-224">32 ビット コマンド プロンプトで、ディレクトリを %BTSSolutionsPath%\BPM\Scripts フォルダーに変更します。</span><span class="sxs-lookup"><span data-stu-id="99715-224">At the 32-bit command prompt, change the directory to the %BTSSolutionsPath%\BPM\Scripts folder.</span></span>  
  
    3.  <span data-ttu-id="99715-225">メモ帳で CreateSouthridgeVideoApplication.cmd を開き、"%CommonProgramFiles%\Enterprise Single Sign-On\ssomanage.exe" を "%SystemDrive%\Program Files\Common Files\Enterprise Single Sign-On\ssomanage.exe" に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="99715-225">Using Notepad, open the CreateSouthridgeVideoApplication.cmd, and then replace "%CommonProgramFiles%\Enterprise Single Sign-On\ssomanage.exe" with "%SystemDrive%\Program Files\Common Files\Enterprise Single Sign-On\ssomanage.exe".</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="99715-226">32 ビット コマンド プロンプトでは、%CommonProgramFiles% 変数が "%ProgramFiles(x86)%\Common Files" に変わります。</span><span class="sxs-lookup"><span data-stu-id="99715-226">At a 32-bit command prompt, the %CommonProgramFiles% variable is changed to "%ProgramFiles(x86)%\Common Files".</span></span> <span data-ttu-id="99715-227">SSO 管理ユーティリティは 64 ビット コンピューターでも %ProgramFiles% にインストールされるので、パスを修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99715-227">Because the SSO administrative utility is installed in the %ProgramFiles% even on a 64-bit computer, you must fix the path.</span></span> <span data-ttu-id="99715-228">DeployBPM.cmd は、CreateSouthridgeVideoApplication.cmd を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="99715-228">The DeployBPM.cmd calls CreateSouthridgeVideoApplication.cmd.</span></span>  
  
    4.  <span data-ttu-id="99715-229">32 ビット コマンド プロンプトで、入力型`DeployBPM.cmd`、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="99715-229">At the 32-bit command prompt, type type `DeployBPM.cmd`, and then press ENTER.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="99715-230">DeployBPM.cmd は、32 ビット コマンド プロンプトで実行する必要があります。cscript.exe の x86 バージョンを必要とする x86 オブジェクトにアクセスする VB スクリプトが含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="99715-230">The DeployBPM.cmd must be run at a 32-bit command prompt because it includes the VB Script accessing x86 objects that requires the x86 version of cscript.exe.</span></span>  
  
4.  <span data-ttu-id="99715-231">コマンド プロンプトで、現在のフォルダーを %btssolutionspath%\bpm\scripts、型に変更`DeployBPM.cmd`、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="99715-231">At a command prompt, change the current folder to %BTSSolutionsPath%\BPM\Scripts, type `DeployBPM.cmd`, and then press ENTER.</span></span> <span data-ttu-id="99715-232">DeployBPM.cmd は、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="99715-232">The DeployBPM.cmd performs the following tasks:</span></span>  
  
    1.  <span data-ttu-id="99715-233">BPM ソリューションのための BizTalk アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="99715-233">Creates BizTalk Applications for the BPM Solution.</span></span>  
  
    2.  <span data-ttu-id="99715-234">アプリケーション間の参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="99715-234">Adds references between the applications.</span></span>  
  
    3.  <span data-ttu-id="99715-235">バインド ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="99715-235">Imports the binding files.</span></span>  
  
    4.  <span data-ttu-id="99715-236">BAM 定義ファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="99715-236">Deploys the BAM definition files.</span></span>  
  
    5.  <span data-ttu-id="99715-237">SouthridgeVideo イベント ソースを登録します。</span><span class="sxs-lookup"><span data-stu-id="99715-237">Registers the SouthridgeVideo event source.</span></span>  
  
    6.  <span data-ttu-id="99715-238">シングル サインオン (SSO) 関連アプリケーションを作成し、SSO アプリケーションの構成値を保存します。</span><span class="sxs-lookup"><span data-stu-id="99715-238">Creates a Single Sign-On (SSO) affiliated application, and saves configuration values to the SSO application.</span></span>  
  
5.  <span data-ttu-id="99715-239">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="99715-239">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
    1.  <span data-ttu-id="99715-240">**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BTSScn.BPM.OrderBrokerApp**、展開**受信場所**を右クリックして**仕入先-RL RP**、し、[プロパティ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99715-240">In the **BizTalk Server Administration Console**, expand **BizTalk Group**, expand **Applications**, expand **BTSScn.BPM.OrderBrokerApp**, expand **Receive Locations**, right-click **Vendor-RP-RL**, and then click Properties.</span></span>  
  
    2.  <span data-ttu-id="99715-241">**プロパティ**ダイアログ ボックスで、をクリックして**構成**、し、次の表として値を入力、**トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="99715-241">On the **Properties** dialog box, click **Configure**, and then enter values as the following table on the **Transport Properties** dialog box:</span></span>  
  
        |<span data-ttu-id="99715-242">プロパティ名</span><span class="sxs-lookup"><span data-stu-id="99715-242">Property Name</span></span>|<span data-ttu-id="99715-243">値</span><span class="sxs-lookup"><span data-stu-id="99715-243">Value</span></span>|  
        |-------------------|-----------|  
        |<span data-ttu-id="99715-244">**[サーバー]**</span><span class="sxs-lookup"><span data-stu-id="99715-244">**Server**</span></span>|`localhost`|  
        |<span data-ttu-id="99715-245">**[ユーザー名]**</span><span class="sxs-lookup"><span data-stu-id="99715-245">**User Name**</span></span>|<span data-ttu-id="99715-246">\<*BizTalk サービス アカウント名*></span><span class="sxs-lookup"><span data-stu-id="99715-246">\<*BizTalk service account name*></span></span>|  
        |<span data-ttu-id="99715-247">**Password**</span><span class="sxs-lookup"><span data-stu-id="99715-247">**Password**</span></span>|<span data-ttu-id="99715-248">\<*BizTalk サービス アカウントのパスワード*></span><span class="sxs-lookup"><span data-stu-id="99715-248">\<*BizTalk service account password*></span></span>|  
  
6.  <span data-ttu-id="99715-249">BPM ソリューションを実行します。</span><span class="sxs-lookup"><span data-stu-id="99715-249">Run the BPM Solution.</span></span> <span data-ttu-id="99715-250">ソリューションの実行の詳細については、次を参照してください。[ビジネス プロセス管理ソリューションを実行する方法](../core/how-to-run-the-business-process-management-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="99715-250">For more information about running the solution, see [How to Run the Business Process Management Solution](../core/how-to-run-the-business-process-management-solution.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="99715-251">次の手順</span><span class="sxs-lookup"><span data-stu-id="99715-251">Next Steps</span></span>  
 <span data-ttu-id="99715-252">ビジネス管理ソリューションがどのように動作するかをテストする[ビジネス プロセス管理ソリューションを実行する方法](../core/how-to-run-the-business-process-management-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="99715-252">You test how the Business Management Solution works in [How to Run the Business Process Management Solution](../core/how-to-run-the-business-process-management-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99715-253">参照</span><span class="sxs-lookup"><span data-stu-id="99715-253">See Also</span></span>  
 <span data-ttu-id="99715-254">[ビジネス プロセス管理ソリューションをインストールする前に](../core/before-installing-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="99715-254">[Before Installing the Business Process Management Solution](../core/before-installing-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="99715-255">ビジネス プロセス管理ソリューションの開発者のコンピュータ設定</span><span class="sxs-lookup"><span data-stu-id="99715-255">Developer Machine Setup for the Business Process Management Solution</span></span>](../core/developer-machine-setup-for-the-business-process-management-solution.md)