---
title: '方法: ESB 入り口を使用して、メッセージの検証 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43dfc791-7cb6-45a4-898f-f53def199c08
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62df8ec8628353aa127ed6cde8380e5724ddf12a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020570"
---
# <a name="how-to-validate-a-message-using-an-esb-on-ramp"></a><span data-ttu-id="b3fa5-102">方法: ESB 入り口を使用して、メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="b3fa5-102">How to: Validate a Message Using an ESB On-Ramp</span></span>
## <a name="goal"></a><span data-ttu-id="b3fa5-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="b3fa5-103">Goal</span></span>  
 <span data-ttu-id="b3fa5-104">このセクションでは、ESB 入り口に送信された XML メッセージのメッセージの検証を実行する ESB ディスパッチャー逆アセンブル パイプライン コンポーネントを構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-104">This section demonstrates how to configure the ESB Dispatcher Disassemble pipeline component to perform message validation for XML messages submitted to an ESB on-ramp.</span></span>  
  
 <span data-ttu-id="b3fa5-105">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="b3fa5-106">ESB 入り口を使用するを作成、 **ItinerarySelectReceiveXml**パイプライン。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-106">Create an ESB on-ramp that uses the **ItinerarySelectReceiveXml** pipeline.</span></span>  
  
-   <span data-ttu-id="b3fa5-107">メッセージの内容を検証する ESB ディスパッチャー逆アセンブル パイプライン コンポーネントを構成します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-107">Configure the ESB Dispatcher Disassemble pipeline component to validate message content.</span></span>  
  
-   <span data-ttu-id="b3fa5-108">適切なスケジュールを解決するのには、スケジュール セレクターのパイプライン コンポーネントを構成します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-108">Configure the Itinerary Selector pipeline component to resolve the appropriate itinerary.</span></span>  
  
-   <span data-ttu-id="b3fa5-109">有効なメッセージと、無効なメッセージを使用してメッセージの検証をテストします。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-109">Test message validation using a valid message and an invalid message.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b3fa5-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="b3fa5-110">Prerequisites</span></span>  
 <span data-ttu-id="b3fa5-111">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-111">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="b3fa5-112">はじめに</span><span class="sxs-lookup"><span data-stu-id="b3fa5-112">Before You Begin</span></span>  
 <span data-ttu-id="b3fa5-113">この操作方法に関するトピックの後半の手順を実行する前に、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-113">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
- <span data-ttu-id="b3fa5-114">無効なテスト メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-114">Create an invalid test message.</span></span>  
  
- <span data-ttu-id="b3fa5-115">ESB スケジュール オンランプ ドメイン固有言語 (DSL) モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-115">Create an ESB itinerary domain-specific language (DSL) model.</span></span>  
  
- <span data-ttu-id="b3fa5-116">旅行プランのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-116">Configure the properties of the itinerary.</span></span>  
  
- <span data-ttu-id="b3fa5-117">旅行プランの構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-117">Define the structure of the itinerary.</span></span>  
  
- <span data-ttu-id="b3fa5-118">モデルは、行程データベースをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-118">Export the model to the Itinerary database.</span></span>  
  
  <span data-ttu-id="b3fa5-119">次の手順では、これらの各方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-119">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-create-an-invalid-test-message"></a><span data-ttu-id="b3fa5-120">無効なテスト メッセージを作成するには</span><span class="sxs-lookup"><span data-stu-id="b3fa5-120">To create an invalid test message</span></span>  
  
1.  <span data-ttu-id="b3fa5-121">Windows エクスプ ローラーでは、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-121">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="b3fa5-122">NAOrderDoc.xml のコピーを作成して、コピー Invalid.xml を変更します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-122">Create a copy of NAOrderDoc.xml, and then rename the copy Invalid.xml.</span></span>  
  
3.  <span data-ttu-id="b3fa5-123">メモ帳で Invalid.xml を開きます。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-123">In Notepad, open Invalid.xml.</span></span>  
  
4.  <span data-ttu-id="b3fa5-124">変更**\<ns0:requestType\>10\</ns0:requestType\>に\<ns0:requestType\>10\</ns0:requestType\>**.</span><span class="sxs-lookup"><span data-stu-id="b3fa5-124">Change **\<ns0:requestType\>10\</ns0:requestType\> to \<ns0:requestType\>TEN\</ns0:requestType\>**.</span></span>  
  
