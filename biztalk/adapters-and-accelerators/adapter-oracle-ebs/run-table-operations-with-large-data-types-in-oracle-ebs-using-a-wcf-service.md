---
title: WCF サービス モデルを使用して Oracle E-business Suite での大規模なデータ型を持つテーブルに対する操作の完了 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93ba3191-d234-424a-b2da-dcf384df4985
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9869cd49ed09d80a866f3dcbb6f4b9429788339b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982563"
---
# <a name="complete-operations-on-tables-with-large-data-types-in-oracle-e-business-suite-using-the-wcf-service-model"></a><span data-ttu-id="1f0f6-102">WCF サービス モデルを使用して Oracle E-business Suite での大規模なデータ型を持つテーブルに対する操作を完了します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-102">Complete operations on tables with large data types in Oracle E-Business Suite using the WCF service model</span></span>
<span data-ttu-id="1f0f6-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアントが BLOB、CLOB、NCLOB、BFILE などの大規模なデータ型を持つインターフェイス テーブルとビューで操作を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] enables adapter clients to perform operations on interface tables and views with large data types such as BLOB, CLOB, NCLOB, and BFILE.</span></span>  

- <span data-ttu-id="1f0f6-104">型の列の BLOB、CLOB、NCLOB、アダプターにより、クライアントは、読み取り、データを更新します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-104">For columns of type BLOB, CLOB, and NCLOB, the adapter enables clients to read as well as update data.</span></span> <span data-ttu-id="1f0f6-105">アダプター公開 Read_\<*LOBColName* \>と Update_\<*LOBColName* \>を読み取って、データを更新する操作、 \<*LOBColName* \>大量のデータ型の列の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-105">The adapter exposes Read_\<*LOBColName*\> and Update_\<*LOBColName*\> operations to read and update data respectively, where \<*LOBColName*\> is the name of column with large data type.</span></span> <span data-ttu-id="1f0f6-106">大規模なデータ型は、1 つのインターフェイス テーブルでは、複数の列がある場合、アダプターは、多くの読み取りし、そのインターフェイス テーブルに対して操作を更新を公開します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-106">If there is more than one column with large data type in a single interface table, the adapter exposes as many read and update operations for that interface table.</span></span>  

