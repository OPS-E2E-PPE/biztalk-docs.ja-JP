---
title: "チュートリアル: ポリシーのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53ed915d-0f3a-48ea-bfd5-a1f89b9b689c
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a6f879111a28d5cbf9b2a75c7b3f3b3b865fb38
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-testing-the-policy"></a><span data-ttu-id="fcd17-102">チュートリアル: ポリシーのテスト</span><span class="sxs-lookup"><span data-stu-id="fcd17-102">Walkthrough: Testing the Policy</span></span>
<span data-ttu-id="fcd17-103">このチュートリアルで作成したポリシーをテストするための手順では、[チュートリアル: 単純なビジネス ポリシーを作成する](../core/walkthrough-creating-a-simple-business-policy.md)チュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="fcd17-103">This walkthrough provides step-by-step procedures for testing the policy you created in the [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md) walkthrough.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fcd17-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="fcd17-104">Prerequisites</span></span>  
 <span data-ttu-id="fcd17-105">完了する必要があります、[チュートリアル: 単純なビジネス ポリシーを作成する](../core/walkthrough-creating-a-simple-business-policy.md)チュートリアルのこのチュートリアルを実行する前にします。</span><span class="sxs-lookup"><span data-stu-id="fcd17-105">You must complete the [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md) walkthrough before you perform this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="fcd17-106">このチュートリアルの概要</span><span class="sxs-lookup"><span data-stu-id="fcd17-106">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="fcd17-107">次の表に示すように、このチュートリアルには 2 つの手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fcd17-107">This walkthrough contains two procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="fcd17-108">手順のタイトル</span><span class="sxs-lookup"><span data-stu-id="fcd17-108">Procedure title</span></span>|<span data-ttu-id="fcd17-109">手順の説明</span><span class="sxs-lookup"><span data-stu-id="fcd17-109">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="fcd17-110">テスト ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="fcd17-110">To create the test files</span></span>|<span data-ttu-id="fcd17-111">作成の 2 つのサンプル XML ファイルを 400 は Quantity フィールドの値を持つ 1 つの手順を説明します (\<= 500) と、もう 1 つは Quantity フィールド 700 (> 500) の値。</span><span class="sxs-lookup"><span data-stu-id="fcd17-111">Provides step-by-step instructions for creating two sample XML files, one with the value of the Quantity field as 400 (\<= 500) and the other one with the value of the Quantity field as 700 (> 500).</span></span>|  
|<span data-ttu-id="fcd17-112">ProcessPurchaseOrder ポリシーをテストするには</span><span class="sxs-lookup"><span data-stu-id="fcd17-112">To test the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="fcd17-113">ステップごとの説明に従って、ビジネス ルール作成ツールを使用してポリシーをテストします。</span><span class="sxs-lookup"><span data-stu-id="fcd17-113">Provides step-by-step instructions for testing the policy using Business Rule Composer.</span></span>|  
  
### <a name="to-create-the-test-files"></a><span data-ttu-id="fcd17-114">テスト ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="fcd17-114">To create the test files</span></span>  
  
