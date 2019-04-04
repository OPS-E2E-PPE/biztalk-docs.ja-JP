---
title: バッチに関連する昇格させたプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- promoted properties, batch related properties
- batching, promoted properties
ms.assetid: 00df1d8f-2f3f-4e3f-9983-37dcf3514fd8
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a27d10fd4fc4224d54db166ecdf5f774192cb10a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000683"
---
# <a name="batch-related-promoted-properties"></a><span data-ttu-id="1d303-102">バッチに関連する昇格させたプロパティ</span><span class="sxs-lookup"><span data-stu-id="1d303-102">Batch-Related Promoted Properties</span></span>
<span data-ttu-id="1d303-103">逆アセンブラーが特別な Microsoft とメッセージをマーク SWIFT 逆アセンブラーがメッセージ ボックス データベースに受信のバッチから送信されたメッセージを発行したとき[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]バッチ メッセージに固有のプロパティを昇格します。</span><span class="sxs-lookup"><span data-stu-id="1d303-103">When the SWIFT disassembler publishes a message that originated from an inbound batch to the MessageBox database, the disassembler marks the message with special Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] promoted properties that are specific to batch messages.</span></span> <span data-ttu-id="1d303-104">これらのプロパティは、どのバッチがどのような序数の位置から、メッセージの送信元など内にあったに A4SWIFT の部分が保持すると、バッチなどのコンテキスト情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="1d303-104">These properties provide context information, such as which batch a message originated from, what ordinal position it was in within the batch, which parts A4SWIFT has preserved, and so forth.</span></span>  
  
 <span data-ttu-id="1d303-105">A4SWIFT は、バッチ メッセージの次の昇格させたプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="1d303-105">A4SWIFT sets the following promoted properties for batch messages:</span></span>  
  
- <span data-ttu-id="1d303-106">**A4SWIFT_BatchId**</span><span class="sxs-lookup"><span data-stu-id="1d303-106">**A4SWIFT_BatchId**</span></span>  
  
- <span data-ttu-id="1d303-107">**A4SWIFT_IsMessageHeaderValued**</span><span class="sxs-lookup"><span data-stu-id="1d303-107">**A4SWIFT_IsMessageHeaderValued**</span></span>  
  
- <span data-ttu-id="1d303-108">**A4SWIFT_IsMessageTrailerValued**</span><span class="sxs-lookup"><span data-stu-id="1d303-108">**A4SWIFT_IsMessageTrailerValued**</span></span>  
  
- <span data-ttu-id="1d303-109">**A4SWIFT_NumberOfParts**</span><span class="sxs-lookup"><span data-stu-id="1d303-109">**A4SWIFT_NumberOfParts**</span></span>  
  
