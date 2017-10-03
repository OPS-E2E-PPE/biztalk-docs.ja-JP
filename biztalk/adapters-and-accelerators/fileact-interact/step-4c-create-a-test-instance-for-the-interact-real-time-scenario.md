---
title: "手順 4 C: のテスト インスタンスを作成、リアルタイムのシナリオを対話 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3557acdc-eb3f-4c70-b64a-3f523a1ba650
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21c0035074eba0eec6994aa7ab024afbcec10984
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4c-create-a-test-instance-for-the-interact-real-time-scenario"></a>手順 4 C: のテスト インスタンスを作成、リアルタイムのシナリオの対話
この手順を開始する前に行う必要があります[手順 4B: 対話リアルタイム シナリオでは、送信ポートと受信ポートを開始](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md)です。  
  
### <a name="to-create-a-test-instance"></a>テスト インスタンスを作成するには  
  
1.  メモ帳などのテキスト エディターで、新しいファイルを開くし、以下を貼り付けます。  
  
    ```  
    <SwInt-ExchangeRequest>  
    <SwInt-Request>  
    <SwInt-RequestPayload>  
    Get Well soon  
    </SwInt-RequestPayload>  
    </SwInt-Request>  
    </SwInt-ExchangeRequest>  
    ```  
  
2.  名前のファイルを保存**ExchangeReqSimple.xml**です。  
  
## <a name="see-also"></a>参照  
 [手順 4: テスト、リアルタイムのエンド ツー エンド シナリオの対話](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)   
 [手順 4 a: SWIFTNet サービスの開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md)   
 [手順 4 b: 送信ポートの開始し、受信のポート、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md)   
 [手順 4 D: テストの有効なインスタンス、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-real-time-scenario.md)