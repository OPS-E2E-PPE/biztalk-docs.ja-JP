---
title: "手順 4 b: 送信ポートの開始し、FileAct ストア アンド フォワードのシナリオの受信ポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f8c34b1-24a5-4ac7-bb96-27834bc3c711
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb40a366a3c4952eaac9557ea04f5a84c846c81e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-fileact-store-and-forward-scenario"></a>手順 4 b: 送信ポートの開始し、FileAct ストア アンド フォワードのシナリオの受信ポート
この手順を開始する前に行う必要があります[手順 4A: FileAct ストア アンド フォワードのシナリオの SWIFTNet サービス起動](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md)です。  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a>送信ポートの開始し、受信ポートに  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成した BizTalk アプリケーションの順に展開します。  
  
3.  次の各送信ポート、送信ポートを右クリックし、クリックして**開始**:  
  
    -   **Tutorial_FA_SendResponseToReceiver**  
  
    -   **Tutorial_FA_SendRequest_SnF**  
  
    -   **Tutorial_ GetStatusReports**  
  
4.  コンソール ツリーで、BizTalk グループを展開し、受信場所を作成した BizTalk アプリケーションの順に展開します。  
  
5.  次の受信場所ごとに、受信場所を右クリックし、をクリックして**を有効にする**:  
  
    -   **Tutorial_FA_InputRequest_SnF**  
  
    -   **Tutorial_FA_HandleRequestOneWay_SnF**  
  
## <a name="see-also"></a>参照  
 [手順 4: FileAct ストア アンド フォワードのエンド ツー エンド シナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)   
 [手順 4 a: FileAct ストア アンド フォワードのシナリオの SWIFTNet サービスの開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md)   
 [手順 4 C: FileAct ストア アンド フォワードのシナリオのテスト インスタンスを作成します。](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md)   
 [手順 4 D: FileAct ストア アンド フォワードのシナリオの有効なインスタンスのテスト](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-scenario.md)