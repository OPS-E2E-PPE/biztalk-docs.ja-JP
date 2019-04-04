---
title: Visual Studio を使用して SAP のデータのインポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing SAP data, how to
- importing SAP data, using Visual Studio
- Visual Studio, importing SAP data
ms.assetid: 70cce089-232d-4ab9-81bd-6b0d6f0097d7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 700d597b3532c0034623553a6d1f0f8147e5642d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986003"
---
# <a name="import-sap-data-using-visual-studio"></a><span data-ttu-id="93318-102">Visual Studio を使用した SAP データのインポート</span><span class="sxs-lookup"><span data-stu-id="93318-102">Import SAP Data Using Visual Studio</span></span>
<span data-ttu-id="93318-103">このセクションでは、Microsoft を使用する方法の情報を提供します[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]SAP システムから SQL Server データベースにデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="93318-103">This section provides information on how to use Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to import data from an SAP system into a SQL Server database.</span></span> <span data-ttu-id="93318-104">このセクションでは、データをインポートする実行可能な SSIS パッケージを作成する方法の手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="93318-104">This section provides instruction on how to create an SSIS package that you can execute to import data.</span></span> <span data-ttu-id="93318-105">このセクションでは、SSIS パッケージを実行する方法に関する情報も提供します。</span><span class="sxs-lookup"><span data-stu-id="93318-105">This section also provides information on how to execute the SSIS package.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="93318-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="93318-106">Prerequisites</span></span>  
 <span data-ttu-id="93318-107">このトピックで説明する手順を実行する前に確認します。</span><span class="sxs-lookup"><span data-stu-id="93318-107">Before performing the procedures provided in this topic, make sure:</span></span>  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] <span data-ttu-id="93318-108">コンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="93318-108">is installed on the computer.</span></span>  
  
- [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] <span data-ttu-id="93318-109">コンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="93318-109">is installed on the computer.</span></span>  
  
### <a name="to-import-data-using-visual-studio"></a><span data-ttu-id="93318-110">Visual Studio を使用してデータをインポートするには</span><span class="sxs-lookup"><span data-stu-id="93318-110">To import data using Visual Studio</span></span>  
  
