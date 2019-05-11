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
ms.openlocfilehash: deaf8e6e6bc968e9666dce9b12c056f4ea3584f3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305936"
---
# <a name="defining-testing-using-an-xml-configuration-file"></a><span data-ttu-id="6812e-102">XML 構成ファイルを使用したテストを定義します。</span><span class="sxs-lookup"><span data-stu-id="6812e-102">Defining Testing Using an XML Configuration File</span></span>
<span data-ttu-id="6812e-103">BizUnit テストを定義する 2 つの方法を提供しています: および Excel ワークシートを使用して、XML 構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="6812e-103">BizUnit offers two ways to define tests: via an XML configuration file and via an Excel worksheet.</span></span> <span data-ttu-id="6812e-104">このトピックのねらい XML 構成ファイルを使用してテストを定義するにはただしも見てください BizUnit SDK では、Excel を使用するための BizUnit テスト_ケースを定義する方法の興味深い例が用意されています。</span><span class="sxs-lookup"><span data-stu-id="6812e-104">This topic focuses on using an XML configuration file to define tests; however, you should also look at the BizUnit SDK, since it provides an interesting example of how to define BizUnit test cases using Excel.</span></span> <span data-ttu-id="6812e-105">さらに、BizUnit テスト_ケースを迅速に作成できる GUI を提供するための BizUnit デザイナー ツールを調査したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="6812e-105">In addition, you may wish to investigate the BizUnit Designer tool, which provides a GUI that allows for rapid creation of BizUnit test cases.</span></span> <span data-ttu-id="6812e-106">このトピックでは、非常に単純なシナリオを使用して XML 構成を使用してテスト_ケースを定義する方法の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="6812e-106">This topic provides an overview of how to define test cases using XML configuration using a very simplified scenario.</span></span>  
  
## <a name="overview-of-defining-a-bizunit-test-case-using-xml-configuration"></a><span data-ttu-id="6812e-107">XML 構成を使用するための BizUnit テスト_ケースの定義の概要</span><span class="sxs-lookup"><span data-stu-id="6812e-107">Overview of defining a BizUnit test case using XML configuration</span></span>  
 <span data-ttu-id="6812e-108">だけに述べたようには、このシナリオは、わかりやすくするための単純化されます。</span><span class="sxs-lookup"><span data-stu-id="6812e-108">As just stated, this scenario is simplified for purposes of illustration.</span></span> <span data-ttu-id="6812e-109">次の図のようにアプリケーションのメッセージングのサンプルを検討してください。</span><span class="sxs-lookup"><span data-stu-id="6812e-109">Consider a sample messaging application such as the one illustrated below.</span></span> <span data-ttu-id="6812e-110">通常の機能の動作をこのアプリケーションは、BizTalk がファイルを使用して XML ファイルを受信する受信場所に送信し、サブスクリプションに基づいて、適切なサブスクライバーと仮定します。</span><span class="sxs-lookup"><span data-stu-id="6812e-110">Let’s assume that normal functional behavior for this application is that BizTalk receives an XML file via a file receive location, it then sends it to an appropriate subscriber based on a subscription.</span></span> <span data-ttu-id="6812e-111">このシナリオを効果的に検証するには、ことがテストで、次の手順を実行します重要です。</span><span class="sxs-lookup"><span data-stu-id="6812e-111">To validate this scenario effectively it is important that we perform the following steps in the test:</span></span>  
  
1. <span data-ttu-id="6812e-112">一貫性のある状態とテストを実行する準備の完了であることを確認して、環境を設定します。</span><span class="sxs-lookup"><span data-stu-id="6812e-112">Set up the environment to ensure that it is in a consistent state and ready for the test to be run:</span></span>  
  
   -   <span data-ttu-id="6812e-113">これは、使用される 2 つのファイルの場所に存在するすべてのファイルを削除することによって行います。</span><span class="sxs-lookup"><span data-stu-id="6812e-113">This is done by deleting any files that are present in the two file locations used.</span></span>  
  
