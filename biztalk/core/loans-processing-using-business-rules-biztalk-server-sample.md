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
ms.openlocfilehash: a1b8b1ae132d095ec70a22b8480818a0b8a11ece
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998531"
---
# <a name="loans-processing-using-business-rules-biztalk-server-sample"></a><span data-ttu-id="a776e-102">Loans Processing Using Business Rules (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="a776e-102">Loans Processing Using Business Rules (BizTalk Server Sample)</span></span>
<span data-ttu-id="a776e-103">Loans Processing Using Business Rules サンプルは、オーケストレーション内で管理しているルール セットを使用する方法、および入力 (ファクトと呼ばれます) の組み合わせを使用して、処理中のドキュメント内のフィールドの設定値を計算する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a776e-103">The Loans Processing Using Business Rules sample demonstrates how to use a set of rules managed within an orchestration, and how to use a combination of inputs known as facts, to calculate settings for some fields within a document being processed.</span></span> <span data-ttu-id="a776e-104">ファクトは、.NET ベースのアセンブリ呼び出しの結果、メッセージの XML から取得した値、またはデータベースから取得したデータです。</span><span class="sxs-lookup"><span data-stu-id="a776e-104">Facts can be the result of calling a .NET-based assembly, the values retrieved from the XML of the message, or the data retrieved from a database.</span></span> <span data-ttu-id="a776e-105">このサンプルでは、ルールを必要に応じて変更して、再展開の必要なしに後続の計算に影響を与える方法も示します。</span><span class="sxs-lookup"><span data-stu-id="a776e-105">The sample also demonstrates how you can change the rules at any time, affecting subsequent calculations without the need to redeploy.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="a776e-106">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="a776e-106">What This Sample Does</span></span>  
 <span data-ttu-id="a776e-107">このサンプルでは、簡単なローン処理のシナリオでこれらの機能を示します。</span><span class="sxs-lookup"><span data-stu-id="a776e-107">This sample demonstrates these capabilities within the context of a simplified loan processing scenario.</span></span> <span data-ttu-id="a776e-108">BizTalk Server オーケストレーションは、XML メッセージ形式のローン申請 (ローン ケースともいう) を取得して処理します。</span><span class="sxs-lookup"><span data-stu-id="a776e-108">BizTalk Server orchestration picks up and processes a loan application, also known as a loan case, in XML message format.</span></span> <span data-ttu-id="a776e-109">このオーケストレーションでは、ビジネス ルール エンジンを使用してルールに従って受信メッセージを評価し、ルール適用の結果を使用してメッセージを変更し、メッセージをファイルとして出力フォルダーに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="a776e-109">This orchestration uses the Business Rule Engine to evaluate incoming messages according to the rules, modifying the message with the result of the application of the rules, and then writing the message as a file to an output folder.</span></span>  

 <span data-ttu-id="a776e-110">このサンプルの設定の処理中のメッセージを含む複数のソースからのファクトに基づいた、 **IncomeStatus**、 **CommitmentsStatus**、 **EmploymentStatus**、および**ResidencyStatus**処理中のメッセージの要素。</span><span class="sxs-lookup"><span data-stu-id="a776e-110">Based on facts from several sources, including the message being processed, this sample sets the **IncomeStatus**, **CommitmentsStatus**, **EmploymentStatus**, and **ResidencyStatus** elements of the message being processed.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="a776e-111">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="a776e-111">Where to Find This Sample</span></span>  
 <span data-ttu-id="a776e-112">\<*パスのサンプル*\>\Business Rules\Loans ビジネス Rules\ を使用した処理</span><span class="sxs-lookup"><span data-stu-id="a776e-112">\<*Samples Path*\>\Business Rules\Loans Processing using Business Rules\\</span></span>  

 <span data-ttu-id="a776e-113">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="a776e-113">The following table shows the files in this sample and describes their purpose.</span></span>  


