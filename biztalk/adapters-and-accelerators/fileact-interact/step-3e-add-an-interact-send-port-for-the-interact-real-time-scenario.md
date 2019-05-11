---
title: 手順 3 e:用の INTERACT 送信ポートを追加、InterAct リアルタイム シナリオ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9522386-e980-4ab1-b65a-939ca7936ad9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9503976d47f70a0077b5a30598d5daa826855e1e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365464"
---
# <a name="step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario"></a>手順 3 e:用の INTERACT 送信ポートを追加、InterAct リアルタイム シナリオ
完全な[手順 3 D:操作のリアルタイム シナリオ用に Sw:HandleResponse メッセージをキャプチャする FILE 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)この手順を開始する前にします。
  
## <a name="add-an-interact-send-port"></a>INTERACT 送信ポートを追加します。  
  
1.  開始**BizTalk Server 管理**します。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを順に展開します。  
  
3.  右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な送信請求-応答送信ポート**します。  
  
4.  **送信ポートのプロパティ**ウィンドウで、送信ポート名**Tutorial_IA_SendRequest_RealTime**します。  
  
5.  **送信ポートのプロパティ**ウィンドウから、**トランスポートの種類**ドロップダウン リストで、 **INTERACT**、順にクリックします**構成**します。  
  
6.  **トランスポートのプロパティの対話** ダイアログ ボックスで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**Password**|SAG 接続に応じて、パスワードを設定します。|  
    |**ユーザー名**|SAG 接続用の適切なユーザー名を設定します。|  
    |**アダプターのモード**|ドロップダウン リストから選択**リアルタイム**します。|  
    |**メッセージの形式**|**InteractMessage**します。|  
    |**否認不可のインジケーター**|**FALSE**。|  
    |**要求の種類**|適切な入力\<RequestType\> SWIFT で、プロビジョニングに基づく文字列。|  
    |**ResponseCrypto**|**FALSE**。|  
    |**要求元**|適切な設定\<リクエスター\> SWIFT で、プロビジョニングに基づく文字列。|  
    |**応答側**|適切な設定\<レスポンダー\> SWIFT で、プロビジョニングに基づく文字列。|  
    |**[サービス名]**|適切な設定\<サービス名\>を基に、SWIFT でプロビジョニングします。|  
    |**配信通知**|ドロップダウン リストから選択**FALSE**します。|  
    |**通知キュー**|SWIFT で、プロビジョニングに基づく、適切なキュー名を入力します。|  
  
    > [!NOTE]
    >  ペイロードは、転送するのには、専用の場合は"Payloadonly"で、対話を MessageFormat をセットの受信ポートと INTERACT 送信ポート。 受信を設定し、パススルー パイプラインに送信します。  
  
7.  **[OK]** をクリックします。  
  
8.  **送信ポートのプロパティ**ウィンドウで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**送信ハンドラー**|ドロップダウン リストから、対話するホストを選択します。|  
    |**送信パイプライン**|ドロップダウン リストから選択**XMLTransmit**します。|  
    |**受信パイプライン**|**[Xmlreceive]**|  
  
9. **送信ポートのプロパティ**ウィンドウで、**フィルター**  タブで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**プロパティ**|ドロップダウン リストから選択**BTS します。ReceivePortName**します。|  
    |**[演算子]**|ドロップダウン リストから選択 **==** します。|  
    |**[値]**|型**Tutorial_IA_InputRequest_RealTime**します。|  
    |**グループ化**|既定値のままにします。|  
  
10. **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [ステップ 3:作成する送信と受信ポートを InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md)   
 [手順 3 a:ファイル受信場所を追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md)   
 [手順 3 b:INTERACT の受信場所を追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md)   
 [手順 3 C:用に Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートを追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md)   
 [手順 3 D:用に Sw:HandleResponse メッセージをキャプチャする FILE 送信ポートを追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)