---
title: 維持可能な最大のパフォーマンスに影響する要因 |Microsoft ドキュメント
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
ms.openlocfilehash: be96ad552abef66e2a401e334da1c27ee0e08cd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245842"
---
# <a name="factors-that-affect-maximum-sustainable-performance"></a>維持可能な最大パフォーマンスに影響を及ぼす要因
維持可能な最大スループットは、使用可能なサーバー リソース、ソリューションで使用される機能の種類、メッセージ サイズ、全体的なメッセージ負荷などのさまざまな要因によって直接的な影響を受けます。 直接的ではないながらも、検討を要するその他の要因もあります。 維持可能な最大パフォーマンスを予測する際は、以下の要因を考慮してください。  
  
## <a name="load-patterns"></a>ロード パターン  
 通常、予測可能な一定のレートでメッセージが BizTalk Server の運用環境に送信されることはありません。 一般的なビジネス要件では、BizTalk Server を使用してメッセージを処理するレートは上下に変動します。 ピーク時には BizTalk Server の処理要件は短時間で最小からオーバードライブ状態まで上昇し、メッセージの処理レートよりも受信レートが上回ります。 このシナリオでは、公開されたメッセージは、バックログされたメッセージが BizTalk によって適切なサブスクライバーに配信されるまで、メッセージ ボックス データベースにバックログされます。 BizTalk Server が、ピーク ロード期間に蓄積されたメッセージのバックログを処理できる限り、これが問題になることはありません。  
  
 BizTalk Server 環境へのメッセージ フローの一般的なパターンは変動するので、テスト シナリオを一定期間実行して、ソリューションが目的のスループットを維持可能で、時間と共にピーク ロードから回復できることを確認してください。  
  
## <a name="monitoring-and-maintenance-activities"></a>監視および保守アクティビティ  
 運用ソリューションの稼働時には、多くの監視および保守アクティビティが生じます。これらのアクティビティは BizTalk のパフォーマンスに影響する可能性があるので、テスト シナリオに組み込む必要があります。 このようなアクティビティには、以下のものが含まれます。  
  
-   **BizTalk 管理コンソール クエリ**これらのクエリがリソースを消費し、種類と、クエリの頻度に応じて全体的なスループットに影響します。  
  
-   **バックアップ、アーカイブ、および削除アクティビティ**もこれらのアクティビティはリソースを消費し、テスト シナリオに組み込む必要があります。 すべての BizTalk Server データベースを定期的にバックアップし、トランザクション ログを整理する必要があります。 この処理を行わない場合、トランザクション ログのサイズが大きくなり、トランザクション データベースのディスク領域がいっぱいになることがあります。 追跡を使用している場合、追跡データベースの定期的なデータ削除および必要に応じたアーカイブを行うことによって、このデータベースのサイズが大きくなりすぎる状況を回避する必要があります。 BizTalk Server データベースの保守の詳細についてを参照してください[をバックアップおよび BizTalk Server データベースの復元](../core/backing-up-and-restoring-biztalk-server-databases.md)です。  
  
## <a name="see-also"></a>参照  
 [維持可能な最大の追跡スループットの測定](../core/measuring-maximum-sustainable-tracking-throughput.md)