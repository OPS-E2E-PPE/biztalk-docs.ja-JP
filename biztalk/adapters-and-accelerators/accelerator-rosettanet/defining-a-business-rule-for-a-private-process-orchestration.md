---
title: "プライベート プロセス オーケストレーションのビジネス ルールの定義 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, policies
- vocabularies, saving
- private processes, orchestrations
- business rules, private processes
- creating, vocabularies
- vocabularies, business rules
- business rules, vocabularies
- policies, deploying
- vocabularies, creating
- orchestrations, private-process orchestrations
- private processes, customizing
- policies, publishing
- business rules, Set elements
- creating, policies
- customizing private processes
- Set elements
- business rules, orchestrations
- publishing, vocabularies
- vocabularies, publishing
- creating, rules
- business rules, Get elements
- policies, saving
- publishing, policies
- Get elements
- orchestrations, business rules
- rules
- private processes, business rules
- policies, creating
ms.assetid: 5d2b0257-1b15-482b-a562-798b808e9a2d
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8dd0ebb22bcf6253604e4e8bf7fd858deb776b0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="defining-a-business-rule-for-a-private-process-orchestration"></a><span data-ttu-id="67cd5-102">プライベート プロセス オーケストレーションのビジネス ルールの定義</span><span class="sxs-lookup"><span data-stu-id="67cd5-102">Defining a Business Rule for a Private Process Orchestration</span></span>
<span data-ttu-id="67cd5-103">受信確認プライベート プロセスで使用するビジネス ルールを定義できます。</span><span class="sxs-lookup"><span data-stu-id="67cd5-103">You can define a business rule for use in an acknowledgement private process.</span></span> <span data-ttu-id="67cd5-104">これにより、プライベート プロセス オーケストレーションを停止することなく、ビジネス ルールを大幅に変更できます。</span><span class="sxs-lookup"><span data-stu-id="67cd5-104">This lets you to modify the business rule dynamically without stopping the private-process orchestration.</span></span> <span data-ttu-id="67cd5-105">このプロセスでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ビジネス ルール エンジンを使用します。</span><span class="sxs-lookup"><span data-stu-id="67cd5-105">This process uses the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Business Rule Engine.</span></span> <span data-ttu-id="67cd5-106">このプロセスには以下の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="67cd5-106">This process involves the following steps:</span></span>  
  
1.  <span data-ttu-id="67cd5-107">新しいボキャブラリの追加。</span><span class="sxs-lookup"><span data-stu-id="67cd5-107">Adding a new vocabulary.</span></span> <span data-ttu-id="67cd5-108">少なくとも 1 つのボキャブラリ定数値を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67cd5-108">This involves defining at least one vocabulary constant value.</span></span> <span data-ttu-id="67cd5-109">この値により、ビジネス ルールのしきい値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="67cd5-109">This sets a business-rule threshold.</span></span> <span data-ttu-id="67cd5-110">さらに XML ドキュメントの `Get` 要素と `Set` 要素の定義も必要です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-110">It also involves defining XML document `Get` and `Set` elements.</span></span> <span data-ttu-id="67cd5-111">これにより、確立方法[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]しきい値を使用します。</span><span class="sxs-lookup"><span data-stu-id="67cd5-111">This establishes how [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] uses the threshold.</span></span>  
  
2.  <span data-ttu-id="67cd5-112">新しいポリシーの追加。</span><span class="sxs-lookup"><span data-stu-id="67cd5-112">Adding a new policy.</span></span> <span data-ttu-id="67cd5-113">ポリシーの作成、ルール セットの作成、およびそのポリシーの保存、公開、展開が含まれます。</span><span class="sxs-lookup"><span data-stu-id="67cd5-113">This involves creating a policy, creating a set of rules, and then saving, publishing, and deploying the policy.</span></span>  
  
