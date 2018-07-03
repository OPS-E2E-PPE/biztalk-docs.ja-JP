---
title: スケジュールについて |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d34632f-8652-49dd-97b7-2513aacc1bd7
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ddd41dcfc1c5b6a090d48411956b19986aa2d676
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001091"
---
# <a name="about-itineraries"></a><span data-ttu-id="7b51e-102">スケジュールについて</span><span class="sxs-lookup"><span data-stu-id="7b51e-102">About Itineraries</span></span>
<span data-ttu-id="7b51e-103">日程、ESB 仲介のポリシーの処理に基づく命令のシーケンスを実行するための表現である、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]拡張可能な形式です。</span><span class="sxs-lookup"><span data-stu-id="7b51e-103">An itinerary is a representation of an ESB mediation policy for executing a sequence of processing instructions based on the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] extensible format.</span></span> <span data-ttu-id="7b51e-104">スケジュールの構成によって仲介コンポーネントに関連付けられているサービスとして宣言型のシーケンスを説明する高度な仲介言語として、旅行プランを表示できます、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コア エンジンです。</span><span class="sxs-lookup"><span data-stu-id="7b51e-104">An itinerary can be viewed as a high-level mediation language that describes a sequence of declarative itinerary services that are associated with mediation components by configuration of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core engine.</span></span> <span data-ttu-id="7b51e-105">メッセージの処理方法を説明する仲介のフローをデザインして、ビジュアルの描画としてフロー全体を整理することができます。</span><span class="sxs-lookup"><span data-stu-id="7b51e-105">You can design mediation flows to describe how messages should be processed, and you can organize the entire flow as a visual drawing.</span></span> <span data-ttu-id="7b51e-106">実行時に、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コア エンジンは、旅行プラン デザイナーによって生成される旅行プランを実行します。</span><span class="sxs-lookup"><span data-stu-id="7b51e-106">At run time, the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core engine executes the itinerary produced by Itinerary Designer.</span></span>  
  
