---
title: 手順 2 C:InterAct ストア アンド フォワード (プル) シナリオ用に INTERACT 送信ポートの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57038f77-85c3-4811-ab3d-df6e2da8fbcf
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3373f7653856800c3cb8a64ca07afe88eb86d192
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366109"
---
# <a name="step-2c-add-an-interact-send-port-for-the-interact-store-and-forward-pull-scenario"></a>手順 2 C:InterAct ストア アンド フォワード (プル) シナリオ用に INTERACT 送信ポートを追加します。
この手順を開始する前に行う必要があります[手順 2 b:InterAct ストア アンド フォワード (プル) シナリオ用に Sw:HandleRequest メッセージをキャプチャするファイルの送信ポートを追加](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)します。  
  
### <a name="to-add-an-interact-send-port"></a>INTERACT 送信ポートを追加するには  
  
1.  開始**BizTalk Server 管理**します。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを順に展開します。  
  
3.  右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な送信請求-応答送信ポート**します。  
  
4.  **送信ポートのプロパティ**ウィンドウで、送信ポート名**Tutorial_IA_SendRequest_SnF**します。  
  
5.  **送信ポートのプロパティ**ウィンドウから、**トランスポートの種類**ドロップダウン リストで、 **INTERACT**、順にクリックします**構成**します。  
  
6.  **トランスポートのプロパティの対話** ダイアログ ボックスで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**Password**|SAG 接続に応じて、パスワードを設定します。|  
    |**ユーザー名**|SAG 接続用の適切なユーザー名を設定します。|  
    |**メッセージの形式**|**InteractMessage**|  
    |**否認不可のインジケーター**|**FALSE**|  
    |**要求の種類**|適切な入力\<RequestType\> SWIFT で、プロビジョニングに基づく文字列。|  
    |**ResponseCrypto**|**FALSE**|  
    |**要求元**|適切な入力\<RequestorDN\> SWIFT で、プロビジョニングに基づく文字列。|  
    |**応答側**|適切な入力\<ResponderDN\> SWIFT で、プロビジョニングに基づく文字列。|  
    |**[サービス名]**|適切な入力\<サービス名\>を基に、SWIFT でプロビジョニングします。|  
    |**配信通知**|ドロップダウン リストから選択**FALSE**します。|  
    |**通知キュー**|SWIFT で、プロビジョニングに基づく、適切なキュー名を入力します。|  
  
    > [!NOTE]
    >  ペイロードは、転送するのには、専用の場合、INTERACT で「ペイロード」MessageFormat をセットの受信ポートと INTERACT 送信ポート。 PassThru には、受信と送信パイプラインを設定します。  
  
7.  **[OK]** をクリックします。  
  
8.  **送信ポートのプロパティ**ウィンドウで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**送信ハンドラー**|ドロップダウン リストから、対話するホストを選択します。|  
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
 [手順 2 a:ファイル受信 InterAct ストア アンド フォワード (プル) シナリオ用の場所を追加します。](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md)   
 [手順 2 b:InterAct ストア アンド フォワード (プル) シナリオ用に Sw:HandleRequest メッセージをキャプチャするファイルの送信ポートの追加します。](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)