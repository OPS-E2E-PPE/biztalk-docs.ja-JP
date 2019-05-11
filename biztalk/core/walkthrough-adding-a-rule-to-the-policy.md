---
title: 'チュートリアル: ポリシーにルールを追加する |Microsoft Docs'
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b2a682c0-a5d7-4550-924d-be9fa29b84d2
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b5a19b02429f946a282ed5609beb3155310c8fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65320780"
---
# <a name="walkthrough-adding-a-rule-to-the-policy"></a><span data-ttu-id="dae45-102">チュートリアル: ポリシーにルールを追加します。</span><span class="sxs-lookup"><span data-stu-id="dae45-102">Walkthrough: Adding a Rule to the Policy</span></span>
<span data-ttu-id="dae45-103">このチュートリアルがという名前の規則を追加するための手順を示します**DeniedRule**を**ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="dae45-103">This walkthrough provides step-by-step procedures for adding a rule named **DeniedRule** to the **ProcessPurchaseOrder** policy.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dae45-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="dae45-104">Prerequisites</span></span>  
 <span data-ttu-id="dae45-105">完了する必要があります、[チュートリアル。作成して、ボキャブラリを使用して、ポリシーで](../core/walkthrough-creating-and-using-a-vocabulary-in-the-policy.md)このチュートリアルを実行する前にチュートリアル。</span><span class="sxs-lookup"><span data-stu-id="dae45-105">You must complete the [Walkthrough: Creating and Using a Vocabulary in the Policy](../core/walkthrough-creating-and-using-a-vocabulary-in-the-policy.md) walkthrough before performing this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="dae45-106">このチュートリアルの概要</span><span class="sxs-lookup"><span data-stu-id="dae45-106">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="dae45-107">このチュートリアルには、次の表に示すように 3 つの手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dae45-107">This walkthrough contains three procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="dae45-108">プロシージャ タイトル</span><span class="sxs-lookup"><span data-stu-id="dae45-108">Procedure title</span></span>|<span data-ttu-id="dae45-109">手順の説明</span><span class="sxs-lookup"><span data-stu-id="dae45-109">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="dae45-110">ProcessPurchaseOrder ポリシーに DeniedRule を追加するには</span><span class="sxs-lookup"><span data-stu-id="dae45-110">To add DeniedRule to the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="dae45-111">という名前の新しい規則を追加するための手順について説明します**DeniedRule**を**ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="dae45-111">Provides step-by-step instructions for adding a new rule named **DeniedRule** to the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="dae45-112">**DeniedRule**規則セットの値、**状態**フィールドを**Denied**場合の値、**数量**が 500 より大きい。</span><span class="sxs-lookup"><span data-stu-id="dae45-112">The **DeniedRule** rule sets the value of the **Status** field to **Denied** if the value of the **Quantity** is greater than 500.</span></span>|  
|<span data-ttu-id="dae45-113">ビジネス ルール作成ツールを使用してテストするには</span><span class="sxs-lookup"><span data-stu-id="dae45-113">To test with Business Rule Composer</span></span>|<span data-ttu-id="dae45-114">テストするための手順について説明します、 **ProcessPurchaseOrder**ビジネス ルール作成ツールを使用してポリシー。</span><span class="sxs-lookup"><span data-stu-id="dae45-114">Provides step-by-step instructions for testing the **ProcessPurchaseOrder** policy by using Business Rule Composer.</span></span>|  
|<span data-ttu-id="dae45-115">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dae45-115">To test the solution</span></span>|<span data-ttu-id="dae45-116">ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="dae45-116">Provides step-by-step instructions for testing the solution.</span></span>|  
  
### <a name="to-add-deniedrule-to-the-processpurchaseorder-policy"></a><span data-ttu-id="dae45-117">ProcessPurchaseOrder ポリシーに DeniedRule を追加するには</span><span class="sxs-lookup"><span data-stu-id="dae45-117">To add DeniedRule to the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="dae45-118">**開始**] メニューの [open**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="dae45-118">On the **Start** menu, open **Business Rule Composer**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dae45-119">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="dae45-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="dae45-120">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="dae45-120">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="dae45-121">ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、展開**ProcessPurchaseOrder**、右クリック**バージョン 1.1**、順にクリックします**コピー**.</span><span class="sxs-lookup"><span data-stu-id="dae45-121">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.1**, and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="dae45-122">右クリック**ProcessPurchaseOrder**、 をクリックし、**ポリシーのバージョンの貼り付け**します。</span><span class="sxs-lookup"><span data-stu-id="dae45-122">Right-click **ProcessPurchaseOrder**, and then click **Paste Policy Version**.</span></span>  
  
