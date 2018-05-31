---
title: '方法: キーの検索をバインド UDDI を使用してサービス エンドポイントを解決するには |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a685641-2beb-4153-a9ba-c766679ce48e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d286f3dd48daa7cc0ddd16f4abda601cf9e8a5f7
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010563"
---
# <a name="how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search"></a><span data-ttu-id="bcdee-102">方法: キーの検索をバインド UDDI を使用してサービス エンドポイントを解決するには</span><span class="sxs-lookup"><span data-stu-id="bcdee-102">How to: Resolve a Service Endpoint Using a UDDI Binding Key Search</span></span>
## <a name="goal"></a><span data-ttu-id="bcdee-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="bcdee-103">Goal</span></span>  
 <span data-ttu-id="bcdee-104">このセクションでは、ESB デザイナー ドメイン固有言語 (DSL) を使用して、行程ベース回覧 Universal Description, Discovery, を使用するを作成する方法を示しますとバインド キーを使用してサービス エンドポイントを検索する Integration (UDDI) 3 競合回避モジュール検索します。</span><span class="sxs-lookup"><span data-stu-id="bcdee-104">This section demonstrates how to use the ESB Designer domain-specific language (DSL) to create an itinerary-based routing slip that uses the Universal Description, Discovery, and Integration (UDDI) 3 resolver to locate a service endpoint using a binding key search.</span></span> <span data-ttu-id="bcdee-105">このシナリオでは、UDDI で公開されるファイル エンドポイントがサービス エンドポイントになります。</span><span class="sxs-lookup"><span data-stu-id="bcdee-105">In this scenario, the service endpoint will be a file endpoint published in UDDI.</span></span>  
  
 <span data-ttu-id="bcdee-106">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="bcdee-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="bcdee-107">サービス エンドポイントを解決するのには itinerary 回覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="bcdee-107">Create an itinerary routing slip to resolve a service endpoint.</span></span>  
  
-   <span data-ttu-id="bcdee-108">UDDI 3 競合回避モジュールを使用してサービス エンドポイントにメッセージをルーティングする旅程を構成します。</span><span class="sxs-lookup"><span data-stu-id="bcdee-108">Configure the itinerary to route the message to a service endpoint using a UDDI 3 resolver.</span></span>  
  
-   <span data-ttu-id="bcdee-109">行程テスト用クライアントのサンプル アプリケーションを使用して旅程をテストします。</span><span class="sxs-lookup"><span data-stu-id="bcdee-109">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bcdee-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="bcdee-110">Prerequisites</span></span>  
 <span data-ttu-id="bcdee-111">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-111">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="bcdee-112">手順</span><span class="sxs-lookup"><span data-stu-id="bcdee-112">Steps</span></span>  
  
#### <a name="to-create-an-itinerary-model"></a><span data-ttu-id="bcdee-113">Itinerary モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="bcdee-113">To create an itinerary model</span></span>  
  
