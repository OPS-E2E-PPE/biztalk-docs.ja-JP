---
title: SWIFT 逆アセンブラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disassembler
- messages, receive pipelines
- receive pipelines, messages
ms.assetid: 42641550-0c88-4535-b5d5-b90acb30a6d3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8baec8f140c0f7f0d3220b17c879a4868247bf6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376980"
---
# <a name="swift-disassembler"></a><span data-ttu-id="a799d-102">SWIFT 逆アセンブラー</span><span class="sxs-lookup"><span data-stu-id="a799d-102">SWIFT Disassembler</span></span>
<span data-ttu-id="a799d-103">パイプラインは、受信処理に送信されたすべてのメッセージ、[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]アプリケーション (受信場所で受信済み)。</span><span class="sxs-lookup"><span data-stu-id="a799d-103">An inbound receive pipeline processes all messages submitted to an [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] application (received at a receive location).</span></span>  
  
 <span data-ttu-id="a799d-104">で、BizTalk の受信処理に関連する論理実行段階では、パイプラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a799d-104">Logical execution stages related to inbound processing make up the BizTalk receive pipelines.</span></span> <span data-ttu-id="a799d-105">パイプライン コンポーネントは、サービスまたは各ステージを実装します。</span><span class="sxs-lookup"><span data-stu-id="a799d-105">A pipeline component services or implements each stage.</span></span> <span data-ttu-id="a799d-106">具体的には、逆アセンブラーは、受信パイプラインの逆アセンブル ステージをサービスします。</span><span class="sxs-lookup"><span data-stu-id="a799d-106">In particular, the disassembler services the disassemble stage in the receive pipeline.</span></span> <span data-ttu-id="a799d-107">A4SWIFT は、SWIFT 固有のメッセージにカスタム逆アセンブラー コンポーネントで処理機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="a799d-107">A4SWIFT provides SWIFT-specific message processing functionality in a custom disassembler component.</span></span>  
  
 <span data-ttu-id="a799d-108">SWIFT 逆アセンブラー、独自のフラット ファイル逆アセンブラーは、SWIFT メッセージの受信と、バッチ処理するための機能を提供し、次の関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="a799d-108">The SWIFT disassembler, a custom flat file disassembler, provides functionality for processing inbound SWIFT messages and batches, and performs the following functions:</span></span>  
  
- <span data-ttu-id="a799d-109">動的にメッセージの種類を検出し、ドキュメント スキーマの解決</span><span class="sxs-lookup"><span data-stu-id="a799d-109">Dynamically discovers the message type and resolves the document schema</span></span>  
  
- <span data-ttu-id="a799d-110">XML に SWIFT のフラット ファイルを解析します。</span><span class="sxs-lookup"><span data-stu-id="a799d-110">Parses SWIFT flat files into XML</span></span>  
  
- <span data-ttu-id="a799d-111">XML (スキーマ) 検証を実行するにはリーダーを検証する XML を呼び出します</span><span class="sxs-lookup"><span data-stu-id="a799d-111">Invokes the XML validating reader to perform XML (schema) validation</span></span>  
  
- <span data-ttu-id="a799d-112">BRE の検証を実行するビジネス ルール エンジン (BRE) を呼び出します</span><span class="sxs-lookup"><span data-stu-id="a799d-112">Invokes the Business Rule Engine (BRE) to perform BRE validation</span></span>  
  
- <span data-ttu-id="a799d-113">昇格されたコンテキスト プロパティと XML のシリアル化されたエラー コレクションを付けて MessageBox データベースに解析された XML メッセージを発行します。</span><span class="sxs-lookup"><span data-stu-id="a799d-113">Publishes a parsed XML message to the MessageBox database with promoted context properties and serialized error collection XML</span></span>  
  
- <span data-ttu-id="a799d-114">処理し、受信バッチを逆アセンブル</span><span class="sxs-lookup"><span data-stu-id="a799d-114">Processes and disassembles inbound batches</span></span>  
  
  <span data-ttu-id="a799d-115">次の図に、SWIFT 逆アセンブラーのデータ フローです。</span><span class="sxs-lookup"><span data-stu-id="a799d-115">The following figure shows the SWIFT disassembler data flow.</span></span>  
  
  <span data-ttu-id="a799d-116">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro2.gif "FSA_Intro2")</span><span class="sxs-lookup"><span data-stu-id="a799d-116">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro2.gif "FSA_Intro2")</span></span>  
  
  <span data-ttu-id="a799d-117">SWIFT 逆アセンブラーの詳細については、次を参照してください。 [SWIFT 逆アセンブラーとアセンブラー](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)します。</span><span class="sxs-lookup"><span data-stu-id="a799d-117">For more information about the SWIFT disassembler, see [Working with the SWIFT Disassembler and Assembler](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a799d-118">参照</span><span class="sxs-lookup"><span data-stu-id="a799d-118">See Also</span></span>  
 [<span data-ttu-id="a799d-119">BizTalk Accelerator for SWIFT ランタイム</span><span class="sxs-lookup"><span data-stu-id="a799d-119">BizTalk Accelerator for SWIFT Runtime</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)