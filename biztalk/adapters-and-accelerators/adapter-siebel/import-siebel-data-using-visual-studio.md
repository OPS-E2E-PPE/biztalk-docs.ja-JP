---
title: Visual Studio を使用して Siebel データのインポート |Microsoft Docs
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
ms.openlocfilehash: 3d631c461c876ef4066e497d7d72d2e5fe13d022
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978035"
---
# <a name="import-siebel-data-using-visual-studio"></a><span data-ttu-id="942b2-102">Visual Studio を使用して Siebel データをインポートします。</span><span class="sxs-lookup"><span data-stu-id="942b2-102">Import Siebel Data Using Visual Studio</span></span>
<span data-ttu-id="942b2-103">このセクションでは、Microsoft を使用する方法についての情報を提供します。 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] Siebel システムから SQL Server データベースにデータをインポートします。</span><span class="sxs-lookup"><span data-stu-id="942b2-103">This section provides information about how to use Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to import data from a Siebel system into a SQL Server database.</span></span> <span data-ttu-id="942b2-104">また、作成し、このデータをインポートする SSIS パッケージを実行する方法の手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="942b2-104">It also provides instructions on how to create and execute an SSIS package to import this data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="942b2-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="942b2-105">Prerequisites</span></span>  
 <span data-ttu-id="942b2-106">このトピックで説明する手順を実行する前に確認します。</span><span class="sxs-lookup"><span data-stu-id="942b2-106">Before performing the procedures provided in this topic, make sure:</span></span>  
  
- <span data-ttu-id="942b2-107">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]コンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="942b2-107">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] is installed on the computer.</span></span>  
  
- <span data-ttu-id="942b2-108">Microsoft Visual Studio は、コンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="942b2-108">Microsoft Visual Studio is installed on the computer.</span></span>  
  
## <a name="import-in-visual-studio"></a><span data-ttu-id="942b2-109">Visual Studio でのインポート</span><span class="sxs-lookup"><span data-stu-id="942b2-109">Import in Visual Studio</span></span>  
 
1. <span data-ttu-id="942b2-110">開始[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]との統合サービス プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="942b2-110">Start [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and create an Integration Service project.</span></span>  
  
2. <span data-ttu-id="942b2-111">**プロジェクト**メニューの  **SSIS インポートおよびエクスポート ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="942b2-111">From the **Project** menu, select **SSIS Import and Export Wizard**.</span></span> <span data-ttu-id="942b2-112">これは、SQL Server インポートおよびエクスポート ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="942b2-112">This starts the SQL Server Import and Export Wizard.</span></span>  
  
3. <span data-ttu-id="942b2-113">クリックして、ようこそ画面の情報を読み取る**次**します。</span><span class="sxs-lookup"><span data-stu-id="942b2-113">Read the information on the Welcome screen, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="942b2-114">**データ ソースの選択** ダイアログ ボックスから、**データ ソース**ドロップダウン リスト**Siebel eBusiness Applications の .NET Framework Data Provider**します。</span><span class="sxs-lookup"><span data-stu-id="942b2-114">In the **Choose a Data Source** dialog box, from the **Data Source** drop-down list **.NET Framework Data Provider for Siebel eBusiness Applications**.</span></span> <span data-ttu-id="942b2-115">さまざまな接続のプロパティの値を指定、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]接続文字列。</span><span class="sxs-lookup"><span data-stu-id="942b2-115">Specify values for the different connection properties for the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] connection string.</span></span> <span data-ttu-id="942b2-116">接続文字列プロパティの詳細については、次を参照してください。 [Siebel 接続文字列のデータ プロバイダー プロパティ](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md)します。</span><span class="sxs-lookup"><span data-stu-id="942b2-116">For more information about the connection string properties, see [Data provider properties for the Siebel connection string](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md).</span></span>  
  
    <span data-ttu-id="942b2-117">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="942b2-117">Click **Next**.</span></span>  
  
5. <span data-ttu-id="942b2-118">**変換先の選択** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="942b2-118">In the **Choose a Destination** dialog box:</span></span>  
  
   1.  <span data-ttu-id="942b2-119">**先**ドロップダウン リストで、 **SQL Native Client**します。</span><span class="sxs-lookup"><span data-stu-id="942b2-119">From the **Destination** drop-down list, select **SQL Native Client**.</span></span>  
  
   2.  <span data-ttu-id="942b2-120">**サーバー名**ドロップダウン リストで、SQL Server 名を選択します。</span><span class="sxs-lookup"><span data-stu-id="942b2-120">From the **Server name** drop-down list, select a SQL Server name.</span></span>  
  
   3.  <span data-ttu-id="942b2-121">認証モードを選択します。</span><span class="sxs-lookup"><span data-stu-id="942b2-121">Select an authentication mode.</span></span>  
  
   4.  <span data-ttu-id="942b2-122">**データベース**ドロップダウン リストで、Siebel テーブルをインポートするデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="942b2-122">From the **Database** drop-down list, select the database to which you want to import the Siebel table.</span></span>  
  
   5.  <span data-ttu-id="942b2-123">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="942b2-123">Click **Next**.</span></span>  
  
