---
title: デザイナー機能拡張サンプルを実行する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 05ac3b50-5bf2-4566-8654-472391476d1f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdfaf1ca75d480e219b0c99fb903b1997859a18f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292499"
---
# <a name="running-the-designer-extensibility-sample"></a><span data-ttu-id="2f1e3-102">デザイナー機能拡張サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-102">Running the Designer Extensibility Sample</span></span>
<span data-ttu-id="2f1e3-103">デザイナーの機能拡張サンプルでは、2 つのサンプルのエクステンダーを使用して、カスタム競合回避モジュール、およびスケジュール サービスとしてのデザイン時構成オプションを提供できる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-103">The Designer Extensibility sample uses two sample extenders to demonstrate how you can provide design-time configuration options for custom resolvers and for itinerary services.</span></span>  
  
 <span data-ttu-id="2f1e3-104">**デザイナーの機能拡張サンプルを実行するには**</span><span class="sxs-lookup"><span data-stu-id="2f1e3-104">**To run the Designer Extensibility sample**</span></span>  
  
1.  <span data-ttu-id="2f1e3-105">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-105">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="2f1e3-106">Visual Studio で、 をポイント**新規**上、**ファイル** メニューをクリック**プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-106">In Visual Studio, point to **New** on the **File** menu, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="2f1e3-107">選択、C#クラス ライブラリ テンプレート、型**ItineraryLibrary**で、**名前**ボックスし、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-107">Select the C# Class Library template, type **ItineraryLibrary** in the **Name** box, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="2f1e3-108">ソリューション エクスプ ローラーで ItineraryLibrary プロジェクトを右クリックして**追加**、 をクリックし、**新しい行程**。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-108">In Solution Explorer, right-click the ItineraryLibrary project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
5.  <span data-ttu-id="2f1e3-109">**名前**ボックスに「 **TestItinerary**、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-109">In the **Name** box, type **TestItinerary**, and then press ENTER.</span></span>  
  
6.  <span data-ttu-id="2f1e3-110">ツールボックスで、On 傾斜モデル要素の場合をクリックし、デザイン画面にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-110">In the Toolbox, click an On-Ramp model element, and then drag it to the design surface.</span></span>  
  
7.  <span data-ttu-id="2f1e3-111">ツールボックスで、スケジュール サービス モデル要素の場合をクリックし、デザイン画面にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-111">In the Toolbox, click an Itinerary Service model element, and then drag it to the design surface.</span></span>  
  
8.  <span data-ttu-id="2f1e3-112">ツールボックスで、別のスケジュール サービス モデル要素をクリックし、デザイン画面にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-112">In the Toolbox, click another Itinerary Service model element, and then drag it to the design surface.</span></span>  
  
9. <span data-ttu-id="2f1e3-113">ツールボックスで、Off 傾斜モデル要素の場合をクリックし、デザイン画面にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-113">In the Toolbox, click an Off-Ramp model element, and then drag it to the design surface.</span></span>  
  
10. <span data-ttu-id="2f1e3-114">ツールボックスで、コネクタ ツール をクリックし、間の接続をドラッグ、 **OnRamp1**モデル要素と**ItineraryService1**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-114">In the Toolbox, click the Connector tool, and then drag a connection between the **OnRamp1** model element and the **ItineraryService1** model element.</span></span>  
  
11. <span data-ttu-id="2f1e3-115">ツールボックスで、コネクタ ツール をクリックし、間の接続をドラッグ、 **ItineraryService1**モデル要素と**ItineraryService2**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-115">In the Toolbox, click the Connector tool, and then drag a connection between the **ItineraryService1** model element and the **ItineraryService2** model element.</span></span>  
  
12. <span data-ttu-id="2f1e3-116">ツールボックスで、コネクタ ツール をクリックし、間の接続をドラッグ、 **ItineraryService2**モデル要素と**OffRamp1**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-116">In the Toolbox, click the Connector tool, and then drag a connection between the **ItineraryService2** model element and the **OffRamp1** model element.</span></span>  
  
13. <span data-ttu-id="2f1e3-117">をクリックして、 **OnRamp1**要素をモデル化し、[プロパティ] ウィンドウでにエクステンダー プロパティを設定し、 **ESB サービス拡張機能の導入**します。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-117">Click the **OnRamp1** model element, and then in the Properties window, set the Extender property to **On-Ramp ESB Service Extension**.</span></span>  
  
14. <span data-ttu-id="2f1e3-118">設定、 **BizTalk アプリケーション**プロパティを**Microsoft.Practices.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-118">Set the **BizTalk Application** property to **Microsoft.Practices.ESB**.</span></span>  
  
15. <span data-ttu-id="2f1e3-119">設定、**受信ポート**プロパティを**OnRamp.Itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-119">Set the **Receive Port** property to **OnRamp.Itinerary**.</span></span>  
  
