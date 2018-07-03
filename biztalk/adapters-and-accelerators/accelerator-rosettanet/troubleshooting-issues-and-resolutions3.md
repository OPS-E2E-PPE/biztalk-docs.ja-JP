---
title: 'トラブルシューティング: 問題と Resolutions3 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: 40f59f54-183e-43db-afb5-0a45b437697f
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad2e2db5e7d4d8c8181248f9345f1df2cca4a6dd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985099"
---
# <a name="troubleshooting-issues-and-resolutions"></a>トラブルシューティング : 問題と解決策
このトピックの「Microsoft® の実行に関連する問題に対処[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]します。 個々の問題について、具体的な現象、考えられる原因、および解決策について詳しく説明します。  
  
## <a name="error-publishing-a-batch-of-n-messages"></a>"n" 通のメッセージのバッチ公開エラー  
  
### <a name="symptom"></a>現象  
 イベント ログに次のようなエラーが記録されます。  
  
 メッセージング エンジンで、トランスポート アダプター "BizTalk HTTP Receiver" のメッセージ ボックス データベースに "n" 通のメッセージのバッチを公開中にエラーが発生しました。 このエラーの詳細については、「状態と動作状況の追跡ツール」を参照してください。また、エンドポイントのバインドが正しく構成されていることを確認してください。  
  
### <a name="possible-cause"></a>考えられる原因  
 このエラーは、次のいずれかの原因により起こる可能性があります。  
  
- 暗号化解除証明書が紛失している。  
  
- メッセージが間違って暗号化されている。  
  
- メッセージが認証されていない (ソースが有効なパートナーとして認識されていない)。  
  
- メッセージが、ヘッダー部位 (Preamble、Delivery Header、Service Header) のいずれかの検証に失敗している。  
  
  このメッセージの前に、原因を詳細に示す別のエラー メッセージが表示されることがあります。  
  
### <a name="solution"></a>解決方法  
 エラー メッセージに記載されている詳細情報も確認してください。 Microsoft の再起動[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]™ この問題を解決する可能性があります。  
  
## <a name="you-cannot-unenlist-all-artifacts"></a>一部のアイテムの登録を解除できない  
  
### <a name="symptom"></a>現象  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Clean ユーティリティを実行しても、登録を解除できないアイテムが残ります。  
  
### <a name="possible-cause"></a>考えられる原因  
 実行する場合、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Microsoft® 管理コンソール (MMC) からアグリーメントとパートナーを削除する前に Clean ユーティリティ BtarnClean ユーティリティできなくでも使用されますので、すべての成果物の参加を解除します。  
  
### <a name="solution"></a>解決方法  
  
##### <a name="to-remove-artifacts-using-the-loopback-utility"></a>Loopback ユーティリティを使用してアイテムを除去するには  
  
1.  コマンド プロンプトで、次のように入力します。  
  
    ```  
    lookback.exe /disable <home org or partner>  
    ```  
  
2.  BtarnClean.exe ファイルを実行します。  
  
3.  BizTalk エクスプローラーで、パーティを削除します。  
  
## <a name="installing-btarn-on-a-computer-without-biztalk-server-causes-missing-files"></a>BizTalk Server がインストールされていないコンピューターに BTARN をインストールするとファイルが欠落する  
  
