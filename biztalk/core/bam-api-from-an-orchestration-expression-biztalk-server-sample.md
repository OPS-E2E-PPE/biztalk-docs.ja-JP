---
title: オーケストレーションの式のサンプルから BAM API を |Microsoft ドキュメント
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
ms.openlocfilehash: 5413940eaba97e6f68d5e068e26625f320e6e817
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710985"
---
# <a name="bam-api-from-an-orchestration-expression-biztalk-server-sample"></a><span data-ttu-id="19ef8-102">オーケストレーション式からの BAM API (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="19ef8-102">BAM API from an Orchestration Expression (BizTalk Server Sample)</span></span>
<span data-ttu-id="19ef8-103">このサンプルで示す方法。</span><span class="sxs-lookup"><span data-stu-id="19ef8-103">This sample demonstrates how to:</span></span>  
  
-   <span data-ttu-id="19ef8-104">BizTalk Server オーケストレーションの式から BAM API を使用します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-104">Use the BAM API from a BizTalk Server orchestration expression.</span></span>  
  
-   <span data-ttu-id="19ef8-105">メッセージ内の繰り返し項目を個別のアクティビティ インスタンスとして追跡する。</span><span class="sxs-lookup"><span data-stu-id="19ef8-105">Track repeating items inside a message as separate activity instances.</span></span>  
  
-   <span data-ttu-id="19ef8-106">追跡プロファイルを使用して追跡される BAM データと、BAM API を使用して追跡される BAM データの間の関係を作成する。</span><span class="sxs-lookup"><span data-stu-id="19ef8-106">Create a relationship between BAM data that is tracked by using a tracking profile, and BAM data tracked by using the BAM API.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="19ef8-107">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="19ef8-107">Where to Find This Sample</span></span>  
 <span data-ttu-id="19ef8-108">このサンプルを見つけることができます*\<サンプル パス\>* \BAM\BamFromExpression です。</span><span class="sxs-lookup"><span data-stu-id="19ef8-108">You can find this sample at *\<Samples Path\>* \BAM\BamFromExpression.</span></span>  
  
 <span data-ttu-id="19ef8-109">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="19ef8-109">The following table lists the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="19ef8-110">ファイル</span><span class="sxs-lookup"><span data-stu-id="19ef8-110">File</span></span>|<span data-ttu-id="19ef8-111">Description</span><span class="sxs-lookup"><span data-stu-id="19ef8-111">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="19ef8-112">BamDefinition.xls</span><span class="sxs-lookup"><span data-stu-id="19ef8-112">BamDefinition.xls</span></span>|<span data-ttu-id="19ef8-113">BAM 定義スタイル シート。</span><span class="sxs-lookup"><span data-stu-id="19ef8-113">BAM definition stylesheet.</span></span>|  
