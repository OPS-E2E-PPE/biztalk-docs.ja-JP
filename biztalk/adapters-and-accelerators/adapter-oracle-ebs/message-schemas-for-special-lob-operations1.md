---
title: 特殊な LOB Operations1 のメッセージ スキーマ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2e418a6-8bc7-42d9-9672-a9c149f32778
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b57e329d1de4740cac230cbb1e8151697d293dc7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962584"
---
# <a name="message-schemas-for-special-lob-operations"></a><span data-ttu-id="f1183-102">特殊な LOB 操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="f1183-102">Message Schemas for Special LOB Operations</span></span>
<span data-ttu-id="f1183-103">Read_\<LOBColName\>と Update_\<LOBColName\>テーブルおよび LOB 列を含むビューの操作が表示された場所\<LOBColName\>テーブルの LOB 列は、または表示します。</span><span class="sxs-lookup"><span data-stu-id="f1183-103">The Read_\<LOBColName\> and Update_\<LOBColName\> operations are surfaced for tables and views that contain LOB columns, where \<LOBColName\> is the LOB column in the table or view.</span></span> <span data-ttu-id="f1183-104">これらの操作では、base64Binary でエンコードされたデータのストリームとして、LOB データを読み書きできます。</span><span class="sxs-lookup"><span data-stu-id="f1183-104">These operations enable you to read or write the LOB data as a stream of base64Binary-encoded data.</span></span> <span data-ttu-id="f1183-105">1 つの行に LOB データの 1 つの列上で動作します。</span><span class="sxs-lookup"><span data-stu-id="f1183-105">They operate on a single column of LOB data in a single row.</span></span>  
  
 <span data-ttu-id="f1183-106">Read_ の概要については\<LOBColName\>と Update_\<LOBColName\>操作し、Oracle LOB データ型のサポートされている、次を参照してください[インターフェイス テーブル、インターフェイス ビュー、テーブルに対する操作と。LOB データを含むビュー](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)です。</span><span class="sxs-lookup"><span data-stu-id="f1183-106">For an overview of the Read_\<LOBColName\> and Update_\<LOBColName\> operations and of the Oracle LOB data types supported, see [Operations on Interface Tables, Interface Views, Tables, and Views That Contain LOB Data](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md).</span></span>  
  
## <a name="message-structure-of-lob-data-type-operations"></a><span data-ttu-id="f1183-107">LOB データ型の操作のメッセージの構造</span><span class="sxs-lookup"><span data-stu-id="f1183-107">Message Structure of LOB Data-Type Operations</span></span>  
 <span data-ttu-id="f1183-108">次の表では、要求と応答メッセージの構造を示します、Read_ の\<LOBColName\>と Update_\<LOBColName\>操作します。</span><span class="sxs-lookup"><span data-stu-id="f1183-108">The following table shows the structure of the request and response messages for the Read_\<LOBColName\> and Update_\<LOBColName\> operations.</span></span> <span data-ttu-id="f1183-109">操作の対象テーブルでは、メッセージのアクションで指定され、ターゲットの名前空間にも表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1183-109">The target table for the operation is specified in the message action and also appears in the target namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1183-110">表の後に、エンティティの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1183-110">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="f1183-111">操作</span><span class="sxs-lookup"><span data-stu-id="f1183-111">Operation</span></span>|<span data-ttu-id="f1183-112">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="f1183-112">XML Message</span></span>|<span data-ttu-id="f1183-113">Description</span><span class="sxs-lookup"><span data-stu-id="f1183-113">Description</span></span>|  