### <a name="symptom"></a>現象  
 ない MicrosoftBizTalk サーバーまたは Microsoft を持たないコンピューターで結果が得られます ConfigFramework.exe ファイルを実行している[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]をインストールします。 この [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 構成は、HTTP クライアントとしてのみ使用できます。  
  
### <a name="possible-cause"></a>考えられる原因  
 インストール先に 2 つの DLL ファイルが見つかりません。  
  
### <a name="solution"></a>解決方法  
 コンピューターに SQLXML をインストールしてから、[System] フォルダーに Msxml4.dll と Atl71.dll ファイルを手動でコピーします。  
  
## <a name="you-receive-an-access-error-when-attempting-to-change-the-btarn-configuration"></a>BTARN 構成を変更しようとすると、アクセス エラーが表示される  
  
### <a name="symptom"></a>現象  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールを使用して構成ファイルをインポートすると、次のようなエラー メッセージが表示されます。  
  
 構成ストアから送信ポート 'RNSTT.Async' のプライマリ トランスポートに対して、トランスポートの種類のデータを格納できませんでした。 アクセスが拒否されました。  
  
 このエラー メッセージは、新しいパートナーを作成するなどして構成を変更しようとするときにも表示されます。  
  
### <a name="possible-cause"></a>考えられる原因  
 現在のユーザーが BizTalk Administrators グループのメンバではありません。  
  
### <a name="solution"></a>解決方法  
 現在のユーザーを BizTalk Administrators グループのメンバにします。  
  
## <a name="you-receive-bam-errors"></a>BAM エラーが発生する  
  
### <a name="symptom"></a>現象  
 イベント ビューアーに次のエラー メッセージが表示されます。  
  
 メッセージ アクティビティの追跡中にエラーが発生しました。 エラー メッセージは "ストアド プロシージャが存在しません" です。  
  
 - または -  
  
 Id の BAM メッセージ アクティビティの終了エラー  *\<ID 番号\>* します。  
  
### <a name="possible-cause"></a>考えられる原因  
 ビジネス アクティビティ監視 (BAM) 追跡ツールがインストールされていません。  
  
### <a name="solution"></a>解決方法  
 BAM 追跡ツールを使用してをインストール、**カスタム インストール**オプション。 BAM 機能が不要な場合は、これらのメッセージを無視するか、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールを使用して追跡機能を無効にします。 追跡機能を無効にした後で、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] とインターネット インフォメーション サービス (IIS) を再起動する必要があります。  
  
## <a name="your-xsd-schema-does-not-display-properly-in-biztalk-editor"></a>BizTalk エディターに XSD スキーマが正しく表示されない  
  
### <a name="symptom"></a>現象  
 BizTalk エディターでスキーマの内容を正しく表示できません。  
  
### <a name="possible-cause"></a>考えられる原因  
 `displayroot_reference` 要素の `schemaInfo` 属性がスキーマにありません。  
  
### <a name="solution"></a>解決方法  
 メモ帳などのテキスト エディターでスキーマを開き、`displayroot_reference` 属性を `schemaInfo` 要素に追加します。 `displayroot_reference` 属性には、`root_reference` 属性と同じ値を指定してください。  
  
 以下に例を示します。  
  
 \<schemaInfo document_type"4A1"バージョン = ="V02_00"xmlns ="<http://schemas.microsoft.com/BizTalk/2003>" *displayroot_reference ="Pip4A1StrategicForecastNotification"* root_reference"Pip4A1StrategicForecastNotification"を = \>  
  
## <a name="404-not-found-error-when-sending-a-http-request"></a>HTTP 要求の送信時に "404 Not found" というエラーが表示される  
  
### <a name="symptom"></a>現象  
 HTTP 要求を送信すると、次のようなエラーが表示されます。  
  
 リモート サーバーが (404) Not Found エラーを返しました。  
  
 メッセージが ../BTSHttpReceive.dll に送信されませんでした。  
  
### <a name="possible-cause"></a>考えられる原因  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Internet Server API (ISAPI) の拡張 DLL (BTSHttpReceive.dll) がインターネット インフォメーション サービス (IIS) で構成されていません。 これは、HwsMessages HttpReceive Web サービス拡張が構成されていないか、この Web サービス拡張が構成されていても、許可されていない場合に発生します。  
  
### <a name="solution"></a>解決方法  
 HwsMessages HttpReceive Web サービス拡張が構成されているかどうかを判断し、構成されていない場合に許可するには、次の手順を実行します。  
  
##### <a name="to-configure-the-biztalk-isapi-extension-dll-in-iis"></a>IIS で BizTalk ISAPI 拡張 DLL を構成するには  
  
1. クリックして**開始**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**します。  
  
2. 展開**\<コンピューター名\>(ローカル コンピューター)**、 をクリックし、 **Web サービス拡張**します。  
  
3. **Web サービス拡張**ウィンドウで、HwsMessages HttpReceive の状態が許可されていることを確認します。 ない場合を右クリックして**HwsMessages HttpReceive**、 をクリックし、**許可**。  
  
   HwsMessages HttpReceive Web サービス拡張が構成されていない場合 (IIS マネージャーの Web サービス拡張一覧に含まれていない場合) は、次の手順を実行します。  
  
