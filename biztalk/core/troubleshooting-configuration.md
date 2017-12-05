---
title: "構成のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 902e591a-4ff4-4053-b329-0c022f44999a
caps.latest.revision: "37"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e523c5c992ea422e6fe81f3c0d948db7007bcdb1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="troubleshooting-configuration"></a>構成のトラブルシューティング
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成プログラムは、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] を実行する 1 つ以上のコンピューター上にデータベースを作成し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が使用するテーブル、ロール、およびストアド プロシージャをそのデータベースに格納して、実行時に使用される .NET アセンブリを BizTalk 管理データベースに展開します。  
  
 このセクションでは、構成エラーを解決するためのトラブルシューティング手法について説明します。 一般的な構成の問題とその解決方法の一覧も含まれています。  
  
## <a name="configuration-logging"></a>構成のログ記録  
 構成プログラムが既定で実行しているコンピューターの一時ディレクトリに格納されている構成ログ ファイルに詳細な情報を書き込みます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 TEMP 環境変数によって指定されているフォルダーを確認するには、そのコンピューターでコマンド プロンプトを開き、次のコマンドを入力して、Enter キーを押します。  
  
 **エコー %temp%**  
  
 構成ログ ファイルの内容は、実行された構成手順の概要と、構成処理中に発生した疑いのあるエラーに関する診断情報です。 構成エラーが発生した場合メモ帳などのテキスト エディターでは、構成ログを開くし、エラーの考えられる原因のログ ファイルを確認します。  
  
## <a name="troubleshooting-tools"></a>トラブルシューティング ツール  
 SQL Server プロファイラー、Filemon、または Regmon を使用して、構成エラーに関する追加情報を収集します。 これらのツールの詳細については、次を参照してください。[トラブルシューティングに使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)です。  
  
## <a name="known-issues"></a>既知の問題  
  
#### <a name="configuration-fails-when-biztalk-server-and-sql-server-are-installed-on-separate-computers"></a>BizTalk Server と SQL Server が別のコンピューターにインストールされていると構成が失敗する  
  
##### <a name="problem"></a>問題  
 エンタープライズ シングル サインオン (SSO) コンポーネントを構成しようとすると、次のようなエラーが発生して構成が失敗します。  
  
 SSO データベースへのアクセスを試みているときにエラーが発生しました。  
  
 関数: FieldInfoCreate  
  
 -または-  
  
 シングル サインオン (SSO) サービスの有効化に失敗しました (エラー コード 0X800706BA)  
  
##### <a name="cause"></a>原因  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] が別のコンピューターにインストールされている場合、構成操作は分散トランザクション コーディネーター (MSDTC) トランザクションのコンテキストで行われます。このため、それらのコンピューターの間のネットワークで MSDTC 機能を利用可能にする必要があります。 かどうか MSDTC 機能は使用できませんを実行しているコンピューター間でネットワーク経由で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]し、このエラーが発生することができます。  
  