1. <span data-ttu-id="93318-111">開始[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]との統合サービス プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="93318-111">Start [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and create an Integration Service project.</span></span>  
  
2. <span data-ttu-id="93318-112">**プロジェクト**メニューの  **SSIS インポートおよびエクスポート ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="93318-112">From the **Project** menu, select **SSIS Import and Export Wizard**.</span></span> <span data-ttu-id="93318-113">起動、 **SQL Server インポートおよびエクスポート ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="93318-113">This starts the **SQL Server Import and Export Wizard**.</span></span>  
  
3. <span data-ttu-id="93318-114">クリックして [ようこそ] 画面の情報を読み取る**次**します。</span><span class="sxs-lookup"><span data-stu-id="93318-114">Read the information on the welcome screen and click **Next**.</span></span>  
  
4. <span data-ttu-id="93318-115">**データ ソースの選択** ダイアログ ボックスから、**データ ソース**ドロップダウン リスト**mySAP Business Suite の .NET Framework Data Provider**します。</span><span class="sxs-lookup"><span data-stu-id="93318-115">In the **Choose a Data Source** dialog box, from the **Data Source** drop-down list **.NET Framework Data Provider for mySAP Business Suite**.</span></span> <span data-ttu-id="93318-116">ダイアログ ボックスでは、SAP システムへの接続に別の接続パラメーターが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="93318-116">The dialog box lists the different connection parameters to connect to an SAP system.</span></span> <span data-ttu-id="93318-117">SAP システムを使用して接続するための一般的な接続文字列、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]が必要です。</span><span class="sxs-lookup"><span data-stu-id="93318-117">A typical connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requires:</span></span>  
  
   - <span data-ttu-id="93318-118">接続の種類の接続パラメーター。</span><span class="sxs-lookup"><span data-stu-id="93318-118">The connection parameters for a connection type.</span></span> <span data-ttu-id="93318-119">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] A、B、および D の接続の種類をサポートしていますSAP システムへの接続には、いずれかの接続パラメーターを指定する必要があります*1 つ*のこれらの接続の種類。</span><span class="sxs-lookup"><span data-stu-id="93318-119">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports connection types A, B, and D. To connect to an SAP system you must provide connection parameters for any *one* of these connection types.</span></span> <span data-ttu-id="93318-120">たとえば、A の接続の種類、アプリケーション サーバーのホストとシステムの数の名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93318-120">For example, for connection type A, you must provide the name of the application server host and the system number.</span></span>  
  
   - <span data-ttu-id="93318-121">ユーザー名とパスワードなどの SAP システムに接続するログイン情報。</span><span class="sxs-lookup"><span data-stu-id="93318-121">The login information to connect to an SAP system such as username and password.</span></span>  
  
     <span data-ttu-id="93318-122">SAP システムを使用して接続する接続文字列の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP 接続文字列のデータ プロバイダーについて](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)します。</span><span class="sxs-lookup"><span data-stu-id="93318-122">For more information about the connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Read about Data Provider for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
     <span data-ttu-id="93318-123">**データ ソースの選択** ダイアログ ボックスで指定します。</span><span class="sxs-lookup"><span data-stu-id="93318-123">In the **Choose a Data Source** dialog box, specify:</span></span>  
  
   - <span data-ttu-id="93318-124">任意の 1 つの接続の接続パラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="93318-124">The connection parameters for any one connection type.</span></span>  
  
   - <span data-ttu-id="93318-125">SAP システムへの接続にログイン情報。</span><span class="sxs-lookup"><span data-stu-id="93318-125">The login information to connect to an SAP system.</span></span>  
  
   - <span data-ttu-id="93318-126">SAP GUI のデバッグを有効にするかどうか。</span><span class="sxs-lookup"><span data-stu-id="93318-126">Whether you want to enable SAP GUI debugging.</span></span>  
  
   - <span data-ttu-id="93318-127">RFC SDK トレースを使用するかどうか。</span><span class="sxs-lookup"><span data-stu-id="93318-127">Whether you want to use RFC SDK tracing.</span></span>  
  
     <span data-ttu-id="93318-128">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="93318-128">Click **Next**.</span></span>  
  
5. <span data-ttu-id="93318-129">**変換先の選択** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="93318-129">In the **Choose a Destination** dialog box:</span></span>  
  
   1.  <span data-ttu-id="93318-130">**先**ドロップダウン リストで、 **SQL Native Client**します。</span><span class="sxs-lookup"><span data-stu-id="93318-130">From the **Destination** drop-down list, select **SQL Native Client**.</span></span>  
  
   2.  <span data-ttu-id="93318-131">**サーバー名**ドロップダウン リストで、SQL server の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="93318-131">From the **Server name** drop-down list, select a SQL server name.</span></span>  
  
   3.  <span data-ttu-id="93318-132">認証モードを選択します。</span><span class="sxs-lookup"><span data-stu-id="93318-132">Select an authentication mode.</span></span>  
  
   4.  <span data-ttu-id="93318-133">**データベース**ドロップダウン リストで、SAP テーブルをインポートするデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="93318-133">From the **Database** drop-down list, select the database to which you want to import the SAP table.</span></span>  
  
   5.  <span data-ttu-id="93318-134">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="93318-134">Click **Next**.</span></span>  
  
6. <span data-ttu-id="93318-135">**指定のテーブルのコピーまたはクエリ** ダイアログ ボックスで、選択、**を転送するデータを指定するクエリを記述**オプションを選択し、をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="93318-135">In the **Specify Table Copy or Query** dialog box, choose the **Write a query to specify the data to transfer** option and click **Next**.</span></span>  
  
