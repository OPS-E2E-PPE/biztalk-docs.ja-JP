---
title: "方法: 動的にビジネス ルール ポリシーを使用して、メッセージ コンテキストに基づいたメッセージをルーティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d3b68de-6b24-46fe-ae0d-91afb630bc19
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 717e0180ba92d49751342e00a4d0367832084135
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-dynamically-route-a-message-based-on-message-context-using-a-business-rules-policy"></a><span data-ttu-id="9c102-102">方法: 動的にビジネス ルール ポリシーを使用して、メッセージ コンテキストに基づいたメッセージをルーティング</span><span class="sxs-lookup"><span data-stu-id="9c102-102">How to: Dynamically Route a Message Based on Message Context Using a Business Rules Policy</span></span>
## <a name="goal"></a><span data-ttu-id="9c102-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="9c102-103">Goal</span></span>  
 <span data-ttu-id="9c102-104">このセクションを使用して、メッセージ コンテキスト プロパティに基づいて、メッセージのエンドポイントを決定する旅程を作成する方法を示します、[!INCLUDE[prague](../includes/prague-md.md)]ビジネス ルール エンジン (BRE) ポリシーと、ルートを使用して、メッセージ、[!INCLUDE[prague](../includes/prague-md.md)]ファイル アダプター。</span><span class="sxs-lookup"><span data-stu-id="9c102-104">This section demonstrates how to create an itinerary that determines message endpoints, based on message context properties, using a [!INCLUDE[prague](../includes/prague-md.md)] Business Rules Engine (BRE) policy, and then routes the message using the [!INCLUDE[prague](../includes/prague-md.md)] FILE adapter.</span></span>  
  
 <span data-ttu-id="9c102-105">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="9c102-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="9c102-106">メッセージ型に評価するビジネス ルール ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="9c102-106">Create a business rules policy to evaluate message type.</span></span>  
  
-   <span data-ttu-id="9c102-107">ビジネス ルール ポリシーを使用して動的にルーティングする itinerary 回覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="9c102-107">Create an itinerary routing slip to dynamically route using a business rules policy.</span></span>  
  
-   <span data-ttu-id="9c102-108">行程テスト用クライアントのサンプル アプリケーションを使用して旅程をテストします。</span><span class="sxs-lookup"><span data-stu-id="9c102-108">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9c102-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="9c102-109">Prerequisites</span></span>  
 <span data-ttu-id="9c102-110">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。</span><span class="sxs-lookup"><span data-stu-id="9c102-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="9c102-111">手順</span><span class="sxs-lookup"><span data-stu-id="9c102-111">Steps</span></span>  
 <span data-ttu-id="9c102-112">**メッセージ コンテキスト プロパティを使用してメッセージをルーティングする BRE ポリシーを作成するには**</span><span class="sxs-lookup"><span data-stu-id="9c102-112">**To create a BRE policy to route a message using message context properties**</span></span>  
  
1.  <span data-ttu-id="9c102-113">をクリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント **[!INCLUDE[prague](../includes/prague-md.md)]** 、順にクリック**ビジネス ルール作成ツール**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-113">Click **Start** on the taskbar, point to **All Programs**, point to **[!INCLUDE[prague](../includes/prague-md.md)]**, and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="9c102-114">ポリシー エクスプ ローラーで右クリック**ポリシー**、クリックして**新しいポリシーの追加**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-114">In Policy Explorer, right-click **Policies**, and then click **Add New Policy**.</span></span> <span data-ttu-id="9c102-115">ポリシーに名前**RouteBasedOnMessageType**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-115">Name the policy **RouteBasedOnMessageType**.</span></span>  
  
 <span data-ttu-id="9c102-116">**北米地域の注文のルーティング規則を追加するには**</span><span class="sxs-lookup"><span data-stu-id="9c102-116">**To add a routing rule for North American orders**</span></span>  
  
