---
title: メッセージと BizTalk Adapter for Oracle E-business Suite のメッセージ スキーマ |Microsoft Docs
description: BizTalk server、Oracle EBS アダプターによって使用されるメッセージとデータの型の XML 構造
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4434b4d4-fbe0-4692-81a5-9883c9a77cf6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0d21fa159295e6b8b38b53a98f18bc9b40c21db
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375369"
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite"></a><span data-ttu-id="c1c84-103">メッセージと BizTalk Adapter for Oracle E-business Suite のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="c1c84-103">Messages and Message Schemas for BizTalk Adapter for Oracle E-Business Suite</span></span>

## <a name="overview"></a><span data-ttu-id="c1c84-104">概要</span><span class="sxs-lookup"><span data-stu-id="c1c84-104">Overview</span></span>
<span data-ttu-id="c1c84-105">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。</span><span class="sxs-lookup"><span data-stu-id="c1c84-105">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="c1c84-106">アプリケーションがそれを呼び出すことができ、アプリケーションで呼び出すことができます、さらに、操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="c1c84-106">It exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="c1c84-107">これらの操作は、チャネル経由で SOAP メッセージを送信することによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c1c84-107">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="c1c84-108">応答が必要な場合、同じチャネル経由で SOAP メッセージで返されます。</span><span class="sxs-lookup"><span data-stu-id="c1c84-108">If a response is required, it is returned in a SOAP message over the same channel.</span></span>  
  
 <span data-ttu-id="c1c84-109">として、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]標準を使用して、その操作とデータ型のメタデータを公開する[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]メカニズム。</span><span class="sxs-lookup"><span data-stu-id="c1c84-109">As a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] exposes metadata for its operations and data types by using standard [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] mechanisms.</span></span> <span data-ttu-id="c1c84-110">このトピックのセクションでは、メッセージの XML 構造を記述して、データの種類を[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を使用します。</span><span class="sxs-lookup"><span data-stu-id="c1c84-110">The sections in this topic describe the XML structure of the messages and data types that the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c1c84-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c1c84-111">In This Section</span></span>  
  
-   [<span data-ttu-id="c1c84-112">基本的な Oracle データ型</span><span class="sxs-lookup"><span data-stu-id="c1c84-112">Basic Oracle Data Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/basic-oracle-data-types2.md)  
  
-   [<span data-ttu-id="c1c84-113">挿入、更新、削除、選択操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="c1c84-113">Message Schemas for Insert, Update, Delete, and Select Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)  
  
-   [<span data-ttu-id="c1c84-114">ストアド プロシージャ、関数、PL/SQL API のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="c1c84-114">Message Schemas for Stored Procedures, Functions, and PL/SQL APIs</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-stored-procedures-functions-and-pl-sql-apis.md)  
  
-   [<span data-ttu-id="c1c84-115">同時実行プログラムのメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="c1c84-115">Message Schemas for Concurrent Programs</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-concurrent-programs.md)  
  
-   [<span data-ttu-id="c1c84-116">要求セットのメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="c1c84-116">Message Schemas for Request Sets</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-request-sets.md)  
  
-   [<span data-ttu-id="c1c84-117">特殊な LOB 操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="c1c84-117">Message Schemas for Special LOB Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-special-lob-operations1.md)  
  
-   [<span data-ttu-id="c1c84-118">ポーリング操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="c1c84-118">Message Schemas for the Polling Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-polling-operations1.md)  
  
-   [<span data-ttu-id="c1c84-119">通知操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="c1c84-119">Message Schemas for the Notification Operation</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-notification-operation2.md)  
  
-   [<span data-ttu-id="c1c84-120">ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="c1c84-120">Message Schemas for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/executenonquery-executereader-and-executescalar-message-schemas.md)  
  
-   [<span data-ttu-id="c1c84-121">複合操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="c1c84-121">Message Schemas for the Composite Operation</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-composite-operation1.md)  
  