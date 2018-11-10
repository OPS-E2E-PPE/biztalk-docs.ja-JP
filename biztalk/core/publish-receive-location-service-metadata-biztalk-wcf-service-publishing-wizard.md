---
title: オーケストレーション ポートにバインドされている、BizTalk WCF サービス公開ウィザードを使用して、WCF 受信場所のサービス メタデータを公開する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF Service Publishing Wizard, publishing metadata
- WCF services, orchestration ports
- WCF services, metadata
- orchestrations, WCF services
ms.assetid: 04ccce9f-8d18-433a-8299-d06fa155db06
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7055531629ec3eadded9562d043fb8a31d7fe11e
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752459"
---
# <a name="how-to-use-the-biztalk-wcf-service-publishing-wizard-to-publish-service-metadata-for-a-wcf-receive-location-bound-to-an-orchestration-port"></a><span data-ttu-id="4fdf1-102">BizTalk WCF サービス公開ウィザードを使用してオーケストレーション ポートにバインドされた WCF 受信場所にサービス メタデータを公開する方法</span><span class="sxs-lookup"><span data-stu-id="4fdf1-102">How to Use the BizTalk WCF Service Publishing Wizard to Publish Service Metadata for a WCF Receive Location Bound to an Orchestration Port</span></span>
<span data-ttu-id="4fdf1-103">WCF サービスを作成して、オーケストレーション ポートにバインドされた既存の WCF 受信場所にサービス メタデータを公開するには、BizTalk WCF サービス公開ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-103">You use the BizTalk WCF Service Publishing Wizard to create a WCF service to publish service metadata for existing WCF receive locations bound to orchestration ports.</span></span>  

> [!NOTE]
>  <span data-ttu-id="4fdf1-104">BizTalk WCF サービス公開ウィザードを実行する前に、BizTalk プロジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-104">You must build your BizTalk projects before running the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="4fdf1-105">BizTalk プロジェクトには、型修飾子がパブリックである受信ポートを 1 つ以上持つオーケストレーションが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-105">The BizTalk projects must include orchestrations having at least one receive port whose type modifier is public.</span></span> <span data-ttu-id="4fdf1-106">また、WCF アダプターにサービス メタデータを公開する前に、WCF 受信場所も作成する必要があります。これには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に付属している BizTalk 管理コンソール、または BTSTask コマンド ライン ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-106">Before you publish service metadata for the WCF adapters, you must also create the WCF receive locations by using the BizTalk Administration console or the BTSTask command-line tool included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="4fdf1-107">WCF を作成する方法の詳細については、受信場所の各 WCF アダプタの適切なトピックを参照して[WCF アダプタ](../core/wcf-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-107">For more information about how to create a WCF receive location, see the appropriate topic for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>  

### <a name="to-publish-service-metadata-for-an-existing-wcf-receive-location-bound-to-an-orchestration-port"></a><span data-ttu-id="4fdf1-108">オーケストレーション ポートにバインドされた既存の WCF 受信場所にサービス メタデータを公開するには</span><span class="sxs-lookup"><span data-stu-id="4fdf1-108">To publish service metadata for an existing WCF receive location bound to an orchestration port</span></span>  

1. <span data-ttu-id="4fdf1-109">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk WCF サービス公開ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-109">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk WCF Service Publishing Wizard**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="4fdf1-110">WCF サービスを作成して BizTalk のオーケストレーションおよびスキーマにメタデータを公開するには、BizTalk WCF サービス公開ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-110">To create and publish WCF serve metadata for BizTalk orchestrations and schemas, you use the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="4fdf1-111">一方、SOAP アダプターを使用してオーケストレーションとスキーマを Web サービスとして公開するには、BizTalk Web サービス公開ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-111">To publish orchestrations and schemas as Web services with the SOAP adapter, you use the BizTalk Web Services Publishing Wizard.</span></span>  

