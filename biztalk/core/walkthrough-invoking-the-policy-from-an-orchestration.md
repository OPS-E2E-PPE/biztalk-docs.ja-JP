---
title: 'チュートリアル: オーケストレーションからのポリシーの呼び出し |Microsoft Docs'
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb2d2974-8a36-4d36-905c-799e4236ef99
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33bef51b2c702e71fcf6ef0ea0c4fd63b28fbde8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976561"
---
# <a name="walkthrough-invoking-the-policy-from-an-orchestration"></a><span data-ttu-id="58247-102">チュートリアル: オーケストレーションからのポリシーの呼び出し</span><span class="sxs-lookup"><span data-stu-id="58247-102">Walkthrough: Invoking the Policy from an Orchestration</span></span>
<span data-ttu-id="58247-103">ポリシーは、次のいずれかの方法でオーケストレーションから呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="58247-103">You can invoke a policy from an orchestration in one of the following ways:</span></span>  

- <span data-ttu-id="58247-104">使用して、**ルールの呼び出し**図形</span><span class="sxs-lookup"><span data-stu-id="58247-104">By using the **Call Rules** shape</span></span>  

- <span data-ttu-id="58247-105">使用して、**式**図形、およびポリシーを実行するルール エンジンをプログラムで呼び出す (**Policy.Execute**メソッド)</span><span class="sxs-lookup"><span data-stu-id="58247-105">By using the **Expression** shape, and programmatically invoking the rule engine to execute the policy (**Policy.Execute** method)</span></span>  

  <span data-ttu-id="58247-106">使用して、**ルールの呼び出し**図形は、最も一般的な方法ともオーケストレーションからポリシーを呼び出すをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="58247-106">Using the **Call Rules** shape is the most common way and also the recommended way to invoke a policy from an orchestration.</span></span> <span data-ttu-id="58247-107">このチュートリアルでは、詳細な手順を使用して、**ルールの呼び出し**図形を呼び出す、 **ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="58247-107">This walkthrough provides step-by-step procedures for using the **Call Rules** shape to invoke the **ProcessPurchaseOrder** policy.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="58247-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="58247-108">Prerequisites</span></span>  
 <span data-ttu-id="58247-109">完了する必要があります、[チュートリアル: ポリシーのテスト](../core/walkthrough-testing-the-policy.md)このチュートリアルを実行する前にチュートリアル。</span><span class="sxs-lookup"><span data-stu-id="58247-109">You must complete the [Walkthrough: Testing the Policy](../core/walkthrough-testing-the-policy.md) walkthrough before performing this walkthrough.</span></span>  

## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="58247-110">このチュートリアルの概要</span><span class="sxs-lookup"><span data-stu-id="58247-110">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="58247-111">次の表に示すように、このチュートリアルには 7 つの手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="58247-111">This walkthrough contains seven procedures, as described in the following table.</span></span>  

|<span data-ttu-id="58247-112">プロシージャ タイトル</span><span class="sxs-lookup"><span data-stu-id="58247-112">Procedure title</span></span>|<span data-ttu-id="58247-113">手順の説明</span><span class="sxs-lookup"><span data-stu-id="58247-113">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="58247-114">スキーマとオーケストレーションを使用して BizTalk プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="58247-114">To create a BizTalk project with a schema and an orchestration</span></span>|<span data-ttu-id="58247-115">スキーマと呼び出すオーケストレーションを作成するための手順について説明します、 **ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="58247-115">Provides step-by-step instructions for creating a schema and an orchestration that invokes the **ProcessPurchaseOrder** policy.</span></span>|  
|<span data-ttu-id="58247-116">メッセージ変数を作成するには</span><span class="sxs-lookup"><span data-stu-id="58247-116">To create message variables</span></span>|<span data-ttu-id="58247-117">ステップごとの説明に従って、オーケストレーションで使用されるメッセージ変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="58247-117">Provides step-by-step instructions for creating message variables used in the orchestration.</span></span>|  
|<span data-ttu-id="58247-118">図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="58247-118">To configure shapes</span></span>|<span data-ttu-id="58247-119">ステップごとの説明に従って、オーケストレーションの図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="58247-119">Provides step-by-step instructions for configuring shapes in the orchestration.</span></span>|  
|<span data-ttu-id="58247-120">ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="58247-120">To create ports</span></span>|<span data-ttu-id="58247-121">ステップごとの説明に従って、オーケストレーションのポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="58247-121">Provides step-by-step instructions for creating ports in the orchestration.</span></span>|  
|<span data-ttu-id="58247-122">ポートを図形に接続するには</span><span class="sxs-lookup"><span data-stu-id="58247-122">To connect ports with the shapes</span></span>|<span data-ttu-id="58247-123">ステップごとの説明に従って、ポートを図形に接続します。</span><span class="sxs-lookup"><span data-stu-id="58247-123">Provides step-by-step instructions for connecting ports with the shapes.</span></span>|  
|<span data-ttu-id="58247-124">ソリューションをビルドおよび配置するには</span><span class="sxs-lookup"><span data-stu-id="58247-124">To build and deploy the solution</span></span>|<span data-ttu-id="58247-125">ステップごとの説明に従って、ソリューションをビルドおよび展開します。</span><span class="sxs-lookup"><span data-stu-id="58247-125">Provides step-by-step instructions for building and deploying the solution.</span></span>|  
|<span data-ttu-id="58247-126">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="58247-126">To test the solution</span></span>|<span data-ttu-id="58247-127">ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="58247-127">Provides step-by-step instructions for testing the solution.</span></span>|  

