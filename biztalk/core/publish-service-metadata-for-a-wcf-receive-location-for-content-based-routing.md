---
title: "BizTalk WCF サービス公開ウィザードを使用して、コンテンツ ベース ルーティングの WCF 受信場所用にサービス メタデータを公開する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Service Publishing Wizard, publishing metadata
- WCF services, metadata
ms.assetid: e900b0a0-db17-4db9-a639-54891e02d6d7
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7be81166f4f66ed79bbb0b00b5e226c9e3c2be7b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-use-the-biztalk-wcf-service-publishing-wizard-to-publish-service-metadata-for-a-wcf-receive-location-for-content-based-routing"></a><span data-ttu-id="906a8-102">BizTalk WCF サービス公開ウィザードを使用してコンテンツ ベース ルーティングの WCF 受信場所にサービス メタデータを公開する方法</span><span class="sxs-lookup"><span data-stu-id="906a8-102">How to Use the BizTalk WCF Service Publishing Wizard to Publish Service Metadata for a WCF Receive Location for Content-Based Routing</span></span>
<span data-ttu-id="906a8-103">BizTalk WCF サービス公開ウィザードを使用して WCF サービスを作成し、コンテンツベース ルーティングの既存の WCF 受信場所にメタデータを公開します。</span><span class="sxs-lookup"><span data-stu-id="906a8-103">You use the BizTalk WCF Service Publishing Wizard to create a WCF service to publish service metadata for existing WCF receive locations for content-based routing.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="906a8-104">BizTalk WCF サービス公開ウィザードを実行する前に、BizTalk プロジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="906a8-104">You must build your BizTalk projects before running the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="906a8-105">BizTalk プロジェクトには、WCF サービスとして公開するスキーマを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="906a8-105">The BizTalk projects must include schemas to publish as WCF services.</span></span> <span data-ttu-id="906a8-106">また、WCF アダプターにサービス メタデータを公開する前に、WCF 受信場所も作成する必要があります。これには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に付属している BizTalk Server 管理コンソール、または BTSTask コマンド ライン ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="906a8-106">Before you publish service metadata for the WCF adapters, you must also create the WCF receive locations by using the BizTalk Server Administration console or the BTSTask command-line tool included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="906a8-107">WCF を作成する方法の詳細については、受信場所の各 WCF アダプタの該当するトピックを参照してください[WCF アダプタ](../core/wcf-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="906a8-107">For more information about how to create a WCF receive location, see the appropriate topic for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>  
  
### <a name="to-publish-service-metadata-for-an-existing-wcf-receive-location-for-content-based-routing"></a><span data-ttu-id="906a8-108">コンテンツベース ルーティングの既存 WCF 受信場所にサービス メタデータを公開するには</span><span class="sxs-lookup"><span data-stu-id="906a8-108">To publish service metadata for an existing WCF receive location for content-based routing</span></span>  
  
1.  <span data-ttu-id="906a8-109">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]** 、順にクリック**BizTalk WCF サービス公開ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="906a8-109">Click **Start**, point to **All Programs**, point to **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**, and then click **BizTalk WCF Service Publishing Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="906a8-110">作成し、BizTalk オーケストレーションとスキーマを WCF サービスのメタデータを公開、BizTalk WCF サービス公開ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="906a8-110">To create and publish WCF service metadata for BizTalk orchestrations and schemas, you use the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="906a8-111">一方、SOAP アダプターを使用してオーケストレーションとスキーマを Web サービスとして公開するには、BizTalk Web サービス公開ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="906a8-111">To publish orchestrations and schemas as Web services with the SOAP adapter, you use the BizTalk Web Services Publishing Wizard.</span></span>  
  