##### <a name="resolution"></a>解決策  
 手順に従います[MSDTC の問題のトラブルシューティング](../core/troubleshooting-problems-with-msdtc.md)を実行しているコンピューター間のネットワークで MSDTC 機能を確認[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。  
  
#### <a name="antivirus-software-interferes-with-configuration-and-causes-configuration-failures"></a>ウイルス対策ソフトウェアの干渉によって構成エラーが発生する  
  
##### <a name="problem"></a>問題  
 ウイルス対策ソフトウェアによって構成プログラムが誤ってウイルスと判断されると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成が失敗します。  
  
##### <a name="cause"></a>原因  
 含める、ウイルス対策ソフトウェアが更新されていない、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成プログラムが正当な (ウイルスではない) プログラムです。  
  
##### <a name="resolution"></a>解決策  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成プログラムが正当な (ウイルスではない) プログラムとして認識されるようにウイルス対策プログラムを構成するか、構成プログラムを実行する間、ウイルス対策ソフトウェアを一時的に無効にします。  
  
#### <a name="configuration-fails-with-a-file-or-assembly-name-filenamedll-or-one-of-its-dependencies-was-not-found-error"></a>"ファイルまたはアセンブリ名 'FileName.dll'、またはその依存関係の 1 つが見つかりませんでした" というエラーによって構成が失敗する  
  
##### <a name="problem"></a>問題  
 構成プロセスで次のようなエラーが表示されます。  
  
 BizTalk システム アセンブリ "C:\Program Files\Microsoft\" を展開できませんでした。  
  
 BizTalk Server 2009\Microsoft.BizTalk.DefaultPipelines.dll です。 [未指定]  
  
 例外: ファイルまたはアセンブリ名 filename.dll、またはのいずれかの  
  
 依存関係の 1 つが見つかりませんでした。 ファイルまたはアセンブリ名 FileName.dll、または  
  
 その依存関係の 1 つが見つかりませんでした。  
  
##### <a name="cause"></a>原因  
 このエラーは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を実行しているコンピューターの一時フォルダーに対する書き込みアクセス許可がネットワーク サービス アカウントにない場合に発生します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成では、構成の間に .NET アセンブリを BizTalk 管理データベースに展開するために Windows Management Instrumentation (WMI) が使用されます。 WMI はこれらのアセンブリを BizTalk 管理データベースに展開する際にネットワーク サービス アカウントを借用するため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を実行しているコンピューターの一時フォルダーに対する書き込みアクセス許可がネットワーク サービス アカウントに必要です。  
  
##### <a name="resolution"></a>解決策  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を実行しているコンピューターの一時フォルダーに対する書き込みアクセス許可をネットワーク サービス アカウントに与えてから、再度構成プログラムを実行します。 TEMP 環境変数で指定されているフォルダーを特定するのには、コンピューターでコマンド プロンプトを開き、次のコマンドを入力およびし、ENTER キーを押します。  
  
```  
echo %TEMP%  
```  
  
#### <a name="configuration-of-the-group-fails-if-the-netbios-name-of-the-computer-running-sql-server-exceeds-15-characters"></a>SQL Server を実行しているコンピューターの NetBIOS 名が 15 文字より長いとグループの構成が失敗する  
  
##### <a name="problem"></a>問題  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のグループの構成が失敗して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成ログに次のようなエラーが表示されます。  
  
 2006-08-29 23:54:00:0902 [WARN] AdminLib GetBTSMessage: hrErr 80070547; を =  
  
 Msg=ドメイン コントローラーから構成情報を読み取れま  
  
 せんでした。コンピューターが有効ではないか、ま  
  
 たはアクセスが拒否されました。  
  
##### <a name="cause"></a>原因  
 この問題は、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] を実行しているコンピューターの NetBIOS 名が 15 文字より長い場合に発生します。 NetBIOS 名が 15 文字より長いと、Windows が NetBIOS 名を 15 文字に切り詰めるため、NetBIOS 名がそのコンピューターの完全修飾ドメイン名 (FQDN) や DNS 名の最初の部分に一致しなくなります。 NetBIOS 名がコンピューターの FQDN の最初の部分に一致しないと、グループの構成は失敗します。  
  
##### <a name="resolution"></a>解決策  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] を実行しているコンピューターの NetBIOS 名を 15 文字以内の名前に変更して、再度構成を実行します。  
  
> [!NOTE]
>  コンピューターの名前を変更した場合は、コンピューターを再起動する必要があります。  
  
#### <a name="configuration-fails-if-a-sql-server-database-file-that-has-the-same-name-as-the-specified-database-already-exists-in-the-sql-server-data-folder"></a>指定したデータベースと同じ名前の SQL Server データベース ファイルが SQL Server のデータ フォルダーに既に存在していると構成が失敗する  
  
##### <a name="problem"></a>問題  
 次のようなエラーが発生して構成が失敗します。  
  
 BAM データベースを設定できませんでした。  
  
 'BAMPrimaryImport' のログインで要求されたデータベースを開けません。  
  
 ログインは失敗します。 ユーザーのログオンに失敗しました '*biztalk \biztalkuser*'  
  
##### <a name="cause"></a>原因  
 このエラーは、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] を実行しているコンピューターの \MSSQL\data フォルダーに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成プログラムが作成しようとしている .mdf ファイルまたは .ldf ファイルと同じ名前の .mdf ファイルまたは .ldf ファイルが既に存在する場合に発生します。 データベースのために作成される .mdf ファイルと .ldf ファイルの名前は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成プログラムで指定したデータベースの名前に .mdf 拡張子と .ldf 拡張子を追加して生成されます。  
  
##### <a name="resolution"></a>解決策  
 この問題を解決するには、以下のいずれかの方法を使用します。  
  
-   現在作成しているデータベースの名前と一致する名前を持つ .mdf ファイルや .ldf ファイルを削除します。  
  
-   SQL Server の \Program Files\Microsoft SQL Server\MSSQL\data フォルダーに既に存在する .mdf ファイルや .ldf ファイルの名前と一致しないデータベース名を選択します。  
  
#### <a name="configuration-fails-on-a-domain-controller-when-specifying-local-accounts"></a>ドメイン コントローラーでローカル アカウントを指定すると構成が失敗する  
  
