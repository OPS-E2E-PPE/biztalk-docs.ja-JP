---
title: 挿入、更新、削除、または WCF サービス モデルを使用して Oracle データベースで操作を選択します |。Microsoft Docs
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
ms.openlocfilehash: 9544551d19b595c113407fda4736f0d5d48bd5fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376521"
---
# <a name="insert-update-delete-or-select-operations-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="e8cdd-102">挿入、更新、削除、または WCF サービス モデルを使用して Oracle データベースで操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-102">Insert, update, delete, or select operations in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="e8cdd-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]サーフェスの基本的な Insert、Update、Delete、および Oracle データベースのテーブルおよびビューに対する Select 操作のセット。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces a set of basic Insert, Update, Delete, and Select operations on Oracle database tables and views.</span></span> <span data-ttu-id="e8cdd-104">これらの操作を使用すると、単純な SQL INSERT、UPDATE、SELECT を実行し、DELETE ステートメントの対象のテーブルまたはビューの WHERE 句で修飾できます。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-104">By using these operations, you can perform simple SQL INSERT, UPDATE, SELECT, and DELETE statements qualified by a WHERE clause on a target table or view.</span></span> <span data-ttu-id="e8cdd-105">たとえば、SQL SELECT クエリの結合演算子を使用するより複雑な操作を実行するには、SQLEXECUTE 操作を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-105">To perform more complex operations, for example a SQL SELECT query that uses the JOIN operator, you can use the SQLEXECUTE operation.</span></span> <span data-ttu-id="e8cdd-106">SQLEXECUTE 操作の詳細については、次を参照してください。 [WCF サービス モデルを使用して Oracle Database SQLEXECUTE 操作を実行する](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-106">For more information about the SQLEXECUTE operation, see [Performing a SQLEXECUTE Operation in Oracle Database Using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
 <span data-ttu-id="e8cdd-107">次の表は、SQL の基本的な操作をまとめたものですが、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]テーブルとビューのサーフェイス。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-107">The following table summarizes the basic SQL operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces on tables and views.</span></span> <span data-ttu-id="e8cdd-108">これらの操作の詳細については、次を参照してください。 [、基本的な挿入、更新、削除、およびテーブルおよびビューの選択操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-108">For a complete description of these operations, see [Message Schemas for the Basic Insert, Update, Delete, and Select Operations on Tables and Views](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).</span></span>  
  
|<span data-ttu-id="e8cdd-109">演算</span><span class="sxs-lookup"><span data-stu-id="e8cdd-109">Operation</span></span>|<span data-ttu-id="e8cdd-110">説明</span><span class="sxs-lookup"><span data-stu-id="e8cdd-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e8cdd-111">Insert</span><span class="sxs-lookup"><span data-stu-id="e8cdd-111">Insert</span></span>|<span data-ttu-id="e8cdd-112">挿入操作では、対象のテーブルまたはビューに複数のレコードまたは一括挿入をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-112">The Insert operation supports multiple record or bulk inserts into the target table or view:</span></span><br /><br /> <span data-ttu-id="e8cdd-113">-複数のレコードの挿入操作では、テーブルまたは指定されたレコード セットに基づいたビューに行を挿入します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-113">-   A multiple record Insert operation inserts rows into a table or view based on a supplied record set.</span></span><br /><span data-ttu-id="e8cdd-114">-一括挿入操作では、テーブルまたは指定した SQL SELECT クエリ、列リストに基づいたビューに行を挿入します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-114">-   A bulk Insert operation inserts rows into a table or view based on a supplied SQL SELECT query and column list.</span></span> <span data-ttu-id="e8cdd-115">クエリから返されるレコードは、列リストに基づく対象テーブルに挿入されます。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-115">The records that the query returns are inserted into the target table based on the column list.</span></span>|  
|<span data-ttu-id="e8cdd-116">Select</span><span class="sxs-lookup"><span data-stu-id="e8cdd-116">Select</span></span>|<span data-ttu-id="e8cdd-117">指定された列の名前と SQL の WHERE 句を指定するフィルター文字列の一覧に基づく対象テーブルに対して SQL SELECT クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-117">Performs a SQL SELECT query on the target table based on a supplied list of column names and a filter string that specifies a SQL WHERE clause.</span></span>|  
|<span data-ttu-id="e8cdd-118">更新</span><span class="sxs-lookup"><span data-stu-id="e8cdd-118">Update</span></span>|<span data-ttu-id="e8cdd-119">対象テーブルに対して更新プログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-119">Performs an UPDATE on the target table.</span></span> <span data-ttu-id="e8cdd-120">更新するレコードは、SQL の WHERE 句を指定するフィルター文字列によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-120">The records to be updated are specified by a filter string that specifies a SQL WHERE clause.</span></span> <span data-ttu-id="e8cdd-121">更新プログラムの値は、テンプレートのレコードで指定されます。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-121">The values for the update are specified in a template record.</span></span>|  
|<span data-ttu-id="e8cdd-122">DELETE</span><span class="sxs-lookup"><span data-stu-id="e8cdd-122">Delete</span></span>|<span data-ttu-id="e8cdd-123">フィルター文字列で指定されている SQL の WHERE 句に基づいて対象テーブルに対して DELETE を実行します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-123">Performs a DELETE on the target table based on a SQL WHERE clause that is specified in a filter string.</span></span>|  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="e8cdd-124">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="e8cdd-124">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="e8cdd-125">このトピックの例では、/SCOTT/ACCOUNTACTIVITY テーブルを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-125">The examples in this topic use the /SCOTT/ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="e8cdd-126">このテーブルを生成するスクリプトは SDK のサンプルで提供されます。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-126">A script to generate this table is supplied with the SDK samples.</span></span> <span data-ttu-id="e8cdd-127">SDK サンプルの詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-127">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="e8cdd-128">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="e8cdd-128">The WCF Client Class</span></span>  
 <span data-ttu-id="e8cdd-129">基本的な SQL 操作に対して生成された WCF クライアントの名前を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェスは、テーブルまたは次の表のように、ビューの名前に基づきます。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-129">The name of the WCF client generated for the basic SQL operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces is based on the name of the table or view, as in the following table.</span></span>  
  
