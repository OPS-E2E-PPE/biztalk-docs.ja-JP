---
title: 'チュートリアル: BizTalk Server のポリシー実行の追跡 |Microsoft ドキュメント'
description: 追跡を有効にして、BizTalk Server で、ポリシーの追跡の詳細を表示するのには、チュートリアル
ms.custom: ''
ms.date: 04/05/2016
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef88eae7-f0f8-4f3f-85d0-3961a47395b6
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f20b35aca2c4fb35419153ccfb149aa34501b21a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975096"
---
# <a name="walkthrough-tracking-policy-execution"></a><span data-ttu-id="d40b7-103">チュートリアル: ポリシーの実行を追跡します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-103">Walkthrough: Tracking Policy Execution</span></span>
<span data-ttu-id="d40b7-104">追跡を有効にするための手順、 **ProcessPurchaseOrder**ポリシー、およびポリシーが実行された後に追跡情報を表示するためです。</span><span class="sxs-lookup"><span data-stu-id="d40b7-104">Step-by-step procedures for enabling tracking for the **ProcessPurchaseOrder** policy, and for viewing the tracking information after the policy is executed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d40b7-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="d40b7-105">Prerequisites</span></span>  
<span data-ttu-id="d40b7-106">完了、[チュートリアル: ポリシーを変更する](../core/walkthrough-modifying-the-policy.md)このチュートリアルを実行する前にチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="d40b7-106">Complete the [Walkthrough: Modifying the Policy](../core/walkthrough-modifying-the-policy.md) walkthrough before performing this walkthrough.</span></span>  
  
## <a name="enable-tracking-for-the-processpurchaseorder-policy"></a><span data-ttu-id="d40b7-107">ProcessPurchaseOrder ポリシーの追跡を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d40b7-107">Enable tracking for the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="d40b7-108">開いている**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-108">Open **BizTalk Server Administration**.</span></span> <span data-ttu-id="d40b7-109">既に開いている場合は、f5 キーを押して更新します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-109">If it's already open, press F5 to refresh it.</span></span>  
  
2.  <span data-ttu-id="d40b7-110">展開**コンソール ルート**、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**RuleTestApp**です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-110">Expand **Console Root**, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **RuleTestApp**.</span></span>  
  
3.  <span data-ttu-id="d40b7-111">右クリック**ポリシー\*\*\*\*追加**、し、**ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-111">Right-click **Policies**, select **Add**, and then select **Policy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d40b7-112">ポリシーの追跡を有効にするには、BizTalk Server 管理コンソールを使用して BizTalk アプリケーションにポリシーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-112">To enable tracking for a policy, you must add the policy to a BizTalk application by using the BizTalk Server Administration console.</span></span>  
  
4.  <span data-ttu-id="d40b7-113">**ポリシーの追加** ダイアログ ボックスで、展開**ProcessPurchaseOrder**、バージョンを選択して**1.3**です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-113">In the **Add Policies** dialog box, expand **ProcessPurchaseOrder**, and select Version **1.3**.</span></span>  
  
5.  <span data-ttu-id="d40b7-114">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d40b7-114">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="d40b7-115">表示されない場合**ProcessPurchaseOrder**一覧で、f5 キーを押して表示を更新するを選択します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-115">If you don't see **ProcessPurchaseOrder** in the list, select F5 to refresh the view.</span></span>
  
7.  <span data-ttu-id="d40b7-116">右クリック**ProcessPurchaseOrder**、し、**追跡します。**</span><span class="sxs-lookup"><span data-stu-id="d40b7-116">Right-click **ProcessPurchaseOrder**, and then select **Tracking.**</span></span>  
  
8.  <span data-ttu-id="d40b7-117">**ポリシー追跡オプション** ダイアログ ボックスで、すべてのチェック ボックスを**ファクト アクティビティ**、**条件の評価**、**ルールの実行**、および**議題の更新**です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-117">In the **Policy Tracking Options** dialog box, select all the check boxes for **Fact activity**, **Condition evaluation**, **Rule firings**, and **Agenda updates**.</span></span>  
  
