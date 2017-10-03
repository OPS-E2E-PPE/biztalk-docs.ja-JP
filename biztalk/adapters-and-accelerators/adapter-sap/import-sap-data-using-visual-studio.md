---
title: "Visual Studio を使用して SAP データのインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing SAP data, how to
- importing SAP data, using Visual Studio
- Visual Studio, importing SAP data
ms.assetid: 70cce089-232d-4ab9-81bd-6b0d6f0097d7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1295f763815872bacedf2262f7c022d6813bd75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="import-sap-data-using-visual-studio"></a><span data-ttu-id="9e81f-102">Visual Studio を使用して SAP データのインポート</span><span class="sxs-lookup"><span data-stu-id="9e81f-102">Import SAP Data Using Visual Studio</span></span>
<span data-ttu-id="9e81f-103">このセクションでは、Microsoft を使用する方法の情報を提供[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]SAP システムから SQL Server データベースにデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="9e81f-103">This section provides information on how to use Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to import data from an SAP system into a SQL Server database.</span></span> <span data-ttu-id="9e81f-104">このセクションでは、データをインポートする実行可能な SSIS パッケージを作成する方法の命令を提供します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-104">This section provides instruction on how to create an SSIS package that you can execute to import data.</span></span> <span data-ttu-id="9e81f-105">このセクションでは、SSIS パッケージを実行する方法についても情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-105">This section also provides information on how to execute the SSIS package.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9e81f-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="9e81f-106">Prerequisites</span></span>  
 <span data-ttu-id="9e81f-107">このトピックに記載されている手順を実行する前に確認します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-107">Before performing the procedures provided in this topic, make sure:</span></span>  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]<span data-ttu-id="9e81f-108">コンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9e81f-108"> is installed on the computer.</span></span>  
  
-   [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]<span data-ttu-id="9e81f-109">コンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9e81f-109"> is installed on the computer.</span></span>  
  
### <a name="to-import-data-using-visual-studio"></a><span data-ttu-id="9e81f-110">Visual Studio を使用してデータをインポートするには</span><span class="sxs-lookup"><span data-stu-id="9e81f-110">To import data using Visual Studio</span></span>  
  
1.  <span data-ttu-id="9e81f-111">開始[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]Integration Service プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-111">Start [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and create an Integration Service project.</span></span>  
  
2.  <span data-ttu-id="9e81f-112">**プロジェクト**メニューの  **SSIS インポートおよびエクスポート ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="9e81f-112">From the **Project** menu, select **SSIS Import and Export Wizard**.</span></span> <span data-ttu-id="9e81f-113">起動、 **SQL Server インポートおよびエクスポート ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="9e81f-113">This starts the **SQL Server Import and Export Wizard**.</span></span>  
  
3.  <span data-ttu-id="9e81f-114">クリックして [ようこそ] 画面の情報を読み取る**次**です。</span><span class="sxs-lookup"><span data-stu-id="9e81f-114">Read the information on the welcome screen and click **Next**.</span></span>  
  
