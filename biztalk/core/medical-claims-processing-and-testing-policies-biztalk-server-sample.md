---
title: Medical Claims Processing and Testing Policies (BizTalk Server サンプル) |Microsoft ドキュメント
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
ms.openlocfilehash: 70cba6055c51371ddaaf99775bd5e7a60e7f3929
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007987"
---
# <a name="medical-claims-processing-and-testing-policies-biztalk-server-sample"></a><span data-ttu-id="65b24-102">Medical Claims 処理およびテストのポリシー (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="65b24-102">Medical Claims Processing and Testing Policies (BizTalk Server Sample)</span></span>
<span data-ttu-id="65b24-103">Medical Claims Processing and Testing Policies サンプルは、データベース テーブルおよび受信ドキュメントから派生したファクトを検証し、.NET ベースのオブジェクトを使用して請求処理の結果を記録する複数のルールを含むルール セットを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="65b24-103">The Medical Claims Processing and Testing Policies sample demonstrates how to create a rule set containing multiple rules that examine facts derived from a database table and the inbound document, and which use .NET-based objects to record the results of the claims processing.</span></span>  
  
 <span data-ttu-id="65b24-104">このサンプルは、ビジネス ルール エンジンを使用して、受信した請求に対して医療費請求ルール セットを実行し、請求のステータスとそのステータスの理由を決定する .NET ベースのシンプルなアプリケーションを使用した請求処理シナリオのエンド ツー エンド実行を示します。</span><span class="sxs-lookup"><span data-stu-id="65b24-104">This sample demonstrates end-end execution of the claim processing scenario using a simple .NET-based application that uses the Business Rule Engine to run a medical claims rule set against incoming claims to determine the STATUS of the claim and the REASON for the status.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65b24-105">このサンプルは、デバッグ トレース ファイルを使用してビジネス ルール エンジンの実行を追跡する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="65b24-105">This sample also demonstrates how to trace Business Rule Engine execution using a debug trace file.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="65b24-106">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="65b24-106">What This Sample Does</span></span>  
 <span data-ttu-id="65b24-107">このサンプルは、送信された請求に対して以下の順序でルールを適用します。</span><span class="sxs-lookup"><span data-stu-id="65b24-107">This sample applies the following sequence of rules to submitted claims:</span></span>  
  
1.  <span data-ttu-id="65b24-108">請求額がポリシーの最大限度額を超えている場合は、請求を拒否します。</span><span class="sxs-lookup"><span data-stu-id="65b24-108">Rejects the claim if the total amount claimed exceeds the maximum permitted by the policy.</span></span>  
  
2.  <span data-ttu-id="65b24-109">患者の入院期間がポリシーの最長期間を超えている場合は、請求を拒否します。</span><span class="sxs-lookup"><span data-stu-id="65b24-109">Rejects the claim if the client has stayed in hospitals more nights than the maximum permitted by the policy.</span></span>  
  
3.  <span data-ttu-id="65b24-110">請求日が将来の日付の場合は、請求を拒否します。</span><span class="sxs-lookup"><span data-stu-id="65b24-110">Rejects the claim if the date on the claim is in the future.</span></span>  
  
4.  <span data-ttu-id="65b24-111">ポリシーが有効でない場合は、請求を拒否します。</span><span class="sxs-lookup"><span data-stu-id="65b24-111">Rejects the claim if the policy is not valid.</span></span>  
  
5.  <span data-ttu-id="65b24-112">ポリシーの有効期限が切れている場合は、情報がポリシー ID および患者名と共にセールス部門に送信されます。</span><span class="sxs-lookup"><span data-stu-id="65b24-112">Sends a lead to the sales department with the policy ID and customer name if the policy has expired.</span></span>  
  
