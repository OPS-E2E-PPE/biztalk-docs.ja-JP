---
title: データベースの構造とジョブ |Microsoft Docs
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
ms.openlocfilehash: f5cf9b5ec724e0070b7425732a74c50d3873bd67
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352588"
---
# <a name="database-structure-and-jobs"></a>データベース構造とジョブ
このトピックでは、データベースの構造とデータベース ジョブについて説明します。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
## <a name="database-write-diagram"></a>データベース書き込みダイアグラム  
 次の図は、プロセスと、BizTalk Server データベースに書き込むエンティティを示します。  
  
 ![BizTalk Server データベースに書き込むプロセス](../core/media/ebiz-ops-backup.gif "ebiz_ops_backup")  
  
        Database write diagram showing the processes and entities that write to the BizTalk Server databases  
  
## <a name="biztalk-server-database-jobs"></a>BizTalk Server データベース ジョブ  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BizTalk Server データベースの管理に役立つ次の SQL Server エージェント ジョブが含まれています。  
  
> [!NOTE]
>  ジョブの名前は、構成時に指定されたデータベース名によって変化します。 環境内で複数のメッセージ ボックス データベースを展開した場合は、各メッセージ ボックスに対して複数のジョブがあります。  
  
> [!WARNING]
>  BizTalk 管理 (BizTalkMgmtDb) データベースでは、という名前のストアド プロシージャ**adm_CleanupMgmtDB**します。 **このストアド プロシージャを実行できません。** このストアド プロシージャを実行する場合は、データベース内のすべてのエントリが削除されます。  
  
|[ジョブ]|説明|  
|---------|-----------------|  
|BizTalk Server (BizTalkMgmtDb) のバックアップします。|このジョブは、データベース全体と、BizTalk Server データベースのログ バックアップを実行します。 構成して、このジョブを実行する方法の詳細についてを参照してください。 [Backing Up and BizTalk Server データベースの復元](../core/backing-up-and-restoring-biztalk-server-databases.md)します。|  
|CleanupBTFExpiredEntriesJob_BizTalkMgmtDb|このジョブは、BizTalk 管理 (BizTalkMgmtDb) データベースの有効期限が切れた BizTalk Framework (BTF) エントリをクリーンアップします。|  
|DTA Purge and Archive (BizTalkDTADb)|このジョブを自動的に BizTalk 追跡 (BizTalkDTADb) データベース内のデータをアーカイブして古いデータを削除します。 構成して、このジョブを実行する方法の詳細についてを参照してください。[アーカイブおよび BizTalk 追跡データベースの削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)します。|  
|MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb|このジョブは、BizTalk Server ホスト インスタンス (NT サービス) が停止し、別のホスト インスタンスによってに作業できるように、そのホスト インスタンスで行われていたすべての作業を解放するときに検出します。|  
|MessageBox_Message_Cleanup_BizTalkMsgBoxDb|このジョブは、不要になった BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースのテーブルで、サブスクライバーによって参照されているすべてのメッセージを削除します。 **注意が必要です。** これは、MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb ジョブによって起動される、スケジュールされていないジョブです。 この仕事を手動で開始します。|  
|MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb|このジョブは、メッセージの参照カウント ログを管理し、メッセージは、サブスクライバーによって参照されなくなったときに決定します。 **注:** この SQL Server エージェント ジョブをスケジュール設定すると、このジョブによって呼び出されるストアド プロシージャには、1 分ごとには、ストアド プロシージャを継続的に実行することを確認するためのロジックが含まれています考えられています。 これは、デザインの動作ではあり、変更しないでください。|  
|MessageBox_Parts_Cleanup_BizTalkMsgBoxDb|このジョブは、不要になった BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースのテーブルで、メッセージによって参照されているすべてのメッセージ部分を削除します。 すべてのメッセージは実際のメッセージ データを含む 1 つまたは複数のメッセージ部分で構成されます。|  
|MessageBox_UpdateStats_BizTalkMsgBoxDb|このジョブは、BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベースの統計を手動で更新します。|  
|BizTalk Server を監視します。|このジョブのスキャン、BizTalkMgmtDb、BizTalkMsgBoxDb および BizTalkDTADb データベースなど、既知の問題を孤立したインスタンス。|  
|Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb|このジョブは、複数のメッセージ ボックスの展開に必要です。 非同期的に、下位のメッセージ ボックスにそれらの変更が適用された後に、マスター メッセージ ボックスの一括終了などの操作を実行します。|  
|PurgeSubscriptionsJob_BizTalkMsgBoxDb|このジョブは、BizTalk Server メッセージ ボックス (BizTalkMsgBoxDb) データベースから未使用のサブスクリプションの述語を削除します。|  
|Rules_Database_Cleanup_BizTalkRuleEngineDb|このジョブに自動的に古い監査データ削除ルール エンジン (BizTalkRuleEngineDb) データベースから 90 日ごと。 このジョブも古い履歴データ (展開/展開解除通知) ルール エンジン (BizTalkRuleEngineDb) データベースから 3 日ごと削除します。|  
  
## <a name="see-also"></a>参照  
 [メッセージング エンジン](../core/the-messaging-engine.md)