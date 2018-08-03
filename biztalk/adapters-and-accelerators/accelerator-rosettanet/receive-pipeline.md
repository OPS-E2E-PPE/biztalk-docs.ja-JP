---
title: 受信パイプライン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd8f03aa-f5c3-49e7-946b-c8c91fe3abc7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a2c1de940fab14aa370dc1358efe36fe702a9d2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990307"
---
# <a name="receive-pipeline"></a><span data-ttu-id="cdec9-102">[受信パイプライン]</span><span class="sxs-lookup"><span data-stu-id="cdec9-102">Receive Pipeline</span></span>
<span data-ttu-id="cdec9-103">このサンプルは、作業 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]受信パイプラインをアプリケーション用にカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="cdec9-103">This sample provides a working Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] receive pipeline that you can customize for your application.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="cdec9-104">使用例</span><span class="sxs-lookup"><span data-stu-id="cdec9-104">Demonstrates</span></span>  
 <span data-ttu-id="cdec9-105">このサンプルは、BTARN 受信パイプライン (PipelineReceive.btp) を使用して、着信 RNIF メッセージを同等の XML メッセージに処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cdec9-105">This sample demonstrates how to process an incoming RNIF message into the equivalent XML message using the BTARN receive pipeline (PipelineReceive.btp).</span></span> <span data-ttu-id="cdec9-106">Pipelinereceive.btp は*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\rnpipelines にあります。</span><span class="sxs-lookup"><span data-stu-id="cdec9-106">PipelineReceive.btp is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\RNPipelines.</span></span> <span data-ttu-id="cdec9-107">このサンプルには次のステージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cdec9-107">It includes the following stages:</span></span>  
  
- <span data-ttu-id="cdec9-108">ReceiveMessageNonRepudiate</span><span class="sxs-lookup"><span data-stu-id="cdec9-108">ReceiveMessageNonRepudiate</span></span>  
  
- <span data-ttu-id="cdec9-109">RNMimeDecoder (MIME プリプロセッサ/デコーダー)</span><span class="sxs-lookup"><span data-stu-id="cdec9-109">RNMimeDecoder (MIME Preprocessor/Decoder)</span></span>  
  
- <span data-ttu-id="cdec9-110">RNDAsm (XML 逆アセンブラ)</span><span class="sxs-lookup"><span data-stu-id="cdec9-110">RNDAsm (XML Disassembler)</span></span>  
  
- <span data-ttu-id="cdec9-111">RNPartyRes (Party Resolution コンポーネント)</span><span class="sxs-lookup"><span data-stu-id="cdec9-111">RNPartyRes (Party Resolution component)</span></span>  
  
- <span data-ttu-id="cdec9-112">MessageUpdater</span><span class="sxs-lookup"><span data-stu-id="cdec9-112">MessageUpdater</span></span>  
  
  <span data-ttu-id="cdec9-113">このパイプラインでは、このパイプラインでのメッセージ フローのコンポーネントに関する詳細については、次を参照してください。 [BTARN 受信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)します。</span><span class="sxs-lookup"><span data-stu-id="cdec9-113">For more information about the components of this pipeline, and the message flow in this pipeline, see [BTARN Receive Pipeline](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdec9-114">参照</span><span class="sxs-lookup"><span data-stu-id="cdec9-114">See Also</span></span>  
 <span data-ttu-id="cdec9-115">[パイプラインのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span><span class="sxs-lookup"><span data-stu-id="cdec9-115">[Pipeline Samples](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span></span>  
 [<span data-ttu-id="cdec9-116">BTARN 受信パイプライン</span><span class="sxs-lookup"><span data-stu-id="cdec9-116">BTARN Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)