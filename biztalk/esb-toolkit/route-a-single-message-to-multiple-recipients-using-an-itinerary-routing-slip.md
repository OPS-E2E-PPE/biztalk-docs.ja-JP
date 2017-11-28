---
title: "方法: Itinerary ルーティング先を使用して複数の受信者を 1 つのメッセージをルーティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42c30493-4fe1-4fd5-8bc7-af091535b091
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fa96603bc93c9d5d19ef102695a1189a50d00ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-route-a-single-message-to-multiple-recipients-using-an-itinerary-routing-slip"></a><span data-ttu-id="becf1-102">方法: Itinerary ルーティング先を使用して複数の受信者を 1 つのメッセージをルーティング</span><span class="sxs-lookup"><span data-stu-id="becf1-102">How to: Route a Single Message to Multiple Recipients Using an Itinerary Routing Slip</span></span>
## <a name="goal"></a><span data-ttu-id="becf1-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="becf1-103">Goal</span></span>  
 <span data-ttu-id="becf1-104">このセクションでは、静的な競合回避モジュールを使用して 3 つの個別の受信者にデザイナー ドメイン固有言語 (DSL) を使用してメッセージをルーティングする旅程を作成する方法を示します、[!INCLUDE[prague](../includes/prague-md.md)]ファイル アダプター。</span><span class="sxs-lookup"><span data-stu-id="becf1-104">This section demonstrates how to use the Designer domain-specific language (DSL) to create an itinerary that routes a message to three distinct recipients using a static resolver and the [!INCLUDE[prague](../includes/prague-md.md)] FILE adapter.</span></span>  
  
 <span data-ttu-id="becf1-105">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="becf1-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="becf1-106">複数の受信者にメッセージをルーティングする 3 つの静的なリゾルバーを日程を作成します。</span><span class="sxs-lookup"><span data-stu-id="becf1-106">Create an itinerary with three static resolvers to route messages to multiple recipients.</span></span>  
  
-   <span data-ttu-id="becf1-107">行程テスト用クライアントのサンプル アプリケーションを使用して旅程をテストします。</span><span class="sxs-lookup"><span data-stu-id="becf1-107">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="becf1-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="becf1-108">Prerequisites</span></span>  
 <span data-ttu-id="becf1-109">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。</span><span class="sxs-lookup"><span data-stu-id="becf1-109">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="becf1-110">手順</span><span class="sxs-lookup"><span data-stu-id="becf1-110">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="becf1-111">ESB itinerary DSL モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="becf1-111">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="becf1-112">[!INCLUDE[vs2010](../includes/vs2010-md.md)]C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="becf1-112">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="becf1-113">ソリューション エクスプ ローラーで右クリック**ItineraryLibrary**、 をポイント**追加**、クリックして**新しい行程**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-113">In Solution Explorer, right-click **ItineraryLibrary**, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="becf1-114">**新しい項目の追加**ダイアログ ボックスで、をクリックして**ItineraryDsl**テンプレート ペインでします。</span><span class="sxs-lookup"><span data-stu-id="becf1-114">In the **Add New Item** dialog box, click **ItineraryDsl** in the Templates pane.</span></span>  
  
