---
title: 手順 3 b:FileAct リアルタイム シナリオ用の場所に、FILEACT の受信の追加 |Microsoft Docs
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
ms.openlocfilehash: 9b4e02b94e567ad80cafc858ce347f2007d8913c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365652"
---
# <a name="step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario"></a>手順 3 b:FileAct リアルタイム シナリオ用の場所に、FILEACT の受信を追加します。
この手順を開始する前に行う必要があります[手順 3 a:ファイル受信 FileAct リアルタイム シナリオ用の場所を追加](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md)します。  
  
### <a name="to-add-a-fileact-receive-location"></a>FILEACT の受信場所を追加するには  
  
1.  開始**BizTalk Server 管理**します。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションを順に展開します。  
  
3.  右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート。**  
  
4.  **受信ポートのプロパティ**ウィンドウで、名前、受信ポート Tutorial_FA_HandleRequestOneWay_RealTime します。  
  
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
    |**FileCompression**|ドロップダウン リストから選択**None**します。|  
    |**PhysicalFolderName**|サーバー上のフォルダーの名前を入力します。 たとえば、C:\Fileact\ServerLocation です。|  
    |**SubscribeFileEvents**|ドロップダウン リストから選択**FALSE**します。|  
    |**TransferAnswer**|ドロップダウン リストから選択**Accepted**します。|  
    |**AllFileEvents**|ドロップダウン リストから選択**TRUE**します。|  
    |**イベントのエンドポイント**|SAG ルーティング セットの適切なエンドポイントを入力します。 この値は、SAG で構成した SnL エンドポイントと一致する必要があります。|  
    |**FullFileStatus**|ドロップダウン リストから選択**TRUE**します。|  
    |**Timeout**|適切なタイムアウトが発生するまでの秒数を入力します。|  
    |**キューを取得します。**|このプロパティの既定値のままにします。 このプロパティは、ストア アンド フォワード シナリオ用に使用されます。|  
    |**ForceAcquire**|このプロパティの既定値のままにします。 このプロパティは、ストア アンド フォワード シナリオ用に使用されます。|  
    |**並べ替え**|このプロパティの既定値のままにします。 このプロパティは、ストア アンド フォワード シナリオ用に使用されます。|  
    |**プッシュ セッション**|このプロパティの既定値のままにします。 このプロパティは、ストア アンド フォワード シナリオ用に使用されます。|  
    |**回復モード**|このプロパティの既定値のままにします。 このプロパティは、ストア アンド フォワード シナリオ用に使用されます。|  
    |**SNL エンドポイント**|このプロパティの既定値のままにします。 このプロパティは、ストア アンド フォワード シナリオ用に使用されます。|  
  
8.  **[OK]** をクリックします。  
  
9. **受信場所のプロパティ**ウィンドウの**全般** タブで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**受信ハンドラー**|ドロップダウン リストから選択**BizTalkServerIsolatedHost**します。|  
    |**受信パイプライン**|ドロップダウン リストから選択**XMLReceive**します。|  
  
10. **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [ステップ 3:送信ポートを作成および FileAct リアルタイム シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md)   
 [手順 3 a:ファイル受信 FileAct リアルタイム シナリオ用の場所を追加します。](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md)   
 [手順 3 C:FileAct リアルタイム シナリオ用に Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加します。](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md)   
 [手順 3 D:FileAct リアルタイム シナリオ用に FILEACT 送信ポートを追加します。](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md)   
 [手順 3 e:FileAct リアルタイム シナリオ用に Sw:ExchangeFileResponse メッセージをキャプチャする FILE 送信ポートの追加します。](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)