---
title: "SQL Server Management Studio を使用して SAP データのインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing SAP data, how to
- SQL Server Management Studio, importing data
ms.assetid: c8151c6d-4b33-40fe-9b83-9bed27df9a99
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28981d2130e82a094e470de1e2b6904382be56b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="import-sap-data-using-sql-server-management-studio"></a><span data-ttu-id="5c0b1-102">SQL Server Management Studio を使用して SAP データのインポート</span><span class="sxs-lookup"><span data-stu-id="5c0b1-102">Import SAP Data Using SQL Server Management Studio</span></span>
<span data-ttu-id="5c0b1-103">このセクションでは、SQL Server Management Studio を使用して SAP システムから SQL Server データベースにデータをインポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-103">This section provides information on how to use the SQL Server Management Studio to import data from an SAP system into a SQL Server database.</span></span> <span data-ttu-id="5c0b1-104">このセクションでは、データをインポートする実行可能な SSIS パッケージを作成する方法の命令を提供します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-104">This section provides instruction on how to create an SSIS package that you can execute to import data.</span></span> <span data-ttu-id="5c0b1-105">このセクションでは、SSIS パッケージを実行する方法についても情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-105">This section also provides information on how to execute the SSIS package.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5c0b1-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="5c0b1-106">Prerequisites</span></span>  
 <span data-ttu-id="5c0b1-107">このトピックに記載されている手順を実行する前に確認します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-107">Before performing the procedures provided in this topic, make sure:</span></span>  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]<span data-ttu-id="5c0b1-108">コンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-108"> is installed on the computer.</span></span>  
  
-   <span data-ttu-id="5c0b1-109">SQL Server Business Intelligence Development Studio は、コンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-109">SQL Server Business Intelligence Development Studio is installed on the computer.</span></span>  
  
### <a name="to-import-data-using-sql-server-management-studio"></a><span data-ttu-id="5c0b1-110">SQL Server Management Studio を使用してデータをインポートするには</span><span class="sxs-lookup"><span data-stu-id="5c0b1-110">To import data using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="5c0b1-111">SQL Server Management Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-111">Start the SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="5c0b1-112">**サーバーへの接続** ダイアログ ボックスで、SQL Server データベースに接続し、をクリックする値を指定**接続**です。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-112">In the **Connect to Server** dialog box, specify the values to connect to a SQL Server database and click **Connect**.</span></span> <span data-ttu-id="5c0b1-113">**Microsoft SQL Server Management Studio**が開きます。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-113">The **Microsoft SQL Server Management Studio** opens.</span></span>  
  
3.  <span data-ttu-id="5c0b1-114">**オブジェクト エクスプ ローラー**、SQL Server 名を展開し、**データベース**、しをエクスポートするテーブルの SAP システムからデータベースを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-114">In the **Object Explorer**, expand the SQL Server name, expand **Databases**, and right-click the database into which you will be exporting the tables from the SAP system.</span></span> <span data-ttu-id="5c0b1-115">コンテキスト メニューのをポイント**タスク**、 をクリック**データのインポート**です。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-115">From the context menu, point to **Tasks**, and click **Import Data**.</span></span> <span data-ttu-id="5c0b1-116">起動、 **SQL Server インポートおよびエクスポート ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-116">This starts the **SQL Server Import and Export Wizard**.</span></span>  
  
4.  <span data-ttu-id="5c0b1-117">クリックして [ようこそ] 画面の情報を読み取る**次**です。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-117">Read the information on the welcome screen and click **Next**.</span></span>  
  