##### <a name="to-configure-the-biztalk-isapi-extension-dll-in-iis"></a>IIS で BizTalk ISAPI 拡張 DLL を構成するには  
  
1.  クリックして**開始**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**します。  
  
2.  展開**\<コンピューター名\>(ローカル コンピューター)** を右クリックして**Web サービス拡張**、 をクリックし、**新しい Web サービス拡張機能の追加**.  
  
3.  **新しい Web サービス拡張** ダイアログ ボックスで、**拡張機能名**ボックスに「 **BizTalk ISAPI Extension**、順にクリックします**追加**します。  
  
4.  **ファイルの追加** ダイアログ ボックスで、**ファイルへのパス**ボックスに「 **\<ドライブ\>: \Program Files\Microsoft BizTalk Server \<のバージョン\>\HttpReceive\BTSHttpReceive.dll**、 をクリックし、 **OK**します。  
  
5.  **新しい Web サービス拡張**ダイアログ ボックスで、**拡張機能の状態を許可 に設定**、順にクリックします**OK**します。  
  
## <a name="an-access-violation-occurs-when-running-the-configuration-wizard"></a>構成ウィザードを実行するとアクセス違反が発生する  
  
### <a name="symptom"></a>現象  
 イベント ログに次のようなエラーが記録されます。  
  
 ユーザー アカウント '\HostSvc' で構成された BizTalk の分離ホスト インスタンスが起動していないか、このコンピューターに存在しません。 BizTalk 管理コンソールを使用して、新しい分離ホストを作成するか、既存の分離ホストを再構成して、"\hostsvc" として実行してください。  
  
### <a name="possible-cause"></a>考えられる原因  
 構成ウィザードを実行するユーザーを構成する必要があります '\<*マシン名*\>\hostsvc'、'\hostsvc'。  
  
### <a name="solution"></a>解決方法  
 BizTalk 管理コンソールを開き、アカウントで実行されるように、アカウント"\hostsvc"で実行しているホストを変更 '\<*マシン名*\>\hostsvc'。  
  
## <a name="you-receive-an-error-when-importing-and-compiling-a-rosettanet-next-generation-pip-schema"></a>RosettaNet Next Generation PIP スキーマをインポートしてコンパイルするときにエラーが発生する  
  
### <a name="symptom"></a>現象  
 イベント ログに次のようなエラーが記録されます。  
  
 エラー CS0234: 型または名前空間 "SerializableAttribute" は、クラスまたは名前空間 "RosettaNet.Schemas.System" に存在しません。アセンブリ参照があるかどうかを確認してください。  
  
### <a name="possible-cause"></a>考えられる原因  
 スキーマの 1 つ、たとえば StandardDocumentHeader.xsd に、RosettaNet.Schemas.System という [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] 名前空間があります。  
  
### <a name="solution"></a>解決方法  
 このスキーマの [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] 名前空間から "System" を削除して、名前空間を RosettaNet.Schemas にします。  
  
## <a name="you-receive-an-error-when-trying-to-manually-deploy-the-bam-package"></a>手動で BAM パッケージを展開しようとするとエラーが発生する  
  
### <a name="symptom"></a>現象  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] の BAM パッケージを手動で展開しようとすると、パッケージが展開できないというエラーが表示されます。  
  
### <a name="possible-cause"></a>考えられる原因  
 BAM_DM_Process と BAM_DM_Message という 2 つの DTS パッケージがシステムにインストールされており、これが BAM パッケージの展開を妨げています。  
  
### <a name="solution"></a>解決方法  
  
##### <a name="to-recover-from-the-error-condition-and-deploy-the-bam-package"></a>エラー状態から回復して BAM パッケージを展開するには  
  
1.  クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server**、順にクリックします**Enterprise Manager**します。  
  
2.  Enterprise Manager で展開**Microsoft SQL Servers**、 **SQL Server グループ**、 **(ローカル) (Windows NT)**、および**データ変換サービス**.  
  
3.  クリックして**ローカル パッケージ**を右クリックして**BAM_DM_Message**、順にクリックします**削除**します。  
  
4.  右クリック**BAM_DM_Process**、 をクリックし、**削除**します。  
  
