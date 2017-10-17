---
title: "HTTP の受信場所の IIS を構成する |Microsoft ドキュメント"
description: "IIS では、BTS HTTP 受信アプリケーションを作成し、BizTalk Server でのアプリケーション プールの設定のテスト"
ms.custom: 
ms.date: 10/10/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c420f46-01f1-4c9c-9144-d8d2acc8b0c4
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e09768d6616a33a4900995f3dd3225fa34318b3c
ms.sourcegitcommit: 75d35f6f230f0846c29a4b146c6d5b074e60b13c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2017
---
# <a name="configure-iis-for-an-http-receive-location"></a><span data-ttu-id="760e1-103">HTTP の受信場所の IIS を構成します。</span><span class="sxs-lookup"><span data-stu-id="760e1-103">Configure IIS for an HTTP Receive Location</span></span>
<span data-ttu-id="760e1-104">HTTP は、場所が使用アプリケーション内では、インターネット インフォメーション サービス (IIS) を受信します。</span><span class="sxs-lookup"><span data-stu-id="760e1-104">The HTTP receive location uses an application within Internet Information Services (IIS).</span></span> <span data-ttu-id="760e1-105">このトピックに HTTP を有効にする手順は、IIS 内の場所を受信します。</span><span class="sxs-lookup"><span data-stu-id="760e1-105">This topic lists the steps to enable the HTTP receive location within IIS.</span></span> 

<span data-ttu-id="760e1-106">オペレーティング システムに応じて、IIS アプリケーションを構成する手順が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="760e1-106">Depending on your operating system, the steps to configure the IIS application may vary.</span></span> <span data-ttu-id="760e1-107">として使用してこれらの手順、ガイドでは、ユーザー インターフェイスが、OS で異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="760e1-107">Use these steps as a guide, as the user interface may be different on your OS.</span></span>
  
## <a name="32-bit-vs-64-bit"></a><span data-ttu-id="760e1-108">32 ビットと 64 ビット</span><span class="sxs-lookup"><span data-stu-id="760e1-108">32-bit vs 64-bit</span></span>

<span data-ttu-id="760e1-109">HTTP の受信場所が、BTSHTTPReceive.dll を使用します。</span><span class="sxs-lookup"><span data-stu-id="760e1-109">An HTTP receive location uses the BTSHTTPReceive.dll.</span></span> <span data-ttu-id="760e1-110">32 ビットと DLL の 64 ビット バージョンがあります。</span><span class="sxs-lookup"><span data-stu-id="760e1-110">There is a 32-bit and a 64-bit version of the DLL.</span></span> <span data-ttu-id="760e1-111">使用するバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="760e1-111">You choose which version you want to use.</span></span> <span data-ttu-id="760e1-112">64 ビット プロセスで使用可能なメモリがためがあるかどうかより大きなメッセージを処理する、64 ビット バージョンが最適な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="760e1-112">64-bit processes have more available memory, so if you process larger messages, then the 64-bit version may be best.</span></span> 

<span data-ttu-id="760e1-113">**32 ビットのインストール場所**: *%program Files (x86) \Microsoft BizTalk Server\HttpReceive*です。</span><span class="sxs-lookup"><span data-stu-id="760e1-113">**32-bit install location**: *Program Files (x86)\Microsoft BizTalk Server\HttpReceive*.</span></span>
<span data-ttu-id="760e1-114">**64 ビットのインストール場所**: *%program Files (x86) \Microsoft BizTalk Server\HttpReceive64*</span><span class="sxs-lookup"><span data-stu-id="760e1-114">**64-bit install location**: *Program Files (x86)\Microsoft BizTalk Server\HttpReceive64*</span></span>

<span data-ttu-id="760e1-115">HTTP の 64 ビット バージョンを実行する 64 ビットのネイティブ モードで受信アダプター、コマンド プロンプトを開き、および次のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="760e1-115">To run the 64-bit version of the HTTP receive adapter in 64-bit native mode,  open a command prompt, and execute the following scripts:</span></span>  

1. <span data-ttu-id="760e1-116">型:`cscript %SystemDrive%\inetpub\AdminScripts\adsutil.vbs set w3svc/AppPools/Enable32bitAppOnWin64 0`</span><span class="sxs-lookup"><span data-stu-id="760e1-116">Type: `cscript %SystemDrive%\inetpub\AdminScripts\adsutil.vbs set w3svc/AppPools/Enable32bitAppOnWin64 0`</span></span>  

2. <span data-ttu-id="760e1-117">型:`C:\WINDOWS\Microsoft.NET\Framework64\vX.X.XXXXX>aspnet_regiis.exe -i`</span><span class="sxs-lookup"><span data-stu-id="760e1-117">Type: `C:\WINDOWS\Microsoft.NET\Framework64\vX.X.XXXXX>aspnet_regiis.exe -i`</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="760e1-118">同一プロセスを共有する SOAP と HTTP を使用する IIS 構成は無効です。</span><span class="sxs-lookup"><span data-stu-id="760e1-118">Any IIS configuration that leads to SOAP and HTTP sharing the same process is not valid.</span></span> <span data-ttu-id="760e1-119">プロセスごとに 1 つの分離受信場所のみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="760e1-119">You can have only one isolated receiver per process.</span></span>  
  
