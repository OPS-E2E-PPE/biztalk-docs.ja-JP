---
title: BizTalk Server 2016 へのアップグレード |Microsoft Docs
ms.custom: ''
ms.prod: biztalk-server
ms.date: 06/08/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 975ec82b-ed27-4545-8e4a-0e567507c9ba
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a545f03f480a2cade3d609feb085449ab9a2f726
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401439"
---
# <a name="upgrade-to-biztalk-server-2016"></a>BizTalk Server 2016 へのアップグレード
アップグレードする[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]から[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]、または BizTalk Server 2013。

このトピックの概要を示します、[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]プロセス、キー情報、および BizTalk Server 2013 R2 または BizTalk Server 2013 からアップグレードするための手順をアップグレードします。


## <a name="upgrade-overview"></a>アップグレードの概要

- アップグレードする前に、このドキュメント全体を読み取る。 BizTalk Server では、企業に内部および外部、多くのさまざまなコンポーネントを接続します。 複数のサーバーを含むほとんどの実際の展開シナリオをさらに多く拡張し、最終的に、物理および仮想の両方のコンピューターのクラスター。

- ない 2 つの BizTalk Server の展開は、同じです。 アップグレードする前に、自社のニーズに関する情報を収集し、IT プロフェッショナル、システム管理者、および BizTalk Server を使用する開発者と共に展開のスコープについて説明します。 このアップグレードのガイドを調査して、企業の特定のニーズを判断で、独自のデプロイ ロードマップを作成します。

- BizTalk Server の展開を確認する、BizTalk Server ベスト プラクティス アナライザー (BPA) を使用し、ベスト プラクティスの一覧を生成します。 BPA は、読み取って報告するだけで構成レベルの検証を実行し、収集したデータを使用して、ベスト プラクティスに従っているかどうかを判断します。

### <a name="planning-your-upgrade"></a>アップグレードの計画

アップグレード プロセスの概要を次に示します。 各手順の一覧は、示されている順序で実行する必要があります。

- オペレーティング システムのアップグレード パス
- Microsoft SQL Server® アップグレード パス
- Windows® SharePoint® Services アップグレード
- Visual Studio によって並列インストールします。
- Microsoft Office 2016/2013 を並列インストールします。

### <a name="supported-upgrade-paths"></a>サポートされるアップグレード パス
次の表は、サポートされるオペレーティング システムをアップグレードできる[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]します。 「はい」そのオペレーティング システムで実行されている BizTalk Server のバージョンをアップグレードすることを意味します。 "No"を意味そのオペレーティング システムで実行されている BizTalk Server のバージョンをアップグレードすることはできません。 "No"のときに、BizTalk 環境がサポートされているオペレーティング システムで再作成する必要があります。  [BizTalk Server 2016 のハードウェアおよびソフトウェア](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)サポートされるオペレーティング システムを一覧表示されます。

| オペレーティング システム | BizTalk Server 2013 R2 |BizTalk Server 2013 |
| --- | --- | --- |
| Windows Server 2012 R2 | はい | いいえ |
| Windows Server 2012 | いいえ | いいえ |
| Windows 8.1 | はい | いいえ |
| Windows 8 | いいえ | いいえ
| Windows 7 SP1 | いいえ | いいえ |

次の表に、サポートされている SQL Server のバージョンにアップグレードできる[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]します。 SQL Server では、BizTalk Server で使用されるデータベースをホストします。 「はい」を SQL Server のバージョンを使用して BizTalk Server をアップグレードできることを意味します。 "No"を意味する SQL Server のバージョンを使用して BizTalk Server をアップグレードすることはできません。 "No"のときに、BizTalk 環境がサポートされている SQL Server のバージョンで再作成する必要があります。 [BizTalk Server 2016 のハードウェアおよびソフトウェア](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)サポートされている SQL Server のバージョンを一覧表示されます。 

