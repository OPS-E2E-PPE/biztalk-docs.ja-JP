---
title: SQL Server Management Studio を使用して SAP のデータのインポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing SAP data, how to
- SQL Server Management Studio, importing data
ms.assetid: c8151c6d-4b33-40fe-9b83-9bed27df9a99
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6c825653321f2dbe0bf5ef1f5ed58676e6ae90e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995683"
---
# <a name="import-sap-data-using-sql-server-management-studio"></a><span data-ttu-id="5c4e8-102">SQL Server Management Studio を使用して SAP データのインポート</span><span class="sxs-lookup"><span data-stu-id="5c4e8-102">Import SAP Data Using SQL Server Management Studio</span></span>
<span data-ttu-id="5c4e8-103">このセクションでは、SAP システムから SQL Server データベースにデータをインポートする、SQL Server Management Studio を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-103">This section provides information on how to use the SQL Server Management Studio to import data from an SAP system into a SQL Server database.</span></span> <span data-ttu-id="5c4e8-104">このセクションでは、データをインポートする実行可能な SSIS パッケージを作成する方法の手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-104">This section provides instruction on how to create an SSIS package that you can execute to import data.</span></span> <span data-ttu-id="5c4e8-105">このセクションでは、SSIS パッケージを実行する方法に関する情報も提供します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-105">This section also provides information on how to execute the SSIS package.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5c4e8-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="5c4e8-106">Prerequisites</span></span>  
 <span data-ttu-id="5c4e8-107">このトピックで説明する手順を実行する前に確認します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-107">Before performing the procedures provided in this topic, make sure:</span></span>  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]<span data-ttu-id="5c4e8-108"> コンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-108"> is installed on the computer.</span></span>  
  
- <span data-ttu-id="5c4e8-109">SQL Server Business Intelligence Development Studio は、コンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-109">SQL Server Business Intelligence Development Studio is installed on the computer.</span></span>  
  
### <a name="to-import-data-using-sql-server-management-studio"></a><span data-ttu-id="5c4e8-110">SQL Server Management Studio を使用してデータをインポートするには</span><span class="sxs-lookup"><span data-stu-id="5c4e8-110">To import data using SQL Server Management Studio</span></span>  
  
1. <span data-ttu-id="5c4e8-111">SQL Server Management Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-111">Start the SQL Server Management Studio.</span></span>  
  
2. <span data-ttu-id="5c4e8-112">**サーバーへの接続** ダイアログ ボックスで、SQL Server データベースに接続し をクリックして値を指定**Connect**します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-112">In the **Connect to Server** dialog box, specify the values to connect to a SQL Server database and click **Connect**.</span></span> <span data-ttu-id="5c4e8-113">**Microsoft SQL Server Management Studio**が開きます。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-113">The **Microsoft SQL Server Management Studio** opens.</span></span>  
  
3. <span data-ttu-id="5c4e8-114">**オブジェクト エクスプ ローラー**展開し、SQL Server 名を展開し、**データベース**をエクスポートするテーブルの SAP システムからデータベースを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-114">In the **Object Explorer**, expand the SQL Server name, expand **Databases**, and right-click the database into which you will be exporting the tables from the SAP system.</span></span> <span data-ttu-id="5c4e8-115">コンテキスト メニューをポイント**タスク**、 をクリック**データのインポート**します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-115">From the context menu, point to **Tasks**, and click **Import Data**.</span></span> <span data-ttu-id="5c4e8-116">起動、 **SQL Server インポートおよびエクスポート ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-116">This starts the **SQL Server Import and Export Wizard**.</span></span>  
  
4. <span data-ttu-id="5c4e8-117">クリックして [ようこそ] 画面の情報を読み取る**次**します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-117">Read the information on the welcome screen and click **Next**.</span></span>  
  