16. <span data-ttu-id="2f1e3-120">をクリックして、 **ItinearyService1**要素をモデル化し、[プロパティ] ウィンドウで次のように設定します。、**エクステンダー**プロパティを**サンプル オーケストレーション スケジュール サービス拡張**します。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-120">Click the **ItinearyService1** model element, and then in the Properties window, set the **Extender** property to **Sample Orchestration Itinerary Service Extension**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f1e3-121">これは、デザイナーの機能拡張サンプルの一部としてインストールされているカスタム拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-121">This is the custom extension installed as part of the Designer Extensibility sample.</span></span> <span data-ttu-id="2f1e3-122">プロパティをオーケストレーションに基づくスケジュール サービスに渡されるプロパティ バッグに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-122">It allows you to add properties to the property bag passed to an orchestration-based itinerary service.</span></span>  
  
17. <span data-ttu-id="2f1e3-123">設定、 **OtherValue**プロパティを**1**します。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-123">Set the **OtherValue** property to **1**.</span></span>  
  
18. <span data-ttu-id="2f1e3-124">設定、 **ServiceName**プロパティを**Microsoft.Practices.ESB.Services.Routing**します。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-124">Set the **ServiceName** property to **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
19. <span data-ttu-id="2f1e3-125">設定、 **SomeValue**プロパティを**2**します。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-125">Set the **SomeValue** property to **2**.</span></span>  
  
20. <span data-ttu-id="2f1e3-126">右クリックし、**リゾルバー**のコレクション**ItineraryService1**、 をクリックし、**新しいリゾルバーを追加**。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-126">Right-click the **Resolver** collection of **ItineraryService1**, and then click **Add new Resolver**.</span></span>  
  
21. <span data-ttu-id="2f1e3-127">クリックして**Resolver1**、し、[プロパティ] ウィンドウで次のように設定します。、**リゾルバーの実装**プロパティを**競合回避モジュールの拡張機能のサンプル**します。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-127">Click **Resolver1**, and then in the Properties window, set the **Resolver Implementation** property to **Sample Resolver Extension**.</span></span>  
  
22. <span data-ttu-id="2f1e3-128">設定、 **SomeResolverValue**プロパティを**テスト**、バージョン プロパティを設定および**1.0**します。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-128">Set the **SomeResolverValue** property to **test**, and then set the version property to **1.0**.</span></span>  
  
23. <span data-ttu-id="2f1e3-129">をクリックして、 **ItineraryService2**要素をモデル化し、[プロパティ] ウィンドウで次のように設定します、**行程サービス エクステンダー**プロパティを**傾斜オフ スケジュール サービス拡張**.</span><span class="sxs-lookup"><span data-stu-id="2f1e3-129">Click the **ItineraryService2** model element, and then in the Properties window, set the **Itinerary Service Extender** property to **Off-Ramp Itinerary Service Extension**.</span></span>  
  
24. <span data-ttu-id="2f1e3-130">設定、**傾斜オフ**プロパティを**OffRamp1 > 送信ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-130">Set the **Off-Ramp** property to **OffRamp1 > Send Handlers**.</span></span>  
  
25. <span data-ttu-id="2f1e3-131">をクリックして、 **OffRamp1**要素をモデル化し、[プロパティ] ウィンドウで次のように設定します。、**エクステンダー**プロパティを**傾斜オフ ESB サービス拡張**します。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-131">Click the **OffRamp1** model element, and then in the Properties window, set the **Extender** property to **Off-Ramp ESB Service Extension**.</span></span>  
  
26. <span data-ttu-id="2f1e3-132">設定、 **BizTalk アプリケーション**プロパティを**GlobalBank.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-132">Set the **BizTalk Application** property to **GlobalBank.ESB**.</span></span>  
  
27. <span data-ttu-id="2f1e3-133">設定、**送信ポート**プロパティを**DynamicResolutionOneWay**します。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-133">Set the **Send Port** property to **DynamicResolutionOneWay**.</span></span>  
  
28. <span data-ttu-id="2f1e3-134">デザイン サーフェイスを右クリックし、**モデルのエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-134">Right-click the design surface, and then click **Export Model**.</span></span>  
  
29. <span data-ttu-id="2f1e3-135">生成された XML を確認します。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-135">Examine the generated XML.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f1e3-136">通知、 **PropertyBag**要素およびプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-136">Notice the **PropertyBag** element and the properties it contains.</span></span> <span data-ttu-id="2f1e3-137">また競合回避モジュールの接続文字列の例との構成方法入力されたプロパティに基づいて。</span><span class="sxs-lookup"><span data-stu-id="2f1e3-137">Also notice the Sample resolver connection string and how it was configured based on the properties entered.</span></span>