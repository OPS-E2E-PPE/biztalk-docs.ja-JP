---
title: 手順 3 a:FileAct ストア アンド フォワード シナリオ用の場所の受信ファイルを追加する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67ecbf4a-a2b4-4534-8ca1-3bfbb6a697bf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d24f40255bd76698a72c614c3ead7cd672ed4b50
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365950"
---
# <a name="step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario"></a>手順 3 a:FileAct ストア アンド フォワード シナリオ用の場所の受信ファイルを追加します。
この手順を開始する前に行う必要があります[手順 2。FileAct ストア アンド フォワード シナリオ用に Paramfile に SWIFTNet 構成を追加](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-store-and-forward.md)します。  
  
### <a name="to-add-a-file-receive-location"></a>ファイル受信場所を追加するには  
  
1.  開始**BizTalk Server 管理**します。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、受信ポートを作成する BizTalk アプリケーションを順に展開します。  
  
3.  右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート。**  
  
4.  **受信ポートのプロパティ**ウィンドウで、名前、受信ポート Tutorial_FA_InputRequest_SnF します。  
  
5.  **受信ポートのプロパティ**ウィンドウで、**受信場所**] タブで [**新規**します。  
  
6.  **受信場所のプロパティ**ウィンドウの**全般** タブから、**トランスポートの種類**ドロップダウン リストで、**ファイル**とクリックして**構成**します。  
  
7.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、**受信フォルダー**ボックスに、C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF を入力し、 をクリックして**OK**。  
  
8.  **受信場所のプロパティ**ウィンドウの**全般** タブで、次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**受信ハンドラー**|ドロップダウン リストから選択**BizTalkServerApplication**します。|  
    |**受信パイプライン**|ドロップダウン リストから選択**XMLReceive**します。|  
  
9. **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [ステップ 3:送信ポートを作成し、受信 FileAct ストア アンド フォワード シナリオ用のポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md)   
 [手順 3 b:FileAct ストア アンド フォワード シナリオ用の場所に、FILEACT の受信を追加します。](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md)   
 [手順 3 C:FileAct ストア アンド フォワード シナリオ用 Sw:HandleFileRequest および Sw:HandleSnFRequest メッセージをキャプチャする FILE 送信ポートの追加します。](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md)   
 [手順 3 D:FileAct ストア アンド フォワード シナリオ用 FILEACT 送信ポートの追加します。](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)