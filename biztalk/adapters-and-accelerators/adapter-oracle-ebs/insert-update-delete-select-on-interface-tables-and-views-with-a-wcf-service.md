---
title: "挿入、更新、削除、またはインターフェイスのテーブルとビューの WCF サービス モデルを使用して操作の選択 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae613c0e-4d9a-4c66-99e4-dd0443f1d495
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fc9e3968b760be10b428e39662ec3d09db490cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="insert-update-delete-or-select-operations-on-interface-tables-and-views-using-the-wcf-service-model"></a><span data-ttu-id="b0bc6-102">挿入、更新、削除、またはインターフェイスのテーブルとビューの WCF サービス モデルを使用して操作の選択</span><span class="sxs-lookup"><span data-stu-id="b0bc6-102">Insert, update, delete, or select operations on interface tables and views using the WCF service model</span></span>
<span data-ttu-id="b0bc6-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]インターフェイス テーブルの基本的な Insert、Select、Update、および Delete の操作のセットを検出します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] discovers a set of basic Insert, Select, Update, and Delete operations on interface tables.</span></span> <span data-ttu-id="b0bc6-104">これらの操作を使用すると、単純な Insert、Select、Update を実行し、対象のインターフェイス テーブルに対する WHERE 句で修飾されたステートメントを削除できます。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-104">By using these operations, you can perform simple Insert, Select, Update, and Delete statements qualified by a WHERE clause on a target interface table.</span></span> <span data-ttu-id="b0bc6-105">このトピックでは、WCF サービス モデルを使用してこれらの操作を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-105">This topic provides instructions on how to perform these operations using the WCF service model.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0bc6-106">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]のみを選択インターフェイス ビューで操作をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-106">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports only Select operations on interface views.</span></span>  
  
 <span data-ttu-id="b0bc6-107">アダプターがこれらの操作をサポートする方法の詳細については、次を参照してください。[インターフェイス テーブルとのインターフェイス ビューで操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)です。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-107">For more information about how the adapter supports these operations, see [Operations on Interface Tables and Interface Views](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="b0bc6-108">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="b0bc6-108">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="b0bc6-109">このトピックの例では、MS_SAMPLE_EMPLOYEE インターフェイス テーブルでの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-109">The example in this topic performs operations on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="b0bc6-110">サンプルに用意されているスクリプトを実行して、テーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-110">The table is created by running the script provided with the samples.</span></span> <span data-ttu-id="b0bc6-111">サンプルの詳細については、次を参照してください。 [Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-111">For more information about samples, see [Samples for the Oracle EBS adapter](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).</span></span> <span data-ttu-id="b0bc6-112">サンプルは、 **Interface_Table_Ops**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプルです。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-112">A sample, **Interface_Table_Ops**, which is based on this topic, is also provided with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="b0bc6-113">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="b0bc6-113">The WCF Client Class</span></span>  
 <span data-ttu-id="b0bc6-114">基本的な操作の生成、WCF クライアントの名前を[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]検出次の表に示すように、テーブルまたはビューの名前に基づきます。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-114">The name of the WCF client generated for the basic operations that the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] discovers is based on the name of the table or view, as listed in the following table.</span></span>  
  
|<span data-ttu-id="b0bc6-115">成果物</span><span class="sxs-lookup"><span data-stu-id="b0bc6-115">Artifact</span></span>|<span data-ttu-id="b0bc6-116">WCF クライアント名</span><span class="sxs-lookup"><span data-stu-id="b0bc6-116">WCF Client Name</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="b0bc6-117">インターフェイス テーブル</span><span class="sxs-lookup"><span data-stu-id="b0bc6-117">Interface tables</span></span>|<span data-ttu-id="b0bc6-118">InterfaceTables_ [APP_NAME] _ [SCHEMA]\_[TABLE_NAME] クライアント</span><span class="sxs-lookup"><span data-stu-id="b0bc6-118">InterfaceTables_[APP_NAME]_[SCHEMA]\_[TABLE_NAME]Client</span></span>|  
|<span data-ttu-id="b0bc6-119">インターフェイス ビュー</span><span class="sxs-lookup"><span data-stu-id="b0bc6-119">Interface views</span></span>|<span data-ttu-id="b0bc6-120">InterfaceViews_ [APP_NAME] _ [SCHEMA]\_[VIEW_NAME] クライアント</span><span class="sxs-lookup"><span data-stu-id="b0bc6-120">InterfaceViews_[APP_NAME]_[SCHEMA]\_[VIEW_NAME]Client</span></span>|  
  
 <span data-ttu-id="b0bc6-121">[構成]、Oracle E-business Suite アプリケーションの実際の名前を =たとえばのヘルプ。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-121">[APP_NAME] = Actual name of the Oracle E-Business Suite application; for example, FND.</span></span>  
  
 <span data-ttu-id="b0bc6-122">[スキーマ]; の成果物のコレクションを =たとえば、アプリです。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-122">[SCHEMA] = Collection of artifacts; for example, APPS.</span></span>  
  
 <span data-ttu-id="b0bc6-123">[TABLE_NAME] テーブルの名前を =たとえば、MS_SAMPLE_EMPLOYEE です。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-123">[TABLE_NAME] = The name of the table; for example, MS_SAMPLE_EMPLOYEE.</span></span>  
  
 <span data-ttu-id="b0bc6-124">[VIEW_NAME] ビューの名前を =たとえば、MS_SAMPLE_EMPLOYEE_View です。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-124">[VIEW_NAME] = The name of the view; for example, MS_SAMPLE_EMPLOYEE_View.</span></span>  
  
