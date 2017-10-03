---
title: "手順 3 C: Sw:HandleFileRequest と Sw:HandleSnFRequest FileAct ストア アンド フォワードのシナリオについてメッセージをキャプチャする FILE 送信ポートの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc41e352-acc5-47eb-bb87-38990f0e76a7
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae6858164ee82f935c607246e7e93ffd86908f93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3c-add-a-file-send-port-to-capture-the-swhandlefilerequest-and-swhandlesnfrequest-messages-for-the-fileact-store-and-forward-scenario"></a>手順 3 C: Sw:HandleFileRequest と Sw:HandleSnFRequest FileAct ストア アンド フォワードのシナリオについてメッセージをキャプチャする FILE 送信ポートの追加
この手順を開始する前に行う必要があります[手順 3 b: FileAct ストア アンド フォワードのシナリオの FILEACT 受信場所を追加](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md)です。  
  
### <a name="to-add-a-file-send-port-to-capture-swresponseserver-message"></a>Sw:ResponseServer メッセージをキャプチャするポートを送信するファイルを追加するには  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。  
  
3.  右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート。**  
  
4.  **送信ポートのプロパティ**ウィンドウで、名前、送信ポートを Tutorial_FA_SendResponseToReceiver です。  
  
5.  **送信ポートのプロパティ** ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、順にクリック**構成**です。  
  
6.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、**コピー先フォルダー**ボックスに、C:\SWIFTAdapterTutorial\Fileact\ResponseServer を入力し、をクリックして**ok**です。  
  
7.  **送信ポートのプロパティ** ウィンドウで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**送信ハンドラー**|ドロップダウン リストから選択**BizTalkServerApplication**です。|  
    |**送信パイプライン**|ドロップダウン リストから選択**XMLTransmit**です。|  
  
8.  **送信ポートのプロパティ** ウィンドウで、**フィルター**  タブで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**最初の行: プロパティ**|ドロップダウン リストから選択**BTS です。MessageType**です。|  
    |**最初の行: 演算子**|ドロップダウン リストから選択 **==**です。|  
    |**最初の行: 値**|型**ソフトウェア HandleFileRequest**です。|  
    |**最初の行: グループ化**|ドロップダウン リストから選択**または**です。|  
    |**2 番目の行: プロパティ**|ドロップダウン リストから選択**BTS です。MessageType**です。|  
    |**2 番目の行: 演算子**|ドロップダウン リストから選択 **==**です。|  
    |**2 番目の行: 値**|型**ソフトウェア HandleSnFRequest**です。|  
    |**2 番目の行: グループ化**|既定値を使用します。|  
  
9. **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [手順 3: 送信ポートを作成し、FileAct ストア アンド フォワードのシナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md)   
 [手順 3: ファイルの受信場所が FileAct ストア アンド フォワードのシナリオを追加](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md)   
 [手順 3 b: FILEACT の受信場所が FileAct ストア アンド フォワードのシナリオを追加](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md)   
 [ステップ 3 D: FileAct ストア アンド フォワードのシナリオの FILEACT 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)