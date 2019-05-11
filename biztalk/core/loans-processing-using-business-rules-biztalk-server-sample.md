---
title: Loans Processing Using Business Rules (BizTalk Server サンプル) |Microsoft Docs
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
ms.assetid: 3e1c80c6-adc1-4a0f-83fd-409ce1b8f21f
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8b878b782c49f1fc4827577444b8bffbec346fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380618"
---
# <a name="loans-processing-using-business-rules-biztalk-server-sample"></a><span data-ttu-id="814cd-102">Loans Processing Using Business Rules (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="814cd-102">Loans Processing Using Business Rules (BizTalk Server Sample)</span></span>
<span data-ttu-id="814cd-103">Loans Processing Using Business Rules サンプルでは、ファクトと呼ばれる入力の組み合わせを使用して、処理中のドキュメント内のフィールドの設定を計算する方法と、オーケストレーション内で管理しているルール セットを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="814cd-103">The Loans Processing Using Business Rules sample demonstrates how to use a set of rules managed within an orchestration, and how to use a combination of inputs known as facts, to calculate settings for some fields within a document being processed.</span></span> <span data-ttu-id="814cd-104">ファクトは呼び出しの結果であることができます、します。NET ベースのアセンブリ、メッセージの XML から取得した値またはデータベースからデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="814cd-104">Facts can be the result of calling a .NET-based assembly, the values retrieved from the XML of the message, or the data retrieved from a database.</span></span> <span data-ttu-id="814cd-105">このサンプルでは、どのルールを変更できます、いつでもでも再デプロイすることがなく、後続の計算に影響を与えるも示します。</span><span class="sxs-lookup"><span data-stu-id="814cd-105">The sample also demonstrates how you can change the rules at any time, affecting subsequent calculations without the need to redeploy.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="814cd-106">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="814cd-106">What This Sample Does</span></span>  
 <span data-ttu-id="814cd-107">このサンプルでは、簡単なローン処理のシナリオのコンテキスト内でこれらの機能を示します。</span><span class="sxs-lookup"><span data-stu-id="814cd-107">This sample demonstrates these capabilities within the context of a simplified loan processing scenario.</span></span> <span data-ttu-id="814cd-108">BizTalk Server オーケストレーションは、ピックアップし、XML メッセージ形式、ローン ケースとも呼ばれますのローン申請を処理します。</span><span class="sxs-lookup"><span data-stu-id="814cd-108">BizTalk Server orchestration picks up and processes a loan application, also known as a loan case, in XML message format.</span></span> <span data-ttu-id="814cd-109">このオーケストレーションは、規則の適用の結果とメッセージの変更と、出力フォルダーにファイルとして、メッセージを書き込み、規則に従って受信メッセージを評価するのにビジネス ルール エンジンを使用します。</span><span class="sxs-lookup"><span data-stu-id="814cd-109">This orchestration uses the Business Rule Engine to evaluate incoming messages according to the rules, modifying the message with the result of the application of the rules, and then writing the message as a file to an output folder.</span></span>  

 <span data-ttu-id="814cd-110">このサンプルの設定の処理中のメッセージを含む複数のソースからのファクトに基づいた、 **IncomeStatus**、 **CommitmentsStatus**、 **EmploymentStatus**、および**ResidencyStatus**処理中のメッセージの要素。</span><span class="sxs-lookup"><span data-stu-id="814cd-110">Based on facts from several sources, including the message being processed, this sample sets the **IncomeStatus**, **CommitmentsStatus**, **EmploymentStatus**, and **ResidencyStatus** elements of the message being processed.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="814cd-111">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="814cd-111">Where to Find This Sample</span></span>  
 <span data-ttu-id="814cd-112">\<*パスのサンプル*\>\Business Rules\Loans ビジネス Rules\ を使用した処理</span><span class="sxs-lookup"><span data-stu-id="814cd-112">\<*Samples Path*\>\Business Rules\Loans Processing using Business Rules\\</span></span>  

 <span data-ttu-id="814cd-113">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="814cd-113">The following table shows the files in this sample and describes their purpose.</span></span>  


