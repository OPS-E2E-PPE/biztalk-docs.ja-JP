---
title: "BizTalk 追跡データベースからデータを削除 |Microsoft ドキュメント"
description: "BizTalk server 追跡データベース (BizTalkDTADB) を消去する dtasp_PurgeTrackingDatabase ストアド プロシージャを構成します。"
ms.custom: 
ms.date: 10/11/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cdf12866-442d-4c1f-b10f-ebf8d665d521
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06217a7d5012eb402698ad35e76ccfc886952f6e
ms.sourcegitcommit: 5e6ef63416e8885a5ee91bd65618a842b3a0cc54
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2017
---
# <a name="purge-data-from-the-biztalk-tracking-database"></a>BizTalk 追跡データベースからデータを削除します。
BizTalk 追跡 (BizTalkDTADb) データベースからデータを削除すると、DTA Purge and Archive ジョブにより、メッセージおよびサービス インスタンスの情報、オーケストレーション イベントの情報、ルール エンジン追跡データなど、さまざまな種類の追跡情報が BizTalk 追跡 (BizTalkDTADb) データベースから削除されます。  
  
> [!IMPORTANT]
>  BizTalk 追跡 (BizTalkDTADb) データベースは、この手順を使用してもアーカイブされません。  
  
> [!WARNING]
>  追跡が有効になっていない状態で例外がキャッチされてオーケストレーションで処理されると、開始状態の孤立した追跡インスタンスおよび例外情報が、BizTalk 追跡 (BizTalkDTADb) データベースに挿入される場合があります。 このレコードは、データベースを削除した後も残ります。  
  
## <a name="prerequisites"></a>前提条件  
この手順を実行するには、SQL Server の sysadmin 固定サーバー ロールのメンバーであるアカウントでサインインします。  
  
## <a name="purge-data-from-the-biztalk-tracking-database"></a>BizTalk 追跡データベースからデータを削除します。  
  
1.  BizTalk 追跡 (BizTalkDTADb) データベースをホストする SQL Server で開く**SQL Server Management Studio**です。 
  
2.  **サーバーへの接続**、SQL server の名前、BizTalk 追跡 (BizTalkDTADb) データベースが存在して入力し、認証の種類を選択し、**接続**SQL サーバーに接続します。 
  
3.  ダブルクリックして**SQL Server エージェント**、し、**ジョブ**です。  
  
4.  **オブジェクト エクスプ ローラーの詳細**を右クリックして**DTA Purge and Archive (BizTalkDTADb)**、し、**プロパティ**です。  
  
5.  **ジョブのプロパティ - DTA Purge and Archive (BizTalkDTADb)****ページの選択****手順**です。  
  
6.  **ジョブ ステップの一覧** **、アーカイブし、削除**、し、**編集**です。  
  
7.  **ジョブ ステップのプロパティ - Archive and Purge**の**全般**] ページの [、**コマンド**ボックスで、変更**exec dtasp_BackupAndPurgeTrackingDatabase**に**exec dtasp_PurgeTrackingDatabase**です。  
  
    > [!CAUTION]
    >  **Exec dtasp_PurgeTrackingDatabase**ストアド プロシージャでは、BizTalk 追跡 (BizTalkDTADb) データベースはアーカイブされません。 このオプションを使用する前に、アーカイブ済みの追跡データが不要であることを確認してください。  
  
8.  **コマンド**ボックスで、次のパラメーターを更新し、 **OK**です。  
  
    -   @nHourstinyint — (live 時間) よりも古いインスタンスに完了した + (live 日) は、関連付けられているすべてのデータと共に削除されます。  
  
    -   @nDaystinyint — (live 時間) よりも古いインスタンスに完了した + (live 日) は、関連付けられているすべてのデータと共に削除されます。 既定の間隔は 1 日です。  
  
    -   @nHardDaystinyint — この日数より古いすべてのデータは、データが完全でない場合でも、削除されます。 HardDeleteDays に指定する間隔は、データの有効期間よりも大きい値にする必要があります。 データの有効期間は、BizTalk 追跡データベース (BizTalkDTADb) でデータを追跡する間隔になります。 この間隔より古いデータは、次のアーカイブ時にアーカイブしてから削除できます。  
  
    -   @dtLastBackup-これを設定して**GetUTCDate()**を BizTalk 追跡 (BizTalkDTADb) データベースからデータを消去します。 設定すると**NULL**データは、データベースから削除されません。  

    -  @fHardDeleteRunningInstancesint - 既定値は 0 です。 1 に設定すると、そのすべてを削除よりも古いサービス インスタンスを実行している、@nHardDeleteDays値。  
    
        > [!NOTE] 
        > @fHardDeleteRunningInstancesプロパティは、以降で利用可能な[BizTalk Server 2016 の累積更新プログラム 1年](https://support.microsoft.com/help/3208238/cumulative-update-1-for-microsoft-biztalk-server-2016)、 [BizTalk Server 2013 R2 の累積更新プログラム 6年](https://support.microsoft.com/en-us/help/4020020/cumulative-update-package-6-for-biztalk-server-2013-r2)、および[BizTalk Server 2013 の累積的な更新プログラム 5 適用](https://support.microsoft.com/help/3194301/cumulative-update-5-for-biztalk-server-2013)です。   

    編集したスクリプトは、次のようにはなります。  
  
    ```  
    declare @dtLastBackup datetime set @dtLastBackup = GetUTCDate() exec dtasp_PurgeTrackingDatabase 1, 0, 1, @dtLastBackup, 1  
    ```  
    
9. **ジョブのプロパティ - DTA Purge and Archive (BizTalkDTADb)**ダイアログ ボックスで、**ページの選択****全般**を選択、**有効**チェック ボックスをオンし、 **OK**です。  
  
## <a name="see-also"></a>参照  
 [BizTalk 追跡データベースのアーカイブおよび削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)
