---
title: 受信確認エラーの状態 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, errors
- errors, acknowledgements
ms.assetid: 605c7fa0-2365-4cb6-92fb-6df570905ca8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae28a26d62ec18f6cfb81db55442b8e440b5a93c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247719"
---
# <a name="acknowledgment-error-conditions"></a><span data-ttu-id="a1c2b-102">受信確認エラーの状態</span><span class="sxs-lookup"><span data-stu-id="a1c2b-102">Acknowledgment Error Conditions</span></span>
<span data-ttu-id="a1c2b-103">致命的なエラーで、次の条件が発生条件の場合に Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) (ACK) メッセージを受信確認の処理には。</span><span class="sxs-lookup"><span data-stu-id="a1c2b-103">The following conditions will result in a fatal error condition when Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) is processing acknowledgment (ACK) messages:</span></span>  
  
- <span data-ttu-id="a1c2b-104">MSH9 で必須のフィールドがありません。</span><span class="sxs-lookup"><span data-stu-id="a1c2b-104">Missing required fields in MSH9</span></span>  
  
- <span data-ttu-id="a1c2b-105">MSH12 で必須のフィールドがありません。</span><span class="sxs-lookup"><span data-stu-id="a1c2b-105">Missing required fields in MSH12</span></span>  
  
  <span data-ttu-id="a1c2b-106">致命的なエラー条件で、次の条件が発生します。</span><span class="sxs-lookup"><span data-stu-id="a1c2b-106">The following conditions result in a non-fatal error condition.</span></span> <span data-ttu-id="a1c2b-107">このような状況で[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ACK が生成されますが、また、ACK が中断します。</span><span class="sxs-lookup"><span data-stu-id="a1c2b-107">In this situation, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates the ACK, but also suspends the ACK:</span></span>  
  
- <span data-ttu-id="a1c2b-108">MSH11 で必要なフィールドが見つかりません</span><span class="sxs-lookup"><span data-stu-id="a1c2b-108">Missing a required field in MSH11</span></span>  
  
- <span data-ttu-id="a1c2b-109">MSH10 値がありません。</span><span class="sxs-lookup"><span data-stu-id="a1c2b-109">Missing a MSH10 value</span></span>  
  
- <span data-ttu-id="a1c2b-110">ヘッダーの省略可能なフィールドの列挙型のエラー。</span><span class="sxs-lookup"><span data-stu-id="a1c2b-110">Enumeration type errors for optional fields in the header.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1c2b-111">AL または ER、MSH 15 が設定されている場合、ヘッダーにある列挙型のエラーの[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]コミット ACK の状態が生成されます**MSA_1 CR を =** します。</span><span class="sxs-lookup"><span data-stu-id="a1c2b-111">For enumeration type errors found in the header when MSH 15 is set to AL or ER, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates a commit ACK with the status **MSA_1=CR**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1c2b-112">参照</span><span class="sxs-lookup"><span data-stu-id="a1c2b-112">See Also</span></span>  
 <span data-ttu-id="a1c2b-113">[作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="a1c2b-113">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="a1c2b-114">[ACK メッセージ スキーマの種類](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span><span class="sxs-lookup"><span data-stu-id="a1c2b-114">[ACK Message Schema Types](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span></span>  
 <span data-ttu-id="a1c2b-115">[メッセージの受信確認セグメント](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span><span class="sxs-lookup"><span data-stu-id="a1c2b-115">[Message Acknowledgment Segment](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span></span>  
 [<span data-ttu-id="a1c2b-116">ACK を受信するための送信ポートの設定</span><span class="sxs-lookup"><span data-stu-id="a1c2b-116">Setting Up a Send Port for Receiving ACKs</span></span>](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)