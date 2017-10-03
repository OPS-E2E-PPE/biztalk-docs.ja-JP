---
title: "方法: メッセージを変換して、要求-応答メッセージ交換パターンを使用してサービス エンドポイントへのルート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b1e656fb-6c5f-4b2b-a1b6-4c812b78ee22
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dfc7c7d572f3370e87df2f03d392a993116b74d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-transform-a-message-and-route-to-a-service-endpoint-using-a-request-response-message-exchange-pattern"></a><span data-ttu-id="9632d-102">方法: メッセージを変換して、要求-応答メッセージ交換パターンを使用してサービス エンドポイントへのルート</span><span class="sxs-lookup"><span data-stu-id="9632d-102">How to: Transform a Message and Route to a Service Endpoint Using a Request-Response Message Exchange Pattern</span></span>
## <a name="goal"></a><span data-ttu-id="9632d-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="9632d-103">Goal</span></span>  
 <span data-ttu-id="9632d-104">このセクションでは、ESB デザイナー ドメイン固有言語 (DSL) を使用して、双方向に着手で使用できる要求-応答旅程を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9632d-104">This section demonstrates how to use the ESB Designer domain-specific language (DSL) to create a request-response itinerary that can be used with a two-way on-ramp.</span></span> <span data-ttu-id="9632d-105">回覧、メッセージを受信、メッセージを変換、サービスにメッセージを送信し、サービス応答メッセージを元のメッセージの送信者に返すを作成します。</span><span class="sxs-lookup"><span data-stu-id="9632d-105">You will create a routing slip to receive a message, transform the message, submit the message to a service, and return the service response message to the submitter of the original message.</span></span>  
  
 <span data-ttu-id="9632d-106">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="9632d-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="9632d-107">Microsoft BizTalk Server マップを実装する変換 itinerary サービスと旅程回覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="9632d-107">Create an itinerary routing slip with a transform itinerary service that implements a Microsoft BizTalk Server map.</span></span>  
  
-   <span data-ttu-id="9632d-108">サービス エンドポイントに変換されたメッセージをルーティングする旅程を構成します。</span><span class="sxs-lookup"><span data-stu-id="9632d-108">Configure the itinerary to route the transformed message to a service endpoint.</span></span>  
  
-   <span data-ttu-id="9632d-109">サービス応答メッセージを元の送信元パーティに返す旅程を構成します。</span><span class="sxs-lookup"><span data-stu-id="9632d-109">Configure the itinerary to return the service response message to the original sending party.</span></span>  
  
-   <span data-ttu-id="9632d-110">行程テスト用クライアントのサンプル アプリケーションを使用して旅程をテストします。</span><span class="sxs-lookup"><span data-stu-id="9632d-110">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9632d-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="9632d-111">Prerequisites</span></span>  
 <span data-ttu-id="9632d-112">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。</span><span class="sxs-lookup"><span data-stu-id="9632d-112">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="9632d-113">手順</span><span class="sxs-lookup"><span data-stu-id="9632d-113">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="9632d-114">ESB itinerary DSL モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="9632d-114">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="9632d-115">[!INCLUDE[vs2010](../includes/vs2010-md.md)]C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="9632d-115">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="9632d-116">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-116">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="9632d-117">**新しい項目の追加** ダイアログ ボックスで、**名前**ボックスに、入力**RequestResponse**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-117">In the **Add New Item** dialog box, in the **Name** box, type **RequestResponse**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="9632d-118">旅行計画のプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="9632d-118">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="9632d-119">Visual Studio でのデザイン画面をクリックして**RequestResponse.itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-119">In Visual Studio, click the design surface of **RequestResponse.itinerary**.</span></span> <span data-ttu-id="9632d-120">**RequestResponse**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9632d-120">In the **RequestResponse** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9632d-121">**は要求の応答**ドロップダウン リストをクリックして**True**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-121">In the **Is Request Response** drop-down list, click **True**.</span></span>  
  
    2.  <span data-ttu-id="9632d-122">**モデル エクスポーター**ドロップダウン リストをクリックして**XML 行程エクスポーター**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-122">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    3.  <span data-ttu-id="9632d-123">**Extender 設定**セクションで、横に、**行程 XML ファイル**プロパティ、省略記号ボタン (...) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9632d-123">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    4.  <span data-ttu-id="9632d-124">**[XML ファイルの**] ダイアログ ボックスで、**ファイル名**ボックスに、入力**C:\HowTos\Itineraries\RequestResponse**、クリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-124">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\RequestResponse**, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="9632d-125">この手順では、旅行計画をローカル ファイルの場所に XML としてエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="9632d-125">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="9632d-126">代わりに、ローカル ファイルの場所に日程を itinerary のデータベースにエクスポートして ESB のテスト用クライアント アプリケーションを使用して旅行計画のテストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9632d-126">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="9632d-127">このトピックの後半には、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="9632d-127">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="9632d-128">旅行計画の構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="9632d-128">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="9632d-129">ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。</span><span class="sxs-lookup"><span data-stu-id="9632d-129">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="9632d-130">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9632d-130">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9632d-131">クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-131">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="9632d-132">**Extender**ドロップダウン リストをクリックして**入り口 ESB Extender**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-132">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="9632d-133">**BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-133">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="9632d-134">**受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary.Response**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-134">In the **Receive Port** drop-down list, click **OnRamp.Itinerary.Response**.</span></span>  
  
