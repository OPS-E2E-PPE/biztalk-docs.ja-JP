---
title: BizTalk Server 2016 でのハードウェアおよびソフトウェア |Microsoft ドキュメント
description: BizTalk Server 2016 をインストールするソフトウェアの前提条件とサポートされているバージョンを一覧表示します。
ms.custom: ''
ms.prod: biztalk-server
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f6120afd-310e-4155-8c23-aadb5b9a1a35
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d473d3bf5be874edb430c80032935ddf2c7937bf
ms.sourcegitcommit: 770523695b34cc54db81f7ab7eba46f2bc19baec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
ms.locfileid: "31816925"
---
# <a name="hardware-and-software-requirements-for-biztalk-server-2016"></a>BizTalk Server 2016 のハードウェアとソフトウェアの要件

## <a name="hardware-requirements"></a>ハードウェア要件
次の表に、BizTalk Server コンピューターの最小ハードウェア要件をリストします。 運用環境の場合、トラフィックの量によっては、サーバーにこれらを超えるハードウェア要件が求められることがあります。 

| リソース  |最小要件 |
| --- | --- |
|コンピューターおよびプロセッサ | 次の条件を満たす Intel Pentium 互換の CPU を搭載したコンピューター: <ul><li>1 GHz 以上 (シングル プロセッサの場合)</li><li>900 MHz 以上 (ダブル プロセッサの場合)</li><li>700 MHz 以上 (クワド プロセッサの場合)</li></ul> **注**: ハイパースレッディングおよびデュアルコア プロセッサがサポートされます。<br/><br/>64 ビット バージョンの BizTalk Server をインストールするには、64 ビット オペレーティング システムが x64 ベース システム上で実行されていることが必要です。 コンピューターの CPU が AMD64 (x86-64) または Extended Memory 64-bit Technology (EM64T) プロセッサ アーキテクチャ互換の場合は、x64 ベースのシステムと見なされます。<br/><br/>Itanium ベースのシステムでは、BizTalk Server はサポートされません。 |
|[メモリ] | 2 GB 以上|
|ハード ディスク  |10 GB の使用可能なハード ディスク領域 (オペレーティング システムおよびすべての必要なソフトウェアを含む完全インストールの場合)。 ハード ディスクは NTFS でフォーマットされている必要があります。|

