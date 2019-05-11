---
title: A4SWIFT データベース内の Bicplus テーブルを管理する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Bank Identifier Code (BIC), Bicplus table
- A4SWIFT database, Bicplus table
- Bicplus table
ms.assetid: a255cdea-5ed4-4481-97f1-8425877a76d6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f446c2757c4454cce681461bae23bd28ecb151f2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377238"
---
# <a name="managing-the-bicplus-table-in-the-a4swift-database"></a><span data-ttu-id="b8795-102">A4SWIFT データベース内の Bicplus テーブルを管理します。</span><span class="sxs-lookup"><span data-stu-id="b8795-102">Managing the Bicplus Table in the A4SWIFT Database</span></span>
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] <span data-ttu-id="b8795-103">BIC エントリのテーブルを使用すると、BIC 検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="b8795-103">uses a table of BIC entries to perform BIC validation.</span></span> <span data-ttu-id="b8795-104">このテーブルの Bicplus テーブルを指定できます、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースまたはカスタムのデータベース内のテーブル。</span><span class="sxs-lookup"><span data-stu-id="b8795-104">This table can be either the Bicplus table in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database or a table in a custom database.</span></span>  
  
 <span data-ttu-id="b8795-105">このテーブルを管理するには、SWIFT からの BIC 値で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8795-105">To manage this table, you must populate it with BIC values from SWIFT.</span></span> <span data-ttu-id="b8795-106">SQL ビューをエクスポートする必要がありますも、カスタム データベースを使用する場合、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]カスタム データベースへのデータベース。</span><span class="sxs-lookup"><span data-stu-id="b8795-106">If you use a custom database, you must also export SQL views in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database into the custom database.</span></span>  
  
## <a name="importing-bic-data-from-the-swift-bicplus-database"></a><span data-ttu-id="b8795-107">SWIFT Bicplus データベースから BIC データのインポート</span><span class="sxs-lookup"><span data-stu-id="b8795-107">Importing BIC data from the SWIFT Bicplus database</span></span>  
 <span data-ttu-id="b8795-108">SWIFT から BIC 値を持つ BIC エントリ (既定またはカスタムのテーブル) のテーブルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8795-108">You must populate the table of BIC entries (either the default or the custom table) with BIC values from SWIFT.</span></span> <span data-ttu-id="b8795-109">SWIFT BIC データが表示されます、[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]スプレッドシートまたは Oracle データベースは毎月更新されます。</span><span class="sxs-lookup"><span data-stu-id="b8795-109">The SWIFT BIC data is available in an [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] spreadsheet or in an Oracle database that is updated monthly.</span></span> <span data-ttu-id="b8795-110">SWIFT BIC データの詳細についてを参照してください[ http://go.microsoft.com/fwlink/?LinkId=27885](http://go.microsoft.com/fwlink/?LinkId=27885)します。</span><span class="sxs-lookup"><span data-stu-id="b8795-110">For more information about SWIFT BIC data, go to [http://go.microsoft.com/fwlink/?LinkId=27885](http://go.microsoft.com/fwlink/?LinkId=27885).</span></span>  
  
 <span data-ttu-id="b8795-111">カスタム データベースを使用する場合は、カスタムのデータベースに SWIFT Bicplus データベースから BIC データをエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8795-111">If you use a custom database, you must export BIC data from the SWIFT Bicplus database into the custom database.</span></span> <span data-ttu-id="b8795-112">しなきゃいけません</span><span class="sxs-lookup"><span data-stu-id="b8795-112">You must</span></span>  
  
 <span data-ttu-id="b8795-113">データをインポートするには、BIC から[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]スプレッドシート内の Bicplus テーブルに SWIFT によって提供される、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースの互換性があるので。</span><span class="sxs-lookup"><span data-stu-id="b8795-113">You can import data from the BIC [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] spreadsheet provided by SWIFT into the Bicplus table in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database, because they are compatible.</span></span> <span data-ttu-id="b8795-114">以外に、SWIFT スプレッドシートからデータをインポートする[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベース フィールドおよび BIC 列では特に、データベース内の列と SWIFT のスプレッドシートと互換性があるかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b8795-114">If you import the data from the SWIFT spreadsheet into a non-[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database, make sure that the fields and columns in your database, particularly the BIC column, are compatible with the SWIFT spreadsheet.</span></span>  
  
 <span data-ttu-id="b8795-115">インポート操作では、SWIFT テーブルで公開されているコードを変換先テーブルを更新する際、発行されていない BIC コードは削除されません。</span><span class="sxs-lookup"><span data-stu-id="b8795-115">The import operation does not remove any unpublished BIC codes when it updates the destination table with the codes published in the SWIFT table.</span></span>  
  
 <span data-ttu-id="b8795-116">Bicplus テーブルへの変更、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベース ログイン、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]ログ ファイル。</span><span class="sxs-lookup"><span data-stu-id="b8795-116">The changes made to the Bicplus table of the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database are logged in the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] log file.</span></span>  
  