4.  <span data-ttu-id="9e81f-115">**データ ソースを選択** ダイアログ ボックスから、**データ ソース**ドロップ ダウン リスト**.NET Framework Data Provider 用 mySAP Business Suite**です。</span><span class="sxs-lookup"><span data-stu-id="9e81f-115">In the **Choose a Data Source** dialog box, from the **Data Source** drop-down list **.NET Framework Data Provider for mySAP Business Suite**.</span></span> <span data-ttu-id="9e81f-116">ダイアログ ボックスは、SAP システムへの接続に別の接続パラメーターを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-116">The dialog box lists the different connection parameters to connect to an SAP system.</span></span> <span data-ttu-id="9e81f-117">使用して SAP システムへの接続に一般的な接続文字列、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]が必要です。</span><span class="sxs-lookup"><span data-stu-id="9e81f-117">A typical connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requires:</span></span>  
  
    -   <span data-ttu-id="9e81f-118">接続の接続パラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-118">The connection parameters for a connection type.</span></span> <span data-ttu-id="9e81f-119">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] A、B、および D の接続の種類をサポートしていますSAP システムへの接続には、いずれかの接続パラメーターを指定する必要があります*1*種類の接続をします。</span><span class="sxs-lookup"><span data-stu-id="9e81f-119">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports connection types A, B, and D. To connect to an SAP system you must provide connection parameters for any *one* of these connection types.</span></span> <span data-ttu-id="9e81f-120">たとえば、接続の種類、システム数と、アプリケーション サーバーのホストの名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e81f-120">For example, for connection type A, you must provide the name of the application server host and the system number.</span></span>  
  
    -   <span data-ttu-id="9e81f-121">ユーザー名やパスワードなど、SAP システムへの接続にログイン情報。</span><span class="sxs-lookup"><span data-stu-id="9e81f-121">The login information to connect to an SAP system such as username and password.</span></span>  
  
     <span data-ttu-id="9e81f-122">使用して SAP システムへの接続への接続文字列の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP 接続文字列のデータ プロバイダーの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)です。</span><span class="sxs-lookup"><span data-stu-id="9e81f-122">For more information about the connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Read about Data Provider for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
     <span data-ttu-id="9e81f-123">**データ ソースを選択** ダイアログ ボックスで指定します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-123">In the **Choose a Data Source** dialog box, specify:</span></span>  
  
    -   <span data-ttu-id="9e81f-124">任意の 1 つの接続の接続パラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-124">The connection parameters for any one connection type.</span></span>  
  
    -   <span data-ttu-id="9e81f-125">SAP システムへの接続にログイン情報。</span><span class="sxs-lookup"><span data-stu-id="9e81f-125">The login information to connect to an SAP system.</span></span>  
  
    -   <span data-ttu-id="9e81f-126">SAP GUI のデバッグを有効にするかどうか。</span><span class="sxs-lookup"><span data-stu-id="9e81f-126">Whether you want to enable SAP GUI debugging.</span></span>  
  
    -   <span data-ttu-id="9e81f-127">RFC SDK トレースを使用するかどうか。</span><span class="sxs-lookup"><span data-stu-id="9e81f-127">Whether you want to use RFC SDK tracing.</span></span>  
  
     <span data-ttu-id="9e81f-128">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e81f-128">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="9e81f-129">**先選択** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="9e81f-129">In the **Choose a Destination** dialog box:</span></span>  
  
    1.  <span data-ttu-id="9e81f-130">**先**ドロップダウン リストで、 **SQL Native Client**です。</span><span class="sxs-lookup"><span data-stu-id="9e81f-130">From the **Destination** drop-down list, select **SQL Native Client**.</span></span>  
  
    2.  <span data-ttu-id="9e81f-131">**サーバー名**ドロップダウン リストで、SQL server 名を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-131">From the **Server name** drop-down list, select a SQL server name.</span></span>  
  
    3.  <span data-ttu-id="9e81f-132">認証モードを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-132">Select an authentication mode.</span></span>  
  
    4.  <span data-ttu-id="9e81f-133">**データベース**ドロップダウン リストで、SAP テーブルをインポートするデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-133">From the **Database** drop-down list, select the database to which you want to import the SAP table.</span></span>  
  
    5.  <span data-ttu-id="9e81f-134">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e81f-134">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="9e81f-135">**テーブルのコピーを指定またはクエリ** ダイアログ ボックスで、選択、**を転送するデータを指定するクエリを記述**オプションし、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="9e81f-135">In the **Specify Table Copy or Query** dialog box, choose the **Write a query to specify the data to transfer** option and click **Next**.</span></span>  
  