6.  <span data-ttu-id="65b24-113">上記以外の場合は、請求が承認されます。</span><span class="sxs-lookup"><span data-stu-id="65b24-113">Otherwise, approves the claim.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="65b24-114">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="65b24-114">Where to Find This Sample</span></span>  
 <span data-ttu-id="65b24-115">\<*パスのサンプル*\>\Business Rules\Medical Claims Processing and Policies\ を Testing</span><span class="sxs-lookup"><span data-stu-id="65b24-115">\<*Samples Path*\>\Business Rules\Medical Claims Processing and Testing Policies\\</span></span>  
  
 <span data-ttu-id="65b24-116">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="65b24-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="65b24-117">ファイル</span><span class="sxs-lookup"><span data-stu-id="65b24-117">File(s)</span></span>|<span data-ttu-id="65b24-118">Description</span><span class="sxs-lookup"><span data-stu-id="65b24-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="65b24-119">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="65b24-119">Cleanup.bat</span></span>|<span data-ttu-id="65b24-120">アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="65b24-120">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="65b24-121">送信ポートと受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="65b24-121">Removes send and receive ports.</span></span> <span data-ttu-id="65b24-122">必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="65b24-122">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="65b24-123">Create_PolicyValidity_Table.sql</span><span class="sxs-lookup"><span data-stu-id="65b24-123">Create_PolicyValidity_Table.sql</span></span>|<span data-ttu-id="65b24-124">PolicyValidity という新しいテーブルを Northwind サンプル データベースに追加する SQL スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="65b24-124">SQL script that adds a new table named PolicyValidity to the Northwind sample database.</span></span>|  
|<span data-ttu-id="65b24-125">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="65b24-125">Setup.bat</span></span>|<span data-ttu-id="65b24-126">このサンプルをビルドおよび初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="65b24-126">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="65b24-127">\Claims フォルダー内のファイル : </span><span class="sxs-lookup"><span data-stu-id="65b24-127">In the \Claims folder:</span></span><br /><br /> <span data-ttu-id="65b24-128">AssemblyInfo.cs、Claims.csproj、Claims.sln、Claims.cs</span><span class="sxs-lookup"><span data-stu-id="65b24-128">AssemblyInfo.cs, Claims.csproj, Claims.sln, Claims.cs</span></span>|<span data-ttu-id="65b24-129">プロジェクト、ソリューション、ソース、および部分では、請求処理の結果を記録するこのサンプルの関連するファイルと呼ばれる、**し**ルールの一部です。</span><span class="sxs-lookup"><span data-stu-id="65b24-129">Project, solution, source, and related files for the portion of this sample that records the result of the claims processing, called the **THEN** portion of a rule.</span></span>|  
|<span data-ttu-id="65b24-130">\FactRetrieverForClaimsProcessing フォルダー内のファイル : </span><span class="sxs-lookup"><span data-stu-id="65b24-130">In the \FactRetrieverForClaimsProcessing folder:</span></span><br /><br /> <span data-ttu-id="65b24-131">AssemblyInfo.cs、FactRetrieverForClaimsProcessing.cs、FactRetrieverForClaimsProcessing.csproj、FactRetrieverForClaimsProcessing.sln</span><span class="sxs-lookup"><span data-stu-id="65b24-131">AssemblyInfo.cs, FactRetrieverForClaimsProcessing.cs, FactRetrieverForClaimsProcessing.csproj, FactRetrieverForClaimsProcessing.sln</span></span>|<span data-ttu-id="65b24-132">このサンプルで、このサンプルによって作成される PolicyValidity テーブルから情報を取得する長期間のファクト取得コンポーネントを提供する部分のプロジェクト、ソリューション、ソース、および関連ファイルです。</span><span class="sxs-lookup"><span data-stu-id="65b24-132">Project, solution, source, and related files for the portion of this sample that provides the long-term fact retriever that retrieves information from the PolicyValidity table created by this sample.</span></span>|  
|<span data-ttu-id="65b24-133">\RulesForMedicalClaims フォルダー内のファイル: </span><span class="sxs-lookup"><span data-stu-id="65b24-133">In the \RulesForMedicalClaims folder:</span></span><br /><br /> <span data-ttu-id="65b24-134">App.ico、AssemblyInfo.cs、RulesForMedicalClaims.cs、RulesForMedicalClaims.csproj、RulesForMedicalClaims.sln</span><span class="sxs-lookup"><span data-stu-id="65b24-134">App.ico, AssemblyInfo.cs, RulesForMedicalClaims.cs, RulesForMedicalClaims.csproj, RulesForMedicalClaims.sln</span></span>|<span data-ttu-id="65b24-135">プロジェクト、ソリューション、ソース、および関連ファイル (RulesForMedicalClaims.exe)、このサンプルとメイン実行可能ファイルをプログラムで構成するこのサンプルの一部ですを定義しルール セットが格納されて、サンプル ファクトの構築および実行し、規則セットを使用して、 **PolicyTester**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="65b24-135">Project, solution, source, and related files for the portion of this sample that constitutes the main executable for this sample (RulesForMedicalClaims.exe), and which programmatically defines and stores the rule set, constructs sample facts, and then runs the rule set using a **PolicyTester** object.</span></span>|  
|<span data-ttu-id="65b24-136">\RulesForMedicalClaims フォルダー内のファイル: </span><span class="sxs-lookup"><span data-stu-id="65b24-136">In the \RulesForMedicalClaims folder:</span></span><br /><br /> <span data-ttu-id="65b24-137">MedicalClaims.xsd</span><span class="sxs-lookup"><span data-stu-id="65b24-137">MedicalClaims.xsd</span></span>|<span data-ttu-id="65b24-138">このサンプルに送信されるサンプル医療費請求の構造を決定するスキーマ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="65b24-138">Schema file that defines the structure of the sample medical claims submitted to this sample.</span></span>|  
|<span data-ttu-id="65b24-139">\RulesForMedicalClaims フォルダー内のファイル: </span><span class="sxs-lookup"><span data-stu-id="65b24-139">In the \RulesForMedicalClaims folder:</span></span><br /><br /> <span data-ttu-id="65b24-140">sampleClaim.xml</span><span class="sxs-lookup"><span data-stu-id="65b24-140">sampleClaim.xml</span></span>|<span data-ttu-id="65b24-141">MedicalClaims.xsd ファイルで定義されているスキーマに準拠したサンプル入力ファイルです。</span><span class="sxs-lookup"><span data-stu-id="65b24-141">Sample input file that conforms to the schema defined in the file MedicalClaims.xsd.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="65b24-142">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="65b24-142">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-medical-claims-processing-and-testing-policies-sample"></a><span data-ttu-id="65b24-143">Medical Claims Processing and Testing Policies サンプルをビルドして初期化するには</span><span class="sxs-lookup"><span data-stu-id="65b24-143">To build and initialize the Medical Claims Processing and Testing Policies sample</span></span>  
  
