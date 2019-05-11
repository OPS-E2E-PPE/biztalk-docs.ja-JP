---
title: 手順 3 b:INTERACT の受信場所 InterAct ストア アンド フォワード シナリオ用の追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: da077518-b2ee-4b5f-88d0-fe73af2baa7a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dd50d40c033fa319e2690ea1a3c6773f694bec5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365634"
---
# <a name="step-3b-add-an-interact-receive-location-for-the-interact-store-and-forward-scenario"></a>手順 3 b:INTERACT の受信場所 InterAct ストア アンド フォワード シナリオ用の追加します。
完全な[手順 3 a:InterAct ストア アンド フォワード シナリオ用のファイルの受信場所を追加](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md)この手順を開始する前にします。
  
## <a name="add-an-interact-receive-location"></a>INTERACT の受信場所を追加します。  
  
1.  開始**BizTalk Server 管理**します。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションを順に展開します。  
  
3.  右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート。**  
  
4.  **受信ポートのプロパティ**ウィンドウで、名前、受信ポート Tutorial_IA_HandleRequestOneWay_SnF します。  
  
5.  **受信ポートのプロパティ**ウィンドウで、**受信場所**] タブで [**新規**します。  
  
6.  **受信場所のプロパティ**ウィンドウの**全般** タブから、**トランスポートの種類**ドロップダウン リストで、 **INTERACT**、クリックして**構成**します。  
  
7.  **トランスポートのプロパティの対話** ダイアログ ボックスで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**Password**|SAG への接続に使用するパスワードを入力します。 詳細については、SAG ヘルプを参照してください。|  
    |**ユーザー名**|SAG への接続に使用するユーザー名を入力します。|  
    |**アプリケーション名**|サーバーの入力\<アプリケーション インターフェイス名\>SAG のボックス ルーティング セット。|  
    |**暗号モード**|ドロップダウン リストから選択**詳細**します。|  
    |**LogMessageBody**|ドロップダウン リストから選択**FALSE**します。 **注:** TRUE に設定した場合は、BizTalk 追跡データベースでメッセージの本文を保持します。 ただし、セキュリティ上の理由から、メッセージ本文は、BAM ポータルでは表示ことはありませんすることができます。|  
    |**し**|ドロップダウン リストから選択**TRUE**します。 これにより、メッセージ イベントをキャプチャし、BAM ポータルで追跡できます。|  
    |**メッセージの形式**|ドロップダウン リストから選択**InterActMessage**します。|  
    |**MemberRef**|ドロップダウン リストから選択**ResponseHeader**します。|  
    |**否認不可のインジケーター**|ドロップダウン リストから選択**FALSE**します。|  
    |**応答側**|適切な入力\<レスポンダー\> SWIFT で、プロビジョニングに基づく文字列。|  
    |**ResponseCrypto**|ドロップダウン リストから選択**FALSE**します。|  
    |**Timeout**|適切なタイムアウトが発生するまでの秒数を入力します。|  
    |**キューを取得します。**|SWIFT で、プロビジョニングに基づく、キュー名を入力します。|  
    |**ForceAcquire**|ドロップダウン リストから選択**TRUE**します。|  
    |**並べ替え**|ドロップダウン リストから選択**Interact**します。|  
    |**プッシュ セッション**|ドロップダウン リストから選択**TRUE**します。|  
    |**回復モード**|ドロップダウン リストから選択**TRUE**します。|  
    |**SNL エンドポイント**|SAG ルーティング セットの適切なエンドポイントを入力します。 この値は、SAG で構成した SnL エンドポイントと一致する必要があります。|  
  
8.  **[OK]** をクリックします。  
  
9. **受信場所のプロパティ**ウィンドウの**全般** タブで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**受信ハンドラー**|ドロップダウン リストから選択**BizTalkServerIsolatedHost**します。|  
    |**受信パイプライン**|ドロップダウン リストから選択**XMLReceive**します。|  
  
10. **[OK]** をクリックします。  
  
## <a name="complete-steps"></a>手順を完了します
 [ステップ 3:送信ポートの作成し、InterAct ストア アンド フォワード シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [手順 3 a:InterAct ストア アンド フォワード シナリオ用の場所の受信ファイルを追加します。](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md)   
 [手順 3 C:InterAct ストア アンド フォワード シナリオ用に Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加します。](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)  
 [手順 3 D:InterAct ストア アンド フォワード シナリオ用に INTERACT 送信ポートを追加します。](../../adapters-and-accelerators/fileact-interact/step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario.md)