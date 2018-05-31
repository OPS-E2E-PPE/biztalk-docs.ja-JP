---
title: '方法: メッセージ コンテキスト プロパティを使用してコンテンツ ベース ルーティングの実装 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 952af792-5762-4b04-9087-980bb3323568
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be099923fea9d5dbb22559203b297fadf5dd1fdc
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010123"
---
# <a name="how-to-implement-content-based-routing-using-message-context-properties"></a><span data-ttu-id="aee00-102">方法: メッセージ コンテキスト プロパティを使用してコンテンツ ベース ルーティングの実装</span><span class="sxs-lookup"><span data-stu-id="aee00-102">How to: Implement Content-Based Routing Using Message Context Properties</span></span>
## <a name="goal"></a><span data-ttu-id="aee00-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="aee00-103">Goal</span></span>  
 <span data-ttu-id="aee00-104">このセクションでは、使用する方法を示します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]行程デザイナーは、メッセージ コンテキスト プロパティに基づいてメッセージの受信者を選択し、メッセージング サービス行程ブローカーを使用してその受信者にメッセージをルーティングする旅程を作成します。</span><span class="sxs-lookup"><span data-stu-id="aee00-104">This section demonstrates how to use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Itinerary Designer to create an itinerary that selects a message recipient based on the message context property and then routes a message to that recipient using the Itinerary Broker messaging service.</span></span>  
  
 <span data-ttu-id="aee00-105">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="aee00-105">In this topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="aee00-106">Itinerary ブローカーと静的な競合回避モジュールで次の 2 つのルーティング サービスでは、日程を作成します。</span><span class="sxs-lookup"><span data-stu-id="aee00-106">Create an itinerary with an itinerary broker and two routing services with static resolvers.</span></span>  
  
-   <span data-ttu-id="aee00-107">行程テスト用クライアントのサンプル アプリケーションを使用して旅程をテストします。</span><span class="sxs-lookup"><span data-stu-id="aee00-107">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aee00-108">現在の実装では、オーケストレーションに基づくブローカー サービスは用意されていません。</span><span class="sxs-lookup"><span data-stu-id="aee00-108">No orchestration-based broker service is provided in the current implementation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="aee00-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="aee00-109">Prerequisites</span></span>  
 <span data-ttu-id="aee00-110">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。</span><span class="sxs-lookup"><span data-stu-id="aee00-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="aee00-111">手順</span><span class="sxs-lookup"><span data-stu-id="aee00-111">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="aee00-112">ESB 行程 DSL モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="aee00-112">To create an ESB Itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="aee00-113">Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="aee00-113">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="aee00-114">ソリューション エクスプ ローラーで右クリック**ItineraryLibrary**、 をポイント**追加**、クリックして**新しい行程**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-114">In Solution Explorer, right-click **ItineraryLibrary**, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="aee00-115">**新しい項目の追加**ダイアログ ボックスで、をクリックして**ItineraryDsl**テンプレート ペインでします。</span><span class="sxs-lookup"><span data-stu-id="aee00-115">In the **Add New Item** dialog box, click **ItineraryDsl** in the Templates pane.</span></span>  
  
