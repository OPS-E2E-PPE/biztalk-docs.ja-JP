---
title: 手順 3 C:FILE 送信ポート Sw:HandleRequest を取得する追加の操作のストア アンド フォワード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c872b4be-ef8b-4e42-b5ef-63dfd120793f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16941c97e1ee74d9cefc1cc2b70e36ec743a8a20
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365521"
---
# <a name="step-3c-add-file-send-port-to-get-swhandlerequest-interact-store-and-forward"></a>手順 3 C:FILE 送信ポート Sw:HandleRequest を取得する追加の操作のストア アンド フォワード
この手順を開始する前に行う必要があります[手順 3 b:InterAct ストア アンド フォワード シナリオ用の場所の受信、INTERACT 追加](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md)します。  
  
### <a name="to-add-a-file-send-port-to-capture-the-swhandlerequest-message"></a>ファイルを追加するには、送信の Sw:HandleRequest メッセージをキャプチャするポート  
  
1.  開始**BizTalk Server 管理**します。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを順に展開します。  
  
3.  右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート。**  
  
4.  **送信ポートのプロパティ**ウィンドウで、名前、送信ポート Tutorial_IA_SendResponseToReceiver します。  
  
5.  **送信ポートのプロパティ**ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、 をクリックし、**構成**。  
  
6.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、**先フォルダー**ボックスに、C:\SWIFTAdapterTutorial\Interact\HandleRequest を入力し、 をクリックし、 **ok**します。  
  
7.  **送信ポートのプロパティ**ウィンドウで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**送信ハンドラー**|ドロップダウン リストから選択**BizTalkServerApplication**します。|  
    |**送信パイプライン**|ドロップダウン リストから選択**XMLTransmit**します。|  
  
8.  **送信ポートのプロパティ**ウィンドウで、**フィルター**  タブで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**プロパティ**|ドロップダウン リストから選択**BTS します。ReceivePortName**します。|  
    |**[演算子]**|ドロップダウン リストから選択 **==** します。|  
    |**[値]**|型**Tutorial_IA_InputRequest_SnF**します。|  
    |**グループ化**|既定値のままにします。|  
  
9. **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [ステップ 3:送信ポートの作成し、InterAct ストア アンド フォワード シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [手順 3 a:InterAct ストア アンド フォワード シナリオ用の場所の受信ファイルを追加します。](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md)   
 [手順 3 b:INTERACT の受信場所 InterAct ストア アンド フォワード シナリオ用の追加します。](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md)   
 [手順 3 D:InterAct ストア アンド フォワード シナリオ用に INTERACT 送信ポートを追加します。](../../adapters-and-accelerators/fileact-interact/step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario.md)