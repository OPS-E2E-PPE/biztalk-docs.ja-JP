---
title: 複合操作のメッセージ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d80c023b-1912-43d4-be29-eb9e1b323593
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 716e87dd2973572d473f6637e12c5a80ac6cf847
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015294"
---
# <a name="message-schemas-for-composite-operations"></a><span data-ttu-id="9fe28-102">複合操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="9fe28-102">Message Schemas for Composite Operations</span></span>
<span data-ttu-id="9fe28-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] SQL Server データベースでの複合操作を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="9fe28-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] enables you to execute composite operations on the SQL Server database.</span></span> <span data-ttu-id="9fe28-104">複合操作では、Insert、Update を含む複数の操作を含めることができ、テーブルとビューを操作およびストアド プロシージャに対する操作を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="9fe28-104">A composite operation can contain multiple operations including the Insert, Update, and Delete operations on the tables and views, and operations on stored procedures.</span></span> <span data-ttu-id="9fe28-105">複合操作では、任意の順序でこれらの操作を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9fe28-105">A composite operation can include these operations in any order.</span></span>  
  
 <span data-ttu-id="9fe28-106">詳細については。</span><span class="sxs-lookup"><span data-stu-id="9fe28-106">For more information about:</span></span>  
  
- <span data-ttu-id="9fe28-107">複合操作を参照してください[複合操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md)します。</span><span class="sxs-lookup"><span data-stu-id="9fe28-107">Composite operations, see [Support for Composite Operations](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md).</span></span>  
  
- <span data-ttu-id="9fe28-108">使用して複合操作を実行する方法、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[複合操作の実行、SQL アダプターを使用して SQL Server で](../../adapters-and-accelerators/adapter-sql/run-composite-operations-in-sql-server-using-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="9fe28-108">How to perform composite operations using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Run composite operations in SQL Server  using the SQL adapter](../../adapters-and-accelerators/adapter-sql/run-composite-operations-in-sql-server-using-the-sql-adapter.md).</span></span>  
  
## <a name="message-structure-for-the-composite-operation"></a><span data-ttu-id="9fe28-109">複合操作のメッセージの構造</span><span class="sxs-lookup"><span data-stu-id="9fe28-109">Message Structure for the Composite Operation</span></span>  
 <span data-ttu-id="9fe28-110">複合操作には、複数個々 の操作が含まれているので複合操作のメッセージ構造には、個々 の操作のメッセージの構造が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9fe28-110">Since a composite operation contains multiple individual operations; the message structure of a composite operation contains message structures of the individual operations.</span></span> <span data-ttu-id="9fe28-111">複合操作には、テーブル、ビュー、およびストアド プロシージャに対する操作が含まれている、複合操作のメッセージは、要求-応答のメッセージ交換パターンに従います。</span><span class="sxs-lookup"><span data-stu-id="9fe28-111">As a composite operation contains operations on tables, views, and stored procedures, the composite operation message follows a request-response message exchange pattern.</span></span>  
  
 <span data-ttu-id="9fe28-112">次の表は、挿入操作を含む複合操作の要求と応答メッセージの構造、ストアド プロシージャを受け取らないいずれかの入力パラメーター、および削除操作です。</span><span class="sxs-lookup"><span data-stu-id="9fe28-112">The following table shows the structure of the request and response messages of a composite operation that contains an Insert operation, a stored procedure that does not take any input parameters, and a Delete operation.</span></span>  
  
|<span data-ttu-id="9fe28-113">演算</span><span class="sxs-lookup"><span data-stu-id="9fe28-113">Operation</span></span>|<span data-ttu-id="9fe28-114">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="9fe28-114">XML Message</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9fe28-115">複合操作の要求</span><span class="sxs-lookup"><span data-stu-id="9fe28-115">Composite Operation Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <Request xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <Rows>       <[TABLE_NAME]>         <[FIELD1_NAME]>[Value1]</[FIELD1_NAME]>         <[FIELD2_NAME]>[Value1]</[FIELD2_NAME]>         …       </[TABLE_NAME]>     </Rows>   </Insert>   <[SP_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]" />   <Delete xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <Rows>       <[TABLE_NAME]>         <[FIELD1_NAME]>[Value1]</[FIELD1_NAME]>       </[TABLE_NAME]>     </Rows>   </Delete> </Request>`|  
|<span data-ttu-id="9fe28-116">複合操作の応答</span><span class="sxs-lookup"><span data-stu-id="9fe28-116">Composite Operation Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?>  <RequestResponse xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <InsertResult>       <long>[value]</long>      </InsertResult>   </InsertResponse>   <[SP_NAME]Response xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]">     <[SP_NAME]Result>       <DataSet>         <any>[Value]</any>          <any>[Value]</any>          …       </DataSet>     </[SP_NAME]Result>     <ReturnValue>[value]</ReturnValue>    </[SP_NAME]Response>   <DeleteResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <DeleteResult>[value]</DeleteResult>    </DeleteResponse> </RequestResponse>`|  
  
 <span data-ttu-id="9fe28-117">[PROJECT_NAME] = 複合操作のスキーマを含む BizTalk プロジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="9fe28-117">[PROJECT_NAME] = Name of the BizTalk project that contains the composite operation schema.</span></span>  
  
 <span data-ttu-id="9fe28-118">[COMPOSITE_SCHEMA_NAME] = ユーザーによって指定された複合操作のスキーマの名前。</span><span class="sxs-lookup"><span data-stu-id="9fe28-118">[COMPOSITE_SCHEMA_NAME] = Name of the composite operation schema given by the user.</span></span>  
  
 <span data-ttu-id="9fe28-119">[スキーマ] コレクションの SQL Server のアイテム、=たとえば、dbo です。</span><span class="sxs-lookup"><span data-stu-id="9fe28-119">[SCHEMA] = Collection of SQL Server artifacts; for example, dbo.</span></span>  
  
 <span data-ttu-id="9fe28-120">[TABLE_NAME]; テーブルの名前を =たとえば、従業員です。</span><span class="sxs-lookup"><span data-stu-id="9fe28-120">[TABLE_NAME] = Name of the table; for example, Employee.</span></span>  
  
 <span data-ttu-id="9fe28-121">[FIELD1_NAME] テーブルのフィールド名を =たとえば、名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="9fe28-121">[FIELD1_NAME] = Table field name; for example, NAME.</span></span>  
  
 <span data-ttu-id="9fe28-122">[SP_NAME] を実行するストアド プロシージャを =たとえば、ADD_EMP_DETAILS です。</span><span class="sxs-lookup"><span data-stu-id="9fe28-122">[SP_NAME] = The stored procedure to be executed; for example, ADD_EMP_DETAILS.</span></span>  
  
## <a name="message-action-for-the-composite-operation"></a><span data-ttu-id="9fe28-123">複合操作のメッセージ アクション</span><span class="sxs-lookup"><span data-stu-id="9fe28-123">Message Action for the Composite Operation</span></span>  
 <span data-ttu-id="9fe28-124">複合操作のメッセージ アクションが"CompositeOperation"</span><span class="sxs-lookup"><span data-stu-id="9fe28-124">The message action for the composite operation is “CompositeOperation.”</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fe28-125">参照</span><span class="sxs-lookup"><span data-stu-id="9fe28-125">See Also</span></span>  
 [<span data-ttu-id="9fe28-126">メッセージと BizTalk adapter for SQL Server のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="9fe28-126">Messages and Message Schemas for BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)