2.  <span data-ttu-id="9632d-135">ツールボックスからドラッグ、**行程サービス**デザイン画面に要素をモデル化の右側に配置し、**入り口**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="9632d-135">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="9632d-136">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9632d-136">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9632d-137">クリックして、**名前**プロパティ、および入力**MapNAOrderToCNOrder**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-137">Click the **Name** property, and then type **MapNAOrderToCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="9632d-138">**行程サービス エクステンダー**ドロップダウン リストをクリックして**エクステンダーのメッセージング**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-138">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="9632d-139">このプロパティは、あるプロセスで行われます (メッセージング) パイプラインを定義します。</span><span class="sxs-lookup"><span data-stu-id="9632d-139">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="9632d-140">または、プロセスは、オーケストレーションで行われます、設定、**行程サービス エクステンダー**プロパティを**オーケストレーション Extender**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-140">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="9632d-141">**コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-141">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="9632d-142">**サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Transform**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-142">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Transform**.</span></span>  
  
3.  <span data-ttu-id="9632d-143">右クリックし、**リゾルバー**のコレクション、 **MapNAOrderToCNOrder**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-143">Right-click the **Resolver** collection of the **MapNAOrderToCNOrder** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="9632d-144">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9632d-144">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9632d-145">クリックして、**名前**プロパティ、および入力**StaticallySpecifyTheMap**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-145">Click the **Name** property, and then type **StaticallySpecifyTheMap**.</span></span>  
  
    2.  <span data-ttu-id="9632d-146">**リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="9632d-146">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="9632d-147">**型の変換**ドロップダウン リストをクリックして**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-147">In the **Transform Type** drop-down list, click **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span></span>  
  
4.  <span data-ttu-id="9632d-148">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-148">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="9632d-149">接続をドラッグして、 **ReceiveNAOrder**モデル要素を**MapNAOrderToCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="9632d-149">Drag a connection from the **ReceiveNAOrder** model element to the **MapNAOrderToCNOrder** model element.</span></span>  
  
5.  <span data-ttu-id="9632d-150">ツールボックスからドラッグして、**行程サービス**デザイン画面に要素をモデル化の右側に配置し、 **MapNAOrderToCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="9632d-150">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **MapNAOrderToCNOrder** model element.</span></span> <span data-ttu-id="9632d-151">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9632d-151">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9632d-152">クリックして、**名前**プロパティ、および入力**RouteToCNService**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-152">Click the **Name** property, and then type **RouteToCNService**.</span></span>  
  
    2.  <span data-ttu-id="9632d-153">**行程サービス エクステンダー**ドロップダウン リストをクリックして**エクステンダーのメッセージング**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-153">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="9632d-154">このプロパティは、あるプロセスで行われます (メッセージング) パイプラインを定義します。</span><span class="sxs-lookup"><span data-stu-id="9632d-154">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="9632d-155">または、プロセスは、オーケストレーションで行われます、設定、**行程サービス エクステンダー**プロパティを**オーケストレーション Extender**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-155">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="9632d-156">**コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-156">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="9632d-157">**サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Routing**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-157">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
