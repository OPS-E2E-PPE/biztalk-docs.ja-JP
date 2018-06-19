---
title: 'チェックリスト: をバックアップし、BizTalk Server データベースを復元 |Microsoft ドキュメント'
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
ms.openlocfilehash: 7f3c8c68eb62273562b0f703ae79c0db76ec837c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232706"
---
# <a name="checklist-back-up-and-restore-biztalk-server-databases"></a>チェックリスト: をバックアップし、BizTalk Server データベースの復元
BizTalk Server をバックアップまたは復元する場合は、あらかじめ必要な作業を把握しておくことが大切です。  
  
## <a name="backing-up-biztalk-server"></a>BizTalk Server のバックアップ  
  
|手順|リファレンス|  
|----------|---------------|  
|BizTalk Server のバックアップと復元の方法を確認します。|[バックアップおよびデータベースを復元するためのベスト プラクティス](../core/best-practices-for-backing-up-and-restoring-databases.md)<br /><br /> [BizTalk Server データベースのバックアップと復元](../core/backing-up-and-restoring-biztalk-server-databases.md)|  
|BizTalk Server のバックアップと復元に必要なアクセス許可を取得します。|[セキュリティの最小ユーザー権限](../core/minimum-security-user-rights.md)|  
|BizTalk Server のバックアップ ジョブを構成します。|[BizTalk Server のバックアップ ジョブを構成する方法](../core/how-to-configure-the-backup-biztalk-server-job.md)|  
|バックアップの格納先サーバーを構成します。|[ログ配布用に送信先システムを構成する方法](../core/how-to-configure-the-destination-system-for-log-shipping.md)|  
|ビジネス アクティビティ監視 (BAM) を使用している場合は、BAM データベースをバックアップします。|[バックアップおよび BAM を復元します。](../core/backing-up-and-restoring-bam.md)|  
|エンタープライズ シングル サインオンを使用している場合は、マスター シークレットをバックアップします。|[マスタ シークレットの管理](../core/managing-the-master-secret.md)|  
  
## <a name="restoring-biztalk-server"></a>BizTalk Server の復元  
  
|手順|リファレンス|  
|----------|---------------|  
|データベースを復元します。|[データベースを復元する方法](../core/how-to-restore-your-databases.md)|  
|BAM データベース名の参照を更新します。|[バックアップ方法、BAM 分析および Tracking Analysis Server データベース](../core/how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases.md)<br /><br /> [BAM Analysis Server およびスター スキーマ データベース名への参照を更新する方法](../core/update-references-to-the-bam-analysis-server-and-star-schema-database-names.md)<br /><br /> [BAM アーカイブ データベース名への参照を更新する方法](../core/how-to-update-references-to-the-bam-archive-database-name.md)<br /><br /> [BAM プライマリ インポート データベース名および接続文字列への参照を更新する方法](../core/update-references-to-bam-primary-import-database-name-and-connection-string.md)<br /><br /> [Services データベース、BAM 通知への参照を更新する方法](../core/how-to-update-references-to-the-bam-notification-services-databases.md)<br /><br /> [不完全なアクティビティ インスタンスを解決する方法](../core/how-to-resolve-incomplete-activity-instances.md)|  
|エンタープライズ シングル サインオンを使用している場合は、マスター シークレットを復元します。|[マスタ シークレットの管理](../core/managing-the-master-secret.md)|  
  
## <a name="see-also"></a>参照  
 [バックアップと、BizTalk Server データベースの復元](../core/backing-up-and-restoring-the-biztalk-server-databases.md)