##### <a name="problem"></a>問題  
 ドメイン コントローラーで [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成プログラムを実行しているときに、BizTalkServerApplication ホストか BizTalkIsolatedHost ホストのいずれかにローカル グループ (BizTalk ホスト ユーザー グループなど) を指定すると、構成が失敗します。  
  
##### <a name="cause"></a>原因  
 ドメイン コントローラーでは、ローカル Windows グループが自動的にドメイン Windows グループとして処理されます (ドメイン コントローラーにはローカル Windows グループのようなものは存在しません)。 構成プログラムの実行中にホストにローカル Windows グループを指定した場合、そのグループに対して [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] ログオンを作成しようとすると構成が失敗します。 サーバーがドメイン コントローラーに設定されていると、構成プログラムのローカル Windows グループ オプションが無効になりません。  
  
##### <a name="resolution"></a>解決策  
 構成中に作成されるホストに対してはドメイン グループを指定します。  
  
#### <a name="configuration-fails-to-create-sql-server-analysis-database-if-the-sql-server-has-been-renamed"></a>SQL サーバーの名前が変更されていると構成プログラムが SQL Server 分析データベースの作成に失敗する  
  
##### <a name="problem"></a>問題  
 SQL Server 分析サーバーをインストールしたコンピューターの名前を変更した場合、新しい SQL Server 分析データベースを作成しようとすると構成プログラムが失敗して、次のようなエラーが生成されます。  
  
 リポジトリに接続できません。  
  
 分析サーバー:\<マシン名\>  
  
 エラー:  
  
 '\\\\< マシン名\>\MsOLAPRepository$\msmdrep.mdb' は有効なパスではありません。  
  
 パス名のスペルが正しいこと、および  
  
 ファイルが存在するサーバーに接続していることを確認してください。  
  
##### <a name="cause"></a>原因  
 SQL Server 分析サーバーをインストールしたコンピューターの新しい名前を構成プログラムが特定できません。  
  
##### <a name="resolution"></a>解決策  
 以下の手順を手動で実行し、分析サーバーを新しいコンピューター名で更新します。  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server**、 をポイント**Analysis Services**をクリックして**分析マネージャー**です。  
  
2.  **分析マネージャー**ナビゲーション ペインをダブルクリックして、 **Analysis Servers**ノードを展開します。  
  
3.  クリックして、編集するリポジトリ接続文字列を使用してサーバーを右クリックして**リポジトリ接続文字列の編集**です。  
  
4.  **リポジトリ接続文字列の編集** ダイアログ ボックスで、この文字列内でサーバー名を確認しが正しくない場合、新しいコンピューター名を更新します。  
  
5.  次の場所に移動: \<*インストール ディレクトリ*\>\Program Files\Microsoft Analysis services \bin です。  
  
6.  右クリックし、 **Bin**フォルダー、およびクリック**共有とセキュリティ**です。 **Bin のプロパティ** ダイアログ ボックスが表示されます。  
  
7.  **Bin のプロパティ**ダイアログ ボックスで、をクリックして、**共有**タブをすべてのオンライン分析処理 (OLAP) 管理者が完全なアクセス許可をこのフォルダーにあることを確認します。  
  
#### <a name="artifacts-disappear-from-configuration-database-on-redeployment-of-assemblies-from-visual-studio"></a>Visual Studio からアセンブリを再展開すると構成データベースからアイテムが消える  
  
##### <a name="problem"></a>問題  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 内で [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトをプロジェクト レベルで再展開すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MMC を更新したときに、再展開したプロジェクトを参照しているプロジェクトに含まれているすべてのアイテムが消えたように見えます。  
  
##### <a name="cause"></a>原因  
 この問題の原因を示すために、ユーザーが Maps プロジェクトを再展開しようとしているサンプル BizTalk Server ソリューションに基づく例について考えてみます。 プロジェクトをコンパイルすると個々のアセンブリが生成されます。 次の図は、ユーザーが再展開を行う前のソリューションの状態を示しています。 アイテム間の関係は次のようになっています。  
  
-   Orch1、Orch2、Maps、Pipelines、および Schemas はプロジェクトです。  
  
-   Orch1 は Maps を参照し、Maps は Schemas を参照しています。  
  
-   Orch2 は Schemas を参照しています。  
  
-   Pipelines は Schemas を参照しています。  
  
 ![](../core/media/bcd-existingbiztalkserversolutionc.gif "bcd_ExistingBizTalkServerSolutionc")  
  
 ユーザーが Visual Studio の既定のプロジェクト設定を使用して Maps プロジェクトを再展開すると、次の図のように、Orch1、Orch2、および Pipeline の各アイテムが消えてしまいます。  
  
 ![](../core/media/bcd-biztalksolutionwlostartifactsc.gif "bcd_BizTalkSolutionWLostArtifactsc")  
  
 Maps の再展開は、現在展開されている Maps.dll アセンブリの展開を解除して、新しい Maps.dll ファイルを展開する、2 段階のプロセスです。 Visual Studio は、再展開プロセスの一部として自動的にこれらの手順を実行します。  
  
> [!NOTE]
>  前の文は厳密には正しくありません。というのも、これらの手順は Visual Studio で常に行われるものなので、正しく行われているかどうかを意識することはありません。  
  
 ここで重要な点は、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] が BizTalk Server アセンブリの展開を解除するためには、そのアセンブリに依存しているすべての (展開フラグが設定されている) アセンブリの展開を解除しなければならないということです。 この例で言うと、再展開の最初の展開解除の手順を実行するには、BizTalk Server が Orch1.dll (Maps.dll に依存している) の展開を解除する必要があります。 Maps.dll の展開を解除する際、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] は Schemas.dll の展開も解除します (展開フラグが設定されている場合)。 Schemas.dll の展開を解除するには、Orch2.dll と Pipelines.dll (いずれも Schemas.dll に依存している) の展開を解除する必要があります。  
  
 問題が存在する[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]Maps.dll とそれが依存するアセンブリのみを再配置: この場合は Schemas.dll します。 そのため、ユーザーが BizTalk Server MMC を更新すると、Orch1、Orch2、および Pipeline の各アセンブリが消えたように見えますが、Maps.dll と Schemas.dll は引き続き表示されます。  
  
