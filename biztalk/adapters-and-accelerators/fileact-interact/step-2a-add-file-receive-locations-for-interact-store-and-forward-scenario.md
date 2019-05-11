---
title: 手順 2 a:ファイルの受信場所 InterAct ストア アンド フォワード (プル) シナリオの追加 |Microsoft Docs
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
ms.openlocfilehash: 39fe96e60ea183c4ab9ccde767f9848395191233
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366219"
---
# <a name="step-2a-add-file-receive-locations-for-the-interact-store-and-forward-pull-scenario"></a>手順 2 a:ファイル受信 InterAct ストア アンド フォワード (プル) シナリオ用の場所を追加します。
この手順を開始する前に行う必要があります[手順 2。InterAct ストア アンド フォワード シナリオ用に Paramfile に SWIFTNet 構成を追加](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-store-and-forward.md)します。  
  
### <a name="to-add-a-file-receive-location"></a>ファイル受信場所を追加するには  
  
1.  開始**BizTalk Server 管理**します。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションを順に展開します。  
  
3.  右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート。**  
  
4.  **受信ポートのプロパティ**ウィンドウで、受信ポート名**Tutorial_IA_InputRequest_SnF**します。  
  
5.  **受信ポートのプロパティ**ウィンドウで、**受信場所**] タブで [**新規**します。  
  
6.  **受信場所のプロパティ**ウィンドウの**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とクリックして**構成**します。  
  
7.  **FILE トランスポートのプロパティ**ダイアログ ボックスに「 **C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF**、順にクリックします**OK**します。  
  
8.  **受信場所のプロパティ**ウィンドウの**全般** タブで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**受信ハンドラー**|ドロップダウン リストから選択**BizTalkServerApplication**します。|  
    |**受信パイプライン**|ドロップダウン リストから選択**XMLReceive**します。|  
  
9. **[OK]** をクリックします。  
  
10. 手順 1. および 2. を繰り返します。  
  
11. 右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート。**  
  
12. **受信ポートのプロパティ**ウィンドウで、受信ポート名**Tutorial_IA_InputRequest_PullMode**します。  
  
13. **受信ポートのプロパティ**ウィンドウで、**受信場所**] タブで [**新規**します。  
  
14. **受信場所のプロパティ**ウィンドウの**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とクリックして**構成**します。  
  
15. **FILE トランスポートのプロパティ**ダイアログ ボックスに「 **C:\SWIFTAdapterTutorial\Interact\PullRequest**、順にクリックします**OK**します。  
  
16. **受信場所のプロパティ**ウィンドウの**全般** タブで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**受信ハンドラー**|ドロップダウン リストから選択**BizTalkServerApplication**します。|  
    |**受信パイプライン**|ドロップダウン リストから選択**XMLReceive**します。|  
  
17. **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [手順 2 b:InterAct ストア アンド フォワード (プル) シナリオ用に Sw:HandleRequest メッセージをキャプチャするファイルの送信ポートの追加します。](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)   
 [手順 2 C:InterAct ストア アンド フォワード (プル) シナリオ用に INTERACT 送信ポートを追加します。](../../adapters-and-accelerators/fileact-interact/step-2c-add-interact-send-port-for-interact-store-and-forward-pull-scenario.md)