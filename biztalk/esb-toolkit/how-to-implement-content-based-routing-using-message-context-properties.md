---
title: 操作方法:メッセージ コンテキスト プロパティを使用してコンテンツ ベース ルーティングの実装 |Microsoft Docs
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
ms.openlocfilehash: 200341cb4866806429ee132d07f17b94379a9583
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295817"
---
# <a name="how-to-implement-content-based-routing-using-message-context-properties"></a><span data-ttu-id="03c23-102">操作方法:メッセージ コンテキスト プロパティを使用してコンテンツ ベース ルーティングを実装します。</span><span class="sxs-lookup"><span data-stu-id="03c23-102">How to: Implement Content-Based Routing Using Message Context Properties</span></span>
## <a name="goal"></a><span data-ttu-id="03c23-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="03c23-103">Goal</span></span>  
 <span data-ttu-id="03c23-104">このセクションで使用する方法を示す、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]行程デザイナーは、メッセージ コンテキスト プロパティに基づいてメッセージの受信者を選択し、日程のブローカー メッセージング サービスを使用して、その受信者にメッセージをルーティングするスケジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="03c23-104">This section demonstrates how to use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Itinerary Designer to create an itinerary that selects a message recipient based on the message context property and then routes a message to that recipient using the Itinerary Broker messaging service.</span></span>  
  
 <span data-ttu-id="03c23-105">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="03c23-105">In this topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="03c23-106">スケジュール オンランプのブローカーと静的な競合回避モジュールで 2 つのルーティング サービスで、旅行プランを作成します。</span><span class="sxs-lookup"><span data-stu-id="03c23-106">Create an itinerary with an itinerary broker and two routing services with static resolvers.</span></span>  
  
-   <span data-ttu-id="03c23-107">旅行プランのテスト用クライアントのサンプル アプリケーションを使用して、旅行プランをテストします。</span><span class="sxs-lookup"><span data-stu-id="03c23-107">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03c23-108">現在の実装では、オーケストレーションに基づくブローカー サービスは提供されません。</span><span class="sxs-lookup"><span data-stu-id="03c23-108">No orchestration-based broker service is provided in the current implementation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="03c23-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="03c23-109">Prerequisites</span></span>  
 <span data-ttu-id="03c23-110">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。</span><span class="sxs-lookup"><span data-stu-id="03c23-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="03c23-111">手順</span><span class="sxs-lookup"><span data-stu-id="03c23-111">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="03c23-112">ESB 行程 DSL モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="03c23-112">To create an ESB Itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="03c23-113">Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="03c23-113">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="03c23-114">ソリューション エクスプ ローラーで右クリック**ItineraryLibrary**、 をポイント**追加**、 をクリックし、**新しいスケジュール**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-114">In Solution Explorer, right-click **ItineraryLibrary**, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="03c23-115">**新しい項目の追加**ダイアログ ボックスで、をクリックして**ItineraryDsl**テンプレート ペインでします。</span><span class="sxs-lookup"><span data-stu-id="03c23-115">In the **Add New Item** dialog box, click **ItineraryDsl** in the Templates pane.</span></span>  
  
