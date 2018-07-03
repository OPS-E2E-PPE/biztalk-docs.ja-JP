---
title: 挿入、更新、削除、またはインターフェイス テーブルと、WCF サービス モデルを使用してビューで操作を選択します |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae613c0e-4d9a-4c66-99e4-dd0443f1d495
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ed57328a925496449ddd73f3c363b32f60dc811
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983475"
---
# <a name="insert-update-delete-or-select-operations-on-interface-tables-and-views-using-the-wcf-service-model"></a><span data-ttu-id="01e4a-102">挿入、更新、削除、またはインターフェイス テーブルと、WCF サービス モデルを使用してビューで操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-102">Insert, update, delete, or select operations on interface tables and views using the WCF service model</span></span>
<span data-ttu-id="01e4a-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]インターフェイス テーブルに対する Insert、Select、Update、および Delete の基本的な操作のセットを検出します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] discovers a set of basic Insert, Select, Update, and Delete operations on interface tables.</span></span> <span data-ttu-id="01e4a-104">これらの操作を使用すると、単純な Insert、Select、Update を実行し、Delete ステートメントの WHERE 句では、ターゲットのインターフェイス テーブルで修飾できます。</span><span class="sxs-lookup"><span data-stu-id="01e4a-104">By using these operations, you can perform simple Insert, Select, Update, and Delete statements qualified by a WHERE clause on a target interface table.</span></span> <span data-ttu-id="01e4a-105">このトピックでは、WCF サービス モデルを使用してこれらの操作を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-105">This topic provides instructions on how to perform these operations using the WCF service model.</span></span>  

> [!NOTE]
>  <span data-ttu-id="01e4a-106">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]選択インターフェイス ビューに対する操作のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="01e4a-106">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports only Select operations on interface views.</span></span>  

 <span data-ttu-id="01e4a-107">アダプターがこれらの操作をサポートする方法の詳細については、次を参照してください。[インターフェイス テーブルとインターフェイス ビューで操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-107">For more information about how the adapter supports these operations, see [Operations on Interface Tables and Interface Views](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md).</span></span>  

## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="01e4a-108">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="01e4a-108">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="01e4a-109">このトピックの例では、MS_SAMPLE_EMPLOYEE インターフェイス テーブルの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-109">The example in this topic performs operations on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="01e4a-110">サンプルに付属のスクリプトを実行して、テーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="01e4a-110">The table is created by running the script provided with the samples.</span></span> <span data-ttu-id="01e4a-111">サンプルの詳細については、次を参照してください。 [Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-111">For more information about samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="01e4a-112">サンプルについては、 **Interface_Table_Ops**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="01e4a-112">A sample, **Interface_Table_Ops**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  

## <a name="the-wcf-client-class"></a><span data-ttu-id="01e4a-113">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="01e4a-113">The WCF Client Class</span></span>  
 <span data-ttu-id="01e4a-114">基本的な操作に対して生成された WCF クライアントの名前を[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]検出、次の表に示すように、テーブルまたはビューの名前に基づきます。</span><span class="sxs-lookup"><span data-stu-id="01e4a-114">The name of the WCF client generated for the basic operations that the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] discovers is based on the name of the table or view, as listed in the following table.</span></span>  


