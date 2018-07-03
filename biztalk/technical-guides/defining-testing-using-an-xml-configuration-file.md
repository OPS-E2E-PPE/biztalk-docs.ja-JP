---
title: XML 構成ファイルを使用したテストの定義 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d8339bcf-26d7-4a43-b68e-c4220a7a851d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd869d69ca11a41daac459229d7b58684e43afe7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992947"
---
# <a name="defining-testing-using-an-xml-configuration-file"></a>XML 構成ファイルを使用したテストを定義します。
BizUnit テストを定義する 2 つの方法を提供しています: および Excel ワークシートを使用して、XML 構成ファイル。 このトピックのねらい XML 構成ファイルを使用してテストを定義するにはただしも見てください BizUnit SDK では、Excel を使用するための BizUnit テスト_ケースを定義する方法の興味深い例が用意されています。 さらに、BizUnit テスト_ケースを迅速に作成できる GUI を提供するための BizUnit デザイナー ツールを調査したい場合があります。 このトピックでは、非常に単純なシナリオを使用して XML 構成を使用してテスト_ケースを定義する方法の概要を示します。  
  
## <a name="overview-of-defining-a-bizunit-test-case-using-xml-configuration"></a>XML 構成を使用するための BizUnit テスト_ケースの定義の概要  
 だけに述べたようには、このシナリオは、わかりやすくするための単純化されます。 次の図のようにアプリケーションのメッセージングのサンプルを検討してください。 通常の機能の動作をこのアプリケーションは、BizTalk がファイルを使用して XML ファイルを受信する受信場所に送信し、サブスクリプションに基づいて、適切なサブスクライバーと仮定します。 このシナリオを効果的に検証するには、ことがテストで、次の手順を実行します重要です。  
  
1. 一貫性のある状態とテストを実行する準備の完了であることを確認して、環境を設定します。  
  
   -   これは、使用される 2 つのファイルの場所に存在するすべてのファイルを削除することによって行います。  
  
2. 機能を検証するテストを実行します。  
  
   -   ファイル受信場所のポーリング フォルダーに有効な XML メッセージを作成します。  
  
   -   正しい XML メッセージが発信フォルダーの場所内に配置されるかを検証します。  
  
   -   検証には、スキーマとメッセージのペイロードの情報の両方をカバーする必要があります。 (通常、キー フィールドのいくつか調べる必要があります。)  
  
3. 環境に確実にテストが実行される前とに、同じ状態では、環境のクリーンアップします。  
  
   -   使用される 2 つのファイルの場所に存在するすべてのファイルを削除します。  
  
   ![サンプル BizTalk メッセージング アプリケーション](../technical-guides/media/440fa6d7-d3a0-476f-9484-fbea77d87e40.gif "440fa6d7-d3a0-476f-9484-fbea77d87e40")  
   サンプル BizTalk メッセージング アプリケーション  
  
   各テスト・ケースが開始され、[testcase] タグで終了testName パラメーターは、ここに示すように、これに渡されます。  
  
```  
<TestCase testName="Test_01_FILECopyWithXmlValidation">  
```  
  
 することが、環境がテストを実行する一貫性のある状態である、TestSetup フェーズを入力します。 この例で、TestData ディレクトリ内に含まれるすべての XML メッセージを削除します。 これを使用して、 **FileDeleteMultipleStep**します。  
  
```  
<TestSetup>  
   <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
      <Directory>..\..\..\TestData\</Directory>  
         <SearchPattern>*.xml</SearchPattern>   
      </TestStep>  
</TestSetup>  
```  
  
 新機能、テスト、テストの実行段階の最も重要なセクションをして入力します。 この段階では、複数のテスト ステップを含めることができます。 FileCreateStep、ドキュメントのコピーを使用してこの例では (InDoc1.xml で示しているように、 \<SourcePath\>タグ) で使用されるファイルのドロップダウンに、受信場所。 BizUnit は、このステップでのファイル名の一意識別子を使用してサポートすることが重要これは、%creationpath タグで Guid % の参照を確認できます。  
  
 使用する必要がありますこれが完了した後、 **FileValidateStep**作成済みの送信メッセージを検証します。 この手順では、タイムアウト値 (ミリ秒単位です)、ディレクトリ、および検索パターンを指定することがわかります。 これに加え、 **DeleteFile**タグでは、ファイルのことが確認された後に削除するかどうかを指定することができます。 最後も注意してください (その値をチェックする PONumber_0。) XML メッセージ内の PONumber ノードを検証する XPath クエリが検証に含まれています調査と送信メッセージのペイロードの検証は、BizUnit を使用する場合に従う必要のある基本原則のもう 1 つの例を示します。  
  
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
  
 テスト_ケースの最終段階では、クリーンアップです。 ここでは、ように、 **FileDelete**テスト ステップは、テストで使用するディレクトリをクリーンアップするために使用します。  
  
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
  
 うまくいけば BizUnit でテストを定義することは比較的簡単です、およびこのテスト フレームワークを使用するがされるを迅速に、アプリケーションの機能テストを提供するテスト_ケースを開発できるように例を示します。  
  
### <a name="full-test-case-example"></a>テスト_ケース全体の例  
 テスト_ケース全体の構成ファイルの内容は、参照用にここで含まれています。  
  
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