> [!TIP] 
> ここにリストされているのは最小のハードウェア要件です。 環境はそれぞれ異なり、ご使用の環境ではこれらを超える要件が必要となる可能性は十分あります。 「[BizTalk Server ソリューションのインストール、サイズ変更、配置、およびメンテナンスを行うための推奨事項](http://social.technet.microsoft.com/wiki/contents/articles/666.recommendations-for-installing-sizing-deploying-and-maintaining-a-biztalk-server-solution.aspx)」を参照してください。 


## <a name="software-requirements--supported-versions"></a>ソフトウェアの要件とサポートされるバージョン

| ソフトウェア  |   バージョン |  このソフトウェアを必要とする機能 | 
| --- | --- | --- | 
| Microsoft Windows | <ul><li>Windows Server 2016</li><li>Windows Server 2012 R2</li><li>Windows 10</li><li>Windows 8.1 </li></ul> | | 
| インターネット インフォメーション サービス (IIS)   | オペレーティング システムに付属するバージョンです。<br/><br/> IIS バージョンのリストについては、[KB 224609](https://support.microsoft.com/kb/224609) を参照してください。 | スケーラブルな Web アプリケーション インフラストラクチャを提供します。これは、EDI、BAM、および SharePoint アダプターに必要です。 |
| Windows Identity Foundation | **機能**としてオペレーティング システムに含まれます。 | 省略可。 <br/><br/>BizTalk Server のインストール時に自動的にインストールされる、Windows SharePoint Services の Client Side Object Model (CSOM) で使用されます。 | 
| Microsoft SharePoint  | <ul><li>SharePoint Services 2016</li><li>SharePoint Services 2013 SP1</li><li>SharePoint Services オンライン</li></ul>  | 省略可。 <br/><br/>SharePoint Services との間でメッセージを送受信する場合は、SharePoint Services コンピューターが必要です。 SharePoint Services は、BizTalk Server と同じコンピューターにインストールできますが、別のコンピューターにインストールすることもできます。 |
| Microsoft Office  | <ul><li>Microsoft Office Excel 2016</li><li>Microsoft Office Excel 2013</li></ul>**注**: BizTalk Server でサポートされるのは、32 ビット版の Office のみです。  | 省略可。 <br/><br/>ビジネス プロセスのリアルタイム ビューを表示するために、ビジネス アクティビティの監視 (BAM) で必要です。 | 
| [Microsoft .NET Framework]  | <ul><li>.NET framework 4.7 (以降で[CU2](https://support.microsoft.com/kb/4021095))</li><li>.NET Framework 4.6.*x* </li></ul>**注**: Visual Studio で作成された BizTalk プロジェクトでは、Visual Studio のビルド ターゲットが .NET Framework のバージョンに設定する必要があります。 | BizTalk Server のすべてのマネージ コンポーネントで必要です。 | 
| Microsoft Visual Studio |Visual Studio 2015 | 省略可。 <br/><br/>BizTalk Server アプリケーションをビルドする開発環境を提供します。 Ultimate Edition の使用をお勧めしますが、Premium と Professional もサポートしています。 BizTalk Server 開発ツールと SDK で必要です。 |
| Microsoft Visual C++ 2013 再頒布可能パッケージ | x86 および x64 バージョンが必要です。 「[Visual Studio 2013 の Visual C++ 再頒布可能パッケージ](https://support.microsoft.com/help/3179560/update-for-visual-c-2013-and-visual-c-redistributable-package)」からダウンロードします。    | 必須。<br/><br/>Microsoft Visual C++ 再頒布可能パッケージは、Visual C++ で開発されたアプリケーションの実行に必要な Visual C++ ライブラリの実行時コンポーネントを、Visual C++ がインストールされていないコンピューターにインストールします。<br/><br/>**注**: <br/> Visual Studio 2015 が使用されている場合でも、2013 バージョンが必要です。|
| Microsoft SQL Server  | <ul><li>Microsoft SQL Server 2016</li><li>Microsoft SQL Server 2014 SP1</li></ul> | BizTalk Server ランタイム、EDI、および BAM で必要です。 <br/><br/>最適なパフォーマンスを実現するには、SQL Server の Enterprise Edition をお勧めします。 BizTalk Server SDK の全機能を使用する場合や、Visual Studio から BizTalk Server アプリケーションを展開する場合には、SQL Server 開発ツールをインストールします。 <br/><br/>その他の考慮事項: <ul><li>SQL Server AlwaysOn 可用性グループ (AG) を使用するには、SQL Server 2016 以降のバージョンを使用します。 MSDTC をサポートしているのは SQL Server 2016 AlwaysOn AG のみです。BizTalk には MSDTC が必要です。 </li><li>BAM リアルタイム集計 (RTA) は、SQL Server の Standard Edition ではサポートされません。 BAM RTA を使用するには、SQL Server Enterprise Edition をインストールします。</li><li>SQL Server Express Edition を使用することはお勧めしません。 Express Edition には、BizTalk Server に必要な特定の機能が含まれていません。</li><li>BizTalk Server では、バイナリ照合順序を除く、大文字と小文字を区別する/区別しないすべての SQL Server 照合順序がサポートされています。 バイナリ照合順序はサポートされません。</li></ul> |  |
| SQL Server データベース メール  | SQL Server に付属するバージョンです。 [SQL Server データベース メールを構成](https://msdn.microsoft.com/library/hh245116(v=sql.130).aspx)します。| 省略可。 <br/><br/>BAM 警告を使用する場合に必要です。 | 
| SQL XML | SQL XML 4.0 Service Pack 1。 [SqlXml 4.0 Service Pack 1 (SP1) をダウンロード](https://www.microsoft.com/en-us/download/details.aspx?id=30403)します。 | BizTalk Server ランタイム、管理ツール、および BAM で必要です。 <br/><br/> SQLXML は、SQL Server データベースに対する XML サポートを有効にします。 SQLXML により、開発者は XML とリレーショナル データとのギャップを解消できます。 既存のリレーショナル データの XML ビューを作成し、XML ファイルと同じようにビューを操作することができます。 <br/><br/>**注**: <br/>これは、再頒布可能 CAB ファイルで自動的にインストールされます。 SQL XML には、CAB ファイルに含まれていない独自のソフトウェア要件 (`.NET Framework 3.5` や `.NET Framework 2.0` など) がある場合があります。 BizTalk Server からインターネットにアクセスできる場合、SQL XML ソフトウェア要件は自動的にインストールされます。 BizTalk Server がインターネットにアクセスできない場合は、SQL XML ソフトウェア要件を手動でインストールします。| 
| WinSCP | WinSCP バージョン 5.7.7。 [WinSCP をダウンロード](http://winscp.net)します。| SFTP アダプターを使用する場合に必要です。 |
| MQSeries アダプター | <ul><li>IBM WebSphere MQ 8</li><li>IBM WebSphere MQ 9 (BizTalk 2016 CU4 以降)</li></ul> | 省略可。<br/>IBM WebSphere MQ を使用する場合にのみ必要です。 |
|LOB およびエンタープライズ システム | [サポートされている基幹業務 (LOB) とエンタープライズ システム](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)サポートされているバージョンを一覧表示します。 | BizTalk Adapter Pack でアダプターを使用する場合に必要です。 <br/><br/> [BizTalk Adapter Pack](../adapters-and-accelerators/biztalk-adapter-pack.md)使用可能なシステムのアダプタを一覧表示します。 |

## <a name="service-pack-and-cumulative-update-support"></a>Service Pack と累積した更新プログラムのサポート

すべてのサービス パック、累積的更新プログラム、セキュリティ更新プログラムと修正プログラムは、BizTalk Server でサポートされます。 Windows、SQL Server、Visual Studio、その他のインストールされているプログラムの最新の更新プログラムをインストールすることを強くお勧めします。 マイクロソフト製品の Service Pack はその製品の基本サポートに基づいてサポートされます。 BizTalk Server、SQL Server、Visual Studio、その他の Microsoft プログラムについては、[サポート ライフサイクルのインデックス](http://go.microsoft.com/fwlink/p/?LinkID=151890)を参照してください。

[BizTalk Server のサービス パックと累積更新プログラムの一覧](https://support.microsoft.com/help/2555976)

 ## <a name="next-step"></a>次の手順
 
 [前提条件の設定とインストール](../install-and-config-guides/set-up-and-install-prerequisites-for-biztalk-server-2016.md)