|     <span data-ttu-id="01e4a-115">成果物</span><span class="sxs-lookup"><span data-stu-id="01e4a-115">Artifact</span></span>     |                     <span data-ttu-id="01e4a-116">WCF クライアント名</span><span class="sxs-lookup"><span data-stu-id="01e4a-116">WCF Client Name</span></span>                      |
|------------------|----------------------------------------------------------|
| <span data-ttu-id="01e4a-117">インターフェイス テーブル</span><span class="sxs-lookup"><span data-stu-id="01e4a-117">Interface tables</span></span> | <span data-ttu-id="01e4a-118">[APP_NAME] InterfaceTables_*[SCHEMA]\\*[TABLE_NAME] のクライアント</span><span class="sxs-lookup"><span data-stu-id="01e4a-118">InterfaceTables_[APP_NAME]*[SCHEMA]\\*[TABLE_NAME]Client</span></span> |
| <span data-ttu-id="01e4a-119">インターフェイス ビュー</span><span class="sxs-lookup"><span data-stu-id="01e4a-119">Interface views</span></span>  |  <span data-ttu-id="01e4a-120">[APP_NAME] InterfaceViews_*[SCHEMA]\\*[VIEW_NAME] クライアント</span><span class="sxs-lookup"><span data-stu-id="01e4a-120">InterfaceViews_[APP_NAME]*[SCHEMA]\\*[VIEW_NAME]Client</span></span>  |

 <span data-ttu-id="01e4a-121">[構成] は、Oracle E-business Suite のアプリケーションの実際の名前を =たとえば、ヘルプです。</span><span class="sxs-lookup"><span data-stu-id="01e4a-121">[APP_NAME] = Actual name of the Oracle E-Business Suite application; for example, FND.</span></span>  

 <span data-ttu-id="01e4a-122">[スキーマ] のアイテムのコレクションを =たとえば、アプリです。</span><span class="sxs-lookup"><span data-stu-id="01e4a-122">[SCHEMA] = Collection of artifacts; for example, APPS.</span></span>  

 <span data-ttu-id="01e4a-123">[TABLE_NAME] テーブルの名前を =たとえば、MS_SAMPLE_EMPLOYEE です。</span><span class="sxs-lookup"><span data-stu-id="01e4a-123">[TABLE_NAME] = The name of the table; for example, MS_SAMPLE_EMPLOYEE.</span></span>  

 <span data-ttu-id="01e4a-124">[VIEW_NAME] ビューの名前を =たとえば、MS_SAMPLE_EMPLOYEE_View です。</span><span class="sxs-lookup"><span data-stu-id="01e4a-124">[VIEW_NAME] = The name of the view; for example, MS_SAMPLE_EMPLOYEE_View.</span></span>  

### <a name="method-signature-for-invoking-operations-on-tables"></a><span data-ttu-id="01e4a-125">テーブルに対する操作を呼び出すためのメソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="01e4a-125">Method Signature for Invoking Operations on Tables</span></span>  
 <span data-ttu-id="01e4a-126">テーブルでの基本的な操作のメソッド シグネチャを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-126">The following table shows the method signatures for the basic operations on an table.</span></span> <span data-ttu-id="01e4a-127">署名は、ビューの名前空間と名前のテーブルを置換する点を除いて表示は、同じです。</span><span class="sxs-lookup"><span data-stu-id="01e4a-127">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  

|<span data-ttu-id="01e4a-128">演算</span><span class="sxs-lookup"><span data-stu-id="01e4a-128">Operation</span></span>|<span data-ttu-id="01e4a-129">メソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="01e4a-129">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="01e4a-130">Insert</span><span class="sxs-lookup"><span data-stu-id="01e4a-130">Insert</span></span>|<span data-ttu-id="01e4a-131">文字列挿入 (InsertRecord [レコード セット)。</span><span class="sxs-lookup"><span data-stu-id="01e4a-131">string Insert(InsertRecord[] RECORDSET);</span></span>|  
|<span data-ttu-id="01e4a-132">Select</span><span class="sxs-lookup"><span data-stu-id="01e4a-132">Select</span></span>|<span data-ttu-id="01e4a-133">SelectRecord] を選択します (文字列それら、文字列フィルター)</span><span class="sxs-lookup"><span data-stu-id="01e4a-133">SelectRecord[] Select(string COLUMN_NAMES, string FILTER);</span></span>|  
|<span data-ttu-id="01e4a-134">更新</span><span class="sxs-lookup"><span data-stu-id="01e4a-134">Update</span></span>|<span data-ttu-id="01e4a-135">文字列の更新プログラム (UpdateRecord RECORDSET、文字列フィルター。)</span><span class="sxs-lookup"><span data-stu-id="01e4a-135">string Update(UpdateRecord RECORDSET, string FILTER);</span></span>|  
|<span data-ttu-id="01e4a-136">DELETE</span><span class="sxs-lookup"><span data-stu-id="01e4a-136">Delete</span></span>|<span data-ttu-id="01e4a-137">文字列の削除 (文字列フィルター)</span><span class="sxs-lookup"><span data-stu-id="01e4a-137">string Delete(string FILTER);</span></span>|  

 <span data-ttu-id="01e4a-138">例として、次のコードが生成され、WCF クライアント クラスのメソッド シグネチャは、削除、挿入、選択、および更新の既定のアプリ スキーマ MS_SAMPLE_EMPLOYEE インターフェイス テーブルを操作します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-138">As an example, the following code shows the method signatures for a WCF client class generated for the Delete, Insert, Select and Update operations on the MS_SAMPLE_EMPLOYEE interface table under the default APPS schema.</span></span>  

