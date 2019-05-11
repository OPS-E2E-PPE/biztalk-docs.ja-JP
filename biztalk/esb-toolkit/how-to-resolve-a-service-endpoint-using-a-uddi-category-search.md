---
title: 操作方法:UDDI カテゴリ検索を使用してサービス エンドポイントを解決する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 61ac5d37-5529-4509-a948-415453944e01
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa3f0d054af872e0ac04338355c34c03b0139f5f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258417"
---
# <a name="how-to-resolve-a-service-endpoint-using-a-uddi-category-search"></a><span data-ttu-id="1a898-102">操作方法:UDDI カテゴリ検索を使用してサービス エンドポイントを解決するには</span><span class="sxs-lookup"><span data-stu-id="1a898-102">How to: Resolve a Service Endpoint Using a UDDI Category Search</span></span>
## <a name="goal"></a><span data-ttu-id="1a898-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="1a898-103">Goal</span></span>  
 <span data-ttu-id="1a898-104">このセクションで、ESB デザイナー ドメイン固有言語 (DSL) を使用して、スケジュールに基づくルーティング スリップ Universal Description, Discovery, を使用するを作成する方法とカテゴリを使用してサービス エンドポイントを検索する Integration (UDDI) 3 競合回避モジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="1a898-104">This section demonstrates how to use the ESB Designer domain-specific language (DSL) to create an itinerary-based routing slip that uses the Universal Description, Discovery, and Integration (UDDI) 3 resolver to locate a service endpoint using a category search.</span></span> <span data-ttu-id="1a898-105">このシナリオでは、UDDI で公開されているファイルのエンドポイントがサービス エンドポイントになります。</span><span class="sxs-lookup"><span data-stu-id="1a898-105">In this scenario, the service endpoint will be a file endpoint published in UDDI.</span></span>  
  
 <span data-ttu-id="1a898-106">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="1a898-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="1a898-107">サービス エンドポイントを解決するのにはのスケジュール ルーティング スリップを作成します。</span><span class="sxs-lookup"><span data-stu-id="1a898-107">Create an itinerary routing slip to resolve a service endpoint.</span></span>  
  
-   <span data-ttu-id="1a898-108">UDDI 3 競合回避モジュールを使用してサービス エンドポイントにメッセージをルーティングするスケジュールを構成します。</span><span class="sxs-lookup"><span data-stu-id="1a898-108">Configure the itinerary to route the message to a service endpoint using a UDDI 3 resolver.</span></span>  
  
-   <span data-ttu-id="1a898-109">旅行プランのテスト用クライアントのサンプル アプリケーションを使用して、旅行プランをテストします。</span><span class="sxs-lookup"><span data-stu-id="1a898-109">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1a898-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="1a898-110">Prerequisites</span></span>  
 <span data-ttu-id="1a898-111">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。</span><span class="sxs-lookup"><span data-stu-id="1a898-111">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="1a898-112">手順</span><span class="sxs-lookup"><span data-stu-id="1a898-112">Steps</span></span>  
  
#### <a name="to-create-an-itinerary-model"></a><span data-ttu-id="1a898-113">スケジュール オンランプ モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="1a898-113">To create an itinerary model</span></span>  
  
1.  <span data-ttu-id="1a898-114">Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="1a898-114">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="1a898-115">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントして、**追加**、順にクリックします**新しい行程**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-115">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="1a898-116">**新しい項目の追加**ダイアログ ボックスに「 **UDDI3CategorySearch**で、**名前**ボックスをクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-116">In the **Add New Item** dialog box, type **UDDI3CategorySearch** in the **Name** box, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="1a898-117">旅行プランのプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="1a898-117">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="1a898-118">Visual Studio でのデザイン画面をクリックします。 **UDDI3CategorySearch.itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-118">In Visual Studio, click the design surface of **UDDI3CategorySearch.itinerary**.</span></span> <span data-ttu-id="1a898-119">**UDDI3CategorySearch**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="1a898-119">In the **UDDI3CategorySearch** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1a898-120">**モデル エクスポーター**ドロップダウン リストでは、をクリックして**XML 行程エクスポーター**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-120">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="1a898-121">下、**エクステンダー設定**セクションで、横に、**旅行プラン XML ファイル**プロパティ、省略記号ボタン (…) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a898-121">Under the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="1a898-122">**XML ファイルの**ダイアログ ボックスに「 **C:\HowTos\Itineraries\UDDI3CategorySearch**で、**ファイル名**ボックスをクリック**保存**.</span><span class="sxs-lookup"><span data-stu-id="1a898-122">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\UDDI3CategorySearch** in the **File name** box, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="1a898-123">この手順では、旅行プランを XML としてローカル ファイルの場所にエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="1a898-123">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="1a898-124">行程データベースの代わりにスケジュールをローカル ファイルの場所にエクスポートして、ESB のテスト用クライアント アプリケーションを使用してスケジュールのテストが可能です。</span><span class="sxs-lookup"><span data-stu-id="1a898-124">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="1a898-125">この操作方法に関するトピックの後半には、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="1a898-125">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="1a898-126">旅行プランの構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="1a898-126">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="1a898-127">ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。</span><span class="sxs-lookup"><span data-stu-id="1a898-127">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="1a898-128">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="1a898-128">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1a898-129">をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-129">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="1a898-130">**エクステンダー**ドロップダウン リストでは、をクリックして**入口 ESB エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-130">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="1a898-131">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-131">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="1a898-132">**受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-132">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="1a898-133">ツールボックスからドラッグして、**スケジュール サービス**デザイン サーフェイスにモデル要素。</span><span class="sxs-lookup"><span data-stu-id="1a898-133">From the Toolbox, drag an **Itinerary Service** model element to the design surface.</span></span> <span data-ttu-id="1a898-134">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="1a898-134">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1a898-135">をクリックして、**名前**プロパティ、および入力**CategoryRoute**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-135">Click the **Name** property, and then type **CategoryRoute**.</span></span>  
  
    2.  <span data-ttu-id="1a898-136">**行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**エクステンダーのメッセージング**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-136">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
    3.  <span data-ttu-id="1a898-137">**コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、 をクリックし、**受信ハンドラー**。</span><span class="sxs-lookup"><span data-stu-id="1a898-137">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="1a898-138">**サービス名**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB.Services.Routing**</span><span class="sxs-lookup"><span data-stu-id="1a898-138">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**</span></span>  
  