> [!TIP]
> SQL Server バージョンはサポートされていません、または、次の一覧に含まれていない場合は、SQL Server のアップグレード マニュアルを確認します。 SQL のアップグレードでは、BizTalk がサポートしているより多くのバージョンについて説明します。 たとえば、SQL Server 2008 を使用している場合は、SQL Server 2016 をアップグレードすることができます。 アップグレードすることができますし、[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]します。 [SQL Server 2016 にアップグレード](https://msdn.microsoft.com/library/bb677622.aspx)と[SQL Server 2014 にアップグレード](https://msdn.microsoft.com/library/bb677622(v=sql.120).aspx)アップグレードできる SQL Server のバージョンを一覧表示します。

| SQL Server | BizTalk Server 2013 R2 |BizTalk Server 2013 |
| --- | --- | --- |
| SQL Server 2014 | はい | いいえ |
| SQL Server 2012 SP1| いいえ | いいえ |
| SQL Server 2012 | いいえ | いいえ |
| SQL Server 2008 R2 SP1 | いいえ | いいえ |


次の表からサポートされているエディションのアップグレード パス[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]します。 「可」は意味、  [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] /2013 エディション エディションにアップグレードできます。 "No"の意味、  [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] /2013年のエディションをエディションにアップグレードできません。 "No"のときに、BizTalk 環境を再作成する必要があります。

| BizTalk Server 2013 R2/2013 | BizTalk Server 2016 Evaluation Edition | BizTalk Server 2016 Branch エディション | BizTalk Server 2016 Developer Edition | BizTalk Server 2016 Standard Edition | BizTalk Server 2016 Enterprise Edition |
| --- | --- | --- | --- | --- | --- |
| Evaluation | いいえ | いいえ | いいえ | いいえ | はい | 
| 分岐 | いいえ | はい | いいえ | いいえ | はい | 
| Developer | いいえ | いいえ | はい | いいえ | はい | 
| Standard | いいえ | いいえ | いいえ | はい | はい | 
| Enterprise | いいえ | いいえ | いいえ | いいえ | はい | 

## <a name="before-the-upgrade--what-you-need-to-know"></a>アップグレードする前に何を知っておくべき


- **アクセス許可**:アップグレードを実行するユーザーは、次のユーザー グループのメンバーであるか、同等のアクセス許可がある必要があります。

    - ローカル コンピューターの administrators グループ
    - SQL Server 上の SQL Server システム管理者グループ
    - BizTalk Server 管理者グループ
    - シングル サインオン (SSO) 管理者グループ

- **SSO**:アップグレード中には、シングル サインオン マスター シークレット サーバーと SSO データベースをホストする SQL Server を実行する必要があります。

- **ネットワーク サービス アカウント**:Windir%\temp への書き込みアクセスが必要です。

- **証明書**:Windows 証明書ストアをバックアップします。  

    [Windows 7 および Windows Server 2008 R2:証明書をインポートします。](http://technet.microsoft.com/library/cc754489.aspx)  
    [Windows 7 および Windows Server 2008 R2:証明書をエクスポートします。](http://technet.microsoft.com/library/cc730988.aspx)  

- **DTC**:Microsoft 分散トランザクション コーディネーター (MSDTC) を有効にする ([、環境を最適化する構成後の手順](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md))、インバウンド/アウト バウンド DTC 規則を有効にします。

    1. サーバー マネージャーで、選択**ツール**、開き**セキュリティが強化された Windows ファイアウォール**します。
    2. 選択**受信規則**します。
    3. **受信の規則**、右クリックして**分散トランザクション コーディネーター** * (必要に応じて)、し**規則の有効化**します。
    4.  セキュリティが強化された Windows ファイアウォールで次のように選択します。**送信の規則**します。
    5.  **送信の規則**、右クリックして**分散トランザクション コーディネーター** * (必要に応じて)、し**規則の有効化**します。

- **SharePoint**:SharePoint サービスに接続するクライアント側オブジェクト モデル (CSOM) を使用します。 サーバー側オブジェクト モデル (SSOM) (web サービス) が削除されて[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]します。

    CSOM をサポートしていない SharePoint のバージョンを使用している場合は、サポートされている SharePoint バージョンにアップグレードすることができます。

    [SharePoint 2016 へのアップグレード](https://technet.microsoft.com/library/cc303420(v=office.16).aspx)  
    [SharePoint 2013 へのアップグレード](https://technet.microsoft.com/library/cc303420(v=office.15).aspx)

- **.NET framework**:.NET Framework 4.5 と .NET Framework 4.6 の間のサイド バイ サイドでインストールの概念はありません。 .NET Framework 4.6 のバイナリは、.NET Framework 4.5 のバイナリを上書きします。 .NET framework 4.6 は、[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]要件ではサポートされていません (とインストールされていない必要があります) 以前のバージョンの BizTalk Server でします。

- **Office 2016 と Office 2013**:[インストールし、異なるバージョンの Office を使用して、](https://support.office.com/article/Install-and-use-different-versions-of-Office-on-the-same-PC-6EBB44CE-18A3-43F9-A187-B78C513788BF)同じコンピューターにします。 また、チェック アウト[これら問題](https://support.microsoft.com/kb/3094527)します。

- **BizTalkServerApplication ホスト**:アップグレードでは、既定のホストが存在する必要があります。 場所が削除された場合は、SQL アダプターに関連付けられている既定のホスト インスタンスの送信ポートと受信には、アップグレードする前に、SQL アダプターに既定のホストを関連付けます。 アップグレードが完了した後は、一覧から既定のホストを削除できます。

- **カスタム バインド**:アップグレードした後は、以前のバージョンの .NET Framework で構築されたユーザー定義のカスタム バインドを使用できません。 カスタム バインドを使用するには、.NET Framework 4.6 machine.config ファイルにカスタム バインドを手動で追加します。

- **構成ファイル**:BizTalk Server 2013 R2/2013 のすべてのカスタム構成ファイルをバックアップします。 BizTalk Server は、変更内容の移行をサポートしているだけで、`btsntsvc.exe.config`と`bm.exe.config`ファイル。



### <a name="bam-alerts"></a>BAM 警告

BAM 警告を使用する SQL Server Database Mail が必要です。 コード型の SQL Server Notification Services で既存の BAM 警告の定義を使用する SQL のバージョンからアップグレードは場合、BAM 警告の定義をバックアップにアップグレードした後に展開し、ことができます。 BM.exe コマンド ライン ツールを使用して (`\Program Files (x86)\Microsoft BizTalk Server <your version>\Tracking`)。 特定の手順は次のとおりです。

1. コマンド プロンプトを開きに移動`\Program Files (x86)\Microsoft BizTalk Server <your version>\Tracking`します。
2. コマンド プロンプトで、定義ファイルを作成します。 `bm.exe get-defxml -FileName:YourBAMDefinition.xml`
3. [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013 構成では、BAM 警告の構成を解除します。
4. SQL Server 2014 SP1 または SQL Server 2016 にアップグレードします。
5. SQL Server データベース メールを構成します。
6. アップグレード[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]します。
7. [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]構成では、BAM 警告を構成します。
8. コマンド プロンプトで保存した定義ファイルを展開します。 `bm.exe update-all -DefinitionFile:YourBAMDefinition.xml`

> [!IMPORTANT]
> 以下の手順を順番にまたは定義ファイルを作成場合、BizTalk Server のアップグレード後に、定義ファイルを再作成する必要があります。
> 
> BM.exe のヘルプを表示するには、入力:`bm.exe help`します。


### <a name="bam"></a>BAM 

- **BAM DTS パッケージ**:すべての BAM データ変換サービス (DTS) パッケージを停止します。 それ以外の場合、データが失われる可能性があります。 またはオンライン分析処理 (OLAP) キューブが破損する可能性があります。 

- **ディスク領域**:空きディスク領域は、既存の BAM データベースのサイズ以上である必要があります。

- **リアルタイム集計**:現在のバージョンの BizTalk Server で BAM リアルタイム集計を使用している SQL Server をアップグレードして場合、インストールするか、SQL Server Enterprise Edition にアップグレードします。 それ以外の場合、アップグレードは失敗します。

- **maxTimeout 値**:サイズの大きな BAM データベースがある場合は、更新、`maxTimeout`値を machine.config ファイルで分散トランザクションの場合。  

    ```
    <system.transactions>
       <machineSettings maxTimeout="23:59:59" />
    </system.transactions>
    ```

- **追跡プロファイル エディター (TPE) で有効になっている BAM 追跡**:アップグレードした後、以前に展開した追跡プロファイルはアップグレードされます。ただし、それに対応するインターセプター構成はアップグレードされません。 新しい受信済み BAM メッセージは、BizTalk Server 2013 R2/2013 参照可能性があります。 対応するインターセプター構成をアップグレードするには、追跡プロファイル エディターを使用して、アクティビティのプロファイルを取得するし、プロファイルを再適用します。

- **LiveData ブック**:アップグレード後に BizTalk Server 2013 R2/2013 で BAM を使用する場合、ライブ データ ブックを手動で再生成する必要があります。 LiveData ブックを再生成します。

  1. 次のコマンドを実行して、BAM 定義を取得します。  
     `BM get-defxml MyDef.xml`
  2. Microsoft Office Excel を開き、BAM アドインを選択し、ピボット テーブル レポートを再作成するには。インポート、 *MyDef.xml*ファイルの作成手順 (1) と、ピボット テーブル レポートを再作成します。 新しい BAM ブックを保存*MyNewBook.xls*します。
  3. ピボット テーブル名を検索して、ピボット テーブル レポートの名前を変更*MyDef.xml* `<Caption>`で、`<BAMDefinition>\<Extension>\<OWC>\<PivotTableView>\<PivotTable>\<PivotView>\<Label>`パス。 これらの名前を使用して、ピボット テーブル レポートでの名前を変更する*MyNewBook.xls*します。
  4. 次のコマンドを実行して、LiveData ブックを再生成します。  
     `BM regenerate-livedataworkbook MyNewBook.xls`

     > [!NOTE]
     > 再生成された LiveData ブックには、元の LiveData ブックである Excel アイテム (チャートなど) が再作成しません。 成果物を手動で再作成します。


### <a name="enterprise-single-sign-on-esso"></a>エンタープライズ シングル サインオン (ESSO)

|                            シナリオ                            |                                                                                                                                                                                                                                                                                                                                          詳細情報                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| エンタープライズ シングル サインオンの以前のバージョンからアップグレードします。 | BizTalk Server には、更新されたバージョン エンタープライズ シングル サインオン (ESSO) にはが含まれています。 以前のバージョンの BizTalk コンピューターでこのリリースをインストールする場合、ESSO はセットアップ中に自動的に更新します。 アップグレードする前に、次の手順を実行することをお勧めします。 <br/><br/> 1.シングル サインオン データベース (SSODB) の現在のバージョンは安全な場所にバックアップしていることを確認します。 <br/>2.現在のマスター シークレット キーは安全な場所にバックアップしていることを確認します。<br/>3.マスター シークレットには、パスワードを認識します。<br/><br/>BizTalk グループ内のすべてのサーバーを同じリリースにアップグレードします。 この要件は、スタンドアロンのマスター シークレット サーバーにも適用されます。 |
|  エンタープライズ シングル サインオン スタンドアロン セットアップを使用したアップグレード  |             次の手順を使用して、スタンドアロンのエンタープライズ シングル サインオンを専用のマスター シークレット サーバーなどにインストールされているコンピューターでアップグレードを実行します。<br/><br/>1.現在のマスター シークレット キーは安全な場所にバックアップしていることを確認します。<br/>2.現在のバージョンの SSODB が安全な場所にバックアップしていることを確認します。<br/>3.実行、ESSO **Setup.exe**から、[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]インストール メディア。 既定のインストール フォルダーは`\Platform\SSO`します。<br/>4.**自動実行**ダイアログ ボックスで、 **Microsoft エンタープライズ シングル サインオン**します。<br/>5.概要 ダイアログ ボックスで、次のように選択します。**アップグレード**します。              |

### <a name="multicomputer-environment"></a>複数コンピューター環境
複数コンピューター環境では、SSO マスター シークレット サーバー コンピューターをアップグレードします。 次に、他の BizTalk Server コンピューターをアップグレードします。 グループ内の BizTalk コンピューターを同時にアップグレードすることはサポートされていません。 次の順序で一度に 1 台のコンピューターをアップグレードします。

1. シングル サインオン マスター シークレット サーバー
2. BizTalk Server を実行しているランタイム コンピューター
3. 管理ツールと監視コンピューター
4. 開発と BizTalk Server を実行している他のコンピューター

**その他**  
設定ダッシュ ボードを使用して、パフォーマンスの最適化のための BizTalk Server 設定を幅広く調整できます。 BizTalk グループ、BizTalk ホスト、および BizTalk ホスト インスタンスの設定を変更することもできます。 参照してください[設定ダッシュ ボードを使用して、BizTalk Server のパフォーマンス チューニング](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)します。

### <a name="general-information"></a>一般的な情報

- **アカウント名**:可能な限り、既定のアカウント名を使用します。 BizTalk Server のセットアップ プログラムでは、既定のアカウントを使用するインストール済みコンポーネントが自動的に構成されます。 Active Directory フォレストに複数の BizTalk Server グループがある場合は、競合を回避するために、アカウント名を変更します。 BizTalk Server のサポートのみ`<NetBIOS domain name>\<user>`形式のサービス アカウントおよび Windows グループの名前します。

- **アカウント名と BAM 管理 Web サービス**:BAM 管理 Web サービス ユーザーは、BizTalk Server は、ビルトイン アカウントまたはパスワードなしのアカウントはサポートしていません。 

  このようなアカウントを使用して BizTalk Server の構成が成功するも、BAM 管理 Web サービスは失敗します。 

  BAM アプリケーション プールのようなアカウントの使用がサポートされています。

- **BizTalk アセンブリ ビューアー**は 64 ビットのオペレーティング システムでサポートされていません。

- **インストールし、アンインストール**:BizTalk Server をアンインストールする場合は、BizTalk Server データベースを手動で削除します。 開発者またはエバリュエーターとして BizTalk Server をインストールする場合は、仮想マシンにインストールを検討してください。 これによりを再インストールする必要がある場合は簡単にロールバックする事前設定されたチェックポイント アンインストール プロセスを経由する必要はありません。

- **32 ビットおよび 64 ビット コンピューター**:Windows の 32 ビットまたは 64 ビット Windows に BizTalk Server をインストールする場合は、大きな違いにはありません。 このドキュメントでは、32 ビットおよび 64 ビットの両方のインストールについて説明します。 それらの相違点が記載されています。

- **ワークグループ**:インストールして、1 台のコンピューター上のワークグループ環境での BizTalk Server の構成がサポートされています。 このシナリオで SQL Server と BizTalk Server の機能とコンポーネントの両方がインストールされているし、同じコンピューター上で構成します。

- **ターミナル サーバー**:BizTalk Server のインストール アプリケーション モードで実行されているターミナル サーバーの使用はサポートされていません。 参照してください[KB 832027](https://support.microsoft.com/kb/832027)します。

- **サイレント アップグレード**はサポートされていません。

- **サポートされていないアプリケーション**:BizTalk Server は、PAM Api、ストアド プロシージャ、またはデータベースに直接アクセスなどのサポートされていない Api に基づいて構築されたカスタム アプリケーションをサポートしていません。 運用環境をアップグレードする前に、少なくとも 1 つのテスト アップグレードを実行します。

- **SQL Server インスタンス**:プラットフォームをアップグレードする前に、SQL Server インスタンスをアップグレードすることをお勧めします。

## <a name="prepare-your-computer-for-upgrade"></a>アップグレード コンピューターを準備します。

|                 タスク                  |                                                                                                                                                                                                                                        Info                                                                                                                                                                                                                                         |
|---------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   重要な Windows 更新プログラムをインストールします。    |                                                                                                                                                                                                [プログラム] メニューから Windows 更新プログラムを選択します。 コンピューターを再起動する必要があります。                                                                                                                                                                                                 |
|      BAM 警告の定義を保存します。       |                                    現在、SQL Server Notification Services で既存の BAM 警告の定義を使用する場合にのみ適用されます。 BM.exe を使用して定義ファイルを作成しで BAM 警告の構成を解除、 [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013 構成します。<br/><br/>**アップグレードする前に**(このトピック) で特定の手順を示します。<br/><br/>それ以外の場合、アップグレードした後は、BAM 警告の定義を再作成します。                                    |
|          SQL Server をアップグレードする           |                                         サポートされている SQL Server のバージョンにアップグレードします。 参照トピック<br/><br/>[BizTalk Server 2016 のハードウェア/ソフトウェア要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)<br/>[SQL Server 2016 へのアップグレード](https://msdn.microsoft.com/library/bb677622.aspx)<br/>[SQL Server 2014 へのアップグレード](https://msdn.microsoft.com/library/bb677622(v=sql.120).aspx)                                          |
|    SQL Server クライアント ツールをアップグレードします。    |                                                                                                                                                複数コンピューター環境には、別のコンピューターに、管理ツールをインストールすることがあります。 SQL Server 管理のクライアント ツール、管理ツールを含むをアップグレードします。                                                                                                                                                |
|         Visual Studio のインストール         |                         参照してください[BizTalk Server 2016 のハードウェアおよびソフトウェア](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)サポートされているバージョン。 異なるバージョンの Visual Studio では、並列でのインストールをすることができます。 参照してください[Visual Studio 2015](https://msdn.microsoft.com/library/ms246609(v=vs.140).aspx)と[Visual Studio 2013](https://msdn.microsoft.com/library/ms246609(v=vs.120).aspx)します。                         |
|            Office をインストールします。             |                                     参照してください[をインストールし、異なるバージョンの Office を使用して、](https://support.office.com/article/Install-and-use-different-versions-of-Office-on-the-same-PC-6EBB44CE-18A3-43F9-A187-B78C513788BF)同じコンピューターにします。 [BizTalk Server 2016 のハードウェアおよびソフトウェア](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)サポートされている Office のバージョンを一覧表示します。                                     |
| BizTalk と Windows サービスを停止します。 |                                                                                                      BizTalk Service BizTalk Group: *< Application_Name >*<br/>-BizTalk ベース EDI サービス<br/>-ルール エンジン更新サービス<br/>-World Wide Web Publishing サービス<br/><br/>**注**<br/>BizTalk Server アクセラレータがインストールされている場合は、HL7 ログ サービスを停止します。                                                                                                      |
|         データベースをバックアップします。         | マスター<br/>-MSDB<br/>-BAMArchive<br/>-BAMPrimaryImport<br/>-BAMStarSchema<br/>-BizTalkDTADb<br/>-BizTalkEDIDb<br/>-BizTalkHwsDb<br/>-BizTalkMgmtDb<br/>-BizTalkMsgBoxDb<br/>-BizTalkRuleEngineDb<br/>-TPM<br/>-BizTalkAnalysisDb<br/>-BAMAnalysis<br/><br/>[SQL Server 2014:バックアップの概要](https://technet.microsoft.com/library/ms175477(v=sql.120).aspx)<br/>[SQL Server 2012:バックアップの概要](https://technet.microsoft.com/library/ms175477(v=sql.110).aspx) |
|  SQL Server データベース メールを構成します。   |                                                                                                                      SQL Server Notification Services で BAM 警告の定義を使用する場合にのみ適用されます。<br/><br/>**アップグレードする前に**(このトピック) で特定の手順を示します。<br/><br/>それ以外の場合、アップグレードした後は、BAM 警告の定義を再作成します。                                                                                                                       |

## <a name="do-the-upgrade"></a>アップグレードを実行します。

> [!IMPORTANT]
> SQL Server のインストール、セットアップはシステム管理者の権限をログオン アカウントに付与されます。 システム管理者の権限は、BizTalk Server のインストールにも必要です。 次のいずれかの操作を行います。
> 
> - SQL Server をインストールしたときに使用した同じアカウントを使用します。  
> **OR**  
> - 現在のログオン アカウントにシステム管理者の権限があることを確認します。

### <a name="upgrade-steps"></a>アップグレード手順

1. 開いているプログラムを閉じます。
2. 実行**Setup.exe**インストール メディアから。
3. スタートでは、次のように選択します。 **Microsoft BizTalk Server のインストール**します。
4. **顧客情報**ユーザー名、組織、およびプロダクト キーを入力します。 **[次へ]** を選択します。
5. ライセンス条項に同意し、選択**次**します。
6. カスタマー エクスペリエンス向上プログラムには、する基本設定を入力します。 参照してください**付録 A** (このトピックでは) の詳細についてはします。
7. **コンポーネントのインストール**で、使用可能なコンポーネントを確認し、**次**します。
8. お使いのコンピューターには、前提条件が不足しているが、再頒布可能パッケージの前提条件がインストールできます。 次のいずれかを実行できます。

    - Select では、web サイトから、再頒布可能コンポーネントを自動的にインストールします。  

      スイッチまたは  

    - 選択を使用、CAB ファイルから CAB ファイルをダウンロードした場合の再頒布可能パッケージのコンポーネントが自動的にインストールします。 CAB ファイルの場所を参照して選択します。

9. **概要**、アップグレード可能なコンポーネントを確認します。
10. 選択**アップグレード**を開始します。
11. 省略可能:選択 **(推奨) 更新プログラムを確認するときに、Microsoft Update を使用**します。
12. **アップグレードは完了しました**、オフに**aunch BizTalk Server 構成**チェック ボックスをオンし、**完了**します。

**その他**  
多くは、BizTalk Server のアップグレード中に発生して、処理中の実行でエラーが発生するケースも少なくありません。 ただし、準備している場合はエラーのほとんどが簡単に修正します。 読み取りをお勧め、**付録 B** (このトピックでは) のアップグレードのエラーを回避する方法と、いずれかが発生した場合の対処に関するヒント。

アップグレード プロセスは、以前のバージョンの BizTalk Server の一部であった機能のみをアップグレードします。 新機能は、アップグレード中にインストールされていません。 これらの機能をインストールするには、アップグレード後にセットアップを再実行、**変更**をインストールする機能を選択します。 インストールした後では、構成を使用して、 **BizTalk Server 構成マネージャー**します。

アップグレードが成功したかどうかことを確認するには、開く**プログラムと機能**を探して[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]します。 記載されている場合は、セットアップが成功しました。

## <a name="post-upgrade"></a>アップグレード後
ロールバックできません [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] /2013。

- **BAM 警告の定義 XML ファイルを作成した場合**:[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]構成では、BAM 警告を構成します。 次に、保存した定義をデプロイします。

    **アップグレードする前に**(このトピック) で特定の手順を示します。 それ以外の場合、アップグレードした後は、BAM 警告の定義を再作成します。

- **MQSAgent のインストール**:MQSAgent.dll ファイルは、リモートの WebSphere MQ Server にインストールする場合は、MQ エージェントからの新しいバージョンをインストール[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]リモートの WebSphere MQ Server 上。

- **MSMQ の開始**:MSMQ アダプターを使用する場合は、メッセージ キュー サービスを起動します。

- **カスタム EXE および BRE**:BizTalk Server 2010 のビジネス ルール エンジン アセンブリを参照するカスタム マネージ実行可能ファイルがあれば、.NET Framework 2.0 でプロセスを実行するアプリケーション構成ファイルに、次を追加します。

    ```
    <?xml version="1.0" encoding="Windows-1252"?>
    <configuration> 
     <startup>
      <supportedRuntime version="v2.0.50727" />
     </startup>   
    </configuration>
    ```

- **SQL エージェント ジョブ**:次の SQL Server エージェント ジョブを再構成するには。

    -   DTA Purge and Archive (BizTalkDTADb):参照してください[構成 DTA Purge and Archive ジョブをする方法](../core/how-to-configure-the-dta-purge-and-archive-job.md)
    -   BizTalk Server (BizTalkMgmtDb) をバックアップしてください。参照してください[バックアップ BizTalk Server ジョブを構成する方法](../core/how-to-configure-the-backup-biztalk-server-job.md)

- **アプリケーションの再起動**:アップグレードされたデプロイされたすべてのアプリケーションを再起動します。

- **BAM ポータル エラー**:BAM ポータルを開くと、次のエラー メッセージが表示される可能性があります。 

    `The server encountered a critical failure while trying to access the list of Views. The Business Management Web Service requires Administrator's attention.` 

    このエラーは、.NET Framework 2.0 を実行しているアプリケーションで使用される web サイトに BAM ポータルが構成されている場合に発生することができます。 このシナリオでは、新しい web サイトで、BAM ポータルをホストします。 Web サイトを追加するを参照してください。 [Web サイトを作成する](http://go.microsoft.com/fwlink/p/?LinkID=196470)します。 Web サイトを作成した後、BAM ポータルを再構成します。

    1. **[BizTalk Server 構成]** を開きます。
    2. 選択**機能の構成解除**します。 **機能の構成解除**を選択、 **BAM ポータル**チェック ボックスをオンし、選択**OK**。
    3. 新しい web サイトを選択して BAM ポータルを再構成、 **BAM ポータル Web サイト**一覧。

- **BizTalk 2016 Accelerator for SWIFT**:BizTalk Server のアップグレード プロセスを編集した更新しません*BREDeployment.exe.config*ファイル。 内のパスを手動で変更、 *BREDeployment.exe.config*にあるファイル、`\Program Files\Microsoft BizTalk 2016 Accelerator for SWIFT\SDK\Tools`フォルダー。

    また、A4SWIFT Web サービスと Message Pack 構成は失われます。 BizTalk Server をアップグレードした後、これらを再構成します。

## <a name="appendix-a-customer-experience-improvement-program"></a>付録 A: カスタマー エクスペリエンス向上プログラム
BizTalk Server のカスタマー エクスペリエンス向上プログラムの一環として、BizTalk Server の機能の使用状況に関する、マイクロソフトに有益なフィードバックを提供できます。 収集されたデータは匿名でとを識別するためには使用できません。 Microsoft は、このプログラムの一部としての機能使用状況の統計を収集します。

このプログラムに参加して、BizTalk Server のさまざまな機能のパフォーマンスと信頼性向上できます。 このプログラムとプライバシー ポリシーの詳細については、次を参照してください。 [Microsoft BizTalk Server CEIP プライバシー ポリシー](http://go.microsoft.com/fwlink/p/?LinkId=188553)します。

## <a name="appendix-b-known-issues"></a>付録 B:既知の問題

- **管理用コンピューターで BAM 警告の構成**:別のコンピューターにインストールされている、管理、ランタイム、および SQL Server コンポーネントを複数コンピューター環境があります。 BAM ツールまたは BAM 警告を使用する場合、次の問題が発生することができます。

    **問題**:BizTalk 管理用コンピューターで BAM ツールを構成する場合は、次のエラーが発生します。

    `Service BAMAlerts was not found on computer ‘.’.The specified service does not exist as an installed service.`

    **問題**:ランタイム コンピューターから BAM アクティビティ定義を展開するときに、次のエラーが発生します。

    `A network-related or instance-specific error occurred while establishing a connection to SQL Server. The server was not found or was not accessible. Verify that the instance name is correct and that SQL Server is configured to allow remote connections. (provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server) (.Net SqlClient Data Provider)`

    これは、ランタイム コンピューターで BAM 警告が構成されている場合に発生します。 を解決するには、BizTalk 管理コンソールと同じコンピューターで BAM 警告を構成します。 ランタイム コンピューターで BAM 警告を構成しないでください。

- **失敗したアップグレードからの復旧**:アップグレードの失敗は、アップグレード中にいつでも発生します。 アップグレードの失敗から復旧する方法は、障害が発生した各フェーズ中にどの時点から決定されます。

  - 前提条件をインストールするときに、アップグレードに失敗セットアップはさらに、前提条件のインストールを停止して、エラーのメッセージが返されます。 問題を修正し、セットアップを再実行できます。

  - 既存の BizTalk Server のバージョンから機能を削除するか、新しいバージョンをインストール、データベースをアップグレードするときに、アップグレードが失敗したセットアップはさらに、インストールを停止して、エラーのメッセージが返されます。 すべての変更はロールバックされます。 BizTalk Server データベースに加えられた変更はロールバックできません。

      以前の BizTalk Server インストールのコンポーネントはアップグレード中に削除する場合は、BizTalk Server コンポーネントがない状態で、コンピューターが残る可能性が。 以前のインストール機能の構成情報を保持することがあります。 およびアップグレード プロセスが失敗した場所に応じて、BizTalk Server データベースがアップグレードされました。 データベース セットアップをもう一度実行する前に、前のバックアップを復元する必要がある場合があります。

  - BizTalk Server の機能を再構成する際に、アップグレードに失敗した場合、セットアップは完了のレベルでメッセージを返します。 構成のアップグレードでは、障害が発生したり、部分的に成功すると、アップグレードを完了する BizTalk Server 構成を実行します。

    アップグレードに引き続き失敗する、以前のバージョンの BizTalk Server に戻す必要がある場合は、バックアップしたデータベースの復元し、BizTalk Server の以前のバージョンを再インストールする必要があります。

- **同じバージョンを使用して**:BizTalk アプリケーション グループでは、コンピューターを異なるバージョンの BizTalk Server を実行することはできません。 たとえば、BizTalk 管理コンソールで、異なるバージョンの BizTalk Server で実行されている受信場所に 1 つのバージョンの BizTalk Server で実行されている送信ポートをバインドできません。 

- **SSO サービスを再起動**:以前のバージョンの Visual Studio または .NET Framework 4.5 をコンピューターにインストールがあれば、以前のバージョンの BizTalk Server で SSO サービスは稼働を停止します。 この問題を解決するには、実行、 `regasm SSOSQL.dll` Visual Studio コマンド プロンプトからコマンド。 このコマンドは、SSO サービスを再起動します。

    > [!NOTE]
    > 64 ビット コンピューターでは、regasm コマンドの 32 ビットおよび 64 ビット バージョンを実行します。

- **SOAP を使用できない**:プラットフォームのアップグレード後は、アクセス許可が原因の SOAP メッセージを送信できるようにしないできます。 これを解決するにある Web.config ファイルを編集`C:\inetpub\wwwroot\<SOAPExternalAppName>\`を次のテキスト。

    ```
    <securityPolicy>
    <trustLevel name="Full" policyFile="internal" />
    <trustLevel name="High" policyFile="web_hightrust.config" />
    <trustLevel name="Medium" policyFile="web_mediumtrust.config" />
    <trustLevel name="Low" policyFile="web_lowtrust.config" />
    <trustLevel name="Minimal" policyFile="web_minimaltrust.config"/>
    </securityPolicy>
    <trust level="Full" originUrl="" processRequestInApplicationTrust="true"/>
    ```

    カスタム エラー モードを変更する必要がありますも**リモートのみ**に**オフ**します。

- **証明書ストア**:アップグレードした後は、BizTalk Server 管理コンソールからの受信場所またはと、エラーが発生する送信ポートを開きます。 `Could not open certificate store, the system cannot find the file specified (System).`

    このエラーは、証明書ストアがない場合に発生します。

- **BAM ポータル**:アップグレードした後、64 ビット コンピューターで BAM ポータルにアクセスできません。 考えられる解決策:

  1. ある web.config ファイルのバックアップ コピーを作成する`%BizTalkInstallDir%\BAMPortal\web.config`します。

  2. Bm.exe を使用して、BizTalk Server の Tracking フォルダーに、コマンド プロンプトで、次を実行します。 `bm.exe get-config –FileName:<filepath> -Server:MyServer -Database:MyDB`

     Config XML ファイルからの値を取得*BAMVRoot* (xpath:BAMConfiguration\ GlobalProperty\Name="BAMVRoot").

  3. BAMVRoot の値として表示されているコンピューターで BizTalk Server 構成を開き、BAM ポータルの構成を解除します。

  4. BizTalk Server の構成を開き、BAM ポータルを構成します。

  5. (1) の手順で示した場所から新しい web.config ファイルを開きます。

  6. 次の値を設定して、web.config ファイルのバックアップ コピーを使用して ( `configuration\appSettings`)。

      - key="MainPageContentUrl"
      - key="AlertNotificationOptions"

     > [!NOTE] 
     > 64 ビット コンピューターで、オペレーティング システムをアップグレードした後をお勧め、BAM ポータルを再構成することです。

- **EDI BAM アクティビティの展開**:アップグレードすると、アップグレードが部分的に成功する可能性があります。 これは、(EDI の構成) を含む SQL Server をアップグレードするときに発生します。 EDI BAM アクティビティが正常にアップグレードしていない可能性があります。 この問題を解決するには、管理者資格情報でコマンド プロンプトで次のコマンドを実行して BAM アクティビティを展開します。

    `"<BizTalk Installation Folder>\Tracking\bm.exe" deploy-all -DefinitionFile:"<BizTalk Installation Folder>\AS2ResendActivityDefs.xml" -Server:"<BAM Database Server Name>" -Database:"<BAM Database Name>"`

    `"<BizTalk Installation Folder>\Tracking\bm.exe" update-all -DefinitionFile:"<BizTalk Installation Folder>\Microsoft.BizTalk.Configuration.EdiAS2.UpgradeR2toR3.xml" -Server:"<BAM Database Server Name>" -Database:"<BAM Database Name>"`

    `"<BizTalk Installation Folder>\Tracking\bm.exe" update-all -DefinitionFile:"<BizTalk Installation Folder>\Microsoft.BizTalk.Configuration.Batching.UpgradeR2toR3.xml" -Server:"<BAM Database Server Name>" -Database:"<BAM Database Name>"`

- **クラスター上の SSO エラー**:BizTalk Server ランタイム クラスター環境をアップグレードするときと、次のエラー メッセージが表示可能性があります。

    `SSO Master Secret Server service is not running on <Cluster name>.Please start the service to continue the upgrade.` 

    この問題を解決するには、SSO を更新するには、SSO および BizTalk Server ランタイム クラスターの両方でのサービスをサービスします。

    **SSO クラスター内の SSO サービスを更新する**:

  1. クラスター アドミニストレーターで、**オンライン**クラスター グループをクラスター化されたエンタープライズ SSO サービス リソースが含まれています。 クラスター グループ内のすべてのリソースこれ開始する必要があります。

  2. **オフライン**エンタープライズ SSO サービスのクラスター化されたインスタンス。 次に、返されること**オンライン**します。

  3. **移動**クラスター グループ。 この手順では、2 番目のノードに最初のノードからクラスター化されたエンタープライズ SSO サービス リソースを含むクラスター グループを移動する必要があります。

  4. **オフライン**エンタープライズ SSO サービスのクラスター化されたインスタンス。 次に、返されること**オンライン**します。

     **BizTalk Server ランタイム クラスターで SSO サービスを更新する**:

  5. クラスター アドミニストレーターで、**オンライン**クラスター化された BizTalk Server ランタイム リソースを含むクラスター グループ。 クラスター グループ内のすべてのリソースこれ開始する必要があります。

  6. **オフライン**エンタープライズ SSO サービスのクラスター化されたインスタンス。 次に、返されること**オンライン**します。

  7. **移動**クラスター グループ。 この手順では、2 番目のノードに最初のノードからクラスター化された BizTalk Server ランタイム リソースを含むクラスター グループを移動する必要があります。

  8. **オフライン**エンタープライズ SSO サービスのクラスター化されたインスタンス。 次に、返されること**オンライン**します。