```  
public partial class InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient : System.ServiceModel.ClientBase<InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE>, InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE {      
    public SelectRecord[] Select(string COLUMN_NAMES, string FILTER);  

    public string Insert(InsertRecord[] RECORDSET);  

    public string Update(UpdateRecord RECORDSET, string FILTER);  

    public string Delete(string FILTER);  
}  
```  

 <span data-ttu-id="01e4a-139">このスニペットで**InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient**によって生成された OracleEBSBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-139">In this snippet, **InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient** is the name of the WCF class in the OracleEBSBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  

### <a name="parameters-for-table-operations"></a><span data-ttu-id="01e4a-140">テーブル操作のパラメーター</span><span class="sxs-lookup"><span data-stu-id="01e4a-140">Parameters for Table Operations</span></span>  
 <span data-ttu-id="01e4a-141">このセクションでは、各テーブルの操作に必要なパラメーターを提供します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-141">This section provides the parameters required by each table operation</span></span>  

 <span data-ttu-id="01e4a-142">**操作を選択します。**</span><span class="sxs-lookup"><span data-stu-id="01e4a-142">**Select Operation**</span></span>  

|<span data-ttu-id="01e4a-143">それら</span><span class="sxs-lookup"><span data-stu-id="01e4a-143">COLUMN_NAMES</span></span>|<span data-ttu-id="01e4a-144">FILTER</span><span class="sxs-lookup"><span data-stu-id="01e4a-144">FILTER</span></span>|  
|-------------------|------------|  
|<span data-ttu-id="01e4a-145">は、ターゲット内の列名のコンマ区切りの一覧たとえば、「EMP_NO, 指定」です。</span><span class="sxs-lookup"><span data-stu-id="01e4a-145">A comma-delimited list of column names in the target; for example, "EMP_NO, DESIGNATION".</span></span> <span data-ttu-id="01e4a-146">列の一覧には、結果セットで返される対象の列を指定します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-146">The column list specifies the columns of the target that should be returned in the result set.</span></span> <span data-ttu-id="01e4a-147">列リストで指定されていない列は、返されたレコード セット内の .NET の既定値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="01e4a-147">Columns not specified in the column list will be set to their .NET default values in the returned record set.</span></span> <span data-ttu-id="01e4a-148">Nillable 列は、この値は**null**します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-148">For nillable columns, this value is **null**.</span></span>|<span data-ttu-id="01e4a-149">クエリの対象の行を指定する WHERE 句の内容たとえば、"指定 = 'マネージャー'"です。</span><span class="sxs-lookup"><span data-stu-id="01e4a-149">The contents of a WHERE clause that specifies the target rows of the query; for example, "Designation = 'Manager'".</span></span> <span data-ttu-id="01e4a-150">このパラメーターを設定する**null**をターゲットのすべての行を返します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-150">You can set this parameter to **null** to return all rows of the target.</span></span>|  

 <span data-ttu-id="01e4a-151">Select 操作の戻り値は、指定した列と行を含む厳密に型指定された結果セットです。</span><span class="sxs-lookup"><span data-stu-id="01e4a-151">The return value for a Select operation is a strongly-typed result set that contains the specified columns and rows.</span></span>  

 <span data-ttu-id="01e4a-152">**挿入操作**</span><span class="sxs-lookup"><span data-stu-id="01e4a-152">**Insert Operation**</span></span>  

