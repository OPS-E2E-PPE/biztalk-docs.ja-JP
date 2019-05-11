---
title: 手順 3 b:INTERACT の受信場所を追加、InterAct リアルタイム シナリオ |Microsoft Docs
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
ms.openlocfilehash: 7f5bb27dc2ff57df0a821cc64e3f26349c278601
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365659"
---
# <a name="step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario"></a>手順 3 b:INTERACT の受信場所を追加、InterAct リアルタイム シナリオ
完全な[手順 3 a:操作のリアルタイム シナリオ用のファイルの受信場所の追加](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md)この手順を開始する前にします。
  
## <a name="add-an-interact-receive-location"></a>INTERACT の受信場所を追加します。  
  
1.  開始**BizTalk Server 管理**します。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションを順に展開します。  
  
3.  右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート。**  
  
4.  **受信ポートのプロパティ**ウィンドウで、受信ポート名**Tutorial_IA_HandleRequestOneWay_RealTime**します。  
  
5.  **受信ポートのプロパティ**ウィンドウで、**受信場所**] タブで [**新規**します。  
  
6.  **受信場所のプロパティ**ウィンドウの**全般** タブから、**トランスポートの種類**ドロップダウン リストで、 **INTERACT**、クリックして**構成**します。  
  
7.  **トランスポートのプロパティの対話** ダイアログ ボックスで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**Password**|SAG への接続に使用するパスワードを入力します。 詳細については、SAG ヘルプを参照してください。|  
    |**ユーザー名**|SAG への接続に使用するユーザー名を入力します。|  
    |**アプリケーション名**|サーバーの入力\<*アプリケーション インターフェイス名*\> SAG のボックス ルーティング セット。|  
    |**暗号モード**|ドロップダウン リストから選択**詳細**します。|  
    |**LogMessageBody**|ドロップダウン リストから選択**FALSE**します。 **注:** TRUE に設定した場合は、追跡データベースにメッセージ本文を保持します。 ただし、セキュリティ上の理由から、メッセージ本文は、BAM ポータルでは表示ことはありませんすることができます。|  
    |**し**|ドロップダウン リストから選択**TRUE**します。 これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。|  
    |**メッセージの形式**|ドロップダウン リストから選択**InterActMessage**します。|  
    |**MemberRef**|ドロップダウン リストから選択**ResponseHeader**します。|  
    |**否認不可のインジケーター**|ドロップダウン リストから選択**FALSE**します。|  
    |**応答側**|適切な入力\< *ResponderDN* \> SWIFT で、プロビジョニングに基づく文字列。|  
    |**ResponseCrypto**|ドロップダウン リストから選択**FALSE**します。|  
    |**Timeout**|接続タイムアウトの秒数が適切な型が発生する必要があります。|  
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
 [ステップ 3:作成する送信と受信ポートを InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md)   
 [手順 3 a:ファイル受信場所を追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md)   
 [手順 3 C:用に Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートを追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md)   
 [手順 3 D:用に Sw:HandleResponse メッセージをキャプチャする FILE 送信ポートを追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)   
 [手順 3 e:用の INTERACT 送信ポートを追加、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)