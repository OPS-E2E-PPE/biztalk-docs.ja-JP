---
title: インストールの既知の問題 |Microsoft Docs
description: 既知の問題と一般的な問題と解決策をインストールすると、BizTalk Server の構成
ms.custom: ''
ms.date: 11/30/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4d0e707-6b9e-49e1-9f17-19b3bac1229e
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a38d3665e71ebc9e11c133dde49ad070f2aa0e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397101"
---
# <a name="troubleshoot-biztalk-server-setup"></a>BizTalk Server のセットアップをトラブルシューティングします。

## <a name="introduction"></a>概要  
 このトラブルシューティング ガイドには、BizTalk Server のインストール中に発生する可能性の最も一般的な問題と同様に既知の問題が一覧表示します。 このガイドでは、Windows Server ロゴ プログラムの BizTalk Server の認定に関する詳細情報を提供するカスタム動作も含まれています。  これは、BizTalk Server セットアップ操作中に実行することがカスタム アクションの一覧を示します。  
  
## <a name="review-install-steps"></a>インストールの手順を確認してください。  
BizTalk Server コンピューターを正しく準備前に、BizTalk Server がインストールされている場合、または BizTalk Server の以前のインストールが完全にアンインストールされない新しいインストールが試みられる前にあるために、BizTalk Server のセットアップに関する問題の大部分が発生します。  
  
2 つのチェックリスト、下のコンピューターが BizTalk Server をサポートするために正しく構成されていることを確認する、BizTalk Server インストール ガイドで検索することもできます。 これを確認します。 この情報を確認した後、セットアップが成功しない場合、このドキュメントの残りの部分では、トラブルシューティングのヒントが役に立ちます。  
  
1. 前提条件のソフトウェアとプログラムをインストールします。

    * [BizTalk Server 2016](set-up-and-install-prerequisites-for-biztalk-server-2016.md)
    * [BizTalk Server 2013 R2 & 2013](prepare-your-computer-for-installation.md)

2. インストールし、BizTalk Server を構成します。  

    1. BizTalk Server をインストールします。[BizTalk 2016](install-biztalk-server-2016.md) 、 [BizTalk 2013 R2/2013](install-biztalk-server-2013-and-2013-r2.md)  
    2. [構成](configure-biztalk-server.md)BizTalk Server
    3. [構成後の手順](post-configuration-steps-to-optimize-your-environment.md)
  
## <a name="some-edias2-artifacts-are-still-active-after-unconfiguring"></a>構成解除した後、一部の edi/as2 アイテムがまだアクティブ  
  
**問題**  
 BizTalk Server EDI に関連する一部の BizTalk Server アイテムの BizTalk edi/as2 機能の構成を解除すると、AS2 処理を BizTalk グループ構成のコンテキストでアクティブにすることができます。 これらの成果物には、EDI および AS2 のパイプラインとバッチ処理オーケストレーションが含まれます。 その結果、BizTalk edi/as2 機能を構成解除した後でも、基本的な EDI および AS2 処理を実行することができます。  
  
**原因**   
 EDI および AS2 処理に関連付けられているアクティブなポートがあります。 一部のアイテムは引き続きこれらのポートをアクティブにしたままに機能します。  
  
**解決方法**  
 すべての edi/as2 アイテムを無効にするを無効にし、停止、または EDI および AS2 処理に関連付けられているポートを削除する必要があります。  
  
## <a name="after-renaming-biztalk-or-sql-server-computer-the-configuration-wizard-fails"></a>構成ウィザードが失敗した後、BizTalk または SQL Server コンピューターの名前を変更するには、  
  
**問題**  
 この問題は、いくつかの方法で問題を発生可能性があります。  
  
-   構成マネージャーが [概要] ページを正しく読み込むが、画面に機能を構成しようとすると、機能のオプションは表示されません。  
  
-   構成ウィザードは、SQL Server に接続できません。  
  
-   すべてではなく、一部の機能の構成を解除するすべての構成を解除しようとしています。  
  
**原因**   
 BizTalk Server の構成では、コンピューターのネットワーク名を格納します。 コンピューターの名前変更は、configuration manager との構成ウィザードは、BizTalk Server を特定できなくなります。 SQL Server コンピューターの名前が変更された後、BizTalk Server が構成されている場合、同様の問題が発生します。  
  
**解決方法**  
 BizTalk Server コンピューター、または SQL Server コンピューターに名前を変更できません。 場合は、サーバーの名前を変更する必要があります、コンピューターの名前を変更する前にすべての BizTalk 機能の構成を解除します。 コンピューターの名前を変更するには後、は、BizTalk Server の機能を再構成します。  
  
## <a name="business-rules-configuration-wizard-fails"></a>ビジネス ルール構成ウィザードが失敗しました。  
  
**問題**  
  
