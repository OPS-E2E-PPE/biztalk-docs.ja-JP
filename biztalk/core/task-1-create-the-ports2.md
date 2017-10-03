---
title: "タスク 1: 作成、Ports2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 097504c3-67de-4a0b-99a5-648121aff1e5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f41f02d464b15841c3f5a00dbd0601f65e18b510
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="task-1-create-the-ports"></a>タスク 1: ポートを作成します。
左側で BeginDoc ポートと EndDocOut ポートを作成し、右側で 3 つの操作を使用して JDEPort ポートを作成します。  
  
|名前および設定|操作|メッセージの種類 > スキーマ|  
|-----------------------|---------------|--------------------------|  
|BeginDoc<br /><br /> BeginDocType/一方向/内部<br /><br /> [常にこのポートでメッセージを受信します。]<br /><br /> [後で指定する]|操作 1 要求 -|BeginDocTest.B4200310Service_1 です。<br />F4211FSBeginDoc|  
|EndDocOut<br /><br /> EndDocType/一方向/内部<br /><br /> [常にこのポートでメッセージを送信します。]<br /><br /> [後で指定する]|操作 1 要求 -|BeginDocTest.B4200310Service_1 です。<br />F4211FSEndDocResponse|  
|JDEPort<br /><br /> JDEPortType/要求 - 応答/内部<br /><br /> 常にされている要求の送信と応答を受信します<br /><br /> 後で指定**注:**補足的な操作のポートを右クリックし **新しい操作**です。|操作 1 要求 -<br /><br /> 操作 1 応答 -<br /><br /> 2 の操作の要求-<br /><br /> 2 の操作応答-<br /><br /> 操作 3 要求-<br /><br /> 操作 3 応答-|BeginDocTest.B4200310Service_1 です。<br />F4211FSBeginDoc<br /><br /> BeginDocTest.B4200310Service_1 です。<br />F4211FSBeginDocResponse<br /><br /> BeginDocTest.B4200310Service_1 です。<br />F4211FSEditLine<br /><br /> BeginDocTest.B4200310Service_1 です。<br />F4211FSEditLineResponse<br /><br /> BeginDocTest.B4200310Service_1 です。<br />F4211FSEndDoc<br /><br /> BeginDocTest.B4200310Service_1 です。<br />F4211FSEndDocResponse|  
  
## <a name="see-also"></a>参照  
 [タスク 2: メッセージを作成します。](../core/task-2-create-the-messages1.md)   
 [タスク 3: 送信、受信図形と構成](../core/task-3-configure-the-send-and-receive-shapes1.md)   
 [タスク 4: メッセージの構築図形を構成します。](../core/task-4-configure-the-construct-message-shape2.md)   
 [タスク 5: 変換図形を構成します。](../core/task-5-configure-the-transform-shape1.md)