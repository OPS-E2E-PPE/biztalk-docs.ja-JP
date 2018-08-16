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
ms.openlocfilehash: bbd6debef5517e95295be0b7680244ee433b6e2f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976579"
---
# <a name="upgrade-to-biztalk-server-2016"></a>BizTalk Server 2016 へのアップグレード
[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] または BizTalk Server 2013 から [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] へのアップグレード。

このトピックでは、[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] のアップグレード プロセスの概要と、BizTalk Server 2013 R2 または BizTalk Server 2013 からのアップグレードに関する重要な情報と手順について説明します。


## <a name="upgrade-overview"></a>アップグレードの概要

- アップグレードを開始する前に、このドキュメント全体をお読みください。 BizTalk Server は、企業内外の多種多様なコンポーネントを接続します。 実際の展開のほとんどはさらに規模が大きく、何台ものサーバーが含まれます。最終的には、物理コンピューターと仮想コンピューターの両方で構成されるクラスターへと発展します。

- BizTalk Server の展開に 2 つとして同じものはありません。 アップグレードを開始する前に、自社のニーズに関する情報を収集し、BizTalk Server を使用する IT 担当者、システム管理者、および開発者と共に展開の範囲について話し合います。 このアップグレード ガイドをよくお読みになり、自社の具体的なニーズを判断すれば、最終的に独自の展開のためのロードマップができあがります。

- BizTalk Server の Best Practices Analyzer (BPA) を使用して、BizTalk Server の展開を調査し、ベスト プラクティスの一覧を生成します。 また、読み取って報告するだけの構成レベルの検証を行い、収集したデータを使用してベスト プラクティスに従っているかどうかを判断します。

### <a name="planning-your-upgrade"></a>アップグレードの計画

アップグレード プロセスの大まかな流れを以下に示します。 一覧の各ステップは、表示されている順序で実行する必要があります。

- オペレーティング システムのアップグレード パス
- Microsoft SQL Server® のアップグレード パス
- Windows® SharePoint® Services アップグレード
- Visual Studio のサイド バイ サイド インストール
- Microsoft Office 2016/2013 のサイド バイ サイド インストール

### <a name="supported-upgrade-paths"></a>サポートされるアップグレード パス
次の表は、[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] にアップグレード可能な、サポートされるオペレーティング システムの一覧です。 "可"は、そのオペレーティング システムで実行されている BizTalk Server をアップグレードできることを意味します。 "不可" は、そのオペレーティング システムで実行されている BizTalk Server をアップグレードできないことを意味します。 "不可" の場合、BizTalk 環境をサポートされるオペレーティング システムで再作成する必要があります。  サポートされるオペレーティング システムの一覧については、「[BizTalk Server 2016 のハードウェアとソフトウェアの要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)」をご覧ください。

| オペレーティング システム | BizTalk Server 2013 R2 |BizTalk Server 2013 |
| --- | --- | --- |
| Windows Server 2012 R2 | はい | いいえ |
| Windows Server 2012 | いいえ | いいえ |
| Windows 8.1 | はい | いいえ |
| Windows 8 | いいえ | いいえ
| Windows 7 SP1 | いいえ | いいえ |

次の表は、[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] にアップグレードできる、サポートされる SQL Server のバージョンの一覧です。 SQL Server は、BizTalk Server で使用されるデータベースをホストします。 「可」は、その SQL Server バージョンを使用している BizTalk Server がアップグレードできることを意味しています。 「いえ」は、その SQL Server バージョンを使用している BizTalk Server がアップグレードできないことを意味しています。 「不可」の場合、BizTalk 環境をサポートされる SQL Server バージョンで再作成する必要があります。 サポートされる SQL Server のバージョンの一覧については、「[BizTalk Server 2016 のハードウェアとソフトウェアの要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)」をご覧ください。 

