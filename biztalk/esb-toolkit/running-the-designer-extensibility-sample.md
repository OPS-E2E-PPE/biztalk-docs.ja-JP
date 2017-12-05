---
title: "デザイナーの機能拡張のサンプルを実行している |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 05ac3b50-5bf2-4566-8654-472391476d1f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69659359af123af7d9239241128cae06934d9a54
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="running-the-designer-extensibility-sample"></a><span data-ttu-id="c3431-102">デザイナーの機能拡張のサンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="c3431-102">Running the Designer Extensibility Sample</span></span>
<span data-ttu-id="c3431-103">デザイナーの機能拡張のサンプルでは、2 つのサンプル エクステンダーを使用して、カスタム競合回避モジュールとの itinerary サービス、デザイン時構成オプションをようにする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c3431-103">The Designer Extensibility sample uses two sample extenders to demonstrate how you can provide design-time configuration options for custom resolvers and for itinerary services.</span></span>  
  
 <span data-ttu-id="c3431-104">**デザイナーの機能拡張のサンプルを実行するには**</span><span class="sxs-lookup"><span data-stu-id="c3431-104">**To run the Designer Extensibility sample**</span></span>  
  
1.  <span data-ttu-id="c3431-105">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="c3431-105">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="c3431-106">Visual Studio で、指す**新規**上、**ファイル** メニューをクリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="c3431-106">In Visual Studio, point to **New** on the **File** menu, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="c3431-107">C# クラス ライブラリ テンプレートの種類の選択**ItineraryLibrary**で、**名前**ボックスし、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="c3431-107">Select the C# Class Library template, type **ItineraryLibrary** in the **Name** box, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="c3431-108">ソリューション エクスプ ローラーでプロジェクトを右クリックして、ItineraryLibrary をポイントし、**追加**、クリックして**新しい行程**です。</span><span class="sxs-lookup"><span data-stu-id="c3431-108">In Solution Explorer, right-click the ItineraryLibrary project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
5.  <span data-ttu-id="c3431-109">**名前**ボックスに、入力**TestItinerary**、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c3431-109">In the **Name** box, type **TestItinerary**, and then press ENTER.</span></span>  
  
6.  <span data-ttu-id="c3431-110">ツールボックスで、On ごとの傾斜増加モデル要素の場合をクリックし、デザイン画面にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="c3431-110">In the Toolbox, click an On-Ramp model element, and then drag it to the design surface.</span></span>  
  
7.  <span data-ttu-id="c3431-111">ツールボックスで、行程サービス モデル要素の場合をクリックし、デザイン画面にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="c3431-111">In the Toolbox, click an Itinerary Service model element, and then drag it to the design surface.</span></span>  
  
8.  <span data-ttu-id="c3431-112">ツールボックスで、別の日程サービス モデル要素をクリックし、デザイン画面にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="c3431-112">In the Toolbox, click another Itinerary Service model element, and then drag it to the design surface.</span></span>  
  
9. <span data-ttu-id="c3431-113">ツールボックスで、Off ごとの傾斜増加モデル要素の場合をクリックし、デザイン画面にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="c3431-113">In the Toolbox, click an Off-Ramp model element, and then drag it to the design surface.</span></span>  
  
10. <span data-ttu-id="c3431-114">ツールボックスで、[コネクタ ツール] をクリックし、ドラッグ間の接続、 **OnRamp1**モデル要素と**ItineraryService1**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="c3431-114">In the Toolbox, click the Connector tool, and then drag a connection between the **OnRamp1** model element and the **ItineraryService1** model element.</span></span>  
  
11. <span data-ttu-id="c3431-115">ツールボックスで、[コネクタ ツール] をクリックし、ドラッグ間の接続、 **ItineraryService1**モデル要素と**ItineraryService2**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="c3431-115">In the Toolbox, click the Connector tool, and then drag a connection between the **ItineraryService1** model element and the **ItineraryService2** model element.</span></span>  
  
12. <span data-ttu-id="c3431-116">ツールボックスで、[コネクタ ツール] をクリックし、ドラッグ間の接続、 **ItineraryService2**モデル要素と**OffRamp1**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="c3431-116">In the Toolbox, click the Connector tool, and then drag a connection between the **ItineraryService2** model element and the **OffRamp1** model element.</span></span>  
  
13. <span data-ttu-id="c3431-117">クリックして、 **OnRamp1**要素をモデル化し、[プロパティ] ウィンドウにエクステンダー プロパティを設定し、**入り口 ESB サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="c3431-117">Click the **OnRamp1** model element, and then in the Properties window, set the Extender property to **On-Ramp ESB Service Extension**.</span></span>  
  
14. <span data-ttu-id="c3431-118">設定、 **BizTalk アプリケーション**プロパティを**Microsoft.Practices.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="c3431-118">Set the **BizTalk Application** property to **Microsoft.Practices.ESB**.</span></span>  
  
15. <span data-ttu-id="c3431-119">設定、**受信ポート**プロパティを**OnRamp.Itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="c3431-119">Set the **Receive Port** property to **OnRamp.Itinerary**.</span></span>  
  
