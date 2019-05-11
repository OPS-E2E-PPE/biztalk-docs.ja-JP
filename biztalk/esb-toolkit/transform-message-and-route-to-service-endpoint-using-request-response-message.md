---
title: 操作方法:メッセージを変換して、要求-応答のメッセージ交換パターンを使用してサービス エンドポイントへのルート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b1e656fb-6c5f-4b2b-a1b6-4c812b78ee22
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7bea07435e4d9bf10df8e47fda319a0fd106ed9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399647"
---
# <a name="how-to-transform-a-message-and-route-to-a-service-endpoint-using-a-request-response-message-exchange-pattern"></a><span data-ttu-id="58851-102">操作方法:メッセージと要求-応答のメッセージ交換パターンを使用してサービス エンドポイントへのルートを変換します。</span><span class="sxs-lookup"><span data-stu-id="58851-102">How to: Transform a Message and Route to a Service Endpoint Using a Request-Response Message Exchange Pattern</span></span>
## <a name="goal"></a><span data-ttu-id="58851-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="58851-103">Goal</span></span>  
 <span data-ttu-id="58851-104">このセクションでは、ESB デザイナー: ドメイン固有言語 (DSL) を使用して、双方向の入り口で使用できる要求-応答の旅行プランを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="58851-104">This section demonstrates how to use the ESB Designer domain-specific language (DSL) to create a request-response itinerary that can be used with a two-way on-ramp.</span></span> <span data-ttu-id="58851-105">メッセージを受信、メッセージを変換、サービスにメッセージを送信し、サービス応答メッセージを元のメッセージの送信者に返す回覧先を作成します。</span><span class="sxs-lookup"><span data-stu-id="58851-105">You will create a routing slip to receive a message, transform the message, submit the message to a service, and return the service response message to the submitter of the original message.</span></span>  
  
 <span data-ttu-id="58851-106">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="58851-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="58851-107">Microsoft BizTalk Server マップを実装する変換のスケジュール サービスで、スケジュール ルーティング スリップを作成します。</span><span class="sxs-lookup"><span data-stu-id="58851-107">Create an itinerary routing slip with a transform itinerary service that implements a Microsoft BizTalk Server map.</span></span>  
  
-   <span data-ttu-id="58851-108">サービス エンドポイントに変換されたメッセージをルーティングするスケジュールを構成します。</span><span class="sxs-lookup"><span data-stu-id="58851-108">Configure the itinerary to route the transformed message to a service endpoint.</span></span>  
  
-   <span data-ttu-id="58851-109">サービスの応答メッセージを元の送信元パーティに返す旅行プランを構成します。</span><span class="sxs-lookup"><span data-stu-id="58851-109">Configure the itinerary to return the service response message to the original sending party.</span></span>  
  
