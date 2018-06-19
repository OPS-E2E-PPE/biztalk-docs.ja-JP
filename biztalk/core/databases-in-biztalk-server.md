---
title: BizTalk Server データベースの |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Notification Services Application database [BAM]
- Archive database [BAM]
- Analysis database [BAM]
- Windows SharePoint Services, content database
- Windows SharePoint Services, configuration database
- TPM database
- BizTalk Server, databases
- Notification Services Instance database [BAM]
- Star Schema database [BAM]
- Primary Import database [BAM]
- Rule Engine database
- databases, BizTalk Server
- SSO database
- Tracking Analysis Server database [BAM]
- Management database
- Tracking database
- MessageBox database
ms.assetid: bb504a26-cae6-4f2a-9b86-3554ef8f6045
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08cd452aa7f56ad7802c1ea458620ed9fcd21047
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22242610"
---
# <a name="databases-in-biztalk-server"></a>BizTalk Server のデータベース
Microsoft BizTalk Server によって、SQL Server にいくつかのデータベースがインストールされます。 このトピックでは、これらのデータベース、およびこれらのデータベースで使用される SQL ロジック グループについて説明します。  

## <a name="database-descriptions"></a>データベースの説明
次の表は、一般的な使用上の特性、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
BizTalk Server ランタイム操作は、通常、最初の 4 つのデータベースを使用します。 BizTalk Server 管理データベース、メッセージ ボックス データベース、追跡データベース、および SSO データベース。 使用するデータベースは、BizTalk Server のどの機能を使うかによって異なります。表に示したデータベースを全部使用する場合も、一部だけを使用する場合もあります。  
  
|データベース|既定のデータベース名|Description|  
|--------------|---------------------------|-----------------|  
|BAM 分析|BAMAnalysis|このデータベースには、オンライン分析用およびオフライン分析用のビジネス アクティビティ監視 (BAM) OLAP キューブが含まれます。|  
|BAM アーカイブ|BAMArchive|このデータベースは、古いビジネス アクティビティ データをアーカイブします。 BAM プライマリ インポート データベースにおけるビジネス アクティビティ データの蓄積を最小限に抑える BAM アーカイブ データベースを作成します。|  
|BAM Notification Services アプリケーション データベース|BAMAlertsApplication|このデータベースには、BAM 通知に関する警告情報が含まれます。 たとえば、BAM ポータルを使用して警告を作成すると、警告に関連する条件とイベントを指定するエントリに加え、警告に関するその他のサポート データ項目がデータベースに挿入されます。|  
|BAM Notification Services インスタンス データベース|BAMAlertsNSMain|このデータベースには、BAM で監視しているシステムに Notification Services が接続する方法を指定するインスタンス情報が格納されます。|  
|BAM プライマリ インポート データベース|BAMPrimaryImport|このデータベースには、BAM によって生の追跡データが収集されます。|  
|BAM スター スキーマ|BAMStarSchema|このデータベースには、段階テーブル、単位テーブル、およびディメンション テーブルが含まれます。|  
|BizTalk 管理データベース|BizTalkMgmtDb|このデータベースには、BizTalk Server のすべてのインスタンスのメタ情報が一元的に保存されます。|  
|BizTalk メッセージ ボックス データベース|BizTalkMsgBoxDb|このデータベースは、ルーティング、キュー処理、インスタンス管理、およびその他のさまざまなタスクを行うために BizTalk Server エンジンによって使用されます。|  
|BizTalk 追跡データベース|BizTalkDTADb|このデータベースには、BizTalk Server 追跡エンジンで追跡した稼働状況の監視データが格納されます。|  
|ルール エンジン データベース|BizTalkRuleEngineDb|このデータベースは以下の項目を格納します。<br /><br /> -ポリシーは、関連するルールのセットが生成されます。<br />-ボキャブラリをルール内でのデータ参照のドメイン固有のわかりやすい名前のコレクションであります。|  
|SSO データベース|SSODB|このエンタープライズ シングル サインオンデータベースは、受信場所の構成情報を安全に格納します。|  
|Windows SharePoint Services 構成データベース|*ユーザー定義*|このデータベースには、サーバーのすべてのグローバル設定が含まれます。|  
|Windows SharePoint Services コンテンツ データベース|*ユーザー定義*|このデータベースには、すべてのサイト コンテンツ (一覧の項目やドキュメントなど) が格納されます。|  

