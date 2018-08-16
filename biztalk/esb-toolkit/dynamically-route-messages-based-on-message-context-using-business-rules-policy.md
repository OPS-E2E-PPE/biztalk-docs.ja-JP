---
title: '方法: 動的にビジネス ルール ポリシーを使用して、メッセージ コンテキストに基づくメッセージのルーティング |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d3b68de-6b24-46fe-ae0d-91afb630bc19
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7406b0daed4374241bb92fdcb4afcdcd5acd77b9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973891"
---
# <a name="how-to-dynamically-route-a-message-based-on-message-context-using-a-business-rules-policy"></a><span data-ttu-id="53b86-102">方法: ビジネス ルール ポリシーを使用してメッセージのコンテキストに基づいてメッセージを動的にルーティング</span><span class="sxs-lookup"><span data-stu-id="53b86-102">How to: Dynamically Route a Message Based on Message Context Using a Business Rules Policy</span></span>
## <a name="goal"></a><span data-ttu-id="53b86-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="53b86-103">Goal</span></span>  
 <span data-ttu-id="53b86-104">このセクションでは、BizTalk Server ビジネス ルール エンジン (BRE) ポリシーを使用して、メッセージ コンテキスト プロパティに基づく、メッセージのエンドポイントを決定し、BizTalk Server ファイル アダプターを使用してメッセージをルーティングし、旅行プランを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="53b86-104">This section demonstrates how to create an itinerary that determines message endpoints, based on message context properties, using a BizTalk Server Business Rules Engine (BRE) policy, and then routes the message using the BizTalk Server FILE adapter.</span></span>  
  
 <span data-ttu-id="53b86-105">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="53b86-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="53b86-106">メッセージの種類を評価するビジネス ルール ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="53b86-106">Create a business rules policy to evaluate message type.</span></span>  
  
-   <span data-ttu-id="53b86-107">ビジネス ルール ポリシーを使用して動的にルーティングするスケジュールの回覧先を作成します。</span><span class="sxs-lookup"><span data-stu-id="53b86-107">Create an itinerary routing slip to dynamically route using a business rules policy.</span></span>  
  
-   <span data-ttu-id="53b86-108">旅行プランのテスト用クライアントのサンプル アプリケーションを使用して、旅行プランをテストします。</span><span class="sxs-lookup"><span data-stu-id="53b86-108">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="53b86-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="53b86-109">Prerequisites</span></span>  
 <span data-ttu-id="53b86-110">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。</span><span class="sxs-lookup"><span data-stu-id="53b86-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="53b86-111">手順</span><span class="sxs-lookup"><span data-stu-id="53b86-111">Steps</span></span>  
 <span data-ttu-id="53b86-112">**メッセージ コンテキスト プロパティを使用してメッセージをルーティングする BRE ポリシーを作成するには**</span><span class="sxs-lookup"><span data-stu-id="53b86-112">**To create a BRE policy to route a message using message context properties**</span></span>  
  
1. <span data-ttu-id="53b86-113">クリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリックします**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-113">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **Business Rule Composer**.</span></span>  
  
2. <span data-ttu-id="53b86-114">ポリシー エクスプ ローラーで右クリック**ポリシー**、 をクリックし、**新しいポリシーの追加**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-114">In Policy Explorer, right-click **Policies**, and then click **Add New Policy**.</span></span> <span data-ttu-id="53b86-115">ポリシーの名前**RouteBasedOnMessageType**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-115">Name the policy **RouteBasedOnMessageType**.</span></span>  
  
   <span data-ttu-id="53b86-116">**北米地域の注文のルーティング規則を追加するには**</span><span class="sxs-lookup"><span data-stu-id="53b86-116">**To add a routing rule for North American orders**</span></span>  
  
3. <span data-ttu-id="53b86-117">**RouteBasedOnMessageType**ポリシーを右クリックして**バージョン 1.0 (未保存)**、順にクリックします**新しいルールの追加**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-117">In the **RouteBasedOnMessageType** policy, right-click **Version 1.0 (not saved)**, and then click **Add New Rule**.</span></span> <span data-ttu-id="53b86-118">ルールの名前として**SetNAOrderEndpoint**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-118">Name the rule **SetNAOrderEndpoint**.</span></span>  
  
