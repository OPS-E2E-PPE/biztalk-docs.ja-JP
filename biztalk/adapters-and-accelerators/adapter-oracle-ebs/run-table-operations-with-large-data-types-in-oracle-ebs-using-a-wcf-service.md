---
title: "WCF サービス モデルを使用して Oracle E-business Suite での大規模なデータ型を持つテーブルでの操作を完了 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93ba3191-d234-424a-b2da-dcf384df4985
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 720da748059d3fe3da376ea42495a2587577f5ee
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="complete-operations-on-tables-with-large-data-types-in-oracle-e-business-suite-using-the-wcf-service-model"></a><span data-ttu-id="4fc8b-102">WCF サービス モデルを使用して Oracle E-business Suite での大規模なデータ型を持つテーブルに対する操作を完了します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-102">Complete operations on tables with large data types in Oracle E-Business Suite using the WCF service model</span></span>
<span data-ttu-id="4fc8b-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアントが BLOB、CLOB、NCLOB、BFILE などの大規模なデータ型とのインターフェイス テーブルやビューでの操作を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] enables adapter clients to perform operations on interface tables and views with large data types such as BLOB, CLOB, NCLOB, and BFILE.</span></span>  
  
-   <span data-ttu-id="4fc8b-104">型の列を読み取るできるだけでなく、データ更新のクライアントにより、アダプター、BLOB、CLOB、NCLOB、します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-104">For columns of type BLOB, CLOB, and NCLOB, the adapter enables clients to read as well as update data.</span></span> <span data-ttu-id="4fc8b-105">アダプター公開 Read_\<*LOBColName* \>と Update_\<*LOBColName* \>を読み取り、それぞれのデータを更新操作、 \<*LOBColName* \>大量のデータ型の列の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-105">The adapter exposes Read_\<*LOBColName*\> and Update_\<*LOBColName*\> operations to read and update data respectively, where \<*LOBColName*\> is the name of column with large data type.</span></span> <span data-ttu-id="4fc8b-106">大規模なデータ型は、1 つのインターフェイス テーブルで 1 つ以上の列がある場合、アダプターは、多くの読み取りし、そのインターフェイス テーブルに対して操作を更新を公開します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-106">If there is more than one column with large data type in a single interface table, the adapter exposes as many read and update operations for that interface table.</span></span>  
  
-   <span data-ttu-id="4fc8b-107">BFILE 型の列は、アダプターのクライアントは、データを読み取るだけことができます。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-107">For columns of type BFILE, adapter clients can only read data.</span></span> <span data-ttu-id="4fc8b-108">アダプター公開 Read_\<*LOBColName* \> BFILE 型の列からデータを操作します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-108">The adapter exposes Read_\<*LOBColName*\> operation to read data from columns of BFILE type.</span></span> <span data-ttu-id="4fc8b-109">大規模なデータ型は、1 つのインターフェイス テーブルで 1 つ以上の列がある場合、アダプターは、多くの読み取り操作インターフェイス テーブルとしてを公開します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-109">If there is more than one column with large data type in a single interface table, the adapter exposes as many read operations for the interface table.</span></span>  
  
 <span data-ttu-id="4fc8b-110">これらの操作の詳細については、次を参照してください。[インターフェイス テーブル、インターフェイス ビュー、テーブル、およびビューを含む LOB データに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)です。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-110">For more information about these operations, see [Operations on Interface Tables, Interface Views, Tables, and Views That Contain LOB Data](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="4fc8b-111">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="4fc8b-111">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="4fc8b-112">このトピックの例では、顧客データベース テーブル内の BLOB 列 (写真) を更新し、同じ列からデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-112">The example in this topic updates a BLOB column (PHOTO) in the CUSTOMER database table and then retrieves the data from the same column.</span></span> <span data-ttu-id="4fc8b-113">サンプルに用意されているスクリプトを実行して、テーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-113">The table is created by running the script provided with the samples.</span></span> <span data-ttu-id="4fc8b-114">サンプルの詳細については、次を参照してください。 [Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-114">For more information about samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="4fc8b-115">サンプルは、 **LargeDataTypes_ServiceModel**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプルです。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-115">A sample, **LargeDataTypes_ServiceModel**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4fc8b-116">このトピックでは、ベース データベース テーブルに大量のデータ型の列を読み取ったり更新に関する詳細なタスクを示します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-116">This topic lists detailed tasks for updating and reading columns of large data types in a base database table.</span></span> <span data-ttu-id="4fc8b-117">更新とのインターフェイス テーブルに大量のデータ型の列を読み取り、同じ一連のタスクを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-117">You must perform the same set of tasks for updating and reading columns of large data types in an interface table.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="4fc8b-118">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="4fc8b-118">The WCF Client Class</span></span>  
 <span data-ttu-id="4fc8b-119">大量のデータ型とは、テーブルでの操作に対して生成される WCF クライアントの名前、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次の表に示すように、テーブルの名前に基づきます。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-119">The name of the WCF client generated for the operations on tables with large data types by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is based on the name of the table, as listed in the following table.</span></span>  
  
