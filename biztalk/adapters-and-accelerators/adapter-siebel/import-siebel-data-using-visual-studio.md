---
title: "Siebel を Visual Studio を使用してデータをインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSIS
- Data Provider for Siebel, importing Siebel data by using Visual Studio
ms.assetid: 33701361-eca2-4795-a5e0-78162a98e9ba
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0671459b39462422768e42e18bf16336a469f43
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="import-siebel-data-using-visual-studio"></a><span data-ttu-id="e4dc2-102">Siebel を Visual Studio を使用してデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-102">Import Siebel Data Using Visual Studio</span></span>
<span data-ttu-id="e4dc2-103">このセクションでは、Microsoft の使用方法に関する情報を提供[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]Siebel システムから SQL Server データベースにデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-103">This section provides information about how to use Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to import data from a Siebel system into a SQL Server database.</span></span> <span data-ttu-id="e4dc2-104">また、作成し、このデータをインポートする SSIS パッケージを実行する方法の手順についても提供します。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-104">It also provides instructions on how to create and execute an SSIS package to import this data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e4dc2-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="e4dc2-105">Prerequisites</span></span>  
 <span data-ttu-id="e4dc2-106">このトピックに記載されている手順を実行する前に確認します。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-106">Before performing the procedures provided in this topic, make sure:</span></span>  
  
-   <span data-ttu-id="e4dc2-107">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]がコンピューターにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-107">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] is installed on the computer.</span></span>  
  
-   <span data-ttu-id="e4dc2-108">Microsoft[!INCLUDE[vs2010](../../includes/vs2010-md.md)]がコンピューターにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-108">Microsoft [!INCLUDE[vs2010](../../includes/vs2010-md.md)] is installed on the computer.</span></span>  
  
## <a name="importing-data-by-using-visual-studio"></a><span data-ttu-id="e4dc2-109">Visual Studio を使用してデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-109">Importing Data by Using Visual Studio</span></span>  
 <span data-ttu-id="e4dc2-110">使用してデータをインポートするのには、次の手順を実行[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]で[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-110">Perform the following steps to import data using [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
#### <a name="to-import-data-by-using-visual-studio"></a><span data-ttu-id="e4dc2-111">Visual Studio を使用してデータをインポートするには</span><span class="sxs-lookup"><span data-stu-id="e4dc2-111">To import data by using Visual Studio</span></span>  
  
1.  <span data-ttu-id="e4dc2-112">開始[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]Integration Service プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-112">Start [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and create an Integration Service project.</span></span>  
  
2.  <span data-ttu-id="e4dc2-113">**プロジェクト**メニューの  **SSIS インポートおよびエクスポート ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-113">From the **Project** menu, select **SSIS Import and Export Wizard**.</span></span> <span data-ttu-id="e4dc2-114">これは、SQL Server インポートおよびエクスポート ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-114">This starts the SQL Server Import and Export Wizard.</span></span>  
  
3.  <span data-ttu-id="e4dc2-115">[ようこそ] 画面で、情報を参照し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-115">Read the information on the Welcome screen, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="e4dc2-116">**データ ソースを選択** ダイアログ ボックスから、**データ ソース**ドロップ ダウン リスト**.NET Framework Data Provider 用 Siebel eBusiness Applications**です。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-116">In the **Choose a Data Source** dialog box, from the **Data Source** drop-down list **.NET Framework Data Provider for Siebel eBusiness Applications**.</span></span> <span data-ttu-id="e4dc2-117">さまざまな接続のプロパティの値を指定、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]接続文字列。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-117">Specify values for the different connection properties for the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] connection string.</span></span> <span data-ttu-id="e4dc2-118">接続文字列プロパティの詳細については、次を参照してください。 [Siebel 接続文字列のデータ プロバイダーのプロパティ](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md)です。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-118">For more information about the connection string properties, see [Data provider properties for the Siebel connection string](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md).</span></span>  
  
     <span data-ttu-id="e4dc2-119">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-119">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="e4dc2-120">**先選択** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-120">In the **Choose a Destination** dialog box:</span></span>  
  
    1.  <span data-ttu-id="e4dc2-121">**先**ドロップダウン リストで、 **SQL Native Client**です。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-121">From the **Destination** drop-down list, select **SQL Native Client**.</span></span>  
  
    2.  <span data-ttu-id="e4dc2-122">**サーバー名**ドロップダウン リストで、SQL Server 名を選択します。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-122">From the **Server name** drop-down list, select a SQL Server name.</span></span>  
  
    3.  <span data-ttu-id="e4dc2-123">認証モードを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-123">Select an authentication mode.</span></span>  
  
    4.  <span data-ttu-id="e4dc2-124">**データベース**ドロップダウン リストで、Siebel テーブルをインポートするデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-124">From the **Database** drop-down list, select the database to which you want to import the Siebel table.</span></span>  
  
    5.  <span data-ttu-id="e4dc2-125">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-125">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="e4dc2-126">**テーブルのコピーを指定またはクエリ** ダイアログ ボックスで、選択、**を転送するデータを指定するクエリを記述**オプション。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-126">In the **Specify Table Copy or Query** dialog box, choose the **Write a query to specify the data to transfer** option.</span></span>  
  
