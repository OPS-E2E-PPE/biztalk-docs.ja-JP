---
title: 操作方法:メッセージを変換し、スケジュール ルーティング スリップを使用してファイルの場所に、結果のメッセージのルーティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c27749ba-c228-4cd4-827e-e8009a0c999d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e671e48ea2da80783b714a8be6c503b80b95f27
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399663"
---
# <a name="how-to-transform-a-message-and-route-the-resulting-message-to-a-file-location-using-an-itinerary-routing-slip"></a><span data-ttu-id="2319a-102">操作方法:メッセージを変換し、スケジュール ルーティング スリップを使用してファイルの場所に、結果のメッセージをルーティング</span><span class="sxs-lookup"><span data-stu-id="2319a-102">How to: Transform a Message and Route the Resulting Message to a File Location Using an Itinerary Routing Slip</span></span>
## <a name="goal"></a><span data-ttu-id="2319a-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="2319a-103">Goal</span></span>  
 <span data-ttu-id="2319a-104">このセクションで、ESB デザイナー ドメイン固有言語 (DSL) を使用して、BizTalk マップを呼び出すことによってメッセージの変換を実装するスケジュールを作成する方法を示すし、を使用してメッセージをルーティングし、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]ファイル アダプター。</span><span class="sxs-lookup"><span data-stu-id="2319a-104">This section demonstrates how to use the ESB Designer domain-specific language (DSL) to create an itinerary that implements message transformation by invoking a BizTalk map, and then it routes the messages using the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] FILE adapter.</span></span>  
  
 <span data-ttu-id="2319a-105">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="2319a-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="2319a-106">BizTalk マップを実装する変換のスケジュール サービスで、スケジュール ルーティング スリップを作成します。</span><span class="sxs-lookup"><span data-stu-id="2319a-106">Create an itinerary routing slip with a transform itinerary service that implements a BizTalk map.</span></span>  
  
-   <span data-ttu-id="2319a-107">ファイルの場所に変換されたメッセージをルーティングするスケジュールを構成します。</span><span class="sxs-lookup"><span data-stu-id="2319a-107">Configure the itinerary to route the transformed message to a file location.</span></span>  
  
-   <span data-ttu-id="2319a-108">旅行プランのテスト用クライアントのサンプル アプリケーションを使用して、旅行プランをテストします。</span><span class="sxs-lookup"><span data-stu-id="2319a-108">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2319a-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="2319a-109">Prerequisites</span></span>  
 <span data-ttu-id="2319a-110">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。</span><span class="sxs-lookup"><span data-stu-id="2319a-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="2319a-111">手順</span><span class="sxs-lookup"><span data-stu-id="2319a-111">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="2319a-112">ESB スケジュール オンランプ DSL モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="2319a-112">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="2319a-113">Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="2319a-113">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="2319a-114">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントして、**追加**、順にクリックします**新しい行程**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-114">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="2319a-115">**新しい項目の追加**ダイアログ ボックスで、をクリックして**ItineraryDsl**テンプレート ペインでします。</span><span class="sxs-lookup"><span data-stu-id="2319a-115">In the **Add New Item** dialog box, click **ItineraryDsl** in the Templates pane.</span></span>  
  
4.  <span data-ttu-id="2319a-116">**名前**ボックスに「 **DataModelTransformation**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-116">In the **Name** box, type **DataModelTransformation**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="2319a-117">旅行プランのプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="2319a-117">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="2319a-118">Visual Studio でのデザイン画面をクリックします。 **DataModelTransformation.itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-118">In Visual Studio, click the design surface of **DataModelTransformation.itinerary**.</span></span> <span data-ttu-id="2319a-119">**DataModelTransformation**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="2319a-119">In the **DataModelTransformation** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="2319a-120">**モデル エクスポーター**ドロップダウン リストでは、をクリックして**XML 行程エクスポーター**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-120">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="2319a-121">**エクステンダー設定**セクションで、次に、**旅行プラン XML ファイル**プロパティ、省略記号ボタン (…) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2319a-121">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="2319a-122">**XML ファイルの** ダイアログ ボックスで、**ファイル名**ボックスに「 **C:\HowTos\Itineraries\DataModelTransformation**、 をクリックし、 **を保存**.</span><span class="sxs-lookup"><span data-stu-id="2319a-122">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\DataModelTransformation**, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="2319a-123">この手順では、旅行プランを XML としてローカル ファイルの場所にエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="2319a-123">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="2319a-124">行程データベースの代わりにスケジュールをローカル ファイルの場所にエクスポートして、ESB のテスト用クライアント アプリケーションを使用してスケジュールのテストが可能です。</span><span class="sxs-lookup"><span data-stu-id="2319a-124">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="2319a-125">この操作方法に関するトピックの後半には、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="2319a-125">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="2319a-126">旅行プランの構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="2319a-126">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="2319a-127">ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。</span><span class="sxs-lookup"><span data-stu-id="2319a-127">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="2319a-128">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="2319a-128">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="2319a-129">をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-129">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="2319a-130">**エクステンダー**ドロップダウン リストでは、をクリックして**ESB サービス拡張機能の導入**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-130">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="2319a-131">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-131">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="2319a-132">**受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-132">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="2319a-133">ツールボックスからドラッグ、**行程サービス**の右側に配置し、デザイン画面に要素をモデル化し、**入口**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="2319a-133">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="2319a-134">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="2319a-134">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="2319a-135">をクリックして、**名前**プロパティ、および入力**MapNAOrderToCNOrder**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-135">Click the **Name** property, and then type **MapNAOrderToCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="2319a-136">**行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**エクステンダーのメッセージング**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-136">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="2319a-137">このプロパティは、プロセスが行われる (メッセージング) パイプラインで定義します。</span><span class="sxs-lookup"><span data-stu-id="2319a-137">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="2319a-138">または、プロセスはオーケストレーション内の場所を受け取らない場合は設定、**行程サービス エクステンダー**プロパティを**オーケストレーション エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-138">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="2319a-139">**コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、 をクリックし、**受信ハンドラー**。</span><span class="sxs-lookup"><span data-stu-id="2319a-139">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="2319a-140">**サービス名**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB.Services.Transform**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-140">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Transform**.</span></span>  
  