|<span data-ttu-id="4fc8b-120">成果物</span><span class="sxs-lookup"><span data-stu-id="4fc8b-120">Artifact</span></span>|<span data-ttu-id="4fc8b-121">WCF クライアント名</span><span class="sxs-lookup"><span data-stu-id="4fc8b-121">WCF Client Name</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="4fc8b-122">インターフェイス テーブル</span><span class="sxs-lookup"><span data-stu-id="4fc8b-122">Interface tables</span></span>|<span data-ttu-id="4fc8b-123">InterfaceTables_ [APP_NAME] _ [SCHEMA]\_[TABLE_NAME] クライアント</span><span class="sxs-lookup"><span data-stu-id="4fc8b-123">InterfaceTables_[APP_NAME]_[SCHEMA]\_[TABLE_NAME]Client</span></span>|  
  
 <span data-ttu-id="4fc8b-124">[構成]、Oracle E-business Suite アプリケーションの実際の名前を =たとえばのヘルプ。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-124">[APP_NAME] = Actual name of the Oracle E-Business Suite application; for example, FND.</span></span>  
  
 <span data-ttu-id="4fc8b-125">[スキーマ]; の成果物のコレクションを =たとえば、アプリです。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-125">[SCHEMA] = Collection of artifacts; for example, APPS.</span></span>  
  
 <span data-ttu-id="4fc8b-126">[TABLE_NAME] テーブルの名前を =たとえば、MS_SAMPLE_EMPLOYEE です。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-126">[TABLE_NAME] = The name of the table; for example, MS_SAMPLE_EMPLOYEE.</span></span>  
  
 <span data-ttu-id="4fc8b-127">[VIEW_NAME] ビューの名前を =たとえば、MS_SAMPLE_EMPLOYEE_View です。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-127">[VIEW_NAME] = The name of the view; for example, MS_SAMPLE_EMPLOYEE_View.</span></span>  
  
### <a name="method-signature-for-invoking-operations-on-tables"></a><span data-ttu-id="4fc8b-128">テーブルに対する操作を呼び出すためのメソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="4fc8b-128">Method Signature for Invoking Operations on Tables</span></span>  
 <span data-ttu-id="4fc8b-129">次の表は、テーブルの基本的な操作について、メソッド シグネチャを示します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-129">The following table shows the method signatures for the basic operations on a table.</span></span> <span data-ttu-id="4fc8b-130">署名は、ビューの名前空間と名前のテーブルを置換する点を除いて、表示は、同じです。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-130">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="4fc8b-131">操作</span><span class="sxs-lookup"><span data-stu-id="4fc8b-131">Operation</span></span>|<span data-ttu-id="4fc8b-132">メソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="4fc8b-132">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="4fc8b-133">Update_\<*column_name*\></span><span class="sxs-lookup"><span data-stu-id="4fc8b-133">Update_\<*column_name*\></span></span>|<span data-ttu-id="4fc8b-134">public void Update_\<*column_name*\>(フィルター、byte[] データを文字列) です。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-134">public void Update_\<*column_name*\>(string FILTER, byte[] DATA);</span></span>|  
