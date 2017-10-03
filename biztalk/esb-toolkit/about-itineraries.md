---
title: "行程に関する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d34632f-8652-49dd-97b7-2513aacc1bd7
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66a9a759a6afdd55c3c1646d02c480aa193261aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="about-itineraries"></a><span data-ttu-id="ca27e-102">行程について</span><span class="sxs-lookup"><span data-stu-id="ca27e-102">About Itineraries</span></span>
<span data-ttu-id="ca27e-103">日程、ESB 仲介ポリシー処理に基づいて命令のシーケンスを実行するための表現である、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]拡張可能な形式です。</span><span class="sxs-lookup"><span data-stu-id="ca27e-103">An itinerary is a representation of an ESB mediation policy for executing a sequence of processing instructions based on the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] extensible format.</span></span> <span data-ttu-id="ca27e-104">日程が宣言型の itinerary サービスの構成で仲介コンポーネントに関連付けられているのシーケンスを記述する高度な仲介言語として見なすことができます、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コア エンジンです。</span><span class="sxs-lookup"><span data-stu-id="ca27e-104">An itinerary can be viewed as a high-level mediation language that describes a sequence of declarative itinerary services that are associated with mediation components by configuration of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core engine.</span></span> <span data-ttu-id="ca27e-105">メッセージの処理方法を説明する仲介フローをデザインすることができ、ビジュアルの描画として全体の流れを整理することができます。</span><span class="sxs-lookup"><span data-stu-id="ca27e-105">You can design mediation flows to describe how messages should be processed, and you can organize the entire flow as a visual drawing.</span></span> <span data-ttu-id="ca27e-106">実行時に、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コア エンジンは、行程デザイナーによって生成される旅程を実行します。</span><span class="sxs-lookup"><span data-stu-id="ca27e-106">At run time, the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core engine executes the itinerary produced by Itinerary Designer.</span></span>  
  