5.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
6.  コマンド プロンプトで、追跡ファイルを展開する次のコードを入力し、クリックして**OK**します。  
  
    ```  
    cd %ProgramFiles%\Microsoft BizTalk Server <version>\Tracking  
    bm deploy all  "%ProgramFiles%\Microsoft BizTalk <version> Accelerator for RosettaNet\BAMTracking\tracking.xml"  
    ```  
  
## <a name="you-receive-an-error-when-adding-a-new-pip"></a>新しい PIP を追加するときにエラーが表示される  
  
### <a name="symptom"></a>現象  
 イベント ログに次のようなエラーが記録されます。  
  
 Service Content の検証中にエラーが発生しました。  
  
 詳細: ドキュメント仕様をメッセージの種類別に検索できませんでした。 スキーマが正しく展開されていることを確認してください。  
  
### <a name="possible-cause"></a>考えられる原因  
 インスタンス Pip4A5NotifyofForecastReply の展開済みスキーマのドキュメント名前空間か、ルート ノード プロパティのどちらかが間違っています。  
  
### <a name="solution"></a>解決方法  
 インスタンス Pip4A5NotifyofForecastReply の展開済みスキーマのドキュメント名前空間とルート ノード プロパティが正しいかどうかを確認します。  
  
## <a name="error-during-the-configuration-of-btarn-at-installation-time-caused-by-presumed-network-connectivity-issues"></a>インストール時の BTARN を構成中にネットワーク接続の問題が推定されてエラーが発生する  
  
### <a name="symptom"></a>現象  
 構成プロセス中に、コンピュータが実際にはネットワークに正しく接続されているのに正しく接続されていないというエラーが [エラー] ダイアログ ボックスに表示されます。  
  
### <a name="possible-cause"></a>考えられる原因  
 このエラーは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 構成プログラムが IP アドレスの解釈を間違えると発生します。 C:\Windows\system32\drivers\etc に格納されているホスト ファイルには、localhost のホスト名を IP アドレス 127.0.0.1 にマップしているエントリが記載されています。 構成プログラムが、この値をループバック アドレスの値と混同した結果、コンピュータがネットワークに正しく接続されていないと誤認している可能性があります。  
  
### <a name="solution"></a>解決方法  
  
##### <a name="to-avoid-this-error-and-complete-the-configuration-process"></a>このエラーを回避して構成プロセスを完了するには  
  
1. [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] エクスプローラーで、C:\Windows\system32\drivers\etc に移動し、メモ帳を使用してホスト ファイルを開きます。  
  
2. 行をコメント アウト"127.0.0.1 localhost"の行の先頭に「#」を配置することで。 変更されたホスト ファイルを保存します。  
  
3. クリックして**再試行**エラー ダイアログ ボックス。  
  
4. 構成が正常に完了した後で、メモ帳でホスト ファイルを再び開き、localhost をマップしている行の行頭に付けたコメント記号を削除して、ホスト ファイルを保存します。  
  
## <a name="you-receive-an-error-regarding-incorrect-signature-length"></a>署名の長さが正しくないというエラーが表示される  
  
### <a name="symptom"></a>現象  
 イベント ログに次のようなエラーが記録されます。  
  
 受信パイプライン "Microsoft.Solutions.BTARN.Pipelines.Receive" を実行中にエラーが発生しました。送信元: "MIME/SMIME decoder"、受信ポート: "/BTARNHttpReceive/BTSHTTPReceive.dll?xRNResponseType=async"、理由: 不正な署名の長さ、値 = 1935897193。  
  
### <a name="possible-cause"></a>考えられる原因  
 このエラー メッセージは、署名の長さが間違っていることを通知します。 このエラーは上記の原因の他に、ヘッダー内容の長さの間違いや不完全によっても発生します。これが原因で署名の長さのバイト数が誤って読み取られます。  
  
### <a name="solution"></a>解決方法  
 署名とヘッダー内容の両方の長さが正しいことを確認します。  
  
## <a name="you-receive-503-service-unavailable-from-internet-explorer-on-64-bit-machine"></a>64 ビット マシンで、Internet Explorer に "503: Service Unavailable" というメッセージが表示される  
  