6.  <span data-ttu-id="9632d-158">右クリックし、**リゾルバー**のコレクション、 **RouteToCNService**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-158">Right-click the **Resolver** collection of the **RouteToCNService** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="9632d-159">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9632d-159">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9632d-160">クリックして、**名前**プロパティ、および入力**StaticallySpecifyTheService**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-160">Click the **Name** property, and then type **StaticallySpecifyTheService**.</span></span>  
  
    2.  <span data-ttu-id="9632d-161">**リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="9632d-161">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="9632d-162">**トランスポート名**ドロップダウン リストをクリックして**Wcf-basichttp**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-162">In the **Transport Name** drop-down list, click **WCF-BasicHttp**.</span></span>  
  
    4.  <span data-ttu-id="9632d-163">クリックして、**トランスポート場所**プロパティ、および入力**http://localhost/ESB.CanadianServices/SubmitPOService.asmx**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-163">Click the **Transport Location** property, and then type **http://localhost/ESB.CanadianServices/SubmitPOService.asmx**.</span></span>  
  
    5.  <span data-ttu-id="9632d-164">クリックして、 **Target Namespace**プロパティ、および入力**http://globalbank.esb.dynamicresolution.com/canadianservices**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-164">Click the **Target Namespace** property, and then type **http://globalbank.esb.dynamicresolution.com/canadianservices**.</span></span>  
  
    6.  <span data-ttu-id="9632d-165">クリックして、**アクション**プロパティ、および入力**submitOrder**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-165">Click the **Action** property, and then type **submitOrder**.</span></span>  
  
7.  <span data-ttu-id="9632d-166">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-166">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="9632d-167">接続をドラッグして、 **MapNAOrderToCNOrder**モデル要素を**RouteToCNService**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="9632d-167">Drag a connection from the **MapNAOrderToCNOrder** model element to the **RouteToCNService** model element.</span></span>  
  
8.  <span data-ttu-id="9632d-168">ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **RouteToCNService**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="9632d-168">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteToCNService** model element.</span></span> <span data-ttu-id="9632d-169">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9632d-169">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9632d-170">クリックして、**名前**プロパティ、および入力**InvokeCNService**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-170">Click the **Name** property, and then type **InvokeCNService**.</span></span>  
  
    2.  <span data-ttu-id="9632d-171">**Extender**ドロップダウン リストをクリックして**出口 ESB Extender**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-171">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="9632d-172">**BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-172">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="9632d-173">**送信ポート**ドロップダウン リストをクリックして**DynamicResolutionSolicitResp**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-173">In the **Send Port** drop-down list, click **DynamicResolutionSolicitResp**.</span></span>  
  
9. <span data-ttu-id="9632d-174">ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **RouteToCNService**モデル要素と**InvokeCNService**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="9632d-174">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteToCNService** model element and the **InvokeCNService** model element.</span></span> <span data-ttu-id="9632d-175">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9632d-175">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9632d-176">クリックして、**名前**プロパティ、および入力**SendPortFilter**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-176">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="9632d-177">**行程サービス エクステンダー**ドロップダウン リストをクリックして**出口 Extender**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-177">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="9632d-178">**出口**ドロップダウン リストで、展開**InvokeCNService**、クリックして**送信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-178">In the **Off-Ramp** drop-down list, expand **InvokeCNService**, and then click **Send Handlers**.</span></span>  
  
10. <span data-ttu-id="9632d-179">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-179">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="9632d-180">接続をドラッグして、 **RouteToCNService**モデル要素を**SendPortFilter**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="9632d-180">Drag a connection from the **RouteToCNService** model element to the **SendPortFilter** model element.</span></span>  
  
11. <span data-ttu-id="9632d-181">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-181">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="9632d-182">接続をドラッグして、 **SendPortFilter**モデル要素を**InvokeCNService**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="9632d-182">Drag a connection from the **SendPortFilter** model element to the **InvokeCNService** model element.</span></span>  
  
