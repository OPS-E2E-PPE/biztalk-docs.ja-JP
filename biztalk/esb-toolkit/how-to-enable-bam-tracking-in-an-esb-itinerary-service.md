---
title: 操作方法:ESB スケジュール サービスで BAM の追跡を有効にする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58859937-f8d0-4c33-9a7a-62fec8441936
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b685c1d1e670bec50f925c615a3a17222e0bfc92
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258481"
---
# <a name="how-to-enable-bam-tracking-in-an-esb-itinerary-service"></a><span data-ttu-id="961e3-102">操作方法:ESB スケジュール サービスで BAM の追跡を有効にします。</span><span class="sxs-lookup"><span data-stu-id="961e3-102">How to: Enable BAM Tracking in an ESB Itinerary Service</span></span>
## <a name="goal"></a><span data-ttu-id="961e3-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="961e3-103">Goal</span></span>  
 <span data-ttu-id="961e3-104">このセクションでは、ビジネス アクティビティ監視 (BAM) が既存のスケジュールの追跡を有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="961e3-104">This section demonstrates how to enable Business Activity Monitor (BAM) tracking for an existing itinerary.</span></span>  
  
 <span data-ttu-id="961e3-105">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="961e3-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="961e3-106">旅行プランをビジネスの利用状況モニターを使用してサービスを追跡するために使用されるプロパティを有効にします。</span><span class="sxs-lookup"><span data-stu-id="961e3-106">Enable the property used for tracking Itinerary Services using Business Activity Monitor.</span></span>  
  
-   <span data-ttu-id="961e3-107">旅行プランのテスト用クライアントのサンプル アプリケーションを使用して BAM の追跡をテストします。</span><span class="sxs-lookup"><span data-stu-id="961e3-107">Test BAM tracking using the Itinerary Test Client sample application.</span></span>  
  
-   <span data-ttu-id="961e3-108">SQL クエリを使用して BAM の結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="961e3-108">Verify the BAM results using a SQL query.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="961e3-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="961e3-109">Prerequisites</span></span>  
 <span data-ttu-id="961e3-110">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。</span><span class="sxs-lookup"><span data-stu-id="961e3-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="961e3-111">はじめに</span><span class="sxs-lookup"><span data-stu-id="961e3-111">Before You Begin</span></span>  
 <span data-ttu-id="961e3-112">この操作方法に関するトピックの後半の手順を実行する前に、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="961e3-112">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
- <span data-ttu-id="961e3-113">ESB スケジュール オンランプ ドメイン固有言語 (DSL) モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="961e3-113">Create an ESB itinerary domain-specific language (DSL) model.</span></span>  
  
- <span data-ttu-id="961e3-114">旅行プランのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="961e3-114">Configure the properties of the itinerary.</span></span>  
  
- <span data-ttu-id="961e3-115">旅行プランの構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="961e3-115">Define the structure of the itinerary.</span></span>  
  
  <span data-ttu-id="961e3-116">次の手順では、これらの各方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="961e3-116">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="961e3-117">ESB スケジュール オンランプ DSL モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="961e3-117">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="961e3-118">Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="961e3-118">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="961e3-119">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントして、**追加**、順にクリックします**新しい行程**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-119">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="961e3-120">**新しい項目の追加**ダイアログ ボックスで、をクリックして**ItineraryDsl**テンプレート ペインでします。</span><span class="sxs-lookup"><span data-stu-id="961e3-120">In the **Add New Item** dialog box, click  **ItineraryDsl** in the Templates pane.</span></span>  
  