## <a name="the-itinerary-designer-surface"></a><span data-ttu-id="7b51e-107">スケジュール オンランプ デザイナー画面</span><span class="sxs-lookup"><span data-stu-id="7b51e-107">The Itinerary Designer Surface</span></span>  
 <span data-ttu-id="7b51e-108">旅行プラン デザイナー サーフェスがビジュアルなデザイナーを作成するために使用する[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]スケジュールと形式の実行時にこれらのスケジュールをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="7b51e-108">The Itinerary Designer surface is a visual designer that is used to create [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itineraries and to export these itineraries into run-time format.</span></span> <span data-ttu-id="7b51e-109">図 1 に示すように、ツールボックスから項目をドラッグする先のキャンバスになります。</span><span class="sxs-lookup"><span data-stu-id="7b51e-109">It is a canvas to which you can drag items from the Toolbox, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="7b51e-110">![Itinerary Designer](../esb-toolkit/media/ch5-itinerarydesigner.gif "Ch5 ItineraryDesigner")</span><span class="sxs-lookup"><span data-stu-id="7b51e-110">![Itinerary Designer](../esb-toolkit/media/ch5-itinerarydesigner.gif "Ch5-ItineraryDesigner")</span></span>  
  
 <span data-ttu-id="7b51e-111">**図 1**</span><span class="sxs-lookup"><span data-stu-id="7b51e-111">**Figure 1**</span></span>  
  
 <span data-ttu-id="7b51e-112">**スケジュール オンランプ デザイナー画面**</span><span class="sxs-lookup"><span data-stu-id="7b51e-112">**Itinerary Designer surface**</span></span>  
  
 <span data-ttu-id="7b51e-113">旅行計画の名前は、Microsoft Visual Studio のタイトル バーと旅程デザイナーの上部のタブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b51e-113">The name of the itinerary is displayed on the top tab of the Itinerary Designer and in the Microsoft Visual Studio title bar.</span></span> <span data-ttu-id="7b51e-114">デザイン画面自体は 1 つの領域であるため、旅行計画の実際のメッセージ フローを記述するモデル要素を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="7b51e-114">The design surface itself is a single area and contains model elements that describe the actual message flow of the itinerary.</span></span> <span data-ttu-id="7b51e-115">ItineraryDSL では、Visual Studio プロパティ ウィンドウを使用して、モデル要素のプロパティを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="7b51e-115">The ItineraryDSL enables you to modify the model element properties using the Visual Studio Properties window.</span></span>  
  
## <a name="itinerary-designer-toolbox"></a><span data-ttu-id="7b51e-116">スケジュール オンランプ デザイナー ツールボックス</span><span class="sxs-lookup"><span data-stu-id="7b51e-116">Itinerary Designer Toolbox</span></span>  
 <span data-ttu-id="7b51e-117">Visual Studio ツールボックスには、ツールのセットを表すのタブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7b51e-117">The Visual Studio Toolbox contains tabs, which represent sets of tools.</span></span> <span data-ttu-id="7b51e-118">旅行プラン デザイナーを使用する Visual Studio プロジェクトを開くと、ツールボックスには 2 つのタブ:**全般**タブおよび**ItineraryDsl**タブ。</span><span class="sxs-lookup"><span data-stu-id="7b51e-118">When you open a Visual Studio project that uses Itinerary Designer, the Toolbox contains two tabs: the **General** tab and the **ItineraryDsl** tabs.</span></span> <span data-ttu-id="7b51e-119">**ItineraryDsl**  タブには、次のツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7b51e-119">The **ItineraryDsl** tab contains the following tools:</span></span>  
  
-   <span data-ttu-id="7b51e-120">**スケジュール オンランプ サービス ツール**します。</span><span class="sxs-lookup"><span data-stu-id="7b51e-120">**Itinerary Service tool**.</span></span> <span data-ttu-id="7b51e-121">このモデルの要素は、スケジュール オンランプ仲介サービスに対応し、処理命令を表します。</span><span class="sxs-lookup"><span data-stu-id="7b51e-121">This model element corresponds to the itinerary mediation service and represents a processing instruction.</span></span>  
  
-   <span data-ttu-id="7b51e-122">**コネクタ ツール**します。</span><span class="sxs-lookup"><span data-stu-id="7b51e-122">**Connector tool**.</span></span> <span data-ttu-id="7b51e-123">このモデルの要素は、旅行プラン デザイナー サーフェイス上の個々 のモデル要素間のリレーションシップを定義します。</span><span class="sxs-lookup"><span data-stu-id="7b51e-123">This model element defines the relationship between individual model elements on the Itinerary Designer surface.</span></span>  
  
-   <span data-ttu-id="7b51e-124">**傾斜オフ ツール**します。</span><span class="sxs-lookup"><span data-stu-id="7b51e-124">**Off-Ramp tool**.</span></span> <span data-ttu-id="7b51e-125">このモデルの要素は、オフの強化などがメッセージを送信するに対応します。</span><span class="sxs-lookup"><span data-stu-id="7b51e-125">This model element corresponds to the off-ramp that sends a message.</span></span> <span data-ttu-id="7b51e-126">旅行プラン デザイナーは、複数オフランプ 1 つのモデルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7b51e-126">The Itinerary Designer allows multiple off-ramps per model.</span></span>  
  
-   <span data-ttu-id="7b51e-127">**入口ツール**します。</span><span class="sxs-lookup"><span data-stu-id="7b51e-127">**On-Ramp tool**.</span></span> <span data-ttu-id="7b51e-128">このモデルの要素は、入り口メッセージを受信に対応します。</span><span class="sxs-lookup"><span data-stu-id="7b51e-128">This model element corresponds to an on-ramp that receives a message.</span></span> <span data-ttu-id="7b51e-129">旅行プラン デザイナーは、1 つだけに着手 1 つのモデルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7b51e-129">The Itinerary Designer allows only one on-ramp per model.</span></span>  
  
-   <span data-ttu-id="7b51e-130">**スケジュール オンランプ ブローカー サービス ツール**します。</span><span class="sxs-lookup"><span data-stu-id="7b51e-130">**Itinerary Broker Service tool**.</span></span> <span data-ttu-id="7b51e-131">このモデルの要素は、複数の入力と複数の出力で定義されたメッセージのフローを許可する、スケジュール オンランプ仲介サービスに対応します。</span><span class="sxs-lookup"><span data-stu-id="7b51e-131">This model element corresponds to the itinerary mediation service that allows defined message flow with multiple inputs and multiple outputs.</span></span>  
  
-   <span data-ttu-id="7b51e-132">**スケジュール オンランプ Broker 出力ポート**します。</span><span class="sxs-lookup"><span data-stu-id="7b51e-132">**Itinerary Broker Output port**.</span></span> <span data-ttu-id="7b51e-133">このモデルの要素は、旅行プラン ブローカー サービスの 1 つの出力ポートに対応します。</span><span class="sxs-lookup"><span data-stu-id="7b51e-133">This model element corresponds to the single output port of the Itinerary Broker Service.</span></span> <span data-ttu-id="7b51e-134">旅行プラン ブローカー サービスのモデル要素には、複数の出力ポートができます。</span><span class="sxs-lookup"><span data-stu-id="7b51e-134">The Itinerary Broker Service model element allows multiple output ports.</span></span>  
  
## <a name="steps-in-itinerary-development"></a><span data-ttu-id="7b51e-135">Itinerary 開発手順</span><span class="sxs-lookup"><span data-stu-id="7b51e-135">Steps in Itinerary Development</span></span>  
 <span data-ttu-id="7b51e-136">ESB 仲介のフローを表す、旅行プランを開発するには、通常次のアクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b51e-136">To develop an itinerary, which represents ESB mediation flow, you should typically perform the following actions:</span></span>  
  
- <span data-ttu-id="7b51e-137">モデル要素を表すメッセージの処理、日程表の手順を追加します。</span><span class="sxs-lookup"><span data-stu-id="7b51e-137">Add model elements to represent the message processing steps for your itinerary.</span></span> <span data-ttu-id="7b51e-138">旅行プラン デザイナーには、さまざまなアクションまたは重要な抽象化を表すために使用する図形を含むツールボックスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="7b51e-138">The Itinerary Designer provides a toolbox that contains shapes used to represent different actions or key abstractions.</span></span>  
  
- <span data-ttu-id="7b51e-139">スケジュール オンランプ モデルのプロパティは、Microsoft BizTalk Server 管理データベースとモデルのエクスポーターの構成への接続文字列を含めるを指定します。</span><span class="sxs-lookup"><span data-stu-id="7b51e-139">Specify itinerary model properties, which include a connection string to the Microsoft BizTalk Server management database and model exporter configuration.</span></span>  
  
- <span data-ttu-id="7b51e-140">物理 biztalk バインド入り口と傾斜をモデル要素は、受信場所と、これらのモデル要素に対応するテクノロジ エクステンダーを関連付けることによって送信ポート。</span><span class="sxs-lookup"><span data-stu-id="7b51e-140">Bind on-ramp and off-ramp model elements to physical BizTalk receive locations and send ports by associating these model elements with corresponding technology extenders.</span></span>  
  
- <span data-ttu-id="7b51e-141">エクステンダーを使用してスケジュール サービスとしてのモデル要素を関連付けるし、エクステンダーで必要なテクノロジに固有のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="7b51e-141">Associate itinerary services model elements with extenders and define technology-specific properties required by an extender.</span></span> <span data-ttu-id="7b51e-142">これらのプロパティでは、特定の種類の extender; が異なる可能性があります。itinerary 仲介サービス プロパティとその実行時コンポーネントとの成果物に関連付けられている BizTalk 固有のプロパティが表すことができます。</span><span class="sxs-lookup"><span data-stu-id="7b51e-142">These properties may vary for a particular type of the extender; they can represent itinerary mediation service properties and BizTalk-specific properties associated with its run-time components and artifacts.</span></span>  
  
- <span data-ttu-id="7b51e-143">スケジュール オンランプ仲介サービスとして参照するカスタム コンポーネントを特定します。</span><span class="sxs-lookup"><span data-stu-id="7b51e-143">Identify custom components that you might want to reference as itinerary mediation services.</span></span> <span data-ttu-id="7b51e-144">たとえば、スケジュール サービスとしてのオーケストレーションを開発する場合があります。</span><span class="sxs-lookup"><span data-stu-id="7b51e-144">For example, you may develop an orchestration as the itinerary service.</span></span>  
  
- <span data-ttu-id="7b51e-145">に対して競合回避モジュール モデル要素の設定を確認して[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]デザイナー画面からリゾルバー サービスを呼び出すことによって実行時の構成。</span><span class="sxs-lookup"><span data-stu-id="7b51e-145">Verify resolver model element settings against [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] run-time configuration by invoking resolver service from the designer surface.</span></span>  
  
- <span data-ttu-id="7b51e-146">検証し、エクスポーターを使用してスケジュールの実行時ポリシーをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="7b51e-146">Validate and export the itinerary run-time policy using an exporter.</span></span> <span data-ttu-id="7b51e-147">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]旅行プラン デザイナーを使用した 2 つのエクスポートを提供します。 ファイル エクスポーターとデータベース エクスポーターします。</span><span class="sxs-lookup"><span data-stu-id="7b51e-147">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides two exporters with the Itinerary Designer: file exporter and database exporter.</span></span> <span data-ttu-id="7b51e-148">または、カスタム エクスポーターを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="7b51e-148">Alternatively, you can implement a custom exporter.</span></span>  
  
