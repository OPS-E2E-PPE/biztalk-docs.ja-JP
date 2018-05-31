---
title: '方法: ESB Itinerary サービスで BAM の追跡を有効にする |Microsoft ドキュメント'
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
ms.openlocfilehash: 011de667e06f4275fe75a28b6566a6bc393cf841
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009627"
---
# <a name="how-to-enable-bam-tracking-in-an-esb-itinerary-service"></a><span data-ttu-id="1f9f4-102">方法: ESB Itinerary サービスで BAM の追跡を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-102">How to: Enable BAM Tracking in an ESB Itinerary Service</span></span>
## <a name="goal"></a><span data-ttu-id="1f9f4-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="1f9f4-103">Goal</span></span>  
 <span data-ttu-id="1f9f4-104">このセクションでは、ビジネス アクティビティ監視 (BAM) が既存旅程を追跡を有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-104">This section demonstrates how to enable Business Activity Monitor (BAM) tracking for an existing itinerary.</span></span>  
  
 <span data-ttu-id="1f9f4-105">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="1f9f4-106">ビジネスの利用状況モニターを使用してサービスを旅程を追跡するために使用されるプロパティを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-106">Enable the property used for tracking Itinerary Services using Business Activity Monitor.</span></span>  
  
-   <span data-ttu-id="1f9f4-107">行程テスト用クライアントのサンプル アプリケーションを使用して BAM の追跡をテストします。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-107">Test BAM tracking using the Itinerary Test Client sample application.</span></span>  
  
-   <span data-ttu-id="1f9f4-108">SQL クエリを使用して、BAM の結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-108">Verify the BAM results using a SQL query.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1f9f4-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="1f9f4-109">Prerequisites</span></span>  
 <span data-ttu-id="1f9f4-110">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="1f9f4-111">はじめに</span><span class="sxs-lookup"><span data-stu-id="1f9f4-111">Before You Begin</span></span>  
 <span data-ttu-id="1f9f4-112">このトピックの「操作方法に関する手順を実行する前に、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-112">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
-   <span data-ttu-id="1f9f4-113">ESB itinerary ドメイン固有言語 (DSL) モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-113">Create an ESB itinerary domain-specific language (DSL) model.</span></span>  
  
-   <span data-ttu-id="1f9f4-114">旅行計画のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-114">Configure the properties of the itinerary.</span></span>  
  
-   <span data-ttu-id="1f9f4-115">旅行計画の構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-115">Define the structure of the itinerary.</span></span>  
  
 <span data-ttu-id="1f9f4-116">次の手順では、これらの各を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-116">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="1f9f4-117">ESB itinerary DSL モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="1f9f4-117">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="1f9f4-118">Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-118">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="1f9f4-119">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-119">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="1f9f4-120">**新しい項目の追加**ダイアログ ボックスで、をクリックして**ItineraryDsl**テンプレート ペインでします。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-120">In the **Add New Item** dialog box, click  **ItineraryDsl** in the Templates pane.</span></span>  
  