- <span data-ttu-id="1f0f6-107">BFILE の型の列は、アダプター クライアントは、データを読み取るだけことができます。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-107">For columns of type BFILE, adapter clients can only read data.</span></span> <span data-ttu-id="1f0f6-108">アダプター公開 Read_\<*LOBColName* \> BFILE 型の列からデータを読み取る操作。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-108">The adapter exposes Read_\<*LOBColName*\> operation to read data from columns of BFILE type.</span></span> <span data-ttu-id="1f0f6-109">大規模なデータ型は、1 つのインターフェイス テーブルでは、複数の列がある場合、アダプターは、インターフェイス テーブルに対する操作の読み取りの多くを公開します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-109">If there is more than one column with large data type in a single interface table, the adapter exposes as many read operations for the interface table.</span></span>  

  <span data-ttu-id="1f0f6-110">これらの操作の詳細については、[インターフェイス テーブル、インターフェイス ビュー、テーブル、ビューを含む LOB データを操作](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-110">For more information about these operations, see [Operations on Interface Tables, Interface Views, Tables, and Views That Contain LOB Data](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md).</span></span>  

## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="1f0f6-111">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="1f0f6-111">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="1f0f6-112">このトピックの例では、顧客のデータベース テーブル内の BLOB 列 (写真) を更新し、同じ列からデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-112">The example in this topic updates a BLOB column (PHOTO) in the CUSTOMER database table and then retrieves the data from the same column.</span></span> <span data-ttu-id="1f0f6-113">サンプルに付属のスクリプトを実行して、テーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-113">The table is created by running the script provided with the samples.</span></span> <span data-ttu-id="1f0f6-114">サンプルの詳細については、[Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-114">For more information about samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="1f0f6-115">サンプルについては、 **LargeDataTypes_ServiceModel**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-115">A sample, **LargeDataTypes_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  

> [!NOTE]
>  <span data-ttu-id="1f0f6-116">このトピックでは、更新とベース データベース テーブル内の大規模なデータ型の列を読み取り用の詳細なタスクを使用します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-116">This topic lists detailed tasks for updating and reading columns of large data types in a base database table.</span></span> <span data-ttu-id="1f0f6-117">更新とのインターフェイス テーブルに大量のデータ型の列を読み取り用同じ一連のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-117">You must perform the same set of tasks for updating and reading columns of large data types in an interface table.</span></span>  

## <a name="the-wcf-client-class"></a><span data-ttu-id="1f0f6-118">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="1f0f6-118">The WCF Client Class</span></span>  
 <span data-ttu-id="1f0f6-119">によって大量のデータ型では、テーブルでの操作に対して生成された WCF クライアントの名前、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次の表に示すように、テーブルの名前に基づきます。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-119">The name of the WCF client generated for the operations on tables with large data types by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is based on the name of the table, as listed in the following table.</span></span>  


|     <span data-ttu-id="1f0f6-120">成果物</span><span class="sxs-lookup"><span data-stu-id="1f0f6-120">Artifact</span></span>     |                     <span data-ttu-id="1f0f6-121">WCF クライアント名</span><span class="sxs-lookup"><span data-stu-id="1f0f6-121">WCF Client Name</span></span>                      |
|------------------|----------------------------------------------------------|
| <span data-ttu-id="1f0f6-122">インターフェイス テーブル</span><span class="sxs-lookup"><span data-stu-id="1f0f6-122">Interface tables</span></span> | <span data-ttu-id="1f0f6-123">[APP_NAME] InterfaceTables_*[SCHEMA]\\*[TABLE_NAME] のクライアント</span><span class="sxs-lookup"><span data-stu-id="1f0f6-123">InterfaceTables_[APP_NAME]*[SCHEMA]\\*[TABLE_NAME]Client</span></span> |

 <span data-ttu-id="1f0f6-124">[構成] は、Oracle E-business Suite のアプリケーションの実際の名前を =たとえば、ヘルプです。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-124">[APP_NAME] = Actual name of the Oracle E-Business Suite application; for example, FND.</span></span>  

 <span data-ttu-id="1f0f6-125">[スキーマ] のアイテムのコレクションを =たとえば、アプリです。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-125">[SCHEMA] = Collection of artifacts; for example, APPS.</span></span>  

 <span data-ttu-id="1f0f6-126">[TABLE_NAME] テーブルの名前を =たとえば、MS_SAMPLE_EMPLOYEE です。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-126">[TABLE_NAME] = The name of the table; for example, MS_SAMPLE_EMPLOYEE.</span></span>  

 <span data-ttu-id="1f0f6-127">[VIEW_NAME] ビューの名前を =たとえば、MS_SAMPLE_EMPLOYEE_View です。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-127">[VIEW_NAME] = The name of the view; for example, MS_SAMPLE_EMPLOYEE_View.</span></span>  

### <a name="method-signature-for-invoking-operations-on-tables"></a><span data-ttu-id="1f0f6-128">テーブルに対する操作を呼び出すためのメソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="1f0f6-128">Method Signature for Invoking Operations on Tables</span></span>  
 <span data-ttu-id="1f0f6-129">次の表では、テーブルに対する基本操作のメソッド シグネチャを示します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-129">The following table shows the method signatures for the basic operations on a table.</span></span> <span data-ttu-id="1f0f6-130">署名は、ビューの名前空間と名前のテーブルを置換する点を除いて表示は、同じです。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-130">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  

|<span data-ttu-id="1f0f6-131">演算</span><span class="sxs-lookup"><span data-stu-id="1f0f6-131">Operation</span></span>|<span data-ttu-id="1f0f6-132">メソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="1f0f6-132">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="1f0f6-133">Update_\<*column_name*\></span><span class="sxs-lookup"><span data-stu-id="1f0f6-133">Update_\<*column_name*\></span></span>|<span data-ttu-id="1f0f6-134">public void Update_\<*column_name*\>(フィルター、byte[] のデータを文字列)。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-134">public void Update_\<*column_name*\>(string FILTER, byte[] DATA);</span></span>|  
|<span data-ttu-id="1f0f6-135">Read_\<*column_name*\></span><span class="sxs-lookup"><span data-stu-id="1f0f6-135">Read_\<*column_name*\></span></span>|<span data-ttu-id="1f0f6-136">パブリック System.IO.Stream Read_\<*column_name*\>(フィルターの文字列)。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-136">public System.IO.Stream Read_\<*column_name*\>(string FILTER);</span></span>|  

 <span data-ttu-id="1f0f6-137">例としては、次のコードは、アプリ スキーマの下で顧客データベースのテーブルに対する Update_PHOTO と Read_PHOTO 操作に対して生成された WCF クライアント クラスのメソッド シグネチャを示します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-137">As an example, the following code shows the method signatures for a WCF client class generated for the Update_PHOTO and Read_PHOTO operations on the CUSTOMER database table under the APPS schema.</span></span>  

```  
public partial class Tables_APPS_CUSTOMERClient : System.ServiceModel.ClientBase<Tables_APPS_CUSTOMER>, Tables_APPS_CUSTOMER {      

    public void Update_PHOTO(string FILTER, byte[] DATA);  

    public System.IO.Stream Read_PHOTO(string FILTER);  
}  
```  

 <span data-ttu-id="1f0f6-138">このスニペットで**Tables_APPS_CUSTOMERClient**によって生成された OracleEBSBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-138">In this snippet, **Tables_APPS_CUSTOMERClient** is the name of the WCF class in the OracleEBSBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="1f0f6-139">Update_PHOTO と Read_PHOTO はの更新および読み取るテーブル内の大規模なデータ型の列を呼び出すことができるメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-139">Update_PHOTO and Read_PHOTO are methods that can be invoked to update and read columns of large data types in a table.</span></span>  

### <a name="parameters-for-table-operations"></a><span data-ttu-id="1f0f6-140">テーブル操作のパラメーター</span><span class="sxs-lookup"><span data-stu-id="1f0f6-140">Parameters for Table Operations</span></span>  
 <span data-ttu-id="1f0f6-141">このセクションでは、Update_ に必要なパラメーターを提供します。\<*column_name* \>と Read_\<*column_name* \>操作。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-141">This section provides the parameters required by the Update_\<*column_name*\> and Read_\<*column_name*\> operation.</span></span>  

|<span data-ttu-id="1f0f6-142">操作名</span><span class="sxs-lookup"><span data-stu-id="1f0f6-142">Operation name</span></span>|<span data-ttu-id="1f0f6-143">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1f0f6-143">Parameters</span></span>|  
|--------------------|----------------|  
|<span data-ttu-id="1f0f6-144">Update_\<*column_name*\></span><span class="sxs-lookup"><span data-stu-id="1f0f6-144">Update_\<*column_name*\></span></span>|<span data-ttu-id="1f0f6-145">次のパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-145">Requires the following parameters:</span></span><br /><br /> <span data-ttu-id="1f0f6-146">-   `string FILTER`.</span><span class="sxs-lookup"><span data-stu-id="1f0f6-146">-   `string FILTER`.</span></span> <span data-ttu-id="1f0f6-147">このパラメーターは、場所を含める必要があります句を更新するデータを持っているレコードを表します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-147">This parameter must contain the where clause that denotes the record for which data has to be updated.</span></span> <span data-ttu-id="1f0f6-148">たとえば、 `"WHERE Name='Mindy Martin'"`のようにします。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-148">For example, `"WHERE Name='Mindy Martin'"`.</span></span><br /><span data-ttu-id="1f0f6-149">-   `byte[] DATA`.</span><span class="sxs-lookup"><span data-stu-id="1f0f6-149">-   `byte[] DATA`.</span></span> <span data-ttu-id="1f0f6-150">大規模なデータ型の列で更新するデータのバイト配列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-150">Contains a byte array of data to be update in a column of large data type.</span></span>|  
|<span data-ttu-id="1f0f6-151">Read_\<*column_name*\></span><span class="sxs-lookup"><span data-stu-id="1f0f6-151">Read_\<*column_name*\></span></span>|<span data-ttu-id="1f0f6-152">次のパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-152">Requires the following parameters:</span></span><br /><br /> <span data-ttu-id="1f0f6-153">-   `string FILTER`.</span><span class="sxs-lookup"><span data-stu-id="1f0f6-153">-   `string FILTER`.</span></span> <span data-ttu-id="1f0f6-154">このパラメーターは、場所を含める必要があります句を元のデータが読み取られるレコードを表します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-154">This parameter must contain the where clause that denotes the record from which the data has to be read.</span></span> <span data-ttu-id="1f0f6-155">たとえば、 `"WHERE Name='Mindy Martin'"`のようにします。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-155">For example, `"WHERE Name='Mindy Martin'"`.</span></span>|  

## <a name="creating-a-wcf-client-to-invoke-operations-on-tables-with-columns-of-large-data-types"></a><span data-ttu-id="1f0f6-156">大規模なデータ型の列を持つテーブルに対する操作の呼び出しに WCF クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-156">Creating a WCF Client to Invoke Operations on Tables with Columns of Large Data Types</span></span>  
 <span data-ttu-id="1f0f6-157">汎用的な一連の WCF クライアントを使用して Oracle E-business Suite での操作を実行するために必要なアクションは、一連のタスクで説明されている[Oracle E-business Suite アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-157">The generic set of actions required to perform an operation on Oracle E-Business Suite using a WCF client involves a set of tasks described in [Overview of the WCF service model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md).</span></span> <span data-ttu-id="1f0f6-158">このセクションでは、顧客のデータベース テーブルでも Update_PHOTO と Read_PHOTO の操作を呼び出すための WCF クライアントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-158">This section describes how to create a WCF client to invoke Update_PHOTO and Read_PHOTO operations on a CUSTOMER database table.</span></span>  

#### <a name="to-create-a-wcf-client"></a><span data-ttu-id="1f0f6-159">WCF クライアントを作成するには</span><span class="sxs-lookup"><span data-stu-id="1f0f6-159">To create a WCF client</span></span>  

1. <span data-ttu-id="1f0f6-160">Visual Studio で Visual c# プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-160">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="1f0f6-161">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-161">For this topic, create a console application.</span></span>  

2. <span data-ttu-id="1f0f6-162">顧客のデータベース テーブルでも Update_PHOTO と Read_PHOTO の操作のための WCF クライアント クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-162">Generate the WCF client class for the Update_PHOTO and Read_PHOTO operations on the CUSTOMER database table.</span></span> <span data-ttu-id="1f0f6-163">WCF クライアント クラスを生成する詳細については、[WCF クライアントまたは Oracle E-business Suite ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-163">For more information about generating a WCF client class, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="1f0f6-164">WCF クライアント クラスを生成する前に必ず設定して、 **EnableBizTalkCompatibilityMode**プロパティを false にバインドします。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-164">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  

3. <span data-ttu-id="1f0f6-165">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.OracleEBS`と`Microsoft.ServiceModel.Channels`、`System.Transactions`します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-165">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS` and `Microsoft.ServiceModel.Channels`, `System.Transactions`.</span></span>  

4. <span data-ttu-id="1f0f6-166">Program.cs ファイルを開き、次の名前空間を追加します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-166">Open the Program.cs file and add the following namespaces:</span></span>  

   -   `Microsoft.Adapters.OracleEBS`  

   -   `System.ServiceModel`  

   -   `System.Transactions`  

   -   `System.IO`  

5. <span data-ttu-id="1f0f6-167">Program.cs ファイルを開き、次のスニペットの説明に従って、クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-167">Open the Program.cs file and create a client as described in the snippet below.</span></span>  

   ```  

             Tables_APPS_CUSTOMERClient client = new Tables_APPS_CUSTOMERClient("OracleEBSBinding_Tables_APPS_CUSTOMER");  

   client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
   client.ClientCredentials.UserName.Password = "<Enter password here>";  
   ```  

    <span data-ttu-id="1f0f6-168">このスニペットで`Tables_APPS_CUSTOMERClient`OracleEBSBindingClient.cs で定義されている WCF クライアントです。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-168">In this snippet, `Tables_APPS_CUSTOMERClient` is the WCF client defined in OracleEBSBindingClient.cs.</span></span> <span data-ttu-id="1f0f6-169">このファイルがによって生成された、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-169">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="1f0f6-170">このスニペットでは、バインディングと構成ファイル app.config ファイルからエンドポイント アドレスを使用します。これらの値は、コードで明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-170">In this snippet, you use the binding and endpoint address from the configuration file app.config. You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="1f0f6-171">クライアント バインディングを指定する、さまざまな方法の詳細については、[Oracle E-business suite バインド クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-171">For more information on the different ways of specifying client binding, see [Configure a client binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  

6. <span data-ttu-id="1f0f6-172">クライアントの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-172">Set the credentials for the client.</span></span>  

   ```  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  

   > [!IMPORTANT]
   >  <span data-ttu-id="1f0f6-173">この例では、データベース テーブルの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-173">In this example, you are performing operations on a database table.</span></span> <span data-ttu-id="1f0f6-174">ただし、インターフェイス テーブルでの操作を実行する場合は、する必要がありますコンテキストを設定するアプリケーションの適切な値を指定することによって、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-174">However, if you are performing operations on an interface table, you must set the application context by specifying appropriate values for the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="1f0f6-175">クライアントを開く前に、これらのバインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-175">You must specify these binding properties before opening the client.</span></span> <span data-ttu-id="1f0f6-176">アプリケーションのコンテキストの詳細については、[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-176">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  

7. <span data-ttu-id="1f0f6-177">次のスニペットで説明されているように、クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-177">Open the client as described in the snippet below:</span></span>  

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

8. <span data-ttu-id="1f0f6-178">顧客テーブルに Update_PHOTO 操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-178">Invoke the Update_PHOTO operation on the CUSTOMER table.</span></span>  

    <span data-ttu-id="1f0f6-179">Update_PHOTO 操作には、更新するデータのバイト配列が必要です。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-179">The Update_PHOTO operation requires a byte array for the data to be updated.</span></span> <span data-ttu-id="1f0f6-180">このコード スニペットでは、FileStream クラスを使用しての写真を SamplePhoto.jpg バイト配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-180">In this code snippet, you use the FileStream class to create a byte array for a photo, SamplePhoto.jpg.</span></span> <span data-ttu-id="1f0f6-181">このアプリケーションを操作するには、プロジェクトの bin ディレクトリにファイルをコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-181">For this application to work, the file must be copied to the project’s bin directory.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="1f0f6-182">トランザクションでは、Update_PHOTO 操作を実行する必要がありますので、 **UseAmbientTransaction**に設定するプロパティをバインドする必要があります**true**内 Update_PHOTO 操作を実行する必要があります、トランザクションのスコープ。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-182">The Update_PHOTO operation must be performed in a transaction, so the **UseAmbientTransaction** binding property must be set to **true** and the Update_PHOTO operation must be performed within a transaction scope.</span></span> <span data-ttu-id="1f0f6-183">設定することができます、 **UseAmbientTransaction** app.config 内、または、アプリケーションで明示的に設定することで、プロパティをバインド`binding.UseAmbientTransaction = true`します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-183">You can set the **UseAmbientTransaction** binding property either in the app.config or by explicitly setting it in your application as `binding.UseAmbientTransaction = true`.</span></span> <span data-ttu-id="1f0f6-184">場合は、コードでバインディングのプロパティを明示的に指定は、設定する必要がありますようにクライアントを開く前に注意してください。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-184">Note that if you are specifying the binding property explicitly in the code, you must do so before opening the client.</span></span>  

   ```  
   byte[] photo;  

   using (FileStream fs = new FileStream("SamplePhoto.jpg", FileMode.Open))  
   {  
       try  
       {  
           Console.WriteLine("Reading the photo");  
           int count = 0;  
           photo = new byte[fs.Length];  
           while ((count += fs.Read(photo, count, (int)(((fs.Length - count) > 4096) ? 4096 : fs.Length - count))) < fs.Length) ;  
       }  
       catch(Exception ex)  
       {  
           Console.WriteLine("Exception: " + ex.Message);  
           throw;  
       }  
   }  

   Console.WriteLine("Updating data for the 'PHOTO' column");  
   // Invoking the Update_PHOTO operation inside a transaction scope  
   using (TransactionScope tx = new TransactionScope())  
   {  
       string filter = "WHERE Name='Mindy Martin'";  
       client.Update_PHOTO(filter, photo);  
       tx.Complete();  
   }  

   ```  

9. <span data-ttu-id="1f0f6-185">顧客テーブルに Read_PHOTO 操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-185">Invoke the Read_PHOTO operation on the CUSTOMER table.</span></span>  

     <span data-ttu-id="1f0f6-186">Read_PHOTO、System.IO.Stream の形式で出力を示します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-186">The Read_PHOTO gives the output in the form of System.IO.Stream.</span></span> <span data-ttu-id="1f0f6-187">アダプターのクライアントでは、Read_PHOTO 操作からのデータの読み取りに FileStream クラスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-187">The adapter client must implement the FileStream class to read the data from Read_PHOTO operation.</span></span> <span data-ttu-id="1f0f6-188">Read_PHOTO 操作が完了した後、プロジェクトの bin ディレクトリの下で PhotoCopy.jpg ファイルがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-188">After the Read_PHOTO operation is complete, a file PhotoCopy.jpg is copied under the project’s bin directory.</span></span>  

    ```  
    using (FileStream fs = new FileStream("PhotoCopy.jpg", FileMode.Create))  
    {  
        Console.WriteLine("Reading photo data");  
        String ReadFilter = "WHERE NAME='Mindy Martin'";  
        Stream photoStream = client.Read_PHOTO(ReadFilter);  
        Console.WriteLine("Photo data read -- writing to PhotoCopy.jpg");  

        int count;  
        int length = 0;  
        byte[] buffer = new byte[4096];  
        while ((count = photoStream.Read(buffer, 0, 4096)) > 0)  
        {  
            fs.Write(buffer, 0, count);  
            length+=count;  
        }  
        Console.WriteLine("{0} bytes written to PhotoCopy.jpg", length);  
    }  

    Console.WriteLine("Photo updated and read back -- Hit <RETURN> to end");  
    Console.ReadLine();  
    ```  

10. <span data-ttu-id="1f0f6-189">次のスニペットの説明に従って、クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-189">Close the client as described in the snippet below:</span></span>  

    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  

11. <span data-ttu-id="1f0f6-190">プロジェクトをビルドし、それを実行します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-190">Build the project and then run it.</span></span> <span data-ttu-id="1f0f6-191">アプリケーションでは、CUSTOMER テーブルの PHOTO 列を更新し、PHOTO 列の内容を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-191">The application updates the PHOTO column of the CUSTOMER table and then reads the content of the PHOTO column.</span></span>  

## <a name="see-also"></a><span data-ttu-id="1f0f6-192">参照</span><span class="sxs-lookup"><span data-stu-id="1f0f6-192">See Also</span></span>  
 [<span data-ttu-id="1f0f6-193">WCF サービス モデルを使用して Oracle E-business Suite のアプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="1f0f6-193">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)