#### <a name="to-import-bic-data-from-the-swift-bicplus-database"></a><span data-ttu-id="b8795-117">SWIFT Bicplus データベースから BIC データをインポートするには</span><span class="sxs-lookup"><span data-stu-id="b8795-117">To import BIC data from the SWIFT Bicplus database</span></span>  
  
1. <span data-ttu-id="b8795-118">をクリックして**開始**、] をポイント**すべてのプログラム**inistalled バージョンの SQL Server の場合をポイントし、[クリックして**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="b8795-118">Click **Start**, point to **All Programs**, point to the inistalled version of SQL Server, and then click **SQL Server Management Studio**.</span></span>  
  
2. <span data-ttu-id="b8795-119">[サーバー] ダイアログ ボックスへの接続、クリックして**Connect**します。</span><span class="sxs-lookup"><span data-stu-id="b8795-119">In the Connect to Server dialog box, click **Connect**.</span></span>  
  
3. <span data-ttu-id="b8795-120">Microsoft SQL Server Management Studio ウィンドウで、サーバー ノードを展開し、**データベース**します。</span><span class="sxs-lookup"><span data-stu-id="b8795-120">In the Microsoft SQL Server Management Studio window, expand your server node, and then **Databases**.</span></span>  
  
4. <span data-ttu-id="b8795-121">右クリック**A4SWIFT**、 をポイント**タスク**、 をクリックし、**データのインポート**します。</span><span class="sxs-lookup"><span data-stu-id="b8795-121">Right-click **A4SWIFT**, point to **Tasks**, and then click **Import Data**.</span></span>  
  
5. <span data-ttu-id="b8795-122">SQL Server インポートおよびエクスポート ウィザードの [ようこそ] ページで、をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="b8795-122">On the SQL Server Import and Export Wizard welcome page, click **Next**.</span></span>  
  
6. <span data-ttu-id="b8795-123">**データ ソースの選択**SWIFT Bicplus から BIC データをインポートする場合、ページ[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]スプレッドシートで、 **Excel**で、**データ ソース**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b8795-123">On the **Choose a Data Source** page, if importing BIC data from the SWIFT Bicplus [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] spreadsheet, select **Microsoft Excel** in the **Data Source** text box.</span></span> <span data-ttu-id="b8795-124">スプレッドシートの場所を参照して、スプレッドシート内のファイル名を選択、 **Excel ファイル パス**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b8795-124">Browse to the location of the spreadsheet, and select the file name of the spreadsheet in the **Excel file path** text box.</span></span> <span data-ttu-id="b8795-125">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8795-125">Click **Next**.</span></span>  
  
    <span data-ttu-id="b8795-126">Oracle データベースから BIC データをインポートする場合は、選択**Microsoft ODBC Driver for Oracle**で、**データソース**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b8795-126">If importing BIC data from the Oracle database, select **Microsoft ODBC Driver for Oracle** in the **Data Source** text box.</span></span> <span data-ttu-id="b8795-127">Oracle データベースとユーザー名と、そのサーバーに接続し、をクリックし、必要なパスワードを使用して、サーバーを入力します。**次**します。</span><span class="sxs-lookup"><span data-stu-id="b8795-127">Enter the server with the Oracle database, and the user name and password required to connect to that server, and then click **Next**.</span></span>  
  
7. <span data-ttu-id="b8795-128">**変換先の選択**ことを確認します ページで、 **Microsoft OLE DB Provider for SQL Server**が入力されて、**先**テキスト ボックスで、**使用Windows 認証**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="b8795-128">On the **Choose a Destination** page, verify that **Microsoft OLE DB Provider for SQL Server** is entered in the **Destination** text box, and that **Use Windows Authentication** is selected.</span></span> <span data-ttu-id="b8795-129">内の Bicplus テーブルを作成する場合、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースであることを確認**A4SWIFT**が入力されて、**データベース**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b8795-129">If you are populating the Bicplus table in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database, verify that **A4SWIFT** is entered in the **Database** text box.</span></span> <span data-ttu-id="b8795-130">カスタム データベースを使用している場合は、そのデータベースの名前を入力、**データベース**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b8795-130">If you are using a custom database, enter the name of that database in the **Database** text box.</span></span> <span data-ttu-id="b8795-131">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8795-131">Click **Next**.</span></span>  
  
8. <span data-ttu-id="b8795-132">**選択テーブルのコピーまたはクエリ**ことを確認します ページで、 **1 つまたは複数のテーブルまたはビューからデータをコピー**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="b8795-132">On the **Select Table Copy or Query** page, verify that **Copy data from one or more tables or views** is selected.</span></span> <span data-ttu-id="b8795-133">データを指定するには、選択クエリを使用する必要がある場合**を転送するデータを指定するクエリを記述**します。</span><span class="sxs-lookup"><span data-stu-id="b8795-133">If you need to use a query to specify the data, select **Write a query to specify the data to transfer**.</span></span> <span data-ttu-id="b8795-134">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8795-134">Click **Next**.</span></span>  
  
9. <span data-ttu-id="b8795-135">**選択元のテーブルおよびビュー** ] ページで [ **Bicplus**で、**ソース**列を選択**Bicplus**で、 **変換先**列、およびクリック**次**します。</span><span class="sxs-lookup"><span data-stu-id="b8795-135">On the **Select Source Tables and Views** page, click **Bicplus** in the **Source** column, select **Bicplus** in the **Destination** column, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="b8795-136">**実行パッケージの保存および** ページで、適切なスケジュール情報を入力してをクリックし、**次**。</span><span class="sxs-lookup"><span data-stu-id="b8795-136">On the **Save and Execute Package** page, enter the appropriate schedule information, and then click **Next**.</span></span>  
  
11. <span data-ttu-id="b8795-137">**ウィザードを完了** ページで概要を確認してクリックして**完了**します。</span><span class="sxs-lookup"><span data-stu-id="b8795-137">On the **Complete the Wizard** page, review the summary and then click **Finish**.</span></span>  
  
## <a name="importing-sql-views-from-the-a4swift-database-into-a-custom-database"></a><span data-ttu-id="b8795-138">カスタム データベース A4SWIFT データベースから SQL ビューにインポートします。</span><span class="sxs-lookup"><span data-stu-id="b8795-138">Importing SQL views from the A4SWIFT database into a Custom Database</span></span>  
 <span data-ttu-id="b8795-139">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]セットアップ プログラムによって 2 つの SQL ビュー、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="b8795-139">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] setup program installs two SQL views in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database.</span></span> <span data-ttu-id="b8795-140">1 つのビューは 8 文字 BICs あり、11 文字 BICs 用、もう一方は。</span><span class="sxs-lookup"><span data-stu-id="b8795-140">One view is for eight-character BICs and the other is for 11-character BICs.</span></span>  
  
 <span data-ttu-id="b8795-141">代わりにカスタム データベースを使用する場合、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベース、カスタム データベースにこれらの SQL ビューをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8795-141">If you use a custom database instead of the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database, you must importing these SQL views into the custom database.</span></span> <span data-ttu-id="b8795-142">クエリ アナライザーで CreateBICViews.sql スクリプトを実行してこれを行います。</span><span class="sxs-lookup"><span data-stu-id="b8795-142">You do so by executing the CreateBICViews.sql script in the Query Analyzer.</span></span> <span data-ttu-id="b8795-143">このスクリプトは\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT/スクリプト。</span><span class="sxs-lookup"><span data-stu-id="b8795-143">This script is in \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT/Scripts.</span></span>  
  
