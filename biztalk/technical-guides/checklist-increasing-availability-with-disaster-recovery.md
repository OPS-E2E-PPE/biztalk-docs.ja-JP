---
title: "チェックリスト: 増やす可用性と災害復旧 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b315110-206a-4fa7-9bde-abab1429c83b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8790d82e3e5830e8145a8af2614413936f3e4b55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-increasing-availability-with-disaster-recovery"></a>チェックリスト: 災害復旧と可用性の向上
このトピックの運用環境の可用性を高めるために従う必要のある手順について説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]災害復旧を使用して環境。 通常、災害復旧はフォールト トレランスおよび負荷分散と高可用性を実現する後に実装されます。  
  
## <a name="backing-up-biztalk-server"></a>BizTalk Server のバックアップ  
  
|手順|リファレンス|  
|----------|---------------|  
|すべての変更の記録を維持する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システムです。||  
|バックアップおよび復元するには、適切なアクセス許可があることを確認[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。|参照してください[セキュリティの最小ユーザー権限](http://go.microsoft.com/fwlink/?LinkId=154374)(http://go.microsoft.com/fwlink/?LinkId=154374)|  
|格納する目的での高可用性ファイル共有を作成、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログ。 Windows クラスタ リングを使用して、Windows のサーバー レベルまたは SAN を使用して、ハードウェア レベルでの高可用性ファイル共有を構成します。|参照してください[クラスター上のファイル共有を作成する方法](http://support.microsoft.com/kb/224967)(http://support.microsoft.com/kb/224967)|  
|インストールし、1 つまたは複数のスタンバイを使用できるように[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]の送信先としてインスタンス[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布します。 ハードウェアと変換先の番号[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]の数とハードウェアのインスタンスが一致する必要があります[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]実稼働環境でのインスタンス。 こうと、変換先[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスは、運用環境と同じ負荷を処理できる[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。|参照してください[SQL Server 2008 のインストール](http://go.microsoft.com/fwlink/?LinkId=154377)(http://go.microsoft.com/fwlink/?LinkId=154377)|  
|障害復旧サイトを準備します。|[障害復旧サイトを準備します。](../technical-guides/prepare-the-disaster-recovery-site.md)|  
|バックアップし、復元[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース|-   [バックアップおよびデータベースを復元するためのベスト プラクティス](http://go.microsoft.com/fwlink/?LinkId=157758)(http://go.microsoft.com/fwlink/?LinkId=157758)<br />-   [バックアップおよび BizTalk Server データベースを復元する](http://go.microsoft.com/fwlink/?LinkId=157757)(http://go.microsoft.com/fwlink/?LinkId=157757)|  
|構成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布します。|[ログ配布の BizTalk Server の構成](../technical-guides/configuring-biztalk-server-log-shipping.md)|  
|バックアップを構成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブです。|[バックアップの BizTalk Server ジョブを構成する方法](http://go.microsoft.com/fwlink/?LinkID=154072)(http://go.microsoft.com/fwlink/?LinkID=154072)|  
|バックアップの格納先サーバーを構成します。|[ログ配布用に送信先システムを構成する方法](http://go.microsoft.com/fwlink/?LinkID=151402)(http://go.microsoft.com/fwlink/?LinkID=151402)|  
|ビジネス アクティビティ監視 (BAM) を使用している場合は、BAM データベースをバックアップします。|[BAM 分析をバックアップして、追跡分析サーバー データベース](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)|  
|BAM を使用している場合は、BAM ポータルのアプリケーション プールと仮想ディレクトリの構成情報をバックアップします。 BAM を使用していない場合、この手順を実行する必要はありません。|[BAM ポータルをバックアップする方法](http://go.microsoft.com/fwlink/?LinkId=154378)(http://go.microsoft.com/fwlink/?LinkId=154378)|  
|バックアップを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成ファイル。|[BizTalk Server の構成のバックアップ方法](http://go.microsoft.com/fwlink/?LinkId=154379)(http://go.microsoft.com/fwlink/?LinkId=154379)|  
|エンタープライズ シングル サインオンを使用している場合は、マスター シークレット サーバーをバックアップします。|[マスター シークレットをバックアップする方法](http://go.microsoft.com/fwlink/?LinkID=151395)(http://go.microsoft.com/fwlink/?LinkID=151395)|  
  
## <a name="restoring-biztalk-server"></a>BizTalk Server の復元  
  
|手順|リファレンス|  
|-----------|---------------|  
|BizTalk グループを復元します。|[BizTalk グループを復元します。](../technical-guides/restoring-the-biztalk-group.md)|  
|回復を実行しているランタイム コンピューター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。|[ランタイム コンピューターを回復します。](../technical-guides/recovering-the-runtime-computers.md)|  
|BAM 警告を復旧します。|[BAM 警告を復旧する方法](http://go.microsoft.com/fwlink/?LinkId=154380)(http://go.microsoft.com/fwlink/?LinkId=154380)|  
|BAM ポータルを復旧します。|[BAM ポータルを復旧する方法](http://go.microsoft.com/fwlink/?LinkId=154381)(http://go.microsoft.com/fwlink/?LinkId=154381)|  
|マスター シークレット サーバーを復元します。|[マスター シークレットを復元する方法](http://go.microsoft.com/fwlink/?LinkId=151394)(http://go.microsoft.com/fwlink/?LinkId=151394)|  
|復元、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。|[データベースの復元方法](http://go.microsoft.com/fwlink/?LinkId=151406)(http://go.microsoft.com/fwlink/?LinkId=151406)|  
|BAM データベース名の参照を更新します。|-   [新しい BAM プライマリ インポート データベースへの参照を更新](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_BAMPIRef)<br />-   [新しい BAM アーカイブ データベースへの参照を更新](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArch)<br />-   [新しい BAM スター スキーマ データベースへの参照を更新](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdate)<br />-   [新しい BAM 分析データベースへの参照を更新](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdate)<br />-   [サービスのデータベースを新しい BAM 通知への参照を更新](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdate)<br />-   [不完全なアクティビティ インスタンスの解決方法](http://go.microsoft.com/fwlink/?LinkId=151475)(http://go.microsoft.com/fwlink/?LinkId=151475)|  
  
## <a name="see-also"></a>参照  
 [災害復旧](../technical-guides/disaster-recovery.md)