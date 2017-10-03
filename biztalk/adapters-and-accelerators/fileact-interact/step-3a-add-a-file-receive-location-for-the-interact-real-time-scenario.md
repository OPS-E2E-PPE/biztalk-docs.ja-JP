---
title: "手順 3: ファイルの受信場所を追加、リアルタイムのシナリオを対話 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5579375-8c05-4583-bcaa-b483ac275d8a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c29b3eb291b1b36daab5d77aae74f6055a3c738
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario"></a>手順 3: ファイルの受信場所を追加、リアルタイムのシナリオの対話
検証のテスト ファイルを簡単に削除することができます、受信場所を設定します。 この場所を使用するには、シナリオをテストします。  
  
## <a name="add-a-file-receive-location"></a>ファイルの受信場所を追加します。  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションの順に展開します。  
  
3.  右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート。**  
  
4.  **受信ポートのプロパティ**ウィンドウで、受信ポート名**Tutorial_IA_InputRequest_RealTime**です。  
  
5.  **受信ポートのプロパティ** ウィンドウで、**受信場所** タブで、をクリックして**新規**です。  
  
6.  **受信場所のプロパティ**ウィンドウで、**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とをクリックして**構成**です。  
  
7.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、**受信フォルダー**ボックスに、入力**C:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime**をクリックして**Ok**です。  
  
8.  **受信場所のプロパティ** ウィンドウで、**全般** タブで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**受信ハンドラー**|ドロップダウン リストから選択**BizTalkServerApplication**です。|  
    |**受信パイプライン**|ドロップダウン リストから選択**XMLReceive**です。|  
  
9. **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [手順 3: が送信を作成し、受信のポート、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md)   
 [手順 3 b: 対話の受信場所を追加、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md)   
 [手順 3 C: の Sw:HandleRequest メッセージをキャプチャする FILE 送信ポートを追加、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md)   
 [ステップ 3 D: の Sw:HandleResponse メッセージをキャプチャする FILE 送信ポートを追加、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)   
 [ステップ 3 e: 対話する送信ポートの追加、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)