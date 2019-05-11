---
title: チェックリスト:毎週のメンテナンス チェックの実行 |Microsoft Docs
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
ms.openlocfilehash: 937d7976cf76a66131644a38ba057d44473e4984
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242647"
---
# <a name="checklist-performing-weekly-maintenance-checks"></a>チェックリスト:毎週のメンテナンス チェックの実行
このトピックでは、毎週の信頼性、管理、セキュリティ、パフォーマンスのメンテナンス チェックの実行に必要な手順を説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム。  
  
|手順|リファレンス|  
|-----------|---------------|  
|各ホストに少なくとも 2 つの物理 BizTalk サーバー (信頼性の確認) で実行されているインスタンスがあることを確認します。|[BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)|  
|確認冗長は、各受信場所であること (信頼性の確認)。|[受信ホストのスケールアウト](../technical-guides/scaling-out-receiving-hosts.md)|  
|SQL server (管理のチェック) で、SQL Server エージェント サービスが実行されていることを確認します。|-   [操作方法：SQL Server エージェントを開始](http://go.microsoft.com/fwlink/p/?LinkId=154672)(http://go.microsoft.com/fwlink/p/?LinkId=154672)します。<br />-   [SQL Server エージェント](http://go.microsoft.com/fwlink/p/?LinkId=106728)(http://go.microsoft.com/fwlink/p/?LinkId=106728)します。|  
|BizTalk Server に関連するすべての SQL Server ジョブが正常に動作していることを確認します (管理確認)。|[SQL Server エージェント ジョブの監視](../technical-guides/monitoring-sql-server-agent-jobs.md)<br /><br /> SQL Server エージェント ジョブが実行されていない場合、システムのパフォーマンスが時間の経過と共に低下します。 BizTalk Server は、BizTalk Server データベースの管理を参照してください詳細については、SQL Server エージェントのジョブを[データベース構造とジョブ](http://go.microsoft.com/fwlink/p/?LinkID=153451)(http://go.microsoft.com/fwlink/p/?LinkID=153451)します。|  
|BizTalk Server データベースをバックアップする責任を負いますの SQL Server ジョブが正常に実行されていることを確認します (管理確認)。|-   [バックアップ BizTalk Server ジョブを構成する方法](http://go.microsoft.com/fwlink/p/?LinkID=153813)(http://go.microsoft.com/fwlink/p/?LinkID=153813)<br />-   [バックアップ BizTalk Server のジョブをスケジュールする方法](http://go.microsoft.com/fwlink/p/?LinkId=154674)(http://go.microsoft.com/fwlink/p/?LinkId=154674)|  
|最新のセキュリティ更新プログラムがインストールされていることを確認します (セキュリティ チェック)。|Microsoft Update サイト [http://update.microsoft.com/microsoftupdate/v6/default.aspx](http://update.microsoft.com/microsoftupdate/v6/default.aspx)|  
|毎週のパフォーマンス ベースラインとしきい値 (パフォーマンス チェック) に対するログの監視を分析します。|-   [ログ (PAL) ツールのパフォーマンス分析を使用します。](../technical-guides/using-the-performance-analysis-of-logs-pal-tool.md)<br />-   [パフォーマンス Issues3 のトラブルシューティング](../technical-guides/troubleshooting-performance-issues3.md)|  
|システムは、BizTalk Server データベース (パフォーマンス チェック) の頻繁に自動拡張が発生していないことを確認します。|-   [データベースの自動拡張設定を定義します。](../technical-guides/defining-auto-growth-settings-for-databases.md)<br />-   [追跡データベースのサイズ ガイドライン](http://go.microsoft.com/fwlink/p/?LinkId=154677)(http://go.microsoft.com/fwlink/p/?LinkId=154677)します。<br />-   [データベース層のボトルネックを識別する](http://go.microsoft.com/fwlink/p/?LinkId=154678)(http://go.microsoft.com/fwlink/p/?LinkId=154678)します。<br />-   [データベース ファイルの初期化](http://go.microsoft.com/fwlink/p/?LinkID=101579)(http://go.microsoft.com/fwlink/p/?LinkID=101579)します。<br />-   [SQL Server のメンテナンスの手順を実行します。](~/technical-guides/checklist-configuring-sql-server.md)|  
|応答時間と高いリソース使用量 (パフォーマンス チェック) を確認する高負荷時に SQL Server Profiler を実行します。|[SQL Server Profiler を使用して](http://go.microsoft.com/fwlink/p/?LinkID=106720)(http://go.microsoft.com/fwlink/p/?LinkID=106720)します。|  
|すべてのアダプターのメッセージのバッチ処理がリソースの消費量や待機時間 (パフォーマンス チェック) の適切なことを確認します。|-   [アダプターのパフォーマンスを向上させるためにバッチ処理の構成](../technical-guides/configuring-batching-to-improve-adapter-performance.md)<br />-   [パフォーマンスの高いアダプターを設計する方法](http://go.microsoft.com/fwlink/p/?LinkId=154679)(http://go.microsoft.com/fwlink/p/?LinkId=154679)します。|  
|サイズの大きいメッセージのしきい値にリソースの消費量 (パフォーマンス チェック) に適していることを確認します。|[BizTalk Server がサイズの大きいメッセージをどのように処理するか](http://go.microsoft.com/fwlink/p/p/?LinkId=154680)(http://go.microsoft.com/fwlink/p/p/?LinkId=154680)します。|  
|バックアップ ファイルをアーカイブし、適切なコンピューターのバックアップを指定します。|データ損失の可能性を避けるためには、元のデータとのコンピューターとは異なる、バックアップ用のコンピューターを指定する必要があります\<宛先パス\>とは異なるデータベースのログを保存するコンピューターを指定する必要があります元のデータベース ログを備えたコンピューター。<br /><br /> バックアップのベスト プラクティスに関する詳細については、次を参照してください。[をバックアップおよびデータベースを復元するためのベスト プラクティス](http://go.microsoft.com/fwlink/p/p/?LinkID=151391)(http://go.microsoft.com/fwlink/p/p/?LinkID=151391)します。|  
  
## <a name="see-also"></a>参照  
 [定期的な監視タスク](../technical-guides/routine-monitoring-tasks.md)