4. <span data-ttu-id="53b86-119">ルール ウィンドウで、右クリック**条件**、 をポイント**述語**、 をクリックし、**等しい**。</span><span class="sxs-lookup"><span data-stu-id="53b86-119">In the Rule window, right-click **Conditions**, point to **Predicates**, and then click **Equal**.</span></span>  
  
5. <span data-ttu-id="53b86-120">ファクト エクスプ ローラーで、 **ESB します。Contextinfo です**ボキャブラリ、展開**バージョン 1.0**、し、ドラッグ、**コンテキストのメッセージ型**ファクト、 **[引数 1]** ノードの下**条件**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-120">In Facts Explorer, expand the **ESB.ContextInfo** vocabulary, expand **Version 1.0**, and then drag the **Context Message Type** fact to the **argument1** node under **Conditions**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="53b86-121">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]ルールを作成するために使用できるいくつかのボキャブラリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="53b86-121">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes several vocabularies that can be used for creating rules.</span></span> <span data-ttu-id="53b86-122">これらのいくつかは、置き換えをまたは独自のボキャブラリで補強します。</span><span class="sxs-lookup"><span data-stu-id="53b86-122">Some of these should be replaced or augmented with your own vocabularies.</span></span> <span data-ttu-id="53b86-123">たとえば、 **DynamicRunTimeMaptypes**ポリシーで提供する地図の定義には、 **GlobalBank**サンプル。</span><span class="sxs-lookup"><span data-stu-id="53b86-123">For example, the **DynamicRunTimeMaptypes** policy has definitions for the maps provided in the **GlobalBank** samples.</span></span>  
  
6. <span data-ttu-id="53b86-124">をクリックして、 **[引数 2]** ノード、および入力し、 **http://globalbank.esb.dynamicresolution.com/northamericanservices/#OrderDoc**</span><span class="sxs-lookup"><span data-stu-id="53b86-124">Click the **argument2** node, and then type **http://globalbank.esb.dynamicresolution.com/northamericanservices/#OrderDoc**</span></span>  
  
7. <span data-ttu-id="53b86-125">ファクト エクスプ ローラーで、 **ESB します。EndPointInfo**ボキャブラリ、展開**バージョン 1.0**、し、ドラッグ、**終点の送信トランスポート場所の設定**の定義を**アクション**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-125">In Facts Explorer, expand the **ESB.EndPointInfo** vocabulary, expand **Version 1.0**, and then drag the **Set End Point Outbound Transport Location** definition to **Actions**.</span></span>  
  
8. <span data-ttu-id="53b86-126">クリックして**\<空の文字列\>**、し、入力**C:\HowTos\Out\NorthAmerica%MessageID%.xml**</span><span class="sxs-lookup"><span data-stu-id="53b86-126">Click **\<empty string\>**, and then type **C:\HowTos\Out\NorthAmerica%MessageID%.xml**</span></span>  
  
9. <span data-ttu-id="53b86-127">ファクト エクスプ ローラーからドラッグして、**設定の終了点送信トランスポートの種類**の定義を**アクション**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-127">From Facts Explorer, drag the **Set End Point Outbound Transport Type** definition to **Actions**.</span></span>  
  
10. <span data-ttu-id="53b86-128">ファクト エクスプ ローラーで、 **ESB します。TansportTypes**ボキャブラリ、展開**バージョン 1.0**、し、ドラッグ、**アダプター プロバイダー**の定義を**\<空の文字列\>**.</span><span class="sxs-lookup"><span data-stu-id="53b86-128">In Facts Explorer, expand the **ESB.TansportTypes** vocabulary, expand **Version 1.0**, and then drag the **Adaptor Providers** definition to **\<empty string\>**.</span></span>  
  
11. <span data-ttu-id="53b86-129">[操作] ウィンドウで、展開、**アダプター プロバイダー**ドロップダウン リスト、およびクリック**ファイル**。</span><span class="sxs-lookup"><span data-stu-id="53b86-129">In the Actions pane, expand the **Adaptor Providers** drop-down list, and then click **FILE**.</span></span>  
  
    <span data-ttu-id="53b86-130">**発行して、ポリシーをデプロイするには**</span><span class="sxs-lookup"><span data-stu-id="53b86-130">**To publish and deploy the policy**</span></span>  
  
