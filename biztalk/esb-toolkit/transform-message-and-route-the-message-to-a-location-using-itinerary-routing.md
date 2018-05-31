---
title: '方法: メッセージを変換および Itinerary のルーティング先を使用してファイルの場所に、結果のメッセージをルーティング |Microsoft ドキュメント'
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
ms.openlocfilehash: 01a20c7c4a58a12f242cbd412c23e2d2fa9fe24f
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010547"
---
# <a name="how-to-transform-a-message-and-route-the-resulting-message-to-a-file-location-using-an-itinerary-routing-slip"></a><span data-ttu-id="41ee8-102">方法: メッセージを変換および Itinerary のルーティング先を使用してファイルの場所に、結果のメッセージをルーティング</span><span class="sxs-lookup"><span data-stu-id="41ee8-102">How to: Transform a Message and Route the Resulting Message to a File Location Using an Itinerary Routing Slip</span></span>
## <a name="goal"></a><span data-ttu-id="41ee8-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="41ee8-103">Goal</span></span>  
 <span data-ttu-id="41ee8-104">このセクションで、ESB デザイナー ドメイン固有言語 (DSL) を使用して、BizTalk マップを呼び出すことによってメッセージの変換を実装する旅程を作成する方法とを使用してメッセージをルーティングし、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]ファイル アダプター。</span><span class="sxs-lookup"><span data-stu-id="41ee8-104">This section demonstrates how to use the ESB Designer domain-specific language (DSL) to create an itinerary that implements message transformation by invoking a BizTalk map, and then it routes the messages using the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] FILE adapter.</span></span>  
  
 <span data-ttu-id="41ee8-105">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="41ee8-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="41ee8-106">BizTalk マップを実装する変換 itinerary サービスと旅程回覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="41ee8-106">Create an itinerary routing slip with a transform itinerary service that implements a BizTalk map.</span></span>  
  
-   <span data-ttu-id="41ee8-107">ファイルの場所に変換されたメッセージをルーティングする旅程を構成します。</span><span class="sxs-lookup"><span data-stu-id="41ee8-107">Configure the itinerary to route the transformed message to a file location.</span></span>  
  
-   <span data-ttu-id="41ee8-108">行程テスト用クライアントのサンプル アプリケーションを使用して旅程をテストします。</span><span class="sxs-lookup"><span data-stu-id="41ee8-108">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="41ee8-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="41ee8-109">Prerequisites</span></span>  
 <span data-ttu-id="41ee8-110">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="41ee8-111">手順</span><span class="sxs-lookup"><span data-stu-id="41ee8-111">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="41ee8-112">ESB itinerary DSL モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="41ee8-112">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="41ee8-113">Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="41ee8-113">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="41ee8-114">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-114">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="41ee8-115">**新しい項目の追加**ダイアログ ボックスで、をクリックして**ItineraryDsl**テンプレート ペインでします。</span><span class="sxs-lookup"><span data-stu-id="41ee8-115">In the **Add New Item** dialog box, click **ItineraryDsl** in the Templates pane.</span></span>  
  
4.  <span data-ttu-id="41ee8-116">**名前**ボックスに、入力**DataModelTransformation**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-116">In the **Name** box, type **DataModelTransformation**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="41ee8-117">旅行計画のプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="41ee8-117">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="41ee8-118">Visual Studio でのデザイン画面をクリックして**DataModelTransformation.itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-118">In Visual Studio, click the design surface of **DataModelTransformation.itinerary**.</span></span> <span data-ttu-id="41ee8-119">**DataModelTransformation**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="41ee8-119">In the **DataModelTransformation** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="41ee8-120">**モデル エクスポーター**ドロップダウン リストをクリックして**XML 行程エクスポーター**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-120">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="41ee8-121">**Extender 設定**セクションで、横に、**行程 XML ファイル**プロパティ、省略記号ボタン (...) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41ee8-121">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="41ee8-122">**[XML ファイルの**] ダイアログ ボックスで、**ファイル名**ボックスに、入力**C:\HowTos\Itineraries\DataModelTransformation**、クリックして**を保存**.</span><span class="sxs-lookup"><span data-stu-id="41ee8-122">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\DataModelTransformation**, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="41ee8-123">この手順では、旅行計画をローカル ファイルの場所に XML としてエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="41ee8-123">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="41ee8-124">代わりに、ローカル ファイルの場所に日程を itinerary のデータベースにエクスポートして ESB のテスト用クライアント アプリケーションを使用して旅行計画のテストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="41ee8-124">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="41ee8-125">このトピックの後半には、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="41ee8-125">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="41ee8-126">旅行計画の構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="41ee8-126">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="41ee8-127">ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。</span><span class="sxs-lookup"><span data-stu-id="41ee8-127">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="41ee8-128">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="41ee8-128">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="41ee8-129">クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-129">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="41ee8-130">**Extender**ドロップダウン リストをクリックして**入り口 ESB サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-130">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="41ee8-131">**BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-131">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="41ee8-132">**受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-132">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="41ee8-133">ツールボックスからドラッグ、**行程サービス**デザイン画面に要素をモデル化の右側に配置し、**入り口**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="41ee8-133">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="41ee8-134">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="41ee8-134">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="41ee8-135">クリックして、**名前**プロパティ、および入力**MapNAOrderToCNOrder**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-135">Click the **Name** property, and then type **MapNAOrderToCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="41ee8-136">**行程サービス エクステンダー**ドロップダウン リストをクリックして**エクステンダーのメッセージング**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-136">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="41ee8-137">このプロパティは、あるプロセスで行われます (メッセージング) パイプラインを定義します。</span><span class="sxs-lookup"><span data-stu-id="41ee8-137">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="41ee8-138">または、プロセスは、オーケストレーションで行われます、設定、**行程サービス エクステンダー**プロパティを**オーケストレーション Extender**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-138">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="41ee8-139">**コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-139">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="41ee8-140">**サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Transform**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-140">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Transform**.</span></span>  
  
