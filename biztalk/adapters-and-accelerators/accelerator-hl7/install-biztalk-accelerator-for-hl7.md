---
title: "HL7 の BizTalk アクセラレータをインストール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52347742-f858-47bb-bc73-1a6095ea9e8e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ad01c0b3966985efdceea421de85778266a294c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="install-biztalk-accelerator-for-hl7"></a>HL7 の BizTalk アクセラレータをインストールします。

## <a name="hardware-and-software-requirements"></a>ハードウェアとソフトウェアの要件

ハードウェアとソフトウェアの最小要件は、同じ[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]です。 

|  |BizTalk の要件  |SQL と OS の要件 |  
|---------|---------|--------- | 
| [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)] | [BizTalk Server 2016 のハードウェア/ソフトウェア要件](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md) | **SQL Server のハードウェアおよびソフトウェア要件**: <br/>[SQL Server 2016](https://msdn.microsoft.com/library/ms143506(v=sql.130).aspx)<br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/><br/>**Windows サーバーのハードウェア要件**: <br/>[Windows Server 2016](https://technet.microsoft.com/windows-server-docs/get-started/server-basics)<br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx) |
| [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] <br/><br/> [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] 2013 | [BizTalk Server 2013 および 2013 R2 のハードウェアおよびソフトウェア](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md) |**SQL Server のハードウェアおよびソフトウェア要件**: <br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/>[SQL Server 2012](https://msdn.microsoft.com/library/ms143506(v=sql.110).aspx)<br/>[SQL Server 2008 R2](https://msdn.microsoft.com/library/ms143506(v=sql.105).aspx)<br/><br/>**Windows サーバーのハードウェア要件**: <br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx)<br/>[Windows Server 2008 R2](https://technet.microsoft.com/library/dd379511(v=ws.10).aspx)  |

> [!TIP]
> ここにリストされているのは最小のハードウェア要件です。 環境はそれぞれ異なり、ご使用の環境ではこれらを超える要件が必要となる可能性は十分あります。 参照してください[インストール、サイズ変更、配置、および BizTalk Server ソリューションを維持するための推奨事項](http://social.technet.microsoft.com/wiki/contents/articles/666.recommendations-for-installing-sizing-deploying-and-maintaining-a-biztalk-server-solution.aspx)

## <a name="install-hl7"></a>HL7 をインストールします。

### <a name="before-you-begin"></a>アンインストールの準備

* HL7 アクセラレータのインストール ファイルは`BizTalk Server <version>\BizTalk Accelerators`上、 [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] ISO、ダウンロード先、ネットワーク共有、またはダウンロードする任意の場所、[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]プログラムです。
* インストールと構成のユーザー [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] BizTalk 管理者グループのメンバーであり、SQL Server の Administrators グループのメンバーにする必要があります場所、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]データを格納します。
* サインイン ユーザーとコンピューターには、プライマリ ドメイン コント ローラー (PDC) へのアクセスがある場合があります。 場合は、セットアップは、PDC し、インストールが失敗し、アクセスが失敗し、続行されません。  
* BizTalk Server が、アダプター、エンタープライズ シングル サインオン (SSO)、グループ、およびランタイム外の標準に 32 ビット BizTalkServerApplication ホストを含む基本的なコンポーネント インストールおよび構成が必要です。
* 読み取り、[インストールの既知の問題](../../adapters-and-accelerators/accelerator-hl7/installation-known-issues.md)です。
*  [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]Enterprise および Standard エディションでは、使用可能です。 次の表のさまざまなエディション間の互換性[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。  
  
    |[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] エディション|互換性のあるエディション[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]|  
    |---|---|  
    |Enterprise Edition|Enterprise Edition|  
    |Standard Edition|Enterprise または Standard Edition|  
    |Developer Edition|Enterprise Edition|  

### <a name="default-installation"></a>既定のインストール

1. 実行、 [!INCLUDE[btaBTAHL7NoNumber_md](../../includes/btabtahl7nonumber-md.md)] (A4HL7) **setup.exe**管理者として。 
  
    > [!TIP]
    >  以降で[!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)]以降のバージョン、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]インストールには、32 ビット インストール パッケージと 64 ビット インストール パッケージが含まれています。
    > 
    > 32 ビット コンピューターでは、32 ビット パッケージのみをインストールします。 64 ビット コンピューターで 32 ビットのインストール**または**64 ビット パッケージです。 64 ビット パッケージでは、アダプターとパイプラインの実行を 32 ビット モードと 64 ビット モードの両方で有効にできます。  
  
2.  [ようこそ] ページで、**次**です。  
  
3.  受け入れる、**使用許諾契約書**、し、**次**です。  
  
4.  ユーザー名と、組織を入力し、**次**です。  
  
5.  選択、**標準**を設定し、**次**です。  
  
6.  **サービス アカウントのログ記録**ページがログ記録のアクセス許可に自動的に次のグループに与えられます。 

  * BizTalk Server 管理者
  * BizTalk Application Users
  * [BizTalk Server B2B Operators]
  * BizTalk Server オペレータ

    **[次へ]** を選択します。 

7. 概要を確認し、選択**次**です。  

8. **コピー先フォルダー** **次へ**既定フォルダーを使用します。 または、選択**変更**別のインストール フォルダーを選択します。 

9. **データベース情報のログ記録**、次を入力し、**次**です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**データベース サーバー名**|既定値は、サーバー名です。 <br/><br/>**注**サーバー名の既定値は、BizTalkMgmtDb データベースが存在するコンピューターの名前。 この値を変更することはできません。|  
    |**HL7 データベース名**|データを含むデータベースの名前を入力、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]ソリューションか、既定の設定をそのまま使用**BTAHL7**です。 <br/><br/>**注**データベース要件ごとに設定する ANSI、ASCII 文字を使用する必要があります[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]他の文字セットをサポートしていません。|  
    | **接続のテスト** | 選択すると、SQL Server の接続があることを確認します。 |
  
    > [!NOTE]
    >  既に選択されているデータベースが存在する場合は、メッセージ ボックスが表示されます。 [**OK**] をクリックし、続行します。  
    