4.  <span data-ttu-id="aee00-116">**名前**ボックスに、入力**ChoiceRouter**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-116">In the **Name** box, type **ChoiceRouter**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="aee00-117">旅行計画のプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="aee00-117">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="aee00-118">Visual Studio でのデザイン画面をクリックして、 **ChoiceRouter**行程です。</span><span class="sxs-lookup"><span data-stu-id="aee00-118">In Visual Studio, click the design surface of the **ChoiceRouter** itinerary.</span></span> <span data-ttu-id="aee00-119">**ChoiceRouter**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="aee00-119">In the **ChoiceRouter** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="aee00-120">**モデル エクスポーター**ドロップダウン リストをクリックして**XML 行程エクスポーター**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-120">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="aee00-121">**Extender 設定**セクションで、横にある省略記号ボタン (...) をクリックして、**行程 XML ファイル**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="aee00-121">In the **Extender Settings** section, click the ellipsis button (...) next to the **Itinerary XML file** property.</span></span>  
  
    3.  <span data-ttu-id="aee00-122">**エクスポート モード**プロパティ ボックスの一覧をクリックして**Strict**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-122">In the **Export Mode** property drop-down list, click **Strict**.</span></span>  
  
    4.  <span data-ttu-id="aee00-123">**[XML ファイルの**] ダイアログ ボックスで、「 **C:\HowTos\Itineraries\ChoiceRouter**で、**ファイル名**ボックスをクリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-123">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\ChoiceRouter** in the **File name** box, and then click **Save**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aee00-124">この手順では、旅行計画をローカル ファイルの場所に XML としてエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="aee00-124">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="aee00-125">代わりに、ローカル ファイルの場所に日程を itinerary のデータベースにエクスポートして ESB テスト用クライアント アプリケーションを使用して旅程をテストできます。</span><span class="sxs-lookup"><span data-stu-id="aee00-125">By exporting an itinerary to a local file location, instead of to the itinerary database, you can test the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="aee00-126">このトピックの後半には、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="aee00-126">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="aee00-127">旅行計画の構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="aee00-127">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="aee00-128">ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。</span><span class="sxs-lookup"><span data-stu-id="aee00-128">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="aee00-129">OnRamp1 [プロパティ] ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="aee00-129">In the OnRamp1 Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="aee00-130">クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-130">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="aee00-131">**Extender**ドロップダウン リストをクリックして**入り口 Extender**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-131">In the **Extender** drop-down list, click **On-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="aee00-132">**BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-132">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="aee00-133">**受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-133">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="aee00-134">ツールボックスからドラッグして、**行程ブローカー サービス**の右側に配置し、デザイナー画面に要素をモデル化し、**入り口**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="aee00-134">From the Toolbox, drag an **Itinerary Broker Service** model element to the designer surface, and then place it to the right side of the **On-Ramp** model element.</span></span> <span data-ttu-id="aee00-135">**ItineraryBrokerService1**、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="aee00-135">In the **ItineraryBrokerService1**, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="aee00-136">クリックして、**名前**プロパティ、および入力**RouteBrokerService**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-136">Click the **Name** property, and then type **RouteBrokerService**.</span></span>  
  
    2.  <span data-ttu-id="aee00-137">**Extender**ドロップダウン リストをクリックして**メッセージング ブローカー Extender**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-137">In the **Extender** drop-down list, click **Messaging Broker Extender**.</span></span>  
  
    3.  <span data-ttu-id="aee00-138">**コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-138">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="aee00-139">**サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Itinerary.Services.Broker.MessagingBroker**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-139">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Itinerary.Services.Broker.MessagingBroker**.</span></span>  
  
3.  <span data-ttu-id="aee00-140">右クリックし、**フィルター**コレクション、およびクリック**新しいフィルターの追加**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-140">Right-click the **Filter** collection, and then click **Add new Filter**.</span></span> <span data-ttu-id="aee00-141">**Filter1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="aee00-141">In the **Filter1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="aee00-142">クリックして、**名前**プロパティ、および入力**ASMXFilter**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-142">Click the **Name** property, and then type **ASMXFilter**.</span></span>  
  
    2.  <span data-ttu-id="aee00-143">クリックして、**フィルター**クリックしてドロップダウン リストの実装、 **XPath フィルター**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-143">Click the **Filter** Implementation drop-down list, and then click **XPath Filter**.</span></span>  
  
    3.  <span data-ttu-id="aee00-144">クリックして、**式**プロパティ、および入力**カウント (ContextProperties/プロパティ [@name= 'InboundTransportLocation'] [が含まれています (.、'ProcessItinerary.asmx')]) > 0**します。</span><span class="sxs-lookup"><span data-stu-id="aee00-144">Click the **Expression** property, and then type **count(/ContextProperties/Property[@name='InboundTransportLocation'][contains(., 'ProcessItinerary.asmx')]) > 0**.</span></span>  
  