1.  <span data-ttu-id="9c102-117">**RouteBasedOnMessageType**ポリシーを右クリックして**バージョン 1.0 (未保存)**、順にクリック**新しいルールの追加**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-117">In the **RouteBasedOnMessageType** policy, right-click **Version 1.0 (not saved)**, and then click **Add New Rule**.</span></span> <span data-ttu-id="9c102-118">ルールの名前として**SetNAOrderEndpoint**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-118">Name the rule **SetNAOrderEndpoint**.</span></span>  
  
2.  <span data-ttu-id="9c102-119">ルール ウィンドウで、右クリック**条件**、 をポイント**述語**、順にクリック**等しい**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-119">In the Rule window, right-click **Conditions**, point to **Predicates**, and then click **Equal**.</span></span>  
  
3.  <span data-ttu-id="9c102-120">ファクト エクスプ ローラーで、展開、 **ESB です。ContextInfo**ボキャブラリ、展開**バージョン 1.0**、し、ドラッグ、**コンテキスト メッセージ型**にファクト、 **argument1**ノードの下**条件**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-120">In Facts Explorer, expand the **ESB.ContextInfo** vocabulary, expand **Version 1.0**, and then drag the **Context Message Type** fact to the **argument1** node under **Conditions**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c102-121">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]ルールの作成に使用できるいくつかのボキャブラリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9c102-121">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes several vocabularies that can be used for creating rules.</span></span> <span data-ttu-id="9c102-122">これらのいくつかは、交換する必要があります。 または独自のボキャブラリで補完されました。</span><span class="sxs-lookup"><span data-stu-id="9c102-122">Some of these should be replaced or augmented with your own vocabularies.</span></span> <span data-ttu-id="9c102-123">たとえば、 **DynamicRunTimeMaptypes**ポリシーに入っているマップの定義には、 **GlobalBank**サンプルです。</span><span class="sxs-lookup"><span data-stu-id="9c102-123">For example, the **DynamicRunTimeMaptypes** policy has definitions for the maps provided in the **GlobalBank** samples.</span></span>  
  
4.  <span data-ttu-id="9c102-124">クリックして、 **argument2**ノード、および入力**http://globalbank.esb.dynamicresolution.com/northamericanservices/#OrderDoc**</span><span class="sxs-lookup"><span data-stu-id="9c102-124">Click the **argument2** node, and then type **http://globalbank.esb.dynamicresolution.com/northamericanservices/#OrderDoc**</span></span>  
  
5.  <span data-ttu-id="9c102-125">ファクト エクスプ ローラーで、展開、 **ESB です。EndPointInfo**ボキャブラリ、展開**バージョン 1.0**、し、ドラッグ、**終点送信トランスポート場所の設定**の定義を**アクション**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-125">In Facts Explorer, expand the **ESB.EndPointInfo** vocabulary, expand **Version 1.0**, and then drag the **Set End Point Outbound Transport Location** definition to **Actions**.</span></span>  
  
6.  <span data-ttu-id="9c102-126">をクリックして**\<空の文字列 >**、し、入力**C:\HowTos\Out\NorthAmerica%MessageID%.xml**</span><span class="sxs-lookup"><span data-stu-id="9c102-126">Click **\<empty string>**, and then type **C:\HowTos\Out\NorthAmerica%MessageID%.xml**</span></span>  
  
7.  <span data-ttu-id="9c102-127">ファクト エクスプ ローラーからドラッグして、**設定の終了点送信トランスポートの種類**定義**アクション**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-127">From Facts Explorer, drag the **Set End Point Outbound Transport Type** definition to **Actions**.</span></span>  
  
8.  <span data-ttu-id="9c102-128">ファクト エクスプ ローラーで、展開、 **ESB です。TansportTypes**ボキャブラリ、展開**バージョン 1.0**、し、ドラッグ、**アダプター プロバイダー**定義**\<空の文字列 >**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-128">In Facts Explorer, expand the **ESB.TansportTypes** vocabulary, expand **Version 1.0**, and then drag the **Adaptor Providers** definition to **\<empty string>**.</span></span>  
  
9. <span data-ttu-id="9c102-129">[操作] ウィンドウで、展開、**アダプター プロバイダー**クリックしてドロップダウン リスト、**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-129">In the Actions pane, expand the **Adaptor Providers** drop-down list, and then click **FILE**.</span></span>  
  
 <span data-ttu-id="9c102-130">**発行して、ポリシーを展開するには**</span><span class="sxs-lookup"><span data-stu-id="9c102-130">**To publish and deploy the policy**</span></span>  
  
