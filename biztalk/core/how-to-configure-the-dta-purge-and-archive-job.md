---
title: 構成 DTA Purge and Archive ジョブ |Microsoft ドキュメント
description: BizTalk server 追跡データベースを維持するために SQL Server エージェントで、DTA Purge and Archive ジョブのパラメーターを設定します。
ms.custom: ''
ms.date: 10/11/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 156ccf9b-284f-4b96-a395-92936e8cebcf
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69b9b221a26ad844aa23b65ada5a8c6cce38cf8c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386095"
---
# <a name="configure-the-dta-purge-and-archive-job"></a>構成 DTA Purge and Archive ジョブ
BizTalk 追跡データベース (BizTalkDTADb) からデータをアーカイブまたは削除する前に、DTA Purge and Archive (BizTalkDTADb) ジョブを構成する必要があります。 このジョブを構成して、プロシージャを呼び出す、dtasp_BackupAndPurgeTrackingDatabase ストア、構成する必要があります、6 つのパラメーターを使用するとします。  
  
## <a name="prerequisites"></a>前提条件  
 SQL Server の sysadmin 固定サーバー ロールのメンバーであるアカウントでサインインします。  
  
## <a name="configure-the-dta-purge-and-archive-job"></a>構成 DTA purge and archive ジョブ  
  
1.  BizTalk 追跡 (BizTalkDTADb) データベースをホストする SQL Server で開く**SQL Server Management Studio**です。  
  
2.  **サーバーへの接続**、SQL server の名前、BizTalk 追跡 (BizTalkDTADb) データベースが存在して入力し、認証の種類を選択し、**接続**SQL サーバーに接続します。  
  
3. ダブルクリックして**SQL Server エージェント**、し、**ジョブ**です。  
  
4.  **オブジェクト エクスプ ローラーの詳細**を右クリックして**DTA Purge and Archive (BizTalkDTADb)** 、し、**プロパティ**です。  
  
5.  **ジョブのプロパティ - DTA Purge and Archive (BizTalkDTADb)** **ページの選択** **手順**です。  
  
6.  **ジョブ ステップの一覧** **、アーカイブし、削除**、し、**編集**です。  
  
7.  **全般**で、**コマンド**ボックスで、次のパラメーターを更新し、 **OK**です。  
  
    -   @nLiveHourstinyint — (live hours) よりも古いインスタンスに完了した + (live 日) は、関連付けられているすべてのデータと共に削除されます。 これは、必須のパラメーターに既定値はありません。  
  
    -   @nLiveDaystinyint — (live hours) よりも古いインスタンスに完了した + (live 日) は、関連付けられているすべてのデータと共に削除されます。 既定の間隔は、0 日です。  
  
        > [!NOTE]
        >  BizTalk 追跡データベース (BizTalkDTADb) では、LiveHours と LiveDays を加算した値が、BizTalk Server 環境で管理するデータの有効期間になります。 有効期間より前に完了したインスタンスに関連付けられているデータはすべて削除されます。  
  
    -   @nHardDeleteDaystinyint — すべてのデータ (不完全な場合でも) これは、削除するよりも古いします。 HardDeleteDays に指定する間隔は、データの有効期間よりも大きい値にする必要があります。 データの有効期間は、BizTalk 追跡データベース (BizTalkDTADb) でデータを追跡する間隔になります。 この間隔より古いデータは、次のアーカイブ時にアーカイブしてから削除できます。 既定では 0 日です。  
  
    -   @nvcFoldernvarchar (1024) — バックアップ ファイルを配置するフォルダーです。 これは、必須のパラメーターに既定値はありません。  
  
    -   @nvcValidatingServersysname — 検証を実行するサーバー。 NULL 値は検証が行われないことを示します。 既定値は NULL  
  
    -   @fForceBackupint — 既定値は 0 です。 これは、将来の使用に備えて予約されています。  
  
    -   @fHardDeleteRunningInstancesint - 既定値は 0 です。 1 に設定すると、そのすべてを削除よりも古いサービス インスタンスを実行している、@nHardDeleteDays値。 
    
        > [!NOTE]
        > @fHardDeleteRunningInstancesプロパティは、以降で利用可能な[BizTalk Server 2016 の累積更新プログラム 1年](https://support.microsoft.com/help/3208238/cumulative-update-1-for-microsoft-biztalk-server-2016)、 [BizTalk Server 2013 R2 の累積更新プログラム 6年](https://support.microsoft.com/en-us/help/4020020/cumulative-update-package-6-for-biztalk-server-2013-r2)、および[BizTalk Server 2013 の累積的な更新プログラム 5 適用](https://support.microsoft.com/help/3194301/cumulative-update-5-for-biztalk-server-2013)です。  
  
    編集したコマンドは次のようになります。 次の例では 1 時間の有効期間、物理削除の 1 日、および削除を実行中のすべてサービス インスタンスが 1 日よりも古い。  
  
    ```  
    exec dtasp_BackupAndPurgeTrackingDatabase 1, 0, 1, '\\MyBizTalkServer\backup', null, 0, 1  
    ```  
  
8.  **ジョブのプロパティ - DTA Purge and Archive (BizTalkDTADb)** ダイアログ ボックスで、**ページの選択** **全般**を選択、**有効**チェック ボックスをオンし、 **OK**です。  
  
## <a name="see-also"></a>参照  
 [BizTalk 追跡データベースのアーカイブおよび削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)
