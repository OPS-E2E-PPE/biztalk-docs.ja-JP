---
title: "方法: XML と旅程のルーティング先を使用してファイルの場所へのルートに、テキスト ドキュメントを変換 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 01597a5f-5ca3-440e-ad97-70332233f319
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8284c1623329133533fe03aab567b1281f07c1a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-convert-a-text-document-to-xml-and-route-to-a-file-location-using-an-itinerary-routing-slip"></a><span data-ttu-id="2bb08-102">方法: テキスト ドキュメントを XML と旅程のルーティング先を使用してファイルの場所へのルートに変換</span><span class="sxs-lookup"><span data-stu-id="2bb08-102">How to: Convert a Text Document to XML and Route to a File Location Using an Itinerary Routing Slip</span></span>
## <a name="goal"></a><span data-ttu-id="2bb08-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="2bb08-103">Goal</span></span>  
 <span data-ttu-id="2bb08-104">セクションでは、テキスト ドキュメントを XML に変換し、適切な旅程を選択し、ファイルの場所にメッセージをルーティングするパイプラインを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2bb08-104">The section demonstrates how to create a pipeline that will convert a text document to XML and then select the appropriate itinerary and route the message to a FILE location.</span></span>  
  
 <span data-ttu-id="2bb08-105">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="2bb08-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="2bb08-106">フラット ファイル ドキュメントを受信し、XML に変換するには、パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="2bb08-106">Use a pipeline to receive a flat file document and convert it to XML.</span></span>  
  
-   <span data-ttu-id="2bb08-107">適切な回覧を解決するのには、行程セレクター パイプライン コンポーネントを構成します。</span><span class="sxs-lookup"><span data-stu-id="2bb08-107">Configure the Itinerary Selector pipeline component to resolve the appropriate routing slip.</span></span>  
  
-   <span data-ttu-id="2bb08-108">入り口、カスタム パイプラインを使用するを作成します。</span><span class="sxs-lookup"><span data-stu-id="2bb08-108">Create an on-ramp that uses the custom pipeline.</span></span>  
  
-   <span data-ttu-id="2bb08-109">行程ベースのフラット ファイル メッセージのルーティングをテストします。</span><span class="sxs-lookup"><span data-stu-id="2bb08-109">Test itinerary-based routing of a flat file message.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2bb08-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="2bb08-110">Prerequisites</span></span>  
 <span data-ttu-id="2bb08-111">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-111">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="2bb08-112">はじめに</span><span class="sxs-lookup"><span data-stu-id="2bb08-112">Before You Begin</span></span>  
 <span data-ttu-id="2bb08-113">このトピックの「操作方法に関する手順を実行する前に、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="2bb08-113">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
-   <span data-ttu-id="2bb08-114">展開、 **DataFormatTransformation**行程です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-114">Deploy the **DataFormatTransformation** itinerary.</span></span>  
  
-   <span data-ttu-id="2bb08-115">テスト メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="2bb08-115">Create the test message.</span></span>  
  
 <span data-ttu-id="2bb08-116">次の手順では、これらの各を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2bb08-116">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-deploy-the-dataformattransformation-itinerary"></a><span data-ttu-id="2bb08-117">DataFormatTransformation 旅程を展開するには</span><span class="sxs-lookup"><span data-stu-id="2bb08-117">To deploy the DataFormatTransformation itinerary</span></span>  
  
1.  <span data-ttu-id="2bb08-118">Visual Studio で、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation\DataFormatTransformation.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="2bb08-118">In Visual Studio, open C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation\DataFormatTransformation.sln.</span></span>  
  
2.  <span data-ttu-id="2bb08-119">ソリューション エクスプ ローラーで、 **Itinerary.Library**プロジェクトをダブルクリックして**DataFormatTransformation.itinerary**行程デザイナーで開きます。</span><span class="sxs-lookup"><span data-stu-id="2bb08-119">In Solution Explorer, in the **Itinerary.Library** project, double-click **DataFormatTransformation.itinerary** to open it in the Itinerary Designer.</span></span>  
  
