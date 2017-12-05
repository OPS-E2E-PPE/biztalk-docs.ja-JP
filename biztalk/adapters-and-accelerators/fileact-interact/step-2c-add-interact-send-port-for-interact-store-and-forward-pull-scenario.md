---
title: "手順 2 C: InterAct ストア アンド フォワード (プル) シナリオの対話の送信ポートを追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57038f77-85c3-4811-ab3d-df6e2da8fbcf
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb46943b20676dbe98f79db8760043bb51606c56
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-2c-add-an-interact-send-port-for-the-interact-store-and-forward-pull-scenario"></a>手順 2 C: InterAct ストア アンド フォワード (プル) シナリオの対話の送信ポートを追加
この手順を開始する前に行う必要があります[Step 2B: InterAct ストア アンド フォワード (プル) シナリオの Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)です。  
  
### <a name="to-add-an-interact-send-port"></a>対話する送信ポートを追加するには  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。  
  
3.  右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。  
  
4.  **送信ポートのプロパティ**ウィンドウで、名前、送信ポートを**Tutorial_IA_SendRequest_SnF**です。  
  
5.  **送信ポートのプロパティ** ウィンドウから、**トランスポートの種類**ドロップダウン リストで、 **INTERACT**、順にクリック**構成**です。  
  
6.  **トランスポートのプロパティの対話** ダイアログ ボックスで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**Password**|SAG 接続適切なパスワードを設定します。|  
    |**ユーザー名**|SAG 接続を適切なユーザー名を設定します。|  
    |**メッセージの形式**|**InteractMessage**|  
    |**否認不可インジケーター**|**FALSE**|  
    |**要求の種類**|適切な入力\<RequestType\> SWIFT でのプロビジョニングに基づく文字列。|  
    |**ResponseCrypto**|**FALSE**|  
    |**要求元**|適切な入力\<RequestorDN\> SWIFT でのプロビジョニングに基づく文字列。|  
    |**応答側**|適切な入力\<ResponderDN\> SWIFT でのプロビジョニングに基づく文字列。|  
    |**サービス名**|適切な入力\<サービス名\>SWIFT でのプロビジョニングに基づきます。|  
    |**配信通知**|ドロップダウン リストから選択**FALSE**です。|  
    |**通知キュー**|SWIFT でのプロビジョニングに基づく、適切なキュー名を入力します。|  
  
    > [!NOTE]
    >  ペイロードは、転送するのには、専用の場合は、ポートと対話する送信ポートが受信の対話で「ペイロード」に MessageFormat を設定します。 PassThru に、受信パイプラインと送信パイプラインを設定します。  
  
7.  **[OK]**をクリックします。  
  
8.  **送信ポートのプロパティ** ウィンドウで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**送信ハンドラー**|ドロップダウン リストから、対話ホストを選択します。|  
    |**送信パイプライン**|ドロップダウン リストから選択**XMLTransmit**です。|  
    |**受信パイプライン**|ドロップダウン リストから選択**XMLReceive**です。|  
  
9. **送信ポートのプロパティ** ウィンドウで、**フィルター**  タブで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**プロパティ**|ドロップダウン リストから選択**BTS です。ReceivePortName**です。|  
    |**演算子**|ドロップダウン リストから選択 **==**です。|  
    |**値**|型**Tutorial_IA_InputRequest_SnF**です。|  
    |**グループ化**|既定値を使用します。|  
  
10. **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [手順 2 a: ファイルの受信場所 InterAct ストア アンド フォワード (プル) シナリオの追加](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md)   
 [手順 2B: InterAct ストア アンド フォワード (プル) シナリオ用に Sw:HandleRequest メッセージをキャプチャするためにファイルの送信ポートを追加する](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)