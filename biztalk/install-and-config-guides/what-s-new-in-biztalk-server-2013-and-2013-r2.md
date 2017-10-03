---
title: "BizTalk Server 2013 および 2013 R2 の新機能 |Microsoft ドキュメント"
description: "新機能および BizTalk Server 2013 R2 と 2013 での変更の完全な一覧"
caps.latest.revision: "67"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 2017-08-10
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bdb841f7-4aa9-45c9-a6f1-d527089fcc09
ms.author: mandia
ms.openlocfilehash: 49a4e668f1c5e23169464fdbc4b4f0464a062628
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="whats-new-in-biztalk-server-2013-and-2013-r2"></a>BizTalk Server 2013 および 2003 R2 の新機能
[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] と [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013 の新機能と廃止予定機能をご覧ください。
  
##  <a name="BKMK_NewR2"></a> BizTalk Server 2013 R2 の新機能  
  
|機能|説明|  
|-------------|-----------------|  
|新しいバージョンの Windows OS、SQL Server、および Visual Studio のサポート|「[BizTalk Server 2013 および 2013 R2 のハードウェア/ソフトウェア要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)」を参照してください。|  
|JSON のサポート|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、JSON メッセージの送受信がサポートされるようになりました。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には JSON インスタンスから XSD スキーマを生成するウィザードと、カスタム パイプラインで使用するエンコーダー/デコーダー コンポーネントがあります。 詳細については、「[BizTalk Server を使用した JSON メッセージの処理](../core/processing-json-messages-using-biztalk-server.md)」を参照してください。|  
|SB-Messaging アダプターのアップデート|SB Messaging アダプターは、ACS に加えて SAS (Shared Access signature) ベースの認証をサポートするよう強化されました。  この改善によって、BizTalk Server での Service Bus のオンプレミス エディションとのやりとりも可能になります。 詳細については、「[SB-Messaging アダプター](../core/sb-messaging-adapter.md)」を参照してください。|  
|SFTP アダプターのアップデート|SFTP アダプターで 2 要素認証がサポートされるようになり、大きなファイルのアップロード/ダウンロード時に一時フォルダーを指定できるようになりました。 また、ターゲットのサーバー固有の Encryption 暗号値を選択することもできます。 詳細については、「[SFTP アダプター](../core/sftp-adapter.md)」を参照してください。|  
|HL7 アクセラレータのアップデート|HL7 アクセラレータで、以下がサポートされるようになりました:<br /><br /> - HL7 パイプラインで処理できるメッセージの一部として、フリー テキスト データを含めることができます。<br /><br /> - HL7 アダプターのホストに 64 ビットがサポートされます。<br /><br /> 「[What's New in BizTalk Accelerator for HL7](http://msdn.microsoft.com/library/ee409458\(v=bts.80\).aspx)」 (HL7 向けの BizTalk アクセラレータの新機能) を参照してください。|  
|BizTalk Health Monitor|BizTalk Health Monitor is は新しい BizTalk スナップインで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境の正常性をモニターするのに役立ちます。 このスナップインは、既存の BizTalk 管理コンソールに追加することも、単独で実行することもできます。 BizTalk Health Monitor には次のような機能があります。<br /><br /> - 状態レポートを生成し、表示<br /><br /> - BizTalk 環境の正常性情報全般をダッシュボードに表示<br /><br /> - 電子メール通知を送信<br /><br /> - レポートの収集をスケジュール<br /><br /> - 読み込み済みシナリオ ベースのパフォーマンス カウンタとのパフォーマンス モニター統合<br /><br /> - 複数の BizTalk 環境をモニター<br /><br /> - レポート管理<br /><br /> BizTalk Health Monitor について詳しくは、「[BizTalk Health Monitor を使用するにあたって](http://go.microsoft.com/fwlink/?LinkId=403315)」と「[BizTalk Health Monitor の概要](http://go.microsoft.com/fwlink/?LinkId=403316)」をご覧ください。|  
  
### <a name="deprecated-list"></a>廃止機能の一覧  
  
|プログラム|Status|代替|  
|-------------|------------|-----------------|  
|RFID Mobile|削除|なし|  
|RFID サーバー|廃止予定|なし|  
|SharePoint SSOM/Web サービス アダプター|廃止予定|クライアント側オブジェクト モデル (CSOM) オプションを使用します。<br /><br /> [Windows SharePoint Services アダプター](../core/windows-sharepoint-services-adapter.md)<br /><br /> [付録 B: Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)|  
|SOAP アダプター|廃止予定|[WCF-BasicHttp アダプター](../core/wcf-basichttp-adapter.md)|  
|以前の SQL アダプター|廃止予定|[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] の WCF ベースの SQL アダプター|  
|UDDI|廃止予定|なし|  
  
> [!IMPORTANT]
>  これらの廃止機能の一部は、新しいバージョンの BizTalk に搭載されている場合があります。 そのような場合、次の点を考慮してください。  
>   
>  -   機能が BizTalk 内で内部的に使用され、顧客のソリューションでの使用が考慮されていない場合があります。 その場合、顧客のソリューションではサポートされません。  
> -   インターフェイスが Microsoft によって変更されており、公開できない場合があります。  
  
##  <a name="BKMK_New"></a> BizTalk Server 2013 の新機能  
 BizTalk Server 2013 に以下の機能が追加されました。  
  
 **Azure IaaS の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**  
  
|機能|説明|  
|-------------|-----------------|  
|[!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[vm](../includes/vm-md.md)] で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する|「[Windows Azure で BizTalk 仮想マシンを作成する](http://msdn.microsoft.com/library/jj572843.aspx)」を参照してください。|  
|[!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[vm](../includes/vm-md.md)] で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] グループを作成する|「[BizTalk グループの前提条件を作成する](http://msdn.microsoft.com/library/jj248711.aspx)」と「[BizTalk グループの構成](http://msdn.microsoft.com/library/jj572845.aspx)」を参照してください。|  
  
 **オンプレミスの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**  
  
|機能|説明|  
|-------------|-----------------|  
|コア ベースのライセンス モデル|BizTalk Server 2013 はコア ベースです。 SQL Server 2012 もコア ベースです。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010 および以前のバージョンはプロセッサ ベースです。<br /><br /> コア数が 4 つ以下のプロセッサで [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を実行する場合、ライセンス料は [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010 と変わりありません。 コア ライセンスは、1 つのプロセッサのライセンス料の 4 分の 1 の価格です。 サーバーを実行する場合、そのプロセッサの処理能力が高ければ高いほど、つまりそのハードウェアの処理能力の向上に合わせてライセンス料も増大します。<br /><br /> 必要なだけのライセンス数を決定できるように、*C:\Program Files (x86)\Microsoft BizTalk Server 20xx\SDK\Utilities\LicenseUsageTracking* には PowerShell コマンドレットが用意されています。<br /><br /> 役立つリンク:<br /><br /> [BizTalk Server 2013 の価格とエディション](http://www.microsoft.com/biztalk/pricing.aspx)<br /><br /> [BizTalk Server 2013 のライセンスを把握する](http://blogs.biztalk360.com/understand-biztalk-server-2013-licensing/)|  
|新しいアダプターのサポート|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションの [!INCLUDE[winazure](../includes/winazure-md.md)] への接続を拡張するために、新しいアダプターが用意されています。 また、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、SharePoint アダプターも更新されていて、ユーザーは、SharePoint サーバーへの接続にクライアント側オブジェクト モデルとサーバー側オブジェクト モデルのどちらを使用するかを選択できます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、SFTP サーバーとの間でメッセージを送受信する新しいアダプターが含まれています。|  
|アイテム間の依存関係の追跡|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールが更新され、UI 駆動型の操作を実現し、オーケストレーション、送信ポート、受信場所などのさまざまな [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のアイテムがどのように相互に依存しているかを示します。 詳細については、「[BizTalk Server アプリケーションにおけるアイテム間の依存関係の追跡](../core/tracking-dependencies-between-artifacts-in-a-biztalk-server-application.md)」を参照してください。|  
|統合された ESB Toolkit|ESB Toolkit は [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] セットアップの一部として統合されました。 また、ESB Toolkit の構成操作が単純化され、ユーザーは開始までの時間を短縮することができます。 詳細については、「[Microsoft BizTalk ESB Toolkit のインストールと構成](../esb-toolkit/install-and-configure-the-microsoft-biztalk-esb-toolkit.md)」を参照してください。|  
|新しいバージョンの Windows OS、SQL Server、および Visual Studio のサポート|「[BizTalk Server 2013 および 2013 R2 のハードウェア/ソフトウェア要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)」を参照してください。|  
|サポートされている EDI スキーマの更新|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、以下の EDI スキーマのサポートが導入されています。<br /><br /> -                     **X12** – 5040、5050、6020、6030<br /><br /> - **EDIFACT** – D06A、D06B、D07A、D07B、D08A、D08B、D09A、D09B、D10A、D10B<br /><br /> -                     **HL7** – メッセージ サポート 2.51 の追加<br /><br /> -                     **SWIFT** – Message Pack 2012<br /><br /> スキーマは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インストール パッケージに含まれています。 インストール パッケージは、[http://go.microsoft.com/fwlink/p/?LinkId=258228](http://go.microsoft.com/fwlink/p/?LinkId=258228) からダウンロードできます。|  
|マッパーの XSLCompiledTransform の使用|マッパーは XSLCompiledTransform クラスを使用します。 旧バージョンの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、XslTransform クラスを使用していましたが、廃止されました。 XSLCompiledTransform クラスは、次のようにパフォーマンスが強化されました。<br /><br /> - Load メソッドが正常に完了すると、複数のスレッドから同時に Transform を呼び出すことができます。<br /><br /> - 新しい XSLT プロセッサは、XSLT スタイル シートを一般的な中間形式にコンパイルします。 スタイル シートがコンパイルされると、キャッシュされ再利用できるようになります。<br /><br /> 「[What the Mapper Updates Mean for You](http://www.quicklearn.com/blog/2013/05/24/what-the-biztalk-server-2013-mapper-updates-mean-for-you/)」 (マッパー更新の概要) と「[XslCompiledTransform クラス](https://msdn.microsoft.com/library/system.xml.xsl.xslcompiledtransform.aspx)」に詳細があります。|  
|構成可能な動的送信ポート ハンドラー|動的送信ポートを作成するときに、インストールされている*すべて*のアダプターについて、アダプターの送信ハンドラーを構成できます。 これには、一方向のポートと応答動的ポートの両方が含まれています。 以前のバージョンの BizTalk では、動的送信ポートでアダプターの既定ホストを使用します。<br /><br /> 「[動的送信ポート ハンドラーは構成可能](../core/dynamic-send-port-handler-is-configurable.md)」に追加情報があります。|  
|順次配送|順次配送で複数のエンドポイントを使用する場合にシナリオを用いた以前の BizTalk バージョンでは、最も遅い種類のアダプターが最高速度になります。 この動作は直接、HL7 ソリューションに影響を及ぼします。 MLLP アダプターを使用する場合は、受信確認 (ACK) が必要です。 次のメッセージが送信される前に ACK が受信される必要があるため、遅延が発生することがあります。<br /><br /> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、前のメッセージの ACK を待つことなく次のメッセージを送信できます。 ACK が届くと、それは内部的にそのメッセージと (相互に) に関連付けられます。|  
|サポート ツール|サポート ツールが BizTalk と共にインストールされます。インストールされる場所は、*C:\Program Files (x86)\Microsoft BizTalk Server 20xx\SDK\Utilities\Support Tools* です。<br /><br /> ツールには以下のものがあります。<br /><br /> - BizTalk アセンブリ チェッカー<br /><br /> - MsgBox ビューアー<br /><br /> - PSSDiagForBizTalk<br /><br /> - BizTalk 終端記号のダウンロードに対するインターネットでのショートカット|  
|PowerShell プロバイダー|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] PowerShell プロバイダーは、*C:\Program Files (x86)\Microsoft BizTalk Server 2013\SDK\Utilities\PowerShell* にあります。<br /><br /> 以前のバージョンの BizTalk については、[http://psbiztalk.codeplex.com/](http://psbiztalk.codeplex.com/) にCodePlex PowerShell プロバイダーがあります。|  
|BAM 警告|BizTalk Server 2013 で [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] を使用する場合、BAM 警告を使用するのにデータベース メールが必要になります。 BizTalk Server で SQL Server 2008 R2 を使用する場合、BAM 警告を使用するのに SQL Server Notification Services が必要になります。<br /><br /> 「[BAM 警告](../install-and-config-guides/prepare-your-computer-for-installation.md#BKMK_BAMAlerts)」にはさらに詳細な情報があります。|  
  
> [!IMPORTANT]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] および [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] が別のコンピューターにインストールされている場合、Distributed Transaction Coordinator (MS DTC) がコンピューター間のトランザクションを処理します。 そのため、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] の AlwaysOn 機能は [!INCLUDE[bts2013r2](../includes/bts2013r2-md.md)] と 2013 ではサポートされません。 [!INCLUDE[bts2016](../includes/bts2016-md.md)] から、AlwaysOn 機能が**サポートされます**。 詳細については、「[BizTalk Server 2016 の新機能](../install-and-config-guides/what-s-new-in-biztalk-server-2016.md)」を参照してください。  
  
### <a name="known-issues"></a>既知の問題  
 [BizTalk Server 2013 での既知の問題](http://support.microsoft.com/kb/2954101)