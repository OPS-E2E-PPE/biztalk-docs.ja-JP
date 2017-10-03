---
title: "チュートリアル: ポリシーにルールを追加する |Microsoft ドキュメント"
ms.custom: 
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2a682c0-a5d7-4550-924d-be9fa29b84d2
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 343dc2e9c7965ffb27a806d18944da99777dd3ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-adding-a-rule-to-the-policy"></a><span data-ttu-id="10dae-102">チュートリアル: ポリシーにルールを追加します。</span><span class="sxs-lookup"><span data-stu-id="10dae-102">Walkthrough: Adding a Rule to the Policy</span></span>
<span data-ttu-id="10dae-103">このチュートリアルでは、という名前のルールを追加するための手順は**DeniedRule**を**ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="10dae-103">This walkthrough provides step-by-step procedures for adding a rule named **DeniedRule** to the **ProcessPurchaseOrder** policy.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="10dae-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="10dae-104">Prerequisites</span></span>  
 <span data-ttu-id="10dae-105">完了する必要があります、[チュートリアル: ポリシーで作成およびボキャブラリ](../core/walkthrough-creating-and-using-a-vocabulary-in-the-policy.md)このチュートリアルを実行する前にチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="10dae-105">You must complete the [Walkthrough: Creating and Using a Vocabulary in the Policy](../core/walkthrough-creating-and-using-a-vocabulary-in-the-policy.md) walkthrough before performing this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="10dae-106">このチュートリアルの概要</span><span class="sxs-lookup"><span data-stu-id="10dae-106">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="10dae-107">次の表に示すように、このチュートリアルには 3 つの手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="10dae-107">This walkthrough contains three procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="10dae-108">手順のタイトル</span><span class="sxs-lookup"><span data-stu-id="10dae-108">Procedure title</span></span>|<span data-ttu-id="10dae-109">手順の説明</span><span class="sxs-lookup"><span data-stu-id="10dae-109">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="10dae-110">ProcessPurchaseOrder ポリシーに DeniedRule を追加するには</span><span class="sxs-lookup"><span data-stu-id="10dae-110">To add DeniedRule to the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="10dae-111">という名前の新しいルールを追加するための手順をわかりやすく説明**DeniedRule**を**ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="10dae-111">Provides step-by-step instructions for adding a new rule named **DeniedRule** to the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="10dae-112">**DeniedRule**規則セットの値、**ステータス**フィールドを**Denied**場合の値、**数量**が 500 より大きい。</span><span class="sxs-lookup"><span data-stu-id="10dae-112">The **DeniedRule** rule sets the value of the **Status** field to **Denied** if the value of the **Quantity** is greater than 500.</span></span>|  
|<span data-ttu-id="10dae-113">ビジネス ルール作成ツールを使用してテストするには</span><span class="sxs-lookup"><span data-stu-id="10dae-113">To test with Business Rule Composer</span></span>|<span data-ttu-id="10dae-114">テストするための手順をわかりやすく説明、 **ProcessPurchaseOrder**ビジネス ルール作成ツールを使用してポリシー。</span><span class="sxs-lookup"><span data-stu-id="10dae-114">Provides step-by-step instructions for testing the **ProcessPurchaseOrder** policy by using Business Rule Composer.</span></span>|  
|<span data-ttu-id="10dae-115">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="10dae-115">To test the solution</span></span>|<span data-ttu-id="10dae-116">ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="10dae-116">Provides step-by-step instructions for testing the solution.</span></span>|  
  
### <a name="to-add-deniedrule-to-the-processpurchaseorder-policy"></a><span data-ttu-id="10dae-117">ProcessPurchaseOrder ポリシーに DeniedRule を追加するには</span><span class="sxs-lookup"><span data-stu-id="10dae-117">To add DeniedRule to the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="10dae-118">**開始**] メニューの [開いている**ビジネス ルール作成ツール**です。</span><span class="sxs-lookup"><span data-stu-id="10dae-118">On the **Start** menu, open **Business Rule Composer**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="10dae-119">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="10dae-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="10dae-120">これを行うには、アプリケーションを右クリックし、**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="10dae-120">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="10dae-121">ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、展開**ProcessPurchaseOrder**を右クリックして**バージョン 1.1**、クリックして**をコピー**.</span><span class="sxs-lookup"><span data-stu-id="10dae-121">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.1**, and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="10dae-122">右クリック**ProcessPurchaseOrder**、クリックして**ポリシーのバージョンの貼り付け**です。</span><span class="sxs-lookup"><span data-stu-id="10dae-122">Right-click **ProcessPurchaseOrder**, and then click **Paste Policy Version**.</span></span>  
  