### <a name="method-signature-for-invoking-operations-on-tables"></a><span data-ttu-id="b0bc6-125">テーブルに対する操作を呼び出すためのメソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="b0bc6-125">Method Signature for Invoking Operations on Tables</span></span>  
 <span data-ttu-id="b0bc6-126">テーブル上の基本的な操作について、メソッド シグネチャを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-126">The following table shows the method signatures for the basic operations on an table.</span></span> <span data-ttu-id="b0bc6-127">署名は、ビューの名前空間と名前のテーブルを置換する点を除いて、表示は、同じです。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-127">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="b0bc6-128">操作</span><span class="sxs-lookup"><span data-stu-id="b0bc6-128">Operation</span></span>|<span data-ttu-id="b0bc6-129">メソッド シグネチャ</span><span class="sxs-lookup"><span data-stu-id="b0bc6-129">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="b0bc6-130">Insert</span><span class="sxs-lookup"><span data-stu-id="b0bc6-130">Insert</span></span>|<span data-ttu-id="b0bc6-131">文字列の挿入 (InsertRecord [レコード セット)。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-131">string Insert(InsertRecord[] RECORDSET);</span></span>|  
|<span data-ttu-id="b0bc6-132">Select</span><span class="sxs-lookup"><span data-stu-id="b0bc6-132">Select</span></span>|<span data-ttu-id="b0bc6-133">SelectRecord を選択 (それら、フィルターの文字列の文字列) です。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-133">SelectRecord[] Select(string COLUMN_NAMES, string FILTER);</span></span>|  
|<span data-ttu-id="b0bc6-134">Update</span><span class="sxs-lookup"><span data-stu-id="b0bc6-134">Update</span></span>|<span data-ttu-id="b0bc6-135">文字列の更新プログラム (UpdateRecord RECORDSET、フィルターの文字列です。)</span><span class="sxs-lookup"><span data-stu-id="b0bc6-135">string Update(UpdateRecord RECORDSET, string FILTER);</span></span>|  
|<span data-ttu-id="b0bc6-136">DELETE</span><span class="sxs-lookup"><span data-stu-id="b0bc6-136">Delete</span></span>|<span data-ttu-id="b0bc6-137">文字列の削除 (フィルターの文字列) です。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-137">string Delete(string FILTER);</span></span>|  
  
 <span data-ttu-id="b0bc6-138">たとえば、次のコードは生成された WCF クライアント クラスのメソッド シグネチャは、選択して 既定のアプリ スキーマ MS_SAMPLE_EMPLOYEE インターフェイス テーブルでの Update 操作、削除、挿入します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-138">As an example, the following code shows the method signatures for a WCF client class generated for the Delete, Insert, Select and Update operations on the MS_SAMPLE_EMPLOYEE interface table under the default APPS schema.</span></span>  
  
```  
public partial class InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient : System.ServiceModel.ClientBase<InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE>, InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE {      
    public SelectRecord[] Select(string COLUMN_NAMES, string FILTER);  
  
    public string Insert(InsertRecord[] RECORDSET);  
  
    public string Update(UpdateRecord RECORDSET, string FILTER);  
  
    public string Delete(string FILTER);  
}  
```  
  
 <span data-ttu-id="b0bc6-139">このスニペットで**InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient**によって生成された OracleEBSBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-139">In this snippet, **InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient** is the name of the WCF class in the OracleEBSBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
### <a name="parameters-for-table-operations"></a><span data-ttu-id="b0bc6-140">テーブル操作のパラメーター</span><span class="sxs-lookup"><span data-stu-id="b0bc6-140">Parameters for Table Operations</span></span>  
 <span data-ttu-id="b0bc6-141">このセクションでは、各テーブルの操作に必要なパラメーターを説明します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-141">This section provides the parameters required by each table operation</span></span>  
  
 <span data-ttu-id="b0bc6-142">**操作を選択します。**</span><span class="sxs-lookup"><span data-stu-id="b0bc6-142">**Select Operation**</span></span>  
  
|<span data-ttu-id="b0bc6-143">それら</span><span class="sxs-lookup"><span data-stu-id="b0bc6-143">COLUMN_NAMES</span></span>|<span data-ttu-id="b0bc6-144">FILTER</span><span class="sxs-lookup"><span data-stu-id="b0bc6-144">FILTER</span></span>|  
|-------------------|------------|  
|<span data-ttu-id="b0bc6-145">ターゲット内の列名のコンマ区切りの一覧たとえば、「EMP_NO, 表記」です。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-145">A comma-delimited list of column names in the target; for example, "EMP_NO, DESIGNATION".</span></span> <span data-ttu-id="b0bc6-146">列の一覧では、結果セットに返される対象の列を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-146">The column list specifies the columns of the target that should be returned in the result set.</span></span> <span data-ttu-id="b0bc6-147">列リストで指定されていない列は、返されるレコード セット内の .NET の既定値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-147">Columns not specified in the column list will be set to their .NET default values in the returned record set.</span></span> <span data-ttu-id="b0bc6-148">Nillable 列は、この値は**null**です。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-148">For nillable columns, this value is **null**.</span></span>|<span data-ttu-id="b0bc6-149">クエリの対象の行を指定する WHERE 句の内容たとえば、"表記 = 'Manager'"です。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-149">The contents of a WHERE clause that specifies the target rows of the query; for example, "Designation = 'Manager'".</span></span> <span data-ttu-id="b0bc6-150">このパラメーターを設定することができます**null**ターゲットのすべての行を取得します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-150">You can set this parameter to **null** to return all rows of the target.</span></span>|  
  
 <span data-ttu-id="b0bc6-151">Select 操作の戻り値は、指定された列と行を含む厳密に型指定された結果セットです。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-151">The return value for a Select operation is a strongly-typed result set that contains the specified columns and rows.</span></span>  
  
 <span data-ttu-id="b0bc6-152">**挿入操作**</span><span class="sxs-lookup"><span data-stu-id="b0bc6-152">**Insert Operation**</span></span>  
  
|<span data-ttu-id="b0bc6-153">挿入操作の種類</span><span class="sxs-lookup"><span data-stu-id="b0bc6-153">Insert operation type</span></span>|<span data-ttu-id="b0bc6-154">レコード セット</span><span class="sxs-lookup"><span data-stu-id="b0bc6-154">RECORDSET</span></span>|  
|---------------------------|---------------|  
|<span data-ttu-id="b0bc6-155">複数のレコード</span><span class="sxs-lookup"><span data-stu-id="b0bc6-155">Multiple record</span></span>|<span data-ttu-id="b0bc6-156">テーブルに挿入する必要があります INSERTRECORDS のコレクション。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-156">A collection of INSERTRECORDS that should be inserted into the table.</span></span>|  
  
 <span data-ttu-id="b0bc6-157">挿入操作の戻り値は、挿入された行の数です。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-157">The return value for an Insert operation is the number of rows inserted.</span></span>  
  
 <span data-ttu-id="b0bc6-158">**更新操作**</span><span class="sxs-lookup"><span data-stu-id="b0bc6-158">**Update Operation**</span></span>  
  
|<span data-ttu-id="b0bc6-159">レコード セット</span><span class="sxs-lookup"><span data-stu-id="b0bc6-159">RECORDSET</span></span>|<span data-ttu-id="b0bc6-160">FILTER</span><span class="sxs-lookup"><span data-stu-id="b0bc6-160">FILTER</span></span>|  
|---------------|------------|  
|<span data-ttu-id="b0bc6-161">テーブルで更新する必要があるレコードのコレクション。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-161">A collection of records that should be updated in the table.</span></span>|<span data-ttu-id="b0bc6-162">クエリの対象の行を指定する WHERE 句の内容たとえば、"表記 = 'Manager'"です。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-162">The contents of a WHERE clause that specifies the target rows of the query; for example, "Designation = 'Manager'".</span></span> <span data-ttu-id="b0bc6-163">このパラメーターを設定することができます**null**ターゲットのすべての行を取得します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-163">You can set this parameter to **null** to return all rows of the target.</span></span>|  
  
 <span data-ttu-id="b0bc6-164">更新操作の戻り値は、更新された行の数です。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-164">The return value for an Update operation is the number of rows updated.</span></span>  
  
 <span data-ttu-id="b0bc6-165">**削除操作**</span><span class="sxs-lookup"><span data-stu-id="b0bc6-165">**Delete Operation**</span></span>  
  
 <span data-ttu-id="b0bc6-166">操作は、削除は、削除する行を指定する WHERE 句を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-166">The Delete operation takes as input a WHERE clause that specifies the rows to be deleted.</span></span> <span data-ttu-id="b0bc6-167">削除操作の戻り値は、削除された行の数です。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-167">The return value for a Delete operation is the number of rows deleted.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-interface-tables-and-interface-views"></a><span data-ttu-id="b0bc6-168">インターフェイス テーブルに対する操作の呼び出しに WCF クライアントを作成してビューのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="b0bc6-168">Creating a WCF Client to Invoke Operations on Interface Tables and Interface Views</span></span>  
 <span data-ttu-id="b0bc6-169">WCF クライアントを使用して Oracle E-business Suite で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[Oracle E-business Suite アダプターで WCF チャネル モデルの概要](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-169">The generic set of actions required to perform an operation on Oracle E-Business Suite using a WCF client involves a set of tasks described in [Overview of the WCF channel model with the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md).</span></span> <span data-ttu-id="b0bc6-170">このセクションでは、基本的な Insert、Select、Update、インターフェイス テーブルに対する Delete 操作を呼び出すための WCF クライアントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-170">This section describes how to create a WCF client to invoke basic Insert, Select, Update, Delete operations on an interface table.</span></span>  
  
#### <a name="to-create-a-wcf-client-to-perform-operations-on-tables"></a><span data-ttu-id="b0bc6-171">テーブルに対する操作を実行する WCF クライアントを作成するには</span><span class="sxs-lookup"><span data-stu-id="b0bc6-171">To create a WCF client to perform operations on tables</span></span>  
  
1.  <span data-ttu-id="b0bc6-172">Visual Studio で Visual c# プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-172">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="b0bc6-173">このトピックでは、コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-173">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="b0bc6-174">Insert、Select、Update の WCF クライアント クラスを生成し、MS_SAMPLE_EMPLOYEE インターフェイス テーブルの操作を削除します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-174">Generate the WCF client class for the Insert, Select, Update, and Delete operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="b0bc6-175">詳細については、WCF クライアント クラスを生成する、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-175">For more information about generating a WCF client class, see [Generate a WCF client or a WCF service contract for Oracle E-Business Suite solution artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b0bc6-176">WCF クライアント クラスを生成する前に必ず設定してください、 **EnableBizTalkCompatibilityMode**プロパティを false にバインドします。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-176">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3.  <span data-ttu-id="b0bc6-177">ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.OracleEBS`と`Microsoft.ServiceModel.Channels`です。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-177">In the Solution Explorer, add reference to `Microsoft.Adapters.OracleEBS` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4.  <span data-ttu-id="b0bc6-178">Program.cs ファイルを開き、次の名前空間を追加します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-178">Open the Program.cs file and add the following namespaces:</span></span>  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
5.  <span data-ttu-id="b0bc6-179">Program.cs ファイルを開き、次のスニペットの説明に従って、クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-179">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
    InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient client = new InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient(binding, address);  
    ```  
  
     <span data-ttu-id="b0bc6-180">このスニペットで`InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient`OracleEBSBindingClient.cs で定義された WCF クライアントです。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-180">In this snippet, `InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient` is the WCF client defined in OracleEBSBindingClient.cs.</span></span> <span data-ttu-id="b0bc6-181">このファイルにより生成されて、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-181">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b0bc6-182">このスニペットでは、アプリケーション コードで明示的にバインドとエンドポイント アドレスを指定するだけです。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-182">In this snippet, you explicitly specify the binding and endpoint address in your application code.</span></span> <span data-ttu-id="b0bc6-183">これらの値を使用するには、アプリケーション構成ファイルから、app.config、によって生成されるも、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-183">You can use these values from the application configuration file, app.config, also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="b0bc6-184">クライアント バインディングを指定するさまざまな方法の詳細については、次を参照してください。 [for Oracle E-business Suite バインド クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)です。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-184">For more information on the different ways of specifying client binding, see [Configure a client binding for the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).</span></span>  
  
6.  <span data-ttu-id="b0bc6-185">クライアントの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-185">Set the credentials for the client.</span></span>  
  
    ```  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
7.  <span data-ttu-id="b0bc6-186">インターフェイス テーブルに対する操作を実行しているため、アプリケーションのコンテキストを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-186">Because you are performing an operation on an interface table, you must set the application context.</span></span> <span data-ttu-id="b0bc6-187">この例では、アプリケーションのコンテキストを設定するを指定する、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-187">In this example, to set the application context, you specify the **OracleUserName**, **OraclePassword**, and **OracleEBSResponsibilityName** binding properties.</span></span> <span data-ttu-id="b0bc6-188">アプリケーション コンテキストの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-188">For more information about application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
8.  <span data-ttu-id="b0bc6-189">次のスニペット」の説明に従って、クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-189">Open the client as described in the snippet below:</span></span>  
  
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
  
9. <span data-ttu-id="b0bc6-190">MS_SAMPLE_EMPLOYEE テーブルに対する挿入操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-190">Invoke the Insert operation on the MS_SAMPLE_EMPLOYEE table.</span></span>  
  
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
  
     <span data-ttu-id="b0bc6-191">Select を実行する上記のコード スニペットを置き換えることができますを更新、または同様の操作を削除します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-191">You can replace the preceding code snippet to perform Select, Update, or Delete operations as well.</span></span> <span data-ttu-id="b0bc6-192">1 つのアプリケーションのすべての操作を実行するコード スニペットを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-192">You can also append the code snippets to perform all operation in a single application.</span></span> <span data-ttu-id="b0bc6-193">これらの操作を実行する方法のコード スニペットを参照してください。[操作の選択](#BKMK_Select)、[更新操作](#BKMK_Update)、および[削除操作](#BKMK_Delete)それぞれします。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-193">For code snippets on how to perform these operations, see [Select Operation](#BKMK_Select), [Update Operation](#BKMK_Update), and [Delete Operation](#BKMK_Delete) respectively.</span></span>  
  
10. <span data-ttu-id="b0bc6-194">次のスニペット」の説明に従って、クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-194">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
11. <span data-ttu-id="b0bc6-195">プロジェクトをビルドし、それを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-195">Build the project and then run it.</span></span> <span data-ttu-id="b0bc6-196">アプリケーションは、MS_SAMPLE_EMPLOYEE テーブルにレコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-196">The application inserts a record in the MS_SAMPLE_EMPLOYEE table.</span></span>  
  
###  <a name="BKMK_Select"></a><span data-ttu-id="b0bc6-197">操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-197">Select Operation</span></span>  
 <span data-ttu-id="b0bc6-198">次のコードは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルを対象とする選択操作を示しています。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-198">The following code shows a Select operation that targets the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="b0bc6-199">選択操作は、テーブルに挿入された最後のレコードを選択します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-199">The Select operation selects the last record inserted into the table.</span></span> <span data-ttu-id="b0bc6-200">返されたレコードは、コンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-200">The returned record is written to the console.</span></span>  
  
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
  
###  <a name="BKMK_Update"></a><span data-ttu-id="b0bc6-201">更新操作</span><span class="sxs-lookup"><span data-stu-id="b0bc6-201">Update Operation</span></span>  
 <span data-ttu-id="b0bc6-202">次のコードでは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルを対象とする更新操作を示します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-202">The following code shows an Update operation that targets the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
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
  
###  <a name="BKMK_Delete"></a><span data-ttu-id="b0bc6-203">削除操作</span><span class="sxs-lookup"><span data-stu-id="b0bc6-203">Delete Operation</span></span>  
 <span data-ttu-id="b0bc6-204">次のコードは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルを対象とする削除操作を示しています。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-204">The following code shows a Delete operation that targets the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b0bc6-205">参照</span><span class="sxs-lookup"><span data-stu-id="b0bc6-205">See Also</span></span>  
 [<span data-ttu-id="b0bc6-206">WCF サービス モデルを使用して Oracle E-business Suite アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="b0bc6-206">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)