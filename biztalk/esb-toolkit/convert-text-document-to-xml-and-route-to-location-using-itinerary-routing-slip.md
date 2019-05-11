---
title: 操作方法:XML に、スケジュール ルーティング スリップを使用してファイルの場所にテキスト ドキュメントを変換 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01597a5f-5ca3-440e-ad97-70332233f319
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9258493ebd15e12bcb10d4a4dba51a14fdb51c0c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302052"
---
# <a name="how-to-convert-a-text-document-to-xml-and-route-to-a-file-location-using-an-itinerary-routing-slip"></a><span data-ttu-id="84c5f-102">操作方法:テキスト ドキュメントを XML と、スケジュール ルーティング スリップを使用してファイルの場所へのルートに変換します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-102">How to: Convert a Text Document to XML and Route to a File Location Using an Itinerary Routing Slip</span></span>
## <a name="goal"></a><span data-ttu-id="84c5f-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="84c5f-103">Goal</span></span>  
 <span data-ttu-id="84c5f-104">セクションでは、テキスト ドキュメントを XML に変換し、適切な旅行プランを選択し、ファイルの場所にメッセージをルーティングするパイプラインを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-104">The section demonstrates how to create a pipeline that will convert a text document to XML and then select the appropriate itinerary and route the message to a FILE location.</span></span>  
  
 <span data-ttu-id="84c5f-105">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="84c5f-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="84c5f-106">パイプラインを使用して、フラット ファイル ドキュメントを受信し、XML に変換します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-106">Use a pipeline to receive a flat file document and convert it to XML.</span></span>  
  
-   <span data-ttu-id="84c5f-107">適切なルーティング スリップを解決するのには、スケジュール セレクターのパイプライン コンポーネントを構成します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-107">Configure the Itinerary Selector pipeline component to resolve the appropriate routing slip.</span></span>  
  
-   <span data-ttu-id="84c5f-108">入り口カスタム パイプラインを使用するを作成します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-108">Create an on-ramp that uses the custom pipeline.</span></span>  
  
-   <span data-ttu-id="84c5f-109">スケジュールに基づくフラット ファイル メッセージのルーティングをテストします。</span><span class="sxs-lookup"><span data-stu-id="84c5f-109">Test itinerary-based routing of a flat file message.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="84c5f-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="84c5f-110">Prerequisites</span></span>  
 <span data-ttu-id="84c5f-111">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-111">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="84c5f-112">はじめに</span><span class="sxs-lookup"><span data-stu-id="84c5f-112">Before You Begin</span></span>  
 <span data-ttu-id="84c5f-113">この操作方法に関するトピックの後半の手順を実行する前に、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-113">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
- <span data-ttu-id="84c5f-114">展開、 **DataFormatTransformation**スケジュールします。</span><span class="sxs-lookup"><span data-stu-id="84c5f-114">Deploy the **DataFormatTransformation** itinerary.</span></span>  
  
- <span data-ttu-id="84c5f-115">テスト メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-115">Create the test message.</span></span>  
  
  <span data-ttu-id="84c5f-116">次の手順では、これらの各方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-116">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-deploy-the-dataformattransformation-itinerary"></a><span data-ttu-id="84c5f-117">DataFormatTransformation 旅行プランをデプロイするには</span><span class="sxs-lookup"><span data-stu-id="84c5f-117">To deploy the DataFormatTransformation itinerary</span></span>  
  
1.  <span data-ttu-id="84c5f-118">Visual Studio で、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation\DataFormatTransformation.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="84c5f-118">In Visual Studio, open C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation\DataFormatTransformation.sln.</span></span>  
  
2.  <span data-ttu-id="84c5f-119">ソリューション エクスプ ローラーで、 **Itinerary.Library**プロジェクトをダブルクリックします**DataFormatTransformation.itinerary**旅行プラン デザイナーで開きます。</span><span class="sxs-lookup"><span data-stu-id="84c5f-119">In Solution Explorer, in the **Itinerary.Library** project, double-click **DataFormatTransformation.itinerary** to open it in the Itinerary Designer.</span></span>  
  
