---
title: "受信確認の既知の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- known issues, acknowledgements
- acknowledgements, known issues
ms.assetid: cb45f80e-ba89-4b3f-a770-4b1cf9b8e220
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af5964e94f2ddc1d53d5259b174f8e551353711d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="acknowledgments-known-issues"></a><span data-ttu-id="0dc72-102">受信確認の既知の問題</span><span class="sxs-lookup"><span data-stu-id="0dc72-102">Acknowledgments Known Issues</span></span>
<span data-ttu-id="0dc72-103">このセクションには、受信確認 (ACK) のエラーを回避するために役立つ有用な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0dc72-103">This section contains useful information that may help you avoid acknowledgment (ACK) errors.</span></span>  
  
## <a name="hl7-v21-acknowledgment-message-accepted-even-if-it-contains-msa6-field"></a><span data-ttu-id="0dc72-104">MSA6 フィールドが含まれている場合でも、HL7 V2.1 受信確認メッセージが受け入れられます</span><span class="sxs-lookup"><span data-stu-id="0dc72-104">HL7 V2.1 acknowledgment message accepted even if it contains MSA6 field</span></span>  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="0dc72-105">[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 場合でも、MSA6 フィールドが含まれています、HL7 V2.1 受信確認メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0dc72-105"> [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) will accept a HL7 V2.1 acknowledgment message even if contains the MSA6 field.</span></span>  
  
## <a name="msa-01-value-not-generated-for-commit-acknowledgment-errors"></a><span data-ttu-id="0dc72-106">MSA-01 値がコミット受信確認エラーは生成されません。</span><span class="sxs-lookup"><span data-stu-id="0dc72-106">MSA-01 value not generated for commit acknowledgment errors</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="0dc72-107">MSA 01、受信確認コード内のコミットの受信確認エラー (CE) を生成しません。</span><span class="sxs-lookup"><span data-stu-id="0dc72-107"> does not generate an MSA-01 acknowledgment code for commit acknowledgments errors (CE).</span></span>  
  
## <a name="two-way-mllp-adapter-might-not-detect-a-problem-with-an-ack"></a><span data-ttu-id="0dc72-108">双方向の MLLP アダプターは、ACK に問題を検出できません可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="0dc72-108">Two-way MLLP adapter might not detect a problem with an ACK</span></span>  
 <span data-ttu-id="0dc72-109">ときに[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ACK を受信する双方向の MLLP アダプターのアダプターがその有効性を決定する ACK の軽量な検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="0dc72-109">When [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] receives an ACK on a two-way MLLP adapter, the adapter performs a lightweight validation on the ACK to determine its validity.</span></span> <span data-ttu-id="0dc72-110">見つかった場合は有効である、MSA1 フィールドを抽出すると、およびその値に応じて、アダプター再試行、中断、または、ACK が応答していた元のメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="0dc72-110">If it is found to be valid, the MSA1 field is extracted, and depending on its value, the adapter retries, suspends, or deletes the original message to which the ACK was responding.</span></span> <span data-ttu-id="0dc72-111">ただし、アダプターによって実行される検証は完全な検証ではないため、可能であれば、アダプターでは、確認に問題は検出されません。</span><span class="sxs-lookup"><span data-stu-id="0dc72-111">However, since the validation performed by the adapter is not a complete validation, it is possible that the adapter will not detect a problem with the ACK.</span></span> <span data-ttu-id="0dc72-112">たとえば、アダプターには、ACK が有効であり、パイプラインは、ACK が整形式でできなかったことを確認および ACK メッセージが中断され、元のメッセージを削除でしたを決定します。</span><span class="sxs-lookup"><span data-stu-id="0dc72-112">For instance, the adapter could determine that the ACK is valid, and delete the original message, whereas the pipeline would determine that the ACK was not well-formed, and suspend the ACK message.</span></span>  
  
## <a name="v2xml-acks-with-multiple-errors-will-fail-validation"></a><span data-ttu-id="0dc72-113">V2 です。複数のエラーのある XML Ack は検証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="0dc72-113">V2.XML ACKs with multiple errors will fail validation</span></span>  
 <span data-ttu-id="0dc72-114">着信 V2 の場合。XML メッセージには、1 つ以上のエラーが含まれています、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パーサーは、V2 を生成する可能性があります。エラー フィールドに 1 つ以上のエラーのための ACK を XML です。</span><span class="sxs-lookup"><span data-stu-id="0dc72-114">If an incoming V2.XML message contains more than one error, the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] parser may generate a V2.XML ACK with more than one error in the error field.</span></span> <span data-ttu-id="0dc72-115">このような V2 です。HL7 標準を指定して、パーサーが、V2 で 1 つだけのエラーを報告できるので、XML ACK では、検証は失敗します。XML ACK エラー フィールドです。</span><span class="sxs-lookup"><span data-stu-id="0dc72-115">Such a V2.XML ACK will fail validation, because the HL7 standard specifies that the parser can report only one error in a V2.XML ACK error field.</span></span>  
  
