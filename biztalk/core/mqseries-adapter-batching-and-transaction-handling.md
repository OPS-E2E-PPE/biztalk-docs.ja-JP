---
title: MQSeries アダプタのバッチ処理とトランザクション処理 |Microsoft ドキュメント
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
ms.openlocfilehash: ffcdec02c464b9398acbece35657e0c3d1dc4432
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262986"
---
# <a name="mqseries-adapter-batching-and-transaction-handling"></a>MQSeries アダプタのバッチ処理とトランザクション処理
MQSeries アダプタは、すべてのデータを受信していない場合に限り、トランザクションを停止します。 MQSeries アダプタのトランザクションの境界は、アダプタのエンドポイント (MQSeries Server の MQSeries キュー) およびメッセージ ボックス データベースです。  
  
 BizTalk アプリケーションでメッセージが無効化された場合、そのメッセージはアダプタにより保留キューに移動されます。 しかし、アダプタから見ると (すべてのデータを受信しており) そのメッセージはまだ有効なトランザクションなので、トランザクションがコミットされます。  
  
 アダプタを構成するときにプロパティを設定することで、バッチ処理とトランザクション処理を制御できます。 詳細については、次を参照してください。 [MQSeries アダプターを構成する](../core/configuring-the-mqseries-adapter.md)です。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプターのプロパティ](../core/mqseries-adapter-properties.md)