7. <span data-ttu-id="93318-136">**ソース クエリの指定** ダイアログ ボックスで、SQL Server にインポートするデータをフィルター選択クエリを指定します。</span><span class="sxs-lookup"><span data-stu-id="93318-136">In the **Provide a Source Query** dialog box, specify a SELECT query to filter the data to be imported into the SQL Server.</span></span> <span data-ttu-id="93318-137">クエリの SELECT、文法の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP で SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="93318-137">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Syntax for a SELECT Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).</span></span>  
  
    <span data-ttu-id="93318-138">をクリックして、**解析** をクリックしてクエリを検証します をクリックして**OK**ポップアップ ダイアログ ボックスで。</span><span class="sxs-lookup"><span data-stu-id="93318-138">Click the **Parse** button to validate the query and click **OK** in the pop-up dialog box.</span></span> <span data-ttu-id="93318-139">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="93318-139">Click **Next**.</span></span>  
  
8. <span data-ttu-id="93318-140">**選択元のテーブルおよびビュー**  ダイアログ ボックスで、ソースと変換先のテーブルに対してチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="93318-140">In the **Select Source Tables and Views** dialog box, select the check box against the source and destination tables.</span></span> <span data-ttu-id="93318-141">ソースは、SAP からデータを取得する指定したクエリです。</span><span class="sxs-lookup"><span data-stu-id="93318-141">The source is the query you specified to retrieve data from SAP.</span></span> <span data-ttu-id="93318-142">変換先は、SQL Server データベースに作成されるテーブルです。</span><span class="sxs-lookup"><span data-stu-id="93318-142">The destination is the table that will be created in the SQL Server database.</span></span>  
  
9. <span data-ttu-id="93318-143">ウィザードは、ソースと宛先の間の既定のマッピング テーブルのフィールドを作成します。</span><span class="sxs-lookup"><span data-stu-id="93318-143">The wizard creates a default mapping between the source and destination table fields.</span></span> <span data-ttu-id="93318-144">ただし、要件に従って、マッピングを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="93318-144">However, you can change the mappings according to your requirement.</span></span> <span data-ttu-id="93318-145">フィールド マッピングを変更するには、クリックして**マッピングの編集**します。</span><span class="sxs-lookup"><span data-stu-id="93318-145">To change the field mappings, click **Edit Mappings**.</span></span>  
  
     <span data-ttu-id="93318-146">![SAP および SQL テーブル間の列マッピング](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")</span><span class="sxs-lookup"><span data-stu-id="93318-146">![Column mappings between SAP and SQL tables](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")</span></span>  
  
10. <span data-ttu-id="93318-147">**列マッピング** ダイアログ ボックスができます。</span><span class="sxs-lookup"><span data-stu-id="93318-147">In the **Column Mappings** dialog box, you can:</span></span>  
  
    -   <span data-ttu-id="93318-148">変換先テーブル内の列の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="93318-148">Change the names of columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="93318-149">変換先テーブルで特定の列を無視します。</span><span class="sxs-lookup"><span data-stu-id="93318-149">Ignore certain columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="93318-150">変換先テーブル内のフィールドのデータ型を変更します。</span><span class="sxs-lookup"><span data-stu-id="93318-150">Change the data type for fields in destination table.</span></span>  
  
    -   <span data-ttu-id="93318-151">Null 許容型のサイズ、有効桁数、およびスケールなどの他のフィールドの属性を変更します。</span><span class="sxs-lookup"><span data-stu-id="93318-151">Change other field attributes such as nullable, size, precision, and scale.</span></span>  
  
    -   <span data-ttu-id="93318-152">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="93318-152">Click **OK**.</span></span>  
  
11. <span data-ttu-id="93318-153">**選択元のテーブルおよびビュー**ダイアログ ボックスで、をクリックして**次**。</span><span class="sxs-lookup"><span data-stu-id="93318-153">In the **Select Source Tables and Views** dialog box, click **Next**.</span></span>  
  
12. <span data-ttu-id="93318-154">**ウィザードを完了** ダイアログ ボックスで、ウィザードを実行し、をクリックする操作の概要を確認**完了**します。</span><span class="sxs-lookup"><span data-stu-id="93318-154">In the **Complete the Wizard** dialog box, review the summary of actions that the wizard will perform, and click **Finish**.</span></span>  
  
