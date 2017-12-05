---
title: "手順 5: Contoso プライベート プロセス オーケストレーションの変更 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private processes, orchestrations
- private process tutorial, modifying private process orchestration
ms.assetid: a5430db8-e5f0-48a6-abb9-e268d8ec2ec4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a222ee518cf0555de60094411df73bf5a5d486a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-5-modifying-the-contoso-private-process-orchestration"></a><span data-ttu-id="0e293-102">手順 5: Contoso プライベート プロセス オーケストレーションの変更</span><span class="sxs-lookup"><span data-stu-id="0e293-102">Step 5: Modifying the Contoso Private Process Orchestration</span></span>
<span data-ttu-id="0e293-103">ここでは、プライベート プロセス オーケストレーションを変更して、Contoso のエンタープライズ リソース計画 (ERP) システムと統合します。</span><span class="sxs-lookup"><span data-stu-id="0e293-103">In this step, you modify the private process orchestration to integrate with the Enterprise Resource Planning (ERP) system for Contoso.</span></span> <span data-ttu-id="0e293-104">Contoso の ERP システムは、製品価格と在庫に対する内部的に定義されたスキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="0e293-104">The ERP system for Contoso uses internally defined schemas for product price and availability.</span></span> <span data-ttu-id="0e293-105">3A2 - Price and Availability PIP (Partner Interface Process) のプライベート プロセスをカスタマイズすることによって、スキーマにマップされた情報を使用して、ERP システムと統合できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0e293-105">By customizing the private process for the 3A2 - Price and Availability Partner Interface Process (PIP), you will be able to integrate with the ERP system by using schema-mapping information.</span></span>  
  
### <a name="to-add-a-reference-to-the-contoso-priceandavailability-and-rnpips-assemblies"></a><span data-ttu-id="0e293-106">Contoso の PriceAndAvailability アセンブリおよび RNPIPs アセンブリの参照の追加</span><span class="sxs-lookup"><span data-stu-id="0e293-106">To add a reference to the Contoso PriceAndAvailability and RNPIPs assemblies</span></span>  
  
1.  <span data-ttu-id="0e293-107">ソリューション エクスプ ローラーに表示される Contoso ソリューションを右クリックし、 **PrivateResponder**プロジェクトをクリックして**参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="0e293-107">With the Contoso solution displayed in Solution Explorer, right-click the **PrivateResponder** project, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="0e293-108">[参照の追加] ダイアログ ボックスで、**参照**です。</span><span class="sxs-lookup"><span data-stu-id="0e293-108">In the Add Reference dialog box, click **Browse**.</span></span> <span data-ttu-id="0e293-109">移動*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \bin フォルダー、および、次のアセンブリを選択**:**</span><span class="sxs-lookup"><span data-stu-id="0e293-109">Move to *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\Bin folder, and then select the following assemblies**:**</span></span>  
  
    -   <span data-ttu-id="0e293-110">Microsoft.solutions.BTARN.CommonTypes.dll</span><span class="sxs-lookup"><span data-stu-id="0e293-110">Microsoft.Solutions.BTARN.CommonTypes.dll</span></span>  
  
    -   <span data-ttu-id="0e293-111">Microsoft.solutions.BTARN.ConfigurationManager.dll</span><span class="sxs-lookup"><span data-stu-id="0e293-111">Microsoft.Solutions.BTARN.ConfigurationManager.dll</span></span>  
  
    -   <span data-ttu-id="0e293-112">Microsoft.solutions.BTARN.GlobalSchemas.dll</span><span class="sxs-lookup"><span data-stu-id="0e293-112">Microsoft.Solutions.BTARN.GlobalSchemas.dll</span></span>  
  
    -   <span data-ttu-id="0e293-113">Microsoft.solutions.BTARN.PublicResponder.dll</span><span class="sxs-lookup"><span data-stu-id="0e293-113">Microsoft.Solutions.BTARN.PublicResponder.dll</span></span>  
  
    -   <span data-ttu-id="0e293-114">Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll</span><span class="sxs-lookup"><span data-stu-id="0e293-114">Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll</span></span>  
  
    -   <span data-ttu-id="0e293-115">Microsoft.solutions.BTARN.Shared.dll</span><span class="sxs-lookup"><span data-stu-id="0e293-115">Microsoft.Solutions.BTARN.Shared.dll</span></span>  
  
    -   <span data-ttu-id="0e293-116">Microsoft.Solutions.BTARN.XSDClasses.GlobalSchemas.dll</span><span class="sxs-lookup"><span data-stu-id="0e293-116">Microsoft.Solutions.BTARN.XSDClasses.GlobalSchemas.dll</span></span>  
  
