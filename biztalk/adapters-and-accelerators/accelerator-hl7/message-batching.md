---
title: メッセージのバッチ処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching
- batching, about batching
- messages, batching
- batching, messages
ms.assetid: d852cf00-3882-4f0f-a4c3-2a39483710ee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f487d479036f9946dbd32ff9444d8cd714a0a1f1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303825"
---
# <a name="message-batching"></a>メッセージのバッチ処理
プロトコルの標準、スケジュールの問題またはメッセージ サイズの制限は、メッセージのバッチの必要を起こさ可能性があります。 正常性レベル 7 (HL7) のバッチは、HL7 バッチ ヘッダーとトレーラーのバッチで囲まれたメッセージで構成されます。 メッセージの区切り記号は、バッチ内の個々 のメッセージを区切ります。  
  
 Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]バッチ処理のシナリオでは、次の 3 つのメッセージ。  
  
-   **断片化した受信バッチ**します。 このシナリオでは、BTAHL7 は、HL7 メッセージのバッチを受信し、送信先システムに、個々 のメッセージをルーティングします。  
  
-   **バッチ処理/バッチ アウト**します。このシナリオでは、BTAHL7 は HL7 メッセージのバッチを受信、バッチ内の個々 のメッセージを確認し、送信先システムにメッセージのバッチをルーティングします。  
  
-   **バッチまたは送信バッチ処理を作成する**します。 このシナリオでは、BTAHL7 は個々 のメッセージを受信し、送信先システムにルーティングする前にバッチとしてします。  
  
    > [!NOTE]
    >  BTAHL7 では、既定では、送信バッチ処理用メッセージのバッチ処理は有効にしません。 BizTalk エクスプ ローラーを使用して、まず、BTAHL7 バッチ オーケストレーションを参加させると、バッチ オーケストレーションを開始する必要があります。 メッセージのバッチ処理を有効にする方法の詳細については、次を参照してください。[バッチ処理構成](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [断片化した受信バッチ](../../adapters-and-accelerators/accelerator-hl7/fragmented-inbound-batch.md)  
  
-   [バッチ処理の構成](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)  
  
-   [バッチ処理のスケジュール](../../adapters-and-accelerators/accelerator-hl7/scheduling-batching.md)  
  
-   [受信確認のバッチ処理の構成](../../adapters-and-accelerators/accelerator-hl7/configuring-batching-acknowledgments.md)