4.  <span data-ttu-id="1f9f4-121">**名前**ボックスに、入力**BamTracking**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-121">In the **Name** box, type **BamTracking**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="1f9f4-122">旅行計画のプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="1f9f4-122">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="1f9f4-123">Visual Studio でのデザイン画面をクリックして**BamTracking.itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-123">In Visual Studio, click the design surface of **BamTracking.itinerary**.</span></span> <span data-ttu-id="1f9f4-124">**BamTracking**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-124">In the **BamTracking** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1f9f4-125">**モデル エクスポーター**ドロップダウン リストをクリックして**XML 行程エクスポーター**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-125">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="1f9f4-126">**Extender 設定**セクションで、横に、**行程 XML ファイル**プロパティ、省略記号ボタン (...) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-126">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="1f9f4-127">**XML ファイルの** ダイアログ ボックスで、**ファイル名**ボックスに、入力**C:\HowTos\Itineraries\BamTracking**  をクリックし、**保存**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-127">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\BamTracking** and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="1f9f4-128">この手順では、旅行計画をローカル ファイルの場所に XML としてエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-128">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="1f9f4-129">代わりに、ローカル ファイルの場所に日程を itinerary のデータベースにエクスポートして ESB のテスト用クライアント アプリケーションを使用して旅行計画のテストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-129">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="1f9f4-130">このトピックの後半には、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-130">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="1f9f4-131">旅行計画の構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="1f9f4-131">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="1f9f4-132">ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-132">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="1f9f4-133">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-133">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1f9f4-134">クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-134">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="1f9f4-135">**Extender**ドロップダウン リストをクリックして**入り口 ESB サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-135">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="1f9f4-136">**BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-136">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="1f9f4-137">**受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-137">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="1f9f4-138">ツールボックスからドラッグ、**行程サービス**デザイン画面に要素をモデル化の右側に配置し、**入り口**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-138">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="1f9f4-139">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-139">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1f9f4-140">クリックして、**名前**プロパティ、および入力**MapNAOrderToCNOrder**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-140">Click the **Name** property, and then type **MapNAOrderToCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="1f9f4-141">**行程サービス エクステンダー**ドロップダウン リストをクリックして**行程サービス拡張のメッセージング**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-141">In the **Itinerary Service Extender** drop-down list, click **Messaging Itinerary Service Extension**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="1f9f4-142">このプロパティは、あるプロセスで行われます (メッセージング) パイプラインを定義します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-142">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="1f9f4-143">または、プロセスは、オーケストレーションで行われます、設定、**行程サービス エクステンダー**プロパティを**オーケストレーション行程サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-143">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="1f9f4-144">**コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-144">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="1f9f4-145">**サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Transform**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-145">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Transform**.</span></span>  
  
3.  <span data-ttu-id="1f9f4-146">右クリックし、**リゾルバー**のコレクション、 **MapNAOrderToCNOrder**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-146">Right-click the **Resolver** collection of the **MapNAOrderToCNOrder** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="1f9f4-147">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-147">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1f9f4-148">クリックして、**名前**プロパティ、および入力**StaticallySpecifyTheMap**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-148">Click the **Name** property, and then type **StaticallySpecifyTheMap**.</span></span>  
  
    2.  <span data-ttu-id="1f9f4-149">**リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-149">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="1f9f4-150">**型の変換**ドロップダウン リストをクリックして**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-150">In the **Transform Type** drop-down list, click **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span></span>  
  
    4.  <span data-ttu-id="1f9f4-151">**TransportName**ドロップダウン リストをクリックして**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-151">In the **TransportName** drop-down list, click **FILE**.</span></span>  
  
4.  <span data-ttu-id="1f9f4-152">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-152">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="1f9f4-153">接続をドラッグして、 **ReceiveNAOrder**モデル要素を**MapNAOrderToCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-153">Drag a connection from the **ReceiveNAOrder** model element to the **MapNAOrderToCNOrder** model element.</span></span>  
  
5.  <span data-ttu-id="1f9f4-154">ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **MapNAOrderToCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-154">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **MapNAOrderToCNOrder** model element.</span></span> <span data-ttu-id="1f9f4-155">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-155">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1f9f4-156">クリックして、**名前**プロパティ、および入力**SendCNOrder**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-156">Click the **Name** property, and then type **SendCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="1f9f4-157">**Extender**ドロップダウン リストをクリックして**出口 ESB サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-157">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="1f9f4-158">**BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-158">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="1f9f4-159">**送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-159">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
6.  <span data-ttu-id="1f9f4-160">ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **MapNAOrderToCNOrder**モデル要素と**SendCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-160">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **MapNAOrderToCNOrder** model element and the **SendCNOrder** model element.</span></span> <span data-ttu-id="1f9f4-161">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-161">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1f9f4-162">クリックして、**名前**プロパティ、および入力**SendPortFilter**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-162">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="1f9f4-163">**行程サービス エクステンダー**ドロップダウン リストをクリックして**出口行程サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-163">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="1f9f4-164">**出口**ドロップダウン リストで、展開**SendCNOrder**、クリックして**送信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-164">In the **Off-Ramp** drop-down list, expand **SendCNOrder**, and then click **Send Handlers**.</span></span>  
  
