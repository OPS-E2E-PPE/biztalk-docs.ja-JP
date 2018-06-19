---
title: インストールの既知の問題 |Microsoft ドキュメント
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
ms.openlocfilehash: 90217a4e80df6f017b451dd7c40f6a1dfe3898ac
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "26011035"
---
# <a name="troubleshoot-biztalk-server-setup"></a>BizTalk Server のセットアップをトラブルシューティングします。

## <a name="introduction"></a>概要  
 このトラブルシューティング ガイドには、BizTalk Server のインストール中に発生する可能性の最も一般的な問題と同様に既知の問題が一覧表示します。 このガイドでは、Windows Server ロゴ プログラムの BizTalk Server の認定に関する詳細を提供するカスタム アクションも含まれます。  BizTalk Server セットアップ操作時に実行することが可能なカスタム動作の一覧を示します。  
  
## <a name="review-install-steps"></a>インストール手順を確認します。  
BizTalk Server のセットアップに関する問題の大半は、BizTalk Server をインストールする前に BizTalk Server コンピューターを正しく準備していなかったか、以前にインストールした BizTalk Server が完全にアンインストールされていない状態で新しいインストールを実行したことが原因です。  
  
2 つのチェックリスト、下のコンピューターが BizTalk Server をサポートするために正しく構成されていることを確認する、BizTalk Server インストール ガイドで検索することもできます。 これを確認してください。 この情報を確認した後もセットアップが正常に完了しない場合は、このドキュメントの残りの部分に示すトラブルシューティングのヒントを参考にしてください。  
  
1. 前提条件のソフトウェアとプログラムをインストールします。

    * [BizTalk Server 2016](set-up-and-install-prerequisites-for-biztalk-server-2016.md)
    * [BizTalk Server 2013 R2 & 2013](prepare-your-computer-for-installation.md)

2. インストールし、BizTalk Server を構成します。  

    1. BizTalk Server のインストール: [BizTalk 2016](install-biztalk-server-2016.md) 、 [BizTalk 2013 R2/2013](install-biztalk-server-2013-and-2013-r2.md)  
    2. [構成](configure-biztalk-server.md)BizTalk Server
    3. [構成後の手順](post-configuration-steps-to-optimize-your-environment.md)
  
## <a name="some-edias2-artifacts-are-still-active-after-unconfiguring"></a>一部の edi/as2 アイテムが構成解除した後アクティブな  
  
**問題**  
 後は、BizTalk Server EDI に関連する一部の BizTalk Server アイテムの BizTalk edi/as2 機能の構成を解除して、AS2 処理を BizTalk グループ構成のコンテキストでアクティブにすることができます。 これらのアイテムには、EDI パイプライン、AS2 パイプライン、バッチ処理オーケストレーションなどがあります。 このため、BizTalk EDI/AS2 機能を構成解除した後でも、基本的な EDI 処理および AS2 処理を実行できます。  
  
**原因**   
 EDI 処理および AS2 処理に関連付けられているアクティブなポートがあります。 一部のアイテムは、これらのポートがアクティブである間は、引き続き機能します。  
  
**解決方法**  
 すべての EDI/AS2 アイテムを無効にするには、EDI 処理および AS2 処理に関連付けられているポートを無効化、停止、または削除する必要があります。  
  
## <a name="after-renaming-biztalk-or-sql-server-computer-the-configuration-wizard-fails"></a>BizTalk または SQL Server コンピューターの名前を変更するには、後に、構成ウィザードが失敗します。  
  
**問題**  
 この問題は、次のようにさまざまなケースで生じることがあります。  
  
-   構成マネージャーは概要ページを正しく読み込むことができましたが、機能を構成しようとすると、画面に機能オプションが表示されません。  
  
-   構成ウィザードが SQL Server に接続できません。  
  
-   すべての構成を解除しようとすると、一部の機能は解除されますが、すべての機能は解除されません。  
  
**原因**   
 BizTalk Server の構成では、コンピューターのネットワーク名を格納します。 コンピューターの名前が変更されると、configuration manager との構成ウィザードを使うことにより、BizTalk Server を検索することはできません。 BizTalk Server を構成した後に SQL Server コンピューターの名前を変更する場合も、同様の問題が発生します。  
  
**解決方法**  
 BizTalk Server コンピューターまたは SQL Server コンピューターの名前を変更しないでください。 サーバーの名前を変更すると、コンピューターの名前が変更される前に、すべての BizTalk 機能の構成が解除されます。 コンピューターの名前を変更してから、BizTalk Server の機能を再構成してください。  
  