1.  <span data-ttu-id="bcdee-114">Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="bcdee-114">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="bcdee-115">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-115">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="bcdee-116">**新しい項目の追加** ダイアログ ボックスで、**名前**ボックスに、入力**UDDI3BindingKeySearch**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-116">In the **Add New Item** dialog box, in the **Name** box, type **UDDI3BindingKeySearch**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="bcdee-117">旅行計画のプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="bcdee-117">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="bcdee-118">Visual Studio でのデザイン画面をクリックして**UDDI3BindingKeySearch.itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-118">In Visual Studio, click the design surface of **UDDI3BindingKeySearch.itinerary**.</span></span> <span data-ttu-id="bcdee-119">**UDDI3BindingKeySearch**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="bcdee-119">In the **UDDI3BindingKeySearch** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="bcdee-120">**モデル エクスポーター**ドロップダウン リストをクリックして**XML 行程エクスポーター**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-120">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="bcdee-121">下にある、 **Extender の設定**セクションで、次に、**行程 XML ファイル**プロパティ、省略記号ボタン (...) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bcdee-121">Under the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="bcdee-122">**[XML ファイルの**] ダイアログ ボックスで、「 **C:\HowTos\Itineraries\UDDI3BindingKeySearch**で、**ファイル名**ボックスをクリックして**を保存**.</span><span class="sxs-lookup"><span data-stu-id="bcdee-122">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\UDDI3BindingKeySearch** in the **File name** box, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="bcdee-123">この手順では、旅行計画をローカル ファイルの場所に XML としてエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="bcdee-123">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="bcdee-124">代わりに、ローカル ファイルの場所に日程を itinerary のデータベースにエクスポートして ESB のテスト用クライアント アプリケーションを使用して旅行計画のテストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="bcdee-124">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="bcdee-125">このトピックの後半には、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="bcdee-125">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="bcdee-126">旅行計画の構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="bcdee-126">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="bcdee-127">ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。</span><span class="sxs-lookup"><span data-stu-id="bcdee-127">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="bcdee-128">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="bcdee-128">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="bcdee-129">クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-129">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="bcdee-130">**Extender**ドロップダウン リストをクリックして**入り口 ESB Extender**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-130">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="bcdee-131">**BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-131">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="bcdee-132">**受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-132">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="bcdee-133">ツールボックスからドラッグして、**行程サービス**デザイン画面にモデル要素。</span><span class="sxs-lookup"><span data-stu-id="bcdee-133">From the Toolbox, drag an **Itinerary Service** model element to the design surface.</span></span> <span data-ttu-id="bcdee-134">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="bcdee-134">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="bcdee-135">クリックして、**名前**プロパティ、および入力**BindingKeyRoute**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-135">Click the **Name** property, and then type **BindingKeyRoute**.</span></span>  
  
    2.  <span data-ttu-id="bcdee-136">**行程サービス エクステンダー**ドロップダウン リストをクリックして**エクステンダーのメッセージング**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-136">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
    3.  <span data-ttu-id="bcdee-137">**コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-137">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="bcdee-138">**サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Routing**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-138">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
3.  <span data-ttu-id="bcdee-139">右クリックし、**リゾルバー**のコレクション、 **BindingKeyRoute**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-139">Right-click the **Resolver** collection of the **BindingKeyRoute** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="bcdee-140">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="bcdee-140">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="bcdee-141">クリックして、**名前**プロパティ、および入力**BindingKeySearch**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-141">Click the **Name** property, and then type **BindingKeySearch**.</span></span>  
  
    2.  <span data-ttu-id="bcdee-142">**リゾルバーの実装**ドロップダウン リストをクリックして**Uddi3 競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="bcdee-142">In the **Resolver Implementation** drop-down list, click **Uddi3 Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="bcdee-143">**リゾルバー モニカー**ドロップダウン リストをクリックして**UDDI3**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-143">In the **Resolver Moniker** drop-down list, click **UDDI3**.</span></span>  
  
    4.  <span data-ttu-id="bcdee-144">クリックして、**バインド キー**プロパティ、および入力**uddi:esb:orderfileservicev3.1**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-144">Click the **Binding key** property, and then type **uddi:esb:orderfileservicev3.1**.</span></span>  
  
4.  <span data-ttu-id="bcdee-145">右クリックし、 **BindingKeySearch**リゾルバーをクリックして**テスト構成の競合回避モジュール**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-145">Right-click the **BindingKeySearch** resolver, and then click **Test Resolver Configuration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bcdee-146">出力ウィンドウに表示される出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="bcdee-146">Verify the output displayed in the Output window.</span></span>  
  
5.  <span data-ttu-id="bcdee-147">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-147">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="bcdee-148">接続をドラッグして、 **ReceiveNAOrder**モデル要素を**BindingKeyRoute**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="bcdee-148">Drag a connection from the **ReceiveNAOrder** model element to the **BindingKeyRoute** model element.</span></span>  
  
