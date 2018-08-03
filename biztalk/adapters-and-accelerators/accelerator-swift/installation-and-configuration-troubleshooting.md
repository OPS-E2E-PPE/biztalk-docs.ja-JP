---
title: インストールと構成のトラブルシューティング |Microsoft Docs
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
ms.openlocfilehash: 10c0816508d2efb05dbac14797f80ffef12765fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967179"
---
# <a name="installation-and-configuration-troubleshooting"></a>インストールと構成のトラブルシューティング
## <a name="setup-is-unable-to-deploy-the-runtimeschemas-assembly"></a>RuntimeSchemas アセンブリを配置できません。  
  
### <a name="symptom"></a>現象  
 A4SWIFT セットアップ プログラムは RuntimeSchemas.dll をデプロイできました。 アセンブリがセットアップ後に手動で展開されていない、A4SWIFT 構成ウィザードが失敗します。  
  
### <a name="possible-cause"></a>考えられる原因  
 次の条件のいずれかが存在します。  
  
- 実行時のスキーマ アセンブリは A4SWIFT の最初のインストールを実行しようとしたときに既に展開されています。  
  
- Microsoft [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] A4SWIFT をインストールしようとするコンピューターで開始されませんでした。  
  
- 実行時のスキーマ アセンブリは A4SWIFT をアップグレードしようとして、別のアセンブリによって参照されているときに既に展開されています。 A4SWIFT ランタイム スキーマ アセンブリの妨げられてこの展開解除は、プログラムをアップグレードします。  
  
### <a name="solution"></a>解決方法  
 問題の性質に応じて、次のように、手順に従います。  
  
- 実行時のスキーマ アセンブリが A4SWIFT の最初のインストールを実行しようとするときに既に展開されている場合は、Microsoft の BizTalk エクスプ ローラーを開きます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]Microsoft のアセンブリを右クリックします。クリックして Solutions.FinancialServices.SWIFT.RuntimeSchemas、展開解除します。 BizTalk 展開ウィザードを使用して、RuntimeSchemas.dll からの最新バージョンを展開する *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Assemblies します。  
  
- 場合[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]が開始されていない起動[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]で、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]サービス マネージャー。 BizTalk 展開ウィザードを使用して、RuntimeSchemas.dll からの最新バージョンを展開する *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Assemblies します。  
  
- A4SWIFT をアップグレードしようとしてによって参照されて、実行時のスキーマ アセンブリが既に展開されている場合、別のアセンブリが BizTalk エクスプローラで、参照元のアセンブリを展開解除し、RuntimeSchemas.dll BizTalk エクスプ ローラーでの展開を解除します。 BizTalk 展開ウィザードを使用して、RuntimeSchemas.dll からの最新バージョンを展開する *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Assemblies します。  
  
## <a name="after-the-web-components-feature-is-removed-message-repair-and-reconciliation-is-incorrectly-shown-as-uninstalled"></a>Web コンポーネントの機能が削除されると、Message Repair and Reconciliation が不適切にアンインストール  
  
### <a name="symptom"></a>現象  
 A4SWIFT の機能を Message Repair and New Submission の Web コンポーネントを削除した後は、アンインストールしてインストール、または Message Repair および調整機能 (または A4SWIFT コンポーネント) を構成できません。 Message Repair and Reconciliation がインストールされている場合は、A4SWIFT には、機能がインストールされていることは認識されません。 インストール、変更、または Message Repair and プログラムの追加/削除 (コントロール パネルから表示される) 内からの調整を削除しようとすると、プログラムの追加/削除は、機能がインストールされていないことを示します。  
  
