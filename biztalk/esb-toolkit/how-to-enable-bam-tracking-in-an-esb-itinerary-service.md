---
title: "方法: ESB Itinerary サービスで BAM の追跡を有効にする |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58859937-f8d0-4c33-9a7a-62fec8441936
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6245ec69e1c8224ccbe9a39c3c2be9eea9237ee8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-bam-tracking-in-an-esb-itinerary-service"></a><span data-ttu-id="9aee3-102">方法: ESB Itinerary サービスで BAM の追跡を有効にします。</span><span class="sxs-lookup"><span data-stu-id="9aee3-102">How to: Enable BAM Tracking in an ESB Itinerary Service</span></span>
## <a name="goal"></a><span data-ttu-id="9aee3-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="9aee3-103">Goal</span></span>  
 <span data-ttu-id="9aee3-104">このセクションでは、ビジネス アクティビティ監視 (BAM) が既存旅程を追跡を有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-104">This section demonstrates how to enable Business Activity Monitor (BAM) tracking for an existing itinerary.</span></span>  
  
 <span data-ttu-id="9aee3-105">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="9aee3-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="9aee3-106">ビジネスの利用状況モニターを使用してサービスを旅程を追跡するために使用されるプロパティを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9aee3-106">Enable the property used for tracking Itinerary Services using Business Activity Monitor.</span></span>  
  
-   <span data-ttu-id="9aee3-107">行程テスト用クライアントのサンプル アプリケーションを使用して BAM の追跡をテストします。</span><span class="sxs-lookup"><span data-stu-id="9aee3-107">Test BAM tracking using the Itinerary Test Client sample application.</span></span>  
  
-   <span data-ttu-id="9aee3-108">SQL クエリを使用して、BAM の結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-108">Verify the BAM results using a SQL query.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9aee3-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="9aee3-109">Prerequisites</span></span>  
 <span data-ttu-id="9aee3-110">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="9aee3-111">はじめに</span><span class="sxs-lookup"><span data-stu-id="9aee3-111">Before You Begin</span></span>  
 <span data-ttu-id="9aee3-112">このトピックの「操作方法に関する手順を実行する前に、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-112">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
-   <span data-ttu-id="9aee3-113">ESB itinerary ドメイン固有言語 (DSL) モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-113">Create an ESB itinerary domain-specific language (DSL) model.</span></span>  
  
-   <span data-ttu-id="9aee3-114">旅行計画のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-114">Configure the properties of the itinerary.</span></span>  
  
-   <span data-ttu-id="9aee3-115">旅行計画の構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-115">Define the structure of the itinerary.</span></span>  
  
 <span data-ttu-id="9aee3-116">次の手順では、これらの各を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-116">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="9aee3-117">ESB itinerary DSL モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="9aee3-117">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="9aee3-118">[!INCLUDE[vs2010](../includes/vs2010-md.md)]C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="9aee3-118">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="9aee3-119">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-119">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="9aee3-120">**新しい項目の追加**ダイアログ ボックスで、をクリックして**ItineraryDsl**テンプレート ペインでします。</span><span class="sxs-lookup"><span data-stu-id="9aee3-120">In the **Add New Item** dialog box, click  **ItineraryDsl** in the Templates pane.</span></span>  
  