|                                                                                    <span data-ttu-id="a776e-114">ファイル</span><span class="sxs-lookup"><span data-stu-id="a776e-114">File(s)</span></span>                                                                                    |                                                                                                                <span data-ttu-id="a776e-115">説明</span><span class="sxs-lookup"><span data-stu-id="a776e-115">Description</span></span>                                                                                                                 |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                   <span data-ttu-id="a776e-116">Case.xsd</span><span class="sxs-lookup"><span data-stu-id="a776e-116">Case.xsd</span></span>                                                                                    |                                                                                 <span data-ttu-id="a776e-117">受信ローン申請 (ローン ケース) のスキーマ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="a776e-117">Schema file for inbound loan applications, otherwise known as loan cases.</span></span>                                                                                  |
|                                                                                  <span data-ttu-id="a776e-118">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="a776e-118">Cleanup.bat</span></span>                                                                                  |                   <span data-ttu-id="a776e-119">アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a776e-119">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="a776e-120">送信ポートと受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="a776e-120">Removes send and receive ports.</span></span> <span data-ttu-id="a776e-121">必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="a776e-121">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>                   |
|                                                                           <span data-ttu-id="a776e-122">Create_CustInfo_Table.sql</span><span class="sxs-lookup"><span data-stu-id="a776e-122">Create_CustInfo_Table.sql</span></span>                                                                           |                                                                              <span data-ttu-id="a776e-123">SQL Northwind サンプル データベースの CustInfo テーブルを作成するための SQL スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="a776e-123">SQL script for creating the CustInfo table in the SQL Northwind sample database.</span></span>                                                                              |
|                                                                           <span data-ttu-id="a776e-124">LoanProcessorBinding.xml</span><span class="sxs-lookup"><span data-stu-id="a776e-124">LoanProcessorBinding.xml</span></span>                                                                            |                                                                                               <span data-ttu-id="a776e-125">ポートのバインドなど、自動化されたセットアップに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a776e-125">Used for automated setup such as port binding.</span></span>                                                                                               |
|                                                                   <span data-ttu-id="a776e-126">LoansProcessor.btproj、LoansProcessor.sln</span><span class="sxs-lookup"><span data-stu-id="a776e-126">LoansProcessor.btproj, LoansProcessor.sln</span></span>                                                                   |                                                                                            <span data-ttu-id="a776e-127">このサンプルの BizTalk プロジェクト ファイルとソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="a776e-127">BizTalk project and solution files for this sample.</span></span>                                                                                             |
|                                                                             <span data-ttu-id="a776e-128">My Sample Service.odx</span><span class="sxs-lookup"><span data-stu-id="a776e-128">My Sample Service.odx</span></span>                                                                             |                                                             <span data-ttu-id="a776e-129">このサンプルの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="a776e-129">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration for this sample.</span></span>                                                              |
|                                                                                <span data-ttu-id="a776e-130">sampleLoan.xml</span><span class="sxs-lookup"><span data-stu-id="a776e-130">sampleLoan.xml</span></span>                                                                                 |                                                               <span data-ttu-id="a776e-131">サンプルの入力ファイルです。ファイルの XML 構造の末尾で、4 つの状態要素の値が空になっています。</span><span class="sxs-lookup"><span data-stu-id="a776e-131">Sample input file, with empty values for the four status elements at the end of the XML structure in the file.</span></span>                                                               |
|                                                                                   <span data-ttu-id="a776e-132">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="a776e-132">Setup.bat</span></span>                                                                                   |                                                                                                 <span data-ttu-id="a776e-133">このサンプルをビルドおよび初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a776e-133">Used to build and initialize this sample.</span></span>                                                                                                  |
|         <span data-ttu-id="a776e-134">\CreateRules フォルダーには、次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a776e-134">In the \CreateRules folder:</span></span><br /><br /> <span data-ttu-id="a776e-135">App.ico、AssemblyInfo.cs、Case.xsd、CreateLoanProcessingPolicy.csproj、CreateLoanProcessingPolicy.sln、WriteToBRL.cs</span><span class="sxs-lookup"><span data-stu-id="a776e-135">App.ico, AssemblyInfo.cs, Case.xsd, CreateLoanProcessingPolicy.csproj, CreateLoanProcessingPolicy.sln, WriteToBRL.cs</span></span>          | <span data-ttu-id="a776e-136">プログラムによってセット内にルールを作成するアプリケーションを作成するために使う Visual C# プロジェクト、ソリューション、ソース、および関連ファイルです。</span><span class="sxs-lookup"><span data-stu-id="a776e-136">Visual C# project, solution, source, and related files used to create the application that programmatically creates the rules in the set.</span></span> <span data-ttu-id="a776e-137">プログラムによってルール セットを作成する方法の例については、ソース ファイル WriteToBRL.cs を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a776e-137">For examples of programmatically building sets of rules, refer to the source file WriteToBRL.cs.</span></span> |
| <span data-ttu-id="a776e-138">\myFactRetriever フォルダーには、次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a776e-138">In the \myFactRetriever folder:</span></span><br /><br /> <span data-ttu-id="a776e-139">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="a776e-139">AssemblyInfo.cs</span></span><br /><br /> <span data-ttu-id="a776e-140">FactRetrieverForLoansProcessing.cs</span><span class="sxs-lookup"><span data-stu-id="a776e-140">FactRetrieverForLoansProcessing.cs</span></span><br /><br /> <span data-ttu-id="a776e-141">myFactRetriever.csproj</span><span class="sxs-lookup"><span data-stu-id="a776e-141">myFactRetriever.csproj</span></span><br /><br /> <span data-ttu-id="a776e-142">myFactRetriever.sln</span><span class="sxs-lookup"><span data-stu-id="a776e-142">myFactRetriever.sln</span></span> |                 <span data-ttu-id="a776e-143">SQL Server のサンプルの Northwind データベースにあらかじめ追加された CustInfo テーブルからの情報の取得に使用するアセンブリを作成するために使う Visual C# プロジェクト、ソリューション、ソース、および関連ファイルです。</span><span class="sxs-lookup"><span data-stu-id="a776e-143">Visual C# project, solution, source, and related files used to create an assembly that you use to retrieve information from the CustInfo table added earlier to the Northwind sample SQL Server database.</span></span>                  |

## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="a776e-144">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="a776e-144">Building and Initializing This Sample</span></span>  

#### <a name="to-build-and-initialize-the-loans-processing-using-business-rules-sample"></a><span data-ttu-id="a776e-145">Loans Processing Using Business Rules サンプルをビルドして初期化するには</span><span class="sxs-lookup"><span data-stu-id="a776e-145">To build and initialize the Loans Processing Using Business Rules sample</span></span>  

1. <span data-ttu-id="a776e-146">コンピューターに Northwind データベースがインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a776e-146">Make sure that you have the Northwind database on your machine.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="a776e-147">このサンプルを実行するには、SQL Server の Northwind サンプル データベースが必要です。</span><span class="sxs-lookup"><span data-stu-id="a776e-147">To run this sample, you must have the Northwind SQL Server sample database.</span></span> <span data-ttu-id="a776e-148">[ダウンロード](https://www.microsoft.com/download/details.aspx?id=23654)、およびインストールします。</span><span class="sxs-lookup"><span data-stu-id="a776e-148">[Download](https://www.microsoft.com/download/details.aspx?id=23654), and install.</span></span> 

2. <span data-ttu-id="a776e-149">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="a776e-149">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="a776e-150">\<*パスのサンプル*\>\Business Rules\Loans Processing using Business Rules</span><span class="sxs-lookup"><span data-stu-id="a776e-150">\<*Samples Path*\>\Business Rules\Loans Processing using Business Rules</span></span>  

