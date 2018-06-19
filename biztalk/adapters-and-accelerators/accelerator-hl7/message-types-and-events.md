---
title: メッセージの種類とイベント |Microsoft ドキュメント
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
ms.openlocfilehash: 9b9880da0ca5fea84c5a2b3d6e9f3a43ace41970
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205954"
---
# <a name="message-types-and-events"></a><span data-ttu-id="3586d-102">メッセージの種類およびイベント</span><span class="sxs-lookup"><span data-stu-id="3586d-102">Message Types and Events</span></span>
<span data-ttu-id="3586d-103">HL7 標準が実際のイベントとしてまとめての特定のグループ化に関連するメッセージをグループ化*メッセージの種類*ADT です。</span><span class="sxs-lookup"><span data-stu-id="3586d-103">The HL7 standard has grouped messages that relate to a particular grouping of real-world events together as *message type* ADT.</span></span> <span data-ttu-id="3586d-104">これらのメッセージには、患者の管理などのトリガー イベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3586d-104">These messages involve trigger events, such as patient administration.</span></span> <span data-ttu-id="3586d-105">HL7 標準のバージョン 2.4 は、100 個を超えるメッセージの種類、それぞれの HL7 組織が割り当てられている 3 文字の一意のメッセージ型のコードを定義します。</span><span class="sxs-lookup"><span data-stu-id="3586d-105">Version 2.4 of the HL7 standard defines more than 100 message types, each of which the HL7 organization has assigned a unique three-character message type code.</span></span> <span data-ttu-id="3586d-106">HL7 標準のバージョンがきたよう HL7 組織が新しい機能を提供する新しいメッセージの種類を追加します。</span><span class="sxs-lookup"><span data-stu-id="3586d-106">As versions of the HL7 standard have evolved, the HL7 organization has added new message types to provide new capabilities.</span></span>  
  
 <span data-ttu-id="3586d-107">すべてのメッセージ型とも呼ばれる、メッセージ イベントを含む*イベント*です。</span><span class="sxs-lookup"><span data-stu-id="3586d-107">All message types contain message events, also called *events*.</span></span> <span data-ttu-id="3586d-108">特定のメッセージ型の中でグループ化されたメッセージの一意の型としてイベントを検討することができます。</span><span class="sxs-lookup"><span data-stu-id="3586d-108">You can think of an event as a unique type of message grouped within a particular message type.</span></span> <span data-ttu-id="3586d-109">たとえば、Admin 訪問/通知 (メッセージ イベント A01) および放電/終了 (メッセージ イベント A03) を参照してくださいは、患者管理メッセージの種類 (ADT) に含まれる一意のメッセージです。</span><span class="sxs-lookup"><span data-stu-id="3586d-109">For example, the Admin/Visit Notification (message event A01) and Discharge/End Visit (message event A03) are unique messages contained by the Patient Administration message type (ADT).</span></span> <span data-ttu-id="3586d-110">HL7 組織が割り当てられているメッセージの各イベントは一意のイベントの 3 文字コード。</span><span class="sxs-lookup"><span data-stu-id="3586d-110">The HL7 organization has assigned each message event a unique three-character event code.</span></span>  
  
 <span data-ttu-id="3586d-111">1 つだけのメッセージの種類は、特定のメッセージ イベントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3586d-111">Only one message type can contain a particular message event.</span></span> <span data-ttu-id="3586d-112">メッセージの種類は、複数のメッセージ イベントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3586d-112">Message types can contain multiple message events.</span></span> <span data-ttu-id="3586d-113">ただし、特定のメッセージ イベントの構造は、HL7 標準のバージョンによって異なることができます。</span><span class="sxs-lookup"><span data-stu-id="3586d-113">However, the structure of a particular message event can vary between versions of the HL7 standard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3586d-114">参照</span><span class="sxs-lookup"><span data-stu-id="3586d-114">See Also</span></span>  
 <span data-ttu-id="3586d-115">[HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="3586d-115">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="3586d-116">[HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="3586d-116">[Using HL7 2.X Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span></span>  
 <span data-ttu-id="3586d-117">[HL7 2. XML スキーマを使用します。](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="3586d-117">[Using HL7 2.XML Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span></span>  
 <span data-ttu-id="3586d-118">[イベントを発生させるとメッセージ](../../adapters-and-accelerators/accelerator-hl7/trigger-events-and-messages.md) </span><span class="sxs-lookup"><span data-stu-id="3586d-118">[Trigger Events and Messages](../../adapters-and-accelerators/accelerator-hl7/trigger-events-and-messages.md) </span></span>  
 [<span data-ttu-id="3586d-119">HL7 メッセージ</span><span class="sxs-lookup"><span data-stu-id="3586d-119">HL7 Messaging</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)