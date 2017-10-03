---
title: "単体テストのスキーマおよびマップの機能を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29bcb159-ffdb-44b9-a3ff-565973d41797
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbc14621a1830f15da02336b7b82e9df475cfe9b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-unit-testing-feature-with-schemas-and-maps"></a><span data-ttu-id="887bf-102">スキーマとマップを含む単体テスト機能の使用</span><span class="sxs-lookup"><span data-stu-id="887bf-102">Using the Unit Testing Feature with Schemas and Maps</span></span>
<span data-ttu-id="887bf-103">このトピックでは、単体テスト機能を使用してスキーマとマップの単体テストを HelloWorld オーケストレーション サンプルに追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="887bf-103">This topic demonstrates how to use the unit testing feature to add a unit test for the schemas and map in the HelloWorld orchestration example.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="887bf-104">現時点において、マップ用の単体テスト機能では、複数の入力マップはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="887bf-104">The unit testing feature for maps currently does not support multiple input maps.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="887bf-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="887bf-105">Prerequisites</span></span>  
 <span data-ttu-id="887bf-106">最初に、HelloWorld サンプルの作成手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="887bf-106">You must first follow the steps for building the HelloWorld sample.</span></span> <span data-ttu-id="887bf-107">これらの手順をご覧ください: [HelloWorld (BizTalk Server サンプル)](../core/helloworld-biztalk-server-sample.md)</span><span class="sxs-lookup"><span data-stu-id="887bf-107">Those steps can be found here: [HelloWorld (BizTalk Server Sample)](../core/helloworld-biztalk-server-sample.md)</span></span>  
  
### <a name="adding-a-unit-test-project-to-the-helloworld-sample"></a><span data-ttu-id="887bf-108">HelloWorld サンプルへの単体テスト プロジェクトの追加</span><span class="sxs-lookup"><span data-stu-id="887bf-108">Adding a Unit Test Project to the HelloWorld Sample</span></span>  
  
1.  <span data-ttu-id="887bf-109">Visual Studio で、HelloWorld.sln ソリューション ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="887bf-109">In Visual Studio, open the HelloWorld.sln solution file.</span></span>  
  
2.  <span data-ttu-id="887bf-110">ソリューション エクスプ ローラーで右クリックし、 **HelloWorld**プロジェクトをクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="887bf-110">In Solution Explorer, right-click the **HelloWorld** project, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="887bf-111">プロジェクト デザイナーで、をクリックして、**展開**プロパティ ページ タブとセット**単体テストを有効にする**に`True`です。</span><span class="sxs-lookup"><span data-stu-id="887bf-111">In Project Designer, click the **Deployment** property page tab and set **Enable Unit Testing** to `True`.</span></span>  
  
4.  <span data-ttu-id="887bf-112">変更内容を保存し、プロジェクト プロパティ ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="887bf-112">Close the project properties page saving the changes.</span></span>  
  
5.  <span data-ttu-id="887bf-113">メイン メニューでクリックして**ビルド**、順にクリック**ソリューションのリビルド**です。</span><span class="sxs-lookup"><span data-stu-id="887bf-113">In main menu, click **Build**, and then click **Rebuild Solution**.</span></span>  
  
6.  <span data-ttu-id="887bf-114">メイン メニューで、をクリックして**テスト**、クリックして**新しいテスト**です。</span><span class="sxs-lookup"><span data-stu-id="887bf-114">On the main menu, click **Test**, and then click **New Test**.</span></span>  
  
7.  <span data-ttu-id="887bf-115">**新しいテストの追加**ダイアログ ボックスで、**新しい Visual c# テスト プロジェクトを作成する**の**テスト プロジェクトに追加**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="887bf-115">In the **Add New Test** dialog box, select **Create a new Visual C# test project** for **Add to Test Project** field.</span></span> <span data-ttu-id="887bf-116">選択**単体テスト ウィザード**で、**テンプレート**ボックスの一覧し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="887bf-116">Select **Unit Test Wizard** in the **Templates** list, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="887bf-117">**新しいテスト プロジェクト** ダイアログ ボックスで、プロジェクト名としてのままにして**TestProject1**  をクリック**作成**です。</span><span class="sxs-lookup"><span data-stu-id="887bf-117">In the **New Test Project** dialog box, leave the project name as **TestProject1** and click **Create**.</span></span>  
  
9. <span data-ttu-id="887bf-118">**単体テストの作成** ダイアログ ボックスで、種類を展開し、選択、 **POSchema()**下でコンス トラクター、 **poschema()**ノード。</span><span class="sxs-lookup"><span data-stu-id="887bf-118">In the **Create Unit Tests** dialog box, expand the types and select the **POSchema()** constructor under the **Microsoft.Samples.BizTalk.HelloWorld.POSchema** node.</span></span> <span data-ttu-id="887bf-119">選択も**POToInvoice()**下でコンス トラクター、 **Microsoft.Samples.BizTalk.HelloWorld.POToInvoice**ノード。</span><span class="sxs-lookup"><span data-stu-id="887bf-119">Also select **POToInvoice()** constructor under the **Microsoft.Samples.BizTalk.HelloWorld.POToInvoice** node.</span></span> <span data-ttu-id="887bf-120">次の図は、選択する要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="887bf-120">The figure below shows the selections that should be made.</span></span> <span data-ttu-id="887bf-121">次に、選択した場合、キーを押して**OK**です。</span><span class="sxs-lookup"><span data-stu-id="887bf-121">After making the selections shown below, press **OK**.</span></span>  
  
     ![](../core/media/schemaandmapsunittestwizardselection.gif "SchemaAndMapsUnitTestWizardSelection")  
  
