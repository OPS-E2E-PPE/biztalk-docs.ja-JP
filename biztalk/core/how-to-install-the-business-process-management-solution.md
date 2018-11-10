---
title: ビジネス プロセス管理ソリューションをインストールする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, examples
- process management solution tutorial, installing
- process management solution tutorial, deployment prerequisites
ms.assetid: 930f3bb1-05e6-4b02-852d-6139aaf341f0
caps.latest.revision: 61
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffb067c206018996bc48641bcd8211921b0294dd
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752523"
---
# <a name="how-to-install-the-business-process-management-solution"></a><span data-ttu-id="c3ff1-102">ビジネス プロセス管理ソリューションのインストール方法</span><span class="sxs-lookup"><span data-stu-id="c3ff1-102">How to Install the Business Process Management Solution</span></span>
<span data-ttu-id="c3ff1-103">次の手順では、ビジネス プロセス管理 (BPM) ソリューションをコンピューターにインストールするための準備方法と、このコンピューターにソリューションをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-103">The following steps describe how to prepare the computer for installing the Business Process Management (BPM) solution, and how to install the solution on this computer.</span></span>  
  
-   [<span data-ttu-id="c3ff1-104">ビジネス プロセス管理ソリューションをインストールするコンピューターを準備します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-104">Prepare the computer for installing the Business Process Management Solution</span></span>](#step1)  
  
     <span data-ttu-id="c3ff1-105">準備手順では、受信ポートと送信ポートによって使用される SQL データベース、フォルダー、およびキューを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-105">In the preparation step, you create the folders, queues, and SQL database that will be used by the receive and send ports.</span></span> <span data-ttu-id="c3ff1-106">また、クライアント アプリケーションである CSRWebApp および OrderBroker プロキシ Web サービスに使用する 2 つの仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-106">You also create the two virtual directories for the client application, CSRWebApp, and the OrderBroker proxy Web Service.</span></span>  
  
-   [<span data-ttu-id="c3ff1-107">ビジネス プロセス管理ソリューションをインストールするのには、コンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-107">Configure the computer for installing the Business Process Management Solution</span></span>](#step3)  
  
-   [<span data-ttu-id="c3ff1-108">ビジネス プロセス管理ソリューションのインストール</span><span class="sxs-lookup"><span data-stu-id="c3ff1-108">Install the Business Process Management Solution</span></span>](#step5)  
  
> [!NOTE]
>  <span data-ttu-id="c3ff1-109">ソリューションを展開するには、いくつかのバッチ ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-109">You will run some batch files to deploy the solution.</span></span> <span data-ttu-id="c3ff1-110">スクリプトが正常終了したことを確認できるように、バッチ ファイルの出力をテキスト ファイルにリダイレクトすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-110">We recommend that you redirect the output of the batch files to a text file to verify that the script completed successfully.</span></span>  
  
##  <a name="step1"></a> <span data-ttu-id="c3ff1-111">ビジネス プロセス管理ソリューションをインストールするコンピューターを準備します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-111">Prepare the computer for installing the Business Process Management Solution</span></span>  
  
#### <a name="to-prepare-the-computer-for-installing-the-business-process-management-solution"></a><span data-ttu-id="c3ff1-112">ビジネス プロセス管理ソリューションをコンピューターにインストールするための準備を行うには</span><span class="sxs-lookup"><span data-stu-id="c3ff1-112">To prepare the computer for installing the Business Process Management Solution</span></span>  
  
1.  <span data-ttu-id="c3ff1-113">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**サービス**します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-113">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span> <span data-ttu-id="c3ff1-114">使用して、**サービス**コンソールで、次のサービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-114">Using the **Services** console, make sure that the following services are running:</span></span>  
  
    -   <span data-ttu-id="c3ff1-115">**FTP 発行**</span><span class="sxs-lookup"><span data-stu-id="c3ff1-115">**FTP Publishing**</span></span>  
  
    -   <span data-ttu-id="c3ff1-116">**メッセージ キュー**</span><span class="sxs-lookup"><span data-stu-id="c3ff1-116">**Message Queuing**</span></span>  
  
    -   <span data-ttu-id="c3ff1-117">**World Wide Web の発行**</span><span class="sxs-lookup"><span data-stu-id="c3ff1-117">**World Wide Web Publishing**</span></span>  
  
2.  <span data-ttu-id="c3ff1-118">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、 をクリックして**コンピュータの管理**コンソール、および追加し、ローカルの Administrators グループに BizTalk サービス アカウント。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-118">Click **Start**, point to **All Programs**, point to **Administrative Tools**, click **Computer Management** console, and then add the BizTalk service account to the local Administrators group.</span></span>  
  
3.  <span data-ttu-id="c3ff1-119">Windows SharePoint Services をインストールした場合の (ルート) を除外する、**既定の Web サイト**Windows SharePoint Services 管理パスから次のようにします をクリック**開始**、 をポイント**すべてのプログラム。**、 をポイント**管理ツール**、 をクリックし、 **SharePoint Central Administration**します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-119">If you installed Windows SharePoint Services, exclude the (root) of the **Default Web Site** from Windows SharePoint Services Managed Paths as follows: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
    1.  <span data-ttu-id="c3ff1-120">**仮想サーバーの構成**、**仮想サーバー設定を構成**します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-120">Under **Virtual Server Configuration**, select **Configure virtual server settings**.</span></span>  
  
    2.  <span data-ttu-id="c3ff1-121">**仮想サーバーのリスト**] ページで [**既定の Web サイト**します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-121">On the **Virtual Server List** page, click **Default Web Site**.</span></span>  
  
    3.  <span data-ttu-id="c3ff1-122">**仮想サーバーの設定**] ページで [**管理パスの定義**します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-122">On the **Virtual Server Settings** page, click **Define managed paths**.</span></span>  
  
    4.  <span data-ttu-id="c3ff1-123">**インクルード パス**のセクション、**管理パスの定義**] ページで、[**ルート**順にクリックします**選択したパスの削除**します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-123">In the **Included Paths** section of the **Defined Managed Path** page, select **Root** and then click **Remove selected paths**.</span></span>  
  
    5.  <span data-ttu-id="c3ff1-124">コマンド プロンプトで IISReset コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-124">At a command prompt, perform an IISReset.</span></span>  
  
##  <a name="step3"></a> <span data-ttu-id="c3ff1-125">ビジネス プロセス管理ソリューションをインストールするのには、コンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-125">Configure the computer for installing the Business Process Management Solution</span></span>  
  
#### <a name="to-configure-the-computer-for-installing-the-business-process-management-solution"></a><span data-ttu-id="c3ff1-126">ビジネス プロセス管理ソリューションをコンピューターにインストールするための構成を行うには</span><span class="sxs-lookup"><span data-stu-id="c3ff1-126">To configure the computer for installing the Business Process Management Solution</span></span>  
  
1.  <span data-ttu-id="c3ff1-127">コンピュータからログオフして、BizTalk サービス アカウントを使用してコンピュータにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-127">Log off the computer, and then log on to the computer as the BizTalk service account.</span></span>  
  
2.  <span data-ttu-id="c3ff1-128">コマンド プロンプトを開き、次のコマンドを入力して Enter キーを押し、%BTSSolutionsPath% 環境変数に E2E ソリューションのベース フォルダーを設定します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-128">Open a command prompt, type the following command, and then press ENTER to set the %BTSSolutionsPath% environment variable to indicate the base folder for the E2E solutions.</span></span> <span data-ttu-id="c3ff1-129">次に、コマンド プロンプトを終了します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-129">Then, exit the command prompt.</span></span>  
  
    -   `setx BTSSolutionsPath "%ProgramFiles%\Microsoft BizTalk Server 2009\SDK\Scenarios"`  
  
        > [!NOTE]
        >  <span data-ttu-id="c3ff1-130">64 ビット コンピューターを使用する場合は、「%ProgramFiles%」の代わりに「%ProgramFiles%(x86)」と入力してください。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-130">If you are using a 64-bit computer, use %ProgramFiles(x86)% instead of %ProgramFiles%.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c3ff1-131">SETX コマンドの詳細については、Microsoft TechNet Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831)します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-131">For more information about the SETX command, see the Microsoft TechNet Web site at [http://go.microsoft.com/fwlink/?LinkId=67831](http://go.microsoft.com/fwlink/?LinkId=67831).</span></span>  
  
3.  <span data-ttu-id="c3ff1-132">コマンド プロンプトを開き、現在のディレクトリを %BTSSolutionsPath%\BPM\HistoryDB フォルダーに型に変更`CreateDatabase.cmd`、履歴データベースを作成するには ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-132">Open a command prompt, change the current directory to %BTSSolutionsPath%\BPM\HistoryDB folder, type `CreateDatabase.cmd`, and press ENTER to create the history database.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c3ff1-133">SQL 送信アダプターのハンドラーとして指定されたホストを実行するユーザーには、SouthridgeVideoHistory データベースのストアド プロシージャを実行する権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-133">The user running the host specified as the handler for the SQL send adapter must have permissions to execute stored procedures on the SouthridgeVideoHistory database.</span></span>  
  
4.  <span data-ttu-id="c3ff1-134">コマンド プロンプトで次のコマンドを実行し、既定のスクリプト ホストを CScript.exe に変更します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-134">At a command prompt, run the following command to change the default script host to CScript.exe</span></span>  
  
    -   `CScript /H:CScript`  
  
5.  <span data-ttu-id="c3ff1-135">コマンド プロンプトで、次のコマンドを実行して、CSRWebApp Web アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-135">At a command prompt, run the following command to create the CSRWebApp Web application</span></span>  
  
    -   `iisvdir /create "Default Web Site" CSRWebApp "%BTSSolutionsPath%\BPM\CSRWebApp"`  
  
        > [!NOTE]
        >  <span data-ttu-id="c3ff1-136">Iisvdir.vbs の詳細については、Microsoft TechNet Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=67830](http://go.microsoft.com/fwlink/?LinkId=67830)します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-136">For more information about iisvdir.vbs, see the Microsoft TechNet Web site at [http://go.microsoft.com/fwlink/?LinkId=67830](http://go.microsoft.com/fwlink/?LinkId=67830).</span></span>  
  
6.  <span data-ttu-id="c3ff1-137">コマンド プロンプトで、次のコマンドを実行し、OrderBroker_Proxy の新しい IIS 仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-137">At a command prompt, run the following command to create a new IIS virtual directory for OrderBroker_Proxy.</span></span>  
  
    -   `iisvdir /create "Default Web Site" BTSScn.BPM.OrderBroker_Proxy "%BTSSolutionsPath%\BPM\OrderBroker_Proxy"`  
  
    > [!NOTE]
    >  <span data-ttu-id="c3ff1-138">Web アプリケーションは、インターネット インフォメーション サービス (IIS) マネージャーを使用して作成することができます。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-138">You can use Internet Information Services (IIS) Manager to create the Web Application.</span></span> <span data-ttu-id="c3ff1-139">IIS 7.0 でアプリケーションを作成する方法の詳細については、IIS 7.0 ドキュメントを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=59263](http://go.microsoft.com/fwlink/?LinkId=59263)します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-139">For more information about how to create applications in IIS 7.0, see the IIS 7.0 Documentation at [http://go.microsoft.com/fwlink/?LinkId=59263](http://go.microsoft.com/fwlink/?LinkId=59263).</span></span>  
  
7.  <span data-ttu-id="c3ff1-140">新しい IIS アプリケーション プールを作成し、次のように、BizTalk 分離ホスト ユーザー グループと IIS_WPG グループのメンバーであるユーザーとしてその id を設定します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-140">Create a new IIS application pool and set its identity as a user that is a member of the BizTalk Isolated Host Users group and the IIS_WPG group, as follows:</span></span>  
  
    1.  <span data-ttu-id="c3ff1-141">インターネット インフォメーション サービス (IIS) マネージャーで、右クリックして**アプリケーション プール**を選択します**新規**、し、**アプリケーション プール**します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-141">In Internet Information Services (IIS) Manager, right-click **Application Pools**, select **New**, and then select **Application Pool**.</span></span>  
  
    2.  <span data-ttu-id="c3ff1-142">型、**アプリケーション プール ID** (任意の値)、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-142">Type the **Application pool ID** (any value), and then click **OK**.</span></span>  
  
    3.  <span data-ttu-id="c3ff1-143">アプリケーション プールを選択し、作成したを右クリックして**詳細設定**します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-143">Right-click the application pool that you created, and then select **Advanced Settings**.</span></span>  
  
    4.  <span data-ttu-id="c3ff1-144">展開**プロセス モデル**、右側の列をクリックして、 **Identity**を設定して、クリックして **.**</span><span class="sxs-lookup"><span data-stu-id="c3ff1-144">Expand **Process Model**, click in the right-column for the **Identity** setting, and then click **…**</span></span>  
  
    5.  <span data-ttu-id="c3ff1-145">ユーザー アカウントを選択します (いずれかを**ビルトイン アカウント**または**カスタム アカウント**) を作成して、windows \temp ディレクトリにファイルを実行する権限を持っています。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-145">Select a user account (either a **Build-in account** or **Custom account** ) that has permissions to create and execute files in the Windows\Temp directory.</span></span> <span data-ttu-id="c3ff1-146">BizTalk を構成した際に、BizTalk 分離ホスト ユーザー グループに追加されるユーザーに対して、これらの権限が設定されています。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-146">When you configured BizTalk, the configuration process already set these permissions for the user it added to the BizTalk Isolated Host Users group.</span></span> <span data-ttu-id="c3ff1-147">したがって、望ましいのは、同じユーザーを指定することです。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-147">Specifying the same user is a good choice.</span></span>  
  
8.  <span data-ttu-id="c3ff1-148">インターネット インフォメーション サービス (IIS) マネージャーで、展開**Websites**、展開**既定の Web サイト**を右クリックして**BTSScn.BPM.OrderBroker_Proxy** をポイント**アプリケーションの管理**、 をクリックし、**詳細設定**します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-148">In Internet Information Services (IIS) Manager, expand **Web Sites**, expand **Default Web Site**, right-click **BTSScn.BPM.OrderBroker_Proxy**, point to **Manage Application**, and then click **Advanced Settings**.</span></span>  
  
9. <span data-ttu-id="c3ff1-149">設定**アプリケーション プール**前の手順で作成したアプリケーション プールにします。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-149">Set **Application Pool** to the application pool that you  created in the previous step.</span></span>  
  
10. <span data-ttu-id="c3ff1-150">前の 2 つの手順を繰り返して、 **CSRWebApp**アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-150">Repeat the previous two steps for the **CSRWebApp** application.</span></span>  
  
11. <span data-ttu-id="c3ff1-151">これらの変更が直ちに有効になるように、IIS をリセットします。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-151">Reset IIS to make sure all these changes take effect immediately.</span></span> <span data-ttu-id="c3ff1-152">これを行うには、次のように実行します。 **iisreset**コマンド プロンプトでします。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-152">To do this, run **iisreset** at a command prompt.</span></span>  
  
12. <span data-ttu-id="c3ff1-153">コマンド プロンプトで、現在のフォルダーを %btssolutionspath%\bpm\scripts、型に変更`CreateQueues.vbs`、し、次のプライベート キューを作成するには ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-153">At a command prompt, change the current folder to the %BTSSolutionsPath%\BPM\Scripts, type `CreateQueues.vbs`, and then press ENTER to create the following private queues.</span></span>  
  
    |<span data-ttu-id="c3ff1-154">名前</span><span class="sxs-lookup"><span data-stu-id="c3ff1-154">Name</span></span>|<span data-ttu-id="c3ff1-155">トランザクション</span><span class="sxs-lookup"><span data-stu-id="c3ff1-155">Transactional</span></span>|<span data-ttu-id="c3ff1-156">トランザクション プロトコル</span><span class="sxs-lookup"><span data-stu-id="c3ff1-156">Transaction protocol</span></span>|  
    |----------|-------------------|--------------------------|  
    |<span data-ttu-id="c3ff1-157">ToFacilitiesQ</span><span class="sxs-lookup"><span data-stu-id="c3ff1-157">ToFacilitiesQ</span></span>|<span data-ttu-id="c3ff1-158">はい</span><span class="sxs-lookup"><span data-stu-id="c3ff1-158">Yes</span></span>|<span data-ttu-id="c3ff1-159">ネイティブ</span><span class="sxs-lookup"><span data-stu-id="c3ff1-159">Native</span></span>|  
    |<span data-ttu-id="c3ff1-160">FromFacilitiesQ</span><span class="sxs-lookup"><span data-stu-id="c3ff1-160">FromFacilitiesQ</span></span>|<span data-ttu-id="c3ff1-161">はい</span><span class="sxs-lookup"><span data-stu-id="c3ff1-161">Yes</span></span>|<span data-ttu-id="c3ff1-162">ネイティブ</span><span class="sxs-lookup"><span data-stu-id="c3ff1-162">Native</span></span>|  
    |<span data-ttu-id="c3ff1-163">FromFixedOrdersQ</span><span class="sxs-lookup"><span data-stu-id="c3ff1-163">FromFixedOrdersQ</span></span>|<span data-ttu-id="c3ff1-164">はい</span><span class="sxs-lookup"><span data-stu-id="c3ff1-164">Yes</span></span>|<span data-ttu-id="c3ff1-165">ネイティブ</span><span class="sxs-lookup"><span data-stu-id="c3ff1-165">Native</span></span>|  
    |<span data-ttu-id="c3ff1-166">ToServicingSystemQ</span><span class="sxs-lookup"><span data-stu-id="c3ff1-166">ToServicingSystemQ</span></span>|<span data-ttu-id="c3ff1-167">はい</span><span class="sxs-lookup"><span data-stu-id="c3ff1-167">Yes</span></span>|<span data-ttu-id="c3ff1-168">ネイティブ</span><span class="sxs-lookup"><span data-stu-id="c3ff1-168">Native</span></span>|  
    |<span data-ttu-id="c3ff1-169">ToCSRSystemQ</span><span class="sxs-lookup"><span data-stu-id="c3ff1-169">ToCSRSystemQ</span></span>|<span data-ttu-id="c3ff1-170">いいえ</span><span class="sxs-lookup"><span data-stu-id="c3ff1-170">No</span></span>|<span data-ttu-id="c3ff1-171">HTTP</span><span class="sxs-lookup"><span data-stu-id="c3ff1-171">HTTP</span></span>|  
    |<span data-ttu-id="c3ff1-172">ToVendorSystemQ</span><span class="sxs-lookup"><span data-stu-id="c3ff1-172">ToVendorSystemQ</span></span>|<span data-ttu-id="c3ff1-173">いいえ</span><span class="sxs-lookup"><span data-stu-id="c3ff1-173">No</span></span>|<span data-ttu-id="c3ff1-174">HTTP</span><span class="sxs-lookup"><span data-stu-id="c3ff1-174">HTTP</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="c3ff1-175">使用することができます**コンピュータの管理**スナップインで、キューを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-175">You can use **Computer Management** snap-in to create the queues.</span></span> <span data-ttu-id="c3ff1-176">プライベート キューを作成する方法の詳細については、メッセージ キュー ドキュメントを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=59264](http://go.microsoft.com/fwlink/?LinkId=59264)します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-176">For more information about how to create a private queue, see the Message Queuing documentation at [http://go.microsoft.com/fwlink/?LinkId=59264](http://go.microsoft.com/fwlink/?LinkId=59264).</span></span> <span data-ttu-id="c3ff1-177">MSMQ 3.0 をインストールする方法の詳細については、メッセージ キュー ドキュメントを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=59265](http://go.microsoft.com/fwlink/?LinkId=59265)します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-177">For more information about how to install MSMQ 3.0, see the Message Queuing documentation at [http://go.microsoft.com/fwlink/?LinkId=59265](http://go.microsoft.com/fwlink/?LinkId=59265).</span></span>  
  
13. <span data-ttu-id="c3ff1-178">コマンド プロンプトで、現在のフォルダーを %btssolutionspath%\bpm\scripts、型に変更`CreateTestDirectories.cmd`、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-178">At a command prompt, change the current folder to the %BTSSolutionsPath%\BPM\Scripts, type `CreateTestDirectories.cmd`, and then press ENTER.</span></span>  
  
    -   <span data-ttu-id="c3ff1-179">次のフォルダーが %SystemDrive%\BPMTest フォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-179">The following folders are crated in %SystemDrive%\BPMTest folder</span></span>  
  
         <span data-ttu-id="c3ff1-180">CSRResponse-DSP</span><span class="sxs-lookup"><span data-stu-id="c3ff1-180">CSRResponse-DSP</span></span>  
  
         <span data-ttu-id="c3ff1-181">VendorResponse-DSP</span><span class="sxs-lookup"><span data-stu-id="c3ff1-181">VendorResponse-DSP</span></span>  
  
         <span data-ttu-id="c3ff1-182">OrderErrors-SP</span><span class="sxs-lookup"><span data-stu-id="c3ff1-182">OrderErrors-SP</span></span>  
  
         <span data-ttu-id="c3ff1-183">ErrorResponse-RP-TestRL</span><span class="sxs-lookup"><span data-stu-id="c3ff1-183">ErrorResponse-RP-TestRL</span></span>  
  
         <span data-ttu-id="c3ff1-184">Facilities-SP</span><span class="sxs-lookup"><span data-stu-id="c3ff1-184">Facilities-SP</span></span>  
  
         <span data-ttu-id="c3ff1-185">Facilities-RP-TestRL</span><span class="sxs-lookup"><span data-stu-id="c3ff1-185">Facilities-RP-TestRL</span></span>  
  
         <span data-ttu-id="c3ff1-186">HistoryInsert-SP</span><span class="sxs-lookup"><span data-stu-id="c3ff1-186">HistoryInsert-SP</span></span>  
  
         <span data-ttu-id="c3ff1-187">HistoryUpdate-SP</span><span class="sxs-lookup"><span data-stu-id="c3ff1-187">HistoryUpdate-SP</span></span>  
  
         <span data-ttu-id="c3ff1-188">Order-RP-TestRL</span><span class="sxs-lookup"><span data-stu-id="c3ff1-188">Order-RP-TestRL</span></span>  
  
         <span data-ttu-id="c3ff1-189">ServicingSystem-SP</span><span class="sxs-lookup"><span data-stu-id="c3ff1-189">ServicingSystem-SP</span></span>  
  
         <span data-ttu-id="c3ff1-190">Vendor-RP-TestRL</span><span class="sxs-lookup"><span data-stu-id="c3ff1-190">Vendor-RP-TestRL</span></span>  
  
         <span data-ttu-id="c3ff1-191">BizTalkErrors-SP</span><span class="sxs-lookup"><span data-stu-id="c3ff1-191">BizTalkErrors-SP</span></span>  
  
    -   <span data-ttu-id="c3ff1-192">FromVendor フォルダーは、%SystemDrive%\Inetpub\ftproot フォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-192">FromVendor folder is created in the %SystemDrive%\Inetpub\ftproot folder.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c3ff1-193">Windows システムのインストール先が C ドライブでない場合は、%SystemDrive% を C: に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-193">If the Windows system is not installed on the C drive, you should replace %SystemDrive% with C:.</span></span> <span data-ttu-id="c3ff1-194">フォルダー名は、BPM ソリューションが提供するバインド ファイルのアドレスに一致させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-194">You have to match the folder names to the address in the binding files that the BPM solution provides.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c3ff1-195">BizTalk サービス アカウントには、FromVendor フォルダーへの読み取り/書き込み権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-195">The BizTalk service account must have read/write permission to the FromVendor folder.</span></span>  
  
##  <a name="step5"></a> <span data-ttu-id="c3ff1-196">ビジネス プロセス管理ソリューションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-196">Install the Business Process Management Solution</span></span>  
  
#### <a name="to-install-the-business-process-management-solution"></a><span data-ttu-id="c3ff1-197">ビジネス プロセス管理ソリューションをインストールするには</span><span class="sxs-lookup"><span data-stu-id="c3ff1-197">To install the Business Process Management Solution</span></span>  
  
1. <span data-ttu-id="c3ff1-198">コマンド プロンプトで、現在のフォルダーを %btssolutionspath%\bpm、型に変更`SetupBPM.bat`、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-198">At a command prompt, change the current folder to %BTSSolutionsPath%\BPM, type `SetupBPM.bat`, and then press ENTER.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c3ff1-199">SetupBPM.bat ファイルを実行する前に **%BTSInstallPath%/SDK/Scenarios/BPM/CSDWebApp/App_WebReferences/SouthridgeVideo_OrderBroker/OrderBrokerOrch_OrderPort.wsdl**と **%BTSInstallPath%/SDK/Scenarios/BPM/OrderBroker_Proxy/App_Code/OrderBrokerOrch_OrderPort.asmx.cs**8f8bbebbb3fb375a のすべてのインスタンスを XXXXXXXXXXXXXXXX に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-199">Before running SetupBPM.bat, in the files **%BTSInstallPath%/SDK/Scenarios/BPM/CSDWebApp/App_WebReferences/SouthridgeVideo_OrderBroker/OrderBrokerOrch_OrderPort.wsdl** and **%BTSInstallPath%/SDK/Scenarios/BPM/OrderBroker_Proxy/App_Code/OrderBrokerOrch_OrderPort.asmx.cs**, replace all instances of 8f8bbebbb3fb375a with XXXXXXXXXXXXXXXX.</span></span>  
  
    <span data-ttu-id="c3ff1-200">SetupBPM.bat では、次のタスクが実行されます。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-200">The SetupBPM.bat performs the following tasks:</span></span>  
  
   1.  <span data-ttu-id="c3ff1-201">BPM ソリューションのアセンブリに署名するための、一意の厳密な名前のキー (SNK) を作成します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-201">Creates a unique strong name key (SNK) for signing the assemblies of the BPM Solution.</span></span>  
  
   2.  <span data-ttu-id="c3ff1-202">SNK から公開キー トークンを抽出します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-202">Extracts the public key token from the SNK.</span></span>  
  
   3.  <span data-ttu-id="c3ff1-203">公開キー トークンを使用してバインド ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-203">Updates the binding files with the public token.</span></span>  
  
   4.  <span data-ttu-id="c3ff1-204">BPM ソリューションを作成し、OpsAdapter をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-204">Builds the BPM solution, and installs OpsAdapter.</span></span>  
  
   5.  <span data-ttu-id="c3ff1-205">%BTSSolutionsPath%\Common フォルダーに SSOApplicationConfig を作成します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-205">Builds the SSOApplicationConfig in the %BTSSolutionsPath%\Common folder.</span></span>  
  
2. <span data-ttu-id="c3ff1-206">ビジネス ルール エンジン展開ウィザードを使用して、Southridge Video ビジネス ルールを展開します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-206">Deploy the Southridge Video business rules using the Business Rule Engine Deployment Wizard:</span></span>  
  
   1. <span data-ttu-id="c3ff1-207">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**ビジネス ルール エンジン展開ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-207">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rules Engine Deployment Wizard**.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="c3ff1-208">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-208">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="c3ff1-209">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-209">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
   2. <span data-ttu-id="c3ff1-210">**へようこそ**  ページで **次**します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-210">On the **Welcome** page, click **Next**.</span></span>  
  
   3. <span data-ttu-id="c3ff1-211">**展開タスク**] ページで、[**インポート ポリシー/ボキャブラリをファイルからデータベースに発行し、**、順にクリックします**次**。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-211">On the **Deployment Task** page, select **Import and publish Policy/Vocabulary to database from file**, and then click **Next**.</span></span>  
  
   4. <span data-ttu-id="c3ff1-212">**ポリシー ストア** ページでその他のすべての設定の既定では、保持してクリックして**次**。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-212">On the **Policy Store** page, keep all other default settings, and then click **Next**.</span></span>  
  
   5. <span data-ttu-id="c3ff1-213">**インポート ルール エンジン ポリシー/ボキャブラリ ファイル** ページで **参照**%BTSSolutionsPath%\BPM\Rules フォルダーの DecodeAndValidateOrderRules.xml ファイルを選択し、をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-213">On the **Import Rules Engine Policy/Vocabulary file** page, click **Browse**, select the DecodeAndValidateOrderRules.xml file in the %BTSSolutionsPath%\BPM\Rules folder, and then click **Next**.</span></span>  
  
   6. <span data-ttu-id="c3ff1-214">**準備ができて**] ページで [ **[次へ]**、し、**ポリシー/ボキャブラリのインポート**] ページで [ **[次へ]**</span><span class="sxs-lookup"><span data-stu-id="c3ff1-214">On the **Ready** page, click **Next**, and then on the **Importing Policy/Vocabulary** page, click **Next**</span></span>  
  
   7. <span data-ttu-id="c3ff1-215">[完了] ページで、次のように選択します。**ウィザードを再度実行**をクリックしてウィザードを再度開いて**完了**。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-215">On the Completion page, select **Run the wizard again** to open the Wizard again, and then click **Finish**.</span></span>  
  
   8. <span data-ttu-id="c3ff1-216">**へようこそ**  ページで **次**します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-216">On the **Welcome** page, click **Next**.</span></span>  
  
   9. <span data-ttu-id="c3ff1-217">**展開タスク**] ページで、[ **[deploypolicy]**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-217">On the **Deployment Task** page, select **DeployPolicy**, and then click **Next**.</span></span>  
  
   10. <span data-ttu-id="c3ff1-218">**ポリシー ストア** ページでその他のすべての設定の既定では、保持してクリックして**次**。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-218">On the **Policy Store** page, keep all other default settings, and then click **Next**.</span></span>  
  
   11. <span data-ttu-id="c3ff1-219">**ポリシーの展開**] ページで、[ **DecodeAndValidateOrder 1.0**で、**ルール エンジン ポリシー**ドロップダウン リスト、およびクリック **[次へ]**.</span><span class="sxs-lookup"><span data-stu-id="c3ff1-219">On the **Deploy Policy** page, select **DecodeAndValidateOrder 1.0** in the **Rule Engine Policy** drop-down list, and then click **Next**.</span></span>  
  
   12. <span data-ttu-id="c3ff1-220">**準備ができて**] ページで [ **[次へ]**、し、**ポリシーの展開**] ページで [ **[次へ]**。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-220">On the **Ready** page, click **Next**, and then on the **Deploying Policy** page, click **Next**.</span></span>  
  
   13. <span data-ttu-id="c3ff1-221">[完了] ページで、次のようにクリックします。**完了**します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-221">On the Completion page, click **Finish**.</span></span>  
  
3. <span data-ttu-id="c3ff1-222">BPM ソリューションを 64 ビット コンピューターにインストールする場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-222">If you install the BPM solution on a 64-bit computer, then</span></span>  
  
   1.  <span data-ttu-id="c3ff1-223">次の 32 ビット コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`%SYSTEMROOT%\SYSWOW64\CMD.EXE`、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-223">Open a 32-bit command prompt as follow: Click **Start**, click **Run**, type `%SYSTEMROOT%\SYSWOW64\CMD.EXE`, and then press ENTER.</span></span>  
  
   2.  <span data-ttu-id="c3ff1-224">32 ビット コマンド プロンプトで、ディレクトリを %BTSSolutionsPath%\BPM\Scripts フォルダーに変更します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-224">At the 32-bit command prompt, change the directory to the %BTSSolutionsPath%\BPM\Scripts folder.</span></span>  
  
   3.  <span data-ttu-id="c3ff1-225">メモ帳で CreateSouthridgeVideoApplication.cmd を開き、"%CommonProgramFiles%\Enterprise Single Sign-On\ssomanage.exe" を "%SystemDrive%\Program Files\Common Files\Enterprise Single Sign-On\ssomanage.exe" に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-225">Using Notepad, open the CreateSouthridgeVideoApplication.cmd, and then replace "%CommonProgramFiles%\Enterprise Single Sign-On\ssomanage.exe" with "%SystemDrive%\Program Files\Common Files\Enterprise Single Sign-On\ssomanage.exe".</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="c3ff1-226">32 ビット コマンド プロンプトでは、%CommonProgramFiles% 変数が "%ProgramFiles(x86)%\Common Files" に変わります。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-226">At a 32-bit command prompt, the %CommonProgramFiles% variable is changed to "%ProgramFiles(x86)%\Common Files".</span></span> <span data-ttu-id="c3ff1-227">SSO 管理ユーティリティは 64 ビット コンピューターでも %ProgramFiles% にインストールされるので、パスを修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-227">Because the SSO administrative utility is installed in the %ProgramFiles% even on a 64-bit computer, you must fix the path.</span></span> <span data-ttu-id="c3ff1-228">DeployBPM.cmd は、CreateSouthridgeVideoApplication.cmd を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-228">The DeployBPM.cmd calls CreateSouthridgeVideoApplication.cmd.</span></span>  
  
   4.  <span data-ttu-id="c3ff1-229">32 ビットのコマンド プロンプトで「 `DeployBPM.cmd`、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-229">At the 32-bit command prompt, type `DeployBPM.cmd`, and then press ENTER.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="c3ff1-230">DeployBPM.cmd は、32 ビット コマンド プロンプトで実行する必要があります。cscript.exe の x86 バージョンを必要とする x86 オブジェクトにアクセスする VB スクリプトが含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-230">The DeployBPM.cmd must be run at a 32-bit command prompt because it includes the VB Script accessing x86 objects that requires the x86 version of cscript.exe.</span></span>  
  
4. <span data-ttu-id="c3ff1-231">コマンド プロンプトで、現在のフォルダーを %btssolutionspath%\bpm\scripts、型に変更`DeployBPM.cmd`、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-231">At a command prompt, change the current folder to %BTSSolutionsPath%\BPM\Scripts, type `DeployBPM.cmd`, and then press ENTER.</span></span> <span data-ttu-id="c3ff1-232">DeployBPM.cmd は、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-232">The DeployBPM.cmd performs the following tasks:</span></span>  
  
   1.  <span data-ttu-id="c3ff1-233">BPM ソリューションのための BizTalk アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-233">Creates BizTalk Applications for the BPM Solution.</span></span>  
  
   2.  <span data-ttu-id="c3ff1-234">アプリケーション間の参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-234">Adds references between the applications.</span></span>  
  
   3.  <span data-ttu-id="c3ff1-235">バインド ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-235">Imports the binding files.</span></span>  
  
   4.  <span data-ttu-id="c3ff1-236">BAM 定義ファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-236">Deploys the BAM definition files.</span></span>  
  
   5.  <span data-ttu-id="c3ff1-237">SouthridgeVideo イベント ソースを登録します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-237">Registers the SouthridgeVideo event source.</span></span>  
  
   6.  <span data-ttu-id="c3ff1-238">シングル サインオン (SSO) 関連アプリケーションを作成し、SSO アプリケーションの構成値を保存します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-238">Creates a Single Sign-On (SSO) affiliated application, and saves configuration values to the SSO application.</span></span>  
  
5. <span data-ttu-id="c3ff1-239">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-239">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
   1.  <span data-ttu-id="c3ff1-240">**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BTSScn.BPM.OrderBrokerApp**、展開**受信場所**、右クリックして**ベンダー-RL RP**、し、[プロパティ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-240">In the **BizTalk Server Administration Console**, expand **BizTalk Group**, expand **Applications**, expand **BTSScn.BPM.OrderBrokerApp**, expand **Receive Locations**, right-click **Vendor-RP-RL**, and then click Properties.</span></span>  
  
   2.  <span data-ttu-id="c3ff1-241">**プロパティ**ダイアログ ボックスで、をクリックして**構成**、として、次の表値を入力し、**トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-241">On the **Properties** dialog box, click **Configure**, and then enter values as the following table on the **Transport Properties** dialog box:</span></span>  
  
       |<span data-ttu-id="c3ff1-242">プロパティ名</span><span class="sxs-lookup"><span data-stu-id="c3ff1-242">Property Name</span></span>|<span data-ttu-id="c3ff1-243">値</span><span class="sxs-lookup"><span data-stu-id="c3ff1-243">Value</span></span>|  
       |-------------------|-----------|  
       |<span data-ttu-id="c3ff1-244">**[サーバー]**</span><span class="sxs-lookup"><span data-stu-id="c3ff1-244">**Server**</span></span>|`localhost`|  
       |<span data-ttu-id="c3ff1-245">**[ユーザー名]**</span><span class="sxs-lookup"><span data-stu-id="c3ff1-245">**User Name**</span></span>|<span data-ttu-id="c3ff1-246">\<*BizTalk サービス アカウント名*\></span><span class="sxs-lookup"><span data-stu-id="c3ff1-246">\<*BizTalk service account name*\></span></span>|  
       |<span data-ttu-id="c3ff1-247">**Password**</span><span class="sxs-lookup"><span data-stu-id="c3ff1-247">**Password**</span></span>|<span data-ttu-id="c3ff1-248">\<*BizTalk サービス アカウントのパスワード*\></span><span class="sxs-lookup"><span data-stu-id="c3ff1-248">\<*BizTalk service account password*\></span></span>|  
  
6. <span data-ttu-id="c3ff1-249">BPM ソリューションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-249">Run the BPM Solution.</span></span> <span data-ttu-id="c3ff1-250">ソリューションの実行の詳細については、次を参照してください。 [、ビジネス プロセス管理ソリューションを実行する方法](../core/how-to-run-the-business-process-management-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-250">For more information about running the solution, see [How to Run the Business Process Management Solution](../core/how-to-run-the-business-process-management-solution.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c3ff1-251">次の手順</span><span class="sxs-lookup"><span data-stu-id="c3ff1-251">Next Steps</span></span>  
 <span data-ttu-id="c3ff1-252">ビジネス管理ソリューションがでどのように動作するかをテストする[、ビジネス プロセス管理ソリューションを実行する方法](../core/how-to-run-the-business-process-management-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="c3ff1-252">You test how the Business Management Solution works in [How to Run the Business Process Management Solution](../core/how-to-run-the-business-process-management-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3ff1-253">参照</span><span class="sxs-lookup"><span data-stu-id="c3ff1-253">See Also</span></span>  
 <span data-ttu-id="c3ff1-254">[ビジネス プロセス管理ソリューションをインストールする前に](../core/before-installing-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="c3ff1-254">[Before Installing the Business Process Management Solution](../core/before-installing-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="c3ff1-255">ビジネス プロセス管理ソリューションに対する開発者のコンピューター設定</span><span class="sxs-lookup"><span data-stu-id="c3ff1-255">Developer Machine Setup for the Business Process Management Solution</span></span>](../core/developer-machine-setup-for-the-business-process-management-solution.md)
