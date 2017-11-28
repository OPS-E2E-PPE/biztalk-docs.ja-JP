---
title: "静的な受信確認 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- static acknowledgements
- acknowledgements, static acknowledgements
ms.assetid: 1cdd01fc-1dae-4851-917f-4f13a0f9595a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8081dc0f3c37c40cb1103567ae06f80037a12730
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="static-acknowledgments"></a><span data-ttu-id="cfe8e-102">静的な受信確認</span><span class="sxs-lookup"><span data-stu-id="cfe8e-102">Static Acknowledgments</span></span>
<span data-ttu-id="cfe8e-103">BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 元、強化された、遅延、および静的な受信確認 (ACK) モードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="cfe8e-103">BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) supports original, enhanced, deferred, and static acknowledgment (ACK) modes.</span></span> <span data-ttu-id="cfe8e-104">パーティの静的 ACK モードを選択するかどうかは[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーで、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]を成功または失敗を示す値だけを含む静的 Ack が生成されます。</span><span class="sxs-lookup"><span data-stu-id="cfe8e-104">If you select static ACK mode for a party in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will generate static ACKs that contain only an indication of success or failure.</span></span> <span data-ttu-id="cfe8e-105">静的 ACK がエラー値で構成し、受信側のシステムが受信され、成功した場合に、メッセージを処理するかどうかを示す[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。</span><span class="sxs-lookup"><span data-stu-id="cfe8e-105">The static ACK indicates whether the receiving system received and processed the message, in success and failure values configured in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
 <span data-ttu-id="cfe8e-106">元に強化され、遅延モードの場合、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]動的 Ack が生成されます。</span><span class="sxs-lookup"><span data-stu-id="cfe8e-106">In original, enhanced, and deferred modes, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates dynamic ACKs.</span></span> <span data-ttu-id="cfe8e-107">HL7 でエンコードされたされ MSA.1 受信確認コード フィールドであり、ERR セグメントなどのフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cfe8e-107">They are HL7-encoded, and contain fields such as the MSA.1 Acknowledgment Code field and the ERR segment.</span></span> <span data-ttu-id="cfe8e-108">動的 ACK の MSA.1 フィールドが示されますかどうか、エラー条件を拒否するか、別の処理が発生するエラー (を参照してください[メッセージ受信確認セグメント](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md))。</span><span class="sxs-lookup"><span data-stu-id="cfe8e-108">The MSA.1 field of a dynamic ACK will indicate whether a failure condition is a Reject or an Error, which result in different processing (see [Message Acknowledgment Segment](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)).</span></span> <span data-ttu-id="cfe8e-109">ERR セグメントは、エラーに関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="cfe8e-109">The ERR segment provides detailed information about the error.</span></span> <span data-ttu-id="cfe8e-110">静的 Ack は、このような情報を提供されません。</span><span class="sxs-lookup"><span data-stu-id="cfe8e-110">Static ACKs provide no such information.</span></span>  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="cfe8e-111">動的受信を異なる静的 ACK を処理します。</span><span class="sxs-lookup"><span data-stu-id="cfe8e-111"> processes a static ACK differently from a dynamic ACK.</span></span> <span data-ttu-id="cfe8e-112">(これは、ACK を受信した後、次のメッセージが送信のみされます)、双方向の送信ポートを受信した場合、静的 ACK ACK 失敗を示します (または有効 ACK ではありません)、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]はセカンダリ トランスポートに移動するか、メッセージを中断します。</span><span class="sxs-lookup"><span data-stu-id="cfe8e-112">If a two-way send port (which will only send the next message after receiving the ACK) receives the static ACK, and the ACK indicates failure (or is not a valid ACK), [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will move to the secondary transport or suspend the message.</span></span> <span data-ttu-id="cfe8e-113">エラー状態に応じて、動的 ACK を受信した場合と同様、メッセージは再試行されません。</span><span class="sxs-lookup"><span data-stu-id="cfe8e-113">It will not retry the message, as it would if it received a dynamic ACK, depending upon the failure condition.</span></span>  
  
 <span data-ttu-id="cfe8e-114">ときに、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]書き込みますパーサーでは、静的な確認を処理する、 **IsStaticAck**メッセージ コンテキストにブール型プロパティです。</span><span class="sxs-lookup"><span data-stu-id="cfe8e-114">When the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] parser processes a static ACK, it writes the **IsStaticAck** Boolean property to the message context.</span></span> <span data-ttu-id="cfe8e-115">シリアライザーでは、この値を使用して、静的な確認メッセージを処理するかどうかを決定</span><span class="sxs-lookup"><span data-stu-id="cfe8e-115">The serializer uses this value to determine whether it should process the message as a static ACK.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfe8e-116">参照</span><span class="sxs-lookup"><span data-stu-id="cfe8e-116">See Also</span></span>  
 <span data-ttu-id="cfe8e-117">[作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="cfe8e-117">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 [<span data-ttu-id="cfe8e-118">メッセージ受信確認セグメント</span><span class="sxs-lookup"><span data-stu-id="cfe8e-118">Message Acknowledgment Segment</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)