---
title: "A4SWIFT データベース内の Bicplus テーブルを管理する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Bank Identifier Code (BIC), Bicplus table
- A4SWIFT database, Bicplus table
- Bicplus table
ms.assetid: a255cdea-5ed4-4481-97f1-8425877a76d6
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a58396a9dd6627f2913da8e3845a99b17cf7698
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="managing-the-bicplus-table-in-the-a4swift-database"></a><span data-ttu-id="76ba2-102">A4SWIFT データベース内の Bicplus テーブルを管理します。</span><span class="sxs-lookup"><span data-stu-id="76ba2-102">Managing the Bicplus Table in the A4SWIFT Database</span></span>
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="76ba2-103">BIC 検証を実行するのにには、BIC エントリのテーブルを使用します。</span><span class="sxs-lookup"><span data-stu-id="76ba2-103"> uses a table of BIC entries to perform BIC validation.</span></span> <span data-ttu-id="76ba2-104">このテーブルがで Bicplus テーブルにすることができます、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースまたはカスタムのデータベース内のテーブルです。</span><span class="sxs-lookup"><span data-stu-id="76ba2-104">This table can be either the Bicplus table in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database or a table in a custom database.</span></span>  
  
 <span data-ttu-id="76ba2-105">このテーブルを管理するには、SWIFT から BIC 値を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76ba2-105">To manage this table, you must populate it with BIC values from SWIFT.</span></span> <span data-ttu-id="76ba2-106">SQL ビューをエクスポートするカスタム データベースを使用する場合もする必要があります、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]カスタム データベースにデータベース。</span><span class="sxs-lookup"><span data-stu-id="76ba2-106">If you use a custom database, you must also export SQL views in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database into the custom database.</span></span>  
  
## <a name="importing-bic-data-from-the-swift-bicplus-database"></a><span data-ttu-id="76ba2-107">SWIFT Bicplus データベースから BIC データのインポート</span><span class="sxs-lookup"><span data-stu-id="76ba2-107">Importing BIC data from the SWIFT Bicplus database</span></span>  
 <span data-ttu-id="76ba2-108">SWIFT から BIC 値を持つ BIC エントリ (既定またはカスタムのテーブル) のテーブルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76ba2-108">You must populate the table of BIC entries (either the default or the custom table) with BIC values from SWIFT.</span></span> <span data-ttu-id="76ba2-109">SWIFT BIC データが使用する[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]スプレッドシートまたは毎月更新される Oracle データベースでします。</span><span class="sxs-lookup"><span data-stu-id="76ba2-109">The SWIFT BIC data is available in an [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] spreadsheet or in an Oracle database that is updated monthly.</span></span> <span data-ttu-id="76ba2-110">SWIFT BIC データに関する詳細についてを参照してください[http://go.microsoft.com/fwlink/?LinkId=27885](http://go.microsoft.com/fwlink/?LinkId=27885)です。</span><span class="sxs-lookup"><span data-stu-id="76ba2-110">For more information about SWIFT BIC data, go to [http://go.microsoft.com/fwlink/?LinkId=27885](http://go.microsoft.com/fwlink/?LinkId=27885).</span></span>  
  
 <span data-ttu-id="76ba2-111">カスタム データベースを使用する場合は、カスタムのデータベースに SWIFT Bicplus データベースから BIC データをエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="76ba2-111">If you use a custom database, you must export BIC data from the SWIFT Bicplus database into the custom database.</span></span> <span data-ttu-id="76ba2-112">しなきゃいけません</span><span class="sxs-lookup"><span data-stu-id="76ba2-112">You must</span></span>  
  
 <span data-ttu-id="76ba2-113">BIC からデータをインポートすることができます[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]スプレッドシートの Bicplus テーブルに SWIFT によって提供される、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースの互換性があるためです。</span><span class="sxs-lookup"><span data-stu-id="76ba2-113">You can import data from the BIC [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] spreadsheet provided by SWIFT into the Bicplus table in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database, because they are compatible.</span></span> <span data-ttu-id="76ba2-114">以外に、SWIFT、スプレッドシートからデータをインポートするかどうかは[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベース、フィールドおよび BIC 列では特に、データベース内の列に SWIFT のスプレッドシートと互換性があるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="76ba2-114">If you import the data from the SWIFT spreadsheet into a non-[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database, make sure that the fields and columns in your database, particularly the BIC column, are compatible with the SWIFT spreadsheet.</span></span>  
  
 <span data-ttu-id="76ba2-115">インポート操作では、SWIFT テーブルでパブリッシュされたコードをコピー先のテーブルを更新するとき、パブリッシュされていない BIC コードは削除されません。</span><span class="sxs-lookup"><span data-stu-id="76ba2-115">The import operation does not remove any unpublished BIC codes when it updates the destination table with the codes published in the SWIFT table.</span></span>  
  
 <span data-ttu-id="76ba2-116">Bicplus テーブルへの変更、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベース ログイン、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]ログ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="76ba2-116">The changes made to the Bicplus table of the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database are logged in the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] log file.</span></span>  
  
