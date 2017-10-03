---
title: "チェックリスト: がアーカイブ化および BizTalk 追跡データベースを削除 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- archiving [Tracking database], checklist
- checklists, purging [Tracking database]
- purging, checklist
- checklists, archiving [Tracking database]
ms.assetid: dccbf471-2add-498e-b292-287d9a94161b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22e97ac12e6b6b304318f57f309767ec7c63815f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-archiving-and-purging-the-biztalk-tracking-database"></a>チェックリスト: がアーカイブ化および BizTalk 追跡データベースを削除
|手順|リファレンス|  
|----------|---------------|  
|アーカイブと削除の概要を読み、追跡データのアーカイブと削除を行う処理についての理解を深めます。|[BizTalk 追跡データベースのアーカイブおよび削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)|  
|自分のログオン資格情報で DTA Purge and Archive ジョブを実行することもできますが、セキュリティを高めるため、DTA Purge and Archive ジョブを実行するために必要な SQL Server 資格情報を使用して BTS_BACKUP_USERS ロールを構成してください。 そうすることで、特権の昇格を防ぐことができます。|[アーカイブおよび BizTalk 追跡データベースからデータを削除するために BTS_BACKUP_USERS ロールを構成する方法](../core/configure-bts_backup_users-role-to-archive-and-purge-from-tracking-database.md)|  
|DTA Purge and Archive ジョブを構成します。|[DTA Purge and Archive ジョブを構成する方法](../core/how-to-configure-the-dta-purge-and-archive-job.md)|  
|BizTalk 追跡データベース (BizTalkDTADb) のデータをアーカイブして古いデータを削除するため、DTA Purge and Archive ジョブを実行します。|[BizTalk 追跡データベースからデータを削除する方法](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)|  
|BizTalk 追跡データベース (BizTalkDTADb) から手動でデータを削除します (任意)。|[BizTalk 追跡データベースからデータを手動で削除する方法](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)|  
|アーカイブした BizTalk 追跡データベース (BizTalkDTADb) のデータの自動検証を有効にします。|[アーカイブの自動検証を有効にする方法](../core/how-to-enable-automatic-archive-validation.md)|  
|BizTalk 追跡 (BizTalkDTADb) データベースに追跡されるメッセージをコピーします。 これは、DTA Purge and Archive ジョブを使用してデータを削除するために必要です。|[BizTalk 追跡データベースに追跡されるメッセージをコピーする方法](../core/how-to-copy-tracked-messages-into-the-biztalk-tracking-database.md)|  
  
## <a name="see-also"></a>参照  
 [BizTalk 追跡データベースのアーカイブおよび削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)