3.  <span data-ttu-id="2319a-141">右クリックし、**リゾルバー**のコレクション、 **MapNAOrderToCNOrder**モデル要素をクリックして**新しいリゾルバーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-141">Right-click the **Resolver** collection of the **MapNAOrderToCNOrder** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="2319a-142">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="2319a-142">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="2319a-143">をクリックして、**名前**プロパティ、および入力**StaticallySpecifyTheMap**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-143">Click the **Name** property, and then type **StaticallySpecifyTheMap**.</span></span>  
  
    2.  <span data-ttu-id="2319a-144">**リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-144">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="2319a-145">**型の変換**ドロップダウン リストでは、をクリックして**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-145">In the **Transform Type** drop-down list, click **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span></span>  
  
    4.  <span data-ttu-id="2319a-146">**トランスポート名**ドロップダウン リストでは、をクリックして**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-146">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
4.  <span data-ttu-id="2319a-147">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-147">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="2319a-148">接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **MapNAOrderToCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="2319a-148">Drag a connection from the **ReceiveNAOrder** model element to the **MapNAOrderToCNOrder** model element.</span></span>  
  
5.  <span data-ttu-id="2319a-149">ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **MapNAOrderToCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="2319a-149">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **MapNAOrderToCNOrder** model element.</span></span> <span data-ttu-id="2319a-150">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="2319a-150">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="2319a-151">をクリックして、**名前**プロパティ、および入力**SendCNOrder**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-151">Click the **Name** property, and then type **SendCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="2319a-152">**エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-152">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="2319a-153">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-153">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="2319a-154">**送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-154">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
6.  <span data-ttu-id="2319a-155">ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **MapNAOrderToCNOrder**モデル要素と**SendCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="2319a-155">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **MapNAOrderToCNOrder** model element and the **SendCNOrder** model element.</span></span> <span data-ttu-id="2319a-156">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="2319a-156">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="2319a-157">をクリックして、**名前**プロパティ、および入力**SendPortFilter**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-157">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="2319a-158">**行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ エクステンダー**。</span><span class="sxs-lookup"><span data-stu-id="2319a-158">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="2319a-159">**傾斜オフ**ドロップダウン リストで、展開**SendCNOrder**、順にクリックします**送信ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-159">In the **Off-Ramp** drop-down list, expand **SendCNOrder**, and then click **Send Handlers**.</span></span>  
  
7.  <span data-ttu-id="2319a-160">右クリックし、**リゾルバー**のコレクション、 **SendPortFilter**モデル要素をクリックして**新しいリゾルバーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-160">Right-click the **Resolver** collection of the **SendPortFilter** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="2319a-161">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="2319a-161">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="2319a-162">をクリックして、**名前**プロパティ、および入力**ConfigureFolderSettings**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-162">Click the **Name** property, and then type **ConfigureFolderSettings**.</span></span>  
  
    2.  <span data-ttu-id="2319a-163">**トランスポート名**ドロップダウン リストでは、をクリックして**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-163">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    3.  <span data-ttu-id="2319a-164">をクリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\\%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-164">Click the **Transport Location** property, and then type **C:\HowTos\Out\\%MessageID%.xml**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="2319a-165">それに関連付けられているスケジュール サービスをそれぞれオフ-ごとの傾斜増加が必要があります。旅行プラン サービスのプロパティとオフ ランプのプロパティの組み合わせでは、動的送信ポートのサブスクリプションを定義します。</span><span class="sxs-lookup"><span data-stu-id="2319a-165">Each off-ramp will have an Itinerary Service associated with it; the combination of the Itinerary Service properties and the properties of the off-ramp define the subscription of the dynamic send port.</span></span>  
  