2. <span data-ttu-id="4fdf1-112">**BizTalk WCF サービス公開ウィザードへようこそ**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-112">On the **Welcome to the BizTalk WCF Service Publishing Wizard** page, click **Next**.</span></span>  

3. <span data-ttu-id="4fdf1-113">**WCF サービスの種類**] ページで、[、**メタデータのみのエンドポイント (MEX)** に wcf サービス メタデータを提供する WCF サービスを発行するオプションは、次の手順で選択した場所を受信します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-113">On the **WCF Service Type** page, select the **Metdata only endpoint (MEX)** option to publish the WCF services to provide service metadata for the WCF receive location that you will select in the next step.</span></span>  

    <span data-ttu-id="4fdf1-114">![WCF サービスの種類ページ](../core/media/794a85b5-6454-4cce-8c15-382b5583b0f2.gif "794a85b5-6454-4cce-8c15-382b5583b0f2")</span><span class="sxs-lookup"><span data-stu-id="4fdf1-114">![WCF Service Type page](../core/media/794a85b5-6454-4cce-8c15-382b5583b0f2.gif "794a85b5-6454-4cce-8c15-382b5583b0f2")</span></span>  

4. <span data-ttu-id="4fdf1-115">**WCF サービスの種類**ページで、**受信場所のメタデータを公開**ドロップダウン リストでは、WCF を選択します受信場所でクリックして、サービス メタデータを公開する **[次へ]**.</span><span class="sxs-lookup"><span data-stu-id="4fdf1-115">On the **WCF Service Type** page, in the **Publish metadata for receive location** drop-down list, select a WCF receive location to publish service metadata for, and then click **Next**.</span></span>  

5. <span data-ttu-id="4fdf1-116">**WCF サービスの作成**] ページで、[ **BizTalk オーケストレーションの WCF サービスとして発行**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-116">On the **Create WCF Service** page, select **Publish BizTalk orchestrations as WCF service**, and then click **Next**.</span></span>  

    <span data-ttu-id="4fdf1-117">![WCF サービス ページを作成する](../core/media/86cb66b5-6842-4330-8942-20afa68ec5fa.gif "86cb66b5-6842-4330-8942-20afa68ec5fa")</span><span class="sxs-lookup"><span data-stu-id="4fdf1-117">![Create WCF Service page](../core/media/86cb66b5-6842-4330-8942-20afa68ec5fa.gif "86cb66b5-6842-4330-8942-20afa68ec5fa")</span></span>  

6. <span data-ttu-id="4fdf1-118">**BizTalk アセンブリ**] ページの [、 **BizTalk アセンブリ ファイル (\*.dll)** テキスト ボックスに、BizTalk アセンブリ ファイルの名前を入力またはクリックして**参照**を参照するにはクリックして、サービス メタデータを公開するオーケストレーションを含むアセンブリ**次**します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-118">On the **BizTalk Assembly** page, in the **BizTalk assembly file (\*.dll)** text box, type the name of the BizTalk assembly file or click **Browse** to browse to the assembly containing the orchestration(s) to publish service metadata for, and then click **Next**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="4fdf1-119">BizTalk アセンブリ ファイルを選択する前にすべての依存アセンブリを BizTalk アセンブリと同じフォルダーにコピーまたは依存アセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールします。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-119">Before selecting a BizTalk assembly file, copy all of the dependent assemblies into the same folder with the BizTalk assembly or install the dependent assemblies to the global assembly cache (GAC).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="4fdf1-120">BizTalk アセンブリ ファイルを GAC にインストールする場合に選択するアセンブリを GAC にアセンブリが更新されたこと確認、 **BizTalk アセンブリ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-120">If you installed the BizTalk assembly file into the GAC, make sure that the assembly in the GAC has been updated with the assembly that you will select in the **BizTalk Assembly** dialog box.</span></span> <span data-ttu-id="4fdf1-121">GAC 内のアセンブリの完全修飾名が同じである場合、BizTalk WCF サービス公開ウィザードでは、選択したアセンブリ ファイルではなく、GAC 内のアセンブリ ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-121">If the assembly in the GAC has the same fully qualified name, the BizTalk WCF Service Publishing Wizard uses the assembly file in the GAC instead of the one you selected.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="4fdf1-122">パス名が 260 文字を超えると、パス名が長すぎるというエラー メッセージが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-122">Paths over 260 characters long may cause an error message that the path is too long.</span></span>  

    <span data-ttu-id="4fdf1-123">![BizTalk アセンブリ ページ](../core/media/d34a027e-ea82-4048-8b15-d97df795b0d4.gif "d34a027e-ea82-4048-8b15-d97df795b0d4")</span><span class="sxs-lookup"><span data-stu-id="4fdf1-123">![BizTalk Assembly page](../core/media/d34a027e-ea82-4048-8b15-d97df795b0d4.gif "d34a027e-ea82-4048-8b15-d97df795b0d4")</span></span>  

7. <span data-ttu-id="4fdf1-124">**オーケストレーションおよびポート** ページで、プラス記号 (+) をクリックして各アセンブリおよびオーケストレーションのツリー ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-124">On the **Orchestrations and Ports** page, expand the tree nodes for each assembly and orchestration by clicking the plus sign (+).</span></span> <span data-ttu-id="4fdf1-125">メタデータを公開するオーケストレーションおよびポートのツリー ノードのチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-125">Select orchestrations and ports to publish metadata for by selecting the corresponding tree node check boxes.</span></span> <span data-ttu-id="4fdf1-126">ごとに 1 つの WCF サービスではなく、選択した受信ポートの受信ポートを選択、すべての 1 つの WCF サービス (.svc ファイル) を作成する場合、**選択したすべてのポートを 1 つの WCF サービスに結合**オプションをクリックして **[次へ]** します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-126">If you want to create one WCF service (.svc file) for all of the selected receive ports instead of one WCF service for each receive port, select the **Merge all selected ports into a single WCF service** option, and then click **Next**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="4fdf1-127">選択したすべてのポートを 1 つの WCF サービスに統合すると、選択したすべてのポートの種類が同じになり、ポート内の操作名も同じになります。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-127">When you merge all selected ports into a single WCF service, all of the selected ports have the same port type, and the operation names in the ports are unique.</span></span>  

    <span data-ttu-id="4fdf1-128">![操作およびポート ページ](../core/media/97112744-ddd4-4512-ac56-41317ba9412b.gif "97112744-ddd4-4512-ac56-41317ba9412b")</span><span class="sxs-lookup"><span data-stu-id="4fdf1-128">![Operations and Ports page](../core/media/97112744-ddd4-4512-ac56-41317ba9412b.gif "97112744-ddd4-4512-ac56-41317ba9412b")</span></span>  

8. <span data-ttu-id="4fdf1-129">**WCF サービスのプロパティ**] ページの [、 **WCF サービスの Targetnamespace**テキスト ボックスに、WCF サービスは、ターゲットの名前空間を入力し、順にクリックします**次**。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-129">On the **WCF Service Properties** page, in the **Targetnamespace of the WCF service** text box, type a target namespace for the WCF services, and then click **Next**.</span></span>  

    <span data-ttu-id="4fdf1-130">![WCF サービスのプロパティ ページ](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")</span><span class="sxs-lookup"><span data-stu-id="4fdf1-130">![WCF Service Properties page](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")</span></span>  

9. <span data-ttu-id="4fdf1-131">**WCF サービスの場所**ページで、**場所**テキスト ボックスに、WCF サービスが生成される Web ディレクトリ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-131">On the **WCF Service Location** page, in the **Location** text box, type the Web directory name where the WCF services are generated.</span></span> <span data-ttu-id="4fdf1-132">既定の場所を受け入れることができます (`http://localhost/<BizTalk Assembly Name>`)、WCF サービスの場所を入力、**場所**テキスト ボックス、またはクリック**参照**Web ディレクトリを選択します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-132">You can accept the default location (`http://localhost/<BizTalk Assembly Name>`), type a location for the WCF services in the **Location** text box, or click **Browse** and select a Web directory.</span></span> <span data-ttu-id="4fdf1-133">次のいずれかのオプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-133">Select any of the following options:</span></span>  

   - <span data-ttu-id="4fdf1-134">**既存のプロジェクトを上書きします。**</span><span class="sxs-lookup"><span data-stu-id="4fdf1-134">**Overwrite existing project.**</span></span> <span data-ttu-id="4fdf1-135">: このオプションは、Web ディレクトリが存在する場合のみ選択できます。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-135">This option is available only if the Web directory already exists.</span></span> <span data-ttu-id="4fdf1-136">このオプションを選択すると、同じ場所にのみ公開できます。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-136">You will be able to publish to the same location only if you select this option.</span></span> <span data-ttu-id="4fdf1-137">このオプションを選択しない場合は、別のプロジェクトの場所を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-137">Otherwise, you must enter a different project location.</span></span>  

   - <span data-ttu-id="4fdf1-138">**WCF サービスへの匿名アクセスを許可します。**</span><span class="sxs-lookup"><span data-stu-id="4fdf1-138">**Allow anonymous access to WCF service.**</span></span> <span data-ttu-id="4fdf1-139">: このオプションでは、作成した仮想ディレクトリに匿名アクセスを追加します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-139">This option adds anonymous access to the created virtual directory.</span></span> <span data-ttu-id="4fdf1-140">既定では、仮想ディレクトリは、その親仮想ディレクトリまたは Web サイト (最上位の仮想ディレクトリである場合) から、アクセス権限を継承します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-140">By default, the virtual directory inherits the access privileges from its parent virtual directory or the Web site (if it is a top-level virtual directory).</span></span>  

     <span data-ttu-id="4fdf1-141">このページを終了したらクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-141">When you finish this page, click **Next**.</span></span>  

     <span data-ttu-id="4fdf1-142">![WCF サービスの場所 ページ](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")</span><span class="sxs-lookup"><span data-stu-id="4fdf1-142">![WCF Service location page](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="4fdf1-143">プロジェクトの場所には、別のサーバーを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-143">The project location can exist on a different server.</span></span> <span data-ttu-id="4fdf1-144">WCF サービスを別のサーバーに発行するには、としてプロジェクト名を入力`http://<servername>/<WCF service location>`します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-144">To publish the WCF services to a different server, type the project name as `http://<servername>/<WCF service location>`.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="4fdf1-145">プロジェクトの場所には、既定以外の Web サイトを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-145">The project location can exist on a non-default Web site.</span></span> <span data-ttu-id="4fdf1-146">既定以外の Web サイトに公開する場合は、URL に Web サイトのポート番号を含めます。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-146">When publishing to a non-default Web site, include the port number of the Web site in the URL.</span></span> <span data-ttu-id="4fdf1-147">たとえば、 `http://<servername>:8080/<WCF service location>` のようにします。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-147">For example, `http://<servername>:8080/<WCF service location>`.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="4fdf1-148">ウィザードで、Web アプリケーションの App_DataTemp フォルダーに作成される BindingInfo.xml ファイルでは、パイプラインの既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-148">The BindingInfo.xml file that the wizard creates in the App_DataTemp folder of the Web application uses the default values for the pipelines.</span></span> <span data-ttu-id="4fdf1-149">受信パイプラインの既定値は、 **Microsoft.BizTalk.DefaultPipelines.XMLReceive**パイプライン、および既定値の送信パイプラインは、 **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**パイプライン。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-149">The default value for the receive pipeline is the **Microsoft.BizTalk.DefaultPipelines.XMLReceive** pipeline, and the default value for the send pipeline is the **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit** pipeline.</span></span>  

10. <span data-ttu-id="4fdf1-150">**WCF サービスの概要** ページで、WCF サービスの設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-150">On the **WCF Service Summary** page, review your settings for the WCF services.</span></span>  

11. <span data-ttu-id="4fdf1-151">クリックして**作成**WCF サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-151">Click **Create** to create the WCF services.</span></span>  

12. <span data-ttu-id="4fdf1-152">クリックして**完了**BizTalk WCF サービス公開ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-152">Click **Finish** to complete the BizTalk WCF Service Publishing Wizard.</span></span>  

### <a name="to-configure-the-web-application-for-publishing-service-metadata"></a><span data-ttu-id="4fdf1-153">サービス メタデータを公開する Web アプリケーションを構成するには</span><span class="sxs-lookup"><span data-stu-id="4fdf1-153">To configure the Web application for publishing service metadata</span></span>  

1. <span data-ttu-id="4fdf1-154">BizTalk WCF サービス公開ウィザードで作成した Web アプリケーションについて ASP.NET を有効にします。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-154">Enable ASP.NET for the Web application that the BizTalk WCF Service Publishing Wizard created.</span></span> <span data-ttu-id="4fdf1-155">詳細については、次を参照してください。 [Web サービスを有効にする](../core/enabling-web-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-155">For more information, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="4fdf1-156">Windows Server 2008 または Windows Vista を使用している場合は、アプリケーション プールの ID アカウントを BizTalk Server 管理者グループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-156">If you are using Windows Server 2008 or Windows Vista, you must add the Identity Account of the Application Pool to the BizTalk Server Administrators group.</span></span> <span data-ttu-id="4fdf1-157">該当するアカウントを BizTalk Server 管理者グループに追加した後は、IIS サービスを再起動して設定を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-157">After you add the appropriate account to the BizTalk Server Administrators group, you need to restart the IIS service fro the setting to take effect.</span></span>  

2. <span data-ttu-id="4fdf1-158">コマンド プロンプトを開き、%SystemDrive%\InetPub で、BizTalk WCF サービス公開ウィザードが WCF サービスを作成するフォルダーに移動して\\、し、メモ帳を使用して Web.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-158">Open a command prompt, go to the folder where the BizTalk WCF Service Publishing Wizard created the WCF services in %SystemDrive%\InetPub\\, and then open the Web.config file using Notepad.</span></span>  

3. <span data-ttu-id="4fdf1-159">メモ帳で、次の行を追加、 **\<system.web\>** 要素。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-159">In Notepad, add the following line inside the **\<system.web\>** element:</span></span>  

   ```  
   <trust level="Full" originUrl="" />  
   ```  

   > [!NOTE]
   >  <span data-ttu-id="4fdf1-160">この設定はオプションで、公開した WCF サービスをホストする ASP.NET アプリケーションに、オペレーティング システムのセキュリティの影響下にあるリソースへのアクセス権限を与えます。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-160">This setting is optional and it grants the ASP.NET application hosting the published WCF service access to any resource that is subject to operating system security.</span></span> <span data-ttu-id="4fdf1-161">これは、公開された WCF サービスと同じコンピューターで Windows SharePoint Services がインストールおよび実行されている場合に、WCF サービスの実行に必要な信頼レベルです。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-161">This is the trust level that WCF requires when you have Windows SharePoint Services installed and running on the same machine with the published WCF services.</span></span>  

4. <span data-ttu-id="4fdf1-162">Internet explorer で、**アドレス**ボックスに、形式 を使用して WCF サービスの URL を入力 http://<em>ホスト [: ポート]</em>/*apppath* /*wcfservicename.svc*を公開した WCF サービスをテストします。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-162">In Internet Explorer, in the **Address** box, type the URL for the WCF service using the format http://<em>host[:port]</em>/*apppath*/*wcfservicename.svc* to test the published WCF service.</span></span> <span data-ttu-id="4fdf1-163">次の表は、これらのパラメーターについてまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-163">The parameters are described in the following table.</span></span>  


   |      <span data-ttu-id="4fdf1-164">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4fdf1-164">Parameter</span></span>       |                                                            <span data-ttu-id="4fdf1-165">値</span><span class="sxs-lookup"><span data-stu-id="4fdf1-165">Value</span></span>                                                            |
   |----------------------|-----------------------------------------------------------------------------------------------------------------------------|
   |    <span data-ttu-id="4fdf1-166">*ホスト [: ポート]*</span><span class="sxs-lookup"><span data-stu-id="4fdf1-166">*host[:port]*</span></span>     | <span data-ttu-id="4fdf1-167">WCF サービスを配置したコンピューターの名前です。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-167">The name of the computer where you have deployed your WCF service.</span></span> <span data-ttu-id="4fdf1-168">このサーバー名の後に、コロンとポート番号を入力できます。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-168">A colon and the port number can follow this server name.</span></span> |
   |      <span data-ttu-id="4fdf1-169">*apppath*</span><span class="sxs-lookup"><span data-stu-id="4fdf1-169">*apppath*</span></span>       |                              <span data-ttu-id="4fdf1-170">仮想ディレクトリ名と Web アプリケーションのパスです。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-170">The name of your virtual directory and the Web application path.</span></span>                               |
   | <span data-ttu-id="4fdf1-171">*wcfservicename.svc*</span><span class="sxs-lookup"><span data-stu-id="4fdf1-171">*wcfservicename.svc*</span></span> |                                           <span data-ttu-id="4fdf1-172">WCF サービスの .svc ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-172">The name of the WCF service .svc file.</span></span>                                            |


5. <span data-ttu-id="4fdf1-173">可能性のある機密性の高いサービス メタデータが誤って漏洩を防ぐためには、次のタスクを実行することによって、運用環境では、この動作を無効にすることお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-173">To prevent unintentional disclosure of potentially sensitive service metadata, we recommend that you disable this behavior in the production environment by performing the following tasks:</span></span>  

   1.  <span data-ttu-id="4fdf1-174">メモ帳で、%SystemDrive%\InetPub で、BizTalk WCF サービス公開ウィザードが WCF サービスを作成するフォルダーの Web.config を開き\\します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-174">In Notepad, open Web.config in the folder where the BizTalk WCF Service Publishing Wizard created the WCF service in %SystemDrive%\InetPub\\.</span></span>  

   2.  <span data-ttu-id="4fdf1-175">メモ帳で、設定、 **httpGetEnabled**属性、 **\<serviceMetadata\>** 要素を次の行のように false に。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-175">In Notepad, set the **httpGetEnabled** attribute in the  **\<serviceMetadata\>** element to false as in the following line:</span></span>  

       ```  
       <serviceMetadata httpGetEnabled="false" httpsGetEnabled="false" />  
       ```  

## <a name="see-also"></a><span data-ttu-id="4fdf1-176">参照</span><span class="sxs-lookup"><span data-stu-id="4fdf1-176">See Also</span></span>  
 <span data-ttu-id="4fdf1-177">[BizTalk WCF サービス公開ウィザードを使用して、コンテンツ ベース ルーティングの WCF 受信場所のサービス メタデータを公開する方法](../core/publish-service-metadata-for-a-wcf-receive-location-for-content-based-routing.md) </span><span class="sxs-lookup"><span data-stu-id="4fdf1-177">[How to Use the BizTalk WCF Service Publishing Wizard to Publish Service Metadata for a WCF Receive Location for Content-Based Routing](../core/publish-service-metadata-for-a-wcf-receive-location-for-content-based-routing.md) </span></span>  
 [<span data-ttu-id="4fdf1-178">チュートリアル: WCF-NetMsmq アダプターを使用した WCF サービスの公開</span><span class="sxs-lookup"><span data-stu-id="4fdf1-178">Walkthrough: Publishing WCF Services with the WCF-NetMsmq Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)