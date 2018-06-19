---
title: MLLP アダプターの既知の問題 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MLLP adapters, known issues
- known issues, MLLP adapters
ms.assetid: 66af8fcc-981a-4a77-80b7-84824bfae608
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cbae1bf4bf04e2ecf4e643ad5107b9e0fd70f70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206058"
---
# <a name="mllp-adapter-known-issues"></a><span data-ttu-id="45365-102">MLLP アダプターの既知の問題</span><span class="sxs-lookup"><span data-stu-id="45365-102">MLLP Adapter Known Issues</span></span>
<span data-ttu-id="45365-103">このセクションには、最小限の下位層プロトコル (MLLP) アダプターのエラーを回避するために役立つ有用な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="45365-103">This section contains useful information that may help you avoid Minimal Lower Layer Protocol (MLLP) adapter errors.</span></span>  
  
## <a name="two-way-mllp-adapter-might-not-detect-a-problem-with-an-ack"></a><span data-ttu-id="45365-104">双方向の MLLP アダプターは、ACK に問題を検出できません可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="45365-104">Two-way MLLP adapter might not detect a problem with an ACK</span></span>  
 <span data-ttu-id="45365-105">ときに[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]) 確認 (ACK) の受信双方向の MLLP アダプターのアダプターがその有効性を決定する ACK の軽量な検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="45365-105">When [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]) receives an acknowledgment (ACK) on a two-way MLLP adapter, the adapter performs a lightweight validation on the ACK to determine its validity.</span></span> <span data-ttu-id="45365-106">見つかった場合は有効である、MSA1 フィールドを抽出すると、およびその値に応じて、アダプター再試行、中断、または、ACK が応答していた元のメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="45365-106">If it is found to be valid, the MSA1 field is extracted, and depending on its value, the adapter retries, suspends, or deletes the original message to which the ACK was responding.</span></span> <span data-ttu-id="45365-107">ただし、アダプターによって実行される検証は完全な検証ではないため、可能であれば、アダプターでは、確認に問題は検出されません。</span><span class="sxs-lookup"><span data-stu-id="45365-107">However, since the validation performed by the adapter is not a complete validation, it is possible that the adapter will not detect a problem with the ACK.</span></span> <span data-ttu-id="45365-108">たとえば、アダプターには、ACK が有効であり、パイプラインは、ACK が整形式でできなかったことを確認および ACK メッセージが中断され、元のメッセージを削除でしたを決定します。</span><span class="sxs-lookup"><span data-stu-id="45365-108">For instance, the adapter could determine that the ACK is valid, and delete the original message, whereas the pipeline would determine that the ACK was not well-formed, and suspend the ACK message.</span></span>  
  
## <a name="mllp-performance-counters-do-not-count-acks"></a><span data-ttu-id="45365-109">パフォーマンス カウンターの MLLP Ack はカウントされません。</span><span class="sxs-lookup"><span data-stu-id="45365-109">MLLP performance counters do not count ACKs</span></span>  
 <span data-ttu-id="45365-110">パフォーマンスの 1 つのメジャーは、MLLP パフォーマンス カウンターによって示される、MLLP アダプターによって処理されるメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="45365-110">One measure of performance is the number of messages processed by an MLLP adapter, as indicated by MLLP performance counters.</span></span> <span data-ttu-id="45365-111">この数は、受信または送信されたメッセージの数を計測します。</span><span class="sxs-lookup"><span data-stu-id="45365-111">This count measures the number of messages received or transmitted.</span></span> <span data-ttu-id="45365-112">ただし、カウントは Ack を受信または送信の数を測定していません。</span><span class="sxs-lookup"><span data-stu-id="45365-112">However, the count does not measure the number of ACKs either received or sent.</span></span>  
  
