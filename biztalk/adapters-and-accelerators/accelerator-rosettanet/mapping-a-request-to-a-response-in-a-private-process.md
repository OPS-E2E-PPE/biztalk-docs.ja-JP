---
title: プライベート プロセスで応答する要求のマッピング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, maps
- private processes, mapping requests
- private processes, customizing
- orchestrations, adding maps
- maps, adding to orchestrations
- maps, creating
- customizing private processes
- requests, mapping
- requests, private processes
ms.assetid: 5452c0a2-3a9b-43e7-bfa7-713eef0eab3b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb7cab4ba412a46f61df89daefd86df260454195
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976227"
---
# <a name="mapping-a-request-to-a-response-in-a-private-process"></a><span data-ttu-id="eb1b0-102">プライベート プロセスで応答する要求のマッピング</span><span class="sxs-lookup"><span data-stu-id="eb1b0-102">Mapping a Request to a Response in a Private Process</span></span>
<span data-ttu-id="eb1b0-103">このトピックでは、応答側プライベート プロセスが受信した要求メッセージにマップする方法を説明します: Microsoft から[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]を応答メッセージを送信できる、パブリック応答側プロセス、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]応答側パブリック プロセス。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-103">This topic describes how to map a request message received by the private responder process—from the Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] public responder process, to a response message that can be sent to the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] public responder process.</span></span>  
  
 <span data-ttu-id="eb1b0-104">応答側が要求メッセージを受信すると、その要求メッセージは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] によってパブリック プロセス オーケストレーションからプライベート プロセス オーケストレーション、基幹業務 (LOB) プログラムへとルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-104">When a responder receives a request message, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] routes the request message from the public-process orchestration, to the private-process orchestration, to the line-of-business (LOB) program.</span></span> <span data-ttu-id="eb1b0-105">応答側では、RosettaNet 応答メッセージを生成し、開始側に返すために、LOB プログラムからの応答サービス コンテンツを必要とします。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-105">The responder requires the response service content from the LOB program to generate a RosettaNet response message back to the initiator.</span></span> <span data-ttu-id="eb1b0-106">応答メッセージ内の多くの要素では、要求メッセージの値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-106">Many of the elements in the response message are populated using the values from the request message.</span></span> <span data-ttu-id="eb1b0-107">その結果、応答側プライベート プロセス オーケストレーションにマップを統合することにより、LOB プログラムで必要な形式の応答サービス コンテンツ メッセージを生成できます。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-107">As a result, you can incorporate a map in the responder private-process orchestration to help the LOB program generate the response service-content message in the required format.</span></span>  
  
 <span data-ttu-id="eb1b0-108">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK には、応答側プライベート プロセスにマップを追加する際に使用できる次のサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-108">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK contains the following samples that you can use when you add a map to a responder private-process:</span></span>  
  
-   [<span data-ttu-id="eb1b0-109">3A2 要求から 3A2 応答へのマップ サンプル</span><span class="sxs-lookup"><span data-stu-id="eb1b0-109">3A2 Request to 3A2 Response Map Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)  
  
-   [<span data-ttu-id="eb1b0-110">3A4 要求から 3A4 応答へのマップ サンプル</span><span class="sxs-lookup"><span data-stu-id="eb1b0-110">3A4 Request to 3A4 Response Map Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)  
  
-   [<span data-ttu-id="eb1b0-111">ダブルアクション PIPAutomation オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="eb1b0-111">Double Action PIPAutomation Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)  
  
-   [<span data-ttu-id="eb1b0-112">ビジネス ルールを使用した 3A4 プライベート レスポンダー オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="eb1b0-112">3A4 Private Responder Orchestration Using a Business Rule</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)  
  
### <a name="to-create-the-map"></a><span data-ttu-id="eb1b0-113">マップを作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-113">To create the map</span></span>  
  
1.  <span data-ttu-id="eb1b0-114">開始**Microsoft Visual Studio 2012**します。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-114">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="eb1b0-115">**ファイル**メニューで、**オープン**、 をクリックし、**プロジェクト**。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-115">On the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="eb1b0-116">マップを追加するプライベート プロセス オーケストレーションを含んでいる BizTalk プロジェクトを格納するフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-116">Locate the folder that contains the BizTalk project that contains the private-process orchestration to which you want to add the map.</span></span>  
  
