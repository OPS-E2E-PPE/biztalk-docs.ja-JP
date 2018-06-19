---
title: トラブルシューティングで使用するツールとユーティリティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c817384f-e328-439d-9c41-a94ed75670ce
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15030040702b8c9150681b5ff31449d6c4c299d0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008419"
---
# <a name="tools-and-utilities-to-use-for-troubleshooting"></a>トラブルシューティングで使用するツールとユーティリティ
このセクションでは、いくつかのツールと Microsoft BizTalk Server コンポーネントまたは依存関係の問題の根本原因を診断するために使用できるユーティリティについて説明します。  
  
## <a name="event-viewer"></a>イベント ビューアー  
 BizTalk Server のログ情報、警告、およびベースのコンピューターに BizTalk Server のイベント ログにエラー。 BizTalk Server コンポーネントまたは依存関係の問題をトラブルシューティングするとき、イベント ログは、最初に、問題の診断に役立つ情報を検索する場所をする必要があります。 
  
## <a name="network-monitor"></a>ネットワーク モニター  
 ネットワーク モニター ユーティリティを使用して、BizTalk Server とリモート クライアントまたはサーバーの間のネットワーク トラフィックをキャプチャします。 取得したネットワーク トラフィック情報を分析することで、ネットワーク関連の問題を診断できます。  
  
 ネットワーク モニターは、Windows Server で使用できます。  
  
 Windows XP の場合、ネットワーク モニター機能は NETCAP.exe ユーティリティを使用することで提供されます。このユーティリティは、Windows XP CD 収録の Windows サポート ツールと共にインストールされます。 NETCAP.exe ユーティリティ参照の詳細については[Network Monitor Capture Utility の説明](http://go.microsoft.com/fwlink/?LinkId=66227)です。  
  
 ネットワーク モニターを使用してネットワーク トラフィックをキャプチャする方法については、次を参照してください。[ネットワーク モニターを使ってネットワーク トラフィックをキャプチャする方法](http://go.microsoft.com/fwlink/?LinkId=66230)です。  
  
## <a name="fiddler-tool"></a>Fiddler ツール  
 Fiddler を使用すると、BizTalk Server とリモート クライアントまたはサーバーの間のすべての HTTP トラフィックを記録します。 Fiddler は Visual Studio Team Edition for Testers と互換性があり、Visual Studio Team Edition for Testers プロジェクトに追加可能な Web テスト ファイルとして記録を保存できます。  
  
 Fiddler の短所としては、現時点で SSL をサポートしていない、ViewState などの非表示フィールドを自動的には追跡しない、依存要求を除外しないなどの点が挙げられます。  
  
 Fiddler は、「 [http://www.fiddlertool.com](http://go.microsoft.com/fwlink/?LinkId=119605)です。 
  
## <a name="sql-server-profiler"></a>SQL Server Profiler  
 SQL Server に送信される TRANSACT-SQL ステートメントをキャプチャする Microsoft SQL Server Profiler を使用することができ、これらのステートメントからの SQL Server の結果セットです。 BizTalk Server は SQL Server と密接に連携しているので、SQL Server Profile のトレースを分析することで、SQL Server データベースに対する読み取りまたは書き込み時に BizTalk Server で発生する問題を分析するのに役立てることができます。 
  
## <a name="sql-server-query-editor"></a>SQL Server クエリ エディター  
 SQL Server クエリ エディターを使用すると、SQL Server データベースに対して SQL ステートメントを直接実行できます。 この機能は、BizTalk Server データベースに対してクエリを実行するときや、特定のシナリオにおいて BizTalk Server データベースを更新するときに役立つ場合があります。 
  
## <a name="dtctester"></a>DTCTester  
 多くの BizTalk Server ランタイム操作では、トランザクション上でランタイム操作の一貫性を維持するために、Microsoft 分散トランザクション コーディネーター (MSDTC) のサポートが必要です。 MSDTC のトランザクション サポートを使用できないと、それに関連付けられた BizTalk Server ランタイム操作を続行できません。 DTCTester ツールを使用すると、ファイアウォール全体またはネットワークの分散トランザクション サポートを確認できます。 DTCTester ユーティリティでは、ODBC を使用して SQL Server データベースのトランザクション サポートを確認します。したがって、テストするコンピューターのうちの 1 台に SQL Server をインストールする必要があります。 DTCTester の詳細については、次を参照してください。[方法に DTCTester ツールを使用する](http://support.microsoft.com/kb/293799)です。  
  
## <a name="dtcping"></a>DTCPing  
 DTCPing ツールを使用すると、ファイアウォール全体またはネットワークの分散トランザクション サポートを確認できます。 DTCPing ツールは、クライアント コンピューターとサーバー コンピューターの両方にインストールする必要があります。また、このツールは、どちらのコンピューターにも SQL Server がインストールされていない場合に DTCTester ユーティリティの代わりに使用できます。 DTCPing を使用して、分散トランザクション サポートを確認する方法の詳細については、次を参照してください。 [MS DTC ファイアウォールの問題のトラブルシューティング方法](https://support.microsoft.com/help/306843/how-to-troubleshoot-ms-dtc-firewall-issues)です。  
  
## <a name="performance-console"></a>パフォーマンス コンソール  
 パフォーマンス コンソールを使用すると、BizTalk Server 環境のパフォーマンス監視データを取得できます。 参照してください[パフォーマンス カウンター](../core/performance-counters.md) BizTalk Server に含まれているパフォーマンス カウンターの包括的な一覧についてはします。 
  
## <a name="regmon-filemon-and-debugview"></a>RegMon、FileMon、および DebugView  
 RegMon を使用すると、レジストリへのアクセス動作がリアルタイムで表示されます。ここでは、アプリケーションからレジストリへの各呼び出しが一覧表示され、結果が記録されます。 このツールでは、アプリケーションからレジストリ キーへのアクセスが失敗した時点を特定できます。 同様に、FileMon を使用すると、ファイル システムの動作がリアルタイムで表示されます。ここでは、アプリケーションで行われる各システム コールが一覧表示され、結果が登録されます。 Debugview を使用すると、ローカル システムまたは TCP/IP 経由でアクセスできる任意のネットワーク コンピューター上の、デバッグ出力を監視できます。  
  
 管理者は RegMon および FileMon を使用してアプリケーションをテストし、アプリケーションからレジストリまたはファイル システムへの呼び出しで発生したエラーを特定できます。 エラーを特定したら、管理者はファイル システムまたはレジストリ キーの権限を変更するなどの方法によって、エラーを軽減できます。  
  
 管理者は DebugView を使用してアプリケーションをテストし、ローカル システムまたは TCP/IP 経由でアクセスできる任意のネットワーク コンピューター上のデバッグ出力を監視できます。  
  
 これらのユーティリティの詳細については、次を参照してください。 [Windows Sysinternals](https://docs.microsoft.com/sysinternals/)です。 
  
## <a name="debug-diagnostics-tool-of-the-iis-diagnostics-toolkit"></a>IIS 診断ツールキットのデバッグ診断ツール  
 IIS 診断ツールキットのデバッグ診断ツールを使用すると、失敗したプロセスのメモリ ダンプを生成でき、生成されたダンプ ファイルの基本分析を実行できます。 IIS 診断ツールキットのデバッグ診断ツールを使用して、メモリ ダンプをキャプチャする方法の詳細についてを参照してください。 [BizTalk プロセスのメモリ ダンプをキャプチャする方法](../core/how-to-capture-a-memory-dump-of-a-biztalk-process.md)です。