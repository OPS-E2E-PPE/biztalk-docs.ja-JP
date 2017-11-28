---
title: "チュートリアル: がオーケストレーションからポリシーを呼び出す |Microsoft ドキュメント"
ms.custom: 
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cb2d2974-8a36-4d36-905c-799e4236ef99
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36de942d34a4235b689b464192a460451e7c921a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-invoking-the-policy-from-an-orchestration"></a><span data-ttu-id="5a65a-102">チュートリアル: オーケストレーションからのポリシーの呼び出し</span><span class="sxs-lookup"><span data-stu-id="5a65a-102">Walkthrough: Invoking the Policy from an Orchestration</span></span>
<span data-ttu-id="5a65a-103">ポリシーは、次のいずれかの方法でオーケストレーションから呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="5a65a-103">You can invoke a policy from an orchestration in one of the following ways:</span></span>  
  
-   <span data-ttu-id="5a65a-104">使用して、**ルールの呼び出し**図形</span><span class="sxs-lookup"><span data-stu-id="5a65a-104">By using the **Call Rules** shape</span></span>  
  
-   <span data-ttu-id="5a65a-105">使用して、**式**図形、およびプログラムでポリシーを実行するルール エンジンを呼び出して (**Policy.Execute**メソッド)</span><span class="sxs-lookup"><span data-stu-id="5a65a-105">By using the **Expression** shape, and programmatically invoking the rule engine to execute the policy (**Policy.Execute** method)</span></span>  
  
 <span data-ttu-id="5a65a-106">使用して、**ルールの呼び出し**図形は、最も一般的な方法もオーケストレーションからポリシーを呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-106">Using the **Call Rules** shape is the most common way and also the recommended way to invoke a policy from an orchestration.</span></span> <span data-ttu-id="5a65a-107">このチュートリアルでは、詳細な手順を使用して、**ルールの呼び出し**図形を呼び出す、 **ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="5a65a-107">This walkthrough provides step-by-step procedures for using the **Call Rules** shape to invoke the **ProcessPurchaseOrder** policy.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5a65a-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="5a65a-108">Prerequisites</span></span>  
 <span data-ttu-id="5a65a-109">完了する必要があります、[チュートリアル: ポリシーのテスト](../core/walkthrough-testing-the-policy.md)このチュートリアルを実行する前にチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="5a65a-109">You must complete the [Walkthrough: Testing the Policy](../core/walkthrough-testing-the-policy.md) walkthrough before performing this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="5a65a-110">このチュートリアルの概要</span><span class="sxs-lookup"><span data-stu-id="5a65a-110">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="5a65a-111">次の表に示すように、このチュートリアルには 7 つの手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5a65a-111">This walkthrough contains seven procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="5a65a-112">手順のタイトル</span><span class="sxs-lookup"><span data-stu-id="5a65a-112">Procedure title</span></span>|<span data-ttu-id="5a65a-113">手順の説明</span><span class="sxs-lookup"><span data-stu-id="5a65a-113">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="5a65a-114">スキーマとオーケストレーションを使用して BizTalk プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="5a65a-114">To create a BizTalk project with a schema and an orchestration</span></span>|<span data-ttu-id="5a65a-115">スキーマとを呼び出すオーケストレーションを作成するための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="5a65a-115">Provides step-by-step instructions for creating a schema and an orchestration that invokes the **ProcessPurchaseOrder** policy.</span></span>|  
|<span data-ttu-id="5a65a-116">メッセージ変数を作成するには</span><span class="sxs-lookup"><span data-stu-id="5a65a-116">To create message variables</span></span>|<span data-ttu-id="5a65a-117">ステップごとの説明に従って、オーケストレーションで使用されるメッセージ変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-117">Provides step-by-step instructions for creating message variables used in the orchestration.</span></span>|  
|<span data-ttu-id="5a65a-118">図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="5a65a-118">To configure shapes</span></span>|<span data-ttu-id="5a65a-119">ステップごとの説明に従って、オーケストレーションの図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-119">Provides step-by-step instructions for configuring shapes in the orchestration.</span></span>|  
|<span data-ttu-id="5a65a-120">ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="5a65a-120">To create ports</span></span>|<span data-ttu-id="5a65a-121">ステップごとの説明に従って、オーケストレーションのポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-121">Provides step-by-step instructions for creating ports in the orchestration.</span></span>|  
|<span data-ttu-id="5a65a-122">ポートを図形に接続するには</span><span class="sxs-lookup"><span data-stu-id="5a65a-122">To connect ports with the shapes</span></span>|<span data-ttu-id="5a65a-123">ステップごとの説明に従って、ポートを図形に接続します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-123">Provides step-by-step instructions for connecting ports with the shapes.</span></span>|  
|<span data-ttu-id="5a65a-124">ソリューションをビルドおよび配置するには</span><span class="sxs-lookup"><span data-stu-id="5a65a-124">To build and deploy the solution</span></span>|<span data-ttu-id="5a65a-125">ステップごとの説明に従って、ソリューションをビルドおよび展開します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-125">Provides step-by-step instructions for building and deploying the solution.</span></span>|  
|<span data-ttu-id="5a65a-126">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5a65a-126">To test the solution</span></span>|<span data-ttu-id="5a65a-127">ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-127">Provides step-by-step instructions for testing the solution.</span></span>|  
  
