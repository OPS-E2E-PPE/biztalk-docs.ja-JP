---
title: 手順 4 b:送信ポートの開始し、受信ポートを InterAct リアルタイム シナリオ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dffee9a6-5877-4744-9b46-12ca4f8fa959
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8dc9021b9e9d42ca8dd9288d57bb976ef91f640
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364900"
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-interact-real-time-scenario"></a>手順 4 b:送信ポートの開始し、受信ポートを InterAct リアルタイム シナリオ
この手順を開始する前に行う必要があります[手順 4 a:SWIFTNet サービスを開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md)します。  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a>ポート、送信ポートと受信開始するには  
  
1.  開始**BizTalk Server 管理**します。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成した BizTalk アプリケーションを順に展開します。  
  
3.  次の各送信ポート、送信ポートを右クリックし、クリックして**開始**:  
  
    -   **Tutorial_IA_SendResponseToReceiver**  
  
    -   **Tutorial_IA_SendResponseToSender**  
  
    -   **Tutorial_IA_SendRequest_RealTime**  
  
4.  コンソール ツリーで、BizTalk グループを展開し、受信場所を作成した BizTalk アプリケーションを順に展開します。  
  
5.  次の受信場所ごとに、受信場所を右クリックし、順にクリックします**を有効にする**:  
  
    -   **Tutorial_IA_InputRequest_RealTime**  
  
    -   **Tutorial_IA_HandleRequestOneWay_RealTime**  
  
## <a name="see-also"></a>参照  
 [手順 4:テスト、InterAct リアルタイム エンド ツー エンドのシナリオ](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)   
 [手順 4 a:SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md)   
 [手順 4 C:テスト インスタンスを作成、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md)   
 [手順 4 D:テストの有効なインスタンス、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-real-time-scenario.md)