---
title: 手順 3 D:InterAct ストア アンド フォワード シナリオ用に INTERACT 送信ポートの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd126d9a-f4e4-429e-bab0-8b4c9c555e36
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55dcfb21444cfdd38faf6e9100d9ff4c9307450b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365539"
---
# <a name="step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario"></a>手順 3 D:InterAct ストア アンド フォワード シナリオ用に INTERACT 送信ポートを追加します。
完全な[手順 3 C:InterAct ストア アンド フォワード シナリオ用に Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)この手順を開始する前にします。
  
## <a name="add-an-interact-send-port"></a>INTERACT 送信ポートを追加します。  
  
1.  開始**BizTalk Server 管理**します。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを順に展開します。  
  
3.  右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な送信請求-応答送信ポート**します。  
  
4.  **送信ポートのプロパティ**ウィンドウで、名前、送信ポート Tutorial_IA_SendRequest_SnF します。  
  
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
    |**[値]**|型 Tutorial_IA_InputRequest_SnF します。|  
    |**グループ化**|既定値のままにします。|  
  
10. **[OK]** をクリックします。  
  
## <a name="complete-steps"></a>手順を完了します
 [ステップ 3:送信ポートの作成し、InterAct ストア アンド フォワード シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [手順 3 a:InterAct ストア アンド フォワード シナリオ用の場所の受信ファイルを追加します。](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md)   
 [手順 3 b:INTERACT の受信場所 InterAct ストア アンド フォワード シナリオ用の追加します。](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md)   
 [手順 3 C:InterAct ストア アンド フォワード シナリオ用に Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加します。](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)  