5. <span data-ttu-id="5c4e8-118">**データ ソースの選択** ダイアログ ボックスから、**データ ソース**ドロップダウン リスト**mySAP Business Suite の .NET Framework Data Provider**します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-118">In the **Choose a Data Source** dialog box, from the **Data Source** drop-down list **.NET Framework Data Provider for mySAP Business Suite**.</span></span> <span data-ttu-id="5c4e8-119">ダイアログ ボックスでは、SAP システムへの接続に別の接続パラメーターが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-119">The dialog box lists the different connection parameters to connect to an SAP system.</span></span> <span data-ttu-id="5c4e8-120">SAP システムを使用して接続するための一般的な接続文字列、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]が必要です。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-120">A typical connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requires:</span></span>  
  
   - <span data-ttu-id="5c4e8-121">接続の種類の接続パラメーター。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-121">The connection parameters for a connection type.</span></span> <span data-ttu-id="5c4e8-122">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] A、B、および D の接続の種類をサポートしていますSAP システムへの接続には、いずれかの接続パラメーターを指定する必要があります*1 つ*のこれらの接続の種類。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-122">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports connection types A, B, and D. To connect to an SAP system you must provide connection parameters for any *one* of these connection types.</span></span> <span data-ttu-id="5c4e8-123">たとえば、A の接続の種類、アプリケーション サーバーのホストとシステムの数の名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-123">For example, for connection type A, you must provide the name of the application server host and the system number.</span></span>  
  
   - <span data-ttu-id="5c4e8-124">ユーザー名とパスワードなどの SAP システムに接続するログイン情報。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-124">The login information to connect to an SAP system such as username and password.</span></span>  
  
     <span data-ttu-id="5c4e8-125">SAP システムを使用して接続する接続文字列の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP 接続文字列のデータ プロバイダーについて](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-125">For more information about the connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Read about Data Provider for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
     <span data-ttu-id="5c4e8-126">**データ ソースの選択** ダイアログ ボックスで指定します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-126">In the **Choose a Data Source** dialog box, specify:</span></span>  
  
   - <span data-ttu-id="5c4e8-127">任意の 1 つの接続の接続パラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-127">The connection parameters for any one connection type.</span></span>  
  
   - <span data-ttu-id="5c4e8-128">SAP システムへの接続にログイン情報。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-128">The login information to connect to an SAP system.</span></span>  
  
   - <span data-ttu-id="5c4e8-129">SAP GUI のデバッグを有効にするかどうか。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-129">Whether you want to enable SAP GUI debugging.</span></span>  
  
   - <span data-ttu-id="5c4e8-130">RFC SDK トレースを使用するかどうか。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-130">Whether you want to use RFC SDK tracing.</span></span>  
  
     <span data-ttu-id="5c4e8-131">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-131">Click **Next**.</span></span>  
  
6. <span data-ttu-id="5c4e8-132">**変換先の選択** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-132">In the **Choose a Destination** dialog box:</span></span>  
  
   1.  <span data-ttu-id="5c4e8-133">**先**ドロップダウン リストで、 **SQL Native Client**します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-133">From the **Destination** drop-down list, select **SQL Native Client**.</span></span>  
  
   2.  <span data-ttu-id="5c4e8-134">**サーバー名**ドロップダウン リストで、SQL server の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-134">From the **Server name** drop-down list, select a SQL server name.</span></span>  
  
   3.  <span data-ttu-id="5c4e8-135">認証モードを選択します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-135">Select an authentication mode.</span></span>  
  
   4.  <span data-ttu-id="5c4e8-136">**データベース**ドロップダウン リストで、SAP テーブルをインポートするデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-136">From the **Database** drop-down list, select the database to which you want to import the SAP table.</span></span>  
  
   5.  <span data-ttu-id="5c4e8-137">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-137">Click **Next**.</span></span>  
  
7. <span data-ttu-id="5c4e8-138">**指定のテーブルのコピーまたはクエリ** ダイアログ ボックスで、選択、**を転送するデータを指定するクエリを記述**オプションを選択し、をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-138">In the **Specify Table Copy or Query** dialog box, choose the **Write a query to specify the data to transfer** option and click **Next**.</span></span>  
  
8. <span data-ttu-id="5c4e8-139">**ソース クエリの指定** ダイアログ ボックスで、SQL Server にインポートするデータをフィルター選択クエリを指定します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-139">In the **Provide a Source Query** dialog box, specify a SELECT query to filter the data to be imported into the SQL Server.</span></span> <span data-ttu-id="5c4e8-140">クエリの SELECT、文法の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[選択ステートメント SAP の構文](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-140">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Syntax for a SELECT Statement SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).</span></span>  
  
    <span data-ttu-id="5c4e8-141">をクリックして、**解析** をクリックしてクエリを検証します をクリックして**OK**ポップアップ ダイアログ ボックスで。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-141">Click the **Parse** button to validate the query and click **OK** in the pop-up dialog box.</span></span> <span data-ttu-id="5c4e8-142">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-142">Click **Next**.</span></span>  
  
9. <span data-ttu-id="5c4e8-143">**選択元のテーブルおよびビュー**  ダイアログ ボックスで、ソースと変換先のテーブルに対してチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-143">In the **Select Source Tables and Views** dialog box, select the check box against the source and destination tables.</span></span> <span data-ttu-id="5c4e8-144">ソースは、SAP からデータを取得する指定したクエリです。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-144">The source is the query you specified to retrieve data from SAP.</span></span> <span data-ttu-id="5c4e8-145">変換先は、SQL Server データベースに作成されるテーブルです。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-145">The destination is the table that will be created in the SQL Server database.</span></span>  
  
