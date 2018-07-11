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
ms.openlocfilehash: bba64728220eb2fc5be99153892d68e93eb8e22c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017208"
---
# <a name="prepare-your-computer-for-installation"></a>インストールのためのコンピューターの準備
ここでは、コンピューターの準備を整える手順について説明します。必要なソフトウェアをすべてインストールして構成し、アカウントを作成してアクセス許可を設定します。  

> [!TIP] 
> 統合に詳しいユーザーが、前提条件と BizTalk Server をインストールするとても詳細な手順が説明された「[BizTalk 2013 Installation and Configuration part 1](http://sandroaspbiztalkblog.wordpress.com/2013/05/05/biztalk-2013-installation-and-configuration-important-considerations-before-set-up-the-server-part-1/)」 (BizTalk 2013 のインストールおよび構成パート 1) を用意しました。  
> 
> ユーザー アクセス制御 (UAC) や Windows ファイアウォールの無効化など、いくつかの手順はマイクロソフトでは推奨していません。 
  
> [!IMPORTANT]
>  ここに示している順序どおりに作業は実行してください。  
  
##  <a name="BKMK_InstUpdates"></a> Windows の更新プログラムをインストールする  
  
- **Windows 7**: [スタート] をクリックします。 **[検索]** テキスト ボックスで、「**Windows Update**」と入力します。  
  
- **Windows 8.1、Windows Server 2012、および Windows Server 2012 R2**: キーボードの Windows ボタンをクリックします。 **Windows Update**します。 検索結果] ウィンドウで、**[Windows Update]** をクリックします。  
  
  更新プログラムのインストール後、コンピューターを再起動する必要がある場合があります。  
  
##  <a name="BKMK_IIS"></a> インターネット インフォメーション サービス (IIS) の有効化  
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
  
- **[Web 管理ツール]**: 次の項目もオンにします。  
  
    - IIS 6 管理互換:  
  
        - IIS 6 管理コンソール  
  
        - IIS メタベースおよび IIS 6 構成との互換性  
  
    - IIS 管理コンソール  
  
- **[World Wide Web サービス]**: **[セキュリティ]** を展開し、次も選択します。  
  
    - 基本認証  
  
    - [Windows 認証]  

次のことも考慮してください。  
  
- **.Net framework 3.5 の機能**: .NET Framework 4.5 と .NET Framework 3.5 は、BizTalk Adapter Pack を使用する .Net アプリケーションを開発に使用できます。 通常、 **.NET Framework 4.5 機能**が既にインストールされています。 このコンピューターで、アプリケーションを作成する .NET Framework 3.5 を使用する場合 **.Net Framework 3.5 の機能**もインストールできます。  
  
- **メッセージ キュー**: MSMQ アダプターを使用する場合は、**[メッセージ キュー]** をオンにしてローカルの MSMQ ストアを作成できます。  
  
- **SMTP サーバー**: SMTP アダプターを使用する場合は、**[SMTP サーバー]** をオンにしてローカルの SMTP サーバーを作成できます。  
  
- **Windows Identity Foundation 3.5**: CSOM インストール オプションを使用する場合に、SharePoint アダプターによって Windows Identity Foundation (WIF) が必要です。 [付録 b: Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)SharePoint アダプターの CSOM インストール オプションについて説明します。    
  
 
##  <a name="BKMK_XLS"></a> Microsoft Office Excel のインストール  
  
1. Microsoft Office のセットアップを実行します。  
  
2. **[インストールの種類]** 画面が表示されたら、**[カスタム インストール]** を選択し、**[次へ]** を選択します。  
  
3. **[カスタム セットアップ]** 画面で、**[Excel]** を選択し、**[次へ]** を選択します。  
  
4. **[インストール]** を選択します。  
  
5. **[セットアップが完了しました]** 画面で、**[終了]** を選択します。  
  
   **追加情報**  
  
-   BizTalk Server は、32 ビット版の Microsoft Office のみをサポートします。  
  
-   Microsoft Office Excel でビジネス アクティビティ監視 (BAM) では、BizTalk Server が必要です。 BAM の Office Excel では、監視するビジネス プロセスを定義します。 この BAM Excel ブックでは、BAM によって収集されたデータをどのようにビジネス ユーザーの画面に表示するかを定義することもできます。  
  
