---
title: 手順 2 C:FileAct ストア アンド フォワード (プル) シナリオに FILEACT 送信ポートの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8743a868-9625-477b-a7da-673bfa262723
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac2579d61aa20db0dcb445b30ebac1bb429221cd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366029"
---
# <a name="step-2c-add-a-fileact-send-port-for-the-fileact-store-and-forward-pull-scenario"></a>手順 2 C:FileAct ストア アンド フォワード (プル) シナリオに FILEACT 送信ポートの追加します。
この手順を開始する前に行う必要があります[手順 2 b:ファイル送信ポート、Sw:HandleFileRequest のキャプチャを追加および Sw:HandleSnFRequest メッセージを FileAct ストア アンド フォワード (プル) シナリオ](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md)します。  
  
### <a name="to-add-a-fileact-send-port"></a>FileACT 送信ポートを追加するには  
  
1.  開始**BizTalk Server 管理**します。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを順に展開します。  
  
3.  右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な送信請求-応答送信ポート**します。  
  
4.  **送信ポートのプロパティ**ウィンドウで、送信ポート名**Tutorial_FA_SendRequest_SnF**します。  
  
5.  **送信ポートのプロパティ**ウィンドウから、**トランスポートの種類**ドロップダウン リストで、 **FILEACT**、 をクリックし、**構成**。  
  
6.  **FILEACT トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**Password**|SAG 接続に応じて、パスワードを設定します。|  
    |**ユーザー名**|SAG 接続用の適切なユーザー名を設定します。|  
    |**アダプターのモード**|ドロップダウン リストから選択**ストア アンド フォワード**します。|  
    |**否認不可のインジケーター**|ドロップダウン リストから選択**FALSE**します。|  
    |**要求の種類**|適切な設定\<RequestType\> SWIFT で、プロビジョニングに基づく文字列。|  
    |**RequestCrypto**|ドロップダウン リストから選択**FALSE**します。|  
    |**要求元**|適切な設定\<リクエスター\> SWIFT で、プロビジョニングに基づく文字列。|  
    |**応答側**|適切な設定\<レスポンダー\>文字列。|  
    |**[サービス名]**|適切な設定**\<サービス名\>** します。|  
    |**受信確認のインジケーター**|ドロップダウン リストから選択**FALSE**します。|  
    |**イベントのエンドポイント**|ドロップダウン リストから選択**FALSE**します。|  
    |**ファイルの圧縮**|ドロップダウン リストから選択**None**します。|  
    |**物理的なフォルダー名**|Type C:\SWIFTAdapterTutorial\Fileact\ClientLocation.|  
    |**エンドポイントを転送します。**|SAG ルーティング セットの適切なエンドポイントを入力します。 この値は、SAG で構成した SNL エンドポイントと一致する必要があります。|  
    |**ServiceProfile**|ドロップダウン リストから選択**トランザクション数**します。|  
    |**配信通知**|ドロップダウン リストから選択**FALSE**します。|  
    |**通知キュー**|SWIFT で、プロビジョニングに基づく、キュー名を入力します。|  
  
    > [!NOTE]
    >  トランザクションの数のメッセージを転送する場合は、サービスのプロファイルでモードを設定「トランザクション数」に FileAct 送信ポート。  
  
7.  **[OK]** をクリックします。  
  
8.  **送信ポートのプロパティ**ウィンドウで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**送信ハンドラー**|ドロップダウン リストから、選択、 **FileActHost**します。|  
    |**送信パイプライン**|ドロップダウン リストから選択**XMLTransmit**します。|  
    |**受信パイプライン**|ドロップダウン リストから選択**XMLReceive**します。|  
  
9. **送信ポートのプロパティ**ウィンドウで、**フィルター**  タブで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**プロパティ**|ドロップダウン リストから選択**BTS します。ReceivePortName**します。|  
    |**[演算子]**|ドロップダウン リストから選択 **==** します。|  
    |**[値]**|型**Tutorial_IA_InputRequest_SnF**します。|  
    |**グループ化**|既定値のままにします。|  
  
10. **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [手順 2 a:ファイルの受信場所 FileAct ストア アンド フォワード (プル) シナリオの追加します。](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md)   
 [手順 2 b:FileAct ストア アンド フォワード (プル) シナリオに Sw:HandleFileRequest および Sw:HandleSnFRequest メッセージをキャプチャするファイルの送信ポートの追加します。](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md)