4.  <span data-ttu-id="aee00-145">右クリックし、**フィルター**コレクション、およびクリック**新しいフィルターの追加**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-145">Right-click the **Filter** collection, and then click **Add new Filter**.</span></span> <span data-ttu-id="aee00-146">**Filter1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="aee00-146">In the **Filter1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="aee00-147">クリックして、**名前**プロパティ、および入力**WCFFilter**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-147">Click the **Name** property, and then type **WCFFilter**.</span></span>  
  
    2.  <span data-ttu-id="aee00-148">クリックして、**フィルター実装**ドロップダウン リストをクリック**XPath フィルター**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-148">Click the **Filter Implementation** drop-down list, and click **XPath Filter**.</span></span>  
  
    3.  <span data-ttu-id="aee00-149">クリックして、**式**プロパティ、および入力**カウント (ContextProperties/プロパティ [@name= 'InboundTransportLocation'] [が含まれています (.、' ESB です。ItineraryServices.WCF')]) > 0**します。</span><span class="sxs-lookup"><span data-stu-id="aee00-149">Click the **Expression** property, and then type **count(/ContextProperties/Property[@name='InboundTransportLocation'][contains(., 'ESB.ItineraryServices.WCF')]) > 0**.</span></span>  
  
5.  <span data-ttu-id="aee00-150">右クリックし、**リゾルバー**のコレクション、 **RouteBrokerService**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-150">Right-click the **Resolver** collection of the **RouteBrokerService** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="aee00-151">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="aee00-151">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="aee00-152">クリックして、**名前**プロパティ、および入力**ResolverBrokerRoute**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-152">Click the **Name** property, and then type **ResolverBrokerRoute**.</span></span>  
  
    2.  <span data-ttu-id="aee00-153">**リゾルバーの実装**ドロップダウン リストをクリックして**MessageContext 競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="aee00-153">In the **Resolver Implementation** drop-down list, click **MessageContext Resolver Extension**.</span></span>  
  
6.  <span data-ttu-id="aee00-154">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-154">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="aee00-155">接続をドラッグして、 **ReceiveNAOrder**モデル要素を**RouteBrokerService**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="aee00-155">Drag a connection from the **ReceiveNAOrder** model element to the **RouteBrokerService** model element.</span></span>  
  
7.  <span data-ttu-id="aee00-156">ツールボックスからドラッグして、**行程サービス**の下に配置し、デザイン画面に要素をモデル化し、 **RouteBrokerService**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="aee00-156">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it under the **RouteBrokerService** model element.</span></span> <span data-ttu-id="aee00-157">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="aee00-157">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="aee00-158">クリックして、**名前**プロパティ、および入力**RouteToFileFromASMX**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-158">Click the **Name** property, and then type **RouteToFileFromASMX**.</span></span>  
  
    2.  <span data-ttu-id="aee00-159">**行程サービス エクステンダー**ドロップダウン リストをクリックして**エクステンダーのメッセージング**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-159">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="aee00-160">このプロパティは、あるプロセスで行われます (メッセージング) パイプラインを定義します。</span><span class="sxs-lookup"><span data-stu-id="aee00-160">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="aee00-161">または、プロセスは、オーケストレーションで行われます、設定、**行程サービス エクステンダー**プロパティを**オーケストレーション Extender**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-161">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="aee00-162">**コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-162">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="aee00-163">**サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Routing**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-163">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
8.  <span data-ttu-id="aee00-164">右クリックし、**リゾルバー**のコレクション、 **RouteToFileFromASMX**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-164">Right-click the **Resolver** collection of the **RouteToFileFromASMX** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="aee00-165">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="aee00-165">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="aee00-166">クリックして、**名前**プロパティ、および入力**ResolverFromAsmx**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-166">Click the **Name** property, and then type **ResolverFromAsmx**.</span></span>  
  
    2.  <span data-ttu-id="aee00-167">**リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="aee00-167">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="aee00-168">**トランスポート名**ドロップダウン リストをクリックして**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-168">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="aee00-169">クリックして、**トランスポート場所**プロパティ、および入力**c:\howtos\out\asmx%MessageId%.xml**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-169">Click the **Transport Location** property, and then type **c:\howtos\out\asmx%MessageId%.xml**.</span></span>  
  
