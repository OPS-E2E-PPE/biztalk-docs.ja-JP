---
title: '手順 4 C: InterAct ストアと転送シナリオのテスト インスタンスを作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64a69dcc-d307-47c0-87e8-b0cb2a4d655b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44addc30191dd9541d7f5964a3de0eec244c9993
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225162"
---
# <a name="step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario"></a>手順 4 C: InterAct ストアと転送シナリオのテスト インスタンスを作成します。
この手順を開始する前に行う必要があります[手順 4B: 送信ポートと対話するストア アンド フォワード シナリオの受信ポートを開始](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md)です。  
  
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
  
2.  ExchangeReqSimple.xml という名前のファイルを保存します。  
  
## <a name="see-also"></a>参照  
 [手順 4: InterAct ストアと転送のエンド ツー エンド シナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)   
 [手順 4 a: サービスを開始します SWIFTNet InterAct ストアと転送シナリオ](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md)   
 [手順 4 b: 送信ポートの開始し、受信ポートを InterAct ストアと転送シナリオ](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md)   
 [手順 4 D: InterAct ストアと転送シナリオの有効なインスタンスのテスト](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-store-and-forward-scenario.md)