### <a name="to-create-a-biztalk-project-with-a-schema-and-an-orchestration"></a><span data-ttu-id="5a65a-128">スキーマとオーケストレーションを使用して BizTalk プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="5a65a-128">To create a BizTalk project with a schema and an orchestration</span></span>  
  
1.  <span data-ttu-id="5a65a-129">開始**Microsoft Visual Studio**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-129">Start **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="5a65a-130">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]の**ファイル**メニューのをポイント**新規**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-130">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="5a65a-131">**新しいプロジェクト** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-131">In the **New Project** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="5a65a-132">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5a65a-132">Use this</span></span>|<span data-ttu-id="5a65a-133">目的</span><span class="sxs-lookup"><span data-stu-id="5a65a-133">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="5a65a-134">**プロジェクトの種類**</span><span class="sxs-lookup"><span data-stu-id="5a65a-134">**Project types**</span></span>|<span data-ttu-id="5a65a-135">をクリックして**BizTalk プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-135">Click **BizTalk Projects**.</span></span>|  
    |<span data-ttu-id="5a65a-136">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="5a65a-136">**Templates**</span></span>|<span data-ttu-id="5a65a-137">をクリックして**空の BizTalk Server プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-137">Click **Empty BizTalk Server Project**.</span></span>|  
    |<span data-ttu-id="5a65a-138">**名前**</span><span class="sxs-lookup"><span data-stu-id="5a65a-138">**Name**</span></span>|<span data-ttu-id="5a65a-139">型**RuleTest**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-139">Type **RuleTest**.</span></span>|  
    |<span data-ttu-id="5a65a-140">**場所**</span><span class="sxs-lookup"><span data-stu-id="5a65a-140">**Location**</span></span>|<span data-ttu-id="5a65a-141">指定**C:\BRE-Walkthroughs**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-141">Specify **C:\BRE-Walkthroughs**.</span></span>|  
    |<span data-ttu-id="5a65a-142">**[ソリューション名]**</span><span class="sxs-lookup"><span data-stu-id="5a65a-142">**Solution Name**</span></span>|<span data-ttu-id="5a65a-143">型**RuleTestSol**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-143">Type **RuleTestSol**.</span></span>|  
    |<span data-ttu-id="5a65a-144">**ソリューションのディレクトリを作成します。**</span><span class="sxs-lookup"><span data-stu-id="5a65a-144">**Create directory for solution**</span></span>|<span data-ttu-id="5a65a-145">ソリューション ファイルのディレクトリを作成するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-145">Select this check box to create a directory for the solution files.</span></span>|  
  
4.  <span data-ttu-id="5a65a-146">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-146">Click **OK**.</span></span> <span data-ttu-id="5a65a-147">**RuleTest**プロジェクトがソリューション エクスプ ローラーで表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a65a-147">The **RuleTest** project should appear in Solution Explorer.</span></span> <span data-ttu-id="5a65a-148">ソリューション エクスプ ローラーが表示されない場合はクリックして**ソリューション エクスプ ローラー**上、**ビュー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="5a65a-148">If you do not see Solution Explorer, click **Solution Explorer** on the **View** menu.</span></span>  
  
5.  <span data-ttu-id="5a65a-149">ソリューション エクスプ ローラーで右クリック**RuleTest**、をポイント**追加**、クリックして**既存項目の**します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-149">In Solution Explorer, right-click **RuleTest**, point to **Add**, and then click **Existing Item**.</span></span>  
  
6.  <span data-ttu-id="5a65a-150">参照したり追加したり、 **PO.xsd**で作成したスキーマ ファイル、[チュートリアル: 単純なビジネス ポリシーを作成する](../core/walkthrough-creating-a-simple-business-policy.md)チュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="5a65a-150">Browse and add the **PO.xsd** schema file you created in the [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md) walkthrough.</span></span> <span data-ttu-id="5a65a-151">Visual Studio でのコピーを作成、 **PO.xsd**ファイルし、プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-151">Visual Studio makes a copy of the **PO.xsd** file and adds it to the project.</span></span>  
  
