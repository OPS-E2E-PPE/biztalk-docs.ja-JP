---
title: BizTalk Server に関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1aa5fb60-e8db-4cd2-88be-3c71b7b1d44d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4f933555f4643fb293d6fad882950eaf2f15ac6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330567"
---
# <a name="known-issues-with-biztalk-server"></a>BizTalk Server に関する既知の問題
このトピックでは、いくつかの既知の問題を示します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
## <a name="dtc-firewall-rules"></a>DTC ファイアウォール規則  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] および [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] が別のコンピューターにインストールされている場合、Distributed Transaction Coordinator (MS DTC) がコンピューター間のトランザクションを処理します。 その結果でファイアウォールの規則で DTC ポートを有効にする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。  
  
 構成するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ファイアウォールで DTC ポートが有効でない場合、次のエラーが発生する可能性が。  
  
 **データベースの作成時に WMI エラーが発生しましたロールバックを試行し、部分的に作成されたデータベース 'SQLServerName\BizTalkMsgBoxDb' を削除**  
  
 **WMI エラーの説明が生成されます。'System.enterpriseservices.transactionproxyexception' 型の例外がスローされました。**  
  
 次のリンクの詳細情報します。  
  
 [管理サーバーのポート](http://go.microsoft.com/fwlink/p/?LinkID=275568)  
  
 [BizTalk Server 2013 および 2013 R2 のインストール後の手順](../install-and-config-guides/post-installation-steps-for-biztalk-server-2013-and-2013-r2.md)  
  
##  <a name="BKMK_BAM"></a> ビジネス アクティビティの監視  
 このセクションでは、ビジネス アクティビティ監視 (BAM) モジュールでは、既知の問題が一覧表示します。  
  
### <a name="bam-definition-deployment-fails-due-to-a-sql-login-error"></a>SQL ログイン エラーのため失敗した BAM 定義の展開  
 BAM 定義をデプロイするときに、操作がエラー コード 42000 のログイン エラーのため失敗します。  
  
```  
...  
Deploying Activity... Done.   
Deploying View... ERROR: The BAM deployment failed.   
Server: The current operation was cancelled because another operation in the transaction failed.   
OLE DB error: OLE DB or ODBC error: Login failed for user <username>.; 42000.   
…  
```  
  
 この問題を修正するには、SQL Analysis サービス ログオン アカウントは、BAM に関連するすべてのデータベースに対する権限を持っていることを確認します。  
  
### <a name="bam-configuration-might-result-in-warnings-related-to-the-bam-analysis-logon-account"></a>BAM の構成は、BAM Analysis のログイン アカウントに関連する警告を可能性があります。  
 BAM 構成では、それらにアクセスできる BAM に関連するすべてのデータベースで BAM Analysis ログイン アカウントのアクセス許可を追加します。 ただし、構成が失敗するようにし、次の前提条件のいずれかが満たされない場合に警告を提供します。  
  
- BAM 構成を実行するユーザーは、Analysis Service がインストールされているコンピューターの管理者である必要があります。  
  
- そのコンピューターでは、ファイアウォール経由のリモート管理を許可する必要があります。  
  
- BAM Analysis のログイン アカウントが BAM に関連するデータベースがインストールされている SQL Server の管理者である場合は、警告を取得することも可能性があります。 警告を無視して進むことができます。  
  
  **回避策**– BAM に関連するすべてのデータベースで BAM Analysis のログイン アカウントに対するアクセス許可を手動で追加する必要があります。  
  
### <a name="bam-portal-compatibility-with-internet-explorer-10"></a>Internet Explorer 10 で BAM ポータルの互換性  
 Internet Explorer 10 では、BAM ポータルを使用するには、常に互換モードでブラウザーを使用する必要があります。  
  
### <a name="receiving-notification-e-mails-even-after-the-alert-host-service-is-stopped"></a>Alert Host 後も通知の電子メールを受信するサービスが停止しました  
 使用する場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]、BAM 警告を使用する場合は、SQL Server でデータベース メール機能を構成する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベース メール機能と組み合わせて、Alert Host サービスを使用して、アラートの通知を送信します。 Alert Host サービス、通知の処理後に通知のワークロードに渡します SQL server データベース メール コンポーネント。 そう、Alert Host サービスを停止する場合でも、データベース メール コンポーネントではありませんが、Alert Host サービスによって処理されたイベントのいくつかの通知をする可能性があります。  
  
### <a name="configuring-tracing-for-bam-alerts"></a>BAM 警告のトレースの構成  
 使用する場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]、BAM 警告の診断トレースを有効にしては、BAM 警告のホストの構成ファイルを作成して行う必要があります。 としてファイルに名前を付けて**BAMAlerts.exe.config** 、EXE と同じ場所にコピー (**BAMAlerts.exe**)、\Program Files\Microsoft BizTalk Server\Tracking にある\\。  
  
 構成ファイルのサンプルは、次のようになります。 このファイルに記録**情報**レベルのイベント ビューアーに詳細情報。  
  
