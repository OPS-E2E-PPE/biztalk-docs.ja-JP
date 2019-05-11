---
title: MQSeries アダプターがバッチ処理とトランザクションの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IBM WebSphere MQ queues
- transactions, MQSeries adapters
- MQSeries adapters, transactions
- MQSeries adapters, IBM WebSphere MQ queues
- MQSeries adapters, batching
- batching, MQSeries adapters
ms.assetid: 2e43fca9-acbd-4fd3-8df3-5f7398553830
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 466201e88b55cd17300deaae3d1b1258e82a2c2c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531200"
---
# <a name="mqseries-adapter-batching-and-transaction-handling"></a>MQSeries アダプターのバッチ処理とトランザクション処理
MQSeries アダプターは、すべてのデータが受信しない場合にのみ、トランザクションを停止します。 アダプターのトランザクションの境界は、アダプターのエンドポイント (MQSeries サーバー上の MQSeries キュー) と、メッセージ ボックス データベースです。  
  
 BizTalk アプリケーションがメッセージを無効にする場合、アダプターは、保留キューにメッセージを移動します。 ただし、アダプター (アダプターで受信したすべてのデータ) の有効なトランザクションの観点からではまだであるため、アダプターは、トランザクションをコミットします。  
  
 バッチ処理とトランザクション アダプターを構成するときにプロパティを設定して処理を制御できます。 詳細については、次を参照してください。 [MQSeries アダプターの構成](../core/configuring-the-mqseries-adapter.md)します。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプター プロパティ](../core/mqseries-adapter-properties.md)