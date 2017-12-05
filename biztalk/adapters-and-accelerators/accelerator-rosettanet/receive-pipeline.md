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
# <a name="receive-pipeline"></a>[受信パイプライン]
このサンプルは、独自のアプリケーション用にカスタマイズできる作業用の [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 受信パイプラインを提供します。  
  
## <a name="demonstrates"></a>使用例  
 このサンプルは、BTARN 受信パイプライン (PipelineReceive.btp) を使用して、着信 RNIF メッセージを同等の XML メッセージに処理する方法を示します。 PipelineReceive.btp にあります*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\rnpipelines です。 このサンプルには次のステージが含まれます。  
  
-   ReceiveMessageNonRepudiate  
  
-   RNMimeDecoder (MIME プリプロセッサ/デコーダー)  
  
-   RNDAsm (XML 逆アセンブラ)  
  
-   RNPartyRes (Party Resolution コンポーネント)  
  
-   MessageUpdater  
  
 このパイプラインおよびパイプラインにおけるメッセージ フローのコンポーネントに関する詳細については、次を参照してください。 [BTARN 受信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)です。  
  
## <a name="see-also"></a>参照  
 [パイプラインのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md)   
 [BTARN 受信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)