### <a name="to-create-a-biztalk-project-with-a-schema-and-an-orchestration"></a><span data-ttu-id="58247-128">スキーマとオーケストレーションを使用して BizTalk プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="58247-128">To create a BizTalk project with a schema and an orchestration</span></span>  

1. <span data-ttu-id="58247-129">開始**Microsoft Visual Studio**します。</span><span class="sxs-lookup"><span data-stu-id="58247-129">Start **Microsoft Visual Studio**.</span></span>  

2. <span data-ttu-id="58247-130">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="58247-130">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  

3. <span data-ttu-id="58247-131">**新しいプロジェクト** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="58247-131">In the **New Project** dialog box, do the following:</span></span>  


   |             <span data-ttu-id="58247-132">プロパティ</span><span class="sxs-lookup"><span data-stu-id="58247-132">Use this</span></span>              |                             <span data-ttu-id="58247-133">目的</span><span class="sxs-lookup"><span data-stu-id="58247-133">To do this</span></span>                              |
   |-----------------------------------|---------------------------------------------------------------------|
   |         <span data-ttu-id="58247-134">**プロジェクトの種類**</span><span class="sxs-lookup"><span data-stu-id="58247-134">**Project types**</span></span>         |                     <span data-ttu-id="58247-135">クリックして**BizTalk プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="58247-135">Click **BizTalk Projects**.</span></span>                     |
   |           <span data-ttu-id="58247-136">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="58247-136">**Templates**</span></span>           |               <span data-ttu-id="58247-137">クリックして**空の BizTalk Server プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="58247-137">Click **Empty BizTalk Server Project**.</span></span>               |
   |             <span data-ttu-id="58247-138">**名前**</span><span class="sxs-lookup"><span data-stu-id="58247-138">**Name**</span></span>              |                         <span data-ttu-id="58247-139">型**RuleTest**します。</span><span class="sxs-lookup"><span data-stu-id="58247-139">Type **RuleTest**.</span></span>                          |
   |           <span data-ttu-id="58247-140">**場所**</span><span class="sxs-lookup"><span data-stu-id="58247-140">**Location**</span></span>            |                  <span data-ttu-id="58247-141">指定**C:\BRE-Walkthroughs**します。</span><span class="sxs-lookup"><span data-stu-id="58247-141">Specify **C:\BRE-Walkthroughs**.</span></span>                   |
   |         <span data-ttu-id="58247-142">**[ソリューション名]**</span><span class="sxs-lookup"><span data-stu-id="58247-142">**Solution Name**</span></span>         |                        <span data-ttu-id="58247-143">型**RuleTestSol**します。</span><span class="sxs-lookup"><span data-stu-id="58247-143">Type **RuleTestSol**.</span></span>                        |
   | <span data-ttu-id="58247-144">**ソリューションのディレクトリを作成します。**</span><span class="sxs-lookup"><span data-stu-id="58247-144">**Create directory for solution**</span></span> | <span data-ttu-id="58247-145">ソリューション ファイルのディレクトリを作成するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="58247-145">Select this check box to create a directory for the solution files.</span></span> |


4. <span data-ttu-id="58247-146">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58247-146">Click **OK**.</span></span> <span data-ttu-id="58247-147">**RuleTest**プロジェクトがソリューション エクスプ ローラーで表示されます。</span><span class="sxs-lookup"><span data-stu-id="58247-147">The **RuleTest** project should appear in Solution Explorer.</span></span> <span data-ttu-id="58247-148">ソリューション エクスプ ローラーが表示されない場合はクリックして**ソリューション エクスプ ローラー**上、**ビュー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="58247-148">If you do not see Solution Explorer, click **Solution Explorer** on the **View** menu.</span></span>  

5. <span data-ttu-id="58247-149">ソリューション エクスプ ローラーで右クリック**RuleTest**、 をポイント**追加**、 をクリックし、**既存項目の**。</span><span class="sxs-lookup"><span data-stu-id="58247-149">In Solution Explorer, right-click **RuleTest**, point to **Add**, and then click **Existing Item**.</span></span>  

6. <span data-ttu-id="58247-150">参照し、追加、 **PO.xsd**で作成したスキーマ ファイル、[チュートリアル: 単純なビジネス ポリシーを作成する](../core/walkthrough-creating-a-simple-business-policy.md)チュートリアル。</span><span class="sxs-lookup"><span data-stu-id="58247-150">Browse and add the **PO.xsd** schema file you created in the [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md) walkthrough.</span></span> <span data-ttu-id="58247-151">Visual Studio でのコピー、 **PO.xsd**ファイルを開き、プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="58247-151">Visual Studio makes a copy of the **PO.xsd** file and adds it to the project.</span></span>  