#### <a name="to-import-bic-data-from-the-swift-bicplus-database"></a><span data-ttu-id="76ba2-117">SWIFT Bicplus データベースから BIC データをインポートするには</span><span class="sxs-lookup"><span data-stu-id="76ba2-117">To import BIC data from the SWIFT Bicplus database</span></span>  
  
1.  <span data-ttu-id="76ba2-118">をクリックして**開始**、 をポイント**すべてのプログラム**inistalled のバージョンの SQL Server をポイントし、クリックして**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="76ba2-118">Click **Start**, point to **All Programs**, point to the inistalled version of SQL Server, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="76ba2-119">[サーバー] ダイアログ ボックスへの接続でクリックして**接続**です。</span><span class="sxs-lookup"><span data-stu-id="76ba2-119">In the Connect to Server dialog box, click **Connect**.</span></span>  
  
3.  <span data-ttu-id="76ba2-120">Microsoft SQL Server Management Studio ウィンドウで、サーバー ノードを展開し、**データベース**です。</span><span class="sxs-lookup"><span data-stu-id="76ba2-120">In the Microsoft SQL Server Management Studio window, expand your server node, and then **Databases**.</span></span>  
  
4.  <span data-ttu-id="76ba2-121">右クリック**A4SWIFT**、 をポイント**タスク**、クリックして**データのインポート**です。</span><span class="sxs-lookup"><span data-stu-id="76ba2-121">Right-click **A4SWIFT**, point to **Tasks**, and then click **Import Data**.</span></span>  
  
