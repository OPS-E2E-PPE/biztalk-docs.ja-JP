---
title: 'チュートリアル: を作成して、ポリシーで、ボキャブラリを使用して |Microsoft Docs'
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2c306a6e-3384-4f43-9c75-c5407cd9aed2
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92a2f458d3ae4aa43befff248d564c92d78ef132
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974771"
---
# <a name="walkthrough-creating-and-using-a-vocabulary-in-the-policy"></a><span data-ttu-id="4b72b-102">チュートリアル: を作成して、ポリシーで、ボキャブラリを使用します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-102">Walkthrough: Creating and Using a Vocabulary in the Policy</span></span>
<span data-ttu-id="4b72b-103">このチュートリアルでは、ボキャブラリを作成すると、では、ボキャブラリを使用してステップ バイ ステップ、 **ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="4b72b-103">This walkthrough provides step-by-step procedures for creating a vocabulary and using the vocabulary in the **ProcessPurchaseOrder** policy.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4b72b-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="4b72b-104">Prerequisites</span></span>  
 <span data-ttu-id="4b72b-105">完了する必要があります、[チュートリアル: 単純なビジネス ポリシーを作成する](../core/walkthrough-creating-a-simple-business-policy.md)このチュートリアルを実行する前にチュートリアル。</span><span class="sxs-lookup"><span data-stu-id="4b72b-105">You must complete the [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md) walkthrough before performing this walkthrough.</span></span> <span data-ttu-id="4b72b-106">ただし、このドキュメントでここまでに記載されていたチュートリアルについては、すべて完了しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4b72b-106">However, we recommend that you complete all the walkthroughs that are listed before this walkthrough in the documentation.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="4b72b-107">このチュートリアルの概要</span><span class="sxs-lookup"><span data-stu-id="4b72b-107">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="4b72b-108">次の表に示すように、このチュートリアルには 3 つの手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b72b-108">This walkthrough contains three procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="4b72b-109">プロシージャ タイトル</span><span class="sxs-lookup"><span data-stu-id="4b72b-109">Procedure title</span></span>|<span data-ttu-id="4b72b-110">プロシージャ descritpion</span><span class="sxs-lookup"><span data-stu-id="4b72b-110">Procedure descritpion</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="4b72b-111">POVocabulary ボキャブラリを作成するには</span><span class="sxs-lookup"><span data-stu-id="4b72b-111">To create the POVocabulary vocabulary</span></span>|<span data-ttu-id="4b72b-112">作成するための手順について説明します、 **POVocabulary** 3 つの定義をボキャブラリ: 要求された数量、最大の指定できるアイテム数、および要求の状態。</span><span class="sxs-lookup"><span data-stu-id="4b72b-112">Provides step-by-step instructions for creating the **POVocabulary** vocabulary with three definitions: Requested Quantity, Maximum Number of Items Allowed, and Request Status.</span></span>|  
|<span data-ttu-id="4b72b-113">ProcessPurchaseOrder ポリシーで POVocabulary を使用するには</span><span class="sxs-lookup"><span data-stu-id="4b72b-113">To use the POVocabulary in the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="4b72b-114">新しいバージョンを作成するための手順について説明します、 **ProcessPurchaseOrder**ポリシーを使用して**POVocabulary**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-114">Provides step-by-step instructions for creating a new version of the **ProcessPurchaseOrder** policy using **POVocabulary**.</span></span>|  
|<span data-ttu-id="4b72b-115">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4b72b-115">To test the solution</span></span>|<span data-ttu-id="4b72b-116">ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="4b72b-116">Provides step-by-step instructions for testing the solution.</span></span>|  
  
### <a name="to-create-the-povocabulary-vocabulary"></a><span data-ttu-id="4b72b-117">POVocabulary ボキャブラリを作成するには</span><span class="sxs-lookup"><span data-stu-id="4b72b-117">To create the POVocabulary vocabulary</span></span>  
  