9. <span data-ttu-id="aee00-170">ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **RouteToFileFromASMX**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="aee00-170">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteToFileFromASMX** model element.</span></span> <span data-ttu-id="aee00-171">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="aee00-171">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="aee00-172">クリックして、**名前**プロパティ、および入力**SendASMXOrder**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-172">Click the **Name** property, and then type **SendASMXOrder**.</span></span>  
  
    2.  <span data-ttu-id="aee00-173">**Extender**ドロップダウン リストをクリックして**出口 ESB Extender**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-173">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="aee00-174">**BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-174">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="aee00-175">**送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-175">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
10. <span data-ttu-id="aee00-176">ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **RouteToFileFromASMX**モデル要素と**SendASMXOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="aee00-176">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteToFileFromASMX** model element and the **SendASMXOrder** model element.</span></span> <span data-ttu-id="aee00-177">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="aee00-177">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="aee00-178">クリックして、**名前**プロパティ、および入力**SendPortFilterASMX**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-178">Click the **Name** property, and then type **SendPortFilterASMX**.</span></span>  
  
    2.  <span data-ttu-id="aee00-179">**行程サービス エクステンダー**ドロップダウン リストをクリックして**出口 Extender**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-179">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="aee00-180">**出口**ドロップダウン リストで、展開**SendASMXOrder**、クリックして**送信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-180">In the **Off-Ramp** drop-down list, expand **SendASMXOrder**, and then click **Send Handlers**.</span></span>  
  
11. <span data-ttu-id="aee00-181">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-181">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="aee00-182">接続をドラッグして、 **RouteToFileFromASMX**モデル要素を**SendPortFilterASMX**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="aee00-182">Drag a connection from the **RouteToFileFromASMX** model element to the **SendPortFilterASMX** model element.</span></span>  
  
12. <span data-ttu-id="aee00-183">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-183">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="aee00-184">接続をドラッグして、 **SendPortFilterASMX**モデル要素を**SendASMXOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="aee00-184">Drag a connection from the **SendPortFilterASMX** model element to the **SendASMXOrder** model element.</span></span>  
  
13. <span data-ttu-id="aee00-185">ツールボックスからドラッグして、**行程サービス**デザイン画面に要素をモデル化の右側に配置し、 **RouteBrokerService**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="aee00-185">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of **RouteBrokerService** model element.</span></span> <span data-ttu-id="aee00-186">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="aee00-186">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="aee00-187">クリックして、**名前**プロパティ、および入力**RouteToFileFromWCF**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-187">Click the **Name** property, and then type **RouteToFileFromWCF**.</span></span>  
  
    2.  <span data-ttu-id="aee00-188">**行程サービス エクステンダー**ドロップダウン リストをクリックして**エクステンダーのメッセージング**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-188">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="aee00-189">このプロパティは、あるプロセスで行われます (メッセージング) パイプラインを定義します。</span><span class="sxs-lookup"><span data-stu-id="aee00-189">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="aee00-190">または、プロセスは、オーケストレーションで行われます、設定、**行程サービス エクステンダー**プロパティを**オーケストレーション Extender**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-190">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="aee00-191">**コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-191">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="aee00-192">**サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Routing**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-192">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
14. <span data-ttu-id="aee00-193">右クリックし、**リゾルバー**のコレクション、 **RouteToFileFromWCF**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-193">Right-click the **Resolver** collection of the **RouteToFileFromWCF** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="aee00-194">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="aee00-194">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="aee00-195">クリックして、**名前**プロパティ、および入力**ResolverFromWCF**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-195">Click the **Name** property, and then type **ResolverFromWCF**.</span></span>  
  
    2.  <span data-ttu-id="aee00-196">**リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="aee00-196">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="aee00-197">**トランスポート名**ドロップダウン リストをクリックして**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-197">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="aee00-198">クリックして、**トランスポート場所**プロパティ、および入力**c:\howtos\out\wcf%MessageId%.xml**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-198">Click the **Transport Location** property, and then type **c:\howtos\out\wcf%MessageId%.xml**.</span></span>  
  
