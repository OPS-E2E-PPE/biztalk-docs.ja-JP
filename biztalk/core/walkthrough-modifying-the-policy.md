---
title: "チュートリアル: ポリシーの変更 |Microsoft ドキュメント"
ms.custom: 
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9dd74440-2a45-4a1a-8e36-98796e1e1392
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7292d541adaf0ae2242d1c504f1a845dde66f5dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-modifying-the-policy"></a><span data-ttu-id="5e0ee-102">チュートリアル: ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-102">Walkthrough: Modifying the Policy</span></span>
<span data-ttu-id="5e0ee-103">このチュートリアルでの新しいバージョンを作成する手順については、 **POVocabulary**の新しいバージョンを作成、 **ProcessPurchaseOrder**ポリシー、およびの最新バージョンを使用して、**POVocabulary**の新しいバージョンで、 **ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-103">This walkthrough provides step-by-step instructions for creating a new version of the **POVocabulary**, creating a new version of the **ProcessPurchaseOrder** policy, and using the latest version of the **POVocabulary** in the new version of the **ProcessPurchaseOrder** policy.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5e0ee-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="5e0ee-104">Prerequisites</span></span>  
 <span data-ttu-id="5e0ee-105">完了する必要があります、[チュートリアル: ポリシーにルールを追加する](../core/walkthrough-adding-a-rule-to-the-policy.md)このチュートリアルを実行する前にチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-105">You must complete the [Walkthrough: Adding a Rule to the Policy](../core/walkthrough-adding-a-rule-to-the-policy.md) walkthrough before performing this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="5e0ee-106">このチュートリアルの概要</span><span class="sxs-lookup"><span data-stu-id="5e0ee-106">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="5e0ee-107">次の表に示すように、このチュートリアルには 3 つの手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-107">This walkthrough contains three procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="5e0ee-108">手順のタイトル</span><span class="sxs-lookup"><span data-stu-id="5e0ee-108">Procedure title</span></span>|<span data-ttu-id="5e0ee-109">手順の説明</span><span class="sxs-lookup"><span data-stu-id="5e0ee-109">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="5e0ee-110">POVocabulary ボキャブラリを変更するには</span><span class="sxs-lookup"><span data-stu-id="5e0ee-110">To modify the POVocabulary vocabulary</span></span>|<span data-ttu-id="5e0ee-111">新しいボキャブラリのバージョンを作成するための値を変更する手順をわかりやすく説明**許可される項目の最大数**から**500**に**1000**です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-111">Provides step-by-step instructions for creating a new vocabulary version to modify the value of **Maximum number of items allowed** from **500** to **1000**.</span></span>|  
|<span data-ttu-id="5e0ee-112">ProcessPurchaseOrder ポリシーを変更して、更新されたボキャブラリを使用するには</span><span class="sxs-lookup"><span data-stu-id="5e0ee-112">To modify the ProcessPurchaseOrder policy to use the updated vocabulary</span></span>|<span data-ttu-id="5e0ee-113">新しいバージョンを作成するための手順をわかりやすく説明、 **ProcessPurchaseOrder**の新しいバージョンを使用するポリシーを**POVocabulary**です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-113">Provides step-by-step instructions for creating a new version of the **ProcessPurchaseOrder** policy to use the new version of **POVocabulary**.</span></span>|  
|<span data-ttu-id="5e0ee-114">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-114">To test the solution</span></span>|<span data-ttu-id="5e0ee-115">ステップごとの説明に従って、ソリューションをテストし、新しいポリシーが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-115">Provides step-by-step instructions for testing the solution and verifying that the new policy is in effect.</span></span>|  
  
### <a name="to-modify-the-povocabulary-vocabulary"></a><span data-ttu-id="5e0ee-116">POVocabulary ボキャブラリを変更するには</span><span class="sxs-lookup"><span data-stu-id="5e0ee-116">To modify the POVocabulary vocabulary</span></span>  
  