#### <a name="to-import-sql-views-from-the-a4swift-database-into-a-custom-database"></a><span data-ttu-id="b8795-144">A4SWIFT データベースからカスタムのデータベースに SQL ビューをインポートするには</span><span class="sxs-lookup"><span data-stu-id="b8795-144">To import SQL views from the A4SWIFT database into a custom database</span></span>  
  
1.  <span data-ttu-id="b8795-145">Windows エクスプ ローラーで、移動\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\Scripts します。</span><span class="sxs-lookup"><span data-stu-id="b8795-145">In Windows Explorer, move to \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\Scripts.</span></span> <span data-ttu-id="b8795-146">ダブルクリック**CreateBICViews.sql**します。</span><span class="sxs-lookup"><span data-stu-id="b8795-146">Double-click **CreateBICViews.sql**.</span></span>  
  
2.  <span data-ttu-id="b8795-147">[サーバー] ダイアログ ボックスへの接続、クリックして**Connect**します。</span><span class="sxs-lookup"><span data-stu-id="b8795-147">In the Connect to Server dialog box, click **Connect**.</span></span>  
  
3.  <span data-ttu-id="b8795-148">Microsoft SQL Server Management Studio ウィンドウで、次のように選択します。 **A4SWIFT**データベース テキスト ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b8795-148">In the Microsoft SQL Server Management Studio window, select **A4SWIFT** in the database text box.</span></span>  
  
