---
title: WCF サービス モデルを使用して SQL の大規模なデータ型を持つテーブルとビューの操作を実行 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d33e17c-e09e-4a57-9acc-43095e67ed8c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1da0def828c1dbfa8511dc61b529fa02cb53ca5a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967128"
---
# <a name="run-operations-on-tables-and-views-with-large-data-types-in-sql-using-the-wcf-service-model"></a><span data-ttu-id="2f8cf-102">WCF サービス モデルを使用して SQL の大規模なデータ型を持つテーブルとビューの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-102">Run Operations on Tables and Views with Large Data Types in SQL using the WCF Service Model</span></span>
<span data-ttu-id="2f8cf-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントの読み取りし、は、大規模なデータ型の列のデータを更新する、varchar (max)、nvarchar (max)、または varbinary (max) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enables adapter clients to read and update data in columns of large data types, that is, varchar(max), nvarchar(max), or varbinary(max).</span></span> <span data-ttu-id="2f8cf-104">このような列からデータを読み取る、アダプターのクライアントは、Select 操作を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-104">To read data from such columns, adapter clients can use the Select operation.</span></span> <span data-ttu-id="2f8cf-105">アダプターの一連の公開を挿入またはこのような列にデータを更新、\<*column_name* \>操作、場所\< *column_name* \>名前を指定します型 varchar (max)、nvarchar (max)、または varbinary (max) 列。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-105">To insert or update data into such columns, the adapter exposes a Set\<*column_name*\> operation, where \<*column_name*\> is the name of the column of type varchar(max), nvarchar(max), or varbinary(max).</span></span>  
  
 <span data-ttu-id="2f8cf-106">さらに、SQL Server でテキスト ドキュメントやイメージなどの非構造化データを格納 varbinay(max) 列を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-106">Additionally, in SQL Server, you can have the varbinay(max) column store unstructured data such as text documents and images.</span></span> <span data-ttu-id="2f8cf-107">このような非構造化データには、FILESTREAM データは呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-107">Such unstructured data is called FILESTREAM data.</span></span> <span data-ttu-id="2f8cf-108">FILESTREAM データは、ファイル システム上のファイルとして格納することができます。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-108">FILESTREAM data can be stored as files on the file system.</span></span> <span data-ttu-id="2f8cf-109">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] Varbinary (max) 型の列に FILESTREAM データを入力するクライアントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-109">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enables the client to enter FILESTREAM data into columns of type varbinary(max).</span></span> <span data-ttu-id="2f8cf-110">[FILESTREAM ストレージ](https://docs.microsoft.com/sql/relational-databases/blob/filestream-sql-server)の詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-110">[FILESTREAM storage](https://docs.microsoft.com/sql/relational-databases/blob/filestream-sql-server) has more information.</span></span> 
  
 <span data-ttu-id="2f8cf-111">このトピックの内容が行う必要があります、特定のタスクに関する情報を提供、コンピューター上には、SQL Server とを挿入または FILESTREAM データを更新できるアダプターのクライアントを実行しているコンピューターを実行しています。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-111">This topic provides information about certain tasks you must perform on the computer running SQL Server and the computer running the adapter client to be able to insert or update FILESTREAM data.</span></span> <span data-ttu-id="2f8cf-112">このトピックの内容についても説明セットを実行する\<*column_name* \> FILESTREAM データを挿入する操作。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-112">This topic also provides instructions on performing Set\<*column_name*\> operations to insert FILESTREAM data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f8cf-113">ユーザー定義型の列を含むテーブルでの操作を実行する場合、必ずするを参照してください[テーブルと、SQL アダプターを使用してユーザー定義型を持つビューに対して操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-113">If you are performing operation on tables that have columns of user-defined types, make sure you refer to [Operations on Tables and Views with User-Defined Types using the SQL adapter](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2f8cf-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="2f8cf-114">Prerequisites</span></span>  
 <span data-ttu-id="2f8cf-115">SQL Server を実行しているコンピューターと、アダプターのクライアントを実行しているコンピューターで、次のタスクを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-115">You must perform the following tasks on the computer running SQL Server and the computer running the adapter client.</span></span>  
  
-   <span data-ttu-id="2f8cf-116">**SQL Server を実行するコンピューター**</span><span class="sxs-lookup"><span data-stu-id="2f8cf-116">**On the computer running SQL Server**</span></span>  
  
    -   <span data-ttu-id="2f8cf-117">SQL Server インスタンスで FILESTREAM を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-117">You must enable FILESTREAM on the SQL Server instance.</span></span> <span data-ttu-id="2f8cf-118">参照してください[を有効にして、FILESTREAM を構成する](https://docs.microsoft.com/sql/relational-databases/blob/enable-and-configure-filestream)です。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-118">See [Enable and Configure FILESTREAM](https://docs.microsoft.com/sql/relational-databases/blob/enable-and-configure-filestream).</span></span>
  
    -   <span data-ttu-id="2f8cf-119">FILESTREAM が有効なデータベースを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-119">You must create a FILESTREAM-enabled database.</span></span> <span data-ttu-id="2f8cf-120">参照してください[FILESTREAM が有効なデータベースを作成する](https://docs.microsoft.com/sql/relational-databases/blob/create-a-filestream-enabled-database)です。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-120">See [Create a FILESTREAM-Enabled Database](https://docs.microsoft.com/sql/relational-databases/blob/create-a-filestream-enabled-database).</span></span>
  
    -   <span data-ttu-id="2f8cf-121">FILESTREAM データを格納するテーブルが必要です。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-121">You must have a table for storing FILESTREAM data.</span></span> <span data-ttu-id="2f8cf-122">参照してください[FILESTREAM データを格納するテーブルを作成する](https://docs.microsoft.com/sql/relational-databases/blob/create-a-table-for-storing-filestream-data)、</span><span class="sxs-lookup"><span data-stu-id="2f8cf-122">See [Create a Table for Storing FILESTREAM Data](https://docs.microsoft.com/sql/relational-databases/blob/create-a-table-for-storing-filestream-data),</span></span>
  
-   <span data-ttu-id="2f8cf-123">**アダプターのクライアントを実行するコンピューター**</span><span class="sxs-lookup"><span data-stu-id="2f8cf-123">**On the computer running the adapter client**</span></span>  
  
    -   <span data-ttu-id="2f8cf-124">SQL クライアント接続 SDK がインストールされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-124">You must have the SQL Client Connectivity SDK installed.</span></span> <span data-ttu-id="2f8cf-125">SQL Server セットアップを実行しを選択すると、SQL クライアント接続 SDK をインストールすることができます**SQL クライアント接続 SDK**で、**機能の選択**ウィザードのページです。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-125">You can install the SQL Client Connectivity SDK by running the SQL Server setup and selecting **SQL Client Connectivity SDK** in the **Feature Selection** page of the wizard.</span></span> <span data-ttu-id="2f8cf-126">アダプターは、FILESTREAM 操作を実行するのに、SQL クライアント接続 SDK と共にインストールされる、sqlncli10.dll を使用します。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-126">The adapter uses the sqlncli10.dll, installed with the SQL Client Connectivity SDK, to perform FILESTREAM operations.</span></span>  
  
 <span data-ttu-id="2f8cf-127">これらのタスクを完了するがすべて設定するを挿入または SQL Server データベース テーブル内の FILESTREAM データを更新します。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-127">After you have completed these tasks, you are all set to insert or update FILESTREAM data in SQL Server database tables.</span></span>  
  
## <a name="how-this-topic-demonstrates-operations-on-large-data-types"></a><span data-ttu-id="2f8cf-128">このトピックの内容が大量のデータ型に対する操作を示しています</span><span class="sxs-lookup"><span data-stu-id="2f8cf-128">How This Topic Demonstrates Operations on Large Data Types</span></span>  
 <span data-ttu-id="2f8cf-129">セットを実行する方法をデモンストレーションする\<*column_name* \> 、大規模なデータ型でテーブルに対する操作にあるテーブルを見て**レコード**、列を持つ**Id**と**ドキュメント**:</span><span class="sxs-lookup"><span data-stu-id="2f8cf-129">To demonstrate how to perform Set\<*column_name*\> operations on tables with large data types, take a table, **Records**, that has columns **Id** and **Document**:</span></span>  
  
-   <span data-ttu-id="2f8cf-130">**レコード**サンプルに用意されている SQL スクリプトを実行してすべてのデータのテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-130">The **Records** table, with all the data, is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="2f8cf-131">詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-131">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
-   <span data-ttu-id="2f8cf-132">**Id**列型は uniqueidentifier は、GUID を取得します。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-132">The **Id** column is of type uniqueidentifier and takes a GUID.</span></span> <span data-ttu-id="2f8cf-133">あると想定、 **Id**列は既に GUID '`438B7B4C-5491-409F-BCC1-78817C399EC3`' です。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-133">Assume that the **Id** column already has a GUID ‘`438B7B4C-5491-409F-BCC1-78817C399EC3`’.</span></span>  
  
-   <span data-ttu-id="2f8cf-134">**ドキュメント**列が varbinary (max) 型です。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-134">The **Document** column is of type VARBINARY(MAX).</span></span> <span data-ttu-id="2f8cf-135">更新する、**ドキュメント**列で、アダプターを公開、 **SetDocument**操作します。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-135">To update the **Document** column, the adapter exposes the **SetDocument** operation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f8cf-136">SQL Server の FILESTREAM 操作を示すためには、あると想定、**ドキュメント**列が FILESTREAM データを格納できます。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-136">For SQL Server, to demonstrate FILESTREAM operations, assume that the **Document** column can store FILESTREAM data.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="2f8cf-137">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="2f8cf-137">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="2f8cf-138">このトピックの例で操作を実行する、**レコード**テーブル。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-138">The example in this topic performs operations on the **Records** table.</span></span> <span data-ttu-id="2f8cf-139">**レコード**サンプルに用意されている SQL スクリプトを実行してテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-139">The **Records** table is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="2f8cf-140">サンプルの詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-140">For more information about samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span> <span data-ttu-id="2f8cf-141">サンプルは、 **Records_FILESTREAM_Op**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプルです。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-141">A sample, **Records_FILESTREAM_Op**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="2f8cf-142">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="2f8cf-142">The WCF Client Class</span></span>  
 <span data-ttu-id="2f8cf-143">大規模なデータでの操作の生成、WCF クライアントの名前の種類を[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]検出、次の表に示すように、テーブルまたはビューの名前に基づきます。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-143">The name of the WCF client generated for the operations on large data types that the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] discovers, is based on the name of the table or view, as listed in the following table.</span></span>  
  
|<span data-ttu-id="2f8cf-144">SQL Server のデータベース成果物</span><span class="sxs-lookup"><span data-stu-id="2f8cf-144">SQL Server Database Artifact</span></span>|<span data-ttu-id="2f8cf-145">WCF クライアント名</span><span class="sxs-lookup"><span data-stu-id="2f8cf-145">WCF Client Name</span></span>|  
|----------------------------------|---------------------|  
|<span data-ttu-id="2f8cf-146">テーブル</span><span class="sxs-lookup"><span data-stu-id="2f8cf-146">Table</span></span>|<span data-ttu-id="2f8cf-147">TableOp_ [Schema] _ [TABLE_NAME] のクライアント</span><span class="sxs-lookup"><span data-stu-id="2f8cf-147">TableOp_[Schema]_[TABLE_NAME]Client</span></span>|  
|<span data-ttu-id="2f8cf-148">表示</span><span class="sxs-lookup"><span data-stu-id="2f8cf-148">View</span></span>|<span data-ttu-id="2f8cf-149">ViewOp_ [Schema] _ [VIEW_NAME] のクライアント</span><span class="sxs-lookup"><span data-stu-id="2f8cf-149">ViewOp_[Schema]_[VIEW_NAME]Client</span></span>|  
  
 <span data-ttu-id="2f8cf-150">[スキーマ]; SQL Server のコレクション アイテムを =たとえば、dbo します。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-150">[SCHEMA] = Collection of SQL Server artifacts; for example, dbo.</span></span>  
  
### <a name="method-signature-for-invoking-operations-on-columns-of-large-data-types"></a><span data-ttu-id="2f8cf-151">大規模なデータ型の列に対する操作を呼び出すためのメソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="2f8cf-151">Method Signature for Invoking Operations on Columns of Large Data Types</span></span>  
 <span data-ttu-id="2f8cf-152">次の表は、テーブルの基本的な操作について、メソッド シグネチャを示します。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-152">The following table shows the method signatures for the basic operations on a table.</span></span> <span data-ttu-id="2f8cf-153">署名は、ビューの名前空間と名前のテーブルを置換する点を除いて、表示は、同じです。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-153">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="2f8cf-154">操作</span><span class="sxs-lookup"><span data-stu-id="2f8cf-154">Operation</span></span>|<span data-ttu-id="2f8cf-155">メソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="2f8cf-155">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="2f8cf-156">設定\<*column_name*\></span><span class="sxs-lookup"><span data-stu-id="2f8cf-156">Set\<*column_name*\></span></span>|<span data-ttu-id="2f8cf-157">public void セット\<*column_name*\>(フィルター、byte[] データを文字列) です。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-157">public void Set\<*column_name*\>(string Filter, byte[] Data);</span></span>|  
  
 <span data-ttu-id="2f8cf-158">\<*column_name* \>大量のデータ型の列の名前を = です。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-158">\<*column_name*\> = Name of the column of large data type.</span></span>  
  
 <span data-ttu-id="2f8cf-159">たとえば、次のコードにはメソッド シグネチャに関するの WCF クライアント クラスを生成、 **SetDocument**で操作、**レコード**既定の"dbo"スキーマの下の表。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-159">As an example, the following code shows the method signatures for a WCF client class generated for the **SetDocument** operation on the **Records** table under the default “dbo” schema.</span></span>  
  
```  
public partial class TableOp_dbo_RecordsClient : System.ServiceModel.ClientBase<TableOp_dbo_Records>, TableOp_dbo_Records {      
    public void SetDocument (string Filter, byte[] Data);  
}  
```  
  
 <span data-ttu-id="2f8cf-160">このスニペットで**TableOp_dbo_RecordsClient**によって生成された SqlAdapterBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-160">In this snippet, **TableOp_dbo_RecordsClient** is the name of the WCF class in the SqlAdapterBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
### <a name="parameters-for-operations-on-columns-of-large-data-types"></a><span data-ttu-id="2f8cf-161">大規模なデータ型の列に対する操作のパラメーター</span><span class="sxs-lookup"><span data-stu-id="2f8cf-161">Parameters for Operations on Columns of Large Data Types</span></span>  
 <span data-ttu-id="2f8cf-162">このセクションでは、セットに必要なパラメーター\<*column_name* \>操作します。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-162">This section provides the parameters required by the Set\<*column_name*\> operation.</span></span>  
  
|<span data-ttu-id="2f8cf-163">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="2f8cf-163">Parameter name</span></span>|<span data-ttu-id="2f8cf-164">Description</span><span class="sxs-lookup"><span data-stu-id="2f8cf-164">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="2f8cf-165">文字列フィルター</span><span class="sxs-lookup"><span data-stu-id="2f8cf-165">string Filter</span></span>|<span data-ttu-id="2f8cf-166">アダプターが大量のデータ型の列のレコードを更新を基に WHERE 句を指定します。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-166">Specifies the WHERE clause based on which the adapter updates the record for the column of large data type.</span></span>|  
|<span data-ttu-id="2f8cf-167">byte[] データ</span><span class="sxs-lookup"><span data-stu-id="2f8cf-167">byte[] Data</span></span>|<span data-ttu-id="2f8cf-168">大規模なデータ型の列を更新する必要があります値を指定します。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-168">Specifies the value that must be updated for the column of large data type.</span></span>|  
  
 <span data-ttu-id="2f8cf-169">セット\<*column_name* \>操作は任意の値を返しません。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-169">The Set\<*column_name*\> operation does not return any values.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-columns-of-large-data-types"></a><span data-ttu-id="2f8cf-170">大規模なデータ型の列に対する操作を呼び出すに WCF クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-170">Creating a WCF Client to Invoke Operations on Columns of Large Data Types</span></span>  
 <span data-ttu-id="2f8cf-171">WCF クライアントを使用して SQL Server で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[SQL アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-171">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF Service Model with the SQL Adapter](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="2f8cf-172">このセクションを呼び出すための WCF クライアントを作成する方法について説明、 **SetDocument**での操作、**レコード**テーブル。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-172">This section describes how to create a WCF client to invoke the **SetDocument** operation on the **Records** table.</span></span> <span data-ttu-id="2f8cf-173">アダプターを公開、 **SetDocument**ラージ データ型の列のデータを更新する操作。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-173">The adapter exposes the **SetDocument** operation to update data in columns of large data types.</span></span>  
  
#### <a name="to-create-a-wcf-client"></a><span data-ttu-id="2f8cf-174">WCF クライアントを作成するには</span><span class="sxs-lookup"><span data-stu-id="2f8cf-174">To create a WCF client</span></span>  
  
1.  <span data-ttu-id="2f8cf-175">Visual Studio で Visual c# プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-175">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="2f8cf-176">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-176">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="2f8cf-177">WCF クライアント クラスを生成、 **SetDocument**での操作、**レコード**テーブル。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-177">Generate the WCF client class for the **SetDocument** operation on the **Records** table.</span></span> <span data-ttu-id="2f8cf-178">詳細については、WCF クライアント クラスを生成する、次を参照してください。 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-178">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
3.  <span data-ttu-id="2f8cf-179">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`、 `Microsoft.ServiceModel.Channels`、および`System.Transactions`です。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-179">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql`, `Microsoft.ServiceModel.Channels`, and `System.Transactions`.</span></span>  
  
4.  <span data-ttu-id="2f8cf-180">Program.cs ファイルを開き、追加、`System.Transactions`名前空間。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-180">Open the Program.cs file and add the `System.Transactions` namespace.</span></span>  
  
5.  <span data-ttu-id="2f8cf-181">Program.cs では、次のスニペット」の説明に従って、クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-181">In the Program.cs, create a client as described in the snippet below.</span></span>  
  
    ```  
  
              TableOp_dbo_RecordsClient client = new TableOp_dbo_RecordsClient("SqlAdapterBinding_TableOp_dbo_Records");  
    client.ClientCredentials.UserName.UserName = "";  
    client.ClientCredentials.UserName.Password = "";  
  
    ```  
  
     <span data-ttu-id="2f8cf-182">このスニペットで`TableOp_dbo_RecordsClient`SqlAdapterBindingClient.cs で定義された WCF クライアントです。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-182">In this snippet, `TableOp_dbo_RecordsClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="2f8cf-183">このファイルにより生成されて、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-183">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="2f8cf-184">`SqlAdapterBinding_TableOp_dbo_Records`クライアント エンドポイント構成の名前を指定、app.config で定義されます。このファイルがによって生成されても、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティおよびその他の構成設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-184">`SqlAdapterBinding_TableOp_dbo_Records` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="2f8cf-185">FILESTREAM データでの操作を行うには、常に Windows 認証を使用して SQL Server に接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-185">To perform operations on FILESTREAM data, you must always connect to SQL Server using Windows authentication.</span></span> <span data-ttu-id="2f8cf-186">Windows 認証を使用して接続するに、前のスニペットに示すように、空のユーザー名とパスワードを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-186">To connect using Windows authentication, you must provide empty username and password, as shown in the preceding snippet.</span></span> <span data-ttu-id="2f8cf-187">また、SQL Server への接続に Windows 認証を使用する前に行うことが必要で説明する手順[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-187">Also, before using Windows authentication to connect to SQL Server, you must have performed the steps mentioned in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f8cf-188">このスニペットでは、構成ファイルからバインディングとエンドポイント アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-188">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="2f8cf-189">これらの値は、コードで明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-189">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="2f8cf-190">クライアント バインディングを指定するさまざまな方法の詳細については、次を参照してください。 [SQL アダプタのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-190">For more information on the different ways of specifying client binding, see [Configure a Client Binding for the SQL Adapter](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
6.  <span data-ttu-id="2f8cf-191">次のスニペット」の説明に従って、クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-191">Open the client as described in the snippet below:</span></span>  
  
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
  
7.  <span data-ttu-id="2f8cf-192">呼び出す、 **SetDocument**での操作、**レコード**テーブル。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-192">Invoke the **SetDocument** operation on the **Records** table.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="2f8cf-193">セット *< column_name >* 操作は、トランザクションで常に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-193">The Set *<column_name>* operations must always be performed in a transaction.</span></span> <span data-ttu-id="2f8cf-194">、これを実現するセット *< column_name >* トランザクション スコープ内で操作を呼び出す必要があります、 **UseAmbientTransaction** binding プロパティを設定する必要があります**true**app.config です。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-194">To ensure this, the Set *<column_name>* operation must be invoked within a transaction scope and the **UseAmbientTransaction** binding property must be set to **true** in the app.config.</span></span>  
  
    ```  
    using (TransactionScope tx = new TransactionScope())  
    {  
        string filter = "WHERE Id='438B7B4C-5491-409F-BCC1-78817C399EC3'";  
        byte[] data = ASCIIEncoding.ASCII.GetBytes("Sample data");  
        client.SetDocument(filter, data);  
        tx.Complete();  
    }  
    ```  
  
     <span data-ttu-id="2f8cf-195">ここでは、文字列「サンプル データ」を base64 でエンコードされた文字列に変換、アプリケーションとフィルター条件を満たすレコードに更新します。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-195">Here, the application converts the string “Sample data” into a base64 encoded string, and updates it in the record that satisfies the filter criteria.</span></span>  
  
8.  <span data-ttu-id="2f8cf-196">次のスニペット」の説明に従って、クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-196">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
9. <span data-ttu-id="2f8cf-197">プロジェクトをビルドし、それを実行します。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-197">Build the project and then run it.</span></span> <span data-ttu-id="2f8cf-198">アプリケーションの更新プログラム、**ドキュメント**内の列、**レコード**テーブル。</span><span class="sxs-lookup"><span data-stu-id="2f8cf-198">The application updates the **Document** column in the **Records** table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f8cf-199">参照</span><span class="sxs-lookup"><span data-stu-id="2f8cf-199">See Also</span></span>  
[<span data-ttu-id="2f8cf-200">WCF サービス モデルを使用してアプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="2f8cf-200">Develop applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)