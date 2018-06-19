---
title: 挿入、更新、削除、または WCF サービス モデルを使用して Oracle データベースで操作の選択 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, Delete operation
- WCF service model, Select operation
- WCF service model, Insert operation
- WCF service model, Update operation
ms.assetid: d1a9f44f-ea0b-4dd6-9489-fa0d963848c4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f312f0fa967c08fabbc27c9269abaae68b9ac958
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217490"
---
# <a name="insert-update-delete-or-select-operations-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="6f09e-102">挿入、更新、削除、または WCF サービス モデルを使用して Oracle データベースで操作の選択</span><span class="sxs-lookup"><span data-stu-id="6f09e-102">Insert, update, delete, or select operations in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="6f09e-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]基本的な Insert、Update、Delete、および Oracle データベースのテーブルおよびビューに対する Select 操作のセットを表示します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces a set of basic Insert, Update, Delete, and Select operations on Oracle database tables and views.</span></span> <span data-ttu-id="6f09e-104">これらの操作を使用すると、単純な SQL INSERT、UPDATE、SELECT を実行し、対象のテーブルまたはビューの WHERE 句で修飾されたステートメントを削除できます。</span><span class="sxs-lookup"><span data-stu-id="6f09e-104">By using these operations, you can perform simple SQL INSERT, UPDATE, SELECT, and DELETE statements qualified by a WHERE clause on a target table or view.</span></span> <span data-ttu-id="6f09e-105">たとえば、SQL SELECT クエリを結合演算子を使用して、複雑な操作を実行するには、SQLEXECUTE 操作を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="6f09e-105">To perform more complex operations, for example a SQL SELECT query that uses the JOIN operator, you can use the SQLEXECUTE operation.</span></span> <span data-ttu-id="6f09e-106">SQLEXECUTE 操作の詳細については、次を参照してください。 [WCF サービス モデルを使用して Oracle データベース SQLEXECUTE 操作を実行する](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-106">For more information about the SQLEXECUTE operation, see [Performing a SQLEXECUTE Operation in Oracle Database Using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
 <span data-ttu-id="6f09e-107">次の表に、SQL の基本的な操作を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]テーブルとビューを表示します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-107">The following table summarizes the basic SQL operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces on tables and views.</span></span> <span data-ttu-id="6f09e-108">これらの操作の詳細については、次を参照してください。 [、基本的な Insert、Update、Delete、およびテーブルおよびビューに対する選択操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-108">For a complete description of these operations, see [Message Schemas for the Basic Insert, Update, Delete, and Select Operations on Tables and Views](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).</span></span>  
  
|<span data-ttu-id="6f09e-109">操作</span><span class="sxs-lookup"><span data-stu-id="6f09e-109">Operation</span></span>|<span data-ttu-id="6f09e-110">Description</span><span class="sxs-lookup"><span data-stu-id="6f09e-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6f09e-111">Insert</span><span class="sxs-lookup"><span data-stu-id="6f09e-111">Insert</span></span>|<span data-ttu-id="6f09e-112">挿入操作では、対象のテーブルまたはビューに複数のレコードまたは一括挿入をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6f09e-112">The Insert operation supports multiple record or bulk inserts into the target table or view:</span></span><br /><br /> <span data-ttu-id="6f09e-113">は、複数のレコードの挿入操作は、テーブルまたは指定されたレコード セットに基づいたビューに行を挿入します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-113">-   A multiple record Insert operation inserts rows into a table or view based on a supplied record set.</span></span><br /><span data-ttu-id="6f09e-114">は、一括挿入操作は、テーブルまたはビューのリストに基づく指定された SQL SELECT クエリと列に行を挿入します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-114">-   A bulk Insert operation inserts rows into a table or view based on a supplied SQL SELECT query and column list.</span></span> <span data-ttu-id="6f09e-115">クエリから返されるレコードは、列リストに基づく対象のテーブルに挿入されます。</span><span class="sxs-lookup"><span data-stu-id="6f09e-115">The records that the query returns are inserted into the target table based on the column list.</span></span>|  
|<span data-ttu-id="6f09e-116">Select</span><span class="sxs-lookup"><span data-stu-id="6f09e-116">Select</span></span>|<span data-ttu-id="6f09e-117">指定された列名と SQL の WHERE 句を指定するフィルター文字列の一覧に基づいて、対象テーブルでの SQL SELECT クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-117">Performs a SQL SELECT query on the target table based on a supplied list of column names and a filter string that specifies a SQL WHERE clause.</span></span>|  
|<span data-ttu-id="6f09e-118">Update</span><span class="sxs-lookup"><span data-stu-id="6f09e-118">Update</span></span>|<span data-ttu-id="6f09e-119">対象のテーブルの更新プログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-119">Performs an UPDATE on the target table.</span></span> <span data-ttu-id="6f09e-120">更新するレコードは、SQL の WHERE 句を指定するフィルター文字列によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="6f09e-120">The records to be updated are specified by a filter string that specifies a SQL WHERE clause.</span></span> <span data-ttu-id="6f09e-121">更新プログラムの値は、テンプレートのレコードで指定されます。</span><span class="sxs-lookup"><span data-stu-id="6f09e-121">The values for the update are specified in a template record.</span></span>|  
|<span data-ttu-id="6f09e-122">DELETE</span><span class="sxs-lookup"><span data-stu-id="6f09e-122">Delete</span></span>|<span data-ttu-id="6f09e-123">SQL の WHERE 句に基づいてフィルター文字列で指定されている対象のテーブルに対して DELETE を実行します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-123">Performs a DELETE on the target table based on a SQL WHERE clause that is specified in a filter string.</span></span>|  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="6f09e-124">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="6f09e-124">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="6f09e-125">このトピックの例では、/SCOTT/ACCOUNTACTIVITY テーブルを使用します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-125">The examples in this topic use the /SCOTT/ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="6f09e-126">このテーブルを生成するスクリプトは、SDK サンプルの値が提供されます。</span><span class="sxs-lookup"><span data-stu-id="6f09e-126">A script to generate this table is supplied with the SDK samples.</span></span> <span data-ttu-id="6f09e-127">SDK サンプルの詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-127">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="6f09e-128">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="6f09e-128">The WCF Client Class</span></span>  
 <span data-ttu-id="6f09e-129">基本的な SQL 操作の生成、WCF クライアントの名前を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェスは、テーブルまたは次の表のように、ビューの名前に基づきます。</span><span class="sxs-lookup"><span data-stu-id="6f09e-129">The name of the WCF client generated for the basic SQL operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces is based on the name of the table or view, as in the following table.</span></span>  
  
