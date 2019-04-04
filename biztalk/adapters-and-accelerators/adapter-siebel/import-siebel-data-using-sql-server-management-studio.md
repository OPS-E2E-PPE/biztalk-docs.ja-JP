---
title: SQL Server Management Studio を使用して Siebel データのインポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQL Server Management Studio, importing data by using
- how to, import data by using SQL Server Management Studio
ms.assetid: 67da7f7b-37ea-4a31-89ef-a9f6974ff976
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdcc6140bb50ebca299cd58f78063be8f108dea4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013179"
---
# <a name="import-siebel-data-using-sql-server-management-studio"></a><span data-ttu-id="ac887-102">SQL Server Management Studio を使用して Siebel データをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ac887-102">Import Siebel Data Using SQL Server Management Studio</span></span>
<span data-ttu-id="ac887-103">このセクションでは、SQL Server Management Studio を使用して Siebel システムから SQL Server データベースにデータをインポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ac887-103">This section provides information about how to use SQL Server Management Studio to import data from a Siebel system into a SQL Server database.</span></span> <span data-ttu-id="ac887-104">また、作成し、このデータをインポートする SSIS パッケージを実行する方法の手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="ac887-104">It also provides instructions on how to create and execute an SSIS package to import this data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ac887-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="ac887-105">Prerequisites</span></span>  
 <span data-ttu-id="ac887-106">このトピックで説明する手順を実行する前に確認します。</span><span class="sxs-lookup"><span data-stu-id="ac887-106">Before performing the procedures provided in this topic, make sure:</span></span>  
  
- <span data-ttu-id="ac887-107">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]コンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ac887-107">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] is installed on the computer.</span></span>  
  
- <span data-ttu-id="ac887-108">SQL Server Business Intelligence Development Studio は、コンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ac887-108">SQL Server Business Intelligence Development Studio is installed on the computer.</span></span>  
  
## <a name="importing-data-by-using-sql-server-management-studio"></a><span data-ttu-id="ac887-109">SQL Server Management Studio を使用してデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ac887-109">Importing Data by Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="ac887-110">使用して Siebel システムからデータをインポートする次の手順に従います[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]SQL Server Management Studio を使用します。</span><span class="sxs-lookup"><span data-stu-id="ac887-110">Perform the following steps to import data from Siebel system using [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] with SQL Server Management Studio.</span></span>  
  
#### <a name="to-import-data-by-using-sql-server-management-studio"></a><span data-ttu-id="ac887-111">SQL Server Management Studio を使用してデータをインポートするには</span><span class="sxs-lookup"><span data-stu-id="ac887-111">To import data by using SQL Server Management Studio</span></span>  
  
1. <span data-ttu-id="ac887-112">SQL Server Management Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="ac887-112">Start the SQL Server Management Studio.</span></span>  
  
2. <span data-ttu-id="ac887-113">**サーバーへの接続** ダイアログ ボックスで、SQL Server データベースに接続し、をクリックし、値を指定します。 **Connect**します。</span><span class="sxs-lookup"><span data-stu-id="ac887-113">In the **Connect to Server** dialog box, specify the values to connect to a SQL Server database, and then click **Connect**.</span></span> <span data-ttu-id="ac887-114">Microsoft SQL Server Management Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="ac887-114">Microsoft SQL Server Management Studio opens.</span></span>  
  
3. <span data-ttu-id="ac887-115">オブジェクト エクスプ ローラーで、SQL Server 名を展開し、**データベース**をエクスポートするテーブル、Siebel システムからデータベースを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="ac887-115">In Object Explorer, expand the SQL Server name, expand **Databases**, and right-click the database into which you will be exporting the tables from the Siebel system.</span></span> <span data-ttu-id="ac887-116">コンテキスト メニューをポイント**タスク**、 をクリックし、**データのインポート**します。</span><span class="sxs-lookup"><span data-stu-id="ac887-116">From the context menu, point to **Tasks**, and then click **Import Data**.</span></span> <span data-ttu-id="ac887-117">これは、SQL Server インポートおよびエクスポート ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="ac887-117">This starts the SQL Server Import and Export Wizard.</span></span>  
  
4. <span data-ttu-id="ac887-118">クリックして、ようこそ画面の情報を読み取る**次**します。</span><span class="sxs-lookup"><span data-stu-id="ac887-118">Read the information on the Welcome screen, and then click **Next**.</span></span>  
  
