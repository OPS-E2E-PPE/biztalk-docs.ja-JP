---
title: "ステップ 3 D: の Sw:HandleResponse メッセージをキャプチャする FILE 送信ポートを追加、リアルタイムのシナリオを対話 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e05e4d20-4cf2-402f-aaea-66987cb6515a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a0c8c8721d9f7de7b1cd1e57537aa02d2ed8fd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3d-add-a-file-send-port-to-capture-the-swhandleresponse-message-for-the-interact-real-time-scenario"></a>ステップ 3 D: の Sw:HandleResponse メッセージをキャプチャする FILE 送信ポートを追加、リアルタイムのシナリオの対話
完全な[手順 3 C: リアルタイム シナリオでは対話 Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートを追加](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md)この手順を開始する前にします。
  
## <a name="add-a-file-send-port-to-capture-swhandleresponse-message"></a>ファイル送信 Sw:HandleResponse メッセージをキャプチャするポートを追加します。  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。  
  
3.  右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート。**  
  
4.  **送信ポートのプロパティ**ウィンドウで、送信ポートの名前**Tutorial_IA_SendResponseToSender**です。  
  
5.  **送信ポートのプロパティ** ウィンドウから、 **Transporttype**ドロップダウン リストで、**ファイル**、順にクリック**構成**です。  
  
6.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、**コピー先フォルダー**ボックスに、入力**C:\SWIFTAdapterTutorial\Interact\Response**をクリックして**OK**です。  
  
7.  **送信ポートのプロパティ** ウィンドウで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**送信ハンドラー**|ドロップダウン リストから選択**BizTalkServerApplication**です。|  
    |**送信パイプライン**|ドロップダウン リストから選択**XMLTransmit**です。|  
  
8.  **送信ポートのプロパティ** ウィンドウで、**フィルター**  タブで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |最初の行:**プロパティ**|ドロップダウン リストから選択**BTS です。SPName**です。|  
    |最初の行:**演算子**|ドロップダウン リストから選択 **==**です。|  
    |最初の行:**値**|型**Tutorial_IA_HandleRequest_RealTime**です。|  
    |最初の行:**でグループ化**|ドロップダウン リストから選択**または**です。|  
    |2 番目の行:**プロパティ**|ドロップダウン リストから選択**BTS です。MessageType**です。|  
    |2 番目の行:**演算子**|ドロップダウン リストから選択 **==**です。|  
    |2 番目の行:**値**|型**SwInt ExchangeResponse**です。|  
    |2 番目の行:**でグループ化**|既定値を使用します。|  
  
9. **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [手順 3: が送信を作成し、受信のポート、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md)   
 [手順 3: ファイルの受信場所を追加、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md)   
 [手順 3 b: 対話の受信場所を追加、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md)   
 [手順 3 C: の Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートを追加、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md)   
 [ステップ 3 e: 対話する送信ポートの追加、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)