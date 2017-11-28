---
title: "単体テストでのパイプライン機能を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d58bfa4-322b-455f-a062-5bd44d368f57
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5aca6e7be3c4fbeff2484f1d59454b09a4777cff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-unit-testing-feature-with-pipelines"></a><span data-ttu-id="aa152-102">パイプラインを含む単体テスト機能の使用</span><span class="sxs-lookup"><span data-stu-id="aa152-102">Using the Unit Testing Feature with Pipelines</span></span>
<span data-ttu-id="aa152-103">このトピックでは、単体テスト機能を使用して、FlatFileReceive パイプラインの例に、パイプラインの単体テストを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aa152-103">This topic demonstrates how to use the unit testing feature to add a unit test for the pipeline in the FlatFileReceive pipeline example.</span></span> <span data-ttu-id="aa152-104">パイプラインの単体テストは」で説明されている Pipeline.exe ツールに似ています。[パイプライン ツール](../core/pipeline-tools.md)です。</span><span class="sxs-lookup"><span data-stu-id="aa152-104">Pipeline unit testing is similar to the Pipeline.exe tool that is documented here: [Pipeline Tools](../core/pipeline-tools.md).</span></span> <span data-ttu-id="aa152-105">単体テストを有効にすると、**展開**から、プロジェクトのプロパティ タブ、プロジェクト内のパイプライン クラスを派生**Microsoft.BizTalk.TestTools.Pipeline.TestableReceivePipeline**です。</span><span class="sxs-lookup"><span data-stu-id="aa152-105">When you enable unit testing on the **Deployment** tab of the project properties, the pipeline class in your project is derived from **Microsoft.BizTalk.TestTools.Pipeline.TestableReceivePipeline**.</span></span>  <span data-ttu-id="aa152-106">このクラスは、Pipeline.exe ツールが公開する機能と同じ機能の一部をモデル化します。</span><span class="sxs-lookup"><span data-stu-id="aa152-106">This class models some of the same functionality exposed by the Pipeline.exe tool.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="aa152-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="aa152-107">Prerequisites</span></span>  
 <span data-ttu-id="aa152-108">最初に、FlatFileReceive サンプルを構築する手順を実行して、このサンプルに慣れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa152-108">You must first follow the steps for building the FlatFileReceive sample and become familiar with that sample.</span></span> <span data-ttu-id="aa152-109">FlatFileReceive サンプルをビルドし、ここで検出できる手順が含まれていますのドキュメント: [FlatFileReceive (BizTalk Server サンプル)](../core/flatfilereceive-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="aa152-109">The documentation that includes the steps for building the FlatFileReceive sample can be found here: [FlatFileReceive (BizTalk Server Sample)](../core/flatfilereceive-biztalk-server-sample.md).</span></span>  
  
## <a name="adding-a-unit-test-project-to-the-flatfilereceive-sample"></a><span data-ttu-id="aa152-110">FlatFileReceive サンプルへの単体テスト プロジェクトの追加</span><span class="sxs-lookup"><span data-stu-id="aa152-110">Adding a Unit Test Project to the FlatFileReceive Sample</span></span>  
  
#### <a name="to-add-a-unit-test-project-to-the-flatfilereceive-sample"></a><span data-ttu-id="aa152-111">FlatFileReceive サンプルに単体テスト プロジェクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="aa152-111">To add a unit test project to the FlatFileReceive sample</span></span>  
  
1.  <span data-ttu-id="aa152-112">Visual Studio で、FlatFileReceive.sln ソリューション ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="aa152-112">In Visual Studio, open the FlatFileReceive.sln solution file.</span></span>  
  
2.  <span data-ttu-id="aa152-113">ソリューション エクスプ ローラーで右クリックし、 **FlatFileReceive**プロジェクトをクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="aa152-113">In Solution Explorer, right-click the **FlatFileReceive** project, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="aa152-114">プロジェクト デザイナーで、をクリックして、**展開**プロパティ ページ タブとセット**単体テストを有効にする**に`True`です。</span><span class="sxs-lookup"><span data-stu-id="aa152-114">In Project Designer, click the **Deployment** property page tab and set **Enable Unit Testing** to `True`.</span></span>  
  
