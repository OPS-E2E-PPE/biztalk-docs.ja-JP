---
title: 操作方法:UDDI バインド キー検索を使用してサービス エンドポイントを解決する |Microsoft Docs
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
ms.openlocfilehash: d4ce78a9637a09754e5cdb065fb25369b2ccac28
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258548"
---
# <a name="how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search"></a><span data-ttu-id="0325b-102">操作方法:UDDI バインド キー検索を使用してサービス エンドポイントを解決するには</span><span class="sxs-lookup"><span data-stu-id="0325b-102">How to: Resolve a Service Endpoint Using a UDDI Binding Key Search</span></span>
## <a name="goal"></a><span data-ttu-id="0325b-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="0325b-103">Goal</span></span>  
 <span data-ttu-id="0325b-104">このセクションでは、ESB デザイナー: ドメイン固有言語 (DSL) を使用して、スケジュールに基づくルーティング スリップ Universal Description, Discovery, を使用するを作成する方法を示しますとバインド キーを使用してサービス エンドポイントを検索する Integration (UDDI) 3 競合回避モジュール検索します。</span><span class="sxs-lookup"><span data-stu-id="0325b-104">This section demonstrates how to use the ESB Designer domain-specific language (DSL) to create an itinerary-based routing slip that uses the Universal Description, Discovery, and Integration (UDDI) 3 resolver to locate a service endpoint using a binding key search.</span></span> <span data-ttu-id="0325b-105">このシナリオでは、UDDI で公開されているファイルのエンドポイントがサービス エンドポイントになります。</span><span class="sxs-lookup"><span data-stu-id="0325b-105">In this scenario, the service endpoint will be a file endpoint published in UDDI.</span></span>  
  
 <span data-ttu-id="0325b-106">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="0325b-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="0325b-107">サービス エンドポイントを解決するのにはのスケジュール ルーティング スリップを作成します。</span><span class="sxs-lookup"><span data-stu-id="0325b-107">Create an itinerary routing slip to resolve a service endpoint.</span></span>  
  
-   <span data-ttu-id="0325b-108">UDDI 3 競合回避モジュールを使用してサービス エンドポイントにメッセージをルーティングするスケジュールを構成します。</span><span class="sxs-lookup"><span data-stu-id="0325b-108">Configure the itinerary to route the message to a service endpoint using a UDDI 3 resolver.</span></span>  
  
-   <span data-ttu-id="0325b-109">旅行プランのテスト用クライアントのサンプル アプリケーションを使用して、旅行プランをテストします。</span><span class="sxs-lookup"><span data-stu-id="0325b-109">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0325b-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="0325b-110">Prerequisites</span></span>  
 <span data-ttu-id="0325b-111">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。</span><span class="sxs-lookup"><span data-stu-id="0325b-111">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="0325b-112">手順</span><span class="sxs-lookup"><span data-stu-id="0325b-112">Steps</span></span>  
  
#### <a name="to-create-an-itinerary-model"></a><span data-ttu-id="0325b-113">スケジュール オンランプ モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="0325b-113">To create an itinerary model</span></span>  
  
