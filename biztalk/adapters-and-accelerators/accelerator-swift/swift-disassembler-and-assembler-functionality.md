---
title: SWIFT 逆アセンブラーおよびアセンブラーの機能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disassembler, about disassembler
- assembler, about assembler
- assembler, functionality
- disassembler, functionality
ms.assetid: d4fc092e-586d-4360-921d-151af66b8bc1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f9a01480c5d308ffa882b2457e26548f4b5e43b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992859"
---
# <a name="swift-disassembler-and-assembler-functionality"></a><span data-ttu-id="24e6b-102">SWIFT 逆アセンブラーおよびアセンブラーの機能</span><span class="sxs-lookup"><span data-stu-id="24e6b-102">SWIFT Disassembler and Assembler Functionality</span></span>
<span data-ttu-id="24e6b-103">SWIFT 逆アセンブラーで呼び出されたときに、次のタスクを実行できる、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="24e6b-103">The SWIFT disassembler can perform the following tasks when invoked in a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] receive pipeline:</span></span>  
  
- <span data-ttu-id="24e6b-104">動的にメッセージの種類を検出し、ドキュメント スキーマを解決します。</span><span class="sxs-lookup"><span data-stu-id="24e6b-104">Dynamically discover the message type and resolve document schema.</span></span> <span data-ttu-id="24e6b-105">これにより、1 つの受信ポートとパイプラインを複数の SWIFT メッセージ型を処理します。</span><span class="sxs-lookup"><span data-stu-id="24e6b-105">This enables a single receive port and pipeline to handle multiple SWIFT message types.</span></span>  
  
- <span data-ttu-id="24e6b-106">SWIFT のフラット ファイルを XML に解析します。</span><span class="sxs-lookup"><span data-stu-id="24e6b-106">Parse a SWIFT flat file into XML.</span></span>  
  
- <span data-ttu-id="24e6b-107">データ型の妥当性、データの形式または長さの適合性チェックなどの XML (スキーマ) 検証を実行するにはリーダーを検証する XML を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="24e6b-107">Invoke the XML validating reader to perform XML (schema) validation, such as checking data type validity, data format, or length conformance.</span></span>  
  
- <span data-ttu-id="24e6b-108">SWIFT ネットワーク ルールに準拠のチェックや、スキーマが実装していないその他の複雑な検証を実行するなど、BRE の検証を実行するビジネス ルール エンジン (BRE) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="24e6b-108">Invoke the Business Rule Engine (BRE) to perform BRE validation, such as checking conformance to SWIFT network rules or performing other complex validation that the schema does not implement.</span></span>  
  
- <span data-ttu-id="24e6b-109">昇格されたコンテキスト プロパティとシリアル化されたエラーのコレクション (解析または検証中に発生したエラーに関する情報を提供する) XML メッセージ ボックス データベースに解析された XML メッセージを発行します。</span><span class="sxs-lookup"><span data-stu-id="24e6b-109">Publish a parsed XML message to the MessageBox database with promoted context properties and serialized error collection XML (providing information about any errors encountered during parsing or validation).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="24e6b-110">逆アセンブラーでは、解析中に致命的なエラーが発生すると、逆アセンブラーは XML ではなく、ネイティブのフラット ファイル形式でメッセージ ボックス データベースにメッセージを公開します。</span><span class="sxs-lookup"><span data-stu-id="24e6b-110">If the disassembler encounters fatal failures during parsing, the disassembler will publish the message to the MessageBox database in native flat file format rather than XML.</span></span>  
  
- <span data-ttu-id="24e6b-111">次のように受信のバッチを処理します。</span><span class="sxs-lookup"><span data-stu-id="24e6b-111">Process inbound batches, as follows:</span></span>  
  
  -   <span data-ttu-id="24e6b-112">解析し、バッチのエンベロープ (バッチ ヘッダー、トレーラーのバッチ) を保持します。</span><span class="sxs-lookup"><span data-stu-id="24e6b-112">Parse and preserve batch envelopes (batch header, batch trailer)</span></span>  
  
  -   <span data-ttu-id="24e6b-113">解析し、メッセージのエンベロープ (メッセージ ヘッダーは、メッセージのトレーラー) を保持します。</span><span class="sxs-lookup"><span data-stu-id="24e6b-113">Parse and preserve message envelopes (message header, message trailer)</span></span>  
  
  -   <span data-ttu-id="24e6b-114">解析し、バッチ内の SWIFT のメッセージを個別に検証</span><span class="sxs-lookup"><span data-stu-id="24e6b-114">Parse and validate SWIFT messages in the batch individually</span></span>  
  
  -   <span data-ttu-id="24e6b-115">SWIFT メッセージをメッセージ ボックス データベースに個別に発行します。</span><span class="sxs-lookup"><span data-stu-id="24e6b-115">Publish SWIFT messages to the MessageBox database individually</span></span>  
  
  -   <span data-ttu-id="24e6b-116">全体の受信のバッチをメッセージ ボックス データベースに 1 つのメッセージ (入力の正確なコピー) として発行します。</span><span class="sxs-lookup"><span data-stu-id="24e6b-116">Publish the entire inbound batch to the MessageBox database as a single message (exact copy of input)</span></span>  
  
  -   <span data-ttu-id="24e6b-117">並べ替えや同じバッチの送信元メッセージの関連付けのバッチに関連するコンテキスト プロパティを昇格させる</span><span class="sxs-lookup"><span data-stu-id="24e6b-117">Promote batch-related context properties for sorting or correlating messages originating from the same batch</span></span>  
  
  <span data-ttu-id="24e6b-118">SWIFT アセンブラーは、BizTalk 送信パイプラインで呼び出されたときに、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="24e6b-118">The SWIFT assembler can perform the following tasks when invoked in a BizTalk send pipeline:</span></span>  
  
- <span data-ttu-id="24e6b-119">動的にメッセージの種類を検出し、ドキュメント スキーマを解決します。</span><span class="sxs-lookup"><span data-stu-id="24e6b-119">Dynamically discover the message type and resolve the document schema.</span></span> <span data-ttu-id="24e6b-120">これにより、単一の送信ポートとパイプラインを複数の SWIFT メッセージの種類。</span><span class="sxs-lookup"><span data-stu-id="24e6b-120">This allows a single send port and pipeline to handle multiple SWIFT message types.</span></span>  
  
- <span data-ttu-id="24e6b-121">SWIFT のフラット ファイル解析された XML にシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="24e6b-121">Serialize parsed XML into a SWIFT flat file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24e6b-122">参照</span><span class="sxs-lookup"><span data-stu-id="24e6b-122">See Also</span></span>  
 [<span data-ttu-id="24e6b-123">SWIFT 逆アセンブラーおよびアセンブラーの操作</span><span class="sxs-lookup"><span data-stu-id="24e6b-123">Working with the SWIFT Disassembler and Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)