1.  <span data-ttu-id="4b72b-118">**開始**] メニューの [open**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-118">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="4b72b-119">ビジネス ルール作成ツールを既に開いている場合は、F5 キーを押して更新します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-119">If you have the Business Rule Composer already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4b72b-120">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="4b72b-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="4b72b-121">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-121">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="4b72b-122">[ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**タブ。</span><span class="sxs-lookup"><span data-stu-id="4b72b-122">In the Facts Explorer window, click the **Vocabularies** tab.</span></span>  
  
3.  <span data-ttu-id="4b72b-123">右クリック**ボキャブラリ**、 をクリックして**新しいボキャブラリの追加**、し、入力**POVocabulary**として、ボキャブラリの名前。</span><span class="sxs-lookup"><span data-stu-id="4b72b-123">Right-click **Vocabularies**, click **Add New Vocabulary**, and then type **POVocabulary** as the name for the vocabulary.</span></span>  
  
4.  <span data-ttu-id="4b72b-124">手順 3. でを POVocabulary ボキャブラリの名前を変更しなかった場合に、ボキャブラリの名前を変更**POVocabulary**プロパティ ウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="4b72b-124">If you did not change the name of the vocabulary to POVocabulary in step 3, change the name of the vocabulary to **POVocabulary**in the Properties window.</span></span>  
  
5.  <span data-ttu-id="4b72b-125">右クリック**バージョン 1.0 (未保存)** で**POVocabulary**、 をクリックし、**新しい定義の追加**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-125">Right-click **Version 1.0(not saved)** in **POVocabulary**, and then click **Add New Definition**.</span></span>  
  
6.  <span data-ttu-id="4b72b-126">ボキャブラリの定義ウィザードで選択**XML ドキュメントの要素または属性**、 をクリックし、**次**。</span><span class="sxs-lookup"><span data-stu-id="4b72b-126">In the Vocabulary Definition Wizard, select **XML Document Element or Attribute**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="4b72b-127">**定義名**、型**要求された数量**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-127">For the **Definition name**, type **Requested Quantity**.</span></span>  
  
8.  <span data-ttu-id="4b72b-128">をクリックして**参照**を選択し、 **PO.xsd**ファイルで作成した[チュートリアル: 単純なビジネス ポリシーを作成する](../core/walkthrough-creating-a-simple-business-policy.md)します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-128">Click **Browse**, and select the **PO.xsd** file you created in [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md).</span></span>  
  
9. <span data-ttu-id="4b72b-129">**バインドの選択** ダイアログ ボックスで、展開**PurchaseOrder**、展開**項目**、し、ダブルクリック**数量**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-129">In the **Select Binding** dialog box, expand **PurchaseOrder**, expand **Item**, and then double-click **Quantity**.</span></span>  
  
10. <span data-ttu-id="4b72b-130">必ず、**ドキュメントの種類**に設定されている**RuleTest.PO**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-130">Make sure that the **document type** is set to **RuleTest.PO**.</span></span> <span data-ttu-id="4b72b-131">そうでない場合、ドキュメントの種類を RuleTest.PO に変更します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-131">If it is not, change the document type to RuleTest.PO.</span></span> <span data-ttu-id="4b72b-132">この手順は非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="4b72b-132">This step is very important.</span></span>  
  
     <span data-ttu-id="4b72b-133">![BRE&#45;チュートリアル&#45;ChangeDocType2](../core/media/090f0bce-0594-4a67-87d0-3cd22fbb1796.gif "090f0bce-0594-4a67-87d0-3cd22fbb1796")</span><span class="sxs-lookup"><span data-stu-id="4b72b-133">![BRE&#45;Walkthrough&#45;ChangeDocType2](../core/media/090f0bce-0594-4a67-87d0-3cd22fbb1796.gif "090f0bce-0594-4a67-87d0-3cd22fbb1796")</span></span>  
  
11. <span data-ttu-id="4b72b-134">指定、**操作を選択して**で、**操作の選択**グループとして**Get 操作の実行**。</span><span class="sxs-lookup"><span data-stu-id="4b72b-134">Specify the **select operation** in the **Select operation** group as **Perform Get Operation**.</span></span>  
  
     <span data-ttu-id="4b72b-135">![BRE&#45;チュートリアル&#45;SelectGet](../core/media/3034649a-2d81-4f08-8044-3ab66a201672.gif "3034649a-2d81-4f08-8044-3ab66a201672")</span><span class="sxs-lookup"><span data-stu-id="4b72b-135">![BRE&#45;Walkthrough&#45;SelectGet](../core/media/3034649a-2d81-4f08-8044-3ab66a201672.gif "3034649a-2d81-4f08-8044-3ab66a201672")</span></span>  
  
12. <span data-ttu-id="4b72b-136">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b72b-136">Click **Finish**.</span></span>  
  
13. <span data-ttu-id="4b72b-137">右クリック**バージョン 1.0 (未保存)**、 をクリックし、**新しい定義の追加**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-137">Right-click **Version 1.0(not saved)**, and then click **Add New Definition**.</span></span>  
  
14. <span data-ttu-id="4b72b-138">選択**XML ドキュメントの要素または属性**、 をクリックし、**次**。</span><span class="sxs-lookup"><span data-stu-id="4b72b-138">Select **XML Document Element or Attribute**, and then click **Next**.</span></span>  
  
15. <span data-ttu-id="4b72b-139">**定義名**、型**要求の状態**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-139">For the **Definition name**, type **Request Status**.</span></span>  
  
16. <span data-ttu-id="4b72b-140">クリックして**参照**を選択し、 **PO.xsd**ファイル。</span><span class="sxs-lookup"><span data-stu-id="4b72b-140">Click **Browse**, and select the **PO.xsd** file.</span></span>  
  
17. <span data-ttu-id="4b72b-141">**バインドの選択** ダイアログ ボックスで、展開**PurchaseOrder**、し、ダブルクリック**状態**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-141">In the **Select Binding** dialog box, expand **PurchaseOrder**, and then double-click **Status**.</span></span>  
  
18. <span data-ttu-id="4b72b-142">変更、**ドキュメントの種類**に**RuleTest.PO**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-142">Change the **document type** to **RuleTest.PO**.</span></span> <span data-ttu-id="4b72b-143">この手順は非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="4b72b-143">This step is very important.</span></span>  
  
19. <span data-ttu-id="4b72b-144">確認します、**操作の実行設定**オプションが選択されているし、クリックして **[次へ]。**</span><span class="sxs-lookup"><span data-stu-id="4b72b-144">Make sure that the  **Perform Set operation** option is selected, and then click **Next.**</span></span>  
  
20. <span data-ttu-id="4b72b-145">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b72b-145">Click **Finish**.</span></span>  
  
21. <span data-ttu-id="4b72b-146">右クリック**バージョン 1.0 (未保存)**、 をクリックし、**新しい定義の追加**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-146">Right-click **Version 1.0(not saved)**, and then click **Add New Definition**.</span></span>  
  
22. <span data-ttu-id="4b72b-147">確認します**定数値、値の範囲、または値セットの**が選択されているし、をクリックし、**次**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-147">Make sure that **Constant Value, Range of Values, or Set of Values** is selected, and then click **Next**.</span></span>  
  
23. <span data-ttu-id="4b72b-148">**定義名**、型**最大の指定できるアイテム数**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-148">For the **Definition name**, type **Maximum Number of Items Allowed**.</span></span>  
  
24. <span data-ttu-id="4b72b-149">確認します**定数値の定義の種類**が選択されているし、をクリックし、**次**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-149">Make sure that **Constant Value definition type** is selected, and then click **Next**.</span></span>  
  
25. <span data-ttu-id="4b72b-150">型**500**値、およびクリック**完了**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-150">Type **500** for the value, and then click **Finish**.</span></span>  
  
26. <span data-ttu-id="4b72b-151">右クリック**バージョン 1.0 (未保存)**、 をクリックし、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-151">Right-click **Version 1.0(not saved)**, and then click **Save**.</span></span>  
  
27. <span data-ttu-id="4b72b-152">右クリック**バージョン 1.0 (未保存)**、 をクリックし、**発行**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-152">Right-click **Version 1.0(not saved)**, and then click **Publish**.</span></span>  
  
### <a name="to-use-the-povocabulary-in-the-processpurchaseorder-policy"></a><span data-ttu-id="4b72b-153">ProcessPurchaseOrder ポリシーで POVocabulary を使用するには</span><span class="sxs-lookup"><span data-stu-id="4b72b-153">To use the POVocabulary in the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="4b72b-154">ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、展開**ProcessPurchaseOrder**、右クリック**バージョン 1.0**、順にクリックします**コピー**.</span><span class="sxs-lookup"><span data-stu-id="4b72b-154">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.0**, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="4b72b-155">右クリック**ProcessPurchaseOrder**  をクリックし、**ポリシーのバージョンの貼り付け**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-155">Right-click **ProcessPurchaseOrder** and then click **Paste Policy Version**.</span></span>  
  
3.  <span data-ttu-id="4b72b-156">クリックして**ApprovalRule**で**バージョン 1.1 (未保存)** します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-156">Click **ApprovalRule** in **Version 1.1(not saved)**.</span></span>  
  
4.  <span data-ttu-id="4b72b-157">ファクト エクスプ ローラー ウィンドウで、**ボキャブラリ**、展開**POVocabulary**、展開**バージョン 1.0**、し、ドラッグ**要求された数量**LessThanOrEqual の述語の左側 (lhs) 引数の置換を IF ペインにします。</span><span class="sxs-lookup"><span data-stu-id="4b72b-157">In the Facts Explorer window, expand **Vocabularies**, expand **POVocabulary**, expand **Version 1.0**, and then drag **Requested Quantity** to the IF pane to replace the left hand side (LHS) argument of the LessThanOrEqual predicate.</span></span>  
  
     <span data-ttu-id="4b72b-158">![BRE&#45;チュートリアル&#45;DragReqQty](../core/media/f5ec8bca-344e-4099-a347-0a2298a3f088.gif "f5ec8bca-344e-4099-a347-0a2298a3f088")</span><span class="sxs-lookup"><span data-stu-id="4b72b-158">![BRE&#45;Walkthrough&#45;DragReqQty](../core/media/f5ec8bca-344e-4099-a347-0a2298a3f088.gif "f5ec8bca-344e-4099-a347-0a2298a3f088")</span></span>  
  
     <span data-ttu-id="4b72b-159">![BRE&#45;チュートリアル&#45;ReqQty](../core/media/7afddd71-31ce-4868-94c1-d7ffd81f1e47.gif "7afddd71-31ce-4868-94c1-d7ffd81f1e47")</span><span class="sxs-lookup"><span data-stu-id="4b72b-159">![BRE&#45;Walkthrough&#45;ReqQty](../core/media/7afddd71-31ce-4868-94c1-d7ffd81f1e47.gif "7afddd71-31ce-4868-94c1-d7ffd81f1e47")</span></span>  
  
5.  <span data-ttu-id="4b72b-160">ドラッグ**最大の指定できるアイテム数**条件の右側 (rhs) の引数を置き換える (**500**)。</span><span class="sxs-lookup"><span data-stu-id="4b72b-160">Drag **Maximum Number of Items Allowed** to replace the right hand side (RHS) argument of the condition (**500**).</span></span>  
  
6.  <span data-ttu-id="4b72b-161">[THEN] ペイン、右クリックし、クリックで既存のアクションを選択します。**アクションの削除**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-161">Select the existing action in the THEN pane, right-click, and then click **Delete action**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4b72b-162">アクションを選択してから Del キーを押して削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="4b72b-162">You can also press DELETE after selecting the action to delete the action.</span></span>  
  
7.  <span data-ttu-id="4b72b-163">ドラッグ**要求の状態**を**し**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="4b72b-163">Drag **Request Status** to the **THEN** pane.</span></span>  
  
8.  <span data-ttu-id="4b72b-164">クリックして**\<空の文字列\>** し、入力**Approved**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-164">Click **\<empty string\>** and then type **Approved**.</span></span>  
  
9. <span data-ttu-id="4b72b-165">右クリック**バージョン 1.1 (未保存)** ポリシー エクスプ ローラー ウィンドウでクリック**保存**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-165">Right-click **Version 1.1(not saved)** in the Policy Explorer window, and then click **Save**.</span></span>  
  
10. <span data-ttu-id="4b72b-166">右クリック**バージョン 1.1 (未保存)** ポリシー エクスプ ローラー ウィンドウでクリック**発行**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-166">Right-click **Version 1.1(not saved)** in the Policy Explorer window, and then click **Publish**.</span></span>  
  
### <a name="to-test-the-solution"></a><span data-ttu-id="4b72b-167">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4b72b-167">To test the solution</span></span>  
  
1.  <span data-ttu-id="4b72b-168">ビジネス ルール作成ツールで展開**ポリシー**、展開**ProcessPurchaseOrder**、右クリックして**バージョン 1.0 - 展開済み**、順にクリックします**展開解除**.</span><span class="sxs-lookup"><span data-stu-id="4b72b-168">In Business Rule Composer, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.0 - Deployed**, and then click **Undeploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4b72b-169">オーケストレーションでは、常に最後に展開されたポリシーのバージョン、つまり、手順 2. を実行した後のバージョン 1.1 が取得されるため、この手順は省略できます。</span><span class="sxs-lookup"><span data-stu-id="4b72b-169">This step is optional because the orchestration always picks the latest deployed version of the policy, which is 1.1 after you perform step 2.</span></span>  
  
2.  <span data-ttu-id="4b72b-170">右クリック**バージョン 1.1-公開**、 をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-170">Right-click **Version 1.1- Published**, and then click **Deploy**.</span></span>  
  
3.  <span data-ttu-id="4b72b-171">程度待ちます**60**秒。</span><span class="sxs-lookup"><span data-stu-id="4b72b-171">Wait for approximately **60** seconds.</span></span> <span data-ttu-id="4b72b-172">キャッシュされたポリシーに変更があった場合は、ルール エンジン更新サービスによって 60 秒ごとにキャッシュが更新されています。</span><span class="sxs-lookup"><span data-stu-id="4b72b-172">The rule engine update service refreshes its cache every 60 seconds if there are any updates to a policy that it caches.</span></span> <span data-ttu-id="4b72b-173">これは、手順 1. を実行したかどうかには関係ありません。オーケストレーションは、最後に展開されたポリシーのバージョン、つまり、バージョン 1.1 を取得します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-173">It does not matter whether you perform step 1—the orchestration picks up the latest deployed version of the policy, which is 1.1</span></span>  
  
4.  <span data-ttu-id="4b72b-174">開いている**SamplePO.xml**と**SamplePO2.xml**メモ帳での値を変更し、**状態**フィールドを**XYZ**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-174">Open **SamplePO.xml** and **SamplePO2.xml** in Notepad and change the value of the **Status** field to **XYZ**.</span></span>  
  
5.  <span data-ttu-id="4b72b-175">コピー、 **SamplePO.xml**オーケストレーション用の C:\BRE-Walkthroughs\RuleTestSol\Input ディレクトリに C:\BRE-Walkthroughs ディレクトリからファイル。</span><span class="sxs-lookup"><span data-stu-id="4b72b-175">Copy the **SamplePO.xml** file from C:\BRE-Walkthroughs directory to C:\BRE-Walkthroughs\RuleTestSol\Input directory for the orchestration.</span></span>  
  
6.  <span data-ttu-id="4b72b-176">オーケストレーションの C:\BRE-Walkthroughs\RuleTestSol\Output ディレクトリに出力ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b72b-176">You should see an output file in the C:\BRE-Walkthroughs\RuleTestSol\Output directory for the orchestration.</span></span> <span data-ttu-id="4b72b-177">出力 XML ファイルを開き、注意の値、**状態**にフィールドが設定されている**Approved**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-177">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
7.  <span data-ttu-id="4b72b-178">手順 5. と 6. を繰り返します**SamplePO2.xml**、いることを確認しの値、**状態**出力ドキュメント内のフィールドは、入力ドキュメントと同じ (**XYZ**)。</span><span class="sxs-lookup"><span data-stu-id="4b72b-178">Repeat steps 5 and 6 with **SamplePO2.xml**, and notice that the value of the **Status** field in the output document is the same as in the input document (**XYZ**).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4b72b-179">値、**状態**フィールド、ルール エンジンがアクションを実行していないため、同じ (XYZ) のまま、 **ApprovalRule**規則条件評価のため`false`します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-179">The value of the **Status** field remains the same (XYZ) because the rule engine does not execute the action in the **ApprovalRule** rule because the condition evaluated to `false`.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="4b72b-180">コメント</span><span class="sxs-lookup"><span data-stu-id="4b72b-180">Comments</span></span>  
  
- <span data-ttu-id="4b72b-181">ボキャブラリは、保存した後も変更できます。</span><span class="sxs-lookup"><span data-stu-id="4b72b-181">After you save the vocabulary, you can still modify it.</span></span> <span data-ttu-id="4b72b-182">公開した後は変更できません。</span><span class="sxs-lookup"><span data-stu-id="4b72b-182">After you publish the vocabulary, you cannot modify it.</span></span>  
  
- <span data-ttu-id="4b72b-183">定義の変更、新しい定義の追加、または定義の削除が必要になった場合は、ボキャブラリの新しいバージョンを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b72b-183">If you need to modify a definition, add a new definition, or delete a definition, you should create a new version of the vocabulary.</span></span>  
  
- <span data-ttu-id="4b72b-184">ポリシーでは、公開されたボキャブラリだけを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b72b-184">Only published vocabularies can be used in policies.</span></span>  
  
- <span data-ttu-id="4b72b-185">「POVocabulary ボキャブラリを作成するには」の手順でドキュメント種類を変更した**RuleTest.PO**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-185">In the "To create the POVocabulary vocabulary" procedure, you changed the document type to **RuleTest.PO**.</span></span> <span data-ttu-id="4b72b-186">この変更の結果を表示する[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーでクリックして**PO.xsd**します。</span><span class="sxs-lookup"><span data-stu-id="4b72b-186">To see the results of this change, in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], in Solution Explorer, click **PO.xsd**.</span></span> <span data-ttu-id="4b72b-187">[プロパティ] ウィンドウで**RuleTest** 、名前空間の名前を指定し、 **PO**の名前を指定、**型**。</span><span class="sxs-lookup"><span data-stu-id="4b72b-187">In the Properties window, note that **RuleTest** is the name of the namespace, and **PO** is the name of the **Type**.</span></span>  
  
- <span data-ttu-id="4b72b-188">このチュートリアルでは、ポリシーのファクトとして XML ドキュメントのみを使用しました。</span><span class="sxs-lookup"><span data-stu-id="4b72b-188">In this walkthrough, you used only an XML document as a fact to the policy.</span></span> <span data-ttu-id="4b72b-189">ポリシーの作成には、.NET のファクトやデータベースのファクトを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="4b72b-189">You can also use .NET facts and database facts when you create policies</span></span>  
  
- <span data-ttu-id="4b72b-190">選択すると **「設定」操作の実行**ボキャブラリの定義ウィザードの 2 番目のページで指定できます、**表示書式文字列**で次のページ。</span><span class="sxs-lookup"><span data-stu-id="4b72b-190">When you select **Perform "Set" operation** on the second page of the Vocabulary Definition Wizard, you can specify a **Display format string** on the page that follows.</span></span> <span data-ttu-id="4b72b-191">表示形式文字列を変更するなど、**要求の状態{0}** に**要求の状態: {0}** クリックする前に**完了**でボキャブラリの作成」の手順の手順 20 です。</span><span class="sxs-lookup"><span data-stu-id="4b72b-191">For example, you could change the display format string from **Request Status {0}** to **Request status is: {0}** before clicking **Finish** in the step 20 of the "create vocabulary" procedure.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4b72b-192">次の手順</span><span class="sxs-lookup"><span data-stu-id="4b72b-192">Next Steps</span></span>  
 <span data-ttu-id="4b72b-193">これで、このチュートリアルを完了すると、実行、[チュートリアル: ポリシーにルールを追加する](../core/walkthrough-adding-a-rule-to-the-policy.md)する新しい規則を追加する手順を説明するチュートリアル、 **ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="4b72b-193">Now that you have completed this walkthrough, perform the [Walkthrough: Adding a Rule to the Policy](../core/walkthrough-adding-a-rule-to-the-policy.md) walkthrough, which gives you step-by-step instructions for adding a new rule to the **ProcessPurchaseOrder** policy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b72b-194">参照</span><span class="sxs-lookup"><span data-stu-id="4b72b-194">See Also</span></span>  
 <span data-ttu-id="4b72b-195">[ボキャブラリ](../core/vocabularies.md) </span><span class="sxs-lookup"><span data-stu-id="4b72b-195">[Vocabularies](../core/vocabularies.md) </span></span>  
 <span data-ttu-id="4b72b-196">[ボキャブラリを作成する方法](../core/how-to-develop-vocabularies.md) </span><span class="sxs-lookup"><span data-stu-id="4b72b-196">[How to Develop Vocabularies](../core/how-to-develop-vocabularies.md) </span></span>  
 <span data-ttu-id="4b72b-197">[条件の評価とアクションの実行](../core/condition-evaluation-and-action-execution.md) </span><span class="sxs-lookup"><span data-stu-id="4b72b-197">[Condition Evaluation and Action Execution](../core/condition-evaluation-and-action-execution.md) </span></span>  
 [<span data-ttu-id="4b72b-198">議題と優先度</span><span class="sxs-lookup"><span data-stu-id="4b72b-198">Agenda and Priority</span></span>](../core/agenda-and-priority.md)