7.  <span data-ttu-id="9e81f-136">**ソース クエリを指定する** ダイアログ ボックスで、SQL Server にインポートするデータをフィルター選択クエリを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-136">In the **Provide a Source Query** dialog box, specify a SELECT query to filter the data to be imported into the SQL Server.</span></span> <span data-ttu-id="9e81f-137">クエリを SELECT の文法の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP の SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="9e81f-137">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Syntax for a SELECT Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).</span></span>  
  
     <span data-ttu-id="9e81f-138">をクリックして、**解析**クエリを検証し、をクリックするボタン**[ok]**ポップアップ ダイアログ ボックスにします。</span><span class="sxs-lookup"><span data-stu-id="9e81f-138">Click the **Parse** button to validate the query and click **OK** in the pop-up dialog box.</span></span> <span data-ttu-id="9e81f-139">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e81f-139">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="9e81f-140">**[ソース テーブルおよびビュー** ] ダイアログ ボックスで、ソース テーブルと対象テーブルに対してチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="9e81f-140">In the **Select Source Tables and Views** dialog box, select the check box against the source and destination tables.</span></span> <span data-ttu-id="9e81f-141">ソースは、SAP からデータを取得するように指定したクエリを示します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-141">The source is the query you specified to retrieve data from SAP.</span></span> <span data-ttu-id="9e81f-142">変換先は、SQL Server データベースに作成されるテーブルです。</span><span class="sxs-lookup"><span data-stu-id="9e81f-142">The destination is the table that will be created in the SQL Server database.</span></span>  
  
9. <span data-ttu-id="9e81f-143">ウィザードでは、テーブルのフィールド、ソースと移行先の既定のマッピングを作成します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-143">The wizard creates a default mapping between the source and destination table fields.</span></span> <span data-ttu-id="9e81f-144">ただし、要件に従って、マッピングを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="9e81f-144">However, you can change the mappings according to your requirement.</span></span> <span data-ttu-id="9e81f-145">フィールド マッピングを変更する をクリックして**マッピングの編集**です。</span><span class="sxs-lookup"><span data-stu-id="9e81f-145">To change the field mappings, click **Edit Mappings**.</span></span>  
  
     <span data-ttu-id="9e81f-146">![SAP テーブルと SQL テーブル間の列マッピング](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")</span><span class="sxs-lookup"><span data-stu-id="9e81f-146">![Column mappings between SAP and SQL tables](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")</span></span>  
  
10. <span data-ttu-id="9e81f-147">**列マッピング**ダイアログ ボックスで、することができます。</span><span class="sxs-lookup"><span data-stu-id="9e81f-147">In the **Column Mappings** dialog box, you can:</span></span>  
  
    -   <span data-ttu-id="9e81f-148">変換先テーブル内の列の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-148">Change the names of columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="9e81f-149">変換先テーブル内の特定の列を無視します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-149">Ignore certain columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="9e81f-150">コピー先のテーブル内のフィールドのデータ型を変更します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-150">Change the data type for fields in destination table.</span></span>  
  
    -   <span data-ttu-id="9e81f-151">Nullable、サイズ、有効桁数、小数点以下桁数などその他のフィールドの属性を変更します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-151">Change other field attributes such as nullable, size, precision, and scale.</span></span>  
  
    -   <span data-ttu-id="9e81f-152">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e81f-152">Click **OK**.</span></span>  
  
11. <span data-ttu-id="9e81f-153">**ソース テーブルおよびビュー**ダイアログ ボックスで、をクリックして**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="9e81f-153">In the **Select Source Tables and Views** dialog box, click **Next**.</span></span>  
  
12. <span data-ttu-id="9e81f-154">**ウィザードを完了** ダイアログ ボックスで、ウィザードを実行し、をクリックする操作の概要を確認**完了**です。</span><span class="sxs-lookup"><span data-stu-id="9e81f-154">In the **Complete the Wizard** dialog box, review the summary of actions that the wizard will perform, and click **Finish**.</span></span>  
  