5.  <span data-ttu-id="5c0b1-118">**データ ソースを選択** ダイアログ ボックスから、**データ ソース**ドロップ ダウン リスト**.NET Framework Data Provider 用 mySAP Business Suite**です。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-118">In the **Choose a Data Source** dialog box, from the **Data Source** drop-down list **.NET Framework Data Provider for mySAP Business Suite**.</span></span> <span data-ttu-id="5c0b1-119">ダイアログ ボックスは、SAP システムへの接続に別の接続パラメーターを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-119">The dialog box lists the different connection parameters to connect to an SAP system.</span></span> <span data-ttu-id="5c0b1-120">使用して SAP システムへの接続に一般的な接続文字列、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]が必要です。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-120">A typical connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requires:</span></span>  
  
    -   <span data-ttu-id="5c0b1-121">接続の接続パラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-121">The connection parameters for a connection type.</span></span> <span data-ttu-id="5c0b1-122">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] A、B、および D の接続の種類をサポートしていますSAP システムへの接続には、いずれかの接続パラメーターを指定する必要があります*1*種類の接続をします。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-122">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports connection types A, B, and D. To connect to an SAP system you must provide connection parameters for any *one* of these connection types.</span></span> <span data-ttu-id="5c0b1-123">たとえば、接続の種類、システム数と、アプリケーション サーバーのホストの名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-123">For example, for connection type A, you must provide the name of the application server host and the system number.</span></span>  
  
    -   <span data-ttu-id="5c0b1-124">ユーザー名やパスワードなど、SAP システムへの接続にログイン情報。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-124">The login information to connect to an SAP system such as username and password.</span></span>  
  
     <span data-ttu-id="5c0b1-125">使用して SAP システムへの接続への接続文字列の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP 接続文字列のデータ プロバイダーの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)です。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-125">For more information about the connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Read about Data Provider for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
     <span data-ttu-id="5c0b1-126">**データ ソースを選択** ダイアログ ボックスで指定します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-126">In the **Choose a Data Source** dialog box, specify:</span></span>  
  
    -   <span data-ttu-id="5c0b1-127">任意の 1 つの接続の接続パラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-127">The connection parameters for any one connection type.</span></span>  
  
    -   <span data-ttu-id="5c0b1-128">SAP システムへの接続にログイン情報。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-128">The login information to connect to an SAP system.</span></span>  
  
    -   <span data-ttu-id="5c0b1-129">SAP GUI のデバッグを有効にするかどうか。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-129">Whether you want to enable SAP GUI debugging.</span></span>  
  
    -   <span data-ttu-id="5c0b1-130">RFC SDK トレースを使用するかどうか。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-130">Whether you want to use RFC SDK tracing.</span></span>  
  
     <span data-ttu-id="5c0b1-131">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-131">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="5c0b1-132">**先選択** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-132">In the **Choose a Destination** dialog box:</span></span>  
  
    1.  <span data-ttu-id="5c0b1-133">**先**ドロップダウン リストで、 **SQL Native Client**です。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-133">From the **Destination** drop-down list, select **SQL Native Client**.</span></span>  
  
    2.  <span data-ttu-id="5c0b1-134">**サーバー名**ドロップダウン リストで、SQL server 名を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-134">From the **Server name** drop-down list, select a SQL server name.</span></span>  
  
    3.  <span data-ttu-id="5c0b1-135">認証モードを選択します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-135">Select an authentication mode.</span></span>  
  
    4.  <span data-ttu-id="5c0b1-136">**データベース**ドロップダウン リストで、SAP テーブルをインポートするデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-136">From the **Database** drop-down list, select the database to which you want to import the SAP table.</span></span>  
  
    5.  <span data-ttu-id="5c0b1-137">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-137">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="5c0b1-138">**テーブルのコピーを指定またはクエリ** ダイアログ ボックスで、選択、**を転送するデータを指定するクエリを記述**オプションし、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-138">In the **Specify Table Copy or Query** dialog box, choose the **Write a query to specify the data to transfer** option and click **Next**.</span></span>  
  
8.  <span data-ttu-id="5c0b1-139">**ソース クエリを指定する** ダイアログ ボックスで、SQL Server にインポートするデータをフィルター選択クエリを指定します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-139">In the **Provide a Source Query** dialog box, specify a SELECT query to filter the data to be imported into the SQL Server.</span></span> <span data-ttu-id="5c0b1-140">クエリを SELECT の文法の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[選択ステートメント SAP の構文](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-140">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Syntax for a SELECT Statement SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).</span></span>  
  
     <span data-ttu-id="5c0b1-141">をクリックして、**解析**クエリを検証し、をクリックするボタン**[ok]**ポップアップ ダイアログ ボックスにします。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-141">Click the **Parse** button to validate the query and click **OK** in the pop-up dialog box.</span></span> <span data-ttu-id="5c0b1-142">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-142">Click **Next**.</span></span>  
  
9. <span data-ttu-id="5c0b1-143">**[ソース テーブルおよびビュー** ] ダイアログ ボックスで、ソース テーブルと対象テーブルに対してチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-143">In the **Select Source Tables and Views** dialog box, select the check box against the source and destination tables.</span></span> <span data-ttu-id="5c0b1-144">ソースは、SAP からデータを取得するように指定したクエリを示します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-144">The source is the query you specified to retrieve data from SAP.</span></span> <span data-ttu-id="5c0b1-145">変換先は、SQL Server データベースに作成されるテーブルです。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-145">The destination is the table that will be created in the SQL Server database.</span></span>  
  
