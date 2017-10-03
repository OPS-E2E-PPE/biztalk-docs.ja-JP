---
title: "HTTP の受信場所用に IIS を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 64-bit support, HTTP adapters
- HTTP adapters, IIS
- configuring [HTTP adapters], IIS
- receive locations, IIS
- IIS, receive locations
- HTTP adapters, 64-bit support
- IIS, HTTP adapters
ms.assetid: 1c420f46-01f1-4c9c-9144-d8d2acc8b0c4
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1daa535c546bef0b390f0f7f84c45d546ac0005
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-iis-for-an-http-receive-location"></a><span data-ttu-id="de338-102">HTTP の受信場所用に IIS を構成する方法</span><span class="sxs-lookup"><span data-stu-id="de338-102">How to Configure IIS for an HTTP Receive Location</span></span>
<span data-ttu-id="de338-103">使用中の Microsoft Windows のバージョンによって、HTTP アダプター受信場所を使用するための Microsoft インターネット インフォメーション サービス (IIS) の構成方法は異なります。</span><span class="sxs-lookup"><span data-stu-id="de338-103">Depending on which version of Microsoft Windows you are using, you will have to configure Microsoft Internet Information Services (IIS) differently to work with the HTTP adapter receive location.</span></span>  
  
 <span data-ttu-id="de338-104">使用中のオペレーティング システムが [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] または [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] の場合、IIS 7.0 では、Web アプリケーションを保護するために 2 種類のアプリケーション分離モードが提供されています。</span><span class="sxs-lookup"><span data-stu-id="de338-104">If your operating system is [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)], IIS 7.0 provides two different application isolation modes to protect Web applications.</span></span> <span data-ttu-id="de338-105">既定のモードは、ワーカー プロセス分離モードです。</span><span class="sxs-lookup"><span data-stu-id="de338-105">Worker process isolation mode is the default mode.</span></span> <span data-ttu-id="de338-106">HTTP アダプター受信場所は、どちらのモードでも動作するように構成できますが、セキュリティを強化するため、ワーカー プロセス分離モードを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="de338-106">You can configure the HTTP adapter receive location to work with either mode, but worker process isolation mode is recommended for its improved security functionality.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de338-107">オペレーティング システムが x64 エディションの[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]、64 ビット版の HTTP 受信アダプターがインストール、 *\<ドライブ >***\Program Files (x86) \Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\HttpReceive64**のディレクトリ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]既定です。</span><span class="sxs-lookup"><span data-stu-id="de338-107">If your operating system is the x64 edition of [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)], the 64-bit version of the HTTP receive adapter is installed to the *\<drive>***\Program Files (x86)\Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**\HttpReceive64** directory of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] by default.</span></span> <span data-ttu-id="de338-108">64 ビット版の HTTP 受信アダプターを 64 ビットのネイティブ モードで実行するには、コマンド ラインから次のスクリプトを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de338-108">To run the 64-bit version of the HTTP receive adapter in 64-bit native mode you must execute the following script from a command line:</span></span>  
>   
>  `cscript %SystemDrive%\inetpub\AdminScripts\adsutil.vbs set w3svc/AppPools/Enable32bitAppOnWin64 0`  
>   
>  `C:\WINDOWS\Microsoft.NET\Framework64\vX.X.XXXXX>aspnet_regiis.exe -i`  
  
> [!NOTE]
>  <span data-ttu-id="de338-109">同一プロセスを共有する SOAP と HTTP を使用する IIS 構成は無効です。</span><span class="sxs-lookup"><span data-stu-id="de338-109">Any IIS configuration that leads to SOAP and HTTP sharing the same process is not valid.</span></span> <span data-ttu-id="de338-110">プロセスごとに 1 つの分離受信場所のみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="de338-110">You can have only one isolated receiver per process.</span></span>  
  
### <a name="to-configure-the-iis-70-worker-process-isolation-mode-to-work-with-the-http-adapter-receive-location"></a><span data-ttu-id="de338-111">HTTP アダプターを使用する IIS 7.0 ワーカー プロセス分離モードの受信場所を構成するには</span><span class="sxs-lookup"><span data-stu-id="de338-111">To configure the IIS 7.0 worker process isolation mode to work with the HTTP adapter receive location</span></span>  
  
