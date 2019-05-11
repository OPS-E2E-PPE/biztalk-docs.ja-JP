---
title: HTTP アダプター (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: f3bd8172-15c4-42fa-aa17-e4bed9d4aba4
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e204d1e15ec7483bf2ae2f10db30ffd019651bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332837"
---
# <a name="http-adapter-biztalk-server-sample"></a><span data-ttu-id="4b987-102">HTTP アダプター (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="4b987-102">HTTP Adapter (BizTalk Server Sample)</span></span>
<span data-ttu-id="4b987-103">HTTP アダプターのサンプルで使用される要求/応答および送信請求-応答の通信パラダイムを実装する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="4b987-103">The HTTP Adapter sample demonstrates how to implement the request/response and solicit/response communication paradigms used in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="4b987-104">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="4b987-104">Where to Find This Sample</span></span>  
 <span data-ttu-id="4b987-105">*\<Samples Path\>* \AdaptersDevelopment\HttpAdapter\\</span><span class="sxs-lookup"><span data-stu-id="4b987-105">*\<Samples Path\>* \AdaptersDevelopment\HttpAdapter\\</span></span>  

 <span data-ttu-id="4b987-106">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="4b987-106">The following table shows the files in this sample and describes their purpose.</span></span>  

|<span data-ttu-id="4b987-107">ファイル</span><span class="sxs-lookup"><span data-stu-id="4b987-107">File(s)</span></span>|<span data-ttu-id="4b987-108">説明</span><span class="sxs-lookup"><span data-stu-id="4b987-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4b987-109">\Design-Time\Adapter Management</span><span class="sxs-lookup"><span data-stu-id="4b987-109">\Design-Time\Adapter Management</span></span>|<span data-ttu-id="4b987-110">このアダプターのデザイン時の部分を実装するプロジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b987-110">Contains the project that implements the design time portion of this adapter.</span></span>|  
|<span data-ttu-id="4b987-111">\Run-Time\HttpReceive</span><span class="sxs-lookup"><span data-stu-id="4b987-111">\Run-Time\HttpReceive</span></span>|<span data-ttu-id="4b987-112">アダプターの要求/応答通信パターンを実装するプロジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b987-112">Contains the project that implements the request/response adapter communication pattern.</span></span> <span data-ttu-id="4b987-113">これは、分離受信場所です。</span><span class="sxs-lookup"><span data-stu-id="4b987-113">This is an isolated receiver.</span></span>|  
|<span data-ttu-id="4b987-114">\Run-Time\HttpSend</span><span class="sxs-lookup"><span data-stu-id="4b987-114">\Run-Time\HttpSend</span></span>|<span data-ttu-id="4b987-115">送信請求-応答アダプターの通信パターンを実装するプロジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b987-115">Contains the project that implements the solicit/response adapter communication pattern.</span></span>|  

## <a name="how-to-use-this-sample"></a><span data-ttu-id="4b987-116">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="4b987-116">How to Use This Sample</span></span>  
 <span data-ttu-id="4b987-117">このサンプルは、カスタム アダプターの開発で使用するためのフレームワークとしてものです。</span><span class="sxs-lookup"><span data-stu-id="4b987-117">This sample is meant as a framework for you to use in developing custom adapters.</span></span> <span data-ttu-id="4b987-118">場合によっては、BizTalk Server が特定のカスタム アプリケーションにメッセージを送信したりするプロトコルを使用する必要があります、ネイティブ アダプターが存在しません。</span><span class="sxs-lookup"><span data-stu-id="4b987-118">In some cases BizTalk Server may need to transport messages to a specific custom application or use a protocol for which a native adapter that does not exist.</span></span> <span data-ttu-id="4b987-119">サードパーティの企業は、追加のプロトコルをサポートするアダプターを作成しています。</span><span class="sxs-lookup"><span data-stu-id="4b987-119">Third-party companies have written adapters to support additional protocols.</span></span> <span data-ttu-id="4b987-120">カスタム アダプターの作成を決定する前に、プロトコルに対するアダプターが存在するかどうかを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4b987-120">You may want to determine if there is an adapter for your protocol before deciding to write a custom adapter.</span></span> <span data-ttu-id="4b987-121">通信要件をサポートするためのアダプターが見つからない場合は、独自のカスタム アダプターを開発できます。</span><span class="sxs-lookup"><span data-stu-id="4b987-121">If you are unable to locate an adapter to support your communication requirements, you can develop your own custom adapter.</span></span>  

 <span data-ttu-id="4b987-122">カスタム アダプターの作成は、難しい作業になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4b987-122">Writing a custom adapter can be a challenging exercise.</span></span> <span data-ttu-id="4b987-123">このプロセスを簡略化するために、マイクロソフトはアダプター フレームワークと呼ばれる基礎を開発しました。</span><span class="sxs-lookup"><span data-stu-id="4b987-123">To simplify this process Microsoft has developed a foundation called the Adapter Framework.</span></span> <span data-ttu-id="4b987-124">このフレームワークは、BizTalk Server SDK のサンプルのアダプター ソース コードと共に開発の基礎として使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b987-124">You can use this framework as a basis for your development along with sample adapter source code in the BizTalk Server SDK.</span></span>  <span data-ttu-id="4b987-125">カスタム アダプターおよびアダプター フレームワークの詳細についてを参照してください、**参照**このドキュメントの最後のセクション。</span><span class="sxs-lookup"><span data-stu-id="4b987-125">For more information on custom adapters, and the Adapter Framework, please refer to the **See Also** section at the end of this document.</span></span>  

## <a name="building-and-initializing-the-sample-adapter"></a><span data-ttu-id="4b987-126">ビルドとサンプル アダプターの初期化</span><span class="sxs-lookup"><span data-stu-id="4b987-126">Building and Initializing the Sample Adapter</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="4b987-127">BizTalk のインストールが 64 ビット、またはインストールの場所が変更された、OutboundAssemblyPath、InboundAssemblyPath、AdapterMgmtAssemblyPath しなければ適切に変更します。</span><span class="sxs-lookup"><span data-stu-id="4b987-127">If the BizTalk installation is 64-bit or the location of installation is modified, OutboundAssemblyPath, InboundAssemblyPath, AdapterMgmtAssemblyPath would need to be changed accordingly.</span></span>  

#### <a name="to-build-and-initialize-the-http-adapter-sample"></a><span data-ttu-id="4b987-128">ビルドして、HTTP アダプタのサンプルの初期化</span><span class="sxs-lookup"><span data-stu-id="4b987-128">To build and initialize the HTTP Adapter sample</span></span>  

1. <span data-ttu-id="4b987-129">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="4b987-129">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="4b987-130">\<*Samples Path*\>\AdaptersDevelopment\HttpAdapter</span><span class="sxs-lookup"><span data-stu-id="4b987-130">\<*Samples Path*\>\AdaptersDevelopment\HttpAdapter</span></span>  

2. <span data-ttu-id="4b987-131">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="4b987-131">Run the file Setup.bat, which performs the following actions:</span></span>  

   -   <span data-ttu-id="4b987-132">HTTPAdapter とその依存関係すべてをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="4b987-132">Compiles the HTTPAdapter and all of its dependencies.</span></span>  

   -   <span data-ttu-id="4b987-133">アダプターの受信側で使用されるインターネット インフォメーション サービス (IIS) アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="4b987-133">Creates an Internet Information Services (IIS) application used by the receiver side of the adapter.</span></span>  

   <span data-ttu-id="4b987-134">IIS 7.0 でこの IIS アプリケーションを実行するアプリケーション プールの id、次のグループのメンバーであることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b987-134">On IIS 7.0, you must ensure the identity of the application pool running this IIS application is a member of the following groups:</span></span>  

-   <span data-ttu-id="4b987-135">BizTalk 分離ホスト ユーザー グループ。</span><span class="sxs-lookup"><span data-stu-id="4b987-135">BizTalk Isolated Host Users group.</span></span>  

-   <span data-ttu-id="4b987-136">IIS_WPG グループ。</span><span class="sxs-lookup"><span data-stu-id="4b987-136">IIS_WPG group.</span></span>  

-   <span data-ttu-id="4b987-137">IIS 7.0 では、統合 .NET モードで動作するアプリケーションを移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b987-137">On IIS 7.0, you must migrate the application to work with the Integrated .NET mode.</span></span> <span data-ttu-id="4b987-138">内容を含め、アプリケーションの構成を移行することができます、 \<httpHandlers\> (ウィンドウを管理者として実行する必要があります)、コマンド ライン ウィンドウから次を使用して、構成セクション。</span><span class="sxs-lookup"><span data-stu-id="4b987-138">You can migrate the application configuration, including the contents of the \<httpHandlers\> configuration section, by using the following from a command line window (the window must be running as Administrator):</span></span>  

    ```  
    %systemroot%\system32\inetsrv\APPCMD.EXE migrate config "Default Web Site/HttpReceive"  
    ```  

-   <span data-ttu-id="4b987-139">アプリケーションを移行した後は、クラシックと統合された .NET の両方のモードをおよびダウンレベルのプラットフォームに実行されます。</span><span class="sxs-lookup"><span data-stu-id="4b987-139">After you migrate your application, it will run in both Classic and Integrated .NET modes, as well as on downlevel platforms.</span></span>  

> [!NOTE]
>  <span data-ttu-id="4b987-140">エラーが報告されていないこと、ビルドおよび初期化プロセス中にこのサンプルを実行する前に確認してください。</span><span class="sxs-lookup"><span data-stu-id="4b987-140">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span>  

> [!NOTE]
>  <span data-ttu-id="4b987-141">開き、Setup.bat ファイルを実行することがなくこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b987-141">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name Utility (sn.exe).</span></span> <span data-ttu-id="4b987-142">このキー ペアは、生成されたアセンブリの署名に使用します。</span><span class="sxs-lookup"><span data-stu-id="4b987-142">Use this key pair to sign the resulting assemblies.</span></span>  

> [!NOTE]
>  <span data-ttu-id="4b987-143">Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="4b987-143">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="4b987-144">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="4b987-144">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  

## <a name="registering-the-sample-adapter"></a><span data-ttu-id="4b987-145">サンプル アダプターの登録</span><span class="sxs-lookup"><span data-stu-id="4b987-145">Registering the Sample Adapter</span></span>  

#### <a name="to-register-the-http-adapter-sample"></a><span data-ttu-id="4b987-146">HTTP アダプターのサンプルを登録するには</span><span class="sxs-lookup"><span data-stu-id="4b987-146">To register the HTTP Adapter sample</span></span>  

1. <span data-ttu-id="4b987-147">Windows エクスプ ローラーでのインストール ドライブに移動します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、順に移動します\<サンプル パス\>\AdaptersDevelopment\HTTPAdapter します。</span><span class="sxs-lookup"><span data-stu-id="4b987-147">In Windows Explorer, navigate to the installation drive for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and then navigate to \<Samples Path\>\AdaptersDevelopment\HTTPAdapter.</span></span>  

2. <span data-ttu-id="4b987-148">サンプル アダプターをレジストリに追加するには、ダブルクリック**HTTP.NET.reg**します。</span><span class="sxs-lookup"><span data-stu-id="4b987-148">To add the sample adapter to the registry, double-click **HTTP.NET.reg**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="4b987-149">HTTP.NET.reg にハードコードされたパスが含まれています、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="4b987-149">HTTP.NET.reg includes hard-coded paths to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation directory.</span></span> <span data-ttu-id="4b987-150">インストールしていない場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]既定の場所にアップグレードした場合、または、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の以前のバージョンからのインストール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、HTTP.NET.reg して適切なパスのファイルを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b987-150">If you did not install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the default location or if you upgraded your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation from a previous version of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you must modify the file HTTP.NET.reg with the appropriate paths.</span></span> <span data-ttu-id="4b987-151">指定されたファイルの正しい場所を指す、"OutboundAssemblyPath"と"AdapterMgmtAssemblyPath"の値に関連付けられたパスを更新します。</span><span class="sxs-lookup"><span data-stu-id="4b987-151">Update the paths associated with the "OutboundAssemblyPath" and "AdapterMgmtAssemblyPath" values to point to the correct location of the specified files.</span></span>  
   > 
   > [!IMPORTANT]
   >  <span data-ttu-id="4b987-152">BizTalk を 64 ビット コンピューターにインストールすると、hkey_classes_root \clsid\ レジストリ エントリのすべてのインスタンスを hkey_classes_root \wow6432node\clsid\ に変更、 **HTTP.NET.reg**レジストリ ファイル。</span><span class="sxs-lookup"><span data-stu-id="4b987-152">If you install BizTalk on a 64 bit machine, change all instances of the HKEY_CLASSES_ROOT\CLSID\ registry entry to HKEY_CLASSES_ROOT\Wow6432Node\CLSID\ in the **HTTP.NET.reg** registry file.</span></span>  