4.  <span data-ttu-id="9aee3-121">**名前**ボックスに、入力**BamTracking**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-121">In the **Name** box, type **BamTracking**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="9aee3-122">旅行計画のプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="9aee3-122">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="9aee3-123">Visual Studio でのデザイン画面をクリックして**BamTracking.itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-123">In Visual Studio, click the design surface of **BamTracking.itinerary**.</span></span> <span data-ttu-id="9aee3-124">**BamTracking**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-124">In the **BamTracking** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9aee3-125">**モデル エクスポーター**ドロップダウン リストをクリックして**XML 行程エクスポーター**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-125">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="9aee3-126">**Extender 設定**セクションで、横に、**行程 XML ファイル**プロパティ、省略記号ボタン (...) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9aee3-126">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="9aee3-127">**XML ファイルの** ダイアログ ボックスで、**ファイル名**ボックスに、入力**C:\HowTos\Itineraries\BamTracking**  をクリックし、**保存**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-127">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\BamTracking** and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="9aee3-128">この手順では、旅行計画をローカル ファイルの場所に XML としてエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="9aee3-128">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="9aee3-129">代わりに、ローカル ファイルの場所に日程を itinerary のデータベースにエクスポートして ESB のテスト用クライアント アプリケーションを使用して旅行計画のテストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9aee3-129">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="9aee3-130">このトピックの後半には、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-130">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="9aee3-131">旅行計画の構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="9aee3-131">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="9aee3-132">ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。</span><span class="sxs-lookup"><span data-stu-id="9aee3-132">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="9aee3-133">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-133">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9aee3-134">クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-134">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="9aee3-135">**Extender**ドロップダウン リストをクリックして**入り口 ESB サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-135">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="9aee3-136">**BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-136">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="9aee3-137">**受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-137">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="9aee3-138">ツールボックスからドラッグ、**行程サービス**デザイン画面に要素をモデル化の右側に配置し、**入り口**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="9aee3-138">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="9aee3-139">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-139">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9aee3-140">クリックして、**名前**プロパティ、および入力**MapNAOrderToCNOrder**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-140">Click the **Name** property, and then type **MapNAOrderToCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="9aee3-141">**行程サービス エクステンダー**ドロップダウン リストをクリックして**行程サービス拡張のメッセージング**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-141">In the **Itinerary Service Extender** drop-down list, click **Messaging Itinerary Service Extension**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="9aee3-142">このプロパティは、あるプロセスで行われます (メッセージング) パイプラインを定義します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-142">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="9aee3-143">または、プロセスは、オーケストレーションで行われます、設定、**行程サービス エクステンダー**プロパティを**オーケストレーション行程サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-143">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="9aee3-144">**コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-144">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="9aee3-145">**サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Transform**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-145">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Transform**.</span></span>  
  
3.  <span data-ttu-id="9aee3-146">右クリックし、**リゾルバー**のコレクション、 **MapNAOrderToCNOrder**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-146">Right-click the **Resolver** collection of the **MapNAOrderToCNOrder** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="9aee3-147">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-147">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9aee3-148">クリックして、**名前**プロパティ、および入力**StaticallySpecifyTheMap**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-148">Click the **Name** property, and then type **StaticallySpecifyTheMap**.</span></span>  
  
    2.  <span data-ttu-id="9aee3-149">**リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-149">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="9aee3-150">**型の変換**ドロップダウン リストをクリックして**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-150">In the **Transform Type** drop-down list, click **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span></span>  
  
    4.  <span data-ttu-id="9aee3-151">**TransportName**ドロップダウン リストをクリックして**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-151">In the **TransportName** drop-down list, click **FILE**.</span></span>  
  
4.  <span data-ttu-id="9aee3-152">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-152">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="9aee3-153">接続をドラッグして、 **ReceiveNAOrder**モデル要素を**MapNAOrderToCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="9aee3-153">Drag a connection from the **ReceiveNAOrder** model element to the **MapNAOrderToCNOrder** model element.</span></span>  
  
5.  <span data-ttu-id="9aee3-154">ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **MapNAOrderToCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="9aee3-154">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **MapNAOrderToCNOrder** model element.</span></span> <span data-ttu-id="9aee3-155">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-155">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9aee3-156">クリックして、**名前**プロパティ、および入力**SendCNOrder**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-156">Click the **Name** property, and then type **SendCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="9aee3-157">**Extender**ドロップダウン リストをクリックして**出口 ESB サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-157">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="9aee3-158">**BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-158">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="9aee3-159">**送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-159">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
6.  <span data-ttu-id="9aee3-160">ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **MapNAOrderToCNOrder**モデル要素と**SendCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="9aee3-160">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **MapNAOrderToCNOrder** model element and the **SendCNOrder** model element.</span></span> <span data-ttu-id="9aee3-161">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-161">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9aee3-162">クリックして、**名前**プロパティ、および入力**SendPortFilter**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-162">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="9aee3-163">**行程サービス エクステンダー**ドロップダウン リストをクリックして**出口行程サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-163">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="9aee3-164">**出口**ドロップダウン リストで、展開**SendCNOrder**、クリックして**送信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-164">In the **Off-Ramp** drop-down list, expand **SendCNOrder**, and then click **Send Handlers**.</span></span>  
  