-   <span data-ttu-id="58851-110">旅行プランのテスト用クライアントのサンプル アプリケーションを使用して、旅行プランをテストします。</span><span class="sxs-lookup"><span data-stu-id="58851-110">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="58851-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="58851-111">Prerequisites</span></span>  
 <span data-ttu-id="58851-112">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。</span><span class="sxs-lookup"><span data-stu-id="58851-112">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="58851-113">手順</span><span class="sxs-lookup"><span data-stu-id="58851-113">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="58851-114">ESB スケジュール オンランプ DSL モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="58851-114">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="58851-115">Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="58851-115">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="58851-116">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントして、**追加**、順にクリックします**新しい行程**します。</span><span class="sxs-lookup"><span data-stu-id="58851-116">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="58851-117">**新しい項目の追加** ダイアログ ボックスで、**名前**ボックスに「 **RequestResponse**、 をクリックし、**追加**。</span><span class="sxs-lookup"><span data-stu-id="58851-117">In the **Add New Item** dialog box, in the **Name** box, type **RequestResponse**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="58851-118">旅行プランのプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="58851-118">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="58851-119">Visual Studio でのデザイン画面をクリックします。 **RequestResponse.itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="58851-119">In Visual Studio, click the design surface of **RequestResponse.itinerary**.</span></span> <span data-ttu-id="58851-120">**RequestResponse**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="58851-120">In the **RequestResponse** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="58851-121">**は Request Response**ドロップダウン リストでは、をクリックして**True**します。</span><span class="sxs-lookup"><span data-stu-id="58851-121">In the **Is Request Response** drop-down list, click **True**.</span></span>  
  
    2.  <span data-ttu-id="58851-122">**モデル エクスポーター**ドロップダウン リストでは、をクリックして**XML 行程エクスポーター**します。</span><span class="sxs-lookup"><span data-stu-id="58851-122">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    3.  <span data-ttu-id="58851-123">**エクステンダー設定**セクションで、次に、**旅行プラン XML ファイル**プロパティ、省略記号ボタン (…) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58851-123">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    4.  <span data-ttu-id="58851-124">**[XML ファイルの**] ダイアログ ボックスで、**ファイル名**ボックスに「 **C:\HowTos\Itineraries\RequestResponse**、順にクリックします**保存**します。</span><span class="sxs-lookup"><span data-stu-id="58851-124">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\RequestResponse**, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="58851-125">この手順では、旅行プランを XML としてローカル ファイルの場所にエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="58851-125">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="58851-126">行程データベースの代わりにスケジュールをローカル ファイルの場所にエクスポートして、ESB のテスト用クライアント アプリケーションを使用してスケジュールのテストが可能です。</span><span class="sxs-lookup"><span data-stu-id="58851-126">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="58851-127">この操作方法に関するトピックの後半には、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="58851-127">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="58851-128">旅行プランの構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="58851-128">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="58851-129">ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。</span><span class="sxs-lookup"><span data-stu-id="58851-129">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="58851-130">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="58851-130">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="58851-131">をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。</span><span class="sxs-lookup"><span data-stu-id="58851-131">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="58851-132">**エクステンダー**ドロップダウン リストでは、をクリックして**入口 ESB エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="58851-132">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="58851-133">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="58851-133">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="58851-134">**受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary.Response**します。</span><span class="sxs-lookup"><span data-stu-id="58851-134">In the **Receive Port** drop-down list, click **OnRamp.Itinerary.Response**.</span></span>  
  
2.  <span data-ttu-id="58851-135">ツールボックスからドラッグ、**行程サービス**の右側に配置し、デザイン画面に要素をモデル化し、**入口**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="58851-135">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="58851-136">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="58851-136">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="58851-137">をクリックして、**名前**プロパティ、および入力**MapNAOrderToCNOrder**します。</span><span class="sxs-lookup"><span data-stu-id="58851-137">Click the **Name** property, and then type **MapNAOrderToCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="58851-138">**行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**エクステンダーのメッセージング**します。</span><span class="sxs-lookup"><span data-stu-id="58851-138">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="58851-139">このプロパティは、プロセスが行われる (メッセージング) パイプラインで定義します。</span><span class="sxs-lookup"><span data-stu-id="58851-139">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="58851-140">または、プロセスはオーケストレーション内の場所を受け取らない場合は設定、**行程サービス エクステンダー**プロパティを**オーケストレーション エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="58851-140">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="58851-141">**コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、 をクリックし、**受信ハンドラー**。</span><span class="sxs-lookup"><span data-stu-id="58851-141">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="58851-142">**サービス名**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB.Services.Transform**します。</span><span class="sxs-lookup"><span data-stu-id="58851-142">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Transform**.</span></span>  
  
3.  <span data-ttu-id="58851-143">右クリックし、**リゾルバー**のコレクション、 **MapNAOrderToCNOrder**モデル要素をクリックして**新しいリゾルバーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="58851-143">Right-click the **Resolver** collection of the **MapNAOrderToCNOrder** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="58851-144">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="58851-144">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="58851-145">をクリックして、**名前**プロパティ、および入力**StaticallySpecifyTheMap**します。</span><span class="sxs-lookup"><span data-stu-id="58851-145">Click the **Name** property, and then type **StaticallySpecifyTheMap**.</span></span>  
  
    2.  <span data-ttu-id="58851-146">**リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。</span><span class="sxs-lookup"><span data-stu-id="58851-146">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="58851-147">**型の変換**ドロップダウン リストでは、をクリックして**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**します。</span><span class="sxs-lookup"><span data-stu-id="58851-147">In the **Transform Type** drop-down list, click **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span></span>  
  
