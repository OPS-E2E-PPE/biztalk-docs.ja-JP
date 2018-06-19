---
title: 単体テストのスキーマおよびマップの機能を使用して |Microsoft ドキュメント
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
ms.openlocfilehash: fbc14621a1830f15da02336b7b82e9df475cfe9b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288994"
---
# <a name="using-the-unit-testing-feature-with-schemas-and-maps"></a>スキーマとマップを含む単体テスト機能の使用
このトピックでは、単体テスト機能を使用してスキーマとマップの単体テストを HelloWorld オーケストレーション サンプルに追加する方法を示します。  
  
> [!NOTE]
>  現時点において、マップ用の単体テスト機能では、複数の入力マップはサポートされていません。  
  
## <a name="prerequisites"></a>前提条件  
 最初に、HelloWorld サンプルの作成手順に従う必要があります。 これらの手順をご覧ください: [HelloWorld (BizTalk Server サンプル)](../core/helloworld-biztalk-server-sample.md)  
  
### <a name="adding-a-unit-test-project-to-the-helloworld-sample"></a>HelloWorld サンプルへの単体テスト プロジェクトの追加  
  
1.  Visual Studio で、HelloWorld.sln ソリューション ファイルを開きます。  
  
2.  ソリューション エクスプ ローラーで右クリックし、 **HelloWorld**プロジェクトをクリックして**プロパティ**です。  
  
3.  プロジェクト デザイナーで、をクリックして、**展開**プロパティ ページ タブとセット**単体テストを有効にする**に`True`です。  
  
4.  変更内容を保存し、プロジェクト プロパティ ページを閉じます。  
  
5.  メイン メニューでクリックして**ビルド**、順にクリック**ソリューションのリビルド**です。  
  
6.  メイン メニューで、をクリックして**テスト**、クリックして**新しいテスト**です。  
  
7.  **新しいテストの追加**ダイアログ ボックスで、**新しい Visual c# テスト プロジェクトを作成する**の**テスト プロジェクトに追加**フィールドです。 選択**単体テスト ウィザード**で、**テンプレート**ボックスの一覧し、をクリックして**OK**です。  
  
8.  **新しいテスト プロジェクト** ダイアログ ボックスで、プロジェクト名としてのままにして**TestProject1**  をクリック**作成**です。  
  
9. **単体テストの作成** ダイアログ ボックスで、種類を展開し、選択、 **POSchema()** 下でコンス トラクター、 **poschema()** ノード。 選択も**POToInvoice()** 下でコンス トラクター、 **Microsoft.Samples.BizTalk.HelloWorld.POToInvoice**ノード。 次の図は、選択する要素を示しています。 次に、選択した場合、キーを押して**OK**です。  
  
     ![](../core/media/schemaandmapsunittestwizardselection.gif "SchemaAndMapsUnitTestWizardSelection")  
  
### <a name="adding-test-code-to-test-the-schemas-and-map"></a>スキーマとマップをテストするテスト コードの追加  
  
1.  次の参照を追加、 **TestProject1**プロジェクトから、 **.NET**  タブで 参照の追加 ダイアログ。  
  
    -   Microsoft.BizTalk.TestTools  
  
    -   Microsoft XLANG/s ベース型  
  
2.  ソリューション エクスプローラーで、POSchemaTest.cs を開きます。  
  
3.  ファイルの一番下までスクロールし、置換、 **POSchemaConstructorTest**を次のコード サンプルの注文書を検証するメソッドは、メッセージを入力します。  
  
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
  
4.  ソリューション エクスプローラーで POToInvoiceTest.cs を開き、次のディレクティブをそのファイルの先頭に追加します。  
  
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
  
1.  ソリューション エクスプ ローラーで右クリック**TestProject1**、クリックして**ビルド**です。  
  
2.  メイン メニューで、をクリックして**テスト**、し、 **Windows**一覧で、クリックして**テスト ビュー**です。  
  
3.  テスト ビュー ウィンドウで右クリック**poschemainstancevalidationtest**、クリックして**選択範囲の実行**です。 されることを確認**成功**テスト結果 ウィンドウでします。  
  
4.  テスト ビュー ウィンドウで右クリック**POToInvoiceMapTest**、クリックして**選択範囲の実行**です。 されることを確認**成功**テスト結果 ウィンドウでします。  
  
5.  テストが不合格の場合、[テスト結果] ウィンドウのテストをダブルクリックして、不合格の原因となったアサートまたは例外を確認します。  
  
## <a name="test-code-summary"></a>テスト コードのまとめ  
 単体テストが有効にすると、 **HelloWorld**プロジェクト、c# のクラスに関連付けられている**POSchema.xsd**から派生した、 **Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**クラスです。 **[Poschemainstancevalidationtest]** メソッド**TestProject1**使用、 **ValidateInstance**のメソッド、 **POSchema**にクラスPO スキーマに対する SamplePOInput.xml を検証します。  
  
 同様に、単体テストが有効な場合の**HelloWorld**プロジェクト、c# のクラスに関連付けられている、 **POToInvoice.btm**マップの派生元の**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**クラスです。 **POToInvoiceMaptest**使用する方法、 **TestMap**のメソッド、 **POToInvoice**同じ SamplePOInput.xml メッセージを使用してマップをテストするクラス。 これにより、SampleInvoiceOutput.xml が HelloWorld ディレクトリで作成されました。  
  
## <a name="see-also"></a>参照  
 [単体テストのパイプラインを持つ機能の使用](../core/using-the-unit-testing-feature-with-pipelines.md)   
 [単体テスト (Visual Studio) の操作](http://go.microsoft.com/fwlink/?LinkId=128890)