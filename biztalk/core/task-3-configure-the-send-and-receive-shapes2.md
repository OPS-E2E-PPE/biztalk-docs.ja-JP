---
title: "タスク 3: が Shapes2 を受信および送信の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ebe7141-f2bd-4e6a-9204-d61bd64286af
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6923a90b43d1bdc3004a03ac588dd2410d81a3cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="task-3-configure-the-send-and-receive-shapes"></a>タスク 3: 送信、受信図形と構成
送信図形と受信図形を構成するには、次の手順に従います。  
  
### <a name="to-configure-the-send-and-receive-shapes"></a>送信図形と受信図形を構成するには  
  
1.  次の順序に従って、送信図形と受信図形をツールボックスからオーケストレーションの中心にドラッグします。  
  
2.  以下のパラメータを設定します。  
  
    |図形|名前|設定|  
    |-----------|----------|-------------|  
    |Receive1|Activate|True|  
    ||メッセージ|BeginDocMsg|  
    ||名前|ReceiveBeginDoc|  
    ||操作|BeginDoc.Operation_1.Request|  
    |Send1|メッセージ|BeginDocSessionMsg|  
    ||名前|SendBeginDoc|  
    ||操作|JDEPort.Operation_1.Request|  
    |Receive2|Activate|False|  
    ||メッセージ|BeginDocResponseMsg|  
    ||名前|ReceiveBeginDocResponse|  
    ||操作|JDEPort.Operation_1.Response|  
    |Send2|メッセージ|EditLineSessionMsg|  
    ||名前|SendEditLine|  
    ||操作|JDEPort.Operation_2.Request|  
    |Receive3|Activate|False|  
    ||メッセージ|EditLineResponseMsg|  
    ||名前|ReceiveEditLine|  
    ||操作|JDEPort.Operation_2.Response|  
    |Send3|メッセージ|EndDocSessionMsg|  
    ||名前|SendEndDoc|  
    ||操作|JDEPort.Operation_3.Request|  
    |Receive4|Activate|False|  
    ||メッセージ|EndDocResponseMsg|  
    ||名前|ReceiveEndDocResponse|  
    ||操作|JDEPort.Operation_3.Response|  
    |Send4|メッセージ|EndDocResponseMsg|  
    ||名前|SendEndDocResponse|  
    ||操作|EndDocOut.Operation_1.Request|  
  
## <a name="see-also"></a>参照  
 [タスク 1: ポートを作成します。](../core/task-1-create-the-ports1.md)   
 [タスク 2: メッセージを作成します。](../core/task-2-create-the-messages2.md)   
 [タスク 4: メッセージの構築図形を構成します。](../core/task-4-configure-the-construct-message-shape1.md)   
 [タスク 5: 変換図形を構成します。](../core/task-5-configure-the-transform-shape2.md)