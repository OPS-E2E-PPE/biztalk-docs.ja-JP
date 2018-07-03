---
title: '手順 2 b: Sw:HandleFileRequest をキャプチャするファイルの送信ポートを追加および Sw:HandleSnFRequest メッセージを FileAct ストア アンド フォワード (プル) シナリオ |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 21d055e9-ff7c-4af1-983b-d03e8d4a94f6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47515324fae89937754e0643563f16df9777868a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991491"
---
# <a name="step-2b-add-file-send-ports-to-capture-the-swhandlefilerequest-and-swhandlesnfrequest-messages-for-the-fileact-store-and-forward-pull-scenario"></a>手順 2 b: Sw:HandleFileRequest をキャプチャするファイルの送信ポートを追加および Sw:HandleSnFRequest メッセージを FileAct ストア アンド フォワード (プル) シナリオ
この手順を開始する前に行う必要があります、 [Step 2 a: FileAct ストア アンド フォワード (プル) シナリオ用のファイル受信場所の追加](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md)セクション。  

### <a name="to-add-a-file-send-port-to-capture-the-sw-handlefilerequest-message"></a>ファイル送信ポート、Sw のキャプチャを追加する: HandleFileRequest メッセージ  

1. 開始**BizTalk Server 管理**します。  

2. コンソール ツリーで、BizTalk グループを展開し、送信ポートを作成する BizTalk アプリケーションを順に展開します。  

3. 右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート。**  

4. **送信ポートのプロパティ**ウィンドウで、送信ポート名**Tutorial_FA_SendPullResponsetoReceiver**します。  

5. **送信ポートのプロパティ**ウィンドウから、**トランスポートの種類**ドロップダウン リストで、**ファイル**、 をクリックし、**構成**。  

6. **FILE トランスポートのプロパティ** ダイアログ ボックスで、**先フォルダー**ボックスに「 **C:\SWIFTAdapterTutorial\FileAct\PullResponse**、をクリックしてして**OK**します。  

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
 [手順 2 a: FileAct ストア アンド フォワード (プル) シナリオ用の場所の受信ファイルを追加](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md)   
 [手順 2C: FileAct ストア アンド フォワード (プル) シナリオ用に FILEACT 送信ポートを追加する](../../adapters-and-accelerators/fileact-interact/step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)