3.  <span data-ttu-id="84c5f-120">Visual Studio でのデザイン画面をクリックします。 **DataFormatTransformation.itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-120">In Visual Studio, click the design surface of **DataFormatTransformation.itinerary**.</span></span> <span data-ttu-id="84c5f-121">**DataFormatTransformation.itinerary**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-121">In the **DataFormatTransformation.itinerary** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="84c5f-122">**行程状態**ドロップダウン リストでは、をクリックして**配置済み**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-122">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    2.  <span data-ttu-id="84c5f-123">**モデル エクスポーター**ドロップダウン リストでは、をクリックして**データベース行程エクスポーター**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-123">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    3.  <span data-ttu-id="84c5f-124">横にある省略記号ボタン (…) をクリックして、**行程データベース**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="84c5f-124">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    4.  <span data-ttu-id="84c5f-125">**接続プロパティ**ダイアログ ボックスは itinerary リポジトリ データベースをホストする SQL Server を選択し、データベースの名前を指定し (既定の名前は**EsbItineraryDb**)。</span><span class="sxs-lookup"><span data-stu-id="84c5f-125">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
4.  <span data-ttu-id="84c5f-126">すべてのプロジェクト成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-126">Save all project artifacts.</span></span>  
  
5.  <span data-ttu-id="84c5f-127">Visual Studio でのデザイン画面を右クリックし、 **DataModelTransformation**旅行プランをクリックして**モデルのエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-127">In Visual Studio, right-click the design surface of the **DataModelTransformation** itinerary, and then click **Export Model**.</span></span>  
  
#### <a name="to-create-the-receive-pipeline"></a><span data-ttu-id="84c5f-128">受信パイプラインを作成するには</span><span class="sxs-lookup"><span data-stu-id="84c5f-128">To create the receive pipeline</span></span>  
  
1.  <span data-ttu-id="84c5f-129">Visual Studio で、右クリックして**DataFormatTransformation.Schemas**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-129">In Visual Studio, right-click **DataFormatTransformation.Schemas**, and then click **Properties**.</span></span> <span data-ttu-id="84c5f-130">クリックして**アプリケーション**、し、入力**GlobalBank.ESB.DataFormatTransformation.Schemas**で、**アセンブリ名**ボックス。</span><span class="sxs-lookup"><span data-stu-id="84c5f-130">Click **Application**, and then type **GlobalBank.ESB.DataFormatTransformation.Schemas** in the **Assembly name** box.</span></span>  
  
2.  <span data-ttu-id="84c5f-131">右クリックして**DataFormatTransformation.Schemas**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-131">Right-click **DataFormatTransformation.Schemas**, and then click **Properties**.</span></span> <span data-ttu-id="84c5f-132">クリックして**署名**、ことを確認し、**アセンブリに署名** チェック ボックスが選択されていること、およびアセンブリの場所を指す **.\\.\\..\\..\\..\\..\keys\Microsoft.Practices.ESB.snk**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-132">Click **Signing**, and then verify that the **Sign the assembly** check box is selected and that the assembly location points to **.\\..\\..\\..\\..\\..\keys\Microsoft.Practices.ESB.snk**.</span></span>  
  
3.  <span data-ttu-id="84c5f-133">右クリック**DataFormatTransformation.Pipelines**、 をクリックし、**削除**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-133">Right-click **DataFormatTransformation.Pipelines**, and then click **Remove**.</span></span>  
  
4.  <span data-ttu-id="84c5f-134">右クリック**DataFormatTransformation**、 をポイント**追加**、 をクリックし、**新しいプロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-134">Right-click **DataFormatTransformation**, point to **Add**, and then click **New Project**.</span></span> <span data-ttu-id="84c5f-135">クリックして**Biztalk プロジェクト**、 をクリックし、**空の Biztalk Server プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-135">Click **Biztalk Projects**, and then click **Empty Biztalk Server Project**.</span></span> <span data-ttu-id="84c5f-136">**名前**ボックスに「 **DataFormatTransformationReceive.Pipeline**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-136">In the **Name** box, type **DataFormatTransformationReceive.Pipeline**.</span></span>  
  