4.  <span data-ttu-id="aa152-115">変更内容を保存し、プロジェクト プロパティ ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="aa152-115">Close the project properties page saving the changes.</span></span>  
  
5.  <span data-ttu-id="aa152-116">メイン メニューで、をクリックして**ビルド**、クリックして**ソリューションのリビルド**です。</span><span class="sxs-lookup"><span data-stu-id="aa152-116">On the main menu, click **Build**, and then click **Rebuild Solution**.</span></span>  
  
6.  <span data-ttu-id="aa152-117">メイン メニューで、をクリックして**テスト**、クリックして**新しいテスト**です。</span><span class="sxs-lookup"><span data-stu-id="aa152-117">On the main menu, click **Test**, and then click **New Test**.</span></span>  
  
7.  <span data-ttu-id="aa152-118">**新しいテストの追加**ダイアログ ボックスで、**新しい Visual c# テスト プロジェクトを作成する**の**テスト プロジェクトに追加**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="aa152-118">In the **Add New Test** dialog box, select **Create a new Visual C# test project** for the **Add to Test Project** field.</span></span> <span data-ttu-id="aa152-119">選択**単体テスト ウィザード**で、**テンプレート**ボックスの一覧し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="aa152-119">Select **Unit Test Wizard** in the **Templates** list, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="aa152-120">**新しいテスト プロジェクト** ダイアログ ボックスで、プロジェクト名としてのままにして**TestProject1**  をクリック**作成**です。</span><span class="sxs-lookup"><span data-stu-id="aa152-120">In the **New Test Project** dialog box, leave the project name as **TestProject1** and click **Create**.</span></span>  
  
9. <span data-ttu-id="aa152-121">**単体テストの作成** ダイアログ ボックスで、種類を展開し、選択、 **FFReceivePipeline()**下でコンス トラクター、 **ffreceivepipeline()**ノード。</span><span class="sxs-lookup"><span data-stu-id="aa152-121">In the **Create Unit Tests** dialog box, expand the types and select the **FFReceivePipeline()** constructor under the **Microsoft.Samples.BizTalk.FlatFileReceive.FFReceivePipeline** node.</span></span> <span data-ttu-id="aa152-122">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa152-122">Click **OK**.</span></span>  
  
## <a name="adding-test-code-to-test-the-pipeline"></a><span data-ttu-id="aa152-123">パイプラインをテストするテスト コードの追加</span><span class="sxs-lookup"><span data-stu-id="aa152-123">Adding Test Code to Test the Pipeline</span></span>  
  
#### <a name="to-add-test-code-to-test-the-pipeline"></a><span data-ttu-id="aa152-124">パイプラインをテストするテスト コードを追加するには</span><span class="sxs-lookup"><span data-stu-id="aa152-124">To add test code to test the pipeline</span></span>  
  
1.  <span data-ttu-id="aa152-125">次の参照を追加、 **TestProject1**プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="aa152-125">Add the following references to the **TestProject1** project:</span></span>  
  
    -   <span data-ttu-id="aa152-126">BizTalk パイプライン相互運用機能</span><span class="sxs-lookup"><span data-stu-id="aa152-126">BizTalk Pipeline Interop</span></span>  
  
    -   <span data-ttu-id="aa152-127">Microsoft.BizTalk.TestTools</span><span class="sxs-lookup"><span data-stu-id="aa152-127">Microsoft.BizTalk.TestTools</span></span>  
  
    -   <span data-ttu-id="aa152-128">Microsoft XLANG/s ベース型</span><span class="sxs-lookup"><span data-stu-id="aa152-128">Microsoft XLANG/s Base Types</span></span>  
  
2.  <span data-ttu-id="aa152-129">ソリューション エクスプローラーで、FFReceivePipelineTest.cs を開き、次のディレクティブをそのファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="aa152-129">In Solution Explorer, open FFReceivePipelineTest.cs and add the following directives to the top of that file:</span></span>  
  
    ```  
    using System.IO;  
    using System.Collections.Specialized;  
    using System.Collections.Generic;  
    ```  
  
