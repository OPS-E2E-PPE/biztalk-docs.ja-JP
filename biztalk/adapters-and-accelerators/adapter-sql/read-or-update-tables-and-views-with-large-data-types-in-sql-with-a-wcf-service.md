---
title: WCF サービス モデルを使用して SQL に大規模なデータ型を持つテーブルとビューで操作を実行する |Microsoft Docs
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
ms.openlocfilehash: a2bfb30c01113e868bd6a662d004639645e29746
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992483"
---
# <a name="run-operations-on-tables-and-views-with-large-data-types-in-sql-using-the-wcf-service-model"></a><span data-ttu-id="f6fe5-102">WCF サービス モデルを使用して SQL に大規模なデータ型を持つテーブルとビューで操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-102">Run Operations on Tables and Views with Large Data Types in SQL using the WCF Service Model</span></span>
<span data-ttu-id="f6fe5-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントの読み取りし、は、大規模なデータ型の列のデータを更新する、varchar (max)、nvarchar (max)、または varbinary (max) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enables adapter clients to read and update data in columns of large data types, that is, varchar(max), nvarchar(max), or varbinary(max).</span></span> <span data-ttu-id="f6fe5-104">このような列からデータを読み取る、アダプターのクライアントは、選択操作を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-104">To read data from such columns, adapter clients can use the Select operation.</span></span> <span data-ttu-id="f6fe5-105">アダプターを挿入またはこのような列にデータを更新するには、セットを公開する\<*column_name* \>操作、 \< *column_name* \>名前を指定します型 varchar (max)、nvarchar (max)、または varbinary (max) 列。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-105">To insert or update data into such columns, the adapter exposes a Set\<*column_name*\> operation, where \<*column_name*\> is the name of the column of type varchar(max), nvarchar(max), or varbinary(max).</span></span>  
  
 <span data-ttu-id="f6fe5-106">さらに、SQL Server でテキスト ドキュメントやイメージなどの非構造化データを格納 varbinay(max) 列があることができます。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-106">Additionally, in SQL Server, you can have the varbinay(max) column store unstructured data such as text documents and images.</span></span> <span data-ttu-id="f6fe5-107">このような非構造化データには、FILESTREAM データが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-107">Such unstructured data is called FILESTREAM data.</span></span> <span data-ttu-id="f6fe5-108">FILESTREAM データは、ファイル システム上のファイルとして格納することができます。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-108">FILESTREAM data can be stored as files on the file system.</span></span> <span data-ttu-id="f6fe5-109">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]により、クライアントは、varbinary (max) 型の列に FILESTREAM データを入力できます。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-109">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] enables the client to enter FILESTREAM data into columns of type varbinary(max).</span></span> <span data-ttu-id="f6fe5-110">[FILESTREAM ストレージ](https://docs.microsoft.com/sql/relational-databases/blob/filestream-sql-server)の詳細。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-110">[FILESTREAM storage](https://docs.microsoft.com/sql/relational-databases/blob/filestream-sql-server) has more information.</span></span> 
  
 <span data-ttu-id="f6fe5-111">このトピックでは実行する必要があります、特定のタスクについては、コンピューター上には、SQL Server および挿入または FILESTREAM データを更新できるアダプター クライアントを実行しているコンピューターを実行しています。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-111">This topic provides information about certain tasks you must perform on the computer running SQL Server and the computer running the adapter client to be able to insert or update FILESTREAM data.</span></span> <span data-ttu-id="f6fe5-112">このトピックの手順をセットを実行する方法も提供します\<*column_name* \> FILESTREAM データを挿入する操作。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-112">This topic also provides instructions on performing Set\<*column_name*\> operations to insert FILESTREAM data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6fe5-113">ユーザー定義型の列を含むテーブルに対して操作を実行している場合ことを確認するを参照してください[テーブルと、SQL アダプターを使用してユーザー定義型を持つビューで操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-113">If you are performing operation on tables that have columns of user-defined types, make sure you refer to [Operations on Tables and Views with User-Defined Types using the SQL adapter](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f6fe5-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="f6fe5-114">Prerequisites</span></span>  
 <span data-ttu-id="f6fe5-115">SQL Server を実行しているコンピューターと、アダプターのクライアントを実行しているコンピューターでは、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-115">You must perform the following tasks on the computer running SQL Server and the computer running the adapter client.</span></span>  
  
- <span data-ttu-id="f6fe5-116">**SQL Server を実行するコンピューター**</span><span class="sxs-lookup"><span data-stu-id="f6fe5-116">**On the computer running SQL Server**</span></span>  
  
  -   <span data-ttu-id="f6fe5-117">SQL Server インスタンスで FILESTREAM を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-117">You must enable FILESTREAM on the SQL Server instance.</span></span> <span data-ttu-id="f6fe5-118">参照してください[を有効にして、FILESTREAM の構成](https://docs.microsoft.com/sql/relational-databases/blob/enable-and-configure-filestream)します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-118">See [Enable and Configure FILESTREAM](https://docs.microsoft.com/sql/relational-databases/blob/enable-and-configure-filestream).</span></span>
  
  -   <span data-ttu-id="f6fe5-119">FILESTREAM が有効なデータベースを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-119">You must create a FILESTREAM-enabled database.</span></span> <span data-ttu-id="f6fe5-120">参照してください[FILESTREAM が有効なデータベースを作成](https://docs.microsoft.com/sql/relational-databases/blob/create-a-filestream-enabled-database)です。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-120">See [Create a FILESTREAM-Enabled Database](https://docs.microsoft.com/sql/relational-databases/blob/create-a-filestream-enabled-database).</span></span>
  
  -   <span data-ttu-id="f6fe5-121">FILESTREAM データを格納するためのテーブルが必要です。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-121">You must have a table for storing FILESTREAM data.</span></span> <span data-ttu-id="f6fe5-122">参照してください[FILESTREAM データを格納するテーブルを作成](https://docs.microsoft.com/sql/relational-databases/blob/create-a-table-for-storing-filestream-data)、</span><span class="sxs-lookup"><span data-stu-id="f6fe5-122">See [Create a Table for Storing FILESTREAM Data](https://docs.microsoft.com/sql/relational-databases/blob/create-a-table-for-storing-filestream-data),</span></span>
  
- <span data-ttu-id="f6fe5-123">**アダプターのクライアントを実行するコンピューター**</span><span class="sxs-lookup"><span data-stu-id="f6fe5-123">**On the computer running the adapter client**</span></span>  
  
  -   <span data-ttu-id="f6fe5-124">インストールされている SQL Client Connectivity SDK が必要です。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-124">You must have the SQL Client Connectivity SDK installed.</span></span> <span data-ttu-id="f6fe5-125">SQL クライアント接続 SDK をインストールするには、SQL Server セットアップを実行し、選択**SQL Client Connectivity SDK**で、**機能の選択**ウィザードのページ。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-125">You can install the SQL Client Connectivity SDK by running the SQL Server setup and selecting **SQL Client Connectivity SDK** in the **Feature Selection** page of the wizard.</span></span> <span data-ttu-id="f6fe5-126">アダプターは、FILESTREAM 操作を実行するのに SQL クライアント接続 sdk では、インストールされている、sqlncli10.dll を使用します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-126">The adapter uses the sqlncli10.dll, installed with the SQL Client Connectivity SDK, to perform FILESTREAM operations.</span></span>  
  
  <span data-ttu-id="f6fe5-127">これらのタスクを完了すると、設定は完了を挿入または SQL Server データベース テーブル内の FILESTREAM データを更新します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-127">After you have completed these tasks, you are all set to insert or update FILESTREAM data in SQL Server database tables.</span></span>  
  
## <a name="how-this-topic-demonstrates-operations-on-large-data-types"></a><span data-ttu-id="f6fe5-128">ここで大量のデータ型に対する演算をについて説明する方法</span><span class="sxs-lookup"><span data-stu-id="f6fe5-128">How This Topic Demonstrates Operations on Large Data Types</span></span>  
 <span data-ttu-id="f6fe5-129">セットを実行する方法を説明するために\<*column_name* \>大量のデータの型を持つテーブルに対する操作は、テーブルを受け取り**レコード**、列を持つ**Id**と**ドキュメント**:</span><span class="sxs-lookup"><span data-stu-id="f6fe5-129">To demonstrate how to perform Set\<*column_name*\> operations on tables with large data types, take a table, **Records**, that has columns **Id** and **Document**:</span></span>  
  
-   <span data-ttu-id="f6fe5-130">**レコード**サンプルで提供される SQL スクリプトを実行して、すべてのデータのテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-130">The **Records** table, with all the data, is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="f6fe5-131">詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-131">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
-   <span data-ttu-id="f6fe5-132">**Id**列の型は uniqueidentifier とは GUID を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-132">The **Id** column is of type uniqueidentifier and takes a GUID.</span></span> <span data-ttu-id="f6fe5-133">ある、 **Id**列は既に GUID '`438B7B4C-5491-409F-BCC1-78817C399EC3`'。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-133">Assume that the **Id** column already has a GUID ‘`438B7B4C-5491-409F-BCC1-78817C399EC3`’.</span></span>  
  
-   <span data-ttu-id="f6fe5-134">**ドキュメント**列が varbinary (max) 型。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-134">The **Document** column is of type VARBINARY(MAX).</span></span> <span data-ttu-id="f6fe5-135">更新する、**ドキュメント**列で、アダプターを公開、 **SetDocument**操作。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-135">To update the **Document** column, the adapter exposes the **SetDocument** operation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6fe5-136">SQL server の FILESTREAM 操作を示すためには、前提としていますが、**ドキュメント**列が FILESTREAM データを格納できます。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-136">For SQL Server, to demonstrate FILESTREAM operations, assume that the **Document** column can store FILESTREAM data.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="f6fe5-137">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="f6fe5-137">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="f6fe5-138">このトピックの例で操作を実行する、**レコード**テーブル。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-138">The example in this topic performs operations on the **Records** table.</span></span> <span data-ttu-id="f6fe5-139">**レコード**サンプルで提供される SQL スクリプトを実行してテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-139">The **Records** table is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="f6fe5-140">サンプルの詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-140">For more information about samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span> <span data-ttu-id="f6fe5-141">サンプルについては、 **Records_FILESTREAM_Op**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-141">A sample, **Records_FILESTREAM_Op**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="f6fe5-142">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="f6fe5-142">The WCF Client Class</span></span>  
 <span data-ttu-id="f6fe5-143">大規模データに対する操作の生成された WCF クライアントの名前の種類を[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]はでは、次の表に示すように、テーブルまたはビューの名前に基づきます。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-143">The name of the WCF client generated for the operations on large data types that the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] discovers, is based on the name of the table or view, as listed in the following table.</span></span>  
  
|<span data-ttu-id="f6fe5-144">SQL Server データベースの成果物</span><span class="sxs-lookup"><span data-stu-id="f6fe5-144">SQL Server Database Artifact</span></span>|<span data-ttu-id="f6fe5-145">WCF クライアント名</span><span class="sxs-lookup"><span data-stu-id="f6fe5-145">WCF Client Name</span></span>|  
|----------------------------------|---------------------|  
|<span data-ttu-id="f6fe5-146">テーブル</span><span class="sxs-lookup"><span data-stu-id="f6fe5-146">Table</span></span>|<span data-ttu-id="f6fe5-147">TableOp_ [Schema] _ [TABLE_NAME] のクライアント</span><span class="sxs-lookup"><span data-stu-id="f6fe5-147">TableOp_[Schema]_[TABLE_NAME]Client</span></span>|  
|<span data-ttu-id="f6fe5-148">表示</span><span class="sxs-lookup"><span data-stu-id="f6fe5-148">View</span></span>|<span data-ttu-id="f6fe5-149">ViewOp_ [Schema] _ [VIEW_NAME] のクライアント</span><span class="sxs-lookup"><span data-stu-id="f6fe5-149">ViewOp_[Schema]_[VIEW_NAME]Client</span></span>|  
  
 <span data-ttu-id="f6fe5-150">[スキーマ] コレクションの SQL Server のアイテム、=たとえば、dbo です。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-150">[SCHEMA] = Collection of SQL Server artifacts; for example, dbo.</span></span>  
  
### <a name="method-signature-for-invoking-operations-on-columns-of-large-data-types"></a><span data-ttu-id="f6fe5-151">大規模なデータ型の列に対する操作を呼び出すためのメソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="f6fe5-151">Method Signature for Invoking Operations on Columns of Large Data Types</span></span>  
 <span data-ttu-id="f6fe5-152">次の表では、テーブルに対する基本操作のメソッド シグネチャを示します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-152">The following table shows the method signatures for the basic operations on a table.</span></span> <span data-ttu-id="f6fe5-153">署名は、ビューの名前空間と名前のテーブルを置換する点を除いて表示は、同じです。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-153">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="f6fe5-154">演算</span><span class="sxs-lookup"><span data-stu-id="f6fe5-154">Operation</span></span>|<span data-ttu-id="f6fe5-155">メソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="f6fe5-155">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="f6fe5-156">設定\<*column_name*\></span><span class="sxs-lookup"><span data-stu-id="f6fe5-156">Set\<*column_name*\></span></span>|<span data-ttu-id="f6fe5-157">public void セット\<*column_name*\>(フィルター、byte[] のデータを文字列)。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-157">public void Set\<*column_name*\>(string Filter, byte[] Data);</span></span>|  
  
 <span data-ttu-id="f6fe5-158">\<*column_name* \> = ラージ データ型の列の名前。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-158">\<*column_name*\> = Name of the column of large data type.</span></span>  
  
 <span data-ttu-id="f6fe5-159">WCF クライアント クラスを生成の例として、次のコードがメソッド シグネチャを示します、 **SetDocument**操作、**レコード**既定の"dbo"スキーマの下のテーブル。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-159">As an example, the following code shows the method signatures for a WCF client class generated for the **SetDocument** operation on the **Records** table under the default “dbo” schema.</span></span>  
  
```  
public partial class TableOp_dbo_RecordsClient : System.ServiceModel.ClientBase<TableOp_dbo_Records>, TableOp_dbo_Records {      
    public void SetDocument (string Filter, byte[] Data);  
}  
```  
  
 <span data-ttu-id="f6fe5-160">このスニペットで**TableOp_dbo_RecordsClient**によって生成された SqlAdapterBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-160">In this snippet, **TableOp_dbo_RecordsClient** is the name of the WCF class in the SqlAdapterBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
### <a name="parameters-for-operations-on-columns-of-large-data-types"></a><span data-ttu-id="f6fe5-161">大規模なデータ型の列に対する操作のパラメーター</span><span class="sxs-lookup"><span data-stu-id="f6fe5-161">Parameters for Operations on Columns of Large Data Types</span></span>  
 <span data-ttu-id="f6fe5-162">このセクションでは、セットに必要なパラメーターを提供します。\<*column_name* \>操作。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-162">This section provides the parameters required by the Set\<*column_name*\> operation.</span></span>  
  
|<span data-ttu-id="f6fe5-163">[パラメーター名]</span><span class="sxs-lookup"><span data-stu-id="f6fe5-163">Parameter name</span></span>|<span data-ttu-id="f6fe5-164">説明</span><span class="sxs-lookup"><span data-stu-id="f6fe5-164">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="f6fe5-165">フィルター文字列</span><span class="sxs-lookup"><span data-stu-id="f6fe5-165">string Filter</span></span>|<span data-ttu-id="f6fe5-166">アダプターが大量のデータ型の列のレコードを更新ベースの WHERE 句を指定します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-166">Specifies the WHERE clause based on which the adapter updates the record for the column of large data type.</span></span>|  
|<span data-ttu-id="f6fe5-167">byte[] データ</span><span class="sxs-lookup"><span data-stu-id="f6fe5-167">byte[] Data</span></span>|<span data-ttu-id="f6fe5-168">大規模なデータ型の列を更新する必要があります値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-168">Specifies the value that must be updated for the column of large data type.</span></span>|  
  
 <span data-ttu-id="f6fe5-169">セット\<*column_name* \>操作では、任意の値は返されません。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-169">The Set\<*column_name*\> operation does not return any values.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-columns-of-large-data-types"></a><span data-ttu-id="f6fe5-170">大規模なデータ型の列の操作の呼び出しに WCF クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-170">Creating a WCF Client to Invoke Operations on Columns of Large Data Types</span></span>  
 <span data-ttu-id="f6fe5-171">WCF クライアントを使用して SQL Server で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[SQL アダプターを使用した WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-171">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF Service Model with the SQL Adapter](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="f6fe5-172">このセクションを呼び出す、WCF クライアントを作成する方法を説明します、 **SetDocument**での操作、**レコード**テーブル。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-172">This section describes how to create a WCF client to invoke the **SetDocument** operation on the **Records** table.</span></span> <span data-ttu-id="f6fe5-173">アダプターを公開、 **SetDocument**ラージ データ型の列のデータを更新する操作。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-173">The adapter exposes the **SetDocument** operation to update data in columns of large data types.</span></span>  
  
#### <a name="to-create-a-wcf-client"></a><span data-ttu-id="f6fe5-174">WCF クライアントを作成するには</span><span class="sxs-lookup"><span data-stu-id="f6fe5-174">To create a WCF client</span></span>  
  
1. <span data-ttu-id="f6fe5-175">Visual Studio で Visual c# プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-175">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="f6fe5-176">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-176">For this topic, create a console application.</span></span>  
  
2. <span data-ttu-id="f6fe5-177">WCF クライアント クラスを生成、 **SetDocument**操作、**レコード**テーブル。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-177">Generate the WCF client class for the **SetDocument** operation on the **Records** table.</span></span> <span data-ttu-id="f6fe5-178">WCF クライアント クラスを生成する詳細については、次を参照してください。 [SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-178">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
3. <span data-ttu-id="f6fe5-179">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`、 `Microsoft.ServiceModel.Channels`、および`System.Transactions`します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-179">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql`, `Microsoft.ServiceModel.Channels`, and `System.Transactions`.</span></span>  
  
4. <span data-ttu-id="f6fe5-180">Program.cs ファイルを開き、追加、`System.Transactions`名前空間。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-180">Open the Program.cs file and add the `System.Transactions` namespace.</span></span>  
  
5. <span data-ttu-id="f6fe5-181">次のスニペットの説明に従って、program.cs に、クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-181">In the Program.cs, create a client as described in the snippet below.</span></span>  
  
   ```  
  
             TableOp_dbo_RecordsClient client = new TableOp_dbo_RecordsClient("SqlAdapterBinding_TableOp_dbo_Records");  
   client.ClientCredentials.UserName.UserName = "";  
   client.ClientCredentials.UserName.Password = "";  
  
   ```  
  
    <span data-ttu-id="f6fe5-182">このスニペットで`TableOp_dbo_RecordsClient`SqlAdapterBindingClient.cs で定義されている WCF クライアントです。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-182">In this snippet, `TableOp_dbo_RecordsClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="f6fe5-183">このファイルがによって生成された、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-183">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="f6fe5-184">`SqlAdapterBinding_TableOp_dbo_Records` クライアント エンドポイント構成の名前を指定され、app.config で定義されます。このファイルがによって生成されても、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティとその他の構成設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-184">`SqlAdapterBinding_TableOp_dbo_Records` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  
  
   > [!CAUTION]
   >  <span data-ttu-id="f6fe5-185">FILESTREAM データの操作を行うには、常に Windows 認証を使用して SQL Server に接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-185">To perform operations on FILESTREAM data, you must always connect to SQL Server using Windows authentication.</span></span> <span data-ttu-id="f6fe5-186">を Windows 認証を使用して接続するには、前のスニペットで示すように、空のユーザー名とパスワードを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-186">To connect using Windows authentication, you must provide empty username and password, as shown in the preceding snippet.</span></span> <span data-ttu-id="f6fe5-187">また、SQL Server への接続に Windows 認証を使用する前に行うことが必要で説明されている手順[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-187">Also, before using Windows authentication to connect to SQL Server, you must have performed the steps mentioned in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f6fe5-188">このスニペットでは、構成ファイルからバインドおよびエンドポイント アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-188">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="f6fe5-189">これらの値は、コードで明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-189">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="f6fe5-190">クライアント バインディングを指定する、さまざまな方法の詳細については、次を参照してください。 [SQL アダプタのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-190">For more information on the different ways of specifying client binding, see [Configure a Client Binding for the SQL Adapter](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
6. <span data-ttu-id="f6fe5-191">次のスニペットで説明されているように、クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-191">Open the client as described in the snippet below:</span></span>  
  
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
  
7. <span data-ttu-id="f6fe5-192">呼び出す、 **SetDocument**操作、**レコード**テーブル。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-192">Invoke the **SetDocument** operation on the **Records** table.</span></span>  
  
   > [!CAUTION]
   >  <span data-ttu-id="f6fe5-193">セット<em>< column_name ></em>操作は、トランザクションで常に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-193">The Set<em><column_name></em> operations must always be performed in a transaction.</span></span> <span data-ttu-id="f6fe5-194">、これを実現するセット<em>< column_name ></em>トランザクション スコープ内で操作を呼び出す必要があると、 **UseAmbientTransaction**に設定するプロパティをバインドする必要があります**true**app.config でします。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-194">To ensure this, the Set<em><column_name></em> operation must be invoked within a transaction scope and the **UseAmbientTransaction** binding property must be set to **true** in the app.config.</span></span>  
  
   ```  
   using (TransactionScope tx = new TransactionScope())  
   {  
       string filter = "WHERE Id='438B7B4C-5491-409F-BCC1-78817C399EC3'";  
       byte[] data = ASCIIEncoding.ASCII.GetBytes("Sample data");  
       client.SetDocument(filter, data);  
       tx.Complete();  
   }  
   ```  
  
    <span data-ttu-id="f6fe5-195">ここでは、文字列"サンプル データ を base64 でエンコードされた文字列に変換、アプリケーションと、フィルター条件を満たすレコードの更新プログラムします。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-195">Here, the application converts the string “Sample data” into a base64 encoded string, and updates it in the record that satisfies the filter criteria.</span></span>  
  
8. <span data-ttu-id="f6fe5-196">次のスニペットの説明に従って、クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-196">Close the client as described in the snippet below:</span></span>  
  
   ```  
   client.Close();  
   Console.WriteLine("Press any key to exit...");  
   Console.ReadLine();  
   ```  
  
9. <span data-ttu-id="f6fe5-197">プロジェクトをビルドし、それを実行します。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-197">Build the project and then run it.</span></span> <span data-ttu-id="f6fe5-198">アプリケーションの更新プログラム、**ドキュメント**内の列、**レコード**テーブル。</span><span class="sxs-lookup"><span data-stu-id="f6fe5-198">The application updates the **Document** column in the **Records** table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6fe5-199">参照</span><span class="sxs-lookup"><span data-stu-id="f6fe5-199">See Also</span></span>  
[<span data-ttu-id="f6fe5-200">WCF サービス モデルを使用してアプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="f6fe5-200">Develop applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)