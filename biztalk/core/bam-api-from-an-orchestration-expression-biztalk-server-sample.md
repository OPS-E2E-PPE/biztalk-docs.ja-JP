---
title: BAM API サンプルのオーケストレーションの式から |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 341bc333-9bfc-484c-b431-9a71f9188792
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acecbaff45eb7fd3e7197a27de5ae9911c174012
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358637"
---
# <a name="bam-api-from-an-orchestration-expression-biztalk-server-sample"></a><span data-ttu-id="e8632-102">BAM API (BizTalk Server サンプル) オーケストレーション式から</span><span class="sxs-lookup"><span data-stu-id="e8632-102">BAM API from an Orchestration Expression (BizTalk Server Sample)</span></span>
<span data-ttu-id="e8632-103">このサンプルでは方法。</span><span class="sxs-lookup"><span data-stu-id="e8632-103">This sample demonstrates how to:</span></span>  
  
-   <span data-ttu-id="e8632-104">BizTalk Server オーケストレーションの式から BAM API を使用します。</span><span class="sxs-lookup"><span data-stu-id="e8632-104">Use the BAM API from a BizTalk Server orchestration expression.</span></span>  
  
-   <span data-ttu-id="e8632-105">個別のアクティビティ インスタンスとしてメッセージ内の項目を繰り返し追跡できます。</span><span class="sxs-lookup"><span data-stu-id="e8632-105">Track repeating items inside a message as separate activity instances.</span></span>  
  
-   <span data-ttu-id="e8632-106">追跡プロファイルを使用して追跡される BAM データ間のリレーションシップを作成し、BAM API を使用して BAM データを追跡します。</span><span class="sxs-lookup"><span data-stu-id="e8632-106">Create a relationship between BAM data that is tracked by using a tracking profile, and BAM data tracked by using the BAM API.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="e8632-107">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="e8632-107">Where to Find This Sample</span></span>  
 <span data-ttu-id="e8632-108">このサンプルで*\<サンプル パス\>* \BAM\BamFromExpression します。</span><span class="sxs-lookup"><span data-stu-id="e8632-108">You can find this sample at *\<Samples Path\>* \BAM\BamFromExpression.</span></span>  
  
 <span data-ttu-id="e8632-109">次の表では、このサンプルではファイルの一覧し、その目的について説明します。</span><span class="sxs-lookup"><span data-stu-id="e8632-109">The following table lists the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="e8632-110">ファイル</span><span class="sxs-lookup"><span data-stu-id="e8632-110">File</span></span>|<span data-ttu-id="e8632-111">説明</span><span class="sxs-lookup"><span data-stu-id="e8632-111">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="e8632-112">BamDefinition.xls</span><span class="sxs-lookup"><span data-stu-id="e8632-112">BamDefinition.xls</span></span>|<span data-ttu-id="e8632-113">BAM 定義スタイル シートです。</span><span class="sxs-lookup"><span data-stu-id="e8632-113">BAM definition stylesheet.</span></span>|  
