---
title: "BizTalk 追跡データベースからデータを削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, purging
- purging
- DTA Purge and Archive job, purging data
- purging, DTA Purge and Archive job
ms.assetid: cdf12866-442d-4c1f-b10f-ebf8d665d521
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01c56629aaa0934010ba79637b4e4a134bf29f26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-purge-data-from-the-biztalk-tracking-database"></a>BizTalk 追跡データベースからデータを削除する方法
BizTalk 追跡 (BizTalkDTADb) データベースからデータを削除すると、DTA Purge and Archive ジョブにより、メッセージおよびサービス インスタンスの情報、オーケストレーション イベントの情報、ルール エンジン追跡データなど、さまざまな種類の追跡情報が BizTalk 追跡 (BizTalkDTADb) データベースから削除されます。  
  
> [!IMPORTANT]
>  BizTalk 追跡 (BizTalkDTADb) データベースは、この手順を使用してもアーカイブされません。  
  
> [!WARNING]
>  追跡が有効になっていない状態で例外がキャッチされてオーケストレーションで処理されると、開始状態の孤立した追跡インスタンスおよび例外情報が、BizTalk 追跡 (BizTalkDTADb) データベースに挿入される場合があります。 このレコードは、データベースを削除した後も残ります。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。  
  
### <a name="to-purge-data-from-the-biztalk-tracking-database"></a>BizTalk 追跡データベースからデータを削除するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP2**、順にクリック**SQL Server Management Studio**です。  
  
2.  **サーバーへの接続**ダイアログ ボックスでは、BizTalk 追跡 (BizTalkDTADb) データベースが存在する SQL Server および適切な認証の種類の名前を指定し、をクリックして**接続**にSQL Server に接続します。  
  
3.  **Microsoft SQL Server Management Studio**をダブルクリックして**SQL Server エージェント**、クリックして**ジョブ**です。  
  
4.  **オブジェクト エクスプ ローラーの詳細** ウィンドウを右クリックして**DTA Purge and Archive (BizTalkDTADb)**、クリックして**プロパティ**です。  
  
5.  **ジョブのプロパティ - DTA Purge and Archive (BizTalkDTADb)**ダイアログ ボックスで、**ページの選択**をクリックして**手順**です。  
  
6.  **ジョブ ステップの一覧**、 をクリックして**、アーカイブし、削除**、クリックして**編集**です。  
  
7.  **ジョブ ステップのプロパティ - Archive and Purge**  ダイアログ ボックスで、**全般** ページの 、**コマンド**ボックスで、変更**exec dtasp_BackupAndPurgeTrackingDatabase**に**exec dtasp_PurgeTrackingDatabase**です。  
  
    > [!CAUTION]
    >  **Exec dtasp_PurgeTrackingDatabase**ストアド プロシージャでは、BizTalk 追跡 (BizTalkDTADb) データベースはアーカイブされません。 このオプションを使用する前に、アーカイブ済みの追跡データが不要であることを確認してください。  
  
8.  **コマンド**ボックスで、必要に応じて、次のパラメーターを編集し、をクリックして**OK**です。  
  
    -   @nHourstinyint — (live 時間) よりも古いインスタンスに完了した + (live 日) は、関連付けられているすべてのデータと共に削除されます。  
  
    -   @nDaystinyint — (live 時間) よりも古いインスタンスに完了した + (live 日) は、関連付けられているすべてのデータと共に削除されます。 既定の間隔は 1 日です。  
  
    -   @nHardDaystinyint — この日数より古いすべてのデータは、データが完全でない場合でも、削除されます。 HardDeleteDays に指定する間隔は、データの有効期間よりも大きい値にする必要があります。 データの有効期間は、BizTalk 追跡データベース (BizTalkDTADb) でデータを追跡する間隔になります。 この間隔より古いデータは、次のアーカイブ時にアーカイブしてから削除できます。  
  
    -   @dtLastBackup-これを設定して**GetUTCDate()**を BizTalk 追跡 (BizTalkDTADb) データベースからデータを消去します。 設定すると**NULL**データは、データベースから削除されません。  
  
     編集したスクリプトは、次のようになります。  
  
    ```  
    declare @dtLastBackup datetime set @dtLastBackup = GetUTCDate() exec dtasp_PurgeTrackingDatabase 1, 0, 1, @dtLastBackup  
    ```  
  
9. **ジョブのプロパティ - DTA Purge and Archive (BizTalkDTADb)**ダイアログ ボックスで、**ページの選択**、 をクリックして**全般**を選択、**有効**チェック ボックスをクリックして**OK**です。  
  
## <a name="see-also"></a>参照  
 [BizTalk 追跡データベースのアーカイブおよび削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)