---
title: "XML 構成ファイルを使用したテストの定義 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8339bcf-26d7-4a43-b68e-c4220a7a851d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f18d6ed5e237a9ee5e9dbe36c58c10ec6f22907d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="defining-testing-using-an-xml-configuration-file"></a>XML 構成ファイルを使用したテストを定義します。
BizUnit は、テストを定義する 2 つの方法を提供しています: XML 構成ファイルを使用して、Excel ワークシートを使用しています。 このトピックのねらいでテストを定義する XML 構成ファイルの使用ただし、する必要がありますも見て BizUnit SDK ので、Excel を使用するための BizUnit テスト_ケースを定義する方法の興味深い例を示します。 さらに、BizUnit テスト ケースの迅速に作成できる GUI を提供するための BizUnit デザイナー ツールを調査することもできます。 このトピックでは、非常に単純なシナリオを使用して XML 構成を使用してテスト_ケースを定義する方法の概要を示します。  
  
## <a name="overview-of-defining-a-bizunit-test-case-using-xml-configuration"></a>XML 構成を使用するための BizUnit テスト_ケースの定義の概要  
 同様に述べたようには、このシナリオはわかりやすくするための簡略化されます。 下図のいずれかのようなアプリケーションのメッセージング サンプルを検討してください。 通常の機能の動作をこのアプリケーションは、BizTalk がファイルによる XML ファイルを受信する受信場所、そのサブスクリプションに基づいて、適切なサブスクライバーに送信し、ことを仮定します。 このシナリオを効果的に検証するには、テストで次の手順を実行して重要なは。  
  
1.  環境をセットアップすると、一貫性のある状態と、テストを実行するための準備完了であることを確認してください。  
  
    -   これは、使用される 2 つのファイルの場所に存在するすべてのファイルを削除することによって行います。  
  
2.  機能を確認するテストを実行します。  
  
    -   有効な XML フォルダー内のメッセージ、ファイルの受信場所のポーリングを作成します。  
  
    -   正しい XML メッセージが送信フォルダーの場所に配置していることを検証します。  
  
    -   検証には、スキーマとメッセージのペイロード情報の両方を取り扱う必要があります。 (通常、キー フィールドのいくつか調べる必要があります。)  
  
3.  テストが実行される前に環境が同じ状態のことを確認するための環境をクリーンアップします。  
  
    -   使用される 2 つのファイルの場所に存在するすべてのファイルを削除します。  
  
 ![サンプル BizTalk メッセージング アプリケーション](../technical-guides/media/440fa6d7-d3a0-476f-9484-fbea77d87e40.gif "440fa6d7-d3a0-476f-9484-fbea77d87e40")  
サンプル BizTalk メッセージング アプリケーション  
  
 各テスト・ケースを開始し、TestCase XML タグです。testName パラメーターは、ここで示したように、これに渡されます。  
  
```  
<TestCase testName="Test_01_FILECopyWithXmlValidation">  
```  
  
 次に、どうすれば、環境がテストを実行する一貫性のある状態である、TestSetup フェーズを入力します。 この例では、TestData ディレクトリに格納されている任意の XML メッセージを削除します。 これを使用して、 **FileDeleteMultipleStep**です。  
  
```  
<TestSetup>  
   <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
      <Directory>..\..\..\TestData\</Directory>  
         <SearchPattern>*.xml</SearchPattern>   
      </TestStep>  
</TestSetup>  
```  
  
 テスト、テストの実行のステージの最も重要なセクションを入力します。 この段階では、複数のテスト ステップを含めることができます。 ドキュメントをコピーする、FileCreateStep を使用してこの例では (InDoc1.xml でわかるようにする、 \<SourcePath\>タグ) で使用されるファイル ドロップに、受信場所。 BizUnit は、です。 この手順ではファイル名の一意識別子を使用してサポートすることが重要これは、%creationpath タグで Guid % 参照で確認できます。  
  
 使用する必要がありますこれが完了した後、 **FileValidateStep**作成済みの送信メッセージを検証します。 この手順では、タイムアウト値 (ミリ秒単位では)、ディレクトリと、検索パターンを指定することができますがわかります。 これには、だけでなく、 **DeleteFile**タグでは、ファイルが検証された後に削除するかどうかを指定することができます。 最後にも注意してください (こと、値が確認 PONumber_0。) XML メッセージ内で [PONumber] ノードを検証する、XPath クエリが検証に含まれています検査および送信メッセージのペイロードの検証は、BizUnit を使用する場合に従う必要のある基本原則の別の例を示します。  
  