13. <span data-ttu-id="93318-155">**操作を実行して**SAP から情報を SQL Server データベースのテーブルにインポートするタスクを実行するダイアログ ボックスで、ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="93318-155">In the **Performing Operation** dialog box, the wizard starts executing tasks to import the information from SAP into a SQL Server database table.</span></span> <span data-ttu-id="93318-156">ウィザードでは、各タスクの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="93318-156">The status for each task is displayed in the wizard.</span></span>  
  
14. <span data-ttu-id="93318-157">すべてのタスクが正常に実行される、クリックして**閉じる**します。</span><span class="sxs-lookup"><span data-stu-id="93318-157">After all the tasks are successfully executed, click **Close**.</span></span> <span data-ttu-id="93318-158">タスクが失敗した場合、対応するエラー メッセージが表示、問題を解決し、ウィザードを再実行します。</span><span class="sxs-lookup"><span data-stu-id="93318-158">If a task fails, see the corresponding error message, fix the issue, and rerun the wizard.</span></span>  
  
15. <span data-ttu-id="93318-159">ウィザードでは、統合サービス プロジェクトに、SSIS パッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="93318-159">The wizard adds an SSIS package to your Integration Service project.</span></span> <span data-ttu-id="93318-160">統合サービス プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="93318-160">Save the Integration Service project.</span></span>  
  
## <a name="running-the-ssis-package"></a><span data-ttu-id="93318-161">SSIS パッケージを実行します。</span><span class="sxs-lookup"><span data-stu-id="93318-161">Running the SSIS Package</span></span>  
 <span data-ttu-id="93318-162">統合サービス プロジェクトでは、パッケージが作成されると、SAP システムから SQL Server データベースにデータをインポートすることを実行できます。</span><span class="sxs-lookup"><span data-stu-id="93318-162">Once the package is created within an Integration Service project, you can execute it to import data from an SAP system into a SQL Server database.</span></span> <span data-ttu-id="93318-163">パッケージを実行して SAP データをインポートするのには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="93318-163">Perform the following steps to import SAP data by executing the package.</span></span>  
  
#### <a name="to-run-the-package-from-visual-studio"></a><span data-ttu-id="93318-164">Visual Studio からパッケージを実行するには</span><span class="sxs-lookup"><span data-stu-id="93318-164">To run the package from Visual Studio</span></span>  
  
1. <span data-ttu-id="93318-165">ソリューション エクスプ ローラーで SSIS パッケージに移動します。</span><span class="sxs-lookup"><span data-stu-id="93318-165">Navigate to the SSIS package in the Solution Explorer.</span></span>  
  
2. <span data-ttu-id="93318-166">パッケージ名を右クリックして**パッケージ実行**します。</span><span class="sxs-lookup"><span data-stu-id="93318-166">Right-click the package name and select **Execute Package**.</span></span>  
  
   <span data-ttu-id="93318-167">パッケージの実行の詳細については、[ http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93318-167">For more information about running packages, see [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972).</span></span> <span data-ttu-id="93318-168">SSIS パッケージに関連するその他の情報を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973)します。</span><span class="sxs-lookup"><span data-stu-id="93318-168">For any other information related to SSIS packages, see [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973).</span></span>  
  
## <a name="verifying-the-results"></a><span data-ttu-id="93318-169">結果の確認</span><span class="sxs-lookup"><span data-stu-id="93318-169">Verifying the Results</span></span>  
 <span data-ttu-id="93318-170">パッケージを実行した後は、SQL Server にログオンしている、SAP データをインポートするデータベースに移動して結果を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93318-170">After executing the package, you must verify the results by logging on to the SQL Server and navigating to the database to which the SAP data is imported.</span></span> <span data-ttu-id="93318-171">パッケージを実行する必要がありますが転送先データベースでテーブルを作成し、SAP テーブルから値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="93318-171">Executing the package should have created a table in destination database and populated with the values from the SAP table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93318-172">参照</span><span class="sxs-lookup"><span data-stu-id="93318-172">See Also</span></span>  
 [<span data-ttu-id="93318-173">Data Provider for SAP を SSIS と一緒に使用する</span><span class="sxs-lookup"><span data-stu-id="93318-173">Use the Data Provider for SAP with SSIS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)