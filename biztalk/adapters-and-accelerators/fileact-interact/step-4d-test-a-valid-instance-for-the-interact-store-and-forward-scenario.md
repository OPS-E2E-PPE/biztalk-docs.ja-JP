---
title: "手順 4 D: InterAct ストアと転送シナリオの有効なインスタンスをテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6aa49df8-ccf6-455a-99ff-38879d2b7bf9
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5d27b23195adffc5915d8cb2170dca9e975ec94
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-store-and-forward-scenario"></a>手順 4 D: InterAct ストアと転送シナリオの有効なインスタンスのテスト
この手順を開始する前に行う必要があります[手順 4 C: InterAct ストア アンド フォワードのシナリオのテスト インスタンスを作成する](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md)です。  
  
### <a name="to-test-a-valid-instance"></a>有効なインスタンスをテストするには  
  
1.  C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF に ExchangeReqSimple.xml ファイルを削除します。  
  
2.  しばらくすると、ExchangeReqSimple.xml ファイルがフォルダーから消えますことを確認します。  
  
3.  C:\SWIFTAdapterTutorial\Interact\HandleRequest を参照します。 フォルダー内にその Sw:HandleRequest を確認します。  
  
4.  Sw:HandleRequest メッセージをメモ帳などのテキスト エディターで開き、payload セクションが ExchangeReqSimple.xml ファイルのものと同じであることを確認します。  
  
## <a name="see-also"></a>参照  
 [手順 4: InterAct ストアと転送のエンド ツー エンド シナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)   
 [手順 4 a: サービスを開始します SWIFTNet InterAct ストアと転送シナリオ](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md)   
 [手順 4 b: 送信ポートの開始し、受信ポートを InterAct ストアと転送シナリオ](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md)   
 [手順 4 C: InterAct ストアと転送シナリオのテスト インスタンスを作成します。](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md)