5.  <span data-ttu-id="84c5f-137">右クリックして**DataFormatTransformationReceive.Pipeline**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-137">Right-click **DataFormatTransformationReceive.Pipeline**, and then click **Properties**.</span></span> <span data-ttu-id="84c5f-138">クリックして**署名**、ことを確認し、**アセンブリに署名** チェック ボックスが選択されていること、およびアセンブリの場所を指す**C:\projects\Microsoft.Practices.ESB\keys\Microsoft.Practices.ESB.snk**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-138">Click **Signing**, and then verify that the **Sign the assembly** check box is selected and that the assembly location points to **C:\projects\Microsoft.Practices.ESB\keys\Microsoft.Practices.ESB.snk**.</span></span>  
  
6.  <span data-ttu-id="84c5f-139">右クリック**DataFormatTransformationReceive.Pipeline**、 をポイント**追加**、 をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-139">Right-click **DataFormatTransformationReceive.Pipeline**, point to **Add**, and then click **New Item**.</span></span>  
  
7.  <span data-ttu-id="84c5f-140">**新しい項目の追加**ダイアログ ボックスで、をクリックして**受信パイプライン**テンプレート ペインでします。</span><span class="sxs-lookup"><span data-stu-id="84c5f-140">In the **Add New Item** dialog box, click **Receive Pipeline** in the Templates pane.</span></span> <span data-ttu-id="84c5f-141">**名前**ボックスに「 **ItinerarySelectReceiveFF**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-141">In the **Name** box, type **ItinerarySelectReceiveFF**, and then click **Add**.</span></span>  
  
8.  <span data-ttu-id="84c5f-142">右クリックして**参照**DataFormatTransformationReceive.Pipeline プロジェクト、およびクリック**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-142">Right-click **References** for the DataFormatTransformationReceive.Pipeline project, and then click **Add Reference**.</span></span> <span data-ttu-id="84c5f-143">をクリックして、**プロジェクト**タブをクリックし、をクリックし、 **DataFormatTransformation.Schemas**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-143">Click the **Projects** tab, and then click **DataFormatTransformation.Schemas**.</span></span> <span data-ttu-id="84c5f-144">クリックして**OK**参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-144">Click **OK** to add the reference.</span></span>  
  
9. <span data-ttu-id="84c5f-145">ツールボックスからドラッグして、**フラット ファイル逆アセンブラー**パイプライン コンポーネントを**逆アセンブル**パイプラインのステージ。</span><span class="sxs-lookup"><span data-stu-id="84c5f-145">From the Toolbox, drag a **Flat file disassembler** pipeline component to the **Disassemble** stage of the pipeline.</span></span>  
  
10. <span data-ttu-id="84c5f-146">逆アセンブル、フラット ファイルのプロパティ ウィンドウで、をクリックして**DataModelTransformation.Schemas.NAOrderDocFF**で、**ドキュメント スキーマ**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="84c5f-146">In the Properties window for the flat file disassemble, click **DataModelTransformation.Schemas.NAOrderDocFF** in the **Document schema** drop-down list.</span></span>  
  
11. <span data-ttu-id="84c5f-147">ツールボックスからドラッグして、 **ESB スケジュール セレクター**パイプライン コンポーネントを**パーティの解決**パイプラインのステージ。</span><span class="sxs-lookup"><span data-stu-id="84c5f-147">From the Toolbox, drag an **ESB Itinerary Selector** pipeline component to the **Resolve Party** stage of the pipeline.</span></span>  
  
12. <span data-ttu-id="84c5f-148">ツールボックスからドラッグ、 **ESB ディスパッチャー**パイプライン コンポーネントを**パーティの解決**、パイプラインのステージと、下に配置し、 **ESB スケジュール セレクター**パイプラインコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="84c5f-148">From the Toolbox, drag an **ESB Dispatcher** pipeline component to the **Resolve Party** stage of the pipeline, and then place it under the **ESB Itinerary Selector** pipeline component.</span></span>  
  