3. <span data-ttu-id="4b987-153">**レジストリ エディター**ダイアログ ボックスで、をクリックして**はい**サンプル アダプターをレジストリに追加し、クリックする **[ok]**。</span><span class="sxs-lookup"><span data-stu-id="4b987-153">In the **Registry Editor** dialog box, click **Yes** to add the sample adapter to the registry, and then click **OK**.</span></span>  

4. <span data-ttu-id="4b987-154">Windows エクスプ ローラーを閉じる、**ファイル** メニューのをクリックして**閉じます**します。</span><span class="sxs-lookup"><span data-stu-id="4b987-154">To close Windows Explorer, on the **File** menu, click **Close**.</span></span>  

## <a name="installing-the-sample-adapter"></a><span data-ttu-id="4b987-155">サンプル アダプターのインストール</span><span class="sxs-lookup"><span data-stu-id="4b987-155">Installing the Sample Adapter</span></span>  

#### <a name="to-install-the-http-adapter-sample"></a><span data-ttu-id="4b987-156">HTTP アダプター サンプルをインストールするには</span><span class="sxs-lookup"><span data-stu-id="4b987-156">To install the HTTP Adapter sample</span></span>  

1. <span data-ttu-id="4b987-157">をクリックして、**開始**メニューの **すべてのプログラム**を選択します[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、し、 **BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="4b987-157">Click the **Start** menu, select **All Programs**, select [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then select **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="4b987-158">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]ツリー、 **BizTalk グループ**ツリー、**プラットフォームの設定**ツリー。</span><span class="sxs-lookup"><span data-stu-id="4b987-158">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand the [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] tree, then expand the **BizTalk Group** tree, then expand the **Platform Settings** tree.</span></span>  

3. <span data-ttu-id="4b987-159">右クリック**アダプター**、 をクリックして**新規**、 をクリックし、**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="4b987-159">Right-click **Adapters**, click **New**, and then click **Adapter**.</span></span>  

4. <span data-ttu-id="4b987-160">**アダプター プロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4b987-160">In the **Adapter Properties** dialog box, do the following.</span></span>  


   |  <span data-ttu-id="4b987-161">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4b987-161">Use this</span></span>   |                  <span data-ttu-id="4b987-162">目的</span><span class="sxs-lookup"><span data-stu-id="4b987-162">To do this</span></span>                  |
   |-------------|----------------------------------------------|
   |    <span data-ttu-id="4b987-163">名前</span><span class="sxs-lookup"><span data-stu-id="4b987-163">Name</span></span>     |              <span data-ttu-id="4b987-164">型**HTTP.NET**します。</span><span class="sxs-lookup"><span data-stu-id="4b987-164">Type **HTTP.NET**.</span></span>              |
   |   <span data-ttu-id="4b987-165">[アダプター]</span><span class="sxs-lookup"><span data-stu-id="4b987-165">Adapter</span></span>   | <span data-ttu-id="4b987-166">選択**HTTP.NET**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="4b987-166">Select **HTTP.NET** from the drop-down list.</span></span> |
   | <span data-ttu-id="4b987-167">説明</span><span class="sxs-lookup"><span data-stu-id="4b987-167">Description</span></span> |      <span data-ttu-id="4b987-168">型**サンプル HTTP.NET アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="4b987-168">Type **Sample HTTP.NET Adapter**.</span></span>       |


5. <span data-ttu-id="4b987-169">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b987-169">Click **OK**.</span></span>  

6. <span data-ttu-id="4b987-170">アダプターは、BizTalk 管理コンソールの右側のウィンドウにあるアダプターの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b987-170">The adapter now appears in the list of adapters in the right window of the BizTalk Administration console.</span></span>  

## <a name="stopping-and-restarting-the-host-instance"></a><span data-ttu-id="4b987-171">停止して、ホスト インスタンスの再起動</span><span class="sxs-lookup"><span data-stu-id="4b987-171">Stopping and Restarting the Host Instance</span></span>  

#### <a name="to-stop-and-restart-the-host-instance-for-the-http-adapter-sample"></a><span data-ttu-id="4b987-172">停止して、HTTP アダプタのサンプルのホスト インスタンスを再起動するには</span><span class="sxs-lookup"><span data-stu-id="4b987-172">To stop and restart the host instance for the HTTP Adapter sample</span></span>  

1. <span data-ttu-id="4b987-173">をクリックして、**開始**メニューの **すべてのプログラム**を選択します[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]を選択し、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="4b987-173">Click the **Start** menu, select **All Programs**, select [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and select [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  

2. <span data-ttu-id="4b987-174">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]ツリー、**プラットフォームの設定**、 をクリック**ホスト インスタンス**します。</span><span class="sxs-lookup"><span data-stu-id="4b987-174">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand the [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] tree, then expand **Platform Settings**, and click **Host Instances**.</span></span>  

3. <span data-ttu-id="4b987-175">結果ウィンドウで、ホスト インスタンス (通常は、コンピューター名) を右クリックし、**停止**します。</span><span class="sxs-lookup"><span data-stu-id="4b987-175">In the results pane, right-click the host instance (typically, the computer name), and then click **Stop**.</span></span>  

    <span data-ttu-id="4b987-176">ホスト インスタンスの状態に変わる**Stopped**します。</span><span class="sxs-lookup"><span data-stu-id="4b987-176">The status of the host instance changes to **Stopped**.</span></span>  

4. <span data-ttu-id="4b987-177">結果ウィンドウで、ホスト インスタンスを右クリックし をクリックし、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="4b987-177">In the results pane, right-click the host instance, and then click **Start**.</span></span>  

   <span data-ttu-id="4b987-178">HTTP.NET アダプターは、アプリケーションで使用する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="4b987-178">The HTTP.NET adapter is now ready to be used by your application.</span></span> <span data-ttu-id="4b987-179">アダプターは、の形式を構成するときに、**仮想ディレクトリ**の形式は、トランスポートのプロパティ:/httpreceive/httpreceive.aspx?optionalQueryString します。</span><span class="sxs-lookup"><span data-stu-id="4b987-179">When configuring the adapter, the format for the **Virtual Directory** transport property is of the form: /httpreceive/httpreceive.aspx?optionalQueryString.</span></span>  

## <a name="comments"></a><span data-ttu-id="4b987-180">コメント</span><span class="sxs-lookup"><span data-stu-id="4b987-180">Comments</span></span>  
 <span data-ttu-id="4b987-181">提供される BaseAdapter クラスを使用して HTTP.NET アダプターは*\<サンプル パス\>* \AdaptersDevelopment\BaseAdapter\v1.0.2\\します。</span><span class="sxs-lookup"><span data-stu-id="4b987-181">The HTTP.NET adapter makes use of the BaseAdapter classes provided in *\<Samples Path\>* \AdaptersDevelopment\BaseAdapter\v1.0..2\\.</span></span> <span data-ttu-id="4b987-182">BaseAdapter プロジェクトで提供されるクラスはアダプターの開発を加速するためのものです。</span><span class="sxs-lookup"><span data-stu-id="4b987-182">The classes provided in the BaseAdapter project are intended to accelerate adapter development.</span></span> <span data-ttu-id="4b987-183">提供されるクラスの詳細については、BaseAdapter コードのコメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b987-183">Refer to the BaseAdapter code comments for details about the classes provided.</span></span>  

## <a name="see-also"></a><span data-ttu-id="4b987-184">参照</span><span class="sxs-lookup"><span data-stu-id="4b987-184">See Also</span></span>  
 <span data-ttu-id="4b987-185">[アダプターの登録](../core/registering-an-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4b987-185">[Registering an Adapter](../core/registering-an-adapter.md) </span></span>  
 <span data-ttu-id="4b987-186">[アダプタ サンプル – 使用状況](../core/adapter-samples-usage.md) </span><span class="sxs-lookup"><span data-stu-id="4b987-186">[Adapter Samples - Usage](../core/adapter-samples-usage.md) </span></span>  
 <span data-ttu-id="4b987-187">[カスタム アダプターの開発](../core/developing-custom-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="4b987-187">[Developing Custom Adapters](../core/developing-custom-adapters.md) </span></span>  
 <span data-ttu-id="4b987-188">[アダプター フレームワークとは何ですか。](../core/what-is-the-adapter-framework.md) </span><span class="sxs-lookup"><span data-stu-id="4b987-188">[What Is the Adapter Framework?](../core/what-is-the-adapter-framework.md) </span></span>  
 <span data-ttu-id="4b987-189">[アダプター フレームワーク ツールの使用](../core/using-the-adapter-framework-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4b987-189">[Using the Adapter Framework Tools](../core/using-the-adapter-framework-tools.md) </span></span>  
 <span data-ttu-id="4b987-190">[開発、受信アダプター](../core/developing-a-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4b987-190">[Developing a Receive Adapter](../core/developing-a-receive-adapter.md) </span></span>  
 <span data-ttu-id="4b987-191">[送信アダプターの開発](../core/developing-a-send-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4b987-191">[Developing a Send Adapter](../core/developing-a-send-adapter.md) </span></span>  
 <span data-ttu-id="4b987-192">[カスタム アダプターを展開する方法](../core/how-to-deploy-a-custom-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4b987-192">[How to Deploy a Custom Adapter](../core/how-to-deploy-a-custom-adapter.md) </span></span>  
 <span data-ttu-id="4b987-193">[アダプターのデザインに関するヒント](../core/tips-for-designing-your-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4b987-193">[Tips for Designing Your Adapter](../core/tips-for-designing-your-adapter.md) </span></span>  
 [<span data-ttu-id="4b987-194">アダプターのデザイン時構成</span><span class="sxs-lookup"><span data-stu-id="4b987-194">Adapter Design-Time Configuration</span></span>](../core/adapter-design-time-configuration.md)