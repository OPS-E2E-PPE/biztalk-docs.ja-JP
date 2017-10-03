---
title: "手順 4 b: 送信ポートの開始し、InterAct ストア アンド フォワード (プル) シナリオの受信ポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00ab119d-ed44-4f4a-84ea-20f2c41e5a92
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b747c76b30b9f7d04bef379be9eaccaaeca063ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-interact-store-and-forward-pull-scenario"></a>手順 4 b: 送信ポートの開始し、InterAct ストア アンド フォワード (プル) シナリオの受信ポート
この手順を開始する前に行う必要があります[手順 4: InterAct ストア アンド フォワード エンド ツー エンドのシナリオをテスト](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)です。  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a>送信ポートの開始し、受信ポートに  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成した BizTalk アプリケーションの順に展開します。  
  
3.  次の各送信ポート、送信ポートを右クリックし、クリックして**開始**:  
  
    -   **Tutorial_ IA_SendPullResponseToReceiver**  
  
    -   **Tutorial_IA_SendRequest_SnF**  
  
    -   **Tutorial_IA_DynamicSendPort**  
  
4.  コンソール ツリーで、BizTalk グループを展開し、受信場所を作成した BizTalk アプリケーションの順に展開します。  
  
5.  次の受信場所ごとに、受信場所を右クリックし、をクリックして**を有効にする**:  
  
    -   **Tutorial_IA_InputRequest_SnF**  
  
    -   **Tutorial_ IA_InputRequest_PullMode**  
  
## <a name="see-also"></a>参照  
 [手順 4 a: InterAct ストア アンド フォワード (プル) シナリオの SWIFTNet サービスを開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md)   
 [手順 4 C: InterAct ストア アンド フォワード (プル) シナリオのテスト インスタンスを作成](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md)   
 [手順 4 D: InterAct ストア アンド フォワード (プル) シナリオの有効なインスタンスをテストします。](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-interact-store-and-forward-pull-scenario.md)