---
title: BizTalk WCF サービス公開ウィザードを使用してオーケストレーションを WCF サービスとして公開する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tools, WCF Service Publishing Wizard
- WCF services, WCF Service Publishing Wizard
- WCF services, orchestrations
- publishing, orchestrations [WCF services]
- orchestrations, WCF services
- WCF Service Publishing Wizard
ms.assetid: db352132-2fe8-4d53-b239-45e5c3525b6c
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07f0a7d3c8f9657c2a2cac53c13095194e5a0401
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974563"
---
# <a name="how-to-use-the-biztalk-wcf-service-publishing-wizard-to-publish-orchestrations-as-wcf-services"></a><span data-ttu-id="59bf7-102">BizTalk WCF サービス公開ウィザードを使用してオーケストレーションを WCF サービスとして公開する方法</span><span class="sxs-lookup"><span data-stu-id="59bf7-102">How to Use the BizTalk WCF Service Publishing Wizard to Publish Orchestrations as WCF Services</span></span>
<span data-ttu-id="59bf7-103">オーケストレーションを WCF サービスとして公開するには、BizTalk WCF サービス公開ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-103">You use the BizTalk WCF Service Publishing Wizard to publish orchestrations as WCF services.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59bf7-104">BizTalk WCF サービス公開ウィザードを実行する前に、BizTalk プロジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59bf7-104">You must build your BizTalk projects before running the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="59bf7-105">BizTalk プロジェクトには、型修飾子がパブリックである受信ポートを 1 つ以上持つオーケストレーションが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="59bf7-105">The BizTalk projects must include orchestrations having at least one receive port whose type modifier is public.</span></span> <span data-ttu-id="59bf7-106">この型修飾子は、ポートが作成されたときのオーケストレーションのプロパティに存在します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-106">This type modifier exists in the properties for the orchestration when the port is created.</span></span>  
  
### <a name="to-publish-an-orchestration-as-a-wcf-service"></a><span data-ttu-id="59bf7-107">オーケストレーションを WCF サービスとして公開するには</span><span class="sxs-lookup"><span data-stu-id="59bf7-107">To publish an orchestration as a WCF service</span></span>  
  
1. <span data-ttu-id="59bf7-108">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、順にクリックします**BizTalk WCF サービス公開ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-108">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and then click **BizTalk WCF Service Publishing Wizard**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="59bf7-109">BizTalk のオーケストレーションおよびスキーマを作成し、WCF アダプターを使用して WCF サービスとして公開するには、BizTalk WCF サービス公開ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-109">To create and publish BizTalk orchestrations and schemas as WCF services with the WCF adapters, you use the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="59bf7-110">一方、SOAP アダプターを使用してオーケストレーションとスキーマを Web サービスとして公開するには、BizTalk Web サービス公開ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-110">To publish orchestrations and schemas as Web services with the SOAP adapter, you use the BizTalk Web Services Publishing Wizard.</span></span>  
  