1.  <span data-ttu-id="fcd17-115">**開始**] メニューの [開いている**メモ帳**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-115">On the **Start** menu, open **Notepad**.</span></span>  
  
2.  <span data-ttu-id="fcd17-116">次の XML をメモ帳にコピーします。</span><span class="sxs-lookup"><span data-stu-id="fcd17-116">Copy the following XML to Notepad:</span></span>  
  
    ```  
    <ns0:PurchaseOrder xmlns:ns0="http://EAISolution.PurchaseOrder">  
      <Header>  
        <ReqID>ReqID_0</ReqID>  
        <Date>Date_0</Date>  
      </Header>  
      <Item>  
        <Description>Description_0</Description>  
        <Quantity>400</Quantity>  
        <UnitPrice>20</UnitPrice>  
      </Item>  
      <Status>XYZ</Status>  
    </ns0:PurchaseOrder>    
    ```  
  
3.  <span data-ttu-id="fcd17-117">**ファイル** メニューのをクリックして**TextFile1.txt に名前を付けて**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-117">On the **File** menu, click **Save TextFile1.txt As**.</span></span>  
  
4.  <span data-ttu-id="fcd17-118">値を変更**名前を付けて保存型**から**テキスト ドキュメント (\*.txt)**に**すべてのファイル**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-118">Change the value for **Save As type** from **Text Documents(\*.txt)** to **All Files**.</span></span>  
  
5.  <span data-ttu-id="fcd17-119">ディレクトリに移動**C:\BRE-Walkthroughs**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-119">Change the directory to **C:\BRE-Walkthroughs**.</span></span>  
  
6.  <span data-ttu-id="fcd17-120">型**SamplePO.xml**の**ファイル名**、クリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-120">Type **SamplePO.xml** for **File name**, and then click **Save**.</span></span>  
  
7.  <span data-ttu-id="fcd17-121">**[ファイル]** メニューの **[新規作成]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcd17-121">On the **File** menu, click **New**.</span></span>  
  
8.  <span data-ttu-id="fcd17-122">次の XML をメモ帳にコピーします。</span><span class="sxs-lookup"><span data-stu-id="fcd17-122">Copy the following XML to Notepad:</span></span>  
  
    ```  
    <ns0:PurchaseOrder xmlns:ns0="http://EAISolution.PurchaseOrder">  
      <Header>  
        <ReqID>ReqID_0</ReqID>  
        <Date>Date_0</Date>  
      </Header>  
      <Item>  
        <Description>Description_0</Description>  
        <Quantity>700</Quantity>  
        <UnitPrice>20</UnitPrice>  
      </Item>  
      <Status>XYZ</Status>  
    </ns0:PurchaseOrder>   
    ```  
  
9. <span data-ttu-id="fcd17-123">**ファイル** メニューのをクリックして**TextFile1.txt に名前を付けて**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-123">On the **File** menu, click **Save TextFile1.txt As**.</span></span>  
  
10. <span data-ttu-id="fcd17-124">値を変更**名前を付けて保存型**から**テキスト ドキュメント (\*.txt)**に**すべてのファイル**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-124">Change the value for **Save As type** from **Text Documents(\*.txt)** to **All Files**.</span></span>  
  
11. <span data-ttu-id="fcd17-125">ディレクトリに移動**C:\BRE-Walkthroughs**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-125">Change the directory to **C:\BRE-Walkthroughs**.</span></span>  
  
12. <span data-ttu-id="fcd17-126">型**SamplePO2.xml**の**ファイル名**、クリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-126">Type **SamplePO2.xml** for **File name**, and then click **Save**.</span></span>  
  
13. <span data-ttu-id="fcd17-127">メモ帳を閉じます。</span><span class="sxs-lookup"><span data-stu-id="fcd17-127">Close Notepad.</span></span>  
  
### <a name="to-test-the-processpurchaseorder-policy"></a><span data-ttu-id="fcd17-128">ProcessPurchaseOrder ポリシーをテストするには</span><span class="sxs-lookup"><span data-stu-id="fcd17-128">To test the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="fcd17-129">**開始**] メニューの [開いている**ビジネス ルール作成ツール**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-129">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="fcd17-130">ある場合は既にを開き、f5 キーを押して更新のビジネス ルール作成ツール。</span><span class="sxs-lookup"><span data-stu-id="fcd17-130">If you have Business Rule Composer already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fcd17-131">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="fcd17-131">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="fcd17-132">これを行うには、アプリケーションを右クリックし、**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-132">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="fcd17-133">ポリシー エクスプ ローラー] ウィンドウで、**ポリシー**、展開**ProcessPurchaseOrder**を右クリックして**バージョン 1.0**、クリックして**[ポリシーのテスト**.</span><span class="sxs-lookup"><span data-stu-id="fcd17-133">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.0**, and then click **Test Policy**.</span></span>  
  
3.  <span data-ttu-id="fcd17-134">**XMLDocuments**ノードで、選択**RuleTest.PO**、クリックして**インスタンスを追加**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-134">In the **XMLDocuments** node, select **RuleTest.PO**, and then click **Add Instance**.</span></span>  
  
     <span data-ttu-id="fcd17-135">![ビジネス ルール作成ツール &#45;TestPolicySelectFacts](../core/media/7115f0d4-0c12-4292-81a5-eb78d62c5543.gif "7115f0d4-0c12-4292-81a5-eb78d62c5543")</span><span class="sxs-lookup"><span data-stu-id="fcd17-135">![Business Rule Composer&#45;TestPolicySelectFacts](../core/media/7115f0d4-0c12-4292-81a5-eb78d62c5543.gif "7115f0d4-0c12-4292-81a5-eb78d62c5543")</span></span>  
  
4.  <span data-ttu-id="fcd17-136">選択、 **SamplePO.xml**クリックしてファイルの前に作成した**開く**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-136">Select the **SamplePO.xml** file that you created earlier, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="fcd17-137">をクリックして**テスト**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-137">Click **Test**.</span></span>  
  
6.  <span data-ttu-id="fcd17-138">出力ウィンドウで出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="fcd17-138">Review the output in the Output window.</span></span> <span data-ttu-id="fcd17-139">表示される出力の説明については、「最初のテスト (samplepo.xml) からの出力の分析」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcd17-139">See the "Analysis of the Output from the First Test (samplepo.xml)" section for an explanation of the output you see.</span></span>  
  
7.  <span data-ttu-id="fcd17-140">開いている**SamplePO.xml**メモ帳で通知の値、**ステータス**フィールドに設定されて**承認済み**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-140">Open **SamplePO.xml** in Notepad and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
8.  <span data-ttu-id="fcd17-141">右クリック**バージョン 1.0**、クリックして**テスト ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-141">Right-click **Version 1.0**, and then click **Test Policy**.</span></span>  
  
9. <span data-ttu-id="fcd17-142">選択**SamplePO.xml**、 をクリックして**削除インスタンス**、クリックして**インスタンスを追加**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-142">Select **SamplePO.xml**, click **Remove instance**, and then click **Add Instance**.</span></span>  
  
10. <span data-ttu-id="fcd17-143">選択、 **SamplePO2.xml**クリックしてファイルの前に作成した**開く**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-143">Select the **SamplePO2.xml** file that you created earlier, and then click **Open**.</span></span>  
  
11. <span data-ttu-id="fcd17-144">をクリックして**テスト**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-144">Click **Test**.</span></span> <span data-ttu-id="fcd17-145">表示される出力の説明については、「2 番目のテスト (samplepo2.xml) からの出力の分析」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcd17-145">See the "Analysis of the Output from the Second Test (samplepo2.xml)" section for an explanation of the output you see.</span></span>  
  
12. <span data-ttu-id="fcd17-146">開く、 **SamplePO2.xml**メモ帳でファイルし、ことに注意しての値、**ステータス**フィールドはまだ**XYZ**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-146">Open the **SamplePO2.xml** file in Notepad and notice that the value of the **Status** field is still **XYZ**.</span></span>  
  
## <a name="analysis-of-the-output-from-the-first-test-samplepoxml"></a><span data-ttu-id="fcd17-147">最初のテスト (samplepo.xml) からの出力の分析</span><span class="sxs-lookup"><span data-stu-id="fcd17-147">Analysis of the Output from the First Test (samplepo.xml)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fcd17-148">出力テキストは太字です。この出力テキストの後に説明が続きます。</span><span class="sxs-lookup"><span data-stu-id="fcd17-148">The output text is bold and the explanation follows the output text.</span></span>  
  
 <span data-ttu-id="fcd17-149">**ルール セットのルール エンジン トレース: ProcessPurchaseOrder 2006/8/31 1時 33分: 10 PM**</span><span class="sxs-lookup"><span data-stu-id="fcd17-149">**RULE ENGINE TRACE for RULESET: ProcessPurchaseOrder 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="fcd17-150">ポリシーの実行に対するルール エンジン トレース**ProcessPurchaseOrder**開始 2006/8/31 1時 33分: 10 PM。</span><span class="sxs-lookup"><span data-stu-id="fcd17-150">The rule engine trace for the execution of policy **ProcessPurchaseOrder** started at 8/31/2006 1:33:10 PM.</span></span>  
  
 <span data-ttu-id="fcd17-151">**ファクト アクティビティ 2006/8/31 1時 33分: 10 PM**</span><span class="sxs-lookup"><span data-stu-id="fcd17-151">**FACT ACTIVITY 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="fcd17-152">**ルール エンジン インスタンス識別子: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="fcd17-152">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="fcd17-153">**ルール セット名: ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="fcd17-153">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="fcd17-154">**操作: アサート**</span><span class="sxs-lookup"><span data-stu-id="fcd17-154">**Operation: Assert**</span></span>  
  
 <span data-ttu-id="fcd17-155">**オブジェクトの種類: TypedXmlDocument:PurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="fcd17-155">**Object Type: TypedXmlDocument:PurchaseOrder**</span></span>  
  
 <span data-ttu-id="fcd17-156">**オブジェクト インスタンス識別子: 14626574**</span><span class="sxs-lookup"><span data-stu-id="fcd17-156">**Object Instance Identifier: 14626574**</span></span>  
  
 <span data-ttu-id="fcd17-157">クリックすると、**テスト**、次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="fcd17-157">When you click **Test**, the following things happen:</span></span>  
  
1.  <span data-ttu-id="fcd17-158">ビジネス ルール作成ツール、 **RuleEngine.Policy**オブジェクトでは、さらに、新しいルール エンジンのインスタンスを作成またはルール エンジン キャッシュからルール エンジン インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="fcd17-158">The Business Rule Composer creates a **RuleEngine.Policy** object, which in turn creates a new rule engine instance or acquires a rule engine instance from the rule engine cache.</span></span>  
  
2.  <span data-ttu-id="fcd17-159">ビジネス ルール作成ツール、 **TypedXmlDocument** SamplePO.xml ファイルに基づいてオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="fcd17-159">The Business Rule Composer creates a **TypedXmlDocument** object based on the SamplePO.xml file.</span></span>  
  
3.  <span data-ttu-id="fcd17-160">ビジネス ルール作成ツールを起動、 **Policy.Execute**メソッドを**TypedXmlDocument**オブジェクトをパラメーターとして。</span><span class="sxs-lookup"><span data-stu-id="fcd17-160">The Business Rule Composer invokes the **Policy.Execute** method with the **TypedXmlDocument** object as a parameter.</span></span>  
  
4.  <span data-ttu-id="fcd17-161">**Policy.Execute**メソッド アサート (追加)、 **TypedXmlDocument**オブジェクトをルール エンジンの作業メモリにファクトとして。</span><span class="sxs-lookup"><span data-stu-id="fcd17-161">The **Policy.Execute** method asserts (adds) the **TypedXmlDocument** object as a fact into the working memory of the rule engine.</span></span>  
  
5.  <span data-ttu-id="fcd17-162">ルール エンジンを使用して、 **TypedXmlDocument**オブジェクトをファクトとしてし、実行、 **ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="fcd17-162">The rule engine uses the **TypedXmlDocument** object as a fact and executes the **ProcessPurchaseOrder** policy.</span></span>  
  
 <span data-ttu-id="fcd17-163">**ファクト アクティビティ 2006/8/31 1時 33分: 10 PM**</span><span class="sxs-lookup"><span data-stu-id="fcd17-163">**FACT ACTIVITY 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="fcd17-164">**ルール エンジン インスタンス識別子: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="fcd17-164">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="fcd17-165">**ルール セット名: ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="fcd17-165">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="fcd17-166">**操作: アサート**</span><span class="sxs-lookup"><span data-stu-id="fcd17-166">**Operation: Assert**</span></span>  
  
 <span data-ttu-id="fcd17-167">**オブジェクトの種類: TypedXmlDocument:PurchaseOrder:/PurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="fcd17-167">**Object Type: TypedXmlDocument:PurchaseOrder:/PurchaseOrder**</span></span>  
  
 <span data-ttu-id="fcd17-168">**オブジェクト インスタンス識別子: 64530307**</span><span class="sxs-lookup"><span data-stu-id="fcd17-168">**Object Instance Identifier: 64530307**</span></span>  
  
 <span data-ttu-id="fcd17-169">**ファクト アクティビティ 2006/8/31 1時 33分: 10 PM**</span><span class="sxs-lookup"><span data-stu-id="fcd17-169">**FACT ACTIVITY 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="fcd17-170">**ルール エンジン インスタンス識別子: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="fcd17-170">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="fcd17-171">**ルール セット名: ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="fcd17-171">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="fcd17-172">**操作: アサート**</span><span class="sxs-lookup"><span data-stu-id="fcd17-172">**Operation: Assert**</span></span>  
  
 <span data-ttu-id="fcd17-173">**オブジェクトの種類: TypedXmlDocument:PurchaseOrder: PurchaseOrder/項目**</span><span class="sxs-lookup"><span data-stu-id="fcd17-173">**Object Type: TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item**</span></span>  
  
 <span data-ttu-id="fcd17-174">**オブジェクト インスタンス識別子: 43901854**</span><span class="sxs-lookup"><span data-stu-id="fcd17-174">**Object Instance Identifier: 43901854**</span></span>  
  
1.  <span data-ttu-id="fcd17-175">ルール エンジンを決定する子**TypedXmlDocument**規則で定義された XPath セレクターに基づいてオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="fcd17-175">The rule engine determines which child **TypedXmlDocument** objects to create based on the XPath selectors defined in the rules.</span></span> <span data-ttu-id="fcd17-176">ビジネス ルール作成ツールでルールを構築するときに、XPath セレクターの既定値で選択したノード上のノードに、 **XML スキーマ**ファクト エクスプ ローラー タブ。</span><span class="sxs-lookup"><span data-stu-id="fcd17-176">When you build rules in the Business Rule Composer, the XPath selector value defaults to the node above the node selected in the **XML Schemas** tab in Facts Explorer.</span></span> <span data-ttu-id="fcd17-177">[XPath フィールド] の既定値は選択したノード自体になり、親ノードに関連しています。</span><span class="sxs-lookup"><span data-stu-id="fcd17-177">The XPath field value defaults to the selected node itself, relative to its parent node.</span></span> <span data-ttu-id="fcd17-178">ただし、選択したノードに子がある場合は、選択したノードを指すために XPath セレクター バインドだけが作成され、XPath フィールド バインドは作成されません。</span><span class="sxs-lookup"><span data-stu-id="fcd17-178">However, if the node you selected has children, only an XPath selector binding is created to point to the node that you selected, and no XPath field binding is created.</span></span>  
  
2.  <span data-ttu-id="fcd17-179">次の表は、XPath セレクターおよび XPath フィールド バインド フィールドの値をで使用される、 **ProcessPurchaseOrder**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="fcd17-179">The following table shows the XPath Selector and XPath Field binding values for the fields used in the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="fcd17-180">(このポリシーには ApprovalRule というルールが 1 つだけあります)。</span><span class="sxs-lookup"><span data-stu-id="fcd17-180">(The policy has only one rule, ApprovalRule.)</span></span>  
  
|<span data-ttu-id="fcd17-181">[フィールド名]</span><span class="sxs-lookup"><span data-stu-id="fcd17-181">Field name</span></span>|<span data-ttu-id="fcd17-182">[XPath セレクター]</span><span class="sxs-lookup"><span data-stu-id="fcd17-182">XPath Selector</span></span>|<span data-ttu-id="fcd17-183">[XPath フィールド]</span><span class="sxs-lookup"><span data-stu-id="fcd17-183">XPath Field</span></span>|<span data-ttu-id="fcd17-184">[XPath セレクター] (簡略化された形式)</span><span class="sxs-lookup"><span data-stu-id="fcd17-184">XPath Selector (simplified form)</span></span>|<span data-ttu-id="fcd17-185">[XPath フィールド]</span><span class="sxs-lookup"><span data-stu-id="fcd17-185">XPath Field</span></span><br /><br /> <span data-ttu-id="fcd17-186">(簡略化された形式)</span><span class="sxs-lookup"><span data-stu-id="fcd17-186">(simplified form)</span></span>|  
|----------------|--------------------|-----------------|----------------------------------------|-----------------------------------------|  
|<span data-ttu-id="fcd17-187">Quantity</span><span class="sxs-lookup"><span data-stu-id="fcd17-187">Quantity</span></span>|<span data-ttu-id="fcd17-188">/* [ローカル名 () = 'PurchaseOrder' and namespace-uri() = 'http://EAISolution.PurchaseOrder']/\*[ローカル名 () 'Item' and namespace-uri() = = ']</span><span class="sxs-lookup"><span data-stu-id="fcd17-188">/*[local-name()='PurchaseOrder' and namespace-uri()='http://EAISolution.PurchaseOrder']/\*[local-name()='Item' and namespace-uri()='']</span></span>|<span data-ttu-id="fcd17-189">*[local-name()='Quantity' and namespace-uri()='']</span><span class="sxs-lookup"><span data-stu-id="fcd17-189">*[local-name()='Quantity' and namespace-uri()='']</span></span>|<span data-ttu-id="fcd17-190">/PurchaseOrder/Item</span><span class="sxs-lookup"><span data-stu-id="fcd17-190">/PurchaseOrder/Item</span></span>|<span data-ttu-id="fcd17-191">Quantity</span><span class="sxs-lookup"><span data-stu-id="fcd17-191">Quantity</span></span>|  
|<span data-ttu-id="fcd17-192">[状態]</span><span class="sxs-lookup"><span data-stu-id="fcd17-192">Status</span></span>|<span data-ttu-id="fcd17-193">/*[local-name()='PurchaseOrder' and namespace-uri()='http://EAISolution.PurchaseOrder']</span><span class="sxs-lookup"><span data-stu-id="fcd17-193">/*[local-name()='PurchaseOrder' and namespace-uri()='http://EAISolution.PurchaseOrder']</span></span>|<span data-ttu-id="fcd17-194">*[local-name()='Status' and namespace-uri()='']</span><span class="sxs-lookup"><span data-stu-id="fcd17-194">*[local-name()='Status' and namespace-uri()='']</span></span>|<span data-ttu-id="fcd17-195">/PurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="fcd17-195">/PurchaseOrder</span></span>|<span data-ttu-id="fcd17-196">[状態]</span><span class="sxs-lookup"><span data-stu-id="fcd17-196">Status</span></span>|  
  
#### <a name="to-view-the-xpath-selector-and-xpath-field-bindings-for-the-quantity-and-status-fields"></a><span data-ttu-id="fcd17-197">Quantity および Status フィールドに対する Xpath セレクターおよび Xpath フィールドのバインドを表示するには</span><span class="sxs-lookup"><span data-stu-id="fcd17-197">To view the Xpath Selector and Xpath Field bindings for the Quantity and Status fields</span></span>  
  
1.  <span data-ttu-id="fcd17-198">ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、展開**ProcessPurchaseOrder**の順に展開および**バージョン 1.0**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-198">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, and then expand **Version 1.0**.</span></span>  
  
2.  <span data-ttu-id="fcd17-199">をクリックして**ApprovalRule**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-199">Click **ApprovalRule**.</span></span>  
  
3.  <span data-ttu-id="fcd17-200">右側の [IF] ペインでをクリックして**PO:/PurchaseOrder/Item/quantity**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-200">In the IF pane on the right, click **PO:/PurchaseOrder/Item/Quantity**.</span></span>  
  
4.  <span data-ttu-id="fcd17-201">前の表に示すように値が表示されることを確認、 **XPath セレクター**と**XPath フィールド**プロパティ ウィンドウにバインドします。</span><span class="sxs-lookup"><span data-stu-id="fcd17-201">Verify that you see the value shown in the preceding table for the **XPath Selector** and **XPath Field** bindings in the Properties window.</span></span>  
  
5.  <span data-ttu-id="fcd17-202">手順 3 と 4 を繰り返して、 **PO:/purchaseorder/status**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="fcd17-202">Repeat steps 3 and 4 for the **PO:/PurchaseOrder/Status** field.</span></span>  
  
 <span data-ttu-id="fcd17-203">ルール エンジンは、子を作成**TypedXmlDocument** 、元のオブジェクト**TypedXmlDocument**各 XPath セレクターに対して送信されます。</span><span class="sxs-lookup"><span data-stu-id="fcd17-203">The rule engine creates a child **TypedXmlDocument** object from the original **TypedXmlDocument** you submitted for each XPath selector.</span></span> <span data-ttu-id="fcd17-204">ポリシーで使用される 2 つの異なる XPath セレクターがあるため (**PurchaseOrder/項目**の**数量**フィールドと**/PurchaseOrder**の**ステータス**フィールド)、ルール エンジンは、2 つの子を作成**TypedXmlDocument**オブジェクトし、ルール エンジンの作業メモリにアサートします。</span><span class="sxs-lookup"><span data-stu-id="fcd17-204">Because there are two distinct XPath selectors used in the policy (**/PurchaseOrder/Item** for the **Quantity** field and **/PurchaseOrder** for the **Status** field), the rule engine creates two child **TypedXmlDocument** objects and asserts them into the working memory of the rule engine.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fcd17-205">出力を再びをクリックして、トレースを表示する**バージョン 1.0**ポリシー エクスプ ローラー ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="fcd17-205">To see the trace output again, click **Version 1.0** in the Policy Explorer window.</span></span>  
  
 <span data-ttu-id="fcd17-206">**条件の評価テスト (一致) 2006/8/31 1時 33分: 10 PM**</span><span class="sxs-lookup"><span data-stu-id="fcd17-206">**CONDITION EVALUATION TEST (MATCH) 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="fcd17-207">**ルール エンジン インスタンス識別子: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="fcd17-207">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="fcd17-208">**ルール セット名: ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="fcd17-208">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="fcd17-209">**テスト式: TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item.Quantity < = 500**</span><span class="sxs-lookup"><span data-stu-id="fcd17-209">**Test Expression: TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item.Quantity <= 500**</span></span>  
  
 <span data-ttu-id="fcd17-210">**左のオペランド値: 400**</span><span class="sxs-lookup"><span data-stu-id="fcd17-210">**Left Operand Value: 400**</span></span>  
  
 <span data-ttu-id="fcd17-211">**右のオペランド値: 500**</span><span class="sxs-lookup"><span data-stu-id="fcd17-211">**Right Operand Value: 500**</span></span>  
  
 <span data-ttu-id="fcd17-212">**テスト結果: True**</span><span class="sxs-lookup"><span data-stu-id="fcd17-212">**Test Result: True**</span></span>  
  
 <span data-ttu-id="fcd17-213">**議題の更新 2006/8/31 1時 33分: 10 PM**</span><span class="sxs-lookup"><span data-stu-id="fcd17-213">**AGENDA UPDATE 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="fcd17-214">**ルール エンジン インスタンス識別子: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="fcd17-214">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="fcd17-215">**ルール セット名: ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="fcd17-215">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="fcd17-216">**操作: 追加**</span><span class="sxs-lookup"><span data-stu-id="fcd17-216">**Operation: Add**</span></span>  
  
 <span data-ttu-id="fcd17-217">**ルール名: ApprovalRule**</span><span class="sxs-lookup"><span data-stu-id="fcd17-217">**Rule Name: ApprovalRule**</span></span>  
  
 <span data-ttu-id="fcd17-218">**競合解決条件: 0**</span><span class="sxs-lookup"><span data-stu-id="fcd17-218">**Conflict Resolution Criteria: 0**</span></span>  
  
 <span data-ttu-id="fcd17-219">ルール エンジンは、条件の評価、競合解決、およびアクションの実行という 3 つのステージによるアルゴリズムを使用してポリシーを実行します。</span><span class="sxs-lookup"><span data-stu-id="fcd17-219">The rule engine uses the three-stage Condition Evaluation-Conflict Resolution-Action Execution algorithm to execute policies.</span></span> <span data-ttu-id="fcd17-220">条件の評価のステージでは、ルール エンジンは、ポリシーのすべてのルールで条件を評価し、条件が議題に対して `true` と評価されているルールを追加します。</span><span class="sxs-lookup"><span data-stu-id="fcd17-220">In the Condition Evaluation stage, the rule engine evaluates the conditions in all the rules in the policy and adds the rules whose conditions evaluate to `true` to the agenda.</span></span> <span data-ttu-id="fcd17-221">この単純な例では、 **ProcessPurchaseOrder**ポリシーが 1 つのルール**ApprovalRule**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-221">In this simple example, the **ProcessPurchaseOrder** policy has only one rule, **ApprovalRule**.</span></span> <span data-ttu-id="fcd17-222">ルール エンジンが、条件を評価するため、**数量 < = 500**で、 **ApprovalRule**の値を使用して、**数量**フィールドに送信された XML ドキュメントこれは**400**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-222">Therefore, the rule engine evaluates the condition, **Quantity <= 500**, in the **ApprovalRule** using the value of the **Quantity** field in the submitted XML document, which is **400**.</span></span> <span data-ttu-id="fcd17-223">上記の出力には、左側のオペランド、右側のオペランド、およびテスト結果の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcd17-223">The output above shows you the values of the left operand, right operand, and test result.</span></span>  
  
 <span data-ttu-id="fcd17-224">第 2 段階である競合解決条件のステージでは、条件が `true` と評価されるルールがそれぞれの優先度に基づいた順序で議題に追加されます。</span><span class="sxs-lookup"><span data-stu-id="fcd17-224">In the second stage, the Conflict Resolution Criteria stage, the rules whose conditions evaluate to `true` are added to the agenda in order based on their priority.</span></span> <span data-ttu-id="fcd17-225">このシナリオでは、ルール エンジンを追加、 **ApprovalRule**議題にための条件、 **ApprovalRule**に評価される`true`です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-225">In this scenario, the rule engine adds the **ApprovalRule** to the agenda because the condition for the **ApprovalRule** evaluated to `true`.</span></span> <span data-ttu-id="fcd17-226">上記の出力に示すように競合解決条件は、ルールの優先度のみ (**ApprovalRule**)。</span><span class="sxs-lookup"><span data-stu-id="fcd17-226">The Conflict Resolution Criteria shown in the output above is only the priority on the rule (**ApprovalRule**).</span></span> <span data-ttu-id="fcd17-227">クリックした場合、 **ApprovalRule**ポリシー エクスプ ローラー ウィンドウでノードの値を表示する、**優先度**プロパティとして プロパティ ウィンドウで、規則を**0**、これは、ルールの既定値です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-227">If you click the **ApprovalRule** node in the Policy Explorer window, you can see the value of the **Priority** property on the rule in the Properties window as **0**, which is the default value of a rule.</span></span> <span data-ttu-id="fcd17-228">ポリシーに複数のルールがあり、1 つのルールのアクションを別のルールのアクションの後に実行する必要がある場合は、適切に優先度を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcd17-228">If you have multiple rules in a policy, and you want to make sure that actions in one rule are executed after actions in another rule, you should set the priority appropriately.</span></span> <span data-ttu-id="fcd17-229">数値が大きいほど、優先順位が高いほど、</span><span class="sxs-lookup"><span data-stu-id="fcd17-229">The larger the number, the higher the priority.</span></span>  
  
 <span data-ttu-id="fcd17-230">**2006/8/31 実行されたルール 1時 33分: 10 PM**</span><span class="sxs-lookup"><span data-stu-id="fcd17-230">**RULE FIRED 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="fcd17-231">**ルール エンジン インスタンス識別子: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="fcd17-231">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="fcd17-232">**ルール セット名: ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="fcd17-232">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="fcd17-233">**ルール名: ApprovalRule**</span><span class="sxs-lookup"><span data-stu-id="fcd17-233">**Rule Name: ApprovalRule**</span></span>  
  
 <span data-ttu-id="fcd17-234">**競合解決条件: 0**</span><span class="sxs-lookup"><span data-stu-id="fcd17-234">**Conflict Resolution Criteria: 0**</span></span>  
  
 <span data-ttu-id="fcd17-235">最終段階であるアクションの実行のステージでは、ルール エンジンによってルールのアクションの実行が開始されます。</span><span class="sxs-lookup"><span data-stu-id="fcd17-235">In the last stage, the Action Execution stage, the rule engine starts executing the actions in the rule.</span></span> <span data-ttu-id="fcd17-236">内の 1 つのアクションがある、 **ApprovalRule**の値を設定する、**ステータス**フィールドに送信された XML ドキュメントに**Approved**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-236">There is one action in the **ApprovalRule**, which sets the value of the **Status** field in the submitted XML document to **Approved**.</span></span>  
  
 <span data-ttu-id="fcd17-237">**ファクト アクティビティ 2006/8/31 1時 33分: 10 PM**</span><span class="sxs-lookup"><span data-stu-id="fcd17-237">**FACT ACTIVITY 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="fcd17-238">**ルール エンジン インスタンス識別子: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="fcd17-238">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="fcd17-239">**ルール セット名: ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="fcd17-239">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="fcd17-240">**操作: 取り消し**</span><span class="sxs-lookup"><span data-stu-id="fcd17-240">**Operation: Retract**</span></span>  
  
 <span data-ttu-id="fcd17-241">**オブジェクトの種類: TypedXmlDocument:PurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="fcd17-241">**Object Type: TypedXmlDocument:PurchaseOrder**</span></span>  
  
 <span data-ttu-id="fcd17-242">**オブジェクト インスタンス識別子: 14626574**</span><span class="sxs-lookup"><span data-stu-id="fcd17-242">**Object Instance Identifier: 14626574**</span></span>  
  
 <span data-ttu-id="fcd17-243">**ファクト アクティビティ 2006/8/31 1時 33分: 10 PM**</span><span class="sxs-lookup"><span data-stu-id="fcd17-243">**FACT ACTIVITY 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="fcd17-244">**ルール エンジン インスタンス識別子: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="fcd17-244">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="fcd17-245">**ルール セット名: ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="fcd17-245">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="fcd17-246">**操作: 取り消し**</span><span class="sxs-lookup"><span data-stu-id="fcd17-246">**Operation: Retract**</span></span>  
  
 <span data-ttu-id="fcd17-247">**オブジェクトの種類: TypedXmlDocument:PurchaseOrder: PurchaseOrder/項目**</span><span class="sxs-lookup"><span data-stu-id="fcd17-247">**Object Type: TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item**</span></span>  
  
 <span data-ttu-id="fcd17-248">**オブジェクト インスタンス識別子: 43901854**</span><span class="sxs-lookup"><span data-stu-id="fcd17-248">**Object Instance Identifier: 43901854**</span></span>  
  
 <span data-ttu-id="fcd17-249">**ファクト アクティビティ 2006/8/31 1時 33分: 10 PM**</span><span class="sxs-lookup"><span data-stu-id="fcd17-249">**FACT ACTIVITY 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="fcd17-250">**ルール エンジン インスタンス識別子: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="fcd17-250">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="fcd17-251">**ルール セット名: ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="fcd17-251">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="fcd17-252">**操作: 取り消し**</span><span class="sxs-lookup"><span data-stu-id="fcd17-252">**Operation: Retract**</span></span>  
  
 <span data-ttu-id="fcd17-253">**オブジェクトの種類: TypedXmlDocument:PurchaseOrder:/PurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="fcd17-253">**Object Type: TypedXmlDocument:PurchaseOrder:/PurchaseOrder**</span></span>  
  
 <span data-ttu-id="fcd17-254">**オブジェクト インスタンス識別子:** 64530307</span><span class="sxs-lookup"><span data-stu-id="fcd17-254">**Object Instance Identifier:** 64530307</span></span>  
  
 <span data-ttu-id="fcd17-255">送信されたすべてのファクト (**PurchaseOrder**)、ルール エンジンと、ルール エンジンによって作成された子ファクト XPath セレクターに基づいて (**\PurchaseOrder**と**\PurchaseOrder\Item**)取り消され (削除)、ルール エンジンの作業メモリからです。</span><span class="sxs-lookup"><span data-stu-id="fcd17-255">All the facts submitted (**PurchaseOrder**) to the rule engine and the child facts created by the rule engine based on XPath selectors (**\PurchaseOrder** and **\PurchaseOrder\Item**) are retracted (removed) from the working memory of the rule engine.</span></span>  
  
## <a name="analysis-of-the-output-from-the-second-test-samplepo2xml"></a><span data-ttu-id="fcd17-256">2 番目のテスト (samplepo2.xml) からの出力の分析</span><span class="sxs-lookup"><span data-stu-id="fcd17-256">Analysis of the Output from the Second Test (samplepo2.xml)</span></span>  
 <span data-ttu-id="fcd17-257">**条件の評価テスト (一致) 2006/9/5 5時 24分: 42 PM**</span><span class="sxs-lookup"><span data-stu-id="fcd17-257">**CONDITION EVALUATION TEST (MATCH) 9/5/2006 5:24:42 PM**</span></span>  
  
 <span data-ttu-id="fcd17-258">**ルール エンジン インスタンス識別子: b749d2fd-a883-4c2f-9974-5cf688010622**</span><span class="sxs-lookup"><span data-stu-id="fcd17-258">**Rule Engine Instance Identifier: b749d2fd-a883-4c2f-9974-5cf688010622**</span></span>  
  
 <span data-ttu-id="fcd17-259">**ルール セット名: ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="fcd17-259">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="fcd17-260">**テスト式: TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item.Quantity < = 500**</span><span class="sxs-lookup"><span data-stu-id="fcd17-260">**Test Expression: TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item.Quantity <= 500**</span></span>  
  
 <span data-ttu-id="fcd17-261">**左のオペランド値: 700**</span><span class="sxs-lookup"><span data-stu-id="fcd17-261">**Left Operand Value: 700**</span></span>  
  
 <span data-ttu-id="fcd17-262">**右のオペランド値: 500**</span><span class="sxs-lookup"><span data-stu-id="fcd17-262">**Right Operand Value: 500**</span></span>  
  
 <span data-ttu-id="fcd17-263">**テスト結果:** False</span><span class="sxs-lookup"><span data-stu-id="fcd17-263">**Test Result:** False</span></span>  
  
 <span data-ttu-id="fcd17-264">条件を評価するルール エンジン (**数量 < = 500**) で、 **ApprovalRule** 、内の単一行を使用して**項目**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="fcd17-264">The rule engine evaluates the condition (**Quantity <= 500**) in the **ApprovalRule** using the lone **Item** object.</span></span> <span data-ttu-id="fcd17-265">左側のオペランド値は、の値であるを参照してください、**数量**XML ドキュメント内の要素**700**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-265">You can see that left operand value is the value of the **Quantity** element in the XML document, **700**.</span></span> <span data-ttu-id="fcd17-266">テスト結果は`false`ため**700 < = 500**ルールがルール エンジンの議題に追加されていないため、します。</span><span class="sxs-lookup"><span data-stu-id="fcd17-266">The test result is `false` because **700 <= 500**, so the rule is not added to the agenda of the rule engine.</span></span> <span data-ttu-id="fcd17-267">議題にはルールが存在しません。</span><span class="sxs-lookup"><span data-stu-id="fcd17-267">There is no rule in the agenda.</span></span> <span data-ttu-id="fcd17-268">したがってを実行するアクションはありませんしの値、**ステータス**ままフィールド**XYZ**です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-268">Therefore, there are no actions to execute, and the value of the **Status** field remains **XYZ**.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="fcd17-269">コメント</span><span class="sxs-lookup"><span data-stu-id="fcd17-269">Comments</span></span>  
  
-   <span data-ttu-id="fcd17-270">BizTalk アプリケーションなどのクライアント アプリケーションからポリシーを使用する前に、ポリシーをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fcd17-270">We recommend that you test the policies before using them from client applications such as BizTalk applications.</span></span>  
  
-   <span data-ttu-id="fcd17-271">と共にデータベース ファクトを使用するポリシーをテストするとき、 **DataConnection** 、ビジネス ルール作成ツールで、バインド、 **DataConnection**オブジェクトが自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="fcd17-271">When you test a policy that uses database facts with the **DataConnection** binding in the Business Rule Composer, a **DataConnection** object is automatically built for you.</span></span> <span data-ttu-id="fcd17-272">ただし、呼び出すと、同じポリシー オーケストレーションからを使用して、**ルールの呼び出し**図形、いいえ**DataConnection**オブジェクトがポリシーに自動的に渡されます。</span><span class="sxs-lookup"><span data-stu-id="fcd17-272">However, when you call the same policy from an orchestration by using the **Call Rules** shape, no **DataConnection** object is passed to the policy automatically.</span></span> <span data-ttu-id="fcd17-273">作成する必要があります、 **DataConnection**オーケストレーション内のオブジェクトしをパラメーターとして渡すかをアサートするファクト取得コンポーネントを作成、 **DataConnection**オブジェクト、および使用するポリシーを構成します。ファクト取得コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="fcd17-273">You should create a **DataConnection** object in the orchestration and pass it as a parameter or create a fact retriever component that asserts the **DataConnection** object, and configure the policy to use the fact retriever component.</span></span>  
  
-   <span data-ttu-id="fcd17-274">.NET ファクトを使用するポリシーをテストするには、ファクト作成コンポーネントを作成し、でを指定する必要があります、 **[ファクトの**] ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="fcd17-274">To test a policy that uses a .NET fact, you should create a fact creator component and specify it in the **Select Facts** dialog box.</span></span> <span data-ttu-id="fcd17-275">ファクト作成コンポーネントの詳細については、次を参照してください。[ファクト取得コンポーネントを作成する方法](../core/how-to-create-a-fact-retriever.md)です。</span><span class="sxs-lookup"><span data-stu-id="fcd17-275">For more information about creating fact creators, see [How to Create a Fact Retriever](../core/how-to-create-a-fact-retriever.md).</span></span> <span data-ttu-id="fcd17-276">ポリシーがデータベース ファクトを使用する場合は、同じ処理を行うことができます (**TypedDataConnection**または**TypedDataTable**または**TypedDataRow**) または XML ファクト (**TypedXmlDocument**)。</span><span class="sxs-lookup"><span data-stu-id="fcd17-276">You can do the same thing when the policy uses database facts (**TypedDataConnection** or **TypedDataTable** or **TypedDataRow**) or XML facts (**TypedXmlDocument**).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fcd17-277">次の手順</span><span class="sxs-lookup"><span data-stu-id="fcd17-277">Next Steps</span></span>  
 <span data-ttu-id="fcd17-278">これで、このチュートリアルを完了すると、実行、[チュートリアル: オーケストレーションからポリシーを呼び出す](../core/walkthrough-invoking-the-policy-from-an-orchestration.md)を呼び出すための手順を説明するチュートリアル、 **ProcessPurchaseOrder**オーケストレーションからポリシー。</span><span class="sxs-lookup"><span data-stu-id="fcd17-278">Now that you have completed this walkthrough, perform the [Walkthrough: Invoking the Policy from an Orchestration](../core/walkthrough-invoking-the-policy-from-an-orchestration.md) walkthrough, which gives you step-by-step instructions for invoking the **ProcessPurchaseOrder** policy from an orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcd17-279">参照</span><span class="sxs-lookup"><span data-stu-id="fcd17-279">See Also</span></span>  
 <span data-ttu-id="fcd17-280">[ポリシー テストのトレース出力](../core/policy-test-trace-output.md) </span><span class="sxs-lookup"><span data-stu-id="fcd17-280">[Policy Test Trace Output](../core/policy-test-trace-output.md) </span></span>  
 <span data-ttu-id="fcd17-281">[条件の評価とアクションの実行](../core/condition-evaluation-and-action-execution.md) </span><span class="sxs-lookup"><span data-stu-id="fcd17-281">[Condition Evaluation and Action Execution](../core/condition-evaluation-and-action-execution.md) </span></span>  
 [<span data-ttu-id="fcd17-282">議題と優先度</span><span class="sxs-lookup"><span data-stu-id="fcd17-282">Agenda and Priority</span></span>](../core/agenda-and-priority.md)