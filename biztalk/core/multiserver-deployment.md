---
title: マルチ サーバー展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Windows SharePoint Services adapters], multi-server deployment
- planning, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, deploying
- Windows SharePoint Services adapters, multi-server deployment
- deploying, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, installing
ms.assetid: 0c6e2aa0-e873-461b-8101-9b0988019597
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e857aece2911aa9f1b3551f339524d2262cc0bf4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979763"
---
# <a name="multiserver-deployment"></a><span data-ttu-id="3168d-102">マルチサーバー展開</span><span class="sxs-lookup"><span data-stu-id="3168d-102">Multiserver Deployment</span></span>
<span data-ttu-id="3168d-103">このトピックでは、Windows SharePoint Services 用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アダプターを、マルチサーバー環境に設定および展開する場合の考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="3168d-103">This topic discusses multiserver setup and deployment considerations for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapter for Windows SharePoint Services.</span></span>  
  
## <a name="installing-the-windows-sharepoint-services-adapter-in-a-multiserver-deployment"></a><span data-ttu-id="3168d-104">マルチサーバー展開への Windows SharePoint Services アダプターのインストール</span><span class="sxs-lookup"><span data-stu-id="3168d-104">Installing the Windows SharePoint Services adapter in a multiserver deployment</span></span>  
 <span data-ttu-id="3168d-105">Windows SharePoint Service アダプター Web サービス コンポーネントを選択すると、送受信されるドキュメントを Windows SharePoint Services アダプターが Windows SharePoint Services 経由で処理するために必要なソフトウェアがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="3168d-105">Selecting the Windows SharePoint Service Adapter Web Service component installs the necessary software for the Windows SharePoint Services adapter to process incoming and outgoing documents through Windows SharePoint Services.</span></span> <span data-ttu-id="3168d-106">この Web サービスは、Windows SharePoint Services がインストールされているサーバーにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3168d-106">This Web service must be installed on the server where Windows SharePoint Services is installed.</span></span>  
  
 <span data-ttu-id="3168d-107">アダプター Web サービスでは、複数の SharePoint サイトを、同一の IIS サイトにあるか、異なる IIS サイトにあるかにかかわらず、処理できます。</span><span class="sxs-lookup"><span data-stu-id="3168d-107">The adapter Web service can handle multiple SharePoint sites regardless of whether they are on the same IIS site or on different IIS sites.</span></span>  
  
 <span data-ttu-id="3168d-108">Windows SharePoint Services アダプターには、次の 3 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="3168d-108">The Windows SharePoint Services Adapter has three components:</span></span>  
  
- <span data-ttu-id="3168d-109">ランタイム コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3168d-109">Runtime components</span></span>  
  
- <span data-ttu-id="3168d-110">デザイン時コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3168d-110">Design time components</span></span>  
  