8.  <span data-ttu-id="2319a-166">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-166">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="2319a-167">接続をドラッグして、 **MapNAOrderToCNOrder**モデル要素に、 **SendPortFilter**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="2319a-167">Drag a connection from the **MapNAOrderToCNOrder** model element to the **SendPortFilter** model element.</span></span>  
  
9. <span data-ttu-id="2319a-168">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-168">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="2319a-169">接続をドラッグして、 **SendPortFilter**モデル要素に、 **SendCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="2319a-169">Drag a connection from the **SendPortFilter** model element to the **SendCNOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="2319a-170">旅行プランのテスト クライアントで使用するモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="2319a-170">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="2319a-171">Visual Studio でのデザイン画面を右クリックし、 **DataModelTransformation**旅行プランをクリックして**モデルのエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="2319a-171">In Visual Studio, right-click the design surface of the **DataModelTransformation** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2319a-172">旅行プランの XML バージョンは、Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="2319a-172">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="2319a-173">すべてのプロジェクト成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="2319a-173">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="2319a-174">Windows エクスプ ローラーでは、C:\HowTos\Itineraries を参照し、旅行プラン XML (DataModelTransformation.xml) の作成に注意してください。</span><span class="sxs-lookup"><span data-stu-id="2319a-174">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (DataModelTransformation.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="2319a-175">旅行プランをテストするには</span><span class="sxs-lookup"><span data-stu-id="2319a-175">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="2319a-176">中に作成されたショートカットを使用してスケジュールのテスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB します。Itinerary.Test.exe - ショートカット)。</span><span class="sxs-lookup"><span data-stu-id="2319a-176">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="2319a-177">行程テスト クライアントでオフ、 **WCF サービスを使用して**チェック ボックスをオンにし**ロード行程**。</span><span class="sxs-lookup"><span data-stu-id="2319a-177">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="2319a-178">**行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="2319a-178">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="2319a-179">選択**DataModelTransformation.xml**、順にクリックします**オープン**旅行プランを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="2319a-179">Select **DataModelTransformation.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="2319a-180">をクリックして**OK**をオフに、**旅行プランは正常に読み込まれる**メッセージ。</span><span class="sxs-lookup"><span data-stu-id="2319a-180">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="2319a-181">旅行プランのテスト クライアントで、横にある省略記号ボタン (…) をクリックします。、**ロード メッセージ**ボックス。</span><span class="sxs-lookup"><span data-stu-id="2319a-181">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="2319a-182">**を読み込む XML ドキュメントの選択** ダイアログ ボックスで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="2319a-182">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="2319a-183">選択**NAOrderDoc.xml**、順にクリックします**オープン**テスト メッセージを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="2319a-183">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="2319a-184">をクリックして、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2319a-184">Click the **Submit Request** button.</span></span> <span data-ttu-id="2319a-185">テストが完了したら、クリックして**OK**表示される確認メッセージを無視します。</span><span class="sxs-lookup"><span data-stu-id="2319a-185">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="2319a-186">Windows エクスプ ローラーでは、C:\HowTos\Out を参照します。いることを確認、 **%MessageID%.xml**メッセージが、ディレクトリに書き込まれました。</span><span class="sxs-lookup"><span data-stu-id="2319a-186">In Windows Explorer, browse to C:\HowTos\Out. Verify that the **%MessageID%.xml** message has been written to the directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="2319a-187">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="2319a-187">Additional Resources</span></span>  
 <span data-ttu-id="2319a-188">詳細については、これらの関連トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2319a-188">For more information, see these related topics:</span></span>  
  
1.  [<span data-ttu-id="2319a-189">方法: インターチェンジを分割し、個別のスケジュールを使用して複数のファイルの場所に作成されるメッセージをルーティング</span><span class="sxs-lookup"><span data-stu-id="2319a-189">How to: Split an Interchange and Route the Resulting Messages to Multiple File Locations Using Distinct Itineraries</span></span>](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)  
  
2.  [<span data-ttu-id="2319a-190">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="2319a-190">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
3.  [<span data-ttu-id="2319a-191">メッセージ変換パターン</span><span class="sxs-lookup"><span data-stu-id="2319a-191">Message Transformation Patterns</span></span>](../esb-toolkit/message-transformation-patterns.md)