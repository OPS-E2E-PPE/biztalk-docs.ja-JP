---
title: SWIFT アセンブラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assembler
- send pipelines, messages
- messages, send pipelines
ms.assetid: 2a95c7d4-da10-4058-bc2c-3efc35958e14
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f2d405a901ae38c7a003fe578aa11d3841fc346
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376986"
---
# <a name="swift-assembler"></a><span data-ttu-id="c2e83-102">SWIFT アセンブラー</span><span class="sxs-lookup"><span data-stu-id="c2e83-102">SWIFT Assembler</span></span>
<span data-ttu-id="c2e83-103">送信の送信パイプラインによって送信されるすべてのメッセージの処理、[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]アプリケーション (送信ポートを通じて送信されます)。</span><span class="sxs-lookup"><span data-stu-id="c2e83-103">An outbound send pipeline processes all messages transmitted by an [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] application (sent through a send port).</span></span>  
  
 <span data-ttu-id="c2e83-104">送信処理に関連する論理実行段階では、BizTalk 送信パイプラインを構成します。</span><span class="sxs-lookup"><span data-stu-id="c2e83-104">Logical execution stages related to outbound processing make up the BizTalk send pipelines.</span></span> <span data-ttu-id="c2e83-105">パイプライン コンポーネントは、サービスまたは各ステージを実装します。</span><span class="sxs-lookup"><span data-stu-id="c2e83-105">A pipeline component services or implements each stage.</span></span> <span data-ttu-id="c2e83-106">具体的には、アセンブラーは、受信パイプラインのアセンブル ステージをサービスします。</span><span class="sxs-lookup"><span data-stu-id="c2e83-106">In particular, the assembler services the assemble stage in the receive pipeline.</span></span> <span data-ttu-id="c2e83-107">A4SWIFT は、SWIFT 固有送信メッセージの処理、カスタムのアセンブラー コンポーネントで機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="c2e83-107">A4SWIFT provides SWIFT-specific outbound message processing functionality in a custom assembler component.</span></span>  
  
 <span data-ttu-id="c2e83-108">SWIFT アセンブラー、独自のフラット ファイル アセンブラーは、送信の SWIFT メッセージを処理するための機能を提供し、次の関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2e83-108">The SWIFT assembler, a custom flat file assembler, provides functionality for processing outbound SWIFT messages, and performs the following functions:</span></span>  
  
- <span data-ttu-id="c2e83-109">動的にメッセージの種類を検出し、ドキュメント スキーマの解決</span><span class="sxs-lookup"><span data-stu-id="c2e83-109">Dynamically discovers the message type and resolves the document schema</span></span>  
  
- <span data-ttu-id="c2e83-110">SWIFT のフラット ファイル解析された XML にシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="c2e83-110">Serializes parsed XML into SWIFT flat files</span></span>  
  
  <span data-ttu-id="c2e83-111">次の図に、SWIFT アセンブラーのデータ フローです。</span><span class="sxs-lookup"><span data-stu-id="c2e83-111">The following figure shows the SWIFT assembler data flow.</span></span>  
  
  <span data-ttu-id="c2e83-112">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro3.gif "FSA_Intro3")</span><span class="sxs-lookup"><span data-stu-id="c2e83-112">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro3.gif "FSA_Intro3")</span></span>  
  
  <span data-ttu-id="c2e83-113">SWIFT アセンブラーの詳細については、次を参照してください。 [SWIFT 逆アセンブラーとアセンブラー](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)します。</span><span class="sxs-lookup"><span data-stu-id="c2e83-113">For more information about the SWIFT assembler, see [Working with the SWIFT Disassembler and Assembler](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2e83-114">参照</span><span class="sxs-lookup"><span data-stu-id="c2e83-114">See Also</span></span>  
 [<span data-ttu-id="c2e83-115">BizTalk Accelerator for SWIFT ランタイム</span><span class="sxs-lookup"><span data-stu-id="c2e83-115">BizTalk Accelerator for SWIFT Runtime</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)