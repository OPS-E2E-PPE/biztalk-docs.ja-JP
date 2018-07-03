---
title: 受信確認の既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- known issues, acknowledgements
- acknowledgements, known issues
ms.assetid: cb45f80e-ba89-4b3f-a770-4b1cf9b8e220
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f585c9f0b147f50bd915bb757a3ed3c09a56ee8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966155"
---
# <a name="acknowledgments-known-issues"></a><span data-ttu-id="b6c9e-102">受信確認の既知の問題</span><span class="sxs-lookup"><span data-stu-id="b6c9e-102">Acknowledgments Known Issues</span></span>
<span data-ttu-id="b6c9e-103">このセクションには、受信確認 (ACK) エラーを回避するために役立つ有用な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b6c9e-103">This section contains useful information that may help you avoid acknowledgment (ACK) errors.</span></span>  
  
## <a name="hl7-v21-acknowledgment-message-accepted-even-if-it-contains-msa6-field"></a><span data-ttu-id="b6c9e-104">MSA6 フィールドが含まれている場合でも、HL7 V2.1 受信確認メッセージが受け入れられる</span><span class="sxs-lookup"><span data-stu-id="b6c9e-104">HL7 V2.1 acknowledgment message accepted even if it contains MSA6 field</span></span>  
 <span data-ttu-id="b6c9e-105">Microsoft [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) MSA6 フィールドを格納する場合でも、HL7 V2.1 受信確認メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b6c9e-105">Microsoft [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) will accept a HL7 V2.1 acknowledgment message even if contains the MSA6 field.</span></span>  
  
## <a name="msa-01-value-not-generated-for-commit-acknowledgment-errors"></a><span data-ttu-id="b6c9e-106">MSA-01 値がコミットの受信確認エラーは生成されません。</span><span class="sxs-lookup"><span data-stu-id="b6c9e-106">MSA-01 value not generated for commit acknowledgment errors</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="b6c9e-107"> コミットの受信確認エラー (CE)、MSA-01 の受信確認コードを生成しません。</span><span class="sxs-lookup"><span data-stu-id="b6c9e-107"> does not generate an MSA-01 acknowledgment code for commit acknowledgments errors (CE).</span></span>  
  
## <a name="two-way-mllp-adapter-might-not-detect-a-problem-with-an-ack"></a><span data-ttu-id="b6c9e-108">双方向の MLLP アダプターでは、ACK に問題が検出されない可能性も</span><span class="sxs-lookup"><span data-stu-id="b6c9e-108">Two-way MLLP adapter might not detect a problem with an ACK</span></span>  
 <span data-ttu-id="b6c9e-109">ときに[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ACK を受信アダプターを双方向の MLLP アダプター上には、有効性を確認で軽量の検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="b6c9e-109">When [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] receives an ACK on a two-way MLLP adapter, the adapter performs a lightweight validation on the ACK to determine its validity.</span></span> <span data-ttu-id="b6c9e-110">有効にすることが見つかると MSA1 フィールドが抽出され、その値に応じて、アダプター再試行、中断、または、ACK が応答していた元のメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="b6c9e-110">If it is found to be valid, the MSA1 field is extracted, and depending on its value, the adapter retries, suspends, or deletes the original message to which the ACK was responding.</span></span> <span data-ttu-id="b6c9e-111">ただし、アダプターによって実行される検証は完全な検証ではないためには、アダプターが ACK に問題を検出できません。</span><span class="sxs-lookup"><span data-stu-id="b6c9e-111">However, since the validation performed by the adapter is not a complete validation, it is possible that the adapter will not detect a problem with the ACK.</span></span> <span data-ttu-id="b6c9e-112">たとえば、アダプターでは、ACK が有効ですをパイプラインは、ACK が整形式でされなかったことを確認し、確認メッセージを中断する一方、元のメッセージを削除することを決定でした。</span><span class="sxs-lookup"><span data-stu-id="b6c9e-112">For instance, the adapter could determine that the ACK is valid, and delete the original message, whereas the pipeline would determine that the ACK was not well-formed, and suspend the ACK message.</span></span>  
  
## <a name="v2xml-acks-with-multiple-errors-will-fail-validation"></a><span data-ttu-id="b6c9e-113">V2。複数のエラーで XML Ack 検証に失敗します</span><span class="sxs-lookup"><span data-stu-id="b6c9e-113">V2.XML ACKs with multiple errors will fail validation</span></span>  
 <span data-ttu-id="b6c9e-114">受信の V2 の場合。XML メッセージには、1 つ以上のエラーが含まれています、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パーサーは、V2 生成可能性があります。Error フィールドに 1 つ以上のエラーで XML 確認します。</span><span class="sxs-lookup"><span data-stu-id="b6c9e-114">If an incoming V2.XML message contains more than one error, the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] parser may generate a V2.XML ACK with more than one error in the error field.</span></span> <span data-ttu-id="b6c9e-115">このような V2。XML の確認には、HL7 標準では、パーサーが、V2 での 1 つだけのエラーを報告できるを指定するために、検証は失敗します。XML の ACK エラー フィールドです。</span><span class="sxs-lookup"><span data-stu-id="b6c9e-115">Such a V2.XML ACK will fail validation, because the HL7 standard specifies that the parser can report only one error in a V2.XML ACK error field.</span></span>  
  