|<span data-ttu-id="19ef8-114">BamDefinition.xml</span><span class="sxs-lookup"><span data-stu-id="19ef8-114">BamDefinition.xml</span></span>|<span data-ttu-id="19ef8-115">BAM 定義。</span><span class="sxs-lookup"><span data-stu-id="19ef8-115">BAM definition.</span></span>|  
|<span data-ttu-id="19ef8-116">BamFromExpression.btproj</span><span class="sxs-lookup"><span data-stu-id="19ef8-116">BamFromExpression.btproj</span></span>|<span data-ttu-id="19ef8-117">Visual Studio プロジェクトのファイルを追跡します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-117">Visual Studio tracking file project.</span></span>|  
|<span data-ttu-id="19ef8-118">BamFromExpression.sln</span><span class="sxs-lookup"><span data-stu-id="19ef8-118">BamFromExpression.sln</span></span>|<span data-ttu-id="19ef8-119">Visual Studio のソリューションです。</span><span class="sxs-lookup"><span data-stu-id="19ef8-119">Visual Studio solution.</span></span>|  
|<span data-ttu-id="19ef8-120">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="19ef8-120">Cleanup.bat</span></span>|<span data-ttu-id="19ef8-121">サンプルの展開解除を行うバッチ ファイル。</span><span class="sxs-lookup"><span data-stu-id="19ef8-121">Batch file to undeploy the sample.</span></span>|  
|<span data-ttu-id="19ef8-122">InputMessage.xml</span><span class="sxs-lookup"><span data-stu-id="19ef8-122">InputMessage.xml</span></span>|<span data-ttu-id="19ef8-123">入力メッセージ。</span><span class="sxs-lookup"><span data-stu-id="19ef8-123">Input message.</span></span>|  
|<span data-ttu-id="19ef8-124">Orchestration1.odx</span><span class="sxs-lookup"><span data-stu-id="19ef8-124">Orchestration1.odx</span></span>|<span data-ttu-id="19ef8-125">オーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="19ef8-125">Orchestration.</span></span>|  
|<span data-ttu-id="19ef8-126">PoSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="19ef8-126">PoSchema.xsd</span></span>|<span data-ttu-id="19ef8-127">注文書スキーマ。</span><span class="sxs-lookup"><span data-stu-id="19ef8-127">Purchase order schema.</span></span>|  
|<span data-ttu-id="19ef8-128">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="19ef8-128">PropertySchema.xsd</span></span>|<span data-ttu-id="19ef8-129">プロパティ スキーマ :</span><span class="sxs-lookup"><span data-stu-id="19ef8-129">Property schema.</span></span>|  
|<span data-ttu-id="19ef8-130">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="19ef8-130">Setup.bat</span></span>|<span data-ttu-id="19ef8-131">サンプルをコンパイルし、展開するバッチ ファイル。</span><span class="sxs-lookup"><span data-stu-id="19ef8-131">Batch file to compile and deploy the sample.</span></span>|  
|<span data-ttu-id="19ef8-132">QueryBam.sql</span><span class="sxs-lookup"><span data-stu-id="19ef8-132">QueryBam.sql</span></span>|<span data-ttu-id="19ef8-133">SQL スクリプト。</span><span class="sxs-lookup"><span data-stu-id="19ef8-133">SQL script.</span></span>|  
  
## <a name="create-the-tracking-profile"></a><span data-ttu-id="19ef8-134">追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-134">Create the tracking profile</span></span>  
  
1.  <span data-ttu-id="19ef8-135">管理者は、コマンド プロンプトを開き、実行*\<サンプル パス\>* \BAM\BAMFromExpression\Setup.bat です。</span><span class="sxs-lookup"><span data-stu-id="19ef8-135">Open a command prompt as Administrator, and run *\<Samples Path\>* \BAM\BAMFromExpression\Setup.bat.</span></span> <span data-ttu-id="19ef8-136">Setup.bat はこのサンプル用に BAM インフラストラクチャを初期化し、BAM アクティビティを展開します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-136">Setup.bat initializes the BAM infrastructure for this sample, and deploys the BAM activity.</span></span>  
  
2.  <span data-ttu-id="19ef8-137">**プログラム** > **Microsoft BizTalk Server**を右クリックして**追跡プロファイル エディター**、および**を管理者として実行**.</span><span class="sxs-lookup"><span data-stu-id="19ef8-137">From your **Programs** > **Microsoft BizTalk Server**, right-click **Tracking Profile Editor**, and **Run as administrator**.</span></span>
  
3.  <span data-ttu-id="19ef8-138">左側のウィンドウで、 **追跡プロファイル エディター** ウィンドウで、をクリックして **ここをクリックして BAM アクティビティ定義をインポートする**です。</span><span class="sxs-lookup"><span data-stu-id="19ef8-138">In the left pane of the **Tracking Profile Editor** window, click **Click here to import a BAM Activity Definition**.</span></span>  
  
4.  <span data-ttu-id="19ef8-139">**BAM アクティビティ定義名** のセクション、 **BAM アクティビティ定義のインポート** ダイアログ ボックスで、 **FromExpressionPo**, 、 をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-139">In the **BAM Activity Definition Name** section of the **Import BAM Activity Definition** dialog box, select **FromExpressionPo**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="19ef8-140">右側のウィンドウで、 **追跡プロファイル エディター** ウィンドウで、をクリックして **ここをクリックすると、イベント ソースを選択する**です。</span><span class="sxs-lookup"><span data-stu-id="19ef8-140">In the right pane of the **Tracking Profile Editor** window, click **Click here to select an event source**.</span></span>  
  