```  
<configuration>  
  <system.diagnostics>  
    <switches>  
      <add name="LogEventProvider" value="Info"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
##  <a name="BKMK_Upgrade"></a> SQL Server 2012 で BizTalk Server を使用中の問題  
 使用中に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]を設定することができます、 **Remote Login Timeout** 20 秒に SQL Server での値。 そうしな場合ストレス条件でエラーが発生する可能性があります。 リモート ログイン タイムアウト値を設定する方法については[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]を参照してください [http://msdn.microsoft.com/library/ms175136.aspx](http://msdn.microsoft.com/library/ms175136.aspx)  
  
##  <a name="BKMK_Adapters"></a> アダプターの問題  
 このセクションの既知の問題を一覧表示、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプター。  
  
### <a name="dynamic-port-may-fail-while-using-the-windows-sharepoint-services-wss-adapter"></a>Windows SharePoint Services (WSS) アダプターを使用しているときに動的なポートが失敗します。  
 WSS アダプターを使用して動的なポートは、次のエラーで失敗します。  
  
```  
Error details: The Windows SharePoint Services site was not found. The URL "http://server:443/site" points to a SharePoint object for which there is no Windows SharePoint Services site.  
```  
  
 **回避策**:  
  
-   ポートの構成で、サイトの URL のポート番号も含まれます。 たとえば、`http://server:80/site` のようにします。  
  
-   有効にする、 **Windows Identity Foundation 3.5**機能します。  
  
-   BizTalk ホストを実行しているアカウントが SharePoint へのアクセスを確認します。  
  
### <a name="adapters-available-with-biztalk-adapter-pack-cannot-be-administered-on-a-computer-that-only-has-biztalk-server-administration-component-installed"></a>BizTalk Server 管理コンポーネントがインストールされているコンピューターで BizTalk Adapter Pack で使用できるアダプターを管理することはできません。  
 BizTalk Adapter Pack ののみされているコンピューターにインストールされているかどうかがある、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールがインストールされている、BizTalk Adapter Pack の一部としてインストールされているアダプターを利用できません送信ポートを作成するか、受信場所。 これらのアダプターが同じコンピューターにインストールされる BizTalk ランタイムで依存関係を持つためにです。  
  
 回避策 – Adapter Pack と BizTalk Server 管理コンポーネントをインストールしたコンピューター上の BizTalk Server ランタイムをインストールします。 コンピューターに BizTalk Server を構成する必要がありません。  
  
## <a name="other-issues"></a>その他の問題  
  
### <a name="setupbat-for-biztalk-server-samples-runs-with-a-32-bit-command-prompt"></a>BizTalk Server の Setup.bat サンプルの 32 ビット コマンド プロンプトで実行します。  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]このリリースに付属のサンプル、32 ビット コマンド プロンプトからのみ付随する setup.bat ファイルを実行する必要があります。 64 ビット コマンド プロンプトからバッチ ファイルを実行するいると、失敗する可能性があります。  
  
### <a name="run-setup-as-administrator"></a>セットアップを管理者として実行します。  
 インストールするときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用して、**管理者として実行**オプション。 それ以外の場合、次のエラーが発生する可能性があります。  
  
 内部エラー 2761 です。 コードが返されます。1  
  
 MSI のインストールには、1603 - インストール中に致命的なエラーが返されます。  
  
### <a name="using-certificates-with-1024-key-for-encoding-and-signing-results-in-failure-of-mime-smime-decoding"></a>1024 キーのエンコードと、MIME-SMIME デコードの失敗の結果を署名証明書の使用  
 Windows 8 の場合、メッセージが暗号化され、1024 キーを持つ証明書を使用して署名したときに、MIME-SMIME デコードでメッセージの認証が失敗します。 この問題を回避するには、2048 キーを持つ証明書を使用することができます。  
  
### <a name="uddi-resolver-with-esb-toolkit-gives-a-serialization-error"></a>ESB Toolkit を使用した UDDI リゾルバーでシリアル化エラー  
 UDDI を使用して、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]バインディングの詳細の検索時に XML シリアル化エラーが発生する可能性があります。 このエラーは、バインド キーが指定されていない場合に発生します。  
  
### <a name="the-itinerary-designer-for-esb-toolkit"></a>ESB Toolkit の itinerary designer  
 Itinerary designer、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]の一部になりましたが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール メディア。 Itinerary designer で、メディアのルート フォルダーを見つけることができ、名前を持つ`Microsoft.Practices.Services.Itinerary.DslPackage.vsix`します。 以前では、このファイルが使用可能なインストールする場所に、 [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]、通常は \Program Files\Microsoft[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]します。  
  
### <a name="edi"></a>EDI   
 EDI バッチ処理が使用されています。 アラビア語のカレンダーまたはローカル設定を使用する場合、オーケストレーションを次のエラーで中断します。  
  
 **エラー コード:0xC0C01B52 (オーケストレーション エンジン エラー) エラーの説明:退避中に永続化エラーにより中断されました。** アラビア語のグレゴリオ暦の日付をサポートしている*04/30/1900 00.00.00*に*2029 13/05/23時 59分: 59*します。  
  
 この問題を解決するには、有効なアラビア語の終了日を入力します。  
  
### <a name="enterprise-single-sign-on"></a>エンタープライズ シングル サインオン  
 エンタープライズ シングル サインオン (ESSO) をインストールするとき、または ESSO サービスを再起動するときは、イベント ビューアーにログインして、次のエラー表示があります。  
  
 **\Program Files\Common \enterprise シングル サインオン \ssopsserver.dll エラー コードの読み込みに失敗しました。0x8007007E、指定したモジュールが見つかりませんでした。** このエラーを無視してかまいません。