3.  <span data-ttu-id="aa152-130">ファイルの一番下までスクロールし、置換、 **FFReceivePipelineConstructorTest**メソッドを次のコードは、パイプラインをテストする前に、パイプラインの入力が存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="aa152-130">Scroll to the bottom of the file and replace the **FFReceivePipelineConstructorTest** method with the following code, which verifies that the pipeline inputs exist before testing the pipeline.</span></span> <span data-ttu-id="aa152-131">また、このコードは、フラット ファイル スキーマに準拠したメッセージが生成されることも検証します。</span><span class="sxs-lookup"><span data-stu-id="aa152-131">This code also verifies that a message conforming to the flat file schema is generated.</span></span>  
  
    ```  
    [TestMethod()]  
    public void FFReceivePipelineUnitTest()  
    {  
        //=== Pipeline class derived from TestableReceivePipeline ===//  
        FFReceivePipeline target = new FFReceivePipeline();  
  
        //=== Collection of messages to test the flat file pipeline ===//  
        StringCollection documents = new StringCollection();  
        string strSourcePO_XML = @".\..\..\..\FlatFileReceive_in.txt";  
        Assert.IsTrue(File.Exists(strSourcePO_XML));  
        documents.Add(strSourcePO_XML);  
  
        //=== Only a body part for this test message so an empty ===//  
        //=== collection will be passed.                         ===//  
        StringCollection parts = new StringCollection();  
  
        //=== Dictionary mapping the schema to the namespace and type ===//  
        //=== as displayed in the properties window for the *.xsd     ===//  
        Dictionary<string, string> schemas = new Dictionary<string, string>();  
        string SchemaFile = @".\..\..\..\PO.xsd";  
        Assert.IsTrue(File.Exists(SchemaFile));  
        schemas.Add("Microsoft.Samples.BizTalk.FlatFileReceive.PO", SchemaFile);  
  
        //=== Test the execution of the pipeline using the inputs ===//  
        target.TestPipeline(documents, parts, schemas);  
  
        //=== Validate that the pipeline test produced the message ===//  
        //=== which conforms to the schema.                        ===//  
        string[] strMessages = Directory.GetFiles(testContextInstance.TestDir + "\\out","Message*.out");              
        Assert.IsTrue(strMessages.Length > 0);                          
        PO PO_target = new PO();  
        foreach(string outFile in strMessages)  
        {  
          Assert.IsTrue(PO_target.ValidateInstance(outFile,Microsoft.BizTalk.TestTools.Schema.OutputInstanceType.XML));  
        }                       
    }  
    ```  
  
## <a name="building-and-running-the-unit-test"></a><span data-ttu-id="aa152-132">単体テストのビルドと実行</span><span class="sxs-lookup"><span data-stu-id="aa152-132">Building and Running the Unit Test</span></span>  
  
#### <a name="to-build-and-run-the-unit-test"></a><span data-ttu-id="aa152-133">単体テストをビルドして実行するには</span><span class="sxs-lookup"><span data-stu-id="aa152-133">To build and run the unit test</span></span>  
  
1.  <span data-ttu-id="aa152-134">ソリューション エクスプ ローラーで右クリック**TestProject1**、クリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="aa152-134">In Solution Explorer, right-click **TestProject1**, and then click **Build**.</span></span>  
  
2.  <span data-ttu-id="aa152-135">メイン メニューで、をクリックして**テスト**、し、 **Windows**一覧で、クリックして**テスト ビュー**です。</span><span class="sxs-lookup"><span data-stu-id="aa152-135">On the main menu, click **Test**, and then in the **Windows** list, click **Test View**.</span></span>  
  
3.  <span data-ttu-id="aa152-136">テスト ビュー ウィンドウで右クリック**ffreceivepipelineunittest**、クリックして**選択範囲の実行**です。</span><span class="sxs-lookup"><span data-stu-id="aa152-136">In the Test View window, right-click **FFReceivePipelineUnitTest**, and then click **Run Selection**.</span></span> <span data-ttu-id="aa152-137">されることを確認**成功**テスト結果 ウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="aa152-137">Verify that you see **Passed** in the Test Results window.</span></span>  
  
