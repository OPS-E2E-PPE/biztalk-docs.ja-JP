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
# <a name="using-the-unit-testing-feature-with-pipelines"></a>パイプラインを含む単体テスト機能の使用
このトピックでは、単体テスト機能を使用して、FlatFileReceive パイプラインの例に、パイプラインの単体テストを追加する方法について説明します。 パイプラインの単体テストはここに記載されている Pipeline.exe ツールに似ています。[パイプライン ツール](../core/pipeline-tools.md)します。 単体テストを有効にすると、**展開**プロジェクトのプロパティをプロジェクト内のパイプライン クラスのタブがから派生した**Microsoft.BizTalk.TestTools.Pipeline.TestableReceivePipeline**します。  このクラスは、Pipeline.exe ツールが公開する機能と同じ機能の一部をモデル化します。  
  
## <a name="prerequisites"></a>前提条件  
 最初に、FlatFileReceive サンプルを構築する手順を実行して、このサンプルに慣れる必要があります。 FlatFileReceive サンプルのビルドはこちらの手順を含むドキュメント: [FlatFileReceive (BizTalk Server サンプル)](../core/flatfilereceive-biztalk-server-sample.md)します。  
  
## <a name="adding-a-unit-test-project-to-the-flatfilereceive-sample"></a>FlatFileReceive サンプルへの単体テスト プロジェクトの追加  
  
#### <a name="to-add-a-unit-test-project-to-the-flatfilereceive-sample"></a>FlatFileReceive サンプルに単体テスト プロジェクトを追加するには  
  
1.  Visual Studio で、FlatFileReceive.sln ソリューション ファイルを開きます。  
  
2.  ソリューション エクスプ ローラーで右クリックし、 **FlatFileReceive**プロジェクトをクリックして**プロパティ**します。  
  
3.  プロジェクト デザイナーで、をクリックして、**展開**プロパティ ページのタブおよびセット**Unit Testing を有効にする**に`True`します。  
  
4.  変更内容を保存し、プロジェクト プロパティ ページを閉じます。  
  
5.  メイン メニューで、次のようにクリックします。**ビルド**、 をクリックし、**ソリューションのリビルド**します。  
  
6.  メイン メニューで、次のようにクリックします。**テスト**、 をクリックし、**新しいテスト**します。  
  
7.  **新しいテストの追加**ダイアログ ボックスで、**新しいビジュアルを作成C#テスト プロジェクト**の**テスト プロジェクトに追加**フィールド。 選択**単体テスト ウィザード**で、**テンプレート**ボックスの一覧をクリックして**OK**します。  
  
8.  **新しいテスト プロジェクト** ダイアログ ボックスで、プロジェクト名としてのままに**TestProject1**  をクリック**作成**です。  
  
9. **単体テストの作成** ダイアログ ボックスで、型を展開し、選択、 **FFReceivePipeline()** 下でコンス トラクター、 **ffreceivepipeline()** ノード。 **[OK]** をクリックします。  
  
## <a name="adding-test-code-to-test-the-pipeline"></a>パイプラインをテストするテスト コードの追加  
  
#### <a name="to-add-test-code-to-test-the-pipeline"></a>パイプラインをテストするテスト コードを追加するには  
  
1.  次の参照を追加、 **TestProject1**プロジェクト。  
  
    -   BizTalk パイプライン相互運用機能  
  
    -   Microsoft.BizTalk.TestTools  
  
    -   Microsoft XLANG/s ベース型  
  
2.  ソリューション エクスプローラーで、FFReceivePipelineTest.cs を開き、次のディレクティブをそのファイルの先頭に追加します。  
  
    ```csharp
    using System.IO;  
    using System.Collections.Specialized;  
    using System.Collections.Generic;  
    ```  
  
3.  ファイルの一番下までスクロールし、置換、 **FFReceivePipelineConstructorTest**メソッドを次のコードは、パイプラインをテストする前に、パイプラインの入力が存在することを確認します。 また、このコードは、フラット ファイル スキーマに準拠したメッセージが生成されることも検証します。  
  
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
  
## <a name="building-and-running-the-unit-test"></a>単体テストのビルドと実行  
  
#### <a name="to-build-and-run-the-unit-test"></a>単体テストをビルドして実行するには  
  
1.  ソリューション エクスプ ローラーで右クリックして**TestProject1**、 をクリックし、**ビルド**します。  
  
2.  メイン メニューで、次のようにクリックします。**テスト**、し、 **Windows**一覧で、**テスト ビュー**します。  
  
3.  テスト ビュー ウィンドウで右クリック**ffreceivepipelineunittest**、 をクリックし、**選択範囲の実行**します。 あることを確認**成功**テスト結果 ウィンドウにします。  
  
4.  TestResults ディレクトリの確認、 \*.out ファイル。 このファイルには、パイプラインによって処理された新しいメッセージが含まれています。  このファイルは次のようなディレクトリにあります。  
  
     C:\Program files \microsoft BizTalk Server\<バージョン\>\SDK\Samples\Pipelines\AssemblerDisassembler\FlatFileReceive\TestResults\Wes_BTS2009Svr 2009-02-04 09_01_04\Out  
  
     処理されたメッセージは次のようになります。  
  
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
  
5.  テストが不合格の場合、[テスト結果] ウィンドウのテストをダブルクリックして、不合格の原因となったアサートまたは例外を確認します。  
  
## <a name="test-code-summary"></a>テスト コードのまとめ  
 単体テストが有効な場合に、 **FlatFileReceive**プロジェクト、 **FFReceivePipeline** C#クラスに関連付けられている**FFReceivePipeline.btp**から派生しました**Microsoft.BizTalk.TestTools.Pipeline.TestableReceivePipeline**クラス。 **[Ffreceivepipelineunittest]** メソッド**TestProject1**使用、 **TestPipeline**メソッドを**FFReceivePipeline**継承テストするフラット ファイル受信パイプラインを使用します。 パイプラインでメッセージが処理された後、出力メッセージがフラット ファイル スキーマと照合して検証されます。 パラメーター、 **TestPipeline**メソッドは、次のとおり。  
  
|[パラメーター名]|説明|  
|--------------------|-----------------|  
|Documents|パイプラインによって処理されるメッセージを格納する StringCollection。|  
|要素|メッセージの部分を格納する StringCollection。|  
|スキーマ|対応する各メッセージの種類をマップするために使用するディクショナリ マッピング\*スキーマの .xsd ファイルです。 キーは、の形式で指定する必要があります**Namespace.Type**します。 [プロパティ] ウィンドウから、名前空間と型の使用に注意してください、 \*Visual Studio での .xsd ファイルです。 次のスクリーンショットを見てください。<br /><br /> ![](../core/media/namespaceandtypeforxsd.gif "NamespaceAndTypeForXSD")<br /><br /> **Namespace および XSD ファイルのプロパティ ウィンドウから公開される型。**|  
  
## <a name="see-also"></a>参照  
 [単体テストのスキーマとマップを含む機能を使用します。](../core/using-the-unit-testing-feature-with-schemas-and-maps.md)   
 [単体テスト (Visual Studio) の操作](http://go.microsoft.com/fwlink/?LinkId=128890)