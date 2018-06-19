---
title: 'チュートリアル: プログラムによって、ポリシーの実行 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6398e7af-2ed1-4596-879c-3b7d000b8de2
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5afbe8bd29f18e71999ff32e0a1100de8a65fcc4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290378"
---
# <a name="walkthrough-executing-the-policy-programmatically"></a><span data-ttu-id="872b2-102">チュートリアル: プログラムによって、ポリシーの実行</span><span class="sxs-lookup"><span data-stu-id="872b2-102">Walkthrough: Executing the Policy Programmatically</span></span>
<span data-ttu-id="872b2-103">このチュートリアルで作成したポリシーを呼び出すための手順では、[チュートリアル: 単純なビジネス ポリシーを作成する](../core/walkthrough-creating-a-simple-business-policy.md)チュートリアルのコンソール アプリケーションからプログラムでします。</span><span class="sxs-lookup"><span data-stu-id="872b2-103">This walkthrough provides step-by-step procedures for invoking the policy you created in the [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md) walkthrough from a console application programmatically.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="872b2-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="872b2-104">Prerequisites</span></span>  
 <span data-ttu-id="872b2-105">完了する必要があります、[チュートリアル: 単純なビジネス ポリシーを作成する](../core/walkthrough-creating-a-simple-business-policy.md)チュートリアルのこのチュートリアルを実行する前にします。</span><span class="sxs-lookup"><span data-stu-id="872b2-105">You must complete the [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md) walkthrough before you perform this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="872b2-106">このチュートリアルの概要</span><span class="sxs-lookup"><span data-stu-id="872b2-106">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="872b2-107">次の表に示すように、このチュートリアルには 2 つの手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="872b2-107">This walkthrough contains two procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="872b2-108">手順のタイトル</span><span class="sxs-lookup"><span data-stu-id="872b2-108">Procedure title</span></span>|<span data-ttu-id="872b2-109">手順の説明</span><span class="sxs-lookup"><span data-stu-id="872b2-109">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="872b2-110">Policy.Execute メソッドを使用して ProcessPurchaseOrder ポリシーを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="872b2-110">To invoke the ProcessPurchaseOrder policy by using the Policy.Execute method</span></span>|<span data-ttu-id="872b2-111">使用してポリシーを呼び出すための手順をわかりやすく説明、 **Policy.Execute**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="872b2-111">Provides step-by-step instructions for invoking a policy by using the **Policy.Execute** method.</span></span>|  
|<span data-ttu-id="872b2-112">RuleEngine.Execute メソッドを使用して ProcessPurchaseOrder ポリシーを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="872b2-112">To invoke the ProcessPurchaseOrder policy by using the RuleEngine.Execute method</span></span>|<span data-ttu-id="872b2-113">使用してポリシーを呼び出すための手順をわかりやすく説明、 **RuleEngine.Execute**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="872b2-113">Provides step-by-step instructions for invoking a policy by using the **RuleEngine.Execute** method.</span></span>|  
  
### <a name="to-invoke-the-processpurchaseorder-policy-by-using-the-policyexecute-method"></a><span data-ttu-id="872b2-114">Policy.Execute メソッドを使用して ProcessPurchaseOrder ポリシーを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="872b2-114">To invoke the ProcessPurchaseOrder policy by using the Policy.Execute method</span></span>  
  
