---
title: チェックリスト:バックアップし、復元 |Microsoft Docs
ms.custom: ''
ms.date: 01/30/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1d46a59-54f9-483e-9290-f4a9461006a7
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36580fea0389431cc590d44312c026261eb9dfef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357431"
---
# <a name="checklist-backup-and-restore"></a>チェックリスト:バックアップと復元
BizTalk Server システムを復元できるようにするハードウェアの障害が生じる前に、次の手順を実行します。  
  
## <a name="back-up-biztalk-server"></a>BizTalk Server をバックアップします。  
  
|手順|リファレンス|  
|----------|---------------|  
|BizTalk Server システムにすべての変更の記録を保持します。||  
|バックアップし、BizTalk Server を復元するには、適切なアクセス許可があることを確認します。|[セキュリティ保護のための最小ユーザー権限](../core/minimum-security-user-rights.md)|  
|バックアップし、BizTalk Server データベースを復元する方法について説明します。|[バックアップおよび BizTalk Server データベースを復元します。](../core/backing-up-and-restoring-biztalk-server-databases.md)|  
|BizTalk Server データベースをバックアップする BizTalk Server のバックアップ ジョブを構成します。|[BizTalk Server のバックアップ ジョブを構成する方法](../core/how-to-configure-the-backup-biztalk-server-job.md)|  
|データベースのバックアップを保存するサーバーを構成します。|[ログ配布用に送信先システムを構成する方法](../core/how-to-configure-the-destination-system-for-log-shipping.md)|  
|ビジネス アクティビティ監視 (BAM) を使用している場合は、BAM データベースをバックアップします。|[BAM のバックアップと復元](../core/backing-up-and-restoring-bam.md)|  
|エンタープライズ シングル サインオン (SSO) を使用する場合は、マスター シークレットをバックアップします。|[マスター シークレットの管理](../core/managing-the-master-secret.md)|  
|BizTalk Server の構成ファイルをバックアップします。|[BizTalk Server の構成をバックアップする方法](../core/how-to-back-up-the-biztalk-server-configuration.md)|  
|エンタープライズ シングル サインオン マスター シークレットをバックアップします。|[マスター シークレットをバックアップする方法](../core/how-to-back-up-the-master-secret.md)|  
|BAM ポータルのアプリケーション プールと仮想ディレクトリの構成情報をバックアップします。 BAM を使用していない場合は、この手順を実行する必要はありません。|[BAM ポータルをバックアップする方法](../core/how-to-back-up-the-bam-portal.md)|  
|BizTalk アプリケーションをバックアップします。|[BizTalk Server アプリケーションのバックアップ](../core/backing-up-biztalk-server-applications.md)|  
  
## <a name="restore-biztalk-server"></a>BizTalk Server を復元します。  
  
|手順|リファレンス|  
|----------|---------------|  
|データベースを復元します。|[データベースを復元する方法](../core/how-to-restore-your-databases.md)|  
|BAM データベース名への参照を更新します。|[BAM 分析および Tracking Analysis Server データベースをバックアップする方法](../core/how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases.md)<br /><br /> [BAM Analysis Server およびスター スキーマ データベース名への参照を更新する方法](../core/update-references-to-the-bam-analysis-server-and-star-schema-database-names.md)<br /><br /> [BAM アーカイブ データベース名への参照を更新する方法](../core/how-to-update-references-to-the-bam-archive-database-name.md)<br /><br /> [BAM プライマリ インポート データベース名および接続文字列への参照を更新する方法](../core/update-references-to-bam-primary-import-database-name-and-connection-string.md)<br /><br /> [Services データベース、BAM 通知への参照を更新する方法](../core/how-to-update-references-to-the-bam-notification-services-databases.md)<br /><br /> [不完全なアクティビティ インスタンスを解決する方法](../core/how-to-resolve-incomplete-activity-instances.md)|  
|エンタープライズ シングル サインオンを使用する場合は、マスター シークレットを復元します。|[マスター シークレットの管理](../core/managing-the-master-secret.md)|  
|BizTalk Server を実行しているコンピューターが失敗した場合は、BizTalk サーバーを代替コンピューターにインストールします。|[BizTalk Server 2013 および 2013 R2 のインストールの概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)|  
|証明書ストアを復元します。<br /><br /> この手順では、Standard Edition の必要があります。 構成プロセスが自動的にこれがあるために、Enterprise Edition などの他のエディションの必要はありません。|[証明書ストアを復元する方法](../core/how-to-restore-the-certificate-store.md)|  
|エンタープライズ シングル サインオンの復元します。|[エンタープライズ シングル サインオンを復旧する方法](../core/how-to-recover-enterprise-single-sign-on.md)|  
|BizTalk グループを復元します。|[BizTalk グループを回復する方法](../core/how-to-recover-the-biztalk-group.md)<br /><br /> Standard Edition を復元する場合、サーバーの復旧を容易にするスクリプトをダウンロードする必要があります。 ダウンロード[RestoreConfig.vbe](https://www.microsoft.com/download/details.aspx?id=7462)します。|  
|BizTalk Server 構成を復元します。|[BizTalk Server の構成を回復する方法](../core/how-to-recover-the-biztalk-server-configuration.md)|  
|BAM を使用している場合は、BAM 警告を復元する必要があります。<br /><br /> BAM を使用していない場合は、この手順を実行する必要はありません。|[BAM 警告を復旧する方法](../core/how-to-recover-bam-alerts.md)|  
|BAM を使用している場合は、BAM ポータルを復元する必要があります。<br /><br /> BAM を使用していない場合は、この手順を実行する必要はありません。|[BAM ポータルを復旧する方法](../core/how-to-recover-the-bam-portal.md)|  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のバックアップと復元](../core/backing-up-and-restoring-biztalk-server.md)
