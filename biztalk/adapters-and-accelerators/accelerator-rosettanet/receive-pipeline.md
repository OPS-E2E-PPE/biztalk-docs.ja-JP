---
title: "受信パイプライン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd8f03aa-f5c3-49e7-946b-c8c91fe3abc7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d5374c46411e0c4924585647736bfde7f1e4428
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="receive-pipeline"></a><span data-ttu-id="b8f46-102">[受信パイプライン]</span><span class="sxs-lookup"><span data-stu-id="b8f46-102">Receive Pipeline</span></span>
<span data-ttu-id="b8f46-103">このサンプルは、独自のアプリケーション用にカスタマイズできる作業用の [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 受信パイプラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="b8f46-103">This sample provides a working [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] receive pipeline that you can customize for your application.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="b8f46-104">使用例</span><span class="sxs-lookup"><span data-stu-id="b8f46-104">Demonstrates</span></span>  
 <span data-ttu-id="b8f46-105">このサンプルは、BTARN 受信パイプライン (PipelineReceive.btp) を使用して、着信 RNIF メッセージを同等の XML メッセージに処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b8f46-105">This sample demonstrates how to process an incoming RNIF message into the equivalent XML message using the BTARN receive pipeline (PipelineReceive.btp).</span></span> <span data-ttu-id="b8f46-106">PipelineReceive.btp にあります*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\rnpipelines です。</span><span class="sxs-lookup"><span data-stu-id="b8f46-106">PipelineReceive.btp is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\RNPipelines.</span></span> <span data-ttu-id="b8f46-107">このサンプルには次のステージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b8f46-107">It includes the following stages:</span></span>  
  
-   <span data-ttu-id="b8f46-108">ReceiveMessageNonRepudiate</span><span class="sxs-lookup"><span data-stu-id="b8f46-108">ReceiveMessageNonRepudiate</span></span>  
  
-   <span data-ttu-id="b8f46-109">RNMimeDecoder (MIME プリプロセッサ/デコーダー)</span><span class="sxs-lookup"><span data-stu-id="b8f46-109">RNMimeDecoder (MIME Preprocessor/Decoder)</span></span>  
  
-   <span data-ttu-id="b8f46-110">RNDAsm (XML 逆アセンブラ)</span><span class="sxs-lookup"><span data-stu-id="b8f46-110">RNDAsm (XML Disassembler)</span></span>  
  
-   <span data-ttu-id="b8f46-111">RNPartyRes (Party Resolution コンポーネント)</span><span class="sxs-lookup"><span data-stu-id="b8f46-111">RNPartyRes (Party Resolution component)</span></span>  
  
-   <span data-ttu-id="b8f46-112">MessageUpdater</span><span class="sxs-lookup"><span data-stu-id="b8f46-112">MessageUpdater</span></span>  
  
 <span data-ttu-id="b8f46-113">このパイプラインおよびパイプラインにおけるメッセージ フローのコンポーネントに関する詳細については、次を参照してください。 [BTARN 受信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)です。</span><span class="sxs-lookup"><span data-stu-id="b8f46-113">For more information about the components of this pipeline, and the message flow in this pipeline, see [BTARN Receive Pipeline](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8f46-114">参照</span><span class="sxs-lookup"><span data-stu-id="b8f46-114">See Also</span></span>  
 <span data-ttu-id="b8f46-115">[パイプラインのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span><span class="sxs-lookup"><span data-stu-id="b8f46-115">[Pipeline Samples](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span></span>  
 [<span data-ttu-id="b8f46-116">BTARN 受信パイプライン</span><span class="sxs-lookup"><span data-stu-id="b8f46-116">BTARN Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)