|<span data-ttu-id="01e4a-153">挿入操作の種類</span><span class="sxs-lookup"><span data-stu-id="01e4a-153">Insert operation type</span></span>|<span data-ttu-id="01e4a-154">レコード セット</span><span class="sxs-lookup"><span data-stu-id="01e4a-154">RECORDSET</span></span>|  
|---------------------------|---------------|  
|<span data-ttu-id="01e4a-155">複数のレコード</span><span class="sxs-lookup"><span data-stu-id="01e4a-155">Multiple record</span></span>|<span data-ttu-id="01e4a-156">テーブルに挿入する必要があります INSERTRECORDS のコレクション。</span><span class="sxs-lookup"><span data-stu-id="01e4a-156">A collection of INSERTRECORDS that should be inserted into the table.</span></span>|  

 <span data-ttu-id="01e4a-157">挿入操作の戻り値では、挿入された行の数です。</span><span class="sxs-lookup"><span data-stu-id="01e4a-157">The return value for an Insert operation is the number of rows inserted.</span></span>  

 <span data-ttu-id="01e4a-158">**更新操作**</span><span class="sxs-lookup"><span data-stu-id="01e4a-158">**Update Operation**</span></span>  

|<span data-ttu-id="01e4a-159">レコード セット</span><span class="sxs-lookup"><span data-stu-id="01e4a-159">RECORDSET</span></span>|<span data-ttu-id="01e4a-160">FILTER</span><span class="sxs-lookup"><span data-stu-id="01e4a-160">FILTER</span></span>|  
|---------------|------------|  
|<span data-ttu-id="01e4a-161">テーブルで更新されるレコードのコレクション。</span><span class="sxs-lookup"><span data-stu-id="01e4a-161">A collection of records that should be updated in the table.</span></span>|<span data-ttu-id="01e4a-162">クエリの対象の行を指定する WHERE 句の内容たとえば、"指定 = 'マネージャー'"です。</span><span class="sxs-lookup"><span data-stu-id="01e4a-162">The contents of a WHERE clause that specifies the target rows of the query; for example, "Designation = 'Manager'".</span></span> <span data-ttu-id="01e4a-163">このパラメーターを設定する**null**をターゲットのすべての行を返します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-163">You can set this parameter to **null** to return all rows of the target.</span></span>|  

 <span data-ttu-id="01e4a-164">更新操作の戻り値では、更新された行の数です。</span><span class="sxs-lookup"><span data-stu-id="01e4a-164">The return value for an Update operation is the number of rows updated.</span></span>  

 <span data-ttu-id="01e4a-165">**削除操作**</span><span class="sxs-lookup"><span data-stu-id="01e4a-165">**Delete Operation**</span></span>  

 <span data-ttu-id="01e4a-166">操作は、削除は、削除する行を指定する WHERE 句を入力します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-166">The Delete operation takes as input a WHERE clause that specifies the rows to be deleted.</span></span> <span data-ttu-id="01e4a-167">削除操作の戻り値では、削除された行の数です。</span><span class="sxs-lookup"><span data-stu-id="01e4a-167">The return value for a Delete operation is the number of rows deleted.</span></span>  

