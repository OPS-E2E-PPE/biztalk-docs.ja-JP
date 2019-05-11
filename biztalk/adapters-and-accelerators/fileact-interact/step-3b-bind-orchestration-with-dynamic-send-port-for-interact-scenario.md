---
title: 手順 3 b:InterAct ストア アンド フォワード (プル) シナリオ用の動的送信ポートとオーケストレーションのバインド |Microsoft Docs
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
ms.openlocfilehash: 4719f347004c473a9e9ab6159d33ab2afaaead21
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365578"
---
# <a name="step-3b-bind-the-orchestration-with-dynamic-send-port-for-interact-store-and-forward-pull-scenario"></a>手順 3 b:InterAct ストア アンド フォワード (プル) シナリオ用の動的送信ポートとオーケストレーションをバインドします。
この手順を開始する前に行う必要があります[手順 3 a:InterAct ストア アンド フォワード (プル) シナリオ用の動的送信ポートにオーケストレーションを作成](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-interact-store-and-forward.md)です。  
  
### <a name="to-add-a-file-receive-location"></a>ファイル受信場所を追加するには  
  
1.  開始**BizTalk Server 管理**します。  
  
2.  左側のウィンドウで、BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、し、クリックして**ホスト インスタンス**します。 いることを確認の状態、 **BizTalkServerApplication**インスタンスと対話するホスト インスタンスをホストが**を実行している**。 そうでない場合、ホスト インスタンスを右クリックし、クリックして**開始**します。  
  
3.  左側のウィンドウで、アプリケーションを展開し、BizTalk アプリケーション 1 の順に展開します。 [オーケストレーション] をクリックします。  
  
4.  右クリック**DynamicSendOrchestration**クリック**プロパティ**します。  
  
5.  **オーケストレーションのプロパティ** ダイアログ ボックスで、左側のウィンドウでをクリックして**バインド**次の操作を行います。  
  
    |**これを使用して、**|**これを行う**|  
    |------------------|--------------------|  
    |**ホスト**|ドロップダウン リストから選択**BizTalkServer アプリケーション**します。|  
    |**動的なプル**|ドロップダウン リストから選択**Tutorial_IA_DynamicSendPort**します。|  
    |**SendPullResponseToSender**|ドロップダウン リストから選択**Tutorial_IA_SendPullResponsetoReceiver**します。|  
  
## <a name="see-also"></a>参照  
 [手順 3 a:InterAct ストア アンド フォワード (プル) シナリオ用の動的送信ポートにオーケストレーションを作成します。](../../adapters-and-accelerators/fileact-interact/step-3a-create-orchestration-for-dynamic-send-port-interact-store-and-forward.md)