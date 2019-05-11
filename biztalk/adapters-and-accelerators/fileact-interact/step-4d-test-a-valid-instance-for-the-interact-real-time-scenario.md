---
title: 手順 4 D:テストの有効なインスタンス、InterAct リアルタイム シナリオ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e163c3ac-a00d-40cf-b1b8-4a38f74ab0e8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 190ba5003d24803bd8b8b3c304e671eb6ab4303c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364653"
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-real-time-scenario"></a>手順 4 D:テストの有効なインスタンス、InterAct リアルタイム シナリオ
この手順を開始する前に行う必要があります[手順 4 C:テスト インスタンスを作成、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md)します。  
  
### <a name="to-test-a-valid-instance"></a>有効なインスタンスをテストするには  
  
1.  Drop the file ExchangeReqSimple.xml into C:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime.  
  
2.  しばらくすると、ExchangeReqSimple.xml ファイルがフォルダーから消えることを確認します。  
  
3.  C:\SWIFTAdapterTutorial\Interact\HandleRequest Sw:HandleRequest、ハンドルの要求メッセージを表示するを参照します。  
  
4.  C:\SWIFTAdapterTutorial\Interact\Response Sw:HandleResponse、ハンドルの応答メッセージを表示するを参照します。  
  
5.  メモ帳などのテキスト エディターで Sw:HandleRequest メッセージを開き、payload セクションが ExchangeReqSimple.xml ファイルと同じであることを確認します。  
  
## <a name="see-also"></a>参照  
 [手順 4:テスト、InterAct リアルタイム エンド ツー エンドのシナリオ](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)   
 [手順 4 a:SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md)   
 [手順 4 b:送信ポートの開始し、受信ポートを InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md)   
 [手順 4 C:テスト インスタンスを作成、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md)