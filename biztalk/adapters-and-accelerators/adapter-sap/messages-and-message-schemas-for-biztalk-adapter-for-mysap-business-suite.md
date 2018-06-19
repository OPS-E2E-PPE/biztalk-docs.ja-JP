---
title: メッセージと BizTalk Adapter 用 mySAP Business Suite のメッセージ スキーマを |Microsoft ドキュメント
description: BizTalk Server 用 mySAP アダプターによって使用されるメッセージとデータ型の XML 構造
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75ea5c27-8297-47bf-bcfd-503870349189
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9db6ec6b0fbea7ce5c8f90158126d52cbc7530ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216346"
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite"></a><span data-ttu-id="4daed-103">メッセージと BizTalk Adapter 用 mySAP Business Suite のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="4daed-103">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>

## <a name="overview"></a><span data-ttu-id="4daed-104">概要</span><span class="sxs-lookup"><span data-stu-id="4daed-104">Overview</span></span>
<span data-ttu-id="4daed-105">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。</span><span class="sxs-lookup"><span data-stu-id="4daed-105">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="4daed-106">これは、アプリケーションがそれで呼び出すことができ、アプリケーションで呼び出すことができます、さらに、操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="4daed-106">It exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="4daed-107">これらの操作がチャネル経由で SOAP メッセージを送信することによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4daed-107">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="4daed-108">応答が必要な場合、同じチャネル経由で SOAP メッセージで返されます。</span><span class="sxs-lookup"><span data-stu-id="4daed-108">If a response is required, it is returned in a SOAP message over the same channel.</span></span>  
  
 <span data-ttu-id="4daed-109">として、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]標準を使用してその操作とデータ型のメタデータが公開[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]メカニズムです。</span><span class="sxs-lookup"><span data-stu-id="4daed-109">As a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] exposes metadata for its operations and data types by using standard [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] mechanisms.</span></span> <span data-ttu-id="4daed-110">このトピックのセクションでは、メッセージの XML 構造の記述し、データの種類を[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を使用します。</span><span class="sxs-lookup"><span data-stu-id="4daed-110">The sections in this topic describe the XML structure of the messages and data types that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4daed-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4daed-111">In This Section</span></span>  
  
-   [<span data-ttu-id="4daed-112">基本的な SAP データ型</span><span class="sxs-lookup"><span data-stu-id="4daed-112">Basic SAP Data Types</span></span>](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md)  
  
-   [<span data-ttu-id="4daed-113">カスタム Rfc のデータ型マッピング</span><span class="sxs-lookup"><span data-stu-id="4daed-113">Data Type Mapping for Custom RFCs</span></span>](../../adapters-and-accelerators/adapter-sap/data-type-mapping-for-custom-rfcs.md)  
  
-   [<span data-ttu-id="4daed-114">IDOC 操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="4daed-114">Message Schemas for IDOC Operations</span></span>](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)  
  
-   [<span data-ttu-id="4daed-115">Idoc を受信するためのメッセージ コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="4daed-115">Message Context Properties for Receiving IDOCs</span></span>](../../adapters-and-accelerators/adapter-sap/message-context-properties-for-receiving-idocs.md)  
  
-   [<span data-ttu-id="4daed-116">RFC 操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="4daed-116">Message Schemas for RFC Operations</span></span>](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)  
  
-   [<span data-ttu-id="4daed-117">TRFC 操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="4daed-117">Message Schemas for tRFC Operations</span></span>](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)  
  
-   [<span data-ttu-id="4daed-118">BAPI 操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="4daed-118">Message Schemas for BAPI Operations</span></span>](../../adapters-and-accelerators/adapter-sap/message-schemas-for-bapi-operations.md)  
  
-   [<span data-ttu-id="4daed-119">特別な操作</span><span class="sxs-lookup"><span data-stu-id="4daed-119">Special Operations</span></span>](../../adapters-and-accelerators/adapter-sap/special-operations.md)  
  
-   [<span data-ttu-id="4daed-120">メッセージ バージョン管理のサポート</span><span class="sxs-lookup"><span data-stu-id="4daed-120">Message Versioning Support</span></span>](../../adapters-and-accelerators/adapter-sap/message-versioning-support1.md)  
  