4.  <span data-ttu-id="eb1b0-117">ソリューション エクスプローラーで、プロジェクトを右クリックして **[追加]** をポイントし、**[新しい項目]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-117">In Solution Explorer, right-click the project, point to **Add**, and then click **New Item**.</span></span>  
  
5.  <span data-ttu-id="eb1b0-118">[新しい項目の追加] ウィンドウで、**カテゴリ**ウィンドウで、をクリックして**マップ ファイル**。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-118">In the Add New Item window, in the **Categories** pane, click **Map Files**.</span></span> <span data-ttu-id="eb1b0-119">[テンプレート] ペインで次のようにクリックします。**マップ**します。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-119">In the Templates pane, click **Map**.</span></span> <span data-ttu-id="eb1b0-120">**名前**ボックスで、マップの名前を入力し、クリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-120">In the **Name** box, type a name for the map, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="eb1b0-121">送信元スキーマ ペインで次のようにクリックします。**ソース スキーマを開く**します。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-121">In the Source Schema pane, click **Open Source Schema**.</span></span>  
  
7.  <span data-ttu-id="eb1b0-122">BizTalk 型の選択 ウィンドウで、**スキーマ**をクリックしてから、マップする要求メッセージの PIP スキーマを選択します。 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-122">In the BizTalk Type Picker window, expand **Schemas**, select the PIP schema for the request message that you want to map from, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="eb1b0-123">送信先スキーマ ペインで次のようにクリックします。**送信先スキーマを開く**します。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-123">In the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
9. <span data-ttu-id="eb1b0-124">BizTalk 型の選択 ウィンドウで、**参照**、展開**microsoft.solutions.btarn.schemas.rnpips**、展開**スキーマ**、PIP スキーマを選択します応答メッセージをクリックし、マップする**OK**します。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-124">In the BizTalk Type Picker window, expand **References**, expand **Microsoft.Solutions.BTARN.Schemas.RNPIPs**, expand **Schemas**, select the PIP schema for the response message to which you want to map, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="eb1b0-125">右クリックし、 \<*スキーマ*\>クリック、送信元スキーマのノード**ツリー ノードの展開**します。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-125">Right-click the \<*Schema*\> node of the source schema, and then click **Expand Tree Node**.</span></span>  
  
11. <span data-ttu-id="eb1b0-126">送信先スキーマについても、手順 10. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-126">Repeat step 10 for the destination schema.</span></span>  
  
12. <span data-ttu-id="eb1b0-127">送信元スキーマ ペインで、送信先スキーマのフィールドにマップするフィールドをクリックしたままにし、</span><span class="sxs-lookup"><span data-stu-id="eb1b0-127">In the Source Schema pane, click and hold on a field that you want to map to a field in the destination schema.</span></span> <span data-ttu-id="eb1b0-128">送信先スキーマ ペインで対応するノードにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-128">Drag to the corresponding node in the Destination Schema pane.</span></span>  
  
13. <span data-ttu-id="eb1b0-129">両スキーマ間でマップする必要のあるすべてのフィールドについて、手順 12. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-129">Repeat step 12 for all fields that you have to map between the two schemas.</span></span>  
  
14. <span data-ttu-id="eb1b0-130">マップの検証とテストを行います。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-130">Validate and test the map.</span></span> <span data-ttu-id="eb1b0-131">詳細については、BizTalk Server ヘルプで「マップのコンパイルとテスト」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-131">For more information, see the "Compiling and Testing Maps" topic in BizTalk Server Help.</span></span>  
  
### <a name="to-add-the-map-to-the-orchestration"></a><span data-ttu-id="eb1b0-132">オーケストレーションにマップを追加するには</span><span class="sxs-lookup"><span data-stu-id="eb1b0-132">To add the map to the orchestration</span></span>  
  
