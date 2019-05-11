---
title: 操作方法:1 つのメッセージをスケジュール ルーティング スリップを使用して複数の受信者にルーティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 42c30493-4fe1-4fd5-8bc7-af091535b091
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9eb1118850c46215ebd57f25956ce3581eee844
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395893"
---
# <a name="how-to-route-a-single-message-to-multiple-recipients-using-an-itinerary-routing-slip"></a><span data-ttu-id="fed08-102">操作方法:1 つのメッセージをスケジュール ルーティング スリップを使用して複数の受信者にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="fed08-102">How to: Route a Single Message to Multiple Recipients Using an Itinerary Routing Slip</span></span>
## <a name="goal"></a><span data-ttu-id="fed08-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="fed08-103">Goal</span></span>  
 <span data-ttu-id="fed08-104">このセクションでは、デザイナー: ドメイン固有言語 (DSL) を使用して静的な競合回避モジュールと、BizTalk Server ファイル アダプターを使用して 3 つの異なる受信者にメッセージをルーティングする旅行プランを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fed08-104">This section demonstrates how to use the Designer domain-specific language (DSL) to create an itinerary that routes a message to three distinct recipients using a static resolver and the BizTalk Server FILE adapter.</span></span>  
  
 <span data-ttu-id="fed08-105">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="fed08-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="fed08-106">複数の受信者にメッセージをルーティングの 3 つの静的リゾルバーを旅行プランを作成します。</span><span class="sxs-lookup"><span data-stu-id="fed08-106">Create an itinerary with three static resolvers to route messages to multiple recipients.</span></span>  
  
-   <span data-ttu-id="fed08-107">旅行プランのテスト用クライアントのサンプル アプリケーションを使用して、旅行プランをテストします。</span><span class="sxs-lookup"><span data-stu-id="fed08-107">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fed08-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="fed08-108">Prerequisites</span></span>  
 <span data-ttu-id="fed08-109">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。</span><span class="sxs-lookup"><span data-stu-id="fed08-109">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="fed08-110">手順</span><span class="sxs-lookup"><span data-stu-id="fed08-110">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="fed08-111">ESB スケジュール オンランプ DSL モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="fed08-111">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="fed08-112">Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="fed08-112">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="fed08-113">ソリューション エクスプ ローラーで右クリック**ItineraryLibrary**、 をポイント**追加**、 をクリックし、**新しいスケジュール**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-113">In Solution Explorer, right-click **ItineraryLibrary**, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="fed08-114">**新しい項目の追加**ダイアログ ボックスで、をクリックして**ItineraryDsl**テンプレート ペインでします。</span><span class="sxs-lookup"><span data-stu-id="fed08-114">In the **Add New Item** dialog box, click **ItineraryDsl** in the Templates pane.</span></span>  
  
4.  <span data-ttu-id="fed08-115">**名前**ボックスに「 **RecipientList**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-115">In the **Name** box, type **RecipientList**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="fed08-116">旅行プランのプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="fed08-116">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="fed08-117">Visual Studio で、RecipientList.itinerary のデザイン画面をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fed08-117">In Visual Studio, click the design surface of RecipientList.itinerary.</span></span> <span data-ttu-id="fed08-118">RecipientList [プロパティ] ウィンドウでは、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="fed08-118">In the RecipientList Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="fed08-119">**モデル エクスポーター**ドロップダウン リストでは、をクリックして**XML 行程エクスポーター**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-119">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="fed08-120">**エクステンダー設定**セクションで、次に、**旅行プラン XML ファイル**プロパティ、省略記号ボタン (…) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fed08-120">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="fed08-121">**[XML ファイルの**] ダイアログ ボックスで、**ファイル名**ボックスに「 **C:\HowTos\Itineraries\RecipientList**、順にクリックします**保存**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-121">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\RecipientList**, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="fed08-122">この手順では、旅行プランを XML としてローカル ファイルの場所にエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="fed08-122">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="fed08-123">行程データベースの代わりにスケジュールをローカル ファイルの場所にエクスポートして、ESB のテスト用クライアント アプリケーションを使用してスケジュールのテストが可能です。</span><span class="sxs-lookup"><span data-stu-id="fed08-123">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="fed08-124">この操作方法に関するトピックの後半には、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="fed08-124">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="fed08-125">旅行プランの構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="fed08-125">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="fed08-126">ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。</span><span class="sxs-lookup"><span data-stu-id="fed08-126">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="fed08-127">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="fed08-127">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="fed08-128">をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-128">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="fed08-129">**エクステンダー**ドロップダウン リストでは、をクリックして**ランプで Extender**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-129">In the **Extender** drop-down list, click **On-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="fed08-130">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-130">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="fed08-131">**受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-131">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="fed08-132">ツールボックスからドラッグ、**行程サービス**の右側に配置し、デザイン画面に要素をモデル化し、**入口**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="fed08-132">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="fed08-133">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="fed08-133">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="fed08-134">をクリックして、**名前**プロパティ、および入力**RouteToThreeRecipients**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-134">Click the **Name** property, and then type **RouteToThreeRecipients**.</span></span>  
  
    2.  <span data-ttu-id="fed08-135">**行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**エクステンダーのメッセージング**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-135">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="fed08-136">このプロパティは、プロセスが行われる (メッセージング) パイプラインで定義します。</span><span class="sxs-lookup"><span data-stu-id="fed08-136">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="fed08-137">または、プロセスはオーケストレーション内の場所を受け取らない場合は設定、**行程サービス エクステンダー**プロパティを**オーケストレーション エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-137">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="fed08-138">**コンテナー**ドロップダウン リストで、展開**ReceiveNaOrderDoc**、 をクリックし、**受信ハンドラー**。</span><span class="sxs-lookup"><span data-stu-id="fed08-138">In the **Container** drop-down list, expand **ReceiveNaOrderDoc**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="fed08-139">**サービス名**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB.Services.Routing**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-139">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