1.  <span data-ttu-id="872b2-115">開始**Microsoft Visual Studio**です。</span><span class="sxs-lookup"><span data-stu-id="872b2-115">Start **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="872b2-116">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]の**ファイル**メニューのをポイント**新規**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="872b2-116">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="872b2-117">**新しいプロジェクト** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="872b2-117">In the **New Project** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="872b2-118">プロパティ</span><span class="sxs-lookup"><span data-stu-id="872b2-118">Use this</span></span>|<span data-ttu-id="872b2-119">目的</span><span class="sxs-lookup"><span data-stu-id="872b2-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="872b2-120">**プロジェクトの種類**</span><span class="sxs-lookup"><span data-stu-id="872b2-120">**Project types**</span></span>|<span data-ttu-id="872b2-121">をクリックして**Visual c#** です。</span><span class="sxs-lookup"><span data-stu-id="872b2-121">Click **Visual C#**.</span></span>|  
    |<span data-ttu-id="872b2-122">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="872b2-122">**Templates**</span></span>|<span data-ttu-id="872b2-123">をクリックして**コンソール アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="872b2-123">Click **Console Application**.</span></span>|  
    |<span data-ttu-id="872b2-124">**名前**</span><span class="sxs-lookup"><span data-stu-id="872b2-124">**Name**</span></span>|<span data-ttu-id="872b2-125">型**ConsoleClient**です。</span><span class="sxs-lookup"><span data-stu-id="872b2-125">Type **ConsoleClient**.</span></span>|  
    |<span data-ttu-id="872b2-126">**場所**</span><span class="sxs-lookup"><span data-stu-id="872b2-126">**Location**</span></span>|<span data-ttu-id="872b2-127">プロジェクト ファイルを保存するフォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="872b2-127">Specify a folder where you want to save the project files.</span></span>|  
    |<span data-ttu-id="872b2-128">**[ソリューション名]**</span><span class="sxs-lookup"><span data-stu-id="872b2-128">**Solution Name**</span></span>|<span data-ttu-id="872b2-129">型**ConsoleClientSol**です。</span><span class="sxs-lookup"><span data-stu-id="872b2-129">Type **ConsoleClientSol**.</span></span>|  
    |<span data-ttu-id="872b2-130">**ソリューションのディレクトリを作成します。**</span><span class="sxs-lookup"><span data-stu-id="872b2-130">**Create directory for solution**</span></span>|<span data-ttu-id="872b2-131">ソリューション ファイルのディレクトリを作成するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="872b2-131">Select this check box to create a directory for the solution files.</span></span>|  
  
4.  <span data-ttu-id="872b2-132">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="872b2-132">Click **OK**.</span></span> <span data-ttu-id="872b2-133">**ConsoleClient**プロジェクトがソリューション エクスプ ローラーで表示されます。</span><span class="sxs-lookup"><span data-stu-id="872b2-133">The **ConsoleClient** project should appear in Solution Explorer.</span></span> <span data-ttu-id="872b2-134">ソリューション エクスプ ローラーが表示されない場合はクリックして**ソリューション エクスプ ローラー**上、**ビュー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="872b2-134">If you do not see Solution Explorer, click **Solution Explorer** on the **View** menu.</span></span>  
  
5.  <span data-ttu-id="872b2-135">ソリューション エクスプ ローラーで右クリック**参照**、クリックして**参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="872b2-135">In Solution Explorer, right-click **References**, and then click **Add Reference**.</span></span>  
  
6.  <span data-ttu-id="872b2-136">をクリックして**参照**を参照、 **\program files \microsoft BizTalk**、順にダブルクリック **[microsoft.ruleengine.dll]** です。</span><span class="sxs-lookup"><span data-stu-id="872b2-136">Click **Browse**, browse to the **\Program Files\Common Files\Microsoft BizTalk**, and then double-click **Microsoft.RuleEngine.dll**.</span></span>  
  
7.  <span data-ttu-id="872b2-137">先頭に次の行を追加、 **Program.cs**後、既存のファイル`using`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="872b2-137">Add the following lines to the top of the **Program.cs** file after the existing `using` statements:</span></span>  
  
    ```  
    //To use the XmlDocument class  
    using System.Xml;  
    //To use the TypedXmlDocument and Policy classes  
    using Microsoft.RuleEngine;   
    ```  
  
8.  <span data-ttu-id="872b2-138">次のコードを追加、 **Main**を作成する関数、 **TypedXmlDocument**オブジェクトが XML ドキュメントに基づきます。</span><span class="sxs-lookup"><span data-stu-id="872b2-138">Add the following code to the **Main** function to create a **TypedXmlDocument** object based on the XML document:</span></span>  
  
    ```  
    XmlDocument doc = new XmlDocument();  
    //Loading the XML from SamplePO.xml file.  
    //Change the directory as needed  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
    ```  
  
9. <span data-ttu-id="872b2-139">次のコードを追加、 **Main**ポリシーを実行する関数。</span><span class="sxs-lookup"><span data-stu-id="872b2-139">Add the following code to the **Main** function to execute the policy:</span></span>  
  
    ```  
    //Create a policy object based on the name, ProcessPurchaseOrder  
    Policy policy = new Policy("ProcessPurchaseOrder");  
    //Execute the policy by invoking Policy.Execute method and   
    //by passing the typed xml document as a fact.   
    policy.Execute(txd);   
    ```  
  