## <a name="creating-a-wcf-client-to-invoke-operations-on-interface-tables-and-interface-views"></a><span data-ttu-id="01e4a-168">インターフェイス テーブルでの操作を呼び出すための WCF クライアントを作成してビューのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="01e4a-168">Creating a WCF Client to Invoke Operations on Interface Tables and Interface Views</span></span>  
 <span data-ttu-id="01e4a-169">汎用的な一連の WCF クライアントを使用して Oracle E-business Suite での操作を実行するために必要なアクションは、一連のタスクで説明されている[Oracle E-business Suite アダプターを使用した WCF チャネル モデルの概要](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-169">The generic set of actions required to perform an operation on Oracle E-Business Suite using a WCF client involves a set of tasks described in [Overview of the WCF channel model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md).</span></span> <span data-ttu-id="01e4a-170">このセクションでは、基本的な Insert、Select、Update、インターフェイス テーブルで削除操作を呼び出すための WCF クライアントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-170">This section describes how to create a WCF client to invoke basic Insert, Select, Update, Delete operations on an interface table.</span></span>  

#### <a name="to-create-a-wcf-client-to-perform-operations-on-tables"></a><span data-ttu-id="01e4a-171">テーブルに対する操作を実行する WCF クライアントを作成するには</span><span class="sxs-lookup"><span data-stu-id="01e4a-171">To create a WCF client to perform operations on tables</span></span>  

1. <span data-ttu-id="01e4a-172">Visual Studio で Visual c# プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-172">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="01e4a-173">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-173">For this topic, create a console application.</span></span>  

2. <span data-ttu-id="01e4a-174">Insert、Select、Update、WCF クライアント クラスを生成し、MS_SAMPLE_EMPLOYEE インターフェイス テーブルに対する操作を削除します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-174">Generate the WCF client class for the Insert, Select, Update, and Delete operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="01e4a-175">WCF クライアント クラスを生成する詳細については、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-175">For more information about generating a WCF client class, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="01e4a-176">WCF クライアント クラスを生成する前に必ず設定して、 **EnableBizTalkCompatibilityMode**プロパティを false にバインドします。</span><span class="sxs-lookup"><span data-stu-id="01e4a-176">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  

3. <span data-ttu-id="01e4a-177">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.OracleEBS`と`Microsoft.ServiceModel.Channels`します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-177">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS` and `Microsoft.ServiceModel.Channels`.</span></span>  

4. <span data-ttu-id="01e4a-178">Program.cs ファイルを開き、次の名前空間を追加します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-178">Open the Program.cs file and add the following namespaces:</span></span>  

   -   `Microsoft.Adapters.OracleEBS`  

   -   `System.ServiceModel`  

5. <span data-ttu-id="01e4a-179">Program.cs ファイルを開き、次のスニペットの説明に従って、クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-179">Open the Program.cs file and create a client as described in the snippet below.</span></span>  

   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
   InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient client = new InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient(binding, address);  
   ```  

    <span data-ttu-id="01e4a-180">このスニペットで`InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient`OracleEBSBindingClient.cs で定義されている WCF クライアントです。</span><span class="sxs-lookup"><span data-stu-id="01e4a-180">In this snippet, `InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient` is the WCF client defined in OracleEBSBindingClient.cs.</span></span> <span data-ttu-id="01e4a-181">このファイルがによって生成された、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-181">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="01e4a-182">このスニペットでは、アプリケーション コードで明示的にバインディングとエンドポイント アドレスを指定するだけ。</span><span class="sxs-lookup"><span data-stu-id="01e4a-182">In this snippet, you explicitly specify the binding and endpoint address in your application code.</span></span> <span data-ttu-id="01e4a-183">これらの値を使用するには、アプリケーション構成ファイルから app.config、によって生成されることも、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-183">You can use these values from the application configuration file, app.config, also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="01e4a-184">クライアント バインディングを指定する、さまざまな方法の詳細については、次を参照してください。 [Oracle E-business suite バインド クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-184">For more information on the different ways of specifying client binding, see [Configure a client binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  

6. <span data-ttu-id="01e4a-185">クライアントの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-185">Set the credentials for the client.</span></span>  

   ```  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  

7. <span data-ttu-id="01e4a-186">インターフェイス テーブルで操作を実行しているため、アプリケーションのコンテキストを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01e4a-186">Because you are performing an operation on an interface table, you must set the application context.</span></span> <span data-ttu-id="01e4a-187">この例で、アプリケーションのコンテキストの設定を指定する、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="01e4a-187">In this example, to set the application context, you specify the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="01e4a-188">アプリケーションのコンテキストの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-188">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  

   ```  
   binding.OracleUserName = "myOracleEBSUserName";  
   binding.OraclePassword = "myOracleEBSPassword";  
   binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
   ```  

8. <span data-ttu-id="01e4a-189">次のスニペットで説明されているように、クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="01e4a-189">Open the client as described in the snippet below:</span></span>  

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

9. <span data-ttu-id="01e4a-190">MS_SAMPLE_EMPLOYEE テーブルに対する挿入操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-190">Invoke the Insert operation on the MS_SAMPLE_EMPLOYEE table.</span></span>  

    ```  
    Console.WriteLine("The application will insert a record in the MS_SAMPLE_EMPLOYEE interface table");  

    // The date values cannot contain time zone information. Hence, you must use  
    // DateTimeKind.Unspecified to not include the time zone information.  
    DateTime date = new DateTime(DateTime.Now.Ticks, DateTimeKind.Unspecified);  

    string result;  

    InsertRecord[] recordSet = new InsertRecord[1];  

    EMP_NO__COMPLEX_TYPE emp_no = new EMP_NO__COMPLEX_TYPE();  
    emp_no.Value = "10007";  

    NAME__COMPLEX_TYPE name = new NAME__COMPLEX_TYPE();  
    name.Value = "John Smith";  

    DESIGNATION__COMPLEX_TYPE desig = new DESIGNATION__COMPLEX_TYPE();  
    desig.Value = "Manager";  

    SALARY__COMPLEX_TYPE salary = new SALARY__COMPLEX_TYPE();  
    salary.Value = "500000";  

    JOIN_DATE__COMPLEX_TYPE doj = new JOIN_DATE__COMPLEX_TYPE();  
    doj.Value = date;  

    recordSet[0] = new InsertRecord();  
    recordSet[0].EMP_NO = emp_no;  
    recordSet[0].NAME = name;  
    recordSet[0].DESIGNATION = desig;  
    recordSet[0].SALARY = salary;  
    recordSet[0].JOIN_DATE = doj;  

    try  
    {  
       result = client.Insert(recordSet);   
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  

    Console.WriteLine("Number of records inserted= " + result);  
    Console.WriteLine("Press any key to continue...");  
    Console.ReadLine();  

    ```  

     <span data-ttu-id="01e4a-191">Select を実行する前のコード スニペットを置き換えることができます更新、または同様の操作を削除します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-191">You can replace the preceding code snippet to perform Select, Update, or Delete operations as well.</span></span> <span data-ttu-id="01e4a-192">単一のアプリケーションですべての操作を実行するコード スニペットを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="01e4a-192">You can also append the code snippets to perform all operation in a single application.</span></span> <span data-ttu-id="01e4a-193">これらの操作を実行する方法については、コードのスニペットを参照してください。[選択操作](#BKMK_Select)、[更新操作](#BKMK_Update)、と[Delete 操作](#BKMK_Delete)それぞれします。</span><span class="sxs-lookup"><span data-stu-id="01e4a-193">For code snippets on how to perform these operations, see [Select Operation](#BKMK_Select), [Update Operation](#BKMK_Update), and [Delete Operation](#BKMK_Delete) respectively.</span></span>  

10. <span data-ttu-id="01e4a-194">次のスニペットの説明に従って、クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="01e4a-194">Close the client as described in the snippet below:</span></span>  

    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  

11. <span data-ttu-id="01e4a-195">プロジェクトをビルドし、それを実行します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-195">Build the project and then run it.</span></span> <span data-ttu-id="01e4a-196">アプリケーションでは、MS_SAMPLE_EMPLOYEE テーブルにレコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-196">The application inserts a record in the MS_SAMPLE_EMPLOYEE table.</span></span>  

###  <a name="BKMK_Select"></a> <span data-ttu-id="01e4a-197">操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-197">Select Operation</span></span>  
 <span data-ttu-id="01e4a-198">次のコードでは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルを対象とする操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-198">The following code shows a Select operation that targets the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="01e4a-199">選択操作では、テーブルに挿入された最後のレコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-199">The Select operation selects the last record inserted into the table.</span></span> <span data-ttu-id="01e4a-200">返されるレコードは、コンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="01e4a-200">The returned record is written to the console.</span></span>  

```  
Console.WriteLine("The application will now select the last inserted record");  
SelectRecord[] selectRecords;  
try  
{  
   selectRecords = client.Select("*", "WHERE EMP_NO LIKE 10007");  
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
   Console.WriteLine("Employee ID         : " + selectRecords[i].EMP_NO);  
   Console.WriteLine("Employee Name       : " + selectRecords[i].NAME);  
   Console.WriteLine("Employee Desigation : " + selectRecords[i].DESIGNATION);  
   Console.WriteLine("Employee Salary     : " + selectRecords[i].SALARY);  
   Console.WriteLine();  
}  
Console.WriteLine("********************************************");  
Console.WriteLine("Press any key to continue ...");  
Console.ReadLine();  
```  

###  <a name="BKMK_Update"></a> <span data-ttu-id="01e4a-201">更新操作</span><span class="sxs-lookup"><span data-stu-id="01e4a-201">Update Operation</span></span>  
 <span data-ttu-id="01e4a-202">次のコードでは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルを対象とする更新操作を示します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-202">The following code shows an Update operation that targets the MS_SAMPLE_EMPLOYEE interface table.</span></span>  

```  
Console.WriteLine("The application will now update the employee name in the newly inserted record");  
string recordsUpdated;  
UpdateRecord updateRecordSet = new UpdateRecord();  
updateRecordSet.NAME = "Tom Smith";  
updateRecordSet.DESIGNATION = "Accountant";  

try  
{  
   recordsUpdated = client.Update(updateRecordSet, "WHERE EMP_NO LIKE 10007");  
}  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  

Console.WriteLine("No of records updated: " + recordsUpdated);  
Console.WriteLine("Press any key to continue...");  
Console.ReadLine();  
```  

###  <a name="BKMK_Delete"></a> <span data-ttu-id="01e4a-203">削除操作</span><span class="sxs-lookup"><span data-stu-id="01e4a-203">Delete Operation</span></span>  
 <span data-ttu-id="01e4a-204">次のコードでは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルを対象とする削除操作を示します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-204">The following code shows a Delete operation that targets the MS_SAMPLE_EMPLOYEE interface table.</span></span>  

```  
Console.WriteLine("The sample will now delete the record that it first inserted");  
string deletedRecords;  
try  
{  
   deletedRecords = client.Delete("WHERE EMP_NO LIKE 10007");  
}  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
Console.WriteLine("No of records deleted: " + deletedRecords);  
Console.WriteLine("Press any key to exit...");  
Console.ReadLine();  
```  

## <a name="see-also"></a><span data-ttu-id="01e4a-205">参照</span><span class="sxs-lookup"><span data-stu-id="01e4a-205">See Also</span></span>  
 [<span data-ttu-id="01e4a-206">WCF サービス モデルを使用して Oracle E-business Suite のアプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="01e4a-206">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)