3.  <span data-ttu-id="fed08-140">右クリックし、**リゾルバー**のコレクション、 **RouteToThreeRecipients**モデル要素をクリックして**新しいリゾルバーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-140">Right-click the **Resolver** collection of the **RouteToThreeRecipients** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="fed08-141">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="fed08-141">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="fed08-142">をクリックして、**名前**プロパティ、および入力**FirstResolver**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-142">Click the **Name** property, and then type **FirstResolver**.</span></span>  
  
    2.  <span data-ttu-id="fed08-143">**リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-143">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="fed08-144">**トランスポート名**ドロップダウン リストでは、をクリックして**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-144">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="fed08-145">をクリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\First%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-145">Click the **Transport Location** property, and then type **C:\HowTos\Out\First%MessageID%.xml**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="fed08-146">このスケジュール サービスの 3 つの競合回避モジュールの最初の数値が追加されました。</span><span class="sxs-lookup"><span data-stu-id="fed08-146">You have added the first of three resolvers for this itinerary service.</span></span> <span data-ttu-id="fed08-147">追加の受信者にメッセージをルーティングする 2 つ以上のリゾルバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fed08-147">You will now add two more resolvers to route the message to additional recipients.</span></span>  
  
4.  <span data-ttu-id="fed08-148">右クリックし、**リゾルバー**のコレクション、 **RouteToThreeRecipients**モデル要素をクリックして**新しいリゾルバーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-148">Right-click the **Resolver** collection of the **RouteToThreeRecipients** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="fed08-149">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="fed08-149">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="fed08-150">をクリックして、**名前**プロパティ、および入力**SecondResolver**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-150">Click the **Name** property, and then type **SecondResolver**.</span></span>  
  
    2.  <span data-ttu-id="fed08-151">**リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-151">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="fed08-152">**トランスポート名**ドロップダウン リストでは、をクリックして**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-152">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="fed08-153">をクリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\Second%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-153">Click the **Transport Location** property, and then type **C:\HowTos\Out\Second%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="fed08-154">右クリックし、**リゾルバー**のコレクション、 **RouteToThreeRecipients**モデル要素をクリックして**新しいリゾルバーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-154">Right-click the **Resolver** collection of the **RouteToThreeRecipients** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="fed08-155">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="fed08-155">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="fed08-156">をクリックして、**名前**プロパティ、および入力**ThirdResolver**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-156">Click the **Name** property, and then type **ThirdResolver**.</span></span>  
  
    2.  <span data-ttu-id="fed08-157">**リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-157">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="fed08-158">**トランスポート名**ドロップダウン リストでは、をクリックして**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-158">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="fed08-159">をクリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\Third%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-159">Click the **Transport Location** property, and then type **C:\HowTos\Out\Third%MessageID%.xml**.</span></span>  
  
6.  <span data-ttu-id="fed08-160">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-160">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="fed08-161">接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **RouteToThreeRecipients**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="fed08-161">Drag a connection from the **ReceiveNAOrder** model element to the **RouteToThreeRecipients** model element.</span></span>  
  
7.  <span data-ttu-id="fed08-162">ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **RouteToThreeRecipients**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="fed08-162">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteToThreeRecipients** model element.</span></span> <span data-ttu-id="fed08-163">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="fed08-163">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="fed08-164">をクリックして、**名前**プロパティ、および入力**SendThreeMessages**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-164">Click the **Name** property, and then type **SendThreeMessages**.</span></span>  
  
    2.  <span data-ttu-id="fed08-165">**エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-165">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="fed08-166">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-166">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="fed08-167">**送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-167">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
8.  <span data-ttu-id="fed08-168">ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **RouteToThreeRecipients**モデル要素と**SendThreeMessages**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="fed08-168">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteToThreeRecipients** model element and the **SendThreeMessages** model element.</span></span> <span data-ttu-id="fed08-169">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="fed08-169">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="fed08-170">をクリックして、**名前**プロパティ、および入力**SendPortFilter**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-170">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="fed08-171">**行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ エクステンダー**。</span><span class="sxs-lookup"><span data-stu-id="fed08-171">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="fed08-172">**傾斜オフ**ドロップダウン リストで、展開**SendThreeMessages**、順にクリックします**送信ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-172">In the **Off-Ramp** drop-down list, expand **SendThreeMessages**, and then click **Send Handlers**.</span></span>  
  