2. <span data-ttu-id="6812e-114">機能を検証するテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="6812e-114">Run the test to verify functionality:</span></span>  
  
   -   <span data-ttu-id="6812e-115">ファイル受信場所のポーリング フォルダーに有効な XML メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="6812e-115">Create a valid XML message in the folder that the file receive location polls.</span></span>  
  
   -   <span data-ttu-id="6812e-116">正しい XML メッセージが発信フォルダーの場所内に配置されるかを検証します。</span><span class="sxs-lookup"><span data-stu-id="6812e-116">Validate that the correct XML message is placed in the outbound folder location.</span></span>  
  
   -   <span data-ttu-id="6812e-117">検証には、スキーマとメッセージのペイロードの情報の両方をカバーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6812e-117">The validation should cover both the schema and the payload information for the message.</span></span> <span data-ttu-id="6812e-118">(通常、キー フィールドのいくつか調べる必要があります。)</span><span class="sxs-lookup"><span data-stu-id="6812e-118">(Typically a couple of the key fields should be examined.)</span></span>  
  
3. <span data-ttu-id="6812e-119">環境に確実にテストが実行される前とに、同じ状態では、環境のクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="6812e-119">Clean up the environment to ensure that the environment is in the same state as before the test executed:</span></span>  
  
   -   <span data-ttu-id="6812e-120">使用される 2 つのファイルの場所に存在するすべてのファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="6812e-120">Delete any files that are present in the two file locations used.</span></span>  
  
   <span data-ttu-id="6812e-121">![サンプル BizTalk メッセージング アプリケーション](../technical-guides/media/440fa6d7-d3a0-476f-9484-fbea77d87e40.gif "440fa6d7-d3a0-476f-9484-fbea77d87e40")</span><span class="sxs-lookup"><span data-stu-id="6812e-121">![Sample BizTalk Messaging Application](../technical-guides/media/440fa6d7-d3a0-476f-9484-fbea77d87e40.gif "440fa6d7-d3a0-476f-9484-fbea77d87e40")</span></span>  
   <span data-ttu-id="6812e-122">サンプル BizTalk メッセージング アプリケーション</span><span class="sxs-lookup"><span data-stu-id="6812e-122">Sample BizTalk Messaging application</span></span>  
  
   <span data-ttu-id="6812e-123">各テスト・ケースが開始され、[testcase] タグで終了testName パラメーターは、ここに示すように、これに渡されます。</span><span class="sxs-lookup"><span data-stu-id="6812e-123">Each test case begins and ends with the TestCase XML tag; the testName parameter is passed into this as indicated here.</span></span>  
  
```  
<TestCase testName="Test_01_FILECopyWithXmlValidation">  
```  
  
 <span data-ttu-id="6812e-124">することが、環境がテストを実行する一貫性のある状態である、TestSetup フェーズを入力します。</span><span class="sxs-lookup"><span data-stu-id="6812e-124">Then we enter the TestSetup phase, in which we ensure that the environment is in a consistent state to run the test.</span></span> <span data-ttu-id="6812e-125">この例で、TestData ディレクトリ内に含まれるすべての XML メッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="6812e-125">In this example, we delete any XML messages that are contained in our TestData directory.</span></span> <span data-ttu-id="6812e-126">これを使用して、 **FileDeleteMultipleStep**します。</span><span class="sxs-lookup"><span data-stu-id="6812e-126">This is done using the **FileDeleteMultipleStep**.</span></span>  
  