1.  <span data-ttu-id="9c102-131">ポリシー エクスプ ローラーで、、 **RouteBasedOnMessageType**ポリシーを右クリック**バージョン 1.0 (未保存)**、クリックして**発行**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-131">In Policy Explorer, under the **RouteBasedOnMessageType** policy, right click **Version 1.0 (not saved)**, and then click **Publish**.</span></span>  
  
2.  <span data-ttu-id="9c102-132">ポリシー エクスプ ローラーで、、 **RouteBasedOnMessageType**ポリシーを右クリック**バージョン 1.0 - 公開済み**、クリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-132">In Policy Explorer, under the **RouteBasedOnMessageType** policy, right click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  
  
 <span data-ttu-id="9c102-133">**ESB itinerary ドメイン固有言語 (DSL) モデルを作成するには**</span><span class="sxs-lookup"><span data-stu-id="9c102-133">**To create an ESB itinerary domain-specific language (DSL) model**</span></span>  
  
1.  <span data-ttu-id="9c102-134">[!INCLUDE[vs2010](../includes/vs2010-md.md)]C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="9c102-134">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="9c102-135">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-135">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="9c102-136">**名前**ボックスに、入力**MessageType**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-136">In the **Name** box, type **MessageType**, and then click **Add**.</span></span>  
  
 <span data-ttu-id="9c102-137">**旅行計画のプロパティを構成するには**</span><span class="sxs-lookup"><span data-stu-id="9c102-137">**To configure the properties of the itinerary**</span></span>  
  
1.  <span data-ttu-id="9c102-138">Visual Studio でのデザイン画面をクリックして**MessageType.itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-138">In Visual Studio, click the design surface of **MessageType.itinerary**.</span></span> <span data-ttu-id="9c102-139">**MessageType**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9c102-139">In the **MessageType** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9c102-140">**モデル エクスポーター**ドロップダウン リストをクリックして**XML 行程エクスポーター**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-140">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="9c102-141">**Extender 設定**セクションで、横に、**行程 XML ファイル**プロパティ、省略記号ボタン (...) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c102-141">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="9c102-142">**[XML ファイルの**] ダイアログ ボックスで、**ファイル名**ボックスに、入力**C:\HowTos\Itineraries\MessageType**、クリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-142">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\MessageType**, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="9c102-143">この手順では、旅行計画をローカル ファイルの場所に XML としてエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="9c102-143">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="9c102-144">ESB のテスト用クライアント アプリケーションを使用して旅行計画のテストを itinerary のデータベースへの代わりに、ローカル ファイルの場所に日程をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="9c102-144">Exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="9c102-145">このトピックの後半には、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="9c102-145">You will complete this process later in this How-to topic.</span></span>  
  
 <span data-ttu-id="9c102-146">**旅行計画の構造を定義するには**</span><span class="sxs-lookup"><span data-stu-id="9c102-146">**To define the structure of the itinerary**</span></span>  
  
1.  <span data-ttu-id="9c102-147">ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。</span><span class="sxs-lookup"><span data-stu-id="9c102-147">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="9c102-148">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9c102-148">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9c102-149">クリックして、**名前**プロパティ、および入力**ReceiveOrders**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-149">Click the **Name** property, and then type **ReceiveOrders**.</span></span>  
  
    2.  <span data-ttu-id="9c102-150">**Extender**ドロップダウン リストをクリックして**入り口 ESB Extender**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-150">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="9c102-151">**BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-151">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="9c102-152">**受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-152">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="9c102-153">ツールボックスからドラッグ、**行程サービス**デザイン画面に要素をモデル化の右側に配置し、**入り口**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="9c102-153">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="9c102-154">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9c102-154">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9c102-155">クリックして、**名前**プロパティ、および入力**BreRoute**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-155">Click the **Name** property, and then type **BreRoute**.</span></span>  
  
    2.  <span data-ttu-id="9c102-156">**行程サービス エクステンダー**ドロップダウン リストをクリックして**エクステンダーのメッセージング**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-156">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="9c102-157">このプロパティは、あるプロセスで行われます (メッセージング) パイプラインを定義します。</span><span class="sxs-lookup"><span data-stu-id="9c102-157">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="9c102-158">または、プロセスは、オーケストレーションで行われます、設定、**行程サービス エクステンダー**プロパティを**オーケストレーション Extender**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-158">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="9c102-159">**コンテナー**ドロップダウン リストで、展開**ReceiveOrders**、クリックして**受信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-159">In the **Container** drop-down list, expand **ReceiveOrders**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="9c102-160">**サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Routing**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-160">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