7.  <span data-ttu-id="e4dc2-127">**ソース クエリを指定する** ダイアログ ボックスで、SQL Server にインポートするデータをフィルター選択クエリを指定します。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-127">In the **Provide a Source Query** dialog box, specify a SELECT query to filter the data to be imported into the SQL Server.</span></span> <span data-ttu-id="e4dc2-128">クエリを SELECT の文法の詳細については、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]を参照してください[Siebel の SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)です。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-128">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], see [Syntax for a SELECT Statement in Siebel](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md).</span></span>  
  
8.  <span data-ttu-id="e4dc2-129">クエリを検証するには、をクリックして、**解析**ボタンをクリックし**OK**をクリックしてポップアップ ダイアログ ボックスで、 **[次へ]**です。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-129">To validate the query, click the **Parse** button, click **OK** in the pop-up dialog box, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="e4dc2-130">**[ソース テーブルおよびビュー** ] ダイアログ ボックスで、ソース テーブルと対象テーブルに対してチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-130">In the **Select Source Tables and Views** dialog box, select the check box against the source and destination tables.</span></span> <span data-ttu-id="e4dc2-131">ソースは、Siebel からデータを取得するように指定したクエリを示します。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-131">The source is the query you specified to retrieve data from Siebel.</span></span> <span data-ttu-id="e4dc2-132">変換先は、SQL Server データベースに作成されるテーブルになります。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-132">The destination will be the table that will be created in the SQL Server database.</span></span>  
  
10. <span data-ttu-id="e4dc2-133">ウィザードでは、テーブルのフィールド、ソースと移行先の既定のマッピングを作成します。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-133">The wizard creates a default mapping between the source and destination table fields.</span></span> <span data-ttu-id="e4dc2-134">ただし、要件に従って、マッピングを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-134">However, you can change the mappings according to your requirement.</span></span> <span data-ttu-id="e4dc2-135">フィールド マッピングを変更する をクリックして**マッピングの編集**です。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-135">To change the field mappings, click **Edit Mappings**.</span></span>  
  
11. <span data-ttu-id="e4dc2-136">**列マッピング**ダイアログ ボックスで、することができます。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-136">In the **Column Mappings** dialog box, you can:</span></span>  
  
    -   <span data-ttu-id="e4dc2-137">変換先テーブル内の列の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-137">Change the names of columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="e4dc2-138">変換先テーブル内の特定の列を無視します。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-138">Ignore certain columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="e4dc2-139">コピー先のテーブル内のフィールドのデータ型を変更します。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-139">Change the data type for fields in destination table.</span></span>  
  
    -   <span data-ttu-id="e4dc2-140">Nullable、サイズ、有効桁数、小数点以下桁数などその他のフィールドの属性を変更します。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-140">Change other field attributes such as nullable, size, precision, and scale.</span></span>  
  
    -   <span data-ttu-id="e4dc2-141">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-141">Click **OK**.</span></span>  
  
     <span data-ttu-id="e4dc2-142">![Siebel テーブルと SQL テーブル間の列マッピング](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")</span><span class="sxs-lookup"><span data-stu-id="e4dc2-142">![Column mappings between Siebel and SQL table](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")</span></span>  
  
12. <span data-ttu-id="e4dc2-143">**ソース テーブルおよびビュー**ダイアログ ボックスで、をクリックして**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-143">In the **Select Source Tables and Views** dialog box, click **Next**.</span></span>  
  
