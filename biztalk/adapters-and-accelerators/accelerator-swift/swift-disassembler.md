---
title: "SWIFT 逆アセンブラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disassembler
- messages, receive pipelines
- receive pipelines, messages
ms.assetid: 42641550-0c88-4535-b5d5-b90acb30a6d3
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac0024abe862f777e7ee798991d97845ec5098a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="swift-disassembler"></a><span data-ttu-id="52e6f-102">SWIFT 逆アセンブラー</span><span class="sxs-lookup"><span data-stu-id="52e6f-102">SWIFT Disassembler</span></span>
<span data-ttu-id="52e6f-103">入力方向の受信パイプラインに送信されたすべてのメッセージの処理、 [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] (受信場所で受信した) アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="52e6f-103">An inbound receive pipeline processes all messages submitted to an [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] application (received at a receive location).</span></span>  
  
 <span data-ttu-id="52e6f-104">BizTalk の受信処理に関連する論理実行段階は受信パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="52e6f-104">Logical execution stages related to inbound processing make up the BizTalk receive pipelines.</span></span> <span data-ttu-id="52e6f-105">パイプライン コンポーネントは、サービスまたは、各ステージを実装します。</span><span class="sxs-lookup"><span data-stu-id="52e6f-105">A pipeline component services or implements each stage.</span></span> <span data-ttu-id="52e6f-106">具体的には、逆アセンブラーは、受信パイプラインの逆アセンブル ステージをサービスします。</span><span class="sxs-lookup"><span data-stu-id="52e6f-106">In particular, the disassembler services the disassemble stage in the receive pipeline.</span></span> <span data-ttu-id="52e6f-107">A4SWIFT は、SWIFT 固有のメッセージにカスタム逆アセンブラー コンポーネントで処理機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="52e6f-107">A4SWIFT provides SWIFT-specific message processing functionality in a custom disassembler component.</span></span>  
  
 <span data-ttu-id="52e6f-108">SWIFT の逆アセンブラー、カスタムのフラット ファイル逆アセンブラーは、SWIFT メッセージの受信と、バッチ処理の機能を提供し、次の機能を実行します。</span><span class="sxs-lookup"><span data-stu-id="52e6f-108">The SWIFT disassembler, a custom flat file disassembler, provides functionality for processing inbound SWIFT messages and batches, and performs the following functions:</span></span>  
  
-   <span data-ttu-id="52e6f-109">動的にメッセージの種類を検出し、ドキュメント スキーマの解決</span><span class="sxs-lookup"><span data-stu-id="52e6f-109">Dynamically discovers the message type and resolves the document schema</span></span>  
  
-   <span data-ttu-id="52e6f-110">XML に SWIFT のフラット ファイルを解析します。</span><span class="sxs-lookup"><span data-stu-id="52e6f-110">Parses SWIFT flat files into XML</span></span>  
  
-   <span data-ttu-id="52e6f-111">XML (スキーマ) 検証を実行するリーダーを検証する XML を呼び出します</span><span class="sxs-lookup"><span data-stu-id="52e6f-111">Invokes the XML validating reader to perform XML (schema) validation</span></span>  
  
-   <span data-ttu-id="52e6f-112">BRE の検証を実行するビジネス ルール エンジン (BRE) を呼び出します</span><span class="sxs-lookup"><span data-stu-id="52e6f-112">Invokes the Business Rule Engine (BRE) to perform BRE validation</span></span>  
  
-   <span data-ttu-id="52e6f-113">解析された XML メッセージを公開します、メッセージ ボックス データベースに昇格されたコンテキスト プロパティと XML のシリアル化されたエラー収集</span><span class="sxs-lookup"><span data-stu-id="52e6f-113">Publishes a parsed XML message to the MessageBox database with promoted context properties and serialized error collection XML</span></span>  
  
-   <span data-ttu-id="52e6f-114">処理し、受信バッチを逆アセンブル</span><span class="sxs-lookup"><span data-stu-id="52e6f-114">Processes and disassembles inbound batches</span></span>  
  
 <span data-ttu-id="52e6f-115">次の図は、逆アセンブラーの迅速なデータ フローです。</span><span class="sxs-lookup"><span data-stu-id="52e6f-115">The following figure shows the SWIFT disassembler data flow.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro2.gif "FSA_Intro2")  
  
 <span data-ttu-id="52e6f-116">SWIFT の逆アセンブラの詳細については、次を参照してください。 [SWIFT 逆アセンブラおよびアセンブラ扱う](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)です。</span><span class="sxs-lookup"><span data-stu-id="52e6f-116">For more information about the SWIFT disassembler, see [Working with the SWIFT Disassembler and Assembler](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52e6f-117">参照</span><span class="sxs-lookup"><span data-stu-id="52e6f-117">See Also</span></span>  
 [<span data-ttu-id="52e6f-118">BizTalk Accelerator for SWIFT のランタイム</span><span class="sxs-lookup"><span data-stu-id="52e6f-118">BizTalk Accelerator for SWIFT Runtime</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)