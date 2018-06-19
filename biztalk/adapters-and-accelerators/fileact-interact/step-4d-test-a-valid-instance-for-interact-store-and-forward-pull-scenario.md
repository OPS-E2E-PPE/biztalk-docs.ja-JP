---
title: '手順 4 D: InterAct ストア アンド フォワード (プル) シナリオの有効なインスタンスをテスト |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c2933d0-bbe3-4486-832e-5009b2d760ac
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c9c8ea24eeb5541cf84448363ca91fcb8171f19
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223946"
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-store-and-forward-pull-scenario"></a>手順 4 D: InterAct ストア アンド フォワード (プル) シナリオの有効なインスタンスをテストします。
この手順を開始する前に行う必要があります[手順 4 C: InterAct ストア アンド フォワード (プル) シナリオのテスト インスタンスを作成する](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md)です。  
  
### <a name="to-test-a-valid-instance"></a>有効なインスタンスをテストするには  
  
1.  ファイル ExchangeReqSimple.xml c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF にドロップします。  
  
2.  しばらくすると、ExchangeReqSimple.xml ファイルがフォルダーから消えますことを確認します。  
  
3.  C:\SWIFTAdapterTutorial\Interact\PullRequest ファイル acquirequeue.xml にドロップします。  
  
4.  参照がフォルダー内に Sw:HandleRequest C:\SWIFTAdapterTutorial\Interact\PullResponse のことを確認します。  
  
5.  Sw:HandleRequest メッセージをメモ帳などのテキスト エディターで開き、payload セクションが ExchangeReqSimple.xml ファイルのものと同じであることを確認します。  
  
## <a name="see-also"></a>参照  
 [手順 4 a: InterAct ストア アンド フォワード (プル) シナリオの SWIFTNet サービスを開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md)   
 [手順 4 b: 送信ポートの開始し、InterAct ストア アンド フォワード (プル) シナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [手順 4 C: InterAct ストア アンド フォワード (プル) シナリオのテスト インスタンスを作成](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md)