4.  <span data-ttu-id="aa152-138">TestResults ディレクトリで、*.out ファイルを調べます。</span><span class="sxs-lookup"><span data-stu-id="aa152-138">In the TestResults directory examine the *.out file.</span></span> <span data-ttu-id="aa152-139">このファイルには、パイプラインによって処理された新しいメッセージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="aa152-139">This file should contain the new message processed by the pipeline.</span></span>  <span data-ttu-id="aa152-140">このファイルは次のようなディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="aa152-140">It should be located in a directory similar to the following:</span></span>  
  
     <span data-ttu-id="aa152-141">C:\Program files \microsoft BizTalk Server\<バージョン > \SDK\Samples\Pipelines\AssemblerDisassembler\FlatFileReceive\TestResults\Wes_BTS2009Svr 2009-02-04 09_01_04\Out</span><span class="sxs-lookup"><span data-stu-id="aa152-141">C:\Program Files\Microsoft BizTalk Server \<version>\SDK\Samples\Pipelines\AssemblerDisassembler\FlatFileReceive\TestResults\Wes_BTS2009Svr 2009-02-04 09_01_04\Out</span></span>  
  
     <span data-ttu-id="aa152-142">処理されたメッセージは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="aa152-142">The processed message should look similar to the following:</span></span>  
  
    ```  
    <purchaseOrder orderDate="1999-10-20" xmlns="http://FlatFileRecieve.PO">  
  
      <shipTo country="US" xmlns="">  
        <name>Alice Smith</name>  
        <street>123 Maple Street</street>  
        <city>Mill Valley</city>  
        <state>CA</state>  
        <zip>90952</zip>  
      </shipTo>  
  
      <billTo country="US" xmlns="">  
        <name>Robert Smith</name>  
        <street>8 Oak Avenue</street>  
        <city>Old Town</city>  
        <state>PA</state>  
        <zip>95819</zip>  
      </billTo>  
  
      <comment>Hurry, my lawn is going wild!</comment>  
  
      <items xmlns="">  
  
        <item partNum="872-AA">  
          <productName>Lawnmower</productName>  
          <quantity>1</quantity>  
          <USPrice>148.95</USPrice>  
          <comment xmlns="http://FlatFileRecieve.PO">Confirm this is electric</comment>  
        </item>  
  
        <item partNum="926-AA">  
          <productName>Baby Monitor</productName>  
          <quantity>1</quantity>  
          <USPrice>39.98</USPrice>  
          <comment xmlns="http://FlatFileRecieve.PO">Confirm this is electric</comment>  
          <shipDate>1999-05-21</shipDate>  
        </item>  
  
      </items>  
  
    </purchaseOrder>  
    ```  
  
5.  <span data-ttu-id="aa152-143">テストが不合格の場合、[テスト結果] ウィンドウのテストをダブルクリックして、不合格の原因となったアサートまたは例外を確認します。</span><span class="sxs-lookup"><span data-stu-id="aa152-143">If any test fails you can double-click the test in the Test Results window to see the assert or exception that caused that test failure.</span></span>  
  
## <a name="test-code-summary"></a><span data-ttu-id="aa152-144">テスト コードのまとめ</span><span class="sxs-lookup"><span data-stu-id="aa152-144">Test Code Summary</span></span>  
 <span data-ttu-id="aa152-145">単体テストが有効にすると、 **FlatFileReceive**プロジェクト、 **FFReceivePipeline** c# クラスに関連付けられている**FFReceivePipeline.btp** から派生しました**Microsoft.BizTalk.TestTools.Pipeline.TestableReceivePipeline**クラスです。</span><span class="sxs-lookup"><span data-stu-id="aa152-145">When unit testing was enabled for the **FlatFileReceive** project, the **FFReceivePipeline** C# class associated with **FFReceivePipeline.btp** was derived from the **Microsoft.BizTalk.TestTools.Pipeline.TestableReceivePipeline** class.</span></span> <span data-ttu-id="aa152-146">**[Ffreceivepipelineunittest]**メソッド**TestProject1**使用、 **TestPipeline**メソッドを**FFReceivePipeline**継承テストするフラット ファイル受信パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa152-146">The **FFReceivePipelineUnitTest** method in **TestProject1** used the **TestPipeline** method that **FFReceivePipeline** inherited to test the flat file receive pipeline.</span></span> <span data-ttu-id="aa152-147">パイプラインでメッセージが処理された後、出力メッセージがフラット ファイル スキーマと照合して検証されます。</span><span class="sxs-lookup"><span data-stu-id="aa152-147">After the pipeline processed the message, the output message was validated against the flat file schema.</span></span> <span data-ttu-id="aa152-148">パラメーター、 **TestPipeline**メソッドは、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="aa152-148">The parameters for the **TestPipeline** method are as follows:</span></span>  
  
