---
title: インストールと構成のトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, troubleshooting
- configuring, troubleshooting
- troubleshooting, configuring
- troubleshooting, installing
ms.assetid: 25a2f6c5-c049-4042-8e38-4f7a2556e066
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62cb7d6181c7be44f7095a6c1d1149132df4e21e
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "25968104"
---
# <a name="installation-and-configuration-troubleshooting"></a>インストールと構成のトラブルシューティング
## <a name="setup-is-unable-to-deploy-the-runtimeschemas-assembly"></a>RuntimeSchemas アセンブリを配置できません。  
  
### <a name="symptom"></a>現象  
 A4SWIFT セットアップ プログラムは、RuntimeSchemas.dll を展開できませんでした。 アセンブリはセットアップ後に手動で展開されず、A4SWIFT 構成ウィザードは失敗します。  
  
### <a name="possible-cause"></a>考えられる原因  
 次の条件のいずれかが存在する場合します。  
  
-   実行時のスキーマ アセンブリは、A4SWIFT の最初のインストールを実行しようとしたときに既に展開されていた。  
  
-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] A4SWIFT をインストールしようとするコンピューターで開始されませんでした。  
  
-   実行時のスキーマ アセンブリは、A4SWIFT をアップグレードしようとしています。 別のアセンブリが参照したするとに既に展開されていた。 このされませんでしたの展開解除、A4SWIFT によって実行時のスキーマ アセンブリのでは、プログラムをアップグレードします。  
  
### <a name="solution"></a>解決方法  
 問題の性質に応じて、次のように、手順に従います。  
  
-   BizTalk エクスプ ローラーを開く場合は、実行時のスキーマ アセンブリは、A4SWIFT の最初のインストールを実行しようとしたときに既に展開されていた、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]、アセンブリを右クリックして[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]です。Solutions.FinancialServices.SWIFT.RuntimeSchemas をクリックして展開を解除します。 RuntimeSchemas.dll の最新バージョンを展開する BizTalk 展開ウィザードを使用して *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Assemblies です。  
  
-   場合[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]が開始されませんが、開始[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]で、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]サービス マネージャーです。 RuntimeSchemas.dll の最新バージョンを展開する BizTalk 展開ウィザードを使用して *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Assemblies です。  
  
-   A4SWIFT をアップグレードしようとしています。 してによって参照されたときに、実行時のスキーマ アセンブリが既に展開されている場合、別のアセンブリは BizTalk エクスプローラで、参照元のアセンブリを展開解除し、RuntimeSchemas.dll BizTalk エクスプ ローラーでの展開を解除します。 RuntimeSchemas.dll の最新バージョンを展開する BizTalk 展開ウィザードを使用して *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Assemblies です。  
  
## <a name="after-the-web-components-feature-is-removed-message-repair-and-reconciliation-is-incorrectly-shown-as-uninstalled"></a>Web コンポーネントの機能が削除されると、Message Repair and 調整が不適切にアンインストール  
  
### <a name="symptom"></a>現象  
 A4SWIFT の機能を Message Repair and New Submission の Web コンポーネントを削除した後は、アンインストールをインストールするまたは Message Repair および調整機能 (または A4SWIFT のコンポーネント) を構成することはできません。 Message Repair and 調整がインストールされている場合は、A4SWIFT には、機能がインストールされていることは認識されません。 インストール、変更、または Message Repair and プログラムの追加/削除 (コントロール パネルから表示される) 内からの調整を削除しようとすると、プログラムの追加/削除は、機能がインストールされていないことを示します。  
  
