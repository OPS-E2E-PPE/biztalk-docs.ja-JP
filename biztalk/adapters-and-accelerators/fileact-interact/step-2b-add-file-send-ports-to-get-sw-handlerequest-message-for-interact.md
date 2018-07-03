---
title: '手順 2 b: InterAct ストア アンド フォワード (プル) シナリオ用に Sw:HandleRequest メッセージをキャプチャするファイルの送信ポートの追加 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa22d6e7-f1bd-43ad-9a0e-0b287057d20f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56cee834f5974d993dfeaa8fbfee8313eeb74064
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004443"
---
# <a name="step-2b-add-file-send-ports-to-capture-the-swhandlerequest-message-for-the-interact-store-and-forward-pull-scenario"></a>手順 2 b: InterAct ストア アンド フォワード (プル) シナリオ用に Sw:HandleRequest メッセージをキャプチャするファイルの送信ポートの追加
この手順を開始する前に行う必要があります[Step 2 a: InterAct ストア アンド フォワード (プル) シナリオ用のファイル受信場所の追加](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md)します。  

### <a name="to-add-a-file-send-port-to-capture-the-swhandlerequest-message"></a>ファイルを追加するには、送信の Sw:HandleRequest メッセージをキャプチャするポート  

1. 開始**BizTalk Server 管理**します。  

2. コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを順に展開します。  

3. 右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート。**  

4. **送信ポートのプロパティ**ウィンドウで、送信ポート名**Tutorial_IA_SendPullResponsetoReceiver**します。  

5. **送信ポートのプロパティ**ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、 をクリックし、**構成**。  

6. **FILE トランスポートのプロパティ** ダイアログ ボックスで、**先フォルダー**ボックスに「 **C:\SWIFTAdapterTutorial\Interact\PullResponse**、をクリックしてして**OK**します。  

7. **送信ポートのプロパティ**ウィンドウで、次の操作を行います。  


   |   **これを使用して、**    |                        **これを行う**                         |
   |-------------------|---------------------------------------------------------------|
   | **送信ハンドラー**  | ドロップダウン リストから選択**BizTalkServerApplication**します。 |
   | **送信パイプライン** |       ドロップダウン リストから選択**XMLTransmit**します。        |


8. **[OK]** をクリックします。  

9. 手順 1. および 2. を繰り返します。  

10. 右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**動的な送信請求-応答送信ポート**します。  

11. **送信ポートのプロパティ**ウィンドウで、送信ポート名<strong>、Tutorial_IA_DynamicSendPort</strong>します。  

12. **送信ポートのプロパティ**ウィンドウで、次の操作を行います。  


    |     **これを使用して、**     |                  **これを行う**                  |
    |----------------------|--------------------------------------------------|
    |  **送信パイプライン**   | ドロップダウン リストから選択**XMLTransmit**します。 |
    | **受信パイプライン** | ドロップダウン リストから選択**XMLReceive**します。  |


13. **[OK]** をクリックします。  

## <a name="see-also"></a>参照  
 [手順 2 a: InterAct ストア アンド フォワード (プル) シナリオ用の場所を受信するファイルの追加](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md)   
 [手順 2C: InterAct ストア アンド フォワード (プル) シナリオ用に INTERACT 送信ポートを追加する](../../adapters-and-accelerators/fileact-interact/step-2c-add-interact-send-port-for-interact-store-and-forward-pull-scenario.md)