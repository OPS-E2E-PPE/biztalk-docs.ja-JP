---
title: "管理およびパフォーマンス ツール |Microsoft ドキュメント"
description: "タスク、パフォーマンス、および BizTalk Server でのトレースを管理する一般的なツール"
ms.custom: 
ms.date: 09/04/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.ops.admintools
ms.assetid: 932814f7-2ab3-45cb-8bbc-eaf00fcb24a0
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc7420fa6bd59e3653f510e96d41015d266bcebc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="administrative-and-performance-tools"></a>管理およびパフォーマンス ツール 

## <a name="tools-list"></a>ツールの一覧
次のツールを使用すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] グループの管理、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションの展開、取引先とのやり取り、および [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の状態の監視を実行できます。  
  
-   **BizTalk Server 管理コンソール**です。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の主要な管理ツールです。 この管理コンソールでは、BizTalk アプリケーションのすべての展開操作を実行するためのグラフィカル ユーザー インターフェイスを提供します。 たとえば、アプリケーションのアイテムを追加および削除したり、その他の変更をアプリケーションに加えたりするだけでなく、インポート ウィザード、インストール ウィザード、エクスポート ウィザードなどを起動することもできます。  
  
     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して、ライブまたはアーカイブ済みのメッセージ イベントまたはサービス インスタンス データを使用して [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 実装の状態を追跡し、ボトルネックを特定し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境を監視できます。 特定のオーケストレーション、パイプライン、またはメッセージ インスタンスに関する技術的な詳細情報だけでなく、システムで受け取った特定のメッセージのメッセージ フローを表示することもできます。  
  
     使用方法について、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを参照してください[、BizTalk Server 管理コンソールを使用して](../core/using-the-biztalk-server-administration-console.md)です。  
  
-   **BTSTask コマンド ライン ツール**です。 BTSTask を使用すると、コマンド ラインから多くの管理タスクを実行できます。 詳細については、BTSTask を使用して、次を参照してください。 [BTSTask コマンドライン リファレンス](../core/btstask-command-line-reference.md)です。  
  
-   **スクリプトとプログラミング Api**です。 Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
     WMI オブジェクト モデルは、管理 API を公開および簡素化します。 すべての管理 API は、管理対象のすべてのオブジェクトに対して、作成、列挙、変更、および削除操作のいくつかを公開します。 WMI は、この機能をすべての WMI オブジェクトに対して一貫した方法で公開します。  
  
-   **ビジネス アクティビティの監視 (BAM)。** BAM を使用する Microsoft [!INCLUDE[btsOfficeNoVersion](../includes/btsofficenoversion-md.md)] [!INCLUDE[btsExcel](../includes/btsexcel-md.md)]ブック ビジネス プロセスのリアルタイムの包括的なビューを表示する方法をビジネス ユーザーに提供します。 BAM の詳細については、次を参照してください。[を使用したビジネス アクティビティ監視](../core/using-business-activity-monitoring.md)です。  


-   [**BizTalk Health Monitor**](http://blogs.msdn.com/b/biztalkhealthmonitor/ "BizTalk Health Monitor")テーブルの使用法、既知の問題など、BizTalk 環境に関する情報を収集する BizTalk サポート チームが作成されました。 潜在的な問題領域が強調表示されている、レポートが生成されます。 このツールを実行して、BizTalk 環境を維持するために定期的に出力を確認することを検討してください。 これには、BizTalk MsbBox ビューアーが置き換えられます。

-   [**BizTalk 終端記号ツール**](https://www.microsoft.com/download/en/details.aspx?id=2846 "BizTalk 終端記号ツール")通常 BizTalk MsgBox ビューアーの出力にある、一般的なデータベース整合性の問題を解決するのには、BizTalk サポート チームによって作成されました。 一般的なタスクには、インスタンスを削除して、大きなテーブルの削除が含まれます。 BizTalk 終端記号ツールの詳細についてを参照してください[この投稿](http://blogs.msdn.com/b/biztalkcpr/archive/2011/02/10/using-biztalk-terminator-to-resolve-issues-identified-by-biztalk-msgboxviewer.aspx)BizTalk エンジニアのブログを 1 つにします。

-   [**Microsoft BizTalk LoadGen 2007**](https://www.microsoft.com/downloads/details.aspx?FamilyID=c8af583f-7044-48db-b7b9-969072df1689&displaylang=en "Microsoft BizTalk LoadGen 2007")パフォーマンスと、Microsoft BizTalk Server アプリケーションのストレス テストを実行するメッセージ転送の負荷を生成し、BizTalk Server を実行しているインフラストラクチャのパフォーマンスを監視するパフォーマンス カウンターを提供します。

-   [**BizTalk Server のベスト プラクティス アナライザー**](https://www.microsoft.com/downloads/details.aspx?FamilyID=93d432fe-1370-4b6d-aaa8-a0c43c30f5ab "BizTalk Server のベスト プラクティス アナライザー")読み取りのみレポートを作成して構成レベルの検証を実行します。 ベスト プラクティス アナライザーは、Windows Management Instrumentation (WMI) クラス、SQL Server データベース、およびレジストリ エントリなど、さまざまな情報のソースからデータを収集します。 ベスト プラクティス アナライザーでは、データを使用して、展開の構成を評価します。 ベスト プラクティス アナライザーは、任意のシステム設定は変更されず、自己調整ツールではありません。

-   [**パフォーマンス分析のログ (PAL)**](http://www.codeplex.com/PAL "パフォーマンス分析のログ (PAL)")はパフォーマンス モニター カウンター ログ (任意の既知形式) に読み取り、分析を使用して、強力なツール、複雑な既知(提供) のしきい値。 このツールでは、視覚的に重要なパフォーマンス カウンターをグラフ化し、しきい値を超えたときにアラートをスローする HTML ベース レポートを生成します。

-   [**DebugView for Windows**](https://technet.microsoft.com/en-us/sysinternals/bb896647.aspx "DebugView for Windows")は、アプリケーションをデバッグ出力をローカル システムまたは TCP/IP 経由でアクセスできるネットワーク上のコンピューターを監視することができます。 デバッガーのアプリケーションまたはデバイス ドライバーを生成するデバッグ出力をキャッチする必要はありません、カーネル モードと Win32 デバッグ出力の両方を表示できます。 また非標準のデバッグ出力の Api を使用するには、アプリケーションまたはドライバーを変更する必要があります。

-   [**ログ パーサー 2.2**](https://www.microsoft.com/downloads/details.aspx?familyid=890CD06B-ABF8-4C25-91B2-F8D975CF8C07&displaylang=en "Log Parser 2.2") windows のキーのデータ ソースに加え、ログ ファイル、XML ファイルおよび CSV ファイルなどのテキスト ベースのデータへのユニバーサル クエリ アクセスを提供する強力な多様なツールですイベント ログ、レジストリ、ファイル システム、および Active Directory などのオペレーティング システムです。

-   [**エクスプ ローラーの処理**](https://technet.microsoft.com/en-us/sysinternals/bb896653.aspx "プロセス エクスプ ローラー")は DLL バージョンの問題、またはハンドルのリークを追跡するために役立ちますし、Windows の方法とアプリケーションの作業を理解できるようにします。

-   [**TCP トレース**](http://www.pocketsoap.com/tcptrace/ "TCP トレース")クライアントとサーバー間でテキスト ベースのネットワーク トラフィックを監視するために使用します。 トラベル ネットワーク経由でメッセージを表示する SOAP、HTTP、POP3 などのようにアダプターを使用しているときに便利です。

-   [**DTCPing**](https://www.microsoft.com/downloads/details.aspx?displaylang=en&FamilyID=5e325025-4dcd-4658-a549-1d549ac17644 "DTCPing") BizTalk のマルチ サーバー展開でわかります多くの場合、Microsoft DTC ファイアウォール問題のトラブルシューティングに役立つよう設計されています。

  
## <a name="see-also"></a>参照  
 [アプリケーションの展開と管理ツール](../core/application-deployment-and-management-tools.md)