> [!TIP]
> お使いの SQL Server のバージョンがサポートされていない場合、または次の一覧にない場合は、SQL Server のアップグレード マニュアルを確認してください。 SQL のアップグレードでは、BizTalk がサポートするものより多くのバージョンがカバーされています。 たとえば、SQL Server 2008 を使っている場合は、SQL Server 2016 にアップグレードすることができます。 その後、[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] にアップグレードできます。 「[SQL Server 2016 へのアップグレード](https://msdn.microsoft.com/library/bb677622.aspx)」および「[SQL Server 2014 へのアップグレード](https://msdn.microsoft.com/library/bb677622(v=sql.120).aspx)」では、アップグレードできる SQL Server のバージョンの一覧が示されています。

| SQL Server | BizTalk Server 2013 R2 |BizTalk Server 2013 |
| --- | --- | --- |
| SQL Server 2014 | はい | いいえ |
| SQL Server 2012 SP1| いいえ | いいえ |
| SQL Server 2012 | 不可 | いいえ |
| SQL Server 2008 R2 SP1 | いいえ | いいえ |


次の表に示すのは、[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013 から [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] へのサポートされるエディション アップグレード パスです。 "可" は、[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013 のエディションをそのエディションにアップグレードできることを示します。 「不可」は、[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013 のエディションをそのエディションにアップグレードできないことを示します。 「無効」の場合、BizTalk 環境を再作成する必要があります。

| BizTalk Server 2013 R2/2013 | BizTalk Server 2016 Evaluation Edition | BizTalk Server 2016 Branch Edition | BizTalk Server 2016 Developer Edition | BizTalk Server 2016 Standard Edition | BizTalk Server 2016 Enterprise Edition |
| --- | --- | --- | --- | --- | --- |
| Evaluation | いいえ | いいえ | いいえ | いいえ | はい | 
| 分岐 | いいえ | はい | いいえ | いいえ | はい | 
| Developer | いいえ | いいえ | はい | いいえ | はい | 
| Standard | いいえ | いいえ | いいえ | はい | はい | 
| Enterprise | いいえ | いいえ | いいえ | いいえ | はい | 

## <a name="before-the-upgrade--what-you-need-to-know"></a>アップグレードする前に知っておくべきこと


- **権限**: アップグレードを実行するユーザーは、次のユーザー グループに所属しているか、同等の権限を持っている必要があります。

    - ローカル コンピューターの Administrators グループ
    - SQL Server の SQL Server システム管理者グループ
    - BizTalk Server 管理者グループ
    - シングル サインオン (SSO) 管理者グループ

- **SSO**: アップグレード中に、SSO データベースをホストするシングル サインオン マスター シークレット サーバーおよび SQL Server が実行されている必要があります。

- **ネットワーク サービス アカウント**: %windir%\temp への書き込みアクセス権限が必要です。

- **証明書**: Windows 証明書ストアをバックアップします。  

    [Windows 7 および Windows Server 2008 R2: 証明書をインポートする](http://technet.microsoft.com/library/cc754489.aspx)  
    [Windows 7 および Windows Server 2008 R2: 証明書をエクスポートする](http://technet.microsoft.com/library/cc730988.aspx)  

- **DTC**: Microsoft 分散トランザクション コーディネーター (MSDTC) を有効にし (「[環境を最適化するための構成後の手順](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)」)、DTC の受信規則と送信規則を有効にします。

    1. サーバー マネージャーで、**[ツール]** を選択して **[セキュリティが強化された Windows ファイアウォール]** を開きます。
    2. **[受信の規則]** を選択します。
    3. **受信の規則**、右クリックして**分散トランザクション コーディネーター** * (必要に応じて)、し**規則の有効化**します。
    4.  [セキュリティが強化された Windows ファイアウォール] で、**[受信の規則]** を選択します。
    5.  **送信の規則**、右クリックして**分散トランザクション コーディネーター** * (必要に応じて)、し**規則の有効化**します。

- **SharePoint**: SharePoint Services に接続するには、Client Side Object Model (CSOM) を使用します。 Server Side Object Model (SSOM) (Web サービス) は、[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] では削除されました。

    CSOM をサポートしていない SharePoint のバージョンを使用している場合は、サポートされる SharePoint バージョンにアップグレードできる可能性があります。

    [SharePoint 2016 へのアップグレード](https://technet.microsoft.com/library/cc303420(v=office.16).aspx)  
    [SharePoint 2013 へのアップグレード](https://technet.microsoft.com/library/cc303420(v=office.15).aspx)

- **.NET Framework**: .NET Framework 4.5 と .NET Framework 4.6 の間には、サイド バイ サイド インストールの概念はありません。 .NET Framework 4.6 のバイナリは、.NET Framework 4.5 のバイナリを上書きします。 .NET Framework 4.6 は [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] の要件であり、以前のバージョンの BizTalk Server ではサポートされていません (インストールされていません)。

- **Office 2016 と Office 2013**: 同じコンピューターに[異なるバージョンの Office をインストールして使用](https://support.office.com/article/Install-and-use-different-versions-of-Office-on-the-same-PC-6EBB44CE-18A3-43F9-A187-B78C513788BF)します。 また、[これらの問題](https://support.microsoft.com/kb/3094527)を確認します。

- **BizTalkServerApplication ホスト**: アップグレードには、既定のホストが存在している必要があります。 SQL アダプターの送信ポートと受信場所に関連付けられている既定のホスト インスタンスが削除された場合、アップグレード前に、既定のホストを SQL アダプターに関連付けます。 アップグレードが完了したら、既定のホストを一覧から削除できます。

- **カスタム バインド**: 以前のバージョンの .NET Framework を使用して作成されたユーザー定義のカスタム バインドは、アップグレード後は使用できなくなります。 カスタム バインドを使用するには、.NET Framework 4.6 machine.config ファイルにカスタム バインドを手動で追加します。

- **構成ファイル**: BizTalk Server 2013 R2/2013 のすべてのカスタム構成ファイルをバックアップします。 BizTalk Server は、`btsntsvc.exe.config` および `bm.exe.config` ファイルについてのみ、変更の移行をサポートします。



### <a name="bam-alerts"></a>BAM 警告

BAM 警告を使用するには、SQL Server Database Mail が必要です。 SQL Server の移行前のバージョンが既存の BAM 警告定義と Notification Services を使用していた場合、BAM 警告の定義をバックアップし、アップグレード後にその定義を展開することができます。 BM.exe コマンド ライン ツールを使用します (`\Program Files (x86)\Microsoft BizTalk Server <your version>\Tracking`)。 具体的には、以下の手順で行います:

1. コマンド プロンプトを開き、`\Program Files (x86)\Microsoft BizTalk Server <your version>\Tracking` に移動します。
2. コマンド プロンプトで定義ファイルを作成します。 `bm.exe get-defxml -FileName:YourBAMDefinition.xml`
3. [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013 の構成で、BAM 警告の構成を解除します。
4. SQL Server 2016 または SQL Server 2014 SP1 にアップグレードします。
5. SQL Server Database Mail を構成します。
6. [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] にアップグレードする。
7. [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] の構成で、BAM 警告を構成します。
8. コマンド プロンプトで、保存した定義ファイルを展開します。 `bm.exe update-all -DefinitionFile:YourBAMDefinition.xml`

> [!IMPORTANT]
> この手順の順番に従わないか、定義ファイルを作成しない場合、BizTalk Server のアップグレード後に定義ファイルを再作成する必要があります。
> 
> BM.exe のヘルプを表示するには、「`bm.exe help`」と入力します。


### <a name="bam"></a>BAM 

- **BAM DTS パッケージ**: すべての BAM データ変換サービス (DTS) パッケージを停止します。 停止しないとデータが失われたり、オンライン分析処理 (OLAP) キューブが破損したりする場合があります。 

- **ディスク容量**: 少なくとも既存の BAM データベースのサイズの空きディスク容量が必要です。

- **リアルタイム集計**: 現在使用しているバージョンの BizTalk Server で BAM リアルタイム集計を使用していて、SQL Server をアップグレードする場合は、SQL Server Enterprise Edition をインストールするか、SQL Server Enterprise Edition にアップグレードします。 Enterprise Edition でないと、アップグレードは失敗します。

- **maxTimeout 値**: サイズの大きな BAM データベースを使用している場合は、machine.config ファイルで分散トランザクションに関する `maxTimeout` 値を次のように更新します。  

    ```
    <system.transactions>
       <machineSettings maxTimeout="23:59:59" />
    </system.transactions>
    ```

- **追跡プロファイル エディター (TPE) で有効にされている BAM 追跡**: アップグレードすると、以前に展開した追跡プロファイルはアップグレードされますが、それに対応するインターセプター構成はアップグレードされません。 新しい受信済み BAM メッセージは、引き続き BizTalk Server 2013 R2/2013 への参照を持つ可能性があります。 対応するインターセプター構成をアップグレードするには、追跡プロファイル エディターを使用してアクティビティのプロファイルを取得し、次にプロファイルを再適用します。

- **LiveData ブック**: BizTalk Server 2013 R2/2013 で BAM を使用している場合は、アップグレード後に手動で LiveData ブックを再生成する必要があります。 LiveData ブックを再生成するには:

  1. 次のコマンドを実行して、BAM 定義を取得します。  
     `BM get-defxml MyDef.xml`
  2. Microsoft Office Excel を起動し、BAM アドインを選択して、PivotTable レポートを再作成します。ステップ 1 で作成した *MyDef.xml* ファイルをインポートし、PivotTable レポートを再作成します。 新しい BAM ブックを *MyNewBook.xls* という名前で保存します。
  3. `<BAMDefinition>\<Extension>\<OWC>\<PivotTableView>\<PivotTable>\<PivotView>\<Label>` パスの `<Caption>` の下にある *MyDef.xml* でピボットテーブル名を探して、ピボットテーブル レポートの名前を変更します。 次の名前を使用して、*MyNewBook.xls* のピボットテーブル レポートの名前を変更します。
  4. 次のコマンドを実行して、LiveData ブックを再生成します。  
     `BM regenerate-livedataworkbook MyNewBook.xls`

     > [!NOTE]
     > 再生成された LiveData ブックでは、元の LiveData ブックにある Excel アイテム (チャートなど) は再作成されません。 手動でアイテムを再作成します。


### <a name="enterprise-single-sign-on-esso"></a>エンタープライズ シングル サインオン (ESSO)

|                            シナリオ                            |                                                                                                                                                                                                                                                                                                                                          詳細                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 以前のバージョンの Enterprise Single Sign-on からのアップグレード | BizTalk Server には、更新されたバージョンの Enterprise Single Sign-On (ESSO) が含まれています。 このリリースを以前のバージョンの BizTalk がインストールされているコンピューターにインストールする場合は、ESSO はセットアップ中に自動的に更新されます。 アップグレード前に次の手順を実行することをお勧めします。 <br/><br/> 1.現在のバージョンのシングル サインオン データベース (SSODB) が安全な場所にバックアップされていることを確認します。 <br/>2.現在のマスター シークレット キーが安全な場所にバックアップされていることを確認します。<br/>3.マスター シークレットのパスワードを確認します。<br/><br/>1 つの BizTalk グループ内のすべてのサーバーを同じリリースにアップグレードします。 この要件は、スタンドアロンのマスター シークレット サーバーの場合でも同じです。 |
|  エンタープライズ シングル サインオン スタンドアロン セットアップを使用したアップグレード  |             次の手順に従って、専用のマスター シークレット サーバーなどの、スタンドアロンのエンタープライズ シングル サインオンがインストールされているコンピューター上でアップグレードを実行します。<br/><br/>1.現在のマスター シークレット キーが安全な場所にバックアップされていることを確認します。<br/>2.現在のバージョンの SSODB が安全な場所にバックアップされていることを確認します。<br/>3.[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] インストール メディアから ESSO の **Setup.exe** を実行します。 既定のインストール フォルダーは `\Platform\SSO` です。<br/>4.**[自動実行]** ダイアログ ボックスで、**[Microsoft Enterprise Single Sign-On]** を選択します。<br/>5.[概要] ダイアログ ボックスで、**[アップグレード]** を選択します。              |

### <a name="multicomputer-environment"></a>複数コンピューター環境
複数コンピューターの環境では、SSO マスター シークレット サーバーのコンピューターをアップグレードします。 その後、その他の BizTalk Server コンピューターをアップグレードします。 グループ内の複数の BizTalk コンピュータを同時にアップグレードすることはできません。 以下の手順で、一度に 1 台ずつコンピュータをアップグレードします:

1. シングル サインオンのマスター シークレット サーバー
2. BizTalk Server を実行しているランタイム コンピューター
3. 管理ツールと監視コンピューター
4. BizTalk Server を実行している開発用コンピューターおよびその他のコンピューター

**追加情報**  
設定ダッシュボードを使用すると、BizTalk Server のさまざまな設定を微調整してパフォーマンスを最適化することができます。 BizTalk グループ、BizTalk ホスト、および BizTalk ホスト インスタンスの設定を変更することもできます。 「[BizTalk Server パフォーマンス チューニングのための設定ダッシュボードの使用](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)」をご覧ください。

### <a name="general-information"></a>一般情報

- **アカウント名**: 可能な場合は常に既定のアカウント名を使用してください。 BizTalk Server セットアップ プログラムでは、インストール済みコンポーネントが既定のアカウントを使用するように、自動的に構成されます。 Active Directory フォレストに複数の BizTalk Server グループがある場合は、競合を回避するためにアカウント名を変更してください。 BizTalk Server では、サービスアカウントおよび Windows グループに対して `<NetBIOS domain name>\<user>` という形式だけがサポートされます。

- **アカウント名と BAM 管理 Web サービス**: BizTalk Server では、ビルトイン アカウントまたはパスワードなしのアカウントを BAM 管理 Web サービス ユーザーに使用することはサポートされていません。 

  このようなアカウントを使用するように BizTalk Server を構成できたように見えても、BAM 管理 Web サービスが異常終了します。 

  BAM アプリケーション プールに対してはこのようなアカウントを使用できます。

- **BizTalk アセンブリ ビューアー**は 64 ビット オペレーティング システムでは使用できません。

- **インストールとアンインストール**: BizTalk Server をアンインストールする場合は、BizTalk Server データベースを手動で削除します。 開発者またはエバリュエーターとして BizTalk Server をインストールする場合、仮想マシンへのインストールを検討してください。 これにより、再インストールが必要になった場合、アンインストールすることなく、事前設定されたチェックポイントまで容易にロールバックできます。

- **32 ビットおよび 64 ビットのコンピューター**: 32 ビット版 Windows または 64 ビット版 Windows への BizTalk Server のインストールに大きな違いはありません。 このドキュメントでは、32 ビット版でのインストールと 64 ビット版でのインストールの両方について説明します。 違いについても説明します。

- **ワークグループ**: 単一コンピューター上のワークグループ環境への BizTalk Server のインストールと構成はサポートされています。 この場合、SQL Server および BizTalk Server の両方の機能とコンポーネントは同じコンピューターにインストールして構成されます。

- **ターミナル サーバー**: アプリケーション モードで動作するターミナル サーバーを使用して BizTalk Server をインストールすることはできません。 詳細については、「[KB 832027](https://support.microsoft.com/kb/832027)」を参照してください。

- **サイレント アップグレード**: サポートされていません。

- **サポートされていないアプリケーション**: BizTalk Server は、サポートされていない API (PAM API など) 上で構築されたカスタム アプリケーション、ストアド プロシージャ、またはデータベースへの直接アクセスをサポートしていません。 運用環境をアップグレードするときは、事前に 1 回以上のテスト アップグレードを実行します。

- **SQL Server インスタンス**: プラットフォームをアップグレードする前に、SQL Server インスタンスをアップグレードすることをお勧めします。

## <a name="prepare-your-computer-for-upgrade"></a>アップグレードのためのコンピューターの準備

|                 タスク                  |                                                                                                                                                                                                                                        Info                                                                                                                                                                                                                                         |
|---------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   重要な Windows 更新プログラムをインストールする    |                                                                                                                                                                                                [プログラム] メニューから [Windows Update] を選択します。 コンピューターの再起動が必要な場合があります。                                                                                                                                                                                                 |
|      BAM 警告の定義を保存する       |                                    現在、既存の BAM 警告の定義と SQL Server Notification Services を使用している場合にのみ適用されます。 BM.exe を使用して定義ファイルを作成し、[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013 の構成で BAM 警告の構成を解除します。<br/><br/>**アップグレードの前に** (このトピックでは) 具体的な手順を列記します。<br/><br/>それ以外の場合、アップグレード後に BAM 警告の定義を再生成します。                                    |
|          SQL Server をアップグレードする           |                                         サポートされるバージョンの SQL Server にアップグレードします。 次のチュートリアルを参照してください。<br/><br/>[BizTalk Server 2016 のハードウェア/ソフトウェア要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)<br/>[SQL Server 2016 へのアップグレード](https://msdn.microsoft.com/library/bb677622.aspx)<br/>[SQL Server 2014 へのアップグレード](https://msdn.microsoft.com/library/bb677622(v=sql.120).aspx)                                          |
|    SQL Server クライアント ツールをアップグレードする    |                                                                                                                                                複数コンピューター環境では、管理ツールを別のコンピューターにインストールすることができます。 管理ツールを含む、SQL Server 管理のクライアント ツールをアップグレードします。                                                                                                                                                |
|         Visual Studio のインストール         |                         サポートされるバージョンについては、「[BizTalk Server 2016 のハードウェアとソフトウェアの要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)」をご覧ください。 異なる Visual Studo のバージョンをサイド バイ サイドでインストールできます。 [Visual Studio 2015](https://msdn.microsoft.com/library/ms246609(v=vs.140).aspx) および [Visual Studio 2013](https://msdn.microsoft.com/library/ms246609(v=vs.120).aspx) を参照してください。                         |
|            Office をインストールする             |                                     「[異なるバージョンの Office を同じ PC にインストールして使う](https://support.office.com/article/Install-and-use-different-versions-of-Office-on-the-same-PC-6EBB44CE-18A3-43F9-A187-B78C513788BF)」をご覧ください。 サポートされる Office のバージョンの一覧については、「[BizTalk Server 2016 のハードウェアとソフトウェアの要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)」をご覧ください。                                     |
| BizTalk Services と Windows サービスを停止する |                                                                                                      - BizTalk Services BizTalk グループ: <*アプリケーション名*><br/>- BizTalk ベース EDI サービス<br/>- ルール エンジン更新サービス<br/>- World Wide Web Publishing サービス<br/><br/>**注**<br/>BizTalk Server のアクセラレータがインストールされている場合は、HL7 ログ サービスを停止します。                                                                                                      |
|         データベースをバックアップする         | - Master<br/>- MSDB<br/>- BAMArchive<br/>- BAMPrimaryImport<br/>- BAMStarSchema<br/>- BizTalkDTADb<br/>- BizTalkEDIDb<br/>- BizTalkHwsDb<br/>- BizTalkMgmtDb<br/>- BizTalkMsgBoxDb<br/>- BizTalkRuleEngineDb<br/>- TPM<br/>- BizTalkAnalysisDb<br/>- BAMAnalysis<br/><br/>[SQL Server 2014: バックアップの概要](https://technet.microsoft.com/library/ms175477(v=sql.120).aspx)<br/>[SQL Server 2012: バックアップの概要](https://technet.microsoft.com/library/ms175477(v=sql.110).aspx) |
|  SQL Server データベース メールを構成する   |                                                                                                                      BAM 警告の定義と SQL Server Notification Services を使用している場合にのみ適用されます。<br/><br/>**アップグレードの前に** (このトピックでは) 具体的な手順を列記します。<br/><br/>それ以外の場合、アップグレード後に BAM 警告の定義を再生成します。                                                                                                                       |

## <a name="do-the-upgrade"></a>アップグレードを実行する

> [!IMPORTANT]
> SQL Server をインストールした場合、SQL Server セットアップを実行したログオン アカウントにシステム管理者の権限が付与されています。 システム管理者の権限は BizTalk Server のインストールにも必要です。 次のいずれかの操作を行います。
> 
> - SQL Server のインストール時に使用した同じアカウントを使用する  
> **または**  
> - 現在のログオン アカウントにシステム管理者権限があることを確認する

### <a name="upgrade-steps"></a>アップグレード手順

1. 開いているプログラムをすべて閉じます。
2. インストール メディアから **Setup.exe** を実行します。
3. [Start (開始)] で **[Install Microsoft BizTalk Server (Microsoft BizTalk Server のインストール)]** を選択します。
4. **[ユーザー情報]** で、ユーザー名、組織、プロダクト キーを入力します。 **[次へ]** を選択します。
5. ライセンス契約に同意して、**[次へ]** を選択します。
6. [カスタマー エクスペリエンス向上プログラム] で、基本設定を入力します。 詳細については、このトピックの「**付録 A**」をご覧ください。
7. **[Component Installation (コンポーネントのインストール)]** でインストール可能なコンポーネントを確認し、**[次へ]** を選択します。
8. 必須コンポーネントがコンピューターにインストールされていない場合、必要な再配布可能コンポーネントをインストールできます。 次のいずれかを実行できます。

    - [必要な再配布可能コンポーネントを Web から自動的にインストールする] を選択します。  

      または  

    - CAB ファイルを既にダウンロードしている場合は、[必要な再配布可能コンポーネントを CAB ファイルから自動的にインストールする] を選択します。 CAB ファイルの場所に移動し、ファイルを選択します。

9. **[概要]** で、アップグレード可能なコンポーネントを確認します。
10. **[アップグレード]** を選択して開始します。
11. 省略可能: **[更新プログラムの確認に Microsoft Update を使用する (推奨)]** を選択します。
12. **[アップグレードは完了しました]** で、**[BizTalk Server 構成の開始]** チェック ボックスをオフにし、**[完了]** を選択します。

**追加情報**  
BizTalk Server のアップグレード中には数多くのことが起こるため、その過程でエラーが発生することも珍しいことではありません。 ただし、準備を整えておけば、大部分のエラーは容易に解決できます。 このトピックの「**付録 B**」に記載されている、アップグレード エラーの回避方法に関するヒントおよびエラーが発生した場合の対処に関するヒントを読むことをお勧めします。

アップグレード プロセスでは、以前のバージョンの BizTalk Server の一部であった機能だけがアップグレードされます。 新機能は、アップグレード時にインストールされません。 これらの機能をインストールするには、アップグレード後にセットアップを再実行し、**[変更]** を選択して、インストールする機能を選択します。 インストールした後、**BizTalk Server 構成マネージャー**を使用して構成します。

インストールが成功したかどうかを検証するには、**[プログラムと機能]** を開き、[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] を探します。 BizTalk Server 2013 R2 が表示されていれば、インストールは成功です。

## <a name="post-upgrade"></a>アップグレード後
[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]/2013 にロールバックすることはできません。

- **BAM 警告定義 XML ファイルを作成してあった場合**: [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] の構成で、BAM 警告を構成します。 次に、保存した定義を展開します。

    **アップグレードの前に** (このトピックでは) 具体的な手順を列記します。 それ以外の場合、アップグレード後に BAM 警告の定義を再生成します。

- **MQSAgent のインストール**: MQSAgent.dll ファイルがリモートの WebSphere MQ Server にインストールされている場合は、リモートの WebSphere MQ Server 上の [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] から新しいバージョンの MQ エージェントをインストールします。

- **MSMQ の開始**: MSMQ アダプターを使用する場合、メッセージ キュー サービスを起動します。

- 
  **カスタム EXE および BRE**: BizTalk Server 2010 内のビジネス ルール エンジン アセンブリを参照するカスタム マネージド実行可能ファイルがある場合は、.NET Framework 2.0 でプロセスを実行するために、アプリケーション構成ファイルに次のコードを追加します。

    ```
    <?xml version="1.0" encoding="Windows-1252"?>
    <configuration> 
     <startup>
      <supportedRuntime version="v2.0.50727" />
     </startup>   
    </configuration>
    ```

- **SQL エージェント ジョブ**: 次の SQL Server エージェント ジョブを再構成します。

    -   DTA Purge and Archive (BizTalkDTADb): 「[DTA Purge and Archive ジョブを構成する方法](../core/how-to-configure-the-dta-purge-and-archive-job.md)」をご覧ください
    -   BizTalk Server のバックアップ (BizTalkMgmtDb): 「[BizTalk Server のバックアップ ジョブを構成する方法](../core/how-to-configure-the-backup-biztalk-server-job.md)」をご覧ください

- **アプリケーションの再起動**: アップグレードされた、展開済みのアプリケーションをすべて再起動します。

- **BAM ポータル エラー**: BAM ポータルを開いたとき、次のエラー メッセージが表示されることがあります。 

    `The server encountered a critical failure while trying to access the list of Views. The Business Management Web Service requires Administrator's attention.` 

    このエラーは、.NET Framework 2.0 を実行しているアプリケーションにより使用される Web サイト上で BAM ポータルが構成されている場合に発生することがあります。 この場合は、BAM ポータルを新しい Web サイトでホストします。 Web サイトの追加については、「[Create a Web Site](http://go.microsoft.com/fwlink/p/?LinkID=196470)」 (Web サイトを作成する) をご覧ください。 Web サイトを作成した後に、BAM ポータルを再構成します:

    1. **[BizTalk Server 構成]** を開きます。
    2. **[機能の構成解除]** を選択します。 **[機能の構成解除]** で、**[BAM ポータル]** チェック ボックスをオンにして、**[OK]** を選択します。
    3. **[BAM ポータル Web サイト]** の一覧から新しい Web サイトを選択して BAM ポータルを再構成します。

- **BizTalk 2016 Accelerator for SWIFT**: BizTalk Server アップグレード プロセスでは、編集した *BREDeployment.exe.config* ファイルは更新されません。 `\Program Files\Microsoft BizTalk 2016 Accelerator for SWIFT\SDK\Tools` フォルダーにある *BREDeployment.exe.config* ファイルに記述されているパスを、手動で変更します。

    また、A4SWIFT Web サービスと Message Pack 構成は削除されます。 BizTalk Server をアップグレードした後で、これらを再構成します。

## <a name="appendix-a-customer-experience-improvement-program"></a>付録 A: カスタマー エクスペリエンス向上プログラム
BizTalk Server のカスタマー エクスペリエンス向上プログラムの一環として、ユーザーは BizTalk Server の機能の使用に関して有益なフィードバックを Microsoft に提供することができます。 収集されるデータは匿名であり、個人を特定できるものではありません。 このプログラムでは、機能の使用状況の統計情報が収集されます。

お客様にこのプログラムに参加していただくことによって、BizTalk Server のさまざまな機能の信頼性とパフォーマンスが向上します。 このプログラムの詳細およびプライバシー ポリシーについては、「[Microsoft BizTalk Server CEIP プライバシー ポリシー](http://go.microsoft.com/fwlink/p/?LinkId=188553)」をご覧ください。

## <a name="appendix-b-known-issues"></a>付録 B: 既知の問題

- **管理用コンピューターでの BAM 警告の構成**: 複数コンピューター環境では、管理用、ランタイム、SQL Server のコンポーネントが別々のコンピューターにインストールされます。 BAM ツールまたは BAM 警告を使用する場合、以下の問題が発生することがあります:

    **問題**: BizTalk 管理用コンピューターで BAM ツールを構成するときに、次のエラーが発生します。

    `Service BAMAlerts was not found on computer ‘.’.The specified service does not exist as an installed service.`

    **問題**: ランタイム コンピューターから BAM アクティビティ定義を展開するときに、次のエラーが発生します:

    `A network-related or instance-specific error occurred while establishing a connection to SQL Server. The server was not found or was not accessible. Verify that the instance name is correct and that SQL Server is configured to allow remote connections. (provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server) (.Net SqlClient Data Provider)`

    このエラーは、BAM 警告がランタイム コンピューターで構成された場合に発生します。 解決するには、BizTalk 管理コンソールと同じコンピュータで BAM 警告を構成します。 ランタイム コンピューターでは BAM 警告を構成しないでください。

- **アップグレードの失敗からの復旧**: アップグレードのいずれかの段階で、アップグレードが失敗する可能性があります。 アップグレードの失敗から復旧する方法は、失敗が発生したのが各フェーズのどのポイントかによって決まります。

  - アップグレードが必須コンポーネントをインストールする際に失敗した場合、必須コンポーネントの以降のインストールが中止され、エラーを示すメッセージが返されます。 この後、問題を解決して、セットアップを再実行できます。

  - アップグレードの失敗が、データベースをアップグレードする際、既存の BizTalk Server バージョンから機能を削除する際、または新しいバージョンをインストールする際に発生した場合、以降のインストールが中止され、エラーを示すメッセージが返されます。 変更はすべてロールバックされます。 BizTalk Server データベースに加えられた変更はロールバックできません。

      BizTalk Server の以前のインストールのコンポーネントがアップグレード中に削除された場合、コンピューターには BizTalk Server コンポーネントがない状態になっている可能性があります。 前のインストールからの機能構成情報は維持される場合があります。 また、アップグレード プロセスが失敗した段階によっては、BizTalk Server データベースがアップグレードされている場合があります。 場合によっては、セットアップを再実行する前に、以前にバックアップしたデータベースを復元する必要があります。

  - BizTalk Server の機能を再構成する際にアップグレードが失敗した場合、完了のレベルを示すメッセージが返されます。 構成のアップグレードに失敗した場合、または部分的にのみ成功した場合、BizTalk Server 構成を実行し、アップグレードを完了します。

    アップグレードに引き続き失敗し、以前のバージョンの BizTalk Server に戻す必要がある場合は、バックアップしたデータベースを復元してから、以前の BizTalk Server のバージョンを再インストールする必要があります。

- **同じバージョンの使用**: BizTalk アプリケーション グループでは、バージョンの異なる BizTalk Server がインストールされたコンピューターを実行することはできません。 たとえば、BizTalk 管理コンソールで、あるバージョンの BizTalk Server 上で実行されている送信ポートを、異なるバージョンの BizTalk Server 上で実行されている受信場所にバインドすることはできません。 

- **SSO サービスの再起動**: 以前にコンピューターに Visual Studio のバージョンまたは .NET Framework 4.5 をインストールしている場合、以前のバージョンの BizTalk Server の SSO サービスが動作を停止します。 この問題を解決するには、Visual Studio のコマンド プロンプトから `regasm SSOSQL.dll` コマンドを実行します。 このコマンドにより SSO サービスが再開されます。

    > [!NOTE]
    > 64 ビット コンピューターでは、regasm コマンドの 32 ビット バージョンと 64 ビット バージョンを実行します。

- **SOAP が使用できない**: プラットフォームのアップグレード後は、アクセス許可の理由により SOAP メッセージを送信できなくなる場合があります。 この問題を解決するには、`C:\inetpub\wwwroot\<SOAPExternalAppName>\` にある Web.config ファイルを、次のテキストを使用して編集します。

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

    場合によっては、カスタム エラー モードを **[リモートのみ]** から **[オフ]** に変更する必要があります。

- **証明書ストア**: アップグレードの後で、BizTalk Server 管理コンソールから送信ポートまたは受信場所を開くと、次のエラーが発生します。 `Could not open certificate store, the system cannot find the file specified (System).`

    このエラーは、証明書ストアが見つからない場合に発生します。

- **BAM ポータル**: 64 ビット コンピューターでは、アップグレードを行った後は BAM ポータルにアクセスできません。 解決方法:

  1. `%BizTalkInstallDir%\BAMPortal\web.config` にある web.config ファイルのバックアップ コピーを作成します。

  2. BizTalk Server の Tracking フォルダーにある bm.exe を使用して、コマンド プロンプトから次のコマンドを実行します。 `bm.exe get-config –FileName:<filepath> -Server:MyServer -Database:MyDB`

     Config XML ファイルから *BAMVRoot* の値を取得します (xpath: BAMConfiguration\ GlobalProperty\Name="BAMVRoot")。

  3. BAMVRoot として示されているコンピューターで BizTalk Server の構成を開き、BAM ポータルの構成を解除します。

  4. BizTalk Server の構成を開き、BAM ポータルを構成します。

  5. ステップ (1) で示した場所から新しい web.config ファイルを開きます。

  6. web.config ファイルのバックアップ コピーを使用して、次の値を設定します (`configuration\appSettings` の下)。

      - key="MainPageContentUrl"
      - key="AlertNotificationOptions"

     > [!NOTE] 
     > 64 ビット コンピューターの場合は、オペレーティング システムをアップグレードした後に BAM ポータルを再構成することをお勧めします。

- **EDI BAM アクティビティの展開**: アップグレードするとき、アップグレードが部分的にしか成功しない場合があります。 これは、(EDI 構成を含む) SQL Server をアップグレードする際に発生することがあります。 EDI BAM アクティビティが適切にアップグレードされないことがあります。 この問題を解決するには、管理者資格情報を使用してコマンド プロンプトから次のコマンドを実行して、BAM アクティビティを展開します。

    `"<BizTalk Installation Folder>\Tracking\bm.exe" deploy-all -DefinitionFile:"<BizTalk Installation Folder>\AS2ResendActivityDefs.xml" -Server:"<BAM Database Server Name>" -Database:"<BAM Database Name>"`

    `"<BizTalk Installation Folder>\Tracking\bm.exe" update-all -DefinitionFile:"<BizTalk Installation Folder>\Microsoft.BizTalk.Configuration.EdiAS2.UpgradeR2toR3.xml" -Server:"<BAM Database Server Name>" -Database:"<BAM Database Name>"`

    `"<BizTalk Installation Folder>\Tracking\bm.exe" update-all -DefinitionFile:"<BizTalk Installation Folder>\Microsoft.BizTalk.Configuration.Batching.UpgradeR2toR3.xml" -Server:"<BAM Database Server Name>" -Database:"<BAM Database Name>"`

- **クラスター上の SSO エラー**: BizTalk Server のランタイム クラスター環境で、アップグレードしようとすると、次のエラー メッセージが表示される場合があります。

    `SSO Master Secret Server service is not running on <Cluster name>.Please start the service to continue the upgrade.` 

    この問題を解決するには、SSO および BizTalk Server ランタイム クラスターの両方で、SSO サービスを最新の状態に更新します。

    **SSO クラスター内の SSO サービスを最新の状態に更新するには**:

  1. クラスター アドミニストレーターで、クラスター化された Enterprise SSO サービス リソースを含むクラスター グループを**オンラインにします**。 これにより、クラスター グループのすべてのリソースが開始します。

  2. Enterprise SSO サービスのクラスター化されたインスタンスを**オフラインにします**。 その後、**オンライン**に戻します。

  3. クラスター グループを**移動**します。 この操作により、クラスター化された Enterprise SSO サービス リソースを含むクラスター グループが最初のノードから 2 番目のノードに移動されます。

  4. Enterprise SSO サービスのクラスター化されたインスタンスを**オフラインにします**。 その後、**オンライン**に戻します。

     **BizTalk Server ランタイム クラスターで SSO サービスを最新の状態に更新するには**:

  5. クラスター アドミニストレーターで、クラスター化された BizTalk Server ランタイム リソースを含むクラスター グループを**オンラインにします**。 これにより、クラスター グループのすべてのリソースが開始します。

  6. Enterprise SSO サービスのクラスター化されたインスタンスを**オフラインにします**。 その後、**オンライン**に戻します。

  7. クラスター グループを**移動**します。 この操作により、クラスター化された BizTalk Server ランタイム リソースを含むクラスター グループが最初のノードから 2 番目のノードに移動されます。

  8. Enterprise SSO サービスのクラスター化されたインスタンスを**オフラインにします**。 その後、**オンライン**に戻します。