3.  <span data-ttu-id="0e293-117">**[追加]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e293-117">Click **Add**.</span></span>  
  
4.  <span data-ttu-id="0e293-118">[参照の追加] ダイアログ ボックス、**プロジェクト**] タブで、[、 **[contosopriceandavailability]**と**HeaderHelper**プロジェクト、およびクリック**追加**です。</span><span class="sxs-lookup"><span data-stu-id="0e293-118">In the Add Reference dialog box, click the **Projects** tab, select the **ContosoPriceAndAvailability** and **HeaderHelper** projects, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="0e293-119">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e293-119">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="0e293-120">[Microsoft 開発環境] ダイアログ ボックスで、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="0e293-120">In the Microsoft Development Environment dialog box, click **OK**.</span></span>  
  
### <a name="to-create-new-message-types"></a><span data-ttu-id="0e293-121">新しいメッセージの種類を作成するには</span><span class="sxs-lookup"><span data-stu-id="0e293-121">To create new message types</span></span>  
  
1.  <span data-ttu-id="0e293-122">ソリューション エクスプ ローラーで、 **PrivateResponder**オーケストレーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="0e293-122">In Solution Explorer, double-click the **PrivateResponder** orchestration to open it.</span></span>  
  
2.  <span data-ttu-id="0e293-123">ソリューション エクスプ ローラーでクリックして**オーケストレーション**です。</span><span class="sxs-lookup"><span data-stu-id="0e293-123">In Solution Explorer, click **Orchestration View**.</span></span>  
  
3.  <span data-ttu-id="0e293-124">オーケストレーション ビューで右クリック**メッセージ**、クリックして**新しいメッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="0e293-124">In Orchestration View, right-click **Messages**, and then click **New Message**.</span></span>  
  
4.  <span data-ttu-id="0e293-125">[プロパティ] ウィンドウ内で、**識別子**ボックスに、入力**PIP3A2RequestMessage**です。</span><span class="sxs-lookup"><span data-stu-id="0e293-125">In the Properties window, in the **Identifier** box, type **PIP3A2RequestMessage**.</span></span>  
  
5.  <span data-ttu-id="0e293-126">**メッセージの種類**ボックス、ドロップダウン矢印をクリックして、展開**スキーマ**、し、 **\<参照されたアセンブリから選択\>**です。</span><span class="sxs-lookup"><span data-stu-id="0e293-126">In the **Message Type** box, click the drop-down arrow, expand **Schemas**, and then select **\<Select from referenced assembly\>**.</span></span>  
  
6.  <span data-ttu-id="0e293-127">成果物 Typedialog の選択ボックスで、次のように選択します**Microsoft.Solutions.BTARN.Schemas.RNPIPs**左のペインで選択**_3A2PriceAndAvailabilityQueryMessageGuideline_v1_3**右側のウィンドウで、。をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="0e293-127">In the Select Artifact Typedialog box, select **Microsoft.Solutions.BTARN.Schemas.RNPIPs** in the left pane, select **_3A2PriceAndAvailabilityQueryMessageGuideline_v1_3** in the right pane, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="0e293-128">ソリューションに対して以下の情報を使用して手順 3. ～ 6. を繰り返し、すべてのメッセージの種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="0e293-128">Repeat steps 3 through 6 to create all the message types for the solution using the following information:</span></span>  
  
    |<span data-ttu-id="0e293-129">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="0e293-129">Identifier</span></span>|<span data-ttu-id="0e293-130">アセンブリ</span><span class="sxs-lookup"><span data-stu-id="0e293-130">Assembly</span></span>|<span data-ttu-id="0e293-131">メッセージの種類</span><span class="sxs-lookup"><span data-stu-id="0e293-131">Message Type</span></span>|  
    |----------------|--------------|------------------|  
    |<span data-ttu-id="0e293-132">PIP3A2ResponseMessage</span><span class="sxs-lookup"><span data-stu-id="0e293-132">PIP3A2ResponseMessage</span></span>|<span data-ttu-id="0e293-133">Microsoft.Solutions.BTARN です。</span><span class="sxs-lookup"><span data-stu-id="0e293-133">Microsoft.Solutions.BTARN.</span></span><br /><span data-ttu-id="0e293-134">Schemas.RNPips</span><span class="sxs-lookup"><span data-stu-id="0e293-134">Schemas.RNPips</span></span>|<span data-ttu-id="0e293-135">_3A2PriceAndAvailability</span><span class="sxs-lookup"><span data-stu-id="0e293-135">_3A2PriceAndAvailability</span></span><br /><span data-ttu-id="0e293-136">ResponseMessageGuideline_v1_3</span><span class="sxs-lookup"><span data-stu-id="0e293-136">ResponseMessageGuideline_v1_3</span></span>|  
    |<span data-ttu-id="0e293-137">Contoso3A2ResponseMessage</span><span class="sxs-lookup"><span data-stu-id="0e293-137">Contoso3A2ResponseMessage</span></span>|<span data-ttu-id="0e293-138">ContosoPriceAndAvailability</span><span class="sxs-lookup"><span data-stu-id="0e293-138">ContosoPriceAndAvailability</span></span>|<span data-ttu-id="0e293-139">rootPriceResponse</span><span class="sxs-lookup"><span data-stu-id="0e293-139">rootPriceResponse</span></span>|  
    |<span data-ttu-id="0e293-140">Contoso3A2RequestMessage</span><span class="sxs-lookup"><span data-stu-id="0e293-140">Contoso3A2RequestMessage</span></span>|<span data-ttu-id="0e293-141">ContosoPriceAndAvailability</span><span class="sxs-lookup"><span data-stu-id="0e293-141">ContosoPriceAndAvailability</span></span>|<span data-ttu-id="0e293-142">rootPriceRequest</span><span class="sxs-lookup"><span data-stu-id="0e293-142">rootPriceRequest</span></span>|  
  
8.  <span data-ttu-id="0e293-143">これで、このソリューションのメッセージの種類の作成が完了しました。</span><span class="sxs-lookup"><span data-stu-id="0e293-143">You have finished creating the message types for the solution.</span></span>  
  
### <a name="to-create-new-variables"></a><span data-ttu-id="0e293-144">新しい変数を作成するには</span><span class="sxs-lookup"><span data-stu-id="0e293-144">To create new variables</span></span>  
  
1.  <span data-ttu-id="0e293-145">オーケストレーション ビューで右クリック**変数、**  をクリックし、**新しい変数**です。</span><span class="sxs-lookup"><span data-stu-id="0e293-145">In Orchestration View, right-click **Variables,** and then click **New Variable**.</span></span>  
  
2.  <span data-ttu-id="0e293-146">[プロパティ] ウィンドウ内で、**識別子**ボックスに、入力**contosoResponseXML**です。</span><span class="sxs-lookup"><span data-stu-id="0e293-146">In the Properties window, in the **Identifier** box, type **contosoResponseXML**.</span></span>  
  
3.  <span data-ttu-id="0e293-147">**型**ボックスで、  **\<.NET クラス\>**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="0e293-147">In the **Type** box, select **\<.NET Class\>** from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="0e293-148">Select の成果物入力ダイアログ ボックスで、左側のウィンドウで、**現在のプロジェクト**と**参照**、ノードを選択**System.Xml**を選択**XmlDocument**をクリックして右側のペインの一覧から**OK**です。</span><span class="sxs-lookup"><span data-stu-id="0e293-148">In the Select Artifact Type dialog box, in the left pane, under the **Current Project** and **References** nodes, select **System.Xml**, select **XmlDocument** from the list in the right pane, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="0e293-149">**オーケストレーション ビュー**、 をクリックして**変数**、クリックして**新しい変数**です。</span><span class="sxs-lookup"><span data-stu-id="0e293-149">In **Orchestration View**, click **Variables**,and then click **New Variable**.</span></span>  
  
6.  <span data-ttu-id="0e293-150">[プロパティ] ウィンドウ内で、**識別子**ボックスに、入力**submitMessage**です。</span><span class="sxs-lookup"><span data-stu-id="0e293-150">In the Properties window, in the **Identifier** box, type **submitMessage**.</span></span>  
  
7.  <span data-ttu-id="0e293-151">**型**ボックスで、  **\<.NET クラス\>**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="0e293-151">In the **Type** box, select **\<.NET Class\>** from the drop-down list.</span></span>  
  
8.  <span data-ttu-id="0e293-152">成果物の種類の選択 ダイアログ ボックスの左側のウィンドウで展開**現在のプロジェクト**と**参照**、ノードを選択**Microsoft.Solutions.BTARN.Shared**の選択**SubmitRNIF**をクリックして右側のペインの一覧から**OK**です。</span><span class="sxs-lookup"><span data-stu-id="0e293-152">In the Select Artifact Type dialog box, in the left pane, expand **Current Project** and **References** nodes, select **Microsoft.Solutions.BTARN.Shared**, select **SubmitRNIF** from the list in the right pane, and then click **OK**.</span></span>  
  
### <a name="to-change-the-orchestration-filter-expression"></a><span data-ttu-id="0e293-153">オーケストレーションのフィルター式を変更するには</span><span class="sxs-lookup"><span data-stu-id="0e293-153">To change the orchestration filter expression</span></span>  
  
1.  <span data-ttu-id="0e293-154">オーケストレーション デザイナーで、選択、 **[receivefrompublicprocessresponder]**図形です。</span><span class="sxs-lookup"><span data-stu-id="0e293-154">In Orchestration Designer, select the **ReceiveFromPublicProcessResponder** shape.</span></span>  
  
2.  <span data-ttu-id="0e293-155">プロパティ ウィンドウでの**フィルター式**ボックス、値 ボックスをクリックし、省略記号ボタンをクリックして (**.**) をフィルター式 ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="0e293-155">In the Properties window, in the **Filter Expression** box, click the value box, and then click the ellipsis button (**...**) to open the Filter Expression dialog box.</span></span>  
  
3.  <span data-ttu-id="0e293-156">フィルター式] ダイアログ ボックスで、 **Group By**セクションで、をクリックして、**または**値の最初の行にし、[ **AND**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="0e293-156">In the Filter Expression dialog box, in the **Group By** section, click the **OR** value on the first line, and then select **AND** from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="0e293-157">フィルター式 ダイアログ ボックスで、**ここをクリックして新しい行を追加する**、し、 **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="0e293-157">In the Filter Expression dialog box, click **Click here to add a new row**, and then select **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="0e293-158">同じ行の **値**、しに入力**「3 a 2」**です。</span><span class="sxs-lookup"><span data-stu-id="0e293-158">In the same row, click **Value**, and then type in **"3A2"**.</span></span>  
  
6.  <span data-ttu-id="0e293-159">同じ行の  **AND**で、 **Group By**ボックスし、**または**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="0e293-159">In the same row, click **AND** in the **Group By** box, and then select **OR** from the drop-down list.</span></span>  
  
7.  <span data-ttu-id="0e293-160">[フィルター式] ダイアログ ボックスで、前の手順で作成した行を選択し、上矢印ボタンを 1 回クリックして行を上に移動します。</span><span class="sxs-lookup"><span data-stu-id="0e293-160">In the Filter Expression dialog box, select the row that you just created, and then click the up arrow button once to move the row up once.</span></span>  
  
8.  <span data-ttu-id="0e293-161">をクリックして**ここをクリックして新しい行を追加する**、し、 **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="0e293-161">Click **Click here to add a new row**, and then select **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** from the drop-down list.</span></span>  
  
9. <span data-ttu-id="0e293-162">同じ行の **値**、しに入力**「3 a 2」**です。</span><span class="sxs-lookup"><span data-stu-id="0e293-162">In the same row, click **Value**, and then type in **"3A2"**.</span></span>  
  
10. <span data-ttu-id="0e293-163">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e293-163">Click OK.</span></span>  
  
### <a name="to-modify-the-business-process-workflow"></a><span data-ttu-id="0e293-164">ビジネス プロセスワークフローを変更するには</span><span class="sxs-lookup"><span data-stu-id="0e293-164">To modify the business process workflow</span></span>  
  
1.  <span data-ttu-id="0e293-165">ドラッグ、**メッセージの割り当て**図形をツールボックスからデザイン画面に、下にドロップし、 **[receivefrompublicprocessresponder]**図形です。</span><span class="sxs-lookup"><span data-stu-id="0e293-165">Drag a **Message Assignment** shape from the Toolbox to the design surface and drop it under the **ReceiveFromPublicProcessResponder** shape.</span></span> <span data-ttu-id="0e293-166">選択、 **ConstructMessage_1**図形が作成されたし、[、**プロパティ**] ウィンドウで、**名前**ボックスに、入力**[constructpip3a2requestmessage]**.</span><span class="sxs-lookup"><span data-stu-id="0e293-166">Select the **ConstructMessage_1** shape that was created and in the **Properties** window, in the **Name** box, type **ConstructPIP3A2RequestMessage**.</span></span>  
  
2.  <span data-ttu-id="0e293-167">ドラッグ、**変換**図形をデザイン画面に、下にドロップし、 **ConstructPIP3A2RequestMessage**図形です。</span><span class="sxs-lookup"><span data-stu-id="0e293-167">Drag a **Transform** shape to the design surface and drop it under the **ConstructPIP3A2RequestMessage** shape.</span></span> <span data-ttu-id="0e293-168">選択、 **ConstructMessage_1**図形が作成されたし、、**プロパティ**ウィンドウで、**名**ボックスに、入力**ConstructContoso3A2RequestMessage**.</span><span class="sxs-lookup"><span data-stu-id="0e293-168">Select the **ConstructMessage_1** shape that was created and in the **Properties** window, in the **Name** box, type **ConstructContoso3A2RequestMessage**.</span></span>  
  
3.  <span data-ttu-id="0e293-169">ドラッグ、**送信**図形をデザイン画面に、下にドロップし、 **ConstructContoso3A2RequestMessage**図形です。</span><span class="sxs-lookup"><span data-stu-id="0e293-169">Drag a **Send** shape to the design surface and drop it under the **ConstructContoso3A2RequestMessage** shape.</span></span>  
  
4.  <span data-ttu-id="0e293-170">ドラッグ、**受信**図形をデザイン画面に、下にドロップし、 **Send_1**図形です。</span><span class="sxs-lookup"><span data-stu-id="0e293-170">Drag a **Receive** shape to the design surface and drop it under the **Send_1** shape.</span></span>  
  
5.  <span data-ttu-id="0e293-171">オーケストレーション デザイン画面の空の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e293-171">On the orchestration design surface, click an empty area.</span></span>  
  
6.  <span data-ttu-id="0e293-172">[プロパティ] ウィンドウで、選択、**トランザクションの種類**プロパティ、およびクリック**長時間**です。</span><span class="sxs-lookup"><span data-stu-id="0e293-172">In the Properties window, select the **Transaction Type** property, and then click **Long Running**.</span></span>  
  
7.  <span data-ttu-id="0e293-173">ドラッグ、**スコープ**図形をデザイン画面に、下にドロップし、 **Receive_1**図形です。</span><span class="sxs-lookup"><span data-stu-id="0e293-173">Drag a **Scope** shape to the design surface and drop it under the **Receive_1** shape.</span></span>  
  
8.  <span data-ttu-id="0e293-174">[プロパティ] ウィンドウでから、**トランザクション タイプ**プロパティのドロップダウン リスト、選択**Atomic**の**スコープ**図形です。</span><span class="sxs-lookup"><span data-stu-id="0e293-174">In the Properties window, from the **Transaction Type** property drop-down list, select **Atomic** for the **Scope** shape.</span></span>  
  
9. <span data-ttu-id="0e293-175">ドラッグ、**ルールの呼び出し**図形をデザイン画面にし、というラベルの上にドロップ**ツールボックスからここに図形をドロップ**内、**スコープ**図形です。</span><span class="sxs-lookup"><span data-stu-id="0e293-175">Drag a **Call Rules** shape to the design surface and drop it on the label that says **Drop a shape from the toolbox here** inside the **Scope** shape.</span></span> <span data-ttu-id="0e293-176">[プロパティ] ウィンドウで、**ルールの呼び出し**図形、**名前**ボックスに、入力**Execute3A2Vocabulary**です。</span><span class="sxs-lookup"><span data-stu-id="0e293-176">In the Properties window for the **Call Rules** shape, in the **Name** box, type **Execute3A2Vocabulary**.</span></span>  
  
10. <span data-ttu-id="0e293-177">ドラッグ、**変換**図形をデザイン画面に、下にドロップし、 **スコープ _ 1**図形です。</span><span class="sxs-lookup"><span data-stu-id="0e293-177">Drag a **Transform** shape to the design surface and drop it under the **Scope_1** shape.</span></span> <span data-ttu-id="0e293-178">クリックして、 **ConstructMessage_1**図形です。</span><span class="sxs-lookup"><span data-stu-id="0e293-178">Click the **ConstructMessage_1** shape.</span></span> <span data-ttu-id="0e293-179">[プロパティ] ウィンドウでの**名前**ボックスに、入力**Construct3A2ResponseMessage**です。</span><span class="sxs-lookup"><span data-stu-id="0e293-179">In the Properties window, in the **Name** box, type **Construct3A2ResponseMessage**.</span></span>  
  
11. <span data-ttu-id="0e293-180">ドラッグ、**式**図形をデザイン画面に、下にドロップし、 **Construct3A2ResponseMessageTransform**図形です。</span><span class="sxs-lookup"><span data-stu-id="0e293-180">Drag an **Expression** shape to the design surface and drop it under the **Construct3A2ResponseMessageTransform** shape.</span></span>  
  
12. <span data-ttu-id="0e293-181">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ファイル**をクリックして**すべてを保存**プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="0e293-181">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File**, click **Save All** to save the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e293-182">参照</span><span class="sxs-lookup"><span data-stu-id="0e293-182">See Also</span></span>  
 [<span data-ttu-id="0e293-183">手順 6: オーケストレーション図形の構成 (Contoso)</span><span class="sxs-lookup"><span data-stu-id="0e293-183">Step 6: Configuring Orchestration Shapes (Contoso)</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-configuring-orchestration-shapes-contoso.md)