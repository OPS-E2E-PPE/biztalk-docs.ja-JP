---
title: 手順 4 D:InterAct ストア アンド フォワード シナリオ用の有効なインスタンスのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6aa49df8-ccf6-455a-99ff-38879d2b7bf9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a9bac2a14267b0767cd0498ecfbb8b0f96f686e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364666"
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-store-and-forward-scenario"></a>手順 4 D:InterAct ストア アンド フォワード シナリオ用の有効なインスタンスをテストします。
この手順を開始する前に行う必要があります[手順 4 C:InterAct ストア アンド フォワード シナリオ用にテスト インスタンスを作成](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md)です。  
  
### <a name="to-test-a-valid-instance"></a>有効なインスタンスをテストするには  
  
1.  Drop the file ExchangeReqSimple.xml into c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF  
  
2.  しばらくすると、ExchangeReqSimple.xml ファイルがフォルダーから消えることを確認します。  
  
3.  C:\SWIFTAdapterTutorial\Interact\HandleRequest に移動します。 その Sw:HandleRequest はフォルダーを確認します。  
  
4.  メモ帳などのテキスト エディターで Sw:HandleRequest メッセージを開き、payload セクションが ExchangeReqSimple.xml ファイルと同じであることを確認します。  
  
## <a name="see-also"></a>参照  
 [手順 4:InterAct ストア アンド フォワード エンド ツー エンド シナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)   
 [手順 4 a:InterAct ストア アンド フォワード シナリオ用に SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md)   
 [手順 4 b:送信ポートの開始し、InterAct ストア アンド フォワード シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md)   
 [手順 4 C:InterAct ストア アンド フォワード シナリオ用のテスト インスタンスを作成します。](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md)