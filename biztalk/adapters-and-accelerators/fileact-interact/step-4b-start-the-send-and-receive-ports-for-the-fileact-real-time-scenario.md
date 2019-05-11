---
title: 手順 4 b:送信ポートを開始および FileAct リアルタイム シナリオ用の受信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c56b5f7b-551a-4bd2-97c7-0996f5d1b1a2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69fb541f792577c2a1bca5e7914a4e2cd6580d65
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364914"
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-fileact-real-time-scenario"></a>手順 4 b:送信ポートを開始および FileAct リアルタイム シナリオ用の受信ポート
この手順を開始する前に行う必要があります[手順 4 a:FileAct リアルタイム シナリオ用に SWIFTNet サービスを開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md)します。  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a>ポート、送信ポートと受信開始するには  
  
1.  開始**BizTalk Server 管理**します。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成した BizTalk アプリケーションを順に展開します。  
  
3.  次の各送信ポート、送信ポートを右クリックし、クリックして**開始**:  
  
    -   **Tutorial_FA_SendResponseToReceiver**  
  
    -   **Tutorial_FA_SendResponseToSender**  
  
    -   **Tutorial_FA_SendRequest_RealTime**  
  
    -   **Tutorial_ GetStatusReports**  
  
4.  コンソール ツリーで、BizTalk グループを展開し、受信場所を作成した BizTalk アプリケーションを順に展開します。  
  
5.  次の受信場所ごとに、受信場所を右クリックし、順にクリックします**を有効にする**:  
  
    -   **Tutorial_FA_InputRequest_RealTime**  
  
    -   **Tutorial_FA_HandleRequestOneWay_RealTime**  
  
## <a name="see-also"></a>参照  
 [手順 4:FileAct リアルタイム エンド ツー エンド シナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md)   
 [手順 4 a:FileAct リアルタイム シナリオ用に SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md)   
 [手順 4 C:FileAct リアルタイム シナリオ用のテスト インスタンスを作成します。](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md)   
 [手順 4 D:FileAct リアルタイム シナリオ用の有効なインスタンスをテストします。](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-fileact-real-time-scenario.md)