3.  <span data-ttu-id="41ee8-141">右クリックし、**リゾルバー**のコレクション、 **MapNAOrderToCNOrder**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-141">Right-click the **Resolver** collection of the **MapNAOrderToCNOrder** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="41ee8-142">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="41ee8-142">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="41ee8-143">クリックして、**名前**プロパティ、および入力**StaticallySpecifyTheMap**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-143">Click the **Name** property, and then type **StaticallySpecifyTheMap**.</span></span>  
  
    2.  <span data-ttu-id="41ee8-144">**リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="41ee8-144">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="41ee8-145">**型の変換**ドロップダウン リストをクリックして**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-145">In the **Transform Type** drop-down list, click **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span></span>  
  
    4.  <span data-ttu-id="41ee8-146">**トランスポート名**ドロップダウン リストをクリックして**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-146">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
4.  <span data-ttu-id="41ee8-147">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-147">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="41ee8-148">接続をドラッグして、 **ReceiveNAOrder**モデル要素を**MapNAOrderToCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="41ee8-148">Drag a connection from the **ReceiveNAOrder** model element to the **MapNAOrderToCNOrder** model element.</span></span>  
  
5.  <span data-ttu-id="41ee8-149">ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **MapNAOrderToCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="41ee8-149">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **MapNAOrderToCNOrder** model element.</span></span> <span data-ttu-id="41ee8-150">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="41ee8-150">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="41ee8-151">クリックして、**名前**プロパティ、および入力**SendCNOrder**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-151">Click the **Name** property, and then type **SendCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="41ee8-152">**Extender**ドロップダウン リストをクリックして**出口 ESB Extender**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-152">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="41ee8-153">**BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-153">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="41ee8-154">**送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-154">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
6.  <span data-ttu-id="41ee8-155">ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **MapNAOrderToCNOrder**モデル要素と**SendCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="41ee8-155">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **MapNAOrderToCNOrder** model element and the **SendCNOrder** model element.</span></span> <span data-ttu-id="41ee8-156">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="41ee8-156">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="41ee8-157">クリックして、**名前**プロパティ、および入力**SendPortFilter**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-157">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="41ee8-158">**行程サービス エクステンダー**ドロップダウン リストをクリックして**出口 Extender**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-158">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="41ee8-159">**出口**ドロップダウン リストで、展開**SendCNOrder**、クリックして**送信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-159">In the **Off-Ramp** drop-down list, expand **SendCNOrder**, and then click **Send Handlers**.</span></span>  
  
7.  <span data-ttu-id="41ee8-160">右クリックし、**リゾルバー**のコレクション、 **SendPortFilter**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-160">Right-click the **Resolver** collection of the **SendPortFilter** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="41ee8-161">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="41ee8-161">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="41ee8-162">クリックして、**名前**プロパティ、および入力**ConfigureFolderSettings**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-162">Click the **Name** property, and then type **ConfigureFolderSettings**.</span></span>  
  
    2.  <span data-ttu-id="41ee8-163">**トランスポート名**ドロップダウン リストをクリックして**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-163">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    3.  <span data-ttu-id="41ee8-164">クリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\\%MessageID%.xml**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-164">Click the **Transport Location** property, and then type **C:\HowTos\Out\\%MessageID%.xml**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="41ee8-165">各出口がそれに関連付けられている行程サービスが行程サービスのプロパティと、出口のプロパティの組み合わせでは、動的送信ポートのサブスクリプションを定義します。</span><span class="sxs-lookup"><span data-stu-id="41ee8-165">Each off-ramp will have an Itinerary Service associated with it; the combination of the Itinerary Service properties and the properties of the off-ramp define the subscription of the dynamic send port.</span></span>  
  
