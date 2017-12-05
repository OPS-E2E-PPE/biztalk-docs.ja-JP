---
title: "マークされたトランザクション、完全バックアップ、およびログ バックアップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up, transaction logs
- backing up, full backups
- transaction logs
- backing up, backup jobs
ms.assetid: a383a16d-1e40-4b0b-a515-f1cb90bfb4d2
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff71cbe7eb910c66530dee3264822eae121c0ce2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="marked-transactions-full-backups-and-log-backups"></a>マークされたトランザクション、完全バックアップ、ログ バックアップ
BizTalk Server のバックアップ ジョブは、BizTalk Server のデータベースと呼ばれるトランザクションの種類と組み合わせて、データベースの完全バックアップとトランザクション ログのバックアップを使用して、すべての同期のバックアップを作成、*マークされたトランザクション*です。 "マークされたトランザクション" とは、そのトランザクションに参加するすべてのデータベースのトランザクション ログに対してマークを設定するトランザクションです。 新しい分散トランザクションの開始を抑制しながら、現在実行されている分散トランザクションの完了を待機し、適切な時期が来たらトランザクションを実行してマークを設定するというものです。  
  
 ここでいうマークとは、すべてのデータベース間で同期されたトランザクション ポイントのことです。それ以降のログ バックアップでは、このマークを目安として、データベースを適切なポイントまで復元できます。  
  
 BizTalk Server のバックアップ ジョブを実行するたびに、すべての BizTalk Server データベースの、マークされたトランザクション ログ バックアップが作成され、指定された期間に基づく完全バックアップが作成されます。  
  
## <a name="full-backups"></a>完全バックアップ  
 最初のバックアップ プロセスが実行される BizTalk Server のバックアップ ジョブを実行するときに*BackupFull*、各期間 (not、ジョブを実行するたびに) 1 回です。 BizTalk Server のバックアップ ジョブをスケジュールする方法の詳細については、次を参照してください。[を BizTalk Server のバックアップ ジョブをスケジュールする方法](../core/how-to-schedule-the-backup-biztalk-server-job.md)です。  
  
 新しく設定した間隔で BizTalk Server のバックアップ ジョブが初めて実行されるときは、完全バックアップが実行されます。 たとえば、ジョブを 1 時間おきに実行するようにスケジュールを設定し、間隔を "毎日" に設定した場合、BizTalk Server のバックアップ ジョブは、1 日の初回実行時 (深夜 0:00 時など) に、完全バックアップが実行されます。  
  
## <a name="transaction-log-backups"></a>トランザクション ログのバックアップ  
 BizTalk Server のバックアップ ジョブを実行する 2 つ目のプロセスは*MarkAndBackupLog*です。 ジョブを実行するたびに、このプロセスですべての BizTalk Server データベースにマークが設定され、トランザクション ログ バックアップが実行されます。  
  
 使用して作成された文字列のマークは *\<ServerName\>*_*\<DatabaseName\>*_Log\_  *\<LogMarkName\>*\_*\<タイムスタンプ\>*.bak、場所、 *\<ログ マーク名\>*は、SQL Server エージェント ジョブで構成します。 各データベースの最後のログを復元するときに、このマークが使用されます。  
  
 詳細については、SQL Server Books Online の「トランザクション ログ バックアップ」および「関連するデータベースのバックアップと復旧」を参照してください。  
  
## <a name="see-also"></a>参照  
 [バックアップおよび復元に関する詳細情報](../core/advanced-information-about-backup-and-restore1.md)