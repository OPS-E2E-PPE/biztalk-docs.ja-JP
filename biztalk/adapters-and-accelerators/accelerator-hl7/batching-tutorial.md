---
title: バッチ処理のチュートリアル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching tutorial
- tutorials, batching tutorial
- batching tutorial, about the tutorial
- batching, tutorial
ms.assetid: e9010638-74cf-47cd-8cc9-9d6fd08a1b8d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 790303ac2026cbbce2fdb1c436e3dc8c7e9ff7f7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980091"
---
# <a name="batching-tutorial"></a>バッチ処理のチュートリアル
このチュートリアルは、Microsoft の使用に関する詳しい手順を示します[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]を受信し、バッチ処理されたメッセージを送信します。 バッチ処理と、1 つの複合メッセージとしてグループの個々 のメッセージ (または受信確認) を送受信する必要があります。  
  
 BTAHL7 サポートする次の 3 つのバッチ処理のシナリオをメッセージします。  
  
- **断片化した受信バッチ**します。 このシナリオでは、BTAHL7 は、HL7 メッセージのバッチを受信し、送信先システムに、個々 のメッセージをルーティングします。  
  
- **バッチ処理/バッチ アウト**します。BTAHL7 は、HL7 メッセージのバッチを受信するには、バッチ内の個々 のメッセージを確認します。 および、送信先システムにメッセージのバッチをルーティングします。  
  
- **バッチ (または、送信バッチ処理) を作成**です。 BTAHL7 では、個々 のメッセージを受信し、送信先システムにルーティングする前にバッチとしてします。  
  
  このチュートリアルには、3 つのバッチ処理のシナリオの各パーツが含まれています。 指定された順序で、チュートリアルの 3 つの部分を使用して、第 1 部には、第 2 部と第 3 部に必要な手順が含まれています。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [バッチ処理のチュートリアルを使用するための準備](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)  
  
-   [パート 1: 断片化した受信バッチのシナリオ](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)  
  
-   [パート 2: バッチ イン/バッチ アウトのシナリオ](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md)  
  
-   [パート 3: バッチの作成シナリオ](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)