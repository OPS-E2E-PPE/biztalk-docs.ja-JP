---
title: メッセージの種類とイベント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, message events
- HL7, message types
- message types
- messages, message types
ms.assetid: d53d51d0-216d-472b-97b7-8a96b8013510
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 143223d0ed0f03d6eaa66141ea052ed701638e56
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303656"
---
# <a name="message-types-and-events"></a><span data-ttu-id="e8790-102">メッセージの種類とイベント</span><span class="sxs-lookup"><span data-stu-id="e8790-102">Message Types and Events</span></span>
<span data-ttu-id="e8790-103">HL7 標準が実際のイベントとしてまとめての特定のグループ化に関連するメッセージをグループ化*メッセージの種類*ADT します。</span><span class="sxs-lookup"><span data-stu-id="e8790-103">The HL7 standard has grouped messages that relate to a particular grouping of real-world events together as *message type* ADT.</span></span> <span data-ttu-id="e8790-104">これらのメッセージには、患者の管理などのトリガー イベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e8790-104">These messages involve trigger events, such as patient administration.</span></span> <span data-ttu-id="e8790-105">HL7 標準のバージョン 2.4 は、100 を超えるメッセージの種類、それぞれの HL7 組織が割り当てられている一意の 3 文字メッセージ型のコードを定義します。</span><span class="sxs-lookup"><span data-stu-id="e8790-105">Version 2.4 of the HL7 standard defines more than 100 message types, each of which the HL7 organization has assigned a unique three-character message type code.</span></span> <span data-ttu-id="e8790-106">HL7 標準のバージョンが発展すると、HL7 組織の新機能を提供する新しいメッセージの種類が追加されます。</span><span class="sxs-lookup"><span data-stu-id="e8790-106">As versions of the HL7 standard have evolved, the HL7 organization has added new message types to provide new capabilities.</span></span>  
  
 <span data-ttu-id="e8790-107">すべてのメッセージ型とも呼ばれる、メッセージ イベントが含まれている*イベント*します。</span><span class="sxs-lookup"><span data-stu-id="e8790-107">All message types contain message events, also called *events*.</span></span> <span data-ttu-id="e8790-108">イベント メッセージの特定のメッセージ型内でグループ化の一意の型として考えることができます。</span><span class="sxs-lookup"><span data-stu-id="e8790-108">You can think of an event as a unique type of message grouped within a particular message type.</span></span> <span data-ttu-id="e8790-109">たとえば、管理者のアクセス/通知 (メッセージ イベント A01) と放電/終了 (メッセージ イベント A03) を参照してくださいは、患者管理メッセージの種類 (ADT) に含まれる一意のメッセージが。</span><span class="sxs-lookup"><span data-stu-id="e8790-109">For example, the Admin/Visit Notification (message event A01) and Discharge/End Visit (message event A03) are unique messages contained by the Patient Administration message type (ADT).</span></span> <span data-ttu-id="e8790-110">HL7 組織では、一意の 3 文字イベント コードを各メッセージ イベントを割り当ています。</span><span class="sxs-lookup"><span data-stu-id="e8790-110">The HL7 organization has assigned each message event a unique three-character event code.</span></span>  
  
 <span data-ttu-id="e8790-111">1 つだけのメッセージの種類には、特定のメッセージ イベントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e8790-111">Only one message type can contain a particular message event.</span></span> <span data-ttu-id="e8790-112">メッセージの種類は、複数のメッセージ イベントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e8790-112">Message types can contain multiple message events.</span></span> <span data-ttu-id="e8790-113">ただし、特定のメッセージ イベントの構造は、HL7 標準のバージョン間で異なることができます。</span><span class="sxs-lookup"><span data-stu-id="e8790-113">However, the structure of a particular message event can vary between versions of the HL7 standard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8790-114">参照</span><span class="sxs-lookup"><span data-stu-id="e8790-114">See Also</span></span>  
 <span data-ttu-id="e8790-115">[HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="e8790-115">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="e8790-116">[HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="e8790-116">[Using HL7 2.X Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span></span>  
 <span data-ttu-id="e8790-117">[HL7 2. XML スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="e8790-117">[Using HL7 2.XML Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span></span>  
 <span data-ttu-id="e8790-118">[トリガー イベントとメッセージ](../../adapters-and-accelerators/accelerator-hl7/trigger-events-and-messages.md) </span><span class="sxs-lookup"><span data-stu-id="e8790-118">[Trigger Events and Messages](../../adapters-and-accelerators/accelerator-hl7/trigger-events-and-messages.md) </span></span>  
 [<span data-ttu-id="e8790-119">HL7 メッセージング</span><span class="sxs-lookup"><span data-stu-id="e8790-119">HL7 Messaging</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)