4.  <span data-ttu-id="03c23-116">**名前**ボックスに「 **ChoiceRouter**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-116">In the **Name** box, type **ChoiceRouter**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="03c23-117">旅行プランのプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="03c23-117">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="03c23-118">Visual Studio でのデザイン画面をクリックして、 **ChoiceRouter**スケジュールします。</span><span class="sxs-lookup"><span data-stu-id="03c23-118">In Visual Studio, click the design surface of the **ChoiceRouter** itinerary.</span></span> <span data-ttu-id="03c23-119">**ChoiceRouter**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="03c23-119">In the **ChoiceRouter** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="03c23-120">**モデル エクスポーター**ドロップダウン リストでは、をクリックして**XML 行程エクスポーター**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-120">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="03c23-121">**エクステンダー設定**セクションで、横にある省略記号ボタン (…) をクリックして、**旅行プラン XML ファイル**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="03c23-121">In the **Extender Settings** section, click the ellipsis button (...) next to the **Itinerary XML file** property.</span></span>  
  
    3.  <span data-ttu-id="03c23-122">**エクスポート モード**プロパティのドロップダウン リストをクリックして**Strict**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-122">In the **Export Mode** property drop-down list, click **Strict**.</span></span>  
  
    4.  <span data-ttu-id="03c23-123">**XML ファイルの**ダイアログ ボックスに「 **C:\HowTos\Itineraries\ChoiceRouter**で、**ファイル名**ボックスをクリック**保存**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-123">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\ChoiceRouter** in the **File name** box, and then click **Save**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="03c23-124">この手順では、旅行プランを XML としてローカル ファイルの場所にエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="03c23-124">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="03c23-125">行程データベースの代わりにスケジュールをローカル ファイルの場所にエクスポートして、ESB テスト用クライアント アプリケーションを使用して、旅行プランをテストできます。</span><span class="sxs-lookup"><span data-stu-id="03c23-125">By exporting an itinerary to a local file location, instead of to the itinerary database, you can test the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="03c23-126">この操作方法に関するトピックの後半には、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="03c23-126">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="03c23-127">旅行プランの構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="03c23-127">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="03c23-128">ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。</span><span class="sxs-lookup"><span data-stu-id="03c23-128">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="03c23-129">OnRamp1 [プロパティ] ウィンドウでは、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="03c23-129">In the OnRamp1 Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="03c23-130">をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-130">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="03c23-131">**エクステンダー**ドロップダウン リストでは、をクリックして**ランプで Extender**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-131">In the **Extender** drop-down list, click **On-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="03c23-132">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-132">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="03c23-133">**受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-133">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="03c23-134">ツールボックスからドラッグ、**行程ブローカー サービス**の右側に配置し、デザイナー画面に要素をモデル化し、**入口**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="03c23-134">From the Toolbox, drag an **Itinerary Broker Service** model element to the designer surface, and then place it to the right side of the **On-Ramp** model element.</span></span> <span data-ttu-id="03c23-135">**ItineraryBrokerService1**、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="03c23-135">In the **ItineraryBrokerService1**, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="03c23-136">をクリックして、**名前**プロパティ、および入力**RouteBrokerService**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-136">Click the **Name** property, and then type **RouteBrokerService**.</span></span>  
  
    2.  <span data-ttu-id="03c23-137">**エクステンダー**ドロップダウン リストでは、をクリックして**メッセージング ブローカー エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-137">In the **Extender** drop-down list, click **Messaging Broker Extender**.</span></span>  
  
    3.  <span data-ttu-id="03c23-138">**コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、 をクリックし、**受信ハンドラー**。</span><span class="sxs-lookup"><span data-stu-id="03c23-138">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="03c23-139">**サービス名**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB.Itinerary.Services.Broker.MessagingBroker**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-139">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Itinerary.Services.Broker.MessagingBroker**.</span></span>  
  
3.  <span data-ttu-id="03c23-140">右クリックし、**フィルター**コレクション、およびクリック**新しいフィルターの追加**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-140">Right-click the **Filter** collection, and then click **Add new Filter**.</span></span> <span data-ttu-id="03c23-141">**Filter1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="03c23-141">In the **Filter1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="03c23-142">をクリックして、**名前**プロパティ、および入力**ASMXFilter**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-142">Click the **Name** property, and then type **ASMXFilter**.</span></span>  
  
    2.  <span data-ttu-id="03c23-143">をクリックして、**フィルター**実装のドロップダウン リスト、およびクリック**XPath フィルター**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-143">Click the **Filter** Implementation drop-down list, and then click **XPath Filter**.</span></span>  
  
    3.  <span data-ttu-id="03c23-144">をクリックして、**式**プロパティ、および入力**数 (/ContextProperties/プロパティ [@name= 'InboundTransportLocation'] [が含まれています (.、'ProcessItinerary.asmx')]) > 0**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-144">Click the **Expression** property, and then type **count(/ContextProperties/Property[@name='InboundTransportLocation'][contains(., 'ProcessItinerary.asmx')]) > 0**.</span></span>  
  
