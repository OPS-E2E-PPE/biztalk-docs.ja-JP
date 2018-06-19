---
title: 受信確認エラーの状態 |Microsoft ドキュメント
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
ms.openlocfilehash: 15b481f4cdb60822841021f7f708a6caea021b8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204586"
---
# <a name="acknowledgment-error-conditions"></a><span data-ttu-id="2ddb3-102">受信確認エラー条件</span><span class="sxs-lookup"><span data-stu-id="2ddb3-102">Acknowledgment Error Conditions</span></span>
<span data-ttu-id="2ddb3-103">致命的なエラーで、次の条件が発生条件の場合に[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) は、処理の受信確認 (ACK) メッセージ。</span><span class="sxs-lookup"><span data-stu-id="2ddb3-103">The following conditions will result in a fatal error condition when [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) is processing acknowledgment (ACK) messages:</span></span>  
  
-   <span data-ttu-id="2ddb3-104">MSH9 内の必須フィールドがありません。</span><span class="sxs-lookup"><span data-stu-id="2ddb3-104">Missing required fields in MSH9</span></span>  
  
-   <span data-ttu-id="2ddb3-105">MSH12 内の必須フィールドがありません。</span><span class="sxs-lookup"><span data-stu-id="2ddb3-105">Missing required fields in MSH12</span></span>  
  
 <span data-ttu-id="2ddb3-106">次の条件は結果として、致命的なエラー状態です。</span><span class="sxs-lookup"><span data-stu-id="2ddb3-106">The following conditions result in a non-fatal error condition.</span></span> <span data-ttu-id="2ddb3-107">このような状況で[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ACK が生成されますが、また、ACK が中断します。</span><span class="sxs-lookup"><span data-stu-id="2ddb3-107">In this situation, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates the ACK, but also suspends the ACK:</span></span>  
  
-   <span data-ttu-id="2ddb3-108">MSH11 の必須フィールドがありません。</span><span class="sxs-lookup"><span data-stu-id="2ddb3-108">Missing a required field in MSH11</span></span>  
  
-   <span data-ttu-id="2ddb3-109">MSH10 値がありません。</span><span class="sxs-lookup"><span data-stu-id="2ddb3-109">Missing a MSH10 value</span></span>  
  
-   <span data-ttu-id="2ddb3-110">ヘッダーにオプションのフィールドに列挙型のエラーです。</span><span class="sxs-lookup"><span data-stu-id="2ddb3-110">Enumeration type errors for optional fields in the header.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ddb3-111">AL または ER、MSH 15 が設定されている場合、ヘッダーにある列挙型のエラーの[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]コミット ACK の状態が生成されます**MSA_1 = CR**です。</span><span class="sxs-lookup"><span data-stu-id="2ddb3-111">For enumeration type errors found in the header when MSH 15 is set to AL or ER, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates a commit ACK with the status **MSA_1=CR**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ddb3-112">参照</span><span class="sxs-lookup"><span data-stu-id="2ddb3-112">See Also</span></span>  
 <span data-ttu-id="2ddb3-113">[作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="2ddb3-113">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="2ddb3-114">[ACK メッセージ スキーマの種類](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span><span class="sxs-lookup"><span data-stu-id="2ddb3-114">[ACK Message Schema Types](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span></span>  
 <span data-ttu-id="2ddb3-115">[メッセージ受信確認セグメント](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span><span class="sxs-lookup"><span data-stu-id="2ddb3-115">[Message Acknowledgment Segment](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span></span>  
 [<span data-ttu-id="2ddb3-116">Ack を受信するための送信ポートの設定</span><span class="sxs-lookup"><span data-stu-id="2ddb3-116">Setting Up a Send Port for Receiving ACKs</span></span>](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)