3.  <span data-ttu-id="2bb08-120">Visual Studio でのデザイン画面をクリックして**DataFormatTransformation.itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-120">In Visual Studio, click the design surface of **DataFormatTransformation.itinerary**.</span></span> <span data-ttu-id="2bb08-121">**DataFormatTransformation.itinerary**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="2bb08-121">In the **DataFormatTransformation.itinerary** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="2bb08-122">**行程ステータス**ドロップダウン リストをクリックして**配置済み**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-122">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    2.  <span data-ttu-id="2bb08-123">**モデル エクスポーター**ドロップダウン リストをクリックして**データベース行程エクスポーター**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-123">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    3.  <span data-ttu-id="2bb08-124">横にある省略記号ボタン (...) をクリックして、**行程データベース**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="2bb08-124">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    4.  <span data-ttu-id="2bb08-125">**接続プロパティ**ダイアログ ボックスで、itinerary リポジトリ データベースをホストする SQL Server を選択し、データベースの名前を指定 (既定の名前は**EsbItineraryDb**)。</span><span class="sxs-lookup"><span data-stu-id="2bb08-125">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
4.  <span data-ttu-id="2bb08-126">すべてのプロジェクトの成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="2bb08-126">Save all project artifacts.</span></span>  
  
5.  <span data-ttu-id="2bb08-127">Visual Studio でのデザイン画面を右クリックし、 **DataModelTransformation**行程をクリックして**モデルのエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-127">In Visual Studio, right-click the design surface of the **DataModelTransformation** itinerary, and then click **Export Model**.</span></span>  
  
#### <a name="to-create-the-receive-pipeline"></a><span data-ttu-id="2bb08-128">受信パイプラインを作成するには</span><span class="sxs-lookup"><span data-stu-id="2bb08-128">To create the receive pipeline</span></span>  
  
1.  <span data-ttu-id="2bb08-129">Visual Studio を右クリックして**DataFormatTransformation.Schemas**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-129">In Visual Studio, right-click **DataFormatTransformation.Schemas**, and then click **Properties**.</span></span> <span data-ttu-id="2bb08-130">をクリックして**アプリケーション**、し、入力**GlobalBank.ESB.DataFormatTransformation.Schemas**で、**アセンブリ名**ボックス。</span><span class="sxs-lookup"><span data-stu-id="2bb08-130">Click **Application**, and then type **GlobalBank.ESB.DataFormatTransformation.Schemas** in the **Assembly name** box.</span></span>  
  
2.  <span data-ttu-id="2bb08-131">右クリック**DataFormatTransformation.Schemas**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-131">Right-click **DataFormatTransformation.Schemas**, and then click **Properties**.</span></span> <span data-ttu-id="2bb08-132">をクリックして**署名**、ことを確認し、**アセンブリに署名** チェック ボックスが選択されていること、およびアセンブリの場所を指す**.\\.\\..\\..\\..\\..\keys\Microsoft.Practices.ESB.snk**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-132">Click **Signing**, and then verify that the **Sign the assembly** check box is selected and that the assembly location points to **.\\..\\..\\..\\..\\..\keys\Microsoft.Practices.ESB.snk**.</span></span>  
  
3.  <span data-ttu-id="2bb08-133">右クリック**DataFormatTransformation.Pipelines**、クリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-133">Right-click **DataFormatTransformation.Pipelines**, and then click **Remove**.</span></span>  
  
4.  <span data-ttu-id="2bb08-134">右クリック**DataFormatTransformation**、 をポイント**追加**、クリックして**新しいプロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-134">Right-click **DataFormatTransformation**, point to **Add**, and then click **New Project**.</span></span> <span data-ttu-id="2bb08-135">をクリックして**Biztalk プロジェクト**、クリックして**空の Biztalk Server プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-135">Click **Biztalk Projects**, and then click **Empty Biztalk Server Project**.</span></span> <span data-ttu-id="2bb08-136">**名前**ボックスに、入力**DataFormatTransformationReceive.Pipeline**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-136">In the **Name** box, type **DataFormatTransformationReceive.Pipeline**.</span></span>  
  