```  
<TestExecution>  
   <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileCreateStep">  
      <SourcePath>..\..\..\TestData\InDoc1.xml</SourcePath>  
      <CreationPath>..\..\..\Rec_03\TransactionId_%Guid%.xml</CreationPath>  
   </TestStep>  
   <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileValidateStep">  
      <Timeout>3000</Timeout>  
      <Directory>..\..\..\Rec_03\</Directory>  
      <SearchPattern>TransactionId_*.xml</SearchPattern>  
      <DeleteFile>true</DeleteFile>  
      <ValidationStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.XmlValidationStep">  
         <XmlSchemaPath>..\..\..\TestData\PurchaseOrder.xsd</XmlSchemaPath>  
         <XmlSchemaNameSpace>http://SendMail.PurchaseOrder</XmlSchemaNameSpace>  
         <XPathList>  
            <XPathValidation query="/*[local-name()='PurchaseOrder' and namespace-uri()='http://SendMail.PurchaseOrder']/*[local-name()='PONumber' and namespace-uri()='']">PONumber_0</XPathValidation>  
         </XPathList>  
      </ValidationStep>  
   </TestStep>  
</TestExecution>  
```  
  
 テスト_ケースの最終ステージは、クリーンアップします。 ここでは、示されているように、 **FileDelete**テスト ステップは、テストによって使用されるディレクトリをクリーンアップするために使用します。  
  
```  
<TestCleanup>  
   <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
      <Directory>..\..\..\TestData\</Directory>  
      <SearchPattern>*.xml</SearchPattern>   
   </TestStep>  
   <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
      <Directory>..\..\..\Rec_03\</Directory>  
      <SearchPattern>*.xml</SearchPattern>   
   </TestStep>  
</TestCleanup>  
```  
  
 おそらく BizUnit でテストを定義することは比較的簡単なと、このテスト フレームワークを使用することができます、アプリケーションの機能テストにテスト_ケースを迅速に開発する例を示します。  
  
### <a name="full-test-case-example"></a>すべてのテスト_ケースの例  
 すべてのテスト_ケースの構成ファイルの内容がここに、参照です。  
  
```  
<TestCase testName="Test_01_FILECopyWithXmlValidation">  
   <TestSetup>  
      <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
         <Directory>..\..\..\TestData\</Directory>  
            <SearchPattern>*.xml</SearchPattern>   
         </TestStep>  
   </TestSetup>  
   <TestExecution>  
      <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileCreateStep">  
         <SourcePath>..\..\..\TestData\InDoc1.xml</SourcePath>  
         <CreationPath>..\..\..\Rec_03\TransactionId_%Guid%.xml</CreationPath>  
      </TestStep>  
      <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileValidateStep">  
         <Timeout>3000</Timeout>  
         <Directory>..\..\..\Rec_03\</Directory>  
         <SearchPattern>TransactionId_*.xml</SearchPattern>  
         <DeleteFile>true</DeleteFile>  
         <ValidationStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.XmlValidationStep">  
            <XmlSchemaPath>..\..\..\TestData\PurchaseOrder.xsd</XmlSchemaPath>  
            <XmlSchemaNameSpace>http://SendMail.PurchaseOrder</XmlSchemaNameSpace>  
            <XPathList>  
               <XPathValidation query="/*[local-name()='PurchaseOrder' and namespace-uri()='http://SendMail.PurchaseOrder']/*[local-name()='PONumber' and namespace-uri()='']">PONumber_0</XPathValidation>  
            </XPathList>  
         </ValidationStep>  
      </TestStep>  
   </TestExecution>  
   <!-- Test cleanup: test cases should always leave the system in the state they found it -->  
   <TestCleanup>  
      <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
         <Directory>..\..\..\TestData\</Directory>  
         <SearchPattern>*.xml</SearchPattern>   
      </TestStep>  
      <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
         <Directory>..\..\..\Rec_03\</Directory>  
         <SearchPattern>*.xml</SearchPattern>   
      </TestStep>  
   </TestCleanup>  
</TestCase>  
```  
  
## <a name="see-also"></a>参照  
 [自動テストを容易にするための BizUnit の使用](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)