10. <span data-ttu-id="872b2-140">出力 XML を確認するための値を出力、**ステータス**にフィールドが設定されている**Approved**です。</span><span class="sxs-lookup"><span data-stu-id="872b2-140">Print the output XML to confirm that the value of the **Status** field is set to **Approved**.</span></span> <span data-ttu-id="872b2-141">なお、ビジネス ルール作成ツールとは異なりを呼び出す、 **Policy.Execute**メソッドでは、元のドキュメントは変更されません。</span><span class="sxs-lookup"><span data-stu-id="872b2-141">Note that unlike the Business Rule Composer, invoking the **Policy.Execute** method does not change the original document.</span></span>  
  
    ```  
    //Print the output document  
    Console.WriteLine(txd.Document.OuterXml);   
    ```  
  
11. <span data-ttu-id="872b2-142">**ビルド** メニューのをクリックして**ビルド ConsoleClient**です。</span><span class="sxs-lookup"><span data-stu-id="872b2-142">On the **Build** menu, click **Build ConsoleClient**.</span></span>  
  
12. <span data-ttu-id="872b2-143">Ctrl キーを押しながら F5 キーを押して、アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="872b2-143">Press CTRL+F5 to execute the application.</span></span> <span data-ttu-id="872b2-144">いることを確認の値、**ステータス**にフィールドが設定されている**Approved**です。</span><span class="sxs-lookup"><span data-stu-id="872b2-144">Confirm that the value of the **Status** field is set to **Approved**.</span></span>  
  
### <a name="to-invoke-the-processpurchaseorder-policy-by-using-the-ruleengineexecute-method"></a><span data-ttu-id="872b2-145">RuleEngine.Execute メソッドを使用して ProcessPurchaseOrder ポリシーを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="872b2-145">To invoke the ProcessPurchaseOrder policy by using the RuleEngine.Execute method</span></span>  
  
1.  <span data-ttu-id="872b2-146">ソリューション エクスプ ローラーで右クリック**参照**、クリックして**参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="872b2-146">In Solution Explorer, right-click **References**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="872b2-147">をクリックして**参照**を参照**\program files \microsoft BizTalk**、順にダブルクリック**Microsoft.BizTalk.RuleEngineExtensions.dll**です。</span><span class="sxs-lookup"><span data-stu-id="872b2-147">Click **Browse**, browse to **\Program Files\Common Files\Microsoft BizTalk**, and then double-click **Microsoft.BizTalk.RuleEngineExtensions.dll**.</span></span>  
  
3.  <span data-ttu-id="872b2-148">次の行をコメント、 **Program.cs**ファイル。</span><span class="sxs-lookup"><span data-stu-id="872b2-148">Comment out the following lines in the **Program.cs** file:</span></span>  
  
    ```  
    //Create a policy object based on the name, ProcessPurchaseOrder  
    Policy policy = new Policy("ProcessPurchaseOrder");  
    //Execute the policy by invoking Policy.Execute method and   
    //by passing the typed xml document as a fact.   
    policy.Execute(txd);   
    ```  
  
4.  <span data-ttu-id="872b2-149">次のコードをコメント化したコードの後に追加して、ルール エンジン データベースにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="872b2-149">Add the following code after the commented-out code to get access to the Rule Engine database:</span></span>  
  
    ```  
    //Get access to the SQL rule store   
    Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
    dd = new Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver();  
    SqlRuleStore sqlRuleStore = (SqlRuleStore)dd.GetRuleStore();  
    ```  
  
5.  <span data-ttu-id="872b2-150">次のコードにアクセスする追加**RuleSetInfoCollection** ProcessPurchaseOrder ポリシー。</span><span class="sxs-lookup"><span data-stu-id="872b2-150">Add the following code to get access to **RuleSetInfoCollection** for the ProcessPurchaseOrder policy:</span></span>  
  
    ```  
    //Get access to RuleSetInfoCollection for the   
    //ProcessPurchaseOrder policy  
    RuleSetInfoCollection rsic = sqlRuleStore.GetRuleSets("ProcessPurchaseOrder", RuleStore.Filter.All);  
    ```  
  
