---
title: "ステップ 3 e: 対話する送信ポートの追加、リアルタイムのシナリオを対話 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9522386-e980-4ab1-b65a-939ca7936ad9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec380c088f27fe09f518c385990e3801b5c019dd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario"></a>ステップ 3 e: 対話する送信ポートの追加、リアルタイムのシナリオの対話
完全な[ステップ 3 D: リアルタイム シナリオでは対話 Sw:HandleResponse メッセージをキャプチャする FILE 送信ポートを追加](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)この手順を開始する前にします。
  
## <a name="add-an-interact-send-port"></a>対話する送信ポートを追加します。  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。  
  
3.  右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。  
  
4.  **送信ポートのプロパティ**ウィンドウで、送信ポートの名前**Tutorial_IA_SendRequest_RealTime**です。  
  
5.  **送信ポートのプロパティ** ウィンドウから、**トランスポートの種類**ドロップダウン リストで、 **INTERACT**、順にクリック**構成**です。  
  
6.  **トランスポートのプロパティの対話** ダイアログ ボックスで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**Password**|SAG 接続適切なパスワードを設定します。|  
    |**ユーザー名**|SAG 接続を適切なユーザー名を設定します。|  
    |**アダプターのモード**|ドロップダウン リストから選択**リアルタイム**です。|  
    |**メッセージの形式**|**InteractMessage**です。|  
    |**否認不可インジケーター**|**FALSE**。|  
    |**要求の種類**|適切な入力\<RequestType\> SWIFT でのプロビジョニングに基づく文字列。|  
    |**ResponseCrypto**|**FALSE**。|  
    |**要求元**|適切な設定\<リクエスター\> SWIFT でのプロビジョニングに基づく文字列。|  
    |**応答側**|適切な設定\<レスポンダー\> SWIFT でのプロビジョニングに基づく文字列。|  
    |**サービス名**|適切な設定\<サービス名\>SWIFT でのプロビジョニングに基づきます。|  
    |**配信通知**|ドロップダウン リストから選択**FALSE**です。|  
    |**通知キュー**|SWIFT でのプロビジョニングに基づく、適切なキュー名を入力します。|  
  
    > [!NOTE]
    >  ペイロードは、転送するのには、専用の場合は、ポートと対話する送信ポートが受信"Payloadonly"で、対話する MessageFormat を設定します。 受信の設定し、送信パイプラインをパススルーします。  
  
7.  **[OK]**をクリックします。  
  
8.  **送信ポートのプロパティ** ウィンドウで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**送信ハンドラー**|ドロップダウン リストから、対話ホストを選択します。|  
    |**送信パイプライン**|ドロップダウン リストから選択**XMLTransmit**です。|  
    |**受信パイプライン**|**[Xmlreceive]**|  
  
9. **送信ポートのプロパティ** ウィンドウで、**フィルター**  タブで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**プロパティ**|ドロップダウン リストから選択**BTS です。ReceivePortName**です。|  
    |**演算子**|ドロップダウン リストから選択 **==**です。|  
    |**値**|型**Tutorial_IA_InputRequest_RealTime**です。|  
    |**グループ化**|既定値を使用します。|  
  
10. **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [手順 3: が送信を作成し、受信のポート、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md)   
 [手順 3: ファイルの受信場所を追加、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md)   
 [手順 3 b: 対話の受信場所を追加、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md)   
 [手順 3 C: の Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートを追加、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md)   
 [手順 3D: InterAct リアルタイム シナリオ用に Sw:HandleResponse メッセージをキャプチャするためにファイルの送信ポートを追加する](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)