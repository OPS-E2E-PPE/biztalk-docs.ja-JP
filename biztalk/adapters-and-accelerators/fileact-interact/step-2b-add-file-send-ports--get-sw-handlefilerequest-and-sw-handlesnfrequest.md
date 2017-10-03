---
title: "手順 2 b: Sw:HandleFileRequest をキャプチャするファイルの送信ポートを追加し、FileAct ストア アンド フォワードの Sw:HandleSnFRequest メッセージ (プル) シナリオ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 21d055e9-ff7c-4af1-983b-d03e8d4a94f6
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c2eb55cd6aca9b26b8a8ac47ab6dbe192f174d8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2b-add-file-send-ports-to-capture-the-swhandlefilerequest-and-swhandlesnfrequest-messages-for-the-fileact-store-and-forward-pull-scenario"></a>手順 2 b: Sw:HandleFileRequest をキャプチャするファイルの送信ポートを追加し、FileAct ストア アンド フォワードの Sw:HandleSnFRequest メッセージ (プル) のシナリオ
この手順を開始する前に行う必要があります、 [Step 2 a: FileAct ストア アンド フォワード (プル) シナリオ用のファイル受信場所の追加](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md)セクションです。  
  
### <a name="to-add-a-file-send-port-to-capture-the-sw-handlefilerequest-message"></a>ファイル送信ポート、ソフトウェアのキャプチャを追加する: HandleFileRequest メッセージ  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。  
  
3.  右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート。**  
  
4.  **送信ポートのプロパティ**ウィンドウで、名前、送信ポートを**Tutorial_FA_SendPullResponsetoReceiver**です。  
  
5.  **送信ポートのプロパティ** ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、順にクリック**構成**です。  
  
6.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、**コピー先フォルダー**ボックスに、入力**C:\SWIFTAdapterTutorial\FileAct\PullResponse**をクリックして**OK**です。  
  
7.  **送信ポートのプロパティ** ウィンドウで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**送信ハンドラー**|ドロップダウン リストから選択**BizTalkServerApplication**です。|  
    |**送信パイプライン**|ドロップダウン リストから選択**XMLTransmit**です。|  
  
8.  **[OK]**をクリックします。  
  
9. 手順 1. および 2. を繰り返します。  
  
10. 右クリック**送信ポート**、 をポイント**新規**、クリックして**動的な送信請求-応答送信ポート**です。  
  
11. **送信ポートのプロパティ**ウィンドウで、送信ポートの名前**、Tutorial_IA_DynamicSendPort**です。  
  
12. **送信ポートのプロパティ** ウィンドウで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**送信パイプライン**|ドロップダウン リストから選択**XMLTransmit**です。|  
    |**受信パイプライン**|ドロップダウン リストから選択**XMLReceive**です。|  
  
13. **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [手順 2 a: ファイルの受信場所 FileAct ストア アンド フォワード (プル) シナリオの追加](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md)   
 [手順 2 C: FileAct ストア アンド フォワード (プル) シナリオの FILEACT 送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)