5.  <span data-ttu-id="76ba2-122">SQL Server インポートおよびエクスポート ウィザードへようこそ ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="76ba2-122">On the SQL Server Import and Export Wizard welcome page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="76ba2-123">**データ ソースを選択**ページに SWIFT Bicplus から BIC データをインポートする場合、[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]スプレッドシートで、 **Microsoft Excel**で、**データソース**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="76ba2-123">On the **Choose a Data Source** page, if importing BIC data from the SWIFT Bicplus [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] spreadsheet, select **Microsoft Excel** in the **Data Source** text box.</span></span> <span data-ttu-id="76ba2-124">スプレッドシートの場所を参照して、スプレッドシート内のファイル名を選択、 **Excel ファイル パス**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="76ba2-124">Browse to the location of the spreadsheet, and select the file name of the spreadsheet in the **Excel file path** text box.</span></span> <span data-ttu-id="76ba2-125">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76ba2-125">Click **Next**.</span></span>  
  
     <span data-ttu-id="76ba2-126">Oracle データベースから BIC データをインポートする場合は、選択**Microsoft ODBC Driver for Oracle**で、**データソース**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="76ba2-126">If importing BIC data from the Oracle database, select **Microsoft ODBC Driver for Oracle** in the **Data Source** text box.</span></span> <span data-ttu-id="76ba2-127">Oracle データベースとユーザー名と、そのサーバーに接続し、をクリックし、必要なパスワードを使用してサーバーを入力**次**です。</span><span class="sxs-lookup"><span data-stu-id="76ba2-127">Enter the server with the Oracle database, and the user name and password required to connect to that server, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="76ba2-128">**変換先を選択**ことを確認 ページで、 **Microsoft OLE DB Provider for SQL Server**で入力した、**先**テキスト ボックスで、**使用Windows 認証**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="76ba2-128">On the **Choose a Destination** page, verify that **Microsoft OLE DB Provider for SQL Server** is entered in the **Destination** text box, and that **Use Windows Authentication** is selected.</span></span> <span data-ttu-id="76ba2-129">Bicplus のテーブルを作成する場合、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースであることを確認**A4SWIFT**で入力した、**データベース**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="76ba2-129">If you are populating the Bicplus table in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database, verify that **A4SWIFT** is entered in the **Database** text box.</span></span> <span data-ttu-id="76ba2-130">カスタム データベースを使用している場合は、そのデータベースでの名前を入力、**データベース**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="76ba2-130">If you are using a custom database, enter the name of that database in the **Database** text box.</span></span> <span data-ttu-id="76ba2-131">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76ba2-131">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="76ba2-132">**選択テーブルのコピーまたはクエリ**ことを確認 ページで、 **1 つまたは複数のテーブルまたはビューからデータをコピー**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="76ba2-132">On the **Select Table Copy or Query** page, verify that **Copy data from one or more tables or views** is selected.</span></span> <span data-ttu-id="76ba2-133">選択をデータを指定するクエリを使用する必要がある場合**を転送するデータを指定するクエリを記述**です。</span><span class="sxs-lookup"><span data-stu-id="76ba2-133">If you need to use a query to specify the data, select **Write a query to specify the data to transfer**.</span></span> <span data-ttu-id="76ba2-134">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76ba2-134">Click **Next**.</span></span>  
  
9. <span data-ttu-id="76ba2-135">**[ソース テーブルおよびビュー** ] ページで、をクリックして**Bicplus**で、**ソース**列を選択**Bicplus**で、 **移行先**列、およびクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="76ba2-135">On the **Select Source Tables and Views** page, click **Bicplus** in the **Source** column, select **Bicplus** in the **Destination** column, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="76ba2-136">**を保存してパッケージ実行** ページで、適切なスケジュール情報を入力してをクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="76ba2-136">On the **Save and Execute Package** page, enter the appropriate schedule information, and then click **Next**.</span></span>  
  
11. <span data-ttu-id="76ba2-137">**ウィザードを完了** ページで概要を確認してをクリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="76ba2-137">On the **Complete the Wizard** page, review the summary and then click **Finish**.</span></span>  
  
## <a name="importing-sql-views-from-the-a4swift-database-into-a-custom-database"></a><span data-ttu-id="76ba2-138">カスタム データベース A4SWIFT データベースからの SQL ビューにインポートします。</span><span class="sxs-lookup"><span data-stu-id="76ba2-138">Importing SQL views from the A4SWIFT database into a Custom Database</span></span>  
 <span data-ttu-id="76ba2-139">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]セットアップ プログラムによって、2 つの SQL ビュー、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="76ba2-139">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] setup program installs two SQL views in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database.</span></span> <span data-ttu-id="76ba2-140">1 つのビューは 8 文字 BICs と 11 文字 BICs は、他のです。</span><span class="sxs-lookup"><span data-stu-id="76ba2-140">One view is for eight-character BICs and the other is for 11-character BICs.</span></span>  
  
 <span data-ttu-id="76ba2-141">代わりにカスタム データベースを使用する場合、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベース、カスタムのデータベースにこれらの SQL ビューをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="76ba2-141">If you use a custom database instead of the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database, you must importing these SQL views into the custom database.</span></span> <span data-ttu-id="76ba2-142">クエリ アナライザーで CreateBICViews.sql スクリプトを実行するようにします。</span><span class="sxs-lookup"><span data-stu-id="76ba2-142">You do so by executing the CreateBICViews.sql script in the Query Analyzer.</span></span> <span data-ttu-id="76ba2-143">このスクリプトが\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT/スクリプト。</span><span class="sxs-lookup"><span data-stu-id="76ba2-143">This script is in \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT/Scripts.</span></span>  
  
