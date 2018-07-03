---
title: トリガー イベントとメッセージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- health care organizations, HL7 messages
- trigger events
- messages, trigger events
- messages, about messages
ms.assetid: e93b397c-8cbe-4589-aa88-e474d7722174
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 309d420d97cdc22c4f0eaca30bb6426e295cbe33
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971611"
---
# <a name="trigger-events-and-messages"></a><span data-ttu-id="52012-102">トリガー イベントとメッセージ</span><span class="sxs-lookup"><span data-stu-id="52012-102">Trigger Events and Messages</span></span>
<span data-ttu-id="52012-103">デジタルの医療システムでは、アプリケーションは、ラボにおける注文または薬の順序の配置などの実際のイベントのため HL7 メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="52012-103">In a digital health care system, applications create HL7 messages because of a real-world event, such as the placing of a laboratory order or drug order.</span></span> <span data-ttu-id="52012-104">HL7 の組織には、医療保険の実際のイベントは、これらのアプリケーションが異種システムにまたがる場合でも、アプリケーション間でフローにデータの必要性を作成することを前提と HL7 標準が書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="52012-104">The HL7 organization has written the HL7 standard based on the assumption that an event in the real world of health care creates the need for data to flow among applications, even when these applications span heterogeneous systems.</span></span> <span data-ttu-id="52012-105">HL7 標準は、この実際のイベントを呼び出して、*トリガー イベント*します。</span><span class="sxs-lookup"><span data-stu-id="52012-105">The HL7 standard calls this real-world event a *trigger event*.</span></span> <span data-ttu-id="52012-106">自動化されたシステムは、トリガー イベントを認識体系的にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="52012-106">An automated system must systematically recognize the trigger event.</span></span>  
  
 <span data-ttu-id="52012-107">この概念を展開するには、次のシナリオを検討してください。</span><span class="sxs-lookup"><span data-stu-id="52012-107">To expand this concept, consider the following scenario.</span></span> <span data-ttu-id="52012-108">病院に到着してすぐには、患者が病院では、患者の管理ソフトウェア アプリケーションを使用して登録します。</span><span class="sxs-lookup"><span data-stu-id="52012-108">On arrival at a hospital, a patient registers in a hospital using a patient administration software application.</span></span> <span data-ttu-id="52012-109">患者のレコードをコミットするには、アプリケーションが必要 (会計、ラボなど) には、他の病院アプリケーションを通知するために、患者の登録についてです。</span><span class="sxs-lookup"><span data-stu-id="52012-109">On committing the patient records, the application needs to inform other hospital applications (such as accounting, labs, and so on) about the registration of the patient.</span></span> <span data-ttu-id="52012-110">アプリケーション間でこの情報を共有すると、それらのアプリケーションを使用するエンティティが必要なサービスで患者を提供できるように、必要があります。</span><span class="sxs-lookup"><span data-stu-id="52012-110">Sharing this information across applications is necessary so that the entities that use those applications can provide the patient with the required services.</span></span> <span data-ttu-id="52012-111">動作は、患者を登録するには、トリガー イベントの一種です。</span><span class="sxs-lookup"><span data-stu-id="52012-111">The act of registering a patient is a type of trigger event.</span></span> <span data-ttu-id="52012-112">通常、Web アプリケーションは、送信された患者レコードのデータを含む、HL7 メッセージを作成してこのトリガー イベントを作成します。</span><span class="sxs-lookup"><span data-stu-id="52012-112">A Web application typically creates this trigger event by creating an HL7 message containing the data for the patient record.</span></span>  
  
 <span data-ttu-id="52012-113">トリガー イベントは、メッセージを処理するアプリケーションでアクションをトリガーする 1 つまたは複数のメッセージの作成時に常にあります。</span><span class="sxs-lookup"><span data-stu-id="52012-113">Trigger events always result in the creation of one or more messages that trigger an action in the application that processes the message.</span></span> <span data-ttu-id="52012-114">トリガー イベントは、IT 担当者が埋め込まれている Microsoft BizTalk Accelerator for HL7 の配置シナリオに関連する ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 病院の基幹業務アプリケーション内で。</span><span class="sxs-lookup"><span data-stu-id="52012-114">Trigger events are relevant in deployment scenarios where IT personnel have embedded Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) within the hospital line-of-business application.</span></span> <span data-ttu-id="52012-115">このような展開シナリオであっても[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]トリガー イベントをトリガー イベントを生成するメッセージのみ意識する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="52012-115">Even in such deployment scenarios, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not need to be aware of the trigger event, only the messages that the trigger event generates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52012-116">参照</span><span class="sxs-lookup"><span data-stu-id="52012-116">See Also</span></span>  
 <span data-ttu-id="52012-117">[HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="52012-117">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="52012-118">[HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="52012-118">[Using HL7 2.X Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span></span>  
 <span data-ttu-id="52012-119">[HL7 2. XML スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="52012-119">[Using HL7 2.XML Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span></span>  
 [<span data-ttu-id="52012-120">HL7 メッセージング</span><span class="sxs-lookup"><span data-stu-id="52012-120">HL7 Messaging</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)