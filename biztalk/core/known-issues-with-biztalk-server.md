---
title: BizTalk Server に関する既知の問題 |Microsoft ドキュメント
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
ms.openlocfilehash: 2b7998225af7ca598d4df5b4fd98f2826edce3a4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264282"
---
# <a name="known-issues-with-biztalk-server"></a>BizTalk Server の既知の問題
このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の既知の問題について取り上げます。  
  
## <a name="dtc-firewall-rules"></a>DTC ファイアウォール規則  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] および [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] が別のコンピューターにインストールされている場合、Distributed Transaction Coordinator (MS DTC) がコンピューター間のトランザクションを処理します。 そのため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターと [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] コンピューターのファイアウォールの規則で DTC ポートを有効にしてください。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成するときに、ファイアウォールで DTC ポートが有効になっていない場合、次のエラーが発生する可能性があります。  
  
 **データベースの作成中に WMI エラーが発生しましたロールバックを試行し、部分的に作成されたデータベース '\biztalkmsgboxdb' を削除**  
  
 **WMI エラーの説明が生成されました: 'system.enterpriseservices.transactionproxyexception' がスローされた型の例外。**  
  
 次のリンクは、詳細を提供します。  
  
 [管理サーバーのポート](http://go.microsoft.com/fwlink/p/?LinkID=275568)  
  
 [BizTalk Server 2013 および 2013 R2 のインストール後の手順](../install-and-config-guides/post-installation-steps-for-biztalk-server-2013-and-2013-r2.md)  
  
##  <a name="BKMK_BAM"></a>ビジネス アクティビティの監視  
 ここでは、ビジネス アクティビティの監視 (BAM) モジュールの既知の問題の一覧を示します。  
  
### <a name="bam-definition-deployment-fails-due-to-a-sql-login-error"></a>SQL ログイン エラーで BAM 定義の展開に失敗する  
 BAM 定義を展開する際、エラー コード 42000 のログイン エラーが原因で操作が失敗する場合があります。  
  
```  
...  
Deploying Activity... Done.   
Deploying View... ERROR: The BAM deployment failed.   
Server: The current operation was cancelled because another operation in the transaction failed.   
OLE DB error: OLE DB or ODBC error: Login failed for user <username>.; 42000.   
…  
```  
  
 この問題を修正するには、SQL Analysis Service のログイン アカウントに、BAM に関するすべてのデータベースへのアクセス権があることを確認してください。  
  
### <a name="bam-configuration-might-result-in-warnings-related-to-the-bam-analysis-logon-account"></a>BAM 構成で BAM Analysis ログイン アカウントに関する警告が表示される  
 BAM 構成では、それらにアクセスできるように BAM に関連するすべてのデータベースで BAM Analysis ログイン アカウントのアクセス許可を追加します。 ただし、次の前提条件を満たさなかった場合はアクセス権の付与に失敗し、警告が表示されます:  
  
-   BAM 構成を実行しているユーザーは、Analysis Service がインストールされているコンピューターの管理者である必要があります。  
  
-   そのコンピューターでは、ファイアウォール経由のリモート管理が許可されている必要があります。  
  
-   BAM Analysis のログイン アカウントが、BAM に関するデータベースがインストールされている SQL Server の管理者である場合にも、警告が表示されることがあります。 警告を無視して次に進むことができます。  
  
 **回避策**– BAM に関連するすべてのデータベースで、BAM Analysis ログイン アカウントに対するアクセス許可を手動で追加する必要があります。  
  
### <a name="bam-portal-compatibility-with-internet-explorer-10"></a>BAM ポータルと Internet Explorer 10 の間の互換性  
 Internet Explorer 10 で BAM ポータルを使用するには、常にブラウザーを互換モードで使用する必要があります。  
  
### <a name="receiving-notification-e-mails-even-after-the-alert-host-service-is-stopped"></a>Alert Host サービスが停止した後であっても通知の電子メールを受信する  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] を併用する場合、BAM 警告を使用する必要があれば、SQL Server でデータベース メール機能を構成する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、Alert Host サービスとデータベース メール機能を組み合わせて使用して、通知警告を送信します。 Alert Host サービスは、通知を処理した後、SQL Server のデータベース メール コンポーネントに通知のワークロードを渡します。 そのため、Alert Host サービスを停止した場合であっても、Alert Host サービスによって処理されたがデータベース メール コンポーネントでは処理されていないイベントに関して、まだいくつかの通知を受け取ることがあります。  
  
### <a name="configuring-tracing-for-bam-alerts"></a>BAM 警告のトレースの構成  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] を併用し、また BAM 警告の診断トレースを有効にする必要がある場合は、BAM 警告のホストに関する構成ファイルを作成する必要があります。 ファイルとして名前を付ける必要があります**BAMAlerts.exe.config** EXE と同じ場所にコピーし、(**BAMAlerts.exe**)、\Program Files\Microsoft BizTalk Server\Tracking \tracking\ にある\\です。  
  
 構成ファイルのサンプルは以下のようになります。 このファイルをログに記録**情報**レベルのイベント ビューアーの詳細情報。  
  
```  
<configuration>  
  <system.diagnostics>  
    <switches>  
      <add name="LogEventProvider" value="Info"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
##  <a name="BKMK_Upgrade"></a>BizTalk Server を SQL Server 2012 で使用中の問題  
 使用しているときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]設定することができます、 **Remote Login Timeout** 20 秒に SQL Server の値。 このように設定しないと、負荷が高い状況でエラーが発生する場合があります。 リモート ログイン タイムアウト値を設定する方法の詳細について[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]を参照してください[http://msdn.microsoft.com/library/ms175136.aspx](http://msdn.microsoft.com/library/ms175136.aspx)  
  
##  <a name="BKMK_Adapters"></a>アダプターの問題  
 ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のアダプターに関する既知の問題の一覧を示します。  
  
### <a name="dynamic-port-may-fail-while-using-the-windows-sharepoint-services-wss-adapter"></a>Windows SharePoint Services (WSS) アダプターを使用している場合に動的ポートでエラーが発生することがある  
 WSS アダプターを使用している動的ポートで障害が発生し、次のエラーが表示される場合があります。  
  
```  
Error details: The Windows SharePoint Services site was not found. The URL "http://server:443/site" points to a SharePoint object for which there is no Windows SharePoint Services site.  
```  
  
 **回避策**:  
  
-   ポートの構成で、サイトの URL にポート番号も含めます。 たとえば、 `http://server:80/site`のようにします。  
  
-   有効にする、 **Windows Identity Foundation 3.5**機能します。  
  
-   BizTalk ホストを実行しているアカウントが SharePoint へのアクセスを確認します。  
  
### <a name="adapters-available-with-biztalk-adapter-pack-cannot-be-administered-on-a-computer-that-only-has-biztalk-server-administration-component-installed"></a>BizTalk Server 管理コンソールのみがインストールされているコンピューターでは、BizTalk Adapter Pack で使用できるアダプターを管理できない  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールのみがインストールされているコンピューターに BizTalk Adapter Pack をインストールした場合、送信ポートまたは受信場所を作成しても、BizTalk Adapter Pack の一部としてインストールされているアダプターを使用できません。 これは、これらのアダプターは、同じコンピューターにインストールされている BizTalk ランタイムに依存するためです。  
  
 回避策 – Adapter Pack と BizTalk Server 管理コンソールがインストールされているコンピューターに BizTalk Server ランタイムをインストールします。 そのコンピューターで BizTalk Server を構成する必要はありません。  
  
## <a name="other-issues"></a>その他の問題  
  
### <a name="setupbat-for-biztalk-server-samples-runs-with-a-32-bit-command-prompt"></a>BizTalk Server のサンプルの setup.bat が 32 ビットのコマンド プロンプトで実行される  
 このリリースに付属する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のサンプルに関して、付随する setup.bat ファイルは、32 ビットのコマンド プロンプトからのみ実行する必要があります。 64 ビットのコマンド プロンプトからバッチ ファイルを実行すると、エラーが発生する場合があります。  
  
### <a name="run-setup-as-administrator"></a>管理者としてセットアップを実行する  
 インストールするときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用して、**管理者として実行**オプション。 このオプションを使用しない場合、次のエラーが発生することがあります。  
  
 内部エラー 2761 です。 リターン コード: 1  
  
 MSI のインストールには、1603 - インストール中に致命的なエラーが返されます。  
  
### <a name="using-certificates-with-1024-key-for-encoding-and-signing-results-in-failure-of-mime-smime-decoding"></a>1024 キーを含む証明書をエンコードと署名に使用すると、MIME-SMIME デコードでエラーが発生する  
 Windows 8 では、1024 キーを含む証明書を使用してメッセージが暗号化および署名されている場合、メッセージの認証で MIME-SMIME デコードにエラーが発生します。 この問題を回避するには、2048 キーを含む証明書を使用する方法があります。  
  
### <a name="uddi-resolver-with-esb-toolkit-gives-a-serialization-error"></a>ESB Toolkit を使用する UDDI リゾルバーでシリアル化エラーが発生する  
 [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] で UDDI を使用している場合、バインドの詳細を検索するときに、XML シリアル化エラーが発生することがあります。 このエラーは、バインドのキーが指定されていない場合に発生します。  
  
### <a name="the-itinerary-designer-for-esb-toolkit"></a>ESB Toolkit の Itinerary Designer  
 [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] の Itinerary Designer は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インストール メディアの一部として収録されています。 Itinerary Designer はメディアのルート フォルダーにあり、名前は `Microsoft.Practices.Services.Itinerary.DslPackage.vsix` です。 以前は、このファイルは、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] のインストール場所 (通常は \Program Files\Microsoft [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]) にありました。  
  
### <a name="edi"></a>EDI   
 EDI バッチ処理が使用されます。 アラビア語のカレンダーまたはローカル設定を使用する場合、オーケストレーションが中断され、次のエラーが表示されます。  
  
 **エラー コード: 0xC0C01B52 (オーケストレーション エンジン エラー) エラーの説明: 退避中に永続化エラーにより中断されました。** アラビア語のグレゴリオ暦の日付をサポートしている*04/30/1900 00.00.00*に*05/13/2029 23時 59分: 59*です。  
  
 この現象を解決するには、有効なアラビア語の終了日を入力します。  
  
### <a name="enterprise-single-sign-on"></a>エンタープライズ シングル サインオン  
 エンタープライズ シングル サインオン (ESSO) をインストールする際、または ESSO サービスを再起動する際は、イベント ビューアーに記録される次のエラーが表示される場合があります。  
  
 **\Program files \common files \enterprise シングル サインオン \ssopsserver.dll エラー コードの読み込みに失敗しました: 0x8007007E、指定したモジュールに見つかりませんでした。** このエラーを無視できます。