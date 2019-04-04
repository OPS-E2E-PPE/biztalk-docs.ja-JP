---
title: Windows グループと BizTalk Server でのユーザー アカウント |Microsoft Docs
ms.custom: ''
ms.date: 09/27/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, BTS_ADMIN_USERS role [SQL Server database]
- MessageBox database, BTS_HOST_USERS role [SQL Server database]
- Rule Engine database, BTS_HOST_USERS role [SQL Server database]
- Management database, BTS_OPERATORS role [SQL Server database]
- BTS_HOST_USERS role [SQL Server database]
- NSSubscriberAdmin role [SQL Server database]
- Management database, tpm_user role [SQL Server database]
- SSO, securityadmin role [SQL Server database]
- IIS_WPG group
- BAM Notification service account
- EDI_ADMIN_USERS role [SQL Server database]
- Archive database [BAM], db_owner role [SQL Server database]
- Primary Import database [BAM], db_owner role [SQL Server database]
- Primary Import database [BAM], BAM_EVENT_WRITER role [SQL Server database]
- Notification Services Application database [BAM], db_owner role [SQL Server database]
- NSRunService role [SQL Server database]
- RE_HOST_USERS role [SQL Server database]
- MessageBox database, BTS_OPERATORS role [SQL Server database]
- Rule Engine database, RE_HOST_USERS role [SQL Server database]
- Windows groups, creating
- securityadmin role [SQL Server database]
- BizTalk Isolated Host Instance service account
- In-Process BizTalk Host groups
- Primary Import database [BAM], BTS_ADMIN_USERS role [SQL Server database]
- SSO Affiliate Administrators [Windows group]
- Star Schema database [BAM], db_owner role [SQL Server database]
- Notification Services Instance database [BAM], db_owner role [SQL Server database]
- MessageBox database, BTS_ADMIN_USERS role [SQL Server database]
- Rule Engine Update Service account
- Configuration Manager, creating user accounts
- SSO Administrators [Windows group]
- Rule Engine database, BTS_ADMIN_USERS role [SQL Server database]
- Tracking database, BTS_OPERATORS role [SQL Server database]
- Primary Import database [BAM], BAM_ManagementNSReader role [SQL Server database]
- Notification Services Instance database [BAM], role [SQL Server database]
- BizTalk Application Users [Windows group]
- user accounts, creating
- Rule Engine database, BTS_OPERATORS role [SQL Server database]
- STS_WPG group
- BAM_ManagementWS role [SQL Server database]
- BTS_OPERATORS role [SQL Server database]
- Tracking database, BTS_HOST_USERS role [SQL Server database]
- SSO, db_owner role [SQL Server database]
- Notification Services Application database [BAM], role [SQL Server database]
- OLAP Administrators
- BAM_EVENT_WRITER role [SQL Server database]
- Windows groups, group list
- tpm_user role [SQL Server database]
- BizTalk Host Instance service account
- Base DBI database, EDI_ADMIN_USERS role [SQL Server database]
- Primary Import database [BAM], role [SQL Server database]
- BizTalk SharePoint Adapter Enabled Hosts [Windows group]
- BAM Management Web service account
- db_owner role [SQL Server database]
- Management database, BTS_ADMIN_USERS role [SQL Server database]
- Configuration Manager, creating groups
- Management database, BTS_HOST_USERS role [SQL Server database]
- BizTalk Server Operators [Windows group]
- Base DBI database, BTS_OPERATORS role [SQL Server database]
- Enterprise Single Sign-On Service account
- NSAdmin role [SQL Server database]
- BAM_ManagementNSReader role [SQL Server database]
- Notification Services Application database [BAM], NSRunService role [SQL Server database]
- BTS_ADMIN_USERS role [SQL Server database]
- BizTalk Isolated Host Users [Windows group]
- Notification Services Instance database [BAM], NSAdmin role [SQL Server database]
- SQLServer2005NotificationServicesUser
- EDI Subsystem Users [Windows group]
- Primary Import database [BAM], BTS_HOST_USERS role [SQL Server database]
- BizTalk Server Administrators [Windows group]
- BAM Portal Users [Windows group]
- Notification Services Application database [BAM], NSAdmin role [SQL Server database]
ms.assetid: a01603bd-4105-4691-819d-de43b00b40f3
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26a9cc092ed8d5747c7f6b7e899d27b62bbc3087
ms.sourcegitcommit: c1e83b63ae34bd586e6e0ccc914640efdf96bd4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48423942"
---
# <a name="windows-groups-and-user-accounts-in-biztalk-server"></a>BizTalk Server の Windows グループ アカウントとユーザー アカウント
BizTalk Server ローカルおよびドメイン グループ アカウントとユーザー アカウントに関する情報。 BizTalk Server と必要なすべてのソフトウェアを 1 台のコンピューターにインストールすると、既定では、必要な BizTalk グループ アカウントが構成マネージャーで作成されます。 このセクションの説明は、複数コンピューター トポロジを対象としています。  
  
