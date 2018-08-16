---
title: シングル サーバー配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services adapters, deploying
- configuring [Windows SharePoint Services adapters], customizing
- deploying, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, installing
- Windows SharePoint Services adapters, configuring
- configuring [Windows SharePoint Services adapters], single-server deployment
- Windows SharePoint Services adapters, single-server deployment
ms.assetid: 94ba8241-9a30-46ca-b962-721e2d00f420
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62b99fd47ec04ecfd0286a694f21da733339885c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996147"
---
# <a name="single-server-deployment"></a><span data-ttu-id="1013b-102">シングルサーバー展開</span><span class="sxs-lookup"><span data-stu-id="1013b-102">Single-Server Deployment</span></span>
<span data-ttu-id="1013b-103">このトピックでは、Windows SharePoint Services 用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アダプターを、シングルサーバー環境に設定および展開する場合の考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="1013b-103">This topic discusses single-server setup and deployment considerations for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapter for Windows SharePoint Services.</span></span>  
  
## <a name="installing-the-windows-sharepoint-services-adapter-in-a-single-server-deployment"></a><span data-ttu-id="1013b-104">シングルサーバー展開への Windows SharePoint Services アダプターのインストール</span><span class="sxs-lookup"><span data-stu-id="1013b-104">Installing the Windows SharePoint Services adapter in a single-server deployment</span></span>  
 <span data-ttu-id="1013b-105">Windows SharePoint Service アダプター Web サービス コンポーネントを選択すると、送受信されるドキュメントを Windows SharePoint Services アダプターが Windows SharePoint Services 経由で処理するために必要なソフトウェアが、インストールされます。</span><span class="sxs-lookup"><span data-stu-id="1013b-105">Selecting the Windows SharePoint Service adapter Web service component installs the necessary software for the Windows SharePoint Services adapter to process incoming and outgoing documents through Windows SharePoint Services.</span></span> <span data-ttu-id="1013b-106">この Web サービスは、Windows SharePoint Services がインストールされているサーバーにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1013b-106">This Web service must be installed on the server where Windows SharePoint Services is installed.</span></span> <span data-ttu-id="1013b-107">アダプター Web サービスでは、ビジネス アクティビティ サービス (BAS) をホストする Web サイトを含めた複数の SharePoint サイトを、同一の IIS サイトにあるか、異なる IIS サイトにあるかにかかわらず、処理できます。</span><span class="sxs-lookup"><span data-stu-id="1013b-107">The adapter Web service can handle multiple SharePoint sites including the Web site that hosts Business Activity Services (BAS), regardless of whether they are on the same IIS site or on different IIS sites.</span></span>  
  
 <span data-ttu-id="1013b-108">Windows SharePoint Services アダプターでは、次の 3 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="1013b-108">The Windows SharePoint Services adapter has three components:</span></span>  
  
- <span data-ttu-id="1013b-109">ランタイム コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1013b-109">Runtime components</span></span>  
  
- <span data-ttu-id="1013b-110">デザイン時コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1013b-110">Design time components</span></span>  
  
