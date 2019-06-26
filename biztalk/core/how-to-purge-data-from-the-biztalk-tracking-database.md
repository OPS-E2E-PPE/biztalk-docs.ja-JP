---
title: BizTalk 追跡データベースからデータを削除 |Microsoft Docs
description: BizTalk server 追跡データベース (BizTalkDTADB) を消去する、dtasp_PurgeTrackingDatabase ストアド プロシージャを構成します。
ms.custom: ''
ms.date: 10/11/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cdf12866-442d-4c1f-b10f-ebf8d665d521
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74a239f1b54ddf14cf0a9707868649a3df562cfc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384448"
---
# <a name="purge-data-from-the-biztalk-tracking-database"></a>BizTalk 追跡データベースからデータを削除します。
BizTalk 追跡 (BizTalkDTADb) データベースからデータを削除すると、DTA Purge and Archive ジョブがさまざまな種類のメッセージなどの情報とサービス インスタンス情報、オーケストレーション イベントの情報、およびルール エンジン追跡データの追跡をにより削除されます。BizTalk 追跡 (BizTalkDTADb) データベース。  
  
> [!IMPORTANT]
>  この手順を使用して、BizTalk 追跡 (BizTalkDTADb) データベースはアーカイブされません。  
  
> [!WARNING]
>  例外がキャッチされ、追跡を有効にせずに、オーケストレーションで処理する場合、開始状態と例外情報を使用して孤立した追跡インスタンスは、BizTalk 追跡 (BizTalkDTADb) データベースに挿入可能性があります。 このレコードは、データベースの削除後に残ります。  
  
## <a name="prerequisites"></a>前提条件  
この手順を実行するには、SQL Server sysadmin 固定サーバー ロールのメンバーであるアカウントでサインインします。  
  
## <a name="purge-data-from-the-biztalk-tracking-database"></a>BizTalk 追跡データベースからデータを削除します。  
  
1.  BizTalk 追跡 (BizTalkDTADb) データベースをホストする SQL Server で開く**SQL Server Management Studio**です。 
  
2.  **サーバーへの接続**、SQL server の名前、BizTalk 追跡 (BizTalkDTADb) データベースが存在して入力し、認証の種類を選択し、**接続**SQL サーバーに接続します。 
  
3.  ダブルクリックして**SQL Server エージェント**、し、**ジョブ**です。  
  
4.  **オブジェクト エクスプ ローラーの詳細**を右クリックして**DTA Purge and Archive (BizTalkDTADb)** 、し、**プロパティ**です。  
  
5.  **ジョブのプロパティ - DTA Purge and Archive (BizTalkDTADb)** **ページの選択** **手順**です。  
  
6.  **ジョブ ステップの一覧**を選択します**のアーカイブおよび削除**、し、**編集**します。  
  
7.  **ジョブ ステップのプロパティ - Archive and Purge**の**全般**ページで、**コマンド**ボックスで、変更**exec dtasp_BackupAndPurgeTrackingDatabase**に**exec dtasp_PurgeTrackingDatabase**します。  
  
    > [!CAUTION]
    >  **Exec dtasp_PurgeTrackingDatabase**ストアド プロシージャでは、BizTalk 追跡 (BizTalkDTADb) データベースはアーカイブされません。 このオプションを使用する前にあるアーカイブされた追跡データが不要になったことを特定します。  
  
8.  **コマンド**ボックスで、次のパラメーターを更新し、 **OK**します。  
  
    -   @nHours tinyint — 完了したインスタンス (live hours) + (live days) は、関連付けられているすべてのデータと共に削除されます。  
  
    -   @nDays tinyint — 完了したインスタンス (live hours) + (live days) は、関連付けられているすべてのデータと共に削除されます。 既定の間隔は、1 日です。  
  
    -   @nHardDays tinyint — この日数より古いすべてのデータは、データが完全でない場合でも、削除されます。 HardDeleteDays に指定する間隔は、データの有効期間よりも大きい値にする必要があります。 データの有効期間は、BizTalk 追跡データベース (BizTalkDTADb) でデータを追跡する間隔になります。 この間隔より古いデータは、次のアーカイブ時にアーカイブしてから削除できます。  
  
    -   @dtLastBackup -この設定**GetUTCDate()** BizTalk 追跡 (BizTalkDTADb) データベースからデータを削除します。 設定すると**NULL**データは、データベースから削除されません。  

    -  @fHardDeleteRunningInstancesint - 既定値は 0 です。 1 に設定すると、そのすべてを削除よりも古いサービス インスタンスを実行している、@nHardDeleteDays値。  
    
        > [!NOTE] 
        > @fHardDeleteRunningInstancesプロパティは、以降で利用可能な[BizTalk Server 2016 の累積更新プログラム 1年](https://support.microsoft.com/help/3208238/cumulative-update-1-for-microsoft-biztalk-server-2016)、 [BizTalk Server 2013 R2 の累積更新プログラム 6年](https://support.microsoft.com/en-us/help/4020020/cumulative-update-package-6-for-biztalk-server-2013-r2)、および[BizTalk Server 2013 の累積的な更新プログラム 5 適用](https://support.microsoft.com/help/3194301/cumulative-update-5-for-biztalk-server-2013)です。   

    編集したスクリプトを次に、次のような  
  
    ```  
    declare @dtLastBackup datetime set @dtLastBackup = GetUTCDate() exec dtasp_PurgeTrackingDatabase 1, 0, 1, @dtLastBackup, 1  
    ```  
    
9. **ジョブのプロパティ - DTA Purge and Archive (BizTalkDTADb)** ダイアログ ボックスで、**ページの選択** **全般**を選択、**有効**チェック ボックスをオンし、 **OK**です。  
  
## <a name="see-also"></a>参照  
 [BizTalk 追跡データベースのアーカイブおよび削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)
