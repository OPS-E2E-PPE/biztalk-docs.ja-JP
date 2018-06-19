---
title: BizTalk Server で RosettaNet accelerator に関する既知の問題 |Microsoft ドキュメント
description: 既知の問題と解決策の障害、BAM、インストールおよび構成、および BizTalk Server で BTARN で複数の 0A1 通知を参照してください。
caps.latest.revision: 11
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 335eb3c9-b565-470f-b69c-2a771ef8b476
ms.author: mandia
ms.openlocfilehash: bbb7ddc2028383f8ac346e7876459f322d2dd96b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010779"
---
# <a name="known-issues"></a>既知の問題
ここでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] に関するエラーを回避するときに役立つ情報を紹介します。 既知の問題は次の分野に分かれています。  
  
-   0A1 エラー通知  
  
-   ビジネス アクティビティ監視 (BAM)  
  
-   インストールと構成  
  
-   その他  
  
## <a name="0a1-notification-of-failure"></a>0A1 エラー通知  
  
### <a name="btarn-does-not-perform-cross-field-validation-for-the-cidx-process-configuration-property-and-the-0a1-agreement-property"></a>BTARN で CIDX プロセス構成プロパティと 0A1 アグリーメント プロパティのクロスフィールド検証が実行されない  
 0A1 アグリーメントが CIDX でサポートされない場合でも、プロセス構成プロファイルを使用しているアグリーメントの "0A1 アグリーメント" プロパティを "0A1" に設定しておくと、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] でそのプロファイルの "標準" プロパティを "CIDX" に設定できてしまいます。  
  
## <a name="business-activity-monitoring"></a>ビジネス アクティビティの監視  
  
### <a name="duplicate-column-data-appears-in-the-business-activity-monitoring-reports"></a>ビジネス アクティビティ監視レポートで列データが重複して表示される  
 BAM アクティビティ Web レポートの [ActivityID] 列と [PIPInstanceID] 列に同じ内容が格納されます。 このデータは、PIP (Partner Interface Process) インスタンス ID を正確に反映しています。 ActivityID は、この値を使用して内部照合を行います。 このメッセージは無視してかまいません。  
  
### <a name="empty-data-columns-in-the-business-activity-monitoring-web-reports"></a>ビジネス アクティビティ監視 Web レポートに空のデータ列がある  
 ビジネス アクティビティ監視 (BAM) の Web レポートに、0A1 メッセージ プロセスのデータがまったく記載されません。 Web レポートの 0A1 メッセージの列が "Initiated 0A1" でハード コードされます。  
  
## <a name="installation-and-configuration"></a>インストールと構成  
  
### <a name="groups-and-users-in-either-the-biztalk-application-users-group-and-the-biztalk-server-administrators-group-must-be-in-the-same-domain"></a>BizTalk Application Users グループと BizTalk Server Administrators グループのいずれかで、グループとユーザーが同じドメインに存在する必要がある  
 [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] では、BizTalk Application Users グループと BizTalk Server Administrators グループのどちらにでもグループを追加できます。 ただし、BizTalk Application Users グループまたは BizTalk Server Administrators グループに所属する個々のユーザー アカウントとグループが同じドメインに属していることが必要です。  
  
### <a name="uninstallation-of-btarn-fails-if-biztalk-server-is-removed-first"></a>BizTalk Server を先に削除すると BTARN のアンインストールに失敗する  
 削除する前に BizTalk Server を削除する場合[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]エラーなく削除処理が失敗しました。 この問題を解決するを再インストールし、BizTalk Server を再構成し、削除[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]です。  
  
### <a name="distributed-deployment-requires-a-domain-controller"></a>分散展開にドメイン コントローラが必要である  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] を 1 台のサーバーにインストールし、構成に使用する [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] データベースを別のサーバーにインストールしているようなマルチサーバー環境では、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] を展開する際にドメイン コントローラーが必要になります。  
  
### <a name="custom-pip-configurations-are-not-supported"></a>カスタム PIP 構成がサポートされていない  
 現在のリリースの [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] では、カスタム要素または他の RosettaNet 以外の標準情報による PIP の構成はサポートしていません。  
  
### <a name="btarn-automatically-starts-the-single-sign-on-service"></a>BTARN でシングル サインオン サービスが自動的に開始される  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] がシングル サインオン (SSO) サービスを必要としているのにそのサービスが実行されていない場合、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は自動的に SSO を開始します。  
  
