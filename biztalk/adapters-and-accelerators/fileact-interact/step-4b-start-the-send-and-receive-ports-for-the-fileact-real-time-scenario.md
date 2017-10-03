---
title: "手順 4 b: 送信ポートの開始し、受信ポートを FileAct リアルタイムのシナリオの |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c56b5f7b-551a-4bd2-97c7-0996f5d1b1a2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a9933f347d2da08dc2b8665dfd01530871a8cdf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-fileact-real-time-scenario"></a>手順 4 b: 送信ポートを開始および FileAct リアルタイム シナリオでは、受信ポート
この手順を開始する前に行う必要があります[手順 4A: FileAct リアルタイム シナリオの SWIFTNet サービス起動](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md)です。  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a>送信ポートの開始し、受信ポートに  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成した BizTalk アプリケーションの順に展開します。  
  
3.  次の各送信ポート、送信ポートを右クリックし、クリックして**開始**:  
  
    -   **Tutorial_FA_SendResponseToReceiver**  
  
    -   **Tutorial_FA_SendResponseToSender**  
  
    -   **Tutorial_FA_SendRequest_RealTime**  
  
    -   **Tutorial_ GetStatusReports**  
  
4.  コンソール ツリーで、BizTalk グループを展開し、受信場所を作成した BizTalk アプリケーションの順に展開します。  
  
5.  次の受信場所ごとに、受信場所を右クリックし、をクリックして**を有効にする**:  
  
    -   **Tutorial_FA_InputRequest_RealTime**  
  
    -   **Tutorial_FA_HandleRequestOneWay_RealTime**  
  
## <a name="see-also"></a>参照  
 [手順 4: FileAct エンド ツー エンドのリアルタイムのシナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md)   
 [手順 4 a: FileAct リアルタイム シナリオの SWIFTNet サービスの開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md)   
 [手順 4 C: FileAct リアルタイム シナリオのテスト インスタンスを作成](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md)   
 [手順 4 D: FileAct リアルタイム シナリオでは、有効なインスタンスをテストします。](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-fileact-real-time-scenario.md)