## <a name="business-rules-configuration-wizard-fails"></a>ビジネス ルール構成ウィザードが失敗します。  
  
**問題**  
  
-   ビジネス ルール構成ウィザードが、"一部のコンポーネントの構成に失敗しました。それらのコンポーネントにはどの設定も適用されませんでした。" というエラーによって失敗します。  
  
-   BizTalk Server コンピューターにビジネス ルール エンジンが既に正常に構成されている場合、ルール エンジン更新サービスの開始は失敗し、手動で開始することはできません。  
  
この問題が発生した場合は、BizTalk Server コンピューターのアプリケーション ログに次のようなエラーが生成されることがあります。  
  
```  
Service could not be started. : System.Net.Sockets.SocketException (10061): No connection could be made because the target machine actively refused it ::1:3132  
  
```  
  
**原因**   
 マイクロソフト マルウェア対応センターは 2010 年 3 月 9 日、SettingsModifier:Win32/PossibleHostsFileHijack からの脅威の可能性に対処するために、更新されたシグネチャ ファイルを公開しました。 この更新されたシグネチャ ファイルにより、SettingsModifier:Win32/PossibleHostsFileHijack からの脅威を緩和するために、Windows Defender などのソフトウェアでローカル HOSTS ファイルが更新されます。 これらの変更の結果、BizTalk Server ルール エンジン更新サービスが正常に開始できない場合があります。  
  
**解決方法**  
 ローカル HOSTS ファイルを更新して次の行を追加してください。  
  
```  
127.0.0.1         localhost  
```  
  
 HOSTS ファイルは %systemroot%\drivers\etc\ ディレクトリにあります。  
  