### <a name="the-configuration-program-will-not-remove-btarn-virtual-directories-from-the-excluded-paths-list-when-webapps-is-not-configured-for-the-default-web-site"></a>WebApps が既定の Web サイト用に構成されていない場合、構成プログラムによりエクスクルード パスの一覧から BTARN 仮想ディレクトリが削除されない  
 Web アプリケーションの仮想フォルダーが既定の Web サイトではなく、SharePoint Server になるように構成されていた [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] インストールの構成を解除する場合は、解除後に btarnapp および btarnhttpreceive 仮想ディレクトリを [SharePoint のサーバー管理] サイトの [エクスクルード パス] 一覧から手動で削除する必要があります。 これは、Web アプリケーションの仮想フォルダーを SharePoint Server に構成するときに、btarnapp および btarnhttpreceive を [エクスクルード パス] 一覧に手動で追加する必要があるためです。 構成プログラムでは、これらのディレクトリを [エクスクルード パス] 一覧から自動的に削除できません。  
  
## <a name="miscellaneous"></a>その他  
  
### <a name="btarn-will-receive-messages-encrypted-in-either-encryption-algorithm"></a>どちらの暗号アルゴリズムで暗号化されているメッセージでも受信する  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] の受信パイプラインは、メッセージの暗号化に使用されるプロトコルと、このフィールドの Encoding 設定が一致しない場合でも、メッセージを受信して暗号化を解除します。 したがって、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] RC2 40 または 3 des で暗号化されているメッセージを受信します。  
  
### <a name="btarn-requires-a-signal-in-a-single-action-synchronous-scenario"></a>シングル アクション同期シナリオでシグナルが必要である  
 シングル アクションの同期シナリオでは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は常にシグナルを要求し、シグナルを生成します。 この動作は、シングル アクションの同期シナリオではシグナルの必要性が場合に応じて変化する RosettaNet の仕様とは異なります。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] が応答側であれば、開始側からのメッセージに応答して常にシグナルを生成します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] が開始側であれば、応答側からのシグナルを常に要求します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は、シグナルを受信しなかった場合、プロセス構成設定の `Time To Perform` プロパティに指定された時間が経過するとタイムアウトになり、0A1 メッセージを生成します。  
  
### <a name="btarn-supports-utf-16-in-received-messages"></a>受信メッセージで UTF-16 がサポートされる  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]受信し、utf-16 の文字セットを持つメッセージを処理します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]utf-8 の文字セットを含むメッセージを送信します。  
  
### <a name="namespaces-must-be-stripped-from-response-messages-mapped-from-request-messages"></a>要求メッセージからマップされた応答メッセージから名前空間を削除する必要がある  
 ダブル アクションのシナリオのプライベート プロセスで BizTalk マッパーを使用すると、BizTalk マッパーは、要求メッセージからマップされた応答メッセージ インスタンスの一部の要素タグに名前空間を追加します。 この名前空間により、送信パイプラインで障害が発生します。 したがって、この名前空間は削除する必要があります。 そのためには、HeaderHelper サンプルを使用します。 詳細については、次を参照してください[Double Action PIPAutomation Orchestration &#91;。RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)と[手順 4: HeaderHelper プロジェクト &#91; を作成します。RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-headerhelper-project.md).  
  
### <a name="changing-uri-settings-requires-iisreset"></a>URI 設定を変更すると IISRESET が必要になる  
 セットアップ プログラムの実行中に、受信と送信の .aspx ページが使用する URI 設定、および受信と送信のアダプタの URI 設定が行われます。 .aspx ページまたはアダプタがインストールされているコンピュータの名前を変更する場合は、この設定を変更する必要があります。 構成処理を再実行することでこれらの設定を変更できますが、そのためには、構成設定をすべてリセットする必要があります。 URI 設定のみを変更するには、関連付けられたレジストリ キー (`AsyncReceivePortURI`、`RNIFSenderURI`、および `SyncReceivePortURI`) を変更します。 このレジストリ設定のいずれかを変更した後は、変更を有効にするため、IISRESET を実行する必要があります。 これは、後で使用するために [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] が設定をキャッシュしているためです。 IISRESET の実行後は、BizTalk サービスも再開する必要があります。  
  
### <a name="btarn-does-not-enforce-restrictions-on-rnif-v11-enumerations"></a>BTARN が RNIF v1.1 列挙には制約を実行しない  
 RosettaNet Implementation Framework (RNIF) Specification v1.1 では、一部の RNIF スキーマ列挙に制限を指定します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]これらの制限を強制しませんしがこれらの制限事項に対して検証されません。 この制約は RNIF V2.01 には適用されません。  
  
 これは、以下の Service Header 要素に適用されます。  
  
