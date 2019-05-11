---
title: 手順 4 C:テスト インスタンスを作成、InterAct リアルタイム シナリオ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3557acdc-eb3f-4c70-b64a-3f523a1ba650
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4539670824f23ddd4b4104da890c38ed6736fc6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364794"
---
# <a name="step-4c-create-a-test-instance-for-the-interact-real-time-scenario"></a>手順 4 C:テスト インスタンスを作成、InterAct リアルタイム シナリオ
この手順を開始する前に行う必要があります[手順 4 b:送信ポートの開始し、受信ポートを InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md)します。  
  
### <a name="to-create-a-test-instance"></a>テスト インスタンスを作成するには  
  
1.  新しいファイルをメモ帳などのテキスト エディターで開き、次を貼り付けます。  
  
    ```  
    <SwInt-ExchangeRequest>  
    <SwInt-Request>  
    <SwInt-RequestPayload>  
    Get Well soon  
    </SwInt-RequestPayload>  
    </SwInt-Request>  
    </SwInt-ExchangeRequest>  
    ```  
  
2.  名前のファイルを保存**ExchangeReqSimple.xml**します。  
  
## <a name="see-also"></a>参照  
 [手順 4:テスト、InterAct リアルタイム エンド ツー エンドのシナリオ](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)   
 [手順 4 a:SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md)   
 [手順 4 b:送信ポートの開始し、受信ポートを InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md)   
 [手順 4 D:テストの有効なインスタンス、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-real-time-scenario.md)