13. <span data-ttu-id="9e81f-155">**を実行する操作**SAP から情報を SQL Server データベース テーブルにインポートするタスクを実行してダイアログ ボックスで、ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-155">In the **Performing Operation** dialog box, the wizard starts executing tasks to import the information from SAP into a SQL Server database table.</span></span> <span data-ttu-id="9e81f-156">各タスクの状態は、ウィザードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e81f-156">The status for each task is displayed in the wizard.</span></span>  
  
14. <span data-ttu-id="9e81f-157">すべてのタスクが正常に実行される、クリックして**閉じる**です。</span><span class="sxs-lookup"><span data-stu-id="9e81f-157">After all the tasks are successfully executed, click **Close**.</span></span> <span data-ttu-id="9e81f-158">タスクが失敗した場合、対応するエラー メッセージを参照してください、問題を修正、ウィザードを再実行します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-158">If a task fails, see the corresponding error message, fix the issue, and rerun the wizard.</span></span>  
  
15. <span data-ttu-id="9e81f-159">ウィザードでは、統合サービス プロジェクトに、SSIS パッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-159">The wizard adds an SSIS package to your Integration Service project.</span></span> <span data-ttu-id="9e81f-160">統合サービス プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-160">Save the Integration Service project.</span></span>  
  
## <a name="running-the-ssis-package"></a><span data-ttu-id="9e81f-161">SSIS パッケージを実行します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-161">Running the SSIS Package</span></span>  
 <span data-ttu-id="9e81f-162">統合サービス プロジェクト内で、パッケージが作成されると、SAP システムから SQL Server データベースにデータをインポートすることを実行できます。</span><span class="sxs-lookup"><span data-stu-id="9e81f-162">Once the package is created within an Integration Service project, you can execute it to import data from an SAP system into a SQL Server database.</span></span> <span data-ttu-id="9e81f-163">パッケージを実行して SAP データをインポートするのには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-163">Perform the following steps to import SAP data by executing the package.</span></span>  
  
#### <a name="to-run-the-package-from-visual-studio"></a><span data-ttu-id="9e81f-164">Visual Studio からパッケージを実行するには</span><span class="sxs-lookup"><span data-stu-id="9e81f-164">To run the package from Visual Studio</span></span>  
  
1.  <span data-ttu-id="9e81f-165">ソリューション エクスプ ローラーで SSIS パッケージに移動します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-165">Navigate to the SSIS package in the Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="9e81f-166">パッケージ名を右クリックし **パッケージ実行**です。</span><span class="sxs-lookup"><span data-stu-id="9e81f-166">Right-click the package name and select **Execute Package**.</span></span>  
  
 <span data-ttu-id="9e81f-167">パッケージの実行の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972)です。</span><span class="sxs-lookup"><span data-stu-id="9e81f-167">For more information about running packages, see [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972).</span></span> <span data-ttu-id="9e81f-168">SSIS パッケージに関連するその他の情報を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973)です。</span><span class="sxs-lookup"><span data-stu-id="9e81f-168">For any other information related to SSIS packages, see [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973).</span></span>  
  
## <a name="verifying-the-results"></a><span data-ttu-id="9e81f-169">結果の確認</span><span class="sxs-lookup"><span data-stu-id="9e81f-169">Verifying the Results</span></span>  
 <span data-ttu-id="9e81f-170">パッケージを実行すると、SQL Server にログオンし、SAP データのインポート先となるデータベースに移動することによって結果を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e81f-170">After executing the package, you must verify the results by logging on to the SQL Server and navigating to the database to which the SAP data is imported.</span></span> <span data-ttu-id="9e81f-171">パッケージの実行がコピー先データベースにテーブルを作成し、SAP テーブルから値を挿入します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-171">Executing the package should have created a table in destination database and populated with the values from the SAP table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e81f-172">参照</span><span class="sxs-lookup"><span data-stu-id="9e81f-172">See Also</span></span>  
 [<span data-ttu-id="9e81f-173">SAP と SSIS のデータ プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-173">Use the Data Provider for SAP with SSIS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)