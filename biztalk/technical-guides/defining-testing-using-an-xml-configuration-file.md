---
title: XML 構成ファイルを使用したテストの定義 |Microsoft ドキュメント
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
ms.openlocfilehash: f18d6ed5e237a9ee5e9dbe36c58c10ec6f22907d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976336"
---
# <a name="defining-testing-using-an-xml-configuration-file"></a><span data-ttu-id="6464a-102">XML 構成ファイルを使用したテストを定義します。</span><span class="sxs-lookup"><span data-stu-id="6464a-102">Defining Testing Using an XML Configuration File</span></span>
<span data-ttu-id="6464a-103">BizUnit は、テストを定義する 2 つの方法を提供しています: XML 構成ファイルを使用して、Excel ワークシートを使用しています。</span><span class="sxs-lookup"><span data-stu-id="6464a-103">BizUnit offers two ways to define tests: via an XML configuration file and via an Excel worksheet.</span></span> <span data-ttu-id="6464a-104">このトピックのねらいでテストを定義する XML 構成ファイルの使用ただし、する必要がありますも見て BizUnit SDK ので、Excel を使用するための BizUnit テスト_ケースを定義する方法の興味深い例を示します。</span><span class="sxs-lookup"><span data-stu-id="6464a-104">This topic focuses on using an XML configuration file to define tests; however, you should also look at the BizUnit SDK, since it provides an interesting example of how to define BizUnit test cases using Excel.</span></span> <span data-ttu-id="6464a-105">さらに、BizUnit テスト ケースの迅速に作成できる GUI を提供するための BizUnit デザイナー ツールを調査することもできます。</span><span class="sxs-lookup"><span data-stu-id="6464a-105">In addition, you may wish to investigate the BizUnit Designer tool, which provides a GUI that allows for rapid creation of BizUnit test cases.</span></span> <span data-ttu-id="6464a-106">このトピックでは、非常に単純なシナリオを使用して XML 構成を使用してテスト_ケースを定義する方法の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="6464a-106">This topic provides an overview of how to define test cases using XML configuration using a very simplified scenario.</span></span>  
  
## <a name="overview-of-defining-a-bizunit-test-case-using-xml-configuration"></a><span data-ttu-id="6464a-107">XML 構成を使用するための BizUnit テスト_ケースの定義の概要</span><span class="sxs-lookup"><span data-stu-id="6464a-107">Overview of defining a BizUnit test case using XML configuration</span></span>  
 <span data-ttu-id="6464a-108">同様に述べたようには、このシナリオはわかりやすくするための簡略化されます。</span><span class="sxs-lookup"><span data-stu-id="6464a-108">As just stated, this scenario is simplified for purposes of illustration.</span></span> <span data-ttu-id="6464a-109">下図のいずれかのようなアプリケーションのメッセージング サンプルを検討してください。</span><span class="sxs-lookup"><span data-stu-id="6464a-109">Consider a sample messaging application such as the one illustrated below.</span></span> <span data-ttu-id="6464a-110">通常の機能の動作をこのアプリケーションは、BizTalk がファイルによる XML ファイルを受信する受信場所、そのサブスクリプションに基づいて、適切なサブスクライバーに送信し、ことを仮定します。</span><span class="sxs-lookup"><span data-stu-id="6464a-110">Let’s assume that normal functional behavior for this application is that BizTalk receives an XML file via a file receive location, it then sends it to an appropriate subscriber based on a subscription.</span></span> <span data-ttu-id="6464a-111">このシナリオを効果的に検証するには、テストで次の手順を実行して重要なは。</span><span class="sxs-lookup"><span data-stu-id="6464a-111">To validate this scenario effectively it is important that we perform the following steps in the test:</span></span>  
  
1.  <span data-ttu-id="6464a-112">環境をセットアップすると、一貫性のある状態と、テストを実行するための準備完了であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6464a-112">Set up the environment to ensure that it is in a consistent state and ready for the test to be run:</span></span>  
  
    -   <span data-ttu-id="6464a-113">これは、使用される 2 つのファイルの場所に存在するすべてのファイルを削除することによって行います。</span><span class="sxs-lookup"><span data-stu-id="6464a-113">This is done by deleting any files that are present in the two file locations used.</span></span>  
  
