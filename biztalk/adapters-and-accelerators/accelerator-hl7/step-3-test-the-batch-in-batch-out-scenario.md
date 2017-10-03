---
title: "手順 3: テストのシナリオをバッチ内にバッチ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c487d39d-b2be-41d4-963e-d0ee9ba169fb
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eec20b86b3e921fba8d1636a0aab7803ec1615d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-test-the-batch-inbatch-out-scenario"></a>手順 3: テストのバッチ処理/シナリオをバッチ処理
この手順では、バッチをテストでバッチをチュートリアルでのバッチ処理のテスト インスタンスの削除/フォルダーにメッセージをバッチ処理/です。 送信ポートを設定するにはメッセージを送信、受信ポートによって受信されます、および受信パイプラインが処理され、コピー先のフォルダーにドロップします。  
  
### <a name="to-test-the-batch-inbatch-out-scenario"></a>バッチのテストでシナリオをバッチ処理/  
  
1.  使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、   **\<*ドライブ*>: \Batching Tutorial\Instances** フォルダーです。  
  
2.  右クリックして**BatchInBatchOut.txt**、クリックして**コピー**です。  
  
3.  参照、   **\<*ドライブ*>: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for HL7\SDK\End エンドツー エンド Tutorial\Tutorial_BTAHL7PickUp * * フォルダーです。  
  
4.  フォルダーを右クリックし、をクリックして**貼り付け**です。  
  
### <a name="to-verify-the-results-of-the-batch-inbatch-out-tutorial"></a>バッチの結果を確認するでチュートリアルをバッチ処理/  
  
-   使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、   **\<*ドライブ*>: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for HL7\SDK\End エンドツー エンド tutorial \* * Tutorial_BTAHL7Drop フォルダーです。 短時間後に、バッチ メッセージおよび受信確認の処理済みのインスタンスを参照してください、フォルダーに表示する必要があります。 これらが表示されない場合は、確認、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]イベント ビューアで、エラー メッセージ。 各ファイル形式で別の名前を持つ必要があります\< *Guid*> .txt です。  
  
     最初のメッセージは、2 つのメッセージで構成されるバッチにする必要があります。 BizTalk Accelerator 用 HL7 (BTAHL7) は .txt ファイルでこれら 2 つのメッセージを順番に含まれます。 このバッチでは、FHS/FTS と BHS/BTS タグは含まれません。 バッチは、タグを含めるかすべて FHS/FTS および BHS/BTS、か、このバッチ メッセージ、FHS/FTS、BHS/BTS タグがないなどの必要があります。  
  
    |MSH.9|MSH.10|MSH.3|MSH.5|  
    |-----------|------------|-----------|-----------|  
    |ADT ^ A03|000001|Tutorial_BatchSource|MESA_IS|  
    |ADT ^ A03|000002|Tutorial_BatchSource|MESA_IS|  
  
     2 番目のメッセージは、バッチ メッセージと、次のフィールドへの応答で送信される 1 つのアプリケーションの受信確認をする必要があります。  
  
    |MSH.9|MSH.3|MSH.5|MSA.1|MSA.2|  
    |-----------|-----------|-----------|-----------|-----------|  
    |ACK ^ A03 ^ ACK|MESA_IS|Tutorial_BatchSource|AA|000001|  
  
## <a name="see-also"></a>参照  
 [パート 1: 断片化した受信バッチのシナリオ](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)   
 [パート 3: 作成するバッチのシナリオ](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)