### <a name="possible-cause"></a>考えられる原因  
 削除された、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Message Repair and New Submission の機能および Message Repair and Reconciliation 機能の Web コンポーネントをインストールした後、管理者がグループ化します。 Web コンポーネントの機能を削除した場合 (のメンバーにならなくても行うことができる[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Administrators グループ)、A4SWIFT セットアップ プログラムは、メッセージを修復するファイルを削除および調整の機能に依存しています。 これらのファイルには、ConfigFramework.exe が含まれます。  
  
### <a name="solution"></a>解決方法  
 この問題が発生した場合は次のようです。  
  
1. 追加に自分でコンピューターの管理 ウィンドウで、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者グループ、コンピューターからログオフしてログオンし直す。  
  
2. Message Repair and New Submission の機能の Web コンポーネントを再インストールします。  
  
   > [!NOTE]
   >  手順 2 では、A4SWIFT インストールに ConfigFramework.exe を追加します。  
  
3. MRSR 機能を再インストールします。  
  
4. まだしないようにする Web コンポーネント Message Repair and New Submission の機能を削除します。  
  
## <a name="repairing-a4swift-to-add-the-service-folder-can-result-in-improper-access-permissions-for-that-folder"></a>そのフォルダーのアクセス許可 の不適切なアクセスにより、サービスのフォルダーを追加する A4SWIFT を修復します。  
  
### <a name="symptom"></a>現象  
 フォルダーを削除する場合 *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Service からサーバー フォルダーを追加する A4SWIFT セットアップの修復機能は、A4SWIFT に戻り、A4SWIFT インストールが適切に構成されたを実行しますインストールでは、サービスのフォルダーのアクセス許可は正しいされません。 A4SWIFT 管理者および読み取りのフル コントロールと A4SWIFT ユーザーの実行は、適切な権限です。  
  
 これは、サービスのフォルダーが存在する場合に、A4SWIFT セットアップの修復機能を実行する場合にも発生します。 アクセス許可、A4SWIFT 構成ウィザードによって設定されたで上書きされますが正しくない値。  
  
### <a name="possible-cause"></a>考えられる原因  
 Message Repair and New Submission の Web コンポーネントをインストールする機能は、サービスのフォルダーを追加します。 フォルダーを削除し、Message Repair and New Submission の Web コンポーネントを追加する A4SWIFT セットアップの修復 オプションを実行すると、A4SWIFT セットアップでは、構成ウィザード、フォルダーのアクセス許可を設定するには、(ConfigFramework.exe) が実行されません。 構成ウィザードは既に実行されている、ためには、構成をリセットするには、もう一度ウィザードを実行することが困難です。 その結果、修復オプションは、削除されたファイルおよびフォルダーのすべてを再作成されますが、これが正しく設定されていないアクセス許可。  
  
 修復処理は、修復を実行すると、フォルダーが存在する場合にも、サービスのフォルダーのアクセス許可を上書きします。 としての修復を実行する前に、サービスのフォルダーを削除する場合とされます、アクセス許可を設定、構成プログラムを実行する非常に困難です。 同様に、このインスタンスでは、アクセス許可が正しくないあり、それらを手動で設定する必要があります。  
  
### <a name="solution"></a>解決方法  
 この問題が発生した場合、サービスのフォルダーの次のアクセス許可を手動で設定します。  
  
|[グループ名またはユーザー名]|権限|  
|------------------------|----------------|  
|A4SWIFT 管理者|フル コントロール|  
|A4SWIFT ユーザー|読み取りと実行|  
  
 これらのアクセス許可を設定するには、ように進めます。  
  
 [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーに移動 *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Service します。  
  
1.  サービスのフォルダーを右クリックし、をクリックして**プロパティ**、 をクリックし、**セキュリティ**タブ。  
  
2.  グループまたはユーザー名ペインで、サービスのプロパティ ダイアログ ボックスの次のようにクリックします**追加**、入力 ***\<サーバー名\>* \A4SWIFT 管理者**、 をクリックし、 **ok**。  
  
    > [!NOTE]
    >  A4SWIFT の管理者グループがドメイン グループの場合は、次のように入力してください ***\<ドメイン名\>* \A4SWIFT 管理者**します。  
  
3.  手順 2. を繰り返します ***\<サーバー名\>* \A4SWIFT ユーザー**、または **\<*ドメイン名*\>\A4SWIFT ユーザー**場合、A4SWIFT ユーザーのグループは、ドメイン グループです。  
  
4.  グループまたはユーザーの名ペインで選択**A4SWIFT 管理者**します。 アクセス許可 ウィンドウで、次のように選択します。**許可**の**フルコントロール**します。  
  
5.  グループまたはユーザーの名ペインで選択**A4SWIFT ユーザー**します。 アクセス許可 ウィンドウで、次のようにクリックします。**許可**の**読み取りと実行**、**フォルダー内容の一覧表示**、および**読み取り**します。  
  
6.  **[OK]** をクリックします。  
  
## <a name="upgrade-results-in-a-side-by-side-installation-of-two-versions-of-a4swift"></a>A4SWIFT の 2 つのバージョンのサイド バイ サイドでインストールのアップグレードの結果  
  
### <a name="symptom"></a>現象  
 アップグレードしようとする[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]A4SWIFT の以前のバージョンは完全に削除できません。 コントロール パネルからプログラムの追加/削除を実行する場合、現在インストールされているプログラムの一覧は、現在と以前のバージョンを表示する可能性があります。  
  
### <a name="possible-cause"></a>考えられる原因  
 次の条件のいずれかは、上記が発生することがあります。  
  
- アップグレードしようとしています。 ユーザーがのメンバーではない、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  
  
- [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] (MSSQLSERVER) サービスが停止します。  
  
- サイレント アップグレードを使用して、実行して、 **setup.exe/addlocal**コマンド。  
  
### <a name="solution"></a>解決方法  
 サイド バイ サイドでインストールされないようにする[!INCLUDE[btaA4SWIFToldest](../../includes/btaa4swiftoldest-md.md)]と[!INCLUDE[btaA4SWIFT2.3abbrev](../../includes/btaa4swift2-3abbrev-md.md)]アップグレード中に発生していることを確認 (ログオンしているユーザー) のメンバー、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators グループ、および、 [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] (MSSQLSERVER) サービスが開始します。  
  
 サイド バイ サイドでインストール終了するかどうかは[!INCLUDE[btaA4SWIFToldest](../../includes/btaa4swiftoldest-md.md)]または[!INCLUDE[btaA4SWIFT2.1abbrev](../../includes/btaa4swift2-1abbrev-md.md)]と[!INCLUDE[btaA4SWIFT2.3abbrev](../../includes/btaa4swift2-3abbrev-md.md)]、手順に従います。  
  
1. SWIFT メッセージ フォルダー内のデータをバックアップします。  
  
2. ログオン、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] BTS Administrators のメンバーとしてグループ化、および MSSQLSERVER サービスが実行されていることを確認します。  
  
3. A4SWIFT の以前のバージョンを削除します。  
  
4. もう一度 A4SWIFT の最新バージョンにアップグレードします。 今度は、アップグレードを使用して、サイド バイ サイド インストールは作成されません。  
  
5. BizTalk 展開ユーティリティを使用して、手動で、Microsoft を展開解除します。Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll、A4SWIFT インストールの場所の [アセンブリ] フォルダーから展開します。 このツールの詳細については、次を参照してください。 [BRE 配置ユーティリティ](../../adapters-and-accelerators/accelerator-swift/bre-deployment-utility.md)します。  
  
## <a name="the-uninstall-or-upgrade-process-may-not-complete-correctly-if-you-do-not-restart-when-prompted"></a>入力を求められたら再起動しない場合、アンインストールまたはアップグレード プロセスが正常に完了しない可能性があります。  
  
### <a name="symptom"></a>現象  
 アンインストールまたはアップグレード プロセスが正常に完了しません。  
  
### <a name="possible-cause"></a>考えられる原因  
 プロジェクトを展開解除がない場合は、既存の展開済みのアセンブリを参照する、A4SWIFT 構成の変更を有効にするには、システムを再起動する必要があることを示すプロンプトが表示される可能性があります。 クリックしない場合**はい**すぐに再起動すると、グローバル アセンブリ キャッシュでは削除割り当てられていた一部のアセンブリは削除できません、追加のアンインストールまたはアップグレードのプロセスが正常に完了しない原因となっています。  
  
### <a name="solution"></a>解決方法  
 既存の展開済みアセンブリを参照する任意のプロジェクトを展開解除し、アンインストールまたはアップグレード プロセスをもう一度実行します。  
  
## <a name="if-the-iis-admin-service-is-stopped-during-setup-you-must-reconfigure-the-webservice-feature"></a>セットアップ中に、IIS Admin サービスを停止すると場合に、web サービスの機能を再構成する必要があります。  
  
### <a name="symptom"></a>現象  
 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]構成ウィザードが web サービスの機能を正しく構成されていません。 次のエラーが表示されます。  
  
 "MRSR アーティファクトを作成できませんリモート サーバーに接続できません。"。  
  