### <a name="possible-cause"></a>考えられる原因  
 削除された、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Message Repair and New Submission の機能および Message Repair and 調整の機能の Web コンポーネントをインストールした後、管理者がグループ化します。 Web コンポーネント機能を削除する場合 (のメンバーでなくて行うことができる[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Administrators グループ)、A4SWIFT セットアップ プログラムがメッセージを修復するファイルを削除して、調整機能に依存しています。 これらのファイルには、ConfigFramework.exe が含まれます。  
  
### <a name="solution"></a>解決方法  
 この問題が発生した場合は、次の手順します。  
  
1.  追加に自分でコンピューターの管理 ウィンドウで、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者グループが、コンピューターからログオフし、再度ログオンします。  
  
2.  Message Repair and New Submission の機能の Web コンポーネントを再インストールします。  
  
    > [!NOTE]
    >  手順 2 では、A4SWIFT インストールに戻す ConfigFramework.exe を追加します。  
  
3.  MRSR 機能を再インストールします。  
  
4.  まだたくない Web コンポーネント Message Repair and New Submission 機能を削除します。  
  
## <a name="repairing-a4swift-to-add-the-service-folder-can-result-in-improper-access-permissions-for-that-folder"></a>Service フォルダーを追加する A4SWIFT を修復することができますと、そのフォルダーの不適切なアクセス許可  
  
### <a name="symptom"></a>現象  
 フォルダーを削除する場合 *%programfiles%* サーバー フォルダーを追加する A4SWIFT セットアップの修復機能は、A4SWIFT に戻します、A4SWIFT インストール環境適切に構成してから実行してから \Microsoft BizTalk Accelerator for SWIFT\Serviceインストールの場合、サービスのフォルダーのアクセス許可は正しいされません。 適切なアクセス許可は、A4SWIFT 管理者および読み取りのフル コントロールと A4SWIFT ユーザーに対して実行します。  
  
 これは、サービスのフォルダーが存在する場合に、A4SWIFT セットアップの修復機能を実行する場合にも発生します。 アクセス許可、A4SWIFT 構成ウィザードによって設定で上書きされます不適切な値です。  
  
### <a name="possible-cause"></a>考えられる原因  
 Message Repair and New Submission の Web コンポーネントをインストールする機能は、サービスのフォルダーを追加します。 フォルダーを削除し、Message Repair and New Submission の Web コンポーネントを追加する A4SWIFT セットアップの修復 オプションを実行すると、A4SWIFT セットアップはフォルダーのアクセス許可を設定するには、(ConfigFramework.exe) の構成ウィザードを実行できません。 構成ウィザードが既に実行されていないため、構成をリセットするには、もう一度ウィザードを実行する非常に困難です。 その結果、削除されたファイルおよびフォルダーのすべての修復オプションが再作成が、アクセス許可が正しく設定ことはできません。  
  
 修復プロセスは、修復を実行すると、フォルダーが存在する場合にも、サービスのフォルダーのアクセス許可を上書きします。 として、ケースの修復を実行する前に、サービスのフォルダーを削除すると、非常に難しくなります、アクセス許可を設定、構成プログラムを実行します。 このインスタンスで同様に、アクセス許可が正しくないあり、それらを手動で設定する必要があります。  
  
### <a name="solution"></a>解決方法  
 この問題が発生した場合、サービスのフォルダーの次のアクセス許可を手動で設定します。  
  
|[グループ名またはユーザー名]|権限|  
|------------------------|----------------|  
|A4SWIFT の管理者|フル コントロール|  
|A4SWIFT のユーザー|読み取りと実行|  
  
 これらのアクセス許可を設定するには、手順に従います。  
  
 [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーに移動 *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Service です。  
  
1.  Service フォルダーを右クリックし、をクリックして**プロパティ**、をクリックし、**セキュリティ**タブです。  
  
2.  グループまたはユーザー名ペインで、サービスのプロパティ ダイアログ ボックスのをクリックして**追加**、入力 ***\<サーバー名\>* \A4SWIFT 管理者**、クリックして**ok**.  
  
    > [!NOTE]
    >  A4SWIFT の Administrators グループがドメイン グループの場合は、次のように入力してください ***\<ドメイン名\>* \A4SWIFT 管理者**です。  
  
3.  手順 2. を繰り返します ***\<サーバー名\>* \A4SWIFT ユーザー**、または **\<*ドメイン名*\>\A4SWIFT ユーザー**場合、A4SWIFT の Users グループは、ドメイン グループです。  
  
4.  グループまたはユーザー名ペインで選択**A4SWIFT 管理者**です。 アクセス許可 ウィンドウで、次のように選択します。**許可**の**フルコントロール**です。  
  
5.  グループまたはユーザー名ペインで選択**A4SWIFT ユーザー**です。 アクセス許可 ウィンドウで、をクリックして**許可**の**読み取りと実行**、**フォルダー内容の一覧**、および**読み取り**です。  
  
6.  **[OK]** をクリックします。  
  
## <a name="upgrade-results-in-a-side-by-side-installation-of-two-versions-of-a4swift"></a>A4SWIFT の 2 つのバージョンのサイド バイ サイド インストールでのアップグレード結果  
  
### <a name="symptom"></a>現象  
 アップグレードしようとする[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]A4SWIFT の以前のバージョンは完全に削除できません。 コントロール パネルの プログラムの追加/削除を実行する場合、現在インストールされているプログラムの一覧は、現在と以前のバージョンを表示する可能性があります。  
  
### <a name="possible-cause"></a>考えられる原因  
 次の条件のいずれかは、上記が発生することがあります。  
  
-   アップグレードしようとしています。 ユーザーがのメンバーではない、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  
  
-   [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] (MSSQLSERVER) サービスが停止します。  
  
-   サイレント アップグレードを使用して、実行して、 **setup.exe/addlocal**コマンド。  
  
### <a name="solution"></a>解決方法  
 サイド バイ サイド インストールされないようにする[!INCLUDE[btaA4SWIFToldest](../../includes/btaa4swiftoldest-md.md)]と[!INCLUDE[btaA4SWIFT2.3abbrev](../../includes/btaa4swift2-3abbrev-md.md)]アップグレード中に発生していることを確認 (ログオン ユーザー) のメンバー、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators グループ、およびを[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)](MSSQLSERVER) サービスが開始します。  
  
 サイド バイ サイド インストール終了するかどうかは[!INCLUDE[btaA4SWIFToldest](../../includes/btaa4swiftoldest-md.md)]または[!INCLUDE[btaA4SWIFT2.1abbrev](../../includes/btaa4swift2-1abbrev-md.md)]と[!INCLUDE[btaA4SWIFT2.3abbrev](../../includes/btaa4swift2-3abbrev-md.md)]、次の手順します。  
  
1.  SWIFT メッセージ フォルダー内のデータをバックアップします。  
  
2.  ログオン、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] BTS Administrators のメンバーとしてグループ化、および MSSQLSERVER サービスが実行されていることを確認してください。  
  
