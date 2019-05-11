---
title: 手順 3 C:FileAct ストア アンド フォワード シナリオ用 Sw:HandleFileRequest および Sw:HandleSnFRequest メッセージをキャプチャする FILE 送信ポートの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc41e352-acc5-47eb-bb87-38990f0e76a7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca89ba30184664aada5f312dc021f858234bc39c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365585"
---
# <a name="step-3c-add-a-file-send-port-to-capture-the-swhandlefilerequest-and-swhandlesnfrequest-messages-for-the-fileact-store-and-forward-scenario"></a>手順 3 C:FileAct ストア アンド フォワード シナリオ用 Sw:HandleFileRequest および Sw:HandleSnFRequest メッセージをキャプチャする FILE 送信ポートの追加します。
この手順を開始する前に行う必要があります[手順 3 b:FileAct ストア アンド フォワード シナリオ用の場所に、FILEACT の受信を追加](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md)します。  
  
### <a name="to-add-a-file-send-port-to-capture-swresponseserver-message"></a>ファイルを追加するには、送信の Sw:ResponseServer メッセージをキャプチャするポート  
  
1.  開始**BizTalk Server 管理**します。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを順に展開します。  
  
3.  右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート。**  
  
4.  **送信ポートのプロパティ**ウィンドウで、名前、送信ポート Tutorial_FA_SendResponseToReceiver します。  
  
5.  **送信ポートのプロパティ**ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、 をクリックし、**構成**。  
  
6.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、**先フォルダー**ボックスに、C:\SWIFTAdapterTutorial\Fileact\ResponseServer を入力し、 をクリックし、 **ok**します。  
  
7.  **送信ポートのプロパティ**ウィンドウで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**送信ハンドラー**|ドロップダウン リストから選択**BizTalkServerApplication**します。|  
    |**送信パイプライン**|ドロップダウン リストから選択**XMLTransmit**します。|  
  
8.  **送信ポートのプロパティ**ウィンドウで、**フィルター**  タブで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**最初の行。プロパティ**|ドロップダウン リストから選択**BTS します。MessageType**します。|  
    |**最初の行。!**|ドロップダウン リストから選択 **==** します。|  
    |**最初の行。値**|型**Sw HandleFileRequest**します。|  
    |**最初の行。グループ化**|ドロップダウン リストから選択**または**します。|  
    |**2 番目の行。プロパティ**|ドロップダウン リストから選択**BTS します。MessageType**します。|  
    |**2 番目の行。!**|ドロップダウン リストから選択 **==** します。|  
    |**2 番目の行。値**|型**Sw HandleSnFRequest**します。|  
    |**2 番目の行。グループ化**|既定値のままにします。|  
  
9. **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [ステップ 3:送信ポートを作成し、受信 FileAct ストア アンド フォワード シナリオ用のポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md)   
 [手順 3 a:FileAct ストア アンド フォワード シナリオ用の場所の受信ファイルを追加します。](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md)   
 [手順 3 b:FileAct ストア アンド フォワード シナリオ用の場所に、FILEACT の受信を追加します。](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md)   
 [手順 3 D:FileAct ストア アンド フォワード シナリオ用 FILEACT 送信ポートの追加します。](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)