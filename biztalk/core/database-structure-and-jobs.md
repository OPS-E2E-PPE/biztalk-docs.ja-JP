---
title: データベースの構造とジョブ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PurgeSubscriptionsJob_BizTalkMsgBoxDb job
- MessageBox database, jobs [SQL Server Agent]
- DTA Purge and Archive (BizTalkDTADb) job
- TrackedMessages_Copy_BizTalkMsgBoxDb job
- MessageBox_Message_Cleanup_BizTalkMsgBoxDb job
- MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb job
- Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb job
- jobs [SQL Server Agent], MessageBox database
- CleanupBTFExpiredEntriesJob_BizTalkMgmtDb job
- databases, structure
- Tracking database, jobs [SQL Server Agent]
- jobs [SQL Server Agent], Management database
- Backup BizTalk Server (BizTalkMgmtDb) job
- databases, SQL Server Agent jobs
- Business Rules Engine, jobs [SQL Server Agent]
- jobs, databases
- Management database, jobs [SQL Server Agent]
- MessageBox_UpdateStats_BizTalkMsgBoxDb job
- jobs [SQL Server Agent], Business Rules Engine
- Rules_Database_Cleanup_BizTalkRuleEngineDb job
- MessageBox_Parts_Cleanup_BizTalkMsgBoxDb job
- jobs [SQL Server Agent], Tracking database
- MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb job
ms.assetid: f5f6b17d-0f5e-4821-a7eb-c345234ffc65
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf98ef7fe236261fd3ee65ac6f4695455ba8c704
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240562"
---
# <a name="database-structure-and-jobs"></a>データベース構造とジョブ
このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のデータベース構造とデータベース ジョブについて説明します。  
  
## <a name="database-write-diagram"></a>データベース書き込みダイアグラム  
 次の図は、BizTalk Server データベースに書き込むプロセスとエンティティを示しています。  
  
 ![BizTalk Server データベースに書き込むプロセス](../core/media/ebiz-ops-backup.gif "ebiz_ops_backup")  
  
        Database write diagram showing the processes and entities that write to the BizTalk Server databases  
  
## <a name="biztalk-server-database-jobs"></a>BizTalk Server データベース ジョブ  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、BizTalk Server データベースの管理に役立つ次の SQL Server エージェント ジョブが含まれています。  
  
> [!NOTE]
>  ジョブの名前は、構成時に指定されたデータベース名によって異なります。 使用している環境で複数のメッセージ ボックス データベースが展開されている場合は、各メッセージ ボックスに対して複数のジョブが存在することになります。  
  
> [!WARNING]
>  BizTalk 管理 (BizTalkMgmtDb) データベースでは、という名前のストアド プロシージャは**adm_CleanupMgmtDB**です。 **このストアド プロシージャを実行しないでください。** このストアド プロシージャを実行すると、データベースのエントリがすべて削除されます。  
  
|[ジョブ]|Description|  
|---------|-----------------|  
|BizTalk Server のバックアップ (BizTalkMgmtDb)|このジョブは、BizTalk Server データベースの完全データベース バックアップとログ バックアップを実行します。 構成して、このジョブの実行に関する詳細については、次を参照してください。[をバックアップおよび BizTalk Server データベースの復元](../core/backing-up-and-restoring-biztalk-server-databases.md)です。|  
|CleanupBTFExpiredEntriesJob_BizTalkMgmtDb|このジョブは、BizTalk 管理 (BizTalkMgmtDb) データベース内にある期限が切れた BizTalk Framework (BTF) エントリをクリーンアップします。|  
|DTA Purge and Archive (BizTalkDTADb)|このジョブは、BizTalk 追跡 (BizTalkDTADb) データベースのデータを自動的にアーカイブして古いデータを削除します。 構成して、このジョブの実行に関する詳細については、次を参照してください。[アーカイブ化および BizTalk 追跡データベースを削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)です。|  
|MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb|このジョブは、BizTalk Server ホスト インスタンス (NT サービス) の停止を検出し、そのホスト インスタンスで行われていたすべての作業を解放して、別のホスト インスタンスが作業できるようにします。|  
|MessageBox_Message_Cleanup_BizTalkMsgBoxDb|このジョブは、BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベース テーブルで、サブスクライバーによって参照されなくなったすべてのメッセージを削除します。 **注意:** MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb ジョブによって開始された、スケジュールされていないジョブです。 このジョブを手動で開始しないでください。|  
|MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb|このジョブは、メッセージの参照カウント ログを管理し、サブスクライバーによってジョブが参照されなくなったかどうかを判断します。 **注:** でもこのジョブによって呼び出されるストアド プロシージャがストアド プロシージャを継続的に実行することを確認するためのロジックを含む、1 分ごと 1 回実行するこの SQL Server エージェント ジョブがスケジュールされていると思っています。 この動作は仕様によるものなので、変更しないでください。|  
|MessageBox_Parts_Cleanup_BizTalkMsgBoxDb|このジョブは、BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベース テーブルで、メッセージによって参照されなくなったすべてのメッセージ部分を削除します。 すべてのメッセージは、実際のメッセージ データを含んでいる 1 つまたは複数のメッセージ部分で構成されています。|  
|MessageBox_UpdateStats_BizTalkMsgBoxDb|このジョブは、BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースの統計を手動で更新します。|  
|BizTalk Server の監視|このジョブは、孤立したインスタンスなど、既知の問題について BizTalkMgmtDb、BizTalkMsgBoxDb および BizTalkDTADb データベースをスキャンします。|  
|Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb|このジョブは、複数のメッセージ ボックスを展開する場合に必要です。 下位のメッセージ ボックスに変更を適用した後の、マスター メッセージ ボックスの一括終了などの操作アクションを非同期で実行します。|  
|PurgeSubscriptionsJob_BizTalkMsgBoxDb|このジョブは、使用されていないサブスクリプションの述語を BizTalk Server メッセージ ボックス (BizTalkMsgBoxDb) データベースから削除します。|  
|Rules_Database_Cleanup_BizTalkRuleEngineDb|このジョブは、古い監査データをルール エンジン (BizTalkRuleEngineDb) データベースから 90 日ごとに自動的に削除します。 また、このジョブは、ルール エンジン (BizTalkRuleEngineDb) データベースから 3 日ごとに古い履歴データ (展開/展開解除通知など) を削除します。|  
  
## <a name="see-also"></a>参照  
 [メッセージング エンジン](../core/the-messaging-engine.md)