-   ビジネス ルールの構成ウィザードは、「一部のコンポーネントの構成に失敗しましたし、それらのコンポーネントの設定は適用されませんでした」エラーで失敗します。  
  
-   対象のビジネス ルール エンジンが既に正常に構成されて、BizTalk サーバー コンピューターには、ルール エンジン更新サービスは開始に失敗し、手動で開始することはできません。  
  
この問題が発生したときに、BizTalk Server コンピューターのアプリケーション ログには、次のようなエラーを生成可能性があります。  
  
```  
Service could not be started. : System.Net.Sockets.SocketException (10061): No connection could be made because the target machine actively refused it ::1:3132  
  
```  
  
**原因**   
 Microsoft マルウェア プロテクション センターのリリースでは、2010 年 3 月 9 日 SettingsModifier:Win32 から潜在的な脅威に対処する、更新されたシグネチャ ファイル/公開しました。 この更新されたシグネチャ ファイル SettingsModifier:Win32 からの脅威を軽減するためにローカルの HOSTS ファイルを更新する Windows Defender などの Microsoft マルウェア検出ソフトウェアが発生することができます/公開しました。 これらの変更の結果として、BizTalk Server ルール エンジン更新サービスを開始する失敗します。  
  
**解決方法**  
 ローカルの HOSTS ファイルに含める、次の行を更新します。  
  
```  
127.0.0.1         localhost  
```  
  
 HOSTS ファイルは %systemroot%\drivers\etc\ ディレクトリ内にあります。  
  