4.  <span data-ttu-id="03c23-145">右クリックし、**フィルター**コレクション、およびクリック**新しいフィルターの追加**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-145">Right-click the **Filter** collection, and then click **Add new Filter**.</span></span> <span data-ttu-id="03c23-146">**Filter1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="03c23-146">In the **Filter1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="03c23-147">をクリックして、**名前**プロパティ、および入力**WCFFilter**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-147">Click the **Name** property, and then type **WCFFilter**.</span></span>  
  
    2.  <span data-ttu-id="03c23-148">をクリックして、**フィルターの実装**ドロップダウン リスト、およびクリック**XPath フィルター**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-148">Click the **Filter Implementation** drop-down list, and click **XPath Filter**.</span></span>  
  
    3.  <span data-ttu-id="03c23-149">をクリックして、**式**プロパティ、および入力**数 (/ContextProperties/プロパティ [@name= 'InboundTransportLocation'] [が含まれています (.、' ESB します。ItineraryServices.WCF')]) > 0**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-149">Click the **Expression** property, and then type **count(/ContextProperties/Property[@name='InboundTransportLocation'][contains(., 'ESB.ItineraryServices.WCF')]) > 0**.</span></span>  
  
5.  <span data-ttu-id="03c23-150">右クリックし、**リゾルバー**のコレクション、 **RouteBrokerService**モデル要素をクリックして**新しいリゾルバーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-150">Right-click the **Resolver** collection of the **RouteBrokerService** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="03c23-151">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="03c23-151">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="03c23-152">をクリックして、**名前**プロパティ、および入力**ResolverBrokerRoute**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-152">Click the **Name** property, and then type **ResolverBrokerRoute**.</span></span>  
  
    2.  <span data-ttu-id="03c23-153">**リゾルバーの実装**ドロップダウン リストでは、をクリックして**MessageContext 競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-153">In the **Resolver Implementation** drop-down list, click **MessageContext Resolver Extension**.</span></span>  
  
6.  <span data-ttu-id="03c23-154">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-154">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="03c23-155">接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **RouteBrokerService**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="03c23-155">Drag a connection from the **ReceiveNAOrder** model element to the **RouteBrokerService** model element.</span></span>  
  
7.  <span data-ttu-id="03c23-156">ツールボックスからドラッグして、**行程サービス**下に配置し、デザイン画面に要素をモデル化し、 **RouteBrokerService**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="03c23-156">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it under the **RouteBrokerService** model element.</span></span> <span data-ttu-id="03c23-157">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="03c23-157">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="03c23-158">をクリックして、**名前**プロパティ、および入力**RouteToFileFromASMX**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-158">Click the **Name** property, and then type **RouteToFileFromASMX**.</span></span>  
  
    2.  <span data-ttu-id="03c23-159">**行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**エクステンダーのメッセージング**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-159">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="03c23-160">このプロパティは、プロセスが行われる (メッセージング) パイプラインで定義します。</span><span class="sxs-lookup"><span data-stu-id="03c23-160">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="03c23-161">または、プロセスはオーケストレーション内の場所を受け取らない場合は設定、**行程サービス エクステンダー**プロパティを**オーケストレーション エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-161">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="03c23-162">**コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、 をクリックし、**受信ハンドラー**。</span><span class="sxs-lookup"><span data-stu-id="03c23-162">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="03c23-163">**サービス名**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB.Services.Routing**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-163">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
8.  <span data-ttu-id="03c23-164">右クリックし、**リゾルバー**のコレクション、 **RouteToFileFromASMX**モデル要素をクリックして**新しいリゾルバーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-164">Right-click the **Resolver** collection of the **RouteToFileFromASMX** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="03c23-165">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="03c23-165">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="03c23-166">をクリックして、**名前**プロパティ、および入力**ResolverFromAsmx**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-166">Click the **Name** property, and then type **ResolverFromAsmx**.</span></span>  
  
    2.  <span data-ttu-id="03c23-167">**リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-167">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="03c23-168">**トランスポート名**ドロップダウン リストでは、をクリックして**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-168">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="03c23-169">をクリックして、**トランスポート場所**プロパティ、および入力**c:\howtos\out\asmx%MessageId%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-169">Click the **Transport Location** property, and then type **c:\howtos\out\asmx%MessageId%.xml**.</span></span>  
  