3.  <span data-ttu-id="1a898-139">右クリックし、**リゾルバー**のコレクション、 **CategoryRoute**モデル要素をクリックして**新しいリゾルバーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-139">Right-click the **Resolver** collection of the **CategoryRoute** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="1a898-140">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="1a898-140">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1a898-141">をクリックして、**名前**プロパティ、および入力**CategorySearch**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-141">Click the **Name** property, and then type **CategorySearch**.</span></span>  
  
    2.  <span data-ttu-id="1a898-142">**リゾルバーの実装**ドロップダウン リストでは、をクリックして**Uddi3 競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-142">In the **Resolver Implementation** drop-down list, click **Uddi3 Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="1a898-143">**リゾルバー モニカー**ドロップダウン リストでは、をクリックして**UDDI3**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-143">In the **Resolver Moniker** drop-down list, click **UDDI3**.</span></span>  
  
    4.  <span data-ttu-id="1a898-144">をクリックして、**カテゴリ検索**プロパティ、省略記号ボタン (…) を順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a898-144">Click the **Category Search** property, and then click the ellipsis button (…).</span></span>  
  
    5.  <span data-ttu-id="1a898-145">**名前値のプロパティ エディター**ダイアログ ボックスで、をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-145">In the **Name Value Property Editor** dialog box, click **Add**.</span></span>  
  
    6.  <span data-ttu-id="1a898-146">をクリックして、**名前**プロパティ、および入力**uddi:esb:biztalkapplication**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-146">Click the **Name** property, and then type **uddi:esb:biztalkapplication**.</span></span>  
  
    7.  <span data-ttu-id="1a898-147">をクリックして、**値**プロパティ、および入力**GlobalBank.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-147">Click the **Value** property, and then type **GlobalBank.ESB**.</span></span>  
  
    8.  <span data-ttu-id="1a898-148">**名前値のプロパティ エディター**ダイアログ ボックスで、をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-148">In the **Name Value Property Editor** dialog box, click **Add**.</span></span>  
  
    9. <span data-ttu-id="1a898-149">をクリックして、**名前**プロパティ、および入力**uddi:esb:portname**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-149">Click the **Name** property, and then type **uddi:esb:portname**.</span></span>  
  
    10. <span data-ttu-id="1a898-150">をクリックして、**値**プロパティ、および入力**OrderFileServicev3**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-150">Click the **Value** property, and then type **OrderFileServicev3**.</span></span>  
  
    11. <span data-ttu-id="1a898-151">**名前値のプロパティ エディター**ダイアログ ボックスで、をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-151">In the **Name Value Property Editor** dialog box, click **Add**.</span></span>  
  
    12. <span data-ttu-id="1a898-152">をクリックして、**名前**プロパティ、および入力**uddi:esb:version**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-152">Click the **Name** property, and then type **uddi:esb:version**.</span></span>  
  
    13. <span data-ttu-id="1a898-153">をクリックして、**値**プロパティ、および入力**1**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-153">Click the **Value** property, and then type **1**.</span></span>  
  
    14. <span data-ttu-id="1a898-154">をクリックして**OK**を閉じる、**名前値のプロパティ エディター**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="1a898-154">Click **OK** to close the **Name Value Property Editor** dialog box.</span></span>  
  
4.  <span data-ttu-id="1a898-155">右クリックし、 **CategorySearch**リゾルバー、およびクリック**テスト構成の競合回避モジュール**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-155">Right-click the **CategorySearch** resolver, and then click **Test Resolver Configuration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1a898-156">出力ウィンドウに表示される出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="1a898-156">Verify the output displayed in the Output window.</span></span>  
  