- <span data-ttu-id="1d303-110">**A4SWIFT_PosInBatch**</span><span class="sxs-lookup"><span data-stu-id="1d303-110">**A4SWIFT_PosInBatch**</span></span>  
  
  <span data-ttu-id="1d303-111">これらおよびその他の昇格させたプロパティについては、[a4swift _ \* 昇格プロパティ](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d303-111">For information about these and other promoted properties, see [A4SWIFT_\* Promoted Properties](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md).</span></span>  
  
## <a name="failures-during-batch-processing"></a><span data-ttu-id="1d303-112">バッチ処理中にエラー</span><span class="sxs-lookup"><span data-stu-id="1d303-112">Failures During Batch Processing</span></span>  
 <span data-ttu-id="1d303-113">SWIFT 逆アセンブラーがメッセージのエラー (解析または検証) を検出した、バッチ処理中に場合 (**受信バッチ解除処理**設定**True**)、として、その動作がバッチ処理の構成によって異なります次に示します。</span><span class="sxs-lookup"><span data-stu-id="1d303-113">When the SWIFT disassembler encounters message failures (parsing or validation) during batch processing (**Inbound Debatching** set to **True**), its behavior depends upon the batching configuration, as follows:</span></span>  
  
- <span data-ttu-id="1d303-114">バッチ処理 (**受信バッチ解除処理**に設定**True**) を有効になっている断片化 (**断片化**に設定**True**)、逆アセンブラーは発行失敗したメッセージをメッセージ ボックス データベースに個別に、昇格させたプロパティに追加され、シリアル化に対応するエラー情報を**ErrorCollection** XML。</span><span class="sxs-lookup"><span data-stu-id="1d303-114">For batch processing (**Inbound Debatching** set to **True**) with fragmentation enabled (**Fragmentation** set to **True**), the disassembler publishes failed messages to the MessageBox database individually, with corresponding error information appended in promoted properties and serialized **ErrorCollection** XML.</span></span> <span data-ttu-id="1d303-115">逆アセンブラーでは、予期しないデータ (つまり、指定したスキーマのいずれかを使用して、逆アセンブラーを解析できませんデータ) のバッチの最後に検出されると、逆アセンブラーが、バッチの最後のメッセージで予期しないデータが含まれています、解析失敗としてマークを付けます.</span><span class="sxs-lookup"><span data-stu-id="1d303-115">If the disassembler finds unexpected data at the end of the batch (that is, data that the disassembler cannot parse using any of the specified schemas), the disassembler includes this unexpected data in the last message in the batch and marks it as having failed parsing.</span></span> <span data-ttu-id="1d303-116">逆アセンブラーでは、処理中に致命的なエラーが発生すると、逆アセンブラーは、致命的なエラーとすべてのデータを 1 つのメッセージとして、インターチェンジの終了の原因となったメッセージを発行します。</span><span class="sxs-lookup"><span data-stu-id="1d303-116">If the disassembler encounters a fatal error during processing, then the disassembler publishes the message that caused the fatal error, plus all data to the end of the interchange, as a single message.</span></span> <span data-ttu-id="1d303-117">逆アセンブラーには、致命的なエラーの発生後のメッセージをフラグメントされません。</span><span class="sxs-lookup"><span data-stu-id="1d303-117">The disassembler does not fragment messages after the fatal error.</span></span>  
  
- <span data-ttu-id="1d303-118">バッチ処理 (**受信バッチ解除処理**に設定**True**) を無効になっている断片化 (**断片化**に設定**False**)、逆アセンブラーは発行失敗したメッセージをメッセージ ボックス データベースに個別に、昇格させたプロパティに追加され、シリアル化に対応するエラー情報を**ErrorCollection** XML。</span><span class="sxs-lookup"><span data-stu-id="1d303-118">For batch processing (**Inbound Debatching** set to **True**) with fragmentation disabled (**Fragmentation** set to **False**), the disassembler publishes failed messages to the MessageBox database individually, with corresponding error information appended in promoted properties and serialized **ErrorCollection** XML.</span></span> <span data-ttu-id="1d303-119">さらに、逆アセンブラーは、ネイティブ形式 (入力の正確なコピー) で、1 つのメッセージとしてメッセージ ボックス データベースにバッチ全体が (1 つまたは複数の失敗したメッセージを含む) を発行します。</span><span class="sxs-lookup"><span data-stu-id="1d303-119">In addition, the disassembler publishes the entire batch (containing one or more failed messages) to the MessageBox database as a single message, in native form (exact copy of input).</span></span> <span data-ttu-id="1d303-120">逆アセンブラーでマークされます、 **A4SWIFT_Failed**プロパティ セットを昇格**True**を 1 つまたは複数の失敗したメッセージがバッチに含まれているかを示します。</span><span class="sxs-lookup"><span data-stu-id="1d303-120">The disassembler marks it with the **A4SWIFT_Failed** promoted property set **True** to indicate that the batch contains one or more failed messages.</span></span> <span data-ttu-id="1d303-121">逆アセンブラーもアタッチしますシリアル化**ErrorCollection** XML フラグメント化されていないバッチで、バッチ内の個々 のメッセージで発生したすべてのエラーの連結を表します。</span><span class="sxs-lookup"><span data-stu-id="1d303-121">The disassembler also attaches serialized **ErrorCollection** XML to the un-fragmented batch that represents the concatenation of all errors encountered in the individual messages within the batch.</span></span> <span data-ttu-id="1d303-122">バッチ内の失敗したメッセージからメッセージごとのエラーの詳細を検出するには、(を関連付けることによって A4SWIFT_BatchId 上)、個々 の失敗したメッセージをメッセージ ボックス データベースから取得し、抽出する必要があります、 **ErrorCollection** XML各メッセージに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="1d303-122">To discover the per-message error details from failed messages in the batch, you must retrieve the individual failed messages from the MessageBox database (by correlating on A4SWIFT_BatchId), and extract the **ErrorCollection** XML for each failed message.</span></span> <span data-ttu-id="1d303-123">逆アセンブラーに失敗したバッチ全体に予期しないデータが含まれています (逆アセンブラーを発行するため、逆アセンブラーでは、予期しないデータ (つまり、指定したスキーマのいずれかを使用して、逆アセンブラーを解析できませんデータ) のバッチの最後に検出されると、メッセージ ボックス データベースにもそのまま)、予期しないデータが原因の解析失敗としてマークを付けます。</span><span class="sxs-lookup"><span data-stu-id="1d303-123">If the disassembler finds unexpected data at the end of the batch (that is, data that the disassembler cannot parse using any of the specified schemas), the disassembler includes the unexpected data with the entire failed batch (since the disassembler publishes it to the MessageBox database verbatim), and marks it as having failed parsing due to unexpected data.</span></span>  
  
- <span data-ttu-id="1d303-124">非バッチ シナリオ (**受信バッチ解除処理**に設定**False**)、逆アセンブラー常にメッセージを発行失敗したメッセージ ボックス データベースに期待どおりに、個別にします。</span><span class="sxs-lookup"><span data-stu-id="1d303-124">For non-batch scenarios (**Inbound Debatching** set to **False**), the disassembler always publishes failed messages to the MessageBox database individually, as expected.</span></span>  
  
  <span data-ttu-id="1d303-125">A4SWIFT のエラーの詳細については、昇格させたプロパティと**ErrorCollection**オブジェクトを参照してください[メッセージ サブスクリプションの失敗の操作](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)します。</span><span class="sxs-lookup"><span data-stu-id="1d303-125">For more information about A4SWIFT failure/error promoted properties and the **ErrorCollection** object, see [Working with Failed Message Subscriptions](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d303-126">参照</span><span class="sxs-lookup"><span data-stu-id="1d303-126">See Also</span></span>  
 <span data-ttu-id="1d303-127">[受信バッチの逆アセンブル](../../adapters-and-accelerators/accelerator-swift/disassembling-inbound-batches.md) </span><span class="sxs-lookup"><span data-stu-id="1d303-127">[Disassembling Inbound Batches](../../adapters-and-accelerators/accelerator-swift/disassembling-inbound-batches.md) </span></span>  
 [<span data-ttu-id="1d303-128">SWIFT 逆アセンブラーおよびアセンブラーの操作</span><span class="sxs-lookup"><span data-stu-id="1d303-128">Working with the SWIFT Disassembler and Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)