3. <span data-ttu-id="a776e-151">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="a776e-151">Run the file Setup.bat, which performs the following actions:</span></span>  

   - <span data-ttu-id="a776e-152">GAC をクリーンアップして、このサンプルを前回実行したときに残ったデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="a776e-152">Cleans up the GAC to eliminate any residual data from previous runs of this sample.</span></span>  

   - <span data-ttu-id="a776e-153">ファクト取得プログラム myFactRetreiever.dll をコンパイルし、展開します。</span><span class="sxs-lookup"><span data-stu-id="a776e-153">Compiles and deploys the fact retriever program, myFactRetreiever.dll.</span></span>  

   - <span data-ttu-id="a776e-154">SQL スクリプト ファイル Create_CustInfo_Table.sql を使用して、Northwind サンプル SQL データベースに CustInfo という名前のテーブルを追加します。</span><span class="sxs-lookup"><span data-stu-id="a776e-154">Using the SQL script file Create_CustInfo_Table.sql, adds a table named CustInfo to the Northwind sample SQL database.</span></span>  

   - <span data-ttu-id="a776e-155">共有 SQL ルール ストアをクリーンアップして、このサンプルを前回実行したときに残ったデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="a776e-155">Cleans up the shared SQL rule store to eliminate residue of previous runs of this sample.</span></span>  

   - <span data-ttu-id="a776e-156">ローン処理ルール セットの最新バージョン (1.0) を作成、公開し、展開します。</span><span class="sxs-lookup"><span data-stu-id="a776e-156">Creates, publishes, and deploys the most recent version (1.0) of the loans processing rule set.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="a776e-157">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に用意されているビジネス ルール作成ツールを使用すると、プログラムによって設定されたルールを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a776e-157">You can use the Business Rule Composer tool supplied with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to examine the rules that have been set programmatically.</span></span>  

   - <span data-ttu-id="a776e-158">このサンプルで使用される入力 (In) フォルダーと出力 (Out) フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a776e-158">Creates the input (In) and output (Out) folders for this sample.</span></span>  

   - <span data-ttu-id="a776e-159">このサンプルの残りの [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクト (このサンプルを調整するために使用するオーケストレーションが格納された BizTalk プロジェクトを含む) をコンパイルして展開します。</span><span class="sxs-lookup"><span data-stu-id="a776e-159">Compiles and deploys the remaining [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample, including the BizTalk project that contains the orchestration you use to coordinate this sample.</span></span>  

   - <span data-ttu-id="a776e-160">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。</span><span class="sxs-lookup"><span data-stu-id="a776e-160">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="a776e-161">このサンプルでは、作成してポートをバインドする場合は、次の警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a776e-161">This sample displays the following warnings when creating and binding ports:</span></span>  
     >   
     >  `Warning: Receive handler not specified for receive location "LoansProcessor_1.0.0.0_LoansProcessor.My_Sample_Service_Incoming_ReceiveLocation"; updating with first receive handler with matching transport type.`  
     >   
     >  `Warning: Host not specified for orchestration "LoansProcessor.My_Sample_Service"; updating with first available host.`  
     >   
     >  <span data-ttu-id="a776e-162">これらの警告は、無視してもかまいません </span><span class="sxs-lookup"><span data-stu-id="a776e-162">You can safely ignore these warnings.</span></span> <span data-ttu-id="a776e-163">(インストールでの名前付け方法はユーザーによって異なる可能性があるため、ホスト名と受信ハンドラーはバインド ファイルから除外されています。)</span><span class="sxs-lookup"><span data-stu-id="a776e-163">(To accommodate for possible naming differences in user installations, the host name and receive handler have been omitted from the binding file.)</span></span>  

   - <span data-ttu-id="a776e-164">受信場所を有効にし、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="a776e-164">Enables the receive location, and starts the send port.</span></span>  

   - <span data-ttu-id="a776e-165">オーケストレーションを登録して開始します。</span><span class="sxs-lookup"><span data-stu-id="a776e-165">Enlists and starts the orchestration.</span></span>  

> [!NOTE]
>  <span data-ttu-id="a776e-166">BizTalk ホスト名が BizTalkServerApplication でない場合は、適切なホスト名を反映するように Setup.bat ファイルおよび LoanProcessorBinding.xml ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="a776e-166">If your BizTalk host name is not BizTalkServerApplication, modify the file Setup.bat and the file LoanProcessorBinding.xml to reflect the proper host name.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="a776e-167">このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a776e-167">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="a776e-168">開き、Setup.bat ファイルを実行することがなくこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a776e-168">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="a776e-169">このキー ペアは、生成されたアセンブリの署名に使用します。</span><span class="sxs-lookup"><span data-stu-id="a776e-169">Use this key pair to sign the resulting assemblies.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="a776e-170">Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="a776e-170">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="a776e-171">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="a776e-171">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  

## <a name="running-this-sample"></a><span data-ttu-id="a776e-172">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="a776e-172">Running This Sample</span></span>  

#### <a name="to-run-the-loans-processing-using-business-rules-sample"></a><span data-ttu-id="a776e-173">Loans Processing Using Business Rules サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="a776e-173">To run the Loans Processing Using Business Rules sample</span></span>  

1. <span data-ttu-id="a776e-174">ファイル sampleLoan.xml のコピー、 **\In**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="a776e-174">Paste a copy of the file sampleLoan.xml into the **\In** folder.</span></span>  

2. <span data-ttu-id="a776e-175">フォルダーに作成した .xml ファイルを観察**アウト**します。XML データ構造の末尾に次の 4 つの状態要素に追加されたデータの入力 XML メッセージが含まれています: **IncomeStatus**、 **CommitmentsStatus**、 **EmploymentStatus**、および**ResidencyStatus**します。</span><span class="sxs-lookup"><span data-stu-id="a776e-175">Observe the .xml file created in the folder **Out**. It contains the input XML message with data added to the following four status elements at the end of the XML structure: **IncomeStatus**, **CommitmentsStatus**, **EmploymentStatus**, and **ResidencyStatus**.</span></span>  

   <span data-ttu-id="a776e-176">ビジネス ルール作成ツールを使用してルール セット内のルールを変更し、変更されたルールを再展開できます。</span><span class="sxs-lookup"><span data-stu-id="a776e-176">You can use the Business Rule Composer tool to change the rules in the rule set, and then redeploy those rules.</span></span>  

#### <a name="to-use-the-business-rule-composer-tool-to-change-one-or-more-of-the-rules-in-a-rule-set"></a><span data-ttu-id="a776e-177">ビジネス ルール作成ツールを使用してルール セット内のルールを変更するには</span><span class="sxs-lookup"><span data-stu-id="a776e-177">To use the Business Rule Composer tool to change one or more of the rules in a rule set</span></span>  

1. <span data-ttu-id="a776e-178">クリックして**開始**、 をポイント**プログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="a776e-178">Click **Start**, point to **Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Business Rule Composer**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="a776e-179">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="a776e-179">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="a776e-180">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="a776e-180">To do this, right-click the application, and then select **Run as administrator**.</span></span>  

2. <span data-ttu-id="a776e-181">**SQL Server**ダイアログ ボックスで、をクリックして **[ok]** ルール ストアに接続します。</span><span class="sxs-lookup"><span data-stu-id="a776e-181">In the **SQL Server** dialog box, click **OK** to connect to the rule store.</span></span>  

3. <span data-ttu-id="a776e-182">**ポリシー エクスプ ローラー**、ノードの下**LoanProcessing**を右クリックし、**バージョン 1.0-展開済み**ノード、およびクリック**コピー**します。</span><span class="sxs-lookup"><span data-stu-id="a776e-182">In **Policy Explorer**, below the node **LoanProcessing**, right-click the **Version 1.0 – Deployed** node, and then click **Copy**.</span></span>  

4. <span data-ttu-id="a776e-183">右クリック**LoanProcessing**、 をクリックし、**貼り付け**します。</span><span class="sxs-lookup"><span data-stu-id="a776e-183">Right-click **LoanProcessing**, and then click **Paste**.</span></span>  

5. <span data-ttu-id="a776e-184">ルールまたはさまざまな値の原因となる方法で処理を変更、 **IncomeStatus**、 **CommitmentsStatus**、 **EmploymentStatus**、および**ResidencyStatus**要素。</span><span class="sxs-lookup"><span data-stu-id="a776e-184">Change any rule or action in a way that will result in different values for the **IncomeStatus**, **CommitmentsStatus**, **EmploymentStatus**, and **ResidencyStatus** elements.</span></span> <span data-ttu-id="a776e-185">否定部分の値を変更することを確認します (基本的には、 **Else**句) ルールを変更するのです。</span><span class="sxs-lookup"><span data-stu-id="a776e-185">Ensure that you also change the value of the negation portion (essentially, the **Else** clause) of any rule that you choose to change.</span></span>  

    <span data-ttu-id="a776e-186">次の表に、このサンプルで使用されるルール セットを示します。</span><span class="sxs-lookup"><span data-stu-id="a776e-186">The following table shows the set of rules used by this sample.</span></span> <span data-ttu-id="a776e-187">特に断りのない限り、ファクトは受信 XML メッセージから取得されます。</span><span class="sxs-lookup"><span data-stu-id="a776e-187">Unless specifically mentioned otherwise, facts are from the incoming XML message.</span></span> <span data-ttu-id="a776e-188">文字列 (db) は、ファクトのソースであるデータベースを表します。</span><span class="sxs-lookup"><span data-stu-id="a776e-188">The string (db) indicates a database as the source of a fact.</span></span>  


   |  <span data-ttu-id="a776e-189">ルール番号</span><span class="sxs-lookup"><span data-stu-id="a776e-189">Rule number</span></span>   |        <span data-ttu-id="a776e-190">ルール名</span><span class="sxs-lookup"><span data-stu-id="a776e-190">Rule name</span></span>        |                                                                             <span data-ttu-id="a776e-191">説明</span><span class="sxs-lookup"><span data-stu-id="a776e-191">Description</span></span>                                                                             |
   |----------------|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |       <span data-ttu-id="a776e-192">1</span><span class="sxs-lookup"><span data-stu-id="a776e-192">1</span></span>        |   <span data-ttu-id="a776e-193">収入状態ルール</span><span class="sxs-lookup"><span data-stu-id="a776e-193">Income Status Rule</span></span>    |                                       <span data-ttu-id="a776e-194">IF **BasicSalary** + **OtherIncome** > 0</span><span class="sxs-lookup"><span data-stu-id="a776e-194">IF **BasicSalary** + **OtherIncome** > 0</span></span><br /><br /> <span data-ttu-id="a776e-195">**IncomeStatus** = **有効**</span><span class="sxs-lookup"><span data-stu-id="a776e-195">THEN **IncomeStatus** = **Valid**</span></span>                                        |
   |       <span data-ttu-id="a776e-196">2</span><span class="sxs-lookup"><span data-stu-id="a776e-196">2</span></span>        | <span data-ttu-id="a776e-197">契約状態ルール</span><span class="sxs-lookup"><span data-stu-id="a776e-197">Commitments Status Rule</span></span> | <span data-ttu-id="a776e-198">IF **ID** == **ID (db)**</span><span class="sxs-lookup"><span data-stu-id="a776e-198">IF **ID** == **ID (db)**</span></span><br /><br /> <span data-ttu-id="a776e-199">AND</span><span class="sxs-lookup"><span data-stu-id="a776e-199">AND</span></span><br /><br /> <span data-ttu-id="a776e-200">IF **CreditCardBalance (db)** > 500</span><span class="sxs-lookup"><span data-stu-id="a776e-200">IF **CreditCardBalance (db)** > 500</span></span><br /><br /> <span data-ttu-id="a776e-201">**CommitmentsStatus** =</span><span class="sxs-lookup"><span data-stu-id="a776e-201">THEN **CommitmentsStatus** =</span></span><br /><br /> <span data-ttu-id="a776e-202">"Compute Commitments"</span><span class="sxs-lookup"><span data-stu-id="a776e-202">"Compute Commitments"</span></span> |
   |       <span data-ttu-id="a776e-203">3</span><span class="sxs-lookup"><span data-stu-id="a776e-203">3</span></span>        | <span data-ttu-id="a776e-204">雇用状態ルール</span><span class="sxs-lookup"><span data-stu-id="a776e-204">Employment Status Rule</span></span>  |                                  <span data-ttu-id="a776e-205">IF **EmploymentType &#124; TimeInMonths** > 18</span><span class="sxs-lookup"><span data-stu-id="a776e-205">IF **EmploymentType &#124; TimeInMonths** > 18</span></span><br /><br /> <span data-ttu-id="a776e-206">**EmploymentStatus** = **有効**</span><span class="sxs-lookup"><span data-stu-id="a776e-206">THEN **EmploymentStatus** = **Valid**</span></span>                                   |
   |       <span data-ttu-id="a776e-207">4</span><span class="sxs-lookup"><span data-stu-id="a776e-207">4</span></span>        |  <span data-ttu-id="a776e-208">常駐状態ルール</span><span class="sxs-lookup"><span data-stu-id="a776e-208">Residency Status Rule</span></span>  |                                  <span data-ttu-id="a776e-209">IF **PlaceOfResidence &#124; TimeInMonths** > 18</span><span class="sxs-lookup"><span data-stu-id="a776e-209">IF **PlaceOfResidence &#124; TimeInMonths** > 18</span></span><br /><br /> <span data-ttu-id="a776e-210">**ResidencyStatus** = **有効**</span><span class="sxs-lookup"><span data-stu-id="a776e-210">THEN **ResidencyStatus** = **Valid**</span></span>                                  |
   | <span data-ttu-id="a776e-211">!1, !2, !3, !4</span><span class="sxs-lookup"><span data-stu-id="a776e-211">!1, !2, !3, !4</span></span> |     <span data-ttu-id="a776e-212">否定ルール</span><span class="sxs-lookup"><span data-stu-id="a776e-212">Negation Rules</span></span>      |    <span data-ttu-id="a776e-213">論理の条件**いない**のルール 1 ~ 4 で説明されている対応する条件。</span><span class="sxs-lookup"><span data-stu-id="a776e-213">Conditions that are a logical **NOT** of the corresponding condition described in rules 1–4.</span></span> <span data-ttu-id="a776e-214">結果が設定される文字列に変わります。</span><span class="sxs-lookup"><span data-stu-id="a776e-214">Resulting actions are a change in the string that is being set.</span></span>     |


6. <span data-ttu-id="a776e-215">右クリックし、**バージョン 1.1 (未保存)** ノード、およびクリック**保存**します。</span><span class="sxs-lookup"><span data-stu-id="a776e-215">Right-click the **Version 1.1(not saved)** node, and then click **Save**.</span></span>  

7. <span data-ttu-id="a776e-216">右クリックし、**バージョン 1.1**ノード、およびクリック**発行**します。</span><span class="sxs-lookup"><span data-stu-id="a776e-216">Right-click the **Version 1.1** node, and then click **Publish**.</span></span>  

8. <span data-ttu-id="a776e-217">右クリックし、**バージョン 1.1**ノード、およびクリック**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="a776e-217">Right-click the **Version 1.1** node, and then click **Deploy**.</span></span>  

9. <span data-ttu-id="a776e-218">共有 SQL Server ルール ストアに変更が反映されるまで、60 秒間待機します。</span><span class="sxs-lookup"><span data-stu-id="a776e-218">Wait for 60 seconds for the changes to propagate to the shared SQL Server rule store.</span></span>  

10. <span data-ttu-id="a776e-219">ファイル sampleLoan.xml のコピーをフォルダーに貼り付ける**で**します。</span><span class="sxs-lookup"><span data-stu-id="a776e-219">Paste a copy of the file sampleLoan.xml into the folder **In**.</span></span>  

11. <span data-ttu-id="a776e-220">フォルダーに作成した .xml ファイルを観察**アウト**します。XML データ構造の末尾に次の 4 つの状態要素に追加されたデータの入力 XML メッセージが含まれています: **IncomeStatus**、 **CommitmentsStatus**、 **EmploymentStatus**、および**ResidencyStatus**します。</span><span class="sxs-lookup"><span data-stu-id="a776e-220">Observe the .xml file created in the folder **Out**. It contains the input XML message with data added to the following four status elements at the end of the XML structure: **IncomeStatus**, **CommitmentsStatus**, **EmploymentStatus**, and **ResidencyStatus**.</span></span> <span data-ttu-id="a776e-221">これらの要素に追加されたデータは、手順 5. で行った変更により、前回の実行結果とは異なります。</span><span class="sxs-lookup"><span data-stu-id="a776e-221">The data added to these elements will differ, or not, from the previous run, based on the nature of the changes made in step 5in this procedure.</span></span>  

## <a name="comments"></a><span data-ttu-id="a776e-222">コメント</span><span class="sxs-lookup"><span data-stu-id="a776e-222">Comments</span></span>  
 <span data-ttu-id="a776e-223">このサンプルの追跡情報を確認するには、ビジネス ルール エンジン展開ウィザードを使用して関連するルール セット (Loans Processing) をいったん展開解除し、再展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a776e-223">If you want to view the tracking information for this sample, you must undeploy and then redeploy the relevant rule set (Loans Processing) by using the Business Rules Engine Deployment Wizard.</span></span>  

 <span data-ttu-id="a776e-224">このサンプルでは、ビジネス ルールを使用してオーケストレーション内のルールの形式でビジネス ポリシーを適用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a776e-224">This sample demonstrates how you can use business rules to apply business policies in the form of rules within an orchestration.</span></span> <span data-ttu-id="a776e-225">ポリシーを変更し、このポリシーの変更を、オーケストレーション ソリューションを再コンパイルまたは再展開せずにオーケストレーション内で動的に反映する方法も示しています。</span><span class="sxs-lookup"><span data-stu-id="a776e-225">It also demonstrates how you can change the policies, and have the change in the policy reflected dynamically within the orchestration without having to recompile or redeploy the orchestration solution.</span></span>  

 <span data-ttu-id="a776e-226">このサンプルへの入力ローン ケースは、次の構造の XML メッセージです。</span><span class="sxs-lookup"><span data-stu-id="a776e-226">Input loan cases to this sample are XML messages that have the following structure:</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="a776e-227">参照</span><span class="sxs-lookup"><span data-stu-id="a776e-227">See Also</span></span>  
 [<span data-ttu-id="a776e-228">ビジネス ルール (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="a776e-228">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)