- <span data-ttu-id="3168d-111">アダプター Web サービス</span><span class="sxs-lookup"><span data-stu-id="3168d-111">Adapter Web service</span></span>  
  
  <span data-ttu-id="3168d-112">アダプター ランタイムは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム機能によって自動的にインストールおよび構成されます。</span><span class="sxs-lookup"><span data-stu-id="3168d-112">The adapter runtime is installed and configured automatically by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Runtime feature.</span></span> <span data-ttu-id="3168d-113">アダプターのデザイン時コンポーネントは、その他の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 機能によってインストールおよび構成されます。</span><span class="sxs-lookup"><span data-stu-id="3168d-113">The adapter design time components are installed and configured with other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features.</span></span> <span data-ttu-id="3168d-114">デザイン時コンポーネントを操作するには、管理ツール、開発ツール、SDK に含まれているツールか、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム機能を使用して、Windows SharePoint Services ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="3168d-114">You interact with the design time components by creating Windows SharePoint Services ports through tools that are included in the Administration Tools, Developer Tools, and SDK or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Runtime features.</span></span> <span data-ttu-id="3168d-115">ランタイム コンポーネントおよびデザイン時コンポーネントの構成オプションは、カスタマイズできません。</span><span class="sxs-lookup"><span data-stu-id="3168d-115">You cannot customize any configuration options for runtime and design time components.</span></span> <span data-ttu-id="3168d-116">Windows SharePoint Services アダプター Web サービス オプションのみをカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="3168d-116">You can customize only the Windows SharePoint Services adapter Web Service options.</span></span>  
  
  <span data-ttu-id="3168d-117">SharePoint Enabled Hosts グループのメンバーだけでは、アダプター Web サービスを呼び出すアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="3168d-117">Only members of the SharePoint Enabled Hosts group will have permissions to invoke the adapter Web service.</span></span> <span data-ttu-id="3168d-118">Windows SharePoint Services アダプターのランタイムで必要な Windows SharePoint Services のアクセス許可の詳細については、セキュリティ」セクションを参照してください。 [、Windows SharePoint Services アダプターとは何ですか?](../core/what-is-the-windows-sharepoint-services-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="3168d-118">For more information about the Windows SharePoint Services permissions needed by the Windows SharePoint Services adapter runtime, see the security section in [What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3168d-119">BAS をインストールするとき、Windows SharePoint Services アダプター Web サービス コンポーネントが自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="3168d-119">The Windows SharePoint Services adapter Web service component will be automatically selected if you choose to install BAS.</span></span>  
  
#### <a name="to-install-the-windows-sharepoint-services-adapter"></a><span data-ttu-id="3168d-120">Windows SharePoint Services アダプターをインストールするには</span><span class="sxs-lookup"><span data-stu-id="3168d-120">To install the Windows SharePoint Services adapter</span></span>  
  
1. <span data-ttu-id="3168d-121">インストール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3168d-121">Install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="3168d-122">詳細については、[BizTalk Server 2013 および 2013 R2 のインストールの概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3168d-122">For more information, see [Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5).</span></span>  
  
2. <span data-ttu-id="3168d-123">**コンポーネントのインストール**画面で、**使用可能なコンポーネント\*\*\*\*追加ソフトウェア**を選択します**Windows SharePoint Services アダプターWeb サービス**します。</span><span class="sxs-lookup"><span data-stu-id="3168d-123">On the **Component Installation** screen, under **Available Components**, under **Additional Software**, select **Windows SharePoint Services Adapter Web service**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3168d-124">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイムをホストするコンピューター、および Windows SharePoint Services を実行するコンピューターでセットアップと構成を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3168d-124">You must run setup and configuration on the computer that hosts the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime and the computer running Windows SharePoint Services.</span></span>  
  
## <a name="configuring-the-windows-sharepoint-services-adapter-web-service-in-a-multiserver-deployment"></a><span data-ttu-id="3168d-125">マルチサーバー展開の Windows SharePoint Services アダプター Web サービスの構成</span><span class="sxs-lookup"><span data-stu-id="3168d-125">Configuring the Windows SharePoint Services adapter Web service in a multiserver deployment</span></span>  
 <span data-ttu-id="3168d-126">Windows SharePoint Services アダプターは、BizTalk Server 構成を使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="3168d-126">You configure the Windows SharePoint Services adapter using the BizTalk Server Configuration.</span></span> <span data-ttu-id="3168d-127">これらのツールの詳細については、[BizTalk Server 2013 および 2013 R2 の構成の概要](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3168d-127">For more information about these tools, see [Configuration Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72).</span></span>  
  
### <a name="using-a-custom-configuration"></a><span data-ttu-id="3168d-128">ユーザー構成の使用</span><span class="sxs-lookup"><span data-stu-id="3168d-128">Using a custom configuration</span></span>  
 <span data-ttu-id="3168d-129">BizTalk Server 構成では、ローカル コンピューターにインストールした機能の構成状態に関する高レベルの分析が提供されます。</span><span class="sxs-lookup"><span data-stu-id="3168d-129">The BizTalk Server Configuration provides a high-level analysis of the configuration state of the features you have installed on the local computer.</span></span> <span data-ttu-id="3168d-130">このツールを使用すると、機能の構成と構成解除、セキュリティ設定の構成、および他のコンピューターの構成のインポートとエクスポートを行えます。</span><span class="sxs-lookup"><span data-stu-id="3168d-130">The tool allows you to configure and unconfigure features, configure security settings, and import and export configurations from other computers.</span></span>  
  
 <span data-ttu-id="3168d-131">使用して、 **Windows SharePoint Services**ページはこのコンピューターに Windows SharePoint Services アダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="3168d-131">Use the **Windows SharePoint Services** page to configure the Windows SharePoint Services adapter on this computer.</span></span> <span data-ttu-id="3168d-132">次の表は、構成のオプションを示しています。</span><span class="sxs-lookup"><span data-stu-id="3168d-132">The following table lists the configuration options.</span></span>  
  
|<span data-ttu-id="3168d-133">プロパティ</span><span class="sxs-lookup"><span data-stu-id="3168d-133">Use this</span></span>|<span data-ttu-id="3168d-134">目的</span><span class="sxs-lookup"><span data-stu-id="3168d-134">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="3168d-135">**このコンピューターで Windows SharePoint Services アダプターを有効にします。**</span><span class="sxs-lookup"><span data-stu-id="3168d-135">**Enable Windows SharePoint Services Adapter on this computer**</span></span>|<span data-ttu-id="3168d-136">選択**このコンピューターで Windows SharePoint Services アダプターを有効にする**このコンピューターでアダプターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3168d-136">Select **Enable Windows SharePoint Services Adapter on this computer** to enable the adapter on this computer.</span></span>|  
|<span data-ttu-id="3168d-137">**Windows グループ**</span><span class="sxs-lookup"><span data-stu-id="3168d-137">**Windows group**</span></span>|<span data-ttu-id="3168d-138">**Windows グループ**一覧は、BizTalk SharePoint アダプター有効になっているホスト Windows グループの編集可能なビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="3168d-138">The **Windows group** list provides a view that you can edit of the BizTalk SharePoint Adapter Enabled Hosts Windows group.</span></span>|  
|<span data-ttu-id="3168d-139">**Windows SharePoint Services アダプター Web サイト**</span><span class="sxs-lookup"><span data-stu-id="3168d-139">**Windows SharePoint Services Adapter Web site**</span></span>|<span data-ttu-id="3168d-140">Windows SharePoint Services アダプター Web サービスをホストする Web サイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="3168d-140">Select the Web site that will host the Windows SharePoint Services adapter Web service.</span></span>|  
  
 <span data-ttu-id="3168d-141">ユーザー構成を使用して Windows SharePoint Services アダプターを構成する際は、次のことが行われます。</span><span class="sxs-lookup"><span data-stu-id="3168d-141">When you configure the Windows SharePoint Services adapter using custom configuration, the following happens:</span></span>  
  
-   <span data-ttu-id="3168d-142">別の Windows グループを指定しない限り、既定で SharePoint Enabled Hosts Windows グループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3168d-142">The SharePoint Enabled Hosts Windows group is created by default unless you specify another Windows group</span></span>  
  
-   <span data-ttu-id="3168d-143">別の Web サイトを指定しない限り、Windows SharePoint Services アダプターのホストには既定の Web サイトが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3168d-143">The Default Web Site is used to host the Windows SharePoint Services adapter unless you specify another Web site</span></span>  
  
-   <span data-ttu-id="3168d-144">BTSSharePointAdapterWSAppPool アプリケーション プールが、Windows SharePoint Services アプリケーション プールを実行するために使用するアカウントで実行されるように作成および構成されます。</span><span class="sxs-lookup"><span data-stu-id="3168d-144">The BTSSharePointAdapterWSAppPool application pool is created and configured to run under the account that is also used to run the Windows SharePoint Services application pool</span></span>  
  
-   <span data-ttu-id="3168d-145">BTSharePointAdapterWS 仮想アプリケーションが、BTSSharePointAdapterWSAppPool アプリケーション プールで実行されるように作成および構成されます。</span><span class="sxs-lookup"><span data-stu-id="3168d-145">The BTSharePointAdapterWS virtual application is created and configured to run in the BTSSharePointAdapterWSAppPool application pool</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3168d-146">この仮想ディレクトリが既に存在する場合は、構成を行ってもメタベースのプロパティが更新されません。</span><span class="sxs-lookup"><span data-stu-id="3168d-146">If this virtual directory already exists, configuration will not update the properties in the metabase.</span></span> <span data-ttu-id="3168d-147">仮想ディレクトリを削除して、構成を再実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3168d-147">You must delete the virtual directory and run configuration again.</span></span>  
  
- <span data-ttu-id="3168d-148">BTSharePointAdapterWS 仮想アプリケーションに Web サービスが含められます。</span><span class="sxs-lookup"><span data-stu-id="3168d-148">The BTSharePointAdapterWS virtual application contains the Web service</span></span>  
  
  <span data-ttu-id="3168d-149">BizTalk Server の構成の詳細については、[のインポートとエクスポートの BizTalk Server 構成](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3168d-149">For more information about the BizTalk Server Configuration, see [Import and Export BizTalk Server Configuration](../install-and-config-guides/import-and-export-biztalk-server-configuration.md).</span></span>  
  
##### <a name="to-configure-the-windows-sharepoint-services-adapter-by-using-custom-configuration"></a><span data-ttu-id="3168d-150">ユーザー設定を使用して Windows SharePoint Services アダプターを構成するには</span><span class="sxs-lookup"><span data-stu-id="3168d-150">To configure the Windows SharePoint Services adapter by using custom configuration</span></span>  
  
1. <span data-ttu-id="3168d-151">**BizTalk Server 構成**を選択、 **SharePoint アダプター**ノード。</span><span class="sxs-lookup"><span data-stu-id="3168d-151">In the **BizTalk Server Configuration**, select the **SharePoint adapter** node.</span></span>  
  
2. <span data-ttu-id="3168d-152">選択**このコンピューターで Windows SharePoint Services アダプターを有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="3168d-152">Select **Enable Windows SharePoint Services Adapter on this computer**.</span></span>  
  
3. <span data-ttu-id="3168d-153">**Windows グループ**、Windows SharePoint Services アダプターを使用する Windows グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="3168d-153">Under **Windows Group**, select the Windows group you will be using for the Windows SharePoint Services adapter.</span></span> <span data-ttu-id="3168d-154">既定では、SharePoint Enabled Hosts です。</span><span class="sxs-lookup"><span data-stu-id="3168d-154">By default, this is SharePoint Enabled Hosts.</span></span>  
  
4. <span data-ttu-id="3168d-155">**Windows SharePoint Services アダプター Web サイト**ドロップダウン ボックスで、Web サイトのアダプター コンポーネントのインストール先を選択します。</span><span class="sxs-lookup"><span data-stu-id="3168d-155">In the **Windows SharePoint Services Adapter Web Site** drop-down box, select the Web site where the adapter components will be installed.</span></span> <span data-ttu-id="3168d-156">特に選択しない場合、既定の Web サイトが選択されます。</span><span class="sxs-lookup"><span data-stu-id="3168d-156">By default, this is the Default Web Site.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="3168d-157">他の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンポーネントがインストールされていないリモート SharePoint Server コンピューターに Windows SharePoint Services アダプター Web サイトをインストールする構成は、完全にサポートされている構成です。</span><span class="sxs-lookup"><span data-stu-id="3168d-157">The installation of the Windows SharePoint Services Adapter Web site on a remote SharePoint Server computer that does not have any other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] components installed is a fully supported configuration.</span></span>  
  
5. <span data-ttu-id="3168d-158">**[構成の適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3168d-158">Click **Apply Configuration**.</span></span>  
  
## <a name="considerations-for-a-multiserver-deployment"></a><span data-ttu-id="3168d-159">マルチサーバー展開に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="3168d-159">Considerations for a multiserver deployment</span></span>  
 <span data-ttu-id="3168d-160">![](../core/media/adapters-wss-multiserver-screenshot01.gif "Adapters_WSS_Multiserver_Screenshot01")</span><span class="sxs-lookup"><span data-stu-id="3168d-160">![](../core/media/adapters-wss-multiserver-screenshot01.gif "Adapters_WSS_Multiserver_Screenshot01")</span></span>  
  
### <a name="general-considerations"></a><span data-ttu-id="3168d-161">全般的な考慮事項</span><span class="sxs-lookup"><span data-stu-id="3168d-161">General considerations</span></span>  
 <span data-ttu-id="3168d-162">マルチサーバー環境で Windows SharePoint Services アダプターを設定および展開する際は、次のことを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="3168d-162">When you set up and deploy the Windows SharePoint Services adapter in a multiserver environment, consider the following:</span></span>  
  
- <span data-ttu-id="3168d-163">各サーバー上で、BizTalk Service アカウントを SharePoint Enabled Hosts Windows グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="3168d-163">Add the BizTalk Service account to the SharePoint Enabled Hosts Windows group on each server.</span></span>  
  
- <span data-ttu-id="3168d-164">SharePoint のサーバーの管理ツールを使用して、SharePoint Enabled Hosts グループを SharePoint の関係者ロールに追加します。</span><span class="sxs-lookup"><span data-stu-id="3168d-164">Add the SharePoint Enabled Hosts group to the SharePoint Contributors role using the SharePoint Central Administration tool.</span></span>  
  
- <span data-ttu-id="3168d-165">[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] では、SharePoint アダプター Web サービスを実行する ID に次のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="3168d-165">On [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], the identity under which the SharePoint Adapter Web Service runs needs the following permissions:</span></span>  
  
   <span data-ttu-id="3168d-166">**読み取り**に対するアクセス許可、 **Program files \microsoft BizTalk Server\<バージョン\>\Business Activity Services\BTSharePointV3AdapterWS**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="3168d-166">**Read** permissions on the **Program Files\Microsoft BizTalk Server \<version\>\Business Activity Services\BTSharePointV3AdapterWS** folder.</span></span> <span data-ttu-id="3168d-167">Windows の 64 ビット バージョンを使用している場合と[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、アクセス許可を設定する必要があります、 **Program Files (x86) \Microsoft BizTalk Server\<バージョン\>\Business Activity Services\BTSharePointV3AdapterWS**</span><span class="sxs-lookup"><span data-stu-id="3168d-167">If using a 64-bit version of Windows and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], permissions need to be set on the **Program Files (x86)\Microsoft BizTalk Server \<version\>\Business Activity Services\BTSharePointV3AdapterWS**</span></span>  
  
   <span data-ttu-id="3168d-168">**読み取り**次のレジストリ キーに対する権限: **hkey_local_machine \software\microsoft\shared Server\Extensions\12.0\Secure\ConfigDB**します。</span><span class="sxs-lookup"><span data-stu-id="3168d-168">**Read** permission on the following registry key: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Shared Tools\Web Server\Extensions\12.0\Secure\ConfigDB**.</span></span>  
  
   <span data-ttu-id="3168d-169">SharePoint データベースを含む SQL Server に対するログオン アクセス許可。</span><span class="sxs-lookup"><span data-stu-id="3168d-169">Logon permissions on the SQL Server that contains the Sharepoint databases.</span></span>  
  
   <span data-ttu-id="3168d-170">メンバー、**パブリック**と**WSS_Content_Application_Pools** SharePoint 構成データベース内のロール。</span><span class="sxs-lookup"><span data-stu-id="3168d-170">A member of the **Public** and **WSS_Content_Application_Pools** roles within the SharePoint configuration database.</span></span>  
  
   <span data-ttu-id="3168d-171">メンバー、**パブリック**と**db 所有者**SharePoint コンテンツ データベース内のロール。</span><span class="sxs-lookup"><span data-stu-id="3168d-171">A member of the **Public** and **db owner** roles within the SharePoint content database.</span></span>  
  
- <span data-ttu-id="3168d-172">Web サービスをインストールする Web サイトは、SharePoint Services Web サイトとして拡張しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="3168d-172">The Web site that you install the Web service on must be extended as a SharePoint Services Web site.</span></span>  
  
- <span data-ttu-id="3168d-173">Windows SharePoint Services アダプターは、サイレント インストールでインストールおよび構成できます。</span><span class="sxs-lookup"><span data-stu-id="3168d-173">You can install and configure the Windows SharePoint Services adapter using a silent installation.</span></span> <span data-ttu-id="3168d-174">詳細については、[付録 a: サイレント インストール](../install-and-config-guides/appendix-a-silent-installation.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3168d-174">For more information, see [Appendix A: Silent Installation](../install-and-config-guides/appendix-a-silent-installation.md).</span></span>  
  
### <a name="considerations-for-network-load-balancing-nlb"></a><span data-ttu-id="3168d-175">ネットワーク負荷分散 (NLB) に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="3168d-175">Considerations for network load balancing (NLB)</span></span>  
 <span data-ttu-id="3168d-176">Windows SharePoint Services 用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アダプターを使用すると、同一グループ内に構成されている複数の BizTalk サーバーと共に Windows SharePoint Services サーバーを NLB クラスターにすることができます。</span><span class="sxs-lookup"><span data-stu-id="3168d-176">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapter for Windows SharePoint Services supports NLB clustering of the Windows SharePoint Services servers along with multiple BizTalk servers that are configured in the same group.</span></span> <span data-ttu-id="3168d-177">この場合、SharePoint のマニュアルで推奨されているように、Windows SharePoint Services を NLB クラスターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3168d-177">For this, Windows SharePoint Services must be installed on the NLB cluster as recommended by SharePoint documentation.</span></span>  
  
 <span data-ttu-id="3168d-178">NLB を設定したマルチサーバー環境で Windows SharePoint Services アダプターを設定および展開する際は、次のことを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="3168d-178">When you set up and deploy the Windows SharePoint Services adapter in a multiserver environment with NLB, consider the following:</span></span>  
  
-   <span data-ttu-id="3168d-179">既存の BizTalk 管理データベースを指すようにオプションを選択することによって、Windows SharePoint Services を構成します。</span><span class="sxs-lookup"><span data-stu-id="3168d-179">Configure Windows SharePoint Services by selecting the option to point to an existing BizTalk Management database.</span></span> <span data-ttu-id="3168d-180">1 台目のコンピューターで作成した BizTalk 管理データベースを指すように設定します。</span><span class="sxs-lookup"><span data-stu-id="3168d-180">Point to the BizTalk Management database created on the first computer.</span></span> <span data-ttu-id="3168d-181">これは、Windows SharePoint Services に対して、Web サーバー環境を使用することを示す操作です。</span><span class="sxs-lookup"><span data-stu-id="3168d-181">This indicates to Windows SharePoint Services that you intend to have a Web server environment.</span></span> <span data-ttu-id="3168d-182">既存のコンテンツ データベースを指すことによって、Web サイトを拡張します。</span><span class="sxs-lookup"><span data-stu-id="3168d-182">Extend the Web site by pointing to the existing content database.</span></span>  
  
-   <span data-ttu-id="3168d-183">Web サーバー環境内の各 Windows SharePoint Services コンピューターで、同一の Web サイト (ポート 80 の既定の Web サイトなど) を拡張する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3168d-183">You must extend the same Web site (for example, the default Web site on port 80) on each Windows SharePoint Services computer in the Web server environment.</span></span>  
  
-   <span data-ttu-id="3168d-184">BTSharePointAdapterWS を各 NLB ホストと同様にインストールおよび構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3168d-184">The BTSharePointAdapterWS must be installed and configured the same way on each of the NLB hosts.</span></span> <span data-ttu-id="3168d-185">構成する必要がある NLB 設定を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3168d-185">You must configure the following NLB settings:</span></span>  
  
    -   <span data-ttu-id="3168d-186">プロトコル: TCP</span><span class="sxs-lookup"><span data-stu-id="3168d-186">Protocol: TCP</span></span>  
  
    -   <span data-ttu-id="3168d-187">ポート: 80 (Windows SharePoint Services アダプター Web サービスがインストールおよび構成された IIS Web サイトの HTTP ポート)</span><span class="sxs-lookup"><span data-stu-id="3168d-187">Ports: 80 (The HTTP Port of the IIS Web site where the Windows SharePoint Services adapter Web service has been installed and configured)</span></span>  
  
    -   <span data-ttu-id="3168d-188">フィルターのモード: 複数ホスト</span><span class="sxs-lookup"><span data-stu-id="3168d-188">Filtering mode: Multiple host</span></span>  
  
    -   <span data-ttu-id="3168d-189">関係: なし</span><span class="sxs-lookup"><span data-stu-id="3168d-189">Affinity: None</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3168d-190">この設定はサイトが HTTPS 用に構成されていない場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="3168d-190">This setting can be used only if the site is not configured for HTTPS.</span></span> <span data-ttu-id="3168d-191">HTTPS を構成しているサイトに BTSharePointAdapterWS Web サービスをインストールする場合、単一クライアントの関係を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3168d-191">If the BTSharePointAdapterWS Web service is installed on a site with HTTPS, then you must use Single-client affinity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3168d-192">参照</span><span class="sxs-lookup"><span data-stu-id="3168d-192">See Also</span></span>  
 <span data-ttu-id="3168d-193">[Windows SharePoint Services アダプター](../core/windows-sharepoint-services-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="3168d-193">[Windows SharePoint Services Adapter](../core/windows-sharepoint-services-adapter.md) </span></span>  
 [<span data-ttu-id="3168d-194">シングルサーバー展開</span><span class="sxs-lookup"><span data-stu-id="3168d-194">Single-Server Deployment</span></span>](../core/single-server-deployment.md)