6.  <span data-ttu-id="872b2-151">次のコード作成を追加、 **RuleSet** ProcessPurchaseOrder ポリシーのルール セット情報に基づいてオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="872b2-151">Add the following code to create a **RuleSet** object based on the rule set information for the ProcessPurchaseOrder policy:</span></span>  
  
    ```  
    //Create a RuleSet object based on the rule set information   
    //for the ProcessPurchaseOrder policy  
    RuleSet rs = sqlRuleStore.GetRuleSet(rsic[0]);  
    ```  
  
7.  <span data-ttu-id="872b2-152">次のコード作成を追加、 **RuleEngine**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="872b2-152">Add the following code to create the **RuleEngine** object:</span></span>  
  
    ```  
    //Create the RuleEngine object  
    Microsoft.RuleEngine.RuleEngine engine = new Microsoft.RuleEngine.RuleEngine(rs);  
    ```  
  
8.  <span data-ttu-id="872b2-153">Assert を次のコードを追加、 **TypedXmlDocument**ルール エンジンの作業メモリにオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="872b2-153">Add the following code to assert the **TypedXmlDocument** object into the working memory of the rule engine:</span></span>  
  
    ```  
    //Assert the TypedXmlDocument object into working memory  
    //of the rule engine  
    engine.Assert(txd);  
    ```  
  
9. <span data-ttu-id="872b2-154">使用してポリシーを実行するコードを追加、 **RuleEngine.Execute**メソッド。</span><span class="sxs-lookup"><span data-stu-id="872b2-154">Now add the code to execute the policy by using the **RuleEngine.Execute** method:</span></span>  
  
    ```  
    //Execute the policy by invoking RuleEngine.Execute method  
    engine.Execute();  
    ```  
  
10. <span data-ttu-id="872b2-155">確認して、 **Console.WriteLine**ステートメントは、最後のステートメントで、 **Main**関数。</span><span class="sxs-lookup"><span data-stu-id="872b2-155">Make sure that the **Console.WriteLine** statement is the last statement in the **Main** function.</span></span>  
  
11. <span data-ttu-id="872b2-156">**ビルド** メニューのをクリックして**ビルド ConsoleClient**です。</span><span class="sxs-lookup"><span data-stu-id="872b2-156">On the **Build** menu, click **Build ConsoleClient**.</span></span>  
  
12. <span data-ttu-id="872b2-157">Ctrl キーを押しながら F5 キーを押して、アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="872b2-157">Press CTRL+F5 to execute the application.</span></span> <span data-ttu-id="872b2-158">いることを確認の値、**ステータス**にフィールドが設定されている**Approved**です。</span><span class="sxs-lookup"><span data-stu-id="872b2-158">Confirm that the value of the **Status** field is set to **Approved**.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="872b2-159">コメント</span><span class="sxs-lookup"><span data-stu-id="872b2-159">Comments</span></span>  
  
-   <span data-ttu-id="872b2-160">コードを完了、 **Main**を使用して ProcessPurchaseOrder ポリシーを実行する関数、 **Policy.Execute**メソッドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="872b2-160">Complete code for the **Main** function to execute the ProcessPurchaseOrder policy by using the **Policy.Execute** method is as follows:</span></span>  
  
    ```  
    static void Main(string[] args)  
    {  
    XmlDocument doc = new XmlDocument();  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
    Policy policy = new Policy("ProcessPurchaseOrder");  
    policy.Execute(txd);  
    Console.WriteLine(txd.Document.OuterXml);   
    }  
    ```  
  
-   <span data-ttu-id="872b2-161">使用して ProcessPurchaseOrder ポリシーを実行するためのコードを完了、 **RuleEngine.Execute**メソッドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="872b2-161">Complete code for executing the ProcessPurchaseOrder policy by using the **RuleEngine.Execute** method is as follows:</span></span>  
  
    ```  
    static void Main(string[] args)  
    {  
    XmlDocument doc = new XmlDocument();  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
    Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
    dd = new Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver();  
    SqlRuleStore sqlRuleStore = (SqlRuleStore)dd.GetRuleStore();  
    RuleSetInfoCollection rsic = sqlRuleStore.GetRuleSets("ProcessPurchaseOrder", RuleStore.Filter.All);  
    RuleSet rs = sqlRuleStore.GetRuleSet(rsic[0]);  
    Microsoft.RuleEngine.RuleEngine engine = new Microsoft.RuleEngine.RuleEngine(rs);  
    engine.Assert(txd);  
    engine.Execute();  
    Console.WriteLine(txd.Document.OuterXml);   
    }  
    ```  
  
