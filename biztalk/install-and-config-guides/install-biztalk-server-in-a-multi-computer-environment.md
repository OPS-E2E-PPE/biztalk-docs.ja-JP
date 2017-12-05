---
title: "複数コンピューター環境で BizTalk Server のインストール |Microsoft ドキュメント"
description: "マルチ サーバー インストールとセットアップ ガイダンス BizTalk と SQL Server が BAM を含む別のコンピューターにインストールされている場合"
ms.custom: 
ms.date: 11/30/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4d0e707-6b9e-49e1-9f17-19b3bac1229e
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26100e268e6dd657369bb044461c42a6ba0b5a9c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="install-biztalk-server-in-a-multi-computer-environment"></a>複数コンピューター環境での BizTalk Server のインストール

## <a name="overview"></a>概要

Microsoft® BizTalk® Server を複数コンピューター環境へインストールすることを計画する際には、多くのことを考慮に入れる必要があります。 多くの場合、ネットワーク インフラストラクチャが存在して、BizTalk Server は、他のネットワーク アプリケーションと共存できるようにする必要があります。 このガイドでは、BizTalk Server と複数コンピューター環境、分散型展開でのビジネス アクティビティ監視 (BAM) のインストール時に適用される際の考慮事項について説明します。 この情報は、インストールと BizTalk Server とビジネス アクティビティ監視 (BAM)、およびアプリケーションとに依存しているコンポーネントの構成を計画するのに役立ちます。

1 台のサーバーのインストール ガイドには、重要な手順と詳細な背景情報が、このドキュメントでは重複していないことが含まれています。 たとえば、次の情報は、1 台のサーバーのインストール ガイドで詳しくについて説明します。

- 詳細なインストール手順
- BizTalk Server の各機能と依存関係
- BizTalk Server の基本的な構成設定に関する詳細情報
- ハードウェア要件とソフトウェア要件
- 再配布可能な CAB ファイルの一覧

## <a name="high-availability"></a>高可用性
BizTalk Server では、ネットワーク負荷分散 (NLB) クラスタ リングおよびフェールオーバー クラスタ リング、および SQL Server Always On 可用性グループ (AG) を使用して使用する高可用性ソリューションを提供します。 高可用性ソリューションでは、ハードウェアまたはソフトウェアの障害が発生した場合に発生するダウンタイムを最小限に抑えるのに役立ちます。 

**NLB とフェールオーバー クラスター**複雑なアーキテクチャで相互に補完します。 NLB クラスタリングは、フロントエンド Web サーバー間で要求を負荷分散するために使用されます。 フェールオーバー クラスタリングは、BizTalk Server インプロセス ホスト、エンタープライズ シングル サインオン マスター シークレット サーバー、および BizTalk Server データベースの高可用性を実現します。 これは通常、内部設置型環境を使用します。 適切なリソースを次に示します。 

