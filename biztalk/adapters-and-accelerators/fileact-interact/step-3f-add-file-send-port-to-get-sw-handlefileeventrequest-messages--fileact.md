---
title: 手順 3 f:Sw-handlefileeventrequest メッセージをキャプチャする FileAct リアルタイム シナリオ用の FILE 送信ポートの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b7594b0-0443-41b7-ae04-55b2cc8bf90e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45ad02b111d6fabde4260994f29a0b756cb1dd66
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365346"
---
# <a name="step-3f-add-a-file-send-port-for-the-fileact-real-time-scenario-to-capture-sw-handlefileeventrequest-messages"></a>手順 3 f:Sw-handlefileeventrequest メッセージをキャプチャする FileAct リアルタイム シナリオ用の FILE 送信ポートの追加します。
この手順を開始する前に行う必要があります[手順 3 e:FileAct リアルタイム シナリオ用に Sw:ExchangeFileResponse メッセージをキャプチャする FILE 送信ポートの追加します。](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)  
  
### <a name="to-add-a-file-send-port-to-capture-status-events"></a>状態イベントをキャプチャする FILE 送信ポートを追加するには。  
  
1.  開始**BizTalk Server 管理**します。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを順に展開します。  
  
3.  右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**します。  
  
4.  **送信ポートのプロパティ**ウィンドウで、名前、送信ポート Tutorial_ GetStatusReports します。  
  
5.  **送信ポートのプロパティ**ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、 をクリックし、**構成**。  
  
6.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、**先フォルダー**ボックス、C:\SWIFTAdapterTutorial\Fileact\ StatusEvents を入力し、をクリックし、 **ok**します。  
  
7.  **送信ポートのプロパティ**ウィンドウで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**送信ハンドラー**|ドロップダウン リストから選択**BizTalkServerApplication**します。|  
    |**送信パイプライン**|ドロップダウン リストから選択**XMLTransmit**します。|  
  
8.  **送信ポートのプロパティ**ウィンドウで、**フィルター**  タブで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**プロパティ**|BTS を選択します。 [MessageType]|  
    |**[演算子]**|選択 = =|  
    |**[値]**|Type Sw-HandleFileEventRequest|  
    |**[グループ]**|または|  
    |**プロパティ**|BTS を選択します。 [MessageType]|  
    |**[演算子]**|選択 = =|  
    |**[値]**|Type Sw-ExchangeSnFResponse|