15. <span data-ttu-id="aee00-199">ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **RouteToFileFromWCF**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="aee00-199">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteToFileFromWCF** model element.</span></span> <span data-ttu-id="aee00-200">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="aee00-200">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="aee00-201">クリックして、**名前**プロパティ、および入力**SendWCFOrder**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-201">Click the **Name** property, and then type **SendWCFOrder**.</span></span>  
  
    2.  <span data-ttu-id="aee00-202">**Extender**ドロップダウン リストをクリックして**出口 ESB Extender**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-202">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="aee00-203">**BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-203">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="aee00-204">**送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-204">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
16. <span data-ttu-id="aee00-205">ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **RouteToFileFromWCF**モデル要素と**SendWCFOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="aee00-205">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteToFileFromWCF** model element and the **SendWCFOrder** model element.</span></span> <span data-ttu-id="aee00-206">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="aee00-206">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="aee00-207">クリックして、**名前**プロパティ、および入力**SendPortFilterWCF**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-207">Click the **Name** property, and then type **SendPortFilterWCF**.</span></span>  
  
    2.  <span data-ttu-id="aee00-208">**行程サービス エクステンダー**ドロップダウン リストをクリックして**出口 Extender**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-208">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="aee00-209">**出口**ドロップダウン リストで、展開**SendWCFOrder**、クリックして**送信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-209">In the **Off-Ramp** drop-down list, expand **SendWCFOrder**, and then click **Send Handlers**.</span></span>  
  
17. <span data-ttu-id="aee00-210">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-210">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="aee00-211">接続をドラッグして、 **RouteToFileFromWCF**モデル要素を**SendPortFilterWCF**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="aee00-211">Drag a connection from the **RouteToFileFromWCF** model element to the **SendPortFilterWCF** model element.</span></span>  
  
18. <span data-ttu-id="aee00-212">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-212">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="aee00-213">接続をドラッグして、 **SendPortFilterWCF**モデル要素を**SendWCFOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="aee00-213">Drag a connection from the **SendPortFilterWCF** model element to the **SendWCFOrder** model element.</span></span>  
  
19. <span data-ttu-id="aee00-214">ツールボックスからドラッグして、**行程 Outport**モデル要素の右側の境界線を**RouteBrokerService**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-214">From the Toolbox, drag an **Itinerary Outport** model element to right border of **RouteBrokerService**.</span></span> <span data-ttu-id="aee00-215">**ItineraryBrokerOutPort1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="aee00-215">In the **ItineraryBrokerOutPort1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="aee00-216">クリックして、**名前**プロパティ、および入力**WCF ポート**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-216">Click the **Name** property, and then type **WCF Port**.</span></span>  
  
    2.  <span data-ttu-id="aee00-217">**フィルター**ドロップダウン リストをクリックして**WCFFilter**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-217">In the **Filter** drop-down list, click **WCFFilter**.</span></span>  
  
    3.  <span data-ttu-id="aee00-218">**リゾルバー**ドロップダウン リストをクリックして**ResolverBrokerRoute**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-218">In the **Resolver** drop-down list, click **ResolverBrokerRoute**.</span></span>  
  