#### <a name="to-import-sql-views-from-the-a4swift-database-into-a-custom-database"></a><span data-ttu-id="76ba2-144">カスタム データベースに A4SWIFT データベースからの SQL ビューをインポートするには</span><span class="sxs-lookup"><span data-stu-id="76ba2-144">To import SQL views from the A4SWIFT database into a custom database</span></span>  
  
1.  <span data-ttu-id="76ba2-145">Windows エクスプローラで、移動\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\Scripts です。</span><span class="sxs-lookup"><span data-stu-id="76ba2-145">In Windows Explorer, move to \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\Scripts.</span></span> <span data-ttu-id="76ba2-146">ダブルクリックして**CreateBICViews.sql**です。</span><span class="sxs-lookup"><span data-stu-id="76ba2-146">Double-click **CreateBICViews.sql**.</span></span>  
  
2.  <span data-ttu-id="76ba2-147">[サーバー] ダイアログ ボックスへの接続でクリックして**接続**です。</span><span class="sxs-lookup"><span data-stu-id="76ba2-147">In the Connect to Server dialog box, click **Connect**.</span></span>  
  
3.  <span data-ttu-id="76ba2-148">Microsoft SQL Server Management Studio ウィンドウで選択**A4SWIFT**データベース テキスト ボックスにします。</span><span class="sxs-lookup"><span data-stu-id="76ba2-148">In the Microsoft SQL Server Management Studio window, select **A4SWIFT** in the database text box.</span></span>  
  
4.  <span data-ttu-id="76ba2-149">クエリ ウィンドウで BICs を"Bicplus"以外のという名前のテーブルに格納する場合が見つけ**dbo します。Bicplus**ビューで**dbo します。Bic11**、適切なテーブル名に変更します。</span><span class="sxs-lookup"><span data-stu-id="76ba2-149">In the query pane, if you are storing BICs in a table that is named other than "Bicplus", find **dbo.Bicplus** in the view **dbo.Bic11**, and change it to the appropriate table name.</span></span> <span data-ttu-id="76ba2-150">ビューの同じ**dbo します。Bic8**です。</span><span class="sxs-lookup"><span data-stu-id="76ba2-150">Do the same for the view **dbo.Bic8**.</span></span>  
  
5.  <span data-ttu-id="76ba2-151">BICs を"BIC"以外の名前は、列に格納する場合は、検索**BIC**で、**選択**、**場所**、および**ORDER BY**句、および適切な列の名前に変更します。</span><span class="sxs-lookup"><span data-stu-id="76ba2-151">If you are storing BICs in a column that is named other than "BIC", find **BIC** in the **SELECT**, **WHERE**, and **ORDER BY** clauses, and change it to the appropriate column name.</span></span>  
  
6.  <span data-ttu-id="76ba2-152">**[実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76ba2-152">Click **Execute**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76ba2-153">参照</span><span class="sxs-lookup"><span data-stu-id="76ba2-153">See Also</span></span>  
 [<span data-ttu-id="76ba2-154">銀行識別コードの検証の有効化</span><span class="sxs-lookup"><span data-stu-id="76ba2-154">Enabling Validation of Bank Identifier Codes</span></span>](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)