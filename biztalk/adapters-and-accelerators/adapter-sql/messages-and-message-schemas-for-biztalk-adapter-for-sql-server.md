---
title: メッセージと BizTalk adapter for SQL Server のメッセージ スキーマ |Microsoft Docs
description: BizTalk Server の SQL Server のアダプターで使用されるメッセージとデータの型の XML 構造
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e95c6342-5420-4fb8-9b41-7c87d27b5b68
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b01d2181423e479a7c39dc680cde34eba2db79fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368524"
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-sql-server"></a><span data-ttu-id="f0a8e-103">メッセージと BizTalk adapter for SQL Server のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="f0a8e-103">Messages and Message Schemas for BizTalk Adapter for SQL Server</span></span>

## <a name="overview"></a><span data-ttu-id="f0a8e-104">概要</span><span class="sxs-lookup"><span data-stu-id="f0a8e-104">Overview</span></span>
<span data-ttu-id="f0a8e-105">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。</span><span class="sxs-lookup"><span data-stu-id="f0a8e-105">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="f0a8e-106">アプリケーションがそれを呼び出すことができ、アプリケーションで呼び出すことができます、さらに、操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="f0a8e-106">It exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="f0a8e-107">これらの操作は、チャネル経由で SOAP メッセージを送信することによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f0a8e-107">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="f0a8e-108">応答が必要な場合、同じチャネル経由で SOAP メッセージで返されます。</span><span class="sxs-lookup"><span data-stu-id="f0a8e-108">If a response is required, it is returned in a SOAP message over the same channel.</span></span>  
  
 <span data-ttu-id="f0a8e-109">として、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]標準を使用して、その操作とデータ型のメタデータを公開する[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]メカニズム。</span><span class="sxs-lookup"><span data-stu-id="f0a8e-109">As a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] exposes metadata for its operations and data types by using standard [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] mechanisms.</span></span> <span data-ttu-id="f0a8e-110">このトピックのセクションでは、メッセージの XML 構造を記述して、データの種類を[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0a8e-110">The sections in this topic describe the XML structure of the messages and data types that the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f0a8e-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f0a8e-111">In This Section</span></span>  
  
-   [<span data-ttu-id="f0a8e-112">SQL Server の基本的なデータ型</span><span class="sxs-lookup"><span data-stu-id="f0a8e-112">Basic SQL Server Data Types</span></span>](../../adapters-and-accelerators/adapter-sql/basic-sql-server-data-types.md)  
  
-   [<span data-ttu-id="f0a8e-113">テーブルとビューに対する挿入、更新、削除、選択の各操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="f0a8e-113">Message Schemas for Insert, Update, Delete, and Select Operations on Tables and Views</span></span>](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)  
  
-   [<span data-ttu-id="f0a8e-114">プロシージャと関数のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="f0a8e-114">Message Schemas for Procedures and Functions</span></span>](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)  
  
-   [<span data-ttu-id="f0a8e-115">Polling 操作と TypedPolling 操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="f0a8e-115">Message Schemas for the Polling and TypedPolling Operations</span></span>](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md)  
  
-   [<span data-ttu-id="f0a8e-116">クエリ通知のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="f0a8e-116">Message Schemas for Query Notification</span></span>](../../adapters-and-accelerators/adapter-sql/message-schemas-for-query-notification.md)  
  
-   [<span data-ttu-id="f0a8e-117">複合操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="f0a8e-117">Message Schemas for Composite Operations</span></span>](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)  
  
-   [<span data-ttu-id="f0a8e-118">ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="f0a8e-118">Message Schemas for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>](../../adapters-and-accelerators/adapter-sql/executenonquery-executereader-and-executescalar-message-schemas-in-sql.md)  
  