2.  <span data-ttu-id="6464a-114">機能を確認するテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="6464a-114">Run the test to verify functionality:</span></span>  
  
    -   <span data-ttu-id="6464a-115">有効な XML フォルダー内のメッセージ、ファイルの受信場所のポーリングを作成します。</span><span class="sxs-lookup"><span data-stu-id="6464a-115">Create a valid XML message in the folder that the file receive location polls.</span></span>  
  
    -   <span data-ttu-id="6464a-116">正しい XML メッセージが送信フォルダーの場所に配置していることを検証します。</span><span class="sxs-lookup"><span data-stu-id="6464a-116">Validate that the correct XML message is placed in the outbound folder location.</span></span>  
  
    -   <span data-ttu-id="6464a-117">検証には、スキーマとメッセージのペイロード情報の両方を取り扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6464a-117">The validation should cover both the schema and the payload information for the message.</span></span> <span data-ttu-id="6464a-118">(通常、キー フィールドのいくつか調べる必要があります。)</span><span class="sxs-lookup"><span data-stu-id="6464a-118">(Typically a couple of the key fields should be examined.)</span></span>  
  
3.  <span data-ttu-id="6464a-119">テストが実行される前に環境が同じ状態のことを確認するための環境をクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="6464a-119">Clean up the environment to ensure that the environment is in the same state as before the test executed:</span></span>  
  
    -   <span data-ttu-id="6464a-120">使用される 2 つのファイルの場所に存在するすべてのファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="6464a-120">Delete any files that are present in the two file locations used.</span></span>  
  
 <span data-ttu-id="6464a-121">![サンプル BizTalk メッセージング アプリケーション](../technical-guides/media/440fa6d7-d3a0-476f-9484-fbea77d87e40.gif "440fa6d7-d3a0-476f-9484-fbea77d87e40")</span><span class="sxs-lookup"><span data-stu-id="6464a-121">![Sample BizTalk Messaging Application](../technical-guides/media/440fa6d7-d3a0-476f-9484-fbea77d87e40.gif "440fa6d7-d3a0-476f-9484-fbea77d87e40")</span></span>  
<span data-ttu-id="6464a-122">サンプル BizTalk メッセージング アプリケーション</span><span class="sxs-lookup"><span data-stu-id="6464a-122">Sample BizTalk Messaging application</span></span>  
  
 <span data-ttu-id="6464a-123">各テスト・ケースを開始し、TestCase XML タグです。testName パラメーターは、ここで示したように、これに渡されます。</span><span class="sxs-lookup"><span data-stu-id="6464a-123">Each test case begins and ends with the TestCase XML tag; the testName parameter is passed into this as indicated here.</span></span>  
  
```  
<TestCase testName="Test_01_FILECopyWithXmlValidation">  
```  
  
 <span data-ttu-id="6464a-124">次に、どうすれば、環境がテストを実行する一貫性のある状態である、TestSetup フェーズを入力します。</span><span class="sxs-lookup"><span data-stu-id="6464a-124">Then we enter the TestSetup phase, in which we ensure that the environment is in a consistent state to run the test.</span></span> <span data-ttu-id="6464a-125">この例では、TestData ディレクトリに格納されている任意の XML メッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="6464a-125">In this example, we delete any XML messages that are contained in our TestData directory.</span></span> <span data-ttu-id="6464a-126">これを使用して、 **FileDeleteMultipleStep**です。</span><span class="sxs-lookup"><span data-stu-id="6464a-126">This is done using the **FileDeleteMultipleStep**.</span></span>  
  
