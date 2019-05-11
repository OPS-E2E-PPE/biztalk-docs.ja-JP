---
title: MLLP アダプターの既知の問題 |Microsoft Docs
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
ms.openlocfilehash: efa05809a785379c994e95dd3219a52a7772fb28
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303587"
---
# <a name="mllp-adapter-known-issues"></a><span data-ttu-id="54077-102">MLLP アダプターの既知の問題</span><span class="sxs-lookup"><span data-stu-id="54077-102">MLLP Adapter Known Issues</span></span>
<span data-ttu-id="54077-103">このセクションには、最小限の下位レイヤー プロトコル (MLLP) アダプターのエラーを回避するために役立つ有用な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="54077-103">This section contains useful information that may help you avoid Minimal Lower Layer Protocol (MLLP) adapter errors.</span></span>  
  
## <a name="two-way-mllp-adapter-might-not-detect-a-problem-with-an-ack"></a><span data-ttu-id="54077-104">双方向の MLLP アダプターでは、ACK に問題が検出されない可能性も</span><span class="sxs-lookup"><span data-stu-id="54077-104">Two-way MLLP adapter might not detect a problem with an ACK</span></span>  
 <span data-ttu-id="54077-105">ときに Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]) 受信確認 (ACK) の受信アダプターを双方向の MLLP アダプター上には、有効性を確認で軽量の検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="54077-105">When Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]) receives an acknowledgment (ACK) on a two-way MLLP adapter, the adapter performs a lightweight validation on the ACK to determine its validity.</span></span> <span data-ttu-id="54077-106">有効にすることが見つかると MSA1 フィールドが抽出され、その値に応じて、アダプター再試行、中断、または、ACK が応答していた元のメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="54077-106">If it is found to be valid, the MSA1 field is extracted, and depending on its value, the adapter retries, suspends, or deletes the original message to which the ACK was responding.</span></span> <span data-ttu-id="54077-107">ただし、アダプターによって実行される検証は完全な検証ではないためには、アダプターが ACK に問題を検出できません。</span><span class="sxs-lookup"><span data-stu-id="54077-107">However, since the validation performed by the adapter is not a complete validation, it is possible that the adapter will not detect a problem with the ACK.</span></span> <span data-ttu-id="54077-108">たとえば、アダプターでは、ACK が有効ですをパイプラインは、ACK が整形式でされなかったことを確認し、確認メッセージを中断する一方、元のメッセージを削除することを決定でした。</span><span class="sxs-lookup"><span data-stu-id="54077-108">For instance, the adapter could determine that the ACK is valid, and delete the original message, whereas the pipeline would determine that the ACK was not well-formed, and suspend the ACK message.</span></span>  
  
## <a name="mllp-performance-counters-do-not-count-acks"></a><span data-ttu-id="54077-109">MLLP パフォーマンス カウンターには Ack はカウントされません。</span><span class="sxs-lookup"><span data-stu-id="54077-109">MLLP performance counters do not count ACKs</span></span>  
 <span data-ttu-id="54077-110">パフォーマンスの 1 つのメジャーは、MLLP パフォーマンス カウンターが示すとおり、MLLP アダプターによって処理されるメッセージの数です。</span><span class="sxs-lookup"><span data-stu-id="54077-110">One measure of performance is the number of messages processed by an MLLP adapter, as indicated by MLLP performance counters.</span></span> <span data-ttu-id="54077-111">この数は、受信または送信されるメッセージの数を測定します。</span><span class="sxs-lookup"><span data-stu-id="54077-111">This count measures the number of messages received or transmitted.</span></span> <span data-ttu-id="54077-112">ただし、カウントの Ack を受信または送信の数を計測しません。</span><span class="sxs-lookup"><span data-stu-id="54077-112">However, the count does not measure the number of ACKs either received or sent.</span></span>  
  
