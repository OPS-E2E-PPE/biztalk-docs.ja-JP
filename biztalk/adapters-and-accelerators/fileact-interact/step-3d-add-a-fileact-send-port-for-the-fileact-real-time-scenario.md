---
title: 'ステップ 3 D: FileAct リアルタイム シナリオ FILEACT 送信ポートの追加 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a22ba41-4f43-4fbb-92f7-a0fd7558d2ce
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f7440a0bad39fbfddb6319f4051a397f08ac09f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966376"
---
# <a name="step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario"></a>ステップ 3 D: FileAct リアルタイム シナリオ FILEACT 送信ポートの追加
この手順を開始する前に行う必要があります[手順 3 C: Sw:HandleRequest メッセージのキャプチャに FileAct リアルタイム シナリオでは、ファイル送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md)です。  
  
### <a name="to-add-a-fileact-send-port"></a>FILEACT 送信ポートを追加するには  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。  
  
3.  右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。  
  
4.  **送信ポートのプロパティ**ウィンドウで、名前、送信ポートを Tutorial_FA_SendRequest_RealTime です。  
  
5.  **送信ポートのプロパティ** ウィンドウから、**トランスポートの種類**ドロップダウン リストで、 **FILEACT**、順にクリック**構成**です。  
  
6.  **FILEACT トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**Password**|SAG 接続適切なパスワードを設定します。|  
    |**ユーザー名**|SAG 接続を適切なユーザー名を設定します。|  
    |**アダプターのモード**|ドロップダウン リストから選択**ストア アンド フォワード**です。|  
    |**否認不可インジケーター**|ドロップダウン リストから選択**FALSE**です。|  
    |**要求の種類**|適切な設定\<RequestType\> SWIFT でのプロビジョニングに基づく文字列。|  
    |**ResponseCrypto**|ドロップダウン リストから選択**FALSE**です。|  
    |**要求元**|適切な設定\<リクエスター\> SWIFT でのプロビジョニングに基づく文字列。|  
    |**応答側**|適切な設定\<レスポンダー\> SWIFT でのプロビジョニングに基づいて文字列。|  
    |**サービス名**|適切な設定\<サービス名\>SWIFT でのプロビジョニングに基づいています。|  
    |**受信確認のインジケーター**|ドロップダウン リストから選択**FALSE**です。|  
    |**イベントのエンドポイント**|ドロップダウン リストから選択**FALSE**です。|  
    |**ファイルの圧縮**|ドロップダウン リストから選択**None**です。|  
    |**物理的なフォルダー名**|C:\SWIFTAdapterTutorial\Fileact\ClientLocation を入力します。|  
    |**エンドポイントを転送します。**|SAG ルーティング セットの適切なエンドポイントを入力します。 この値は、SAG で構成されている SnL エンドポイントと一致する必要があります。|  
    |**ServiceProfile**|ドロップダウン リストから選択**トランザクション カウント**です。|  
    |**配信通知**|ドロップダウン リストから選択**FALSE**です。|  
    |**通知キュー**|SWIFT でのプロビジョニングに基づく、キュー名を入力します。|  
  
    > [!NOTE]
    >  メッセージでのトランザクション数を転送する場合は、サービスのプロファイルでモードを設定「トランザクション数」に、FileAct 送信ポート。  
  
7.  **[OK]** をクリックします。  
  
8.  **送信ポートのプロパティ** ウィンドウで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**送信ハンドラー**|ドロップダウン リストから、Fileact ホストを選択します。|  
    |**送信パイプライン**|ドロップダウン リストから選択**XMLTransmit**です。|  
    |**受信パイプライン**|ドロップダウン リストから選択**XMLReceive**です。|  
  
9. 送信ポートのプロパティ ウィンドウで、**フィルター**  タブで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**プロパティ**|ドロップダウン リストから選択**BTS です。ReceivePortName**です。|  
    |**演算子**|ドロップダウン リストから選択 **==** です。|  
    |**値**|型 Tutorial_FA_InputRequest_RealTime です。|  
    |**グループ化**|既定値を使用します。|  
  
10. **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [手順 3: 送信ポートを作成し、FileAct リアルタイムのシナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md)   
 [手順 3: ファイルの受信場所、FileAct リアルタイムのシナリオの追加](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md)   
 [手順 3 b: FILEACT の受信場所が FileAct リアルタイム シナリオの追加](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md)   
 [手順 3 C: FileAct リアルタイム シナリオ Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md)   
 [手順 3E: FileAct リアルタイム シナリオ用に Sw:ExchangeFileResponse メッセージをキャプチャするためにファイルの送信ポートを追加する](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)