1.  <span data-ttu-id="de338-112">をクリックして**開始**、] をポイント**設定**、順にクリック**コントロール パネルの [**です。</span><span class="sxs-lookup"><span data-stu-id="de338-112">Click **Start**, point to **Settings**, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="de338-113">コントロール パネルで、ダブルクリック**管理ツール**です。</span><span class="sxs-lookup"><span data-stu-id="de338-113">In Control Panel, double-click **Administrative Tools**.</span></span>  
  
3.  <span data-ttu-id="de338-114">[管理ツール] をダブルクリック**インターネット インフォメーション サービス**です。</span><span class="sxs-lookup"><span data-stu-id="de338-114">In Administrative Tools, double-click **Internet Information Services**.</span></span>  
  
4.  <span data-ttu-id="de338-115">インターネット インフォメーション サービスでルート Web サーバーのエントリを選択します。</span><span class="sxs-lookup"><span data-stu-id="de338-115">In Internet Information Services, select the root Web server entry.</span></span> <span data-ttu-id="de338-116">**機能ビュー**をダブルクリックして**ハンドラー マッピング**、[操作] ウィンドウで、クリックして**スクリプト マップの追加**です。</span><span class="sxs-lookup"><span data-stu-id="de338-116">In the **Features View**, double-click **Handler Mappings**, and then in the Actions pane, click **Add Script Map**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="de338-117">Web サーバー レベルでスクリプトのマッピングを構成すると、すべての子 Web サイトにこのマッピングが適用されます。</span><span class="sxs-lookup"><span data-stu-id="de338-117">Configuring the script mapping at the Web server level will cause this mapping to apply to all child Web sites.</span></span> <span data-ttu-id="de338-118">マッピングを特定の Web サイトまたは仮想フォルダーに制限する場合は、Web サーバーではなくターゲット サイトまたはターゲット フォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="de338-118">If you want to restrict the mapping to a specific Web site or virtual folder, select the target site or folder instead of the Web server.</span></span>  
  
5.  <span data-ttu-id="de338-119">**スクリプト マップの追加** ダイアログ ボックスで、**要求パス**フィールドに「`BtsHttpReceive.dll`です。</span><span class="sxs-lookup"><span data-stu-id="de338-119">In the **Add Script Map** dialog box, in the **Request path** field, type `BtsHttpReceive.dll`.</span></span>  
  
6.  <span data-ttu-id="de338-120">**実行可能ファイル**フィールドで、省略記号ボタン (**.**) ボタンをクリックしを参照[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive です。</span><span class="sxs-lookup"><span data-stu-id="de338-120">In the **Executable** field, click the ellipsis (**…**) button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive.</span></span> <span data-ttu-id="de338-121">選択**BtsHttpReceive.dll**  をクリックし、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="de338-121">Select **BtsHttpReceive.dll** and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="de338-122">**名前**フィールドに「 `BizTalk HTTP Receive`、クリックしてして**要求の制限**です。</span><span class="sxs-lookup"><span data-stu-id="de338-122">In the **Name** field, type `BizTalk HTTP Receive`, and then click **Request Restrictions**.</span></span>  
  
8.  <span data-ttu-id="de338-123">**要求の制限** ダイアログ ボックスをクリックして、**動詞**タブをクリックし**次の動詞のいずれかの**です。</span><span class="sxs-lookup"><span data-stu-id="de338-123">In the **Request Restrictions** dialog box, click the **Verbs** tab and then select **One of the following verbs**.</span></span> <span data-ttu-id="de338-124">入力`POST`動詞として。</span><span class="sxs-lookup"><span data-stu-id="de338-124">Enter `POST` as the verb.</span></span>  
  
9. <span data-ttu-id="de338-125">**アクセス**] タブで [**スクリプト**、クリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="de338-125">On the **Access** tab, select **Script**, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="de338-126">ISAPI 拡張機能を許可するように求めるメッセージが表示されたら、 **[はい]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de338-126">When prompted to allow the ISAPI extension, click **Yes**.</span></span>  
  
11. <span data-ttu-id="de338-127">右クリック**アプリケーション プール**、 をポイント**新規**、クリックして**アプリケーション プール**です。</span><span class="sxs-lookup"><span data-stu-id="de338-127">Right-click **Application Pools**, point to **New**, and then click **Application pool**.</span></span>  
  
12. <span data-ttu-id="de338-128">**アプリケーション プールの追加** ダイアログ ボックスで、**名前**ボックスで、アプリケーション プールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="de338-128">In the **Add Application Pool** dialog box, in the **Name** box, type a name for the application pool.</span></span> <span data-ttu-id="de338-129">選択**NET Framework v4.0.30319**  をクリックし、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="de338-129">Select **NET Framework v4.0.30319** and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="de338-130">バージョン番号は、コンピューターにインストールされている .NET Framework のバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="de338-130">The version number may vary depending on the version of .NET Framework installed on the computer.</span></span>  
  
     <span data-ttu-id="de338-131">新しいアプリケーション プールの一覧に含ま**アプリケーション プール**です。</span><span class="sxs-lookup"><span data-stu-id="de338-131">The new application pool appears in the list of **Application Pools**.</span></span>  
  
13. <span data-ttu-id="de338-132">**アプリケーション プール**の**機能ビュー**、新しいアプリケーション プールを選択して、をクリックして**詳細設定**[操作] ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="de338-132">In **Application Pools**, in the **Features View**, select the new application pool, and then click **Advanced Settings** in the Actions pane.</span></span>  
  
14. <span data-ttu-id="de338-133">**詳細設定** ダイアログ ボックスで、**プロセス モデル**セクションで、 **Identity**フィールドで省略記号ボタンをクリックして (**.**) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="de338-133">In the **Advanced Settings** dialog box, in the **Process Model** section, in the **Identity** field, click the ellipsis (**…**) button.</span></span>  
  
15. <span data-ttu-id="de338-134">**アプリケーション プール Id**ダイアログ ボックスで、**カスタム アカウント**、クリックして**設定**です。</span><span class="sxs-lookup"><span data-stu-id="de338-134">In the **Application Pool Identity** dialog box, select **Custom account**, and then click **Set**.</span></span> <span data-ttu-id="de338-135">**[OK]** をクリックして **[詳細設定]** ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="de338-135">Click **OK** to close the **Advanced Settings** dialog box.</span></span>  
  
16. <span data-ttu-id="de338-136">IIS マネージャーで、開く、**サイト**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="de338-136">In IIS Manager, open the **Sites** folder.</span></span> <span data-ttu-id="de338-137">右クリックし、 **Default Web Site**  をクリックし、**アプリケーションの追加**です。</span><span class="sxs-lookup"><span data-stu-id="de338-137">Right-click the **Default Web Site** and then click **Add Application**.</span></span>  
  
17. <span data-ttu-id="de338-138">**アプリケーションの追加**ダイアログ ボックスで、**エイリアス**、クリックして、アプリケーションに関連付けるエイリアスを入力して**選択**です。</span><span class="sxs-lookup"><span data-stu-id="de338-138">In the **Add Application** dialog box, in **Alias**, enter an alias to associate with the application, and then click **Select**.</span></span>  
  
18. <span data-ttu-id="de338-139">**アプリケーション プールの選択**ダイアログ ボックスで、先ほど作成した新しいアプリケーション プールを選択し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="de338-139">In the **Select Application Pool** dialog box, select the new application pool you created earlier, and then click **OK**.</span></span>  
  
19. <span data-ttu-id="de338-140">省略記号ボタン (**.**) ボタンをクリックしを参照[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive、**物理パス**です。</span><span class="sxs-lookup"><span data-stu-id="de338-140">Click the ellipsis (**…**) button and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive for the **Physical path**.</span></span>  
  
20. <span data-ttu-id="de338-141">をクリックして**接続として**を入力し、**ユーザー名**と**パスワード**Administrators グループのメンバーであるし、ユーザー アカウントの**ok**.</span><span class="sxs-lookup"><span data-stu-id="de338-141">Click **Connect As** and enter the **User name** and **Password** for a user account that is a member of the Administrators group, and then click **OK**.</span></span>  
  
21. <span data-ttu-id="de338-142">をクリックして**テストの設定**でエラーが表示されていないことを確認し、**接続のテスト** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="de338-142">Click **Test Settings** and verify that no errors are displayed in the **Test Connection** dialog box.</span></span> <span data-ttu-id="de338-143">**[閉じる]**をクリックし、 **[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de338-143">Click **Close**, and then click **OK**.</span></span>  
  
22. <span data-ttu-id="de338-144">新しいアプリケーションの一覧に表示**既定の Web サイト**インターネット インフォメーション サービス (IIS) マネージャーでします。</span><span class="sxs-lookup"><span data-stu-id="de338-144">The new application appears in the list of **Default Web Sites** in Internet Information Services (IIS) Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de338-145">参照</span><span class="sxs-lookup"><span data-stu-id="de338-145">See Also</span></span>  
 [<span data-ttu-id="de338-146">HTTP 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="de338-146">How to Configure an HTTP Receive Location</span></span>](../core/how-to-configure-an-http-receive-location.md)