4.  <span data-ttu-id="becf1-115">**名前**ボックスに、入力**RecipientList**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-115">In the **Name** box, type **RecipientList**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="becf1-116">旅行計画のプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="becf1-116">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="becf1-117">Visual Studio で、RecipientList.itinerary のデザイン画面をクリックします。</span><span class="sxs-lookup"><span data-stu-id="becf1-117">In Visual Studio, click the design surface of RecipientList.itinerary.</span></span> <span data-ttu-id="becf1-118">RecipientList [プロパティ] ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="becf1-118">In the RecipientList Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="becf1-119">**モデル エクスポーター**ドロップダウン リストをクリックして**XML 行程エクスポーター**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-119">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="becf1-120">**Extender 設定**セクションで、横に、**行程 XML ファイル**プロパティ、省略記号ボタン (...) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="becf1-120">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="becf1-121">**[XML ファイルの**] ダイアログ ボックスで、**ファイル名**ボックスに、入力**C:\HowTos\Itineraries\RecipientList**、クリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-121">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\RecipientList**, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="becf1-122">この手順では、旅行計画をローカル ファイルの場所に XML としてエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="becf1-122">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="becf1-123">代わりに、ローカル ファイルの場所に日程を itinerary のデータベースにエクスポートして ESB のテスト用クライアント アプリケーションを使用して旅行計画のテストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="becf1-123">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="becf1-124">このトピックの後半には、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="becf1-124">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="becf1-125">旅行計画の構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="becf1-125">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="becf1-126">ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。</span><span class="sxs-lookup"><span data-stu-id="becf1-126">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="becf1-127">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="becf1-127">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="becf1-128">クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-128">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="becf1-129">**Extender**ドロップダウン リストをクリックして**入り口 Extender**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-129">In the **Extender** drop-down list, click **On-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="becf1-130">**BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-130">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="becf1-131">**受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-131">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="becf1-132">ツールボックスからドラッグ、**行程サービス**デザイン画面に要素をモデル化の右側に配置し、**入り口**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="becf1-132">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="becf1-133">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="becf1-133">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="becf1-134">クリックして、**名前**プロパティ、および入力**RouteToThreeRecipients**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-134">Click the **Name** property, and then type **RouteToThreeRecipients**.</span></span>  
  
    2.  <span data-ttu-id="becf1-135">**行程サービス エクステンダー**ドロップダウン リストをクリックして**エクステンダーのメッセージング**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-135">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="becf1-136">このプロパティは、あるプロセスで行われます (メッセージング) パイプラインを定義します。</span><span class="sxs-lookup"><span data-stu-id="becf1-136">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="becf1-137">または、プロセスは、オーケストレーションで行われます、設定、**行程サービス エクステンダー**プロパティを**オーケストレーション Extender**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-137">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="becf1-138">**コンテナー**ドロップダウン リストで、展開**ReceiveNaOrderDoc**、クリックして**受信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-138">In the **Container** drop-down list, expand **ReceiveNaOrderDoc**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="becf1-139">**サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Routing**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-139">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
3.  <span data-ttu-id="becf1-140">右クリックし、**リゾルバー**のコレクション、 **RouteToThreeRecipients**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-140">Right-click the **Resolver** collection of the **RouteToThreeRecipients** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="becf1-141">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="becf1-141">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="becf1-142">クリックして、**名前**プロパティ、および入力**FirstResolver**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-142">Click the **Name** property, and then type **FirstResolver**.</span></span>  
  
    2.  <span data-ttu-id="becf1-143">**リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="becf1-143">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="becf1-144">**トランスポート名**ドロップダウン リストをクリックして**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-144">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="becf1-145">クリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\First%MessageID%.xml**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-145">Click the **Transport Location** property, and then type **C:\HowTos\Out\First%MessageID%.xml**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="becf1-146">この itinerary サービスの 3 つの競合回避モジュールの最初の数値を追加しました。</span><span class="sxs-lookup"><span data-stu-id="becf1-146">You have added the first of three resolvers for this itinerary service.</span></span> <span data-ttu-id="becf1-147">追加の受信者にメッセージをルーティングする競合回避モジュールは、次の 2 つ以上を追加します。</span><span class="sxs-lookup"><span data-stu-id="becf1-147">You will now add two more resolvers to route the message to additional recipients.</span></span>  
  