## <a name="database-login-accounts"></a>データベース ログイン アカウント

[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SQL ログイン グループを作成し、SQL Server ロールと次の表に一覧表示されたデータベース ロールにマップします。  
  
|[グループ]|説明|SQL Server ロールまたはデータベース ロール|  
|-----------|-----------------|----------------------------------------|  
|BizTalk Application Users|BizTalk Server の BTSNTSvc.exe プロセスをホストするインプロセス BizTalk ホストにアクセスできるすべてのアカウントが含まれます。  使用している環境のインプロセス ホストごとに 1 つの BizTalk ホスト グループを使用します。|次のデータベースの BTS_HOST_USERS SQL Server データベース ロール<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb<br /><br /> BizTalkDTADb<br /><br /> BAMPrimaryImport<br /><br /> BAMPrimaryImport の BAM_EVENT_WRITER SQL Server データベース ロール|  
|BizTalk 分離ホスト ユーザー|BizTalk 分離ホストにアクセスできるすべてのアカウントが含まれます。 使用している環境の分離ホストごとに 1 つの BizTalk 分離ホスト グループを使用します。|次のデータベースの BTS_HOST_USERS SQL Server データベース ロール<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb<br /><br /> BizTalkDTADb<br /><br /> BAMPrimaryImport|  
|BizTalk Server 管理者|ソリューションの配置、アプリケーションの管理、およびメッセージ処理に関する問題の解決を実行する、すべての BizTalk Server 管理者が含まれます。|次のデータベースの BTS_HOST_USERS SQL Server データベース ロール<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb<br /><br /> BizTalkDTADb<br /><br /> BAMPrimaryImport<br /><br /> 次のデータベースの db_owner SQL Server データベース ロール<br /><br /> BAMStarSchema<br /><br /> BAMPrimaryImport<br /><br /> BAMArchive<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> 次のデータベースの NSAdmin SQL Server データベース ロール<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> BizTalkDTADb<br /><br /> BizTalkMgmtDb<br /><br /> BAMAnalysis OLAP データベースをホストしているコンピューター上の OLAP 管理者。|  
|BizTalk Server オペレータ|権限レベルの低いロールで、監視操作とトラブルシューティング操作にのみアクセスできます。<br /><br /> サービス アカウントは含まれません。|次のデータベースの BTS_OPERATORS SQL Server データベース ロール<br /><br /> BizTalkDTADb<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb|  
|SSO 管理者|エンタープライズ シングル サインオン (SSO) サービスの最上位の管理者。<br /><br /> BizTalk 構成の実行に使用するユーザー アカウントを、このグループに含める必要があります。<br /><br /> エンタープライズ シングル サインオン サービス アカウント、および BizTalk Server および SSO を構成および管理する権限が必要なユーザーまたはグループが含まれます。|SSO の db_owner SQL Server データベース ロール<br /><br /> SSO が配置されている SQL Server の securityadmin SQL Server ロール|  

[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、SQL ログイン アカウントを作成し、次の表に、SQL Server データベース ロールにマップします。  
  
|ユーザー アカウント|説明|SQL データベース ロール|  
|------------------|-----------------|------------------------|  
|ルール エンジン更新サービス|ルール エンジン更新サービスの実行に使用されるユーザー アカウント。|BizTalkRuleEngineDb の RE_HOST_USERS SQL Server データベース ロール|  
|BAM Notification Services ユーザー|BAM Notification Services の実行に使用されるユーザー アカウント。|次のデータベースの NSRunService SQL Server データベース ロール<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> BAMPrimaryImport の BAM_ManagmentNSReader SQL Server データベース ロール|  
|BAM 管理 Web サービス ユーザー|BAM 管理 Web サービスの実行に使用されるユーザー アカウント。|次のデータベースの NSSubscriberAdmin SQL Server データベース ロール<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> BAMPrimaryImport の BAM_ManagementWS SQL Server データベース ロール|  
  
  
## <a name="see-also"></a>参照  
 [データベース構造とジョブ](../core/database-structure-and-jobs.md)   
 [メッセージ ボックス データベース](../core/the-messagebox-database.md)   
 [BizTalk サーバーの保守](../technical-guides/maintaining-biztalk-server-databases.md)   
 [ソリューションの拡張](../core/scaling-your-solutions.md)   
 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)   
 [サービス アカウントとパスワードを変更する方法](../core/how-to-change-service-accounts-and-passwords.md)