-   `GlobalBusinessActionCode`  
  
-   `GlobalPartnerClassificationCode`  
  
-   `GlobalBusinessServiceCode`  
  
-   `GlobalProcessCode`  
  
-   `GlobalProcessIndicatorCode`  
  
-   `VersionIdentifier`  
  
### <a name="performancecontrolrequest-parameters-will-not-override-default-process-configuration-settings"></a>PerformanceControlRequest パラメーターが既定のプロセス構成設定を上書きしない  
 受信メッセージでは、サービス ヘッダーに `PerformanceControlRequest` パラメーターを組み込むことができます。 これらのパラメーターで行われた、プロセス構成設定で設定されている Time to Acknowledge (Receipt) と Time to Perform の時間遅延パラメータの値を含める、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理コンソールです。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]基づくこの遅延時間を動的に設定しません、`PerformanceControlRequest`受信メッセージ内のパラメーターです。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]プロセス構成設定で設定する既定の PIP 値から時間遅延を引き継ぎます。 この処理は RNIF (RosettaNet Implementation Framework) Specification V1.1 に準拠しています。  
  
### <a name="the-pip-name-and-pip-version-of-double-action-messages-are-case-sensitive"></a>ダブルアクション メッセージの PIP 名と PIP バージョンで大文字と小文字が区別される  
 応答メッセージの PIP 名および PIP バージョンの大文字と小文字の区別が、元のダブル アクション要求メッセージの対応する値と異なる場合、開始側 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は応答メッセージを無効として拒否し、応答側に例外を返します。  
  
### <a name="btarn-does-not-support-changing-agreement-settings-while-there-are-active-processes"></a>アクティブなプロセスが存在する間はアグリーメントを変更できない  
 クリックすると、すぐにアグリーメントのプロパティへの変更が適用されます**適用**または**OK**を受け付けるようにします。 アグリーメントを変更すると、そのアグリーメントが関係している、既に実行中のプロセスまたは新しいプロセスでの新しいアクティビティで、変更されたアグリーメント プロパティが使用されます。 アグリーメントを変更した時点で実行中のプロセスがあった場合、以前のアグリーメント プロパティが既にメッセージに使用されていた可能性があります。 このプロセスの新しいメッセージでは、新しいアグリーメント設定が使用されるので、予測不可能な結果が生じることがあります。 アグリーメント設定の変更は、実行中のプロセスがないときに行うことをお勧めします。  
  
### <a name="btarn-will-not-perform-cross-field-validation-after-changes-to-a-process-configuration-profile"></a>プロセス構成プロファイルの変更後にスフィールド検証が実行されない  
 プロセス構成プロファイルを作成してからアグリーメントを作成すると、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] でクロスフィールド検証が実行され、アグリーメントとプロファイルのプロパティに互換性があることが確認されます。 たとえば、"CIDX" に設定されている標準プロパティを持つプロファイルに対して、アグリーメントの 0A1 アグリーメント プロパティが "非 0A1" に設定されていることが確認されます。 ただし、アグリーメントの作成後に、プロセス構成プロファイルを変更する場合は、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]クロス フィールド検証は実行されません。 プロパティ変更した場合、標準的な"RosettaNet"から"CIDX"に[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]"0A1"に、アグリーメントの 0A1 アグリーメント プロパティを設定することを確認できません。  
  
### <a name="errors-will-result-if-all-orchestrations-are-not-started"></a>全部のオーケストレーションを開始しないとエラーが発生する  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] セットアップ プログラムでは 9 つのオーケストレーションがインストールされます。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] がメッセージを正常に処理するには、処理を開始する前に、これら 9 つのオーケストレーションをすべてバインド、登録、開始する必要があります。 詳細については、BizTalk Server ヘルプの「BizTalk エクスプ ローラーのオーケストレーション管理」または「オーケストレーション管理」のトピックを参照してください。  
  