7. <span data-ttu-id="58247-152">ソリューション エクスプ ローラーで右クリック**RuleTest**、 をポイント**追加**、 をクリックし、**新しい項目の**。</span><span class="sxs-lookup"><span data-stu-id="58247-152">In Solution Explorer, right-click **RuleTest**, point to **Add**, and then click **New Item**.</span></span>  

8. <span data-ttu-id="58247-153">**新しい項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="58247-153">In the **Add New Item** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="58247-154">プロパティ</span><span class="sxs-lookup"><span data-stu-id="58247-154">Use this</span></span>    |            <span data-ttu-id="58247-155">目的</span><span class="sxs-lookup"><span data-stu-id="58247-155">To do this</span></span>            |
   |----------------|----------------------------------|
   | <span data-ttu-id="58247-156">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="58247-156">**Categories**</span></span> |  <span data-ttu-id="58247-157">クリックして**オーケストレーション ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="58247-157">Click **Orchestration Files**.</span></span>  |
   | <span data-ttu-id="58247-158">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="58247-158">**Templates**</span></span>  | <span data-ttu-id="58247-159">クリックして**BizTalk オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="58247-159">Click **BizTalk Orchestration**.</span></span> |
   |    <span data-ttu-id="58247-160">**名前**</span><span class="sxs-lookup"><span data-stu-id="58247-160">**Name**</span></span>    |      <span data-ttu-id="58247-161">型**RuleTest.odx**します。</span><span class="sxs-lookup"><span data-stu-id="58247-161">Type **RuleTest.odx**.</span></span>      |


9. <span data-ttu-id="58247-162">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58247-162">Click **Add**.</span></span>  

10. <span data-ttu-id="58247-163">右クリックして**ここで、ツールボックスから図形をドロップ**、 をポイント**図形の挿入**、順にクリックします**受信**します。</span><span class="sxs-lookup"><span data-stu-id="58247-163">Right-click **Drop a shape from the toolbox here**, point to **Insert Shape**, and then click **Receive**.</span></span>  

11. <span data-ttu-id="58247-164">[プロパティ] ウィンドウでの名前変更、**受信**図形を **[receivepo]** の値を設定し、**アクティブ化**プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="58247-164">In the Properties window, change the name of the **Receive** shape to **ReceivePO**, and set the value of the **Activate** property to `true`.</span></span>  

12. <span data-ttu-id="58247-165">ツールボックスで、上、 **BizTalk オーケストレーション** タブで、ドラッグ、**ルールの呼び出し**図形を区分線の下に、**受信**図形。</span><span class="sxs-lookup"><span data-stu-id="58247-165">In the Toolbox, on the **BizTalk Orchestrations** tab, drag the **Call Rules** shape onto a connecting line below the **Receive** shape.</span></span>  

13. <span data-ttu-id="58247-166">[プロパティ] ウィンドウでの名前変更、**ルールの呼び出し**図形を**CallProcessPOPolicy**します。</span><span class="sxs-lookup"><span data-stu-id="58247-166">In the Properties window, change the name of the **Call Rules** shape to **CallProcessPOPolicy**.</span></span>  

14. <span data-ttu-id="58247-167">下を右クリック、**ルールの呼び出し**図形をポイントして、**図形の挿入**、 をクリックし、**送信**します。</span><span class="sxs-lookup"><span data-stu-id="58247-167">Right-click below the **Call Rules** shape, point to **Insert Shape**, and then click **Send**.</span></span>  