3.  <span data-ttu-id="67cd5-114">プライベート プロセス オーケストレーションからのビジネス ルールの呼び出し。</span><span class="sxs-lookup"><span data-stu-id="67cd5-114">Calling the business rule from the private-process orchestration.</span></span> <span data-ttu-id="67cd5-115">これは、追加、**ルールの呼び出し**オーケストレーションへの図形です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-115">This involves adding a **Call Rules** shape to the orchestration.</span></span>  
  
 <span data-ttu-id="67cd5-116">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK には、サンプルが含まれています[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]ビジネス ポリシー、samplebtarnpolicy.xml、で\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>。Accelerator for rosettanet \sdk\pipautomation\3a4 です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-116">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK includes a sample [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] business policy, samplebtarnpolicy.xml, in \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\PipAutomation\3A4.</span></span> <span data-ttu-id="67cd5-117">詳細については、次を参照してください。[サンプル BTARN ビジネス ポリシー](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md)です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-117">For more information, see [Sample BTARN Business Policy](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md).</span></span>  
  
 <span data-ttu-id="67cd5-118">PIP3A4PrivateResponder.odx オーケストレーションは、ビジネス ルールを組み込んでいる PIP (Partner Interface Process) 固有の応答側プライベート プロセスを実装する方法を示すプライベート プロセス オーケストレーションのサンプルです。</span><span class="sxs-lookup"><span data-stu-id="67cd5-118">PIP3A4PrivateResponder.odx orchestration is a sample private-process orchestration that demonstrates how to implement a Partner Interface Process (PIP)-specific responder private process incorporating a business rule.</span></span> <span data-ttu-id="67cd5-119">このサンプルの詳細については、次を参照してください。 [3A4 プライベート応答側オーケストレーションを使用して、ビジネス ルール](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-119">For more information about this sample, see [3A4 Private Responder Orchestration Using a Business Rule](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md).</span></span>  
  
 <span data-ttu-id="67cd5-120">ボキャブラリおよびポリシーの詳細については、BizTalk Server で「ビジネス ルールの開発」トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="67cd5-120">For more information about vocabularies and policies, see the "Developing with Business Rules" topic in BizTalk Server.</span></span>  
  
### <a name="to-add-a-new-vocabulary"></a><span data-ttu-id="67cd5-121">新しいボキャブラリを追加するには</span><span class="sxs-lookup"><span data-stu-id="67cd5-121">To add a new vocabulary</span></span>  
  
1.  <span data-ttu-id="67cd5-122">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**ビジネス ルール作成ツール**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-122">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="67cd5-123">場合、**ルール ストアを開く**ダイアログ ボックスが開き、選択、 **BizTalk ルール エンジン**データベースを現在のサーバーを設定し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-123">If the **Open Rule Store** dialog box opens, select the **BizTalk Rule Engine** database that you set up on the current server, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="67cd5-124">[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]ビジネス ルール作成ツールで、ファクト エクスプ ローラー ウィンドウを右クリックして**ボキャブラリ**、クリックして**新しいボキャブラリの追加**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-124">In [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Business Rule Composer, in the Facts Explorer pane, right-click **Vocabularies**, and then click **Add New Vocabulary**.</span></span>  
  
4.  <span data-ttu-id="67cd5-125">プロパティ ウィンドウで (左下)、次のように設定します。、**名前**プロパティを適切なボキャブラリは、を押してからの名前に**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-125">In the Property pane (lower left), set the **Name** property to the name of the appropriate vocabulary, and then press **Enter**.</span></span>  
  
5.  <span data-ttu-id="67cd5-126">作成したボキャブラリ フォルダを展開しを右クリックして**バージョン 1.0 (未保存)**、クリックして**新しい定義の追加**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-126">Expand the vocabulary folder you just created, right-click **Version 1.0 (not saved)**, and then click **Add New Definition**.</span></span>  
  
6.  <span data-ttu-id="67cd5-127">**ボキャブラリの定義ウィザード**] ページで、[**定数値、値の範囲、または値セット**、クリックして**[次へ]**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-127">On the **Vocabulary Definition Wizard** page, select **Constant Value, Range of Values, or Set of Values**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="67cd5-128">**定数値、値の範囲、または値セット**] ページの [、**定義名**ボックスで、適切なボキャブラリ定数値の名前を入力します**Maximum Quantity Allowed。**、クリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-128">On the **Constant Value, Range of Values, or Set of Values** page, in the **Definition Name** box, type the name of the appropriate vocabulary constant value, such as **Maximum Quantity Allowed**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="67cd5-129">**定数値の定義**] ページの [、**値フィールド**ボックスに、しきい値を入力し、をクリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-129">On the **Define a Constant Value** page, in the **Value Field** box, type the threshold, and then click **Finish**.</span></span>  
  
### <a name="to-define-get-and-set-elements"></a><span data-ttu-id="67cd5-130">Get 要素と Set 要素を定義するには</span><span class="sxs-lookup"><span data-stu-id="67cd5-130">To define Get and Set elements</span></span>  
  
1.  <span data-ttu-id="67cd5-131">ビジネス ルール作成ツールのファクト エクスプローラ ペインで、"に、新しいボキャブラリ プロシージャ"を追加で作成したボキャブラリ フォルダの下を右クリックして**バージョン 1.0 (未保存)**、クリックして**新しい定義の追加**.</span><span class="sxs-lookup"><span data-stu-id="67cd5-131">In Business Rule Composer, in the Facts Explorer pane, under the vocabulary folder created in the "To add a new vocabulary procedure", right-click **Version 1.0 (not saved)**, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="67cd5-132">**ボキャブラリの定義ウィザード**] ページで、[ **XML ドキュメントの要素または属性**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-132">On the **Vocabulary Definition Wizard** page, select **XML Document Element or Attribute**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="67cd5-133">**XML ドキュメントの要素または属性** ページの定義名 テキスト ボックス内の名前を入力、**取得**要素。</span><span class="sxs-lookup"><span data-stu-id="67cd5-133">On the **XML Document Element or Attribute** page, in the Definition Name text box, type a name for a **Get** element.</span></span>  
  
4.  <span data-ttu-id="67cd5-134">をクリックして**参照**を使用して、スキーマ ファイルを選択してをクリックするスキーマの場所に移動して**開く**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-134">Click **Browse**, move to the location of the schema that you want to use, select the schema file, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="67cd5-135">場合、**ルート ノードの選択**ページが表示されたらを参照するルート ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="67cd5-135">If the **Select Root Node** page opens, select the root node to browse.</span></span>  
  
6.  <span data-ttu-id="67cd5-136">**バインドの選択** ページで、しきい値を定義するフィールドに移動してをクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-136">On the **Select Binding** page, move to the field for which you want to define the threshold, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="67cd5-137">**ドキュメントの種類**ボックスに、ドキュメントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="67cd5-137">In the **Document Type** box, type the name of the document.</span></span>  
  
8.  <span data-ttu-id="67cd5-138">**操作の種類**セクションで、 **「取得」操作の実行**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-138">In the **Operation Type** section, select **Perform “Get” operation**.</span></span>  
  
9. <span data-ttu-id="67cd5-139">**[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67cd5-139">Click **Finish**.</span></span>  
  
10. <span data-ttu-id="67cd5-140">1 つまたは複数を定義するには、この手順を繰り返します`Set`操作で、 **「設定」操作の実行**の**操作の種類**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-140">Repeat these steps to define one or more `Set` operations, select **Perform “Set” operation** for the **Operation Type**.</span></span>  
  
### <a name="to-save-and-publish-the-vocabulary"></a><span data-ttu-id="67cd5-141">ボキャブラリを保存および公開するには</span><span class="sxs-lookup"><span data-stu-id="67cd5-141">To save and publish the vocabulary</span></span>  
  
1.  <span data-ttu-id="67cd5-142">ビジネス ルール作成ツールで、ファクト エクスプ ローラー ウィンドウで、作成したボキャブラリ フォルダの下を右クリックして**バージョン 1.0 (未保存)**、クリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-142">In Business Rule Composer, in the Facts Explorer pane, under the vocabulary folder that you created, right-click **Version 1.0 (not saved)**, and then click **Save**.</span></span>  
  
2.  <span data-ttu-id="67cd5-143">ファクト エクスプ ローラー ウィンドウで、3 a4purchaseordervocabulary フォルダの下を右クリックして**バージョン 1.0**、し、**発行**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-143">In the Facts Explorer pane, under the 3A4PurchaseOrderVocabulary folder, right-click **Version 1.0**, and then select **Publish**.</span></span>  
  
### <a name="to-add-a-new-policy-and-rules"></a><span data-ttu-id="67cd5-144">新しいポリシーとルールを追加するには</span><span class="sxs-lookup"><span data-stu-id="67cd5-144">To add a new policy and rules</span></span>  
  
1.  <span data-ttu-id="67cd5-145">ビジネス ルール作成ツールでポリシー エクスプローラ ペインで右クリック**ポリシー**、クリックして**新しいポリシーの追加**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-145">In Business Rule Composer, in the Policy Explorer pane, right-click **Policies**, and then click **Add New Policy**.</span></span>  
  
2.  <span data-ttu-id="67cd5-146">をクリックして**"policy1"**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-146">Click **Policy1**.</span></span>  
  
3.  <span data-ttu-id="67cd5-147">プロパティ ペインで、設定、**名前**プロパティを適切なポリシーの名前にします。</span><span class="sxs-lookup"><span data-stu-id="67cd5-147">In the Property pane, set the **Name** property to the appropriate policy name.</span></span>  
  
4.  <span data-ttu-id="67cd5-148">ポリシー エクスプ ローラー ウィンドウで、新しいポリシーのフォルダーを右クリックして**バージョン 1.0 (未保存)**、クリックして**新しいルールの追加**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-148">In the Policy Explorer pane, under the folder for the new policy, right-click **Version 1.0 (not saved)**, and then click **Add New Rule**.</span></span>  
  
5.  <span data-ttu-id="67cd5-149">をクリックして**Rule1**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-149">Click **Rule1**.</span></span>  
  
6.  <span data-ttu-id="67cd5-150">プロパティ ウィンドウで、次のように設定します。、**名前**プロパティをルール名を選択し、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-150">In the Property pane, set the **Name** property to the rule name you want, and then press **Enter**.</span></span>  
  
7.  <span data-ttu-id="67cd5-151">ルール作成ツールで下にある、 **IF**  ウィンドウを右クリックして**条件**、し、該当する場合、論理条件を選択します。</span><span class="sxs-lookup"><span data-stu-id="67cd5-151">In the Rule Composer, under the **IF** pane, right-click **Conditions**, and then select a logical condition, if appropriate.</span></span>  
  
8.  <span data-ttu-id="67cd5-152">ファクト エクスプローラ ペインで下にある**ボキャブラリ**、展開**述語**、展開**バージョン 1.0 - 公開済み**、作成ツール画面にドラッグして、希望の述語の選択上にドロップして**条件**または論理演算子です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-152">In the Facts Explorer pane, under **Vocabularies**, expand **Predicates**, expand **Version 1.0 - Published**, select the predicate you want, drag it to the composer surface, and then drop it on **Conditions** or the logical operator.</span></span>  
  
9. <span data-ttu-id="67cd5-153">ファクト エクスプ ローラー ウィンドウで、ボキャブラリ フォルダーの下で作成したボキャブラリを展開し、**バージョン 1.0 - 公開済み**、select、`Get`または`Set`要素が作成ツール画面にドラッグし、上にドロップ**argument1**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-153">In the Facts Explorer pane, under the Vocabularies folder, expand the vocabulary that you created, expand **Version 1.0 - Published**, select a `Get` or `Set` element, drag it to the composer surface, and drop it on **argument1**.</span></span>  
  
10. <span data-ttu-id="67cd5-154">ボキャブラリ フォルダーを選択、`Get`または`Set`要素が作成ツール画面にドラッグし、上にドロップ**argument2**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-154">Under the vocabulary folder, select a `Get` or `Set` element, drag it to the composer surface and drop it on **argument2**.</span></span>  
  
11. <span data-ttu-id="67cd5-155">ボキャブラリ フォルダーの下の選択、`Set`要素、作成ツール画面にドラッグしにドロップ、**アクション**ボックスの [THEN] ペインでします。</span><span class="sxs-lookup"><span data-stu-id="67cd5-155">Under the vocabulary folder, select a `Set` element, drag it to the composer surface, and drop it in the **Actions** box in the THEN pane.</span></span>  
  
12. <span data-ttu-id="67cd5-156">変数に関連付けられている場合、`Set`要素に、必要に応じて変更し、変数、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-156">If a variable is associated with the `Set` element, click the variable, make changes as appropriate, and then press **Enter**.</span></span> <span data-ttu-id="67cd5-157">必要に応じて、他の `Set` 要素を使用してこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="67cd5-157">If appropriate, repeat with other `Set` elements.</span></span>  
  
### <a name="to-save-publish-and-deploy-the-policy"></a><span data-ttu-id="67cd5-158">ポリシーを保存、公開、展開するには</span><span class="sxs-lookup"><span data-stu-id="67cd5-158">To save, publish, and deploy the policy</span></span>  
  
1.  <span data-ttu-id="67cd5-159">ポリシー エクスプ ローラー ウィンドウで、作成したポリシー フォルダの下でビジネス ルール作成ツールでは、ルールの定義が完了したら、右クリック**バージョン 1.0 (未保存)**、クリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-159">When you have finished defining the rules, in Business Rule Composer, in the Policy Explorer pane, under the policy folder that you created, right-click **Version 1.0 (not saved)**, and then click **Save**.</span></span>  
  
2.  <span data-ttu-id="67cd5-160">ポリシー エクスプ ローラー ウィンドウで、作成したポリシー フォルダの下を右クリックして**バージョン 1.0**、クリックして**発行**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-160">In the Policy Explorer pane, under the policy folder that you created, right-click **Version 1.0**, and then click **Publish**.</span></span>  
  
3.  <span data-ttu-id="67cd5-161">ポリシー エクスプ ローラー ウィンドウで、作成したポリシー フォルダの下を右クリックして**バージョン 1.0**、クリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-161">In the Policy Explorer pane, under the policy folder that you created, right-click **Version 1.0**, and then click **Deploy**.</span></span>  
  
### <a name="to-call-the-business-rule-from-the-orchestration"></a><span data-ttu-id="67cd5-162">オーケストレーションからビジネス ルールを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="67cd5-162">To call the business rule from the orchestration</span></span>  
  
1.  <span data-ttu-id="67cd5-163">開始**Microsoft Visual Studio 2012**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-163">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="67cd5-164">**ファイル** メニューの 開く をポイントし、をクリックして**プロジェクト/ソリューション**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-164">On the **File** menu, point to Open, and then click **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="67cd5-165">ビジネス ルールを呼び出す必要があります、クリックしてオーケストレーションを含むソリューションを見つける**開く**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-165">Locate the solution that contains the orchestration that you must call the business rule from, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="67cd5-166">をクリックして**ビュー**、 をポイント**その他のウィンドウ**、順にクリック**オーケストレーション ビュー**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-166">Click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
5.  <span data-ttu-id="67cd5-167">展開**変数**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-167">Expand **Variables**.</span></span> <span data-ttu-id="67cd5-168">オーケストレーション変数の一覧に、オーケストレーションから呼び出すビジネス ポリシー内の各パラメーターに対応する変数が含まれているいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="67cd5-168">Make sure that the orchestration variable list contains a variable that corresponds to each parameter in the business policy that you call from the orchestration.</span></span> <span data-ttu-id="67cd5-169">その変数がポリシー パラメーターと同じ種類であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="67cd5-169">Make sure that the variable has the same type as the policy parameter.</span></span> <span data-ttu-id="67cd5-170">右クリックし、一覧に各ポリシー パラメーターのオーケストレーション変数が含まれていない場合**変数**、クリックして**新しい変数**です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-170">If the list does not contain an orchestration variable for each policy parameter, right-click **Variables**, and then click **New Variable**.</span></span> <span data-ttu-id="67cd5-171">[オーケストレーションの種類] に変数名を入力し、プロパティ ウィンドウでパラメーターの種類を入力します。</span><span class="sxs-lookup"><span data-stu-id="67cd5-171">In Orchestration View, type a variable name, and then in the Properties window, enter the type of the parameter.</span></span>  
  
6.  <span data-ttu-id="67cd5-172">**ツールボックス**、ドラッグ、**ルールの呼び出し**図形をオーケストレーション デザイン画面に、下にドロップし、**受信**図形です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-172">From the **Toolbox**, drag a **Call Rules** shape to the orchestration design surface, and then drop it under the **Receive** shape.</span></span>  
  
7.  <span data-ttu-id="67cd5-173">ダブルクリックして、**ルールの呼び出し**図形です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-173">Double-click the **Call Rules** shape.</span></span>  
  
8.  <span data-ttu-id="67cd5-174">**呼び出すビジネス ポリシーの選択**ボックスで、ドロップダウン リストから、ビジネス ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="67cd5-174">In the **Select the business policy you wish to call** box, select the business policy from the drop-down list.</span></span>  
  
9. <span data-ttu-id="67cd5-175">最初のパラメーターが示すようの**パラメーター名**、ドロップダウン リストから名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="67cd5-175">For the first parameter shown, for **Parameter Name**, select a name from the drop-down list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="67cd5-176">Btarn、**ポリシー パラメーター**ビジネス ポリシー内のすべてのパラメーターを使用してリスト。</span><span class="sxs-lookup"><span data-stu-id="67cd5-176">BTARN populates the **Policy Parameter** list with all the parameters in the business policy.</span></span> <span data-ttu-id="67cd5-177">リスト内の各パラメーターの BTARN が入力した値で**パラメーターの型**ビジネス ポリシーから。</span><span class="sxs-lookup"><span data-stu-id="67cd5-177">For each parameter in the list, BTARN enters a value in **Parameter Type** from the business policy.</span></span> <span data-ttu-id="67cd5-178">関連付けられているドロップダウン リストで**パラメーター名**BTARN は、ポリシー パラメータと同じ型を持つオーケストレーションの変数の一覧からすべての変数の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="67cd5-178">In the drop-down list associated with **Parameter Name**, BTARN enters the names of all variables from the orchestration's variable list that has the same type as the policy parameters.</span></span> <span data-ttu-id="67cd5-179">オーケストレーション変数を選択することにより、その変数はポリシー パラメーターに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="67cd5-179">By selecting an orchestration variable, you are associating that variable with the policy parameter.</span></span> <span data-ttu-id="67cd5-180">オーケストレーション変数は、[オーケストレーションの種類] で表示できます。</span><span class="sxs-lookup"><span data-stu-id="67cd5-180">You can view the orchestration variables in Orchestration View.</span></span>  
  
10. <span data-ttu-id="67cd5-181">その他すべてのパラメーターについて手順 9. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="67cd5-181">Repeat step 9 for all other parameters.</span></span>  
  
11. <span data-ttu-id="67cd5-182">オーケストレーション デザイン ウィンドウで、入力の追加など、ビジネス ポリシーに関連付けられている処理に必要なすべての他の図形、**デシジョン**図形の下、**ルールの呼び出し**図形です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-182">In the Orchestration Design window, enter all the additional shapes required for the processing associated with the business policy, including adding a **Decision** shape under the **Call Rules** shape.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="67cd5-183">使用する方法の例については、**ルールの呼び出し**オーケストレーションに図形を BTARN SDK に付属の PIP3A4PrivateResponder.odx オーケストレーションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="67cd5-183">For an example of how to use a **Call Rules** shape in an orchestration, see the PIP3A4PrivateResponder.odx orchestration included in the BTARN SDK.</span></span> <span data-ttu-id="67cd5-184">これは、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\pipautomation\3a4\pr です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-184">It is located at \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\PipAutomation\3A4\PR.</span></span> <span data-ttu-id="67cd5-185">詳細については、次を参照してください。 [3A4 プライベート応答側オーケストレーションを使用して、ビジネス ルール](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)です。</span><span class="sxs-lookup"><span data-stu-id="67cd5-185">For more information, see [3A4 Private Responder Orchestration Using a Business Rule](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md).</span></span>  
  
12. <span data-ttu-id="67cd5-186">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67cd5-186">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67cd5-187">参照</span><span class="sxs-lookup"><span data-stu-id="67cd5-187">See Also</span></span>  
 <span data-ttu-id="67cd5-188">[プログラミング ガイド](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md) </span><span class="sxs-lookup"><span data-stu-id="67cd5-188">[Programming Guide](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md) </span></span>  
 <span data-ttu-id="67cd5-189">[サンプル BTARN ビジネス ポリシー](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md) </span><span class="sxs-lookup"><span data-stu-id="67cd5-189">[Sample BTARN Business Policy](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md) </span></span>  
 [<span data-ttu-id="67cd5-190">ビジネス ルールを使用した 3A4 プライベート レスポンダー オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="67cd5-190">3A4 Private Responder Orchestration Using a Business Rule</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)