7.  <span data-ttu-id="5a65a-152">ソリューション エクスプ ローラーで右クリック**RuleTest**、をポイント**追加**、クリックして**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-152">In Solution Explorer, right-click **RuleTest**, point to **Add**, and then click **New Item**.</span></span>  
  
8.  <span data-ttu-id="5a65a-153">**新しい項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-153">In the **Add New Item** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="5a65a-154">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5a65a-154">Use this</span></span>|<span data-ttu-id="5a65a-155">目的</span><span class="sxs-lookup"><span data-stu-id="5a65a-155">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="5a65a-156">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="5a65a-156">**Categories**</span></span>|<span data-ttu-id="5a65a-157">をクリックして**オーケストレーション ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-157">Click **Orchestration Files**.</span></span>|  
    |<span data-ttu-id="5a65a-158">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="5a65a-158">**Templates**</span></span>|<span data-ttu-id="5a65a-159">をクリックして**BizTalk オーケストレーション**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-159">Click **BizTalk Orchestration**.</span></span>|  
    |<span data-ttu-id="5a65a-160">**名前**</span><span class="sxs-lookup"><span data-stu-id="5a65a-160">**Name**</span></span>|<span data-ttu-id="5a65a-161">型**RuleTest.odx**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-161">Type **RuleTest.odx**.</span></span>|  
  
9. <span data-ttu-id="5a65a-162">**[追加]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-162">Click **Add**.</span></span>  
  
10. <span data-ttu-id="5a65a-163">右クリック**ツールボックスからここに図形をドロップ**、をポイント**図形の挿入**、クリックして**受信**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-163">Right-click **Drop a shape from the toolbox here**, point to **Insert Shape**, and then click **Receive**.</span></span>  
  
11. <span data-ttu-id="5a65a-164">[プロパティ] ウィンドウでの名前を変更、**受信**図形を**ReceivePO**の値を設定し、 **Activate**プロパティを`true`です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-164">In the Properties window, change the name of the **Receive** shape to **ReceivePO**, and set the value of the **Activate** property to `true`.</span></span>  
  
12. <span data-ttu-id="5a65a-165">ツールボックスで、上、 **BizTalk オーケストレーション** タブで、ドラッグ、**ルールの呼び出し**下の区分線に図形、**受信**図形です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-165">In the Toolbox, on the **BizTalk Orchestrations** tab, drag the **Call Rules** shape onto a connecting line below the **Receive** shape.</span></span>  
  
13. <span data-ttu-id="5a65a-166">[プロパティ] ウィンドウでの名前変更、**ルールの呼び出し**図形を**CallProcessPOPolicy**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-166">In the Properties window, change the name of the **Call Rules** shape to **CallProcessPOPolicy**.</span></span>  
  
14. <span data-ttu-id="5a65a-167">下を右クリックし、**ルールの呼び出し**図形をポイントし、**図形の挿入**、順にクリック**送信**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-167">Right-click below the **Call Rules** shape, point to **Insert Shape**, and then click **Send**.</span></span>  
  