9. <span data-ttu-id="03c23-170">ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **RouteToFileFromASMX**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="03c23-170">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteToFileFromASMX** model element.</span></span> <span data-ttu-id="03c23-171">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="03c23-171">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="03c23-172">をクリックして、**名前**プロパティ、および入力**SendASMXOrder**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-172">Click the **Name** property, and then type **SendASMXOrder**.</span></span>  
  
    2.  <span data-ttu-id="03c23-173">**エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-173">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="03c23-174">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-174">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="03c23-175">**送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-175">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
10. <span data-ttu-id="03c23-176">ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **RouteToFileFromASMX**モデル要素と**SendASMXOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="03c23-176">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteToFileFromASMX** model element and the **SendASMXOrder** model element.</span></span> <span data-ttu-id="03c23-177">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="03c23-177">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="03c23-178">をクリックして、**名前**プロパティ、および入力**SendPortFilterASMX**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-178">Click the **Name** property, and then type **SendPortFilterASMX**.</span></span>  
  
    2.  <span data-ttu-id="03c23-179">**行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ エクステンダー**。</span><span class="sxs-lookup"><span data-stu-id="03c23-179">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="03c23-180">**傾斜オフ**ドロップダウン リストで、展開**SendASMXOrder**、順にクリックします**送信ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-180">In the **Off-Ramp** drop-down list, expand **SendASMXOrder**, and then click **Send Handlers**.</span></span>  
  
11. <span data-ttu-id="03c23-181">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-181">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="03c23-182">接続をドラッグして、 **RouteToFileFromASMX**モデル要素に、 **SendPortFilterASMX**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="03c23-182">Drag a connection from the **RouteToFileFromASMX** model element to the **SendPortFilterASMX** model element.</span></span>  
  
12. <span data-ttu-id="03c23-183">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-183">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="03c23-184">接続をドラッグして、 **SendPortFilterASMX**モデル要素に、 **SendASMXOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="03c23-184">Drag a connection from the **SendPortFilterASMX** model element to the **SendASMXOrder** model element.</span></span>  
  
13. <span data-ttu-id="03c23-185">ツールボックスからドラッグして、**行程サービス**の右側に配置し、デザイン画面に要素をモデル化し**RouteBrokerService**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="03c23-185">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of **RouteBrokerService** model element.</span></span> <span data-ttu-id="03c23-186">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="03c23-186">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="03c23-187">をクリックして、**名前**プロパティ、および入力**RouteToFileFromWCF**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-187">Click the **Name** property, and then type **RouteToFileFromWCF**.</span></span>  
  
    2.  <span data-ttu-id="03c23-188">**行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**エクステンダーのメッセージング**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-188">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="03c23-189">このプロパティは、プロセスが行われる (メッセージング) パイプラインで定義します。</span><span class="sxs-lookup"><span data-stu-id="03c23-189">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="03c23-190">または、プロセスはオーケストレーション内の場所を受け取らない場合は設定、**行程サービス エクステンダー**プロパティを**オーケストレーション エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-190">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="03c23-191">**コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、 をクリックし、**受信ハンドラー**。</span><span class="sxs-lookup"><span data-stu-id="03c23-191">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="03c23-192">**サービス名**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB.Services.Routing**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-192">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
14. <span data-ttu-id="03c23-193">右クリックし、**リゾルバー**のコレクション、 **RouteToFileFromWCF**モデル要素をクリックして**新しいリゾルバーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-193">Right-click the **Resolver** collection of the **RouteToFileFromWCF** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="03c23-194">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="03c23-194">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="03c23-195">をクリックして、**名前**プロパティ、および入力**ResolverFromWCF**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-195">Click the **Name** property, and then type **ResolverFromWCF**.</span></span>  
  
    2.  <span data-ttu-id="03c23-196">**リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-196">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="03c23-197">**トランスポート名**ドロップダウン リストでは、をクリックして**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-197">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="03c23-198">をクリックして、**トランスポート場所**プロパティ、および入力**c:\howtos\out\wcf%MessageId%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-198">Click the **Transport Location** property, and then type **c:\howtos\out\wcf%MessageId%.xml**.</span></span>  
  
