---
title: Siebel を Visual Studio を使用してデータをインポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33701361-eca2-4795-a5e0-78162a98e9ba
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4479fbbfd704cea30b8981866d3b7a354ca7269f
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2017
ms.locfileid: "23450507"
---
# <a name="import-siebel-data-using-visual-studio"></a><span data-ttu-id="8d54d-102">Siebel を Visual Studio を使用してデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="8d54d-102">Import Siebel Data Using Visual Studio</span></span>
<span data-ttu-id="8d54d-103">このセクションでは、Microsoft の使用方法に関する情報を提供[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]Siebel システムから SQL Server データベースにデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="8d54d-103">This section provides information about how to use Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to import data from a Siebel system into a SQL Server database.</span></span> <span data-ttu-id="8d54d-104">また、作成し、このデータをインポートする SSIS パッケージを実行する方法の手順についても提供します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-104">It also provides instructions on how to create and execute an SSIS package to import this data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8d54d-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="8d54d-105">Prerequisites</span></span>  
 <span data-ttu-id="8d54d-106">このトピックに記載されている手順を実行する前に確認します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-106">Before performing the procedures provided in this topic, make sure:</span></span>  
  
-   <span data-ttu-id="8d54d-107">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]がコンピューターにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="8d54d-107">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] is installed on the computer.</span></span>  
  
-   <span data-ttu-id="8d54d-108">Microsoft Visual Studio は、コンピューターにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="8d54d-108">Microsoft Visual Studio is installed on the computer.</span></span>  
  
## <a name="import-in-visual-studio"></a><span data-ttu-id="8d54d-109">Visual Studio でのインポート</span><span class="sxs-lookup"><span data-stu-id="8d54d-109">Import in Visual Studio</span></span>  
 
1.  <span data-ttu-id="8d54d-110">開始[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]Integration Service プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-110">Start [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and create an Integration Service project.</span></span>  
  
2.  <span data-ttu-id="8d54d-111">**プロジェクト**メニューの  **SSIS インポートおよびエクスポート ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="8d54d-111">From the **Project** menu, select **SSIS Import and Export Wizard**.</span></span> <span data-ttu-id="8d54d-112">これは、SQL Server インポートおよびエクスポート ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-112">This starts the SQL Server Import and Export Wizard.</span></span>  
  
3.  <span data-ttu-id="8d54d-113">[ようこそ] 画面で、情報を参照し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="8d54d-113">Read the information on the Welcome screen, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="8d54d-114">**データ ソースを選択** ダイアログ ボックスから、**データ ソース**ドロップ ダウン リスト **.NET Framework Data Provider 用 Siebel eBusiness Applications**です。</span><span class="sxs-lookup"><span data-stu-id="8d54d-114">In the **Choose a Data Source** dialog box, from the **Data Source** drop-down list **.NET Framework Data Provider for Siebel eBusiness Applications**.</span></span> <span data-ttu-id="8d54d-115">さまざまな接続のプロパティの値を指定、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]接続文字列。</span><span class="sxs-lookup"><span data-stu-id="8d54d-115">Specify values for the different connection properties for the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] connection string.</span></span> <span data-ttu-id="8d54d-116">接続文字列プロパティの詳細については、次を参照してください。 [Siebel 接続文字列のデータ プロバイダーのプロパティ](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md)です。</span><span class="sxs-lookup"><span data-stu-id="8d54d-116">For more information about the connection string properties, see [Data provider properties for the Siebel connection string](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md).</span></span>  
  
     <span data-ttu-id="8d54d-117">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d54d-117">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="8d54d-118">**先選択** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="8d54d-118">In the **Choose a Destination** dialog box:</span></span>  
  
    1.  <span data-ttu-id="8d54d-119">**先**ドロップダウン リストで、 **SQL Native Client**です。</span><span class="sxs-lookup"><span data-stu-id="8d54d-119">From the **Destination** drop-down list, select **SQL Native Client**.</span></span>  
  
    2.  <span data-ttu-id="8d54d-120">**サーバー名**ドロップダウン リストで、SQL Server 名を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-120">From the **Server name** drop-down list, select a SQL Server name.</span></span>  
  
    3.  <span data-ttu-id="8d54d-121">認証モードを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-121">Select an authentication mode.</span></span>  
  
    4.  <span data-ttu-id="8d54d-122">**データベース**ドロップダウン リストで、Siebel テーブルをインポートするデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-122">From the **Database** drop-down list, select the database to which you want to import the Siebel table.</span></span>  
  
    5.  <span data-ttu-id="8d54d-123">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d54d-123">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="8d54d-124">**テーブルのコピーを指定またはクエリ** ダイアログ ボックスで、選択、**を転送するデータを指定するクエリを記述**オプション。</span><span class="sxs-lookup"><span data-stu-id="8d54d-124">In the **Specify Table Copy or Query** dialog box, choose the **Write a query to specify the data to transfer** option.</span></span>  
  
