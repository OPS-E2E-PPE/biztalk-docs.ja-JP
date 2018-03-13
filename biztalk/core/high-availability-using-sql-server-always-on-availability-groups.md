---
title: "SQL Server Always On 可用性グループを使用して高可用性 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4511a578-77d2-49ee-99bd-f0406ad625d0
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d065013cb4975e6d37e2ab50211c5207852ece64
ms.sourcegitcommit: 6fe505d37e81dc2da43f89548e8977b60a6f5dbd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2018
---
# <a name="high-availability-using-sql-server-always-on-availability-groups"></a>SQL Server Always On 可用性グループを使用して高可用性
SQL Server AlwaysOn 可用性グループを使用して高可用性を構成します。

> [!TIP] 
[ラボをグループの可用性を使用して BizTalk Server 2016 セットアップ](https://skastberg.wordpress.com/2017/02/22/setting-up-my-biztalk-server-2016-using-availability-groups-lab/)Microsoft フィールド エンジニアが書いたステップ バイ ステップ ガイドを提供します。 ラボ環境に基づいてし、いくつかの観測値が含まれています。 試してみて下さい。  

> [!IMPORTANT]
> * Always On 可用性グループでは、SQL Server 2016 以降で使用できます。 SQL Server の以前のバージョンを使用している場合、このトピックは、するには適用されません。 
> * BizTalk Server 2016 には、同期コミット モードがサポートしています非同期コミット モードがサポートされていません。 災害復旧のため、BizTalk Server のバックアップ ジョブを構成およびログ配布を使用することをお勧めします。 参照してください[をバックアップおよび BizTalk Server データベースの復元](../core/backing-up-and-restoring-biztalk-server-databases.md)詳細です。
> 
>    [可用性モード](https://docs.microsoft.com/sql/database-engine/availability-groups/windows/availability-modes-always-on-availability-groups)Always On 可用性グループで、コミットのオプションについて詳しく説明します。 


## <a name="background-and-history"></a>背景と履歴

データの永続化のため、BizTalk Server が SQL Server では大きく依存します。 他のコンポーネントと BizTalk Server 内のホストの受信、処理、またはメッセージをルーティングするなどの多種多様な業務アプリケーションを統合するときに特定のロールがあります。 データベース コンピューターでは、この作業をキャプチャし、ディスクに永続化します。 

BizTalk では、SQL Server フェールオーバー クラスタ リングとログ配布を使用して、その内部設置型データベースの高可用性、バックアップと復元、および災害復旧を提供します。 Azure iaas (Azure の仮想マシン) で SQL Server の以前のバージョンは、フェールオーバー クラスター インスタンス (MSDTC はサポートされません) をサポートしています。 その結果、Azure Vm を使用するときに、BizTalk は HA ソリューションがありませんでした。

SQL Server 2016 から始めて、SQL Server AlwaysOn 可用性グループは、オンプレミスと Azure Vm を使用するため、MSDTC をサポートします。 その結果、SQL Server 2016 の AlwaysOn 機能には、BizTalk データベースでのオンプレミスまたは Azure IaaS のシナリオではサポートされています。 

## <a name="sql-server-2016-alwayson-availability-groups"></a>SQL Server 2016 の AlwaysOn 可用性グループ 
AlwaysOn 可用性グループを展開するには、Windows Server フェールオーバー クラスタ リング (WSFC) クラスターが必要です。 指定された可用性グループの各可用性レプリカは、同一の WSFC クラスターの異なるノード上に存在する必要があります。 WSFC リソース グループは、作成されたすべての可用性グループに対して作成されます。 WSFC クラスターは、このリソース グループを監視して、プライマリ レプリカの正常性を評価します。  

次の図は、1 つのプライマリ レプリカと 4 つのセカンダリ レプリカを含む可用性グループを示しています。  
 
 ![SQLAG_PrimaryReplica](../core/media/sqlag-primaryreplica.png)

クライアントは、可用性グループ リスナーを使用して、特定の可用性グループのプライマリ レプリカに接続できます。 可用性グループ リスナーには、一連の適切な可用性レプリカへのクライアント接続をダイレクトする特定の可用性グループに関連付けられているリソースが用意されています。 

>[!IMPORTANT]
> SQL Server 2016 は、Windows Server 2016 および Windows Server 2012 R2 上の MSDTC AlwaysOn 可用性グループ (AG) をサポートします。 **Windows Server 2012 R2**が必要です、 [3090973](https://support.microsoft.com/kb/3090973) Windows 修正プログラムをインストールします。 
> **Windows Server 2016**いる必要があります、 [RemoteAccessEnabled レジストリ キー](https://support.microsoft.com/kb/3182294)を有効にします。

SQL Server 2016 より前の任意のバージョンの AlwaysOn 可用性グループで MSDTC ができませんでした。  

SQL Server AlwaysOn 可用性グループには、同じ SQL Server インスタンス上のデータベース間の MSDTC はサポートされていません。 これは、同じ SQL server インスタンスで、分散トランザクションにない 2 つの BizTalk データベースをホストできることを意味します。 トランザクションの一貫性を保つためには、別の SQL server のインスタンスでの分散トランザクションに参加している BizTalk データベースをホストする必要があります。 SQL インスタンスが同じコンピューターまたは別のコンピューター上にあるかどうかが重要でないことに注意してください。  


## <a name="providing-high-availability-for-biztalk-databases-using-alwayson-availability-groups"></a>AlwaysOn 可用性グループを使用する BizTalk データベースに高可用性を実現します。 
BizTalk Server の基本的な構成で 9 データベースの最小値は、ルールや BAM などのデータベースに作成されます。 MSDTC により可用性グループの制限に記載されている、次のような構成ではトランザクションの一貫性が確保されません。 

![SQLAG_NoTrans](../core/media/sqlag-notrans.gif)
 
次の 4 つの SQL Server インスタンスは、BizTalk Server データベースがグループ化されることをお勧めします。
 
| インスタンス |ロール |そのグループ内の BizTalk データベース  |
|--- | --- | ---|
|1 |[認証] |SSODB|
|2 |管理 |BizTalkMgmtDb| 
|3 |ランタイム |BizTalkMsgBoxDb<br/> BizTalkRulesEngineDb<br/> BAMPrimaryImport<br/>BAMStarSchema <br/>BAMAlertsApplication |
|4 |Tracking |BizTalkDTADb<br/>EsbItineraryDb<br/>EsbExceptionDb | 
 
1 つ以上のメッセージ ボックス データベースがあるシナリオでは、スケール アウトされたメッセージ ボックス (1 つ以上のメッセージ ボックスで構成)、および各メッセージ ボックス データベースが専用の SQL Server インスタンスにする必要があります。 

BizTalk Server は、SQL Server Analysis Services と BAM 分析とアーカイブのための SQL Server Integration Services により異なります。 SQL Server Integration Services または Azure IaaS での Analysis Services の高可用性ソリューションを行いません。 したがって、BAMArchive と BAMAnalysis Analysis Services データベースに別のスタンドアロン SQL Server インスタンスを使用することをお勧めします。 内部設置型インストールの場合、高可用性構成を設定するため SQL フェールオーバー クラスタ リング インスタンスを使用できます。 

この構成は、以下に示すよう、可用性グループ内の BizTalk データベースのことをお勧めします。  

![SQLAG_Recommended](../core/media/sqlag-recommended.png)
 
BizTalk Server の構成と SQL Server データベース、SQL Server セキュリティ ログイン、SQL エージェント ジョブも作成されます。 AlwaysOn 可用性グループは、データベースを可用性グループ内の管理機能のみを提供します。 ログインと BizTalk の SQL エージェント ジョブは、作成/更新/管理が手動ですべての可用性レプリカで必要があります。  

次の SQL Server セキュリティ ログインの一覧は、BizTalk Server に関連付けられます。 追加のログインを BizTalk Server のアプリケーションを作成するがあります。 その場合は、BizTalk データベースのレプリカをホストする SQL Server のすべてのインスタンス上でそれらをレプリケートする必要があります。 

1. BizTalk アプリケーションのユーザーが (各インプロセス ホストに対応する 1 つまたは複数) 
2. BizTalk 分離ホスト ユーザー (分離ホストごとに対応する 1 つまたは複数) 
3. BizTalk Server 管理者 
4. [BizTalk Server B2B Operators] 
5. BizTalk Server オペレータ 
6. SSO 管理者 
7. BAM 警告ユーザー 
8. BAM 管理 Web サービス ユーザー 
9. ルール エンジン更新サービスのアカウント 

さらにホストを作成した後で別のホストを作成するか、このプロセスの一部として作成された新しい SQL ログインがあります。 対応するレプリカの手動でこれらの SQL ログインを作成することを確認してください。

以下の SQL Server エージェント ジョブが BizTalk Server と関連付けられています。 各サーバーにインストールされるジョブは、インストールされて構成されている機能によって異なります。 これらのジョブのほとんどは、BizTalk Server の構成時に作成されます。 ログ配布の構成を行う際に作成されるものもあります。 これらのジョブは、対応する BizTalk データベースの SQL Server ホストのレプリカの各インスタンスにレプリケートされる必要があります。 これは手動で行う必要があります。 

- BizTalkMgmtDb ジョブ: 
    - BizTalk Server のバックアップ (BizTalkMgmtDb) 
    - CleanupBTFExpiredEntriesJob_BizTalkMgmtDb 
    - BizTalk Server の監視 (BizTalkMgmtDb) 
- BizTalkMsgBoxDb ジョブ: 
    - MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb 
    - MessageBox_Message_Cleanup_BizTalkMsgBoxDb
    - MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb
    - MessageBox_Parts_Cleanup_BizTalkMsgBoxDb 
    - MessageBox_UpdateStats_BizTalkMsgBoxDb 
    - Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb 
    - PurgeSubscriptionsJob_BizTalkMsgBoxDb 
    - TrackedMessages_Copy_BizTalkMsgBoxDb 
- その他のメッセージ ダイアログ上のジョブ
- BizTalkDTADb ジョブ: 
    - DTA Purge and Archive (BizTalkDTADb) 
- BizTalkRulesEngineDb ジョブ: 
    - Rules_Database_Cleanup_BizTalkRuleEngineDb 
- BAMAlertsApplication ジョブ: 
    - 0 または複数の DelAlertHistJob 

異なり SQL フェールオーバー クラスタ リングのインスタンスでは、可用性グループのすべてのレプリカはアクティブな実行、および使用可能なです。 フェールオーバーの各レプリカでは、SQL エージェント ジョブが複製されて、ときにファイルが現在プライマリ ロールまたはセカンダリ ロールに関係なく、対応するレプリカに対して実行されます。 これらのジョブが現在プライマリ レプリカでのみ実行されるようにするはのようにすべてのジョブのすべての段階、IF ブロック内で囲む必要があります。 

    IF (sys.fn_hadr_is_primary_replica(‘dbname’) = 1)  
    BEGIN  
    …  
    END
  
置換 `‘dbname’` 対応するデータベース名を対象となるジョブが実行するよう構成します。 次の例では、BizTalkMsgBoxDb TrackedMessages_Copy_BizTalkMsgBoxDb、この変更を示しています。 
 
 ![SQLAG_AgentJob](../core/media/sqlag-agentjob.gif)

### <a name="configure-biztalk-server-when-availability-groups-are-already-set-up"></a>可用性グループが既に設定されている場合は、BizTalk Server を構成します。

1. OS 要件を確認します。 
* すべての**Windows Server 2012 R2**コンピューターでは、インストール、 [3090973 MSDTC 修正プログラム](https://support.microsoft.com/kb/3090973)(サポート技術情報記事が表示されます)
* すべての**Windows Server 2016** 、コンピューターを有効にする、 [RemoteAccessEnabled レジストリ キー](https://support.microsoft.com/kb/3182294) (サポート技術情報記事が表示されます)
2. さまざまな BizTalk データベースをホストするには、少なくとも 4 つの異なる SQL インスタンスがあることを確認してください。 セカンダリ レプリカは、異なる SQL インスタンスに設定する必要があります。 これは、結果、8 個の SQL インスタンス (1 プライマリと 1 のセカンダリ レプリカを 4 個のインスタンスの各)、最小値、4 つの可用性グループの最小値。 この可用性グループの構成については、上記の図を参照してください。 ことを確認して可用性グループで作成された、 **データベースごとの DTC サポート** オプションこれは後で変更できません。 
3. BizTalk Server を構成して、SQL server 名を指定は、実際のマシン名の代わりに、可用性グループのリスナー名を使用します。 これにより、現在のプライマリ レプリカで BizTalk データベース、ログイン、および SQL エージェント ジョブが作成されます。 
4. (ホスト インスタンス、SSO サービス、IIS、ルール エンジン更新サービス、BAMAlerts サービスおよびなど)、BizTalk 処理を停止し、SQL エージェント ジョブを停止します。 
5. それぞれの可用性グループを BIzTalk データベースを追加します。 
6. 内の SQL エージェント ジョブ ステップの本文を囲む `IF` ブロック (前述) をターゲットがプライマリ レプリカである場合にのみを実行するかどうかを確認します。 
7. それらを対応するレプリカでレプリケートするには、ログインと SQL エージェント ジョブのスクリプトを作成します。 
8. レプリケート SQL DBMail プロファイルとアカウント BAM 警告のセカンダリ レプリカをホストしている対応する SQL インスタンスにします。 
9. 追加のメッセージ ボックス データベースを追加するか、ビューを展開する新しい BAM アクティビティ/以降では、新しい場合は、新しいメッセージ ボックス データベースまたは現在のプライマリ レプリカ上の BAM 警告データベースの SQL ジョブが作成されます。 プライマリ レプリカで編集することを確認してから、対応するセカンダリ レプリカでそれらを手動で作成します。 

この構成を実行することも、プライマリ レプリカをホストしている SQL インスタンスを使用します。 この場合は、BizTalk の構成後に次のように実行します。、 `UpdateDatabase.vbs` と `UpdateRegistry.vbs` 上記の手順の後の BizTalk コンピューター上のスクリプトです。 これについては、次のセクションで詳しく説明します。  
 
### <a name="move-biztalk-server-databases-of-an-existing-biztalk-system-to-availability-groups"></a>既存の BizTalk システムの BizTalk Server データベースを可用性グループに移動します。

1. OS 要件を確認します。 
* すべての**Windows Server 2012 R2**コンピューターでは、インストール、 [3090973 MSDTC 修正プログラム](https://support.microsoft.com/kb/3090973)(サポート技術情報記事が表示されます)
* すべての**Windows Server 2016** 、コンピューターを有効にする、 [RemoteAccessEnabled レジストリ キー](https://support.microsoft.com/kb/3182294) (サポート技術情報記事が表示されます)
2. さまざまな BizTalk データベースをホストするには、少なくとも 4 つの異なる SQL インスタンスがあることを確認してください。 セカンダリ レプリカは、異なる SQL インスタンスに設定する必要があります。 これは、結果、8 個の SQL インスタンス (1 プライマリと 1 のセカンダリ レプリカを 4 個のインスタンスの各)、最小値、4 つの可用性グループの最小値。 この可用性グループの構成については、上記の図を参照してください。 ことを確認して可用性グループで作成された **データベースごとの DTC サポート** オプションこれは後で変更できません。  
3. BizTalk 処理と SQL エージェント ジョブを停止します。 
4. すべての BizTalk データベースの完全バックアップを実行します。 
5. 現在、プライマリ ロールでは、可用性グループ内の SQL インスタンス上の BizTalk データベースを復元します。 
6. ログインと SQL エージェント スクリプトを作成可用性グループにプライマリ ロールの現在の対応する SQL インスタンス上のジョブです。  
7. 実行、 `UpdateDatabase.vbs` と `UpdateRegistry.vbs` 、次の手順を使用して BizTalk マシン上のスクリプトです。 入力の更新情報の xml で新しいサーバー名として、可用性グループ リスナーを入力します。  
    1. BizTalk Server では、すべての BizTalk サービスとエンタープライズ SSO サービスを停止します。 SQL Server 上の SQL エージェント サービスを停止します。 
    2. BizTalk Server では、次のフォルダーに SampleUpdateInfo.xml を編集します。 
 
        32 ビット コンピューター: `%SystemRoot%\Program Files\Microsoft BizTalk Server 20xx\Schema\Restore`
 
        64 ビット コンピューター: `%SystemRoot%\Program Files (x86)\Microsoft BizTalk Server 20xx\Bins32\Schema\Restore`
 
            1. Replace "SourceServer" with the source server name (old SQL Server hosting old databases).  
            2. Replace "DestinationServer" with the name of the destination server, which should be the availability group listener name.  
            3. If you have the BAMAnalysis, BAM databases or RuleEngineDB, uncomment the appropriate sections. 

    3. コマンド プロンプトを開きに移動します。 
 
        32 ビット コンピューター: `%SystemRoot%\Program Files\Microsoft BizTalk Server 20xx\Schema\Restore` 
 
        64 ビット コンピューター: `%SystemRoot%\Program Files (x86)\Microsoft BizTalk Server 20xx\Bins32\Schema\Restore` 
 
        コマンド プロンプトで次のコマンドを実行します。  
    `cscript UpdateDatabase.vbs SampleUpdateInfo.xml`  
 
        BizTalk グループ内の 1 つだけのサーバーで UpdateDatabase.vbs を実行します。 

    4. この BizTalk グループ内のすべての BizTalk Server コンピューターの次のフォルダーには、編集した SampleUpdateInfo.xml ファイルをコピーします。 
 
        32 ビット コンピューター: `%SystemRoot%\Program Files\Microsoft BizTalk Server 20xx\Schema\Restore` 
 
        64 ビット コンピューター: `%SystemRoot%\Program Files (x86)\Microsoft BizTalk Server 20xx\Bins32\Schema\Restore` 
 
    5. BizTalk Server グループ内の各コンピューターでコマンド プロンプトを開いてに移動します。 
 
        32 ビット コンピューター: `%SystemRoot%\Program Files\Microsoft BizTalk Server 20xx\Schema\Restore`
 
        64 ビット コンピューター: `%SystemRoot%\Program Files (x86)\Microsoft BizTalk Server 20xx\Bins32\Schema\Restore` 
 
        コマンド プロンプトで次のコマンドを実行します。  
    `cscript UpdateRegistry.vbs SampleUpdateInfo.xml` 
 
        BizTalk グループ内のすべてのサーバーで UpdateRegistry.vbs を実行します。 
 
8. ここで、データベースをそれぞれの可用性グループに移動します。 
9. SQL DBMail プロファイルと SQL の BAM 警告用のアカウントをインスタンス化 BAMAlerts データベースのレプリカをホストしているレプリケーションを実行します。 
10. ターゲットがプライマリである場合にのみを実行するかどうかを確認する場合はブロック内では、SQL エージェント ジョブ ステップの本文を囲みます。 
11. これらを対応するレプリカにレプリケートするには、ログインと SQL エージェント ジョブのスクリプトを作成します。 UpdateDatabase スクリプトはまた、Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb および TrackedMessages_Copy_BizTalkMsgBoxDb ジョブ内のサーバー名を更新します。 したがって UpdateDatabase スクリプトを実行した後のみ SQL エージェント ジョブのスクリプトを作成します。 

## <a name="requirements"></a>必要条件 
* BizTalk Server 2016 Enterprise
* SQL Server 2016 Enterprise
* Windows Server 2012 R2
* Windows Server 2016 

### <a name="availability-group-listener-configured-with-non-default-port-1433"></a>既定以外に構成されている可用性グループ リスナーのポート (1433) 
BizTalk Server コンピューターでエイリアス SQL を使用します。 

### <a name="supporting-availability-group-multi-subnet-failovers"></a>可用性グループ マルチサブネット フェールオーバーのサポート 
BizTalk Server を使用して Microsoft OLE DB データベース接続をサポートしない、 **MultiSubnetFailover**接続オプションを選択します。 BizTalk Server がサポートされません、 `MultiSubnetFailover (=TRUE)` 接続オプション、およびこれがマルチ サブネット フェールオーバー中に、上位の復旧時間あります。 

### <a name="read-only-routing"></a>読み取り専用ルーティング 
読み取り専用ルーティングは読み取り専用ワークロードを許可するように構成されているセカンダリ レプリカを可用性グループ リスナーに対する受信接続をルーティングする SQL Server の機能を表します。 

BizTalk は使いません読み取り専用ルーティングのいずれかのデータベースの接続。 つまり、可用性グループの可用性レプリカに「読み取り可能なセカンダリ」オプションでは、BizTalk データベースの接続には、影響はありません。 

### <a name="behavior-of-biztalk-server-host-instances-during-sql-server-failover"></a>SQL Server フェールオーバー時の BizTalk Server ホスト インスタンスの動作 
SQL Server 可用性グループにフェールオーバーが発生した場合、可用性グループ上の BizTalk Server データベースは一時的に使用できません。 

#### <a name="behavior-of-in-process-host-instances-during-sql-server-failover"></a>SQL Server フェールオーバー時のインプロセス ホスト インスタンスの動作 
BizTalk Server データベースが利用できない場合、BizTalk Server ホストのインプロセスでインスタンスがリサイクルされる SQL Server への接続が復元されるまで。 SQL Server データベースへの接続が復元されると、ドキュメントの処理は通常どおり再開されます。
 
#### <a name="behavior-of-isolated-host-instances-during-sql-server-failover"></a>SQL Server フェールオーバー時の分離ホスト インスタンスの動作 
BizTalk Server データベースが利用できない場合は、BizTalk Server ホストの分離インスタンスが一時停止し、および BizTalk Server アプリケーション ログに次のようなエラーが生成します。 

    All receive locations are being temporarily disabled because either the MessageBox or Configuration database is not available. When these databases become available, the receive locations will be automatically enabled.
 
SQL Server データベースへの接続が復元されると、次のような情報メッセージが BizTalk Server アプリケーション ログに書き込まれ、ドキュメントの処理は通常どおりに再開されます。 

    All receive locations are being enabled because both the MessageBox and Configuration databases are back online.

#### <a name="biztalk-server-log-shipping-for-disaster-recovery"></a>BizTalk Server に対してログ配布を災害復旧 
BizTalk Server データベースを使用してデータベースのスタンバイ機能を実装してログ配布します。 スタンバイ サーバーが、実稼働データベース サーバー、データベースの処理を再開できるようにログ配布の自動化のバックアップとデータベースと、トランザクション ログ ファイルの復元は、BizTalk Server は失敗します。 

**可用性グループ内のセカンダリ データベースは、バックアップではありません。** BizTalk データベースのバックアップを続行し、BizTalk Server のログ配布ジョブを使用して独自のトランザクション ログに記録します。 送信される BizTalk ログを実装する方法は、バックアップがすべてのデータベースの現在のプライマリ レプリカに対して常に実行することを確認します。 可用性グループのバックアップの設定は BizTalk Server のログ配布ジョブでは受け入れられません。 

、BizTalk データベースのバックアップ ジョブを他の BizTalk データベースを追加する場合は、バックアップのセットアップ時に、それらのデータベース サーバーとして可用性グループ リスナー名を使用することを確認します。  
 
## <a name="references"></a>References 
 
* [BizTalk Server データベースの高可用性を実現します。](../core/providing-high-availability-for-biztalk-server-databases.md)  
* [Microsoft Azure の仮想マシンの Microsoft サーバー ソフトウェアのサポート](https://support.microsoft.com/kb/2721672)  
* [SQL Server データベース ミラーリング、ボリューム シャドウ コピー サービス、および AlwaysOn の使用](../core/sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson.md)  
* [AlwaysOn 可用性グループ (SQL Server) の概要](https://msdn.microsoft.com/library/ff877884.aspx)  
* [データベース ミラーリングまたは AlwaysOn 可用性グループ (SQL Server) のデータベースにまたがるトランザクションのサポート](https://msdn.microsoft.com/library/ms366279.aspx)  
* [SQL Server Windows Server 2012 R2 での MSDTC からトランザクションの結果を受信すると、reenlist を呼び出すことができません。](https://support.microsoft.com/kb/3090973)  
* [BizTalk Server データベースのバックアップと復元](../core/backing-up-and-restoring-biztalk-server-databases.md)  
* [BizTalk Server データベースを移動する方法](../core/how-to-move-the-biztalk-server-databases.md)  
* [データベースを復元する方法](../core/how-to-restore-your-databases.md)   
* [マルチ サブネットの可用性グループ内の接続のタイムアウト](https://blogs.msdn.microsoft.com/alwaysonpro/2014/06/03/connection-timeouts-in-multi-subnet-availability-group/)  
 
## <a name="known-limitations"></a>既知の制限事項 

これらの制限は BizTalk Server、SQL Server AlwaysOn 可用性グループ、および Azure の仮想マシンです。 これらの制限事項は、将来の解決を取得しない可能性があります。 

* ログイン、SQL エージェント ジョブ、SQL データベース メール プロファイルとアカウントは、可用性グループ内で管理されていません。 これには、プライマリ レプリカに対して実行するかどうかを確認するジョブの手動で変更が必要です。 
* SQL Server Analysis Services と SQL Server Integration Services は、可用性グループには参加しません。 SQL Server からのこのサポートなしは、Azure の仮想マシンでこれらの HA ソリューションはありません。 BizTalk Server BAM 機能は、次のサービスに依存します。 
* 可用性グループは、同じ SQL インスタンス上のデータベース間で MSDTC をサポートしていません。 そのため、BizTalk を構成する最小 8 個の SQL インスタンスが必要です。 
* MSDTC に対処するには、2 つのサーバーをホストしている 4 つの SQL インスタンスごとの最小値を使用して可用性グループ、BizTalk データベースでの制限を構成できます。 ただし、Azure Virtual Machines で ILB できません複数の IP アドレス。 これにより、別のサーバーで SQL の各インスタンスを作成することです。 
* BizTalk Server では、読み取り専用ルーティングを使用できません。 
* BizTalk Server が設定されていない、 `MultiSubnetFailover` 接続プロパティです。 
* ログ配布を使用して BizTalk バックアップ ジョブは、可用性グループの設定、バックアップの設定に関係なく、プライマリ レプリカを常に対象します。 
 