5.  <span data-ttu-id="b3fa5-125">Invalid.xml を utf-8 として保存し、メモ帳を終了します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-125">Save Invalid.xml as UTF-8, and then close Notepad.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b3fa5-126">この要素の数値をテキストに変更すると、メッセージできなくスキーマに対して無効です。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-126">By changing the numerical value of this element to text, the message will no longer be valid according to the schema.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="b3fa5-127">ESB スケジュール オンランプ DSL モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="b3fa5-127">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="b3fa5-128">Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-128">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="b3fa5-129">ソリューション エクスプ ローラーで右クリック**ItineraryLibrary**、 をポイント**追加**、 をクリックし、**新しいスケジュール**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-129">In Solution Explorer, right-click **ItineraryLibrary**, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="b3fa5-130">**新しい項目の追加**ダイアログ ボックスに「**検証**で、**名前**ボックスをクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-130">In the **Add New Item** dialog box, type **Validation** in the **Name** box, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="b3fa5-131">旅行プランのプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="b3fa5-131">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="b3fa5-132">Visual Studio でのデザイン画面をクリックします。 **Validation.itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-132">In Visual Studio, click the design surface of **Validation.itinerary**.</span></span> <span data-ttu-id="b3fa5-133">**検証**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-133">In the **Validation** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="b3fa5-134">**モデル エクスポーター**ドロップダウン リストでは、をクリックして**データベース行程エクスポーター**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-134">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="b3fa5-135">横にある省略記号ボタン (…) をクリックして、**行程データベース**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-135">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    3.  <span data-ttu-id="b3fa5-136">**接続プロパティ**ダイアログ ボックスは itinerary リポジトリ データベースをホストする SQL Server を選択し、データベースの名前を指定し (既定の名前は**EsbItineraryDb**)。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-136">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
2.  <span data-ttu-id="b3fa5-137">**行程状態**ドロップダウン リストでは、をクリックして**配置済み**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-137">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b3fa5-138">この手順では、旅行プランを中央のリポジトリにエクスポートできます。スケジュールを選択し、メッセージが受信したときに、このリポジトリからアタッチします。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-138">This step enables you to export the itinerary to a central repository; itineraries can be selected and attached from this repository when the message is received.</span></span> <span data-ttu-id="b3fa5-139">後で、静的な競合回避モジュールを使用してこのリポジトリから適切な旅行プランを選択するスケジュール セレクターのパイプライン コンポーネントを構成します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-139">You will later configure the Itinerary Selector pipeline component to use a static resolver to select the appropriate itinerary from this repository.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="b3fa5-140">旅行プランの構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="b3fa5-140">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="b3fa5-141">ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-141">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="b3fa5-142">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-142">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="b3fa5-143">をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-143">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="b3fa5-144">**エクステンダー**ドロップダウン リストでは、をクリックして**入口 ESB エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-144">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="b3fa5-145">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-145">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="b3fa5-146">**受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-146">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="b3fa5-147">ツールボックスからドラッグ、**傾斜をオフ**デザイン画面に要素をモデル化し、既存のモデル要素の右側に配置します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-147">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the existing model element.</span></span> <span data-ttu-id="b3fa5-148">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-148">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="b3fa5-149">をクリックして、**名前**プロパティ、および入力**SendNAOrder**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-149">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="b3fa5-150">**エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-150">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="b3fa5-151">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-151">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="b3fa5-152">**送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-152">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="b3fa5-153">ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **ReceiveNAOrder**モデル要素と**SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-153">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="b3fa5-154">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-154">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="b3fa5-155">をクリックして、**名前**プロパティ、および入力**SendPortFilter**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-155">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="b3fa5-156">**行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ エクステンダー**。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-156">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="b3fa5-157">**傾斜オフ**ドロップダウン リストで、展開**SendNAOrder**、順にクリックします**送信ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-157">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="b3fa5-158">右クリックし、**リゾルバー**のコレクション、 **SendPortFilter**要素、およびクリック**新しいリゾルバーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-158">Right-click the **Resolver** collection of the **SendPortFilter** element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="b3fa5-159">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-159">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="b3fa5-160">をクリックして、**名前**プロパティ、および入力**ConfigureOffRamp**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-160">Click the **Name** property, and then type **ConfigureOffRamp**.</span></span>  
  
    2.  <span data-ttu-id="b3fa5-161">**リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-161">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="b3fa5-162">**トランスポート名**ドロップダウン リストでは、をクリックして**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-162">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="b3fa5-163">をクリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\Validated%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-163">Click the **Transport Location** property, and then type **C:\HowTos\Out\Validated%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="b3fa5-164">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-164">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="b3fa5-165">接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **SendPortFilter**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-165">Drag a connection from the **ReceiveNAOrder** model element to the **SendPortFilter** model element.</span></span>  
  