6.  <span data-ttu-id="19ef8-141">**アセンブリ名** のセクション、 **[イベント ソースの親アセンブリ** ダイアログ ボックスで、 **Microsoft.Samples.BizTalk.BamFromExpression**, 、] をクリックし、 **次**します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-141">In the **Assembly Name** section of the **Select Event Source Parent Assembly** dialog box, select **Microsoft.Samples.BizTalk.BamFromExpression**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="19ef8-142">**オーケストレーション名** のセクション、 **オーケストレーションの選択** ダイアログ ボックスで、 **BamFromExpression.Orchestration1**, 、 をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-142">In the **Orchestration Name** section of the **Select Orchestration** dialog box, select **BamFromExpression.Orchestration1**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="19ef8-143">右クリックし、 **Receive_1** 図形をクリックして **メッセージ ペイロード スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-143">Right-click the **Receive_1** shape, and then click **Message Payload Schema**.</span></span>  
  
9. <span data-ttu-id="19ef8-144">展開**\<スキーマ\>**、展開**PurchaseOrder**、展開**から**、し、ドラッグ**PoID**右のウィンドウ**ActivityID**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="19ef8-144">Expand **\<Schema\>**, expand **PurchaseOrder**, expand **From**, and then drag **PoID** in the right pane to **ActivityID** in the left pane.</span></span>  
  
10. <span data-ttu-id="19ef8-145">右側のウィンドウから次の要素をドラッグし、左側のウィンドウの名前付きノードにドロップします。</span><span class="sxs-lookup"><span data-stu-id="19ef8-145">Drag the following elements from the right pane, and drop them onto the named nodes in the left pane:</span></span>  
  
    |<span data-ttu-id="19ef8-146">From</span><span class="sxs-lookup"><span data-stu-id="19ef8-146">From</span></span>|<span data-ttu-id="19ef8-147">変換先</span><span class="sxs-lookup"><span data-stu-id="19ef8-147">To</span></span>|  
    |----------|--------|  
    |<span data-ttu-id="19ef8-148">名前</span><span class="sxs-lookup"><span data-stu-id="19ef8-148">Name</span></span>|<span data-ttu-id="19ef8-149">From</span><span class="sxs-lookup"><span data-stu-id="19ef8-149">From</span></span>|  
    |<span data-ttu-id="19ef8-150">状態</span><span class="sxs-lookup"><span data-stu-id="19ef8-150">State</span></span>|<span data-ttu-id="19ef8-151">状態</span><span class="sxs-lookup"><span data-stu-id="19ef8-151">State</span></span>|  
    |<span data-ttu-id="19ef8-152">City</span><span class="sxs-lookup"><span data-stu-id="19ef8-152">City</span></span>|<span data-ttu-id="19ef8-153">City</span><span class="sxs-lookup"><span data-stu-id="19ef8-153">City</span></span>|  
    |<span data-ttu-id="19ef8-154">Phone</span><span class="sxs-lookup"><span data-stu-id="19ef8-154">Phone</span></span>|<span data-ttu-id="19ef8-155">Phone</span><span class="sxs-lookup"><span data-stu-id="19ef8-155">Phone</span></span>|  
    |<span data-ttu-id="19ef8-156">Total</span><span class="sxs-lookup"><span data-stu-id="19ef8-156">Total</span></span>|<span data-ttu-id="19ef8-157">PoTotal</span><span class="sxs-lookup"><span data-stu-id="19ef8-157">PoTotal</span></span>|  
  