## <a name="mllp-performance-counters-do-not-count-acks"></a><span data-ttu-id="0dc72-116">パフォーマンス カウンターの MLLP Ack はカウントされません。</span><span class="sxs-lookup"><span data-stu-id="0dc72-116">MLLP performance counters do not count ACKs</span></span>  
 <span data-ttu-id="0dc72-117">1 つのメジャーの[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]MLLP パフォーマンス カウンターによって示される、パフォーマンスが MLLP アダプターによって処理されるメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="0dc72-117">One measure of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] performance is the number of messages processed by an MLLP adapter, as indicated by MLLP performance counters.</span></span> <span data-ttu-id="0dc72-118">この数は、受信または送信されたメッセージの数を計測します。</span><span class="sxs-lookup"><span data-stu-id="0dc72-118">This count measures the number of messages received or transmitted.</span></span> <span data-ttu-id="0dc72-119">ただし、カウントは Ack を受信または送信の数を測定していません。</span><span class="sxs-lookup"><span data-stu-id="0dc72-119">However, the count does not measure the number of ACKs either received or sent.</span></span>  
  
## <a name="nak-generated-by-two-way-mllp-adapter"></a><span data-ttu-id="0dc72-120">双方向の MLLP アダプターによって生成された NAK</span><span class="sxs-lookup"><span data-stu-id="0dc72-120">NAK generated by two-way MLLP adapter</span></span>  
 <span data-ttu-id="0dc72-121">双方向の MLLP アダプター、メッセージを中断するときに[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]NAK (否定受信確認) を生成し、メッセージ ボックス データベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="0dc72-121">When a two-way MLLP adapter suspends a message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates a NAK (negative acknowledgment) and places it in the MessageBox database.</span></span> <span data-ttu-id="0dc72-122">予期しない動作があります。</span><span class="sxs-lookup"><span data-stu-id="0dc72-122">This may be unexpected behavior.</span></span> <span data-ttu-id="0dc72-123">メッセージ ボックス データベースから、NAK を削除するか、別のメッセージにマップすることがあります。</span><span class="sxs-lookup"><span data-stu-id="0dc72-123">You may want to remove the NAK from the MessageBox database or map it into another message.</span></span>  
  
## <a name="data-type-of-an-ack-to-a-batch-message"></a><span data-ttu-id="0dc72-124">バッチ メッセージに ACK のデータ型</span><span class="sxs-lookup"><span data-stu-id="0dc72-124">Data type of an ACK to a batch message</span></span>  
 <span data-ttu-id="0dc72-125">バッチ メッセージへの応答で生成される ACK メッセージのバッチ メッセージの MSH10 フィールドのデータ型に基づいているのではなく、GUID、MSH10 フィールド (メッセージ コントロール ID) になります。</span><span class="sxs-lookup"><span data-stu-id="0dc72-125">In an ACK message generated in response to a batch message, the MSH10 field (message control ID) will be a GUID, rather than being based on the data type of the MSH10 field in the batch message.</span></span>  
  
## <a name="generated-acknowledgments-doc-type"></a><span data-ttu-id="0dc72-126">生成された受信確認ドキュメントの種類</span><span class="sxs-lookup"><span data-stu-id="0dc72-126">Generated acknowledgments DOC type</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="0dc72-127">ドキュメント型 http:// を使用して受信確認の生成[!INCLUDE[btsCoName](../../includes/btsconame-md.md)].com/HealthCare/HL7/2X#ACK_24_GLO_DEF または http://[!INCLUDE[btsCoName](../../includes/btsconame-md.md)].com/HealthCare/HL7/2X #ACK_25_GLO_DEF です。</span><span class="sxs-lookup"><span data-stu-id="0dc72-127"> generates acknowledgments using the DOC type http://[!INCLUDE[btsCoName](../../includes/btsconame-md.md)].com/HealthCare/HL7/2X#ACK_24_GLO_DEF or http://[!INCLUDE[btsCoName](../../includes/btsconame-md.md)].com/HealthCare/HL7/2X#ACK_25_GLO_DEF.</span></span> <span data-ttu-id="0dc72-128">送信ポート; 本文マップを適用する必要があります、送信先パーティでは、別の名前空間を使用する場合それ以外の場合、シリアル化エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0dc72-128">If your destination party uses a different namespace, you must apply a body map in the send port; otherwise, you may encounter serialization errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dc72-129">参照</span><span class="sxs-lookup"><span data-stu-id="0dc72-129">See Also</span></span>  
 [<span data-ttu-id="0dc72-130">既知の問題</span><span class="sxs-lookup"><span data-stu-id="0dc72-130">Known Issues</span></span>](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)