13. <span data-ttu-id="84c5f-149">すべてのプロジェクト成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-149">Save all project artifacts.</span></span>  
  
## <a name="to-create-the-test-message"></a><span data-ttu-id="84c5f-150">テスト メッセージを作成するには</span><span class="sxs-lookup"><span data-stu-id="84c5f-150">To create the test message</span></span>  
  
1.  <span data-ttu-id="84c5f-151">DataFormatTransformation.Schemas プロジェクトの NAOrderDocFF.xsd スキーマ ファイルで 1 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="84c5f-151">Click once in the NAOrderDocFF.xsd schema file of the DataFormatTransformation.Schemas project.</span></span> <span data-ttu-id="84c5f-152">Visual Studio の [プロパティ] ペインでは、次の 2 つのプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-152">In the Properties pane of Visual Studio, change the following two properties:</span></span>  
  
    -   <span data-ttu-id="84c5f-153">**インスタンスの出力の種類の生成**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-153">**Generate Instance Output Type**.</span></span> <span data-ttu-id="84c5f-154">ドロップダウン リストに変更するには、このプロパティをクリックして**ネイティブ**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-154">Click the drop-down list for this property to change it to **Native**.</span></span>  
  
    -   <span data-ttu-id="84c5f-155">**出力インスタンス ファイル名**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-155">**Output Instance Filename**.</span></span> <span data-ttu-id="84c5f-156">このプロパティの省略記号ボタン (…) をクリックし、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation の既定のパスをそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-156">Click the ellipsis button (…) for this property and accept the default path of C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation.</span></span> <span data-ttu-id="84c5f-157">**ファイル名**ボックスに「 **NAOrderDocFF**、 をクリックし、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-157">In the **File name** box, type **NAOrderDocFF**, and then click **Save**.</span></span>  
  
2.  <span data-ttu-id="84c5f-158">右クリック**NAOrderDocFF.xsd** [ **DataFormatTransformation.Schemas**、] をクリックし、**インスタンスの生成**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-158">Right-click **NAOrderDocFF.xsd** under **DataFormatTransformation.Schemas**, and then click **Generate Instance**.</span></span> <span data-ttu-id="84c5f-159">この時点では、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation ディレクトリに生成された新しいファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="84c5f-159">At this point, you should have a new file generated in the C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation directory.</span></span>  
  
3.  <span data-ttu-id="84c5f-160">コピー (移動しないでください) に C:\HowTos C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation から NAOrderDocFF.txt ファイル。</span><span class="sxs-lookup"><span data-stu-id="84c5f-160">Copy (do not move) the file NAOrderDocFF.txt from C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation to C:\HowTos.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="84c5f-161">これは、メッセージはメッセージを受信して XML に変換します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-161">This is the message you will receive and convert to XML.</span></span> <span data-ttu-id="84c5f-162">このドキュメントでは、North American 注文ドキュメントのフラット ファイルのバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-162">This document represents a flat file version of North American Order document.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="84c5f-163">手順</span><span class="sxs-lookup"><span data-stu-id="84c5f-163">Steps</span></span>  
  
#### <a name="to-deploy-the-receive-pipeline-and-the-schema"></a><span data-ttu-id="84c5f-164">受信パイプラインとスキーマを展開するには</span><span class="sxs-lookup"><span data-stu-id="84c5f-164">To deploy the receive pipeline and the schema</span></span>  
  
1.  <span data-ttu-id="84c5f-165">右クリックして**DataFormatTransformationReceive.Pipeline**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-165">Right-click **DataFormatTransformationReceive.Pipeline**, and then click **Properties**.</span></span> <span data-ttu-id="84c5f-166">クリックして**展開**、し、入力**Microsoft.Practices.ESB**で、**アプリケーション名**ボックス。</span><span class="sxs-lookup"><span data-stu-id="84c5f-166">Click **Deployment**, and then type **Microsoft.Practices.ESB** in the **Application Name** box.</span></span>  
  