### <a name="possible-cause"></a>考えられる原因  
 実行したときに、IIS 管理サービスが停止しました、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]構成ウィザード。  
  
### <a name="solution"></a>解決方法  
 構成プロセスが正常に完了するには、ように進めます。  
  
1. 閉じる、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]構成コンソール。  
  
2. IIS 管理サービスを再起動します。  
  
3. 実行 *%programfiles%* \Microsoft BizTalk Accelerator for SWIFT\Configuration.exe します。  
  
4. [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]構成コンソールで、**機能の構成解除**選び**WebService**します。  
  
5. 構成を解除すると、構成コンソールで web サービス機能の状態が表示されることを確認します。  
  
6. 選択**構成の適用**します。  
  
   > [!NOTE]
   >  A4SWIFT 構成ウィザードは、web サービスの機能を正しく構成してようになりました。  
  
## <a name="a4swift-configuration-will-fail-if-the-biztalkserverapplication-host-was-not-created-in-biztalk-server-configuration"></a>A4SWIFT 構成には、BizTalkServerApplication ホストは、BizTalk Server の構成で作成されていない場合は失敗します。  
  
### <a name="symptom"></a>現象  
 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]構成ウィザードが web サービスの機能を正しく構成されていません。 次のエラーが表示されます。  
  
 "MRSR アーティファクトを作成できません: オブジェクト参照がオブジェクトのインスタンスに設定されていません"。  
  
