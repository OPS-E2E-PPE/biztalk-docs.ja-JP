---
title: バッチ メッセージの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, batching
- batching, examples
- batching, batch types
ms.assetid: 264f91b5-3e33-4b87-9da3-866eaa464b0f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75cde12720ac67d74396c22282bddaf53e015960
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972371"
---
# <a name="batch-message-processing"></a>バッチ メッセージの処理
Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 処理する 3 種類の HL7 2.X の batch シナリオ。  
  
- 断片化した受信バッチのシナリオです。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 別の出力メッセージには、これらのバッチを解析します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 断片化したバッチでは、各メッセージの受信確認 (Ack) を送信します。  
  
- バッチ処理/バッチ アウト シナリオ。 これらは、バインドでバッチを[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]を断片化しますが、渡され、そのままのバッチとして送信します。 場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチでは、ACK ACK の送信には、バージョン ID が含まれています。  
  
- バッチの作成シナリオです。 このシナリオで[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]結合は、入力メッセージを出力バッチに分割します。  
  
  2 つの方法のいずれかでバッチの書式を設定できます。  
  
- でファイルのヘッダーとトレーラー (FHS/FTS) バッチ ヘッダーとトレーラー (BHS/BTS)。  
  
- でないファイルまたはバッチ ヘッダー/トレーラです。  
  
## <a name="see-also"></a>参照  
 [メッセージのバッチ処理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)   
 [バッチ処理のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)   
 [パート 1: 断片化した受信バッチのシナリオ](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)   
 [パート 2: 内のバッチ/バッチ アウト シナリオ](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md)   
 [パート 3: バッチの作成シナリオ](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)   
 [メッセージ処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)