9. <span data-ttu-id="d40b7-118">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d40b7-118">Click **OK**.</span></span>  
  
## <a name="test-the-solution-and-view-the-tracking-information"></a><span data-ttu-id="d40b7-119">ソリューションをテストして、追跡情報を表示</span><span class="sxs-lookup"><span data-stu-id="d40b7-119">Test the solution and view the tracking information</span></span>  
  
1.  <span data-ttu-id="d40b7-120">開いている**SamplePO.xml**と**SamplePO2.xml**メモ帳の値を変更し、**ステータス**フィールドを**XYZ**です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-120">Open **SamplePO.xml** and **SamplePO2.xml** in notepad, and change the value of the **Status** field to **XYZ**.</span></span>  
  
2.  <span data-ttu-id="d40b7-121">コピー **SamplePO.xml**で作成した[チュートリアル: ポリシーのテスト](../core/walkthrough-testing-the-policy.md)オーケストレーションの入力ディレクトリにします。</span><span class="sxs-lookup"><span data-stu-id="d40b7-121">Copy **SamplePO.xml** that you created in [Walkthrough: Testing the Policy](../core/walkthrough-testing-the-policy.md) to the input directory for the orchestration.</span></span>  
  
3.  <span data-ttu-id="d40b7-122">オーケストレーションの出力ディレクトリに、出力ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-122">You should see an output file in the output directory for the orchestration.</span></span> <span data-ttu-id="d40b7-123">出力 XML ファイルを開くことを確認の値、**ステータス**にフィールドが設定されている**Approved**です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-123">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
4.  <span data-ttu-id="d40b7-124">**BizTalk Server 管理コンソール**に移動して、**グループの概要** ページで、をクリックして、**グループ ハブ** タブし、をクリックして**追跡サービス インスタンス**.</span><span class="sxs-lookup"><span data-stu-id="d40b7-124">In **BizTalk Server Administration**, go to the **Group Overview** page, click on the **Group Hub** tab, and then click on **Tracked Service Instances**.</span></span>  
  
5.  <span data-ttu-id="d40b7-125">オーケストレーション (RuleTest.Orchestration_1) の名前を右クリックし、をクリックして**メッセージ フロー**です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-125">Right-click the name of the Orchestration (RuleTest.Orchestration_1), and then click **Message Flow**.</span></span>  
  
