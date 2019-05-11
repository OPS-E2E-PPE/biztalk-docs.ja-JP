---
title: メッセージの受信確認セグメント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- segments, acknowledgements
- acknowledgements, segments
ms.assetid: 6f2b9f6f-a328-4a0f-9e7d-edba32cc045a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20c0e8377666d551867148ebff871b6728e8b561
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65309584"
---
# <a name="message-acknowledgment-segment"></a><span data-ttu-id="e4e43-102">メッセージの受信確認セグメント</span><span class="sxs-lookup"><span data-stu-id="e4e43-102">Message Acknowledgment Segment</span></span>
<span data-ttu-id="e4e43-103">受信確認 (ACK) メッセージのメッセージ受信確認 (MSA) セグメントでは、ACK を受信する、システムが送信を示し、どのようなメッセージの受信確認の種類を識別します。</span><span class="sxs-lookup"><span data-stu-id="e4e43-103">The Message Acknowledgment (MSA) segment of an acknowledgment (ACK) message identifies what type of acknowledgment the system is sending, and indicates what message the ACK is acknowledging.</span></span> <span data-ttu-id="e4e43-104">2 つの必須セグメントで構成されています。 受信確認、コードとメッセージのコントロール id。</span><span class="sxs-lookup"><span data-stu-id="e4e43-104">It consists of two required segments: an acknowledgment code and a message control ID.</span></span>  

## <a name="acknowledgment-code-msa1"></a><span data-ttu-id="e4e43-105">受信確認コード:MSA1</span><span class="sxs-lookup"><span data-stu-id="e4e43-105">Acknowledgment Code: MSA1</span></span>  
 <span data-ttu-id="e4e43-106">次の表では、メッセージの受信の結果を示す MSA1 の使用可能なフィールド値を示します。</span><span class="sxs-lookup"><span data-stu-id="e4e43-106">The following table lists the available MSA1 field values indicating the result of the message receiving.</span></span>  

|<span data-ttu-id="e4e43-107">値</span><span class="sxs-lookup"><span data-stu-id="e4e43-107">Value</span></span>|<span data-ttu-id="e4e43-108">説明</span><span class="sxs-lookup"><span data-stu-id="e4e43-108">Meaning</span></span>|<span data-ttu-id="e4e43-109">説明</span><span class="sxs-lookup"><span data-stu-id="e4e43-109">Description</span></span>|  
|-----------|-------------|-----------------|  
|<span data-ttu-id="e4e43-110">AA</span><span class="sxs-lookup"><span data-stu-id="e4e43-110">AA</span></span>|<span data-ttu-id="e4e43-111">アプリケーションの受信確認</span><span class="sxs-lookup"><span data-stu-id="e4e43-111">Application Acknowledgment</span></span>|<span data-ttu-id="e4e43-112">システムがメッセージを受信してそれを問題なく処理します。</span><span class="sxs-lookup"><span data-stu-id="e4e43-112">The system has received the message and processed it with no problem.</span></span>|  
|<span data-ttu-id="e4e43-113">AE</span><span class="sxs-lookup"><span data-stu-id="e4e43-113">AE</span></span>|<span data-ttu-id="e4e43-114">アプリケーション エラー</span><span class="sxs-lookup"><span data-stu-id="e4e43-114">Application Error</span></span>|<span data-ttu-id="e4e43-115">受信側のアプリケーション メッセージまたはその構造に関連する処理の問題が発生しました。</span><span class="sxs-lookup"><span data-stu-id="e4e43-115">A processing problem related to the message or its structure occurred at the receiving application.</span></span> <span data-ttu-id="e4e43-116">送信元システムは、診断し、メッセージの再送を試行する前に、問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4e43-116">The sending system should diagnose and correct the problem before attempting to resend the message.</span></span>|  
|<span data-ttu-id="e4e43-117">AR</span><span class="sxs-lookup"><span data-stu-id="e4e43-117">AR</span></span>|<span data-ttu-id="e4e43-118">アプリケーションの却下</span><span class="sxs-lookup"><span data-stu-id="e4e43-118">Application Reject</span></span>|<span data-ttu-id="e4e43-119">MSH9 の値に関連する受信場所で、いずれかの問題が発生しました (メッセージの種類)、MSH11 (ID を処理)、または MSH12 (バージョン ID) の場合、送信元システムが診断し、メッセージを再送信する前に問題が解決する必要がありますまたは、メッセージや場合、送信元システムがメッセージを変更しなくても、適切な期間の後にメッセージを再送する必要があります、その構造に関連した受信側のシステムで問題が発生しました。</span><span class="sxs-lookup"><span data-stu-id="e4e43-119">Either a problem occurred at the receiving location related to the value in MSH9 (message type), MSH11 (processing ID), or MSH12 (version ID), in which case the sending system should diagnose and correct the problem before resending the message; or a problem occurred at the receiving system that was unrelated to the message or its structure, in which case the sending system should resend the message after an appropriate period, without change to the message.</span></span>|  

