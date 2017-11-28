---
title: "バッチに関連する昇格させたプロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- promoted properties, batch related properties
- batching, promoted properties
ms.assetid: 00df1d8f-2f3f-4e3f-9983-37dcf3514fd8
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20fa421c6536d1d5182a11872206783392c65f69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="batch-related-promoted-properties"></a><span data-ttu-id="9f04d-102">バッチに関連する昇格させたプロパティ</span><span class="sxs-lookup"><span data-stu-id="9f04d-102">Batch-Related Promoted Properties</span></span>
<span data-ttu-id="9f04d-103">逆アセンブラーが特殊なメッセージをマーク SWIFT の逆アセンブラーを発行すると、メッセージ ボックス データベースに受信のバッチから発信されたメッセージ、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]バッチ メッセージに固有のプロパティを昇格します。</span><span class="sxs-lookup"><span data-stu-id="9f04d-103">When the SWIFT disassembler publishes a message that originated from an inbound batch to the MessageBox database, the disassembler marks the message with special [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] promoted properties that are specific to batch messages.</span></span> <span data-ttu-id="9f04d-104">これらのプロパティは、メッセージをどのような序数の位置から開始するバッチなど内にあったに A4SWIFT の部分が保持されると、バッチなどのコンテキスト情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="9f04d-104">These properties provide context information, such as which batch a message originated from, what ordinal position it was in within the batch, which parts A4SWIFT has preserved, and so forth.</span></span>  
  
 <span data-ttu-id="9f04d-105">A4SWIFT は、バッチ メッセージの次の昇格させたプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="9f04d-105">A4SWIFT sets the following promoted properties for batch messages:</span></span>  
  
-   <span data-ttu-id="9f04d-106">**A4SWIFT_BatchId**</span><span class="sxs-lookup"><span data-stu-id="9f04d-106">**A4SWIFT_BatchId**</span></span>  
  
-   <span data-ttu-id="9f04d-107">**A4SWIFT_IsMessageHeaderValued**</span><span class="sxs-lookup"><span data-stu-id="9f04d-107">**A4SWIFT_IsMessageHeaderValued**</span></span>  
  
-   <span data-ttu-id="9f04d-108">**A4SWIFT_IsMessageTrailerValued**</span><span class="sxs-lookup"><span data-stu-id="9f04d-108">**A4SWIFT_IsMessageTrailerValued**</span></span>  
  
-   <span data-ttu-id="9f04d-109">**A4SWIFT_NumberOfParts**</span><span class="sxs-lookup"><span data-stu-id="9f04d-109">**A4SWIFT_NumberOfParts**</span></span>  
  
