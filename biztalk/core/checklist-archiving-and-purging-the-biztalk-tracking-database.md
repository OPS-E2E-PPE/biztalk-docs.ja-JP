---
title: チェックリスト:アーカイブおよび BizTalk 追跡データベースの削除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- archiving [Tracking database], checklist
- checklists, purging [Tracking database]
- purging, checklist
- checklists, archiving [Tracking database]
ms.assetid: dccbf471-2add-498e-b292-287d9a94161b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59ceb1ed0c31f3b984a38f4a6890e42e289d10dc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357461"
---
# <a name="checklist-archiving-and-purging-the-biztalk-tracking-database"></a>チェックリスト:BizTalk 追跡データベースのアーカイブおよび削除

|手順|リファレンス|  
|----------|---------------|  
|追跡データ アーカイブおよび削除のプロセスの理解を深め、アーカイブと削除の概要を読み取ります。|[BizTalk 追跡データベースのアーカイブおよび削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)|  
|DTA Purge and Archive ジョブのセキュリティを高めるため、ログオン資格情報を使用して行うことができますが、DTA Purge and Archive ジョブを実行するために必要な SQL Server 資格情報を持つために BTS_BACKUP_USERS ロールを構成してください。 これは、特権の昇格を防ぐのに役立ちます。|[アーカイブおよび BizTalk 追跡データベースからデータを削除のために BTS_BACKUP_USERS ロールを構成する方法](../core/configure-bts_backup_users-role-to-archive-and-purge-from-tracking-database.md)|  
|DTA Purge and Archive ジョブを構成します。|[構成の DTA Purge and Archive ジョブをする方法](../core/how-to-configure-the-dta-purge-and-archive-job.md)|  
|DTA Purge and Archive ジョブを BizTalk 追跡 (BizTalkDTADb) データベース内のデータをアーカイブして古いデータの削除を実行します。|[BizTalk 追跡データベースからデータを削除する方法](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)|  
|必要に応じて、BizTalk 追跡 (BizTalkDTADb) データベースからデータを手動で消去することができます。|[BizTalk 追跡データベースからデータを手動で削除する方法](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)|  
|BizTalk 追跡 (BizTalkDTADb) データベースからアーカイブされたデータの自動検証を有効にします。|[アーカイブの自動検証を有効にする方法](../core/how-to-enable-automatic-archive-validation.md)|  
|追跡メッセージは、BizTalk 追跡 (BizTalkDTADb) データベースにコピーします。 これは、DTA Purge and Archive ジョブを使用してデータを削除するために必要です。|[追跡メッセージを BizTalk 追跡データベースにコピーする方法](../core/how-to-copy-tracked-messages-into-the-biztalk-tracking-database.md)|  

## <a name="see-also"></a>参照  
 [BizTalk 追跡データベースのアーカイブおよび削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)