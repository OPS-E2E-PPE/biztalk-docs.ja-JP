---
title: バッチ メッセージの処理 |Microsoft ドキュメント
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
ms.openlocfilehash: aad80bb8fe9a59163ee17e7862bece728fdc52b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204762"
---
# <a name="batch-message-processing"></a>バッチ メッセージの処理
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) HL7 の 3 種類の処理 2.X バッチ シナリオ。  
  
-   受信バッチの断片化されたシナリオです。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]これらのバッチを別々 の出力メッセージに解析します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]断片化されたバッチの各メッセージの受信確認 (Ack) を送信します。  
  
-   バッチ/バッチ シナリオ アウトします。 これらは、バインドでバッチを[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]を断片化します、を通過し、そのままのバッチとして送信します。 場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バッチ、ACK の ACK の送信には、バージョン ID が含まれています。  
  
-   作成するバッチのシナリオです。 このシナリオで[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]を組み合わせたものが、出力のバッチに入力メッセージを区別します。  
  
 2 つの方法のいずれかでバッチの書式を設定することができます。  
  
-   でファイルのヘッダーとトレーラー (FHS/FTS) バッチ ヘッダーとトレーラー (BHS/BTS)。  
  
-   でないファイルまたはバッチ ヘッダー/トレーラです。  
  
## <a name="see-also"></a>参照  
 [メッセージのバッチ処理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)   
 [バッチ処理のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)   
 [パート 1: 断片化した受信バッチのシナリオ](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)   
 [パート 2: バッチのシナリオをバッチ処理/](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md)   
 [パート 3: 作成するバッチのシナリオ](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)   
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)