5.  <span data-ttu-id="1a898-157">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-157">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="1a898-158">接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **CategoryRoute**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="1a898-158">Drag a connection from the **ReceiveNAOrder** model element to the **CategoryRoute** model element.</span></span>  
  
6.  <span data-ttu-id="1a898-159">ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **CategoryRoute**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="1a898-159">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **CategoryRoute** model element.</span></span> <span data-ttu-id="1a898-160">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="1a898-160">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1a898-161">をクリックして、**名前**プロパティ、および入力**SendNAOrder**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-161">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="1a898-162">**エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-162">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="1a898-163">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-163">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="1a898-164">**送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-164">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
7.  <span data-ttu-id="1a898-165">ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **CategoryRoute**モデル要素と**SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="1a898-165">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **CategoryRoute** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="1a898-166">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="1a898-166">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1a898-167">をクリックして、**名前**プロパティ、および入力**SendPortFilter**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-167">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="1a898-168">**行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ エクステンダー**。</span><span class="sxs-lookup"><span data-stu-id="1a898-168">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="1a898-169">**傾斜オフ**ドロップダウン リストで、展開**SendNAOrder**、順にクリックします**送信ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-169">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
8.  <span data-ttu-id="1a898-170">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-170">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="1a898-171">接続をドラッグして、 **CategoryRoute**モデル要素に、 **SendPortFilter**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="1a898-171">Drag a connection from the **CategoryRoute** model element to the **SendPortFilter** model element.</span></span>  
  
9. <span data-ttu-id="1a898-172">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-172">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="1a898-173">接続をドラッグして、 **SendPortFilter**モデル要素に、 **SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="1a898-173">Drag a connection from the **SendPortFilter** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="1a898-174">旅行プランのテスト クライアントで使用するモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="1a898-174">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="1a898-175">Visual Studio でのデザイン画面を右クリックし、 **UDDI3CategorySearch**旅行プランをクリックして**モデルのエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="1a898-175">In Visual Studio, right-click the design surface of the **UDDI3CategorySearch** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1a898-176">旅行プランの XML バージョンは、Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="1a898-176">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="1a898-177">すべてのプロジェクト成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="1a898-177">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="1a898-178">Windows エクスプ ローラーでは、C:\HowTos\Itineraries を参照し、旅行プラン XML (UDDI3CategorySearch.xml) の作成に注意してください。</span><span class="sxs-lookup"><span data-stu-id="1a898-178">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (UDDI3CategorySearch.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="1a898-179">旅行プランをテストするには</span><span class="sxs-lookup"><span data-stu-id="1a898-179">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="1a898-180">中に作成されたショートカットを使用してスケジュールのテスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB します。Itinerary.Test.exe - ショートカット)。</span><span class="sxs-lookup"><span data-stu-id="1a898-180">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="1a898-181">行程テスト クライアントでオフ、 **WCF サービスを使用して**チェック ボックスをオンにし**ロード行程**。</span><span class="sxs-lookup"><span data-stu-id="1a898-181">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="1a898-182">**行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="1a898-182">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="1a898-183">選択**UDDI3CategorySearch.xml**、順にクリックします**オープン**旅行プランを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="1a898-183">Select **UDDI3CategorySearch.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="1a898-184">をクリックして**OK**をオフに、**旅行プランは正常に読み込まれる**メッセージ。</span><span class="sxs-lookup"><span data-stu-id="1a898-184">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="1a898-185">旅行プランのテスト クライアントで、横にある省略記号ボタン (…) をクリックします。、**ロード メッセージ**ボックス。</span><span class="sxs-lookup"><span data-stu-id="1a898-185">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="1a898-186">**を読み込む XML ドキュメントの選択** ダイアログ ボックスで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="1a898-186">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="1a898-187">NAOrderDoc.xml を選択し、クリックして**オープン**テスト メッセージを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="1a898-187">Select NAOrderDoc.xml, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="1a898-188">をクリックして、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a898-188">Click the **Submit Request** button.</span></span> <span data-ttu-id="1a898-189">テストが完了したら、クリックして**OK**表示される確認メッセージを無視します。</span><span class="sxs-lookup"><span data-stu-id="1a898-189">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="1a898-190">Windows エクスプ ローラーを参照**C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out**いることを確認し、 **%MessageID%.xml**にメッセージが書き込まれた、ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="1a898-190">In Windows Explorer, browse to **C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out** and verify that the **%MessageID%.xml** message has been written to the directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="1a898-191">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="1a898-191">Additional Resources</span></span>  
 <span data-ttu-id="1a898-192">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a898-192">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="1a898-193">方法: UDDI バインド キー検索を使用してサービス エンドポイントを解決するには</span><span class="sxs-lookup"><span data-stu-id="1a898-193">How to: Resolve a Service Endpoint Using a UDDI Binding Key Search</span></span>](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search.md)  
  
-   [<span data-ttu-id="1a898-194">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="1a898-194">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="1a898-195">動的な解決とルーティングを利用する</span><span class="sxs-lookup"><span data-stu-id="1a898-195">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)