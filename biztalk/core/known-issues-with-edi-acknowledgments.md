---
title: EDI 受信確認に関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a769a78e-8a49-4aa4-899e-e9f54fdd5f37
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9768bffc83589ae826a9110d994b19b83cdb3fbb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380829"
---
# <a name="known-issues-with-edi-acknowledgments"></a><span data-ttu-id="832f5-102">EDI 受信確認に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="832f5-102">Known Issues with EDI Acknowledgments</span></span>
<span data-ttu-id="832f5-103">このトピックでは、EDI 受信確認に関する既知の問題を説明します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="832f5-103">This topic describes known issues with EDI acknowledgments in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="ak102-in-a-997-acknowledgment-can-be-negative"></a><span data-ttu-id="832f5-104">997 受信確認の AK102 が負の値にできます。</span><span class="sxs-lookup"><span data-stu-id="832f5-104">AK102 in a 997 Acknowledgment Can Be Negative</span></span>  
 <span data-ttu-id="832f5-105">AK102 データ要素 (グループ制御番号) x12 997 受信確認は、負の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="832f5-105">The AK102 data element (group control number) in an X12 997 acknowledgment can be a negative value.</span></span> <span data-ttu-id="832f5-106">負の AK102 データ要素を使用して、確認がによって実行される検証を通過[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]負の値のグループ制御番号は意味がないにもかかわらず、します。</span><span class="sxs-lookup"><span data-stu-id="832f5-106">An acknowledgment with a negative AK102 data element will pass the validation performed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], even though a negative group control number is not meaningful.</span></span>  
  
## <a name="a-contrl-receipt-may-report-a-status-of-accepted-when-part-of-the-message-is-rejected"></a><span data-ttu-id="832f5-107">CONTRL 受信確認はステータスを報告が受け入れ、メッセージの一部が拒否された場合</span><span class="sxs-lookup"><span data-stu-id="832f5-107">A CONTRL Receipt May Report a Status of Accepted when Part of the Message Is Rejected</span></span>  
 <span data-ttu-id="832f5-108">CONTRL 受信確認 (EDIFACT 技術確認) では、受信した EDIFACT メッセージが重複している場合、またはエンベロープにエラー (文字セットの問題など) がある場合にのみ、[拒否] 状態がレポートされます。</span><span class="sxs-lookup"><span data-stu-id="832f5-108">A CONTRL receipt (EDIFACT technical acknowledgment) reports a status of “Rejected” only when the incoming EDIFACT message is a duplicate or there are errors in the envelope (for example, an issue with the character set).</span></span> <span data-ttu-id="832f5-109">EDIFACT では、X12 による TA1 受信確認の TA104 フィールドでのレポートとは、CONTRL 技術確認で「インターチェンジを受理 (ただしエラーが発生)」状態がレポートされません。</span><span class="sxs-lookup"><span data-stu-id="832f5-109">EDIFACT does not report a state of “Interchange accepted with errors” in the CONTRL technical acknowledgment, as X12 does in the TA104 field in a TA1 acknowledgment.</span></span> <span data-ttu-id="832f5-110">EDIFACT メッセージの一部が受理された場合、CONTRL 技術確認では [受理] がレポートされます。</span><span class="sxs-lookup"><span data-stu-id="832f5-110">If part of the EDIFACT message is accepted, the CONTRL technical acknowledgment will report “Accepted”.</span></span> <span data-ttu-id="832f5-111">シナリオによっては、メッセージの一部が拒否されても、CONTRL 受信確認では [受理] の状態がレポートされます。</span><span class="sxs-lookup"><span data-stu-id="832f5-111">In some scenarios, part of the message will be rejected, but the CONTRL acknowledgment will still report a status of “Accepted”.</span></span> <span data-ttu-id="832f5-112">このようなシナリオでは、UCI5 要素でエラーがレポートされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="832f5-112">In such scenarios, the UCI5 element may report the error.</span></span>  
  