7.  <span data-ttu-id="8d54d-125">**ソース クエリを指定する** ダイアログ ボックスで、SQL Server にインポートするデータをフィルター選択クエリを指定します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-125">In the **Provide a Source Query** dialog box, specify a SELECT query to filter the data to be imported into the SQL Server.</span></span> <span data-ttu-id="8d54d-126">クエリを SELECT の文法の詳細については、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]を参照してください[Siebel の SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)です。</span><span class="sxs-lookup"><span data-stu-id="8d54d-126">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], see [Syntax for a SELECT Statement in Siebel](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md).</span></span>  
  
8.  <span data-ttu-id="8d54d-127">クエリを検証するには、をクリックして、**解析**ボタンをクリックし**OK**をクリックしてポップアップ ダイアログ ボックスで、 **[次へ]** です。</span><span class="sxs-lookup"><span data-stu-id="8d54d-127">To validate the query, click the **Parse** button, click **OK** in the pop-up dialog box, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="8d54d-128">**[ソース テーブルおよびビュー** ] ダイアログ ボックスで、ソース テーブルと対象テーブルに対してチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8d54d-128">In the **Select Source Tables and Views** dialog box, select the check box against the source and destination tables.</span></span> <span data-ttu-id="8d54d-129">ソースは、Siebel からデータを取得するように指定したクエリを示します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-129">The source is the query you specified to retrieve data from Siebel.</span></span> <span data-ttu-id="8d54d-130">変換先は、SQL Server データベースに作成されるテーブルになります。</span><span class="sxs-lookup"><span data-stu-id="8d54d-130">The destination will be the table that will be created in the SQL Server database.</span></span>  
  
10. <span data-ttu-id="8d54d-131">ウィザードでは、テーブルのフィールド、ソースと移行先の既定のマッピングを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-131">The wizard creates a default mapping between the source and destination table fields.</span></span> <span data-ttu-id="8d54d-132">ただし、要件に従って、マッピングを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="8d54d-132">However, you can change the mappings according to your requirement.</span></span> <span data-ttu-id="8d54d-133">フィールド マッピングを変更する をクリックして**マッピングの編集**です。</span><span class="sxs-lookup"><span data-stu-id="8d54d-133">To change the field mappings, click **Edit Mappings**.</span></span>  
  
11. <span data-ttu-id="8d54d-134">**列マッピング**ダイアログ ボックスで、することができます。</span><span class="sxs-lookup"><span data-stu-id="8d54d-134">In the **Column Mappings** dialog box, you can:</span></span>  
  
    -   <span data-ttu-id="8d54d-135">変換先テーブル内の列の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-135">Change the names of columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="8d54d-136">変換先テーブル内の特定の列を無視します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-136">Ignore certain columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="8d54d-137">コピー先のテーブル内のフィールドのデータ型を変更します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-137">Change the data type for fields in destination table.</span></span>  
  
    -   <span data-ttu-id="8d54d-138">Nullable、サイズ、有効桁数、小数点以下桁数などその他のフィールドの属性を変更します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-138">Change other field attributes such as nullable, size, precision, and scale.</span></span>  
  
    -   <span data-ttu-id="8d54d-139">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d54d-139">Click **OK**.</span></span>  
  
     <span data-ttu-id="8d54d-140">![Siebel テーブルと SQL テーブル間の列マッピング](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")</span><span class="sxs-lookup"><span data-stu-id="8d54d-140">![Column mappings between Siebel and SQL table](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")</span></span>  
  
12. <span data-ttu-id="8d54d-141">**ソース テーブルおよびビュー**ダイアログ ボックスで、をクリックして**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="8d54d-141">In the **Select Source Tables and Views** dialog box, click **Next**.</span></span>  
  