### <a name="rnifreceiveaspx-does-not-remove-the-mime-bottom-boundary-from-a-message"></a>RNIFReceive.aspx でメッセージから MIME の下位境界が削除されない  
 RNIFReceive.aspx ページが、パートナーの RNIFSend.aspx ページからメッセージを受信すると、メッセージには MIME ヘッダー、および MIME の上下の境界値 (64 進数) が埋め込まれます。 RNIFSend.aspx は、ヘッダーと境界を RNIF 送信のメッセージに追加します。 RNIFReceive.aspx は、メッセージをパブリック プロセスに送信する前に、メッセージから MIME ヘッダーと境界を削除する必要があります。 RNIFReceive.aspx は MIME ヘッダーと上位境界は削除しますが、下位境界は削除しません。 下位境界が存在しても、パブリック プロセスにおけるメッセージの処理には影響ありません。  
  
### <a name="btarn-does-not-support-a-case-sensitive-configuration-of-sql-server-databases"></a>SQL Server データベースの大文字小文字の区別の設定がサポートされない  
 加えた場合[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベースおよびデータベース オブジェクトが、大文字小文字を区別、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理コンソールがデータベース リソースを見つけることはできませんし、例外をスローします。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベースおよびデータベース オブジェクトを大文字にする必要があります。  
  
### <a name="all-queries-in-database-maintenance-scripts-should-be-written-for-utc-time"></a>データベース管理スクリプトのすべてのクエリを UTC 時刻形式で記述しなければならない  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] データベースでは協定世界時 (UTC) の時刻を使用します。したがって、このデータベースを管理するためのクエリは、UTC 時刻用に作成する必要があります。 たとえば、管理スクリプトで `GetDate()` コマンドを使用する場合は、それを `GetUTCDate()` に変更する必要があります。  
  
### <a name="a-publicresponder-orchestration-will-reject-a-duplicate-request-action-message"></a>PublicResponder オーケストレーションが重複する要求アクション メッセージを拒否する  
 `PublicResponder` オーケストレーション (PublicResponderV11.odx) は重複する要求アクション メッセージを受け取ると、イベント ログに警告を記録してから、メッセージを拒否します。 応答側オーケストレーションの完了後に重複メッセージを受け取ると、サブスクリプションがないため、BizTalk Server がメッセージを停止します。  
  
### <a name="transmission-errors-will-not-be-shown-in-bam-if-the-public-process-has-stopped"></a>パブリック プロセスが停止した場合に転送エラーが BAM に表示されない  
 パブリック プロセスのオーケストレーションがその最終メッセージを処理するときに送信エラーが発生すると、イベント ログと HAT にはエラーが表示されますが、BAM には表示されません。 オーケストレーションが停止しているため、BAM にこのエラー メッセージを表示できません。  
  
### <a name="the-pipelineexe-tool-cannot-be-used-to-debug-a-btarn-receive-pipeline"></a>pipeline.exe ツールを使用して BTARN 受信パイプラインをデバッグできない  
 受信パイプラインをデバッグする場合、パイプラインをホストするポートを作成する必要があります。 BizTalk Server は、pipeline.exe ツールを使用してデバッグすることはできません。  
  
### <a name="an-error-may-be-generated-for-a-retried-message-that-is-successfully-processed-after-the-orchestration-finishes"></a>オーケストレーション完了後に正常に処理されたメッセージを再送するとエラーが生成される  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] では、プロセス フローを表すためにオーケストレーションを使用しています。 再試行メッセージがいくつか再試行される場合、再試行メッセージの 1 つが BizTalk MessageBox に到着しないうちにオーケストレーションが正常に終了することがあります。 この現象が発生すると、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] により、"完了したが破棄された" ことを示すエラー メッセージが生成されます。 プロセスが終了したかどうかを判断するには、基幹業務 (LOB) アプリケーションを確認する必要があります。 正常に終了したことが LOB アプリケーションで確認できた場合は、"完了したが破棄された" ことを示すエラー メッセージを無視してかまいません。  
  
### <a name="an-xml-file-exported-from-trackingxls-may-have-incorrect-fields"></a>tracking.xls からエクスポートされた XML ファイルに間違ったフィールドが含まれている  
 tracking.xls ファイルに新しい追跡ビューを定義してこのファイルから XML ファイルをエクスポートすると、一部のフィールド名が若干変更されます。 これを修正するには、カスタマイズした tracking.xml ファイルのフィールドを、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] のセットアップ プログラムでインストールされた標準の tracking.xml フィールドと照合します。  
  