### <a name="adding-test-code-to-test-the-schemas-and-map"></a><span data-ttu-id="887bf-122">スキーマとマップをテストするテスト コードの追加</span><span class="sxs-lookup"><span data-stu-id="887bf-122">Adding Test Code to Test the Schemas and Map</span></span>  
  
1.  <span data-ttu-id="887bf-123">次の参照を追加、 **TestProject1**プロジェクトから、 **.NET**  タブで 参照の追加 ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="887bf-123">Add the following references to the **TestProject1** project from the **.NET** tab in the Add Reference dialog:</span></span>  
  
    -   <span data-ttu-id="887bf-124">Microsoft.BizTalk.TestTools</span><span class="sxs-lookup"><span data-stu-id="887bf-124">Microsoft.BizTalk.TestTools</span></span>  
  
    -   <span data-ttu-id="887bf-125">Microsoft XLANG/s ベース型</span><span class="sxs-lookup"><span data-stu-id="887bf-125">Microsoft XLANG/s Base Types</span></span>  
  
2.  <span data-ttu-id="887bf-126">ソリューション エクスプローラーで、POSchemaTest.cs を開きます。</span><span class="sxs-lookup"><span data-stu-id="887bf-126">In Solution Explorer, open POSchemaTest.cs</span></span>  
  
3.  <span data-ttu-id="887bf-127">ファイルの一番下までスクロールし、置換、 **POSchemaConstructorTest**を次のコード サンプルの注文書を検証するメソッドは、メッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="887bf-127">Scroll to the bottom of the file and replace the **POSchemaConstructorTest** method with the following code which validates the sample PO input message:</span></span>  
  
    ```  
    [TestMethod()]  
    public void POSchemaInstanceValidationTest()  
    {  
        POSchema target = new POSchema();  
  
        //=== The SamplePOInput.xml file from <Samples Path>\Orchestrations\HelloWorld ===//  
        string strSourcePO_XML = testContextInstance.TestDir + "..\\..\\..\\SamplePOInput.xml";  
  
        //=== Validate the SamplePOInput message against the schema ===//  
        Assert.IsTrue(target.ValidateInstance(strSourcePO_XML, Microsoft.BizTalk.TestTools.Schema.OutputInstanceType.XML));  
    }  
    ```  
  
4.  <span data-ttu-id="887bf-128">ソリューション エクスプローラーで POToInvoiceTest.cs を開き、次のディレクティブをそのファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="887bf-128">In Solution Explorer open POToInvoiceTest.cs and add the following directive to the top of that file:</span></span>  
  
    ```  
  
    using System.IO;   
    ```  
  
5.  <span data-ttu-id="887bf-129">ファイルの一番下までスクロールし、置換、 **POToInvoiceConstructorTest**を次のコード サンプルの注文書を使用してマップをテストするメソッドは、メッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="887bf-129">Scroll to the bottom of the file and replace the **POToInvoiceConstructorTest** method with the following code which tests the map using the sample PO input message:</span></span>  
  
    ```  
  
    [TestMethod()]  
    public void POToInvoiceMapTest()  
    {  
        POToInvoice target = new POToInvoice();  
  
        //=== Use the HelloWorld sample directory path for the message files ===//  
  
        string strSourcePO_XML = testContextInstance.TestDir + "..\\..\\..\\SamplePOInput.xml";  
        string strDestInvoice_XML = testContextInstance.TestDir + "..\\..\\..\\SampleInvoiceOutput.xml";  
  
        //=== Test the map by using the TestMap method of the TestableMapBase class ===//  
  
        target.ValidateOutput = true;  
        target.TestMap(strSourcePO_XML,  
                       Microsoft.BizTalk.TestTools.Schema.InputInstanceType.Xml,  
                       strDestInvoice_XML,  
                       Microsoft.BizTalk.TestTools.Schema.OutputInstanceType.XML);  
  
        //=== Output file should be created as a result of testing the map ===//  
  
        Assert.IsTrue(File.Exists(strDestInvoice_XML));   
    }  
    ```  
  
### <a name="building-and-running-the-unit-test"></a><span data-ttu-id="887bf-130">単体テストのビルドと実行</span><span class="sxs-lookup"><span data-stu-id="887bf-130">Building and Running the Unit Test</span></span>  
  
