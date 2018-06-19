---
title: 'チェックリスト: 毎週の保守チェックの実行 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b13e43ba-4bac-4d4b-aaf8-46d60c0561bf
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4cc715db0ec4047b9625b83d457af8df3974719
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976528"
---
# <a name="checklist-performing-weekly-maintenance-checks"></a>チェックリスト: 毎週の保守チェックの実行
このトピックの内容が毎週の信頼性、管理、セキュリティ、およびパフォーマンスのメンテナンス チェックの実行に必要な手順について説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システムです。  
  
|手順|リファレンス|  
|-----------|---------------|  
|各ホストが少なくとも 2 台の物理的な BizTalk サーバー (信頼性チェック) で実行されているインスタンスであることを確認します。|[BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)|  
|確認が重複している各受信場所 (信頼性チェック)。|[受信ホストのスケールアウト](../technical-guides/scaling-out-receiving-hosts.md)|  
|SQL server (管理チェック) で、SQL Server エージェント サービスが実行されていることを確認します。|-   [方法: SQL Server エージェントの起動](http://go.microsoft.com/fwlink/p/?LinkId=154672)(http://go.microsoft.com/fwlink/p/?LinkId=154672)。<br />-   [SQL Server エージェント](http://go.microsoft.com/fwlink/p/?LinkId=106728)(http://go.microsoft.com/fwlink/p/?LinkId=106728)。|  
|BizTalk Server に関連するすべての SQL Server ジョブが正常に動作していることを確認してください (管理確認) します。|[SQL Server エージェント ジョブの監視](../technical-guides/monitoring-sql-server-agent-jobs.md)<br /><br /> SQL Server エージェント ジョブが実行されていない場合は、時間の経過と共にシステムのパフォーマンスが低下します。 詳細については、SQL Server エージェント ジョブの BizTalk Server では、BizTalk Server データベースの管理を参照してください[データベース構造とジョブ](http://go.microsoft.com/fwlink/p/?LinkID=153451)(http://go.microsoft.com/fwlink/p/?LinkID=153451)。|  
|BizTalk Server データベースのバックアップを担当する SQL Server ジョブが正常に実行されていることを確認してください (管理確認) します。|-   [バックアップの BizTalk Server ジョブを構成する方法](http://go.microsoft.com/fwlink/p/?LinkID=153813)(http://go.microsoft.com/fwlink/p/?LinkID=153813)<br />-   [バックアップの BizTalk Server のジョブをスケジュールする方法](http://go.microsoft.com/fwlink/p/?LinkId=154674)(http://go.microsoft.com/fwlink/p/?LinkId=154674)|  
|最新のセキュリティ更新プログラムがインストールされていることを確認してください (セキュリティ チェック)。|Microsoft Update サイト[http://update.microsoft.com/microsoftupdate/v6/default.aspx](http://update.microsoft.com/microsoftupdate/v6/default.aspx)|  
|週単位のパフォーマンス ベースラインとしきい値 (パフォーマンス チェック) に対するログの監視を分析します。|-   [ログ (PAL) のツールのパフォーマンス分析の使用](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)<br />-   [パフォーマンス Issues3 のトラブルシューティング](../technical-guides/troubleshooting-performance-issues3.md)|  
|システムは、BizTalk Server データベース (パフォーマンス チェック) の頻繁に自動拡張が発生していないことを確認します。|-   [データベースの自動拡張設定を定義します。](../technical-guides/defining-auto-growth-settings-for-databases.md)<br />-   [追跡データベースのサイズに関するガイドライン](http://go.microsoft.com/fwlink/p/?LinkId=154677)(http://go.microsoft.com/fwlink/p/?LinkId=154677)。<br />-   [データベース層のボトルネックの特定](http://go.microsoft.com/fwlink/p/?LinkId=154678)(http://go.microsoft.com/fwlink/p/?LinkId=154678)。<br />-   [データベースのファイルの初期化](http://go.microsoft.com/fwlink/p/?LinkID=101579)(http://go.microsoft.com/fwlink/p/?LinkID=101579)。<br />-   [SQL Server のメンテナンスの手順を実行します。](~/technical-guides/checklist-configuring-sql-server.md)|  
|応答時間と高いリソース使用率 (パフォーマンス チェック) を確認する高負荷時に SQL Server Profiler を実行します。|[SQL Server Profiler を使用して](http://go.microsoft.com/fwlink/p/?LinkID=106720)(http://go.microsoft.com/fwlink/p/?LinkID=106720)。|  
|すべてのアダプターのメッセージのバッチ処理がリソースの消費量や待機時間 (パフォーマンス チェック) の適切なことを確認します。|-   [アダプターのパフォーマンスを向上させるためにバッチ処理の構成](../technical-guides/configuring-batching-to-improve-adapter-performance.md)<br />-   [パフォーマンスの高いアダプターを設計する方法](http://go.microsoft.com/fwlink/p/?LinkId=154679)(http://go.microsoft.com/fwlink/p/?LinkId=154679)。|  
|サイズの大きいメッセージのしきい値がリソースの消費量 (パフォーマンス チェック) に適していることを確認します。|[BizTalk Server がサイズの大きいメッセージをどのように処理するか](http://go.microsoft.com/fwlink/p/p/?LinkId=154680)(http://go.microsoft.com/fwlink/p/p/?LinkId=154680)。|  
|バックアップ ファイルをアーカイブし、適切なコンピューターのバックアップを指定します。|データ損失の可能性を回避するのには、元のデータとは、コンピューターとは異なる、バックアップ先としてコンピューターを指定する必要があります\<移行先パス\>とは異なるデータベース ログを格納するコンピューターを指定する必要があります元のデータベースのログ コンピューターからです。<br /><br /> バックアップのベスト プラクティスの詳細については、次を参照してください。 [Backing Up and Restoring Databases のベスト プラクティス](http://go.microsoft.com/fwlink/p/p/?LinkID=151391)(http://go.microsoft.com/fwlink/p/p/?LinkID=151391)。|  
  
## <a name="see-also"></a>参照  
 [定期的な監視タスク](../technical-guides/routine-monitoring-tasks.md)