|<span data-ttu-id="e8632-114">BamDefinition.xml</span><span class="sxs-lookup"><span data-stu-id="e8632-114">BamDefinition.xml</span></span>|<span data-ttu-id="e8632-115">BAM 定義します。</span><span class="sxs-lookup"><span data-stu-id="e8632-115">BAM definition.</span></span>|  
|<span data-ttu-id="e8632-116">BamFromExpression.btproj</span><span class="sxs-lookup"><span data-stu-id="e8632-116">BamFromExpression.btproj</span></span>|<span data-ttu-id="e8632-117">Visual Studio プロジェクトのファイルを追跡します。</span><span class="sxs-lookup"><span data-stu-id="e8632-117">Visual Studio tracking file project.</span></span>|  
|<span data-ttu-id="e8632-118">BamFromExpression.sln</span><span class="sxs-lookup"><span data-stu-id="e8632-118">BamFromExpression.sln</span></span>|<span data-ttu-id="e8632-119">Visual Studio のソリューションです。</span><span class="sxs-lookup"><span data-stu-id="e8632-119">Visual Studio solution.</span></span>|  
|<span data-ttu-id="e8632-120">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="e8632-120">Cleanup.bat</span></span>|<span data-ttu-id="e8632-121">サンプルの展開解除するバッチ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="e8632-121">Batch file to undeploy the sample.</span></span>|  
|<span data-ttu-id="e8632-122">InputMessage.xml</span><span class="sxs-lookup"><span data-stu-id="e8632-122">InputMessage.xml</span></span>|<span data-ttu-id="e8632-123">入力メッセージ。</span><span class="sxs-lookup"><span data-stu-id="e8632-123">Input message.</span></span>|  
|<span data-ttu-id="e8632-124">Orchestration1.odx</span><span class="sxs-lookup"><span data-stu-id="e8632-124">Orchestration1.odx</span></span>|<span data-ttu-id="e8632-125">オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="e8632-125">Orchestration.</span></span>|  
|<span data-ttu-id="e8632-126">PoSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="e8632-126">PoSchema.xsd</span></span>|<span data-ttu-id="e8632-127">注文書スキーマ。</span><span class="sxs-lookup"><span data-stu-id="e8632-127">Purchase order schema.</span></span>|  
|<span data-ttu-id="e8632-128">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="e8632-128">PropertySchema.xsd</span></span>|<span data-ttu-id="e8632-129">プロパティ スキーマ : </span><span class="sxs-lookup"><span data-stu-id="e8632-129">Property schema.</span></span>|  
|<span data-ttu-id="e8632-130">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="e8632-130">Setup.bat</span></span>|<span data-ttu-id="e8632-131">コンパイルして、サンプルを配置するバッチ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="e8632-131">Batch file to compile and deploy the sample.</span></span>|  
|<span data-ttu-id="e8632-132">QueryBam.sql</span><span class="sxs-lookup"><span data-stu-id="e8632-132">QueryBam.sql</span></span>|<span data-ttu-id="e8632-133">SQL スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="e8632-133">SQL script.</span></span>|  
  
## <a name="create-the-tracking-profile"></a><span data-ttu-id="e8632-134">追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e8632-134">Create the tracking profile</span></span>  
  
1.  <span data-ttu-id="e8632-135">管理者は、コマンド プロンプトを開き、実行*\<サンプル パス\>* \BAM\BAMFromExpression\Setup.bat します。</span><span class="sxs-lookup"><span data-stu-id="e8632-135">Open a command prompt as Administrator, and run *\<Samples Path\>* \BAM\BAMFromExpression\Setup.bat.</span></span> <span data-ttu-id="e8632-136">Setup.bat は、このサンプルでは、BAM インフラストラクチャを初期化し、BAM アクティビティを展開します。</span><span class="sxs-lookup"><span data-stu-id="e8632-136">Setup.bat initializes the BAM infrastructure for this sample, and deploys the BAM activity.</span></span>  
  
2.  <span data-ttu-id="e8632-137">**プログラム** > **Microsoft BizTalk Server**、右クリックして**追跡プロファイル エディター**、および**を管理者として実行**.</span><span class="sxs-lookup"><span data-stu-id="e8632-137">From your **Programs** > **Microsoft BizTalk Server**, right-click **Tracking Profile Editor**, and **Run as administrator**.</span></span>
  
3.  <span data-ttu-id="e8632-138">左側のウィンドウで、**追跡プロファイル エディター**ウィンドウで、をクリックして**ここをクリックすると、BAM アクティビティ定義をインポートする**します。</span><span class="sxs-lookup"><span data-stu-id="e8632-138">In the left pane of the **Tracking Profile Editor** window, click **Click here to import a BAM Activity Definition**.</span></span>  
  
4.  <span data-ttu-id="e8632-139">**BAM アクティビティ定義名**のセクション、 **BAM アクティビティ定義のインポート**ダイアログ ボックスで、 **FromExpressionPo**、 をクリックし、 **ok**.</span><span class="sxs-lookup"><span data-stu-id="e8632-139">In the **BAM Activity Definition Name** section of the **Import BAM Activity Definition** dialog box, select **FromExpressionPo**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="e8632-140">右側のウィンドウで、**追跡プロファイル エディター**ウィンドウで、をクリックして**ここをクリックすると、イベント ソースを選択する**します。</span><span class="sxs-lookup"><span data-stu-id="e8632-140">In the right pane of the **Tracking Profile Editor** window, click **Click here to select an event source**.</span></span>  
  