12. <span data-ttu-id="53b86-131">ポリシー エクスプ ローラーで [、 **RouteBasedOnMessageType**ポリシーを右クリック**バージョン 1.0 (未保存)**、] をクリックし、**発行**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-131">In Policy Explorer, under the **RouteBasedOnMessageType** policy, right click **Version 1.0 (not saved)**, and then click **Publish**.</span></span>  
  
13. <span data-ttu-id="53b86-132">ポリシー エクスプ ローラーで [、 **RouteBasedOnMessageType**ポリシーを右クリック**バージョン 1.0 - 公開済み**、] をクリックし、**デプロイ**。</span><span class="sxs-lookup"><span data-stu-id="53b86-132">In Policy Explorer, under the **RouteBasedOnMessageType** policy, right click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  
  
    <span data-ttu-id="53b86-133">**ESB スケジュール オンランプ ドメイン固有言語 (DSL) モデルを作成するには**</span><span class="sxs-lookup"><span data-stu-id="53b86-133">**To create an ESB itinerary domain-specific language (DSL) model**</span></span>  
  
14. <span data-ttu-id="53b86-134">Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="53b86-134">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
15. <span data-ttu-id="53b86-135">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントして、**追加**、順にクリックします**新しい行程**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-135">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
16. <span data-ttu-id="53b86-136">**名前**ボックスに「 **MessageType**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-136">In the **Name** box, type **MessageType**, and then click **Add**.</span></span>  
  
    <span data-ttu-id="53b86-137">**旅行プランのプロパティを構成するには**</span><span class="sxs-lookup"><span data-stu-id="53b86-137">**To configure the properties of the itinerary**</span></span>  
  
17. <span data-ttu-id="53b86-138">Visual Studio でのデザイン画面をクリックします。 **MessageType.itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-138">In Visual Studio, click the design surface of **MessageType.itinerary**.</span></span> <span data-ttu-id="53b86-139">**MessageType**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="53b86-139">In the **MessageType** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="53b86-140">**モデル エクスポーター**ドロップダウン リストでは、をクリックして**XML 行程エクスポーター**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-140">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="53b86-141">**エクステンダー設定**セクションで、次に、**旅行プラン XML ファイル**プロパティ、省略記号ボタン (…) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53b86-141">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="53b86-142">**[XML ファイルの**] ダイアログ ボックスで、**ファイル名**ボックスに「 **C:\HowTos\Itineraries\MessageType**、順にクリックします**保存**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-142">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\MessageType**, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="53b86-143">この手順では、旅行プランを XML としてローカル ファイルの場所にエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="53b86-143">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="53b86-144">行程データベースへの代わりにスケジュールをローカル ファイルの場所へのエクスポートは、ESB のテスト用クライアント アプリケーションを使用してスケジュールのテストを使用できます。</span><span class="sxs-lookup"><span data-stu-id="53b86-144">Exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="53b86-145">この操作方法に関するトピックの後半には、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="53b86-145">You will complete this process later in this How-to topic.</span></span>  
  
    <span data-ttu-id="53b86-146">**旅行プランの構造を定義するには**</span><span class="sxs-lookup"><span data-stu-id="53b86-146">**To define the structure of the itinerary**</span></span>  
  
18. <span data-ttu-id="53b86-147">ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。</span><span class="sxs-lookup"><span data-stu-id="53b86-147">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="53b86-148">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="53b86-148">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="53b86-149">をクリックして、**名前**プロパティ、および入力**ReceiveOrders**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-149">Click the **Name** property, and then type **ReceiveOrders**.</span></span>  
  
    2.  <span data-ttu-id="53b86-150">**エクステンダー**ドロップダウン リストでは、をクリックして**入口 ESB エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-150">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="53b86-151">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-151">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="53b86-152">**受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-152">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