1.  <span data-ttu-id="0325b-114">Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="0325b-114">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="0325b-115">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントして、**追加**、順にクリックします**新しい行程**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-115">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="0325b-116">**新しい項目の追加** ダイアログ ボックスで、**名前**ボックスに「 **UDDI3BindingKeySearch**、 をクリックし、**追加**。</span><span class="sxs-lookup"><span data-stu-id="0325b-116">In the **Add New Item** dialog box, in the **Name** box, type **UDDI3BindingKeySearch**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="0325b-117">旅行プランのプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="0325b-117">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="0325b-118">Visual Studio でのデザイン画面をクリックします。 **UDDI3BindingKeySearch.itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-118">In Visual Studio, click the design surface of **UDDI3BindingKeySearch.itinerary**.</span></span> <span data-ttu-id="0325b-119">**UDDI3BindingKeySearch**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="0325b-119">In the **UDDI3BindingKeySearch** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="0325b-120">**モデル エクスポーター**ドロップダウン リストでは、をクリックして**XML 行程エクスポーター**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-120">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="0325b-121">下、**エクステンダー設定**セクションで、横に、**旅行プラン XML ファイル**プロパティ、省略記号ボタン (…) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0325b-121">Under the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="0325b-122">**XML ファイルの**ダイアログ ボックスに「 **C:\HowTos\Itineraries\UDDI3BindingKeySearch**で、**ファイル名**ボックスをクリック**保存**.</span><span class="sxs-lookup"><span data-stu-id="0325b-122">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\UDDI3BindingKeySearch** in the **File name** box, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0325b-123">この手順では、旅行プランを XML としてローカル ファイルの場所にエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="0325b-123">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="0325b-124">行程データベースの代わりにスケジュールをローカル ファイルの場所にエクスポートして、ESB のテスト用クライアント アプリケーションを使用してスケジュールのテストが可能です。</span><span class="sxs-lookup"><span data-stu-id="0325b-124">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="0325b-125">この操作方法に関するトピックの後半には、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="0325b-125">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="0325b-126">旅行プランの構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="0325b-126">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="0325b-127">ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。</span><span class="sxs-lookup"><span data-stu-id="0325b-127">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="0325b-128">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="0325b-128">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="0325b-129">をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-129">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="0325b-130">**エクステンダー**ドロップダウン リストでは、をクリックして**入口 ESB エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-130">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="0325b-131">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-131">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="0325b-132">**受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-132">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="0325b-133">ツールボックスからドラッグして、**スケジュール サービス**デザイン サーフェイスにモデル要素。</span><span class="sxs-lookup"><span data-stu-id="0325b-133">From the Toolbox, drag an **Itinerary Service** model element to the design surface.</span></span> <span data-ttu-id="0325b-134">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="0325b-134">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="0325b-135">をクリックして、**名前**プロパティ、および入力**BindingKeyRoute**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-135">Click the **Name** property, and then type **BindingKeyRoute**.</span></span>  
  
    2.  <span data-ttu-id="0325b-136">**行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**エクステンダーのメッセージング**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-136">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
    3.  <span data-ttu-id="0325b-137">**コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、 をクリックし、**受信ハンドラー**。</span><span class="sxs-lookup"><span data-stu-id="0325b-137">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="0325b-138">**サービス名**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB.Services.Routing**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-138">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
3.  <span data-ttu-id="0325b-139">右クリックし、**リゾルバー**のコレクション、 **BindingKeyRoute**モデル要素をクリックして**新しいリゾルバーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-139">Right-click the **Resolver** collection of the **BindingKeyRoute** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="0325b-140">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="0325b-140">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="0325b-141">をクリックして、**名前**プロパティ、および入力**BindingKeySearch**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-141">Click the **Name** property, and then type **BindingKeySearch**.</span></span>  
  
    2.  <span data-ttu-id="0325b-142">**リゾルバーの実装**ドロップダウン リストでは、をクリックして**Uddi3 競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-142">In the **Resolver Implementation** drop-down list, click **Uddi3 Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="0325b-143">**リゾルバー モニカー**ドロップダウン リストでは、をクリックして**UDDI3**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-143">In the **Resolver Moniker** drop-down list, click **UDDI3**.</span></span>  
  
    4.  <span data-ttu-id="0325b-144">をクリックして、**バインド キー**プロパティ、および入力**uddi:esb:orderfileservicev3.1**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-144">Click the **Binding key** property, and then type **uddi:esb:orderfileservicev3.1**.</span></span>  
  
4.  <span data-ttu-id="0325b-145">右クリックし、 **BindingKeySearch**リゾルバー、およびクリック**テスト構成の競合回避モジュール**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-145">Right-click the **BindingKeySearch** resolver, and then click **Test Resolver Configuration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0325b-146">出力ウィンドウに表示される出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="0325b-146">Verify the output displayed in the Output window.</span></span>  
  
5.  <span data-ttu-id="0325b-147">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-147">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="0325b-148">接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **BindingKeyRoute**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="0325b-148">Drag a connection from the **ReceiveNAOrder** model element to the **BindingKeyRoute** model element.</span></span>  
  