15. <span data-ttu-id="03c23-199">ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **RouteToFileFromWCF**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="03c23-199">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteToFileFromWCF** model element.</span></span> <span data-ttu-id="03c23-200">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="03c23-200">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="03c23-201">をクリックして、**名前**プロパティ、および入力**SendWCFOrder**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-201">Click the **Name** property, and then type **SendWCFOrder**.</span></span>  
  
    2.  <span data-ttu-id="03c23-202">**エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-202">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="03c23-203">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-203">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="03c23-204">**送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-204">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
16. <span data-ttu-id="03c23-205">ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **RouteToFileFromWCF**モデル要素と**SendWCFOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="03c23-205">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteToFileFromWCF** model element and the **SendWCFOrder** model element.</span></span> <span data-ttu-id="03c23-206">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="03c23-206">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="03c23-207">をクリックして、**名前**プロパティ、および入力**SendPortFilterWCF**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-207">Click the **Name** property, and then type **SendPortFilterWCF**.</span></span>  
  
    2.  <span data-ttu-id="03c23-208">**行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ エクステンダー**。</span><span class="sxs-lookup"><span data-stu-id="03c23-208">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="03c23-209">**傾斜オフ**ドロップダウン リストで、展開**SendWCFOrder**、順にクリックします**送信ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-209">In the **Off-Ramp** drop-down list, expand **SendWCFOrder**, and then click **Send Handlers**.</span></span>  
  
17. <span data-ttu-id="03c23-210">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-210">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="03c23-211">接続をドラッグして、 **RouteToFileFromWCF**モデル要素に、 **SendPortFilterWCF**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="03c23-211">Drag a connection from the **RouteToFileFromWCF** model element to the **SendPortFilterWCF** model element.</span></span>  
  
18. <span data-ttu-id="03c23-212">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-212">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="03c23-213">接続をドラッグして、 **SendPortFilterWCF**モデル要素に、 **SendWCFOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="03c23-213">Drag a connection from the **SendPortFilterWCF** model element to the **SendWCFOrder** model element.</span></span>  
  
19. <span data-ttu-id="03c23-214">ツールボックスからドラッグして、**行程 Outport**モデル要素の右境界線を**RouteBrokerService**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-214">From the Toolbox, drag an **Itinerary Outport** model element to right border of **RouteBrokerService**.</span></span> <span data-ttu-id="03c23-215">**ItineraryBrokerOutPort1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="03c23-215">In the **ItineraryBrokerOutPort1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="03c23-216">をクリックして、**名前**プロパティ、および入力**WCF ポート**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-216">Click the **Name** property, and then type **WCF Port**.</span></span>  
  
    2.  <span data-ttu-id="03c23-217">**フィルター**ドロップダウン リストでは、をクリックして**WCFFilter**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-217">In the **Filter** drop-down list, click **WCFFilter**.</span></span>  
  
    3.  <span data-ttu-id="03c23-218">**リゾルバー**ドロップダウン リストでは、をクリックして**ResolverBrokerRoute**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-218">In the **Resolver** drop-down list, click **ResolverBrokerRoute**.</span></span>  
  