9. <span data-ttu-id="fed08-173">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-173">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="fed08-174">接続をドラッグして、 **RouteToThreeRecipients**モデル要素に、 **SendPortFilter**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="fed08-174">Drag a connection from the **RouteToThreeRecipients** model element to the **SendPortFilter** model element.</span></span>  
  
10. <span data-ttu-id="fed08-175">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-175">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="fed08-176">接続をドラッグして、 **SendPortFilter**モデル要素に、 **SendThreeMessages**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="fed08-176">Drag a connection from the **SendPortFilter** model element to the **SendThreeMessages** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="fed08-177">旅行プランのテスト クライアントで使用するモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="fed08-177">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="fed08-178">Visual Studio でのデザイン画面を右クリックし、 **RecipientList**旅行プランをクリックして**モデルのエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="fed08-178">In Visual Studio, right-click the design surface of the **RecipientList** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fed08-179">旅行プランの XML バージョンは、Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="fed08-179">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="fed08-180">すべてのプロジェクト成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="fed08-180">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="fed08-181">Windows エクスプ ローラーでは、C:\HowTos\Itineraries を参照して、旅行プラン XML (RecipientList.xml) の作成に注意してください。</span><span class="sxs-lookup"><span data-stu-id="fed08-181">In Windows Explorer, browse to C:\HowTos\Itineraries, and then notice the creation of your itinerary XML (RecipientList.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="fed08-182">旅行プランをテストするには</span><span class="sxs-lookup"><span data-stu-id="fed08-182">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="fed08-183">中に作成されたショートカットを使用してスケジュールのテスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB します。Itinerary.Test.exe - ショートカット)。</span><span class="sxs-lookup"><span data-stu-id="fed08-183">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="fed08-184">行程テスト クライアントでオフ、 **WCF サービスを使用して**チェック ボックスをオンにし**ロード行程**。</span><span class="sxs-lookup"><span data-stu-id="fed08-184">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="fed08-185">**行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="fed08-185">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="fed08-186">選択**RecipientList.xml**、順にクリックします**オープン**旅行プランを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="fed08-186">Select **RecipientList.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="fed08-187">をクリックして**OK**をオフに、"スケジュールが正常に読み込まれました: メッセージ。</span><span class="sxs-lookup"><span data-stu-id="fed08-187">Click **OK** to clear the "Itinerary Loaded Successfully: message.</span></span>  
  
5.  <span data-ttu-id="fed08-188">旅行プランのテスト クライアントで、横にある省略記号ボタン (…) をクリックします。、**ロード メッセージ**ボックス。</span><span class="sxs-lookup"><span data-stu-id="fed08-188">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="fed08-189">**を読み込む XML ドキュメントの選択** ダイアログ ボックスで、C:\Patterns を参照します。</span><span class="sxs-lookup"><span data-stu-id="fed08-189">In the **Select XML Document to load** dialog box, browse to C:\Patterns.</span></span> <span data-ttu-id="fed08-190">NAOrderDoc.xml を選択し、クリックして**オープン**テスト メッセージを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="fed08-190">Select NAOrderDoc.xml, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="fed08-191">をクリックして、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fed08-191">Click the **Submit Request** button.</span></span> <span data-ttu-id="fed08-192">テストが完了したら、クリックして**OK**表示される確認メッセージを無視します。</span><span class="sxs-lookup"><span data-stu-id="fed08-192">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="fed08-193">Windows エクスプ ローラーで参照 C:\HowTos\Out\\します。</span><span class="sxs-lookup"><span data-stu-id="fed08-193">In Windows Explorer, browse to C:\HowTos\Out\\.</span></span> <span data-ttu-id="fed08-194">次のメッセージが、ディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="fed08-194">Verify that the following messages have been written to the directory:</span></span>  
  
    -   <span data-ttu-id="fed08-195">First%MessageID%.xml</span><span class="sxs-lookup"><span data-stu-id="fed08-195">First%MessageID%.xml</span></span>  
  
    -   <span data-ttu-id="fed08-196">Second%MessageID%.xml</span><span class="sxs-lookup"><span data-stu-id="fed08-196">Second%MessageID%.xml</span></span>  
  
    -   <span data-ttu-id="fed08-197">Third%MessageID%.xml</span><span class="sxs-lookup"><span data-stu-id="fed08-197">Third%MessageID%.xml</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="fed08-198">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="fed08-198">Additional Resources</span></span>  
 <span data-ttu-id="fed08-199">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fed08-199">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="fed08-200">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="fed08-200">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="fed08-201">メッセージ ルーティング パターン</span><span class="sxs-lookup"><span data-stu-id="fed08-201">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)  
  
-   [<span data-ttu-id="fed08-202">動的な解決とルーティングを利用する</span><span class="sxs-lookup"><span data-stu-id="fed08-202">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)