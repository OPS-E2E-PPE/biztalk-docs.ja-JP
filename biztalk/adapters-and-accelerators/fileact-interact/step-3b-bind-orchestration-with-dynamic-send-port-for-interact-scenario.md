---
title: '手順 3 b: InterAct ストアと転送 (するプル) シナリオ用の動的送信ポートにオーケストレーションをバインド |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55eec1f3-b920-48f8-946a-9ad7afa36fd6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b289d8478eb020067d9231fb1d4f135c7b43b289
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223298"
---
# <a name="step-3b-bind-the-orchestration-with-dynamic-send-port-for-interact-store-and-forward-pull-scenario"></a>手順 3 b: InterAct ストアと転送 (するプル) シナリオ用の動的送信ポートにオーケストレーションをバインド
この手順を開始する前に行う必要があります[手順 3A: InterAct ストアと転送 (するプル) シナリオの動的送信ポートのオーケストレーションを作成](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-interact-store-and-forward.md)です。  
  
### <a name="to-add-a-file-receive-location"></a>ファイル受信場所を追加するには  
  
1.  開始**BizTalk Server 管理**です。  
  
2.  左側のウィンドウで、BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**プラットフォームの設定**、し、をクリックして**ホスト インスタンス**です。 いることを確認の状態、 **BizTalkServerApplication**インスタンスと対話するホスト インスタンスをホストが**を実行している**です。 ホスト インスタンスを右クリックしをクリックしていない場合は、**開始**です。  
  
3.  左側のウィンドウで、アプリケーションを展開し、BizTalk アプリケーション 1 の順に展開します。 [オーケストレーション] をクリックします。  
  
4.  右クリック**DynamicSendOrchestration**  をクリック**プロパティ**です。  
  
5.  **オーケストレーションのプロパティ**ダイアログ ボックスで、左側のウィンドウでをクリックして**バインド**し、次の操作を行います。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**ホスト**|ドロップダウン リストから選択**BizTalkServer アプリケーション**です。|  
    |**動的なプル**|ドロップダウン リストから選択**Tutorial_IA_DynamicSendPort**です。|  
    |**SendPullResponseToSender**|ドロップダウン リストから選択**Tutorial_IA_SendPullResponsetoReceiver**です。|  
  
## <a name="see-also"></a>参照  
 [手順 3: InterAct ストアと転送 (するプル) シナリオの動的送信ポートのオーケストレーションを作成します。](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-interact-store-and-forward.md)