|---------------|-----------------|-----------------|  
|<span data-ttu-id="f1183-114">Read_\<LOBColName\></span><span class="sxs-lookup"><span data-stu-id="f1183-114">Read_\<LOBColName\></span></span>|`<Read_[LOBColName] xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]">  <FILTER>[WHERE_clause]</FILTER></Read_[LOBColName]>`|<span data-ttu-id="f1183-115">LOB データ、一致する行が where フィルター要素で指定された句が返されます。</span><span class="sxs-lookup"><span data-stu-id="f1183-115">The LOB data in the row that matches the where clause specified in the FILTER element is returned.</span></span> <span data-ttu-id="f1183-116">Where 句が 1 つの行のみを一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1183-116">The where clause should match only a single row.</span></span> <span data-ttu-id="f1183-117">1 つ以上の一致する行がある場合、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="f1183-117">If there is more than one matching row, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] will throw an exception.</span></span>|  
|<span data-ttu-id="f1183-118">Read_\<LOBColName\>応答</span><span class="sxs-lookup"><span data-stu-id="f1183-118">Read_\<LOBColName\> Response</span></span>|`<Read_[LOBColName]Response xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]">  <Read_[LOBColName]Result>    [LOB_DATA]  </Read_[LOBColName]Result></Read_[LOBColName]Response>`|<span data-ttu-id="f1183-119">LOB データは、base64Binary でエンコードされたデータのストリームとして返されます。</span><span class="sxs-lookup"><span data-stu-id="f1183-119">The LOB data is returned as a stream of base64Binary encoded data.</span></span>|  
|<span data-ttu-id="f1183-120">Update_\<LOBColName\></span><span class="sxs-lookup"><span data-stu-id="f1183-120">Update_\<LOBColName\></span></span>|`<Update_[LOBColName] xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]">  <FILTER>[WHERE_clause]</LOB_COLUMN>  <DATA>[Value]</DATA></Update_[LOBColName]>`|<span data-ttu-id="f1183-121">LOB データ where に一致する行のフィルター要素で指定されている句は、データで更新、\<データ\>要素。</span><span class="sxs-lookup"><span data-stu-id="f1183-121">The LOB data in the row that matches the where clause specified in the FILTER element is updated with the data in the \<DATA\> element.</span></span> <span data-ttu-id="f1183-122">Where 句が 1 つの行のみを一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1183-122">The where clause should match only a single row.</span></span> <span data-ttu-id="f1183-123">1 つ以上の一致する行がある場合、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="f1183-123">If there is more than one matching row, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] throws an exception.</span></span><br /><br /> <span data-ttu-id="f1183-124">**注**BLOB 列の更新中に、\<データ\>要素に base64 でエンコードされた値が含まれて常にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1183-124">**Note** While updating BLOB columns, the \<DATA\> element must always contain a base64 encoded value.</span></span> <span data-ttu-id="f1183-125">CLOB、NCLOB、ため、\<データ\>要素は、文字列値を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="f1183-125">For CLOB and NCLOB, the \<DATA\> element can have string values.</span></span>|  
|<span data-ttu-id="f1183-126">Update_\<LOBColName\>応答</span><span class="sxs-lookup"><span data-stu-id="f1183-126">Update_\<LOBColName\> Response</span></span>|`<Update_[LOBColName]Response xmlns="[VERSION]/Tables/[SCHEMA]/[TABLE_NAME]"></Update_[LOBColName]Response>`|<span data-ttu-id="f1183-127">空の応答が返されます。</span><span class="sxs-lookup"><span data-stu-id="f1183-127">An empty response is returned.</span></span>|  
  
 <span data-ttu-id="f1183-128">エンティティの説明</span><span class="sxs-lookup"><span data-stu-id="f1183-128">Entity descriptions:</span></span>  
  
 <span data-ttu-id="f1183-129">[バージョン]、メッセージのバージョン文字列を =たとえば、"http://schemas.microsoft.com/OracleEBS/2008/05"です。</span><span class="sxs-lookup"><span data-stu-id="f1183-129">[VERSION] = The message version string; for example, "http://schemas.microsoft.com/OracleEBS/2008/05".</span></span>  
  
 <span data-ttu-id="f1183-130">[スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。</span><span class="sxs-lookup"><span data-stu-id="f1183-130">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="f1183-131">[TABLE_NAME] を対象となる、LOB の列を含むテーブルを =たとえば、顧客です。</span><span class="sxs-lookup"><span data-stu-id="f1183-131">[TABLE_NAME] = The table that contains the targeted LOB column; for example, CUSTOMER.</span></span>  
  
 <span data-ttu-id="f1183-132">[LOBCol_Name]、LOB の列の名前を =たとえば、写真。</span><span class="sxs-lookup"><span data-stu-id="f1183-132">[LOBCol_Name] = The name of a LOB column; for example, Photo.</span></span>  
  
 <span data-ttu-id="f1183-133">[WHERE_clause] に Oracle データベースの SELECT ステートメントです 1 つの行に一致する WHERE 句を =。たとえば、ID = 1 です。</span><span class="sxs-lookup"><span data-stu-id="f1183-133">[WHERE_clause] = An Oracle database SELECT statement WHERE clause that matches a single row; for example, ID = 1.</span></span>  
  
 <span data-ttu-id="f1183-134">[LOB_DATA] base64Binary 型の列のデータ、LOB を = です。</span><span class="sxs-lookup"><span data-stu-id="f1183-134">[LOB_DATA] = The LOB column data in base64Binary type.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f1183-135">メッセージ構造、Read_\<LOBColName\>と Update_\<LOBColName\>ビューでの操作と同じテーブルが操作の名前空間は、テーブルではなく、ビューを指定する点を除いて`<ReadLOB xmlns ="[VERSION]/Views/[SCHEMA]/[VIEW_NAME]">`。</span><span class="sxs-lookup"><span data-stu-id="f1183-135">The message structure for the Read_\<LOBColName\> and Update_\<LOBColName\> operations on views is the same as that on tables except that the namespace for the operation specifies a view rather than a table: `<ReadLOB xmlns ="[VERSION]/Views/[SCHEMA]/[VIEW_NAME]">`.</span></span>  
  
## <a name="message-actions-for-lob-data-type-operations"></a><span data-ttu-id="f1183-136">メッセージの動作の LOB データ型の操作</span><span class="sxs-lookup"><span data-stu-id="f1183-136">Message Actions for LOB Data-Type Operations</span></span>  
 <span data-ttu-id="f1183-137">次の表は、メッセージ アクションで使用される、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] 、Read_ の\<LOBColName\>と Update_\<LOBColName\>テーブルに対する操作です。</span><span class="sxs-lookup"><span data-stu-id="f1183-137">The following table shows the message actions that are used by the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] for the Read_\<LOBColName\> and Update_\<LOBColName\> operations on tables.</span></span> <span data-ttu-id="f1183-138">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]対象のテーブルを特定し、LOB 操作の列をテーブル名とメッセージのアクションで指定された LOB の列名を使用します。</span><span class="sxs-lookup"><span data-stu-id="f1183-138">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] uses the table name and the LOB column name specified in the message action to determine the target table and LOB column for the operation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1183-139">表の後に、エンティティの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1183-139">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="f1183-140">操作</span><span class="sxs-lookup"><span data-stu-id="f1183-140">Operation</span></span>|<span data-ttu-id="f1183-141">操作</span><span class="sxs-lookup"><span data-stu-id="f1183-141">Action</span></span>|<span data-ttu-id="f1183-142">例</span><span class="sxs-lookup"><span data-stu-id="f1183-142">Example</span></span>|  
