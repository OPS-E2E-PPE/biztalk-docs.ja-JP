---
title: 単体テストのパイプラインを持つ機能を使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d58bfa4-322b-455f-a062-5bd44d368f57
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7deaaa8d0ca60f13e5f3b835a91a31e06cdf2cbd
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826327"
---
# <a name="using-the-unit-testing-feature-with-pipelines"></a><span data-ttu-id="15e34-102">パイプラインを含む単体テスト機能の使用</span><span class="sxs-lookup"><span data-stu-id="15e34-102">Using the Unit Testing Feature with Pipelines</span></span>
<span data-ttu-id="15e34-103">このトピックでは、単体テスト機能を使用して、FlatFileReceive パイプラインの例に、パイプラインの単体テストを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="15e34-103">This topic demonstrates how to use the unit testing feature to add a unit test for the pipeline in the FlatFileReceive pipeline example.</span></span> <span data-ttu-id="15e34-104">パイプラインの単体テストはここに記載されている Pipeline.exe ツールに似ています。[パイプライン ツール](../core/pipeline-tools.md)します。</span><span class="sxs-lookup"><span data-stu-id="15e34-104">Pipeline unit testing is similar to the Pipeline.exe tool that is documented here: [Pipeline Tools](../core/pipeline-tools.md).</span></span> <span data-ttu-id="15e34-105">単体テストを有効にすると、**展開**プロジェクトのプロパティをプロジェクト内のパイプライン クラスのタブがから派生した**Microsoft.BizTalk.TestTools.Pipeline.TestableReceivePipeline**します。</span><span class="sxs-lookup"><span data-stu-id="15e34-105">When you enable unit testing on the **Deployment** tab of the project properties, the pipeline class in your project is derived from **Microsoft.BizTalk.TestTools.Pipeline.TestableReceivePipeline**.</span></span>  <span data-ttu-id="15e34-106">このクラスは、Pipeline.exe ツールが公開する機能と同じ機能の一部をモデル化します。</span><span class="sxs-lookup"><span data-stu-id="15e34-106">This class models some of the same functionality exposed by the Pipeline.exe tool.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="15e34-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="15e34-107">Prerequisites</span></span>  
 <span data-ttu-id="15e34-108">最初に、FlatFileReceive サンプルを構築する手順を実行して、このサンプルに慣れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="15e34-108">You must first follow the steps for building the FlatFileReceive sample and become familiar with that sample.</span></span> <span data-ttu-id="15e34-109">FlatFileReceive サンプルのビルドはこちらの手順を含むドキュメント: [FlatFileReceive (BizTalk Server サンプル)](../core/flatfilereceive-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="15e34-109">The documentation that includes the steps for building the FlatFileReceive sample can be found here: [FlatFileReceive (BizTalk Server Sample)](../core/flatfilereceive-biztalk-server-sample.md).</span></span>  
  
## <a name="adding-a-unit-test-project-to-the-flatfilereceive-sample"></a><span data-ttu-id="15e34-110">FlatFileReceive サンプルへの単体テスト プロジェクトの追加</span><span class="sxs-lookup"><span data-stu-id="15e34-110">Adding a Unit Test Project to the FlatFileReceive Sample</span></span>  
  
#### <a name="to-add-a-unit-test-project-to-the-flatfilereceive-sample"></a><span data-ttu-id="15e34-111">FlatFileReceive サンプルに単体テスト プロジェクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="15e34-111">To add a unit test project to the FlatFileReceive sample</span></span>  
  
1.  <span data-ttu-id="15e34-112">Visual Studio で、FlatFileReceive.sln ソリューション ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="15e34-112">In Visual Studio, open the FlatFileReceive.sln solution file.</span></span>  
  
2.  <span data-ttu-id="15e34-113">ソリューション エクスプ ローラーで右クリックし、 **FlatFileReceive**プロジェクトをクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="15e34-113">In Solution Explorer, right-click the **FlatFileReceive** project, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="15e34-114">プロジェクト デザイナーで、をクリックして、**展開**プロパティ ページのタブおよびセット**Unit Testing を有効にする**に`True`します。</span><span class="sxs-lookup"><span data-stu-id="15e34-114">In Project Designer, click the **Deployment** property page tab and set **Enable Unit Testing** to `True`.</span></span>  
  
4.  <span data-ttu-id="15e34-115">変更内容を保存し、プロジェクト プロパティ ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="15e34-115">Close the project properties page saving the changes.</span></span>  
  
5.  <span data-ttu-id="15e34-116">メイン メニューで、次のようにクリックします。**ビルド**、 をクリックし、**ソリューションのリビルド**します。</span><span class="sxs-lookup"><span data-stu-id="15e34-116">On the main menu, click **Build**, and then click **Rebuild Solution**.</span></span>  
  
6.  <span data-ttu-id="15e34-117">メイン メニューで、次のようにクリックします。**テスト**、 をクリックし、**新しいテスト**します。</span><span class="sxs-lookup"><span data-stu-id="15e34-117">On the main menu, click **Test**, and then click **New Test**.</span></span>  
  
7.  <span data-ttu-id="15e34-118">**新しいテストの追加**ダイアログ ボックスで、**新しいビジュアルを作成C#テスト プロジェクト**の**テスト プロジェクトに追加**フィールド。</span><span class="sxs-lookup"><span data-stu-id="15e34-118">In the **Add New Test** dialog box, select **Create a new Visual C# test project** for the **Add to Test Project** field.</span></span> <span data-ttu-id="15e34-119">選択**単体テスト ウィザード**で、**テンプレート**ボックスの一覧をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="15e34-119">Select **Unit Test Wizard** in the **Templates** list, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="15e34-120">**新しいテスト プロジェクト** ダイアログ ボックスで、プロジェクト名としてのままに**TestProject1**  をクリック**作成**です。</span><span class="sxs-lookup"><span data-stu-id="15e34-120">In the **New Test Project** dialog box, leave the project name as **TestProject1** and click **Create**.</span></span>  
  
9. <span data-ttu-id="15e34-121">**単体テストの作成** ダイアログ ボックスで、型を展開し、選択、 **FFReceivePipeline()** 下でコンストラクター、 **ffreceivepipeline()** ノード。</span><span class="sxs-lookup"><span data-stu-id="15e34-121">In the **Create Unit Tests** dialog box, expand the types and select the **FFReceivePipeline()** constructor under the **Microsoft.Samples.BizTalk.FlatFileReceive.FFReceivePipeline** node.</span></span> <span data-ttu-id="15e34-122">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15e34-122">Click **OK**.</span></span>  
  
## <a name="adding-test-code-to-test-the-pipeline"></a><span data-ttu-id="15e34-123">パイプラインをテストするテスト コードの追加</span><span class="sxs-lookup"><span data-stu-id="15e34-123">Adding Test Code to Test the Pipeline</span></span>  
  
#### <a name="to-add-test-code-to-test-the-pipeline"></a><span data-ttu-id="15e34-124">パイプラインをテストするテスト コードを追加するには</span><span class="sxs-lookup"><span data-stu-id="15e34-124">To add test code to test the pipeline</span></span>  
  
1.  <span data-ttu-id="15e34-125">次の参照を追加、 **TestProject1**プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="15e34-125">Add the following references to the **TestProject1** project:</span></span>  
  
    -   <span data-ttu-id="15e34-126">BizTalk パイプライン相互運用機能</span><span class="sxs-lookup"><span data-stu-id="15e34-126">BizTalk Pipeline Interop</span></span>  
  
    -   <span data-ttu-id="15e34-127">Microsoft.BizTalk.TestTools</span><span class="sxs-lookup"><span data-stu-id="15e34-127">Microsoft.BizTalk.TestTools</span></span>  
  
    -   <span data-ttu-id="15e34-128">Microsoft XLANG/s ベース型</span><span class="sxs-lookup"><span data-stu-id="15e34-128">Microsoft XLANG/s Base Types</span></span>  
  
2.  <span data-ttu-id="15e34-129">ソリューション エクスプローラーで、FFReceivePipelineTest.cs を開き、次のディレクティブをそのファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="15e34-129">In Solution Explorer, open FFReceivePipelineTest.cs and add the following directives to the top of that file:</span></span>  
  
    ```csharp
    using System.IO;  
    using System.Collections.Specialized;  
    using System.Collections.Generic;  
    ```  
  
3.  <span data-ttu-id="15e34-130">ファイルの一番下までスクロールし、置換、 **FFReceivePipelineConstructorTest**メソッドを次のコードは、パイプラインをテストする前に、パイプラインの入力が存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="15e34-130">Scroll to the bottom of the file and replace the **FFReceivePipelineConstructorTest** method with the following code, which verifies that the pipeline inputs exist before testing the pipeline.</span></span> <span data-ttu-id="15e34-131">また、このコードは、フラット ファイル スキーマに準拠したメッセージが生成されることも検証します。</span><span class="sxs-lookup"><span data-stu-id="15e34-131">This code also verifies that a message conforming to the flat file schema is generated.</span></span>  
  
    ```csharp
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
  
## <a name="building-and-running-the-unit-test"></a><span data-ttu-id="15e34-132">単体テストのビルドと実行</span><span class="sxs-lookup"><span data-stu-id="15e34-132">Building and Running the Unit Test</span></span>  
  
#### <a name="to-build-and-run-the-unit-test"></a><span data-ttu-id="15e34-133">単体テストをビルドして実行するには</span><span class="sxs-lookup"><span data-stu-id="15e34-133">To build and run the unit test</span></span>  
  
1.  <span data-ttu-id="15e34-134">ソリューション エクスプ ローラーで右クリックして**TestProject1**、 をクリックし、**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="15e34-134">In Solution Explorer, right-click **TestProject1**, and then click **Build**.</span></span>  
  
2.  <span data-ttu-id="15e34-135">メイン メニューで、次のようにクリックします。**テスト**、し、 **Windows**一覧で、**テスト ビュー**します。</span><span class="sxs-lookup"><span data-stu-id="15e34-135">On the main menu, click **Test**, and then in the **Windows** list, click **Test View**.</span></span>  
  
3.  <span data-ttu-id="15e34-136">テスト ビュー ウィンドウで右クリック**ffreceivepipelineunittest**、 をクリックし、**選択範囲の実行**します。</span><span class="sxs-lookup"><span data-stu-id="15e34-136">In the Test View window, right-click **FFReceivePipelineUnitTest**, and then click **Run Selection**.</span></span> <span data-ttu-id="15e34-137">あることを確認**成功**テスト結果 ウィンドウにします。</span><span class="sxs-lookup"><span data-stu-id="15e34-137">Verify that you see **Passed** in the Test Results window.</span></span>  
  
4.  <span data-ttu-id="15e34-138">TestResults ディレクトリの確認、 \*.out ファイル。</span><span class="sxs-lookup"><span data-stu-id="15e34-138">In the TestResults directory examine the \*.out file.</span></span> <span data-ttu-id="15e34-139">このファイルには、パイプラインによって処理された新しいメッセージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="15e34-139">This file should contain the new message processed by the pipeline.</span></span>  <span data-ttu-id="15e34-140">このファイルは次のようなディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="15e34-140">It should be located in a directory similar to the following:</span></span>  
  
     <span data-ttu-id="15e34-141">C:\Program files \microsoft BizTalk Server\<バージョン\>\SDK\Samples\Pipelines\AssemblerDisassembler\FlatFileReceive\TestResults\Wes_BTS2009Svr 2009-02-04 09_01_04\Out</span><span class="sxs-lookup"><span data-stu-id="15e34-141">C:\Program Files\Microsoft BizTalk Server \<version\>\SDK\Samples\Pipelines\AssemblerDisassembler\FlatFileReceive\TestResults\Wes_BTS2009Svr 2009-02-04 09_01_04\Out</span></span>  
  
     <span data-ttu-id="15e34-142">処理されたメッセージは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="15e34-142">The processed message should look similar to the following:</span></span>  
  
    ```xml
    <purchaseOrder orderDate="1999-10-20" xmlns="http://FlatFileReceive.PO">  
  
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
          <comment xmlns="http://FlatFileReceive.PO">Confirm this is electric</comment>  
        </item>  
  
        <item partNum="926-AA">  
          <productName>Baby Monitor</productName>  
          <quantity>1</quantity>  
          <USPrice>39.98</USPrice>  
          <comment xmlns="http://FlatFileReceive.PO">Confirm this is electric</comment>  
          <shipDate>1999-05-21</shipDate>  
        </item>  
  
      </items>  
  
    </purchaseOrder>  
    ```  
  
5.  <span data-ttu-id="15e34-143">テストが不合格の場合、[テスト結果] ウィンドウのテストをダブルクリックして、不合格の原因となったアサートまたは例外を確認します。</span><span class="sxs-lookup"><span data-stu-id="15e34-143">If any test fails you can double-click the test in the Test Results window to see the assert or exception that caused that test failure.</span></span>  
  
## <a name="test-code-summary"></a><span data-ttu-id="15e34-144">テスト コードのまとめ</span><span class="sxs-lookup"><span data-stu-id="15e34-144">Test Code Summary</span></span>  
 <span data-ttu-id="15e34-145">単体テストが有効な場合に、 **FlatFileReceive**プロジェクト、 **FFReceivePipeline** C#クラスに関連付けられている**FFReceivePipeline.btp**から派生しました**Microsoft.BizTalk.TestTools.Pipeline.TestableReceivePipeline**クラス。</span><span class="sxs-lookup"><span data-stu-id="15e34-145">When unit testing was enabled for the **FlatFileReceive** project, the **FFReceivePipeline** C# class associated with **FFReceivePipeline.btp** was derived from the **Microsoft.BizTalk.TestTools.Pipeline.TestableReceivePipeline** class.</span></span> <span data-ttu-id="15e34-146">**[Ffreceivepipelineunittest]** メソッド**TestProject1**使用、 **TestPipeline**メソッドを**FFReceivePipeline**継承テストするフラット ファイル受信パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="15e34-146">The **FFReceivePipelineUnitTest** method in **TestProject1** used the **TestPipeline** method that **FFReceivePipeline** inherited to test the flat file receive pipeline.</span></span> <span data-ttu-id="15e34-147">パイプラインでメッセージが処理された後、出力メッセージがフラット ファイル スキーマと照合して検証されます。</span><span class="sxs-lookup"><span data-stu-id="15e34-147">After the pipeline processed the message, the output message was validated against the flat file schema.</span></span> <span data-ttu-id="15e34-148">パラメーター、 **TestPipeline**メソッドは、次のとおり。</span><span class="sxs-lookup"><span data-stu-id="15e34-148">The parameters for the **TestPipeline** method are as follows:</span></span>  
  
|<span data-ttu-id="15e34-149">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="15e34-149">Parameter Name</span></span>|<span data-ttu-id="15e34-150">説明</span><span class="sxs-lookup"><span data-stu-id="15e34-150">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="15e34-151">Documents</span><span class="sxs-lookup"><span data-stu-id="15e34-151">Documents</span></span>|<span data-ttu-id="15e34-152">パイプラインによって処理されるメッセージを格納する StringCollection。</span><span class="sxs-lookup"><span data-stu-id="15e34-152">StringCollection containing messages to be processed by the pipeline.</span></span>|  
|<span data-ttu-id="15e34-153">要素</span><span class="sxs-lookup"><span data-stu-id="15e34-153">Parts</span></span>|<span data-ttu-id="15e34-154">メッセージの部分を格納する StringCollection。</span><span class="sxs-lookup"><span data-stu-id="15e34-154">StringCollection containing the parts for the messages.</span></span>|  
|<span data-ttu-id="15e34-155">スキーマ</span><span class="sxs-lookup"><span data-stu-id="15e34-155">Schemas</span></span>|<span data-ttu-id="15e34-156">対応する各メッセージの種類をマップするために使用するディクショナリ マッピング\*スキーマの .xsd ファイルです。</span><span class="sxs-lookup"><span data-stu-id="15e34-156">Dictionary mapping used to map each message type to its corresponding \*.xsd schema file.</span></span> <span data-ttu-id="15e34-157">キーは、の形式で指定する必要があります**Namespace.Type**します。</span><span class="sxs-lookup"><span data-stu-id="15e34-157">The key must be in the format **Namespace.Type**.</span></span> <span data-ttu-id="15e34-158">[プロパティ] ウィンドウから、名前空間と型の使用に注意してください、 \*Visual Studio での .xsd ファイルです。</span><span class="sxs-lookup"><span data-stu-id="15e34-158">The namespace and type used should be noted from the properties window for the \*.xsd file in Visual Studio.</span></span> <span data-ttu-id="15e34-159">次のスクリーンショットを見てください。</span><span class="sxs-lookup"><span data-stu-id="15e34-159">See the screenshot below.</span></span><br /><br /> <span data-ttu-id="15e34-160">![](../core/media/namespaceandtypeforxsd.gif "NamespaceAndTypeForXSD")</span><span class="sxs-lookup"><span data-stu-id="15e34-160">![](../core/media/namespaceandtypeforxsd.gif "NamespaceAndTypeForXSD")</span></span><br /><br /> <span data-ttu-id="15e34-161">**Namespace および XSD ファイルのプロパティ ウィンドウから公開される型。**</span><span class="sxs-lookup"><span data-stu-id="15e34-161">**Namespace and type exposed from the properties window of an XSD file.**</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="15e34-162">参照</span><span class="sxs-lookup"><span data-stu-id="15e34-162">See Also</span></span>  
 <span data-ttu-id="15e34-163">[単体テストのスキーマとマップを含む機能を使用します。](../core/using-the-unit-testing-feature-with-schemas-and-maps.md) </span><span class="sxs-lookup"><span data-stu-id="15e34-163">[Using the Unit Testing Feature with Schemas and Maps](../core/using-the-unit-testing-feature-with-schemas-and-maps.md) </span></span>  
 [<span data-ttu-id="15e34-164">単体テスト (Visual Studio) の操作</span><span class="sxs-lookup"><span data-stu-id="15e34-164">Working with Unit Tests (Visual Studio)</span></span>](http://go.microsoft.com/fwlink/?LinkId=128890)