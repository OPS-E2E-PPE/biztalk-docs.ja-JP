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
ms.openlocfilehash: 849106d0a64df6520e25ccf35b50c78a60ea9749
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970595"
---
# <a name="install-biztalk-server-2013-and-2013-r2"></a>BizTalk Server 2013 および 2013 R2 のインストール
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストール手順を示します。  

## <a name="before-you-get-started"></a>始める前に

- **アカウント名** – 可能な場合は常に既定のアカウント名を使用してください。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のセットアップでは自動的に既定のアカウントが入力されます。 ドメイン内に複数の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] グループがある場合は、競合を防ぐためアカウント名を変更してください。 場合は、名前を変更する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のみをサポートして\< *NetBIOS ドメイン名*\>\\<*ユーザー* \>サービスアカウントおよび Windows グループ。  

- **アカウント名と BAM 管理 Web サービス** – [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、BAM 管理 Web サービス ユーザーに対して、ビルトイン アカウントまたはパスワードなしのアカウントはサポートされていません。 Web サービスが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースにアクセスするときに、これらのアカウントでセキュリティの脅威が生じる場合があります。  

  > [!NOTE]
  >  これらの種類のアカウントでの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成は成功する場合がありますが、BAM 管理 Web サービスは失敗します。 ビルトイン アカウントまたはパスワードなしのアカウントは、BAM アプリケーション プールに使用できます。  

- **BizTalk アセンブリ ビューアー** – 64 ビットのプラットフォームではサポートされません。  

- **インストールとアンインストール** – [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をアンインストールするには、手動で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースを削除する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を開発者または評価担当者としてインストールする場合は、仮想マシンを使用します。 再インストールが必要になった場合は、アンインストールやデータベースを削除することなく、仮想マシンを簡単にロールバックできます。  

- **32 ビットおよび 64 ビットのコンピューター** – 32 ビットまたは 64ビットのコンピューターへの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストールに大きな違いはありません。 インストールと構成は 32 ビットおよび 64 ビットのコンピューターに対応しています。 特に違いはありません。  

- **ワークグループ** - ワークグループ環境では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を 1 台のコンピューターだけにインストールして構成できます。 SQL Server および [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の機能とコンポーネントを同じコンピューターにインストールして構成できます。  

- **ターミナル サーバー** – アプリケーション モードのターミナル サーバーを使用した [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストールはサポートされていません。 詳細については、「[KB 832027](http://support.microsoft.com/kb/832027)」を参照してください。  

- **BAM ポータル** - .NET Framework 2.0 を実行するアプリで使用される Web サイトに BAM ポータルが構成されている場合は、BAM ポータルの新しい Web サイトを作成します。  

   [IIS 7 Web サイトの作成](http://technet.microsoft.com/library/cc772350\(WS.10\).aspx)  

   [IIS 8 Web サイトの作成](http://technet.microsoft.com/library/hh831515.aspx)  

   新しい Web サイトを作成したら:  

  1. [**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成**] を開きます。  

  2. BAM ポータルを構成し、**[BAM ポータル Web サイト]** の一覧から新しい Web サイトを選択します。  

- **コミュニティによる補足**: 閲覧:  

   [BizTalk Server のプロアクティブ性](http://msdn.microsoft.com/library/dn393929\(v=bts.10\).aspx)  

   [BizTalk Server 2013 R2: Installation and Configuration – Important considerations before set up the server (Part 1) (BizTalk Server 2013 R2: インストールと構成 – サーバー セットアップ前の重要な検討事項 (パート 1))](http://sandroaspbiztalkblog.wordpress.com/2015/01/04/biztalk-server-2013-r2-installation-and-configuration-important-considerations-before-set-up-the-server-part-1/)  

##  <a name="BKMK_Install"></a> BizTalk Server のインストール  

1. 開いているプログラムをすべて閉じます。 管理者として [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インストーラーを実行します。  

2. **[スタート]** で **[Microsoft BizTalk Server のインストール]** を選択します。  

3. **[ユーザー情報]** で、ユーザー名、組織、プロダクト キーを入力して **[次へ]** を選択します。  

4. **[ライセンス契約]** に同意し、**[次へ]** をクリックします。  

5. **[カスタマー エクスペリエンス向上プログラム]** で、参加希望かどうかを選択し、**[次へ]** を選択します。  

    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はカスタマー エクスペリエンス向上プログラムに参加しています。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の機能の使用状況レポートに関する有益なフィードバックを Microsoft に提供することを選択できます。 収集されるデータは匿名であり、個人を特定できるものではありません。 このプログラムでは、機能の使用状況の統計情報が収集されます。 お客様にこのプログラムに参加していただくことによって、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のさまざまな機能の信頼性とパフォーマンスが向上します。 このプログラムの詳細およびプライバシー ポリシーについては、「[Microsoft BizTalk Server CEIP プライバシー ポリシー](http://go.microsoft.com/fwlink/p/?LinkId=188553)」を参照してください。  

6. **[インストールするコンポーネント]** で、インストール可能なコンポーネントの一覧から必要なコンポーネントを選択します。  


   |                             機能                             |                                                                                                                                                                                                                                                                                                                                                                                                               説明                                                                                                                                                                                                                                                                                                                                                                                                                |
   |-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                        **ドキュメント**                        |                                                                                                                                                                                                                                                                                                                                                 主要なマニュアル、チュートリアル、UI リファレンス (F1 ヘルプ)、プログラマーズ リファレンス、および SDK サンプルとユーティリティの使用に関する説明。                                                                                                                                                                                                                                                                                                                                                 |
   |                       **Server ランタイム**                        |                                                                                                                                                                                                                                                                                                                                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に不可欠なランタイム サービス。                                                                                                                                                                                                                                                                                                                                                          |
   |                   **BizTalk EDI/AS2 ランタイム**                   |                                                                                                                                                                                                                                                                                      電子データ交換 (EDI) および AS2 (Applicability Statement 2) データ トランスポート メッセージング機能のネイティブ サポートを提供するランタイム サービス。 **注:** これは、**Server ランタイム**機能を選択した場合にのみ選択できます。                                                                                                                                                                                                                                                                                       |
   |   **Windows Communication Foundation (WCF) アダプター ランタイム**    |                                                                                                                                                                                                                                                                                                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で WCF ベースのアプリケーションと通信できるようにするアダプター。 **注:** これは、**Server ランタイム**機能を選択した場合にのみ選択できます。                                                                                                                                                                                                                                                                                                   |
   |                      **ポータル コンポーネント**                      |                                                                                                                                                                                                                                                                                                                                               ポータル コンポーネントは、ビジネス データを使用して通信、協力、および意思決定を行うためにビジネス アナリストにより使用される機能のセットです。                                                                                                                                                                                                                                                                                                                                                |
   |                **ビジネス アクティビティの監視**                 |                                                                                                                                                                                                                                                                         BAM とも呼ばれ、ビジネス ユーザーがさまざまな種類のビジネス プロセスをリアルタイムに表示し、業務上重要な決定を可能にするための機能のセットです。 **注:** これは、**ポータル コンポーネント**機能を選択した場合にのみ選択できます。                                                                                                                                                                                                                                                                          |
   |             **管理ツールと監視**             |                                                                                                                                                                                                                                                                                                                            ローカル コンピューターとリモート サーバーの両方の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を管理および監視するために必要なコンポーネント。                                                                                                                                                                                                                                                                                                                             |
   | **Windows Communication Foundation (WCF) 管理ツール** |                                                                                                                                                                                                                                                                                                                         この機能を選択すると、WCF コンポーネント用の管理サービスがインストールされます。 **注:** これは、**管理ツールと監視**機能を選択した場合にのみ選択できます。                                                                                                                                                                                                                                                                                                                         |
   |                   **開発ツールおよび SDK**                   |                                                                                                                                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ソリューションの迅速な作成を可能にするサンプルとユーティリティ。 このコンポーネントの内容は、SDK サンプルおよびサポート ドキュメント、スキーマおよびマップのデザイナー、Visual Studio プロジェクト テンプレートです。 **重要:** 開発作業の予定がある場合は、このコンポーネントをインストールする必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって使用される Visual Studio 拡張機能が動作するには、この**開発ツールおよび SDK** コンポーネントがインストールされている必要があります。                                                                                                                                    |
   |                    ***追加ソフトウェア***                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
   |    **Enterprise Single Sign-On (SSO) の管理モジュール**    |                                                                                                                                                                                                                                                                                                                                                                                SSO 関連アプリケーションとそのマッピングを管理するためのインターフェイス。                                                                                                                                                                                                                                                                                                                                                                                 |
   |       **Enterprise Single Sign-On のマスター シークレット サーバー**        |                                                                                                                                                                                                                                                                                   この SSO サーバーにマスター シークレットが保存されます。 システム内の他の SSO サーバーはすべて、このサーバーからマスター シークレットを取得します。 マスター シークレット サーバーは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境に必須です。                                                                                                                                                                                                                                                                                    |
   |                  **ビジネス ルール コンポーネント**                  |                                                                                                                                                                                                                                                                                                                                                                                 ビジネス ルール エンジンによって使用されるポリシーを作成するためのコンポーネントです。                                                                                                                                                                                                                                                                                                                                                                                 |
   |                       **MQSeries エージェント**                        |                                                                                                                                                                                                                                                                                                                                                                     BizTalk Adapter for MQSeries と MQSeries Server for Windows との通信を可能にします。                                                                                                                                                                                                                                                                                                                                                                     |
   |       **Windows SharePoint Services アダプター Web サービス**       | **非推奨**。 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] コンピューターにインストールされている IIS Web サービスを使用して、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] アダプターは、Microsoft SharePoint を介して送受信されるドキュメントを処理します。<br /><br /> **推奨事項**: インストール**しないでください**。 既定では、「[付録 B: Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)」で説明されているように、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にインストールされている再配布可能な SharePoint クライアント側オブジェクト モデル (CSOM) を自動的に使用します。 |
   |                     **BAM 警告プロバイダー**                      |                                                                                                                                                                                                                                                                        BAM 警告を構成します。<br /><br /> [!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)] または [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] SP1 で BAM 警告を使用する場合は、データベース メール機能を構成する必要があります。 SQL Server Notification Services は使用できません。                                                                                                                                                                                                                                                                        |
   |                         **BAM クライアント**                          |                                                                                                                                                                                                                                                                                                                                                                                      ビジネス ユーザーが BAM を使用するためのクライアント側ソフトウェア。                                                                                                                                                                                                                                                                                                                                                                                      |
   |                        **BAM イベント**                         |                                                                                                                                                                                                                                                                                                                           Windows Workflow Foundation および Windows Communication Foundation のインターセプター。 カスタム アプリケーションから BAM データベースにイベントを送信する BAM イベント API も含まれます。                                                                                                                                                                                                                                                                                                                           |
   |                   **プロジェクト ビルド コンポーネント**                   |                                                                                                                                                                                                                                                                                                                                        このツールを使用すると、Visual Studio を使用しなくても [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ソリューションをビルドできます。                                                                                                                                                                                                                                                                                                                                        |


7. 既定のインストール先を使用するか、**[参照]** を選択して [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストール先を選択します。 **[次へ]** を選択します。  

8. ADOMD.NET などの必須コンポーネントがコンピューターにインストールされていない場合は、セットアップで必要な再配布可能コンポーネントをインストールできます。 次のいずれかを実行できます。  

   -   **[必要な再配布可能コンポーネントを Web から自動的にインストールする]** を選択します。  

        OR  

   -   CAB ファイルを既にダウンロードしている場合は、**[必要な再配布可能コンポーネントを CAB ファイルから自動的にインストールする]** を選択します。 このオプションを選択した場合は、CAB ファイルの場所を参照できます。  

9. **[概要]** で、正しいコンポーネントが選択されていることを確認します。 システム再起動後に自動的にログオンするには、**[設定]** を選択してログオン情報を入力します。 自動ログオンが有効になるのは、セットアップ実行中の再起動に対してのみであり、セットアップが完了すると無効になります。  

10. **[インストール]** をクリックしてインストール プロセスを開始します。  

11. **[Microsoft Update のセットアップ]** で、基本設定を行い、**[次へ]** を選択します。  

12. **[インストールの完了]** で、[**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成の開始**] チェック ボックスをオフにして、**[終了]** を選択します。  

## <a name="additional"></a>追加情報  

- SQL Server をインストールすると、SQL Server セットアップを実行したログオン アカウントにシステム管理者の権限が付与されます。 この権限は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールするときも必要です。したがって、次のいずれかを行う必要があります。  

  -   SQL Server のインストール時に使用した同じアカウントを使用する。  

  -   ログオン アカウントにシステム管理者の権限を付与する。  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の自己解凍 EXE をダウンロードすると、インストール ガイドが表示されます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の Setup.exe は、インストール ガイドと同じ場所にあります。  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を物理コンピューターにインストールする代わりに、[!INCLUDE[winazure](../includes/winazure-md.md)] イメージを使用して [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 仮想マシンを構成することもできます。 「[Azure VM での BizTalk Server の構成](http://msdn.microsoft.com/library/azure/jj248689.aspx)」を参照してください。  

- コマンド プロンプトを使用して [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールする手順については、「[付録 A: サイレント インストール](../install-and-config-guides/appendix-a-silent-installation.md)」を参照してください。  


## <a name="see-also"></a>参照  

 [付録 A: サイレント インストール](../install-and-config-guides/appendix-a-silent-installation.md)   
 [付録 B: Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)   
 [付録 C: 再配布可能な CAB ファイル](../install-and-config-guides/appendix-c-redistributable-cab-files.md)   
 [付録 D: SMTP サーバーの作成](../install-and-config-guides/appendix-d-create-the-smtp-server.md)