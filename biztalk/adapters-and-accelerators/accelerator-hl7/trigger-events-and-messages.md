---
title: イベントとメッセージをトリガー |Microsoft ドキュメント
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
ms.openlocfilehash: 188d7f1e09ae3f96c953c6a83bbad42ccdce3643
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206538"
---
# <a name="trigger-events-and-messages"></a><span data-ttu-id="334f6-102">イベントを発生させるとメッセージ</span><span class="sxs-lookup"><span data-stu-id="334f6-102">Trigger Events and Messages</span></span>
<span data-ttu-id="334f6-103">デジタルの医療システムでは、アプリケーションは、ラボにおける注文または医薬品の注文の配置などの実際のイベントのため HL7 メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="334f6-103">In a digital health care system, applications create HL7 messages because of a real-world event, such as the placing of a laboratory order or drug order.</span></span> <span data-ttu-id="334f6-104">HL7 組織が医療保険の実際のイベント データをこれらのアプリケーションが異種システムにまたがる場合でも、アプリケーション間でやり取りの必要性を作成することを前提として、HL7 標準を作成しています。</span><span class="sxs-lookup"><span data-stu-id="334f6-104">The HL7 organization has written the HL7 standard based on the assumption that an event in the real world of health care creates the need for data to flow among applications, even when these applications span heterogeneous systems.</span></span> <span data-ttu-id="334f6-105">HL7 標準は、この実際のイベントを呼び出して、*トリガー イベント*です。</span><span class="sxs-lookup"><span data-stu-id="334f6-105">The HL7 standard calls this real-world event a *trigger event*.</span></span> <span data-ttu-id="334f6-106">自動化されたシステムでは、トリガー イベントが認識体系的にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="334f6-106">An automated system must systematically recognize the trigger event.</span></span>  
  
 <span data-ttu-id="334f6-107">この概念を展開するには、次のシナリオを検討してください。</span><span class="sxs-lookup"><span data-stu-id="334f6-107">To expand this concept, consider the following scenario.</span></span> <span data-ttu-id="334f6-108">病院では、到着するまでの患者に病院では、患者の管理ソフトウェア アプリケーションを使用して登録します。</span><span class="sxs-lookup"><span data-stu-id="334f6-108">On arrival at a hospital, a patient registers in a hospital using a patient administration software application.</span></span> <span data-ttu-id="334f6-109">患者のレコードをコミットするには、、アプリケーションは、患者の登録に関する他の病院アプリケーション (会計、ラボなど) を通知するために必要です。</span><span class="sxs-lookup"><span data-stu-id="334f6-109">On committing the patient records, the application needs to inform other hospital applications (such as accounting, labs, and so on) about the registration of the patient.</span></span> <span data-ttu-id="334f6-110">アプリケーション間でこの情報を共有すると、それらのアプリケーションを使用するエンティティは、患者に必要なサービスを提供できるように、必要があります。</span><span class="sxs-lookup"><span data-stu-id="334f6-110">Sharing this information across applications is necessary so that the entities that use those applications can provide the patient with the required services.</span></span> <span data-ttu-id="334f6-111">患者を登録する次の操作は、トリガー イベントの種類です。</span><span class="sxs-lookup"><span data-stu-id="334f6-111">The act of registering a patient is a type of trigger event.</span></span> <span data-ttu-id="334f6-112">通常、Web アプリケーションは、患者のレコードのデータを含む HL7 メッセージを作成することでこのイベントのトリガーを作成します。</span><span class="sxs-lookup"><span data-stu-id="334f6-112">A Web application typically creates this trigger event by creating an HL7 message containing the data for the patient record.</span></span>  
  
 <span data-ttu-id="334f6-113">トリガー イベントは、メッセージを処理するアプリケーションでアクションをトリガーする 1 つまたは複数のメッセージの作成時に常に発生することがします。</span><span class="sxs-lookup"><span data-stu-id="334f6-113">Trigger events always result in the creation of one or more messages that trigger an action in the application that processes the message.</span></span> <span data-ttu-id="334f6-114">IT 担当者が埋め込まれている展開シナリオに関係のあるイベントを発生させる[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 病院基幹業務アプリケーション内で。</span><span class="sxs-lookup"><span data-stu-id="334f6-114">Trigger events are relevant in deployment scenarios where IT personnel have embedded [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) within the hospital line-of-business application.</span></span> <span data-ttu-id="334f6-115">このような展開シナリオであっても[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]するトリガー イベントをトリガー イベントを生成するメッセージだけを認識する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="334f6-115">Even in such deployment scenarios, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not need to be aware of the trigger event, only the messages that the trigger event generates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="334f6-116">参照</span><span class="sxs-lookup"><span data-stu-id="334f6-116">See Also</span></span>  
 <span data-ttu-id="334f6-117">[HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="334f6-117">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="334f6-118">[HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="334f6-118">[Using HL7 2.X Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span></span>  
 <span data-ttu-id="334f6-119">[HL7 2. XML スキーマを使用します。](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="334f6-119">[Using HL7 2.XML Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span></span>  
 [<span data-ttu-id="334f6-120">HL7 メッセージ</span><span class="sxs-lookup"><span data-stu-id="334f6-120">HL7 Messaging</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)