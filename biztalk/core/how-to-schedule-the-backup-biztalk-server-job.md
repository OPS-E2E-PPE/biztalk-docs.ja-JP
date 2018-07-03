---
title: バックアップ BizTalk Server ジョブのスケジュール |Microsoft Docs
description: BizTalk Server のバックアップ ジョブのパラメーターを構成し、毎月実行、毎週、日単位、または 1 時間ごとに、スケジュールを設定
ms.custom: ''
ms.date: 11/02/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e89fff4-da87-4cdc-acc4-46f03c3269fc
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83dd415648c55b53a9212ce20f4b1f754fb4fbb6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005131"
---
# <a name="schedule-the-backup-biztalk-server-job"></a>バックアップ BizTalk Server ジョブのスケジュール設定します。
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブは、SQL Server エージェント サービスにより設定されたスケジュールに従って実行されます。 バックアップの実行頻度を変更するには、SQL Server Management Studio を使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブのスケジュールを変更します。  
  
## <a name="prerequisites"></a>前提条件  
SQL Server sysadmin 固定サーバー ロールのメンバーであるアカウントでサインインします。  
  
## <a name="schedule-the-backup-biztalk-server-job"></a>BizTalk Server のバックアップ ジョブのスケジュール設定します。
  
1. BizTalk 管理データベースをホストする SQL Server で開きます**SQL Server Management Studio**します。

2. **サーバーへの接続**、データベースが存在すると、BizTalk Server が、認証の種類を選択する SQL Server の名前を入力し、 **Connect**します。  
  
3. オブジェクト エクスプ ローラーでダブルクリック**SQL Server エージェント**、し、**ジョブ**します。  
  
4. 詳細ペインで右クリックして**BizTalk Server のバックアップ (BizTalkMgmtDb)**、し、**プロパティ**します。  
  
5. **ジョブのプロパティ - Backup BizTalk Server (BizTalkMgmtDb)****ページの選択**を選択します**手順**します。  
  
6. **ジョブ ステップの一覧**、 **BackupFull**、し、**編集**。  
  
7. **ジョブ ステップのプロパティ - BackupFull**の**コマンド**ボックスに、完全バックアップを実行する頻度を変更することで、コマンドの更新: **'h'** (時間)、**が '** (毎日) **'w'** (毎週)、**います '** (毎月)、 **'y'** (年単位)。 **[OK]** を選択します。  
  
   > [!NOTE]
   >  最初に、BizTalk Server のバックアップ ジョブの実行時間に、完全バックアップが完了します。  
    
8. 追加構成<strong>@frequency</strong>パラメーター。  
  
   - <strong>@ForceFullBackupAfterPartialSetFailure</strong>: 既定値は**false**します。 ときに**false**完全バックアップが行われるまでは、次のサイクルの完全バックアップの失敗は、システムが待機する場合は、します。  
    
     > [!NOTE]
     >  場合、 <strong>@frequency</strong>設定は時間の長い (毎週、毎月、毎年) など、このパラメーターを設定**false**危険な可能性があります。 このシナリオでこのフラグを設定する最適な場合があります**true**します。 ときに**true**、毎回の障害が発生した、システムを強制的に完全バックアップを作成します。 、小さなパフォーマンスに影響がある可能性がありますが、回復可能なシステムが safter します。
  
   - <strong>@BackupHour</strong>既定値 NULL。 このパラメーターは直接関連して <strong>@Frequency</strong>します。 頻度設定すると**h**フル バックアップを実行する曜日を 1 時間を設定する (時間)。 0 (深夜) から 23 (11 PM) までの値を選択できます。 空白のまま、完全バックアップは 1 時間ごとに実行されます。  
    
      > [!NOTE]
       >  0 ~ 23 の範囲 (たとえば、100 または-1) 外の数値をこのパラメーターを設定すると、0 に、システム強制的します。
  
   - <strong>@UseLocalTime</strong>状態をローカル時刻を使用する: 余分なパラメーター。 既定では、ジョブは、UTC 時刻で動作します。 (これは、UTC + 10 時間) オーストラリアに住んでいる場合は、午前 0 時ではなく、午前 10 時に、バックアップが実行されます。 これを設定するベスト プラクティスとして推奨が**1** (true)。  
  
9. **ジョブのプロパティ - Backup BizTalk Server (BizTalkMgmtDb)**[**ページの選択**、] をクリックして**スケジュール**します。  
  
10. **スケジュール一覧**、 をクリックして**MarkAndBackupLogSched**、 をクリックし、**編集**。  
  
11. **ジョブ スケジュールのプロパティ - MarkAndBackupLogSched**、スケジュールの種類を選択**定期的**ドロップダウン リストから。  
  
     既定では、ジョブが 15 分おきに実行されるようにスケジュールが設定されます。  
     
    > [!NOTE]
    >  に従って、要件が最初のテスト、運用環境では、この値を変更することができます。 バックアップの頻度で不足の結果をこの値に設定し、SQL 環境内のバック グラウンドの負荷を追加します。 値が高すぎるを設定すると、トランザクション ログのサイズを増やすことがあり、パフォーマンスに影響を与えます。 場合によっては、既定値のままにすることをお勧めします。    
  
12. 必要な場合、スケジュールを更新し、 **OK**します。  
  
    > [!NOTE]
    >  [ジョブのスケジュール設定](https://docs.microsoft.com/sql/ssms/agent/schedule-a-job)について詳しく説明します。
  
13. **ジョブのプロパティ - Backup BizTalk Server (BizTalkMgmtDb)**、 をクリックして**OK**します。  
  
## <a name="more-good-stuff"></a>便利な機能  
 [バックアップ BizTalk Server ジョブを構成します。](../core/how-to-configure-the-backup-biztalk-server-job.md)   
 [ログ配布用の送信先システムを構成します。](../core/how-to-configure-the-destination-system-for-log-shipping.md)   
 [データベースを復元します。](../core/how-to-restore-your-databases.md)   
 [バックアップおよび復元に関する詳細情報](../core/advanced-information-about-backup-and-restore1.md)
