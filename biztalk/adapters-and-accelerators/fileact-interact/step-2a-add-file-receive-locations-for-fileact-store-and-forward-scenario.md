---
title: 手順 2A - 追加するファイルの受信場所 |Microsoft ドキュメント
description: 手順 2A-追加のファイルは、BizTalk server FileAct ストア アンド フォワード (プル) シナリオの場所を受信
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
ms.openlocfilehash: e297a85f309445c3caf569d2d752be58997e9754
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224074"
---
# <a name="step-2a-add-file-receive-locations-for-the-fileact-store-and-forward-pull-scenario"></a>手順 2 a: ファイルの受信場所 FileAct ストア アンド フォワード (プル) シナリオの追加
この手順を開始する前に行う必要があります[手順 1: SWIFT アダプター FileAct ストア アンド フォワード (プル) シナリオ用に構成](step-1-configure-the-swift-adapter-for-fileact-store-and-forward-pull-scenario.md)です。  
  
## <a name="add-a-file-receive-location"></a>ファイル受信場所を追加します。  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションの順に展開します。  
  
3.  右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート。**  
  
4.  **受信ポートのプロパティ**ウィンドウで、受信ポート名**Tutorial_FA_InputRequest_SnF**です。  
  
5.  **受信ポートのプロパティ** ウィンドウで、**受信場所** タブで、をクリックして**新規**です。  
  
6.  **受信場所のプロパティ**ウィンドウで、**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とをクリックして**構成**です。  
  
7.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、「 **C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF**、順にクリック**OK**です。  
  
8.  **受信場所のプロパティ** ウィンドウで、**全般** タブで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**受信ハンドラー**|ドロップダウン リストから選択**BizTalkServerApplication**です。|  
    |**受信パイプライン**|ドロップダウン リストから選択**XMLReceive**です。|  
  
9. **[OK]** をクリックします。  
  
10. 手順 1. と 2. を繰り返します。  
  
11. 右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート。**  
  
12. **受信ポートのプロパティ**ウィンドウで、受信ポート名**Tutorial_ FA_InputRequest_PullMode**です。  
  
13. **受信ポートのプロパティ** ウィンドウで、**受信場所** タブで、をクリックして**新規**です。  
  
14. **受信場所のプロパティ**ウィンドウで、**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とをクリックして**構成**です。  
  
15. **FILE トランスポートのプロパティ** ダイアログ ボックスで、「 **C:\SWIFTAdapterTutorial\Interact\PullRequest**、順にクリック**OK**です。  
  
16. **受信場所のプロパティ** ウィンドウで、**全般** タブで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**受信ハンドラー**|ドロップダウン リストから選択**BizTalkServerApplication**です。|  
    |**受信パイプライン**|ドロップダウン リストから選択**XMLReceive**です。|  
  
17. **[OK]** をクリックします。  
  
## <a name="next-steps"></a>次の手順
-  [手順 2 b: Sw:HandleFileRequest をキャプチャするファイルの送信ポートを追加し、FileAct ストア アンド フォワードの Sw:HandleSnFRequest メッセージ (プル) のシナリオ](step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md)   
-  [手順 2 C: FileAct ストア アンド フォワード (プル) シナリオの FILEACT 送信ポートの追加](step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)