10. <span data-ttu-id="5c4e8-146">ウィザードは、ソースと宛先の間の既定のマッピング テーブルのフィールドを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-146">The wizard creates a default mapping between the source and destination table fields.</span></span> <span data-ttu-id="5c4e8-147">ただし、要件に従って、マッピングを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-147">However, you can change the mappings according to your requirement.</span></span> <span data-ttu-id="5c4e8-148">フィールド マッピングを変更するには、クリックして**マッピングの編集**します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-148">To change the field mappings, click **Edit Mappings**.</span></span>  
  
     <span data-ttu-id="5c4e8-149">![SAP および SQL テーブル間の列マッピング](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")</span><span class="sxs-lookup"><span data-stu-id="5c4e8-149">![Column mappings between SAP and SQL tables](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")</span></span>  
  
11. <span data-ttu-id="5c4e8-150">**列マッピング** ダイアログ ボックスができます。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-150">In the **Column Mappings** dialog box, you can:</span></span>  
  
    -   <span data-ttu-id="5c4e8-151">変換先テーブル内の列の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-151">Change the names of columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="5c4e8-152">変換先テーブルで特定の列を無視します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-152">Ignore certain columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="5c4e8-153">変換先テーブル内のフィールドのデータ型を変更します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-153">Change the data type for fields in destination table.</span></span>  
  
    -   <span data-ttu-id="5c4e8-154">Null 許容型のサイズ、有効桁数、およびスケールなどの他のフィールドの属性を変更します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-154">Change other field attributes such as nullable, size, precision, and scale.</span></span>  
  
    -   <span data-ttu-id="5c4e8-155">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-155">Click **OK**.</span></span>  
  
12. <span data-ttu-id="5c4e8-156">**選択元のテーブルおよびビュー**ダイアログ ボックスで、をクリックして**次**。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-156">In the **Select Source Tables and Views** dialog box, click **Next**.</span></span>  
  
13. <span data-ttu-id="5c4e8-157">**実行パッケージの保存および**ダイアログ ボックスで、</span><span class="sxs-lookup"><span data-stu-id="5c4e8-157">In the **Save and Execute Package** dialog box,</span></span>  
  
    - <span data-ttu-id="5c4e8-158">選択、**をすぐに実行**クエリを実行する チェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-158">Select the **Execute immediately** check box to execute the query.</span></span>  
  
    - <span data-ttu-id="5c4e8-159">選択、 **SSIS パッケージの保存**パッケージとしてクエリが保存され、後で実行する チェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-159">Select the **Save SSIS Package** check box to save the query as a package and execute it later.</span></span> <span data-ttu-id="5c4e8-160">パッケージを保存する場合は、SQL Server またはファイル システムにパッケージを保存するかどうかも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-160">If you chose to save the package, you must also specify whether you want to save the package in the SQL Server or the file system.</span></span>  
  
    - <span data-ttu-id="5c4e8-161">**パッケージの保護レベル**ドロップダウン リスト、選択、保護、パッケージのレベルし、資格情報を指定が必要です。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-161">From the **Package protection level** drop-down list, select a protection level for the package and specify credentials where required.</span></span>  
  
    - <span data-ttu-id="5c4e8-162">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-162">Click **Next**.</span></span>  
  
      <span data-ttu-id="5c4e8-163">パッケージを保存することを選択した場合は、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-163">If you chose to save the package, proceed to next step.</span></span> <span data-ttu-id="5c4e8-164">それ以外の場合、手順 15 に進みます。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-164">Otherwise, skip to step 15.</span></span>  
  
14. <span data-ttu-id="5c4e8-165">**SSIS パッケージの保存** ダイアログ ボックスで指定します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-165">In the **Save SSIS Package** dialog box, specify:</span></span>  
  
    -   <span data-ttu-id="5c4e8-166">パッケージの名前</span><span class="sxs-lookup"><span data-stu-id="5c4e8-166">Name for the package</span></span>  
  
    -   <span data-ttu-id="5c4e8-167">パッケージの説明</span><span class="sxs-lookup"><span data-stu-id="5c4e8-167">Description for the package</span></span>  
  
    -   <span data-ttu-id="5c4e8-168">SQL server にパッケージを保存する場合は、選択から SQL Server、**サーバー名**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-168">If you chose to save the package to a SQL server, select a SQL Server from the **Server name** drop-down list.</span></span>  
  
    -   <span data-ttu-id="5c4e8-169">ファイル システムにパッケージを保存する場合は、指定のファイルの場所と名前、**ファイル名**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-169">If you chose to save the package to the file system, specify the name and location of the file in the **File name** text box.</span></span>  
  
    -   <span data-ttu-id="5c4e8-170">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-170">Click **Next**.</span></span>  
  
