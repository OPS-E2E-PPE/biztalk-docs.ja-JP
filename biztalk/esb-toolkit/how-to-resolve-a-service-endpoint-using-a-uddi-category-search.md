---
title: "方法: UDDI カテゴリの検索を使用してサービス エンドポイントを解決するには |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61ac5d37-5529-4509-a948-415453944e01
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3953baf4a60e2863f986ec54fe9c12663b2b587d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-resolve-a-service-endpoint-using-a-uddi-category-search"></a><span data-ttu-id="1fbf7-102">方法: UDDI カテゴリの検索を使用してサービス エンドポイントを解決するには</span><span class="sxs-lookup"><span data-stu-id="1fbf7-102">How to: Resolve a Service Endpoint Using a UDDI Category Search</span></span>
## <a name="goal"></a><span data-ttu-id="1fbf7-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="1fbf7-103">Goal</span></span>  
 <span data-ttu-id="1fbf7-104">このセクションで、ESB デザイナー ドメイン固有言語 (DSL) を使用して、行程ベース回覧 Universal Description, Discovery, を使用するを作成する方法と、カテゴリを使用してサービス エンドポイントを検索する Integration (UDDI) 3 競合回避モジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-104">This section demonstrates how to use the ESB Designer domain-specific language (DSL) to create an itinerary-based routing slip that uses the Universal Description, Discovery, and Integration (UDDI) 3 resolver to locate a service endpoint using a category search.</span></span> <span data-ttu-id="1fbf7-105">このシナリオでは、UDDI で公開されるファイル エンドポイントがサービス エンドポイントになります。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-105">In this scenario, the service endpoint will be a file endpoint published in UDDI.</span></span>  
  
 <span data-ttu-id="1fbf7-106">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="1fbf7-107">サービス エンドポイントを解決するのには itinerary 回覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-107">Create an itinerary routing slip to resolve a service endpoint.</span></span>  
  
-   <span data-ttu-id="1fbf7-108">UDDI 3 競合回避モジュールを使用してサービス エンドポイントにメッセージをルーティングする旅程を構成します。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-108">Configure the itinerary to route the message to a service endpoint using a UDDI 3 resolver.</span></span>  
  
-   <span data-ttu-id="1fbf7-109">行程テスト用クライアントのサンプル アプリケーションを使用して旅程をテストします。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-109">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1fbf7-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="1fbf7-110">Prerequisites</span></span>  
 <span data-ttu-id="1fbf7-111">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-111">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="1fbf7-112">手順</span><span class="sxs-lookup"><span data-stu-id="1fbf7-112">Steps</span></span>  
  
#### <a name="to-create-an-itinerary-model"></a><span data-ttu-id="1fbf7-113">Itinerary モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="1fbf7-113">To create an itinerary model</span></span>  
  
1.  <span data-ttu-id="1fbf7-114">[!INCLUDE[vs2010](../includes/vs2010-md.md)]C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-114">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="1fbf7-115">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-115">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="1fbf7-116">**新しい項目の追加** ダイアログ ボックスで、「 **UDDI3CategorySearch**で、**名前**ボックスをクリックしてして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-116">In the **Add New Item** dialog box, type **UDDI3CategorySearch** in the **Name** box, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="1fbf7-117">旅行計画のプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="1fbf7-117">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="1fbf7-118">Visual Studio でのデザイン画面をクリックして**UDDI3CategorySearch.itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-118">In Visual Studio, click the design surface of **UDDI3CategorySearch.itinerary**.</span></span> <span data-ttu-id="1fbf7-119">**UDDI3CategorySearch**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-119">In the **UDDI3CategorySearch** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1fbf7-120">**モデル エクスポーター**ドロップダウン リストをクリックして**XML 行程エクスポーター**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-120">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="1fbf7-121">下にある、 **Extender の設定**セクションで、次に、**行程 XML ファイル**プロパティ、省略記号ボタン (...) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-121">Under the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="1fbf7-122">**[XML ファイルの**] ダイアログ ボックスで、「 **C:\HowTos\Itineraries\UDDI3CategorySearch**で、**ファイル名**ボックスをクリックして**を保存**.</span><span class="sxs-lookup"><span data-stu-id="1fbf7-122">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\UDDI3CategorySearch** in the **File name** box, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="1fbf7-123">この手順では、旅行計画をローカル ファイルの場所に XML としてエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-123">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="1fbf7-124">代わりに、ローカル ファイルの場所に日程を itinerary のデータベースにエクスポートして ESB のテスト用クライアント アプリケーションを使用して旅行計画のテストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-124">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="1fbf7-125">このトピックの後半には、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-125">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="1fbf7-126">旅行計画の構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="1fbf7-126">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="1fbf7-127">ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-127">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="1fbf7-128">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-128">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1fbf7-129">クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-129">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="1fbf7-130">**Extender**ドロップダウン リストをクリックして**入り口 ESB Extender**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-130">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="1fbf7-131">**BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-131">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="1fbf7-132">**受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-132">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="1fbf7-133">ツールボックスからドラッグして、**行程サービス**デザイン画面にモデル要素。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-133">From the Toolbox, drag an **Itinerary Service** model element to the design surface.</span></span> <span data-ttu-id="1fbf7-134">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-134">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1fbf7-135">クリックして、**名前**プロパティ、および入力**CategoryRoute**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-135">Click the **Name** property, and then type **CategoryRoute**.</span></span>  
  
    2.  <span data-ttu-id="1fbf7-136">**行程サービス エクステンダー**ドロップダウン リストをクリックして**エクステンダーのメッセージング**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-136">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
    3.  <span data-ttu-id="1fbf7-137">**コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-137">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="1fbf7-138">**サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Routing**</span><span class="sxs-lookup"><span data-stu-id="1fbf7-138">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**</span></span>  
  