4.  <span data-ttu-id="961e3-121">**名前**ボックスに「 **BamTracking**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-121">In the **Name** box, type **BamTracking**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="961e3-122">旅行プランのプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="961e3-122">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="961e3-123">Visual Studio でのデザイン画面をクリックします。 **BamTracking.itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-123">In Visual Studio, click the design surface of **BamTracking.itinerary**.</span></span> <span data-ttu-id="961e3-124">**BamTracking**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="961e3-124">In the **BamTracking** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="961e3-125">**モデル エクスポーター**ドロップダウン リストでは、をクリックして**XML 行程エクスポーター**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-125">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="961e3-126">**エクステンダー設定**セクションで、次に、**旅行プラン XML ファイル**プロパティ、省略記号ボタン (…) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="961e3-126">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="961e3-127">**[XML ファイルの**] ダイアログ ボックスで、**ファイル名**ボックスに「 **C:\HowTos\Itineraries\BamTracking**順にクリックします**保存**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-127">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\BamTracking** and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="961e3-128">この手順では、旅行プランを XML としてローカル ファイルの場所にエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="961e3-128">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="961e3-129">行程データベースの代わりにスケジュールをローカル ファイルの場所にエクスポートして、ESB のテスト用クライアント アプリケーションを使用してスケジュールのテストが可能です。</span><span class="sxs-lookup"><span data-stu-id="961e3-129">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="961e3-130">この操作方法に関するトピックの後半には、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="961e3-130">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="961e3-131">旅行プランの構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="961e3-131">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="961e3-132">ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。</span><span class="sxs-lookup"><span data-stu-id="961e3-132">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="961e3-133">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="961e3-133">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="961e3-134">をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-134">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="961e3-135">**エクステンダー**ドロップダウン リストでは、をクリックして**ESB サービス拡張機能の導入**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-135">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="961e3-136">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-136">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="961e3-137">**受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-137">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="961e3-138">ツールボックスからドラッグ、**行程サービス**の右側に配置し、デザイン画面に要素をモデル化し、**入口**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="961e3-138">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="961e3-139">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="961e3-139">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="961e3-140">をクリックして、**名前**プロパティ、および入力**MapNAOrderToCNOrder**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-140">Click the **Name** property, and then type **MapNAOrderToCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="961e3-141">**旅行プラン サービスのエクステンダー**ドロップダウン リストでは、をクリックして**旅行プラン サービスの拡張機能をメッセージング**。</span><span class="sxs-lookup"><span data-stu-id="961e3-141">In the **Itinerary Service Extender** drop-down list, click **Messaging Itinerary Service Extension**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="961e3-142">このプロパティは、プロセスが行われる (メッセージング) パイプラインで定義します。</span><span class="sxs-lookup"><span data-stu-id="961e3-142">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="961e3-143">または、プロセスはオーケストレーション内の場所を受け取らない場合は設定、**行程サービス エクステンダー**プロパティを**オーケストレーション スケジュール サービス拡張**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-143">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="961e3-144">**コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、 をクリックし、**受信ハンドラー**。</span><span class="sxs-lookup"><span data-stu-id="961e3-144">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="961e3-145">**サービス名**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB.Services.Transform**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-145">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Transform**.</span></span>  
  
3.  <span data-ttu-id="961e3-146">右クリックし、**リゾルバー**のコレクション、 **MapNAOrderToCNOrder**モデル要素をクリックして**新しいリゾルバーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-146">Right-click the **Resolver** collection of the **MapNAOrderToCNOrder** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="961e3-147">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="961e3-147">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="961e3-148">をクリックして、**名前**プロパティ、および入力**StaticallySpecifyTheMap**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-148">Click the **Name** property, and then type **StaticallySpecifyTheMap**.</span></span>  
  
    2.  <span data-ttu-id="961e3-149">**リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-149">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="961e3-150">**型の変換**ドロップダウン リストでは、をクリックして**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-150">In the **Transform Type** drop-down list, click **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span></span>  
  
    4.  <span data-ttu-id="961e3-151">**TransportName**ドロップダウン リストでは、をクリックして**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-151">In the **TransportName** drop-down list, click **FILE**.</span></span>  
  
4.  <span data-ttu-id="961e3-152">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-152">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="961e3-153">接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **MapNAOrderToCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="961e3-153">Drag a connection from the **ReceiveNAOrder** model element to the **MapNAOrderToCNOrder** model element.</span></span>  
  
5.  <span data-ttu-id="961e3-154">ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **MapNAOrderToCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="961e3-154">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **MapNAOrderToCNOrder** model element.</span></span> <span data-ttu-id="961e3-155">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="961e3-155">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="961e3-156">をクリックして、**名前**プロパティ、および入力**SendCNOrder**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-156">Click the **Name** property, and then type **SendCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="961e3-157">**エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB サービス拡張**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-157">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="961e3-158">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-158">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="961e3-159">**送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-159">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
6.  <span data-ttu-id="961e3-160">ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **MapNAOrderToCNOrder**モデル要素と**SendCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="961e3-160">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **MapNAOrderToCNOrder** model element and the **SendCNOrder** model element.</span></span> <span data-ttu-id="961e3-161">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="961e3-161">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="961e3-162">をクリックして、**名前**プロパティ、および入力**SendPortFilter**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-162">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="961e3-163">**旅行プラン サービスのエクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ旅行プラン サービスの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-163">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="961e3-164">**傾斜オフ**ドロップダウン リストで、展開**SendCNOrder**、順にクリックします**送信ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-164">In the **Off-Ramp** drop-down list, expand **SendCNOrder**, and then click **Send Handlers**.</span></span>  
  