10. <span data-ttu-id="5c0b1-146">ウィザードでは、テーブルのフィールド、ソースと移行先の既定のマッピングを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-146">The wizard creates a default mapping between the source and destination table fields.</span></span> <span data-ttu-id="5c0b1-147">ただし、要件に従って、マッピングを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-147">However, you can change the mappings according to your requirement.</span></span> <span data-ttu-id="5c0b1-148">フィールド マッピングを変更する をクリックして**マッピングの編集**です。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-148">To change the field mappings, click **Edit Mappings**.</span></span>  
  
     <span data-ttu-id="5c0b1-149">![SAP テーブルと SQL テーブル間の列マッピング](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")</span><span class="sxs-lookup"><span data-stu-id="5c0b1-149">![Column mappings between SAP and SQL tables](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")</span></span>  
  
11. <span data-ttu-id="5c0b1-150">**列マッピング**ダイアログ ボックスで、することができます。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-150">In the **Column Mappings** dialog box, you can:</span></span>  
  
    -   <span data-ttu-id="5c0b1-151">変換先テーブル内の列の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-151">Change the names of columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="5c0b1-152">変換先テーブル内の特定の列を無視します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-152">Ignore certain columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="5c0b1-153">コピー先のテーブル内のフィールドのデータ型を変更します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-153">Change the data type for fields in destination table.</span></span>  
  
    -   <span data-ttu-id="5c0b1-154">Nullable、サイズ、有効桁数、小数点以下桁数などその他のフィールドの属性を変更します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-154">Change other field attributes such as nullable, size, precision, and scale.</span></span>  
  
    -   <span data-ttu-id="5c0b1-155">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-155">Click **OK**.</span></span>  
  
12. <span data-ttu-id="5c0b1-156">**ソース テーブルおよびビュー**ダイアログ ボックスで、をクリックして**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-156">In the **Select Source Tables and Views** dialog box, click **Next**.</span></span>  
  
13. <span data-ttu-id="5c0b1-157">**パッケージの実行を保存して** ダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="5c0b1-157">In the **Save and Execute Package** dialog box,</span></span>  
  
    -   <span data-ttu-id="5c0b1-158">選択、**をすぐに実行**クエリを実行する チェック ボックスです。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-158">Select the **Execute immediately** check box to execute the query.</span></span>  
  
    -   <span data-ttu-id="5c0b1-159">選択、 **SSIS パッケージの保存**パッケージとしてクエリを保存し、後で実行する チェック ボックスです。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-159">Select the **Save SSIS Package** check box to save the query as a package and execute it later.</span></span> <span data-ttu-id="5c0b1-160">パッケージの保存先を選択した場合も、SQL Server またはファイル システムにパッケージを保存するかどうかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-160">If you chose to save the package, you must also specify whether you want to save the package in the SQL Server or the file system.</span></span>  
  
    -   <span data-ttu-id="5c0b1-161">**パッケージの保護レベル**-ドロップダウン リスト、選択、保護は、パッケージ レベルし、資格情報を指定必要な場所です。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-161">From the **Package protection level** drop-down list, select a protection level for the package and specify credentials where required.</span></span>  
  
    -   <span data-ttu-id="5c0b1-162">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-162">Click **Next**.</span></span>  
  
     <span data-ttu-id="5c0b1-163">パッケージを保存することを選択する場合は、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-163">If you chose to save the package, proceed to next step.</span></span> <span data-ttu-id="5c0b1-164">それ以外の場合、手順 15 に進みます。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-164">Otherwise, skip to step 15.</span></span>  
  
14. <span data-ttu-id="5c0b1-165">**SSIS パッケージの保存** ダイアログ ボックスで指定します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-165">In the **Save SSIS Package** dialog box, specify:</span></span>  
  
    -   <span data-ttu-id="5c0b1-166">パッケージの名前</span><span class="sxs-lookup"><span data-stu-id="5c0b1-166">Name for the package</span></span>  
  
    -   <span data-ttu-id="5c0b1-167">パッケージの説明</span><span class="sxs-lookup"><span data-stu-id="5c0b1-167">Description for the package</span></span>  
  
    -   <span data-ttu-id="5c0b1-168">SQL server にパッケージを保存する場合は、選択から SQL Server、**サーバー名**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-168">If you chose to save the package to a SQL server, select a SQL Server from the **Server name** drop-down list.</span></span>  
  
    -   <span data-ttu-id="5c0b1-169">ファイル システムにパッケージを保存する場合は、指定のファイルの場所と名前、**ファイル名**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-169">If you chose to save the package to the file system, specify the name and location of the file in the **File name** text box.</span></span>  
  
    -   <span data-ttu-id="5c0b1-170">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-170">Click **Next**.</span></span>  
  