1.  <span data-ttu-id="65b24-144">コンピューターに Northwind データベースがインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="65b24-144">Make sure that you have the Northwind database on your machine.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="65b24-145">このサンプルを実行するには、SQL Server の Northwind サンプル データベースが必要です。</span><span class="sxs-lookup"><span data-stu-id="65b24-145">To run this sample, you must have the Northwind SQL Server sample database.</span></span> <span data-ttu-id="65b24-146">[ダウンロード](https://www.microsoft.com/download/details.aspx?id=23654)、およびインストールします。</span><span class="sxs-lookup"><span data-stu-id="65b24-146">[Download](https://www.microsoft.com/download/details.aspx?id=23654), and install.</span></span> 
  
2.  <span data-ttu-id="65b24-147">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="65b24-147">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="65b24-148">\<*パスのサンプル*\>\Business Rules\Medical Claims Processing and Policies\ を Testing</span><span class="sxs-lookup"><span data-stu-id="65b24-148">\<*Samples Path*\>\Business Rules\Medical Claims Processing and Testing Policies\\</span></span>  
  
3.  <span data-ttu-id="65b24-149">次の操作を実行する Setup.bat ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="65b24-149">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="65b24-150">このサンプルの [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクト (Claims.dll、FactRetrieverForClaimsProcessing.dll、および RulesForMedicalClaims.dll を含む) をコンパイルして展開します。</span><span class="sxs-lookup"><span data-stu-id="65b24-150">Compiles and deploys the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample, including Claims.dll, FactRetrieverForClaimsProcessing.dll, and RulesForMedicalClaims.dll.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="65b24-151">このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65b24-151">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="65b24-152">開き、Setup.bat ファイルを実行せずにこのサンプルのプロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して、厳密な名前のキー ペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65b24-152">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="65b24-153">このキー ペアは、生成されたアセンブリの署名に使用します。</span><span class="sxs-lookup"><span data-stu-id="65b24-153">Use this key pair to sign the resulting assemblies.</span></span>  
  
    -   <span data-ttu-id="65b24-154">SQL Query Analyzer を使用して、Create_PolicyValidity_Table.sql という付属の SQL スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="65b24-154">Runs the provided SQL script Create_PolicyValidity_Table.sql using SQL Query Analyzer.</span></span> <span data-ttu-id="65b24-155">このスクリプトによって、2 つのサンプル行を含む PolicyValidity というテーブルが Northwind サンプル データベースに作成されます。</span><span class="sxs-lookup"><span data-stu-id="65b24-155">The script creates the table, PolicyValidity, with two sample rows in the Northwind sample database.</span></span> <span data-ttu-id="65b24-156">このテーブルには、2 つの列 (ID および PolicyStatus) があります。</span><span class="sxs-lookup"><span data-stu-id="65b24-156">This table has two columns: ID and PolicyStatus.</span></span>  
  
    -   <span data-ttu-id="65b24-157">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の送信ポートおよび受信ポートを作成し、バインドします。</span><span class="sxs-lookup"><span data-stu-id="65b24-157">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send and receive ports.</span></span>  
  
    -   <span data-ttu-id="65b24-158">受信場所を有効にし、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="65b24-158">Enables the receive location, and starts the send port.</span></span>  
  
    -   <span data-ttu-id="65b24-159">オーケストレーションを参加させ、開始します。</span><span class="sxs-lookup"><span data-stu-id="65b24-159">Enlists and starts orchestration.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="65b24-160">Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="65b24-160">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="65b24-161">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="65b24-161">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="65b24-162">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="65b24-162">Running This Sample</span></span>  
  
#### <a name="to-run-the-medical-claims-processing-and-testing-policies-sample"></a><span data-ttu-id="65b24-163">Medical Claims Processing and Testing Policies サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="65b24-163">To run the Medical Claims Processing and Testing Policies sample</span></span>  
  
1.  <span data-ttu-id="65b24-164">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="65b24-164">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="65b24-165">\<*パスのサンプル*\>\Business Rules\Medical Claims Processing and Policies\RulesForMedicalClaims\bin\Debug\ を Testing</span><span class="sxs-lookup"><span data-stu-id="65b24-165">\<*Samples Path*\>\Business Rules\Medical Claims Processing and Testing Policies\RulesForMedicalClaims\bin\Debug\\</span></span>  
  
2.  <span data-ttu-id="65b24-166">コマンド ラインで RulesForMedicalClaims.exe ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="65b24-166">Run the file RulesForMedicalClaims.exe on the command line.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="65b24-167">サンプル請求ファイル sampleClaim.xml の個々の要素の値を変更して、サンプルを繰り返し実行できます。</span><span class="sxs-lookup"><span data-stu-id="65b24-167">You can change the values of individual elements in the sample claim file sampleClaim.xml and run the sample repeatedly.</span></span> <span data-ttu-id="65b24-168">これらの要素の値が異なるいくつかのシナリオの予期される出力を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="65b24-168">The expected outputs for different values in these elements are shown in the list that follows.</span></span>  
  
 <span data-ttu-id="65b24-169">送信されたサンプル請求ファイル内の値のさまざまな組み合わせによって得られる出力シナリオは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="65b24-169">Output scenarios based on various combinations of values in the submitted sample claims file are:</span></span>  
  
-   <span data-ttu-id="65b24-170">請求額が $1000 を超える場合、次の出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="65b24-170">For a claim whose amount exceeds $1000, the following output is obtained:</span></span>  
  
    ```  
    Status:  REJECTED!  
    Reason:  Amount of claim has exceeded Policy limit  
    ```  
  
-   <span data-ttu-id="65b24-171">入院期間が 10 泊を超える請求の場合、次の出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="65b24-171">For a claim whose number of nights exceeds 10, the following output is obtained:</span></span>  
  
    ```  
    Status:  REJECTED!  
    Reason:  Amount of Nights has exceeded Policy limit  
    ```  
  
-   <span data-ttu-id="65b24-172">日付が無効な請求の場合 (日付が現在の日付よりも先の場合)、次の出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="65b24-172">For a claim whose date is not valid (date > current date), the following output in obtained:</span></span>  
  
    ```  
    Status:  REJECTED!  
    Reason:  Cannot submit claims for future dates!  
    ```  
  
-   <span data-ttu-id="65b24-173">無効なポリシー ID を持つクレームの (など、変更することによって、 **ID** 2 の値を持つ要素) ポリシーの有効期限のため、次の出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="65b24-173">For a claim with a policy ID that is not valid (for example, by changing the **ID** element to have a value of 2) because of policy expiration, the following output is obtained:</span></span>  
  
    ```  
    Sending to Renewal Department for Customer Smir with Policy # 2  
    Status:  REJECTED!  
    Reason:  Policy ID is invalid  
    ```  
  
-   <span data-ttu-id="65b24-174">有効な請求の場合は、次の出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="65b24-174">For a claim that is valid, the following output is obtained:</span></span>  
  
    ```  
    Status:  Claim Accepted!  
    Reason:  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="65b24-175">このサンプルを実行するたびに、outputtrace.txt というテキスト ファイルが ...\RulesForMedicalClaims\bin\Debug フォルダに作成されます。</span><span class="sxs-lookup"><span data-stu-id="65b24-175">A text file, outputtrace.txt, is created in the folder ...\RulesForMedicalClaims\bin\Debug folder every time you run this sample.</span></span> <span data-ttu-id="65b24-176">このテキスト ファイルには、ルール実行のデバッグ トレースが含まれます。このファイルは、各実行サイクルの後に \RulesForMedicalClaims\bin\Debug フォルダに作成されます。</span><span class="sxs-lookup"><span data-stu-id="65b24-176">It contains a debug trace of rule execution, and it is created after every execution cycle under the folder \RulesForMedicalClaims\bin\Debug.</span></span> <span data-ttu-id="65b24-177">このファイルを参照して、ルール実行の出力トレースを確認できます。</span><span class="sxs-lookup"><span data-stu-id="65b24-177">You can examine this file to see the output trace of rule execution.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="65b24-178">コメント</span><span class="sxs-lookup"><span data-stu-id="65b24-178">Comments</span></span>  
 <span data-ttu-id="65b24-179">ルール セットの評価に使用されるファクト ソースは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="65b24-179">The fact sources used in the rule set evaluation are:</span></span>  
  
-   <span data-ttu-id="65b24-180">長期的なファクト取得コンポーネント、します。実装する NET ベースのアプリケーション、 **IFactReriever**インターフェイスでは、FactRetrieverForClaimsProcessing フォルダ内に組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="65b24-180">A long-term fact retriever, a .NET-based application that implements the **IFactReriever** interface, is built in the folder FactRetrieverForClaimsProcessing.</span></span> <span data-ttu-id="65b24-181">このコンポーネントは、PolicyValidity データベースからデータを (データセットの形式で) 取得し、ルール条件を評価するために Medical Claims Processing ポリシーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="65b24-181">It is used by the medical claims processing policy to retrieve data (in the form of a dataset) from the PolicyValidity database and to use in rule condition evaluation.</span></span>  
  
-   <span data-ttu-id="65b24-182">請求の形式は、兄弟要素に保存された名前、ID、請求額、泊数、および日付の情報を含む XML ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="65b24-182">The claim is in the form of an XML document that contains the following information, stored in sibling elements: Name, ID, Amount, Nights, and Date.</span></span>  
  
-   <span data-ttu-id="65b24-183">です。NET ベースのクラス ライブラリ (Claims) で、 **ClaimResults**クラスには、状態と、プロパティを使用して、要求の理由を記録する (ポリシーが有効でない場合)、潜在顧客を送信して、使用を呼び出すことによって、 **SendLeads**ID と名前のパラメーターを含むメソッドです。</span><span class="sxs-lookup"><span data-stu-id="65b24-183">A .NET-based class library (Claims), with a **ClaimResults** class is used to record the STATUS and REASON of the claim using properties, and to send a lead (if the policy is not valid) by invoking the **SendLeads** method with ID and name as parameters.</span></span>  
  
 <span data-ttu-id="65b24-184">これらのファクト ソースに基づいて、このシナリオについて定義されたルールは、次のように説明できます。</span><span class="sxs-lookup"><span data-stu-id="65b24-184">Based on these fact sources, you can informally describe the rules defined for this scenario as follows:</span></span>  
  
1.  <span data-ttu-id="65b24-185">受信した請求が有効かどうかをチェックします。</span><span class="sxs-lookup"><span data-stu-id="65b24-185">Check to see if the incoming claim is valid.</span></span> <span data-ttu-id="65b24-186">請求額が限度額を超えている場合、ポリシーの有効期限が切れている場合 (データベース テーブルをチェックすることによって確認)、入院日数が限度を超えている場合、および請求日が将来の日付である場合、請求は無効です。</span><span class="sxs-lookup"><span data-stu-id="65b24-186">The claim is not valid if the amount is over the allowable limit for a claim, if the policy has expired (verified by checking the database table), if the number of nights has exceeded the maximum allowable limit, and if the claim is made for a future date.</span></span> <span data-ttu-id="65b24-187">請求が無効であると判断された場合、請求のステータスおよび理由を適宜設定します。</span><span class="sxs-lookup"><span data-stu-id="65b24-187">If the claim has been determined to be not valid, set the STATUS and REASON of the claim appropriately.</span></span>  
  
2.  <span data-ttu-id="65b24-188">受信請求のポリシー ID の有効期限が切れている場合は、ポリシー更新部門に情報 (ポリシー ID および患者名) を送信します。</span><span class="sxs-lookup"><span data-stu-id="65b24-188">If the policy ID of the incoming claim has expired, send a lead (with policy ID and customer name) to the policy renewal department.</span></span>  
  
3.  <span data-ttu-id="65b24-189">請求が有効な場合は、請求のステータスおよび理由を適宜設定します。</span><span class="sxs-lookup"><span data-stu-id="65b24-189">If the claim is valid, set the STATUS and REASON of the claim appropriately.</span></span>  
  
 <span data-ttu-id="65b24-190">ルールとその条件のバインドをより形式的に表現すると次のようになります。</span><span class="sxs-lookup"><span data-stu-id="65b24-190">A more formal representation of the rules and their term bindings is as follows:</span></span>  
  
-   <span data-ttu-id="65b24-191">**ルール 1 です。金額のチェック**</span><span class="sxs-lookup"><span data-stu-id="65b24-191">**Rule 1. Amount check**</span></span>  
  
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
  
-   <span data-ttu-id="65b24-192">**ルール 2 です。病院で費やされた夜間**</span><span class="sxs-lookup"><span data-stu-id="65b24-192">**Rule 2. Nights spent in the hospital**</span></span>  
  
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
  
-   <span data-ttu-id="65b24-193">**規則 3 です。日付の有効性**</span><span class="sxs-lookup"><span data-stu-id="65b24-193">**Rule 3. Date validity**</span></span>  
  
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
  
-   <span data-ttu-id="65b24-194">**ルール 4. です。ポリシーの有効性**</span><span class="sxs-lookup"><span data-stu-id="65b24-194">**Rule 4. Policy validity**</span></span>  
  
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
  
-   <span data-ttu-id="65b24-195">**ルール 5. です。セールス リード**</span><span class="sxs-lookup"><span data-stu-id="65b24-195">**Rule 5. Sales lead**</span></span>  
  
    ```  
    IF Claim.ClaimResults.Reason = "Policy invalid"  
  
    THEN send a lead to the policy department by invoking the function Claim.ClaimResults.SendLead with customer ID and Name from the incoming XML document.  
  
    ```  
  
-   <span data-ttu-id="65b24-196">**ルール 6. です。請求の受理**</span><span class="sxs-lookup"><span data-stu-id="65b24-196">**Rule 6. Claim accepted**</span></span>  
  
    ```  
    IF Claim.ClaimResults.Status = null  
  
    THEN Set the claim status to be valid  
         &&  
         Send the lead to the sales department  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="65b24-197">参照</span><span class="sxs-lookup"><span data-stu-id="65b24-197">See Also</span></span>  
 [<span data-ttu-id="65b24-198">ビジネス ルール (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="65b24-198">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)