## <a name="the-itinerary-designer-surface"></a><span data-ttu-id="ca27e-107">Itinerary デザイナー画面</span><span class="sxs-lookup"><span data-stu-id="ca27e-107">The Itinerary Designer Surface</span></span>  
 <span data-ttu-id="ca27e-108">行程デザイナー画面の作成に使用される、ビジュアル デザイナーは、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]旅程日程を実行時の形式にエクスポートするとします。</span><span class="sxs-lookup"><span data-stu-id="ca27e-108">The Itinerary Designer surface is a visual designer that is used to create [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itineraries and to export these itineraries into run-time format.</span></span> <span data-ttu-id="ca27e-109">これは、図 1 に示すように、ツールボックスの項目をドラッグする先のキャンバスです。</span><span class="sxs-lookup"><span data-stu-id="ca27e-109">It is a canvas to which you can drag items from the Toolbox, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="ca27e-110">![Itinerary Designer](../esb-toolkit/media/ch5-itinerarydesigner.gif "Ch5 ItineraryDesigner")</span><span class="sxs-lookup"><span data-stu-id="ca27e-110">![Itinerary Designer](../esb-toolkit/media/ch5-itinerarydesigner.gif "Ch5-ItineraryDesigner")</span></span>  
  
 <span data-ttu-id="ca27e-111">**図 1**</span><span class="sxs-lookup"><span data-stu-id="ca27e-111">**Figure 1**</span></span>  
  
 <span data-ttu-id="ca27e-112">**Itinerary Designer 画面**</span><span class="sxs-lookup"><span data-stu-id="ca27e-112">**Itinerary Designer surface**</span></span>  
  
 <span data-ttu-id="ca27e-113">旅行計画の名前は、Microsoft Visual Studio タイトル バーと旅程デザイナーの上部のタブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca27e-113">The name of the itinerary is displayed on the top tab of the Itinerary Designer and in the Microsoft Visual Studio title bar.</span></span> <span data-ttu-id="ca27e-114">デザイン画面は 1 つの領域で、旅行計画の実際のメッセージ フローを記述するモデル要素を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="ca27e-114">The design surface itself is a single area and contains model elements that describe the actual message flow of the itinerary.</span></span> <span data-ttu-id="ca27e-115">ItineraryDSL では、Visual Studio プロパティ ウィンドウを使用してモデル要素のプロパティを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="ca27e-115">The ItineraryDSL enables you to modify the model element properties using the Visual Studio Properties window.</span></span>  
  
## <a name="itinerary-designer-toolbox"></a><span data-ttu-id="ca27e-116">Itinerary デザイナー ツールボックス</span><span class="sxs-lookup"><span data-stu-id="ca27e-116">Itinerary Designer Toolbox</span></span>  
 <span data-ttu-id="ca27e-117">Visual Studio ツールボックスには、ツールのセットを表すのタブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ca27e-117">The Visual Studio Toolbox contains tabs, which represent sets of tools.</span></span> <span data-ttu-id="ca27e-118">ツールボックスには行程デザイナーを使用する Visual Studio プロジェクトを開いたときに 2 つのタブが含まれています。**全般** タブおよび**ItineraryDsl**タブです。</span><span class="sxs-lookup"><span data-stu-id="ca27e-118">When you open a Visual Studio project that uses Itinerary Designer, the Toolbox contains two tabs: the **General** tab and the **ItineraryDsl** tabs.</span></span> <span data-ttu-id="ca27e-119">**ItineraryDsl**  タブには、次のツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ca27e-119">The **ItineraryDsl** tab contains the following tools:</span></span>  
  
-   <span data-ttu-id="ca27e-120">**Itinerary サービス ツール**です。</span><span class="sxs-lookup"><span data-stu-id="ca27e-120">**Itinerary Service tool**.</span></span> <span data-ttu-id="ca27e-121">このモデル要素は itinerary 仲介サービスに対応し、処理命令を表します。</span><span class="sxs-lookup"><span data-stu-id="ca27e-121">This model element corresponds to the itinerary mediation service and represents a processing instruction.</span></span>  
  
-   <span data-ttu-id="ca27e-122">**コネクタ ツール**です。</span><span class="sxs-lookup"><span data-stu-id="ca27e-122">**Connector tool**.</span></span> <span data-ttu-id="ca27e-123">このモデルの要素では、行程デザイナー サーフェイス上の個々 のモデル要素間のリレーションシップを定義します。</span><span class="sxs-lookup"><span data-stu-id="ca27e-123">This model element defines the relationship between individual model elements on the Itinerary Designer surface.</span></span>  
  
-   <span data-ttu-id="ca27e-124">**出口ツール**です。</span><span class="sxs-lookup"><span data-stu-id="ca27e-124">**Off-Ramp tool**.</span></span> <span data-ttu-id="ca27e-125">このモデル要素は、出口メッセージを送信するに対応します。</span><span class="sxs-lookup"><span data-stu-id="ca27e-125">This model element corresponds to the off-ramp that sends a message.</span></span> <span data-ttu-id="ca27e-126">行程デザイナーでは、複数オフ-ランプ モデルに 1 を実行します。</span><span class="sxs-lookup"><span data-stu-id="ca27e-126">The Itinerary Designer allows multiple off-ramps per model.</span></span>  
  
-   <span data-ttu-id="ca27e-127">**入り口ツール**です。</span><span class="sxs-lookup"><span data-stu-id="ca27e-127">**On-Ramp tool**.</span></span> <span data-ttu-id="ca27e-128">このモデル要素は、入り口メッセージを受信に対応します。</span><span class="sxs-lookup"><span data-stu-id="ca27e-128">This model element corresponds to an on-ramp that receives a message.</span></span> <span data-ttu-id="ca27e-129">行程デザイナーは、1 つだけに着手モデルに 1 を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca27e-129">The Itinerary Designer allows only one on-ramp per model.</span></span>  
  
-   <span data-ttu-id="ca27e-130">**道順の Broker Service ツール**です。</span><span class="sxs-lookup"><span data-stu-id="ca27e-130">**Itinerary Broker Service tool**.</span></span> <span data-ttu-id="ca27e-131">このモデル要素は、複数の入力と複数の出力を使用した定義済みのメッセージ フローを可能にする itinerary 仲介サービスに対応します。</span><span class="sxs-lookup"><span data-stu-id="ca27e-131">This model element corresponds to the itinerary mediation service that allows defined message flow with multiple inputs and multiple outputs.</span></span>  
  
-   <span data-ttu-id="ca27e-132">**Itinerary Broker 出力ポート**です。</span><span class="sxs-lookup"><span data-stu-id="ca27e-132">**Itinerary Broker Output port**.</span></span> <span data-ttu-id="ca27e-133">このモデル要素には、行程 Broker サービスの 1 つの出力ポートに対応しています。</span><span class="sxs-lookup"><span data-stu-id="ca27e-133">This model element corresponds to the single output port of the Itinerary Broker Service.</span></span> <span data-ttu-id="ca27e-134">行程ブローカー サービスのモデル要素は、複数の出力ポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="ca27e-134">The Itinerary Broker Service model element allows multiple output ports.</span></span>  
  
## <a name="steps-in-itinerary-development"></a><span data-ttu-id="ca27e-135">Itinerary 開発手順</span><span class="sxs-lookup"><span data-stu-id="ca27e-135">Steps in Itinerary Development</span></span>  
 <span data-ttu-id="ca27e-136">ESB 仲介のフローを表し、日程を開発するのには、通常、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ca27e-136">To develop an itinerary, which represents ESB mediation flow, you should typically perform the following actions:</span></span>  
  
-   <span data-ttu-id="ca27e-137">処理手順、日程のメッセージを表すモデル要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="ca27e-137">Add model elements to represent the message processing steps for your itinerary.</span></span> <span data-ttu-id="ca27e-138">行程デザイナーには、さまざまな操作またはキーの抽象化を表すために使用する図形を含むツールボックスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ca27e-138">The Itinerary Designer provides a toolbox that contains shapes used to represent different actions or key abstractions.</span></span>  
  
-   <span data-ttu-id="ca27e-139">Itinerary モデルのプロパティは、Microsoft BizTalk Server 管理データベースとモデルのエクスポーター構成への接続文字列を含めるを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca27e-139">Specify itinerary model properties, which include a connection string to the Microsoft BizTalk Server management database and model exporter configuration.</span></span>  
  
-   <span data-ttu-id="ca27e-140">物理 BizTalk へのバインド入り口と出口のモデル要素は、受信場所と、これらのモデル要素に対応するテクノロジのエクステンダーを関連付けることによってポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="ca27e-140">Bind on-ramp and off-ramp model elements to physical BizTalk receive locations and send ports by associating these model elements with corresponding technology extenders.</span></span>  
  
-   <span data-ttu-id="ca27e-141">Itinerary サービス モデル要素を関連付けるエクステンダーし、extender に必要なテクノロジに固有のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="ca27e-141">Associate itinerary services model elements with extenders and define technology-specific properties required by an extender.</span></span> <span data-ttu-id="ca27e-142">これらのプロパティでは、特定の種類の extender; が異なる可能性があります。これらは、itinerary 仲介サービスのプロパティとその実行時コンポーネントとの成果物に関連付けられた BizTalk 固有のプロパティを表すことができます。</span><span class="sxs-lookup"><span data-stu-id="ca27e-142">These properties may vary for a particular type of the extender; they can represent itinerary mediation service properties and BizTalk-specific properties associated with its run-time components and artifacts.</span></span>  
  
-   <span data-ttu-id="ca27e-143">Itinerary 仲介サービスとして参照することができますをカスタム コンポーネントを識別します。</span><span class="sxs-lookup"><span data-stu-id="ca27e-143">Identify custom components that you might want to reference as itinerary mediation services.</span></span> <span data-ttu-id="ca27e-144">たとえば、itinerary サービスとしてのオーケストレーションを開発する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ca27e-144">For example, you may develop an orchestration as the itinerary service.</span></span>  
  
-   <span data-ttu-id="ca27e-145">に対して競合回避モジュール モデル要素の設定を確認する[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]デザイナー サーフェスからリゾルバー サービスを呼び出すことによって実行時構成します。</span><span class="sxs-lookup"><span data-stu-id="ca27e-145">Verify resolver model element settings against [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] run-time configuration by invoking resolver service from the designer surface.</span></span>  
  
-   <span data-ttu-id="ca27e-146">検証し、エクスポーターを使用して、itinerary 実行時ポリシーをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ca27e-146">Validate and export the itinerary run-time policy using an exporter.</span></span> <span data-ttu-id="ca27e-147">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]行程デザイナーで 2 つのエクスポートを提供します。 ファイル エクスポーターとエクスポーターのデータベースです。</span><span class="sxs-lookup"><span data-stu-id="ca27e-147">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides two exporters with the Itinerary Designer: file exporter and database exporter.</span></span> <span data-ttu-id="ca27e-148">また、カスタム エクスポーターを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="ca27e-148">Alternatively, you can implement a custom exporter.</span></span>  
  
-   <span data-ttu-id="ca27e-149">テスト クライアント アプリケーションまたは BizUnit フレームワークを使用して、日程をテストします。</span><span class="sxs-lookup"><span data-stu-id="ca27e-149">Test your itinerary using test client applications or BizUnit framework.</span></span>  
  
## <a name="security-considerations-for-developing-itineraries"></a><span data-ttu-id="ca27e-150">日程を開発するためのセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="ca27e-150">Security Considerations for Developing Itineraries</span></span>  
 <span data-ttu-id="ca27e-151">日程を設計するときは、潜在的なセキュリティの問題を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="ca27e-151">When you design itineraries, you should consider potential security issues:</span></span>  
  
-   <span data-ttu-id="ca27e-152">モデルのプロパティからの証明書を使用せずにユーザーの資格情報を指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="ca27e-152">Avoid specifying user credentials without using a certificate from the model properties.</span></span>  
  
-   <span data-ttu-id="ca27e-153">BizTalk を参照しない受信ポートと受信の匿名アクセスを許可する場所です。</span><span class="sxs-lookup"><span data-stu-id="ca27e-153">Do not refer to BizTalk receive ports with receive locations that allow anonymous access.</span></span>  
  
-   <span data-ttu-id="ca27e-154">Itinerary メッセージには、機密データが含まれている場合は、メッセージまたはトランスポート チャネルを保護します。</span><span class="sxs-lookup"><span data-stu-id="ca27e-154">Protect the message or transport channel if the itinerary message contains sensitive data.</span></span>  
  
-   <span data-ttu-id="ca27e-155">メッセージには、転送中に保護する必要がある機密データが含まれている場合は、パイプライン コンポーネントを含むメッセージ ボックス内のメッセージを保護します。</span><span class="sxs-lookup"><span data-stu-id="ca27e-155">Protect messages in the Message box with a pipeline component if the messages contain sensitive data that needs to be protected while in transit.</span></span>