5.  <span data-ttu-id="2bb08-137">右クリック**DataFormatTransformationReceive.Pipeline**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-137">Right-click **DataFormatTransformationReceive.Pipeline**, and then click **Properties**.</span></span> <span data-ttu-id="2bb08-138">をクリックして**署名**、ことを確認し、**アセンブリに署名** チェック ボックスが選択されていること、およびアセンブリの場所を指す**C:\projects\Microsoft.Practices.ESB\keys\Microsoft.Practices.ESB.snk**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-138">Click **Signing**, and then verify that the **Sign the assembly** check box is selected and that the assembly location points to **C:\projects\Microsoft.Practices.ESB\keys\Microsoft.Practices.ESB.snk**.</span></span>  
  
6.  <span data-ttu-id="2bb08-139">右クリック**DataFormatTransformationReceive.Pipeline**、 をポイント**追加**、クリックして**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="2bb08-139">Right-click **DataFormatTransformationReceive.Pipeline**, point to **Add**, and then click **New Item**.</span></span>  
  
7.  <span data-ttu-id="2bb08-140">**新しい項目の追加**ダイアログ ボックスで、をクリックして**受信パイプライン**テンプレート ペインでします。</span><span class="sxs-lookup"><span data-stu-id="2bb08-140">In the **Add New Item** dialog box, click **Receive Pipeline** in the Templates pane.</span></span> <span data-ttu-id="2bb08-141">**名前**ボックスに、入力**ItinerarySelectReceiveFF**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-141">In the **Name** box, type **ItinerarySelectReceiveFF**, and then click **Add**.</span></span>  
  
8.  <span data-ttu-id="2bb08-142">右クリック**参照**DataFormatTransformationReceive.Pipeline プロジェクト、およびクリック**参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-142">Right-click **References** for the DataFormatTransformationReceive.Pipeline project, and then click **Add Reference**.</span></span> <span data-ttu-id="2bb08-143">クリックして、**プロジェクト** タブをクリックして**DataFormatTransformation.Schemas**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-143">Click the **Projects** tab, and then click **DataFormatTransformation.Schemas**.</span></span> <span data-ttu-id="2bb08-144">をクリックして**OK**参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="2bb08-144">Click **OK** to add the reference.</span></span>  
  
9. <span data-ttu-id="2bb08-145">ツールボックスからドラッグして、**フラット ファイル逆アセンブラー**パイプライン コンポーネントを**逆アセンブル**パイプラインのステージ。</span><span class="sxs-lookup"><span data-stu-id="2bb08-145">From the Toolbox, drag a **Flat file disassembler** pipeline component to the **Disassemble** stage of the pipeline.</span></span>  
  
10. <span data-ttu-id="2bb08-146">逆アセンブル、フラット ファイルのプロパティ ウィンドウで、をクリックして**DataModelTransformation.Schemas.NAOrderDocFF**で、**ドキュメント スキーマ**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="2bb08-146">In the Properties window for the flat file disassemble, click **DataModelTransformation.Schemas.NAOrderDocFF** in the **Document schema** drop-down list.</span></span>  
  
11. <span data-ttu-id="2bb08-147">ツールボックスからドラッグして、 **ESB 行程セレクター**パイプライン コンポーネントを**パーティの解決**パイプラインのステージ。</span><span class="sxs-lookup"><span data-stu-id="2bb08-147">From the Toolbox, drag an **ESB Itinerary Selector** pipeline component to the **Resolve Party** stage of the pipeline.</span></span>  
  
12. <span data-ttu-id="2bb08-148">ツールボックスからドラッグ、 **ESB ディスパッチャー**パイプライン コンポーネントを**パーティの解決**、パイプラインのステージの下に配置し、 **ESB 行程セレクター**パイプラインコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="2bb08-148">From the Toolbox, drag an **ESB Dispatcher** pipeline component to the **Resolve Party** stage of the pipeline, and then place it under the **ESB Itinerary Selector** pipeline component.</span></span>  
  
13. <span data-ttu-id="2bb08-149">すべてのプロジェクトの成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="2bb08-149">Save all project artifacts.</span></span>  
  
