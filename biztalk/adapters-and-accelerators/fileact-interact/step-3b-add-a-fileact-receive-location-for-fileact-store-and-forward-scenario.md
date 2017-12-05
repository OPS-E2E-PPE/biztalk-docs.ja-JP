---
title: "手順 3 b: FILEACT の受信場所が FileAct ストア アンド フォワードのシナリオの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f30bb7d-1efb-4350-8809-be35f5634ea0
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9357c172ff538bce73d3618739f3db4f98141814
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-3b-add-a-fileact-receive-location-for-the-fileact-store-and-forward-scenario"></a>手順 3 b: FILEACT の受信場所が FileAct ストア アンド フォワードのシナリオを追加
この手順を開始する前に行う必要があります[手順 3A: FileAct ストア アンド フォワードのシナリオのファイルの受信場所を追加](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md)です。  
  
### <a name="to-add-an-fileact-receive-location"></a>FILEACT、受信場所を追加するには  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションの順に展開します。  
  
3.  右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート。**  
  
4.  **受信ポートのプロパティ**ウィンドウで、受信ポート名 Tutorial_FA_HandleRequestOneWay_SnF です。  
  
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
    |**FileCompression**|ドロップダウン リストから [なし] を選択します。|  
    |**PhysicalFolderName**|サーバー上のフォルダーの名前を入力します。 たとえば、C:\Fileact\ServerLocation です。|  
    |**SubscribeFileEvents**|ドロップダウン リストから選択**FALSE**です。|  
    |**TransferAnswer**|ドロップダウン リストから選択**Accepted**です。|  
    |**AllFileEvents**|ドロップダウン リストから選択**TRUE**です。|  
    |**イベントのエンドポイント**|適切な SAG エンドポイントを入力します。|  
    |**FullFileStatus**|ドロップダウン リストから選択**TRUE**です。|  
    |**Timeout**|適切なタイムアウトが発生するまでの秒数を入力します。|  
    |**キューを取得します。**|SWIFT でのプロビジョニングに基づく、キュー名を入力します。|  
    |**ForceAcquire**|ドロップダウン リストから選択**TRUE**です。|  
    |**Order by**|ドロップダウン リストから選択**FileAct**です。|  
    |**プッシュ セッション**|ドロップダウン リストから選択**TRUE**です。|  
    |**回復モード**|ドロップダウン リストから選択**FALSE**です。|  
    |**SNL エンドポイント**|SAG ルーティング セットの適切なエンドポイントを入力します。 この値は、SAG で構成されている SnL エンドポイントと一致する必要があります。|  
  
8.  **[OK]**をクリックします。  
  
9. **受信場所のプロパティ** ウィンドウで、**全般** タブで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**受信ハンドラー**|ドロップダウン リストから選択**BizTalkServerIsolatedHost**です。|  
    |**受信パイプライン**|ドロップダウン リストから選択**XMLReceive**です。|  
  
10. **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [手順 3: 送信ポートを作成し、FileAct ストア アンド フォワードのシナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md)   
 [手順 3: ファイルの受信場所が FileAct ストア アンド フォワードのシナリオを追加](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md)   
 [手順 3 C: Sw:HandleFileRequest と Sw:HandleSnFRequest FileAct ストア アンド フォワードのシナリオについてメッセージをキャプチャする FILE 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md)   
 [手順 3D: FileAct ストア アンド フォワード シナリオ用に FILEACT 送信ポートを追加する](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)