6. <span data-ttu-id="942b2-124">**指定のテーブルのコピーまたはクエリ** ダイアログ ボックスで、選択、**を転送するデータを指定するクエリを記述**オプション。</span><span class="sxs-lookup"><span data-stu-id="942b2-124">In the **Specify Table Copy or Query** dialog box, choose the **Write a query to specify the data to transfer** option.</span></span>  
  
7. <span data-ttu-id="942b2-125">**ソース クエリの指定** ダイアログ ボックスで、SQL Server にインポートするデータをフィルター選択クエリを指定します。</span><span class="sxs-lookup"><span data-stu-id="942b2-125">In the **Provide a Source Query** dialog box, specify a SELECT query to filter the data to be imported into the SQL Server.</span></span> <span data-ttu-id="942b2-126">クエリの SELECT、文法の詳細については、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]を参照してください[Siebel の SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)します。</span><span class="sxs-lookup"><span data-stu-id="942b2-126">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], see [Syntax for a SELECT Statement in Siebel](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md).</span></span>  
  
8. <span data-ttu-id="942b2-127">クエリを検証するには、次のようにクリックします。、**解析**ボタンをクリック**OK**でクリックしてポップアップ ダイアログ ボックスで、 **[次へ]**。</span><span class="sxs-lookup"><span data-stu-id="942b2-127">To validate the query, click the **Parse** button, click **OK** in the pop-up dialog box, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="942b2-128">**選択元のテーブルおよびビュー**  ダイアログ ボックスで、ソースと変換先のテーブルに対してチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="942b2-128">In the **Select Source Tables and Views** dialog box, select the check box against the source and destination tables.</span></span> <span data-ttu-id="942b2-129">ソースは、Siebel からデータを取得する指定したクエリです。</span><span class="sxs-lookup"><span data-stu-id="942b2-129">The source is the query you specified to retrieve data from Siebel.</span></span> <span data-ttu-id="942b2-130">変換先は、SQL Server データベースに作成されるテーブルになります。</span><span class="sxs-lookup"><span data-stu-id="942b2-130">The destination will be the table that will be created in the SQL Server database.</span></span>  
  
10. <span data-ttu-id="942b2-131">ウィザードは、ソースと宛先の間の既定のマッピング テーブルのフィールドを作成します。</span><span class="sxs-lookup"><span data-stu-id="942b2-131">The wizard creates a default mapping between the source and destination table fields.</span></span> <span data-ttu-id="942b2-132">ただし、要件に従って、マッピングを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="942b2-132">However, you can change the mappings according to your requirement.</span></span> <span data-ttu-id="942b2-133">フィールド マッピングを変更するには、クリックして**マッピングの編集**します。</span><span class="sxs-lookup"><span data-stu-id="942b2-133">To change the field mappings, click **Edit Mappings**.</span></span>  
  
11. <span data-ttu-id="942b2-134">**列マッピング** ダイアログ ボックスができます。</span><span class="sxs-lookup"><span data-stu-id="942b2-134">In the **Column Mappings** dialog box, you can:</span></span>  
  
    - <span data-ttu-id="942b2-135">変換先テーブル内の列の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="942b2-135">Change the names of columns in the destination table.</span></span>  
  
    - <span data-ttu-id="942b2-136">変換先テーブルで特定の列を無視します。</span><span class="sxs-lookup"><span data-stu-id="942b2-136">Ignore certain columns in the destination table.</span></span>  
  
    - <span data-ttu-id="942b2-137">変換先テーブル内のフィールドのデータ型を変更します。</span><span class="sxs-lookup"><span data-stu-id="942b2-137">Change the data type for fields in destination table.</span></span>  
  
    - <span data-ttu-id="942b2-138">Null 許容型のサイズ、有効桁数、およびスケールなどの他のフィールドの属性を変更します。</span><span class="sxs-lookup"><span data-stu-id="942b2-138">Change other field attributes such as nullable, size, precision, and scale.</span></span>  
  
    - <span data-ttu-id="942b2-139">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="942b2-139">Click **OK**.</span></span>  
  
      <span data-ttu-id="942b2-140">![Siebel および SQL テーブル間の列マッピング](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")</span><span class="sxs-lookup"><span data-stu-id="942b2-140">![Column mappings between Siebel and SQL table](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")</span></span>  
  