4.  <span data-ttu-id="58851-148">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="58851-148">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="58851-149">接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **MapNAOrderToCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="58851-149">Drag a connection from the **ReceiveNAOrder** model element to the **MapNAOrderToCNOrder** model element.</span></span>  
  
5.  <span data-ttu-id="58851-150">ツールボックスからドラッグして、**行程サービス**の右側に配置し、デザイン画面に要素をモデル化し、 **MapNAOrderToCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="58851-150">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **MapNAOrderToCNOrder** model element.</span></span> <span data-ttu-id="58851-151">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="58851-151">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="58851-152">をクリックして、**名前**プロパティ、および入力**RouteToCNService**します。</span><span class="sxs-lookup"><span data-stu-id="58851-152">Click the **Name** property, and then type **RouteToCNService**.</span></span>  
  
    2.  <span data-ttu-id="58851-153">**行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**エクステンダーのメッセージング**します。</span><span class="sxs-lookup"><span data-stu-id="58851-153">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="58851-154">このプロパティは、プロセスが行われる (メッセージング) パイプラインで定義します。</span><span class="sxs-lookup"><span data-stu-id="58851-154">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="58851-155">または、プロセスはオーケストレーション内の場所を受け取らない場合は設定、**行程サービス エクステンダー**プロパティを**オーケストレーション エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="58851-155">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="58851-156">**コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、 をクリックし、**受信ハンドラー**。</span><span class="sxs-lookup"><span data-stu-id="58851-156">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="58851-157">**サービス名**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB.Services.Routing**します。</span><span class="sxs-lookup"><span data-stu-id="58851-157">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
6.  <span data-ttu-id="58851-158">右クリックし、**リゾルバー**のコレクション、 **RouteToCNService**モデル要素をクリックして**新しいリゾルバーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="58851-158">Right-click the **Resolver** collection of the **RouteToCNService** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="58851-159">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="58851-159">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="58851-160">をクリックして、**名前**プロパティ、および入力**StaticallySpecifyTheService**します。</span><span class="sxs-lookup"><span data-stu-id="58851-160">Click the **Name** property, and then type **StaticallySpecifyTheService**.</span></span>  
  
    2.  <span data-ttu-id="58851-161">**リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。</span><span class="sxs-lookup"><span data-stu-id="58851-161">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="58851-162">**トランスポート名**ドロップダウン リストでは、をクリックして**Wcf-basichttp**します。</span><span class="sxs-lookup"><span data-stu-id="58851-162">In the **Transport Name** drop-down list, click **WCF-BasicHttp**.</span></span>  
  
    4.  <span data-ttu-id="58851-163">をクリックして、**トランスポート場所**プロパティ、および入力 **http://localhost/ESB.CanadianServices/SubmitPOService.asmx**します。</span><span class="sxs-lookup"><span data-stu-id="58851-163">Click the **Transport Location** property, and then type **http://localhost/ESB.CanadianServices/SubmitPOService.asmx**.</span></span>  
  
    5.  <span data-ttu-id="58851-164">をクリックして、 **Target Namespace**プロパティ、および入力 **http://globalbank.esb.dynamicresolution.com/canadianservices**します。</span><span class="sxs-lookup"><span data-stu-id="58851-164">Click the **Target Namespace** property, and then type **http://globalbank.esb.dynamicresolution.com/canadianservices**.</span></span>  
  
    6.  <span data-ttu-id="58851-165">をクリックして、**アクション**プロパティ、および入力**submitOrder**します。</span><span class="sxs-lookup"><span data-stu-id="58851-165">Click the **Action** property, and then type **submitOrder**.</span></span>  
  