|<span data-ttu-id="aa152-149">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="aa152-149">Parameter Name</span></span>|<span data-ttu-id="aa152-150">Description</span><span class="sxs-lookup"><span data-stu-id="aa152-150">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="aa152-151">Documents</span><span class="sxs-lookup"><span data-stu-id="aa152-151">Documents</span></span>|<span data-ttu-id="aa152-152">パイプラインによって処理されるメッセージを格納する StringCollection。</span><span class="sxs-lookup"><span data-stu-id="aa152-152">StringCollection containing messages to be processed by the pipeline.</span></span>|  
|<span data-ttu-id="aa152-153">要素</span><span class="sxs-lookup"><span data-stu-id="aa152-153">Parts</span></span>|<span data-ttu-id="aa152-154">メッセージの部分を格納する StringCollection。</span><span class="sxs-lookup"><span data-stu-id="aa152-154">StringCollection containing the parts for the messages.</span></span>|  
|<span data-ttu-id="aa152-155">スキーマ</span><span class="sxs-lookup"><span data-stu-id="aa152-155">Schemas</span></span>|<span data-ttu-id="aa152-156">対応する各メッセージの種類をマップするディクショナリ マッピング\*.xsd スキーマ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="aa152-156">Dictionary mapping used to map each message type to its corresponding \*.xsd schema file.</span></span> <span data-ttu-id="aa152-157">キーが形式である必要があります**Namespace.Type**です。</span><span class="sxs-lookup"><span data-stu-id="aa152-157">The key must be in the format **Namespace.Type**.</span></span> <span data-ttu-id="aa152-158">[プロパティ] ウィンドウから、名前空間と型の使用に注意してください、 \*.xsd ファイルで[!INCLUDE[vs2010](../includes/vs2010-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="aa152-158">The namespace and type used should be noted from the properties window for the \*.xsd file in [!INCLUDE[vs2010](../includes/vs2010-md.md)].</span></span> <span data-ttu-id="aa152-159">次のスクリーンショットを見てください。</span><span class="sxs-lookup"><span data-stu-id="aa152-159">See the screenshot below.</span></span><br /><br /> ![](../core/media/namespaceandtypeforxsd.gif "NamespaceAndTypeForXSD")<br /><br /> <span data-ttu-id="aa152-160">**Namespace および XSD ファイルのプロパティ ウィンドウから公開されている型。**</span><span class="sxs-lookup"><span data-stu-id="aa152-160">**Namespace and type exposed from the properties window of an XSD file.**</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa152-161">参照</span><span class="sxs-lookup"><span data-stu-id="aa152-161">See Also</span></span>  
 <span data-ttu-id="aa152-162">[単体テストのスキーマおよびマップを持つ機能の使用](../core/using-the-unit-testing-feature-with-schemas-and-maps.md) </span><span class="sxs-lookup"><span data-stu-id="aa152-162">[Using the Unit Testing Feature with Schemas and Maps](../core/using-the-unit-testing-feature-with-schemas-and-maps.md) </span></span>  
 [<span data-ttu-id="aa152-163">単体テスト (Visual Studio) の操作</span><span class="sxs-lookup"><span data-stu-id="aa152-163">Working with Unit Tests (Visual Studio)</span></span>](http://go.microsoft.com/fwlink/?LinkId=128890)