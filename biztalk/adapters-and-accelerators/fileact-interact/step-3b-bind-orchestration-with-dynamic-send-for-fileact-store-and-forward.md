---
title: '手順 3 b: FileAct ストア アンド フォワード (プル) シナリオ用の動的送信ポートにオーケストレーションをバインド |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb973066-8797-4f51-a89e-3845f2811605
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10111de1080aacd532be96f501be1d20acda1dc5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224386"
---
# <a name="step-3b-bind-the-orchestration-with-dynamic-send-port-for-fileact-store-and-forward-pull-scenario"></a>手順 3 b: FileAct ストア アンド フォワード (プル) シナリオ用の動的送信ポートにオーケストレーションをバインド
この手順を開始する前に行う必要があります[手順 3A: FileAct ストア アンド フォワード (プル) シナリオの動的送信ポート用のオーケストレーションを作成](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-fileact-store-and-forward.md)です。  
  
### <a name="to-add-a-file-receive-location"></a>ファイル受信場所を追加するには  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  左側のウィンドウで、BizTalk Server 管理コンソールで BizTalk Server 管理コンソールを展開し、 **BizTalk グループ**、展開**プラットフォームの設定**、クリックして**ホスト インスタンス**. いることを確認の状態、 **BizTalkServerApplication**と FileActhost インスタンスのインスタンスをホストが**を実行している**です。 ホスト インスタンスを右クリックしをクリックしていない場合は、**開始**です。  
  
3.  左側のウィンドウで、アプリケーションを展開し、BizTalk アプリケーション 1 の順に展開します。 [オーケストレーション] をクリックします。  
  
4.  右クリック**DynamicSendOrchestration**  をクリック**プロパティ**です。  
  
5.  **オーケストレーションのプロパティ**ダイアログ ボックスで、左側のウィンドウでをクリックして**バインド**し、次の操作を行います。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**ホスト**|ドロップダウン リストから選択**BizTalkServer アプリケーション**です。|  
    |**動的なプル**|ドロップダウン リストから選択**Tutorial_FA_DynamicSendPort**です。|  
    |**SendPullResponseToSender**|ドロップダウン リストから選択**Tutorial_FA_SendPullResponsetoReceiver**です。|  
  
## <a name="see-also"></a>参照  
 [手順 3: FileAct ストア アンド フォワード (プル) シナリオの動的送信ポート用のオーケストレーションを作成します。](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-fileact-store-and-forward.md)