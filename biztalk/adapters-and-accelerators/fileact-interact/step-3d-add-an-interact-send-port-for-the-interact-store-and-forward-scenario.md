---
title: "ステップ 3 D: InterAct ストアと転送シナリオの対話の送信ポートの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd126d9a-f4e4-429e-bab0-8b4c9c555e36
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ac1d379f2e68431f197f2db339cd0ac9f50c92e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario"></a>ステップ 3 D: InterAct ストアと転送シナリオの対話の送信ポートの追加
完全な[手順 3 C: InterAct ストアと転送シナリオ Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートを追加](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)この手順を開始する前にします。
  
## <a name="add-an-interact-send-port"></a>対話する送信ポートを追加します。  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。  
  
3.  右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。  
  
4.  **送信ポートのプロパティ**ウィンドウで、名前、送信ポートを Tutorial_IA_SendRequest_SnF です。  
  
5.  **送信ポートのプロパティ** ウィンドウから、**トランスポートの種類**ドロップダウン リストで、 **INTERACT**、順にクリック**構成**です。  
  
6.  **トランスポートのプロパティの対話** ダイアログ ボックスで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**Password**|SAG 接続適切なパスワードを設定します。|  
    |**ユーザー名**|SAG 接続を適切なユーザー名を設定します。|  
    |**メッセージの形式**|**InteractMessage**|  
    |**否認不可インジケーター**|**FALSE**|  
    |**要求の種類**|適切な入力\<RequestType > SWIFT でのプロビジョニングに基づく文字列。|  
    |**ResponseCrypto**|**FALSE**|  
    |**要求元**|適切な入力\<RequestorDN > SWIFT でのプロビジョニングに基づく文字列。|  
    |**応答側**|適切な入力\<ResponderDN > SWIFT でのプロビジョニングに基づく文字列。|  
    |**サービス名**|適切な入力\<サービス名 > SWIFT でのプロビジョニングに基づきます。|  
    |**配信通知**|ドロップダウン リストから選択**FALSE**です。|  
    |**通知キュー**|SWIFT でのプロビジョニングに基づく、適切なキュー名を入力します。|  
  
    > [!NOTE]
    >  ペイロードは、転送するのには、専用の場合は、ポートと対話する送信ポートが受信の対話で「ペイロード」に MessageFormat を設定します。 PassThru に、受信パイプラインと送信パイプラインを設定します。  
  
7.  **[OK]**をクリックします。  
  
8.  **送信ポートのプロパティ** ウィンドウで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**送信ハンドラー**|ドロップダウン リストから、対話ホストを選択します。|  
    |**送信パイプライン**|ドロップダウン リストから選択**XMLTransmit**です。|  
    |**受信パイプライン**|ドロップダウン リストから選択**XMLReceive**です。|  
  
9. **送信ポートのプロパティ** ウィンドウで、**フィルター**  タブで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**プロパティ**|ドロップダウン リストから選択**BTS です。ReceivePortName**です。|  
    |**演算子**|ドロップダウン リストから選択 **==**です。|  
    |**値**|型 Tutorial_IA_InputRequest_SnF です。|  
    |**グループ化**|既定値を使用します。|  
  
10. **[OK]**をクリックします。  
  
## <a name="complete-steps"></a>詳細な手順
 [手順 3: 送信ポートを作成し、対話ストアと転送シナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [手順 3: ファイルの受信場所が、対話ストアと転送シナリオの追加](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md)   
 [手順 3 b: 追加、対話の受信場所が、対話ストアと転送シナリオ](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md)   
 [手順 3 C: InterAct ストアと転送シナリオ Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)  