20. <span data-ttu-id="03c23-219">ツールボックスからドラッグして、**行程 Outport**モデル要素の下の境界線に**RouteBrokerService**。</span><span class="sxs-lookup"><span data-stu-id="03c23-219">From the Toolbox, drag an **Itinerary Outport** model element to the bottom border of **RouteBrokerService**.</span></span> <span data-ttu-id="03c23-220">**ItineraryBrokerOutPort1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="03c23-220">In the **ItineraryBrokerOutPort1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="03c23-221">をクリックして、**名前**プロパティ、および入力**ASMX ポート**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-221">Click the **Name** property, and then type **ASMX Port**.</span></span>  
  
    2.  <span data-ttu-id="03c23-222">**フィルター**ドロップダウン リストでは、をクリックして**ASMXFilter**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-222">In the **Filter** drop-down list, click **ASMXFilter**.</span></span>  
  
    3.  <span data-ttu-id="03c23-223">**リゾルバー**ドロップダウン リストでは、をクリックして**ResolverBrokerRoute**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-223">In the **Resolver** drop-down list, click **ResolverBrokerRoute**.</span></span>  
  
21. <span data-ttu-id="03c23-224">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-224">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="03c23-225">接続をドラッグして、 **WCF ポート**モデル要素に、 **RouteToFileFromWCF**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="03c23-225">Drag a connection from the **WCF Port** model element to the **RouteToFileFromWCF** model element.</span></span>  
  
22. <span data-ttu-id="03c23-226">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-226">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="03c23-227">接続をドラッグして、 **ASMX ポート**モデル要素に、 **RouteToFileFromASMX**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="03c23-227">Drag a connection from the **ASMX Port** model element to the **RouteToFileFromASMX** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="03c23-228">旅行プランのテスト クライアントで使用するモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="03c23-228">To export the model for use with the Itinerary Test Client</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03c23-229">旅行プランを 2 回エクスポートする必要があります。 ブローカーを介してルーティングをテストするデータベースに XML に 1 回、もう 1 つにします。</span><span class="sxs-lookup"><span data-stu-id="03c23-229">You will need to export the itinerary twice: one time in XML and one time to the database to test the routing through the broker.</span></span>  
  
1.  <span data-ttu-id="03c23-230">Visual Studio でのデザイン画面を右クリックし、 **ChoiceRouter**旅行プランをクリックして**モデルのエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-230">In Visual Studio, right-click the design surface of the **ChoiceRouter** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="03c23-231">旅行プランの XML バージョンは、Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="03c23-231">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="03c23-232">Windows エクスプ ローラーでは、C:\HowTos\Itineraries を参照して、旅行プラン XML (ChoiceRouter.xml) の作成に注意してください。</span><span class="sxs-lookup"><span data-stu-id="03c23-232">In Windows Explorer, browse to C:\HowTos\Itineraries, and then notice the creation of your itinerary XML (ChoiceRouter.xml).</span></span>  
  
3.  <span data-ttu-id="03c23-233">Visual Studio でのデザイン画面を右クリックし、 **ChoiceRouter**旅行プランをクリックして**モデルのエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-233">In Visual Studio, right-click the design surface of the **ChoiceRouter** itinerary, and then click **Export Model**.</span></span>  
  
4.  <span data-ttu-id="03c23-234">[プロパティ] ウィンドウで次のようにクリックします。**データベース行程エクスポーター**で、**モデル エクスポーター**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="03c23-234">In the Properties window, click **Database Itinerary Exporter** in the **Model Exporter** drop-down list.</span></span>  
  
5.  <span data-ttu-id="03c23-235">[プロパティ] ウィンドウで次のように設定します。、**行程データベース**行程データベースを指す接続文字列のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="03c23-235">In the Properties window, set the **Itinerary Database** property connection string to point to the itinerary database.</span></span>  
  
6.  <span data-ttu-id="03c23-236">**行程状態**プロパティのドロップダウン リストを**配置済み**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-236">In the **Itinerary Status** property drop-down list select **Deployed**.</span></span>  
  