3.  A4SWIFT の以前のバージョンを削除します。  
  
4.  もう一度 A4SWIFT の最新バージョンにアップグレードします。 今度は、アップグレードを使用し、サイド バイ サイド インストールは作成されません。  
  
5.  BizTalk 展開ユーティリティを使用して手動で解除[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]です。Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll、A4SWIFT インストールの場所の Assemblies フォルダーを展開します。 このツールの詳細については、次を参照してください。 [BRE 配置ユーティリティ](../../adapters-and-accelerators/accelerator-swift/bre-deployment-utility.md)です。  
  
## <a name="the-uninstall-or-upgrade-process-may-not-complete-correctly-if-you-do-not-restart-when-prompted"></a>表示されたら再起動しない場合、アンインストールまたはアップグレードの処理が正しく完了しない可能性があります。  
  
### <a name="symptom"></a>現象  
 アンインストールまたはアップグレードのプロセスが正常に完了しません。  
  
### <a name="possible-cause"></a>考えられる原因  
 プロジェクトを展開解除がない場合は、既存の展開済みアセンブリを参照する、A4SWIFT 構成の変更を有効にするには、システムを再起動する必要があることを示すメッセージが表示される可能性があります。 クリックしない場合**はい**をすぐに再起動すると、グローバル アセンブリ キャッシュ内の削除の割り当てられている一部のアセンブリは削除できません、追加のアンインストールまたはアップグレードのプロセスが正常に完了しない原因です。  
  
### <a name="solution"></a>解決方法  
 既存の展開済みアセンブリを参照する他のプロジェクトを展開解除し、もう一度アンインストールまたはアップグレードの処理を実行します。  
  
## <a name="if-the-iis-admin-service-is-stopped-during-setup-you-must-reconfigure-the-webservice-feature"></a>セットアップ中に、IIS Admin サービスを停止すると場合、は、web サービス機能を再構成する必要があります。  
  
### <a name="symptom"></a>現象  
 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]構成ウィザードが web サービス機能を正しく構成されていません。 次のエラーが表示されます。  
  
 "MRSR アーティファクトを作成できませんリモート サーバーに接続できません。"。  
  
### <a name="possible-cause"></a>考えられる原因  
 実行したときに、IIS 管理サービスが停止されました、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]構成ウィザード。  
  
