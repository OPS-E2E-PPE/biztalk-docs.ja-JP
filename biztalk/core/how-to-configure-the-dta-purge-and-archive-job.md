---
title: "構成 DTA Purge and Archive ジョブをする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 2015-11-09
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- purging, configuring
- DTA Purge and Archive job, configuring
- archiving [Tracking database], DTA Purge and Archive job
- archiving [Tracking database], configuring
- purging, DTA Purge and Archive job
ms.assetid: 156ccf9b-284f-4b96-a395-92936e8cebcf
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f4985e657f26945aa2fdc168b273dbfdb159efc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-dta-purge-and-archive-job"></a>DTA Purge and Archive ジョブを構成する方法
BizTalk 追跡データベース (BizTalkDTADb) からデータをアーカイブまたは削除する前に、DTA Purge and Archive (BizTalkDTADb) ジョブを構成する必要があります。 このジョブを構成して、プロシージャを呼び出す、dtasp_BackupAndPurgeTrackingDatabase ストア、構成する必要があります、6 つのパラメーターを使用するとします。  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順に従うには、SQL Server の sysadmin 固定サーバー ロールのメンバーであるアカウントでログオンする必要があります。  
  
### <a name="to-configure-the-dta-purge-and-archive-job"></a>DTA purge and archive ジョブを構成するには  
  
1.  BizTalk 追跡 (BizTalkDTADb) データベースをホストする SQL Server で開く**SQL Server Management Studio**です。  
  
2.  **サーバーへの接続**、SQL server の名前、BizTalk 追跡 (BizTalkDTADb) データベースが存在して入力し、認証の種類を選択し、**接続**SQL サーバーに接続します。  
  
3.  **Microsoft SQL Server Management Studio**をダブルクリックして**SQL Server エージェント**、クリックして**ジョブ**です。  
  
4.  **オブジェクト エクスプ ローラーの詳細** ウィンドウを右クリックして**DTA Purge and Archive (BizTalkDTADb)**、クリックして**プロパティ**です。  
  
5.  **ジョブのプロパティ - DTA Purge and Archive (BizTalkDTADb)**ダイアログ ボックスで、**ページの選択**をクリックして**手順**です。  
  
6.  **ジョブ ステップの一覧**、 をクリックして**、アーカイブし、削除**、クリックして**編集**です。  
  
7.  **全般**] ページの [、**コマンド**ボックスで、必要に応じて、次のパラメーターを編集し、をクリックして**OK**です。  
  
    -   @nLiveHourstinyint — (live hours) よりも古いインスタンスに完了した + (live 日) は、関連付けられているすべてのデータと共に削除されます。 これは、必須のパラメーターに既定値はありません。  
  
    -   @nLiveDaystinyint — (live hours) よりも古いインスタンスに完了した + (live 日) は、関連付けられているすべてのデータと共に削除されます。 既定の間隔は、0 日です。  
  
        > [!NOTE]
        >  BizTalk 追跡データベース (BizTalkDTADb) では、LiveHours と LiveDays を加算した値が、BizTalk Server 環境で管理するデータの有効期間になります。 有効期間より前に完了したインスタンスに関連付けられているデータはすべて削除されます。  
  
    -   @nHardDeleteDaystinyint — すべてのデータ (不完全な場合でも) これは、削除するよりも古いします。 HardDeleteDays に指定する間隔は、データの有効期間よりも大きい値にする必要があります。 データの有効期間は、BizTalk 追跡データベース (BizTalkDTADb) でデータを追跡する間隔になります。 この間隔より古いデータは、次のアーカイブ時にアーカイブしてから削除できます。 既定では 0 日です。  
  
    -   @nvcFoldernvarchar (1024) — バックアップ ファイルを配置するフォルダーです。 これは、必須のパラメーターに既定値はありません。  
  
    -   @nvcValidatingServersysname — 検証を実行するサーバー。 NULL 値は検証が行われないことを示します。 既定値は NULL  
  
    -   @fForceBackupint — 既定値は 0 です。 これは、将来の使用に備えて予約されています。  
  
     編集済みのコマンドは、次のようになります。 次の例では 1 時間の有効期間と 1 日の物理削除です。  
  
    ```  
    exec dtasp_BackupAndPurgeTrackingDatabase 1, 0, 1, '\\MyBizTalkServer\backup', null, 0  
    ```  
  
8.  **ジョブのプロパティ - DTA Purge and Archive (BizTalkDTADb)**ダイアログ ボックスで、**ページの選択**、 をクリックして**全般**を選択、**有効**チェック ボックスをクリックして**OK**です。  
  
## <a name="see-also"></a>参照  
 [BizTalk 追跡データベースのアーカイブおよび削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)