15. <span data-ttu-id="5a65a-168">[プロパティ] ウィンドウでの名前変更、**送信**図形を**SendPO**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-168">In the Properties window, change the name of the **Send** shape to **SendPO**.</span></span> <span data-ttu-id="5a65a-169">オーケストレーションは次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="5a65a-169">The orchestration should look like the following figure.</span></span>  
  
     <span data-ttu-id="5a65a-170">![BRE &#45;チュートリアル &#45;UnconfiguredOrch](../core/media/1f3502ac-82a9-40bf-ae31-6e8356a283e2.gif "1f3502ac-82a9-40bf-ae31-6e8356a283e2")</span><span class="sxs-lookup"><span data-stu-id="5a65a-170">![BRE&#45;Walkthrough&#45;UnconfiguredOrch](../core/media/1f3502ac-82a9-40bf-ae31-6e8356a283e2.gif "1f3502ac-82a9-40bf-ae31-6e8356a283e2")</span></span>  
  
### <a name="to-create-message-variables"></a><span data-ttu-id="5a65a-171">メッセージ変数を作成するには</span><span class="sxs-lookup"><span data-stu-id="5a65a-171">To create message variables</span></span>  
  
1.  <span data-ttu-id="5a65a-172">オーケストレーションの種類 ウィンドウで、右クリック**メッセージ**、クリックして**新しいメッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-172">In the Orchestration View window, right-click **Messages**, and then click **New Message**.</span></span> <span data-ttu-id="5a65a-173">オーケストレーションの種類 ウィンドウが表示されない場合にクリックして、**ビュー** メニューのをポイント**その他のウィンドウ**、順にクリック**オーケストレーションの種類**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-173">If you do not see the Orchestration View window, click the **View** menu, point to **Other Windows**, and then click **Orchestration View**.</span></span> <span data-ttu-id="5a65a-174">通常、[オーケストレーションの種類] ウィンドウは、[ソリューション エクスプローラー] タブの隣のタブにあります。既定では、新しいメッセージが名前付き**Message_1**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-174">Typically, the Orchestration View window is on the tab next to the Solution Explorer tab. By default, the new message is named **Message_1**.</span></span>  
  
     <span data-ttu-id="5a65a-175">![BRE &#45;チュートリアル &#45; OrchViewNewMsg](../core/media/a0b7fee3-af90-4c01-9464-146f0ca449e5.gif "a0b7fee3-af90-4c01-9464-146f0ca449e5")</span><span class="sxs-lookup"><span data-stu-id="5a65a-175">![BRE&#45;Walkthrough&#45;OrchViewNewMsg](../core/media/a0b7fee3-af90-4c01-9464-146f0ca449e5.gif "a0b7fee3-af90-4c01-9464-146f0ca449e5")</span></span>  
  
2.  <span data-ttu-id="5a65a-176">オーケストレーションの種類] ウィンドウで、[ **Message_1**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-176">In the Orchestration View window, click **Message_1**.</span></span>  
  
3.  <span data-ttu-id="5a65a-177">[プロパティ ウィンドウ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5a65a-177">In the Properties window, do the following:</span></span>  
  
    |<span data-ttu-id="5a65a-178">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5a65a-178">Use this</span></span>|<span data-ttu-id="5a65a-179">目的</span><span class="sxs-lookup"><span data-stu-id="5a65a-179">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="5a65a-180">**[Identifier]**</span><span class="sxs-lookup"><span data-stu-id="5a65a-180">**Identifier**</span></span>|<span data-ttu-id="5a65a-181">型**[poinst]**、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-181">Type **POInst**, and then press ENTER.</span></span>|  
    |<span data-ttu-id="5a65a-182">**メッセージの種類**</span><span class="sxs-lookup"><span data-stu-id="5a65a-182">**Message Type**</span></span>|<span data-ttu-id="5a65a-183">ドロップダウン リストから、展開**スキーマ**、し、 **RuleTest.PO**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-183">From the drop-down list, expand **Schemas**, and then select **RuleTest.PO**.</span></span>|  
  
     <span data-ttu-id="5a65a-184">![BRE &#45;チュートリアル &#45;MsgProps](../core/media/c82cfb67-63f6-4133-95bf-daadac0e213a.gif "c82cfb67-63f6-4133-95bf-daadac0e213a")</span><span class="sxs-lookup"><span data-stu-id="5a65a-184">![BRE&#45;Walkthrough&#45;MsgProps](../core/media/c82cfb67-63f6-4133-95bf-daadac0e213a.gif "c82cfb67-63f6-4133-95bf-daadac0e213a")</span></span>  
  
### <a name="to-configure-shapes"></a><span data-ttu-id="5a65a-185">図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="5a65a-185">To configure shapes</span></span>  
  
1.  <span data-ttu-id="5a65a-186">選択、**受信**オーケストレーション デザイナーでの図形です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-186">Select the **Receive** shape in Orchestration Designer.</span></span>  
  
2.  <span data-ttu-id="5a65a-187">[プロパティ] ウィンドウで選択**[poinst]**の**メッセージ**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="5a65a-187">In the Properties window, select **POInst** for the **Message** property.</span></span>  
  
3.  <span data-ttu-id="5a65a-188">ダブルクリックして、**ルールの呼び出し**オーケストレーション デザイナーでの図形です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-188">Double-click the **Call Rules** shape in Orchestration Designer.</span></span>  
  
4.  <span data-ttu-id="5a65a-189">**ルールの呼び出しのポリシー構成**ダイアログ ボックスで、 **ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="5a65a-189">In the **Call Rules policy configuration** dialog box, select **ProcessPurchaseOrder** for the policy.</span></span>  
  
5.  <span data-ttu-id="5a65a-190">[次へ] をクリックして **\*** 、下**パラメーター名**を選択し、 **[poinst]**ポリシーへのパラメーターとして。</span><span class="sxs-lookup"><span data-stu-id="5a65a-190">Click next to **\***, below **Parameter Name**, and select **POInst** as a parameter to the policy.</span></span>  
  
     <span data-ttu-id="5a65a-191">![BRE &#45;チュートリアル &#45;ConfigureCallRules](../core/media/0e7dab04-41db-433b-bbf5-b13901033b41.gif "0e7dab04-41db-433b-bbf5-b13901033b41")</span><span class="sxs-lookup"><span data-stu-id="5a65a-191">![BRE&#45;Walkthrough&#45;ConfigureCallRules](../core/media/0e7dab04-41db-433b-bbf5-b13901033b41.gif "0e7dab04-41db-433b-bbf5-b13901033b41")</span></span>  
  
6.  <span data-ttu-id="5a65a-192">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-192">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="5a65a-193">選択、**送信**オーケストレーションの図形です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-193">Select the **Send** shape in the orchestration.</span></span>  
  
8.  <span data-ttu-id="5a65a-194">[プロパティ] ウィンドウ内の値を設定、**メッセージの種類**プロパティを**[poinst]**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-194">In the Properties window, set the value of the **Message Type** property to **POInst**.</span></span>  
  
### <a name="to-create-ports"></a><span data-ttu-id="5a65a-195">ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="5a65a-195">To create ports</span></span>  
  
1.  <span data-ttu-id="5a65a-196">2 つのフォルダーを作成する**入力**と**出力**、C:\BRE-Walkthroughs\RuleTestSol フォルダー内です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-196">Create two folders, **Input** and **Output**, in the C:\BRE-Walkthroughs\RuleTestSol folder.</span></span>  
  
2.  <span data-ttu-id="5a65a-197">オーケストレーションの左のポート画面を右クリックし、をクリックして**新しい構成済みポート**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-197">Right-click the left port surface of the orchestration, and then click **New Configured Port**.</span></span>  
  
3.  <span data-ttu-id="5a65a-198">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-198">Click **Next**.</span></span> <span data-ttu-id="5a65a-199">型**ReceivePOPrt**ポートの名前をします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-199">Type **ReceivePOPrt** for the port name.</span></span>  
  
4.  <span data-ttu-id="5a65a-200">をクリックして**次**2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-200">Click **Next** twice.</span></span>  
  
5.  <span data-ttu-id="5a65a-201">選択**今指定**の**ポートのバインド**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-201">Select **Specify Now** for the **port binding**.</span></span>  
  
6.  <span data-ttu-id="5a65a-202">指定**ファイル**の**トランスポート**、として入力ディレクトリの名前を入力および**C:\BRE-Walkthroughs\RuleTestSol\Input\\\*.xml**ファイル マスクと共に (**\*.xml**) の URI。</span><span class="sxs-lookup"><span data-stu-id="5a65a-202">Specify **FILE** for the **transport**, and type the name of the input directory as **C:\BRE-Walkthroughs\RuleTestSol\Input\\\*.xml** along with the file mask (**\*.xml**) for the URI.</span></span>  
  
7.  <span data-ttu-id="5a65a-203">**[次へ]**をクリックし、 **[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-203">Click **Next**, and then click **Finish**.</span></span>  
  
8.  <span data-ttu-id="5a65a-204">オーケストレーションの右ポート画面を右クリックし、をクリックして**新しい構成ポート**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-204">Right-click the right port surface of the orchestration, and then click **New Configuration Port**.</span></span>  
  
9. <span data-ttu-id="5a65a-205">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-205">Click **Next**.</span></span> <span data-ttu-id="5a65a-206">型**SendPOPort**ポートの名前をします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-206">Type **SendPOPort** for the port name.</span></span>  
  
10. <span data-ttu-id="5a65a-207">をクリックして**次**2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-207">Click **Next** twice.</span></span>  
  
11. <span data-ttu-id="5a65a-208">変更、**ポートの通信方向**に**すればを常にメッセージを送信するこのポートで**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-208">Change the **Port direction of communication** to **I'll always be sending messages on this port**.</span></span>  
  
12. <span data-ttu-id="5a65a-209">選択**今指定**の**ポートのバインド**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-209">Select **Specify Now** for the **port binding**.</span></span>  
  
13. <span data-ttu-id="5a65a-210">指定**ファイル**の**トランスポート**、として出力ディレクトリの名前を入力して**C:\BRE-Walkthroughs\RuleTestSol\Output**、%messageid%.xml 出力ファイル名前です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-210">Specify **FILE** for the **transport**, and type the name of the output directory as **C:\BRE-Walkthroughs\RuleTestSol\Output**,and %MessageID%.xml as the output file name.</span></span>  
  
14. <span data-ttu-id="5a65a-211">**[次へ]**をクリックし、 **[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-211">Click **Next**, and then click **Finish**.</span></span>  
  
### <a name="to-connect-ports-with-the-shapes"></a><span data-ttu-id="5a65a-212">ポートを図形に接続するには</span><span class="sxs-lookup"><span data-stu-id="5a65a-212">To connect ports with the shapes</span></span>  
  
1.  <span data-ttu-id="5a65a-213">接続、 **ReceivePOPrt**ポートを**ReceivePO**図形です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-213">Connect the **ReceivePOPrt** port to the **ReceivePO** shape.</span></span> <span data-ttu-id="5a65a-214">ポート画面の [ReceivePOPrt] ポートの右側の矢印を [ReceivePO] 図形のボックスにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-214">(Drag the arrow to the right of ReceivePOPrt port on the port surface to the box on the ReceivePO shape.)</span></span>  
  
     <span data-ttu-id="5a65a-215">![BRE &#45;チュートリアル &#45;ConnectRP](../core/media/75bdf79e-ca98-43bb-8ff6-5f46005a6490.gif "75bdf79e-ca98-43bb-8ff6-5f46005a6490")</span><span class="sxs-lookup"><span data-stu-id="5a65a-215">![BRE&#45;Walkthrough&#45;ConnectRP](../core/media/75bdf79e-ca98-43bb-8ff6-5f46005a6490.gif "75bdf79e-ca98-43bb-8ff6-5f46005a6490")</span></span>  
  
2.  <span data-ttu-id="5a65a-216">接続、 **SendPO**図形を**[sendpoprt]**ポートです。</span><span class="sxs-lookup"><span data-stu-id="5a65a-216">Connect the **SendPO** shape to the **SendPOPrt** port.</span></span>  
  
     <span data-ttu-id="5a65a-217">![BRE &#45;チュートリアル &#45;ConnectSP](../core/media/7513f52b-2782-4357-b8eb-1874dec33869.gif "7513f52b-2782-4357-b8eb-1874dec33869")</span><span class="sxs-lookup"><span data-stu-id="5a65a-217">![BRE&#45;Walkthrough&#45;ConnectSP](../core/media/7513f52b-2782-4357-b8eb-1874dec33869.gif "7513f52b-2782-4357-b8eb-1874dec33869")</span></span>  
  
### <a name="to-build-and-deploy-the-solution"></a><span data-ttu-id="5a65a-218">ソリューションをビルドおよび配置するには</span><span class="sxs-lookup"><span data-stu-id="5a65a-218">To build and deploy the solution</span></span>  
  
1.  <span data-ttu-id="5a65a-219">開始**Microsoft Visual Studio**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-219">Start **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="5a65a-220">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで右クリックし、 **RuleTest**プロジェクトをクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-220">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], in Solution Explorer, right-click the **RuleTest** project, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="5a65a-221">プロジェクト デザイナー (中央のペイン) で、をクリックして**署名**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-221">In Project Designer (in the center pane), click **Signing**.</span></span>  
  
4.  <span data-ttu-id="5a65a-222">[署名] タブで、確認**アセンブリに署名**チェック ボックスをオンにします。ドロップダウン リストで**厳密な名前キー ファイルを選択して**をクリックして**新規**;**キー ファイル名**フィールドに、ルールのテストの入力**パスワード**(省略可能) をフィールド、パスワードを設定し、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-222">In Signing tab, Check **Sign the assembly** checkbox; In the dropdown list **Choose a strong name key file**, click **New**; In the **Key File name** field, enter Rule Test; In the **Password** field (Optional),  set Password, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="5a65a-223">プロジェクト デザイナーで、をクリックして**展開**展開 タブに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="5a65a-223">In Project Designer, click **Deployment** to switch to the Deployment tab.</span></span>  
  
6.  <span data-ttu-id="5a65a-224">指定**RuleTestApp**アプリケーション名として。</span><span class="sxs-lookup"><span data-stu-id="5a65a-224">Specify **RuleTestApp** as the application name.</span></span>  
  
     <span data-ttu-id="5a65a-225">![BRE &#45;チュートリアル &#45;[Ruletestapp]](../core/media/b153e5b0-ca46-4d27-bfa1-9ad4e58e9787.gif "b153e5b0-ca46-4d27-bfa1-9ad4e58e9787")</span><span class="sxs-lookup"><span data-stu-id="5a65a-225">![BRE&#45;Walkthrough&#45;RuleTestApp](../core/media/b153e5b0-ca46-4d27-bfa1-9ad4e58e9787.gif "b153e5b0-ca46-4d27-bfa1-9ad4e58e9787")</span></span>  
  
7.  <span data-ttu-id="5a65a-226">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-226">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="5a65a-227">右クリックし、 **RuleTest**プロジェクトをクリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-227">Right-click the **RuleTest** project, and then click **Build**.</span></span>  
  
9. <span data-ttu-id="5a65a-228">右クリックし、 **RuleTest**プロジェクトをクリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-228">Right-click the **RuleTest** project, and then click **Deploy**.</span></span>  
  
### <a name="to-test-the-solution"></a><span data-ttu-id="5a65a-229">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5a65a-229">To test the solution</span></span>  
  
1.  <span data-ttu-id="5a65a-230">ビジネス ルール作成ツールで展開**ポリシー**、展開**ProcessPurchaseOrder**を右クリックして**バージョン 1.0**、クリックして**発行**.</span><span class="sxs-lookup"><span data-stu-id="5a65a-230">In Business Rule Composer, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.0**, and then click **Publish**.</span></span>  
  
2.  <span data-ttu-id="5a65a-231">右クリック**バージョン 1.0 - 公開済み**、クリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-231">Right-click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  
  
3.  <span data-ttu-id="5a65a-232">**開始**] メニューの [開いている**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-232">In the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="5a65a-233">BizTalk Server 管理コンソールを既に開いている場合は、F5 キーを押して更新します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-233">If you have the BizTalk Server Administration console already open, press F5 to refresh it.</span></span>  
  
4.  <span data-ttu-id="5a65a-234">展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、順に展開**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-234">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
5.  <span data-ttu-id="5a65a-235">右クリック**RuleTestApp**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-235">Right-click **RuleTestApp**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="5a65a-236">をクリックして**Orchestration_1**、し、指定**BizTalkServerApplication**としてホストします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-236">Click **Orchestration_1**, and specify **BizTalkServerApplication** as the host.</span></span>  
  
     <span data-ttu-id="5a65a-237">![BRE &#45;チュートリアル &#45;AppHost](../core/media/ba348a98-661f-4e71-8b9b-b8c5fadf035a.gif "ba348a98-661f-4e71-8b9b-b8c5fadf035a")</span><span class="sxs-lookup"><span data-stu-id="5a65a-237">![BRE&#45;Walkthrough&#45;AppHost](../core/media/ba348a98-661f-4e71-8b9b-b8c5fadf035a.gif "ba348a98-661f-4e71-8b9b-b8c5fadf035a")</span></span>  
  
7.  <span data-ttu-id="5a65a-238">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a65a-238">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="5a65a-239">右クリック**RuleTestApp**、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-239">Right-click **RuleTestApp**, and then click **Start**.</span></span>  
  
9. <span data-ttu-id="5a65a-240">**'RuleTestApp' アプリケーションの起動**ダイアログ ボックスで、をクリックして**開始**アプリケーションが正常に開始されるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-240">In the **Start 'RuleTestApp' Application** dialog box, click **Start**, and then wait until the application is started successfully.</span></span>  
  
10. <span data-ttu-id="5a65a-241">開いている**SamplePO.xml**と**SamplePO2.xml**メモ帳での値を変更し、**ステータス**フィールドを**XYZ**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-241">Open **SamplePO.xml** and **SamplePO2.xml** in Notepad and change the value of the **Status** field to **XYZ**.</span></span>  
  
11. <span data-ttu-id="5a65a-242">コピー、 **SamplePO.xml**オーケストレーション用の C:\BRE-Walkthroughs\RuleTestSol\Input ディレクトリに C:\BRE-Walkthroughs ディレクトリからファイルです。</span><span class="sxs-lookup"><span data-stu-id="5a65a-242">Copy the **SamplePO.xml** file from the C:\BRE-Walkthroughs directory to the C:\BRE-Walkthroughs\RuleTestSol\Input directory for the orchestration.</span></span>  
  
12. <span data-ttu-id="5a65a-243">オーケストレーションの C:\BRE-Walkthroughs\RuleTestSol\Output ディレクトリに出力ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a65a-243">You should see an output file in the C:\BRE-Walkthroughs\RuleTestSol\Output directory for the orchestration.</span></span> <span data-ttu-id="5a65a-244">出力 XML ファイルを開くことを確認の値、**ステータス**にフィールドが設定されている**Approved**です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-244">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
13. <span data-ttu-id="5a65a-245">手順 11 ~ 12. を繰り返して**SamplePO2.xml**、ことを確認の値、**ステータス**出力ドキュメント内のフィールドは、入力ドキュメントと同じ (**xyz**)。</span><span class="sxs-lookup"><span data-stu-id="5a65a-245">Repeat steps 11 and 12 with **SamplePO2.xml**, and notice that the value of the **Status** field in the output document is the same as in the input document (**xyz**).</span></span>  
  
## <a name="comments"></a><span data-ttu-id="5a65a-246">コメント</span><span class="sxs-lookup"><span data-stu-id="5a65a-246">Comments</span></span>  
  
-   <span data-ttu-id="5a65a-247">このチュートリアルでは、オーケストレーションに図形を追加する際に、ツールボックスの図形は使用しませんでした。</span><span class="sxs-lookup"><span data-stu-id="5a65a-247">In this walkthrough, to add the shapes to the orchestration, you did not use the shapes from the Toolbox.</span></span> <span data-ttu-id="5a65a-248">代わりに、マウスの右ボタンをクリックして挿入する図形を選択しました。</span><span class="sxs-lookup"><span data-stu-id="5a65a-248">Instead, you clicked the right mouse button and selected the shape that you wanted to insert.</span></span>  
  
-   <span data-ttu-id="5a65a-249">構成、**ルールの呼び出し**図形は、使用される型を決定する際に保存されている最新バージョンは検索します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-249">The configuration for the **Call Rules** shape looks at the latest saved version when determining the types used.</span></span> <span data-ttu-id="5a65a-250">実行時に、展開されている最新のバージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="5a65a-250">At run time, the latest deployed version will be used.</span></span>  
  
-   <span data-ttu-id="5a65a-251">展開されている最新バージョン以外のポリシーのバージョンを使用する場合は、する必要がありますを使用する、**式**図形、およびその特定のバージョンのポリシーを実行するには、プログラムによってルール エンジンを起動します。</span><span class="sxs-lookup"><span data-stu-id="5a65a-251">If you plan to use a policy version other than the latest deployed version, you should use an **Expression** shape, and invoke the rule engine programmatically to execute the policy of that specific version.</span></span> <span data-ttu-id="5a65a-252">詳細については、次を参照してください。[ポリシーの実行方法](../core/how-to-execute-policies.md)です。</span><span class="sxs-lookup"><span data-stu-id="5a65a-252">For more information, see [How to Execute Policies](../core/how-to-execute-policies.md).</span></span>  
  
-   <span data-ttu-id="5a65a-253">**ルールの呼び出し**図形を使用するかのように、メッセージを再構築、**メッセージの構築**図形、さらに、失われるメッセージのコンテキスト プロパティを引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5a65a-253">The **Call Rules** shape reconstructs the message, as if using a **Construct Message** shape, which in turn may cause context properties of the message to be lost.</span></span>  
  
-   <span data-ttu-id="5a65a-254">公開されたポリシーは、変更できません。</span><span class="sxs-lookup"><span data-stu-id="5a65a-254">A policy cannot be modified after it is published.</span></span>  
  
-   <span data-ttu-id="5a65a-255">クライアント アプリケーションは、展開されたポリシーのみにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5a65a-255">The client applications can access only the deployed policies.</span></span> <span data-ttu-id="5a65a-256">ルール エンジンを生成するクライアント アプリケーションが展開されていないポリシーを呼び出す場合、 **RuleEngineDeploymentNotDeployedException**例外。</span><span class="sxs-lookup"><span data-stu-id="5a65a-256">If a client application invokes a policy that is not deployed, the rule engine generates a **RuleEngineDeploymentNotDeployedException** exception.</span></span> <span data-ttu-id="5a65a-257">アプリケーション イベント ログで、詳細エラー メッセージを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5a65a-257">You can see the detailed error message in the application event log.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5a65a-258">次の手順</span><span class="sxs-lookup"><span data-stu-id="5a65a-258">Next Steps</span></span>  
 <span data-ttu-id="5a65a-259">これで、このチュートリアルを完了すると、実行、[チュートリアル: ポリシーで作成およびボキャブラリ](../core/walkthrough-creating-and-using-a-vocabulary-in-the-policy.md)およびでボキャブラリを使用するボキャブラリを作成するための手順を説明するチュートリアルについては、**ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="5a65a-259">Now that you have completed this walkthrough, perform the [Walkthrough: Creating and Using a Vocabulary in the Policy](../core/walkthrough-creating-and-using-a-vocabulary-in-the-policy.md) walkthrough, which gives you step-by-step instructions for creating a vocabulary and using the vocabulary in the **ProcessPurchaseOrder** policy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a65a-260">参照</span><span class="sxs-lookup"><span data-stu-id="5a65a-260">See Also</span></span>  
 <span data-ttu-id="5a65a-261">[条件の評価とアクションの実行](../core/condition-evaluation-and-action-execution.md) </span><span class="sxs-lookup"><span data-stu-id="5a65a-261">[Condition Evaluation and Action Execution](../core/condition-evaluation-and-action-execution.md) </span></span>  
 <span data-ttu-id="5a65a-262">[議題と優先度](../core/agenda-and-priority.md) </span><span class="sxs-lookup"><span data-stu-id="5a65a-262">[Agenda and Priority](../core/agenda-and-priority.md) </span></span>  
 [<span data-ttu-id="5a65a-263">オーケストレーションでビジネス ルールの呼び出し</span><span class="sxs-lookup"><span data-stu-id="5a65a-263">Invoking Business Rules in Orchestrations</span></span>](../core/invoking-business-rules-in-orchestrations.md)