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
ms.openlocfilehash: 211817d704faec2f936f33a04944360804b52e14
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282473"
---
# <a name="receive-pipeline"></a>[受信パイプライン]
このサンプルは、作業 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]受信パイプラインをアプリケーション用にカスタマイズできます。  
  
## <a name="demonstrates"></a>使用例  
 このサンプルは、BTARN 受信パイプライン (PipelineReceive.btp) を使用して、着信 RNIF メッセージを同等の XML メッセージに処理する方法を示します。 Pipelinereceive.btp は*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\rnpipelines にあります。 このサンプルには次のステージが含まれます。  
  
- ReceiveMessageNonRepudiate  
  
- RNMimeDecoder (MIME プリプロセッサ/デコーダー)  
  
- RNDAsm (XML 逆アセンブラ)  
  
- RNPartyRes (Party Resolution コンポーネント)  
  
- MessageUpdater  
  
  このパイプラインでは、このパイプラインでのメッセージ フローのコンポーネントに関する詳細については、次を参照してください。 [BTARN 受信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)します。  
  
## <a name="see-also"></a>参照  
 [パイプラインのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md)   
 [BTARN 受信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)