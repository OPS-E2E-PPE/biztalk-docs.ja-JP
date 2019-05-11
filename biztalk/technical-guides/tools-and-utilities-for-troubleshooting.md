---
title: トラブルシューティングのツールとユーティリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56b0946a-56de-47cd-95d9-365722cdbaed
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 069df3178612c86f56552e7863aa7b9d6fa2ccf5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401188"
---
# <a name="tools-and-utilities-for-troubleshooting"></a>トラブルシューティングのツールとユーティリティ
このトピックでは、いくつかのツールと Microsoft の問題の根本原因を診断するために使用できるユーティリティについて説明します。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンポーネントまたは依存関係。  
  
|トラブルシューティング|ツール|新しく使用する機能|  
|---------------------|----------|---------|  
|**SQL Server のトラブルシューティング**|SQL の利用状況モニター|SQL Server 2008 の利用状況モニターは、SQL Server のプロセスおよびこれらのプロセスが現在の SQL Server インスタンスに与える影響についての情報を提供します。 SQL Server 2008 の利用状況モニターの詳細については、次を参照してください。[の利用状況モニター](http://go.microsoft.com/fwlink/?LinkId=146355) (http://go.microsoft.com/fwlink/?LinkId=146355) 、SQL Server のドキュメントにします。 SQL Server Management Studio からの利用状況モニターを開く方法については、次を参照してください。[方法。(SQL Server Management Studio) の利用状況モニターを開く](http://go.microsoft.com/fwlink/?LinkId=135094)(http://go.microsoft.com/fwlink/?LinkId=135094) SQL Server のドキュメントにします。|  
||SQL Server 2008 のデータの収集|SQL Server 2008 では、取得、複数のソースから収集されるデータを保存し使用できるデータ コレクターを提供します。 データ コレクターでは、範囲と SQL Server 2008 を実行しているコンピューター上のデータ収集の頻度を決定するためのデータのコレクション コンテナーを使用することができます。 SQL Server 2008 のデータ コレクションの実装の詳細については、次を参照してください。[データ コレクション](http://go.microsoft.com/fwlink/?LinkId=146356)(http://go.microsoft.com/fwlink/?LinkId=146356) 、SQL Server のドキュメントにします。|  
||**パフォーマンス関連のトラブルシューティング**|Relog ユーティリティでは、パフォーマンス モニターで作成されたログからパフォーマンス カウンターを抽出するために使用し、タブ区切りテキスト ファイル (TSV)、コンマ区切りのテキスト ファイル (CSV)、バイナリ ファイル、および SQL データベースなどの他の形式にデータを変換します。 このデータは、し分析することができ、Log Parser などの他のツールを使用して主要業績評価指標 (Kpi) の統計情報を生成するクエリを実行します。 Relog ユーティリティは、Windows Server 2003 およびそれ以降のバージョンで提供されます。|  
|Windows パフォーマンス分析ツール||Windows パフォーマンス ツールが遅延プロシージャ呼び出しのさまざまなアプリケーションの開始時刻、ブートの問題を含むパフォーマンスの問題の分析用にデザインされ、中断アクティビティ (Dpc および Isr) システムの応答性の問題は、アプリケーションのリソース使用状況、および割り込みの大量発生します。 詳細については、次を参照してください。 [Windows パフォーマンス分析デベロッパー センター](http://go.microsoft.com/fwlink/?LinkId=139763) (http://go.microsoft.com/fwlink/?LinkId=139763)します。|  
|pathping||Pathping では、ターゲット ホストする方法の 1 つまたは複数のルーター ホップでのデータの損失についてを説明します。 これを行うには、pathping は、インターネット制御メッセージ プロトコル (ICMP) パケットをパス内の各ルーターに送信します。 Pathping.exe は、Windows 2000 Server 以降すべてのバージョンの Windows で使用できます。|  
|IOMeter||IOMeter は、ディスク I/O パフォーマンスを測定するためのオープン ソース ツールです。 詳細については、次を参照してください。 [IOMeter](http://go.microsoft.com/fwlink/?LinkId=122412) (http://go.microsoft.com/fwlink/?LinkId=122412)します。 **重要:**、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関する保証をいたしません。 このプログラムは、ユーザー自身の責任で使用してください。|  
|**一般的なトラブルシューティング**|イベント ビューアー<br />-ネットワーク モニター<br />SQL Server Profiler<br />SQL Server クエリ エディター<br />-DTCTester<br />-   DTCPing<br />パフォーマンス コンソール<br />-RegMon<br />-   FileMon<br />-IIS 診断ツールキットの診断ツールをデバッグします。|参照してください[トラブルシューティングで使用するツールとユーティリティ](http://go.microsoft.com/fwlink/?LinkId=154416)(http://go.microsoft.com/fwlink/?LinkId=154416)します。|  
  
## <a name="see-also"></a>参照  
 [テスト用ツール](../technical-guides/tools-for-testing.md)   
 [チェックリスト:BizTalk Server の構成](~/technical-guides/checklist-configuring-biztalk-server.md)