##### <a name="resolution"></a>解決策  
 メイン プロジェクト (他のプロジェクトを参照しているプロジェクト) に対して次の手順を実行します。  
  
1.  ソリューション エクスプローラーで、ソリューション ノードを右クリックします。  
  
2.  をクリックして**プロパティ**を開くには、**ソリューション プロパティ ページ** ダイアログ ボックス。  
  
3.  をクリックして**構成プロパティ**、クリックして**構成**です。  
  
4.  クリア、**展開**参照プロジェクトのチェック ボックスです。  
  
5.  ソリューション エクスプローラーで、新しいソリューション レベルの展開を実行します。 これを行うには、ソリューション ノードを右クリックし、をクリックして**ソリューションの配置**です。  
  
#### <a name="supported-virtual-directory-types"></a>サポートされている仮想ディレクトリのタイプ  
 関連付けられている仮想ディレクトリが型の場合にのみエクスポート操作は成功 MSI のエクスポートを実行しようと、オーケストレーションから Web サービスを参照する、ときに**IIsWebVirtualDir**または**IIsWebDirectory**. **IIsWebVirtualDir**と**IIsWebDirectory** IIS メタベースに表示するノード型です。 **IIsWebVirtualDir**の仮想ディレクトリ、**パス**絶対ファイル フォルダーを指すプロパティです。 **IIsWebDirectory**なしの仮想ディレクトリ、**パス**プロパティ別のサブフォルダーでは通常、相対ファイル フォルダーを参照および**IIsWebVirtualDir**または**IIsWebDirectory**ノード。 メタベース階層でフォルダーを表すものとしてはこの 2 つのタイプが一般的です。  
  
 型の仮想ディレクトリ**IIsConfigObject**はサポートされていませんし、MSI のエクスポートはここでは失敗します。 **IIsConfigObject**が BizTalk Server が正しく処理されないか、有効なノード型では予期しないメタベース ノード タイプか、正しく作成されていない (およびしたがって無効な) メタベース エントリを示す値。 このような状況では、BizTalk Server によって、次のようなエラー メッセージが示されます。 種類 IIsConfigObject の予期しないディレクトリ エントリ"IIS://LM/W3SVC/1/ROOT/BadVdir/"です。  
  
#### <a name="unable-to-view-group-information-after-removing-stale-logons"></a>古いログオンを削除するとグループ情報を表示できなくなる  
  
##### <a name="problem"></a>問題  
 構成中に古いログオンを見つけて削除すると、グループ情報を表示できなくなる場合があります。  
  
##### <a name="cause"></a>原因  
 これは既知の構成の問題です。  
  
##### <a name="resolution"></a>解決策  
 Host Windows グループのログオンを削除して再構成すると解決する場合があります。 それでもグループ情報を表示できない場合は、マイクロソフト製品サポートにご連絡ください。  
  
##### <a name="cannot-change-computer-name-after-biztalk-server-is-installed"></a>BizTalk Server のインストール後にコンピューター名を変更できない  
  
###### <a name="problem"></a>問題  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を実行しているコンピューターのコンピューター名を変更し、コンピューターを再起動 (リブート) すると、エラー メッセージが表示される場合があります。  
  
###### <a name="cause"></a>原因  
 SQL Server はコンピューター名の変更をサポートしていないため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がインストールおよび構成された後のコンピューター名の変更はサポートされません。  
  
###### <a name="resolution"></a>解決策  
 BizTalk Server のインストール後はコンピューター名を変更しないことをお勧めします。