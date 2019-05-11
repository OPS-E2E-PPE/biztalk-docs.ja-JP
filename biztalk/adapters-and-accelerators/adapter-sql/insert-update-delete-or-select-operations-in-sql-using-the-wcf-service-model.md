---
title: 挿入、更新、削除、または WCF サービス モデルを使用して SQL の操作を選択します |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 340048ad-ce28-4acf-ae4e-f18bdb3b6f47
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed0b353ddfd5a04ba2eafc0205d7d154e2049c33
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369436"
---
# <a name="insert-update-delete-or-select-operations-in-sql-using-the-wcf-service-model"></a><span data-ttu-id="3c0e8-102">挿入、更新、削除、または WCF サービス モデルを使用して SQL の操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-102">Insert, update, delete, or select operations in SQL using the WCF service model</span></span>
<span data-ttu-id="3c0e8-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]一連の SQL Server データベースのテーブルおよびビューに対する Insert、Select、Update、および Delete の基本的な操作を検出します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] discovers a set of basic Insert, Select, Update, and Delete operations on SQL Server database tables and views.</span></span> <span data-ttu-id="3c0e8-104">これらの操作を使用すると、実行の単純な SQL Insert、Select、Update、および Delete ステートメントで Where 修飾対象のテーブルまたはビューの句。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-104">By using these operations, you can perform simple SQL Insert, Select, Update, and Delete statements qualified by a Where clause on a target table or view.</span></span> <span data-ttu-id="3c0e8-105">このトピックでは、WCF サービス モデルを使用してこれらの操作を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-105">This topic provides instructions on how to perform these operations using the WCF service model.</span></span>  
  
 <span data-ttu-id="3c0e8-106">アダプターがこれらの操作をサポートする方法の詳細については、次を参照してください。 [Insert、Update、Delete、およびテーブルとビューを SQL アダプターを使用した操作の選択](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-106">For more information on how the adapter supports these operations, see [Insert, Update, Delete, and Select Operations on Tables and Views with the SQL adapter](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c0e8-107">ユーザー定義型の列を含むテーブルに対して操作を実行している場合ことを確認するを参照してください[テーブルと、SQL アダプターを使用してユーザー定義型を持つビューで操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)アプリケーションの開発を開始する前にします。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-107">If you are performing operation on tables that have columns of user-defined types, make sure you refer to [Operations on Tables and Views with User-Defined Types using the SQL adapter](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) before you start developing your application.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="3c0e8-108">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="3c0e8-108">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="3c0e8-109">このトピックの例では、Employee テーブルに対する操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-109">The example in this topic performs operations on the Employee table.</span></span> <span data-ttu-id="3c0e8-110">サンプルで提供される SQL スクリプトを実行して、従業員テーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-110">The Employee table is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="3c0e8-111">サンプルの詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-111">For more information about samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span> <span data-ttu-id="3c0e8-112">サンプルについては、 **EmployeeBasicOps**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-112">A sample, **EmployeeBasicOps**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="3c0e8-113">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="3c0e8-113">The WCF Client Class</span></span>  
 <span data-ttu-id="3c0e8-114">基本的な SQL 操作に対して生成された WCF クライアントの名前を[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]検出、次の表に示すように、テーブルまたはビューの名前に基づきます。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-114">The name of the WCF client generated for the basic SQL operations that the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] discovers is based on the name of the table or view, as listed in the following table.</span></span>  
  
|<span data-ttu-id="3c0e8-115">SQL Server データベースの成果物</span><span class="sxs-lookup"><span data-stu-id="3c0e8-115">SQL Server Database Artifact</span></span>|<span data-ttu-id="3c0e8-116">WCF クライアント名</span><span class="sxs-lookup"><span data-stu-id="3c0e8-116">WCF Client Name</span></span>|  
|----------------------------------|---------------------|  
|<span data-ttu-id="3c0e8-117">テーブル</span><span class="sxs-lookup"><span data-stu-id="3c0e8-117">Table</span></span>|<span data-ttu-id="3c0e8-118">TableOp_ [Schema] _ [TABLE_NAME] のクライアント</span><span class="sxs-lookup"><span data-stu-id="3c0e8-118">TableOp_[Schema]_[TABLE_NAME]Client</span></span>|  
|<span data-ttu-id="3c0e8-119">表示</span><span class="sxs-lookup"><span data-stu-id="3c0e8-119">View</span></span>|<span data-ttu-id="3c0e8-120">ViewOp_ [Schema] _ [VIEW_NAME] のクライアント</span><span class="sxs-lookup"><span data-stu-id="3c0e8-120">ViewOp_[Schema]_[VIEW_NAME]Client</span></span>|  
  
 <span data-ttu-id="3c0e8-121">[スキーマ] コレクションの SQL Server のアイテム、=たとえば、dbo です。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-121">[SCHEMA] = Collection of SQL Server artifacts; for example, dbo.</span></span>  
  
 <span data-ttu-id="3c0e8-122">[TABLE_NAME] テーブルの名前を =たとえば、従業員です。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-122">[TABLE_NAME] = The name of the table; for example, Employee.</span></span>  
  
 <span data-ttu-id="3c0e8-123">[VIEW_NAME] ビューの名前を =たとえば、Employee_View です。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-123">[VIEW_NAME] = The name of the view; for example, Employee_View.</span></span>  
  
### <a name="method-signature-for-invoking-operations-on-tables"></a><span data-ttu-id="3c0e8-124">テーブルに対する操作を呼び出すためのメソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="3c0e8-124">Method Signature for Invoking Operations on Tables</span></span>  
 <span data-ttu-id="3c0e8-125">次の表では、テーブルに対する基本操作のメソッド シグネチャを示します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-125">The following table shows the method signatures for the basic operations on a table.</span></span> <span data-ttu-id="3c0e8-126">署名は、ビューの名前空間と名前のテーブルを置換する点を除いて表示は、同じです。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-126">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="3c0e8-127">演算</span><span class="sxs-lookup"><span data-stu-id="3c0e8-127">Operation</span></span>|<span data-ttu-id="3c0e8-128">メソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="3c0e8-128">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="3c0e8-129">Insert</span><span class="sxs-lookup"><span data-stu-id="3c0e8-129">Insert</span></span>|<span data-ttu-id="3c0e8-130">long[] Insert([TABLE_NS].[TABLE_NAME][] Rows);</span><span class="sxs-lookup"><span data-stu-id="3c0e8-130">long[] Insert([TABLE_NS].[TABLE_NAME][] Rows);</span></span>|  
|<span data-ttu-id="3c0e8-131">Select</span><span class="sxs-lookup"><span data-stu-id="3c0e8-131">Select</span></span>|<span data-ttu-id="3c0e8-132">[TABLE_NS].[TABLE_NAME][] Select(string COLUMNS, string QUERY);</span><span class="sxs-lookup"><span data-stu-id="3c0e8-132">[TABLE_NS].[TABLE_NAME][] Select(string COLUMNS, string QUERY);</span></span>|  
|<span data-ttu-id="3c0e8-133">更新</span><span class="sxs-lookup"><span data-stu-id="3c0e8-133">Update</span></span>|<span data-ttu-id="3c0e8-134">int Update([TABLE_NS].[TABLE_NAME].RowPair[] Rows);</span><span class="sxs-lookup"><span data-stu-id="3c0e8-134">int Update([TABLE_NS].[TABLE_NAME].RowPair[] Rows);</span></span>|  
|<span data-ttu-id="3c0e8-135">DELETE</span><span class="sxs-lookup"><span data-stu-id="3c0e8-135">Delete</span></span>|<span data-ttu-id="3c0e8-136">int Delete([TABLE_NS].[TABLE_NAME][] Rows);</span><span class="sxs-lookup"><span data-stu-id="3c0e8-136">int Delete([TABLE_NS].[TABLE_NAME][] Rows);</span></span>|  
  
 <span data-ttu-id="3c0e8-137">[TABLE_NS] テーブル、名前空間の名前を =たとえば、schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-137">[TABLE_NS] = The name of the table namespace; for example, schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee.</span></span>  
  
 <span data-ttu-id="3c0e8-138">[TABLE_NAME] テーブルの名前を =たとえば、従業員です。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-138">[TABLE_NAME] = The name of the table; for example, Employee.</span></span>  
  
 <span data-ttu-id="3c0e8-139">例としては、次のコードは、既定値"dbo"スキーマの Employee テーブルに対する Delete、Insert、Select および Update 操作に対して生成された WCF クライアント クラスのメソッド シグネチャを示します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-139">As an example, the following code shows the method signatures for a WCF client class generated for the Delete, Insert, Select and Update operations on the Employee table under the default “dbo” schema.</span></span>  
  
```  
public partial class TableOp_dbo_EmployeeClient : System.ServiceModel.ClientBase<TableOp_dbo_Employee>, TableOp_dbo_Employee {      
    public int Delete(schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Rows);  
  
    public long[] Insert(schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Rows);  
  
    public schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Select(string Columns, string Query);  
  
    public int Update(schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair[] Rows);  
}  
```  
  
 <span data-ttu-id="3c0e8-140">このスニペットで TableOp_dbo_EmployeeClient はによって生成された SqlAdapterBindingClient.cs で WCF クラスの名前、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-140">In this snippet, TableOp_dbo_EmployeeClient is the name of the WCF class in the SqlAdapterBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
### <a name="parameters-for-table-operations"></a><span data-ttu-id="3c0e8-141">テーブル操作のパラメーター</span><span class="sxs-lookup"><span data-stu-id="3c0e8-141">Parameters for Table Operations</span></span>  
 <span data-ttu-id="3c0e8-142">このセクションでは、各テーブルの操作に必要なパラメーターを提供します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-142">This section provides the parameters required by each table operation</span></span>  
  
 <span data-ttu-id="3c0e8-143">**挿入操作**</span><span class="sxs-lookup"><span data-stu-id="3c0e8-143">**Insert Operation**</span></span>  
  
|<span data-ttu-id="3c0e8-144">挿入操作の種類</span><span class="sxs-lookup"><span data-stu-id="3c0e8-144">Insert operation type</span></span>|<span data-ttu-id="3c0e8-145">レコード セット</span><span class="sxs-lookup"><span data-stu-id="3c0e8-145">RECORDSET</span></span>|  
|---------------------------|---------------|  
|<span data-ttu-id="3c0e8-146">複数のレコード</span><span class="sxs-lookup"><span data-stu-id="3c0e8-146">Multiple record</span></span>|<span data-ttu-id="3c0e8-147">テーブルに挿入する必要があります INSERTRECORDS のコレクション。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-147">A collection of INSERTRECORDS that should be inserted into the table.</span></span>|  
  
 <span data-ttu-id="3c0e8-148">挿入操作では、長い形式のデータ型の配列を返し、存在する場合、挿入された行の id 値を格納します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-148">The insert operation returns an array of Long data type and stores the identity values of the inserted rows, if any.</span></span> <span data-ttu-id="3c0e8-149">テーブル内に id 列がない場合、戻り値は NULL です。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-149">If there is no identity column in a table, the return value is NULL.</span></span>  
  
 <span data-ttu-id="3c0e8-150">**操作を選択します。**</span><span class="sxs-lookup"><span data-stu-id="3c0e8-150">**Select Operation**</span></span>  
  
|<span data-ttu-id="3c0e8-151">それら</span><span class="sxs-lookup"><span data-stu-id="3c0e8-151">COLUMN_NAMES</span></span>|<span data-ttu-id="3c0e8-152">QUERY</span><span class="sxs-lookup"><span data-stu-id="3c0e8-152">QUERY</span></span>|  
|-------------------|-----------|  
|<span data-ttu-id="3c0e8-153">は、ターゲット内の列名のコンマ区切りの一覧たとえば、「Employee_ID, 指定」です。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-153">A comma-delimited list of column names in the target; for example, "Employee_ID, Designation".</span></span> <span data-ttu-id="3c0e8-154">列の一覧には、結果セットで返される対象の列を指定します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-154">The column list specifies the columns of the target that should be returned in the result set.</span></span> <span data-ttu-id="3c0e8-155">列リストで指定されていない列は、返されたレコード セット内の .NET の既定値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-155">Columns not specified in the column list will be set to their .NET default values in the returned record set.</span></span> <span data-ttu-id="3c0e8-156">Nillable 列は、この値は**null**します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-156">For nillable columns, this value is **null**.</span></span>|<span data-ttu-id="3c0e8-157">クエリの対象の行を指定する SQL の WHERE 句の内容たとえば、"指定 = 'マネージャー'"です。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-157">The contents of a SQL WHERE clause that specifies the target rows of the query; for example, "Designation = 'Manager'".</span></span> <span data-ttu-id="3c0e8-158">このパラメーターを設定する**null**をターゲットのすべての行を返します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-158">You can set this parameter to **null** to return all rows of the target.</span></span>|  
  
 <span data-ttu-id="3c0e8-159">選択操作の戻り値は、指定された列と対象のテーブルまたはビューから行を含む厳密に型指定された結果セットです。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-159">The return value of the Select operation is a strongly-typed result set that contains the specified columns and rows from the target table or view.</span></span>  
  
 <span data-ttu-id="3c0e8-160">**更新操作**</span><span class="sxs-lookup"><span data-stu-id="3c0e8-160">**Update Operation**</span></span>  
  
|<span data-ttu-id="3c0e8-161">ペアの最初の行</span><span class="sxs-lookup"><span data-stu-id="3c0e8-161">First row of the pair</span></span>|<span data-ttu-id="3c0e8-162">ペアの 2 行目</span><span class="sxs-lookup"><span data-stu-id="3c0e8-162">Second row of the pair</span></span>|  
|---------------------------|----------------------------|  
|<span data-ttu-id="3c0e8-163">ペアが、更新する必要がある新しい値に対応するレコードの最初のレコードは、対応、UPDATE ステートメントの SET 句にします。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-163">The first record of the record pair corresponds to new values that need to be updated, that is, it corresponds to the SET clause of the UPDATE statement.</span></span> <span data-ttu-id="3c0e8-164">使用して設定できます`RowPair.After`します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-164">This can be set using `RowPair.After`.</span></span>|<span data-ttu-id="3c0e8-165">レコードのペアの 2 番目のレコード行の古い値、つまり、UPDATE ステートメントの WHERE 句に対応します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-165">The second record of the record pair corresponds to the old values of the rows, that is, it corresponds to the WHERE clause of the UPDATE statement.</span></span> <span data-ttu-id="3c0e8-166">使用して設定できます`RowPair.Before`します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-166">This can be set using `RowPair.Before`.</span></span>|  
  
 <span data-ttu-id="3c0e8-167">更新操作の戻り値では、Int32 データ型では、更新された行の数を表します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-167">The return value of the Update operation is of Int32 data type, and denotes the number of rows updated.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3c0e8-168">更新する必要のあるレコードを指定するには、中にすべての値が更新されていない場合でも、すべての列の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-168">While specifying the record that has to be updated, you must provide values for all the columns, even if all values are not being updated.</span></span> <span data-ttu-id="3c0e8-169">たとえば場合は、行は 5 つの列を備え、更新操作では、2 つだけの列を更新 RowPair.Before の一部として、すべての 5 つの列値を渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-169">For example, if a row has five columns and the Update operation updates only 2 columns, as part of RowPair.Before, you must pass all the 5 column values.</span></span> <span data-ttu-id="3c0e8-170">ただし、RowPair.After、更新される列のみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-170">However, for RowPair.After, you can specify only the columns that will be updated.</span></span>  
  
 <span data-ttu-id="3c0e8-171">**削除操作**</span><span class="sxs-lookup"><span data-stu-id="3c0e8-171">**Delete Operation**</span></span>  
  
 <span data-ttu-id="3c0e8-172">削除操作はレコードの配列を厳密に型指定の入力として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-172">The Delete operation takes as input a strongly-typed array of records.</span></span> <span data-ttu-id="3c0e8-173">削除操作の戻り値では、Int32 データ型では、削除された行の数を表します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-173">The return value of the Delete operation is of Int32 data type, and denotes the number of rows deleted.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-tables-and-views"></a><span data-ttu-id="3c0e8-174">テーブルおよびビューの操作を呼び出すための WCF クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-174">Creating a WCF Client to Invoke Operations on Tables and Views</span></span>  
 <span data-ttu-id="3c0e8-175">WCF クライアントを使用して SQL Server で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[SQL アダプターを使用した WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-175">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF Service Model with the SQL adapter](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="3c0e8-176">このセクションでは、基本的な Insert、Select、Update、テーブルに対する削除操作を呼び出すための WCF クライアントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-176">This section describes how to create a WCF client to invoke basic Insert, Select, Update, Delete operations on a table.</span></span>  
  
#### <a name="to-create-a-wcf-client-to-perform-operations-on-tables"></a><span data-ttu-id="3c0e8-177">テーブルに対する操作を実行する WCF クライアントを作成するには</span><span class="sxs-lookup"><span data-stu-id="3c0e8-177">To create a WCF client to perform operations on tables</span></span>  
  
1. <span data-ttu-id="3c0e8-178">Visual Studio で Visual c# プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-178">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="3c0e8-179">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-179">For this topic, create a console application.</span></span>  
  
2. <span data-ttu-id="3c0e8-180">Insert、Select、Update、WCF クライアント クラスを生成し、Employee テーブルに対して操作を削除します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-180">Generate the WCF client class for the Insert, Select, Update, and Delete operation on the Employee table.</span></span> <span data-ttu-id="3c0e8-181">WCF クライアント クラスを生成する詳細については、次を参照してください。 [SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-181">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="3c0e8-182">WCF クライアント クラスを生成する前に必ず設定して、 **EnableBizTalkCompatibilityMode**プロパティを false にバインドします。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-182">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3. <span data-ttu-id="3c0e8-183">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`と`Microsoft.ServiceModel.Channels`します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-183">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4. <span data-ttu-id="3c0e8-184">Program.cs ファイルを開き、次のスニペットの説明に従って、クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-184">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
   ```  
  
             TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee");  
   client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
   client.ClientCredentials.UserName.Password = "<Enter password here>";  
   ```  
  
    <span data-ttu-id="3c0e8-185">このスニペットで`TableOp_dbo_EmployeeClient`SqlAdapterBindingClient.cs で定義されている WCF クライアントです。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-185">In this snippet, `TableOp_dbo_EmployeeClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="3c0e8-186">このファイルがによって生成された、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-186">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="3c0e8-187">`SqlAdapterBinding_TableOp_dbo_Employee` クライアント エンドポイント構成の名前を指定され、app.config で定義されます。このファイルがによって生成されても、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティとその他の構成設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-187">`SqlAdapterBinding_TableOp_dbo_Employee` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="3c0e8-188">このスニペットでは、構成ファイルからバインドおよびエンドポイント アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-188">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="3c0e8-189">これらの値は、コードで明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-189">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="3c0e8-190">クライアント バインディングを指定する、さまざまな方法の詳細については、次を参照してください。 [SQL アダプタのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-190">For more information on the different ways of specifying client binding, see [Configure a Client Binding for the SQL Adapter](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
5. <span data-ttu-id="3c0e8-191">次のスニペットで説明されているように、クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-191">Open the client as described in the snippet below:</span></span>  
  
   ```  
   try  
   {  
      Console.WriteLine("Opening Client...");  
      client.Open();  
   }  
   catch (Exception ex)  
   {  
      Console.WriteLine("Exception: " + ex.Message);  
      throw;  
   }  
   ```  
  
6. <span data-ttu-id="3c0e8-192">Employee テーブルに対する挿入操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-192">Invoke the Insert operation on the Employee table.</span></span>  
  
   ```  
   long[] recordsInserted;  
  
   schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] insertRecord =  
   new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[1];  
  
   insertRecord[0] = new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee();  
   insertRecord[0].Name = "John Smith";  
   insertRecord[0].Designation = "Manager";  
   insertRecord[0].Salary = 500000;  
  
   try  
   {  
      Console.WriteLine("Inserting new table entry...");  
      recordsInserted = client.Insert(insertRecord);  
   }  
   catch (Exception ex)  
   {  
      Console.WriteLine("Exception: " + ex.Message);  
      throw;  
   }  
  
   Console.WriteLine("Record inserted");  
   Console.WriteLine("Press any key to continue ...");  
   Console.ReadLine();  
   ```  
  
    <span data-ttu-id="3c0e8-193">Select を実行する前のコード スニペットを置き換えることができます更新、または同様の操作を削除します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-193">You can replace the preceding code snippet to perform Select, Update, or Delete operations as well.</span></span> <span data-ttu-id="3c0e8-194">単一のアプリケーションですべての操作を実行するコード スニペットを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-194">You can also append the code snippets to perform all operation in a single application.</span></span> <span data-ttu-id="3c0e8-195">これらの操作を実行する方法のコード スニペット。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-195">For code snippets on how to perform these operations.</span></span>  
  
7. <span data-ttu-id="3c0e8-196">次のスニペットの説明に従って、クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-196">Close the client as described in the snippet below:</span></span>  
  
   ```  
   client.Close();  
   Console.WriteLine("Press any key to exit...");  
   Console.ReadLine();  
   ```  
  
8. <span data-ttu-id="3c0e8-197">プロジェクトをビルドし、それを実行します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-197">Build the project and then run it.</span></span> <span data-ttu-id="3c0e8-198">アプリケーションでは、Employee テーブルにレコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-198">The application inserts a record in the Employee table.</span></span>  
  
###   <a name="select-operation"></a><span data-ttu-id="3c0e8-199">操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-199">Select Operation</span></span>  
 <span data-ttu-id="3c0e8-200">次のコードでは、Employee テーブルを対象とする操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-200">The following code shows a Select operation that targets the Employee table.</span></span> <span data-ttu-id="3c0e8-201">選択操作では、テーブルに挿入された最後のレコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-201">The Select operation selects the last record inserted into the table.</span></span> <span data-ttu-id="3c0e8-202">返されるレコードは、コンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-202">The returned records are written to the console.</span></span>  
  
```  
schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] selectRecords;  
  
try  
{  
   Console.WriteLine("Selecting Row...");  
   selectRecords = client.Select("*", "where [Employee_ID] = (select IDENT_CURRENT('Employee'))");  
}  
  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
  
Console.WriteLine("The details of the newly added employee are:");  
Console.WriteLine("********************************************");  
for (int i = 0; i < selectRecords.Length; i++)  
{  
   Console.WriteLine("Employee ID        : " + selectRecords[i].Employee_ID);  
   Console.WriteLine("Employee Name      : " + selectRecords[i].Name);  
   Console.WriteLine("Employee Desigation: " + selectRecords[i].Designation);  
   Console.WriteLine();  
}  
Console.WriteLine("********************************************");  
Console.WriteLine("Press any key to continue ...");  
Console.ReadLine();  
```  
  
###   <a name="update-operation"></a><span data-ttu-id="3c0e8-203">更新操作</span><span class="sxs-lookup"><span data-stu-id="3c0e8-203">Update Operation</span></span>  
 <span data-ttu-id="3c0e8-204">次のコードでは、Employee テーブルを対象とする更新操作を示します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-204">The following code shows an Update operation that targets the Employee table.</span></span>  
  
```  
int result;  
  
schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair updateRecordPair =  
   new schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair();  
  
schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee updateRecord =   
   new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee();  
  
schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair[] updateArray =  
   new schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair[1];  
  
updateRecord = insertRecord[0];  
updateRecord.Name = "Jeff Smith";  
  
updateRecordPair.After = updateRecord;  
updateRecordPair.Before = selectRecords[0];  
  
updateArray[0] = updateRecordPair;  
  
try  
{  
   Console.WriteLine("Updating the database...");  
   result = client.Update(updateArray);  
}  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
  
Console.WriteLine("Updated Record for {0}", updateRecordPair.Before.Name);  
Console.WriteLine("The new name for the employee is {0}", updateRecordPair.After.Name);  
Console.WriteLine("Press any key to continue ...");  
Console.ReadLine();  
```  
  
###   <a name="delete-operation"></a><span data-ttu-id="3c0e8-205">削除操作</span><span class="sxs-lookup"><span data-stu-id="3c0e8-205">Delete Operation</span></span>  
 <span data-ttu-id="3c0e8-206">次のコードでは、Employee テーブルを対象とする削除操作を示します。</span><span class="sxs-lookup"><span data-stu-id="3c0e8-206">The following code shows a Delete operation that targets the Employee table.</span></span>  
  
```  
int deleteSuccess;  
  
schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] deleteRecords =  
   new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[1];  
  
deleteRecords = client.Select("*", "where [Employee_ID] = (select IDENT_CURRENT('Employee'))");  
  
Console.WriteLine("Following employees will be deleted from the database:");  
for (int i = 0; i < deleteRecords.Length; i++)  
{  
   Console.WriteLine("Name: {0}", deleteRecords[i].Name);  
}  
Console.WriteLine("Press any key to begin deletion...");  
Console.ReadLine();  
  
try  
{  
   Console.WriteLine("Deleting employee record...");  
   deleteSuccess = client.Delete(deleteRecords);  
}  
  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c0e8-207">参照</span><span class="sxs-lookup"><span data-stu-id="3c0e8-207">See Also</span></span>  
[<span data-ttu-id="3c0e8-208">WCF サービス モデルを使用してアプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="3c0e8-208">Develop applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)