### <a name="solution"></a>解決方法  
 構成プロセスを正常に完了するには、次の手順します。  
  
1.  閉じる、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]構成コンソールです。  
  
2.  IIS 管理サービスを再起動します。  
  
3.  実行 *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Configuration.exe です。  
  
4.  [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]構成コンソールで、**機能の構成解除**し、 **WebService**です。  
  
5.  未使用の領域として、構成コンソールで web サービス機能の状態が表示されていることを確認します。  
  
6.  選択**構成を適用**です。  
  
    > [!NOTE]
    >  A4SWIFT 構成ウィザードは、web サービス機能を正しく構成してようになりました。  
  
## <a name="a4swift-configuration-will-fail-if-the-biztalkserverapplication-host-was-not-created-in-biztalk-server-configuration"></a>BizTalk Server の構成では、BizTalkServerApplication ホストは作成されていない場合は、A4SWIFT 構成は失敗します  
  
### <a name="symptom"></a>現象  
 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]構成ウィザードが web サービス機能を正しく構成されていません。 次のエラーが表示されます。  
  
 "MRSR アーティファクトを作成できません: オブジェクトの参照オブジェクトのインスタンスに設定されていません"。  
  
### <a name="possible-cause"></a>考えられる原因  
 インプロセス ホストとホスト インスタンスは、BizTalk Server ランタイムの構成時に作成されませんでした。  
  
### <a name="solution"></a>解決方法  
 A4SWIFT 構成を修復するには、手順に従います。  
  
-   BizTalk Server 管理コンソールで、ホストを作成します。 今すぐ実行中のインスタンスを設定する必要はありません。  
  
-   RepairBAS ツールを実行、 *%programfiles%* \Microsoft BizTalk Accelerator for swift \sdk\tools フォルダーに、A4SWIFT インストール環境のです。  
  
 これを行うには、次の手順します。  
  
1.  開始**BizTalk Server 管理コンソール**コンソールです。  
  
2.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**の順に展開**BizTalk グループ**、順に展開**プラットフォームの設定。**  
  
3.  右クリック**ホスト**、指す**新規**、し、**ホスト**です。  
  
4.  [ホストのプロパティ] 画面で、[全般] ペインで、次のように入力します。  
  
    -   ホスト名: **BizTalkServerApplication**  
  
    -   型:**インプロセス**  
  
    -   Windows グループ:  **\<*ドメイン*\>\BizTalk Application Users** (または BizTalk プロセスを実行するための BizTalk Server 構成で設定したアカウントアプリケーションの)  
  
    -   [オプション] の両方を選択**ホストの追跡を許可する**と**しやすいように、既定のホスト グループに**です。  
  
5.  **[OK]** をクリックします。  
  
6.  をクリックして**開始**し、[実行] をクリックします。 型**cmd**  をクリックし、 **OK**です。  
  
7.  コマンド プロンプトに移動します。 * % programfiles % ***\Microsoft BizTalk Accelerator for swift \sdk\tools**です。  
  
8.  型**RepairBAS.exe**キーを押します**Enter**です。  
  
## <a name="you-must-change-the-bre-deployment-configuration-file-when-running-the-bre-deployment-utility-on-a-64-bit-computer"></a>64 ビット コンピューターで BRE 配置ユーティリティを実行する場合は、BRE 配置構成ファイルを変更する必要があります。  
  
### <a name="symptom"></a>現象  
 BRE 配置ユーティリティが正しく機能しないまたは実行すると、64 ビット コンピューターで既定以外のディレクトリ (C:\Program files \microsoft BizTalk Accelerator 用 SWIFT) 以外で 32 ビット コンピューターにします。  
  
### <a name="possible-cause"></a>考えられる原因  
 BRE 配置ユーティリティは正しく動きませんにある BREDeployment.exe.config ファイル内のパスを変更するまで、\<ドライブ\>: \Program Files\Microsoft BizTalk Accelerator for swift \sdk\tools フォルダーです。  
  
### <a name="solution"></a>解決方法  
 ユーティリティの構成を更新するには、メモ帳で、BREDeployment.exe.config を開き、基本ポリシー、スキーマ、およびボキャブラリのディレクトリのフォルダーを変更します。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティング: 問題と解決策](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)