4.  <span data-ttu-id="dae45-123">右クリック**Version 1.2 (未保存)**、 をクリックして**新しいルールの追加**、規則の名前を変更し、 **DeniedRule**します。</span><span class="sxs-lookup"><span data-stu-id="dae45-123">Right-click **Version 1.2(not saved)**, click **Add New Rule**, and then change the name of the rule to **DeniedRule**.</span></span>  
  
5.  <span data-ttu-id="dae45-124">規則の名前を変更し忘れたかどうか**DeniedRule**手順 4 で、次のようにクリックします。 **Rule1**、名を変更して、 **DeniedRule**プロパティ ウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="dae45-124">If you forgot to change the name of the rule to **DeniedRule** in step 4, click **Rule1**, and change the name to **DeniedRule** in the Properties window.</span></span>  
  
6.  <span data-ttu-id="dae45-125">IF ペインで右クリック**条件**、 をポイント**述語**、 をクリックし、**より大きい**します。</span><span class="sxs-lookup"><span data-stu-id="dae45-125">In the IF pane, right-click **Conditions**, point to **Predicates**, and then click **Greater Than**.</span></span>  
  
7.  <span data-ttu-id="dae45-126">[ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**タブ。</span><span class="sxs-lookup"><span data-stu-id="dae45-126">In the Facts Explorer window, click the **Vocabularies** tab.</span></span>  
  
8.  <span data-ttu-id="dae45-127">展開**ボキャブラリ**、展開**POVocabulary**、展開**バージョン 1.0 - 公開済み**、し、ドラッグ**要求された数量**に**引数 1** IF ペインでします。</span><span class="sxs-lookup"><span data-stu-id="dae45-127">Expand **Vocabularies**, expand **POVocabulary**, expand **Version 1.0 - Published**, and then drag **Request Quantity** to **argument1** in the IF pane.</span></span>  
  
9. <span data-ttu-id="dae45-128">ドラッグ**許可される項目の最大数**に**引数 2** IF ペインでします。</span><span class="sxs-lookup"><span data-stu-id="dae45-128">Drag **Maximum number of items allowed** to **argument2** in the IF pane.</span></span>  
  
10. <span data-ttu-id="dae45-129">ドラッグ**要求の状態**[THEN] ペインにします。</span><span class="sxs-lookup"><span data-stu-id="dae45-129">Drag **Request Status** to the THEN pane.</span></span>  
  
11. <span data-ttu-id="dae45-130">をクリックして**\<空の文字列\>** し、入力**Denied**します。</span><span class="sxs-lookup"><span data-stu-id="dae45-130">Click **\<empty string\>** and then type **Denied**.</span></span>  
  
12. <span data-ttu-id="dae45-131">右クリック**Version 1.2 (未保存)**、 をクリックし、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="dae45-131">Right-click **Version 1.2 (not saved)**, and then click **Save**.</span></span>  
  
13. <span data-ttu-id="dae45-132">右クリックして**バージョン 1.2**、 をクリックし、**発行**します。</span><span class="sxs-lookup"><span data-stu-id="dae45-132">Right-click **Version 1.2**, and then click **Publish**.</span></span>  
  
14. <span data-ttu-id="dae45-133">右クリック**バージョン 1.2**、 をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="dae45-133">Right-click **Version 1.2**, and then click **Deploy**.</span></span>  
  
### <a name="to-test-with-business-rule-composer"></a><span data-ttu-id="dae45-134">ビジネス ルール作成ツールを使用してテストするには</span><span class="sxs-lookup"><span data-stu-id="dae45-134">To test with Business Rule Composer</span></span>  
  
1.  <span data-ttu-id="dae45-135">メモ帳で SamplePO.xml と SamplePO2.xml ファイルを開きの値を変更、**状態**フィールドを**XYZ**します。</span><span class="sxs-lookup"><span data-stu-id="dae45-135">Open the SamplePO.xml and SamplePO2.xml files in Notepad and change the value of the **Status** field to **XYZ**.</span></span>  
  
2.  <span data-ttu-id="dae45-136">ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、展開**ProcessPurchaseOrder**を右クリックして**バージョン 1.2**、 をクリックし、 **ポリシーのテスト**.</span><span class="sxs-lookup"><span data-stu-id="dae45-136">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.2**, and then click **Test Policy**.</span></span>  
  
3.  <span data-ttu-id="dae45-137">下、 **XMLDocuments**ノードの  **RuleTest.PO**、順にクリックします**インスタンスの追加**します。</span><span class="sxs-lookup"><span data-stu-id="dae45-137">Under the **XMLDocuments** node, select **RuleTest.PO**, and then click **Add Instance**.</span></span>  
  
4.  <span data-ttu-id="dae45-138">選択**SamplePO.xml**、 をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="dae45-138">Select **SamplePO.xml**, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="dae45-139">クリックして**テスト**します。</span><span class="sxs-lookup"><span data-stu-id="dae45-139">Click **Test**.</span></span>  
  
6.  <span data-ttu-id="dae45-140">見て、**議題の更新**出力では、セクションだけを注意してください。 **ApprovalRule** 、議題に追加されます。</span><span class="sxs-lookup"><span data-stu-id="dae45-140">Look at the **Agenda Update** section in the output, and notice that only **ApprovalRule** is added to the agenda.</span></span> <span data-ttu-id="dae45-141">そのため起動されるルールだけが (、規則に関連付けられたアクションが実行されます)。</span><span class="sxs-lookup"><span data-stu-id="dae45-141">Therefore it is the only rule that fires (actions associated with the rule are executed).</span></span>  
  
7.  <span data-ttu-id="dae45-142">開いている**SamplePO.xml**でメモ帳に注目してくださいの値、**状態**にフィールドが設定されている**Approved**します。</span><span class="sxs-lookup"><span data-stu-id="dae45-142">Open **SamplePO.xml** in Notepad and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
8.  <span data-ttu-id="dae45-143">ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、展開**ProcessPurchaseOrder**を右クリックして**バージョン 1.2**、 をクリックし、**ポリシーのテスト。**</span><span class="sxs-lookup"><span data-stu-id="dae45-143">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.2**, and then click **Test Policy.**</span></span>  
  
9. <span data-ttu-id="dae45-144">選択**SamplePO.xml**、 をクリックして**インスタンスの削除**、 をクリックし、**インスタンスの追加**します。</span><span class="sxs-lookup"><span data-stu-id="dae45-144">Select **SamplePO.xml**, click **Remove instance**, and then click **Add Instance**.</span></span>  
  
10. <span data-ttu-id="dae45-145">選択**SamplePO2.xml**、 をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="dae45-145">Select **SamplePO2.xml**, and then click **Open**.</span></span>  
  
11. <span data-ttu-id="dae45-146">クリックして**テスト**します。</span><span class="sxs-lookup"><span data-stu-id="dae45-146">Click **Test**.</span></span>  
  
12. <span data-ttu-id="dae45-147">見て、**議題の更新**出力では、セクションだけを注意してください。 **DeniedRule** 、議題に追加されます。</span><span class="sxs-lookup"><span data-stu-id="dae45-147">Look at the **Agenda Update** section in the output, and notice that only **DeniedRule** is added to the agenda.</span></span> <span data-ttu-id="dae45-148">そのため、この起動のみルールが。</span><span class="sxs-lookup"><span data-stu-id="dae45-148">Therefore it is the only rule that fires.</span></span>  
  
13. <span data-ttu-id="dae45-149">開いている**SamplePO2.xml**でメモ帳に注目してくださいの値、**状態**フィールドは**Denied**。</span><span class="sxs-lookup"><span data-stu-id="dae45-149">Open **SamplePO2.xml** in Notepad and notice that the value of the **Status** field is **Denied**.</span></span>  
  
### <a name="to-test-the-solution"></a><span data-ttu-id="dae45-150">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dae45-150">To test the solution</span></span>  
  
1.  <span data-ttu-id="dae45-151">開いている**SamplePO.xml**と**SamplePO2.xml**メモ帳での値を変更し、**状態**フィールドを**XYZ**します。</span><span class="sxs-lookup"><span data-stu-id="dae45-151">Open **SamplePO.xml** and **SamplePO2.xml** in Notepad and change the value of the **Status** field to **XYZ**.</span></span>  
  
2.  <span data-ttu-id="dae45-152">コピー、 **SamplePO.xml**オーケストレーション用の C:\BRE-Walkthroughs\RuleTestSol\Input ディレクトリに C:\BRE-Walkthroughs ディレクトリからファイル。</span><span class="sxs-lookup"><span data-stu-id="dae45-152">Copy the **SamplePO.xml** file from the C:\BRE-Walkthroughs directory to the C:\BRE-Walkthroughs\RuleTestSol\Input directory for the orchestration.</span></span>  
  
3.  <span data-ttu-id="dae45-153">オーケストレーションの C:\BRE-Walkthroughs\RuleTestSol\Output ディレクトリに出力ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dae45-153">You should see an output file in the C:\BRE-Walkthroughs\RuleTestSol\Output directory for the orchestration.</span></span> <span data-ttu-id="dae45-154">出力 XML ファイルを開き、注意の値、**状態**にフィールドが設定されている**Approved**します。</span><span class="sxs-lookup"><span data-stu-id="dae45-154">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
4.  <span data-ttu-id="dae45-155">手順 2 と 3 を繰り返します**SamplePO2.xml**、ことに注意しての値、**状態**にフィールドが設定されている**Denied**出力ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="dae45-155">Repeat steps 2 and 3 with **SamplePO2.xml**, and notice that the value of the **Status** field is set to **Denied** in the output document.</span></span> <span data-ttu-id="dae45-156">オーケストレーションでのバージョン 1.2 を使用していることが証明されます、 **ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="dae45-156">This proves that the orchestration is using version 1.2 of the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="dae45-157">オーケストレーションの展開された最新のバージョンを使用して、 **ProcessPurchaseOrder**ポリシーが**1.2**します。</span><span class="sxs-lookup"><span data-stu-id="dae45-157">The orchestration uses the latest deployed version of the **ProcessPurchaseOrder** policy, which is **1.2**.</span></span> <span data-ttu-id="dae45-158">ポリシーのバージョン 1.2 を使用するポリシーのバージョン 1.1 の展開を解除する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dae45-158">You do not need to undeploy version 1.1 of the policy to use version 1.2 of the policy.</span></span> <span data-ttu-id="dae45-159">ただし、ソリューションをテストする前に約 60 秒間待機する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dae45-159">However, you need to wait for approximately 60 seconds before testing the solution.</span></span> <span data-ttu-id="dae45-160">詳細については、コメント セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dae45-160">For more information, see the Comments section.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="dae45-161">コメント</span><span class="sxs-lookup"><span data-stu-id="dae45-161">Comments</span></span>  
  
-   <span data-ttu-id="dae45-162">ポリシーは、1 つまたは複数のルールを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="dae45-162">A policy can have one or more rules.</span></span> <span data-ttu-id="dae45-163">ポリシーの規則の数の論理の制限はありません。</span><span class="sxs-lookup"><span data-stu-id="dae45-163">There is no logical limit on the number of rules in a policy.</span></span>  
  
-   <span data-ttu-id="dae45-164">ルール エンジンは、条件の評価、競合解決 - アクションの実行アルゴリズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="dae45-164">The rule engine uses a Condition Evaluation - Conflict Resolution - Action Execution algorithm.</span></span> <span data-ttu-id="dae45-165">**条件の評価**ステージでは、ルール エンジンは、すべてのルールの条件を評価します。</span><span class="sxs-lookup"><span data-stu-id="dae45-165">In the **Condition Evaluation** stage, the rule engine evaluates conditions in all the rules.</span></span> <span data-ttu-id="dae45-166">条件が true に評価ルールでは、実行のルールの候補になります。</span><span class="sxs-lookup"><span data-stu-id="dae45-166">The rules whose conditions evaluate to true become candidate rules for execution.</span></span> <span data-ttu-id="dae45-167">**競合の解決**ステージで、候補ルールがルールの優先順位に従って議題に追加されます。</span><span class="sxs-lookup"><span data-stu-id="dae45-167">In the **Conflict Resolution** stage, the candidate rules are added to the agenda in the order of the priority of the rule.</span></span> <span data-ttu-id="dae45-168">**アクションの実行**ステージで、候補ルールが実行されるアクション。</span><span class="sxs-lookup"><span data-stu-id="dae45-168">In the **Action Execution** stage, the actions in the candidate rules are executed.</span></span> <span data-ttu-id="dae45-169">候補ルールの優先順位が同じ場合は、決定的な順序がこれらのルールのアクションが実行されることはありません。</span><span class="sxs-lookup"><span data-stu-id="dae45-169">If candidate rules have the same priority, there is no deterministic order in which the actions for those rules are executed.</span></span> <span data-ttu-id="dae45-170">それらが並列で実行されることを想定してください。</span><span class="sxs-lookup"><span data-stu-id="dae45-170">You should assume that they are executed in parallel.</span></span>  
  
-   <span data-ttu-id="dae45-171">この場合は、任意の指定されたサンプル ファイルで、規則のいずれかのみが発生します。</span><span class="sxs-lookup"><span data-stu-id="dae45-171">In this scenario, for any given sample file, only one of the rules is fired.</span></span> <span data-ttu-id="dae45-172">値を変更することを確認、**状態**フィールド テストを実行する前にします。</span><span class="sxs-lookup"><span data-stu-id="dae45-172">Make sure that you change the value of the **Status** field before running a test.</span></span>  
  
-   <span data-ttu-id="dae45-173">新しいバージョンのポリシーを展開するときは、テストする前に約 60 秒間を待機する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dae45-173">When a new version of the policy is deployed, you should wait approximately 60 seconds before testing.</span></span> <span data-ttu-id="dae45-174">ルール エンジン更新サービスは、新しく展開されたポリシーを探すように定期的に (既定では 60 秒ごと) ルール エンジン データベースをポーリングします。</span><span class="sxs-lookup"><span data-stu-id="dae45-174">The rule engine update service polls the rule engine database on a periodic basis (every 60 seconds by default) to look for newly deployed policies.</span></span> <span data-ttu-id="dae45-175">ルール エンジン更新サービスは、ルール エンジン データベースからのポリシーの展開された最新のバージョンに関する情報をメモリ内のポリシー オブジェクトを更新します。</span><span class="sxs-lookup"><span data-stu-id="dae45-175">The rule engine update service updates the policy object in memory with the information about the latest deployed version of the policy from the rule engine database.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="dae45-176">次の手順</span><span class="sxs-lookup"><span data-stu-id="dae45-176">Next Steps</span></span>  
 <span data-ttu-id="dae45-177">これで、このチュートリアルを完了すると、実行、[チュートリアル。ポリシーを変更する](../core/walkthrough-modifying-the-policy.md)の値を持つ注文書を承認する、ポリシーを変更するための手順を説明するチュートリアル**数量**(500) ではなく 1000 未満。</span><span class="sxs-lookup"><span data-stu-id="dae45-177">Now that you have completed this walkthrough, perform the [Walkthrough: Modifying the Policy](../core/walkthrough-modifying-the-policy.md) walkthrough, which gives you step-by-step instructions for modifying the policy to approve purchase orders with the value of **quantity** less than or equal to 1000 (instead of 500).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dae45-178">参照</span><span class="sxs-lookup"><span data-stu-id="dae45-178">See Also</span></span>  
 <span data-ttu-id="dae45-179">[条件の評価とアクションの実行](../core/condition-evaluation-and-action-execution.md) </span><span class="sxs-lookup"><span data-stu-id="dae45-179">[Condition Evaluation and Action Execution](../core/condition-evaluation-and-action-execution.md) </span></span>  
 [<span data-ttu-id="dae45-180">議題と優先度</span><span class="sxs-lookup"><span data-stu-id="dae45-180">Agenda and Priority</span></span>](../core/agenda-and-priority.md)