19. <span data-ttu-id="53b86-153">ツールボックスからドラッグ、**行程サービス**の右側に配置し、デザイン画面に要素をモデル化し、**入口**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="53b86-153">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="53b86-154">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="53b86-154">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="53b86-155">をクリックして、**名前**プロパティ、および入力**BreRoute**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-155">Click the **Name** property, and then type **BreRoute**.</span></span>  
  
    2.  <span data-ttu-id="53b86-156">**行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**エクステンダーのメッセージング**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-156">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="53b86-157">このプロパティは、プロセスが行われる (メッセージング) パイプラインで定義します。</span><span class="sxs-lookup"><span data-stu-id="53b86-157">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="53b86-158">または、プロセスはオーケストレーション内の場所を受け取らない場合は設定、**行程サービス エクステンダー**プロパティを**オーケストレーション エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-158">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="53b86-159">**コンテナー**ドロップダウン リストで、展開**ReceiveOrders**、 をクリックし、**受信ハンドラー**。</span><span class="sxs-lookup"><span data-stu-id="53b86-159">In the **Container** drop-down list, expand **ReceiveOrders**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="53b86-160">**サービス名**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB.Services.Routing**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-160">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
20. <span data-ttu-id="53b86-161">右クリックし、**リゾルバー**のコレクション、 **BreRoute**モデル要素をクリックして**新しいリゾルバーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-161">Right-click the **Resolver** collection of the **BreRoute** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="53b86-162">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="53b86-162">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="53b86-163">をクリックして、**名前**プロパティ、および入力**ByMessageType**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-163">Click the **Name** property, and then type **ByMessageType**.</span></span>  
  
    2.  <span data-ttu-id="53b86-164">**リゾルバーの実装**ドロップダウン リストでは、をクリックして**Bre 競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-164">In the **Resolver Implementation** drop-down list, click **Bre Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="53b86-165">**ポリシー**ドロップダウン リストでは、をクリックして**RouteBasedOnMessageType v 1.0**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-165">In the **Policy** drop-down list, click **RouteBasedOnMessageType v 1.0**.</span></span>  
  
21. <span data-ttu-id="53b86-166">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-166">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="53b86-167">接続をドラッグして、 **ReceiveOrders**モデル要素に、 **BreRoute**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="53b86-167">Drag a connection from the **ReceiveOrders** model element to the **BreRoute** model element.</span></span>  
  
22. <span data-ttu-id="53b86-168">ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **BreRoute**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="53b86-168">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **BreRoute** model element.</span></span> <span data-ttu-id="53b86-169">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="53b86-169">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="53b86-170">をクリックして、**名前**プロパティ、および入力**SendBasedOnType**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-170">Click the **Name** property, and then type **SendBasedOnType**.</span></span>  
  
    2.  <span data-ttu-id="53b86-171">**エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-171">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="53b86-172">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-172">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="53b86-173">**送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-173">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
23. <span data-ttu-id="53b86-174">ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **BreRoute**モデル要素と**SendBasedOnType**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="53b86-174">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **BreRoute** model element and the **SendBasedOnType** model element.</span></span> <span data-ttu-id="53b86-175">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="53b86-175">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="53b86-176">をクリックして、**名前**プロパティ、および入力**SendPortFilter**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-176">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="53b86-177">**行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ エクステンダー**。</span><span class="sxs-lookup"><span data-stu-id="53b86-177">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="53b86-178">**傾斜オフ**ドロップダウン リストで、展開**SendBasedOnType**、順にクリックします**送信ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-178">In the **Off-Ramp** drop-down list, expand **SendBasedOnType**, and then click **Send Handlers**.</span></span>  
  
24. <span data-ttu-id="53b86-179">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-179">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="53b86-180">接続をドラッグして、 **BreRoute**モデル要素に、 **SendPortFilter**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="53b86-180">Drag a connection from the **BreRoute** model element to the **SendPortFilter** model element.</span></span>  
  
25. <span data-ttu-id="53b86-181">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-181">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="53b86-182">接続をドラッグして、 **SendPortFilter**モデル要素に、 **SendBasedOnType**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="53b86-182">Drag a connection from the **SendPortFilter** model element to the **SendBasedOnType** model element.</span></span>  
  
    <span data-ttu-id="53b86-183">**旅行プランのテスト クライアントで使用するモデルをエクスポートするには**</span><span class="sxs-lookup"><span data-stu-id="53b86-183">**To export the model for use with the Itinerary Test Client**</span></span>  
  
26. <span data-ttu-id="53b86-184">Visual Studio でのデザイン画面を右クリックし、 **MessageType**旅行プランをクリックして**モデルのエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="53b86-184">In Visual Studio, right-click the design surface of the **MessageType** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="53b86-185">旅行プランの XML バージョンは、Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="53b86-185">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
27. <span data-ttu-id="53b86-186">すべてのプロジェクト成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="53b86-186">Save all project artifacts.</span></span>  
  