- <span data-ttu-id="7b51e-149">クライアント アプリケーションのテストまたは BizUnit フレームワークを使用して、旅行プランをテストします。</span><span class="sxs-lookup"><span data-stu-id="7b51e-149">Test your itinerary using test client applications or BizUnit framework.</span></span>  
  
## <a name="security-considerations-for-developing-itineraries"></a><span data-ttu-id="7b51e-150">スケジュールを開発するためのセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="7b51e-150">Security Considerations for Developing Itineraries</span></span>  
 <span data-ttu-id="7b51e-151">スケジュールを設計するときは、潜在的なセキュリティの問題を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="7b51e-151">When you design itineraries, you should consider potential security issues:</span></span>  
  
-   <span data-ttu-id="7b51e-152">モデルのプロパティからの証明書を使用せずにユーザーの資格情報を指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="7b51e-152">Avoid specifying user credentials without using a certificate from the model properties.</span></span>  
  
-   <span data-ttu-id="7b51e-153">BizTalk を参照しない受信ポートと受信の匿名アクセスを許可する場所。</span><span class="sxs-lookup"><span data-stu-id="7b51e-153">Do not refer to BizTalk receive ports with receive locations that allow anonymous access.</span></span>  
  
-   <span data-ttu-id="7b51e-154">スケジュール オンランプ メッセージに機密データが含まれている場合は、メッセージまたはトランスポート チャネルを保護します。</span><span class="sxs-lookup"><span data-stu-id="7b51e-154">Protect the message or transport channel if the itinerary message contains sensitive data.</span></span>  
  
-   <span data-ttu-id="7b51e-155">メッセージには、転送中に保護する必要がある機密データが含まれている場合は、パイプライン コンポーネントを含むメッセージ ボックスにメッセージを保護します。</span><span class="sxs-lookup"><span data-stu-id="7b51e-155">Protect messages in the Message box with a pipeline component if the messages contain sensitive data that needs to be protected while in transit.</span></span>