|<span data-ttu-id="6f09e-130">Oracle データベース アイテム</span><span class="sxs-lookup"><span data-stu-id="6f09e-130">Oracle Database Artifact</span></span>|<span data-ttu-id="6f09e-131">WCF クライアント名</span><span class="sxs-lookup"><span data-stu-id="6f09e-131">WCF Client Name</span></span>|  
|------------------------------|---------------------|  
|<span data-ttu-id="6f09e-132">テーブル</span><span class="sxs-lookup"><span data-stu-id="6f09e-132">Table</span></span>|<span data-ttu-id="6f09e-133">[スキーマ]テーブル [TABLE_NAME] クライアント</span><span class="sxs-lookup"><span data-stu-id="6f09e-133">[SCHEMA]Table[TABLE_NAME]Client</span></span>|  
|<span data-ttu-id="6f09e-134">表示</span><span class="sxs-lookup"><span data-stu-id="6f09e-134">View</span></span>|<span data-ttu-id="6f09e-135">[スキーマ]ビュー [VIEW_NAME] クライアント</span><span class="sxs-lookup"><span data-stu-id="6f09e-135">[SCHEMA]View[VIEW_NAME]Client</span></span>|  
  
 <span data-ttu-id="6f09e-136">[スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-136">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="6f09e-137">[TABLE_NAME] テーブルの名前を =たとえば、ACCOUNTACTIVITY です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-137">[TABLE_NAME] = The name of the table; for example, ACCOUNTACTIVITY.</span></span>  
  
 <span data-ttu-id="6f09e-138">[VIEW_NAME] ビューの名前を = です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-138">[VIEW_NAME] = The name of the view.</span></span>  
  
 <span data-ttu-id="6f09e-139">次の表は、テーブルの基本的な SQL 操作のメソッドのシグニチャを示します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-139">The following table shows the method signatures for the basic SQL operations on a table.</span></span> <span data-ttu-id="6f09e-140">署名は、ビューの名前空間と名前のテーブルを置換する点を除いて、表示は、同じです。</span><span class="sxs-lookup"><span data-stu-id="6f09e-140">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="6f09e-141">操作</span><span class="sxs-lookup"><span data-stu-id="6f09e-141">Operation</span></span>|<span data-ttu-id="6f09e-142">メソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="6f09e-142">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="6f09e-143">Insert</span><span class="sxs-lookup"><span data-stu-id="6f09e-143">Insert</span></span>|<span data-ttu-id="6f09e-144">挿入長い ([TABLE_NS]. [TABLE_NAME] RECORDINSERT [RECORDSET、それらを文字列クエリの文字列) です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-144">long Insert([TABLE_NS].[TABLE_NAME]RECORDINSERT[] RECORDSET, string COLUMN_NAMES, string QUERY);</span></span>|  
|<span data-ttu-id="6f09e-145">Select</span><span class="sxs-lookup"><span data-stu-id="6f09e-145">Select</span></span>|<span data-ttu-id="6f09e-146">[TABLE_NS] です。[TABLE_NAME]RECORDSELECT を選択 (それら、フィルターの文字列の文字列) です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-146">[TABLE_NS].[TABLE_NAME]RECORDSELECT[] Select(string COLUMN_NAMES, string FILTER);</span></span>|  
|<span data-ttu-id="6f09e-147">Update</span><span class="sxs-lookup"><span data-stu-id="6f09e-147">Update</span></span>|<span data-ttu-id="6f09e-148">時間を更新 ([TABLE_NS]. [TABLE_NAME] RECORDUPDATE レコード セットをフィルターの文字列) です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-148">long Update([TABLE_NS].[TABLE_NAME]RECORDUPDATE RECORDSET, string FILTER);</span></span>|  
|<span data-ttu-id="6f09e-149">DELETE</span><span class="sxs-lookup"><span data-stu-id="6f09e-149">Delete</span></span>|<span data-ttu-id="6f09e-150">長い Delete (フィルターの文字列) です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-150">Long Delete(string FILTER);</span></span>|  
  
 <span data-ttu-id="6f09e-151">[TABLE_NS] テーブルの名前空間の名前を =たとえば、microsoft.lobservices.oracledb._2007._03.SCOTT です。Table.ACCOUNTACTIVITY です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-151">[TABLE_NS] = The name of the table namespace; for example, microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.</span></span>  
  
 <span data-ttu-id="6f09e-152">[TABLE_NAME] テーブルの名前を =たとえば、ACCOUNTACTIVITY です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-152">[TABLE_NAME] = The name of the table; for example, ACCOUNTACTIVITY.</span></span>  
  
 <span data-ttu-id="6f09e-153">Insert、Update、および Select 操作で使用されるレコードの種類は、すべてが、テーブルで定義されているまたは名前空間を表示します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-153">The record types used by the Insert, Update, and Select operations are all defined in the table or view namespace.</span></span>  
  
 <span data-ttu-id="6f09e-154">SCOTT/ACCOUNTACTIVITY テーブルでの操作、Delete、Insert、Select および Update の次のコードに示す WCF クライアント クラスのメソッド シグネチャが生成されます。</span><span class="sxs-lookup"><span data-stu-id="6f09e-154">The following code shows the method signatures for a WCF client class generated for the Delete, Insert, Select and Update operations on the /SCOTT/ACCOUNTACTIVITY table.</span></span>  
  
```  
public partial class SCOTTTableACCOUNTACTIVITYClient : System.ServiceModel.ClientBase<SCOTTTableACCOUNTACTIVITY>, SCOTTTableACCOUNTACTIVITY {  
  
    public long Delete(string FILTER);  
  
    public long Insert(microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT[] RECORDSET, string COLUMN_NAMES, string QUERY);  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDSELECT[] Select(string COLUMN_NAMES, string FILTER);  
  
    public long Update(microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDUPDATE RECORDSET, string FILTER);  
}  
```  
  
## <a name="invoking-the-basic-sql-operations"></a><span data-ttu-id="6f09e-155">基本的な SQL の操作を呼び出す</span><span class="sxs-lookup"><span data-stu-id="6f09e-155">Invoking the Basic SQL Operations</span></span>  
 <span data-ttu-id="6f09e-156">WCF クライアントを使用して、テーブルまたはビューの基本的な SQL 操作を呼び出すには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-156">To invoke the basic SQL operations on a table or view by using a WCF client, perform the following steps.</span></span>  
  
1.  <span data-ttu-id="6f09e-157">対象のテーブルまたはビューの WCF クライアント クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-157">Generate a WCF client class for the target table or view.</span></span> <span data-ttu-id="6f09e-158">このクラスは、ターゲットの成果物に呼び出すことができる操作のメソッドを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f09e-158">This class should contain methods for the operations that you will invoke on the target artifact.</span></span>  
  
2.  <span data-ttu-id="6f09e-159">WCF クライアント クラスのインスタンスを作成し、テーブルまたはビューに対する操作を実行するには、そのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-159">Create an instance of the WCF client class and invoke its methods to perform operations on the table or view.</span></span>  
  
 <span data-ttu-id="6f09e-160">詳細については、WCF クライアント クラスを作成し、に対して操作を呼び出す方法については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle データベース アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-160">For more detailed information about how to create a WCF client class and invoke operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Overview of the WCF Service Model with the Oracle Database Adapter](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md).</span></span>  
  
 <span data-ttu-id="6f09e-161">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースで、トランザクション内で各操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-161">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] executes each operation inside of a transaction on the Oracle database.</span></span> <span data-ttu-id="6f09e-162">このトランザクションの分離レベルを設定して制御することができます、 **TransactionIsolationLevel**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="6f09e-162">You can control the isolation level of this transaction by setting the **TransactionIsolationLevel** binding property.</span></span> <span data-ttu-id="6f09e-163">詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドのプロパティを参照してください[BizTalk Adapter 用 Oracle Database バインド プロパティの操作](https://msdn.microsoft.com/library/dd788467.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-163">For more information about the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] binding properties, see [Working with BizTalk Adapter for Oracle Database Binding Properties](https://msdn.microsoft.com/library/dd788467.aspx).</span></span>  
  
 <span data-ttu-id="6f09e-164">次のセクションでは、コード内の各基本 SQL 操作を呼び出す方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-164">The following sections provide details about how to invoke each basic SQL operation in your code.</span></span>  
  
###  <a name="BKMK_InsertOperation"></a><span data-ttu-id="6f09e-165">挿入操作</span><span class="sxs-lookup"><span data-stu-id="6f09e-165">Insert Operation</span></span>  
 <span data-ttu-id="6f09e-166">次の表は、複数のレコード挿入のパラメーターを設定し、一括挿入操作する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-166">The following table shows how to set parameters for multiple record Insert and bulk Insert operations.</span></span>  
  
|<span data-ttu-id="6f09e-167">挿入操作の種類</span><span class="sxs-lookup"><span data-stu-id="6f09e-167">Insert operation type</span></span>|<span data-ttu-id="6f09e-168">レコード セット</span><span class="sxs-lookup"><span data-stu-id="6f09e-168">RECORDSET</span></span>|<span data-ttu-id="6f09e-169">それら</span><span class="sxs-lookup"><span data-stu-id="6f09e-169">COLUMN_NAMES</span></span>|<span data-ttu-id="6f09e-170">QUERY</span><span class="sxs-lookup"><span data-stu-id="6f09e-170">QUERY</span></span>|  
|---------------------------|---------------|-------------------|-----------|  
|<span data-ttu-id="6f09e-171">複数のレコード</span><span class="sxs-lookup"><span data-stu-id="6f09e-171">Multiple record</span></span>|<span data-ttu-id="6f09e-172">ターゲットに挿入する必要がある INSERTRECORDS のコレクション。</span><span class="sxs-lookup"><span data-stu-id="6f09e-172">A collection of INSERTRECORDS that should be inserted into the target.</span></span>|<span data-ttu-id="6f09e-173">null</span><span class="sxs-lookup"><span data-stu-id="6f09e-173">null</span></span>|<span data-ttu-id="6f09e-174">null</span><span class="sxs-lookup"><span data-stu-id="6f09e-174">null</span></span>|  
|<span data-ttu-id="6f09e-175">一括</span><span class="sxs-lookup"><span data-stu-id="6f09e-175">Bulk</span></span>|<span data-ttu-id="6f09e-176">null</span><span class="sxs-lookup"><span data-stu-id="6f09e-176">null</span></span>|<span data-ttu-id="6f09e-177">ターゲット内の列名のコンマ区切りの一覧たとえば、「TID, アカウント」です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-177">A comma-delimited list of column names in the target; for example, "TID, ACCOUNT".</span></span> <span data-ttu-id="6f09e-178">列の一覧では、これには、挿入された行ごとに、クエリの結果を配置する列を指定します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-178">The column list specifies the columns into which the query results should be placed in each inserted row.</span></span> <span data-ttu-id="6f09e-179">クエリでは、数と型の両方で列リストで指定された列に一致する結果セットを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f09e-179">The query must return a result set that matches the columns specified in the column list in both number and type.</span></span>|<span data-ttu-id="6f09e-180">データベース テーブルまたはビューをターゲットに挿入する、結果セットを返します上の SQL SELECT クエリたとえば、"NEW_TRANSACTIONS WHERE アカウントから選択 (TID、アカウント) = 100001"です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-180">A SQL SELECT query on a database table or view that returns a result set to insert into the target; for example, "SELECT (TID, ACCOUNT) FROM NEW_TRANSACTIONS WHERE ACCOUNT = 100001".</span></span> <span data-ttu-id="6f09e-181">結果セットは、数と型の両方で列リストと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f09e-181">The result set must match the column list in both number and type.</span></span>|  
  
 <span data-ttu-id="6f09e-182">挿入操作では、ターゲットに挿入されたレコードの数を返します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-182">The Insert operation returns the number of records inserted into the target.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6f09e-183">WCF サービス モデルでは、挿入操作で使用されるレコード セットは、厳密に型指定されたです。</span><span class="sxs-lookup"><span data-stu-id="6f09e-183">In the WCF service model, the record set used in the Insert operation is strongly-typed.</span></span> <span data-ttu-id="6f09e-184">Nillable 列の値を設定することができます**null** ; の挿入操作からその列を除外するレコードにただし、値は設定できません、nillable ではない列の**null**です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-184">You can set the value of a nillable column to **null** in a record to exclude that column from the Insert operation; however, you cannot set the value of a non-nillable column to **null**.</span></span> <span data-ttu-id="6f09e-185">つまり、複数のレコードの挿入操作、各レコードのすべての非 nillable 列の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f09e-185">This means that in a multiple record Insert operation, you must supply values for all non-nillable columns in each record.</span></span> <span data-ttu-id="6f09e-186">さらは基本的な SQL 操作のストリーミング サポート、WCF サービス モデルを使用する場合です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-186">In addition, there is no streaming support for the basic SQL operations when you use the WCF service model.</span></span> <span data-ttu-id="6f09e-187">複数のレコードの挿入操作には、大量のレコード セットが含まれている場合、重要な考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="6f09e-187">If your multiple record Insert operation involves a large record set, this may be an important consideration.</span></span> <span data-ttu-id="6f09e-188">詳細については、次を参照してください。 [WCF サービス モデルを使用して基本的な SQL 操作の呼び出しの制限事項](#BKMK_LimitationsInvoking)です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-188">For more information, see [Limitations of Invoking the Basic SQL Operations by Using the WCF Service Model](#BKMK_LimitationsInvoking).</span></span>  
  
 <span data-ttu-id="6f09e-189">次のコードは、複数レコードの挿入操作 (2 つのレコード) を ACCOUNTACTIVITY テーブルを対象とするを示します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-189">The following code shows a multiple record Insert operation (two records) that targets the ACCOUNTACTIVITY table.</span></span>  
  
```  
// Insert records  
                using (SCOTTTableACCOUNTACTIVITYClient aaTableClient =   
                    new SCOTTTableACCOUNTACTIVITYClient("OracleDBBinding_SCOTT.Table.ACCOUNTACTIVITY"))  
                {  
                    long recsInserted;  
  
                    aaTableClient.ClientCredentials.UserName.UserName = "SCOTT";  
                    aaTableClient.ClientCredentials.UserName.Password = "TIGER";  
  
                    try  
                    {  
                        aaTableClient.Open();  
                    }  
                    catch (Exception ex)  
                    {  
                        // handle exception  
                        Console.WriteLine("Exception: " + ex.Message);  
                        throw;  
                    }  
  
                    // Do a multiple record Insert of 2 records for account 100001  
  
                    microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT[] insertRecs =  
                        new microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT[2];  
  
                                  TID__COMPLEX_TYPE tid = new TID__COMPLEX_TYPE();  
                                  tid.InlineValue = "tidSequence.NextVal()";  
  
                                  ACCOUNT__COMPLEX_TYPE account = new ACCOUNT__COMPLEX_TYPE();  
                                  account.Value = 100001;  
  
                    AMOUNT__COMPLEX_TYPE amount = new AMOUNT__COMPLEX_TYPE();  
                    amount.Value = 400;  
  
                    TRANSDATE__COMPLEX_TYPE transdate = new TRANSDATE__COMPLEX_TYPE();  
                    transdate.Value = DateTime.Now.Date;  
  
                    PROCESSED__COMPLEX_TYPE processed = new PROCESSED__COMPLEX_TYPE();  
                    processed.Value = "n";  
  
                    DESCRIPTION__COMPLEX_TYPE description1 = new DESCRIPTION__COMPLEX_TYPE();  
                    description1.Value = "Inserted Record #1";  
  
                    DESCRIPTION__COMPLEX_TYPE description2 = new DESCRIPTION__COMPLEX_TYPE();  
                    description2.Value = "Inserted Record #2";  
  
                    insertRecs[0] =   
                        new microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT();  
                    insertRecs[0].TID = tid;  
                    insertRecs[0].ACCOUNT = account;  
                    insertRecs[0].AMOUNT = amount;  
                    insertRecs[0].TRANSDATE = transdate;  
                    insertRecs[0].DESCRIPTION = description1;  
                    insertRecs[0].PROCESSED = processed;  
  
                    insertRecs[1] =   
                        new microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT();  
                    insertRecs[1].TID = tid;  
                    insertRecs[1].ACCOUNT = account;  
                    insertRecs[1].AMOUNT = amount;  
                    insertRecs[1].TRANSDATE = transdate;  
                    insertRecs[1].DESCRIPTION = description2;  
                    insertRecs[1].PROCESSED = processed;  
  
                    try  
                    {  
                        recsInserted = aaTableClient.Insert(insertRecs, null, null);  
                    }  
                    catch (Exception ex)  
                    {  
                        // handle exception  
                        Console.WriteLine("Exception: " + ex.Message);  
                        throw;  
                    }  
  
                    Console.WriteLine("Insert Done: {0} records inserted", recsInserted);  
```  
  
### <a name="select-operation"></a><span data-ttu-id="6f09e-190">操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-190">Select Operation</span></span>  
 <span data-ttu-id="6f09e-191">次の表は、Select 操作のパラメーターを示します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-191">The following table shows the parameters for the Select operation.</span></span>  
  
|<span data-ttu-id="6f09e-192">それら</span><span class="sxs-lookup"><span data-stu-id="6f09e-192">COLUMN_NAMES</span></span>|<span data-ttu-id="6f09e-193">FILTER</span><span class="sxs-lookup"><span data-stu-id="6f09e-193">FILTER</span></span>|  
|-------------------|------------|  
|<span data-ttu-id="6f09e-194">ターゲット内の列名のコンマ区切りの一覧たとえば、「TID, アカウント」です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-194">A comma-delimited list of column names in the target; for example, "TID, ACCOUNT".</span></span> <span data-ttu-id="6f09e-195">列の一覧では、結果セットに返される対象の列を指定します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-195">The column list specifies the columns of the target that should be returned in the result set.</span></span> <span data-ttu-id="6f09e-196">列リストで指定されていない列は、返されるレコード セット内の .NET の既定値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6f09e-196">Columns not specified in the column list will be set to their .NET default values in the returned record set.</span></span> <span data-ttu-id="6f09e-197">Nillable 列は、この値は**null**です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-197">For nillable columns, this value is **null**.</span></span>|<span data-ttu-id="6f09e-198">クエリの対象の行を指定する SQL の WHERE 句の内容たとえば、"説明 'Insert レコード 1' を ="です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-198">The contents of a SQL WHERE clause that specifies the target rows of the query; for example, "DESCRIPTION = 'Insert Record #1'".</span></span> <span data-ttu-id="6f09e-199">このパラメーターを設定することができます**null**ターゲットのすべての行を取得します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-199">You can set this parameter to **null** to return all rows of the target.</span></span>|  
  
 <span data-ttu-id="6f09e-200">選択操作は、対象の行の型に基づいて厳密に型指定されたレコード セットを返します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-200">The Select operation returns a strongly-typed record set based on the row type of the target.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6f09e-201">WCF サービス モデルを使用すると、基本的な SQL 操作のストリーミング サポートはありません。</span><span class="sxs-lookup"><span data-stu-id="6f09e-201">There is no streaming support for the basic SQL operations when you use the WCF service model.</span></span> <span data-ttu-id="6f09e-202">クエリでは、大量のレコード セットが返された場合は、WCF チャネル モデルを使用してパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="6f09e-202">If your query returns a large record set, you might be able to improve performance by using the WCF channel model.</span></span> <span data-ttu-id="6f09e-203">詳細については、次を参照してください。 [WCF サービス モデルを使用して基本的な SQL 操作の呼び出しの制限事項](#BKMK_LimitationsInvoking)です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-203">For more information, see [Limitations of Invoking the Basic SQL Operations by Using the WCF Service Model](#BKMK_LimitationsInvoking).</span></span>  
  
 <span data-ttu-id="6f09e-204">次のコードは、ACCOUNTACTIVITY テーブルを対象とする選択操作を示しています。</span><span class="sxs-lookup"><span data-stu-id="6f09e-204">The following code shows a Select operation that targets the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="6f09e-205">返されたレコードは、コンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="6f09e-205">The returned records are written to the console.</span></span>  
  
```  
// Declare a variable to hold the result set  
microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDSELECT[] selectRecords;  
  
// Select all records and write them to the console  
try  
{  
    selectRecords = aaTableClient.Select("*", null);  
}  
catch (Exception ex)  
{  
    // handle exception  
}  
  
Console.WriteLine("ACCOUNTACTIVITY before any operations");  
for (int i = 0; i \< selectRecords.Length; i++)  
{  
    Console.WriteLine("{0}\t{1}\t{2}\t{3}\t{4}", selectRecords[i].TID,  
    selectRecords[i].ACCOUNT,  
    selectRecords[i].AMOUNT,  
    selectRecords[i].TRANSDATE,  
    selectRecords[i].DESCRIPTION);  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="6f09e-206">このコードは、作成、構成、および WCF クライアントのインスタンスを開く手順を省略します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-206">This code omits steps to create, configure, and open the WCF client instance.</span></span> <span data-ttu-id="6f09e-207">次の手順を含む例は、次を参照してください。 [Insert 操作](#BKMK_InsertOperation)です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-207">For an example that includes these steps, see [Insert Operation](#BKMK_InsertOperation).</span></span>  
  
### <a name="update-operation"></a><span data-ttu-id="6f09e-208">更新操作</span><span class="sxs-lookup"><span data-stu-id="6f09e-208">Update Operation</span></span>  
 <span data-ttu-id="6f09e-209">次の表は、更新操作のパラメーターを示します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-209">The following table shows the parameters for the Update operation.</span></span>  
  
|<span data-ttu-id="6f09e-210">レコード セット</span><span class="sxs-lookup"><span data-stu-id="6f09e-210">RECORDSET</span></span>|<span data-ttu-id="6f09e-211">FILTER</span><span class="sxs-lookup"><span data-stu-id="6f09e-211">FILTER</span></span>|  
|---------------|------------|  
|<span data-ttu-id="6f09e-212">ターゲットの行の種類に基づいて厳密に型指定されたテンプレートのレコードです。</span><span class="sxs-lookup"><span data-stu-id="6f09e-212">A strongly-typed template record based on the row type of the target.</span></span> <span data-ttu-id="6f09e-213">テンプレートのレコードでは、特定の行の値の更新を指定します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-213">The template record specifies the update values for the target rows.</span></span> <span data-ttu-id="6f09e-214">Nillable 行列では、特定の行で列を更新できないことを示すために、null 値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6f09e-214">For nillable row columns, you can specify a null value to indicate that the column should not be updated in the target rows.</span></span>|<span data-ttu-id="6f09e-215">ターゲットで更新する行を指定する SQL の WHERE 句の内容です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-215">The contents of a SQL WHERE clause that specifies the rows to be updated in the target.</span></span> <span data-ttu-id="6f09e-216">たとえば、"説明 'Inserted レコード 1' を ="です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-216">For example, "DESCRIPTION= 'Inserted Record #1'".</span></span>|  
  
 <span data-ttu-id="6f09e-217">更新操作では、ターゲットから削除された行の数を返します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-217">The Update operation returns the number of rows deleted from the target.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6f09e-218">WCF サービス モデルでは、更新操作で使用されるテンプレート レコードは、厳密に型指定されたがします。</span><span class="sxs-lookup"><span data-stu-id="6f09e-218">In the WCF service model, the template record used in the Update operation is strongly-typed.</span></span> <span data-ttu-id="6f09e-219">その値を設定して、更新操作からの列を省略するには、列が nillable の場合は、 **null**テンプレート レコードです。 ただし、場合、列は、nillable ではありません必要があります設定するテンプレート レコード内の値。</span><span class="sxs-lookup"><span data-stu-id="6f09e-219">If a column is nillable, you can omit the column from the Update operation by setting its value to **null** in the template record; however, if a column is not nillable, then you must set its value in the template record.</span></span> <span data-ttu-id="6f09e-220">たとえば、列が主キーの場合は、値を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f09e-220">For example, if a column is a primary key, it must contain a value.</span></span> <span data-ttu-id="6f09e-221">詳細については、次を参照してください。 [WCF サービス モデルを使用して基本的な SQL 操作の呼び出しの制限事項](#BKMK_LimitationsInvoking)です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-221">For more information, see [Limitations of Invoking the Basic SQL Operations by Using the WCF Service Model](#BKMK_LimitationsInvoking).</span></span>  
  
 <span data-ttu-id="6f09e-222">次のコードでは、ACCOUNTACTIVITY テーブルを対象とする更新操作を示します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-222">The following code shows an Update operation that targets the ACCOUNTACTIVITY table.</span></span>  
  
```  
long recsUpdated;  
  
...  
  
// Create updated template. The TID, TIME, AMOUNT, and DESCRIPTION fields will be updated  
microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDUPDATE updateRecord =  
    new microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDUPDATE();  
        updateRecord.TID = tidSequence.NextVal();  
        updateRecord.ACCOUNT = null;  
        updateRecord.AMOUNT = 300;  
        updateRecord.TRANSDATE = DateTime.Now.Date;  
        updateRecord.DESCRIPTION = "Updated Record #2";  
        updateRecord.PROCESSED = null;  
  
// Set filter string to specify the target record by using the DESCRIPTION field  
string filter = "DESCRIPTION = 'Inserted Record #2'";  
  
try  
{  
    recsUpdated = aaTableClient.Update(updateRecord, filter);  
}  
catch (Exception ex)  
{  
    // handle exception  
    ...  
}  
  
Console.WriteLine("{0} records updated", recsUpdated);  
```  
  
> [!NOTE]
>  <span data-ttu-id="6f09e-223">このコードは、作成、構成、および WCF クライアントのインスタンスを開く手順を省略します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-223">This code omits steps to create, configure, and open the WCF client instance.</span></span> <span data-ttu-id="6f09e-224">次の手順を含む例は、次を参照してください。 [Insert 操作](#BKMK_InsertOperation)です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-224">For an example that includes these steps, see [Insert Operation](#BKMK_InsertOperation).</span></span>  
  
### <a name="delete-operation"></a><span data-ttu-id="6f09e-225">削除操作</span><span class="sxs-lookup"><span data-stu-id="6f09e-225">Delete Operation</span></span>  
 <span data-ttu-id="6f09e-226">次の表は、削除操作のパラメーターを示します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-226">The following table shows the parameters for the Delete operation.</span></span>  
  
|<span data-ttu-id="6f09e-227">FILTER</span><span class="sxs-lookup"><span data-stu-id="6f09e-227">FILTER</span></span>|  
|------------|  
|<span data-ttu-id="6f09e-228">ターゲットから削除する行を指定する SQL の WHERE 句の内容です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-228">The contents of a SQL WHERE clause that specifies the rows to be deleted from the target.</span></span> <span data-ttu-id="6f09e-229">たとえば、"説明 'Inserted レコード 1' を ="です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-229">For example, "DESCRIPTION= 'Inserted Record #1'".</span></span>|  
  
 <span data-ttu-id="6f09e-230">削除操作では、ターゲットから削除された行の数を返します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-230">The Delete operation returns the number of rows deleted from the target.</span></span> <span data-ttu-id="6f09e-231">次のコードは、ACCOUNTACTIVITY テーブルを対象とする削除操作を示しています。</span><span class="sxs-lookup"><span data-stu-id="6f09e-231">The following code shows a Delete operation that targets the ACCOUNTACTIVITY table.</span></span>  
  
```  
// Set filter string equal to the DESCRIPTION field of the target record  
string filter = "DESCRIPTION = 'Inserted Record #1'";  
  
try  
{  
    recsDeleted = aaTableClient.Delete(filter);  
}  
catch (Exception ex)  
{  
    // handle exception  
  
    ...  
}  
Console.WriteLine("{0} records deleted", recsDeleted);  
```  
  
> [!NOTE]
>  <span data-ttu-id="6f09e-232">このコードは、作成、構成、および WCF クライアントのインスタンスを開く手順を省略します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-232">This code omits steps to create, configure, and open the WCF client instance.</span></span> <span data-ttu-id="6f09e-233">次の手順を含む例については、[挿入操作](#BKMK_InsertOperation)です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-233">For an example that includes these steps, see the [Insert Operation](#BKMK_InsertOperation).</span></span>  
  
##  <a name="BKMK_LimitationsInvoking"></a><span data-ttu-id="6f09e-234">WCF サービス モデルを使用して基本的な SQL 操作を呼び出すことの制限事項</span><span class="sxs-lookup"><span data-stu-id="6f09e-234">Limitations of Invoking the Basic SQL Operations by Using the WCF Service Model</span></span>  
 <span data-ttu-id="6f09e-235">WCF クライアントを使用して SQL の基本的な操作を呼び出すときは、次の制限事項があります。</span><span class="sxs-lookup"><span data-stu-id="6f09e-235">The following limitations exist when you invoke the basic SQL operations by using a WCF client:</span></span>  
  
-   <span data-ttu-id="6f09e-236">**操作を挿入します。**</span><span class="sxs-lookup"><span data-stu-id="6f09e-236">**Insert operation.**</span></span> <span data-ttu-id="6f09e-237">複数のレコード挿入操作で使用されるレコード セット厳密に型指定されたは、そのためにすべての行の列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6f09e-237">The record set used in a multiple record Insert operation is strongly-typed and therefore includes all row columns.</span></span> <span data-ttu-id="6f09e-238">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ことを意味するレコード内で null 値を解釈すること、列は、挿入操作から除外する必要があります。 ただし、null 値に設定することはできませんので nillable 以外の列を除外することはできません。</span><span class="sxs-lookup"><span data-stu-id="6f09e-238">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interprets a null value in a record to mean that the column should be excluded from the Insert operation; however, non-nillable columns cannot be excluded because you cannot set them to a null value.</span></span> <span data-ttu-id="6f09e-239">そのため、複数のレコード挿入操作を実行するときに非 nillable 列の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f09e-239">Therefore, you must specify values for non-nillable columns when you perform a multiple record Insert operation.</span></span>  
  
-   <span data-ttu-id="6f09e-240">**操作を挿入します。**</span><span class="sxs-lookup"><span data-stu-id="6f09e-240">**Insert operation.**</span></span> <span data-ttu-id="6f09e-241">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]解釈、 **DbNull**列が複数のレコード挿入操作から除外されることを意味する nillable のデータ列の値。</span><span class="sxs-lookup"><span data-stu-id="6f09e-241">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interprets a **DbNull** value in a nillable data column to mean that the column should be excluded from a multiple record Insert operation.</span></span> <span data-ttu-id="6f09e-242">つまり nillable 列を設定することはできません**DbNull**複数レコードの Oracle データベースで操作を挿入します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-242">This means that you cannot set a nillable column to **DbNull** on the Oracle database in a multiple record Insert operation.</span></span>  
  
-   <span data-ttu-id="6f09e-243">**操作を挿入します。**</span><span class="sxs-lookup"><span data-stu-id="6f09e-243">**Insert operation.**</span></span> <span data-ttu-id="6f09e-244">大量のレコード セットを含む複数のレコードの挿入操作用のストリーミング サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6f09e-244">There is no streaming support for multiple record insert operations that involve a large record set.</span></span>  
  
-   <span data-ttu-id="6f09e-245">**操作を更新します。**</span><span class="sxs-lookup"><span data-stu-id="6f09e-245">**Update operation.**</span></span> <span data-ttu-id="6f09e-246">更新操作で使用されるテンプレート レコードは厳密に型指定された、そのためにすべての行の列が含まれます</span><span class="sxs-lookup"><span data-stu-id="6f09e-246">The template record used in an Update operation is strongly-typed and therefore includes all row columns.</span></span> <span data-ttu-id="6f09e-247">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ことを意味するには、このレコードに null 値を解釈する、列は、更新操作から除外する必要があります以外の場合は、null 値にできないするために非 nillable 列を除外することはできませんただし、します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-247">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interprets a null value in this record to mean that the column should be excluded from the Update operation; however, non-nillable columns cannot be excluded because you cannot them to a null value.</span></span> <span data-ttu-id="6f09e-248">したがって、更新操作を実行するときに、nillable 以外の列の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f09e-248">Therefore, you must specify values for non-nillable columns when you perform an Update operation.</span></span>  
  
-   <span data-ttu-id="6f09e-249">**操作を更新します。**</span><span class="sxs-lookup"><span data-stu-id="6f09e-249">**Update operation.**</span></span> <span data-ttu-id="6f09e-250">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]解釈、 **DbNull**列を操作から除外することを意味するテンプレート レコードで nillable データ列の値。</span><span class="sxs-lookup"><span data-stu-id="6f09e-250">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interprets a **DbNull** value in a nillable data column in the template record to mean that the column should be excluded from the operation.</span></span> <span data-ttu-id="6f09e-251">つまり nillable 列を設定することはできません**DbNull**更新操作を使用して Oracle データベースでします。</span><span class="sxs-lookup"><span data-stu-id="6f09e-251">This means that you cannot set a nillable column to **DbNull** on the Oracle database by using the Update operation.</span></span>  
  
-   <span data-ttu-id="6f09e-252">**操作を選択します。**</span><span class="sxs-lookup"><span data-stu-id="6f09e-252">**Select operation.**</span></span> <span data-ttu-id="6f09e-253">大量のレコード セットを返す SELECT クエリのストリーミング サポートはありません。</span><span class="sxs-lookup"><span data-stu-id="6f09e-253">There is no streaming support for SELECT queries that return a large record set.</span></span>  
  
 <span data-ttu-id="6f09e-254">これらの制限が課題のシナリオでは、モデルを使用して、WCF チャネルのため、操作を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="6f09e-254">For scenarios where these limitations present challenges, you can invoke the operation by using the WCF channel model because:</span></span>  
  
-   <span data-ttu-id="6f09e-255">WCF チャネル モデルを使用すると、更新、挿入操作から特定のデータ列を除外できます。</span><span class="sxs-lookup"><span data-stu-id="6f09e-255">By using the WCF channel model, you can exclude specific data columns from Update and Insert operations.</span></span>  
  
-   <span data-ttu-id="6f09e-256">基本的な SQL 操作の WCF チャネル モデルはノード レベルのストリーミング サポートを提供、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を公開します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-256">The WCF channel model provides node-level streaming support for the basic SQL operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes.</span></span>  
  
 <span data-ttu-id="6f09e-257">モデルを使用して、WCF チャネルでの詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[開発 Oracle データベースのアプリケーション モデルを使用して、WCF チャネル](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)です。</span><span class="sxs-lookup"><span data-stu-id="6f09e-257">For more information about using the WCF channel model with the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Develop Oracle Database Applications Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f09e-258">参照</span><span class="sxs-lookup"><span data-stu-id="6f09e-258">See Also</span></span>  
 [<span data-ttu-id="6f09e-259">WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="6f09e-259">Develop Oracle Database Applications Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)