-   BAM.xla を Excel に正しく読み込むには、**[Office 共有機能]** の下の **[Visual Basic for Applications]** をインストールします。 これを行わない場合は、「このブックにある、VBA プロジェクト、ActiveX コントロール、およびその他のプログラミング関連の機能は失われています。」というエラーが表示されることがあります。  
  
##  <a name="BKMK_VS"></a> Visual Studio のインストール  
  
1. Visual Studio のセットアップを管理者として実行します。  
  
2. ライセンス契約に同意して、**[次へ]** をクリックします。  
  
3. **[インストールするオプション機能]** で必要なオプションを選択し、**[インストール]** を選択します。 BizTalk Server は、オプション機能を必要としません。  
  
4. **[完了]** ページで、ウィンドウを閉じるか **[起動]** をクリックして Visual Studio を開きます。  
  
   **追加情報**  
  
-   BizTalk Server をインストールする前に Visual Studio をインストールして、Visual Studio チーム エクスプ ローラーにアップグレードし、する必要がありますから BizTalk Server インストールを修復する場合、**コントロール パネルの ** / **プログラム**オプション。  
  
-   Visual Studio では、Microsoft SQL Server Express は自動的にインストールされますが、BizTalk Server では使用しません。 Microsoft SQL Server Express をアンインストールすることをお勧めします。  
  
-   BizTalk Server 開発ツールは、Visual Studio をベースとして動作します。 少なくとも、BizTalk Server をインストールする前に、Visual Studio の Microsoft Visual c#® .NET コンポーネントをインストールする必要があります**開発ツールおよび SDK**します。  
  
-   Visual Studio は*いない*アプリケーション開発やデバッグが必要な実稼働コンピューター (ランタイムのみ)、BizTalk Server をインストールするかどうかに必要な。  
  
-   BizTalk Server ランタイムでは、.NET Framework 4.5 が必要です。 Windows Communication Foundation (WCF) アダプターまたは WCF インターセプターをインストールする場合は、.NET Framework 3.0 が必要です。  
  
