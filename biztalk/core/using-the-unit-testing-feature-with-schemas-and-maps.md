---
title: 単体テストのスキーマとマップを含む機能を使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29bcb159-ffdb-44b9-a3ff-565973d41797
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 576974b71b5f5312fdcea792458b86ea1590d42d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302827"
---
# <a name="using-the-unit-testing-feature-with-schemas-and-maps"></a>単体テストのスキーマとマップを含む機能を使用します。
このトピックでは、単体テスト機能を使用して、HelloWorld オーケストレーションの例では、スキーマやマップの単体テストを追加する方法を示します。  
  
> [!NOTE]
>  単体テストのマップの機能を現時点では、複数の入力マップはサポートされていません。  
  
## <a name="prerequisites"></a>前提条件  
 まず、HelloWorld サンプルを構築するための手順に従ってください。 これらの手順はここにあります。[HelloWorld (BizTalk Server サンプル)](../core/helloworld-biztalk-server-sample.md)  
  
### <a name="adding-a-unit-test-project-to-the-helloworld-sample"></a>HelloWorld サンプルへの単体テスト プロジェクトの追加  
  
1.  Visual Studio で、HelloWorld.sln ソリューション ファイルを開きます。  
  
2.  ソリューション エクスプ ローラーで右クリックし、 **HelloWorld**プロジェクトをクリックして**プロパティ**します。  
  
3.  プロジェクト デザイナーで、をクリックして、**展開**プロパティ ページのタブおよびセット**Unit Testing を有効にする**に`True`します。  
  
4.  変更内容を保存し、プロジェクト プロパティ ページを閉じます。  
  
5.  メイン メニューで、次のようにクリックします。**ビルド**、 をクリックし、**ソリューションのリビルド**します。  
  
6.  メイン メニューで、次のようにクリックします。**テスト**、 をクリックし、**新しいテスト**します。  
  
7.  **新しいテストの追加**ダイアログ ボックスで、**新しいビジュアルを作成C#テスト プロジェクト**の**テスト プロジェクトに追加**フィールド。 選択**単体テスト ウィザード**で、**テンプレート**ボックスの一覧をクリックして**OK**します。  
  
8.  **新しいテスト プロジェクト** ダイアログ ボックスで、プロジェクト名としてのままに**TestProject1**  をクリック**作成**です。  
  
9. **単体テストの作成** ダイアログ ボックスで、型を展開し、選択、 **POSchema()** 下でコンス トラクター、 **Microsoft.Samples.BizTalk.HelloWorld.POSchema**ノード。 選択も**POToInvoice()** 下でコンス トラクター、 **[potoinvoice()]** ノード。 次の図は、選択する必要があります。 下に表示される選択した場合、キーを押して**OK**します。  
  
     ![](../core/media/schemaandmapsunittestwizardselection.gif "SchemaAndMapsUnitTestWizardSelection")  
  
### <a name="adding-test-code-to-test-the-schemas-and-map"></a>スキーマとマップをテストするテスト コードを追加します。  
  
1.  次の参照を追加、 **TestProject1**からプロジェクトを **.NET**  タブで 参照の追加 ダイアログ。  
  
    -   Microsoft.BizTalk.TestTools  
  
    -   Microsoft XLANG/s ベース型  
  
2.  ソリューション エクスプローラで、poschematest.cs します。  
  
3.  ファイルの一番下までスクロールし、置換、 **POSchemaConstructorTest**を次のコード サンプルの注文書を検証メソッドは、メッセージを入力します。  
  
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
  
4.  ソリューション エクスプ ローラーで potoinvoicetest.cs を開き、次のディレクティブをそのファイルの先頭に追加します。  
  
    ```  
  
    using System.IO;   
    ```  
  
5.  ファイルの一番下までスクロールし、置換、 **POToInvoiceConstructorTest**を次のコード サンプルの注文書を使用してマップをテストするメソッドは、メッセージを入力します。  
  
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
  
### <a name="building-and-running-the-unit-test"></a>単体テストのビルドと実行  
  
1.  ソリューション エクスプ ローラーで右クリックして**TestProject1**、 をクリックし、**ビルド**します。  
  
2.  メイン メニューで、次のようにクリックします。**テスト**、し、 **Windows**一覧で、**テスト ビュー**します。  
  
3.  テスト ビュー ウィンドウで右クリック**poschemainstancevalidationtest**、 をクリックし、**選択範囲の実行**します。 あることを確認**成功**テスト結果 ウィンドウにします。  
  
4.  テスト ビュー ウィンドウで右クリック**POToInvoiceMapTest**、 をクリックし、**選択範囲の実行**します。 あることを確認**成功**テスト結果 ウィンドウにします。  
  
5.  テストが不合格の場合、[テスト結果] ウィンドウのテストをダブルクリックして、不合格の原因となったアサートまたは例外を確認します。  
  
## <a name="test-code-summary"></a>テスト コードのまとめ  
 単体テストが有効な場合に、 **HelloWorld**プロジェクト、C#クラスに関連付けられている**POSchema.xsd**から派生した、 **Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**クラス。 **[Poschemainstancevalidationtest]** メソッド**TestProject1**使用、 **ValidateInstance**のメソッド、 **POSchema**クラスPO スキーマに対する SamplePOInput.xml を検証します。  
  
 同様に、単体テストが有効な場合の**HelloWorld**プロジェクト、C#クラスに関連付けられている、 **POToInvoice.btm**マップがから派生した、 **Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**クラス。 **POToInvoiceMaptest**メソッドの使用、 **TestMap**のメソッド、 **POToInvoice**同じ SamplePOInput.xml メッセージを使用してマップをテストするクラス。 これにより、SampleInvoiceOutput.xml が HelloWorld ディレクトリで作成されています。  
  
## <a name="see-also"></a>参照  
 [単体テストのパイプラインを持つ機能を使用します。](../core/using-the-unit-testing-feature-with-pipelines.md)   
 [単体テスト (Visual Studio) の操作](http://go.microsoft.com/fwlink/?LinkId=128890)