6.  <span data-ttu-id="b3fa5-166">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-166">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="b3fa5-167">接続をドラッグして、 **SendPortFilter**モデル要素に、 **SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-167">Drag a connection from the **SendPortFilter** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a><span data-ttu-id="b3fa5-168">行程データベースにモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="b3fa5-168">To export the model to the itinerary database</span></span>  
  
1.  <span data-ttu-id="b3fa5-169">Visual Studio でのデザイン画面を右クリックし、**検証**旅行プランをクリックして**モデルのエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-169">In Visual Studio, right-click the design surface of the **Validation** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b3fa5-170">旅行プランは、行程データベースにエクスポートされ、旅程セレクターのパイプライン コンポーネントで使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-170">The itinerary has been exported to the itinerary database and can now be used by the Itinerary Selector pipeline component.</span></span>  
  
2.  <span data-ttu-id="b3fa5-171">すべてのプロジェクト成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-171">Save all project artifacts.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="b3fa5-172">手順</span><span class="sxs-lookup"><span data-stu-id="b3fa5-172">Steps</span></span>  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a><span data-ttu-id="b3fa5-173">作成および ESB 入り口を構成するには</span><span class="sxs-lookup"><span data-stu-id="b3fa5-173">To create and configure an ESB on-ramp</span></span>  
  
1.  <span data-ttu-id="b3fa5-174">クリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-174">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="b3fa5-175">BizTalk Server 管理コンソールで  **BizTalk グループ**、展開**アプリケーション**、順に展開**Microsoft.Practices.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-175">In the BizTalk Server Administration Console, expand **BizTalk Group**, expand **Applications**, and then expand **Microsoft.Practices.ESB**.</span></span>  
  
3.  <span data-ttu-id="b3fa5-176">右クリック**受信場所**、 をポイント**新規**、 をクリックし、**一方向の受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-176">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
4.  <span data-ttu-id="b3fa5-177">**受信ポートの選択**ダイアログ ボックスで、をクリックして**OnRamp.Itinerary**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-177">In the **Select a Receive Port** dialog box, click **OnRamp.Itinerary**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="b3fa5-178">**受信場所のプロパティ**ダイアログ ボックスに「 **OnRamp.Itinerary.HowTo**で、**名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-178">In the **Receive Location Properties** dialog box, type **OnRamp.Itinerary.HowTo** in the **Name** box.</span></span>  
  
6.  <span data-ttu-id="b3fa5-179">**型**ドロップダウン リストでは、をクリックして**ファイル**、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-179">In the **Type** drop-down list, click **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="b3fa5-180">**FILE トランスポートのプロパティ**ダイアログ ボックスに「 **C:\HowTos\DropFolder**で、**受信フォルダー**ボックスをクリック**OK**。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-180">In the **FILE Transport Properties** dialog box, type **C:\HowTos\DropFolder** in the **Receive folder** box, and then click **OK**.</span></span>  
  
#### <a name="to-configure-the-on-ramp-to-perform-message-validation"></a><span data-ttu-id="b3fa5-181">構成に導入メッセージ検証を実行するには</span><span class="sxs-lookup"><span data-stu-id="b3fa5-181">To configure the on-ramp to perform message validation</span></span>  
  
1.  <span data-ttu-id="b3fa5-182">**受信場所のプロパティ** ダイアログ ボックスで、**受信パイプライン**ドロップダウン リストでは、をクリックして**ItinerarySelectReceiveXml**、省略記号ボタン (... を順にクリックします).</span><span class="sxs-lookup"><span data-stu-id="b3fa5-182">In the **Receive Location Properties** dialog box, in the **Receive pipeline** drop-down list, click **ItinerarySelectReceiveXml**, and then click the ellipsis button (...).</span></span>  
  
