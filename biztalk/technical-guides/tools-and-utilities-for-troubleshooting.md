---
title: "ツールとユーティリティのトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56b0946a-56de-47cd-95d9-365722cdbaed
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 086c7144d39b459a342e3c4f6c5c87f669fffedc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tools-and-utilities-for-troubleshooting"></a>ツールとユーティリティのトラブルシューティング
このトピックは、いくつかのツールと、Microsoft の問題の根本原因を診断するために使用できるユーティリティについて説明します。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンポーネントまたは依存関係。  
  
|トラブルシューティング|ツール|新しく使用する機能|  
|---------------------|----------|---------|  
|**SQL Server のトラブルシューティング**|SQL の利用状況モニター|SQL Server 2008 の利用状況モニターは、SQL Server プロセスおよびこれらのプロセスが現在の SQL Server インスタンスに与える影響に関する情報を提供します。 SQL Server 2008 の利用状況モニターの詳細については、次を参照してください。[利用状況モニター](http://go.microsoft.com/fwlink/?LinkId=146355) (http://go.microsoft.com/fwlink/?LinkId=146355) SQL Server のドキュメントにします。 SQL Server Management Studio からの利用状況モニターを開く方法については、次を参照してください。[する方法: 利用状況モニターを開く」(SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=135094) (http://go.microsoft.com/fwlink/?LinkId=135094) SQL Server のドキュメントにします。|  
||SQL Server 2008 のデータの収集|SQL Server 2008 では、取得して、複数のソースから収集されるデータの保存に使用できるデータ コレクターを提供します。 データ コレクターでは、データ コレクション コンテナーは、スコープと SQL Server 2008 を実行しているコンピューター上のデータ収集の頻度を決定するために使用することができます。 SQL Server 2008 のデータ コレクションの実装の詳細については、次を参照してください。[データ コレクション](http://go.microsoft.com/fwlink/?LinkId=146356)(http://go.microsoft.com/fwlink/?LinkId=146356) SQL Server のドキュメントにします。|  
||**パフォーマンス関連のトラブルシューティング**|Relog ユーティリティは、パフォーマンス カウンターをパフォーマンス モニターで作成されたログから抽出するために使用し、データ タブ区切りのテキスト ファイル (TSV)、コンマ区切りのテキスト ファイル (CSV)、バイナリ ファイル、および SQL データベースなど、他の形式に変換します。 このデータは、解析できますされ、ログ パーサーなど、他のツールを使用して主要業績評価指標 (Kpi) の統計を生成するクエリします。 Relog ユーティリティは、Windows Server 2003 およびそれ以降のバージョンで提供されます。|  
|Windows パフォーマンス分析ツール||Windows パフォーマンス ツールは、遅延プロシージャ呼び出しの広範なアプリケーションの開始時刻、ブートの問題を含めてパフォーマンス問題の分析用にデザインされたされ、アクティビティ (dpc の処理と Isr)、システムの応答を中断の問題は、アプリケーションのリソース使用状況、および割り込みストームが発生します。 詳細については、次を参照してください。 [Windows パフォーマンス分析のデベロッパー センター](http://go.microsoft.com/fwlink/?LinkId=139763) (http://go.microsoft.com/fwlink/?LinkId=139763)。|  
|Pathping||Pathping は、ターゲット ホストするための方法で 1 つまたは複数のルーター ホップでデータ損失の可能性に関する情報を提供します。 これを行うには、pathping は、パス内の各ルーターをインターネット制御メッセージ プロトコル (ICMP) パケットを送信します。 Pathping.exe は、Windows 2000 Server 以来はすべてのバージョンの Windows で使用できます。|  
|IOMeter||IOMeter は、ディスク I/O パフォーマンスの測定に使用されるオープン ソース ツールです。 詳細については、次を参照してください。 [IOMeter](http://go.microsoft.com/fwlink/?LinkId=122412) (http://go.microsoft.com/fwlink/?LinkId=122412)。 **重要:** Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。 このプログラムは、ユーザー自身の責任で使用してください。|  
|**一般的なトラブルシューティング**|イベント ビューアー<br />ネットワーク モニター<br />SQL Server Profiler<br />SQL Server クエリ エディター<br />-DTCTester<br />-DTCPing<br />パフォーマンス コンソール<br />-RegMon<br />-FileMon<br />-IIS 診断ツールキットの診断ツールをデバッグします。|参照してください[トラブルシューティングで使用するツールとユーティリティ](http://go.microsoft.com/fwlink/?LinkId=154416)(http://go.microsoft.com/fwlink/?LinkId=154416)。|  
  
## <a name="see-also"></a>参照  
 [テスト用ツール](../technical-guides/tools-for-testing.md)   
 [チェックリスト: BizTalk Server を構成します。](~/technical-guides/checklist-configuring-biztalk-server.md)