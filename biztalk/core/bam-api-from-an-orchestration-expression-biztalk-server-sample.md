---
title: "オーケストレーションの式 (BizTalk Server サンプル) から BAM API を |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, BAM
- examples, orchestrations
- BAM, examples
ms.assetid: 341bc333-9bfc-484c-b431-9a71f9188792
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3f78297b57dc2c9bc61d5996c49f7543ac64163
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="bam-api-from-an-orchestration-expression-biztalk-server-sample"></a><span data-ttu-id="16143-102">オーケストレーション式からの BAM API (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="16143-102">BAM API from an Orchestration Expression (BizTalk Server Sample)</span></span>
<span data-ttu-id="16143-103">このサンプルをする方法。</span><span class="sxs-lookup"><span data-stu-id="16143-103">This sample demonstrates how to:</span></span>  
  
-   <span data-ttu-id="16143-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションの式から BAM API を使用する。</span><span class="sxs-lookup"><span data-stu-id="16143-104">Use the BAM API from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration expression.</span></span>  
  
-   <span data-ttu-id="16143-105">メッセージ内の繰り返し項目を個別のアクティビティ インスタンスとして追跡する。</span><span class="sxs-lookup"><span data-stu-id="16143-105">Track repeating items inside a message as separate activity instances.</span></span>  
  
-   <span data-ttu-id="16143-106">追跡プロファイルを使用して追跡される BAM データと、BAM API を使用して追跡される BAM データの間の関係を作成する。</span><span class="sxs-lookup"><span data-stu-id="16143-106">Create a relationship between BAM data that is tracked by using a tracking profile, and BAM data tracked by using the BAM API.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="16143-107">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="16143-107">Where to Find This Sample</span></span>  
 <span data-ttu-id="16143-108">このサンプルを見つけることができます*\<サンプル パス\>*\BAM\BamFromExpression です。</span><span class="sxs-lookup"><span data-stu-id="16143-108">You can find this sample at *\<Samples Path\>*\BAM\BamFromExpression.</span></span>  
  
 <span data-ttu-id="16143-109">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="16143-109">The following table lists the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="16143-110">ファイル</span><span class="sxs-lookup"><span data-stu-id="16143-110">File</span></span>|<span data-ttu-id="16143-111">Description</span><span class="sxs-lookup"><span data-stu-id="16143-111">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="16143-112">BamDefinition.xls</span><span class="sxs-lookup"><span data-stu-id="16143-112">BamDefinition.xls</span></span>|<span data-ttu-id="16143-113">BAM 定義スタイル シートです。</span><span class="sxs-lookup"><span data-stu-id="16143-113">BAM definition stylesheet.</span></span>|  
|<span data-ttu-id="16143-114">BamDefinition.xml</span><span class="sxs-lookup"><span data-stu-id="16143-114">BamDefinition.xml</span></span>|<span data-ttu-id="16143-115">BAM 定義。</span><span class="sxs-lookup"><span data-stu-id="16143-115">BAM definition.</span></span>|  
|<span data-ttu-id="16143-116">BamFromExpression.btproj</span><span class="sxs-lookup"><span data-stu-id="16143-116">BamFromExpression.btproj</span></span>|[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="16143-117"> 追跡ファイル プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="16143-117"> tracking file project.</span></span>|  
|<span data-ttu-id="16143-118">BamFromExpression.sln</span><span class="sxs-lookup"><span data-stu-id="16143-118">BamFromExpression.sln</span></span>|[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="16143-119"> ソリューション。</span><span class="sxs-lookup"><span data-stu-id="16143-119"> solution.</span></span>|  
|<span data-ttu-id="16143-120">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="16143-120">Cleanup.bat</span></span>|<span data-ttu-id="16143-121">サンプルの展開解除を行うバッチ ファイル。</span><span class="sxs-lookup"><span data-stu-id="16143-121">Batch file to undeploy the sample.</span></span>|  
|<span data-ttu-id="16143-122">InputMessage.xml</span><span class="sxs-lookup"><span data-stu-id="16143-122">InputMessage.xml</span></span>|<span data-ttu-id="16143-123">入力メッセージ。</span><span class="sxs-lookup"><span data-stu-id="16143-123">Input message.</span></span>|  
|<span data-ttu-id="16143-124">Orchestration1.odx</span><span class="sxs-lookup"><span data-stu-id="16143-124">Orchestration1.odx</span></span>|<span data-ttu-id="16143-125">オーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="16143-125">Orchestration.</span></span>|  
|<span data-ttu-id="16143-126">PoSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="16143-126">PoSchema.xsd</span></span>|<span data-ttu-id="16143-127">注文書スキーマ。</span><span class="sxs-lookup"><span data-stu-id="16143-127">Purchase order schema.</span></span>|  
|<span data-ttu-id="16143-128">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="16143-128">PropertySchema.xsd</span></span>|<span data-ttu-id="16143-129">プロパティ スキーマ : </span><span class="sxs-lookup"><span data-stu-id="16143-129">Property schema.</span></span>|  
|<span data-ttu-id="16143-130">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="16143-130">Setup.bat</span></span>|<span data-ttu-id="16143-131">サンプルをコンパイルし、展開するバッチ ファイル。</span><span class="sxs-lookup"><span data-stu-id="16143-131">Batch file to compile and deploy the sample.</span></span>|  
|<span data-ttu-id="16143-132">QueryBam.sql</span><span class="sxs-lookup"><span data-stu-id="16143-132">QueryBam.sql</span></span>|<span data-ttu-id="16143-133">SQL スクリプト。</span><span class="sxs-lookup"><span data-stu-id="16143-133">SQL script.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="16143-134">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="16143-134">How to Use This Sample</span></span>  
 <span data-ttu-id="16143-135">次の手順を使用して追跡プロファイルを作成し、サンプルを実行して、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="16143-135">Use the following procedures to create the tracking profile, run the sample, and view the results.</span></span>  
  
#### <a name="to-create-the-tracking-profile"></a><span data-ttu-id="16143-136">追跡プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="16143-136">To create the tracking profile</span></span>  
  
1.  <span data-ttu-id="16143-137">コマンド プロンプトを開き、実行*\<サンプル パス\>*\BAM\BAMFromExpression\Setup.bat です。</span><span class="sxs-lookup"><span data-stu-id="16143-137">Open a command prompt and run *\<Samples Path\>*\BAM\BAMFromExpression\Setup.bat.</span></span> <span data-ttu-id="16143-138">[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] を使用している場合は、管理者としてコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="16143-138">If you are using [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], open the command prompt as administrator.</span></span> <span data-ttu-id="16143-139">Setup.bat はこのサンプル用に BAM インフラストラクチャを初期化し、BAM アクティビティを展開します。</span><span class="sxs-lookup"><span data-stu-id="16143-139">Setup.bat initializes the BAM infrastructure for this sample, and deploys the BAM activity.</span></span>  
  
2.  <span data-ttu-id="16143-140">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**追跡プロファイル エディター**です。</span><span class="sxs-lookup"><span data-stu-id="16143-140">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Tracking Profile Editor**.</span></span> <span data-ttu-id="16143-141">使用している場合[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]を右クリックして**追跡プロファイル エディター**  をクリックし、**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="16143-141">If you are using [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], right-click **Tracking Profile Editor** and then click **Run as administrator**.</span></span>  
  
3.  <span data-ttu-id="16143-142">左側のウィンドウで、**追跡プロファイル エディター**ウィンドウで、をクリックして**ここをクリックして、BAM アクティビティ定義をインポートする**です。</span><span class="sxs-lookup"><span data-stu-id="16143-142">In the left pane of the **Tracking Profile Editor** window, click **Click here to import a BAM Activity Definition**.</span></span>  
  
4.  <span data-ttu-id="16143-143">**BAM アクティビティ定義名**のセクションで、 **BAM アクティビティ定義のインポート**ダイアログ ボックスで、 **FromExpressionPo**、クリックして**[ok]**.</span><span class="sxs-lookup"><span data-stu-id="16143-143">In the **BAM Activity Definition Name** section of the **Import BAM Activity Definition** dialog box, select **FromExpressionPo**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="16143-144">右側のペインで、**追跡プロファイル エディター**ウィンドウで、をクリックして**ここをクリックすると、イベント ソースを選択する**です。</span><span class="sxs-lookup"><span data-stu-id="16143-144">In the right pane of the **Tracking Profile Editor** window, click **Click here to select an event source**.</span></span>  
  
6.  <span data-ttu-id="16143-145">**アセンブリ名**のセクションで、**イベント ソースの親アセンブリの選択**ダイアログ ボックスで、 **Microsoft.Samples.BizTalk.BamFromExpression**をクリックして**[次へ]**です。</span><span class="sxs-lookup"><span data-stu-id="16143-145">In the **Assembly Name** section of the **Select Event Source Parent Assembly** dialog box, select **Microsoft.Samples.BizTalk.BamFromExpression**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="16143-146">**オーケストレーション名**のセクションで、**オーケストレーションの選択**ダイアログ ボックスで、 **BamFromExpression.Orchestration1**、クリックして**[ok]**.</span><span class="sxs-lookup"><span data-stu-id="16143-146">In the **Orchestration Name** section of the **Select Orchestration** dialog box, select **BamFromExpression.Orchestration1**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="16143-147">右クリックし、 **Receive_1**図形をクリックして**メッセージ ペイロード スキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="16143-147">Right-click the **Receive_1** shape, and then click **Message Payload Schema**.</span></span>  
  
9. <span data-ttu-id="16143-148">展開**\<スキーマ\>**、展開**PurchaseOrder**、展開**から**、し、ドラッグ**PoID**右のウィンドウ**ActivityID**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="16143-148">Expand **\<Schema\>**, expand **PurchaseOrder**, expand **From**, and then drag **PoID** in the right pane to **ActivityID** in the left pane.</span></span>  
  
10. <span data-ttu-id="16143-149">右側のウィンドウから次の要素をドラッグし、左側のウィンドウの名前付きノードにドロップします。</span><span class="sxs-lookup"><span data-stu-id="16143-149">Drag the following elements from the right pane, and drop them onto the named nodes in the left pane:</span></span>  
  
    |<span data-ttu-id="16143-150">From</span><span class="sxs-lookup"><span data-stu-id="16143-150">From</span></span>|<span data-ttu-id="16143-151">変換先</span><span class="sxs-lookup"><span data-stu-id="16143-151">To</span></span>|  
    |----------|--------|  
    |<span data-ttu-id="16143-152">名前</span><span class="sxs-lookup"><span data-stu-id="16143-152">Name</span></span>|<span data-ttu-id="16143-153">From</span><span class="sxs-lookup"><span data-stu-id="16143-153">From</span></span>|  
    |<span data-ttu-id="16143-154">状態</span><span class="sxs-lookup"><span data-stu-id="16143-154">State</span></span>|<span data-ttu-id="16143-155">状態</span><span class="sxs-lookup"><span data-stu-id="16143-155">State</span></span>|  
    |<span data-ttu-id="16143-156">City</span><span class="sxs-lookup"><span data-stu-id="16143-156">City</span></span>|<span data-ttu-id="16143-157">City</span><span class="sxs-lookup"><span data-stu-id="16143-157">City</span></span>|  
    |<span data-ttu-id="16143-158">Phone</span><span class="sxs-lookup"><span data-stu-id="16143-158">Phone</span></span>|<span data-ttu-id="16143-159">Phone</span><span class="sxs-lookup"><span data-stu-id="16143-159">Phone</span></span>|  
    |<span data-ttu-id="16143-160">Total</span><span class="sxs-lookup"><span data-stu-id="16143-160">Total</span></span>|<span data-ttu-id="16143-161">PoTotal</span><span class="sxs-lookup"><span data-stu-id="16143-161">PoTotal</span></span>|  
  
11. <span data-ttu-id="16143-162">矢印の付いたフォルダー アイコンをクリックして (![フォルダーとし、上のボタン &#45; 矢印](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4"))、オーケストレーションを表示します。</span><span class="sxs-lookup"><span data-stu-id="16143-162">Click the folder icon with the arrow (![button with folder and up&#45;arrow](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) to display the orchestration.</span></span>  
  
12. <span data-ttu-id="16143-163">ドラッグ、 **Receive_1**図形を右側のペインで**Received**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="16143-163">Drag the **Receive_1** shape in the right pane to **Received** in the left pane.</span></span>  
  
13. <span data-ttu-id="16143-164">ドラッグ、 **Send_1**図形を右側のペインで**送信**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="16143-164">Drag the **Send_1** shape in the right pane to **Send** in the left pane.</span></span>  
  
14. <span data-ttu-id="16143-165">追跡プロファイルを保存*\<サンプル パス\>*\BAM\BamFromExpression\ BamFromExpression.btt です。</span><span class="sxs-lookup"><span data-stu-id="16143-165">Save the tracking profile to *\<Samples Path\>*\BAM\BamFromExpression\ BamFromExpression.btt.</span></span>  
  
15. <span data-ttu-id="16143-166">**ツール** メニューのをクリックして**追跡プロファイルの適用**です。</span><span class="sxs-lookup"><span data-stu-id="16143-166">On the **Tools** menu, click **Apply Tracking Profile**.</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="16143-167">このサンプルを作成および初期化するには</span><span class="sxs-lookup"><span data-stu-id="16143-167">To build and initialize this sample</span></span>  
  
-   <span data-ttu-id="16143-168">BamFromExpression.btt 追跡プロファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="16143-168">Deploy the BamFromExpression.btt tracking profile.</span></span> <span data-ttu-id="16143-169">詳細については、次を参照してください。[追跡プロファイル管理ユーティリティを使って追跡プロファイルを展開する方法](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md)です。</span><span class="sxs-lookup"><span data-stu-id="16143-169">For more information, see [How to Deploy Tracking Profiles with the Tracking Profiles Management Utility](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md).</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="16143-170">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="16143-170">To run this sample</span></span>  
  
-   <span data-ttu-id="16143-171">ファイルをコピー *\<サンプル パス\>*に \BamFromExpression\InputMessage.xml *\<サンプル パス\>*\BamFromExpression\Input です。</span><span class="sxs-lookup"><span data-stu-id="16143-171">Copy the file *\<Samples Path\>*\BamFromExpression\InputMessage.xml to *\<Samples Path\>*\BamFromExpression\Input.</span></span>  
  
     <span data-ttu-id="16143-172">約 10 秒後に、出力メッセージが表示されます*\<サンプル パス\>*\BamFromExpression\Output です。</span><span class="sxs-lookup"><span data-stu-id="16143-172">In about 10 seconds the output message will appear in *\<Samples Path\>*\BamFromExpression\Output.</span></span>  
  
#### <a name="to-view-the-bam-data"></a><span data-ttu-id="16143-173">BAM データを表示するには</span><span class="sxs-lookup"><span data-stu-id="16143-173">To view the BAM data</span></span>  
  
1.  <span data-ttu-id="16143-174">SQL Server Management Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="16143-174">Open SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="16143-175">SQL Server Management Studio で、サーバーを展開し、**データベース**、展開**BAMPrimaryImport**の順に展開および**テーブル**です。</span><span class="sxs-lookup"><span data-stu-id="16143-175">In SQL Server Management Studio, expand the server, expand **Databases**, expand **BAMPrimaryImport**, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="16143-176">右クリック**dbo.bam_FromExpressionPo_Completed**、クリックして**テーブルを開く**です。</span><span class="sxs-lookup"><span data-stu-id="16143-176">Right-click **dbo.bam_FromExpressionPo_Completed**, and then click **Open Table**.</span></span> <span data-ttu-id="16143-177">SQL Server を使用している場合はクリックして**上位 1000 行を選択して**です。</span><span class="sxs-lookup"><span data-stu-id="16143-177">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="16143-178">bam_FromExpressionPo_Completed テーブルの内容が、右側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="16143-178">The contents of the bam_FromExpressionPo_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="16143-179">アクティビティ ID が 123 の 1 行は、入力メッセージに含まれていた $345 の注文を表します。</span><span class="sxs-lookup"><span data-stu-id="16143-179">The one row, which has an activity ID of 123, represents the purchase order for $345 that was contained in the input message.</span></span>  
  
4.  <span data-ttu-id="16143-180">右クリック**dbo.bam_FromExpressionPoItem_Completed**、クリックして**テーブルを開く**です。</span><span class="sxs-lookup"><span data-stu-id="16143-180">Right-click **dbo.bam_FromExpressionPoItem_Completed**, and then click **Open Table**.</span></span> <span data-ttu-id="16143-181">SQL Server を使用している場合はクリックして**上位 1000 行を選択して**です。</span><span class="sxs-lookup"><span data-stu-id="16143-181">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="16143-182">bam_FromExpressionPoItem_Completed テーブルの内容が、右側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="16143-182">The contents of the bam_FromExpressionPoItem_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="16143-183">アクティビティ ID が 123_0 および 123_1 の 2 行は、注文のアイテム Flash MC と Infrared Decoder を表します。</span><span class="sxs-lookup"><span data-stu-id="16143-183">The two rows, which have activity IDs 123_0 and 123_1, represent the items in the purchase order: Flash MC and Infrared Decoder.</span></span>  
  
5.  <span data-ttu-id="16143-184">右クリック**dbo.bam_FromExpressionPoItem_CompletedRelationships**、クリックして**テーブルを開く**です。</span><span class="sxs-lookup"><span data-stu-id="16143-184">Right-click **dbo.bam_FromExpressionPoItem_CompletedRelationships**, and then click **Open Table**.</span></span> <span data-ttu-id="16143-185">SQL Server を使用している場合はクリックして**上位 1000 行を選択して**です。</span><span class="sxs-lookup"><span data-stu-id="16143-185">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="16143-186">bam_FromExpressionPoItem_CompletedRelationships テーブルの内容が、右側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="16143-186">The contents of the bam_FromExpressionPoItem_CompletedRelationships table are displayed in the right pane.</span></span> <span data-ttu-id="16143-187">テーブルの各行は、FromExpressionPoItem アクティビティと FromExpressionPo アクティビティの関係を表します。</span><span class="sxs-lookup"><span data-stu-id="16143-187">Each row in the table represents a relationship between a FromExpressionPoItem activity and a FromExpressionPo activity.</span></span> <span data-ttu-id="16143-188">値、 **ActivityID**列は、FromExpressionPoItem アクティビティのアクティビティ ID を示します。</span><span class="sxs-lookup"><span data-stu-id="16143-188">The value in the **ActivityID** column refers to the activity ID of the FromExpressionPoItem activity.</span></span> <span data-ttu-id="16143-189">値、 **ReferenceData**列は、FromExpressionPo アクティビティのアクティビティ ID を示します。</span><span class="sxs-lookup"><span data-stu-id="16143-189">The value in the **ReferenceData** column refers to the activity ID of the FromExpressionPo activity.</span></span> <span data-ttu-id="16143-190">この場合、2 つのレコードは、Flash MC アイテムと Infrared Decoder アイテムが $345 の注文で関連付けられていることを示します。</span><span class="sxs-lookup"><span data-stu-id="16143-190">In this case, the two records indicate that the Flash MC and Infrared Decoder items are associated with the purchase order for $345.</span></span>  
  
#### <a name="to-re-run-the-sample"></a><span data-ttu-id="16143-191">サンプルを再実行するには</span><span class="sxs-lookup"><span data-stu-id="16143-191">To re-run the sample</span></span>  
  
1.  <span data-ttu-id="16143-192">コマンド プロンプトを開き、実行*\<サンプル パス\>*\BAM\BamFromExpression\Cleanup.bat 追跡プロファイルとその他の BAM インフラストラクチャを削除します。</span><span class="sxs-lookup"><span data-stu-id="16143-192">Open a command prompt and run *\<Samples Path\>*\BAM\BamFromExpression\Cleanup.bat to remove the tracking profile and other BAM infrastructure.</span></span> <span data-ttu-id="16143-193">[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] を使用している場合は、管理者としてコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="16143-193">If you are using [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], open the command prompt as administrator.</span></span>  
  
2.  <span data-ttu-id="16143-194">実行*\<サンプル パス\>*\BAM\BamFromExpression\Setup.bat をサンプルをコンパイルして展開します。</span><span class="sxs-lookup"><span data-stu-id="16143-194">Run *\<Samples Path\>*\BAM\BamFromExpression\Setup.bat to compile the sample and deploy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16143-195">参照</span><span class="sxs-lookup"><span data-stu-id="16143-195">See Also</span></span>  
 <span data-ttu-id="16143-196">[ビジネス アクティビティ監視 (BizTalk Server Samples フォルダ)](../core/business-activity-monitoring-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="16143-196">[Business Activity Monitoring (BizTalk Server Samples Folder)](../core/business-activity-monitoring-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="16143-197">アクティビティ リレーションシップ</span><span class="sxs-lookup"><span data-stu-id="16143-197">Activity Relationships</span></span>](../core/activity-relationships.md)