20. <span data-ttu-id="aee00-219">ツールボックスからドラッグして、**行程 Outport**モデル要素の下枠に**RouteBrokerService**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-219">From the Toolbox, drag an **Itinerary Outport** model element to the bottom border of **RouteBrokerService**.</span></span> <span data-ttu-id="aee00-220">**ItineraryBrokerOutPort1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="aee00-220">In the **ItineraryBrokerOutPort1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="aee00-221">クリックして、**名前**プロパティ、および入力**ASMX ポート**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-221">Click the **Name** property, and then type **ASMX Port**.</span></span>  
  
    2.  <span data-ttu-id="aee00-222">**フィルター**ドロップダウン リストをクリックして**ASMXFilter**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-222">In the **Filter** drop-down list, click **ASMXFilter**.</span></span>  
  
    3.  <span data-ttu-id="aee00-223">**リゾルバー**ドロップダウン リストをクリックして**ResolverBrokerRoute**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-223">In the **Resolver** drop-down list, click **ResolverBrokerRoute**.</span></span>  
  
21. <span data-ttu-id="aee00-224">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-224">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="aee00-225">接続をドラッグして、 **WCF ポート**モデル要素を**RouteToFileFromWCF**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="aee00-225">Drag a connection from the **WCF Port** model element to the **RouteToFileFromWCF** model element.</span></span>  
  
22. <span data-ttu-id="aee00-226">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-226">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="aee00-227">接続をドラッグして、 **ASMX ポート**モデル要素を**RouteToFileFromASMX**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="aee00-227">Drag a connection from the **ASMX Port** model element to the **RouteToFileFromASMX** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="aee00-228">行程テスト クライアントで使用するモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="aee00-228">To export the model for use with the Itinerary Test Client</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aee00-229">2 回、日程をエクスポートする必要があります: ブローカー経由のルーティングをテストするデータベースに 1 回は XML で、いずれかの時刻します。</span><span class="sxs-lookup"><span data-stu-id="aee00-229">You will need to export the itinerary twice: one time in XML and one time to the database to test the routing through the broker.</span></span>  
  
1.  <span data-ttu-id="aee00-230">Visual Studio でのデザイン画面を右クリックし、 **ChoiceRouter**行程をクリックして**モデルのエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-230">In Visual Studio, right-click the design surface of the **ChoiceRouter** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aee00-231">旅行計画の XML バージョンは、Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="aee00-231">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="aee00-232">Windows エクスプ ローラーで、C:\HowTos\Itineraries を参照し、旅程 XML (ChoiceRouter.xml) の作成を確認します。</span><span class="sxs-lookup"><span data-stu-id="aee00-232">In Windows Explorer, browse to C:\HowTos\Itineraries, and then notice the creation of your itinerary XML (ChoiceRouter.xml).</span></span>  
  
3.  <span data-ttu-id="aee00-233">Visual Studio でのデザイン画面を右クリックし、 **ChoiceRouter**行程をクリックして**モデルのエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-233">In Visual Studio, right-click the design surface of the **ChoiceRouter** itinerary, and then click **Export Model**.</span></span>  
  
4.  <span data-ttu-id="aee00-234">[プロパティ] ウィンドウでをクリックして**データベース行程エクスポーター**で、**モデル エクスポーター**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="aee00-234">In the Properties window, click **Database Itinerary Exporter** in the **Model Exporter** drop-down list.</span></span>  
  
5.  <span data-ttu-id="aee00-235">[プロパティ] ウィンドウで、設定、**行程データベース**行程データベースを指す接続文字列のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="aee00-235">In the Properties window, set the **Itinerary Database** property connection string to point to the itinerary database.</span></span>  
  
6.  <span data-ttu-id="aee00-236">**行程ステータス**プロパティのドロップダウン リストを選択**配置済み**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-236">In the **Itinerary Status** property drop-down list select **Deployed**.</span></span>  
  
