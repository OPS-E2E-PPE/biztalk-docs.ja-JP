---
title: "複合 Operation1 のメッセージ スキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 768473ef-da8d-4e58-86cb-597c28ded49c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b22861d36693ab3ef487e5e3d0b86544f048e95
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-the-composite-operation"></a><span data-ttu-id="5aeac-102">複合操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="5aeac-102">Message Schemas for the Composite Operation</span></span>
<span data-ttu-id="5aeac-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] Oracle E-business Suite で複合操作を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="5aeac-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] enables you to execute composite operations in Oracle E-Business Suite.</span></span> <span data-ttu-id="5aeac-104">複合操作は、複数の操作を含めることができ、任意の順序で。</span><span class="sxs-lookup"><span data-stu-id="5aeac-104">A composite operation can contain multiple operations, and in any order.</span></span> <span data-ttu-id="5aeac-105">どの操作に指定する複合操作については、次を参照してください。[複合操作に対するサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md)です。</span><span class="sxs-lookup"><span data-stu-id="5aeac-105">For information about which operations can be included in a composite operation, see [Support for Composite Operations](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md).</span></span>  
  
 <span data-ttu-id="5aeac-106">使用して複合操作を実行する方法については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[BizTalk Server を使用して Oracle データベースでの複合操作を実行](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="5aeac-106">For information about how to perform composite operations using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], see [Run Composite Operations on Oracle Database using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md).</span></span>  
  
## <a name="message-structure-for-the-composite-operation"></a><span data-ttu-id="5aeac-107">複合操作のメッセージの構造</span><span class="sxs-lookup"><span data-stu-id="5aeac-107">Message Structure for the Composite Operation</span></span>  
 <span data-ttu-id="5aeac-108">複合操作には、複数個々 の操作が含まれているので複合操作のメッセージの構造には、個々 の操作のメッセージの構造体が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5aeac-108">Since a composite operation contains multiple individual operations; the message structure of a composite operation contains message structures of the individual operations.</span></span> <span data-ttu-id="5aeac-109">複合操作メッセージには、要求-応答メッセージ交換パターンが続きます。</span><span class="sxs-lookup"><span data-stu-id="5aeac-109">The composite operation message follows a request-response message exchange pattern.</span></span>  
  
 <span data-ttu-id="5aeac-110">受け取らないをパッケージ化されたストアド プロシージャの入力パラメーター、および削除操作、次の表は、挿入操作を含む複合操作の要求と応答メッセージの構造を示します。</span><span class="sxs-lookup"><span data-stu-id="5aeac-110">The following table shows the structure of the request and response messages of a composite operation that contains an Insert operation, a packaged stored procedure that does not take any input parameters, and a Delete operation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5aeac-111">表の後に、エンティティの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5aeac-111">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="5aeac-112">操作</span><span class="sxs-lookup"><span data-stu-id="5aeac-112">Operation</span></span>|<span data-ttu-id="5aeac-113">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="5aeac-113">XML Message</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5aeac-114">複合操作要求</span><span class="sxs-lookup"><span data-stu-id="5aeac-114">Composite Operation Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <Request xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/[SCHEMA]/[TABLE_NAME]">     <Recordset>       <InsertRecord>         <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>           <InLineValue>[value]</InlineValue>         <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>           <InLineValue>[value]</InlineValue>         …       <InsertRecord>    </RECORDSET>   </Insert>   <[SP_NAME] xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/[SCHEMA]/[APP_NAME]" />   <Delete xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/[SCHEMA]/[TABLE_NAME]">     <FILTER>[WHERE_clause]</FILTER>   </Delete> </Request>`|  
|<span data-ttu-id="5aeac-115">複合操作の応答</span><span class="sxs-lookup"><span data-stu-id="5aeac-115">Composite Operation Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?>  <RequestResponse xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <InsertResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/[SCHEMA]/[TABLE_NAME]">     <InsertResult>[value]</InsertResult>    </InsertResponse>   <[SP_NAME]Response xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Procedures/[SCHEMA]">     <[PRM1_NAME]>value1<[PRM1_NAME]>     <[PRM2_NAME]>value2</[PRM2_NAME]>     …   </[SP_NAME]Response>    <DeleteResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <DeleteResult>[value]</DeleteResult>    </DeleteResponse> </RequestResponse>`|  
  
 <span data-ttu-id="5aeac-116">エンティティの説明</span><span class="sxs-lookup"><span data-stu-id="5aeac-116">Entity descriptions:</span></span>  
  
 <span data-ttu-id="5aeac-117">[PROJECT_NAME] = 複合操作のスキーマを含む BizTalk プロジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="5aeac-117">[PROJECT_NAME] = Name of the BizTalk project that contains the composite operation schema.</span></span>  
  
 <span data-ttu-id="5aeac-118">[COMPOSITE_SCHEMA_NAME]、ユーザーによって指定された複合操作のスキーマの名前を = です。</span><span class="sxs-lookup"><span data-stu-id="5aeac-118">[COMPOSITE_SCHEMA_NAME] = Name of the composite operation schema given by the user.</span></span>  
  
 <span data-ttu-id="5aeac-119">[スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。</span><span class="sxs-lookup"><span data-stu-id="5aeac-119">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="5aeac-120">[TABLE_NAME] テーブルの名前を =たとえば、従業員です。</span><span class="sxs-lookup"><span data-stu-id="5aeac-120">[TABLE_NAME] = Name of the table; for example, EMPLOYEE.</span></span>  
  
 <span data-ttu-id="5aeac-121">[FIELD1_NAME] = テーブルのフィールド名です。たとえば、名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="5aeac-121">[FIELD1_NAME] = Table field name; for example, NAME.</span></span>  
  
 <span data-ttu-id="5aeac-122">[SP_NAME] を実行するパッケージ化されたストアド プロシージャを =たとえば、ADD_EMP_DETAILS です。</span><span class="sxs-lookup"><span data-stu-id="5aeac-122">[SP_NAME] = The packaged stored procedure to be executed; for example, ADD_EMP_DETAILS.</span></span>  
  
 <span data-ttu-id="5aeac-123">[APP_NAME] パッケージ化されたストアド プロシージャを含む Oracle アプリケーションの名前を = です。</span><span class="sxs-lookup"><span data-stu-id="5aeac-123">[APP_NAME] = Name of the Oracle Application that contains the packaged stored procedure.</span></span>  
  
 <span data-ttu-id="5aeac-124">[PRM1_NAME] パッケージ化されたストアド プロシージャでの Oracle パラメーターの名前を = です。</span><span class="sxs-lookup"><span data-stu-id="5aeac-124">[PRM1_NAME] = The name of the Oracle parameter in the packaged stored procedure.</span></span>  
  
## <a name="message-action-for-the-composite-operation"></a><span data-ttu-id="5aeac-125">複合操作のメッセージ アクション</span><span class="sxs-lookup"><span data-stu-id="5aeac-125">Message Action for the Composite Operation</span></span>  
 <span data-ttu-id="5aeac-126">複合操作のメッセージ アクションが"CompositeOperation"</span><span class="sxs-lookup"><span data-stu-id="5aeac-126">The message action for the composite operation is “CompositeOperation.”</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aeac-127">参照</span><span class="sxs-lookup"><span data-stu-id="5aeac-127">See Also</span></span>  
 [<span data-ttu-id="5aeac-128">メッセージと BizTalk Adapter for Oracle E-business Suite のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="5aeac-128">Messages and Message Schemas for BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)