### <a name="rnif-11-service-header-schema-for-signals-and-responses-may-need-modification"></a>シグナルと応答用の RNIF 1.1 サービス ヘッダー スキーマの変更が必要になる  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は、既定では RosettaNet ヘッダー スキーマをすべて送出します。 以下で説明するように、一部の実装では、Signal Control ノードと Action Control ノードの使い方が他と異なります。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は、既定では Signal Control 要素を以下のように送出します。 場合によっては、Action Control 要素にも同様のことが言えます。  
  
```  
<!ELEMENT SignalControl (  
          InstanceIdentifier,  
          PartnerRoute,  
          SignalIdentity,  
          inResponseTo)>  
```  
  
 使用するソリューションにこのシーケンスが必要な場合は、何もする必要がありません。  
  
 また、実装によっては次のコードを使用してください。  
  
```  
<!ELEMENT SignalControl (  
          inResponseTo,  
          InstanceIdentifier,  
          PartnerRoute,  
          SignalIdentity)>  
```  
  
 使用するソリューションにこのシーケンスが必要な場合は、サポート技術情報の記事 889523 を参照してください。 このソフトウェア更新プログラムによって、対応する XML スキーマが変更されます。 この更新プログラムは RNIF 1.1 プロセスのみに影響することに注意してください。  
  
### <a name="pipautomationgetaction-sql-stored-procedure-needs-update"></a>PipAutomationGetAction SQL ストアド プロシージャの更新が必要である  
 単一レコードをロックするには、PipAutomationGetAction SQL ストアド プロシージャを更新する必要があります。 次の行を削除します。  
  
```  
IF @@ERROR <> 0  
    UPDATE MessagesToLOB SET Delivered = -1 WHERE MessageID = @tempGUID  
```  
  
 正しい PipAutomationGetAction ストアド プロシージャは、次のとおりです。  
  
```  
CREATE PROCEDURE PipAutomationGetAction  
AS  
 SET TRANSACTION ISOLATION LEVEL READ COMMITTED  
BEGIN TRANSACTION  
DECLARE @tempGUID nvarchar(36)  
SELECT TOP 1 @tempGUID = MessageID FROM MessagesToLOB WITH (READPAST,UPDLOCK,ROWLOCK)  
   WHERE Delivered = 0 AND MessageCategory = 10  
  ORDER BY TimeCreated  
  SELECT PIPInstanceID,DestinationPartyName,SourcePartyName,PIPCode,PIPVersion, ServiceContent FROM MessagesToLOB  
   WHERE MessageID = @tempGUID  
For xml auto  
UPDATE MessagesToLOB SET Delivered = 1 WHERE MessageID = @tempGUID  
 COMMIT TRANSACTION  
GO  
```  
  
### <a name="you-can-customize-aspx-code-to-return-the-error-description"></a>エラーの説明を返すように aspx コードをカスタマイズできる  
 エラーの説明を記録したり送信したりする必要がある場合、aspx コードをカスタマイズして、応答メッセージに実際のテキストを含めることができます。 そのためには、HttpResponse.Status (本来の asp 要求の応答オブジェクト) または HttpWebResponse.StatusDescription ([!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] コールにより、HttpWebRequest オブジェクトの GetResponse メソッドに返される) を使用します。 該当する応答オブジェクトのいずれかから戻り値を返すには、Response.Status 値を、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] に付属の aspx コードに設定されている Response.StatusCode の設定値と同様に設定します。  
  
### <a name="rnif-11-messages-cannot-be-read-in-plain-text-from-non-repudiation-tables-if-the-encoding-method-is-set-to-base64"></a>エンコード方式を Base64 に設定している場合に否認不可テーブルから RNIF 1.1 のメッセージをプレーン テキストで読むことができない  
 これはエンコード方式が Base64 に設定されている場合にのみ発生します。 エンコード方式が quoted-printable または 8 ビットに設定されている場合は、否認不可テーブルからメッセージをクリア テキストで読むことができます。 メッセージを参照するには、メッセージ ファイルを拡張子 *.eml で保存してから、Outlook Express でそれを開くと、自動的にデコードされます。 または、以下のコードを使用すると、Base64 でエンコードされているメッセージを否認不可テーブルから読むことができます。  
  
```  
byte[] textBytes = Convert.FromBase64String(txtEncodedText.Text);  
string plainText = Encoding.UTF8.GetString(textBytes);  
txtOutput.Text = plainText;  
```  
  
## <a name="see-also"></a>参照  
[トラブルシューティングと既知の問題](troubleshooting-and-known-issues-in-rosettanet.md)