## <a name="to-create-the-test-message"></a><span data-ttu-id="2bb08-150">テスト メッセージを作成するには</span><span class="sxs-lookup"><span data-stu-id="2bb08-150">To create the test message</span></span>  
  
1.  <span data-ttu-id="2bb08-151">DataFormatTransformation.Schemas プロジェクトの NAOrderDocFF.xsd スキーマ ファイルで 1 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="2bb08-151">Click once in the NAOrderDocFF.xsd schema file of the DataFormatTransformation.Schemas project.</span></span> <span data-ttu-id="2bb08-152">Visual Studio の [プロパティ] ペインで、次の 2 つのプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="2bb08-152">In the Properties pane of Visual Studio, change the following two properties:</span></span>  
  
    -   <span data-ttu-id="2bb08-153">**インスタンスの出力の種類の生成**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-153">**Generate Instance Output Type**.</span></span> <span data-ttu-id="2bb08-154">変更するには、このプロパティのドロップダウン リストをクリックして**ネイティブ**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-154">Click the drop-down list for this property to change it to **Native**.</span></span>  
  
    -   <span data-ttu-id="2bb08-155">**出力インスタンス ファイル名**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-155">**Output Instance Filename**.</span></span> <span data-ttu-id="2bb08-156">このプロパティの省略記号ボタン (...) をクリックし、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation の既定のパスをそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="2bb08-156">Click the ellipsis button (…) for this property and accept the default path of C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation.</span></span> <span data-ttu-id="2bb08-157">**ファイル名**ボックスに、入力**NAOrderDocFF**、クリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-157">In the **File name** box, type **NAOrderDocFF**, and then click **Save**.</span></span>  
  
2.  <span data-ttu-id="2bb08-158">右クリック**NAOrderDocFF.xsd**  **DataFormatTransformation.Schemas**、クリックして**インスタンスの生成**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-158">Right-click **NAOrderDocFF.xsd** under **DataFormatTransformation.Schemas**, and then click **Generate Instance**.</span></span> <span data-ttu-id="2bb08-159">この時点では、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation ディレクトリに生成された新しいファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-159">At this point, you should have a new file generated in the C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation directory.</span></span>  
  
3.  <span data-ttu-id="2bb08-160">コピー (移動しないでください)、ファイルに C:\HowTos C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation から NAOrderDocFF.txt です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-160">Copy (do not move) the file NAOrderDocFF.txt from C:\Projects\Microsoft.Practices.ESB\Source\Samples\DataFormatTransformation to C:\HowTos.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2bb08-161">これは、メッセージはメッセージを受信して、XML に変換します。</span><span class="sxs-lookup"><span data-stu-id="2bb08-161">This is the message you will receive and convert to XML.</span></span> <span data-ttu-id="2bb08-162">このドキュメントでは、North American 注文ドキュメントのフラット ファイル バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="2bb08-162">This document represents a flat file version of North American Order document.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="2bb08-163">手順</span><span class="sxs-lookup"><span data-stu-id="2bb08-163">Steps</span></span>  
  
#### <a name="to-deploy-the-receive-pipeline-and-the-schema"></a><span data-ttu-id="2bb08-164">受信パイプラインとスキーマを展開するには</span><span class="sxs-lookup"><span data-stu-id="2bb08-164">To deploy the receive pipeline and the schema</span></span>  
  
1.  <span data-ttu-id="2bb08-165">右クリック**DataFormatTransformationReceive.Pipeline**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-165">Right-click **DataFormatTransformationReceive.Pipeline**, and then click **Properties**.</span></span> <span data-ttu-id="2bb08-166">をクリックして**展開**、し、入力**Microsoft.Practices.ESB**で、**アプリケーション名**ボックス。</span><span class="sxs-lookup"><span data-stu-id="2bb08-166">Click **Deployment**, and then type **Microsoft.Practices.ESB** in the **Application Name** box.</span></span>  
  