```  
<TestSetup>  
   <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
      <Directory>..\..\..\TestData\</Directory>  
         <SearchPattern>*.xml</SearchPattern>   
      </TestStep>  
</TestSetup>  
```  
  
 <span data-ttu-id="6812e-127">新機能、テスト、テストの実行段階の最も重要なセクションをして入力します。</span><span class="sxs-lookup"><span data-stu-id="6812e-127">We then enter what is the most critical section of the test, the test execution stage.</span></span> <span data-ttu-id="6812e-128">この段階では、複数のテスト ステップを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6812e-128">This stage can contain multiple test steps.</span></span> <span data-ttu-id="6812e-129">FileCreateStep、ドキュメントのコピーを使用してこの例では (InDoc1.xml で示しているように、 \<SourcePath\>タグ) で使用されるファイルのドロップダウンに、受信場所。</span><span class="sxs-lookup"><span data-stu-id="6812e-129">In this example we use the FileCreateStep to copy a document (InDoc1.xml which can be seen in the \<SourcePath\> tag) to a file drop which is used by our receive location.</span></span> <span data-ttu-id="6812e-130">BizUnit は、このステップでのファイル名の一意識別子を使用してサポートすることが重要これは、%creationpath タグで Guid % の参照を確認できます。</span><span class="sxs-lookup"><span data-stu-id="6812e-130">It’s important to note that BizUnit supports using unique identifiers for filenames in this step; this can be seen with the %Guid% reference in the CreationPath tag.</span></span>  
  
 <span data-ttu-id="6812e-131">使用する必要がありますこれが完了した後、 **FileValidateStep**作成済みの送信メッセージを検証します。</span><span class="sxs-lookup"><span data-stu-id="6812e-131">After this has been completed, we need to use the **FileValidateStep** to validate the outbound message has been created.</span></span> <span data-ttu-id="6812e-132">この手順では、タイムアウト値 (ミリ秒単位です)、ディレクトリ、および検索パターンを指定することがわかります。</span><span class="sxs-lookup"><span data-stu-id="6812e-132">You will notice this step allows you to specify a timeout value (this is in milliseconds), the directory and the search pattern.</span></span> <span data-ttu-id="6812e-133">これに加え、 **DeleteFile**タグでは、ファイルのことが確認された後に削除するかどうかを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="6812e-133">In addition to this, the **DeleteFile** tag enables you to specify whether you want the file to be removed after it has been validated.</span></span> <span data-ttu-id="6812e-134">最後も注意してください (その値をチェックする PONumber_0。) XML メッセージ内の PONumber ノードを検証する XPath クエリが検証に含まれています調査と送信メッセージのペイロードの検証は、BizUnit を使用する場合に従う必要のある基本原則のもう 1 つの例を示します。</span><span class="sxs-lookup"><span data-stu-id="6812e-134">Finally, you should also note the validation includes an XPath query, which validates the PONumber node within the XML message (it checks that the value is PONumber_0.) Examination and validation of the payload of any outbound messages is another example of a guiding principle that you should follow when using BizUnit.</span></span>  
  
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
  
 <span data-ttu-id="6812e-135">テスト_ケースの最終段階では、クリーンアップです。</span><span class="sxs-lookup"><span data-stu-id="6812e-135">The final stage of the test case is the cleanup.</span></span> <span data-ttu-id="6812e-136">ここでは、ように、 **FileDelete**テスト ステップは、テストで使用するディレクトリをクリーンアップするために使用します。</span><span class="sxs-lookup"><span data-stu-id="6812e-136">As can be seen here, the **FileDelete** test step is used to clean up the directories used by the test.</span></span>  
  
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
  
 <span data-ttu-id="6812e-137">うまくいけば BizUnit でテストを定義することは比較的簡単です、およびこのテスト フレームワークを使用するがされるを迅速に、アプリケーションの機能テストを提供するテスト_ケースを開発できるように例を示します。</span><span class="sxs-lookup"><span data-stu-id="6812e-137">Hopefully this example illustrates that defining tests in BizUnit is relatively straightforward and that by using this test framework, you will be able to rapidly develop test cases to provide functional testing of your application.</span></span>  
  
### <a name="full-test-case-example"></a><span data-ttu-id="6812e-138">テスト_ケース全体の例</span><span class="sxs-lookup"><span data-stu-id="6812e-138">Full test case example</span></span>  
 <span data-ttu-id="6812e-139">テスト_ケース全体の構成ファイルの内容は、参照用にここで含まれています。</span><span class="sxs-lookup"><span data-stu-id="6812e-139">The full test case configuration file contents are included here for your reference:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6812e-140">参照</span><span class="sxs-lookup"><span data-stu-id="6812e-140">See Also</span></span>  
 [<span data-ttu-id="6812e-141">自動テストを容易にするための BizUnit の使用</span><span class="sxs-lookup"><span data-stu-id="6812e-141">Using BizUnit to Facilitate Automated Testing</span></span>](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)