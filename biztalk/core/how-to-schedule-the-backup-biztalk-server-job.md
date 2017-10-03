---
title: "バックアップの BizTalk Server のジョブをスケジュールする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up, scheduling
- backing up, backup jobs
- scheduling, backup jobs
ms.assetid: 6e89fff4-da87-4cdc-acc4-46f03c3269fc
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d6b40ae933874e1c25cb3a93dbbeab514ef5dfe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-schedule-the-backup-biztalk-server-job"></a>BizTalk Server のバックアップ ジョブのスケジュールを設定する方法
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブは、SQL Server エージェント サービスにより設定されたスケジュールに従って実行されます。 バックアップの実行頻度を変更するには、SQL Server Management Studio を使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブのスケジュールを変更します。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。  
  
### <a name="to-schedule-the-backup-biztalk-server-job-sql-server-2008"></a>BizTalk Server のバックアップ ジョブ (SQL Server 2008) をスケジュールするには  
  
1.  を BizTalk 管理データベースが格納されているコンピューターでをクリックして**開始**、をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 R2**、をクリックして**Microsoft SQL Server Management Studio**です。  
  
2.  **サーバーへの接続** ダイアログ ボックスで、BizTalk Server がデータベース、SQL Server の名前が存在するを指定し、適切な認証の種類をクリックし、**接続**です。  
  
3.  オブジェクト エクスプ ローラーをダブルクリックして**SQL Server エージェント**、クリックして**ジョブ**です。  
  
4.  詳細ウィンドウで右クリック**Backup BizTalk Server (BizTalkMgmtDb)**、クリックして**プロパティ**です。  
  
5.  **ジョブのプロパティ - Backup BizTalk Server (BizTalkMgmtDb)**ダイアログ ボックスで、**ページの選択**をクリックして**手順**です。  
  
6.  **ジョブ ステップの一覧**をクリックして**BackupFull**、順にクリック**編集**です。  
  
7.  **ジョブ ステップのプロパティ - BackupFull**  ダイアログ ボックスで、**コマンド**ボックスで、完全バックアップを実行する間隔を頻度を変更することで、コマンドを編集: **'h'**(1 時間ごと)、**が '** (毎日) **'w'** (毎週)、 **am'** (毎月)、 **'y'** (毎年) をクリックし、 **ok**.  
  
    > [!NOTE]
    >  新しく設定した間隔で BizTalk Server のバックアップ ジョブが最初に実行される際には、完全バックアップが実行されます。  
  
8.  **ジョブのプロパティ - Backup BizTalk Server (BizTalkMgmtDb)**ダイアログ ボックスで、**ページの選択**をクリックして**スケジュール**です。  
  
9. **スケジュール一覧**、 をクリックして**MarkAndBackupLogSched**、クリックして**編集**です。  
  
10. **ジョブ スケジュールのプロパティ - MarkAndBackupLogSched**スケジュールの種類を選択 ダイアログ ボックス**定期的**(既に選択されていない) 場合は、ドロップダウン リスト ボックスからです。  
  
     既定では、ジョブが 15 分おきに実行されるようにスケジュールが設定されます。  
  
11. 必要に応じて、スケジュールを更新し、をクリックして**OK**です。  
  
    > [!NOTE]
    >  SQL Server エージェント ジョブのスケジュール設定に関する詳細については、次を参照してください"[ジョブのスケジュール](http://go.microsoft.com/fwlink/?LinkId=195887)。"。  
  
12. **ジョブのプロパティ - Backup BizTalk Server (BizTalkMgmtDb)**ダイアログ ボックスで、をクリックして**OK**です。  
  
## <a name="see-also"></a>参照  
 [バックアップの BizTalk Server ジョブを構成する方法](../core/how-to-configure-the-backup-biztalk-server-job.md)   
 [ログ配布用に送信先システムを構成する方法](../core/how-to-configure-the-destination-system-for-log-shipping.md)   
 [データベースを復元する方法](../core/how-to-restore-your-databases.md)   
 [バックアップと復元に関する詳細情報](../core/advanced-information-about-backup-and-restore1.md)