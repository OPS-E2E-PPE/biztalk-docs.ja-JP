---
title: タスク 1:作成、Ports2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 097504c3-67de-4a0b-99a5-648121aff1e5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a68c8814331ea3a34985eebc0ef1fe8e019fe49
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291518"
---
# <a name="task-1-create-the-ports"></a>タスク 1:ポートを作成します。
BeginDoc と EndDocOut 左側で、次のポートを作成し、右側の 3 つの操作で JDEPort します。  
  
|名前と設定|操作|メッセージの種類 > スキーマ|  
|-----------------------|---------------|--------------------------|  
|BeginDoc<br /><br /> BeginDocType/一方向/内部<br /><br /> しますが常にこのポートでメッセージを受信<br /><br /> 後で指定します。|操作 1 要求-|BeginDocTest.B4200310Service_1 します。<br />F4211FSBeginDoc|  
|EndDocOut<br /><br /> EndDocType/一方向/内部<br /><br /> しますが常にこのポートでメッセージを送信します。<br /><br /> 後で指定します。|操作 1 要求-|BeginDocTest.B4200310Service_1 します。<br />F4211FSEndDocResponse|  
|JDEPort<br /><br /> JDEPortType/要求-応答/内部<br /><br /> 常にされている要求の送信と応答を受信します<br /><br /> 後で指定する**に注意してください。** 追加操作の場合は、ポートを右クリックして**新しい操作**します。|操作 1 要求-<br /><br /> 操作 1 応答-<br /><br /> 操作 2 要求-<br /><br /> 操作 2 応答-<br /><br /> 操作 3 要求-<br /><br /> 操作 3 応答-|BeginDocTest.B4200310Service_1 します。<br />F4211FSBeginDoc<br /><br /> BeginDocTest.B4200310Service_1 します。<br />F4211FSBeginDocResponse<br /><br /> BeginDocTest.B4200310Service_1 します。<br />F4211FSEditLine<br /><br /> BeginDocTest.B4200310Service_1 します。<br />F4211FSEditLineResponse<br /><br /> BeginDocTest.B4200310Service_1 します。<br />F4211FSEndDoc<br /><br /> BeginDocTest.B4200310Service_1 します。<br />F4211FSEndDocResponse|  
  
## <a name="see-also"></a>参照  
 [タスク 2:メッセージを作成します。](../core/task-2-create-the-messages1.md)   
 [タスク 3:受信図形と送信の構成](../core/task-3-configure-the-send-and-receive-shapes1.md)   
 [タスク 4:メッセージの構築図形を構成します。](../core/task-4-configure-the-construct-message-shape2.md)   
 [タスク 5:変換図形を構成します。](../core/task-5-configure-the-transform-shape1.md)