4.  <span data-ttu-id="becf1-148">右クリックし、**リゾルバー**のコレクション、 **RouteToThreeRecipients**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-148">Right-click the **Resolver** collection of the **RouteToThreeRecipients** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="becf1-149">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="becf1-149">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="becf1-150">クリックして、**名前**プロパティ、および入力**SecondResolver**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-150">Click the **Name** property, and then type **SecondResolver**.</span></span>  
  
    2.  <span data-ttu-id="becf1-151">**リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="becf1-151">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="becf1-152">**トランスポート名**ドロップダウン リストをクリックして**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-152">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="becf1-153">クリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\Second%MessageID%.xml**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-153">Click the **Transport Location** property, and then type **C:\HowTos\Out\Second%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="becf1-154">右クリックし、**リゾルバー**のコレクション、 **RouteToThreeRecipients**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-154">Right-click the **Resolver** collection of the **RouteToThreeRecipients** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="becf1-155">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="becf1-155">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="becf1-156">クリックして、**名前**プロパティ、および入力**ThirdResolver**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-156">Click the **Name** property, and then type **ThirdResolver**.</span></span>  
  
    2.  <span data-ttu-id="becf1-157">**リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="becf1-157">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="becf1-158">**トランスポート名**ドロップダウン リストをクリックして**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-158">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="becf1-159">クリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\Third%MessageID%.xml**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-159">Click the **Transport Location** property, and then type **C:\HowTos\Out\Third%MessageID%.xml**.</span></span>  
  
6.  <span data-ttu-id="becf1-160">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-160">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="becf1-161">接続をドラッグして、 **ReceiveNAOrder**モデル要素を**RouteToThreeRecipients**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="becf1-161">Drag a connection from the **ReceiveNAOrder** model element to the **RouteToThreeRecipients** model element.</span></span>  
  
7.  <span data-ttu-id="becf1-162">ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **RouteToThreeRecipients**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="becf1-162">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteToThreeRecipients** model element.</span></span> <span data-ttu-id="becf1-163">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="becf1-163">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="becf1-164">クリックして、**名前**プロパティ、および入力**SendThreeMessages**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-164">Click the **Name** property, and then type **SendThreeMessages**.</span></span>  
  
    2.  <span data-ttu-id="becf1-165">**Extender**ドロップダウン リストをクリックして**出口 ESB Extender**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-165">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="becf1-166">**BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-166">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="becf1-167">**送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-167">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
8.  <span data-ttu-id="becf1-168">ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **RouteToThreeRecipients**モデル要素と**SendThreeMessages**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="becf1-168">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteToThreeRecipients** model element and the **SendThreeMessages** model element.</span></span> <span data-ttu-id="becf1-169">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="becf1-169">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="becf1-170">クリックして、**名前**プロパティ、および入力**SendPortFilter**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-170">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="becf1-171">**行程サービス エクステンダー**ドロップダウン リストをクリックして**出口 Extender**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-171">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="becf1-172">**出口**ドロップダウン リストで、展開**SendThreeMessages**、クリックして**送信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-172">In the **Off-Ramp** drop-down list, expand **SendThreeMessages**, and then click **Send Handlers**.</span></span>  
  
9. <span data-ttu-id="becf1-173">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-173">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="becf1-174">接続をドラッグして、 **RouteToThreeRecipients**モデル要素を**SendPortFilter**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="becf1-174">Drag a connection from the **RouteToThreeRecipients** model element to the **SendPortFilter** model element.</span></span>  
  