6.  <span data-ttu-id="d40b7-126">をクリックして**このオーケストレーション インスタンスのポリシー実行の詳細を表示するには、このリンク**です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-126">Click **Follow this link to view the Policy execution details for this orchestration instance**.</span></span> <span data-ttu-id="d40b7-127">次の図のようなウィンドウに表示することを確認します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-127">Make sure you see the window that looks like the following figure:</span></span>  
  
     <span data-ttu-id="d40b7-128">![BRE & #45;チュートリアル & #45;FirstScreen](../core/media/1e59fe9e-cf2d-407a-81cd-102b57a515d2.gif "1e59fe9e-cf2d-407a-81cd-102b57a515d2")</span><span class="sxs-lookup"><span data-stu-id="d40b7-128">![BRE&#45;Walkthrough&#45;FirstScreen](../core/media/1e59fe9e-cf2d-407a-81cd-102b57a515d2.gif "1e59fe9e-cf2d-407a-81cd-102b57a515d2")</span></span>  
  
7. <span data-ttu-id="d40b7-129">[時刻] をクリックしてまたは**ProcessPurchaseOrder1.3**を次の画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-129">Click the time or **ProcessPurchaseOrder1.3** to see the following screen.</span></span> <span data-ttu-id="d40b7-130">この画面では、ポリシーの実行を要求したサービス (オーケストレーション)、オーケストレーションの ID、ポリシーが実行された時刻、およびポリシーの ID を参照できます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-130">In this screen, you can see the service (orchestration) that requested the policy execution, the ID of the orchestration, the time at which the policy was executed, and the ID of the policy.</span></span>  
  
     <span data-ttu-id="d40b7-131">![BRE & #45;チュートリアル & #45;PolicyExecDetails](../core/media/a65fd48f-2a54-4cc5-9b45-4cd3c211da33.gif "a65fd48f-2a54-4cc5-9b45-4cd3c211da33")</span><span class="sxs-lookup"><span data-stu-id="d40b7-131">![BRE&#45;Walkthrough&#45;PolicyExecDetails](../core/media/a65fd48f-2a54-4cc5-9b45-4cd3c211da33.gif "a65fd48f-2a54-4cc5-9b45-4cd3c211da33")</span></span>  
  
8. <span data-ttu-id="d40b7-132">をクリックして**ファクト アクティビティ**ルールにアサートされたファクト (データ) を表示するエンジンの作業メモリと、取り消されたファクトをルール エンジンの作業メモリからです。</span><span class="sxs-lookup"><span data-stu-id="d40b7-132">Click **Fact Activity** to see the facts (data) that were asserted into the rule engine's working memory and the facts that were retracted from the rule engine's working memory.</span></span>  
  
     <span data-ttu-id="d40b7-133">![BRE & #45;チュートリアル & #45;FactActivity](../core/media/27bc0d84-f202-4f5a-87a1-8b53006b3cee.gif "27bc0d84-f202-4f5a-87a1-8b53006b3cee")</span><span class="sxs-lookup"><span data-stu-id="d40b7-133">![BRE&#45;Walkthrough&#45;FactActivity](../core/media/27bc0d84-f202-4f5a-87a1-8b53006b3cee.gif "27bc0d84-f202-4f5a-87a1-8b53006b3cee")</span></span>  
  
9. <span data-ttu-id="d40b7-134">**ファイル** メニューのをクリックして**移動背面**です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-134">On the **File** menu, click **Navigate back**.</span></span>  
  
10. <span data-ttu-id="d40b7-135">をクリックして**評価条件**です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-135">Click **Conditions that Evaluated**.</span></span> <span data-ttu-id="d40b7-136">評価された条件の詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d40b7-136">You see the details about the conditions that were evaluated.</span></span> <span data-ttu-id="d40b7-137">この場合は、ポリシーに 2 つのルールがあり、各ポリシーに条件が 1 つずつ設定されています。</span><span class="sxs-lookup"><span data-stu-id="d40b7-137">In this case, there are two rules in the policy, and each policy has a condition.</span></span> <span data-ttu-id="d40b7-138">は 2 つの条件が評価されたことを確認できます評価される 1 つ`true`に評価される、もう 1 つと`false`です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-138">You can see that two conditions were evaluated; one evaluated to `true`, and the other one evaluated to `false`.</span></span>  
  
     <span data-ttu-id="d40b7-139">![BRE & #45;チュートリアル & #45;ConditionEvaluation](../core/media/ac772d01-919f-4b22-995b-409501a96848.gif "ac772d01-919f-4b22-995b-409501a96848")</span><span class="sxs-lookup"><span data-stu-id="d40b7-139">![BRE&#45;Walkthrough&#45;ConditionEvaluation](../core/media/ac772d01-919f-4b22-995b-409501a96848.gif "ac772d01-919f-4b22-995b-409501a96848")</span></span>  
  
11. <span data-ttu-id="d40b7-140">**ファイル** メニューのをクリックして**移動背面**です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-140">On the **File** menu, click **Navigate back**.</span></span>  
  
12. <span data-ttu-id="d40b7-141">をクリックして**議題の更新**です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-141">Click **Agenda Updates**.</span></span> <span data-ttu-id="d40b7-142">ApprovalRule のみが議題に追加されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-142">You can see that only the ApprovalRule is added to the agenda.</span></span> <span data-ttu-id="d40b7-143">DeniedRule は、条件が `false` と評価されるため議題に追加されていません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-143">The DeniedRule is not added to the agenda because its condition evaluates to `false`.</span></span>  
  
     <span data-ttu-id="d40b7-144">![BRE & #45;チュートリアル & #45;議題](../core/media/bc85d9ea-fc76-44de-aa75-134f47a5ec20.gif "bc85d9ea-fc76-44de-aa75-134f47a5ec20")</span><span class="sxs-lookup"><span data-stu-id="d40b7-144">![BRE&#45;Walkthrough&#45;Agenda](../core/media/bc85d9ea-fc76-44de-aa75-134f47a5ec20.gif "bc85d9ea-fc76-44de-aa75-134f47a5ec20")</span></span>  
  
13. <span data-ttu-id="d40b7-145">をクリックして**ApprovalRule** ApprovalRule の定義を表示します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-145">Click **ApprovalRule** to see the definition of the ApprovalRule.</span></span>  
  
14. <span data-ttu-id="d40b7-146">**ファイル** メニューのをクリックして**移動背面**です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-146">On the **File** menu, click **Navigate back**.</span></span>  
  
15. <span data-ttu-id="d40b7-147">**[ファイル]** メニューのをクリックして**移動背面**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-147">On **File** menu, click **Navigate back** again.</span></span>  
  
16. <span data-ttu-id="d40b7-148">をクリックして**を発生させたルール**です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-148">Click **Rules that fired**.</span></span> <span data-ttu-id="d40b7-149">ApprovalRule のみが実行された (ApprovalRule のアクションが実行された) ことがわかります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-149">You can see that only ApprovalRule was fired (actions for the ApprovalRule were executed).</span></span>  
  
17. <span data-ttu-id="d40b7-150">**ファイル** メニューのをクリックして**移動背面**です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-150">On the **File** menu, click **Navigate back**.</span></span>  
  
18. <span data-ttu-id="d40b7-151">をクリックして**実行されなかったルール**です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-151">Click **Rules that did not fire**.</span></span> <span data-ttu-id="d40b7-152">DeniedRule は、議題に含まれていなかったため実行されなかったことがわかります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-152">You can see that DeniedRule was not fired because it was not in the agenda.</span></span>  
  
19. <span data-ttu-id="d40b7-153">手順 1-18 で**SamplePO2.xml**です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-153">Repeat steps 1-18 with **SamplePO2.xml**.</span></span>  
  
## <a name="key-details"></a><span data-ttu-id="d40b7-154">キーの詳細</span><span class="sxs-lookup"><span data-stu-id="d40b7-154">Key details</span></span>  
  
-   <span data-ttu-id="d40b7-155">ポリシーの追跡情報は、ポリシーをテストする場合にビジネス ルール作成ツールで表示される追跡情報とよく似ています。</span><span class="sxs-lookup"><span data-stu-id="d40b7-155">The policy tracking information is very similar to the tracking information you see in Business Rule Composer when you test a policy.</span></span>  
  
-   <span data-ttu-id="d40b7-156">オーケストレーション名は RuleTest.odx ですが、名前が変更されてもオーケストレーションの型名が Orchestration_1 に設定されているため、オーケストレーションの名前は Orchestration_1 と表示されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-156">Although the orchestration name is RuleTest.odx, you see the name of the orchestration as Orchestration_1, because the Type Name for the orchestration is set to Orchestration_1 even though the Name is changed.</span></span> <span data-ttu-id="d40b7-157">追跡は、オーケストレーション名形式で表示\<Namespace\>.\<名前を入力\>です。</span><span class="sxs-lookup"><span data-stu-id="d40b7-157">Tracking is showing you the orchestration name in the format \<Namespace\>.\<Type Name\>.</span></span>  
  
-   <span data-ttu-id="d40b7-158">BizTalk Server 管理コンソールを使用して BizTalk アプリケーションからポリシーを削除した場合、そのポリシーはアプリケーションから削除されるだけでなく、ルール エンジン データベースからも削除されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-158">If you delete a policy from a BizTalk application by using the BizTalk Server Administration console, the tool deletes the policy not only from the application, but also from the rule engine database.</span></span> <span data-ttu-id="d40b7-159">削除されたポリシーは、ビジネス ルール作成ツールに表示されなくなります (F5 キーを押して表示を更新してください)。</span><span class="sxs-lookup"><span data-stu-id="d40b7-159">You will no longer see the policy in Business Rule Composer (press F5 to refresh).</span></span> <span data-ttu-id="d40b7-160">このため、アプリケーションからポリシーを削除する場合は、十分に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-160">Therefore, you should be careful when deleting a policy from an application.</span></span>  
  
-   <span data-ttu-id="d40b7-161">RuleTestApp の停止し、選択すると、**完全停止**オプション、ProcessPurchaseOrder ポリシー (バージョン 1.3) は自動的に展開されていません。</span><span class="sxs-lookup"><span data-stu-id="d40b7-161">When you stop the RuleTestApp and select the **Full Stop** option, the ProcessPurchaseOrder policy (version 1.3) is automatically undeployed.</span></span>  
  
-   <span data-ttu-id="d40b7-162">複数のアプリケーションでポリシーを使用する場合は、ポリシー用に独立したアプリケーションを作成して、クライアント アプリケーションからそのアプリケーションへの参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="d40b7-162">If a policy is used by multiple applications, create a separate application for the policy and then create references to it from the client applications.</span></span> <span data-ttu-id="d40b7-163">ポリシーをすべてのクライアント アプリケーションに追加すると、クライアント アプリケーションの 1 つを停止した時点でポリシーが展開解除され、そのポリシーを他のクライアント アプリケーションで使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="d40b7-163">If you add the policy to all the client applications, when you stop one of the client applications, the policy is undeployed, and the other client applications can no longer use the policy.</span></span> <span data-ttu-id="d40b7-164">したがって、複数のアプリケーション間で共有するポリシーについては、独立したアプリケーションを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d40b7-164">Therefore it is a good practice to create a separate application for a policy that is shared across two or more applications.</span></span>  
  
-   <span data-ttu-id="d40b7-165">RuleTestApp を開始すると、ProcessPurchaseOrder ポリシー (バージョン 1.3) は自動的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="d40b7-165">When you start the RuleTestApp, the ProcessPurchaseOrder policy (version 1.3) is automatically deployed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d40b7-166">次の手順</span><span class="sxs-lookup"><span data-stu-id="d40b7-166">Next Steps</span></span>  
 <span data-ttu-id="d40b7-167">これで、このチュートリアルを完了するには、[チュートリアル: ポリシーを展開する](../core/walkthrough-deploying-the-policy.md)ポリシーを展開するための手順を説明するチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="d40b7-167">Now that you have completed this walkthrough, go to the [Walkthrough: Deploying the Policy](../core/walkthrough-deploying-the-policy.md) walkthrough, which gives you step-by-step instructions for deploying policies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d40b7-168">参照</span><span class="sxs-lookup"><span data-stu-id="d40b7-168">See Also</span></span>  
 <span data-ttu-id="d40b7-169">[ポリシーの追跡を構成する方法](../core/how-to-configure-tracking-for-a-policy.md) </span><span class="sxs-lookup"><span data-stu-id="d40b7-169">[How to Configure Tracking for a Policy](../core/how-to-configure-tracking-for-a-policy.md) </span></span>  
 [<span data-ttu-id="d40b7-170">ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="d40b7-170">Managing Policies</span></span>](../core/managing-policies.md)