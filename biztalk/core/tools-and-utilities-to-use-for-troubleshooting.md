---
title: トラブルシューティングで使用するツールとユーティリティ |Microsoft Docs
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
ms.openlocfilehash: b13d6d57ff393fd5ec1336ec1639ba58fd8cda23
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379830"
---
# <a name="tools-and-utilities-to-use-for-troubleshooting"></a>トラブルシューティングで使用するツールとユーティリティ
このセクションでは、いくつかのツールと Microsoft BizTalk Server コンポーネントまたは依存関係の問題の根本原因を診断するために使用できるユーティリティについて説明します。  
  
## <a name="event-viewer"></a>イベント ビューアー  
 BizTalk Server ログについては、警告、およびベースのコンピューターに BizTalk Server のイベント ログにエラー。 BizTalk Server コンポーネントまたは依存関係の問題をトラブルシューティングするとき、イベント ログには、まず、問題の診断に役立つ情報を検索する必要があります。 
  
## <a name="network-monitor"></a>ネットワーク モニター  
 BizTalk Server とリモート クライアントまたはサーバー間のネットワーク トラフィックをキャプチャするのにには、ネットワーク モニター ユーティリティを使用します。 キャプチャされたネットワーク トラフィックを分析し、ネットワークの診断に関連する問題です。  
  
 ネットワーク モニターは、Windows Server で使用できます。  
  
 ネットワーク モニターの機能は、Windows xp、Windows XP CD 収録の Windows サポート ツールと共にインストールされている NETCAP.exe ユーティリティを使用して提供されます。 NETCAP.exe ユーティリティを参照の詳細については[Network Monitor Capture Utility の説明](http://go.microsoft.com/fwlink/?LinkId=66227)します。  
  
 ネットワーク モニターを使用してネットワーク トラフィックをキャプチャする方法については、次を参照してください。[ネットワーク モニターを使用してネットワーク トラフィックのキャプチャ方法](http://go.microsoft.com/fwlink/?LinkId=66230)します。  
  
## <a name="fiddler-tool"></a>Fiddler ツール  
 Fiddler を使用すると、BizTalk Server とリモート クライアントまたはサーバー間のすべての HTTP トラフィックを記録します。 Fiddler は、Visual Studio Team Edition for Testers と互換性のある Visual Studio Team edition for Testers プロジェクト追加できる Web テスト ファイルとして録画を保存することができます。  
  
 Fiddler の短所は SSL を現在サポートされないため、ViewState などの非表示フィールドを自動的に追跡しません、依存する要求をフィルター処理しないことです。  
  
 Fiddler は、「 [ http://www.fiddlertool.com](http://go.microsoft.com/fwlink/?LinkId=119605)します。 
  
## <a name="sql-server-profiler"></a>SQL Server Profiler  
 Microsoft SQL Server Profiler は、SQL Server に送信される TRANSACT-SQL ステートメントをキャプチャするために使用でき、これらのステートメントから SQL Server の結果を設定します。 BizTalk Server は SQL Server と密接に連携しているので、SQL Server Profile のトレースを分析することで、SQL Server データベースに対する読み取りまたは書き込み時に BizTalk Server で発生する問題を分析するのに役立てることができます。 
  
## <a name="sql-server-query-editor"></a>SQL Server クエリ エディター  
 SQL Server データベースに対して直接 SQL ステートメントを実行する SQL Server クエリ エディターを使用できます。 この機能は、BizTalk Server データベースに対してクエリを実行するときや、特定のシナリオにおいて BizTalk Server データベースを更新するときに役立つ場合があります。 
  
## <a name="dtctester"></a>DTCTester  
 多くの BizTalk Server ランタイム操作では、トランザクション上でランタイム操作の一貫性を維持するために、Microsoft 分散トランザクション コーディネーター (MSDTC) のサポートが必要です。 MSDTC のトランザクション サポートを使用できないと、それに関連付けられた BizTalk Server ランタイム操作を続行できません。 DTCTester ツールを使用して、ファイアウォール全体またはネットワークは、分散トランザクション サポートを確認します。 DTCTester ユーティリティでは、ODBC を使用して SQL Server データベースのトランザクション サポートを確認し、ためテスト対象コンピューターの 1 つの SQL Server がインストールされていることが必要です。 DTCTester の詳細については、次を参照してください。[使用 DTCTester ツールをどのように](http://support.microsoft.com/kb/293799)します。  
  
## <a name="dtcping"></a>DTCPing  
 DTCPing ツールを使用して、ファイアウォール全体またはネットワークは、分散トランザクション サポートを確認します。 DTCPing ツールは、クライアントとサーバーの両方のコンピューターにインストールする必要があり、DTCTester ユーティリティに代わる優れた手段は、どちらのコンピューターに SQL Server がインストールされていない場合。 DTCPing を使用して、分散トランザクション サポートを確認の詳細については、次を参照してください。 [MS DTC ファイアウォールの問題のトラブルシューティングを行う方法](https://support.microsoft.com/help/306843/how-to-troubleshoot-ms-dtc-firewall-issues)します。  
  
## <a name="performance-console"></a>パフォーマンス コンソール  
 パフォーマンス コンソールを使用して、パフォーマンスの監視、BizTalk Server 環境でのデータをキャプチャします。 参照してください[パフォーマンス カウンター](../core/performance-counters.md) BizTalk Server に含まれているパフォーマンス カウンターの包括的な一覧についてはします。 
  
## <a name="regmon-filemon-and-debugview"></a>RegMon、FileMon、および DebugView  
 RegMon をアプリケーションで、レジストリへの各呼び出しの一覧を表示して、結果をログ記録、リアルタイムでレジストリへのアクセス アクティビティが表示されます。 このツールを使用すると、アプリケーションがレジストリ キーにアクセスできないときに特定できます。 同様に、FileMon は、各システム コールがアプリケーションの一覧を表示して、結果が登録、リアルタイムでファイル システムの使用状況を表示します。 Debugview を使用して、デバッグ出力をローカル システムまたは TCP/IP 経由でアクセスできるネットワーク上のコンピューターを監視できます。  
  
 RegMon および FileMon には、アプリケーションをテストして、アプリケーションがレジストリやファイル システムを作成するすべての呼び出しのエラーを特定して、管理者が有効にします。 管理者は、しを緩和できますエラーをたとえば、ファイル システムまたはレジストリ キーのアクセス許可を変更することで。  
  
 DebugView に、アプリケーションをテストおよびデバッグ出力をローカル システムまたは TCP/IP 経由でアクセスできるネットワーク上のコンピューターを監視できます。  
  
 これらのユーティリティの詳細については、次を参照してください。 [Windows Sysinternals](https://docs.microsoft.com/sysinternals/)します。 
  
## <a name="debug-diagnostics-tool-of-the-iis-diagnostics-toolkit"></a>IIS 診断ツールキットのデバッグ診断ツール  
 IIS 診断ツールキットのデバッグ診断ツールは、失敗したプロセスのメモリ ダンプを生成し、生成されたダンプ ファイルの基本的な分析を実行できます。 詳細については、IIS 診断ツールキットのデバッグ診断ツールを使用してメモリ ダンプを取得する方法を参照してください。 [BizTalk プロセスのメモリ ダンプをキャプチャする方法](../core/how-to-capture-a-memory-dump-of-a-biztalk-process.md)します。