15. <span data-ttu-id="58247-168">[プロパティ] ウィンドウでの名前変更、**送信**図形を**SendPO**します。</span><span class="sxs-lookup"><span data-stu-id="58247-168">In the Properties window, change the name of the **Send** shape to **SendPO**.</span></span> <span data-ttu-id="58247-169">オーケストレーションは次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="58247-169">The orchestration should look like the following figure.</span></span>  

     <span data-ttu-id="58247-170">![BRE&#45;チュートリアル&#45;UnconfiguredOrch](../core/media/1f3502ac-82a9-40bf-ae31-6e8356a283e2.gif "1f3502ac-82a9-40bf-ae31-6e8356a283e2")</span><span class="sxs-lookup"><span data-stu-id="58247-170">![BRE&#45;Walkthrough&#45;UnconfiguredOrch](../core/media/1f3502ac-82a9-40bf-ae31-6e8356a283e2.gif "1f3502ac-82a9-40bf-ae31-6e8356a283e2")</span></span>  

### <a name="to-create-message-variables"></a><span data-ttu-id="58247-171">メッセージ変数を作成するには</span><span class="sxs-lookup"><span data-stu-id="58247-171">To create message variables</span></span>  

1.  <span data-ttu-id="58247-172">オーケストレーションの種類 ウィンドウで、右クリック**メッセージ**、 をクリックし、**新しいメッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="58247-172">In the Orchestration View window, right-click **Messages**, and then click **New Message**.</span></span> <span data-ttu-id="58247-173">オーケストレーションの種類 ウィンドウが表示されない場合はクリックして、**ビュー**メニューで、**その他の Windows**、順にクリックします**オーケストレーション**。</span><span class="sxs-lookup"><span data-stu-id="58247-173">If you do not see the Orchestration View window, click the **View** menu, point to **Other Windows**, and then click **Orchestration View**.</span></span> <span data-ttu-id="58247-174">通常、[オーケストレーションの種類] ウィンドウは、[ソリューション エクスプローラー] タブの隣のタブにあります。既定では、新しいメッセージが名前付き**Message_1**します。</span><span class="sxs-lookup"><span data-stu-id="58247-174">Typically, the Orchestration View window is on the tab next to the Solution Explorer tab. By default, the new message is named **Message_1**.</span></span>  

     <span data-ttu-id="58247-175">![BRE&#45;チュートリアル&#45;OrchViewNewMsg](../core/media/a0b7fee3-af90-4c01-9464-146f0ca449e5.gif "a0b7fee3-af90-4c01-9464-146f0ca449e5")</span><span class="sxs-lookup"><span data-stu-id="58247-175">![BRE&#45;Walkthrough&#45;OrchViewNewMsg](../core/media/a0b7fee3-af90-4c01-9464-146f0ca449e5.gif "a0b7fee3-af90-4c01-9464-146f0ca449e5")</span></span>  

2.  <span data-ttu-id="58247-176">オーケストレーションの種類] ウィンドウで、[ **Message_1**します。</span><span class="sxs-lookup"><span data-stu-id="58247-176">In the Orchestration View window, click **Message_1**.</span></span>  

3.  <span data-ttu-id="58247-177">[プロパティ ウィンドウ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="58247-177">In the Properties window, do the following:</span></span>  

    |<span data-ttu-id="58247-178">プロパティ</span><span class="sxs-lookup"><span data-stu-id="58247-178">Use this</span></span>|<span data-ttu-id="58247-179">目的</span><span class="sxs-lookup"><span data-stu-id="58247-179">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="58247-180">**[Identifier]**</span><span class="sxs-lookup"><span data-stu-id="58247-180">**Identifier**</span></span>|<span data-ttu-id="58247-181">型 **[poinst]**、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="58247-181">Type **POInst**, and then press ENTER.</span></span>|  
    |<span data-ttu-id="58247-182">**メッセージの種類**</span><span class="sxs-lookup"><span data-stu-id="58247-182">**Message Type**</span></span>|<span data-ttu-id="58247-183">ドロップダウン リストから展開**スキーマ**、し、 **RuleTest.PO**します。</span><span class="sxs-lookup"><span data-stu-id="58247-183">From the drop-down list, expand **Schemas**, and then select **RuleTest.PO**.</span></span>|  

     <span data-ttu-id="58247-184">![BRE&#45;チュートリアル&#45;MsgProps](../core/media/c82cfb67-63f6-4133-95bf-daadac0e213a.gif "c82cfb67-63f6-4133-95bf-daadac0e213a")</span><span class="sxs-lookup"><span data-stu-id="58247-184">![BRE&#45;Walkthrough&#45;MsgProps](../core/media/c82cfb67-63f6-4133-95bf-daadac0e213a.gif "c82cfb67-63f6-4133-95bf-daadac0e213a")</span></span>  

### <a name="to-configure-shapes"></a><span data-ttu-id="58247-185">図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="58247-185">To configure shapes</span></span>  

1. <span data-ttu-id="58247-186">選択、**受信**オーケストレーション デザイナーで図形。</span><span class="sxs-lookup"><span data-stu-id="58247-186">Select the **Receive** shape in Orchestration Designer.</span></span>  

2. <span data-ttu-id="58247-187">[プロパティ] ウィンドウで次のように選択します。 **[poinst]** の、**メッセージ**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="58247-187">In the Properties window, select **POInst** for the **Message** property.</span></span>  

3. <span data-ttu-id="58247-188">ダブルクリックして、**ルールの呼び出し**オーケストレーション デザイナーで図形。</span><span class="sxs-lookup"><span data-stu-id="58247-188">Double-click the **Call Rules** shape in Orchestration Designer.</span></span>  

4. <span data-ttu-id="58247-189">**ルールの呼び出しのポリシー構成**ダイアログ ボックスで、 **ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="58247-189">In the **Call Rules policy configuration** dialog box, select **ProcessPurchaseOrder** for the policy.</span></span>  

5. <span data-ttu-id="58247-190">[横] をクリックして**\\**<em>下の \* \* パラメーター名</em><em>を選択して \**[poinst]</em>* ポリシーへのパラメーターとして。</span><span class="sxs-lookup"><span data-stu-id="58247-190">Click next to **\\**<em>, below \*\*Parameter Name</em><em>, and select \**POInst</em>* as a parameter to the policy.</span></span>  

    <span data-ttu-id="58247-191">![BRE&#45;チュートリアル&#45;ConfigureCallRules](../core/media/0e7dab04-41db-433b-bbf5-b13901033b41.gif "0e7dab04-41db-433b-bbf5-b13901033b41")</span><span class="sxs-lookup"><span data-stu-id="58247-191">![BRE&#45;Walkthrough&#45;ConfigureCallRules](../core/media/0e7dab04-41db-433b-bbf5-b13901033b41.gif "0e7dab04-41db-433b-bbf5-b13901033b41")</span></span>  

6. <span data-ttu-id="58247-192">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58247-192">Click **OK**.</span></span>  

7. <span data-ttu-id="58247-193">選択、**送信**オーケストレーションの図形。</span><span class="sxs-lookup"><span data-stu-id="58247-193">Select the **Send** shape in the orchestration.</span></span>  

8. <span data-ttu-id="58247-194">[プロパティ] ウィンドウでの値を設定、**メッセージの種類**プロパティを **[poinst]** します。</span><span class="sxs-lookup"><span data-stu-id="58247-194">In the Properties window, set the value of the **Message Type** property to **POInst**.</span></span>  

### <a name="to-create-ports"></a><span data-ttu-id="58247-195">ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="58247-195">To create ports</span></span>  

1.  <span data-ttu-id="58247-196">2 つのフォルダーを作成する**入力**と**出力**、C:\BRE-Walkthroughs\RuleTestSol フォルダー内です。</span><span class="sxs-lookup"><span data-stu-id="58247-196">Create two folders, **Input** and **Output**, in the C:\BRE-Walkthroughs\RuleTestSol folder.</span></span>  

2.  <span data-ttu-id="58247-197">オーケストレーションの左のポート画面を右クリックし、クリックして**新しい構成済みポート**。</span><span class="sxs-lookup"><span data-stu-id="58247-197">Right-click the left port surface of the orchestration, and then click **New Configured Port**.</span></span>  

3.  <span data-ttu-id="58247-198">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58247-198">Click **Next**.</span></span> <span data-ttu-id="58247-199">型**ReceivePOPrt**ポートの名前をします。</span><span class="sxs-lookup"><span data-stu-id="58247-199">Type **ReceivePOPrt** for the port name.</span></span>  

4.  <span data-ttu-id="58247-200">クリックして**次**2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="58247-200">Click **Next** twice.</span></span>  

5.  <span data-ttu-id="58247-201">選択**今指定**の**ポートのバインド**します。</span><span class="sxs-lookup"><span data-stu-id="58247-201">Select **Specify Now** for the **port binding**.</span></span>  

6.  <span data-ttu-id="58247-202">指定**ファイル**の**トランスポート**、入力ディレクトリの名前を入力および**C:\BRE-Walkthroughs\RuleTestSol\Input\\\*.xml**ファイル マスク (**\*.xml**) の URI。</span><span class="sxs-lookup"><span data-stu-id="58247-202">Specify **FILE** for the **transport**, and type the name of the input directory as **C:\BRE-Walkthroughs\RuleTestSol\Input\\\*.xml** along with the file mask (**\*.xml**) for the URI.</span></span>  

7.  <span data-ttu-id="58247-203">**[次へ]** をクリックし、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58247-203">Click **Next**, and then click **Finish**.</span></span>  

8.  <span data-ttu-id="58247-204">クリックして、オーケストレーションの右ポート画面を右クリックして**新しい構成ポート**します。</span><span class="sxs-lookup"><span data-stu-id="58247-204">Right-click the right port surface of the orchestration, and then click **New Configuration Port**.</span></span>  

9. <span data-ttu-id="58247-205">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58247-205">Click **Next**.</span></span> <span data-ttu-id="58247-206">型**SendPOPort**ポートの名前をします。</span><span class="sxs-lookup"><span data-stu-id="58247-206">Type **SendPOPort** for the port name.</span></span>  

10. <span data-ttu-id="58247-207">クリックして**次**2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="58247-207">Click **Next** twice.</span></span>  

11. <span data-ttu-id="58247-208">変更、**ポートの通信方向**に**は常にメッセージを送信しますこのポートで**します。</span><span class="sxs-lookup"><span data-stu-id="58247-208">Change the **Port direction of communication** to **I'll always be sending messages on this port**.</span></span>  

12. <span data-ttu-id="58247-209">選択**今指定**の**ポートのバインド**します。</span><span class="sxs-lookup"><span data-stu-id="58247-209">Select **Specify Now** for the **port binding**.</span></span>  

13. <span data-ttu-id="58247-210">指定**ファイル**の**トランスポート**、として出力ディレクトリの名前を入力および**C:\BRE-Walkthroughs\RuleTestSol\Output**、%messageid%.xml 出力ファイル名前。</span><span class="sxs-lookup"><span data-stu-id="58247-210">Specify **FILE** for the **transport**, and type the name of the output directory as **C:\BRE-Walkthroughs\RuleTestSol\Output**,and %MessageID%.xml as the output file name.</span></span>  

14. <span data-ttu-id="58247-211">**[次へ]** をクリックし、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58247-211">Click **Next**, and then click **Finish**.</span></span>  

### <a name="to-connect-ports-with-the-shapes"></a><span data-ttu-id="58247-212">ポートを図形に接続するには</span><span class="sxs-lookup"><span data-stu-id="58247-212">To connect ports with the shapes</span></span>  

1.  <span data-ttu-id="58247-213">接続、 **ReceivePOPrt**ポートを**ReceivePO**図形。</span><span class="sxs-lookup"><span data-stu-id="58247-213">Connect the **ReceivePOPrt** port to the **ReceivePO** shape.</span></span> <span data-ttu-id="58247-214">ポート画面の [ReceivePOPrt] ポートの右側の矢印を [ReceivePO] 図形のボックスにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="58247-214">(Drag the arrow to the right of ReceivePOPrt port on the port surface to the box on the ReceivePO shape.)</span></span>  

     <span data-ttu-id="58247-215">![BRE&#45;チュートリアル&#45;ConnectRP](../core/media/75bdf79e-ca98-43bb-8ff6-5f46005a6490.gif "75bdf79e-ca98-43bb-8ff6-5f46005a6490")</span><span class="sxs-lookup"><span data-stu-id="58247-215">![BRE&#45;Walkthrough&#45;ConnectRP](../core/media/75bdf79e-ca98-43bb-8ff6-5f46005a6490.gif "75bdf79e-ca98-43bb-8ff6-5f46005a6490")</span></span>  

2.  <span data-ttu-id="58247-216">接続、 **SendPO**図形を **[sendpoprt]** ポート。</span><span class="sxs-lookup"><span data-stu-id="58247-216">Connect the **SendPO** shape to the **SendPOPrt** port.</span></span>  

     <span data-ttu-id="58247-217">![BRE&#45;チュートリアル&#45;ConnectSP](../core/media/7513f52b-2782-4357-b8eb-1874dec33869.gif "7513f52b-2782-4357-b8eb-1874dec33869")</span><span class="sxs-lookup"><span data-stu-id="58247-217">![BRE&#45;Walkthrough&#45;ConnectSP](../core/media/7513f52b-2782-4357-b8eb-1874dec33869.gif "7513f52b-2782-4357-b8eb-1874dec33869")</span></span>  

### <a name="to-build-and-deploy-the-solution"></a><span data-ttu-id="58247-218">ソリューションをビルドおよび配置するには</span><span class="sxs-lookup"><span data-stu-id="58247-218">To build and deploy the solution</span></span>  

1. <span data-ttu-id="58247-219">開始**Microsoft Visual Studio**します。</span><span class="sxs-lookup"><span data-stu-id="58247-219">Start **Microsoft Visual Studio**.</span></span>  

2. <span data-ttu-id="58247-220">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで右クリックし、 **RuleTest**プロジェクトをクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="58247-220">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], in Solution Explorer, right-click the **RuleTest** project, and then click **Properties**.</span></span>  

3. <span data-ttu-id="58247-221">プロジェクト デザイナー (中央のウィンドウ) で、次のようにクリックします。**署名**します。</span><span class="sxs-lookup"><span data-stu-id="58247-221">In Project Designer (in the center pane), click **Signing**.</span></span>  

4. <span data-ttu-id="58247-222">署名 タブで確認**アセンブリに署名**チェック ボックスをオンにします。ドロップダウン リストで**厳密な名前キー ファイルを選択して**、 をクリックして**新規**;**キー ファイル名**フィールドに、ルールのテストの入力**パスワード**(省略可能) をフィールドにパスワードを設定してクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="58247-222">In Signing tab, Check **Sign the assembly** checkbox; In the dropdown list **Choose a strong name key file**, click **New**; In the **Key File name** field, enter Rule Test; In the **Password** field (Optional),  set Password, and then click **OK**.</span></span>  

5. <span data-ttu-id="58247-223">プロジェクト デザイナーで、次のようにクリックします。**展開**展開 タブに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="58247-223">In Project Designer, click **Deployment** to switch to the Deployment tab.</span></span>  

6. <span data-ttu-id="58247-224">指定**RuleTestApp**アプリケーション名として。</span><span class="sxs-lookup"><span data-stu-id="58247-224">Specify **RuleTestApp** as the application name.</span></span>  

    <span data-ttu-id="58247-225">![BRE&#45;チュートリアル&#45;RuleTestApp](../core/media/b153e5b0-ca46-4d27-bfa1-9ad4e58e9787.gif "b153e5b0-ca46-4d27-bfa1-9ad4e58e9787")</span><span class="sxs-lookup"><span data-stu-id="58247-225">![BRE&#45;Walkthrough&#45;RuleTestApp](../core/media/b153e5b0-ca46-4d27-bfa1-9ad4e58e9787.gif "b153e5b0-ca46-4d27-bfa1-9ad4e58e9787")</span></span>  

7. <span data-ttu-id="58247-226">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58247-226">Click **OK**.</span></span>  

8. <span data-ttu-id="58247-227">右クリックし、 **RuleTest**プロジェクトをクリックして**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="58247-227">Right-click the **RuleTest** project, and then click **Build**.</span></span>  

9. <span data-ttu-id="58247-228">右クリックし、 **RuleTest**プロジェクトをクリックして**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="58247-228">Right-click the **RuleTest** project, and then click **Deploy**.</span></span>  

### <a name="to-test-the-solution"></a><span data-ttu-id="58247-229">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="58247-229">To test the solution</span></span>  

1. <span data-ttu-id="58247-230">ビジネス ルール作成ツールで展開**ポリシー**、展開**ProcessPurchaseOrder**を右クリックして**バージョン 1.0**、 をクリックし、**発行**.</span><span class="sxs-lookup"><span data-stu-id="58247-230">In Business Rule Composer, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.0**, and then click **Publish**.</span></span>  

2. <span data-ttu-id="58247-231">右クリック**バージョン 1.0 - 公開済み**、 をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="58247-231">Right-click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  

3. <span data-ttu-id="58247-232">**開始**] メニューの [open **BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="58247-232">In the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="58247-233">BizTalk Server 管理コンソールを既に開いている場合は、F5 キーを押して更新します。</span><span class="sxs-lookup"><span data-stu-id="58247-233">If you have the BizTalk Server Administration console already open, press F5 to refresh it.</span></span>  

4. <span data-ttu-id="58247-234">展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="58247-234">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and then expand **Applications**.</span></span>  

5. <span data-ttu-id="58247-235">右クリック**RuleTestApp**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="58247-235">Right-click **RuleTestApp**, and then click **Configure**.</span></span>  

6. <span data-ttu-id="58247-236">をクリックして**Orchestration_1**、し、指定**BizTalkServerApplication**としてホストします。</span><span class="sxs-lookup"><span data-stu-id="58247-236">Click **Orchestration_1**, and specify **BizTalkServerApplication** as the host.</span></span>  

    <span data-ttu-id="58247-237">![BRE&#45;チュートリアル&#45;AppHost](../core/media/ba348a98-661f-4e71-8b9b-b8c5fadf035a.gif "ba348a98-661f-4e71-8b9b-b8c5fadf035a")</span><span class="sxs-lookup"><span data-stu-id="58247-237">![BRE&#45;Walkthrough&#45;AppHost](../core/media/ba348a98-661f-4e71-8b9b-b8c5fadf035a.gif "ba348a98-661f-4e71-8b9b-b8c5fadf035a")</span></span>  

7. <span data-ttu-id="58247-238">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58247-238">Click **OK**.</span></span>  

8. <span data-ttu-id="58247-239">右クリック**RuleTestApp**、 をクリックし、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="58247-239">Right-click **RuleTestApp**, and then click **Start**.</span></span>  

9. <span data-ttu-id="58247-240">**'RuleTestApp' アプリケーションの起動**ダイアログ ボックスで、をクリックして**開始**アプリケーションが正常に開始されるを待ちます。</span><span class="sxs-lookup"><span data-stu-id="58247-240">In the **Start 'RuleTestApp' Application** dialog box, click **Start**, and then wait until the application is started successfully.</span></span>  

10. <span data-ttu-id="58247-241">開いている**SamplePO.xml**と**SamplePO2.xml**メモ帳での値を変更し、**状態**フィールドを**XYZ**します。</span><span class="sxs-lookup"><span data-stu-id="58247-241">Open **SamplePO.xml** and **SamplePO2.xml** in Notepad and change the value of the **Status** field to **XYZ**.</span></span>  

11. <span data-ttu-id="58247-242">コピー、 **SamplePO.xml**オーケストレーション用の C:\BRE-Walkthroughs\RuleTestSol\Input ディレクトリに C:\BRE-Walkthroughs ディレクトリからファイル。</span><span class="sxs-lookup"><span data-stu-id="58247-242">Copy the **SamplePO.xml** file from the C:\BRE-Walkthroughs directory to the C:\BRE-Walkthroughs\RuleTestSol\Input directory for the orchestration.</span></span>  

12. <span data-ttu-id="58247-243">オーケストレーションの C:\BRE-Walkthroughs\RuleTestSol\Output ディレクトリに出力ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="58247-243">You should see an output file in the C:\BRE-Walkthroughs\RuleTestSol\Output directory for the orchestration.</span></span> <span data-ttu-id="58247-244">出力 XML ファイルを開き、注意の値、**状態**にフィールドが設定されている**Approved**します。</span><span class="sxs-lookup"><span data-stu-id="58247-244">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  

13. <span data-ttu-id="58247-245">手順 11. ~ 12. を繰り返します**SamplePO2.xml**、いることを確認しの値、**状態**出力ドキュメント内のフィールドは、入力ドキュメントと同じ (**xyz**)。</span><span class="sxs-lookup"><span data-stu-id="58247-245">Repeat steps 11 and 12 with **SamplePO2.xml**, and notice that the value of the **Status** field in the output document is the same as in the input document (**xyz**).</span></span>  

## <a name="comments"></a><span data-ttu-id="58247-246">コメント</span><span class="sxs-lookup"><span data-stu-id="58247-246">Comments</span></span>  

-   <span data-ttu-id="58247-247">このチュートリアルでは、オーケストレーションに図形を追加する際に、ツールボックスの図形は使用しませんでした。</span><span class="sxs-lookup"><span data-stu-id="58247-247">In this walkthrough, to add the shapes to the orchestration, you did not use the shapes from the Toolbox.</span></span> <span data-ttu-id="58247-248">代わりに、マウスの右ボタンをクリックして挿入する図形を選択しました。</span><span class="sxs-lookup"><span data-stu-id="58247-248">Instead, you clicked the right mouse button and selected the shape that you wanted to insert.</span></span>  

-   <span data-ttu-id="58247-249">構成、**ルールの呼び出し**図形が使用される型を決定するときに保存されている最新バージョンは。</span><span class="sxs-lookup"><span data-stu-id="58247-249">The configuration for the **Call Rules** shape looks at the latest saved version when determining the types used.</span></span> <span data-ttu-id="58247-250">実行時に、展開されている最新のバージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="58247-250">At run time, the latest deployed version will be used.</span></span>  

-   <span data-ttu-id="58247-251">使用する必要が展開されている最新バージョン以外のポリシー バージョンを使用する場合は、**式**図形し、その特定のバージョンのポリシーを実行するには、プログラムによってルール エンジンを呼び出しています。</span><span class="sxs-lookup"><span data-stu-id="58247-251">If you plan to use a policy version other than the latest deployed version, you should use an **Expression** shape, and invoke the rule engine programmatically to execute the policy of that specific version.</span></span> <span data-ttu-id="58247-252">詳細については、次を参照してください。[ポリシーの実行方法](../core/how-to-execute-policies.md)します。</span><span class="sxs-lookup"><span data-stu-id="58247-252">For more information, see [How to Execute Policies](../core/how-to-execute-policies.md).</span></span>  

-   <span data-ttu-id="58247-253">**ルールの呼び出し**図形を使用したかのように、メッセージを再構築、**メッセージの構築**図形、失われたメッセージのコンテキスト プロパティがさらに可能性があります。</span><span class="sxs-lookup"><span data-stu-id="58247-253">The **Call Rules** shape reconstructs the message, as if using a **Construct Message** shape, which in turn may cause context properties of the message to be lost.</span></span>  

-   <span data-ttu-id="58247-254">公開されたポリシーは、変更できません。</span><span class="sxs-lookup"><span data-stu-id="58247-254">A policy cannot be modified after it is published.</span></span>  

-   <span data-ttu-id="58247-255">クライアント アプリケーションは、展開されているポリシーのみにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="58247-255">The client applications can access only the deployed policies.</span></span> <span data-ttu-id="58247-256">ルール エンジンを生成するクライアント アプリケーションに展開されていないポリシーが呼び出される場合、 **RuleEngineDeploymentNotDeployedException**例外。</span><span class="sxs-lookup"><span data-stu-id="58247-256">If a client application invokes a policy that is not deployed, the rule engine generates a **RuleEngineDeploymentNotDeployedException** exception.</span></span> <span data-ttu-id="58247-257">アプリケーション イベント ログで、詳細エラー メッセージを確認できます。</span><span class="sxs-lookup"><span data-stu-id="58247-257">You can see the detailed error message in the application event log.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="58247-258">次の手順</span><span class="sxs-lookup"><span data-stu-id="58247-258">Next Steps</span></span>  
 <span data-ttu-id="58247-259">これで、このチュートリアルを完了すると、実行、[チュートリアル: ポリシーでのボキャブラリの作成と](../core/walkthrough-creating-and-using-a-vocabulary-in-the-policy.md)ボキャブラリを作成すると、では、ボキャブラリを使用して詳細な手順を説明するチュートリアル、**ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="58247-259">Now that you have completed this walkthrough, perform the [Walkthrough: Creating and Using a Vocabulary in the Policy](../core/walkthrough-creating-and-using-a-vocabulary-in-the-policy.md) walkthrough, which gives you step-by-step instructions for creating a vocabulary and using the vocabulary in the **ProcessPurchaseOrder** policy.</span></span>  

## <a name="see-also"></a><span data-ttu-id="58247-260">参照</span><span class="sxs-lookup"><span data-stu-id="58247-260">See Also</span></span>  
 <span data-ttu-id="58247-261">[条件の評価とアクションの実行](../core/condition-evaluation-and-action-execution.md) </span><span class="sxs-lookup"><span data-stu-id="58247-261">[Condition Evaluation and Action Execution](../core/condition-evaluation-and-action-execution.md) </span></span>  
 <span data-ttu-id="58247-262">[議題と優先度](../core/agenda-and-priority.md) </span><span class="sxs-lookup"><span data-stu-id="58247-262">[Agenda and Priority](../core/agenda-and-priority.md) </span></span>  
 [<span data-ttu-id="58247-263">オーケストレーションでのビジネス ルールの呼び出し</span><span class="sxs-lookup"><span data-stu-id="58247-263">Invoking Business Rules in Orchestrations</span></span>](../core/invoking-business-rules-in-orchestrations.md)