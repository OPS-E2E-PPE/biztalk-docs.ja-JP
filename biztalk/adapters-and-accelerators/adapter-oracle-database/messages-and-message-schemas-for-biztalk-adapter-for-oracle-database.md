---
title: "メッセージと BizTalk Adapter 用 Oracle Database のメッセージ スキーマを |Microsoft ドキュメント"
description: "BizTalk server、Oracle データベース アダプターで使用されるメッセージとデータの型の XML 構造"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fee0a531-b1e6-4b99-bb79-45368c401395
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bda5ed06470e051dc1f0bdf4595a1539aab6e6bc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-oracle-database"></a><span data-ttu-id="2b1f9-103">メッセージと BizTalk Adapter 用 Oracle Database のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="2b1f9-103">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>

## <a name="overview"></a><span data-ttu-id="2b1f9-104">概要</span><span class="sxs-lookup"><span data-stu-id="2b1f9-104">Overview</span></span>
<span data-ttu-id="2b1f9-105">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-105">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="2b1f9-106">これは、アプリケーションがそれで呼び出すことができ、アプリケーションで呼び出すことができます、さらに、操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-106">It exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="2b1f9-107">これらの操作がチャネル経由で SOAP メッセージを送信することによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-107">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="2b1f9-108">応答が必要な場合、同じチャネル経由で SOAP メッセージで返されます。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-108">If a response is required, it is returned in a SOAP message over the same channel.</span></span>  
  
 <span data-ttu-id="2b1f9-109">として、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]標準を使用してその操作とデータ型のメタデータが公開[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]メカニズムです。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-109">As a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes metadata for its operations and data types by using standard [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] mechanisms.</span></span> <span data-ttu-id="2b1f9-110">このトピックのセクションでは、メッセージの XML 構造の記述し、データの種類を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を使用します。</span><span class="sxs-lookup"><span data-stu-id="2b1f9-110">The sections in this topic describe the XML structure of the messages and data types that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2b1f9-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2b1f9-111">In This Section</span></span>  
  
-   [<span data-ttu-id="2b1f9-112">基本的な Oracle データ型</span><span class="sxs-lookup"><span data-stu-id="2b1f9-112">Basic Oracle Data Types</span></span>](../../adapters-and-accelerators/adapter-oracle-database/basic-oracle-data-types1.md)  
  
-   [<span data-ttu-id="2b1f9-113">基本的な insert、メッセージ スキーマを更新、削除、およびテーブルおよびビューの操作の選択</span><span class="sxs-lookup"><span data-stu-id="2b1f9-113">Message Schemas for the Basic Insert, Update, Delete, and Select Operations on Tables and Views</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)  
  
-   [<span data-ttu-id="2b1f9-114">特殊な LOB 操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="2b1f9-114">Message Schemas for Special LOB Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md)  
  
-   [<span data-ttu-id="2b1f9-115">関数およびプロシージャのメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="2b1f9-115">Message Schemas for Functions and Procedures</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)  
  
-   [<span data-ttu-id="2b1f9-116">REF CURSOR のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="2b1f9-116">Message Schemas for REF CURSORS</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md)  
  
-   [<span data-ttu-id="2b1f9-117">レコードの種類のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="2b1f9-117">Message Schemas for RECORD Types</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-record-types.md)  
  
-   [<span data-ttu-id="2b1f9-118">SQLEXECUTE 操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="2b1f9-118">Message Schemas for the SQLEXECUTE Operation</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md)  
  
-   [<span data-ttu-id="2b1f9-119">ポーリング操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="2b1f9-119">Message Schemas for the Polling Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-polling-operations2.md)  
  
-   [<span data-ttu-id="2b1f9-120">複合操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="2b1f9-120">Message Schemas for the Composite Operation</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md)  
  
-   [<span data-ttu-id="2b1f9-121">通知操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="2b1f9-121">Message Schemas for the Notification Operation</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-notification-operation1.md)  
  