7.  <span data-ttu-id="1f9f4-165">右クリックし、**リゾルバー**のコレクション、 **SendPortFilter**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-165">Right-click the **Resolver** collection of the **SendPortFilter** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="1f9f4-166">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-166">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1f9f4-167">クリックして、**名前**プロパティ、および入力**ConfigureFolderSettings**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-167">Click the **Name** property, and then type **ConfigureFolderSettings**.</span></span>  
  
    2.  <span data-ttu-id="1f9f4-168">**リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-168">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="1f9f4-169">**トランスポート名**ドロップダウン リストをクリックして**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-169">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="1f9f4-170">クリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\BAM%MessageID%.xml**</span><span class="sxs-lookup"><span data-stu-id="1f9f4-170">Click the **Transport Location** property, and then type **C:\HowTos\Out\BAM%MessageID%.xml**</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="1f9f4-171">各出口がそれに関連付けられている itinerary サービスされています。itinerary サービスのプロパティと、出口のプロパティの組み合わせでは、動的送信ポートのサブスクリプションを定義します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-171">Each off-ramp will have an itinerary service associated with it; the combination of the itinerary service properties and the properties of the off-ramp define the subscription of the dynamic send port.</span></span>  
  
8.  <span data-ttu-id="1f9f4-172">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-172">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="1f9f4-173">接続をドラッグして、 **MapNAOrderToCNOrder**モデル要素を**SendPortFilter**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-173">Drag a connection from the **MapNAOrderToCNOrder** model element to the **SendPortFilter** model element.</span></span>  
  
9. <span data-ttu-id="1f9f4-174">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-174">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="1f9f4-175">接続をドラッグして、 **SendPortFilter**モデル要素を**SendCNOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-175">Drag a connection from the **SendPortFilter** model element to the **SendCNOrder** model element.</span></span>  
  
10. <span data-ttu-id="1f9f4-176">すべてのプロジェクトの成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-176">Save all project artifacts.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="1f9f4-177">手順</span><span class="sxs-lookup"><span data-stu-id="1f9f4-177">Steps</span></span>  
  
#### <a name="to-modify-the-itinerary"></a><span data-ttu-id="1f9f4-178">旅行計画を変更するには</span><span class="sxs-lookup"><span data-stu-id="1f9f4-178">To modify the itinerary</span></span>  
  
1.  <span data-ttu-id="1f9f4-179">Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-179">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="1f9f4-180">ソリューション エクスプ ローラーで、 **BamTracking.itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-180">In Solution Explorer, double-click **BamTracking.itinerary**.</span></span>  
  
3.  <span data-ttu-id="1f9f4-181">クリックして、 **MapNAOrderToCNOrder** itinerary サービス要素。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-181">Click the **MapNAOrderToCNOrder** itinerary service element.</span></span>  
  
4.  <span data-ttu-id="1f9f4-182">**MapNAOrderToCNOrder**プロパティ ウィンドウでをクリックして**True**で、**追跡が有効になっている**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-182">In the **MapNAOrderToCNOrder** Properties window, click **True** in the **Tracking Enabled** drop-down list.</span></span>  
  
5.  <span data-ttu-id="1f9f4-183">クリックして、 **SendPortFilter** itinerary サービス要素。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-183">Click the **SendPortFilter** itinerary service element.</span></span>  
  