|<span data-ttu-id="e8cdd-130">Oracle データベース成果物</span><span class="sxs-lookup"><span data-stu-id="e8cdd-130">Oracle Database Artifact</span></span>|<span data-ttu-id="e8cdd-131">WCF クライアント名</span><span class="sxs-lookup"><span data-stu-id="e8cdd-131">WCF Client Name</span></span>|  
|------------------------------|---------------------|  
|<span data-ttu-id="e8cdd-132">テーブル</span><span class="sxs-lookup"><span data-stu-id="e8cdd-132">Table</span></span>|<span data-ttu-id="e8cdd-133">[スキーマ]テーブル [TABLE_NAME] のクライアント</span><span class="sxs-lookup"><span data-stu-id="e8cdd-133">[SCHEMA]Table[TABLE_NAME]Client</span></span>|  
|<span data-ttu-id="e8cdd-134">表示</span><span class="sxs-lookup"><span data-stu-id="e8cdd-134">View</span></span>|<span data-ttu-id="e8cdd-135">[スキーマ]ビュー [VIEW_NAME] クライアント</span><span class="sxs-lookup"><span data-stu-id="e8cdd-135">[SCHEMA]View[VIEW_NAME]Client</span></span>|  
  
 <span data-ttu-id="e8cdd-136">[スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-136">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="e8cdd-137">[TABLE_NAME] テーブルの名前を =たとえば、ACCOUNTACTIVITY です。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-137">[TABLE_NAME] = The name of the table; for example, ACCOUNTACTIVITY.</span></span>  
  
 <span data-ttu-id="e8cdd-138">[VIEW_NAME] ビューの名前を = です。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-138">[VIEW_NAME] = The name of the view.</span></span>  
  
 <span data-ttu-id="e8cdd-139">次の表では、テーブルに対する基本的な SQL 操作のメソッド シグネチャを示します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-139">The following table shows the method signatures for the basic SQL operations on a table.</span></span> <span data-ttu-id="e8cdd-140">署名は、ビューの名前空間と名前のテーブルを置換する点を除いて表示は、同じです。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-140">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="e8cdd-141">演算</span><span class="sxs-lookup"><span data-stu-id="e8cdd-141">Operation</span></span>|<span data-ttu-id="e8cdd-142">メソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="e8cdd-142">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="e8cdd-143">Insert</span><span class="sxs-lookup"><span data-stu-id="e8cdd-143">Insert</span></span>|<span data-ttu-id="e8cdd-144">挿入時間の長い ([TABLE_NS]. [TABLE_NAME] RECORDINSERT [レコード セット、それらをクエリ文字列の文字列)。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-144">long Insert([TABLE_NS].[TABLE_NAME]RECORDINSERT[] RECORDSET, string COLUMN_NAMES, string QUERY);</span></span>|  
|<span data-ttu-id="e8cdd-145">Select</span><span class="sxs-lookup"><span data-stu-id="e8cdd-145">Select</span></span>|<span data-ttu-id="e8cdd-146">[TABLE_NS].[TABLE_NAME]RECORDSELECT[] Select(string COLUMN_NAMES, string FILTER);</span><span class="sxs-lookup"><span data-stu-id="e8cdd-146">[TABLE_NS].[TABLE_NAME]RECORDSELECT[] Select(string COLUMN_NAMES, string FILTER);</span></span>|  
|<span data-ttu-id="e8cdd-147">更新</span><span class="sxs-lookup"><span data-stu-id="e8cdd-147">Update</span></span>|<span data-ttu-id="e8cdd-148">long Update([TABLE_NS].[TABLE_NAME]RECORDUPDATE RECORDSET, string FILTER);</span><span class="sxs-lookup"><span data-stu-id="e8cdd-148">long Update([TABLE_NS].[TABLE_NAME]RECORDUPDATE RECORDSET, string FILTER);</span></span>|  
|<span data-ttu-id="e8cdd-149">DELETE</span><span class="sxs-lookup"><span data-stu-id="e8cdd-149">Delete</span></span>|<span data-ttu-id="e8cdd-150">Long Delete(string FILTER);</span><span class="sxs-lookup"><span data-stu-id="e8cdd-150">Long Delete(string FILTER);</span></span>|  
  
 <span data-ttu-id="e8cdd-151">[TABLE_NS] テーブル、名前空間の名前を =たとえば、microsoft.lobservices.oracledb._2007._03.SCOTT します。Table.ACCOUNTACTIVITY します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-151">[TABLE_NS] = The name of the table namespace; for example, microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.</span></span>  
  
 <span data-ttu-id="e8cdd-152">[TABLE_NAME] テーブルの名前を =たとえば、ACCOUNTACTIVITY です。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-152">[TABLE_NAME] = The name of the table; for example, ACCOUNTACTIVITY.</span></span>  
  
 <span data-ttu-id="e8cdd-153">Insert、Update、および選択操作で使用されるレコードの種類では、すべてが、テーブルで定義されているまたは名前空間を表示します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-153">The record types used by the Insert, Update, and Select operations are all defined in the table or view namespace.</span></span>  
  
 <span data-ttu-id="e8cdd-154">SCOTT/ACCOUNTACTIVITY テーブルに対する操作、Delete、Insert、Select および Update の次のコードに示す WCF クライアント クラスのメソッド シグネチャが生成されます。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-154">The following code shows the method signatures for a WCF client class generated for the Delete, Insert, Select and Update operations on the /SCOTT/ACCOUNTACTIVITY table.</span></span>  
  
```  
public partial class SCOTTTableACCOUNTACTIVITYClient : System.ServiceModel.ClientBase<SCOTTTableACCOUNTACTIVITY>, SCOTTTableACCOUNTACTIVITY {  
  
    public long Delete(string FILTER);  
  
    public long Insert(microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT[] RECORDSET, string COLUMN_NAMES, string QUERY);  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDSELECT[] Select(string COLUMN_NAMES, string FILTER);  
  
    public long Update(microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDUPDATE RECORDSET, string FILTER);  
}  
```  
  
## <a name="invoking-the-basic-sql-operations"></a><span data-ttu-id="e8cdd-155">基本的な SQL の操作を呼び出す</span><span class="sxs-lookup"><span data-stu-id="e8cdd-155">Invoking the Basic SQL Operations</span></span>  
 <span data-ttu-id="e8cdd-156">WCF クライアントを使用してテーブルまたはビューに対する基本的な SQL 操作を呼び出すには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-156">To invoke the basic SQL operations on a table or view by using a WCF client, perform the following steps.</span></span>  
  
1. <span data-ttu-id="e8cdd-157">対象のテーブルまたはビューの WCF クライアント クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-157">Generate a WCF client class for the target table or view.</span></span> <span data-ttu-id="e8cdd-158">このクラスは、対象のアイテムに呼び出す操作のメソッドを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-158">This class should contain methods for the operations that you will invoke on the target artifact.</span></span>  
  
2. <span data-ttu-id="e8cdd-159">WCF クライアント クラスのインスタンスを作成し、テーブルまたはビューに対する操作を実行するには、そのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-159">Create an instance of the WCF client class and invoke its methods to perform operations on the table or view.</span></span>  
  
   <span data-ttu-id="e8cdd-160">WCF クライアント クラスを作成し、操作を呼び出す方法についての詳細、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle データベース アダプターを使用した WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-160">For more detailed information about how to create a WCF client class and invoke operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Overview of the WCF Service Model with the Oracle Database Adapter](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md).</span></span>  
  
   <span data-ttu-id="e8cdd-161">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースで、トランザクション内で各操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-161">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] executes each operation inside of a transaction on the Oracle database.</span></span> <span data-ttu-id="e8cdd-162">このトランザクションの分離レベルを設定して制御することができます、 **TransactionIsolationLevel**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-162">You can control the isolation level of this transaction by setting the **TransactionIsolationLevel** binding property.</span></span> <span data-ttu-id="e8cdd-163">詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドのプロパティを参照してください[BizTalk Adapter for Oracle Database バインド プロパティの操作](https://msdn.microsoft.com/library/dd788467.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-163">For more information about the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] binding properties, see [Working with BizTalk Adapter for Oracle Database Binding Properties](https://msdn.microsoft.com/library/dd788467.aspx).</span></span>  
  
   <span data-ttu-id="e8cdd-164">次のセクションでは、コードで基本的な各 SQL 操作を呼び出す方法の詳細について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-164">The following sections provide details about how to invoke each basic SQL operation in your code.</span></span>  
  
###  <a name="BKMK_InsertOperation"></a> <span data-ttu-id="e8cdd-165">挿入操作</span><span class="sxs-lookup"><span data-stu-id="e8cdd-165">Insert Operation</span></span>  
 <span data-ttu-id="e8cdd-166">次の表では、複数のレコード挿入にパラメーターを設定し、一括挿入操作する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-166">The following table shows how to set parameters for multiple record Insert and bulk Insert operations.</span></span>  
  
|<span data-ttu-id="e8cdd-167">挿入操作の種類</span><span class="sxs-lookup"><span data-stu-id="e8cdd-167">Insert operation type</span></span>|<span data-ttu-id="e8cdd-168">レコード セット</span><span class="sxs-lookup"><span data-stu-id="e8cdd-168">RECORDSET</span></span>|<span data-ttu-id="e8cdd-169">それら</span><span class="sxs-lookup"><span data-stu-id="e8cdd-169">COLUMN_NAMES</span></span>|<span data-ttu-id="e8cdd-170">QUERY</span><span class="sxs-lookup"><span data-stu-id="e8cdd-170">QUERY</span></span>|  
|---------------------------|---------------|-------------------|-----------|  
|<span data-ttu-id="e8cdd-171">複数のレコード</span><span class="sxs-lookup"><span data-stu-id="e8cdd-171">Multiple record</span></span>|<span data-ttu-id="e8cdd-172">ターゲットに挿入する必要があります INSERTRECORDS のコレクション。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-172">A collection of INSERTRECORDS that should be inserted into the target.</span></span>|<span data-ttu-id="e8cdd-173">null</span><span class="sxs-lookup"><span data-stu-id="e8cdd-173">null</span></span>|<span data-ttu-id="e8cdd-174">null</span><span class="sxs-lookup"><span data-stu-id="e8cdd-174">null</span></span>|  
|<span data-ttu-id="e8cdd-175">一括</span><span class="sxs-lookup"><span data-stu-id="e8cdd-175">Bulk</span></span>|<span data-ttu-id="e8cdd-176">null</span><span class="sxs-lookup"><span data-stu-id="e8cdd-176">null</span></span>|<span data-ttu-id="e8cdd-177">は、ターゲット内の列名のコンマ区切りの一覧たとえば、「TID, アカウント」です。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-177">A comma-delimited list of column names in the target; for example, "TID, ACCOUNT".</span></span> <span data-ttu-id="e8cdd-178">列の一覧には、列を挿入された行ごとに、クエリの結果を配置する必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-178">The column list specifies the columns into which the query results should be placed in each inserted row.</span></span> <span data-ttu-id="e8cdd-179">クエリでは、両方の数と種類で列リストで指定された列に一致する結果セットを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-179">The query must return a result set that matches the columns specified in the column list in both number and type.</span></span>|<span data-ttu-id="e8cdd-180">データベース テーブルまたはビューを返す結果セットは、ターゲットに挿入する SQL SELECT クエリたとえば、"NEW_TRANSACTIONS WHERE アカウントから選択する (TID, アカウント) = 100001"。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-180">A SQL SELECT query on a database table or view that returns a result set to insert into the target; for example, "SELECT (TID, ACCOUNT) FROM NEW_TRANSACTIONS WHERE ACCOUNT = 100001".</span></span> <span data-ttu-id="e8cdd-181">結果セットは、両方の数と種類で列リストと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-181">The result set must match the column list in both number and type.</span></span>|  
  
 <span data-ttu-id="e8cdd-182">挿入操作では、ターゲットに挿入されたレコードの数を返します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-182">The Insert operation returns the number of records inserted into the target.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e8cdd-183">WCF サービス モデルでは、挿入操作で使用されるレコード セットは、厳密に型指定されたです。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-183">In the WCF service model, the record set used in the Insert operation is strongly-typed.</span></span> <span data-ttu-id="e8cdd-184">Nillable 列の値を設定する**null**で挿入操作; から列を除外するレコードただしは設定できませんを nillable 以外の列の値**null**します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-184">You can set the value of a nillable column to **null** in a record to exclude that column from the Insert operation; however, you cannot set the value of a non-nillable column to **null**.</span></span> <span data-ttu-id="e8cdd-185">つまり、複数のレコードの挿入操作、各レコード内のすべての非 nillable 列の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-185">This means that in a multiple record Insert operation, you must supply values for all non-nillable columns in each record.</span></span> <span data-ttu-id="e8cdd-186">さらはありません、基本的な SQL 操作のストリーミング サポート、WCF サービス モデルを使用する場合です。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-186">In addition, there is no streaming support for the basic SQL operations when you use the WCF service model.</span></span> <span data-ttu-id="e8cdd-187">場合は、複数のレコードの挿入操作では、大量のレコード セットでは、重要な考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-187">If your multiple record Insert operation involves a large record set, this may be an important consideration.</span></span> <span data-ttu-id="e8cdd-188">詳細については、次を参照してください。 [WCF サービス モデルを使用して基本的な SQL 操作の呼び出しの制限事項](#BKMK_LimitationsInvoking)します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-188">For more information, see [Limitations of Invoking the Basic SQL Operations by Using the WCF Service Model](#BKMK_LimitationsInvoking).</span></span>  
  
 <span data-ttu-id="e8cdd-189">次のコードは、複数レコード挿入の操作 (2 つのレコード) を ACCOUNTACTIVITY テーブルを対象とします。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-189">The following code shows a multiple record Insert operation (two records) that targets the ACCOUNTACTIVITY table.</span></span>  
  
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
  
### <a name="select-operation"></a><span data-ttu-id="e8cdd-190">操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-190">Select Operation</span></span>  
 <span data-ttu-id="e8cdd-191">次の表では、選択操作のパラメーターを示します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-191">The following table shows the parameters for the Select operation.</span></span>  
  
|<span data-ttu-id="e8cdd-192">それら</span><span class="sxs-lookup"><span data-stu-id="e8cdd-192">COLUMN_NAMES</span></span>|<span data-ttu-id="e8cdd-193">FILTER</span><span class="sxs-lookup"><span data-stu-id="e8cdd-193">FILTER</span></span>|  
|-------------------|------------|  
|<span data-ttu-id="e8cdd-194">は、ターゲット内の列名のコンマ区切りの一覧たとえば、「TID, アカウント」です。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-194">A comma-delimited list of column names in the target; for example, "TID, ACCOUNT".</span></span> <span data-ttu-id="e8cdd-195">列の一覧には、結果セットで返される対象の列を指定します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-195">The column list specifies the columns of the target that should be returned in the result set.</span></span> <span data-ttu-id="e8cdd-196">列リストで指定されていない列は、返されたレコード セット内の .NET の既定値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-196">Columns not specified in the column list will be set to their .NET default values in the returned record set.</span></span> <span data-ttu-id="e8cdd-197">Nillable 列は、この値は**null**します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-197">For nillable columns, this value is **null**.</span></span>|<span data-ttu-id="e8cdd-198">クエリの対象の行を指定する SQL の WHERE 句の内容たとえば、"説明 = 'Insert レコード 1'"です。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-198">The contents of a SQL WHERE clause that specifies the target rows of the query; for example, "DESCRIPTION = 'Insert Record #1'".</span></span> <span data-ttu-id="e8cdd-199">このパラメーターを設定する**null**をターゲットのすべての行を返します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-199">You can set this parameter to **null** to return all rows of the target.</span></span>|  
  
 <span data-ttu-id="e8cdd-200">選択操作では、対象の行の型に基づいて厳密に型指定されたレコード セットを返します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-200">The Select operation returns a strongly-typed record set based on the row type of the target.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e8cdd-201">WCF サービス モデルを使用すると、基本的な SQL 操作のストリーミング サポートはありません。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-201">There is no streaming support for the basic SQL operations when you use the WCF service model.</span></span> <span data-ttu-id="e8cdd-202">クエリでは、大量のレコード セットが返された場合は、WCF チャネル モデルを使用してパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-202">If your query returns a large record set, you might be able to improve performance by using the WCF channel model.</span></span> <span data-ttu-id="e8cdd-203">詳細については、次を参照してください。 [WCF サービス モデルを使用して基本的な SQL 操作の呼び出しの制限事項](#BKMK_LimitationsInvoking)します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-203">For more information, see [Limitations of Invoking the Basic SQL Operations by Using the WCF Service Model](#BKMK_LimitationsInvoking).</span></span>  
  
 <span data-ttu-id="e8cdd-204">次のコードでは、ACCOUNTACTIVITY テーブルを対象とする操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-204">The following code shows a Select operation that targets the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="e8cdd-205">返されるレコードは、コンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-205">The returned records are written to the console.</span></span>  
  
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
>  <span data-ttu-id="e8cdd-206">このコードは、作成、構成、および WCF クライアントのインスタンスを開く手順を省略します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-206">This code omits steps to create, configure, and open the WCF client instance.</span></span> <span data-ttu-id="e8cdd-207">次の手順を含む、例では、次を参照してください。[挿入操作](#BKMK_InsertOperation)します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-207">For an example that includes these steps, see [Insert Operation](#BKMK_InsertOperation).</span></span>  
  
### <a name="update-operation"></a><span data-ttu-id="e8cdd-208">更新操作</span><span class="sxs-lookup"><span data-stu-id="e8cdd-208">Update Operation</span></span>  
 <span data-ttu-id="e8cdd-209">次の表では、更新操作のパラメーターを示します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-209">The following table shows the parameters for the Update operation.</span></span>  
  
|<span data-ttu-id="e8cdd-210">レコード セット</span><span class="sxs-lookup"><span data-stu-id="e8cdd-210">RECORDSET</span></span>|<span data-ttu-id="e8cdd-211">FILTER</span><span class="sxs-lookup"><span data-stu-id="e8cdd-211">FILTER</span></span>|  
|---------------|------------|  
|<span data-ttu-id="e8cdd-212">対象の行の型に基づいて厳密に型指定されたテンプレートのレコードです。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-212">A strongly-typed template record based on the row type of the target.</span></span> <span data-ttu-id="e8cdd-213">テンプレートのレコードには、対象の行の更新プログラムの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-213">The template record specifies the update values for the target rows.</span></span> <span data-ttu-id="e8cdd-214">Nillable 行の列を特定の行で、列を更新しないことを示すために null 値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-214">For nillable row columns, you can specify a null value to indicate that the column should not be updated in the target rows.</span></span>|<span data-ttu-id="e8cdd-215">ターゲットで更新する行を指定する SQL の WHERE 句の内容。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-215">The contents of a SQL WHERE clause that specifies the rows to be updated in the target.</span></span> <span data-ttu-id="e8cdd-216">たとえば、"説明 = 'Inserted レコード 1'"です。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-216">For example, "DESCRIPTION= 'Inserted Record #1'".</span></span>|  
  
 <span data-ttu-id="e8cdd-217">更新操作では、ターゲットから削除された行の数を返します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-217">The Update operation returns the number of rows deleted from the target.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e8cdd-218">WCF サービス モデルでは、更新操作で使用されるテンプレート レコードは、厳密に型指定されたが。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-218">In the WCF service model, the template record used in the Update operation is strongly-typed.</span></span> <span data-ttu-id="e8cdd-219">列が nillable の場合は、その値に設定して、更新操作から列を省略できます**null**テンプレート レコードでただし、列は、nillable がない場合する必要があります設定テンプレート レコード内の値。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-219">If a column is nillable, you can omit the column from the Update operation by setting its value to **null** in the template record; however, if a column is not nillable, then you must set its value in the template record.</span></span> <span data-ttu-id="e8cdd-220">たとえば、列が主キーの場合、値を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-220">For example, if a column is a primary key, it must contain a value.</span></span> <span data-ttu-id="e8cdd-221">詳細については、次を参照してください。 [WCF サービス モデルを使用して基本的な SQL 操作の呼び出しの制限事項](#BKMK_LimitationsInvoking)します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-221">For more information, see [Limitations of Invoking the Basic SQL Operations by Using the WCF Service Model](#BKMK_LimitationsInvoking).</span></span>  
  
 <span data-ttu-id="e8cdd-222">次のコードでは、ACCOUNTACTIVITY テーブルを対象とする更新操作を示します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-222">The following code shows an Update operation that targets the ACCOUNTACTIVITY table.</span></span>  
  
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
>  <span data-ttu-id="e8cdd-223">このコードは、作成、構成、および WCF クライアントのインスタンスを開く手順を省略します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-223">This code omits steps to create, configure, and open the WCF client instance.</span></span> <span data-ttu-id="e8cdd-224">次の手順を含む、例では、次を参照してください。[挿入操作](#BKMK_InsertOperation)します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-224">For an example that includes these steps, see [Insert Operation](#BKMK_InsertOperation).</span></span>  
  
### <a name="delete-operation"></a><span data-ttu-id="e8cdd-225">削除操作</span><span class="sxs-lookup"><span data-stu-id="e8cdd-225">Delete Operation</span></span>  
 <span data-ttu-id="e8cdd-226">次の表では、削除操作のパラメーターを示します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-226">The following table shows the parameters for the Delete operation.</span></span>  
  
|<span data-ttu-id="e8cdd-227">FILTER</span><span class="sxs-lookup"><span data-stu-id="e8cdd-227">FILTER</span></span>|  
|------------|  
|<span data-ttu-id="e8cdd-228">ターゲットから削除する行を指定する SQL の WHERE 句の内容。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-228">The contents of a SQL WHERE clause that specifies the rows to be deleted from the target.</span></span> <span data-ttu-id="e8cdd-229">たとえば、"説明 = 'Inserted レコード 1'"です。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-229">For example, "DESCRIPTION= 'Inserted Record #1'".</span></span>|  
  
 <span data-ttu-id="e8cdd-230">削除操作は、ターゲットから削除された行の数を返します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-230">The Delete operation returns the number of rows deleted from the target.</span></span> <span data-ttu-id="e8cdd-231">次のコードでは、ACCOUNTACTIVITY テーブルを対象とする削除操作を示します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-231">The following code shows a Delete operation that targets the ACCOUNTACTIVITY table.</span></span>  
  
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
>  <span data-ttu-id="e8cdd-232">このコードは、作成、構成、および WCF クライアントのインスタンスを開く手順を省略します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-232">This code omits steps to create, configure, and open the WCF client instance.</span></span> <span data-ttu-id="e8cdd-233">次の手順を含む、例では、次を参照してください。、[挿入操作](#BKMK_InsertOperation)します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-233">For an example that includes these steps, see the [Insert Operation](#BKMK_InsertOperation).</span></span>  
  
##  <a name="BKMK_LimitationsInvoking"></a> <span data-ttu-id="e8cdd-234">WCF サービス モデルを使用して基本的な SQL 操作の呼び出しの制限事項</span><span class="sxs-lookup"><span data-stu-id="e8cdd-234">Limitations of Invoking the Basic SQL Operations by Using the WCF Service Model</span></span>  
 <span data-ttu-id="e8cdd-235">WCF クライアントを使用して SQL の基本的な操作を呼び出すときに、次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-235">The following limitations exist when you invoke the basic SQL operations by using a WCF client:</span></span>  
  
- <span data-ttu-id="e8cdd-236">**操作を挿入します。**</span><span class="sxs-lookup"><span data-stu-id="e8cdd-236">**Insert operation.**</span></span> <span data-ttu-id="e8cdd-237">複数のレコード挿入操作で使用されるレコード セットは厳密に型指定され、そのためにすべての行の列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-237">The record set used in a multiple record Insert operation is strongly-typed and therefore includes all row columns.</span></span> <span data-ttu-id="e8cdd-238">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を意味するレコード内の null 値を解釈するには、列は、挿入操作から除外する必要があります。 ただし、null 値に設定することはできませんので nillable 以外の列を除外することはできません。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-238">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interprets a null value in a record to mean that the column should be excluded from the Insert operation; however, non-nillable columns cannot be excluded because you cannot set them to a null value.</span></span> <span data-ttu-id="e8cdd-239">そのため、複数のレコード挿入操作を実行するときに nillable ではない列の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-239">Therefore, you must specify values for non-nillable columns when you perform a multiple record Insert operation.</span></span>  
  
- <span data-ttu-id="e8cdd-240">**操作を挿入します。**</span><span class="sxs-lookup"><span data-stu-id="e8cdd-240">**Insert operation.**</span></span> <span data-ttu-id="e8cdd-241">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]解釈、 **DbNull**列を複数のレコード挿入操作から除外することを意味する nillable データ列の値。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-241">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interprets a **DbNull** value in a nillable data column to mean that the column should be excluded from a multiple record Insert operation.</span></span> <span data-ttu-id="e8cdd-242">つまりに nillable 列を設定することはできません**DbNull**複数レコードの Oracle データベースで操作を挿入します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-242">This means that you cannot set a nillable column to **DbNull** on the Oracle database in a multiple record Insert operation.</span></span>  
  
- <span data-ttu-id="e8cdd-243">**操作を挿入します。**</span><span class="sxs-lookup"><span data-stu-id="e8cdd-243">**Insert operation.**</span></span> <span data-ttu-id="e8cdd-244">大量のレコード セットに関連する複数のレコードの挿入操作のストリーミング サポートはありません。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-244">There is no streaming support for multiple record insert operations that involve a large record set.</span></span>  
  
- <span data-ttu-id="e8cdd-245">**操作を更新します。**</span><span class="sxs-lookup"><span data-stu-id="e8cdd-245">**Update operation.**</span></span> <span data-ttu-id="e8cdd-246">更新操作で使用されるテンプレート レコードは厳密に型指定し、そのためにすべての行の列が含まれます</span><span class="sxs-lookup"><span data-stu-id="e8cdd-246">The template record used in an Update operation is strongly-typed and therefore includes all row columns.</span></span> <span data-ttu-id="e8cdd-247">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を意味するには、このレコードに null 値を解釈するには、列は更新操作から除外する必要があります。 ただし、それらを null 値にできないので nillable 以外の列を除外することはできません。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-247">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interprets a null value in this record to mean that the column should be excluded from the Update operation; however, non-nillable columns cannot be excluded because you cannot them to a null value.</span></span> <span data-ttu-id="e8cdd-248">したがって、更新操作を実行するときは、nillable 以外の列の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-248">Therefore, you must specify values for non-nillable columns when you perform an Update operation.</span></span>  
  
- <span data-ttu-id="e8cdd-249">**操作を更新します。**</span><span class="sxs-lookup"><span data-stu-id="e8cdd-249">**Update operation.**</span></span> <span data-ttu-id="e8cdd-250">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]解釈、 **DbNull** nillable データの列に列を操作から除外することを意味するテンプレートのレコード値。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-250">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interprets a **DbNull** value in a nillable data column in the template record to mean that the column should be excluded from the operation.</span></span> <span data-ttu-id="e8cdd-251">つまりに nillable 列を設定することはできません**DbNull**更新操作を使用して Oracle データベースでします。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-251">This means that you cannot set a nillable column to **DbNull** on the Oracle database by using the Update operation.</span></span>  
  
- <span data-ttu-id="e8cdd-252">**操作を選択します。**</span><span class="sxs-lookup"><span data-stu-id="e8cdd-252">**Select operation.**</span></span> <span data-ttu-id="e8cdd-253">大量のレコード セットを返す SELECT クエリのストリーミング サポートはありません。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-253">There is no streaming support for SELECT queries that return a large record set.</span></span>  
  
  <span data-ttu-id="e8cdd-254">これらの制限に課題が存在する場合は、ために、WCF チャネル モデルを使用して、操作を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-254">For scenarios where these limitations present challenges, you can invoke the operation by using the WCF channel model because:</span></span>  
  
- <span data-ttu-id="e8cdd-255">WCF チャネル モデルを使用すると、更新、挿入操作から特定のデータ列を除外できます。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-255">By using the WCF channel model, you can exclude specific data columns from Update and Insert operations.</span></span>  
  
- <span data-ttu-id="e8cdd-256">WCF チャネル モデル ノード レベルのストリーミング サポートの基本的な SQL 操作を提供、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を公開します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-256">The WCF channel model provides node-level streaming support for the basic SQL operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes.</span></span>  
  
  <span data-ttu-id="e8cdd-257">使用した WCF チャネル モデルを使用しての詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[開発 Oracle データベース アプリケーションを使用して、WCF チャネル モデル](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-257">For more information about using the WCF channel model with the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Develop Oracle Database Applications Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8cdd-258">参照</span><span class="sxs-lookup"><span data-stu-id="e8cdd-258">See Also</span></span>  
 [<span data-ttu-id="e8cdd-259">WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="e8cdd-259">Develop Oracle Database Applications Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)