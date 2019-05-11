---
title: 手順 3 D:FileAct リアルタイム シナリオ用に FILEACT 送信ポートを追加する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a22ba41-4f43-4fbb-92f7-a0fd7558d2ce
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cf9bcd5a893a01b053c5c78452bdac339d115c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365515"
---
# <a name="step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario"></a>手順 3 D:FileAct リアルタイム シナリオ用に FILEACT 送信ポートを追加します。
この手順を開始する前に行う必要があります[手順 3 C:FileAct リアルタイム シナリオ用に Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md)します。  
  
### <a name="to-add-a-fileact-send-port"></a>FILEACT 送信ポートを追加するには  
  
1.  開始**BizTalk Server 管理**します。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを順に展開します。  
  
3.  右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な送信請求-応答送信ポート**します。  
  
4.  **送信ポートのプロパティ**ウィンドウで、名前、送信ポート Tutorial_FA_SendRequest_RealTime します。  
  
5.  **送信ポートのプロパティ**ウィンドウから、**トランスポートの種類**ドロップダウン リストで、 **FILEACT**、 をクリックし、**構成**。  
  
6.  **FILEACT トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**Password**|SAG 接続に応じて、パスワードを設定します。|  
    |**ユーザー名**|SAG 接続用の適切なユーザー名を設定します。|  
    |**アダプターのモード**|ドロップダウン リストから選択**ストア アンド フォワード**します。|  
    |**否認不可のインジケーター**|ドロップダウン リストから選択**FALSE**します。|  
    |**要求の種類**|適切な設定\<RequestType\> SWIFT で、プロビジョニングに基づく文字列。|  
    |**ResponseCrypto**|ドロップダウン リストから選択**FALSE**します。|  
    |**要求元**|適切な設定\<リクエスター\> SWIFT で、プロビジョニングに基づく文字列。|  
    |**応答側**|適切な設定\<レスポンダー\> SWIFT で、プロビジョニングに基づいた文字列。|  
    |**[サービス名]**|適切な設定\<サービス名\>SWIFT で、プロビジョニングに基づいています。|  
    |**受信確認のインジケーター**|ドロップダウン リストから選択**FALSE**します。|  
    |**イベントのエンドポイント**|ドロップダウン リストから選択**FALSE**します。|  
    |**ファイルの圧縮**|ドロップダウン リストから選択**None**します。|  
    |**物理的なフォルダー名**|Type C:\SWIFTAdapterTutorial\Fileact\ClientLocation.|  
    |**エンドポイントを転送します。**|SAG ルーティング セットの適切なエンドポイントを入力します。 この値は、SAG で構成した SnL エンドポイントと一致する必要があります。|  
    |**ServiceProfile**|ドロップダウン リストから選択**トランザクション数**します。|  
    |**配信通知**|ドロップダウン リストから選択**FALSE**します。|  
    |**通知キュー**|SWIFT で、プロビジョニングに基づく、キュー名を入力します。|  
  
    > [!NOTE]
    >  トランザクションの数のメッセージを転送する場合は、サービスのプロファイルでモードを設定「トランザクション数」に FileAct 送信ポート。  
  
7.  **[OK]** をクリックします。  
  
8.  **送信ポートのプロパティ**ウィンドウで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**送信ハンドラー**|ドロップダウン リストから Fileact ホストを選択します。|  
    |**送信パイプライン**|ドロップダウン リストから選択**XMLTransmit**します。|  
    |**受信パイプライン**|ドロップダウン リストから選択**XMLReceive**します。|  
  
9. 送信ポートのプロパティ ウィンドウで、**フィルター**  タブで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**プロパティ**|ドロップダウン リストから選択**BTS します。ReceivePortName**します。|  
    |**[演算子]**|ドロップダウン リストから選択 **==** します。|  
    |**[値]**|型 Tutorial_FA_InputRequest_RealTime します。|  
    |**グループ化**|既定値のままにします。|  
  
10. **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [ステップ 3:送信ポートを作成および FileAct リアルタイム シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md)   
 [手順 3 a:ファイル受信 FileAct リアルタイム シナリオ用の場所を追加します。](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md)   
 [手順 3 b:FileAct リアルタイム シナリオ用の場所に、FILEACT の受信を追加します。](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md)   
 [手順 3 C:FileAct リアルタイム シナリオ用に Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加します。](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md)   
 [手順 3 e:FileAct リアルタイム シナリオ用に Sw:ExchangeFileResponse メッセージをキャプチャする FILE 送信ポートの追加します。](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)