13. <span data-ttu-id="8d54d-142">**ウィザードを完了** ダイアログ ボックスで、ウィザードを実行し、をクリックする操作の概要を確認**完了**です。</span><span class="sxs-lookup"><span data-stu-id="8d54d-142">In the **Complete the Wizard** dialog box, review the summary of actions that the wizard will perform, and then click **Finish**.</span></span>  
  
14. <span data-ttu-id="8d54d-143">**操作の実行**Siebel から SQL Server データベース テーブルに情報をインポートするタスクを実行してダイアログ ボックスで、ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-143">In the **Performing Operations** dialog box, the wizard starts executing tasks to import the information from Siebel into a SQL Server database table.</span></span> <span data-ttu-id="8d54d-144">各タスクの状態は、ウィザードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d54d-144">The status for each task is displayed in the wizard.</span></span>  
  
15. <span data-ttu-id="8d54d-145">すべてのタスクが正常に実行される、クリックして**閉じる**です。</span><span class="sxs-lookup"><span data-stu-id="8d54d-145">After all the tasks are successfully executed, click **Close**.</span></span> <span data-ttu-id="8d54d-146">タスクが失敗した場合、対応するエラー メッセージを参照してください、問題を修正、ウィザードを再実行します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-146">If a task fails, see the corresponding error message, fix the issue, and rerun the wizard.</span></span>  
  
16. <span data-ttu-id="8d54d-147">ウィザードでは、統合サービス プロジェクトに、SSIS パッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-147">The wizard adds an SSIS package to your Integration Service project.</span></span> <span data-ttu-id="8d54d-148">統合サービス プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-148">Save the Integration Service project.</span></span>  
  
## <a name="run-the-ssis-package"></a><span data-ttu-id="8d54d-149">SSIS パッケージを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-149">Run the SSIS Package</span></span>  
 <span data-ttu-id="8d54d-150">統合サービス プロジェクト内で、パッケージが作成されると、Siebel システムから SQL Server データベースにデータをインポートすることを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8d54d-150">Once the package is created within an Integration Service project, you can execute it to import data from a Siebel system into a SQL Server database.</span></span> <span data-ttu-id="8d54d-151">パッケージを実行して Siebel データをインポートするのには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-151">Perform the following steps to import Siebel data by executing the package.</span></span>  
  
1.  <span data-ttu-id="8d54d-152">ソリューション エクスプ ローラーで SSIS パッケージに移動します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-152">Navigate to the SSIS package in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="8d54d-153">パッケージ名を右クリックし、**パッケージ実行**です。</span><span class="sxs-lookup"><span data-stu-id="8d54d-153">Right-click the package name, and then select **Execute Package**.</span></span>  
  
<span data-ttu-id="8d54d-154">[Integration Services (SSIS) パッケージの実行](https://docs.microsoft.com/sql/integration-services/packages/run-integration-services-ssis-packages)詳細な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-154">[Run Integration Services (SSIS) Packages](https://docs.microsoft.com/sql/integration-services/packages/run-integration-services-ssis-packages) provides more info.</span></span> 
  
## <a name="verify-the-results"></a><span data-ttu-id="8d54d-155">結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-155">Verify the Results</span></span>  
 <span data-ttu-id="8d54d-156">パッケージを実行すると、SQL Server にログオンし、Siebel データのインポート先となるデータベースに移動することによって結果を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d54d-156">After executing the package, you must verify the results by logging on to the SQL Server and navigating to the database to which the Siebel data is imported.</span></span> <span data-ttu-id="8d54d-157">パッケージを実行する必要がありますテーブルを作成したコピー先データベースにします。</span><span class="sxs-lookup"><span data-stu-id="8d54d-157">Executing the package should have created a table in the destination database.</span></span> <span data-ttu-id="8d54d-158">このテーブルは、Siebel テーブルからの値に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d54d-158">This table should be populated with the values from the Siebel table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d54d-159">参照</span><span class="sxs-lookup"><span data-stu-id="8d54d-159">See Also</span></span>  
 [<span data-ttu-id="8d54d-160">Siebel と SSIS のデータ プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="8d54d-160">Use the Data Provider for Siebel with SSIS</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-data-provider-for-siebel-with-ssis.md)