7.  <span data-ttu-id="9aee3-165">右クリックし、**リゾルバー**のコレクション、 **SendPortFilter**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-165">Right-click the **Resolver** collection of the **SendPortFilter** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="9aee3-166">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-166">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="9aee3-167">クリックして、**名前**プロパティ、および入力**ConfigureFolderSettings**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-167">Click the **Name** property, and then type **ConfigureFolderSettings**.</span></span>  
  
    2.  <span data-ttu-id="9aee3-168">**リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-168">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="9aee3-169">**トランスポート名**ドロップダウン リストをクリックして**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-169">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="9aee3-170">クリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\BAM%MessageID%.xml**</span><span class="sxs-lookup"><span data-stu-id="9aee3-170">Click the **Transport Location** property, and then type **C:\HowTos\Out\BAM%MessageID%.xml**</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="9aee3-171">各出口がそれに関連付けられている itinerary サービスされています。itinerary サービスのプロパティと、出口のプロパティの組み合わせでは、動的送信ポートのサブスクリプションを定義します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-171">Each off-ramp will have an itinerary service associated with it; the combination of the itinerary service properties and the properties of the off-ramp define the subscription of the dynamic send port.</span></span>  
  
8.  <span data-ttu-id="9aee3-172">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-172">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="9aee3-173">接続をドラッグして、 **MapNAOrderToCNOrder**モデル要素を**SendPortFilter**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="9aee3-173">Drag a connection from the **MapNAOrderToCNOrder** model element to the **SendPortFilter** model element.</span></span>  
  
9. <span data-ttu-id="9aee3-174">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-174">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="9aee3-175">接続をドラッグして、 **SendPortFilter**モデル要素を**SendCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="9aee3-175">Drag a connection from the **SendPortFilter** model element to the **SendCNOrder** model element.</span></span>  
  
10. <span data-ttu-id="9aee3-176">すべてのプロジェクトの成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-176">Save all project artifacts.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="9aee3-177">手順</span><span class="sxs-lookup"><span data-stu-id="9aee3-177">Steps</span></span>  
  
#### <a name="to-modify-the-itinerary"></a><span data-ttu-id="9aee3-178">旅行計画を変更するには</span><span class="sxs-lookup"><span data-stu-id="9aee3-178">To modify the itinerary</span></span>  
  
1.  <span data-ttu-id="9aee3-179">[!INCLUDE[vs2010](../includes/vs2010-md.md)]C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="9aee3-179">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="9aee3-180">ソリューション エクスプ ローラーで、 **BamTracking.itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-180">In Solution Explorer, double-click **BamTracking.itinerary**.</span></span>  
  
3.  <span data-ttu-id="9aee3-181">クリックして、 **MapNAOrderToCNOrder** itinerary サービス要素。</span><span class="sxs-lookup"><span data-stu-id="9aee3-181">Click the **MapNAOrderToCNOrder** itinerary service element.</span></span>  
  
4.  <span data-ttu-id="9aee3-182">**MapNAOrderToCNOrder**プロパティ ウィンドウでをクリックして**True**で、**追跡が有効になっている**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="9aee3-182">In the **MapNAOrderToCNOrder** Properties window, click **True** in the **Tracking Enabled** drop-down list.</span></span>  
  
5.  <span data-ttu-id="9aee3-183">クリックして、 **SendPortFilter** itinerary サービス要素。</span><span class="sxs-lookup"><span data-stu-id="9aee3-183">Click the **SendPortFilter** itinerary service element.</span></span>  
  