## <a name="mllp-adapter-connection-names-are-not-guaranteed-to-be-unique"></a><span data-ttu-id="45365-113">MLLP アダプターの接続名が一意である保証はありません。</span><span class="sxs-lookup"><span data-stu-id="45365-113">MLLP adapter connection names are not guaranteed to be unique</span></span>  
 [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]<span data-ttu-id="45365-114">MLLP アダプターのプロパティ ページに入力された接続名の一意性は保証されません。</span><span class="sxs-lookup"><span data-stu-id="45365-114"> does not guarantee the uniqueness of the connection name entered in the property pages of an MLLP adapter.</span></span> <span data-ttu-id="45365-115">この必須フィールドに名前が入力わかりやすい名前と関連する接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="45365-115">Ensure that descriptive and relevant connection names are entered in this required field.</span></span> <span data-ttu-id="45365-116">基幹業務アプリケーションを表す接続名を使用するは、接続の動作を把握しようとしているときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="45365-116">Using connection names that represent line-of-business applications can be useful when trying to understand the behavior of the connection.</span></span> <span data-ttu-id="45365-117">たとえば、PerfMon カウンターは、接続名を使用します。</span><span class="sxs-lookup"><span data-stu-id="45365-117">For example, PerfMon counters use the connection name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45365-118">一意性を確保は BTAHL7 受信場所または送信ポートの名前。</span><span class="sxs-lookup"><span data-stu-id="45365-118">BTAHL7 does ensure the uniqueness of receive locations or send port names.</span></span>  
  
## <a name="two-way-mllp-adapters-do-not-send-commit-acks-for-all-messages-in-a-batch"></a><span data-ttu-id="45365-119">双方向の MLLP アダプターはバッチ内のすべてのメッセージのコミットの確認を送信しません。</span><span class="sxs-lookup"><span data-stu-id="45365-119">Two-way MLLP adapters do not send Commit ACKs for all messages in a batch</span></span>  
 <span data-ttu-id="45365-120">コミットの確認の生成にバッチで各メッセージを構成すると、システムにバッチを送信する双方向の MLLP の受信アダプター、アダプターはバッチの最初のメッセージに対応するコミット ACK のみ送信します。</span><span class="sxs-lookup"><span data-stu-id="45365-120">When you configure each message in a batch to generate a Commit ACK, and the system sends the batch to a two-way MLLP receive adapter, the adapter will only send the Commit ACK corresponding to the first message in the batch.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45365-121">バッチをトランスポートには、一方向の MLLP アダプターを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="45365-121">It is recommended that you use a one-way MLLP adapter to transport batches.</span></span>  
  
## <a name="nak-generated-by-two-way-mllp-adapter"></a><span data-ttu-id="45365-122">双方向の MLLP アダプターによって生成された NAK</span><span class="sxs-lookup"><span data-stu-id="45365-122">NAK generated by two-way MLLP adapter</span></span>  
 <span data-ttu-id="45365-123">双方向の MLLP アダプターは、すべてのメッセージを中断、ときに MLLP アダプターは NAK (否定受信確認) を生成し、メッセージ ボックス データベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="45365-123">When a two-way MLLP adapter suspends any message, the MLLP adapter generates a NAK (negative acknowledgment) and places it in the MessageBox database.</span></span> <span data-ttu-id="45365-124">予期しない動作があります。</span><span class="sxs-lookup"><span data-stu-id="45365-124">This may be unexpected behavior.</span></span> <span data-ttu-id="45365-125">メッセージ ボックス データベースから、NAK を削除するか、別のメッセージにマップすることがあります。</span><span class="sxs-lookup"><span data-stu-id="45365-125">You may want to remove the NAK from the MessageBox database or map it into another message.</span></span>  
  
## <a name="two-way-mllp-adapter-only-supports-the-2x-message-format"></a><span data-ttu-id="45365-126">双方向の MLLP アダプターのみ 2.X メッセージ形式をサポートしています</span><span class="sxs-lookup"><span data-stu-id="45365-126">Two-way MLLP adapter only supports the 2.X message format</span></span>  
 <span data-ttu-id="45365-127">双方向の MLLP アダプターは、現在 2.X メッセージ形式のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="45365-127">The two-way MLLP adapter currently supports only the 2.X message format.</span></span>  
  
## <a name="two-way-mllp-adapter-does-not-support-static-acknowledgments"></a><span data-ttu-id="45365-128">双方向の MLLP アダプターが静的な受信確認をサポートしていません</span><span class="sxs-lookup"><span data-stu-id="45365-128">Two-way MLLP adapter does not support static acknowledgments</span></span>  
 <span data-ttu-id="45365-129">双方向の送信アダプタが静的な受信確認の処理をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="45365-129">The two-way send adapter does not support processing static acknowledgments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45365-130">参照</span><span class="sxs-lookup"><span data-stu-id="45365-130">See Also</span></span>  
 [<span data-ttu-id="45365-131">既知の問題</span><span class="sxs-lookup"><span data-stu-id="45365-131">Known Issues</span></span>](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)