|<span data-ttu-id="4fc8b-135">Read_\<*column_name*\></span><span class="sxs-lookup"><span data-stu-id="4fc8b-135">Read_\<*column_name*\></span></span>|<span data-ttu-id="4fc8b-136">パブリック System.IO.Stream Read_\<*column_name*\>(文字列のフィルター) です。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-136">public System.IO.Stream Read_\<*column_name*\>(string FILTER);</span></span>|  
  
 <span data-ttu-id="4fc8b-137">例としては、次のコードは、アプリケーション スキーマの下にある顧客データベース テーブルに Update_PHOTO および Read_PHOTO 操作に対して生成される WCF クライアント クラスのメソッドのシグニチャを示します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-137">As an example, the following code shows the method signatures for a WCF client class generated for the Update_PHOTO and Read_PHOTO operations on the CUSTOMER database table under the APPS schema.</span></span>  
  
```  
public partial class Tables_APPS_CUSTOMERClient : System.ServiceModel.ClientBase<Tables_APPS_CUSTOMER>, Tables_APPS_CUSTOMER {      
  
    public void Update_PHOTO(string FILTER, byte[] DATA);  
  
    public System.IO.Stream Read_PHOTO(string FILTER);  
}  
```  
  
 <span data-ttu-id="4fc8b-138">このスニペットで**Tables_APPS_CUSTOMERClient**によって生成された OracleEBSBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-138">In this snippet, **Tables_APPS_CUSTOMERClient** is the name of the WCF class in the OracleEBSBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="4fc8b-139">Update_PHOTO と Read_PHOTO は、更新し、テーブル内の大規模なデータ型の列を表示するに呼び出せるようにする方法です。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-139">Update_PHOTO and Read_PHOTO are methods that can be invoked to update and read columns of large data types in a table.</span></span>  
  
### <a name="parameters-for-table-operations"></a><span data-ttu-id="4fc8b-140">テーブル操作のパラメーター</span><span class="sxs-lookup"><span data-stu-id="4fc8b-140">Parameters for Table Operations</span></span>  
 <span data-ttu-id="4fc8b-141">このセクションでは、Update_ に必要なパラメーター\<*column_name* \>と Read_\<*column_name* \>操作します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-141">This section provides the parameters required by the Update_\<*column_name*\> and Read_\<*column_name*\> operation.</span></span>  
  