28. <span data-ttu-id="53b86-187">Windows エクスプ ローラーでは、C:\HowTos\Itineraries を参照し、旅行プラン XML (MessageType.xml) の作成に注意してください。</span><span class="sxs-lookup"><span data-stu-id="53b86-187">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (MessageType.xml).</span></span>  
  
    <span data-ttu-id="53b86-188">**旅行プランをテストするには**</span><span class="sxs-lookup"><span data-stu-id="53b86-188">**To test the itinerary**</span></span>  
  
29. <span data-ttu-id="53b86-189">中に作成されたショートカットを使用してスケジュールのテスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB します。Itinerary.Test.exe - ショートカット)。</span><span class="sxs-lookup"><span data-stu-id="53b86-189">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
30. <span data-ttu-id="53b86-190">行程テスト クライアントでオフ、 **WCF サービスを使用して**チェック ボックスをオンにし**ロード行程**。</span><span class="sxs-lookup"><span data-stu-id="53b86-190">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
31. <span data-ttu-id="53b86-191">**行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="53b86-191">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="53b86-192">選択**MessageType.xml**、順にクリックします**オープン**旅行プランを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="53b86-192">Select **MessageType.xml**, and then click **Open** to load the itinerary.</span></span>  
  
32. <span data-ttu-id="53b86-193">をクリックして**OK**をオフに、**旅行プランは正常に読み込まれる**メッセージ。</span><span class="sxs-lookup"><span data-stu-id="53b86-193">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
33. <span data-ttu-id="53b86-194">旅行プランのテスト クライアントで、横にある省略記号ボタン (…) をクリックします。、**ロード メッセージ**ボックス。</span><span class="sxs-lookup"><span data-stu-id="53b86-194">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
34. <span data-ttu-id="53b86-195">**を読み込む XML ドキュメントの選択** ダイアログ ボックスで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="53b86-195">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="53b86-196">選択**NAOrderDoc.xml**、順にクリックします**オープン**テスト メッセージを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="53b86-196">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
35. <span data-ttu-id="53b86-197">をクリックして、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="53b86-197">Click the **Submit Request** button.</span></span> <span data-ttu-id="53b86-198">テストが完了したら、クリックして**OK**表示される確認メッセージを無視します。</span><span class="sxs-lookup"><span data-stu-id="53b86-198">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
36. <span data-ttu-id="53b86-199">Windows エクスプ ローラーで参照 C:\HowTos\Out\\します。</span><span class="sxs-lookup"><span data-stu-id="53b86-199">In Windows Explorer, browse to C:\HowTos\Out\\.</span></span> <span data-ttu-id="53b86-200">NorthAmerica%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="53b86-200">Verify that the NorthAmerica%MessageID%.xml message has been written to the directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="53b86-201">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="53b86-201">Additional Resources</span></span>  
 <span data-ttu-id="53b86-202">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53b86-202">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="53b86-203">方法: ビジネス ルール ポリシーを使用して、日程を選択</span><span class="sxs-lookup"><span data-stu-id="53b86-203">How to: Select an Itinerary Using a Business Rules Policy</span></span>](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [<span data-ttu-id="53b86-204">方法: メッセージを変換し、スケジュール ルーティング スリップを利用してファイルの場所に送信する</span><span class="sxs-lookup"><span data-stu-id="53b86-204">How to: Transform a Message and Route the Resulting Message to a File Location Using an Itinerary Routing Slip</span></span>](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [<span data-ttu-id="53b86-205">方法: 既知のメッセージ タイプに関するビジネス ルール ポリシーを利用し、コンテンツベースのルーティングを実装する</span><span class="sxs-lookup"><span data-stu-id="53b86-205">How to: Implement Content-Based Routing Using a Business Rules Policy for a Known Message Type</span></span>](../esb-toolkit/apply-content-based-routing-using-business-rules-policy-for-known-message-type.md)  
  
-   [<span data-ttu-id="53b86-206">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="53b86-206">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="53b86-207">メッセージ ルーティング パターン</span><span class="sxs-lookup"><span data-stu-id="53b86-207">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)  
  
-   [<span data-ttu-id="53b86-208">動的な解決とルーティングを利用する</span><span class="sxs-lookup"><span data-stu-id="53b86-208">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)