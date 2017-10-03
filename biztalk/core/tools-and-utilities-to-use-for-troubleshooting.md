---
title: "トラブルシューティングで使用するツールとユーティリティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c817384f-e328-439d-9c41-a94ed75670ce
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86eab8504ab3dff93370783cca6c8fce1a0b9388
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tools-and-utilities-to-use-for-troubleshooting"></a>トラブルシューティングで使用するツールとユーティリティ
ここでは、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のコンポーネントまたは依存関係で発生する問題の根本的な原因を診断するのに役立つ、いくつかのツールとユーティリティについて説明します。  
  
## <a name="event-viewer"></a>イベント ビューアー  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ベースのコンピューターのイベント ログに、情報、警告、およびエラーが記録されます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のコンポーネントまたは依存関係で発生する問題のトラブルシューティングを行うときには、最初にイベント ログで、診断の手掛かりになる情報を探します。 イベント ビューアーの詳細については、Windows のマニュアルを参照してください。  
  
## <a name="network-monitor"></a>ネットワーク モニター  
 ネットワーク モニター ユーティリティを使用すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] とリモート クライアントまたはリモート サーバーとの間のネットワーク トラフィック情報を取得できます。 取得したネットワーク トラフィック情報を分析することで、ネットワーク関連の問題を診断できます。  
  
 ネットワーク モニターで使用できる[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]を通じて、 **Windows コンポーネントの追加/削除**で用意されているオプション**プログラムの追加/削除**です。  
  
 Windows XP の場合、ネットワーク モニター機能は NETCAP.exe ユーティリティを使用することで提供されます。このユーティリティは、Windows XP CD 収録の Windows サポート ツールと共にインストールされます。 NETCAP.exe ユーティリティ参照の詳細については[Network Monitor Capture Utility の説明](http://go.microsoft.com/fwlink/?LinkId=66227)です。  
  
 ネットワーク モニターを使用してネットワーク トラフィックをキャプチャする方法については、次を参照してください。[ネットワーク モニターを使ってネットワーク トラフィックをキャプチャする方法](http://go.microsoft.com/fwlink/?LinkId=66230)です。  
  
## <a name="fiddler-tool"></a>Fiddler ツール  
 Fiddler を使用すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] とリモート クライアントまたはリモート サーバーとの間のすべての HTTP トラフィックを記録できます。 Fiddler は Visual Studio Team Edition for Testers と互換性があり、Visual Studio Team Edition for Testers プロジェクトに追加可能な Web テスト ファイルとして記録を保存できます。  
  
 Fiddler の短所としては、現時点で SSL をサポートしていない、ViewState などの非表示フィールドを自動的には追跡しない、依存要求を除外しないなどの点が挙げられます。  
  
 Fiddler は、「 [http://www.fiddlertool.com](http://go.microsoft.com/fwlink/?LinkId=119605)です。Fiddler を使用する方法の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=84814](http://go.microsoft.com/fwlink/?LinkId=84814)です。  
  
## <a name="sql-server-profiler"></a>SQL Server Profiler  
 Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Profiler を使用すると、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] に送信される Transact-SQL ステートメントや、これらのステートメントで返される [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] の結果セットを取得できます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] と密接に連携しているので、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Profile のトレースを分析することで、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] データベースに対する読み取りまたは書き込み時に BizTalk Server で発生する問題を分析するのに役立てることができます。 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Profiler を使用する方法については、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] のマニュアルを参照してください。  
  
## <a name="sql-server-query-editor"></a>SQL Server クエリ エディター  
 SQL Server クエリ エディターを使用すると、SQL Server データベースに対して SQL ステートメントを直接実行できます。 この機能は、BizTalk Server データベースに対してクエリを実行するときや、特定のシナリオにおいて BizTalk Server データベースを更新するときに役立つ場合があります。 クエリ エディターの詳細については、[!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)] または [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] のマニュアルを参照してください。  
  
