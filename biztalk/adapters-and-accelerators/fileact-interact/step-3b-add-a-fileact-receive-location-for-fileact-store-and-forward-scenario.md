---
title: 手順 3 b:FileAct ストア アンド フォワード シナリオ用の場所に、FILEACT の受信の追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f30bb7d-1efb-4350-8809-be35f5634ea0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7879dacb4aab2e2d14ec4a00025569484fc52d57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365721"
---
# <a name="step-3b-add-a-fileact-receive-location-for-the-fileact-store-and-forward-scenario"></a>手順 3 b:FileAct ストア アンド フォワード シナリオ用の場所に、FILEACT の受信を追加します。
この手順を開始する前に行う必要があります[手順 3 a:FileAct ストア アンド フォワード シナリオ用の場所の受信ファイルを追加する](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md)します。  
  
### <a name="to-add-an-fileact-receive-location"></a>FILEACT の受信場所を追加するには  
  
1.  開始**BizTalk Server 管理**します。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションを順に展開します。  
  
3.  右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート。**  
  
4.  **受信ポートのプロパティ**ウィンドウで、名前、受信ポート Tutorial_FA_HandleRequestOneWay_SnF します。  
  
5.  **受信ポートのプロパティ**ウィンドウで、**受信場所**] タブで [**新規**します。  
  
6.  **受信場所のプロパティ**ウィンドウの**全般** タブから、**トランスポートの種類**ドロップダウン リストで、 **FILEACT**とクリックして**構成**します。  
  
7.  **FILEACT トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**Password**|SAG への接続に使用するパスワードを入力します。 詳細については、SAG ヘルプを参照してください。|  
    |**ユーザー名**|SAG への接続に使用するユーザー名を入力します。|  
    |**アプリケーション名**|サーバーの入力\<アプリケーション インターフェイス名\>SAG のボックス ルーティング セット。|  
    |**暗号モード**|ドロップダウン リストから選択**詳細**します。|  
    |**FACrypto モード**|ドロップダウン リストから選択**詳細**します。|  
    |**し**|ドロップダウン リストから選択**TRUE**します。 これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。|  
    |**MemberRef**|ドロップダウン リストから選択**ResponsePayload**します。|  
    |**否認不可のインジケーター**|ドロップダウン リストから選択**FALSE**します。|  
    |**応答側**|適切な入力\<レスポンダー\> SWIFT で、プロビジョニングに基づく文字列。|  
    |**ResponseCrypto**|ドロップダウン リストから選択**FALSE**します。|  
    |**受信確認のインジケーター**|ドロップダウン リストから選択**ResponsePayload**します。|  
    |**FileCompression**|ドロップダウン リストから [なし] を選択します。|  
    |**PhysicalFolderName**|サーバー上のフォルダーの名前を入力します。 たとえば、C:\Fileact\ServerLocation です。|  
    |**SubscribeFileEvents**|ドロップダウン リストから選択**FALSE**します。|  
    |**TransferAnswer**|ドロップダウン リストから選択**Accepted**します。|  
    |**AllFileEvents**|ドロップダウン リストから選択**TRUE**します。|  
    |**イベントのエンドポイント**|適切な SAG エンドポイントを入力します。|  
    |**FullFileStatus**|ドロップダウン リストから選択**TRUE**します。|  
    |**Timeout**|適切なタイムアウトが発生するまでの秒数を入力します。|  
    |**キューを取得します。**|SWIFT で、プロビジョニングに基づく、キュー名を入力します。|  
    |**ForceAcquire**|ドロップダウン リストから選択**TRUE**します。|  
    |**並べ替え**|ドロップダウン リストから選択**FileAct**します。|  
    |**プッシュ セッション**|ドロップダウン リストから選択**TRUE**します。|  
    |**回復モード**|ドロップダウン リストから選択**FALSE**します。|  
    |**SNL エンドポイント**|SAG ルーティング セットの適切なエンドポイントを入力します。 この値は、SAG で構成した SnL エンドポイントと一致する必要があります。|  
  
8.  **[OK]** をクリックします。  
  
9. **受信場所のプロパティ**ウィンドウの**全般** タブで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**受信ハンドラー**|ドロップダウン リストから選択**BizTalkServerIsolatedHost**します。|  
    |**受信パイプライン**|ドロップダウン リストから選択**XMLReceive**します。|  
  
10. **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [ステップ 3:送信ポートを作成し、受信 FileAct ストア アンド フォワード シナリオ用のポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md)   
 [手順 3 a:FileAct ストア アンド フォワード シナリオ用の場所の受信ファイルを追加します。](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md)   
 [手順 3 C:FileAct ストア アンド フォワード シナリオ用 Sw:HandleFileRequest および Sw:HandleSnFRequest メッセージをキャプチャする FILE 送信ポートの追加します。](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md)   
 [手順 3 D:FileAct ストア アンド フォワード シナリオ用 FILEACT 送信ポートの追加します。](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)