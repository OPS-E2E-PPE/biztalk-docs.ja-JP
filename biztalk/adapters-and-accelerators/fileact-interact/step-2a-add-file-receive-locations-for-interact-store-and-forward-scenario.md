---
title: '手順 2 a: ファイルの受信場所 InterAct ストア アンド フォワード (プル) シナリオの追加 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acdc30e1-d80c-40bf-864d-bf136c77a2b8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 195480b616437eea7b1cfafa703d4ec5d0bd2b54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225274"
---
# <a name="step-2a-add-file-receive-locations-for-the-interact-store-and-forward-pull-scenario"></a>手順 2 a: ファイルの受信場所 InterAct ストア アンド フォワード (プル) シナリオの追加
この手順を開始する前に行う必要があります[手順 2: InterAct ストアと転送シナリオ Paramfile に SWIFTNet 構成を追加](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md)です。  
  
### <a name="to-add-a-file-receive-location"></a>ファイル受信場所を追加するには  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションの順に展開します。  
  
3.  右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート。**  
  
4.  **受信ポートのプロパティ**ウィンドウで、受信ポート名**Tutorial_IA_InputRequest_SnF**です。  
  
5.  **受信ポートのプロパティ** ウィンドウで、**受信場所** タブで、をクリックして**新規**です。  
  
6.  **受信場所のプロパティ**ウィンドウで、**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とをクリックして**構成**です。  
  
7.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、「 **C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF**、順にクリック**OK**です。  
  
8.  **受信場所のプロパティ** ウィンドウで、**全般** タブで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**受信ハンドラー**|ドロップダウン リストから選択**BizTalkServerApplication**です。|  
    |**受信パイプライン**|ドロップダウン リストから選択**XMLReceive**です。|  
  
9. **[OK]** をクリックします。  
  
10. 手順 1. と 2. を繰り返します。  
  
11. 右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート。**  
  
12. **受信ポートのプロパティ**ウィンドウで、受信ポート名**Tutorial_IA_InputRequest_PullMode**です。  
  
13. **受信ポートのプロパティ** ウィンドウで、**受信場所** タブで、をクリックして**新規**です。  
  
14. **受信場所のプロパティ**ウィンドウで、**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とをクリックして**構成**です。  
  
15. **FILE トランスポートのプロパティ** ダイアログ ボックスで、「 **C:\SWIFTAdapterTutorial\Interact\PullRequest**、順にクリック**OK**です。  
  
16. **受信場所のプロパティ** ウィンドウで、**全般** タブで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**受信ハンドラー**|ドロップダウン リストから選択**BizTalkServerApplication**です。|  
    |**受信パイプライン**|ドロップダウン リストから選択**XMLReceive**です。|  
  
17. **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [手順 2 b: InterAct ストア アンド フォワード (プル) シナリオの Sw:HandleRequest メッセージをキャプチャするファイルの送信ポートの追加](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)   
 [手順 2 C: InterAct ストア アンド フォワード (プル) シナリオの対話の送信ポートを追加](../../adapters-and-accelerators/fileact-interact/step-2c-add-interact-send-port-for-interact-store-and-forward-pull-scenario.md)