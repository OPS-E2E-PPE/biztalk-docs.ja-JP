---
title: "SWIFT 逆アセンブラーおよびアセンブラー機能 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disassembler, about disassembler
- assembler, about assembler
- assembler, functionality
- disassembler, functionality
ms.assetid: d4fc092e-586d-4360-921d-151af66b8bc1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0109979fbb9bf61fc0e1be833061b2a15b470690
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="swift-disassembler-and-assembler-functionality"></a><span data-ttu-id="11e9e-102">SWIFT 逆アセンブラーおよびアセンブラー機能</span><span class="sxs-lookup"><span data-stu-id="11e9e-102">SWIFT Disassembler and Assembler Functionality</span></span>
<span data-ttu-id="11e9e-103">SWIFT の逆アセンブラーで呼び出されたときに、次のタスクを実行できる、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="11e9e-103">The SWIFT disassembler can perform the following tasks when invoked in a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] receive pipeline:</span></span>  
  
-   <span data-ttu-id="11e9e-104">動的にメッセージの種類を検出し、ドキュメント スキーマを解決します。</span><span class="sxs-lookup"><span data-stu-id="11e9e-104">Dynamically discover the message type and resolve document schema.</span></span> <span data-ttu-id="11e9e-105">これにより、単一の受信ポートとパイプラインを複数の SWIFT メッセージ型を処理します。</span><span class="sxs-lookup"><span data-stu-id="11e9e-105">This enables a single receive port and pipeline to handle multiple SWIFT message types.</span></span>  
  
-   <span data-ttu-id="11e9e-106">XML に SWIFT のフラット ファイルを解析します。</span><span class="sxs-lookup"><span data-stu-id="11e9e-106">Parse a SWIFT flat file into XML.</span></span>  
  
-   <span data-ttu-id="11e9e-107">データ型の有効性、データ形式または長さの準拠の確認などの XML (スキーマ) 検証を実行するリーダーを検証する XML を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="11e9e-107">Invoke the XML validating reader to perform XML (schema) validation, such as checking data type validity, data format, or length conformance.</span></span>  
  
-   <span data-ttu-id="11e9e-108">SWIFT ネットワーク ルールへの準拠の確認や、スキーマが実装されていないその他の複雑な検証を実行するなど、BRE の検証を実行するビジネス ルール エンジン (BRE) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="11e9e-108">Invoke the Business Rule Engine (BRE) to perform BRE validation, such as checking conformance to SWIFT network rules or performing other complex validation that the schema does not implement.</span></span>  
  
-   <span data-ttu-id="11e9e-109">メッセージ ボックス データベースに昇格されたコンテキスト プロパティとシリアル化されたエラーのコレクション (解析または検証中に発生したエラーに関する情報を提供する) を XML に解析された XML メッセージを発行します。</span><span class="sxs-lookup"><span data-stu-id="11e9e-109">Publish a parsed XML message to the MessageBox database with promoted context properties and serialized error collection XML (providing information about any errors encountered during parsing or validation).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="11e9e-110">逆アセンブラーでは、解析中に致命的なエラーが発生すると、逆アセンブラーは XML ではなく、ネイティブのフラット ファイル形式でメッセージ ボックス データベースにメッセージを公開します。</span><span class="sxs-lookup"><span data-stu-id="11e9e-110">If the disassembler encounters fatal failures during parsing, the disassembler will publish the message to the MessageBox database in native flat file format rather than XML.</span></span>  
  
-   <span data-ttu-id="11e9e-111">次のように受信のバッチを処理します。</span><span class="sxs-lookup"><span data-stu-id="11e9e-111">Process inbound batches, as follows:</span></span>  
  
    -   <span data-ttu-id="11e9e-112">解析し、バッチのエンベロープ (バッチ ヘッダー、トレーラーのバッチ) を保持します。</span><span class="sxs-lookup"><span data-stu-id="11e9e-112">Parse and preserve batch envelopes (batch header, batch trailer)</span></span>  
  
    -   <span data-ttu-id="11e9e-113">解析し、メッセージのエンベロープ (メッセージ ヘッダー、メッセージ トレーラー) を保持します。</span><span class="sxs-lookup"><span data-stu-id="11e9e-113">Parse and preserve message envelopes (message header, message trailer)</span></span>  
  
    -   <span data-ttu-id="11e9e-114">解析し、個別に SWIFT メッセージのバッチでの検証</span><span class="sxs-lookup"><span data-stu-id="11e9e-114">Parse and validate SWIFT messages in the batch individually</span></span>  
  
    -   <span data-ttu-id="11e9e-115">個別に SWIFT メッセージをメッセージ ボックス データベースに発行します。</span><span class="sxs-lookup"><span data-stu-id="11e9e-115">Publish SWIFT messages to the MessageBox database individually</span></span>  
  
    -   <span data-ttu-id="11e9e-116">全体の受信のバッチをメッセージ ボックス データベースに 1 つのメッセージ (入力の正確なコピー) として公開します。</span><span class="sxs-lookup"><span data-stu-id="11e9e-116">Publish the entire inbound batch to the MessageBox database as a single message (exact copy of input)</span></span>  
  
    -   <span data-ttu-id="11e9e-117">並べ替えや同じバッチから送信されたメッセージの関連付けのバッチに関連するコンテキスト プロパティを昇格させる</span><span class="sxs-lookup"><span data-stu-id="11e9e-117">Promote batch-related context properties for sorting or correlating messages originating from the same batch</span></span>  
  
 <span data-ttu-id="11e9e-118">SWIFT のアセンブラーは、BizTalk 送信パイプラインで呼び出されたときに、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="11e9e-118">The SWIFT assembler can perform the following tasks when invoked in a BizTalk send pipeline:</span></span>  
  
-   <span data-ttu-id="11e9e-119">動的にメッセージの種類を検出し、ドキュメント スキーマを解決します。</span><span class="sxs-lookup"><span data-stu-id="11e9e-119">Dynamically discover the message type and resolve the document schema.</span></span> <span data-ttu-id="11e9e-120">これにより、単一の送信ポートとパイプラインを複数 SWIFT メッセージの種類。</span><span class="sxs-lookup"><span data-stu-id="11e9e-120">This allows a single send port and pipeline to handle multiple SWIFT message types.</span></span>  
  
-   <span data-ttu-id="11e9e-121">SWIFT のフラット ファイル解析された XML にシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="11e9e-121">Serialize parsed XML into a SWIFT flat file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11e9e-122">参照</span><span class="sxs-lookup"><span data-stu-id="11e9e-122">See Also</span></span>  
 [<span data-ttu-id="11e9e-123">SWIFT 逆アセンブラおよびアセンブラの操作</span><span class="sxs-lookup"><span data-stu-id="11e9e-123">Working with the SWIFT Disassembler and Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)