> [!IMPORTANT]
>  BizTalk Server では、ローカル グループ アカウントとローカル ユーザー アカウントは、単一コンピューター構成でのみサポートされます。 また、ドメイン グループ アカウントとドメイン ユーザー アカウントは、単一および複数の両方のコンピュータ構成でサポートされます。 BizTalk Server の構成にドメイン グループを使用する場合は、BizTalk Server を構成する前に、グループを手動で作成しておく必要があります。 構成マネージャーでは、ドメイン グループを作成できません。  
  
## <a name="procedures"></a>手順  
  
#### <a name="to-create-windows-group-and-user-accounts-in-biztalk-server"></a>BizTalk Server で Windows グループ アカウントとユーザー アカウントを作成するには  
  
1. Active Directory を使用して、**開始**メニューで、**プログラム**、 をポイント**管理ツール**、選択と**Active Directory ユーザーとコンピューター**します。  
  
2. Active Directory ユーザーとコンピュータ ウィンドウで、右側のウィンドウの下部にある右または右クリックし、**ユーザー**ナビゲーション ツリーで、左側のウィンドウでフォルダー。  
  
3. 選択**新規**を選択し、**グループ**または**ユーザー**します。  
  
4. 次の表にあるグループまたはユーザーの情報を入力します。  
  
   次の表は、Windows グループと BizTalk Server で使用されるそのメンバーシップを示します。 また、グループの SQL Server ロールまたはデータベース ロールについても説明します。  
  
|グループ化|グループの説明|メンバーシップ|SQL Server ロールまたはデータベース ロール|  
|-----------|-----------------------|----------------|----------------------------------------|  
|SSO 管理者|エンタープライズ シングル サインオン (SSO) サービスの管理者。|エンタープライズ シングル サインオン サービスのサービス アカウントが含まれます。<br /><br /> BizTalk Server および SSO サービスを構成および管理する権限が必要なユーザーまたはグループが含まれます。<br /><br /> SSO マスター シークレット サーバーを構成する場合に BizTalk 構成マネージャーの実行に使用するアカウントが含まれます。|SSO の db_owner SQL Server データベース ロール<br /><br /> SSO が配置されている SQL Server の securityadmin SQL Server ロール|  
|SSO 関連管理者|特定の SSO 関連アプリケーションの管理者。<br /><br /> できます SSO 関連アプリケーションの作成/削除、管理ユーザーのマッピング、および関連会社の資格情報をアプリケーションのユーザー設定|サービス アカウントは含まれません。<br /><br /> BizTalk Server 管理者に使用するアカウントが含まれます。||  
|BizTalk Server 管理者|管理タスクの実行に最低限必要な権限を持ちます。<br /><br /> ソリューションの配置、アプリケーションの管理、およびメッセージ処理に関する問題の解決を実行できます。<br /><br /> アダプター、受信ハンドラーと送信ハンドラー、および受信場所に対する管理タスクを実行するには、BizTalk Server 管理者をシングル サインオン関連管理者に追加する必要があります。<br /><br /> 詳細については、[BizTalk Server のセキュリティを管理する](../core/managing-biztalk-server-security.md)を参照してください。|BizTalk Server を構成および管理する権限が必要なユーザーまたはグループが含まれます。|次のデータベースの BTS_HOST_USERS SQL Server データベース ロール<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb<br /><br /> BizTalkDTADb<br /><br /> BAMPrimaryImport<br /><br /> 次のデータベースの db_owner SQL Server データベース ロール<br /><br /> BAMStarSchema<br /><br /> BAMPrimaryImport<br /><br /> BAMArchive<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> 次のデータベースの NSAdmin SQL Server データベース ロール<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> BAMAnalysis OLAP データベースをホストしているコンピューター上の OLAP 管理者。|  
|BizTalk Server オペレータ|権限レベルの低いロールで、監視操作とトラブルシューティング操作にのみアクセスできます。<br /><br /> 詳細については、次を参照してください[BizTalk Server のセキュリティの管理。](../core/managing-biztalk-server-security.md)|ソリューションを監視するユーザーまたはグループが含まれます。<br /><br /> サービス アカウントは含まれません。|次のデータベースの BTS_OPERATORS SQL Server データベース ロール<br /><br /> BizTalkDTADb<br /><br /> BizTalkEDIDb<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb|  
|BizTalk Application Users|構成マネージャーで作成される最初のインプロセス BizTalk ホスト グループの既定の名前。<br /><br /> 使用している環境のインプロセス ホストごとに 1 つの BizTalk ホスト グループを使用します。<br /><br /> BizTalk Server の BTSNTSvc.exe プロセスをホストするインプロセス BizTalk ホストにアクセスできるアカウントが含まれます。|BizTalk インプロセス ホスト インスタンスと、BizTalk ホスト グループの指定先ホストで BizTalk ルール エンジン サービスのサービス アカウントが含まれています。|次のデータベースの BTS_HOST_USERS SQL Server データベース ロール<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb<br /><br /> BizTalkDTADb<br /><br /> BAMPrimaryImport<br /><br /> BAMPrimaryImport の BAM_EVENT_WRITER SQL Server データベース ロール|  
|BizTalk 分離ホスト ユーザー|構成マネージャーで作成される最初の BizTalk 分離ホスト グループの既定の名前。 HTTP や SOAP など、BizTalk Server 上で実行されない BizTalk 分離ホストです。<br /><br /> 使用している環境の分離ホストごとに 1 つの BizTalk 分離ホスト グループを使用します。|BizTalk 分離ホスト グループの指定先ホストにある BizTalk 分離ホスト インスタンスのサービス アカウントが含まれます。|次のデータベースの BTS_HOST_USERS SQL Server データベース ロール<br /><br /> BizTalkMgmtDb<br /><br /> BizTalkMsgBoxDb<br /><br /> BizTalkRuleEngineDb<br /><br /> BizTalkDTADb<br /><br /> BAMPrimaryImport|  
|BAM ポータル ユーザー|BAM ポータル Web サイトにアクセスできます。|既定では、Everyone グループがこのロールで使用されます。<br /><br /> サービス アカウントは含まれません。||  
|BizTalk SharePoint アダプター対応ホスト|Windows SharePoint Services アダプター Web サービスにアクセスできます。|SharePoint アダプターを呼び出すことができる BizTalk ホスト インスタンスのサービス アカウントが含まれます。||  
|[BizTalk B2B Operators グループ]|すべてのパーティの管理操作を実行する管理者の負担を軽減する、BizTalk の新しいロール。 このロールでは、ロールに関連付けられた Windows ユーザーがすべてのパーティの管理操作を実行できます。|BizTalk Server TPM データを構成および管理し、ソリューションを監視する権限が必要なユーザーまたはグループが含まれます。|次のデータベースの BTS_OPERATORS SQL Server データベース ロール: BizTalkDTADb、BizTalkMgmtDb、BizTalkMsgBoxDb、BizTalkRuleEngineDb、および BAMPrimaryImport|  
  
 次の表に、Windows ユーザー アカウントまたはサービス アカウント、および BizTalk Server で使用されるグループ関連を示します。 また、アカウントの SQL Server ロールまたはデータベース ロールについても説明します。  
  