2.  <span data-ttu-id="84c5f-167">右クリックし、 **DataFormatTransformation.Schemas**プロジェクトをクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-167">Right-click the **DataFormatTransformation.Schemas** project, and then click **Properties**.</span></span> <span data-ttu-id="84c5f-168">クリックして**展開**、し、入力**Microsoft.Practices.ESB**で、**アプリケーション名**ボックス。</span><span class="sxs-lookup"><span data-stu-id="84c5f-168">Click **Deployment**, and then type **Microsoft.Practices.ESB** in the **Application Name** box.</span></span>  
  
3.  <span data-ttu-id="84c5f-169">両方のプロパティ ウィンドウを閉じる**DataFormatTransformationReceive.Pipeline**と**DataFormatTransformation.Schemas**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-169">Close the Properties panes for both **DataFormatTransformationReceive.Pipeline** and **DataFormatTransformation.Schemas**.</span></span>  
  
4.  <span data-ttu-id="84c5f-170">ソリューション エクスプ ローラーで右クリックし、 **DataFormatTransformation**プロジェクトをクリックして**ソリューションの配置**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-170">In Solution Explorer, right-click the **DataFormatTransformation** project, and then click **Deploy Solution**.</span></span>  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a><span data-ttu-id="84c5f-171">作成および ESB 入り口を構成するには</span><span class="sxs-lookup"><span data-stu-id="84c5f-171">To create and configure an ESB on-ramp</span></span>  
  
1.  <span data-ttu-id="84c5f-172">クリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-172">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="84c5f-173">BizTalk Server 管理コンソールで [ **BizTalk グループ**、展開**アプリケーション**、] をクリックし、 **Microsoft.Practices.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-173">In the BizTalk Server Administration Console, expand **BizTalk Group**, expand **Applications**, and then click **Microsoft.Practices.ESB**.</span></span>  
  
3.  <span data-ttu-id="84c5f-174">右クリック**受信場所**、 をポイント**新規**、 をクリックし、**一方向の受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-174">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
4.  <span data-ttu-id="84c5f-175">**受信ポートの選択**ダイアログ ボックスで、をクリックして**OnRamp.Itinerary**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="84c5f-175">In the **Select a Receive Port** dialog box, click **OnRamp.Itinerary**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="84c5f-176">**受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに「 **OnRamp.Itinerary.FlatFile.FILE**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-176">In the **Receive Location Properties** dialog box, in the **Name** box, type **OnRamp.Itinerary.FlatFile.FILE**.</span></span>  
  
6.  <span data-ttu-id="84c5f-177">**型**ドロップダウン リストでは、をクリックして**ファイル**、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-177">In the **Type** drop-down list, click **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="84c5f-178">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**受信フォルダー**ボックスに「 **C:\HowTos\DropFolder**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-178">In the **FILE Transport Properties** dialog box, in the **Receive Folder** box, type **C:\HowTos\DropFolder**.</span></span>  
  
8.  <span data-ttu-id="84c5f-179">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**ファイル マスク**ボックスに「  **\*.txt**順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-179">In the **FILE Transport Properties** dialog box, in the **File mask** box, type **\*.txt**, and then click **OK**.</span></span>  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a><span data-ttu-id="84c5f-180">旅行プラン セレクターのパイプライン コンポーネントを構成するには</span><span class="sxs-lookup"><span data-stu-id="84c5f-180">To configure the Itinerary Selector pipeline component</span></span>  
  
1.  <span data-ttu-id="84c5f-181">**受信場所のプロパティ**ダイアログ ボックスで、をクリックして**ItinerarySelectReceiveFF**で、**受信パイプライン**ドロップダウン リストで、省略記号ボタン (…) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84c5f-181">In the **Receive Location Properties** dialog box, click **ItinerarySelectReceiveFF** in the **Receive pipeline** drop down list, and then click the ellipsis button (...).</span></span>  
  
