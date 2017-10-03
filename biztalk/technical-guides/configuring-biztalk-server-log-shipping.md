---
title: "ログ配布の BizTalk Server の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bcef31f7-30d1-4ada-b627-2a5c9ec7e43e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3209d96c4516c603510f3cbb7fb48e3b1eb3209
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-biztalk-server-log-shipping"></a>ログ配布の BizTalk Server の構成
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブを使用すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 送信元システムのすべてのデータベース (ただし、ビジネス アクティビティ監視 (BAM) により使用されているデータベースは除く) をバックアップできます。 送信元システムは、ライブ データが格納されたサーバーまたはサーバーのグループです。 BAM データベースの一部がある別のバックアップおよび復元の要件、ため、これらのデータベースはバックアップはされ、他のメソッドを使用して復元されます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースのバックアップおよび復元は、次の手順で行います。  
  
1.  **BizTalk Server のバックアップ ジョブを構成します。**  
  
     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースをバックアップするには、あらかじめ、送信元システムで [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブを構成しておく必要があります。バックアップが、後から送信先システムでデータベースを復元するときに使用できるフォルダーに自動的に書き込まれるように指定します。 送信先システムは、送信元システムによって生成されたデータベース バックアップを復元するときに使用されるサーバーまたはサーバーのグループです。 この手順の詳細については、次を参照してください。 [Backup BizTalk Server ジョブを構成する方法](../technical-guides/how-to-configure-a-backup-biztalk-server-job.md)です。  
  
2.  **ログ配布用に送信先システムを構成します。**  
  
     送信先システムはログ配布用にも構成する必要があります。ログ配布は、システム障害時のダウンタイムを短縮することを目的とした、スタンバイ サーバーの機能です。 この手順の詳細については、次を参照してください。[を送信先システムを構成する方法](../technical-guides/how-to-configure-the-destination-system.md)です。  
  
3.  **データベースを復元します。**  
  
     ハードウェア障害が発生した場合は、送信先システムに送信されたバックアップおよびログを使用してデータベースを復元できます。 この手順の詳細については、次を参照してください。 [BizTalk Server のバックアップ ジョブでデータベースを復元する方法](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)です。  
  
## <a name="biztalk-server-databases"></a>BizTalk Server データベース  
 次の表で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって使用されるデータベースについて説明し、データベースのバックアップに使用する方法を示します。  
  
### <a name="databases-backed-up-by-the-backup-biztalk-server-job"></a>BizTalk Server のバックアップ ジョブによるデータベースのバックアップ  
 次の表は、BizTalk Server のバックアップ ジョブの一部としてバックアップおよび復元されるデータベースの一覧です。 カスタム データベースがバックアップされるように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブを変更するには、adm_OtherBackupDatabases テーブルにデータベースを追加します。 詳細については、次を参照してください。[カスタム データベースを戻す方法](http://go.microsoft.com/fwlink/?LinkID=151569)(http://go.microsoft.com/fwlink/?LinkID=151569)。  
  
|データベース|既定のデータベース名|Description|  
|--------------|---------------------------|-----------------|  
|BAM プライマリ インポート データベース|BAMPrimaryImport|このデータベースには、ビジネス アクティビティ監視 (BAM) ツールによって未処理の追跡データが収集されます。|  
|BAM Notification Services アプリケーション データベース|BAMAlertsApplication|このデータベースには、BAM 通知に関する警告情報が含まれます。 たとえば、BAM ポータルを使用して警告を作成すると、警告に関連する条件とイベントを指定するエントリに加え、警告に関するその他のサポート データ項目がデータベースに挿入されます。|  
|BAM Notification Services インスタンス データベース|BAMAlertsNSMain|このデータベースには、BAM で監視しているシステムに Notification Services が接続する方法を指定するインスタンス情報が格納されます。|  
|BizTalk 追跡データベース|BizTalkDTADb|このデータベースには、BizTalk Server 追跡エンジンで追跡した稼働状況の監視データが格納されます。|  
|BizTalk 管理データベース|BizTalkMgmtDb|このデータベースには、BizTalk Server のすべてのインスタンスのメタ情報が一元的に保存されます。|  
|BizTalk メッセージ ボックス データベース|BizTalkMsgBoxDb|このデータベースは、ルーティング、キュー処理、インスタンス管理、およびその他のさまざまなタスクを行うために BizTalk Server エンジンによって使用されます。|  
|ルール エンジン データベース|BizTalkRuleEngineDb|このデータベースは以下の項目を格納します。<br /><br /> -ポリシーは、関連するルールのセットが生成されます。<br />-ボキャブラリをルール内でのデータ参照のドメイン固有のわかりやすい名前のコレクションであります。|  
|SSO データベース|SSODB|このエンタープライズ シングル サインオン データベースに安全に格納、構成の情報を受信場所。|  
  
### <a name="databases-backed-up-when-backing-up-the-bam-analysis-and-tracking-analysis-server-databases"></a>データベースがバックアップ時に、BAM 分析および Tracking Analysis Server データベースのバックアップ  
 次の表に、バックアップにプロシージャを使用して、データベース[BAM 分析をバックアップし、追跡分析サーバー データベース](http://msdn.microsoft.com/library/aa578580\(v=bts.70\).aspx):  
  
|データベース|既定のデータベース名|Description|  
|--------------|---------------------------|-----------------|  
|BAM スター スキーマ|BAMStarSchema|このデータベースには、段階テーブル、単位テーブル、およびディメンション テーブルが含まれます。|  
|BAM 分析|BAMAnalysis|このデータベースには、オンライン分析用およびオフライン分析用の BAM OLAP キューブが含まれています。|  
|BAM アーカイブ|BAMArchive|このデータベースは、古いビジネス アクティビティ データをアーカイブします。 BAM プライマリ インポート データベースにおけるビジネス アクティビティ データの蓄積を最小限に抑える BAM アーカイブ データベースを作成します。|  
|Tracking Analysis Server|BizTalkAnalysisDb|このデータベースには、稼動状況の監視のオンライン分析処理 (OLAP) キューブが格納されます。|  
  
 操作ガイドのこのセクションでは、BizTalk Server 構成に従う必要のある追加の手順をについて説明しますログ配布します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ソース システムを構成します。](../technical-guides/configuring-the-source-system.md)  
  
-   [送信先システムを構成する方法](../technical-guides/how-to-configure-the-destination-system.md)  
  
-   [BizTalk Server に対してログ配布を他のデータベースを構成します。](../technical-guides/configuring-biztalk-server-log-shipping-for-additional-databases.md)  
  
-   [ログ配布の BizTalk Server の監視](../technical-guides/monitoring-biztalk-server-log-shipping.md)