4.  <span data-ttu-id="10dae-123">右クリック**Version 1.2 (未保存)**、 をクリックして**新しいルールの追加**、規則の名前を変更し、 **DeniedRule**です。</span><span class="sxs-lookup"><span data-stu-id="10dae-123">Right-click **Version 1.2(not saved)**, click **Add New Rule**, and then change the name of the rule to **DeniedRule**.</span></span>  
  
5.  <span data-ttu-id="10dae-124">規則の名前を変更する忘れたかどうか**DeniedRule**手順 4 で、をクリックして**Rule1**、名前を変更して**DeniedRule**プロパティ ウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="10dae-124">If you forgot to change the name of the rule to **DeniedRule** in step 4, click **Rule1**, and change the name to **DeniedRule** in the Properties window.</span></span>  
  
6.  <span data-ttu-id="10dae-125">IF ペインで右クリック**条件**、 をポイント**述語**、クリックして**より大きい**です。</span><span class="sxs-lookup"><span data-stu-id="10dae-125">In the IF pane, right-click **Conditions**, point to **Predicates**, and then click **Greater Than**.</span></span>  
  
7.  <span data-ttu-id="10dae-126">[ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**タブです。</span><span class="sxs-lookup"><span data-stu-id="10dae-126">In the Facts Explorer window, click the **Vocabularies** tab.</span></span>  
  
8.  <span data-ttu-id="10dae-127">展開**ボキャブラリ**、展開**POVocabulary**、展開**バージョン 1.0 - 公開済み**、し、ドラッグ**要求された数量**に**argument1** IF ペイン。</span><span class="sxs-lookup"><span data-stu-id="10dae-127">Expand **Vocabularies**, expand **POVocabulary**, expand **Version 1.0 - Published**, and then drag **Request Quantity** to **argument1** in the IF pane.</span></span>  
  
9. <span data-ttu-id="10dae-128">ドラッグ**許可される項目の最大数**に**argument2** IF ペイン。</span><span class="sxs-lookup"><span data-stu-id="10dae-128">Drag **Maximum number of items allowed** to **argument2** in the IF pane.</span></span>  
  
10. <span data-ttu-id="10dae-129">ドラッグ**要求の状態**[THEN] ペインにします。</span><span class="sxs-lookup"><span data-stu-id="10dae-129">Drag **Request Status** to the THEN pane.</span></span>  
  
11. <span data-ttu-id="10dae-130">をクリックして**\<空の文字列 >**し、入力**Denied**です。</span><span class="sxs-lookup"><span data-stu-id="10dae-130">Click **\<empty string>** and then type **Denied**.</span></span>  
  
12. <span data-ttu-id="10dae-131">右クリック**Version 1.2 (未保存)**、クリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="10dae-131">Right-click **Version 1.2 (not saved)**, and then click **Save**.</span></span>  
  
13. <span data-ttu-id="10dae-132">右クリック**バージョン 1.2**、クリックして**発行**です。</span><span class="sxs-lookup"><span data-stu-id="10dae-132">Right-click **Version 1.2**, and then click **Publish**.</span></span>  
  
14. <span data-ttu-id="10dae-133">右クリック**バージョン 1.2**、クリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="10dae-133">Right-click **Version 1.2**, and then click **Deploy**.</span></span>  
  
### <a name="to-test-with-business-rule-composer"></a><span data-ttu-id="10dae-134">ビジネス ルール作成ツールを使用してテストするには</span><span class="sxs-lookup"><span data-stu-id="10dae-134">To test with Business Rule Composer</span></span>  
  
1.  <span data-ttu-id="10dae-135">値を変更して、SamplePO.xml ファイルと SamplePO2.xml ファイルをメモ帳で開き、**ステータス**フィールドを**XYZ**です。</span><span class="sxs-lookup"><span data-stu-id="10dae-135">Open the SamplePO.xml and SamplePO2.xml files in Notepad and change the value of the **Status** field to **XYZ**.</span></span>  
  
2.  <span data-ttu-id="10dae-136">ポリシー エクスプ ローラー] ウィンドウで、**ポリシー**、展開**ProcessPurchaseOrder**を右クリックして**バージョン 1.2**、クリックして**[ポリシーのテスト**.</span><span class="sxs-lookup"><span data-stu-id="10dae-136">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.2**, and then click **Test Policy**.</span></span>  
  
3.  <span data-ttu-id="10dae-137">下にある、 **XMLDocuments**ノードで、選択**RuleTest.PO**、クリックして**インスタンスを追加**です。</span><span class="sxs-lookup"><span data-stu-id="10dae-137">Under the **XMLDocuments** node, select **RuleTest.PO**, and then click **Add Instance**.</span></span>  
  
4.  <span data-ttu-id="10dae-138">選択**SamplePO.xml**、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="10dae-138">Select **SamplePO.xml**, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="10dae-139">をクリックして**テスト**です。</span><span class="sxs-lookup"><span data-stu-id="10dae-139">Click **Test**.</span></span>  
  
6.  <span data-ttu-id="10dae-140">見て、**議題の更新**出力では、セクションし、だけであることを確認**ApprovalRule**議題に追加します。</span><span class="sxs-lookup"><span data-stu-id="10dae-140">Look at the **Agenda Update** section in the output, and notice that only **ApprovalRule** is added to the agenda.</span></span> <span data-ttu-id="10dae-141">このため、このルールだけが実行されます (このルールに関連付けられたアクションが実行されます)。</span><span class="sxs-lookup"><span data-stu-id="10dae-141">Therefore it is the only rule that fires (actions associated with the rule are executed).</span></span>  
  
7.  <span data-ttu-id="10dae-142">開いている**SamplePO.xml**メモ帳で通知の値、**ステータス**フィールドに設定されて**承認済み**です。</span><span class="sxs-lookup"><span data-stu-id="10dae-142">Open **SamplePO.xml** in Notepad and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
8.  <span data-ttu-id="10dae-143">ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、展開**ProcessPurchaseOrder**を右クリックして**バージョン 1.2**、順にクリック**テスト ポリシーです。**</span><span class="sxs-lookup"><span data-stu-id="10dae-143">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.2**, and then click **Test Policy.**</span></span>  
  
9. <span data-ttu-id="10dae-144">選択**SamplePO.xml**、 をクリックして**削除インスタンス**、クリックして**インスタンスを追加**です。</span><span class="sxs-lookup"><span data-stu-id="10dae-144">Select **SamplePO.xml**, click **Remove instance**, and then click **Add Instance**.</span></span>  
  
10. <span data-ttu-id="10dae-145">選択**SamplePO2.xml**、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="10dae-145">Select **SamplePO2.xml**, and then click **Open**.</span></span>  
  
11. <span data-ttu-id="10dae-146">をクリックして**テスト**です。</span><span class="sxs-lookup"><span data-stu-id="10dae-146">Click **Test**.</span></span>  
  
12. <span data-ttu-id="10dae-147">見て、**議題の更新**出力では、セクションし、だけであることを確認**DeniedRule**議題に追加します。</span><span class="sxs-lookup"><span data-stu-id="10dae-147">Look at the **Agenda Update** section in the output, and notice that only **DeniedRule** is added to the agenda.</span></span> <span data-ttu-id="10dae-148">このため、このルールだけが実行されます。</span><span class="sxs-lookup"><span data-stu-id="10dae-148">Therefore it is the only rule that fires.</span></span>  
  
13. <span data-ttu-id="10dae-149">開いている**SamplePO2.xml**メモ帳で通知の値、**ステータス**フィールドは**が拒否されました**です。</span><span class="sxs-lookup"><span data-stu-id="10dae-149">Open **SamplePO2.xml** in Notepad and notice that the value of the **Status** field is **Denied**.</span></span>  
  
### <a name="to-test-the-solution"></a><span data-ttu-id="10dae-150">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="10dae-150">To test the solution</span></span>  
  
1.  <span data-ttu-id="10dae-151">開いている**SamplePO.xml**と**SamplePO2.xml**メモ帳での値を変更し、**ステータス**フィールドを**XYZ**です。</span><span class="sxs-lookup"><span data-stu-id="10dae-151">Open **SamplePO.xml** and **SamplePO2.xml** in Notepad and change the value of the **Status** field to **XYZ**.</span></span>  
  
2.  <span data-ttu-id="10dae-152">コピー、 **SamplePO.xml**オーケストレーション用の C:\BRE-Walkthroughs\RuleTestSol\Input ディレクトリに C:\BRE-Walkthroughs ディレクトリからファイルです。</span><span class="sxs-lookup"><span data-stu-id="10dae-152">Copy the **SamplePO.xml** file from the C:\BRE-Walkthroughs directory to the C:\BRE-Walkthroughs\RuleTestSol\Input directory for the orchestration.</span></span>  
  
3.  <span data-ttu-id="10dae-153">オーケストレーションの C:\BRE-Walkthroughs\RuleTestSol\Output ディレクトリに出力ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="10dae-153">You should see an output file in the C:\BRE-Walkthroughs\RuleTestSol\Output directory for the orchestration.</span></span> <span data-ttu-id="10dae-154">出力 XML ファイルを開くことを確認の値、**ステータス**にフィールドが設定されている**Approved**です。</span><span class="sxs-lookup"><span data-stu-id="10dae-154">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
4.  <span data-ttu-id="10dae-155">手順 2 および 3 を繰り返します**SamplePO2.xml**、ことを確認の値、**ステータス**フィールドに設定されて**Denied**出力ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="10dae-155">Repeat steps 2 and 3 with **SamplePO2.xml**, and notice that the value of the **Status** field is set to **Denied** in the output document.</span></span> <span data-ttu-id="10dae-156">オーケストレーションでのバージョン 1.2 を使用していることが証明、 **ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="10dae-156">This proves that the orchestration is using version 1.2 of the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="10dae-157">オーケストレーションは、配置済みの最新バージョンを使用して、 **ProcessPurchaseOrder**ポリシーが**1.2**です。</span><span class="sxs-lookup"><span data-stu-id="10dae-157">The orchestration uses the latest deployed version of the **ProcessPurchaseOrder** policy, which is **1.2**.</span></span> <span data-ttu-id="10dae-158">ポリシーのバージョン 1.2 を使用するためにポリシーのバージョン 1.1 を展開解除する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="10dae-158">You do not need to undeploy version 1.1 of the policy to use version 1.2 of the policy.</span></span> <span data-ttu-id="10dae-159">ただし、ソリューションをテストする前に約 60 秒間待つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="10dae-159">However, you need to wait for approximately 60 seconds before testing the solution.</span></span> <span data-ttu-id="10dae-160">詳細については、「コメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10dae-160">For more information, see the Comments section.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="10dae-161">コメント</span><span class="sxs-lookup"><span data-stu-id="10dae-161">Comments</span></span>  
  
-   <span data-ttu-id="10dae-162">ポリシーには、1 つ以上のルールを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="10dae-162">A policy can have one or more rules.</span></span> <span data-ttu-id="10dae-163">理論上は、1 つのポリシー内のルールの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="10dae-163">There is no logical limit on the number of rules in a policy.</span></span>  
  
-   <span data-ttu-id="10dae-164">ルール エンジンは、条件の評価、競合解決、アクションの実行というアルゴリズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="10dae-164">The rule engine uses a Condition Evaluation - Conflict Resolution - Action Execution algorithm.</span></span> <span data-ttu-id="10dae-165">**条件の評価**段階では、ルール エンジンは、すべてのルールの条件を評価します。</span><span class="sxs-lookup"><span data-stu-id="10dae-165">In the **Condition Evaluation** stage, the rule engine evaluates conditions in all the rules.</span></span> <span data-ttu-id="10dae-166">条件が true と評価される条件を持つルールは、実行の候補となるルールになります。</span><span class="sxs-lookup"><span data-stu-id="10dae-166">The rules whose conditions evaluate to true become candidate rules for execution.</span></span> <span data-ttu-id="10dae-167">**競合の解決**ステージで候補ルールがルールの優先度の順序で議題に追加されます。</span><span class="sxs-lookup"><span data-stu-id="10dae-167">In the **Conflict Resolution** stage, the candidate rules are added to the agenda in the order of the priority of the rule.</span></span> <span data-ttu-id="10dae-168">**アクションの実行**ステージで規則が実行される候補では、操作します。</span><span class="sxs-lookup"><span data-stu-id="10dae-168">In the **Action Execution** stage, the actions in the candidate rules are executed.</span></span> <span data-ttu-id="10dae-169">複数の候補ルールが同じ優先度を持っている場合、それらのルールのアクションの実行については決定的な順序はありません。</span><span class="sxs-lookup"><span data-stu-id="10dae-169">If candidate rules have the same priority, there is no deterministic order in which the actions for those rules are executed.</span></span> <span data-ttu-id="10dae-170">これらのアクションは並列して実行されることを想定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10dae-170">You should assume that they are executed in parallel.</span></span>  
  
-   <span data-ttu-id="10dae-171">このシナリオでは、任意の指定されたサンプル ファイルに対して、ルールの 1 つだけが実行されます。</span><span class="sxs-lookup"><span data-stu-id="10dae-171">In this scenario, for any given sample file, only one of the rules is fired.</span></span> <span data-ttu-id="10dae-172">値を変更することを確認してください、**ステータス**テストを実行する前にフィールドです。</span><span class="sxs-lookup"><span data-stu-id="10dae-172">Make sure that you change the value of the **Status** field before running a test.</span></span>  
  
-   <span data-ttu-id="10dae-173">ポリシーの新しいバージョンが展開される場合は、テスト前に約 60 秒間待つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="10dae-173">When a new version of the policy is deployed, you should wait approximately 60 seconds before testing.</span></span> <span data-ttu-id="10dae-174">ルール エンジン更新サービスは、定期的に (既定では 60 秒ごとに) ルール エンジン データベースをポーリングして、新しく展開されたポリシーを検索します。</span><span class="sxs-lookup"><span data-stu-id="10dae-174">The rule engine update service polls the rule engine database on a periodic basis (every 60 seconds by default) to look for newly deployed policies.</span></span> <span data-ttu-id="10dae-175">ルール エンジン更新サービスは、ルール エンジン データベースからポリシーの展開されている最新のバージョンに関する情報を使用して、メモリ内のポリシー オブジェクトを更新します。</span><span class="sxs-lookup"><span data-stu-id="10dae-175">The rule engine update service updates the policy object in memory with the information about the latest deployed version of the policy from the rule engine database.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="10dae-176">次の手順</span><span class="sxs-lookup"><span data-stu-id="10dae-176">Next Steps</span></span>  
 <span data-ttu-id="10dae-177">これで、このチュートリアルを完了すると、実行、[チュートリアル: ポリシーを変更する](../core/walkthrough-modifying-the-policy.md)の値は、発注書を承認するポリシーを変更するための手順を説明するチュートリアル**数量**(500) ではなく 1000 以下です。</span><span class="sxs-lookup"><span data-stu-id="10dae-177">Now that you have completed this walkthrough, perform the [Walkthrough: Modifying the Policy](../core/walkthrough-modifying-the-policy.md) walkthrough, which gives you step-by-step instructions for modifying the policy to approve purchase orders with the value of **quantity** less than or equal to 1000 (instead of 500).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10dae-178">参照</span><span class="sxs-lookup"><span data-stu-id="10dae-178">See Also</span></span>  
 <span data-ttu-id="10dae-179">[条件の評価とアクションの実行](../core/condition-evaluation-and-action-execution.md) </span><span class="sxs-lookup"><span data-stu-id="10dae-179">[Condition Evaluation and Action Execution](../core/condition-evaluation-and-action-execution.md) </span></span>  
 [<span data-ttu-id="10dae-180">議題と優先度</span><span class="sxs-lookup"><span data-stu-id="10dae-180">Agenda and Priority</span></span>](../core/agenda-and-priority.md)