-   <span data-ttu-id="872b2-162">追加することがあります、 **Console.ReadLine()** ステートメントの最後に、 **Main**アプリケーションが待機すると、アプリケーションを終了するように機能します。</span><span class="sxs-lookup"><span data-stu-id="872b2-162">You may want to add a **Console.ReadLine()** statement at the end of the **Main** function so that the application waits for you to terminate the application.</span></span>  
  
-   <span data-ttu-id="872b2-163">このチュートリアルでは、クライアントが ProcessPurchaseOrder ポリシーに送信するファクトは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="872b2-163">In this walkthrough, the client submits only one fact to the ProcessPurchaseOrder policy.</span></span> <span data-ttu-id="872b2-164">ファクトの配列を作成し、オーバー ロードを使用する必要がある場合は、クライアントは、1 つ以上のファクトをポリシーを送信する必要があります、 **Execute**メソッド パラメーターとして配列を受け取る。</span><span class="sxs-lookup"><span data-stu-id="872b2-164">If the client needs to submit more than one fact to a policy, it needs to create an array of facts and use the overloaded **Execute** method that takes an array as a parameter.</span></span> <span data-ttu-id="872b2-165">次のサンプル コードは、その方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="872b2-165">The following sample code shows how to do that:</span></span>  
  
    ```  
    Policy policy = new Policy("PolicyName");  
    object[] facts = new object[2];  
    facts[0] = txd;  
    facts[1] = new MyClass();  
    policy.Execute(facts);  
    policy.Dispose();  
    ```  
  
-   <span data-ttu-id="872b2-166">最初のパラメーター、 **TypedXmlDocument**コードでコンス トラクターは、ポリシーの構築に使用した型の名前。</span><span class="sxs-lookup"><span data-stu-id="872b2-166">The first parameter to the **TypedXmlDocument** constructor in the code is the name of the type you used to build the policy.</span></span>  
  
-   <span data-ttu-id="872b2-167">**Policy.Execute**メソッドがラップするラッパーでは基本的に、 **RuleEngine.Execute**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="872b2-167">The **Policy.Execute** method is basically a wrapper around the **RuleEngine.Execute** method.</span></span> <span data-ttu-id="872b2-168">したがってを使用して、 **Policy.Execute**メソッドは、このチュートリアルで説明したように、ポリシーを呼び出すの最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="872b2-168">Therefore, using the **Policy.Execute** method is the easiest way of invoking a policy, as you have seen in this walkthrough.</span></span>  
  
-   <span data-ttu-id="872b2-169">使用する、ポリシーの実行をより細かく制御する可能性があります、 **RuleEngine.Execute**メソッドを使用してではなく**Policy.Execute**です。</span><span class="sxs-lookup"><span data-stu-id="872b2-169">For more control over the execution of the policy, you may want to use the **RuleEngine.Execute** method instead of using **Policy.Execute**.</span></span> <span data-ttu-id="872b2-170">使用してエンジンを一時的に停止するなど、**停止**関数とを使用して、再開、 **Execute**関数。</span><span class="sxs-lookup"><span data-stu-id="872b2-170">For example, you can halt the engine temporarily by using the **Halt** function, and then resume it by using the **Execute** function.</span></span> <span data-ttu-id="872b2-171">詳細については、次を参照してください。[停止](../core/halt.md)です。</span><span class="sxs-lookup"><span data-stu-id="872b2-171">For more information, see [Halt](../core/halt.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="872b2-172">参照</span><span class="sxs-lookup"><span data-stu-id="872b2-172">See Also</span></span>  
 [<span data-ttu-id="872b2-173">ポリシーを実行する方法</span><span class="sxs-lookup"><span data-stu-id="872b2-173">How to Execute Policies</span></span>](../core/how-to-execute-policies.md)