12. <span data-ttu-id="9632d-183">デザイン サーフェイスを右クリックし、をクリックして**検証**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-183">Right-click the design surface, and then click **Validate**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9632d-184">旅行計画を検証します。要求元のパーティに応答メッセージを送信するために、入り口に戻す、出口を接続する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9632d-184">The itinerary validates; it is not necessary to connect the off-ramp back to the on-ramp in order to send the response message back to the requesting party.</span></span> <span data-ttu-id="9632d-185">双方向での傾斜を使用すると、要求元のパーティに最後のメッセージが自動的に返されます。</span><span class="sxs-lookup"><span data-stu-id="9632d-185">By using a two-way on-ramp, the final message is automatically returned to the requesting party.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="9632d-186">行程テスト クライアントで使用するモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="9632d-186">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="9632d-187">Visual Studio でのデザイン画面を右クリックし、 **RequestResponse**行程をクリックして**モデルのエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-187">In Visual Studio, right-click the design surface of the **RequestResponse** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9632d-188">旅行計画の XML バージョンは、Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="9632d-188">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="9632d-189">すべてのプロジェクトの成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="9632d-189">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="9632d-190">Windows エクスプローラで、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="9632d-190">In Windows Explorer, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="9632d-191">旅程 XML (RequestResponse.xml) の作成に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9632d-191">Notice the creation of your itinerary XML (RequestResponse.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="9632d-192">旅行計画をテストするには</span><span class="sxs-lookup"><span data-stu-id="9632d-192">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="9632d-193">中に作成されたショートカットを使用して行程テスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB です。Itinerary.Test.exe - ショートカット)。</span><span class="sxs-lookup"><span data-stu-id="9632d-193">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="9632d-194">行程テスト クライアントで、消去、**を使用して WCF サービス**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="9632d-194">In the Itinerary Test Client, clear the **Use WCF Service** check box.</span></span>  
  
3.  <span data-ttu-id="9632d-195">**Web サービス オプション** セクションで、選択、**方法の 2 つのサービス**チェック ボックスをクリックして**ロード行程**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-195">In the **Web Service Options** section, select the **Two Way Service** check box, and then click **Load Itinerary**.</span></span>  
  
4.  <span data-ttu-id="9632d-196">**行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="9632d-196">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="9632d-197">選択**RequestResponse.xml**、順にクリック**開く**日程を読み込めません。</span><span class="sxs-lookup"><span data-stu-id="9632d-197">Select **RequestResponse.xml**, and then click **Open** to load the itinerary.</span></span>  
  
5.  <span data-ttu-id="9632d-198">をクリックして**OK**をクリアする、**行程が正常に読み込まれる**メッセージ。</span><span class="sxs-lookup"><span data-stu-id="9632d-198">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
6.  <span data-ttu-id="9632d-199">行程テスト クライアントで、横にある省略記号ボタン (...) をクリックして、**メッセージの読み込み**ボックス。</span><span class="sxs-lookup"><span data-stu-id="9632d-199">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
7.  <span data-ttu-id="9632d-200">**選択読み込む XML ドキュメントを** ダイアログ ボックスで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="9632d-200">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="9632d-201">選択**NAOrderDoc.xml**、順にクリック**開く**テスト メッセージを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="9632d-201">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
8.  <span data-ttu-id="9632d-202">クリックして、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9632d-202">Click the **Submit Request** button.</span></span> <span data-ttu-id="9632d-203">テストが完了したらをクリックして**OK**表示される確認メッセージを破棄します。</span><span class="sxs-lookup"><span data-stu-id="9632d-203">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
9. <span data-ttu-id="9632d-204">**結果**ボックスでは、メッセージのルート ノードに**submitOrderResponse**既定の名前空間としています.**canadianservices**です。</span><span class="sxs-lookup"><span data-stu-id="9632d-204">In the **Results** box, notice the message's root node is **submitOrderResponse** and the default namespace is ... **canadianservices**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9632d-205">応答メッセージでは、要求元のパーティに応答を送信する前に、追加の変換が必要とする場合は、ESB フォワーダー コンポーネントを含むパイプラインを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9632d-205">If the response message requires additional transformation before the response is sent to the requesting party, you must use a pipeline that contains the ESB Forwarder component.</span></span> <span data-ttu-id="9632d-206">この機能の例は、次を参照してください。、[をインストールすると、複数の Web サービス サンプルを実行している](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="9632d-206">For an example of this functionality, see the [Installing and Running the Multiple Web Services Sample](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md).</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="9632d-207">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="9632d-207">Additional Resources</span></span>  
 <span data-ttu-id="9632d-208">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9632d-208">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="9632d-209">方法: メッセージを変換および Itinerary のルーティング先を使用してファイルの場所に、結果のメッセージをルーティング</span><span class="sxs-lookup"><span data-stu-id="9632d-209">How to: Transform a Message and Route the Resulting Message to a File Location Using an Itinerary Routing Slip</span></span>](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [<span data-ttu-id="9632d-210">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="9632d-210">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="9632d-211">メッセージのルーティング パターン</span><span class="sxs-lookup"><span data-stu-id="9632d-211">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)  
  
-   [<span data-ttu-id="9632d-212">インストールして、複数の Web サービス サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="9632d-212">Installing and Running the Multiple Web Services Sample</span></span>](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)