3.  <span data-ttu-id="1fbf7-139">右クリックし、**リゾルバー**のコレクション、 **CategoryRoute**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-139">Right-click the **Resolver** collection of the **CategoryRoute** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="1fbf7-140">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-140">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1fbf7-141">クリックして、**名前**プロパティ、および入力**CategorySearch**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-141">Click the **Name** property, and then type **CategorySearch**.</span></span>  
  
    2.  <span data-ttu-id="1fbf7-142">**リゾルバーの実装**ドロップダウン リストをクリックして**Uddi3 競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-142">In the **Resolver Implementation** drop-down list, click **Uddi3 Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="1fbf7-143">**リゾルバー モニカー**ドロップダウン リストをクリックして**UDDI3**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-143">In the **Resolver Moniker** drop-down list, click **UDDI3**.</span></span>  
  
    4.  <span data-ttu-id="1fbf7-144">をクリックして、**カテゴリの検索**プロパティ、省略記号ボタン (...) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-144">Click the **Category Search** property, and then click the ellipsis button (…).</span></span>  
  
    5.  <span data-ttu-id="1fbf7-145">**名前値のプロパティ エディター**ダイアログ ボックスで、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-145">In the **Name Value Property Editor** dialog box, click **Add**.</span></span>  
  
    6.  <span data-ttu-id="1fbf7-146">クリックして、**名前**プロパティ、および入力**uddi:esb:biztalkapplication**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-146">Click the **Name** property, and then type **uddi:esb:biztalkapplication**.</span></span>  
  
    7.  <span data-ttu-id="1fbf7-147">クリックして、**値**プロパティ、および入力**GlobalBank.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-147">Click the **Value** property, and then type **GlobalBank.ESB**.</span></span>  
  
    8.  <span data-ttu-id="1fbf7-148">**名前値のプロパティ エディター**ダイアログ ボックスで、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-148">In the **Name Value Property Editor** dialog box, click **Add**.</span></span>  
  
    9. <span data-ttu-id="1fbf7-149">クリックして、**名前**プロパティ、および入力**uddi:esb:portname**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-149">Click the **Name** property, and then type **uddi:esb:portname**.</span></span>  
  
    10. <span data-ttu-id="1fbf7-150">クリックして、**値**プロパティ、および入力**OrderFileServicev3**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-150">Click the **Value** property, and then type **OrderFileServicev3**.</span></span>  
  
    11. <span data-ttu-id="1fbf7-151">**名前値のプロパティ エディター**ダイアログ ボックスで、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-151">In the **Name Value Property Editor** dialog box, click **Add**.</span></span>  
  
    12. <span data-ttu-id="1fbf7-152">クリックして、**名前**プロパティ、および入力**uddi:esb:version**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-152">Click the **Name** property, and then type **uddi:esb:version**.</span></span>  
  
    13. <span data-ttu-id="1fbf7-153">クリックして、**値**プロパティ、および入力**1**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-153">Click the **Value** property, and then type **1**.</span></span>  
  
    14. <span data-ttu-id="1fbf7-154">をクリックして**OK**を閉じる、**名前値のプロパティ エディター**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-154">Click **OK** to close the **Name Value Property Editor** dialog box.</span></span>  
  
4.  <span data-ttu-id="1fbf7-155">右クリックし、 **CategorySearch**リゾルバーをクリックして**テスト構成の競合回避モジュール**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-155">Right-click the **CategorySearch** resolver, and then click **Test Resolver Configuration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1fbf7-156">出力ウィンドウに表示される出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-156">Verify the output displayed in the Output window.</span></span>  
  