## <a name="dtctester"></a>DTCTester  
 多くの BizTalk Server ランタイム操作では、トランザクション上でランタイム操作の一貫性を維持するために、Microsoft 分散トランザクション コーディネーター (MSDTC) のサポートが必要です。 MSDTC のトランザクション サポートを使用できないと、それに関連付けられた BizTalk Server ランタイム操作を続行できません。 DTCTester ツールを使用すると、ファイアウォール全体またはネットワークの分散トランザクション サポートを確認できます。 DTCTester ユーティリティでは、ODBC を使用して SQL Server データベースのトランザクション サポートを確認します。したがって、テストするコンピューターのうちの 1 台に SQL Server をインストールする必要があります。 DTCTester の詳細については、次を参照してください。[方法に DTCTester ツールを使用する](http://support.microsoft.com/kb/293799)です。  
  
## <a name="dtcping"></a>DTCPing  
 DTCPing ツールを使用すると、ファイアウォール全体またはネットワークの分散トランザクション サポートを確認できます。 DTCPing ツールは、クライアント コンピューターとサーバー コンピューターの両方にインストールする必要があります。また、このツールは、どちらのコンピューターにも SQL Server がインストールされていない場合に DTCTester ユーティリティの代わりに使用できます。 DTCPing を使用して、分散トランザクション サポートを確認する方法の詳細については、次を参照してください。 [MS DTC ファイアウォールの問題のトラブルシューティング方法](http://go.microsoft.com/fwlink/?LinkId=61915)です。  
  
## <a name="performance-console"></a>パフォーマンス コンソール  
 パフォーマンス コンソールを使用すると、BizTalk Server 環境のパフォーマンス監視データを取得できます。 参照してください[パフォーマンス カウンター](../core/performance-counters.md)に含まれているパフォーマンス カウンターの包括的な一覧について[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 パフォーマンス コンソールの使用方法の詳細については、Windows のドキュメントを参照してください。  
  
## <a name="regmon-filemon-and-debugview"></a>RegMon、FileMon、および DebugView  
 RegMon を使用すると、レジストリへのアクセス動作がリアルタイムで表示されます。ここでは、アプリケーションからレジストリへの各呼び出しが一覧表示され、結果が記録されます。 このツールでは、アプリケーションからレジストリ キーへのアクセスが失敗した時点を特定できます。 同様に、FileMon を使用すると、ファイル システムの動作がリアルタイムで表示されます。ここでは、アプリケーションで行われる各システム コールが一覧表示され、結果が登録されます。 Debugview を使用すると、ローカル システムまたは TCP/IP 経由でアクセスできる任意のネットワーク コンピューター上の、デバッグ出力を監視できます。  
  
 管理者は RegMon および FileMon を使用してアプリケーションをテストし、アプリケーションからレジストリまたはファイル システムへの呼び出しで発生したエラーを特定できます。 エラーを特定したら、管理者はファイル システムまたはレジストリ キーの権限を変更するなどの方法によって、エラーを軽減できます。  
  
 管理者は DebugView を使用してアプリケーションをテストし、ローカル システムまたは TCP/IP 経由でアクセスできる任意のネットワーク コンピューター上のデバッグ出力を監視できます。  
  
 これらのユーティリティの詳細については、Windows Sysinternals の Web サイトを参照してください。 [http://www.microsoft.com/technet/sysinternals/default.mspx](http://go.microsoft.com/fwlink/?LinkId=66235)です。  
  
## <a name="debug-diagnostics-tool-of-the-iis-diagnostics-toolkit"></a>IIS 診断ツールキットのデバッグ診断ツール  
 IIS 診断ツールキットのデバッグ診断ツールを使用すると、失敗したプロセスのメモリ ダンプを生成でき、生成されたダンプ ファイルの基本分析を実行できます。 IIS 診断ツールキットのデバッグ診断ツールを使用して、メモリ ダンプをキャプチャする方法の詳細についてを参照してください。 [BizTalk プロセスのメモリ ダンプをキャプチャする方法](../core/how-to-capture-a-memory-dump-of-a-biztalk-process.md)です。