10. <span data-ttu-id="becf1-175">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-175">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="becf1-176">接続をドラッグして、 **SendPortFilter**モデル要素を**SendThreeMessages**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="becf1-176">Drag a connection from the **SendPortFilter** model element to the **SendThreeMessages** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="becf1-177">行程テスト クライアントで使用するモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="becf1-177">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="becf1-178">Visual Studio でのデザイン画面を右クリックし、 **RecipientList**行程をクリックして**モデルのエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-178">In Visual Studio, right-click the design surface of the **RecipientList** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="becf1-179">旅行計画の XML バージョンは、Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="becf1-179">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="becf1-180">すべてのプロジェクトの成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="becf1-180">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="becf1-181">Windows エクスプ ローラーで、C:\HowTos\Itineraries を参照し、旅程 XML (RecipientList.xml) の作成を確認します。</span><span class="sxs-lookup"><span data-stu-id="becf1-181">In Windows Explorer, browse to C:\HowTos\Itineraries, and then notice the creation of your itinerary XML (RecipientList.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="becf1-182">旅行計画をテストするには</span><span class="sxs-lookup"><span data-stu-id="becf1-182">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="becf1-183">中に作成されたショートカットを使用して行程テスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB です。Itinerary.Test.exe - ショートカット)。</span><span class="sxs-lookup"><span data-stu-id="becf1-183">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="becf1-184">行程テスト クライアントで、クリア、**を使用して WCF サービス**チェック ボックスをクリックして**ロード行程**です。</span><span class="sxs-lookup"><span data-stu-id="becf1-184">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="becf1-185">**行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="becf1-185">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="becf1-186">選択**RecipientList.xml**、順にクリック**開く**日程を読み込めません。</span><span class="sxs-lookup"><span data-stu-id="becf1-186">Select **RecipientList.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="becf1-187">をクリックして**OK**をオフに、"行程が正常に読み込まれた: メッセージ。</span><span class="sxs-lookup"><span data-stu-id="becf1-187">Click **OK** to clear the "Itinerary Loaded Successfully: message.</span></span>  
  
5.  <span data-ttu-id="becf1-188">行程テスト クライアントで、横にある省略記号ボタン (...) をクリックして、**メッセージの読み込み**ボックス。</span><span class="sxs-lookup"><span data-stu-id="becf1-188">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="becf1-189">**選択読み込む XML ドキュメントを** ダイアログ ボックスで、C:\Patterns を参照します。</span><span class="sxs-lookup"><span data-stu-id="becf1-189">In the **Select XML Document to load** dialog box, browse to C:\Patterns.</span></span> <span data-ttu-id="becf1-190">NAOrderDoc.xml を選択し、クリックして**開く**テスト メッセージを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="becf1-190">Select NAOrderDoc.xml, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="becf1-191">クリックして、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="becf1-191">Click the **Submit Request** button.</span></span> <span data-ttu-id="becf1-192">テストが完了したらをクリックして**OK**表示される確認メッセージを破棄します。</span><span class="sxs-lookup"><span data-stu-id="becf1-192">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="becf1-193">Windows エクスプローラで、参照 C:\HowTos\Out\\です。</span><span class="sxs-lookup"><span data-stu-id="becf1-193">In Windows Explorer, browse to C:\HowTos\Out\\.</span></span> <span data-ttu-id="becf1-194">ディレクトリに、次のメッセージが書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="becf1-194">Verify that the following messages have been written to the directory:</span></span>  
  
    -   <span data-ttu-id="becf1-195">First%MessageID%.xml</span><span class="sxs-lookup"><span data-stu-id="becf1-195">First%MessageID%.xml</span></span>  
  
    -   <span data-ttu-id="becf1-196">Second%MessageID%.xml</span><span class="sxs-lookup"><span data-stu-id="becf1-196">Second%MessageID%.xml</span></span>  
  
    -   <span data-ttu-id="becf1-197">Third%MessageID%.xml</span><span class="sxs-lookup"><span data-stu-id="becf1-197">Third%MessageID%.xml</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="becf1-198">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="becf1-198">Additional Resources</span></span>  
 <span data-ttu-id="becf1-199">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="becf1-199">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="becf1-200">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="becf1-200">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="becf1-201">メッセージのルーティング パターン</span><span class="sxs-lookup"><span data-stu-id="becf1-201">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)  
  
-   [<span data-ttu-id="becf1-202">動的な解決を使用して、ルーティング</span><span class="sxs-lookup"><span data-stu-id="becf1-202">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)