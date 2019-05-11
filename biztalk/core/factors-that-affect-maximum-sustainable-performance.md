---
title: 維持可能な最大のパフォーマンスに影響する要因 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maximum sustainable throughput (MST), maintenance
- monitoring, maximum sustainable thoughput (MST)
- maintaining, maximum sustainable thoughput (MST)
- maximum sustainable throughput (MST), monitoring
- maximum sustainable throughput (MST), load patterns
- maximum sustainable throughput (MST), sustainable load test
- sustainable performance
ms.assetid: 99b99655-bc77-425c-a133-204781d7c430
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4f14a1915f70856342f61c8c41f5fbb90233205
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345888"
---
# <a name="factors-that-affect-maximum-sustainable-performance"></a>維持可能な最大パフォーマンスに影響を及ぼす要因
最大持続可能スループットが直接多岐にわたって利用可能なサーバー リソース、ソリューション、メッセージのサイズ、および全体的なメッセージ負荷で使用される機能の種類などの要因によって影響を受けます。 すぐにわかりにくいも、検討を他の要素があります。 維持可能な最大のパフォーマンスを推定する際にも、次の要因を検討してください。  
  
## <a name="load-patterns"></a>ロード パターン  
 メッセージは、通常は、一貫性のある予測可能な速度での BizTalk Server 環境の運用環境にフローしません。 一般的には、ビジネス上のニーズは上下谷に評価する BizTalk Server 変数メッセージを処理します。 ピークが発生すると、BizTalk Server 処理要件可能性がありますにすばやく移動からごくわずか overdrive の条件をメッセージが処理されるよりも速く受信場所。 このシナリオで BizTalk が適切なサブスクライバーに未処理のメッセージを配信するまでに公開されたメッセージがメッセージ ボックス データベース バックログします。 BizTalk Server が負荷のピーク期間の間でメッセージのバックログが蓄積されたプロセスをできる限り、これは問題になりません。  
  
 BizTalk Server 環境へのメッセージ フローの通常の変数パターン、テストのシナリオを実行する、長期間にわたって、ソリューションが必要なスループットは無期限に、ピーク ロードから回復を維持できることを確認します。推移します。  
  
## <a name="monitoring-and-maintenance-activities"></a>監視および保守アクティビティ  
 運用環境のソリューションの有効期間、中に監視のホストがあるし、メンテナンス作業と BizTalk のパフォーマンスに影響を与えることができますが、テスト シナリオに組み込む必要があります。 これらのアクティビティは次のとおりです。  
  
-   **BizTalk 管理コンソール クエリ**これらのクエリがリソースを消費し、種類と、クエリの頻度に応じて全体的なスループットに影響します。  
  
-   **バックアップ、アーカイブ、および削除アクティビティ**もこれらのアクティビティはリソースを消費し、テスト シナリオに組み込む必要があります。 BizTalk Server のすべてのデータベースは定期的にバックアップする必要があり、トランザクション ログの切り捨てられます。 実行されません、トランザクション ログ可能性がありますオフが大きくなり、すべてのトランザクション データベースの使用可能なディスク領域を消費します。 追跡データベース定期的に削除する必要があります、追跡が使用されている場合と大きくなりすぎないようにする必要に応じたアーカイブします。 BizTalk Server データベースの保守の詳細についてを参照してください[Backing Up and BizTalk Server データベースの復元](../core/backing-up-and-restoring-biztalk-server-databases.md)します。  
  
## <a name="see-also"></a>参照  
 [維持可能な最大の追跡スループットの測定](../core/measuring-maximum-sustainable-tracking-throughput.md)