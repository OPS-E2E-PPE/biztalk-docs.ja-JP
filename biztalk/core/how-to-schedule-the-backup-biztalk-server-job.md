---
title: "バックアップの BizTalk Server のジョブのスケジュールを設定 |Microsoft ドキュメント"
description: "BizTalk Server のバックアップ ジョブのパラメーターを構成および実行毎月、毎週、日単位、または 1 時間ごとに、スケジュールを設定"
ms.custom: 
ms.date: 11/02/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e89fff4-da87-4cdc-acc4-46f03c3269fc
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f09ca97f65605ac3bf427d1c1fcc322a14feb53
ms.sourcegitcommit: 9aaed443492b74729171fef79c634bff561af929
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2017
---
# <a name="schedule-the-backup-biztalk-server-job"></a>バックアップの BizTalk Server ジョブのスケジュール
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブは、SQL Server エージェント サービスにより設定されたスケジュールに従って実行されます。 バックアップの実行頻度を変更するには、SQL Server Management Studio を使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブのスケジュールを変更します。  
  
## <a name="prerequisites"></a>前提条件  
SQL Server の sysadmin 固定サーバー ロールのメンバーであるアカウントでサインインします。  
  
## <a name="schedule-the-backup-biztalk-server-job"></a>BizTalk Server のバックアップ ジョブのスケジュール
  
1.  BizTalk 管理データベースをホストする SQL Server で開く**SQL Server Management Studio**です。

2.  **サーバーへの接続**、ここでデータベースが存在する、BizTalk Server は、認証の種類を選択します。 SQL Server の名前を入力し、**接続**です。  
  
3.  オブジェクト エクスプ ローラーでダブルクリック**SQL Server エージェント**、し、**ジョブ**です。  
  
4.  詳細ウィンドウで右クリック**Backup BizTalk Server (BizTalkMgmtDb)**、し、**プロパティ**です。  
  
5.  **ジョブのプロパティ - Backup BizTalk Server (BizTalkMgmtDb)****ページの選択****手順**です。  
  
6.  **ジョブ ステップの一覧** **BackupFull**、し、**編集**です。  
  
7.  **ジョブ ステップのプロパティ - BackupFull**で、**コマンド**ボックスで、完全バックアップを実行する頻度を変更することで、コマンドを更新します**'h'** (1 時間ごと)、**が '。** (毎日) **'w'** (毎週)、 **am'** (毎月)、 **'y'** (毎年)。 **[ OK]** を選択します。  
  
    > [!NOTE]
    >  BizTalk Server のバックアップ ジョブを初めて実行するには、完全バックアップが完了します。  
    
8.  追加の構成 **@frequency** パラメーター。  
  
    - **@ForceFullBackupAfterPartialSetFailure**: 既定値は**false**です。 ときに**false**次回のサイクル、完全バックアップが行われるまで、完全バックアップが失敗したら、システムが待機する場合、します。  
    
        > [!NOTE]
        >  場合、  **@frequency** 設定が長い (毎週、月、毎年) などし、このパラメーターを設定**false**危険な可能性があります。 このシナリオである可能性がありますにこのフラグを設定することをお**true**です。 ときに**true**、毎回の障害が発生した、システム強制的に完全バックアップを作成します。 小さいパフォーマンスに影響がある可能性がありますが、回復可能なシステムが safter です。
  
    - **@BackupHour**: デフォルトの値は NULL です。 このパラメーターに直接関係する **@Frequency**です。 頻度を設定すると**h**完全バックアップを実行する曜日を 1 時間を設定する (時間単位)。 0 (深夜) から 23 (11 PM) までの値を選択できます。 空白の場合、完全バックアップには、1 時間ごとが実行されます。  
    
       > [!NOTE]
        >  (たとえば、100 または-1) 0 ~ 23 の範囲外の数値でこのパラメーターを設定する場合、システム リテラルに 0 です。
  
    - **@UseLocalTime**: ローカル時刻を使用する状態余分なパラメーターです。 既定では、ジョブは UTC 時刻で動作します。 したがってオーストラリア (これは、UTC + 10 時間) に住んでいる場合は、午前 0 時ではなく、午前 10 時、バックアップが実行されます。 ベスト プラクティスとしてお勧めこの**1** (true)。  
  
9.  **ジョブのプロパティ - Backup BizTalk Server (BizTalkMgmtDb)****ページの選択**をクリックして**スケジュール**です。  
  
10. **スケジュール一覧**、 をクリックして**MarkAndBackupLogSched**、クリックして**編集**です。  
  
11. **ジョブ スケジュールのプロパティ - MarkAndBackupLogSched**、スケジュールの種類の選択**定期的**ドロップダウン リストからです。  
  
     既定では、ジョブが 15 分おきに実行されるようにスケジュールが設定されます。  
     
    > [!NOTE]
    >  に従って、要件が、運用環境以外の最初のテストには、この値を変更することができます。 頻繁なバックアップで低すぎる結果をこの値に設定し、SQL 環境内で負荷を背景に追加します。 この値が大きすぎるを設定すると、トランザクション ログのサイズを増やすことがあり、パフォーマンスに影響を与えます。 一部の状況で、既定値のままにしておくことをお勧めします。    
  
12. 必要な場合、スケジュールを更新し、 **OK**です。  
  
    > [!NOTE]
    >  [ジョブのスケジュール](https://docs.microsoft.com/sql/ssms/agent/schedule-a-job)詳細を示します。
  
13. **ジョブのプロパティ - Backup BizTalk Server (BizTalkMgmtDb)**をクリックして**OK**です。  
  
## <a name="more-good-stuff"></a>便利な機能  
 [バックアップの BizTalk Server のジョブを構成します。](../core/how-to-configure-the-backup-biztalk-server-job.md)   
 [ログ配布の送信先システムを構成します。](../core/how-to-configure-the-destination-system-for-log-shipping.md)   
 [データベースを復元します。](../core/how-to-restore-your-databases.md)   
 [バックアップおよび復元に関する詳細情報](../core/advanced-information-about-backup-and-restore1.md)