5.  <span data-ttu-id="1fbf7-157">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-157">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="1fbf7-158">接続をドラッグして、 **ReceiveNAOrder**モデル要素を**CategoryRoute**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-158">Drag a connection from the **ReceiveNAOrder** model element to the **CategoryRoute** model element.</span></span>  
  
6.  <span data-ttu-id="1fbf7-159">ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **CategoryRoute**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-159">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **CategoryRoute** model element.</span></span> <span data-ttu-id="1fbf7-160">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-160">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1fbf7-161">クリックして、**名前**プロパティ、および入力**SendNAOrder**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-161">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="1fbf7-162">**Extender**ドロップダウン リストをクリックして**出口 ESB Extender**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-162">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="1fbf7-163">**BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-163">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="1fbf7-164">**送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-164">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
7.  <span data-ttu-id="1fbf7-165">ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **CategoryRoute**モデル要素と**SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-165">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **CategoryRoute** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="1fbf7-166">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-166">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1fbf7-167">クリックして、**名前**プロパティ、および入力**SendPortFilter**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-167">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="1fbf7-168">**行程サービス エクステンダー**ドロップダウン リストをクリックして**出口 Extender**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-168">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="1fbf7-169">**出口**ドロップダウン リストで、展開**SendNAOrder**、クリックして**送信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-169">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
8.  <span data-ttu-id="1fbf7-170">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-170">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="1fbf7-171">接続をドラッグして、 **CategoryRoute**モデル要素を**SendPortFilter**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-171">Drag a connection from the **CategoryRoute** model element to the **SendPortFilter** model element.</span></span>  
  
9. <span data-ttu-id="1fbf7-172">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-172">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="1fbf7-173">接続をドラッグして、 **SendPortFilter**モデル要素を**SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-173">Drag a connection from the **SendPortFilter** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="1fbf7-174">行程テスト クライアントで使用するモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="1fbf7-174">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="1fbf7-175">Visual Studio でのデザイン画面を右クリックし、 **UDDI3CategorySearch**行程をクリックして**モデルのエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-175">In Visual Studio, right-click the design surface of the **UDDI3CategorySearch** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1fbf7-176">旅行計画の XML バージョンは、Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-176">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="1fbf7-177">すべてのプロジェクトの成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-177">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="1fbf7-178">Windows エクスプローラで、C:\HowTos\Itineraries を参照し、行程 XML (UDDI3CategorySearch.xml) の作成に注意してください。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-178">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (UDDI3CategorySearch.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="1fbf7-179">旅行計画をテストするには</span><span class="sxs-lookup"><span data-stu-id="1fbf7-179">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="1fbf7-180">中に作成されたショートカットを使用して行程テスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB です。Itinerary.Test.exe - ショートカット)。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-180">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="1fbf7-181">行程テスト クライアントで、クリア、**を使用して WCF サービス**チェック ボックスをクリックして**ロード行程**です。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-181">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="1fbf7-182">**行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-182">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="1fbf7-183">選択**UDDI3CategorySearch.xml**、順にクリック**開く**日程を読み込めません。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-183">Select **UDDI3CategorySearch.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="1fbf7-184">をクリックして**OK**をクリアする、**行程が正常に読み込まれる**メッセージ。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-184">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="1fbf7-185">行程テスト クライアントで、横にある省略記号ボタン (...) をクリックして、**メッセージの読み込み**ボックス。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-185">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="1fbf7-186">**選択読み込む XML ドキュメントを** ダイアログ ボックスで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-186">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="1fbf7-187">NAOrderDoc.xml を選択し、クリックして**開く**テスト メッセージを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-187">Select NAOrderDoc.xml, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="1fbf7-188">クリックして、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-188">Click the **Submit Request** button.</span></span> <span data-ttu-id="1fbf7-189">テストが完了したらをクリックして**OK**表示される確認メッセージを破棄します。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-189">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="1fbf7-190">Windows エクスプ ローラーで参照**C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out**ことを確認し、 **%MessageID%.xml**にメッセージが書き込まれた、ディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-190">In Windows Explorer, browse to **C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out** and verify that the **%MessageID%.xml** message has been written to the directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="1fbf7-191">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="1fbf7-191">Additional Resources</span></span>  
 <span data-ttu-id="1fbf7-192">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fbf7-192">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="1fbf7-193">方法: キーの検索をバインド UDDI を使用してサービス エンドポイントを解決するには</span><span class="sxs-lookup"><span data-stu-id="1fbf7-193">How to: Resolve a Service Endpoint Using a UDDI Binding Key Search</span></span>](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search.md)  
  
-   [<span data-ttu-id="1fbf7-194">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="1fbf7-194">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="1fbf7-195">動的な解決を使用して、ルーティング</span><span class="sxs-lookup"><span data-stu-id="1fbf7-195">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)