3.  <span data-ttu-id="9c102-161">右クリックし、**リゾルバー**のコレクション、 **BreRoute**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-161">Right-click the **Resolver** collection of the **BreRoute** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="9c102-162">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9c102-162">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9c102-163">クリックして、**名前**プロパティ、および入力**ByMessageType**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-163">Click the **Name** property, and then type **ByMessageType**.</span></span>  
  
    2.  <span data-ttu-id="9c102-164">**リゾルバーの実装**ドロップダウン リストをクリックして**Bre 競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="9c102-164">In the **Resolver Implementation** drop-down list, click **Bre Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="9c102-165">**ポリシー**ドロップダウン リストをクリックして**RouteBasedOnMessageType v 1.0**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-165">In the **Policy** drop-down list, click **RouteBasedOnMessageType v 1.0**.</span></span>  
  
4.  <span data-ttu-id="9c102-166">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-166">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="9c102-167">接続をドラッグして、 **ReceiveOrders**モデル要素を**BreRoute**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="9c102-167">Drag a connection from the **ReceiveOrders** model element to the **BreRoute** model element.</span></span>  
  
5.  <span data-ttu-id="9c102-168">ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **BreRoute**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="9c102-168">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **BreRoute** model element.</span></span> <span data-ttu-id="9c102-169">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9c102-169">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9c102-170">クリックして、**名前**プロパティ、および入力**SendBasedOnType**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-170">Click the **Name** property, and then type **SendBasedOnType**.</span></span>  
  
    2.  <span data-ttu-id="9c102-171">**Extender**ドロップダウン リストをクリックして**出口 ESB Extender**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-171">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="9c102-172">**BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-172">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="9c102-173">**送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-173">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
6.  <span data-ttu-id="9c102-174">ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **BreRoute**モデル要素と**SendBasedOnType**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="9c102-174">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **BreRoute** model element and the **SendBasedOnType** model element.</span></span> <span data-ttu-id="9c102-175">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9c102-175">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9c102-176">クリックして、**名前**プロパティ、および入力**SendPortFilter**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-176">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="9c102-177">**行程サービス エクステンダー**ドロップダウン リストをクリックして**出口 Extender**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-177">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="9c102-178">**出口**ドロップダウン リストで、展開**SendBasedOnType**、クリックして**送信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-178">In the **Off-Ramp** drop-down list, expand **SendBasedOnType**, and then click **Send Handlers**.</span></span>  
  
7.  <span data-ttu-id="9c102-179">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-179">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="9c102-180">接続をドラッグして、 **BreRoute**モデル要素を**SendPortFilter**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="9c102-180">Drag a connection from the **BreRoute** model element to the **SendPortFilter** model element.</span></span>  
  
8.  <span data-ttu-id="9c102-181">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-181">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="9c102-182">接続をドラッグして、 **SendPortFilter**モデル要素を**SendBasedOnType**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="9c102-182">Drag a connection from the **SendPortFilter** model element to the **SendBasedOnType** model element.</span></span>  
  
 <span data-ttu-id="9c102-183">**行程テスト クライアントで使用するモデルをエクスポートするには**</span><span class="sxs-lookup"><span data-stu-id="9c102-183">**To export the model for use with the Itinerary Test Client**</span></span>  
  
