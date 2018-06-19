---
title: 複合操作のメッセージ スキーマ |Microsoft ドキュメント
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
ms.openlocfilehash: b89c354baea2ddb46abf549752dc09699b9c9695
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222514"
---
# <a name="message-schemas-for-composite-operations"></a><span data-ttu-id="19c85-102">複合操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="19c85-102">Message Schemas for Composite Operations</span></span>
<span data-ttu-id="19c85-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] SQL Server データベースでの複合操作を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="19c85-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] enables you to execute composite operations on the SQL Server database.</span></span> <span data-ttu-id="19c85-104">複合操作では、Insert、Update を含む複数の操作を含むでき、テーブルとビューを操作およびストアド プロシージャでの操作を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="19c85-104">A composite operation can contain multiple operations including the Insert, Update, and Delete operations on the tables and views, and operations on stored procedures.</span></span> <span data-ttu-id="19c85-105">複合操作は、任意の順序でこれらの操作を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="19c85-105">A composite operation can include these operations in any order.</span></span>  
  
 <span data-ttu-id="19c85-106">詳細については。</span><span class="sxs-lookup"><span data-stu-id="19c85-106">For more information about:</span></span>  
  
-   <span data-ttu-id="19c85-107">複合操作を参照してください[複合操作に対するサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md)です。</span><span class="sxs-lookup"><span data-stu-id="19c85-107">Composite operations, see [Support for Composite Operations](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md).</span></span>  
  
-   <span data-ttu-id="19c85-108">使用して複合操作を実行する方法、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[SQL アダプタを使用して SQL Server で複合操作を実行](../../adapters-and-accelerators/adapter-sql/run-composite-operations-in-sql-server-using-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="19c85-108">How to perform composite operations using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Run composite operations in SQL Server  using the SQL adapter](../../adapters-and-accelerators/adapter-sql/run-composite-operations-in-sql-server-using-the-sql-adapter.md).</span></span>  
  
## <a name="message-structure-for-the-composite-operation"></a><span data-ttu-id="19c85-109">複合操作のメッセージの構造</span><span class="sxs-lookup"><span data-stu-id="19c85-109">Message Structure for the Composite Operation</span></span>  
 <span data-ttu-id="19c85-110">複合操作には、複数個々 の操作が含まれているので複合操作のメッセージの構造には、個々 の操作のメッセージの構造体が含まれています。</span><span class="sxs-lookup"><span data-stu-id="19c85-110">Since a composite operation contains multiple individual operations; the message structure of a composite operation contains message structures of the individual operations.</span></span> <span data-ttu-id="19c85-111">複合操作には、テーブル、ビュー、およびストアド プロシージャでの操作が含まれている、合成の操作メッセージは、要求-応答メッセージ交換パターンに従います。</span><span class="sxs-lookup"><span data-stu-id="19c85-111">As a composite operation contains operations on tables, views, and stored procedures, the composite operation message follows a request-response message exchange pattern.</span></span>  
  
 <span data-ttu-id="19c85-112">次の表は、挿入操作を含む複合操作の要求および応答メッセージの構造を示しています。 は、ストアド プロシージャを受け取らない入力パラメーター、および削除操作。</span><span class="sxs-lookup"><span data-stu-id="19c85-112">The following table shows the structure of the request and response messages of a composite operation that contains an Insert operation, a stored procedure that does not take any input parameters, and a Delete operation.</span></span>  
  
|<span data-ttu-id="19c85-113">操作</span><span class="sxs-lookup"><span data-stu-id="19c85-113">Operation</span></span>|<span data-ttu-id="19c85-114">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="19c85-114">XML Message</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="19c85-115">複合操作要求</span><span class="sxs-lookup"><span data-stu-id="19c85-115">Composite Operation Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <Request xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <Rows>       <[TABLE_NAME]>         <[FIELD1_NAME]>[Value1]</[FIELD1_NAME]>         <[FIELD2_NAME]>[Value1]</[FIELD2_NAME]>         …       </[TABLE_NAME]>     </Rows>   </Insert>   <[SP_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]" />   <Delete xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <Rows>       <[TABLE_NAME]>         <[FIELD1_NAME]>[Value1]</[FIELD1_NAME]>       </[TABLE_NAME]>     </Rows>   </Delete> </Request>`|  
|<span data-ttu-id="19c85-116">複合操作の応答</span><span class="sxs-lookup"><span data-stu-id="19c85-116">Composite Operation Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?>  <RequestResponse xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <InsertResult>       <long>[value]</long>      </InsertResult>   </InsertResponse>   <[SP_NAME]Response xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]">     <[SP_NAME]Result>       <DataSet>         <any>[Value]</any>          <any>[Value]</any>          …       </DataSet>     </[SP_NAME]Result>     <ReturnValue>[value]</ReturnValue>    </[SP_NAME]Response>   <DeleteResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <DeleteResult>[value]</DeleteResult>    </DeleteResponse> </RequestResponse>`|  
  
 <span data-ttu-id="19c85-117">[PROJECT_NAME] = 複合操作のスキーマを含む BizTalk プロジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="19c85-117">[PROJECT_NAME] = Name of the BizTalk project that contains the composite operation schema.</span></span>  
  
 <span data-ttu-id="19c85-118">[COMPOSITE_SCHEMA_NAME]、ユーザーによって指定された複合操作のスキーマの名前を = です。</span><span class="sxs-lookup"><span data-stu-id="19c85-118">[COMPOSITE_SCHEMA_NAME] = Name of the composite operation schema given by the user.</span></span>  
  
 <span data-ttu-id="19c85-119">[スキーマ]; SQL Server のコレクション アイテムを =たとえば、dbo します。</span><span class="sxs-lookup"><span data-stu-id="19c85-119">[SCHEMA] = Collection of SQL Server artifacts; for example, dbo.</span></span>  
  
 <span data-ttu-id="19c85-120">[TABLE_NAME] テーブルの名前を =たとえば、従業員です。</span><span class="sxs-lookup"><span data-stu-id="19c85-120">[TABLE_NAME] = Name of the table; for example, Employee.</span></span>  
  
 <span data-ttu-id="19c85-121">[FIELD1_NAME] = テーブルのフィールド名です。たとえば、名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="19c85-121">[FIELD1_NAME] = Table field name; for example, NAME.</span></span>  
  
 <span data-ttu-id="19c85-122">[SP_NAME] を実行するストアド プロシージャを =たとえば、ADD_EMP_DETAILS です。</span><span class="sxs-lookup"><span data-stu-id="19c85-122">[SP_NAME] = The stored procedure to be executed; for example, ADD_EMP_DETAILS.</span></span>  
  
## <a name="message-action-for-the-composite-operation"></a><span data-ttu-id="19c85-123">複合操作のメッセージ アクション</span><span class="sxs-lookup"><span data-stu-id="19c85-123">Message Action for the Composite Operation</span></span>  
 <span data-ttu-id="19c85-124">複合操作のメッセージ アクションが"CompositeOperation"</span><span class="sxs-lookup"><span data-stu-id="19c85-124">The message action for the composite operation is “CompositeOperation.”</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19c85-125">参照</span><span class="sxs-lookup"><span data-stu-id="19c85-125">See Also</span></span>  
 [<span data-ttu-id="19c85-126">メッセージと BizTalk Adapter for SQL Server のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="19c85-126">Messages and Message Schemas for BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)