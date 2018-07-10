---
title: BizTalk Accelerator を BizTalk Server では、RosettaNet (BTARN) のインストール |Microsoft Docs
description: ハードウェアおよびソフトウェア要件、インストール手順、および BizTalk Server で BTARN の構成手順を参照してください。
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecb8e527abe896719da881f0c7df0e4f5566a90f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005803"
---
# <a name="install-biztalk-accelerator-for-rosettanet"></a>BizTalk Accelerator を RosettaNet をインストールします。

## <a name="overview"></a>概要
Microsoft BizTalk Accelerator は、RosettaNet (BTARN) 用にインストールします。

> [!NOTE]
>  Enterprise エディションの BizTalk Server に、RosettaNet (BTARN) のみ、Enterprise エディションの BizTalk アクセラレータをインストールできます。 、BizTalk Server の Standard Edition でのみ、Standard エディションの BizTalk アクセラレータに RosettaNet (BTARN) をインストールできます。  

 BTARN のインストールには、次の項目が含まれます。  

-   BTARN の管理  

-   BizTalk Orchestration Designer XLANG スケジュール (Partner Interface Process パターン)  

-   RosettaNet Implementation Framework (RNIF)  

-   BTARN データベース  

-   HTTP フロント エンドの Web アプリケーション  

## <a name="hardware-and-software-requirements"></a>ハードウェアとソフトウェアの要件

ハードウェアとソフトウェアの最小要件は、BizTalk Server と同じです。


