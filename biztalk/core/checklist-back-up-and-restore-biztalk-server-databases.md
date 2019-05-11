---
title: チェックリスト:バックアップおよび BizTalk Server データベースを復元する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, BizTalk Server
- restoring, checklists
- maintaining, restoring
- maintaining, checklists
- restoring, BizTalk Server
- maintaining, backing up
- checklists, backing up
- backing up, checklists
- BizTalk Server, backing up
- checklists, restoring
- BizTalk Server, restoring
ms.assetid: 12f7e02e-57b1-4e55-8e44-7fe2d7920f5a
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3233d941e17e23e07895586b711d47ee86cdc15
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357454"
---
# <a name="checklist-back-up-and-restore-biztalk-server-databases"></a>チェックリスト:バックアップおよび BizTalk Server データベースを復元します。
をバックアップまたは BizTalk Server を復元する前に、関連するプロセスについて理解することを確認します。  
  
## <a name="backing-up-biztalk-server"></a>BizTalk Server のバックアップ  
  
|手順|リファレンス|  
|----------|---------------|  
|バックアップを作成して、BizTalk Server を復元する方法について説明します。|[データベースのバックアップと復元のベスト プラクティス](../core/best-practices-for-backing-up-and-restoring-databases.md)<br /><br /> [バックアップおよび BizTalk Server データベースを復元します。](../core/backing-up-and-restoring-biztalk-server-databases.md)|  
|バックアップし、BizTalk Server を復元するには、適切なアクセス許可があることを確認します。|[セキュリティ保護のための最小ユーザー権限](../core/minimum-security-user-rights.md)|  
|BizTalk Server のバックアップ ジョブを構成します。|[BizTalk Server のバックアップ ジョブを構成する方法](../core/how-to-configure-the-backup-biztalk-server-job.md)|  
|バックアップの格納先サーバーを構成します。|[ログ配布用に送信先システムを構成する方法](../core/how-to-configure-the-destination-system-for-log-shipping.md)|  
|ビジネス アクティビティ監視 (BAM) を使用している場合は、BAM データベースをバックアップします。|[BAM のバックアップと復元](../core/backing-up-and-restoring-bam.md)|  
|エンタープライズ シングル サインオンを使用する場合は、マスター シークレットをバックアップします。|[マスター シークレットの管理](../core/managing-the-master-secret.md)|  
  
## <a name="restoring-biztalk-server"></a>BizTalk Server の復元  
  
|手順|リファレンス|  
|----------|---------------|  
|データベースを復元します。|[データベースを復元する方法](../core/how-to-restore-your-databases.md)|  
|BAM データベース名への参照を更新します。|[BAM 分析および Tracking Analysis Server データベースをバックアップする方法](../core/how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases.md)<br /><br /> [BAM Analysis Server およびスター スキーマ データベース名への参照を更新する方法](../core/update-references-to-the-bam-analysis-server-and-star-schema-database-names.md)<br /><br /> [BAM アーカイブ データベース名への参照を更新する方法](../core/how-to-update-references-to-the-bam-archive-database-name.md)<br /><br /> [BAM プライマリ インポート データベース名および接続文字列への参照を更新する方法](../core/update-references-to-bam-primary-import-database-name-and-connection-string.md)<br /><br /> [Services データベース、BAM 通知への参照を更新する方法](../core/how-to-update-references-to-the-bam-notification-services-databases.md)<br /><br /> [不完全なアクティビティ インスタンスを解決する方法](../core/how-to-resolve-incomplete-activity-instances.md)|  
|エンタープライズ シングル サインオンを使用する場合は、マスター シークレットを復元します。|[マスター シークレットの管理](../core/managing-the-master-secret.md)|  
  
## <a name="see-also"></a>参照  
 [BizTalk Server データベースのバックアップと復元](../core/backing-up-and-restoring-the-biztalk-server-databases.md)