7.  <span data-ttu-id="aee00-237">Visual Studio でのデザイン画面を右クリックし、 **ChoiceRouter**行程をクリックして**モデルのエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-237">In Visual Studio, right-click the design surface of the **ChoiceRouter** itinerary, and then click **Export Model**.</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="aee00-238">旅行計画をテストするには</span><span class="sxs-lookup"><span data-stu-id="aee00-238">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="aee00-239">中に作成されたショートカットを使用して行程テスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB です。Itinerary.Test.exe - ショートカット)。</span><span class="sxs-lookup"><span data-stu-id="aee00-239">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="aee00-240">行程テスト クライアントで、クリア、**を使用して WCF サービス**チェック ボックスをクリックして**ロード行程**です。</span><span class="sxs-lookup"><span data-stu-id="aee00-240">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="aee00-241">**行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="aee00-241">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="aee00-242">選択**ChoiceRouter.xml**、順にクリック**開く**日程を読み込めません。</span><span class="sxs-lookup"><span data-stu-id="aee00-242">Select **ChoiceRouter.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="aee00-243">をクリックして**OK** 「行程正しく読み込まれました」メッセージを閉じます。</span><span class="sxs-lookup"><span data-stu-id="aee00-243">Click **OK** to close the "Itinerary Loaded Successfully" message.</span></span>  
  
5.  <span data-ttu-id="aee00-244">行程テスト クライアントで、横にある省略記号ボタン (...) をクリックして、**メッセージの読み込み**ボックス。</span><span class="sxs-lookup"><span data-stu-id="aee00-244">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="aee00-245">**選択読み込む XML ドキュメントを** ダイアログ ボックスで、C:\Patterns\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="aee00-245">In the **Select XML Document to load** dialog box, browse to C:\Patterns\HowTos.</span></span> <span data-ttu-id="aee00-246">NAOrderDoc.xml を選択し、クリックして**開く**テスト メッセージを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="aee00-246">Select NAOrderDoc.xml, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="aee00-247">クリックして、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="aee00-247">Click the **Submit Request** button.</span></span> <span data-ttu-id="aee00-248">テストが完了したらをクリックして**OK**表示される確認メッセージを閉じます。</span><span class="sxs-lookup"><span data-stu-id="aee00-248">When the test completes, click **OK** to close the confirmation message that appears.</span></span>  
  
8.  <span data-ttu-id="aee00-249">Windows エクスプローラで、C:\HowTos\Out を参照します。ASMX%MessageID%.xml メッセージがこのディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="aee00-249">In Windows Explorer, browse to C:\HowTos\Out. Verify that the ASMX%MessageID%.xml messages have been written to this directory.</span></span>  
  
9. <span data-ttu-id="aee00-250">行程テスト クライアント をクリックして**を使用して WCF サービス**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="aee00-250">Click the Itinerary Test client **Use WCF Service** check box.</span></span> <span data-ttu-id="aee00-251">**行程名前**ボックスに、入力**ChoiceRouter**、をクリックし、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="aee00-251">In the **Itinerary Name** box, type **ChoiceRouter**, and then click the **Submit Request** button.</span></span> <span data-ttu-id="aee00-252">テストが完了したらをクリックして**OK**確認メッセージを閉じます。</span><span class="sxs-lookup"><span data-stu-id="aee00-252">When the test completes, click **OK** to close the confirmation message.</span></span>  
  
10. <span data-ttu-id="aee00-253">Windows エクスプローラで、C:\HowTos\Out を参照します。WCF%MessageID%.xml メッセージがこのディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="aee00-253">In Windows Explorer, browse to C:\HowTos\Out. Verify that the WCF%MessageID%.xml messages have been written to this directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="aee00-254">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="aee00-254">Additional Resources</span></span>  
 <span data-ttu-id="aee00-255">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee00-255">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="aee00-256">方法: ビジネス ルール ポリシーを使用して、日程を選択</span><span class="sxs-lookup"><span data-stu-id="aee00-256">How to: Select an Itinerary Using a Business Rules Policy</span></span>](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [<span data-ttu-id="aee00-257">方法: ビジネス ルール ポリシーを利用し、メッセージ コンテキストに基づき、メッセージの経路を動的に決定する</span><span class="sxs-lookup"><span data-stu-id="aee00-257">How to: Dynamically Route a Message Based on Message Context Using a Business Rules Policy</span></span>](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
-   [<span data-ttu-id="aee00-258">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="aee00-258">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="aee00-259">メッセージ ルーティング パターン</span><span class="sxs-lookup"><span data-stu-id="aee00-259">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)