|                                                                                    <span data-ttu-id="814cd-114">ファイル</span><span class="sxs-lookup"><span data-stu-id="814cd-114">File(s)</span></span>                                                                                    |                                                                                                                <span data-ttu-id="814cd-115">説明</span><span class="sxs-lookup"><span data-stu-id="814cd-115">Description</span></span>                                                                                                                 |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                   <span data-ttu-id="814cd-116">Case.xsd</span><span class="sxs-lookup"><span data-stu-id="814cd-116">Case.xsd</span></span>                                                                                    |                                                                                 <span data-ttu-id="814cd-117">受信ローン申請、ローン ケースとも呼ばれるスキーマ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="814cd-117">Schema file for inbound loan applications, otherwise known as loan cases.</span></span>                                                                                  |
|                                                                                  <span data-ttu-id="814cd-118">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="814cd-118">Cleanup.bat</span></span>                                                                                  |                   <span data-ttu-id="814cd-119">アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="814cd-119">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="814cd-120">送信ポートと受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="814cd-120">Removes send and receive ports.</span></span> <span data-ttu-id="814cd-121">必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="814cd-121">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>                   |
|                                                                           <span data-ttu-id="814cd-122">Create_CustInfo_Table.sql</span><span class="sxs-lookup"><span data-stu-id="814cd-122">Create_CustInfo_Table.sql</span></span>                                                                           |                                                                              <span data-ttu-id="814cd-123">SQL Northwind サンプル データベースに CustInfo テーブルを作成するための SQL スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="814cd-123">SQL script for creating the CustInfo table in the SQL Northwind sample database.</span></span>                                                                              |
|                                                                           <span data-ttu-id="814cd-124">LoanProcessorBinding.xml</span><span class="sxs-lookup"><span data-stu-id="814cd-124">LoanProcessorBinding.xml</span></span>                                                                            |                                                                                               <span data-ttu-id="814cd-125">ポートのバインドなど、自動化されたセットアップに使用されます。</span><span class="sxs-lookup"><span data-stu-id="814cd-125">Used for automated setup such as port binding.</span></span>                                                                                               |
|                                                                   <span data-ttu-id="814cd-126">LoansProcessor.btproj, LoansProcessor.sln</span><span class="sxs-lookup"><span data-stu-id="814cd-126">LoansProcessor.btproj, LoansProcessor.sln</span></span>                                                                   |                                                                                            <span data-ttu-id="814cd-127">このサンプルの BizTalk プロジェクトおよびソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="814cd-127">BizTalk project and solution files for this sample.</span></span>                                                                                             |
|                                                                             <span data-ttu-id="814cd-128">マイ サンプル Service.odx</span><span class="sxs-lookup"><span data-stu-id="814cd-128">My Sample Service.odx</span></span>                                                                             |                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="814cd-129">このサンプルのオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="814cd-129">orchestration for this sample.</span></span>                                                              |
|                                                                                <span data-ttu-id="814cd-130">sampleLoan.xml</span><span class="sxs-lookup"><span data-stu-id="814cd-130">sampleLoan.xml</span></span>                                                                                 |                                                               <span data-ttu-id="814cd-131">サンプル入力ファイル、ファイルの XML 構造の末尾に次の 4 つの状態要素の空の値です。</span><span class="sxs-lookup"><span data-stu-id="814cd-131">Sample input file, with empty values for the four status elements at the end of the XML structure in the file.</span></span>                                                               |
|                                                                                   <span data-ttu-id="814cd-132">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="814cd-132">Setup.bat</span></span>                                                                                   |                                                                                                 <span data-ttu-id="814cd-133">このサンプルをビルドおよび初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="814cd-133">Used to build and initialize this sample.</span></span>                                                                                                  |
|         <span data-ttu-id="814cd-134">\CreateRules フォルダー。</span><span class="sxs-lookup"><span data-stu-id="814cd-134">In the \CreateRules folder:</span></span><br /><br /> <span data-ttu-id="814cd-135">App.ico, AssemblyInfo.cs, Case.xsd, CreateLoanProcessingPolicy.csproj, CreateLoanProcessingPolicy.sln, WriteToBRL.cs</span><span class="sxs-lookup"><span data-stu-id="814cd-135">App.ico, AssemblyInfo.cs, Case.xsd, CreateLoanProcessingPolicy.csproj, CreateLoanProcessingPolicy.sln, WriteToBRL.cs</span></span>          | <span data-ttu-id="814cd-136">VisualC#プロジェクト、ソリューション、ソース、および関連ファイルをプログラムで、セット内の規則を作成するアプリケーションを作成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="814cd-136">Visual C# project, solution, source, and related files used to create the application that programmatically creates the rules in the set.</span></span> <span data-ttu-id="814cd-137">一連の規則をプログラムで構築するための例については、ソース ファイル WriteToBRL.cs を参照してください。</span><span class="sxs-lookup"><span data-stu-id="814cd-137">For examples of programmatically building sets of rules, refer to the source file WriteToBRL.cs.</span></span> |
| <span data-ttu-id="814cd-138">\MyFactRetriever フォルダー。</span><span class="sxs-lookup"><span data-stu-id="814cd-138">In the \myFactRetriever folder:</span></span><br /><br /> <span data-ttu-id="814cd-139">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="814cd-139">AssemblyInfo.cs</span></span><br /><br /> <span data-ttu-id="814cd-140">FactRetrieverForLoansProcessing.cs</span><span class="sxs-lookup"><span data-stu-id="814cd-140">FactRetrieverForLoansProcessing.cs</span></span><br /><br /> <span data-ttu-id="814cd-141">myFactRetriever.csproj</span><span class="sxs-lookup"><span data-stu-id="814cd-141">myFactRetriever.csproj</span></span><br /><br /> <span data-ttu-id="814cd-142">myFactRetriever.sln</span><span class="sxs-lookup"><span data-stu-id="814cd-142">myFactRetriever.sln</span></span> |                 <span data-ttu-id="814cd-143">VisualC#プロジェクト、ソリューション、ソース、および関連ファイルを使用して、先ほど追加した Northwind サンプルの SQL Server データベースに CustInfo テーブルから情報を取得するアセンブリを作成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="814cd-143">Visual C# project, solution, source, and related files used to create an assembly that you use to retrieve information from the CustInfo table added earlier to the Northwind sample SQL Server database.</span></span>                  |

## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="814cd-144">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="814cd-144">Building and Initializing This Sample</span></span>  

#### <a name="to-build-and-initialize-the-loans-processing-using-business-rules-sample"></a><span data-ttu-id="814cd-145">ビルドして初期化 Loans Processing Using Business Rules サンプル</span><span class="sxs-lookup"><span data-stu-id="814cd-145">To build and initialize the Loans Processing Using Business Rules sample</span></span>  

1. <span data-ttu-id="814cd-146">コンピューターに Northwind データベースがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="814cd-146">Make sure that you have the Northwind database on your machine.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="814cd-147">このサンプルを実行するには、SQL Server の Northwind サンプル データベースが必要です。</span><span class="sxs-lookup"><span data-stu-id="814cd-147">To run this sample, you must have the Northwind SQL Server sample database.</span></span> <span data-ttu-id="814cd-148">[ダウンロード](https://www.microsoft.com/download/details.aspx?id=23654)、およびインストールします。</span><span class="sxs-lookup"><span data-stu-id="814cd-148">[Download](https://www.microsoft.com/download/details.aspx?id=23654), and install.</span></span> 

2. <span data-ttu-id="814cd-149">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="814cd-149">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="814cd-150">\<*パスのサンプル*\>\Business Rules\Loans Processing using Business Rules</span><span class="sxs-lookup"><span data-stu-id="814cd-150">\<*Samples Path*\>\Business Rules\Loans Processing using Business Rules</span></span>  

3. <span data-ttu-id="814cd-151">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="814cd-151">Run the file Setup.bat, which performs the following actions:</span></span>  

   - <span data-ttu-id="814cd-152">このサンプルの以前の実行からときに残ったデータを排除する GAC をクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="814cd-152">Cleans up the GAC to eliminate any residual data from previous runs of this sample.</span></span>  

   - <span data-ttu-id="814cd-153">コンパイルし、展開、ファクト取得プログラム myFactRetreiever.dll します。</span><span class="sxs-lookup"><span data-stu-id="814cd-153">Compiles and deploys the fact retriever program, myFactRetreiever.dll.</span></span>  

   - <span data-ttu-id="814cd-154">SQL スクリプト ファイル Create_CustInfo_Table.sql を使用して、Northwind サンプル SQL データベースに CustInfo という名前のテーブルを追加します。</span><span class="sxs-lookup"><span data-stu-id="814cd-154">Using the SQL script file Create_CustInfo_Table.sql, adds a table named CustInfo to the Northwind sample SQL database.</span></span>  

   - <span data-ttu-id="814cd-155">このサンプルの以前の実行のときに残ったに共有 SQL ルール ストアをクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="814cd-155">Cleans up the shared SQL rule store to eliminate residue of previous runs of this sample.</span></span>  

   - <span data-ttu-id="814cd-156">作成、公開、され、ローン処理ルール セットの最新バージョン (1.0) をデプロイします。</span><span class="sxs-lookup"><span data-stu-id="814cd-156">Creates, publishes, and deploys the most recent version (1.0) of the loans processing rule set.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="814cd-157">ツールに付属しているビジネス ルール作成ツールを使用する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をプログラムで設定されているルールを確認します。</span><span class="sxs-lookup"><span data-stu-id="814cd-157">You can use the Business Rule Composer tool supplied with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to examine the rules that have been set programmatically.</span></span>  

   - <span data-ttu-id="814cd-158">入力 (In) フォルダと出力 (Out) フォルダこのサンプルを作成します。</span><span class="sxs-lookup"><span data-stu-id="814cd-158">Creates the input (In) and output (Out) folders for this sample.</span></span>  

   - <span data-ttu-id="814cd-159">コンパイルし、残りの展開[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルでは、このサンプルを調整するために使用するオーケストレーションを含む BizTalk プロジェクトを含むプロジェクト。</span><span class="sxs-lookup"><span data-stu-id="814cd-159">Compiles and deploys the remaining [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample, including the BizTalk project that contains the orchestration you use to coordinate this sample.</span></span>  

   - <span data-ttu-id="814cd-160">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。</span><span class="sxs-lookup"><span data-stu-id="814cd-160">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="814cd-161">このサンプルでは、作成してポートをバインドする場合は、次の警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="814cd-161">This sample displays the following warnings when creating and binding ports:</span></span>  
     >   
     >  `Warning: Receive handler not specified for receive location "LoansProcessor_1.0.0.0_LoansProcessor.My_Sample_Service_Incoming_ReceiveLocation"; updating with first receive handler with matching transport type.`  
     >   
     >  `Warning: Host not specified for orchestration "LoansProcessor.My_Sample_Service"; updating with first available host.`  
     >   
     >  <span data-ttu-id="814cd-162">これらの警告は、無視してもかまいません </span><span class="sxs-lookup"><span data-stu-id="814cd-162">You can safely ignore these warnings.</span></span> <span data-ttu-id="814cd-163">(インストールでの名前付け方法はユーザーによって異なる可能性があるため、ホスト名と受信ハンドラーはバインド ファイルから除外されています。)</span><span class="sxs-lookup"><span data-stu-id="814cd-163">(To accommodate for possible naming differences in user installations, the host name and receive handler have been omitted from the binding file.)</span></span>  

   - <span data-ttu-id="814cd-164">受信場所を有効にし、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="814cd-164">Enables the receive location, and starts the send port.</span></span>  

   - <span data-ttu-id="814cd-165">参加させ、オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="814cd-165">Enlists and starts the orchestration.</span></span>  

> [!NOTE]
>  <span data-ttu-id="814cd-166">BizTalk ホスト名が BizTalkServerApplication でない場合は、Setup.bat ファイルおよび LoanProcessorBinding.xml 適切なホスト名を反映するようにファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="814cd-166">If your BizTalk host name is not BizTalkServerApplication, modify the file Setup.bat and the file LoanProcessorBinding.xml to reflect the proper host name.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="814cd-167">このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="814cd-167">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="814cd-168">開き、Setup.bat ファイルを実行することがなくこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="814cd-168">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="814cd-169">このキー ペアは、生成されたアセンブリの署名に使用します。</span><span class="sxs-lookup"><span data-stu-id="814cd-169">Use this key pair to sign the resulting assemblies.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="814cd-170">Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="814cd-170">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="814cd-171">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="814cd-171">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  

## <a name="running-this-sample"></a><span data-ttu-id="814cd-172">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="814cd-172">Running This Sample</span></span>  

#### <a name="to-run-the-loans-processing-using-business-rules-sample"></a><span data-ttu-id="814cd-173">Loans Processing Using Business Rules サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="814cd-173">To run the Loans Processing Using Business Rules sample</span></span>  

1. <span data-ttu-id="814cd-174">ファイル sampleLoan.xml のコピー、 **\In**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="814cd-174">Paste a copy of the file sampleLoan.xml into the **\In** folder.</span></span>  

2. <span data-ttu-id="814cd-175">フォルダーに作成した .xml ファイルを観察**アウト**します。データが XML 構造の末尾に次の 4 つの状態要素に追加の入力 XML メッセージが含まれています。**IncomeStatus**、 **CommitmentsStatus**、 **EmploymentStatus**、および**ResidencyStatus**します。</span><span class="sxs-lookup"><span data-stu-id="814cd-175">Observe the .xml file created in the folder **Out**. It contains the input XML message with data added to the following four status elements at the end of the XML structure: **IncomeStatus**, **CommitmentsStatus**, **EmploymentStatus**, and **ResidencyStatus**.</span></span>  

   <span data-ttu-id="814cd-176">規則セット内のルールを変更するビジネス ルール作成ツールを使用し、それらのルールを再デプロイできます。</span><span class="sxs-lookup"><span data-stu-id="814cd-176">You can use the Business Rule Composer tool to change the rules in the rule set, and then redeploy those rules.</span></span>  

#### <a name="to-use-the-business-rule-composer-tool-to-change-one-or-more-of-the-rules-in-a-rule-set"></a><span data-ttu-id="814cd-177">ビジネス ルール作成ツールを使用して、1 つ以上の規則セット内のルールを変更するには</span><span class="sxs-lookup"><span data-stu-id="814cd-177">To use the Business Rule Composer tool to change one or more of the rules in a rule set</span></span>  

1. <span data-ttu-id="814cd-178">クリックして**開始**、 をポイント**プログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="814cd-178">Click **Start**, point to **Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Business Rule Composer**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="814cd-179">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="814cd-179">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="814cd-180">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="814cd-180">To do this, right-click the application, and then select **Run as administrator**.</span></span>  

2. <span data-ttu-id="814cd-181">**SQL Server**ダイアログ ボックスで、をクリックして **[ok]** ルール ストアに接続します。</span><span class="sxs-lookup"><span data-stu-id="814cd-181">In the **SQL Server** dialog box, click **OK** to connect to the rule store.</span></span>  

3. <span data-ttu-id="814cd-182">**ポリシー エクスプ ローラー**、ノードの下**LoanProcessing**を右クリックし、**バージョン 1.0-展開済み**ノード、およびクリック**コピー**します。</span><span class="sxs-lookup"><span data-stu-id="814cd-182">In **Policy Explorer**, below the node **LoanProcessing**, right-click the **Version 1.0 – Deployed** node, and then click **Copy**.</span></span>  

4. <span data-ttu-id="814cd-183">右クリック**LoanProcessing**、 をクリックし、**貼り付け**します。</span><span class="sxs-lookup"><span data-stu-id="814cd-183">Right-click **LoanProcessing**, and then click **Paste**.</span></span>  

5. <span data-ttu-id="814cd-184">ルールまたはさまざまな値の原因となる方法で処理を変更、 **IncomeStatus**、 **CommitmentsStatus**、 **EmploymentStatus**、および**ResidencyStatus**要素。</span><span class="sxs-lookup"><span data-stu-id="814cd-184">Change any rule or action in a way that will result in different values for the **IncomeStatus**, **CommitmentsStatus**, **EmploymentStatus**, and **ResidencyStatus** elements.</span></span> <span data-ttu-id="814cd-185">否定部分の値を変更することを確認します (基本的には、 **Else**句) ルールを変更するのです。</span><span class="sxs-lookup"><span data-stu-id="814cd-185">Ensure that you also change the value of the negation portion (essentially, the **Else** clause) of any rule that you choose to change.</span></span>  

    <span data-ttu-id="814cd-186">次の表では、このサンプルで使用される規則のセットを示します。</span><span class="sxs-lookup"><span data-stu-id="814cd-186">The following table shows the set of rules used by this sample.</span></span> <span data-ttu-id="814cd-187">特に断り、しない限り、ファクトは受信 XML メッセージです。</span><span class="sxs-lookup"><span data-stu-id="814cd-187">Unless specifically mentioned otherwise, facts are from the incoming XML message.</span></span> <span data-ttu-id="814cd-188">文字列 (db) では、ファクトのソースとしてデータベースを示します。</span><span class="sxs-lookup"><span data-stu-id="814cd-188">The string (db) indicates a database as the source of a fact.</span></span>  


   |  <span data-ttu-id="814cd-189">規則番号</span><span class="sxs-lookup"><span data-stu-id="814cd-189">Rule number</span></span>   |        <span data-ttu-id="814cd-190">ルール名</span><span class="sxs-lookup"><span data-stu-id="814cd-190">Rule name</span></span>        |                                                                             <span data-ttu-id="814cd-191">説明</span><span class="sxs-lookup"><span data-stu-id="814cd-191">Description</span></span>                                                                             |
   |----------------|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |       <span data-ttu-id="814cd-192">1</span><span class="sxs-lookup"><span data-stu-id="814cd-192">1</span></span>        |   <span data-ttu-id="814cd-193">収入状態ルール</span><span class="sxs-lookup"><span data-stu-id="814cd-193">Income Status Rule</span></span>    |                                       <span data-ttu-id="814cd-194">IF **BasicSalary** + **OtherIncome** > 0</span><span class="sxs-lookup"><span data-stu-id="814cd-194">IF **BasicSalary** + **OtherIncome** > 0</span></span><br /><br /> <span data-ttu-id="814cd-195">**IncomeStatus** = **有効**</span><span class="sxs-lookup"><span data-stu-id="814cd-195">THEN **IncomeStatus** = **Valid**</span></span>                                        |
   |       <span data-ttu-id="814cd-196">2</span><span class="sxs-lookup"><span data-stu-id="814cd-196">2</span></span>        | <span data-ttu-id="814cd-197">契約状態ルール</span><span class="sxs-lookup"><span data-stu-id="814cd-197">Commitments Status Rule</span></span> | <span data-ttu-id="814cd-198">IF **ID** == **ID (db)**</span><span class="sxs-lookup"><span data-stu-id="814cd-198">IF **ID** == **ID (db)**</span></span><br /><br /> <span data-ttu-id="814cd-199">AND</span><span class="sxs-lookup"><span data-stu-id="814cd-199">AND</span></span><br /><br /> <span data-ttu-id="814cd-200">IF **CreditCardBalance (db)** > 500</span><span class="sxs-lookup"><span data-stu-id="814cd-200">IF **CreditCardBalance (db)** > 500</span></span><br /><br /> <span data-ttu-id="814cd-201">THEN **CommitmentsStatus** =</span><span class="sxs-lookup"><span data-stu-id="814cd-201">THEN **CommitmentsStatus** =</span></span><br /><br /> <span data-ttu-id="814cd-202">「コンピューティング コミットメント」</span><span class="sxs-lookup"><span data-stu-id="814cd-202">"Compute Commitments"</span></span> |
   |       <span data-ttu-id="814cd-203">3</span><span class="sxs-lookup"><span data-stu-id="814cd-203">3</span></span>        | <span data-ttu-id="814cd-204">雇用状態ルール</span><span class="sxs-lookup"><span data-stu-id="814cd-204">Employment Status Rule</span></span>  |                                  <span data-ttu-id="814cd-205">IF **EmploymentType &#124; TimeInMonths** > 18</span><span class="sxs-lookup"><span data-stu-id="814cd-205">IF **EmploymentType &#124; TimeInMonths** > 18</span></span><br /><br /> <span data-ttu-id="814cd-206">**EmploymentStatus** = **有効**</span><span class="sxs-lookup"><span data-stu-id="814cd-206">THEN **EmploymentStatus** = **Valid**</span></span>                                   |
   |       <span data-ttu-id="814cd-207">4</span><span class="sxs-lookup"><span data-stu-id="814cd-207">4</span></span>        |  <span data-ttu-id="814cd-208">常駐状態ルール</span><span class="sxs-lookup"><span data-stu-id="814cd-208">Residency Status Rule</span></span>  |                                  <span data-ttu-id="814cd-209">IF **PlaceOfResidence &#124; TimeInMonths** > 18</span><span class="sxs-lookup"><span data-stu-id="814cd-209">IF **PlaceOfResidence &#124; TimeInMonths** > 18</span></span><br /><br /> <span data-ttu-id="814cd-210">**ResidencyStatus** = **有効**</span><span class="sxs-lookup"><span data-stu-id="814cd-210">THEN **ResidencyStatus** = **Valid**</span></span>                                  |
   | <span data-ttu-id="814cd-211">!1, !2, !3, !4</span><span class="sxs-lookup"><span data-stu-id="814cd-211">!1, !2, !3, !4</span></span> |     <span data-ttu-id="814cd-212">否定ルール</span><span class="sxs-lookup"><span data-stu-id="814cd-212">Negation Rules</span></span>      |    <span data-ttu-id="814cd-213">論理の条件**いない**のルール 1 ~ 4 で説明されている対応する条件。</span><span class="sxs-lookup"><span data-stu-id="814cd-213">Conditions that are a logical **NOT** of the corresponding condition described in rules 1–4.</span></span> <span data-ttu-id="814cd-214">結果が設定される文字列に変わります。</span><span class="sxs-lookup"><span data-stu-id="814cd-214">Resulting actions are a change in the string that is being set.</span></span>     |


6. <span data-ttu-id="814cd-215">右クリックし、**バージョン 1.1 (未保存)** ノード、およびクリック**保存**します。</span><span class="sxs-lookup"><span data-stu-id="814cd-215">Right-click the **Version 1.1(not saved)** node, and then click **Save**.</span></span>  

7. <span data-ttu-id="814cd-216">右クリックし、**バージョン 1.1**ノード、およびクリック**発行**します。</span><span class="sxs-lookup"><span data-stu-id="814cd-216">Right-click the **Version 1.1** node, and then click **Publish**.</span></span>  

8. <span data-ttu-id="814cd-217">右クリックし、**バージョン 1.1**ノード、およびクリック**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="814cd-217">Right-click the **Version 1.1** node, and then click **Deploy**.</span></span>  

9. <span data-ttu-id="814cd-218">共有の SQL Server ルール ストアに反映されるまで、変更の 60 秒間待機します。</span><span class="sxs-lookup"><span data-stu-id="814cd-218">Wait for 60 seconds for the changes to propagate to the shared SQL Server rule store.</span></span>  

10. <span data-ttu-id="814cd-219">ファイル sampleLoan.xml のコピーをフォルダーに貼り付ける**で**します。</span><span class="sxs-lookup"><span data-stu-id="814cd-219">Paste a copy of the file sampleLoan.xml into the folder **In**.</span></span>  

11. <span data-ttu-id="814cd-220">フォルダーに作成した .xml ファイルを観察**アウト**します。データが XML 構造の末尾に次の 4 つの状態要素に追加の入力 XML メッセージが含まれています。**IncomeStatus**、 **CommitmentsStatus**、 **EmploymentStatus**、および**ResidencyStatus**します。</span><span class="sxs-lookup"><span data-stu-id="814cd-220">Observe the .xml file created in the folder **Out**. It contains the input XML message with data added to the following four status elements at the end of the XML structure: **IncomeStatus**, **CommitmentsStatus**, **EmploymentStatus**, and **ResidencyStatus**.</span></span> <span data-ttu-id="814cd-221">これらの要素に追加されたデータは異なります、またはそうでない、前の手順 5. でこの手順で行われた変更の種類に基づいて、実行します。</span><span class="sxs-lookup"><span data-stu-id="814cd-221">The data added to these elements will differ, or not, from the previous run, based on the nature of the changes made in step 5in this procedure.</span></span>  

## <a name="comments"></a><span data-ttu-id="814cd-222">コメント</span><span class="sxs-lookup"><span data-stu-id="814cd-222">Comments</span></span>  
 <span data-ttu-id="814cd-223">このサンプルの追跡情報を表示する場合は、解除して、ビジネス ルール エンジン展開ウィザードを使用して、関連するルールのセット (Loans Processing) を再デプロイする必要があります。</span><span class="sxs-lookup"><span data-stu-id="814cd-223">If you want to view the tracking information for this sample, you must undeploy and then redeploy the relevant rule set (Loans Processing) by using the Business Rules Engine Deployment Wizard.</span></span>  

 <span data-ttu-id="814cd-224">このサンプルでは、ビジネス ルールを使用して、オーケストレーション内のルールの形式でビジネス ポリシーを適用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="814cd-224">This sample demonstrates how you can use business rules to apply business policies in the form of rules within an orchestration.</span></span> <span data-ttu-id="814cd-225">また、ポリシーを変更し、再コンパイルやオーケストレーション ソリューションを再デプロイしなくても、オーケストレーション内で動的に反映されるポリシーに変更がある方法を示します。</span><span class="sxs-lookup"><span data-stu-id="814cd-225">It also demonstrates how you can change the policies, and have the change in the policy reflected dynamically within the orchestration without having to recompile or redeploy the orchestration solution.</span></span>  

 <span data-ttu-id="814cd-226">このサンプルの入力ローン ケースは、次の構造を持つ XML メッセージです。</span><span class="sxs-lookup"><span data-stu-id="814cd-226">Input loan cases to this sample are XML messages that have the following structure:</span></span>  

```  
    Name  
    ID  
    Income  
        BasicSalary  
        OtherIncome  
    EmploymentType  
        TimeInMonths  
    PlaceOfResidence  
        TimeInMonths  
    CommitmentsStatus  
    IncomeStatus  
    EmploymentStatus  
    ResidencyStatus  
```  

## <a name="see-also"></a><span data-ttu-id="814cd-227">参照</span><span class="sxs-lookup"><span data-stu-id="814cd-227">See Also</span></span>  
 [<span data-ttu-id="814cd-228">ビジネス ルール (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="814cd-228">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)