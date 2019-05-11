---
title: 手順 3:テスト シナリオをバッチ内に Batch |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c487d39d-b2be-41d4-963e-d0ee9ba169fb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c619c6f6ba1ee874c6b6eb54b9e499957d1dcee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288190"
---
# <a name="step-3-test-the-batch-inbatch-out-scenario"></a>手順 3:テストのバッチ処理/バッチ アウト シナリオ
この手順では、バッチをテストで/バッチ アウト チュートリアル で、バッチ内のテスト インスタンスを削除/フォルダーにメッセージをバッチ処理します。 送信ポートを設定することは、メッセージを送信、受信ポートによって受信されます、および受信パイプラインが処理され、コピー先のフォルダーにドロップします。  
  
### <a name="to-test-the-batch-inbatch-out-scenario"></a>バッチをテストするで/バッチ アウト シナリオ  
  
1. 使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、  **\<*ドライブ*\>: \Batching Tutorial\Instances**フォルダー。  
  
2. 右クリックして**BatchInBatchOut.txt**、 をクリックし、**コピー**します。  
  
3. 参照、  **\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator HL7\SDK\End ツー エンド Tutorial\Tutorial_BTAHL7PickUp for**フォルダー。  
  
4. フォルダーを右クリックし、**貼り付け**します。  
  
### <a name="to-verify-the-results-of-the-batch-inbatch-out-tutorial"></a>バッチの結果を確認するに/バッチ アウトのチュートリアル  
  
- 使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、  **\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンドのアクセラレータTutorial\Tutorial_BTAHL7Drop**フォルダー。 短時間では後は、必要があります、バッチ メッセージおよび受信確認の処理済みのインスタンスを参照してください、フォルダーに表示されます。 確認して、表示されない場合、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]イベント ビューアーにエラー メッセージ。 各ファイルが別の名前をフォーム\< *Guid*\>.txt します。  
  
   2 つのメッセージで構成されるバッチの最初のメッセージがあります。 BizTalk Accelerator 用 HL7 (BTAHL7) は .txt ファイルでこれら 2 つのメッセージを順番に含めるは。 このバッチは FHS/FTS と BHS/BTS タグは含まれません。 バッチは、タグを含む、すべて FHS/FTS および BHS/BTS、かなどのバッチ メッセージをこの、FHS/FTS BHS/BTS タグがありません必要があります。  
  
  |MSH.9|MSH.10|MSH.3|MSH.5|  
  |-----------|------------|-----------|-----------|  
  |ADT^A03|000001|Tutorial_BatchSource|MESA_IS|  
  |ADT^A03|000002|Tutorial_BatchSource|MESA_IS|  
  
   2 番目のメッセージは、次のフィールドで、バッチ メッセージへの応答で送信される 1 つのアプリケーションの受信確認をする必要があります。  
  
  |MSH.9|MSH.3|MSH.5|MSA.1|MSA.2|  
  |-----------|-----------|-----------|-----------|-----------|  
  |ACK^A03^ACK|MESA_IS|Tutorial_BatchSource|AA|000001|  
  
## <a name="see-also"></a>参照  
 [パート 1: 断片化した受信バッチのシナリオ](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)   
 [パート 3: バッチの作成シナリオ](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)