11. <span data-ttu-id="19ef8-158">矢印の付いたフォルダー アイコンをクリックして (![フォルダーとし、上のボタン & #45; 矢印](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4"))、オーケストレーションを表示します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-158">Click the folder icon with the arrow (![button with folder and up&#45;arrow](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) to display the orchestration.</span></span>  
  
12. <span data-ttu-id="19ef8-159">ドラッグ、 **Receive_1** 右側のウィンドウに図形 **受信** 左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="19ef8-159">Drag the **Receive_1** shape in the right pane to **Received** in the left pane.</span></span>  
  
13. <span data-ttu-id="19ef8-160">ドラッグ、 **Send_1** 右側のウィンドウに図形 **送信** 左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="19ef8-160">Drag the **Send_1** shape in the right pane to **Send** in the left pane.</span></span>  
  
14. <span data-ttu-id="19ef8-161">追跡プロファイルを保存*\<サンプル パス\>* \BAM\BamFromExpression\ BamFromExpression.btt です。</span><span class="sxs-lookup"><span data-stu-id="19ef8-161">Save the tracking profile to *\<Samples Path\>* \BAM\BamFromExpression\ BamFromExpression.btt.</span></span>  
  
15. <span data-ttu-id="19ef8-162">**ツール**  メニューのをクリックして **追跡プロファイルの適用**します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-162">On the **Tools** menu, click **Apply Tracking Profile**.</span></span>  
  
## <a name="build-and-initialize-this-sample"></a><span data-ttu-id="19ef8-163">ビルドおよび初期化するこのサンプル</span><span class="sxs-lookup"><span data-stu-id="19ef8-163">Build and initialize this sample</span></span>  
  
<span data-ttu-id="19ef8-164">BamFromExpression.btt 追跡プロファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-164">Deploy the BamFromExpression.btt tracking profile.</span></span> <span data-ttu-id="19ef8-165">参照してください[追跡を使用して追跡プロファイルを展開する方法のプロファイル管理ユーティリティ](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md)です。</span><span class="sxs-lookup"><span data-stu-id="19ef8-165">See [How to Deploy Tracking Profiles with the Tracking Profiles Management Utility](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md).</span></span>  
  
## <a name="run-this-sample"></a><span data-ttu-id="19ef8-166">このサンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-166">Run this sample</span></span>  
  
<span data-ttu-id="19ef8-167">ファイルをコピー *\<サンプル パス\>* に \BamFromExpression\InputMessage.xml *\<サンプル パス\>* \BamFromExpression\Input です。</span><span class="sxs-lookup"><span data-stu-id="19ef8-167">Copy the file *\<Samples Path\>* \BamFromExpression\InputMessage.xml to *\<Samples Path\>* \BamFromExpression\Input.</span></span>  
  
<span data-ttu-id="19ef8-168">約 10 秒後に、出力メッセージが表示されます*\<サンプル パス\>* \BamFromExpression\Output です。</span><span class="sxs-lookup"><span data-stu-id="19ef8-168">In about 10 seconds the output message will appear in *\<Samples Path\>* \BamFromExpression\Output.</span></span>  
  
## <a name="view-the-bam-data"></a><span data-ttu-id="19ef8-169">BAM データを表示します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-169">View the BAM data</span></span>  
  
1.  <span data-ttu-id="19ef8-170">SQL Server Management Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="19ef8-170">Open SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="19ef8-171">SQL Server Management Studio で、サーバーを展開し、 **データベース**, 、展開 **BAMPrimaryImport**, 、順に展開 **テーブル**します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-171">In SQL Server Management Studio, expand the server, expand **Databases**, expand **BAMPrimaryImport**, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="19ef8-172">右クリック **dbo.bam_FromExpressionPo_Completed**, 、クリックして **テーブルを開く**します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-172">Right-click **dbo.bam_FromExpressionPo_Completed**, and then click **Open Table**.</span></span> <span data-ttu-id="19ef8-173">SQL Server を使用している場合はクリックして**上位 1000 行を選択して**です。</span><span class="sxs-lookup"><span data-stu-id="19ef8-173">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="19ef8-174">bam_FromExpressionPo_Completed テーブルの内容が、右側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="19ef8-174">The contents of the bam_FromExpressionPo_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="19ef8-175">アクティビティ ID が 123 の 1 行は、入力メッセージに含まれていた $345 の注文を表します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-175">The one row, which has an activity ID of 123, represents the purchase order for $345 that was contained in the input message.</span></span>  
  
4.  <span data-ttu-id="19ef8-176">右クリック **dbo.bam_FromExpressionPoItem_Completed**, 、クリックして **テーブルを開く**します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-176">Right-click **dbo.bam_FromExpressionPoItem_Completed**, and then click **Open Table**.</span></span> <span data-ttu-id="19ef8-177">SQL Server を使用している場合はクリックして**上位 1000 行を選択して**です。</span><span class="sxs-lookup"><span data-stu-id="19ef8-177">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="19ef8-178">bam_FromExpressionPoItem_Completed テーブルの内容が、右側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="19ef8-178">The contents of the bam_FromExpressionPoItem_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="19ef8-179">アクティビティ ID が 123_0 および 123_1 の 2 行は、注文のアイテム Flash MC と Infrared Decoder を表します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-179">The two rows, which have activity IDs 123_0 and 123_1, represent the items in the purchase order: Flash MC and Infrared Decoder.</span></span>  
  
5.  <span data-ttu-id="19ef8-180">右クリック **dbo.bam_FromExpressionPoItem_CompletedRelationships**, 、クリックして **テーブルを開く**します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-180">Right-click **dbo.bam_FromExpressionPoItem_CompletedRelationships**, and then click **Open Table**.</span></span> <span data-ttu-id="19ef8-181">SQL Server を使用している場合はクリックして**上位 1000 行を選択して**です。</span><span class="sxs-lookup"><span data-stu-id="19ef8-181">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="19ef8-182">bam_FromExpressionPoItem_CompletedRelationships テーブルの内容が、右側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="19ef8-182">The contents of the bam_FromExpressionPoItem_CompletedRelationships table are displayed in the right pane.</span></span> <span data-ttu-id="19ef8-183">テーブルの各行は、FromExpressionPoItem アクティビティと FromExpressionPo アクティビティの関係を表します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-183">Each row in the table represents a relationship between a FromExpressionPoItem activity and a FromExpressionPo activity.</span></span> <span data-ttu-id="19ef8-184">値、 **ActivityID** 列は、FromExpressionPoItem アクティビティのアクティビティ ID を示します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-184">The value in the **ActivityID** column refers to the activity ID of the FromExpressionPoItem activity.</span></span> <span data-ttu-id="19ef8-185">値、 **ReferenceData** 列は、FromExpressionPo アクティビティのアクティビティ ID を示します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-185">The value in the **ReferenceData** column refers to the activity ID of the FromExpressionPo activity.</span></span> <span data-ttu-id="19ef8-186">この場合、2 つのレコードは、Flash MC アイテムと Infrared Decoder アイテムが $345 の注文で関連付けられていることを示します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-186">In this case, the two records indicate that the Flash MC and Infrared Decoder items are associated with the purchase order for $345.</span></span>  
  
## <a name="re-run-the-sample"></a><span data-ttu-id="19ef8-187">このサンプルを再実行します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-187">Re-run the sample</span></span>  
  
1.  <span data-ttu-id="19ef8-188">管理者は、コマンド プロンプトを開き、実行*\<サンプル パス\>* \BAM\BamFromExpression\Cleanup.bat 追跡プロファイルとその他の BAM インフラストラクチャを削除します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-188">Open a command prompt as Administrator, and run *\<Samples Path\>* \BAM\BamFromExpression\Cleanup.bat to remove the tracking profile and other BAM infrastructure.</span></span> 
  
2.  <span data-ttu-id="19ef8-189">実行*\<サンプル パス\>* \BAM\BamFromExpression\Setup.bat をサンプルをコンパイルして展開します。</span><span class="sxs-lookup"><span data-stu-id="19ef8-189">Run *\<Samples Path\>* \BAM\BamFromExpression\Setup.bat to compile the sample and deploy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19ef8-190">参照</span><span class="sxs-lookup"><span data-stu-id="19ef8-190">See Also</span></span>  
 <span data-ttu-id="19ef8-191">[ビジネス アクティビティ監視 (BizTalk Server Samples フォルダ)](../core/business-activity-monitoring-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="19ef8-191">[Business Activity Monitoring (BizTalk Server Samples Folder)](../core/business-activity-monitoring-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="19ef8-192">アクティビティ リレーションシップ</span><span class="sxs-lookup"><span data-stu-id="19ef8-192">Activity Relationships</span></span>](../core/activity-relationships.md)