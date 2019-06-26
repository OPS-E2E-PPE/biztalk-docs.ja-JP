---
title: コンピューターのインストールの準備 |Microsoft Docs
ms.custom: ''
ms.date: 03/15/2016
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53df7a2f-638b-4921-a97f-736760248526
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d971338680c1cf9351b179bd94e253b4d69437c5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399381"
---
# <a name="prepare-your-computer-for-installation"></a>コンピューターのインストールを準備します。
このトピックでは、インストール、すべてのソフトウェア前提条件の構成しアカウントの作成とアクセス許可を設定して、コンピューターを準備する手順を使用します。  

> [!TIP] 
> 統合 MVP は、前提条件、および BizTalk Server をインストールする場合は、非常に詳細なステップ バイ ステップ ガイドを準備します。[BizTalk 2013 のインストールおよび構成パート 1](http://sandroaspbiztalkblog.wordpress.com/2013/05/05/biztalk-2013-installation-and-configuration-important-considerations-before-set-up-the-server-part-1/)します。  
> 
> ユーザー アクセス制御 (UAC) または Windows ファイアウォールを無効にするなど、いくつかの手順は Microsoft がお勧めしません。 
  
> [!IMPORTANT]
>  表示されている順序でこれらのタスクを完了します。  
  
##  <a name="BKMK_InstUpdates"></a> Windows 更新プログラムをインストールします。  
  
- **Windows 7**:[開始] をクリックします。 **検索**テキスト ボックスに「 **Windows Update**します。  
  
- **Windows 8.1、Windows Server 2012、および Windows Server 2012 R2**:キーボードと型の Windows ボタンをクリックします。 **Windows Update**します。 検索結果から次のようにクリックします。 **Windows Update**します。  
  
  更新プログラムのインストール後、コンピューターを再起動する必要がある場合があります。  
  
##  <a name="BKMK_IIS"></a> インターネット インフォメーション サービスを有効にします。  
 Microsoft インターネット インフォメーション サービス (IIS) など、多くの BizTalk Server 機能の Web アプリケーション インフラストラクチャを提供します。  
  
-   HTTP アダプター  
  
-   SOAP アダプター  
  
-   Windows SharePoint Services アダプター  
  
-   SSL (Secure Sockets Layer) 暗号化  
  
-   BAM ポータル  
  
#### <a name="install-iis"></a>IIS をインストールします。

特定のインストールの手順を参照してください。 

[IIS (Windows 8 および Windows Server 2012) のインストールします。](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/installing-iis-8-on-windows-server-2012)

[IIS (Windows 7 および Windows Vista) のインストールします。](https://docs.microsoft.com/iis/install/installing-iis-7/installing-iis-on-windows-vista-and-windows-7)


既定のチェックのオプションに加えて、IIS をインストールするときに、次も確認します。  
  
- **Web 管理ツール**:確認します。  
  
    - IIS 6 管理互換性:  
  
        - IIS 6 管理コンソール  
  
        - IIS メタベースおよび IIS 6 構成との互換性  
  
    - IIS 管理コンソール  
  
- **World Wide Web サービス**:展開**セキュリティ**も選択します。  
  
    - 基本認証  
  
    - [Windows 認証]  

また、次の点を検討してください。  
  
- **.Net framework 3.5 の機能**: .NET Framework 4.5 と .NET Framework 3.5 は、BizTalk Adapter Pack を使用する .Net アプリケーションを開発に使用できます。 通常、 **.NET Framework 4.5 機能**が既にインストールされています。 このコンピューターで、アプリケーションを作成する .NET Framework 3.5 を使用する場合 **.Net Framework 3.5 の機能**もインストールできます。  
  
- **メッセージ キュー**:チェックして、ローカルの MSMQ ストアを作成するには、MSMQ アダプターを使用している場合**メッセージ キュー**します。  
  
- **SMTP サーバー**:チェックして、ローカルの SMTP サーバーを作成するには、SMTP アダプタを使用している場合**SMTP サーバー**します。  
  
- **Windows Identity Foundation 3.5**:Windows Identity Foundation (WIF) は、CSOM インストール オプションを使用する場合、SharePoint アダプターで必要です。 [付録 b:Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)SharePoint アダプターの CSOM インストール オプションについて説明します。    
  
 
##  <a name="BKMK_XLS"></a> Microsoft Office Excel をインストールします。  
  
1. Microsoft Office のセットアップを実行します。  
  
2. 表示されたら、**インストールの種類**画面で、**カスタム インストール**、し、**次**。  
  
3. **カスタム セットアップ**画面で、 **Excel**、し、**次**します。  
  
4. **[インストール]** を選択します。  
  
5. **セットアップの完了**を選択します**完了**します。  
  
   **その他**  
  
-   BizTalk Server は、32 ビット版の Microsoft Office のみをサポートします。  
  
-   Microsoft Office Excel でビジネス アクティビティ監視 (BAM) では、BizTalk Server が必要です。 BAM の Office Excel では、監視するビジネス プロセスを定義します。 この BAM Excel ブックでは、BAM によって収集されたデータをどのようにビジネス ユーザーの画面に表示するかを定義することもできます。  
  
-   BAM.xla を Excel に正しく読み込むにインストール**アプリケーション用の Visual Basic**  **Office 共有機能**します。 それ以外の場合、エラーが発生「このブックは、VBA プロジェクト、ActiveX コントロールおよびその他のプログラミング関連の機能を紛失が」  
  
##  <a name="BKMK_VS"></a> Visual Studio をインストールします。  
  
1. Visual Studio のセットアップを管理者として実行します。  
  
2. ライセンス条項に同意し、をクリックして**次**します。  
  
3. **インストールするオプション機能**、必要なオプションを選択しを選択します。**インストール**します。 BizTalk Server は、オプション機能を必要としません。  
  
4. **完了**ページ、ウィンドウを閉じるか、をクリックして**起動**Visual Studio を開きます。  
  
   **その他**  
  
-   BizTalk Server をインストールする前に Visual Studio をインストールして、Visual Studio チーム エクスプ ローラーにアップグレードし、する必要がありますから BizTalk Server インストールを修復する場合、**コントロール パネルの**  / **プログラム**オプション。  
  
-   Visual Studio では、Microsoft SQL Server Express は自動的にインストールされますが、BizTalk Server では使用しません。 ベスト プラクティスとして、Microsoft SQL Server Express をアンインストールします。  
  
-   BizTalk Server 開発ツールは、Visual Studio をベースとして動作します。 少なくとも、BizTalk Server をインストールする前に、Visual Studio の Microsoft Visual c#® .NET コンポーネントをインストールする必要があります**開発ツールおよび SDK**します。  
  
-   Visual Studio は*いない*アプリケーション開発やデバッグが必要な実稼働コンピューター (ランタイムのみ)、BizTalk Server をインストールするかどうかに必要な。  
  
-   BizTalk Server ランタイムでは、.NET Framework 4.5 が必要です。 Windows Communication Foundation (WCF) アダプターまたは WCF インターセプターをインストールする場合、.NET Framework 3.0 が必要です。  
  
##  <a name="BKMK_SQL"></a> SQL Server をインストールします。  
 インストール[SQL Server 2008 R2](http://msdn.microsoft.com/library/bb500395\(v=sql.105\).aspx)  
  
 インストール[SQL Server 2012](http://msdn.microsoft.com/library/bb500469\(v=sql.110\).aspx)  
  
 インストール[SQL Server 2014](http://msdn.microsoft.com/library/bb500469\(v=sql.120\).aspx)  
  
 SQL Server をインストールするときに、次の機能を選択します。  
  
- データベース エンジン サービス  
  
  -   SQL Server のレプリケーション  
  
  -   フルテキスト検索  
  
- Analysis Services  
  
- Reporting Services  
  
- 共有機能  
  
  -   SQL Server Data Tools (SQL Server 2014/SQL Server 2012) または Business Intelligence Development Studio (SQL Server 2008 R2)  
  
       [SQL Server 2014 Data Tools をダウンロードします。](http://www.microsoft.com/download/details.aspx?id=42313)  
  
  -   クライアント ツール接続  
  
  -   Integration Services  
  
  -   管理ツール - 基本  
  
      -   管理ツール - 完全  
  
  **その他**  
  
- BizTalk Server では、バイナリ照合順序を除く、大文字と小文字を区別する/区別しないすべての SQL Server 照合順序がサポートされています。 バイナリ照合順序はサポートされません。  
  
- 最適なパフォーマンスは、Microsoft では、SQL Server の Enterprise Edition を使用してお勧めします。 参照してください[SQL Server 2008 R2 エディション](http://msdn.microsoft.com/library/cc645993\(v=sql.105\).aspx)、 [SQL Server 2012 エディション](http://msdn.microsoft.com/library/cc645993\(v=sql.110\).aspx)、または[SQL Server 2014 エディション](http://msdn.microsoft.com/library/cc645993\(v=sql.120\).aspx)します。  
  
- サービス パックと Windows 更新プログラムがサポートされて、インストールする必要があります。  
  
- BizTalk Server と SQL Server が別々 のコンピューター上にある場合は、分散トランザクション コーディネーター (MS DTC) は、コンピューター間のトランザクションを処理します。 SQL Server AlwaysOn 機能は、MSDTC トランザクションをサポートしません。 SQL Server AlwaysOn 機能がサポートされていません。  
  
##  <a name="BKMK_MQSeries"></a> MQSeries の前提条件をインストールします。  
 **MQSeries アダプター**:BizTalk Server のインストールと共に自動的にインストールします。  
  
 **MQSeries Client (MQSC) アダプター**:  
  
1. Host Integration Server (HIS) インストールを実行します。  
  
2. コンポーネントのインストール、展開**BizTalk Adapters**します。  
  
3. 選択**BizTalk Adapter for WebSphere MQ (クライアント ベース)** します。  
  
   **サポートされている IBM WebSphere MQ バージョン**:  
  
-   IBM WebSphere MQ 6.0.2.12 以降  
  
-   IBM WebSphere MQ 7.0.1.9 以降  
  
-   IBM WebSphere MQ 7.1.0.5 以降  
  
-   IBM WebSphere MQ 7.5.0.3 以降  
  
-   IBM WebSphere MQ 8 (実行時に限定。 管理 Api)  
  
     MQ バージョン 8 のサポートが含まれます[Host Integration Server CU3](https://support.microsoft.com/kb/3019572)します。  
  
> [!NOTE]
>  特定の WebSphere MQ バージョンが表示されない場合 MQ など 5.x では、その後はサポートされていませんこの BizTalk Server のバージョン。  
  
 **その他**  
  
- ベスト プラクティスとして常に最新の WebSphere MQ 修正パックをインストールします。 参照してください[ http://www.ibm.com/support/docview.wss?uid=swg27006037](http://www.ibm.com/support/docview.wss?uid=swg27006037)します。  
  
- IBM WebSphere MQ は、Windows 以外のコンピューターにインストールする場合は、インストール、 **MQSAgent COM + アプリケーション**(MQSConfigWiz.exe) と**MQSeries Server for Windows**同じコンピューターにします。 IBM WebSphere MQ が Windows コンピューターにインストールされている場合、 **MQSAgent COM + アプリケーション**と**MQSeries Server for Windows**プログラムがないために使用および必要な。  
  
   **MQSConfigWiz.exe** BizTalk Server インストール ファイルに含まれています。  
  
   **MQSeries Server for Windows** Microsoft プログラムでないし、IBM WebSphere MQ プログラムから入手する必要があります。  
  
- [MQSeries アダプター](http://technet.microsoft.com/library/aa547973\(v=BTS.80\).aspx)異なるコンポーネント構成など、MQSeries アダプターについて詳しく説明します。 [BizTalk Server:MQSeries と MQSeries Client (MQSC) アダプター](http://social.technet.microsoft.com/wiki/contents/articles/18316.biztalk-server-mqseries-and-mqseries-client-mqsc-adapters.aspx) MQSeries と MQSC のアダプターの追加の詳細を提供します。  
  
- IBM WebSphere はマイクロソフト製品ではないは Microsoft によってサポートされていません。 Microsoft では、このプログラムの適合性に関する保証はありません。 ダウンロードの手順を含む、IBM WebSphere MQ の詳細については、 www.ibm.com を参照してください。  
  
##  <a name="BKMK_BAMAlerts"></a> BAM 警告  
 BAM 警告の SQL Server 2012 と新しいバージョンでは、SQL Server でデータベース メールを使用します。 BAM 警告では、SQL Server 2008 R2 と以前のバージョンでは、SQL Notification Services を使用します。 インストールまたは BAM 警告の構成、前に SQL Server での Notification Services またはデータベース メールを構成する必要があります。  
  
###  <a name="BKMK_DBMail"></a> SQL Server 2012/2014 を使用して BAM 警告  
 構成[SQL Server 2012 データベース メール](http://msdn.microsoft.com/library/hh245116\(v=sql.110\).aspx)します。  
  
 構成[SQL Server 2014 Database Mail](http://msdn.microsoft.com/library/hh245116\(v=sql.120\).aspx)します。  
  
 **その他**  
  
-   データベース メールでは、SMTP サーバーを使用して、BAM 警告を送信します。 SMTP サーバーは、BizTalk サーバーまたは別の IIS サーバー上でローカルにインストールできます。 [付録 d:SMTP サーバーの作成](../install-and-config-guides/appendix-d-create-the-smtp-server.md)をインストールして、SMTP サーバーを構成する手順について説明します。  
  
###  <a name="BKMK_SSNS"></a> SQL Server 2008 R2 の SQL Server の 2005 Notification Services をインストールを使用して BAM 警告  
  
1. 移動して[Microsoft SQL Server 2005 SP4 用 Feature Pack](http://go.microsoft.com/fwlink/p/?LinkId=286285)します。  
  
2. ダウンロードして、次のコンポーネントに適したプラットフォーム パッケージをインストールします。  
  
    **Microsoft SQL Server Native Client**  
  
   - HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli.msi>"X86 パッケージ (sqlncli.msi)  
  
   - HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli_x64.msi>"X64 パッケージ (sqlncli_x64.msi)  
  
     **Microsoft SQL Server 2005 管理オブジェクト コレクション**  
  
   - HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO.msi>"X86 パッケージ (SQLServer2005_XMO.msi)  
  
   - HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO_x64.msi>"X64 パッケージ (SQLServer2005_XMO_x64.msi)  
  
     **Microsoft SQL Server 2005 Notification Services クライアント コンポーネント**  
  
   - HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS.msi>"X86 パッケージ (SQLServer2005_NS.msi)  
  
   - HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS_x64.msi>"X64 パッケージ (SQLServer2005_NS_x64.msi)  
  
   **その他**  
  
-   SQL Notification Services は; を構成する必要はありません。BizTalk Server にインストールされているだけです。  
  
##  <a name="BKMK_WIF"></a> Windows Identity Foundation  
  
|                                                              |                                                                                                                                                                                      |
|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Windows 8.1、Windows Server 2012、および Windows Server 2012 R2 |                                Windows Identity Foundation が機能として、オペレーティング システムに含まれている**オンまたはオフにする Windows 機能**します。                                |
|                      Windows Vista SP1                       | ダウンロードできます[Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331) HYPERLINK"<http://www.microsoft.com/download/details.aspx?id=17331>"。 |
  
 **その他**  
  
-   Windows Identity Foundation (WIF) は、SharePoint アダプターまたは SharePoint クライアント側オブジェクト モデル (CSOM) を使用すると SharePoint Online に必要です。 具体的な内容は次のとおりです。  
  
    |インストール オプション|WIF が必要|  
    |-------------------------|------------------|  
    |CSOM を使用した SharePoint アダプター|はい|  
    |SharePoint Online CSOM を使用しました。|はい|  
    |SharePoint アダプター Web サービスを (非推奨)|いいえ|  
    |SharePoint なし|いいえ|  
  
-   [付録 b:Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)SharePoint のインストール オプションで特定の情報を提供します。  
  
##  <a name="BKMK_WSS"></a> インストールおよび Microsoft SharePoint の構成  
 インストール[SharePoint 2013](http://technet.microsoft.com/library/cc303424.aspx)  
  
 インストール[SharePoint Online サービス](http://technet.microsoft.com/library/jj819267.aspx)  
  
 インストール[SharePoint Server 2010](http://technet.microsoft.com/library/cc303424\(v=office.14\).aspx)  
  
 インストール[SharePoint 2007](http://technet.microsoft.com/library/cc303424\(v=office.12\).aspx)  
  
 **その他**  
  
-   SharePoint をインストールする場合は、残りの BizTalk Server の前提条件を続行する前にこれを行う必要があります。  
  
-   インストールと SharePoint の構成は、次の手順で構成されます。  
  
    -   SharePoint をインストールします。  
  
    -   SharePoint を構成します。  
  
    -   仮想サーバーとして既定の Web サイトを拡張します。  
  
-   [付録 b:Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)BizTalk Server の SharePoint アダプターのインストール オプションについて説明します。  
  
-   SharePoint アダプターを使用する場合は、SharePoint サービス Web サービスではなく新しい CSOM オプションをインストール勧め説明されている[付録 b:Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)します。  
  
##  <a name="BKMK_SharedMem"></a> 共有メモリ プロトコルを無効にします。  
  
1. **[SQL Server 構成マネージャー]** を開きます。  
  
2. **SQL Server 構成マネージャー**、展開**SQL Server ネットワーク構成**、し、 **MSSQLSERVER のプロトコル**します。  
  
3. **[共有メモリ]** を右クリックし、 **[無効]** を選択します。  
  
4. 選択**SQL Server サービス**を右クリックして**SQL Server (MSSQLSERVER)** 、し、**停止**します。 右クリックし、サービスが停止したら、 **SQL Server (MSSQLSERVER)** もう一度、し、**開始**。  
  
5. **SQL Server 構成マネージャー**を終了します。  
  
   **その他**  
  
-   ある種のストレス条件下では (たとえば、同じコンピューターから複数のクライアントが SQL Server にアクセスしている場合)、SQL Server の共有メモリ プロトコルが原因で BizTalk Server のパフォーマンスが低下することがあります。 この問題を解決するには、SQL Server ネットワークの構成で、共有メモリ ネットワーク プロトコルを無効にします。  
  
-   ReplaceThisText  
  
##  <a name="BKMK_LocalAdmin"></a> ローカルの Administrators グループに参加します。  
 **Windows Server 2012** :[Windows Server 2012:ローカル管理者グループにアカウントを追加する方法](http://social.technet.microsoft.com/wiki/contents/articles/13436.windows-server-2012-how-to-add-an-account-to-a-local-administrator-group.aspx)  
  
 **Windows 8.1**:Windows 8 でローカル ユーザーとグループを開くには、キーボードと型の Windows ボタンをクリックして**グループ**します。 [検索] ウィンドウで、次のようにクリックします。**設定**します。 結果ウィンドウで次のようにクリックします。**ローカル ユーザーとグループの編集**します。 クリックして**グループ**し、アカウントを追加する管理者をダブルクリックします。  
  
 **Windows 7 SP1**:[開始] をクリックします。 **検索**テキスト ボックスに「**コンピュータの管理**、 をクリックして開きます。 展開**ローカル ユーザーとグループ**、 をクリックして**グループ**、し、アカウントを追加する管理者をダブルクリックします。  
  
 **その他**  
  
-   インストールして、BizTalk Server を構成するには、ローカルの Administrators グループのメンバーがあります。  
  
##  <a name="BKMK_AppLog"></a> アプリケーション イベント ログを構成します。  
  
1. 開いている**イベント ビューアー**:  
  
    **Windows Server 2012** :キーボードと型の Windows ボタンをクリックします。**イベント ビューアー**します。 結果ウィンドウで次のようにクリックします。**イベント ビューアー**します。  
  
    **Windows 8.1**:キーボードと型の Windows ボタンをクリックします。**イベント ビューアー**します。 [検索] ウィンドウで、次のようにクリックします。**設定**します。 結果ウィンドウで次のようにクリックします。**イベント ログを表示**します。  
  
    **Windows 7 SP1**:[開始] をクリックします。 **検索**テキスト ボックスに「**イベント ビューアー** をクリックして開きます。  
  
2. 展開**Windows ログ**を右クリックして**アプリケーション**、 をクリックし、**プロパティ**します。 **ログ プロパティ**:  
  
   -   使用可能な空き領域を確認するには、 **[ログ サイズ]** と **[最大ログ サイズ]** のプロパティを比較します。  
  
   -   多くの領域を提供するには、上位の番号を入力します。**最大ログ サイズ**します。  
  
   -   ログの空き領域がなくなったときに古いイベントが上書きされるようにするには、 **[必要に応じてイベントを上書きする]** を選択します。  
  
   -   ログ イベントを消去するには、 **[ログの消去]** を選択します。  
  
3. をクリックして**OK**を閉じる、**イベント ビューアー**します。  
  
   **その他**  
  
-   BizTalk Server のセットアップを実行すると、イベントの記録がアプリケーション イベント ログに保存されます。 インストールされる BizTalk Server の機能によっては、ログの空き領域を超える大きさのログが作成されることもあります。 BizTalk Server のセットアップ中に、アプリケーション イベント ログの領域が不足している場合、インストールは失敗します。 アプリケーション イベント ログの設定を変更すれば、この失敗を回避できます。  
  
## <a name="next"></a>Next  
 [BizTalk Server の機能とコンポーネントを選択します。](http://msdn.microsoft.com/library/b8c43fcf-9e5c-48ba-830b-13a5177e30f0)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 2013 および 2013 R2 のインストールの概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)   
 [付録 a:サイレント インストール](../install-and-config-guides/appendix-a-silent-installation.md)   
 [付録 b:Microsoft SharePoint アダプターをインストールします。](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)   
 [付録 c:再頒布可能 CAB ファイル](../install-and-config-guides/appendix-c-redistributable-cab-files.md)   
 [付録 d:SMTP サーバーを作成します。](../install-and-config-guides/appendix-d-create-the-smtp-server.md)