7.  <span data-ttu-id="961e3-165">右クリックし、**リゾルバー**のコレクション、 **SendPortFilter**モデル要素をクリックして**新しいリゾルバーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-165">Right-click the **Resolver** collection of the **SendPortFilter** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="961e3-166">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="961e3-166">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="961e3-167">をクリックして、**名前**プロパティ、および入力**ConfigureFolderSettings**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-167">Click the **Name** property, and then type **ConfigureFolderSettings**.</span></span>  
  
    2.  <span data-ttu-id="961e3-168">**リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-168">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="961e3-169">**トランスポート名**ドロップダウン リストでは、をクリックして**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-169">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="961e3-170">をクリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\BAM%MessageID%.xml**</span><span class="sxs-lookup"><span data-stu-id="961e3-170">Click the **Transport Location** property, and then type **C:\HowTos\Out\BAM%MessageID%.xml**</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="961e3-171">各オフ-ごとの傾斜増加はそれに関連付けられているスケジュールのサービスにはスケジュール サービスのプロパティとオフ ランプのプロパティの組み合わせでは、動的送信ポートのサブスクリプションを定義します。</span><span class="sxs-lookup"><span data-stu-id="961e3-171">Each off-ramp will have an itinerary service associated with it; the combination of the itinerary service properties and the properties of the off-ramp define the subscription of the dynamic send port.</span></span>  
  
8.  <span data-ttu-id="961e3-172">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-172">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="961e3-173">接続をドラッグして、 **MapNAOrderToCNOrder**モデル要素に、 **SendPortFilter**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="961e3-173">Drag a connection from the **MapNAOrderToCNOrder** model element to the **SendPortFilter** model element.</span></span>  
  
9. <span data-ttu-id="961e3-174">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-174">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="961e3-175">接続をドラッグして、 **SendPortFilter**モデル要素に、 **SendCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="961e3-175">Drag a connection from the **SendPortFilter** model element to the **SendCNOrder** model element.</span></span>  
  
10. <span data-ttu-id="961e3-176">すべてのプロジェクト成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="961e3-176">Save all project artifacts.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="961e3-177">手順</span><span class="sxs-lookup"><span data-stu-id="961e3-177">Steps</span></span>  
  
#### <a name="to-modify-the-itinerary"></a><span data-ttu-id="961e3-178">旅行プランを変更するには</span><span class="sxs-lookup"><span data-stu-id="961e3-178">To modify the itinerary</span></span>  
  
1.  <span data-ttu-id="961e3-179">Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="961e3-179">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="961e3-180">ソリューション エクスプ ローラーでダブルクリック**BamTracking.itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-180">In Solution Explorer, double-click **BamTracking.itinerary**.</span></span>  
  
3.  <span data-ttu-id="961e3-181">をクリックして、 **MapNAOrderToCNOrder**スケジュール サービス要素。</span><span class="sxs-lookup"><span data-stu-id="961e3-181">Click the **MapNAOrderToCNOrder** itinerary service element.</span></span>  
  
4.  <span data-ttu-id="961e3-182">**MapNAOrderToCNOrder**プロパティ ウィンドウで、をクリックして**True**で、**追跡が有効になっている**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="961e3-182">In the **MapNAOrderToCNOrder** Properties window, click **True** in the **Tracking Enabled** drop-down list.</span></span>  
  
5.  <span data-ttu-id="961e3-183">をクリックして、 **SendPortFilter**スケジュール サービス要素。</span><span class="sxs-lookup"><span data-stu-id="961e3-183">Click the **SendPortFilter** itinerary service element.</span></span>  
  