6.  <span data-ttu-id="bcdee-149">ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **BindingKeyRoute**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="bcdee-149">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **BindingKeyRoute** model element.</span></span> <span data-ttu-id="bcdee-150">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="bcdee-150">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="bcdee-151">クリックして、**名前**プロパティ、および入力**SendNAOrder**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-151">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="bcdee-152">**Extender**ドロップダウン リストをクリックして**出口 ESB Extender**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-152">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="bcdee-153">**BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-153">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="bcdee-154">**送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-154">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
7.  <span data-ttu-id="bcdee-155">ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **BindingKeyRoute**モデル要素と**SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="bcdee-155">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **BindingKeyRoute** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="bcdee-156">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="bcdee-156">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="bcdee-157">クリックして、**名前**プロパティ、および入力**SendPortFilter**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-157">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="bcdee-158">**行程サービス エクステンダー**ドロップダウン リストをクリックして**出口 Extender**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-158">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="bcdee-159">**出口**ドロップダウン リストで、展開**SendNAOrder**、クリックして**送信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-159">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
8.  <span data-ttu-id="bcdee-160">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-160">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="bcdee-161">接続をドラッグして、 **BindingKeyRoute**モデル要素を**SendPortFilter**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="bcdee-161">Drag a connection from the **BindingKeyRoute** model element to the **SendPortFilter** model element.</span></span>  
  
9. <span data-ttu-id="bcdee-162">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-162">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="bcdee-163">接続をドラッグして、 **SendPortFilter**モデル要素を**SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="bcdee-163">Drag a connection from the **SendPortFilter** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="bcdee-164">行程テスト クライアントで使用するモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="bcdee-164">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="bcdee-165">Visual Studio でのデザイン画面を右クリックし、 **UDDI3BindingKeySearch**行程をクリックして**モデルのエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-165">In Visual Studio, right-click the design surface of the **UDDI3BindingKeySearch** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bcdee-166">旅行計画の XML バージョンは、Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="bcdee-166">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="bcdee-167">すべてのプロジェクトの成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="bcdee-167">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="bcdee-168">Windows エクスプローラで、C:\HowTos\Itineraries を参照し、行程 XML (UDDI3BindingKeySearch.xml) の作成に注意してください。</span><span class="sxs-lookup"><span data-stu-id="bcdee-168">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (UDDI3BindingKeySearch.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="bcdee-169">旅行計画をテストするには</span><span class="sxs-lookup"><span data-stu-id="bcdee-169">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="bcdee-170">中に作成されたショートカットを使用して行程テスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB です。Itinerary.Test.exe - ショートカット)。</span><span class="sxs-lookup"><span data-stu-id="bcdee-170">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="bcdee-171">行程テスト クライアントで、クリア、**を使用して WCF サービス**チェック ボックスをクリックして**ロード行程**です。</span><span class="sxs-lookup"><span data-stu-id="bcdee-171">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="bcdee-172">行程ファイルを開く ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="bcdee-172">In the Open Itinerary File dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="bcdee-173">UDDI3BindingKeySearch.xml を選択し、日程を読み込む をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bcdee-173">Select UDDI3BindingKeySearch.xml, and then click Open to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="bcdee-174">をクリックして**OK**をクリアする、**行程が正常に読み込まれる**メッセージ。</span><span class="sxs-lookup"><span data-stu-id="bcdee-174">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="bcdee-175">行程テスト クライアントで、横にある省略記号ボタン (...) をクリックして、**メッセージの読み込み**ボックス。</span><span class="sxs-lookup"><span data-stu-id="bcdee-175">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="bcdee-176">**選択読み込む XML ドキュメントを** ダイアログ ボックスで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="bcdee-176">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="bcdee-177">選択**NAOrderDoc.xml**、順にクリック**開く**テスト メッセージを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="bcdee-177">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="bcdee-178">クリックして、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bcdee-178">Click the **Submit Request** button.</span></span> <span data-ttu-id="bcdee-179">テストが完了したらをクリックして**OK**表示される確認メッセージを破棄します。</span><span class="sxs-lookup"><span data-stu-id="bcdee-179">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="bcdee-180">Windows エクスプローラで、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out を参照します。%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="bcdee-180">In Windows Explorer, browse to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out. Verify that the %MessageID%.xml message has been written to the directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="bcdee-181">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="bcdee-181">Additional Resources</span></span>  
 <span data-ttu-id="bcdee-182">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcdee-182">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="bcdee-183">方法: UDDI カテゴリ検索を利用し、サービス エンドポイントを解決する</span><span class="sxs-lookup"><span data-stu-id="bcdee-183">How to: Resolve a Service Endpoint Using a UDDI Category Search</span></span>](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-category-search.md)  
  
-   [<span data-ttu-id="bcdee-184">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="bcdee-184">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="bcdee-185">動的な解決とルーティングを利用する</span><span class="sxs-lookup"><span data-stu-id="bcdee-185">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)