2.  <span data-ttu-id="2bb08-167">右クリックし、 **DataFormatTransformation.Schemas**プロジェクトをクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-167">Right-click the **DataFormatTransformation.Schemas** project, and then click **Properties**.</span></span> <span data-ttu-id="2bb08-168">をクリックして**展開**、し、入力**Microsoft.Practices.ESB**で、**アプリケーション名**ボックス。</span><span class="sxs-lookup"><span data-stu-id="2bb08-168">Click **Deployment**, and then type **Microsoft.Practices.ESB** in the **Application Name** box.</span></span>  
  
3.  <span data-ttu-id="2bb08-169">両方のプロパティ ウィンドウを閉じる**DataFormatTransformationReceive.Pipeline**と**DataFormatTransformation.Schemas**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-169">Close the Properties panes for both **DataFormatTransformationReceive.Pipeline** and **DataFormatTransformation.Schemas**.</span></span>  
  
4.  <span data-ttu-id="2bb08-170">ソリューション エクスプ ローラーで右クリックし、 **DataFormatTransformation**プロジェクトをクリックして**ソリューションの配置**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-170">In Solution Explorer, right-click the **DataFormatTransformation** project, and then click **Deploy Solution**.</span></span>  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a><span data-ttu-id="2bb08-171">作成し、ESB 入り口を構成します。</span><span class="sxs-lookup"><span data-stu-id="2bb08-171">To create and configure an ESB on-ramp</span></span>  
  
1.  <span data-ttu-id="2bb08-172">をクリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-172">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="2bb08-173">BizTalk Server 管理コンソールで、展開**BizTalk グループ**、展開**アプリケーション**、クリックして**Microsoft.Practices.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-173">In the BizTalk Server Administration Console, expand **BizTalk Group**, expand **Applications**, and then click **Microsoft.Practices.ESB**.</span></span>  
  
3.  <span data-ttu-id="2bb08-174">右クリック**受信場所**、 をポイント**新規**、クリックして**一方向の受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-174">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
4.  <span data-ttu-id="2bb08-175">**受信ポートの選択**ダイアログ ボックスで、をクリックして**OnRamp.Itinerary**、クリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-175">In the **Select a Receive Port** dialog box, click **OnRamp.Itinerary**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="2bb08-176">**受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに、入力**OnRamp.Itinerary.FlatFile.FILE**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-176">In the **Receive Location Properties** dialog box, in the **Name** box, type **OnRamp.Itinerary.FlatFile.FILE**.</span></span>  
  
6.  <span data-ttu-id="2bb08-177">**型**ドロップダウン リストをクリックして**ファイル**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-177">In the **Type** drop-down list, click **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="2bb08-178">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**受信フォルダー**ボックスに、入力**C:\HowTos\DropFolder**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-178">In the **FILE Transport Properties** dialog box, in the **Receive Folder** box, type **C:\HowTos\DropFolder**.</span></span>  
  
8.  <span data-ttu-id="2bb08-179">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**ファイル マスク**ボックスに、入力 **\*.txt**、クリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-179">In the **FILE Transport Properties** dialog box, in the **File mask** box, type **\*.txt**, and then click **OK**.</span></span>  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a><span data-ttu-id="2bb08-180">行程セレクター パイプライン コンポーネントを構成するには</span><span class="sxs-lookup"><span data-stu-id="2bb08-180">To configure the Itinerary Selector pipeline component</span></span>  
  
1.  <span data-ttu-id="2bb08-181">**受信場所のプロパティ**ダイアログ ボックスで、 をクリックして**ItinerarySelectReceiveFF**で、**受信パイプライン**ドロップダウン リストで、省略記号ボタン (...) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2bb08-181">In the **Receive Location Properties** dialog box, click **ItinerarySelectReceiveFF** in the **Receive pipeline** drop down list, and then click the ellipsis button (...).</span></span>  
  