```  
<TestSetup>  
   <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
      <Directory>..\..\..\TestData\</Directory>  
         <SearchPattern>*.xml</SearchPattern>   
      </TestStep>  
</TestSetup>  
```  
  
 <span data-ttu-id="6464a-127">テスト、テストの実行のステージの最も重要なセクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="6464a-127">We then enter what is the most critical section of the test, the test execution stage.</span></span> <span data-ttu-id="6464a-128">この段階では、複数のテスト ステップを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6464a-128">This stage can contain multiple test steps.</span></span> <span data-ttu-id="6464a-129">ドキュメントをコピーする、FileCreateStep を使用してこの例では (InDoc1.xml でわかるようにする、 \<SourcePath\>タグ) で使用されるファイル ドロップに、受信場所。</span><span class="sxs-lookup"><span data-stu-id="6464a-129">In this example we use the FileCreateStep to copy a document (InDoc1.xml which can be seen in the \<SourcePath\> tag) to a file drop which is used by our receive location.</span></span> <span data-ttu-id="6464a-130">BizUnit は、です。 この手順ではファイル名の一意識別子を使用してサポートすることが重要これは、%creationpath タグで Guid % 参照で確認できます。</span><span class="sxs-lookup"><span data-stu-id="6464a-130">It’s important to note that BizUnit supports using unique identifiers for filenames in this step; this can be seen with the %Guid% reference in the CreationPath tag.</span></span>  
  
 <span data-ttu-id="6464a-131">使用する必要がありますこれが完了した後、 **FileValidateStep**作成済みの送信メッセージを検証します。</span><span class="sxs-lookup"><span data-stu-id="6464a-131">After this has been completed, we need to use the **FileValidateStep** to validate the outbound message has been created.</span></span> <span data-ttu-id="6464a-132">この手順では、タイムアウト値 (ミリ秒単位では)、ディレクトリと、検索パターンを指定することができますがわかります。</span><span class="sxs-lookup"><span data-stu-id="6464a-132">You will notice this step allows you to specify a timeout value (this is in milliseconds), the directory and the search pattern.</span></span> <span data-ttu-id="6464a-133">これには、だけでなく、 **DeleteFile**タグでは、ファイルが検証された後に削除するかどうかを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="6464a-133">In addition to this, the **DeleteFile** tag enables you to specify whether you want the file to be removed after it has been validated.</span></span> <span data-ttu-id="6464a-134">最後にも注意してください (こと、値が確認 PONumber_0。) XML メッセージ内で [PONumber] ノードを検証する、XPath クエリが検証に含まれています検査および送信メッセージのペイロードの検証は、BizUnit を使用する場合に従う必要のある基本原則の別の例を示します。</span><span class="sxs-lookup"><span data-stu-id="6464a-134">Finally, you should also note the validation includes an XPath query, which validates the PONumber node within the XML message (it checks that the value is PONumber_0.) Examination and validation of the payload of any outbound messages is another example of a guiding principle that you should follow when using BizUnit.</span></span>  
  
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
  
 <span data-ttu-id="6464a-135">テスト_ケースの最終ステージは、クリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="6464a-135">The final stage of the test case is the cleanup.</span></span> <span data-ttu-id="6464a-136">ここでは、示されているように、 **FileDelete**テスト ステップは、テストによって使用されるディレクトリをクリーンアップするために使用します。</span><span class="sxs-lookup"><span data-stu-id="6464a-136">As can be seen here, the **FileDelete** test step is used to clean up the directories used by the test.</span></span>  
  
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
  
 <span data-ttu-id="6464a-137">おそらく BizUnit でテストを定義することは比較的簡単なと、このテスト フレームワークを使用することができます、アプリケーションの機能テストにテスト_ケースを迅速に開発する例を示します。</span><span class="sxs-lookup"><span data-stu-id="6464a-137">Hopefully this example illustrates that defining tests in BizUnit is relatively straightforward and that by using this test framework, you will be able to rapidly develop test cases to provide functional testing of your application.</span></span>  
  
### <a name="full-test-case-example"></a><span data-ttu-id="6464a-138">すべてのテスト_ケースの例</span><span class="sxs-lookup"><span data-stu-id="6464a-138">Full test case example</span></span>  
 <span data-ttu-id="6464a-139">すべてのテスト_ケースの構成ファイルの内容がここに、参照です。</span><span class="sxs-lookup"><span data-stu-id="6464a-139">The full test case configuration file contents are included here for your reference:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6464a-140">参照</span><span class="sxs-lookup"><span data-stu-id="6464a-140">See Also</span></span>  
 [<span data-ttu-id="6464a-141">自動テストを容易にするための BizUnit の使用</span><span class="sxs-lookup"><span data-stu-id="6464a-141">Using BizUnit to Facilitate Automated Testing</span></span>](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)