|                                                                                         |                                                                                BizTalk の要件                                                                                 |                                                                                                                                                                                                                                                            SQL と OS の要件                                                                                                                                                                                                                                                            |
|-----------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                  [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]                   |             [BizTalk Server 2016 のハードウェア/ソフトウェア要件](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)             |                                      **SQL Server のハードウェアおよびソフトウェア要件**: <br/>[SQL Server 2016](https://msdn.microsoft.com/library/ms143506(v=sql.130).aspx)<br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/><br/>**Windows サーバーのハードウェア要件**: <br/>[Windows Server 2016](https://technet.microsoft.com/windows-server-docs/get-started/server-basics)<br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx)                                      |
| [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] <br/><br/> BizTalk Server 2013 | [BizTalk Server 2013 および 2013 R2 のハードウェア/ソフトウェア要件](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md) | **SQL Server のハードウェアおよびソフトウェア要件**: <br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/>[SQL Server 2012](https://msdn.microsoft.com/library/ms143506(v=sql.110).aspx)<br/>[SQL Server 2008 R2](https://msdn.microsoft.com/library/ms143506(v=sql.105).aspx)<br/><br/>**Windows サーバーのハードウェア要件**: <br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx)<br/>[Windows Server 2008 R2](https://technet.microsoft.com/library/dd379511(v=ws.10).aspx) |

> [!TIP] 
> ここにリストされているのは最小のハードウェア要件です。 環境はそれぞれ異なり、ご使用の環境ではこれらを超える要件が必要となる可能性は十分あります。 「[BizTalk Server ソリューションのインストール、サイズ変更、配置、およびメンテナンスを行うための推奨事項](http://social.technet.microsoft.com/wiki/contents/articles/666.recommendations-for-installing-sizing-deploying-and-maintaining-a-biztalk-server-solution.aspx)」を参照してください。 

## <a name="install-and-configure"></a>[インストールと構成]

### <a name="before-you-begin"></a>アンインストールの準備

* BTARN データベースでは、BTARN により、SQL Server コンピューター名とデータベース名のプロパティのみ構成します。 このプロパティについての情報は、レジストリに格納されます。
* メンバーであるアカウントを使用してサインイン、BizTalk Server 管理者グループ。 
* BizTalk Server のダウンロードでは、BTARN セットアップは、`\BizTalk Accelerators`フォルダー。
* BizTalk Server をインストールする必要があります、および SQL Server を実行する必要があります。
* BTARN と BizTalk Server の両方は、ソフトウェアの前提条件として Microsoft .NET Framework が必要です。 複数のバージョンの .NET Framework をコンピューターにインストールした場合、BtarnAPP Web アプリケーションが .NET Framework 4.0 クラシックを参照することを確認します。 この構成は、インターネット インフォメーション サービス (IIS) マネージャーで行えます。  
* BizTalk ホスト インスタンス アカウントおよび BizTalk 分離ホスト インスタンス アカウントは同じである必要があります。 それ以外の場合、BTARN が正常に機能しません。  
* BTARN では、BizTalk Server 管理者グループまたは BizTalk Application Users グループに個々 のサービス アカウントとグループではなく、のみを追加できます。  
* IIS 分離モードを構成して、BTSHTTPReceive.dll 用の WebService 拡張を作成する必要があります。 詳細については、"404 Not found エラー HTTP 要求を送信するときに"エントリにある「のトラブルシューティング: 問題と解決策」のトピックを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=188560](http://go.microsoft.com/fwlink/?LinkId=188560)します。 またを参照してください[IIS の HTTP 受信場所を構成する方法](../../core/how-to-configure-iis-for-an-http-receive-location.md)します。  
* サーバーを追加する (http:// <*サーバー名*>) をローカル インターネット ゾーンに Internet Explorer のセキュリティ オプション。  
*  既定以外のポートを使用するリモート SQL インスタンスを使用して BTARN を構成する場合は、Microsoft SQL Server クライアント ツールをローカル コンピューターにインストールする必要があります。 詳細については、次を参照してください。[複数コンピューター環境向けの BizTalk Server インストール ガイド](../../install-and-config-guides/install-biztalk-server-in-a-multi-computer-environment.md)します。
*  BizTalk Server の構成中に BizTalk 管理者、BizTalk ホスト ユーザー、および BizTalk 分離ホスト ユーザー ロールの別のグループを使用する必要があります。  
*  BTARN は、BTARN データベースを構成する SQL インスタンス用に作成されたエイリアスの使用をサポートしていません。  

### <a name="install-btarn"></a>BTARN をインストールします。

1.  BTARN の実行**setup.exe**管理者として。

2.  **[インストール]** を選択します。  

3.  **顧客情報** ページで、ユーザー名と組織、プロダクト キーを入力してをクリックし、**次**します。  

4.  **使用許諾契約書**ページ、使用許諾契約書を読んで、 をクリックし、 **Accept**します。  

    > [!NOTE]
    >  インストールを続行するには、使用許諾契約書に同意する必要があります。  

5.  **インストール オプション**] ページで、[**完了**フル インストールする場合または**カスタム**部分インストールします。 インストール パスが正しいことを確認し、をクリックし、**次**します。  

    > [!NOTE]
    >  選択した場合**カスタム**からをインストールするコンポーネントを選択して、**カスタム インストール**ページ。 SDK またはドキュメント コンポーネントのみをインストールすることを選択した場合、セットアップ プログラムを実行する前にインストールされている .NET Framework が必要です。  

6.  **概要**をインストールし、をクリックし、コンポーネントを確認 ページで、**インストール**します。 **インストールの進行状況**画面には、インストール手順の進行状況が表示されます。  

7.  **のインストールを完了** ページで、ことを確認、**構成ウィザードの実行**ボックスが選択されているをクリックして**完了**。  

     BTARN 構成ウィザードが開きます。 次に、BTARN を構成します。  

    > [!IMPORTANT]
    >  セットアップが完了すると、表示する BTARN の構成が失敗する可能性があります、BTARN HTTP フロント エンド機能のみをインストールするカスタム インストールを実行する場合、"機能のオブジェクトを作成できませんでした: WebApp"エラー。 このような場合は、2 つのファイルをコピー (**Microsoft.VC80.ATL.manifest**と**atl80.dll**) BizTalk Server を使用しているコンピューターからにインストールされている、BTARN HTTP フロント エンド機能をインストールしたコンピューターにします。  
    >   
    >  2 つのファイルのソース フォルダーは、Visual Studio は、BizTalk Server と同じコンピューターにインストールされて場合、 *< ドライブ\>*: \Program Files\Microsoft Visual Studio 11.0\VC\redist\x86\Microsoft.VC100.ATL します。 BizTalk server の 2 つのファイルのソース フォルダーの下のフォルダーは、BizTalk server に Visual Studio がインストールされていない場合 *< ドライブ\>*: \WINDOWS\WinSxS します。 ファイルのバージョンは、8.0.50727.42 です。 HTTP フロント エンド機能をインストールしたコンピューター上の宛先フォルダーは、BTARN のインストール ディレクトリ (既定では、 *< ドライブ\>*: \Program Files\Microsoft BTARN)。  
    >   
    >  HTTP フロント エンド機能がインストールされたコンピューターをこれらのファイルをコピーしたら後で再実行**Configuration.exe**します。  

### <a name="configure-btarn"></a>BTARN を構成します。  

> [!TIP]
 >  BTARN を構成する前に、IIS でのハンドラー マッピングの .NET Framework のマッピングを確認します。 また、BTARN を構成する場合は、手動で IIS_WPG グループを作成する必要があります。  

1.  **Microsoft BTARN 構成ウィザード**] ページで、[**基本的な構成**、サーバーの既定の設定を構成するか、**カスタム構成**に高度な構成オプションを使用してサーバーを構成します。  

    > [!NOTE]
    >  ローカル管理者アカウントを使用して BTARN を構成する場合は、入力としてアカウント *< マシン名\>\\< 管理者名\>* で、**ユーザー ID**フィールド、**サービス資格情報**領域。  

2.  **データベース サーバー名**テキスト ボックスを表示、サーバー名が正しいことを確認します。 **サービス資格情報**領域で、サービスを実行するアカウント (ドメイン) を持つユーザー名とパスワードを入力します。 クリックして**構成**します。  

3.  自分のアカウントに管理者特権がある場合は、クリックして**はい**構成を続行します。  

4.  選択した場合**基本的な構成**ステップ 1 で、検証で構成するコンポーネントの一覧表示、**概要**クリックしてダイアログ ボックスで、 **[次へ]**。 手順 10 に進みます。  

5.  選択した場合**カスタム構成**ステップ 1 で、次の手順を実行します。  

    > [!NOTE]
    >  BTARN のデータベース名に特殊文字が使用されていると、BTARN の構成に失敗します。  

6.  ランタイムを構成する、 **Microsoft BTRAN 構成**ダイアログ ボックスで、をクリックして**ランタイム**左側のウィンドウでします。 右にある**ランタイム**ウィンドウで、をクリックして**このコンピューターでランタイム機能を有効にする**します。 既存のデータベース グループに参加するには、オフ**新しいデータベース グループを作成したい**します。 適切な Web サーバー名、ポート番号、データ ストア、アプリケーション プール サービス アカウント、および BizTalk HTTP 受信仮想フォルダーを選択します。  

7.  Web Apps 機能を構成する、 **Microsoft BTRAN 構成**ダイアログ ボックスで、をクリックして**WebApps**で左側のウィンドウをクリック**このコンピューターでランタイム機能を有効にします。**. 適切な BizTalk Server の名前を入力し、ポート番号、または、既定値を選択します。 適切な Web アプリケーション仮想フォルダーを選択します。  

8.  **[構成の適用]** をクリックします。  

9. **概要**] ページで [**次**します。  

10. **構成完了**] ページで [**完了**。  

    > [!NOTE]
    >  BTARN のインストール後に、BAS ビジネス ユーザー、ビジネス マネージャー、およびビジネス管理者の各グループにシステム管理者がユーザーを追加する必要があります。 システム管理者が自分自身をこれらのグループに追加する場合は、ユーザーをグループに追加してから一度ログオフし、再度ログオンする必要があります。

    > [!WARNING]
    >  次の 3 つの異なるグループは、BizTalk 管理者、BizTalk ホスト ユーザー、および BizTalk Isolated Host Users の BizTalk Server を構成するときに使用する必要があります。  

## <a name="start-the-artifacts"></a>成果物を開始します。
BTARN のオーケストレーション、送信ポート、および受信場所の BTARN を構成した後自動的に開始されていません。

> [!NOTE]
>  PrivateInitiatorProcess と PrivateResponderProcess の各オーケストレーションを開始する前に、PrivateInitiator_To_LOB と PrivateResponder_To_LOB の各送信ポートを開始する必要があります。  

-   インターネット インフォメーション サービス (IIS) 仮想サーバーを SSL (Secure Sockets Layer) を使用して構成したコンピューターでは、クライアント証明書を受け入れるように仮想サーバーを構成する必要があります。 参照してください[手順 4: IIS でレイヤーをセキュリティで保護を有効にするソケット](step-4-enabling-secure-sockets-layer-in-iis.md)で、[ダブル アクション チュートリアル](double-action-tutorial.md)します。


1.  開いている**BizTalk Server 管理**に管理者として。  

2.  展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalk アプリケーション 1**します。  

3.  クリックして**送信ポート**します。 右側のウィンドウでが開始されていない各送信ポートを右クリックし をクリックし、**開始**します。  

4.  クリックして**受信ポート**と**受信場所**します。 右側のウィンドウで各受信場所に対して、開始されていない、右クリックし、をクリックし、**開始**します。  

    > [!NOTE]
    >  PrivateInitiatorProcess と PrivateResponderProcess のオーケストレーションを開始する前に、PrivateInitiator_To_LOB と PrivateResponder_To_LOB の送信ポートを開始する必要があります。  

5.  クリックして**オーケストレーション**と**受信場所**します。 右側のウィンドウでが開始されていない各オーケストレーションを右クリックし をクリックし、**開始**します。  

## <a name="restart-your-computer"></a>コンピューターを再起動します。  

コンピューターを再起動して、構成およびアクセス許可に対する変更を適用します。  

> [!NOTE]
>  開発者は、開発、ステージング、またはテストのために、単一のサーバーに BTARN をインストールして構成することができます。 その場合、このサーバーを使用して独自のコードを作成し、テストしたうえで、運用環境に移行します。  

 1 台のサーバーに BTARN をインストールする方法の詳細については、次を参照してください。、 [Loopback チュートリアル](loopback-tutorial.md)します。

## <a name="next-steps"></a>次のステップ  

* [RosettaNet アクセラレータのアップグレード](upgrade-biztalk-accelerator-for-rosettanet.md)
* [RosettaNet アクセラレータのアンインストール](uninstall-biztalk-accelerator-for-rosettanet.md)
* [インストールのトラブルシューティングとインストールの既知の問題](troubleshoot-known-issues-installation.md)