8.  <span data-ttu-id="41ee8-166">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-166">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="41ee8-167">接続をドラッグして、 **MapNAOrderToCNOrder**モデル要素を**SendPortFilter**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="41ee8-167">Drag a connection from the **MapNAOrderToCNOrder** model element to the **SendPortFilter** model element.</span></span>  
  
9. <span data-ttu-id="41ee8-168">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-168">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="41ee8-169">接続をドラッグして、 **SendPortFilter**モデル要素を**SendCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="41ee8-169">Drag a connection from the **SendPortFilter** model element to the **SendCNOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="41ee8-170">行程テスト クライアントで使用するモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="41ee8-170">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="41ee8-171">Visual Studio でのデザイン画面を右クリックし、 **DataModelTransformation**行程をクリックして**モデルのエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-171">In Visual Studio, right-click the design surface of the **DataModelTransformation** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="41ee8-172">旅行計画の XML バージョンは、Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="41ee8-172">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="41ee8-173">すべてのプロジェクトの成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="41ee8-173">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="41ee8-174">Windows エクスプローラで、C:\HowTos\Itineraries を参照し、行程 XML (DataModelTransformation.xml) の作成に注意してください。</span><span class="sxs-lookup"><span data-stu-id="41ee8-174">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (DataModelTransformation.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="41ee8-175">旅行計画をテストするには</span><span class="sxs-lookup"><span data-stu-id="41ee8-175">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="41ee8-176">中に作成されたショートカットを使用して行程テスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB です。Itinerary.Test.exe - ショートカット)。</span><span class="sxs-lookup"><span data-stu-id="41ee8-176">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="41ee8-177">行程テスト クライアントで、クリア、**を使用して WCF サービス**チェック ボックスをクリックして**ロード行程**です。</span><span class="sxs-lookup"><span data-stu-id="41ee8-177">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="41ee8-178">**行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="41ee8-178">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="41ee8-179">選択**DataModelTransformation.xml**、順にクリック**開く**日程を読み込めません。</span><span class="sxs-lookup"><span data-stu-id="41ee8-179">Select **DataModelTransformation.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="41ee8-180">をクリックして**OK**をクリアする、**行程が正常に読み込まれる**メッセージ。</span><span class="sxs-lookup"><span data-stu-id="41ee8-180">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="41ee8-181">行程テスト クライアントで、横にある省略記号ボタン (...) をクリックして、**メッセージの読み込み**ボックス。</span><span class="sxs-lookup"><span data-stu-id="41ee8-181">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="41ee8-182">**選択読み込む XML ドキュメントを** ダイアログ ボックスで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="41ee8-182">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="41ee8-183">選択**NAOrderDoc.xml**、順にクリック**開く**テスト メッセージを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="41ee8-183">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="41ee8-184">クリックして、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="41ee8-184">Click the **Submit Request** button.</span></span> <span data-ttu-id="41ee8-185">テストが完了したらをクリックして**OK**表示される確認メッセージを破棄します。</span><span class="sxs-lookup"><span data-stu-id="41ee8-185">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="41ee8-186">Windows エクスプローラで、C:\HowTos\Out を参照します。いることを確認、 **%MessageID%.xml**ディレクトリに書き込まれたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="41ee8-186">In Windows Explorer, browse to C:\HowTos\Out. Verify that the **%MessageID%.xml** message has been written to the directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="41ee8-187">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="41ee8-187">Additional Resources</span></span>  
 <span data-ttu-id="41ee8-188">詳細については、これらの関連するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="41ee8-188">For more information, see these related topics:</span></span>  
  
1.  [<span data-ttu-id="41ee8-189">方法: 別個のスケジュールを利用し、インターチェンジを分割して結果的に生成されたメッセージを複数のファイルの場所に送る</span><span class="sxs-lookup"><span data-stu-id="41ee8-189">How to: Split an Interchange and Route the Resulting Messages to Multiple File Locations Using Distinct Itineraries</span></span>](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)  
  
2.  [<span data-ttu-id="41ee8-190">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="41ee8-190">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
3.  [<span data-ttu-id="41ee8-191">メッセージ変換パターン</span><span class="sxs-lookup"><span data-stu-id="41ee8-191">Message Transformation Patterns</span></span>](../esb-toolkit/message-transformation-patterns.md)