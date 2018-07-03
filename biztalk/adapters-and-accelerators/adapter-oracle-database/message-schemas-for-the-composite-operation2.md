---
title: 複合 Operation2 のメッセージ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0164ea07-a373-430b-b569-3e29df1d081b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04ff8ec57d3c94e2191b1615593f0047e01b0e01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967995"
---
# <a name="message-schemas-for-the-composite-operation"></a><span data-ttu-id="405ca-102">複合操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="405ca-102">Message Schemas for the Composite Operation</span></span>
<span data-ttu-id="405ca-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle データベースでの複合操作を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="405ca-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] enables you to execute composite operations on the Oracle database.</span></span> <span data-ttu-id="405ca-104">複合操作は、複数の操作を含めることができ、任意の順序で。</span><span class="sxs-lookup"><span data-stu-id="405ca-104">A composite operation can contain multiple operations, and in any order.</span></span> <span data-ttu-id="405ca-105">複合操作に含まれる操作については、次を参照してください。 [Oracle データベースでの複合操作を実行](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="405ca-105">For information about which operations can be included in a composite operation, see [Run Composite Operations in Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md).</span></span>  
  
 <span data-ttu-id="405ca-106">使用して複合操作を実行する方法については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[BizTalk Server を使用して Oracle データベースでの複合操作を実行](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="405ca-106">For information about how to perform composite operations using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Run Composite Operations on Oracle Database using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md).</span></span>  
  
## <a name="message-structure-for-the-composite-operation"></a><span data-ttu-id="405ca-107">複合操作のメッセージの構造</span><span class="sxs-lookup"><span data-stu-id="405ca-107">Message Structure for the Composite Operation</span></span>  
 <span data-ttu-id="405ca-108">複合操作には複数個々 の操作が含まれています複合操作のメッセージ構造には、個々 の操作のメッセージの構造が含まれています。</span><span class="sxs-lookup"><span data-stu-id="405ca-108">Because a composite operation contains multiple individual operations; the message structure of a composite operation contains message structures of the individual operations.</span></span> <span data-ttu-id="405ca-109">複合操作のメッセージでは、要求-応答のメッセージ交換パターンに従います。</span><span class="sxs-lookup"><span data-stu-id="405ca-109">The composite operation message follows a request-response message exchange pattern.</span></span>  
  
 <span data-ttu-id="405ca-110">受け取らないいずれかのパッケージ化されたストアド プロシージャの入力パラメーター、および削除操作、次の表は、挿入操作を含む複合操作の要求と応答メッセージの構造を示します。</span><span class="sxs-lookup"><span data-stu-id="405ca-110">The following table shows the structure of the request and response messages of a composite operation that contains an Insert operation, a packaged stored procedure that does not take any input parameters, and a Delete operation.</span></span>  
  
|<span data-ttu-id="405ca-111">演算</span><span class="sxs-lookup"><span data-stu-id="405ca-111">Operation</span></span>|<span data-ttu-id="405ca-112">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="405ca-112">XML Message</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="405ca-113">複合操作の要求</span><span class="sxs-lookup"><span data-stu-id="405ca-113">Composite Operation Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <Request xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <Insert xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <RECORDSET>       <[TABLE_NAME]RECORDINSERT>         <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>         <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>         …       </[TABLE_NAME]RECORDINSERT>    </RECORDSET>   </Insert>   <[SP_NAME] xmlns="[VERSION]/[SCHEMA]/Procedure" />   <Delete xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <FILTER>[WHERE_clause]</FILTER>   </Delete> </Request>`|  
|<span data-ttu-id="405ca-114">複合操作の応答</span><span class="sxs-lookup"><span data-stu-id="405ca-114">Composite Operation Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?>  <RequestResponse xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <InsertResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <InsertResult>[value]</InsertResult>    </InsertResponse>   <[SP_NAME]Response xmlns="[VERSION]/[SCHEMA]/Procedure">     <[PRM1_NAME]>value1<[PRM1_NAME]>     <[PRM2_NAME]>value2</[PRM2_NAME]>     …   </[SP_NAME]Response>    <DeleteResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <DeleteResult>[value]</DeleteResult>    </DeleteResponse> </RequestResponse>`|  
  
 <span data-ttu-id="405ca-115">[バージョン] = メッセージ バージョン文字列。例えば http://Microsoft.LobServices.OracleDB/2007/03</span><span class="sxs-lookup"><span data-stu-id="405ca-115">[VERSION] = The message version string; for example, http://Microsoft.LobServices.OracleDB/2007/03</span></span>  
  
 <span data-ttu-id="405ca-116">[PROJECT_NAME] = 複合操作のスキーマを含む BizTalk プロジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="405ca-116">[PROJECT_NAME] = Name of the BizTalk project that contains the composite operation schema.</span></span>  
  
 <span data-ttu-id="405ca-117">[COMPOSITE_SCHEMA_NAME] = ユーザーによって指定された複合操作のスキーマの名前。</span><span class="sxs-lookup"><span data-stu-id="405ca-117">[COMPOSITE_SCHEMA_NAME] = Name of the composite operation schema given by the user.</span></span>  
  
 <span data-ttu-id="405ca-118">[スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。</span><span class="sxs-lookup"><span data-stu-id="405ca-118">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="405ca-119">[TABLE_NAME]; テーブルの名前を =たとえば、従業員です。</span><span class="sxs-lookup"><span data-stu-id="405ca-119">[TABLE_NAME] = Name of the table; for example, EMPLOYEE.</span></span>  
  
 <span data-ttu-id="405ca-120">[FIELD1_NAME] テーブルのフィールド名を =たとえば、名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="405ca-120">[FIELD1_NAME] = Table field name; for example, NAME.</span></span>  
  
 <span data-ttu-id="405ca-121">[SP_NAME] を実行するパッケージ化されたストアド プロシージャを =たとえば、ADD_EMP_DETAILS です。</span><span class="sxs-lookup"><span data-stu-id="405ca-121">[SP_NAME] = The packaged stored procedure to be executed; for example, ADD_EMP_DETAILS.</span></span>  
  
 <span data-ttu-id="405ca-122">[PRM1_NAME] = ストアド プロシージャでの Oracle パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="405ca-122">[PRM1_NAME] = The name of the Oracle parameter in the stored procedure.</span></span>  
  
## <a name="message-action-for-the-composite-operation"></a><span data-ttu-id="405ca-123">複合操作のメッセージ アクション</span><span class="sxs-lookup"><span data-stu-id="405ca-123">Message Action for the Composite Operation</span></span>  
 <span data-ttu-id="405ca-124">複合操作のメッセージのアクションは、"<http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation.”></span><span class="sxs-lookup"><span data-stu-id="405ca-124">The message action for the composite operation is “<http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation.”></span></span>  
  
## <a name="see-also"></a><span data-ttu-id="405ca-125">参照</span><span class="sxs-lookup"><span data-stu-id="405ca-125">See Also</span></span>  
 [<span data-ttu-id="405ca-126">BizTalk Adapter for Oracle Database 用のメッセージとメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="405ca-126">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)