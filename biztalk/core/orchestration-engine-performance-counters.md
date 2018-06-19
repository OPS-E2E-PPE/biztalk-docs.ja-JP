---
title: オーケストレーション エンジンのパフォーマンス カウンター |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dcaf7517-da4a-4ed0-a3bb-7e9b73931bff
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30c4b3dada1e3775c918d99b1ce0269ac8b1e2a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265610"
---
# <a name="orchestration-engine-performance-counters"></a>オーケストレーション エンジンのパフォーマンス カウンター
オーケストレーション エンジンのパフォーマンス カウンターを使用すると、オーケストレーション エンジンによって一定時間に処理されたオーケストレーション インスタンス数やトランザクション数をパフォーマンス モニターを使って追跡できます。  
  
 パフォーマンス モニターを実行するには、**開始**] メニューの [選択**実行**で入力**perfmon**とキーを押します**Enter**です。 クリックして、**追加**ボタンをクリックし、選択**xlang/s Orchestrations**から、**パフォーマンス オブジェクト**ドロップダウン リスト。  
  
 次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできる、 **xlang/s Orchestrations**パフォーマンス オブジェクト カテゴリ。  
  
|カウンター|コメント|  
|-------------|--------------|  
|% used physical memory|コンピューターの合計物理メモリに対する使用率。|  
|Active application domains|プロセスで読み込まれているオーケストレーション アプリケーション ドメインの数。|  
|Average batch factor|ホスト インスタンスの起動以降に達した永続化ポイントの数を、基になるトランザクション数で割った値。|  
|Database transactions|ホスト インスタンスの起動以降に実行されたデータベース トランザクションの数。|  
|Database transactions/sec|1 秒あたりの平均実行数。|  
|Dehydratable orchestrations|ホスト インスタンスが現在ホストしている、待避可能なオーケストレーション インスタンスの数。|  
|Dehydrating orchestrations|待避処理中のオーケストレーション数。|  
|Dehydration cycle in progress|待避サイクルが現在進行中であるかどうか。|  
|Dehydration cycles|完了した待避サイクルの数。|  
|Dehydration threshold|オーケストレーションを待避する頻度を決定するしきい値 (ミリ秒)。 オーケストレーション エンジンによって推定された待避可能時間が、このしきい値を超えた場合、インスタンス待避されます。|  
|Idle orchestrations|ホスト インスタンスが現在ホストしている、アイドル状態のオーケストレーション インスタンスの数。 これは、アトミック トランザクションにおける受信、待ち受け、または遅延により処理がブロックされているために待機状態にあり、なんら処理は進行していないものの、待避可能な状態にはなっていないオーケストレーションを指します。|  
|Megabytes allocated private memory|ホスト インスタンスに割り当てられたプライベート メモリのサイズ (MB 単位)。|  
|Megabytes allocated virtual memory|ホスト インスタンスに予約された仮想メモリのサイズ (MB 単位)。|  
|MessageBox database connection failures|ホスト インスタンスの起動以降に発生したデータベース接続エラー数。|  
|Online MessageBox databases|現在アプリケーションが利用可能なメッセージ ボックス データベース数。|  
|Orchestrations completed|ホスト インスタンスの起動以降に完了したオーケストレーション インスタンスの数。|  
|Orchestrations completed/sec|1 秒あたりの完了の平均数。|  
|Orchestrations created|ホスト インスタンスの起動以降に作成されたオーケストレーション インスタンスの数。|  
|Orchestrations created/sec|1 秒あたりの平均作成数。|  
|Orchestrations dehydrated|ホスト インスタンスの起動以降に待避されたオーケストレーション インスタンスの数。|  
|Orchestrations dehydrated/sec|1 秒あたりの平均待避数。|  
|Orchestrations discarded|ホスト インスタンスの起動以降にメモリから破棄されたオーケストレーション インスタンスの数。 エンジンがオーケストレーション状態の永続化に失敗した場合、そのオーケストレーションは破棄可能と見なされます。|  
|Orchestrations discarded/sec|1 秒あたりの平均破棄数。|  
|Orchestrations rehydrated|ホスト インスタンスの起動以降に復元されたオーケストレーション インスタンスの数。|  
|Orchestrations rehydrated/sec|1 秒あたりの平均復元数。|  
|Orchestrations resident in memory|ホスト インスタンスによって現在ホストされているオーケストレーション インスタンスの数。|  
|Orchestrations scheduled for dehydration|保留中の待避要求が存在する、待避可能なオーケストレーション数。|  
|Orchestrations suspended|ホスト インスタンスの起動以降に中断されたオーケストレーション インスタンスの数。|  
|Orchestrations suspended/sec|1 秒あたりの平均中断数。|  
|Pending messages|配信確認がメッセージ ボックスに到達していない受信メッセージの数。|  
|Pending work items|実行が予定されているコード実行ブロック数。|  
|Persistence points|ホスト インスタンスの起動以降に、オーケストレーション インスタンスの状態が永続化された回数。|  
|Persistence points/sec|永続化されたオーケストレーション インスタンスの 1 秒あたりの平均数。|  
|Runnable orchestrations|実行する準備が整ったオーケストレーション インスタンス数。|  
|Running orchestrations|現在実行されているオーケストレーション インスタンス数。|  
|Transactional scopes aborted|ホスト インスタンスの起動以降に中止された、長時間またはアトミックのスコープ数。|  
|Transactional scopes aborted/sec|1 秒あたりの平均中止数。|  
|Transactional scopes committed|ホスト インスタンスの起動以降に正常完了した、長時間またはアトミックのスコープ数。|  
|Transactional scopes committed/sec|1 秒あたりの平均コミット数。|  
|Transactional scopes compensated|アプリケーションの起動以降に補正スコープが正常完了した、長時間またはアトミックのスコープ数。|  
|Transactional scopes compensated/sec|1 秒あたりの平均補正数。|  
  
## <a name="see-also"></a>参照  
 [エンジン パフォーマンスの特性](../core/engine-performance-characteristics.md)   
 [シナリオ 2: オーケストレーションでメッセージの追跡データベースのサイズ変更](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [維持可能な最大のエンジン スループットの測定](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [維持可能な最大の追跡スループットの測定](../core/measuring-maximum-sustainable-tracking-throughput.md)