> [!NOTE]
> Microsoft マルウェア プロテクション センター署名をする可能性のある脅威のアドレスを更新を参照してください。 [SettingsModifier:Win32/公開しました](http://go.microsoft.com/fwlink/?LinkId=146221)します。  
  
## <a name="configuration-logging"></a>構成のログ記録  
 構成プログラムでは、既定では BizTalk Server を実行しているコンピューターの一時ディレクトリに格納されている構成ログ ファイルに詳細な情報を書き込みます。 TEMP 環境変数によって指定されているフォルダーを確認するには、そのコンピューターでコマンド プロンプトを開き、次のコマンドを入力して、Enter キーを押します。  
  
 **エコー %temp%**  
  
 構成ログ ファイルの内容は、実行された構成手順の概要と、構成処理中に発生した疑いのあるエラーに関する診断情報です。 構成エラーが発生した場合、メモ帳などのテキスト エディターでは、構成ログを開くし、エラーの考えられる原因は、ログ ファイルを確認してください。  
  
## <a name="troubleshooting-tools"></a>トラブルシューティング ツール  
 SQL Server プロファイラー、Filemon、または Regmon を使用して、構成エラーに関する追加情報を収集します。 参照してください[トラブルシューティングに使用するには、ツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)します。  
  
### <a name="configuration-fails-when-biztalk-and-sql-are-installed-on-separate-computers"></a>BizTalk と SQL が別々 のコンピューターにインストールされているときに、構成が失敗します。  
  
**問題**  
 エンタープライズ シングル サインオン (SSO) コンポーネントを構成しようとすると、次のようなエラーが発生して構成が失敗します。  
  
```
An error occurred while attempting to access the SSO database.  
Function: FieldInfoCreate  
```
  
 - または -  
  
```Failed to enable the Single Sign-On (SSO) Service (error code 0X800706BA)```  
  
**原因**    
 BizTalk Server と SQL Server が別々 のコンピューターにインストールされている場合は、構成操作が Microsoft 分散トランザクション コーディネーター (MSDTC) トランザクションのコンテキストで実行される MSDTC 機能を利用できる必要があります、これらのコンピューター間のネットワーク。 BizTalk Server と SQL Server を実行しているコンピューター間のネットワークで MSDTC 機能を利用することはできません、このエラーは発生します。  
  
**解決方法**    
使用[MSDTC を使用した問題のトラブルシューティング](https://support.microsoft.com/help/306843/how-to-troubleshoot-ms-dtc-firewall-issues)に BizTalk Server と SQL Server を実行しているコンピューター間のネットワークで MSDTC 機能を確認します。  
  
### <a name="antivirus-software-interferes-with-configuration-and-causes-configuration-failures"></a>ウイルス対策ソフトウェアの干渉によって構成エラーが発生する  
  
**問題**   
 BizTalk Server の構成は、ウイルス対策ソフトウェアが、構成プログラムがウイルスであると誤って判断するときに失敗します。  
  
**原因**  
 正当な (ウイルスではない) プログラムとして、BizTalk Server 構成プログラムを含める、ウイルス対策ソフトウェアが更新されていません。  
  
**解決方法**  
 構成プログラムの実行中に、ウイルス対策ソフトウェアを一時的に無効にするか、正当な (ウイルスではない) プログラムとして、BizTalk Server 構成プログラムを認識するには、ウイルス対策プログラムを構成します。  
  
### <a name="configuration-fails-with-a-file-or-assembly-name-filenamedll-or-one-of-its-dependencies-was-not-found-error"></a>"ファイルまたはアセンブリ名 'FileName.dll'、またはその依存関係の 1 つが見つかりませんでした" というエラーによって構成が失敗する  
  
**問題**  
 構成プロセスで次のようなエラーが表示されます。  
  
 BizTalk システム アセンブリ"C:\Program \microsoft\biztalk Server 20xx\Microsoft.BizTalk.DefaultPipelines.dll 展開に失敗しました。 指定されていない例外:ファイルまたはアセンブリ名 filename.dll、またはその依存関係の 1 つが見つかりませんでした。"  
  
**原因**  
 このエラーは、アカウントがネットワーク サービスの一時フォルダーに BizTalk Server を実行するコンピューターでアクセス許可を記述する場合に発生することができます。 構成時に、BizTalk Server の構成は、.NET アセンブリを BizTalk 管理データベースに展開するのに Windows Management Instrumentation (WMI) を使用します。 WMI は、これらのアセンブリを BizTalk 管理データベースにデプロイするときに、Network Service アカウントを偽装そのため、ネットワーク サービス アカウントは、BizTalk Server を実行しているコンピューター上の一時フォルダーの書き込みアクセス権がする必要があります。  
  
**解決方法**  
 ネットワーク サービス アカウントの BizTalk Server を実行しているコンピューター上の一時フォルダーへの書き込みアクセスを付与し、構成プログラムをもう一度実行します。 TEMP 環境変数で指定されているフォルダーを決定するには、コンピューターでコマンド プロンプトを開き、次のコマンドを入力し、ENTER キーを押します。  
  
```  
echo %TEMP%  
```  
  
### <a name="configuration-fails-if-a-sql-server-database-file-that-has-the-same-name-as-the-specified-database-already-exists-in-the-sql-server-data-folder"></a>指定したデータベースと同じ名前の SQL Server データベース ファイルが SQL Server のデータ フォルダーに既に存在していると構成が失敗する  
  
#### <a name="problem"></a>問題  
 次のようなエラーが発生して構成が失敗します。  
  
```
Failed to set up BAM database(s)  
  
Cannot open database requested in login 'BAMPrimaryImport'  
  
Logon fails. Logon failed for user '*BizTalk\BizTalkUser*'  
```
  
**原因**  
 このエラーは、.mdf ファイルの場合に発生する可能性がまたは .mdf ファイルまたは .ldf ファイルを作成しようとして、BizTalk Server 構成プログラムと同じ名前を持つ SQL Server を実行しているコンピューターの \MSSQL\data フォルダーに、.ldf ファイルが既に存在します。 データベースに対して作成される .mdf ファイルと .ldf ファイルの名前は、.mdf と .ldf 拡張子を追加すると、BizTalk Server 構成プログラムで指定されているデータベースの名前から派生します。  
  
**解決方法**  
 この問題を解決するには、以下のいずれかの方法を使用します。  
  
-   現在作成しているデータベースの名前と一致する名前を持つ .mdf ファイルや .ldf ファイルを削除します。  
  
-   SQL Server の \Program Files\Microsoft SQL Server\MSSQL\data フォルダーに既に存在する .mdf ファイルや .ldf ファイルの名前と一致しないデータベース名を選択します。  
  
### <a name="configuration-fails-on-a-domain-controller-when-specifying-local-accounts"></a>ドメイン コントローラーでローカル アカウントを指定すると構成が失敗する  
  
**問題**  
 ドメイン コント ローラーで、BizTalk Server 構成プログラムを実行するときに構成はローカル グループ (たとえば、BizTalk ホスト ユーザー グループ) を指定した場合、BizTalkServerApplication ホストか BizTalkIsolatedHost ホストのいずれかの失敗します。  
  
**原因**  
 ドメイン コントローラーでは、ローカル Windows グループが自動的にドメイン Windows グループとして処理されます (ドメイン コントローラーにはローカル Windows グループのようなものは存在しません)。 構成プログラムの実行中に、ホストのローカル Windows グループを指定した場合、グループの SQL Server ログオンを作成しようとするときの構成は失敗します。 サーバーがドメイン コントローラーに設定されていると、構成プログラムのローカル Windows グループ オプションが無効になりません。  
  
**解決方法**  
 構成中に作成されるホストに対してはドメイン グループを指定します。  
  
### <a name="configuration-fails-to-create-sql-server-analysis-database-if-the-sql-server-has-been-renamed"></a>SQL サーバーの名前が変更されていると構成プログラムが SQL Server 分析データベースの作成に失敗する  
  
**問題**  
 SQL Server 分析サーバーをインストールしたコンピューターの名前を変更した場合、新しい SQL Server 分析データベースを作成しようとすると構成プログラムが失敗して、次のようなエラーが生成されます。  

```  
 Cannot connect to the repository.  
  
 Analysis server: <machine name\>  
  
 Error:  
  
 '\\\\<machine name\>\MsOLAPRepository$\msmdrep.mdb' is not a valid path.  
  
 Make sure that you correctly spell the path name and that you are  
  
 connected to the server on which the file resides.  
```
  
**原因**  
 SQL Server 分析サーバーをインストールしたコンピューターの新しい名前を構成プログラムが特定できません。  
  
**解決方法**  
 以下の手順を手動で実行し、分析サーバーを新しいコンピューター名で更新します。  
  
1.  SQL Server で開く**Microsoft SQL Server**を選択します**Analysis Services**、 をクリックし、**分析マネージャー**。  
  
2.  **分析マネージャー**ナビゲーション ウィンドウで、ダブルクリックして、**分析サーバー**ノードを展開します。  
  
3.  リポジトリ接続文字列を編集して、選択すると、サーバーを右クリックして**リポジトリ接続文字列の編集**します。  
  
4.  **リポジトリ接続文字列の編集** ダイアログ ボックスでこの文字列内のサーバー名を確認しが正しくない場合、新しいコンピューター名を更新します。  
  
5.  次の場所に移動します: <*インストール ディレクトリ*> \Program Files\Microsoft Analysis services \bin です。  
  
6.  右クリックし、 **Bin**フォルダー、およびクリック**共有とセキュリティ**します。 **Bin のプロパティ** ダイアログ ボックスが表示されます。  
  
7.  **Bin のプロパティ**ダイアログ ボックスで、をクリックして、**共有** タブに、すべてのオンライン分析処理 (OLAP) 管理者が完全なアクセス許可をこのフォルダーにあることを確認します。  
  
### <a name="artifacts-disappear-from-configuration-database-on-redeployment-of-assemblies-from-visual-studio"></a>Visual Studio からアセンブリを再展開の構成データベースからアイテムが表示されなくなります  
  
**問題**  
 ときに BizTalk Server プロジェクトを再展開 Visual Studio で、プロジェクト レベルで再デプロイ プロジェクトの参照が消える、BizTalk Server MMC が更新されたときに表示されるプロジェクト内に含まれるすべての成果物。  
  
**原因**  
 この問題の原因を示すために、ユーザーが Maps プロジェクトを再展開しようとしているサンプル BizTalk Server ソリューションに基づく例について考えてみます。 プロジェクトをコンパイルすると個々のアセンブリが生成されます。 次の図は、ユーザーが再展開を行う前のソリューションの状態を示しています。 アイテム間の関係は次のようになっています。  
  
-   Orch1、Orch2、Maps、Pipelines、および Schemas はプロジェクトです。  
  
-   Orch1 は Maps を参照し、Maps は Schemas を参照しています。  
  
-   Orch2 は Schemas を参照しています。  
  
-   Pipelines は Schemas を参照しています。  
  
![bcd_ExistingBizTalkServerSolutionc](../install-and-config-guides/media/bcd_ExistingBizTalkServerSolutionc.gif)  
  
ユーザーが Visual Studio の既定のプロジェクト設定を使用して Maps プロジェクトを再展開すると、次の図のように、Orch1、Orch2、および Pipeline の各アイテムが消えてしまいます。  
  
![bcd_BizTalkSolutionWLostArtifactsc](../install-and-config-guides/media/bcd_BizTalkSolutionWLostArtifactsc.gif)  
  
 Maps の再展開は、現在展開されている Maps.dll アセンブリの展開を解除して、新しい Maps.dll ファイルを展開する、2 段階のプロセスです。 Visual Studio は、再デプロイ プロセスの一環として自動的に次の手順を実行します。  
  
> [!NOTE]
>  前の文は厳密には正しくありません。というのも、これらの手順は Visual Studio で常に行われるものなので、正しく行われているかどうかを意識することはありません。  
  
 重要なポイントは、BizTalk Server アセンブリの展開を解除するためには Visual Studio が、すべてのアセンブリはそのアセンブリに依存する展開フラグが設定されているを展開解除するには。 この例で言うと、再展開の最初の展開解除の手順を実行するには、BizTalk Server が Orch1.dll (Maps.dll に依存している) の展開を解除する必要があります。 Maps.dll の展開を解除する、Visual Studio には、(展開フラグの設定があると仮定) Schemas.dll も展開解除されます。 Schemas.dll の展開を解除するには、Orch2.dll と Pipelines.dll (いずれも Schemas.dll に依存している) の展開を解除する必要があります。  
  
 Visual Studio Maps.dll とそれが依存するアセンブリのみを再デプロイで問題が存在する。 この場合は Schemas.dll します。 そのため、ユーザーが BizTalk Server MMC を更新すると、Orch1、Orch2、および Pipeline の各アセンブリが消えたように見えますが、Maps.dll と Schemas.dll は引き続き表示されます。  
  
**解決方法**  
 メイン プロジェクト (他のプロジェクトを参照しているプロジェクト) に対して次の手順を実行します。  
  
1.  ソリューション エクスプローラーで、ソリューション ノードを右クリックします。  
  
2.  クリックして**プロパティ**を開く、**ソリューション プロパティ ページ** ダイアログ ボックス。  
  
3.  をクリックして**構成プロパティ**、 をクリックし、**構成**します。  
  
4.  クリア、**デプロイ**参照先のプロジェクトのチェック ボックス。  
  
5.  ソリューション エクスプローラーで、新しいソリューション レベルの展開を実行します。 これを行うには、ソリューション ノードを右クリックし をクリックし、**ソリューションの配置**します。  
  
### <a name="supported-virtual-directory-types"></a>サポートされている仮想ディレクトリのタイプ  
 関連付けられている仮想ディレクトリが型の場合にのみ、エクスポート操作は成功を MSI のエクスポートを実行しようと、オーケストレーションから Web サービスを参照するときに**IIsWebVirtualDir**または**IIsWebDirectory**. **IIsWebVirtualDir**と**IIsWebDirectory**は IIS メタベースに表示されるノードの種類。 **IIsWebVirtualDir**の仮想ディレクトリ、**パス**絶対ファイル フォルダーを指すプロパティ。 **IIsWebDirectory**仮想ディレクトリでは、**パス**プロパティ別のサブフォルダーでは通常、相対ファイル フォルダーを参照および**IIsWebVirtualDir**または**IIsWebDirectory**ノード。 メタベース階層でフォルダーを表すものとしてはこの 2 つのタイプが一般的です。  
  
 型の仮想ディレクトリ**IIsConfigObject**はサポートされていませんし、この場合、MSI のエクスポートは失敗します。 **IIsConfigObject**が、予期しないメタベース ノード タイプは BizTalk Server が正しく処理されないか、有効なノード型か、正しく作成されていない (およびしたがって無効な) メタベース エントリを示す値。 BizTalk Server ではこのような状況で、次のようなエラー メッセージが表示されます。種類 IIsConfigObject の予期しないディレクトリ エントリ"IIS://LM/W3SVC/1/ROOT/BadVdir/"。  
  
### <a name="unable-to-view-group-information-after-removing-stale-logons"></a>古いログオンを削除するとグループ情報を表示できなくなる  
  
**問題**  
 構成中に古いログオンを見つけて削除すると、グループ情報を表示できなくなる場合があります。  
  
**原因**  
 これは既知の構成の問題です。  
  
**解決方法**  
 Host Windows グループのログオンを削除して再構成すると解決する場合があります。 それでもグループ情報を表示できない場合は、マイクロソフト製品サポートにご連絡ください。  
  
### <a name="cannot-change-computer-name-after-biztalk-server-is-installed"></a>BizTalk Server のインストール後にコンピューター名を変更できない  
  
**問題**  
 、BizTalk Server を実行しているコンピューター上のコンピューター名を変更して、(再起動) が、コンピューターでは、エラー メッセージを再起動するときに発生します。  
  
**原因**  
 SQL Server では、BizTalk Server が BizTalk Server をインストールして構成したら、コンピューター名の変更をサポートしていないため、コンピューター名を変更することはできません。  
  
**解決方法**  
 BizTalk Server のインストール後はコンピューター名を変更しないことをお勧めします。  
  
### <a name="known-issues-with-enterprise-single-sign-on"></a>エンタープライズ シングル サインオンに関する既知の問題  
 このセクションにエンタープライズ シングル サインオン (SSO) 関連するセットアップと構成の問題について説明します。  
  
##### <a name="entsso-service-fails-to-start"></a>ENTSSO サービスを開始できません。  
  
**問題**  
 ENTSSO サービスを開始できません。  
  
**原因**  
 ENTSSO サービスが有効な SSO 管理者アカウントで実行されていない場合、サービスを開始できません。  
  
**解決方法**  
 有効な SSO 管理者アカウントを ENTSSO サービスに指定して、サービス コントロール マネージャー (SCM) スナップインからサービスを再起動します。  
  
##### <a name="biztalk-services-dependent-on-the-enterprise-single-sign-on-service-entsso-fail-to-start-after-a-reboot"></a>エンタープライズ シングル サインオン サービス (ENTSSO) に依存する BizTalk Services は、再起動後に起動しません。  
  
**問題**  
 BTSSvc$BizTalkServerApplication はエンタープライズ シングル サインオン サービス (ENTSSO) と依存関係があり、リブート後の起動中にタイムアウトすることがあります。  
  
**原因**  
 エンタープライズ シングル サインオン サービスは、起動に約 3 分かかる場合があります。  
  
**解決方法**  
 構成の"BizTalk Service BizTalk Group:自動 (遅延開始) のスタートアップの種類のオプションを持つ BizTalkServerApplication"サービス。 これにより、すべての自動サービスのスタートアップ ルーチン完了後に、このサービスが開始されます。  
  
##### <a name="cannot-access-an-affiliate-application"></a>関連アプリケーションにアクセスできません。  
  
**問題**  
 関連するアプリケーションの管理者アカウントが有効でない場合、エンタープライズ シングル サインオン サービスはこの関連アプリケーションを無効にします。  
  
**原因**  
 SSO アプリケーションの管理者アカウントが無効です。  
  
**解決方法**  
 関連アプリケーションを作成する前に、SSO アプリケーションの管理者アカウントが有効なことを確認します。 関連アプリケーションを使用するには、そのアプリケーションを有効にする必要があります。  
  
##### <a name="rpc-error-occurs-when-connecting-to-a-client-computer"></a>RPC エラーは、クライアント コンピューターに接続するときに発生します。  
  
**問題**  
 などのコマンドを実行すると**ssomanage-displayapp** *< applicationname\>* コンピューターは、情報を取得するリモート SSO サーバーに接続しようとしていますが、受信する、次のエラー:ERROR:0x800706BA:RPC サーバーを利用できません。  
  
**原因**  
 このエラーは、間違ったサーバー情報を指定する場合、または SSO サービスがリモート サーバーで利用できない場合に発生します。  
  
**解決方法**  
  
-   次の手順では、 [SSO サーバーを設定](../core/how-to-set-the-sso-server.md)正しい SSO サーバーに接続しているかどうかを確認します。  
  
-   接続先の SSO サーバーで SSO サービスが有効になっており、実行されていることを確認します。  
  
##### <a name="master-secret-is-missing-or-corrupt"></a>マスター シークレットが見つからないか破損しています  
  
**問題**  
 マスター シークレットがない、または破損しています。 この問題は、主に構成中に発生します。 シークレットがない場合、エンタープライズ シングル サインオン サービスが開始されるときに、以下のいずれかのメッセージがイベント ログに表示されます。  
  
```
MessageId=10520  
Severity=Warning  
SSO_WARN_NO_SECRETS  
MessageId=10565  
Severity=Error  
SSO_ERROR_SECRET_VALIDATE_FAILED  
MessageId=10521  
Severity=Error  
SSO_ERROR_SECRETS_NOT_LOADED  
```

**原因**  
 この問題は、あるサービス アカウントでエンタープライズ シングル サインオン サービス (SSO) を実行中にシークレットを生成した後で、サービス アカウントが変更された場合に発生する可能性があります。 シークレットは、暗号化された形式でレジストリに保存されます。暗号化には、(ENTSSO を実行する) サービス アカウントの ID を基にしたキーが使用されます。  
  
**解決方法**  
 ENTSSO を実行しているサービス アカウントを、マスター シークレット作成時の元のサービス アカウントに変更します。  
  
1.  マスター シークレットをバックアップします。 参照してください[マスター シークレットをバックアップ](../core/how-to-back-up-the-master-secret.md)します。  
  
2.  エンタープライズ シングル サインオン サービスを停止します。  
  
3.  サービス アカウントを変更します。  
  
4.  SSO を再起動します。破損したシークレットに関するイベント ログのエラーは一切無視します。  
  
5.  マスター シークレットを復元します。 参照してください[マスター シークレットを復元](../core/how-to-restore-the-master-secret.md)します。  
  
### <a name="custom-action"></a>カスタム アクション  
 このトピックでは、Windows Server ロゴ プログラムの BizTalk Server の認定に関する詳細情報を提供します。 BizTalk Server セットアップ操作中には、次のカスタム アクションを実行することができます。  
  
|カスタム アクション|説明|  
|-------------------|-----------------|  
|ReadComplusData|カスタム COM + テーブルを読み取って XML ドキュメントを作成して、Complus_XML_Data プロパティに保存します。|  
|SchedXmlConfig|RFID データを持つマシンを構成するために使用されます。|  
|CheckBaseEDI|古いバージョンの EDI の存在を確認します|  
|CheckMQSeries|MQSeries の存在を確認します|  
|CheckNET30Vista|WCF の存在を確認します|  
|CheckWSSV3SP1|Windows SharePoint Services 3.0 SP1 の存在を確認します。|  
|CheckWSSV4|Windows SharePoint Services 4 の存在を確認します|  
|GetFrameworkPath|Microsoft .Net framework 4 および 2.0 のインストール パスを保持するインストーラーのインストーラーのプロパティを設定します。|  
|Set_BAMClientExcelDir|インストーラーで Microsoft Office ライブラリ パスを保持するプロパティを設定するための Excel アプリケーション オブジェクトを作成します。|  
|Set_CurrentUser|現在のユーザーのドメイン \ ユーザー名情報を設定します|  
|ViewInstallGuide|インストールのソース ディレクトリから BizTalk Server インストール ガイドを起動します。|  
|CA_CheckSTSLanguage|WSS および BizTalk の言語セットが同じ場合、STS_Language_Property プロパティを設定します。|  
|CA_CleanupRegistry|BizTalk Server をアンインストールする場合は、BizTalk Server の構成中に作成されたレジストリ エントリをクリーンアップします。|  
|CA_CleanupRegistry_OldProducts|以前のバージョンの BizTalk Server に属し、BizTalk Server の新規インストールの必要のないレジストリ エントリをクリーンアップします。|  
|CA_RemovePatches|BizTalk Server をアンインストールする場合に、Microsoft BizTalk Server の更新プログラムを削除します。|  
|CA_ResolveWellKnownNames|よく知られている名前を持つインストーラーのプロパティを作成し、それらに対応する SID を割り当てます。|  
|CA_SaveTargetVSVersionToRegistry|サポートされているバージョンの Visual Studio の値を TargetVSVersion_Property プロパティを設定します。|  
|CA_StopServices|IISAdmin、ルール エンジンの更新、および EDI サブシステム サービスを停止します。|  
|CleanupUsersKeys|関連するエントリは HKEY_CURRENT_USER レジストリ キーから BizTalk Server を削除します。|  
|DevEnvRunning|Visual Studio が実行されているかどうかを確認します。|  
|ValidateINSTALLDIR|BizTalk Server のインストール ディレクトリ形式を検証します。|  
|StartHostInstances|BizTalk Server ホスト インスタンスを開始します。|  
|StopHostInstances|BizTalk Server ホスト インスタンスを停止します。|  
|MQSUnConfig|構成解除の MQSeries の MQSeries 構成ウィザードを起動エージェント。|  
|LaunchConfigFmk|BizTalk Server 構成ウィザードを起動します。|  
|CHKASPNET|ASP.NET のインストール状態を確認します。|  
|CHKIIS|IIS のインストール状態を確認します。|  
|TBExpired|BizTalk Server の TimeBomb の有効期限が切れてを確認します。|  
|BrandSKU|SKU のインストールに依存する BizTalk Server の timebomb の値を更新します。|  
|CA_ERROR|インストール エラーを返します|  
|InstallComplus|Complus アプリケーションとコンポーネントをインストールします。|  
|BAM_Add_Perf_Silent|BAM のパフォーマンス カウンターをインストールします。|  
|RegsvcsApplicationDeployment|BizTalk 展開 COM + アプリケーション Dll に対して Regsvcs.exe (.NET サービス インストール ツール) を実行します。|  
|RegsvcsDeployment|Dll に対して Regsvcs.exe を実行します。|  
|RegsvcsMQSAdapter|Dll に対して Regsvcs.exe を実行します。|  
|RegsvcsSQLAdapter|Dll に対して Regsvcs.exe を実行します。|  
|WMI_Add_MSBTS_Silent|BizTalk Server の名前空間とクラスを WMI に登録します。|  
|LaunchConfigFmk_SlashUP|BizTalk Server の構成を解除します|  
|CleanupComplus|Complus アプリケーションとコンポーネントをアンインストールします。|  
|RemoveSKU|BizTalk Server TimeBomb データを削除します。|  
|BAM_Remove_Perf|BAM のパフォーマンス カウンターをアンインストールします。|  
|LoadBTSCounters|BizTalk Server パフォーマンス カウンターを読み込みます。|  
|RegisterBtprojExtn|BizTalk プロジェクト ファイル (.btproj) の拡張機能を登録します。|  
|UnRegisterBtprojExtn|BizTalk プロジェクト ファイル (.btproj) の拡張子を登録を解除します。|  
|UnRegsvcsApplicationDeployment|BizTalk Server をアンインストールするときに、特定の Dll で Regsvcs.exe を実行します。|  
|UnRegsvcsDeployment|BizTalk Server をアンインストールするときに、特定の Dll で Regsvcs.exe を実行します。|  
|UnRegsvcsMQSAdapter|BizTalk Server をアンインストールするときに、特定の Dll で Regsvcs.exe を実行します。|  
|UnRegsvcsSQLAdapter|BizTalk Server をアンインストールするときに、特定の Dll で Regsvcs.exe を実行します。|  
|UnloadBTSCounters|BizTalk Server パフォーマンス カウンターをアンロードします。|  
|WMI_Remove_MSBTS|WMI から BizTalk Server の名前空間を削除します。|  
|RegisterComsvcs|Runs regsvr32.exe on comsvcs.dll silently.|  
|DevenvSetupUninstall|DevEnv.exe/setup/resetskippkgs を実行します。|  
|RollbackComplus|ロールバック Complus アプリケーションとコンポーネントをインストールします。|  
|ResRegsvcsMQSAdapter|指定されたバイナリで regsvcs.exe を実行します。|  
|ResRegsvcsSQLAdapter|指定されたバイナリで regsvcs.exe を実行します。|  
|RestoreRegsvcsApplicationDeployment|Microsoft.biztalk.applicationdeployment.engine.dll フレームワークのパスを追加します。|  
|RestoreRegsvcsDeployment|Microsoft.biztalk.applicationdeployment.engine.dll フレームワークのパスを追加します。|  
|BrandSKURollback|インストール エラーが発生した場合、登録した SKU 情報をロールバックします。|  
|CA_RestartServices_rollback|停止したサービスを再起動します。|  
|RemoveSKURollback|レジストリから SKU 値を更新します。|  
|BAM_Res_Perf_Silent|サイレント インストール時に BAM パフォーマンス カウンター Dll としての Microsoft.BizTalk.Bam.EventObservation.dll を登録します。|  
|BAM_Rollback_Perf|Microsoft.BizTalk.Bam.EventObservation.dll を BAM パフォーマンス カウンター DLL として登録を解除します|  
|RBKRegsvcsMQSAdapter|指定されたバイナリでは、regsvcs.exe を実行します。|  
|RBKRegsvcsSQLAdapter|指定されたバイナリでは、regsvcs.exe を実行します。|  
|RestoreBTSCounters|パフォーマンス カウンターの .ini ファイル名のプロパティを復元します。|  
|RollbackBTSCounters|Unlodctr BTSSvc.3.0 コマンドします。|  
|RollbackRegsvcsApplicationDeployment|[FrameworkPath] 設定&#124;[失敗したインストール シナリオの INSTALLDIR]Microsoft.BizTalk.ApplicationDeployment.Engine.dll します。|  
|RollbackRegsvcsDeployment|アンインストール/ロールバック シナリオで regsvcs.exe を起動します。|  
|WMI_Restore_MSBTS_Silent|WMI スキーマを登録する mofcomp を呼び出してください。|  
|WMI_Rollback_MSBTS|WMI から BizTalk Server の名前空間を削除します。|  
|CA_RestartServices_commit|停止したサービスします。|  
|DevenvSetup|BizTalk Server の中にインストール/アンインストール プロセスの両方で DevEnv.exe/Setup/resetskippkgs を実行します。|  
|ExecXmlConfig|RFID の machine.config に構成の変更に使用されるデータに関連します。|  
|ExecXmlConfigRollback|RFID の machine.config に構成の変更に使用されるデータに関連します。|  
  
#### <a name="running-biztalk-components"></a>BizTalk コンポーネントの実行  
 次の表に、管理者特権で実行する必要がある BizTalk コンポーネントまたは使用可能な最高です。  
  
|フォルダーのパス|ファイル名|ユーザー特権|  
|-----------------|---------------|---------------------|  
|\Program Files (x86)\Common Files\Microsoft shared\Help 9\Microsoft Document Explorer 2008|Install.exe|最も高い特権|  
|\Program files (x86) \Microsoft BizTalk Server*バージョン*|BTSHatApp.exe|最も高い特権|  
|\Program files (x86) \Microsoft BizTalk Server*バージョン*|BTSMMCLauncher.exe|最も高い特権|  
|\Program files (x86) \Microsoft BizTalk Server*バージョン*|BtsWcfServicePublishingWizard.exe|最も高い特権|  
|\Program files (x86) \Microsoft BizTalk Server*バージョン*|BTSWebSvcWiz.exe|最も高い特権|  
|\Program files (x86) \Microsoft BizTalk Server*バージョン*|Configuration.exe|最も高い特権|  
|\Program files (x86) \Microsoft BizTalk Server*バージョン*|REDeployWiz.exe|最も高い特権|  
|\Program files (x86) \Microsoft BizTalk Server*バージョン*|Setup.exe|管理者特権|  
|\Program files (x86) \Microsoft BizTalk Server*バージョン*\XSD Schema\EDI|MicrosoftEdiXSDTemplates.exe|自己解凍形式の .exe ファイルです。|  
|\Program Files (x86)\Microsoft UDDI Services\config|構成の .exe|管理者特権|  
|\Program Files\ Microsoft BizTalk RFID\bin|BTSMMCLauncher.exe|最も高い特権|  
|\Program Files\Microsoft BizTalk RFID\BREConfi 再構成|構成の .exe|管理者特権|  