7.  <span data-ttu-id="03c23-237">Visual Studio でのデザイン画面を右クリックし、 **ChoiceRouter**旅行プランをクリックして**モデルのエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="03c23-237">In Visual Studio, right-click the design surface of the **ChoiceRouter** itinerary, and then click **Export Model**.</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="03c23-238">旅行プランをテストするには</span><span class="sxs-lookup"><span data-stu-id="03c23-238">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="03c23-239">中に作成されたショートカットを使用してスケジュールのテスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB します。Itinerary.Test.exe - ショートカット)。</span><span class="sxs-lookup"><span data-stu-id="03c23-239">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="03c23-240">行程テスト クライアントでオフ、 **WCF サービスを使用して**チェック ボックスをオンにし**ロード行程**。</span><span class="sxs-lookup"><span data-stu-id="03c23-240">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="03c23-241">**行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="03c23-241">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="03c23-242">選択**ChoiceRouter.xml**、順にクリックします**オープン**旅行プランを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="03c23-242">Select **ChoiceRouter.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="03c23-243">クリックして**OK** 「行程正しく読み込まれました」メッセージを閉じます。</span><span class="sxs-lookup"><span data-stu-id="03c23-243">Click **OK** to close the "Itinerary Loaded Successfully" message.</span></span>  
  
5.  <span data-ttu-id="03c23-244">旅行プランのテスト クライアントで、横にある省略記号ボタン (…) をクリックします。、**ロード メッセージ**ボックス。</span><span class="sxs-lookup"><span data-stu-id="03c23-244">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="03c23-245">**を読み込む XML ドキュメントの選択** ダイアログ ボックスで、C:\Patterns\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="03c23-245">In the **Select XML Document to load** dialog box, browse to C:\Patterns\HowTos.</span></span> <span data-ttu-id="03c23-246">NAOrderDoc.xml を選択し、クリックして**オープン**テスト メッセージを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="03c23-246">Select NAOrderDoc.xml, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="03c23-247">をクリックして、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="03c23-247">Click the **Submit Request** button.</span></span> <span data-ttu-id="03c23-248">テストが完了したら、クリックして**OK**表示される確認メッセージを閉じます。</span><span class="sxs-lookup"><span data-stu-id="03c23-248">When the test completes, click **OK** to close the confirmation message that appears.</span></span>  
  
8.  <span data-ttu-id="03c23-249">Windows エクスプ ローラーでは、C:\HowTos\Out を参照します。ASMX%MessageID%.xml メッセージがこのディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="03c23-249">In Windows Explorer, browse to C:\HowTos\Out. Verify that the ASMX%MessageID%.xml messages have been written to this directory.</span></span>  
  
9. <span data-ttu-id="03c23-250">旅行プランのテスト クライアント をクリックして**WCF サービスを使用して**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="03c23-250">Click the Itinerary Test client **Use WCF Service** check box.</span></span> <span data-ttu-id="03c23-251">**旅行プラン名**ボックスに「 **ChoiceRouter**、順にクリックします、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="03c23-251">In the **Itinerary Name** box, type **ChoiceRouter**, and then click the **Submit Request** button.</span></span> <span data-ttu-id="03c23-252">テストが完了したら、クリックして**OK**確認メッセージを閉じます。</span><span class="sxs-lookup"><span data-stu-id="03c23-252">When the test completes, click **OK** to close the confirmation message.</span></span>  
  
10. <span data-ttu-id="03c23-253">Windows エクスプ ローラーでは、C:\HowTos\Out を参照します。WCF%MessageID%.xml メッセージがこのディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="03c23-253">In Windows Explorer, browse to C:\HowTos\Out. Verify that the WCF%MessageID%.xml messages have been written to this directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="03c23-254">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="03c23-254">Additional Resources</span></span>  
 <span data-ttu-id="03c23-255">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03c23-255">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="03c23-256">方法: ビジネス ルール ポリシーを使用するスケジュールを選択します。</span><span class="sxs-lookup"><span data-stu-id="03c23-256">How to: Select an Itinerary Using a Business Rules Policy</span></span>](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [<span data-ttu-id="03c23-257">方法: ビジネス ルール ポリシーを使用してメッセージのコンテキストに基づいてメッセージを動的にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="03c23-257">How to: Dynamically Route a Message Based on Message Context Using a Business Rules Policy</span></span>](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
-   [<span data-ttu-id="03c23-258">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="03c23-258">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="03c23-259">メッセージ ルーティング パターン</span><span class="sxs-lookup"><span data-stu-id="03c23-259">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)