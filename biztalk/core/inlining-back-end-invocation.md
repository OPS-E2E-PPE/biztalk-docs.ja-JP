---
title: バック エンド呼び出しのインライン化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MessageBox database, performance
- service solution tutorial, performance
- performance, in-line invocation
- Inline Invocation of Back-End Processes [service solutions], performance
- performance, MessageBox database
ms.assetid: 991d080f-a4cc-4f14-bab3-3b8b74636daf
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbd4d24cfc1e78a82e2ec3ddd42218390aaee289
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382162"
---
# <a name="inlining-back-end-invocation"></a>バック エンド呼び出しのインライン化
インライン呼び出しバージョンの完全なソリューションの最も高速な処理時間を提供します。 インライン バージョンでは、要求と応答メッセージを送受信メッセージ ボックス データベース内のバックエンド システムを維持するオーバーヘッドがなくなります。 アダプター バージョンでは、メッセージは送信オーケストレーションからメッセージ ボックスに移動します。 アダプターを実行しているホストは、メッセージを取得し、もう一度メッセージ ボックスに投稿をバックエンド プロセスにメッセージを送信します。  
  
 効率のインライン展開には、オーケストレーションをバックエンド システムのトランスポート プロトコルに直接バインドのコスト。 インライン バージョンではなく論理ポート経由の通信、オーケストレーションは、次の 3 つのカスタム アセンブリを介してバックエンド システムを呼び出します。 バックエンド システムのトランスポートが変更された場合アセンブリを記述し直すし、再コンパイルする必要があります。 次の表では、アセンブリとその機能について説明します。  
  
|アセンブリ名|バック エンド接続|  
|-------------------|--------------------------|  
|Microsoft.Samples.BizTalk.WoodgroveBank.PaymentTrackerCall|MQSeries を使用して**取得**と**配置**メッセージ関数。|  
|Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactionsCall|トランザクション システム用の Web サービスを呼び出します。|  
|Microsoft.Samples.BizTalk.WoodgroveBank.SAPCall|SAP をシミュレートする web サービスを呼び出します。|  
  
## <a name="see-also"></a>参照  
 [サービスの実装の要点指向のソリューション](../core/implementation-highlights-of-the-service-oriented-solution.md)   
 [開発、サービス指向ソリューション](../core/developing-a-service-oriented-solution.md)   
 [指向ソリューションのサービスのパターンの変換](../core/translating-the-patterns-of-the-service-oriented-solution.md)   
 [BAM によるソリューションを指向サービスを監視します。](../core/monitoring-the-service-oriented-solution-with-bam.md)