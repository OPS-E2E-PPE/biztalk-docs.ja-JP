---
title: 手順 2 a - 追加のファイルの受信場所 |Microsoft Docs
description: 手順 2 a-追加のファイルは、BizTalk server FileAct ストア アンド フォワード (プル) シナリオ用の場所を受信
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 13720ebb-fbe4-4fe1-a095-9ae14c62def1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30311c846b26142e0beeea5ab503dd9599b41e18
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366188"
---
# <a name="step-2a-add-file-receive-locations-for-the-fileact-store-and-forward-pull-scenario"></a>手順 2 a:ファイルの受信場所 FileAct ストア アンド フォワード (プル) シナリオの追加します。
この手順を開始する前に行う必要があります[手順 1。FileAct ストア アンド フォワード (プル) シナリオ用に SWIFT アダプターを構成する](step-1-configure-the-swift-adapter-for-fileact-store-and-forward-pull-scenario.md)します。  
  
## <a name="add-a-file-receive-location"></a>ファイル受信場所を追加します。  
  
1.  開始**BizTalk Server 管理**します。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションを順に展開します。  
  
3.  右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート。**  
  
4.  **受信ポートのプロパティ**ウィンドウで、受信ポート名**Tutorial_FA_InputRequest_SnF**します。  
  
5.  **受信ポートのプロパティ**ウィンドウで、**受信場所**] タブで [**新規**します。  
  
6.  **受信場所のプロパティ**ウィンドウの**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とクリックして**構成**します。  
  
7.  **FILE トランスポートのプロパティ**ダイアログ ボックスに「 **C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF**、順にクリックします**OK**します。  
  
8.  **受信場所のプロパティ**ウィンドウの**全般** タブで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**受信ハンドラー**|ドロップダウン リストから選択**BizTalkServerApplication**します。|  
    |**受信パイプライン**|ドロップダウン リストから選択**XMLReceive**します。|  
  
9. **[OK]** をクリックします。  
  
10. 手順 1. および 2. を繰り返します。  
  
11. 右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート。**  
  
12. **受信ポートのプロパティ**ウィンドウで、受信ポート名**Tutorial_ FA_InputRequest_PullMode**します。  
  
13. **受信ポートのプロパティ**ウィンドウで、**受信場所**] タブで [**新規**します。  
  
14. **受信場所のプロパティ**ウィンドウの**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とクリックして**構成**します。  
  
15. **FILE トランスポートのプロパティ**ダイアログ ボックスに「 **C:\SWIFTAdapterTutorial\Interact\PullRequest**、順にクリックします**OK**します。  
  
16. **受信場所のプロパティ**ウィンドウの**全般** タブで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**受信ハンドラー**|ドロップダウン リストから選択**BizTalkServerApplication**します。|  
    |**受信パイプライン**|ドロップダウン リストから選択**XMLReceive**します。|  
  
17. **[OK]** をクリックします。  
  
## <a name="next-steps"></a>次のステップ
-  [手順 2 b:FileAct ストア アンド フォワード (プル) シナリオに Sw:HandleFileRequest および Sw:HandleSnFRequest メッセージをキャプチャするファイルの送信ポートの追加します。](step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md)   
-  [手順 2 C:FileAct ストア アンド フォワード (プル) シナリオに FILEACT 送信ポートの追加します。](step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)