5. <span data-ttu-id="ac887-119">**データ ソースの選択** ダイアログ ボックスから、**データ ソース**ドロップダウン リストで、 **Siebel eBusiness Applications の .NET Framework Data Provider**します。</span><span class="sxs-lookup"><span data-stu-id="ac887-119">In the **Choose a Data Source** dialog box, from the **Data Source** drop-down list, select **.NET Framework Data Provider for Siebel eBusiness Applications**.</span></span> <span data-ttu-id="ac887-120">さまざまな接続のプロパティの値を指定、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]接続文字列。</span><span class="sxs-lookup"><span data-stu-id="ac887-120">Specify values for the different connection properties for the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] connection string.</span></span> <span data-ttu-id="ac887-121">接続文字列プロパティの詳細については、[Siebel 接続文字列のデータ プロバイダー プロパティ](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac887-121">For more information about the connection string properties, see [Data provider properties for the Siebel connection string](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md).</span></span>  
  
    <span data-ttu-id="ac887-122">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac887-122">Click **Next**.</span></span>  
  
6. <span data-ttu-id="ac887-123">**変換先の選択** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="ac887-123">In the **Choose a Destination** dialog box:</span></span>  
  
   1.  <span data-ttu-id="ac887-124">**先**ドロップダウン リストで、 **SQL Native Client**します。</span><span class="sxs-lookup"><span data-stu-id="ac887-124">From the **Destination** drop-down list, select **SQL Native Client**.</span></span>  
  
   2.  <span data-ttu-id="ac887-125">**サーバー名**ドロップダウン リストで、SQL Server 名を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac887-125">From the **Server name** drop-down list, select a SQL Server name.</span></span>  
  
   3.  <span data-ttu-id="ac887-126">認証モードを選択します。</span><span class="sxs-lookup"><span data-stu-id="ac887-126">Select an authentication mode.</span></span>  
  
   4.  <span data-ttu-id="ac887-127">**データベース**ドロップダウン リストで、Siebel テーブルをインポートするデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="ac887-127">From the **Database** drop-down list, select the database to which you want to import the Siebel table.</span></span>  
  
   5.  <span data-ttu-id="ac887-128">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac887-128">Click **Next**.</span></span>  
  
7. <span data-ttu-id="ac887-129">**指定のテーブルのコピーまたはクエリ** ダイアログ ボックスで、選択、**を転送するデータを指定するクエリを記述**オプション。</span><span class="sxs-lookup"><span data-stu-id="ac887-129">In the **Specify Table Copy or Query** dialog box, choose the **Write a query to specify the data to transfer** option.</span></span>  
  
8. <span data-ttu-id="ac887-130">**ソース クエリの指定** ダイアログ ボックスで、SQL Server にインポートするデータをフィルター選択クエリを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac887-130">In the **Provide a Source Query** dialog box, specify a SELECT query to filter the data to be imported into the SQL Server.</span></span> <span data-ttu-id="ac887-131">クエリの SELECT、文法の詳細については、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]を参照してください[Siebel の SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)します。</span><span class="sxs-lookup"><span data-stu-id="ac887-131">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], see [Syntax for a SELECT Statement in Siebel](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md).</span></span>  
  
    <span data-ttu-id="ac887-132">をクリックして、**解析**クエリを検証します をクリックするボタン**OK**でクリックしてポップアップ ダイアログ ボックスで、 **次へ**。</span><span class="sxs-lookup"><span data-stu-id="ac887-132">Click the **Parse** button to validate the query, click **OK** in the pop-up dialog box, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="ac887-133">**選択元のテーブルおよびビュー**  ダイアログ ボックスで、ソースと変換先のテーブルに対してチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ac887-133">In the **Select Source Tables and Views** dialog box, select the check box against the source and destination tables.</span></span> <span data-ttu-id="ac887-134">ソースは、Siebel からデータを取得する指定したクエリです。</span><span class="sxs-lookup"><span data-stu-id="ac887-134">The source is the query you specified to retrieve data from Siebel.</span></span> <span data-ttu-id="ac887-135">変換先は、SQL Server データベースに作成されるテーブルです。</span><span class="sxs-lookup"><span data-stu-id="ac887-135">The destination is the table that will be created in the SQL Server database.</span></span>  
  
10. <span data-ttu-id="ac887-136">ウィザードは、ソースと宛先の間の既定のマッピング テーブルのフィールドを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac887-136">The wizard creates a default mapping between the source and destination table fields.</span></span> <span data-ttu-id="ac887-137">ただし、要件に従って、マッピングを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="ac887-137">However, you can change the mappings according to your requirement.</span></span> <span data-ttu-id="ac887-138">フィールド マッピングを変更するには、クリックして**マッピングの編集**します。</span><span class="sxs-lookup"><span data-stu-id="ac887-138">To change the field mappings, click **Edit Mappings**.</span></span>  
  
     <span data-ttu-id="ac887-139">![Siebel および SQL テーブル間の列マッピング](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")</span><span class="sxs-lookup"><span data-stu-id="ac887-139">![Column mappings between Siebel and SQL table](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")</span></span>  
  
11. <span data-ttu-id="ac887-140">**列マッピング** ダイアログ ボックスができます。</span><span class="sxs-lookup"><span data-stu-id="ac887-140">In the **Column Mappings** dialog box, you can:</span></span>  
  
    -   <span data-ttu-id="ac887-141">変換先テーブル内の列の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="ac887-141">Change the names of columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="ac887-142">変換先テーブルで特定の列を無視します。</span><span class="sxs-lookup"><span data-stu-id="ac887-142">Ignore certain columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="ac887-143">変換先テーブル内のフィールドのデータ型を変更します。</span><span class="sxs-lookup"><span data-stu-id="ac887-143">Change the data type for fields in destination table.</span></span>  
  
    -   <span data-ttu-id="ac887-144">Null 許容型のサイズ、有効桁数、およびスケールなどの他のフィールドの属性を変更します。</span><span class="sxs-lookup"><span data-stu-id="ac887-144">Change other field attributes such as nullable, size, precision, and scale.</span></span>  
  
         <span data-ttu-id="ac887-145">終了したら **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac887-145">When you are finished, click **OK**.</span></span>  
  
12. <span data-ttu-id="ac887-146">**選択元のテーブルおよびビュー**ダイアログ ボックスで、をクリックして**次**。</span><span class="sxs-lookup"><span data-stu-id="ac887-146">In the **Select Source Tables and Views** dialog box, click **Next**.</span></span>  
  
13. <span data-ttu-id="ac887-147">**実行パッケージの保存および** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="ac887-147">In the **Save and Execute Package** dialog box:</span></span>  
  
    - <span data-ttu-id="ac887-148">選択、**をすぐに実行**クエリを実行する チェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="ac887-148">Select the **Execute immediately** check box to execute the query.</span></span>  
  
    - <span data-ttu-id="ac887-149">選択、 **SSIS パッケージの保存**パッケージとしてクエリが保存され、後で実行する チェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="ac887-149">Select the **Save SSIS Package** check box to save the query as a package and execute it later.</span></span> <span data-ttu-id="ac887-150">パッケージを保存する場合は、SQL Server またはファイル システムにパッケージを保存するかどうかも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac887-150">If you chose to save the package, you must also specify whether you want to save the package in the SQL Server or the file system.</span></span>  
  
    - <span data-ttu-id="ac887-151">**パッケージの保護レベル**ドロップダウン リスト、選択、保護、パッケージのレベルし、資格情報を指定が必要です。</span><span class="sxs-lookup"><span data-stu-id="ac887-151">From the **Package protection level** drop-down list, select a protection level for the package and specify credentials where required.</span></span>  
  
    - <span data-ttu-id="ac887-152">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac887-152">Click **Next**.</span></span>  
  
      <span data-ttu-id="ac887-153">パッケージを保存することを選択した場合は、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="ac887-153">If you chose to save the package, proceed to the next step.</span></span> <span data-ttu-id="ac887-154">それ以外の場合、手順 15 に進みます。</span><span class="sxs-lookup"><span data-stu-id="ac887-154">Otherwise, skip to step 15.</span></span>  
  
14. <span data-ttu-id="ac887-155">**SSIS パッケージの保存** ダイアログ ボックスで、次を指定します。</span><span class="sxs-lookup"><span data-stu-id="ac887-155">In the **Save SSIS Package** dialog box, specify the following:</span></span>  
  
    -   <span data-ttu-id="ac887-156">パッケージの名前</span><span class="sxs-lookup"><span data-stu-id="ac887-156">The name for the package</span></span>  
  
    -   <span data-ttu-id="ac887-157">パッケージの説明</span><span class="sxs-lookup"><span data-stu-id="ac887-157">The description for the package</span></span>  
  
    -   <span data-ttu-id="ac887-158">SQL Server にパッケージを保存する場合は、選択から SQL Server、**サーバー名**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="ac887-158">If you chose to save the package to a SQL Server, select a SQL Server from the **Server name** drop-down list.</span></span>  
  
    -   <span data-ttu-id="ac887-159">ファイル システムにパッケージを保存する場合は、指定のファイルの場所と名前、**ファイル名**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="ac887-159">If you chose to save the package to the file system, specify the name and location of the file in the **File name** text box.</span></span>  
  
         <span data-ttu-id="ac887-160">終了したら **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac887-160">When you are finished, click **Next**.</span></span>  
  
15. <span data-ttu-id="ac887-161">**ウィザードを完了**] ダイアログ ボックスで、ウィザードを実行し、[アクションの概要を確認**完了**します。</span><span class="sxs-lookup"><span data-stu-id="ac887-161">In the **Complete the Wizard** dialog box, review the summary of actions that the wizard will perform, and then click **Finish**.</span></span>  
  
16. <span data-ttu-id="ac887-162">**操作の実行**Siebel から SQL Server データベースのテーブルに情報をインポートするタスクの実行 ダイアログ ボックスで、ウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="ac887-162">In the **Performing Operations** dialog box, the wizard starts executing tasks to import the information from Siebel into a SQL Server database table.</span></span> <span data-ttu-id="ac887-163">ウィザードでは、各タスクの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac887-163">The status for each task is displayed in the wizard.</span></span>  
  
17. <span data-ttu-id="ac887-164">すべてのタスクが正常に実行される、クリックして**閉じる**します。</span><span class="sxs-lookup"><span data-stu-id="ac887-164">After all the tasks are successfully executed, click **Close**.</span></span> <span data-ttu-id="ac887-165">タスクが失敗した場合、対応するエラー メッセージが表示、問題を解決し、ウィザードを再実行します。</span><span class="sxs-lookup"><span data-stu-id="ac887-165">If a task fails, see the corresponding error message, fix the issue, and rerun the wizard.</span></span>  
  
## <a name="running-the-ssis-package"></a><span data-ttu-id="ac887-166">SSIS パッケージを実行します。</span><span class="sxs-lookup"><span data-stu-id="ac887-166">Running the SSIS Package</span></span>  
 <span data-ttu-id="ac887-167">SSIS パッケージを保存する場合は、Siebel システムの最新の情報を取得することを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ac887-167">If you chose to save the SSIS package, you can run it to retrieve the most recent information from the Siebel system.</span></span> <span data-ttu-id="ac887-168">このセクションでは、ファイル システムに保存した場合は、パッケージを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ac887-168">This section provides information about how to run the package if you chose to save it to the file system.</span></span>  
  
#### <a name="to-run-the-package-from-windows-explorer"></a><span data-ttu-id="ac887-169">Windows エクスプ ローラーからパッケージを実行するには</span><span class="sxs-lookup"><span data-stu-id="ac887-169">To run the package from Windows Explorer</span></span>  
  
1. <span data-ttu-id="ac887-170">**Windows エクスプ ローラー**パッケージを保存した場所に移動して、パッケージをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac887-170">From **Windows Explorer**, navigate to the location where you saved the package, and double-click the package.</span></span>  
  
2. <span data-ttu-id="ac887-171">**[パッケージ実行ユーティリティ]** ダイアログ ボックスで **[実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac887-171">In the **Execute Package Utility** dialog box, click **Execute**.</span></span> <span data-ttu-id="ac887-172">**パッケージ実行の進行状況** ダイアログ ボックスには、さまざまなタスクの進行状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac887-172">The **Package Execution Progress** dialog box displays the progress of the different tasks.</span></span>  
  
3. <span data-ttu-id="ac887-173">すべてのタスクが正常に実行される、クリックして**閉じる**します。</span><span class="sxs-lookup"><span data-stu-id="ac887-173">After all the tasks are successfully executed, click **Close**.</span></span>  
  
4. <span data-ttu-id="ac887-174">**[パッケージ実行ユーティリティ]** ダイアログ ボックスで **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac887-174">In the **Execute Package Utility** dialog box, click **Close**.</span></span>  
  
   <span data-ttu-id="ac887-175">パッケージの実行に関する詳細については、パッケージの実行」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972)します。</span><span class="sxs-lookup"><span data-stu-id="ac887-175">For more information about running packages, see "Running Packages" at [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972).</span></span> <span data-ttu-id="ac887-176">いずれか、SSIS パッケージに関連するその他の情報を参照してください"パッケージ方法に関するトピック (SSIS)"で[ http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973)します。</span><span class="sxs-lookup"><span data-stu-id="ac887-176">For any other information related to SSIS packages, see "Package How-to Topics (SSIS)" at [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973).</span></span>  
  
## <a name="verifying-the-results"></a><span data-ttu-id="ac887-177">結果の確認</span><span class="sxs-lookup"><span data-stu-id="ac887-177">Verifying the Results</span></span>  
 <span data-ttu-id="ac887-178">パッケージを実行した後は、Siebel データをインポートする SQL Server データベースに移動して結果を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac887-178">After executing the package, you must verify the results by going to the SQL Server database to which the Siebel data is imported.</span></span> <span data-ttu-id="ac887-179">パッケージを実行する必要がありますのテーブルを作成、転送先データベース。</span><span class="sxs-lookup"><span data-stu-id="ac887-179">Executing the package should have created a table in the destination database.</span></span> <span data-ttu-id="ac887-180">このテーブル Siebel テーブルから値を持つデータを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac887-180">This table should be populated with the values from the Siebel table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac887-181">参照</span><span class="sxs-lookup"><span data-stu-id="ac887-181">See Also</span></span>  
 [<span data-ttu-id="ac887-182">Data Provider for Siebel を SSIS と一緒に使用する</span><span class="sxs-lookup"><span data-stu-id="ac887-182">Use the Data Provider for Siebel with SSIS</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-data-provider-for-siebel-with-ssis.md)