## <a name="x12-acknowledgments-will-show-accepted-for-a-preserved-interchange-suspend-interchange-on-error-when-a-group-header-or-trailer-is-in-error"></a><span data-ttu-id="832f5-113">X12 では、エラーが受信確認は、保存済みインターチェンジ (エラーでインターチェンジを中断) ときに、グループ ヘッダーやトレーラーの受け入れを表示します。</span><span class="sxs-lookup"><span data-stu-id="832f5-113">X12 Acknowledgments Will Show Accepted for a Preserved Interchange (Suspend Interchange on Error) When a Group Header or Trailer is in Error</span></span>  
 <span data-ttu-id="832f5-114">受信バッチ処理オプション、x12 のメッセージは、グループ ヘッダーやトレーラ フィールドと「インターチェンジの保存-エラーでインターチェンジを中断」に設定が有効でない場合は、TA1 および 997 受信確認の両方で 受理の状態が報告されます。</span><span class="sxs-lookup"><span data-stu-id="832f5-114">If the inbound batch processing option for an X12 message is set to “Preserve Interchange – suspend interchange on error”, and a field in the group header or trailer is invalid, the status will be reported as Accepted in both TA1 and 997 acknowledgments.</span></span> <span data-ttu-id="832f5-115">EDI 状態レポートおよびトランザクション セットの詳細は受理 の状態も示します。</span><span class="sxs-lookup"><span data-stu-id="832f5-115">The EDI status report and transaction set details will also indicate a status of Accepted.</span></span> <span data-ttu-id="832f5-116">これは、インターチェンジが中断され、イベント ビューアーでエラーは、インターチェンジが中断されたことを示す場合でも発生します。</span><span class="sxs-lookup"><span data-stu-id="832f5-116">This occurs even though the interchange will be suspended, and an error in the Event Viewer will indicate that the interchange was suspended.</span></span>  
  
 <span data-ttu-id="832f5-117">TA1 受信確認の ISA ヘッダーおよび IEA トレーラー、正確性が GS ヘッダーおよび GE トレーラの正確さないことを確認することが目的のため、受理 のステータスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="832f5-117">The TA1 acknowledgment will show a status of Accepted because it is intended to verify the correctness of the ISA header and IEA trailer, but not the correctness of the GS header and GE trailer.</span></span> <span data-ttu-id="832f5-118">ただし、997 受信確認は、受理 の状態も表示されます。</span><span class="sxs-lookup"><span data-stu-id="832f5-118">However, the 997 acknowledgment will also show a status of Accepted.</span></span>  
  
## <a name="if-groups-in-an-interchange-have-the-same-name-the-status-report-will-show-twice-as-many-acknowledgments"></a><span data-ttu-id="832f5-119">インターチェンジ内のグループがある同じ名前、状態レポートに表示されます 2 倍の数の受信確認</span><span class="sxs-lookup"><span data-stu-id="832f5-119">If groups in an interchange have the same name, the status report will show twice as many acknowledgments</span></span>  
 <span data-ttu-id="832f5-120">BizTalk Server では、同じ名前を持つ複数のグループを含む EDI インターチェンジを処理する場合、EDI インターチェンジと関連する ACK の状態レポートで想定どおりに機能確認の 2 倍の数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="832f5-120">If BizTalk Server processes an EDI interchange with multiple groups that have the same name, the EDI Interchange and Correlated ACK status report will list twice as many functional acknowledgments as expected.</span></span> <span data-ttu-id="832f5-121">たとえば、インターチェンジ内の 2 つのグループの同じ名前である場合は、状態レポートは 2 つではなく、4 つの受信確認表示されます。</span><span class="sxs-lookup"><span data-stu-id="832f5-121">For example, if two groups in an interchange have the same name, the status report will list four acknowledgments, rather than two.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="832f5-122">参照</span><span class="sxs-lookup"><span data-stu-id="832f5-122">See Also</span></span>  
 <span data-ttu-id="832f5-123">[EDI の処理に関する既知の問題](../core/known-issues-with-edi-processing.md) </span><span class="sxs-lookup"><span data-stu-id="832f5-123">[Known Issues with EDI Processing](../core/known-issues-with-edi-processing.md) </span></span>  
 <span data-ttu-id="832f5-124">[EDI 受信確認を送信します。](../core/sending-an-edi-acknowledgment.md) </span><span class="sxs-lookup"><span data-stu-id="832f5-124">[Sending an EDI Acknowledgment](../core/sending-an-edi-acknowledgment.md) </span></span>  
 <span data-ttu-id="832f5-125">[受信確認の処理](../core/processing-a-received-acknowledgment.md) </span><span class="sxs-lookup"><span data-stu-id="832f5-125">[Processing a Received Acknowledgment](../core/processing-a-received-acknowledgment.md) </span></span>  
 [<span data-ttu-id="832f5-126">EDI 受信確認の構成</span><span class="sxs-lookup"><span data-stu-id="832f5-126">Configuring EDI Acknowledgments</span></span>](../core/configuring-edi-acknowledgments.md)