---
title: "チェックリスト: バックアップし、復元の |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1d46a59-54f9-483e-9290-f4a9461006a7
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9c9a540467b24374fec7ca5881fef129f582f3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-backup-and-restore"></a>チェックリスト: バックアップと復元
ハードウェア障害に備え、次の手順を実行して BizTalk Server システムを復元できるようにしておいてください。  
  
## <a name="backing-up-biztalk-server"></a>BizTalk Server のバックアップ  
  
|手順|リファレンス|  
|----------|---------------|  
|BizTalk Server システムに対するすべての変更を記録しておきます。||  
|BizTalk Server のバックアップと復元に必要なアクセス許可を取得します。|[セキュリティの最小ユーザー権限](../core/minimum-security-user-rights.md)|  
|BizTalk Server データベースのバックアップと復元の方法を確認します。|[BizTalk Server データベースのバックアップと復元](../core/backing-up-and-restoring-biztalk-server-databases.md)|  
|BizTalk Server データベースをバックアップするための、BizTalk Server のバックアップ ジョブを構成します。|[BizTalk Server のバックアップ ジョブを構成する方法](../core/how-to-configure-the-backup-biztalk-server-job.md)|  
|データベース バックアップの格納先サーバーを構成します。|[ログ配布用に送信先システムを構成する方法](../core/how-to-configure-the-destination-system-for-log-shipping.md)|  
|ビジネス アクティビティ監視 (BAM) を使用している場合は、BAM データベースをバックアップします。|[バックアップおよび BAM を復元します。](../core/backing-up-and-restoring-bam.md)|  
|エンタープライズ シングル サインオン (SSO) を使用している場合は、マスター シークレットをバックアップします。|[マスタ シークレットの管理](../core/managing-the-master-secret.md)|  
|BizTalk Server 構成ファイルをバックアップします。|[BizTalk Server の構成をバックアップする方法](../core/how-to-back-up-the-biztalk-server-configuration.md)|  
|エンタープライズ シングル サインオンのマスター シークレットをバックアップします。|[マスター シークレットをバックアップする方法](../core/how-to-back-up-the-master-secret.md)|  
|BAM ポータル アプリケーション プールと仮想ディレクトリの構成情報をバックアップします。 BAM を使用していない場合、この手順を実行する必要はありません。|[BAM ポータルをバックアップする方法](../core/how-to-back-up-the-bam-portal.md)|  
|BizTalk アプリケーションをバックアップします。|[BizTalk Server アプリケーションをバックアップします。](../core/backing-up-biztalk-server-applications.md)|  
  
## <a name="restoring-biztalk-server"></a>BizTalk Server の復元  
  
|手順|リファレンス|  
|----------|---------------|  
|データベースを復元します。|[データベースを復元する方法](../core/how-to-restore-your-databases.md)|  
|BAM データベース名の参照を更新します。|[バックアップ方法、BAM 分析および Tracking Analysis Server データベース](../core/how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases.md)<br /><br /> [BAM Analysis Server およびスター スキーマ データベース名への参照を更新する方法](../core/update-references-to-the-bam-analysis-server-and-star-schema-database-names.md)<br /><br /> [BAM アーカイブ データベース名への参照を更新する方法](../core/how-to-update-references-to-the-bam-archive-database-name.md)<br /><br /> [BAM プライマリ インポート データベース名および接続文字列への参照を更新する方法](../core/update-references-to-bam-primary-import-database-name-and-connection-string.md)<br /><br /> [Services データベース、BAM 通知への参照を更新する方法](../core/how-to-update-references-to-the-bam-notification-services-databases.md)<br /><br /> [不完全なアクティビティ インスタンスを解決する方法](../core/how-to-resolve-incomplete-activity-instances.md)|  
|エンタープライズ シングル サインオンを使用している場合は、マスター シークレットを復元します。|[マスタ シークレットの管理](../core/managing-the-master-secret.md)|  
|BizTalk Server を実行しているコンピューターで障害が発生した場合は、代わりのコンピューターに BizTalk Server をインストールします。|[BizTalk Server 2013 および 2013 R2 のインストール概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)|  
|証明書ストアを復元します。<br /><br /> この手順は、Standard Edition の場合に必要です。 Enterprise Edition などの他のエディションの場合、この手順は構成プロセスで自動的に行われるので必要ありません。|[証明書ストアを復元する方法](../core/how-to-restore-the-certificate-store.md)|  
|エンタープライズ シングル サインオンを復元します。|[エンタープライズ シングル サインオンを回復する方法](../core/how-to-recover-enterprise-single-sign-on.md)|  
|BizTalk グループを復元します。|[BizTalk グループを回復する方法](../core/how-to-recover-the-biztalk-group.md)<br /><br /> Standard Edition を復元する場合は、サーバーの復元を円滑にするスクリプトをダウンロードする必要があります。 ダウンロード[RestoreConfig.vbe](http://go.microsoft.com/fwlink/?LinkId=195799)です。|  
|BizTalk Server 構成を復元します。|[BizTalk Server の構成を回復する方法](../core/how-to-recover-the-biztalk-server-configuration.md)|  
|BAM を使用している場合は、BAM 警告を復元します。<br /><br /> BAM を使用していない場合、この手順を実行する必要はありません。|[BAM 警告を復旧する方法](../core/how-to-recover-bam-alerts.md)|  
|BAM を使用している場合は、BAM ポータルを復元します。<br /><br /> BAM を使用していない場合、この手順を実行する必要はありません。|[BAM ポータルを復旧する方法](../core/how-to-recover-the-bam-portal.md)|  
  
## <a name="see-also"></a>参照  
 [バックアップおよび BizTalk Server を復元します。](../core/backing-up-and-restoring-biztalk-server.md)