-   <span data-ttu-id="9f04d-110">**A4SWIFT_PosInBatch**</span><span class="sxs-lookup"><span data-stu-id="9f04d-110">**A4SWIFT_PosInBatch**</span></span>  
  
 <span data-ttu-id="9f04d-111">これらおよびその他の昇格させたプロパティについては、次を参照してください。 [A4SWIFT_ * 昇格されたプロパティ](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="9f04d-111">For information about these and other promoted properties, see [A4SWIFT_* Promoted Properties](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md).</span></span>  
  
## <a name="failures-during-batch-processing"></a><span data-ttu-id="9f04d-112">バッチ処理中にエラー</span><span class="sxs-lookup"><span data-stu-id="9f04d-112">Failures During Batch Processing</span></span>  
 <span data-ttu-id="9f04d-113">バッチ処理中に SWIFT の逆アセンブラーがメッセージのエラー (解析または検証) を検出した場合 (**受信バッチ解除処理**'éý' **True**)、として、その動作がバッチ処理の構成によって異なります次に示します。</span><span class="sxs-lookup"><span data-stu-id="9f04d-113">When the SWIFT disassembler encounters message failures (parsing or validation) during batch processing (**Inbound Debatching** set to **True**), its behavior depends upon the batching configuration, as follows:</span></span>  
  
-   <span data-ttu-id="9f04d-114">バッチ処理の (**受信バッチ解除処理**に設定**True**) 断片化が有効になっていると (**断片化**に設定**True**) では、逆アセンブラー、MessageBox データベースに失敗したメッセージに個別に、公開されたメッセージの昇格させたプロパティに追加され、シリアル化に対応するエラー情報**元**XML です。</span><span class="sxs-lookup"><span data-stu-id="9f04d-114">For batch processing (**Inbound Debatching** set to **True**) with fragmentation enabled (**Fragmentation** set to **True**), the disassembler publishes failed messages to the MessageBox database individually, with corresponding error information appended in promoted properties and serialized **ErrorCollection** XML.</span></span> <span data-ttu-id="9f04d-115">逆アセンブラーには、(つまり、指定したスキーマのいずれかを使用して、逆アセンブラーを解析できませんデータ) のバッチの終了時に予期しないデータが検出されると、逆アセンブラー、バッチの最後のメッセージで予期しないデータが含まれています、解析失敗としてマーク.</span><span class="sxs-lookup"><span data-stu-id="9f04d-115">If the disassembler finds unexpected data at the end of the batch (that is, data that the disassembler cannot parse using any of the specified schemas), the disassembler includes this unexpected data in the last message in the batch and marks it as having failed parsing.</span></span> <span data-ttu-id="9f04d-116">逆アセンブラーでは、処理中に致命的なエラーが発生すると、逆アセンブラーは、致命的なエラーとすべてのデータを単一のメッセージとして、インターチェンジの終了の原因となったメッセージを公開します。</span><span class="sxs-lookup"><span data-stu-id="9f04d-116">If the disassembler encounters a fatal error during processing, then the disassembler publishes the message that caused the fatal error, plus all data to the end of the interchange, as a single message.</span></span> <span data-ttu-id="9f04d-117">逆アセンブラーは致命的なエラーの後にメッセージをフラグメント化されません。</span><span class="sxs-lookup"><span data-stu-id="9f04d-117">The disassembler does not fragment messages after the fatal error.</span></span>  
  
-   <span data-ttu-id="9f04d-118">バッチ処理の (**受信バッチ解除処理**に設定**True**) 断片化が無効になっていると (**断片化**'éý' **False**) では、逆アセンブラー、MessageBox データベースに失敗したメッセージに個別に、公開されたメッセージの昇格させたプロパティに追加され、シリアル化に対応するエラー情報**元**XML です。</span><span class="sxs-lookup"><span data-stu-id="9f04d-118">For batch processing (**Inbound Debatching** set to **True**) with fragmentation disabled (**Fragmentation** set to **False**), the disassembler publishes failed messages to the MessageBox database individually, with corresponding error information appended in promoted properties and serialized **ErrorCollection** XML.</span></span> <span data-ttu-id="9f04d-119">さらに、逆アセンブラーは、ネイティブ形式 (入力の正確なコピー) で、1 つのメッセージとしてメッセージ ボックス データベースにバッチ全体が (1 つまたは複数の失敗したメッセージを含む) を公開します。</span><span class="sxs-lookup"><span data-stu-id="9f04d-119">In addition, the disassembler publishes the entire batch (containing one or more failed messages) to the MessageBox database as a single message, in native form (exact copy of input).</span></span> <span data-ttu-id="9f04d-120">逆アセンブラーをマークして、 **A4SWIFT_Failed**プロパティ セットを昇格**True**を 1 つまたは複数の失敗したメッセージが、バッチに含まれていることを示します。</span><span class="sxs-lookup"><span data-stu-id="9f04d-120">The disassembler marks it with the **A4SWIFT_Failed** promoted property set **True** to indicate that the batch contains one or more failed messages.</span></span> <span data-ttu-id="9f04d-121">逆アセンブラーがアタッチもシリアル化**元**を断片化されていないバッチをバッチ内の個々 のメッセージで発生したすべてのエラーの連結を表す XML。</span><span class="sxs-lookup"><span data-stu-id="9f04d-121">The disassembler also attaches serialized **ErrorCollection** XML to the un-fragmented batch that represents the concatenation of all errors encountered in the individual messages within the batch.</span></span> <span data-ttu-id="9f04d-122">バッチ内の失敗したメッセージからメッセージごとのエラーの詳細を探索するには、(を関連付けることによって A4SWIFT_BatchId で)、メッセージ ボックス データベースから個々 の失敗したメッセージを取得し、抽出する必要があります、**元**XML各メッセージに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="9f04d-122">To discover the per-message error details from failed messages in the batch, you must retrieve the individual failed messages from the MessageBox database (by correlating on A4SWIFT_BatchId), and extract the **ErrorCollection** XML for each failed message.</span></span> <span data-ttu-id="9f04d-123">逆アセンブラーに失敗したバッチ全体に予期しないデータが含まれています (逆アセンブラーを公開するため、逆アセンブラーでは、(つまり、指定したスキーマのいずれかを使用して、逆アセンブラーを解析できませんデータ) のバッチの終了時に予期しないデータが検出されると、メッセージ ボックス データベースにもそのまま)、予期しないデータのための解析失敗としてマークを付けます。</span><span class="sxs-lookup"><span data-stu-id="9f04d-123">If the disassembler finds unexpected data at the end of the batch (that is, data that the disassembler cannot parse using any of the specified schemas), the disassembler includes the unexpected data with the entire failed batch (since the disassembler publishes it to the MessageBox database verbatim), and marks it as having failed parsing due to unexpected data.</span></span>  
  
-   <span data-ttu-id="9f04d-124">バッチ以外のシナリオ (**受信バッチ解除処理**'éý' **False**)、逆アセンブラー常にメッセージの公開失敗したメッセージ ボックス データベースに期待どおりに、個別にします。</span><span class="sxs-lookup"><span data-stu-id="9f04d-124">For non-batch scenarios (**Inbound Debatching** set to **False**), the disassembler always publishes failed messages to the MessageBox database individually, as expected.</span></span>  
  
 <span data-ttu-id="9f04d-125">昇格させたプロパティ A4SWIFT のエラーの詳細については、**元**オブジェクトを参照してください[メッセージ サブスクリプションの失敗の操作](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)です。</span><span class="sxs-lookup"><span data-stu-id="9f04d-125">For more information about A4SWIFT failure/error promoted properties and the **ErrorCollection** object, see [Working with Failed Message Subscriptions](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f04d-126">参照</span><span class="sxs-lookup"><span data-stu-id="9f04d-126">See Also</span></span>  
 <span data-ttu-id="9f04d-127">[受信バッチを逆アセンブル](../../adapters-and-accelerators/accelerator-swift/disassembling-inbound-batches.md) </span><span class="sxs-lookup"><span data-stu-id="9f04d-127">[Disassembling Inbound Batches](../../adapters-and-accelerators/accelerator-swift/disassembling-inbound-batches.md) </span></span>  
 [<span data-ttu-id="9f04d-128">SWIFT 逆アセンブラおよびアセンブラの操作</span><span class="sxs-lookup"><span data-stu-id="9f04d-128">Working with the SWIFT Disassembler and Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)