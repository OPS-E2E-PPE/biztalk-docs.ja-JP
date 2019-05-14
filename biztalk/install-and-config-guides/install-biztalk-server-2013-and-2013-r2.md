---
title: BizTalk Server 2013 および 2013 R2 のインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3b4665ea-6f2c-477f-98ec-1cebef05ad4a
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3ce184bf0562ae9dd18291b37a75fc5360d9b5c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266178"
---
# <a name="install-biztalk-server-2013-and-2013-r2"></a>BizTalk Server 2013 および 2013 R2 のインストール
インストールする手順について説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  

## <a name="before-you-get-started"></a>始める前に

- **アカウント名**– 可能な限り、既定のアカウント名を使用します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セットアップでは、既定のアカウントが自動的に入力します。 複数ある場合は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ドメイン内のグループは、競合を回避するためにアカウント名を変更します。 場合は、名前を変更する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のみをサポートして\< *NetBIOS ドメイン名*\>\\<*ユーザー* \>サービスアカウントおよび Windows グループ。  

- **アカウント名と BAM 管理 Web サービス**–[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]はサポートしていませんビルトイン アカウントまたはパスワードなしのアカウントを BAM 管理 Web サービス ユーザーです。 Web サービスへのアクセス、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースとこれらのアカウントがセキュリティの脅威を提案します。  

  > [!NOTE]
  >  構成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]これらの種類のアカウントでは成功しても、BAM 管理 Web サービスが失敗します。 BAM アプリケーション プールのビルトイン アカウントまたはパスワードなしのアカウントを使用できます。  

- **BizTalk アセンブリ ビューアー** – 64 ビット プラットフォームでサポートされていません。  

- **インストールし、アンインストール**アンインストール –[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]手動で削除する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 インストールする場合は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]開発者またはエバリュエーターは、仮想マシンを使用します。 再インストールする必要がある場合に簡単にロールバックできます仮想マシンをアンインストールし、データベースを削除する必要はありません。  

