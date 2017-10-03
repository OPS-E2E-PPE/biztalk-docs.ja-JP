---
title: "手順 2 b: InterAct ストア アンド フォワード (プル) シナリオの Sw:HandleRequest メッセージをキャプチャするファイルの送信ポートの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa22d6e7-f1bd-43ad-9a0e-0b287057d20f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24200d21ef4a2047b94f9d818864a0a9da2ceb3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2b-add-file-send-ports-to-capture-the-swhandlerequest-message-for-the-interact-store-and-forward-pull-scenario"></a>手順 2 b: InterAct ストア アンド フォワード (プル) シナリオの Sw:HandleRequest メッセージをキャプチャするファイルの送信ポートの追加
この手順を開始する前に行う必要があります[Step 2 a: InterAct ストア アンド フォワード (プル) シナリオ用のファイル受信場所の追加](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md)です。  
  
### <a name="to-add-a-file-send-port-to-capture-the-swhandlerequest-message"></a>Sw:HandleRequest メッセージをキャプチャするポートを送信するファイルを追加するには  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。  
  
3.  右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート。**  
  
4.  **送信ポートのプロパティ**ウィンドウで、名前、送信ポートを**Tutorial_IA_SendPullResponsetoReceiver**です。  
  
5.  **送信ポートのプロパティ** ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、順にクリック**構成**です。  
  
6.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、**コピー先フォルダー**ボックスに、入力**C:\SWIFTAdapterTutorial\Interact\PullResponse**をクリックして**OK**です。  
  
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
 [手順 2 a: ファイルの受信場所 InterAct ストア アンド フォワード (プル) シナリオの追加](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md)   
 [手順 2 C: InterAct ストア アンド フォワード (プル) シナリオの対話の送信ポートを追加](../../adapters-and-accelerators/fileact-interact/step-2c-add-interact-send-port-for-interact-store-and-forward-pull-scenario.md)