## <a name="mllp-performance-counters-do-not-count-acks"></a><span data-ttu-id="b6c9e-116">MLLP パフォーマンス カウンターには Ack はカウントされません。</span><span class="sxs-lookup"><span data-stu-id="b6c9e-116">MLLP performance counters do not count ACKs</span></span>  
 <span data-ttu-id="b6c9e-117">1 つのメジャーの[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]MLLP パフォーマンス カウンターが示すとおり、パフォーマンスが、MLLP アダプターによって処理されるメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="b6c9e-117">One measure of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] performance is the number of messages processed by an MLLP adapter, as indicated by MLLP performance counters.</span></span> <span data-ttu-id="b6c9e-118">この数は、受信または送信されるメッセージの数を測定します。</span><span class="sxs-lookup"><span data-stu-id="b6c9e-118">This count measures the number of messages received or transmitted.</span></span> <span data-ttu-id="b6c9e-119">ただし、カウントの Ack を受信または送信の数を計測しません。</span><span class="sxs-lookup"><span data-stu-id="b6c9e-119">However, the count does not measure the number of ACKs either received or sent.</span></span>  
  
## <a name="nak-generated-by-two-way-mllp-adapter"></a><span data-ttu-id="b6c9e-120">双方向の MLLP アダプターによって生成された NAK</span><span class="sxs-lookup"><span data-stu-id="b6c9e-120">NAK generated by two-way MLLP adapter</span></span>  
 <span data-ttu-id="b6c9e-121">双方向の MLLP アダプター、メッセージを中断するときに[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]NAK (否定受信確認) を生成し、メッセージ ボックス データベースに配置されます。</span><span class="sxs-lookup"><span data-stu-id="b6c9e-121">When a two-way MLLP adapter suspends a message, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generates a NAK (negative acknowledgment) and places it in the MessageBox database.</span></span> <span data-ttu-id="b6c9e-122">これにより、予期しない動作可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b6c9e-122">This may be unexpected behavior.</span></span> <span data-ttu-id="b6c9e-123">メッセージ ボックス データベースから、NAK を削除するか、別のメッセージにマップすることがあります。</span><span class="sxs-lookup"><span data-stu-id="b6c9e-123">You may want to remove the NAK from the MessageBox database or map it into another message.</span></span>  
  
## <a name="data-type-of-an-ack-to-a-batch-message"></a><span data-ttu-id="b6c9e-124">ACK をバッチ メッセージのデータ型</span><span class="sxs-lookup"><span data-stu-id="b6c9e-124">Data type of an ACK to a batch message</span></span>  
 <span data-ttu-id="b6c9e-125">ACK メッセージのバッチ メッセージへの応答で生成された MSH10 フィールド (メッセージのコントロール ID) は、バッチ メッセージに MSH10 フィールドのデータ型に基づくのではなく、GUID になります。</span><span class="sxs-lookup"><span data-stu-id="b6c9e-125">In an ACK message generated in response to a batch message, the MSH10 field (message control ID) will be a GUID, rather than being based on the data type of the MSH10 field in the batch message.</span></span>  
  
## <a name="generated-acknowledgments-doc-type"></a><span data-ttu-id="b6c9e-126">受信確認の生成されたドキュメントの種類</span><span class="sxs-lookup"><span data-stu-id="b6c9e-126">Generated acknowledgments DOC type</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="b6c9e-127"> ドキュメントの種類を使用して受信確認の生成http://Microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEFまたはhttp://Microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEFします。</span><span class="sxs-lookup"><span data-stu-id="b6c9e-127"> generates acknowledgments using the DOC type http://Microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF or http://Microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF.</span></span> <span data-ttu-id="b6c9e-128">送信先のパーティは、別の名前空間を使用している場合は、送信ポートで本文マップを適用する必要があります。それ以外の場合、シリアル化エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b6c9e-128">If your destination party uses a different namespace, you must apply a body map in the send port; otherwise, you may encounter serialization errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6c9e-129">参照</span><span class="sxs-lookup"><span data-stu-id="b6c9e-129">See Also</span></span>  
 [<span data-ttu-id="b6c9e-130">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b6c9e-130">Known Issues</span></span>](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)