13. <span data-ttu-id="e4dc2-144">**ウィザードを完了** ダイアログ ボックスで、ウィザードを実行し、をクリックする操作の概要を確認**完了**です。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-144">In the **Complete the Wizard** dialog box, review the summary of actions that the wizard will perform, and then click **Finish**.</span></span>  
  
14. <span data-ttu-id="e4dc2-145">**操作の実行**Siebel から SQL Server データベース テーブルに情報をインポートするタスクを実行してダイアログ ボックスで、ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-145">In the **Performing Operations** dialog box, the wizard starts executing tasks to import the information from Siebel into a SQL Server database table.</span></span> <span data-ttu-id="e4dc2-146">各タスクの状態は、ウィザードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-146">The status for each task is displayed in the wizard.</span></span>  
  
15. <span data-ttu-id="e4dc2-147">すべてのタスクが正常に実行される、クリックして**閉じる**です。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-147">After all the tasks are successfully executed, click **Close**.</span></span> <span data-ttu-id="e4dc2-148">タスクが失敗した場合、対応するエラー メッセージを参照してください、問題を修正、ウィザードを再実行します。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-148">If a task fails, see the corresponding error message, fix the issue, and rerun the wizard.</span></span>  
  
16. <span data-ttu-id="e4dc2-149">ウィザードでは、統合サービス プロジェクトに、SSIS パッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-149">The wizard adds an SSIS package to your Integration Service project.</span></span> <span data-ttu-id="e4dc2-150">統合サービス プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-150">Save the Integration Service project.</span></span>  
  
## <a name="running-the-ssis-package"></a><span data-ttu-id="e4dc2-151">SSIS パッケージを実行します。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-151">Running the SSIS Package</span></span>  
 <span data-ttu-id="e4dc2-152">統合サービス プロジェクト内で、パッケージが作成されると、Siebel システムから SQL Server データベースにデータをインポートすることを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-152">Once the package is created within an Integration Service project, you can execute it to import data from a Siebel system into a SQL Server database.</span></span> <span data-ttu-id="e4dc2-153">パッケージを実行して Siebel データをインポートするのには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-153">Perform the following steps to import Siebel data by executing the package.</span></span>  
  
#### <a name="to-run-the-package-from-visual-studio"></a><span data-ttu-id="e4dc2-154">Visual Studio からパッケージを実行するには</span><span class="sxs-lookup"><span data-stu-id="e4dc2-154">To run the package from Visual Studio</span></span>  
  
1.  <span data-ttu-id="e4dc2-155">ソリューション エクスプ ローラーで SSIS パッケージに移動します。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-155">Navigate to the SSIS package in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="e4dc2-156">パッケージ名を右クリックし、**パッケージ実行**です。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-156">Right-click the package name, and then select **Execute Package**.</span></span>  
  
 <span data-ttu-id="e4dc2-157">パッケージの実行に関する詳細についてでパッケージの実行」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972)です。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-157">For more information about running packages, see "Running Packages" at [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972).</span></span> <span data-ttu-id="e4dc2-158">いずれかの SSIS パッケージに関連するその他の情報を参照してください"パッケージ操作方法に関するトピック (SSIS)"で[http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973)です。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-158">For any other information related to SSIS packages, see "Package How-to Topics (SSIS)" at [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973).</span></span>  
  
## <a name="verifying-the-results"></a><span data-ttu-id="e4dc2-159">結果の確認</span><span class="sxs-lookup"><span data-stu-id="e4dc2-159">Verifying the Results</span></span>  
 <span data-ttu-id="e4dc2-160">パッケージを実行すると、SQL Server にログオンし、Siebel データのインポート先となるデータベースに移動することによって結果を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-160">After executing the package, you must verify the results by logging on to the SQL Server and navigating to the database to which the Siebel data is imported.</span></span> <span data-ttu-id="e4dc2-161">パッケージを実行する必要がありますテーブルを作成したコピー先データベースにします。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-161">Executing the package should have created a table in the destination database.</span></span> <span data-ttu-id="e4dc2-162">このテーブルは、Siebel テーブルからの値に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-162">This table should be populated with the values from the Siebel table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4dc2-163">参照</span><span class="sxs-lookup"><span data-stu-id="e4dc2-163">See Also</span></span>  
 [<span data-ttu-id="e4dc2-164">Siebel と SSIS のデータ プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4dc2-164">Use the Data Provider for Siebel with SSIS</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-data-provider-for-siebel-with-ssis.md)