### <a name="possible-cause"></a>考えられる原因  
 BizTalk Server ランタイムの構成時に、インプロセス ホストとホスト インスタンスが作成されていません。  
  
### <a name="solution"></a>解決方法  
 A4SWIFT 構成を修復するには、ように進めます。  
  
- BizTalk Server 管理コンソールで、ホストを作成します。 現在実行中のインスタンスを用意する必要はありません。  
  
- RepairBAS ツールを実行、 *%programfiles%* \Microsoft BizTalk Accelerator for swift \sdk\tools フォルダーの A4SWIFT インストールします。  
  
  これを行うように進めます。  
  
1.  開始**BizTalk Server 管理**コンソール。  
  
2.  BizTalk Server 管理コンソールで  **BizTalk Server 管理**の順に展開**BizTalk グループ**、順に展開**プラットフォームの設定。**  
  
3.  右クリックして**ホスト**、] をポイント**新規**、し、[**ホスト**します。  
  
4.  ホストのプロパティ] 画面の [全般] ペインで、[次のように入力します。  
  
    -   ホスト名: **BizTalkServerApplication**  
  
    -   型:**インプロセス**  
  
    -   Windows グループ:  **\<*ドメイン*\>\BizTalk Application Users** (または BizTalk プロセスを実行するための BizTalk Server の構成時に設定したアカウントアプリケーションの場合)  
  
    -   [オプション] の両方を選択します**ホストの追跡を許可する**と**グループで、既定のホストを確認**します。  
  
5.  **[OK]** をクリックします。  
  
6.  クリックして**開始**実行順にクリックします。 型**cmd**  をクリックし、 **OK**します。  
  
7.  コマンド プロンプトに移動します * %programfiles%%% ***\Microsoft BizTalk Accelerator for swift \sdk\tools**します。  
  
8.  型**RepairBAS.exe**しキーを押します**Enter**します。  
  
## <a name="you-must-change-the-bre-deployment-configuration-file-when-running-the-bre-deployment-utility-on-a-64-bit-computer"></a>64 ビット コンピューターで BRE 配置ユーティリティを実行すると、BRE 展開構成ファイルを変更する必要があります。  
  
### <a name="symptom"></a>現象  
 BRE 配置ユーティリティが正しく機能しないまたは実行すると、64 ビット コンピューターで既定以外のディレクトリ (C:\Program files \microsoft BizTalk Accelerator for SWIFT) 以外で 32 ビット コンピューターで。  
  
### <a name="possible-cause"></a>考えられる原因  
 BRE 配置ユーティリティは正しく動作しませんにある BREDeployment.exe.config ファイル内のパスを変更するまで、\<ドライブ\>: \Program Files\Microsoft BizTalk Accelerator for swift \sdk\tools フォルダー。  
  
### <a name="solution"></a>解決方法  
 ユーティリティの構成を更新するには、メモ帳で BREDeployment.exe.config を開き、基本ポリシー、スキーマ、およびボキャブラリのディレクトリのフォルダーを変更します。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティング: 問題と解決策](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)