1.  <span data-ttu-id="9c102-184">Visual Studio でのデザイン画面を右クリックし、 **MessageType**行程をクリックして**モデルのエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-184">In Visual Studio, right-click the design surface of the **MessageType** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9c102-185">旅行計画の XML バージョンは、Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="9c102-185">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="9c102-186">すべてのプロジェクトの成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="9c102-186">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="9c102-187">Windows エクスプローラで、C:\HowTos\Itineraries を参照し、行程 XML (MessageType.xml) の作成に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9c102-187">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (MessageType.xml).</span></span>  
  
 <span data-ttu-id="9c102-188">**旅行計画をテストするには**</span><span class="sxs-lookup"><span data-stu-id="9c102-188">**To test the itinerary**</span></span>  
  
1.  <span data-ttu-id="9c102-189">中に作成されたショートカットを使用して行程テスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB です。Itinerary.Test.exe - ショートカット)。</span><span class="sxs-lookup"><span data-stu-id="9c102-189">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="9c102-190">行程テスト クライアントで、クリア、**を使用して WCF サービス**チェック ボックスをクリックして**ロード行程**です。</span><span class="sxs-lookup"><span data-stu-id="9c102-190">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="9c102-191">**行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="9c102-191">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="9c102-192">選択**MessageType.xml**、順にクリック**開く**日程を読み込めません。</span><span class="sxs-lookup"><span data-stu-id="9c102-192">Select **MessageType.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="9c102-193">をクリックして**OK**をクリアする、**行程が正常に読み込まれる**メッセージ。</span><span class="sxs-lookup"><span data-stu-id="9c102-193">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="9c102-194">行程テスト クライアントで、横にある省略記号ボタン (...) をクリックして、**メッセージの読み込み**ボックス。</span><span class="sxs-lookup"><span data-stu-id="9c102-194">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="9c102-195">**選択読み込む XML ドキュメントを** ダイアログ ボックスで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="9c102-195">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="9c102-196">選択**NAOrderDoc.xml**、順にクリック**開く**テスト メッセージを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="9c102-196">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="9c102-197">クリックして、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c102-197">Click the **Submit Request** button.</span></span> <span data-ttu-id="9c102-198">テストが完了したらをクリックして**OK**表示される確認メッセージを破棄します。</span><span class="sxs-lookup"><span data-stu-id="9c102-198">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="9c102-199">Windows エクスプローラで、参照 C:\HowTos\Out\\です。</span><span class="sxs-lookup"><span data-stu-id="9c102-199">In Windows Explorer, browse to C:\HowTos\Out\\.</span></span> <span data-ttu-id="9c102-200">NorthAmerica%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c102-200">Verify that the NorthAmerica%MessageID%.xml message has been written to the directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="9c102-201">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="9c102-201">Additional Resources</span></span>  
 <span data-ttu-id="9c102-202">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c102-202">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="9c102-203">方法: ビジネス ルール ポリシーを使用して、日程を選択</span><span class="sxs-lookup"><span data-stu-id="9c102-203">How to: Select an Itinerary Using a Business Rules Policy</span></span>](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [<span data-ttu-id="9c102-204">方法: メッセージを変換および Itinerary のルーティング先を使用してファイルの場所に、結果のメッセージをルーティング</span><span class="sxs-lookup"><span data-stu-id="9c102-204">How to: Transform a Message and Route the Resulting Message to a File Location Using an Itinerary Routing Slip</span></span>](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [<span data-ttu-id="9c102-205">方法: 既知のメッセージの種類のポリシーをルール実装のビジネスを使用してコンテンツ ベース ルーティング</span><span class="sxs-lookup"><span data-stu-id="9c102-205">How to: Implement Content-Based Routing Using a Business Rules Policy for a Known Message Type</span></span>](../esb-toolkit/apply-content-based-routing-using-business-rules-policy-for-known-message-type.md)  
  
-   [<span data-ttu-id="9c102-206">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="9c102-206">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="9c102-207">メッセージのルーティング パターン</span><span class="sxs-lookup"><span data-stu-id="9c102-207">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)  
  
-   [<span data-ttu-id="9c102-208">動的な解決を使用して、ルーティング</span><span class="sxs-lookup"><span data-stu-id="9c102-208">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)