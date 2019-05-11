---
title: アーカイブの自動検証を有効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, archives [Tracking database]
- archiving [Tracking database], validating archive
ms.assetid: 406ca54a-6b1f-4bdb-9bad-bea5ea0f6e66
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 257e6de9ce64b8d9e1f2c27bd401b453a1a47cda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337981"
---
# <a name="how-to-enable-automatic-archive-validation"></a>アーカイブの自動検証を有効にする方法
アーカイブの検証が作成されるときに、アーカイブを検証することができます。 アーカイブの自動検証を有効にする前に、検証サーバーとも呼ばれます。 セカンダリ データベース サーバーを設定する必要があります。 アーカイブ プロセスは、単純なバックアップであるために、ハードウェアの問題のため、ディスクに格納されている実際の画像を破損することが可能なです。  
  
 アーカイブ検証機能を使用して、アーカイブ (バックアップ) が成功し、復元することを保証できます。 アーカイブが作成されると、新しいアーカイブが作成されている検証サーバーに通知されます。 検証サーバーは、アーカイブを復元しようとします。 検証サーバーは別のインスタンスである必要があります[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ジョブが実行されているものと異なる。 バージョンの[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]サーバー検証と同じバージョンをする必要があります、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースをホストするために使用します。  
  
 復元が成功した場合は、検証サーバーは、BizTalk 追跡 (BizTalkDTADb) データベースに戻すには、この情報を通信します。 成功した復元が完了するまで、purge ジョブは、これ以上データが削除されません。  
  
 復元が成功しなかった場合、検証サーバーは、BizTalk 追跡データベースに戻すには、この情報を通信します。 Purge ジョブでは、別のアーカイブを作成し、新しいアーカイブの検証を待機します。 これには、アーカイブの破損が追跡データが失われる可能性ができないようにします。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定サーバー ロールのメンバーであるアカウントを使用してログオンする必要があります。  
  
### <a name="to-enable-automatic-archive-validation"></a>アーカイブの自動検証を有効にするには  
  
1. 検証サーバーで、をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP2**、 をクリックし、 **SQL Server Management Studio**.  
  
2. **サーバーへの接続** ダイアログ ボックスでの名前を指定します、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 、復元プロセスのテストを実行してアーカイブをクリックできます**Connect**への接続に、適切な SQL Server。  
  
   > [!NOTE]
   >  このサーバーしないで別[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース サーバーのアーカイブを検証するときに、システム パフォーマンスが低下します。  
  
3. **Microsoft SQL Server Management Studio**、 をクリックして**ファイル**、 をクリックして**オープン**、 をクリックし、**ファイル**します。  
  
4. **ファイルを開く** ダイアログ ボックスで、次の SQL スクリプトを参照します。  
  
   ```  
   %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\BTS_Tracking_ValidateArchive.sql  
   ```  
  
   > [!NOTE]
   >  スクリプトを実行しているコンピューターからコピーする必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]検証サーバーにします。  
  
5. をクリックして、**クエリ** メニューをクリック**Execute**します。  
  
   > [!NOTE]
   >  この BTS_Tracking_ValidateArchive.sql スクリプトは、BizTalk 追跡 (BizTalkDTADb) データベースをアーカイブするフォルダーがネットワーク共有である場合にのみ機能します。  
  
    この BTS_Tracking_ValidateArchive.sql スクリプトは、ValidateArchive という SQL Server エージェント ジョブを作成します。  
  
6. アーカイブおよび削除のプロセスは可能性のあるアクセスや、別の SQL Server でデータベースを更新するため、関連する SQL Server インスタンス間のリンク サーバーを設定する必要があります。 **SQL Server Management Studio**、 をダブルクリックします**サーバー オブジェクト**、右クリック**リンク サーバー**、順にクリックします**新しいリンク サーバー**.  
  
    間にリンク サーバーを設定する必要があります。  
  
   -   各 BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースと異なるサーバー上に存在する場合、BizTalk 追跡 (BizTalkDTADb) データベース。  
  
   -   BizTalk 追跡 (BizTalkDTADb) データベースとアーカイブ検証用の検証サーバー。  
  
   -   BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースをホストするコンピューター上の SQL Server エージェント サービス アカウント、リンク サーバーで、BizTalk 追跡 (BizTalkDTADb) データベースの db_datareader と db_datawriter 権限が必要です。  
  
   > [!NOTE]
   >  ジョブの実行に使用されるアカウントは、両方のデータベースに Database Operator (DBO) 特権が必要です。  
  
7. **新しいリンク サーバー**  ダイアログ ボックスで、**全般** ページの **リンク サーバー**にリンクするサーバーの名前を入力します。  
  
    たとえば、BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベース、BizTalk 追跡 (BizTalkDTADb) データベース、または検証サーバーをホストしているサーバー。  
  
8. [**サーバーの種類**、] をクリックして**SQL Server**、順にクリックします**OK**します。  
  
9. **Microsoft SQL Server Management Studio**、ダブルクリックして**SQL Server エージェント**、順にクリックします**ジョブ**します。  
  
10. **オブジェクト エクスプ ローラーの詳細**ウィンドウで、右クリック**ValidateArchive**、 をクリックし、**プロパティ**。  
  
11. **ジョブのプロパティ - ValidateArchive**ダイアログ ボックスで、**ページの選択**、 をクリックして**手順**します。  
  
12. **ジョブ ステップの一覧**、 をクリックして**検証**、 をクリックし、**編集**します。  
  
13. **全般**] ページの [、**コマンド**ボックスで、コマンドで、 **exec dtasp_ValidateArchive null の場合、null**、置換 null の場合、null では、BizTalk をホストするサーバーの名前追跡で囲まれたデータベースの単一引用符、二重引用符で囲まれた、BizTalk 追跡データベースの名前が続くし、順にクリックします**OK**します。 以下に例を示します。  
  
     **exec dtasp_ValidateArchive '** *\<TrackingServerName\>* **', '** *\<TrackingDatabaseName\>* **'**  
  
> [!NOTE]
>  ValidateArchive ジョブにスケジュールがないし、そのスケジュールを構成しないでください。 代わりに、DTA Purge and Archive (BizTalkDTADb) ジョブの開始、アーカイブの作成時に自動的には、このジョブ。  
  
## <a name="see-also"></a>参照  
 [BizTalk 追跡データベースのアーカイブおよび削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)