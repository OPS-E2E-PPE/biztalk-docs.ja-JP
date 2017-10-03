---
title: "メッセージのバッチ処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching
- batching, about batching
- messages, batching
- batching, messages
ms.assetid: d852cf00-3882-4f0f-a4c3-2a39483710ee
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 849f14113d5a5e4776c303ef7a5ea4e1e50a552b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-batching"></a>メッセージのバッチ処理
プロトコルの標準、スケジューリング問題、またはメッセージのサイズ制限は、メッセージ バッチ処理する必要を決める場合があります。 HL7 バッチ ヘッダーとトレーラーのバッチで囲まれたメッセージの正常性レベル 7 (HL7) のバッチで構成されます。 メッセージの区切り記号は、バッチ内の個々 のメッセージを区切ります。  
  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]バッチ処理のシナリオでは、次の 3 つのメッセージ。  
  
-   **断片化された受信バッチ**です。 このシナリオでは、BTAHL7 は、HL7 メッセージ バッチを受信し、送信先システムに個々 のメッセージをルーティングします。  
  
-   **バッチ/アウト バッチ**です。このシナリオでは、BTAHL7 は HL7 メッセージ バッチの受信、バッチ内の個々 のメッセージを確認し、送信先システムに、メッセージ バッチをルーティングします。  
  
-   **バッチまたは送信バッチ処理を作成する**です。 このシナリオでは、BTAHL7 は個々 のメッセージを受信して、送信先システムにルーティングする前にバッチします。  
  
    > [!NOTE]
    >  BTAHL7 では、既定では、送信バッチ処理用メッセージのバッチ処理は有効にしません。 BizTalk エクスプ ローラーを使用して、まず、BTAHL7 バッチ オーケストレーションを参加させると、バッチ オーケストレーションを開始する必要があります。 メッセージのバッチ処理を有効にする方法の詳細については、次を参照してください。[バッチ処理構成](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [受信バッチの断片化](../../adapters-and-accelerators/accelerator-hl7/fragmented-inbound-batch.md)  
  
-   [バッチ処理の構成](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)  
  
-   [バッチ処理のスケジュール設定](../../adapters-and-accelerators/accelerator-hl7/scheduling-batching.md)  
  
-   [受信確認をバッチ処理を構成します。](../../adapters-and-accelerators/accelerator-hl7/configuring-batching-acknowledgments.md)