2.  <span data-ttu-id="84c5f-182">使用して、**パイプラインの構成**、以下の構成 ダイアログ ボックス**スケジュール セレクター**コンポーネントのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="84c5f-182">Use the **Configure Pipeline** dialog box to configure the following **Itinerary Selector** component properties:</span></span>  
  
    1.  <span data-ttu-id="84c5f-183">をクリックして、 **ItineraryFactKey**プロパティ、および入力**Resolver.Itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-183">Click the **ItineraryFactKey** property, and then type **Resolver.Itinerary**.</span></span>  
  
    2.  <span data-ttu-id="84c5f-184">をクリックして、 **ResolverConnectionString**プロパティに、入力**行程:\\\name=DataFormatTransformation;** 順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="84c5f-184">Click the **ResolverConnectionString** property, type **ITINERARY:\\\name=DataFormatTransformation;** and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="84c5f-185">クリックして**OK**を閉じる、**受信場所のプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="84c5f-185">Click **OK** to close the **Receive Location Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="84c5f-186">右クリックし、BizTalk Server 管理コンソールで、 **OnRamp.Itinerary.FlatFile.FILE**受信場所をクリックして**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-186">In the BizTalk Server Administration Console, right-click the **OnRamp.Itinerary.FlatFile.FILE** receive location, and then click **Enable**.</span></span>  
  
#### <a name="to-test-itinerary-based-routing-of-a-flat-file-message"></a><span data-ttu-id="84c5f-187">スケジュールに基づくフラット ファイル メッセージのルーティングをテストするには</span><span class="sxs-lookup"><span data-stu-id="84c5f-187">To test itinerary-based routing of a flat file message</span></span>  
  
1.  <span data-ttu-id="84c5f-188">Windows エクスプ ローラーでは、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-188">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="84c5f-189">コピー (移動しないでください) NAOrderDocFF.txt C:\HowTos\DropFolder にします。</span><span class="sxs-lookup"><span data-stu-id="84c5f-189">Copy (do not move) NAOrderDocFF.txt to C:\HowTos\DropFolder.</span></span>  
  
3.  <span data-ttu-id="84c5f-190">C:\HowTos\Out に移動します。DFT%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-190">Browse to C:\HowTos\Out. Verify that the DFT%MessageID%.xml message has been written to the directory.</span></span>  
  
4.  <span data-ttu-id="84c5f-191">右クリックし、BizTalk Server 管理コンソールで、 **OnRamp.Itinerary.FlatFile.FILE**受信場所をクリックして**を無効にする**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-191">In the BizTalk Server Administration Console, right-click the **OnRamp.Itinerary.FlatFile.FILE** receive location, and then click **Disable**.</span></span>  
  
5.  <span data-ttu-id="84c5f-192">後に、 **OnRamp.Itinerary.FlatFile.FILE**受信場所が無効になっている、右クリックし、 をクリックし、**削除**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-192">After the **OnRamp.Itinerary.FlatFile.FILE** receive location is disabled, right-click it, and then click **Delete**.</span></span> <span data-ttu-id="84c5f-193">**削除の確認の受信場所**ダイアログ ボックスで、をクリックして**はい**します。</span><span class="sxs-lookup"><span data-stu-id="84c5f-193">In the **Confirm delete receive location** dialog box, click **Yes**.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="84c5f-194">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="84c5f-194">Additional Resources</span></span>  
 <span data-ttu-id="84c5f-195">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84c5f-195">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="84c5f-196">方法: メッセージを変換し、スケジュール ルーティング スリップを使用してファイルの場所に、結果のメッセージをルーティング</span><span class="sxs-lookup"><span data-stu-id="84c5f-196">How to: Transform a Message and Route the Resulting Message to a File Location Using an Itinerary Routing Slip</span></span>](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [<span data-ttu-id="84c5f-197">方法: 1 つのメッセージをスケジュール ルーティング スリップを使用して複数の受信者にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="84c5f-197">How to: Route a Single Message to Multiple Recipients Using an Itinerary Routing Slip</span></span>](../esb-toolkit/route-a-single-message-to-multiple-recipients-using-an-itinerary-routing-slip.md)  
  
-   [<span data-ttu-id="84c5f-198">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="84c5f-198">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="84c5f-199">メッセージ変換パターン</span><span class="sxs-lookup"><span data-stu-id="84c5f-199">Message Transformation Patterns</span></span>](../esb-toolkit/message-transformation-patterns.md)