- <span data-ttu-id="1013b-111">アダプター Web サービス</span><span class="sxs-lookup"><span data-stu-id="1013b-111">Adapter Web service</span></span>  
  
  <span data-ttu-id="1013b-112">アダプター ランタイムは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム機能によって自動的にインストールおよび構成されます。</span><span class="sxs-lookup"><span data-stu-id="1013b-112">The adapter runtime is installed and configured automatically by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Runtime feature.</span></span> <span data-ttu-id="1013b-113">アダプターのデザイン時コンポーネントがインストールされ、他の構成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]機能します。</span><span class="sxs-lookup"><span data-stu-id="1013b-113">The adapter design time components are installed and configured with the other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features.</span></span> <span data-ttu-id="1013b-114">デザイン時コンポーネントを操作するには、管理ツール、開発ツール、SDK に含まれているツールか、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム機能を使用して、Windows SharePoint Services ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="1013b-114">You interact with the design time components by creating Windows SharePoint Services ports through tools that are included in the Administration Tools, Developer Tools, and SDK or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Runtime features.</span></span> <span data-ttu-id="1013b-115">ランタイム コンポーネントおよびデザイン時コンポーネントの構成オプションは、カスタマイズできません。</span><span class="sxs-lookup"><span data-stu-id="1013b-115">You cannot customize any configuration options for runtime and design time components.</span></span> <span data-ttu-id="1013b-116">Windows SharePoint Services アダプター Web サービス オプションのみカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="1013b-116">You can customize only the Windows SharePoint Service adapter Web service options.</span></span>  
  
  <span data-ttu-id="1013b-117">アダプター Web サービスを呼び出すアクセス許可は、SharePoint Enabled Hosts グループのメンバーのみに与えられます。</span><span class="sxs-lookup"><span data-stu-id="1013b-117">Only members of the SharePoint Enabled Hosts group have permissions to invoke the adapter Web service.</span></span> <span data-ttu-id="1013b-118">Windows SharePoint Services アダプターのランタイムで必要な Windows SharePoint Services のアクセス許可の詳細については、セキュリティ」セクションを参照してください。 [、Windows SharePoint Services アダプターとは何ですか?](../core/what-is-the-windows-sharepoint-services-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="1013b-118">For more information about the Windows SharePoint Services permissions needed by the Windows SharePoint Services adapter runtime, see the security section in [What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1013b-119">BAS をインストールするとき、Windows SharePoint Services アダプター Web サービス コンポーネントが自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="1013b-119">The Windows SharePoint Services adapter Web service component will be automatically selected if you choose to install BAS.</span></span>  
  
#### <a name="to-install-the-windows-sharepoint-services-adapter"></a><span data-ttu-id="1013b-120">Windows SharePoint Services アダプターをインストールするには</span><span class="sxs-lookup"><span data-stu-id="1013b-120">To install the Windows SharePoint Services adapter</span></span>  
  
1.  <span data-ttu-id="1013b-121">BizTalk Server をインストールします。</span><span class="sxs-lookup"><span data-stu-id="1013b-121">Install BizTalk Server.</span></span> <span data-ttu-id="1013b-122">詳細については、次を参照してください。 [BizTalk Server 2013 および 2013 R2 のインストールの概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)します。</span><span class="sxs-lookup"><span data-stu-id="1013b-122">For more information, see [Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5).</span></span>  
  
2.  <span data-ttu-id="1013b-123">**コンポーネントのインストール**画面で、**使用可能なコンポーネント****追加ソフトウェア**を選択します**Windows SharePoint Services アダプターWeb サービス**します。</span><span class="sxs-lookup"><span data-stu-id="1013b-123">On the **Component Installation** screen, under **Available Components**, under **Additional Software**, select **Windows SharePoint Services Adapter Web service**.</span></span>  
  
## <a name="configuring-the-windows-sharepoint-services-adapter-web-service-in-a-single-server-deployment"></a><span data-ttu-id="1013b-124">シングルサーバー展開の Windows SharePoint Services アダプター Web サービスの構成</span><span class="sxs-lookup"><span data-stu-id="1013b-124">Configuring the Windows SharePoint Services adapter Web service in a single-server deployment</span></span>  
 <span data-ttu-id="1013b-125">Windows SharePoint Services アダプターは、基本構成またはユーザー構成のいずれかを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="1013b-125">You can configure the Windows SharePoint Services adapter using either a basic configuration or a custom configuration.</span></span> <span data-ttu-id="1013b-126">これらのツールの詳細については、次を参照してください。 [BizTalk Server 2013 および 2013 R2 の構成の概要](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)します。</span><span class="sxs-lookup"><span data-stu-id="1013b-126">For more information about these tools, see [Configuration Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72).</span></span>  
  
### <a name="using-a-basic-configuration"></a><span data-ttu-id="1013b-127">基本構成の使用</span><span class="sxs-lookup"><span data-stu-id="1013b-127">Using a basic configuration</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="1013b-128"> では、サーバーの構成に既定の設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1013b-128"> allows you to configure the server by using default settings.</span></span> <span data-ttu-id="1013b-129">サーバーの基本構成は、構成ウィザードで入力するデータベース サーバー名、ユーザー名、およびパスワードを使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="1013b-129">The default settings for the server are configured using the database server name, user name, and password that you enter into the configuration wizard.</span></span> <span data-ttu-id="1013b-130">基本構成を使用して Windows SharePoint Services アダプター Web サービスを構成する際は、次のことが行われます。</span><span class="sxs-lookup"><span data-stu-id="1013b-130">When you configure the Windows SharePoint Services adapter Web service using a basic configuration, the following happens:</span></span>  
  
-   <span data-ttu-id="1013b-131">SharePoint Enabled Hosts Windows グループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1013b-131">The SharePoint Enabled Hosts Windows group is created.</span></span>  
  
-   <span data-ttu-id="1013b-132">Windows SharePoint Service アダプターをホストする Web サイトには、既定の Web サイトが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1013b-132">The Default Web Site is used to host the Windows SharePoint Services Adapter</span></span>  
  
-   <span data-ttu-id="1013b-133">BTSSharePointAdapterWSAppPool アプリケーション プールが作成され、Windows SharePoint Services アプリケーション プールの実行にも使用されるアカウントで実行するように構成します。</span><span class="sxs-lookup"><span data-stu-id="1013b-133">The BTSSharePointAdapterWSAppPool application pool is created and configured to run under the account that is also used to run the Windows SharePoint Services application pool.</span></span>  
  
-   <span data-ttu-id="1013b-134">BTSharePointAdapterWS 仮想アプリケーションが、BTSSharePointAdapterWSAppPool アプリケーション プールで実行されるように作成および構成されます。</span><span class="sxs-lookup"><span data-stu-id="1013b-134">The BTSharePointAdapterWS virtual application is created and configured to run in the BTSSharePointAdapterWSAppPool application pool</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1013b-135">この仮想ディレクトリが既に存在する場合は、構成を行ってもメタベースのプロパティが更新されません。</span><span class="sxs-lookup"><span data-stu-id="1013b-135">If this virtual directory already exists, configuration will not update the properties in the metabase.</span></span> <span data-ttu-id="1013b-136">仮想ディレクトリを削除し、構成を再実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1013b-136">You must delete the virtual directory, and run configuration again.</span></span>  
  
- <span data-ttu-id="1013b-137">BTSharePointAdapterWS 仮想アプリケーションに Web サービスが含められます。</span><span class="sxs-lookup"><span data-stu-id="1013b-137">The BTSharePointAdapterWS virtual application contains the Web service</span></span>  
  
  <span data-ttu-id="1013b-138">基本的な構成の詳細については、次を参照してください。[基本的な構成](http://msdn.microsoft.com/library/abdf3eb5-9779-47ff-bc97-2209eb4b12f5)します。</span><span class="sxs-lookup"><span data-stu-id="1013b-138">For more information about basic configuration, see [Basic Configuration](http://msdn.microsoft.com/library/abdf3eb5-9779-47ff-bc97-2209eb4b12f5).</span></span>  
  
### <a name="using-a-custom-configuration"></a><span data-ttu-id="1013b-139">ユーザー構成の使用</span><span class="sxs-lookup"><span data-stu-id="1013b-139">Using a custom configuration</span></span>  
 <span data-ttu-id="1013b-140">BizTalk Server 構成では、ローカル コンピューターにインストールした機能の構成状態に関する高レベルの分析が提供されます。</span><span class="sxs-lookup"><span data-stu-id="1013b-140">The BizTalk Server Configuration provides a high-level analysis of the configuration state of the features you have installed on the local computer.</span></span> <span data-ttu-id="1013b-141">このツールを使用すると、機能の構成と構成解除、セキュリティ設定の構成、および他のコンピューターの構成のインポートとエクスポートを行えます。</span><span class="sxs-lookup"><span data-stu-id="1013b-141">The tool allows you to configure and unconfigure features, configure security settings, and import and export configurations from other computers.</span></span>  
  
 <span data-ttu-id="1013b-142">使用して、 **Windows SharePoint Services アダプター Web サービス**ページはこのコンピューターに Windows SharePoint Services アダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="1013b-142">Use the **Windows SharePoint Services Adapter Web Service** page to configure the Windows SharePoint Services adapter on this computer.</span></span> <span data-ttu-id="1013b-143">次の表は、構成のオプションを示しています。</span><span class="sxs-lookup"><span data-stu-id="1013b-143">The following table lists the configuration options.</span></span>  
  
|<span data-ttu-id="1013b-144">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1013b-144">Use this</span></span>|<span data-ttu-id="1013b-145">目的</span><span class="sxs-lookup"><span data-stu-id="1013b-145">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="1013b-146">**このコンピューターで Windows SharePoint Services アダプターを有効にします。**</span><span class="sxs-lookup"><span data-stu-id="1013b-146">**Enable Windows SharePoint Services Adapter on this computer**</span></span>|<span data-ttu-id="1013b-147">選択**このコンピューターで Windows SharePoint Services アダプターを有効にする**このコンピューターでアダプターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1013b-147">Select **Enable Windows SharePoint Services Adapter on this computer** to enable the adapter on this computer.</span></span>|  
|<span data-ttu-id="1013b-148">**Windows グループ**</span><span class="sxs-lookup"><span data-stu-id="1013b-148">**Windows group**</span></span>|<span data-ttu-id="1013b-149">**Windows グループ**一覧は、BizTalk SharePoint アダプター有効になっているホスト Windows グループの編集可能なビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="1013b-149">The **Windows group** list provides a view that you can edit of the BizTalk SharePoint Adapter Enabled Hosts Windows group.</span></span>|  
|<span data-ttu-id="1013b-150">**Windows SharePoint Services アダプター Web サイト**</span><span class="sxs-lookup"><span data-stu-id="1013b-150">**Windows SharePoint Services Adapter Web site**</span></span>|<span data-ttu-id="1013b-151">Windows SharePoint Service アダプター Web サービスをホストする Web サイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="1013b-151">Select the Web site that will host the Windows SharePoint Service adapter Web service.</span></span>|  
  
 <span data-ttu-id="1013b-152">カスタム構成を使用して、Windows SharePoint Services アダプターを構成するときに、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1013b-152">When you configure the Windows SharePoint Services adapter using a custom configuration, the following happens:</span></span>  
  
-   <span data-ttu-id="1013b-153">別の Windows グループを指定しない限り、既定で SharePoint Enabled Hosts Windows グループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1013b-153">The SharePoint Enabled Hosts Windows group is created by default unless you specify another Windows group</span></span>  
  
-   <span data-ttu-id="1013b-154">別の Web サイトを指定しない限り、Windows SharePoint Services アダプターのホストには既定の Web サイトが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1013b-154">The Default Web Site is used to host the Windows SharePoint Services adapter unless you specify another Web site</span></span>  
  
-   <span data-ttu-id="1013b-155">BTSSharePointAdapterWSAppPool アプリケーション プールが、Windows SharePoint Services アプリケーション プールを実行するために使用するアカウントで実行されるように作成および構成されます。</span><span class="sxs-lookup"><span data-stu-id="1013b-155">The BTSSharePointAdapterWSAppPool application pool is created and configured to run under the account that is also used to run the Windows SharePoint Services application pool</span></span>  
  
-   <span data-ttu-id="1013b-156">BTSharePointAdapterWS 仮想アプリケーションが、BTSSharePointAdapterWSAppPool アプリケーション プールで実行されるように作成および構成されます。</span><span class="sxs-lookup"><span data-stu-id="1013b-156">The BTSharePointAdapterWS virtual application is created and configured to run in the BTSSharePointAdapterWSAppPool application pool</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1013b-157">この仮想ディレクトリが既に存在する場合は、構成を行ってもメタベースのプロパティが更新されません。</span><span class="sxs-lookup"><span data-stu-id="1013b-157">If this virtual directory already exists, configuration will not update the properties in the metabase.</span></span> <span data-ttu-id="1013b-158">仮想ディレクトリを削除し、構成を再実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1013b-158">You must delete the virtual directory, and run configuration again.</span></span>  
  
- <span data-ttu-id="1013b-159">BTSharePointAdapterWS 仮想アプリケーションに Web サービスが含められます。</span><span class="sxs-lookup"><span data-stu-id="1013b-159">The BTSharePointAdapterWS virtual application contains the Web service</span></span>  
  
  <span data-ttu-id="1013b-160">カスタム構成マネージャの詳細については、次を参照してください。[のインポートとエクスポートの BizTalk Server 構成](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)します。</span><span class="sxs-lookup"><span data-stu-id="1013b-160">For more information about the custom configuration manager, see [Import and Export BizTalk Server Configuration](../install-and-config-guides/import-and-export-biztalk-server-configuration.md).</span></span>  
  
##### <a name="to-configure-the-windows-sharepoint-services-adapter-by-using-a-custom-configuration"></a><span data-ttu-id="1013b-161">ユーザー構成を使用して Windows SharePoint Services アダプターを構成するには</span><span class="sxs-lookup"><span data-stu-id="1013b-161">To configure the Windows SharePoint Services adapter by using a custom configuration</span></span>  
  
1.  <span data-ttu-id="1013b-162">**BizTalk Server 構成**を選択、 **SharePoint アダプター**ノード。</span><span class="sxs-lookup"><span data-stu-id="1013b-162">In the **BizTalk Server Configuration**, select the **SharePoint adapter** node.</span></span>  
  
2.  <span data-ttu-id="1013b-163">選択**このコンピューターで Windows SharePoint Services アダプターを有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="1013b-163">Select **Enable Windows SharePoint Services Adapter on this computer**.</span></span>  
  
3.  <span data-ttu-id="1013b-164">**Windows グループ**、Windows SharePoint Services アダプターを使用する Windows グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="1013b-164">Under **Windows Group**, select the Windows group you will be using for the Windows SharePoint Services adapter.</span></span> <span data-ttu-id="1013b-165">既定では、SharePoint Enabled Hosts です。</span><span class="sxs-lookup"><span data-stu-id="1013b-165">By default, this is SharePoint Enabled Hosts.</span></span>  
  
4.  <span data-ttu-id="1013b-166">**Windows SharePoint Services アダプター Web サイト**ドロップダウン ボックスで、Web サイトのアダプター コンポーネントのインストール先を選択します。</span><span class="sxs-lookup"><span data-stu-id="1013b-166">In the **Windows SharePoint Services Adapter Web Site** drop-down box, select the Web site where the adapter components will be installed.</span></span> <span data-ttu-id="1013b-167">特に選択しない場合、既定の Web サイトが選択されます。</span><span class="sxs-lookup"><span data-stu-id="1013b-167">By default, this is the Default Web Site.</span></span>  
  
5.  <span data-ttu-id="1013b-168">**[構成の適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1013b-168">Click **Apply Configuration**.</span></span>  
  
## <a name="considerations-for-a-single-server-deployment"></a><span data-ttu-id="1013b-169">シングルサーバー展開に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="1013b-169">Considerations for a single-server deployment</span></span>  
 <span data-ttu-id="1013b-170">シングルサーバー環境で Windows SharePoint Services アダプターを設定および展開する際は、次のことを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="1013b-170">When you set up and deploy the Windows SharePoint Services adapter in a single-server environment, consider the following:</span></span>  
  
- <span data-ttu-id="1013b-171">サーバー上で、BizTalk Service アカウントを SharePoint Enabled Hosts Windows グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="1013b-171">Add the BizTalk Service account to the SharePoint Enabled Hosts Windows group on that server.</span></span>  
  
- <span data-ttu-id="1013b-172">SharePoint のサーバーの管理ツールを使用して、SharePoint Enabled Hosts グループを SharePoint の関係者ロールに追加します。</span><span class="sxs-lookup"><span data-stu-id="1013b-172">Add the SharePoint Enabled Hosts group to the SharePoint Contributors role using the SharePoint Central Administration tool.</span></span>  
  
- <span data-ttu-id="1013b-173">[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] では、SharePoint アダプター Web サービスを実行する ID に次のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="1013b-173">On [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], the identity under which the SharePoint Adapter Web Service runs needs the following permissions:</span></span>  
  
   <span data-ttu-id="1013b-174">**読み取り**に対するアクセス許可、 **Program files \microsoft BizTalk Server\<バージョン\>\Business Activity Services\BTSharePointV3AdapterWS**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="1013b-174">**Read** permissions on the **Program Files\Microsoft BizTalk Server \<version\>\Business Activity Services\BTSharePointV3AdapterWS** folder.</span></span> <span data-ttu-id="1013b-175">設定するアクセス許可が必要な Windows と BizTalk Server の 64 ビット バージョンを使用している場合、 **Program Files (x86) \Microsoft BizTalk Server\<バージョン\>\Business Activity Services\BTSharePointV3AdapterWS**</span><span class="sxs-lookup"><span data-stu-id="1013b-175">If using a 64-bit version of Windows and BizTalk Server, permissions need to be set on the **Program Files (x86)\Microsoft BizTalk Server \<version\>\Business Activity Services\BTSharePointV3AdapterWS**</span></span>  
  
   <span data-ttu-id="1013b-176">**読み取り**次のレジストリ キーに対する権限: **hkey_local_machine \software\microsoft\shared Server\Extensions\12.0\Secure\ConfigDB**します。</span><span class="sxs-lookup"><span data-stu-id="1013b-176">**Read** permission on the following registry key: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Shared Tools\Web Server\Extensions\12.0\Secure\ConfigDB**.</span></span>  
  
   <span data-ttu-id="1013b-177">SharePoint データベースを含む SQL Server に対するログオン アクセス許可。</span><span class="sxs-lookup"><span data-stu-id="1013b-177">Logon permissions on the SQL Server that contains the Sharepoint databases.</span></span>  
  
   <span data-ttu-id="1013b-178">メンバー、**パブリック**と**WSS_Content_Application_Pools** SharePoint 構成データベース内のロール。</span><span class="sxs-lookup"><span data-stu-id="1013b-178">A member of the **Public** and **WSS_Content_Application_Pools** roles within the SharePoint configuration database.</span></span>  
  
   <span data-ttu-id="1013b-179">メンバー、**パブリック**と**db 所有者**SharePoint コンテンツ データベース内のロール。</span><span class="sxs-lookup"><span data-stu-id="1013b-179">A member of the **Public** and **db owner** roles within the SharePoint content database.</span></span>  
  
- <span data-ttu-id="1013b-180">Web サービスをインストールする Web サイトは、SharePoint Services Web サイトとして拡張しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="1013b-180">The Web site that you install the Web service on must be extended as a SharePoint Services Web site.</span></span>  
  
- <span data-ttu-id="1013b-181">インストールして、サイレント インストールを使用して、Windows SharePoint Services アダプターを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1013b-181">You can install and configure the Windows SharePoint Services adapter using silent installation.</span></span> <span data-ttu-id="1013b-182">詳細については、次を参照してください。[付録 a: サイレント インストール](../install-and-config-guides/appendix-a-silent-installation.md)します。</span><span class="sxs-lookup"><span data-stu-id="1013b-182">For more information, see [Appendix A: Silent Installation](../install-and-config-guides/appendix-a-silent-installation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1013b-183">参照</span><span class="sxs-lookup"><span data-stu-id="1013b-183">See Also</span></span>  
 <span data-ttu-id="1013b-184">[Windows SharePoint Services アダプター](../core/windows-sharepoint-services-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="1013b-184">[Windows SharePoint Services Adapter](../core/windows-sharepoint-services-adapter.md) </span></span>  
 [<span data-ttu-id="1013b-185">マルチサーバー展開</span><span class="sxs-lookup"><span data-stu-id="1013b-185">Multiserver Deployment</span></span>](../core/multiserver-deployment.md)