### <a name="symptom"></a>現象  
 後[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]にアクセスしようとすると、構成が完了した[ http://localhost ](http://localhost/)または[ http://localhost/BtarnApp/RnifSend.aspx ](http://localhost/BtarnApp/RnifSend.aspx)、以下のようなエラーが発生した可能性があります。  
  
 503: Service Unavailable  
  
### <a name="possible-cause"></a>考えられる原因  
 このエラーは、C:\windows\system32\rpcproxy\rpcproxy.dll の IIS Web サイトに設定されている ISAPI フィルターが原因で発生します。  
  
### <a name="solution"></a>解決方法  
  
##### <a name="to-remove-rpcproxy-filter-entry-in-iis"></a>IIS で RpcProxy フィルターを削除するには  
  
1.  クリックして**開始**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**します。  
  
2.  展開**\<コンピューター名\>(ローカル コンピューター)** を右クリックして**Websites**、順にクリックします**プロパティ**します。  
  
3.  選択**ISAPI フィルター**タブ。  
  
4.  選択**RpcProxy フィルター**、 をクリック**削除**します。  
  
5.  **[OK]** をクリックします。  
  
6.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
7.  コマンド プロンプトで、次のコードを入力して IIS をリセットします。  
  
    ```  
    iisreset  
    ```  
  
> [!NOTE]
>  アクセスしようとする場合http://localhostまたはhttp://localhost/BtarnApp/RnifSend.aspxもう一度上記の手順を実行すると、メッセージが表示されます HTTP 400 から Internet Explorer は IIS が正しく機能しています。  
  
## <a name="the-hubscenario-sample-will-not-be-installed-correctly-if-the-assembly-key-files-are-not-entered-for-the-projects"></a>アセンブリ キー ファイルがプロジェクトに入力されていない場合に HubScenario サンプルが正しくインストールされない  
  
### <a name="symptom"></a>現象  
 Setup.bat を実行すると*\<ドライブ\>*: \Program Files\\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\hubscenario を設定するにはHubScenario サンプルでは、操作は失敗します。  
  
### <a name="possible-cause"></a>考えられる原因  
 アセンブリ キー ファイルがプロジェクトに設定されていないので、HubScenario および HubHelper アセンブリが正しく展開されていません。  
  
### <a name="solution"></a>解決方法  
 HubScenario および HubHelper プロジェクトのアセンブリ キー ファイルを設定します。 詳細については、次を参照してください。 [HubScenario サンプル](../../adapters-and-accelerators/accelerator-rosettanet/hubscenario-sample.md)します。  
  
## <a name="run-setupx64bat-to-set-up-the-double-action-pipautomation-orchestration-sample-on-sql-server-2008-r22008-sp1"></a>SQL Server 2008 R2 または SQL Server 2008 SP1 で setupx64.bat を実行して Double Action PIPAutomation オーケストレーション サンプルを設定する  
  
### <a name="symptom"></a>現象  
 setup.bat を実行して Double Action PIPAutomation オーケストレーション サンプルを構築および初期化しようとしたときに、BTARNData データベースに PipAutomationGetAction ストアド プロシージャが作成されない。  
  
### <a name="possible-cause"></a>考えられる原因  
 64 ビット コンピューターで、または SQL Server 2008 R2 または 2008 SP1 で実行されている BizTalk Server のインストールでは、setup.bat を実行します。 これらのインスタンスでは setupx64.bat を実行する必要があります。  
  
### <a name="solution"></a>解決方法  
 setupx64.bat を実行してストアド プロシージャを作成します。 詳細については、次を参照してください。 [Double Action PIPAutomation Orchestration](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)します。  
  
## <a name="enable-the-btarn-application-pools-for-32-bit-on-windows-server-2008-64-bit-windows-operating-system-os"></a>64 ビットの Windows オペレーティング システム (OS) の Windows Server 2008 で 32 ビットの BTARN アプリケーション プールを有効にする  
 インターネット インフォメーション サービス マネージャー 7.5 または 7.0 を使用して、64 ビットの Windows オペレーティング システム (OS) の Windows Server 2008 で BTARN エンド ツー エンド シナリオを実行するには  
  
 1. 32 ビットの BTARN アプリケーション プールを有効にします。  
  
 2. IsapiModule フィルターを参照する *.dll の HTTP ハンドラーを追加します。  
  
## <a name="see-also"></a>参照  
 [BtarnClean](../../adapters-and-accelerators/accelerator-rosettanet/btarnclean.md)   
 [Loopback](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md)