6.  <span data-ttu-id="e8632-141">**アセンブリ名**のセクション、 **イベント ソースの親アセンブリ**ダイアログ ボックスで、 **Microsoft.Samples.BizTalk.BamFromExpression**順にクリックします**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="e8632-141">In the **Assembly Name** section of the **Select Event Source Parent Assembly** dialog box, select **Microsoft.Samples.BizTalk.BamFromExpression**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="e8632-142">**オーケストレーション名**のセクション、**オーケストレーションの選択**ダイアログ ボックスで、 **BamFromExpression.Orchestration1**、 をクリックし、 **ok**.</span><span class="sxs-lookup"><span data-stu-id="e8632-142">In the **Orchestration Name** section of the **Select Orchestration** dialog box, select **BamFromExpression.Orchestration1**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="e8632-143">右クリックし、 **Receive_1**図形をクリックして**メッセージ ペイロード スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="e8632-143">Right-click the **Receive_1** shape, and then click **Message Payload Schema**.</span></span>  
  
9. <span data-ttu-id="e8632-144">展開**\<スキーマ\>**、展開**PurchaseOrder**、展開**から**、し、ドラッグ**PoID**右にあります。ウィンドウ**ActivityID**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="e8632-144">Expand **\<Schema\>**, expand **PurchaseOrder**, expand **From**, and then drag **PoID** in the right pane to **ActivityID** in the left pane.</span></span>  
  
10. <span data-ttu-id="e8632-145">右側のウィンドウから、次の要素をドラッグし、左側のウィンドウで名前付きノードにドロップします。</span><span class="sxs-lookup"><span data-stu-id="e8632-145">Drag the following elements from the right pane, and drop them onto the named nodes in the left pane:</span></span>  
  
    |<span data-ttu-id="e8632-146">From</span><span class="sxs-lookup"><span data-stu-id="e8632-146">From</span></span>|<span data-ttu-id="e8632-147">目的</span><span class="sxs-lookup"><span data-stu-id="e8632-147">To</span></span>|  
    |----------|--------|  
    |<span data-ttu-id="e8632-148">名前</span><span class="sxs-lookup"><span data-stu-id="e8632-148">Name</span></span>|<span data-ttu-id="e8632-149">From</span><span class="sxs-lookup"><span data-stu-id="e8632-149">From</span></span>|  
    |<span data-ttu-id="e8632-150">状態</span><span class="sxs-lookup"><span data-stu-id="e8632-150">State</span></span>|<span data-ttu-id="e8632-151">状態</span><span class="sxs-lookup"><span data-stu-id="e8632-151">State</span></span>|  
    |<span data-ttu-id="e8632-152">City</span><span class="sxs-lookup"><span data-stu-id="e8632-152">City</span></span>|<span data-ttu-id="e8632-153">City</span><span class="sxs-lookup"><span data-stu-id="e8632-153">City</span></span>|  
    |<span data-ttu-id="e8632-154">Phone</span><span class="sxs-lookup"><span data-stu-id="e8632-154">Phone</span></span>|<span data-ttu-id="e8632-155">Phone</span><span class="sxs-lookup"><span data-stu-id="e8632-155">Phone</span></span>|  
    |<span data-ttu-id="e8632-156">Total</span><span class="sxs-lookup"><span data-stu-id="e8632-156">Total</span></span>|<span data-ttu-id="e8632-157">書</span><span class="sxs-lookup"><span data-stu-id="e8632-157">PoTotal</span></span>|  
  
