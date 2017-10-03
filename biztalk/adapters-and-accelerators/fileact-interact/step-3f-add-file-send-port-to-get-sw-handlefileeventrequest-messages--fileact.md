---
title: "ステップ 3 f: ソフトウェア HandleFileEventRequest メッセージをキャプチャする FileAct リアルタイム シナリオの FILE 送信ポートの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b7594b0-0443-41b7-ae04-55b2cc8bf90e
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1d70c338696f1c4455161a88c8d2988e0ea0ccb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3f-add-a-file-send-port-for-the-fileact-real-time-scenario-to-capture-sw-handlefileeventrequest-messages"></a>ステップ 3 f: ソフトウェア HandleFileEventRequest メッセージをキャプチャする FileAct リアルタイム シナリオの FILE 送信ポートの追加
この手順を開始する前に行う必要があります[ステップ 3 e: Sw:ExchangeFileResponse メッセージのキャプチャに FileAct リアルタイム シナリオでは、ファイル送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)  
  
### <a name="to-add-a-file-send-port-to-capture-status-events"></a>状態イベントをキャプチャする FILE 送信ポートを追加するには。  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションの順に展開します。  
  
3.  右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。  
  
4.  **送信ポートのプロパティ**ウィンドウで、名前、送信ポートを Tutorial_ GetStatusReports です。  
  
5.  **送信ポートのプロパティ** ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、順にクリック**構成**です。  
  
6.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、**コピー先フォルダー**ボックス、C:\SWIFTAdapterTutorial\Fileact\ StatusEvents を入力し、をクリックして**ok**です。  
  
7.  **送信ポートのプロパティ** ウィンドウで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**送信ハンドラー**|ドロップダウン リストから選択**BizTalkServerApplication**です。|  
    |**送信パイプライン**|ドロップダウン リストから選択**XMLTransmit**です。|  
  
8.  **送信ポートのプロパティ** ウィンドウで、**フィルター**  タブで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**プロパティ**|BTS を選択します。 [MessageType]|  
    |**演算子**|オン = =|  
    |**値**|型のソフトウェア HandleFileEventRequest|  
    |**[グループ]**|または|  
    |**プロパティ**|BTS を選択します。 [MessageType]|  
    |**演算子**|オン = =|  
    |**値**|型のソフトウェア ExchangeSnFResponse|