|<span data-ttu-id="4fc8b-142">操作名</span><span class="sxs-lookup"><span data-stu-id="4fc8b-142">Operation name</span></span>|<span data-ttu-id="4fc8b-143">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4fc8b-143">Parameters</span></span>|  
|--------------------|----------------|  
|<span data-ttu-id="4fc8b-144">Update_\<*column_name*\></span><span class="sxs-lookup"><span data-stu-id="4fc8b-144">Update_\<*column_name*\></span></span>|<span data-ttu-id="4fc8b-145">次のパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-145">Requires the following parameters:</span></span><br /><br /> <span data-ttu-id="4fc8b-146">-   `string FILTER`.</span><span class="sxs-lookup"><span data-stu-id="4fc8b-146">-   `string FILTER`.</span></span> <span data-ttu-id="4fc8b-147">このパラメーターは、where を含める必要があります句を更新するデータを持っているレコードを表します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-147">This parameter must contain the where clause that denotes the record for which data has to be updated.</span></span> <span data-ttu-id="4fc8b-148">たとえば、 `"WHERE Name='Mindy Martin'"`のようにします。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-148">For example, `"WHERE Name='Mindy Martin'"`.</span></span><br /><span data-ttu-id="4fc8b-149">-   `byte[] DATA`.</span><span class="sxs-lookup"><span data-stu-id="4fc8b-149">-   `byte[] DATA`.</span></span> <span data-ttu-id="4fc8b-150">大規模なデータ型の列で更新するデータのバイト配列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-150">Contains a byte array of data to be update in a column of large data type.</span></span>|  
|<span data-ttu-id="4fc8b-151">Read_\<*column_name*\></span><span class="sxs-lookup"><span data-stu-id="4fc8b-151">Read_\<*column_name*\></span></span>|<span data-ttu-id="4fc8b-152">次のパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-152">Requires the following parameters:</span></span><br /><br /> <span data-ttu-id="4fc8b-153">-   `string FILTER`.</span><span class="sxs-lookup"><span data-stu-id="4fc8b-153">-   `string FILTER`.</span></span> <span data-ttu-id="4fc8b-154">このパラメーターは、where を含める必要がありますを元のデータが読み取られるレコードを示す句。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-154">This parameter must contain the where clause that denotes the record from which the data has to be read.</span></span> <span data-ttu-id="4fc8b-155">たとえば、 `"WHERE Name='Mindy Martin'"`のようにします。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-155">For example, `"WHERE Name='Mindy Martin'"`.</span></span>|  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-tables-with-columns-of-large-data-types"></a><span data-ttu-id="4fc8b-156">大規模なデータ型の列を持つテーブルの操作の呼び出しに WCF クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-156">Creating a WCF Client to Invoke Operations on Tables with Columns of Large Data Types</span></span>  
 <span data-ttu-id="4fc8b-157">WCF クライアントを使用して Oracle E-business Suite で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[Oracle E-business Suite アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-157">The generic set of actions required to perform an operation on Oracle E-Business Suite using a WCF client involves a set of tasks described in [Overview of the WCF service model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md).</span></span> <span data-ttu-id="4fc8b-158">このセクションでは、顧客データベース テーブルに Update_PHOTO と Read_PHOTO 操作の呼び出しに WCF クライアントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-158">This section describes how to create a WCF client to invoke Update_PHOTO and Read_PHOTO operations on a CUSTOMER database table.</span></span>  
  
#### <a name="to-create-a-wcf-client"></a><span data-ttu-id="4fc8b-159">WCF クライアントを作成するには</span><span class="sxs-lookup"><span data-stu-id="4fc8b-159">To create a WCF client</span></span>  
  
1.  <span data-ttu-id="4fc8b-160">Visual Studio で Visual c# プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-160">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="4fc8b-161">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-161">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="4fc8b-162">顧客データベース テーブルに Update_PHOTO および Read_PHOTO 操作の WCF クライアント クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-162">Generate the WCF client class for the Update_PHOTO and Read_PHOTO operations on the CUSTOMER database table.</span></span> <span data-ttu-id="4fc8b-163">詳細については、WCF クライアント クラスを生成する、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-163">For more information about generating a WCF client class, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="4fc8b-164">WCF クライアント クラスを生成する前に必ず設定してください、 **EnableBizTalkCompatibilityMode**プロパティを false にバインドします。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-164">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3.  <span data-ttu-id="4fc8b-165">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.OracleEBS`と`Microsoft.ServiceModel.Channels`、`System.Transactions`です。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-165">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS` and `Microsoft.ServiceModel.Channels`, `System.Transactions`.</span></span>  
  
4.  <span data-ttu-id="4fc8b-166">Program.cs ファイルを開き、次の名前空間を追加します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-166">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
    -   `System.Transactions`  
  
    -   `System.IO`  
  
5.  <span data-ttu-id="4fc8b-167">Program.cs ファイルを開き、次のスニペットの説明に従って、クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-167">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
    ```  
  
              Tables_APPS_CUSTOMERClient client = new Tables_APPS_CUSTOMERClient("OracleEBSBinding_Tables_APPS_CUSTOMER");  
  
    client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     <span data-ttu-id="4fc8b-168">このスニペットで`Tables_APPS_CUSTOMERClient`OracleEBSBindingClient.cs で定義された WCF クライアントです。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-168">In this snippet, `Tables_APPS_CUSTOMERClient` is the WCF client defined in OracleEBSBindingClient.cs.</span></span> <span data-ttu-id="4fc8b-169">このファイルにより生成されて、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-169">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4fc8b-170">このスニペットでは、バインディングと構成ファイル app.config ファイルからエンドポイント アドレスを使用します。これらの値は、コードで明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-170">In this snippet, you use the binding and endpoint address from the configuration file app.config. You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="4fc8b-171">クライアント バインディングを指定するさまざまな方法の詳細については、次を参照してください。 [for Oracle E-business Suite バインド クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)です。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-171">For more information on the different ways of specifying client binding, see [Configure a client binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  
  
6.  <span data-ttu-id="4fc8b-172">クライアントの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-172">Set the credentials for the client.</span></span>  
  
    ```  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="4fc8b-173">この例では、データベースのテーブルに対する操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-173">In this example, you are performing operations on a database table.</span></span> <span data-ttu-id="4fc8b-174">ただし場合インターフェイス テーブルに対する操作を実行する場合は、する必要があります設定、アプリケーションのコンテキストの適切な値を指定することによって、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-174">However, if you are performing operations on an interface table, you must set the application context by specifying appropriate values for the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="4fc8b-175">クライアントを開く前にこれらのバインディング プロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-175">You must specify these binding properties before opening the client.</span></span> <span data-ttu-id="4fc8b-176">アプリケーション コンテキストの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-176">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
7.  <span data-ttu-id="4fc8b-177">次のスニペット」の説明に従って、クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-177">Open the client as described in the snippet below:</span></span>  
  
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
  
8.  <span data-ttu-id="4fc8b-178">操作を呼び出し、Update_PHOTO 顧客テーブルにします。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-178">Invoke the Update_PHOTO operation on the CUSTOMER table.</span></span>  
  
     <span data-ttu-id="4fc8b-179">Update_PHOTO 操作には、更新するデータのバイト配列が必要です。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-179">The Update_PHOTO operation requires a byte array for the data to be updated.</span></span> <span data-ttu-id="4fc8b-180">このコード スニペットでは、写真、SamplePhoto.jpg のバイト配列を作成するのに FileStream クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-180">In this code snippet, you use the FileStream class to create a byte array for a photo, SamplePhoto.jpg.</span></span> <span data-ttu-id="4fc8b-181">このアプリケーションが動作するには、ため、プロジェクトの bin ディレクトリにファイルをコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-181">For this application to work, the file must be copied to the project’s bin directory.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="4fc8b-182">トランザクションでは、Update_PHOTO 操作を実行する必要がありますので、 **UseAmbientTransaction** binding プロパティを設定する必要があります**true** Update_PHOTO 操作を内で実行する必要があります、トランザクションのスコープです。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-182">The Update_PHOTO operation must be performed in a transaction, so the **UseAmbientTransaction** binding property must be set to **true** and the Update_PHOTO operation must be performed within a transaction scope.</span></span> <span data-ttu-id="4fc8b-183">設定することができます、 **UseAmbientTransaction**として、アプリケーションで明示的に設定することによってまたは app.config では、プロパティをバインド`binding.UseAmbientTransaction = true`です。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-183">You can set the **UseAmbientTransaction** binding property either in the app.config or by explicitly setting it in your application as `binding.UseAmbientTransaction = true`.</span></span> <span data-ttu-id="4fc8b-184">ある場合は、コードでは、バインディング プロパティを明示的に指定は、行う必要があります、クライアントを開く前に注意してください。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-184">Note that if you are specifying the binding property explicitly in the code, you must do so before opening the client.</span></span>  
  
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
  
9. <span data-ttu-id="4fc8b-185">操作を呼び出し、Read_PHOTO 顧客テーブルにします。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-185">Invoke the Read_PHOTO operation on the CUSTOMER table.</span></span>  
  
     <span data-ttu-id="4fc8b-186">Read_PHOTO は、System.IO.Stream の形式で出力を示します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-186">The Read_PHOTO gives the output in the form of System.IO.Stream.</span></span> <span data-ttu-id="4fc8b-187">アダプターのクライアントは、Read_PHOTO 操作からのデータを読み取る FileStream クラスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-187">The adapter client must implement the FileStream class to read the data from Read_PHOTO operation.</span></span> <span data-ttu-id="4fc8b-188">Read_PHOTO 操作が完了したら、プロジェクトの bin ディレクトリの下にある PhotoCopy.jpg ファイルがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-188">After the Read_PHOTO operation is complete, a file PhotoCopy.jpg is copied under the project’s bin directory.</span></span>  
  
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
  
10. <span data-ttu-id="4fc8b-189">次のスニペット」の説明に従って、クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-189">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
11. <span data-ttu-id="4fc8b-190">プロジェクトをビルドし、それを実行します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-190">Build the project and then run it.</span></span> <span data-ttu-id="4fc8b-191">アプリケーションでは、CUSTOMER テーブルの PHOTO 列を更新し、PHOTO 列の内容を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-191">The application updates the PHOTO column of the CUSTOMER table and then reads the content of the PHOTO column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fc8b-192">参照</span><span class="sxs-lookup"><span data-stu-id="4fc8b-192">See Also</span></span>  
 [<span data-ttu-id="4fc8b-193">WCF サービス モデルを使用して Oracle E-business Suite アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="4fc8b-193">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)