4.  <span data-ttu-id="b8795-149">BICs"Bicplus"以外の名前はテーブル内に格納する場合が検索クエリ ペインで**dbo します。Bicplus**ビューで**dbo します。Bic11**、適切なテーブル名に変更します。</span><span class="sxs-lookup"><span data-stu-id="b8795-149">In the query pane, if you are storing BICs in a table that is named other than "Bicplus", find **dbo.Bicplus** in the view **dbo.Bic11**, and change it to the appropriate table name.</span></span> <span data-ttu-id="b8795-150">ビューの同じ操作を行います**dbo します。Bic8**します。</span><span class="sxs-lookup"><span data-stu-id="b8795-150">Do the same for the view **dbo.Bic8**.</span></span>  
  
5.  <span data-ttu-id="b8795-151">BICs を"BIC"以外の名前は列に格納する場合は、検索**BIC**で、**選択**、**場所**、および**ORDER BY**句、および適切な列の名前に変更します。</span><span class="sxs-lookup"><span data-stu-id="b8795-151">If you are storing BICs in a column that is named other than "BIC", find **BIC** in the **SELECT**, **WHERE**, and **ORDER BY** clauses, and change it to the appropriate column name.</span></span>  
  
6.  <span data-ttu-id="b8795-152">**[実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8795-152">Click **Execute**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8795-153">参照</span><span class="sxs-lookup"><span data-stu-id="b8795-153">See Also</span></span>  
 [<span data-ttu-id="b8795-154">銀行識別コードの検証の有効化</span><span class="sxs-lookup"><span data-stu-id="b8795-154">Enabling Validation of Bank Identifier Codes</span></span>](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)