|---------------|------------|-------------|  
|<span data-ttu-id="f1183-143">Read_\<LOBColName\></span><span class="sxs-lookup"><span data-stu-id="f1183-143">Read_\<LOBColName\></span></span>|`Tables/ReadLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]`|`Tables/ReadLOB/SCOTT/CUSTOMER/Photo`|  
|<span data-ttu-id="f1183-144">Read_\<LOBColName\>応答</span><span class="sxs-lookup"><span data-stu-id="f1183-144">Read_\<LOBColName\> Response</span></span>|`Tables/ReadLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]/response`|`Tables/ReadLOB/SCOTT/CUSTOMER/Photo/response`|  
|<span data-ttu-id="f1183-145">Update_\<LOBColName\></span><span class="sxs-lookup"><span data-stu-id="f1183-145">Update_\<LOBColName\></span></span>|<span data-ttu-id="f1183-146">**BLOB の**:</span><span class="sxs-lookup"><span data-stu-id="f1183-146">**For BLOB**:</span></span><br /><br /> `Tables/UpdateBLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]`<br /><br /> <span data-ttu-id="f1183-147">**CLOB や NCLOB を**:</span><span class="sxs-lookup"><span data-stu-id="f1183-147">**For CLOB and NCLOB**:</span></span><br /><br /> `Tables/UpdateCLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]`|<span data-ttu-id="f1183-148">**BLOB の**:</span><span class="sxs-lookup"><span data-stu-id="f1183-148">**For BLOB**:</span></span><br /><br /> `Tables/UpdateBLOB/SCOTT/CUSTOMER/Photo/`<br /><br /> <span data-ttu-id="f1183-149">**CLOB や NCLOB を**:</span><span class="sxs-lookup"><span data-stu-id="f1183-149">**For CLOB and NCLOB**:</span></span><br /><br /> `Tables/UpdateCLOB/SCOTT/CUSTOMER/Photo1/`|  
|<span data-ttu-id="f1183-150">Update_\<LOBColName\>応答</span><span class="sxs-lookup"><span data-stu-id="f1183-150">Update_\<LOBColName\> Response</span></span>|<span data-ttu-id="f1183-151">**BLOB の**:</span><span class="sxs-lookup"><span data-stu-id="f1183-151">**For BLOB**:</span></span><br /><br /> `Tables/UpdateBLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]/response`<br /><br /> <span data-ttu-id="f1183-152">**CLOB や NCLOB を**:</span><span class="sxs-lookup"><span data-stu-id="f1183-152">**For CLOB and NCLOB**:</span></span><br /><br /> `Tables/UpdateCLOB/[SCHEMA]/[TABLE_NAME]/[LOBColName]/response`|<span data-ttu-id="f1183-153">**BLOB の**:</span><span class="sxs-lookup"><span data-stu-id="f1183-153">**For BLOB**:</span></span><br /><br /> `Tables/UpdateBLOB/SCOTT/CUSTOMER/Photo/response`<br /><br /> <span data-ttu-id="f1183-154">**CLOB や NCLOB を**:</span><span class="sxs-lookup"><span data-stu-id="f1183-154">**For CLOB and NCLOB**:</span></span><br /><br /> `Tables/UpdateCLOB/SCOTT/CUSTOMER/Photo1/response`|  
  
 <span data-ttu-id="f1183-155">エンティティの説明</span><span class="sxs-lookup"><span data-stu-id="f1183-155">Entity descriptions:</span></span>  
  
 <span data-ttu-id="f1183-156">[スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。</span><span class="sxs-lookup"><span data-stu-id="f1183-156">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="f1183-157">[TABLE_NAME] を対象となる、LOB の列を含むテーブルを =たとえば、顧客です。</span><span class="sxs-lookup"><span data-stu-id="f1183-157">[TABLE_NAME] = The table that contains the targeted LOB column; for example, CUSTOMER.</span></span> <span data-ttu-id="f1183-158">(SCOTT です。CUSTOMER テーブルではインストール SQL スクリプトのサンプルに含まれています。)</span><span class="sxs-lookup"><span data-stu-id="f1183-158">(The SCOTT.CUSTOMER table is installed by a SQL script included in the samples.)</span></span>  
  
 <span data-ttu-id="f1183-159">[LOBCol_Name]、LOB の列の名前を =たとえば、写真。</span><span class="sxs-lookup"><span data-stu-id="f1183-159">[LOBCol_Name] = The name of a LOB column; for example, Photo.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f1183-160">Read_ のメッセージ アクション\<LOBColName\>と Update_\<LOBColName\>操作ビューに似ていますが、テーブルは、使用されている操作のアクションは、テーブルではなく、ビューを指定します: `Views/ReadLOB/[SCHEMA]/[VIEW_NAME]/[LOBColName]` 。</span><span class="sxs-lookup"><span data-stu-id="f1183-160">The message action for Read_\<LOBColName\> and Update_\<LOBColName\> operations on views is similar to that used for tables, except that action for the operation specifies a view rather than a table: `Views/ReadLOB/[SCHEMA]/[VIEW_NAME]/[LOBColName]`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1183-161">参照</span><span class="sxs-lookup"><span data-stu-id="f1183-161">See Also</span></span>  
 [<span data-ttu-id="f1183-162">BizTalk Adapter for Oracle E-Business Suite 用のメッセージとメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="f1183-162">Messages and Message Schemas for BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)