## <a name="mllp-adapter-connection-names-are-not-guaranteed-to-be-unique"></a><span data-ttu-id="54077-113">MLLP アダプターの接続名は一意であることは保証されません。</span><span class="sxs-lookup"><span data-stu-id="54077-113">MLLP adapter connection names are not guaranteed to be unique</span></span>  
 [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] <span data-ttu-id="54077-114">MLLP アダプターのプロパティ ページに入力された接続名の一意性は保証されません。</span><span class="sxs-lookup"><span data-stu-id="54077-114">does not guarantee the uniqueness of the connection name entered in the property pages of an MLLP adapter.</span></span> <span data-ttu-id="54077-115">この必須のフィールド名を入力したそのわかりやすい名前と関連する接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="54077-115">Ensure that descriptive and relevant connection names are entered in this required field.</span></span> <span data-ttu-id="54077-116">基幹業務アプリケーションを表す接続名を使用するは、接続の動作を理解しようとするときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="54077-116">Using connection names that represent line-of-business applications can be useful when trying to understand the behavior of the connection.</span></span> <span data-ttu-id="54077-117">たとえば、PerfMon カウンターは、接続名を使用します。</span><span class="sxs-lookup"><span data-stu-id="54077-117">For example, PerfMon counters use the connection name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54077-118">一意性を確保は BTAHL7 受信場所または送信ポートの名前。</span><span class="sxs-lookup"><span data-stu-id="54077-118">BTAHL7 does ensure the uniqueness of receive locations or send port names.</span></span>  
  
## <a name="two-way-mllp-adapters-do-not-send-commit-acks-for-all-messages-in-a-batch"></a><span data-ttu-id="54077-119">双方向の MLLP アダプターはすべてのメッセージ バッチのコミットの確認を送信しません。</span><span class="sxs-lookup"><span data-stu-id="54077-119">Two-way MLLP adapters do not send Commit ACKs for all messages in a batch</span></span>  
 <span data-ttu-id="54077-120">コミットの確認を生成するバッチ内の各メッセージを構成すると、システムにバッチを送信する双方向の MLLP 受信アダプター、アダプターはバッチの最初のメッセージに対応するコミットの確認のみを送信します。</span><span class="sxs-lookup"><span data-stu-id="54077-120">When you configure each message in a batch to generate a Commit ACK, and the system sends the batch to a two-way MLLP receive adapter, the adapter will only send the Commit ACK corresponding to the first message in the batch.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54077-121">バッチをトランスポートする一方向の MLLP アダプターを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="54077-121">It is recommended that you use a one-way MLLP adapter to transport batches.</span></span>  
  
## <a name="nak-generated-by-two-way-mllp-adapter"></a><span data-ttu-id="54077-122">双方向の MLLP アダプターによって生成された NAK</span><span class="sxs-lookup"><span data-stu-id="54077-122">NAK generated by two-way MLLP adapter</span></span>  
 <span data-ttu-id="54077-123">双方向の MLLP アダプターでは、すべてのメッセージを中断、MLLP アダプターは NAK (否定受信確認応答) が生成され、メッセージ ボックス データベースに配置します。</span><span class="sxs-lookup"><span data-stu-id="54077-123">When a two-way MLLP adapter suspends any message, the MLLP adapter generates a NAK (negative acknowledgment) and places it in the MessageBox database.</span></span> <span data-ttu-id="54077-124">これにより、予期しない動作可能性があります。</span><span class="sxs-lookup"><span data-stu-id="54077-124">This may be unexpected behavior.</span></span> <span data-ttu-id="54077-125">メッセージ ボックス データベースから、NAK を削除するか、別のメッセージにマップすることがあります。</span><span class="sxs-lookup"><span data-stu-id="54077-125">You may want to remove the NAK from the MessageBox database or map it into another message.</span></span>  
  
## <a name="two-way-mllp-adapter-only-supports-the-2x-message-format"></a><span data-ttu-id="54077-126">双方向の MLLP アダプターは、2.X のメッセージ形式のみサポートしています。</span><span class="sxs-lookup"><span data-stu-id="54077-126">Two-way MLLP adapter only supports the 2.X message format</span></span>  
 <span data-ttu-id="54077-127">双方向の MLLP アダプターでは、2.X のメッセージ形式のみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="54077-127">The two-way MLLP adapter currently supports only the 2.X message format.</span></span>  
  
## <a name="two-way-mllp-adapter-does-not-support-static-acknowledgments"></a><span data-ttu-id="54077-128">双方向の MLLP アダプターが静的受信確認をサポートしていません</span><span class="sxs-lookup"><span data-stu-id="54077-128">Two-way MLLP adapter does not support static acknowledgments</span></span>  
 <span data-ttu-id="54077-129">双方向の送信アダプタが静的受信確認の処理をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="54077-129">The two-way send adapter does not support processing static acknowledgments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54077-130">参照</span><span class="sxs-lookup"><span data-stu-id="54077-130">See Also</span></span>  
 [<span data-ttu-id="54077-131">既知の問題</span><span class="sxs-lookup"><span data-stu-id="54077-131">Known Issues</span></span>](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)