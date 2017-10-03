---
title: "アーカイブの自動検証を有効にする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validating, archives [Tracking database]
- archiving [Tracking database], validating archive
ms.assetid: 406ca54a-6b1f-4bdb-9bad-bea5ea0f6e66
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 258fcb96bbb9bbb045aeb3f48c2b324502d44940
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-automatic-archive-validation"></a>アーカイブの自動検証を有効にする方法
アーカイブ検証を使用すると、アーカイブを作成時に検証することができます。 アーカイブの自動検証を有効にするには、セカンダリ データベース サーバー (検証サーバー) をセットアップしておく必要があります。 アーカイブ プロセスは単純なバックアップなので、ハードウェアの問題で、ディスク上に格納される実際のイメージが破損する可能性があります。  
  
 アーカイブ検証機能を使用することで、アーカイブ (バックアップ) が正常に行われ、復元できることを保証できます。 アーカイブが作成されると、新しいアーカイブが作成されたことが検証サーバーに通知されます。 検証サーバーではそのアーカイブの復元が試行されます。 検証サーバーは、ジョブを実行しているものとは別の [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] インスタンスにする必要があります。 検証サーバー上の [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] のバージョンは、データベースをホストするために使用されている [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] と同じバージョンである必要があります。  
  
 検証サーバーで復元が正常に行われると、その情報が BizTalk 追跡 (BizTalkDTADb) データベースに返送されます。 復元が正常に完了するまでは、Purge ジョブによってそれ以上データが削除されません。  
  
 検証サーバーで復元が正常に行われないと、その情報が BizTalk 追跡データベースに返送されます。 その結果、Purge ジョブは別のアーカイブを作成し、新しいアーカイブの検証が完了するのを待機します。 これにより、アーカイブの破損によって追跡データが失われるのを防ぐことができます。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定サーバー ロールのメンバーであるアカウントを使用してログオンする必要があります。  
  
### <a name="to-enable-automatic-archive-validation"></a>アーカイブの自動検証を有効にするには  
  
1.  検証サーバーで、をクリックして**開始**をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP2**、順にクリック**SQL Server Management Studio**.  
  
2.  **サーバーへの接続** ダイアログ ボックスで、指定の名前、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]する復元プロセスのテストを実行してアーカイブし、をクリックして**接続**への接続に、適切な SQL Server。  
  
    > [!NOTE]
    >  アーカイブを検証しているときにシステム パフォーマンスが低下するため、このサーバーを別の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベース サーバーにはしないでください。  
  
3.  **Microsoft SQL Server Management Studio**、 をクリックして**ファイル**、 をクリックして**開く**、クリックして**ファイル**です。  
  
4.  **ファイルを開く** ダイアログ ボックスで、次の SQL スクリプトを参照します。  
  
    ```  
    %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\BTS_Tracking_ValidateArchive.sql  
    ```  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を実行しているコンピューターから検証サーバーにスクリプトをコピーする必要がある場合があります。  
  
5.  クリックして、**クエリ** メニューをクリックして**Execute**です。  
  
    > [!NOTE]
    >  BTS_Tracking_ValidateArchive.sql スクリプトは、BizTalk 追跡 (BizTalkDTADb) データベースをアーカイブしているフォルダーがネットワーク共有の場合のみ機能します。  
  
     この BTS_Tracking_ValidateArchive.sql スクリプトによって、ValidateArchive という SQL Server エージェント ジョブが作成されます。  
  
6.  アーカイブおよび削除のプロセスは可能性のあるに対するアクセスや、別の SQL Server でデータベースを更新するため、関連する SQL Server インスタンス間のリンク サーバーを設定する必要があります。 **SQL Server Management Studio**をダブルクリックして**Server オブジェクト**を右クリックして**リンク サーバー**、順にクリック**新規リンク サーバー**.  
  
     次のそれぞれの間にリンク サーバーを設定してください。  
  
    -   異なるサーバー上に存在する場合は、各 BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースと BizTalk 追跡 (BizTalkDTADb) データベース。  
  
    -   BizTalk 追跡 (BizTalkDTADb) データベースとアーカイブ検証用の検証サーバー。  
  
    -   BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースをホストしているコンピューター上の SQL Server エージェントのサービス アカウントは、リンク サーバー上の BizTalk 追跡 (BizTalkDTADb) データベースの db_datareader 権限および db_datawriter 権限を持っている必要があります。  
  
    > [!NOTE]
    >  ジョブの実行に使用するアカウントには、両方のデータベースに Database Operator (DBO) 特権が必要です。  
  
7.  **新規リンク サーバー**ダイアログ ボックスの**全般**] ページの [**リンク サーバー**にリンクするサーバーの名前を入力します。  
  
     たとえば、BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベース、BizTalk 追跡 (BizTalkDTADb) データベース、または検証サーバーをホストしているサーバーを指定します。  
  
8.  [**サーバーの種類**、] をクリックして**SQL Server**、順にクリック**OK**です。  
  
9. **Microsoft SQL Server Management Studio**をダブルクリックして**SQL Server エージェント**、クリックして**ジョブ**です。  
  
10. **オブジェクト エクスプ ローラーの詳細** ウィンドウを右クリックして**ValidateArchive**、クリックして**プロパティ**です。  
  
11. **ジョブのプロパティ - ValidateArchive**ダイアログ ボックスで、**ページの選択**をクリックして**手順**です。  
  
12. **ジョブ ステップの一覧**、 をクリックして**検証**、クリックして**編集**です。  
  
13. **全般**] ページの [、**コマンド**ボックスで、コマンドで、 **exec dtasp_ValidateArchive null の場合、null**、置換 null の場合、null では、BizTalk をホストしているサーバーの名前クリックして、単一引用符、二重引用符で囲まれた、BizTalk 追跡データベースの名前を続けて追跡データベースで囲まれた**OK**です。 例:  
  
     **exec dtasp_ValidateArchive '**  *\<TrackingServerName >* **'、'**  *\<TrackingDatabaseName >* **'**  
  
> [!NOTE]
>  ValidateArchive ジョブにはスケジュールが設定されていません。このジョブのスケジュールは構成しないでください。 代わりに、アーカイブが作成されるときに、DTA Purge and Archive (BizTalkDTADb) ジョブがこのジョブを自動的に開始します。  
  
## <a name="see-also"></a>参照  
 [BizTalk 追跡データベースのアーカイブおよび削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)