##  <a name="configure-the-iis-application"></a><span data-ttu-id="760e1-120">IIS アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="760e1-120">Configure the IIS application</span></span>
  
1.  <span data-ttu-id="760e1-121">開く**インターネット インフォメーション サービス**(開く**サーバー マネージャー****ツール**を選択し、**インターネット インフォメーション サービス マネージャー**).</span><span class="sxs-lookup"><span data-stu-id="760e1-121">Open **Internet Information Services** (open **Server Manager**, select **Tools**, and select **Internet Information Services Manager**).</span></span> 
  
2.  <span data-ttu-id="760e1-122">IIS では、サーバー名を選択します。</span><span class="sxs-lookup"><span data-stu-id="760e1-122">In IIS, select your server name.</span></span> <span data-ttu-id="760e1-123">**機能ビュー**をダブルクリックして**ハンドラー マッピング**です。</span><span class="sxs-lookup"><span data-stu-id="760e1-123">In the **Features View**, double-click **Handler Mappings**.</span></span> <span data-ttu-id="760e1-124">[操作] ウィンドウで、次のように選択します。**スクリプト マップの追加**です。</span><span class="sxs-lookup"><span data-stu-id="760e1-124">In the Actions pane, select **Add Script Map**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="760e1-125">Web サーバー レベルでスクリプト マッピングを構成するときに、マッピングがすべての web サイトに適用されます。</span><span class="sxs-lookup"><span data-stu-id="760e1-125">When you configure the script mapping at the web server-level, the mapping applies to all web sites.</span></span> <span data-ttu-id="760e1-126">特定の Web サイトまたは仮想フォルダーへのマッピングを制限する場合は、その web サイトまたはフォルダーを選択し、スクリプト マップを追加します。</span><span class="sxs-lookup"><span data-stu-id="760e1-126">If you want to restrict the mapping to a specific Web site or virtual folder, select that web site or folder, and then add the script map.</span></span>  
  
3.  <span data-ttu-id="760e1-127">**スクリプト マップの追加****要求パス**、および種類`BtsHttpReceive.dll`です。</span><span class="sxs-lookup"><span data-stu-id="760e1-127">In **Add Script Map**, select **Request path**, and type `BtsHttpReceive.dll`.</span></span>  
  