6.  <span data-ttu-id="0325b-149">ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **BindingKeyRoute**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="0325b-149">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **BindingKeyRoute** model element.</span></span> <span data-ttu-id="0325b-150">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="0325b-150">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="0325b-151">をクリックして、**名前**プロパティ、および入力**SendNAOrder**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-151">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="0325b-152">**エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-152">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="0325b-153">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-153">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="0325b-154">**送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-154">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
7.  <span data-ttu-id="0325b-155">ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **BindingKeyRoute**モデル要素と**SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="0325b-155">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **BindingKeyRoute** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="0325b-156">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="0325b-156">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="0325b-157">をクリックして、**名前**プロパティ、および入力**SendPortFilter**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-157">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="0325b-158">**行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ エクステンダー**。</span><span class="sxs-lookup"><span data-stu-id="0325b-158">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="0325b-159">**傾斜オフ**ドロップダウン リストで、展開**SendNAOrder**、順にクリックします**送信ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-159">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
8.  <span data-ttu-id="0325b-160">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-160">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="0325b-161">接続をドラッグして、 **BindingKeyRoute**モデル要素に、 **SendPortFilter**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="0325b-161">Drag a connection from the **BindingKeyRoute** model element to the **SendPortFilter** model element.</span></span>  
  
9. <span data-ttu-id="0325b-162">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-162">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="0325b-163">接続をドラッグして、 **SendPortFilter**モデル要素に、 **SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="0325b-163">Drag a connection from the **SendPortFilter** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="0325b-164">旅行プランのテスト クライアントで使用するモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="0325b-164">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="0325b-165">Visual Studio でのデザイン画面を右クリックし、 **UDDI3BindingKeySearch**旅行プランをクリックして**モデルのエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="0325b-165">In Visual Studio, right-click the design surface of the **UDDI3BindingKeySearch** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0325b-166">旅行プランの XML バージョンは、Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="0325b-166">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="0325b-167">すべてのプロジェクト成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="0325b-167">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="0325b-168">Windows エクスプ ローラーでは、C:\HowTos\Itineraries を参照し、旅行プラン XML (UDDI3BindingKeySearch.xml) の作成に注意してください。</span><span class="sxs-lookup"><span data-stu-id="0325b-168">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (UDDI3BindingKeySearch.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="0325b-169">旅行プランをテストするには</span><span class="sxs-lookup"><span data-stu-id="0325b-169">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="0325b-170">中に作成されたショートカットを使用してスケジュールのテスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB します。Itinerary.Test.exe - ショートカット)。</span><span class="sxs-lookup"><span data-stu-id="0325b-170">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="0325b-171">行程テスト クライアントでオフ、 **WCF サービスを使用して**チェック ボックスをオンにし**ロード行程**。</span><span class="sxs-lookup"><span data-stu-id="0325b-171">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="0325b-172">旅行プラン ファイルを開く ダイアログ ボックスでは、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="0325b-172">In the Open Itinerary File dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="0325b-173">UDDI3BindingKeySearch.xml を選択し、旅行プランを読み込む をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0325b-173">Select UDDI3BindingKeySearch.xml, and then click Open to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="0325b-174">をクリックして**OK**をオフに、**旅行プランは正常に読み込まれる**メッセージ。</span><span class="sxs-lookup"><span data-stu-id="0325b-174">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="0325b-175">旅行プランのテスト クライアントで、横にある省略記号ボタン (…) をクリックします。、**ロード メッセージ**ボックス。</span><span class="sxs-lookup"><span data-stu-id="0325b-175">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="0325b-176">**を読み込む XML ドキュメントの選択** ダイアログ ボックスで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="0325b-176">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="0325b-177">選択**NAOrderDoc.xml**、順にクリックします**オープン**テスト メッセージを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="0325b-177">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="0325b-178">をクリックして、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0325b-178">Click the **Submit Request** button.</span></span> <span data-ttu-id="0325b-179">テストが完了したら、クリックして**OK**表示される確認メッセージを無視します。</span><span class="sxs-lookup"><span data-stu-id="0325b-179">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="0325b-180">Windows エクスプ ローラーでは、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out を参照します。%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="0325b-180">In Windows Explorer, browse to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out. Verify that the %MessageID%.xml message has been written to the directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="0325b-181">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="0325b-181">Additional Resources</span></span>  
 <span data-ttu-id="0325b-182">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0325b-182">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="0325b-183">方法: UDDI カテゴリ検索を使用してサービス エンドポイントを解決するには</span><span class="sxs-lookup"><span data-stu-id="0325b-183">How to: Resolve a Service Endpoint Using a UDDI Category Search</span></span>](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-category-search.md)  
  
-   [<span data-ttu-id="0325b-184">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="0325b-184">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="0325b-185">動的な解決とルーティングを利用する</span><span class="sxs-lookup"><span data-stu-id="0325b-185">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)