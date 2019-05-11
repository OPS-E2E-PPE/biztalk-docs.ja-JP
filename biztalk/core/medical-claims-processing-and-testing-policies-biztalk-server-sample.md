---
title: Medical Claims Processing and Testing Policies (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, business rules
- business rules, examples
ms.assetid: c0bdf7b7-3e55-4560-a5a8-00c5b661d14d
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5108e5d26b7da7761285c8b8e7ec1bde8deaf00c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65325564"
---
# <a name="medical-claims-processing-and-testing-policies-biztalk-server-sample"></a><span data-ttu-id="5a881-102">Medical Claims Processing and Testing Policies (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="5a881-102">Medical Claims Processing and Testing Policies (BizTalk Server Sample)</span></span>
<span data-ttu-id="5a881-103">Medical Claims Processing and Testing Policies サンプルでは、データベース テーブルと、受信ドキュメントから派生したファクトを検証して、これを使用して複数のルールを含んだ規則セットを作成する方法を示します。処理要求の結果を記録する NET ベースのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5a881-103">The Medical Claims Processing and Testing Policies sample demonstrates how to create a rule set containing multiple rules that examine facts derived from a database table and the inbound document, and which use .NET-based objects to record the results of the claims processing.</span></span>  
  
 <span data-ttu-id="5a881-104">このサンプルでは、単純なを使用して請求処理シナリオのエンド ツー エンドの実行を示します。要求の状態および状態の理由を確認する入力方向の要求に対して医療費請求ルールを実行するビジネス ルール エンジンを使用する NET ベースのアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="5a881-104">This sample demonstrates end-end execution of the claim processing scenario using a simple .NET-based application that uses the Business Rule Engine to run a medical claims rule set against incoming claims to determine the STATUS of the claim and the REASON for the status.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a881-105">このサンプルでは、デバッグ トレース ファイルを使用してビジネス ルール エンジン実行をトレースする方法も示します。</span><span class="sxs-lookup"><span data-stu-id="5a881-105">This sample also demonstrates how to trace Business Rule Engine execution using a debug trace file.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="5a881-106">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="5a881-106">What This Sample Does</span></span>  
 <span data-ttu-id="5a881-107">このサンプルでは、送信された要求に、次の一連の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="5a881-107">This sample applies the following sequence of rules to submitted claims:</span></span>  
  
1.  <span data-ttu-id="5a881-108">要求の合計量が、ポリシーによって許可された最大値を超えた場合、請求を拒否します。</span><span class="sxs-lookup"><span data-stu-id="5a881-108">Rejects the claim if the total amount claimed exceeds the maximum permitted by the policy.</span></span>  
  
2.  <span data-ttu-id="5a881-109">場合、クライアントが病院で、ポリシーによって許可された最大値よりも詳細の夜、請求を拒否します。</span><span class="sxs-lookup"><span data-stu-id="5a881-109">Rejects the claim if the client has stayed in hospitals more nights than the maximum permitted by the policy.</span></span>  
  
3.  <span data-ttu-id="5a881-110">要求の日付が、将来の場合、請求を拒否します。</span><span class="sxs-lookup"><span data-stu-id="5a881-110">Rejects the claim if the date on the claim is in the future.</span></span>  
  
4.  <span data-ttu-id="5a881-111">ポリシーが有効でない場合は、要求を拒否します。</span><span class="sxs-lookup"><span data-stu-id="5a881-111">Rejects the claim if the policy is not valid.</span></span>  
  
5.  <span data-ttu-id="5a881-112">ポリシーの有効期限が切れている場合は、潜在顧客がポリシー ID および患者名と共にセールス部門に送信します。</span><span class="sxs-lookup"><span data-stu-id="5a881-112">Sends a lead to the sales department with the policy ID and customer name if the policy has expired.</span></span>  
  
6.  <span data-ttu-id="5a881-113">それ以外の場合、要求を承認します。</span><span class="sxs-lookup"><span data-stu-id="5a881-113">Otherwise, approves the claim.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="5a881-114">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="5a881-114">Where to Find This Sample</span></span>  
 <span data-ttu-id="5a881-115">\<*パスのサンプル*\>\Business Rules\Medical Claims Processing and Policies\ を Testing</span><span class="sxs-lookup"><span data-stu-id="5a881-115">\<*Samples Path*\>\Business Rules\Medical Claims Processing and Testing Policies\\</span></span>  
  
 <span data-ttu-id="5a881-116">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="5a881-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="5a881-117">ファイル</span><span class="sxs-lookup"><span data-stu-id="5a881-117">File(s)</span></span>|<span data-ttu-id="5a881-118">説明</span><span class="sxs-lookup"><span data-stu-id="5a881-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5a881-119">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="5a881-119">Cleanup.bat</span></span>|<span data-ttu-id="5a881-120">アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5a881-120">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="5a881-121">送信ポートと受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="5a881-121">Removes send and receive ports.</span></span> <span data-ttu-id="5a881-122">必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="5a881-122">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="5a881-123">Create_PolicyValidity_Table.sql</span><span class="sxs-lookup"><span data-stu-id="5a881-123">Create_PolicyValidity_Table.sql</span></span>|<span data-ttu-id="5a881-124">新しいテーブルを追加する SQL スクリプトでは、Northwind サンプル データベースに PolicyValidity という名前です。</span><span class="sxs-lookup"><span data-stu-id="5a881-124">SQL script that adds a new table named PolicyValidity to the Northwind sample database.</span></span>|  
|<span data-ttu-id="5a881-125">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="5a881-125">Setup.bat</span></span>|<span data-ttu-id="5a881-126">このサンプルをビルドおよび初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5a881-126">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="5a881-127">\Claims フォルダー。</span><span class="sxs-lookup"><span data-stu-id="5a881-127">In the \Claims folder:</span></span><br /><br /> <span data-ttu-id="5a881-128">AssemblyInfo.cs、Claims.csproj、Claims.sln、Claims.cs</span><span class="sxs-lookup"><span data-stu-id="5a881-128">AssemblyInfo.cs, Claims.csproj, Claims.sln, Claims.cs</span></span>|<span data-ttu-id="5a881-129">プロジェクト、ソリューション、ソース、および、請求処理の結果を記録するこのサンプルの部分に関連するファイルと呼ばれる、**し**ルールの一部です。</span><span class="sxs-lookup"><span data-stu-id="5a881-129">Project, solution, source, and related files for the portion of this sample that records the result of the claims processing, called the **THEN** portion of a rule.</span></span>|  
|<span data-ttu-id="5a881-130">\FactRetrieverForClaimsProcessing フォルダー。</span><span class="sxs-lookup"><span data-stu-id="5a881-130">In the \FactRetrieverForClaimsProcessing folder:</span></span><br /><br /> <span data-ttu-id="5a881-131">AssemblyInfo.cs、FactRetrieverForClaimsProcessing.cs、FactRetrieverForClaimsProcessing.csproj、FactRetrieverForClaimsProcessing.sln</span><span class="sxs-lookup"><span data-stu-id="5a881-131">AssemblyInfo.cs, FactRetrieverForClaimsProcessing.cs, FactRetrieverForClaimsProcessing.csproj, FactRetrieverForClaimsProcessing.sln</span></span>|<span data-ttu-id="5a881-132">プロジェクト、ソリューション、ソース、およびこのサンプルで作成される PolicyValidity テーブルから情報を取得する長期間のファクト取得コンポーネントを提供するこのサンプルの部分に関連するファイル。</span><span class="sxs-lookup"><span data-stu-id="5a881-132">Project, solution, source, and related files for the portion of this sample that provides the long-term fact retriever that retrieves information from the PolicyValidity table created by this sample.</span></span>|  
|<span data-ttu-id="5a881-133">\RulesForMedicalClaims フォルダー。</span><span class="sxs-lookup"><span data-stu-id="5a881-133">In the \RulesForMedicalClaims folder:</span></span><br /><br /> <span data-ttu-id="5a881-134">App.ico、AssemblyInfo.cs、RulesForMedicalClaims.cs、RulesForMedicalClaims.csproj、RulesForMedicalClaims.sln</span><span class="sxs-lookup"><span data-stu-id="5a881-134">App.ico, AssemblyInfo.cs, RulesForMedicalClaims.cs, RulesForMedicalClaims.csproj, RulesForMedicalClaims.sln</span></span>|<span data-ttu-id="5a881-135">プロジェクト、ソリューション、ソース、および他の関連ファイル (RulesForMedicalClaims.exe)、このサンプルとのメイン実行可能ファイルをプログラムで構成するこのサンプルの一部を定義しルール セットが格納されて、サンプルのファクトの構築および実行し、規則セットを使用して、 **PolicyTester**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5a881-135">Project, solution, source, and related files for the portion of this sample that constitutes the main executable for this sample (RulesForMedicalClaims.exe), and which programmatically defines and stores the rule set, constructs sample facts, and then runs the rule set using a **PolicyTester** object.</span></span>|  
|<span data-ttu-id="5a881-136">\RulesForMedicalClaims フォルダー。</span><span class="sxs-lookup"><span data-stu-id="5a881-136">In the \RulesForMedicalClaims folder:</span></span><br /><br /> <span data-ttu-id="5a881-137">MedicalClaims.xsd</span><span class="sxs-lookup"><span data-stu-id="5a881-137">MedicalClaims.xsd</span></span>|<span data-ttu-id="5a881-138">このサンプルに送信されるサンプル医療費請求の構造を定義するスキーマ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="5a881-138">Schema file that defines the structure of the sample medical claims submitted to this sample.</span></span>|  
|<span data-ttu-id="5a881-139">\RulesForMedicalClaims フォルダー。</span><span class="sxs-lookup"><span data-stu-id="5a881-139">In the \RulesForMedicalClaims folder:</span></span><br /><br /> <span data-ttu-id="5a881-140">sampleClaim.xml</span><span class="sxs-lookup"><span data-stu-id="5a881-140">sampleClaim.xml</span></span>|<span data-ttu-id="5a881-141">MedicalClaims.xsd ファイルで定義されているスキーマに準拠しているサンプル入力ファイルです。</span><span class="sxs-lookup"><span data-stu-id="5a881-141">Sample input file that conforms to the schema defined in the file MedicalClaims.xsd.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="5a881-142">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="5a881-142">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-medical-claims-processing-and-testing-policies-sample"></a><span data-ttu-id="5a881-143">ビルドして初期化 Medical Claims Processing and Testing Policies サンプル</span><span class="sxs-lookup"><span data-stu-id="5a881-143">To build and initialize the Medical Claims Processing and Testing Policies sample</span></span>  
  
1. <span data-ttu-id="5a881-144">コンピューターに Northwind データベースがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5a881-144">Make sure that you have the Northwind database on your machine.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="5a881-145">このサンプルを実行するには、SQL Server の Northwind サンプル データベースが必要です。</span><span class="sxs-lookup"><span data-stu-id="5a881-145">To run this sample, you must have the Northwind SQL Server sample database.</span></span> <span data-ttu-id="5a881-146">[ダウンロード](https://www.microsoft.com/download/details.aspx?id=23654)、およびインストールします。</span><span class="sxs-lookup"><span data-stu-id="5a881-146">[Download](https://www.microsoft.com/download/details.aspx?id=23654), and install.</span></span> 
  
2. <span data-ttu-id="5a881-147">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="5a881-147">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="5a881-148">\<*パスのサンプル*\>\Business Rules\Medical Claims Processing and Policies\ を Testing</span><span class="sxs-lookup"><span data-stu-id="5a881-148">\<*Samples Path*\>\Business Rules\Medical Claims Processing and Testing Policies\\</span></span>  
  
3. <span data-ttu-id="5a881-149">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="5a881-149">Run the file Setup.bat, which performs the following actions:</span></span>  
  
   - <span data-ttu-id="5a881-150">コンパイルし、展開、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Claims.dll、FactRetrieverForClaimsProcessing.dll、および RulesForMedicalClaims.dll を含む、このサンプルのプロジェクト。</span><span class="sxs-lookup"><span data-stu-id="5a881-150">Compiles and deploys the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample, including Claims.dll, FactRetrieverForClaimsProcessing.dll, and RulesForMedicalClaims.dll.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5a881-151">このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a881-151">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="5a881-152">開き、Setup.bat ファイルを実行することがなくこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a881-152">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="5a881-153">このキー ペアは、生成されたアセンブリの署名に使用します。</span><span class="sxs-lookup"><span data-stu-id="5a881-153">Use this key pair to sign the resulting assemblies.</span></span>  
  
   - <span data-ttu-id="5a881-154">指定された SQL の実行 SQL クエリ アナライザーを使用して、create_policyvalidity_table.sql という付属のスクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a881-154">Runs the provided SQL script Create_PolicyValidity_Table.sql using SQL Query Analyzer.</span></span> <span data-ttu-id="5a881-155">スクリプトでは、Northwind サンプル データベース内の 2 つのサンプル行と、PolicyValidity テーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a881-155">The script creates the table, PolicyValidity, with two sample rows in the Northwind sample database.</span></span> <span data-ttu-id="5a881-156">このテーブルは、2 つの列を持っています。ID および PolicyStatus します。</span><span class="sxs-lookup"><span data-stu-id="5a881-156">This table has two columns: ID and PolicyStatus.</span></span>  
  
   - <span data-ttu-id="5a881-157">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の送信ポートおよび受信ポートを作成し、バインドします。</span><span class="sxs-lookup"><span data-stu-id="5a881-157">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send and receive ports.</span></span>  
  
   - <span data-ttu-id="5a881-158">受信場所を有効にし、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="5a881-158">Enables the receive location, and starts the send port.</span></span>  
  
   - <span data-ttu-id="5a881-159">オーケストレーションを参加させ、開始します。</span><span class="sxs-lookup"><span data-stu-id="5a881-159">Enlists and starts orchestration.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5a881-160">Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="5a881-160">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="5a881-161">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="5a881-161">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="5a881-162">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="5a881-162">Running This Sample</span></span>  
  
#### <a name="to-run-the-medical-claims-processing-and-testing-policies-sample"></a><span data-ttu-id="5a881-163">Medical Claims Processing and Testing Policies サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="5a881-163">To run the Medical Claims Processing and Testing Policies sample</span></span>  
  
1. <span data-ttu-id="5a881-164">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="5a881-164">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="5a881-165">\<*パスのサンプル*\>\Business Rules\Medical Claims Processing and Policies\RulesForMedicalClaims\bin\Debug\ を Testing</span><span class="sxs-lookup"><span data-stu-id="5a881-165">\<*Samples Path*\>\Business Rules\Medical Claims Processing and Testing Policies\RulesForMedicalClaims\bin\Debug\\</span></span>  
  
2. <span data-ttu-id="5a881-166">コマンドラインで RulesForMedicalClaims.exe ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a881-166">Run the file RulesForMedicalClaims.exe on the command line.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5a881-167">サンプルの請求ファイル sampleClaim.xml の個々 の要素の値を変更し、サンプルを繰り返し実行できます。</span><span class="sxs-lookup"><span data-stu-id="5a881-167">You can change the values of individual elements in the sample claim file sampleClaim.xml and run the sample repeatedly.</span></span> <span data-ttu-id="5a881-168">これらの要素で別の値に対する想定される出力は、次の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a881-168">The expected outputs for different values in these elements are shown in the list that follows.</span></span>  
  
   <span data-ttu-id="5a881-169">送信されたサンプル請求ファイル内の値のさまざまな組み合わせに基づいた出力シナリオは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5a881-169">Output scenarios based on various combinations of values in the submitted sample claims file are:</span></span>  
  
-   <span data-ttu-id="5a881-170">額が $1000 を超える要求を次の出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="5a881-170">For a claim whose amount exceeds $1000, the following output is obtained:</span></span>  
  
    ```  
    Status:  REJECTED!  
    Reason:  Amount of claim has exceeded Policy limit  
    ```  
  
-   <span data-ttu-id="5a881-171">宿泊数が 10 を超える要求を次の出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="5a881-171">For a claim whose number of nights exceeds 10, the following output is obtained:</span></span>  
  
    ```  
    Status:  REJECTED!  
    Reason:  Amount of Nights has exceeded Policy limit  
    ```  
  
-   <span data-ttu-id="5a881-172">日付が有効でない要求 (日付 > 現在の日付)、次の出力が取得します。</span><span class="sxs-lookup"><span data-stu-id="5a881-172">For a claim whose date is not valid (date > current date), the following output in obtained:</span></span>  
  
    ```  
    Status:  REJECTED!  
    Reason:  Cannot submit claims for future dates!  
    ```  
  
-   <span data-ttu-id="5a881-173">無効なポリシー ID を持つクレームの (など、変更することで、 **ID**要素に値 2) ポリシーの有効期限のために次の出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="5a881-173">For a claim with a policy ID that is not valid (for example, by changing the **ID** element to have a value of 2) because of policy expiration, the following output is obtained:</span></span>  
  
    ```  
    Sending to Renewal Department for Customer Smir with Policy # 2  
    Status:  REJECTED!  
    Reason:  Policy ID is invalid  
    ```  
  
-   <span data-ttu-id="5a881-174">有効な要求を次の出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="5a881-174">For a claim that is valid, the following output is obtained:</span></span>  
  
    ```  
    Status:  Claim Accepted!  
    Reason:  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="5a881-175">テキスト ファイル、outputtrace.txt というこのサンプルを実行するたびに、フォルダーの ...\RulesForMedicalClaims\bin\Debug フォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="5a881-175">A text file, outputtrace.txt, is created in the folder ...\RulesForMedicalClaims\bin\Debug folder every time you run this sample.</span></span> <span data-ttu-id="5a881-176">、ルール実行のデバッグ トレースが含まれていると、フォルダー \RulesForMedicalClaims\bin\Debug 下の各実行サイクルの後に作成されます。</span><span class="sxs-lookup"><span data-stu-id="5a881-176">It contains a debug trace of rule execution, and it is created after every execution cycle under the folder \RulesForMedicalClaims\bin\Debug.</span></span> <span data-ttu-id="5a881-177">ルールの実行の出力のトレースを表示するには、このファイルを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="5a881-177">You can examine this file to see the output trace of rule execution.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="5a881-178">コメント</span><span class="sxs-lookup"><span data-stu-id="5a881-178">Comments</span></span>  
 <span data-ttu-id="5a881-179">規則セットの評価で使用されるファクト ソースは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5a881-179">The fact sources used in the rule set evaluation are:</span></span>  
  
- <span data-ttu-id="5a881-180">長期的なファクト取得コンポーネントをします。実装する NET ベースのアプリケーション、 **IFactReriever**インターフェイスでは、FactRetrieverForClaimsProcessing フォルダ内に構築されています。</span><span class="sxs-lookup"><span data-stu-id="5a881-180">A long-term fact retriever, a .NET-based application that implements the **IFactReriever** interface, is built in the folder FactRetrieverForClaimsProcessing.</span></span> <span data-ttu-id="5a881-181">PolicyValidity データベースから (データセットの形式) でデータを取得、ルール条件の評価で使用して、medical claims processing ポリシーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="5a881-181">It is used by the medical claims processing policy to retrieve data (in the form of a dataset) from the PolicyValidity database and to use in rule condition evaluation.</span></span>  
  
- <span data-ttu-id="5a881-182">クレームは、兄弟要素に格納されている、次の情報を含む XML ドキュメントの形式では。名前、ID、額、泊数、および日付。</span><span class="sxs-lookup"><span data-stu-id="5a881-182">The claim is in the form of an XML document that contains the following information, stored in sibling elements: Name, ID, Amount, Nights, and Date.</span></span>  
  
- <span data-ttu-id="5a881-183">A。NET ベースのクラス ライブラリ (Claims) は、使用、 **ClaimResults** (ポリシーが有効でない場合) は、潜在顧客を送信して、状態と、プロパティを使用して、要求の理由を記録するクラスが使用を呼び出すことによって、 **SendLeads**ID とパラメーターとして名前を持つメソッド。</span><span class="sxs-lookup"><span data-stu-id="5a881-183">A .NET-based class library (Claims), with a **ClaimResults** class is used to record the STATUS and REASON of the claim using properties, and to send a lead (if the policy is not valid) by invoking the **SendLeads** method with ID and name as parameters.</span></span>  
  
  <span data-ttu-id="5a881-184">これらのファクト ソースに基づいて、次のように、このシナリオで定義されたルールに説明できます。</span><span class="sxs-lookup"><span data-stu-id="5a881-184">Based on these fact sources, you can informally describe the rules defined for this scenario as follows:</span></span>  
  
1. <span data-ttu-id="5a881-185">入力方向の要求が有効かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5a881-185">Check to see if the incoming claim is valid.</span></span> <span data-ttu-id="5a881-186">量は、クレームの許容される制限を超えるポリシーが (データベース テーブルを調べて確認済み)、期限切れの場合の夜の数が許容される最大を超えたかどうかし、将来の日付、要求が行われた場合、要求が無効です。</span><span class="sxs-lookup"><span data-stu-id="5a881-186">The claim is not valid if the amount is over the allowable limit for a claim, if the policy has expired (verified by checking the database table), if the number of nights has exceeded the maximum allowable limit, and if the claim is made for a future date.</span></span> <span data-ttu-id="5a881-187">要求が無効であると特定された場合、状態と要求の理由を適切に設定します。</span><span class="sxs-lookup"><span data-stu-id="5a881-187">If the claim has been determined to be not valid, set the STATUS and REASON of the claim appropriately.</span></span>  
  
2. <span data-ttu-id="5a881-188">入力方向の要求のポリシー ID の有効期限が切れている場合 (ポリシー ID および患者名) に潜在顧客をポリシー更新部門に送信します。</span><span class="sxs-lookup"><span data-stu-id="5a881-188">If the policy ID of the incoming claim has expired, send a lead (with policy ID and customer name) to the policy renewal department.</span></span>  
  
3. <span data-ttu-id="5a881-189">要求が有効な場合、状態と要求の理由を適切に設定します。</span><span class="sxs-lookup"><span data-stu-id="5a881-189">If the claim is valid, set the STATUS and REASON of the claim appropriately.</span></span>  
  
   <span data-ttu-id="5a881-190">規則とその用語バインドのより形式的に表現は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5a881-190">A more formal representation of the rules and their term bindings is as follows:</span></span>  
  
-   <span data-ttu-id="5a881-191">**ルール 1。チェックの量**</span><span class="sxs-lookup"><span data-stu-id="5a881-191">**Rule 1. Amount check**</span></span>  
  
    ```  
    IF Amount in the XML document is > 1000  
      AND  
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"\  
         &&  
         Claims.ClaimResults.Reason = "Amount of claim has exceeded limit"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   <span data-ttu-id="5a881-192">**規則 2 です。病院に費やされた夜間**</span><span class="sxs-lookup"><span data-stu-id="5a881-192">**Rule 2. Nights spent in the hospital**</span></span>  
  
    ```  
    IF number of nights in the XML document is > 10  
      AND  
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"  
         &&  
         Claims.ClaimResults.Reason = "Amount of claim has exceeded limit"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   <span data-ttu-id="5a881-193">**規則 3 です。日付の有効性**</span><span class="sxs-lookup"><span data-stu-id="5a881-193">**Rule 3. Date validity**</span></span>  
  
    ```  
    IF date on the incoming XML claim is > Today  
      AND   
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"  
         &&  
         Claims.ClaimResults.Reason = "Cannot submit claims in the future!"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   <span data-ttu-id="5a881-194">**規則 4 です。ポリシーの有効性**</span><span class="sxs-lookup"><span data-stu-id="5a881-194">**Rule 4. Policy validity**</span></span>  
  
    ```  
    IF Policy is invalid for the ID in the XML claim (check database)  
      AND  
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"  
         &&  
         Claims.ClaimResults.Reason = "Policy Invalid"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   <span data-ttu-id="5a881-195">**ルール 5。潜在顧客**</span><span class="sxs-lookup"><span data-stu-id="5a881-195">**Rule 5. Sales lead**</span></span>  
  
    ```  
    IF Claim.ClaimResults.Reason = "Policy invalid"  
  
    THEN send a lead to the policy department by invoking the function Claim.ClaimResults.SendLead with customer ID and Name from the incoming XML document.  
  
    ```  
  
-   <span data-ttu-id="5a881-196">**ルール 6。請求の受理**</span><span class="sxs-lookup"><span data-stu-id="5a881-196">**Rule 6. Claim accepted**</span></span>  
  
    ```  
    IF Claim.ClaimResults.Status = null  
  
    THEN Set the claim status to be valid  
         &&  
         Send the lead to the sales department  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5a881-197">参照</span><span class="sxs-lookup"><span data-stu-id="5a881-197">See Also</span></span>  
 [<span data-ttu-id="5a881-198">ビジネス ルール (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="5a881-198">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)