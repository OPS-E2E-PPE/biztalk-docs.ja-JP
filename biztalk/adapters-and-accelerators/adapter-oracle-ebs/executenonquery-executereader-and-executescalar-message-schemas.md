---
title: ExecuteNonQuery、ExecuteReader、ExecuteScalar Operations1 のメッセージ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8aa5fdb2-1e7f-4a34-a1e5-c16d8fb477d5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7078fed7a007eca4dfb3eb5608eb6e688bb74a45
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011971"
---
# <a name="message-schemas-for-the-executenonquery-executereader-and-executescalar-operations"></a><span data-ttu-id="507f0-102">ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="507f0-102">Message Schemas for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>
<span data-ttu-id="507f0-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] Oracle E-business Suite で、任意の SQL ステートメントまたは PL/SQL ブロックを実行する、ルート レベルで ExecuteNonQuery、ExecuteReader、executescalar 送信操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="507f0-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] exposes the ExecuteNonQuery, ExecuteReader, and ExecuteScalar outbound operations at the root level to execute any arbitrary SQL statements or PL/SQL blocks in Oracle E-Business Suite.</span></span>  
  
 <span data-ttu-id="507f0-104">詳細については。</span><span class="sxs-lookup"><span data-stu-id="507f0-104">For more information about:</span></span>  
  
- <span data-ttu-id="507f0-105">これらの操作を参照してください[ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="507f0-105">These operations, see [Support for ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).</span></span>  
  
- <span data-ttu-id="507f0-106">使用してこれらの操作を実行する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[ExecuteReader、executescalar、ExecuteNonQuery 操作では、BizTalk Server を使用して SQL](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)します。</span><span class="sxs-lookup"><span data-stu-id="507f0-106">Performing these operations using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], see [ExecuteReader, ExecuteScalar, or ExecuteNonQuery Operations in SQL using BizTalk Server](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md).</span></span>  
  
## <a name="message-structure-for-the-executenonquery-executereader-and-executescalar-operations"></a><span data-ttu-id="507f0-107">ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のメッセージの構造</span><span class="sxs-lookup"><span data-stu-id="507f0-107">Message Structure for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>  
 <span data-ttu-id="507f0-108">これらの操作でメッセージが、要求-応答メッセージ交換パターンに従うし、次の表は、これらの要求と応答メッセージの構造を示します。</span><span class="sxs-lookup"><span data-stu-id="507f0-108">The messages in these operations follow a request-response message exchange pattern, and the following table shows the structure of these request and response messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="507f0-109">表の後は、エンティティの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="507f0-109">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="507f0-110">演算</span><span class="sxs-lookup"><span data-stu-id="507f0-110">Operation</span></span>|<span data-ttu-id="507f0-111">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="507f0-111">XML Message</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="507f0-112">ExecuteNonQuery 要求</span><span class="sxs-lookup"><span data-stu-id="507f0-112">ExecuteNonQuery Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteNonQuery xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query>   <OutputRefCursorNames>     <string>[stringvalue1]</string>     <string>[stringvalue2]</string>     …   </OutputRefCursorNames> </ExecuteNonQuery>`|  
|<span data-ttu-id="507f0-113">ExecuteNonQuery 応答</span><span class="sxs-lookup"><span data-stu-id="507f0-113">ExecuteNonQuery Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteNonQueryResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteNonQueryResult>[value]</ExecuteNonQueryResult>   <OutputRefCursors>     <DataSet>       <Any>[value]</Any>       <Any>[value]</Any>       …     </DataSet>   </OutputRefCursors> </ExecuteNonQueryResponse>`|  
|<span data-ttu-id="507f0-114">ExecuteReader 要求</span><span class="sxs-lookup"><span data-stu-id="507f0-114">ExecuteReader Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteReader xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query> </ExecuteReader>`|  
|<span data-ttu-id="507f0-115">ExecuteReader 応答</span><span class="sxs-lookup"><span data-stu-id="507f0-115">ExecuteReader Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteReaderResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteReaderResult>     <Any>[value]</Any>     <Any>[value]</Any>       …   </ExecuteReaderResult> </ExecuteReaderResponse>`|  
|<span data-ttu-id="507f0-116">ExecuteScalar 要求</span><span class="sxs-lookup"><span data-stu-id="507f0-116">ExecuteScalar Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteScalar xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query> </ExecuteScalar>`|  
|<span data-ttu-id="507f0-117">ExecuteScalar 応答</span><span class="sxs-lookup"><span data-stu-id="507f0-117">ExecuteScalar Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteScalarResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteScalarResult>[value]</ExecuteScalarResult> </ExecuteScalarResponse>`|  
  
 <span data-ttu-id="507f0-118">エンティティの説明:</span><span class="sxs-lookup"><span data-stu-id="507f0-118">Entity descriptions:</span></span>  
  
 <span data-ttu-id="507f0-119">[ブロックの PL/SQL] = PL/SQL ブロック全体を実行します。</span><span class="sxs-lookup"><span data-stu-id="507f0-119">[PL/SQL block] = The entire PL/SQL block to be executed.</span></span>  
  
 <span data-ttu-id="507f0-120">[stringvalue1] = 文字列の配列内の値。</span><span class="sxs-lookup"><span data-stu-id="507f0-120">[stringvalue1] = A value in the array of strings.</span></span>  
  
