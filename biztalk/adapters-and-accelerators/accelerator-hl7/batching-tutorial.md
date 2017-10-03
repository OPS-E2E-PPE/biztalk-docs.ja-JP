---
title: "チュートリアルをバッチ処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching tutorial
- tutorials, batching tutorial
- batching tutorial, about the tutorial
- batching, tutorial
ms.assetid: e9010638-74cf-47cd-8cc9-9d6fd08a1b8d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27e2aff66468c697c92adb4c452250b70dae2e59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="batching-tutorial"></a>バッチ処理のチュートリアル
このチュートリアルを使用するための手順の説明[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]を受け取り、バッチ処理されたメッセージを送信します。 バッチ処理と、1 つの複合メッセージとして、個々 のメッセージ (または受信確認) のグループの送受信が含まれます。  
  
 BTAHL7 では次の 3 つは、バッチ処理のシナリオをメッセージします。  
  
-   **断片化された受信バッチ**です。 このシナリオでは、BTAHL7 は、HL7 メッセージ バッチを受信し、送信先システムに個々 のメッセージをルーティングします。  
  
-   **バッチ/アウト バッチ**です。BTAHL7 は、HL7 メッセージ バッチを受信、バッチ内の個々 のメッセージを確認し、送信先システムに、メッセージ バッチをルーティングします。  
  
-   **バッチ (または、送信バッチ処理) を作成**です。 BTAHL7 では、個々 のメッセージを受信し、送信先システムにルーティングする前にそれらをバッチ処理します。  
  
 このチュートリアルには、3 つのバッチ処理のシナリオの各部分が含まれています。 指定された順序で、チュートリアルの 3 つの部分を使用します。第 1 部には、第 2 部と第 3 部の前提条件となる手順が含まれています。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [バッチ処理のチュートリアルを使用する準備をしています](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)  
  
-   [パート 1: 断片化した受信バッチのシナリオ](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)  
  
-   [パート 2: バッチのシナリオをバッチ処理/](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md)  
  
-   [パート 3: 作成するバッチのシナリオ](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)