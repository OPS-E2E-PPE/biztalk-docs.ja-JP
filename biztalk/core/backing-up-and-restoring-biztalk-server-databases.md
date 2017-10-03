---
title: "バックアップと BizTalk Server データベースを復元 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up [BAM]
- databases, backing up
- databases, restoring
- backing up, restoring
- backing up, databases
- restoring, BAM
- backing up, BAM
- backing up, backup jobs
- BAM, restoring
- restoring, databases
- restoring [BAM]
- BAM, backing up
ms.assetid: 82fc1af2-1389-4c79-80dc-f2df5656d201
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dba0e9e7cb5d01bf845eaa4adf3557dc3b6ea34a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="backing-up-and-restoring-biztalk-server-databases"></a>バックアップおよび BizTalk Server データベースを復元します。
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブを使用すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 送信元システムのすべてのデータベース (ただし、ビジネス アクティビティ監視 (BAM) により使用されているデータベースは除く) をバックアップできます。 送信元システムは、ライブ データが格納されたサーバーまたはサーバーのグループです。 BAM データベースはバックアップおよび復元の要件が異なるので、これらのデータベースについては別の方法を使用してバックアップおよび復元を行います。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースのバックアップおよび復元は、次の手順で行います。  
  
1.  **BizTalk Server のバックアップ ジョブを構成します。**  
  
     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースをバックアップするには、あらかじめ、送信元システムで [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブを構成しておく必要があります。バックアップが、後から送信先システムでデータベースを復元するときに使用できるフォルダーに自動的に書き込まれるように指定します。 送信先システムは、送信元システムによって生成されたデータベース バックアップを復元するときに使用されるサーバーまたはサーバーのグループです。 この手順の詳細については、次を参照してください。[を BizTalk Server のバックアップ ジョブを構成する方法](../core/how-to-configure-the-backup-biztalk-server-job.md)です。  
  
2.  **ログ配布用に送信先システムを構成します。**  
  
     送信先システムはログ配布用にも構成する必要があります。ログ配布は、システム障害時のダウンタイムを短縮することを目的とした、スタンバイ サーバーの機能です。 この手順の詳細については、次を参照してください。[ログ配布用に送信先システムを構成する方法](../core/how-to-configure-the-destination-system-for-log-shipping.md)です。  
  
3.  **データベースを復元します。**  
  
     ハードウェア障害が発生した場合は、送信先システムに送信されたバックアップおよびログを使用してデータベースを復元できます。 この手順の詳細については、次を参照してください。 [、データベースを復元する方法](../core/how-to-restore-your-databases.md)です。  
  
## <a name="biztalk-server-databases"></a>BizTalk Server データベース  
 次の表で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって使用されるデータベースについて説明し、データベースのバックアップに使用する方法を示します。  
  
### <a name="databases-backed-up-by-the-backup-biztalk-server-job"></a>BizTalk Server のバックアップ ジョブによるデータベースのバックアップ  
 次の表は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブの一部としてバックアップおよび復元されるデータベースの一覧です。 カスタム データベースがバックアップされるように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のバックアップ ジョブを変更するには、adm_OtherBackupDatabases テーブルにデータベースを追加します。 詳細については、次を参照してください。[カスタム データベースを戻す方法](../core/how-to-back-up-custom-databases.md)です。  
  
|データベース|既定のデータベース名|Description|  
|--------------|---------------------------|-----------------|  
|BAM プライマリ インポート データベース|BAMPrimaryImport|このデータベースには、ビジネス アクティビティ監視 (BAM) ツールによって未処理の追跡データが収集されます。|  
|BAM Notification Services アプリケーション データベース|BAMAlertsApplication|このデータベースには、BAM 通知に関する警告情報が含まれます。 たとえば、BAM ポータルを使用して警告を作成すると、警告に関連する条件とイベントを指定するエントリに加え、警告に関するその他のサポート データ項目がデータベースに挿入されます。|  
|BAM Notification Services インスタンス データベース|BAMAlertsNSMain|このデータベースには、BAM で監視しているシステムに Notification Services が接続する方法を指定するインスタンス情報が格納されます。|  
|BizTalk 追跡データベース|BizTalkDTADb|このデータベースには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 追跡エンジンで追跡した稼働状況の監視データが格納されます。|  
|BizTalk 管理データベース|BizTalkMgmtDb|このデータベースには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のすべてのインスタンスのメタ情報が一元的に保存されます。|  
|BizTalk メッセージ ボックス データベース|BizTalkMsgBoxDb|このデータベースは、ルーティング、キュー処理、インスタンス管理、およびその他のさまざまなタスクを行うために [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] エンジンによって使用されます。|  
|ルール エンジン データベース|BizTalkRuleEngineDb|このデータベースは以下の項目を格納します。<br /><br /> -ポリシーは、関連するルールのセットが生成されます。<br />-ボキャブラリをルール内でのデータ参照のドメイン固有のわかりやすい名前のコレクションであります。|  
|SSO データベース|SSODB|このエンタープライズ シングル サインオンデータベースは、受信場所の構成情報を安全に格納します。|  
  
### <a name="databases-backed-up-by-the-bam-backup-process"></a>BAS バックアップ プロセスによりバックアップされるデータベース  
 次の表に、データベースをバックアップおよび復元の手順を使用して[をバックアップおよび復元する BAM](../core/backing-up-and-restoring-bam.md):  
  
|データベース|既定のデータベース名|Description|  
|--------------|---------------------------|-----------------|  
|BAM スター スキーマ|BAMStarSchema|このデータベースには、段階テーブル、単位テーブル、およびディメンション テーブルが含まれます。|  
|BAM 分析|BAMAnalysis|このデータベースには、オンライン分析用およびオフライン分析用の BAM OLAP キューブが含まれています。|  
|BAM アーカイブ|BAMArchive|このデータベースは、古いビジネス アクティビティ データをアーカイブします。 BAM プライマリ インポート データベースにおけるビジネス アクティビティ データの蓄積を最小限に抑える BAM アーカイブ データベースを作成します。|  
|Tracking Analysis Server|BizTalkAnalysisDb|このデータベースには、稼動状況の監視のオンライン分析処理 (OLAP) キューブが格納されます。|  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Server のバックアップ ジョブを構成する方法](../core/how-to-configure-the-backup-biztalk-server-job.md)  
  
-   [ログ配布用に送信先システムを構成する方法](../core/how-to-configure-the-destination-system-for-log-shipping.md)  
  
-   [データベースを復元する方法](../core/how-to-restore-your-databases.md)  
  
-   [バックアップおよび SQL エージェント ジョブを復元する方法](../core/how-to-back-up-and-restore-sql-agent-jobs.md)  
  
-   [バックアップおよび SQL Server ログインを復元する方法](../core/how-to-back-up-and-restore-sql-server-logins.md)