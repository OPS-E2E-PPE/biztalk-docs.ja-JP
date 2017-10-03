---
title: "チェックリスト: 毎週のパフォーマンス チェックの実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c36fe78d-1be8-49f2-97ce-b6d0cadffab8
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7898702e42253ab1155b0a6e32af3008800db1f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-performing-weekly-performance-checks"></a>チェックリスト: 毎週のパフォーマンス チェックの実行
このトピックに送信するときにパフォーマンスを回避するには毎週に従う必要のあるベスト プラクティスが一覧表示、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システムです。  
  
|手順|リファレンス|  
|-----------|---------------|  
|固定の数値にデータベースの自動拡張を設定します。|-データベースの自動拡張は、特に、メッセージ ボックス データベースおよび追跡 (DTA) データベースのパーセンテージではなくメガバイト数が固定に設定する必要があります。 によって、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションとスループット、メッセージ ボックス データベースおよび追跡データベースが非常に大きくなることができます。 自動拡張設定されている場合、このパーセンテージを自動拡張がかなり大きくなる場合もします。<br />-場合、システムが新しいは、静的なサイズが決定的確立されていないは、[自動拡張を有効にする] オプションを使用してファイルを構成し、ファイル拡張のメガバイト数を指定します。 拡張増分値を超える 100 MB (サイズの大きいファイル)、10 MB (中規模ファイル用)、または 1 MB (小さなファイル用)、通常場合があります。 参照してください、**付録 B – BizTalk Server データベース構成の推奨**のセクションで、 [BizTalk Server データベースの最適化のホワイト ペーパー](http://go.microsoft.com/fwlink/p/?LinkID=153594) (http://go.microsoft.com/fwlink/p/?LinkID = 153594) ごとに推奨されるファイルのサイズをテーブルに対して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。|  
|SQL Server Profiler で監視するイベントを制限します。|関心があるイベントだけを監視するのにには、SQL Server Profiler を使用します。 トレースが必要になる大きすぎる場合、イベント データのサブセットのみが収集できるように、必要な情報に基づいてフィルター処理できます。 監視するイベントが多すぎると、サーバーと監視プロセスのオーバーヘッドが増え、トレース ファイルやトレース テーブルが非常に大きくなる可能性があります。特に、監視プロセスを長期にわたって実行する場合はこの可能性が高くなります。|  
|アダプターのパフォーマンスを向上させるメッセージのバッチ処理を構成します。|-単一のバッチに 1 つ以上の操作を組み合わせることによって、アダプターによって実行されたトランザクションの数を最小限に抑えます。<br />-メッセージ数だけでなく、バッチ内のバイトの合計数に基づいてバッチ サイズを制限します。 バッチ サイズの制限の詳細については、次を参照してください。[アダプターのパフォーマンスを向上させるバッチ処理構成](../technical-guides/configuring-batching-to-improve-adapter-performance.md)です。|  
|サイズの大きいメッセージのしきい値を調整します。|スループットを向上させるのにはバッファーに格納されるサイズの大きいメッセージの数を減らすことがサイズの大きいメッセージのしきい値を増やすマッピング中にディスクにします。|  
|メモリ リークや、BizTalk Server プロセスでメモリ不足の例外を調査します。|BizTalk プロセスのメモリ リークは、さまざまな理由で発生することができます。 Microsoft サポート技術情報の記事 918643 を参照してください[、メモリ リークや、BizTalk Server プロセスでのメモリ不足の例外のトラブルシューティング方法](http://go.microsoft.com/fwlink/p/?LinkId=157212)(http://go.microsoft.com/fwlink/p/?LinkId = 157212) については、メモリ リークが発生すると、その修正方法のシナリオです。|  
  
## <a name="see-also"></a>参照  
 [日常的なパフォーマンスのチェックリスト](../technical-guides/routine-performance-checklists.md)   
 [チェックリスト: を実行する毎月パフォーマンス チェック](../technical-guides/checklist-performing-monthly-performance-checks.md)