1.  <span data-ttu-id="5e0ee-117">**開始**] メニューの [開いている**ビジネス ルール作成ツール**です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-117">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="5e0ee-118">開く、f5 キーを押して、またはをクリックを既にのビジネス ルール作成ツールがあるかどうか**再読み込み**で、**ファイル**メニューを更新します。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-118">If you have Business Rule Composer already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5e0ee-119">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="5e0ee-120">これを行うには、アプリケーションを右クリックし、**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-120">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="5e0ee-121">ファクト エクスプ ローラー ウィンドウで、**ボキャブラリ**の順に展開および**POVocabulary**です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-121">In the Facts Explorer window, expand **Vocabularies**, and then expand **POVocabulary**.</span></span>  
  
3.  <span data-ttu-id="5e0ee-122">右クリック**バージョン 1.0 - 公開済み**、クリックして**コピー**です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-122">Right-click **Version 1.0 - Published**, and then click **Copy**.</span></span>  
  
4.  <span data-ttu-id="5e0ee-123">右クリック**POVocabulary**、クリックして**ボキャブラリのバージョンの貼り付け**です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-123">Right-click **POVocabulary**, and then click **Paste Vocabulary Version**.</span></span>  
  
5.  <span data-ttu-id="5e0ee-124">ダブルクリックして**最大数の指定できるアイテム**で**バージョン 1.1 (未保存)**ボキャブラリの定義ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-124">Double-click **Maximum Number of Items Allowed** in **Version 1.1 (not saved)** to start the Vocabulary Definition Wizard.</span></span>  
  
6.  <span data-ttu-id="5e0ee-125">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-125">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="5e0ee-126">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-126">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="5e0ee-127">値から変更**500**に**1000**です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-127">Change the value from **500** to **1000**.</span></span>  
  
9. <span data-ttu-id="5e0ee-128">**[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-128">Click **Finish**.</span></span>  
  
10. <span data-ttu-id="5e0ee-129">右クリック**バージョン 1.1 (未保存)**、クリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-129">Right-click **Version 1.1 (not saved)**, and then click **Save**.</span></span>  
  
11. <span data-ttu-id="5e0ee-130">右クリック**バージョン 1.1**、クリックして**発行**です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-130">Right-click **Version 1.1**, and then click **Publish**.</span></span>  
  
### <a name="to-modify-the-processpurchaseorder-policy-to-use-the-updated-vocabulary"></a><span data-ttu-id="5e0ee-131">ProcessPurchaseOrder ポリシーを変更して、更新されたボキャブラリを使用するには</span><span class="sxs-lookup"><span data-stu-id="5e0ee-131">To modify the ProcessPurchaseOrder policy to use the updated vocabulary</span></span>  
  
1.  <span data-ttu-id="5e0ee-132">ポリシー エクスプ ローラーで、**ポリシー**の順に展開および**ProcessPurchaseOrder**です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-132">In Policy Explorer, expand **Policies**, and then expand **ProcessPurchaseOrder**.</span></span>  
  
2.  <span data-ttu-id="5e0ee-133">右クリック**バージョン 1.2**、クリックして**コピー**です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-133">Right-click **Version 1.2**, and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="5e0ee-134">右クリック**ProcessPurchaseOrder**、クリックして**[pastepolicyversion]**です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-134">Right-click **ProcessPurchaseOrder**, and then click **PastePolicyVersion**.</span></span>  
  
4.  <span data-ttu-id="5e0ee-135">をクリックして**ApprovalRule**で**Version 1.3 (未保存)**です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-135">Click **ApprovalRule** in **Version 1.3 (not saved)**.</span></span>  
  
5.  <span data-ttu-id="5e0ee-136">ファクト エクスプ ローラーで、**ボキャブラリ**、展開**POVocabulary**、順に展開**バージョン 1.1 - 公開済み**です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-136">In Facts Explorer, expand **Vocabularies**, expand **POVocabulary**, and then expand **Version 1.1 - Published**.</span></span>  
  
6.  <span data-ttu-id="5e0ee-137">ドラッグ**最大数の指定できるアイテム**で**バージョン 1.1 - 公開済み**を置き換える**最大数の指定できるアイテム**[IF] ペインで、バージョン 1.0 のです。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-137">Drag **Maximum Number of Items Allowed** in **Version 1.1 - Published** to replace **Maximum Number of Items Allowed** of version 1.0 in the IF pane.</span></span>  
  
7.  <span data-ttu-id="5e0ee-138">手順 4. ~ 6. を繰り返します**DeniedRule**です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-138">Repeat steps 4-6 with **DeniedRule**.</span></span>  
  
8.  <span data-ttu-id="5e0ee-139">右クリック**Version 1.3 (未保存)**、クリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-139">Right-click **Version 1.3 (not saved)**, and then click **Save**.</span></span>  
  
9. <span data-ttu-id="5e0ee-140">右クリック**Version 1.3**、クリックして**発行**です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-140">Right-click **Version 1.3**, and then click **Publish**.</span></span>  
  
10. <span data-ttu-id="5e0ee-141">右クリック**Version 1.3**、クリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-141">Right-click **Version 1.3**, and then click **Deploy**.</span></span>  
  
### <a name="to-test-the-solution"></a><span data-ttu-id="5e0ee-142">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-142">To test the solution</span></span>  
  
1.  <span data-ttu-id="5e0ee-143">をクリックして**開始**、開かれている**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-143">Click **Start**, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="5e0ee-144">BizTalk Server 管理コンソールを既に開いている場合は、F5 キーを押して更新します。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-144">If you have the BizTalk Server Administration console already open, press F5 to refresh it.</span></span>  
  
2.  <span data-ttu-id="5e0ee-145">右クリック**RuleTestApp**、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-145">Right-click **RuleTestApp**, and then click **Start**.</span></span> <span data-ttu-id="5e0ee-146">場合**開始**は無効にすると、アプリケーションが既に実行されていると、次の手順を無視することができます。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-146">If **Start** is disabled, the application is already running and you can ignore the next step.</span></span>  
  
3.  <span data-ttu-id="5e0ee-147">をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-147">Click **Start**.</span></span>  
  
4.  <span data-ttu-id="5e0ee-148">コピー、 **SamplePO2.xml**オーケストレーション用の C:\BRE-Walkthroughs\RuleTestSol\Input ディレクトリに C:\BRE-Walkthroughs ディレクトリからファイルです。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-148">Copy the **SamplePO2.xml** file from the C:\BRE-Walkthroughs directory to the C:\BRE-Walkthroughs\RuleTestSol\Input directory for the orchestration.</span></span>  
  
5.  <span data-ttu-id="5e0ee-149">C:\BRE-Walkthroughs\RuleTestSol\Output ディレクトリに出力ファイルができます。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-149">You should see an output file in the C:\BRE-Walkthroughs\RuleTestSol\Output directory.</span></span> <span data-ttu-id="5e0ee-150">出力 XML ファイルを開くことを確認の値、**ステータス**にフィールドが設定されている**Approved**です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-150">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5e0ee-151">値、**数量**SamplePO2.xml のフィールドが 700 です。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-151">The value of the **Quantity** field in SamplePO2.xml is 700.</span></span> <span data-ttu-id="5e0ee-152">バージョン 1.3、 **ProcessPurchaseOrder**ポリシーは、この値は、バージョン 1.2 と同様、500 と比較することではなく 1000 とを比較します。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-152">Version 1.3 of the **ProcessPurchaseOrder** policy compares this value with 1000 instead of comparing it with 500 as version 1.2 did.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="5e0ee-153">コメント</span><span class="sxs-lookup"><span data-stu-id="5e0ee-153">Comments</span></span>  
  
-   <span data-ttu-id="5e0ee-154">公開済みのポリシーは変更できません。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-154">A published policy cannot be modified.</span></span> <span data-ttu-id="5e0ee-155">変更するには、新しいバージョンのポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-155">You must create a new version of the policy to modify it.</span></span> <span data-ttu-id="5e0ee-156">同様に、公開済みのボキャブラリは変更できません。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-156">Similarly, a published vocabulary cannot be modified.</span></span> <span data-ttu-id="5e0ee-157">変更するには、新しいバージョンのボキャブラリを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-157">You must create a new version of the vocabulary to modify it.</span></span>  
  
-   <span data-ttu-id="5e0ee-158">使用してポリシーを呼び出すオーケストレーション、**ルールの呼び出し**図形を展開した最新バージョンのポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-158">The orchestration invoking a policy by using the **Call Rules** shape uses the latest deployed version of the policy.</span></span> <span data-ttu-id="5e0ee-159">たとえば、展開済みのポリシーのバージョンが 1.0、1.1、1.2、および 1.3 の場合は、オーケストレーションはバージョン 1.3 を使用します。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-159">For example, if you have versions 1.0, 1.1, 1.2, and 1.3 of the policy deployed, the orchestration uses version 1.3.</span></span> <span data-ttu-id="5e0ee-160">バージョン 1.3 が展開されておらず、バージョン 1.2 が展開されている場合は、オーケストレーションはバージョン 1.2 を使用します。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-160">If version 1.3 is not deployed and version 1.2 is deployed, the orchestration uses version 1.2.</span></span> <span data-ttu-id="5e0ee-161">したがって、バージョン 1.2 を使用する必要がある場合は、バージョン 1.3 を展開解除し、バージョン 1.2 が展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-161">Therefore if you want to switch back to using version 1.2, you just need to undeploy version 1.3, and make sure that version 1.2 is deployed.</span></span>  
  
-   <span data-ttu-id="5e0ee-162">オーケストレーションからポリシーの特定のバージョンを使用する必要がありますを使用する、**式**図形し、ポリシーを使用してプログラムで実行するルール エンジンを呼び出して、 **Policy.Execute**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-162">To use a specific version of a policy from an orchestration, you should use an **Expression** shape and invoke the rule engine to execute the policy programmatically by using the **Policy.Execute** method.</span></span>  
  
-   <span data-ttu-id="5e0ee-163">ポリシーのバージョン 1.3 は、バージョン 1.0 およびバージョン 1.1 の POVocabulary ボキャブラリのボキャブラリ定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-163">Note that version 1.3 of the policy uses the vocabulary definitions from both version 1.0 and version 1.1 of the POVocabulary vocabulary.</span></span> <span data-ttu-id="5e0ee-164">バージョン 1.3 のポリシーを XML ファイルにエクスポートし、別のコンピューター上でインポートしてポリシーを作成する場合、インポート処理では両方のバージョンのボキャブラリを探します。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-164">If you export version 1.3 of the policy to an XML file, and import it to create the policy on a different computer, the import process looks for both versions of the vocabulary.</span></span> <span data-ttu-id="5e0ee-165">そのため、バージョン 1.0 とバージョン 1.1 のボキャブラリをエクスポートし、バージョン 1.3 のポリシーをインポートする前にインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-165">Therefore you need to export both version 1.0 and version 1.1 of the vocabulary and import them before importing version 1.3 of the policy.</span></span>  
  
-   <span data-ttu-id="5e0ee-166">新しいバージョンのポリシーを展開した後、ソリューションをテストする前に約 60 秒間待つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-166">After you deploy a newer version of the policy, you should wait approximately 60 seconds before testing the solution.</span></span> <span data-ttu-id="5e0ee-167">ルール エンジン更新サービスは、既定では 60 秒 (1 分) ごとにポリシーの更新を確認します。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-167">The rule engine update service looks for any updates to a policy every 60 seconds (1 minute) by default.</span></span> <span data-ttu-id="5e0ee-168">更新があると、キャッシュの情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-168">If there are updates, it refreshes the cache with the updated information.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5e0ee-169">次の手順</span><span class="sxs-lookup"><span data-stu-id="5e0ee-169">Next Steps</span></span>  
  
-   <span data-ttu-id="5e0ee-170">これで、このチュートリアルを完了すると、実行、[チュートリアル: ポリシーの実行を追跡](../core/walkthrough-tracking-policy-execution.md)ポリシー実行の詳細を追跡するための手順を説明するチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="5e0ee-170">Now that you have completed this walkthrough, perform the [Walkthrough: Tracking Policy Execution](../core/walkthrough-tracking-policy-execution.md) walkthrough, which gives you step-by-step instructions for tracking policy execution details.</span></span>