12. <span data-ttu-id="942b2-141">**選択元のテーブルおよびビュー**ダイアログ ボックスで、をクリックして**次**。</span><span class="sxs-lookup"><span data-stu-id="942b2-141">In the **Select Source Tables and Views** dialog box, click **Next**.</span></span>  
  
13. <span data-ttu-id="942b2-142">**ウィザードを完了**] ダイアログ ボックスで、ウィザードを実行し、[アクションの概要を確認**完了**します。</span><span class="sxs-lookup"><span data-stu-id="942b2-142">In the **Complete the Wizard** dialog box, review the summary of actions that the wizard will perform, and then click **Finish**.</span></span>  
  
14. <span data-ttu-id="942b2-143">**操作の実行**Siebel から SQL Server データベースのテーブルに情報をインポートするタスクの実行 ダイアログ ボックスで、ウィザードが起動します。</span><span class="sxs-lookup"><span data-stu-id="942b2-143">In the **Performing Operations** dialog box, the wizard starts executing tasks to import the information from Siebel into a SQL Server database table.</span></span> <span data-ttu-id="942b2-144">ウィザードでは、各タスクの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="942b2-144">The status for each task is displayed in the wizard.</span></span>  
  
15. <span data-ttu-id="942b2-145">すべてのタスクが正常に実行される、クリックして**閉じる**します。</span><span class="sxs-lookup"><span data-stu-id="942b2-145">After all the tasks are successfully executed, click **Close**.</span></span> <span data-ttu-id="942b2-146">タスクが失敗した場合、対応するエラー メッセージが表示、問題を解決し、ウィザードを再実行します。</span><span class="sxs-lookup"><span data-stu-id="942b2-146">If a task fails, see the corresponding error message, fix the issue, and rerun the wizard.</span></span>  
  
16. <span data-ttu-id="942b2-147">ウィザードでは、統合サービス プロジェクトに、SSIS パッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="942b2-147">The wizard adds an SSIS package to your Integration Service project.</span></span> <span data-ttu-id="942b2-148">統合サービス プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="942b2-148">Save the Integration Service project.</span></span>  
  
## <a name="run-the-ssis-package"></a><span data-ttu-id="942b2-149">SSIS パッケージを実行します。</span><span class="sxs-lookup"><span data-stu-id="942b2-149">Run the SSIS Package</span></span>  
 <span data-ttu-id="942b2-150">統合サービス プロジェクトでは、パッケージが作成されたら、Siebel システムから SQL Server データベースにデータをインポートすることを実行できます。</span><span class="sxs-lookup"><span data-stu-id="942b2-150">Once the package is created within an Integration Service project, you can execute it to import data from a Siebel system into a SQL Server database.</span></span> <span data-ttu-id="942b2-151">パッケージを実行して Siebel データをインポートするのには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="942b2-151">Perform the following steps to import Siebel data by executing the package.</span></span>  
  
1.  <span data-ttu-id="942b2-152">ソリューション エクスプ ローラーで SSIS パッケージに移動します。</span><span class="sxs-lookup"><span data-stu-id="942b2-152">Navigate to the SSIS package in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="942b2-153">パッケージ名を右クリックし、**パッケージ実行**します。</span><span class="sxs-lookup"><span data-stu-id="942b2-153">Right-click the package name, and then select **Execute Package**.</span></span>  
  
<span data-ttu-id="942b2-154">[Integration Services (SSIS) パッケージを実行する](https://docs.microsoft.com/sql/integration-services/packages/run-integration-services-ssis-packages)詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="942b2-154">[Run Integration Services (SSIS) Packages](https://docs.microsoft.com/sql/integration-services/packages/run-integration-services-ssis-packages) provides more info.</span></span> 
  
## <a name="verify-the-results"></a><span data-ttu-id="942b2-155">結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="942b2-155">Verify the Results</span></span>  
 <span data-ttu-id="942b2-156">パッケージを実行した後は、SQL Server にログオンしている、Siebel データをインポートするデータベースに移動して結果を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="942b2-156">After executing the package, you must verify the results by logging on to the SQL Server and navigating to the database to which the Siebel data is imported.</span></span> <span data-ttu-id="942b2-157">パッケージを実行する必要がありますのテーブルを作成、転送先データベース。</span><span class="sxs-lookup"><span data-stu-id="942b2-157">Executing the package should have created a table in the destination database.</span></span> <span data-ttu-id="942b2-158">このテーブル Siebel テーブルから値を持つデータを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="942b2-158">This table should be populated with the values from the Siebel table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="942b2-159">参照</span><span class="sxs-lookup"><span data-stu-id="942b2-159">See Also</span></span>  
 [<span data-ttu-id="942b2-160">Data Provider for Siebel を SSIS と一緒に使用する</span><span class="sxs-lookup"><span data-stu-id="942b2-160">Use the Data Provider for Siebel with SSIS</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-data-provider-for-siebel-with-ssis.md)