1.  <span data-ttu-id="887bf-131">ソリューション エクスプ ローラーで右クリック**TestProject1**、クリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="887bf-131">In Solution Explorer, right-click **TestProject1**, and then click **Build**.</span></span>  
  
2.  <span data-ttu-id="887bf-132">メイン メニューで、をクリックして**テスト**、し、 **Windows**一覧で、クリックして**テスト ビュー**です。</span><span class="sxs-lookup"><span data-stu-id="887bf-132">On the main menu, click **Test**, and then in the **Windows** list, click **Test View**.</span></span>  
  
3.  <span data-ttu-id="887bf-133">テスト ビュー ウィンドウで右クリック**poschemainstancevalidationtest**、クリックして**選択範囲の実行**です。</span><span class="sxs-lookup"><span data-stu-id="887bf-133">In the Test View window, right-click **POSchemaInstanceValidationTest**, and then click **Run Selection**.</span></span> <span data-ttu-id="887bf-134">されることを確認**成功**テスト結果 ウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="887bf-134">Verify that you see **Passed** in the Test Results window.</span></span>  
  
4.  <span data-ttu-id="887bf-135">テスト ビュー ウィンドウで右クリック**POToInvoiceMapTest**、クリックして**選択範囲の実行**です。</span><span class="sxs-lookup"><span data-stu-id="887bf-135">In the Test View window, right-click **POToInvoiceMapTest**, and then click **Run Selection**.</span></span> <span data-ttu-id="887bf-136">されることを確認**成功**テスト結果 ウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="887bf-136">Verify that you see **Passed** in the Test Results window.</span></span>  
  
5.  <span data-ttu-id="887bf-137">テストが不合格の場合、[テスト結果] ウィンドウのテストをダブルクリックして、不合格の原因となったアサートまたは例外を確認します。</span><span class="sxs-lookup"><span data-stu-id="887bf-137">If any test fails you can double-click the test in the Test Results window to see the assert or exception that caused that test failure.</span></span>  
  
## <a name="test-code-summary"></a><span data-ttu-id="887bf-138">テスト コードのまとめ</span><span class="sxs-lookup"><span data-stu-id="887bf-138">Test Code Summary</span></span>  
 <span data-ttu-id="887bf-139">単体テストが有効にすると、 **HelloWorld**プロジェクト、c# のクラスに関連付けられている**POSchema.xsd**から派生した、 **Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**クラスです。</span><span class="sxs-lookup"><span data-stu-id="887bf-139">When unit testing was enabled for the **HelloWorld** project, the C# class associated with **POSchema.xsd** was derived from the **Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase** class.</span></span> <span data-ttu-id="887bf-140">**[Poschemainstancevalidationtest]**メソッド**TestProject1**使用、 **ValidateInstance**のメソッド、 **POSchema**にクラスPO スキーマに対する SamplePOInput.xml を検証します。</span><span class="sxs-lookup"><span data-stu-id="887bf-140">The **POSchemaInstanceValidationTest** method in **TestProject1** used the **ValidateInstance** method of the **POSchema** class to validate SamplePOInput.xml against the PO schema.</span></span>  
  
 <span data-ttu-id="887bf-141">同様に、単体テストが有効な場合の**HelloWorld**プロジェクト、c# のクラスに関連付けられている、 **POToInvoice.btm**マップの派生元の**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**クラスです。</span><span class="sxs-lookup"><span data-stu-id="887bf-141">Similarly, when unit testing was enabled for the **HelloWorld** project, the C# class associated with the **POToInvoice.btm** map was derived from the **Microsoft.BizTalk.TestTools.Mapper.TestableMapBase** class.</span></span> <span data-ttu-id="887bf-142">**POToInvoiceMaptest**使用する方法、 **TestMap**のメソッド、 **POToInvoice**同じ SamplePOInput.xml メッセージを使用してマップをテストするクラス。</span><span class="sxs-lookup"><span data-stu-id="887bf-142">The **POToInvoiceMaptest** method used the **TestMap** method of the **POToInvoice** class to test the map using the same SamplePOInput.xml message.</span></span> <span data-ttu-id="887bf-143">これにより、SampleInvoiceOutput.xml が HelloWorld ディレクトリで作成されました。</span><span class="sxs-lookup"><span data-stu-id="887bf-143">This resulted in SampleInvoiceOutput.xml being created in the HelloWorld directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="887bf-144">参照</span><span class="sxs-lookup"><span data-stu-id="887bf-144">See Also</span></span>  
 <span data-ttu-id="887bf-145">[単体テストのパイプラインを持つ機能の使用](../core/using-the-unit-testing-feature-with-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="887bf-145">[Using the Unit Testing Feature with Pipelines](../core/using-the-unit-testing-feature-with-pipelines.md) </span></span>  
 [<span data-ttu-id="887bf-146">単体テスト (Visual Studio) の操作</span><span class="sxs-lookup"><span data-stu-id="887bf-146">Working with Unit Tests (Visual Studio)</span></span>](http://go.microsoft.com/fwlink/?LinkId=128890)