15. <span data-ttu-id="5c0b1-171">**ウィザードを完了** ダイアログ ボックスで、ウィザードを実行し、をクリックする操作の概要を確認**完了**です。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-171">In the **Complete the Wizard** dialog box, review the summary of actions that the wizard will perform, and click **Finish**.</span></span>  
  
16. <span data-ttu-id="5c0b1-172">**操作の実行**SAP から情報を SQL Server データベース テーブルにインポートするタスクを実行してダイアログ ボックスで、ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-172">In the **Performing Operations** dialog box, the wizard starts executing tasks to import the information from SAP into a SQL Server database table.</span></span> <span data-ttu-id="5c0b1-173">各タスクの状態は、ウィザードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-173">The status for each task is displayed in the wizard.</span></span>  
  
17. <span data-ttu-id="5c0b1-174">すべてのタスクが正常に実行される、クリックして**閉じる**です。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-174">After all the tasks are successfully executed, click **Close**.</span></span> <span data-ttu-id="5c0b1-175">タスクが失敗した場合、対応するエラー メッセージを参照してください、問題を修正、ウィザードを再実行します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-175">If a task fails, see the corresponding error message, fix the issue, and rerun the wizard.</span></span>  
  
## <a name="running-the-ssis-package"></a><span data-ttu-id="5c0b1-176">SSIS パッケージを実行します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-176">Running the SSIS Package</span></span>  
 <span data-ttu-id="5c0b1-177">SSIS パッケージを保存する場合を実行すると、SAP システムから最新の情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-177">If you chose to save the SSIS package, you can run it to retrieve the most recent information from the SAP system.</span></span> <span data-ttu-id="5c0b1-178">このセクションでは、ファイル システムに保存する場合は、パッケージを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-178">This section provides information on how to run the package if you chose to save it to the file system.</span></span>  
  
#### <a name="to-run-the-package-from-windows-explorer"></a><span data-ttu-id="5c0b1-179">Windows エクスプ ローラーからパッケージを実行するには</span><span class="sxs-lookup"><span data-stu-id="5c0b1-179">To run the package from Windows Explorer</span></span>  
  
1.  <span data-ttu-id="5c0b1-180">**Windows エクスプ ローラー**パッケージを保存した場所に移動し、パッケージをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-180">From the **Windows Explorer**, navigate to the location where you saved the package, and double-click the package.</span></span>  
  
2.  <span data-ttu-id="5c0b1-181">**パッケージ実行ユーティリティ**ダイアログ ボックスで、をクリックして**Execute**です。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-181">On the **Execute Package Utility** dialog box, click **Execute**.</span></span>  
  
3.  <span data-ttu-id="5c0b1-182">**パッケージ実行の進行状況** ダイアログ ボックスには、さまざまなタスクの進行状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-182">The **Package Execution Progress** dialog box displays the progress of the different tasks.</span></span>  
  
4.  <span data-ttu-id="5c0b1-183">すべてのタスクが正常に実行される、クリックして**閉じる**です。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-183">After all the tasks are successfully executed, click **Close**.</span></span>  
  
5.  <span data-ttu-id="5c0b1-184">**パッケージ実行ユーティリティ**ダイアログ ボックスで、をクリックして**閉じる**です。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-184">On the **Execute Package Utility** dialog box, click **Close**.</span></span>  
  
 <span data-ttu-id="5c0b1-185">パッケージの実行の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972)です。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-185">For more information about running packages, see [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972).</span></span> <span data-ttu-id="5c0b1-186">SSIS パッケージに関連するその他の情報を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973)です。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-186">For any other information related to SSIS packages, see [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973).</span></span>  
  
## <a name="verifying-the-results"></a><span data-ttu-id="5c0b1-187">結果の確認</span><span class="sxs-lookup"><span data-stu-id="5c0b1-187">Verifying the Results</span></span>  
 <span data-ttu-id="5c0b1-188">パッケージを実行すると、SAP データのインポート先となる SQL Server データベースに移動して、結果を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-188">After executing the package, you must verify the results by going to the SQL Server database to which the SAP data is imported.</span></span> <span data-ttu-id="5c0b1-189">パッケージの実行がコピー先データベースにテーブルを作成し、SAP テーブルから値を挿入します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-189">Executing the package should have created a table in destination database and populated with the values from the SAP table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c0b1-190">参照</span><span class="sxs-lookup"><span data-stu-id="5c0b1-190">See Also</span></span>  
 [<span data-ttu-id="5c0b1-191">SAP と SSIS のデータ プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="5c0b1-191">Using the Data Provider for SAP with SSIS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)