## <a name="message-control-id-msa2"></a><span data-ttu-id="e4e43-120">メッセージのコントロール ID (MSA2)</span><span class="sxs-lookup"><span data-stu-id="e4e43-120">Message Control ID (MSA2)</span></span>  
 <span data-ttu-id="e4e43-121">MSA2 フィールドには、ACK が受信確認メッセージが識別されます。</span><span class="sxs-lookup"><span data-stu-id="e4e43-121">The MSA2 field identifies the message that the ACK is acknowledging.</span></span> <span data-ttu-id="e4e43-122">Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 受信確認のモードに基づいて MSA2 で値が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e4e43-122">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) generates the value in MSA2 based upon the acknowledgment mode.</span></span> <span data-ttu-id="e4e43-123">この値は、メッセージを送信側と受信側アプリケーションを有効にし、受信確認を同期します。</span><span class="sxs-lookup"><span data-stu-id="e4e43-123">This value enables the sending and receiving applications to keep the message and the acknowledgment synchronized.</span></span> <span data-ttu-id="e4e43-124">次の表では、MSA2 フィールドに使用できる値を示します。</span><span class="sxs-lookup"><span data-stu-id="e4e43-124">The following table lists the available values for the MSA2 field.</span></span>  


|            <span data-ttu-id="e4e43-125">受信確認のモード</span><span class="sxs-lookup"><span data-stu-id="e4e43-125">Acknowledgment Mode</span></span>            |                                                           <span data-ttu-id="e4e43-126">MSA2 内の値</span><span class="sxs-lookup"><span data-stu-id="e4e43-126">Value in MSA2</span></span>                                                            |
|-------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|               <span data-ttu-id="e4e43-127">元のモード</span><span class="sxs-lookup"><span data-stu-id="e4e43-127">Original mode</span></span>               |                  <span data-ttu-id="e4e43-128">転置、MSH10 内の値の値 (コントロールの ID をメッセージ)、元のメッセージのフィールド</span><span class="sxs-lookup"><span data-stu-id="e4e43-128">A transposed value of the value in the MSH10 (message control ID) field of the original message</span></span>                   |
|   <span data-ttu-id="e4e43-129">拡張モード:受信確認をコミットします。</span><span class="sxs-lookup"><span data-stu-id="e4e43-129">Enhanced Mode: Commit Acknowledgment</span></span>    |                  <span data-ttu-id="e4e43-130">転置、MSH10 内の値の値 (コントロールの ID をメッセージ)、元のメッセージのフィールド</span><span class="sxs-lookup"><span data-stu-id="e4e43-130">A transposed value of the value in the MSH10 (message control ID) field of the original message</span></span>                   |
| <span data-ttu-id="e4e43-131">拡張モード:アプリケーションの受信確認</span><span class="sxs-lookup"><span data-stu-id="e4e43-131">Enhanced Mode: Application Acknowledgment</span></span> | <span data-ttu-id="e4e43-132">によって生成された GUID[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]受信確認の場合</span><span class="sxs-lookup"><span data-stu-id="e4e43-132">A GUID generated by [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] for the acknowledgment</span></span> |

## <a name="see-also"></a><span data-ttu-id="e4e43-133">参照</span><span class="sxs-lookup"><span data-stu-id="e4e43-133">See Also</span></span>  
 <span data-ttu-id="e4e43-134">[作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="e4e43-134">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="e4e43-135">[ACK メッセージ スキーマの種類](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span><span class="sxs-lookup"><span data-stu-id="e4e43-135">[ACK Message Schema Types](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span></span>  
 <span data-ttu-id="e4e43-136">[Ack を受信するための送信ポートの設定](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md) </span><span class="sxs-lookup"><span data-stu-id="e4e43-136">[Setting Up a Send Port for Receiving ACKs](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md) </span></span>  
 [<span data-ttu-id="e4e43-137">受信確認エラーの条件</span><span class="sxs-lookup"><span data-stu-id="e4e43-137">Acknowledgment Error Conditions</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)