##  <a name="BKMK_SQL"></a> SQL Server のインストール  
 [SQL Server 2008 R2](http://msdn.microsoft.com/library/bb500395\(v=sql.105\).aspx) のインストール  
  
 [SQL Server 2012](http://msdn.microsoft.com/library/bb500469\(v=sql.110\).aspx) のインストール  
  
 [SQL Server 2014 ](http://msdn.microsoft.com/library/bb500469\(v=sql.120\).aspx) のインストール  
  
 SQL Server をインストールするときに、次の機能を選択します。  
  
- データベース エンジン サービス  
  
  -   SQL Server のレプリケーション  
  
  -   フルテキスト検索  
  
- Analysis Services  
  
- Reporting Services  
  
- 共有機能  
  
  -   SQL Server Data Tools (SQL Server 2014 / SQL Server 2012) または Business Intelligence Development Studio (SQL Server 2008 R2)  
  
       [SQL Server 2014 Data Tools のダウンロード](http://www.microsoft.com/download/details.aspx?id=42313)  
  
  -   クライアント ツール接続  
  
  -   Integration Services  
  
  -   管理ツール - 基本  
  
      -   管理ツール - 完全  
  
  **追加情報**  
  
- BizTalk Server では、バイナリ照合順序を除く、大文字と小文字を区別する/区別しないすべての SQL Server 照合順序がサポートされています。 バイナリ照合順序はサポートされません。  
  
- 最適なパフォーマンスを得るには、SQL Server の Enterprise Edition を使用することをお勧めします。 詳細は、「[SQL Server 2008 R2 の各エディションがサポートする機能](http://msdn.microsoft.com/library/cc645993\(v=sql.105\).aspx)」、「[SQL Server 2012 の各エディションがサポートする機能](http://msdn.microsoft.com/library/cc645993\(v=sql.110\).aspx)」または「[SQL Server 2014 の各エディションがサポートする機能](http://msdn.microsoft.com/library/cc645993\(v=sql.120\).aspx)」をご覧ください。  
  
- Service Pack および Windows Updates はいずれもサポートされており、インストールする必要があります。  
  
- BizTalk Server と SQL Server が別々 のコンピューター上にある場合は、分散トランザクション コーディネーター (MS DTC) は、コンピューター間のトランザクションを処理します。 SQL Server AlwaysOn 機能は、MSDTC トランザクションをサポートしません。 SQL Server AlwaysOn 機能がサポートされていません。  
  
##  <a name="BKMK_MQSeries"></a> MQSeries に必要なソフトウェアをインストールする  
 **MQSeries アダプター**: BizTalk Server のインストール時に自動的にインストールされます。  
  
 **MQSeries Client (MQSC) アダプター**:  
  
1. Host Integration Server (HIS) インストールの実行  
  
2. コンポーネントのインストールで、**[BizTalk アダプター]** を展開します。  
  
3. **[BizTalk Adapter for WebSphere MQ (クライアント ベース)]** を選択します。  
  
   **サポート対象の IBM WebSphere MQ バージョン**:  
  
-   IBM WebSphere MQ 6.0.2.12 以降  
  
-   IBM WebSphere MQ 7.0.1.9 以降  
  
-   IBM WebSphere MQ 7.1.0.5 以降  
  
-   IBM WebSphere MQ 7.5.0.3 以降  
  
-   IBM WebSphere MQ 8 (実行時に限定。管理 API はなし)  
  
     MQ バージョン 8 は [Host Integration Server CU3](https://support.microsoft.com/kb/3019572) でサポートされています。  
  
> [!NOTE]
>  特定の WebSphere MQ バージョンが表示されない場合 MQ など 5.x では、その後はサポートされていませんこの BizTalk Server のバージョン。  
  
 **追加情報**  
  
- 常に最新の WebSphere MQ 修正パックをインストールすることをお勧めします。 参照してください[ http://www.ibm.com/support/docview.wss?uid=swg27006037](http://www.ibm.com/support/docview.wss?uid=swg27006037)します。  
  
- IBM WebSphere MQ が Windows 以外のコンピューターにインストールされている場合は、同じコンピューターに **MQSAgent COM+ アプリ** (MQSConfigWiz.exe) と **MQSeries Server for Windows** をインストールします。 IBM WebSphere MQ が Windows コンピューターにインストールされている場合は、**MQSAgent COM+ アプリ**と **MQSeries Server for Windows** プログラムは使用することも必要になることもありません。  
  
   **MQSConfigWiz.exe** BizTalk Server インストール ファイルに含まれています。  
  
   **MQSeries Server for Windows** はマイクロソフトのプログラムではありませんので、IBM WebSphere MQ プログラムから入手する必要があります。  
  
- 「[MQSeries アダプター](http://technet.microsoft.com/library/aa547973\(v=BTS.80\).aspx)」には、異なるコンポーネント構成など、MQSeries アダプターに関する詳細情報が記載されています。 [BizTalk Server: 「MQSeries と MQSeries Client (MQSC) のアダプター](http://social.technet.microsoft.com/wiki/contents/articles/18316.biztalk-server-mqseries-and-mqseries-client-mqsc-adapters.aspx)」には、MQSeries と MQSC のアダプターの詳細が記載されています。  
  
- IBM WebSphere はマイクロソフト製品ではないため、マイクロソフトによるサポートはありません。 マイクロソフトでは、このプログラムの適合性に関して一切の保証も行いません。 IBM WebSphere MQ のダウンロード方法をはじめとする詳細については、www.ibm.com をご覧ください。  
  
##  <a name="BKMK_BAMAlerts"></a> BAM 警告  
 BAM 警告の SQL Server 2012 と新しいバージョンでは、SQL Server でデータベース メールを使用します。 BAM 警告では、SQL Server 2008 R2 と以前のバージョンでは、SQL Notification Services を使用します。 インストールまたは BAM 警告の構成、前に SQL Server での Notification Services またはデータベース メールを構成する必要があります。  
  
###  <a name="BKMK_DBMail"></a> SQL Server 2012/2014 での BAM 警告  
 [SQL Server 2012 データベース メールの構成](http://msdn.microsoft.com/library/hh245116\(v=sql.110\).aspx)を行います。  
  
 [SQL Server 2014 データベース メールの構成](http://msdn.microsoft.com/library/hh245116\(v=sql.120\).aspx)を行います。  
  
 **追加情報**  
  
-   データベース メールでは SMTP サーバーを使用して BAM 警告を送信します。 SMTP サーバーは、BizTalk サーバーまたは別の IIS サーバー上でローカルにインストールできます。 「[付録 D: SMTP サーバーの作成](../install-and-config-guides/appendix-d-create-the-smtp-server.md)」には、SMTP サーバーのインストールおよび構成手順があります。  
  
###  <a name="BKMK_SSNS"></a> SQL Server 2008 R2 を使用する BAM 警告 - SQL Server 2005 通知サービスのインストール  
  
1. 「[Microsoft SQL Server 2005 SP4 用 Feature Pack](http://go.microsoft.com/fwlink/p/?LinkId=286285)」にアクセスします。  
  
2. 次のコンポーネントに適したプラットフォーム パッケージをダウンロードしてインストールします。  
  
    **Microsoft SQL Server Native Client**  
  
   - HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli.msi>"X86 パッケージ (sqlncli.msi)  
  
   - HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli_x64.msi>"X64 パッケージ (sqlncli_x64.msi)  
  
     **Microsoft SQL Server 2005 管理オブジェクト コレクション**  
  
   - HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO.msi>"X86 パッケージ (SQLServer2005_XMO.msi)  
  
   - HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO_x64.msi>"X64 パッケージ (SQLServer2005_XMO_x64.msi)  
  
     **Microsoft SQL Server 2005 Notification Services クライアント コンポーネント**  
  
   - HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS.msi>"X86 パッケージ (SQLServer2005_NS.msi)  
  
   - HYPERLINK"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS_x64.msi>"X64 パッケージ (SQLServer2005_NS_x64.msi)  
  
   **追加情報**  
  
-   SQL Notification Services は; を構成する必要はありません。BizTalk Server にインストールされているだけです。  
  
##  <a name="BKMK_WIF"></a> Windows Identity Foundation  
  
|                                                              |                                                                                                                                                                                      |
|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Windows 8.1、Windows Server 2012、および Windows Server 2012 R2 |                                Windows Identity Foundation は **[Windows の機能の有効化または無効化]** に表示される機能としてオペレーティング システムに含まれています。                                |
|                      Windows Vista SP1                       | ダウンロードできます[Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331) HYPERLINK"<http://www.microsoft.com/download/details.aspx?id=17331>"。 |
  
 **追加情報**  
  
-   Windows Identity Foundation (WIF) は、SharePoint アダプターまたは SharePoint クライアント側オブジェクト モデル (CSOM) を使用すると SharePoint Online に必要です。 具体的な内容は次のとおりです。  
  
    |インストール オプション|WIF が必要|  
    |-------------------------|------------------|  
    |CSOM を使用した SharePoint アダプター|はい|  
    |CSOM を使用した SharePoint Online|はい|  
    |SharePoint アダプター Web サービスを (非推奨)|いいえ|  
    |SharePoint なし|いいえ|  
  
-   [付録 b: Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)SharePoint のインストール オプションで特定の情報を提供します。  
  
##  <a name="BKMK_WSS"></a> Microsoft SharePoint のインストールと構成  
 [SharePoint 2013](http://technet.microsoft.com/library/cc303424.aspx) をインストールする  
  
 [SharePoint Online Service](http://technet.microsoft.com/library/jj819267.aspx) をインストールする  
  
 [SharePoint Server 2010](http://technet.microsoft.com/library/cc303424\(v=office.14\).aspx) をインストールする  
  
 [SharePoint 2007](http://technet.microsoft.com/library/cc303424\(v=office.12\).aspx) をインストールする  
  
 **追加情報**  
  
-   SharePoint をインストールする場合は、残りの BizTalk Server の前提条件を続行する前にこれを行う必要があります。  
  
-   SharePoint のインストールと構成の手順は、次のとおりです。  
  
    -   SharePoint をインストールする  
  
    -   SharePoint を構成する  
  
    -   既定の Web サイトを仮想サーバーとして拡張する  
  
-   「[付録 B: Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)」には、BizTalk Server の SharePoint アダプターのインストール オプションに関する情報があります。  
  
-   SharePoint アダプターを使用する際は、SharePoint サービスの Web サービスの代わりに新しい CSOM オプションをインストールすることをお勧めします。詳細は「[付録 B: Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)」をご覧ください。  
  
##  <a name="BKMK_SharedMem"></a> 共有メモリ プロトコルの無効化  
  
1. **[SQL Server 構成マネージャー]** を開きます。  
  
2. **SQL Server 構成マネージャー**で、**[SQL Server ネットワークの構成]** を展開して **[MSSQLSERVER のプロトコル]** を選択します。  
  
3. **[共有メモリ]** を右クリックし、**[無効]** を選択します。  
  
4. **[SQL Server サービス]** を選択し、**[SQL Server (MSSQLSERVER)]** を右クリックして、**[停止]** を選択します。 サービスが停止したら、**[SQL Server (MSSQLSERVER)]** をもう一度右クリックして **[開始]** を選択します。  
  
5. **SQL Server 構成マネージャー**を終了します。  
  
   **追加情報**  
  
-   ある種のストレス条件下では (たとえば、同じコンピューターから複数のクライアントが SQL Server にアクセスしている場合)、SQL Server の共有メモリ プロトコルが原因で BizTalk Server のパフォーマンスが低下することがあります。 この動作を解決するには、共有メモリ ネットワーク プロトコルを無効にするよう SQL Server ネットワークの構成で設定します。  
  
-   ReplaceThisText  
  
##  <a name="BKMK_LocalAdmin"></a>ローカルの Administrators グループへの参加  
 **Windows Server 2012** : [Windows Server 2012: ローカル管理者グループにアカウントを追加する方法](http://social.technet.microsoft.com/wiki/contents/articles/13436.windows-server-2012-how-to-add-an-account-to-a-local-administrator-group.aspx)  
  
 **Windows 8.1**: Windows 8 でローカルのユーザーとグループを開くには、キーボードの Windows ボタンをクリックして「**グループ**」と入力します。 検索] ウィンドウで、**[設定]** をクリックします。 検索結果] ウィンドウで、**[ローカル ユーザーとグループの編集]** をクリックします。 **[グループ]** をクリックし、[Administrators をダブルクリックしてアカウントを追加します。  
  
 **Windows 7 SP1**: [スタート] をクリックします。 **[検索]** テキスト ボックスに「**コンピューターの管理**」と入力し、クリックして開きます。 **[ローカル ユーザーとグループ]** を展開し、**[グループ]** をクリックしてから [Administrator をダブルクリックしてアカウントを追加します。  
  
 **追加情報**  
  
-   インストールして、BizTalk Server を構成するには、ローカルの Administrators グループのメンバーがあります。  
  
##  <a name="BKMK_AppLog"></a> アプリケーション イベント ログの構成  
  
1. **イベント ビューアー**を開きます。  
  
    **Windows Server 2012** : キーボードの Windows ボタンをクリックします。**イベント ビューアー**します。 検索結果] ウィンドウで、**[イベント ビューアー]** をクリックします。  
  
    **Windows 8.1**: キーボードの Windows ボタンをクリックして「**イベント ビューアー**」と入力します。 検索] ウィンドウで、**[設定]** をクリックします。 検索結果] ウィンドウで、**[イベント ログの表示]** をクリックします。  
  
    **Windows 7 SP1**: [スタート] をクリックします。 **[検索]** テキスト ボックスに **「イベント ビューアー」** と入力し、クリックして開きます。  
  
2. **[Windows ログ]** を展開し、**[アプリケーション]** を右クリックして **[プロパティ]** をクリックします。 **[ログのプロパティ]**:  
  
   -   使用可能な空き領域を確認するには、**[ログ サイズ]** と **[最大ログ サイズ]** のプロパティを比較します。  
  
   -   空き領域を増やすには、**[最大ログ サイズ]** の数値を増やします。  
  
   -   ログの空き領域がなくなったときに古いイベントが上書きされるようにするには、**[必要に応じてイベントを上書きする]** を選択します。  
  
   -   ログ イベントを消去するには、**[ログの消去]** を選択します。  
  
3. **[OK]** をクリックして **[イベント ビューアー]** を閉じます。  
  
   **追加情報**  
  
-   BizTalk Server のセットアップを実行すると、イベントの記録がアプリケーション イベント ログに保存されます。 インストールされる BizTalk Server の機能によっては、ログの空き領域を超える大きさのログが作成されることもあります。 BizTalk Server のセットアップ中に、アプリケーション イベント ログの領域が不足している場合、インストールは失敗します。 アプリケーション イベント ログの設定を変更すれば、この失敗を回避できます。  
  
## <a name="next"></a>Next  
 [BizTalk Server の機能とコンポーネントの選択](http://msdn.microsoft.com/library/b8c43fcf-9e5c-48ba-830b-13a5177e30f0)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 2013 および 2013 R2 のインストール概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)   
 [付録 A: サイレント インストール](../install-and-config-guides/appendix-a-silent-installation.md)   
 [付録 B: Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)   
 [付録 C: 再配布可能な CAB ファイル](../install-and-config-guides/appendix-c-redistributable-cab-files.md)   
 [付録 D: SMTP サーバーの作成](../install-and-config-guides/appendix-d-create-the-smtp-server.md)