7.  <span data-ttu-id="58851-166">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="58851-166">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="58851-167">接続をドラッグして、 **MapNAOrderToCNOrder**モデル要素に、 **RouteToCNService**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="58851-167">Drag a connection from the **MapNAOrderToCNOrder** model element to the **RouteToCNService** model element.</span></span>  
  
8.  <span data-ttu-id="58851-168">ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **RouteToCNService**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="58851-168">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteToCNService** model element.</span></span> <span data-ttu-id="58851-169">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="58851-169">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="58851-170">をクリックして、**名前**プロパティ、および入力**InvokeCNService**します。</span><span class="sxs-lookup"><span data-stu-id="58851-170">Click the **Name** property, and then type **InvokeCNService**.</span></span>  
  
    2.  <span data-ttu-id="58851-171">**エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="58851-171">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="58851-172">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="58851-172">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="58851-173">**送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionSolicitResp**します。</span><span class="sxs-lookup"><span data-stu-id="58851-173">In the **Send Port** drop-down list, click **DynamicResolutionSolicitResp**.</span></span>  
  
9. <span data-ttu-id="58851-174">ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **RouteToCNService**モデル要素と**InvokeCNService**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="58851-174">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteToCNService** model element and the **InvokeCNService** model element.</span></span> <span data-ttu-id="58851-175">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="58851-175">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="58851-176">をクリックして、**名前**プロパティ、および入力**SendPortFilter**します。</span><span class="sxs-lookup"><span data-stu-id="58851-176">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="58851-177">**行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ エクステンダー**。</span><span class="sxs-lookup"><span data-stu-id="58851-177">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="58851-178">**傾斜オフ**ドロップダウン リストで、展開**InvokeCNService**、順にクリックします**送信ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="58851-178">In the **Off-Ramp** drop-down list, expand **InvokeCNService**, and then click **Send Handlers**.</span></span>  
  
10. <span data-ttu-id="58851-179">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="58851-179">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="58851-180">接続をドラッグして、 **RouteToCNService**モデル要素に、 **SendPortFilter**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="58851-180">Drag a connection from the **RouteToCNService** model element to the **SendPortFilter** model element.</span></span>  
  
11. <span data-ttu-id="58851-181">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="58851-181">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="58851-182">接続をドラッグして、 **SendPortFilter**モデル要素に、 **InvokeCNService**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="58851-182">Drag a connection from the **SendPortFilter** model element to the **InvokeCNService** model element.</span></span>  
  
12. <span data-ttu-id="58851-183">デザイン サーフェイスを右クリックし、**検証**です。</span><span class="sxs-lookup"><span data-stu-id="58851-183">Right-click the design surface, and then click **Validate**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="58851-184">旅行プランを検証します。要求元のパーティに応答メッセージを送信するには 傾斜にオフ傾斜を接続する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="58851-184">The itinerary validates; it is not necessary to connect the off-ramp back to the on-ramp in order to send the response message back to the requesting party.</span></span> <span data-ttu-id="58851-185">双方向での傾斜を使用すると、要求元のパーティに最後のメッセージが自動的に返されます。</span><span class="sxs-lookup"><span data-stu-id="58851-185">By using a two-way on-ramp, the final message is automatically returned to the requesting party.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="58851-186">旅行プランのテスト クライアントで使用するモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="58851-186">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="58851-187">Visual Studio でのデザイン画面を右クリックし、 **RequestResponse**旅行プランをクリックして**モデルのエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="58851-187">In Visual Studio, right-click the design surface of the **RequestResponse** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="58851-188">旅行プランの XML バージョンは、Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="58851-188">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="58851-189">すべてのプロジェクト成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="58851-189">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="58851-190">Windows エクスプ ローラーでは、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="58851-190">In Windows Explorer, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="58851-191">XML (RequestResponse.xml)、スケジュールの作成に注意してください。</span><span class="sxs-lookup"><span data-stu-id="58851-191">Notice the creation of your itinerary XML (RequestResponse.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="58851-192">旅行プランをテストするには</span><span class="sxs-lookup"><span data-stu-id="58851-192">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="58851-193">中に作成されたショートカットを使用してスケジュールのテスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB します。Itinerary.Test.exe - ショートカット)。</span><span class="sxs-lookup"><span data-stu-id="58851-193">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="58851-194">旅行プランのテスト クライアントでクリア、 **WCF サービスを使用して**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="58851-194">In the Itinerary Test Client, clear the **Use WCF Service** check box.</span></span>  
  
