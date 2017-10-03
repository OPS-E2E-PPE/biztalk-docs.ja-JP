---
title: "手順 4 b: 送信ポートの開始し、FileAct ストア アンド フォワード (プル) シナリオの受信ポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea2215c5-fb43-4c7e-a42d-5d131a6dee38
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad4c6b9d17ab1ea55c1f8378f1cb481a07b09e34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-fileact-store-and-forward-pull-scenario"></a>手順 4 b: 送信ポートの開始し、FileAct ストア アンド フォワード (プル) シナリオの受信ポート
この手順を開始する前に行う必要があります[手順 4A: FileAct ストア アンド フォワード (プル) シナリオの SWIFTNet サービス起動](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md)です。  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a>送信ポートの開始し、受信ポートに  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成した BizTalk アプリケーションの順に展開します。  
  
3.  次の各送信ポート、送信ポートを右クリックし、クリックして**開始**:  
  
    -   **Tutorial_ FA_SendPullResponseToReceiver**  
  
    -   **Tutorial_ FA_SendRequest_SnF**  
  
    -   **Tutorial_ FA_DynamicSendPort**  
  
4.  コンソール ツリーで、BizTalk グループを展開し、受信場所を作成した BizTalk アプリケーションの順に展開します。  
  
5.  次の受信場所ごとに、受信場所を右クリックし、をクリックして**を有効にする**:  
  
    -   **Tutorial_ FA_InputRequest_SnF**  
  
    -   **Tutorial_ FA_InputRequest_PullMode**  
  
## <a name="see-also"></a>参照  
 [手順 4 a: FileAct ストア アンド フォワード (プル) シナリオの SWIFTNet サービスの開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md)   
 [手順 4 C: FileAct ストア アンド フォワード (プル) シナリオのテスト インスタンスを作成します。](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md)   
 [手順 4 D: FileAct ストア アンド フォワード (プル) シナリオの有効なインスタンスのテスト](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-fileact-store-and-forward-pull-scenario.md)