2.  <span data-ttu-id="2bb08-182">使用して、**パイプラインの構成**、次を構成するダイアログ ボックス**行程セレクター**コンポーネントのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="2bb08-182">Use the **Configure Pipeline** dialog box to configure the following **Itinerary Selector** component properties:</span></span>  
  
    1.  <span data-ttu-id="2bb08-183">クリックして、 **ItineraryFactKey**プロパティ、および入力**Resolver.Itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-183">Click the **ItineraryFactKey** property, and then type **Resolver.Itinerary**.</span></span>  
  
    2.  <span data-ttu-id="2bb08-184">クリックして、 **ResolverConnectionString**プロパティ、型**行程:\\\name=DataFormatTransformation;**順にクリック**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-184">Click the **ResolverConnectionString** property, type **ITINERARY:\\\name=DataFormatTransformation;** and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="2bb08-185">をクリックして**OK**を閉じる、**受信場所のプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="2bb08-185">Click **OK** to close the **Receive Location Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="2bb08-186">BizTalk Server 管理コンソールを右クリックし、 **OnRamp.Itinerary.FlatFile.FILE**受信場所をクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-186">In the BizTalk Server Administration Console, right-click the **OnRamp.Itinerary.FlatFile.FILE** receive location, and then click **Enable**.</span></span>  
  
#### <a name="to-test-itinerary-based-routing-of-a-flat-file-message"></a><span data-ttu-id="2bb08-187">行程ベースのフラット ファイル メッセージのルーティングをテストするには</span><span class="sxs-lookup"><span data-stu-id="2bb08-187">To test itinerary-based routing of a flat file message</span></span>  
  
1.  <span data-ttu-id="2bb08-188">Windows エクスプローラで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="2bb08-188">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="2bb08-189">コピー (移動しないでください) NAOrderDocFF.txt C:\HowTos\DropFolder にします。</span><span class="sxs-lookup"><span data-stu-id="2bb08-189">Copy (do not move) NAOrderDocFF.txt to C:\HowTos\DropFolder.</span></span>  
  
3.  <span data-ttu-id="2bb08-190">C:\HowTos\Out を参照します。DFT%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="2bb08-190">Browse to C:\HowTos\Out. Verify that the DFT%MessageID%.xml message has been written to the directory.</span></span>  
  
4.  <span data-ttu-id="2bb08-191">BizTalk Server 管理コンソールを右クリックし、 **OnRamp.Itinerary.FlatFile.FILE**受信場所をクリックして**を無効にする**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-191">In the BizTalk Server Administration Console, right-click the **OnRamp.Itinerary.FlatFile.FILE** receive location, and then click **Disable**.</span></span>  
  
5.  <span data-ttu-id="2bb08-192">後に、 **OnRamp.Itinerary.FlatFile.FILE**受信場所が無効になっている、右クリックし、をクリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-192">After the **OnRamp.Itinerary.FlatFile.FILE** receive location is disabled, right-click it, and then click **Delete**.</span></span> <span data-ttu-id="2bb08-193">**受信場所のことを確認して削除**ダイアログ ボックスで、をクリックして**はい**です。</span><span class="sxs-lookup"><span data-stu-id="2bb08-193">In the **Confirm delete receive location** dialog box, click **Yes**.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="2bb08-194">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="2bb08-194">Additional Resources</span></span>  
 <span data-ttu-id="2bb08-195">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bb08-195">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="2bb08-196">方法: メッセージを変換し、スケジュール ルーティング スリップを利用してファイルの場所に送信する</span><span class="sxs-lookup"><span data-stu-id="2bb08-196">How to: Transform a Message and Route the Resulting Message to a File Location Using an Itinerary Routing Slip</span></span>](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [<span data-ttu-id="2bb08-197">方法: スケジュール ルーティング スリップを利用し、1 つのメッセージを複数の受信者に送信する</span><span class="sxs-lookup"><span data-stu-id="2bb08-197">How to: Route a Single Message to Multiple Recipients Using an Itinerary Routing Slip</span></span>](../esb-toolkit/route-a-single-message-to-multiple-recipients-using-an-itinerary-routing-slip.md)  
  
-   [<span data-ttu-id="2bb08-198">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="2bb08-198">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="2bb08-199">メッセージ変換パターン</span><span class="sxs-lookup"><span data-stu-id="2bb08-199">Message Transformation Patterns</span></span>](../esb-toolkit/message-transformation-patterns.md)