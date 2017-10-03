---
title: "ステップ 3 e: FileAct リアルタイム シナリオ Sw:ExchangeFileResponse メッセージをキャプチャする FILE 送信ポートの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9314f86-a2c9-4ef3-8474-b7e2e2f8bf66
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18e26d13196a46045191b9e5767040e2216ceba2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3e-add-a-file-send-port-to-capture-swexchangefileresponse-message-for-the-fileact-real-time-scenario"></a>ステップ 3 e: FileAct リアルタイム シナリオ Sw:ExchangeFileResponse メッセージをキャプチャする FILE 送信ポートの追加
この手順を開始する前に行う必要があります[ステップ 3 D: FileAct リアルタイム シナリオ FILEACT 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md)です。  
  
### <a name="to-add-a-file-send-port-to-capture-swexchangefileresponse-message"></a>Sw:ExchangeFileResponse メッセージをキャプチャするポートを送信するファイルを追加するには  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。  
  
3.  右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート。**  
  
4.  **送信ポートのプロパティ**ウィンドウで、名前、送信ポートを Tutorial_FA_SendResponseToSender です。  
  
5.  **送信ポートのプロパティ** ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、順にクリック**構成**です。  
  
6.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、**コピー先フォルダー**ボックスに、C:\SWIFTAdapterTutorial\Fileact\ResponseClient を入力し、をクリックして**ok**です。  
  
7.  **送信ポートのプロパティ** ウィンドウで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**送信ハンドラー**|ドロップダウン リストから選択**BizTalkServerApplication**です。|  
    |**送信パイプライン**|ドロップダウン リストから選択**XMLTransmit**です。|  
  
8.  **送信ポートのプロパティ** ウィンドウで、**フィルター**  タブで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**プロパティ**|ドロップダウン リストから選択**BTS です。SPName**です。|  
    |**演算子**|ドロップダウン リストから選択 **==**です。|  
    |**値**|型 Tutorial_FA_SendRequest_RealTime です。|  
    |**グループ化**|既定値を使用します。|  
  
9. **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [手順 3: 送信ポートを作成し、FileAct リアルタイムのシナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md)   
 [手順 3: ファイルの受信場所、FileAct リアルタイムのシナリオの追加](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md)   
 [手順 3 b: FILEACT の受信場所が FileAct リアルタイム シナリオの追加](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md)   
 [手順 3 C: FileAct リアルタイム シナリオ Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md)   
 [ステップ 3 D: FileAct リアルタイム シナリオ FILEACT 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md)