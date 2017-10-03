---
title: "バック エンド呼び出しのインライン展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MessageBox database, performance
- service solution tutorial, performance
- performance, in-line invocation
- Inline Invocation of Back-End Processes [service solutions], performance
- performance, MessageBox database
ms.assetid: 991d080f-a4cc-4f14-bab3-3b8b74636daf
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7300429e9f74abc7bc10569c653bdaa0a4c13b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="inlining-back-end-invocation"></a>バック エンド呼び出しのインライン展開
完全ソリューションのインライン呼び出しバージョンでは、処理時間の短縮が可能になります。 インライン バージョンでは、メッセージ ボックス データベースにおいてバックエンド システムに対する要求および応答メッセージを維持するオーバーヘッドがありません。 アダプタ バージョンでは、メッセージは送信オーケストレーションからメッセージ ボックスに送信されます。 アダプタを実行するホストがメッセージを受け取ってバックエンド プロセスに送信しますが、このとき、メッセージがメッセージ ボックスに再度送信されます。  
  
 インライン化の効率性は、オーケストレーションをバックエンド システムのトランスポート プロトコルに直接バインドするコストに反映されます。 インライン バージョンでは、論理ポート経由の通信ではなく、オーケストレーションが 3 つのカスタム アセンブリを介してバックエンド システムを呼び出します。 バックエンド システムのトランスポートが変更された場合、アセンブリを再記述して再コンパイルする必要があります。 次の表では、アセンブリとその機能について説明します。  
  
|アセンブリ名|バックエンド接続|  
|-------------------|--------------------------|  
|Microsoft.Samples.BizTalk.WoodgroveBank.PaymentTrackerCall|MQSeries を使用して**取得**と**put**メッセージ関数。|  
|Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactionsCall|トランザクション システム用の Web サービスを呼び出します。|  
|Microsoft.Samples.BizTalk.WoodgroveBank.SAPCall|SAP をシミュレートする Web サービスを呼び出します。|  
  
## <a name="see-also"></a>参照  
 [指向ソリューションのサービスの実装の要点](../core/implementation-highlights-of-the-service-oriented-solution.md)   
 [指向ソリューションのサービスの開発](../core/developing-a-service-oriented-solution.md)   
 [指向ソリューションのパターンのサービスの変換](../core/translating-the-patterns-of-the-service-oriented-solution.md)   
 [BAM によるソリューションを指向サービスを監視します。](../core/monitoring-the-service-oriented-solution-with-bam.md)