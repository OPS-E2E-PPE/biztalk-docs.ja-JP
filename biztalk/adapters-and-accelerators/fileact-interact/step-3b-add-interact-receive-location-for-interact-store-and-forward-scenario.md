---
title: "手順 3 b: 対話の受信場所が、対話ストアと転送シナリオの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: da077518-b2ee-4b5f-88d0-fe73af2baa7a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e9aa8e153cf510f2d24cbe30a62317d26810e4a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-3b-add-an-interact-receive-location-for-the-interact-store-and-forward-scenario"></a>手順 3 b: 追加、対話の受信場所が、対話ストアと転送シナリオ
完全な[手順 3A: InterAct ストア アンド フォワードのシナリオのファイルの受信場所を追加](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md)この手順を開始する前にします。
  
## <a name="add-an-interact-receive-location"></a>受信場所が、対話を追加します。  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションの順に展開します。  
  
3.  右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート。**  
  
4.  **受信ポートのプロパティ**ウィンドウで、受信ポート名 Tutorial_IA_HandleRequestOneWay_SnF です。  
  
5.  **受信ポートのプロパティ** ウィンドウで、**受信場所** タブで、をクリックして**新規**です。  
  
6.  **受信場所のプロパティ**ウィンドウの**全般** タブから、**トランスポートの種類**ドロップダウン リストで、 **INTERACT**、クリックして**構成**です。  
  
7.  **トランスポートのプロパティの対話** ダイアログ ボックスで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**Password**|SAG への接続に使用するパスワードを入力します。 詳細については、SAG のヘルプを参照してください。|  
    |**ユーザー名**|SAG への接続に使用するユーザー名を入力します。|  
    |**アプリケーション名**|サーバーを入力\<アプリケーション インターフェイス名\>SAG のボックス ルーティング セット。|  
    |**暗号化モード**|ドロップダウン リストから選択**詳細**です。|  
    |**LogMessageBody**|ドロップダウン リストから選択**FALSE**です。 **注:**を TRUE に設定する場合、BizTalk 追跡データベースでメッセージ本文が保持されます。 ただし、セキュリティ上の理由から、メッセージの本文見なすことができることはありません、BAM ポータルにします。|  
    |**し**|ドロップダウン リストから選択**TRUE**です。 これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。|  
    |**メッセージの形式**|ドロップダウン リストから選択**InterActMessage**です。|  
    |**MemberRef**|ドロップダウン リストから選択**ResponseHeader**です。|  
    |**否認不可インジケーター**|ドロップダウン リストから選択**FALSE**です。|  
    |**応答側**|適切な入力\<レスポンダー\> SWIFT でのプロビジョニングに基づく文字列。|  
    |**ResponseCrypto**|ドロップダウン リストから選択**FALSE**です。|  
    |**Timeout**|適切なタイムアウトが発生するまでの秒数を入力します。|  
    |**キューを取得します。**|SWIFT でのプロビジョニングに基づく、キュー名を入力します。|  
    |**ForceAcquire**|ドロップダウン リストから選択**TRUE**です。|  
    |**Order by**|ドロップダウン リストから選択**Interact**です。|  
    |**プッシュ セッション**|ドロップダウン リストから選択**TRUE**です。|  
    |**回復モード**|ドロップダウン リストから選択**TRUE**です。|  
    |**SNL エンドポイント**|SAG ルーティング セットの適切なエンドポイントを入力します。 この値は、SAG で構成されている SnL エンドポイントと一致する必要があります。|  
  
8.  **[OK]**をクリックします。  
  
9. **受信場所のプロパティ** ウィンドウで、**全般** タブで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**受信ハンドラー**|ドロップダウン リストから選択**BizTalkServerIsolatedHost**です。|  
    |**受信パイプライン**|ドロップダウン リストから選択**XMLReceive**です。|  
  
10. **[OK]**をクリックします。  
  
## <a name="complete-steps"></a>詳細な手順
 [手順 3: 送信ポートを作成し、対話ストアと転送シナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [手順 3: ファイルの受信場所が、対話ストアと転送シナリオの追加](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md)   
 [手順 3C: InterAct ストア アンド フォワード シナリオ用に Sw:HandleRequest メッセージをキャプチャするためにファイルの送信ポートを追加する](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)  
 [手順 3D: InterAct ストア アンド フォワード シナリオ用に INTERACT 送信ポートを追加する](../../adapters-and-accelerators/fileact-interact/step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario.md)