## <a name="message-action-for-the-executenonquery-executereader-and-executescalar-operations"></a><span data-ttu-id="507f0-121">ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のメッセージのアクション</span><span class="sxs-lookup"><span data-stu-id="507f0-121">Message Action for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>  
 <span data-ttu-id="507f0-122">ExecuteNonQuery、ExecuteReader、executescalar 操作によって使用されるメッセージのアクションを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="507f0-122">The following table shows the message actions that are used by the ExecuteNonQuery, ExecuteReader, and ExecuteScalar operations.</span></span>  
  
|<span data-ttu-id="507f0-123">演算</span><span class="sxs-lookup"><span data-stu-id="507f0-123">Operation</span></span>|<span data-ttu-id="507f0-124">操作</span><span class="sxs-lookup"><span data-stu-id="507f0-124">Action</span></span>|  
|---------------|------------|  
|<span data-ttu-id="507f0-125">ExecuteNonQuery 要求</span><span class="sxs-lookup"><span data-stu-id="507f0-125">ExecuteNonQuery Request</span></span>|<span data-ttu-id="507f0-126">GenericOp/ExecuteNonQuery</span><span class="sxs-lookup"><span data-stu-id="507f0-126">GenericOp/ExecuteNonQuery</span></span>|  
|<span data-ttu-id="507f0-127">ExecuteNonQuery 応答</span><span class="sxs-lookup"><span data-stu-id="507f0-127">ExecuteNonQuery Response</span></span>|<span data-ttu-id="507f0-128">GenericOp/ExecuteNonQuery/応答</span><span class="sxs-lookup"><span data-stu-id="507f0-128">GenericOp/ExecuteNonQuery/response</span></span>|  
|<span data-ttu-id="507f0-129">ExecuteReader 要求</span><span class="sxs-lookup"><span data-stu-id="507f0-129">ExecuteReader Request</span></span>|<span data-ttu-id="507f0-130">GenericOp/ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="507f0-130">GenericOp/ExecuteReader</span></span>|  
|<span data-ttu-id="507f0-131">ExecuteReader 応答</span><span class="sxs-lookup"><span data-stu-id="507f0-131">ExecuteReader Response</span></span>|<span data-ttu-id="507f0-132">GenericOp/ExecuteReader/応答</span><span class="sxs-lookup"><span data-stu-id="507f0-132">GenericOp/ExecuteReader/response</span></span>|  
|<span data-ttu-id="507f0-133">ExecuteScalar 要求</span><span class="sxs-lookup"><span data-stu-id="507f0-133">ExecuteScalar Request</span></span>|<span data-ttu-id="507f0-134">GenericOp/ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="507f0-134">GenericOp/ExecuteScalar</span></span>|  
|<span data-ttu-id="507f0-135">ExecuteScalar 応答</span><span class="sxs-lookup"><span data-stu-id="507f0-135">ExecuteScalar Response</span></span>|<span data-ttu-id="507f0-136">GenericOp/ExecuteScalar/応答</span><span class="sxs-lookup"><span data-stu-id="507f0-136">GenericOp/ExecuteScalar/response</span></span>|