> [!NOTE]
> Microsoft Malware Protection Center 署名からことがある脅威のアドレスを更新表示[SettingsModifier:Win32/公開しました](http://go.microsoft.com/fwlink/?LinkId=146221)です。  
  
## <a name="configuration-logging"></a>構成のログ記録  
 構成プログラムでは、構成ログ ファイルが既定では BizTalk Server を実行しているコンピューターの一時ディレクトリに格納する詳細な情報が書き込まれます。 TEMP 環境変数によって指定されているフォルダーを確認するには、そのコンピューターでコマンド プロンプトを開き、次のコマンドを入力して、Enter キーを押します。  
  
 **echo %temp%**  
  
 構成ログ ファイルの内容は、実行された構成手順の概要と、構成処理中に発生した疑いのあるエラーに関する診断情報です。 構成エラーが発生した場合は、構成ログをメモ帳などのテキスト エディターで開くし、エラーの考えられる原因は、ログ ファイルを確認します。  
  
## <a name="troubleshooting-tools"></a>トラブルシューティング ツール  
 SQL Server プロファイラー、Filemon、または Regmon を使用して、構成エラーに関する追加情報を収集します。 参照してください[トラブルシューティングに使用するには、ツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)です。  
  
### <a name="configuration-fails-when-biztalk-and-sql-are-installed-on-separate-computers"></a>BizTalk と SQL が別々 のコンピューターにインストールすると、構成が失敗します。  
  
**問題**  
 エンタープライズ シングル サインオン (SSO) コンポーネントを構成しようとすると、次のようなエラーが発生して構成が失敗します。  
  
```
An error occurred while attempting to access the SSO database.  
Function: FieldInfoCreate  
```
  
 -または-  
  
```Failed to enable the Single Sign-On (SSO) Service (error code 0X800706BA)```  
  
**原因**    
 BizTalk Server と SQL Server が別々 のコンピューターにインストールされているし、構成の操作が Microsoft 分散トランザクション コーディネーター (MSDTC) トランザクションのコンテキストで実行される、MSDTC 機能は、上で公開する必要がある場合、これらのコンピューター間のネットワーク。 BizTalk Server と SQL Server を実行しているコンピューター間のネットワークで MSDTC 機能を使用できない場合は、このエラーは発生します。  
  
**解決策**    
使用して[MSDTC の問題のトラブルシューティング](https://support.microsoft.com/help/306843/how-to-troubleshoot-ms-dtc-firewall-issues)を BizTalk Server と SQL Server を実行しているコンピューター間のネットワークで MSDTC 機能を確認します。  
  
### <a name="antivirus-software-interferes-with-configuration-and-causes-configuration-failures"></a>ウイルス対策ソフトウェアの干渉によって構成エラーが発生する  
  
**問題**   
 ウイルス対策ソフトウェアが、構成プログラムがウイルスであると誤って判断ときに、BizTalk Server の構成が失敗します。  
  
**原因**  
 正当な (ウイルスではない) プログラムとして、BizTalk Server 構成プログラムを含めるにウイルス対策ソフトウェアが更新されていません。  
  
**解決方法**  
 構成プログラムの実行中に一時的にウイルス対策ソフトウェアを無効にするか、または正当な (ウイルスではない) プログラムとして、BizTalk Server 構成プログラムを認識するには、ウイルス対策プログラムを構成します。  
  
### <a name="configuration-fails-with-a-file-or-assembly-name-filenamedll-or-one-of-its-dependencies-was-not-found-error"></a>"ファイルまたはアセンブリ名 'FileName.dll'、またはその依存関係の 1 つが見つかりませんでした" というエラーによって構成が失敗する  
  
**問題**  
 構成プロセスで次のようなエラーが表示されます。  
  
 BizTalk システム アセンブリ"C:\Program \microsoft\biztalk Server 20xx\Microsoft.BizTalk.DefaultPipelines.dll 配置に失敗しました。 特定できない例外: ファイルまたはアセンブリ名 filename.dll、またはその依存関係の 1 つが見つかりませんでした"。  
  
**原因**  
 このエラーは、アカウントがネットワーク サービスの一時フォルダーに BizTalk Server を実行しているコンピューター上のアクセス許可を記述する場合に発生することができます。 構成時に、BizTalk Server 構成は、.NET アセンブリを BizTalk 管理データベースに展開するのに Windows Management Instrumentation (WMI) を使用します。 WMI は、BizTalk 管理データベースにこれらのアセンブリの展開中に、Network Service アカウントを偽装しますします。 そのため、Network Service アカウント必要がありますが書き込みアクセスを BizTalk Server を実行しているコンピューター上の一時フォルダーです。  
  
**解決方法**  
 ネットワーク サービス アカウントの BizTalk Server を実行しているコンピューター上の一時フォルダーへの書き込みアクセスを付与し、構成プログラムを再実行します。 TEMP 環境変数で指定されているフォルダーを確認するのには、コンピューターでコマンド プロンプトを開き、次のコマンドを入力および ENTER キーを押します。  
  
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
 .Mdf ファイルの場合、このエラーが発生する可能性がまたは .ldf ファイルが同じ名前の .mdf ファイルまたは .ldf ファイルを作成しようとして、BizTalk Server 構成プログラムを持つ SQL Server を実行しているコンピューターの \MSSQL\data フォルダーに既に存在します。 データベースに対して作成される .mdf ファイルおよび .ldf ファイルの名前は、BizTalk Server 構成プログラムに .mdf 拡張子と .ldf 拡張子を追加で指定されているデータベースの名前から派生します。  
  
**解決方法**  
 この問題を解決するには、以下のいずれかの方法を使用します。  
  
-   現在作成しているデータベースの名前と一致する名前を持つ .mdf ファイルや .ldf ファイルを削除します。  
  
-   SQL Server の \Program Files\Microsoft SQL Server\MSSQL\data フォルダーに既に存在する .mdf ファイルや .ldf ファイルの名前と一致しないデータベース名を選択します。  
  
### <a name="configuration-fails-on-a-domain-controller-when-specifying-local-accounts"></a>ドメイン コントローラーでローカル アカウントを指定すると構成が失敗する  
  
**問題**  
 ドメイン コント ローラーで、BizTalk Server 構成プログラムを実行するときに構成はローカル グループ (たとえば、BizTalk ホスト ユーザー グループ) を指定した場合、BizTalkServerApplication ホストか BizTalkIsolatedHost ホストのいずれかの失敗します。  
  
**原因**  
 ドメイン コントローラーでは、ローカル Windows グループが自動的にドメイン Windows グループとして処理されます (ドメイン コントローラーにはローカル Windows グループのようなものは存在しません)。 構成プログラムの実行中に、ホストのローカル Windows グループを指定した場合、グループ用の SQL Server ログオンを作成しようとするときの構成は失敗します。 サーバーがドメイン コントローラーに設定されていると、構成プログラムのローカル Windows グループ オプションが無効になりません。  
  
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
  
1.  SQL Server で開きます**Microsoft SQL Server** **Analysis Services**、順にクリック**分析マネージャー**です。  
  
2.  **分析マネージャー** ナビゲーション ペインをダブルクリックして、 **Analysis Servers** ノードを展開します。  
  
3.  リポジトリの接続文字列を編集して、選択すると、サーバーを右クリックして **リポジトリ接続文字列の編集**します。  
  
4.  **リポジトリ接続文字列の編集**  ダイアログ ボックスで、この文字列でサーバー名を確認しが正しくない場合、新しいコンピューター名を更新します。  
  
5.  次の場所に移動します。 <*インストール ディレクトリ*> \Program Files\Microsoft Analysis services \bin です。  
  
6.  右クリックし、 **Bin** フォルダー、およびクリック **共有とセキュリティ**します。 **Bin のプロパティ**  ダイアログ ボックスが表示されます。  
  
7.  **Bin のプロパティ** ダイアログ ボックスで、をクリックして、 **共有**  タブをクリックすると、すべてのオンライン分析処理 (OLAP) 管理者が完全なアクセス許可をこのフォルダーにあることを確認します。  
  
### <a name="artifacts-disappear-from-configuration-database-on-redeployment-of-assemblies-from-visual-studio"></a>Visual Studio からアセンブリを再展開構成データベースからアイテムが表示されなくなります  
  
**問題**  
 ときに、BizTalk Server プロジェクトを再展開、Visual Studio 内のプロジェクト レベルで再デプロイするプロジェクトの参照は、BizTalk Server MMC が更新されたときに表示されなくに表示されるプロジェクト内に含まれるすべての成果物です。  
  
**原因**  
 この問題の原因を示すために、ユーザーが Maps プロジェクトを再展開しようとしているサンプル BizTalk Server ソリューションに基づく例について考えてみます。 プロジェクトをコンパイルすると個々のアセンブリが生成されます。 次の図は、ユーザーが再展開を行う前のソリューションの状態を示しています。 アイテム間の関係は次のようになっています。  
  
-   Orch1、Orch2、Maps、Pipelines、および Schemas はプロジェクトです。  
  
-   Orch1 は Maps を参照し、Maps は Schemas を参照しています。  
  
-   Orch2 は Schemas を参照しています。  
  
-   Pipelines は Schemas を参照しています。  
  
![bcd_ExistingBizTalkServerSolutionc](../install-and-config-guides/media/bcd_ExistingBizTalkServerSolutionc.gif)  
  
ユーザーが Visual Studio の既定のプロジェクト設定を使用して Maps プロジェクトを再展開すると、次の図のように、Orch1、Orch2、および Pipeline の各アイテムが消えてしまいます。  
  
![bcd_BizTalkSolutionWLostArtifactsc](../install-and-config-guides/media/bcd_BizTalkSolutionWLostArtifactsc.gif)  
  
 Maps の再展開は、現在展開されている Maps.dll アセンブリの展開を解除して、新しい Maps.dll ファイルを展開する、2 段階のプロセスです。 Visual Studio は、再展開プロセスの一部として自動的に次の手順を実行します。  
  
> [!NOTE]
>  前の文は厳密には正しくありません。というのも、これらの手順は Visual Studio で常に行われるものなので、正しく行われているかどうかを意識することはありません。  
  
 重要な点は、BizTalk Server アセンブリを展開解除するために Visual Studio すべてのアセンブリをアセンブリに依存している展開フラグが設定されている展開を解除します。 この例で言うと、再展開の最初の展開解除の手順を実行するには、BizTalk Server が Orch1.dll (Maps.dll に依存している) の展開を解除する必要があります。 Maps.dll の展開を解除する、Visual Studio の展開も解除 Schemas.dll (展開フラグの設定があると仮定)。 Schemas.dll の展開を解除するには、Orch2.dll と Pipelines.dll (いずれも Schemas.dll に依存している) の展開を解除する必要があります。  
  
 問題がある点で、Visual Studio は Maps.dll とそれが依存するアセンブリを再配置。 この場合は Schemas.dll します。 そのため、ユーザーが BizTalk Server MMC を更新すると、Orch1、Orch2、および Pipeline の各アセンブリが消えたように見えますが、Maps.dll と Schemas.dll は引き続き表示されます。  
  
**解決方法**  
 メイン プロジェクト (他のプロジェクトを参照しているプロジェクト) に対して次の手順を実行します。  
  
1.  ソリューション エクスプローラーで、ソリューション ノードを右クリックします。  
  
2.  クリックして **プロパティ** を開くには、 **ソリューション プロパティ ページ**  ダイアログ ボックス。  
  
3.  クリックして **構成プロパティ**, 、 をクリックし、 **構成**します。  
  
4.  クリア、 **展開** 参照先のプロジェクトのチェック ボックスです。  
  
5.  ソリューション エクスプローラーで、新しいソリューション レベルの展開を実行します。 これを行うには、ソリューション ノードを右クリックし、をクリックし、 **ソリューションの配置**します。  
  
### <a name="supported-virtual-directory-types"></a>サポートされている仮想ディレクトリのタイプ  
 関連付けられている仮想ディレクトリが型の場合にのみ、MSI のエクスポートを実行しようと、オーケストレーションから Web サービスを参照するとエクスポート操作が成功は **IIsWebVirtualDir** または **IIsWebDirectory**します。 **IIsWebVirtualDir** と **IIsWebDirectory** IIS メタベースに表示されるノード型です。 **IIsWebVirtualDir** の仮想ディレクトリ、 **パス** 絶対ファイル フォルダーを指すプロパティです。 **IIsWebDirectory** なしの仮想ディレクトリ、 **パス** プロパティを別のサブフォルダーでは通常、相対ファイル フォルダーに参照および **IIsWebVirtualDir** または **IIsWebDirectory** ノードです。 メタベース階層でフォルダーを表すものとしてはこの 2 つのタイプが一般的です。  
  
 型の仮想ディレクトリ **IIsConfigObject** はサポートされていませんし、MSI のエクスポートはここでは失敗します。 **IIsConfigObject** が BizTalk Server が正しく処理されないか、有効なノード型では予期しないメタベース ノード タイプか、正しく作成されていない (およびしたがって無効な) メタベース エントリを示す値。 このような状況では、BizTalk Server によって、次のようなエラー メッセージが示されます。 種類 IIsConfigObject 予期しないディレクトリ エントリ"IIS://LM/W3SVC/1/ROOT/BadVdir/"です。  
  
### <a name="unable-to-view-group-information-after-removing-stale-logons"></a>古いログオンを削除するとグループ情報を表示できなくなる  
  
**問題**  
 構成中に古いログオンを見つけて削除すると、グループ情報を表示できなくなる場合があります。  
  
**原因**  
 これは既知の構成の問題です。  
  
**解決方法**  
 Host Windows グループのログオンを削除して再構成すると解決する場合があります。 それでもグループ情報を表示できない場合は、マイクロソフト製品サポートにご連絡ください。  
  
### <a name="cannot-change-computer-name-after-biztalk-server-is-installed"></a>BizTalk Server のインストール後にコンピューター名を変更できない  
  
**問題**  
 BizTalk Server を実行しているコンピューター上のコンピューター名を変更して、(リブート)、コンピューターでは、エラー メッセージを再起動するときに発生します。  
  
**原因**  
 SQL Server は、BizTalk Server が BizTalk Server をインストールおよび構成したら、コンピューター名の変更をサポートしていないため、コンピューター名の変更をサポートしていません。  
  
**解決方法**  
 BizTalk Server のインストール後はコンピューター名を変更しないことをお勧めします。  
  
### <a name="known-issues-with-enterprise-single-sign-on"></a>エンタープライズ シングル サインオンに関する既知の問題  
 ここでは、エンタープライズ シングル サインオン (SSO) に関係する可能性があるセットアップと構成の問題について説明します。  
  
##### <a name="entsso-service-fails-to-start"></a>ENTSSO サービスを開始できません。  
  
**問題**  
 ENTSSO サービスを開始できません。  
  
**原因**  
 ENTSSO サービスが有効な SSO 管理者アカウントで実行されていない場合、サービスを開始できません。  
  
**解決方法**  
 有効な SSO 管理者アカウントを ENTSSO サービスに指定して、サービス コントロール マネージャー (SCM) スナップインからサービスを再起動します。  
  
##### <a name="biztalk-services-dependent-on-the-enterprise-single-sign-on-service-entsso-fail-to-start-after-a-reboot"></a>再起動後、エンタープライズ シングル サインオン サービス (ENTSSO) に依存する BizTalk Services が起動しない  
  
**問題**  
 BTSSvc$BizTalkServerApplication はエンタープライズ シングル サインオン サービス (ENTSSO) と依存関係があり、リブート後の起動中にタイムアウトすることがあります。  
  
**原因**  
 エンタープライズ シングル サインオン サービスは、起動に約 3 分かかる場合があります。  
  
**解決方法**  
 "BizTalk Service BizTalk グループ: BizTalkServerApplication" サービスを、スタートアップ オプションの種類を [自動 (遅延スタート)] として構成します。 これにより、すべての自動サービスのスタートアップ ルーチン完了後に、このサービスが開始されます。  
  
##### <a name="cannot-access-an-affiliate-application"></a>関連アプリケーションにアクセスできない  
  
**問題**  
 関連するアプリケーションの管理者アカウントが有効でない場合、エンタープライズ シングル サインオン サービスはこの関連アプリケーションを無効にします。  
  
**原因**  
 SSO アプリケーションの管理者アカウントが無効です。  
  
**解決方法**  
 関連アプリケーションを作成する前に、SSO アプリケーションの管理者アカウントが有効なことを確認します。 関連アプリケーションを使用するには、そのアプリケーションを有効にする必要があります。  
  
##### <a name="rpc-error-occurs-when-connecting-to-a-client-computer"></a>クライアント コンピューターに接続するときに、RPC エラーが発生します。  
  
**問題**  
 などのコマンドを実行すると**ssomanage-displayapp** *< applicationname\>* コンピューター、情報を取得するリモート SSO サーバーに接続しようとしましたここで、が表示されたら、。次のエラー: エラー: 0x800706BA: RPC サーバーは使用できません。  
  
**原因**  
 このエラーは、間違ったサーバー情報を指定した場合、またはリモート サーバーで SSO サービスを利用できない場合に発生します。  
  
**解決方法**  
  
-   手順に従います[SSO Server を設定](../core/how-to-set-the-sso-server.md)正しい SSO サーバーに接続しているかどうかを確認します。  
  
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
  
1.  マスター シークレットをバックアップします。 参照してください[マスター シークレットをバックアップ](../core/how-to-back-up-the-master-secret.md)です。  
  
2.  エンタープライズ シングル サインオン サービスを停止します。  
  
3.  サービス アカウントを変更します。  
  
4.  SSO を再起動します。破損したシークレットに関するイベント ログのエラーは一切無視します。  
  
5.  マスター シークレットを復元します。 参照してください[マスター シークレットを復元](../core/how-to-restore-the-master-secret.md)です。  
  
### <a name="custom-action"></a>カスタム アクション  
 このトピックでは、Windows Server ロゴ プログラムの BizTalk Server の認定に関する詳細を提供します。 BizTalk Server セットアップ操作時に次のカスタム動作を実行することが可能です。  
  
|カスタム アクション|Description|  
|-------------------|-----------------|  
|ReadComplusData|カスタム COM+ テーブルを読み取り、XML ドキュメントを作成して、Complus_XML_Data プロパティに保存します。|  
|SchedXmlConfig|RFID データを持つコンピューターを構成するために使用されます。|  
|CheckBaseEDI|古いバージョンの EDI の存在を確認します。|  
|CheckMQSeries|MQSeries の存在を確認します。|  
|CheckNET30Vista|WCF の存在を確認します。|  
|CheckWSSV3SP1|Windows SharePoint Services 3.0 SP1 の存在を確認します。|  
|CheckWSSV4|Windows SharePoint Services 4 の存在を確認します。|  
|GetFrameworkPath|Microsoft .NET Framework 4 および 2.0 のインストール パスを保持するインストーラーのプロパティをインストーラーに設定します。|  
|Set_BAMClientExcelDir|Microsoft Office ライブラリ パスを保持するプロパティをインストーラーに設定するための Excel アプリケーション オブジェクトを作成します。|  
|Set_CurrentUser|現在のユーザーのドメイン\ユーザー名の情報を設定します。|  
|ViewInstallGuide|インストール ソース ディレクトリから BizTalk Server インストール ガイドを起動します。|  
|CA_CheckSTSLanguage|WSS に設定されている言語と BizTalk に設定されている言語が同じである場合に、STS_Language_Property プロパティを設定します。|  
|CA_CleanupRegistry|BizTalk Server をアンインストールすると、BizTalk Server 構成時に作成されたレジストリ エントリがクリーンアップされます。|  
|CA_CleanupRegistry_OldProducts|古いバージョンの BizTalk Server に属し、BizTalk Server の新しいインストールに必要でないレジストリ エントリをクリーンアップします。|  
|CA_RemovePatches|BizTalk Server のアンインストール時に Microsoft BizTalk Server 更新プログラムを削除します。|  
|CA_ResolveWellKnownNames|既知の名前を持つインストーラーのプロパティを作成し、作成したプロパティに対応する SID を割り当てます。|  
|CA_SaveTargetVSVersionToRegistry|サポートされている Visual Studio のバージョンの値を TargetVSVersion_Property プロパティに設定します。|  
|CA_StopServices|IISAdmin サービス、ルール エンジン更新プログラム サービス、および EDI サブシステム サービスを停止します。|  
|CleanupUsersKeys|HKEY_CURRENT_USER レジストリ キーから BizTalk Server 関連エントリを削除します。|  
|DevEnvRunning|Visual Studio が実行中かどうかを確認します。|  
|ValidateINSTALLDIR|BizTalk Server のインストール ディレクトリ形式を確認します。|  
|StartHostInstances|BizTalk Server ホスト インスタンスを開始します。|  
|StopHostInstances|BizTalk Server ホスト インスタンスを停止します。|  
|MQSUnConfig|MQSeries エージェントの構成を解除するために MQSeries 構成ウィザードを起動します。|  
|LaunchConfigFmk|BizTalk Server 構成ウィザードを起動します。|  
|CHKASPNET|ASP.NET のインストール状態を確認します。|  
|CHKIIS|IIS のインストール状態を確認します。|  
|TBExpired|BizTalk Server の TimeBomb の有効期限が終了しているかどうかを確認します。|  
|BrandSKU|SKU のインストールに依存する BizTalk Server の timebomb の値を更新します。|  
|CA_ERROR|インストール エラーを返します。|  
|InstallComplus|Complus アプリケーションとコンポーネントをインストールします。|  
|BAM_Add_Perf_Silent|BAM のパフォーマンス カウンターをインストールします。|  
|RegsvcsApplicationDeployment|BizTalk 展開 COM+ アプリケーション DLL に対して Regsvcs.exe (.NET サービス インストール ツール) を実行します。|  
|RegsvcsDeployment|DLL に対して Regsvcs.exe を実行します。|  
|RegsvcsMQSAdapter|DLL に対して Regsvcs.exe を実行します。|  
|RegsvcsSQLAdapter|DLL に対して Regsvcs.exe を実行します。|  
|WMI_Add_MSBTS_Silent|BizTalk Server の名前空間とクラスを WMI に登録します。|  
|LaunchConfigFmk_SlashUP|BizTalk Server の構成を解除します。|  
|CleanupComplus|Complus アプリケーションとコンポーネントをアンインストールします。|  
|RemoveSKU|BizTalk Server TimeBomb データを削除します。|  
|BAM_Remove_Perf|BAM のパフォーマンス カウンターをアンインストールします。|  
|LoadBTSCounters|BizTalk Server パフォーマンス カウンターを読み込みます。|  
|RegisterBtprojExtn|BizTalk プロジェクト ファイル (.btproj) の拡張子を登録します。|  
|UnRegisterBtprojExtn|BizTalk プロジェクト ファイル (.btproj) の拡張子を登録解除します。|  
|UnRegsvcsApplicationDeployment|BizTalk Server のアンインストール時に、特定の DLL に対して Regsvcs.exe を実行します。|  
|UnRegsvcsDeployment|BizTalk Server のアンインストール時に、特定の DLL に対して Regsvcs.exe を実行します。|  
|UnRegsvcsMQSAdapter|BizTalk Server のアンインストール時に、特定の DLL に対して Regsvcs.exe を実行します。|  
|UnRegsvcsSQLAdapter|BizTalk Server のアンインストール時に、特定の DLL に対して Regsvcs.exe を実行します。|  
|UnloadBTSCounters|BizTalk Server パフォーマンス カウンターをアンロードします。|  
|WMI_Remove_MSBTS|WMI から BizTalk Server 名前空間を削除します。|  
|RegisterComsvcs|comsvcs.dll に対して regsvr32.exe をサイレント実行します。|  
|DevenvSetupUninstall|DevEnv.exe /Setup/resetskippkgs を実行します。|  
|RollbackComplus|Complus アプリケーションとコンポーネントのインストールをロールバックします。|  
|ResRegsvcsMQSAdapter|指定されたバイナリで regsvcs.exe を実行します。|  
|ResRegsvcsSQLAdapter|指定されたバイナリで regsvcs.exe を実行します。|  
|RestoreRegsvcsApplicationDeployment|フレームワークのパスを Microsoft.BizTalk.ApplicationDeployment.Engine.dll に付加します。|  
|RestoreRegsvcsDeployment|フレームワークのパスを Microsoft.BizTalk.ApplicationDeployment.Engine.dll に付加します。|  
|BrandSKURollback|インストール エラーが発生した場合、登録した SKU 情報をロールバックします。|  
|CA_RestartServices_rollback|停止したサービスを再起動します。|  
|RemoveSKURollback|レジストリの SKU 値を更新します。|  
|BAM_Res_Perf_Silent|サイレント インストール時に、Microsoft.BizTalk.Bam.EventObservation.dll を BAM パフォーマンス カウンター DLL として登録します。|  
|BAM_Rollback_Perf|BAM パフォーマンス カウンター DLL としての Microsoft.BizTalk.Bam.EventObservation.dll の登録を解除します。|  
|RBKRegsvcsMQSAdapter|指定されたバイナリに対して regsvcs.exe を実行します。|  
|RBKRegsvcsSQLAdapter|指定されたバイナリに対して regsvcs.exe を実行します。|  
|RestoreBTSCounters|パフォーマンス カウンターの .ini ファイル名を使用してプロパティを復元します。|  
|RollbackBTSCounters|unlodctr BTSSvc.3.0 コマンドを実行します。|  
|RollbackRegsvcsApplicationDeployment|[FrameworkPath] 設定&#124;[失敗したインストール シナリオの INSTALLDIR]Microsoft.BizTalk.ApplicationDeployment.Engine.dll します。|  
|RollbackRegsvcsDeployment|アンインストール/ロールバック シナリオで regsvcs.exe を起動します。|  
|WMI_Restore_MSBTS_Silent|mofcomp を呼び出して WMI スキーマを登録します。|  
|WMI_Rollback_MSBTS|WMI から BizTalk Server 名前空間を削除します。|  
|CA_RestartServices_commit|停止したサービスを再開します。|  
|DevenvSetup|BizTalk Server のインストール プロセスおよびアンインストール プロセスの両方で DevEnv.exe /Setup /resetskippkgs を実行します。|  
|ExecXmlConfig|RFID 関連データの machine.config で構成を変更するために使用されます。|  
|ExecXmlConfigRollback|RFID 関連データの machine.config で構成を変更するために使用されます。|  
  
#### <a name="running-biztalk-components"></a>BizTalk コンポーネントの実行  
 次の表は、管理者特権または使用可能な最高の特権を使用して実行する必要のある BizTalk コンポーネントの一覧です。  
  
|フォルダー パス|ファイル名|ユーザー特権|  
|-----------------|---------------|---------------------|  
|\Program Files (x86)\Common Files\Microsoft shared\Help 9\Microsoft Document Explorer 2008|Install.exe|使用可能な最高の特権|  
|\Program Files (x86)\Microsoft BizTalk Server *your version*|BTSHatApp.exe|使用可能な最高の特権|  
|\Program Files (x86)\Microsoft BizTalk Server *your version*|BTSMMCLauncher.exe|使用可能な最高の特権|  
|\Program Files (x86)\Microsoft BizTalk Server *your version*|BtsWcfServicePublishingWizard.exe|使用可能な最高の特権|  
|\Program Files (x86)\Microsoft BizTalk Server *your version*|BTSWebSvcWiz.exe|使用可能な最高の特権|  
|\Program Files (x86)\Microsoft BizTalk Server *your version*|Configuration.exe|使用可能な最高の特権|  
|\Program Files (x86)\Microsoft BizTalk Server *your version*|REDeployWiz.exe|使用可能な最高の特権|  
|\Program Files (x86)\Microsoft BizTalk Server *your version*|Setup.exe|管理者特権|  
|\Program Files (x86)\Microsoft BizTalk Server *your version*\XSD Schema\EDI|MicrosoftEdiXSDTemplates.exe|自己展開形式 .exe ファイル|  
|\Program Files (x86)\Microsoft UDDI Services\config|Configuration .exe|管理者特権|  
|\Program Files\ Microsoft BizTalk RFID\bin|BTSMMCLauncher.exe|使用可能な最高の特権|  
|\Program Files\Microsoft BizTalk RFID\BREConfi guration|Configuration .exe|管理者特権|  
