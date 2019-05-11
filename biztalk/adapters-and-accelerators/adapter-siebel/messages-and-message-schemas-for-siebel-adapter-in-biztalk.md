---
title: メッセージと BizTalk adapter for Siebel eBusiness Applications のメッセージ スキーマ |Microsoft Docs
description: Siebel アダプターの BizTalk アダプター パック (BAP) によって使用されるメッセージとデータ型の XML 構造
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b4da884-89b0-4ab1-a728-c5569088a993
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05a96682063437bb59c04372a7e8540743b27113
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371291"
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-siebel-ebusiness-applications"></a><span data-ttu-id="cc866-103">メッセージと BizTalk adapter for Siebel eBusiness Applications のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="cc866-103">Messages and Message Schemas for BizTalk Adapter for Siebel eBusiness Applications</span></span>

## <a name="overview"></a><span data-ttu-id="cc866-104">概要</span><span class="sxs-lookup"><span data-stu-id="cc866-104">Overview</span></span>
<span data-ttu-id="cc866-105">[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。</span><span class="sxs-lookup"><span data-stu-id="cc866-105">The [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="cc866-106">Siebel システムでアプリケーションを呼び出すことができる操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="cc866-106">It exposes operations that applications can invoke on a Siebel system.</span></span> <span data-ttu-id="cc866-107">これらの操作は、チャネル経由で SOAP メッセージを送信することによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cc866-107">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="cc866-108">応答が必要な場合、同じチャネル経由で SOAP メッセージで返されます。</span><span class="sxs-lookup"><span data-stu-id="cc866-108">If a response is required, it is returned in a SOAP message over the same channel.</span></span>  
  
 <span data-ttu-id="cc866-109">として、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]標準を使用して、その操作とデータ型のメタデータを公開する[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]メカニズム。</span><span class="sxs-lookup"><span data-stu-id="cc866-109">As a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] exposes metadata for its operations and data types by using standard [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] mechanisms.</span></span> <span data-ttu-id="cc866-110">このトピックのセクションでは、メッセージの XML 構造を記述して、データの種類を[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を使用します。</span><span class="sxs-lookup"><span data-stu-id="cc866-110">The sections in this topic describe the XML structure of the messages and data types that the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cc866-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="cc866-111">In This Section</span></span>  
  
-   [<span data-ttu-id="cc866-112">基本的な Siebel データ型</span><span class="sxs-lookup"><span data-stu-id="cc866-112">Basic Siebel Data Types</span></span>](basic-siebel-data-types.md)  
  
-   [<span data-ttu-id="cc866-113">ビジネス コンポーネント操作用のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="cc866-113">Message Schemas for Business Component Operations</span></span>](message-schemas-for-business-component-operations.md)  
  
-   [<span data-ttu-id="cc866-114">ビジネス サービス操作用のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="cc866-114">Message Schemas for Business Service Operations</span></span>](message-schemas-for-business-service-operations.md)  
  
-   [<span data-ttu-id="cc866-115">候補リスト操作用のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="cc866-115">Message Schema for Picklist Operations</span></span>](message-schema-for-picklist-operations.md)  
  
-   [<span data-ttu-id="cc866-116">メッセージ バージョン管理のサポート</span><span class="sxs-lookup"><span data-stu-id="cc866-116">Message Versioning Support</span></span>](message-versioning-support2.md)  
  