* [BizTalk Server: 高可用性のサバイバル ガイド](http://social.technet.microsoft.com/wiki/contents/articles/6532.biztalk-server-high-availability-survival-guide.aspx)

* [Windows Server フェールオーバー クラスターまたは Windows Server クラスターを使用して BizTalk Server のフォールト トレランスを向上させる](http://go.microsoft.com/fwlink/p/?LinkId=154499)

**SQL Server 常に AG**内部設置型環境と Azure の仮想マシンに使用することができます。 AG のサポートは、BizTalk Server 2016 で開始し、任意の新しいバージョンの BizTalk Server ではサポートされています。 可用性グループには、プライマリ データベースのレプリカとセカンダリ データベース レプリカが含まれています。 BizTalk Server は、セカンダリ データベース レプリカは、冗長性を提供し、フェールオーバー中に、プライマリ データベースのレプリカに接続します。 [Always On 可用性グループ (SQL Server)](https://docs.microsoft.com/sql/database-engine/availability-groups/windows/always-on-availability-groups-sql-server) AG の仕組みの詳細を提供します。 

[BizTalk HA SQL Server 常に 可用性グループを使用して](../core/high-availability-using-sql-server-always-on-availability-groups.md)BizTalk の観点から見たから詳細を提供します。

## <a name="separate-runtime-and-administration"></a>個別のランタイムと管理
BizTalk Server では、実稼働環境でさまざまなインストール シナリオをサポートしています。 たとえば、実行専用の環境と管理ツール専用の環境を 2 台のコンピューターに分けて、インストール、構成、展開することも可能です。

管理ツールのみインストール中に、次のコンポーネントがインストールされます。 BizTalk 管理コンソール、BM.exe、および BTSDeploy.exe です。 BizTalk Server の管理ツールだけをインストールする場合、次のことを考慮に入れてください:

- BizTalk Server メッセージ ボックス データベースをホストするすべてのコンピューターで、SQL Server エージェントが実行されている必要があります。 BizTalk Server メッセージング エンジンでメッセージ本文を追跡する場合、SQL Server エージェントは必須です。

- BizTalk Server 構成ウィザードを実行するときは、Analysis Services データベースを作成します。

- SQL Server Analysis Services で、BizTalk 追跡データベースを使用することはできません。

- SQL Server Analysis Services の名前付きインスタンスを使用することはサポートされていません。

BizTalk server 管理ツールだけをインストールするにのみを選択**管理ツール**セットアップ中にします。 インストールが完了したら、カスタム構成マネージャーを開き、既存のエンタープライズ シングル サインオン (SSO) システムと BizTalk グループを関連付けます。
ページの先頭

## <a name="enable-msdtc"></a>MSDTC を有効にします。
複数コンピューター環境に BizTalk Server をインストールして構成する前に、すべての BizTalk Server および BizTalk Server が使用するリモートの SQL Server インスタンス上 で、ネットワーク DTC アクセスとネットワーク COM+ アクセスを有効にします。 参照してください[、環境を最適化するために後の構成手順](post-configuration-steps-to-optimize-your-environment.md)です。

追加。

- すべての BizTalk サーバーと SQL サーバー グループのレベルが適用されて、同じリモート プロシージャ コール (RPC) 認証が必要です。 コンピューター間で異なる OS が実行されている場合、各コンピューターがワークグループに所属している場合、または、各コンピューターが相互に信頼関係のない別々のドメインに所属している場合、DTC プロキシが DTC を正しく認証できない場合があります。 参照してください[MSDTC が相互に認証に失敗した](https://msdn.microsoft.com/library/ms686976(VS.85).aspx)です。

- ファイアウォールを使用する場合、必要な DTC ポートと RPC ポートを開きます。 参照してください[サービス概要およびネットワーク ポート要件の Windows](http://support.microsoft.com/kb/832017)です。

- DTC の設定が正しいかどうかを確認するには、DTC Tester と DTC Ping ツールを使用します。 これらのツールと DTC のトラブルシューティングの詳細については説明で[BizTalk Server - MSDTC に関する問題のトラブルシューティング](https://social.technet.microsoft.com/wiki/contents/articles/2031.biztalk-server-troubleshooting-problems-with-msdtc.aspx)です。

## <a name="remote-sql-server"></a>リモートの SQL Server
リモート コンピューターで SQL Server がインストールされている場合。

- [SQL Server 管理ツール](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms)(新しい SQL バージョン) または SQL Server がリモートの場合、ローカルの BizTalk Server コンピューターに SQL Server クライアント ツール接続 (古い SQL バージョン) をインストールする必要があります。 SQL Server ツールでは、SQL Server のリモート インスタンスと通信するために必要なクライアント ライブラリをインストールします。 ローカルの BizTalk Server コンピューター上の SQL Server ツールのバージョンは、リモートの SQL Server にインストールされているのと同じバージョンである必要があります。

- Analysis Services をリモートで使用する場合は、SQL Server OLAP クライアントをローカル コンピューターにインストールしておく必要があります。 OLAP クライアントを含めることができます[SQL Server 2016 Feature Pack](https://www.microsoft.com/download/details.aspx?id=52676)です。

- BizTalk Server の構成時には、リモート コンピューター上の SQL Server が実行されている必要があります。

- BizTalk Server の構成時には、SQL Server のセットアップ時に指定した TCP ポートおよび UDP ポートを開いておく必要があります。

- BAM ツールを構成するのには、SQL Server 管理ツール - 基本および完全を BizTalk BAM サーバーをインストールします。 設定して、複数コンピューター環境での BAM の構成の詳細については、次を参照してください。 [BAM インストールおよび構成 (ビジネス アクティビティ監視)、複数コンピューター環境で](https://social.technet.microsoft.com/wiki/contents/articles/1888.install-and-configure-bam-business-activity-monitoring-in-a-multi-computer-environment.aspx)です。 

- SQL Server Analysis Services の名前付きインスタンスはサポートされません。

### <a name="sql-server-topologies"></a>SQL Server トポロジ
SQL Server は、BizTalk サーバーで、または SQL Server に専用の別のサーバー上でローカルにインストールできます。 ほとんどの実稼働のシナリオは、BizTalk Server と SQL Server が別々 のコンピューターにインストールされています。 

サポートされている SQL Server のバージョンの一覧を参照してください。 

* [BizTalk Server 2016 ソフトウェア要件](hardware-and-software-requirements-for-biztalk-server-2016.md) 
* [BizTalk Server 2013R2 と 2013 のソフトウェア要件](hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)

> [!IMPORTANT]
> その他の Service Pack および Windows Updates はいずれもサポートされているので、インストールする必要があります。

### <a name="maintain-and-troubleshoot-databases"></a>管理データベースとトラブルシューティング

参照してください[を維持し、BizTalk Server データベースのトラブルシューティングを行う方法](http://support.microsoft.com/kb/952555)です。

## <a name="business-activity-monitoring-bam"></a>ビジネス アクティビティ監視 (BAM)
BizTalk Server には、BAM などのインフォーメーション ワーカー用ツールが用意されています。 コンポーネントのアーキテクチャの基本的な知識を使用して、BizTalk Server のインストールを利用できるサーバーのリソースを利用できます。
ビジネス アクティビティ監視 (BAM) は、集計、警告、および主要業績評価指標または Kpi と呼ばれる、関連するビジネス指標を監視するプロファイルを管理するためのツールのコレクションです。

BAM は、モジュールの状態とさまざまな運用プロセスおよびトランザクションの結果に関する情報を提供するビジネス プロセスにエンド ツー エンドの可視性を提供します。 BAM の出力を活用すれば、ビジネスで問題がある領域を見つけて、その問題を解決できます。 BAM のライフ サイクルの詳細については、ビジネス アクティビティ監視 (BAM) ポスターを参照してください。 [BizTalk Server BAP ポスター](https://www.microsoft.com/download/details.aspx?id=56123)です。

BAM は次の層で構成されます:

| 層 | 実行内容 | 使用例 | インストールされています。 |
|---| ---|---|---|
| プレゼンテーションおよびツール | ビジネス ユーザーおよび開発者用のフロントエンド サービス。 データの表示により、ビジネス ユーザーと開発者を定義および管理にテンプレートとプロファイルです。その他の機能です。 | Office Excel、BAM ポータル | Excel、管理ツール、およびカスタム ユーザー インターフェイスは、ビジネス ユーザーまたは開発者のワークステーションにインストールします。 BAM ポータル、および BAM インフラストラクチャ上で構築されたカスタム Web アプリケーションは、サーバーにインストールします。 |
| Web サービス、および処理 | プレゼンテーション層とデータベース層を結び付ける役割を果たします。ビジネス ルールとビジネス プロセスが実装されます。データの集計と分析が行われます。 | Windows SharePoint Services (WSS)、取引先管理 Web サービス、BAM 管理 Web サービス、および BizTalk Server エンジン | IIS および SQL Notification Services が構成されているサーバー上 (アプリケーションによっては、カスタム Web サービスが構成されている場合もあります)。 BizTalk ホスト サービスは、このサーバーにインストールすることもできますが、3 台以上のコンピューターで構成される複数コンピューター環境の場合は、別のサーバーにインストールすることもできます。 |
| データベースおよびプラットフォーム サービス | データの格納と取得、セキュリティと認証、ネットワーク処理、および OS 機能が実行されます。 | SQL Server、Windows Server、エンタープライズ シングル サインオン (SSO)、およびフェールオーバーおよび NLB クラスタ リング | Windows Server、SQL Server でのサーバー。 パフォーマンス上の理由から、このサーバー通常が実行されない BizTalk ホスト サービス。 |

### <a name="install-bam"></a>BAM をインストールします。
ステップ バイ ステップ ガイド: [BAM インストールおよび構成 (ビジネス アクティビティ監視)、複数コンピューター環境で](https://social.technet.microsoft.com/wiki/contents/articles/1888.install-and-configure-bam-business-activity-monitoring-in-a-multi-computer-environment.aspx)

次の表に示す 3 つの BizTalk Server 環境を分割して、BAM、インストールおよび構成プロセスで、依存関係を理解しやすくは。

| 実行時の環境 | デザイン時の環境 | 使用時の環境 |
|---|---|---|
| 基本的な BizTalk Server ランタイム環境では、次のサーバーを含めることができます。 <ul><li>BizTalk Server</li><li>SQL Server</li><li>BizTalk BAM サーバー</li><li>Web サーバー</li></ul> | BAM の開発および展開プロセスには、3 つのロールが関与します。 ロールは、次のとおりです: <ul><li>ビジネス アナリスト</li><li>ビジネス管理者</li><li>アプリケーション開発者</li></ul> | BAM ソリューションが実装して、展開、後に、ビジネス エンドユーザーはさまざまなレポート ツールによって生成されたレポートを表示できます。 これらのツールは次のとおりです。 <ul><li>BAM ポータル </li><li>SQL Server Reporting Services (SQL Server Reporting Services)</li><li>Microsoft PerformancePoint Monitoring Server</li><li>カスタム BAM レポート アプリケーション</li></ul> |

次の表では、BAM コンポーネントをインストールするについて説明します。

|カテゴリ |BAM コンポーネント|用途|
|---|---|---|
| ポータル コンポーネント | ビジネス アクティビティの監視 | ビジネス アクティビティ監視コンポーネントを選択するには、ビジネス ユーザーに重要なビジネスの意思決定を行えるように、異種ビジネス プロセスのリアルタイム ビューを提供するソフトウェアがインストールされます。 |
| 追加ソフトウェア | BAM 警告 | BizTalk Server がビジネス アクティビティ監視 (BAM) 警告を提供するために必要なソフトウェアをインストールします。 <br/><br/>BizTalk Server 2013 R2 で BAM 警告では、SQL Server データベース メールを使用します。 SQL Notification Services は使用もサポートもされません。<br/><br/>SQL Server 2012 での BizTalk Server 2013 での BAM 警告では、SQL Notification Services を使用します。 SQL Server 2008 R2 での BizTalk Server 2013 での BAM 警告では、SQL Notification Services を使用します。 |
| | BAM クライアント | BAM クライアント コンポーネントを選択するには、BizTalk Server のビジネス アクティビティ監視機能を使用するビジネス ユーザーが必要なクライアント側ソフトウェアがインストールされます。 | 
| | BAM イベント | BAM イベント サポート コンポーネントを選択してでは、BAM イベント インターセプター for Windows Workflow Foundation および Windows Communication Foundation 用ソフトウェアをインストールします。 また、カスタム アプリケーションから BAM データベースにイベントを送信するために使用する BAM イベント API もインストールされます。 BAM イベント サポートは、BizTalk Server でビジネス アクティビティ監視機能の一部です。 | 

### <a name="configure-bam"></a>BAM を構成します。
ステップ バイ ステップ ガイド: [BAM インストールおよび構成 (ビジネス アクティビティ監視)、複数コンピューター環境で](https://social.technet.microsoft.com/wiki/contents/articles/1888.install-and-configure-bam-business-activity-monitoring-in-a-multi-computer-environment.aspx)

BizTalk Server の構成を開き、[カスタム構成](configure-biztalk-server.md)です。 [カスタム構成]で、拡張オプションを構成し、各機能を選択的に構成したり、構成を解除したりできます。 

### <a name="install-and-configure-sql-server-for-bam"></a>BAM 用の SQL Server のインストールと構成

[は新規、インストール、構成、およびアップグレード](biztalk-server-what-s-new-installation-configuration-and-upgrade.md)、することができます。 

- サポートされている SQL Server のバージョンを含む BizTalk Server のサポートされているソフトウェア要件を参照してください。
- SQL Server を含め、前提条件ソフトウェアをインストールします。 SQL Server に固有のインストール手順については、次を参照してください。 [SQL Server 2016 のインストール](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup)または[SQL Server 2014 のインストール](https://msdn.microsoft.com/library/bb500469(v=sql.120).aspx)です。

BizTalk Server のコア機能によって必要とされるデータベース サービスに加え、BAM には次のコンポーネントも必要です:

- SQL Server Analysis Services (SSAS)

- SQL Server Integration Services (SSIS)

- SQL Server データベース メールまたは SQL Server Notification Services (SSNS)

##### <a name="configure-ssis"></a>SSIS を構成します。
BizTalk Server 以外のコンピューターに SQL Server がインストールされている場合は、SSIS の構成が必要です。 このタスクでは、リモートの SQL Server 上にある msdb データベースを使用するために SSIS を構成します。

1. コマンド プロンプトを開きます。

2. %ProgramFiles%\Microsoft SQL server \100\dts\binn にディレクトリを変更します。
 
3. 次のコマンドを実行します notepad MsDtsSrvr.ini.xml。

4. メモ帳で、内のテキストを更新、"<ServerName>"に、SQL Server のホスト名のタグ。 変更を保存します。

5. コマンド プロンプトから次のコマンドを実行します net MsDtsServer の停止。

6. コマンド プロンプトから次のコマンドを実行します net MsDtsServer の開始。

    **追加**:  
    Integration Services サービスは既定で、データベース エンジンの既定のローカル インスタンス内の msdb データベースに格納されるパッケージを管理するように構成されます。 名前付きインスタンスまたはリモートのデータベース エンジンのインスタンスまたはデータベース エンジンの複数のインスタンスに格納されているパッケージを管理するには、構成ファイルを変更します。 たとえば、データベース エンジンの複数インスタンスの msdb データベースに格納されるパッケージを管理するには、種類が SqlServerFolder の追加のルート フォルダーを作成できます。サービスが停止する場合、構成ファイルを変更し、パッケージが継続して実行されるようにできます。 このオプションは、Object Explorer 内のルート フォルダーをさらに表示するか、Integration Services サービスが管理するファイル システム内の異なるフォルダーまたは追加のフォルダーを指定します。

    `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSDTS\ServiceConfigFile`レジストリ キーは、Integration Services サービスが使用する構成ファイルの名前と場所を指定します。 このレジストリ キーの既定値は C:\Program Files\Microsoft SQL Server\100\DTS\Binn\ MsDtsSrvr.ini.xml です。 構成ファイルに対して別の名前と場所を使用するには、レジストリ キーの値を更新します。

#### <a name="configure-bam-databases"></a>BAM データベースを構成します。
BAM プライマリ インポート、BAM アーカイブ、BAM スター スキーマ、BAM 分析、BAM Notification Services Application の各データベースは、それぞれ異なるコンピューター上で構成できます。 以下は、ソフトウェア要件については、BizTalk Server 以外のコンピューターに SQL Server がインストールされている場合。

| BAM 機能 | 機能構成 | BizTalk Server | SQL Server | 
|---|---|---|---|
|BAM ツール | BAM プライマリ インポート テーブルおよび BAM アーカイブ データベース | ADOMD.NET の SQL Server Integration Services します。 | サポートされている SQL Server のバージョン。 参照してください[新機能、インストール、構成、およびアップグレード](biztalk-server-what-s-new-installation-configuration-and-upgrade.md)です。|
| BAM ツール| BAM 集計用に Analysis Services を有効にする| SQL Server Integration Services| SQL Server Analysis Services (SQL Server Analysis Services)| 
| BAM Notification Services アプリケーション データベース| BAM 警告| BAM 警告 <br/>一覧された要件[は新規、インストール、構成、およびアップグレード](biztalk-server-what-s-new-installation-configuration-and-upgrade.md)です。| SQL Server 2012 または SQL Server 2014 を使用している場合は、SQL Server データベース メールを構成します。 SQL Server 2008 R2 を使用する場合は、SQL Server 2005 Notification Services エンジン コンポーネントをインストールします。<br/><br/>コンピューターのインストールを準備するのには、BAM 警告の要件が記載されています。

> [!NOTE] 
> OLAP サービスに使用するサービス アカウントには、BAM スター スキーマ データベースに対する db_datareader 権限が付与されている必要があります。

##### <a name="notification-services--biztalk-2013--sql-server-2008-r2-only"></a>通知サービス – BizTalk 2013/SQL Server 2008 R2 のみ

> [!IMPORTANT]
> このセクションでは、SQL Server 2008 R2 を使用する場合にのみ適用されます。

SQL Server Notification Services を、Notification Services のプロバイダー、ジェネレーター、ディストリビューターの各ロールが別々のコンピューターにある、複数コンピューター環境にインストールすることができます。 このシナリオでは、次に示すファイルが必要となります。

- プロバイダーの役割をホストするコンピューターに、AggregationEventProvider.dll をインストールする必要があります。 この .dll ファイルは、BizTalk Server のインストール中に、BAM 警告集計イベント プロバイダーをインストールするときにインストールされます。 BizTalk ランタイム、管理ツール、または、開発ツールと SDK がインストールされていれば、BAM 警告集計イベント プロバイダーもインストールされています。

- ディストリビューターの役割をホストするコンピューターでは、EmailNotification.xslt および FileNotification.xslt が必要です。 既存の BizTalk Server から次のパスにファイルをコピーすることができます BizTalk Server \Program Files\Microsoft*バージョン*\Tracking。

- ディストリビューターの役割をホストするコンピューター上の .xslt ファイルの正確な場所で、Notification Services Application 定義ファイル (.adf ファイル) を更新します。 

**アプリケーション定義ファイル (.adf ファイル) を更新**:  

1. BizTalk Server がインストールされているコンピューターでは、Notification Services コマンド プロンプトを開きます。
2. \Program Files\Microsoft BizTalk Server に移動*バージョン*\Tracking です。
3. ProcessBamNsFiles.vbs を実行し、初期状態の .adf ファイルを作成します。
4. .xslt ファイルのパスに合わせて .adf ファイルを修正します。
5. ProcessBamNsFiles.vbs をもう一度実行して、.adf ファイルを更新します。
6. BAMAlerts NT サービスを再起動します。

##### <a name="bam-scale-out-alerts-topology"></a>BAM スケール アウト警告のトポロジ
BAM スケール アウト警告の既存のトポロジを BizTalk Server 2013 にアップグレードする場合は、各サーバーで、次の手順を実行します。

1. Notification Services を停止し、Notification Services のインスタンスの登録を解除します。
    1. **プログラム**をクリックして**Microsoft SQL Server 2005**、 をクリックして**構成ツール**、クリックして**Notification Services コマンド プロンプト**.
    1. コマンド プロンプトで次のように入力します。:`net stop NS$<instance_name>`です。 たとえば、入力:`net stop NS$BamAlerts`です。
    1. インスタンスの登録を解除するには、次のコマンドを入力:`nscontrol unregister -name BamAlerts`です。 

        インスタンスの登録を解除すると、レジストリのエントリが削除されるほか、NS$instance_name サービスも (存在する場合は) 削除されます。さらに、このサービスに対応するパフォーマンス カウンターも削除されます。

2. Notification Services インスタンスを上位エディションの SQL Server 2005 Notification Services が存在するサーバーをアップグレードします。

3. アップグレードする SQL Server のバージョンに基づいて BAM データベースを移行するには、BizTalk Server の Tracking フォルダーにある移行データベース コマンド bm.exe プログラムを実行します。 たとえば、SQL Server 2005 を SQL Server 2008 R2 にアップグレードすると、実行次管理者資格情報でコマンド プロンプトで:`bm.exe migrate-sql –From:sql2005 –To:sql2008 –NSUser:<username>`です。

4. 移行プログラム (bm.exe) が使用されているサーバーを除くすべてのサーバーへの通知サービスを登録してください。

    1. **プログラム**をクリックして**Microsoft SQL Server 2005**、 をクリックして**構成ツール**、クリックして**Notification Services コマンド プロンプト**.
    2. コマンド プロンプトで次のように入力します。`nscontrol register -name BamAlerts -server <NS DB Server> -service -serviceusername "<NSServiceUserName>" -servicepassword "<NSServicePassword>"`

    これにより、Notification Services が、適切なデータベース (この情報は、nscontrol により、サービス コンピューターのレジストリに保持) にログオンします。

    > [!IMPORTANT] 
    > 新しい Notification Services データベース サーバーを使用してサーバー オプションは、サービスを再登録するときにします。 また、新しい Notification Services サービスには、以前と同じユーザー名を使用します。

5. BAM 警告を検証: オープン、 **Notification Services コマンド プロンプト**および型:`nscontrol.exe status –name BAMAlerts –server <NS DB Server>`です。

### <a name="bam-portal"></a>BAM ポータル
ポータル コンポーネントは、一連の通信、協力、およびそれらの相互作用を有効にする意思決定を行うビジネス担当者によって使用されるサービスの構成、およびビジネス プロセスやワークフローの監視します。 この機能を使用するには、インターネット インフォメーション サービス (IIS) をインストールします。 IIS の要件を[は新規、インストール、構成、およびアップグレード](biztalk-server-what-s-new-installation-configuration-and-upgrade.md)です。

### <a name="bam-add-in-from-excel"></a>BAM アドインを Excel から
[追加または削除するアドイン](https://support.office.com/article/add-or-remove-add-ins-0af570c4-5cf3-4fa9-9b88-403625a0b460)Excel 用の手順を示します。 BAM アドインでは、名前が**ビジネス アクティビティ監視**です。

### <a name="configure-multiple-biztalk-groups-to-use-a-single-bam-database"></a>1 つの BAM データベースを使用する複数の BizTalk グループを構成します。
複数の BizTalk グループ、BAM データベースを共有します。

1. 1 番目の BizTalk グループおよび BAM 機能を構成します。 これらの機能には、BAM ツール、BAM 分析データベース、BAM 警告、および BAM ポータルが含まれます。

2. 2 番目以降の BizTalk グループを構成し、BizTalk Server 構成ウィザードでは、次を実行します。

    1. 選択**BAM ツール**、し、選択、**ビジネス アクティビティの監視を有効にするツール**と**BAM 集計用に Analysis Services を有効にする**チェック ボックスです。

    2. 変更、**サーバー名**と**データベース名**BAM データ ストアの最初の BizTalk グループを構成するときに使用される同じ名前の一致するようにします。

    3. 選択**BAM 警告**し、**を有効にする BAM 警告**です。

    4. 空白のユーザー名とパスワードであるために、BAM 警告のサービス アカウントを変更します。

    5. 警告データベース用の BAM 警告 SMTP サーバー、BAM 警告ファイルの場所、SQL Server の変更し、最初の BizTalk グループを構成するときに使用される同じ名前の一致するように警告データベース名のプレフィックスします。

    > !注意してください]、同じプライマリ インポート テーブル (PIT) を使用しましたが、異なる BAM アーカイブ、BAM 分析、およびスター スキーマ データベースを指定できます。 ただし、このオプションは、同じ PIT を使用するすべてのグループに影響します。

3. 選択**BAM ポータル**、し、選択、 **BAM ポータルを**チェック ボックスをオンします。

    > [!NOTE]
    > BAM プライマリ インポート データベースと BAM ポータルの間には 1 対 1 のリレーションシップが存在するため、この画面のフィールドはすべて読み取り専用になります。 同じ BAM データベースに対して複数の BizTalk グループを構成した場合は、これらの BizTalk グループで BAM ポータルが共有されます。

4. 選択**構成を適用**です。

### <a name="bam-client-software-requirements"></a>BAM クライアント ソフトウェアの要件
- Web クライアントは、する必要があります Internet Explorer および Office Web Components 11 version 4.0 またはそれ以降。

- Web クライアントを実行して、SQL Server 2008 R2 Analysis Services を使用している場合は、Microsoft SQL Server 2008 R2 Analysis Services 10.0 OLE DB Provider をインストールします。 

- Excel クライアントは、Microsoft Excel および BAM Excel アドインを BizTalk Server に用意されている必要があります。


## <a name="groups-and-service-accounts"></a>グループおよびサービス アカウント
手動で複数コンピューター環境で BizTalk Server を構成する前に、すべてのドメイン グループおよびアカウントを作成します。 次の情報は、これらのグループとアカウントの作成に役立ちます。

複数コンピューター環境において、BizTalk Server ではドメイン グループおよびドメイン サービス アカウントのみがサポートされています。 

- BizTalk Server のサポートのみ<NetBIOSDomainName>\<ユーザー > の Windows グループの形式の名前を指定し、サービス アカウント。

- BizTalk Server を複数コンピューター環境で構成する場合、Active Directory のドメイン グループとユーザー アカウントだけがサポートされます。 ドメイン ローカル グループ、グローバル グループ、ユニバーサル グループの各ドメイン グループについては、単一コンピューター環境と複数コンピューター環境の両方でサポートされます。

- 一般に、同じドメインに属するすべての SQL Server などの BizTalk Server インフラストラクチャで、サーバーの使用が必要であるために、ドメイン ローカル グループは推奨されません。 この考慮事項は、サーバーやユーザー アカウントが単一のドメインに存在する小規模なネットワークには当てはまりません。 [Active Directory グループ](http://technet.microsoft.com/library/cc733001.aspx)詳しく説明します。

- BizTalk Server を複数コンピューター環境にインストールして構成した場合、NT AUTHORITY\LOCAL SERVICE、NT AUTHORITY\NETWORK SERVICE、NT AUTHORITY\SERVICE、NT AUTHORITY\SYSTEM、Everyone などのビルトイン アカウントはサポートされません。

- BizTalk Server の構成を実行しているユーザーは、次のユーザー グループに属している必要がありますローカルのコンピューターでは、BizTalk Server 管理者に使用されるドメイン グループ、SQL Server コンピューターのシステム管理者グループの Administrators グループ。グループ、および SSO 管理者グループに使用されるドメイン グループです。

- 可能な限り、セットアップ中に作成された既定のアカウント名を使用します。 BizTalk Server セットアップ プログラムによってインストールされたコンポーネントは、既定のアカウントを使用するように自動的に構成されます。 既定の名前を使用すると、セットアップおよび構成が簡素化されますが、常に使用できるとは限りません。 たとえば、Active Domain フォレスト内に複数の BizTalk Server グループが存在することができます。 このような状況では、競合を回避するアカウント名を変更する必要があります。 あるいは、自社でサービスとユーザー アカウントに名前付け標準を使用している場合は、その標準に準拠するように既定のアカウントを変更します。

### <a name="windows-groups"></a>[Windows グループ]
次の表に、BizTalk Server で使用される Windows グループとそのメンバーシップを示します。 また、グループの SQL Server ロールまたはデータベース ロールについても説明します。

| [グループ] | グループの説明 | メンバーシップ | SQL Server ロールまたはデータベース ロール | 
| ---|---|---|---|
| SSO 管理者 | エンタープライズ シングル サインオン (SSO) サービスの管理者。 [SSO 管理者および関連管理者アカウントを指定](../core/how-to-specify-sso-administrators-and-affiliate-administrators-accounts.md)の詳細についてはします。 | エンタープライズ シングル サインオン サービスのサービス アカウントが含まれます。 BizTalk Server と SSO サービスを構成および管理する権限が必要なユーザーまたはグループが含まれます。SSO マスター シークレット サーバーを構成する場合に BizTalk 構成マネージャーの実行に使用するアカウントが含まれます。 | **db_owner** SSO の SQL Server データベース ロール <br/><br/>**securityadmin** SSO が配置されている SQL Server 用の SQL Server ロール。 |
| SSO 関連管理者 | 特定の SSO 関連アプリケーションの管理者。 SSO 関連アプリケーションの作成または削除、ユーザー マッピングの管理、および関連アプリケーション ユーザーの資格情報の設定を行えます。 | サービス アカウントは含まれません。 BizTalk Server 管理者に使用するアカウントが含まれます。| |
|BizTalk Server 管理者 | 管理タスクの実行に必要な最小限の特権が付与されます。 ソリューションの配置、アプリケーションの管理、およびメッセージ処理に関する問題の解決を実行できます。 アダプター、受信ハンドラーと送信ハンドラー、および受信場所に対する管理タスクを実行するには、BizTalk Server 管理者をシングル サインオン関連管理者に追加する必要があります。 参照してください[BizTalk Server のセキュリティを管理](../core/managing-biztalk-server-security.md)です。 | BizTalk Server を構成および管理する権限が必要なユーザーまたはグループが含まれます。 | **BTS_ADMIN_USERS**次のデータベースの SQL Server データベース ロール。<br/>BizTalkMgmtDb<br/>BizTalkMsgBoxDb<br/>BizTalkRuleEngineDb<br/>BizTalkDTADb<br/>BAMPrimaryImport<br/><br/>**db_owner**次のデータベースの SQL Server データベース ロール。<br/>BAMStarSchema<br/>BAMPrimaryImport<br/>BAMArchive<br/>BAMAlertsApplication<br/>BAMAlertsNSMain<br/><br/>**NSAdmin**次のデータベースの SQL Server データベース ロール。 <br/>BAMAlertsApplication<br/>BAMAlertsNSMain<br/><br/>次のデータベースの SQL Server データベース ロール:  <br/>BizTalkDTADb<br/>BizTalkMgmtDb です。 <br/><br/>**OLAP 管理者**BAMAnalysis OLAP データベースをホストするコンピューターにします。 |
| BizTalk Server オペレータ | 監視とトラブルシューティング操作にのみアクセス権を持つ特権の低いロールがあります。 | ソリューションを監視するユーザーまたはグループが含まれています。 サービス アカウントは含まれません。 | **BTS_OPERATORS**次のデータベースの SQL Server データベース ロール。 <br/>BizTalkDTADb<br/>BizTalkEDIDb<br/>BizTalkMgmtDb<br/>BizTalkMsgBoxDb<br/>BizTalkRuleEngineDb | 
| BizTalk Application Users | 構成マネージャーで作成される最初のインプロセス BizTalk ホスト グループの既定の名前。 使用している環境のインプロセス ホストごとに 1 つの BizTalk ホスト グループを使用します。 BizTalk Server の BTSNTSvc.exe プロセスをホストするインプロセス BizTalk ホストにアクセスできるアカウントが含まれます。 | BizTalk ホスト グループの指定先ホストにある BizTalk インプロセス ホスト インスタンスのサービス アカウントが含まれます。  | **BTS_HOST_USERS**次のデータベースの SQL Server データベース ロール。<br/>BizTalkMgmtDb<br/>BizTalkMsgBoxDb<br/>BizTalkRuleEngineDb<br/>BizTalkDTADb<br/>BAMPrimaryImport<br/><br/> **BAM_EVENT_WRITER** BAMPrimaryImport の SQL Server データベース ロール。 | 
| BizTalk 分離ホスト ユーザー | 構成マネージャーで作成される最初の BizTalk 分離ホスト グループの既定の名前。 HTTP や SOAP など、BizTalk Server 上で実行されない BizTalk 分離ホストです。 使用している環境の分離ホストごとに 1 つの BizTalk 分離ホスト グループを使用します。 | BizTalk 分離ホスト グループの指定先ホストにある BizTalk 分離ホスト インスタンスのサービス アカウントが含まれます。 | **BTS_HOST_USERS**次のデータベースの SQL Server データベース ロール。<br/>BizTalkMgmtDb<br/>BizTalkMsgBoxDb<br/>BizTalkRuleEngineDb<br/>BizTalkDTADb<br/>BAMPrimaryImport | 
| EDI サブシステム ユーザー | EDI データベースにアクセスできます。 | BizTalk ベース EDI サービスのサービス アカウントが含まれます。 | **EDI_ADMIN_USERS** BizTalkEDIDb の SQL Server データベース ロール。 | 
| BAM ポータル ユーザー | BAM ポータル web サイトにアクセスしています。 | 既定では、Everyone グループがこのロールで使用されます。 サービス アカウントは含まれません。 |  | 
| BizTalk SharePoint アダプター対応ホスト | Windows SharePoint Services アダプター Web サービスへのアクセスがあります。 | SharePoint アダプターを使用する BizTalk ホスト インスタンスのサービス アカウントが含まれています。 |  | 
| [BizTalk B2B Operators グループ] | すべてのパーティの管理操作を実行する管理者の負担を軽減する BizTalk のロール。 このロールでは、ロールに関連付けられた Windows ユーザーがすべてのパーティの管理操作を実行できます。 | BizTalk Server TPM データを構成および管理し、ソリューションを監視する権限が必要なユーザーまたはグループが含まれます。 | **BTS_OPERATORS**次のデータベースの SQL Server データベース ロール。 <br/>BizTalkDTADb<br/>BizTalkMgmtDb<br/>BizTalkMsgBoxDb<br/>BizTalkRuleEngineDb<br/>BAMPrimaryImport |

### <a name="user-and-service-accounts"></a>ユーザーおよびサービスのアカウント
次の表に、Windows ユーザー アカウントまたはサービス アカウント、および BizTalk Server で使用されるグループ関連を示します。 また、アカウントの SQL Server ロールまたはデータベース ロールについても説明します。

| ユーザー| ユーザーの説明| グループ関連 | SQL Server ロールまたはデータベース ロール| 
| ---|---|---|---|
| エンタープライズ シングル サインオン サービス | サービス アカウントがサービスを実行するエンタープライズ シングル サインオン、SSO データベースにアクセスするために使用します。 | SSO 管理者 | | 
| BizTalk ホスト インスタンス アカウント | BizTalk インプロセス ホスト インスタンス (BTNTSVC) の実行に使用されるサービス アカウント。 | BizTalk Application Users | | 
| BizTalk 分離ホスト インスタンス アカウント | BizTalk 分離ホスト インスタンス (HTTP または SOAP) の実行に使用されるサービス アカウント。 | BizTalk 分離ホスト ユーザー、IIS_WPG | | 
| ルール エンジン更新サービス | ルール エンジン更新サービスの実行に使用されるサービス アカウント。サービスでは、ルール エンジン データベースから展開ポリシーおよび展開解除ポリシーへの通知を受信します。| | **RE_HOST_USERS** BizTalkRuleEngineDb の SQL Server データベース ロール。| 
| BAM Notification Services ユーザー | BAM Notification Services は、BAM データベースにアクセスを実行するために使用するサービス アカウント。 | SQLServer2005NotificationServicesUser $<ComputerName> | **NSRunService**次のデータベースの SQL Server データベース ロール。<br/>BAMAlertsApplication<br/>BAMAlertsNSMain<br/><br/>**BAM_ManagementNSReader** BAMPrimaryImport の SQL Server ロール。 | 
| BAM 管理 Web サービス ユーザー | さまざまな BAM リソースにアクセスできる BAM 管理 Web サービス (BAMManagementService) 用のユーザー アカウント。 BAM ポータルでは、BAM ポータルにログオンしたユーザーの資格情報を使用して BAMManagementService を呼び出し、警告を管理したり、BAM 定義 XML ビューおよび BAM ビューを取得することができます。 | IIS_WPG | **NSSubscriberAdmin**次のデータベースの SQL Server データベース ロール。<br/>BAMAlertsApplication<br/>BAMAlertsNSMain<br/><br/>**BAM_ManagementWS** BAMPrimaryImport の SQL Server ロール。 | 
| BAM アプリケーション プール アカウント| BAM ポータル web サイトをホストする BAMAppPool のアプリケーション プール アカウント。 | IIS_WPG | | 

> [!IMPORTANT]
> Windows グループと BizTalk Server で使用されるサービス アカウントの詳細については、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)です。

## <a name="databases-list"></a>データベースの一覧
BizTalk Server で使用される SQL Server データベースの一覧を次に示します:

| データ ストア名 | 既定のデータベース名 | Volume | 容量の増大 | Description | 
| ---|---|---|---|---|
| SSO データベース | SSODB | Low | Low | このエンタープライズ シングル サインオン資格情報データベースには、ユーザー名およびパスワードが安全に格納されます。| 
| BizTalk 管理データベース | BizTalkMgmtDb | Low | Low | このデータベースには、BizTalk Server のすべてのインスタンスのメタ情報が一元的に保存されます。| 
| BizTalk メッセージ ボックス データベース | BizTalkMsgBoxDb | 高 | Medium | BizTalk Server エンジンでは、ルーティング、キュー、インスタンス管理、およびその他のさまざまなタスクのこのデータベースを使用します。<br/><br/>**注**<br/>統計の自動更新、統計の自動作成、および並列処理の設定はオフになって、BizTalk Server BizTalkMsgBoxDB データベースをホストする SQL Server データベース インスタンスです。 これらの設定を有効にしないでください。 | 
| BizTalk 追跡データベース | BizTalkDTADb | 高 | 高 | このデータベースには、BizTalk Server 追跡エンジンで追跡したビジネス データおよび稼働状態の監視データが格納されます。 | 
| ルール エンジン データベース | BizTalkRuleEngineDb | Low | Low | このデータベースは、関連するルールおよびボキャブラリのセットであるポリシーのリポジトリです。 ボキャブラリは、ルール内でデータを参照するための、ユーザーにわかりやすいドメイン固有の名前の集まりです。 | 
| BAM プライマリ インポート データベース | BAMPrimaryImport | Medium | Medium | このデータベースでは、未処理の BAM の追跡データを収集します。 | 
| BAM アーカイブ データベース | BAMArchive | Medium | Medium | このデータベースは、古いビジネス アクティビティ データをアーカイブします。 BAM プライマリ インポート データベースにおけるビジネス アクティビティ データの蓄積を最小限にする BAM アーカイブ データベースを作成します。 | 
| BAM スター スキーマ データベース | BAMStarSchema | Medium | Medium | このデータベースには、段階テーブル、単位テーブル、およびディメンション テーブルが含まれます。 | 
| BAM Notification Services アプリケーション データベース | BAMAlertsApplication | Medium | Medium | このデータベースには、BAM 通知に関する警告情報が含まれます。 たとえば、BAM ポータルを使用して警告を作成するときにエントリがアラートに関連する、アラートをサポートするその他のデータだけでなく条件およびイベントを指定するこのデータベースに挿入されます。 | 
| BAM Notification Services インスタンス データベース | BAMAlertsNSMain | Medium | Medium | このデータベースには、notification services が BAM が監視しているシステムに接続する方法を指定するインスタンス情報が含まれています。 | 

#### <a name="sql-server-databases-used-by-sharepoint"></a>SharePoint で使用される SQL Server データベース

| データ ストア名 | 既定のデータベース名 | Volume | 容量の増大 | Description | 
|---|---|---|---|---|
| Windows SharePoint Services 構成データベース | ユーザー定義 | Low | Low | このデータベースには、サーバーのすべてのグローバル設定が含まれます。 | 
| Windows SharePoint Services コンテンツ データベース | ユーザー定義 | Medium | Medium | このデータベースには、すべてのサイト コンテンツ (一覧の項目やドキュメントなど) が格納されます。 | 

## <a name="install-biztalk-a-multi-server-environment"></a>BizTalk をマルチ サーバー環境をインストールします。

1. **Active Directory ドメイン サービス インストール**-複数サーバー環境に BizTalk Server のインストールに必要な最初の手順は、さまざまな BizTalk Server グループとアカウントの Active Directory ドメイン サービスをインストールします。 Active Directory ドメインを作成するには、以下を参照してください:

    - Windows Server 2012 以降: [Active Directory ドメイン サービスのインストール](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/deploy/install-active-directory-domain-services--level-100-)
    - Windows Server 2008 R2: [AD DS のインストールと削除のステップ バイ ステップ ガイド](https://technet.microsoft.com/library/cc755258(WS.10).aspx)

    > [!IMPORTANT]
    > BizTalk Server グループで説明、**ユーザーおよびサービス アカウントを使用で BizTalk Server**複数サーバー環境に BizTalk Server をインストールする前に (このトピックでは) 内のテーブルを作成する必要があります。

2. **必要に応じて、複数の SQL Server のインスタンスをインストール**自社の負荷要件には、複数のメッセージ ボックス データベースを必要または複数の SQL Server インスタンスに、BizTalk Server の I/O 負荷を分散し、複数の SQL Server をインストールする必要がありますがによって求められる場合。必要に応じてインスタンス。 

    データベースの最適化と、BizTalk Server 環境のテストのパフォーマンスに関する詳細については、次を参照してください。、 [BizTalk Server パフォーマンス最適化ガイド](../technical-guides/biztalk-server-2013-performance-optimization-guide.md)です。 

3. **必要に応じて、BizTalk Server グループに複数の BizTalk Server コンピューターをインストール**自社の負荷要件は、BizTalk Server グループに複数の BizTalk Server コンピューターが必要しするには、BizTalk Server Enterprise Edition を使用することによって求められる場合。複数の BizTalk サーバーをスケール アウト処理の要件。 

    > [!IMPORTANT]
    > BizTalk Server のエンタープライズ レベルの機能の多くは (クラスター化、グループへの複数サーバーの追加、ネイティブの 64 ビット処理など)、BizTalk Server Enterprise エディションでのみ提供されます。

4. **累積的な更新プログラムをインストール**-累積的更新プログラムが Windows Update に一覧表示されます。 利用可能なサービス パックおよび累積的な更新プログラムの一覧は、[KB 文書 2555976](http://support.microsoft.com/kb/2555976) をご覧ください。

## <a name="cluster-considerations"></a>クラスターの考慮事項

- **MSDTC のクラスター化**–、Microsoft 分散トランザクション コーディネーター (MSDTC) は、BizTalk Server 環境の中心的なコンポーネントです。 BizTalk Server 環境の他のコンポーネントがクラスター化されている場合、MSDTC もクラスター化することをお勧めします。 

- **SQL Server フェールオーバー クラスタ リングをインストール**– BizTalk Server データベースの高可用性/フォールト トレランスを提供する、BizTalk Server データベースが SQL Server フェールオーバー クラスターにインストールされていることをお勧めします。 SQL Server フェールオーバー クラスターのインストール方法の詳細についてを参照してください。 

    * SQL Server 2016: [Always On フェールオーバー クラスター インスタンス (SQL Server)](https://docs.microsoft.com/sql/sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server)
    * SQL Server 2014: [Windows Server のフェールオーバー クラスタ リング (WSFC) を SQL Server](https://msdn.microsoft.com/library/ms189134(v=sql.120).aspx)

    SQL Server で高可用性およびフォールト トレランスを実現するための構成が完了すると、SQL Server 構成は SQL Server のクラスター インスタンスを他の SQL Server インスタンスと同様に参照できるようになります。

- **クラスター リソースとして、エンタープライズ シングル サインオン マスター シークレット サーバーを構成する**–、エンタープライズ シングル サインオン マスター シークレット サーバーの障害、BizTalk Server 環境のシステム全体の障害が発生することができます。 マスター シークレット サーバーをクラスター リソースとして構成することで、エンタープライズ シングル サインオンのマスター シークレット サーバーで高可用性およびフォールト トレランスを実現することをお勧めします。 マスター シークレット サーバーは BizTalk Server 環境でリソースを特に消費するコンポーネントではないので、SQL Server インスタンスと同じクラスター ノード上でマスター シークレット サーバーをクラスター化することをお勧めします。 クラスター リソースとして、エンタープライズ シングル サインオン マスター シークレット サーバーを構成する方法の詳細については、次を参照してください。[マスター シークレット サーバーをクラスター化](../core/how-to-cluster-the-master-secret-server1.md)です。 

- **BizTalk ホストをクラスター リソースとして構成**– BizTalk Server ホストの複数のインスタンスを実行する高可用性/フォールト トレランスを実現できます。 そのため、特定の状況を除き、BizTalk ホストをクラスター リソースとして構成することはお勧めしません。 たとえば、高可用性およびフォールト トレランスに対応したり、特定の BizTalk Server アダプターで順次配送を実現したりする場合、BizTalk ホストをクラスター リソースとして構成することができます。 詳細については、BizTalk ホストをクラスター リソースとして構成する適切な場合は、次を参照してください。[化されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)です。 参照してください[BizTalk ホストをクラスター リソースとして構成する方法](../core/how-to-configure-a-biztalk-host-as-a-cluster-resource1.md)です。 

- **メッセージ キューをクラスター** – を参照してください[をインストールし、クラスターの MSMQ](https://blogs.msdn.microsoft.com/biztalknotes/2013/03/20/how-to-install-and-cluster-msmq-on-windows-server-2012/)です。

- **クラスター ファイル システム**– を参照してください[ファイル システムをクラスター化する方法](http://go.microsoft.com/fwlink/p/?LinkId=189517)です。

## <a name="use-scom"></a>SCOM を使用します。
Operations Manager 用には、BizTalk Server 管理パックは、BizTalk Server コンポーネントおよび複数のコンピューターで実行されているアプリケーションの包括的な検出と監視を提供します。 BizTalk Server 管理パックの詳細については、http://www.microsoft.com/download/details.aspx?id=39617 を参照してください。
  
## <a name="next"></a>Next  
[BizTalk を構成します。](configure-biztalk-server.md)