2.  <span data-ttu-id="b3fa5-183">使用して、**パイプラインの構成**、以下の構成 ダイアログ ボックス**XML 逆アセンブラー**コンポーネントのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-183">Use the **Configure Pipeline** dialog box to configure the following **XML disassembler** component properties:</span></span>  
  
    1.  <span data-ttu-id="b3fa5-184">GlobalBank.Esb アプリケーションを展開し、クリックして**スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-184">Expand the GlobalBank.Esb application, and then click **Schemas**.</span></span> <span data-ttu-id="b3fa5-185">右クリックして**GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-185">Right-click **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**, and then click **Properties**.</span></span> <span data-ttu-id="b3fa5-186">コピー、**名前**と**アセンブリ**プロパティのテキスト ファイルに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-186">Copy the **Name** and **Assembly** properties and paste them into a text file.</span></span>  
  
    2.  <span data-ttu-id="b3fa5-187">**逆アセンブル**コンポーネント、 をクリックして**True**で、 **ValidateDocument**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-187">In the **Disassemble** component, click **True** in the **ValidateDocument** drop-down list.</span></span>  
  
    3.  <span data-ttu-id="b3fa5-188">をクリックして、 **DocumentSpecNames**プロパティ、およびスキーマの完全修飾名を入力します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-188">Click the **DocumentSpecNames** property, and then type the fully qualified name of the schema.</span></span> <span data-ttu-id="b3fa5-189">完全修飾名が名前で始まるし、コンマと手順で抽出されたアセンブリの情報が続きますをします。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-189">The fully qualified name starts with the name and is followed by a comma and the assembly information extracted in step a.</span></span> <span data-ttu-id="b3fa5-190">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-190">The following is an example:</span></span>  
  
         <span data-ttu-id="b3fa5-191">GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc、GlobalBank.ESB.DynamicResolution.Schemas、バージョン 2.0.0.0、Culture = neutral, PublicKeyToken = c2c8b2b87f54180a を =</span><span class="sxs-lookup"><span data-stu-id="b3fa5-191">GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc, GlobalBank.ESB.DynamicResolution.Schemas, Version=2.0.0.0, Culture=neutral, PublicKeyToken=c2c8b2b87f54180a</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="b3fa5-192">これは、スキーマ検証の完全修飾名です。スキーマ名と 4 つのアセンブリ プロパティで構成されています。 アセンブリ名、バージョン、カルチャ、および公開キー トークン。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-192">This is the fully qualified name of the schema to be validated; it is comprised of the schema name and four assembly properties: assembly name, version, culture, and public key token.</span></span> <span data-ttu-id="b3fa5-193">複数の値が許可されます。複数のスキーマをパイプで区切ります (&#124;) シンボル。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-193">Multiple values are allowed; separate multiple schemas with a pipe (&#124;) symbol.</span></span>  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a><span data-ttu-id="b3fa5-194">旅行プラン セレクターのパイプライン コンポーネントを構成するには</span><span class="sxs-lookup"><span data-stu-id="b3fa5-194">To configure the Itinerary Selector Pipeline component</span></span>  
  
1.  <span data-ttu-id="b3fa5-195">**パイプラインの構成** ダイアログ ボックスで、次の構成**スケジュール セレクター**コンポーネントのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-195">In the **Configure Pipeline** dialog box, configure the following **Itinerary Selector** component properties:</span></span>  
  
    1.  <span data-ttu-id="b3fa5-196">をクリックして、 **ItineraryFactKey**プロパティ、および入力**Resolver.Itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-196">Click the **ItineraryFactKey** property, and then type **Resolver.Itinerary**.</span></span>  
  
    2.  <span data-ttu-id="b3fa5-197">をクリックして、 **ResolverConnectionString**プロパティ、および入力**行程:\\\name=Validation;** します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-197">Click the **ResolverConnectionString** property, and then type **ITINERARY:\\\name=Validation;**.</span></span>  
  
    3.  <span data-ttu-id="b3fa5-198">クリックして**OK**を閉じる、**パイプラインの構成** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-198">Click **OK** to close the **Configure Pipeline** dialog box.</span></span>  
  
2.  <span data-ttu-id="b3fa5-199">クリックして**OK**を閉じる、**受信場所のプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-199">Click **OK** to close the **Receive Location Properties** dialog box.</span></span>  
  
3.  <span data-ttu-id="b3fa5-200">右クリックし、BizTalk Server 管理コンソールで、 **OnRamp.Itinerary.HowTo**受信場所をクリックして**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-200">In the BizTalk Server Administration Console, right-click the **OnRamp.Itinerary.HowTo** receive location, and then click **Enable**.</span></span>  
  
#### <a name="to-test-the-message-validation-and-itinerary-selection"></a><span data-ttu-id="b3fa5-201">メッセージの検証とスケジュールの選択をテストするには</span><span class="sxs-lookup"><span data-stu-id="b3fa5-201">To test the message validation and itinerary selection</span></span>  
  
1.  <span data-ttu-id="b3fa5-202">Windows エクスプ ローラーでは、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-202">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="b3fa5-203">コピー (移動しないでください) NAOrderDoc.xml DropFolder フォルダーにします。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-203">Copy (do not move) NAOrderDoc.xml to the DropFolder folder.</span></span>  
  
3.  <span data-ttu-id="b3fa5-204">C:\HowTos\Out に移動します。Validated%MessageID%.xml がディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-204">Browse to C:\HowTos\Out. Verify that Validated%MessageID%.xml has been written to the directory.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b3fa5-205">期待どおりに、有効なメッセージは、そのスケジュールに基づくルーティングを完了します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-205">The valid message completed its itinerary-based routing, as expected.</span></span>  
  
4.  <span data-ttu-id="b3fa5-206">Validated%MessageID%.xml を Out フォルダから削除します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-206">Delete Validated%MessageID%.xml from the Out folder.</span></span>  
  
5.  <span data-ttu-id="b3fa5-207">Windows エクスプ ローラーでは、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-207">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
6.  <span data-ttu-id="b3fa5-208">コピー (移動しないでください) Invalid.xml DropFolder フォルダーにします。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-208">Copy (do not move) Invalid.xml to the DropFolder folder.</span></span>  
  
7.  <span data-ttu-id="b3fa5-209">C:\HowTos\Out に移動します。新しいメッセージが配信されないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-209">Browse to C:\HowTos\Out. Verify that no new message has been delivered.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b3fa5-210">メッセージを検証できませんでした。そのため、スケジュールに基づくルーティングできませんでした。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-210">The message could not be validated; therefore, itinerary-based routing could not be completed.</span></span>  
  
8.  <span data-ttu-id="b3fa5-211">をクリックして**開始**タスク バーで、をポイント**管理ツール**、 をクリックし、**イベント ビューアー**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-211">Click **Start** on the taskbar, point to **Administrative Tools**, and then click **Event Viewer**.</span></span>  
  
9. <span data-ttu-id="b3fa5-212">イベント ビューアーで、展開**Windows ログ**、 をクリックし、**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-212">In Event Viewer, expand **Windows Logs**, and then click **Application**.</span></span>  
  
10. <span data-ttu-id="b3fa5-213">最近のイベントを検索場所、**ソース**は**BizTalk Server**、および**イベント ID**は**5719**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-213">Locate a recent event where the **Source** is **BizTalk Server**, and the **Event ID** is **5719**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b3fa5-214">送信と、無効なメッセージの失敗、アプリケーション イベント ログに例外のエントリでが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-214">The submission and failure of the invalid message resulted in an exception entry to the application event log.</span></span>  
  
11. <span data-ttu-id="b3fa5-215">右クリックし、BizTalk Server 管理コンソールで、 **OnRamp.Itinerary.HowTo**受信場所をクリックして**を無効にする**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-215">In the BizTalk Server Administration Console, right-click the **OnRamp.Itinerary.HowTo** receive location, and then click **Disable**.</span></span>  
  
12. <span data-ttu-id="b3fa5-216">後に、 **OnRamp.Itinerary.HowTo**受信場所が無効になっている、右クリックし、 をクリックし、**削除**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-216">After the **OnRamp.Itinerary.HowTo** receive location is disabled, right-click it, and then click **Delete**.</span></span> <span data-ttu-id="b3fa5-217">**削除の確認の受信場所**ダイアログ ボックスで、をクリックして**はい**します。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-217">In the **Confirm delete receive location** dialog box, click **Yes**.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="b3fa5-218">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="b3fa5-218">Additional Resources</span></span>  
 <span data-ttu-id="b3fa5-219">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3fa5-219">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="b3fa5-220">方法: ビジネス ルール ポリシーを使用して、日程を選択</span><span class="sxs-lookup"><span data-stu-id="b3fa5-220">How to: Select an Itinerary Using a Business Rules Policy</span></span>](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [<span data-ttu-id="b3fa5-221">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="b3fa5-221">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="b3fa5-222">動的解決サンプルをインストールし、実行する</span><span class="sxs-lookup"><span data-stu-id="b3fa5-222">Installing and Running the Dynamic Resolution Sample</span></span>](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)