6.  <span data-ttu-id="9aee3-184">**SendPortFilter**プロパティ ウィンドウでをクリックして**True**で、**追跡が有効になっている**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="9aee3-184">In the **SendPortFilter** Properties window, click **True** in the **Tracking Enabled** drop-down list.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="9aee3-185">行程テスト クライアントで使用するモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="9aee3-185">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="9aee3-186">Visual Studio でのデザイン画面を右クリックし、 **BamTracking**行程をクリックして**モデルのエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-186">In Visual Studio, right-click the design surface of the **BamTracking** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9aee3-187">旅行計画の XML バージョンは、Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="9aee3-187">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="9aee3-188">すべてのプロジェクトの成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-188">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="9aee3-189">Windows エクスプローラで、C:\HowTos\Itineraries を参照し、行程 XML (BamTracking.xml) の作成に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9aee3-189">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (BamTracking.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="9aee3-190">旅行計画をテストするには</span><span class="sxs-lookup"><span data-stu-id="9aee3-190">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="9aee3-191">中に作成されたショートカットを使用して行程テスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB です。Itinerary.Test.exe - ショートカット)。</span><span class="sxs-lookup"><span data-stu-id="9aee3-191">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="9aee3-192">行程テスト クライアントで、クリア、**を使用して WCF サービス**チェック ボックスをクリックして**ロード行程**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-192">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="9aee3-193">**行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-193">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="9aee3-194">選択**BamTracking.xml**、順にクリック**開く**日程を読み込めません。</span><span class="sxs-lookup"><span data-stu-id="9aee3-194">Select **BamTracking.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="9aee3-195">をクリックして**OK**をクリアする、**行程が正常に読み込まれる**メッセージ。</span><span class="sxs-lookup"><span data-stu-id="9aee3-195">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="9aee3-196">行程テスト クライアントで、横にある省略記号ボタン (...) をクリックして、**メッセージの読み込み**ボックス。</span><span class="sxs-lookup"><span data-stu-id="9aee3-196">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="9aee3-197">**選択読み込む XML ドキュメントを** ダイアログ ボックスで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-197">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="9aee3-198">選択**NAOrderDoc.xml**、順にクリック**開く**テスト メッセージを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="9aee3-198">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="9aee3-199">クリックして、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9aee3-199">Click the **Submit Request** button.</span></span> <span data-ttu-id="9aee3-200">テストが完了したらをクリックして**OK**表示される確認メッセージを破棄します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-200">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="9aee3-201">Windows エクスプローラで、C:\HowTos\Out を参照します。BAM%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-201">In Windows Explorer, browse to C:\HowTos\Out. Verify that the BAM%MessageID%.xml message has been written to the directory.</span></span>  
  
#### <a name="to-verify-message-tracking"></a><span data-ttu-id="9aee3-202">メッセージの追跡を確認するには</span><span class="sxs-lookup"><span data-stu-id="9aee3-202">To verify message tracking</span></span>  
  
1.  <span data-ttu-id="9aee3-203">をクリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント[!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]、順にクリック**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="9aee3-203">Click **Start** on the taskbar, point to **All Programs**, point to [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)], and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="9aee3-204">**[新しいクエリ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9aee3-204">Click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9aee3-205">クエリ ウィンドウで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="9aee3-205">In the query pane, type the following:</span></span>  
  
    ```  
    SELECT *  
    FROM [BAMPrimaryImport].[dbo].[bam_ItineraryServiceActivity_Completed]  
    GO  
    ```  
  
4.  <span data-ttu-id="9aee3-206">**[実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9aee3-206">Click **Execute**.</span></span>  
  
5.  <span data-ttu-id="9aee3-207">結果ウィンドウで、使用、**タイムスタンプ**最新のエントリを検索する列。</span><span class="sxs-lookup"><span data-stu-id="9aee3-207">In the Results pane, use the **TimeStamp** column to locate the most recent entry.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="9aee3-208">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="9aee3-208">Additional Resources</span></span>  
 <span data-ttu-id="9aee3-209">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9aee3-209">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="9aee3-210">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="9aee3-210">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="9aee3-211">メッセージのルーティング パターン</span><span class="sxs-lookup"><span data-stu-id="9aee3-211">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)  
  
-   [<span data-ttu-id="9aee3-212">動的な解決を使用して、ルーティング</span><span class="sxs-lookup"><span data-stu-id="9aee3-212">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)