6.  <span data-ttu-id="961e3-184">**SendPortFilter**プロパティ ウィンドウで、をクリックして**True**で、**追跡が有効になっている**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="961e3-184">In the **SendPortFilter** Properties window, click **True** in the **Tracking Enabled** drop-down list.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="961e3-185">旅行プランのテスト クライアントで使用するモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="961e3-185">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="961e3-186">Visual Studio でのデザイン画面を右クリックし、 **BamTracking**旅行プランをクリックして**モデルのエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-186">In Visual Studio, right-click the design surface of the **BamTracking** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="961e3-187">旅行プランの XML バージョンは、Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="961e3-187">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="961e3-188">すべてのプロジェクト成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="961e3-188">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="961e3-189">Windows エクスプ ローラーでは、C:\HowTos\Itineraries を参照し、旅行プラン XML (BamTracking.xml) の作成に注意してください。</span><span class="sxs-lookup"><span data-stu-id="961e3-189">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (BamTracking.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="961e3-190">旅行プランをテストするには</span><span class="sxs-lookup"><span data-stu-id="961e3-190">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="961e3-191">中に作成されたショートカットを使用してスケジュールのテスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB します。Itinerary.Test.exe - ショートカット)。</span><span class="sxs-lookup"><span data-stu-id="961e3-191">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="961e3-192">行程テスト クライアントでオフ、 **WCF サービスを使用して**チェック ボックスをオンにし**ロード行程**。</span><span class="sxs-lookup"><span data-stu-id="961e3-192">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="961e3-193">**行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="961e3-193">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="961e3-194">選択**BamTracking.xml**、順にクリックします**オープン**旅行プランを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="961e3-194">Select **BamTracking.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="961e3-195">をクリックして**OK**をオフに、**旅行プランは正常に読み込まれる**メッセージ。</span><span class="sxs-lookup"><span data-stu-id="961e3-195">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="961e3-196">旅行プランのテスト クライアントで、横にある省略記号ボタン (…) をクリックします。、**ロード メッセージ**ボックス。</span><span class="sxs-lookup"><span data-stu-id="961e3-196">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="961e3-197">**を読み込む XML ドキュメントの選択** ダイアログ ボックスで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="961e3-197">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="961e3-198">選択**NAOrderDoc.xml**、順にクリックします**オープン**テスト メッセージを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="961e3-198">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="961e3-199">をクリックして、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="961e3-199">Click the **Submit Request** button.</span></span> <span data-ttu-id="961e3-200">テストが完了したら、クリックして**OK**表示される確認メッセージを無視します。</span><span class="sxs-lookup"><span data-stu-id="961e3-200">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="961e3-201">Windows エクスプ ローラーでは、C:\HowTos\Out を参照します。BAM%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="961e3-201">In Windows Explorer, browse to C:\HowTos\Out. Verify that the BAM%MessageID%.xml message has been written to the directory.</span></span>  
  
#### <a name="to-verify-message-tracking"></a><span data-ttu-id="961e3-202">メッセージの追跡を確認するには</span><span class="sxs-lookup"><span data-stu-id="961e3-202">To verify message tracking</span></span>  
  
1. <span data-ttu-id="961e3-203">クリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント[!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]、順にクリックします**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="961e3-203">Click **Start** on the taskbar, point to **All Programs**, point to [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)], and then click **SQL Server Management Studio**.</span></span>  
  
2. <span data-ttu-id="961e3-204">**[新しいクエリ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="961e3-204">Click **New Query**.</span></span>  
  
3. <span data-ttu-id="961e3-205">クエリ ペインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="961e3-205">In the query pane, type the following:</span></span>  
  
   ```  
   SELECT *  
   FROM [BAMPrimaryImport].[dbo].[bam_ItineraryServiceActivity_Completed]  
   GO  
   ```  
  
4. <span data-ttu-id="961e3-206">**[実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="961e3-206">Click **Execute**.</span></span>  
  
5. <span data-ttu-id="961e3-207">結果ウィンドウで、使用して、**タイムスタンプ**最新のエントリを検索する列。</span><span class="sxs-lookup"><span data-stu-id="961e3-207">In the Results pane, use the **TimeStamp** column to locate the most recent entry.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="961e3-208">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="961e3-208">Additional Resources</span></span>  
 <span data-ttu-id="961e3-209">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="961e3-209">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="961e3-210">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="961e3-210">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="961e3-211">メッセージ ルーティング パターン</span><span class="sxs-lookup"><span data-stu-id="961e3-211">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)  
  
-   [<span data-ttu-id="961e3-212">動的な解決とルーティングを利用する</span><span class="sxs-lookup"><span data-stu-id="961e3-212">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)