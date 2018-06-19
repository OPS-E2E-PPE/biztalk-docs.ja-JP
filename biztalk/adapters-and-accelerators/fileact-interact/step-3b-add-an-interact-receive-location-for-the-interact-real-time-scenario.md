---
title: '手順 3 b: 対話の受信場所を追加、リアルタイムのシナリオを対話 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59780635-e1b6-4e74-a89a-73ec26d6c670
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa1a98f97cba9f46b43b92128a6585ad18afb894
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966304"
---
# <a name="step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario"></a>手順 3 b: 対話の受信場所を追加、リアルタイムのシナリオの対話
完全な[手順 3A: 対話リアルタイム シナリオではファイルの受信場所を追加](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md)この手順を開始する前にします。
  
## <a name="add-an-interact-receive-location"></a>受信場所が、対話を追加します。  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションの順に展開します。  
  
3.  右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート。**  
  
4.  **受信ポートのプロパティ**ウィンドウで、受信ポート名**Tutorial_IA_HandleRequestOneWay_RealTime**です。  
  
5.  **受信ポートのプロパティ** ウィンドウで、**受信場所** タブで、をクリックして**新規**です。  
  
6.  **受信場所のプロパティ**ウィンドウの**全般** タブから、**トランスポートの種類**ドロップダウン リストで、 **INTERACT**、クリックして**構成**です。  
  
7.  **トランスポートのプロパティの対話** ダイアログ ボックスで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**Password**|SAG への接続に使用するパスワードを入力します。 詳細については、SAG のヘルプを参照してください。|  
    |**ユーザー名**|SAG への接続に使用するユーザー名を入力します。|  
    |**アプリケーション名**|サーバーを入力\<*アプリケーション インターフェイス名*\> SAG のボックス ルーティング セット。|  
    |**暗号化モード**|ドロップダウン リストから選択**詳細**です。|  
    |**LogMessageBody**|ドロップダウン リストから選択**FALSE**です。 **注:** を TRUE に設定する場合、追跡データベースにメッセージ本文が保持されます。 ただし、セキュリティ上の理由から、メッセージの本文見なすことができることはありません、BAM ポータルにします。|  
    |**し**|ドロップダウン リストから選択**TRUE**です。 これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。|  
    |**メッセージの形式**|ドロップダウン リストから選択**InterActMessage**です。|  
    |**MemberRef**|ドロップダウン リストから選択**ResponseHeader**です。|  
    |**否認不可インジケーター**|ドロップダウン リストから選択**FALSE**です。|  
    |**応答側**|適切な入力\< *ResponderDN* \> SWIFT でのプロビジョニングに基づく文字列。|  
    |**ResponseCrypto**|ドロップダウン リストから選択**FALSE**です。|  
    |**Timeout**|適切な接続がタイムアウトするまでの秒数の種類に発生する必要があります。|  
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
 [手順 3: が送信を作成し、受信のポート、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md)   
 [手順 3: ファイルの受信場所を追加、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md)   
 [手順 3 C: の Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートを追加、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md)   
 [ステップ 3 D: の Sw:HandleResponse メッセージをキャプチャする FILE 送信ポートを追加、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)   
 [手順 3E: InterAct リアルタイム シナリオ用に INTERACT 送信ポートを追加する](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)