2.  <span data-ttu-id="906a8-112">**BizTalk WCF サービス公開ウィザードへようこそ** ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="906a8-112">On the **Welcome to the BizTalk WCF Service Publishing Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="906a8-113">**WCF サービスの種類**] ページで、[、**メタデータのみのエンドポイント (MEX)**に wcf サービス メタデータを提供する WCF サービスを発行するオプションを受信場所は、次の手順で選択します。</span><span class="sxs-lookup"><span data-stu-id="906a8-113">On the **WCF Service Type** page, select the **Metdata only endpoint (MEX)** option to publish the WCF services to provide service metadata for the WCF receive location that you will select in the next step.</span></span>  
  
     <span data-ttu-id="906a8-114">![WCF サービスの種類ページ](../core/media/794a85b5-6454-4cce-8c15-382b5583b0f2.gif "794a85b5-6454-4cce-8c15-382b5583b0f2")</span><span class="sxs-lookup"><span data-stu-id="906a8-114">![WCF Service Type page](../core/media/794a85b5-6454-4cce-8c15-382b5583b0f2.gif "794a85b5-6454-4cce-8c15-382b5583b0f2")</span></span>  
  
4.  <span data-ttu-id="906a8-115">**WCF サービスの種類** ページの 、**受信場所のメタデータを公開**ドロップダウン リストでは、wcf 受信場所で、サービス メタデータを公開し、をクリックする**次へ**.</span><span class="sxs-lookup"><span data-stu-id="906a8-115">On the **WCF Service Type** page, in the **Publish metadata for receive location** drop-down list, select a WCF receive location to publish service metadata for, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="906a8-116">**WCF サービスの作成**] ページで、[**スキーマを WCF サービスとして公開**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="906a8-116">On the **Create WCF Service** page, select **Publish schemas as WCF service**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="906a8-117">![WCF サービス ページを作成する](../core/media/717db27a-2843-4950-899d-0946460f5c1f.gif "717db27a-2843-4950-899d-0946460f5c1f")</span><span class="sxs-lookup"><span data-stu-id="906a8-117">![Create WCF Service page](../core/media/717db27a-2843-4950-899d-0946460f5c1f.gif "717db27a-2843-4950-899d-0946460f5c1f")</span></span>  
  
6.  <span data-ttu-id="906a8-118">**WCF サービス**ページで、サービス メタデータを公開する WCF サービス コントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="906a8-118">On the **WCF Service** page, define the WCF service contract(s) to publish service metadata for.</span></span> <span data-ttu-id="906a8-119">ツリーを使用する、 **Web サービスの説明**を追加、削除、名前の変更、および公開する WCF サービスの Web サービス説明ノードの編集 ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="906a8-119">You use the tree in the **Web service description** dialog box to add, remove, rename, and edit the Web service description nodes for the WCF services to publish.</span></span> <span data-ttu-id="906a8-120">**情報** ダイアログ ボックスが選択したノードに関する情報を提供し、現在のノードまたはサブノードでエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="906a8-120">The **Information** dialog box provides information about the selected node and displays any errors in the current node or any subnodes:</span></span>  
  
    -   <span data-ttu-id="906a8-121">ツリーのルート ノード (Web サービスの説明) は、公開する WCF サービス コントラクトについての説明です。</span><span class="sxs-lookup"><span data-stu-id="906a8-121">The root node to the tree (Web service description) describes the WCF service contracts to publish.</span></span> <span data-ttu-id="906a8-122">仮想ディレクトリ名では、ルート ノードが既定の名前として使用されます。</span><span class="sxs-lookup"><span data-stu-id="906a8-122">The virtual directory name uses the root node as the default name.</span></span> <span data-ttu-id="906a8-123">選択して公開する WCF サービスの Web サービス説明の名前を変更することができます**web サービスの説明の名前を変更**です。</span><span class="sxs-lookup"><span data-stu-id="906a8-123">You can modify the Web service description name for the WCF services to publish by selecting **Rename web service description**.</span></span>  
  
         <span data-ttu-id="906a8-124">![WCF サービス ページ](../core/media/35131a58-dae7-45fe-ac6a-928c8570f27d.gif "35131a58-dae7-45fe-ac6a-928c8570f27d")</span><span class="sxs-lookup"><span data-stu-id="906a8-124">![WCF Service page](../core/media/35131a58-dae7-45fe-ac6a-928c8570f27d.gif "35131a58-dae7-45fe-ac6a-928c8570f27d")</span></span>  
  
    -   <span data-ttu-id="906a8-125">Web メソッド ノード**Operation1**、既定のサービス ノードの**Service1**、既定で表示されている、 **Web サービスの説明**のダイアログ ボックスを使用して、要求-応答の受信場所。</span><span class="sxs-lookup"><span data-stu-id="906a8-125">The Web method node, **Operation1**, of the default service node, **Service1**, shown by default in the **Web service description** dialog box can be used for a request-response receive location.</span></span> <span data-ttu-id="906a8-126">一方向の WCF を選択した場合はこのサービス コントラクトの受信場所が、既定の Web メソッド ノードを右クリックし、をクリックして**web メソッドの削除**、し、次のように、一方向の Web メソッドを作成します既定のサービス ノード ポイントを右クリック。**web メソッドを追加**、クリックして**一方向**です。</span><span class="sxs-lookup"><span data-stu-id="906a8-126">If you selected a one-way WCF receive location for this service contract, right-click the default Web method node, click **Delete web method**, and then create a one-way Web method as follows: Right-click the default service node, point to **Add web method**, and then click **One-Way**.</span></span>  
  
    -   <span data-ttu-id="906a8-127">新しい WCF サービスを追加、Web サービス説明の名前を右クリックし、をクリックして**web サービスの追加**です。</span><span class="sxs-lookup"><span data-stu-id="906a8-127">To add a new WCF service, right-click the Web service description name, and then click **Add web service**.</span></span> <span data-ttu-id="906a8-128">これにより、WCF 操作なしの新しい WCF サービスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="906a8-128">This creates a new WCF service without any WCF operations.</span></span> <span data-ttu-id="906a8-129">WCF サービスの名前を変更、WCF サービス ノードを右クリックし、をクリックして**web サービスの名前を変更**、し、enter キーを押して新しい名前を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="906a8-129">To modify the name of the WCF service, right-click the WCF service node, click **Rename web service**, and then press ENTER to accept the new name.</span></span>  
  
    -   <span data-ttu-id="906a8-130">新しい WCF 操作を追加するには、WCF サービス ノードを右クリックし、 をポイント**Web メソッドの追加**、順にクリック**一方向**(要求 WCF 操作の場合) 用または**要求-応答**(用、要求-応答 WCF 操作)。</span><span class="sxs-lookup"><span data-stu-id="906a8-130">To add a new WCF operation, right-click the WCF service node, point to **Add Web Method**, and then click **One-way** (for a request WCF operation) or **Request-response** (for a request-response WCF operation).</span></span>  
  
    -   <span data-ttu-id="906a8-131">を設定する要求および応答スキーマの種類を右クリックし、**要求**または**応答**ノードをクリックして**スキーマの種類を選択**です。</span><span class="sxs-lookup"><span data-stu-id="906a8-131">To set the request and response schema types, right-click the **Request** or **Response** node, and then click **Select schema type**.</span></span> <span data-ttu-id="906a8-132">**要求メッセージの種類** ダイアログ ボックスでドキュメント スキーマを含むアセンブリの名前を入力、 **BizTalk アセンブリ ファイル**テキスト ボックスまたはクリック**参照**を検索するにはアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="906a8-132">In the **Request Message Type** dialog box, type the name of the assembly containing the document schema in the **BizTalk assembly file** text box or click **Browse** to search for the assembly.</span></span> <span data-ttu-id="906a8-133">**使用可能なスキーマ型**リスト ビューには、スキーマの各ルート要素が表示されます。</span><span class="sxs-lookup"><span data-stu-id="906a8-133">The **Available schema types** list view displays each root element of the schema.</span></span> <span data-ttu-id="906a8-134">要求または応答のスキーマの種類として追加するルート ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="906a8-134">Select a root node to add as the request or response schema type.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="906a8-135">グローバル アセンブリ キャッシュ (GAC) に、BizTalk アセンブリ ファイルがインストールされている場合はで選択するアセンブリに GAC にアセンブリが更新されたことを確認してください、**要求メッセージの種類** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="906a8-135">If you installed the BizTalk assembly file into the global assembly cache (GAC), make sure that the assembly in the GAC has been updated with the assembly that you will select in the **Request Message Type** dialog box.</span></span> <span data-ttu-id="906a8-136">GAC の完全修飾名が同じである場合、BizTalk WCF サービス公開ウィザードでは、選択したアセンブリ ファイルではなく、GAC 内のアセンブリ ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="906a8-136">If the GAC has the same fully qualified name, the BizTalk WCF Service Publishing Wizard uses the assembly file in the GAC instead of the one you selected.</span></span>  
  
         <span data-ttu-id="906a8-137">![要求メッセージの種類 ページ](../core/media/6bb4cc17-b108-4692-a5ca-548c7ef46045.gif "6bb4cc17-b108-4692-a5ca-548c7ef46045")</span><span class="sxs-lookup"><span data-stu-id="906a8-137">![Request Message Type page](../core/media/6bb4cc17-b108-4692-a5ca-548c7ef46045.gif "6bb4cc17-b108-4692-a5ca-548c7ef46045")</span></span>  
  
    -   <span data-ttu-id="906a8-138">名前を変更することができます、**要求**と**応答**生成されたコードに影響を与えずにノードです。</span><span class="sxs-lookup"><span data-stu-id="906a8-138">You can rename the **Request** and **Response** nodes without affecting the generated code.</span></span> <span data-ttu-id="906a8-139">スキーマを定義した後で部分要素の名前を変更すると、WCF 操作パラメーターの名前が変更されます。</span><span class="sxs-lookup"><span data-stu-id="906a8-139">After defining your schemas, you can rename the part elements, which modifies the WCF operation parameter name.</span></span> <span data-ttu-id="906a8-140">公開する WCF サービスのサービス メタデータを表示することで、変更内容を確認できます。</span><span class="sxs-lookup"><span data-stu-id="906a8-140">You can see the changes by viewing the service metadata for the WCF services to publish.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="906a8-141">Web サービス説明ノードの名前を変更するとき、空白文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="906a8-141">You cannot use spaces when renaming any of the Web service description nodes.</span></span>  
  
7.  <span data-ttu-id="906a8-142">をクリックして**次**ウィザードを続行します。</span><span class="sxs-lookup"><span data-stu-id="906a8-142">Click **Next** to continue the wizard.</span></span>  
  
8.  <span data-ttu-id="906a8-143">**WCF サービスのプロパティ**] ページの [、 **、WCF サービスの Targetnamespace**テキスト ボックスでは、WCF サービスのターゲットの名前空間を入力し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="906a8-143">On the **WCF Service Properties** page, in the **Targetnamespace of the WCF service** text box, type a target namespace for the WCF services, and then click **Next**.</span></span>  
  
     <span data-ttu-id="906a8-144">![WCF サービスのプロパティ ページ](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")</span><span class="sxs-lookup"><span data-stu-id="906a8-144">![WCF Service Properties page](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")</span></span>  
  
9. <span data-ttu-id="906a8-145">**WCF サービスの場所**] ページの [、**場所**テキスト ボックスに、WCF サービスが生成される Web ディレクトリ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="906a8-145">On the **WCF Service Location** page, in the **Location** text box, type the Web directory name where the WCF services are generated.</span></span> <span data-ttu-id="906a8-146">既定の場所を受け入れることができます (http://localhost/ <*Web サービス説明の名前*>)、WCF サービスの場所を入力、**場所**テキスト ボックス、またはをクリックして**を参照** Web ディレクトリを選択します。</span><span class="sxs-lookup"><span data-stu-id="906a8-146">You can accept the default location (http://localhost/<*Web service description name*>), type a location for the WCF services in the **Location** text box, or click **Browse** and select a Web directory.</span></span> <span data-ttu-id="906a8-147">次のいずれかのオプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="906a8-147">Select any of the following options:</span></span>  
  
    -   <span data-ttu-id="906a8-148">**既存のプロジェクトを上書きします。**</span><span class="sxs-lookup"><span data-stu-id="906a8-148">**Overwrite existing project.**</span></span> <span data-ttu-id="906a8-149">: このオプションは、Web ディレクトリが存在する場合のみ選択できます。</span><span class="sxs-lookup"><span data-stu-id="906a8-149">This option is available only if the Web directory already exists.</span></span> <span data-ttu-id="906a8-150">このオプションを選択すると、同じ場所にのみ公開できます。</span><span class="sxs-lookup"><span data-stu-id="906a8-150">You will be able to publish to the same location only if you select this option.</span></span> <span data-ttu-id="906a8-151">このオプションを選択しない場合は、別のプロジェクトの場所を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="906a8-151">Otherwise, you must enter a different project location.</span></span>  
  
    -   <span data-ttu-id="906a8-152">**WCF サービスへの匿名アクセスを許可します。**</span><span class="sxs-lookup"><span data-stu-id="906a8-152">**Allow anonymous access to WCF service.**</span></span> <span data-ttu-id="906a8-153">: このオプションでは、作成した仮想ディレクトリに匿名アクセスを追加します。</span><span class="sxs-lookup"><span data-stu-id="906a8-153">This option adds anonymous access to the created virtual directory.</span></span> <span data-ttu-id="906a8-154">既定では、仮想ディレクトリは、その親仮想ディレクトリまたは Web サイト (最上位の仮想ディレクトリである場合) から、アクセス権限を継承します。</span><span class="sxs-lookup"><span data-stu-id="906a8-154">By default, the virtual directory inherits the access privileges from its parent virtual directory or the Web site (if it is a top-level virtual directory).</span></span>  
  
     <span data-ttu-id="906a8-155">このページを終了したらクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="906a8-155">When you finish this page, click **Next**.</span></span>  
  
     <span data-ttu-id="906a8-156">![WCF サービスの場所 ページ](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")</span><span class="sxs-lookup"><span data-stu-id="906a8-156">![WCF Service location page](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="906a8-157">プロジェクトの場所には、別のサーバーを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="906a8-157">The project location can exist on a different server.</span></span> <span data-ttu-id="906a8-158">WCF サービスを別のサーバーで発行するプロジェクト名を入力として http://&lt です*servername*>/<*WCF サービスの場所*>。</span><span class="sxs-lookup"><span data-stu-id="906a8-158">To publish the WCF services to a different server, type the project name as http://<*servername*>/<*WCF service location*>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="906a8-159">プロジェクトの場所には、既定以外の Web サイトを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="906a8-159">The project location can exist on a non-default Web site.</span></span> <span data-ttu-id="906a8-160">既定以外の Web サイトに公開する場合は、URL に Web サイトのポート番号を含めます。</span><span class="sxs-lookup"><span data-stu-id="906a8-160">When publishing to a non-default Web site, include the port number of the Web site in the URL.</span></span> <span data-ttu-id="906a8-161">たとえば、http://&lt*servername*>: 8080/<*WCF サービスの場所*>。</span><span class="sxs-lookup"><span data-stu-id="906a8-161">For example, http://<*servername*>:8080/<*WCF service location*>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="906a8-162">このウィザードで Web アプリケーションの \App_Data\Temp フォルダーに作成される BindingInfo.xml ファイルでは、パイプラインに既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="906a8-162">The BindingInfo.xml file that the wizard creates in the \App_Data\Temp folder of the Web application uses the default values for the pipelines.</span></span> <span data-ttu-id="906a8-163">受信パイプラインの既定値は、 **Microsoft.BizTalk.DefaultPipelines.XMLReceive**パイプライン、および既定値、送信パイプラインは、 **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**パイプライン。</span><span class="sxs-lookup"><span data-stu-id="906a8-163">The default value for the receive pipeline is the **Microsoft.BizTalk.DefaultPipelines.XMLReceive** pipeline, and the default value for the send pipeline is the **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit** pipeline.</span></span>  
  
10. <span data-ttu-id="906a8-164">**WCF サービスの概要** ページで、WCF サービスの設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="906a8-164">On the **WCF Service Summary** page, review your settings for the WCF services.</span></span>  
  
11. <span data-ttu-id="906a8-165">をクリックして**作成**WCF サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="906a8-165">Click **Create** to create the WCF services.</span></span>  
  
12. <span data-ttu-id="906a8-166">をクリックして**完了**を BizTalk WCF サービス公開ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="906a8-166">Click **Finish** to complete the BizTalk WCF Service Publishing Wizard.</span></span>  
  
### <a name="to-configure-the-web-application-for-publishing-service-metadata"></a><span data-ttu-id="906a8-167">サービス メタデータを公開する Web アプリケーションを構成するには</span><span class="sxs-lookup"><span data-stu-id="906a8-167">To configure the Web application for publishing service metadata</span></span>  
  
1.  <span data-ttu-id="906a8-168">BizTalk WCF サービス公開ウィザードで作成した Web アプリケーションについて ASP.NET を有効にします。</span><span class="sxs-lookup"><span data-stu-id="906a8-168">Enable ASP.NET for the Web application that the BizTalk WCF Service Publishing Wizard created.</span></span> <span data-ttu-id="906a8-169">詳細については、次を参照してください。 [Web サービスを有効にすると](../core/enabling-web-services.md)です。</span><span class="sxs-lookup"><span data-stu-id="906a8-169">For more information, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="906a8-170">その他のバージョンの Windows オペレーティング システムを使用している場合は、アプリケーション プールの ID アカウントを BizTalk Server 管理者グループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="906a8-170">If you are using another version of the Windows operating system, you must add the Identity Account of the Application Pool to the BizTalk Server Administrators group.</span></span> <span data-ttu-id="906a8-171">BizTalk Server 管理者グループに、適切なアカウントを追加した後は、IIS サービスを有効にする設定を再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="906a8-171">After you add the appropriate account to the BizTalk Server Administrators group, you need to restart the IIS service for the setting to take effect.</span></span>  
  
2.  <span data-ttu-id="906a8-172">コマンド プロンプトを開き、BizTalk WCF サービス公開ウィザードが %SystemDrive%\InetPub で WCF サービスを作成する場所のフォルダーに移動\\、メモ帳を使用して Web.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="906a8-172">Open a command prompt, go to the folder where the BizTalk WCF Service Publishing Wizard created the WCF services in %SystemDrive%\InetPub\\, and then open the Web.config file using Notepad.</span></span>  
  
3.  <span data-ttu-id="906a8-173">メモ帳で、内部の次の行を追加、  **\<system.web\>** 要素。</span><span class="sxs-lookup"><span data-stu-id="906a8-173">In Notepad, add the following line inside the **\<system.web\>** element:</span></span>  
  
    ```  
    <trust level="Full" originUrl="" />  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="906a8-174">この設定はオプションで、公開した WCF サービスをホストする ASP.NET アプリケーションに、オペレーティング システムのセキュリティの影響下にあるリソースへのアクセス権限を与えます。</span><span class="sxs-lookup"><span data-stu-id="906a8-174">This setting is optional and it grants the ASP.NET application hosting the published WCF service access to any resource that is subject to operating system security.</span></span> <span data-ttu-id="906a8-175">これは、公開された WCF サービスと同じコンピューターで Windows SharePoint Services がインストールおよび実行されている場合に、WCF サービスの実行に必要な信頼レベルです。</span><span class="sxs-lookup"><span data-stu-id="906a8-175">This is the trust level that WCF requires when you have Windows SharePoint Services installed and running on the same machine with the published WCF services.</span></span>  
  
4.  <span data-ttu-id="906a8-176">Internet explorer で、**アドレス**ボックス、書式 http:// を使用して、WCF サービスの URL を入力*ホスト [: ポート]*/*apppath* /*名.svc*を公開した WCF サービスをテストします。</span><span class="sxs-lookup"><span data-stu-id="906a8-176">In Internet Explorer, in the **Address** box, type the URL for the WCF service using the format http://*host[:port]*/*apppath*/*wcfservicename.svc* to test the published WCF service.</span></span> <span data-ttu-id="906a8-177">次の表は、これらのパラメーターについてまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="906a8-177">The parameters are described in the following table.</span></span>  
  
    |<span data-ttu-id="906a8-178">パラメーター</span><span class="sxs-lookup"><span data-stu-id="906a8-178">Parameter</span></span>|<span data-ttu-id="906a8-179">値</span><span class="sxs-lookup"><span data-stu-id="906a8-179">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="906a8-180">*ホスト [: ポート]*</span><span class="sxs-lookup"><span data-stu-id="906a8-180">*host[:port]*</span></span>|<span data-ttu-id="906a8-181">WCF サービスを配置したコンピューターの名前です。</span><span class="sxs-lookup"><span data-stu-id="906a8-181">The name of the computer where you have deployed your WCF service.</span></span> <span data-ttu-id="906a8-182">このサーバー名の後に、コロンとポート番号を入力できます。</span><span class="sxs-lookup"><span data-stu-id="906a8-182">A colon and the port number can follow this server name.</span></span>|  
    |<span data-ttu-id="906a8-183">*アプリケーションのパス*</span><span class="sxs-lookup"><span data-stu-id="906a8-183">*apppath*</span></span>|<span data-ttu-id="906a8-184">仮想ディレクトリ名と Web アプリケーションのパスです。</span><span class="sxs-lookup"><span data-stu-id="906a8-184">The name of your virtual directory and the Web application path.</span></span>|  
    |<span data-ttu-id="906a8-185">*名.svc*</span><span class="sxs-lookup"><span data-stu-id="906a8-185">*wcfservicename.svc*</span></span>|<span data-ttu-id="906a8-186">WCF サービスの .svc ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="906a8-186">The name of the WCF service .svc file.</span></span>|  
  
5.  <span data-ttu-id="906a8-187">機密性の高いサービス メタデータが誤って漏洩を防ぐためには、次のタスクを実行することによって、実稼働環境でこの動作を無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="906a8-187">To prevent unintentional disclosure of potentially sensitive service metadata, we recommend that you disable this behavior in the production environment by performing the following tasks:</span></span>  
  
    1.  <span data-ttu-id="906a8-188">メモ帳で、%SystemDrive%\InetPub で、BizTalk WCF サービス公開ウィザードが、WCF サービスを作成するフォルダーの Web.config を開き\\です。</span><span class="sxs-lookup"><span data-stu-id="906a8-188">In Notepad, open Web.config in the folder where the BizTalk WCF Service Publishing Wizard created the WCF service in %SystemDrive%\InetPub\\.</span></span>  
  
    2.  <span data-ttu-id="906a8-189">メモ帳で、次のように設定します。、、 **httpGetEnabled**属性、  **\<serviceMetadata\>** 要素を次の行として false にします。</span><span class="sxs-lookup"><span data-stu-id="906a8-189">In Notepad, set the  the **httpGetEnabled** attribute in the  **\<serviceMetadata\>** element to false as following line:</span></span>  
  
        ```  
        <serviceMetadata httpGetEnabled="false" httpsGetEnabled="false" />  
        ```  
  
## <a name="see-also"></a><span data-ttu-id="906a8-190">参照</span><span class="sxs-lookup"><span data-stu-id="906a8-190">See Also</span></span>  
 <span data-ttu-id="906a8-191">[BizTalk WCF サービス公開ウィザードを使用してスキーマを WCF サービスとして公開する方法](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="906a8-191">[How to Use the BizTalk WCF Service Publishing Wizard to Publish Schemas as WCF Services](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md) </span></span>  
 [<span data-ttu-id="906a8-192">チュートリアル: WCF-NetMsmq アダプターを使用した WCF サービスの公開</span><span class="sxs-lookup"><span data-stu-id="906a8-192">Walkthrough: Publishing WCF Services with the WCF-NetMsmq Adapter</span></span>](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)