3.  <span data-ttu-id="58851-195">**Web サービス オプション**セクションで、**方法の 2 つのサービス**チェック ボックスをオンにして**ロード行程**します。</span><span class="sxs-lookup"><span data-stu-id="58851-195">In the **Web Service Options** section, select the **Two Way Service** check box, and then click **Load Itinerary**.</span></span>  
  
4.  <span data-ttu-id="58851-196">**行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="58851-196">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="58851-197">選択**RequestResponse.xml**、順にクリックします**オープン**旅行プランを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="58851-197">Select **RequestResponse.xml**, and then click **Open** to load the itinerary.</span></span>  
  
5.  <span data-ttu-id="58851-198">をクリックして**OK**をオフに、**旅行プランは正常に読み込まれる**メッセージ。</span><span class="sxs-lookup"><span data-stu-id="58851-198">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
6.  <span data-ttu-id="58851-199">旅行プランのテスト クライアントで、横にある省略記号ボタン (…) をクリックします。、**ロード メッセージ**ボックス。</span><span class="sxs-lookup"><span data-stu-id="58851-199">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
7.  <span data-ttu-id="58851-200">**を読み込む XML ドキュメントの選択** ダイアログ ボックスで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="58851-200">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="58851-201">選択**NAOrderDoc.xml**、順にクリックします**オープン**テスト メッセージを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="58851-201">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
8.  <span data-ttu-id="58851-202">をクリックして、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="58851-202">Click the **Submit Request** button.</span></span> <span data-ttu-id="58851-203">テストが完了したら、クリックして**OK**表示される確認メッセージを無視します。</span><span class="sxs-lookup"><span data-stu-id="58851-203">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
9. <span data-ttu-id="58851-204">**結果**ボックスに、メッセージのルート ノードは**submitOrderResponse**既定の名前空間としています.**canadianservices**します。</span><span class="sxs-lookup"><span data-stu-id="58851-204">In the **Results** box, notice the message's root node is **submitOrderResponse** and the default namespace is ... **canadianservices**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="58851-205">応答メッセージでは、応答が要求元のパーティに送信される前に、追加の変換が必要とする場合は、ESB フォワーダー コンポーネントを含むパイプラインを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58851-205">If the response message requires additional transformation before the response is sent to the requesting party, you must use a pipeline that contains the ESB Forwarder component.</span></span> <span data-ttu-id="58851-206">この機能の例は、次を参照してください。、[をインストールすると、複数の Web サービス サンプルを実行している](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="58851-206">For an example of this functionality, see the [Installing and Running the Multiple Web Services Sample](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md).</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="58851-207">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="58851-207">Additional Resources</span></span>  
 <span data-ttu-id="58851-208">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58851-208">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="58851-209">方法: メッセージを変換し、スケジュール ルーティング スリップを使用してファイルの場所に、結果のメッセージをルーティング</span><span class="sxs-lookup"><span data-stu-id="58851-209">How to: Transform a Message and Route the Resulting Message to a File Location Using an Itinerary Routing Slip</span></span>](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [<span data-ttu-id="58851-210">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="58851-210">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="58851-211">メッセージ ルーティング パターン</span><span class="sxs-lookup"><span data-stu-id="58851-211">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)  
  
-   [<span data-ttu-id="58851-212">複数の Web サービス サンプルをインストールし、実行する</span><span class="sxs-lookup"><span data-stu-id="58851-212">Installing and Running the Multiple Web Services Sample</span></span>](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)