16. <span data-ttu-id="c3431-120">クリックして、 **ItinearyService1**要素をモデル化し、[プロパティ] ウィンドウで次のように設定します。、 **Extender**プロパティを**サンプル オーケストレーション行程サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="c3431-120">Click the **ItinearyService1** model element, and then in the Properties window, set the **Extender** property to **Sample Orchestration Itinerary Service Extension**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c3431-121">これは、デザイナーの機能拡張のサンプルの一部としてインストールされているカスタム拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="c3431-121">This is the custom extension installed as part of the Designer Extensibility sample.</span></span> <span data-ttu-id="c3431-122">プロパティをオーケストレーションに基づく itinerary サービスに渡されるプロパティ バッグに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="c3431-122">It allows you to add properties to the property bag passed to an orchestration-based itinerary service.</span></span>  
  
17. <span data-ttu-id="c3431-123">設定、 **OtherValue**プロパティを**1**です。</span><span class="sxs-lookup"><span data-stu-id="c3431-123">Set the **OtherValue** property to **1**.</span></span>  
  
18. <span data-ttu-id="c3431-124">設定、 **ServiceName**プロパティを**Microsoft.Practices.ESB.Services.Routing**です。</span><span class="sxs-lookup"><span data-stu-id="c3431-124">Set the **ServiceName** property to **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
19. <span data-ttu-id="c3431-125">設定、 **SomeValue**プロパティを**2**です。</span><span class="sxs-lookup"><span data-stu-id="c3431-125">Set the **SomeValue** property to **2**.</span></span>  
  
20. <span data-ttu-id="c3431-126">右クリックし、**リゾルバー**のコレクション**ItineraryService1**、クリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="c3431-126">Right-click the **Resolver** collection of **ItineraryService1**, and then click **Add new Resolver**.</span></span>  
  
21. <span data-ttu-id="c3431-127">をクリックして**Resolver1**、し、[プロパティ] ウィンドウで次のように設定します。、**リゾルバーの実装**プロパティを**競合回避モジュールの拡張機能のサンプル**です。</span><span class="sxs-lookup"><span data-stu-id="c3431-127">Click **Resolver1**, and then in the Properties window, set the **Resolver Implementation** property to **Sample Resolver Extension**.</span></span>  
  
22. <span data-ttu-id="c3431-128">設定、 **SomeResolverValue**プロパティを**テスト**に version プロパティを設定および**1.0**です。</span><span class="sxs-lookup"><span data-stu-id="c3431-128">Set the **SomeResolverValue** property to **test**, and then set the version property to **1.0**.</span></span>  
  
23. <span data-ttu-id="c3431-129">クリックして、 **ItineraryService2**要素をモデル化し、[プロパティ] ウィンドウで次のように設定します、**行程サービス エクステンダー**プロパティを**出口行程サービス拡張**.</span><span class="sxs-lookup"><span data-stu-id="c3431-129">Click the **ItineraryService2** model element, and then in the Properties window, set the **Itinerary Service Extender** property to **Off-Ramp Itinerary Service Extension**.</span></span>  
  
24. <span data-ttu-id="c3431-130">設定、**出口**プロパティを**OffRamp1 > 送信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="c3431-130">Set the **Off-Ramp** property to **OffRamp1 > Send Handlers**.</span></span>  
  
25. <span data-ttu-id="c3431-131">クリックして、 **OffRamp1**要素をモデル化し、[プロパティ] ウィンドウで次のように設定します。、 **Extender**プロパティを**出口 ESB サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="c3431-131">Click the **OffRamp1** model element, and then in the Properties window, set the **Extender** property to **Off-Ramp ESB Service Extension**.</span></span>  
  
26. <span data-ttu-id="c3431-132">設定、 **BizTalk アプリケーション**プロパティを**GlobalBank.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="c3431-132">Set the **BizTalk Application** property to **GlobalBank.ESB**.</span></span>  
  
27. <span data-ttu-id="c3431-133">設定、**送信ポート**プロパティを**DynamicResolutionOneWay**です。</span><span class="sxs-lookup"><span data-stu-id="c3431-133">Set the **Send Port** property to **DynamicResolutionOneWay**.</span></span>  
  
28. <span data-ttu-id="c3431-134">デザイン サーフェイスを右クリックし、をクリックして**モデルのエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="c3431-134">Right-click the design surface, and then click **Export Model**.</span></span>  
  
29. <span data-ttu-id="c3431-135">生成された XML を確認します。</span><span class="sxs-lookup"><span data-stu-id="c3431-135">Examine the generated XML.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c3431-136">通知、 **PropertyBag**要素およびプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c3431-136">Notice the **PropertyBag** element and the properties it contains.</span></span> <span data-ttu-id="c3431-137">競合回避モジュールの接続文字列の例およびを確認の構成方法入力プロパティを基にします。</span><span class="sxs-lookup"><span data-stu-id="c3431-137">Also notice the Sample resolver connection string and how it was configured based on the properties entered.</span></span>