10. **[インストール]**を選択します。
  
11. 選択**完了**完了したときにします。  
  
    > [!TIP] 
    > 選択**Launch Tutorial**をエンド ツー エンド チュートリアルをインストールします。 
    
### <a name="custom-installation"></a>カスタム インストール
1. 実行、 [!INCLUDE[btaBTAHL7NoNumber_md](../../includes/btabtahl7nonumber-md.md)] (A4HL7) **setup.exe**管理者として。 
  
    > [!TIP]
    >  以降で[!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)]以降のバージョン、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]インストールには、32 ビット インストール パッケージと 64 ビット インストール パッケージが含まれています。 
    > 
    > 32 ビット コンピューターでは、32 ビット パッケージのみをインストールします。 64 ビット コンピューターで 32 ビットのインストール**または**64 ビット パッケージです。 64 ビット パッケージでは、アダプターとパイプラインの実行を 32 ビット モードと 64 ビット モードの両方で有効にできます。  
  
2.  [ようこそ] ページで、**次**です。  
  
3.  受け入れる、**使用許諾契約書**、し、**次**です。  
  
4.  ユーザー名とパスワードを入力し、**次**です。  
  
5. 選択**カスタム**、し、**次**です。  
  
6.  インストールして、選択する機能の選択**次**です。  
  
    |機能|サブ機能|Description|標準インストール|カスタム インストール|  
    |---|---|---|---|---|  
    |**エンジン**||検証し、処理、メッセージをルーティングします。<br /><br /> この機能をインストールするには、BizTalk Server 管理者グループのメンバーである必要がある必要があります。|✓|✓|  
    |**エンジン**|エンジン コンポーネント|プロセス[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]フラット ファイルおよび XML でエンコードされたメッセージ。|✓|✓|  
    |**エンジン**|送信バッチ処理|作成し、ルーティング[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]形式のドキュメントをバッチ処理します。|✓|✓|  
    |**エンジン**|パイプライン|構築するためのパイプラインのサンプル、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]ソリューションです。|✓|✓|  
    |**アダプター**||エンドポイントの接続を有効にするユーティリティです。|✓|✓|  
    |**アダプター**|MLLP|MLLP アダプターを使用した IP ベースの接続を有効にする[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]MLLP のプロトコルです。|✓|✓|  
    |**アダプター**|MLLP テスト ツール|TCP ベースの接続上でクライアント アプリケーションを送受信する MLLP ベースをエミュレートするツールをテストします。|||  
    |**スキーマ**||HL7 V2 の選択。XSD スキーマをフラット ファイルを X に基づいています。|✓|✓|  
    |**成果物**||使用するためのツール[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]成果物です。||✓|  
    |**成果物**|オーケストレーション|構築に使用できるサンプル オーケストレーション、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]ソリューションです。||✓|  
    |**その他のコンポーネント**|テストのインスタンス|サンプル/テスト データの開始点として使用することができます、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]ソリューションです。|||  
    |**その他のコンポーネント**|-|他のコンポーネント[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]です。|✓|✓|  
    |**その他のコンポーネント**|エクスプ ローラーの構成|データ ストアのログ記録の定義に使用するアプリケーションでは、パーティ固有の検証、マッピングのヘッダー、バッチ処理、および受信確認の要件を構成します。|✓|✓|  
    |**その他のコンポーネント**|SDK|コンポーネントとの成果物と必要なエンド ツー エンド チュートリアル、MLLP ユーティリティなど、HL7 2. XML スキーマのためのユーティリティが含まれています。|✓|✓|  
    |**その他のコンポーネント**|ログ フレームワーク|ログ記録をサポートするコンポーネント[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]イベント。|✓|✓|  
    |**その他のコンポーネント**|スタート プロジェクト|プラグインを[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を有効にする[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]プロジェクトの開発。|✓|✓|  
  
7. **サービス アカウントのログ記録**、次を入力し、**次**です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**アカウント名**|ログ サービスの開始に使用するアカウント名を入力します。|  
    |**Password**|このアカウントのパスワードを入力します。|  
    |**[ドメイン]**|このアカウントのドメイン名を入力します。|  
  
8. 入力を求められたら**アカウント名が与えられてログオン右サービスとして** **OK**です。  
  
9. 概要を確認し、選択**次**です。  
  
10. **コピー先フォルダー** **次へ**既定フォルダーを使用します。 または、選択**変更**別のインストール フォルダーを選択します。
  
11. **データベース情報のログ記録** ページで、次を入力して選択し、、**次**です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**データベース サーバー名**|既定値は、サーバー名です。 <br/><br/>**注**サーバー名の既定値は、BizTalkMgmtDb データベースが存在するコンピューターの名前。 この値を変更することはできません。|  
    |**HL7 データベース名**|データを含むデータベースの名前を入力、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]ソリューションか、既定の設定です。 これはそのまま使用**BTAHL7**です。 <br/><br/> **注**データベース要件ごとに設定する ANSI、ASCII 文字を使用する必要があります[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]他の文字セットをサポートしていません。|  
  
12. **[インストール]**を選択します。  
  
15. 選択**完了**完了したときにします。  
  
    > [!TIP] 
    > 選択**Launch Tutorial**をエンド ツー エンド チュートリアルをインストールします。   
    
## <a name="next-steps"></a>次の手順
いくつかのチュートリアルをステップ[始める BizTalk Accelerator 用 HL7](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md)です。