1.  <span data-ttu-id="eb1b0-133">ソリューション エクスプローラで、プライベート プロセス オーケストレーションをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-133">In Solution Explorer, double-click the private-process orchestration.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eb1b0-134">オーケストレーションに、スキーマを含んでいるアセンブリへの参照があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-134">Make sure that the orchestration has references to the assemblies that contain the schemas.</span></span>  
  
2.  <span data-ttu-id="eb1b0-135">ツールボックスで、をクリックして、**変換**図形、および位置は、要求メッセージを応答メッセージに変換する必要があるオーケストレーション内の位置にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-135">In the Toolbox, click the **Transform** shape, and drag it to the point in the orchestration at which you have to transform the request message into the response message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eb1b0-136">配置の例については、**変換**図形、PIP3A4PrivateResponder.odx オーケストレーションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-136">For an example of the placement of the **Transform** shape, see the PIP3A4PrivateResponder.odx orchestration.</span></span> <span data-ttu-id="eb1b0-137">ある\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\pipautomation\3a4\pr です。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-137">It is located in \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\PipAutomation\3A4\PR.</span></span> <span data-ttu-id="eb1b0-138">このサンプルでは、**変換**図形のすぐ下、 **IsActivityDoubleAction**図形。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-138">This sample puts the **Transform** shape immediately under the **IsActivityDoubleAction** shape.</span></span> <span data-ttu-id="eb1b0-139">詳細については、[3A4 プライベート レスポンダー オーケストレーションを使用してビジネス ルール](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-139">For more information, see [3A4 Private Responder Orchestration Using a Business Rule](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eb1b0-140">複数の Pip の複数のマップを組み込む方法の例は、[Double Action PIPAutomation Orchestration](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-140">For an example of how you can incorporate multiple maps for multiple PIPs, see [Double Action PIPAutomation Orchestration](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md).</span></span>  
  
3.  <span data-ttu-id="eb1b0-141">オーケストレーション デザイン画面でクリックして**ConstructMessage1**します。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-141">On the orchestration design surface, click **ConstructMessage1**.</span></span> <span data-ttu-id="eb1b0-142">プロパティ ウィンドウで、図形の名前、および作成するメッセージの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-142">In the Properties window, type a name for the shape, and a name for the message to be constructed.</span></span>  
  
4.  <span data-ttu-id="eb1b0-143">オーケストレーション デザイン画面でクリックして**変換**します。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-143">On the orchestration design surface, click **Transform**.</span></span> <span data-ttu-id="eb1b0-144">[プロパティ] ウィンドウで、省略記号ボタンをクリックします (**...**) 横に**マップ名**します。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-144">In the Properties window, click the ellipsis button (**...**) next to **Map Name**.</span></span>  
  
5.  <span data-ttu-id="eb1b0-145">変換の構成 ウィンドウで、次のようにクリックします。**既存のマップ**、および**完全修飾マップ名**、先ほど作成したマップをクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-145">In the Transform Configuration window, click **Existing Map**, and in **Fully Qualified Map Name**, click the map that you just created.</span></span>  
  
6.  <span data-ttu-id="eb1b0-146">[**変換**、] をクリックして**ソース**します。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-146">Under **Transform**, click **Source**.</span></span> <span data-ttu-id="eb1b0-147">変数の下の空のボックスをクリックし、ドロップダウン リストから要求メッセージの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-147">Click the empty box under variable, and select the name of the request message from the drop-down list.</span></span>  
  
7.  <span data-ttu-id="eb1b0-148">[**変換**、] をクリックして**先**します。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-148">Under **Transform**, click **Destination**.</span></span> <span data-ttu-id="eb1b0-149">変数の下の空のボックスをクリックし、ドロップダウン リストから応答メッセージの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-149">Click the empty box under variable, and select the name of the response message from the drop-down list.</span></span>  
  
8.  <span data-ttu-id="eb1b0-150">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb1b0-150">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb1b0-151">参照</span><span class="sxs-lookup"><span data-stu-id="eb1b0-151">See Also</span></span>  
 [<span data-ttu-id="eb1b0-152">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="eb1b0-152">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)