---
title: '手順 3 b: FILEACT の受信場所が FileAct リアルタイム シナリオの追加 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e086c86-1525-4cef-b7e5-a66e14bd8d4f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ea9d5e9cab7cedf0a4d83ac19b2e241f6776209
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965824"
---
# <a name="step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario"></a>手順 3 b: FILEACT の受信場所が FileAct リアルタイム シナリオの追加
この手順を開始する前に行う必要があります[手順 3A: FileAct リアルタイム シナリオでは、ファイルの受信場所を追加](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md)です。  
  
### <a name="to-add-a-fileact-receive-location"></a>FILEACT、受信場所を追加するには  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションの順に展開します。  
  
3.  右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート。**  
  
4.  **受信ポートのプロパティ**ウィンドウで、受信ポート名 Tutorial_FA_HandleRequestOneWay_RealTime です。  
  
5.  **受信ポートのプロパティ** ウィンドウで、**受信場所** タブで、をクリックして**新規**です。  
  
6.  **受信場所のプロパティ**ウィンドウで、**全般** タブから、**トランスポートの種類**ドロップダウン リストで、 **FILEACT**とをクリックして**構成**です。  
  
7.  **FILEACT トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**Password**|SAG への接続に使用するパスワードを入力します。 詳細については、SAG のヘルプを参照してください。|  
    |**ユーザー名**|SAG への接続に使用するユーザー名を入力します。|  
    |**アプリケーション名**|サーバーを入力\<アプリケーション インターフェイス名\>SAG のボックス ルーティング セット。|  
    |**暗号化モード**|ドロップダウン リストから選択**詳細**です。|  
    |**FACrypto モード**|ドロップダウン リストから選択**詳細**です。|  
    |**し**|ドロップダウン リストから選択**TRUE**です。 これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。|  
    |**MemberRef**|ドロップダウン リストから選択**ResponsePayload**です。|  
    |**否認不可インジケーター**|ドロップダウン リストから選択**FALSE**です。|  
    |**応答側**|適切な入力\<レスポンダー\> SWIFT でのプロビジョニングに基づく文字列。|  
    |**ResponseCrypto**|ドロップダウン リストから選択**FALSE**です。|  
    |**受信確認のインジケーター**|ドロップダウン リストから選択**ResponsePayload**です。|  
    |**FileCompression**|ドロップダウン リストから選択**None**です。|  
    |**PhysicalFolderName**|サーバー上のフォルダーの名前を入力します。 たとえば、C:\Fileact\ServerLocation です。|  
    |**SubscribeFileEvents**|ドロップダウン リストから選択**FALSE**です。|  
    |**TransferAnswer**|ドロップダウン リストから選択**Accepted**です。|  
    |**AllFileEvents**|ドロップダウン リストから選択**TRUE**です。|  
    |**イベントのエンドポイント**|SAG ルーティング セットの適切なエンドポイントを入力します。 この値は、SAG で構成されている SnL エンドポイントと一致する必要があります。|  
    |**FullFileStatus**|ドロップダウン リストから選択**TRUE**です。|  
    |**Timeout**|適切なタイムアウトが発生するまでの秒数を入力します。|  
    |**キューを取得します。**|このプロパティの既定値のままにします。 このプロパティは、ストア アンド フォワードのシナリオに使用されます。|  
    |**ForceAcquire**|このプロパティの既定値のままにします。 このプロパティは、ストア アンド フォワードのシナリオに使用されます。|  
    |**Order by**|このプロパティの既定値のままにします。 このプロパティは、ストア アンド フォワードのシナリオに使用されます。|  
    |**プッシュ セッション**|このプロパティの既定値のままにします。 このプロパティは、ストア アンド フォワードのシナリオに使用されます。|  
    |**回復モード**|このプロパティの既定値のままにします。 このプロパティは、ストア アンド フォワードのシナリオに使用されます。|  
    |**SNL エンドポイント**|このプロパティの既定値のままにします。 このプロパティは、ストア アンド フォワードのシナリオに使用されます。|  
  
8.  **[OK]** をクリックします。  
  
9. **受信場所のプロパティ** ウィンドウで、**全般** タブで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**受信ハンドラー**|ドロップダウン リストから選択**BizTalkServerIsolatedHost**です。|  
    |**受信パイプライン**|ドロップダウン リストから選択**XMLReceive**です。|  
  
10. **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [手順 3: 送信ポートを作成し、FileAct リアルタイムのシナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md)   
 [手順 3: ファイルの受信場所、FileAct リアルタイムのシナリオの追加](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md)   
 [手順 3 C: FileAct リアルタイム シナリオ Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md)   
 [ステップ 3 D: FileAct リアルタイム シナリオ FILEACT 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md)   
 [手順 3E: FileAct リアルタイム シナリオ用に Sw:ExchangeFileResponse メッセージをキャプチャするためにファイルの送信ポートを追加する](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)