- **32 ビットおよび 64 ビット コンピューター** – インストールするときにいくつかの違いがある[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 ビットまたは 64 ビット コンピューターです。 インストールと構成は、32 ビットおよび 64 ビット コンピューターをについて説明します。 相違点が記載されています。  

- **ワークグループ**- インストールと構成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ワークグループで 1 台のコンピューター上の環境がサポートされています。 SQL Server と[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]機能とコンポーネントがインストールされ、同じコンピューター上で構成します。  

- **ターミナル サーバー** – インストール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション モードで実行されているターミナル サーバーの使用はサポートされていません。 参照してください[KB 832027](http://support.microsoft.com/kb/832027)します。  

- **BAM ポータル**- .NET Framework 2.0 を実行しているし、BAM ポータルの新しい web サイトを作成するアプリケーションで使用される web サイトに BAM ポータルが構成されている場合。  

   [IIS 7 web サイトを作成します。](http://technet.microsoft.com/library/cc772350\(WS.10\).aspx)  

   [IIS 8 web サイトを作成します。](http://technet.microsoft.com/library/hh831515.aspx)  

   後に、新しい web サイトを作成するには。  

  1. 開いている**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成**します。  

  2. BAM ポータルを構成してから新しい web サイトを選択、 **BAM ポータル Web サイト**一覧。  

- **コミュニティによる補足**:読み取り:  

   [BizTalk Server のプロアクティブ性](http://msdn.microsoft.com/library/dn393929\(v=bts.10\).aspx)  

   [BizTalk Server 2013 R2:前に重要な考慮事項を設定する (パート 1) サーバーのインストールと構成。](http://sandroaspbiztalkblog.wordpress.com/2015/01/04/biztalk-server-2013-r2-installation-and-configuration-important-considerations-before-set-up-the-server-part-1/)  

##  <a name="BKMK_Install"></a> BizTalk Server をインストールします。  

1. 開いているプログラムを閉じます。 実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者としてインストーラー。  

2. **開始**、 **Microsoft BizTalk Server のインストール**します。  

3. **顧客情報**、ユーザー名、組織、プロダクト キーを入力し、**次**します。  

4. **使用許諾契約書**ライセンス条項に同意し、選択**次**します。  

5. **カスタマー エクスペリエンス向上プログラム**、参加希望を選択し、**次**します。  

    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] カスタマー エクスペリエンス向上プログラムに参加します。 機能の使用状況レポートの機能に関する有益なフィードバックをマイクロソフトに提供する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 収集されたデータは匿名でありを識別するためには使用できません。 Microsoft は、このプログラムの一部としての機能使用状況の統計を収集します。 このプログラムに参加している、信頼性およびパフォーマンスのさまざまな機能の向上を支援できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 このプログラムとプライバシー ポリシーの詳細については、次を参照してください。 [Microsoft BizTalk Server CEIP プライバシー ポリシー](http://go.microsoft.com/fwlink/p/?LinkId=188553)します。  

6. **コンポーネントのインストール**で、使用可能なコンポーネントを確認し、インストールするものを選択します。  


   |                             機能                             |                                                                                                                                                                                                                                                                                                                                                                                                               説明                                                                                                                                                                                                                                                                                                                                                                                                                |
   |-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                        **ドキュメント**                        |                                                                                                                                                                                                                                                                                                                                                 主要なマニュアル、チュートリアル、UI リファレンス (F1 ヘルプ)、プログラマーズ リファレンス、および SDK サンプルとユーティリティの使用に関する説明。                                                                                                                                                                                                                                                                                                                                                 |
   |                       **Server ランタイム**                        |                                                                                                                                                                                                                                                                                                                                                          サービスの不可欠なランタイム[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。                                                                                                                                                                                                                                                                                                                                                          |
   |                   **BizTalk edi/as2 ランタイム**                   |                                                                                                                                                                                                                                                                                      ネイティブに提供するランタイム サービスは、電子データ交換 (edi) および Applicability Statement 2 (AS2) データ トランスポート メッセージング機能のサポートします。 **注:** 選択した場合にのみ選択することができます、**サーバー ランタイム**機能します。                                                                                                                                                                                                                                                                                       |
   |   **Windows Communication Foundation (WCF) アダプター ランタイム**    |                                                                                                                                                                                                                                                                                                   アダプターを有効にする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]WCF ベースのアプリケーションと通信します。 **注:** 選択した場合にのみ選択することができます、**サーバー ランタイム**機能します。                                                                                                                                                                                                                                                                                                   |
   |                      **ポータル コンポーネント**                      |                                                                                                                                                                                                                                                                                                                                               ポータル コンポーネントは、通信、共同作業、およびビジネス データを使用して意思決定にビジネス アナリストによって使用される機能のセットです。                                                                                                                                                                                                                                                                                                                                                |
   |                **ビジネス アクティビティの監視**                 |                                                                                                                                                                                                                                                                         呼ばれます BAM では、これらは、重要なビジネスの意思決定を実行することにより、異種ビジネス プロセスのリアルタイム ビューをビジネス ユーザーに提供する一連の機能です。 **注:** 選択した場合にのみ選択することができます、**ポータル コンポーネント**機能します。                                                                                                                                                                                                                                                                          |
   |             **管理ツールと監視**             |                                                                                                                                                                                                                                                                                                                            管理し、監視に必要なコンポーネント[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ローカル コンピューターとリモート サーバーの両方でします。                                                                                                                                                                                                                                                                                                                             |
   | **Windows Communication Foundation (WCF) 管理ツール** |                                                                                                                                                                                                                                                                                                                         この機能を選択すると、WCF コンポーネント用の管理サービスがインストールされます。 **注:** 選択した場合にのみ選択することができます、**管理ツールと監視**機能します。                                                                                                                                                                                                                                                                                                                         |
   |                   **開発ツールおよび SDK**                   |                                                                                                                                   サンプルとユーティリティを迅速に作成できるようにする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション。 これには、SDK サンプルおよびサポート ドキュメント、スキーマおよびマップ デザイナー、および Visual Studio プロジェクト テンプレートが含まれます。 **重要:** 任意の開発作業を実行する予定の場合は、このコンポーネントをインストールする必要があります。 使用する Visual Studio 拡張機能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は機能しません、**開発ツールおよび SDK**コンポーネントをインストールします。                                                                                                                                    |
   |                    ***追加のソフトウェア***                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
   |    **エンタープライズ シングル サインオン (SSO) 管理モジュール**    |                                                                                                                                                                                                                                                                                                                                                                                SSO 関連アプリケーションとそのマッピングを管理するためのインターフェイス。                                                                                                                                                                                                                                                                                                                                                                                 |
   |       **エンタープライズ シングル サインオン マスター シークレット サーバー**        |                                                                                                                                                                                                                                                                                   SSO サーバーをマスター シークレットを格納します。 システムの場合は、他のすべての SSO サーバーは、このサーバーからマスター シークレットを取得します。 マスター シークレット サーバーが必要で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。                                                                                                                                                                                                                                                                                    |
   |                  **ビジネス ルール コンポーネント**                  |                                                                                                                                                                                                                                                                                                                                                                                 ビジネス ルール エンジンで使用されるポリシーの作成に使用されます。                                                                                                                                                                                                                                                                                                                                                                                 |
   |                       **MQSeries エージェント**                        |                                                                                                                                                                                                                                                                                                                                                                     BizTalk Adapter for MQSeries と MQSeries Server for Windows の間の通信を提供します。                                                                                                                                                                                                                                                                                                                                                                     |
   |       **Windows SharePoint Services アダプター Web サービス**       | **非推奨**。 Web にインストールされているサービスを IIS を使用して、 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 、コンピューター、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]アダプターは、Microsoft SharePoint を介して送受信のドキュメントを処理します。<br /><br /> **推奨事項**:**いない**をインストールします。 既定では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]に自動的にインストールされているに再配布可能な SharePoint クライアント側オブジェクト モデル (CSOM) を使用して、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]」の説明に従って;[付録 b:Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)します。 |
   |                     **BAM 警告プロバイダー**                      |                                                                                                                                                                                                                                                                        BAM 警告を構成します。<br /><br /> BAM 警告を使用すると[!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)]または[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]SP1 では、データベース メール機能を構成する必要があります。 SQL Server Notification Services を使用することはできません。                                                                                                                                                                                                                                                                        |
   |                         **BAM クライアント**                          |                                                                                                                                                                                                                                                                                                                                                                                      ビジネス ユーザーが BAM を使用するためのクライアント側ソフトウェア。                                                                                                                                                                                                                                                                                                                                                                                      |
   |                        **BAM イベント**                         |                                                                                                                                                                                                                                                                                                                           Windows Workflow Foundation および Windows Communication Foundation のインターセプター。 また、カスタム アプリケーションから BAM データベースにイベントを送信する BAM イベント API も含まれています。                                                                                                                                                                                                                                                                                                                           |
   |                   **プロジェクト ビルド コンポーネント**                   |                                                                                                                                                                                                                                                                                                                                        ツールを構築することができます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューションせず、Visual Studio を使用します。                                                                                                                                                                                                                                                                                                                                        |


7. 既定のインストール場所を受け入れるか選択**参照**をインストールする別の場所を入力する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 **[次へ]** を選択します。  

8. お使いのコンピューターで、ADOMD.NET などの必須コンポーネントが不足している場合、セットアップは、再頒布可能パッケージの前提条件をインストールできます。 次のいずれかを実行できます。  

   -   選択**web から自動的に再頒布可能パッケージの前提条件をインストール**  

        スイッチまたは  

   -   選択**CAB ファイルから再頒布可能パッケージのコンポーネントを自動的にインストール**CAB ファイルをダウンロードしている場合。 これを選択する場合、CAB ファイルの場所を参照できます。  

9. **概要**コンポーネントが正しいことを確認します。 自動ログオンをできるように、システムの再起動後、次のように選択します。**設定**、ログオン情報を入力します。 自動ログオンは、セットアップ中に、再起動に対してのみ有効になっているし、セットアップが完了したら無効になっています。  

10. 選択**インストール**インストール プロセスを開始します。  

11. **Microsoft Update のセットアップ**好みを選択し、選択**次**します。  

12. **のインストールを完了**、オフに**起動[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成**、し、**完了**。  

## <a name="additional"></a>その他  

- SQL Server をインストールした SQL Server セットアップはシステム管理者の権限をログオン アカウントに付与されます。 この権限をインストールするために必要なも[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次のいずれかを実行する必要があります。  

  -   SQL Server をインストールしたときに使用した同じアカウントを使用します。  

  -   ログオン アカウントにシステム管理者権限を付与します。  

- 自己解凍 EXE をダウンロードしたら[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、インストール ガイドが表示されます。 Setup.exe[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール ガイドと同じ場所にします。  

- インストールではなく[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]o は、物理コンピューター上構成、[!INCLUDE[winazure](../includes/winazure-md.md)]で仮想マシンを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]イメージ。 参照してください[Azure VM での BizTalk Server を構成する](http://msdn.microsoft.com/library/azure/jj248689.aspx)します。  

- インストールする手順については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コマンド プロンプトを使用して、参照してください[付録 a:サイレント インストール](../install-and-config-guides/appendix-a-silent-installation.md)します。  


## <a name="see-also"></a>参照  

 [付録 a:サイレント インストール](../install-and-config-guides/appendix-a-silent-installation.md)   
 [付録 b:Microsoft SharePoint アダプターをインストールします。](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)   
 [付録 c:再頒布可能 CAB ファイル](../install-and-config-guides/appendix-c-redistributable-cab-files.md)   
 [付録 d:SMTP サーバーを作成します。](../install-and-config-guides/appendix-d-create-the-smtp-server.md)