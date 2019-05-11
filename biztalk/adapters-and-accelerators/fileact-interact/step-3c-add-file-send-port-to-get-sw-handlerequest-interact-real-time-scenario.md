---
title: 手順 3 C:FILE 送信ポート Sw:HandleRequest を取得する追加の InterAct リアルタイム シナリオ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31e9c942-ba74-4ae2-b6e1-5266d0fbcb14
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a1deeb12f4af2cf5540217463c211f31a385ba3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365670"
---
# <a name="step-3c-add-file-send-port-to-get-swhandlerequest-interact-real-time-scenario"></a>手順 3 C:FILE 送信ポート Sw:HandleRequest を取得する追加の InterAct リアルタイム シナリオ
パートナーにメッセージを送信するときに、SWIFT はメッセージ ヘッダーを変換し、Sw:HandleRequest メッセージとしてパートナーにメッセージを転送します。 この手順を開始する前に行う必要があります[手順 3 b:INTERACT の受信場所を追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md)します。  
  
### <a name="to-add-a-file-send-port-to-capture-swhandlerequest-message"></a>ファイルを追加するには、送信の Sw:HandleRequest メッセージをキャプチャするポート  
  
1.  開始**BizTalk Server 管理**します。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを順に展開します。  
  
3.  右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート。**  
  
4.  **送信ポートのプロパティ**ウィンドウで、送信ポート名**Tutorial_IA_SendResponseToReceiver**します。  
  
5.  **送信ポートのプロパティ**ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、 をクリックし、**構成**。  
  
6.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、**先フォルダー**ボックスに、C:\SWIFTAdapterTutorial\Interact\HandleRequest を入力し、 をクリックし、 **ok**します。  
  
7.  **送信ポートのプロパティ**ウィンドウで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**送信ハンドラー**|ドロップダウン リストから選択**BizTalkServerApplication**します。|  
    |**送信パイプライン**|ドロップダウン リストから選択**XMLTransmit**します。|  
  
8.  **送信ポートのプロパティ**ウィンドウで、**フィルター**  タブで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**プロパティ**|ドロップダウン リストから選択**BTS します。ReceivePortName**します。|  
    |**[演算子]**|ドロップダウン リストから選択 **==** します。|  
    |**[値]**|型**Tutorial_IA_HandleRequestOneWay_RealTime します。**|  
    |**グループ化**|既定値のままにします。|  
  
9. **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [ステップ 3:作成する送信と受信ポートを InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md)   
 [手順 3 a:ファイル受信場所を追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md)   
 [手順 3 b:INTERACT の受信場所を追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md)   
 [手順 3 D:用に Sw:HandleResponse メッセージをキャプチャする FILE 送信ポートを追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)   
 [手順 3 e:用の INTERACT 送信ポートを追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)