4.  <span data-ttu-id="760e1-128">**実行可能ファイル**、省略記号 (**.**) を参照および[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive です。</span><span class="sxs-lookup"><span data-stu-id="760e1-128">In **Executable**, select the ellipsis (**…**), and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive.</span></span> <span data-ttu-id="760e1-129">選択**BtsHttpReceive.dll**、し、**開く**です。</span><span class="sxs-lookup"><span data-stu-id="760e1-129">Select **BtsHttpReceive.dll**, and then select **Open**.</span></span>  
  
5.  <span data-ttu-id="760e1-130">**名前**、入力`BizTalk HTTP Receive`、し、**要求の制限**です。</span><span class="sxs-lookup"><span data-stu-id="760e1-130">In **Name**, enter `BizTalk HTTP Receive`, and then select **Request Restrictions**.</span></span> <span data-ttu-id="760e1-131">このウィンドウには。</span><span class="sxs-lookup"><span data-stu-id="760e1-131">In this window:</span></span>
  
    1. <span data-ttu-id="760e1-132">**動詞****次の動詞のいずれかの**、入力と`POST`です。</span><span class="sxs-lookup"><span data-stu-id="760e1-132">In **Verbs**, select **One of the following verbs**, and enter `POST`.</span></span>  
  
    2. <span data-ttu-id="760e1-133">**アクセス****スクリプト**、し、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="760e1-133">In **Access**, select **Script**, and then select **OK**.</span></span>  
  
    3. <span data-ttu-id="760e1-134">ISAPI 拡張を許可するメッセージが表示されたら、**はい**です。</span><span class="sxs-lookup"><span data-stu-id="760e1-134">When prompted to allow the ISAPI extension, select **Yes**.</span></span>  
  
6. <span data-ttu-id="760e1-135">新しいアプリケーション プールの作成 (を右クリックして**アプリケーション プール****アプリケーション プールの追加**)。</span><span class="sxs-lookup"><span data-stu-id="760e1-135">Create a new application pool (right-click **Application Pools**, select **Add application pool**).</span></span> <span data-ttu-id="760e1-136">**名前**アプリケーション プール (など`BTSHTTPReceive`) を選択**NET Framework v4.0.30319**を選択し、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="760e1-136">**Name** your application pool (such as `BTSHTTPReceive`), select **NET Framework v4.0.30319**, and select **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="760e1-137">.NET バージョン番号は、コンピューターにインストールされている .NET Framework のバージョンによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="760e1-137">The .NET version number may vary depending on the version of .NET Framework installed on the computer.</span></span>  
  
     <span data-ttu-id="760e1-138">新しいアプリケーション プールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="760e1-138">The new application pool is listed.</span></span>  
  
7. <span data-ttu-id="760e1-139">新しいアプリケーション プールを選択して開きます、**詳細設定**(**アクション**ウィンドウ)。</span><span class="sxs-lookup"><span data-stu-id="760e1-139">Select your new application pool, and open the **Advanced Settings** (**Actions** pane).</span></span> <span data-ttu-id="760e1-140">このウィンドウには。</span><span class="sxs-lookup"><span data-stu-id="760e1-140">In this window:</span></span>

    - <span data-ttu-id="760e1-141">**32 ビット アプリケーションを有効にする**: 'Éý' **True**する場合は、32 ビット**BtsHttpReceive.dll**</span><span class="sxs-lookup"><span data-stu-id="760e1-141">**Enable 32-Bit Application**: Set to **True** if you chose the 32-bit **BtsHttpReceive.dll**</span></span>
    - <span data-ttu-id="760e1-142">**モデルの処理** セクションで、 **Identity**: は、省略記号 (**.**) を選択**カスタム アカウント**、し**設定**のメンバーであるアカウントに、 **BizTalk Isolated Host Users**と**IIS_WPG**グループ。</span><span class="sxs-lookup"><span data-stu-id="760e1-142">**Process Model** section, **Identity**: Select the ellipsis (**…**), select **Custom account**, and then **Set** it to an account that is a member of the **BizTalk Isolated Host Users** and **IIS_WPG** groups.</span></span> <span data-ttu-id="760e1-143">[ **OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="760e1-143">Select **OK**.</span></span> 
  
8. <span data-ttu-id="760e1-144">Web サイトに新しいアプリケーションを追加 (を右クリックし、**既定の Web サイト****アプリケーションの追加**)。</span><span class="sxs-lookup"><span data-stu-id="760e1-144">Add a new application to the web site (right-click the **Default Web Site**, select **Add Application**).</span></span> <span data-ttu-id="760e1-145">このウィンドウには。</span><span class="sxs-lookup"><span data-stu-id="760e1-145">In this window:</span></span>
  
    1. <span data-ttu-id="760e1-146">**エイリアス**: アプリケーションに関連付けるエイリアスを入力 (など`BTS HTTP Receive`、し**選択**です。</span><span class="sxs-lookup"><span data-stu-id="760e1-146">**Alias** : Enter an alias that you associate with the application (such as `BTS HTTP Receive`, and then **Select**.</span></span>  
    2. <span data-ttu-id="760e1-147">作成した新しいアプリケーション プールを選択し、選択**OK**です。</span><span class="sxs-lookup"><span data-stu-id="760e1-147">Select the new application pool you just created, and then select **OK**.</span></span>  
    3. <span data-ttu-id="760e1-148">**物理パス**: は、省略記号 (**.**) を参照および[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive です。</span><span class="sxs-lookup"><span data-stu-id="760e1-148">**Physical path**: Select the ellipsis (**…**), and browse to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive.</span></span>  
    4. <span data-ttu-id="760e1-149">**テストの設定**にエラーがないことを確認する、 **Test-connection**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="760e1-149">**Test Settings** to verify there are no errors in the **Test Connection** dialog box.</span></span> <span data-ttu-id="760e1-150">**閉じる**、し、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="760e1-150">**Close**, and then select **OK**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="760e1-151">テストの設定には、警告が返された場合は、フォルダーへのアクセス許可またはグループへのアクセス、アプリケーション プールの id がない可能性がします。</span><span class="sxs-lookup"><span data-stu-id="760e1-151">If Test Settings returns a warning, the identity of the application pool may be missing permissions to a folder, or access to a group.</span></span> <span data-ttu-id="760e1-152">トラブルシューティング手順として、次のように選択します。**接続として**、入力、**ユーザー名**と**パスワード**Administrators グループのメンバーであるユーザー アカウントのです。</span><span class="sxs-lookup"><span data-stu-id="760e1-152">As a troubleshooting step, select **Connect As**, enter the **User name** and **Password** for a user account that is a member of the Administrators group.</span></span> 

9. <span data-ttu-id="760e1-153">新しいアプリケーションの表示の下に表示**既定の Web サイト**です。</span><span class="sxs-lookup"><span data-stu-id="760e1-153">The new application appears is listed under **Default Web Sites**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="760e1-154">参照</span><span class="sxs-lookup"><span data-stu-id="760e1-154">See Also</span></span>  
 [<span data-ttu-id="760e1-155">HTTP 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="760e1-155">How to Configure an HTTP Receive Location</span></span>](../core/how-to-configure-an-http-receive-location.md)
