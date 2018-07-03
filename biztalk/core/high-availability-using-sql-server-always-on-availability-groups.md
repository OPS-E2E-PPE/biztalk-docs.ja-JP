---
title: SQL Server Always On 可用性グループを使用して高可用性 |Microsoft Docs
description: SQL Server 常にで使用可能なグループ (AG)、システム要件や制限事項などを使用して高可用性 (HA) ソリューションを取得する別のノードで BizTalk Server データベースをグループ化します。 Always on AG では、Windows Server フェールオーバー クラスタ リング (WSFC) が必要です。
ms.custom: ''
ms.date: 06/27/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4511a578-77d2-49ee-99bd-f0406ad625d0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24a72698a97aa79ccd1b748a390f8e919ff0717f
ms.sourcegitcommit: 6379723045cf05ed36f2bc500f6b41be1135f47c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37069399"
---
# <a name="high-availability-using-sql-server-always-on-availability-groups---biztalk-server"></a>SQL Server Always On 可用性グループの BizTalk Server を使用して高可用性
SQL Server AlwaysOn 可用性グループを使用して高可用性を構成します。

> [!TIP]
> [ラボをグループの可用性を使用して BizTalk Server 2016 セットアップ](https://skastberg.wordpress.com/2017/02/22/setting-up-my-biztalk-server-2016-using-availability-groups-lab/)Microsoft のフィールド エンジニアによって作成されたステップ バイ ステップ ガイドを提供します。 ラボ環境に基づいており、いくつか所見が含まれています。 試してみて下さい。  
> 
> [!IMPORTANT]
> * Always On 可用性グループは、SQL Server 2016 以降から使用できます。 SQL Server の以前のバージョンを使用している場合にこのトピックでは適用されません。 
> * BizTalk Server 2016 には、同期コミット モードがサポートしています非同期コミット モードがサポートされていません。 ディザスター リカバリーを BizTalk Server のバックアップ ジョブを構成およびログ配布を使用することをお勧めします。 参照してください[Backing Up and BizTalk Server データベースの復元](../core/backing-up-and-restoring-biztalk-server-databases.md)に関する特定の詳細。
> 
>    [可用性モード](https://docs.microsoft.com/sql/database-engine/availability-groups/windows/availability-modes-always-on-availability-groups)Always On 可用性グループのコミットのオプションの詳細。 


## <a name="background-and-history"></a>背景と履歴

データの永続性、BizTalk Server が SQL Server では大きく依存します。 その他のコンポーネントおよび BizTalk server ホストの受信、処理、またはメッセージのルーティングなどのさまざまなビジネス アプリケーションを統合するときに特定のロールがあります。 データベース コンピューターは、この動作をキャプチャし、ディスクに永続化します。 

BizTalk では、SQL Server フェールオーバー クラスタ リングとログ配布を使用して、そのオンプレミス データベースの高可用性、バックアップと復元、およびディザスター リカバリーを提供します。 Azure iaas (Azure の仮想マシン) で SQL Server の以前のバージョンは、フェールオーバー クラスター インスタンス (MSDTC はサポートされません) をサポートしています。 その結果、Azure Vm を使用する場合、BizTalk は、HA ソリューションがありませんでした。

SQL Server 2016 以降、SQL Server AlwaysOn 可用性グループは、オンプレミスと Azure Vm を使用して MSDTC をサポートします。 その結果、BizTalk データベース、オンプレミスまたは Azure IaaS のシナリオで、SQL Server 2016 AlwaysOn 機能はサポートされています。 

## <a name="sql-server-2016-alwayson-availability-groups"></a>SQL Server 2016 AlwaysOn 可用性グループ 
AlwaysOn 可用性グループを展開するには、Windows Server フェールオーバー クラスタ リング (WSFC) クラスターが必要です。 指定された可用性グループの各可用性レプリカは、同一の WSFC クラスターの異なるノード上に存在する必要があります。 WSFC リソース グループは、作成されたすべての可用性グループに対して作成されます。 WSFC クラスターは、このリソース グループを監視して、プライマリ レプリカの正常性を評価します。  

次の図は、1 つのプライマリ レプリカと 4 つのセカンダリ レプリカを含む可用性グループを示しています。  
 
 ![SQLAG_PrimaryReplica](../core/media/sqlag-primaryreplica.png)

クライアントは、可用性グループ リスナーを使用して特定の可用性グループのプライマリ レプリカに接続できます。 可用性グループ リスナーは、一連の適切な可用性レプリカに対するクライアント接続を送るための特定の可用性グループに関連付けられているリソースを提供します。 

>[!IMPORTANT]
> SQL Server 2016 では、Windows Server 2016 および Windows Server 2012 R2 で MSDTC AlwaysOn 可用性グループ (AG) をサポートしています。 **Windows Server 2012 R2**が必要です、 [3090973](https://support.microsoft.com/kb/3090973)インストールする Windows 修正プログラム。 
> **Windows Server 2016**いる必要があります、 [RemoteAccessEnabled レジストリ キー](https://support.microsoft.com/kb/3182294)を有効にします。

SQL Server は、2016年より前のバージョンの AlwaysOn AG で MSDTC をサポートしていません。  

SQL Server AlwaysOn 可用性グループでは、同じ SQL Server インスタンス上のデータベース間の MSDTC はサポートされていません。 つまり、同じ SQL server インスタンスに分散トランザクションに 2 つの BizTalk データベースをホストすることができます。 トランザクションの一貫性を保つのためには、別の SQL server インスタンスでの分散トランザクションに参加している BizTalk データベースをホストする必要があります。 SQL インスタンスが同じコンピューターまたは別のコンピューター上にあるかどうかが重要でないことに注意してください。 


## <a name="provide-high-availability-for-biztalk-databases-using-alwayson-availability-groups"></a>AlwaysOn 可用性グループを使用して BizTalk データベースの高可用性を実現します。 
BizTalk Server の基本的な構成で 9 データベースの最小値は、ルールや BAM などのデータベースに作成されます。 MSDTC が原因で可用性グループの制限が前に説明した、次などの構成ではトランザクションの一貫性が確保されません。 

![SQLAG_NoTrans](../core/media/sqlag-notrans.gif)
 
BizTalk Server データベースが次の 4 つの SQL Server インスタンスにまとめられていることをお勧めします。
 
| Instance |ロール |そのグループ内の BizTalk データベース  |
|--- | --- | ---|
|1 |[認証] |SSODB|
|2 |管理 |BizTalkMgmtDb| 
|3 |ランタイム |BizTalkMsgBoxDb<br/> BizTalkRulesEngineDb<br/> BAMPrimaryImport<br/>BAMStarSchema <br/>BAMAlertsApplication |
|4 |Tracking |BizTalkDTADb<br/>EsbItineraryDb<br/>EsbExceptionDb | 
 
スケール アウト メッセージ ボックス シナリオ (1 つ以上のメッセージ ボックスと構成) では、1 つ以上のメッセージ ボックス データベースと、各メッセージ ボックス データベースは、独自の SQL Server インスタンスである必要があります。 

BizTalk Server は、SQL Server Analysis Services と BAM 分析とアーカイブのための SQL Server Integration Services にも依存します。 SQL Server は Integration Services または Azure IaaS での Analysis Services の高可用性ソリューションを提供していません。 そのため、BAMArchive と BAMAnalysis Analysis Services データベースを別のスタンドアロン SQL Server インスタンスを使用することをお勧めします。 オンプレミスでインストールする場合、高可用性構成の設定を SQL フェールオーバー クラスタ リング インスタンスを使用できます。 

この構成は、次の図に、可用性グループ内の BizTalk データベースのことをお勧めします。  

![SQLAG_Recommended](../core/media/sqlag-recommended.png)
 
BizTalk Server の構成と SQL Server データベース、SQL Server セキュリティ ログイン、SQL エージェント ジョブも作成されます。 AlwaysOn 可用性グループは、可用性グループ内のデータベースを管理する機能のみを提供します。 ログインと BizTalk の SQL エージェント ジョブは、作成および更新/管理できる手動ですべての可用性レプリカにする必要があります。  

> [!NOTE]
> SQL Server 2016 Service Pack 2 では、同じ可用性グループ内の複数のデータベース間の DTC トランザクションをサポートします。 BizTalk Server では、CU5 以降、この機能をサポートします。

次の SQL Server セキュリティ ログインの一覧は、BizTalk Server に関連付けられます。 追加のログインが、BizTalk Server アプリケーション用に作成する必要があります。 そうである場合は、BizTalk データベースのレプリカをホストする SQL Server のすべてのインスタンスでこれらをレプリケートする必要があります。 

1. BizTalk アプリケーション ユーザーが (各インプロセス ホストに対応する 1 つまたは複数) 
2. BizTalk 分離ホスト ユーザー (分離ホストごとに対応する 1 つまたは複数) 
3. BizTalk Server 管理者 
4. [BizTalk Server B2B Operators] 
5. BizTalk Server オペレータ 
6. SSO 管理者 
7. BAM 警告ユーザー 
8. BAM 管理 Web サービス ユーザー 
9. ルール エンジン更新サービス アカウント 

追加のホストを作成した後で追加のホストを作成するか、このプロセスの一環として作成された新しい SQL ログインがあります。 対応するレプリカに手動でこれらの SQL ログインを作成することを確認しておく必要があります。

以下の SQL Server エージェント ジョブが BizTalk Server と関連付けられています。 各サーバーにインストールされるジョブは、インストールされて構成されている機能によって異なります。 これらのジョブのほとんどは、BizTalk Server の構成中に作成されます。 ログ配布の構成を行う際に作成されるものもあります。 これらのジョブは、対応する BizTalk データベースの SQL Server ホストのレプリカの各インスタンスにレプリケートする必要があります。 これは手動で実行する必要があります。 

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
- 追加のメッセージ ダイアログ上のジョブ
- BizTalkDTADb ジョブ: 
    - DTA Purge and Archive (BizTalkDTADb) 
- BizTalkRulesEngineDb ジョブ: 
    - Rules_Database_Cleanup_BizTalkRuleEngineDb 
- BAMAlertsApplication ジョブ: 
    - 0 または複数の DelAlertHistJob 

異なり SQL フェールオーバー クラスタ リングのインスタンスでは、可用性グループですべてのレプリカはアクティブ、実行中、および使用できます。 SQL エージェント ジョブが各レプリカのフェールオーバーで重複しているときにするかどうかは、現在プライマリ ロールまたはセカンダリ ロールに関係なく、対応するレプリカに対して実行されます。 これらのジョブが現在プライマリ レプリカでのみ実行されるようにするに示すようにすべての手順では、すべてのジョブ、IF ブロックで囲む必要があります。 

    ```
    IF (sys.fn_hadr_is_primary_replica(‘dbname’) = 1)  
    BEGIN  
    …  
    END
    ```
  
置換`‘dbname’`対応するデータベース名を対象となるジョブが実行するよう構成します。 次の例では、BizTalkMsgBoxDb で TrackedMessages_Copy_BizTalkMsgBoxDb にこの変更を示しています。 
 
 ![SQLAG_AgentJob](../core/media/sqlag-agentjob.gif)

### <a name="configure-biztalk-when-availability-groups-are-already-set-up"></a>可用性グループが既にセットアップされているときに BizTalk を構成します。

1. OS の要件を確認します。 
2. すべての**Windows Server 2012 R2** 、コンピューターのインストール、 [3090973 MSDTC の修正プログラム](https://support.microsoft.com/kb/3090973)(サポート技術情報の記事が表示されます)
3. すべての**Windows Server 2016** 、コンピューターを有効にする、 [RemoteAccessEnabled レジストリ キー](https://support.microsoft.com/kb/3182294) (サポート技術情報の記事が表示されます)
4. さまざまな BizTalk データベースをホストするには少なくとも 4 つの異なる SQL インスタンスを確認します。 セカンダリ レプリカは、異なる SQL インスタンスで設定する必要があります。 これにより、(1 プライマリと 1 のセカンダリ レプリカを 4 つのインスタンスの各)、8 個の SQL インスタンスの最小値と 4 つの可用性グループの最小値。 この可用性グループ構成上の図を参照してください。 ことを確認して可用性グループを作成する、**データベースごとの DTC サポート**オプションとして、この後で変更することはできません。 
5. ときに BizTalk Server を構成し、SQL サーバー名を指定する実際のコンピューター名ではなく、可用性グループのリスナー名を使用します。 これにより、現在のプライマリ レプリカで、BizTalk データベース、ログイン、および SQL エージェント ジョブが作成されます。 
6. (ホスト インスタンス、SSO サービス、IIS、ルール エンジン更新サービス、BAMAlerts サービス、およびなど)、BizTalk 処理を停止し、SQL エージェント ジョブを停止します。 
7. BIzTalk データベースをそれぞれの可用性グループに追加します。 
8. 内の SQL エージェント ジョブ ステップの本文を囲む`IF`ブロック (前述) をターゲットがプライマリ レプリカである場合にのみを実行するかどうかを確認します。 
9. 対応するレプリカでこれらをレプリケートするには、ログインと SQL エージェント ジョブのスクリプトを作成します。 
10. SQL DBMail プロファイルと、セカンダリ レプリカをホストしている、対応する SQL インスタンスで BAM 警告用のアカウントのレプリケート。 
11. 追加のメッセージ ボックス データベースを追加する新しい BAM アクティビティ/ビュー以降では、新しいし展開する場合は、新しいメッセージ ボックス データベースまたは現在のプライマリ レプリカ上の BAM 警告データベースの SQL ジョブが作成されます。 プライマリ レプリカで編集することを確認し、対応するセカンダリ レプリカでそれらを手動で作成します。 

この構成を実行することも、プライマリ レプリカをホストしている SQL インスタンスを使用します。 この場合、BizTalk の構成後に実行、`UpdateDatabase.vbs`と`UpdateRegistry.vbs`BizTalk コンピューター上の手順の後のスクリプト。 これは、次のセクションで詳しく説明します。  
 
### <a name="move-existing-biztalk-databases-to-availability-groups"></a>既存の BizTalk データベースを可用性グループに移動します。

1. OS の要件を確認します。 
2. すべての**Windows Server 2012 R2** 、コンピューターのインストール、 [3090973 MSDTC の修正プログラム](https://support.microsoft.com/kb/3090973)(サポート技術情報の記事が表示されます)
3. すべての**Windows Server 2016** 、コンピューターを有効にする、 [RemoteAccessEnabled レジストリ キー](https://support.microsoft.com/kb/3182294) (サポート技術情報の記事が表示されます)
4. さまざまな BizTalk データベースをホストするには少なくとも 4 つの異なる SQL インスタンスを確認します。 セカンダリ レプリカは、異なる SQL インスタンスで設定する必要があります。 これにより、(1 プライマリと 1 のセカンダリ レプリカを 4 つのインスタンスの各)、8 個の SQL インスタンスの最小値と 4 つの可用性グループの最小値。 この可用性グループ構成上の図を参照してください。 ことを確認して可用性グループを作成する**データベースごとの DTC サポート**オプションとして、この後で変更することはできません。  
5. BizTalk 処理、SQL エージェント ジョブを停止します。 
6. すべての BizTalk データベースの完全バックアップを実行します。 
7. 可用性グループのプライマリ ロールの現在の SQL インスタンス上の BizTalk データベースを復元します。 
8. スクリプト ログインと SQL エージェント ジョブは現在、可用性グループのプライマリ ロールに対応する SQL インスタンスにします。  
9. 実行、`UpdateDatabase.vbs`と`UpdateRegistry.vbs`次の手順を使用して BizTalk のマシン上のスクリプト。 入力の更新情報の xml で新しいサーバー名として、可用性グループ リスナーを入力します。  
    1. BizTalk Server では、すべての BizTalk サービスとエンタープライズ SSO サービスを停止します。 SQL Server で SQL エージェント サービスを停止します。 
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
 
    5. BizTalk Server グループ内の各コンピューターでコマンド プロンプトを開きに移動します。 
 
        32 ビット コンピューター: `%SystemRoot%\Program Files\Microsoft BizTalk Server 20xx\Schema\Restore`
 
        64 ビット コンピューター: `%SystemRoot%\Program Files (x86)\Microsoft BizTalk Server 20xx\Bins32\Schema\Restore` 
 
        コマンド プロンプトで次のコマンドを実行します。  
    `cscript UpdateRegistry.vbs SampleUpdateInfo.xml` 
 
        BizTalk グループ内のすべてのサーバーで UpdateRegistry.vbs を実行します。 
 
10. 今すぐデータベースをそれぞれの可用性グループに移動します。 
11. SQL DBMail プロファイルと、SQL で BAM 警告のアカウントを BAMAlerts データベースのレプリカをホストのインスタンスをレプリケートします。 
12. ターゲットがプライマリである場合にのみを実行するかどうかを確認する IF ブロック内では、SQL エージェント ジョブ ステップの本文を囲みます。 
13. これらを対応するレプリカにレプリケートするには、ログインと SQL エージェント ジョブのスクリプトを作成します。 UpdateDatabase スクリプトでは、Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb および TrackedMessages_Copy_BizTalkMsgBoxDb ジョブ内のサーバー名も更新されます。 そのスクリプト UpdateDatabase スクリプトを実行した後にのみ、SQL エージェント ジョブ。 

## <a name="requirements"></a>要件 
* BizTalk Server 2016 Enterprise
* SQL Server 2016 Enterprise または SQL Server 2016 Standard (を参照してください**既知の制限**このトピックの)
* Windows Server 2012 R2 または Windows Server 2016 

### <a name="availability-group-listener-configured-with-non-default-port-1433"></a>既定以外で構成されている可用性グループ リスナー ポート (1433) 
BizTalk Server コンピューターでエイリアス SQL を使用します。 

### <a name="support-availability-group-multi-subnet-failovers"></a>サポートの可用性グループ マルチ サブネット フェールオーバー 
BizTalk Server を使用して Microsoft OLE DB のデータベースの接続でサポートされていない、 **MultiSubnetFailover**接続オプションを選択します。 BizTalk Server がサポートしていません、`MultiSubnetFailover (=TRUE)`接続オプション、およびこれが上位の復旧時間マルチ サブネット フェールオーバー中にあります。 

### <a name="read-only-routing"></a>読み取り専用ルーティング 
読み取り専用ルーティングは読み取り専用ワークロードを許可するように構成されたセカンダリ レプリカを可用性グループ リスナーに対する着信接続をルーティングする SQL Server の機能を表します。 

BizTalk は使いません読み取り専用ルーティングのいずれかのデータベースに接続します。 つまり、可用性グループ内の可用性レプリカ上の「読み取り可能なセカンダリ」オプションでは、BizTalk データベースの接続には、影響はありません。 

### <a name="behavior-of-biztalk-host-instances-during-sql-server-failover"></a>SQL Server フェールオーバー時の BizTalk ホスト インスタンスの動作 
SQL Server 可用性グループにフェールオーバーが発生した場合、可用性グループの BizTalk Server データベースの内容が一時的に使用します。 

#### <a name="behavior-of-in-process-host-instances-during-sql-server-failover"></a>SQL Server フェールオーバー時のインプロセス ホスト インスタンスの動作 
BizTalk Server データベースが使用できない場合、BizTalk Server ホストのインプロセス インスタンスがリサイクルされる SQL Server への接続が復元されるまで。 SQL Server データベースへの接続が復元されると、通常ドキュメントの処理を再開します。
 
#### <a name="behavior-of-isolated-host-instances-during-sql-server-failover"></a>SQL Server フェールオーバー時の分離ホスト インスタンスの動作 
BizTalk Server データベースが利用できない場合は、BizTalk Server ホストの分離インスタンスが一時停止し、および BizTalk Server アプリケーション ログに次のようなエラーが生成されます。 

    All receive locations are being temporarily disabled because either the MessageBox or Configuration database is not available. When these databases become available, the receive locations will be automatically enabled.
 
SQL Server データベースへの接続が復元されると、次のような情報メッセージは、BizTalk Server アプリケーション ログに書き込まれます、ドキュメントの処理を通常どおり再開します。 

    All receive locations are being enabled because both the MessageBox and Configuration databases are back online.

#### <a name="log-shipping-for-disaster-recovery"></a>ログ配布のディザスター リカバリー 
BizTalk Server データベースを使用してデータベースのスタンバイ機能を実装するログ配布します。 スタンバイ サーバーが、実稼働データベース サーバー、データベースが処理を再開できるようにログ配布のバックアップとデータベースとそのトランザクション ログ ファイルの復元を自動化する BizTalk Server は失敗します。 

**可用性グループ内のセカンダリ データベースは、バックアップではありません。** BizTalk データベースのバックアップを続行し、BizTalk Server のログ配布ジョブを使用して、トランザクション ログに記録します。 BizTalk ログ配布を実装する方法は、バックアップは常にすべてのデータベースの現在のプライマリ レプリカに対して実行することにより、します。 可用性グループのバックアップ設定は、BizTalk Server のログ配布ジョブでは無視されます。 

BizTalk データベースのバックアップ ジョブに他の BizTalk データベースを追加する場合は、バックアップのセットアップ時に、それらのデータベース サーバーとして、可用性グループ リスナー名を使用することを確認します。  
 
## <a name="references"></a>References 
 
* [BizTalk Server データベースの高可用性を実現します。](../core/providing-high-availability-for-biztalk-server-databases.md)  
* [Microsoft Azure 仮想マシンのマイクロソフト サーバー ソフトウェア サポート](https://support.microsoft.com/kb/2721672)  
* [SQL Server データベース ミラーリング、ボリューム シャドウ コピー サービス、および AlwaysOn の使用](../core/sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson.md)  
* [AlwaysOn 可用性グループ (SQL Server) の概要](https://msdn.microsoft.com/library/ff877884.aspx)  
* [データベース ミラーリングまたは AlwaysOn 可用性グループ (SQL Server) のデータベースにまたがるトランザクションのサポート](https://msdn.microsoft.com/library/ms366279.aspx)  
* [SQL Server Windows Server 2012 R2 での MSDTC からトランザクションの結果を受信すると、reenlist を呼び出すことができません。](https://support.microsoft.com/kb/3090973)  
* [BizTalk Server データベースのバックアップと復元](../core/backing-up-and-restoring-biztalk-server-databases.md)  
* [BizTalk Server データベースを移動する方法](../core/how-to-move-the-biztalk-server-databases.md)  
* [データベースを復元する方法](../core/how-to-restore-your-databases.md)   
* [マルチ サブネット可用性グループ内の接続のタイムアウト](https://blogs.msdn.microsoft.com/alwaysonpro/2014/06/03/connection-timeouts-in-multi-subnet-availability-group/)  
 
## <a name="known-limitations"></a>既知の制限事項 

これらの制限は BizTalk Server、SQL Server AlwaysOn 可用性グループ、および Azure の仮想マシンです。 これらの制限は、後で対処を取得しない場合があります。 

* 可用性グループ内では、ログイン、SQL エージェント ジョブ、SQL DB のメール プロファイル、およびアカウントが管理されていません。 これには、プライマリ レプリカに対して実行するかどうかを確認するジョブを手動で変更が必要です。 
* SQL Server Analysis Services と SQL Server Integration Services は、可用性グループに参加しません。 SQL Server からのこのサポートがない場合は、これらの Azure Virtual Machines での HA ソリューションはありません。 BizTalk Server の BAM 機能では、これらのサービスに依存します。 
* SQL Server 2016 SP2 では、前に、可用性グループは、同じ SQL インスタンス上のデータベース間で MSDTC をサポートされていません。 そのため、最小 8 SQL インスタンスでは、BizTalk を構成する必要があります。 

  SQL Server 2016 SP2 以降では*と*BizTalk Server 2016 [CU5](https://support.microsoft.com/help/2555976/service-pack-and-cumulative-update-list-for-biztalk-server)、BizTalk データベースが同じ SQL Server インスタンスを使用できます。 

* MSDTC に対処するには、2 つのサーバーをホストしている 4 つの SQL インスタンスごとの最小値を使用して可用性グループ、BizTalk データベースの制限を構成できます。 使用することも[Azure Load Balancer の複数の IP アドレス](https://docs.microsoft.com/azure/load-balancer/load-balancer-multivip-overview)します。 1 台のサーバー上のポート 1433 で 4 つの既定の SQL インスタンスを使用する場合は、4 つの IP アドレスが必要です。 1 つの IP アドレスに制限されている場合、同じサーバー上の複数の SQL インスタンスをホストする SQL インスタンスごとにカスタム ポートを使用することを確認になります。 

  SQL Server 2016 SP2 以降では*と*BizTalk Server 2016 [CU5](https://support.microsoft.com/help/2555976/service-pack-and-cumulative-update-list-for-biztalk-server)、BizTalk Server データベースが同じ SQL Server インスタンスを使用できます。 

* BizTalk Server では、読み取り専用ルーティングを使用できません。 
* BizTalk Server が設定されていない、`MultiSubnetFailover`接続プロパティです。 
* ログ配布を使用して BizTalk バックアップ ジョブは、可用性グループの設定、バックアップの設定に関係なく、プライマリ レプリカを常に対象とします。 
* SQL Server 2016 Standard は、各 SQL AlwaysOn 可用性グループの 1 つのデータベースを 1 つだけをサポートします。 BizTalk では、多数のデータベースを使用するための SQL Server Enterprise edition は通常お勧めします。
* Azure Vm を使用する場合、専用に使用する推奨が、MSDTC の固定 TCP/IP ポート。 以前のオペレーティング システムで通常使用される、RPC ポートの範囲を制限することは、固定 TCP/IP ポートを使用する場合ファイアウォールを簡素化し、ロード バランサー規則をそのします。 下の既知のポートとの競合を避けるためより高い固定ポートを使用してを検討してください (など > 20000)。 [1 つのポートのサポートの DTC を構成する](https://msdn.microsoft.com/library/windows/desktop/dd573191(v=vs.85).aspx)について説明します、`ServerTcpPort`レジストリ キー。 MSDTC の固定ポートに加え、メインの RPC ポート 135 も使用されます。 