15. <span data-ttu-id="5c4e8-171">**ウィザードを完了** ダイアログ ボックスで、ウィザードを実行し、をクリックする操作の概要を確認**完了**します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-171">In the **Complete the Wizard** dialog box, review the summary of actions that the wizard will perform, and click **Finish**.</span></span>  
  
16. <span data-ttu-id="5c4e8-172">**操作の実行**SAP から情報を SQL Server データベースのテーブルにインポートするタスクを実行するダイアログ ボックスで、ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-172">In the **Performing Operations** dialog box, the wizard starts executing tasks to import the information from SAP into a SQL Server database table.</span></span> <span data-ttu-id="5c4e8-173">ウィザードでは、各タスクの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-173">The status for each task is displayed in the wizard.</span></span>  
  
17. <span data-ttu-id="5c4e8-174">すべてのタスクが正常に実行される、クリックして**閉じる**します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-174">After all the tasks are successfully executed, click **Close**.</span></span> <span data-ttu-id="5c4e8-175">タスクが失敗した場合、対応するエラー メッセージが表示、問題を解決し、ウィザードを再実行します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-175">If a task fails, see the corresponding error message, fix the issue, and rerun the wizard.</span></span>  
  
## <a name="running-the-ssis-package"></a><span data-ttu-id="5c4e8-176">SSIS パッケージを実行します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-176">Running the SSIS Package</span></span>  
 <span data-ttu-id="5c4e8-177">SSIS パッケージを保存する場合を実行すると、SAP システムから最新の情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-177">If you chose to save the SSIS package, you can run it to retrieve the most recent information from the SAP system.</span></span> <span data-ttu-id="5c4e8-178">このセクションでは、ファイル システムに保存した場合に、パッケージを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-178">This section provides information on how to run the package if you chose to save it to the file system.</span></span>  
  
#### <a name="to-run-the-package-from-windows-explorer"></a><span data-ttu-id="5c4e8-179">Windows エクスプ ローラーからパッケージを実行するには</span><span class="sxs-lookup"><span data-stu-id="5c4e8-179">To run the package from Windows Explorer</span></span>  
  
1. <span data-ttu-id="5c4e8-180">**Windows エクスプ ローラー**パッケージを保存した場所に移動して、パッケージをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-180">From the **Windows Explorer**, navigate to the location where you saved the package, and double-click the package.</span></span>  
  
2. <span data-ttu-id="5c4e8-181">**パッケージ実行ユーティリティ**ダイアログ ボックスで、をクリックして**Execute**します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-181">On the **Execute Package Utility** dialog box, click **Execute**.</span></span>  
  
3. <span data-ttu-id="5c4e8-182">**パッケージ実行の進行状況** ダイアログ ボックスには、さまざまなタスクの進行状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-182">The **Package Execution Progress** dialog box displays the progress of the different tasks.</span></span>  
  
4. <span data-ttu-id="5c4e8-183">すべてのタスクが正常に実行される、クリックして**閉じる**します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-183">After all the tasks are successfully executed, click **Close**.</span></span>  
  
5. <span data-ttu-id="5c4e8-184">**パッケージ実行ユーティリティ**ダイアログ ボックスで、をクリックして**閉じる**します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-184">On the **Execute Package Utility** dialog box, click **Close**.</span></span>  
  
   <span data-ttu-id="5c4e8-185">パッケージの実行の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972)します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-185">For more information about running packages, see [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972).</span></span> <span data-ttu-id="5c4e8-186">SSIS パッケージに関連するその他の情報を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973)します。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-186">For any other information related to SSIS packages, see [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973).</span></span>  
  
## <a name="verifying-the-results"></a><span data-ttu-id="5c4e8-187">結果の確認</span><span class="sxs-lookup"><span data-stu-id="5c4e8-187">Verifying the Results</span></span>  
 <span data-ttu-id="5c4e8-188">パッケージを実行した後は、SAP のデータをインポートする SQL Server データベースに移動して結果を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-188">After executing the package, you must verify the results by going to the SQL Server database to which the SAP data is imported.</span></span> <span data-ttu-id="5c4e8-189">パッケージを実行する必要がありますが転送先データベースでテーブルを作成し、SAP テーブルから値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="5c4e8-189">Executing the package should have created a table in destination database and populated with the values from the SAP table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c4e8-190">参照</span><span class="sxs-lookup"><span data-stu-id="5c4e8-190">See Also</span></span>  
 [<span data-ttu-id="5c4e8-191">Data Provider for SAP を SSIS と一緒にの使用</span><span class="sxs-lookup"><span data-stu-id="5c4e8-191">Using the Data Provider for SAP with SSIS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)