2. <span data-ttu-id="59bf7-111">**BizTalk WCF サービス公開ウィザードへようこそ**] ページで [**次**します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-111">On the **Welcome to the BizTalk WCF Service Publishing Wizard** page, click **Next**.</span></span>  
  
3. <span data-ttu-id="59bf7-112">**WCF サービスの種類**] ページで、[**サービス エンドポイント**選択した BizTalk オーケストレーションを BizTalk アセンブリ内で WCF サービスを発行するオプション。</span><span class="sxs-lookup"><span data-stu-id="59bf7-112">On the **WCF Service Type** page, select **Service endpoint** option to publish the WCF services on selected BizTalk orchestrations in a BizTalk assembly.</span></span>  
  
    <span data-ttu-id="59bf7-113">![WCF サービスの種類ページ](../core/media/959900fd-44c9-4f3a-8836-9786a2f5e707.gif "959900fd-44c9-4f3a-8836-9786a2f5e707")</span><span class="sxs-lookup"><span data-stu-id="59bf7-113">![WCF Service Type page](../core/media/959900fd-44c9-4f3a-8836-9786a2f5e707.gif "959900fd-44c9-4f3a-8836-9786a2f5e707")</span></span>  
  
4. <span data-ttu-id="59bf7-114">**WCF サービスの種類**] ページで、[**メタデータ エンドポイントを有効にする**分離 WCF の受信場所のインターネット インフォメーション サービス (IIS) によってホストされているかどうかを示すチェック ボックスは、サービス メタデータを公開HTTP GET 要求を使用して取得します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-114">On the **WCF Service Type** page, select **Enable metadata endpoint** check-box to indicate whether the isolated WCF receive location hosted by Internet Information Services (IIS) publish service metadata for retrieval using an HTTP/GET request.</span></span> <span data-ttu-id="59bf7-115">このチェック ボックスを有効にすると、ウィザードには、Web.config が生成されます場所、 **httpGetEnabled**の属性、 **\<serviceMetadata\>** 要素に設定されて**は true**。</span><span class="sxs-lookup"><span data-stu-id="59bf7-115">By enabling this check-box, the wizard generates Web.config where the **httpGetEnabled** attribute of the **\<serviceMetadata\>** element is set to **true**.</span></span> <span data-ttu-id="59bf7-116">メタデータ インポート ツール (SvcUtil.exe など) を使用すると、開発環境でこのサービスを呼び出すために必要なクライアント コードを生成できます。</span><span class="sxs-lookup"><span data-stu-id="59bf7-116">You can use a metadata import tool (such as SvcUtil.exe) to generate the client code required to call this service in the development environment.</span></span> <span data-ttu-id="59bf7-117">メタデータが公開されるアドレスは、エンドポイント アドレスと **? wsdl**クエリ文字列。</span><span class="sxs-lookup"><span data-stu-id="59bf7-117">The address at which the metadata is published is the endpoint address plus a **?wsdl** query string.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="59bf7-118">機密性の高いサービス メタデータが誤って公開されないように、実稼働環境ではこの動作を無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="59bf7-118">To prevent unintentional disclosure of potentially sensitive service metadata, it is recommended to disable this behavior on the production environment.</span></span> <span data-ttu-id="59bf7-119">これは、httpgetenabled を false に設定するか、MEX 仮想ディレクトリを削除して実行できます。</span><span class="sxs-lookup"><span data-stu-id="59bf7-119">This can be done by setting httpgetenabled to false, or deleting the MEX virtual directory.</span></span>  
  
5. <span data-ttu-id="59bf7-120">**WCF サービスの種類**] ページの [、**アダプター名 (トランスポートの種類)** ドロップダウン リストで、WCF サービスを発行する際の分離 WCF アダプターを選択します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-120">On the **WCF Service Type** page, in the **Adapter name (Transport type)** drop-down list, select the isolated WCF adapter with which the WCF services are published.</span></span> <span data-ttu-id="59bf7-121">以下のいずれかのアダプターを選択できます。</span><span class="sxs-lookup"><span data-stu-id="59bf7-121">You can select any of the following adapters:</span></span>  
  
   -   <span data-ttu-id="59bf7-122">**Wcf-basichttp します。**</span><span class="sxs-lookup"><span data-stu-id="59bf7-122">**WCF-BasicHttp.**</span></span> <span data-ttu-id="59bf7-123">: WCF-BasicHttp 受信アダプターは、ASMX ベースのサービスなど WS-I 基本プロファイル 1.1 準拠の Web サービスと通信できます。</span><span class="sxs-lookup"><span data-stu-id="59bf7-123">The WCF-BasicHttp adapter can communicate with WS-I Basic Profile 1.1-conformant Web services like ASMX-based services.</span></span>  
  
   -   <span data-ttu-id="59bf7-124">**Wcf-wshttp します。**</span><span class="sxs-lookup"><span data-stu-id="59bf7-124">**WCF-WSHttp.**</span></span> <span data-ttu-id="59bf7-125">: WCF-WSHttp アダプターは、HTTP および HTTPS を使用し WS-\* 標準をとおしてサービスと通信できます。</span><span class="sxs-lookup"><span data-stu-id="59bf7-125">The WCF-WSHttp adapter can communicate with a service through the WS-\* standards over HTTP and HTTPS.</span></span>  
  
   -   <span data-ttu-id="59bf7-126">**Wcf-customisolated します。**</span><span class="sxs-lookup"><span data-stu-id="59bf7-126">**WCF-CustomIsolated.**</span></span> <span data-ttu-id="59bf7-127">: WCF-CustomIsolated アダプターを使用すると、HTTP トランスポートで WCF (Windows Communication Foundation) の拡張機能を利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="59bf7-127">The WCF-CustomIsolated adapter enables the use of Windows Communication Foundation (WCF) extensibility features over the HTTP transport.</span></span>  
  
6. <span data-ttu-id="59bf7-128">**WCF サービスの種類**] ページで、[、**次のアプリケーションを作成する BizTalk 受信場所**チェック ボックスを受信ポートと各生成 .svc ファイルに対応する場所を作成するには選択した WCF アダプター、**アダプター名**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="59bf7-128">On the **WCF Service Type** page, select the **Create BizTalk receive locations in the following application** check-box to create the receive ports and locations corresponding to each generated .svc file for the WCF adapter that you selected in the **Adapter name** drop-down list.</span></span> <span data-ttu-id="59bf7-129">受信場所が既に存在する場合、既存の受信場所は置き換えられません。</span><span class="sxs-lookup"><span data-stu-id="59bf7-129">If a receive location already exists, it is not replaced.</span></span> <span data-ttu-id="59bf7-130">このオプションを選択した後、アプリケーションで、受信ポートと受信場所が生成される場所を選択、 **BizTalk アプリケーション名**ドロップダウン リスト、およびクリック **[次へ]** します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-130">After selecting this option, choose the application where the receive ports and locations will be generated in the **BizTalk application name** drop-down list, and then click **Next**.</span></span>  
  
7. <span data-ttu-id="59bf7-131">**WCF サービスの作成**] ページで、[ **BizTalk オーケストレーションの WCF サービスとして発行**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-131">On the **Create WCF Service** page, select **Publish BizTalk orchestrations as WCF service**, and then click **Next**.</span></span>  
  
    <span data-ttu-id="59bf7-132">![WCF サービス ページを作成する](../core/media/86cb66b5-6842-4330-8942-20afa68ec5fa.gif "86cb66b5-6842-4330-8942-20afa68ec5fa")</span><span class="sxs-lookup"><span data-stu-id="59bf7-132">![Create WCF Service page](../core/media/86cb66b5-6842-4330-8942-20afa68ec5fa.gif "86cb66b5-6842-4330-8942-20afa68ec5fa")</span></span>  
  
8. <span data-ttu-id="59bf7-133">**BizTalk アセンブリ**] ページの [、 **BizTalk アセンブリ ファイル (\*.dll)** テキスト ボックスに、BizTalk アセンブリ ファイルの名前を入力またはクリックして**参照**を参照するにはをクリックし、オーケストレーションを含むアセンブリ**次**します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-133">On the **BizTalk Assembly** page, in the **BizTalk assembly file (\*.dll)** text box, type the name of the BizTalk assembly file or click **Browse** to browse to the assembly containing the orchestration(s) to publish, and then click **Next**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="59bf7-134">BizTalk アセンブリ ファイルを選択する前にすべての依存アセンブリを BizTalk アセンブリと同じフォルダーにコピーまたは依存アセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールします。</span><span class="sxs-lookup"><span data-stu-id="59bf7-134">Before choosing a BizTalk assembly file, copy all of the dependent assemblies into the same folder with the BizTalk assembly or install the dependent assemblies to the global assembly cache (GAC).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="59bf7-135">BizTalk アセンブリ ファイルを GAC にインストールする場合に選択するアセンブリを GAC にアセンブリが更新されたこと確認、 **BizTalk アセンブリ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="59bf7-135">If you installed the BizTalk assembly file into the GAC, make sure that the assembly in the GAC has been updated with the assembly that you will select in the **BizTalk Assembly** dialog box.</span></span> <span data-ttu-id="59bf7-136">GAC 内のアセンブリの完全修飾名が同じである場合、BizTalk WCF サービス公開ウィザードでは、選択したアセンブリ ファイルではなく、GAC 内のアセンブリ ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="59bf7-136">If the assembly in the GAC has the same fully qualified name, the BizTalk WCF Service Publishing Wizard uses the assembly file in the GAC instead of the one you selected.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="59bf7-137">パス名が 260 文字を超えると、パス名が長すぎるというエラー メッセージが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="59bf7-137">Paths over 260 characters long may cause an error message that the path is too long.</span></span>  
  
    <span data-ttu-id="59bf7-138">![BizTalk アセンブリ ページ](../core/media/d34a027e-ea82-4048-8b15-d97df795b0d4.gif "d34a027e-ea82-4048-8b15-d97df795b0d4")</span><span class="sxs-lookup"><span data-stu-id="59bf7-138">![BizTalk Assembly page](../core/media/d34a027e-ea82-4048-8b15-d97df795b0d4.gif "d34a027e-ea82-4048-8b15-d97df795b0d4")</span></span>  
  
9. <span data-ttu-id="59bf7-139">**オーケストレーションおよびポート** ページで、プラス記号 (+) をクリックして各アセンブリおよびオーケストレーションのツリー ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-139">On the **Orchestrations and Ports** page, expand the tree nodes for each assembly and orchestration by clicking the plus sign (+).</span></span> <span data-ttu-id="59bf7-140">対応するツリー ノードのチェック ボックスを選択して発行するオーケストレーションおよびポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-140">Select orchestrations and ports to publish by selecting the corresponding tree node check boxes.</span></span> <span data-ttu-id="59bf7-141">ごとに 1 つの WCF サービスではなく、選択した受信ポートの受信ポートを選択、すべての 1 つの WCF サービス (.svc ファイル) を作成する場合、**選択したすべてのポートを 1 つの WCF サービスに結合**オプションをクリックして **[次へ]** します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-141">If you want to create one WCF service (.svc file) for all of the selected receive ports instead of one WCF service for each receive port, select the **Merge all selected ports into a single WCF service** option, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="59bf7-142">選択したすべてのポートを 1 つの WCF サービスに統合すると、選択したすべてのポートの種類が同じになり、ポート内の操作名も同じになります。</span><span class="sxs-lookup"><span data-stu-id="59bf7-142">When you merge all selected ports into a single WCF service, all of the selected ports have the same port type, and the operation names in the ports are unique.</span></span>  
  
     <span data-ttu-id="59bf7-143">![操作およびポート ページ](../core/media/97112744-ddd4-4512-ac56-41317ba9412b.gif "97112744-ddd4-4512-ac56-41317ba9412b")</span><span class="sxs-lookup"><span data-stu-id="59bf7-143">![Operations and Ports page](../core/media/97112744-ddd4-4512-ac56-41317ba9412b.gif "97112744-ddd4-4512-ac56-41317ba9412b")</span></span>  
  
10. <span data-ttu-id="59bf7-144">**WCF サービスのプロパティ**] ページの [、 **WCF サービスの Targetnamespace**テキスト ボックスに、WCF サービスは、ターゲットの名前空間を入力し、順にクリックします**次**。</span><span class="sxs-lookup"><span data-stu-id="59bf7-144">On the **WCF Service Properties** page, in the **Targetnamespace of the WCF service** text box, type a target namespace for the WCF services, and then click **Next**.</span></span>  
  
     <span data-ttu-id="59bf7-145">![WCF サービスのプロパティ ページ](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")</span><span class="sxs-lookup"><span data-stu-id="59bf7-145">![WCF Service Properties page](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")</span></span>  
  
11. <span data-ttu-id="59bf7-146">**WCF サービスの場所**ページで、**場所**テキスト ボックスに、WCF サービスが生成される Web ディレクトリ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-146">On the **WCF Service Location** page, in the **Location** text box, type the Web directory name where the WCF services are generated.</span></span> <span data-ttu-id="59bf7-147">既定の場所を受け入れることができます (http://localhost/<*BizTalk アセンブリ名*>)、WCF サービスの場所を入力、**場所**テキスト ボックス、またはクリック**参照**Web ディレクトリを選択します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-147">You can accept the default location (http://localhost/<*BizTalk Assembly Name*>), type a location for the WCF services in the **Location** text box, or click **Browse** and select a Web directory.</span></span> <span data-ttu-id="59bf7-148">次のいずれかのオプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="59bf7-148">Select any of the following options:</span></span>  
  
    - <span data-ttu-id="59bf7-149">**既存のプロジェクトを上書きします。**</span><span class="sxs-lookup"><span data-stu-id="59bf7-149">**Overwrite existing project.**</span></span> <span data-ttu-id="59bf7-150">: このオプションは、Web ディレクトリが既に存在する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="59bf7-150">This option is only available if the Web directory already exists.</span></span> <span data-ttu-id="59bf7-151">このオプションを選択すると、同じ場所にのみ公開できます。</span><span class="sxs-lookup"><span data-stu-id="59bf7-151">You will be able to publish to the same location only if you select this option.</span></span> <span data-ttu-id="59bf7-152">このオプションを選択しない場合は、別のプロジェクトの場所を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59bf7-152">Otherwise, you must enter a different project location.</span></span>  
  
    - <span data-ttu-id="59bf7-153">**WCF サービスへの匿名アクセスを許可します。**</span><span class="sxs-lookup"><span data-stu-id="59bf7-153">**Allow anonymous access to WCF service.**</span></span> <span data-ttu-id="59bf7-154">: このオプションでは、作成した仮想ディレクトリに匿名アクセスを追加します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-154">This option adds anonymous access to the created virtual directory.</span></span> <span data-ttu-id="59bf7-155">既定では、仮想ディレクトリは、その親仮想ディレクトリまたは Web サイト (最上位の仮想ディレクトリである場合) から、アクセス権限を継承します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-155">By default, the virtual directory inherits the access privileges from its parent virtual directory or the Web site (if it is a top-level virtual directory).</span></span>  
  
      <span data-ttu-id="59bf7-156">このページを終了したらクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-156">When you finish this page, click **Next**.</span></span>  
  
      <span data-ttu-id="59bf7-157">![WCF サービスの場所 ページ](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")</span><span class="sxs-lookup"><span data-stu-id="59bf7-157">![WCF Service location page](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="59bf7-158">プロジェクトの場所には、別のサーバーを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="59bf7-158">The project location can exist on a different server.</span></span> <span data-ttu-id="59bf7-159">WCF サービスを別のサーバーに発行するプロジェクト名を入力として http://&lt*servername*>/<*WCF サービスの場所*>。</span><span class="sxs-lookup"><span data-stu-id="59bf7-159">To publish the WCF services to a different server, type the project name as http://<*servername*>/<*WCF service location*>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="59bf7-160">プロジェクトの場所には、既定以外の Web サイトを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="59bf7-160">The project location can exist on a non-default Web site.</span></span> <span data-ttu-id="59bf7-161">既定以外の Web サイトに公開する場合は、URL に Web サイトのポート番号を含めます。</span><span class="sxs-lookup"><span data-stu-id="59bf7-161">When publishing to a non-default Web site, include the port number of the Web site in the URL.</span></span> <span data-ttu-id="59bf7-162">たとえば、 http://&lt*servername*>: 8080/<*WCF サービスの場所*>。</span><span class="sxs-lookup"><span data-stu-id="59bf7-162">For example, http://<*servername*>:8080/<*WCF service location*>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="59bf7-163">ウィザードを使用して受信場所を作成する場合は、既定値を使用して受信場所が作成されます。</span><span class="sxs-lookup"><span data-stu-id="59bf7-163">When using the wizard to create receive locations, the wizard creates the receive locations using the default values.</span></span> <span data-ttu-id="59bf7-164">受信パイプラインの既定値は、 **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**パイプライン。</span><span class="sxs-lookup"><span data-stu-id="59bf7-164">The default value for the receive pipeline is the **Microsoft.BizTalk.DefaultPipelines.PassThruReceive** pipeline.</span></span> <span data-ttu-id="59bf7-165">公開された WCF サービスを通じて受信するメッセージが、特別なパイプライン処理 (たとえば、検証、関連付け/プロパティの昇格、または受信/送信マップ) を必要とする場合には、受信パイプラインを設定する必要があります**Microsoft.BizTalk.DefaultPipelines.XMLReceive**、またはカスタム パイプラインでは、BizTalk Server 管理コンソールを使用します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-165">If messages received through the published WCF services require any special pipeline processing (for example, validation, correlation/property promotion, or inbound/outbound maps) then you should set the receive pipeline to **Microsoft.BizTalk.DefaultPipelines.XMLReceive**, or to a custom pipeline, using the BizTalk Server Administration console.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="59bf7-166">使用しない場合、**オーケストレーションを WCF サービスとして公開**オプションで、このページに達した後に、 **WCF サービスの作成**ページの表示を**Web サービスの説明**公開オプションを変更する前に選択した BizTalk アセンブリからのサービスおよびメソッドの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="59bf7-166">If you decide not to use the **Publishing orchestration as WCF service** option after you reach this page, on the **Create WCF Service** page, you may see that the **Web service description** displays the service and method names from the BizTalk assembly that you selected before you changed the publishing option.</span></span> <span data-ttu-id="59bf7-167">これは、発行方法が変更されたときに、メモリ内の Web サービスの説明はクリアされないためにです。</span><span class="sxs-lookup"><span data-stu-id="59bf7-167">This is because the in-memory Web service description is not cleared when the publishing method is changed.</span></span>  
  
12. <span data-ttu-id="59bf7-168">**WCF サービスの概要** ページで、WCF サービスの設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-168">On the **WCF Service Summary** page, review your settings for the WCF services.</span></span>  
  
13. <span data-ttu-id="59bf7-169">クリックして**作成**WCF サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-169">Click **Create** to create the WCF services.</span></span>  
  
14. <span data-ttu-id="59bf7-170">クリックして**完了**BizTalk WCF サービス公開ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-170">Click **Finish** to complete the BizTalk WCF Service Publishing Wizard.</span></span>  
  
15. <span data-ttu-id="59bf7-171">BizTalk WCF サービス公開ウィザードを使用して WCF サービスを公開した後、これらのサービスを適切に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59bf7-171">After publishing WCF services with the BizTalk WCF Service Publishing Wizard, you must configure them properly.</span></span> <span data-ttu-id="59bf7-172">分離 WCF を構成する方法については、受信アダプターを参照してください[BizTalk WCF サービス公開ウィザードで WCF サービス公開を構成する方法](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md)します。</span><span class="sxs-lookup"><span data-stu-id="59bf7-172">For information about how to configure the isolated WCF receive adapter, see [How to Configure WCF Services Published with the BizTalk WCF Service Publishing Wizard](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59bf7-173">参照</span><span class="sxs-lookup"><span data-stu-id="59bf7-173">See Also</span></span>  
 <span data-ttu-id="59bf7-174">[BizTalk WCF サービス公開ウィザードで公開した WCF サービスを構成する方法](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="59bf7-174">[How to Configure WCF Services Published with the BizTalk WCF Service Publishing Wizard](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md) </span></span>  
 <span data-ttu-id="59bf7-175">[チュートリアル: Wcf-basichttp アダプターを使用した WCF サービスの発行](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="59bf7-175">[Walkthrough: Publishing WCF Services with the WCF-BasicHttp Adapter](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md) </span></span>  
 [<span data-ttu-id="59bf7-176">BizTalk WCF サービス公開ウィザードを使用してスキーマを WCF サービスとして公開する方法</span><span class="sxs-lookup"><span data-stu-id="59bf7-176">How to Use the BizTalk WCF Service Publishing Wizard to Publish Schemas as WCF Services</span></span>](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md)