6.  <span data-ttu-id="1f9f4-184">**SendPortFilter**プロパティ ウィンドウでをクリックして**True**で、**追跡が有効になっている**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-184">In the **SendPortFilter** Properties window, click **True** in the **Tracking Enabled** drop-down list.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="1f9f4-185">行程テスト クライアントで使用するモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="1f9f4-185">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="1f9f4-186">Visual Studio でのデザイン画面を右クリックし、 **BamTracking**行程をクリックして**モデルのエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-186">In Visual Studio, right-click the design surface of the **BamTracking** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1f9f4-187">旅行計画の XML バージョンは、Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-187">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="1f9f4-188">すべてのプロジェクトの成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-188">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="1f9f4-189">Windows エクスプローラで、C:\HowTos\Itineraries を参照し、行程 XML (BamTracking.xml) の作成に注意してください。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-189">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (BamTracking.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="1f9f4-190">旅行計画をテストするには</span><span class="sxs-lookup"><span data-stu-id="1f9f4-190">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="1f9f4-191">中に作成されたショートカットを使用して行程テスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB です。Itinerary.Test.exe - ショートカット)。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-191">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="1f9f4-192">行程テスト クライアントで、クリア、**を使用して WCF サービス**チェック ボックスをクリックして**ロード行程**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-192">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="1f9f4-193">**行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-193">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="1f9f4-194">選択**BamTracking.xml**、順にクリック**開く**日程を読み込めません。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-194">Select **BamTracking.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="1f9f4-195">をクリックして**OK**をクリアする、**行程が正常に読み込まれる**メッセージ。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-195">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="1f9f4-196">行程テスト クライアントで、横にある省略記号ボタン (...) をクリックして、**メッセージの読み込み**ボックス。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-196">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="1f9f4-197">**選択読み込む XML ドキュメントを** ダイアログ ボックスで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-197">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="1f9f4-198">選択**NAOrderDoc.xml**、順にクリック**開く**テスト メッセージを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-198">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="1f9f4-199">クリックして、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-199">Click the **Submit Request** button.</span></span> <span data-ttu-id="1f9f4-200">テストが完了したらをクリックして**OK**表示される確認メッセージを破棄します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-200">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="1f9f4-201">Windows エクスプローラで、C:\HowTos\Out を参照します。BAM%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-201">In Windows Explorer, browse to C:\HowTos\Out. Verify that the BAM%MessageID%.xml message has been written to the directory.</span></span>  
  
#### <a name="to-verify-message-tracking"></a><span data-ttu-id="1f9f4-202">メッセージの追跡を確認するには</span><span class="sxs-lookup"><span data-stu-id="1f9f4-202">To verify message tracking</span></span>  
  
1.  <span data-ttu-id="1f9f4-203">をクリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント[!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]、順にクリック**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-203">Click **Start** on the taskbar, point to **All Programs**, point to [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)], and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="1f9f4-204">**[新しいクエリ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-204">Click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1f9f4-205">クエリ ウィンドウで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-205">In the query pane, type the following:</span></span>  
  
    ```  
    SELECT *  
    FROM [BAMPrimaryImport].[dbo].[bam_ItineraryServiceActivity_Completed]  
    GO  
    ```  
  
4.  <span data-ttu-id="1f9f4-206">**[実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-206">Click **Execute**.</span></span>  
  
5.  <span data-ttu-id="1f9f4-207">結果ウィンドウで、使用、**タイムスタンプ**最新のエントリを検索する列。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-207">In the Results pane, use the **TimeStamp** column to locate the most recent entry.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="1f9f4-208">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="1f9f4-208">Additional Resources</span></span>  
 <span data-ttu-id="1f9f4-209">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f9f4-209">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="1f9f4-210">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="1f9f4-210">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="1f9f4-211">メッセージ ルーティング パターン</span><span class="sxs-lookup"><span data-stu-id="1f9f4-211">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)  
  
-   [<span data-ttu-id="1f9f4-212">動的な解決とルーティングを利用する</span><span class="sxs-lookup"><span data-stu-id="1f9f4-212">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)