11. <span data-ttu-id="e8632-158">矢印の付いたフォルダー アイコンをクリックします (![フォルダーでボタンをクリックし、セットアップ&#45;矢印](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4"))、オーケストレーションを表示します。</span><span class="sxs-lookup"><span data-stu-id="e8632-158">Click the folder icon with the arrow (![button with folder and up&#45;arrow](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) to display the orchestration.</span></span>  
  
12. <span data-ttu-id="e8632-159">ドラッグ、 **Receive_1**右側のウィンドウに図形**Received**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="e8632-159">Drag the **Receive_1** shape in the right pane to **Received** in the left pane.</span></span>  
  
13. <span data-ttu-id="e8632-160">ドラッグ、 **Send_1**右側のウィンドウに図形**送信**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="e8632-160">Drag the **Send_1** shape in the right pane to **Send** in the left pane.</span></span>  
  
14. <span data-ttu-id="e8632-161">追跡プロファイルを保存*\<サンプル パス\>* \BAM\BamFromExpression\ BamFromExpression.btt します。</span><span class="sxs-lookup"><span data-stu-id="e8632-161">Save the tracking profile to *\<Samples Path\>* \BAM\BamFromExpression\ BamFromExpression.btt.</span></span>  
  
15. <span data-ttu-id="e8632-162">**ツール** メニューのをクリックして**追跡プロファイルの適用**します。</span><span class="sxs-lookup"><span data-stu-id="e8632-162">On the **Tools** menu, click **Apply Tracking Profile**.</span></span>  
  
## <a name="build-and-initialize-this-sample"></a><span data-ttu-id="e8632-163">ビルドしてこのサンプルの初期化</span><span class="sxs-lookup"><span data-stu-id="e8632-163">Build and initialize this sample</span></span>  
  
<span data-ttu-id="e8632-164">BamFromExpression.btt 追跡プロファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="e8632-164">Deploy the BamFromExpression.btt tracking profile.</span></span> <span data-ttu-id="e8632-165">参照してください[追跡を使用して追跡プロファイルを展開する方法のプロファイル管理ユーティリティ](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md)します。</span><span class="sxs-lookup"><span data-stu-id="e8632-165">See [How to Deploy Tracking Profiles with the Tracking Profiles Management Utility](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md).</span></span>  
  
## <a name="run-this-sample"></a><span data-ttu-id="e8632-166">このサンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8632-166">Run this sample</span></span>  
  
<span data-ttu-id="e8632-167">ファイルをコピー *\<サンプル パス\>* に \BamFromExpression\InputMessage.xml *\<サンプル パス\>* \BamFromExpression\Input します。</span><span class="sxs-lookup"><span data-stu-id="e8632-167">Copy the file *\<Samples Path\>* \BamFromExpression\InputMessage.xml to *\<Samples Path\>* \BamFromExpression\Input.</span></span>  
  
<span data-ttu-id="e8632-168">約 10 秒間には、出力メッセージに表示されます*\<サンプル パス\>* \BamFromExpression\Output します。</span><span class="sxs-lookup"><span data-stu-id="e8632-168">In about 10 seconds the output message will appear in *\<Samples Path\>* \BamFromExpression\Output.</span></span>  
  
## <a name="view-the-bam-data"></a><span data-ttu-id="e8632-169">BAM データを表示します。</span><span class="sxs-lookup"><span data-stu-id="e8632-169">View the BAM data</span></span>  
  
1.  <span data-ttu-id="e8632-170">SQL Server Management Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="e8632-170">Open SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="e8632-171">SQL Server Management studio で、サーバーを展開し、**データベース**、展開**BAMPrimaryImport**、順に展開**テーブル**します。</span><span class="sxs-lookup"><span data-stu-id="e8632-171">In SQL Server Management Studio, expand the server, expand **Databases**, expand **BAMPrimaryImport**, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="e8632-172">右クリックして**dbo.bam_FromExpressionPo_Completed**、 をクリックし、**テーブルを開く**します。</span><span class="sxs-lookup"><span data-stu-id="e8632-172">Right-click **dbo.bam_FromExpressionPo_Completed**, and then click **Open Table**.</span></span> <span data-ttu-id="e8632-173">SQL Server を使用している場合はクリックして**上位 1000 行を選択する**します。</span><span class="sxs-lookup"><span data-stu-id="e8632-173">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="e8632-174">Bam_FromExpressionPo_Completed テーブルの内容は、右側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8632-174">The contents of the bam_FromExpressionPo_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="e8632-175">1 つの行は、アクティビティ ID が 123 には、入力メッセージに含まれていた $345 の注文書を表します。</span><span class="sxs-lookup"><span data-stu-id="e8632-175">The one row, which has an activity ID of 123, represents the purchase order for $345 that was contained in the input message.</span></span>  
  
4.  <span data-ttu-id="e8632-176">右クリックして**dbo.bam_FromExpressionPoItem_Completed**、 をクリックし、**テーブルを開く**します。</span><span class="sxs-lookup"><span data-stu-id="e8632-176">Right-click **dbo.bam_FromExpressionPoItem_Completed**, and then click **Open Table**.</span></span> <span data-ttu-id="e8632-177">SQL Server を使用している場合はクリックして**上位 1000 行を選択する**します。</span><span class="sxs-lookup"><span data-stu-id="e8632-177">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="e8632-178">Bam_FromExpressionPoItem_Completed テーブルの内容は、右側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8632-178">The contents of the bam_FromExpressionPoItem_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="e8632-179">アクティビティ Id 123_0 と 123_1 を持ち、2 つの行では、注文書内の項目を表します。MC と Infrared Decoder をフラッシュします。</span><span class="sxs-lookup"><span data-stu-id="e8632-179">The two rows, which have activity IDs 123_0 and 123_1, represent the items in the purchase order: Flash MC and Infrared Decoder.</span></span>  
  
5.  <span data-ttu-id="e8632-180">右クリックして**dbo.bam_FromExpressionPoItem_CompletedRelationships**、 をクリックし、**テーブルを開く**します。</span><span class="sxs-lookup"><span data-stu-id="e8632-180">Right-click **dbo.bam_FromExpressionPoItem_CompletedRelationships**, and then click **Open Table**.</span></span> <span data-ttu-id="e8632-181">SQL Server を使用している場合はクリックして**上位 1000 行を選択する**します。</span><span class="sxs-lookup"><span data-stu-id="e8632-181">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="e8632-182">Bam_FromExpressionPoItem_CompletedRelationships テーブルの内容は、右側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8632-182">The contents of the bam_FromExpressionPoItem_CompletedRelationships table are displayed in the right pane.</span></span> <span data-ttu-id="e8632-183">テーブルの各行は、FromExpressionPoItem アクティビティと FromExpressionPo アクティビティ間のリレーションシップを表します。</span><span class="sxs-lookup"><span data-stu-id="e8632-183">Each row in the table represents a relationship between a FromExpressionPoItem activity and a FromExpressionPo activity.</span></span> <span data-ttu-id="e8632-184">値、 **ActivityID**列は、FromExpressionPoItem アクティビティのアクティビティ ID を参照します。</span><span class="sxs-lookup"><span data-stu-id="e8632-184">The value in the **ActivityID** column refers to the activity ID of the FromExpressionPoItem activity.</span></span> <span data-ttu-id="e8632-185">値、 **ReferenceData** FromExpressionPo アクティビティのアクティビティ ID を参照する列。</span><span class="sxs-lookup"><span data-stu-id="e8632-185">The value in the **ReferenceData** column refers to the activity ID of the FromExpressionPo activity.</span></span> <span data-ttu-id="e8632-186">この場合、2 つのレコードは、Flash MC と Infrared Decoder アイテムが $345 の注文書に関連付けられたことを示します。</span><span class="sxs-lookup"><span data-stu-id="e8632-186">In this case, the two records indicate that the Flash MC and Infrared Decoder items are associated with the purchase order for $345.</span></span>  
  
## <a name="re-run-the-sample"></a><span data-ttu-id="e8632-187">このサンプルを再実行します。</span><span class="sxs-lookup"><span data-stu-id="e8632-187">Re-run the sample</span></span>  
  
1.  <span data-ttu-id="e8632-188">管理者は、コマンド プロンプトを開き、実行*\<サンプル パス\>* \BAM\BamFromExpression\Cleanup.bat を追跡プロファイルとその他の BAM インフラストラクチャを削除します。</span><span class="sxs-lookup"><span data-stu-id="e8632-188">Open a command prompt as Administrator, and run *\<Samples Path\>* \BAM\BamFromExpression\Cleanup.bat to remove the tracking profile and other BAM infrastructure.</span></span> 
  
2.  <span data-ttu-id="e8632-189">実行*\<サンプル パス\>* \BAM\BamFromExpression\Setup.bat サンプルをコンパイルし、デプロイします。</span><span class="sxs-lookup"><span data-stu-id="e8632-189">Run *\<Samples Path\>* \BAM\BamFromExpression\Setup.bat to compile the sample and deploy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8632-190">参照</span><span class="sxs-lookup"><span data-stu-id="e8632-190">See Also</span></span>  
 <span data-ttu-id="e8632-191">[ビジネス アクティビティ監視 (BizTalk Server Samples フォルダー)](../core/business-activity-monitoring-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="e8632-191">[Business Activity Monitoring (BizTalk Server Samples Folder)](../core/business-activity-monitoring-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="e8632-192">アクティビティ リレーションシップ</span><span class="sxs-lookup"><span data-stu-id="e8632-192">Activity Relationships</span></span>](../core/activity-relationships.md)