|ユーザー|ユーザーの説明|グループ関連|SQL Server ロールまたはデータベース ロール|  
|----------|----------------------|-----------------------|----------------------------------------|  
|エンタープライズ シングル サインオン サービス|エンタープライズ シングル サインオン サービスの実行に使用されるサービス アカウント。サービスを使用して SSO データベースにアクセスできます。|SSO 管理者||  
|BizTalk ホスト インスタンス アカウント|BizTalk インプロセス ホスト インスタンスの実行に使用されるサービス アカウント。ホスト インスタンスを使用して、インプロセス BizTalk ホスト インスタンス (BTNTSVC) にアクセスできます。|BizTalk Application Users<br /><br /> SSO 関連管理者||  
|BizTalk 分離ホスト インスタンス アカウント|BizTalk 分離ホスト インスタンス (HTTP または SOAP) の実行に使用されるサービス アカウント。|BizTalk 分離ホスト ユーザー<br /><br /> SSO 関連管理者<br /><br /> IIS_WPG||  
|ルール エンジン更新サービス|展開/展開解除ポリシーにルール エンジン データベースから通知を受信するルール エンジン更新サービスを実行するために使用するサービス アカウント。||BizTalkRuleEngineDb の RE_HOST_USERS SQL Server データベース ロール|  
|BAM Notification Services ユーザー|BAM データベースにアクセスする BAM Notification Services の実行に使用されるサービス アカウント。|SQLServer2008NotificationServicesUser$\<**ComputerName**\>|次のデータベースの NSRunService SQL Server データベース ロール<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> BAMPrimaryImport の BAM_ManagmentNSReader SQL Server ロール|  
|BAM 管理 Web サービス ユーザー|さまざまな BAM リソースにアクセスできる BAM 管理 Web サービス (BAMManagementService) 用のユーザー アカウント。 BAM ポータルでは、BAMManagementService を呼び出してアラートの管理、BAM 定義 XML と BAM ビューを取得する BAM ポータルにログオンしてユーザーの資格情報を使用|IIS_WPG|次のデータベースの NSSubscriberAdmin SQL Server データベース ロール<br /><br /> BAMAlertsApplication<br /><br /> BAMAlertsNSMain<br /><br /> BAMPrimaryImport の BAM_ManagementWS SQL Server ロール|  
|BAM アプリケーション プール アカウント|BAM ポータル Web サイトをホストする BAMAppPool のアプリケーション プール アカウント。|IIS_WPG||  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ローカル グループ](../core/local-groups.md)  
  
-   [ドメイン グループ](../core/domain-groups.md)
